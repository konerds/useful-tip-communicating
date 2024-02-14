# Documenting

## 소스코드 문서화 도구를 사용할 때 고려해볼 사항

1. 문서화의 목적은 내부 동작 방식이 아닌 파일, 클래스 수준에서의 큰 그림을 설명하는 것
> 시스템 내부에 속한 클래스와 함수는 반드시 작성할 필요는 없음
>
> 외부 공개 클래스, 외부 공개 메서드, 외부 공개 상수 등 외부 공개 API 에 대해서만 작성
>
> 꼭 필요하지 않은 부분까지 전부 작성한다면 전체 코드 가독성을 떨어뜨릴 수 있음

2. Comment Style Guide
> - 2인칭이 아닌 3인칭을 사용
> > Get the label. -> Gets the label.
>
> - 메서드에 대한 설명은 동사 형태가 좋음
> > Gets the label of this button.
>
> - 인터페이스, 클래스, 필드에 대한 설명은 주어를 생략해도 무관
> > This field is a button label. -> A button label.
>
> - 설명하고 있는 클래스에서 생성된 객체는 this 로 지칭
> > Gets the toolkit for the component. -> Gets the toolkit for this component.

3. Javadoc / Doxygen 추천
> [How to use Javadoc](https://www.oracle.com/technical-resources/articles/java/javadoc-tool.html)
> 
> [How to use Doxygen](https://www.doxygen.nl/manual/index.html)
