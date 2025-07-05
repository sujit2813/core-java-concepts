
---

## 📄 File 2: `JVM_VERSIONS_FEATURES.md`  
> 📍 Location suggestion: `core-java-concepts/notes/JVM_VERSIONS_FEATURES.md`

```markdown
# 📈 JVM Evolution: Java 8 to Java 21

This document highlights how JVM internals and features have evolved across major Java versions.

---

## ✅ Java 8 (2014)

- **PermGen Removed** → Replaced with **Metaspace**
- **Lambda Expressions** → Uses `invokedynamic` in JVM
- **Stream API** → Lazy evaluation improves performance
- **Default Methods in Interfaces**
- **Nashorn JS Engine** added

🔍 JVM Insight:
- Introduced **tiered compilation**
- JVM memory management improved for metaspace auto-resizing

---

## 🚀 Java 9 (2017)

- **Project Jigsaw (Modules)** → JVM supports modular system
- **JShell (REPL)** for quick prototyping
- **Compact Strings** → Saves heap space

🔍 JVM Insight:
- Class Loader isolation improved
- JVM logs exposed via `Unified Logging Framework`

---

## ⚙️ Java 11 (2018 LTS)

- Removed `Java EE`, `CORBA` modules
- New `HttpClient` API
- **Flight Recorder & JDK Mission Control** open-sourced

🔍 JVM Insight:
- **ZGC (Z Garbage Collector)** introduced (experimental)
- Flight Recorder provides real-time JVM metrics

---

## ⚙️ Java 17 (2021 LTS)

- **Sealed Classes**
- **Pattern Matching for instanceof**
- Improved support for JVM Records

🔍 JVM Insight:
- **Improved JIT compilation**
- Better GC logging and tuning
- **Enhanced switch** in bytecode generation

---

## 🔥 Java 21 (2023 LTS)

- **Virtual Threads** (Project Loom) → Lightweight, OS-thread-independent threads
- **String Templates**
- **Record Patterns**
- Improved GC (ZGC, G1)
- Performance optimizations in **JIT and GC tuning**

🔍 JVM Insight:
- **Scalable JVM threading model**
- Massive improvements in **parallelism** and **memory footprint**

---

## 📝 Summary Table

| Version | Key JVM Feature                         |
|---------|------------------------------------------|
| Java 8  | Metaspace, Lambda, Tiered Compilation    |
| Java 9  | Modules, Compact Strings, Logging        |
| Java 11 | ZGC, Flight Recorder, Removed EE         |
| Java 17 | Sealed Classes, Pattern Matching         |
| Java 21 | Virtual Threads, Record Patterns         |

---

## 📚 References

- [OpenJDK Features](https://openjdk.org/)
- [JVM Internals Explained - Baeldung](https://www.baeldung.com/jvm)
- [Java Versions Summary - Azul](https://www.azul.com/jdk-versions/)

