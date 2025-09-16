➤ Node.js & Express Basics
1. Node.js single-threaded kaise hai aur phir asynchronous code kaise handle karta hai?

Answer:
✔ Node.js main single thread use karta hai (event loop)
✔ Heavy I/O operations ko non-blocking async way mein handle karta hai
✔ Callbacks, Promises aur async/await event loop ke saath integrate hote hain

2. Express mein middleware kya hai aur kaise kaam karta hai?

Answer:
✔ Middleware functions request aur response object ke beech execute hote hain
✔ Logging, auth, validation, CORS handle karne ke liye use hote hain
Example:

app.use((req, res, next) => {
  console.log(req.method, req.url);
  next();
});

3. Error handling middleware Express mein kaise banate hain?

Answer:
✔ 4 parameters (err, req, res, next) use karte hain
Example:

app.use((err, req, res, next) => {
  console.error(err.stack);
  res.status(500).json({ message: 'Something went wrong!' });
});

4. CORS kya hai aur Express mein enable kaise karte hain?

Answer:
✔ CORS Cross-Origin requests allow/deny karta hai
✔ Express mein cors middleware se enable hota hai
Example:

const cors = require('cors');
app.use(cors({ origin: 'http://localhost:3000', credentials: true }));

➤ Environment & Configuration
5. dotenv ka use kyun karte hain aur kaise use hota hai?

Answer:
✔ Sensitive data (DB credentials, secret keys) environment variables mein rakhte hain
✔ .env file se load karte hain process.env ke through
Example:

require('dotenv').config();
const PORT = process.env.PORT || 5000;

6. nodemon ka use kyun karte hain?

Answer:
✔ Development ke liye file changes detect karke auto server restart karta hai
✔ Productivity improve karta hai

➤ Database (MySQL2 & Sequelize)
7. MySQL2 vs Sequelize differences?

Answer:
✔ MySQL2 – low-level driver, raw SQL queries run karte hain
✔ Sequelize – ORM, models aur associations provide karta hai, SQL abstraction deta hai
✔ Complex queries ke liye raw SQL aur Sequelize dono use ho sakte hain

8. Sequelize associations kaise define karte hain?

Answer:
✔ hasOne, hasMany, belongsTo, belongsToMany associations
Example:

User.hasMany(Post);
Post.belongsTo(User);

9. Transactions kaise implement karte hain Sequelize mein?

Answer:
✔ Multiple queries ek saath ya commit hote hain ya rollback hote hain
Example:

const t = await sequelize.transaction();
try {
  await User.create({ name: 'Ashish' }, { transaction: t });
  await Post.create({ title: 'Node.js' }, { transaction: t });
  await t.commit();
} catch(err) {
  await t.rollback();
}

10. Raw queries kaise execute karte hain Sequelize/MySQL2 mein?

Answer:
✔ sequelize.query() method
Example:

const [results] = await sequelize.query('SELECT * FROM Users WHERE id = ?', {
  replacements: [1]
});

➤ Authentication & Security
11. JWT authentication kaise kaam karta hai?

Answer:
✔ User login ke baad server token generate karta hai
✔ Token client ke paas store hota hai (localStorage/cookies)
✔ Requests mein token bhej kar server validate karta hai

Example:

const jwt = require('jsonwebtoken');
const token = jwt.sign({ id: user.id }, process.env.JWT_SECRET, { expiresIn: '1h' });

12. Password hashing bcryptjs se kaise karte hain?

Answer:
✔ Plain password ko hash karte hain before DB store
✔ Compare function se login verify karte hain

const bcrypt = require('bcryptjs');
const hash = await bcrypt.hash('mypassword', 10);
const isMatch = await bcrypt.compare('mypassword', hash);

13. Token expiration aur refresh token kaise implement karte hain?

Answer:
✔ Short-lived access token + long-lived refresh token
✔ Access token expire hone par refresh token se naya access token generate karte hain

➤ File Handling & Uploads
14. Multer ka use aur configuration kaise hota hai?

