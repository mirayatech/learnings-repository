# 📦 Require vs. Import

In Node.js, you have two methods to bring external modules into your code: `require` and `import`. They serve the same purpose but have differences:

## 🧩 Require

`require` is a built-in Node.js function that synchronously loads external modules. It blocks code execution until the module is loaded. Example:

```javascript
const fs = require("fs");
const data = fs.readFileSync("file.txt", "utf8");
console.log(data);
```

Here, we use `require` to load the `fs` module for file operations and read a file's contents.

## 🔄 Import

`import` is from ES6 (ECMAScript 2015) and works asynchronously. Example:

```javascript
import fs from "fs/promises";

async function readFile() {
  const data = await fs.readFile("file.txt", "utf8");
  console.log(data);
}

readFile();
```

This snippet uses `import` to load the `fs/promises` module, offering file capabilities with promises, and reads and logs file contents.

## 🏁 Conclusion

In summary, `require` and `import` are methods for importing external modules in Node.js. They differ in behavior but share the same purpose. Choose based on your needs.
