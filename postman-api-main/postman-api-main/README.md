 <h1>Admin–Manager–Employee Portal</h1>
    <p>A robust <strong>Node.js</strong> application to manage Admin, Manager, and Employee roles with secure authentication, role-based authorization, and automated email notifications.</p>

 <div class="card">
      <strong>Highlights:</strong>
      <span class="tag">Node.js</span>
      <span class="tag">Express</span>
      <span class="tag">MongoDB</span>
      <span class="tag">JWT</span>
      <span class="tag">Passport</span>
      <span class="tag">Multer</span>
      <span class="tag">Nodemailer</span>
      <span class="tag">EJS</span>
      <span class="tag">express-validator</span>
      <span class="tag">bcryptjs</span>
      <span class="tag">Nodemon</span>
    </div>

 <h2>Capabilities</h2>
    <div class="grid cols-2">
      <div class="card">
        <h3>Admin</h3>
        <ul class="list-tight">
          <li>Register admin (username, email, phone, password, image)</li>
          <li>Login with username/email + password</li>
          <li>View own profile (JWT)</li>
          <li>Change password (JWT)</li>
          <li>Forgot/reset password (no token)</li>
          <li>Add manager + email notification (JWT)</li>
          <li>List all managers (JWT)</li>
          <li>Activate / Deactivate / Delete managers (JWT)</li>
          <li>List all employees (JWT)</li>
          <li>Activate / Deactivate / Delete employees (JWT)</li>
        </ul>
      </div>
      <div class="card">
        <h3>Manager</h3>
        <ul class="list-tight">
          <li>Login</li>
          <li>View own profile (JWT)</li>
          <li>Change password (JWT)</li>
          <li>Forgot/reset password (no token)</li>
          <li>Add employee + email notification (JWT)</li>
          <li>View employees under management (JWT)</li>
          <li>Toggle employee status (JWT)</li>
        </ul>
      </div>
      <div class="card">
        <h3>Employee</h3>
        <ul class="list-tight">
          <li>Login</li>
          <li>View own profile (JWT)</li>
          <li>Change password (JWT)</li>
          <li>Forgot/reset password (no token)</li>
          <li>Update profile (JWT)</li>
          <li>Access dashboard (JWT)</li>
        </ul>
      </div>
      <div class="card">
        <h3>Security</h3>
        <ul class="list-tight">
          <li><strong>bcryptjs</strong> password hashing</li>
          <li><strong>JWT</strong> for protected routes</li>
          <li>Input validation with <strong>express-validator</strong></li>
          <li>File type/size checks via <strong>Multer</strong></li>
          <li>Session management & password reset flow</li>
          <li>CORS enabled</li>
        </ul>
      </div>
    </div>
    <h2>Tech Stack</h2>
    <ul>
      <li><strong>Backend:</strong> Node.js, Express.js</li>
      <li><strong>Database:</strong> MongoDB with Mongoose</li>
      <li><strong>Auth:</strong> Passport.js + JWT</li>
      <li><strong>Uploads:</strong> Multer</li>
      <li><strong>Email:</strong> Nodemailer</li>
      <li><strong>Views:</strong> EJS</li>
      <li><strong>Validation:</strong> express-validator</li>
      <li><strong>Security:</strong> bcryptjs</li>
      <li><strong>Dev:</strong> Nodemon</li>
    </ul>

 <h2>Installation</h2>
    <ol>
      <li><strong>Clone</strong> the repository:
        <pre><code>git clone &lt;your-repo-url&gt;
cd admin-manager-employee-portal</code></pre>
      </li>
      <li><strong>Install</strong> dependencies:
        <pre><code>npm install</code></pre>
      </li>
      <li><strong>Configure</strong> environment variables in <code>.env</code>:
        <pre><code>PORT=8000
MONGODB_URI=mongodb://127.0.0.1:27017/role_portal
JWT_SECRET=your-strong-jwt-secret
SESSION_SECRET=your-session-secret
EMAIL_USER=your-email@gmail.com
EMAIL_PASS=your-app-password
BASE_URL=http://localhost:8000</code></pre>
      </li>
      <li>Ensure <strong>MongoDB</strong> is running locally.</li>
      <li><strong>Start</strong> the server:
        <pre><code># Development
