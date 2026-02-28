## ReactJS

**1. What is React, and what are its main features?**

React is a JavaScript library developed by Facebook for creating user interfaces, particularly in single-page applications. It enables the use of reusable components that manage their own state. Key advantages include a component-driven architecture, optimized updates through the virtual DOM, a declarative approach for better readability, and robust community backing.

**2. What is JSX and how does it work?**

JSX (JavaScript XML) is a syntax extension for JavaScript used in React to describe UI.
It looks like HTML but is compiled into JavaScript (e.g., React.createElement) before running in the browser.

JSX (JavaScript XML) — это расширение синтаксиса JavaScript, используемое в React для описания интерфейса.
Похоже на HTML, но перед выполнением компилируется в обычный JavaScript (например, в React.createElement).

**3. Explain the concept of the Virtual DOM in React.**

The Virtual DOM is a lightweight JavaScript representation of the real DOM used by React.
When the state or props change, React creates a new Virtual DOM, compares it with the previous one (diffing),
and updates only the changed parts in the real DOM. This process improves performance by minimizing direct DOM manipulations.

Virtual DOM — это облегчённая JavaScript-копия реального DOM, используемая в React.
Когда изменяются state или props, React создаёт новый Virtual DOM, сравнивает его с предыдущим (diffing)
и обновляет только изменённые части в реальном DOM. Это повышает производительность за счёт минимизации прямых операций с DOM.

**4. How does virtual DOM in React work? What are its benefits and downsides?**

The Virtual DOM in React works by creating a lightweight copy of the real DOM as a JavaScript object.
When state or props change, React creates a new Virtual DOM tree, compares it with the previous one
(diffing), calculates the differences, and updates only the changed elements in the real DOM.
This process is called reconciliation.

Benefits: improved performance through minimized direct DOM updates, predictable UI updates,
and better developer experience with declarative code.

Downsides: additional memory usage for storing Virtual DOM, extra computation during diffing,
and it may not always be faster for very simple or highly optimized manual DOM updates.

Virtual DOM в React работает как облегчённая копия реального DOM в виде JavaScript-объекта.
Когда изменяются state или props, React создаёт новое дерево Virtual DOM, сравнивает его с предыдущим
(diffing), вычисляет различия и обновляет только изменённые элементы в реальном DOM.
Этот процесс называется reconciliation.

Преимущества: повышение производительности за счёт минимизации прямых обновлений DOM,
предсказуемые обновления интерфейса и удобная декларативная модель разработки.

Недостатки: дополнительное использование памяти для хранения Virtual DOM, дополнительные вычисления
при сравнении и не всегда более высокая скорость в очень простых или вручную оптимизированных сценариях.

**5. What is the difference Between React Node, React Element, and React Component?**

A **React Node** is anything that can be rendered by React, such as strings, numbers, React elements, arrays, fragments, or null/undefined.

A **React Element** is a plain JavaScript object that describes what should appear on the screen. It is usually created using JSX or React.createElement and represents a specific DOM node or component.

A **React Component** is a function or class that returns React elements. It contains logic and can accept props and manage state.

**React Node** — это всё, что React может отобразить: строки, числа, React-элементы, массивы, фрагменты или null/undefined.
**React Element** — это обычный JavaScript-объект, который описывает, что должно быть отображено на экране. Обычно создаётся с помощью JSX или React.createElement и представляет конкретный DOM-узел или компонент.
**React Component** — это функция или класс, который возвращает React-элементы. Он содержит логику, может принимать props и управлять состоянием.

**What are the main features of React?**

React is a declarative, component-based JavaScript library for building user interfaces.
Its main features include:

**Component-Based Architecture**  
Applications are built using reusable, isolated components, which improves maintainability and scalability.

**Declarative UI**  
Developers describe how the UI should look for a given state, and React efficiently updates the DOM when the state changes.

**Virtual DOM & Reconciliation**  
React uses a virtual representation of the DOM and updates only the parts that changed, improving performance.

**Unidirectional Data Flow**  
Data flows from parent to child via props, making the data structure predictable and easier to debug.

**Hooks & State Management**  
Hooks like useState, useEffect, and useContext allow function components to manage state and lifecycle logic.

**JSX Syntax**  
JSX allows writing UI structure in a syntax similar to HTML, improving readability.

**Strong Ecosystem**  
Large community support, rich tooling, and compatibility with libraries like Redux, React Router, etc.

**6. What are React Fragments used for?**

React Fragments are used to group multiple elements without adding extra nodes to the DOM.  
They allow a component to return multiple elements without wrapping them in an additional div.  
Fragments help keep the DOM clean and avoid unnecessary markup.

React Fragments используются для объединения нескольких элементов без добавления лишних узлов в DOM.  
Они позволяют компоненту возвращать несколько элементов без оборачивания их в дополнительный div.  
Это помогает сохранить чистоту DOM и избежать лишней разметки.

```
return (
  <>
    <ChildComponent1 />
    <ChildComponent2 />
  </>
);
```

**7. What is the purpose of the key prop in React?**

The key prop in React is used to uniquely identify elements in a list.  
It helps React determine which items have changed, been added, or removed during re-rendering.  
This improves performance and ensures correct UI updates when working with dynamic lists.

Свойство key в React используется для уникальной идентификации элементов в списке.  
Оно помогает React определить, какие элементы были изменены, добавлены или удалены при повторном рендеринге.  
Это повышает производительность и обеспечивает корректное обновление интерфейса при работе с динамическими списками.

```
{
  items.map((item) => <ListItem key={item.id} value={item.value} />);
}
```

**8. What is the consequence of using array indices as keys in React?**
Using array indices as keys in React can lead to incorrect UI updates when items are added, removed, or reordered.  
Since indices change, React may reuse the wrong components, causing bugs, state mismatches, or unexpected behavior.  
It is safe to use indices only if the list is static and never changes.

Использование индексов массива в качестве key в React может привести к некорректным обновлениям интерфейса при добавлении,  
удалении или изменении порядка элементов. Поскольку индексы меняются, React может повторно использовать неправильные компоненты,  
что вызывает ошибки, потерю состояния или непредсказуемое поведение.  
Индексы безопасно использовать только если список статический и не изменяется.

**9. What are props in React? How are they different from state?**

**Props** in React are inputs passed from a parent component to a child component.  
They are read-only and allow components to receive data and configuration from outside.

**State** is internal data managed inside a component.  
It can change over time and causes the component to re-render when updated.

The main difference is that **props** are passed from outside and  
cannot be modified by the receiving component, while **state** is managed inside the component and can be updated.

**Props** в React — это входные данные, которые передаются от родительского компонента к дочернему.  
Они доступны только для чтения и позволяют компоненту получать данные и настройки изввне.

**State** — это внутренние данные компонента.  
Они могут изменяться со временем и вызывают повторный рендер при обновлении.

Главное отличие в том, что **props** передаются извне и не могут изменяться получающим компонентом,  
а **state** управляется внутри компонента и может обновляться.

**10. What is the difference between React's class components and functional components?**

**Class components** are ES6 classes that extend React.Component.  
They can use lifecycle methods (like componentDidMount) and manage state using this.state and this.setState.  
They require more boilerplate and use the this keyword.

**Functional components** are plain JavaScript functions that return JSX.  
With React Hooks (like useState and useEffect), they can manage state and side effects.  
They are simpler, cleaner, and are the modern recommended approach.

**Классовые компоненты** — это ES6-классы, которые наследуются от React.Component.  
Они используют методы жизненного цикла (например, componentDidMount) и управляют состоянием через this.state и this.setState.  
Требуют больше шаблонного кода и используют this.

**Функциональные компоненты** — это обычные JavaScript-функции, которые возвращают JSX.  
С помощью React Hooks (например, useState и useEffect) они могут управлять состоянием и побочными эффектами.  
Они проще, чище и являются современным рекомендуемым подходом.

**11. When should you use a class component over a function component?**
You should use a class component only in legacy codebases that already rely on class components or when maintaining older projects that use lifecycle methods without Hooks.  
In modern React development, functional components with Hooks are preferred because they are simpler and more flexible.

Классовые компоненты стоит использовать только в устаревших проектах, где уже используется такой подход, или при поддержке старого кода с методами жизненного цикла без Hooks.  
В современной разработке React предпочтительнее функциональные компоненты с Hooks, так как они проще и более гибкие.

**12. What is React Fiber?**
**React Fiber** is the new reconciliation engine introduced in React 16.  
It improves how React updates the UI by making rendering incremental and interruptible.  
Fiber allows React to split rendering work into small units, pause and resume tasks, and prioritize more important updates,  
which improves performance and responsiveness.

**React Fiber** — это новый механизм согласования (reconciliation), представленный в React 16.  
Он улучшает процесс обновления интерфейса, делая рендеринг поэтапным и прерываемым.  
Fiber позволяет React разбивать работу на небольшие части, приостанавливать и возобновлять задачи,  
а также расставлять приоритеты обновлений, что повышает производительность и отзывчивость приложения.

**13. What is reconciliation?**

**Reconciliation** is the process by which React updates the DOM.  
When state or props change, React creates a new Virtual DOM,  
compares it with the previous version (diffing), determines what has changed,  
and updates only the necessary parts of the real DOM.

**Reconciliation** — это процесс обновления DOM в React.  
Когда изменяются state или props, React создаёт новый Virtual DOM,  
сравнивает его с предыдущей версией (diffing), определяет изменения и  
обновляет только необходимые части реального DOM.

**14. What is the difference between Shadow DOM and Virtual DOM?**

**The Virtual DOM** is a lightweight JavaScript representation of the real DOM used by React to optimize UI updates.  
It compares previous and current versions (diffing) and updates only the changed parts of the real DOM.

The **Shadow DOM** is a browser technology that encapsulates DOM and CSS inside a component.  
It creates a separate DOM tree attached to an element, preventing styles and structure from leaking in or out.

The main difference is that the Virtual DOM is a performance optimization technique used by libraries like React,  
while the Shadow DOM is a native browser feature for encapsulation and style isolation.

**Virtual DOM** — это облегчённая JavaScript-копия реального DOM, используемая в React для оптимизации обновлений интерфейса.  
Он сравнивает предыдущую и текущую версии (diffing) и обновляет только изменённые части реального DOM.

**Shadow DOM** — это технология браузера для инкапсуляции DOM и CSS внутри компонента.  
Он создаёт отдельное дерево DOM, привязанное к элементу, предотвращая «утечку» стилей и структуры наружу и внутрь.

Главное отличие в том, что **Virtual DOM** — это техника оптимизации производительности, используемая библиотеками вроде React,  
а Shadow DOM — нативная браузерная функция для изоляции и инкапсуляции.

**15. What is the difference between Controlled and Uncontrolled React components?**

**Controlled components** are form elements whose values are managed by React state. The component controls the input value through state and updates it via event handlers. React is the single source of truth.

**Uncontrolled components** are form elements that manage their own state internally in the DOM. Their values are accessed using refs instead of being controlled by React state.

The main difference is that **controlled components** rely on React state to manage data, while **uncontrolled components** rely on the DOM.

**Controlled компоненты** — это элементы формы, значения которых управляются состоянием React. Компонент контролирует значение через state и обновляет его с помощью обработчиков событий. React является единственным источником истины.

**Uncontrolled компоненты** — это элементы формы, которые хранят своё состояние внутри DOM. Их значения получают через refs, а не через состояние React.

Главное отличие в том, что **controlled компоненты** управляются через state React, а **uncontrolled** — через DOM.

Example of a controlled component:

