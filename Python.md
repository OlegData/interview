# Python

**1. What is Python, what are the benefits of using it, and what do you understand of PEP 8?**

---

Python is a high-level, interpreted, dynamically typed programming language focused on readability and simplicity. It supports multiple paradigms  
(OOP, procedural, functional) and has a large standard library and ecosystem.

Benefits: clean and readable syntax, fast development speed, huge community and libraries, cross-platform support, strong ecosystem for web,  
data science, automation, and scripting.

PEP 8 is the official style guide for Python code. It defines naming conventions (snake_case for functions/variables, PascalCase for classes),  
indentation (4 spaces), line length limits, import ordering, spacing rules, and general formatting standards to keep code consistent and readable.

Python — это высокоуровневый, интерпретируемый, динамически типизированный язык программирования с акцентом на читаемость и простоту. Поддерживает  
несколько парадигм (ООП, процедурную, функциональную) и имеет большую стандартную библиотеку.

Преимущества: простой и понятный синтаксис, высокая скорость разработки, большое сообщество и экосистема библиотек, кроссплатформенность, сильные  
позиции в веб-разработке, data science и автоматизации.

PEP 8 — это официальный гайд по стилю кода Python. Он определяет соглашения по именованию (snake_case для функций и переменных, PascalCase для классов),  
отступы (4 пробела), длину строки, порядок импортов, правила пробелов и общий стиль для поддержания читаемости и единообразия кода.

**2. What is the statement that can be used in Python if the program requires no action but requires it syntactically?**

---

The statement is pass. It is a no-op statement — it does nothing but is used as a placeholder when a statement is syntactically required  
(e.g., in empty functions, classes, loops, or conditionals).

Оператор — pass. Он ничего не делает, но используется как заглушка, когда по синтаксису требуется инструкция (например, в пустой функции, классе,  
цикле или условии).

**3. What’s the process to get the home directory using ‘~’ in Python?**

---

Use `os.path.expanduser("~") or Path.home() from pathlib.`

Example:

```
os.path.expanduser("~")

from pathlib import Path; Path.home()
```

Использовать `os.path.expanduser("~")` или `Path.home()` из `pathlib`.

Пример:

```
os.path.expanduser("~")

from pathlib import Path; Path.home()
```

**4. What are the built-in types available in Python?**

---

Immutable types:

- int, float, complex, bool, str, tuple, range, frozenset, bytes, NoneType

Mutable types:

- list, dict, set, bytearray, memoryview

Да, на интервью лучше делить на изменяемые и неизменяемые.

Неизменяемые (immutable):

- int, float, complex, bool, str, tuple, range, frozenset, bytes, NoneType

Изменяемые (mutable):

- list, dict, set, bytearray, memoryview

**5. How to find bugs or perform static analysis in a Python application?**

---

Use linters and type checkers: ruff / flake8 / pylint for code issues and style, mypy or pyright for static type analysis.  
Use formatters like black and import sorting (isort or ruff format) to keep consistency. Also use security/static scanners  
like bandit, plus tests and coverage (pytest, coverage) to catch issues early (often run via pre-commit and CI).

Для статанализа и поиска багов: линтеры и тайпчекеры — ruff / flake8 / pylint, для типов — mypy или pyright. Форматирование —  
black, сортировка импортов — isort или ruff. Для security-скана — bandit. Плюс тесты и покрытие (pytest, coverage), обычно  
через pre-commit и CI.

**6. When is the Python decorator used?**

---

A decorator is used when you want to extend or modify the behavior of a function or method without changing its source code.  
It wraps a function and adds functionality before or after its execution.

Common use cases: logging, authentication/authorization, caching, validation, measuring execution time, transaction handling.

Декоратор используют, когда нужно расширить или изменить поведение функции/метода без изменения её кода. Он оборачивает  
функцию и добавляет логику до или после её выполнения.

Частые случаи: логирование, авторизация, кэширование, валидация, измерение времени выполнения, управление транзакциями.

**7. What is the principal difference between a list and a tuple?**

---

The main difference is mutability: a list is mutable (can be changed after creation), while a tuple is immutable  
(cannot be modified).

Lists use [], tuples use (). Tuples are generally faster and can be used as dictionary keys (if they contain only  
immutable elements), while lists cannot.

Главное различие — изменяемость: list изменяемый (можно менять элементы), tuple неизменяемый (нельзя изменить  
после создания).

List создаётся через [], tuple — через (). Tuple обычно быстрее и может использоваться как ключ словаря (если  
содержит только immutable элементы), list — нет.

**8. How does Python handle memory management?**

---

Python uses automatic memory management with reference counting and a garbage collector.

Each object has a reference counter; when it drops to zero, the memory is released immediately.  
To handle circular references, Python also uses a cyclic garbage collector that detects and frees  
objects involved in reference cycles.

Additionally, Python has a private heap for object allocation managed by the Python memory manager.

Python использует автоматическое управление памятью через reference counting и garbage collector.

У каждого объекта есть счётчик ссылок; когда он становится равен нулю, память освобождается.  
Для обработки циклических ссылок используется циклический сборщик мусора, который находит и удаляет  
объекты в циклах.

Также Python использует собственную кучу (private heap), управляемую внутренним менеджером памяти.

**9. What are the principal differences between lambda and def?**

---

lambda creates an anonymous function in a single expression and is limited to one expression  
(no statements). It’s typically used for short, simple functions (e.g., in map, filter, sorted).

def defines a named function, can contain multiple statements, annotations, docstrings, and complex logic.  
It’s used for full-featured functions.

lambda — это анонимная функция из одного выражения (только expression, без операторов). Обычно  
используется для коротких простых функций.

def — именованная функция, может содержать несколько операторов, аннотации, docstring и сложную  
логику. Используется для полноценных функций.

**10. What is a built-in function that Python uses to iterate over a number sequence?**

---

The built-in function is range(). It generates a sequence of numbers and is commonly used in for loops.

Example: for i in range(5):

Встроенная функция — range(). Она создаёт числовую последовательность и обычно используется в цикле for.

Пример: for i in range(5):

**11. What are the optional statements possible inside a try-except block in Python?**

---

The optional clauses inside a try block are else and finally.

- else runs if no exception occurs.

- finally always runs, whether an exception occurred or not (used for cleanup).

В блоке try опционально можно использовать else и finally.

- else выполняется, если исключения не было.

- finally выполняется всегда, независимо от наличия исключения (обычно для очистки ресурсов).

**12. What is a string in Python?**

---

A string in Python is an immutable sequence of Unicode characters used to represent text.  
It is defined using single quotes, double quotes, or triple quotes for multi-line strings.

Strings support indexing, slicing, and many built-in methods for manipulation.

Строка в Python — это неизменяемая последовательность Unicode-символов, используемая для  
представления текста. Она создаётся с помощью одинарных, двойных или тройных кавычек  
(для многострочных строк).

Строки поддерживают индексацию, срезы и множество встроенных методов для работы с текстом.

**13. What is slicing in Python?**

---

Slicing is a way to extract a portion of a sequence (like a list, tuple, or string) using  
the syntax sequence[start:stop:step].
start is inclusive, stop is exclusive, and step defines the interval.

Example: my_list[1:4]

Срез (slicing) — это способ получить часть последовательности (list, tuple, string) с помощью  
синтаксиса sequence[start:stop:step].
start включается, stop не включается, step задаёт шаг.

**14. What is Docstring in Python?**

---

A docstring is a string literal used to document a module, class, function, or method.  
It is written as the first statement inside the definition, usually using triple quotes.  
It describes what the object does and can be accessed via \_\_doc\_\_ or the help() function.

Docstring — это строка документации для модуля, класса, функции или метода. Она размещается  
первой строкой внутри определения, обычно в тройных кавычках. Описывает назначение объекта и  
доступна через \_\_doc\_\_ или help().

**15. What is a function in Python programming?**

---

A function in Python is a reusable block of code that performs a specific task. It is defined  
using the def keyword, can accept parameters, and may return a value using return.

Functions help organize code, improve readability, and promote reusability.

Функция в Python — это переиспользуемый блок кода, который выполняет определённую задачу. Она  
определяется с помощью def, может принимать параметры и возвращать значение через return.

Функции помогают структурировать код, повышают читаемость и обеспечивают переиспользуемость.

**16. What is the return keyword used in Python?**

---

The return keyword is used to exit a function and send a value back to the caller. When return  
is executed, the function stops immediately. If no value is specified, the function returns None  
by default.

return используется для выхода из функции и возврата значения вызывающему коду. При выполнении  
return функция сразу прекращает работу. Если значение не указано, по умолчанию возвращается None.

**17. What is “Call by Value” in Python?**

---

Python does not use pure call by value or call by reference — it uses call by object reference  
(also called call by assignment).

When a function is called, the reference to the object is passed.
If the object is immutable, it behaves like call by value (you can’t modify the original).
If the object is mutable, changes inside the function can affect the original object.

В Python нет чистого call by value или call by reference — используется call by object reference  
(call by assignment).

В функцию передаётся ссылка на объект.
Если объект неизменяемый — поведение похоже на call by value.
Если изменяемый — изменения внутри функции могут повлиять на оригинальный объект.

**18. What is “Call by Reference” in Python?**

---

Python does not support true call by reference. It uses call by object reference (call by assignment).

The function receives a reference to the object, but you cannot rebind the caller’s variable. You can  
modify the object if it’s mutable, but reassignment inside the function does not affect the original  
variable.

В Python нет настоящего call by reference. Используется call by object reference (call by assignment).

Функция получает ссылку на объект, но нельзя изменить саму переменную у вызывающей стороны. Можно  
изменить объект, если он изменяемый, но переназначение внутри функции не меняет исходную переменную.

**19. What is the purpose of the id() function in Python?**

---

The id() function returns the unique identity of an object. In CPython, it represents the memory address  
where the object is stored. It is often used to check whether two variables reference the same object.

Функция id() возвращает уникальный идентификатор объекта. В CPython это обычно адрес памяти объекта.  
Используется для проверки, ссылаются ли две переменные на один и тот же объект.

**20. What does the \_\_name\_\_ do in Python?**

---

`__name__` is a special built-in variable that indicates how a Python file is being executed.

If a file is run directly, `__name__` == "`__main__`".
If it is imported as a module, `__name__` equals the module’s name.

It is commonly used to prevent certain code from running when the file is imported.

`__name__` — это специальная встроенная переменная, которая показывает, как запускается файл.

