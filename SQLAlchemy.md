## SQLAlchemy

**1. Can you explain the concept of ORM and how SQLAlchemy provides this functionality?**

ORM (Object-Relational Mapping) is a programming technique that allows developers to interact with  
a relational database using objects instead of writing raw SQL queries. It maps database tables to  
classes and rows to objects, so you can work with database data as native objects in your programming language.

Benefits of ORM:

- Reduces the need to write repetitive SQL queries.

- Provides abstraction over database differences.

- Improves maintainability by working with objects and relationships instead of tables and joins.

- Can enforce constraints and relationships at the object level.

SQLAlchemy and ORM in Python:

- SQLAlchemy is a popular Python library that provides ORM functionality.

- You define Python classes that represent tables and their columns.

- Relationships between tables (one-to-many, many-to-many) are represented as Python relationships.

- You interact with the database using Python objects and methods instead of raw SQL.

Example using SQLAlchemy ORM:

```
from sqlalchemy import Column, Integer, String, ForeignKey
from sqlalchemy.orm import relationship, declarative_base, sessionmaker
from sqlalchemy import create_engine

Base = declarative_base()

class User(Base):
**tablename** = 'users'
id = Column(Integer, primary_key=True)
name = Column(String)
orders = relationship("Order", back_populates="user")

class Order(Base):
**tablename** = 'orders'
id = Column(Integer, primary_key=True)
user_id = Column(Integer, ForeignKey('users.id'))
amount = Column(Integer)
user = relationship("User", back_populates="orders")

engine = create_engine('mysql+pymysql://user:pass@localhost/mydb')
Base.metadata.create_all(engine)

Session = sessionmaker(bind=engine)
session = Session()

# Add a new user

new_user = User(name="Alice")
session.add(new_user)
session.commit()

# Query using ORM

alice_orders = session.query(Order).filter_by(user=new_user).all()
```

How SQLAlchemy ORM works:

- Mapping: Classes → Tables, Attributes → Columns

- Session: Manages object states (new, modified, deleted) and transactions.

- Querying: Allows Pythonic queries instead of raw SQL.

- Relationships: Automatically handles joins and foreign keys via object attributes.

Summary:

- ORM abstracts SQL, letting you work with objects.

- SQLAlchemy provides a robust, flexible ORM for Python with full control over table mapping, relationships, and queries.

ORM (Object-Relational Mapping) — это метод работы с реляционной базой данных через объекты,  
а не напрямую через SQL-запросы. Таблицы базы данных сопоставляются с классами,  
а строки — с объектами, что позволяет работать с данными как с обычными объектами в коде.

Преимущества ORM:

- Меньше необходимости писать повторяющийся SQL.

- Абстракция от различий между СУБД.

- Упрощает поддержку, позволяя работать с объектами вместо таблиц и JOIN.

- Позволяет реализовать ограничения и связи на уровне объектов.

SQLAlchemy и ORM в Python:

- SQLAlchemy — популярная библиотека Python для ORM.

- Классы Python представляют таблицы и их колонки.

- Связи между таблицами (one-to-many, many-to-many) отображаются как атрибуты объектов.

- Работа с базой через объекты Python и методы, а не через SQL.

Как работает SQLAlchemy ORM:

- Mapping (сопоставление): Классы → таблицы, атрибуты → колонки

- Session (сессия): Управляет состояниями объектов (new, modified, deleted) и транзакциями

- Querying (запросы): Позволяет писать Python-стиль запросов вместо SQL

- Relationships (связи): Автоматически управляет JOIN и внешними ключами через атрибуты объектов

Итог:

- ORM абстрагирует SQL, позволяя работать с объектами.

- SQLAlchemy предоставляет гибкий и мощный ORM для Python с полным контролем над таблицами, связями и запросами.

**2. How can you implement many-to-many relationships in SQLAlchemy?**

Use an association (junction) table with two foreign keys and define relationship (..., secondary=association_table)  
in both models with back_populates. If the relationship needs extra fields, use an association object  
(a mapped class instead of a plain table).

Через таблицу-связку с двумя внешними ключами и relationship(..., secondary=...) в обеих моделях с back_populates.  
Если в связи нужны дополнительные поля — использовать association object (отдельный mapped-класс).

