
# Express.js Interview Questions and Answers

## 1️⃣ What is Express.js and why was it created?

- Express.js is a lightweight web framework built on top of Node.js.
- It was created to simplify building server-side applications and APIs in Node.js.
- Without Express, developers have to write a lot of boilerplate code using the core http module.
- Express provides simple routing, middleware support, and request-response handling, which makes development faster and cleaner.

## 2️⃣ What problem does Express.js solve?

- Express.js solves the problem of writing a lot of boilerplate code in plain Node.js.
- Using the core http module, handling routes, requests, responses, and middleware becomes messy and hard to manage.
- Express offers simple routing, middleware support, and request-response handling, making development faster and more organized.

## 3️⃣ Explain the Express request–response lifecycle?

- When a client sends a request, it first reaches the Express application.
- The request then passes through middleware functions one by one.
- Middleware can modify the request or response, perform validation, authentication, or logging.
- After middleware, the request reaches the matching route handler.
- The route handler processes the request, interacts with the database or business logic, and sends a response back to the client.
- Once the response is sent, the request–response cycle ends.

## 4️⃣ What is app in Express?

- `app` is an instance of an Express application.
- It is created by calling the `express()` function.
- The `app` object is used to define routes, add middleware, and start the server.

## 5️⃣ What is middleware in Express?

- Middleware in Express is a function that runs between the request and the response.
- It has access to the `req`, `res`, and `next()` function.
- Middleware can modify request and response objects and perform tasks like logging, authentication, validation, and error handling.
- Once the work is complete, it passes control to the next middleware using `next()`.

## 6️⃣ Types of middleware in Express

- **Application-level middleware**: applied to the whole app using `app.use()`.
- **Router-level middleware**: applied to specific routes using `router.use()`.
- **Built-in middleware**: provided by Express, e.g., `express.json()`, `express.urlencoded()`.
- **Third-party middleware**: external libraries installed via npm, e.g., `cors`, `morgan`.
- **Error-handling middleware**: used to handle errors and has four parameters.

## 7️⃣ What is `next()` and why is it needed? What happens if `next()` is not called?

- `next()` is a function used to pass control from one middleware to the next in the cycle.
- It is needed because Express executes middleware in order (top to bottom).
- If `next()` is not called, the request will get stuck and the response will never be sent.

## 8️⃣ What is error-handling middleware in Express?

- Error-handling middleware is a special middleware used to handle errors.
- It has four parameters: `(err, req, res, next)`.
- It runs only when an error occurs, bypassing normal middleware, and sends the error response.

## 9️⃣ Difference between normal middleware and error middleware

- **Normal middleware**:
  - Used to modify requests before reaching route handlers.
  - Has three parameters: `(req, res, next)`.
  - Tasks include logging, authentication, validation.
- **Error middleware**:
  - Used to handle errors in the application.
  - Has four parameters: `(err, req, res, next)`.
  - Runs only when an error occurs.

## 🔟 What is routing in Express?

- Routing defines how an application responds to client requests based on URL and HTTP method.
- It matches the URL path and method of incoming requests.
- Based on this match, Express calls the corresponding route handler function.

## 1️⃣1️⃣ What is the `req` object in Express?

- The `req` object represents the incoming HTTP request.
- It contains all information sent by the client, such as URL parameters, query parameters, request body, headers, and cookies.

**Common properties:**
- `req.params` — Dynamic values of the URL path (route parameters) that send using : colon .
- `req.query` — Key-value pairs of the URL query string that send using &&.
- `req.body` — Data sent in the request body.
- `req.headers` — Metadata about the request like content type and authorization.

## 1️⃣2️⃣ What are route parameters in Express?

- Route parameters are dynamic values within the URL.
- Defined using a colon (`:`) in the URL path.
- Their values are accessible via `req.params`.

## 1️⃣3️⃣ What is the `res` object in Express?

- The `res` object represents the HTTP response sent back to the client.
- It contains methods and properties to send data, such as status code, headers, and response body (JSON, text, HTML).

## 1️⃣4️⃣ What happens when no route matches?

- If no route matches, Express goes through all routes and middleware.
- By default, Express returns a `404 Not Found` error.
- If a custom 404 middleware is defined, it executes instead of the default response.

## 1️⃣5️⃣ How do you handle errors globally in Express?

- Global error handling is done using error-handling middleware.
- Create middleware with four parameters: `(err, req, res, next)` and place it at the end of all routes.
- When an error occurs, it is passed via `next(err)`, and Express forwards it to this middleware.
