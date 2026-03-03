# FastApi

**1. What is FastAPI, and how does it differ from other web frameworks?**

---

FastAPI is a modern Python web framework for building APIs, based on ASGI and Starlette.
It provides high performance (comparable to Node.js/Go) due to async support and type hints.
Unlike Django or Flask, FastAPI uses Python type annotations for automatic validation, serialization, and OpenAPI documentation generation. It is designed specifically for building RESTful APIs with minimal boilerplate.
Key Differences from Other Frameworks:

vs Flask:

- FastAPI has automatic API documentation (OpenAPI/Swagger)

- Built-in data validation using Pydantic

- Async support by default

- Type hints for better IDE support and validation

vs Django REST Framework:

- FastAPI is lighter and more focused on APIs

- Better performance (one of the fastest Python frameworks)

- Simpler setup for API-only applications

- Built-in async support

vs Express.js (Node.js):

- Comparable performance
- Automatic data validation and serialization
- Built-in documentation generation

FastAPI — это современный Python-фреймворк для создания API, построенный на ASGI и Starlette. Обеспечивает высокую производительность благодаря async и type hints. В отличие от Django и Flask, использует аннотации типов для автоматической валидации, сериализации и генерации документации OpenAPI. Ориентирован именно на разработку REST API с минимальным количеством шаблонного кода.

**2. Benefits of Using FastAPI**

---

FastAPI provides high performance due to async support and ASGI. It offers automatic request validation and serialization using Python type hints. It generates interactive API documentation (Swagger UI and ReDoc) out of the box. FastAPI reduces boilerplate code and improves developer productivity.

FastAPI обеспечивает высокую производительность благодаря async и ASGI. Автоматически валидирует и сериализует данные через аннотации типов Python. Генерирует интерактивную документацию (Swagger UI и ReDoc) “из коробки”. Сокращает количество шаблонного кода и повышает продуктивность разработки.

**3. How FastAPI Handles Requests and Responses**

---

FastAPI handles requests using ASGI and async functions for non-blocking I/O. Incoming requests are validated automatically based on type hints and Pydantic models. Path, query, header, and body parameters are parsed and converted to Python types. Responses are automatically serialized to JSON, and response models can enforce output validation.

FastAPI обрабатывает запросы через ASGI и async-функции для неблокирующего I/O. Входящие данные автоматически валидируются на основе аннотаций типов и Pydantic-моделей. Параметры пути, запроса, заголовков и тела автоматически парсятся и приводятся к Python-типам. Ответы сериализуются в JSON, а response models позволяют валидировать выходные данные.

**4. Route Definition Syntax**

---

In FastAPI, routes are defined using decorators like `@app.get(), @app.post(), @app.put(), and @app.delete().` The decorator specifies the HTTP method and path, and the function handles the request. Path parameters are declared inside the URL, and query/body parameters are defined via function arguments. Type hints enable automatic validation and documentation generation.

В FastAPI маршруты объявляются через декораторы @app.get(), @app.post(), @app.put(), @app.delete(). Декоратор задаёт HTTP-метод и путь, а функция обрабатывает запрос. Параметры пути указываются в URL, параметры запроса и тела — через аргументы функции. Аннотации типов обеспечивают автоматическую валидацию и генерацию документации.

**5. Types of Request Parameters**

FastAPI supports several types of request parameters: path, query, header, cookie, and body. Path parameters are part of the URL and are required. Query parameters are optional by default and passed in the URL after ?. Headers and cookies are extracted from the request metadata. Body parameters are typically defined using Pydantic models for validation.

**Path Parameters**

```python
@app.get("/users/{user_id}")
def get_user(user_id: int):
    return {"user_id": user_id}
```

**Query Parameters**

```python
@app.get("/items/")
def read_items(skip: int = 0, limit: int = 10):
    return {"skip": skip, "limit": limit}
```

**Request Body**

```python
from pydantic import BaseModel
class Item(BaseModel):
    name: str
    price: float
@app.post("/items/")
def create_item(item: Item):
    return item
```

Headers

```python
from fastapi import Header

@app.get("/items/")
def read_items(user_agent: str = Header(None)):
    return {"User-Agent": user_agent}
```

Cookies

```python
from fastapi import Cookie

@app.get("/items/")
def read_items(session_id: str = Cookie(None)):
    return {"session_id": session_id}
```

FastAPI поддерживает несколько типов параметров запроса: path, query, header, cookie и body. Path-параметры находятся в URL и обязательны. Query-параметры передаются после ? и по умолчанию необязательны. Headers и cookies извлекаются из метаданных запроса. Body-параметры обычно описываются через Pydantic-модели для валидации.

**6. Dependency Injection in FastAPI**

---

FastAPI uses a built-in dependency injection system based on the Depends() function. Dependencies are declared as function parameters and can handle logic like authentication, database sessions, or validation. They are resolved automatically before the endpoint function is executed. Dependencies can be reused, nested, and scoped per request.

В FastAPI используется встроенная система dependency injection через функцию Depends(). Зависимости объявляются как параметры функции и могут содержать логику аутентификации, работы с БД или валидации. Они автоматически выполняются перед вызовом endpoint. Зависимости можно переиспользовать, вкладывать друг в друга и ограничивать областью запроса.

**7. Defining and Using Dependencies**

---

