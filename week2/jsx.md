# React에서는 왜 JSX를 사용하는가?

## JSX란?

JSX(JavaScript XML)는 Javascript에 XML을 추가한 확장한 문법이다.

JSX는 함수 호출과 객체 생성을 위한 문법적 편의를 제공하는 자바스크립트의 확장으로, 특히 React.createElement() 호출을 반복해야 하는 불편을 해소한다. 템플릿 엔진이나 HTML처럼 보일 수도 있지만 그렇지 않다. JSX는 React 엘리먼트를 생성하면서 자바스크립트의 모든 기능을 쓸 수 있도록 도와준다.

JSX는 React 컴포넌트를 생성하는 좋은 방법이다. JSX의 장점을 정리해보면 다음과 같다.

• 개발자 경험(developer experience, DX) 개선: 표현력이 뛰어나 코드를 읽기 쉽다. XML과 문법이 유사하여 중첩된 선언형 구조를 더 잘 나타낸다.

### XML이란?
XML(eXtensible Markup Language)은 W3C에서 개발된, 다른 특수한 목적을 갖는 마크업 언어를 만드는데 사용하도록 권장하는 다목적 마크업 언어이다.

- 예제
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/7/73/RecipeBook_XML_Example.svg/1920px-RecipeBook_XML_Example.svg.png" />

• 팀의 생산성 향상: 전문 개발자 외에도 개발 지식이 있는 팀원이 있다면 직접 코드를 수정할 수도 있다. JSX는 HTML과 비슷하여 이들에게도 친숙하기 때문이다.

• 문법 오류와 코드량 감소: 작성해야 할 코드가 줄어들며, 이는 곧 실수나 반복으로 인한 스트레스를 줄여준다.

JSX가 React에 필수적이지는 않지만 React에 잘 어울리고, 나의 의견도 그렇지만 React를 만드는 제작자들도 사용을 매우 권장하고 있다. 공식 웹사이트의 “JSX 소개” 페이지1를 보면 “우리는 JSX의 사용을 권장합니다”라고 쓰여 있다.
