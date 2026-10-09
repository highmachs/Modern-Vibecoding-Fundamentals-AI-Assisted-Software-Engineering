
# Software & Web Development Fundamentals

## A Beginner's Engineering Reference

The basic concepts, terminology, and mental models to understand before building software with AI.

---

# 1. HTTP, APIs & Networking

## HTTP and HTTPS

**HTTP:** A protocol that allows a client and server to communicate.

**HTTPS:** HTTP secured with encryption using TLS. ( Transport Layer Security)

Example: Your browser sends a request to `https://example.com` to load a website.

## Request and Response

**Request:** A message sent to a server asking it to do something or return data.

**Response:** The server's reply to that request.

Example: You click Login → your browser sends your credentials → the server responds with success or an error.

## HTTP Methods

Methods describe the type of operation being requested. ( Commonly used is GET POST PUT DELETE)

- **GET:** Retrieve data.
- **POST:** Submit data or create something.
- **PUT:** Replace a resource.
- **PATCH:** Update part of a resource.
- **DELETE:** Delete a resource.
- **HEAD:** Retrieve response headers without the response body.
- **OPTIONS:** Ask which communication options are supported.

Example:

- `GET /users` retrieves users.
- `POST /users` creates a user.
- `PATCH /users/42` updates user 42.
- `DELETE /users/42` deletes user 42.

## HTTP Status Codes

Status codes indicate the result of an HTTP request.

| Code | Meaning               | Example                                           |
| ---- | --------------------- | ------------------------------------------------- |
| 200  | OK                    | User data retrieved successfully                  |
| 201  | Created               | New account created                               |
| 204  | No Content            | Deletion succeeded; no response body              |
| 301  | Moved Permanently     | Website address changed                           |
| 304  | Not Modified          | Cached content can be reused                      |
| 400  | Bad Request           | Request data is malformed                         |
| 401  | Unauthorized          | Login credentials are missing or invalid          |
| 403  | Forbidden             | User lacks permission                             |
| 404  | Not Found             | Requested resource does not exist or is concealed |
| 409  | Conflict              | Duplicate username or conflicting state           |
| 422  | Unprocessable Content | Input fails application validation                |
| 429  | Too Many Requests     | Rate limit exceeded                               |
| 500  | Internal Server Error | Server encountered an unexpected problem          |
| 502  | Bad Gateway           | Upstream server returned an invalid response      |
| 503  | Service Unavailable   | Service is temporarily unavailable                |
| 504  | Gateway Timeout       | Upstream server took too long to respond          |

**Remember:**

- `2xx` = Success
- `3xx` = Redirection or cache-related response
- `4xx` = Request or client-related issue
- `5xx` = Server or upstream issue

## API

An API (Application Programming Interface) defines how one piece of software communicates with another.

Example: A weather application uses a weather API to retrieve forecasts.

Common API approaches:

- **REST:** Uses resources and HTTP methods.
- **GraphQL:** Lets clients request specific data through a query language.
- **RPC:** Lets clients invoke defined operations remotely.

A webhook is a related concept: one system sends another system a notification when an event happens.

## Endpoint

An endpoint is an API operation available at a particular address.

Example: `GET /api/products` retrieves products.

The HTTP method and endpoint together determine the operation.

## Headers

Headers carry additional information with an HTTP request or response.

Example:

- `Content-Type: application/json`
- `Authorization: Bearer <token>`

## Request Body

The body contains data sent with a request.

Example:

```json
{
  "name": "Alex",
  "email": "alex@example.com"
}
```

## Path Parameters

Values included in the URL path to identify a resource.

Example: `/users/42` identifies user 42.

## Query Parameters

Values added to a URL to filter or control a request.

Example: `/products?page=2&limit=10`

Here, `page=2` requests the second page.

## JSON

A format for representing structured data.

Example:

```json
{
  "product": "Laptop",
  "price": 50000,
  "available": true
}
```

## DNS

DNS translates domain names into IP addresses.

Example: It helps a browser find the server associated with `example.com`.

## IP Address and Port

An IP address identifies a network destination. A port identifies a particular service or listening process on that destination.

Example: `localhost:3000` refers to port 3000 on your own computer.

## CORS

Cross-Origin Resource Sharing is a browser security mechanism that controls which origins can access certain cross-origin responses.

Example: A frontend running at `localhost:3000` requests an API at `localhost:8000`. The API may need to permit that frontend's origin.

---

# 2. Frontend, Backend & Architecture

## Frontend

The part of an application users interact with.

