# React Redux

**1. What is Flux?**

---

**Flux** is an application architecture pattern introduced by Facebook for managing state in client-side applications. It follows a unidirectional data flow: Action → Dispatcher → Store → View. Actions describe what happened, the Dispatcher sends them to Stores, Stores update state, and the View re-renders. Flux influenced libraries like Redux and helps make state changes predictable.

**Flux** — это архитектурный паттерн, предложенный Facebook для управления состоянием в клиентских приложениях. Он основан на однонаправленном потоке данных: Action → Dispatcher → Store → View. Actions описывают событие, Dispatcher передаёт его в Store, Store обновляет состояние, а View перерисовывается. Flux повлиял на создание Redux и помогает делать изменения состояния предсказуемыми.

**2. What is Redux?**

---

Redux is a predictable state management library for JavaScript applications, often used with React. It stores the entire application state in a single store and updates it through pure functions called reducers. State changes are triggered by dispatching actions, following a unidirectional data flow.
Redux makes state predictable, easier to debug, and supports tools like time-travel debugging.

Redux — это библиотека для предсказуемого управления состоянием в JavaScript-приложениях, часто используемая с React. Она хранит всё состояние приложения в одном store и обновляет его через чистые функции — reducers. Изменения состояния происходят через dispatch действий (actions) с однонаправленным потоком данных. Redux делает состояние предсказуемым, упрощает отладку и поддерживает инструменты вроде time-travel debugging.

**3. What are the core principles of Redux?**

---

Redux is based on three core principles.
First, there is a single source of truth — the entire application state is stored in one store.
Second, state is read-only — the only way to change it is by dispatching an action.
Third, changes are made with pure functions called reducers, which return a new state based on the previous state and the action.

Redux основан на трёх ключевых принципах.
Первый — единственный источник истины: всё состояние приложения хранится в одном store.
Второй — состояние только для чтения: изменить его можно только через dispatch действия.
Третий — изменения выполняются чистыми функциями (reducers), которые возвращают новое состояние на основе предыдущего состояния и action.

**4. What are the downsides of Redux compared to Flux?**

---

Redux can introduce more boilerplate, especially in large applications with many actions and reducers. It enforces strict immutability and pure reducers, which may add complexity for beginners. All state is stored in a single global store, which can become hard to manage if not well structured. Middleware setup (for async logic) adds extra configuration compared to classic Flux implementations.

Redux может создавать больше шаблонного кода, особенно в крупных приложениях с множеством actions и reducers. Он строго требует неизменяемости состояния и чистых reducers, что может усложнять работу новичкам. Всё состояние хранится в одном глобальном store, который при плохой структуре становится сложным для управления. Для асинхронной логики требуется middleware, что добавляет дополнительную настройку по сравнению с классическим Flux.

**5. What is the difference between mapStateToProps() and mapDispatchToProps()?**

---

mapStateToProps is used to select data from the Redux store and pass it as props to a component. It subscribes the component to store updates and re-renders it when selected state changes. mapDispatchToProps is used to provide action dispatching functions as props to the component. It allows the component to trigger state changes by dispatching actions.

mapStateToProps используется для выбора данных из Redux store и передачи их в компонент через props. Он подписывает компонент на обновления store и вызывает перерисовку при изменении выбранного состояния. mapDispatchToProps используется для передачи функций dispatch в компонент через props. Он позволяет компоненту инициировать изменения состояния, отправляя actions.

**6. Can you dispatch an action in a reducer?**

---

No, you should not dispatch an action inside a reducer. Reducers must be pure functions — they take the current state and an action, and return a new state without side effects. Dispatching inside a reducer would break Redux principles and cause unpredictable behavior. Side effects and additional dispatches should be handled in middleware like Redux Thunk or Redux Saga.

Нет, нельзя dispatch-ить action внутри reducer. Reducer должен быть чистой функцией — он принимает текущее состояние и action и возвращает новое состояние без побочных эффектов. Dispatch внутри reducer нарушает принципы Redux и делает поведение непредсказуемым. Побочные эффекты и дополнительные dispatch выполняют через middleware, например Redux Thunk или Redux Saga.

**7. How do you access the Redux store outside a component?**

---

You can access the Redux store outside a component by importing the store instance directly. After exporting the store from its configuration file, you can use store.getState() to read state and store.dispatch() to dispatch actions.
This approach should be used carefully to avoid tight coupling. For async logic, it's often better to use middleware like Redux Thunk instead of directly accessing the store.