Dependencies in FastAPI are defined as regular Python functions and injected using Depends(). You declare them as parameters in your path operation function. FastAPI resolves and executes the dependency before calling the endpoint. Dependencies can return values, raise exceptions, or manage resources (e.g., DB sessions with yield).

```python
from fastapi import Depends
# Simple dependency
def common_parameters(q: str = None, skip: int = 0, limit: int = 100):
    return {"q": q, "skip": skip, "limit": limit}
@app.get("/items/")
def read_items(commons: dict = Depends(common_parameters)):
    return commons
# Class-based dependency
class CommonQueryParams:
    def __init__(self, q: str = None, skip: int = 0, limit: int = 100):
        self.q = q
        self.skip = skip
        self.limit = limit
@app.get("/users/")
def read_users(commons: CommonQueryParams = Depends(CommonQueryParams)):
    return commons
```

В FastAPI зависимости определяются как обычные Python-функции и подключаются через Depends(). Они объявляются как параметры в функции обработчика маршрута.
FastAPI автоматически выполняет зависимость перед вызовом endpoint. Зависимости могут возвращать значения, выбрасывать исключения или управлять ресурсами (например, DB-сессией через yield).

**8. Middleware in FastAPI**

---

Middleware in FastAPI is used to process requests and responses globally before they reach the route handler. It can be used for logging, authentication, CORS, metrics, or modifying requests/responses. Middleware runs on every request and can execute code before and after the endpoint. It is added using app.add_middleware() or custom @app.middleware("http") decorators.

Middleware в FastAPI используется для глобальной обработки запросов и ответов до попадания в обработчик. Применяется для логирования, аутентификации, CORS, метрик или изменения запроса/ответа. Выполняется для каждого запроса и может выполнять код до и после endpoint. Добавляется через app.add_middleware() или кастомный декоратор @app.middleware("http").

**9. Adding Middleware**

---

Middleware in FastAPI is added using app.add_middleware() for built-in or third-party middleware. For custom logic, you can use the @app.middleware("http") decorator. Middleware can modify the request before it reaches the endpoint and the response before it is returned. It is typically used for CORS, authentication, logging, and performance monitoring.

```python
from fastapi import FastAPI, Request
import time

app = FastAPI()
@app.middleware("http")
async def add_process_time_header(request: Request, call_next):
    start_time = time.time()
    response = await call_next(request)
    process_time = time.time() - start_time
    response.headers["X-Process-Time"] = str(process_time)
    return response
# Using third-party middleware
from fastapi.middleware.cors import CORSMiddleware
app.add_middleware(
    CORSMiddleware,
    allow_origins=["*"],
    allow_credentials=True,
    allow_methods=["*"],
    allow_headers=["*"],
)
```

Middleware в FastAPI добавляется через app.add_middleware() для встроенных или сторонних компонентов. Для собственной логики используется декоратор @app.middleware("http"). Middleware может изменять запрос до обработки endpoint и ответ перед возвратом клиенту. Чаще всего применяется для CORS, аутентификации, логирования и мониторинга производительности.

**10. Path Parameters vs Query Parameters**

--

Path parameters are part of the URL path and are required to identify a specific resource. Query parameters are optional and passed after ? to filter, sort, or modify the request. Path parameters define resource identity, while query parameters refine the request. In FastAPI, both are defined via function arguments with type hints.

Path-параметры являются частью URL и обязательны для идентификации ресурса. Query-параметры передаются после ? и обычно используются для фильтрации или сортировки. Path определяет ресурс, Query уточняет запрос. В FastAPI оба типа объявляются через аргументы функции с аннотациями типов.

**11. Exception and Error Handling**

---

FastAPI handles errors using HTTPException to return custom status codes and error messages. You can define global exception handlers using @app.exception_handler(). Validation errors are automatically handled and returned as structured JSON responses. Custom exceptions can be created and mapped to specific HTTP responses.

```python
from fastapi import HTTPException

@app.get("/items/{item_id}")
def read_item(item_id: str):
    if item_id not in items:
        raise HTTPException(status_code=404, detail="Item not found")
    return {"item": items[item_id]}
# Custom exception handler
from fastapi.responses import JSONResponse
class UnicornException(Exception):
    def __init__(self, name: str):
        self.name = name
@app.exception_handler(UnicornException)
async def unicorn_exception_handler(request: Request, exc: UnicornException):
    return JSONResponse(
        status_code=418,
        content={"message": f"Oops! {exc.name} did something."}
    )
```

В FastAPI ошибки обрабатываются через HTTPException с указанием статуса и сообщения. Глобальные обработчики можно задать через @app.exception_handler().
Ошибки валидации обрабатываются автоматически и возвращаются в формате JSON. Можно создавать собственные исключения и сопоставлять их с HTTP-ответами.

**12. Handling CORS**

---

CORS in FastAPI is handled using CORSMiddleware. You add it with app.add_middleware(CORSMiddleware, allow_origins, allow_methods, allow_headers, etc.).
It controls which domains, HTTP methods, and headers are allowed to access the API. This is required when the frontend and backend run on different origins.

```python
from fastapi.middleware.cors import CORSMiddleware
app.add_middleware(
    CORSMiddleware,
    allow_origins=["http://localhost:3000", "https://mydomain.com"],
    allow_credentials=True,
    allow_methods=["GET", "POST"],
    allow_headers=["*"],
)
```

CORS в FastAPI настраивается через CORSMiddleware. Он добавляется через app.add_middleware() с параметрами allow_origins, allow_methods, allow_headers и т.д. Позволяет управлять тем, какие домены, методы и заголовки могут обращаться к API. Необходим, если frontend и backend работают на разных origin.

