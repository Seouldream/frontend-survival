# π React virtualDom

## 1. DOM(Document Object Model)

μΉ νμ΄μ§λ μΉ μ±μ μλ HTML μμλ€μ κ΅¬μ‘°μ μΌλ‘ ννν κ²μ΄λ€.

DOM stands for Document Object Model. It is a programming interface for web documents that allows programs to manipulate the content, structure, and style of a web page. The DOM represents the page as nodes and objects, making it possible to programmatically manipulate and dynamically update the page without needing to reload it.

DOMμ μ νλ¦¬μΌμ΄μμ μ μ²΄ UIλ₯Ό λνλ΄λ©° νΈλ¦¬ λ°μ΄ν° κ΅¬μ‘°λ‘ ννλλ€. μ¬κΈ°μλ Web Documentμ μλ κ° UI μμμ λν λΈλκ° ν¬ν¨λλ€. μΉ κ°λ°μκ° JavaScriptλ₯Ό ν΅ν΄ μ½νμΈ λ₯Ό μμ ν  μ μκΈ° λλ¬Έμ λ§€μ° μ μ©νλ€. λν κ΅¬μ‘°νλ νμμΌλ‘ λμ΄ μμ΄ νΉμ  λμμ μ νν  μ μκ³ , λͺ¨λ  μ½λ μμμ΄ ν¨μ¬ μ¬μμ§κΈ° λλ¬Έμ λ§μ λμμ΄ λλ€.

### DOM μ μ΄λ»κ² μλν κΉ?

When a web page is loaded in a browser, the browser creates a DOM tree representing the page's structure. The DOM tree consists of nodes that represent the HTML tags, as well as text and other content on the page. The browser uses the DOM to render the page, and it exposes the DOM to JavaScript, allowing JavaScript code to manipulate the page's content and structure.

JavaScript code can access the DOM through the Document object, which is the entry point to the DOM. The Document object provides methods for accessing and manipulating the nodes in the DOM tree, as well as properties and methods for manipulating the page's content and style. JavaScript code can also attach event listeners to nodes in the DOM tree, allowing it to respond to user interactions such as mouse clicks and key presses.

When JavaScript code manipulates the DOM, the changes are immediately reflected in the rendered page. For example, adding a new node to the DOM tree will cause the browser to add a new element to the page, while changing the text content of a node will cause the browser to update the rendered text on the page.

### 2. DOMμ λ¬Έμ μ 

DOMμ νΈλ¦¬ κ΅¬μ‘°λ‘ λμ΄ μμ΄μ μ΄ν΄νκΈ° μ½μ§λ§, λΈλμ μκ° λ§μμ§ μλ‘ μλκ° λλ €μ§κ³ , DOM μλ°μ΄νΈμ μ¦μ μ€λ₯λ₯Ό λ°μμν¬ μ μλ€.

λν, μ΅κ·Ό λͺ¨λ μΉμ SPA(Single Page Application)μ μ¬μ©νλ€. νλμ μΉ νμ΄μ§λ₯Ό μ΄νλ¦¬μΌμ΄μμ²λΌ κ΅¬μ±νλ SPAμμλ HTML λ¬Έμ μμ²΄κ° νλμ΄λ©°, μ¬λ¬ λμ μΈ κΈ°λ₯μ΄ λ€μ΄κ°κΈ° λλ¬Έμ μκ·Έλλ λ¦¬μμ€κ° λͺ¨λ ν©μ³μ§ λ¬΄κ±°μ΄ HTML λ¬Έμλ₯Ό μ§μμ μΌλ‘ μ¬λλλ§ ν΄μ€μΌνλ€λ λ¬Έμ μ μ΄ λ°μνκ² λμλ€.

JavaScriptλ₯Ό κ³΅λΆν μ μ΄ μλ€λ©΄, 'getElementById()' λλ 'getElementByClass()' λ©μλλ₯Ό μ¬μ©νμ¬ DOMμ λ΄μ©μ μμ ν  μ μλ κ²μ μκ³  μμ κ²μ΄λ€.

```js
// Simple getElementById() method
document.getElementById('some-id').innerValue = 'updated value';
```

μ½μμ΄λ JavaScript νμΌμ μμ κ°μ μ½λκ° μ€νλ  λ μλμ κ°μ κ³Όμ μ΄ μΌμ΄λλ€.