```
function ControlledInput() {
  const [value, setValue] = React.useState('');
  return (
    <input
      type="text"
      value={value}
      onChange={(e) => setValue(e.target.value)}
    />
  );
}
```

Example of an uncontrolled component:

```
function UncontrolledInput() {
  const inputRef = React.useRef();
  return <input type="text" ref={inputRef} />;
}
```

**16. How would you lift the state up in a React application, and why is it necessary?**

**Lifting state up** means moving shared state to the closest common parent component.  
Instead of keeping state in child components, you store it in their parent and pass the data down via props.  
The parent also passes callback functions to allow children to update that state.

It is necessary when multiple components need to share or synchronize the same data.  
This ensures a single source of truth and keeps the application predictable and easier to maintain.

**Поднятие состояния (lifting state up)** — это перенос общего состояния в ближайший общий родительский компонент.  
Вместо хранения состояния в дочерних компонентах, оно хранится у родителя и передаётся вниз через props.  
Родитель также передаёт функции-колбэки, чтобы дочерние компоненты могли обновлять это состояние.

Это необходимо, когда несколько компонентов должны использовать или синхронизировать одни и те же данные.  
Такой подход обеспечивает единый источник истины и делает приложение более предсказуемым и удобным в поддержке.

```
// Lifting state up
const Parent = () => {
  const [counter, setCounter] = useState(0);

  return (
    <div>
      <Child1 counter={counter} />
      <Child2 setCounter={setCounter} />
    </div>
  );
};

const Child1 = ({ counter }) => <h1>{counter}</h1>;
const Child2 = ({ setCounter }) => (
  <button onClick={() => setCounter((prev) => prev + 1)}>Increment</button>
);
```

**17. What are Pure Components?**

**Pure Components** are components that prevent unnecessary re-renders by performing a shallow comparison of props (and state in class components).  
In **class components**, React.PureComponent automatically implements shouldComponentUpdate with shallow comparison of props and state.  
In **functional components**, the same behavior is achieved using React.memo.  
React.memo wraps a component and performs a shallow comparison of props.  
The component re-renders only if its props change.  
If needed, you can provide a custom comparison function as a second argument to React.memo.  
**Pure Components** help improve performance, but since the comparison is shallow, they require immutable data structures.  
Mutating objects without changing their reference may prevent updates from being detected.

**Pure Components** — это компоненты, которые предотвращают лишние перерендеры за счёт поверхностного сравнения props (и state в классовых компонентах).  
В **классовых компонентах** React.PureComponent автоматически реализует shouldComponentUpdate с поверхностным сравнением props и state.
В **функциональных компонентах** аналогичное поведение достигается с помощью React.memo.  
React.memo оборачивает компонент и выполняет поверхностное сравнение props. Компонент перерендеривается только если его props изменились.  
При необходимости можно передать собственную функцию сравнения вторым аргументом в React.memo.  
**Pure Components** улучшают производительность, но из-за поверхностного сравнения требуют использования неизменяемых (immutable) данных.  
Мутация объектов без изменения ссылки может привести к тому, что обновление не будет обнаружено.

```
const PureFunctionalExample = React.memo(function ({ value }) {
  return <div>{value}</div>;
});
```

**18. What is the difference between createElement and cloneElement?**

**React.createElement** is used to create a new React element from scratch.  
It takes a **type**, **props**, and **children**, and returns a**new element**.

**React.cloneElement** is used to clone an existing React element and optionally modify its props or children.  
It keeps the original element’s type and key but allows extending or overriding its props.

The main difference is that **createElement creates a new element**, while **cloneElement copies and modifies an existing** one.

**React.createElement** используется для создания нового React-элемента с нуля. Он принимает тип, props и дочерние элементы и возвращает новый элемент.

```
React.createElement('div', { className: 'container' }, 'Hello World');
```

**React.cloneElement** используется для клонирования существующего React-элемента с возможностью изменения его props или children.

```
const element = <button className="btn">Click Me</button>;
const clonedElement = React.cloneElement(element, { className: 'btn-primary' });
```

Он сохраняет исходный тип и key, но позволяет расширить или переопределить свойства.

Главное отличие в том, что **createElement создаёт новый элемент**, а **cloneElement копирует и модифицирует существующий**.

**19. What is the role of PropTypes in React?**

PropTypes is a runtime type-checking mechanism in React used to validate the props passed to a component.  
It helps developers catch bugs by warning in development mode if props have the wrong type or are missing when required.

PropTypes improves code reliability, documentation, and maintainability, but it does not work in production and does not replace TypeScript.

PropTypes — это механизм проверки типов во время выполнения в React, который используется для валидации props, передаваемых в компонент.  
Он помогает находить ошибки, выдавая предупреждения в режиме разработки, если props имеют неверный тип или отсутствуют при обязательности.

PropTypes повышают надёжность, читаемость и поддерживаемость кода, но работают только в режиме разработки и не заменяют TypeScript.

```
import PropTypes from 'prop-types';

function MyComponent({ name, age }) {
  return (
    <div>
      {name} is {age} years old
    </div>
  );
}

MyComponent.propTypes = {
  name: PropTypes.string.isRequired,
  age: PropTypes.number.isRequired,
};
```

**20. What are stateless components?**

**Stateless** components are components that do not manage their own state. They receive data through props and render UI based only on those props.  
They do not use this.state (in classes) or useState (in functions).
In modern React, **stateless** components are usually functional components that simply return JSX without managing internal state or side effects.

**Stateless** components are simpler, easier to test, and more predictable because their output depends only on input props.

**Stateless** компоненты — это компоненты, которые не управляют собственным состоянием. Они получают данные через props и отображают интерфейс только на их основе.  
Они не используют this.state (в классах) или useState (в функциях).
В современном React **stateless** компоненты обычно являются функциональными компонентами, которые просто возвращают JSX без управления внутренним состоянием или побочными эффектами.

**Stateless**компоненты проще, легче тестируются и более предсказуемы, так как их результат зависит только от входных props.

```
function StatelessComponent({ message }) {
  return <div>{message}</div>;
}
```

**21. What are stateful components?**

**Stateful** components are components that manage and control their own state. They store data inside the component and update it over time, which causes re-rendering when the state changes.

In class components, state is managed using this.state and this.setState. In functional components, state is managed using Hooks such as useState and useReducer.

**Stateful** components are used when a component needs to handle dynamic data, user interactions, or side effects.

**Stateful** компоненты — это компоненты, которые управляют собственным состоянием. Они хранят данные внутри себя и обновляют их со временем, что вызывает повторный рендер при изменении состояния.

В классовых компонентах состояние управляется через this.state и this.setState. В функциональных компонентах состояние управляется с помощью хуков, таких как useState и useReducer.

**Stateful** компоненты используются, когда компоненту нужно обрабатывать динамические данные, действия пользователя или побочные эффекты.

```
function StatefulComponent() {
  const [count, setCount] = React.useState(0);

  return (
    <div>
      <p>{count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
}
```

**22. What are the recommended ways for type checking of React component props?**
The recommended ways for type checking React component props are **TypeScript** and **PropTypes.**

**TypeScript** is the most recommended approach in modern React development. It provides static type checking at compile time, improves developer experience, catches errors early, and offers better scalability for large applications.

```
interface MyComponentProps {
  name: string;
  age: number;
}

function MyComponent({ name, age }: MyComponentProps) {
  return <div>{name} is {age} years old</div>;
}
```

**PropTypes** is a runtime type-checking solution built for React. It validates props during development and shows warnings if types are incorrect, but it does not work in production and is less powerful than TypeScript.

```
import PropTypes from 'prop-types';

function MyComponent({ name, age }) {
  return (
    <div>
      {name} is {age} years old
    </div>
  );
}

MyComponent.propTypes = {
  name: PropTypes.string.isRequired,
  age: PropTypes.number.isRequired,
};
```

In modern projects, TypeScript is preferred, while **PropTypes** is mainly used in smaller projects or legacy codebases.

Рекомендуемые способы проверки типов props в React — это **TypeScript** и **PropTypes**.

**TypeScript** является наиболее рекомендуемым подходом в современной разработке React. Он обеспечивает статическую проверку типов на этапе компиляции, улучшает опыт разработки, помогает находить ошибки раньше и лучше масштабируется в крупных приложениях.

**PropTypes** — это механизм проверки типов во время выполнения, предназначенный для React. Он проверяет props в режиме разработки и показывает предупреждения при ошибках типов, но не работает в production и менее мощный по сравнению с TypeScript.

В современных проектах предпочтение отдаётся **TypeScript**, а **PropTypes** чаще используется в небольших или устаревших проектах.

**23. Why does React recommend against mutating state?**

React recommends against **mutating state** because it relies on reference comparison to detect changes.  
If you mutate state directly, the reference may stay the same, and React may not detect the update, which can prevent re-rendering.

**Immutability** ensures predictable state updates, easier debugging, better performance optimization  
(e.g., with PureComponent or React.memo), and compatibility with React’s reconciliation process.

Instead of **mutating state**, you should create a new object or array when updating it.

React не рекомендует изменять (**мутировать**) state напрямую, потому что он использует сравнение ссылок для определения изменений.  
Если изменить объект напрямую, ссылка может остаться прежней, и React не обнаружит обновление, что может привести к отсутствию перерендеринга.

Неизменяемость (**immutability**) обеспечивает предсказуемость обновлений состояния, упрощает отладку, улучшает оптимизацию производительности  
(например, с PureComponent или React.memo) и корректную работу механизма reconciliation.

Вместо мутации состояния следует создавать новый объект или массив при обновлении.

**24. What are the benefits of using hooks in React?**

**Hooks** allow functional components to use state, lifecycle features, and side effects without writing class components. They make code simpler and easier to read.

Benefits of hooks include better code reuse through custom hooks, improved separation of concerns, less boilerplate compared to classes, and easier testing.  
Hooks also allow logic to be organized by feature instead of lifecycle methods.

Overall, hooks make components more flexible, maintainable, and reusable.

**Хуки** позволяют функциональным компонентам использовать состояние, методы жизненного цикла и побочные эффекты без написания классовых компонентов.  
Они делают код проще и понятнее.

Преимущества хуков включают повторное использование логики через пользовательские хуки, лучшее разделение ответственности,  
меньше шаблонного кода по сравнению с классами и более простое тестирование. Хуки позволяют организовывать логику по функциональности, а не по методам жизненного цикла.

В целом хуки делают компоненты более гибкими, поддерживаемыми и переиспользуемыми.

**25. What are the rules of React hooks?**
The rules of React Hooks are:

- Only call hooks at the top level. Do not call hooks inside loops, conditions, or nested functions. This ensures that hooks are called in the same order on every render.

- Only call hooks from React function components or from custom hooks. Do not call hooks from regular JavaScript functions or class components.

These rules ensure consistent hook execution order and correct state management.

Правила React Hooks:

- Вызывать хуки только на верхнем уровне компонента. Нельзя вызывать хуки внутри циклов, условий или вложенных функций. Это гарантирует одинаковый порядок вызова хуков при каждом рендере.

- Вызывать хуки только внутри функциональных компонентов React или внутри пользовательских хуков. Нельзя вызывать хуки в обычных JavaScript-функциях или классовых компонентах.

Эти правила обеспечивают корректный порядок выполнения хуков и правильное управление состоянием.

**26. What is the difference between useEffect and useLayoutEffect in React?**

The difference between **useEffect** and **useLayoutEffect** is when they run in the rendering process.

**useEffect** runs asynchronously after the browser has painted the screen. It does not block visual updates and is used for data fetching, subscriptions, logging, and most side effects.

