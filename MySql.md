# MySQL

**1. What is MySQL and how does it work?**

---

MySQL is an open-source relational database management system (RDBMS) that stores data in structured tables and uses SQL (Structured Query Language) to manage it.

How it works:

Client-Server Architecture
Applications (clients) send SQL queries to the MySQL server.
The server processes queries and returns results.

Query Processing

Parse the SQL statement

Optimize the execution plan

Execute using storage engine

Storage Engines
MySQL supports different engines:

InnoDB (default) — supports transactions, ACID, row-level locking

MyISAM — non-transactional, faster reads (older usage)

Data Storage
Data is stored in tables with rows and columns.
Indexes are used to speed up searches.

Transactions
With InnoDB, MySQL supports ACID properties using logs and MVCC.

Replication & Scaling
Supports replication (primary-replica) and clustering for scalability and availability.

In short:
MySQL receives SQL queries, optimizes them, accesses data through a storage engine, and returns results while ensuring consistency and reliability.

MySQL — это реляционная система управления базами данных (СУБД) с открытым исходным кодом, использующая SQL.

Как работает:

Клиент-серверная архитектура
Приложение отправляет SQL-запросы серверу MySQL.

Обработка запроса
Парсинг → оптимизация → выполнение.

Движки хранения

InnoDB (по умолчанию) — транзакции, ACID

MyISAM — без транзакций (устаревший вариант)

Хранение данных
Таблицы, строки, столбцы и индексы.

Транзакции
Поддержка ACID через InnoDB.

Репликация
Поддержка масштабирования и отказоустойчивости.

Коротко: MySQL — это сервер, который обрабатывает SQL-запросы и управляет структурированными данными.

**2. What are the different data types available in MySQL?**

---

MySQL provides several categories of data types:

Numeric Types

TINYINT, SMALLINT, MEDIUMINT, INT, BIGINT

DECIMAL (fixed-point)

FLOAT, DOUBLE (floating-point)

BIT

Date and Time Types

DATE

TIME

DATETIME

TIMESTAMP

YEAR

String Types

CHAR (fixed length)

VARCHAR (variable length)

TEXT (TINYTEXT, TEXT, MEDIUMTEXT, LONGTEXT)

BLOB (binary data)

ENUM

SET

JSON Type

JSON (stores JSON documents)

Spatial Types

GEOMETRY

POINT

LINESTRING

POLYGON

Summary:

Numeric → numbers

Date/Time → temporal data

String → text/binary

JSON → semi-structured data

Spatial → geographic data

В MySQL есть несколько категорий типов данных:

Числовые
TINYINT, INT, BIGINT, DECIMAL, FLOAT, DOUBLE и др.

Дата и время
DATE, TIME, DATETIME, TIMESTAMP, YEAR.

Строковые
CHAR, VARCHAR, TEXT, BLOB, ENUM, SET.

JSON
Тип JSON для хранения документов.

Пространственные
GEOMETRY, POINT, POLYGON и др.

Итого: MySQL поддерживает числовые, временные, строковые, JSON и географические типы данных.

**3. How is MySQL different from other relational database systems?**

---

MySQL differs from other relational database systems in several ways:

Storage Engine Architecture
MySQL supports multiple storage engines (InnoDB, MyISAM, etc.), allowing flexibility in performance and features. Most other RDBMS use a single engine.

Performance Focus
MySQL is optimized for fast read-heavy web applications and is widely used in LAMP stacks.

Ease of Use
Known for simple setup, configuration, and administration compared to systems like Oracle.

Open Source
MySQL is open-source (with enterprise editions), making it popular for startups and web projects.

Replication & Scaling
Strong support for replication and read replicas, commonly used for horizontal scaling.

Feature Set Differences
Compared to PostgreSQL or Oracle:

Historically fewer advanced features (though much improved in recent versions)

Simpler optimizer and extensions

Different handling of strict standards compliance

Default Behavior
MySQL historically allowed more lenient SQL behavior (e.g., implicit type conversions), though modern versions enforce stricter modes.

In short:
MySQL is lightweight, easy to deploy, and optimized for web workloads, while other systems like PostgreSQL focus more on advanced features and strict standards compliance.

MySQL отличается от других СУБД:

Поддержка нескольких движков хранения.

Ориентация на веб-нагрузку и быстрые чтения.

Простота установки и администрирования.

Открытый исходный код.

Активное использование репликации.

Меньше «продвинутых» функций по сравнению с PostgreSQL/Oracle (исторически).

Более гибкое (иногда менее строгое) поведение SQL.

Коротко: MySQL — простая, производительная и популярная СУБД для веб-приложений.

**4. What is the difference between a database and a table in MySQL?**

---

A database in MySQL is a logical container that holds related objects such as tables, views, indexes, and procedures.

A table is a structured collection of data inside a database, organized into rows and columns.

Example:

CREATE DATABASE company;

USE company;

CREATE TABLE employees (
id INT PRIMARY KEY,
name VARCHAR(100),
salary DECIMAL(10,2)
);

Key differences:

Scope

Database → container of multiple tables and objects

Table → stores actual data

Structure

Database → organizational unit

Table → structured data format (rows & columns)

Relationship

A database can contain many tables

A table belongs to one database

In short:
A database is the storage container; a table is where the data is stored.

База данных — это логический контейнер для хранения таблиц и других объектов.

Таблица — это структура внутри базы данных, где хранятся данные в виде строк и столбцов.

Главное отличие:
База данных содержит таблицы, а таблицы содержат данные.

**5. What is a primary key and why is it used?**

---

A primary key is a column (or set of columns) that uniquely identifies each row in a table.

Key properties:

Must be unique

Cannot contain NULL values

Only one primary key per table (can be composite)

Example:

CREATE TABLE users (
id INT PRIMARY KEY,
name VARCHAR(100)
);

Why it is used:

Ensures uniqueness
Prevents duplicate records.

Maintains data integrity
Each row can be reliably identified.

Enables relationships
Used as a reference by foreign keys in other tables.

Improves performance
Primary keys are automatically indexed.

In short:
A primary key guarantees that every row in a table is uniquely identifiable.

Первичный ключ (Primary Key) — это поле (или набор полей), которое уникально идентифицирует строку в таблице.

Свойства:

Уникальность

Не допускает NULL

В таблице только один PK (может быть составным)

Зачем нужен:

Предотвращает дубликаты

Обеспечивает целостность данных

Используется для связей между таблицами

Автоматически индексируется

Коротко: первичный ключ делает каждую запись уникальной и однозначно определяемой.

**6. What is the purpose of the AUTO_INCREMENT attribute?**

---

AUTO_INCREMENT is a MySQL attribute used to automatically generate a unique numeric value for a column, usually a primary key.

Each time a new row is inserted, MySQL assigns the next sequential number automatically.

Example:

CREATE TABLE users (
id INT AUTO_INCREMENT PRIMARY KEY,
name VARCHAR(100)
);

If you insert:

INSERT INTO users (name) VALUES ('Alice');
INSERT INTO users (name) VALUES ('Bob');

MySQL automatically generates:

Alice → id = 1

Bob → id = 2

Purpose:

Automatically generate unique IDs

Prevent manual ID management

Ensure primary key uniqueness

Simplify inserts

In short:
AUTO_INCREMENT automatically creates sequential unique identifiers for new records.

AUTO_INCREMENT — это атрибут в MySQL, который автоматически генерирует уникальное числовое значение для столбца (обычно первичного ключа).

При каждой вставке новой строки значение увеличивается автоматически.

Назначение:

Автоматическая генерация уникальных ID

Исключение ручного управления идентификаторами

Обеспечение уникальности первичного ключа

Упрощение вставки данных

Коротко: AUTO_INCREMENT автоматически создаёт последовательные уникальные идентификаторы.

**7. What is a foreign key? Give an example.**

---

A foreign key is a column (or set of columns) in one table that references the primary key of another table.

Its purpose is to enforce referential integrity between related tables.

Example:

```sql
CREATE TABLE users (
id INT PRIMARY KEY,
name VARCHAR(100)
);

CREATE TABLE orders (
id INT PRIMARY KEY,
user_id INT,
FOREIGN KEY (user_id) REFERENCES users(id)
);
```

In this example:

users.id is the primary key

orders.user_id is the foreign key

Each order must reference an existing user

