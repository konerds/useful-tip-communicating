# Naming

## General Rule

### * (필수) 기존 컨벤션 따르기

### 기존 컨벤션을 따르지 않아도 된다면,

#### 1. Style Guide 참고
> [Google Style Guide](https://google.github.io/styleguide/) << 여기 좋음
>
> #### 언어마다 컨벤션이 다르므로 개인적으로 여기를 참고하여 작성하고 있음
#### 2. Open Source Code 참고

## Principal

### 1. 명확하고 서술적인 이름 사용
> #### 만일 부수 효과가 있다면, 이도 이름에 포함하는 것이 좋음
>
> #### 상황에 따라 적절한 이름을 사용
> > stop -> 되돌릴 수 없으면(kill) / 되돌릴 수 있으면(pause)
> > 
> > send -> 편지/메시지(dispatch) / 경로(route) / 공지(announce)
> > 
> > find -> DB 관련(search) / 추출(extract) / 위치(locate)
> > 
> > start -> 프로그램(launch) / 프로세스(create)
> > 
> > make -> 목적 파일(build) / 비즈니스 결과물(generate) / 구성 요소(compose)

```
// getOos 보다는 createOrReturnOos 같은 이름이 더 명확함
public ObjectOutputStream getOos() throws IOException {
  if (m_oos == null) {
    m_oos = new ObjectOutputStream(m_socket.getOutputStream());
  }
  return m_oos;
}
```

### 2. 저수준보다는 적절한 추상화 수준에서 이름을 선택
> #### 구현을 드러내는 이름은 피하는 것이 좋음
>
> #### 해당 클래스, 함수가 위치하는 추상화 수준을 반영할 수 있는 이름 찾아보기

```
/*
public interface Modem {
  boolean dial(String phoneNumber);
  boolean disconnect();
  boolean send(char c);
  char recv();
  String getConnectedPhoneNumber();
}
*/

public interface Modem {
  boolean connect(String connectionLocator);
  boolean disconnect();
  boolean send(char c);
  char recv();
  String getConnectedLocator();
}
```

### 3. 가능하다면 표준 명명법을 준수

```
DECORATOR 패턴 활용 시, 이름에 Decorator 사용
클래스 구현부 분리 시, 이름에 Impl 사용
JAVA 클래스의 toString 함수 Override
```

### 4. 이름의 길이는 Scope 에 비례하도록
> #### Scope 이 넓어질수록 변수의 이름이 중복될 가능성이 큼
>
> #### Scope 이 짧다고 이름도 너무 짧게 지으면 Multi Selection 할 때 좀 번거로움 (개인적으로)

### 5. 인코딩 피하기
> #### 이름에 Type 이나 Scope 정보가 들어가지 않는 게 좋다고 함
>
> #### 예를 들면 헝가리안 표기법을 들 수 있음 (pszLocatorStr, g_count, m_index, ...)
>
> #### (단, 이를 요구하는 환경의 경우는 예외 - WIN32 API)

### 6. 한 단어는 한 가지 목적으로 통일하여 사용
> #### remove, delete / get, fetch, retrieve / ...

## Tip

### 자연어에 맞추는 것이 좋음
> #### 개인적으로 전치 수식이랑 후치 수식 때문에 매번 헷갈렸는데, 자연어에 해당된다면 둘 다 괜찮을듯 함

```
pointsMax vs maxPoints -> 이왕이면 maxPoints
indexOf
elementAt
Fib.nth(n)
```
