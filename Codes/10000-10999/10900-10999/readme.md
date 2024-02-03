# 10900 ~ 10999


## 10926 : ??!

## 10942 : 팰린드롬?
2차원 배열을 사용한다.  
`isPalindrome[i][j]`에 문자열 인덱스 `i`부터 `j`까지가 팰린드롬인지 여부를 저장한다.  
`i`부터 `j`까지의 문자열이 팰린드롬인지는 어떻게 알 수 있을까?  
`i + 1`부터 `j - 1`까지의 문자열이 팰린드롬이면서 `i`번째, `j`번째 문자가 같아야 하겠다.  
```cpp
isPalindrome[i][i + k] = (isPalindrome[i + 1][i - 1 + k] && number[i] == number[i + k]);
```
이렇게 계산하려면 1글자와 2글자 문자열에 대해서 초기화를 해 주어야 한다!

## 10950 : A+B - 3

## 10951 : A+B - 4

## 10952 : A+B - 5

## 10974 : 모든 순열

## 10989 : 수 정렬하기 3
`N`이 최대 10,000,000이기 때문에 계수 정렬(Counting Sort)을 이용한다.

## 10998 : A×B