# Java Virtual Machine (JVM) Subsystems Overview

The Java Virtual Machine (JVM) is a crucial part of the Java runtime environment. It consists of multiple subsystems responsible for managing and executing Java applications. Below is a breakdown of the four major subsystems:

## 1. Class Loader Subsystem
   The **Class Loader** subsystem is responsible for loading `.class` files at runtime. The class loader works in three phases:
   - **Verification**: Ensures the bytecode is valid and does not violate security constraints.
   - **Preparation**: Allocates memory for static fields.
   - **Resolution**: Converts symbolic references into actual memory addresses.

   The class loader follows a delegation model and consists of three main types:
   - **Bootstrap**: Loads core Java classes.
   - **Extension**: Loads classes from the Java Extensions library.
   - **Application**: Loads application-specific classes.

## 2. Runtime Data Areas
   The JVM memory is divided into shared and thread-specific areas:
   - **Shared**:
     - **Heap**: Stores all objects and arrays, managed by the Garbage Collector (GC). It is further divided into the Young and Old generations.
     - **Method Area/Metaspace**: Holds class metadata, static variables, and constant pools.
   - **Per-Thread**:
     - **JVM Stack**: Stores local variables, method calls, and operand stacks.
     - **Program Counter (PC) Register**: Points to the current instruction being executed.
     - **Native Method Stack**: Used for calls to native methods (e.g., C/C++ through JNI).

## 3. Execution Engine
   The **Execution Engine** is responsible for turning bytecode into machine-level instructions:
   - **Interpreter**: Executes bytecode one instruction at a time, ideal for quick startup but slower execution.
   - **JIT (Just-In-Time) Compiler**: Compiles "hot" code paths (frequently executed code) into optimized native machine code for better performance. It has two stages:
     - **C1 Compiler**: Focuses on fast compilation.
     - **C2 Compiler**: Performs more aggressive optimizations.
   - **Garbage Collector**: Reclaims heap memory, with modern GC strategies (e.g., G1 and ZGC) designed to minimize pause times.

## 4. Native Interface Layer (JNI)
   The **Java Native Interface (JNI)** allows Java code to interact with platform-specific native libraries. JNI is used extensively by the JVM for I/O operations, networking, and other low-level system functions. It enables seamless interaction between Java and C/C++ code, ensuring that Java can access and manipulate system resources as needed.

   # Java Virtual Machine (JVM) Subsystems

![JVM Internal Architecture](https://raw.githubusercontent.com/swap72/Java/refs/heads/main/JVM%20Internal%20Architecture/jvm_internal_architecture.svg)

## The Java Virtual Machine (JVM) is a crucial part of the Java runtime environment. It consists of multiple subsystems responsible for managing and executing Java applications.

---