If you try to insert an order with a user_id that does not exist in users, the database will reject it.

In short:
A foreign key creates a relationship between tables and ensures data consistency.

Foreign Key (внешний ключ) — это столбец в одной таблице, который ссылается на первичный ключ другой таблицы.

Он обеспечивает ссылочную целостность данных.

В примере:

users.id — первичный ключ

orders.user_id — внешний ключ

Каждый заказ связан с существующим пользователем

Если пользователь не существует, вставка будет отклонена.

Коротко: внешний ключ связывает таблицы и гарантирует корректность данных.

**8. How can you retrieve current date and time in MySQL?**

---

In MySQL, you can retrieve the current date and time using built-in functions:

Current date and time: `SELECT NOW();`

Current date only: `SELECT CURDATE();`

Current time only: `SELECT CURTIME();`

Using standard SQL: `SELECT CURRENT_TIMESTAMP;`

These functions return the server's current date and time.

В MySQL текущую дату и время можно получить с помощью встроенных функций:

Текущая дата и время: `SELECT NOW();`

Только дата: `SELECT CURDATE();`

Только время: `SELECT CURTIME();`

Стандарт SQL: `SELECT CURRENT_TIMESTAMP;`

Эти функции возвращают текущие дату и время сервера MySQL.

**9. What is the purpose of the SELECT statement?**

---

The SELECT statement is used to retrieve data from one or more tables in a database.

It allows you to:

- Fetch specific columns

- Filter rows using WHERE

- Sort results using ORDER BY

- Group data using GROUP BY

- Join multiple tables

Example:

```sql
SELECT name, salary
FROM employees
WHERE salary > 5000
ORDER BY salary DESC;
```

Purpose:

- Read/query data

- Analyze and filter information

- Generate reports

In short: `SELECT` is used to query and retrieve data from a database.

Оператор `SELECT` используется для получения данных из одной или нескольких таблиц.

Он позволяет:

- Выбирать нужные столбцы

- Фильтровать строки (WHERE)

- Сортировать (ORDER BY)

- Группировать (GROUP BY)

- Объединять таблицы (JOIN)

Коротко: `SELECT` применяется для чтения и анализа данных в базе.

**10. What command is used to view all databases on a MySQL server?**

---

To view all databases on a MySQL server, use: `SHOW DATABASES`;

This command lists all databases that the current user has permission to see.

Чтобы посмотреть все базы данных на сервере MySQL, используется команда: SHOW DATABASES;

Она выводит список баз данных, доступных текущему пользователю.

**11. How do you optimize slow-running queries in MySQL?**

---

To optimize slow-running queries in MySQL:

Identify the slow queries

Enable and review the slow query log

Use `EXPLAIN / EXPLAIN ANALYZE` to see the execution plan

Add or improve indexes

Index columns used in `WHERE, JOIN, ORDER BY, GROUP BY`

Use composite indexes that match your filter order

Remove unused or redundant indexes

Rewrite the query

Avoid `SELECT *`

Filter early with WHERE

Use LIMIT when possible

Prefer EXISTS over IN for large subqueries (often)

Avoid functions on indexed columns in WHERE

Optimize joins

Ensure join keys are indexed

Reduce dataset before joining

Check join order and join type via EXPLAIN

Reduce sorting and temporary tables

Index for ORDER BY

Avoid large filesorts; watch for "Using temporary" / "Using filesort" in EXPLAIN

Update statistics and maintain tables

Run ANALYZE TABLE (and OPTIMIZE TABLE when appropriate)

Tune server configuration (if needed)

InnoDB buffer pool size, query cache (deprecated), connection limits, etc.

In short: measure (slow log + EXPLAIN) → index → rewrite → maintain → tune.

Чтобы ускорить медленные запросы в MySQL:

Найди "узкие места"
slow query log + EXPLAIN / EXPLAIN ANALYZE.

Добавь/исправь индексы
на WHERE/JOIN/ORDER BY/GROUP BY, часто нужны составные индексы.

Перепиши запрос
не `SELECT *`, фильтровать раньше, LIMIT, избегать функций по индексируемым полям.

Оптимизируй JOIN
индексы на ключах, уменьшай объём данных до JOIN.

Уменьши сортировки и временные таблицы
индексы под ORDER BY, смотри Using temporary / Using filesort.

Поддержка и статистика
ANALYZE TABLE, иногда OPTIMIZE TABLE.

Тюнинг сервера
InnoDB buffer pool и др.

Главное: замер → план → индексы → переписывание → обслуживание/тюнинг.

**12. What are indexes? How do they improve query performance?**

---

Indexes are special data structures that allow the database to find rows faster without scanning the entire table.

They work like an index in a book — instead of reading every page, the database jumps directly to the relevant data.

How they improve performance:

Faster lookups
Indexes speed up queries with WHERE conditions.

Faster joins
Indexed foreign keys improve JOIN operations.

Faster sorting
Indexes can optimize ORDER BY and sometimes GROUP BY.

Efficient range queries
B-tree indexes are optimized for ranges (>, <, BETWEEN).

Example: `CREATE INDEX idx_users_email ON users(email);`

Without an index → full table scan (slow for large tables).
With an index → index lookup (much faster).

Trade-offs:

Slower INSERT/UPDATE/DELETE (index maintenance)

Additional storage space

In short:
Indexes improve read performance by reducing the amount of data scanned, but add overhead to write operations.

Индексы — это специальные структуры данных, которые ускоряют поиск строк в таблице.

Они работают как оглавление в книге — позволяют быстро найти нужные данные без полного сканирования таблицы.

Как улучшают производительность:

Ускоряют фильтрацию (WHERE)

Ускоряют JOIN

Оптимизируют сортировку (ORDER BY)

Эффективны для диапазонов значений

Минусы:

Замедляют операции вставки и обновления

Требуют дополнительное место

Коротко: индексы ускоряют чтение данных за счёт уменьшения объёма сканируемых строк.

**13. Explain the concept of ACID properties in MySQL.**

---

Indexes are special data structures that allow the database to find rows faster without scanning the entire table.

They work like an index in a book — instead of reading every page, the database jumps directly to the relevant data.

How they improve performance:

Faster lookups
Indexes speed up queries with WHERE conditions.

Faster joins
Indexed foreign keys improve JOIN operations.

Faster sorting
Indexes can optimize ORDER BY and sometimes GROUP BY.

Efficient range queries
B-tree indexes are optimized for ranges (>, <, BETWEEN).

Example: `CREATE INDEX idx_users_email ON users(email);`

Without an index → full table scan (slow for large tables).
With an index → index lookup (much faster).

Trade-offs:

Slower INSERT/UPDATE/DELETE (index maintenance)

Additional storage space

In short:
Indexes improve read performance by reducing the amount of data scanned, but add overhead to write operations.

Индексы — это специальные структуры данных, которые ускоряют поиск строк в таблице.

Они работают как оглавление в книге — позволяют быстро найти нужные данные без полного сканирования таблицы.

Как улучшают производительность:

Ускоряют фильтрацию (WHERE)

Ускоряют JOIN

Оптимизируют сортировку (ORDER BY)

Эффективны для диапазонов значений

Минусы:

Замедляют операции вставки и обновления

Требуют дополнительное место

Коротко: индексы ускоряют чтение данных за счёт уменьшения объёма сканируемых строк.

**14. What is the difference between DELETE, TRUNCATE, and DROP?**

---

DELETE, TRUNCATE, and DROP are used to remove data, but they work differently.

DELETE - Removes selected rows from a table.

Can use WHERE

Transactional (can be rolled back)

Slower for large tables (row-by-row)

Example: `DELETE FROM users WHERE id = 5;`

TRUNCATE - Removes all rows from a table.

Cannot use WHERE

Faster (minimal logging)

Resets AUTO_INCREMENT

In MySQL, typically cannot be rolled back (DDL)

Example: `TRUNCATE TABLE users;`

DROP - Deletes the entire table (structure + data).

Removes table definition

Frees storage

Cannot be rolled back

Example: `DROP TABLE users;`

Key differences:

DELETE → removes rows

TRUNCATE → removes all rows quickly

DROP → removes the table itself

DELETE, TRUNCATE и DROP отличаются по уровню удаления данных.

DELETE — удаляет строки (можно с WHERE), медленнее, можно откатить.

