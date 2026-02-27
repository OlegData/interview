# Interview questions
- [Python](#Python)
- [ReactJS](#ReactJS)

## Python

## ReactJS
1. How to create components in React?
React provides two ways to create a component – **function components and class components.***
**Function Components** is the simplest way to create a component. It uses pure JavaScript functions that accept props and returns a React element.
```
function Welcome({ message }) {
  return <h1>{`Hello, ${message}`}</h1>
}
```
**Class Components**, on the other hand, uses ES6 class to define a component. The same function component can be rewritten as the following class component:
