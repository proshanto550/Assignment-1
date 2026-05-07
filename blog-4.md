# How do the four pillars of OOP—Inheritance, Polymorphism, Abstraction, and Encapsulation—help manage logic and reduce complexity in large-scale TypeScript projects?

## Introduction
Object-Oriented Programming (OOP) is an important programming approach used in large software projects. TypeScript supports OOP concepts that help developers organize code, reduce complexity, and improve maintainability.

The four main pillars of OOP are:

- Inheritance
- Polymorphism
- Abstraction
- Encapsulation

---

## Inheritance
Inheritance allows one class to reuse properties and methods from another class.

```typescript
class Person {
    constructor(public name: string) {}
}

class Student extends Person {
    constructor(name: string, public grade: string) {
        super(name);
    }
}
```

Here, the `Student` class inherits from the `Person` class. This reduces duplicate code and improves reusability.

---

## Polymorphism
Polymorphism allows the same method to behave differently in different classes.

```typescript
class Animal {
    makeSound(): void {
        console.log("Animal sound");
    }
}

class Dog extends Animal {
    makeSound(): void {
        console.log("Bark");
    }
}
```

This makes applications more flexible and scalable.

---

## Abstraction
Abstraction hides unnecessary details and focuses only on important features.

```typescript
abstract class Vehicle {
    abstract start(): void;
}
```

Here, the implementation details are hidden, and only the required structure is shown.

---

## Encapsulation
Encapsulation protects data by restricting direct access.

```typescript
class BankAccount {
    private balance: number = 0;

    deposit(amount: number) {
        this.balance += amount;
    }
}
```

The `balance` cannot be modified directly from outside the class.

---

## Benefits in Large Projects
The four pillars of OOP help developers:

- Reduce code complexity
- Improve code organization
- Increase security
- Reuse existing logic
- Maintain large applications more easily

---

## Conclusion
The four pillars of OOP help developers build clean, organized, and scalable TypeScript applications. By using Inheritance, Polymorphism, Abstraction, and Encapsulation, large projects become easier to manage and maintain.