**useLayoutEffect** runs synchronously after DOM mutations but before the browser paints the screen.  
It blocks painting until it finishes and is used when you need to measure or modify the DOM before the user sees it.

In most cases, useEffect is preferred. **useLayoutEffect** should be used only when you need to read layout or make visual DOM changes immediately.

```
import React, { useEffect, useLayoutEffect, useRef } from 'react';

function Example() {
  const ref = useRef();

  useEffect(() => {
    console.log('useEffect: Runs after DOM paint');
  });

  useLayoutEffect(() => {
    console.log('useLayoutEffect: Runs before DOM paint');
    console.log('Element width:', ref.current.offsetWidth);
  });

  return <div ref={ref}>Hello</div>;
}
```

Разница между **useEffect** и **useLayoutEffect** заключается в моменте их выполнения.

**useEffect** выполняется асинхронно после того, как браузер отрисовал изменения на экране. Он не блокирует отображение и используется для загрузки данных, подписок, логирования и большинства побочных эффектов.

**useLayoutEffect** выполняется синхронно после изменения DOM, но до того, как браузер отрисует экран.  
Он блокирует отрисовку до завершения и используется, когда нужно измерить или изменить DOM до того, как пользователь увидит результат.

В большинстве случаев предпочтительно использовать useEffect. **useLayoutEffect** применяется только когда требуется работа с layout или немедленные визуальные изменения DOM.

**27. What does the dependency array of useEffect affect?**
The **dependency array of useEffect** controls when the effect runs.

If the dependency array is empty ([]), the effect runs only once after the initial render.

If dependencies are provided ([value1, value2]), the effect runs after the initial render and again whenever any dependency changes.

If no dependency array is provided, the effect runs after every render.

The dependency array helps optimize performance and ensures that effects run only when necessary.

**Массив зависимостей useEffect** определяет, когда будет выполняться эффект.

Если массив пустой ([]), эффект выполняется только один раз после первого рендера.

Если указаны зависимости ([value1, value2]), эффект выполняется после первого рендера и каждый раз, когда изменяется хотя бы одна из зависимостей.

Если массив зависимостей не указан, эффект выполняется после каждого рендера.

Массив зависимостей помогает оптимизировать производительность и гарантирует, что эффект запускается только при необходимости.

**28. What is the useRef hook in React and when should it be used?**

**useRef** is a React hook that returns a mutable object with a .current property. It is used to store a value that persists across renders without causing a re-render when it changes.

It is commonly used to access DOM elements directly, store previous values, keep mutable variables, or manage timers and intervals.

Unlike state, updating **useRef** does not trigger a re-render. It should be used when you need to keep a persistent value or reference that does not affect the UI rendering.

**useRef** — это хук React, который возвращает изменяемый объект с свойством .current. Он используется для хранения значения между рендерами без вызова повторного рендера при его изменении.

```
import React, { useRef, useEffect } from 'react';

function TextInputWithFocusButton() {
  const inputEl = useRef(null);
  useEffect(() => {
    inputEl.current.focus();
  }, []);
  return <input ref={inputEl} type="text" />;
}
```

Чаще всего используется для доступа к DOM-элементам, хранения предыдущих значений, сохранения изменяемых переменных, управления таймерами или интервалами.

В отличие от state, обновление **useRef** не вызывает перерендер. Его следует использовать, когда нужно сохранить значение или ссылку, не влияющую напрямую на отображение интерфейса.

**29. What is the purpose of callback function argument format of setState() in React class components and when should it be used?**
The callback function argument format of setState() is used to update state based on the previous state or props. Instead of passing an object, you pass a function:
**setState((prevState, props) => newState).**

It should be used when the new state depends on the previous state, because state updates in React are asynchronous and may be batched.  
Using the functional form ensures you always receive the latest state value and avoid bugs caused by stale data.

```
this.setState((prevState, props) => ({
  counter: prevState.counter + props.increment,
}));
```

The second callback argument of setState (setState(updater, callback)) can also be used to run code after the state has been updated and the component has re-rendered.

Функциональный формат аргумента setState() используется для обновления состояния на основе предыдущего state или props. Вместо объекта передаётся функция:
**setState((prevState, props) => newState).**

Его следует использовать, когда новое состояние зависит от предыдущего, потому что обновления состояния в React асинхронны и могут объединяться (batching).  
Функциональный формат гарантирует получение актуального значения state и предотвращает ошибки из-за устаревших данных.

Второй аргумент setState (setState(updater, callback)) можно использовать для выполнения кода после обновления состояния и завершения перерендеринга компонента.

**30. What is the useCallback hook in React and when should it be used?**

**useCallback** is a React hook that memoizes a function and returns the same function instance between renders unless its dependencies change.

It is mainly used to prevent unnecessary re-creations of functions on every render, especially when passing callbacks to memoized child components (e.g., with React.memo).  
This helps avoid unnecessary re-renders caused by changing function references.

**useCallback** should be used when performance optimization is needed, particularly in large components or when functions are passed as props to optimized children.  
It is not necessary in every component.

```
const memoizedCallback = useCallback(() => {
  doSomething(a, b);
}, [a, b]);
```

**useCallback** — это хук React, который запоминает (мемоизирует) функцию и возвращает одну и ту же ссылку между рендерами, если зависимости не изменились.

Он используется для предотвращения повторного создания функций при каждом рендере, особенно когда колбэки передаются в мемоизированные дочерние компоненты (например, с React.memo).  
Это помогает избежать лишних перерендеров из-за изменения ссылки на функцию.

**useCallback** следует использовать для оптимизации производительности, особенно в крупных компонентах или когда функции передаются как props в оптимизированные дочерние компоненты.  
Использовать его в каждом компоненте не требуется.

**31. What is the useMemo hook in React and when should it be used?**

**useMemo** is a React hook that memoizes the result of a computation and returns the cached value unless its dependencies change.

It is used to optimize performance by avoiding expensive recalculations on every render. React recomputes the value only when one of the dependencies in the dependency array changes.

**useMemo** should be used when you have heavy computations, derived data, or expensive calculations that run during rendering.  
It is a performance optimization and should not be used unnecessarily.

```
const memoizedValue = useMemo(() => computeExpensiveValue(a, b), [a, b]);
```

**useMemo** — это хук React, который запоминает (мемоизирует) результат вычисления и возвращает сохранённое значение, если зависимости не изменились.

Он используется для оптимизации производительности, предотвращая повторные тяжёлые вычисления при каждом рендере.  
Значение пересчитывается только тогда, когда изменяется одна из зависимостей.

**useMemo** следует применять при сложных вычислениях, производных данных или ресурсоёмких операциях во время рендера.  
Это инструмент оптимизации, и его не стоит использовать без необходимости.

**32. What is the useReducer hook in React and when should it be used?**

**useReducer** is a React hook used for managing complex state logic using a reducer function.  
It works similarly to Redux: you dispatch actions, and a reducer function determines how the state changes.

It is useful when state logic is complex, involves multiple related values, or when the next state depends on the previous one.  
It also helps keep state transitions predictable and centralized.

**useReducer** is often preferred over useState when managing complex forms, multiple state updates, or when state logic needs better structure and scalability.

```
const [state, dispatch] = useReducer(reducer, initialState);
```

**useReducer** — это хук React для управления сложной логикой состояния с помощью функции-редьюсера.  
Он работает по принципу, похожему на Redux: вы отправляете действия (actions), а функция-редьюсер определяет, как изменится состояние.

Он полезен, когда логика состояния сложная, включает несколько связанных значений или когда новое состояние зависит от предыдущего.  
Также он делает переходы состояния более предсказуемыми и централизованными.

**useReducer** часто предпочтительнее useState при работе со сложными формами, множественными обновлениями состояния или когда требуется более структурированная и масштабируемая логика.

**33. What is the useId hook in React and when should it be used?**

**useId** is a React hook that generates a unique and stable ID for a component instance.  
The ID remains consistent across renders and works correctly with server-side rendering (SSR) and hydration.

It is mainly used for accessibility purposes, such as linking a label to an input (using htmlFor and id) or connecting ARIA attributes.

```
import { useId } from 'react';

function MyComponent() {
  const id = useId();

  return (
    <div>
      <label htmlFor={id}>Name:</label>
      <input id={id} type="text" />
    </div>
  );
```

**useId** should be used when you need unique IDs that must match between the server and the client. It should not be used for generating keys in lists.

**useId** — это хук React, который генерирует уникальный и стабильный идентификатор для экземпляра компонента.  
Этот ID остаётся постоянным между рендерами и корректно работает при серверном рендеринге (SSR) и гидратации.

Он в основном используется для доступности, например, для связывания label и input (через htmlFor и id) или для ARIA-атрибутов.

**useId** следует использовать, когда нужны уникальные идентификаторы, совпадающие на сервере и клиенте.  
Его не следует использовать для генерации key в списках.

**34. Can you explain how to create and use custom hooks in React?**

**Custom hooks** are JavaScript functions that allow you to extract and reuse stateful logic between components.  
A custom hook must start with the word "use" and can call other React hooks inside it.

To create a custom hook, define a function (e.g., useSomething), use built-in hooks like useState or useEffect inside it, and return the values or functions you want to expose.

**Custom hooks** are used when you need to reuse logic such as data fetching, form handling, subscriptions, or other side effects across multiple components.  
They help keep components clean and improve code reusability and separation of concerns.

**Custom hooks**

```
function useForm(initialState) {
  const [formData, setFormData] = useState(initialState);
  const handleChange = (e) =>
    setFormData({ ...formData, [e.target.name]: e.target.value });
  return [formData, handleChange];
}
```

Use the Hook:

```
function MyForm() {
  const [formData, handleChange] = useForm({ name: '', email: '' });
  return <input name="name" value={formData.name} onChange={handleChange} />;
}
```

**Пользовательские хуки** — это JavaScript-функции, которые позволяют выносить и переиспользовать логику состояния между компонентами.  
Имя пользовательского хука должно начинаться с "use", и внутри него можно вызывать другие хуки React.

Чтобы создать **пользовательский хук**, нужно определить функцию (например, useSomething), использовать внутри неё встроенные хуки, такие как useState или useEffect,  
и вернуть значения или функции, которые нужно использовать снаружи.

**Пользовательские хуки** применяются, когда необходимо переиспользовать логику — например, для загрузки данных, работы с формами, подписок или других побочных эффектов.  
Они помогают сделать компоненты чище и улучшают переиспользуемость и разделение ответственности.

**35. What does re-rendering mean in React?**

**Re-rendering** in React means that a component function is executed again (or a class component’s render method is called again) to produce a new Virtual DOM.  
This happens when state changes, props change, or a parent component re-renders.

During **re-rendering**, React compares the new Virtual DOM with the previous one (diffing) and updates only the parts of the real DOM that have changed.

**Re-rendering** does not mean the entire real DOM is rebuilt — only the necessary updates are applied.

Повторный рендер (**re-rendering**) в React означает, что функция компонента выполняется снова (или метод render в классовом компоненте вызывается повторно) для создания нового Virtual DOM.  
Это происходит при изменении state, props или при перерендере родительского компонента.

Во время повторного рендера React сравнивает новый Virtual DOM с предыдущим (diffing) и обновляет только изменённые части реального DOM.

Повторный рендер не означает полную перестройку DOM — обновляются только необходимые элементы.

**36. What is forwardRef() in React used for?**

**forwardRef** is a React API that allows a component to pass a ref it receives down to one of its child components.  
It is mainly used to give parent components access to a child’s DOM element or instance.

Normally, refs cannot be directly attached to functional components.  
**forwardRef** enables functional components to accept a ref and forward it to a DOM node or another component.

