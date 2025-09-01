# Admin Manager Employee Portal

A comprehensive Node.js application for managing Admin, Manager, and Employee roles with authentication, authorization, and email notifications.

## Features

### Admin Features
1. Admin Registration (Username, Email, Phone, Password, Image)
2. Admin Login (Username or Email & Password)
3. Profile Management (Show Own Details) - Admin Token Required
4. Change Password - Admin Token Required
5. Forgot Password - No Token Required
6. Add Manager Detail (Registration + Email Notification) - Admin Token Required
7. View All Managers Data - Admin Token Required
8. Manager Delete/Activate/Deactivate - Admin Token Required
9. View All Employees - Admin Token Required
10. Employee Delete/Activate/Deactivate - Admin Token Required

### Manager Features
1. Manager Login
2. Profile Management (Show Manager Details) - Manager Token Required
3. Change Password - Manager Token Required
4. Forgot Password - No Token Required
5. Add Employee (Registration + Email Notification) - Manager Token Required
6. View All Employees under Management - Manager Token Required

### Employee Features
1. Employee Login
2. Profile Management (Show Employee Details) - Employee Token Required
3. Change Password - Employee Token Required
4. Forgot Password - No Token Required

## Tech Stack

- **Backend**: Node.js, Express.js
- **Database**: MongoDB with Mongoose
- **Authentication**: Passport.js, JWT (JSON Web Tokens)
- **File Upload**: Multer
- **Email**: Nodemailer
- **View Engine**: EJS
- **Validation**: Express-validator
- **Password Hashing**: bcryptjs
- **Development**: Nodemon

## Installation

1. Clone the repository or navigate to the project directory
2. Install dependencies:
   ```bash
   npm install
   ```

3. Create a `.env` file in the root directory with the following variables:
   ```env
   PORT=3000
   NODE_ENV=development
   MONGODB_URI=mongodb://localhost:27017/admin_manager_employee_portal
   JWT_SECRET=your-super-secret-jwt-key-change-this-in-production
   SESSION_SECRET=your-super-secret-session-key-change-this-in-production
   EMAIL_USER=your-email@gmail.com
   EMAIL_PASS=your-app-password
   PORTAL_URL=http://localhost:3000
   ```

4. Make sure MongoDB is running on your system

5. Start the development server:
   ```bash
   npm run dev
   ```

## API Endpoints

### Admin Endpoints
- `POST /api/admin/register` - Admin Registration
- `POST /api/admin/login` - Admin Login
- `GET /api/admin/profile` - Get Admin Profile (Token Required)
- `PUT /api/admin/change-password` - Change Password (Token Required)
- `POST /api/admin/forgot-password` - Forgot Password
- `POST /api/admin/add-manager` - Add Manager (Token Required)
- `GET /api/admin/managers` - Get All Managers (Token Required)
- `PUT /api/admin/manager/:id/toggle-status` - Toggle Manager Status (Token Required)
- `GET /api/admin/employees` - Get All Employees (Token Required)
- `PUT /api/admin/employee/:id/toggle-status` - Toggle Employee Status (Token Required)

### Manager Endpoints
- `POST /api/manager/login` - Manager Login
- `GET /api/manager/profile` - Get Manager Profile (Token Required)
- `PUT /api/manager/change-password` - Change Password (Token Required)
- `POST /api/manager/forgot-password` - Forgot Password
- `POST /api/manager/add-employee` - Add Employee (Token Required)
- `GET /api/manager/employees` - Get Manager's Employees (Token Required)
- `PUT /api/manager/employee/:id/toggle-status` - Toggle Employee Status (Token Required)
- `GET /api/manager/stats` - Get Manager Statistics (Token Required)

### Employee Endpoints
- `POST /api/employee/login` - Employee Login
- `GET /api/employee/profile` - Get Employee Profile (Token Required)
- `PUT /api/employee/change-password` - Change Password (Token Required)
- `POST /api/employee/forgot-password` - Forgot Password
- `GET /api/employee/dashboard` - Get Employee Dashboard (Token Required)
- `PUT /api/employee/update-profile` - Update Employee Profile (Token Required)

## Authentication

The application uses JWT (JSON Web Tokens) for authentication. Include the token in the Authorization header:

```
Authorization: Bearer <your-jwt-token>
```

## File Upload

Profile images can be uploaded during registration. Supported formats: JPG, JPEG, PNG, GIF (Max size: 5MB)

## Email Configuration

Update the `.env` file with your email credentials:
- For Gmail, use App Passwords instead of your regular password
- Enable 2-factor authentication and generate an app password

## Testing with Postman

1. Import the provided Postman collection (if available)
2. Set up environment variables for base URL and tokens
3. Test all endpoints systematically
4. Verify email functionality

## Project Structure

```
├── config/
│   ├── database.js      # MongoDB connection
│   └── passport.js      # Passport strategies
├── middleware/
│   ├── auth.js          # Authentication middleware
│   └── upload.js        # File upload middleware
├── models/
│   ├── Admin.js         # Admin model
│   ├── Manager.js       # Manager model
│   └── Employee.js      # Employee model
├── routes/
│   ├── admin.js         # Admin routes
│   ├── manager.js       # Manager routes
│   └── employee.js      # Employee routes
├── utils/
│   └── email.js         # Email utility functions
├── views/
│   └── index.ejs        # Home page template
├── uploads/             # Uploaded files directory
├── .env                 # Environment variables
├── package.json         # Dependencies and scripts
├── server.js            # Main server file
└── README.md           # This file
```

## Security Features

- Password hashing with bcryptjs
- JWT token authentication
- Input validation with express-validator
- File upload restrictions
- CORS enabled
- Session management
- Password reset functionality

## Development

- Use `npm run dev` for development with nodemon
- Use `npm start` for production

## License

ISC License