Если файл запущен напрямую, `__name__` == "`__main__`".
Если импортирован как модуль, `__name__` равен имени модуля.

Обычно используется, чтобы код выполнялся только при прямом запуске файла.

**21. What is GIL in Python language?**

---

The GIL (Global Interpreter Lock) is a mutex in CPython that allows only one thread to execute Python  
bytecode at a time. It prevents true parallel execution of threads in CPU-bound programs.

It simplifies memory management and makes CPython thread-safe, but limits multi-threaded performance  
for CPU-intensive tasks (multiprocessing can be used instead).

GIL (Global Interpreter Lock) — это механизм в CPython, который позволяет выполнять байткод Python  
только одному потоку одновременно. Он не даёт потокам работать параллельно в CPU-bound задачах.

Он упрощает управление памятью и делает интерпретатор потокобезопасным, но ограничивает производительность  
при вычислительно тяжёлых задачах (вместо этого используют multiprocessing).

**22. How is the Python thread safe?**

---

In CPython, thread safety is mainly ensured by the GIL (Global Interpreter Lock), which allows only one  
thread to execute Python bytecode at a time. This prevents race conditions at the interpreter level for  
memory management.

However, it does not make your application logic automatically thread-safe. For shared mutable data, you  
still need synchronization primitives like Lock, RLock, Semaphore, etc., from the threading module.

В CPython потокобезопасность обеспечивается в основном за счёт GIL (Global Interpreter Lock), который  
позволяет выполнять байткод только одному потоку одновременно. Это защищает управление памятью на уровне  
интерпретатора.

Но это не делает логику программы автоматически потокобезопасной. При работе с общими изменяемыми данными  
нужно использовать примитивы синхронизации (Lock, RLock, Semaphore и т.д.) из модуля threading.

**23. How does Python manage memory?**

---

Python manages memory automatically using reference counting and a cyclic garbage collector.

Each object has a reference counter. When the reference count drops to zero, the memory is  
immediately freed. To handle circular references, Python uses a cyclic garbage collector that detects  
and cleans up unreachable object cycles.

Memory is allocated in a private heap managed by Python’s memory manager (PyMalloc in CPython).

Python управляет памятью автоматически через reference counting и циклический garbage collector.

У каждого объекта есть счётчик ссылок. Когда он становится равным нулю, память освобождается.  
Для обработки циклических ссылок используется циклический сборщик мусора.

Память выделяется в private heap, которым управляет внутренний менеджер памяти Python (PyMalloc в CPython).

**24. What is a tuple in Python?**

---

A tuple in Python is an immutable ordered collection of elements. It can store different data types  
and allows indexing and slicing. Tuples are defined using parentheses () or by separating values with commas.

Because they are immutable, tuples can be used as dictionary keys (if all elements are immutable).

Tuple в Python — это неизменяемая упорядоченная коллекция элементов. Она может содержать разные типы  
данных и поддерживает индексацию и срезы. Создаётся с помощью () или просто через запятые.

Так как tuple неизменяемый, его можно использовать как ключ словаря (если все элементы тоже immutable).

**25. What is a dictionary in Python programming?**

---

A dictionary in Python is a built-in mutable mapping type that stores data as key–value pairs. Keys must  
be unique and immutable, while values can be of any type. Dictionaries are defined using {}.

They provide fast lookup, insertion, and deletion by key.

Dictionary в Python — это встроенный изменяемый тип отображения (mapping), который хранит данные в виде  
пар ключ–значение. Ключи должны быть уникальными и неизменяемыми, значения могут быть любого типа.
Создаётся с помощью {}.

Обеспечивает быстрый доступ, добавление и удаление по ключу.

**26. What is the set object in Python?**

---

A set in Python is a built-in mutable, unordered collection of unique elements. It does not allow duplicate  
values and supports mathematical set operations like union, intersection, difference, and symmetric difference.

Sets are created using {} (with elements) or the set() constructor.

Set в Python — это встроенная изменяемая, неупорядоченная коллекция уникальных элементов. Дубликаты не  
допускаются. Поддерживает операции множеств: объединение, пересечение, разность и симметрическую разность.

Создаётся с помощью {} (с элементами) или конструктора set().

**27. What is Class in Python?**

---

A class in Python is a blueprint for creating objects. It defines attributes (data) and methods (functions)  
that describe the behavior of the objects. A class is defined using the class keyword.

Classes are the foundation of object-oriented programming (OOP) in Python.

Класс в Python — это шаблон для создания объектов. Он определяет атрибуты (данные) и методы (функции),  
которые описывают поведение объектов. Объявляется с помощью ключевого слова class.

Классы — основа объектно-ориентированного программирования (ООП) в Python.

**28. What are Attributes and Methods in a Python class?**

---

Attributes are variables that belong to a class or its instances. They store the state or data of an object  
(instance attributes and class attributes).

Methods are functions defined inside a class that describe the behavior of its objects. They usually operate  
on the object’s attributes and take self as the first parameter.

Атрибуты — это переменные, принадлежащие классу или его экземплярам. Они хранят состояние или данные объекта  
(атрибуты экземпляра и атрибуты класса).

Методы — это функции, определённые внутри класса, которые описывают поведение объекта. Обычно они работают с  
атрибутами и принимают self как первый параметр.

**29. How to assign values for the Class attributes at runtime?**

---

You can assign class attributes at runtime either directly through the class or dynamically using setattr().

Example:

```python
MyClass.attribute = value

setattr(MyClass, "attribute", value)
```

This changes the attribute for the class itself (affects all instances unless overridden).

Значения атрибутам класса во время выполнения можно присвоить напрямую через класс или через setattr().

Это изменяет атрибут на уровне класса (влияет на все экземпляры, если не переопределено в объекте).

**30. What is Inheritance in Python programming?**

---

Inheritance is an OOP feature where a class (child/subclass) derives from another class (parent/base class)  
and inherits its attributes and methods. It allows code reuse and extension of existing functionality.

It is defined by passing the parent class in parentheses: class Child(Parent):

Наследование — это механизм ООП, при котором один класс (дочерний) наследует атрибуты и методы другого класса  
(родительского). Это позволяет переиспользовать код и расширять функциональность.

Объявляется через указание родительского класса в скобках: class Child(Parent):

**31. What is Composition in Python?**

---

Composition is an OOP concept where one class contains an instance of another class as an attribute, instead  
of inheriting from it. It represents a “has-a” relationship and promotes flexibility and loose coupling.

Example: a Car class containing an Engine object.

Композиция — это принцип ООП, при котором один класс содержит объект другого класса как атрибут, а не наследуется  
от него. Это отношение типа “has-a” и даёт большую гибкость и слабую связанность.

Пример: класс Car, который содержит объект Engine.

**32. What are Errors and Exceptions in Python programs?**

---

Errors are problems in a program that prevent it from running correctly. They can be syntax errors (detected before  
execution) or runtime errors.

Exceptions are runtime errors that occur during program execution and can be handled using try, except, else, and  
finally. Handling exceptions allows the program to continue running instead of crashing.

Ошибки (Errors) — это проблемы в программе, которые мешают её корректному выполнению. Это могут быть синтаксические  
ошибки или ошибки времени выполнения.

Исключения (Exceptions) — это ошибки, возникающие во время выполнения программы, которые можно обработать с помощью  
try, except, else, finally. Обработка исключений позволяет программе не завершаться аварийно.

**33. How do you raise exceptions for a predefined condition in Python?**

---

You raise exceptions using the raise keyword with a specific exception class.

Example:

```python
raise ValueError("Invalid input")
```

You can also define custom exceptions by inheriting from Exception.

Исключения вызываются с помощью ключевого слова raise и указания класса исключения.

Также можно создавать собственные исключения, наследуясь от Exception.

**34. What are Python Iterators?**

---

Python iterators are objects that implement the iterator protocol: they have \_\iter\_\_() and \_\next\_\_() methods.  
They produce items one at a time and raise StopIteration when no more items are available.

Iterators are used in loops like for and allow lazy iteration (values are generated on demand).

Итераторы в Python — это объекты, реализующие протокол итератора: методы \_\iter\_\_() и \_\next\_\_(). Они возвращают  
элементы по одному и вызывают StopIteration, когда элементы заканчиваются.

Используются в цикле for и позволяют ленивую (lazy) итерацию — значения создаются по мере необходимости.

**35. What is the difference between an Iterator and an Iterable?**

---

An Iterable is an object that can return an iterator. It implements the `__iter__`() method and can be used  
in a for loop (e.g., list, tuple, string).

An Iterator is an object that actually produces the next value. It implements both `__iter__`() and `__next__`()  
and keeps state during iteration.

Iterable можно перебирать — он реализует `__iter__`() и возвращает итератор (например, list, tuple, string).

Iterator — это объект, который возвращает элементы по одному. Он реализует `__iter__`() и `__next__`() и хранит  
состояние во время итерации.

**36. What are Python Generators?**

---

Python generators are a special type of iterator that produce values lazily using the yield keyword.  
Instead of returning all values at once, they generate them one by one and maintain their state between calls.

They are memory-efficient and commonly used for large datasets or infinite sequences.

Генераторы в Python — это особый тип итераторов, которые создают значения лениво с помощью yield.  
Они не возвращают все данные сразу, а генерируют их по одному и сохраняют своё состояние между вызовами.

Они экономят память и часто используются для больших наборов данных или бесконечных последовательностей.

**37. What are metaclasses in Python, and when would you use them in your code?**

Metaclasses in Python are classes that define how other classes are created. In Python, everything is an object, including classes. A metaclass controls the process of class creation (class construction). Normally, classes are created by the default metaclass type.

Example:

```python
class MyMeta(type):
def _new__(cls, name, bases, attrs):
print("Creating class:", name)
return super()._new__(cls, name, bases, attrs)

class MyClass(metaclass=MyMeta):
pass
```

When MyClass is defined, the metaclass intercepts and customizes its creation.

Metaclasses are used when you need to modify or control class behavior automatically, for example:

- Enforcing coding rules in classes

- Automatically registering classes (plugin systems)

- Implementing ORMs (like Django models)

- Creating APIs or frameworks

- Injecting methods or attributes into classes

In practice, metaclasses are rarely needed in normal application code and are mostly used in frameworks and advanced libraries.

Метаклассы в Python — это классы, которые управляют созданием других классов. В Python всё является объектом, включая классы. Метакласс контролирует процесс создания класса. По умолчанию используется метакласс type.

