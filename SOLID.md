## SOLID

**1. What does SOLID stand for in object-oriented design?**

SOLID stands for Single Responsibility Principle, Open/Closed Principle, Liskov Substitution Principle, Interface Segregation Principle, and Dependency Inversion Principle.

SOLID — это Принцип единственной ответственности, Принцип открытости/закрытости, Принцип подстановки Лисков, Принцип разделения интерфейсов и Принцип инверсии зависимостей.

**2. Why is it important to utilise the SOLID design principles?**

It is important to use SOLID principles because they make code more maintainable, scalable, flexible, and easier to test.

They reduce coupling, improve readability, and help prevent bugs when the system grows.

Важно использовать принципы SOLID, потому что они делают код более поддерживаемым, масштабируемым, гибким и удобным для тестирования.

Они уменьшают связанность, улучшают читаемость и помогают избегать ошибок при росте системы.

**3. What is the single responsibility principle?**

The Single Responsibility Principle states that a class should have only one reason to change, meaning it should have only one responsibility or job.

Принцип единственной ответственности гласит, что у класса должна быть только одна причина для изменения, то есть он должен выполнять только одну ответственность или задачу.

**4. What is the open close principle?**

The Open/Closed Principle states that software entities should be open for extension but closed for modification. This means you can add new functionality without changing existing code.

Принцип открытости/закрытости гласит, что программные сущности должны быть открыты для расширения, но закрыты для изменения. Это означает, что новую функциональность можно добавлять без изменения существующего кода.

**5. What is the Liskov substitution principle?**

The Liskov Substitution Principle states that objects of a subclass should be replaceable with objects of the superclass without breaking the program’s behavior.

Принцип подстановки Лисков гласит, что объекты подкласса должны быть взаимозаменяемы с объектами базового класса без нарушения корректной работы программы.

**6. What is the interface segregation principle?**

The Interface Segregation Principle states that clients should not be forced to depend on interfaces they do not use. It is better to have many small, specific interfaces than one large, general-purpose interface.

Принцип разделения интерфейсов гласит, что клиенты не должны зависеть от интерфейсов, которые они не используют. Лучше иметь несколько небольших специализированных интерфейсов, чем один большой универсальный интерфейс.

**7. What is the dependency inversion principle?**

The Dependency Inversion Principle states that high-level modules should not depend on low-level modules. Both should depend on abstractions. Abstractions should not depend on details; details should depend on abstractions.

Принцип инверсии зависимостей гласит, что высокоуровневые модули не должны зависеть от низкоуровневых. И те и другие должны зависеть от абстракций. Абстракции не должны зависеть от деталей, детали должны зависеть от абстракций.

**8. How does the Single Responsibility Principle (SRP) improve code maintainability?**
The Single Responsibility Principle improves maintainability by ensuring that each class has only one responsibility. This makes the code easier to understand, modify, test, and debug because changes affect only one specific part of the system.

Принцип единственной ответственности улучшает поддерживаемость кода, поскольку каждый класс отвечает только за одну задачу. Это делает код более понятным, упрощает изменения, тестирование и отладку, так как изменения затрагивают только одну конкретную часть системы.

**9. Why is it important for classes to adhere to the Open/Closed Principle (OCP)?**

It is important because it allows the system to be extended with new functionality without modifying existing code. This reduces the risk of breaking working features, improves stability, and makes the codebase easier to maintain and scale.

Это важно, потому что позволяет расширять систему новой функциональностью без изменения существующего кода. Это снижает риск поломки уже работающих функций, повышает стабильность и упрощает поддержку и масштабирование проекта.

**10. How would you refactor a class to follow the Liskov Substitution Principle?**

To refactor for the Liskov Substitution Principle, make sure every subclass can be used wherever the base class is expected without changing correct behavior. Remove or redesign subclasses that weaken preconditions, strengthen postconditions, throw unexpected exceptions, or break invariants. If a subtype doesn’t truly fit the base type, split the hierarchy, introduce a better abstraction/interface, or use composition instead of inheritance.

Чтобы привести класс к принципу подстановки Лисков, нужно гарантировать, что любой подкласс можно использовать там, где ожидается базовый класс, не ломая корректное поведение. Уберите или переработайте подклассы, которые ослабляют обещания базового типа: усиливают предусловия, ослабляют постусловия, бросают неожиданные исключения или нарушают инварианты. Если подтип не является “настоящим” подтипом, разделите иерархию, введите более подходящую абстракцию/интерфейс или используйте композицию вместо наследования.

**11. Can you give an example of a class violating the Interface Segregation Principle (ISP)?**

An example of violating the Interface Segregation Principle is a large interface like Worker with methods work(), eat(), and sleep(). If a Robot class implements this interface but does not need eat() or sleep(), it is forced to implement unnecessary methods. This means the interface is too broad and should be split into smaller, specific interfaces.

