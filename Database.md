## Database

---

**1. What is a Database Schema and Why is It Important?**

A database schema is a logical container (namespace) within a database that organizes database objects such as tables, views, indexes, functions, and types.

Example:

```
CREATE SCHEMA accounting;

CREATE TABLE accounting.invoices (
  id serial,
  amount numeric
);
```

Why it is important:

**Organization** — separates objects into logical groups (e.g., public, auth, reporting).

**Namespace isolation** — allows objects with the same name in different schemas.

**Security** — permissions can be granted per schema.

**Maintainability** — easier migrations, modular design.

**Search path control** — PostgreSQL resolves object names based on the search_path.

So, a schema helps structure, secure, and manage a database effectively.

Схема базы данных — это логический контейнер (пространство имён) внутри базы, который организует объекты: таблицы, представления, индексы, функции и типы.

Почему это важно:

Организация — разделение объектов по логическим группам.

Пространство имён — можно иметь одинаковые имена объектов в разных схемах.

Безопасность — можно управлять правами на уровне схемы.

Поддерживаемость — удобнее управлять миграциями и структурой.

Управление search_path — PostgreSQL ищет объекты по порядку схем.

Схема помогает структурировать, защищать и масштабировать базу данных.

---

**2. Explain the Difference Between a Primary Key and a Foreign Key.**

A Primary Key (PK) uniquely identifies each row in a table.

**Must be unique**

**Cannot be NULL**

**Only one primary key per table (can be composite)**

Example:

```
CREATE TABLE users (
id serial PRIMARY KEY,
name text
);
```

A Foreign Key (FK) is a column (or set of columns) that references the primary key of another table.

**Enforces referential integrity**

**Can have duplicates**

**Can be NULL (unless restricted)**

Example:

```
CREATE TABLE orders (
id serial PRIMARY KEY,
user_id int REFERENCES users(id)
);
```

Key difference:

**Primary Key identifies a record in its own table.**

**Foreign Key links a record to another table.**

Primary Key (первичный ключ) — уникально идентифицирует строку в таблице.
**Должен быть уникальным**

**Не может быть NULL**

**В таблице только один PK (может быть составным)**

Foreign Key (внешний ключ) — ссылается на первичный ключ другой таблицы.

**Обеспечивает целостность данных**

**Может повторяться**

**Может быть NULL (если не запрещено)**

Главное отличие:

**Primary Key — идентификатор записи в своей таблице.**

**Foreign Key — связь между таблицами.**

---

**3. What is CRUD Operations?**

CRUD stands for Create, Read, Update, Delete — the four basic operations performed on data in a database or application.

In SQL:

Create — add new data `INSERT INTO users (name) VALUES ('John');`

Read — retrieve data `SELECT \* FROM users;`

Update — modify existing data `UPDATE users SET name = 'Jane' WHERE id = 1;`

Delete — remove data `DELETE FROM users WHERE id = 1;`

CRUD represents the fundamental data lifecycle in most applications.

CRUD — это Create, Read, Update, Delete (Создание, Чтение, Обновление, Удаление) — четыре базовые операции над данными.

В SQL:

**Create — добавление данных (INSERT)**

**Read — получение данных (SELECT)**

**Update — изменение данных (UPDATE)**

**Delete — удаление данных (DELETE)**

CRUD — это основа работы с данными в любой системе.

---

**4. How to Ensure Data Integrity in a Relational Database?**

To ensure data integrity in a relational database, use built-in constraints and transactional mechanisms.

- Use constraints

**PRIMARY KEY — unique row identification**

**FOREIGN KEY — enforce referential integrity**

**UNIQUE — prevent duplicates**

**NOT NULL — require values**

**CHECK — enforce custom rules**

- Use transactions (ACID) - Ensure atomicity and consistency with BEGIN / COMMIT / ROLLBACK.

- Proper data types - Choose correct column types (e.g., date, numeric, boolean) to prevent invalid data.

- Indexes - Support constraints and maintain performance for validations.

- Triggers (when needed) - Enforce complex business rules.

- Application-level validation - Validate input before it reaches the database.

Чтобы обеспечить целостность данных в реляционной базе данных, используют ограничения и механизмы транзакций.

- Ограничения (constraints)

**PRIMARY KEY — уникальность строки**

**FOREIGN KEY — ссылочная целостность**

**UNIQUE — запрет дубликатов**

**NOT NULL — обязательные значения**

**CHECK — пользовательские правила**

- Транзакции (ACID) - Гарантируют атомарность и согласованность.

- Правильные типы данных - Выбор подходящих типов предотвращает некорректные значения.

- Индексы - Поддерживают ограничения и производительность.

- Триггеры - Для сложной бизнес-логики.

- Валидация на уровне приложения - Проверка данных до записи в БД.

---

**5. Explain the Difference Between OLTP and OLAP Databases.**

LTP (Online Transaction Processing) is designed for real-time transactional systems.

- Many short, fast transactions (INSERT/UPDATE/DELETE)

- High concurrency

- Normalized schema

- Focus on consistency and low latency

Example: banking systems, e-commerce apps

OLAP (Online Analytical Processing) is designed for analytical queries and reporting.

- Complex, long-running queries

- Large data scans and aggregations

- Often denormalized (star/snowflake schema)

- Focus on read performance and analytics

Example: business intelligence, data warehouses

Key difference:

- OLTP = operational systems (day-to-day transactions).

- OLAP = analytical systems (reporting and insights).

- OLTP (Online Transaction Processing) — системы для обработки транзакций в реальном времени.

