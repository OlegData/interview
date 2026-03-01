## Python

---

**1. What is Python, what are the benefits of using it, and what do you understand of PEP 8?**

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

**What is the statement that can be used in Python if the program requires no action but requires it syntactically?**

The statement is pass. It is a no-op statement — it does nothing but is used as a placeholder when a statement is syntactically required  
(e.g., in empty functions, classes, loops, or conditionals).

Оператор — pass. Он ничего не делает, но используется как заглушка, когда по синтаксису требуется инструкция (например, в пустой функции, классе,  
цикле или условии).

---

**2. What’s the process to get the home directory using ‘~’ in Python?**

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

---

**3. What are the built-in types available in Python?**

Immutable types:

- int, float, complex, bool, str, tuple, range, frozenset, bytes, NoneType

Mutable types:

- list, dict, set, bytearray, memoryview

Да, на интервью лучше делить на изменяемые и неизменяемые.

Неизменяемые (immutable):

- int, float, complex, bool, str, tuple, range, frozenset, bytes, NoneType

Изменяемые (mutable):

- list, dict, set, bytearray, memoryview

---

**4. How to find bugs or perform static analysis in a Python application?**

Use linters and type checkers: ruff / flake8 / pylint for code issues and style, mypy or pyright for static type analysis.  
Use formatters like black and import sorting (isort or ruff format) to keep consistency. Also use security/static scanners  
like bandit, plus tests and coverage (pytest, coverage) to catch issues early (often run via pre-commit and CI).

Для статанализа и поиска багов: линтеры и тайпчекеры — ruff / flake8 / pylint, для типов — mypy или pyright. Форматирование —  
black, сортировка импортов — isort или ruff. Для security-скана — bandit. Плюс тесты и покрытие (pytest, coverage), обычно  
через pre-commit и CI.

**When is the Python decorator used?**

A decorator is used when you want to extend or modify the behavior of a function or method without changing its source code.  
It wraps a function and adds functionality before or after its execution.

Common use cases: logging, authentication/authorization, caching, validation, measuring execution time, transaction handling.

Декоратор используют, когда нужно расширить или изменить поведение функции/метода без изменения её кода. Он оборачивает  
функцию и добавляет логику до или после её выполнения.

Частые случаи: логирование, авторизация, кэширование, валидация, измерение времени выполнения, управление транзакциями.

**What is the principal difference between a list and a tuple?**

The main difference is mutability: a list is mutable (can be changed after creation), while a tuple is immutable  
(cannot be modified).

Lists use [], tuples use (). Tuples are generally faster and can be used as dictionary keys (if they contain only  
immutable elements), while lists cannot.

Главное различие — изменяемость: list изменяемый (можно менять элементы), tuple неизменяемый (нельзя изменить  
после создания).

List создаётся через [], tuple — через (). Tuple обычно быстрее и может использоваться как ключ словаря (если  
содержит только immutable элементы), list — нет.

**How does Python handle memory management?**

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

**What are the principal differences between lambda and def?**

lambda creates an anonymous function in a single expression and is limited to one expression  
(no statements). It’s typically used for short, simple functions (e.g., in map, filter, sorted).

def defines a named function, can contain multiple statements, annotations, docstrings, and complex logic.  
It’s used for full-featured functions.

lambda — это анонимная функция из одного выражения (только expression, без операторов). Обычно  
используется для коротких простых функций.

def — именованная функция, может содержать несколько операторов, аннотации, docstring и сложную  
логику. Используется для полноценных функций.

**What is a built-in function that Python uses to iterate over a number sequence?**

The built-in function is range(). It generates a sequence of numbers and is commonly used in for loops.

Example: for i in range(5):

Встроенная функция — range(). Она создаёт числовую последовательность и обычно используется в цикле for.

Пример: for i in range(5):

**What are the optional statements possible inside a try-except block in Python?**

The optional clauses inside a try block are else and finally.

- else runs if no exception occurs.

- finally always runs, whether an exception occurred or not (used for cleanup).

В блоке try опционально можно использовать else и finally.

