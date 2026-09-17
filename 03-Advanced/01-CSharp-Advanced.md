# 01 — C# Advanced

## 🎯 Learning Objectives
Understand the language and runtime at a level that lets you diagnose performance issues, write high-performance code, and understand what's happening "under the hood."

## 📚 Topics & Subtopics

### Advanced Type System
- [ ] Reflection — inspecting types/members at runtime, use cases and costs
- [ ] Attributes — building custom attributes, reading them via reflection
- [ ] Source Generators — compile-time code generation (why they're faster than reflection)
- [ ] Expression Trees — building and compiling expressions dynamically (used heavily by EF Core/LINQ providers)
- [ ] Dynamic typing (`dynamic`) — when it's justified (interop) and when it's a smell

### Memory & Performance
- [ ] Value types vs reference types in memory, struct layout, `readonly struct`
- [ ] `Span<T>`, `Memory<T>`, `stackalloc` — avoiding allocations in hot paths
- [ ] Garbage Collection deep dive: generations, Server GC vs Workstation GC, GC modes for ASP.NET Core
- [ ] Object pooling (`ObjectPool<T>` from `Microsoft.Extensions.ObjectPool`)
- [ ] `ArrayPool<T>` for buffer reuse
- [ ] Boxing/unboxing performance impact, avoiding unnecessary allocations in loops/LINQ

### Concurrency & Parallelism
- [ ] Threads vs Tasks vs the Thread Pool
- [ ] `Parallel.For`/`Parallel.ForEach`, PLINQ
- [ ] `System.Threading.Channels` for producer/consumer pipelines
- [ ] Synchronization primitives: `lock`, `SemaphoreSlim`, `Mutex`, `ReaderWriterLockSlim`
- [ ] Race conditions, deadlocks — recognizing and avoiding them
- [ ] `Interlocked` for lock-free counters
- [ ] `async`/`await` internals — the state machine, `SynchronizationContext`

### Diagnostics & Profiling
- [ ] `dotnet-trace`, `dotnet-counters`, `dotnet-dump`
- [ ] BenchmarkDotNet for micro-benchmarking
- [ ] Reading a memory dump / identifying memory leaks

## 🧪 Hands-on Practice
- Use BenchmarkDotNet to compare `List<T>.Where().ToList()` vs a hand-written loop vs `Span<T>`-based processing for a large TaskFlow dataset
- Build a producer/consumer pipeline with `System.Threading.Channels` that processes incoming task notifications asynchronously
- Deliberately introduce a deadlock (blocking async code) and fix it
- Profile TaskFlow under load with `dotnet-counters` and identify GC pressure

## 📖 Resources
- Microsoft Learn: *.NET Garbage Collection*
- Book: *Pro .NET Memory Management* by Konrad Kokosa
- Book: *Concurrency in C# Cookbook* by Stephen Cleary
- BenchmarkDotNet official docs

## ❓ Self-Check Questions
- Why does `Span<T>` help reduce allocations, and what are its restrictions (can't be used in async methods, etc.)?
- What's the difference between Server GC and Workstation GC, and which does ASP.NET Core use by default?
- How does `async`/`await` avoid blocking a thread, conceptually?

## ➡️ Next
[`02-AspNetCore-Advanced.md`](./02-AspNetCore-Advanced.md)
