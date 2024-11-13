# Teacher-Crud
This Node.js application manages teachers, students, and courses with JWT-based authentication and authorization, allowing CRUD operations for students and courses, along with email notifications on student creation.

# Server Setup Using Express, Mongoose, JWT, and Nodemailer

<p>Here's a breakdown of the main components in your server setup using Express, Mongoose, JWT, and Nodemailer, organized by functionality.</p>

## Project Dependencies

- **Express**: <p>A web framework for creating HTTP servers and handling routes.</p>
- **Mongoose**: <p>An ODM (Object Data Modeling) library for MongoDB, used to define schemas and interact with the database.</p>
- **JWT (jsonwebtoken)**: <p>Used for creating and verifying tokens for secure authentication.</p>
- **Nodemailer**: <p>Used for sending emails through your application.</p>
- **CORS**: <p>Enables Cross-Origin Resource Sharing, allowing restricted resources to be accessed on different domains.</p>
- **Body-Parser**: <p>Middleware for parsing request bodies (now integrated within Express).</p>

## Database and Model Definitions

### MongoDB Connection

<p>Uses <code>mongoose.connect</code> to connect to a MongoDB database. Connection logs success or failure messages.</p>

### Schemas and Models

1. **Teacher Schema**:
   <p>Contains fields like <code>name</code>, <code>email</code>, <code>age</code>, and <code>password</code>.</p>

2. **Student Schema**:
   <p>Contains fields like <code>name</code>, <code>email</code>, <code>dob</code>, <code>batch</code>, and a reference to a <code>Teacher</code>.</p>

3. **Course Schema**:
   <p>Contains fields like <code>name</code>, <code>author</code>, and a reference to a <code>Student</code>.</p>

## Middleware and Helpers

### CORS and JSON Parsing

```javascript
app.use(cors()); // Enables cross-origin requests.
app.use(express.json()); // Enables JSON parsing of incoming request bodies.