**13. Pydantic in FastAPI**

---

Pydantic is used in FastAPI for data validation, serialization, and settings management. Request and response models are defined as Pydantic classes with type annotations. It automatically validates incoming data and returns clear error messages. Pydantic also supports default values, optional fields, and complex nested models.

```python
from pydantic import BaseModel, validator
from typing import Optional

class User(BaseModel):
    name: str
    email: str
    age: Optional[int] = None

    @validator('email')
    def email_must_contain_at(cls, v):
        if '@' not in v:
            raise ValueError('Invalid email')
        return v
```

Pydantic в FastAPI используется для валидации данных, сериализации и управления настройками. Модели запроса и ответа описываются как классы Pydantic с аннотациями типов. Входящие данные автоматически валидируются с понятными сообщениями об ошибках. Поддерживаются значения по умолчанию, optional-поля и вложенные модели.

**14. Response Model Syntax**

---

In FastAPI, a response model is defined using the response_model parameter in the route decorator. It specifies the Pydantic model that shapes and validates the response data. FastAPI automatically filters and serializes the output according to the model. This ensures consistent API responses and automatic OpenAPI documentation.

```python
from pydantic import BaseModel
class Item(BaseModel):
    name: str
    price: float
    is_offer: bool = False
class ItemResponse(BaseModel):
    name: str
    price: float
@app.post("/items/", response_model=ItemResponse)
def create_item(item: Item):
    return item
# Response model with list
from typing import List
@app.get("/items/", response_model=List[ItemResponse])
def read_items():
    return items
```

В FastAPI модель ответа задаётся через параметр response_model в декораторе маршрута. Она указывает Pydantic-модель, которая формирует и валидирует выходные данные. FastAPI автоматически фильтрует и сериализует ответ согласно модели. Это обеспечивает консистентность API и автоматическую генерацию документации OpenAPI.

**15. Background Tasks**

---

FastAPI supports background tasks using the BackgroundTasks utility. You add a task inside the endpoint, and it runs after the response is returned to the client. This is useful for sending emails, logging, or triggering external processes without blocking the request. Background tasks run in the same application process.

В FastAPI фоновые задачи реализуются через BackgroundTasks. Задача добавляется в endpoint и выполняется после отправки ответа клиенту. Это удобно для отправки email, логирования или вызова внешних сервисов без блокировки запроса. Фоновые задачи выполняются в рамках того же процесса приложения.

**16. Using Background Tasks**

---

To use background tasks in FastAPI, include BackgroundTasks as a parameter in the endpoint function. Call background_tasks.add_task(function, \*args) to register a task. The task runs after the response is sent to the client. This allows non-blocking execution of operations like sending emails or writing logs.

```python
from fastapi import BackgroundTasks

def write_log(message: str):
    with open("log.txt", "a") as log:
        log.write(message)
@app.post("/send-notification/")
async def send_notification(email: str, background_tasks: BackgroundTasks):
    background_tasks.add_task(write_log, f"Notification sent to {email}")
    return {"message": "Notification sent in the background"}
# Multiple background tasks
@app.post("/process-items/")
async def process_items(background_tasks: BackgroundTasks):
    background_tasks.add_task(task_one, "arg1")
    background_tasks.add_task(task_two, "arg2", keyword="value")
    return {"message": "Tasks started"}
```

Чтобы использовать фоновые задачи в FastAPI, добавьте BackgroundTasks как параметр функции endpoint. Зарегистрируйте задачу через background_tasks.add_task(function, \*args). Задача выполнится после отправки ответа клиенту. Это позволяет выполнять операции (например, отправку email или логирование) без блокировки запроса.

**17. WebSocket Purpose in FastAPI**

---

WebSockets in FastAPI are used for real-time, bidirectional communication between client and server. They allow persistent connections instead of the traditional request-response model. Common use cases include chat applications, live notifications, dashboards, and streaming data. FastAPI provides native support for WebSocket routes using ASGI.

WebSocket в FastAPI используются для двусторонней связи в реальном времени между клиентом и сервером. Они создают постоянное соединение вместо модели запрос-ответ. Применяются для чатов, уведомлений, дашбордов и стриминга данных. FastAPI имеет встроенную поддержку WebSocket через ASGI.

**18. Implementing WebSockets**

---

In FastAPI, WebSockets are implemented using a @app.websocket() route. The server accepts the connection with websocket.accept() and then sends/receives messages in a loop. You can use websocket.receive_text() / receive_json() and websocket.send_text() / send_json(). WebSockets are typically used for real-time features like chat or live updates.

```python
from fastapi import WebSocket, WebSocketDisconnect
@app.websocket("/ws")
async def websocket_endpoint(websocket: WebSocket):
    await websocket.accept()
    try:
        while True:
            data = await websocket.receive_text()
            await websocket.send_text(f"Message text was: {data}")
    except WebSocketDisconnect:
        print("Client disconnected")
# WebSocket with path parameters
@app.websocket("/ws/{client_id}")
async def websocket_endpoint(websocket: WebSocket, client_id: int):
    await websocket.accept()
    # Handle client-specific logic
```

В FastAPI WebSockets реализуются через маршрут @app.websocket(). Сервер принимает соединение через websocket.accept(), затем в цикле читает и отправляет сообщения. Используются методы websocket.receive_text()/receive_json() и websocket.send_text()/send_json(). Обычно применяются для чатов и live-обновлений.

