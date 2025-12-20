<h1 align="center">Node-JS Script</h1>

## Table Content

1. [What is Node.js?](#1%EF%B8%8F⃣-what-is-nodejs)
2. [How does Node.js execute JavaScript code internally?](#2%EF%B8%8F⃣-how-does-nodejs-execute-javascript-code-internally)
3. [How does Node.js handle multiple concurrent requests?](#3%EF%B8%8F⃣-how-does-nodejs-handle-multiple-concurrent-requests)
4. [What is the Event Loop in Node.js?](#4%EF%B8%8F⃣-what-is-the-event-loop-in-nodejs)
5. [Explain Event Loop phases](#5%EF%B8%8F⃣-explain-event-loop-phases)
6. [Difference between Call Stack, Callback Queue, and Microtask Queue](#6%EF%B8%8F⃣-difference-between-call-stack-callback-queue-and-microtask-queue)
7. [`setTimeout`, `setImmediate`, `process.nextTick`](#7%EF%B8%8F⃣-settimeout-setimmediate-processnexttick)
8. [What is the Node.js thread pool?](#8%EF%B8%8F⃣-what-is-the-nodejs-thread-pool)
9. [What are Streams in Node.js and their types?](#9%EF%B8%8F⃣-what-are-streams-in-nodejs-and-their-types)
10. [What is a Buffer?](#-what-is-a-buffer)
11. [Difference between Buffer and Stream](#1%EF%B8%8F⃣1%EF%B8%8F⃣-difference-between-buffer-and-stream)
12. [What is the `fs` module?](#1%EF%B8%8F⃣2%EF%B8%8F⃣-what-is-the-fs-module)
13. [What is the process object in Node.js?](#1%EF%B8%8F⃣3%EF%B8%8F⃣-what-is-the-process-object-in-nodejs)
14. [What are Environment Variables?](#1%EF%B8%8F⃣4%EF%B8%8F⃣-what-are-environment-variables)
15. [What is clustering in Node.js?](#1%EF%B8%8F⃣5%EF%B8%8F⃣-what-is-clustering-in-nodejs)
16. [Difference between Cluster and Worker Threads](#1%EF%B8%8F⃣6%EF%B8%8F⃣-difference-between-cluster-and-worker-threads)


## 1️⃣ What is Node.js?
- Node.js is a JavaScript runtime environment.
- It allows us to run JavaScript outside the browser, primarily on the server side.
- It is built on Google’s V8 engine and uses an event-driven, non-blocking I/O model.

## 2️⃣ How does Node.js execute JavaScript code internally?
- Node.js executes JavaScript code using the V8 engine.
- When we run a JavaScript file, Node.js passed it to the V8 engine which compile JavaScript code into machine code and executes it.
- Synchronous code is executed in the call stack.
- Asynchronous code is handle by libuv that manage event loop and thread pool.
- Once the async operation is completed, its callback is push to the appropriate task queue.
- The event loop continuously checks whether the call stack is empty or not.
- If the call stack is empty, it picks callbacks from the queues and pushes them to the call stack for execution.
- It first executes microtasks like promises, then executes macrotasks like timers and I/O callbacks.

## 3️⃣ How does Node.js handle multiple concurrent requests?
- Node.js handles multiple concurrent requests using a single-threaded, event-driven, non-blocking I/O Architecture.
- It uses the Event Loop to manage asynchronous operations.
- Time-consuming operation (like I/O, database calls, file system operations) are  delegated to the thread pool, allowing Node.js to continue processing other requests without waiting.
- As a result, Node.js can handle thousands of concurrent connections efficiently with a single main thread.
  
## 4️⃣ What is the Event Loop in Node.js?
- The event loop is the core mechanism that allow Node.js to perform non-blocking asynchronous operations without blocking the main thread.
- It continuously checks whether the call stack is empty.
- If empty, it picks callbacks from the queues and pushes it to the call stack for execution.
- It first executes microtasks like promises, then macrotasks like timers and I/O callbacks.

## 5️⃣ Explain Event Loop phases
- The event loop has various phases:
  - **Timers:** Executes callbacks of `setTimeout` and `setInterval`.
  - **I/O callbacks:** Executes callbacks of completed I/O operations.
  - **Poll:** Waits for new I/O events and executes their callbacks.
  - **Check:** Executes `setImmediate` callbacks.
  - **Close:** Executes cleanup callbacks like closing sockets.
- Between every phases, the event loop executes all microtasks, such as promise callbacks.

## 6️⃣ Difference between Call Stack, Callback Queue, and Microtask Queue
- **Call Stack:** Executes synchronous code and follow  LIFO order.
- **Macrotask Queue:** Stores callbacks of timer functions (`setTimeout`, `setInterval`) and I/O tasks.
- **Microtask Queue:** Stores promise callbacks (`.then()`, `async/await`).
- Microtasks have higher priority and execute before macrotasks.

## 7️⃣ `setTimeout`, `setImmediate`, `process.nextTick`
- **`setTimeout`:** Executes callback after at least the specified delay; callback is placed in the macrotask queue.
- **`setImmediate`:** Executes callback after the current poll phase; callback is placed in the macrotask queue.
- **`process.nextTick`:** Executes callback immediately after the current operation, before the event loop continues; callback is placed in the microtask queue, which has higher priority than macrotasks.

## 8️⃣ What is the Node.js thread pool?
- The thread pool is a set of worker threads provided by libuv to handle heavy or blocking operations.
- By default, it has 4 threads, which Node.js uses to execute heavy tasks in parallel without blocking the main thread
- Once an operation completes, its callback is sent back to the event loop for processing.

## 9️⃣ What are Streams in Node.js and their types?
- Streams used to process large data in chunks instead of loading all at once in memory
- Used in continously reading or writing files, videos streaming, or network data.
- **Types of Streams:**
  - **Readable Stream:** Reads data in chunks (`fs.createReadStream()`).
  - **Writable Stream:** Writes data in chunks (`fs.createWriteStream()`).
  - **Duplex Stream:** Can read and write simultaneously (e.g., TCP socket).
  - **Transform Stream:** Modifies data while reading/writing (e.g., compression).

## 🔟 What is a Buffer?
- A Buffer is a temporary memory area used to store raw binary data.
- Mainly used when working with streams or processing data from files or network.

## 1️⃣1️⃣ Difference between Buffer and Stream
- **Buffer:** Stores entire data in memory; suitable for small, fixed data sizes.
- **Stream:** Processes data in chunks; suitable for large or continuous data.
- Streams are more memory-efficient and faster, often using buffers internally.

## 1️⃣2️⃣ What is the `fs` module?
- The `fs` module (File System) provides methods to interact with files and directories.
- Supports creating, reading, writing, updating, and deleting files.
- Offers both synchronous and asynchronous methods:
  - Sync methods block execution until completion.
  - Async methods start the operation and continue doing other task;Once operation is complete Its results are
  - handled via callback or promise.

## 1️⃣3️⃣ What is the `process` object in Node.js?
- A global object providing information and control over the current Node.js process.
- Information such as
  - Access environment variables (`process.env`)
  -  command-line arguments (`process.argv`)
  -  process ID (`process.pid`)
  -  Manage process lifecycle (`process.exit()`).

## 1️⃣4️⃣ What are Environment Variables?
- Values used to store configuration data outside application code.
- Examples include database URLs, API keys, port numbers, and secrets.
- Accessed in Node.js via `process.env`.

## 1️⃣5️⃣ What is clustering in Node.js?
- Clustering creates multiple worker processes that sharing the same server port.
- When incoming request come master process distributes among worker processes.
- Since node js is single thread,it it help to utilize all cpu core
- Enhances performance, scalability, and fault tolerance.

## 1️⃣6️⃣ Difference between Cluster and Worker Threads
| Aspect | Cluster | Worker Threads |
| --- | --- | --- |
| Processes or Threads | Multiple processes | Multiple threads |
| Memory | Separate memory | Shared memory |
| Best suited for | I/O & server applications | CPU-heavy tasks |
| Communication | Inter-Process Communication (IPC) | Shared memory |

<h1 align="center">Completed</h1>
