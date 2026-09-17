# 01 — C# Fundamentals

## 🎯 Learning Objectives
Understand core C# syntax and constructs well enough to write basic console/business logic confidently.

## 📚 Topics & Subtopics

### Language Basics
- [ ] .NET vs .NET Framework vs .NET Core vs Mono — history & unification
- [ ] CLR, IL, JIT compilation — how C# code runs
- [ ] Variables, data types (value vs reference types), `var` vs explicit typing
- [ ] Operators, type conversion, boxing/unboxing
- [ ] Control flow: `if/else`, `switch`/`switch expressions`, loops (`for`, `foreach`, `while`, `do-while`)
- [ ] Arrays, `List<T>`, basic collections overview

### Object-Oriented Programming
- [ ] Classes vs structs vs records
- [ ] Fields, properties (auto-properties, init-only, expression-bodied)
- [ ] Constructors, static members, constants vs readonly
- [ ] Encapsulation, inheritance, polymorphism, abstraction
- [ ] Interfaces vs abstract classes
- [ ] `sealed`, `virtual`, `override`, `new` keyword shadowing
- [ ] Access modifiers (`public`, `private`, `protected`, `internal`, `protected internal`, `private protected`)

### Methods & Functions
- [ ] Method overloading, optional/named parameters
- [ ] `ref`, `out`, `in` parameters
- [ ] Params arrays
- [ ] Local functions vs lambda expressions
- [ ] Extension methods

### Error Handling Basics
- [ ] `try/catch/finally`
- [ ] Throwing and creating custom exceptions (intro — deep dive later)
- [ ] `using` statement / `IDisposable` basics

### Collections & LINQ Basics
- [ ] `List<T>`, `Dictionary<TKey,TValue>`, `HashSet<T>`, `Queue<T>`, `Stack<T>`
- [ ] `IEnumerable<T>` vs `ICollection<T>` vs `IList<T>`
- [ ] Basic LINQ: `Where`, `Select`, `OrderBy`, `FirstOrDefault`, `Any`, `Count`

### Nullability & Modern C#
- [ ] Nullable reference types (`string?`), null-conditional (`?.`), null-coalescing (`??`, `??=`)
- [ ] Pattern matching basics (`is`, `switch` patterns)
- [ ] String interpolation, verbatim/raw strings

## 🧪 Hands-on Practice
Build a **console-based Task Manager**:
- Model a `TaskItem` class (Id, Title, Priority enum, IsDone, DueDate)
- Store tasks in a `List<TaskItem>`
- Implement Add/Complete/Delete/List operations via a menu loop
- Use LINQ to filter overdue or high-priority tasks
- Add basic try/catch around user input parsing

## 📖 Resources
- Microsoft Learn: *C# documentation* — https://learn.microsoft.com/dotnet/csharp/
- Microsoft Learn: *Tour of C#*
- Book: *C# in Depth* by Jon Skeet (reference for deeper understanding)
- Book: *C# 12 in a Nutshell* by Joseph Albahari

## ❓ Self-Check Questions
- What's the difference between a `struct` and a `class`?
- When would you use `readonly` vs `const`?
- What does covariance/contravariance mean at a beginner level (interfaces with `out`/`in`)?
- Why are nullable reference types useful?

## ➡️ Next
[`02-DotNet-Basics.md`](./02-DotNet-Basics.md)