TRUNCATE — быстро очищает всю таблицу, сбрасывает AUTO_INCREMENT.

DROP — удаляет таблицу полностью (структуру и данные).

Коротко:
DELETE — строки, TRUNCATE — все данные, DROP — вся таблица.

**15. How does MySQL handle transactions?**

---

MySQL handles transactions using the ACID principles (Atomicity, Consistency, Isolation, Durability). Transactions are supported mainly by the InnoDB storage engine. You start a transaction with START TRANSACTION (or BEGIN), make changes (INSERT, UPDATE, DELETE), and then either COMMIT to save them or ROLLBACK to undo them. Isolation levels (READ UNCOMMITTED, READ COMMITTED, REPEATABLE READ, SERIALIZABLE) control how transactions see each other's changes. MySQL uses row-level locking in InnoDB to ensure consistency and concurrency control.

MySQL работает с транзакциями на основе принципов ACID (атомарность, согласованность, изоляция, долговечность). Транзакции поддерживаются в основном движком InnoDB. Транзакция начинается с START TRANSACTION (или BEGIN), затем выполняются изменения (INSERT, UPDATE, DELETE), после чего используется COMMIT для сохранения или ROLLBACK для отката. Уровни изоляции (READ UNCOMMITTED, READ COMMITTED, REPEATABLE READ, SERIALIZABLE) определяют, как транзакции видят изменения друг друга. InnoDB использует блокировки на уровне строк для обеспечения согласованности и конкурентного доступа.

**16. What are the key differences between MyISAM and InnoDB storage engines?**

---

MyISAM vs InnoDB — key differences:

Transactions

InnoDB: Supports transactions (ACID), COMMIT and ROLLBACK.

MyISAM: Does not support transactions.

Locking

InnoDB: Row-level locking (better concurrency).

MyISAM: Table-level locking (less efficient under high load).

Foreign Keys

InnoDB: Supports foreign key constraints.

MyISAM: Does not support foreign keys.

Crash Recovery

InnoDB: Has crash recovery and better data integrity.

MyISAM: No automatic crash recovery.

Performance

InnoDB: Better for write-heavy and high-concurrency systems.

MyISAM: Faster for simple read-heavy workloads.

Ключевые различия MyISAM и InnoDB:

Транзакции

InnoDB: Поддерживает транзакции (ACID), COMMIT и ROLLBACK.

MyISAM: Не поддерживает транзакции.

Блокировки

InnoDB: Блокировки на уровне строк (лучше при высокой нагрузке).

MyISAM: Блокировки на уровне таблицы.

Внешние ключи

InnoDB: Поддерживает внешние ключи.

MyISAM: Не поддерживает.

Восстановление после сбоев

InnoDB: Есть механизм восстановления.

MyISAM: Нет автоматического восстановления.

Производительность

InnoDB: Лучше для систем с большим количеством записей и параллельных операций.

MyISAM: Быстрее при простых операциях чтения.

**17. What is Multi-Version Concurrency Control (MVCC) in MySQL?**

---

Multi-Version Concurrency Control (MVCC) in MySQL is a concurrency mechanism used by the InnoDB engine
to allow multiple transactions to access the same data without blocking each other.

Instead of locking rows for reads, InnoDB keeps multiple versions of a row. When a transaction updates a row,
the old version is kept in the undo log. Each transaction sees a consistent snapshot of the data based on its isolation level.

This allows:

- Non-blocking reads (reads don't block writes and writes don't block reads).

- Better performance and scalability under high concurrency.

- Consistent reads, especially in REPEATABLE READ isolation level.

MVCC (Multi-Version Concurrency Control) в MySQL — это механизм конкурентного доступа, используемый движком InnoDB, который позволяет нескольким транзакциям работать с одними и теми же данными без взаимных блокировок.

Вместо блокировки строк при чтении InnoDB хранит несколько версий строки. При обновлении старая версия сохраняется в undo log. Каждая транзакция видит согласованный «снимок» данных в зависимости от уровня изоляции.

Это обеспечивает:

Чтение без блокировок (чтения не блокируют записи и наоборот).

Лучшую производительность при высокой конкуренции.

Консистентное чтение, особенно при уровне изоляции REPEATABLE READ.

**18. How do triggers work and when would you use one?**

---

A trigger in MySQL is a database object that automatically executes when a specific event happens on a table (INSERT, UPDATE, or DELETE).

Triggers can run:

BEFORE the event (BEFORE INSERT/UPDATE/DELETE)

AFTER the event (AFTER INSERT/UPDATE/DELETE)

They are executed automatically and are tied to a specific table. Inside a trigger, you can access NEW values (for INSERT/UPDATE) and OLD values (for UPDATE/DELETE).

When to use triggers:

Auditing changes (e.g., logging updates or deletes).

Automatically updating related data (e.g., updating totals).

Enforcing complex business rules at the database level.

Maintaining history tables.

Триггер в MySQL — это объект базы данных, который автоматически выполняется при определённом событии в таблице (INSERT, UPDATE или DELETE).

Триггеры могут выполняться:

BEFORE (до операции)

AFTER (после операции)

Они привязаны к конкретной таблице. Внутри триггера доступны значения NEW (для INSERT/UPDATE) и OLD (для UPDATE/DELETE).

Когда использовать триггеры:

Для аудита изменений (логирование обновлений и удалений).

Для автоматического обновления связанных данных (например, пересчёт сумм).

Для реализации сложной бизнес-логики на уровне БД.

Для ведения истории изменений.

**19. What is the difference between statement-level and row-level triggers?**

---

Statement-level trigger

Executes once per SQL statement.

Does not run separately for each affected row.

Example: UPDATE users SET active = 0 → trigger runs once, even if 1000 rows are updated.

More efficient when you only need to react to the statement itself.

Row-level trigger

Executes once for each affected row.

If 1000 rows are updated, the trigger runs 1000 times.

Allows access to OLD and NEW values for each row.

Used when logic depends on individual row data (e.g., auditing changes per record).

Statement-level триггер

Выполняется один раз на SQL-оператор.

Не запускается отдельно для каждой строки.

Например: UPDATE users SET active = 0 → триггер выполнится один раз, даже если обновлено 1000 строк.

Подходит, когда нужно реагировать на сам факт выполнения запроса.

Row-level триггер

Выполняется для каждой затронутой строки.

Если обновлено 1000 строк — выполнится 1000 раз.

Позволяет работать с OLD и NEW значениями каждой строки.

Используется, когда логика зависит от конкретных данных строки (например, аудит изменений).

**20. How does MySQL implement full-text search?**

---

MySQL implements full-text search using FULLTEXT indexes. These indexes allow efficient text searching in large text columns (CHAR, VARCHAR, TEXT).

You create a FULLTEXT index on one or more columns, and then use the MATCH(column) AGAINST(expression) syntax to search.

There are three main search modes:

Natural Language Mode — searches by relevance score (default).

Boolean Mode — supports operators like +, -, \*, and phrase matching.

Query Expansion Mode — expands the search using related terms.

Full-text search is supported in InnoDB and MyISAM (modern MySQL versions). It is optimized for word-based searching, not for partial matches like '%word%'.

MySQL реализует полнотекстовый поиск с помощью FULLTEXT-индексов. Они позволяют эффективно искать текст в колонках типа CHAR, VARCHAR и TEXT.

Создаётся FULLTEXT-индекс для одной или нескольких колонок, после чего используется синтаксис MATCH(column) AGAINST(expression).

Основные режимы поиска:

Natural Language Mode — поиск по релевантности (по умолчанию).

Boolean Mode — поддержка операторов +, -, \*, поиск по фразам.

Query Expansion Mode — расширяет запрос связанными терминами.

Полнотекстовый поиск поддерживается в InnoDB и MyISAM (в современных версиях MySQL). Он оптимизирован для поиска по словам, а не для шаблонов вида '%word%'.

**21. What are common pitfalls with stored procedures?**

---

Common pitfalls with stored procedures in MySQL:

Overuse - Putting too much business logic in the database can make maintenance harder and reduce flexibility.

Performance issues - Complex procedures with loops or large data processing can be slower than equivalent application-level code.

Debugging difficulties - Limited debugging tools make it harder to trace errors inside procedures.

Version control challenges - Stored procedures live in the database, so managing changes alongside application code can be tricky.

Security risks - Improper handling of input parameters can lead to SQL injection if dynamic SQL is used.

