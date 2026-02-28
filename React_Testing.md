## React Testштп

**1. How do you test React applications?**
React apps are typically tested with a mix of unit, integration, and end-to-end tests.

Common stack: Jest or Vitest as the test runner, React Testing Library for component tests focused on user behavior, and Cypress or Playwright for E2E.

You often mock network requests with MSW, and test hooks/utilities separately.

Avoid testing implementation details; prefer testing what the user sees and does (rendering, interactions, routing).

React-приложения обычно тестируют сочетанием unit, integration и end-to-end тестов.

Частый стек: Jest или Vitest как раннер, React Testing Library для тестов компонентов через поведение пользователя, и Cypress или Playwright для E2E.

Сетевые запросы часто мокают через MSW, а хуки/утилиты тестируют отдельно.

Лучше не тестировать внутреннюю реализацию, а проверять то, что видит и делает пользователь (рендер, клики, навигация).

**2. What is Jest and how is it used for testing React applications?**

Jest is a JavaScript testing framework developed by Facebook, commonly used for testing React applications.

It provides a test runner, assertion library, mocking capabilities, and snapshot testing out of the box.

In React apps, Jest is usually combined with React Testing Library to test components and user interactions.

It can mock modules, functions, and API calls, and integrates well with Babel and TypeScript.

Jest — это JavaScript-фреймворк для тестирования, разработанный Facebook и широко используемый для React-приложений.

Он включает в себя тест-раннер, библиотеку утверждений, инструменты для моков и snapshot-тестирование.

В React-проектах Jest обычно используют вместе с React Testing Library для тестирования компонентов и пользовательских сценариев.

Он позволяет мокать модули, функции и API-запросы и хорошо интегрируется с Babel и TypeScript.

**89. What is React Testing Library and how is it used for testing React components?**

React Testing Library is a library for testing React components by focusing on user behavior rather than implementation details.

It encourages testing what the user sees and interacts with, such as text, buttons, and form inputs.

You render components using render(), then query elements with screen.getByText, getByRole, etc.

User interactions are simulated with userEvent, and assertions are made using Jest matchers.

React Testing Library — это библиотека для тестирования React-компонентов с акцентом на поведение пользователя, а не на внутреннюю реализацию.

Она предлагает тестировать то, что видит и с чем взаимодействует пользователь: текст, кнопки, формы.

Компонент рендерят через render(), затем ищут элементы с помощью screen.getByText, getByRole и других методов.

Действия пользователя имитируют через userEvent, а проверки выполняют с помощью матчеров Jest.

**90. How do you test React components using React Testing Library?**
To test React components with React Testing Library, you first render the component using render().

Then you query elements using screen.getByText, getByRole, getByLabelText, etc., based on how users access them.

You simulate user interactions with userEvent (click, type, submit).

Finally, you assert expected behavior using Jest matchers like expect(...).toBeInTheDocument().

```
import { render, screen, fireEvent } from '@testing-library/react';
import MyComponent from './MyComponent';

test('renders component', () => {
  render(<MyComponent />);
  const button = screen.getByRole('button');
  fireEvent.click(button);
  expect(screen.getByText('Clicked!')).toBeInTheDocument();
});
```

Чтобы тестировать React-компоненты с помощью React Testing Library, сначала рендерят компонент через render().

Затем находят элементы с помощью screen.getByText, getByRole, getByLabelText и других методов — так, как это делает пользователь.

Действия пользователя имитируют через userEvent (click, type, submit).

После этого проверяют ожидаемое поведение с помощью матчеров Jest, например expect(...).toBeInTheDocument().

**91. How do you test asynchronous code in React components?**
To test asynchronous code in React components, you use async/await with utilities like waitFor and findBy queries from React Testing Library.

findBy\* queries automatically wait for elements to appear.

waitFor is used to wait until a condition becomes true (for example, after a state update).

You usually mock API calls (e.g., with Jest or MSW) to control async behavior.

```
import { render, screen, waitFor } from '@testing-library/react';
import MyComponent from './MyComponent';

test('fetches data and renders it', async () => {
  render(<MyComponent />);
  await waitFor(() => {
    expect(screen.getByText('Data loaded')).toBeInTheDocument();
  });
});
```

Для тестирования асинхронного кода в React-компонентах используют async/await вместе с waitFor и findBy-запросами из React Testing Library.

Методы findBy\* автоматически ждут появления элемента.

waitFor применяют, чтобы дождаться выполнения условия (например, обновления состояния).

API-запросы обычно мокают (через Jest или MSW), чтобы контролировать асинхронное поведение.

**92. How do you mock API calls in React component tests?**
API calls in React tests are usually mocked to avoid real network requests and control responses.

You can mock fetch or axios using Jest with jest.fn() or jest.mock().

A more robust approach is using MSW (Mock Service Worker) to mock API endpoints at the network level.

This allows you to simulate success, error, and loading states in a predictable way.

