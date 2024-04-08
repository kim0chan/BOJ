# 분리 집합 Disjoint Set
서로소 집합이라고도 한다.  
전체집합 U에 대해 U의 분리집합 A, B는 다음을 만족한다.
* A, B는 U의 부분집합이다.
* A, B는 공통 원소를 가지지 않는다.
* A, B의 합집합은 전체집합 U이다. (A, B에 속하지 않는 U의 원소가 없어야 한다.)  
💥 분리 집합이 3개 이상일 때도 마찬가지이다.

## Union-Find 알고리즘
분리집합을 구현하는 알고리즘이다.  
각 그룹을 트리의 형태로 표현한다.  
각 노드마다 부모 노드 번호를 기록하여 그래프를 트리 구조로 나타낸다.  
이렇게 나타낸 트리는 항상 최상위 노드인 root 노드를 가지게 되는데 이 root 노드를 통해 그룹을 구별할 수 있게 된다.  
(root 노드는 항상 부모로 자기 자신, root를 갖는다.)  
💥 두 노드가 같은 그룹인지 판단하기 위해서는 소속한 그룹의 root를 비교하면 된다.

## Find : root 노드를 찾는 작업
```cpp
int Find(int x) {
  if (x == parent[x])  return x;
  return Find(parent[x]);
}
```

## Union : 두 트리를 병합하는 작업
```cpp
void Union(int x, int y) {
  x = Find(x);
  y = Find(y);
​
  if (x != y) {  // 만약 두 노드가 다른 그룹에 속해있다면 한 쪽의 트리를 다른 쪽에 붙인다.
    parent[x] = y;
  }
}
```

## Path Compression - 최적화 : 경로 압축
새로 생성되는 관계가 `(i, i + 1)` 노드끼리 발생한다고 하면  
같은 그룹에 속해 있는지 확인하기 위해 root까지 타고 올라가야 하고 이는 비효율적이다.  
따라서 한 노드에 대해 `Find`를 수행할 때마다 그 노드의 부모 노드를 항상 root 노드로 만들어준다면  
더 효율적으로 root 노드를 찾을 수 있을 것이다.
```cpp
int Find (int x) {
  if (x == parent[x])  return x;
  return parent[x] = Find(parent[x]);
}
```

## Union by Rank - 최적화
`Find`의 시간복잡도는 트리의 높이에 의해 결정된다.  
Union 연산 시 항상 높이가 낮은 트리를 높이가 높은 트리에 붙임으로써 시간복잡도를 줄일 수 있다.  
> 높이가 높은 트리가 낮은 트리에 붙을 경우, 합쳐진 트리의 높이가 더 많이 증가하기 때문이다.
```cpp
void Union(int x, int y) {
	x = Find(x);
	y = Find(y);
​
	if (x != y) {
		if (node_rank[x] < node_rank[y])	parent[x] = y;
		else if (node_rank[x] > node_rank[y]) parent[y] = x;
		else {
			parent[x] = y;
			node_rank[y]++;
		}
	}
}​
```

초기에 `rank(size)`는 1, `parent`는 자기 자신으로 설정하는 것 같아 보인다.  
`node_rank[x] == node_rank[y]` 일 때  
`parent[x] = y;`  
로 설정하고  
`node_rank[x]++;`  
하라고 블로그엔 되어있는데  
관념적으로 생각했을 때는 `node_rank[y]++;`가 맞는 것 같다.  
실제 실행했을 때 더 빠르기도 하고