Portability - Procedures are database-specific, so migrating to another DBMS may require rewriting them.

Распространённые проблемы с хранимыми процедурами в MySQL:

Чрезмерное использование — слишком много бизнес-логики в базе усложняет поддержку и снижает гибкость.

Проблемы с производительностью — сложные процедуры с циклами или обработкой больших данных могут работать медленнее, чем аналогичный код на стороне приложения.

Сложности отладки — ограниченные инструменты затрудняют поиск ошибок внутри процедур.

Контроль версий — процедуры хранятся в базе, и синхронизация изменений с кодом приложения может быть трудной.

Риски безопасности — неправильная обработка входных параметров при динамическом SQL может привести к SQL-инъекциям.

Портативность — процедуры специфичны для конкретной СУБД, при миграции на другую базу их часто нужно переписывать.

**22. You need to find products with above-average sales. How would you write this query?**

---

You can use a subquery to calculate the average sales and filter products above it:

```sql
SELECT *
FROM products
WHERE sales > (SELECT AVG(sales) FROM products);
```

Explanation:

The subquery (SELECT AVG(sales) FROM products) calculates the average sales.

The outer query selects all products with sales greater than this average.

Чтобы найти товары с продажами выше среднего, можно использовать подзапрос:

```sql
SELECT *
FROM products
WHERE sales > (SELECT AVG(sales) FROM products);
```

Пояснение:

Подзапрос (SELECT AVG(sales) FROM products) вычисляет среднее значение продаж.

Внешний запрос выбирает все товары, у которых продажи выше этого среднего.

**23. A table is growing too large to query efficiently. What steps would you take?**

---

When a table grows too large and queries become inefficient, you can take several steps:

1. Indexing

   Add proper indexes on columns used in WHERE, JOIN, ORDER BY, and GROUP BY clauses.

   Consider composite indexes if multiple columns are frequently queried together.

2. Partitioning

   Split the table into smaller partitions (range, list, hash, or key) to improve query performance.

   MySQL can scan only relevant partitions instead of the full table.

3. Archiving old data

   Move historical or rarely accessed data to an archive table or database.

   Reduces the size of the active table.

4. Denormalization / Summary tables

   Precompute aggregates or frequently queried summaries to avoid scanning large tables.

5. Optimize queries

   Use EXPLAIN to check query plans.

   Rewrite queries to be more efficient (avoid `SELECT *`, unnecessary joins, subqueries).

6. Hardware / configuration

   Increase memory, buffer pool (for InnoDB), or consider sharding if scale requires it.

Если таблица растёт слишком большой и запросы становятся медленными, можно предпринять следующие шаги:

1. Индексы

   Добавить индексы на колонки, используемые в WHERE, JOIN, ORDER BY, GROUP BY.

   Рассмотреть составные индексы для часто совместно используемых колонок.

2. Партиционирование

   Разбить таблицу на партиции (range, list, hash, key), чтобы ускорить запросы.

   MySQL будет сканировать только нужные партиции, а не всю таблицу.

3. Архивирование старых данных

   Перенести исторические или редко используемые данные в архивную таблицу или базу.

   Уменьшает размер активной таблицы.

4. Денормализация / таблицы-сводки

   Предварительно вычислять агрегаты или часто запрашиваемые сводные данные, чтобы не сканировать всю таблицу.

5. Оптимизация запросов

   Использовать EXPLAIN для анализа плана запроса.

   Переписать запросы эффективнее (избегать `SELECT *`, ненужных `JOIN` и подзапросов).

6. Аппаратное обеспечение / настройки

   Увеличить память, buffer pool (для InnoDB), или рассмотреть шардинг при больших масштабах.

**24. A user complains that data they updated isn't reflected. How would you troubleshoot?**

---

When a user reports that updated data isn't reflected, you can troubleshoot as follows:

1. Check transaction status

   Ensure the update was committed (COMMIT).

   If using transactions, uncommitted changes aren't visible to other sessions.

2. Verify isolation level / visibility

   High isolation levels (e.g., REPEATABLE READ, SERIALIZABLE) can make changes invisible until the transaction ends.

3. Confirm the update actually ran

   Check affected rows with SELECT or ROW_COUNT() after the update.

   Ensure the WHERE clause matched the intended rows.

4. Check caching layers

   Application-level caches (Redis, Memcached) or query caches may return stale data.

5. Verify the correct database / table

   Make sure the update was executed on the correct database, table, and environment (dev vs production).

6. Look for triggers or replication issues

   Triggers could overwrite changes.

   Replication lag in replicated setups can delay visibility.

Если пользователь жалуется, что обновлённые данные не отображаются, проверяйте так:

1. Статус транзакции

   Убедитесь, что изменения были зафиксированы через COMMIT.

   Незавершённые транзакции не видны другим сессиям.

2. Уровень изоляции / видимость

   Высокие уровни изоляции (REPEATABLE READ, SERIALIZABLE) могут скрывать изменения до конца транзакции.

3. Проверка выполнения обновления

   Используйте SELECT или ROW_COUNT(), чтобы убедиться, что обновление затронуло строки.

   Проверьте, что WHERE действительно совпадает с нужными строками.

4. Кэширование

   Приложенческий кэш (Redis, Memcached) или query cache могут возвращать устаревшие данные.

5. Правильная база и таблица

   Убедитесь, что обновление выполнялось в правильной базе, таблице и окружении (dev/prod).

6. Триггеры и репликация

   Триггеры могут перезаписывать изменения.

Задержка репликации в мастере/реплике может временно скрывать данные.

**25. Your database is experiencing lock contention. What would you do?**

---

When a database has lock contention, queries or transactions are waiting on each other, causing slow performance. Here's how to troubleshoot and resolve it:

1. Identify the locks

   Use SHOW ENGINE INNODB STATUS; to see current locks and transactions.

   Check INFORMATION_SCHEMA.INNODB_LOCKS and INNODB_LOCK_WAITS for blocked queries.

2. Analyze queries

   Find long-running or frequent queries holding locks.

   Use EXPLAIN to optimize queries, reduce full table scans, or avoid unnecessary writes.

3. Reduce transaction scope

   Keep transactions short — commit or rollback as soon as possible.

   Avoid user interaction or long processing inside transactions.

4. Use appropriate isolation levels

   Lower isolation levels (READ COMMITTED vs REPEATABLE READ) can reduce locking.

5. Optimize indexes

   Proper indexing can reduce the number of rows locked during updates/deletes.

6. Consider row-level locking

   Ensure InnoDB is used (row-level locks), not MyISAM (table-level locks).

7. Application-level strategies

   Retry logic for deadlocks.

   Queue or batch writes to reduce contention.

Если в базе данных наблюдается конкуренция за блокировки (lock contention), действуйте так:

1. Определите блокировки

   Используйте SHOW ENGINE INNODB STATUS; для просмотра текущих блокировок и транзакций.

   Проверьте INFORMATION_SCHEMA.INNODB_LOCKS и INNODB_LOCK_WAITS для блокированных запросов.

2. Проанализируйте запросы

   Найдите долгие или часто выполняемые запросы, удерживающие блокировки.

   Используйте EXPLAIN, оптимизируйте запросы, избегайте full table scan и ненужных обновлений.

3. Сократите транзакции

   Держите транзакции короткими — коммит или откат сразу после изменений.

   Избегайте пользовательского ввода или долгой обработки внутри транзакции.

4. Используйте подходящий уровень изоляции

   Более низкие уровни (READ COMMITTED вместо REPEATABLE READ) снижают конкуренцию за блокировки.

5. Оптимизируйте индексы

   Индексы уменьшают количество строк, блокируемых при UPDATE/DELETE.

6. Используйте блокировки на уровне строк

   InnoDB поддерживает row-level блокировки, а MyISAM — только table-level.

7. Стратегии на уровне приложения

   Логика повторных попыток при deadlock.

Пакетная обработка или очереди для уменьшения конкуренции.

**26. What are the different types of JOINs in MySQL and when to use them?**

---

Types of JOINs in MySQL:

1. INNER JOIN

   Returns only rows that have matching values in both tables.

   Use when you need data present in both tables.

   `SELECT * FROM orders o INNER JOIN customers c ON o.customer_id = c.id;`