Много коротких операций (INSERT/UPDATE/DELETE)

- Высокая конкурентность

- Нормализованная структура

- Приоритет — скорость и согласованность

Пример: банковские системы, интернет-магазины

OLAP (Online Analytical Processing) — системы для аналитики и отчётности.

- Сложные и длительные запросы

- Большие выборки и агрегации

- Часто денормализованные схемы

- Приоритет — аналитическая производительность

Главное отличие:

OLTP — операционные транзакции.

OLAP — аналитика и отчёты.

---

**6. What are the ACID Properties in a Database and Why are They Important?**

ACID describes four guarantees that ensure reliable database transactions:

**Atomicity** — All operations in a transaction succeed or none are applied. If one step fails, the whole transaction is rolled back.

**Consistency** — After a committed transaction, the database remains in a valid state and all constraints are satisfied.

**Isolation** — Concurrent transactions do not interfere improperly with each other. The result is as if transactions ran in a controlled order (depending on isolation level).

**Durability** — Once a transaction is committed, its changes are permanently stored, even after crashes.

Why they are important:

- Prevent data corruption

- Ensure reliable concurrent access

- Protect against partial updates

- Maintain trust in financial and critical systems

ACID — это четыре свойства, гарантирующие надёжность транзакций:

**Atomicity (Атомарность)** — либо выполняются все операции, либо ни одна.

**Consistency (Согласованность)** — после commit база остаётся в корректном состоянии.

**Isolation (Изоляция)** — параллельные транзакции не нарушают целостность данных.

**Durability (Надёжность)** — после commit изменения сохраняются даже при сбоях.

Почему это важно:

- Предотвращает повреждение данных

- Обеспечивает безопасную конкурентную работу

- Исключает частичные изменения

- Критично для финансовых и ответственных систем

---

**7.Describe the Process of ETL (Extract, Transform, Load).**

ETL (Extract, Transform, Load) is a process used to move and prepare data from multiple sources into a data warehouse or analytics system.

**Extract** - Data is collected from source systems (databases, APIs, files, logs, etc.). **Goal**: retrieve raw data without changing it.

**Transform** - Data is cleaned and processed:

- Remove duplicates

- Handle missing values

- Convert formats and data types

- Apply business rules

- Aggregate or normalize data

**Load**
The transformed data is loaded into a target system (e.g., data warehouse).
Loading can be:

- Full load (entire dataset)

- Incremental load (only new/changed data)

Why ETL is important:

- Ensures data quality and consistency

- Integrates multiple data sources

- Prepares data for analytics and reporting

ETL (Extract, Transform, Load) — это процесс извлечения, преобразования и загрузки данных в аналитическую систему или хранилище.

**Extract (Извлечение)** - Данные собираются из различных источников (БД, API, файлы, логи).

Transform (Преобразование) - Данные очищаются и обрабатываются:

- Удаление дубликатов

- Обработка пропусков

- Приведение типов и форматов

- Применение бизнес-правил

- Агрегация

Load (Загрузка) - Подготовленные данные загружаются в целевую систему. Может быть полная или инкрементальная загрузка.

ETL обеспечивает качество данных и подготовку их для аналитики и отчётности.

---

**8. What is a Data Warehouse and How is it Different from a Traditional Database?**
A Data Warehouse is a centralized system designed for storing and analyzing large volumes of historical data from multiple sources. It is optimized for reporting and analytics (OLAP).

A Traditional Database (typically OLTP) is designed for day-to-day transactional operations such as inserts, updates, and deletes.

| Key differences:                                                     | Workload                                            | Data Structure                                              | Data Type                                    |
| -------------------------------------------------------------------- | --------------------------------------------------- | ----------------------------------------------------------- | -------------------------------------------- |
| Purpose Data Warehouse → analytics, reporting, business intelligence | Data Warehouse → complex, long-running read queries | Data Warehouse → often denormalized (star/snowflake schema) | Data Warehouse → historical, aggregated data |
| Traditional DB → operational transactions                            | Traditional DB → many short, fast transactions      | Traditional DB → normalized schema                          | Traditional DB → current, real-time data     |

In short:
Traditional databases run the business; data warehouses analyze the business.

Data Warehouse (Хранилище данных) — это централизованная система для хранения и анализа больших объёмов исторических данных из разных источников. Оптимизирована для аналитики (OLAP).

Традиционная база данных (обычно OLTP) предназначена для повседневных транзакций — вставки, обновления и удаления данных.

Основные различия:

| Назначение                                | Тип нагрузки                                | Структура                                 | Тип данных                          |
| ----------------------------------------- | ------------------------------------------- | ----------------------------------------- | ----------------------------------- |
| Хранилище данных → аналитика и отчётность | Хранилище → сложные аналитические запросы   | Хранилище → часто денормализованная схема | Хранилище → исторические данные     |
| Операционная БД → транзакционная работа   | Операционная БД → быстрые короткие операции | Операционная БД → нормализованная схема   | Операционная БД → актуальные данные |

Коротко: Операционная БД обслуживает бизнес-процессы, хранилище данных анализирует их.

---

**9. How to Handle Data Migration Between Different Databases?**

Handling data migration between different databases requires planning, validation, and controlled execution.

Analyze source and target schemas

Compare data types

Map tables and columns

Identify constraints and dependencies

Choose migration method

Dump & restore (e.g., SQL export/import)

ETL tools

Database replication

Custom scripts

Transform data if needed

Convert data types

Normalize/denormalize structure

