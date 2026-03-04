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

**2. What’s the process to get the home directory using ‘~’ in Python?**

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

**3. What are the built-in types available in Python?**

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

**4. What is the principal difference between a list and a tuple?**

---

The main difference is mutability: a list is mutable (can be changed after creation), while a tuple is immutable  
(cannot be modified).

Lists use [], tuples use (). Tuples are generally faster and can be used as dictionary keys (if they contain only  
immutable elements), while lists cannot.

Главное различие — изменяемость: list изменяемый (можно менять элементы), tuple неизменяемый (нельзя изменить  
после создания).

List создаётся через [], tuple — через (). Tuple обычно быстрее и может использоваться как ключ словаря (если  
содержит только immutable элементы), list — нет.

**5. How does Python handle memory management?**

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

**6. What are the principal differences between lambda and def?**

---

lambda creates an anonymous function in a single expression and is limited to one expression  
(no statements). It’s typically used for short, simple functions (e.g., in map, filter, sorted).

def defines a named function, can contain multiple statements, annotations, docstrings, and complex logic.  
It’s used for full-featured functions.

lambda — это анонимная функция из одного выражения (только expression, без операторов). Обычно  
используется для коротких простых функций.

def — именованная функция, может содержать несколько операторов, аннотации, docstring и сложную  
логику. Используется для полноценных функций.

**7. What is a built-in function that Python uses to iterate over a number sequence?**

---

The built-in function is range(). It generates a sequence of numbers and is commonly used in for loops.

Example: for i in range(5):

Встроенная функция — range(). Она создаёт числовую последовательность и обычно используется в цикле for.

Пример: for i in range(5):

**8. What are the optional statements possible inside a try-except block in Python?**

---

The optional clauses inside a try block are else and finally.

- else runs if no exception occurs.

- finally always runs, whether an exception occurred or not (used for cleanup).

В блоке try опционально можно использовать else и finally.

- else выполняется, если исключения не было.

- finally выполняется всегда, независимо от наличия исключения (обычно для очистки ресурсов).

**9. What is a string in Python?**

---

A string in Python is an immutable sequence of Unicode characters used to represent text.  
It is defined using single quotes, double quotes, or triple quotes for multi-line strings.

Strings support indexing, slicing, and many built-in methods for manipulation.

Строка в Python — это неизменяемая последовательность Unicode-символов, используемая для  
представления текста. Она создаётся с помощью одинарных, двойных или тройных кавычек  
(для многострочных строк).

Строки поддерживают индексацию, срезы и множество встроенных методов для работы с текстом.

**10. What is slicing in Python?**

---

Slicing is a way to extract a portion of a sequence (like a list, tuple, or string) using  
the syntax sequence[start:stop:step].
start is inclusive, stop is exclusive, and step defines the interval.

Example: my_list[1:4]

Срез (slicing) — это способ получить часть последовательности (list, tuple, string) с помощью  
синтаксиса sequence[start:stop:step].
start включается, stop не включается, step задаёт шаг.

**11. What is Docstring in Python?**

---

A docstring is a string literal used to document a module, class, function, or method.  
It is written as the first statement inside the definition, usually using triple quotes.  
It describes what the object does and can be accessed via \_\_doc\_\_ or the help() function.

Docstring — это строка документации для модуля, класса, функции или метода. Она размещается  
первой строкой внутри определения, обычно в тройных кавычках. Описывает назначение объекта и  
доступна через \_\_doc\_\_ или help().

**12. What is a function in Python programming?**

---

A function in Python is a reusable block of code that performs a specific task. It is defined  
using the def keyword, can accept parameters, and may return a value using return.

Functions help organize code, improve readability, and promote reusability.

Функция в Python — это переиспользуемый блок кода, который выполняет определённую задачу. Она  
определяется с помощью def, может принимать параметры и возвращать значение через return.

Функции помогают структурировать код, повышают читаемость и обеспечивают переиспользуемость.

**13. What is the return keyword used in Python?**

---

The return keyword is used to exit a function and send a value back to the caller. When return  
is executed, the function stops immediately. If no value is specified, the function returns None  
by default.

return используется для выхода из функции и возврата значения вызывающему коду. При выполнении  
return функция сразу прекращает работу. Если значение не указано, по умолчанию возвращается None.

**14. What is “Call by Value” in Python?**

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

**15. What is “Call by Reference” in Python?**

---

Python does not support true call by reference. It uses call by object reference (call by assignment).

The function receives a reference to the object, but you cannot rebind the caller’s variable. You can  
modify the object if it’s mutable, but reassignment inside the function does not affect the original  
variable.

В Python нет настоящего call by reference. Используется call by object reference (call by assignment).

Функция получает ссылку на объект, но нельзя изменить саму переменную у вызывающей стороны. Можно  
изменить объект, если он изменяемый, но переназначение внутри функции не меняет исходную переменную.

**16. What is the purpose of the id() function in Python?**

---

The id() function returns the unique identity of an object. In CPython, it represents the memory address  
where the object is stored. It is often used to check whether two variables reference the same object.

Функция id() возвращает уникальный идентификатор объекта. В CPython это обычно адрес памяти объекта.  
Используется для проверки, ссылаются ли две переменные на один и тот же объект.

**17. How is the Python thread safe?**

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

**18. What is a tuple in Python?**

---

A tuple in Python is an immutable ordered collection of elements. It can store different data types  
and allows indexing and slicing. Tuples are defined using parentheses () or by separating values with commas.

Because they are immutable, tuples can be used as dictionary keys (if all elements are immutable).

Tuple в Python — это неизменяемая упорядоченная коллекция элементов. Она может содержать разные типы  
данных и поддерживает индексацию и срезы. Создаётся с помощью () или просто через запятые.

Так как tuple неизменяемый, его можно использовать как ключ словаря (если все элементы тоже immutable).

**19. What is a dictionary in Python programming?**

---

A dictionary in Python is a built-in mutable mapping type that stores data as key–value pairs. Keys must  
be unique and immutable, while values can be of any type. Dictionaries are defined using {}.

They provide fast lookup, insertion, and deletion by key.

Dictionary в Python — это встроенный изменяемый тип отображения (mapping), который хранит данные в виде  
пар ключ–значение. Ключи должны быть уникальными и неизменяемыми, значения могут быть любого типа.
Создаётся с помощью {}.

Обеспечивает быстрый доступ, добавление и удаление по ключу.

**20. What is the set object in Python?**

---

A set in Python is a built-in mutable, unordered collection of unique elements. It does not allow duplicate  
values and supports mathematical set operations like union, intersection, difference, and symmetric difference.

Sets are created using {} (with elements) or the set() constructor.

Set в Python — это встроенная изменяемая, неупорядоченная коллекция уникальных элементов. Дубликаты не  
допускаются. Поддерживает операции множеств: объединение, пересечение, разность и симметрическую разность.

Создаётся с помощью {} (с элементами) или конструктора set().

**21. What is Class in Python?**

---

A class in Python is a blueprint for creating objects. It defines attributes (data) and methods (functions)  
that describe the behavior of the objects. A class is defined using the class keyword.

Classes are the foundation of object-oriented programming (OOP) in Python.

Класс в Python — это шаблон для создания объектов. Он определяет атрибуты (данные) и методы (функции),  
которые описывают поведение объектов. Объявляется с помощью ключевого слова class.

Классы — основа объектно-ориентированного программирования (ООП) в Python.

**22. What are Attributes and Methods in a Python class?**

---

Attributes are variables that belong to a class or its instances. They store the state or data of an object  
(instance attributes and class attributes).

Methods are functions defined inside a class that describe the behavior of its objects. They usually operate  
on the object’s attributes and take self as the first parameter.

Атрибуты — это переменные, принадлежащие классу или его экземплярам. Они хранят состояние или данные объекта  
(атрибуты экземпляра и атрибуты класса).

Методы — это функции, определённые внутри класса, которые описывают поведение объекта. Обычно они работают с  
атрибутами и принимают self как первый параметр.

**23. How to assign values for the Class attributes at runtime?**

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

**24. What is Inheritance in Python programming?**

---

Inheritance is an OOP feature where a class (child/subclass) derives from another class (parent/base class)  
and inherits its attributes and methods. It allows code reuse and extension of existing functionality.

It is defined by passing the parent class in parentheses: class Child(Parent):

Наследование — это механизм ООП, при котором один класс (дочерний) наследует атрибуты и методы другого класса  
(родительского). Это позволяет переиспользовать код и расширять функциональность.

Объявляется через указание родительского класса в скобках: class Child(Parent):

**25. What is Composition in Python?**

---

Composition is an OOP concept where one class contains an instance of another class as an attribute, instead  
of inheriting from it. It represents a “has-a” relationship and promotes flexibility and loose coupling.

Example: a Car class containing an Engine object.

Композиция — это принцип ООП, при котором один класс содержит объект другого класса как атрибут, а не наследуется  
от него. Это отношение типа “has-a” и даёт большую гибкость и слабую связанность.

Пример: класс Car, который содержит объект Engine.

**26. What are Errors and Exceptions in Python programs?**

---

Errors are problems in a program that prevent it from running correctly. They can be syntax errors (detected before  
execution) or runtime errors.

Exceptions are runtime errors that occur during program execution and can be handled using try, except, else, and  
finally. Handling exceptions allows the program to continue running instead of crashing.

Ошибки (Errors) — это проблемы в программе, которые мешают её корректному выполнению. Это могут быть синтаксические  
ошибки или ошибки времени выполнения.

Исключения (Exceptions) — это ошибки, возникающие во время выполнения программы, которые можно обработать с помощью  
try, except, else, finally. Обработка исключений позволяет программе не завершаться аварийно.

**27. How do you raise exceptions for a predefined condition in Python?**

---

You raise exceptions using the raise keyword with a specific exception class.

Example:

```python
raise ValueError("Invalid input")
```

You can also define custom exceptions by inheriting from Exception.

Исключения вызываются с помощью ключевого слова raise и указания класса исключения.

Также можно создавать собственные исключения, наследуясь от Exception.

**28. What are Python Iterators?**

---

Python iterators are objects that implement the iterator protocol: they have \_\iter\_\_() and \_\next\_\_() methods.  
They produce items one at a time and raise StopIteration when no more items are available.

Iterators are used in loops like for and allow lazy iteration (values are generated on demand).

Итераторы в Python — это объекты, реализующие протокол итератора: методы \_\iter\_\_() и \_\next\_\_(). Они возвращают  
элементы по одному и вызывают StopIteration, когда элементы заканчиваются.

Используются в цикле for и позволяют ленивую (lazy) итерацию — значения создаются по мере необходимости.

**29. What is the difference between an Iterator and an Iterable?**

---

An Iterable is an object that can return an iterator. It implements the `__iter__`() method and can be used  
in a for loop (e.g., list, tuple, string).

An Iterator is an object that actually produces the next value. It implements both `__iter__`() and `__next__`()  
and keeps state during iteration.

Iterable можно перебирать — он реализует `__iter__`() и возвращает итератор (например, list, tuple, string).

Iterator — это объект, который возвращает элементы по одному. Он реализует `__iter__`() и `__next__`() и хранит  
состояние во время итерации.

**30. What are Python Generators?**

---

Python generators are a special type of iterator that produce values lazily using the yield keyword.  
Instead of returning all values at once, they generate them one by one and maintain their state between calls.

They are memory-efficient and commonly used for large datasets or infinite sequences.

Генераторы в Python — это особый тип итераторов, которые создают значения лениво с помощью yield.  
Они не возвращают все данные сразу, а генерируют их по одному и сохраняют своё состояние между вызовами.

Они экономят память и часто используются для больших наборов данных или бесконечных последовательностей.

**31. What are metaclasses in Python, and when would you use them in your code?**

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

**32. Explain the purpose of the contextlib module and how it is used for managing resources in Python.**

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