It is commonly used for reusable UI components like inputs, modals, or buttons where the parent needs to control focus, selection, or other DOM methods.

**forwardRef** — это API React, который позволяет компоненту передать полученный ref дальше своему дочернему элементу.  
Обычно используется для предоставления родительскому компоненту доступа к DOM-элементу или экземпляру дочернего компонента.

По умолчанию ref нельзя напрямую передать функциональному компоненту.  
**forwardRef** позволяет функциональному компоненту принять ref и передать его к DOM-узлу или другому компоненту.

Чаще всего используется в переиспользуемых UI-компонентах, таких как input, modal или button, когда родителю нужно управлять фокусом, выделением или другими DOM-методами.

**37. What are error boundaries in React for?**

**Error boundaries** are React components that catch JavaScript errors in their child component tree during rendering, lifecycle methods, and constructors.  
They prevent the whole application from crashing by displaying a fallback UI instead of the broken component tree.

**Error boundaries** are implemented using class components with componentDidCatch and getDerivedStateFromError lifecycle methods.

They do not catch errors inside event handlers, asynchronous code (like setTimeout), or server-side rendering.

**Error boundaries** — это компоненты React, которые перехватывают JavaScript-ошибки в дочерних компонентах во время рендеринга, в методах жизненного цикла и конструкторах.  
Они предотвращают падение всего приложения, отображая резервный интерфейс (fallback UI) вместо повреждённого дерева компонентов.

**Error boundaries** реализуются с помощью классовых компонентов, используя методы componentDidCatch и getDerivedStateFromError.

Они не перехватывают ошибки в обработчиках событий, асинхронном коде (например, setTimeout) или при серверном рендеринге.

**38. What is React Suspense?**

React Suspense is a feature that allows components to “wait” for something before rendering, such as lazy-loaded components or asynchronous data.  
While waiting, Suspense displays a fallback UI (like a loading spinner).

It is commonly used with React.lazy for code-splitting and can also be used with data-fetching libraries that support Suspense.

Suspense improves user experience by handling loading states declaratively inside the component tree.

React Suspense — это механизм, который позволяет компонентам «ожидать» загрузки данных или кода перед отображением.  
Пока происходит ожидание, Suspense показывает резервный интерфейс (например, индикатор загрузки).

Чаще всего используется вместе с React.lazy для ленивой загрузки компонентов и может применяться с библиотеками для загрузки данных, поддерживающими Suspense.

Suspense улучшает пользовательский опыт, позволяя декларативно управлять состояниями загрузки внутри дерева компонентов.

**39. Explain what React hydration is?**

React hydration is the process of attaching React’s event listeners and functionality to HTML that was pre-rendered on the server.  
Instead of re-rendering everything on the client, React reuses the existing server-generated markup and makes it interactive.

Hydration is used in server-side rendering (SSR) frameworks like Next.js to improve performance and initial page load time.  
React compares the server-rendered HTML with the client-side Virtual DOM and connects them.

Hydration — это процесс подключения логики React и обработчиков событий к HTML, который был предварительно сгенерирован на сервере.  
Вместо полной перерисовки на клиенте React повторно использует готовую разметку и делает её интерактивной.

Гидратация используется при серверном рендеринге (SSR), например, в Next.js, чтобы улучшить производительность и ускорить первую загрузку страницы.  
React сравнивает серверную разметку с клиентским Virtual DOM и связывает их.

**40. What are React Portals used for?**

React Portals are used to render a component’s children into a different part of the DOM tree outside the parent component’s DOM hierarchy.

They are commonly used for modals, tooltips, dropdowns, or overlays where the UI element needs to visually break out of its parent container  
(for example, to avoid overflow or z-index issues).

Even though the DOM position changes, the portal component still behaves as part of the React component tree, so context and event bubbling work normally.

React Portals используются для рендеринга дочерних элементов компонента в другую часть DOM-дерева вне иерархии родительского элемента.

Обычно применяются для модальных окон, тултипов, выпадающих меню или оверлеев, когда элемент интерфейса должен «выйти» за пределы родительского контейнера  
(например, чтобы избежать проблем с overflow или z-index).

Несмотря на изменение позиции в DOM, портал остаётся частью React-дерева компонентов, поэтому контекст и всплытие событий работают как обычно.

**41. What is React strict mode and what are its benefits?**

**React Strict Mode** is a development tool that helps identify potential problems in an application.  
It does not render any visible UI and works only in development mode.

Strict Mode activates additional checks and warnings for **unsafe lifecycle methods**, **legacy APIs**, **unexpected side effects**, and **deprecated features**.  
In React 18, it also intentionally double-invokes certain functions (like components and effects) in development to detect side effects.

Its benefits include early detection of bugs, improved code quality, safer migration to future React versions, and better adherence to best practices.

```
<React.StrictMode>
  <App />
</React.StrictMode>
```

**React Strict Mode** — это инструмент разработки, который помогает выявлять потенциальные проблемы в приложении.  
Он не отображает никакого интерфейса и работает только в режиме разработки.

Strict Mode включает дополнительные проверки и предупреждения для **небезопасных методов жизненного цикла**, **устаревших API**, **неожиданных побочных эффектов** и **deprecated-функций**.  
В React 18 он также намеренно вызывает некоторые функции (например, компоненты и эффекты) дважды в режиме разработки для выявления побочных эффектов.

Преимущества включают раннее обнаружение ошибок, улучшение качества кода, более безопасную миграцию на будущие версии React и соблюдение лучших практик.

**42. What is code splitting in a React application?**

**Code splitting** is a technique that splits a React application’s bundle into smaller chunks that are loaded on demand instead of loading the entire application at once.

It improves performance and reduces initial load time by loading only the code required for the current page or feature.  
In React, code splitting is commonly implemented using dynamic import() and React.lazy together with Suspense.

This approach makes applications faster and more scalable, especially large ones.

```
// Using React.lazy and Suspense
const LazyComponent = React.lazy(() => import('./LazyComponent'));

function App() {
  return (
    <React.Suspense fallback={<div>Loading...</div>}>
      <LazyComponent />
    </React.Suspense>
  );
}
```

**Code splitting** — это техника разделения общего бандла приложения React на более мелкие части, которые загружаются по мере необходимости, а не все сразу.

Это улучшает производительность и уменьшает время первоначальной загрузки, загружая только тот код, который нужен для текущей страницы или функциональности.  
В React обычно используется динамический import() вместе с React.lazy и Suspense.

Такой подход делает приложения быстрее и лучше масштабируемыми, особенно крупные проекты.

**43. How would one optimize the performance of React contexts to reduce rerenders?**
To optimize React Context performance and reduce rerenders, minimize how often the provider value changes and limit how many components subscribe to the same context.

**Key approaches:**

- **Split contexts:** separate unrelated values into different contexts so changes don’t rerender everything.

- **Memoize the provider value:** wrap the value object in useMemo so its reference changes only when needed.

- **Memoize callbacks inside the value:** use useCallback to keep function references stable.

- **Keep state close to where it’s used:** don’t put frequently changing UI state (like input text) in a global context.

- **Use React.memo for consumers:** memoize components so they don’t rerender due to parent rerenders (note: context changes still trigger rerenders for consumers).

- **Use context selectors / external libs:** tools like use-context-selector or state libraries (Zustand, Jotai, Redux) can let components subscribe to only the slice they need.

The main idea is to reduce provider value reference changes and narrow the subscription scope.

Чтобы оптимизировать производительность React Context и уменьшить количество перерендеров, нужно реже менять значение value у Provider и уменьшить число компонентов, подписанных на один и тот же контекст.

**Основные подходы:**

- **Разделять контексты:** выносить несвязанные данные в разные Context, чтобы изменения не перерендеривали всех.

- **Мемоизировать value провайдера:** оборачивать объект value в useMemo, чтобы ссылка менялась только при необходимости.

- **Мемоизировать функции внутри value:** использовать useCallback, чтобы ссылки на колбэки были стабильными.

- **Держать state ближе к месту использования:** не класть часто меняющееся UI-состояние (например, текст инпута) в глобальный контекст.

- **Использовать React.memo для потребителей:** мемоизировать компоненты, чтобы они меньше перерендеривались из-за перерендеров родителей (но изменения контекста всё равно триггерят подписчиков).

- **Использовать context selectors / внешние библиотеки:** например use-context-selector или стейт-менеджеры (Zustand, Jotai, Redux), чтобы подписываться только на нужный кусок состояния.

Идея одна: стабилизировать ссылку value и сузить область подписки.

**44. What is the Flux pattern?**

The Flux pattern is an architectural pattern for managing application state with a unidirectional data flow.  
It was introduced by Facebook to make state changes predictable and easier to debug.

In Flux, data flows in one direction:

- **Action** — describes what happened.

- **Dispatcher** — sends the action to stores.

- **Store** — updates the state based on the action.

- **View** — re-renders based on the updated state.

The main idea of Flux is centralized state management and predictable updates through explicit actions.

Flux — это архитектурный паттерн управления состоянием приложения с однонаправленным потоком данных.  
Он был предложен Facebook для того, чтобы сделать изменения состояния более предсказуемыми и удобными для отладки.

Во Flux данные движутся в одном направлении:

- **Action** — описывает, что произошло.

- **Dispatcher** — передаёт действие в хранилища.

- **Store** — обновляет состояние на основе действия.

- **View** — перерендеривается при изменении состояния.

Главная идея Flux — централизованное управление состоянием и предсказуемые обновления через явные действия.

**45. Explain one-way data flow of React**

One-way data flow in React means that data flows in a single direction — from parent components to child components through props.

The parent component holds the state and passes it down to children. If a child needs to update the data, it calls a callback function provided by the parent.  
The parent updates the state, and the updated data flows down again.

This pattern makes the application predictable, easier to debug, and simpler to maintain because the state has a single source of truth.

```
function Parent() {
  const [count, setCount] = React.useState(0);
  return <Child count={count} increment={() => setCount(count + 1)} />;
}

function Child({ count, increment }) {
  return <button onClick={increment}>Count: {count}</button>;
}
```

Однонаправленный поток данных в React означает, что данные передаются в одном направлении — от родительских компонентов к дочерним через props.

Родитель хранит состояние и передаёт его вниз. Если дочернему компоненту нужно изменить данные, он вызывает функцию-колбэк, переданную родителем.  
Родитель обновляет state, и обновлённые данные снова передаются вниз.

Такой подход делает приложение более предсказуемым, упрощает отладку и поддержку, поскольку существует единый источник истины.

**46. What are some pitfalls of using context in React?**
Some pitfalls of using React Context include unnecessary rerenders, tight coupling, and reduced reusability.

When the context value changes, all consuming components rerender, even if they use only part of the data. This can hurt performance if the context holds frequently changing state.

Context can also create tight coupling between components and global state, making components harder to reuse outside that context.

It is not ideal for high-frequency updates (like animations or input typing) and is not a full state management solution for complex applications.

Некоторые недостатки использования React Context включают лишние перерендеры, сильную связанность компонентов и снижение переиспользуемости.

Когда значение context меняется, все подписанные компоненты перерендериваются, даже если используют только часть данных. Это может негативно влиять на производительность, если состояние часто изменяется.

Context также создаёт тесную зависимость компонентов от глобального состояния, что усложняет их повторное использование вне этого контекста.

Он не подходит для часто обновляющихся данных (например, анимаций или ввода текста) и не является полноценной заменой сложным системам управления состоянием.

**47. What are some React anti-patterns?**

Some common React anti-patterns include:

- Mutating state directly instead of creating new objects.

- Using array index as key in dynamic lists.

- Storing derived data in state instead of calculating it from props/state.

- Overusing context for frequently changing state.

- Creating functions inside render without need (causing unnecessary rerenders).

- Copying props into state unnecessarily.

- Large components with too much logic instead of splitting into smaller ones.

- Ignoring dependency arrays in useEffect or disabling ESLint hook rules.

These anti-patterns can lead to performance issues, bugs, and harder-to-maintain code.

Некоторые распространённые анти-паттерны в React:

- Прямая мутация state вместо создания нового объекта.

- Использование индекса массива как key в динамических списках.

- Хранение производных данных в state вместо вычисления их из props/state.

- Чрезмерное использование context для часто изменяющегося состояния.

- Создание функций внутри render без необходимости (лишние перерендеры).

- Копирование props в state без реальной причины.

- Слишком большие компоненты с избыточной логикой вместо разделения на более мелкие.

- Игнорирование массива зависимостей в useEffect или отключение правил ESLint для хуков.

Такие анти-паттерны приводят к проблемам с производительностью, ошибкам и усложняют поддержку кода.

**48. How do you decide between using React state, context, and external state managers?**
Decide based on scope, update frequency, and complexity.

Use React state (useState/useReducer) when the state is local to a component or a small subtree, updates frequently, and doesn’t need to be shared widely.

Use Context when you need to share relatively stable data across many components without prop drilling (e.g., theme, locale, auth user, feature flags).  
Avoid putting high-frequency changing data into context because it can trigger many rerenders.

Use external state managers (Redux, Zustand, Jotai, MobX, etc.) when state is truly global or complex: many updates from different places,  
complex interactions, caching/server state, time-travel/debug tooling needs, or you need fine-grained subscriptions to avoid rerenders.

A good rule: keep state as close as possible to where it’s used; lift it up only when needed; use context for app-wide “environment” data;  
use a state manager when app complexity and performance needs outgrow React’s built-in tools.

Решай по трём критериям: область применения, частота обновлений и сложность.

Используй state (useState/useReducer), когда состояние локальное для компонента или небольшой ветки, часто меняется и не нужно многим частям приложения.

Используй Context, когда нужно делиться относительно стабильными данными по всему дереву без prop drilling (например, тема, язык, текущий пользователь, feature flags).  
Не клади в context часто меняющиеся данные — это может вызвать много перерендеров.

Используй внешние менеджеры состояния (Redux, Zustand, Jotai, MobX и т.д.), когда состояние реально глобальное или сложное: много обновлений из разных мест,  
сложные зависимости, кеширование/серверное состояние, нужны инструменты отладки или тонкая подписка на “слайсы” состояния для уменьшения перерендеров.

Правило: держи состояние максимально близко к месту использования; поднимай выше только при необходимости; context — для “глобального окружения”;  
менеджер — когда сложность и требования к перформансу перерастают встроенные средства React.

**49. Explain what happens when setState is called in React?**
When **setState** is called in React, it schedules an update to the component’s state rather than updating it immediately.

React marks the component as needing an update and may batch multiple state updates together for performance. During the next render cycle,  
React recalculates the component by calling render (or re-running the function component), creates a new Virtual DOM, compares it with  
the previous one (diffing), and updates only the changed parts of the real DOM.

State updates are asynchronous, so accessing this.state immediately after **setState** may not reflect the updated value.  
That’s why the functional form of **setState** should be used when the new state depends on the previous state.

Когда вызывается **setState** в React, обновление состояния не происходит мгновенно — оно планируется (scheduled).

React помечает компонент как требующий обновления и может объединять несколько вызовов **setState** (batching) для оптимизации производительности.  
В следующем цикле рендера React пересчитывает компонент (вызывает render или повторно выполняет функциональный компонент), создаёт новый Virtual DOM,  
сравнивает его с предыдущим (diffing) и обновляет только изменённые части реального DOM.

Обновления состояния асинхронны, поэтому чтение this.state сразу после **setState** может вернуть старое значение. Именно поэтому функциональная форма  
**setState** используется, когда новое состояние зависит от предыдущего.

```
function Counter() {
  const [count, setCount] = React.useState(0);

  const increment = () => {
    setCount(count + 1); // Calls setState to update state
  };

  return <button onClick={increment}>Count: {count}</button>;
}
```

**50. Explain prop drilling**

**Prop drilling** is the process of passing data from a parent component to deeply nested child components through multiple intermediate components that do not actually use the data.

This happens when props must be forwarded through several levels just to reach the component that needs them. It can make the code harder to read, maintain, and refactor.

**Prop drilling** can be avoided by using Context, composition patterns, or external state management solutions when appropriate.

```
function Grandparent() {
  const data = 'Hello from Grandparent';
  return <Parent data={data} />;
}

function Parent({ data }) {
  return <Child data={data} />;
}

function Child({ data }) {
  return <p>{data}</p>;
}
```

**Prop drilling** — это передача данных от родительского компонента к глубоко вложенному дочернему компоненту через несколько промежуточных компонентов, которые сами эти данные не используют.

Это приводит к тому, что props передаются через несколько уровней только ради конечного получателя, что усложняет чтение, поддержку и рефакторинг кода.

Избежать **prop drilling** можно с помощью Context, композиции компонентов или внешних менеджеров состояния при необходимости.

**51. Describe lazy loading in React**

**Lazy loading** in React is a technique where components or code are loaded only when they are needed, instead of loading everything at the initial page load.

It is commonly implemented using React.lazy with dynamic import(), and wrapped with Suspense to show a fallback UI (like a loader) while the component is being loaded.

**Lazy loading** improves performance by reducing the initial bundle size and speeding up the first page load, especially in large applications.

```
import React, { Suspense, lazy } from 'react';

const LazyComponent = lazy(() => import('./LazyComponent'));

function App() {
  return (
    <Suspense fallback={<div>Loading...</div>}>
      <LazyComponent />
    </Suspense>
  );
}
```

**Lazy loading** в React — это техника, при которой компоненты или части кода загружаются только тогда, когда они действительно нужны, а не при первоначальной загрузке страницы.

Обычно реализуется с помощью React.lazy вместе с динамическим import(), а также оборачивается в Suspense для отображения резервного интерфейса (например, индикатора загрузки) во время загрузки компонента.

**Lazy loading** улучшает производительность, уменьшая размер начального бандла и ускоряя первую загрузку страницы, особенно в крупных приложениях.

**52. Discuss synthetic events in React**
**Synthetic events** in React are cross-browser wrapper objects around the browser’s native events. They normalize event behavior so that events work consistently across different browsers.

React uses a single event listener at the root (event delegation) and dispatches events through its synthetic event system. This improves performance and provides a consistent API.

**Synthetic events** have the same interface as native events (e.g., preventDefault, stopPropagation), but they are managed by React.

In older versions of React, synthetic events were pooled (reused), but since React 17, event pooling has been removed.

```
function MyComponent() {
  const handleClick = (event) => {
    event.preventDefault();
    console.log('Button clicked');
  };

  return <button onClick={handleClick}>Click me</button>;
}
```

**Synthetic events** в React — это кроссбраузерная обёртка над нативными событиями браузера. Они обеспечивают одинаковое поведение событий во всех браузерах.

React использует делегирование событий (один обработчик на корневом уровне) и управляет событиями через собственную систему synthetic events. Это повышает производительность и даёт единый API.

**Synthetic events** имеют тот же интерфейс, что и нативные события (например, preventDefault, stopPropagation), но управляются React.

В старых версиях React synthetic events использовали пуллинг (повторное использование объектов), но начиная с React 17 механизм пуллинга был удалён.

**53. Explain the React component lifecycle methods in class components.**
In class components, the lifecycle methods describe different stages of a component’s life: mounting, updating, and unmounting.

**Mounting (when the component is created and inserted into the DOM):
**

- constructor — initializes state and binds methods.

- static getDerivedStateFromProps — syncs state with props (rarely used).

- render — returns JSX.

- componentDidMount — runs after the component is added to the DOM (used for data fetching, subscriptions, side effects).

**Updating (when props or state change):**

- static getDerivedStateFromProps — called before every render.

- shouldComponentUpdate — determines whether re-rendering should occur.

- render — re-renders UI.

- getSnapshotBeforeUpdate — captures information from the DOM before changes.

- componentDidUpdate — runs after the update (used for side effects based on changes).

**Unmounting (when the component is removed from the DOM):**

- componentWillUnmount — used for cleanup (timers, subscriptions, event listeners).

Some legacy methods like componentWillMount, componentWillReceiveProps, and componentWillUpdate are deprecated.

В классовых компонентах методы жизненного цикла описывают этапы жизни компонента: монтирование, обновление и размонтирование.

**Монтирование (создание и добавление в DOM):**

- constructor — инициализация состояния и привязка методов.

- static getDerivedStateFromProps — синхронизация state с props (редко используется).

- render — возвращает JSX.

- componentDidMount — вызывается после добавления в DOM (используется для загрузки данных, подписок, побочных эффектов).

**Обновление (при изменении props или state):**

- static getDerivedStateFromProps — вызывается перед каждым рендером.

- shouldComponentUpdate — определяет, нужно ли выполнять повторный рендер.

- render — обновляет интерфейс.

- getSnapshotBeforeUpdate — получает данные из DOM перед обновлением.

- componentDidUpdate — вызывается после обновления (для побочных эффектов).

**Размонтирование (удаление из DOM):**

- componentWillUnmount — используется для очистки (таймеры, подписки, обработчики событий).

Некоторые устаревшие методы, такие как componentWillMount, componentWillReceiveProps и componentWillUpdate, были помечены как deprecated.

**54. What is Concurrent Mode in React, and how does it improve rendering performance?**

**Concurrent Mode** (now referred to as Concurrent Features in React 18) is a set of capabilities that allow React to interrupt, pause, resume, and prioritize rendering work.

Instead of rendering the entire update synchronously, React can break rendering into smaller chunks and work on high-priority updates first (like user input), while delaying less important updates. This makes the UI more responsive.

It improves performance by enabling interruptible rendering, automatic batching of updates, transitions (startTransition), and better handling of asynchronous rendering without blocking the main thread.

**Concurrent Mode** does not make rendering faster in terms of raw speed — it makes the application feel faster and more responsive.

**Concurrent Mode** (в React 18 — Concurrent Features) — это набор возможностей, позволяющих React прерывать, приостанавливать, возобновлять и приоритизировать процесс рендеринга.

Вместо синхронного выполнения всего обновления React может разбивать работу на части и сначала обрабатывать высокоприоритетные задачи (например, ввод пользователя), откладывая менее важные. Это делает интерфейс более отзывчивым.

Производительность улучшается за счёт прерываемого рендеринга, автоматического батчинга обновлений, использования transitions (startTransition) и лучшей работы с асинхронным рендерингом без блокировки основного потока.

**Concurrent Mode** не делает рендеринг быстрее по абсолютной скорости — он делает приложение более плавным и отзывчивым для пользователя.

**55. How does React handle concurrent rendering with multiple updates and prioritize them?**

**React handles concurrent** rendering using its Fiber architecture and a priority-based scheduling system.

When multiple updates occur, React assigns them different priority levels (called lanes). High-priority updates  
(like user input or urgent UI feedback) are processed first, while low-priority updates  
(like background data loading or transitions) can be paused and resumed later.

React can interrupt rendering work before it finishes, switch to a higher-priority update, and then continue the previous work.  
This makes rendering non-blocking and keeps the UI responsive.