**19. OAuth2 and JWT Authentication Support**

---

FastAPI provides built-in support for OAuth2 using OAuth2PasswordBearer and security utilities. JWT is commonly used to generate and verify access tokens for authenticated users. Tokens are created after successful login and included in the Authorization header (Bearer token). Dependencies with Depends() are used to validate and decode JWT on protected routes.

```python
from fastapi import Depends, HTTPException, status
from fastapi.security import OAuth2PasswordBearer, OAuth2PasswordRequestForm
from jose import JWTError, jwt
from passlib.context import CryptContext

oauth2_scheme = OAuth2PasswordBearer(tokenUrl="token")
pwd_context = CryptContext(schemes=["bcrypt"], deprecated="auto")
SECRET_KEY = "your-secret-key"
ALGORITHM = "HS256"
def create_access_token(data: dict):
    return jwt.encode(data, SECRET_KEY, algorithm=ALGORITHM)
async def get_current_user(token: str = Depends(oauth2_scheme)):
    try:
        payload = jwt.decode(token, SECRET_KEY, algorithms=[ALGORITHM])
        username: str = payload.get("sub")
        if username is None:
            raise HTTPException(status_code=401, detail="Invalid token")
        return username
    except JWTError:
        raise HTTPException(status_code=401, detail="Invalid token")
@app.get("/protected")
async def protected_route(current_user: str = Depends(get_current_user)):
    return {"user": current_user}
```

FastAPI имеет встроенную поддержку OAuth2 через OAuth2PasswordBearer и security-инструменты. JWT используется для создания и проверки access-токенов пользователей. Токен выдаётся после логина и передаётся в заголовке Authorization (Bearer token). Через Depends() выполняется проверка и декодирование JWT на защищённых маршрутах.

**20. Securing FastAPI Applications**

---

To secure a FastAPI application, enforce authentication and authorization using OAuth2/JWT or another identity provider. Validate and sanitize input with Pydantic models and strict schemas. Use HTTPS, configure CORS correctly, and store secrets in a secure manager (AWS Secrets Manager, Vault). Add rate limiting, logging/monitoring, and keep dependencies updated to reduce vulnerabilities.

```python
from fastapi.security import HTTPBearer, HTTPAuthorizationCredentials
from fastapi import Depends, HTTPException

security = HTTPBearer()
async def verify_token(credentials: HTTPAuthorizationCredentials = Depends(security)):
    if not verify_jwt_token(credentials.credentials):
        raise HTTPException(status_code=401, detail="Invalid token")
    return credentials.credentials
# Rate limiting
from slowapi import Limiter, _rate_limit_exceeded_handler
from slowapi.util import get_remote_address
limiter = Limiter(key_func=get_remote_address)
app.state.limiter = limiter
app.add_exception_handler(429, _rate_limit_exceeded_handler)
@app.get("/limited")
@limiter.limit("5/minute")
async def limited_endpoint(request: Request):
    return {"message": "This endpoint is rate limited"}
```

Чтобы защитить приложение FastAPI, включите аутентификацию и авторизацию через OAuth2/JWT или внешний провайдер. Валидируйте входные данные через Pydantic и строгие схемы. Используйте HTTPS, корректно настройте CORS и храните секреты в менеджере (AWS Secrets Manager, Vault). Добавьте rate limiting, логирование/мониторинг и обновляйте зависимости для снижения уязвимостей.

**21. Benefits of Using FastAPI with Docker**

---

Using FastAPI with Docker ensures consistent environments across development, testing, and production. It simplifies deployment by packaging the app and dependencies into a single container. Docker enables easy scaling and orchestration with tools like Kubernetes or Docker Compose. It improves isolation, portability, and reproducibility of the application.

```yml
FROM python:3.9
ORKDIR /app
COPY requirements.txt .
RUN pip install -r requirements.txt
COPY . .
CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]
```

Использование FastAPI с Docker обеспечивает одинаковое окружение на всех этапах разработки и продакшена. Приложение и зависимости упаковываются в единый контейнер, что упрощает деплой. Docker облегчает масштабирование и оркестрацию (Kubernetes, Docker Compose). Повышает изоляцию, переносимость и воспроизводимость приложения.

**22. Deploying to Cloud Platforms**

FastAPI applications can be deployed to cloud platforms like AWS, GCP, or Azure. You typically containerize the app with Docker and deploy using services like ECS, EKS, Cloud Run, or App Service. Use a production ASGI server such as Uvicorn with Gunicorn. Configure environment variables, HTTPS, load balancing, and monitoring for production readiness.

**Procfile**

```
web: uvicorn main:app --host=0.0.0.0 --port=${PORT:-5000}
```

**Deploy commands**

```bash
heroku create myapp
git push heroku main
```

Приложения FastAPI можно разворачивать в облаках AWS, GCP или Azure. Обычно приложение упаковывают в Docker и деплоят через ECS, EKS, Cloud Run или App Service. В продакшене используют ASGI-сервер Uvicorn с Gunicorn. Настраивают переменные окружения, HTTPS, балансировку нагрузки и мониторинг.

**23. Testing Support**

---

FastAPI provides strong testing support through Starlette’s TestClient and tools like pytest. You can test endpoints with in-memory requests without running a real server. Dependencies can be overridden to mock databases or external services. This makes it easy to write unit and integration tests for APIs.

