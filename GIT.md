# Git

## Commit Message

### Overview

- 작은 단위로 한 번에 하나의 문제만 다루는 편이 유리

- HOW 보다는 WHAT, WHY 위주로 (좋은 코드는 HOW 를 이미 포함)

- 제목과 본문으로 구성

- See also , Reference 등 필요 시 추가해도 좋음

### Consideration

- 변경이 필요했던 이유

- 변경이 야기할 수 있는 Side Effect

- 문제를 해소할 방법 (필요 시)

### Principal

1. git log --oneline 출력 형태를 고려하기
> - 제목 행과 본문 행 사이에 한 행을 떨어뜨리기
>
> - 제목 행은 50 글자 이내, 본문 행은 70 글자 이내로 작성하면 좋음

2. 제목 행 첫 글자는 대문자, 마지막에는 마침표 생략

3. 제목 행을 명령문 구조로 작성
> 좋은 방법은 작성할 Commit Message 앞에 다음 문장을 붙여보는 것
> > If applied, this commit will

4. 본문은 72행에서 반드시 줄바꿈을 통해 행을 구분

5. 이왕이면 방법보다는 이유를 설명

6. Git 의 목적은 코드의 형상 관리
> 해당 Commit Message 가 코드 이력을 추적하는 데 도움이 되는 지 생각

### Good Reference
> [How to Write a Git Commit Message](https://cbea.ms/git-commit)
> 
> [좋은 git commit 메시지를 위한 영어 사전](https://blog.ull.im/engineering/2019/03/10/logs-on-git.html)
