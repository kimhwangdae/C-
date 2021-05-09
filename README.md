# C++
알고리즘을 풀때 썻던 라이브러리 정리
## String.find()

![string_find](https://user-images.githubusercontent.com/59689327/117568589-170e6a80-b0fc-11eb-8521-2891f28174f0.PNG)

C++ 라이브러리중에 부분 문자열을 찾는 유용한 라이브러리가 있어서 정리해본다.<br>

2.find()는 s가 가키는 문자부터 count 개 만큼을 취한 부분 문자열을 원 문자열에서 찾는다. s 중간에 NULL 이 있어도 괜찮다.<br>

3.s 가 가리키는 문자열을 원 문자열에서 검색한다. 이 때 s는 NULL 종료 문자열로 간주 된다.<br>

만약 문자열을 찾는데 성공하였다면, 해당 문자열의 시작 위치를 반환하고, 찾지 못했다면 ```npos``` 를 리터한다. ```npos```는 ```string::npos```로 정의되는 상수이다. <br>

### 인자들
<li> str - 찾고자 하는 문자열</li>
<li> pos - 검색을 시작할 위치</li>
<li> count - 찾고자 하는 문자열의 길이</li>
<li> s - 찾고자 하는 문자열을 가리키는 포인턴</li>
<li> ch - 찾고자 하는 문자</li>
<li> t - 찾고자 하는 string_view 로 변환 가능한 객체</li>

### 예시

```
void print(std::string::size_type n, std::string const &s) {
  if (n == std::string::npos) {
    std::cout << "not found\n";
  } else {
    std::cout << "found: " << s.substr(n) << '\n';
  }
}

int main() {
  std::string::size_type n;
  std::string const s = "This is a string";

  // s 의 처음 부터 찾는다.
  n = s.find("is");
  print(n, s);

  // s 의 5번째 문자부터 찾는다.
  n = s.find("is", 5);
  print(n, s);
  }
 ```
 