* λΈλΌμ°μ λ HTMLμ κ΅¬λ¬Έ λΆμνμ¬ μ΄ IDλ₯Ό κ°μ§ λΈλλ₯Ό μ°Ύλλ€.
* μ΄ νΉμ  μμμ μμ μμλ₯Ό μ κ±°νλ€.
* 'updated value'μΌλ‘ μμ(DOM)μ μλ°μ΄νΈνλ€.
* λΆλͺ¨ λ° μμ λΈλμ λν CSSλ₯Ό λ€μ κ³μ°νλ€.
* λ§μ§λ§μΌλ‘ λΈλΌμ°μ  λμ€νλ μ΄μ νμΈνλλ€.
* λ°λΌμ DOMμ μλ°μ΄νΈ νλ κ²μ μ½νμΈ  λ³κ²½μ ν¬ν¨ν  λΏλ§μ΄ μλλΌ ν¨μ¬ λ λ§μ μμλ€μ΄ μκ΅¬λλ€. λν CSSλ₯Ό λ€μ κ³μ°νκ³  λ μ΄μμμ λ³κ²½νλ €λ©΄ λ³΅μ‘ν μκ³ λ¦¬μ¦μ΄ νμνλ©° μ±λ₯μ μν₯μ λ―ΈμΉλ€.

μ΄μ²λΌ κΈ°μ‘΄μλ νλ©΄μ λ³κ²½μ¬ν­μ DOMμ μ§μ  μ‘°μνμ¬ λΈλΌμ°μ μ λ°μνμλ€. νμ§λ§, μ΄ λ°©λ²μ κ°μ₯ ν° λ¨μ μ DOM νΈλ¦¬κ° μμ λ  λλ§λ€ λ λ νΈλ¦¬κ° κ³μν΄μ μ€μκ°μΌλ‘ κ°±μ λλ€λ μ μ΄λ€. μ¦, νλ©΄μμ 10κ°μ μμ μ¬ν­μ΄ λ°μνλ©΄ μμ ν  λλ§λ€ μλ‘μ΄ λλ νΈλ¦¬κ° 10λ² μμ λλ©΄μ μλ‘­κ² λ§λ€μ΄μ§κ² λλ κ²μ΄λ€.

## 3. Virtual DOM(κ°μ DOM)

κ°μ DOMμ΄λ DOMμ κ°λ³κ² λ§λ  JavaScript ννμ΄λΌκ³  ν  μ μκ³  μ£Όλ‘ React, Vue.js κ·Έλ¦¬κ³  Elmμ μ¬μ©λλ€. κ°μDOMμ μ€μ λ‘ μ€ν¬λ¦°μ λλλ§νλ κ²μ΄ μλκΈ° λλ¬Έμ DOMμ μ§μ  μλ°μ΄νΈνλ κ²λ³΄λ€ μλμ μΌλ‘ λΉ λ₯΄λ€.

κ°μ DOMμ μ€μ  DOMμμ μ²λ¦¬νλ λ°©μμ΄ μλ Virtual DOMκ³Ό λ©λͺ¨λ¦¬μμ λ―Έλ¦¬ μ²λ¦¬νκ³  μ μ₯ν ν μ€μ  DOMκ³Ό λκΈ°ννλ νλ‘κ·Έλλ° κ°λμ΄λ€. ν΄λΉ DOMμ μ»΄ν¬λνΈ λ¨μλ‘ μͺΌκ°μ΄ HTML μ»΄ν¬λνΈ μ‘°λ¦½ν μ²λΌ λ€λ£¨λ κ°λμ΄λ€.

### 4. DOMκ³Ό Virtual DOMμ λΉκ΅

The main difference between DOM (Document Object Model) and Virtual DOM is that the DOM is a programming interface for web documents, while the Virtual DOM is an abstract representation of the actual DOM.

The DOM is a hierarchical tree structure that represents the content and structure of a web page. It is created by the browser when a page is loaded, and it provides a way for JavaScript to interact with and manipulate the content and structure of the page.

The Virtual DOM, on the other hand, is an in-memory representation of the DOM that is used by some JavaScript libraries and frameworks, such as React. When the state of a component in React changes, the Virtual DOM is updated to reflect the new state. The Virtual DOM is then compared to the previous version to determine the minimum set of changes that need to be made to the actual DOM to reflect the new state.

One of the main advantages of using a Virtual DOM is that it can improve performance by reducing the number of actual DOM manipulations required. Since updating the actual DOM can be a slow and expensive operation, minimizing the number of updates can help to improve the performance of a web application. Additionally, by abstracting the actual DOM, the Virtual DOM can make it easier to reason about the state of a web application and how it should be updated in response to user interactions.

|                            | DOM                                           | VirtualDom                                                                                                   |
| -------------------------- | --------------------------------------------- | ------------------------------------------------------------------------------------------------------------ |
| Update                     | slow                                          | fast                                                                                                         |
| HTML Update                | directly update HTML                          | non-directly                                                                                                 |
| New Element Update Process | when new element is updated, generate new DOM | when new element is updated, generate new V-DOM and compare present DOM and update differences between them. |
| Memory                     | takes large memory                            | takes less memory                                                                                            |
