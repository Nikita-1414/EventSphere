# EventSphere Frontend

React frontend application for EventSphere event management and booking platform.

## Features

- 🎨 Modern, responsive UI with Tailwind CSS
- 🔐 Secure user authentication
- 📅 Browse and search events
- 🎟️ Book events and manage bookings
- 💳 Payment integration
- 📱 Mobile-friendly design
- 🎯 Admin dashboard for event management
- 🔄 Real-time state management with Context API

## Tech Stack

- **Framework**: React 18+
- **Build Tool**: Vite
- **Styling**: Tailwind CSS
- **HTTP Client**: Axios
- **State Management**: React Context API

## Prerequisites

- Node.js (v14 or higher)
- npm or yarn
- Backend API running on localhost:5000

## Installation

1. **Navigate to frontend directory**
   ```bash
   cd frontend
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
   VITE_API_BASE_URL=http://localhost:5000/api
   VITE_APP_NAME=EventSphere
   ```

## Running the Application

### Development Mode
```bash
npm run dev
```
The application will start on `http://localhost:5173`

### Build for Production
```bash
npm run build
```

### Preview Production Build
```bash
npm run preview
```

## Project Structure

```
frontend/
├── src/
│   ├── components/
│   │   └── Navbar.jsx         # Navigation component
│   ├── pages/
│   │   ├── Home.jsx           # Home page
│   │   ├── Login.jsx          # Login page
│   │   ├── Register.jsx       # Registration page
│   │   ├── EventDetail.jsx    # Event details page
│   │   ├── UserDashboard.jsx  # User booking dashboard
│   │   ├── AdminDashboard.jsx # Admin management dashboard
│   │   ├── PaymentSuccess.jsx # Payment success page
│   │   └── PaymentFailed.jsx  # Payment failed page
│   ├── context/
│   │   └── AuthContext.jsx    # Authentication context
│   ├── utils/
│   │   └── axios.js           # Axios instance configuration
│   ├── App.jsx                # Main app component
│   ├── main.jsx               # Entry point
│   └── index.css              # Global styles
├── index.html                 # HTML template
├── vite.config.js             # Vite configuration
├── tailwind.config.js         # Tailwind configuration
├── postcss.config.js          # PostCSS configuration
└── package.json               # Dependencies
```

## Pages Overview

### Home Page
- Display all available events
- Search and filter events
- Quick booking options

### Login Page
- User login with email and password
- OTP verification
- "Remember me" functionality

### Register Page
- New user registration
- Email verification
- Password strength validation

### Event Detail Page
- Full event information
- Event description and schedule
- Seat selection
- Booking form

### User Dashboard
- View all user bookings
- Booking status
- Cancel bookings
- Download tickets

### Admin Dashboard
- Create new events
- Edit existing events
- Delete events
- View bookings
- Manage users

### Payment Pages
- Payment success confirmation
- Payment failure handling
- Order receipt

## Authentication Flow

1. User registers or logs in
2. OTP is sent to email
3. OTP is verified
4. JWT token is stored in localStorage
5. Token is sent in API requests
6. Context API manages auth state

## Components

### Navbar
- Navigation links
- User profile menu
- Admin panel link (for admins)
- Logout functionality

### axios.js
- Axios instance with base URL
- Automatic token injection
- Request/response interceptors
- Error handling

## State Management

Uses React Context API for:
- User authentication state
- Current user information
- Auth token management

## Environment Variables

```
VITE_API_BASE_URL  - Backend API base URL
VITE_APP_NAME      - Application name
```

## Styling

- **Tailwind CSS** for utility-first styling
- Responsive breakpoints for mobile, tablet, desktop
- Custom color scheme
- Consistent spacing and design system

## Development Workflow

1. Create feature branch
2. Modify components/pages
3. Test in development mode
4. Build and verify production build
5. Submit pull request

## Common Tasks

### Adding a New Page
```jsx
// pages/NewPage.jsx
export default function NewPage() {
  return (
    <div>
      {/* Page content */}
    </div>
  );
}
```

### Using Authentication Context
```jsx
import { useAuth } from '../context/AuthContext';

export default function MyComponent() {
  const { user, login, logout } = useAuth();
  // Use auth context
}
```

### Making API Calls
```jsx
import axios from '../utils/axios';

// API calls automatically include auth token
axios.get('/events')
  .then(res => console.log(res.data))
  .catch(err => console.error(err));
```

## Debugging

### Debug Mode
Add `?debug=true` to URL to enable console logging

### Browser DevTools
- React Developer Tools extension
- Network tab for API calls
- Console for errors

## Performance Tips

- Use React.memo for expensive components
- Implement code splitting for routes
- Optimize images
- Use lazy loading for components

## Troubleshooting

### API Connection Issues
- Verify backend is running on port 5000
- Check VITE_API_BASE_URL in .env
- Check browser console for CORS errors

### Authentication Issues
- Clear localStorage
- Verify JWT token is valid
- Check token expiration

### Build Issues
- Clear node_modules and reinstall
- Clear Vite cache: `rm -rf .vite`
- Check Node.js version compatibility

## Contributing

1. Create a feature branch
2. Make your changes
3. Test thoroughly in development
4. Build and verify production build
5. Submit a pull request

## License

MIT License

---

For more information, see the [main README](../README.md) and [Backend README](../backend/README.md)
