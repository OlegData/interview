# Postgres

**1. What is PostgreSQL? What do you know about PostgreSQL?**

---

PostgreSQL is an open-source relational database management system (RDBMS). It supports SQL standards and advanced features like transactions (ACID compliance), indexing, constraints, and foreign keys. PostgreSQL supports complex data types such as JSON, arrays, UUID, and custom types. It is known for reliability, extensibility, performance, and strong support for concurrency (MVCC).

PostgreSQL — это открытая реляционная система управления базами данных (СУБД). Она поддерживает стандарт SQL и расширенные возможности, такие как транзакции (ACID), индексы, ограничения и внешние ключи. PostgreSQL работает со сложными типами данных, включая JSON, массивы, UUID и пользовательские типы. Она известна своей надёжностью, расширяемостью, производительностью и поддержкой конкурентного доступа (MVCC).

**2. What are the various features and advantages of PostgreSQL?**

---

PostgreSQL supports full ACID compliance, ensuring reliable transactions and data integrity. It offers advanced indexing methods (B-tree, GIN, GiST), constraints, triggers, and stored procedures. It supports rich data types like JSON/JSONB, arrays, UUID, and custom types. PostgreSQL provides MVCC for high concurrency without heavy locking. It is open-source, highly extensible, and supports replication and partitioning.

PostgreSQL поддерживает полную ACID-согласованность, обеспечивая надёжные транзакции и целостность данных. Он предлагает продвинутые методы индексирования (B-tree, GIN, GiST), ограничения, триггеры и хранимые процедуры. Поддерживает сложные типы данных, такие как JSON/JSONB, массивы, UUID и пользовательские типы. PostgreSQL использует MVCC для высокой конкурентности без жёстких блокировок. Это open-source система с высокой расширяемостью, поддержкой репликации и партиционирования.

**3. What are the key differences between MySQL and PostgreSQL? Which Open Source Database to Choose? Which one is best?**

---

Key differences between MySQL and PostgreSQL

- PostgreSQL is more feature-rich and standards-compliant, with strong support for complex queries, advanced indexing, JSONB, window functions, and extensibility.

- MySQL is often considered simpler, easier to set up, and historically popular for web applications (especially LAMP stack).

- PostgreSQL has stronger support for ACID compliance and advanced concurrency (MVCC implementation).

- MySQL can be faster for simple read-heavy workloads, while PostgreSQL performs better for complex queries and data integrity–focused systems.

Which one to choose?

- Choose PostgreSQL if you need complex queries, advanced features, strong data integrity, or plan to scale and extend the system.

- Choose MySQL if you need a simple, lightweight solution for straightforward CRUD applications.

- There is no universal "best" database — it depends on your project requirements.

Ключевые различия MySQL и PostgreSQL

- PostgreSQL более функционален и ближе к стандарту SQL, поддерживает сложные запросы, продвинутые индексы, JSONB, оконные функции и расширяемость.

- MySQL считается более простым и лёгким в настройке, исторически популярен для веб-приложений (LAMP-стек).

- PostgreSQL обеспечивает более строгую ACID-согласованность и продвинутую модель конкурентности (MVCC).

- MySQL может быть быстрее при простых read-heavy нагрузках, тогда как PostgreSQL лучше справляется со сложной логикой и требованиями к целостности данных.

Что выбрать?

- PostgreSQL — если нужны сложные запросы, расширенные возможности и высокая надёжность данных.

- MySQL — если нужен простой и лёгкий вариант для базовых CRUD-приложений.

- Универсальной базы нет — выбор зависит от задач проекта.

**4. What are the various PostgreSQL database administration commands and tools?**

---

Common PostgreSQL administration commands and tools include:

- psql — command-line client for running queries and managing databases.

- createdb / dropdb — create and delete databases.

- createuser / dropuser — manage database users and roles.

- pg_dump / pg_restore — backup and restore databases.

- pg_ctl — start, stop, and manage the PostgreSQL server.

- psql meta-commands like \l, \dt, \du — list databases, tables, and users.

Основные команды и инструменты администрирования PostgreSQL:

- psql — консольный клиент для выполнения запросов и управления базами.

- createdb / dropdb — создание и удаление баз данных.

- createuser / dropuser — управление пользователями и ролями.

- pg_dump / pg_restore — резервное копирование и восстановление.

- pg_ctl — запуск, остановка и управление сервером PostgreSQL.

- Meta-команды psql, например \l, \dt, \du — просмотр баз данных, таблиц и пользователей.

**5. PostgreSQL database general concepts**

---

PostgreSQL is a relational database based on tables (relations) organized inside schemas and databases. Data is stored in rows and columns, and tables can be linked using primary keys and foreign keys. It follows ACID principles to guarantee transaction reliability. PostgreSQL uses MVCC (Multi-Version Concurrency Control) to handle concurrent transactions efficiently. It supports indexes, constraints, views, triggers, functions, and stored procedures.

PostgreSQL — это реляционная база данных, основанная на таблицах (relations), которые организованы в схемы и базы данных. Данные хранятся в строках и столбцах, а таблицы связываются через primary key и foreign key. Система придерживается принципов ACID для обеспечения надёжности транзакций. PostgreSQL использует MVCC (Multi-Version Concurrency Control) для эффективной работы с конкурентными транзакциями. Поддерживаются индексы, ограничения, представления (views), триггеры, функции и хранимые процедуры.

**6. What is PostgreSQL and list down its main features?**

---

PostgreSQL is an open-source relational database management system (RDBMS) known for reliability and advanced features.

Main features include:

- ACID-compliant transactions for strong data integrity.

- Advanced indexing (B-tree, GIN, GiST) and query optimization.

- Support for complex data types like JSON/JSONB, arrays, UUID, and custom types.

- MVCC for high concurrency without heavy locking.

- Extensibility with custom functions, extensions, and procedural languages.

- Replication, partitioning, and high availability support.

PostgreSQL — это открытая реляционная система управления базами данных (СУБД), известная своей надёжностью и расширенными возможностями.

Основные особенности:

- ACID-транзакции для обеспечения целостности данных.

- Продвинутые индексы (B-tree, GIN, GiST) и оптимизация запросов.

- Поддержка сложных типов данных: JSON/JSONB, массивы, UUID и пользовательские типы.

- MVCC для высокой конкурентности без жёстких блокировок.

- Расширяемость через функции, расширения и процедурные языки.

- Поддержка репликации, партиционирования и высокой доступности.

**7. How does PostgreSQL differ from other database management systems?**

---

PostgreSQL stands out for its strong standards compliance and advanced SQL support. It offers full ACID compliance and a robust MVCC implementation for high concurrency. Unlike many systems, it supports advanced data types like JSONB, arrays, and custom types natively. It is highly extensible, allowing custom functions, operators, and extensions. Compared to some DBMS, it focuses more on data integrity and complex queries rather than just simple CRUD performance.

PostgreSQL отличается строгим соблюдением стандартов SQL и расширенной поддержкой возможностей языка. Он обеспечивает полную ACID-согласованность и надёжную реализацию MVCC для высокой конкурентности. В отличие от многих СУБД, PostgreSQL нативно поддерживает сложные типы данных, такие как JSONB, массивы и пользовательские типы. Он обладает высокой расширяемостью — можно добавлять собственные функции, операторы и расширения. По сравнению с некоторыми СУБД, PostgreSQL больше ориентирован на целостность данных и сложные запросы, а не только на простые CRUD-операции.