Метаклассы применяются, когда нужно автоматически изменить поведение классов, например:

- Проверять правила при создании классов

- Автоматически регистрировать классы (plugin системы)

- Реализовывать ORM (например, Django)

- Строить фреймворки и DSL

В обычном коде метаклассы используются редко и чаще встречаются во фреймворках.

**38. Explain the purpose of the contextlib module and how it is used for managing resources in Python.**

---

The contextlib module provides utilities for creating and working with context managers, which help manage resources safely using the with statement. It ensures that resources (files, database connections, locks, etc.) are properly acquired and released, even if an exception occurs. A common way to create a context manager with contextlib is using the @contextmanager decorator.

Example:

```python
from contextlib import contextmanager

@contextmanager
def open_file(name):
    f = open(name, "w")
    try:
        yield f
    finally:
        f.close()

with open_file("test.txt") as f:
    f.write("Hello")
```

Key benefits:

- Simplifies resource management

- Ensures cleanup with finally

- Makes code cleaner and safer

Common tools in contextlib include:

- contextmanager

- closing()

- suppress()

- redirect_stdout()

Модуль contextlib используется для создания и работы с контекстными менеджерами. Контекстные менеджеры позволяют безопасно управлять ресурсами через конструкцию with. Они гарантируют, что ресурсы (файлы, соединения с БД, блокировки и т.д.) будут корректно освобождены, даже если возникнет ошибка. Обычно контекстный менеджер создаётся с помощью декоратора @contextmanager.

Преимущества:

- Упрощает управление ресурсами

- Гарантирует освобождение ресурсов

- Делает код чище и безопаснее.

**39. What is method resolution order (MRO) in Python, and how is it determined for classes with multiple inheritance?**

---

Method Resolution Order (MRO) is the order in which Python searches for a method or attribute in a class hierarchy. It is especially important in multiple inheritance, where a class inherits from more than one parent class.

Python determines MRO using the C3 linearization algorithm, which ensures:

- A consistent search order

- Parents are checked before grandparents

- The order of base classes is preserved

Example:

```python
class A:
    pass

class B(A):
    pass

class C(A):
    pass

class D(B, C):
    pass
```

For class D, the MRO is: `D → B → C → A → object`

You can view the MRO using: `D.__mro__` or `D.mro()`

MRO (Method Resolution Order) — это порядок, в котором Python ищет методы и атрибуты в иерархии классов. Это особенно важно при множественном наследовании.

Python использует алгоритм C3 linearization, который:

- гарантирует последовательный порядок поиска

- сначала проверяет родителей, затем их родителей

- сохраняет порядок базовых классов

Посмотреть MRO можно так: `ClassName.mro()` или `ClassName.__mro__.`

**40. How can you work with binary data in Python, and what are the benefits of using the struct module?**

---

Binary data in Python can be handled using bytes, bytearray, and binary file modes (rb, wb). Numbers can also be converted to and from bytes using int.to_bytes() and int.from_bytes().
The struct module allows packing Python values into binary format and unpacking binary data into Python types using format strings.

Benefits of struct:

- Efficient conversion between Python types and binary data

- Control over byte order, size, and alignment

- Useful for network protocols, binary files, and low-level data processing

С бинарными данными в Python работают через bytes, bytearray и файлы в бинарном режиме (rb, wb). Числа можно преобразовывать в байты и обратно с помощью int.to_bytes() и int.from_bytes(). Модуль struct позволяет упаковывать значения Python в бинарный формат и распаковывать бинарные данные обратно в типы Python с помощью строки формата.

Преимущества struct:

- Быстрое преобразование между типами Python и бинарными данными

- Контроль порядка байтов, размера и выравнивания

- Полезен при работе с сетевыми протоколами, бинарными файлами и низкоуровневыми форматами данных

**41. What is the GIL, and how does it affect CPU-bound and I/O-bound tasks differently?**

---

The GIL (Global Interpreter Lock) is a mechanism in CPython that allows only one thread to execute Python bytecode at a time. It is used to simplify memory management and make the interpreter thread-safe. For CPU-bound tasks, the GIL becomes a bottleneck because multiple threads cannot run Python code in parallel on multiple CPU cores. In such cases, multiprocessing is usually used instead of multithreading. For I/O-bound tasks, the GIL is less of a problem because it is released during I/O operations (such as network requests or file access). This allows other threads to run while one thread is waiting for I/O, making multithreading effective for these tasks.

GIL (Global Interpreter Lock) — это механизм в CPython, который позволяет только одному потоку одновременно выполнять Python bytecode. Он упрощает управление памятью и делает интерпретатор потокобезопасным. Для CPU-bound задач GIL становится узким местом, потому что несколько потоков не могут выполнять Python-код параллельно на разных ядрах процессора. Поэтому в таких случаях чаще используют multiprocessing. Для I/O-bound задач GIL менее проблемен, потому что он освобождается во время операций ввода-вывода (например, сетевые запросы или работа с файлами). Пока один поток ждёт I/O, другие могут выполняться, поэтому multithreading работает эффективно.

**42. What are the key differences between the multiprocessing and threading modules in Python, and when would you use each for parallelism?**

---

threading uses multiple threads within a single process. Threads share the same memory space but are limited by the GIL, so only one thread executes Python bytecode at a time.

multiprocessing creates separate processes. Each process has its own Python interpreter and memory space, so it is not limited by the GIL and can run on multiple CPU cores.

When to use them:

- threading — for I/O-bound tasks (network calls, file operations, waiting for external services).

- multiprocessing — for CPU-bound tasks (heavy calculations, data processing) where true parallel execution on multiple cores is needed.

Key differences:

- Memory: shared in threads, separate in processes

- GIL: affects threads, not processes

- Overhead: threads are lighter; processes are heavier but allow real parallelism

threading использует несколько потоков внутри одного процесса. Потоки разделяют одну память, но ограничены GIL, поэтому одновременно выполняется только один Python bytecode.

multiprocessing создаёт отдельные процессы. У каждого процесса свой интерпретатор Python и своя память, поэтому они не ограничены GIL и могут работать на разных ядрах процессора.

Когда использовать:

- threading — для I/O-bound задач (сетевые запросы, работа с файлами, ожидание внешних сервисов).

- multiprocessing — для CPU-bound задач (тяжёлые вычисления, обработка данных), где нужна реальная параллельность.

Основные различия:

- Память: общая у потоков, отдельная у процессов

- GIL: влияет на потоки, не влияет на процессы

- Нагрузка: потоки легче, процессы тяжелее, но дают настоящую параллельность

**43. Describe the concept of ABCs (Abstract Base Classes) in Python and when you would use them.**

**Abstract Base Classes (ABCs)** in Python define a common interface for a group of related classes. They are created using the abc module and allow you to declare abstract methods that must be implemented by subclasses.

An abstract class cannot be instantiated directly. Any subclass must implement all abstract methods, otherwise it cannot be instantiated.

When to use them:

- To enforce a consistent interface across different classes

- To define a base API for frameworks or libraries

- When designing systems where multiple implementations must follow the same contract

Example: defining a base class for different storage systems (file storage, database storage, cloud storage) where each must implement methods like save() or load().

**Abstract Base Classes (ABC)** в Python задают общий интерфейс для группы связанных классов. Они создаются с помощью модуля abc и позволяют объявлять абстрактные методы, которые должны быть реализованы в подклассах.

Абстрактный класс нельзя создать напрямую. Подкласс обязан реализовать все абстрактные методы, иначе его тоже нельзя будет создать.

Когда используются:

- Чтобы обеспечить единый интерфейс для разных классов

- Для определения базового API в библиотеках или фреймворках

- При проектировании систем, где разные реализации должны соблюдать один контракт

Пример: базовый класс для разных типов хранилищ (файловое, база данных, облако), где каждый должен реализовать методы save() или load().

**44. What are Python descriptors, and how are they used to customize attribute access in classes?**

---

Descriptors are objects that define how attribute access is managed in a class. They implement special methods \_\_get\_\_, \_\_set\_\_, or \_\_delete\_\_. When an attribute is accessed on an instance, Python calls these descriptor methods instead of directly accessing the attribute.

How they work:

- \_\_get\_\_(self, instance, owner) — controls attribute reading

- \_\_set\_\_(self, instance, value) — controls attribute assignment

- \_\_delete\_\_(self, instance) — controls attribute deletion

Descriptors are used to customize attribute behavior, such as validation, computed attributes, lazy loading, or access control. They are also the mechanism behind features like @property, @classmethod, @staticmethod, and methods in classes.

Дескрипторы — это объекты, которые управляют доступом к атрибутам класса. Они реализуют специальные методы \_\_get\_\_, \_\_set\_\_ и \_\_delete\_\_. Когда происходит доступ к атрибуту объекта, Python вызывает методы дескриптора вместо прямого обращения к атрибуту.

Как работают:

- \_\_get\_\_(self, instance, owner) — управляет чтением атрибута

- \_\_set\_\_(self, instance, value) — управляет присваиванием

- \_\_delete\_\_(self, instance) — управляет удалением

Дескрипторы позволяют настраивать поведение атрибутов: делать валидацию, вычисляемые свойства, ленивую загрузку или контроль доступа. Также на механизме дескрипторов построены @property, @classmethod, @staticmethod и методы классов.

**45. How can you create and work with asynchronous code in Python, and what is the purpose of the await keyword?**

---

Asynchronous code in Python is created using async and await, mainly with the asyncio library. Functions defined with async def return coroutines that can run concurrently in an event loop. Tasks are scheduled in the event loop and switch execution while waiting for I/O operations, allowing efficient handling of many concurrent operations. The await keyword pauses the execution of the coroutine until the awaited coroutine or task completes, without blocking the whole program. During this time, the event loop can run other tasks.

Typical use cases:

- Network requests

- Working with APIs

- Asynchronous databases

- High-concurrency servers

Асинхронный код в Python создаётся с помощью async и await, чаще всего с библиотекой asyncio. Функции, объявленные через async def, возвращают корутины, которые выполняются внутри event loop. Задачи планируются в event loop и переключаются между собой во время ожидания операций ввода-вывода, что позволяет эффективно обрабатывать большое количество параллельных операций. Ключевое слово await приостанавливает выполнение корутины до завершения другой корутины или задачи, не блокируя всю программу. В это время event loop может выполнять другие задачи.

Типичные применения:

- Сетевые запросы

- Работа с API

- Асинхронные базы данных

- Серверы с высокой конкурентностью