```python
from fastapi.testclient import TestClient
from main import app

client = TestClient(app)
def test_read_main():
    response = client.get("/")
    assert response.status_code == 200
    assert response.json() == {"Hello": "World"}
def test_create_item():
    response = client.post(
        "/items/",
        json={"name": "Foo", "price": 50.5}
    )
    assert response.status_code == 200
    assert response.json()["name"] == "Foo"
# Testing with authentication
def test_protected_endpoint():
    headers = {"Authorization": "Bearer valid-token"}
    response = client.get("/protected", headers=headers)
    assert response.status_code == 200
```

FastAPI хорошо поддерживает тестирование через TestClient от Starlette и инструменты вроде pytest. Можно тестировать endpoint’ы в памяти без запуска реального сервера. Зависимости можно переопределять, чтобы мокать базу или внешние сервисы. Это упрощает написание unit и integration тестов для API.

**24. Best Practices for Development and Deployment**

---

Development Best Practices:

- Use type hints consistently.
- Implement proper error handling.
- Use Pydantic models for data validation.
- Organize code with routers.
- Write comprehensive tests.
- Use environment variables for configuration.
- Implement logging.
- Use dependency injection for reusable components.

Deployment Best Practices:

- Use HTTPS in production.
- Set up proper monitoring and logging.
- Implement health checks.
- Use environment-specific configurations.
- Set up CI/CD pipelines.
- Use secrets management.
- Implement rate limiting.
- Regular security updates.

Лучшие практики разработки:

- Использовать type hints последовательно.
- Реализовать корректную обработку ошибок.
- Использовать Pydantic-модели для валидации данных.
- Организовать код через routers.
- Писать полноценные тесты.
- Использовать переменные окружения для конфигурации.
- Добавить логирование.
- Использовать dependency injection для переиспользуемых компонентов.

Лучшие практики деплоя:

- Использовать HTTPS в продакшене.
- Настроить мониторинг и логирование.
- Добавить health checks.
- Использовать конфигурации под разные окружения.
- Настроить CI/CD.
- Хранить секреты через secrets management.
- Добавить rate limiting.
- Регулярно обновлять зависимости и патчить уязвимости.

```bash
app/
├── main.py
├── models/
│   ├── __init__.py
│   └── user.py
├── routers/
│   ├── __init__.py
│   ├── users.py
│   └── items.py
├── dependencies/
│   ├── __init__.py
│   └── auth.py
└── tests/
    ├── __init__.py
    └── test_main.py
```

**25. Scalability and Performance**

---

FastAPI scales well because it runs on ASGI and supports async, which improves throughput for I/O-bound workloads. For performance, avoid blocking calls in async endpoints and use proper connection pooling for DB and external services. Scale horizontally with multiple workers/instances behind a load balancer, typically using Gunicorn + Uvicorn workers. Use caching (Redis), rate limiting, and background processing (Celery/RQ) for heavy tasks.

FastAPI хорошо масштабируется благодаря ASGI и поддержке async, что повышает пропускную способность для I/O-нагрузки. Для производительности избегают блокирующих вызовов в async endpoint’ах и настраивают пул соединений для БД и внешних сервисов. Масштабирование обычно горизонтальное: несколько воркеров/инстансов за load balancer (часто Gunicorn + Uvicorn workers). Для тяжёлых задач используют кэш (Redis), rate limiting и фоновые очереди (Celery/RQ).

**26. Explain the concept of asynchronous programming in Python.**

---

Asynchronous programming in Python allows a program to handle multiple tasks concurrently without blocking execution. It is based on the event loop and uses async and await keywords. Instead of waiting for I/O operations (e.g., network or file access), the program pauses the task and switches to another one. It is especially useful for I/O-bound applications like web servers and APIs.

Асинхронное программирование в Python позволяет выполнять несколько задач параллельно без блокировки выполнения. Оно основано на event loop и использует ключевые слова async и await. Вместо ожидания I/O-операций программа приостанавливает задачу и переключается на другую. Особенно эффективно для I/O-нагрузки, например веб-серверов и API.

**27. How does FastAPI leverage asynchronous programming for performance?**

FastAPI leverages asynchronous programming by running on ASGI and supporting async endpoints. When you define endpoints with async def, FastAPI can handle multiple concurrent requests without blocking the event loop. While waiting for I/O operations (DB calls, HTTP requests), the server switches to other tasks, improving throughput. This makes FastAPI highly efficient for I/O-bound and high-concurrency applications.

FastAPI использует асинхронность благодаря работе на ASGI и поддержке async endpoint’ов. При использовании async def сервер может обрабатывать множество запросов без блокировки event loop. Во время ожидания I/O (БД, внешние HTTP-вызовы) выполнение переключается на другие задачи. Это повышает пропускную способность при высокой конкурентной нагрузке.

**28. What are the benefits of using asynchronous programming in FastAPI?**

--

Using asynchronous programming in FastAPI improves concurrency and allows handling many requests simultaneously. It increases throughput for I/O-bound operations like database queries and external API calls. It reduces idle waiting time by switching tasks during I/O operations. This results in better resource utilization and higher performance under load.

Использование асинхронности в FastAPI повышает конкурентность и позволяет обрабатывать много запросов одновременно. Увеличивает пропускную способность при I/O-нагрузке (БД, внешние API). Снижает время простоя за счёт переключения задач во время ожидания I/O. Это обеспечивает более эффективное использование ресурсов и лучшую производительность под нагрузкой.

