# JavaScript Async/Await Concurrency Patterns

> A practical case study demonstrating how asynchronous programming works in JavaScript using async/await, Promises and the Fetch API.

![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-yellow?style=for-the-badge&logo=javascript)
![Async](https://img.shields.io/badge/Pattern-Async%2FAwait-purple?style=for-the-badge)
![Concurrency](https://img.shields.io/badge/Concept-Concurrency-blue?style=for-the-badge)
![Fetch](https://img.shields.io/badge/API-Fetch-green?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Case%20Study-black?style=for-the-badge)

---

## Overview

Async/Await is a fundamental concept in modern JavaScript.

It allows developers to handle asynchronous operations in a way that looks synchronous, improving:

- Readability
- Maintainability
- Error handling

---

## The Problem

Traditional async code using callbacks leads to:

```text
Callback hell
Complex nesting
Hard-to-read logic
Difficult error handling
```

Promises improve this, but can still be verbose.

Async/Await simplifies everything.

## How JavaScript Handles Async

JavaScript is single-threaded but uses an event-driven model.
```text
Call Stack
   ↓
Web APIs
   ↓
Callback Queue
   ↓
Event Loop
```

## Async/Await Flow
```text
async function → returns Promise
await → pauses execution until resolved
```

## Example: Fetch Data
```js
async function carregarDados() {
  const response = await fetch("https://reqres.in/api/users");
  const data = await response.json();

  console.log(data);
}
```

## With Error Handling
```js
async function carregarDados() {
  try {
    const response = await fetch("https://reqres.in/api/users");

    if (!response.ok) {
      throw new Error("Erro na requisição");
    }

    const data = await response.json();

    console.log(data);

  } catch (error) {
    console.error(error);
  }
}
```

## Without Async/Await (Promise Chain)
```js
fetch("https://reqres.in/api/users")
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error(error));
```

## Architecture Insight
```text
Async/Await = orchestration layer
Fetch = transport layer
Promise = execution model
```

## Sequential vs Parallel Execution
Sequential
```js
await fetch(url1);
await fetch(url2);
```

## Parallel
```js
await Promise.all([
  fetch(url1),
  fetch(url2)
]);
```

## Real Engineering Use Cases
```text
API calls
Database queries
File processing
Event-driven systems
Microservices communication
```

## Performance Considerations
```text
Avoid blocking async flows
Use parallel execution when possible
Handle errors properly
Avoid unnecessary awaits
```

## Common Mistakes

❌ Forgetting await
❌ Not handling errors
❌ Sequential calls when parallel is better
❌ Mixing callbacks with async/await
❌ Ignoring Promise rejections

## Advanced Topics

```text
Event loop internals
Microtasks vs macrotasks
Promise chaining
Concurrency control
Async pipelines
```

## Demo
## Layout Async/Await

[![Assista ao vídeo do Async/Await](https://github.com/Thiago771414/imagensProjetos/blob/main/slices/mobile/asyncAwait.png)](https://youtu.be/eSJSFngyir4)

*Clique na imagem acima para assistir à demonstração.*

---

## Summary

Async/Await is not just syntax.

It is the foundation of modern JavaScript concurrency.

```text
Async = non-blocking execution
Await = control flow
Promise = underlying engine
```

## Author

Thiago Lima
Software Engineer | System Design | Async Architecture