Examples: Buttons, forms, navigation menus, dashboards and product pages.

Common technologies: HTML, CSS, JavaScript, React.

## Backend

The part that processes requests, applies business rules and communicates with databases or external services.

Example: When a user logs in, the backend verifies their credentials and establishes an authenticated session.

Common technologies: Node.js, Python, Java, Go.

## Database

A system used to store and retrieve application data.

Example: A shopping application stores users, products and orders in a database.

## Client-Server Architecture

The client requests something; the server processes the request and returns a response.

Example:

1. You click "View Orders."
2. The frontend requests your orders.
3. The backend checks your access.
4. The backend retrieves the orders.
5. The frontend displays them.

## Business Logic

The rules that determine how an application behaves.

Example: An online store calculates the final price after applying discounts and taxes.

## Middleware

Code that runs while a request is being processed.

Example: Authentication middleware checks whether a user has logged in before allowing access to a protected endpoint.

## Environment Variables

Configuration values supplied outside the application's source code.

Example:

```text
DATABASE_URL=...
API_KEY=...
```

They are commonly used for configuration and secrets. Secret values must remain on the server and out of public frontend code.

## Build

The process of preparing code for execution or deployment.

Example: A frontend build tool bundles JavaScript and optimizes assets for production.

## Runtime

The environment in which a program executes.

Example: Node.js runs JavaScript on a server.

---

# 3. Databases & Data

## SQL

A language used to work with relational databases.

Example:

```sql
SELECT * FROM users;
```

This retrieves rows from the `users` table.

## Relational Database

A database that organizes data into tables and relationships.

Example: A `users` table and an `orders` table connected through a user ID.

## NoSQL Database

A broad category of databases using data models such as documents or key-value pairs.

Example: A document database stores a product and its attributes in a JSON-like document.

## Table, Row and Column

- **Table:** A collection of related records.
- **Row:** One record.
- **Column:** One attribute of that record.

Example: A `users` table contains rows for users and columns such as `id`, `name` and `email`.

## Primary Key

A value that uniquely identifies a record.

Example: User ID `42` identifies one user.

## Foreign Key

A field that references a record in another table, or sometimes the same table.

Example: An order's `user_id` references the user who placed it.

## CRUD

The four basic data operations:

- Create
- Read
- Update
- Delete

Example: Adding a product, viewing it, changing its price and removing it.

## Schema

The defined structure of a database, including tables, fields and constraints.

Example: A user table requires an ID and an email address.

## Index

A database structure that helps locate records faster.

Example: An index on `email` can speed up searches for users by email.

## Transaction

A group of database operations treated as one logical unit.

Example: Transferring money between accounts requires the withdrawal and deposit to be handled consistently.

## Migration

A controlled change to a database's structure.

Example: Adding a `phone_number` column to the users table.

## Join

A SQL operation that combines related records from multiple tables.

Example: Retrieving an order together with the name of the user who placed it.

## ORM

An Object-Relational Mapper lets application code work with database records through programming-language objects.

Example: Creating a user with an ORM instead of writing an SQL `INSERT` statement manually.

## Caching

Keeping frequently used data somewhere faster to access.

Example: Caching a product catalogue so the application does not repeatedly query the database for the same information.

---

# 4. Authentication & Security

## Authentication

Verifying who a user is.

Example: Logging in with a password.

## Authorization

Determining what an authenticated user is allowed to do.

Example: An ordinary user can view their profile, while an administrator can manage all users.

## Session

A way to maintain a user's authenticated state across multiple requests.

Example: After logging in, a browser sends a session cookie with subsequent requests.

## Cookie

A small piece of data stored by a browser and sent with matching requests according to its settings.

Example: A cookie holds a session identifier.

## JWT

JSON Web Token is a format for carrying claims, often in a signed token.

Example: A backend validates a token before accepting a protected request.

A JWT is a token format, not a complete authentication system by itself.

## OAuth 2.0

A framework for granting applications limited access to resources.

Example: An application receives permission to access a user's calendar through an authorization flow.

## OpenID Connect

An identity layer built on OAuth 2.0, commonly used for login.

Example: Signing in to an application using an identity provider.

## Password Hashing

Transforming a password into a one-way verifier using a password-hashing algorithm.

Example: A server stores an Argon2id password hash instead of storing the actual password.

## RBAC

Role-Based Access Control assigns permissions through roles.

Example: `Admin`, `Editor` and `Viewer` have different permissions.

## Input Validation

Checking whether incoming data meets the application's requirements.

Example: Rejecting a registration request with a missing or invalid email address.

