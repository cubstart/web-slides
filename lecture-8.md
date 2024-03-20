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
title: Cubstart Lecture 8
mdc: true
---

<img class="w-24 m-auto mb-8" src="/images/cubstart-logo.png" alt="cubstart logo" />

# Cubstart Lecture 8

## Backends, Deployment, and Authentication


---
layout: cubstart-cover
---

# \[start recording\]


---

# Administrivia

<v-clicks>

- HW 7: Quizlet-ish (Part 2) was pushed to this week
  - Will be released today, due Sat/Sun of the week after Spring break
  - No other HW this week!
- New automated [Extension Request Form](https://forms.gle/ngVNtwp1uPdeNktY8)
- Lab will be on Firebase :)
- Final Project is coming up!

</v-clicks>

---

# Final Project

- Very open-ended: build what you'd like to make!
- Spec will be released soon
  - Must have a frontend and interact with some API
  - Backend is optional but would be really cool!
- [Team Formation Form](https://forms.gle/9C6Kj8kJs2eMgRAUA) due by end of week - will also be posted on Ed
  - Groups of 1-4 people
- Mid-Semester Feedback Form will be posted on Ed - required!

---
layout: cubstart-cover
---

# More Backend Topics

What else can backends do? What do they consist of?

---

# File Serving - express.static()
<https://expressjs.com/en/starter/static-files.html>

- `express.static()`: A built-in middleware function in Express.js used to serve static files such as HTML, CSS, and JavaScript from a specified directory.

```js
// serves our frontend files from the 'public' directory
// (GET /, /script.js, /styles.css, etc.)
app.use(express.static(__dirname + "/public"));
```


---

# Real-Time Data - Websockets

- Websockets: A communication protocol (like HTTP) that enables real-time data transfer between clients and servers, allowing for interactive web applications.
- Use Cases: chat applications, live sports scores, and collaborative editing tools, etc.
- In Node.js: can use [socket.io](https://socket.io/) for a beginner-friendly library


---

# Security with [Helmet](https://github.com/helmetjs/helmet)
Generally, lots of security considerations in full-stack web dev!

- Helmet is a middleware for Express.js that helps secure webapps by setting various security-related HTTP headers.
- Mitigates some security risks and protects webapps from common vulnerabilities, such as cross-site scripting (XSS) and clickjacking.
- Common Security Headers: Content Security Policy (CSP), X-XSS-Protection, X-Frame-Options, X-Content-Type-Options

---

# Cookies & Sessions
<div/>

Cookies: Small pieces of data sent from servers that browsers store
  - Commonly used for authentication, session management, personalization, and ad tracking

<br/>

Sessions: mechanism to store user data on the server temporarily
  - Typically identified by a unique session ID
  - Used to maintain user state across multiple requests
  - [express-session](https://expressjs.com/en/resources/middleware/session.html)


---

# Validation (Requests)

- Ensure that data submitted by users is accurate, secure, and compliant before processing
  - Prevent security vulnerabilities and ensure data integrity
- Common Techniques:
  - input sanitization (remove potential malicious code!)
  - data type and/or schema validation (i.e. mongoose schemas)

<!-- Speaker Notes: Discuss the importance of request validation in preventing security vulnerabilities and ensuring data integrity. Mention libraries like Joi for request validation in Express.js applications. -->

---

# Proper Error Handling

- Improves user experience and application reliability by handling unexpected issues gracefully (don't crash server!) and providing clients with useful information.
- Critical for debugging, troubleshooting, and maintaining application stability.
- Techniques: try-catch blocks, error middleware, logging

---

# Logging

- Logging records events and actions within an application, providing valuable insights for monitoring, debugging, and performance analysis.
- Common Logging Levels: Debug, Info, Warning, Error, Critical.
- Tools: pino, winston, morgan, etc. (node.js)


---

# Caching

- Caching improves application performance by storing frequently accessed data temporarily, reducing server load and response times.
- Optimizes resource utilization and delivers content quickly and efficiently.
- Techniques: Client-side caching, server-side caching, content delivery networks (CDNs).

---

# Testing

- Testing ensures application reliability and identifies bugs early in the development process, reducing maintenance costs and improving code quality.
- Types of Testing: Unit testing, integration testing, end-to-end testing (both frontend and backend!)
- Tools: Jest, Mocha, Chai

---

# <https://roadmap.sh/backend>

Explore the comprehensive roadmap for learning backend development.

  <iframe src="https://roadmap.sh/backend" class="w-full mt-8 h-90" />


---
layout: cubstart-cover
---

# Deployment & Hosting

---

# Components of Web Applications

- Frontend: Often consists of static files (HTML, CSS, JavaScript).
- Web Servers: Handle API requests and potentially serve static files.
- Databases: Store and manage application data.

---

# "Managed" Services

- BaaS (Backend as a Service): Provides backend infrastructure and services, allowing developers to focus on application logic.
- PaaS (Platform as a Service): Offers platforms for application deployment and management, including runtime environments and middleware.
- IaaS (Infrastructure as a Service): Provides virtualized computing resources over the internet, including servers, storage, and networking.

---

# Databases

- Databases also need to be deployed and managed.
- Options include using managed database services or setting up databases on virtual machines.

---

# How to Deploy

- Consider scalability, performance, cost, complexity, etc.
- Think about specific requirements of your application
- Ensure proper security measures are implemented throughout the deployment process


---

# 1. Self-Managed Servers

- Provision virtual or physical servers from a cloud provider (IaaS) or your own infrastructure
- Install necessary software (e.g., web server, database server, application runtime)
- Configure security settings
- Deploy your application manually or using deployment tools like Ansible, Chef, or Puppet

---

# 2. Platform as a Service (PaaS)

- Use platforms like Heroku, Google App Engine, or Microsoft Azure App Service
- These platforms manage infrastructure and provide tools for deploying, scaling, and monitoring applications
- Typically, you only need to focus on code and configuration, without dealing with server management

---

# 3. Containerization

- Dockerize your application and dependencies into containers
- Use container orchestration tools like Kubernetes, Docker Swarm, or Amazon ECS to manage and deploy containers at scale
- Provides consistency across different environments and simplifies deployment and scaling

---

# 4. Serverless Computing

- Deploy backend applications as functions or serverless APIs
- Use platforms like AWS Lambda, Google Cloud Functions, or Azure Functions
- Pay only for the resources consumed during execution
- Well-suited for event-driven architectures and microservices

---

# Managed Backend Services

- Utilize managed services for specific backend components:
  - databases (e.g., Amazon RDS, Google Cloud SQL, MongoDB Atlas)
  - caching (e.g., Amazon ElastiCache, Redis Labs)
  - message queues (e.g., Amazon SQS, Google Cloud Pub/Sub)
- Focus on application logic while offloading operational tasks to the service provider

---

# Summary: How to Deploy
Can combine multiple methods!

- DIY: set up servers, install packages, configure security, etc. on your own
  - Fully Self-Host: Use your own infrastructure (i.e. actual computers)
  - IaaS Platforms: Utilize cloud providers like AWS, Linode, or Digital Ocean to provision virtual machines

---

# Summary: How to Deploy
Can combine multiple methods!

- PaaS Platforms: Deploy **applications** on platforms like Heroku, which abstract away infrastructure and system management
- Containerization: Deploy **containers**, or lightweight packages containing your code and all software/system dependencies
- Serverless Platforms: Deploy just **functions** (pieces of code) that run on the cloud


---

# Continuous Integration/Continuous Deployment (CI/CD)

- Automate the deployment process using CI/CD pipelines
- Build, test, and deploy your backend application whenever changes are made to the codebase
- Use platforms/tools like GitHub Actions, CircleCI, Jenkins, etc.

---
layout: cubstart-cover
---

# Authentication

---

# Authentication Overview

- Authentication is the process of verifying the identity of a user.
- Important for controlling access to resources and protecting sensitive data.

---

# Many Ways to Implement Authentication

- Write Your Own Fully: Not recommended due to security risks and complexity.
- Use a Library (e.g., Passport.js): Leverage existing authentication strategies and middleware.
- Use a Managed Service Like Auth0: Simplifies authentication with comprehensive features and integrations.

---

# Under-the-Hood: Cookies & Sessions or JWT Tokens

- Cookies & Sessions: Traditional approach using server-side session management and cookies to track user sessions.
- JWT Tokens: Stateless authentication using JSON Web Tokens for secure authentication and authorization.

---

# Express + [Auth0](https://auth0.com/)

- Use express-openid-connect middleware for seamless integration with Auth0
- Connect Auth0 user authentication to MongoDB for user management and access control
- Will show demo!

---
layout: cubstart-cover
---

# Demo: Express + Auth0

---

# Set Up Auth0 Application

- Create an Auth0 account and set up a new application.
- Obtain the client ID and other variables for the application.

Setup Guides:
- https://auth0.com/docs/quickstart/webapp/express/interactive
- https://github.com/auth0/express-openid-connect/blob/master/EXAMPLES.md


---

# Install Dependencies

```bash
npm install express express-openid-connect dotenv
```

- [express-openid-connect](https://github.com/auth0/express-openid-connect)
- [dotenv](https://github.com/motdotla/dotenv)

---

# Configure Auth0 Middleware

```js
const { auth } = require('express-openid-connect');

app.use(
  auth({
    issuerBaseURL: process.env.ISSUER_BASE_URL,
    baseURL: process.env.BASE_URL,
    clientID: process.env.CLIENT_ID,
    secret: process.env.SECRET,
    requiresAuth: false // make routes public unless explicitly stated
  })
);
```

---

# Protect Routes and Get User Info

```js
const { requiresAuth } = require('express-openid-connect');

app.get('/profile', requiresAuth(), (req, res) => {
    res.json(req.oidc.user);
});
```

---

# Connect to MongoDB and Store User Data

```js
const mongoose = require('mongoose');
mongoose.connect(process.env.DB_CONNECTION_URI, { dbName: 'demo' });
```

```js
const userSchema = new mongoose.Schema({
    sub: String,
    email: String,
    name: String,
});

const User = mongoose.model('User', userSchema);
```

---

# Save Auth0 User to MongoDB


```js
app.get('/profile', requiresAuth(), asyncHandler(async (req, res) => {
    const { sub, email, name } = req.oidc.user;
    const user = await User.findOneAndUpdate(
        { sub }, // find by auth0 ID
        { email, name }, // add email and name
        {
            upsert: true, // insert if not already exists
            new: true, // return updated (new) data
        }
    );
    res.json(user);
}));
```

---

<div style="overflow: auto; max-height: 100%">

```js {all|3,4,10,14-19,22-24,28-39}{lines:true}
// server.js (scroll, next page to highlight)

const dotenv = require('dotenv');
dotenv.config(); // load environment variables from .env file

const express = require('express');
const mongoose = require('mongoose');
const asyncHandler = require('express-async-handler');
const bodyParser = require('body-parser');
const { auth, requiresAuth } = require('express-openid-connect');

const app = express();

const userSchema = new mongoose.Schema({
    sub: String,
    email: String,
    name: String,
});
const User = mongoose.model('User', userSchema);

app.use(bodyParser.json());
app.use(auth({
    authRequired: false,
}));

app.get('/', (req, res) => res.sendFile(__dirname + '/index.html'));

app.get('/profile', requiresAuth(), asyncHandler(async (req, res) => {
    const { sub, email, name } = req.oidc.user;
    const user = await User.findOneAndUpdate(
        { sub }, // find by auth0 ID
        { email, name }, // add email and name
        {
            upsert: true, // insert if not already exists
            new: true, // return updated (new) data
        }
    );
    res.json(user);
}));

// function to connect to database and start the server
async function start() {
    const dbName = process.env.DB_NAME;
    await mongoose.connect(process.env.DB_CONNECTION_URI, { dbName });

    console.log(`Connected to the mongoDB database '${dbName}'`);

    app.listen(3000, () => {
        console.log('Server listening on port 3000')
    });
}

start();
```

</div>

---

```ini
# .env file

ISSUER_BASE_URL=https://<from auth0>.us.auth0.com
CLIENT_ID=<client ID from auth0>
BASE_URL=http://localhost:3000
SECRET=<some long random secret>

DB_CONNECTION_URI='mongodb+srv://ddoski:<password>@cluster0.XXXXXXX.mongodb.net/?retryWrites=true&w=majority&appName=Cluster0'
DB_NAME=cubhub
```

---

<div style="overflow: auto; max-height: 100%">

```json
// package.json

{
  "name": "cubstart-lecture8",
  "version": "1.0.0",
  "description": "Demo app with express and auth0",
  "main": "server.js",
  "scripts": {
    "start": "node server.js",
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "author": "Cubstart Web",
  "private": true,
  "license": "UNLICENSED",
  "dependencies": {
    "body-parser": "^1.20.2",
    "dotenv": "^16.4.5",
    "express": "^4.18.3",
    "express-async-handler": "^1.2.0",
    "express-openid-connect": "^2.17.1",
    "mongoose": "^8.2.2"
  }
}
```

</div>

---

<div style="overflow: auto; max-height: 100%">

```html
<!-- index.html -->

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CubHub</title>

    <link
        rel="stylesheet"
        href="https://cdn.jsdelivr.net/npm/@picocss/pico@2/css/pico.min.css"
    />

    <style>
        main {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            text-align: center;
        }

        pre {
            text-align: initial;
            padding: 1rem;
        }

        #login-view, .logged-in #user-view {
            display: block;
        }

        .logged-in #login-view, #user-view {
            display: none;
        }
    </style>
</head>
<body>
    <main>
        <h1>CubHub</h1>

        <div id="login-view">
            <p>You're not logged in!</p>
            <a href="/login">Login</a>
        </div>

        <div id="user-view">
            <pre id="user-info"></pre>
            <a href="/logout">Logout</a>
        </div>
    </main>

    <script>
        const userInfoEl = document.querySelector('#user-info');

        async function getUserData() {
            const res = await fetch('/profile');

            if (res.ok) {
                const data = await res.json();
                userInfoEl.textContent = JSON.stringify(data, undefined, 2);
                document.body.classList.add('logged-in');
            } else {
                console.log('Error fetching user data - maybe not logged in');
                console.log(res);
            }
        }

        getUserData();
    </script>
</body>
</html>
```

</div>


---

# Notes on Auth0

- Showed a simple example: not production-ready!
- Better ways to do things like user signup flow

Links:
- https://auth0.com/docs/quickstart/webapp/express/interactive
- https://github.com/auth0/express-openid-connect/blob/master/EXAMPLES.md


---
layout: cubstart-cover
---

# Closing Notes

forgive my ramblings... but go build!

---

# Closing Notes: Summary
Backend knowledge, like all things web, is *vast*

- We showed Express + Mongo + Auth0
	- routes, JSON-based APIs, file serving, auth management
- Clients can also be mobile or other native (desktop) apps
- Other tech stacks exist! Continue exploring server-side programming


---

# What if I don't want to write my own backend?

- Preview: Enter *backend-as-a-service*
- Firebase Auth + Firestore (DB) at lab this week!


---
layout: cubstart-cover
---

# \[stop recording\]