Получить доступ к Redux store вне компонента можно, импортировав сам экземпляр store. После экспорта store из файла конфигурации можно использовать store.getState() для чтения состояния и store.dispatch() для отправки действий. Этот способ стоит применять осторожно, чтобы избежать жёсткой связности кода.
Для асинхронной логики чаще используют middleware, например Redux Thunk, вместо прямого обращения к store.

**8. What are the drawbacks of the MVW pattern?**

---

MVW (Model-View-Whatever) lacks strict structure, since "Whatever" is not clearly defined. This can lead to inconsistent architecture and unclear separation of responsibilities. Large applications may become hard to maintain due to tight coupling between components. It can also make testing more difficult because logic is often spread across layers. MVW (Model-View-Whatever) не имеет строгой структуры, так как «Whatever» чётко не определён.

Это приводит к размытым границам ответственности и непоследовательной архитектуре. В больших приложениях появляется сильная связность компонентов, что усложняет поддержку. Также усложняется тестирование, поскольку логика часто распределена по разным слоям.

**\*9. Are there any similarities between Redux and RxJS?**

---

Yes, Redux and RxJS share some conceptual similarities. Both follow a reactive pattern and are based on unidirectional data flow. Both work with streams of data over time — Redux with action streams, RxJS with observable streams. They promote predictable state management and separation of side effects from core logic.

Да, между Redux и RxJS есть концептуальные сходства. Оба используют реактивный подход и однонаправленный поток данных. Оба работают с потоками данных во времени — Redux с потоком actions, RxJS с observable-потоками. Они способствуют предсказуемому управлению состоянием и отделению побочных эффектов от основной логики.

**10. How do you reset state in Redux?**

---

You reset state in Redux by handling a specific action in the reducer, such as RESET or LOGOUT. In the reducer, you return the initialState when that action is dispatched. For example: if (action.type === "RESET") return initialState. You can also reset the entire store by returning undefined in the root reducer and letting reducers reinitialize state.

Сброс состояния в Redux делают через обработку специального action, например RESET или LOGOUT, в reducer. reducer при получении этого action возвращают initialState. Например: if (action.type === "RESET") return initialState. Также можно сбросить весь store, вернув undefined в root reducer, чтобы reducers заново инициализировали состояние.

**11. What is the difference between React Context and React Redux?**

---

React Context is a built-in React feature used to share data across the component tree without prop drilling. It's suitable for simple global state like theme, locale, or auth status. React Redux is a state management library built on top of Redux, designed for complex and large-scale state logic. It provides structured state updates, middleware support, DevTools, and better performance optimization for frequent updates.

React Context — это встроенный механизм React для передачи данных по дереву компонентов без prop drilling. Он подходит для простого глобального состояния, например темы, локали или статуса авторизации. React Redux — это библиотека управления состоянием поверх Redux, предназначенная для сложной и масштабной логики состояния. Она предоставляет структурированные обновления состояния, поддержку middleware, DevTools и лучшую оптимизацию при частых обновлениях.

**12. Why are Redux state functions called reducers?**

---

They are called reducers because they reduce the previous state and an action into a new state. The name comes from the functional programming concept of a reduce function, like Array.prototype.reduce(), which accumulates values into a single result. In Redux, a reducer takes (state, action) and returns a new state, following the same idea of transforming input into a single output.

Их называют reducers, потому что они «сводят» (reduce) предыдущее состояние и action к новому состоянию. Название происходит из функционального программирования — от функции reduce, например Array.prototype.reduce(), которая сворачивает значения в один результат. В Redux reducer принимает (state, action) и возвращает новое состояние, реализуя ту же идею преобразования входных данных в один итоговый результат.

**13. How do you make an AJAX request in Redux?**

---

In Redux, AJAX requests are handled outside reducers using middleware. A common approach is Redux Thunk: you dispatch an async function that performs the request (fetch/axios) and then dispatches success or failure actions. Another approach is Redux Saga, where generator functions handle side effects and dispatch actions based on request results. With Redux Toolkit, createAsyncThunk is often used to encapsulate the async request and auto-generate pending/fulfilled/rejected actions.

В Redux AJAX-запросы выполняют вне reducers, через middleware. Частый вариант — Redux Thunk: диспатчится async-функция, которая делает запрос (fetch/axios), а затем отправляет actions успеха или ошибки. Другой вариант — Redux Saga, где побочные эффекты обрабатываются generator-функциями и затем диспатчатся actions по результатам запроса. В Redux Toolkit часто используют createAsyncThunk, который инкапсулирует запрос и автоматически создаёт pending/fulfilled/rejected actions.