**3. What is the role of a Session in SQLAlchemy and how it is different from the Connection?**

The Session is an ORM-level unit of work that manages object states, tracks changes, handles transactions,  
and flushes data to the database. It works with mapped objects.

A Connection is a lower-level Core object used to execute raw SQL and manage DBAPI connections directly.  
It does not track ORM objects or their state.

Session — это ORM-уровень (unit of work), который управляет состояниями объектов, отслеживает изменения,  
управляет транзакциями и выполняет flush в БД. Он работает с mapped-объектами.

Connection — это низкоуровневый объект Core для выполнения SQL и управления соединением с БД напрямую.  
Он не отслеживает ORM-объекты и их состояние.

**4. Can you detail the difference between a SQLAlchemy Core and SQLAlchemy ORM?**

SQLAlchemy Core is a lower-level SQL toolkit that works with tables, columns, and SQL expressions. You write queries using Python constructs that generate SQL. It gives full control and is close to raw SQL.

SQLAlchemy ORM is built on top of Core and works with Python classes mapped to database tables. It allows you to interact with the database using objects instead of writing SQL directly and manages relationships, identity map, and unit of work.

SQLAlchemy Core — это низкоуровневый инструмент для работы с SQL через таблицы, колонки и выражения. Запросы строятся через Python и генерируется SQL. Даёт полный контроль и близок к raw SQL.

SQLAlchemy ORM — это уровень выше Core, работает с Python-классами, сопоставленными с таблицами. Позволяет работать через объекты вместо прямого SQL и управляет связями, identity map и unit of work.

**5. Explain the purpose of declarative base in SQLAlchemy.**

Declarative Base is a base class for ORM models that combines table definition and class mapping in one place.  
It allows you to define database tables as Python classes, automatically registering them with the ORM and metadata.

Declarative Base — это базовый класс для ORM-моделей, который объединяет описание таблицы и маппинг класса.  
Позволяет определять таблицы БД как Python-классы и автоматически регистрирует их в ORM и metadata.

**6. How does SQLAlchemy perform mapping and what are its advantages?**

SQLAlchemy performs mapping by linking Python classes to database tables using a mapper (via Declarative or classical mapping).  
Class attributes are mapped to table columns, and relationships define links between tables.  
The ORM translates object operations into SQL statements.

Advantages: abstraction over SQL, cleaner and more maintainable code, automatic change tracking (unit of work), identity map,  
relationship handling, database portability, and reduced boilerplate.

SQLAlchemy выполняет маппинг, связывая Python-классы с таблицами БД через mapper (Declarative или classical mapping).  
Атрибуты класса сопоставляются с колонками, а relationships описывают связи.  
ORM преобразует операции с объектами в SQL-запросы.

Преимущества: абстракция над SQL, более чистый и поддерживаемый код, автоматическое отслеживание изменений (unit of work),  
identity map, удобная работа со связями, переносимость между БД и меньше шаблонного кода.

**7. How would you handle database migrations using SQLAlchemy?**

Use Alembic (SQLAlchemy’s migration tool). Configure it with your SQLAlchemy engine and Base.metadata, generate revisions  
with alembic revision --autogenerate, review/edit the script, then apply with alembic upgrade head. Run downgrades with  
alembic downgrade <rev> when needed.

Используют Alembic. Настраиваешь его на engine и Base.metadata, генерируешь миграции alembic revision --autogenerate,  
проверяешь/правишь файл, применяешь alembic upgrade head. Откат — alembic downgrade <rev>.

**8. Can you explain the concept of lazy loading in SQLAlchemy?**

Lazy loading means related data is not loaded from the database until it is actually accessed. When you access a relationship  
attribute, SQLAlchemy automatically issues a separate query to fetch that data. It helps reduce initial query size but can  
cause the N+1 query problem if not managed properly (can use joinedload/selectinload to optimize).

Lazy loading — это когда связанные данные загружаются не сразу, а только при обращении к атрибуту relationship. В этот момент  
SQLAlchemy выполняет отдельный запрос. Это уменьшает первоначальный объём данных, но может привести к проблеме N+1, если не  
контролировать (используют joinedload/selectinload для оптимизации).