```
import { render, screen } from '@testing-library/react';

jest.mock('./api', () => ({
  fetchData: jest.fn(() => Promise.resolve('mocked data')),
}));

import MyComponent from './MyComponent';

test('fetches data and renders it', async () => {
  render(<MyComponent />);
  expect(screen.getByText('Loading...')).toBeInTheDocument();
  expect(await screen.findByText('mocked data')).toBeInTheDocument();
});
```

В тестах React API-запросы обычно мокают, чтобы не выполнять реальные сетевые вызовы и контролировать ответы.

Можно замокать fetch или axios с помощью Jest через jest.fn() или jest.mock().

Более надёжный способ — использовать MSW (Mock Service Worker), который перехватывает запросы на уровне сети.

Это позволяет предсказуемо тестировать состояния успеха, ошибки и загрузки.

**93. How do you test React hooks in functional components?**
To test React hooks, you can use React Testing Library by rendering a component that uses the hook.

For isolated hook testing, you can use renderHook from @testing-library/react.

You trigger state updates or actions and then assert the updated result.

For async hooks, use waitFor to handle state changes.

```
import { renderHook, act } from '@testing-library/react-hooks';
import useCounter from './useCounter';

test('increments counter', () => {
  const { result } = renderHook(() => useCounter());
  act(() => {
    result.current.increment();
  });
  expect(result.current.count).toBe(1);
});
```

Для тестирования React-хуков можно использовать React Testing Library, отрендерив компонент, который использует этот хук.

Для изолированного тестирования применяют renderHook из @testing-library/react.

Затем вызывают действия или обновления состояния и проверяют результат.

Для асинхронных хуков используют waitFor, чтобы дождаться изменения состояния.

**94. How do you test custom hooks in React?**
Custom hooks are tested similarly to regular hooks using renderHook from @testing-library/react.

You call renderHook(() => useCustomHook()) to execute the hook in a test environment.

Then you interact with the returned values or functions and assert state changes using result.current.

For async logic, use waitFor, and mock external dependencies like API calls if needed.

```
import { renderHook, act } from '@testing-library/react-hooks';
import useCustomHook from './useCustomHook';

test('hook behavior', () => {
  const { result } = renderHook(() => useCustomHook());
  act(() => {
    result.current.doSomething();
  });
  expect(result.current.value).toBe('expected value');
});
```

Кастомные хуки тестируются так же, как и обычные, с помощью renderHook из @testing-library/react.

Вызывают renderHook(() => useCustomHook()), чтобы запустить хук в тестовой среде.

Затем взаимодействуют с возвращаемыми значениями или функциями и проверяют изменения через result.current.

Для асинхронной логики используют waitFor и при необходимости мокают внешние зависимости, например API-запросы.

**95. What is Shallow Renderer in React testing?**
Shallow Renderer is a testing utility that renders a React component one level deep without rendering its child components.

It was mainly used with Enzyme for shallow rendering to isolate a component from its children.

This allowed testing component structure and props without mounting the full component tree.

Today, it’s less recommended, as React Testing Library encourages testing behavior rather than implementation details.

```
import React from 'react';
import { shallow } from 'enzyme';

// Example Component
function Button({ onClick, label }) {
  return <button onClick={onClick}>{label}</button>;
}

// Test using Shallow Renderer
describe('Button Component', () => {
  it('renders the button with the correct label', () => {
    const wrapper = shallow(<Button label="Click Me" />);
    expect(wrapper.text()).toBe('Click Me'); // Test the button label
  });

  it('calls onClick when the button is clicked', () => {
    const onClickMock = jest.fn(); // Mock function
    const wrapper = shallow(<Button label="Click Me" onClick={onClickMock} />);
    wrapper.simulate('click'); // Simulate click event
    expect(onClickMock).toHaveBeenCalledTimes(1); // Verify onClick was called
  });
});
```

Shallow Renderer — это инструмент для тестирования, который рендерит компонент React только на один уровень, не рендеря его дочерние компоненты.

Чаще всего он использовался вместе с Enzyme для изолированного тестирования компонента.

Это позволяло проверять структуру и props без полного монтирования дерева компонентов.

Сегодня такой подход используется реже, так как React Testing Library рекомендует тестировать поведение, а не внутреннюю реализацию.

**96. What is Snapshot Testing in React?**
Snapshot testing is a technique where a rendered component output is saved as a snapshot file and compared in future test runs.

If the output changes, Jest shows a diff so you can review whether the change is expected.

It’s commonly used with Jest and react-test-renderer or React Testing Library.

Snapshot tests are useful for detecting unintended UI changes, but should not replace behavioral tests.

```
import React from 'react';
import renderer from 'react-test-renderer';
import MyComponent from './MyComponent';

test('renders correctly', () => {
  const tree = renderer.create(<MyComponent />).toJSON();
  expect(tree).toMatchSnapshot();
});
```

Snapshot testing — это метод тестирования, при котором результат рендера компонента сохраняется в файл-снимок и сравнивается при следующих запусках тестов.