Features like automatic batching and startTransition help mark updates as low priority, allowing React to manage scheduling more efficiently.

**React обрабатывает конкурентный рендеринг** с помощью архитектуры Fiber и системы планирования с приоритетами.

Когда происходит несколько обновлений, React присваивает им разные уровни приоритета (lanes).  
Высокоприоритетные обновления (например, ввод пользователя или срочный UI-ответ) обрабатываются первыми, а низкоприоритетные  
(например, фоновая загрузка данных или transition) могут быть приостановлены и продолжены позже.

React может прервать незавершённый рендер, переключиться на более важное обновление, а затем вернуться к предыдущей работе.  
Это делает рендеринг неблокирующим и сохраняет отзывчивость интерфейса.

Такие возможности, как автоматический batching и startTransition, позволяют помечать обновления как низкоприоритетные, что помогает React эффективнее управлять планированием.

**56. How would you handle long-running tasks or expensive computations in React applications without blocking the UI?**

You can avoid blocking the UI by moving expensive work off the main render path and scheduling it with lower priority.

**Common approaches:**

- Memoize expensive calculations with useMemo (and stable dependencies) so they don’t run every render.

- Defer non-urgent updates with startTransition / useTransition so user input stays responsive.

- Split work into smaller chunks (e.g., process in batches) and yield to the browser using setTimeout(0), requestIdleCallback, or scheduler-style chunking.

- Offload heavy computations to a Web Worker so the main thread stays free.

- Virtualize large lists (react-window / react-virtualized) to render only visible items.

- Debounce/throttle high-frequency events (typing, scroll) so you compute less often.

- Do heavy data processing outside render (e.g., in effects) and store results, instead of computing during render.

- Use code splitting / lazy loading so large modules load only when needed.

These techniques keep rendering fast and prevent long synchronous JavaScript from freezing the UI.

Чтобы не блокировать UI, нужно уводить тяжёлую работу из синхронного рендера и выполнять её с более низким приоритетом или вне главного потока.

**Частые подходы:**

- Мемоизировать тяжёлые вычисления через useMemo (с корректными зависимостями), чтобы они не выполнялись при каждом рендере.

- Откладывать несрочные обновления через startTransition / useTransition, чтобы ввод пользователя оставался отзывчивым.

- Разбивать работу на чанки (обработка батчами) и “уступать” браузеру через setTimeout(0), requestIdleCallback или похожий подход.

- Переносить тяжёлые вычисления в Web Worker, чтобы не грузить main thread.

- Виртуализировать большие списки (react-window / react-virtualized), рендеря только видимую часть.

- Debounce/throttle для частых событий (ввод, скролл), чтобы реже считать.

- Делать тяжёлую обработку данных вне рендера (например, в useEffect) и сохранять результат, а не вычислять в render.

- Использовать code splitting / lazy loading, чтобы большие части кода загружались только при необходимости.

Так UI остаётся плавным, а длинный синхронный JS не “замораживает” интерфейс.

**57. Explain server-side rendering of React applications and its benefits**

**Server-side rendering (SSR)** in React means that the HTML for a page is generated on the server and sent to the browser, instead of rendering everything first on the client. After the HTML is delivered, React hydrates it on the client to make the page interactive.

Instead of sending an empty HTML file and rendering via JavaScript, SSR sends fully formed markup, which improves the initial user experience.

**Benefits:**

- Faster initial page load (better First Contentful Paint).

- Better SEO, since search engines can crawl fully rendered HTML.

- Improved performance on slow devices or networks.

- Better perceived performance for users.

SSR is commonly implemented using frameworks like Next.js.

**Server-side rendering (SSR)** в React — это процесс, при котором HTML страницы генерируется на сервере и отправляется в браузер, вместо первоначального рендеринга полностью на клиенте. После загрузки HTML React выполняет гидратацию, делая страницу интерактивной.

Вместо отправки пустого HTML и последующего рендера через JavaScript, SSR отправляет уже готовую разметку, что улучшает пользовательский опыт.

**Преимущества:**

- Более быстрая первая загрузка страницы (лучший First Contentful Paint).

- Улучшенная SEO-оптимизация, так как поисковые системы получают готовый HTML.

- Лучшая производительность на слабых устройствах или медленном интернете.

- Улучшенное субъективное восприятие скорости.

SSR часто реализуется с помощью фреймворков, таких как Next.js.

**58. Explain static generation of React applications**
**Static generation (Static Site Generation, SSG)** means that HTML pages are generated at build time, not on every request. The generated files are served as static assets from a CDN or server.

Unlike SSR, which renders pages on each request, static generation creates pages once during the build process. The pages are then instantly delivered to users.

**Benefits:**

- Very fast load times.

- Excellent performance through CDN caching.

- Better scalability (no server rendering on each request).

- Good SEO because HTML is pre-rendered.

Static generation is commonly used for blogs, marketing sites, and documentation where content does not change frequently. It is supported by frameworks like Next.js.

**Static generation (SSG)** — это процесс, при котором HTML-страницы генерируются на этапе сборки (build time), а не при каждом запросе пользователя. Сгенерированные файлы отдаются как статические ресурсы с сервера или CDN.

В отличие от SSR, который рендерит страницу при каждом запросе, SSG создаёт страницы один раз во время сборки и затем мгновенно доставляет их пользователям.

Преимущества:

- Очень быстрая загрузка.

- Отличная производительность благодаря кешированию через CDN.

- Хорошая масштабируемость (нет серверного рендеринга на каждый запрос).

- Хорошая SEO-оптимизация благодаря предварительно сгенерированному HTML.

Static generation часто используется для блогов, лендингов и документации, где контент меняется редко. Поддерживается такими фреймворками, как Next.js.

**59. What are higher-order components in React?**
**Higher-order components (HOCs)** are functions that take a component as an argument and return a new enhanced component.

They are used to reuse component logic, such as authentication checks, data fetching, logging, or conditional rendering. A HOC does not modify the original component but wraps it and adds additional behavior.

HOCs follow the pattern:
const EnhancedComponent = withSomething(WrappedComponent);

They were commonly used before React Hooks and are still used in some libraries.

**Higher-order components (HOC)** — это функции, которые принимают компонент в качестве аргумента и возвращают новый расширенный компонент.

Они используются для повторного использования логики компонентов, например для проверки авторизации, загрузки данных, логирования или условного рендеринга. HOC не изменяет исходный компонент, а оборачивает его и добавляет дополнительное поведение.

Обычно используются по шаблону:
const EnhancedComponent = withSomething(WrappedComponent);

HOC широко применялись до появления React Hooks и до сих пор используются в некоторых библиотеках.

**60. Explain the presentational vs container component pattern in React**
The presentational vs container component pattern is a design pattern that separates UI rendering from business logic.

Presentational components are responsible only for displaying UI. They receive data via props and usually do not manage complex state or side effects. They focus on how things look.

Container components handle logic, data fetching, state management, and pass data and callbacks to presentational components. They focus on how things work.

This separation improves code readability, reusability, testability, and maintainability. With the introduction of React Hooks, this pattern is often implemented using custom hooks instead of separate container components.

Паттерн presentational vs container — это подход, который разделяет отображение интерфейса и бизнес-логику.

Presentational компоненты отвечают только за отображение UI. Они получают данные через props и обычно не управляют сложным состоянием или побочными эффектами. Их задача — как выглядит интерфейс.

Container компоненты управляют логикой, загрузкой данных и состоянием, а затем передают данные и колбэки в presentational компоненты. Их задача — как работает приложение.

Такое разделение улучшает читаемость, переиспользуемость, тестируемость и поддержку кода. С появлением React Hooks этот паттерн часто реализуется через пользовательские хуки вместо отдельных container-компонентов.

**61. What are render props in React?**
**Render props** is a pattern in React where a component receives a function as a prop and calls that function to determine what to render.

Instead of passing JSX directly, you pass a function that returns JSX. This allows sharing reusable logic while giving full control over the UI rendering.

Example pattern:

```
<Component render={(data) => <UI data={data} />} />
```

**Render props** were commonly used to share logic before React Hooks became popular.

**Render props** — это паттерн в React, при котором компонент получает функцию в качестве props и вызывает её для определения того, что нужно отрисовать.

Вместо передачи готового JSX передаётся функция, которая возвращает JSX. Это позволяет переиспользовать логику и при этом сохранять гибкость в отображении интерфейса.

**Render props** широко использовались для повторного использования логики до появления React Hooks.

**62. Explain the composition pattern in React.**
The **composition pattern** in React means building complex components by combining smaller, reusable components instead of using inheritance.

React encourages **composition** through props and children. A component can accept other components as children or props and render them inside its layout.

Example patterns:

Using props.children to nest components.

Passing components as props (e.g., header, footer, render functions).

**Composition** makes components flexible, reusable, and easier to maintain. It follows the principle: **“composition** over inheritance.”

```
function WelcomeDialog() {
  return (
    <Dialog>
      <h1>Welcome</h1>
      <p>Thank you for visiting our spacecraft!</p>
    </Dialog>
  );
}

function Dialog(props) {
  return <div className="dialog">{props.children}</div>;
}
```

Паттерн композиции в React означает построение сложных компонентов путём объединения более мелких и переиспользуемых компонентов вместо использования наследования.

React поощряет композицию через props и children. Компонент может принимать другие компоненты как children или через props и отображать их внутри своей разметки.

Примеры:

Использование props.children для вложенных компонентов.

Передача компонентов через props (например, header, footer, render-функции).

Композиция делает компоненты гибкими, переиспользуемыми и более простыми в поддержке. Основной принцип — «композиция вместо наследования».

**63. How do you re-render the view when the browser is resized?**

To re-render the view when the browser is resized, you need to listen to the window resize event and update component state. When state changes, React re-renders the component.

In functional components, this is typically done using useEffect to add a resize event listener and useState to store the window size. The listener updates the state whenever the window size changes.

It is important to clean up the event listener in the cleanup function of useEffect to prevent memory leaks.

Alternatively, you can use a custom hook (e.g., useWindowSize) or libraries like react-use.

```
import React, { useState, useEffect } from 'react';

function ResizeComponent() {
  const [windowWidth, setWindowWidth] = useState(window.innerWidth);

  useEffect(() => {
    const handleResize = () => setWindowWidth(window.innerWidth);
    window.addEventListener('resize', handleResize);
    return () => window.removeEventListener('resize', handleResize);
  }, []);

  return <div>Window width: {windowWidth}px</div>;
}

export default ResizeComponent;
```

Чтобы перерендерить компонент при изменении размера окна браузера, нужно подписаться на событие resize и обновлять состояние компонента. При изменении state React автоматически выполняет повторный рендер.

В функциональных компонентах это обычно реализуется через useEffect (для добавления обработчика resize) и useState (для хранения размеров окна). Обработчик обновляет состояние при каждом изменении размера.

Важно удалять обработчик события в функции очистки useEffect, чтобы избежать утечек памяти.

Также можно использовать пользовательский хук (например, useWindowSize) или готовые библиотеки, такие как react-use.

**64. How do you handle asynchronous data loading in React applications?**
Asynchronous data loading in React is typically handled using useEffect for side effects and useState to store loading, data, and error states.

The common pattern:

- Set loading to true.

- Fetch data inside useEffect.

- Store the result in state.

- Handle errors.

- Set loading to false.

You should also handle cleanup (e.g., aborting fetch requests) to prevent memory leaks when a component unmounts.

For more complex scenarios, libraries like React Query, SWR, or Redux Toolkit Query are often used. They provide caching, background updates, deduplication, and better server-state management.

