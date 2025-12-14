# Shop Eazy

A simple e-commerce API built with Node.js and Express for managing products and users with authentication and file uploads.

## Features

- **User Management**: User registration, authentication, and authorization using JWT
- **Product Management**: Create, read, update, and delete products
- **File Uploads**: Upload product images using Cloudinary integration
- **Security**: Password hashing with bcrypt and security headers with Helmet
- **Validation**: Input validation using Joi
- **Logging**: HTTP request logging with Morgan and application logging with Winston
- **Error Handling**: Centralized error handling middleware
- **CORS**: Cross-Origin Resource Sharing enabled

## Prerequisites

- Node.js (v12 or higher)
- MongoDB
- Cloudinary account (for file uploads)

## Installation

1. Clone the repository
```bash
git clone <repository-url>
cd shop_eazy
```

2. Install dependencies
```bash
npm install
```

3. Create a `.env` file in the root directory with the following variables:
```env
PORT=3000
MONGODB_URI=<your-mongodb-connection-string>
JWT_SECRET=<your-jwt-secret>
CLOUDINARY_NAME=<your-cloudinary-name>
CLOUDINARY_API_KEY=<your-cloudinary-api-key>
CLOUDINARY_API_SECRET=<your-cloudinary-api-secret>
```

## Running the Application

### Development
```bash
npm run dev
```

The server will start on the configured PORT (default: 3000).

## API Endpoints

### User Routes
- `POST /auth/register` - Register a new user
- `POST /auth/login` - Login user
- `GET /user/:id` - Get user profile

### Product Routes
- `GET /api/v0/product` - Get all products
- `GET /api/v0/product/:id` - Get product by ID
- `POST /api/v0/product` - Create a new product
- `PUT /api/v0/product/:id` - Update a product
- `DELETE /api/v0/product/:id` - Delete a product

## Project Structure

```
shop_eazy/
├── src/
│   ├── app.js                 # Express app configuration
│   ├── index.js               # Application entry point
│   ├── config/
│   │   └── config.js          # Configuration settings
│   ├── controllers/           # Request handlers
│   │   ├── file.controller.js
│   │   ├── product.controller.js
│   │   └── user.controller.js
│   ├── database/
│   │   └── db.js              # MongoDB connection
│   ├── logging/
│   │   ├── httpLogger.js      # HTTP request logging
│   │   └── logger.js          # Application logger
│   ├── middlewares/
│   │   └── errorHandler.js    # Error handling middleware
│   ├── models/                # Database schemas
│   │   ├── product.model.js
│   │   └── user.model.js
│   ├── routes/                # API routes
│   │   ├── product.routes.js
│   │   └── user.routes.js
│   ├── uploads/               # Uploaded files directory
│   └── validators/            # Input validation schemas
│       ├── product.validator.js
│       └── user.validator.js
└── package.json
```

## Dependencies

- **express** - Web framework
- **mongoose** - MongoDB ODM
- **jsonwebtoken** - JWT authentication
- **bcrypt** - Password hashing
- **cloudinary** - File upload service
- **joi** - Data validation
- **helmet** - Security headers
- **cors** - Cross-origin resource sharing
- **morgan** - HTTP request logging
- **winston** - Application logging
- **multer** - File upload middleware
- **dotenv** - Environment variables