Если вывод изменился, Jest показывает разницу, чтобы проверить, ожидаемо ли изменение.

Обычно используется вместе с Jest и react-test-renderer или React Testing Library.

Snapshot-тесты помогают выявлять непреднамеренные изменения UI, но не должны заменять тесты поведения.

**97. How do you test React components that use context?**
To test components that use context, you wrap them with the required Context Provider during rendering.

In React Testing Library, you pass a custom wrapper to render() that provides the context value.

Example: render(<Component />, { wrapper: ({ children }) => <MyContext.Provider value={mockValue}>{children}</MyContext.Provider> }).

This allows you to control the context data and test different scenarios.

```
import { render } from '@testing-library/react';
import { MyContextProvider } from './MyContextProvider';
import MyComponent from './MyComponent';

test('renders correctly with context', () => {
  const { getByText } = render(
    <MyContextProvider value="test value">
      <MyComponent />
    </MyContextProvider>,
  );
  expect(getByText('test value')).toBeInTheDocument();
});
```

Чтобы тестировать компоненты, использующие context, их оборачивают в соответствующий Context Provider при рендере.

В React Testing Library можно передать кастомный wrapper в render(), который предоставляет нужное значение контекста.

Пример: render(<Component />, { wrapper: ({ children }) => <MyContext.Provider value={mockValue}>{children}</MyContext.Provider> }).

Так можно контролировать данные контекста и тестировать разные сценарии.

**98. How do you test React components that use Redux?**
To test React components that use Redux, you wrap them with the Redux Provider and pass a test store.

You can create a real store with configureStore (Redux Toolkit) or use a mock store.

In React Testing Library, render the component with a custom wrapper that includes <Provider store={store}>.

Then test behavior by dispatching actions or checking UI updates based on state changes.

```
import { render } from '@testing-library/react';
import configureStore from 'redux-mock-store';
import { Provider } from 'react-redux';
import MyComponent from './MyComponent';

const mockStore = configureStore([]);

test('renders correctly with Redux state', () => {
  const store = mockStore({ counter: 0 });
  const { getByText } = render(
    <Provider store={store}>
      <MyComponent />
    </Provider>,
  );
  expect(getByText('Counter: 0')).toBeInTheDocument();
});
```

Чтобы тестировать React-компоненты с Redux, их оборачивают в Redux Provider и передают тестовый store.

Можно создать реальный store через configureStore (Redux Toolkit) или использовать mock store.

В React Testing Library компонент рендерят с кастомным wrapper, который содержит <Provider store={store}>.

После этого проверяют поведение: диспатч действий и обновление UI в зависимости от состояния.

**99. What are the key differences between shallow rendering and full DOM rendering in React tests?**
Shallow rendering renders only the component itself, without rendering its child components.

Full DOM rendering mounts the entire component tree, including children and lifecycle methods.

Shallow is faster and isolates the component, but focuses on implementation details.

Full DOM rendering tests real behavior and interactions, but is heavier and closer to real usage.

Shallow rendering рендерит только сам компонент без его дочерних компонентов.

Full DOM rendering монтирует всё дерево компонентов вместе с дочерними элементами и жизненными циклами.

Shallow быстрее и изолирует компонент, но больше ориентирован на внутреннюю реализацию.

Full DOM rendering тестирует реальное поведение и взаимодействие, но более тяжёлый и ближе к реальному использованию.

**100. What is the TestRenderer package in React?**

TestRenderer (react-test-renderer) is a package that renders React components to pure JavaScript objects without using the DOM.

It allows you to inspect the component tree and is commonly used for snapshot testing with Jest.

It provides methods like create() and toJSON() to analyze the rendered output.

It’s mainly used for structural testing rather than user interaction testing.
import TestRenderer from 'react-test-renderer';
import MyComponent from './MyComponent';

const renderer = TestRenderer.create(<MyComponent />);
const tree = renderer.toJSON();
expect(tree).toMatchSnapshot();
TestRenderer (react-test-renderer) — это пакет, который рендерит React-компоненты в обычные JavaScript-объекты без использования DOM.

Он позволяет анализировать дерево компонентов и часто используется для snapshot-тестирования с Jest.

Предоставляет методы create() и toJSON() для получения структуры рендера.

Обычно применяется для структурного тестирования, а не для проверки пользовательских взаимодействий.

**What is the purpose of ReactTestUtils package?**
ReactTestUtils is a testing utility package provided by React to help test components and simulate user interactions.

It allows rendering components into a test DOM and triggering events like click or change.

It was commonly used before React Testing Library became popular.

Today, it’s considered lower-level and less recommended compared to modern testing tools.

ReactTestUtils — это пакет утилит для тестирования от React, предназначенный для тестирования компонентов и имитации пользовательских действий.

Он позволяет рендерить компоненты в тестовый DOM и вызывать события, например click или change.

Чаще использовался до популярности React Testing Library.

Сегодня считается более низкоуровневым инструментом и используется реже по сравнению с современными библиотеками тестирования.