**47. What are the differences between the os.path and pathlib modules in Python for file and directory manipulation?**

---

os.path is an older module that works with file paths as strings and provides functions for manipulating them, such as join(), exists(), dirname(), and basename().

pathlib is a newer, object-oriented module that represents paths as Path objects and provides methods for working with files and directories in a more readable way.

Key differences:

- os.path uses string-based functions, while pathlib uses objects and methods

- pathlib provides a cleaner and more intuitive API

- pathlib integrates path operations and file system operations in one interface

- pathlib supports operator overloading (e.g., path / "file.txt")

Example:

```python
os.path.join("folder", "file.txt")
Path("folder") / "file.txt"
```

In modern Python code, pathlib is generally preferred because it is more readable and easier to use.

os.path — это старый модуль, который работает с путями как со строками и предоставляет функции для их обработки: join(), exists(), dirname(), basename().

pathlib — более новый модуль с объектно-ориентированным подходом. Пути представлены объектами Path, у которых есть методы для работы с файлами и директориями.

Основные различия:

- os.path работает со строками, pathlib — с объектами

- pathlib имеет более читаемый и удобный API

- pathlib объединяет операции над путями и файловой системой

- pathlib поддерживает оператор / для построения путей

Пример:

```python
os.path.join("folder", "file.txt")
Path("folder") / "file.txt"
```

В современном Python чаще используют pathlib, потому что код получается чище и удобнее.

**48. How do you serialize and deserialize Python objects, and what is the purpose of libraries like pickle and json for data interchange?**

---

Serialization is the process of converting a Python object into a format that can be stored or transmitted (file, network).
Deserialization is the reverse process — converting that format back into a Python object.

Two common libraries are pickle and json.

pickle:

Serializes almost any Python object (lists, dictionaries, classes, etc.) Produces a Python-specific binary format Mainly used for saving Python objects internally Not safe for untrusted data

json:

Serializes data into a text format (JSON) Works with basic types: dict, list, str, int, float, bool, None Language-independent and widely used for APIs and data exchange

When to use:

- pickle — internal Python object storage

- json — data interchange between systems or services

Сериализация — это преобразование Python-объекта в формат, который можно сохранить или передать (файл, сеть).
Десериализация — обратный процесс, восстановление объекта из этого формата.
Две распространённые библиотеки — pickle и json.

pickle:

Сериализует почти любые Python-объекты (списки, словари, классы и т.д.)Создаёт бинарный формат, специфичный для Python
Используется для внутреннего хранения объектов Python Небезопасен для данных из недоверенных источников

json:

Сериализует данные в текстовый формат JSON Работает с базовыми типами: dict, list, str, int, float, bool, None Независим от языка и широко используется в API и обмене данными

Когда использовать:

- pickle — для хранения Python-объектов внутри Python

- json — для обмена данными между системами или сервисами

**49. What is the purpose of the unittest library in Python, and how can you write unit tests for your code?**

---

The unittest library is Python’s built-in framework for writing and running automated tests. It helps verify that individual parts of the code (units such as functions or classes) work correctly. To write unit tests, you create a class that inherits from unittest.TestCase and define test methods that start with test\_. Inside these methods you call the code and check results using assertions like assertEqual, assertTrue, or assertRaises.

Example flow:

- import unittest

- create a test class inheriting from TestCase

- write test methods

- run tests using unittest.main()

Benefits:

- automatic testing of code behavior

- easier debugging and regression detection

- safer refactoring

unittest — это встроенный фреймворк Python для написания и запуска автоматических тестов. Он позволяет проверять, что отдельные части программы (функции или классы) работают правильно. Юнит-тесты пишутся в классе, который наследуется от unittest.TestCase. Методы тестов должны начинаться с test\_. Внутри них вызывается код и проверяются результаты через проверки (assertions) например assertEqual, assertTrue, assertRaises.

Основная схема:

- импортировать unittest

- создать класс, наследующий TestCase

- написать методы тестов

- запустить тесты через unittest.main()

Преимущества:

- автоматическая проверка работы кода

- упрощение поиска ошибок

- безопасный рефакторинг кода

**50. What are the differences between mutable and immutable data types in Python, and can you provide examples of each?**

---

Mutable data types can be changed after they are created. Their content can be modified without creating a new object. Immutable data types cannot be changed after creation. Any modification creates a new object instead of changing the existing one.

Examples of mutable types: `list, dict, set, bytearray`
Examples of immutable types: `int, float, str, tuple, frozenset, bytes`

Example:
A list can be modified: my_list.append(5) changes the same object. A string cannot be modified; operations like concatenation create a new string.

Mutable типы данных можно изменять после создания. Их содержимое можно менять без создания нового объекта. Immutable типы данных нельзя изменить после создания. Любая «модификация» создаёт новый объект.

Примеры mutable типов: `list, dict, set, bytearray`
Примеры immutable типов: `int, float, str, tuple, frozenset, bytes`

Пример:
Список можно изменить: my_list.append(5) изменяет тот же объект.
Строку изменить нельзя — операции вроде конкатенации создают новую строку.

**51. How can you work with JSON data in Python, and what is the purpose of the json module?**

---

The json module is used to serialize Python objects into JSON format and deserialize JSON data back into Python objects. It is commonly used for data exchange between systems, APIs, and configuration files.

Main functions:

- json.dumps() — convert a Python object to a JSON string

- json.loads() — convert a JSON string to a Python object

- json.dump() — write JSON data to a file

- json.load() — read JSON data from a file

Supported Python types include dict, list, str, int, float, bool, and None.

Typical use cases:

- Working with REST APIs

- Reading/writing configuration files

- Data interchange between services

Модуль json используется для сериализации Python-объектов в формат JSON и десериализации JSON обратно в объекты Python. Он часто применяется для обмена данными между системами, API и конфигурационными файлами.

Основные функции:

- json.dumps() — преобразует Python-объект в JSON-строку

- json.loads() — преобразует JSON-строку в Python-объект

- json.dump() — записывает JSON в файл

- json.load() — читает JSON из файла

Поддерживаемые типы Python: dict, list, str, int, float, bool, None.

Типичные применения:

- Работа с REST API

- Чтение и запись конфигурационных файлов

- Обмен данными между сервисами

**52. What is the purpose of the async and await keywords in Python, and how are they used in asynchronous programming?**

---

async and await are used to write asynchronous code that can run multiple tasks concurrently without blocking the program. async is used to define a coroutine function (async def). Such functions can be paused and resumed by the event loop. await is used inside an async function to pause execution until another coroutine or asynchronous operation finishes, while allowing other tasks to run.

Purpose:

- efficient handling of many I/O operations

- non-blocking execution

- better performance for network services and high-concurrency systems

Typical use cases:

- API requests

- web servers

- database queries

- asynchronous file or network operations

async и await используются для написания асинхронного кода, который позволяет выполнять несколько задач параллельно без блокировки программы. async используется для объявления корутины (async def). Такие функции могут приостанавливаться и продолжаться event loop.
await используется внутри async-функции и приостанавливает её выполнение до завершения другой корутины или асинхронной операции, при этом другие задачи могут выполняться.

Назначение:

- эффективная работа с большим количеством I/O операций

- неблокирующее выполнение

- лучшая производительность для сетевых сервисов и систем с высокой конкуренцией

Типичные применения:

- запросы к API

- веб-серверы

- запросы к базам данных

- асинхронные сетевые или файловые операции

**53. Explain the differences between the requests and urllib libraries for making HTTP requests in Python.**

---

requests is a third-party library designed to make HTTP requests simple and readable. It provides a high-level API and handles many details automatically, such as encoding, sessions, cookies, and JSON parsing.

urllib is a built-in Python module for working with URLs and HTTP requests. It is more low-level and requires more code to perform the same tasks.

Key differences:

- requests — simpler and more user-friendly API

- urllib — part of the Python standard library

- requests automatically handles JSON, headers, sessions, and authentication more easily

- urllib requires more manual configuration

When to use:

- requests — preferred for most HTTP tasks and API communication

- urllib — used when avoiding external dependencies or working strictly with the standard library

requests — это сторонняя библиотека, созданная для простого и удобного выполнения HTTP-запросов. Она имеет высокоуровневый API и автоматически обрабатывает многие детали: кодировку, сессии, cookies и JSON.

urllib — встроенный модуль Python для работы с URL и HTTP-запросами. Он более низкоуровневый и требует больше кода для тех же задач.

Основные различия:

- requests — более простой и удобный API

- urllib — входит в стандартную библиотеку Python

- requests автоматически упрощает работу с JSON, заголовками, сессиями и авторизацией

- urllib требует больше ручной настройки

Когда использовать:

- requests — для большинства HTTP-запросов и работы с API

- urllib — когда нельзя использовать сторонние библиотеки или нужен только стандартный Python

**54. What is the purpose of the subprocess module in Python, and how can you use it to execute external processes?**

---

The subprocess module is used to run external programs or system commands from a Python script and interact with them. It allows you to start processes, capture their output, pass input, and check exit codes. The most common function is subprocess.run(), which executes a command and waits for it to finish.

Example uses:

- running shell commands

- executing other programs or scripts

- capturing command output

- automating system tasks

Example: `subprocess.run(["ls", "-l"], capture_output=True, text=True)`

This runs the command, waits for completion, and allows access to the output.

Модуль subprocess используется для запуска внешних программ или системных команд из Python и взаимодействия с ними. Он позволяет запускать процессы, получать их вывод, передавать входные данные и проверять код завершения. Самая часто используемая функция — subprocess.run(), которая выполняет команду и ждёт её завершения.

Примеры применения:

- запуск команд shell

- выполнение других программ или скриптов

- получение вывода команды

- автоматизация системных задач

Пример: `subprocess.run(["ls", "-l"], capture_output=True, text=True)`

Эта команда запускается, Python ждёт её завершения и позволяет получить вывод.

**55. Explain the concept of method resolution order (MRO) in Python, and how does it affect class inheritance in multiple inheritance scenarios?**

---

Method Resolution Order (MRO) defines the order in which Python searches for methods and attributes in a class hierarchy. It determines which method is executed when a method is called on an object. In single inheritance, Python looks first in the class, then in its parent classes.

In multiple inheritance, Python uses the C3 linearization algorithm to create a consistent order of classes to search. This ensures:

- child classes are checked before parent classes

- parent classes keep the order defined in the inheritance list

- the hierarchy remains predictable and conflict-free

