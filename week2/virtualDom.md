# VDOM(Virtual DOM)이란?

## 1. DOM(Document Object Model)

웹 페이지나 웹 앱에 있는 HTML 요소들을 구조적으로 표현한 것이다.

DOM stands for Document Object Model. It is a programming interface for web documents that allows programs to manipulate the content, structure, and style of a web page. The DOM represents the page as nodes and objects, making it possible to programmatically manipulate and dynamically update the page without needing to reload it.

DOM은 애플리케이션의 전체 UI를 나타내며 트리 데이터 구조로 표현된다. 여기에는 Web Document에 있는 각 UI 요소에 대한 노드가 포함된다. 웹 개발자가 JavaScript를 통해 콘텐츠를 수정할 수 있기 때문에 매우 유용하다. 또한 구조화된 형식으로 되어 있어 특정 대상을 선택할 수 있고, 모든 코드 작업이 훨씬 쉬워지기 때문에 많은 도움이 된다.

### DOM 은 어떻게 작동할까?

When a web page is loaded in a browser, the browser creates a DOM tree representing the page's structure. The DOM tree consists of nodes that represent the HTML tags, as well as text and other content on the page. The browser uses the DOM to render the page, and it exposes the DOM to JavaScript, allowing JavaScript code to manipulate the page's content and structure.

JavaScript code can access the DOM through the Document object, which is the entry point to the DOM. The Document object provides methods for accessing and manipulating the nodes in the DOM tree, as well as properties and methods for manipulating the page's content and style. JavaScript code can also attach event listeners to nodes in the DOM tree, allowing it to respond to user interactions such as mouse clicks and key presses.

When JavaScript code manipulates the DOM, the changes are immediately reflected in the rendered page. For example, adding a new node to the DOM tree will cause the browser to add a new element to the page, while changing the text content of a node will cause the browser to update the rendered text on the page.
 
### 2. DOM의 문제점

DOM은 트리 구조로 되어 있어서 이해하기 쉽지만, 노드의 수가 많아질 수록 속도가 느려지고, DOM 업데이트에 잦은 오류를 발생시킬 수 있다.

또한, 최근 모던 웹은 SPA(Single Page Application)을 사용한다. 하나의 웹 페이지를 어플리케이션처럼 구성하는 SPA에서는 HTML 문서 자체가 하나이며, 여러 동적인 기능이 들어가기 때문에 안그래도 리소스가 모두 합쳐진 무거운 HTML 문서를 지속적으로 재랜더링 해줘야한다는 문제점이 발생하게 되었다.

JavaScript를 공부한 적이 있다면, 'getElementById()' 또는 'getElementByClass()' 메서드를 사용하여 DOM의 내용을 수정할 수 있는 것을 알고 있을 것이다. 

```js
// Simple getElementById() method
document.getElementById('some-id').innerValue = 'updated value';
```

콘솔이나 JavaScript 파일에 위와 같은 코드가 실행될 때 아래와 같은 과정이 일어난다.

- 브라우저는 HTML을 구문 분석하여 이 ID를 가진 노드를 찾는다.
- 이 특정 요소의 자식 요소를 제거한다.
- 'updated value'으로 요소(DOM)을 업데이트한다.
- 부모 및 자식 노드에 대한 CSS를 다시 계산한다.
- 마지막으로 브라우저 디스플레이에 페인팅된다.
- 따라서 DOM을 업데이트 하는 것은 콘텐츠 변경을 포함할 뿐만이 아니라 훨씬 더 많은 작업들이 요구된다. 또한 CSS를 다시 계산하고 레이아웃을 변경하려면 복잡한 알고리즘이 필요하며 성능에 영향을 미친다.

이처럼 기존에는 화면의 변경사항을 DOM을 직접 조작하여 브라우저에 반영하였다. 하지만, 이 방법의 가장 큰 단점은 DOM 트리가 수정될 때마다 렌더 트리가 계속해서 실시간으로 갱신된다는 점이다. 즉, 화면에서 10개의 수정사항이 발생하면 수정할 때마다 새로운 랜더 트리가 10번 수정되면서 새롭게 만들어지게 되는 것이다.

## 3. Virtual DOM(가상 DOM)

가상 DOM이란 DOM을 가볍게 만든 JavaScript 표현이라고 할 수 있고 주로 React, Vue.js 그리고 Elm에 사용된다. 가상DOM은 실제로 스크린에 랜더링하는 것이 아니기 때문에 DOM을 직접 업데이트하는 것보다 상대적으로 빠르다.

가상 DOM은 실제 DOM에서 처리하는 방식이 아닌 Virtual DOM과 메모리에서 미리 처리하고 저장한 후 실제 DOM과 동기화하는 프로그래밍 개념이다. 해당 DOM을 컴포넌트 단위로 쪼개어 HTML 컴포넌트 조립품 처럼 다루는 개념이다.

### 4. DOM과 Virtual DOM의 비교

The main difference between DOM (Document Object Model) and Virtual DOM is that the DOM is a programming interface for web documents, while the Virtual DOM is an abstract representation of the actual DOM.

The DOM is a hierarchical tree structure that represents the content and structure of a web page. It is created by the browser when a page is loaded, and it provides a way for JavaScript to interact with and manipulate the content and structure of the page.

The Virtual DOM, on the other hand, is an in-memory representation of the DOM that is used by some JavaScript libraries and frameworks, such as React. When the state of a component in React changes, the Virtual DOM is updated to reflect the new state. The Virtual DOM is then compared to the previous version to determine the minimum set of changes that need to be made to the actual DOM to reflect the new state.

One of the main advantages of using a Virtual DOM is that it can improve performance by reducing the number of actual DOM manipulations required. Since updating the actual DOM can be a slow and expensive operation, minimizing the number of updates can help to improve the performance of a web application. Additionally, by abstracting the actual DOM, the Virtual DOM can make it easier to reason about the state of a web application and how it should be updated in response to user interactions.


|                            | DOM                                          | VirtualDom                                                                                                    |
|----------------------------|----------------------------------------------|---------------------------------------------------------------------------------------------------------------|
| Update                     | slow                                         | fast                                                                                                          |
| HTML Update                | directly update HTML                         | non-directly                                                                                                  |
| New Element Update Process | when new element is updated, generate new DOM | when new element is updated, generate new V-DOM and compare present DOM and update differences between them. |
| Memory                     |                  takes large memory                            |                                             takes less memory                                                                  |
 