```python
class FileManager:
    def __init__(self, filename, mode):
        self.filename = filename
        self.mode = mode

    def __enter__(self):
        self.file = open(self.filename, self.mode)
        return self.file

    def __exit__(self, exc_type, exc_value, traceback):
        self.file.close()

with FileManager('test.txt', 'w') as f:
    f.write('Hello, world!')
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

**33. What is method resolution order (MRO) in Python, and how is it determined for classes with multiple inheritance?**

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

**34. How can you work with binary data in Python, and what are the benefits of using the struct module?**

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

**35. What is the GIL, and how does it affect CPU-bound and I/O-bound tasks differently?**

---

The GIL (Global Interpreter Lock) is a mechanism in CPython that allows only one thread to execute Python bytecode at a time. It is used to simplify memory management and make the interpreter thread-safe. For CPU-bound tasks, the GIL becomes a bottleneck because multiple threads cannot run Python code in parallel on multiple CPU cores. In such cases, multiprocessing is usually used instead of multithreading. For I/O-bound tasks, the GIL is less of a problem because it is released during I/O operations (such as network requests or file access). This allows other threads to run while one thread is waiting for I/O, making multithreading effective for these tasks.

GIL (Global Interpreter Lock) — это механизм в CPython, который позволяет только одному потоку одновременно выполнять Python bytecode. Он упрощает управление памятью и делает интерпретатор потокобезопасным. Для CPU-bound задач GIL становится узким местом, потому что несколько потоков не могут выполнять Python-код параллельно на разных ядрах процессора. Поэтому в таких случаях чаще используют multiprocessing. Для I/O-bound задач GIL менее проблемен, потому что он освобождается во время операций ввода-вывода (например, сетевые запросы или работа с файлами). Пока один поток ждёт I/O, другие могут выполняться, поэтому multithreading работает эффективно.

**36. What are the key differences between the multiprocessing and threading modules in Python, and when would you use each for parallelism?**

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

**37. Describe the concept of ABCs (Abstract Base Classes) in Python and when you would use them.**

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

**38. What are Python descriptors, and how are they used to customize attribute access in classes?**

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

**39. How can you create and work with asynchronous code in Python, and what is the purpose of the await keyword?**

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

**40. What are the differences between the os.path and pathlib modules in Python for file and directory manipulation?**

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

**41. How do you serialize and deserialize Python objects, and what is the purpose of libraries like pickle and json for data interchange?**

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

**42. What is the purpose of the unittest library in Python, and how can you write unit tests for your code?**

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

**43. What are the differences between mutable and immutable data types in Python, and can you provide examples of each?**

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

**44. How can you work with JSON data in Python, and what is the purpose of the json module?**

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

**45. What is the purpose of the async and await keywords in Python, and how are they used in asynchronous programming?**

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

**46. Explain the differences between the requests and urllib libraries for making HTTP requests in Python.**

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

**47. What is the purpose of the subprocess module in Python, and how can you use it to execute external processes?**

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

**48. Explain the use of Python's built-in map, filter, and reduce functions, and provide examples of their usage.**

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

**49. How do you implement memoization in Python, and why is it useful in recursive functions?**

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

**50. Explain the benefits of using type hints (PEP 484) in Python code, and how can you use them to improve code readability and maintainability?**

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

**51. How can you work with threads in Python, and what are some common challenges and best practices when dealing with multi-threading?**

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

**52. What is the asyncio module in Python?**

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

**53. What is a coroutine in Python?**

---

A coroutine in Python is a special type of function that can pause and resume its execution. It is defined using async def. Coroutines are used in asynchronous programming to allow multiple tasks to run concurrently without blocking the program. They work with the event loop and use await to pause execution until another asynchronous operation completes.

Purpose:

- efficient handling of I/O-bound operations

- cooperative multitasking within a single thread

Корутиина в Python — это специальный тип функции, которая может приостанавливать и продолжать своё выполнение. Она объявляется с помощью async def. Корутиины используются в асинхронном программировании, чтобы несколько задач могли выполняться конкурентно без блокировки программы. Они работают через event loop и используют await, чтобы приостановить выполнение до завершения другой асинхронной операции.

Назначение:

- эффективная работа с I/O задачами

- кооперативная многозадачность в одном потоке

**54. What is a future in the concurrent.futures module?**

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

**55. How can you represent a graph in Python?**

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

**56. How *args and *kwargs are used in python**

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

**57. How will you find bugs and errors in python code?**

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

**58. Can you state the name of the tool which are used to find the bugs in python?**

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

**59. What is the purpose of the try and except keywords in Python?**

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

**60. What is the difference between the except and finally blocks in Python?**

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

**61. What is the purpose of the raise keyword in Python?**

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

**62. What is the difference between the assert statement and the raise keyword in Python?**

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

**63. What is the purpose of the else block in a try statement in Python?**

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

**64. What is the purpose of the finally block in a try statement in Python?**

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

**65. What is the difference between the try and else blocks in a try statement in Python?**

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

**66. What is the difference between a built-in exception and a custom exception in Python?**

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

**67. How do you handle multiple exceptions in Python?**

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

**68. What is the purpose of the \_\_init\_\_.py file in a Python package?**

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

**69. What is the purpose of the if \_\_name\_\_ == "\_\_main\_\_": block in a Python script?**

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

**70. Explain the Global Interpreter Lock (GIL) in Python.**

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

**71. How can you remove duplicates from a list in Python?**

---

Duplicates can be removed from a list in several ways. **Using a set** (simplest way): `list(set(my_list))` This removes duplicates but does not preserve order.
Preserving order using dict: `list(dict.fromkeys(my_list))`
**Using a loop:** Create a new list and add elements only if they are not already present.
Most commonly **used approach**: `list(dict.fromkeys(my_list))` because it removes duplicates while keeping the original order.

Удалить дубликаты из списка можно несколькими способами. Через set (самый простой способ): `list(set(my_list))` Удаляет дубликаты, но не сохраняет порядок элементов. С сохранением порядка через dict: `list(dict.fromkeys(my_list))`

Через цикл: Создать новый список и добавлять элементы только если их там ещё нет.
Чаще всего используют `list(dict.fromkeys(my_list))`, потому что он удаляет дубликаты и сохраняет порядок элементов.

**72. What is a lambda function in Python, and how is it different from a regular function?**

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

**73. What are list comprehensions, and how do they work in Python?**

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

**74. What is the purpose of the super() function in Python?**

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

**75. How can you iterate over the items of a dictionary in Python?**

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

**76. Explain the purpose of the global keyword in Python.**

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

**77. What is the difference between a deep copy and a shallow copy of an object in Python?**

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

**78. What is a decorator in Python, and how is it used?**

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

**79. What is the purpose of the is operator in Python?**

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

**80. What is the pass statement in Python, and when is it used?**

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

**81. Explain the purpose of the break and continue statements in Python loops.**

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

**82. What is a generator in Python, and how is it different from a regular function?**

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

**83. How do you create a list of unique random numbers in Python?**

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

**84. What are the built-in data types for numbers in Python, and how are they different?**

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

**85. How is memory managed in Python?**

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

**86. What are Python namespaces? Why are they used?**

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

**87. What is Scope Resolution in Python?**

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

**88. How does Python support object-oriented programming?**

---

Python supports object-oriented programming by allowing programs to be structured using classes and objects.

Main OOP features in Python:

- Encapsulation — combining data and methods inside a class

- Inheritance — creating new classes based on existing ones to reuse code

- Polymorphism — allowing the same method name to behave differently for different objects

- Abstraction — hiding implementation details and exposing only necessary functionality

Purpose:

- organize code into reusable components

- improve code maintainability and scalability

Python поддерживает объектно-ориентированное программирование, позволяя строить программы с использованием классов и объектов.

Основные возможности OOP в Python:

- Инкапсуляция — объединение данных и методов внутри класса

- Наследование — создание новых классов на основе существующих для повторного использования кода

- Полиморфизм — один и тот же метод может работать по-разному для разных объектов

- Абстракция — скрытие деталей реализации и предоставление только необходимого интерфейса

Назначение:

- организация кода в переиспользуемые компоненты

- улучшение поддержки и масштабируемости программы.

**89. How do you achieve encapsulation in Python?**

---

Encapsulation in Python is achieved by controlling access to class attributes and methods.

Python uses naming conventions for access levels:

- Public — normal attributes and methods, accessible from anywhere.

- Protected — prefix with \_ (single underscore), intended for internal use within the class or subclasses.

- Private — prefix with \_\_ (double underscore), which triggers name mangling to restrict direct access.

Encapsulation can also be implemented using getter and setter methods or the @property decorator to control how attributes are accessed or modified.

Purpose:

- protect internal state of objects

- control how data is accessed or modified

Инкапсуляция в Python достигается контролем доступа к атрибутам и методам класса.

Python использует соглашения об именовании для уровней доступа:

- Public — обычные атрибуты и методы, доступны отовсюду.

- Protected — префикс \_ (один underscore), предназначены для использования внутри класса и наследников.

- Private — префикс \_\_ (два underscore), применяется name mangling для ограничения прямого доступа.

Также инкапсуляцию реализуют через геттеры и сеттеры или декоратор @property, чтобы контролировать доступ и изменение атрибутов.

Назначение:

- защита внутреннего состояния объекта

- контроль доступа и изменения данных.

**90. What is inheritance and give an example in Python?**

Inheritance is an OOP concept where a child class (subclass) inherits attributes and methods from a parent class (base class). It allows code reuse and extension of existing functionality.

Example idea: Parent class defines common behavior, and the child class inherits it and can add or override methods.

Purpose:

- reuse existing code

- extend functionality

- organize class hierarchies

Наследование — это концепция ООП, при которой дочерний класс (subclass) наследует атрибуты и методы родительского класса (base class). Это позволяет повторно использовать код и расширять функциональность.

Пример: Родительский класс определяет общее поведение, а дочерний класс наследует его и может добавлять или переопределять методы.

Назначение:

- повторное использование кода

- расширение функциональности

- построение иерархии классов.

**91. What are class methods, static methods, and instance methods?**

---

Instance methods operate on a specific object of a class. They take self as the first parameter and can access or modify instance attributes.
Class methods operate on the class itself rather than a specific object. They take cls as the first parameter and are defined using the @classmethod decorator.
Static methods belong to the class but do not access instance or class data. They behave like regular functions placed inside a class and use the @staticmethod decorator.

Key differences:

- instance method → works with object data (self)

- class method → works with class-level data (cls)

static method → utility method that doesn’t depend on class or instance state

Instance methods работают с конкретным объектом класса. Они принимают self как первый параметр и могут изменять атрибуты объекта.
Class methods работают с самим классом, а не с отдельным объектом. Они принимают cls как первый параметр и объявляются с помощью @classmethod.
Static methods принадлежат классу, но не работают ни с объектом, ни с классом. Это обычные функции внутри класса, объявленные через @staticmethod.

Основные различия:

- instance method → работает с данными объекта (self)

- class method → работает с данными класса (cls)

- static method → вспомогательная функция, не зависящая от состояния класса или объекта.

**92. What is polymorphism in Python?**

---

Polymorphism is an OOP concept where the same method or operation can behave differently depending on the object or data type.
In Python, polymorphism allows different classes to define methods with the same name but with different implementations.

Examples:

- method overriding in inheritance

- the same function working with different object types

Purpose:

- write flexible and reusable code

- allow different objects to be used through a common interface

Полиморфизм — это концепция ООП, при которой один и тот же метод или операция могут работать по-разному в зависимости от объекта или типа данных. В Python разные классы могут иметь методы с одинаковым именем, но с разной реализацией.

Примеры:

- переопределение методов при наследовании

- одна функция работает с разными типами объектов

Назначение:

- писать гибкий и переиспользуемый код

- использовать разные объекты через общий интерфейс.

**93. Explain the use of the super() function.**

---

super() is used to call methods from a parent (base) class inside a child class. It allows a subclass to reuse and extend the functionality of the parent class. It is most commonly used to call the parent class constructor (\_\_init\_\_) when creating a subclass.

Purpose:

- access parent class methods

- avoid directly referencing the parent class name

- support proper method resolution in multiple inheritance (MRO)

super() используется для вызова методов родительского класса внутри дочернего класса. Это позволяет дочернему классу использовать и расширять функциональность родительского. Чаще всего применяется для вызова конструктора родительского класса (\_\_init\_\_) при создании наследника.

Назначение:

- доступ к методам родительского класса

- не нужно явно указывать имя родительского класса

- поддержка корректного порядка вызовов при множественном наследовании (MRO).

**94. What are magic methods in Python?**

---

Magic methods (also called dunder methods) are special methods in Python that start and end with double underscores, such as \_\_init\_\_, \_\str\_\_, or \_\add\_\_.

They allow developers to define how objects behave with built-in operations and syntax.

Examples:

\_\_init\_\_ — constructor, called when an object is created

\_\str\_\_ — defines how the object is displayed as a string

\_\add\_\_ — defines behavior for the + operator

\_\len\_\_ — defines behavior for len()

Purpose:

customize object behavior

enable operator overloading

integrate objects with Python’s built-in functions

Магические методы (или dunder methods) — это специальные методы в Python, которые начинаются и заканчиваются двойным подчёркиванием, например \_\_init\_\_, \_\str\_\_, \_\add\_\_.

Они позволяют определять, как объекты ведут себя при использовании встроенных операций и синтаксиса Python.

Примеры:

\_\_init\_\_ — конструктор, вызывается при создании объекта

\_\str\_\_ — определяет строковое представление объекта

\_\add\_\_ — определяет поведение оператора +

\_\len\_\_ — определяет работу функции len()

Назначение:

настройка поведения объектов

перегрузка операторов

интеграция объектов со встроенными функциями Python.

**95. How do you prevent a class from being inherited?**

---

In Python there is no strict built-in way to completely prevent inheritance, but it can be controlled using \_\_init_subclass\_\_() or by raising an exception when a class is subclassed.

Idea:
Override \_\_init_subclass\_\_ in the class and raise an error if someone tries to inherit from it.

Purpose:

restrict subclassing

enforce design rules in frameworks or libraries

В Python нет встроенного механизма, который полностью запрещает наследование, но его можно контролировать через \_\_init_subclass\_\_() или выбрасывая исключение при попытке наследования.

Идея:
Переопределить \_\_init_subclass\_\_ в классе и вызвать ошибку, если кто-то попытается унаследоваться.

Назначение:

ограничить наследование

обеспечить соблюдение архитектурных правил в библиотеках или фреймворках.

**96. How do you write a basic test case in Python using unittest?**

---

A basic test case using unittest is written by creating a class that inherits from unittest.TestCase and defining test methods that start with test\_.

Steps:

- import unittest

- create a test class

- write test methods

- use assertions to check results

- run tests with unittest.main()

Example idea: testing that a function returns the correct result.

Базовый тест в unittest создаётся через класс, который наследуется от unittest.TestCase, и методы тестирования, начинающиеся с test\_.

Шаги:

- импортировать unittest

- создать класс теста

- написать методы тестирования

- использовать проверки (assertions)

- запустить тесты через unittest.main()

Пример: проверка, что функция возвращает правильный результат.

**97. What is pytest and how is it used?**

---

pytest is a popular third-party testing framework for Python used to write and run automated tests.
It is simpler and more flexible than unittest, and allows writing tests as plain functions without creating classes.

How it is used:

- write test functions whose names start with test\_

- use simple assert statements to check results

- run tests using the command pytest

Benefits:

- simpler syntax

- powerful fixtures for test setup

- detailed test output

- easy integration with CI/CD

pytest — это популярный сторонний фреймворк для тестирования Python, который используется для написания и запуска автоматических тестов.
Он проще и гибче, чем unittest, и позволяет писать тесты как обычные функции, без обязательных классов.

Как используется:

- писать функции тестов с именем, начинающимся на test\_

- использовать обычные assert для проверок

- запускать тесты командой pytest

Преимущества:

- более простой синтаксис

- мощная система fixtures для подготовки тестов

- подробный вывод результатов

- удобная интеграция с CI/CD.

**98. How do you test a Python function with side effects?**

---

To test a function with side effects (file writes, network calls, DB updates, printing, time), you usually isolate the side effect and verify behavior without doing real external work.

Common approaches:

- Mock external dependencies with unittest.mock (patch, Mock) to replace network/DB/file calls and assert they were called correctly

- Use temporary resources like tempfile for file system side effects

- Capture output (stdout/logs) to verify printed/logged messages

Dependency injection: pass dependencies (client, repository, clock) into the function so they are easy to replace in tests

Best practice: keep pure logic separated from side-effect code, so most tests stay simple and fast.

Чтобы тестировать функцию с side effects (запись в файл, сеть, БД, печать, время), обычно изолируют побочный эффект и проверяют поведение без реального обращения к внешним ресурсам.

Частые подходы:

- Мокать зависимости через unittest.mock (patch, Mock), подменять сетевые/БД/файловые вызовы и проверять, что они вызваны как надо

- Использовать временные ресурсы типа tempfile для файловых операций

- Перехватывать вывод (stdout/logs), чтобы проверить печать/логирование

Dependency injection: передавать зависимости (клиент, репозиторий, часы) в функцию, чтобы их легко подменять в тестах

Лучшая практика: отделять чистую логику от кода с побочными эффектами — тогда тесты будут проще, быстрее и надёжнее.

**99. How do you log messages in Python?**

---

Messages in Python are logged using the logging module. You import logging, configure a logging level such as DEBUG, INFO, WARNING, ERROR, or CRITICAL, and write log messages using functions like logging.debug(), logging.info(), logging.warning(), logging.error(), and logging.critical().

В Python сообщения логируются с помощью модуля logging. Нужно импортировать logging, задать уровень логирования, например DEBUG, INFO, WARNING, ERROR или CRITICAL, и записывать сообщения через функции logging.debug(), logging.info(), logging.warning(), logging.error() и logging.critical().

**100. How do you use assertions in Python?**

---

Assertions in Python are used to check that a condition is true during program execution. They are written with the assert statement. If the condition is false, Python raises an AssertionError.

Example: `assert x > 0`, "x must be positive"

Ассерты в Python используются для проверки того, что условие истинно во время выполнения программы. Они записываются с помощью оператора assert. Если условие ложно, Python вызывает исключение AssertionError.

Пример: `assert x > 0`, "x должен быть положительным"

**101. What is a traceback, and how do you analyze it?**

---

A traceback is an error report in Python that shows the sequence of function calls that led to an exception. It includes the file names, line numbers, and the exact error message. To analyze it, you usually read it from the bottom up to identify the type of error and the line of code where it occurred.

Traceback в Python — это отчет об ошибке, который показывает последовательность вызовов функций, приведших к исключению. Он содержит имена файлов, номера строк и точное сообщение об ошибке. Чтобы его проанализировать, обычно читают его снизу вверх, чтобы определить тип ошибки и строку кода, где она произошла.

**102. What is typing.Protocol and when is it better than using ABC or inheritance?**

---

typing.Protocol is a way to define an interface by required methods/attributes (structural typing, “duck typing”). A class matches the protocol if it has the right members, even without inheriting from it. It’s better than ABC/inheritance when you want flexible plugin-style APIs, to accept third-party classes you can’t modify, or to avoid forcing a shared base class just for typing.

typing.Protocol — это способ описать интерфейс через набор обязательных методов/атрибутов (структурная типизация, “duck typing”). Класс соответствует протоколу, если у него есть нужные члены, даже без наследования. Это лучше, чем ABC/наследование, когда нужна гибкость (плагинные API), нужно принимать сторонние классы, которые нельзя менять, или не хочется навязывать общий базовый класс только ради типизации.

**103. What are TypeVar and Generic? Explain covariance and contravariance and when they are needed.**

---

TypeVar is used to declare a type variable that can represent different types. Generic is used to create classes or functions that operate on those type variables, allowing type-safe reusable code. Covariance means that a generic type can use a more specific type than originally declared. For example, if Cat is a subtype of Animal, then Box[Cat] can be treated as Box[Animal]. It is used when the type is only returned (read-only). Contravariance means that a generic type can accept a more general type. If Cat is a subtype of Animal, then Handler[Animal] can be used where Handler[Cat] is expected. It is used when the type is only consumed (used as input).

TypeVar используется для объявления переменной типа, которая может представлять разные типы. Generic используется для создания классов или функций, работающих с такими переменными типов, что позволяет писать безопасный и переиспользуемый код. Ковариантность означает, что обобщенный тип может использовать более конкретный тип. Например, если Cat — подтип Animal, то Box[Cat] можно рассматривать как Box[Animal]. Это используется, когда тип только возвращается (только чтение).
Контравариантность означает, что обобщенный тип может принимать более общий тип. Если Cat — подтип Animal, то Handler[Animal] можно использовать там, где ожидается Handler[Cat]. Это используется, когда тип используется только как входной параметр.

**104. TypedDict vs dataclass vs pydantic model — when should each be used?**

---

Use TypedDict when you want to type-check plain dict data (often JSON-like) with minimal overhead and no runtime validation. It’s best for static typing and interoperability with existing dicts. Use dataclass when you want a lightweight Python object with fields, defaults, and simple behavior; it’s great for internal domain models, but it doesn’t validate types at runtime by default. Use a Pydantic model when you need runtime parsing/validation/coercion (e.g., request/response schemas, config, external input), plus strong error messages and easy serialization.

TypedDict используйте, когда нужно типизировать обычные dict (часто JSON-подобные данные) с минимальными накладными расходами и без рантайм-валидации. Лучше всего подходит для статической типизации и работы с уже существующими словарями.
dataclass используйте, когда нужен легкий Python-объект с полями, дефолтами и простой логикой; отлично для внутренних моделей предметной области, но по умолчанию не делает рантайм-проверку типов.
Pydantic-модель используйте, когда нужна рантайм-валидация/парсинг/приведение типов (например, входящие/исходящие схемы API, конфиг, внешние данные), хорошие сообщения об ошибках и удобная сериализация.

**105. What is @overload in typing and when is it useful? What are common pitfalls?**

---

@overload in typing is used to define multiple type signatures for the same function so static type checkers can understand different argument/return type combinations. The overloads are only for type checking; the actual implementation is written once without @overload.

It is useful when the return type depends on the input type, for example when a function returns different types depending on arguments.

Common pitfalls:

- Overload functions must contain only type signatures and no implementation.

- Only the final non-@overload function contains the real code.

- The implementation must support all declared overload cases.

- Overloads are ignored at runtime and work only for static type checkers.

@overload в typing используется для описания нескольких сигнатур одной функции, чтобы статические анализаторы типов понимали разные комбинации аргументов и возвращаемых типов. Перегрузки используются только для проверки типов; реальная реализация функции пишется один раз без @overload.

Это полезно, когда возвращаемый тип зависит от типа входных аргументов.

Частые ошибки:

- Функции с @overload должны содержать только сигнатуры без реализации.

- Реальный код пишется только в последней функции без @overload.

- Реализация должна поддерживать все объявленные варианты перегрузки.

- Перегрузки работают только для статической проверки типов и игнорируются во время выполнения.

**106. How do you type a decorator while preserving the original function signature? (Explain ParamSpec and Concatenate.)**

---

To type a decorator and preserve the original function signature, use ParamSpec to capture the wrapped function’s parameter types and TypeVar for its return type. Then type the decorator as taking Callable[P, R] and returning Callable[P, R], so the parameters/return are preserved. Concatenate is used when the decorator adds or modifies leading parameters in the wrapper. For example, if your wrapper injects a Context as the first argument, you can express that as Callable[Concatenate[Context, P], R].

Чтобы типизировать декоратор и сохранить исходную сигнатуру функции, используют ParamSpec для “захвата” типов параметров оборачиваемой функции и TypeVar для её возвращаемого типа. Тогда декоратор типизируется как принимающий Callable[P, R] и возвращающий Callable[P, R], что сохраняет параметры и return type. Concatenate нужен, когда декоратор добавляет или меняет начальные параметры у обертки. Например, если обертка добавляет Context первым аргументом, это выражается как Callable[Concatenate[Context, P], R].

**107. NewType vs type alias — what is the practical difference?**

---

A type alias is just another name for an existing type. It does not create a new type and is treated exactly the same as the original type by type checkers.

Example: `UserId = int`

NewType creates a distinct type for static type checking, even though at runtime it behaves like the underlying type. It helps prevent mixing logically different values that share the same base type.

Example: `UserId = NewType("UserId", int)`

Практическая разница: alias — это просто другое имя существующего типа, а NewType создаёт новый логический тип для статической проверки.

Type alias — это просто другое имя существующего типа. Проверка типов рассматривает его как тот же самый тип.

Пример: `UserId = int`

NewType создаёт отдельный тип для статической проверки, хотя во время выполнения он ведёт себя как исходный тип. Это помогает избежать смешивания логически разных значений с одинаковым базовым типом.

Пример: `UserId = NewType("UserId", int)`

**108. How do you configure mypy or pyright for a real project? (strict mode, incremental checks, stub files)**

---

For a real project you usually pick one primary checker (mypy or pyright) and make it run in CI + pre-commit.

mypy (strict, incremental)

Add mypy to dev deps and create mypy.ini (or pyproject.toml section).

Enable strictness and keep incremental cache on (default).

Run on your source package(s) only (not the whole repo).

Example mypy.ini:

```ini
[mypy]
python_version = 3.11
strict = True
warn_unused_ignores = True
warn_redundant_casts = True
warn_return_any = True
no_implicit_reexport = True
pretty = True
show_error_codes = True