Answer:
✔ Multipart form data handle karta hai (file uploads)
✔ Disk storage ya memory storage define karte hain

const multer = require('multer');
const storage = multer.diskStorage({
  destination: (req, file, cb) => cb(null, 'uploads/'),
  filename: (req, file, cb) => cb(null, Date.now() + '-' + file.originalname)
});
const upload = multer({ storage });
app.post('/upload', upload.single('file'), (req, res) => res.send('File uploaded!'));

15. Multiple files ka upload kaise handle karte hain?

Answer:
✔ upload.array('files', maxCount) use karte hain
✔ req.files mein files available hoti hain

➤ Advanced & Complicated Backend Questions
16. API rate limiting kaise implement karte hain Express mein?

Answer:
✔ express-rate-limit middleware use karke
✔ DOS attacks aur abuse prevent karte hain
Example:

const rateLimit = require('express-rate-limit');
const limiter = rateLimit({ windowMs: 15*60*1000, max: 100 });
app.use('/api', limiter);

17. CORS, CSRF, XSS ko backend level pe kaise prevent karein?

Answer:
✔ CORS – origin restriction, credentials
✔ CSRF – token-based validation, same-origin policy
✔ XSS – input sanitization aur escaping

18. Sequelize hooks kya hote hain?

Answer:
✔ Model level callbacks – create, update, delete actions ke liye
✔ Pre/post actions execute karne ke liye
Example:

User.beforeCreate(async (user, options) => {
  user.password = await bcrypt.hash(user.password, 10);
});

19. Express.js mein streaming data kaise handle karte hain?

Answer:
✔ Large file uploads ya downloads ke liye streams use karte hain
✔ fs.createReadStream() aur res.pipe() ka use hota hai

20. Sequelize migration aur seeding ka use kyun hota hai?

Answer:
✔ DB structure maintain karne ke liye migrations
✔ Sample data populate karne ke liye seeders
✔ Version control aur team collaboration easy hoti hai

21. Environment-based config kaise manage karte hain?

Answer:
✔ .env files aur process.env.NODE_ENV use karte hain
✔ Development, staging aur production configs alag rakhte hain

22. JWT & role-based access kaise implement karte hain?

Answer:
✔ Middleware me token decode karte hain
✔ User roles check karke route access allow/deny karte hain
Example:

const authorize = roles => (req, res, next) => {
  const userRole = req.user.role;
  if(!roles.includes(userRole)) return res.status(403).json({ message: 'Forbidden' });
  next();
};

23. How do you handle database connection pooling in MySQL2/Sequelize?

Answer:
✔ Pool settings define karte hain, multiple requests efficiently handle hoti hain
Example:

const mysql = require('mysql2');
const pool = mysql.createPool({ host, user, password, database, waitForConnections: true, connectionLimit: 10 });

24. Error handling in async Express routes without try/catch

Answer:
✔ express-async-errors library use karte hain
✔ Async route mein errors automatically next middleware ko pass hote hain

25. Complex Query Handling in Sequelize

Answer:
✔ Nested include with associations
✔ Aggregations (COUNT, SUM)
✔ Transactions with multiple queries
Example:

const users = await User.findAll({
  include: [{ model: Post, where: { published: true } }],
  attributes: ['id', 'name'],
  order: [['createdAt', 'DESC']]
});

✅ Advanced Backend JS Interview Questions – Part 2
➤ Express & Routing Advanced Questions
26. What is router-level middleware in Express?

Answer:
✔ Middleware jo specific router ke liye apply hota hai
✔ Modular route handling aur cleaner code ke liye use hota hai
Example:

const router = require('express').Router();
router.use((req, res, next) => { console.log('Router middleware'); next(); });
router.get('/users', (req, res) => res.send('Users'));
app.use('/api', router);

27. What is the difference between app.use() and app.all()?

Answer:
✔ app.use() – middleware for all HTTP methods and path prefixes
✔ app.all() – specific route aur all HTTP methods ke liye
Example:

app.all('/admin', (req, res) => res.send('Admin access'));

28. How do you implement versioned API routes in Express?

Answer:
✔ Different router files for v1, v2
✔ /api/v1/users, /api/v2/users
Example:

app.use('/api/v1', require('./routes/v1'));
app.use('/api/v2', require('./routes/v2'));

29. How to handle 404 and undefined routes in Express?

Answer:
✔ Last middleware mein handle karte hain

app.use((req, res, next) => res.status(404).json({ message: 'Route not found' }));

➤ MySQL2 / Sequelize Advanced Questions
30. How do you prevent SQL injection in Node.js?

Answer:
✔ Prepared statements ya parameterized queries use karo
✔ Sequelize query replacements ya ORM features use karo
Example:

const [rows] = await sequelize.query('SELECT * FROM Users WHERE id = ?', { replacements: [id] });

31. What are scopes in Sequelize and why use them?

Answer:
✔ Predefined queries define karne ke liye
✔ Reusable filtering ya projection ke liye useful
Example:

User.addScope('active', { where: { status: 'active' } });
const activeUsers = await User.scope('active').findAll();

32. Sequelize hooks vs middleware differences?

Answer:
✔ Hooks – model level callbacks (beforeCreate, afterUpdate)
✔ Middleware – Express level request/response handling

33. How do you implement pagination in Sequelize?

Answer:
✔ limit aur offset use karte hain
Example:

const page = 2, size = 10;
const users = await User.findAll({ limit: size, offset: (page-1)*size });

34. Transactions with multiple models in Sequelize

Answer:
✔ Multiple queries atomic way mein run karte hain
✔ Commit ya rollback ke liye try/catch
Example:

const t = await sequelize.transaction();
try {
  const user = await User.create({ name: 'Ashish' }, { transaction: t });
  await Profile.create({ userId: user.id }, { transaction: t });
  await t.commit();
} catch(err) {
  await t.rollback();
}

➤ Authentication & Security Advanced
35. JWT token blacklisting / logout implementation

Answer:
✔ Token expire hone se pehle revoke karne ke liye blacklist store karte hain
✔ Redis ya DB mein revoked tokens store
✔ Middleware check karta hai token valid hai ya nahi

36. Password reset functionality flow

Answer:
✔ User requests reset → generate unique token → send email
✔ Token verify → update password → hash new password
✔ Token expiry handle karna

37. Role-based and permission-based access control

Answer:
✔ Middleware me user role check karte hain
✔ Example: Admin-only routes

const authorize = (roles) => (req, res, next) => {
  if(!roles.includes(req.user.role)) return res.status(403).json({ message: 'Forbidden' });
  next();
};

38. How to securely store environment variables in production?

Answer:
✔ .env file local development ke liye
✔ Production – cloud secrets manager ya encrypted config
✔ Avoid commit to git

➤ File Upload / Multer Advanced
39. Multiple file uploads with custom file filter

Answer:

const upload = multer({ 
  storage,
  fileFilter: (req, file, cb) => {
    if(file.mimetype.startsWith('image/')) cb(null, true);
    else cb(new Error('Only images allowed'), false);
  }
});
app.post('/upload', upload.array('photos', 5), (req, res) => res.send('Files uploaded'));

40. Handling large files / streaming uploads

Answer:
✔ Streams use karo instead of memory storage
✔ fs.createWriteStream() + piping
✔ Prevent server crash on huge file uploads

➤ Error Handling & Debugging Advanced
41. Async error handling without try/catch in Express

Answer:
✔ express-async-errors library
✔ Async routes automatically next middleware ko pass kare

42. Global error handling pattern in Node.js

Answer:
✔ process.on('unhandledRejection') aur process.on('uncaughtException') handle karo
✔ Server crash prevent aur logging maintain karo

43. Logging best practices

Answer:
✔ winston ya pino library use karo
✔ Level-wise logs (info, error, debug)
✔ Production logs rotate karne ke liye file transport ya cloud logging