```
import React, { useState, useEffect } from 'react';

const FetchAndDisplayData = () => {
  const [info, updateInfo] = useState(null);
  const [isLoading, toggleLoading] = useState(true);

  useEffect(() => {
    const retrieveData = async () => {
      try {
        const res = await fetch('https://api.example.com/data');
        const data = await res.json();
        updateInfo(data);
      } catch (err) {
        console.error('Error fetching data:', err);
      } finally {
        toggleLoading(false);
      }
    };

    retrieveData();
  }, []);

  return (
    <div>
      {isLoading ? (
        <p>Fetching data, please wait...</p>
      ) : (
        <pre>{JSON.stringify(info, null, 2)}</pre>
      )}
    </div>
  );
};

export default FetchAndDisplayData;
```

Асинхронная загрузка данных в React обычно реализуется с помощью useEffect для побочных эффектов и useState для хранения состояний загрузки, данных и ошибки.

Типичный подход:

- Установить loading в true.

- Выполнить запрос внутри useEffect.

- Сохранить результат в state.

- Обработать возможные ошибки.

- Установить loading в false.

Также важно реализовать очистку (например, отмену fetch-запроса), чтобы избежать утечек памяти при размонтировании компонента.

В более сложных случаях используют библиотеки, такие как React Query, SWR или Redux Toolkit Query, которые обеспечивают кеширование, фоновые обновления, устранение дублирования запросов и более удобное управление серверным состоянием.

**65. What are some common pitfalls when doing data fetching in React?**
Some common pitfalls when doing data fetching in React include:

- Missing dependencies in useEffect, which can cause stale data or infinite loops.

- Not handling loading and error states properly.

- Updating state after a component has unmounted (causing memory leaks or warnings).

- Race conditions when multiple requests are triggered and older responses override newer ones.

- Fetching data inside render instead of inside useEffect.

- Over-fetching due to unnecessary rerenders.

- Not aborting fetch requests when components unmount.

- Storing server data in multiple places instead of using a proper caching strategy.

To avoid these issues, use proper dependency management, cleanup functions (AbortController), and consider using data-fetching libraries like React Query or SWR for complex scenarios.

Некоторые распространённые ошибки при загрузке данных в React:

- Отсутствие зависимостей в useEffect, что может привести к устаревшим данным или бесконечным циклам.

- Неправильная обработка состояний загрузки и ошибки.

- Обновление state после размонтирования компонента (утечки памяти и предупреждения).

- Состояния гонки (race conditions), когда старый ответ запроса перезаписывает новый.

- Выполнение запроса внутри render вместо useEffect.

- Лишние запросы из-за ненужных перерендеров.

- Отсутствие отмены запроса при размонтировании компонента.

- Хранение серверных данных в нескольких местах без стратегии кеширования.

Чтобы избежать этих проблем, нужно правильно управлять зависимостями, использовать очистку (AbortController) и при сложной логике применять библиотеки вроде React Query или SWR.

**66. What is a React Router?**

**React Router** is a library for handling routing in React applications.  
It enables navigation between different components or pages without reloading the entire page, using client-side routing.

Instead of requesting a new page from the server, React Router updates the URL and renders the corresponding component based on the defined routes.

It provides features like dynamic routing, nested routes, route parameters, navigation hooks, and protected routes.

**React Router** — это библиотека для организации маршрутизации в приложениях React.  
Она позволяет переходить между разными компонентами или страницами без полной перезагрузки страницы, используя клиентскую маршрутизацию.

Вместо запроса новой страницы с сервера React Router изменяет URL и отображает соответствующий компонент на основе настроенных маршрутов.

Библиотека поддерживает динамические маршруты, вложенные маршруты, параметры URL, хуки для навигации и защищённые маршруты.

**67. How does React Router work, and how do you implement dynamic routing?**

React Router works by listening to URL changes (using the History API) and matching the current path to a route configuration.  
When the path matches a route, React Router renders the corresponding component without reloading the page.

To implement dynamic routing, you define route parameters in the path using a colon, like /users/:id.  
React Router then parses the URL and provides the parameter values to the component (e.g., via useParams).  
This lets you render different content based on the URL.

```
import { BrowserRouter, Routes, Route, useParams } from 'react-router-dom';

function UserPage() {
  const { id } = useParams(); // Access dynamic parameter
  return <h1>User ID: {id}</h1>;
}

export default function App() {
  return (
    <BrowserRouter>
      <Routes>
        <Route path="/user/:id" element={<UserPage />} /> {/* Dynamic path */}
      </Routes>
    </BrowserRouter>
  );
}
```

React Router работает, слушая изменения URL (через History API) и сопоставляя текущий путь с конфигурацией маршрутов.  
Когда путь совпадает с маршрутом, React Router рендерит соответствующий компонент без перезагрузки страницы.

Чтобы реализовать динамическую маршрутизацию, задают параметры маршрута через двоеточие, например /users/:id.  
Затем React Router извлекает параметры из URL и передаёт их компоненту (например, через useParams).  
Это позволяет показывать разный контент в зависимости от URL. 68. How do you handle nested routes and route parameters in React Router?

**68. How do you handle nested routes and route parameters in React Router?**

Nested routes in React Router are handled by defining child routes inside a parent route.  
The parent component renders an <Outlet />, which acts as a placeholder where the matched child route will be rendered.

Route parameters are defined using a colon (e.g., /users/:id).  
Inside the component, you can access these parameters using the useParams hook.

You can combine both by defining nested routes with parameters, such as /users/:id/posts/:postId, and then access both id and postId using useParams.

```
import {
  BrowserRouter,
  Routes,
  Route,
  Outlet,
  useParams,
} from 'react-router-dom';

function UserProfile() {
  const { userId } = useParams();
  return <h2>User ID: {userId}</h2>;
}

function App() {
  return (
    <BrowserRouter>
      <Routes>
        <Route path="user/:userId" element={<Outlet />}>
          <Route path="profile" element={<UserProfile />} />
        </Route>
      </Routes>
    </BrowserRouter>
  );
}
```

Вложенные маршруты (nested routes) в React Router настраиваются через определение дочерних маршрутов внутри родительского маршрута.
Родительский компонент должен содержать <Outlet />, который служит местом для отображения совпавшего дочернего маршрута.

Параметры маршрута задаются через двоеточие (например, /users/:id).
Внутри компонента их можно получить с помощью хука useParams.

Можно комбинировать вложенные маршруты и параметры, например /users/:id/posts/:postId, и получать оба параметра (id и postId) через useParams.

**69. What is the difference between BrowserRouter and HashRouter?**

BrowserRouter uses the HTML5 History API to manage navigation and keeps clean URLs like /about.
It requires proper server configuration to handle client-side routes, otherwise refreshing the page may result in a 404 error.

