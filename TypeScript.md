## TypeScripts

**1. What is TypeScript and how does it differ from JavaScript?**
TypeScript is a statically typed superset of JavaScript developed by Microsoft.

It adds optional static typing, interfaces, generics, and compile-time type checking.

TypeScript code is compiled to plain JavaScript before running in the browser or Node.js.

Unlike JavaScript, TypeScript helps catch type errors during development, improving reliability and maintainability.

TypeScript — это статически типизированное надмножество JavaScript, разработанное Microsoft.

Он добавляет опциональную статическую типизацию, интерфейсы, дженерики и проверку типов на этапе компиляции.

Код TypeScript компилируется в обычный JavaScript перед выполнением в браузере или Node.js.

В отличие от JavaScript, TypeScript позволяет находить ошибки типов на этапе разработки, повышая надёжность и поддержку кода.

**2. Can you explain what is meant by "TypeScript is a superset of JavaScript"?**

When we say TypeScript is a superset of JavaScript, it means that all valid JavaScript code is also valid TypeScript code.

TypeScript includes all JavaScript features and adds extra features like static typing and interfaces.

You can rename a .js file to .ts and it will usually work without changes.

After compilation, TypeScript produces standard JavaScript that runs in any JS environment.

```
let num: number = 5;
num = "this will raise a type error";
```

Когда говорят, что TypeScript — это надмножество JavaScript, это означает, что любой корректный JavaScript-код является корректным и в TypeScript.

TypeScript включает все возможности JavaScript и добавляет дополнительные функции, например статическую типизацию и интерфейсы.

Можно переименовать файл .js в .ts, и в большинстве случаев он будет работать без изменений.

После компиляции TypeScript превращается в обычный JavaScript, который выполняется в любой JS-среде.

3. What are the basic types available in TypeScript?

Basic types in TypeScript include:

string, number, boolean — primitive types.

null and undefined — represent absence of value.

any — disables type checking.

unknown — safer alternative to any.

void — used for functions that return nothing.

never — represents values that never occur.

array and tuple — for collections of values.

object — for non-primitive values.

Базовые типы в TypeScript включают:

string, number, boolean — примитивные типы.

null и undefined — отсутствие значения.

any — отключает проверку типов.

unknown — более безопасная альтернатива any.

void — для функций, которые ничего не возвращают.

never — значения, которые никогда не возникают.

array и tuple — для коллекций значений.

object — для непримитивных значений.

```
// Boolean
let isActive: boolean = true;

// Number
let age: number = 30;

// String
let title: string = "Manager";

// Array
let scores: number[] = [85, 90, 78];
// or use a compact form: let scores: Array<number> = [85, 90, 78];

// Tuple
let employee: [string, number, boolean] = ['John', 35, true];

// Enum
enum WeekDays { Monday, Tuesday, Wednesday, Thursday, Friday }
let today: WeekDays = WeekDays.Wednesday;

// Any
let dynamicData: any = 20;

// Void
function greet(): void {
  console.log("Hello!");
}

// Null and Undefined
let data: null = null;
let user: undefined = undefined;

// Never
function errorMessage(message: string): never {
  throw new Error(message);
}

// Object
let person: object = {
  name: 'John',
  age: 30
};

// Function
let calculate: Function;
calculate = function (x: number, y: number): number {
  return x + y;
```

**4. How do you declare variables in TypeScript?**

In TypeScript, variables are declared using let, const, or var, just like in JavaScript.

You can optionally add a type annotation after the variable name.

Example:

```
let age: number = 30;
```

If you don’t specify a type, TypeScript can infer it automatically.

В TypeScript переменные объявляются с помощью let, const или var, как и в JavaScript.

После имени переменной можно указать аннотацию типа.

Если тип явно не указан, TypeScript может определить его автоматически (type inference).

**5. What are Interfaces in TypeScript and how do they work?**
Interfaces in TypeScript define the structure (shape) of an object.

They specify what properties and methods an object should have and their types.

Example:

```
interface User { name: string; age: number; }
```

Any object assigned to type User must follow this structure.

Interfaces can also extend other interfaces and describe function or class contracts.

Interfaces в TypeScript определяют структуру (форму) объекта.

Они описывают, какие свойства и методы должен иметь объект и их типы.

Любой объект типа User должен соответствовать этой структуре.

Интерфейсы могут расширять другие интерфейсы и задавать контракт для функций или классов.

**6. Describe the Enum type and when you might use it.**

Enum in TypeScript is a special type that defines a set of named constant values.

It makes code more readable by giving meaningful names to numeric or string values.

Example:

```
enum Status { Pending, Approved, Rejected }
```

You use enums when you need a fixed set of related constants, like roles, statuses, or directions.

Enum в TypeScript — это специальный тип, который задаёт набор именованных констант.

Он делает код более читаемым, присваивая понятные имена числовым или строковым значениям.