Clean inconsistent data

Migrate in stages

Full migration (one-time)

Incremental migration (sync changes)

Ensure data integrity

Disable/enable constraints carefully

Validate row counts and checksums

Test referential integrity

Minimize downtime

Use staging environment

Perform migration during low traffic

Apply cutover strategy

Test thoroughly

Functional testing

Performance testing

Rollback plan

Миграция данных между разными БД требует планирования и контроля.

Анализ схем
Сравнить структуры, типы данных, зависимости.

Выбор способа

Экспорт/импорт

ETL-инструменты

Репликация

Кастомные скрипты

Преобразование данных
Конвертация типов, очистка, изменение структуры.

Поэтапная миграция
Полная или инкрементальная.

Проверка целостности
Сверка количества строк, проверка ограничений.

Минимизация простоя
Тестовая среда, миграция в непиковое время.

Тестирование и план отката
Обязательная проверка и возможность rollback.

---

**10. What is a Relational Database and How does it Differ from a NoSQL Database?**

A Relational Database (RDBMS) stores data in structured tables (rows and columns) and uses SQL for querying. It enforces relationships through primary and foreign keys and follows a fixed schema.

Examples: PostgreSQL, MySQL, Oracle.

Key features:

- Structured schema

- ACID transactions

- Strong consistency

- SQL-based queries

- Normalized data model

A NoSQL database stores data in flexible, non-relational formats (document, key-value, column-family, graph). It is designed for scalability and handling unstructured or semi-structured data.

Examples: MongoDB, Cassandra, Redis.

Key features:

- Flexible or schema-less

- Horizontal scalability

- Optimized for large distributed systems

- Often eventual consistency

Main differences:

| Structure                             | Scaling                                 | Consistency                            | Use cases                                                  |
| ------------------------------------- | --------------------------------------- | -------------------------------------- | ---------------------------------------------------------- |
| Relational → tables with fixed schema | Relational → typically vertical scaling | Relational → strong consistency (ACID) | Relational → financial systems, transactional apps         |
| NoSQL → flexible data models          | NoSQL → horizontal scaling              | NoSQL → often eventual consistency     | NoSQL → big data, real-time analytics, distributed systems |

Реляционная база данных (RDBMS) хранит данные в таблицах (строки и столбцы) и использует SQL. Связи между таблицами реализуются через ключи и строгую схему.

Особенности:

- Чёткая структура

- ACID-транзакции

- Строгая согласованность

- SQL

- Нормализация

NoSQL база данных хранит данные в гибких форматах (документы, ключ-значение, графы и др.) и ориентирована на масштабируемость.

Особенности:

- Гибкая схема

- Горизонтальное масштабирование

- Работа в распределённых системах

- Часто eventual consistency

Главное отличие:

- Реляционные БД — строгая структура и транзакционная надёжность.

- NoSQL — гибкость и масштабируемость.

---

**11. Explain the Importance of Data Normalization.**

Data normalization is the process of organizing data in a relational database to reduce redundancy and improve data integrity.

It involves dividing data into related tables and defining relationships using primary and foreign keys.

Main goals:

- Reduce data duplication - Store each piece of information only once.

- Prevent data anomalies - Avoid update, insert, and delete inconsistencies.

- Improve data integrity - Ensure consistency through structured relationships.

- Simplify maintenance -Changes are made in one place instead of multiple duplicated records.

Normalization is typically structured into normal forms (1NF, 2NF, 3NF, etc.), each addressing specific types of redundancy and dependency issues.

In short: normalization makes databases more consistent, reliable, and easier to maintain.

Нормализация данных — это процесс организации данных в реляционной базе для уменьшения избыточности и повышения целостности.

Она предполагает разделение данных на связанные таблицы и использование первичных и внешних ключей.

Основные цели:

- Уменьшение дублирования данных - Каждая информация хранится в одном месте.

- Предотвращение аномалий -Исключение проблем при вставке, обновлении и удалении.

- Повышение целостности данных -Обеспечение согласованности через связи.

- Упрощение поддержки -Изменения вносятся в одном месте.

Нормализация делится на нормальные формы (1NF, 2NF, 3NF и т.д.).

Коротко: нормализация делает базу данных более устойчивой, логичной и удобной в сопровождении.

---

**12. How to Perform Data Cleaning and Preprocessing?**

Data cleaning and preprocessing prepare raw data for analysis or storage to ensure accuracy, consistency, and usability.

Main steps:

- Handle missing values (remove, fill with mean/median, or imputation techniques)

- Remove duplicates - Identify and eliminate repeated records.

- Fix inconsistent data

- Standardize formats (dates, casing)

- Normalize units (kg vs lbs)

- Correct typos

- Validate data types - Ensure numeric, date, boolean fields are correctly typed.

- Handle outliers - Detect unusual values and decide whether to remove or transform them.

- Encode categorical variables - Convert categories to numeric (one-hot encoding, label encoding).

- Normalize/scale data - Scale numeric features (min-max scaling, standardization).

-Feature engineering (optional) - Create new useful columns from existing data.

**Goal**: produce clean, structured, and reliable data for analysis, ML, or reporting.

Очистка и предобработка данных — подготовка «сырых» данных для анализа или хранения.

Основные этапы:

Работа с пропусками - Удаление или заполнение значений.

Удаление дубликатов - Исключение повторяющихся записей.

Исправление несоответствий - Стандартизация форматов и единиц измерения.

Проверка типов данных -Корректные числовые, текстовые, датовые типы.