## SQL Injection

An attack in which unsafe input changes the meaning of a database query.

Example: A login query built by concatenating raw user input can be manipulated. Parameterized queries help prevent this.

## XSS

Cross-Site Scripting occurs when malicious script content executes in a user's browser through a vulnerable application.

Example: A comment field displays untrusted HTML as executable content.

## CSRF

Cross-Site Request Forgery tricks a user's browser into making an unwanted authenticated request.

Example: A malicious site attempts to trigger an action on another site where the user is logged in.

## Rate Limiting

Restricting how frequently a client can make requests.

Example: Limiting repeated login attempts to reduce automated abuse.

## Secrets Management

Protecting credentials such as API keys, database passwords and private tokens.

Example: Storing a backend API key in a secure environment configuration rather than committing it to Git.

## Least Privilege

Giving each user or service only the permissions needed for its job.

Example: A reporting service can read sales records without being allowed to delete them.

---

# 5. Software Design & Architecture Fundamentals

## Requirements

A description of what the software must do and the conditions it must satisfy.

Example:

- Users can register and log in.
- Users can create tasks.
- Users can mark tasks as completed.

## PRD (Product Requirements Document)

A document explaining what product should be built, who it is for, why it matters and what it must accomplish.

A PRD commonly contains:

- Problem statement
- Target users
- Goals
- Features and requirements
- User flows
- Scope and exclusions
- Acceptance criteria

Example: A task-management PRD specifies that users can create tasks, assign deadlines and filter tasks by completion status.

## Architecture

The high-level structure of the software and how its major components interact.

Example: A task application has a React frontend, a backend API and a PostgreSQL database.

## Tech Stack

The technologies used to build and operate the application.

Example:

- Frontend: React
- Backend: Node.js
- Database: PostgreSQL
- Hosting: A cloud platform
- Version control: Git

## API Contract

The agreed structure of an API request and response.

Example: `POST /api/tasks` accepts a task title and returns the created task with its ID.

## Pagination

Dividing a large set of results into smaller pages.

Example: A product catalogue displays 20 products per page instead of loading 10,000 products at once.

## Monolith

An application whose main components are developed and deployed as one application.

Example: A single backend contains authentication, products, payments and order management.

## Microservices

An architecture in which functionality is split across independently deployable services.

Example: Separate services handle payments, notifications and order management.

## Versioning

Identifying different versions of software or an API.

Example: `/api/v1/products` and `/api/v2/products` expose different API versions.

## Backward Compatibility

A change that allows existing users or integrations to keep working as expected.

Example: Adding an optional response field without removing fields that existing clients rely on.

## Idempotency

Repeating an operation produces the same intended result as performing it once, under the relevant conditions.

Example: Retrying a payment request with the same idempotency key prevents the same payment from being created twice.

## Technical Debt

Future maintenance work caused by shortcuts or decisions that make the software harder to change.

Example: Copying the same business rules into five places means all five may need updating when the rules change.

---

# 6. Browser & Frontend Fundamentals

## HTML

Defines the structure and meaning of a webpage.

Example: Headings, forms, buttons and tables.

## CSS

Controls the appearance and layout of a webpage.

Example: Setting a button's color, spacing and responsive width.

## JavaScript

Adds behavior and interactivity to webpages.

Example: Validating a form or updating a shopping cart.

## DOM

The Document Object Model represents a webpage as a tree of elements that JavaScript can inspect and modify.

Example: JavaScript changes a heading's text after a button is clicked.

## Browser Storage

Browsers provide different mechanisms for storing information.

- **Cookies:** Often used for sessions and request-related state.
- **Local storage:** Persists data across browser restarts.
- **Session storage:** Generally persists for the lifetime of a browser tab's page session.

Example: A theme preference can be stored in local storage. Sensitive authentication tokens require more careful storage decisions.

## State Management

Managing data that changes while an application runs.

Example: A shopping cart's item count changes when the user adds or removes products.

## Forms

Interfaces for collecting user input.

Example: A registration form collects a name, email and password.

## Accessibility

Making software usable by people with different abilities and assistive technologies.

Example: A form has properly associated labels and can be operated using a keyboard.

## Responsive Design

Making an interface adapt to different screen sizes.

Example: A desktop navigation bar becomes a compact mobile menu.

## Browser Developer Tools

Built-in tools for inspecting and debugging web applications.

Example: Use the Network tab to inspect API requests, the Console to inspect errors and the Elements tab to inspect the page structure.

## Basic Performance

How quickly and smoothly an application loads and responds.