**9. In what scenarios would you prefer using SQLAlchemy’s Core SQL over ORM?**

Prefer Core when you need fine-grained control over SQL, complex vendor-specific queries, heavy reporting/analytics, bulk  
inserts/updates where ORM overhead is costly, or when working with raw tables/views without a natural domain model. It’s  
also useful in performance-critical paths and when you want a thinner abstraction closer to SQL.

Core лучше, когда нужен точный контроль над SQL, сложные/специфичные для БД запросы, отчёты/аналитика, массовые  
insert/update без ORM-оверхода, или работа с таблицами/вьюхами без удобной объектной модели. Также — в критичных по  
производительности местах и когда нужен более “тонкий” слой близко к SQL.

**10. How does SQLAlchemy handle SQL injections and what methods does it use to prevent it?**

SQLAlchemy prevents SQL injection by using parameterized queries (bound parameters). Instead of inserting values directly  
into SQL strings, it sends them separately to the database driver, which safely escapes them. Both Core and ORM automatically  
use bind parameters when passing values. It also supports prepared statements via the DBAPI layer.

SQLAlchemy предотвращает SQL-инъекции за счёт параметризованных запросов (bind parameters). Значения не вставляются напрямую  
в строку SQL, а передаются отдельно в драйвер БД, который безопасно их экранирует. И Core, и ORM автоматически используют  
параметры. Также используются prepared statements через DBAPI.

**11. How can you implement one-to-one and one-to-many relationships in SQLAlchemy?**

One-to-many: put a foreign key on the “many” table pointing to the “one” table, then define relationship() on both sides  
(Parent.children, Child.parent) with back_populates (or backref).

One-to-one: same as one-to-many but enforce uniqueness on the foreign key (e.g., UniqueConstraint / unique=True) and set  
uselist=False on the relationship so SQLAlchemy treats it as a single object.

One-to-many: внешний ключ на стороне “many” на таблицу “one”, и relationship() с двух сторон (Parent.children, Child.parent)  
с back_populates (или backref).

One-to-one: то же, но FK делаем уникальным (unique=True / UniqueConstraint) и на relationship ставим uselist=False,  
чтобы связь была “один объект”.

**12. Can you illustrate a scenario where you would use the SQLAlchemy’s Hybrid Property?**

Use Hybrid Property when you need an attribute that works both at the Python object level and in SQL queries.

Example: a User model with first_name and last_name, and you define full_name as a hybrid property.
In Python, it returns first_name + " " + last_name.
In a query, it generates a SQL expression so you can filter like: session.query(User).filter(User.full_name == "John Smith").

Hybrid Property используют, когда нужно поле, которое работает и как обычный Python-атрибут, и как SQL-выражение в запросах.

Например, в модели User есть first_name и last_name, а full_name — это hybrid property.
В Python она возвращает объединённую строку.
В SQL-запросе она превращается в выражение, и можно писать фильтр: filter(User.full_name == "John Smith").

**13. How would you handle transactions and rollbacks in SQLAlchemy?**

Use the Session to manage transactions: commit on success and rollback on error. Typically wrap work in try/except,  
call session.commit(), and on exception do session.rollback() (and usually session.close() / use a context manager).  
You can also use with session.begin(): to auto-commit or auto-rollback.

Транзакции ведут через Session: при успехе commit, при ошибке rollback. Обычно try/except: session.commit(), в except —  
session.rollback() (и часто close() или контекстный менеджер). Можно with session.begin(): — тогда commit/rollback  
делается автоматически.

**14. What is the role of the MetaData class in SQLAlchemy?**

MetaData is a container that stores information about database tables, columns, constraints, and schema objects.  
It keeps track of table definitions and is used to create or drop tables (metadata.create_all() / drop_all()).  
In Declarative, all models share the same MetaData through Base.metadata.

MetaData — это контейнер, который хранит описание таблиц, колонок, ограничений и других объектов схемы. Он управляет  
структурой БД и используется для создания/удаления таблиц (metadata.create_all() / drop_all()). В Declarative все  
модели используют общий Base.metadata.

**15. How can you perform CRUD operations using SQLAlchemy?**