You can see the MRO of a class using: `ClassName.__mro__ or ClassName.mro()`
MRO is important in multiple inheritance because it determines which parent method is used when multiple parents define the same method.

Method Resolution Order (MRO) — это порядок, в котором Python ищет методы и атрибуты в иерархии классов. Он определяет, какой метод будет вызван при обращении к объекту. При одиночном наследовании Python сначала ищет метод в самом классе, затем в родительских классах.

При множественном наследовании Python использует алгоритм C3 linearization, который формирует последовательный порядок поиска классов. Он гарантирует:

- сначала проверяются дочерние классы

- сохраняется порядок родителей, указанный в объявлении класса

- иерархия остаётся предсказуемой и без конфликтов

Посмотреть MRO можно так: `ClassName.__mro__ или ClassName.mro()`

MRO важен при множественном наследовании, потому что определяет, метод какого родительского класса будет использован, если несколько родителей имеют метод с одинаковым именем.

**56. Explain the use of Python's built-in map, filter, and reduce functions, and provide examples of their usage.**

---

ap, filter, and reduce are functional programming tools used to process iterables like lists.

map applies a function to each element of an iterable and returns a new iterator with the results.

Example: `map(lambda x: x * 2, [1,2,3]) → [2,4,6]`

filter selects elements from an iterable that satisfy a condition.

Example: `filter(lambda x: x % 2 == 0, [1,2,3,4]) → [2,4]`

reduce applies a function cumulatively to elements to produce a single result. It is in the functools module.

Example: `reduce(lambda a,b: a + b, [1,2,3,4]) → 10`

Typical purposes:

- map — transform elements

- filter — select elements by condition

- reduce — aggregate elements into one value

map, filter и reduce — это функции функционального программирования для обработки итерируемых объектов (например, списков).

map применяет функцию к каждому элементу и возвращает новый итератор с результатами.

Пример: `map(lambda x: x * 2, [1,2,3]) → [2,4,6]`

filter выбирает элементы, которые удовлетворяют условию.

Пример: `filter(lambda x: x % 2 == 0, [1,2,3,4]) → [2,4]`

reduce применяет функцию последовательно ко всем элементам и возвращает одно итоговое значение. Находится в модуле functools.

Пример: `reduce(lambda a,b: a + b, [1,2,3,4]) → 10`

Назначение:

- map — преобразование элементов

- filter — отбор элементов по условию

- reduce — сведение элементов к одному значению

**57. How do you implement memoization in Python, and why is it useful in recursive functions?**

---

Memoization is caching function results so repeated calls with the same arguments return the stored result instead of recomputing.

In Python, the common way is functools.lru_cache:

- add @lru_cache(maxsize=None) to a recursive function

Why it’s useful in recursion:

- avoids repeating the same subproblems

- turns exponential recursion (like naive Fibonacci) into near-linear time

- reduces CPU usage significantly

Example idea: Fibonacci/DP-style problems benefit the most.

Мемоизация — это кэширование результатов функции, чтобы при повторном вызове с теми же аргументами возвращать сохранённый результат, а не считать заново.

В Python обычно используют functools.lru_cache:

- добавить декоратор @lru_cache(maxsize=None) к рекурсивной функции

Почему полезно для рекурсии:

- убирает повторные вычисления одних и тех же подзадач

- превращает экспоненциальную рекурсию (например, наивный Fibonacci) почти в линейную

- сильно снижает нагрузку на CPU

Чаще всего помогает в задачах типа Fibonacci и dynamic programming.

**58. What is the purpose of Python's contextlib module, and how can you create context managers using it?**

---

The contextlib module provides utilities for working with context managers and simplifies resource management (files, locks, connections). Its main purpose is to make it easier to create and manage context managers used with the with statement. The most common way is using the @contextmanager decorator. It allows you to write a generator function that defines setup and cleanup logic around yield.

How it works:

- code before yield runs when entering the context

- code after yield runs when exiting the context

Typical uses:

- managing files or network connections

- acquiring and releasing locks

- handling setup/cleanup logic

Модуль contextlib предоставляет инструменты для работы с контекстными менеджерами и упрощает управление ресурсами (файлы, блокировки, соединения).

Его основная цель — упростить создание и использование контекстных менеджеров с оператором with.

Самый распространённый способ — использовать декоратор @contextmanager. Он позволяет написать генераторную функцию, которая описывает логику входа и выхода из контекста через yield.

Как это работает:

- код до yield выполняется при входе в контекст

- код после yield выполняется при выходе из контекста

Типичные применения:

- управление файлами или сетевыми соединениями

- захват и освобождение блокировок

- выполнение setup/cleanup логики

**59. Explain the benefits of using type hints (PEP 484) in Python code, and how can you use them to improve code readability and maintainability?**

---

Type hints (PEP 484) allow you to specify expected data types for function parameters, return values, and variables. They do not change runtime behavior but provide type information for developers and tools.

Benefits:

- Improves code readability by clearly showing expected types

- Helps catch errors using static analysis tools (like mypy)

- Makes large codebases easier to understand and maintain

- Improves IDE support (autocomplete, refactoring, warnings)

Example idea: `def add(a: int, b: int) -> int`

Use cases:

- documenting function interfaces

- reducing bugs in complex systems

- improving collaboration in teams

Type hints (PEP 484) позволяют указывать ожидаемые типы данных для параметров функций, возвращаемых значений и переменных. Они не влияют на выполнение программы, а служат для документации и инструментов анализа.

Преимущества:

- Улучшают читаемость кода, показывая ожидаемые типы

- Помогают находить ошибки через статический анализ (например, mypy)

- Упрощают поддержку больших проектов

- Улучшают работу IDE (автодополнение, предупреждения, рефакторинг)

Пример: `def add(a: int, b: int) -> int`

Применение:

- документирование интерфейсов функций

- уменьшение количества ошибок

- облегчение совместной разработки

**60. How can you work with threads in Python, and what are some common challenges and best practices when dealing with multi-threading?**

---

Threads in Python are typically managed with the threading module: create a Thread with a target function, start it with .start(), and wait with .join(). For higher-level usage, concurrent.futures.ThreadPoolExecutor is often preferred.

Common challenges:

- Race conditions when multiple threads modify shared data

- Deadlocks from incorrect lock usage

- Hard-to-reproduce bugs due to non-deterministic scheduling

- GIL limits parallelism for CPU-bound code

Best practices:

- Use threads mainly for I/O-bound work

- Prefer thread pools (ThreadPoolExecutor) over manually managing many threads

- Protect shared state with Lock, RLock, Semaphore, or use thread-safe queues (queue.Queue)

- Keep critical sections small; avoid holding locks during I/O

- Design around message passing (queues) instead of shared mutable state

- Set timeouts for blocking operations when possible

С потоками в Python обычно работают через модуль threading: создают Thread с целевой функцией, запускают через .start() и ждут завершения через .join(). Более высокий уровень — concurrent.futures.ThreadPoolExecutor.

Типичные проблемы:

- Race conditions, когда несколько потоков меняют общие данные

- Deadlocks из-за неправильного использования блокировок

- Трудновоспроизводимые баги из-за непредсказуемого планирования

- GIL ограничивает параллельность для CPU-bound кода

Лучшие практики:

- Использовать потоки в основном для I/O-bound задач

- Предпочитать пул потоков (ThreadPoolExecutor) вместо ручного управления множеством потоков

- Защищать общий стейт через Lock, RLock, Semaphore или использовать потокобезопасные очереди (queue.Queue)

- Держать критические секции короткими; не держать lock во время I/O

- Строить взаимодействие через очереди, а не через общий изменяемый стейт

- По возможности ставить таймауты на блокирующие операции

**61. What is the asyncio module in Python?**

---

asyncio is a Python standard library module used for writing asynchronous, non-blocking code using async and await. It is built around an event loop that manages and schedules multiple tasks (coroutines) so they can run concurrently without creating multiple threads.

Purpose:

- handle many I/O operations efficiently

- support high-concurrency applications

- avoid blocking the program while waiting for operations like network or disk I/O

Key concepts:

- coroutines (async def) — asynchronous functions

- event loop — scheduler that runs tasks

- tasks/futures — objects representing running async operations

Typical use cases:

- web servers

- API calls

- asynchronous database access

- real-time network applications

asyncio — это модуль стандартной библиотеки Python для написания асинхронного неблокирующего кода с использованием async и await.

Он работает на основе event loop, который управляет и планирует выполнение нескольких задач (корутин), позволяя им выполняться конкурентно без создания множества потоков.

Назначение:

- эффективно обрабатывать большое количество I/O операций

- поддерживать приложения с высокой конкурентностью

- не блокировать программу во время ожидания сетевых или файловых операций

Основные понятия:

- coroutines (async def) — асинхронные функции

- event loop — планировщик задач

- tasks/futures — объекты, представляющие выполняющиеся асинхронные операции

Типичные применения:

- веб-серверы

- запросы к API

- асинхронные базы данных

- сетевые приложения в реальном времени

**62. What is the asyncio module in Python?**

---

The asyncio module is a Python standard library for writing asynchronous, non-blocking code using async and await. It provides an event loop that schedules and runs coroutines concurrently within a single thread. It is mainly used to efficiently handle many I/O-bound operations such as network requests, API calls, and database access without blocking the program.

asyncio — это модуль стандартной библиотеки Python для написания асинхронного неблокирующего кода с использованием async и await. Он предоставляет event loop, который планирует и выполняет корутины конкурентно в одном потоке. Он используется для эффективной обработки большого количества I/O операций, например сетевых запросов, API или работы с базами данных, без блокировки программы.

**63. What is a coroutine in Python?**

---

A coroutine in Python is a special type of function that can pause and resume its execution. It is defined using async def. Coroutines are used in asynchronous programming to allow multiple tasks to run concurrently without blocking the program. They work with the event loop and use await to pause execution until another asynchronous operation completes.

Purpose:

- efficient handling of I/O-bound operations

- cooperative multitasking within a single thread

Корутиина в Python — это специальный тип функции, которая может приостанавливать и продолжать своё выполнение. Она объявляется с помощью async def. Корутиины используются в асинхронном программировании, чтобы несколько задач могли выполняться конкурентно без блокировки программы. Они работают через event loop и используют await, чтобы приостановить выполнение до завершения другой асинхронной операции.

Назначение:

- эффективная работа с I/O задачами

- кооперативная многозадачность в одном потоке

**64. What is a future in the concurrent.futures module?**

---

