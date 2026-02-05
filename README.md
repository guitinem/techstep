# Shopping Cart Application

A full-stack e-commerce shopping cart application built with React, Node.js, Express, and MongoDB.

## Prerequisites

- **Node.js** (v14 or higher)
- **MongoDB** (local installation required)
- **npm** or **yarn**

## MongoDB Installation

### macOS
```bash
brew tap mongodb/brew
brew install mongodb-community
brew services start mongodb-community
```

### Windows
Download and install from [MongoDB Official Website](https://www.mongodb.com/try/download/community)

### Linux (Ubuntu/Debian)
```bash
sudo apt-get install mongodb
sudo systemctl start mongodb
```

Verify MongoDB is running:
```bash
mongosh
```

## Installation

1. **Install frontend dependencies**
```bash
npm install
```

2. **Install backend dependencies**
```bash
cd server
npm install
cd ..
```

## Environment Setup

1. **Create `.env` file in root directory:**
```env
VITE_SERVER_URL=http://localhost:3001
```

2. **Create `.env` file in `server/` directory:**
```env
MONGO_URI=mongodb://127.0.0.1:27017/techstep
JWT_SECRET=your_jwt_secret_key_here
ORIGIN=http://localhost:5173
STRIPE_KEY=your_stripe_secret_key_here
```

## Running the Application

```bash
npm run dev
```


## Access the Application

- **Frontend:** http://localhost:5173
- **Backend API:** http://localhost:3001

## Features

- User authentication (Register/Login)
- Product browsing and search
- Shopping cart management
- **BuyALL feature** - Purchase all cart items with confirmation modal
- Stripe checkout integration
- Responsive design

## Tech Stack

**Frontend:**
- React
- Redux Toolkit
- React Router
- Tailwind CSS
- Vite

**Backend:**
- Node.js
- Express
- MongoDB
- JWT Authentication
- Stripe

## Project Structure

```
techstep/
├── src/                 # Frontend source files
│   ├── components/      # React components
│   ├── pages/          # Page components
│   ├── app/            # Redux store and slices
│   └── helpers/        # Utility functions
├── server/             # Backend source files
│   ├── controllers/    # Route controllers
│   ├── models/         # MongoDB models
│   ├── routes/         # API routes
│   ├── middlewares/    # Custom middlewares
│   └── config/         # Configuration files
└── public/             # Static assets
```

## API Endpoints

### Authentication
- `POST /api/auth/register` - Register new user
- `POST /api/auth/login` - Login user
- `GET /api/auth/logout` - Logout user
- `GET /api/auth/user` - Get current user

### Cart
- `POST /api/cart/add` - Add item to cart
- `DELETE /api/cart/remove/:id` - Remove item from cart
- `POST /api/cart/increment/:id` - Increment item quantity
- `POST /api/cart/decrement/:id` - Decrement item quantity
- `POST /api/cart/checkout` - Stripe checkout
- `POST /api/cart/buy-all` - Buy all cart items
- `GET /api/cart/clear` - Clear cart

## Troubleshooting

**MongoDB connection error:**
- Ensure MongoDB is running: `brew services list` (macOS) or `sudo systemctl status mongodb` (Linux)
- Check connection string in `server/.env`