➤ Advanced API Design / Real-World Scenarios
44. Rate-limiting, throttling & API abuse prevention

Answer:
✔ express-rate-limit ya Redis-based limiter
✔ Example: 100 requests / 15 minutes

45. Versioned APIs & backward compatibility

Answer:
✔ /api/v1/users vs /api/v2/users
✔ Clients v1 continue use kar sake aur new features v2 mein

46. Optimizing database queries for large tables

Answer:
✔ Indexing columns
✔ SELECT specific fields instead of SELECT *
✔ Use LIMIT + OFFSET / pagination
✔ Avoid N+1 queries, use Sequelize include efficiently

47. JWT refresh tokens & session management

Answer:
✔ Short-lived access token + long-lived refresh token
✔ Refresh token rotate karo, blacklist old ones
✔ Middleware verify token + check expiry

48. Sequelize eager loading vs lazy loading

Answer:
✔ Eager loading – related models fetch immediately (include)
✔ Lazy loading – fetch when required, reduces initial load

49. Handling CORS preflight (OPTIONS) requests

Answer:
✔ Browser preflight request pe server proper headers return kare
✔ cors() middleware Express mein automatically handle karta hai

50. Multer memory storage vs disk storage differences

Answer:
✔ Memory – file buffer in RAM, faster but risky for large files
✔ Disk – store files on disk, safer, slower
✔ Use case: memory – small images, disk – large files/videos

Node.js & Express Advanced Questions
51. Explain cluster module in Node.js. Why and how is it used?

Answer:
✔ Node.js single-threaded hota hai, cluster module multiple processes create kar ke CPU cores utilize karta hai
✔ Load balancing aur high availability ke liye useful
Example:

const cluster = require('cluster');
const numCPUs = require('os').cpus().length;

if(cluster.isMaster){
  for(let i=0;i<numCPUs;i++) cluster.fork();
  cluster.on('exit', (worker)=>console.log(`Worker ${worker.process.pid} died`));
}else{
  require('./app'); // server start
}

52. How to handle uncaught exceptions and unhandled promise rejections?

Answer:
✔ Prevent server crash and log errors

process.on('uncaughtException', err => console.error('Uncaught Exception:', err));
process.on('unhandledRejection', err => console.error('Unhandled Rejection:', err));

53. Explain middleware chaining and execution order

Answer:
✔ Express middleware sequentially execute hota hai
✔ next() call karke next middleware trigger hota hai
✔ Order important hai, e.g., auth middleware pehle aur error handling last

54. How do you secure Express APIs?

Answer:
✔ Helmet middleware for HTTP headers
✔ Rate limiting (express-rate-limit)
✔ CORS properly configure
✔ JWT & role-based auth
✔ Input validation (express-validator)

➤ Database & Sequelize Advanced
55. What is lazy loading and N+1 problem in Sequelize?

Answer:
✔ Lazy loading – associated data fetch tab hota hai jab access kiya jaye
✔ N+1 problem – loop me query multiple times run ho jaye
✔ Solution: eager loading (include)

56. How do you perform complex JOINs in Sequelize?

Answer:
✔ include ke saath where, attributes, nested includes
Example:

User.findAll({
  include: [{ model: Post, include: [Comment] }],
  where: { status: 'active' }
});

57. How to implement soft delete in Sequelize?

Answer:
✔ paranoid: true option model me use
✔ Records delete nahi hote, deletedAt timestamp set hota hai
Example:

const User = sequelize.define('User', { name: Sequelize.STRING }, { paranoid: true });
await User.destroy({ where: { id: 1 } }); // soft delete

58. Transactions across multiple models in Sequelize

✔ Already discussed but advanced: nested transactions, savepoints

const t = await sequelize.transaction();
try {
  await User.update(..., { transaction: t });
  await Profile.create(..., { transaction: t });
  await t.commit();
} catch(err) { await t.rollback(); }

