# EventHub - Event Booking System

A modern, full-stack event booking platform built with React, TypeScript, and Node.js. EventHub allows users to discover and book events while providing administrators with powerful event management capabilities.

![EventHub Screenshot](https://images.pexels.com/photos/2747449/pexels-photo-2747449.jpeg)

## 🌟 Features

### For Users
- Browse and search events by title, description, or venue
- Filter events by category
- View detailed event information
- Book event tickets
- Track booking history
- User authentication (register/login)

### For Administrators
- Comprehensive event management
- Create, edit, and delete events
- View all events in an organized dashboard
- Secure admin-only access

## 🛠 Tech Stack

### Frontend
- React 18
- TypeScript
- React Router for navigation
- React Hook Form for form management
- Zod for form validation
- Tailwind CSS for styling
- Lucide React for icons
- Axios for API requests

### Backend
- Node.js
- Express.js
- SQLite database
- JWT for authentication
- bcrypt for password hashing

## 🚀 Getting Started

### Prerequisites
- Node.js (v14 or later)
- npm or yarn

### Installation

1. Clone the repository
```bash
git clone https://github.com/your-username/eventhub.git
cd eventhub
```

2. Install dependencies
```bash
npm install
```

3. Create a `.env` file in the root directory with the following variables:
```env
VITE_API_URL=http://localhost:5000
JWT_SECRET=your_jwt_secret
```

4. Start the development servers

In one terminal, start the backend server:
```bash
npm run server
```

In another terminal, start the frontend development server:
```bash
npm run dev
```

5. Access the application
- Frontend: http://localhost:5173
- Backend API: http://localhost:5000

## 📝 API Documentation

### Authentication Endpoints

#### Register User
```http
POST /api/auth/register
Content-Type: application/json

{
  "name": "string",
  "email": "string",
  "password": "string"
}
```

#### Login User
```http
POST /api/auth/login
Content-Type: application/json

{
  "email": "string",
  "password": "string"
}
```

### Event Endpoints

#### Get All Events
```http
GET /api/events
```

#### Get Single Event
```http
GET /api/events/:id
```

#### Create Event (Admin only)
```http
POST /api/events
Authorization: Bearer <token>
Content-Type: application/json

{
  "title": "string",
  "description": "string",
  "category": "string",
  "date": "string",
  "venue": "string",
  "price": number,
  "image": "string"
}
```

#### Update Event (Admin only)
```http
PUT /api/events/:id
Authorization: Bearer <token>
Content-Type: application/json

{
  "title": "string",
  "description": "string",
  "category": "string",
  "date": "string",
  "venue": "string",
  "price": number,
  "image": "string"
}
```

#### Delete Event (Admin only)
```http
DELETE /api/events/:id
Authorization: Bearer <token>
```

### Booking Endpoints

#### Get User Bookings
```http
GET /api/bookings
Authorization: Bearer <token>
```

#### Create Booking
```http
POST /api/bookings
Authorization: Bearer <token>
Content-Type: application/json

{
  "eventId": number
}
```

## 👥 Default Admin Account
- Email: admin@example.com
- Password: admin123

## 📁 Project Structure
```
├── public/             # Static files
├── server/            # Backend code
│   └── index.js      # Express server
├── src/              # Frontend code
│   ├── components/   # Reusable components
│   ├── context/     # React context providers
│   ├── pages/       # App pages
│   └── main.tsx     # Entry point
├── .env             # Environment variables
└── package.json     # Dependencies and scripts
```

## 🔒 Security Features
- JWT-based authentication
- Password hashing with bcrypt
- Role-based access control
- Protected API endpoints
- Secure HTTP-only cookies

## 🤝 Contributing
1. Fork the repository
2. Create a new branch
3. Make your changes
4. Submit a pull request

## 📄 License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.