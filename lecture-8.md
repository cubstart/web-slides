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
title: Welcome to Slidev
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

- HW 7: Quizlet-ish (Part 2) was delayed from last week
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
- Start thinking about partners

---
layout: cubstart-cover
---

# More Backend Topics

What else can backends do? What do they consist of?

---

# File Serving - express.static()

- `express.static()`: A built-in middleware function in Express.js used to serve static files such as HTML, CSS, and JavaScript from a specified directory. It simplifies the process of serving static assets in web applications.
- Importance: Serving static files is essential for delivering frontend resources required for rendering web pages in our applications.

<!-- Speaker Notes: Explain how to serve static files using express.static() in Express.js. Discuss the importance of organizing static files in a public directory and how to configure express.static(). -->

---

# Real-Time Data - Websockets

- Websockets: A communication protocol (like HTTP) that enables real-time data transfer between clients and servers, allowing for interactive web applications.
- Use Cases: chat applications, live sports scores, and collaborative editing tools, etc.

<!--
Speaker Notes: Introduce Websockets as a technology for real-time communication between the client and server. Mention common use cases such as chat applications and live updates. Discuss libraries like Socket.io for implementing Websockets in Node.js applications.
-->

---

# Cookies & Sessions
<div/>

Cookies: Small pieces of data sent from servers that browsers store
  - Commonly used for authentication, session management, personalization, and ad tracking

<br/>

Sessions: mechanism to store user data on the server temporarily
  - Typically identified by a unique session ID
  - Used to maintain user state across multiple requests

<!--
Speaker Notes: Discuss the purpose and use cases of cookies and sessions in web applications. Mention how sessions can be implemented in Express.js using middleware like express-session.
-->

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

- Effective error handling improves user experience and application reliability by gracefully managing unexpected conditions and providing informative feedback to users and developers.
- Techniques: try-catch blocks, error middleware, logging
- Importance: Proper error handling is critical for debugging, troubleshooting, and maintaining application stability.

<!--
Speaker Notes: Explain the significance of proper error handling in backend development. Discuss strategies for handling errors gracefully and logging error details for debugging purposes.
-->

---

# Logging

- Logging records events and actions within an application, providing valuable insights for monitoring, debugging, and performance analysis.
- Common Logging Levels: Debug, Info, Warning, Error, Critical.
- Tools: pino, winston, morgan, etc. (node.js)

<!-- Speaker Notes: Introduce logging as a critical aspect of backend development. Discuss the importance of logging different types of events and choosing appropriate logging levels. Mention popular logging libraries like Winston and Morgan. -->

---

# Security (ex. use Helmet)
Generally, lots of security considerations in full-stack web dev!

- Helmet is a middleware for Express.js that helps secure HTTP headers by setting various security-related headers.
- Common Security Headers: Content Security Policy (CSP), X-XSS-Protection, X-Frame-Options, X-Content-Type-Options
- Importance: Helmet helps mitigate security risks and protect web applications from common vulnerabilities, such as cross-site scripting (XSS) and clickjacking.

<!--
Speaker Notes: Discuss the importance of security in web applications and how Helmet helps mitigate security risks by setting HTTP headers securely. Explain common security headers provided by Helmet and their purposes.
-->

---

# Caching

- Caching improves application performance by storing frequently accessed data temporarily, reducing server load and response times.
- Techniques: Client-side caching, server-side caching, content delivery networks (CDNs).
- Importance: Caching helps optimize resource utilization and enhance user experience by delivering content quickly and efficiently.

<!-- Speaker Notes: Explain caching as a technique for improving performance and reducing server load. Discuss different caching strategies and when to use them. Mention caching libraries like Node-cache for server-side caching. -->

---

# Testing

- Testing ensures application reliability and identifies bugs early in the development process, reducing maintenance costs and improving code quality.
- Types of Testing: Unit testing, integration testing, end-to-end testing.
- Tools: Jest, Mocha, Chai

<!-- Speaker Notes: Discuss the importance of testing in backend development and the different types of testing methodologies. Mention popular testing frameworks like Jest and Mocha for testing Node.js applications. -->

---

# <https://roadmap.sh/backend>

Explore the comprehensive roadmap for learning backend development.

  <iframe src="https://roadmap.sh/backend" class="w-full mt-8 h-90" />

<!--
Speaker Notes: Introduce roadmap.sh/backend as a valuable resource for learning and mastering backend development concepts. Encourage students to explore the roadmap to gain a deeper understanding of backend technologies and best practices.
-->

---
layout: cubstart-cover
---

# Deployment & Hosting

---

# Components of Web Applications

- Frontend: Often consists of static files (HTML, CSS, JavaScript).
- Web Servers: Handle API requests and potentially serve static files.
- Databases: Store and manage application data.

<!-- Speaker Notes: Explain the components of web applications and their respective roles. Emphasize the separation of concerns between frontend, backend, and database layers. -->

---

# "Managed" Services

- BaaS (Backend as a Service): Provides backend infrastructure and services, allowing developers to focus on application logic.
- PaaS (Platform as a Service): Offers platforms for application deployment and management, including runtime environments and middleware.
- IaaS (Infrastructure as a Service): Provides virtualized computing resources over the internet, including servers, storage, and networking.

