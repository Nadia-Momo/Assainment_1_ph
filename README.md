## What are some differences between interfaces and types in typescript?

      `Interface` 🆚`Type`

| Feature | `interface` | `type` |
|--------|-------------|--------|
| 🧬 **Extending** | ✅ via `extends` | ✅ via `&` (intersection) |
| 🧩 **Declaration Merging** | ✅ Yes | ❌ No |
| 🧪 **Primitives/Unions** | ❌ No | ✅ Yes |
| 🏗️ **Class `implements`** | ✅ Yes | ✅ Yes |
| 🎯 **Best Use Case** | Object/class shape | Unions, primitives, complex types |

---

### 🎀 When to Use What?

- Use **`interface`** when describing the shape of an object or a class.
- Use **`type`** for more complex structures (e.g., unions, primitives, tuples).

---

### Cute Example:

```ts
interface Cat {
  name: string;
  purrs: boolean;
}
![Cute Cat](https://example.com/path-to-cat.jpg)

type Dog = {
  name: string;
  barks: boolean;
} | { sleeps: boolean }; // a sleepy dog!


# ðŸ§¸ Understanding the `keyof` Keyword in TypeScript

![Cute Cat](https://images.unsplash.com/photo-1601758123927-196d5f5f1c4b?auto=format&fit=crop&w=800&q=60)

## ðŸ§  What is `keyof`?

The `keyof` keyword in TypeScript is a **type operator** used to obtain the union of keys from a given object type. It's particularly useful for creating **generic** and **type-safe** code when working with dynamic object properties.

## ðŸŽ¯ Why Use `keyof`?

Using `keyof` allows you to:

- Access keys of a type as a union of string or number literals.
- Create generic types or utility functions that are constrained to valid property names.
- Safely reference object keys and values in a type-safe way.

## ðŸ’¡ Example

```ts
// Define an object type
type Person = {
  name: string;
  age: number;
  isStudent: boolean;
};

// Use keyof to get a union of keys
type PersonKeys = keyof Person; // "name" | "age" | "isStudent"

// A function that only accepts valid Person keys
function getProperty<T, K extends keyof T>(obj: T, key: K): T[K] {
  return obj[key];
}

const person: Person = {
  name: "Alice",
  age: 25,
  isStudent: false,
};

// Valid usage
const name = getProperty(person, "name"); // string
const age = getProperty(person, "age");   // number

// Invalid usage (TypeScript will show an error)
// const invalid = getProperty(person, "height");
```

![Cute Dog](https://images.unsplash.com/photo-1560807707-8cc77767d783?auto=format&fit=crop&w=800&q=60)

## ðŸ“ Summary

- `keyof` creates a union of keys from a type.
- It's essential for working with generic and dynamic object properties.
- It enhances type safety by preventing access to non-existent properties.

---

**Use `keyof` to write smarter, safer TypeScript code!**

![Cute Bunny](https://images.unsplash.com/photo-1546182990-dffeafbe841d?auto=format&fit=crop&w=800&q=60)

---

*Images sourced from [Unsplash](https://unsplash.com/s/photos/cute) and are free for commercial use.*