59. Sequelize scopes for filtering & security

Answer:
✔ Predefined query logic
✔ Example: active users only

User.addScope('active', { where: { status: 'active' } });
const users = await User.scope('active').findAll();

60. Handling connection pool and performance optimization

✔ Pooling configure karna
✔ connectionLimit, acquireTimeout define karna
✔ Avoid unnecessary connections

➤ Authentication & Security Advanced
61. JWT refresh token rotation & invalidation

✔ Issue new refresh token on each use
✔ Blacklist old refresh tokens (Redis / DB)
✔ Prevent stolen token misuse

62. Role-based, permission-based, and field-level access control

✔ Middleware me role + permissions check
✔ Field-level: return only allowed fields based on user
Example:

const filteredUser = { name: user.name };
if(req.user.role === 'admin') filteredUser.email = user.email;

63. How do you prevent brute-force attacks?

✔ Rate-limiting login attempts
✔ Account lockout after N attempts
✔ CAPTCHA integration

64. Password reset flow secure implementation

✔ Unique token + expiry
✔ Send via email
✔ Hash token before storing in DB
✔ Verify token before password update

65. Two-factor authentication (2FA) in backend

✔ OTP generation + email/SMS delivery
✔ TOTP using libraries (speakeasy)
✔ Verify during login

➤ File Handling & Multer Advanced
66. File validation and sanitization

✔ Check MIME type, size limits
✔ Rename files to avoid conflicts / XSS
✔ Virus scanning (optional)

67. Streaming large files

✔ Use streams (fs.createReadStream())
✔ Avoid loading entire file in memory

68. Cloud storage integration (S3 / GCS)

✔ Multer storage engine for S3
✔ Store files directly in cloud instead of local

➤ Performance & Optimization
69. Caching strategies in Node.js backend

✔ In-memory cache (Redis / Node cache)
✔ Cache DB queries, frequent computations
✔ Cache headers for static files

70. API rate-limiting and throttling

✔ express-rate-limit or Redis-based throttler
✔ Protect critical endpoints

71. Database query optimization

✔ Indexing
✔ Avoid SELECT *
✔ Use joins wisely, batch inserts
✔ Pagination

72. Handling heavy computation in Node.js

✔ Worker threads or child processes
✔ Offload CPU-intensive tasks
✔ Avoid blocking event loop

73. Logging & monitoring best practices

✔ Winston, Pino
✔ Error level logs (info, warn, error)
✔ Rotate logs / send to centralized logging service

74. Environment separation

✔ .env files for dev
✔ Secrets manager / encrypted variables for production
✔ Use NODE_ENV for conditional configs

75. Common security vulnerabilities in Node.js

✔ SQL Injection → parameterized queries / ORM
✔ XSS → sanitize inputs, escape outputs
✔ CSRF → tokens / same-origin policies
✔ Sensitive data in responses → avoid leaking passwords / secrets


➤ Express & API Design Advanced
76. How do you structure a large Express project?

Answer:
✔ Modular folder structure:

/controllers
/models
/routes
/middleware
/config
/utils


✔ Separation of concerns, clean code, easier maintenance

77. REST API best practices

✔ Proper HTTP methods (GET, POST, PUT, DELETE)
✔ Use plural resource names (/users)
✔ Proper status codes (200, 201, 400, 401, 403, 404, 500)
✔ Pagination, filtering, sorting

78. Versioned APIs

✔ /api/v1/..., /api/v2/...
✔ Backward compatibility
✔ Easy client migration

79. Handling query parameters & validation

✔ express-validator library
✔ Validate body, params, query
Example:

const { body, validationResult } = require('express-validator');
app.post('/user', body('email').isEmail(), (req,res)=>{
  const errors = validationResult(req);
  if(!errors.isEmpty()) return res.status(400).json({ errors: errors.array() });
});

80. Rate limiting & throttling

✔ Protect endpoints from abuse
✔ express-rate-limit or Redis-based limiter
✔ Example: Login endpoint limit

