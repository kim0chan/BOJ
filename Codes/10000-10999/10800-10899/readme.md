# 10800 ~ 10899


## 10808 : 알파벳 개수

## 10809 : 알파벳 찾기
문자열 문제이다.  
`string.find()` 함수를 이용했다. 코드를 참고하십쇼  
지금은 배열을 전역변수에 선언하여 0으로 초기화되지만 block 내에서 선언과 동시에 0으로 초기화 하려면  
`int array[n] = { 0 , };` 이렇게 하면 된다.

## 10814 : 나이순 정렬

## 10815 : 숫자 카드
('23. 9. 13.) 코드 수정

## 10816 : 숫자 카드 2
\* 이분 탐색으로도 풀 수 있다  
`lower_bound`, `upper_bound` 이용

## 10817 : 세 수

## 10818 : 최소, 최대

## 10825 : 국영수
정렬 문제이다. `STUDENT`라는 구조체를 만들고 알맞는 비교함수를 정의하여 풀었다.  
비교함수에 `STUDENT&` 인자를 넘겨 주어 불필요한 복사가 이루어지지 않게 한 점에 주의합시다  
(메모리 뿐만 아니라 실행 시간에서도 손해봄)

## 10828 : 스택
스택(Stack) 기본기

## 10844 : 쉬운 계단 수

## 10845 : 큐
큐(Queue) 기본기

## 10866 : 덱
덱(Deque) 기본기

## 10867 : 중복 빼고 정렬하기
나는 벡터와 `sort()`, `binary_search()`를 이용하여 구현했는데,  
`arr.erase(unique(v.begin(), v.end()), v.end())`와 같은 방식으로 구현할 수도 있을 것 같다.

## 10869 : 사칙연산

## 10870 : 피보나치 수 5

## 10871 : X보다 작은 수

## 10872 : 팩토리얼
재귀 이용한 basic한 팩토리얼 계산 문제