A Future in concurrent.futures is an object that represents the result of a computation that may not have finished yet. When you submit a task to an executor (ThreadPoolExecutor or ProcessPoolExecutor), it immediately returns a Future. The task runs in the background, and the Future allows you to check its status or retrieve the result later.

Main uses:

- get the result with .result()

- check if the task is finished with .done()

- check for exceptions with .exception()

- cancel the task with .cancel()

Purpose: It provides a way to track and manage asynchronous tasks.

Future в модуле concurrent.futures — это объект, который представляет результат вычисления, которое может ещё не завершиться. Когда задача отправляется в executor (ThreadPoolExecutor или ProcessPoolExecutor), сразу возвращается объект Future. Задача выполняется в фоне, а Future позволяет проверить её состояние или получить результат позже.

Основные возможности:

- получить результат через .result()

- проверить завершена ли задача через .done()

- проверить исключение через .exception()

- отменить задачу через .cancel()

Назначение: Позволяет отслеживать и управлять асинхронными задачами.

**65. How can you represent a graph in Python?**

---

A graph in Python is usually represented using adjacency lists or adjacency matrices. The most common representation is an adjacency list, where each node stores a list of its neighbors. It is typically implemented using a dictionary.

Example idea: `graph = { 'A': ['B', 'C'], 'B': ['A', 'D'], 'C': ['A'], 'D': ['B'] }`

Advantages:

- memory efficient for sparse graphs

- easy to iterate through neighbors

An adjacency matrix represents the graph as a 2D list where rows and columns represent nodes and values indicate connections.

Advantages:

- fast edge lookup

- useful for dense graphs

Libraries like networkx can also be used for more complex graph operations.

Граф в Python обычно представляют с помощью списков смежности или матрицы смежности. Самый распространённый способ — список смежности, где каждая вершина хранит список соседей. Обычно используется словарь.

Пример: `graph = { 'A': ['B', 'C'], 'B': ['A', 'D'], 'C': ['A'], 'D': ['B'] }`

Преимущества:

- экономит память для разреженных графов

- удобно обходить соседние вершины

Матрица смежности — это двумерный список, где строки и столбцы представляют вершины, а значения показывают наличие ребра.

Преимущества:

- быстрый доступ к проверке наличия ребра

- подходит для плотных графов

Для более сложной работы с графами часто используют библиотеку networkx.

**66. How *args and *kwargs are used in python**

---

*args and \*\*kwargs allow a function to accept a variable number of arguments.
*args collects positional arguments into a tuple. It is used when you don’t know how many positional parameters will be passed.

Example idea: `def func(*args):` You can iterate through args inside the function.

\*\*kwargs collects keyword arguments into a dictionary. It is used when you want to accept named parameters dynamically.

Example idea: `def func(**kwargs):` Inside the function you access them like a dictionary.

Typical use:

- flexible function interfaces

- wrapper functions

- decorators

- passing parameters to other functions

*args и \*\*kwargs позволяют функции принимать переменное количество аргументов.
*args собирает позиционные аргументы в кортеж. Используется, когда неизвестно сколько позиционных параметров будет передано.

Пример: `def func(*args):` Внутри функции можно перебирать args.

\*\*kwargs собирает именованные аргументы в словарь. Используется, когда нужно принимать параметры по имени.

Пример: `def func(**kwargs):`
Внутри функции они доступны как словарь.

Типичное применение:

- гибкие интерфейсы функций

- функции-обёртки

- декораторы

- передача параметров в другие функции

**67. How will you find bugs and errors in python code?**

---

Bugs and errors in Python code can be found using several approaches:

- Read error messages and stack traces — Python exceptions show where the error occurred and help identify the problem.

- Use debugging tools — the built-in pdb debugger allows stepping through code, inspecting variables, and understanding program flow.

- Add logging or print statements — helps trace program execution and check variable values.

- Write unit tests — frameworks like unittest or pytest help detect bugs automatically.

- Static analysis tools — tools like flake8, pylint, or mypy can find potential issues before runtime.

These methods help isolate the problem, understand its cause, and fix it efficiently.

Ошибки и баги в Python-коде находят несколькими способами:

- Чтение сообщений об ошибках и stack trace — исключения Python показывают место ошибки и помогают понять причину.

- Использование отладчиков — встроенный отладчик pdb позволяет пошагово выполнять код и проверять значения переменных.

- Добавление logging или print — помогает отслеживать выполнение программы и значения переменных.

- Юнит-тесты — фреймворки unittest или pytest помогают автоматически обнаруживать ошибки.

- Статический анализ кода — инструменты flake8, pylint, mypy могут находить проблемы ещё до запуска программы.

Эти методы помогают локализовать проблему, понять её причину и исправить её.

**68. Can you state the name of the tool which are used to find the bugs in python?**

---

Some common tools used to find bugs in Python are:

- pdb — built-in Python debugger for stepping through code

- pytest — testing framework that helps detect failures in code

- unittest — built-in testing framework for writing unit tests

- pylint — static analysis tool that finds code issues and bad practices

- flake8 — checks style errors and potential problems

- mypy — static type checker that detects type-related bugs

Некоторые инструменты для поиска багов в Python:

- pdb — встроенный отладчик Python для пошагового выполнения кода

- pytest — фреймворк тестирования, помогает находить ошибки

- unittest — встроенный фреймворк для написания тестов

- pylint — инструмент статического анализа кода

- flake8 — проверяет стиль и потенциальные ошибки

- mypy — статический анализатор типов, помогает находить ошибки типов

**69. What is the purpose of the try and except keywords in Python?**

---

try and except are used for exception handling in Python. They allow a program to handle runtime errors without crashing. Code that might raise an error is placed inside the try block. If an exception occurs, the except block catches the error and handles it.

Purpose:

- prevent program crashes

- handle errors gracefully

- allow alternative logic when an error occurs

Example idea: handling errors like division by zero or file not found.

try и except используются для обработки исключений в Python. Они позволяют программе обрабатывать ошибки во время выполнения без остановки программы. Код, который может вызвать ошибку, помещается в блок try. Если возникает исключение, блок except перехватывает ошибку и обрабатывает её.

Назначение:

- предотвращение падения программы

- корректная обработка ошибок

- выполнение альтернативной логики при возникновении ошибки

Пример: обработка ошибок вроде деления на ноль или отсутствующего файла.

**70. What is the difference between the except and finally blocks in Python?**

---

except is used to catch and handle an exception that occurs in the try block. finally is used to execute code that must run no matter what, whether an exception occurs or not.

Key difference:

- except runs only if an exception happens

- finally runs always, after try and except

Typical use of finally:

- closing files

- releasing resources

- cleaning up operations

except используется для перехвата и обработки исключения, которое возникло в блоке try. finally используется для выполнения кода в любом случае, независимо от того произошла ошибка или нет.

Основная разница:

- except выполняется только если возникла ошибка

- finally выполняется всегда, после try и except

Типичное применение finally:

- закрытие файлов

- освобождение ресурсов

- очистка после выполнения операций

**71. What is the purpose of the raise keyword in Python?**

---

raise is used to manually trigger an exception in Python. It allows a program to signal that an error has occurred and stop normal execution unless the exception is handled.

Purposes:

- signal invalid conditions in code

- enforce validation rules

- re-raise an exception after catching it

Example idea: raising an error if an input value is invalid.

raise используется для ручного вызова исключения в Python. Он позволяет программе сообщить о возникновении ошибки и остановить обычное выполнение, если исключение не будет обработано.

Назначение:

- сигнализировать о некорректных условиях в коде

- проверка и валидация данных

- повторный выброс исключения после его перехвата

**72. What is the difference between the assert statement and the raise keyword in Python?**

---

raise is used to explicitly trigger an exception in code. It is meant for normal error handling and is always executed. assert is used for debugging to check that a condition is true. If the condition is false, it raises an AssertionError.

Key differences:

- raise is used for handling real errors in production code

- assert is mainly used for debugging and internal checks

- assert statements can be disabled when Python runs with optimization (-O)

Example idea: `assert x > 0` checks a condition. `raise ValueError("Invalid value")` explicitly throws an error.

raise используется для явного вызова исключения в коде. Он применяется для нормальной обработки ошибок и всегда выполняется. assert используется для отладки и проверки, что условие истинно. Если условие ложное, возникает AssertionError.

Основные различия:

- raise применяется для реальных ошибок в рабочем коде

- assert используется в основном для отладки и внутренних проверок

- assert может быть отключён при запуске Python с оптимизацией (-O)

Пример: `assert x > 0` проверяет условие. `raise ValueError("Invalid value")` явно вызывает исключение.

**73. What is the purpose of the else block in a try statement in Python?**

---

The else block in a try statement runs only if no exception occurs in the try block. It is used to separate the code that should run when the try block succeeds from the code that handles exceptions.

Purpose:

- keep error-handling code (except) separate from normal execution

- make the structure of the program clearer

Execution order: try → except (if error) → else (if no error) → finally (always)

Блок else в конструкции try выполняется только если в блоке try не произошло исключения. Он используется для отделения обычного кода, который должен выполниться при успешном выполнении try, от кода обработки ошибок.

Назначение:

- отделить обработку ошибок (except) от нормального выполнения

- сделать структуру кода более понятной

Порядок выполнения: try → except (если ошибка) → else (если ошибки нет) → finally (всегда)

**74. What is the purpose of the finally block in a try statement in Python?**

---

The finally block in a try statement is used to execute code regardless of whether an exception occurs or not.

It always runs after the try and except blocks.

Purpose:

- ensure cleanup operations are performed

- release resources such as files, network connections, or locks

Typical use cases:

- closing files

- releasing database connections

- freeing system resources

Блок finally в конструкции try используется для выполнения кода независимо от того, произошла ошибка или нет.

Он выполняется всегда после блоков try и except.

Назначение:

- гарантировать выполнение операций очистки

- освобождение ресурсов, таких как файлы, сетевые соединения или блокировки

Типичные применения:

- закрытие файлов

- освобождение соединений с базой данных

- освобождение системных ресурсов

**75. What is the difference between the try and else blocks in a try statement in Python?**

---

The try block contains code that may raise an exception. The else block contains code that runs only if the try block executes successfully without any exception.

Key difference:

- try — where the risky code is placed

- else — runs after try if no exception occurred

Purpose of else:

- separate normal execution logic from exception handling

- keep the try block minimal and focused only on code that may fail

Блок try содержит код, который может вызвать исключение. Блок else содержит код, который выполняется только если в try не произошло ошибки.