**8. What are the advantages of using PostgreSQL?**

---

PostgreSQL offers strong ACID compliance, ensuring reliable transactions and data integrity. It supports advanced SQL features, complex queries, and powerful indexing mechanisms. It provides rich data types like JSON/JSONB, arrays, UUID, and custom types. PostgreSQL uses MVCC for high concurrency without heavy locking. It is open-source, highly extensible, and supports replication, partitioning, and high availability.

PostgreSQL обеспечивает строгую ACID-согласованность, гарантируя надёжные транзакции и целостность данных. Он поддерживает расширенные возможности SQL, сложные запросы и мощные механизмы индексирования. Предоставляет богатые типы данных: JSON/JSONB, массивы, UUID и пользовательские типы. PostgreSQL использует MVCC для высокой конкурентности без жёстких блокировок. Это open-source система с высокой расширяемостью, поддержкой репликации, партиционирования и высокой доступности.

**9. What is a table in PostgreSQL?**

---

A table in PostgreSQL is a structured collection of data organized into rows and columns. Each table represents an entity, and each row represents a record. Columns define the data types and constraints for stored values. Tables can be linked to other tables using primary keys and foreign keys.

Таблица в PostgreSQL — это структурированная коллекция данных, организованная в строки и столбцы. Каждая таблица представляет сущность, а каждая строка — отдельную запись. Столбцы определяют типы данных и ограничения для хранимых значений. Таблицы могут быть связаны между собой через primary key и foreign key.

**10. What is a schema in PostgreSQL?**

---

A schema in PostgreSQL is a logical container that organizes database objects like tables, views, functions, and indexes. It helps group related objects and avoid name conflicts within the same database. Schemas allow better structure, security control, and namespace management. For example, the default schema is public.

Схема в PostgreSQL — это логический контейнер для объектов базы данных, таких как таблицы, представления, функции и индексы. Она помогает группировать связанные объекты и избегать конфликтов имён внутри одной базы. Схемы улучшают структуру, управление доступом и организацию пространств имён. По умолчанию используется схема public.

**11. How do you create a database in PostgreSQL?**

---

You can create a database in PostgreSQL using the SQL command: `CREATE DATABASE my_database;` You can run this command inside the psql client. Alternatively, you can use the command-line tool: `createdb my_database`. In pgAdmin, you can create a database through the graphical interface.

Создать базу данных в PostgreSQL можно с помощью SQL-команды: `CREATE DATABASE my_database;` Её можно выполнить в клиенте psql. Также можно использовать командную утилиту: `createdb my_database` В pgAdmin базу данных можно создать через графический интерфейс.

**12. How do you create a table in PostgreSQL?**

---

You create a table in PostgreSQL using the CREATE TABLE statement.

Example:

```sql
CREATE TABLE users (
id SERIAL PRIMARY KEY,
name VARCHAR(100),
email VARCHAR(255) UNIQUE,
created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

You define column names, data types, and optional constraints like PRIMARY KEY, UNIQUE, or DEFAULT.

Таблицу в PostgreSQL создают с помощью команды CREATE TABLE.

Пример:

```sql
CREATE TABLE users (
id SERIAL PRIMARY KEY,
name VARCHAR(100),
email VARCHAR(255) UNIQUE,
created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

При создании указывают имена столбцов, типы данных и при необходимости ограничения, такие как PRIMARY KEY, UNIQUE или DEFAULT.

**13. What are functions in PostgreSQL?**

---

Functions in PostgreSQL are reusable database routines that perform specific operations and return a value. They can contain SQL statements, procedural logic, variables, and control structures. Functions can accept parameters and return a single value or a result set. They are often written in PL/pgSQL but can also use other supported languages.

Функции в PostgreSQL — это переиспользуемые процедуры базы данных, которые выполняют определённые операции и возвращают значение. Они могут содержать SQL-запросы, процедурную логику, переменные и управляющие конструкции. Функции могут принимать параметры и возвращать одно значение или набор строк. Чаще всего пишутся на PL/pgSQL, но могут использовать и другие поддерживаемые языки.

**14. What is the maximum table size in PostgreSQL?**

---

In PostgreSQL, the theoretical maximum table size is about 32 TB per table by default. This limit comes from the maximum size of a single table file (1 GB per segment, up to 32,000 segments). The actual size can be larger depending on configuration, table partitioning, and storage setup. In practice, table size is usually limited by disk capacity rather than PostgreSQL itself.

В PostgreSQL теоретический максимальный размер одной таблицы составляет примерно 32 ТБ по умолчанию. Это ограничение связано с максимальным размером файлов таблицы (до 1 ГБ на сегмент и до 32 000 сегментов). Фактически размер может быть больше при использовании партиционирования и соответствующей конфигурации хранения. На практике ограничение чаще определяется объёмом дискового пространства, а не самой СУБД.

**15. What does command enable-debug mean in PostgreSQL?**

---

PostgreSQL does not have a standard SQL command called enable-debug. Debugging in PostgreSQL is usually controlled through configuration parameters in postgresql.conf, such as log_min_messages, debug_print_parse, debug_print_plan, or debug_print_rewritten. You enable debugging by changing these settings and restarting or reloading the server. There is also a build-time option (--enable-debug) when compiling PostgreSQL from source, which enables additional debugging symbols.

В PostgreSQL нет стандартной SQL-команды enable-debug. Отладка настраивается через параметры конфигурации в postgresql.conf, например log_min_messages, debug_print_parse, debug_print_plan или debug_print_rewritten. Для включения отладки изменяют параметры и перезапускают или перезагружают сервер.
Также существует опция сборки (--enable-debug) при компиляции PostgreSQL из исходников, которая добавляет дополнительные отладочные возможности.

**16. What are the different data types supported by PostgreSQL?**

---

PostgreSQL supports a wide range of data types:

Numeric types — smallint, integer, bigint, decimal, numeric, real, double precision, serial.

Character types — char, varchar, text.

Boolean type — boolean.

Date and time types — date, time, timestamp, timestamptz, interval.

Binary data — bytea.

UUID type — uuid.

JSON types — json and jsonb.

Array types — any data type can be stored as an array.

Geometric types — point, line, circle, etc.

Custom types — enums, composite types, and user-defined types.

PostgreSQL поддерживает широкий набор типов данных:

Числовые типы — smallint, integer, bigint, decimal, numeric, real, double precision, serial.

Строковые типы — char, varchar, text.

Логический тип — boolean.

Дата и время — date, time, timestamp, timestamptz, interval.

Бинарные данные — bytea.

UUID — uuid.

JSON-типы — json и jsonb.

Массивы — любой тип может быть представлен как массив.

Геометрические типы — point, line, circle и другие.

Пользовательские типы — enum, composite types и другие пользовательские определения.

**17. How do you insert data into a table in PostgreSQL?**

---

You insert data into a table in PostgreSQL using the INSERT INTO statement.

```sql
INSERT INTO users (name, email)
VALUES ('John', 'john@example.com
');
```

You can insert multiple rows at once by separating values with commas. You can also insert data from another table using `INSERT INTO ... SELECT`.

Данные в таблицу PostgreSQL вставляют с помощью команды `INSERT INTO`. Можно вставлять несколько строк, перечисляя значения через запятую.
Также можно вставлять данные из другой таблицы с помощью `INSERT INTO ... SELECT`.

**18. How do you update data in a table in PostgreSQL?**

---

You update data in PostgreSQL using the UPDATE statement.

```sql
UPDATE users
SET email = 'new@example.com
'
WHERE id = 1;
```

The WHERE clause is important to specify which rows should be updated. Without WHERE, all rows in the table will be updated.

Обновление данных в PostgreSQL выполняется с помощью команды UPDATE. Условие WHERE важно для указания конкретных строк. Без WHERE будут обновлены все строки таблицы.

**19. What do you understand by pgadmin?**

---

pgAdmin is a graphical administration and management tool for PostgreSQL. It provides a user-friendly interface to create databases, tables, users, and run SQL queries. It allows monitoring server activity, managing backups, and configuring database settings. pgAdmin can be used as a desktop application or via a web interface.

pgAdmin — это графический инструмент администрирования и управления PostgreSQL. Он предоставляет удобный интерфейс для создания баз данных, таблиц, пользователей и выполнения SQL-запросов. Позволяет мониторить активность сервера, управлять резервным копированием и настраивать параметры базы данных. pgAdmin может работать как настольное приложение или через веб-интерфейс.

**20. How can you change a user's password in PostgreSQL?**

---

You can change a user's password in PostgreSQL using the ALTER USER or ALTER ROLE command.`ALTER USER username WITH PASSWORD 'new_password';` You must have sufficient privileges (usually superuser or the same user). The same can be done in psql or through pgAdmin's user properties.

Изменить пароль пользователя в PostgreSQL можно с помощью команды ALTER USER или ALTER ROLE. Для этого нужны соответствующие права (обычно superuser или сам пользователь). Это можно сделать через psql или через настройки пользователя в pgAdmin.

**21. What are the different data types in PostgreSQL?**

---

PostgreSQL supports many categories of data types:

Numeric types — smallint, integer, bigint, numeric, decimal, real, double precision, serial.

Character types — char, varchar, text.

Boolean type — boolean.

Date and time types — date, time, timestamp, timestamptz, interval.

Binary type — bytea.

UUID — uuid.

JSON types — json and jsonb.

Array types — arrays of any supported data type.

Geometric types — point, line, circle, polygon.

Custom types — enum, composite types, and user-defined types.

PostgreSQL поддерживает разные категории типов данных:

Числовые типы — smallint, integer, bigint, numeric, decimal, real, double precision, serial.

Строковые типы — char, varchar, text.

Логический тип — boolean.

Типы даты и времени — date, time, timestamp, timestamptz, interval.

Бинарный тип — bytea.

UUID — uuid.

JSON-типы — json и jsonb.

Массивы — массивы любого поддерживаемого типа.

Геометрические типы — point, line, circle, polygon.

Пользовательские типы — enum, composite types и другие пользовательские определения.

**22. What do CTIDs mean in PostgreSQL?**

---

CTID in PostgreSQL is a system column that uniquely identifies the physical location of a row within a table. It consists of a tuple (block_number, row_offset) pointing to the exact position of the row on disk. CTID changes when a row is updated, because PostgreSQL creates a new version of the row (MVCC). It is mainly used for internal purposes and debugging, not as a permanent row identifier.

CTID в PostgreSQL — это системная колонка, которая указывает на физическое расположение строки в таблице. Она представляет собой кортеж (номер*блока, смещение*строки), указывающий точную позицию строки на диске. CTID изменяется при обновлении строки, так как PostgreSQL создаёт новую версию записи (MVCC). Используется в основном для внутренних целей и отладки, а не как постоянный идентификатор строки.

**23. Explain tokens in PostgreSQL.**

In PostgreSQL (and SQL in general), tokens are the smallest meaningful elements of a SQL statement. When PostgreSQL parses a query, it breaks the input into tokens during lexical analysis. Common types of tokens include keywords (SELECT, INSERT), identifiers (table or column names), literals (strings, numbers), operators (=, +, AND), and symbols (comma, parentheses). Tokens are then passed to the parser to build the query structure.

В PostgreSQL (как и в SQL) токены — это минимальные смысловые элементы SQL-запроса. При разборе запроса PostgreSQL сначала разбивает его на токены на этапе лексического анализа. К токенам относятся ключевые слова (SELECT, INSERT), идентификаторы (имена таблиц и колонок), литералы (строки, числа), операторы (=, +, AND) и символы (запятая, скобки). Затем токены передаются парсеру для построения структуры запроса.

**24 How do you delete data from a table in PostgreSQL?**

---

You delete data in PostgreSQL using the DELETE statement.

```sql
DELETE FROM users
WHERE id = 1;
```

The WHERE clause specifies which rows to remove. If you omit WHERE, all rows in the table will be deleted. To remove all rows faster, you can use TRUNCATE TABLE users.

Удаление данных в PostgreSQL выполняется с помощью команды DELETE. Условие WHERE определяет, какие строки удалить. Если не указать WHERE, будут удалены все строки таблицы. Для быстрой очистки всей таблицы можно использовать TRUNCATE TABLE users.

**25. How do you query data from a table in PostgreSQL?**

You query data in PostgreSQL using the SELECT statement. `SELECT * FROM users;` You can specify columns instead of \* and add conditions with WHERE. You can also use ORDER BY, GROUP BY, LIMIT, and JOIN to refine the query.

Данные в PostgreSQL запрашиваются с помощью команды SELECT. Можно указать конкретные столбцы вместо \* и добавить условия через WHERE. Также можно использовать ORDER BY, GROUP BY, LIMIT и JOIN для уточнения запроса.

**26. What is a primary key in PostgreSQL?**

---

A primary key in PostgreSQL is a column (or a set of columns) that uniquely identifies each row in a table. It enforces uniqueness and does not allow NULL values. Each table can have only one primary key. PostgreSQL automatically creates a unique index for the primary key.

Первичный ключ (primary key) в PostgreSQL — это столбец или набор столбцов, которые уникально идентифицируют каждую строку таблицы. Он обеспечивает уникальность значений и не допускает NULL. У таблицы может быть только один primary key. PostgreSQL автоматически создаёт уникальный индекс для первичного ключа.

**27. What is a foreign key in PostgreSQL?**

A foreign key in PostgreSQL is a column (or set of columns) that creates a relationship between two tables. It references the primary key (or a unique key) in another table. Foreign keys enforce referential integrity, ensuring that referenced values exist. They can also define actions like ON DELETE CASCADE or ON UPDATE CASCADE.

Внешний ключ (foreign key) в PostgreSQL — это столбец или набор столбцов, который создаёт связь между двумя таблицами. Он ссылается на primary key или уникальный ключ в другой таблице. Foreign key обеспечивает ссылочную целостность, гарантируя существование связанных значений. Также можно задать действия, например ON DELETE CASCADE или ON UPDATE CASCADE.

**28. How do you create an index in PostgreSQL?**

You create an index in PostgreSQL using the CREATE INDEX statement.

```sql
CREATE INDEX idx_users_email
ON users (email);
```

You can also create a unique index using CREATE UNIQUE INDEX. Indexes improve query performance, especially for searches and filtering.

Индекс в PostgreSQL создаётся с помощью команды CREATE INDEX. Также можно создать уникальный индекс через CREATE UNIQUE INDEX. Индексы ускоряют выполнение запросов, особенно при поиске и фильтрации данных.

**29. What is a transaction in PostgreSQL?**

A transaction in PostgreSQL is a sequence of one or more SQL statements executed as a single unit of work. It ensures ACID properties: Atomicity, Consistency, Isolation, and Durability. A transaction starts with BEGIN (or START TRANSACTION) and ends with COMMIT or ROLLBACK. If an error occurs, ROLLBACK undoes all changes made within the transaction.

Транзакция в PostgreSQL — это последовательность одного или нескольких SQL-запросов, выполняемых как единое целое. Она обеспечивает свойства ACID: атомарность, согласованность, изоляцию и надёжность. Транзакция начинается с BEGIN (или START TRANSACTION) и завершается COMMIT или ROLLBACK. При ошибке ROLLBACK отменяет все изменения, сделанные в рамках транзакции.

**30. How do you perform a backup and restore in PostgreSQL?**

You typically back up PostgreSQL using pg_dump and restore using pg_restore (or psql for plain SQL dumps). Backup example (custom format): `pg_dump -Fc -f backup.dump mydb` Restore example: `pg_restore -d mydb backup.dump` For a plain SQL backup: `pg_dump -f backup.sql mydb`, then restore with `psql -d mydb -f backup.sql`. In production, you may also use physical backups (pg_basebackup) and WAL archiving for point-in-time recovery.

Обычно бэкап PostgreSQL делают через pg_dump, а восстановление — через pg_restore (или psql для SQL-дампа). Пример бэкапа (custom format): `pg_dump -Fc -f backup.dump mydb` Пример восстановления: `pg_restore -d mydb backup.dump` Для plain SQL: `pg_dump -f backup.sql mydb`, затем восстановление через `psql -d mydb -f backup.sql`. В продакшене также используют физические бэкапы (pg_basebackup) и архивирование WAL для восстановления на конкретный момент времени (PITR).

**31. What is the role of the pg_hba.conf file in PostgreSQL?**

---

The pg_hba.conf file (Host-Based Authentication) controls client authentication in PostgreSQL. It defines which users can connect, from which hosts, to which databases, and what authentication method (e.g., password, md5, scram, trust, peer) is required. PostgreSQL checks this file whenever a client attempts to connect.

Файл pg_hba.conf (Host-Based Authentication) управляет аутентификацией клиентов в PostgreSQL. Он определяет, какие пользователи могут подключаться, с каких хостов, к каким базам данных и какой метод аутентификации (например, password, md5, scram, trust, peer) используется. PostgreSQL проверяет этот файл при каждом подключении клиента.

**32. How do you connect to a PostgreSQL database using psql?**

---

You connect to a PostgreSQL database using the psql command-line tool with connection parameters such as host, port, user, and database name.
Basic syntax: `psql -h host -p port -U username -d database`
Example: `psql -h localhost -p 5432 -U postgres -d mydb`
You can also use a connection string: `psql "postgresql://username:password@host:port/database"` After running the command, you'll be prompted for a password (if required), and then you'll enter the interactive psql shell.

Подключение к базе PostgreSQL выполняется через утилиту командной строки psql, указывая хост, порт, пользователя и имя базы данных.
Базовый синтаксис: `psql -h host -p port -U username -d database` Пример: `psql -h localhost -p 5432 -U postgres -d mydb`
Также можно использовать строку подключения: `psql "postgresql://username:password@host:port/database"` После выполнения команды (если требуется) будет запрошен пароль, и вы попадёте в интерактивную консоль psql.

**33. What is the difference between a serial and a sequence in PostgreSQL?**

---

Serial is a pseudo-type used in table definitions to auto-generate integer IDs. When you declare a column as serial, PostgreSQL automatically:

- Creates a sequence object

- Sets the column's default value to nextval(sequence)

- Links the sequence to the column

Example: id serial primary key
Sequence is a separate database object that generates numeric values independently. You can create and use it manually:

```sql
CREATE SEQUENCE my_seq;
SELECT nextval('my_seq');
```

So, serial is just a shortcut that automatically creates and configures a sequence for a column, while a sequence is the underlying standalone object that generates numbers.

Serial — это псевдотип для автоинкрементного целочисленного поля. При объявлении serial PostgreSQL автоматически:

- Создаёт объект sequence

- Устанавливает значение по умолчанию nextval(sequence)

- Связывает sequence с колонкой

Sequence — это отдельный объект базы данных, который генерирует числовые значения независимо от таблиц. Его можно создать и использовать вручную. Итого: serial — это удобный синтаксический сахар, а sequence — реальный объект, который генерирует значения.

**34. How do you handle concurrent updates in PostgreSQL?**

Concurrent updates in PostgreSQL are handled using transactions and built-in concurrency control mechanisms (MVCC). Main approaches:

- Row-level locking - Use SELECT ... FOR UPDATE to lock selected rows so other transactions cannot modify them until the current transaction finishes.

- Transactions with proper isolation levels - PostgreSQL supports isolation levels like Read Committed (default), Repeatable Read, and Serializable to control visibility and prevent anomalies.

- Optimistic locking - Use a version column (e.g., version or updated_at) and check it in the WHERE clause during UPDATE. If no rows are affected, it means the row was modified by another transaction.

- Handling conflicts - Catch errors such as serialization failures and retry the transaction.

В PostgreSQL конкурентные обновления обрабатываются через транзакции и механизм MVCC (многоверсионность).

Основные способы:

- Блокировка строк - SELECT ... FOR UPDATE блокирует выбранные строки до завершения транзакции.

- Уровни изоляции транзакций - Read Committed (по умолчанию), Repeatable Read и Serializable управляют видимостью данных и предотвращают аномалии.

- Оптимистическая блокировка - Добавляют поле версии или времени обновления и проверяют его в WHERE при UPDATE. Если строка не обновилась — её изменили параллельно.

- Обработка конфликтов - Перехват ошибок сериализации и повторный запуск транзакции.

**35. What is a composite type in PostgreSQL?**

---

A composite type in PostgreSQL is a user-defined data type that groups multiple fields into a single structured value (similar to a row or struct). It can be automatically created when you define a table (each table has an implicit composite type with the same name), or you can define it manually: `CREATE TYPE address AS (street text, city text, zip_code text);`
You can then use it as a column type: `CREATE TABLE users (id serial, home_address address);` Composite types are useful for structured data, function parameters/returns, and complex queries.

Composite type в PostgreSQL — это пользовательский тип данных, который объединяет несколько полей в одну структуру (аналог строки таблицы или struct). Он автоматически создаётся для каждой таблицы (таблица имеет одноимённый составной тип) или может быть создан вручную: `CREATE TYPE address AS (street text, city text, zip_code text);` Затем его можно использовать как тип колонки: `CREATE TABLE users (id serial, home_address address);` Composite type удобен для хранения структурированных данных, передачи параметров в функции и возврата сложных результатов.

**36. How do you use window functions in PostgreSQL?**

---

Window functions in PostgreSQL perform calculations across a set of rows related to the current row, without collapsing the result like GROUP BY. They are used with the OVER() clause.

Basic syntax: `function_name(...) OVER (PARTITION BY ... ORDER BY ...)`

Example — ranking users by salary within each department: `SELECT name, department, salary, RANK() OVER (PARTITION BY department ORDER BY salary DESC) AS rank FROM employees;`

Common window functions:

- ROW_NUMBER() — assigns a unique row number

- RANK() / DENSE_RANK() — ranking with or without gaps

- SUM() / AVG() — running totals or averages

- LAG() / LEAD() — access previous/next row values

Example — running total:

- SELECT date, amount, SUM(amount) OVER (ORDER BY date) AS running_total FROM sales;

Оконные функции в PostgreSQL выполняют вычисления по набору строк, связанных с текущей строкой, не объединяя их как GROUP BY.

Используются с конструкцией OVER().

Базовый синтаксис: `function_name(...) OVER (PARTITION BY ... ORDER BY ...)`

Пример — ранжирование сотрудников по зарплате внутри отдела: `SELECT name, department, salary, RANK() OVER (PARTITION BY department ORDER BY salary DESC) AS rank FROM employees;`

Часто используемые функции:

- ROW_NUMBER() — нумерация строк

- RANK() / DENSE_RANK() — ранжирование

- SUM() / AVG() — накопительные суммы и средние

- LAG() / LEAD() — доступ к предыдущей/следующей строке

**37. What is the purpose of the pg_stat_user_indexes view in PostgreSQL?**

---

The pg_stat_user_indexes view provides statistics about index usage for user-defined tables in PostgreSQL. Its purpose is to help monitor and analyze how indexes are being used, so you can optimize performance.

Key information it provides:

- indexrelname — index name

- relname — table name

- idx_scan — number of times the index was used

- idx_tup_read — number of index entries returned

- idx_tup_fetch — number of table rows fetched via the index

It is commonly used to:

- Detect unused indexes (low or zero idx_scan)

- Identify heavily used indexes

- Decide whether an index should be kept, optimized, or removed

pg_stat_user_indexes — это представление со статистикой использования индексов пользовательских таблиц в PostgreSQL. Его цель — мониторинг и анализ использования индексов для оптимизации производительности.

Основные поля:

- indexrelname — имя индекса

- relname — имя таблицы

- idx_scan — сколько раз индекс использовался

- idx_tup_read — сколько записей прочитано через индекс

- idx_tup_fetch — сколько строк таблицы получено через индекс

Используется для:

- Поиска неиспользуемых индексов

- Выявления активно используемых индексов

- Принятия решения об удалении или оптимизации индекса

**38. How do you implement full-text search with stemming in PostgreSQL?**

---

To implement full-text search with stemming in PostgreSQL, use tsvector + tsquery with a language text search configuration (e.g., english, russian). The language config applies stemming (normalizes words to their base forms). Create a searchable tsvector (often as a generated column)

```sql
ALTER TABLE docs
ADD COLUMN fts tsvector
GENERATED ALWAYS AS (
to_tsvector('english', coalesce(title,'') || ' ' || coalesce(body,''))
) STORED;
```

Add a GIN index for fast search `CREATE INDEX docs_fts_gin ON docs USING GIN (fts);` Query using a stemming-aware query builder

```sql
SELECT id, title
FROM docs
WHERE fts @@ plainto_tsquery('english', 'running shoes');
```

Notes:

- Use the correct config per language ('russian', 'english', etc.) to get proper stemming.

- For ranking results: ts_rank(fts, tsquery).

- For phrase-like input: websearch_to_tsquery('english', 'quick brown fox').

Чтобы сделать full-text search со стеммингом в PostgreSQL, используют tsvector + tsquery и текстовую конфигурацию языка (например, english, russian). Конфигурация языка включает стемминг (приведение слов к основе). Создать tsvector (часто как generated column)

Добавить GIN-индекс для ускорения поиска

Искать через запрос, учитывающий стемминг
Заметки:

- Выбирай конфигурацию под язык ('russian', 'english'), иначе стемминг будет неправильным.

- Для сортировки по релевантности: ts_rank(fts, tsquery).

- Для поисковой строки "как в Google": websearch_to_tsquery('english', '...').

**39. What is the purpose of the pg_cron extension in PostgreSQL?**

---

pg_cron is a PostgreSQL extension that allows you to schedule and run SQL commands or stored procedures directly inside the database using cron-style syntax. Its purpose is to automate recurring tasks without relying on external system cron jobs.

Typical use cases:

- Running periodic maintenance (e.g., cleanup, archiving)

- Refreshing materialized views

- Updating aggregates

- Scheduling reports

- Deleting old records

```sql
SELECT cron.schedule(
'daily_cleanup',
'0 3 \* \* \*',
$$DELETE FROM logs WHERE created_at < now() - interval '30 days'$$
);
```

So, pg_cron enables built-in job scheduling inside PostgreSQL, similar to Linux cron, but managed from the database.

pg_cron — это расширение PostgreSQL для планирования и выполнения SQL-запросов или процедур по расписанию в формате cron. Его цель — автоматизация регулярных задач прямо внутри базы данных без использования внешнего системного cron.

Типичные сценарии:

- Регулярная очистка и обслуживание

- Обновление materialized views

- Пересчёт агрегатов

- Формирование отчётов

- Удаление старых данных

Таким образом, pg_cron позволяет организовать встроенный планировщик задач в PostgreSQL по аналогии с Linux cron.

**40. How do you perform bulk inserts in PostgreSQL?**

Bulk inserts in PostgreSQL can be done efficiently in several ways:

Multi-row INSERT (good for moderate batches)

```sql
INSERT INTO users (name, email)
VALUES
('Alice', 'a@example.com'),
('Bob', 'b@example.com'),
('Charlie', 'c@example.com');

COPY (fastest method for large datasets)
Load data from a file:

COPY users (name, email)
FROM '/path/to/file.csv'
WITH (FORMAT csv, HEADER true);

```

Or from STDIN (e.g., via psql): `COPY users (name, email) FROM STDIN WITH (FORMAT csv);` Using transactions -Wrap inserts in a single transaction to avoid per-row commit overhead:

```sql
BEGIN;
-- multiple INSERT statements
COMMIT;
```

Using UNLOGGED tables (optional optimization)
For temporary or non-critical data, UNLOGGED tables reduce WAL overhead. Best practice for very large imports: use COPY + single transaction + proper indexing strategy (often create indexes after loading data).

Массовая вставка данных в PostgreSQL выполняется несколькими способами:

- INSERT с несколькими строками - Подходит для средних объёмов данных.

- COPY (самый быстрый способ) -Позволяет загружать данные из CSV-файлов или через STDIN.

- Использование транзакции - Объединение вставок в одну транзакцию снижает накладные расходы на commit.

- UNLOGGED таблицы - Снижают нагрузку на WAL (подходит для временных или некритичных данных).

Для больших объёмов данных обычно используют COPY + одну транзакцию + создание индексов после загрузки.

**41. What is the role of the pg_stat_progress_vacuum view in PostgreSQL?**

---

pg_stat_progress_vacuum is a system view that shows real-time progress of running VACUUM operations in PostgreSQL. Its role is to monitor and troubleshoot vacuum processes, especially for large tables.

It provides information such as:

- relid — table being vacuumed

- phase — current phase (e.g., scanning heap, vacuuming indexes, cleanup)

- heap_blks_total — total heap blocks

- heap_blks_scanned — scanned blocks

- heap_blks_vacuumed — vacuumed blocks

- index_vacuum_count — number of indexes processed

Use cases:

- Check how far a VACUUM has progressed

- Estimate remaining work

- Detect long-running or stuck vacuum processes

pg_stat_progress_vacuum — это системное представление, показывающее прогресс выполняющихся операций VACUUM в реальном времени. Его задача — мониторинг и диагностика процесса очистки таблиц, особенно больших.

Оно содержит:

- relid — таблица, над которой выполняется VACUUM

- phase — текущая фаза процесса

- heap_blks_total — всего блоков

- heap_blks_scanned — просканировано блоков

- heap_blks_vacuumed — очищено блоков

- index_vacuum_count — количество обработанных индексов

Используется для:

- Контроля прогресса VACUUM

- Оценки оставшегося времени

- Выявления долгих или зависших процессов.

**42. What is the role of the pg_stat_progress_vacuum view in PostgreSQL?**

---

pg_stat_progress_vacuum is a system view that displays the live progress of currently running VACUUM operations in PostgreSQL. Its role is to help monitor and diagnose vacuum activity, especially on large tables.

It shows details such as:

- The table being vacuumed

- The current phase (scanning heap, vacuuming indexes, cleanup, etc.)

- Total, scanned, and vacuumed heap blocks

- Index processing progress

It is mainly used to track long-running VACUUM processes, estimate remaining work, and troubleshoot performance issues.

pg_stat_progress_vacuum — это системное представление, которое показывает прогресс выполняющихся операций VACUUM в реальном времени. Его задача — мониторинг и диагностика процесса очистки таблиц, особенно больших.

Оно отображает:

- Таблицу, над которой выполняется VACUUM

- Текущую фазу процесса

- Общее количество блоков, просканированные и очищенные блоки

- Прогресс обработки индексов

Используется для контроля длительных операций VACUUM и анализа проблем производительности.

**43. What is a View in PostgreSQL?**

---

A View in PostgreSQL is a virtual table based on the result of a SQL query. It does not store data itself — it dynamically shows data from underlying tables.

```sql
CREATE VIEW active_users AS
SELECT id, name, email
FROM users
WHERE is_active = true;

When you query the view:

SELECT * FROM active_users;
```

PostgreSQL executes the underlying SELECT statement.

Views are used to:

- Simplify complex queries

- Provide abstraction

- Restrict access to specific columns or rows

- Improve code readability

View в PostgreSQL — это виртуальная таблица, основанная на результате SQL-запроса. Она не хранит данные самостоятельно, а отображает данные из базовых таблиц.

При запросе к view PostgreSQL выполняет связанный SELECT.

View используется для:

- Упрощения сложных запросов

- Абстракции

- Ограничения доступа к данным

- Улучшения читаемости кода

**44. Explain the Concept of Transactions in PostgreSQL.**

A transaction in PostgreSQL is a sequence of one or more SQL operations executed as a single logical unit of work.
It guarantees ACID properties:

- Atomicity — all operations succeed or none are applied (rollback on failure).

- Consistency — the database remains in a valid state after commit.

- Isolation — concurrent transactions don't interfere improperly (controlled by isolation levels).

- Durability — once committed, changes are permanently saved.

Basic usage:

```sql
BEGIN;
UPDATE accounts SET balance = balance - 100 WHERE id = 1;
UPDATE accounts SET balance = balance + 100 WHERE id = 2;
COMMIT;
```

If something goes wrong: - ROLLBACK;

PostgreSQL uses MVCC (Multi-Version Concurrency Control) to handle concurrent transactions efficiently.

Транзакция в PostgreSQL — это последовательность одной или нескольких SQL-операций, выполняемых как единое логическое действие.

Она обеспечивает свойства ACID:

- Atomicity (Атомарность) — либо выполняются все операции, либо ни одна (rollback при ошибке).

- Consistency (Согласованность) — база остаётся в корректном состоянии после commit.

- Isolation (Изоляция) — параллельные транзакции корректно изолированы друг от друга.

- Durability (Надёжность) — после commit изменения сохраняются постоянно.

При ошибке выполняется: ROLLBACK;

Для работы с конкурентностью PostgreSQL использует механизм MVCC (многоверсионность).

**45. What are Triggers in PostgreSQL, and How to Create Them?**

---

Triggers in PostgreSQL are special database objects that automatically execute a function when a specific event occurs on a table or view.

They are commonly used for:

- Auditing changes

- Enforcing business rules

- Automatic updates (e.g., timestamps)

- Data validation

- A trigger is always linked to a trigger function.

Step 1 — Create a trigger function:

```sql
CREATE OR REPLACE FUNCTION set_updated_at()
RETURNS TRIGGER AS $$
BEGIN
NEW.updated_at = now();
RETURN NEW;
END;

LANGUAGE plpgsql;
```

Step 2 — Create the trigger:

```sql
CREATE TRIGGER update_timestamp
BEFORE UPDATE ON users
FOR EACH ROW
EXECUTE FUNCTION set_updated_at();
```

Types of triggers:

- BEFORE or AFTER (when they run)

- INSERT, UPDATE, DELETE, TRUNCATE (event type)

- FOR EACH ROW or FOR EACH STATEMENT

Триггеры в PostgreSQL — это специальные объекты базы данных, которые автоматически выполняют функцию при наступлении определённого события на таблице или представлении.

Используются для:

- Аудита изменений

- Реализации бизнес-логики

- Автоматического обновления полей (например, времени изменения)

- Валидации данных

- Триггер всегда связан с функцией.

Шаг 1 — Создать функцию триггера:

```sql
CREATE OR REPLACE FUNCTION set_updated_at()
RETURNS TRIGGER AS

BEGIN
NEW.updated_at = now();
RETURN NEW;
END;


LANGUAGE plpgsql;
```

Шаг 2 — Создать триггер:

```sql
CREATE TRIGGER update_timestamp
BEFORE UPDATE ON users
FOR EACH ROW
EXECUTE FUNCTION set_updated_at();
```

Типы триггеров:

- BEFORE или AFTER

- INSERT, UPDATE, DELETE, TRUNCATE

- FOR EACH ROW или FOR EACH STATEMENT.

**46. What are CTEs (Common Table Expressions) in PostgreSQL?**

---

CTEs (Common Table Expressions) in PostgreSQL are temporary result sets defined within a query using the WITH clause. They help structure complex queries and improve readability.

Basic syntax:

```sql
WITH recent*orders AS (
SELECT * FROM orders
WHERE created*at > now() - interval '7 days'
)
SELECT * FROM recent_orders;
```

Benefits:

- Break complex queries into logical steps

- Reuse intermediate results

- Improve readability and maintainability

- CTEs can also be recursive:

```sql
WITH RECURSIVE category_tree AS (
SELECT id, parent_id, name
FROM categories
WHERE parent_id IS NULL
UNION ALL
SELECT c.id, c.parent_id, c.name
FROM categories c
JOIN category_tree ct ON c.parent_id = ct.id
)
SELECT \* FROM category_tree;
```

Recursive CTEs are used for hierarchical data (e.g., trees, organizational structures).

CTE (Common Table Expressions) в PostgreSQL — это временные результирующие наборы данных, определяемые внутри запроса с помощью WITH.

Преимущества:

- Разбиение сложных запросов на логические части

- Повторное использование промежуточных результатов

- Улучшение читаемости

CTE могут быть рекурсивными (WITH RECURSIVE) и применяются для работы с иерархическими данными.

**47. How to Use Window Functions in PostgreSQL?**

---

Window functions in PostgreSQL perform calculations across a set of rows related to the current row without grouping them into a single result like GROUP BY. They are used with the OVER() clause.

Basic syntax:`function_name(...) OVER (PARTITION BY ... ORDER BY ...)`

Example — assign row numbers per department:

```sql
SELECT name, department, salary,
ROW_NUMBER() OVER (PARTITION BY department ORDER BY salary DESC) AS row_num
FROM employees;
```

Common window functions:

- ROW_NUMBER() — unique row number

- RANK() / DENSE_RANK() — ranking

- SUM() / AVG() — running totals or averages

- LAG() / LEAD() — access previous/next row values

Example — running total:

```sql
SELECT date, amount,
SUM(amount) OVER (ORDER BY date) AS running_total
FROM sales;
```

Оконные функции в PostgreSQL выполняют вычисления по набору строк, связанных с текущей строкой, не объединяя их как GROUP BY. Используются с OVER().
Базовый синтаксис: `function_name(...) OVER (PARTITION BY ... ORDER BY ...)`

Пример — нумерация сотрудников внутри отдела:

```sql
SELECT name, department, salary,
ROW_NUMBER() OVER (PARTITION BY department ORDER BY salary DESC) AS row_num
FROM employees;
```

Частые функции:

- ROW_NUMBER() — нумерация

- RANK() / DENSE_RANK() — ранжирование

- SUM() / AVG() — накопительные вычисления

- LAG() / LEAD() — доступ к соседним строкам

Пример — накопительная сумма:

```sql
SELECT date, amount,
SUM(amount) OVER (ORDER BY date) AS running_total
FROM sales;
```

**48. Explain the Concept of JSON Data Types in PostgreSQL.**

---

PostgreSQL supports two JSON data types: json and jsonb, used to store semi-structured data. json stores data as plain text (exact input format is preserved). jsonb stores data in a binary format (faster for querying and indexing, does not preserve formatting or key order).

Example:

```sql
CREATE TABLE users (
  id serial,
  profile jsonb
);
```

Insert data:

```sql
INSERT INTO users (profile)
VALUES ('{"name": "John", "age": 30}');
```

Query JSON fields: `SELECT profile->>'name' FROM users;`

Key features:

- Store nested objects and arrays

- Extract values using operators (->, ->>, #>)

- Index with GIN for fast searches (recommended with jsonb)

- Use JSON functions for filtering and transformation

- jsonb is generally preferred for performance and indexing.

В PostgreSQL есть два типа для работы с JSON: json и jsonb. json хранит данные как текст (сохраняет исходный формат). jsonb хранит данные в бинарном виде (быстрее для поиска и индексации, не сохраняет порядок ключей).

```sql
CREATE TABLE users (
  id serial,
  profile jsonb
);

INSERT INTO users (profile)
VALUES ('{"name": "John", "age": 30}');

SELECT profile->>'name' FROM users;
```

Основные возможности:

- Хранение вложенных объектов и массивов

- Извлечение значений через операторы (->, ->>, #>)

- Индексация через GIN (лучше использовать с jsonb)

- Использование встроенных JSON-функций

В большинстве случаев предпочтительнее использовать jsonb из-за производительности.

**49. How to Implement Partitioning in PostgreSQL?**

---

Partitioning in PostgreSQL splits a large table into smaller, more manageable pieces (partitions) based on a key column. It improves performance and maintenance for large datasets.

PostgreSQL supports:

- RANGE partitioning

- LIST partitioning

- HASH partitioning

Step 1 — Create a partitioned table:

```sql
CREATE TABLE orders (
id serial,
order_date date,
amount numeric
) PARTITION BY RANGE (order_date);
```

Step 2 — Create partitions:

```sql
CREATE TABLE orders_2025
PARTITION OF orders
FOR VALUES FROM ('2025-01-01') TO ('2026-01-01');

CREATE TABLE orders_2026
PARTITION OF orders
FOR VALUES FROM ('2026-01-01') TO ('2027-01-01');
```

Now PostgreSQL automatically routes inserted rows to the correct partition.

Benefits:

- Faster queries (partition pruning)

- Easier maintenance (drop/archive partitions)

- Better performance for large tables

Партиционирование в PostgreSQL — это разделение большой таблицы на более мелкие части (партиции) по ключевому столбцу. Это повышает производительность и упрощает обслуживание больших данных.

Поддерживаются типы:

- RANGE

- LIST

- HASH

Шаг 1 — Создать партиционированную таблицу:

```sql
CREATE TABLE orders (
id serial,
order_date date,
amount numeric
) PARTITION BY RANGE (order_date);
```

Шаг 2 — Создать партиции:

```sql
CREATE TABLE orders_2025
PARTITION OF orders
FOR VALUES FROM ('2025-01-01') TO ('2026-01-01');

CREATE TABLE orders_2026
PARTITION OF orders
FOR VALUES FROM ('2026-01-01') TO ('2027-01-01');
```

PostgreSQL автоматически распределяет данные по нужной партиции.

Преимущества:

- Быстрее запросы (partition pruning)

- Удобное удаление/архивация данных

- Лучшая масштабируемость для больших таблиц.

**50. How Do You Optimize Queries In PostgreSQL?**

---

Optimize PostgreSQL queries by focusing on measurement first, then indexes, then query/schema changes:

- Use EXPLAIN (ANALYZE, BUFFERS) to see the real plan, timing, and I/O hot spots.

- Add the right indexes (B-tree for equality/range, GIN for jsonb/FTS, GiST/SP-GiST for geo/special cases). Prefer multicolumn or partial indexes when they match your WHERE/JOIN pattern.

- Write sargable predicates (avoid functions on indexed columns in WHERE, avoid leading-wildcard LIKE '%x').

- Fix joins: correct join keys, reduce row counts early, avoid unnecessary SELECT \*, consider EXISTS vs IN when appropriate.

- Keep stats fresh: ANALYZE, proper autovacuum settings; watch table bloat and VACUUM.

- Limit large sorts/aggregations: filter earlier, index for ORDER BY, consider incremental/materialized aggregates.

Use partitioning for very large tables and time-based data; benefit from partition pruning. Tune for workload: work_mem, shared_buffers, effective_cache_size, and connection pooling (e.g., PgBouncer). Cache and batch at the app level when queries are repetitive.

Оптимизация запросов в PostgreSQL обычно идёт так: сначала измеряем, потом индексы, потом переписываем запрос/схему:

- Используй EXPLAIN (ANALYZE, BUFFERS) — покажет реальный план, время и где упираешься в I/O.

- Добавляй правильные индексы (B-tree для equality/range, GIN для jsonb/полнотекстового поиска, GiST/SP-GiST для гео и спец. случаев). Часто лучше составные или частичные индексы под конкретный WHERE/JOIN.

- Делай условия "индексируемыми" (не применяй функции к индексируемым колонкам в WHERE, избегай LIKE '%x').

- Чини JOIN'ы: правильные ключи, уменьшай выборку как можно раньше, не тяни SELECT \*, иногда выгоднее EXISTS, чем IN.

- Обновляй статистику: ANALYZE, адекватный autovacuum; следи за bloat и делай VACUUM.

- Ограничивай тяжёлые сортировки/агрегации: фильтруй раньше, индексируй под ORDER BY, при необходимости используй materialized views/агрегаты.

Для огромных таблиц используй partitioning (особенно по времени) и partition pruning. Тюнинг под нагрузку: work_mem, shared_buffers, effective_cache_size, пул соединений (например, PgBouncer). Кэшируй и батчь на уровне приложения, если запросы повторяются.

**51 What are the Different Isolation Levels in PostgreSQL?**

--

PostgreSQL supports three transaction isolation levels (internally implemented using MVCC):

- Read Committed (default) - A transaction sees only committed data. Each query sees a fresh snapshot of committed rows. Non-repeatable reads can occur.

- Repeatable Read - The transaction sees a consistent snapshot taken at the start of the transaction. Prevents non-repeatable reads. Phantom reads are prevented in PostgreSQL (stronger than standard definition).

- Serializable - The strictest level. Ensures the result is the same as if transactions ran one after another. May raise serialization errors that require retrying the transaction.

Set isolation level:

```sql
BEGIN;
SET TRANSACTION ISOLATION LEVEL SERIALIZABLE;
```

В PostgreSQL поддерживаются три уровня изоляции транзакций (реализованы через MVCC):

- Read Committed (по умолчанию) - Видны только подтверждённые данные. Каждый запрос получает новый снимок данных. Возможны неповторяемые чтения.

- Repeatable Read - Транзакция работает с одним снимком данных с момента начала. Предотвращает неповторяемые чтения. В PostgreSQL также предотвращает фантомные чтения.

- Serializable Самый строгий уровень. Гарантирует поведение как при последовательном выполнении транзакций. Возможны ошибки сериализации, требующие повторного выполнения транзакции.

**52. How to Handle Deadlocks in PostgreSQL?**

---

Deadlocks occur when two or more transactions wait on each other's locks. PostgreSQL automatically detects deadlocks and aborts one transaction with an error.

How to handle them:

Detect the error
PostgreSQL raises: ERROR: deadlock detected.
The aborted transaction must be retried.

Keep transactions short
Reduce the time locks are held.

Lock rows in a consistent order
Always update/select tables and rows in the same order across transactions.

Use proper indexing
Avoid full table scans that escalate locking conflicts.

Use explicit locking carefully
SELECT ... FOR UPDATE should be used consistently.

Retry logic
In application code, catch deadlock errors and retry the transaction.

Example retry pattern (conceptually):

BEGIN

Execute queries

If deadlock → ROLLBACK and retry

Deadlock возникает, когда две или более транзакции ждут блокировки друг друга. PostgreSQL автоматически обнаруживает дедлок и прерывает одну из транзакций.

Как с ними работать:

Обнаружение
PostgreSQL выдаёт ошибку deadlock detected.
Транзакцию нужно повторить.

Делать транзакции короткими
Минимизировать время удержания блокировок.

Единый порядок блокировок
Всегда обращаться к таблицам и строкам в одном и том же порядке.

Правильные индексы
Избегать full table scan, который увеличивает вероятность конфликтов.

Аккуратное использование SELECT ... FOR UPDATE
Использовать последовательно и предсказуемо.

Реализация retry в приложении
При ошибке дедлока делать rollback и повтор транзакции.

**53. Explain the Concept of the Query Planner and Optimizer in PostgreSQL.**

---

The Query Planner (Optimizer) in PostgreSQL is responsible for deciding how a SQL query will be executed.

When you send a query, PostgreSQL:

- Parses it (syntax analysis)

- Rewrites it (rules, view expansion)

- Generates multiple possible execution plans

- Estimates the cost of each plan using table statistics

- Chooses the cheapest plan

The planner decides:

- Which indexes to use

- Join order

- Join methods (Nested Loop, Hash Join, Merge Join)

- Whether to use sequential scan or index scan

- How to perform sorting and aggregation

- It relies on statistics collected by ANALYZE.

You can inspect the chosen plan with: `EXPLAIN ANALYZE SELECT ...`
Good performance depends on:

Accurate statistics

Proper indexes

Correct query structure

Планировщик запросов (Query Planner / Optimizer) в PostgreSQL определяет, как именно будет выполнен SQL-запрос.

При выполнении запроса PostgreSQL:

- Разбирает его (парсинг)

- Переписывает (правила, раскрытие view)

- Генерирует несколько вариантов плана выполнения

- Оценивает стоимость каждого плана

- Выбирает самый дешёвый

Планировщик решает:

- Какие индексы использовать

- Порядок соединения таблиц

- Тип JOIN (Nested Loop, Hash Join, Merge Join)

- Использовать ли Seq Scan или Index Scan

- Как выполнять сортировку и агрегацию

Он опирается на статистику (ANALYZE).

Посмотреть план можно через: `EXPLAIN ANALYZE SELECT ...`

**54. How Do You Implement Sharding In PostgreSQL?**

---

There are two common ways to implement sharding with PostgreSQL: (1) application-level sharding or (2) using a distributed extension (most commonly Citus). Native PostgreSQL partitioning is not sharding—it keeps data on one server.

1. Application-level sharding (manual)

   Choose a shard key (e.g., tenant_id, user_id) and a routing rule (hash/mod, ranges).

   Create multiple PostgreSQL clusters (each is a shard).

   In the app (or a routing layer), compute shard = hash(key) % N and send queries to the right shard.

   Keep global uniqueness in mind (UUID/ULID, or "shard id + local sequence").

   Handle cross-shard queries via:

   fan-out (query all shards + merge),

   a reporting replica/warehouse,

   or denormalizing/duplicating reference data.

2. Distributed PostgreSQL via extension (Citus)

   Install Citus and create a coordinator + worker nodes.

   Pick a distribution column (shard key).

   Convert tables to distributed tables; Citus creates and manages shards and routes queries.

Typical flow:

```sql
-- on coordinator
CREATE EXTENSION citus;

SELECT citus_add_node('worker1', 5432);
SELECT citus_add_node('worker2', 5432);

-- distribute by tenant_id
SELECT create_distributed_table('orders', 'tenant_id');
```

Good practices (both approaches)

Pick a shard key that matches most queries (so joins stay local). Avoid cross-shard transactions; keep transactions within one shard. Plan rebalancing (adding nodes and moving shards). Add observability: per-shard metrics, slow query logs, and consistent schema migrations.

В PostgreSQL шардинг обычно делают двумя способами: (1) на уровне приложения или (2) через распределённое расширение (чаще всего Citus). Встроенное partitioning — это не шардинг, т.к. данные остаются на одном сервере.

1. Шардинг на уровне приложения (ручной)

   Выбрать ключ шардинга (например, tenant_id, user_id) и правило маршрутизации (hash/mod, диапазоны).

   Поднять несколько PostgreSQL кластеров (каждый — отдельный шард).

   В приложении (или прокси) вычислять shard = hash(key) % N и отправлять запросы в нужный шард.

   Продумать глобальную уникальность (UUID/ULID или "id шарда + локальная последовательность").

   Кросс-шардовые запросы решать через fan-out + объединение результатов, отдельную витрину/реплику, либо денормализацию.

2. Распределённый PostgreSQL через расширение (Citus)

   Ставишь Citus: coordinator + worker-ноды.

   Выбираешь колонку распределения (ключ шардинга).

Делаешь таблицы distributed; Citus создаёт шарды и роутит запросы.

Пример:

```sql
CREATE EXTENSION citus;

SELECT citus_add_node('worker1', 5432);
SELECT citus_add_node('worker2', 5432);

SELECT create_distributed_table('orders', 'tenant_id');
```

Практики

Ключ шардинга должен совпадать с большинством фильтров/джоинов.

Транзакции лучше держать в пределах одного шарда.

Заранее продумай ребалансировку при добавлении нод.

Метрики/логи по каждому шару и аккуратные миграции схемы.