<!-- Speaker Notes: Discuss the different types of managed services for deploying web applications. Explain the trade-offs between BaaS, PaaS, and IaaS in terms of control, scalability, and management overhead. -->

---

# Databases

- Databases also need to be deployed and managed.
- Options include using managed database services or setting up databases on virtual machines.

<!-- Speaker Notes: Highlight the importance of deploying and managing databases for web applications. Discuss the benefits of using managed database services for scalability, reliability, and ease of maintenance. -->

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

<!-- Speaker Notes: Explain the various deployment options available for web applications, ranging from self-hosting to serverless architectures. Discuss the benefits and drawbacks of each approach in terms of scalability, cost, and complexity. -->

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

<!-- Speaker Notes: Introduce authentication as a crucial aspect of web application security. Discuss the importance of verifying user identities to control access and maintain data integrity. -->

---

# Many Ways to Implement Authentication

- Write Your Own Fully: Not recommended due to security risks and complexity.
- Use a Library (e.g., Passport.js): Leverage existing authentication strategies and middleware.
- Use a Managed Service Like Auth0: Simplifies authentication with comprehensive features and integrations.

<!-- Speaker Notes: Discuss different approaches to implementing authentication in web applications. Emphasize the benefits of using libraries or managed services for authentication to reduce development time and improve security. -->

---

# Under-the-Hood: Cookies & Sessions or JWT Tokens

- Cookies & Sessions: Traditional approach using server-side session management and cookies to track user sessions.
- JWT Tokens: Stateless authentication using JSON Web Tokens for secure authentication and authorization.

<!-- Speaker Notes: Explain the mechanisms used for authentication, including cookies and sessions for server-side session management and JWT tokens for stateless authentication. Discuss the pros and cons of each approach and when to use them. -->

---

# Express + [Auth0](https://auth0.com/)

- Use express-openid-connect middleware for seamless integration with Auth0
- Connect Auth0 user authentication to MongoDB for user management and access control
- Will show demo!

<!--
Speaker Notes: Walk through the live demonstration of implementing authentication with Express and Auth0. Highlight the steps involved in setting up Auth0 integration, configuring express-openid-connect middleware, and connecting Auth0 users to MongoDB for user management.
-->

---
layout: cubstart-cover
---

# Demo: Express + Auth0

---

# Set Up Auth0 Application

- Create an Auth0 account and set up a new application.
- Obtain the client ID and client secret for the application.

<!-- Speaker Notes: Explain the initial setup process for creating an Auth0 application. Mention the importance of obtaining the client ID and client secret for integrating Auth0 with Express. -->

---

# Install Dependencies

```bash
npm install express express-openid-connect dotenv
```

- [express-openid-connect](https://github.com/auth0/express-openid-connect)
- dotenv

<!--
Speaker Notes: Guide students through installing the necessary dependencies for implementing authentication with Express and Auth0. Emphasize the use of express-openid-connect middleware for seamless integration.
-->

---

# Configure Auth0 Middleware

```javascript
const { auth } = require('express-openid-connect');

app.use(
  auth({
    issuerBaseURL: process.env.AUTH0_ISSUER_BASE_URL,
    baseURL: process.env.BASE_URL,
    clientID: process.env.AUTH0_CLIENT_ID,
    secret: process.env.SESSION_SECRET,
    requiresAuth: false // make routes public unless explicitly stated
  })
);
```

<!-- Speaker Notes: Explain how to configure the express-openid-connect middleware in Express.js to authenticate users with Auth0. Mention the required parameters such as issuerBaseURL, clientID, and secret, which should be stored in environment variables. -->

---

# Protect Routes

```javascript
const { requiresAuth } = require('express-openid-connect');

app.get('/profile', requireAuth(), (req, res) => {
  res.json(req.openid.user);
});
```

<!-- Speaker Notes: Show how to protect routes by requiring authentication using the express-openid-connect middleware. Demonstrate accessing user information from the req.openid.user object, which contains authenticated user data. -->

---

# Connect to MongoDB

```javascript
const mongoose = require('mongoose');
mongoose.connect(process.env.MONGODB_URI);
```

<!-- Speaker Notes: Provide a brief code snippet demonstrating how to connect Express.js with MongoDB using Mongoose. Mention the importance of storing MongoDB connection URI in environment variables for security. -->

---

# Store User Data

```javascript
const userSchema = new mongoose.Schema({
  sub: String,
  email: String,
  name: String,
});

const User = mongoose.model('User', userSchema);
```

<!-- Speaker Notes: Show how to define a Mongoose schema for storing user data retrieved from Auth0. Explain the structure of the userSchema and how it maps to user information obtained during authentication. -->

---

# Save Auth0 User to MongoDB


```javascript
app.get('/profile', asyncHandler(async (req, res) => {
  const { sub, email, name } = req.openid.user;
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

<!--
Speaker Notes: Demonstrate how to save authenticated Auth0 users to MongoDB using Mongoose. Explain the findOneAndUpdate() method to either create a new user or update an existing user based on the Auth0 sub (subject) identifier.
-->

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