- else выполняется, если исключения не было.

- finally выполняется всегда, независимо от наличия исключения (обычно для очистки ресурсов).

**What is a string in Python?**

A string in Python is an immutable sequence of Unicode characters used to represent text.  
It is defined using single quotes, double quotes, or triple quotes for multi-line strings.

Strings support indexing, slicing, and many built-in methods for manipulation.

Строка в Python — это неизменяемая последовательность Unicode-символов, используемая для  
представления текста. Она создаётся с помощью одинарных, двойных или тройных кавычек  
(для многострочных строк).

Строки поддерживают индексацию, срезы и множество встроенных методов для работы с текстом.

**What is slicing in Python?**

Slicing is a way to extract a portion of a sequence (like a list, tuple, or string) using  
the syntax sequence[start:stop:step].
start is inclusive, stop is exclusive, and step defines the interval.

Example: my_list[1:4]

Срез (slicing) — это способ получить часть последовательности (list, tuple, string) с помощью  
синтаксиса sequence[start:stop:step].
start включается, stop не включается, step задаёт шаг.

**What is Docstring in Python?**

A docstring is a string literal used to document a module, class, function, or method.  
It is written as the first statement inside the definition, usually using triple quotes.  
It describes what the object does and can be accessed via **doc** or the help() function.

Docstring — это строка документации для модуля, класса, функции или метода. Она размещается  
первой строкой внутри определения, обычно в тройных кавычках. Описывает назначение объекта и  
доступна через **doc** или help().

**What is a function in Python programming?**

A function in Python is a reusable block of code that performs a specific task. It is defined  
using the def keyword, can accept parameters, and may return a value using return.

Functions help organize code, improve readability, and promote reusability.

Функция в Python — это переиспользуемый блок кода, который выполняет определённую задачу. Она  
определяется с помощью def, может принимать параметры и возвращать значение через return.

Функции помогают структурировать код, повышают читаемость и обеспечивают переиспользуемость.

**What is the return keyword used in Python?**

The return keyword is used to exit a function and send a value back to the caller. When return  
is executed, the function stops immediately. If no value is specified, the function returns None  
by default.

return используется для выхода из функции и возврата значения вызывающему коду. При выполнении  
return функция сразу прекращает работу. Если значение не указано, по умолчанию возвращается None.

**What is “Call by Value” in Python?**

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

**What is “Call by Reference” in Python?**

Python does not support true call by reference. It uses call by object reference (call by assignment).

The function receives a reference to the object, but you cannot rebind the caller’s variable. You can  
modify the object if it’s mutable, but reassignment inside the function does not affect the original  
variable.

В Python нет настоящего call by reference. Используется call by object reference (call by assignment).

Функция получает ссылку на объект, но нельзя изменить саму переменную у вызывающей стороны. Можно  
изменить объект, если он изменяемый, но переназначение внутри функции не меняет исходную переменную.

**What is the purpose of the id() function in Python?**

he id() function returns the unique identity of an object. In CPython, it represents the memory address  
where the object is stored. It is often used to check whether two variables reference the same object.

Функция id() возвращает уникальный идентификатор объекта. В CPython это обычно адрес памяти объекта.  
Используется для проверки, ссылаются ли две переменные на один и тот же объект.

**What does the **name** do in Python?**

`__name__` is a special built-in variable that indicates how a Python file is being executed.

If a file is run directly, `__name__` == "`__main__`".
If it is imported as a module, `__name__` equals the module’s name.

It is commonly used to prevent certain code from running when the file is imported.

`__name__` — это специальная встроенная переменная, которая показывает, как запускается файл.

Если файл запущен напрямую, `__name__` == "`__main__`".
Если импортирован как модуль, `__name__` равен имени модуля.

Обычно используется, чтобы код выполнялся только при прямом запуске файла.

**What is GIL in Python language?**

The GIL (Global Interpreter Lock) is a mutex in CPython that allows only one thread to execute Python  
bytecode at a time. It prevents true parallel execution of threads in CPU-bound programs.

