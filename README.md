# Computer Science Project — JavaScript Runtime + Compiler (C++)

A compact, educational implementation of a JavaScript-like runtime and compiler written in C++. Designed as a public project for a computer science course to demonstrate language implementation concepts: lexing, parsing, bytecode interpretation, simple JIT ideas, and garbage collection strategies.

## Table of Contents

- [Overview](#overview)
- [Goals](#goals)
- [Progress tracker](#progress-tracker)
- [Architecture](#architecture)
- [Getting started](#getting-started)
- [Usage](#usage)
- [Testing](#testing)
- [Roadmap & Stretch goals](#roadmap--stretch-goals)
- [Contributing](#contributing)
- [License](#license)

## Overview

This project implements a small subset of JavaScript features to illustrate how real language runtimes work. Focus areas:

- Lexer and parser → AST
- Bytecode compiler → simple stack-based VM
- Runtime with GC (mark-sweep)
- Optional JIT experiments (prototype)

## Goals

Short-term:

- Build a working REPL and small program runner.
- Implement core language constructs: variables, functions, control flow, closures.
- Add a bytecode interpreter.

Medium-term:

- Implement mark-sweep GC, basic optimization passes.
- Measure simple benchmarks vs reference interpreters (educational).

Stretch:

- Basic JIT (emit x86_64 for hot functions).
- Async/event loop primitives.
- Small standard library (strings, arrays, JSON).

## Progress tracker

Milestones are tracked as tasks; checkboxes show status. Update this file as tasks are completed.

### High-level milestones

- [ ] Project skeleton, build system (CMake)
- [ ] Lexer + token stream
- [ ] Parser → AST generation
- [ ] AST-based interpreter (reference)
- [ ] Bytecode compiler
- [ ] Bytecode VM (stack-based)
- [ ] Garbage collector (mark-sweep)
- [ ] Closures & lexical scoping
- [ ] Function inlining / bytecode optimizations
- [ ] Basic profiling + JIT prototype
- [ ] REPL improvements, expression history
- [ ] Test suite & CI

### Current sprint (next 2 weeks)

- [ ] Implement root-set and allocation tracing for mark-sweep GC
- [ ] Integrate GC into VM allocation path
- [ ] Add tests for parser corner cases
- Progress: 55%

### Issues / TODO short list

- [ ] Fix recursive function stack overflow on deeply nested recursion
- [ ] Reduce bytecode instruction size for common ops
- [ ] Add serialization for bytecode modules

## Architecture

- src/
  - lexer/ — tokenization
  - parser/ — AST builder
  - compiler/ — AST → Bytecode
  - vm/ — bytecode interpreter, GC
  - runtime/ — standard library primitives
  - tools/ — benchmarks, REPL
- tests/ — unit and integration tests
- docs/ — design notes and diagrams

Design notes:

- Simple, typed bytecode for compactness.
- Stack-based VM to keep the implementation straightforward.
- GC will be a simple mark-sweep collector with explicit roots from VM frames and global objects.

## Roadmap & Stretch goals

- Improve GC performance (generational GC experiment)
- Add async/await and event loop primitives
- Build a tiny standard library and small module system
- Compare and document differences vs Duktape, QuickJS