Обработка выбросов - Поиск и корректировка аномальных значений.

Кодирование категорий - Преобразование категориальных данных в числовые.

Масштабирование -Нормализация числовых признаков.

Создание новых признаков -Дополнительные вычисляемые поля.

**Цель** — получить чистые и корректные данные для анализа и моделей.

---

**13. What are the Common SQL Functions Used for Data Aggregation?**
Common SQL aggregation functions operate on multiple rows and return a single result.

Main aggregate functions:

- COUNT() — counts rows `SELECT COUNT(\*) FROM users;`

- SUM() — calculates total `SELECT SUM(amount) FROM orders;`

- AVG() — calculates average `SELECT AVG(salary) FROM employees;`

- MIN() — minimum value `SELECT MIN(price) FROM products;`

- MAX() — maximum value `SELECT MAX(price) FROM products;`

- GROUP BY — groups rows for aggregation `SELECT department, AVG(salary) FROM employees GROUP BY department;`

- HAVING — filters aggregated results `SELECT department, COUNT(_) FROM employees GROUP BY department HAVING COUNT(_) > 5;`

These functions are essential for reporting, analytics, and summarizing data.

Основные SQL-функции для агрегации данных:

- COUNT() — подсчёт строк

- SUM() — сумма

- AVG() — среднее значение

- MIN() — минимальное значение

- MAX() — максимальное значение

Также используются:

- GROUP BY — группировка данных

- HAVING — фильтрация агрегированных результатов

Эти функции применяются для отчётов, аналитики и сводных расчётов.

---

**14. Explain the Concept of Database Transactions and Their Importance in Application Development**

A database transaction is a sequence of operations executed as a single logical unit of work.
All operations inside a transaction either succeed together or fail together.

Transactions follow the ACID principles:

- **Atomicity** — all or nothing execution

- **Consistency** — database remains valid after commit

- **Isolation** — concurrent transactions don’t corrupt each other

- **Durability** — committed changes are permanent

```
BEGIN;
UPDATE accounts SET balance = balance - 100 WHERE id = 1;
UPDATE accounts SET balance = balance + 100 WHERE id = 2;
COMMIT;
```

If any step fails → ROLLBACK.

Importance in application development:

- Prevents partial updates - Ensures business operations (e.g., money transfer) are completed safely.

- Maintains data integrity -Protects relationships and constraints.

- Handles concurrency safely -Prevents race conditions and inconsistent reads.

- Improves reliability -Applications can safely retry failed transactions.

In short, transactions ensure data consistency, correctness, and reliability in real-world applications.

Транзакция базы данных — это последовательность операций, выполняемых как единое логическое действие.
Либо выполняются все операции, либо ни одна.

Транзакции обеспечивают свойства ACID:

- **Атомарность** — всё или ничего

- **Согласованность** — база остаётся корректной

- **Изоляция** — параллельные операции не мешают друг другу

- **Надёжность** — изменения сохраняются после commit

Если возникает ошибка — выполняется ROLLBACK.

Значение для разработки:

- Предотвращает частичные изменения

- Гарантирует целостность данных

- Обеспечивает безопасную конкурентность

- Повышает надёжность приложения

Транзакции — основа безопасной и корректной работы любой серьёзной системы.

---

**15. How to Optimize Database Queries for Performance?**

To optimize database queries for performance, follow a structured approach:

- Analyze the query plan Use: `EXPLAIN ANALYZE SELECT ...`

- Identify slow operations (Seq Scan, large sorts, nested loops).

- Add proper indexes

- Index columns used in WHERE, JOIN, ORDER BY

- Use composite indexes for multi-column filters

- Avoid unnecessary indexes

- Reduce scanned data - Select only needed columns (avoid SELECT \*)

- Filter early

- Use LIMIT when possible

- Optimize joins - Ensure join columns are indexed

- Choose correct join type - Reduce dataset before joining

- Keep statistics updated - Run ANALYZE and ensure autovacuum works properly.

- Avoid functions on indexed columns - They can prevent index usage.

- Use caching or materialized views - Precompute heavy aggregations.

- Consider partitioning - For very large tables, partitioning improves query pruning.

In short: measure → analyze → index → rewrite → monitor.

Чтобы оптимизировать запросы к базе данных:

- Анализируй план выполнения Используй `EXPLAIN ANALYZE.`

- Добавляй правильные индексы - Индексируй поля в WHERE, JOIN, ORDER BY.

- Уменьшай объём данных - Не используй SELECT \*, фильтруй как можно раньше.

- Оптимизируй JOIN - Индексируй ключи соединения.

- Обновляй статистику - ANALYZE, корректная работа autovacuum.

- Не применяй функции к индексируемым колонкам.

- Используй кэширование и materialized views.

- Применяй партиционирование для больших таблиц.

Главное правило: измеряй, анализируй, оптимизируй, проверяй.

---

**16. What are Stored Procedures and When would we Use Them?**

Stored Procedures are database objects that contain predefined SQL logic stored and executed on the database server.

They can include:

- Multiple SQL statements

- Control flow (IF, LOOP, CASE)

- Variables

- Error handling

```
CREATE OR REPLACE PROCEDURE transfer_money(from_id int, to_id int, amount numeric)
LANGUAGE plpgsql
AS
BEGIN
UPDATE accounts SET balance = balance - amount WHERE id = from_id;
UPDATE accounts SET balance = balance + amount WHERE id = to_id;
END;
;
```

Call it:

```
CALL transfer_money(1, 2, 100);
```

When to use stored procedures:

- Complex business logic - Encapsulate multi-step operations in the database.

- Performance optimization - Reduce network round trips between app and DB.

- Security - Restrict direct table access and expose only procedures.

- Reusability - Centralize common logic.

- Transaction control - Manage commits and rollbacks inside procedures.

In short, stored procedures help centralize logic, improve performance, and enforce security at the database level.

Stored Procedures (хранимые процедуры) — это объекты базы данных с заранее определённой логикой, выполняемой на сервере БД.

Они могут содержать:

- Несколько SQL-запросов

- Условия и циклы

- Переменные

- Обработку ошибок

Когда используются:

- Сложная бизнес-логика - Оптимизация производительности

- Повышение безопасности - Повторное использование кода

- Управление транзакциями

Хранимые процедуры позволяют перенести логику ближе к данным, повысить эффективность и контроль доступа.

---

**17. Describe the Process of Database Normalization and Denormalization.**

**Database Normalization** is the process of organizing data to reduce redundancy and improve data integrity.

**Process of Normalization**:

- Identify repeating groups → move them into separate tables (1NF).

- Remove partial dependencies → ensure non-key columns depend on the whole primary key (2NF).

- Remove transitive dependencies → non-key columns should depend only on the primary key (3NF).

- Further refinements (BCNF, etc.) for advanced dependency rules.

**Goal**:

- Eliminate duplicate data

- Prevent update/insert/delete anomalies

- Improve consistency

Example: Instead of storing customer data in every order row, create a separate customers table and reference it with a foreign key.

**Database Denormalization** is the intentional introduction of redundancy to improve performance.

**Process of Denormalization**:

- Combine related tables

- Duplicate frequently accessed data

- Store precomputed values (aggregates)

- Reduce joins in read-heavy workloads

**Goal**:

- Improve query speed

- Reduce complex joins

- Optimize for reporting/analytics

| Trade-off                                               | In practice                                                      |
| ------------------------------------------------------- | ---------------------------------------------------------------- |
| Normalization → better integrity, less redundancy       | OLTP systems are usually normalized.                             |
| Denormalization → better read performance, more storage | OLAP systems often use denormalized schemas (e.g., star schema). |

**Нормализация** — это процесс структурирования данных для уменьшения избыточности и повышения целостности.
**Денормализация** — осознанное добавление избыточности ради повышения производительности.

Нормализация повышает согласованность, денормализация ускоряет чтение.

---

**18. How to Handle Concurrent Data Access and Prevent Deadlocks?**
To handle concurrent data access and prevent deadlocks:

- Keep transactions short - Hold locks for the minimum time possible. Avoid long-running transactions.

- Access tables and rows in a consistent order - Always lock/update resources in the same sequence across transactions to prevent circular waits.

- Use proper indexes - Prevent full table scans that increase lock contention.

- Choose appropriate isolation level - Use the lowest isolation level that satisfies consistency requirements.

- Use row-level locking - Prefer SELECT ... FOR UPDATE instead of locking entire tables.

- Avoid unnecessary explicit locks - Lock only what is required.

- Implement retry logic - If a deadlock occurs, catch the error and retry the transaction.

- Monitor locking - Use system views (e.g., pg_locks) to analyze blocking and conflicts.

In short: minimize lock time, maintain consistent locking order, use proper indexing, and implement retry mechanisms.

Чтобы управлять конкурентным доступом и предотвращать дедлоки:

- Делайте транзакции короткими.

- Используйте единый порядок блокировок.

- Добавляйте правильные индексы.

- Выбирайте подходящий уровень изоляции.

- Предпочитайте блокировки строк вместо таблиц.

- Не используйте лишние блокировки.

- Реализуйте повтор транзакции при ошибке дедлока.

- Мониторьте блокировки через системные представления.

Главное — минимизировать время блокировок и соблюдать предсказуемый порядок доступа к данным.

---

**19. Explain the Concept of Database Indexing and its Importance in Query Performance.**

**Database indexing** is a technique that improves query performance by creating a data structure that allows fast lookup of rows without scanning the entire table.

An index works like a book index — instead of reading every page, the database can quickly locate matching records.

How it works:

- The database creates a separate structure (commonly a B-tree)

- It stores indexed column values with pointers to table rows

- Queries use the index to avoid full table scans

Example: `CREATE INDEX idx_users_email ON users(email);`

Why indexing is important:

- Faster SELECT queries - Especially for large tables with filters (WHERE), joins, or sorting.

- Better JOIN performance - Indexed foreign keys speed up joins.

- Efficient ORDER BY and GROUP BY - Indexes can reduce sorting cost.

- Supports constraints - PRIMARY KEY and UNIQUE use indexes internally.

Trade-offs:

- Slower INSERT/UPDATE/DELETE (index maintenance)

- Additional storage usage

In short: indexes dramatically improve read performance but add write overhead.

**Индексация** — это механизм ускорения поиска данных за счёт создания специальной структуры (например, B-tree), которая позволяет находить строки без полного сканирования таблицы.

Индекс хранит значения столбца и ссылки на строки таблицы.

Преимущества:

- Быстрее SELECT-запросы

- Ускорение JOIN

- Оптимизация ORDER BY и GROUP BY

- Поддержка PRIMARY KEY и UNIQUE

Недостатки:

- Замедление операций вставки и обновления

- Дополнительное использование памяти

- Индексы существенно ускоряют чтение, но увеличивают нагрузку при записи.

---

**20, What are the Different types of Database Partitioning and When would we Use Each Type?**