Пример нарушения принципа разделения интерфейсов — это большой интерфейс Worker с методами work(), eat() и sleep(). Если класс Robot реализует этот интерфейс, но ему не нужны методы eat() или sleep(), он вынужден реализовывать лишние методы. Это означает, что интерфейс слишком общий и его нужно разделить на более узкие специализированные интерфейсы.

**12. What is an example of Dependency Inversion in practice?**

An example of Dependency Inversion in practice is when a high-level class like OrderService depends on an abstraction such as PaymentProcessor instead of a concrete class like StripePaymentProcessor. The specific implementation is injected (for example, through the constructor), so the service works with any payment provider without changing its code.

Пример инверсии зависимостей на практике — когда высокоуровневый класс OrderService зависит от абстракции, например PaymentProcessor, а не от конкретной реализации вроде StripePaymentProcessor. Конкретная реализация передается (например, через конструктор), поэтому сервис может работать с любым платежным провайдером без изменения своего кода.

**13. How would you refactor a class to follow the Single Responsibility Principle (SRP)?**

To refactor a class to follow SRP, identify the different responsibilities it has and split them into separate classes/modules. Move unrelated logic (for example, persistence, formatting, validation, logging, or external API calls) into dedicated components, then compose them so each class has one clear reason to change.

Чтобы привести класс к SRP, нужно найти разные ответственности, которые он выполняет, и разделить их на отдельные классы/модули. Вынесите несвязанную логику (например, сохранение в БД, форматирование, валидацию, логирование или вызовы внешних API) в отдельные компоненты и свяжите их через композицию, чтобы у каждого класса была одна понятная причина для изменения.

**14. How does SOLID help with code reusability?**

SOLID improves code reusability by promoting low coupling and high cohesion. Small, focused classes (SRP) are easier to reuse, abstractions (DIP) allow components to work with different implementations, and OCP enables extending behavior without modifying existing code. This makes components more flexible and reusable across different parts of the system.

SOLID повышает переиспользуемость кода, продвигая низкую связанность и высокую связность. Небольшие специализированные классы (SRP) легче переиспользовать, абстракции (DIP) позволяют работать с разными реализациями, а OCP дает возможность расширять поведение без изменения существующего кода. Это делает компоненты более гибкими и пригодными для повторного использования в разных частях системы.

**15. Can you give an example of the Open/Closed Principle (OCP) in a real-world application?**

A real-world example of the Open/Closed Principle is a payment system in an e-commerce application. Instead of modifying the existing checkout logic every time a new payment method is added, the system defines a PaymentMethod interface. New payment types like CreditCardPayment, PayPalPayment, or CryptoPayment implement this interface. The checkout service works with the abstraction, so new payment methods can be added without changing existing code.

Пример принципа открытости/закрытости в реальном приложении — это система оплаты в интернет-магазине. Вместо изменения логики оформления заказа при добавлении нового способа оплаты создаётся интерфейс PaymentMethod. Новые способы оплаты, такие как CreditCardPayment, PayPalPayment или CryptoPayment, реализуют этот интерфейс. Сервис оформления заказа работает с абстракцией, поэтому новые методы оплаты можно добавлять без изменения существующего кода.

---

**16. Why is Dependency Injection important for the Dependency Inversion Principle (DIP)?**

Dependency Injection is important for DIP because it allows high-level modules to depend on abstractions rather than concrete implementations. Dependencies are provided from the outside (for example, through a constructor), which reduces coupling, improves flexibility, and makes the system easier to test and maintain.

Внедрение зависимостей важно для DIP, потому что оно позволяет высокоуровневым модулям зависеть от абстракций, а не от конкретных реализаций. Зависимости передаются извне (например, через конструктор), что снижает связанность, повышает гибкость и упрощает тестирование и поддержку системы.

---

**17. What does the Interface Segregation Principle mean for a class’s design?**

The Interface Segregation Principle means that a class should implement only the methods it actually needs. Instead of large, general-purpose interfaces, the design should use smaller, focused interfaces so classes are not forced to depend on unused functionality.

Принцип разделения интерфейсов означает, что класс должен реализовывать только те методы, которые ему действительно нужны. Вместо больших универсальных интерфейсов в проектировании следует использовать небольшие специализированные интерфейсы, чтобы классы не зависели от ненужной функциональности.

---

**18. What are the benefits of applying SOLID principles in object-oriented programming?**
Applying SOLID principles improves code maintainability, scalability, flexibility, and testability. It reduces coupling, increases cohesion, makes the system easier to extend, and helps prevent bugs as the application grows.

Применение принципов SOLID повышает поддерживаемость, масштабируемость, гибкость и тестируемость кода. Оно снижает связанность, увеличивает связность, упрощает расширение системы и помогает предотвращать ошибки по мере роста приложения.