Основная разница:

- try — код, который может вызвать ошибку

- else — выполняется после try, если ошибки не было

Назначение else:

- отделить обычную логику выполнения от обработки ошибок

- держать блок try минимальным и только для потенциально опасного кода.

**76. What is the difference between a built-in exception and a custom exception in Python?**

---

A built-in exception is an error class provided by Python itself. These are predefined and used for common error situations.

Examples: `ValueError, TypeError, IndexError, KeyError, ZeroDivisionError.`

A custom exception is a user-defined exception created by inheriting from the Exception class. It is used to represent specific errors in an application.

Key difference:

- built-in exceptions — provided by Python for general errors

- custom exceptions — created by developers for application-specific errors

Purpose of custom exceptions:

- make error handling clearer

- represent domain-specific problems in code

Built-in exception — это класс ошибки, уже определённый в Python. Они используются для стандартных ситуаций ошибок.

Примеры: `ValueError, TypeError, IndexError, KeyError, ZeroDivisionError.`

Custom exception — это пользовательское исключение, которое создаётся разработчиком путём наследования от класса Exception. Оно используется для описания специфических ошибок приложения.

Основная разница:

- built-in exceptions — стандартные ошибки Python

- custom exceptions — создаются разработчиком для конкретной логики приложения

Назначение пользовательских исключений:

- сделать обработку ошибок более понятной

- описывать специфические ошибки в программе.

**77. How do you handle multiple exceptions in Python?**

---

Multiple exceptions in Python can be handled in two main ways. Using multiple except blocks — handle different exceptions separately.

Example idea:
try: ...
except ValueError: ...
except TypeError: ...

Handling multiple exceptions in one block — group them in a tuple.

Example idea: except (ValueError, TypeError): ...

Purpose:

- handle different error types appropriately

- simplify error handling when multiple exceptions require the same logic

В Python несколько исключений можно обрабатывать двумя основными способами.
Несколько блоков except — для обработки разных типов ошибок отдельно.

Пример:
try: ...
except ValueError: ...
except TypeError: ...

Несколько исключений в одном блоке — объединяются в кортеж.

Пример: except (ValueError, TypeError): ...

Назначение:

- обрабатывать разные типы ошибок по-разному

- упростить код, если для нескольких ошибок используется одна и та же логика.

**78. What is PEP 8, and why is it important?**

---

EP 8 is the official Python style guide that defines conventions for writing readable and consistent Python code.

It covers rules for:

- indentation and formatting

- naming conventions for variables, functions, and classes

- line length and spacing

- code layout and structure

Why it is important:

- improves code readability

- keeps code consistent across projects and teams

- makes maintenance and collaboration easier

Many tools like flake8 and pylint help check if code follows PEP 8.

PEP 8 — это официальный гайд по стилю Python, который определяет правила написания читаемого и единообразного кода.

Он описывает правила для:

- отступов и форматирования

- именования переменных, функций и классов

- длины строк и пробелов

- структуры и оформления кода

Почему это важно:

- улучшает читаемость кода

- делает код единообразным в командах и проектах

- упрощает поддержку и совместную разработку

Инструменты flake8 и pylint помогают проверять соответствие кода PEP 8.

**78. What is the purpose of the \_\_init\_\_.py file in a Python package?**

---

The \_\_init\_\_.py file marks a directory as a Python package and allows the directory to be imported as a module.

It can also be used to:

- initialize package-level variables

- control what is exported with \_\_all\_\_

- simplify imports by exposing selected modules or objects

In modern Python (3.3+), packages can work without \_\_init\_\_.py, but it is still commonly used for package initialization and structure.

Файл \_\_init\_\_.py обозначает директорию как Python-пакет и позволяет импортировать её как модуль.

Также он может использоваться для:

- инициализации переменных уровня пакета

- управления экспортом через \_\_all\_\_

- упрощения импортов, открывая доступ к нужным модулям или объектам

В современных версиях Python (3.3+) пакет может работать и без \_\_init\_\_.py, но файл по-прежнему часто используют для инициализации пакета и управления структурой.

**79. What is the purpose of the if \_\_name\_\_ == "\_\_main\_\_": block in a Python script?**

The if \_\_name\_\_ == "\_\_main\_\_: block ensures that certain code runs only when the script is executed directly, not when it is imported as a module.
When a Python file runs directly, the special variable \_\_name\_\_ is set to "\_\_main\_\_". When the file is imported, \_\_name\_\_ is set to the module’s name.

Purpose:

- prevent code from running during import

- define the main entry point of a script

- allow a file to be both reusable as a module and executable as a script

Блок if \_\_name\_\_ == "\_\_main\_\_: используется, чтобы код выполнялся только при прямом запуске файла, а не при его импорте как модуля.
Когда Python запускает файл напрямую, переменная \_\_name\_\_ равна "\_\_main\_\_".
Когда файл импортируется, \_\_name\_\_ становится именем модуля.

Назначение:

- предотвратить выполнение кода при импорте

- определить основную точку входа программы

- позволить файлу быть и модулем, и исполняемым скриптом.

**80. Explain the Global Interpreter Lock (GIL) in Python.**

---

The Global Interpreter Lock (GIL) is a mechanism in CPython that ensures only one thread executes Python bytecode at a time within a single process. It exists to simplify memory management and make the interpreter thread-safe.

Impact:

- CPU-bound tasks do not gain real parallelism with threads because the GIL allows only one thread to run Python code at a time.

- I/O-bound tasks can still benefit from multithreading because the GIL is released during I/O operations (e.g., file or network access).

Workarounds:

- use multiprocessing for CPU-bound tasks

- use asyncio or threading for I/O-bound tasks

Global Interpreter Lock (GIL) — это механизм в CPython, который гарантирует, что только один поток одновременно выполняет Python bytecode в рамках одного процесса. Он существует для упрощения управления памятью и обеспечения потокобезопасности интерпретатора.

Влияние:

- CPU-bound задачи не получают настоящего параллелизма с потоками, потому что GIL позволяет выполнять Python-код только одному потоку.

- I/O-bound задачи могут выигрывать от многопоточности, потому что GIL освобождается во время операций ввода-вывода.

Обходные решения:

- использовать multiprocessing для CPU-bound задач

- использовать asyncio или threading для I/O-bound задач.

**81. How can you remove duplicates from a list in Python?**

---

Duplicates can be removed from a list in several ways. **Using a set** (simplest way): `list(set(my_list))` This removes duplicates but does not preserve order.
Preserving order using dict: `list(dict.fromkeys(my_list))`
**Using a loop:** Create a new list and add elements only if they are not already present.
Most commonly **used approach**: `list(dict.fromkeys(my_list))` because it removes duplicates while keeping the original order.

Удалить дубликаты из списка можно несколькими способами. Через set (самый простой способ): `list(set(my_list))` Удаляет дубликаты, но не сохраняет порядок элементов. С сохранением порядка через dict: `list(dict.fromkeys(my_list))`

Через цикл: Создать новый список и добавлять элементы только если их там ещё нет.
Чаще всего используют `list(dict.fromkeys(my_list))`, потому что он удаляет дубликаты и сохраняет порядок элементов.

**82. What is a lambda function in Python, and how is it different from a regular function?**

---

A lambda function is a small anonymous function defined using the lambda keyword. It can take any number of arguments but can contain only one expression. The result of the expression is automatically returned.

Example idea: `lambda x: x * 2`

Key differences from a regular function:

- lambda has no name

- written in a single expression

- used for short, simple operations

- regular functions (def) can contain multiple statements and more complex logic

Typical use cases:

- with functions like map(), filter(), sorted()

- for short one-time operations

Lambda-функция — это небольшая анонимная функция, которая создаётся с помощью ключевого слова lambda. Она может принимать любое количество аргументов, но содержит только одно выражение. Результат выражения автоматически возвращается.

Пример: `lambda x: x * 2`

Основные отличия от обычной функции:

- lambda не имеет имени

- состоит из одного выражения

- используется для коротких и простых операций

- обычные функции (def) могут содержать несколько выражений и сложную логику

Типичные применения:

- вместе с map(), filter(), sorted()

- для коротких одноразовых операций.

**83. What are list comprehensions, and how do they work in Python?**

--

List comprehensions provide a compact way to create lists by applying an expression to each element of an iterable.
Syntax idea: [expression for item in iterable if condition]

How they work:

- iterate through an iterable

- apply an expression to each element

- optionally filter elements with a condition

- return a new list

Example idea: `[x * 2 for x in range(5)] → [0, 2, 4, 6, 8]`

Benefits:

- shorter and more readable than loops

- often faster than building lists with for loops

List comprehension — это короткий способ создания списков, применяя выражение к каждому элементу итерируемого объекта.

Синтаксис: [expression for item in iterable if condition]

Как работает:

- проходит по элементам iterable

- применяет выражение к каждому элементу

- может фильтровать элементы через условие

- возвращает новый список

Пример: [x * 2 for x in range(5)] → [0, 2, 4, 6, 8]

Преимущества:

- короче и читаемее обычного цикла

- часто работает быстрее, чем создание списка через for.

**84. What is the purpose of the super() function in Python?**

super() is used to call methods from a parent class in a subclass. It allows a child class to reuse and extend the functionality of the parent class. It is commonly used in inheritance, especially to call the parent class constructor.

Purpose:

- access parent class methods

- avoid directly naming the parent class

- support multiple inheritance through proper method resolution (MRO)

Typical use case: calling the parent class \_\_init\_\_ method inside a subclass.

super() используется для вызова методов родительского класса из дочернего класса. Это позволяет повторно использовать и расширять функциональность родительского класса. Чаще всего применяется при наследовании, например для вызова конструктора родительского класса.

Назначение:

- доступ к методам родительского класса

- не нужно явно указывать имя родительского класса

- поддержка множественного наследования через механизм MRO

Типичное применение: вызов метода \_\_init\_\_ родительского класса внутри дочернего класса.

**85. How can you iterate over the items of a dictionary in Python?**

---

You can iterate over a dictionary in several ways depending on what you need.

- Iterate over keys: `for key in my_dict:` or `for key in my_dict.keys():`

- Iterate over values: `for value in my_dict.values():`

- Iterate over key–value pairs (most common): `for key, value in my_dict.items():`

Purpose:

- keys() → access dictionary keys

- values() → access dictionary values

- items() → access both key and value together

Итерироваться по словарю в Python можно несколькими способами.