**29. How does dependency injection simplify code organization and testing in FastAPI?**

---

Dependency injection in FastAPI separates business logic from infrastructure concerns. Dependencies are defined once and reused across multiple endpoints, improving modularity. They can be easily overridden in tests to mock databases, authentication, or external services. This simplifies testing, reduces coupling, and improves maintainability.

Dependency injection в FastAPI отделяет бизнес-логику от инфраструктурных деталей. Зависимости объявляются один раз и переиспользуются в разных endpoint’ах, что улучшает модульность. В тестах их можно переопределять для моков БД, аутентификации или внешних сервисов. Это упрощает тестирование, снижает связанность кода и повышает поддерживаемость.

**30. What are path operations in FastAPI?**

---

Path operations in FastAPI are functions mapped to specific HTTP methods and URL paths. They are defined using decorators like @app.get(), @app.post(), @app.put(), etc. Each path operation handles a request and returns a response. They define how the API behaves for different routes and HTTP methods.

Path operations в FastAPI — это функции, привязанные к конкретным HTTP-методам и URL-путям. Они объявляются через декораторы @app.get(), @app.post(), @app.put() и т.д. Каждая операция обрабатывает запрос и возвращает ответ. Они определяют поведение API для разных маршрутов и методов.

**31. Discuss different types of path operations (GET, POST, PUT, DELETE, etc.)**

---

- GET is used to retrieve data without modifying the resource.
- POST is used to create a new resource.
- PUT is used to fully update or replace an existing resource.
- PATCH is used for partial updates.
- DELETE is used to remove a resource.

Each path operation corresponds to an HTTP method and defines how the server handles the request.

- GET используется для получения данных без изменения ресурса.
- POST — для создания нового ресурса.
- PUT — для полного обновления или замены существующего ресурса.
- PATCH — для частичного обновления.
- DELETE — для удаления ресурса.

Каждая операция соответствует HTTP-методу и определяет поведение сервера.

**32. Explain the importance of data validation in API development.**

---

Data validation ensures that incoming requests contain correct and expected data before processing. It prevents invalid, malformed, or malicious input from reaching business logic or the database. Validation improves security, reliability, and consistency of the API. It also provides clear error messages to clients, making integration easier.

Валидация данных гарантирует, что входящие запросы содержат корректные и ожидаемые данные. Она предотвращает передачу некорректных или вредоносных данных в бизнес-логику и базу. Повышает безопасность, надёжность и консистентность API. Также обеспечивает понятные сообщения об ошибках для клиентов.

**33. How does FastAPI use Pydantic for data validation?**

---

FastAPI uses Pydantic models to define the structure and types of request and response data. When a request is received, FastAPI automatically validates the input against the Pydantic model. If validation fails, it returns a structured JSON error response. Pydantic also handles type conversion, default values, and nested models automatically.

FastAPI использует Pydantic-модели для описания структуры и типов входных и выходных данных. При получении запроса данные автоматически валидируются согласно модели. При ошибке валидации возвращается структурированный JSON-ответ с описанием ошибки. Pydantic также автоматически выполняет приведение типов, поддерживает значения по умолчанию и вложенные модели.

**34. Explain the concept of WebSockets and their use cases.**

---

WebSockets are a communication protocol that provides full-duplex, persistent connections between client and server. Unlike HTTP, they allow real-time bidirectional data exchange over a single open connection. They are used for chat applications, live notifications, online gaming, trading platforms, and real-time dashboards. WebSockets reduce overhead compared to repeated HTTP requests for continuous updates.

WebSocket — это протокол связи, обеспечивающий двустороннее постоянное соединение между клиентом и сервером. В отличие от HTTP, он позволяет обмениваться данными в реальном времени по одному открытому соединению. Используется для чатов, уведомлений, онлайн-игр, трейдинговых платформ и live-дашбордов. Снижает накладные расходы по сравнению с постоянными HTTP-запросами.

**35. Discuss challenges and best practices for WebSocket development.**

---

WebSocket development introduces challenges such as connection management, scaling, and handling dropped connections. You must manage authentication, authorization, and message validation manually. At scale, use load balancers with sticky sessions or a shared message broker (e.g., Redis, Kafka) for distributed state. Implement heartbeats/ping-pong to detect dead connections and handle reconnection logic on the client. Add rate limiting, proper error handling, and structured logging for reliability.

Разработка WebSocket сталкивается с проблемами управления соединениями, масштабирования и обрывов связи. Аутентификацию, авторизацию и валидацию сообщений нужно реализовывать самостоятельно. При масштабировании используют sticky sessions или брокер сообщений (Redis, Kafka) для общего состояния. Реализуют heartbeat/ping-pong для обнаружения мёртвых соединений и логику переподключения на клиенте. Добавляют rate limiting, корректную обработку ошибок и логирование для стабильности.

**36. Discuss best practices for managing background tasks.**

---

Background tasks should be used for short, non-critical work that can run after returning the response. For long-running or critical jobs, use a proper task queue like Celery/RQ with a broker (Redis/SQS). Make tasks idempotent and retry-safe, with timeouts and proper error handling. Track task execution with logging/metrics and use DLQ for failed messages. Avoid heavy CPU work in the web process; offload it to workers.

