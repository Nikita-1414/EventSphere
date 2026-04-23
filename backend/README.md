# EventSphere Backend

Node.js/Express backend API for EventSphere event management application.

## Features

- ✅ User authentication with JWT and OTP
- ✅ Event CRUD operations
- ✅ Booking management
- ✅ Email notifications
- ✅ Secure API endpoints with middleware
- ✅ MongoDB integration

## Tech Stack

- **Runtime**: Node.js
- **Framework**: Express.js
- **Database**: MongoDB
- **Authentication**: JWT (JSON Web Tokens)
- **Email**: Nodemailer
- **Environment**: dotenv

## Prerequisites

- Node.js (v14 or higher)
- MongoDB database
- npm or yarn
- Email service credentials (for OTP and confirmations)

## Installation

1. **Navigate to backend directory**
   ```bash
   cd backend
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Create .env file**
   ```bash
   cp .env.example .env
   ```

4. **Configure environment variables**
   ```
   MONGODB_URI=your_mongodb_connection_string
   JWT_SECRET=your_jwt_secret_key
   EMAIL_USER=your_email@gmail.com
   EMAIL_PASSWORD=your_app_password
   PORT=5000
   FRONTEND_URL=http://localhost:5173
   ```

5. **Initialize database (optional)**
   ```bash
   npm run seed
   ```

## Running the Application

### Development Mode
```bash
npm run dev
```
The server will start on `http://localhost:5000`

### Production Mode
```bash
npm start
```

## Project Structure

```
backend/
├── controllers/
│   ├── authController.js      # User authentication logic
│   ├── eventController.js     # Event CRUD operations
│   └── bookingController.js   # Booking management
├── models/
│   ├── User.js                # User schema
│   ├── Event.js               # Event schema
│   ├── Booking.js             # Booking schema
│   └── OTP.js                 # OTP schema
├── routes/
│   ├── auth.js                # Auth endpoints
│   ├── events.js              # Event endpoints
│   └── bookings.js            # Booking endpoints
├── middleware/
│   └── auth.js                # JWT authentication middleware
├── utils/
│   └── email.js               # Email service
├── server.js                  # Express app configuration
├── index.js                   # Entry point
└── seed.js                    # Database seeding
```

## API Endpoints

### Authentication Endpoints (`/api/auth`)
- `POST /register` - User registration
- `POST /login` - User login
- `POST /verify-otp` - OTP verification
- `POST /send-otp` - Send OTP to email

### Event Endpoints (`/api/events`)
- `GET /` - Get all events
- `GET /:id` - Get event details
- `POST /` - Create event (admin only)
- `PUT /:id` - Update event (admin only)
- `DELETE /:id` - Delete event (admin only)

### Booking Endpoints (`/api/bookings`)
- `GET /` - Get user bookings
- `POST /` - Create booking
- `GET /:id` - Get booking details
- `PUT /:id` - Update booking
- `DELETE /:id` - Cancel booking

## Database Models

### User
- Email (unique)
- Password (hashed)
- Profile information
- User type (admin/user)
- Bookings reference

### Event
- Title
- Description
- Date & Time
- Location
- Ticket price
- Available seats
- Admin reference

### Booking
- User reference
- Event reference
- Number of tickets
- Total amount
- Booking status
- Payment status

### OTP
- Email
- OTP code
- Expiration time

## Environment Variables

```
MONGODB_URI        - MongoDB connection string
JWT_SECRET         - Secret key for JWT signing
EMAIL_USER         - Gmail address for sending emails
EMAIL_PASSWORD     - Gmail app password
PORT               - Server port (default: 5000)
FRONTEND_URL       - Frontend application URL
```

## Middleware

### Authentication Middleware
Located in `middleware/auth.js`
- Validates JWT tokens
- Extracts user information
- Protects routes

## Error Handling

The API returns standard HTTP status codes:
- `200` - Success
- `201` - Created
- `400` - Bad Request
- `401` - Unauthorized
- `403` - Forbidden
- `404` - Not Found
- `500` - Server Error

## Security Features

- Password hashing with bcrypt
- JWT token-based authentication
- OTP verification for sensitive operations
- CORS configuration
- Input validation
- Error handling

## Contributing

1. Create a feature branch
2. Make your changes
3. Test thoroughly
4. Submit a pull request

## Troubleshooting

### MongoDB Connection Issues
- Ensure MongoDB is running
- Check MONGODB_URI in .env
- Verify network connectivity

### Email Not Sending
- Enable "Less secure app access" for Gmail
- Use app-specific passwords
- Check email credentials in .env

### JWT Errors
- Verify JWT_SECRET is set
- Check token expiration
- Ensure token is sent in Authorization header

## License

MIT License

---

For more information, see the [main README](../README.md)
