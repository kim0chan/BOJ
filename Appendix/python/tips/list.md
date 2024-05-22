# Python List
```py
list_1 = []         # 직관적 생성
list_2 = list()     # 명시적 생성
```
### Believe it or not 👀
* `[]`는 리터럴을 사용하여 즉시 리스트를 생성하기 때문에 약간 더 빠름
* `list()`는 `list` 클래스의 생성자를 호출하는 방식이고, 함수 호출 오버헤드 때문에 아주 미세하게 느림

## Indexing and Slicing
```py
a = [0, 1, 2, 3]
a[-1]   # 마지막 원소인 3
```

## List Operations

## Useful Functions
### `len`
```py
a = ['a', 'b', 'c']
len(a)      # 3
```
리스트 길이 반환

### `append`
```py
a = ['e', 'p', 'i']
a.append('k')   # ['e', 'p', 'i', 'k']
```
리스트에 요소 추가

### `sort`
```py
a = [1, 3, 2, 4]
a.sort()
print(a)    # [1, 2, 3, 4]
```
리스트 요소를 순서대로 정렬한다.  
문자도 정렬할 수 있다.

### `reverse`
```py
a = ['a', 'b', 'c']
a.reverse()
print(a)    # ['c', 'b', 'a']
```

### `index`
```py
a = [1, 2, 3]
a.index(3)      # 2
a.index(1)      # 0
```
요소의 인덱스를 반환  
리스트에 찾으려는 요소가 없으면 에러 발생

### `remove`
```py
a = [1, 2, 3, 1, 2, 3]
a.remove(3)
print(a)        # [1, 2, 1, 2, 3]
```
리스트에 첫 번째로 나오는 요소 삭제

### `pop`
```py
a = [1, 2, 3]
a.pop()     # returns 2
print(a)    # 2
```
리스트의 맨 마지막(오른쪽) 요소를 리턴하고 그 요소를 삭제

### `count`
```py
a = ['a', 'b', 'a', 'c']
a.count('a')    # 2
```
리스트에 있는 요소의 개수 리턴

### `extend`
```py
a = ['k', 'a', 'n']
b = ['y', 'e']
a.extend(b)
print(a)    # ['k', 'a', 'n', 'y', 'e']
```
리스트 더하기  
`a += b` 해도 됨
