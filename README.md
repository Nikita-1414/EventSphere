# EventSphere 

A full-stack web application for event management and booking. Users can browse events, book tickets, make payments, and manage their bookings. Admins can create and manage events with a dedicated dashboard.

## Features

- 🎟️ **Event Discovery** - Browse and search for events
- 📅 **Event Booking** - Easy ticket booking with seat selection
- 💳 **Payment Integration** - Secure payment processing
- 👥 **User Authentication** - Secure login and registration with OTP verification
- 📊 **Admin Dashboard** - Complete event management system
- 📱 **Responsive Design** - Works on all devices
- 📧 **Email Notifications** - Booking confirmations and OTP via email

## Tech Stack

### Frontend
- **Framework**: React + Vite
- **Styling**: Tailwind CSS
- **HTTP Client**: Axios
- **State Management**: React Context API

### Backend
- **Runtime**: Node.js
- **Framework**: Express.js
- **Database**: MongoDB
- **Authentication**: JWT with OTP

## Project Structure

```
EventSphere/
├── frontend/          # React frontend application
├── backend/           # Node.js/Express backend API
└── README.md          # This file
```

## Getting Started

### Prerequisites
- Node.js (v14 or higher)
- MongoDB
- npm or yarn

### Installation & Setup

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd EventSphere
   ```

2. **Backend Setup**
   See [Backend README](./backend/README.md) for detailed instructions

3. **Frontend Setup**
   See [Frontend README](./frontend/README.md) for detailed instructions

## Documentation

- [Backend Documentation](./backend/README.md)
- [Frontend Documentation](./frontend/README.md)

## API Endpoints

The backend provides RESTful API endpoints for:
- Authentication (Register, Login, OTP verification)
- Events (CRUD operations)
- Bookings (Create, view, manage bookings)

See backend README for complete API documentation.

## Contributing

Contributions are welcome! Please follow these steps:
1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Support

For support, email support@eventsphere.com or open an issue on GitHub.

---

**Happy Event Booking! 🎉**