**14. Should you keep all component states in the Redux store?**

---

No, you shouldn't keep all component state in Redux. Redux is best for global, shared state that multiple parts of the app need (auth, cached server data, app-wide UI state). Local UI state like input values, open/closed dropdowns, or temporary form state is usually better kept in component state. Putting everything in Redux adds complexity and boilerplate without real benefit.

Нет, не стоит хранить весь component state в Redux. Redux лучше подходит для глобального общего состояния, которое нужно разным частям приложения (auth, кэш серверных данных, общий UI state). Локальное UI-состояние вроде значений инпутов, открытых dropdown'ов или временного состояния формы обычно лучше держать в state компонента. Если складывать всё в Redux, это добавляет лишнюю сложность и шаблонный код без реальной пользы.

**15. What is the proper way to access the Redux store?**

---

The proper way to access the Redux store in React is through React Redux hooks like useSelector and useDispatch. useSelector is used to read data from the store, and useDispatch is used to dispatch actions. In older code, connect with mapStateToProps and mapDispatchToProps is used. Directly importing the store should be avoided in components to keep the architecture clean and testable.

Правильный способ доступа к Redux store в React — через хуки React Redux: useSelector и useDispatch. useSelector используют для чтения данных из store, а useDispatch — для отправки actions. В старом коде применяют connect с mapStateToProps и mapDispatchToProps. Прямой импорт store в компонентах нежелателен, чтобы сохранить чистую архитектуру и тестируемость.

**16. What is the difference between a component and a container in React Redux?**

---

A component (presentational component) is responsible for UI rendering and receives data and callbacks via props. A container (smart component) connects to the Redux store, handles state selection and dispatching actions. Containers use connect or hooks like useSelector and useDispatch to interact with Redux.
This separation improves reusability and keeps UI logic separate from state management logic.

Компонент (presentational component) отвечает за отображение UI и получает данные и колбэки через props. Контейнер (smart component) подключается к Redux store, выбирает состояние и диспатчит actions. Контейнеры используют connect или хуки useSelector и useDispatch для работы с Redux. Такое разделение повышает переиспользуемость и отделяет UI-логику от логики управления состоянием.

**17. What is the purpose of constants in Redux?**

---

Constants in Redux are used to define action types as fixed values. They help prevent typos and make action types consistent across actions and reducers.
Using constants also improves maintainability and makes refactoring easier. For example: export const ADD_TODO = "ADD_TODO".

Константы в Redux используются для определения типов actions как фиксированных значений. Они помогают избежать опечаток и обеспечивают единообразие между actions и reducers. Использование констант упрощает поддержку и рефакторинг кода.
Например: export const ADD_TODO = "ADD_TODO

**18. What are the different ways to write mapDispatchToProps()?**

---

There are two main ways to write mapDispatchToProps. First, as a function that receives dispatch and returns an object with action dispatchers. Second, as an object shorthand, where action creators are automatically wrapped with dispatch. The object shorthand is shorter and more commonly used in modern Redux code.

Существует два основных способа написать mapDispatchToProps.
Первый — как функцию, которая принимает dispatch и возвращает объект с функциями-диспатчерами.
Второй — как объект (shorthand), где action creators автоматически оборачиваются в dispatch.
Сокращённая запись через объект короче и чаще используется в современном коде Redux.

The ownProps parameter gives access to the component's own props inside mapStateToProps or mapDispatchToProps. It allows you to derive state or dispatch logic based on props passed from a parent component. For example, you can select data from the store using an id from ownProps. It helps make connected components more dynamic and context-aware.

Параметр ownProps даёт доступ к собственным props компонента внутри mapStateToProps или mapDispatchToProps. Он позволяет формировать state или логику dispatch на основе props, переданных родителем. Например, можно выбрать данные из store, используя id из ownProps. Это делает подключённые компоненты более динамичными и контекстно-зависимыми.

**19. How do you structure Redux top-level directories?**

---

A common approach is feature-based structure, where each feature has its own folder containing slice, actions, reducers, and selectors.
For example:
features/
auth/
users/
posts/

Another approach is type-based structure, separating actions, reducers, and types into top-level folders. In modern Redux (with Redux Toolkit), feature-based structure is recommended for scalability and maintainability.

Часто используют feature-based структуру, где у каждой функциональности есть своя папка со slice, actions, reducers и selectors.
Например:
features/
auth/
users/
posts/

Другой вариант — type-based структура, где actions, reducers и types разделены по отдельным верхнеуровневым папкам.
В современном Redux (с Redux Toolkit) рекомендуется feature-based подход для лучшей масштабируемости и поддержки.