It simplifies memory management and makes CPython thread-safe, but limits multi-threaded performance  
for CPU-intensive tasks (multiprocessing can be used instead).

GIL (Global Interpreter Lock) — это механизм в CPython, который позволяет выполнять байткод Python  
только одному потоку одновременно. Он не даёт потокам работать параллельно в CPU-bound задачах.

Он упрощает управление памятью и делает интерпретатор потокобезопасным, но ограничивает производительность  
при вычислительно тяжёлых задачах (вместо этого используют multiprocessing).

**How is the Python thread safe?**

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

**How does Python manage memory?**

Python manages memory automatically using reference counting and a cyclic garbage collector.

Each object has a reference counter. When the reference count drops to zero, the memory is  
immediately freed. To handle circular references, Python uses a cyclic garbage collector that detects  
and cleans up unreachable object cycles.

Memory is allocated in a private heap managed by Python’s memory manager (PyMalloc in CPython).

Python управляет памятью автоматически через reference counting и циклический garbage collector.

У каждого объекта есть счётчик ссылок. Когда он становится равным нулю, память освобождается.  
Для обработки циклических ссылок используется циклический сборщик мусора.

Память выделяется в private heap, которым управляет внутренний менеджер памяти Python (PyMalloc в CPython).

**What is a tuple in Python?**

A tuple in Python is an immutable ordered collection of elements. It can store different data types  
and allows indexing and slicing. Tuples are defined using parentheses () or by separating values with commas.

Because they are immutable, tuples can be used as dictionary keys (if all elements are immutable).

Tuple в Python — это неизменяемая упорядоченная коллекция элементов. Она может содержать разные типы  
данных и поддерживает индексацию и срезы. Создаётся с помощью () или просто через запятые.

Так как tuple неизменяемый, его можно использовать как ключ словаря (если все элементы тоже immutable).

**What is a dictionary in Python programming?**

A dictionary in Python is a built-in mutable mapping type that stores data as key–value pairs. Keys must  
be unique and immutable, while values can be of any type. Dictionaries are defined using {}.

They provide fast lookup, insertion, and deletion by key.

Dictionary в Python — это встроенный изменяемый тип отображения (mapping), который хранит данные в виде  
пар ключ–значение. Ключи должны быть уникальными и неизменяемыми, значения могут быть любого типа.
Создаётся с помощью {}.

Обеспечивает быстрый доступ, добавление и удаление по ключу.

**What is the set object in Python?**

A set in Python is a built-in mutable, unordered collection of unique elements. It does not allow duplicate  
values and supports mathematical set operations like union, intersection, difference, and symmetric difference.

Sets are created using {} (with elements) or the set() constructor.

Set в Python — это встроенная изменяемая, неупорядоченная коллекция уникальных элементов. Дубликаты не  
допускаются. Поддерживает операции множеств: объединение, пересечение, разность и симметрическую разность.

Создаётся с помощью {} (с элементами) или конструктора set().

**What is Class in Python?**

A class in Python is a blueprint for creating objects. It defines attributes (data) and methods (functions)  
that describe the behavior of the objects. A class is defined using the class keyword.

Classes are the foundation of object-oriented programming (OOP) in Python.

Класс в Python — это шаблон для создания объектов. Он определяет атрибуты (данные) и методы (функции),  
которые описывают поведение объектов. Объявляется с помощью ключевого слова class.

Классы — основа объектно-ориентированного программирования (ООП) в Python.

**What are Attributes and Methods in a Python class?**

Attributes are variables that belong to a class or its instances. They store the state or data of an object  
(instance attributes and class attributes).

Methods are functions defined inside a class that describe the behavior of its objects. They usually operate  
on the object’s attributes and take self as the first parameter.

Атрибуты — это переменные, принадлежащие классу или его экземплярам. Они хранят состояние или данные объекта  
(атрибуты экземпляра и атрибуты класса).

Методы — это функции, определённые внутри класса, которые описывают поведение объекта. Обычно они работают с  
атрибутами и принимают self как первый параметр.

**How to assign values for the Class attributes at runtime?**
You can assign class attributes at runtime either directly through the class or dynamically using setattr().