Фоновые задачи стоит использовать для коротких операций, которые можно выполнить после ответа клиенту. Для долгих или критичных задач лучше использовать очередь (Celery/RQ) с брокером (Redis/SQS). Задачи должны быть идемпотентными и безопасными к ретраям, с таймаутами и обработкой ошибок. Отслеживай выполнение через логи/метрики и используй DLQ для неудачных задач. Тяжёлую CPU-нагрузку не выполняй в веб-процессе — выноси в воркеры.

**37. Discuss security considerations in FastAPI development.**

---

FastAPI security starts with strong authentication and authorization, typically OAuth2 with JWT or an external IdP. Validate all input with Pydantic and enforce least-privilege access with scoped roles/permissions. Use HTTPS, secure headers, and properly configured CORS to prevent common web attacks.
Store secrets in a secrets manager, not in code or images. Add rate limiting, logging/auditing, and keep dependencies patched; scan for vulnerabilities.

Безопасность в FastAPI начинается с аутентификации и авторизации: OAuth2 + JWT или внешний провайдер. Валидируй весь ввод через Pydantic и придерживайся принципа минимальных привилегий (roles/scopes). Используй HTTPS, security headers и корректный CORS для защиты от типовых атак. Секреты храни в secrets manager, а не в коде или образах. Добавь rate limiting, аудит/логирование и регулярно обновляй зависимости, включая сканирование уязвимостей.

**38. Provide examples of using security features in FastAPI.**

---

Password hashing: Use strong password hashing algorithms like bcrypt to store user passwords securely.
CORS: Configure CORS settings to allow requests from specific domains.
Rate limiting: Limit the number of requests a client can make within a certain time period to prevent abuse.
Data encryption: Encrypt sensitive data using libraries like cryptography.
Security headers: Set security headers like Content-Security-Policy and HTTP Strict Transport Security to protect against common web attacks.
FastAPI provides security utilities like OAuth2PasswordBearer and HTTPBearer.
Example with OAuth2 and JWT:

```python
from fastapi import FastAPI, Depends, HTTPException
from fastapi.security import OAuth2PasswordBearer
import jwt

app = FastAPI()
oauth2_scheme = OAuth2PasswordBearer(tokenUrl="token")

SECRET = "secret-key"

def get_current_user(token: str = Depends(oauth2_scheme)):
    try:
        payload = jwt.decode(token, SECRET, algorithms=["HS256"])
        return payload
    except jwt.PyJWTError:
        raise HTTPException(status_code=401, detail="Invalid token")

@app.get("/protected")
def protected_route(user=Depends(get_current_user)):
    return {"user": user}
```

Here, the token is extracted from the Authorization header (Bearer token), validated, and injected into the route.

В FastAPI для безопасности используются OAuth2PasswordBearer и другие security-инструменты. В примере токен извлекается из заголовка Authorization, проверяется через JWT и передаётся в endpoint через Depends(). Если токен невалидный — возвращается ошибка 401.

**39. Discuss the importance of testing in FastAPI development.**

---

Testing is critical in FastAPI to ensure endpoints behave correctly and contracts remain stable. It validates request/response schemas, authentication flows, and edge cases before production. Automated tests prevent regressions during refactoring and speed up development through confidence. Use unit tests for business logic and integration tests with TestClient for API behavior.

Тестирование в FastAPI важно для гарантии корректной работы endpoint’ов и стабильности API-контрактов. Оно проверяет схемы запросов/ответов, аутентификацию и граничные случаи до выхода в продакшен. Автотесты предотвращают регрессии и ускоряют разработку за счёт уверенности при изменениях. Используйте unit-тесты для бизнес-логики и интеграционные тесты через TestClient для проверки API.

**40. Explain best practices for testing FastAPI applications.**

---

Best practices for testing FastAPI include separating unit tests from integration tests. Use TestClient for endpoint testing and pytest fixtures to manage setup/teardown. Override dependencies to mock databases, authentication, and external services. Test validation errors, auth/permissions, and edge cases, not only “happy paths”. Run tests in CI, use coverage thresholds, and keep test data isolated and repeatable.

Лучшие практики тестирования FastAPI — разделять unit-тесты и интеграционные тесты. Использовать TestClient для проверки endpoint’ов и pytest fixtures для setup/teardown. Переопределять зависимости, чтобы мокать БД, аутентификацию и внешние сервисы. Тестировать ошибки валидации, права доступа и edge cases, а не только “happy path”. Запускать тесты в CI, следить за покрытием и держать тестовые данные изолированными и воспроизводимыми.

**41. How do you handle request validation errors in FastAPI?**

---

FastAPI automatically handles request validation errors using Pydantic models. When validation fails, it returns a 422 Unprocessable Entity response with detailed error information in JSON. You can customize validation error handling by defining a global exception handler for RequestValidationError. This allows you to modify the error structure or log validation failures centrally.

FastAPI автоматически обрабатывает ошибки валидации через Pydantic. При ошибке возвращается 422 Unprocessable Entity с подробным JSON-описанием проблемы.
Можно переопределить поведение через глобальный обработчик RequestValidationError. Это позволяет изменить формат ответа или централизованно логировать ошибки.

**42. How can you secure FastAPI endpoints with OAuth2?**

---

To secure FastAPI endpoints with OAuth2, use OAuth2PasswordBearer (or another OAuth2 flow) to extract the access token. Create a dependency that validates the token (often JWT) and loads the current user. Attach that dependency to protected routes using Depends(), and enforce scopes/roles for authorization. Expose a token endpoint (e.g., /token) for login and token issuance, and use HTTPS in production.