2. LEFT JOIN (LEFT OUTER JOIN)

   Returns all rows from the left table and matching rows from the right table; NULL if no match.

   Use when you want all rows from the main table, even if related data is missing.

   `SELECT * FROM customers c LEFT JOIN orders o ON c.id = o.customer_id;`

3. RIGHT JOIN (RIGHT OUTER JOIN)

   Returns all rows from the right table and matching rows from the left table; NULL if no match.

   Less common; useful when the secondary table is the main focus.

   `SELECT * FROM orders o RIGHT JOIN customers c ON o.customer_id = c.id;`

4. FULL OUTER JOIN

   MySQL doesn't support it natively. Can be simulated with UNION of LEFT JOIN and RIGHT JOIN.

   Returns all rows from both tables, with NULLs where no match exists.

5. CROSS JOIN

   Returns the Cartesian product of two tables (all possible combinations).

   Use with caution, only when all combinations are required.

   `SELECT * FROM products p CROSS JOIN categories c;`

6. SELF JOIN

   A table joined with itself.

   Useful for hierarchical data or comparing rows within the same table.

```sql
SELECT e1.name AS Employee, e2.name AS Manager
FROM employees e1
LEFT JOIN employees e2 ON e1.manager_id = e2.id;
```

Типы JOIN в MySQL и когда использовать:

1. INNER JOIN

   Возвращает только строки с совпадениями в обеих таблицах.

   Используется, когда нужны данные, существующие в обеих таблицах.

2. LEFT JOIN (LEFT OUTER JOIN)

   Возвращает все строки из левой таблицы и совпадающие из правой; NULL, если совпадения нет.

   Используется, когда нужны все строки основной таблицы, даже если связанных данных нет.

3. RIGHT JOIN (RIGHT OUTER JOIN)

   Возвращает все строки из правой таблицы и совпадающие из левой; NULL, если совпадения нет.

   Реже используется, когда правая таблица — основной источник данных.

4. FULL OUTER JOIN

   В MySQL нет нативной поддержки; имитация через UNION LEFT JOIN и RIGHT JOIN.

   Возвращает все строки из обеих таблиц, с NULL там, где нет совпадений.

5. CROSS JOIN

   Возвращает декартово произведение двух таблиц (все возможные комбинации).

   Используется только когда нужны все комбинации.

6. SELF JOIN

   Таблица соединяется сама с собой.

Полезно для работы с иерархиями или сравнения строк внутри одной таблицы.

**How do you inspect the query execution plan in MySQL?**

You can inspect a query execution plan in MySQL using the EXPLAIN statement:

EXPLAIN SELECT \* FROM orders o
JOIN customers c ON o.customer_id = c.id
WHERE o.amount > 100;

Key points in the output:

id — the query sequence number.

select_type — type of SELECT (simple, primary, subquery).

table — the table being accessed.

type — join type / access method (ALL, index, ref, eq_ref).

possible_keys — which indexes could be used.

key — the actual index used.

rows — estimated rows scanned.

Extra — additional info (Using where, Using index, Using temporary, Using filesort).

You can also use EXPLAIN ANALYZE in MySQL 8+ to see actual execution times and rows, not just estimates.

В MySQL план выполнения запроса можно просмотреть с помощью EXPLAIN:

EXPLAIN SELECT \* FROM orders o
JOIN customers c ON o.customer_id = c.id
WHERE o.amount > 100;

Основные поля в выводе:

id — номер запроса в последовательности.

select_type — тип SELECT (simple, primary, subquery).

table — таблица, к которой идёт обращение.

type — тип соединения / способ доступа (ALL, index, ref, eq_ref).

possible_keys — индексы, которые могли бы быть использованы.

key — индекс, который реально использован.

rows — оценка количества проверяемых строк.

Extra — дополнительная информация (Using where, Using index, Using temporary, Using filesort).

В MySQL 8+ можно использовать EXPLAIN ANALYZE, чтобы увидеть реальные времена выполнения и количество обработанных строк, а не только оценки.

**27. What are temporary tables and how are they used?**

---

Temporary tables in MySQL are tables that exist only for the duration of a session. They are automatically dropped when the session ends or the connection is closed.

Key points:

- Created with CREATE TEMPORARY TABLE.

- Visible only to the session that created them; other sessions cannot see them.

- Can have indexes, primary keys, and constraints like regular tables.

- Useful for storing intermediate results or simplifying complex queries.

Example usage:

```sql
CREATE TEMPORARY TABLE temp_orders AS
SELECT customer_id, SUM(amount) AS total_amount
FROM orders
GROUP BY customer_id;

SELECT \* FROM temp_orders WHERE total_amount > 1000;

```

Use cases:

- Break down complex queries into simpler steps.

- Store intermediate aggregates for further processing.

- Reduce repeated calculations within a session.

- Support batch processing or reporting tasks without affecting main tables.

Временные таблицы в MySQL — это таблицы, существующие только в течение сессии. Они автоматически удаляются при завершении сессии или закрытии соединения.

Основные моменты:

- Создаются через CREATE TEMPORARY TABLE.

- Видимы только в той сессии, которая их создала; другие сессии не видят.

- Могут иметь индексы, первичные ключи и ограничения, как обычные таблицы.

Полезны для хранения промежуточных результатов или упрощения сложных запросов.

Сценарии применения:

- Разделение сложных запросов на простые шаги.

- Хранение промежуточных агрегатов для дальнейшей обработки.

- Сокращение повторных вычислений в рамках одной сессии.

- Поддержка пакетной обработки или отчётности без изменения основных таблиц.

**28. How does MySQL handle concurrency?**

---

MySQL handles concurrency mainly through locking and Multi-Version Concurrency Control (MVCC), especially in the InnoDB storage engine.

1. MVCC (InnoDB)

   Maintains multiple versions of rows so that reads don't block writes and writes don't block reads.

   Each transaction sees a consistent snapshot of the data based on its isolation level.

   Supports high concurrency without heavy locking for SELECT queries.

2. Locking

   Row-level locks in InnoDB: only the affected rows are locked during updates/deletes.

   Table-level locks in MyISAM: entire table is locked for writes, limiting concurrency.

   Deadlocks can occur when multiple transactions lock resources in conflicting order; MySQL detects and resolves them by rolling back one transaction.

3. Transaction isolation levels

   READ UNCOMMITTED, READ COMMITTED, REPEATABLE READ (default for InnoDB), SERIALIZABLE.

   Control visibility of uncommitted or concurrent changes, balancing consistency and concurrency.

4. Optimizations

   Proper indexing reduces the number of locked rows.

   Short transactions minimize contention.

Using MVCC with appropriate isolation levels improves read/write concurrency.

MySQL управляет параллелизмом в основном через блокировки и MVCC (Multi-Version Concurrency Control), особенно в InnoDB.

1. MVCC (InnoDB)

   Хранит несколько версий строк, чтобы чтение не блокировало запись и запись не блокировала чтение.

   Каждая транзакция видит согласованный «снимок» данных в зависимости от уровня изоляции.

   Позволяет высокой конкуренции без тяжёлых блокировок для SELECT-запросов.

2. Блокировки

   Блокировки на уровне строк (InnoDB): блокируются только затронутые строки при UPDATE/DELETE.

   Блокировки на уровне таблицы (MyISAM): блокируется вся таблица при записи, что ограничивает параллелизм.

   Могут возникать deadlock'и; MySQL их обнаруживает и решает, откатывая одну из транзакций.

3. Уровни изоляции транзакций

   READ UNCOMMITTED, READ COMMITTED, REPEATABLE READ (по умолчанию в InnoDB), SERIALIZABLE.

   Управляют видимостью незавершённых или параллельных изменений, балансируя согласованность и конкуренцию.

4. Оптимизации

   Правильные индексы уменьшают количество блокируемых строк.

   Короткие транзакции минимизируют конкуренцию.

Использование MVCC с подходящим уровнем изоляции улучшает параллельную работу чтений и записей.

**29. What are the different storage engines in MySQL?**

---

MySQL supports multiple storage engines, each with different features and use cases. The main ones are:

1. InnoDB

   Default engine in modern MySQL.

   Supports transactions (ACID), foreign keys, and row-level locking.

   MVCC for high concurrency and consistent reads.

   Good for write-heavy and transactional workloads.

2. MyISAM

   Older default before InnoDB.

   No transactions, table-level locking.

   Fast for read-heavy workloads.

   Supports full-text search (legacy versions).