**Database partitioning** splits a large table into smaller parts (partitions) to improve performance and manageability.

**Main types:**

- Range Partitioning - Data is divided based on value ranges. Example: partition by date (2024, 2025, 2026).

Use when:

- Data is time-based - Queries filter by ranges (e.g., WHERE order_date BETWEEN ...)

- Archiving old data is required

- List Partitioning Data is divided based on predefined values. Example: partition by region (US, EU, ASIA).

Use when:

- Data belongs to specific categories - Filtering is based on discrete values

- Hash Partitioning - Data is distributed using a hash function.

Use when:

- Even data distribution is needed

- No natural range grouping exists

- High write throughput is required

Composite (Subpartitioning) - Combination of partitioning methods (e.g., range + hash).

Use when:

- Large datasets require multi-level organization

- Both time-based and distribution-based optimization are needed

Benefits:

- Faster queries (partition pruning)

- Easier maintenance

- Improved scalability

In short:

- Range → time-series or numeric intervals

- List → categorical data

- Hash → uniform distribution

- Composite → complex, large-scale systems

Партиционирование делит большую таблицу на части.

Типы:

- Range — по диапазонам (обычно по дате).

- List — по конкретным значениям (категории, регионы).

- Hash — равномерное распределение по хешу.

- Composite — комбинация методов.

Выбор зависит от структуры данных и характера запросов.

---

**21. Describe the Role of a Data Lake in a Big Data Architecture.**

A **Data Lake** is a centralized storage system designed to hold large volumes of raw data in its native format (structured, semi-structured, and unstructured).

It is a core component of Big Data architecture.

**Key characteristics**:

- Stores raw data - Data is stored as-is (JSON, CSV, logs, images, etc.).

- Schema-on-read - Structure is applied when the data is read, not when it is stored.

- Highly scalable - Built on distributed storage systems (e.g., cloud object storage).

- Supports advanced analytics - Used for machine learning, data science, and large-scale analytics.

**Role in Big Data architecture:**

- Acts as the central data repository

- Collects data from multiple sources (apps, IoT, APIs, databases)

- Feeds data warehouses and analytical systems

- Enables exploratory analysis

**Data Lake vs Data Warehouse:**

- Data Lake → raw, flexible, large-scale storage

- Data Warehouse → structured, cleaned, optimized for reporting

In short:
A Data Lake stores everything first, then structures it when needed for analytics.

**Data Lake (озеро данных)** — это централизованное хранилище больших объёмов данных в исходном формате (структурированные и неструктурированные).

**Основные особенности:**

- Хранение «сырых» данных

- Schema-on-read (структура при чтении)

- Масштабируемость

- Поддержка ML и аналитики

**Роль в Big Data архитектуре:**

- Централизованный источник данных

- Интеграция разных источников

- Основа для аналитики и data science

**Разница:**

- Data Lake — хранит всё в сыром виде

- Data Warehouse — хранит структурированные и очищенные данные

Коротко: Data Lake — это масштабируемое хранилище для всех типов данных в Big Data-системе.

---

**22. Explain the Use of Caching Strategies to Improve Database Performance.**

**Caching **improves database performance by storing frequently accessed data in a faster layer (memory) to reduce repeated database queries.

**Main caching strategies:**

- Application-level cache - Store query results in memory (e.g., Redis, Memcached). - Use when data is frequently read and rarely updated.

- Query result caching - Cache the output of expensive queries. -Invalidate cache when underlying data changes.

- Object caching - Cache fully constructed objects (e.g., user profiles).

- Read-through cache - Application checks cache first; if missing, it loads from DB and stores in cache automatically.

- Write-through cache - Data is written to both cache and DB simultaneously.

- Write-behind (write-back) - Data is written to cache first and persisted to DB later (improves write speed but adds complexity).

- TTL (Time-To-Live) - Automatically expire cached data after a defined period.

**Benefits:**

- Reduces database load

- Decreases latency

- Improves scalability

- Handles traffic spikes

**Trade-offs:**

- Cache invalidation complexity

- Risk of stale data

- Extra memory usage

In short: caching shifts read pressure away from the database and significantly improves performance when used correctly.

**Кэширование** ускоряет работу базы данных, сохраняя часто используемые данные в памяти.

**Основные стратегии:**

- Кэш на уровне приложения

- Кэширование результатов запросов

- Кэширование объектов

- Read-through

- Write-through

- Write-back

- TTL (время жизни кэша)

**Преимущества:**

- Снижение нагрузки на БД

- Меньшая задержка

- Лучшая масштабируемость

**Недостатки:**

- Сложность инвалидации

- Риск устаревших данных

Кэширование значительно повышает производительность при правильной стратегии.

---

**23. Describe the Process of Implementing Database Security and Encryption.**

**Implementing database security** and encryption involves multiple layers of protection.

- Access Control (Authentication & Authorization) - Create separate roles/users

- Apply least privilege principle - Use strong passwords or certificate-based auth

- Grant only necessary permissions (GRANT / REVOKE)

- Network Security - Restrict access via firewall

- Allow connections only from trusted IPs

- Use private networks/VPC

- Disable unnecessary ports

- Encryption in Transit

- Enable SSL/TLS for client–server communication

- Prevent data interception over the network

- Encryption at Rest

- Use disk-level encryption (e.g., cloud provider encryption) Or database-level encryption (TDE if supported)

- Column-level Encryption

- Encrypt sensitive fields (e.g., passwords, SSN)

- Use hashing for passwords (bcrypt, argon2)

