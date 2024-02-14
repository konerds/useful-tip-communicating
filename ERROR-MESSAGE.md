# Error Message

## Who is end-user?

### 소프트웨어
> 사용자

### 프레임워크, 라이브러리
> 개발자, 엔지니어, 관리자 등

## Consideration

### 맥락
#### Error 의 원인이 무엇인지, 코드에서 무엇을 시도하다가 실패한 것인지
> 파일 내용의 특정 부분인 경우 -> 줄 번호 또는 줄 내용을 출력
> 
> 입력 파일, 구성 파일과 관련된 경우 -> 파일 경로 출력

```
"Couldn't parse config file: /etc/sample-config.properties"
```

### Error 정보
#### 정확히 무슨 일이 발생했는지 짧고 간결하게 설명
> Error 의 심각성 / 발생한 Error 소개 / Error 발생 위치 / Error 발생 이유

```
"Couldn't parse config file: /etc/sample-config.properties; given snapshot mode 'nevr' isn't valid
```

### Error 완화 방법
#### 사용자가 Error 를 완화하기 위한 조치를 설명
> Error Code 를 포함하면 좋음

```
"ERROR-CODE-00001: Couldn't parse config file: /etc/sample-config.properties; given snapshot mode 'nevr' isn't valid (must be one of 'initial', 'always', 'never')
```

## Rule

### 통일된 태와 스타일
> #### 능동태 vs 수동태
> > "Couldn't parse config file." vs "config file couldn't be parsed."
> #### 대소문자와 마침표
> > "couldn't parse config file" vs "Couldn't parse config file."

### 한 가지 개념에는 한 가지 용어만
> #### Error 메시지마다 한 가지 개념에 여러 용어를 함께 사용하는 것은 좋지 않음
> > 반대로 여러 개념에 한 가지 용어만을 고집하는 것도 좋지 않음

### Error 메시지를 API 계약으로 만들지 말 것
> #### API 를 사용하는 쪽에서 구문 분석하지 않도록 코드화하는 것이 좋음

### 개인 정보 등 민감한 정보를 노출하지 말 것
> #### GDPR 등 관련 법률 참고

### Error 메시지 출력은 정확하게 한 번만
> #### 예외 처리를 하는 경우, 중복된 출력이 생기지 않도록 주의
> > 가장 빨리 일어난 시점에서 출력되는 것이 좋음