npm run dev

# Production
npm start</code></pre>
      </li>
    </ol>

 <h2>Authentication</h2>
    <p>Protected requests require a valid JWT in the <code>Authorization</code> header:</p>
    <pre><code>Authorization: Bearer &lt;your-jwt-token&gt;</code></pre>

 <h2>File Uploads</h2>
    <ul>
      <li>Accepted: <strong>JPG, JPEG, PNG, GIF</strong></li>
      <li>Max size: <strong>5&nbsp;MB</strong></li>
      <li>Stored in: <code>/uploads</code></li>
    </ul>

 <h2>Email Configuration</h2>
    <p class="note">For Gmail, enable 2-Step Verification and create an <em>App Password</em>. Use that app password in <code>EMAIL_PASS</code>.</p>

  <h2>API Endpoints</h2>

  <h3>Admin</h3>
    <ul>
      <li><code>POST /api/admin/register</code> — Register admin</li>
      <li><code>POST /api/admin/login</code> — Login</li>
      <li><code>GET /api/admin/profile</code> — Get profile (JWT)</li>
      <li><code>PUT /api/admin/change-password</code> — Change password (JWT)</li>
      <li><code>POST /api/admin/forgot-password</code> — Forgot password</li>
      <li><code>POST /api/admin/add-manager</code> — Create manager (JWT)</li>
      <li><code>GET /api/admin/managers</code> — List managers (JWT)</li>
      <li><code>PUT /api/admin/manager/:id/toggle-status</code> — Toggle manager status (JWT)</li>
      <li><code>GET /api/admin/employees</code> — List employees (JWT)</li>
      <li><code>PUT /api/admin/employee/:id/toggle-status</code> — Toggle employee status (JWT)</li>
    </ul>

   <h3>Manager</h3>
  <ul>
      <li><code>POST /api/manager/login</code> — Login</li>
      <li><code>GET /api/manager/profile</code> — Get profile (JWT)</li>
      <li><code>PUT /api/manager/change-password</code> — Change password (JWT)</li>
      <li><code>POST /api/manager/forgot-password</code> — Forgot password</li>
      <li><code>POST /api/manager/add-employee</code> — Add employee (JWT)</li>
      <li><code>GET /api/manager/employees</code> — Employees under manager (JWT)</li>
      <li><code>PUT /api/manager/employee/:id/toggle-status</code> — Toggle employee status (JWT)</li>
    </ul>

 <h3>Employee</h3>
    <ul>
      <li><code>POST /api/employee/login</code> — Login</li>
      <li><code>GET /api/employee/profile</code> — Get profile (JWT)</li>
      <li><code>PUT /api/employee/change-password</code> — Change password (JWT)</li>
      <li><code>POST /api/employee/forgot-password</code> — Forgot password</li>
      <li><code>PUT /api/employee/update-profile</code> — Update profile (JWT)</li>
      <li><code>GET /api/employee/dashboard</code> — Dashboard (JWT)</li>
    </ul>

 <h2>Project Structure</h2>
    <pre><code>├── config/
│   ├── database.js       # MongoDB connection
│   └── passport.js       # Passport strategies
├── middleware/
│   ├── auth.js           # JWT verification
│   └── upload.js         # Multer config
├── models/
│   ├── Admin.js
│   ├── Manager.js
│   └── Employee.js
├── routes/
│   ├── admin.js
│   ├── manager.js
│   └── employee.js
├── utils/
│   └── email.js          # Email helper
├── views/
│   └── index.ejs
├── uploads/
├── .env
├── package.json
├── server.js
└── README.html</code></pre>

   <h2>Testing with Postman</h2>
    <ol>
      <li>Import the collection (if provided).</li>
      <li>Define environment variables for <code>baseUrl</code> and tokens.</li>
      <li>Exercise endpoints in order (auth → CRUD → status toggles).</li>
      <li>Verify email and password reset flows.</li>
    </ol>
    <h2>Development</h2>
    <ul>
      <li><kbd class="kbd">npm run dev</kbd> for development (nodemon)</li>
      <li><kbd class="kbd">npm start</kbd> for production</li>
    </ul>