Example:

```
MyClass.attribute = value

setattr(MyClass, "attribute", value)
```

This changes the attribute for the class itself (affects all instances unless overridden).

Значения атрибутам класса во время выполнения можно присвоить напрямую через класс или через setattr().

Это изменяет атрибут на уровне класса (влияет на все экземпляры, если не переопределено в объекте).

**What is Inheritance in Python programming?**

Inheritance is an OOP feature where a class (child/subclass) derives from another class (parent/base class)  
and inherits its attributes and methods. It allows code reuse and extension of existing functionality.

It is defined by passing the parent class in parentheses: class Child(Parent):

Наследование — это механизм ООП, при котором один класс (дочерний) наследует атрибуты и методы другого класса  
(родительского). Это позволяет переиспользовать код и расширять функциональность.

Объявляется через указание родительского класса в скобках: class Child(Parent):

**What is Composition in Python?**

Composition is an OOP concept where one class contains an instance of another class as an attribute, instead  
of inheriting from it. It represents a “has-a” relationship and promotes flexibility and loose coupling.

Example: a Car class containing an Engine object.

Композиция — это принцип ООП, при котором один класс содержит объект другого класса как атрибут, а не наследуется  
от него. Это отношение типа “has-a” и даёт большую гибкость и слабую связанность.

Пример: класс Car, который содержит объект Engine.

**What are Errors and Exceptions in Python programs?**

Errors are problems in a program that prevent it from running correctly. They can be syntax errors (detected before  
execution) or runtime errors.

Exceptions are runtime errors that occur during program execution and can be handled using try, except, else, and  
finally. Handling exceptions allows the program to continue running instead of crashing.

Ошибки (Errors) — это проблемы в программе, которые мешают её корректному выполнению. Это могут быть синтаксические  
ошибки или ошибки времени выполнения.

Исключения (Exceptions) — это ошибки, возникающие во время выполнения программы, которые можно обработать с помощью  
try, except, else, finally. Обработка исключений позволяет программе не завершаться аварийно.

**How do you raise exceptions for a predefined condition in Python?**

You raise exceptions using the raise keyword with a specific exception class.

Example:

```
raise ValueError("Invalid input")
```

You can also define custom exceptions by inheriting from Exception.

Исключения вызываются с помощью ключевого слова raise и указания класса исключения.

Также можно создавать собственные исключения, наследуясь от Exception.

**What are Python Iterators?**

Python iterators are objects that implement the iterator protocol: they have **iter**() and **next**() methods.  
They produce items one at a time and raise StopIteration when no more items are available.

Iterators are used in loops like for and allow lazy iteration (values are generated on demand).

Итераторы в Python — это объекты, реализующие протокол итератора: методы **iter**() и **next**(). Они возвращают  
элементы по одному и вызывают StopIteration, когда элементы заканчиваются.

Используются в цикле for и позволяют ленивую (lazy) итерацию — значения создаются по мере необходимости.

**What is the difference between an Iterator and an Iterable?**

An Iterable is an object that can return an iterator. It implements the `__iter__`() method and can be used  
in a for loop (e.g., list, tuple, string).

An Iterator is an object that actually produces the next value. It implements both `__iter__`() and `__next__`()  
and keeps state during iteration.

Iterable можно перебирать — он реализует `__iter__`() и возвращает итератор (например, list, tuple, string).

Iterator — это объект, который возвращает элементы по одному. Он реализует `__iter__`() и `__next__`() и хранит  
состояние во время итерации.

**What are Python Generators?**

Python generators are a special type of iterator that produce values lazily using the yield keyword.  
Instead of returning all values at once, they generate them one by one and maintain their state between calls.

They are memory-efficient and commonly used for large datasets or infinite sequences.

Генераторы в Python — это особый тип итераторов, которые создают значения лениво с помощью yield.  
Они не возвращают все данные сразу, а генерируют их по одному и сохраняют своё состояние между вызовами.

Они экономят память и часто используются для больших наборов данных или бесконечных последовательностей.