**20.What is Redux Saga?**

---

Redux Saga is a middleware library used to handle side effects in Redux applications. It uses generator functions to manage asynchronous logic like API calls, delays, and complex workflows. Sagas listen for specific actions and then perform effects such as calling APIs or dispatching new actions. It helps keep reducers pure and separates side-effect logic from components.

Redux Saga — это middleware-библиотека для обработки побочных эффектов в приложениях с Redux. Она использует generator-функции для управления асинхронной логикой, такой как API-запросы, задержки и сложные сценарии. Saga отслеживают определённые actions и выполняют эффекты, например вызов API или dispatch новых actions. Это позволяет сохранять reducers чистыми и отделять побочную логику от компонентов.

**21. What is the mental model of Redux Saga?**

---

The mental model of Redux Saga is "a background process" that listens for dispatched actions and reacts to them. Sagas run like separate threads, waiting for specific actions using effects like take, then performing side effects with call, put, etc. They coordinate complex async flows in a synchronous-looking way using generator functions. In short, think of Saga as an event listener and workflow manager for side effects.

Ментальная модель Redux Saga — это «фоновый процесс», который слушает отправленные actions и реагирует на них. Saga работают как отдельные потоки, ожидая определённые actions через эффекты вроде take, а затем выполняют побочные действия через call, put и другие. Они позволяют описывать сложные асинхронные сценарии в синхронном стиле с помощью generator-функций. Проще говоря, Saga — это слушатель событий и менеджер побочных эффектов.

**22. What are the differences between call and put in Redux Saga?**

---

call is used to invoke a function, usually for asynchronous operations like API requests. It blocks the saga until the function resolves and returns its result. put is used to dispatch a Redux action.
It sends an action to the store, similar to dispatch in Redux.

call используется для вызова функции, чаще всего асинхронной, например API-запроса. Он приостанавливает выполнение saga до получения результата функции. put используется для отправки Redux action. Он диспатчит action в store, аналогично dispatch в Redux.

**23. What is Redux Thunk?**

---

Redux Thunk is a middleware that allows you to write action creators that return functions instead of plain action objects.
These functions receive dispatch and getState as arguments, enabling asynchronous logic like API calls.
After completing async work, you can dispatch regular actions with the results.
It's a simple and widely used solution for handling side effects in Redux.

Redux Thunk — это middleware, которое позволяет писать action creators, возвращающие функции вместо обычных объектов action.
Эти функции получают dispatch и getState, что позволяет выполнять асинхронную логику, например API-запросы.
После завершения асинхронной операции можно диспатчить обычные actions с результатами.
Это простой и широко используемый способ обработки побочных эффектов в Redux.

**24. What are the differences between Redux Saga and Redux Thunk?**

---

Redux Thunk uses functions inside action creators to handle async logic.
Redux Saga uses generator functions and a separate middleware layer to manage side effects.
Thunk is simpler and easier to learn, suitable for basic async flows.
Saga is more powerful for complex workflows, parallel tasks, cancellation, and better testability.

Redux Thunk использует функции внутри action creators для обработки асинхронной логики.
Redux Saga использует generator-функции и отдельный слой middleware для управления побочными эффектами.
Thunk проще и легче в освоении, подходит для базовых асинхронных сценариев.
Saga мощнее для сложных процессов, параллельных задач, отмены операций и более удобного тестирования.

**25. What is Redux DevTools?**

---

Redux DevTools is a browser extension that helps debug Redux applications.
It allows you to inspect dispatched actions, view state changes, and track the history of updates.
It supports time-travel debugging, letting you move backward and forward through state changes.
It makes debugging and understanding state flow much easier.

Redux DevTools — это расширение для браузера, которое помогает отлаживать Redux-приложения.
Оно позволяет просматривать отправленные actions, изменения состояния и историю обновлений.
Поддерживает time-travel debugging — можно перемещаться назад и вперёд по изменениям состояния.
Это значительно упрощает отладку и понимание потока состояния.

**26. What are the features of Redux DevTools?**

---

Redux DevTools provides action inspection, allowing you to see every dispatched action and its payload.
It shows state diffs and full state snapshots after each action.
It supports time-travel debugging, letting you jump to any previous state.
It allows action replay, import/export of state, and monitoring async actions.
Redux DevTools позволяет просматривать все отправленные actions и их payload.

