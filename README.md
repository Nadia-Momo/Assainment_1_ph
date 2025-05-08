## 🆚 Interfaces vs Types in TypeScript

Here's a quick comparison to help you decide when to use `interface` or `type`!

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

type Dog = {
  name: string;
  barks: boolean;
} | { sleeps: boolean }; // a sleepy dog!