- Auditing & Monitoring

- Enable logging

- Monitor suspicious activity

- Use intrusion detection tools

- Backup Security

- Encrypt backups

- Restrict access to backup storage

- Regular Updates & Patching

- Keep DB engine updated

- Fix security vulnerabilities

In short:
Database security requires layered protection — access control, encryption, monitoring, and maintenance.

**Реализация безопасности базы данных** включает несколько уровней защиты.

- Контроль доступа
- Разделение ролей и принцип минимальных привилегий.

- Сетевая защита - Ограничение доступа по IP и firewall.

- Шифрование при передаче - Использование SSL/TLS.

- Шифрование при хранении - Дисковое или встроенное шифрование.

- Шифрование отдельных полей - Хеширование паролей и защита чувствительных данных.

- Аудит и мониторинг - Логирование и контроль подозрительной активности.

- Защита резервных копий - Шифрование и ограничение доступа.

- Обновления и патчи - Регулярное обновление СУБД.

Безопасность БД — это комплекс мер, включающий контроль доступа, шифрование и постоянный мониторинг.

---

**24. How to Handle Database Migrations in a Continuous Deployment Environment?**
Handle database migrations in continuous deployment by making them safe, automated, and reversible:

- Versioned migrations in VCS - Use a migration tool (Flyway, Liquibase, Alembic, Rails/Django migrations). Migrations are code-reviewed and run in CI/CD.
- Backward-compatible (expand/contract) changes
  Deploy in steps to avoid breaking running app versions:

**Expand**: add new columns/tables (nullable), create new indexes concurrently

Deploy app that writes both old+new (or reads new with fallback)

**Contract**: remove old columns/constraints only after traffic is fully on new code

Zero/low-downtime practices

Avoid long locks: use online DDL where possible

In Postgres: CREATE INDEX CONCURRENTLY, careful with ALTER TABLE on big tables

Backfill data in batches (background job) instead of one huge migration

Separate schema and data migrations
Schema changes in pipeline; heavy backfills/rewrites as dedicated jobs with monitoring.

Transaction strategy
Most migrations should be transactional, but note some Postgres ops can’t run in a transaction (e.g., CREATE INDEX CONCURRENTLY).

Observability + safety rails

Pre-checks (disk space, replication lag)

Timeouts/lock time limits

Alerting and logs for migration steps

Rollback plan

Prefer roll-forward fixes (another migration)

Keep old columns until you’re sure

Backups/restore tested regularly

В continuous deployment миграции делают безопасными, автоматизированными и обратимыми:

Версионируемые миграции в репозитории (Flyway/Liquibase/и т.д.) и запуск в CI/CD.

Backward-compatible подход (expand/contract): сначала добавляем новое, потом переключаем код, потом удаляем старое.

Практики low/zero downtime: избегать долгих блокировок, CREATE INDEX CONCURRENTLY, бэкфиллы батчами.

Разделять schema-миграции и тяжёлые data-миграции.

Учитывать транзакционность: не всё DDL в Postgres можно в транзакции (например, CONCURRENTLY).

Мониторинг, лимиты на блокировки, алерты.

План отката: чаще roll-forward, старые поля держать до стабилизации, бэкапы проверять.

---

**25, Explain the Concept of Data Replication and Its Importance in a Distributed Database System.**
**Data replication** is the process of copying and maintaining the same data across multiple database nodes in a distributed system.

The goal is to keep data synchronized between servers.

**Types of replication:**

-- Synchronous replication - Data is written to primary and replica before commit.

- Strong consistency

- Higher latency

- Asynchronous replication -- Primary commits first, replicas update later.

- Better performance

- Possible replication lag

**Logical replication** - Replicates specific tables or changes (row-level).

**Physical (streaming) replication** - Replicates entire database at the storage level.

**Importance in distributed systems:**

- High availability - If one node fails, another can take over.

- Fault tolerance - Reduces risk of data loss.

- Read scalability - Distribute read queries across replicas.

- Disaster recovery - Maintain copies in different geographic regions.

- Load balancing - Reduce pressure on the primary node.

**Trade-offs:**

-- Replication lag

-- Conflict handling (in multi-primary setups)

-- Increased infrastructure complexity

In short: Replication improves availability, scalability, and reliability in distributed databases.

**Репликация данных** — это процесс копирования и синхронизации данных между несколькими узлами в распределённой системе.

**Основные типы:**

- Синхронная — выше согласованность, выше задержка.

- Асинхронная — быстрее, возможна задержка репликации.

- Логическая — по таблицам/строкам.

- Физическая — копирование всей базы.

**Значение:**

- Высокая доступность

- Отказоустойчивость

- Масштабирование чтения

- Аварийное восстановление

- Балансировка нагрузки

**Репликация** — ключевой механизм повышения надёжности и масштабируемости распределённых систем.

---

**26. Describe the Architecture of a NoSQL Database and Its Use Cases.**
A **NoSQL database** is designed for scalability, flexibility, and distributed systems. Its architecture differs from traditional relational databases.

**Core architectural characteristics:**

- Distributed architecture - Data is stored across multiple nodes (horizontal scaling).

- Sharding - Data is partitioned across servers based on a shard key.

- Replication - Multiple copies of data are maintained for fault tolerance.

- Flexible schema - Schema-less or dynamic schema (especially in document databases).

- BASE model (often) - Basically Available, Soft state, Eventually consistent (instead of strict ACID in many systems).

**Main types of NoSQL databases:**

- Document databases (e.g., MongoDB) - Store JSON-like documents.

