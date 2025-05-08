# What are some differences between interfaces and types in typescript?

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
### 😦 Example 💘

<pre> ``` interface User { name: string; age: number; } 
      
     type User={name: string; age: number;}``` </pre>

# 🐻🐤What is the use of the keyof keyword in Typescript?Provide an example.🐥🐼 Understanding `keyof` in TypeScript! 🐻✨

Welcome to the adorable guide on the `keyof` keyword in TypeScript! 🐨💖

---

## What is `keyof`? 🤔

`keyof` helps you get a **union type** of all the property names of an object. It's like a magical string list of all keys! 🌟

![Cute Pookie 1](https://images.unsplash.com/photo-1592194996308-7b43878e84a6?ixlib=rb-4.0.1&auto=format&fit=crop&w=800&q=60)  
*Imagine a cute pookie saying: "Show me the keys!"* 🐶

---
## 🐶 Summary
>🐻keyof creates a union of object keys.
>🐻Helps you write safer and more flexible TypeScript code.
>🐻Perfect for functions that work with object properties! 🎈
>🐻Access object properties
>🐻Build reusable ggeneric functions
>🐻Avoid hardcoded property names
>💥Pookie's tip: Use keyof to prevent typos! 

![Unlocking Keys](https://media.giphy.com/media/3o7aD2saalBwwftBIY/giphy.gif)
>Happy coding with adorable pookies! 🐼💕
## Example Usage 🎉

```typescript
interface Person {
  name: string;
  age: number;
  location: string;
}

function getProperty<T, K extends keyof T>(obj: T, key: K): T[K] {
  return obj[key];
}

const person: Person = { name: "Nadia", age: 30, location: "Switzerland" };

const name = getProperty(person, "name"); // string
const age = getProperty(person, "age");   // number