Он показывает изменения состояния (diff) и полный snapshot state после каждого action.
Поддерживает time-travel debugging — переход к любому предыдущему состоянию.
Также позволяет переигрывать actions, импортировать/экспортировать state и отслеживать асинхронные действия.

**27. What are Redux selectors and why should you use them?**

---

Redux selectors are functions that extract specific pieces of data from the Redux store.
They help keep components clean by centralizing state selection logic.
Selectors improve reusability and make refactoring easier if the state structure changes.
With libraries like Reselect, selectors can be memoized for performance optimization.

Redux selectors — это функции, которые извлекают конкретные данные из Redux store.
Они помогают держать компоненты чистыми, вынося логику выбора состояния в отдельное место.
Селекторы повышают переиспользуемость и упрощают рефакторинг при изменении структуры state.
С библиотекой Reselect селекторы можно мемоизировать для оптимизации производительности.

**28. What is Redux Form?**

---

Redux Form is a library that manages form state in Redux store. It stores form values, validation state, and errors inside Redux.
It provides higher-order components and helpers to connect forms to Redux. Today, it's less commonly used, as simpler solutions like React Hook Form or Formik are preferred.

Redux Form — это библиотека для управления состоянием форм через Redux store. Она хранит значения полей, состояние валидации и ошибки в Redux.
Предоставляет HOC и утилиты для подключения форм к Redux. Сегодня используется реже, так как чаще выбирают более простые решения, например React Hook Form или Formik.

**29. What are the main features of Redux Form?**

Redux Form stores all form state (values, touched fields, errors) inside the Redux store.

It provides automatic field value tracking and validation support (sync and async).

It offers higher-order components to connect forms to Redux and manage submission.

It supports form-level and field-level validation, normalization, and error handling.

Redux Form хранит всё состояние формы (значения, touched-поля, ошибки) в Redux store.

Она автоматически отслеживает изменения полей и поддерживает синхронную и асинхронную валидацию.

Предоставляет HOC для подключения формы к Redux и управления отправкой данных.

Поддерживает валидацию на уровне формы и отдельных полей, нормализацию и обработку ошибок.

**How do you add multiple middlewares to Redux?**

You add multiple middlewares by passing them to applyMiddleware when creating the store.

Example: createStore(rootReducer, applyMiddleware(thunk, sagaMiddleware, logger)).

Middlewares are executed in the order they are provided.

With Redux Toolkit, you configure them inside configureStore using the middleware option.

Несколько middleware добавляют через applyMiddleware при создании store.

Пример: createStore(rootReducer, applyMiddleware(thunk, sagaMiddleware, logger)).

Middleware выполняются в том порядке, в котором переданы.

В Redux Toolkit их настраивают внутри configureStore через опцию middleware.

**How do you set the initial state in Redux?**

The initial state in Redux is defined inside the reducer.

You set a default value for the state parameter, for example: function reducer(state = initialState, action).

When Redux initializes the store, it calls the reducer with undefined state, so the default initialState is returned.

You can also provide a preloadedState when creating the store to override the default initial state.

Начальное состояние в Redux задаётся внутри reducer.

Для параметра state указывают значение по умолчанию, например: function reducer(state = initialState, action).

При инициализации Redux вызывает reducer с undefined, поэтому возвращается initialState.

Также можно передать preloadedState при создании store, чтобы переопределить стандартное начальное состояние.

**How is Relay different from Redux?**

Relay is a data-fetching framework developed by Facebook, tightly integrated with GraphQL.

It focuses on fetching, caching, and synchronizing server data with React components.

Redux is a general-purpose state management library for managing client-side application state.

Relay is specialized for GraphQL-based server state, while Redux manages global client state and side effects.

Relay — это фреймворк для работы с данными, разработанный Facebook и тесно связанный с GraphQL.

Он ориентирован на получение, кэширование и синхронизацию серверных данных с React-компонентами.

Redux — это универсальная библиотека управления состоянием на клиенте.

Relay специализируется на серверном состоянии через GraphQL, а Redux управляет глобальным клиентским состоянием и побочными эффектами.

**What is an action in Redux?**
An action in Redux is a plain JavaScript object that describes what happened in the application.

It must have a type property and can optionally include additional data called payload.

Actions are dispatched to trigger state changes in reducers.

They represent events in the app and follow a unidirectional data flow.

Action в Redux — это обычный JavaScript-объект, который описывает произошедшее событие в приложении.

Он обязательно содержит свойство type и может иметь дополнительные данные (payload).

Actions диспатчатся, чтобы инициировать изменение состояния в reducers.

Они представляют события приложения и работают в рамках однонаправленного потока данных.
