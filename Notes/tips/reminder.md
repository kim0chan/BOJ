# 유용하지만 자꾸만 까먹는 것들

## 문자열(string)에서 정수형(int, long long)으로 바꾸는 함수
```cpp
stoi(string st)
stoll(string st)
```
* 중간에 숫자가 아닌 문자가 있을 경우 그 전까지 나온 substring을 숫자로 변환한다.

## 배열에서 두 개 비교하기
```cpp
for (int i = 0; i < N - 1; i++) {
	for (int j = i + 1; j < N; j++) {​
        // compare
    }
}
```
```
(0, 1), (0, 2), (0, 3), ... , (N-1, N)
```

## 문자열 대소 비교 연산자 ( `<`, `>,` `<=`, `>=` )
* 대소 비교 연산자는 `std::string` 클래스에 직접 지원이 되지 않는다.
* `std::string` 클래스는 문자열의 사전식 순서를 비교할 수 있도록 `compare()` 함수를 제공한다.
```cpp
int result = str1.compare(str2);
if(result < 0) {
    // str1이 str2보다 사전식으로 작다.
} else if (result > 0) {
    // str1이 str2보다 사전식으로 크다.
} else {
    // str1과 str2가 사전식으로 같다.
}
```
> 💥 `str1 - str2` 값이다. 라고 외우자ㅋㅋ;

## 대/소문자 변경 함수
```cpp
toupper(char);
tolower(char);​
```

## 뒤집기 (reverse)
```cpp
reverse(vct.begin(), vct.end());
```
* 문자열이나 컨테이너를 뒤집을 수 있음.