HashRouter uses the URL hash (#) to manage routing, like /#/about.
The part after # is not sent to the server, so it does not require special server configuration.
However, URLs look less clean and are not ideal for SEO.

In modern applications, BrowserRouter is preferred when server configuration is available, while HashRouter is useful for static hosting without server control.

BrowserRouter использует HTML5 History API для управления навигацией и создаёт «чистые» URL, например /about.
Он требует правильной настройки сервера для обработки клиентских маршрутов, иначе при обновлении страницы может возникнуть ошибка 404.

HashRouter использует хеш в URL (#), например /#/about. Часть после # не отправляется на сервер, поэтому дополнительная настройка сервера не требуется.
Однако такие URL выглядят менее аккуратно и хуже подходят для SEO.

В современных приложениях чаще используют BrowserRouter при наличии настройки сервера, а HashRouter подходит для статического хостинга без доступа к конфигурации сервера.

**70. How React Router is different from the history library?**

React Router is a routing library that provides declarative navigation and route-based component rendering in React applications.
It defines routes, matches URLs, renders components, and provides hooks like useParams and useNavigate.

The history library is a lower-level utility that manages session history using the browser’s History API.
It handles pushing, replacing, and listening to URL changes but does not render components or manage route matching.

In simple terms, React Router uses the history library internally to manage navigation, while also adding routing logic and integration with React.

React Router — это библиотека маршрутизации, которая предоставляет декларативную навигацию и рендеринг компонентов на основе маршрутов в приложениях React.
Она определяет маршруты, сопоставляет URL, рендерит компоненты и предоставляет хуки, такие как useParams и useNavigate.

Библиотека history — это более низкоуровневый инструмент для управления историей браузера через History API.
Она позволяет изменять URL (push, replace) и отслеживать изменения, но не занимается рендерингом компонентов или сопоставлением маршрутов.

Проще говоря, React Router использует history внутри себя для управления навигацией, добавляя поверх этого логику маршрутизации и интеграцию с React.

**71. What are the main router components and router creation APIs used with React 19?**
With React 19, routing is typically handled using the modern React Router (Data Router architecture).

Main router creation APIs:

- createBrowserRouter — uses the HTML5 History API for standard web applications.

- createHashRouter — uses hash-based URLs.

- createMemoryRouter — keeps navigation history in memory (testing, React Native).

- createStaticRouter — used for server-side rendering (SSR).

Core router component:

- RouterProvider — provides the routing context to the application and receives the router instance created by one of the create\*Router functions.

Traditional wrapper components (still supported):

- BrowserRouter

- HashRouter

- MemoryRouter

- StaticRouter

In modern applications, the recommended approach is using create\*Router together with RouterProvider.

С React 19 маршрутизация обычно реализуется с использованием современной архитектуры React Router (Data Router).

Основные API создания роутеров:

- createBrowserRouter — использует HTML5 History API для веб-приложений.

- createHashRouter — использует hash-маршрутизацию.

- createMemoryRouter — хранит историю в памяти (тестирование, React Native).

- createStaticRouter — используется для серверного рендеринга (SSR).

Основной компонент маршрутизации:

- RouterProvider — предоставляет routing-контекст приложению и принимает экземпляр роутера, созданный через create\*Router.

Традиционные обёртки (по-прежнему поддерживаются):

- BrowserRouter

- HashRouter

- MemoryRouter

- StaticRouter

В современных приложениях рекомендуется использовать create\*Router вместе с RouterProvider.

**72. What is the purpose of the push and replace methods of history?**
The push method adds a new entry to the browser’s history stack.  
It navigates to a new URL and allows the user to go back to the previous page using the back button.

The replace method replaces the current entry in the history stack instead of adding a new one.  
After replace, the user cannot go back to the previous URL using the back button because it was overwritten.

**push is used when you want normal navigation behavior.**
**replace is used when you want to redirect without keeping the previous route in history **(for example, after login).

Метод push добавляет новую запись в стек истории браузера.  
Он выполняет переход на новый URL и позволяет пользователю вернуться назад через кнопку «Назад».

Метод replace заменяет текущую запись в истории вместо добавления новой.  
После replace пользователь не сможет вернуться к предыдущему URL, так как он был перезаписан.

**push используется для обычной навигации.**
**replace используется для редиректа без сохранения предыдущего маршрута в истории** (например, после авторизации).

**73. How do you navigate programmatically in React Router?**
In modern React Router, programmatic navigation is done using the useNavigate hook.

The useNavigate hook returns a navigate function that allows you to change routes inside event handlers or logic (e.g., after form submission).

Example:

```const navigate = useNavigate();
navigate("/dashboard"); // similar to push
navigate("/login", { replace: true }); // similar to replace

You can also navigate backward or forward using:
navigate(-1); // go back
navigate(1); // go forward
```

In older versions, this was done using history.push or history.replace.

В современном React Router программная навигация выполняется с помощью хука useNavigate.

Хук useNavigate возвращает функцию navigate, которую можно вызывать внутри обработчиков событий или логики (например, после отправки формы).

В старых версиях это делалось через history.push или history.replace.

**74. How would you implement route guards or private routes in React?**

Route guards (private routes) are implemented by checking authentication (or permissions) before rendering a protected route. If the user is not allowed, you redirect them (or render a fallback).

In React Router, the common approach is to create a wrapper component like RequireAuth:

If authenticated → render <Outlet /> (nested protected routes) or the protected component.

If not authenticated → return <Navigate to="/login" replace />.

You can also store the original location and redirect back after login.

Route guards can be extended for roles/permissions (e.g., admin-only routes) by checking user roles before allowing access.

Route guards (private routes) в React реализуются через проверку авторизации (или прав) перед рендером защищённого маршрута. Если доступа нет — делается редирект (или показывается заглушка).

```
import { Navigate } from 'react-router-dom';

function PrivateRoute({ children }) {
  return isAuthenticated ? children : <Navigate to="/login" />;
}
```

В React Router обычно делают обёртку-компонент типа RequireAuth:

Если пользователь авторизован → рендерим <Outlet /> (вложенные защищённые маршруты) или нужный компонент.

Если не авторизован → возвращаем <Navigate to="/login" replace />.

Также часто сохраняют текущий route (location), чтобы после логина вернуть пользователя обратно.

Проверку можно расширять на роли/права (например, маршруты только для админа), добавляя проверку ролей перед выдачей доступа.

**75. How do you manage the active route state in a multi-page React application?**
In React Router, you usually don’t store “active route” in your own state — you derive it from the router.

Common ways:

NavLink: it automatically applies an “active” state/class when its route matches the current URL.

useLocation: gives the current location (pathname, search, hash), so you can compute which menu item is active.

useMatch / matchPath: check if a specific path matches the current URL (useful for custom matching).

useParams: for active state based on route parameters (e.g., highlighting a user page).

For complex navigation (nested menus), you typically compute active items from pathname and params rather than duplicating route state.

```
import { useLocation } from 'react-router-dom';

function NavBar() {
  const location = useLocation();
  return (
    <nav>
      <ul>
        <li className={location.pathname === '/home' ? 'active' : ''}>Home</li>
        <li className={location.pathname === '/about' ? 'active' : ''}>
          About
        </li>
      </ul>
    </nav>
  );
}
```

В React Router обычно не хранят “активный маршрут” в собственном state — его получают из роутера.

Типичные способы:

NavLink: автоматически добавляет “active” состояние/класс, когда маршрут совпадает с текущим URL.

useLocation: даёт текущий location (pathname, search, hash), и по нему можно вычислять активный пункт меню.

useMatch / matchPath: проверяет совпадение конкретного пути с текущим URL (для кастомной логики).

useParams: когда активность зависит от параметров маршрута (например, подсветка страницы пользователя).

Для сложной навигации (вложенные меню) обычно вычисляют активные пункты из pathname и params, а не дублируют состояние маршрута в своём state.

**76. How do you handle 404 errors or page not found in React Router?**
In React Router, 404 is handled by defining a fallback route that matches unmatched paths.

In v6, you use path="\*" to render a NotFound component when no other route matches.

You can also redirect users using <Navigate /> if needed.

For nested routes, you define a wildcard route inside the layout to handle unknown child paths.

In React Router обработка 404 делается через fallback-маршрут, который перехватывает все несовпавшие пути.

```
import { Routes, Route } from 'react-router-dom';

function NotFound() {
  return <h1>404 - Page Not Found</h1>;
}

function App() {
  return (
    <Routes>
      <Route path="/" element={<Home />} />
      <Route path="/about" element={<About />} />
      <Route path="*" element={<NotFound />} />
    </Routes>
  );
}
```

В версии v6 используют path="\*", чтобы отобразить компонент NotFound, если ни один маршрут не совпал.

При необходимости можно сделать редирект через <Navigate />.

Для вложенных маршрутов добавляют wildcard-маршрут внутри layout, чтобы обрабатывать неизвестные дочерние пути.

**77. How to get query parameters in React Router?**

In React Router v6, query parameters are accessed using the useSearchParams hook.

It returns a URLSearchParams object and a setter function.

You can get a value with searchParams.get("key") and update it with setSearchParams().

Alternatively, you can use useLocation and manually parse location.search.

```
import { useSearchParams } from 'react-router-dom';

function MyComponent() {
  const [searchParams] = useSearchParams();
  const queryParam = searchParams.get('paramName');
  return <div>Query Param: {queryParam}</div>;
}
```

В React Router v6 query-параметры получают через хук useSearchParams.

Он возвращает объект URLSearchParams и функцию для обновления параметров.

Значение получают через searchParams.get("key"), а изменяют через setSearchParams().

Также можно использовать useLocation и вручную разобрать location.search.

**78. How do you perform an automatic redirect after login in React Router?**

After login, you typically redirect using the useNavigate hook in React Router v6.

Once authentication succeeds, you call navigate("/dashboard") or another protected route.

If the user was redirected to login from a protected page, you can store the intended location in state and navigate back after login.

For protected routes, you can also conditionally render <Navigate to="/login" /> when the user is not authenticated.

```
import { useNavigate } from 'react-router-dom';

function Login() {
  const navigate = useNavigate();

  const handleLogin = () => {
    // Perform login logic
    navigate('/dashboard');
  };

  return (
    <div>
      <button onClick={handleLogin}>Login</button>
    </div>
  );
}
```

После логина обычно делают редирект через хук useNavigate в React Router v6.

После успешной аутентификации вызывают navigate("/dashboard") или другой защищённый маршрут.

Если пользователь был перенаправлен на login с защищённой страницы, можно сохранить исходный путь в state и вернуть его после входа.

Для защищённых маршрутов также можно условно рендерить <Navigate to="/login" />, если пользователь не авторизован. 79. How do you pass props to a route component in React Router?

**79. How do you pass props to a route component in React Router?**

In React Router v6, you pass props to a route component using the element prop.

Instead of component, you render JSX: <Route path="/profile" element={<Profile user={user} />} />.

You can also pass data via context, URL params, or state in navigation.

For navigation state, use navigate("/path", { state: data }) and access it via useLocation().

В React Router v6 пропсы передают через свойство element.

Вместо component рендерят JSX: <Route path="/profile" element={<Profile user={user} />} />.

Также можно передавать данные через context, параметры URL или state при навигации.

Для передачи через navigation state используют navigate("/path", { state: data }) и получают данные через useLocation().

**80. How do you localize React applications?**
React apps are usually localized using an i18n library like react-i18next or FormatJS.

You store translations in JSON files and organize them by language and namespace.

The language can be detected automatically (browser settings) or selected manually and stored in localStorage.

Text is rendered using translation hooks like useTranslation and keys instead of hardcoded strings.

For dates, numbers, and currency, you use the Intl API or formatting utilities from the i18n library.

```
// Example using react-i18next
import { useTranslation } from 'react-i18next';

const MyComponent = () => {
  const { t } = useTranslation();
  return <p>{t('welcome_message')}</p>;
};
```

React-приложения обычно локализуют с помощью i18n-библиотек, например react-i18next или FormatJS.

Переводы хранятся в JSON-файлах и разделяются по языкам и неймспейсам.

Язык можно определять автоматически (по браузеру) или выбирать вручную и сохранять в localStorage.

Текст выводится через хуки перевода, например useTranslation, используя ключи вместо жёстко прописанных строк.

Для форматирования дат, чисел и валют используют Intl API или утилиты библиотеки локализации.

**81. What is react-intl?**

React Intl is a library for internationalization in React applications, part of the FormatJS ecosystem.

It provides components and APIs to format messages, dates, numbers, currencies, and pluralization according to locale.

Translations are defined as message descriptors and rendered using components like FormattedMessage or hooks like useIntl.

It relies on the JavaScript Intl API under the hood.

React Intl — это библиотека для интернационализации React-приложений, часть экосистемы FormatJS.

Она предоставляет компоненты и API для форматирования сообщений, дат, чисел, валют и множественных форм в зависимости от локали.

Переводы задаются как message descriptors и выводятся через компоненты FormattedMessage или хук useIntl.

Внутри библиотека использует JavaScript Intl API.

**82. What are the main features of react-intl?**

Main features of react-intl include message translation, date and time formatting, number and currency formatting, and pluralization support.

It provides components like FormattedMessage, FormattedDate, and FormattedNumber.

It also offers the useIntl hook for programmatic formatting.

It supports dynamic locale switching and is based on the native Intl API.

Основные возможности react-intl включают перевод сообщений, форматирование даты и времени, чисел и валют, а также поддержку множественных форм.

Библиотека предоставляет компоненты FormattedMessage, FormattedDate и FormattedNumber.

Также есть хук useIntl для программного форматирования.

Поддерживается динамическая смена языка, а внутри используется нативный Intl API.

**83. What are the two ways of formatting in react-intl?**

In react-intl, there are two main ways of formatting: declarative and imperative.

Declarative formatting uses React components like FormattedMessage, FormattedDate, and FormattedNumber directly in JSX.

Imperative formatting uses the useIntl hook (or injectIntl) to access formatting methods like intl.formatMessage() inside JavaScript logic.

В react-intl есть два основных способа форматирования: декларативный и императивный.

Декларативный способ использует React-компоненты, такие как FormattedMessage, FormattedDate и FormattedNumber, прямо в JSX.

Императивный способ использует хук useIntl (или injectIntl), чтобы вызывать методы форматирования, например intl.formatMessage(), внутри логики JavaScript.

**84. How to use FormattedMessage as a placeholder using react-intl?**
To use FormattedMessage as a placeholder, you can’t pass it directly as a string because placeholder expects plain text.

Instead, use the useIntl hook and call intl.formatMessage() to get the translated string.

Then pass that string to the placeholder prop:
placeholder={intl.formatMessage({ id: "input.placeholder" })}.

```
import { FormattedMessage } from 'react-intl';

function WelcomeMessage() {
  return (
    <FormattedMessage
      id="welcome"
      defaultMessage="Hello, {name}!"
      values={{ name: 'John' }}
    />
  );
}
```

Чтобы использовать FormattedMessage как placeholder, его нельзя передать напрямую, потому что placeholder принимает строку.

Вместо этого используют хук useIntl и вызывают intl.formatMessage(), чтобы получить переведённую строку.

Затем передают её в prop placeholder:
placeholder={intl.formatMessage({ id: "input.placeholder" })}.

**85. How to access the current locale with React Intl?**
You can access the current locale using the useIntl hook.

Call const intl = useIntl(), then read intl.locale to get the active locale.

In class components, you can use injectIntl and access locale from props.intl.locale.

Текущую локаль можно получить через хук useIntl.

Нужно вызвать const intl = useIntl(), затем использовать intl.locale для получения активной локали.

В классовых компонентах используют injectIntl и получают locale из props.intl.locale.

**86. How to format date using react-intl?**

In react-intl, you can format a date declaratively using the FormattedDate component in JSX.

Example: <FormattedDate value={date} year="numeric" month="long" day="2-digit" />.

You can also format a date imperatively using the useIntl hook and calling intl.formatDate(date, options).

В react-intl дату можно форматировать декларативно с помощью компонента FormattedDate в JSX.

```
import { useIntl } from 'react-intl';

function DateComponent() {
  const intl = useIntl();
  const formattedDate = intl.formatDate(new Date(), {
    year: 'numeric',
    month: 'long',
    day: '2-digit',
  });
  return <div>{formattedDate}</div>;
}
```

Также можно форматировать дату императивно через хук useIntl, вызывая intl.formatDate(date, options).
