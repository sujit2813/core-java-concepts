# ♻️ Garbage Collection in Java – In-Depth Guide

Java provides **automatic memory management** using a process called **Garbage Collection (GC)**. The JVM automatically reclaims memory used by **objects that are no longer reachable** to prevent memory leaks and `OutOfMemoryError`.

---

## 🧠 What is Garbage Collection?

Garbage Collection is the process by which Java programs perform **automatic memory management**. The JVM removes objects that are **no longer used** to free up heap space.

---

## 🗃️ JVM Memory Areas (Relevant to GC)

| Memory Area      | Description                               |
|------------------|-------------------------------------------|
| **Heap**         | Main area where objects are stored        |
| **Young Generation** | Where new objects are created         |
| **Old Generation**   | Where long-lived objects are moved    |
| **Metaspace** (Java 8+) | Stores class metadata             |

---

## 🚀 GC Lifecycle: Generational Collection

### 🔹 1. **Young Generation (Eden + Survivor S0/S1)**
- New objects are created in **Eden**.
- **Minor GC** occurs frequently in this space.
- Objects that survive a few GCs move to **Old Generation**.

### 🔹 2. **Old Generation**
- Holds long-lived objects.
- **Major GC** (or Full GC) happens less frequently but takes more time.
  
### 🔹 3. **Metaspace (Java 8 onwards)**
- Replaces **PermGen**.
- Grows dynamically based on class metadata usage.

---

## 🧪 GC Process Steps

1. **Mark** – Identify which objects are in use.
2. **Sweep** – Remove unreferenced objects.
3. **Compact** – Rearrange memory to avoid fragmentation (mostly for old gen).
4. **Copy** – Move surviving objects from Eden to Survivor spaces.

---

## 🧰 Common Garbage Collectors (GC Algorithms)

| GC Name         | Description                                       | Best For                          |
|------------------|---------------------------------------------------|-----------------------------------|
| **Serial GC**     | Single-threaded, stop-the-world                  | Small apps or single-core systems |
| **Parallel GC**   | Multi-threaded, default in many versions         | High-throughput systems           |
| **CMS (Concurrent Mark-Sweep)** | Low pause time, deprecated in Java 14 | Apps needing low latency          |
| **G1 GC (Garbage First)** | Region-based, predictable pause times     | Balanced latency/performance      |
| **ZGC** (Java 11+) | Scalable, low-latency, sub-millisecond pauses  | Large heap apps                   |
| **Shenandoah** (Java 12+) | Pauses concurrent with app threads        | Low latency and large memory      |

---

## ⚙️ JVM GC Tuning Options

| Option | Description |
|--------|-------------|
| `-Xms<size>` | Initial heap size |
| `-Xmx<size>` | Maximum heap size |
| `-XX:+UseG1GC` | Use G1 Garbage Collector |
| `-XX:+PrintGCDetails` | Print GC logs |
| `-XX:MaxMetaspaceSize` | Limit metaspace size |

Example:
```bash
java -Xms512m -Xmx1024m -XX:+UseG1GC -XX:+PrintGCDetails MyApp


**Summary Table**
Concept	Details
Minor GC	Cleans Young Gen
Major (Full) GC	Cleans Old Gen + Young Gen
Compacting	Rearranging memory
Promotion	Moving long-lived objects to Old Gen
Tuning	Via -Xms, -Xmx, and GC flags
