# Section 2

## 5. https://www.udemy.com/course/nodejs-express-mongodb-bootcamp/learn/lecture/15080910#content

- NodeJS is a JavaScript runtime built on Google's open-source V8 engine.
- A runtime is like an environment in which a program can run in.
- V8 parses and executes JavaScript code.
- With JavaScript outside of the browser, we can do things like access the file system, have access to better networking capabilities, and build the backend of applications.
- Node.js is great for building fast, scalable, and data-intensive applications because it is single-threaded, based on an event-driven, non-blocking I/O model.
- We can build many things with Node.js, such as APIs with databases behind them (preferably NoSQL), data streaming platforms, real-time chat applications, server-side web applications, and so on.
- We should prefer not to build applications with heavy server-side processing with NodeJS.

## 6. https://www.udemy.com/course/nodejs-express-mongodb-bootcamp/learn/lecture/15080912?start=0#content

- REPL stands for Read-Evaluate-Print-Loop, which is a programming environment that allows users to input and evaluate code, and then see the results.
- To access the Node.js REPL, you can type 'node' in your command line shell.
- In Node.js REPL, underscore(\_) is a special variable which stores the result of last expression evaluation.
- Press Ctrl + D to exit Node.js REPL.

## 7. https://www.udemy.com/course/nodejs-express-mongodb-bootcamp/learn/lecture/15080914#content

- Node.js is So Node.js is built around the concept of modules where all kinds of additional functionality are stored.
- Think of them as building blocks for your application.
- Modules allow you to organize your code into smaller, manageable units, promote code reusability, and avoid global namespace pollution.
- In Node.js, 'require()' is a built-in function that allows you to include and use modules in your JavaScript code.
- The Node.js file system module allows you to work with the file system on your computer.
- To include the File System module, use the require() method:
  ```javascript
  const fs = require("fs");
  ```
- The `fs.readFile()` method is used to read files on your computer.
- Its syntax is
  ```javascript
  fs.readFile(filename, [options], callback);
  ```
  where _filename_ is the file path, _options_ are optional encoding or flag options, and _callback_ is a function to handle the read operation's result.
- The `fs.readFileSync()` method is used to read files synchronously.
- Its syntax is:
  ```javascript
  fs.readFileSync(filename, [options]);
  ```
  where _filename_ is the file path, and _options_ are optional encoding or flag options.
- The `fs.writeFile()` method is used to write data to a file asynchronously.
- Its syntax is:
  ```javascript
  fs.writeFile(filename, data, [options], callback);
  ```
  where _filename_ is the file path, _data_ is the content to write, _options_ are optional encoding or flag options, and _callback_ is a function to handle the write operation's result.
- The fs.writeFileSync() method is used to write data to a file synchronously.
- Its syntax is:
  ```javascript
  fs.writeFileSync(filename, data, [options]);
  ```
  where _filename_ is the file path, _data_ is the content to write, and _options_ are optional encoding or flag options.
