---
theme: default
class: cover text-center
colorSchema: light
highlighter: shiki
lineNumbers: false
info: |
  # Cubstart Lecture 8
  Backends, Deployment, and Authentication

  See more at [cubstart.com](https://cubstart.com)
drawings:
  persist: false
defaults:
  foo: true
transition: slide-left
title: Cubstart Lecture 6
mdc: true
---

<img class="w-24 m-auto mb-8" src="/images/cubstart-logo.png" alt="cubstart logo" />

# Cubstart Lecture 6

## Node.js and Express


---
layout: cubstart-cover
---

# \[start recording\]


---

# Administrivia

<v-clicks>

- HW 5: OpenWeatherMap is due this weekend
- HW 6 will be released soon
- Final project: maybe start thinking about partners?

</v-clicks>


---

# So far: client-side apps
<div />

<v-clicks>

Webpages that run on the user's computer (browser)

  - HTML/CSS/JS, can *use* APIs

Limitations:
  - Storing data
  - Authentication and authorization
  - Communication across users
  - Generally limited by browser's capabilities

</v-clicks>


---
layout: cubstart-cover
---

# Intro to server-side programming

---

# What is a web server?
<!-- <div /> -->

hardware/software that serves content over HTTP

<v-clicks>

- host files (sometimes called static file server)
- host APIs to expose data (aka API server)

</v-clicks>

<img class="mt-16 h-48" src="https://geobgu.xyz/web-mapping/images/web-server.png">


---

# How to make a web server?

<v-clicks>

- Java, Python, C++, etc. all have libraries for HTTP servers
- **Node.js** - JavaScript runtime
- Other (newer, experimental) JS runtimes: deno, bun

</v-clicks>

<!-- - TypeScript is also often used:
  - superset of JS that adds type-checking
  - “transpiles” down to JS (can be run by any JS runtime - nodejs, browser, etc.) -->


---

# Intro to <img class="ml-2 w-24 inline" alt="node.js logo" src="https://upload.wikimedia.org/wikipedia/commons/thumb/d/d9/Node.js_logo.svg/2560px-Node.js_logo.svg.png">

- Runtime for JavaScript
- Module system: require(‘’) files and packages
- Today: run locally, or on stackblitz


<!--
- boot up stackblitz
- basic node.js example -->


---

# NPM: Packages in Node.js
- npm: node package manager
  - alternatives for node.js: `yarn`, `pnpm`, etc.
  - other languages: python `pip`, rust `cargo`
- declare dependencies in `package.json`
- `npm install <xyz>`

---

# Web frameworks for web servers
- Language-specific
- Express for node.js
  - Simple API
  - Alternatives: fastify, nest.js, a ton more
- Other languages: python flask or django, java spring, ASP.NET

---

# Intro to Express.js

- basic boilerplate
- serving basic requests


```js
const express = require('express');
const app = express();
const port = 3000;

app.get('/', (req, res) => {
  res.send('<html><body><h1> hello world! </h1></body></html>');
});

app.listen(port, () => {
  console.log('express app is running!');
});
```

---

# Basic functionality

- Route handlers
- Status codes & error messages
- Path params & query params
- Setting headers

---

# Middleware in express.js

i.e. body-parser for parsing POST request bodies


---

# RESTful APIs and conventions

- path params & query params
- routing

---
# Books API (live demo)


---

# What else can servers do?

- authentication
- managing sessions
- sending real-time data (websockets)

---

# Server hosting & deployment

---
layout: cover
---

<div class="flex items-center">

<img class="w-20 ml-12 mr-12 mb-4" src="/images/cubstart-logo.png" alt="cubstart logo" />

# Other topics

</div>