Create: instantiate a mapped object, session.add(obj) (or add_all), then session.commit().
Read: session.query(Model) / select(Model) with filter, get, first, all.
Update: load the object, change its attributes, then session.commit() (or use update() for bulk).
Delete: session.delete(obj) then session.commit() (or delete() for bulk).

Create: создать объект, session.add(obj) (или add_all), затем session.commit().
Read: query/select + filter, get, first, all.
Update: загрузить объект, изменить поля и commit (или update() для bulk).
Delete: session.delete(obj) и commit (или delete() для bulk).

**16. Can you explain the process of database reflection in SQLAlchemy?**

Database reflection is the process of loading existing database schema into SQLAlchemy objects. SQLAlchemy inspects  
the database (tables, columns, constraints) and automatically creates Table objects in MetaData using autoload_with=engine  
or MetaData.reflect(). It’s useful when working with an existing database without manually defining models.

Reflection — это процесс загрузки существующей схемы БД в объекты SQLAlchemy. Библиотека считывает таблицы, колонки и  
ограничения и автоматически создаёт объекты Table в MetaData через autoload_with=engine или MetaData.reflect().  
Используется при работе с уже существующей БД без ручного описания моделей.

**17. How can you use SQLAlchemy to query for data in a database?**

You can query using ORM or Core.

ORM: use select(Model) or session.query(Model) with filter, where, order_by, join, etc., then execute via session.execute()  
or call scalars().all(), first(), one(), etc.

Core: build a SQL expression with select(table) and execute it through a Connection or Session.

Можно делать запросы через ORM или Core.

ORM: использовать select(Model) или session.query(Model) с filter/where, order_by, join и выполнить через session.execute(),  
затем scalars().all(), first(), one() и т.д.

Core: создать выражение select(table) и выполнить через Connection или Session.

**18. What are the benefits of using SQLAlchemy for database manipulation over raw SQL queries?**

Benefits: abstraction over SQL and DB drivers, cleaner and more maintainable code, automatic parameter binding  
(protection from SQL injection), ORM features like identity map and unit of work, relationship handling, database portability,  
easier migrations (Alembic), and reduced boilerplate.

Преимущества: абстракция над SQL и драйверами БД, более чистый и поддерживаемый код, автоматическая параметризация  
(защита от SQL-инъекций), возможности ORM (identity map, unit of work), удобная работа со связями, переносимость между БД,  
удобные миграции (Alembic) и меньше шаблонного кода.

**19. How can you handle model inheritance in SQLAlchemy?**

SQLAlchemy supports three inheritance strategies:

- Single Table Inheritance — all classes share one table with a discriminator column to distinguish types.

- Joined Table Inheritance — base class has its own table, and each subclass has a separate table joined by a foreign key.

- Concrete Table Inheritance — each subclass has its own independent table with all fields duplicated.

SQLAlchemy поддерживает три стратегии наследования:

- Single Table Inheritance — все классы в одной таблице с discriminator-колонкой для определения типа.

- Joined Table Inheritance — у базового класса своя таблица, у наследников — отдельные таблицы, связанные через FK.

- Concrete Table Inheritance — у каждого наследника своя отдельная таблица со всеми полями.

**20. What is the role of SQLAlchemy’s Query API and how would you use it?**

The Query API is used to build and execute database queries in an ORM-style way. It allows filtering, joining, ordering,  
grouping, and loading related objects using Python methods instead of writing raw SQL.

You use it via session.query(Model) (or modern select(Model)), then chain methods like filter(), join(), order_by(), and  
finally execute with .all(), .first(), .one().

Query API — это инструмент для построения и выполнения ORM-запросов без написания raw SQL. Позволяет делать фильтрацию, join,  
сортировку, группировку и загрузку связанных данных через методы Python.

Используется через session.query(Model) (или современный select(Model)), далее цепочка filter(), join(), order_by(), и  
выполнение через .all(), .first(), .one().

**21. Can you explain how relationship loading techniques work in SQLAlchemy?**

SQLAlchemy provides different relationship loading strategies to control how related objects are fetched:

- Lazy loading (default) — loads related data only when the attribute is accessed (separate query).