- По ключам: `for key in my_dict:` или `for key in my_dict.keys():`

- По значениям: `for value in my_dict.values():`

- По ключам и значениям (самый частый способ): `for key, value in my_dict.items():`

Назначение:

- keys() → получить ключи словаря

- values() → получить значения

- items() → получить ключ и значение одновременно.

**86. Explain the purpose of the global keyword in Python.**

---

The global keyword is used inside a function to indicate that a variable refers to a global variable defined outside the function. Normally, assigning a value inside a function creates a local variable. Using global allows the function to modify the global variable instead.

Purpose:

- access and modify variables defined at the module (global) level

- avoid creating a new local variable when assigning a value

Typical use case: when a function needs to update a global state.

Ключевое слово global используется внутри функции, чтобы указать, что переменная относится к глобальной переменной, определённой вне функции. Обычно присваивание внутри функции создаёт локальную переменную. Использование global позволяет изменять глобальную переменную.

Назначение:

- доступ и изменение переменных, определённых на уровне модуля

- избежать создания новой локальной переменной при присваивании

Типичное применение: когда функция должна изменить глобальное состояние программы.

**87. What is the difference between a deep copy and a shallow copy of an object in Python?**

---

A shallow copy creates a new object but copies only the references to the nested objects. If the nested objects are modified, the change will affect both copies. A deep copy creates a completely independent copy of the object and all objects inside it.

Key difference:

- shallow copy — copies the outer object, inner objects are shared

- deep copy — copies the entire structure recursively

Typical tools:

- copy.copy() → shallow copy

- copy.deepcopy() → deep copy

Example idea: If a list contains other lists, a shallow copy will share those inner lists, while a deep copy will duplicate them.

Shallow copy создаёт новый объект, но копирует только ссылки на вложенные объекты. Если изменить вложенный объект, изменения будут видны в обеих копиях. Deep copy создаёт полностью независимую копию объекта и всех вложенных объектов.

Основная разница:

- shallow copy — копируется только внешний объект, вложенные остаются общими

- deep copy — копируется вся структура рекурсивно

Обычно используют:

- copy.copy() → поверхностная копия

- copy.deepcopy() → глубокая копия

Пример: Если список содержит другие списки, shallow copy будет делить внутренние списки, а deep copy создаст их отдельные копии.

**88. What is a decorator in Python, and how is it used?**

---

A decorator in Python is a function that modifies or extends the behavior of another function or method without changing its code.
Decorators wrap a function and are applied using the @decorator_name syntax.

Purpose:

- add extra functionality (logging, authentication, caching)

- keep code reusable and clean

- separate cross-cutting concerns from business logic

Common examples: `@staticmethod`, `@classmethod`, `@property`

Декоратор в Python — это функция, которая изменяет или расширяет поведение другой функции или метода без изменения её кода.
Декораторы оборачивают функцию и применяются с помощью синтаксиса @decorator_name.

Назначение:

- добавление дополнительной логики (логирование, авторизация, кэширование)

- улучшение переиспользуемости и чистоты кода

- отделение вспомогательной логики от основной

Распространённые примеры: `@staticmethod`, `@classmethod`, `@property`

**89. What is the purpose of the is operator in Python?**

---

The is operator is used to check object identity — whether two variables refer to the same object in memory. It does not compare values, but compares whether both variables point to the exact same object.

Difference:

- is → checks identity (same object)

- == → checks value equality

Typical use case: checking against None.

Оператор is используется для проверки идентичности объектов — указывают ли две переменные на один и тот же объект в памяти. Он не сравнивает значения, а проверяет, являются ли объекты одним и тем же объектом.

Разница:

- is → проверяет идентичность объекта

- == → проверяет равенство значений

Типичное применение: проверка на None.

**90. What is the pass statement in Python, and when is it used?**

---

The pass statement is a null operation in Python — it does nothing when executed. It is used as a placeholder where a statement is syntactically required but no action is needed yet.

Typical use cases:

- empty functions

- empty classes

- empty loops or conditional blocks

- during development when code will be added later

Оператор pass в Python — это пустая операция, которая ничего не делает при выполнении. Он используется как заглушка, когда синтаксис требует наличие инструкции, но логика ещё не реализована.

Типичные случаи использования:

- пустые функции

- пустые классы

- пустые циклы или условия

- во время разработки, когда код будет добавлен позже.

**91. Explain the purpose of the break and continue statements in Python loops.**

---

**break** and **continue** control the flow of loops. **break** immediately stops the loop and exits it, even if the loop condition is still true. **continue** skips the rest of the current iteration and moves to the next iteration of the loop.

Key difference:

- break → exits the loop completely

- continue → skips only the current iteration

**break** и **continue** управляют выполнением циклов.

**break** немедленно завершает цикл и выходит из него, даже если условие цикла ещё истинно.

**continue** пропускает оставшуюся часть текущей итерации и переходит к следующей итерации цикла.

Основная разница:

- break → полностью завершает цикл

- continue → пропускает только текущую итерацию.

**92. What is a generator in Python, and how is it different from a regular function?**

A generator is a special type of function that returns an iterator and produces values one at a time using yield, instead of returning them all at once. Each time the generator is called, it resumes execution from where it stopped.

Difference from a regular function:

- regular function uses return and returns a final value once

- generator uses yield and produces a sequence of values lazily

Benefits:

- memory efficient

- useful for large datasets or infinite sequences

Generator в Python — это специальная функция, которая возвращает итератор и выдаёт значения по одному с помощью yield, а не сразу все.
Каждый вызов продолжает выполнение с того места, где функция остановилась.

Разница с обычной функцией:

- обычная функция использует return и возвращает значение один раз

- генератор использует yield и выдаёт последовательность значений по одному

Преимущества:

- экономия памяти

- удобен для работы с большими наборами данных или бесконечными последовательностями.

**93. How do you create a list of unique random numbers in Python?**

---

You can create a list of unique random numbers using `random.sample().` `random.sample()` returns a specified number of unique elements from a range or sequence.

Example idea: `random.sample(range(1, 101), 10)`

This generates 10 unique random numbers between 1 and 100.

Why it works: `sample()` automatically avoids duplicates, no need for additional checks or loops

Список уникальных случайных чисел можно создать с помощью random.sample().

random.sample() возвращает заданное количество уникальных элементов из диапазона или последовательности.

Пример: `random.sample(range(1, 101), 10)`

Это создаст 10 уникальных случайных чисел от 1 до 100.

Почему это работает: sample() автоматически исключает дубликаты, не нужно писать дополнительные проверки или циклы.

**94. What are the built-in data types for numbers in Python, and how are they different?**

---

Python has three main built-in numeric data types:

**int** — represents integers (whole numbers) without a decimal point. Example: -5, 0, 42.

**float** — represents floating-point numbers with a decimal point. Example: 3.14, -0.5, 2.0.

**complex** — represents complex numbers with a real and imaginary part. Example: 3+4j.

Key differences:

- int → whole numbers

- float → numbers with decimal values

- complex → numbers with real and imaginary components

В Python есть три основных встроенных числовых типа данных:

**int** — целые числа без десятичной части. Пример: -5, 0, 42.

**float** — числа с плавающей точкой (с десятичной частью). Пример: 3.14, -0.5, 2.0.

**complex** — комплексные числа с действительной и мнимой частью. Пример: 3+4j.

Основные различия:

- int → целые числа

- float → числа с десятичной частью

- complex → числа с действительной и мнимой частью.

**95. How is memory managed in Python?**

---

Memory in Python is managed automatically by the Python memory manager.

Python uses two main mechanisms:

- **Reference counting** — each object keeps a count of references pointing to it. When the reference count becomes zero, the memory is automatically released.

- **Garbage collection** (GC) — handles cases where objects reference each other in cycles. The garbage collector periodically detects and removes these unused objects.

Purpose:

- automatic memory allocation and deallocation

- prevents most memory leaks

- simplifies development because programmers do not manually manage memory

Память в Python управляется автоматически менеджером памяти Python.

Python использует два основных механизма:

- **Подсчёт ссылок** (reference counting) — каждый объект хранит количество ссылок на него. Когда число ссылок становится нулевым, память автоматически освобождается.

- **Сборщик мусора** (garbage collector) — обрабатывает ситуации, когда объекты ссылаются друг на друга по циклу. Он периодически находит и удаляет такие неиспользуемые объекты.

Назначение:

- автоматическое выделение и освобождение памяти

- предотвращение большинства утечек памяти

- упрощение разработки, так как программист не управляет памятью вручную.

**96. What are Python namespaces? Why are they used?**

---

A namespace in Python is a container that holds names (identifiers) and maps them to objects such as variables, functions, and classes.

Namespaces are used to organize and isolate names, preventing conflicts between identifiers with the same name.

Types of namespaces:

- **Built-in namespace** — contains built-in functions like print, len

- **Global namespace** — names defined at the module level

- **Local namespace** — names defined inside a function

Purpose:

- avoid name collisions

- organize code and scope of variables

- control visibility and lifetime of variables

Namespace в Python — это пространство, которое хранит имена (идентификаторы) и связывает их с объектами, такими как переменные, функции и классы.

Namespaces используются для организации и изоляции имён, чтобы избежать конфликтов между одинаковыми именами.

Типы пространств имён:

- **Built-in namespace** — содержит встроенные функции, например print, len

- **Global namespace** — имена, определённые на уровне модуля

- **Local namespace** — имена внутри функции

Назначение:

- избежать конфликтов имён

- организовать код и области видимости переменных

- управлять доступностью и временем жизни переменных.

**97. What is Scope Resolution in Python?**

---

Scope resolution in Python defines how Python looks up variable names in different scopes.

Python follows the LEGB rule:

- L — Local: variables inside the current function

- E — Enclosing: variables in outer (enclosing) functions

- G — Global: variables defined at the module level

- B — Built-in: names from Python’s built-in namespace

Python searches for a variable in this order: Local → Enclosing → Global → Built-in.

Purpose:

- determine where a variable is found

- control visibility and access to variables in different parts of the program

Scope Resolution в Python определяет как Python ищет переменные в разных областях видимости.

Python использует правило LEGB:

- L — Local: переменные внутри текущей функции

- E — Enclosing: переменные во внешних функциях

- G — Global: переменные уровня модуля

- B — Built-in: встроенные имена Python

Поиск переменной происходит в порядке: Local → Enclosing → Global → Built-in.

Назначение:

- определить, где находится переменная

- управлять видимостью и доступом к переменным в программе.