Example: Compressing large images can reduce loading time. Loading only the data a page needs can reduce unnecessary work.

---

# 7. Reliability & Performance Basics

## Timeout

A limit on how long an operation is allowed to wait.

Example: An API request times out after waiting too long for an upstream service.

## Retry

Attempting an operation again after a temporary failure.

Example: Retrying a request after a temporary network error. Retries should be limited and designed carefully for operations that create or modify data.

## Exponential Backoff

Increasing the delay between repeated attempts.

Example: Retry after 1 second, then 2 seconds, then 4 seconds, with appropriate limits and jitter.

## Race Condition

A bug caused by operations happening in an unexpected order or at the same time.

Example: Two requests update the same account balance based on an outdated value.

## Latency

The time taken for an operation to complete or produce a response.

Example: An API responds in 150 milliseconds.

## Throughput

The amount of work a system completes in a given period.

Example: An API processes 500 requests per second.

## Logging

Recording events and errors to help understand application behavior.

Example: Recording a failed payment attempt with a request ID and error reason.

## Monitoring

Tracking application health and performance over time.

Example: Monitoring error rates, response times and CPU usage.

## Backup and Recovery

Keeping recoverable copies of data and having a process to restore it.

Example: Restoring a database from a verified backup after accidental deletion.

## Scalability

The ability to handle increased workload by adding resources or improving the system.

Example: Running additional application instances when traffic increases.

## Load Balancing

Distributing incoming requests across multiple application instances.

Example: Sending requests across three servers rather than relying on one server.

## Queue and Background Job

A queue holds work that can be processed asynchronously.

Example: A user places an order, and a background worker sends the confirmation email afterward.

---

# 8. Fundamental Checklist

Use this checklist before starting a software project or reviewing AI-generated code.

## A. HTTP & APIs

- [ ] I understand HTTP requests and responses.
- [ ] I know GET, POST, PUT, PATCH and DELETE.
- [ ] I recognize common 2xx, 4xx and 5xx status codes.
- [ ] I understand APIs, endpoints, headers, request bodies and JSON.
- [ ] I understand path parameters, query parameters and CORS.

## B. Application Architecture

- [ ] I understand frontend versus backend.
- [ ] I can explain the client-server request flow.
- [ ] I understand business logic and middleware.
- [ ] I know what environment variables are.
- [ ] I understand what happens during a build and at runtime.

## C. Databases

- [ ] I understand tables, rows, columns and schemas.
- [ ] I know primary keys and foreign keys.
- [ ] I understand CRUD and basic SQL.
- [ ] I understand relationships, indexes and migrations.
- [ ] I know why transactions and backups matter.

## D. Security

- [ ] I understand authentication versus authorization.
- [ ] I know the purpose of sessions, cookies and tokens.
- [ ] I understand password hashing and secret protection.
- [ ] I recognize SQL injection, XSS and CSRF.
- [ ] I understand input validation, rate limiting and permissions.

## E. Software Design

- [ ] I understand requirements and PRDs.
- [ ] I can explain architecture and tech stack.
- [ ] I understand API contracts and versioning.
- [ ] I know what pagination is.
- [ ] I understand monoliths and microservices.
- [ ] I understand backward compatibility and idempotency.

## F. Browser & Frontend

- [ ] I know the purpose of HTML, CSS and JavaScript.
- [ ] I understand the DOM and state management.
- [ ] I understand forms and browser storage.
- [ ] I know the basics of accessibility and responsive design.
- [ ] I can inspect network requests and console errors.

## G. Reliability & Operations

- [ ] I understand timeouts, retries and race conditions.
- [ ] I know the difference between latency and throughput.
- [ ] I understand logs, monitoring and error diagnosis.
- [ ] I understand development and production environments.
- [ ] I know the purpose of deployment, backups and recovery.

---

## Final Mental Model

When you build any web application, keep these questions in mind:

1. **What are we building?** Requirements and PRD.
2. **How is it structured?** Architecture and tech stack.
3. **What does the user interact with?** Frontend.
4. **Where does the logic run?** Backend.
5. **How do components communicate?** APIs and HTTP.
6. **Where is the data stored?** Database and storage.
7. **Who can do what?** Authentication and authorization.
8. **How do we know it works?** Testing, logs and debugging.
9. **How does it reach users?** Deployment and hosting.
10. **How do we keep it reliable?** Security, monitoring, backups and recovery.

These fundamentals give you the vocabulary and mental models needed to understand a codebase, plan a project, guide AI coding tools and identify mistakes before they become production problems.