- Joined loading (joinedload) — loads related data in the same query using JOIN.

- Select-in loading (selectinload) — loads related data in a separate query using IN with primary keys (efficient for collections).

- Subquery loading (subqueryload) — uses a subquery to load related data.

- Noload / Raiseload — disables loading or raises an error if accessed.

These strategies help balance performance and avoid the N+1 problem.

SQLAlchemy предоставляет разные стратегии загрузки связей:

- Lazy loading — данные загружаются при обращении к атрибуту (отдельный запрос).

- Joined loading (joinedload) — загрузка через JOIN в одном запросе.

- Select-in loading (selectinload) — отдельный запрос с IN по списку ключей (эффективно для коллекций).

- Subquery loading (subqueryload) — загрузка через подзапрос.

- Noload / Raiseload — отключает загрузку или вызывает ошибку при обращении.

Эти стратегии позволяют управлять производительностью и избегать проблемы N+1.

**22. How does SQLAlchemy handle relationships between tables and what are its advantages?**

SQLAlchemy handles relationships using relationship() combined with foreign keys. The foreign key defines the database-level link,  
and relationship() defines the ORM-level connection between mapped classes. It supports one-to-one, one-to-many, and many-to-many  
relationships, with options like back_populates, backref, and different loading strategies.

Advantages: automatic join handling, object navigation instead of manual SQL, identity map consistency, cascade operations,  
lazy/eager loading control, and cleaner domain modeling.

SQLAlchemy управляет связями через relationship() и внешние ключи. FK задаёт связь на уровне БД, а relationship() — на уровне ORM  
между классами. Поддерживаются one-to-one, one-to-many и many-to-many, с back_populates, backref и разными стратегиями загрузки.

Преимущества: автоматические join, навигация через объекты вместо ручного SQL, согласованность identity map, каскадные операции,  
контроль lazy/eager загрузки и более чистая модель предметной области.

**23. How can you implement polymorphism in SQLAlchemy?**

Implement polymorphism using SQLAlchemy’s inheritance mapping with a discriminator column.

Typical setup: define a base class with **mapper_args** like polymorphic_on (the discriminator column) and polymorphic_identity  
(type value). Each subclass sets its own polymorphic_identity. You can use single-table or joined-table inheritance depending on  
your schema.

Полиморфизм делают через ORM-наследование с discriminator-колонкой.

Обычно: в базовом классе в **mapper_args** задают polymorphic_on (колонка-дискриминатор) и polymorphic_identity (значение типа).  
В каждом наследнике — свой polymorphic_identity. Можно использовать single-table или joined-table inheritance.

**24. Could you explain how you handle complex queries and joins using SQLAlchemy?**

For complex queries, I prefer the select() API: build queries step-by-step with select(), join() / outerjoin(), where(), order_by(),  
group_by(), and aggregates (func.\*). For multi-table filtering I join explicitly and use aliasing (aliased()) when the same table is  
joined multiple times. For performance and correctness I control relationship loading (joinedload/selectinload) and watch for N+1.

Для сложных запросов обычно использую select(): собираю запрос по шагам через select(), join() / outerjoin(), where(), order_by(),  
group_by() и агрегаты (func.\*). Когда одну таблицу нужно join-ить несколько раз — применяю алиасы (aliased()). Для производительности  
контролирую загрузку связей (joinedload/selectinload) и избегаю N+1.

**25. How do you handle event listening in SQLAlchemy and explain a scenario where it might be useful?**

SQLAlchemy provides an event system via event.listen() or decorators like @event.listens_for(). You can attach listeners to models,  
mappers, sessions, engines, or connections (e.g., before_insert, after_update, before_commit).

Example scenario: automatically set audit fields (created_at, updated_at) before insert/update, validate data before flush, log SQL  
execution, or enforce business rules at the ORM level.

В SQLAlchemy есть система событий через event.listen() или декоратор @event.listens_for(). Слушатели можно навешивать на модели,  
мапперы, сессии, engine или connection (например, before_insert, after_update, before_commit).

Пример: автоматически заполнять поля аудита (created_at, updated_at), валидировать данные перед flush, логировать SQL или применять  
бизнес-правила на уровне ORM.