Чтобы защитить endpoint’ы FastAPI через OAuth2, используют OAuth2PasswordBearer (или другой OAuth2 flow) для извлечения access token. Далее делают dependency, которое валидирует токен (часто JWT) и получает текущего пользователя. Подключают dependency к защищённым маршрутам через Depends() и проверяют scopes/roles для авторизации. Добавляют token endpoint (например, /token) для выдачи токенов и используют HTTPS в продакшене.

**43. What are CORS, and how do you handle them in FastAPI?**

CORS (Cross-Origin Resource Sharing) is a browser security mechanism that controls which domains can access your API. Browsers block cross-origin requests unless the server explicitly allows them via CORS headers. In FastAPI, CORS is handled using CORSMiddleware. You configure allowed origins, methods, headers, and credentials with app.add_middleware(CORSMiddleware, ...).

```python
from fastapi.middleware.cors import CORSMiddleware
app.add_middleware(
    CORSMiddleware,
    allow_origins=["*"],
    allow_credentials=True,
    allow_methods=["*"],
    allow_headers=["*"],
)
```

CORS — это механизм безопасности браузера, который определяет, какие домены могут обращаться к вашему API. Браузер блокирует междоменные запросы, если сервер не разрешил их через CORS-заголовки. В FastAPI CORS настраивается через CORSMiddleware. Разрешённые origin, методы, заголовки и credentials указываются через app.add_middleware(CORSMiddleware, ...).

**44. How do you upload files in FastAPI?**

---

In FastAPI, files are uploaded using the UploadFile and File classes. You declare a file parameter in the endpoint, typically as UploadFile = File(...).
UploadFile provides file metadata and supports async read operations. For large files, UploadFile is preferred because it uses a temporary file instead of loading everything into memory.

```python
from fastapi import File, UploadFile
@app.post("/uploadfile/")
def upload_file(file: UploadFile = File(...)):
    return {"filename": file.filename}
```

В FastAPI загрузка файлов выполняется через UploadFile и File. Файл объявляется как параметр endpoint’а, например UploadFile = File(...).
UploadFile предоставляет метаданные файла и поддерживает асинхронное чтение. Для больших файлов UploadFile предпочтительнее, так как использует временный файл и не загружает всё в память.

**45. How do you implement pagination in FastAPI?**

---

Pagination in FastAPI is typically implemented using query parameters like limit/offset or page/size. The endpoint accepts these parameters, validates them with type hints, and applies them in the database query. Return a structured response with items plus pagination metadata (total, page, size, next/prev).For larger systems, cursor-based pagination can be used for better performance and consistency.

```python
@app.get("/items/")
def get_items(skip: int = 0, limit: int = 10):
    return items[skip : skip + limit]
```

Пагинация в FastAPI обычно делается через query-параметры limit/offset или page/size. Endpoint принимает параметры, валидирует их через type hints и применяет в запросе к базе. Лучше возвращать структуру: список элементов + метаданные (total, page/size, next/prev). Для больших нагрузок часто используют cursor-based пагинацию для стабильности и производительности.

**46. How can you customize exception handling in FastAPI?**

---

You customize exception handling in FastAPI by registering exception handlers with @app.exception_handler(ExceptionType). You can handle built-in exceptions like HTTPException and RequestValidationError, or your own custom exceptions. Handlers let you return a consistent error format and add centralized logging/metrics. This makes error responses predictable for clients and easier to debug in production.

Кастомизация обработки исключений в FastAPI делается через регистрацию handlers с @app.exception_handler(ТипИсключения). Можно обрабатывать HTTPException, RequestValidationError и собственные исключения. Handlers позволяют унифицировать формат ошибок и централизованно добавлять логирование/метрики. Это делает ответы предсказуемыми для клиентов и упрощает диагностику в продакшене.

**47. How do you handle global dependencies in FastAPI?**

---

Global dependencies in FastAPI are defined at the application or router level using the dependencies parameter. They are executed for every request without being explicitly added to each endpoint. This is useful for authentication, logging, or request validation applied across the app. You can define them when creating FastAPI() or APIRouter().

Глобальные зависимости в FastAPI задаются на уровне приложения или роутера через параметр dependencies. Они выполняются для каждого запроса без явного указания в каждом endpoint. Подходят для общей аутентификации, логирования или валидации запросов. Определяются при создании FastAPI() или APIRouter().

## **48. How do you handle large file uploads in FastAPI?**

To handle large file uploads in FastAPI, use UploadFile instead of reading the file into memory. UploadFile stores data in a temporary file and supports async streaming via .read() in chunks. Process the file in chunks to avoid high memory usage. You can also configure server limits (e.g., reverse proxy or ASGI server) and validate file size/type before processing.

```python
python from fastapi.responses import StreamingResponse
@app.post("/upload/")
async def upload_large_file(file: UploadFile = File(...)):
    async def iterfile():
        yield from file.file
        return StreamingResponse(iterfile(), media_type="application/octet-stream")
```

Для загрузки больших файлов в FastAPI используйте UploadFile, а не чтение всего файла в память. UploadFile сохраняет данные во временный файл и поддерживает асинхронное чтение по частям. Обрабатывайте файл чанками, чтобы не перегружать память. Также настройте лимиты на уровне сервера (reverse proxy/ASGI) и валидируйте размер и тип файла перед обработкой.