3. MEMORY

   Stores data in RAM for very fast access.

   Data is lost when MySQL restarts.

   Useful for temporary tables, caching, or session storage.

4. CSV

   Stores data in CSV files.

   Easy to import/export, but slow and limited in features.

5. ARCHIVE

   Optimized for storing large amounts of rarely accessed data.

   Only supports INSERT and SELECT; no UPDATE/DELETE.

6. NDB / Cluster

   Used in MySQL Cluster setups.

   Supports distributed, highly available storage.

7. Other engines

   BLACKHOLE: Accepts writes but discards data (useful for replication setups).

   FEDERATED: Accesses tables on remote MySQL servers.

MySQL поддерживает несколько движков хранения с разными возможностями и сценариями применения. Основные:

1. InnoDB

   Движок по умолчанию в современных версиях.

   Поддерживает транзакции (ACID), внешние ключи, блокировки на уровне строк.

   MVCC обеспечивает высокую конкуренцию и согласованные чтения.

   Подходит для транзакционных и write-heavy нагрузок.

2. MyISAM

   Старый движок по умолчанию до InnoDB.

   Нет транзакций, блокировки на уровне таблицы.

   Быстрый для read-heavy нагрузок.

   Поддержка полнотекстового поиска (в старых версиях).

3. MEMORY

   Хранение данных в RAM для очень быстрого доступа.

   Данные теряются при перезапуске MySQL.

   Полезен для временных таблиц, кэшей или хранения сессий.

4. CSV

   Хранение данных в CSV-файлах.

   Легко импортировать/экспортировать, но медленно и с ограниченными возможностями.

5. ARCHIVE

   Оптимизирован для хранения больших объёмов редко используемых данных.

   Поддерживает только INSERT и SELECT; нет UPDATE/DELETE.

6. NDB / Cluster

   Используется в MySQL Cluster.

   Обеспечивает распределённое, высокодоступное хранение.

7. Другие движки

   BLACKHOLE: принимает записи, но отбрасывает данные (полезно для репликации).

   FEDERATED: доступ к таблицам на удалённых MySQL-серверах.

**30. What are the best practices for schema design in MySQL?**

---

Best practices for schema design in MySQL:

1. Normalize where appropriate

   Use 3NF (Third Normal Form) to reduce data redundancy.

   Denormalize only when performance requires it (e.g., summary tables).

2. Choose proper data types

   Use the smallest type that fits the data (e.g., INT vs BIGINT).

   Avoid VARCHAR for fixed-length data; use CHAR when appropriate.

   Use ENUM or SET for limited categorical values.

3. Use indexes wisely

   Index columns used in WHERE, JOIN, ORDER BY, GROUP BY.

   Avoid over-indexing — it slows down writes.

   Consider composite indexes for multi-column queries.

4. Define primary and foreign keys

   Always have primary keys for uniqueness and clustering (InnoDB).

   Use foreign keys to enforce referential integrity.

5. Optimize for queries

   Analyze expected queries and design tables to minimize costly joins.

   Consider indexing, partitioning, or materialized views for heavy reporting.

6. Handle NULLs and defaults carefully

   Avoid unnecessary NULLs in critical columns.

   Set sensible default values where applicable.

7. Plan for growth

   Use AUTO_INCREMENT carefully for high-scale tables.

   Consider partitioning for very large tables.

8. Use consistent naming conventions

   Consistent table, column, and index names improve readability and maintainability.

9. Document your schema

   Maintain ER diagrams and data dictionaries for future reference.

10. Monitor and refactor

    Periodically review schema performance and adjust indexes, types, or partitioning as needed.

Лучшие практики проектирования схемы в MySQL:

1. Нормализация

   Используйте 3NF, чтобы снизить избыточность данных.

   Денормализуйте только при необходимости для производительности (например, таблицы-сводки).

2. Правильный выбор типов данных

   Используйте минимально подходящий тип (INT вместо BIGINT, если достаточно).

   Не используйте VARCHAR для фиксированной длины; применяйте CHAR, если уместно.

   ENUM или SET для ограниченных категорий значений.

3. Разумное использование индексов

   Индексируйте колонки в WHERE, JOIN, ORDER BY, GROUP BY.

   Не создавайте слишком много индексов — это замедляет запись.

   Составные индексы для запросов по нескольким колонкам.

4. Определение первичных и внешних ключей

   Всегда задавайте первичные ключи для уникальности и кластеризации (InnoDB).

   Внешние ключи обеспечивают целостность ссылок.

5. Оптимизация под запросы

   Проектируйте таблицы с учётом типичных запросов, чтобы минимизировать дорогие JOIN.

   Для отчетности используйте индексы, партиционирование или materialized views.

6. Работа с NULL и значениями по умолчанию

   Избегайте ненужных NULL в критичных колонках.

   Устанавливайте разумные значения по умолчанию.

7. Планирование роста

   Осторожно используйте AUTO_INCREMENT для высоконагруженных таблиц.

   Для очень больших таблиц рассматривать партиционирование.

8. Единообразные имена

   Последовательные имена таблиц, колонок и индексов повышают читаемость и поддержку.

9. Документирование схемы

   Ведите ER-диаграммы и словари данных для справки.

10. Мониторинг и рефакторинг

    Периодически проверяйте производительность схемы и корректируйте индексы, типы и партиционирование при необходимости.

**31. How do you handle schema migrations in production?**

---

Handling schema migrations in production requires careful planning to avoid downtime and data loss. Here's a best-practice approach:

1. Use version-controlled migration scripts

   Maintain all schema changes as SQL scripts in source control.

   Each script should be idempotent or have a rollback plan.

2. Test thoroughly in staging

   Apply migrations to a staging or replica environment first.

   Verify queries, indexes, constraints, and application behavior.

3. Apply migrations in small, incremental steps

   Avoid massive schema changes in one go.

   Split complex migrations into multiple steps (e.g., add new column, backfill data, then remove old column).

4. Minimize downtime

   Use online schema changes when possible (e.g., pt-online-schema-change or native MySQL 8+ ALGORITHM=INPLACE).

   Avoid operations that lock tables for long periods.

5. Maintain backward compatibility

   Add new columns or tables without removing existing ones until the application is ready.

   Ensure both old and new application versions can work with the schema during the migration window.

6. Back up before changes

   Always take a backup of critical data before applying migrations.

7. Monitor after migration

   Check logs, query performance, and application behavior.

   Be ready to rollback quickly if issues occur.

8. Automate with migration tools

   Use tools like Flyway, Liquibase, or framework-specific migrations to track schema versions and apply them safely.

Обновление схемы в продакшене требует осторожности, чтобы избежать простоя и потери данных:

1. Скрипты с контролем версий

   Все изменения схемы храните как SQL-скрипты в системе контроля версий.

   Скрипты должны быть идемпотентными или иметь план отката.

2. Тестирование на staging

   Применяйте миграции сначала на staging или реплике.

   Проверяйте запросы, индексы, ограничения и работу приложения.

3. Малые пошаговые изменения

   Не делайте крупные изменения схемы за один раз.

   Разделяйте сложные миграции на шаги (например: добавить колонку, заполнить данными, удалить старую колонку).

4. Минимизация простоя

   Используйте онлайн изменения схемы (например, pt-online-schema-change или MySQL 8+ ALGORITHM=INPLACE).

   Избегайте операций, блокирующих таблицы надолго.

5. Обратная совместимость

   Добавляйте новые колонки или таблицы, не удаляя старые, пока приложение не готово.

   Убедитесь, что старые и новые версии приложения могут работать с новой схемой в период миграции.

6. Резервное копирование

   Всегда делайте бэкап критичных данных перед миграцией.

7. Мониторинг после миграции

   Проверяйте логи, производительность запросов и работу приложения.

   Будьте готовы быстро откатить изменения при проблемах.

8. Автоматизация через инструменты миграции

   Используйте Flyway, Liquibase или встроенные миграции фреймворков для безопасного контроля версий схемы.

**32. What are the key differences between OLTP and OLAP database structures?**

---

Key differences between OLTP and OLAP database structures:

- Feature OLTP (Online Transaction Processing) OLAP (Online Analytical Processing)

- Purpose Handles day-to-day transactional operations (INSERT, UPDATE, DELETE) Supports complex analysis and reporting (SELECT-heavy)