# incremental cache (default, but explicit is fine)

incremental = True
cache_dir = .mypy_cache

# keep third-party noise manageable

ignore_missing_imports = False

[mypy-some_untyped_lib.*]
ignore_missing_imports = True
```

Incremental / “fast” workflow:

- Local: mypy package_name/

- CI: same command, fail build on errors.

Pre-commit: run mypy only on staged files or the package (pre-commit is already incremental by scope).

Stub files (.pyi):

- Use when you can’t edit the code (vendor/third-party) or want a clean typed interface.

- Put stubs in a typings/ dir and point mypy to it:

```ini
[mypy]
mypy_path = typings
```

- Or create a package stub next to code: module.pyi overrides module.py typing view.

pyright (strict, fast, great incremental)

- Add pyright and create pyrightconfig.json.

- Use typeCheckingMode: "strict" and limit scope to your src.

Example pyrightconfig.json:

```json
{
  "typeCheckingMode": "strict",
  "pythonVersion": "3.11",
  "include": ["src"],
  "exclude": ["**/build", "**/dist", "**/.venv", "**/.mypy_cache"],
  "reportMissingTypeStubs": "warning",
  "reportUnknownMemberType": "warning"
}
```

Incremental checks:

- Pyright is designed to be fast; in editors it’s incremental automatically.

- In CI: pyright over include paths.

Stub files:

- Same .pyi idea; keep them in the import path or in a configured stub path.

- For missing third-party typings: prefer installing types-... packages when available.

Practical setup in a repo

- Put code under src/ (recommended) and run checker only on src/your_pkg.

- Add a CI job: mypy src/your_pkg or pyright.

- Add pre-commit hook for the chosen tool.

Для реального проекта обычно выбирают один основной проверяющий (mypy или pyright) и запускают его в CI + pre-commit.

1. mypy (strict, incremental)

- Добавь mypy в dev-зависимости и создай mypy.ini (или секцию в pyproject.toml).

- Включи строгий режим и оставь incremental cache (по умолчанию он включен).

- Проверяй только свои пакеты/папки с кодом, а не весь репозиторий.

Пример mypy.ini:

```ini
[mypy]
python_version = 3.11
strict = True
warn_unused_ignores = True
warn_redundant_casts = True
warn_return_any = True
no_implicit_reexport = True
pretty = True
show_error_codes = True

