# How do Generics allow you to build reusable components and functions that stay strictly typed regardless of the data structures passed in?

## Introduction
Generics are one of the most useful features in TypeScript. They allow developers to write reusable code while still keeping strong type safety.

Without generics, developers often need to write the same logic multiple times for different data types.

---

## The Problem Without Generics
Consider the following example:

```typescript
function getString(value: string): string {
    return value;
}

function getNumber(value: number): number {
    return value;
}
```

The logic is exactly the same, but separate functions are written for different types.

---

## Using Generics
Generics solve this problem by making the type flexible.

```typescript
function identity<T>(value: T): T {
    return value;
}
```

Now the same function works with different data types.

```typescript
console.log(identity<string>("Hello"));
console.log(identity<number>(100));
```

---

## Type Safety with Generics
Even though generics are flexible, TypeScript still checks types properly.

```typescript
identity<string>(123);
```

The code above will produce an error because `123` is not a string.

This ensures type safety while keeping the function reusable.

---

## Generics with Interfaces
Generics can also be used with interfaces.

```typescript
interface ApiResponse<T> {
    success: boolean;
    data: T;
}
```

Example:

```typescript
const userResponse: ApiResponse<string> = {
    success: true,
    data: "John"
};
```

This allows the same interface to work with different data types.

---

## Benefits of Generics
Generics provide many advantages:

- Reusable code
- Better type safety
- Cleaner project structure
- Reduced code duplication

They are commonly used in APIs, React components, utility functions, and data structures.

---

## Conclusion
Generics make TypeScript applications more flexible and reusable without sacrificing type safety. They reduce repeated code and help developers build scalable and maintainable applications more efficiently.

---