Enum используют, когда нужен фиксированный набор связанных значений, например роли, статусы или направления.

**7. How do you define and use a function in TypeScript?**

In TypeScript, you define a function like in JavaScript but can add type annotations for parameters and return value.

Example:

```
function add(a: number, b: number): number { return a + b; }
```

You can also define arrow functions with types: const add = (a: number, b: number): number => a + b;

TypeScript checks that arguments and return values match the declared types.

В TypeScript функции определяются как в JavaScript, но можно добавлять аннотации типов для параметров и возвращаемого значения.

Также можно использовать стрелочные функции с типами: const add = (a: number, b: number): number => a + b;

TypeScript проверяет соответствие аргументов и возвращаемого значения объявленным типам.

**8. What does "type inference" mean in the context of TypeScript?**

Type inference means that TypeScript automatically determines the type of a variable or expression without explicit annotation.

For example, if you write let count = 10, TypeScript infers the type as number.

It analyzes assigned values, function returns, and context to deduce types.

This reduces the need for manual type annotations while still providing type safety.

Type inference — это автоматическое определение типа переменной или выражения без явной аннотации.

Например, при let count = 10 TypeScript выводит тип number.

Он анализирует присвоенные значения, возвращаемые значения функций и контекст, чтобы определить тип.

Это уменьшает количество явных аннотаций, сохраняя типобезопасность.

**9. Explain the use of 'let' and 'const' in TypeScript.**

In TypeScript, let and const work the same way as in JavaScript.

let is used for variables whose value can be reassigned.

const is used for variables that cannot be reassigned after initialization.

Both are block-scoped and support type annotations or type inference.

```
const productId: number = 5;
let productName: string = 'Tesla';

const getProductDetails = (id: number): string => {
  return `Product ID: ${id}`;
};

// Attempting to modify will result in a compilation error
// productId = 6;

// Reference is still immutable
const anotherProductId: number = 10;
// This will throw a compilation error since it's a constant
// anotherProductId = 12;

// Modifying internal state of an object is allowed for a const
const myArray: number[] = [1, 2, 3];
myArray.push(4);

let vehicleType: string = 'Car';

if (true) {
  let vehicleType: string = 'Motorcycle';
  console.log(vehicleType);  // Output: Motorcycle
}

console.log(vehicleType);  // Output: Car
```

В TypeScript let и const работают так же, как в JavaScript.

let используют для переменных, значение которых можно изменить.

const используют для переменных, которые нельзя переназначить после инициализации.

Обе имеют блочную область видимости и поддерживают аннотацию типов или автоматический вывод типа.

**10. How do you compile TypeScript files into JavaScript?**

You compile TypeScript files into JavaScript using the TypeScript compiler (tsc).

After installing TypeScript, you run tsc filename.ts to generate a .js file.

For larger projects, you use a tsconfig.json file and run tsc to compile the entire project.

The compiler converts TypeScript code into plain JavaScript that can run in the browser or Node.js.
Here is the tsconfig.json file. The full configuration guide is available here.

```

{
"compilerOptions": {
"target": "ES5",
"module": "commonjs",
"strict": true,
"outDir": "dist",
"rootDir": "src"
},
"include": [
"src/**/*.ts"
],
"exclude": [
"node_modules",
"**/*.spec.ts"
]
}

```

Файлы TypeScript компилируются в JavaScript с помощью компилятора TypeScript (tsc).

После установки TypeScript можно выполнить команду tsc filename.ts, чтобы получить .js файл.

В крупных проектах используют tsconfig.json и запускают tsc для компиляции всего проекта.

Компилятор преобразует TypeScript-код в обычный JavaScript, который выполняется в браузере или Node.js.

**11. Explain classes in TypeScript. How are they different from ES6 classes?**

Classes in TypeScript are similar to ES6 classes but add type annotations and access modifiers.

You can define typed properties, constructor parameters, and method return types.

TypeScript also supports public, private, and protected modifiers, which are not enforced in plain ES6.

Additionally, TypeScript provides features like readonly properties and parameter properties for cleaner syntax.

Классы в TypeScript похожи на ES6-классы, но добавляют аннотации типов и модификаторы доступа.

Можно указывать типы свойств, параметров конструктора и возвращаемых значений методов.

TypeScript поддерживает модификаторы public, private и protected, которых нет в чистом ES6.

Также есть дополнительные возможности, например readonly-свойства и сокращённая запись параметров конструктора.

**12. How do you implement Inheritance in TypeScript?**

Inheritance in TypeScript is implemented using the extends keyword.

A child class extends a parent class and inherits its properties and methods.

You can call the parent constructor using super() inside the child constructor.

TypeScript also enforces access modifiers (public, protected, private) in inheritance.