incremental = True
cache_dir = .mypy_cache

ignore_missing_imports = False

[mypy-some_untyped_lib.*]
ignore_missing_imports = True
```

Инкрементальные/быстрые проверки:

- Локально: mypy package_name/

- В CI: то же самое, падать при ошибках.

- В pre-commit: обычно запускают по пакету или по измененным файлам (и так быстро).

Stub-файлы (.pyi):

- Нужны, когда нельзя менять код (вендор/сторонний) или хочется отделить интерфейс типизации.

- Положи стабы в typings/ и укажи mypy путь:

```ini
[mypy]
mypy_path = typings
```

- Или module.pyi рядом с module.py — будет использоваться для типизации.

2. pyright (strict, быстрый, отличный incremental)

- Добавь pyright и создай pyrightconfig.json.

- Включи typeCheckingMode: "strict" и ограничь область include своим src.

- Пример pyrightconfig.json:

```json
{
  "typeCheckingMode": "strict",
  "pythonVersion": "3.11",
  "include": ["src"],
  "exclude": ["**/build", "**/dist", "**/.venv", "**/.mypy_cache"],
  "reportMissingTypeStubs": "warning",
  "reportUnknownMemberType": "warning"
}
```

Инкрементальные проверки:

- В редакторе pyright работает инкрементально сам.

- В CI: pyright по путям из include.

Stub-файлы:

- Те же .pyi: держи их в import path или в настроенном пути.

- Для библиотек без типов чаще всего ставят types-... пакет, если есть.

3. Рекомендованный минимум для репы

- Код в src/, проверка только src/your_pkg.

- CI job: mypy src/your_pkg или pyright.

- pre-commit hook на выбранный инструмент.

- Строгость держать глобально, а послабления делать точечно по модулям/пакетам.

**109. What is the difference between asyncio.Task and asyncio.Future?**

---

asyncio.Future is a low-level object that represents a result that will be available in the future. It does not run a coroutine by itself; it only stores the eventual result or exception and can be awaited.
asyncio.Task is a subclass of Future that wraps and schedules a coroutine to run in the event loop. When you create a task (for example with asyncio.create_task()), the coroutine starts executing concurrently.

Практическая разница: Future — это контейнер для будущего результата, а Task — это объект, который запускает и управляет выполнением корутины.
asyncio.Future — низкоуровневый объект, представляющий результат, который появится в будущем. Он сам не выполняет корутину, а лишь хранит результат или исключение и может быть ожидаем через await.
asyncio.Task — это подкласс Future, который оборачивает корутину и планирует её выполнение в event loop. Когда создаётся Task (например через asyncio.create_task()), корутина начинает выполняться параллельно.

**110. What is structured concurrency in Python (TaskGroup) and why is it important?**

---

Structured concurrency in Python means that concurrent tasks are created and managed within a well-defined scope so their lifetime is tied to that scope. In Python it is implemented with asyncio.TaskGroup (Python 3.11+).

TaskGroup ensures that all tasks started inside the group are awaited before the block exits. If one task fails, the remaining tasks are automatically cancelled and the exception is propagated. This prevents orphaned tasks and makes error handling predictable.

Структурированная конкурентность в Python означает, что параллельные задачи создаются и управляются внутри четко определённой области, и их жизненный цикл связан с этой областью. В Python это реализовано через asyncio.TaskGroup (Python 3.11+).

TaskGroup гарантирует, что все задачи, созданные внутри группы, будут завершены до выхода из блока. Если одна задача падает с ошибкой, остальные автоматически отменяются, а исключение передается дальше. Это предотвращает «висящие» задачи и делает обработку ошибок предсказуемой.

**111. What is backpressure in async systems and how can you limit concurrency**(e.g. semaphores, bounded queues)?

---

Backpressure is a mechanism where a system slows down producers when consumers can’t keep up, preventing unbounded buffering, memory growth, and cascading latency. In async code you apply backpressure by limiting how much work can be “in flight” and by bounding queues between stages.

Common ways to limit concurrency:

- Semaphores: cap the number of concurrent operations (e.g., HTTP requests, DB calls).

- Bounded queues: producers await put() when the queue is full, naturally throttling input.

- Worker pool pattern: fixed number of consumer tasks pulling from a queue.

- Rate limiting: enforce max requests per time window (often combined with semaphores).

Backpressure (обратное давление) — это механизм, при котором система замедляет производителей, когда потребители не успевают, чтобы не росли бесконечные буферы, память и задержки. В async-коде backpressure достигается ограничением количества задач “в полёте” и ограниченными очередями между этапами обработки.

Способы ограничить конкурентность:

- Семафоры: ограничивают число одновременных операций (например, запросов/вызовов БД).

- Ограниченные очереди: await put() блокируется, когда очередь заполнена, и автоматически «душит» производителей.

- Пул воркеров: фиксированное число задач-потребителей, которые берут элементы из очереди.

- Rate limiting: ограничение запросов во времени (часто вместе с семафорами).

**112. How should cancellation be handled in asyncio?**

---

Cancellation in asyncio is delivered by raising asyncio.CancelledError inside the coroutine at an await point. You should generally let it propagate, and use try/finally to release resources (locks, semaphores) and clean up.

Key rules:

- Don’t swallow CancelledError; if you catch it, re-raise it after cleanup.

- Use finally for cleanup; keep cancellation paths fast.

- If you cancel a task, you should usually await it to ensure it finishes cleanup.

- In TaskGroup, cancellations and errors are coordinated: a failing task cancels siblings.

Отмена в asyncio приходит как исключение asyncio.CancelledError, которое возникает внутри корутины в точке await. Обычно его нужно пропускать дальше, а для освобождения ресурсов (локи, семафоры) и корректного завершения использовать try/finally.

Основные правила:

- Не “глотать” CancelledError; если поймал — после cleanup обязательно raise.

- Делай очистку в finally, и пусть путь отмены будет быстрым.

- Если отменил задачу, обычно нужно её await-нуть, чтобы дождаться cleanup.

- В TaskGroup отмены и ошибки согласованы: падение одной задачи отменяет соседние.

**113. When should you use asyncio.to_thread() or thread pool executors?**

---

Use asyncio.to_thread() (or loop.run_in_executor() / a thread pool) when you need to call blocking code from async code without freezing the event loop. Typical cases: blocking I/O libraries (non-async DB/HTTP clients, filesystem calls that block), and “mostly I/O” work that releases the GIL.
Do not use threads for CPU-bound Python work; it won’t scale due to the GIL—use processes instead.

Используйте asyncio.to_thread() (или loop.run_in_executor() / thread pool), когда из async-кода нужно вызвать блокирующую функцию и не заморозить event loop. Типичные случаи: блокирующие I/O-библиотеки (не-async клиенты БД/HTTP), операции с файловой системой и другой ввод/вывод, который блокирует поток, а также работа, которая в основном I/O и может отпускать GIL.
Не используйте потоки для CPU-bound задач на чистом Python: из-за GIL они плохо масштабируются — для этого лучше процессы.

**114. What are contextvars and how are they used to store things like request IDs or trace IDs?**

---

contextvars is a Python module that provides context-local variables. They store values that are specific to the current async task or execution context, avoiding conflicts between concurrent requests.

They are commonly used in async systems to keep per-request data such as request IDs, trace IDs, or user context without passing them through every function.

Usage pattern:

- Create a ContextVar.

- Set the value at the start of the request.

- Access it anywhere in the same async context.

contextvars — это модуль Python, который предоставляет переменные, привязанные к текущему контексту выполнения. Они хранят значения отдельно для каждой async-задачи или контекста выполнения, чтобы данные не смешивались между параллельными запросами.

Обычно используются в асинхронных системах для хранения данных запроса, например request ID, trace ID или пользовательского контекста, без необходимости передавать их через все функции.

Типичный паттерн использования:

- Создать ContextVar.

- Установить значение в начале обработки запроса.

- Читать его в любом месте внутри того же async-контекста.

**115. What is the difference between ASGI and WSGI and how does the execution model change?**

---

WSGI is a synchronous interface between Python web servers and applications. Each request is handled in a blocking way, typically using threads or processes. The server calls the application once per request and waits until it finishes.
ASGI is an asynchronous interface designed for async frameworks. It supports async/await, long-lived connections, and protocols like WebSockets. Requests are handled by an event loop where many connections can be processed concurrently without blocking threads.

Основное отличие — модель выполнения.
WSGI — это синхронный интерфейс между веб-сервером и Python-приложением. Каждый запрос обрабатывается блокирующим образом, обычно через потоки или процессы. Сервер вызывает приложение для каждого запроса и ждёт завершения обработки.
ASGI — асинхронный интерфейс, созданный для async-фреймворков. Он поддерживает async/await, долгоживущие соединения и протоколы вроде WebSocket. Запросы обрабатываются через event loop, что позволяет одновременно обслуживать множество соединений без блокировки потоков.

**116. What are \_\_slots\_\_ in Python? What benefits and limitations do they have?**

---

\_\_slots\_\_ is a class attribute that restricts the set of attributes an instance can have and stores them in a fixed structure instead of a per-instance \_\_\_dict\_\_\_\_.

Benefits:

Reduces memory usage because instances don’t need a \_\_\_dict\_\_\_\_.

Slightly faster attribute access in some cases.

Prevents creation of arbitrary new attributes.

Limitations:

You cannot add new attributes that are not listed in \_\_slots\_\_.

Instances usually do not have a \_\_\_dict\_\_\_\_ unless explicitly added.

Multiple inheritance with \_\_slots\_\_ can be complicated.

Some tools and libraries that rely on \_\_\_dict\_\_\_\_ may not work.

\_\_slots\_\_ — это атрибут класса, который ограничивает набор атрибутов объекта и хранит их в фиксированной структуре вместо обычного \_\_\_dict\_\_\_\_.

Преимущества:

Меньше потребление памяти, так как у экземпляра нет \_\_\_dict\_\_\_\_.

Иногда более быстрый доступ к атрибутам.

Нельзя случайно добавить новые атрибуты.

Ограничения:

Нельзя добавлять атрибуты, которые не указаны в \_\_slots\_\_.

Обычно у экземпляра нет \_\_\_dict\_\_\_\_, если его явно не добавить.

Множественное наследование с \_\_slots\_\_ может быть сложным.

Некоторые библиотеки и инструменты, которые используют \_\_\_dict\_\_\_\_, могут работать некорректно.

**117. How would you detect and debug memory leaks in Python?**

---

Detect by watching RSS/heap over time and comparing snapshots. Common tools: tracemalloc (Python-level allocations), gc (unreachable objects), and profilers like objgraph / pympler. For C-extension/native leaks, use OS tools (e.g., psutil/top) and native profilers.

Debug approach:

- Reproduce with a tight loop and stable workload.

- Take tracemalloc snapshots and compare “top differences”.

- Check for growing containers, caches, globals, singletons.

- Look for reference cycles and objects with **del**; use gc.get_referrers() / objgraph to see who keeps references.

- Ensure resources are closed (files, sockets) and tasks/threads are not accumulating.

Выявляют утечки, наблюдая рост памяти (RSS/heap) во времени и сравнивая снимки. Основные инструменты: tracemalloc (выделения на уровне Python), gc (не достижимые объекты), профилировщики вроде objgraph / pympler. Для утечек в C-расширениях/нативной памяти — системные инструменты и нативные профилировщики.

Подход к отладке:

- Воспроизвести утечку в цикле со стабильной нагрузкой.

- Снять tracemalloc snapshots и сравнить “top differences”.

- Проверить растущие контейнеры, кэши, глобальные переменные, синглтоны.

- Искать циклические ссылки и объекты с **del**; смотреть кто держит ссылки через gc.get_referrers() / objgraph.

- Убедиться, что ресурсы закрываются (файлы, сокеты) и не копятся задачи/потоки.

**118. How can you profile CPU usage in production?**

---

In production, prefer low-overhead sampling profilers and targeted profiling windows to avoid impacting latency.

Common approaches:

- Sampling profilers: py-spy, scalene, or Austin to capture stack samples with minimal overhead.

- Built-in cProfile only for short, controlled runs (it adds noticeable overhead).

- Continuous profiling: run an agent that periodically samples and aggregates profiles (useful for long-running services).

- Use flame graphs to find hotspots and confirm with metrics (p95 latency, CPU %, request rate).

В проде лучше использовать сэмплирующие (sampling) профилировщики с низким оверхедом и включать профилирование на короткие окна, чтобы не портить latency.

Подходы:

- Sampling профилировщики: py-spy, scalene или Austin — снимают стеки с минимальным влиянием.

- cProfile — только для коротких контролируемых запусков (заметный оверхед).

- Continuous profiling: агент, который периодически сэмплирует и агрегирует профили (удобно для долгоживущих сервисов).

- Flame graphs для поиска hot spots и сверка с метриками (p95 latency, CPU %, RPS).

**119. When should you use a list comprehension vs a generator expression?**

---

Use a list comprehension when you need the full list in memory or when the result will be reused multiple times. It evaluates immediately and returns a list.
Use a generator expression when you want lazy evaluation and lower memory usage. It produces items one by one and is useful for large datasets or when the result is consumed only once (for example in a loop or functions like sum()).

Используйте list comprehension, когда нужен готовый список в памяти или результат будет использоваться несколько раз. Он вычисляется сразу и возвращает список.
Используйте generator expression, когда нужна ленивaя (lazy) генерация и меньшее потребление памяти. Он создаёт элементы по одному и подходит для больших данных или когда результат используется только один раз (например в цикле или функциях вроде sum()).

**120. What techniques can improve I/O performance in Python?**

---

I/O performance in Python can be improved by reducing blocking operations and increasing parallelism for I/O-bound tasks.

Common techniques:

- Use asynchronous I/O (asyncio, aiohttp, async database clients).

- Use concurrency with threads for blocking I/O (thread pools).

- Batch operations instead of many small reads/writes.

- Use buffered I/O and avoid frequent disk access.

- Use connection pooling for databases or HTTP clients.

- Stream large files instead of loading everything into memory.

Производительность I/O в Python улучшается за счёт уменьшения блокирующих операций и увеличения параллельности для задач, связанных с вводом-выводом.

Основные техники:

- Использовать асинхронный I/O (asyncio, aiohttp, асинхронные клиенты БД).

- Использовать потоки для блокирующего I/O (thread pool).

- Делать пакетные операции вместо множества мелких чтений/записей.

- Использовать буферизацию и избегать частых обращений к диску.

- Использовать пул соединений для БД или HTTP-клиентов.

- Стримить большие файлы вместо полной загрузки в память.

**121. What is pyproject.toml and why is it used?**

---

pyproject.toml is a standard configuration file for Python projects that defines build system requirements and tool configuration. It was introduced by PEP 518 and PEP 621 to unify project metadata and replace multiple configuration files like setup.py, setup.cfg, and tool-specific configs.

It is used to:

- Define the build system (build-system section).

- Store project metadata (name, version, dependencies).

- Configure development tools such as black, mypy, ruff, or pytest.

- Provide a single standard place for project configuration.

pyproject.toml — это стандартный конфигурационный файл Python-проекта, который определяет требования системы сборки и настройки инструментов. Он был введён в PEP 518 и PEP 621, чтобы объединить метаданные проекта и заменить несколько файлов конфигурации, таких как setup.py, setup.cfg и отдельные конфиги инструментов.

Он используется для:

- определения системы сборки (build-system);

- хранения метаданных проекта (имя, версия, зависимости);

- настройки инструментов разработки (black, mypy, ruff, pytest);

- предоставления одного стандартного места для конфигурации проекта.

**122. What is the difference between wheels and source distributions (sdist)?**

---

A wheel is a pre-built binary distribution of a Python package. It contains compiled code and metadata, so installation is fast and does not require building the package.
A source distribution (sdist) contains the original source code of the package. During installation, the package must be built locally, which can require compilers and build dependencies.

Практическая разница: wheel устанавливается сразу, а sdist нужно сначала собрать.

Wheel — это уже собранный бинарный пакет Python. В нём есть скомпилированный код и метаданные, поэтому установка происходит быстро и без этапа сборки.
Source distribution (sdist) — это архив с исходным кодом пакета. При установке пакет сначала собирается локально, что может требовать компилятор и зависимости для сборки.

**123. What are lock files (poetry.lock, pip-tools, pdm.lock) and why are they important?**

---

Lock files store the exact versions of all dependencies and their transitive dependencies that were resolved for a project.
They are important because they guarantee reproducible builds: every developer, CI environment, and production system installs the same dependency versions.
They also improve security and stability by preventing unexpected upgrades when dependency ranges change.
Lock files are generated by dependency managers such as Poetry (poetry.lock), pip-tools (requirements.txt from pip-compile), or PDM (pdm.lock).

Lock-файлы хранят точные версии всех зависимостей и их транзитивных зависимостей, которые были разрешены для проекта.
Они важны потому, что обеспечивают воспроизводимую сборку: у всех разработчиков, в CI и в продакшене устанавливаются одинаковые версии зависимостей.
Также они повышают стабильность и безопасность, предотвращая неожиданные обновления зависимостей при использовании диапазонов версий.
Lock-файлы генерируются менеджерами зависимостей, например Poetry (poetry.lock), pip-tools (requirements.txt, созданный pip-compile) или PDM (pdm.lock).

**124. How does semantic versioning affect API compatibility?**

---

Semantic versioning uses the format MAJOR.MINOR.PATCH and defines how version changes relate to API compatibility.
PATCH version increases for backward-compatible bug fixes.
MINOR version increases for backward-compatible new features.
MAJOR version increases when backward-incompatible changes are introduced.
This helps users understand whether upgrading a dependency will break existing code.

Семантическое версионирование использует формат MAJOR.MINOR.PATCH и определяет связь между изменением версии и совместимостью API.
PATCH увеличивается при исправлениях ошибок без нарушения обратной совместимости.
MINOR увеличивается при добавлении новых возможностей, которые не ломают совместимость.
MAJOR увеличивается, когда вносятся изменения, нарушающие обратную совместимость.
Это позволяет понять, может ли обновление зависимости сломать существующий код.

**125. What are entry points / console scripts in Python packaging?**

---

Entry points (console scripts) are a packaging feature that allows a Python package to expose executable command-line tools. When the package is installed, the packaging system generates a small wrapper script that calls a specified Python function.
They are defined in the project configuration and map a command name to a function inside the package.

Entry points / console scripts — это механизм упаковки Python, который позволяет пакету предоставлять исполняемые команды для командной строки. При установке пакета система создаёт небольшой скрипт-обёртку, который вызывает указанную функцию Python.
Они объявляются в конфигурации проекта и связывают имя команды с функцией внутри пакета.

**126. What are common mistakes when using mock / patch in Python tests?**

Common mistakes when using mock / patch:

- Patching the wrong location. You must patch where the object is used, not where it is originally defined.

- Forgetting to stop patches. Use decorators, context managers, or fixtures so patches are automatically cleaned up.

- Over-mocking. Tests become fragile when too many internal details are mocked instead of testing behavior.

- Not setting return values or side effects properly, leading to unrealistic test behavior.

Mocking built-ins or standard library objects incorrectly, which can break unrelated parts of the test.

Частые ошибки при использовании mock / patch:

- Патчинг не того места. Нужно патчить там, где объект используется, а не где он был определён.

- Забывают остановить патчи. Лучше использовать декораторы, контекстные менеджеры или фикстуры.

- Чрезмерное мокирование. Тесты становятся хрупкими, когда мокаются внутренние детали вместо проверки поведения.

- Неправильно заданные return_value или side_effect, из-за чего тест работает нереалистично.

- Неправильное мокирование встроенных или стандартных объектов, что может ломать другие части теста.

**127. What are the main types of software tests (unit, integration, end-to-end)? Explain the purpose of each type and when they should be used.**

---

Unit tests verify small, isolated pieces of code such as functions or classes. They usually mock external dependencies (databases, APIs, files) and run very fast. They are used during development to quickly check logic and prevent regressions.

Integration tests verify how multiple components work together, for example an application interacting with a database or external service. They test real interactions between modules and help detect problems in configuration, data flow, or interfaces.

End-to-end (E2E) tests verify the complete system from the user’s perspective. They simulate real user behavior and test the entire workflow across all components (UI, backend, database, external services). They are slower but ensure the whole system works correctly.

Unit tests проверяют небольшие изолированные части кода, например функции или классы. Обычно они используют моки для внешних зависимостей (база данных, API, файлы) и выполняются очень быстро. Их используют во время разработки для проверки логики и предотвращения регрессий.

Integration tests проверяют, как несколько компонентов работают вместе, например взаимодействие приложения с базой данных или внешним сервисом. Они тестируют реальные взаимодействия между модулями и помогают обнаружить проблемы в конфигурации, потоке данных или интерфейсах.

End-to-end (E2E) tests проверяют систему целиком с точки зрения пользователя. Они имитируют реальные действия пользователя и тестируют полный рабочий процесс через все компоненты (UI, backend, база данных, внешние сервисы). Такие тесты медленнее, но подтверждают, что вся система работает корректно.

**128. What is property-based testing (e.g. Hypothesis) and when is it useful?**

---

Property-based testing verifies that code satisfies general properties instead of checking specific examples. Tools like Hypothesis automatically generate many random inputs to test whether the defined properties always hold.
It is useful for testing edge cases, complex logic, and functions that should work correctly for a wide range of inputs. It helps discover unexpected bugs that example-based tests might miss.

Property-based testing — это подход к тестированию, при котором проверяются общие свойства программы, а не конкретные примеры входных данных. Инструменты вроде Hypothesis автоматически генерируют множество случайных входных значений и проверяют, выполняются ли заданные свойства.
Этот подход полезен для поиска граничных случаев, тестирования сложной логики и функций, которые должны корректно работать для большого диапазона входных данных. Он помогает находить ошибки, которые обычные тесты с фиксированными примерами могут пропустить.

**129. How do you test asynchronous code in Python?**

---

Use an async-capable test runner and await the code under test. The most common approach is pytest + pytest-asyncio (or anyio plugin), marking async tests and running them on an event loop.

Typical practices:

- Mark async tests (e.g. @pytest.mark.asyncio) and await coroutines.

- Use AsyncMock to mock async functions.

- Control time with fake clocks (e.g. anyio time or libraries like freezegun for sync parts) to avoid real sleeps.

- Use TaskGroup/cancellation tests by asserting tasks are cancelled and resources cleaned up.

Тестируйте async-код с помощью раннера, который умеет асинхронные тесты, и делайте await для проверяемых корутин. Самый частый вариант — pytest + pytest-asyncio (или плагин anyio), где async-тесты запускаются в event loop.

Практики:

- Помечать async-тесты (например @pytest.mark.asyncio) и await-ить корутины.

- Использовать AsyncMock для моков async-функций.

- Контролировать время “фейковыми” часами, чтобы не делать реальные sleep.

- Проверять TaskGroup/отмену, убеждаясь что задачи отменяются и cleanup выполняется.

**130. What are contract tests and when should they be used?**

---

Contract tests verify that two systems (usually a service and its client) follow an agreed interface or contract. They ensure that requests, responses, and data formats remain compatible between the provider and the consumer.
They are useful in distributed systems and microservices to detect breaking API changes early without needing full end-to-end tests between services.

Contract tests — это тесты, которые проверяют, что два взаимодействующих сервиса (обычно клиент и сервер) соблюдают согласованный контракт интерфейса. Они гарантируют, что формат запросов, ответов и структура данных остаются совместимыми.
Такие тесты полезны в распределённых системах и микросервисной архитектуре, чтобы рано обнаруживать несовместимые изменения API без необходимости запускать полноценные end-to-end тесты между сервисами.

**131. What is structured logging and why is it important in distributed systems?**

---

Structured logging means writing logs in a structured format (for example JSON) where log entries contain key-value fields instead of only plain text messages.
This is important in distributed systems because logs can be easily parsed, indexed, and searched by log aggregation systems. It also allows attaching metadata such as request IDs, trace IDs, service names, and user IDs, which helps correlate events across multiple services.

Структурированное логирование — это запись логов в структурированном формате (например JSON), где записи содержат поля ключ-значение, а не только текстовые сообщения.
Это важно для распределённых систем, потому что такие логи легко парсить, индексировать и искать в системах агрегации логов. Также можно добавлять метаданные, например request ID, trace ID, имя сервиса или ID пользователя, что помогает связывать события между разными сервисами.

**132. How should retry, circuit breakers, and idempotency be implemented?**

---

Retry, circuit breakers, and idempotency should be implemented together to avoid making failures worse.

Retry:

- Retry only transient errors (timeouts, 429, 503, network resets), not validation/4xx (except 429).

- Use exponential backoff + jitter; cap max delay and max attempts.

- Set per-attempt timeout and an overall deadline.

- Don’t retry non-idempotent operations unless you have idempotency keys.

Circuit breaker:

- Track failures per dependency; when failure rate crosses a threshold, open the circuit.

- In open state: fail fast (or serve fallback) for a cool-down period.

- Use half-open probing: allow a small number of test requests to decide recovery.

- Keep it isolated per endpoint/host to avoid taking down everything.

Idempotency:

- Ensure repeated requests have the same effect (especially for POST creating resources).

- Use an Idempotency-Key header (or request id) + store the result keyed by (client, key) with TTL.

- Server must return the same response for the same key and reject conflicting payloads for the same key.

- Design operations as idempotent where possible (PUT for replace, “create-if-not-exists”, upserts).

Ретраи, circuit breaker и идемпотентность нужно делать вместе, иначе ретраи могут усилить аварию.

Retry (повтор):

- Повторять только временные ошибки (timeouts, 429, 503, сетевые сбои), а не логические/4xx (кроме 429).

- Использовать экспоненциальную задержку + jitter, с лимитами на число попыток и максимальную паузу.

- Делать таймаут на попытку и общий deadline.

- Не ретраить неидемпотентные операции без идемпотентных ключей.

Circuit breaker:

- Считать ошибки по каждой внешней зависимости; при превышении порога открывать (fail fast).

- В открытом состоянии быстро возвращать ошибку или fallback некоторое время.

- Half-open: пускать ограниченное число пробных запросов для проверки восстановления.

- Держать отдельно по endpoint/host, чтобы не “уронить” всё сразу.

Idempotency (идемпотентность):

- Повторный запрос не должен давать второй “эффект” (особенно для POST, создающих ресурс).

- Использовать Idempotency-Key (или request id) и хранить результат по (клиент, ключ) с TTL.

- Сервер должен вернуть тот же ответ для того же ключа и не принимать другой payload с тем же ключом.

- По возможности проектировать операции идемпотентными (PUT, upsert, create-if-not-exists).

**133. What is graceful shutdown in a Python service and how should it be implemented?**

---

Graceful shutdown means stopping a service without dropping in-flight work: stop accepting new requests, let current requests finish (within a deadline), then cleanly release resources.

Typical implementation:

- Handle termination signals (SIGTERM, SIGINT) and start shutdown.

- Stop accepting new traffic (close listeners / tell load balancer “unready”).

- Cancel/stop background tasks and worker loops.

- Wait for in-flight requests/jobs with a timeout, then force-cancel.

- Close resources: DB pools, HTTP clients, file handles; flush logs/metrics.

- Exit with a clear status code.

Graceful shutdown — это корректная остановка сервиса без потери выполняющейся работы: перестать принимать новые запросы, дать текущим завершиться (с дедлайном), затем аккуратно освободить ресурсы.

Типичная реализация:

- Обработать сигналы завершения (SIGTERM, SIGINT) и запустить shutdown.

- Перестать принимать новый трафик (закрыть listener / выставить “unready” в балансировщике).

- Остановить/отменить фоновые задачи и воркеры.

- Дождаться in-flight запросов/джобов с таймаутом, затем принудительно отменить.

- Закрыть ресурсы: пулы БД, HTTP-клиенты, файлы; сбросить логи/метрики.

- Завершиться с понятным кодом выхода.

**134. What concurrency problems can occur in Python systems**

---

Common concurrency problems in Python systems:

- Race conditions — multiple threads/tasks modify shared state at the same time, leading to unpredictable results.

- Deadlocks — two or more threads/tasks wait on each other’s locks and none can proceed.

- Livelocks — tasks keep reacting to each other and retrying but no progress is made.

- Starvation — some tasks never get CPU time or resources because others continuously take them.

- Resource contention — too many threads/tasks compete for the same resource (locks, DB connections, file handles), reducing performance.

- Lost updates — concurrent writes overwrite each other without proper synchronization.

Основные проблемы конкурентности в Python-системах:

- Race condition (гонка) — несколько потоков или задач одновременно изменяют общее состояние, что приводит к непредсказуемым результатам.

- Deadlock (взаимная блокировка) — потоки или задачи ждут друг друга из-за захваченных блокировок и выполнение останавливается.

- Livelock — задачи продолжают реагировать друг на друга и повторять операции, но прогресс не происходит.

- Starvation (голодание) — некоторые задачи не получают CPU или ресурсы, потому что другие постоянно их занимают.

- Конфликт ресурсов — слишком много потоков или задач используют один и тот же ресурс (локи, соединения БД, файлы).

- Потеря обновлений — параллельные записи перезаписывают изменения друг друга без синхронизации.

**135. How should secrets be managed in Python applications?**

---

Secrets should not be stored in code or committed to git. They should be injected at runtime and access should be tightly controlled.

Good practices:

- Use environment variables or a secrets manager (Vault, AWS Secrets Manager, GCP Secret Manager, Azure Key Vault).

- Encrypt secrets at rest and restrict access with least privilege.

- Rotate secrets regularly and support revocation.

- Don’t log secrets; redact them in logs and error reports.

- Separate configs from secrets; use different values per environment (dev/staging/prod).

Секреты нельзя хранить в коде или коммитить в git. Их нужно передавать приложению во время запуска, а доступ к ним строго ограничивать.

Хорошие практики:

- Использовать переменные окружения или менеджер секретов (Vault, AWS Secrets Manager, GCP Secret Manager, Azure Key Vault).

- Шифровать секреты “на диске” и выдавать доступ по принципу минимальных прав.

- Регулярно ротировать секреты и поддерживать отзыв/замену.

- Не логировать секреты; делать редактирование (redaction) в логах и ошибках.

- Отделять конфиги от секретов и держать разные значения для dev/staging/prod.

**136. What are common Python security vulnerabilities (SSRF, command injection, path traversal)?**

---

Common Python security vulnerabilities include:

**SSRF (Server-Side Request Forgery)** Occurs when an application fetches URLs provided by users and attackers force it to access internal services or metadata endpoints. Mitigation: validate URLs, restrict allowed hosts, and block internal network ranges.

**Command injection** Happens when user input is passed to system commands (e.g., os.system, subprocess) without proper sanitization, allowing attackers to execute arbitrary commands. Mitigation: avoid shell execution (shell=True), use argument lists, and validate input.

**Path traversal** Occurs when attackers manipulate file paths (e.g., ../../etc/passwd) to access files outside the intended directory. Mitigation: normalize paths, restrict file access to specific directories, and validate input.

Основные уязвимости безопасности в Python-приложениях:

**SSRF (Server-Side Request Forgery)**
Возникает, когда приложение делает HTTP-запросы по URL, предоставленным пользователем, и злоумышленник заставляет сервер обращаться к внутренним сервисам или метаданным. Защита: проверка URL, ограничение разрешённых хостов и блокировка внутренних сетей.

**Command injection**
Возникает, когда пользовательский ввод передаётся в системные команды (os.system, subprocess) без проверки, что позволяет выполнить произвольные команды. Защита: не использовать shell=True, передавать аргументы списком и валидировать входные данные.

**Path traversal**
Возникает, когда злоумышленник изменяет путь к файлу (например ../../etc/passwd), чтобы получить доступ к файлам вне разрешённой директории. Защита: нормализация путей, ограничение доступа к директориям и проверка входных данных.

**137. What are supply chain risks in Python dependencies and how can they be mitigated?**
(pip-audit, dependency pinning, SBOM)

---

Supply chain risks occur when third-party dependencies introduce vulnerabilities or malicious code into a project. Since Python projects often rely on many packages and transitive dependencies, compromised packages can affect the entire application.

Mitigation techniques:

Dependency pinning — lock exact versions of dependencies to ensure reproducible builds and avoid unexpected updates.

Security scanning — use tools like pip-audit to detect known vulnerabilities in installed packages.

SBOM (Software Bill of Materials) — maintain a list of all dependencies used by the application to track and audit them.

Regularly update dependencies and monitor security advisories.

Use trusted package sources and verify package integrity.

Риски цепочки поставок возникают, когда сторонние зависимости содержат уязвимости или вредоносный код. Поскольку Python-проекты часто используют множество пакетов и транзитивных зависимостей, скомпрометированный пакет может повлиять на всё приложение.

Способы защиты:

Dependency pinning — фиксировать точные версии зависимостей, чтобы обеспечить воспроизводимую сборку и избежать неожиданных обновлений.

Сканирование безопасности — использовать инструменты вроде pip-audit для поиска известных уязвимостей в пакетах.

SBOM (Software Bill of Materials) — вести список всех зависимостей приложения для отслеживания и аудита.

Регулярно обновлять зависимости и следить за security-advisories.

Использовать только доверенные источники пакетов и проверять их целостность.

**138. How should you design module boundaries to avoid circular imports?**

---

Design boundaries so dependencies flow one way and shared concepts live in a stable “lower” layer.

Techniques:

Keep domain/models independent; put shared types/constants in a small common module.

Use dependency inversion: define interfaces/protocols in the consumer layer, implement them in the provider layer.

Move side effects out of imports: avoid running code at import time; use main()/factory functions.

Use local imports only as a last resort (inside functions) to break a cycle.

For typing-only dependencies, use if TYPE_CHECKING: and string annotations to avoid runtime imports.

Avoid “god modules”; split by feature, not by reuse.

Проектируй границы модулей так, чтобы зависимости шли в одну сторону, а общие сущности жили в стабильном “нижнем” слое.

Техники:

Держи domain/models независимыми; общие типы/константы вынеси в небольшой общий модуль.

Используй инверсию зависимостей: интерфейсы/протоколы объявляй в слое потребителя, реализации — в слое провайдера.

Убери сайд-эффекты из импортов: не выполняй логику при импорте; используй main()/фабрики.

Локальные импорты (внутри функций) — только как крайний способ разорвать цикл.

Для зависимостей только ради типизации: if TYPE_CHECKING: и строковые аннотации, чтобы не было runtime-импортов.

Избегай “god module”; дели по фичам, а не по попытке всё переиспользовать.

**139. What is dependency injection in Python and when should it be used?**

---

Dependency injection is a design pattern where a class or function receives its dependencies from the outside instead of creating them internally.

It is used to reduce coupling between components, improve testability, and make code easier to maintain. Dependencies such as database clients, configuration objects, or external services are passed as parameters or through constructors.

Dependency injection — это паттерн проектирования, при котором класс или функция получает зависимости извне, а не создаёт их внутри.

Он используется для уменьшения связанности компонентов, улучшения тестируемости и упрощения поддержки кода. Например, клиент базы данных, конфигурация или внешний сервис передаются в конструктор или параметры функции.

**140. How are patterns like Adapter, Strategy, and Factory implemented in Python?**

---

Adapter wraps an existing class to match a required interface. You implement it as a thin wrapper that translates method names/arguments and delegates to the adaptee.

Strategy defines a family of interchangeable behaviors. In Python it’s often implemented by passing a callable (function) or an object implementing a common protocol, then selecting/swapping it at runtime.

Factory centralizes object creation. In Python it’s commonly a function or classmethod that chooses which class to instantiate based on config/type and returns the created object.

Adapter оборачивает существующий класс, чтобы привести его к нужному интерфейсу. В Python это тонкая обёртка, которая преобразует методы/аргументы и делегирует вызовы “адаптируемому” объекту.

Strategy задаёт набор взаимозаменяемых алгоритмов. В Python чаще всего это передача callable (функции) или объекта с общим протоколом, с возможностью выбирать/менять стратегию во время выполнения.

Factory централизует создание объектов. В Python обычно это функция или @classmethod, которая выбирает класс по настройкам/типу и возвращает созданный объект.

**141. What is the difference between composition and inheritance?**

---

Inheritance means a class derives from another class and reuses or extends its behavior. It represents an “is-a” relationship (for example, Dog is an Animal).
Composition means a class contains other objects and delegates work to them. It represents a “has-a” relationship (for example, Car has an Engine).
Inheritance is useful when there is a clear hierarchical relationship. Composition is usually preferred because it provides more flexibility and reduces tight coupling.

Наследование означает, что класс создаётся на основе другого класса и наследует или расширяет его поведение. Это отношение типа “является” (например, Dog является Animal).
Композиция означает, что класс содержит другие объекты и использует их для выполнения задач. Это отношение типа “имеет” (например, Car имеет Engine).
Наследование полезно при чёткой иерархии. Композиция чаще предпочтительнее, потому что она более гибкая и уменьшает жёсткую связанность.

**142. What is EAFP vs LBYL in Python and when should each approach be used?**

---

EAFP (“Easier to Ask Forgiveness than Permission”) means you try the operation and handle exceptions if it fails. It’s common in Python and works well in concurrent code where state can change between a check and an action.
LBYL (“Look Before You Leap”) means you check conditions before doing the operation (e.g., if key in d:). It’s useful when exceptions are expensive/too frequent, or when you want clearer control flow for expected cases.

EAFP (“проще попросить прощения, чем разрешения”) — это подход: сначала выполнить операцию, а если она не удалась — обработать исключение. Он типичен для Python и особенно хорош в конкурентном коде, где состояние может измениться между проверкой и действием.
LBYL (“сначала посмотри, потом прыгай”) — это подход: сначала проверить условие, потом выполнить действие (например if key in d:). Он полезен, когда ошибки ожидаемы и часты (исключения будут слишком дорогими), или когда нужен более явный контроль потока выполнения.
