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
- Synchronous code  executed immedetely in the call stack.
- Asynchronous TIme consuming operation such as database call or I/o operation are delegated to threadpool which manage by libuv.
- Instead of waiting operation to complete,Node js contitnue to execute other code
- Once the async operation is completed, its callback is push to the appropriate task queue.
- The event loop continuously checks whether the call stack is empty or not.
- If the call stack is empty, it picks callbacks from the queues and pushes them to the call stack for execution.
- It first executes microtasks like promises, then executes macrotasks like timers and I/O callbacks.

## 3️⃣ How does Node.js handle multiple concurrent requests?
- Node.js handles multiple concurrent requests using a single-threaded, event-driven, non-blocking I/O Architecture.
- Asynchronous Time-consuming operation (like I/O, database calls, file system operations) are delegated to the thread pool,which is manage by Libuv
- Instead of waiting for operation to coplete,nodejs continue to proceed other request
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
- This function also known as timer Function Module
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
- using Buffer.from we can create buffer of string
- using Buffer.toString() convert bufffer in string

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
  -  Environment variables (`process.env`)
  -  command-line arguments (`process.argv`)
  -  process ID (`process.pid`)
  -  Manage process lifecycle (`process.exit()`).

## 1️⃣4️⃣ What are Environment Variables?
- Values used to store configuration data outside application code.
- Examples include database URLs, API keys, port numbers, and secrets.
- Accessed proceess in nodejs using dotenv module and `process.env`.

## 1️⃣5️⃣ What is clustering in Node.js?
- Clustering isthe procees of creating multiple child processes that sharing the same server port.
- When incoming request come master process distributes among child processes.
- Since node js is single thread,it it help to utilize all cpu core
- Enhances performance, scalability, and fault tolerance.

## 1️⃣6️⃣ Difference between Cluster and Worker Threads
| Aspect | Cluster | Worker Threads |
| --- | --- | --- |
| Processes or Threads | Multiple processes | Multiple threads |
| Memory | Separate memory | Shared memory |


## 17 What is Module

- Module are reuseable block of code that encapsulate specfic functionality and can be import and export across file
- Node Js support two type of module system
- Common JS -> IT is older and  default module system, that allow to import and export using require() and module.export=
- ES Module-> It is modern module system that allow import and export using import and export keyword,To use we need to define type="module" in pakage.JSON

### Built-in Modules

- Built-In module provide nodejs are

| Module | Description |operation|
|---------|-------------|--------|
| **fs** | The **fs** module used interaction with the file system. |provide operation such fs.readFile,fsWriteFile,fs.appendFile,fs.unlinkFile|
| **http** | Creates web servers and handles HTTP requests/responses. |http.createServer()|
| **path** | Handles file and directory paths (`path.join`, `path.resolve`). |`path.join`, `path.basename`,`path.dirname`,`path.extname`)|
 **events** | Enables event-driven programming (`EventEmitter`). |
| **os** | Provides system-related info (CPU, memory, OS type). |
| **stream** |process data in chunks (read/write streams). |
| **util** | Contains utility functions (e.g., `util.promisify`). |
| **crypto** | Provides cryptographic functionality (hashing, encryption). |

 ## 18- Event driven programming

- Event-Driven Programming** is a programming paradigm where program react to  events **like user interaction or messages**, and whenever an event happens, it corresponding code gets executed..
- The **EventEmitter** class (from Node’s `events` module) allows creating **custom events**.
- `.on()` → listens for an event  
- `.emit()` → triggers the event

## 19- NPM (Node Package Manager)
- **NPM (Node Package Manager)** is the **default package manager for Node.js**.  
- It used to **install, manage** packages and dependencies for their projects.
- Node Js uses semantic versioning in format MAJOR:MINOR:PATCH
- ^->upload to latest minor and patch ~ what to latest patch no sysmbol mean exact version
- Local package -> Install inside project folder can accessable only with in that folder
- Global pakage -> Global package install system wide and can be accessable from anywhere

### Package.json
- The **`package.json`**  defines  metadata and dependencies of project
- `npm init -y`
- 
### npx
- **npx** is the CLI tool that used to **execute packages without installing them globally**.

## 20- What is REPL in Node.js?

REPL in Node.js stands for Read–Eval–Print–Loop.
It is an interactive environment where we can execute JavaScript code line by line, and Node.js immediately reads the input, evaluates it, prints the result, and waits for the next command.

## what control flow

Control flow in Node.js  determines in which order code executes

<h1 align="center">Completed</h1>
