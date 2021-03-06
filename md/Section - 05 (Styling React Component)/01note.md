# Styling react component

## inline styling in react

in react for in style first we use the style keyword and the set a object into it.

```jsx
<input
  // inline style in react
  style={{
    border: isValid ? "2px solid black" : "5px solid red",
    background: !isValid ? "orange" : "transparent",
  }}
  type="text"
  onChange={goalInputChangeHandler}
/>
```

# Setting CSS Classes Dynamically

we can also use Dynamically style using css class

- first i make a css style

```css
.form-control.invalid input {
  border: #fad0ec 5px solid;
  background-color: #f87d67;
}
.form-control.invalid label {
  color: #f87d67;
}
```

- then i add this style in my jsx code and using ternary operator for condition

```jsx
// inValid is a state for more information see the code
// CourseInput.js
<div className={`form-control ${!isValid ? "invalid" : ""}`}>
  <label>Course Goal</label>
  <input type="text" onChange={goalInputChangeHandler} />
</div>
```

# Introducing Styled Components

first we need to install <code>Styled Components</code>

```bash
npm i --save styled-components
```

Syntax for styled component

```jsx
import styled from "styled-components";
const Button = styled.button`
   {
    font: inherit;
    padding: 0.5rem 1.5rem;
    border: 1px solid #8b005d;
    color: white;
    background: #8b005d;
    box-shadow: 0 0 4px rgba(0, 0, 0, 0.26);
    cursor: pointer;
  }

  &:focus {
    outline: none;
  }

  &:hover,
  &:active {
    background: #ac0e77;
    border-color: #ac0e77;
    box-shadow: 0 0 8px rgba(0, 0, 0, 0.26);
  }
`;
```

- first we import styled component

```jsx
import styled from "styled-components";
```

then we can work with styled-components

# condition using styled-components

we can also use condition in styled component

```js
const FormDiv = styled.div`
  margin: 0.5rem 0;

  & label {
    font-weight: bold;
    display: block;
    margin-bottom: 0.5rem;
  }

  & input {
    display: block;
    width: 100%;
    border: 1px solid ${(props) => (props.invalid ? "red" : "black")};
    font: inherit;
    line-height: 1.5rem;
    padding: 0 0.25rem;
  }

  & input:focus {
    outline: none;
    background: #fad0ec;
    border-color: #8b005d;
  }

  & .invalid input {
    border: #fad0ec 5px solid;
    background-color: #f87d67;
  }
  & .invalid label {
    color: #f87d67;
  }
`;
<FormDiv invalid={!isValid}>
  <label>Course Goal</label>
  <input type="text" onChange={goalInputChangeHandler} />
</FormDiv>;
```

- pass a props to our styled components
- and in styled-components style we can use it
- since we are in back-tick so if we need to work with javascript we need to add ${}
- create arrow function and handle the props
