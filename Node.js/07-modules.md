# 📦 What is a Module

In Node.js, a module is a self-contained block of code designed for a specific task. There are three main types of modules:

## 🏢 Internal Modules

These modules come bundled with Node.js, making them instantly available. For example, the `http` module is used to create web servers:

```javascript
const http = require("http");
```

## 🎱 User-Created Modules

You can craft custom modules tailored to your needs, like this one for adding numbers:

```javascript
// math.js
function add(a, b) {
  return a + b;
}
module.exports = add;
```

## 🌐 Third-Party Modules

npm offers a treasure trove of pre-built tools. For instance, `axios` simplifies HTTP requests:

```javascript
const axios = require("axios");
```

In summary, Node.js modules are self-contained code blocks that bring order and simplicity to your projects.
