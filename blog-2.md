# How do `Pick` and `Omit` utility types prevent code duplication while creating specialized "slices" of a master interface? Discuss how this keeps your code DRY (Don't Repeat Yourself).

## Introduction
In large TypeScript applications, developers often need different versions of the same interface. Writing multiple similar interfaces again and again creates duplicate code and makes maintenance difficult.

TypeScript provides utility types like `Pick` and `Omit` to solve this problem. These utility types help create smaller and specialized versions of a main interface while keeping the code DRY (Don't Repeat Yourself).

---

## Understanding the Problem
Suppose we have a main interface:

```typescript
interface User {
    id: number;
    name: string;
    email: string;
    password: string;
}
```

Now imagine we want a version of the user object without the password field for public display.

Without utility types, we may write another interface manually:

```typescript
interface PublicUser {
    id: number;
    name: string;
    email: string;
}
```

This creates repeated code.

---

## Using `Pick`
The `Pick` utility type allows us to select specific properties from an existing interface.

```typescript
interface User {
    id: number;
    name: string;
    email: string;
    password: string;
}

type PublicUser = Pick<User, "id" | "name" | "email">;
```

Here, `PublicUser` contains only the selected properties from `User`.

---

## Using `Omit`
The `Omit` utility type creates a new type by removing specific properties.

```typescript
type SafeUser = Omit<User, "password">;
```

This creates a new type containing everything except the `password` field.

---

## How This Keeps Code DRY
DRY means "Don't Repeat Yourself."

`Pick` and `Omit` help maintain DRY principles because:

- Less repeated code
- Easier maintenance
- Better consistency
- Faster updates

For example, if we later add a new property to the `User` interface, related types can update automatically without rewriting everything.

---

## Real-Life Example

```typescript
interface Product {
    id: number;
    name: string;
    price: number;
    description: string;
}

type ProductPreview = Pick<Product, "id" | "name" | "price">;
```

This is useful when showing product cards in an e-commerce website.

---

## Conclusion
`Pick` and `Omit` are powerful TypeScript utility types that reduce duplication and improve maintainability. They help developers create specialized versions of interfaces without rewriting code repeatedly.

As a result, applications become cleaner, easier to manage, and more scalable.

---