- Data Structure Highly normalized tables to reduce redundancy Often denormalized or in star/snowflake schemas for query performance

- Transaction Volume High number of short transactions Fewer transactions but queries are long and complex

- Query Type Simple, fast queries on small data sets Complex queries, aggregations, joins on large datasets

- Update Frequency Frequent inserts, updates, and deletes Mostly read-only; data is periodically loaded (ETL)

- Indexing Focused on fast lookups and primary key access Optimized for aggregations and multi-dimensional queries

- Schema Examples 3NF normalized schema Star schema, snowflake schema, fact and dimension tables

- Performance Focus Low latency, fast write performance High throughput for analytical queries

**Summary**: OLTP is designed for fast, transactional workloads with many small changes, while OLAP is designed for analytical workloads with complex queries on large, mostly read-only datasets.

Ключевые различия между OLTP и OLAP структурами баз данных:

- Особенность OLTP (Online Transaction Processing) OLAP (Online Analytical Processing)

- Назначение Обработка ежедневных транзакций (INSERT, UPDATE, DELETE) Анализ и отчётность (SELECT-запросы)

- Структура данных Сильно нормализованные таблицы для уменьшения избыточности Часто денормализованные, схемы звезды/снежинки для скорости запросов

- Объём транзакций Высокий, короткие транзакции Меньше транзакций, но длинные и сложные запросы

- Тип запросов Простые, быстрые запросы по небольшим наборам данных Сложные запросы с агрегациями и объединениями по большим данным

- Частота обновлений Частые вставки, обновления и удаления В основном чтение; данные загружаются периодически (ETL)

- Индексация Оптимизация под быстрый поиск по ключам Оптимизация под агрегации и многомерные запросы

- Примеры схем 3NF нормализованная схема Схема звезды, снежинки, факт и измерения

- Фокус производительности Низкая задержка, высокая скорость записи Высокая пропускная способность для аналитических запросов

OLTP ориентирован на быстрые транзакционные операции с частыми изменениями данных, тогда как OLAP — на аналитические задачи с сложными запросами по большим и преимущественно статичным наборам данных.

**33. What is the default port number for MySQL?**

---

The default port number for MySQL is 3306.

Порт по умолчанию для MySQL — 3306.

**34. What are constraints in MySQL?**

--

Constraints in MySQL are rules applied to table columns to enforce data integrity and consistency. They restrict the type of data that can be inserted or updated in a table.

Common types of constraints:

- PRIMARY KEY - Uniquely identifies each row in a table; cannot be NULL.

- FOREIGN KEY - Ensures referential integrity between tables; values must match a primary key in another table.

- UNIQUE - Ensures all values in a column or group of columns are unique.

- NOT NULL - Prevents a column from having NULL values.

- CHECK - Ensures that values meet a specific condition (supported in MySQL 8+).

- DEFAULT - Sets a default value for a column when none is provided.

- AUTO_INCREMENT - Automatically generates a unique number for each new row (usually used with primary keys).

Purpose:

- Maintain accurate and consistent data.

- Enforce business rules at the database level.

- Prevent invalid or duplicate data entry.

Ограничения (constraints) в MySQL — это правила для колонок таблицы, которые обеспечивают целостность и корректность данных. Они ограничивают тип данных, который можно вставлять или обновлять в таблице.

Основные типы ограничений:

- PRIMARY KEY - уникально идентифицирует каждую строку таблицы; не может быть NULL.

- FOREIGN KEY - обеспечивает ссылочную целостность между таблицами; значения должны соответствовать первичному ключу другой таблицы.

- UNIQUE - все значения в колонке или наборе колонок должны быть уникальными.

- NOT NULL - запрещает NULL значения.

- CHECK - проверяет выполнение определённого условия для значений (поддерживается в MySQL 8+).

- DEFAULT - задаёт значение по умолчанию, если оно не указано.

- AUTO_INCREMENT - автоматически генерирует уникальный номер для каждой новой строки (обычно используется с первичным ключом).

Назначение:

- Поддерживать точность и согласованность данных.

- Реализовывать бизнес-правила на уровне базы данных.

- Предотвращать ввод некорректных или дублирующихся данных.

**35. What is MySQL clustering?**

---

MySQL clustering refers to a setup where multiple MySQL servers work together to provide high availability, fault tolerance, and scalability. The most common implementation is MySQL NDB Cluster.

**Key points**: Data distribution: Data is automatically partitioned (sharded) across multiple nodes (data nodes).

**High availability**: If one node fails, other nodes continue serving requests with minimal downtime.

**Replication**: Nodes are synchronized to keep data consistent across the cluster. No single point of failure: Cluster nodes handle both storage and query processing.

**Use cases**: Real-time applications requiring continuous uptime, large-scale transactional systems, telecom, and financial services.

Components of MySQL NDB Cluster:

- Data nodes - store the actual data in memory and on disk.

- SQL nodes - run MySQL server instances and handle client queries.

- Management nodes - coordinate cluster configuration and monitoring.

Benefits:

- Fault tolerance and automatic failover.

- Horizontal scalability by adding more data nodes.

- Low-latency, real-time transactional processing.

Limitations:

- More complex to manage than single-server MySQL.

- Requires careful planning for memory and network resources.

**Кластеризация MySQL** — это конфигурация, в которой несколько серверов MySQL работают вместе для обеспечения высокой доступности, отказоустойчивости и масштабируемости. Наиболее распространённая реализация — MySQL NDB Cluster.

Основные моменты:

- Распределение данных: Данные автоматически делятся (шардируются) между узлами кластера.

- Высокая доступность: При сбое одного узла остальные продолжают обслуживать запросы с минимальным простоем.

- Репликация: Узлы синхронизируются, чтобы данные оставались согласованными. Отсутствие единой точки отказа: Узлы кластера обрабатывают и хранение данных, и выполнение запросов.

- Сценарии применения: Реальные приложения с требованиями к постоянной доступности, крупные транзакционные системы, телеком, финансы.

Компоненты MySQL NDB Cluster:

- Data nodes - хранят данные в памяти и на диске.

- SQL nodes - экземпляры MySQL, обрабатывающие клиентские запросы.

- Management nodes - управляют конфигурацией кластера и мониторингом.

Преимущества:

- Отказоустойчивость и автоматический failover.

- Горизонтальное масштабирование за счёт добавления узлов данных.

- Низкая задержка, обработка транзакций в реальном времени.

Ограничения:

- Более сложен в управлении, чем одиночный сервер MySQL.

- Требует тщательного планирования памяти и сетевых ресурсов.

**36, What are DDL, DML, and DCL?**

---

DDL, DML, and DCL are categories of SQL commands in MySQL (and other relational databases):

1. DDL — Data Definition Language
   - Used to define or modify database structures (tables, indexes, schemas).

   Commands: `CREATE, ALTER, DROP, TRUNCATE, RENAME.`

   Affects the schema rather than data content.

2. DML — Data Manipulation Language

   Used to manipulate the data stored in tables.

   Commands: `SELECT, INSERT, UPDATE, DELETE, REPLACE.`

   Operates on the data without changing the table structure.

3. DCL — Data Control Language

   Used to control access and permissions to the database.

   Commands: `GRANT, REVOKE`.

   Manages user privileges and security.

**Summary**:

    DDL → Schema changes.

    DML → Data changes.

    DCL → Access control.

    DDL, DML и DCL — это категории SQL-команд в MySQL (и других СУБД):

1. DDL — язык определения данных (Data Definition Language)

   Используется для создания или изменения структуры базы данных (таблиц, индексов, схем).

   Команды: `CREATE, ALTER, DROP, TRUNCATE, RENAME`.

   Влияет на структуру, а не на содержимое данных.

2. DML — язык манипулирования данными (Data Manipulation Language)

   Используется для работы с данными в таблицах.

   Команды: `SELECT, INSERT, UPDATE, DELETE, REPLACE`.

   Изменяет данные, не затрагивая структуру таблиц.

3. DCL — язык управления доступом (Data Control Language)

   Используется для управления доступом и правами пользователей.

   Команды: GRANT, REVOKE.

   Управляет привилегиями и безопасностью.

**Итог**:

    DDL → изменения схемы.

    DML → изменения данных.

    DCL → контроль доступа.

