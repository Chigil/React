# Interview Questions

<details>
<summary>1. What is React?</summary>

>#### Answer:
>* React is a front-end JavaScript library developed by Facebook in 2011.
>* It follows the component based approach which helps in building reusable UI components.
>* It is used for developing complex and interactive web and mobile UI.
>* Even though it was open-sourced only in 2015, it has one of the largest communities supporting it.
</details>

<details>
<summary>2. What are the features of React?</summary>

>#### Answer:
>* It uses the virtual DOM instead of the real DOM.
>* It uses server-side rendering.
>* It follows uni-directional data flow or data binding.
</details>

<details>
<summary>3. List some of the major advantages of React.</summary>

>#### Answer:
>* It increases the application’s performance.
>* It can be conveniently used on the client as well as server side.
>* Because of JSX, code’s readability increases.
>* React is easy to integrate with other frameworks like Meteor, Angular, etc.
>* Using React, writing UI test cases become extremely easy.
</details>

<details>
<summary>4. What are the limitations of React?</summary>

>#### Answer:
>* React is just a library, not a full-blown framework.
>* Its library is very large and takes time to understand.
>* It can be little difficult for the novice programmers to understand.
>* Coding gets complex as it uses inline templating and JSX.
</details>

<details>
<summary>5. What is JSX?</summary>

>#### Answer:
>JSX is a shorthand for JavaScript XML. This is a type of file used by React which utilizes the expressiveness of JavaScript along with HTML like template syntax.
>This makes the HTML file really easy to understand. This file makes applications robust and boosts its performance.
</details>

<details>
<summary>6. Why can’t browsers read JSX?</summary>

>#### Answer:
>Browsers can only read JavaScript objects but JSX in not a regular JavaScript object.
>Thus to enable a browser to read JSX, first, we need to transform JSX file into a JavaScript object using JSX transformers like Babel and then pass it to the browser.
</details>

<details>
<summary>7. What do you understand from “In React, everything is a component.”</summary>

>#### Answer:
>Components are the building blocks of a React application’s UI. These components split up the entire UI into small independent and reusable pieces.
>Then it renders each of these components independent of each other without affecting the rest of the UI.
</details>

<details>
<summary>8. Explain the purpose of `render()` in React.</summary>

>#### Answer:
>Each React component must have a `render()` mandatorily. It returns a single React element which is the representation of the native DOM component.
>If more than one HTML element needs to be rendered, then they must be grouped together inside one enclosing tag such as `<form>`, `<group>`, `<div>` etc.
>This function must be kept pure i.e., it must return the same result each time it is invoked.
</details>

<details>
<summary>9. How to create components in React?</summary>

>#### Answer:
>There are two possible ways to create a component.
> 1. **Function Components:** This is the simplest way to create a component. Those are pure JavaScript functions that accept props object as first parameter and return React elements:
>
>```jsx harmony
>function Greeting({ message }) {
>   return <h1>{`Hello, ${message}`}</h1>
>}
>```
>2. **Class Components:** You can also use ES6 class to define a component. The above function component can be written as:
>
>```jsx harmony
>class Greeting extends React.Component {
>   render() {
>     return <h1>{`Hello, ${this.props.message}`}</h1>
>   }
>}
>```
</details>

<details>
<summary>10. What is `props`?</summary>

>#### Answer:
>Props is the shorthand for Properties in React. They are read-only components which must be kept pure i.e. immutable.
>They are always passed down from the parent to the child components throughout the application.
>A child component can never send a prop back to the parent component.
>This help in maintaining the unidirectional data flow and are generally used to render the dynamically generated data.
</details>

<details>
<summary>11. What are the limitations of `props`?</summary>

>#### Answer:
>Props (short for properties) are a component’s configuration. Props are how components talk to each other.
>They are received from above component and immutable as far as the component receiving them is concerned. A component cannot change its props.
</details>

<details>
<summary>12. What is a `state` in React and how is it used?</summary>

>#### Answer:
>States are the heart of React components. States are the source of data and must be kept as simple as possible.
>Basically, states are the objects which determine components rendering and behavior.
>They are mutable unlike the props and create dynamic and interactive components. They are accessed via `this.state`.
</details>

<details>
<summary>13. How can you update the `state` of a component?</summary>

>#### Answer:
>State of a component can be updated using `this.setState()`.
</details>

<details>
<summary>14. How to bind methods or event handlers in JSX callbacks?</summary>

>#### Answer:
>There are 3 possible ways to achieve this:
>1.	**Binding in Constructor:** In JavaScript classes, the methods are not bound by default. The same thing applies for React event handlers defined as class methods. Normally we bind them in constructor.
>    ```javascript
>    class Component extends React.Componenet {
>      constructor(props) {
>        super(props)
>        this.handleClick = this.handleClick.bind(this)
>      }
>
>      handleClick() {
>        // ...
>      }
>    }
>    ```
>
>2. **Public class fields syntax:** If you don't like to use bind approach then *public class fields syntax* can be used to correctly bind callbacks.
>
>    ```jsx harmony
>    handleClick = () => {
>      console.log('this is:', this)
>    }
>    ```
>
>    ```jsx harmony
>    <button onClick={this.handleClick}>
>      {'Click me'}
>    </button>
>    ```
>3. **Arrow functions in callbacks:** You can use *arrow functions* directly in the callbacks.
>
>    ```jsx harmony
>    <button onClick={(event) => this.handleClick(event)}>
>      {'Click me'}
>    </button>
>    ```
>
>    **Note:** If the callback is passed as prop to child components, those components might do an extra re-rendering. In those cases, it is preferred to go with `.bind()` or *public class fields syntax* approach considering performance.
</details>

<details>
<summary>15. What is Redux?</summary>

>#### Answer:
>Redux is a predictable state container for JavaScript apps based on the Flux design pattern. Redux can be used together with React, or with any other view library. It is tiny (about 2kB) and has no dependencies.
</details>

**[⬆ back to top](#interview-questions)**
