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


 