**37. What is the MySQL binary log, and how do you use it?**

---

MySQL binary log is a file (or set of files) that records all changes to the database that modify data or structure, such as INSERT, UPDATE, DELETE, and DDL statements. It is mainly used for replication and recovery.

**Key points**:

- Contains events representing database changes, in order of execution.

- Does not log SELECT statements.

- Helps replicate changes from a master to one or more slaves in MySQL replication.

- Useful for point-in-time recovery after a backup.

**Using the binary log**:

Enable binary logging in my.cnf (MySQL configuration):

```log
[mysqld]
log-bin=mysql-bin
server-id=1
```

View binary logs: `SHOW BINARY LOGS;`

Inspect the contents: `mysqlbinlog mysql-bin.000001`

Replay changes:  
 For recovery: pipe output of mysqlbinlog into MySQL to reapply events. `mysqlbinlog mysql-bin.000001 | mysql -u root -p`

Replication: Binary log events are sent to slave servers to keep them in sync with the master.

Summary: Tracks all data-modifying statements.

Essential for replication and point-in-time recovery.

Can be inspected and replayed using mysqlbinlog.

Бинарный лог MySQL — это файл (или набор файлов), который фиксирует все изменения в базе данных, такие как INSERT, UPDATE, DELETE и DDL-команды. Основное назначение — репликация и восстановление.

Основные моменты:

- Содержит события, отражающие изменения в порядке выполнения.

- Не фиксирует SELECT-запросы.

- Используется для репликации с мастера на слейвы.

- Полезен для восстановления до определённого момента времени после резервного копирования.

Использование бинарного лога: Включение логирования в my.cnf:

```log
[mysqld]
log-bin=mysql-bin
server-id=1
```

Просмотр логов: `SHOW BINARY LOGS;`

Просмотр содержимого: `mysqlbinlog mysql-bin.000001`

Воспроизведение изменений: Для восстановления: вывод mysqlbinlog можно направить в MySQL.

`mysqlbinlog mysql-bin.000001 | mysql -u root -p`

Репликация: События из бинарного лога отправляются на слейвы для синхронизации с мастером.

Итог:

- Фиксирует все изменения данных.

- Необходим для репликации и восстановления до определённого момента.

- Можно просматривать и воспроизводить с помощью mysqlbinlog.

**38. What is the difference between a clustered and a non-clustered index?**

---

Clustered vs Non-Clustered Index in MySQL:

- Feature Clustered Index Non-Clustered Index

- Storage The table's data is physically stored in the order of the index. The table's data is stored separately; index contains pointers to the data.

- Primary Key In InnoDB, the primary key is always a clustered index. Non-primary key indexes are non-clustered.

- Number per table Only one clustered index per table (because data can be ordered only one way). Multiple non-clustered indexes allowed per table.

- Lookup speed Fast for range queries or lookups by the indexed column. Slightly slower; requires an extra lookup to fetch actual row data.

- Insert/Update impact Modifying data can require reorganizing the table to maintain order. Less impact on table data; only the index tree is updated.

**Summary**:

- Clustered index determines the physical order of rows; ideal for primary keys and range queries.

- Non-clustered index is separate from table data; useful for secondary columns to speed up queries without reorganizing the table.

Кластерный vs некластерный индекс в MySQL:

- Особенность Кластерный индекс Некластерный индекс

- Хранение Данные таблицы физически упорядочены по индексу. Данные таблицы хранятся отдельно; индекс содержит указатели на строки.

- Первичный ключ В InnoDB первичный ключ всегда является кластерным индексом. Индексы на неключевых колонках — некластерные.
  Количество на таблицу Только один кластерный индекс (данные можно упорядочить только одним способом). Можно иметь несколько некластерных индексов.

- Скорость поиска Быстро для диапазонных запросов или поиска по индексированному столбцу. Чуть медленнее; требуется дополнительное обращение к данным строки.

- Влияние на вставку/обновление Изменение данных может потребовать перестройки таблицы для поддержания порядка. Меньшее влияние; обновляется только структура индекса.

Итог:

- Кластерный индекс задаёт физический порядок строк; хорошо подходит для первичных ключей и диапазонных запросов.

- Некластерный индекс хранится отдельно; ускоряет доступ по второстепенным колонкам без перестройки таблицы.

**39. What is the difference between an inner join and a natural join?**

---

Inner Join vs Natural Join in MySQL:

1. INNER JOIN
   Combines rows from two tables based on a specified condition (usually using ON).

   Only rows that satisfy the join condition appear in the result.

   Column names do not need to match; you explicitly define the joining columns.

```sql
SELECT o.id, c.name
FROM orders o
INNER JOIN customers c ON o.customer_id = c.id;
```

2. NATURAL JOIN

   Automatically joins two tables using all columns with the same name in both tables.

   Only rows with matching values in these same-named columns appear.

   No ON clause needed, but you have less control over which columns are used.

```sql
SELECT *
FROM orders
NATURAL JOIN customers;
```

Key Differences:

- Feature INNER JOIN NATURAL JOIN

- Join condition Explicitly specified with ON or USING Implicitly based on columns with the same name

- Control High; you choose which columns to join Low; joins all columns with matching names automatically

- Risk Safe; nothing unexpected if you specify columns Can produce unexpected results if tables have multiple same-named columns

- Usage Most common join type Rarely used in production due to implicit behavior

**Summary**:

- INNER JOIN = controlled join by specific columns.

- NATURAL JOIN = automatic join on same-named columns; less explicit, riskier.

- INNER JOIN vs NATURAL JOIN в MySQL:

1. INNER JOIN

   Объединяет строки двух таблиц по указанному условию (через ON).

   В результат попадают только строки, удовлетворяющие условию.

   Имена колонок могут не совпадать; вы сами указываете, какие колонки соединять.

2. NATURAL JOIN

   Автоматически соединяет таблицы по всем колонкам с одинаковыми именами.

   В результат попадают только строки с совпадающими значениями в этих колонках.

   ON не нужен, но вы меньше контролируете, какие колонки участвуют в соединении.

Основные различия:

- Особенность INNER JOIN NATURAL JOIN

- Условие соединения Явно указывается через ON или USING Неявно по колонкам с одинаковыми именами

- Контроль Высокий; вы сами выбираете колонки Низкий; автоматически все совпадающие по имени колонки

- Риск Безопасно, если указаны нужные колонки Может давать неожиданные результаты при нескольких одинаковых колонках

- Использование Наиболее распространённый тип соединения Редко используется в продакшене из-за неявного поведения

Итог:

- INNER JOIN = контролируемое соединение по конкретным колонкам.

- NATURAL JOIN = автоматическое соединение по колонкам с одинаковыми именами; менее явное, с потенциальными рисками.

**39. What is a temporary table, and how do you create one in MySQL?**

---

A **temporary table** in MySQL is a table that exists only for the duration of a session. It is automatically dropped when the session ends or the connection is closed. Temporary tables are useful for storing intermediate results, simplifying complex queries, or caching data during a session.

Key points:

- Visible only to the session that created it.

- Can have indexes, primary keys, and constraints like regular tables.

- Useful for breaking complex queries into smaller steps or aggregating intermediate results.

Creating a temporary table:

```sql
CREATE TEMPORARY TABLE temp_orders (
order_id INT PRIMARY KEY,
customer_id INT,
total_amount DECIMAL(10,2)
);
```

Populating and using it:

```sql
INSERT INTO temp_orders (order_id, customer_id, total_amount)
SELECT id, customer_id, amount
FROM orders
WHERE amount > 100;
SELECT \* FROM temp_orders;
```

Notes:

- The table disappears automatically at the end of the session.

- Multiple sessions can create temporary tables with the same name without conflict.

**Временная таблица в MySQL** — это таблица, которая существует только в течение сессии. Она автоматически удаляется после завершения сессии или закрытия соединения. Временные таблицы полезны для хранения промежуточных результатов, упрощения сложных запросов или кэширования данных на время сессии.

Основные моменты:

- Видима только для сессии, которая её создала.

- Может иметь индексы, первичные ключи и ограничения, как обычная таблица.

- Удобна для разбиения сложных запросов на шаги или агрегирования промежуточных данных.

**Примечания**:

- Таблица автоматически исчезает после окончания сессии.

- Несколько сессий могут создавать временные таблицы с одинаковым именем без конфликта.