➤ Authentication & Security
81. JWT access & refresh token flow

✔ Short-lived access token + long-lived refresh token
✔ Middleware verify access token
✔ Refresh token rotation & blacklist

82. Role-based & permission-based access

✔ Middleware check for roles and permissions
✔ Field-level access control
✔ Admin-only routes example

83. Password hashing & salting

✔ bcryptjs with salt rounds
✔ Compare during login
✔ Never store plain passwords

84. CSRF & XSS prevention

✔ CSRF tokens (csurf)
✔ Input sanitization (validator.js)
✔ Escape outputs in frontend

85. API security headers

✔ Helmet middleware
✔ Set HSTS, X-Frame-Options, Content-Security-Policy

86. CORS handling

✔ Allow specific origins, methods
✔ Preflight request handling
✔ Credentials support

➤ Database Advanced
87. Sequelize associations & eager loading

✔ hasMany, belongsTo, belongsToMany
✔ Nested include queries for performance
✔ Avoid N+1 problem

88. Sequelize scopes & soft delete

✔ paranoid: true for soft delete
✔ Predefined scopes for filtering

89. Transactions & nested transactions

✔ Multiple models atomic operations
✔ Commit / rollback with try/catch
✔ Savepoints for partial rollback

90. Database optimization

✔ Indexing for frequent queries
✔ Use pagination (limit + offset)
✔ Avoid SELECT *, fetch only needed fields

91. Raw queries & replacements

✔ Prevent SQL injection
✔ sequelize.query('SELECT * FROM Users WHERE id=?', { replacements: [id] })

92. Caching frequently accessed data

✔ Redis / in-memory cache
✔ Example: frequently queried users/products

93. Database connection pooling

✔ connectionLimit, waitForConnections, queueLimit
✔ Efficient multiple concurrent requests

➤ File Upload / Multer / Cloud
94. Single & multiple file upload

✔ upload.single() or upload.array()
✔ File filter by MIME type

95. Large file streaming

✔ fs.createReadStream() + res.pipe()
✔ Prevent memory overload

96. Cloud storage integration (S3 / GCS)

✔ Multer S3 storage engine
✔ Direct upload to cloud
✔ Store metadata in DB

97. File security & validation

✔ Check file type & size
✔ Rename files to prevent conflicts
✔ Optional virus scan

➤ Error Handling & Debugging
98. Global error handling pattern

✔ Central error middleware
✔ process.on('unhandledRejection') & uncaughtException
✔ Log errors properly

99. Async route error handling

✔ express-async-errors library
✔ Avoid repetitive try/catch

100. Logging & monitoring

✔ Winston / Pino logging library
✔ Separate logs by level
✔ Production monitoring (PM2, NewRelic, Sentry)

101. Debugging Node.js

✔ node --inspect or VSCode debugger
✔ Log stack traces, breakpoints
✔ Check async flow

➤ Advanced & Real-World Scenarios
102. API throttling for high traffic endpoints

✔ Limit requests per IP per timeframe
✔ Prevent abuse & server crash

103. Graceful shutdown

✔ Close DB connections & server
✔ Handle ongoing requests

process.on('SIGTERM', async () => {
  await sequelize.close();
  server.close(() => console.log('Server closed'));
});

104. Handling environment & config for multiple stages

✔ .env for dev
✔ Cloud secrets manager for production
✔ Conditional configs by NODE_ENV

105. WebSockets & real-time updates

✔ Socket.IO or ws library
✔ Push notifications, chat apps, real-time dashboards

106. Unit testing & integration testing

✔ Jest / Mocha / Chai
✔ Test routes, controllers, DB integration

107. API versioning & backward compatibility

✔ Clients using old API continue work
✔ New features in v2

108. Common security vulnerabilities

✔ SQL Injection → parameterized queries / ORM
✔ XSS → sanitize inputs
✔ CSRF → tokens / same-origin
✔ Sensitive data → never return passwords or secrets