
---

## 🧩 Core Components of JVM

### 1. **Class Loader Subsystem**
- Loads `.class` files into memory.
- Three main class loaders:
  - **Bootstrap**: Loads core Java classes (`java.lang.*`)
  - **Extension**: Loads JDK extensions (`javax.*`)
  - **Application**: Loads user-defined classes

### 2. **Runtime Data Areas**
| Memory Area       | Purpose |
|-------------------|---------|
| Method Area        | Stores class structures, method data |
| Heap               | Stores objects (shared among threads) |
| Stack              | Stores method frames (per thread) |
| PC Register        | Stores address of current executing instruction |
| Native Method Stack| Used for native (non-Java) methods |

### 3. **Execution Engine**
- **Interpreter**: Executes bytecode line-by-line
- **JIT Compiler (Just-In-Time)**: Converts bytecode to machine code for better performance
- **Garbage Collector**: Removes unused objects from heap memory

---

## ♻️ Garbage Collection Phases
- **Mark**: Identify which objects are in use
- **Sweep**: Remove unreferenced objects
- **Compact**: Rearranging memory blocks

---
