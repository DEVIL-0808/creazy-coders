# 🌌 Cosmic Watch: Real-Time NEO Monitoring Platform

A full-stack web platform for monitoring Near-Earth Objects (NEOs) with real-time data from NASA, risk analysis, user authentication, and interactive 3D visualizations.

## 🚀 Features

- **Real-Time Data Feed**: Integration with NASA NeoWs API for live asteroid tracking
- **Risk Analysis Engine**: Intelligent categorization of asteroids by hazard level and proximity
- **User Authentication**: Secure login system with role-based access (users and admins)
- **Interactive Dashboard**: Comprehensive monitoring interface with asteroid details
- **3D Visualization**: Orbital visualization using Three.js (planned feature)
- **Real-Time Chat**: Community discussion threads for specific asteroids (planned feature)
- **Alert System**: Customizable notifications for asteroid approaches
- **Admin Panel**: User management and system administration
- **Containerized Deployment**: Docker and docker-compose setup for easy deployment

## 🛠️ Technology Stack

### Backend
- **Node.js** with Express.js
- **MongoDB** for data storage
- **JWT** for authentication
- **Socket.io** for real-time features
- **NASA NeoWs API** integration

### Frontend
- **React** with Material-UI
- **Three.js** for 3D visualizations
- **Axios** for API communication
- **Socket.io-client** for real-time chat

### DevOps
- **Docker** & **Docker Compose**
- **Nginx** reverse proxy
- **Postman** API documentation

## 📁 Project Structure

```
cosmic-watch/
├── backend/                 # Node.js/Express API server
│   ├── models/             # MongoDB schemas
│   ├── routes/             # API endpoints
│   ├── services/           # Business logic (NASA API)
│   ├── middleware/         # Authentication middleware
│   └── server.js           # Main server file
├── frontend/               # React application
│   ├── public/            # Static assets
│   ├── src/
│   │   ├── components/    # React components
│   │   ├── contexts/      # React context providers
│   │   └── App.js         # Main app component
├── database/              # Database initialization
├── docs/                  # Documentation
├── Dockerfile.backend     # Backend container config
├── Dockerfile.frontend    # Frontend container config
├── docker-compose.yml     # Multi-container orchestration
├── nginx.conf            # Reverse proxy configuration
└── README.md             # This file
```

## 🚀 Quick Start

### Prerequisites
- Docker and Docker Compose
- Node.js 18+ (for local development)
- MongoDB (handled by Docker)

### Development Setup

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd cosmic-watch
   ```

2. **Start with Docker Compose**
   ```bash
   docker-compose up --build
   ```

3. **Access the application**
   - Frontend: http://localhost:3000
   - Backend API: http://localhost:5000
   - API Documentation: Import `docs/CosmicWatch_API.postman_collection.json` into Postman

### Local Development

1. **Backend Setup**
   ```bash
   cd backend
   npm install
   npm run dev
   ```

2. **Frontend Setup**
   ```bash
   cd frontend
   npm install
   npm start
   ```

3. **Database**
   - MongoDB runs in Docker container
   - Initial data is seeded automatically

## 🔧 Configuration

### Environment Variables

Create `.env` file in the backend directory:

```env
NODE_ENV=development
MONGODB_URI=mongodb://localhost:27017/cosmic-watch
JWT_SECRET=your-super-secret-jwt-key
NASA_API_KEY=your-nasa-api-key
PORT=5000
```

### NASA API Key

1. Get your API key from [NASA API Portal](https://api.nasa.gov/)
2. Replace `DEMO_KEY` in environment variables

## 📚 API Documentation

The API is fully documented using Postman. Import the collection from `docs/CosmicWatch_API.postman_collection.json`.

### Key Endpoints

- `POST /api/auth/register` - User registration
- `POST /api/auth/login` - User authentication
- `GET /api/asteroids` - Get all asteroids
- `POST /api/asteroids/sync` - Sync NASA data
- `GET /api/alerts` - Get user alerts
- `GET /api/users` - Admin: Get all users

## 🎨 UI/UX Design

- **Space Theme**: Dark cosmic color scheme with cyan/blue accents
- **Material Design**: Clean, modern interface using Material-UI
- **Responsive**: Mobile-friendly design
- **Accessibility**: WCAG compliant components

## 🔒 Security Features

- JWT-based authentication
- Password hashing with bcrypt
- CORS protection
- Input validation and sanitization
- Role-based access control

## 🚀 Deployment

### Production Deployment

1. **Build and deploy**
   ```bash
   docker-compose -f docker-compose.yml up -d
   ```

2. **Scale services**
   ```bash
   docker-compose up -d --scale backend=3
   ```

3. **Update application**
   ```bash
   docker-compose build --no-cache
   docker-compose up -d
   ```

### Environment Setup

- Set production environment variables
- Configure MongoDB replica set for production
- Set up SSL certificates for HTTPS
- Configure nginx for production optimizations

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🙏 Acknowledgments

- NASA for providing the NeoWs API
- Material-UI for the component library
- Three.js community for 3D visualization tools

## 📞 Support

For support, email support@cosmicwatch.com or create an issue in the repository.

---

**🌍 Making space exploration accessible to everyone, one asteroid at a time.**