- Key-Value stores (e.g., Redis) - Store data as key → value pairs.

- Column-family databases (e.g., Cassandra) - Store data in distributed column structures.

- Graph databases (e.g., Neo4j) - Optimized for relationship-heavy data.

**Use cases:**

- Big data and large-scale web apps

- Real-time analytics

- IoT systems

- Caching and session storage

- Content management systems

- Social networks and recommendation engines

**When to use NoSQL:**

- When horizontal scaling is required

- When schema flexibility is important

- When handling large volumes of semi/unstructured data

In short:

- NoSQL databases are built for distributed scalability and flexible data models.

**Архитектура NoSQL БД** ориентирована на распределённость и масштабируемость.

**Основные особенности:**

- Горизонтальное масштабирование

- Шардирование

- Репликация

- Гибкая схема

- Часто модель BASE вместо строгого ACID

**Типы:**

- Документо-ориентированные

- Key-Value

- Колонночные

- Графовые

**Применение:**

- Big Data

- Высоконагруженные веб-системы

- IoT

- Кэширование

- Социальные сети

NoSQL используется там, где важны масштабируемость и гибкость структуры данных.

---

**27. What Are the Best Practices for Optimizing ETL Processes in a Large-Scale Data Environment?**

**Optimizing ETL** in a large-scale data environment requires performance, scalability, and reliability practices.

Use incremental loads - Process only new or changed data (CDC) instead of full reloads.

Parallel processing - Split workloads across multiple threads, partitions, or distributed nodes.

Push transformations closer to storage- Use ELT when possible — let the data warehouse handle heavy transformations.

Partition large datasets - Partition by date or key to reduce scan size and enable parallelism.

Optimize data formats- Use columnar formats (Parquet, ORC) and compression for better performance.

Batch processing wisely - Choose optimal batch sizes to avoid memory overload.

Minimize data movement - Avoid unnecessary transfers between systems.

Monitor and log everything - Track job duration, failures, throughput, and bottlenecks.

Data validation and quality checks - Implement validation at each stage to avoid propagating bad data.

Fault tolerance and retries - Design idempotent jobs and automatic retry mechanisms.

Resource management - Tune memory, CPU, and I/O allocation.

Orchestration tools - Use workflow managers (Airflow, Prefect, etc.) for scheduling and dependency control.

**In short:**
Incremental processing, parallelism, efficient storage formats, monitoring, and automation are key to scalable ETL.

**Лучшие практики оптимизации ETL:**

- Инкрементальная загрузка (CDC)

- Параллельная обработка

- ELT-подход (перенос трансформаций в хранилище)

- Партиционирование данных

- Колонночные форматы и сжатие

- Оптимальные батчи

- Минимизация перемещения данных

- Мониторинг и логирование

- Проверка качества данных

- Отказоустойчивость

- Оптимизация ресурсов

- Использование оркестраторов

Главное — масштабируемость, надёжность и контроль качества данных.

---

**28. How Do You Handle Real-Time Data Streaming and Processing?**

**Handle real-time data streaming** and processing by building a pipeline that can ingest → process → store → serve events with low latency and reliability.

Ingestion layer (event broker)

- Use Kafka / Pulsar / Kinesis (or RabbitMQ for simpler queues) to:
  - buffer bursts (backpressure)

  - decouple producers from consumers

  - provide ordering and durability (by partitions)

- Stream processing layer
  Use Flink / Spark Structured Streaming / Kafka Streams to:
  - parse/validate events

  - windowed aggregations (tumbling/sliding/session windows)

  - joins/enrichment (lookup tables, dimension data)

  - stateful processing with checkpoints

- Storage/serving layer
  **Pick stores by access pattern:**

- hot operational reads: Redis / PostgreSQL

- analytics/time series: ClickHouse / Druid / BigQuery / Timescale

- long-term raw storage: object storage (S3/GCS) as a data lake

Reliability patterns

At-least-once vs exactly-once semantics

Idempotent consumers + dedup keys

DLQ (dead-letter queue) for poison messages

Schema registry + versioning (Avro/Protobuf/JSON Schema)

Checkpointing, replay, and retention strategy

Scaling and performance

Partition by a good key (user_id/tenant_id)

Autoscale consumers, tune batch sizes

Use backpressure and rate limiting

Avoid heavy per-event DB writes; batch or use sinks

Observability

End-to-end lag, throughput, error rate

Consumer group offsets, watermark delay

Tracing with correlation IDs

Реалтайм-стриминг строят как конвейер ввод → обработка → хранение → выдача.

| Слой приёма (брокер событий)                                                           | Слой обработки                                                                                                   |
| -------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- |
| Kafka / Pulsar / Kinesis (или RabbitMQ) — буферизация, decoupling, порядок/надёжность. | Flink / Spark Structured Streaming / Kafka Streams — валидация, окна, агрегации, enrichment, state + checkpoint. |

Хранение/выдача
**Выбор по паттерну:**

- быстрые чтения: Redis / PostgreSQL

- аналитика: ClickHouse / Druid / BigQuery / Timescale

- сырьё: S3/GCS как data lake

**Надёжность**

- at-least-once vs exactly-once

- идемпотентность + дедупликация

- DLQ

- схемы и версионирование

- replay/retention

**Масштабирование**

- правильный ключ партиционирования

автоскейл консьюмеров

backpressure/rate limit

батчинг вместо записи “по событию”

Наблюдаемость
лаг, throughput, ошибки, offsets/watermarks, tracing.