```

// Define the Parent Class
function Animal(this: Animal, name: string) {
this.name = name;
}

Animal.prototype.move = function(distanceInMeters: number = 0) {
console.log(`${this.name} moved ${distanceInMeters}m.`);
};

// Define the Child Class
function Snake(name: string) {
Animal.call(this, name);
}

// Set up the Inheritance
Snake.prototype = Object.create(Animal.prototype);
Snake.prototype.constructor = Snake;

// Override the Base Type's Method
Snake.prototype.move = function(distanceInMeters = 5) {
console.log("Slithering...");
Animal.prototype.move.call(this, distanceInMeters);
};

const mySnake = new Snake("Cobra");
mySnake.move(); // Output: Slithering... Cobra moved 5m.

```

Наследование в TypeScript реализуется с помощью ключевого слова extends.

Дочерний класс расширяет родительский и наследует его свойства и методы.

В конструкторе дочернего класса вызывают super() для обращения к родительскому конструктору.

TypeScript также учитывает модификаторы доступа (public, protected, private) при наследовании.

**13. What are access modifiers and how do they work in TypeScript?**

Access modifiers in TypeScript control the visibility of class members.

There are three main modifiers: public, private, and protected.

public members are accessible from anywhere.

private members are accessible only within the same class.

protected members are accessible within the class and its subclasses.

```

class Person {
public name: string;
private age: number;
protected contact: string;

    constructor(name: string, age: number, contact: string) {
        this.name = name;
        this.age = age;
        this.contact = contact;
    }

}

class Employee extends Person {
private employeeId: string;

    constructor(name: string, age: number, contact: string, employeeId: string) {
        super(name, age, contact);
        this.employeeId = employeeId;
    }

    public displayDetails(): void {
        console.log(`${this.name} - ${this.age} - ${this.contact} - ${this.employeeId}`);
    }

}

// Somewhere in your code
const person = new Person("John Doe", 30, "1234567");
console.log(person.name); // Accessible
console.log(person.age); // ERROR: 'age' is private

const employee = new Employee("Jane Doe", 25, "2345678", "E123");
console.log(employee.contact); // ERROR: 'contact' is protected
employee.displayDetails(); // Correctly displays details

employee.age = 35; // ERROR: 'age' is private
employee.contact = "3456789"; // ERROR: 'contact' is protected

```

Модификаторы доступа в TypeScript управляют видимостью членов класса.

Существует три основных модификатора: public, private и protected.

public — доступен отовсюду.

private — доступен только внутри самого класса.

protected — доступен внутри класса и его наследников.

**14. Discuss Abstract classes and their purposes in TypeScript.**

An abstract class in TypeScript is a class that cannot be instantiated directly.

It is used as a base class and may contain abstract methods without implementation.

Subclasses must implement all abstract methods defined in the abstract class.

Abstract classes help define a common structure and enforce contracts for related classes.

```

abstract class Shape {
abstract getArea(): number;
abstract getPerimeter(): number;
color: string;

    constructor(color: string) {
        this.color = color;
    }

    static defaultColor: string = 'red';

    describe() {
        return `This shape is ${this.color}.`;
    }

}

// This will throw an error because the derived class does not provide concrete implementations for abstract methods.
class Circle extends Shape {
constructor(public radius: number, color: string) {
super(color);
}

    // The 'Circle' class inherited the following properties from 'Shape', but neither implements nor specifies them in the derived class: 'getArea' and 'getPerimeter'.
    getArea(): number {
        return Math.PI * this.radius ** 2;
    }

    getPerimeter(): number {
        return 2 * Math.PI * this.radius;
    }

}

const myCircle = new Circle(5, 'blue');
console.log(myCircle.getArea()); // Outputs: 78.54
console.log(myCircle.describe()); // Outputs: This shape is blue.
console.log(Shape.defaultColor); // Outputs: red

```

Абстрактный класс в TypeScript — это класс, который нельзя создать напрямую (нельзя инстанцировать).

Он используется как базовый класс и может содержать абстрактные методы без реализации.

Дочерние классы обязаны реализовать все абстрактные методы.

Абстрактные классы помогают задать общую структуру и контракт для связанных классов.

**15. Can you describe the use of Constructors within TypeScript classes?**

A constructor in TypeScript is a special method used to initialize class properties when a new instance is created.

It runs automatically when you create an object with the new keyword.

You can define typed parameters and assign them to class fields.

TypeScript also supports parameter properties, allowing you to declare and initialize fields directly in the constructor.

```

class Person {
// Member variables
name: string;
age: number;

// Constructor
constructor(name: string, age: number) {
this.name = name;
this.age = age;
}
}

```

Конструктор в TypeScript — это специальный метод, который используется для инициализации свойств класса при создании нового экземпляра.

Он автоматически вызывается при создании объекта с помощью ключевого слова new.

В конструкторе можно указывать типизированные параметры и присваивать их полям класса.

TypeScript поддерживает сокращённую запись — parameter properties, позволяя объявлять и инициализировать поля прямо в конструкторе.

```

```
