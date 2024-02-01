# C++ STL unordered set and map (해시)
```cpp
#include <set>
#include <map>
```

## 이진 트리
각 노드의 자식이 2개 이하인 트리

## 이진 검색 트리
왼쪽 서브트리의 모든 값은 부모의 값보다 작고 오른쪽 서브트리의 모든 값은 부모의 값보다 큰 이진 트리
* 트리를 쓰는 이유?
    * `insert`, `erase`, `find`, `update`를 모두 $O(lgN)$에 할 수 있다.
    * 즉 **CRUD가 빈번**하게 일어나면서 **원소의 대소와 관련한 성질**이 있을 때 이진 검색 트리 사용
* 해시 쓰면 되는거 아니냐?
    * **크기 순으로 정렬**된다는 장점이 있음.​

## 원소의 삭제
원소 삭제하고 오른쪽 자식의 가장 왼쪽에 있는 자식(or vice versa)으로 대체

## 트리의 편향
원소가 크기 순으로 삽입되면 원소들이 일직선으로 연결되는 편향된 트리가 되는데 이 경우에 높이가 $O(N)$에 가깝게 되므로 사실상 Linked List와 차이가 없어진다.  
이를 해결하기 위한 트리를 자가 균형 트리(Self-Balancing Tree)라고 하며 AVL 트리와 Red Black 트리가 있다.

> 문제를 풀다가 뭔가 `set`, `map` 느낌의 성질이 필요하면서 특히 `lower_bound`나 `prev`, `next` 이런걸 사용해야만 풀리는 문제라면 꼭 STL `set`, `map`으로 해결하기

## STL
### `set`
```cpp
set<int> s;
s.insert(-10);
s.erase(-10);  // 삭제 성공(값이 set에 있을 때) 시에 1, 아니면 0을 반환
//( 맨 뒤의 값을 삭제할 때는 s.erase(prev(s.end())) 해 줘야됨 ..) 💥
if(s.find(값) != s.end())  // then 값이 s에 있는 것;
else   //then 값이 s에 없는 것;
s.size();
s.count(값);   //값이 몇 개 있는가?
for(auto a : s) cout << a << ' ';
s.empty();
​
set<int>::iterator it1 = s.begin();
it1++;
auto it2= prev(it1);
it2 = next(it1);
advance(it2, -2);   // 이터레이터를 이동시킴!
auto it3 = s.lower_bound(값);
auto it4 = s.find(값);
cout << *it4 << '\n';   // 이런 식으로 이터레이터 기반 값 출력
//equal_range()
```

### `multiset`
* `erase`
    * 해당 요소를 다 지워버림
* `find`
    * 아무 거나 반환함
> `find`로 `iterator`를 반환하여 `erase` 인자로 넘겨주면 하나만 지울 수 있음.  
> `lower_bound`도 가능한듯?

### `map`
```cpp
​map<string, int> m;
//  ^key    ^value
m["hi"] = 12;
m["wumonga"] = 2;
cout << m.size() << '\n';
if(m.find("hi") != m.end())   // then "hi"가 있음
else   // then "hi"가 없음
m.erase("wumonga");
for(auto a : m) {
    cout << a.first << ' ' << a.second << '\n';
}
auto it1 = m.find("gogo");
cout << it1->first << ' ' << it2->second << '\n';
```
