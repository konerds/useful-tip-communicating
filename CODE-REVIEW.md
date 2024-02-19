# Code Review

> 코드 품질을 높이고 지식 공유를 전사적으로 수행하기 위한 활동

## LGTM (Looks Good To Me)

> Github 에서 가장 인기 있는 코멘트

## Overview

##### [Ways to make code reviews more effective](https://www.infoq.com/articles/effective-code-reviews/)

```
잘못된 결과를 낳는 시나리오의 근본적인 원인을 회피하기 위해 우리는 무엇을 해야 하는가?
```

### Spectrum

> 검토 작업을 위해 얼마나 많은 사람이 준비하고 참여해야 하는가?

```
Inspection (가장 정형적)

Team Review

Walkthrough

Pair Programming

Peer Deskcheck, Passaround (Google 에서 많이 쓴다고 함)

Ad Hoc Review (가장 비정형적)
```

### Key Point

> Code Review 과정에서 무엇이 중요할까?

1. 팀은 프로젝트에 중요한 것이 무엇인지 식별하고 검토 과정에서 이를 일관되게 검사해야 함
2. 검토 시간을 최소화하기 위해 **형식 지정**, **스타일 지정**, **일반적인 버그 확인**, **일반적인 보안 문제 식별**, **자동화된 테스트 실행** 등 자동화 수준을 높여야 함
3. 전투가 아닌 공동 토론의 성격에 맞게 중요한 부분과 중요하지 않은 부분을 미리 결정하여야 함

### Consideration

-   새로운 코드가 전체 아키텍처와 조화를 이룰 수 있는가?
-   새로운 코드에 SOLID, Domain Driven 등 적절한 디자인 패턴이 사용되고 있는지, 그리고 팀에서 선호하는 설계 원칙과 잘 맞아 떨어지는가?
-   새로운 코드가 올바른 위치에 작성되었는가?
-   새로운 코드가 기존 코드의 일부를 재사용하고 있는지, 그리고 새로운 코드에 중복된 부분이 있는지?
-   새로운 코드가 Under Engineering / Over Engineering 되지 않았는지?

### V&V (Verification & Validation)

#### Verification

> 제품을 올바르게 만들고 있는가?

#### Validation

> 올바른 제품을 만들고 있는가?

### Readability & Maintainability

> Verification

-   필드, 변수, 파라미터, 메서드, 클래스의 이름이 실제로 나타내는 내용을 잘 반영하고 있는가?
-   코드를 읽으면 무엇을 하는지 이해할 수 있는가?
-   테스트 코드를 읽으면 무엇을 하는지 이해할 수 있는가?
-   테스트 코드가 정상 케이스와 예외 케이스를 모두 다루고 있는지, 미처 고려되지 않은 사례가 있는지?
-   예외 및 오류 메시지를 이해할 수 있는지?
-   코드에서 혼란스러운 부분이 문서화, 주석 처리 또는 이해할 수 있는 테스트로 다뤄지고 있는가? (팀 선호도에 따라)

### Functionality

> Validation

-   코드가 실제로 수행해야 하는 작업을 수행하고 있는지?
-   잘못된 변수를 사용하거나 논리 연산자 실수 등 미묘한 버그가 포함되어 있는지?

### Production Consideration

-   코드의 변경에 따라 작성자가 새로운 공개 문서를 작성해야 하거나 기존 문서 파일을 변경해야 하는가?
-   사용자에게 표시되는 메시지의 정확성을 확이했는가?

## Approach

##### [How to Make Your Code Reviewer Fall in Love with You](https://mtlynch.io/code-review-love)

### 1. 스스로 코드를 검토하라

> 만일 내가 검토자라면?

### 2. 깔끔한 변경 목록 준비

> 변경에 대한 이유 + 검색 가능한 문자열 + 조사 방법에 대한 기록

##### [Good Example](https://github.com/alphagov/govuk-puppet/commit/63b36f93bf75a848e2125008aa1e880c5861cf46)

### 3. 쉬운 작업은 자동화

> 기계가 잘 하는 일은 기계에게

#### 사람이 했을 때 들어가는 비용

1. 검토자는 Whitespace 문제와 부적절한 들여쓰기를 찾아야 함
2. 검토자는 올바르지 않은 들여쓰기를 지적하는 노트를 작성함
3. 검토자는 노트를 읽고 비난하지 않는 어조로 명백한 방식으로 작성했는지를 검토
4. 개발자가 노트를 읽음
5. 개발자가 코드 들여쓰기를 수정함
6. 검토자는 개발자가 노트에 적힌 문제를 적절히 해소했는지 검증함

#### Formatter 를 활용했다면?

> 없음

### 4. 스스로 답할 수 있는 코드

> 변경 내역을 살펴보고 모든 코드 검토 토론을 읽어야만 비로소 이해가 되는 코드라면 이는 좋은 코드가 아니다

#### 검토자가 코드의 동작 방식에 대한 혼란을 표명하면?

> 한 사람이 아닌 모든 사람에게 설명해야 한다
>
> 따라서 질문에 답하는 가장 현명한 방법은 Code Refactoring

-   이름을 바꾸거나 논리를 명확하게 만들기 위해 재구성이 가능한지?
-   부적절한 주석을 제거하고 그 자리에 좋은 코드를 채우는 것이 현명

### 5. 기능과 비기능 변경의 분리

> chore / fix / design / style / docs / refactor / ...
