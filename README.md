# 📈 StockPulse — Real-Time Stock Trading Platform

### *A Full-Stack MERN Application for Simulated Stock Trading, Portfolio Management & Market Analytics*

[![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=for-the-badge&logo=mongodb&logoColor=white)](https://www.mongodb.com/)
[![Express.js](https://img.shields.io/badge/Express.js-000000?style=for-the-badge&logo=express&logoColor=white)](https://expressjs.com/)
[![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)](https://reactjs.org/)
[![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=node.js&logoColor=white)](https://nodejs.org/)
[![JWT](https://img.shields.io/badge/JWT-Auth-black?style=for-the-badge&logo=jsonwebtokens&logoColor=white)](https://jwt.io/)
[![Socket.io](https://img.shields.io/badge/Socket.io-010101?style=for-the-badge&logo=socket.io&logoColor=white)](https://socket.io/)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](LICENSE)
[![Status](https://img.shields.io/badge/Status-Active-success?style=for-the-badge)]()

## DEMO LINK
https://photos.app.goo.gl/QsPavesJrhpmXDGf6

</div>

---

## 📑 Table of Contents

1. [Technical Architecture](#-technical-architecture)
2. [ER Diagram](#-er-diagram)
3. [Features](#-features)
4. [Roles and Responsibilities](#-roles-and-responsibilities)
5. [User Flow](#-user-flow)
6. [MVC Pattern & Project Folder Creation](#-mvc-pattern--project-folder-creation)
7. [Client Setup](#-client-setup)
8. [Server Setup & Backend Structure](#-server-setup--backend-structure)
9. [Development & Explanation — Configure MongoDB](#-development--explanation--configure-mongodb)
10. [Create Database Connection](#-create-database-connection)
11. [Create Schema and Models](#-create-schema-and-models)
12. [Frontend Structure](#-frontend-structure)
13. [Development & Explanation — Frontend](#-development--explanation--frontend)
14. [Steps for Project Execution](#-steps-for-project-execution)
15. [Output Screenshots](#-output-screenshots)
16. [Drive Links](#-drive-links)

---

## 🏗️ Technical Architecture

StockPulse follows a **3-tier client-server architecture** using the MERN stack, with real-time price updates powered by Socket.io and a RESTful API layer connecting the client to MongoDB.

<img width="1440" height="1160" alt="image" src="https://github.com/user-attachments/assets/f30df102-9fb4-428e-8383-785602e09c9e" />


### Architecture Layers

| Layer | Technology | Responsibility |
|---|---|---|
| **Presentation** | React.js, Tailwind CSS, Recharts | UI rendering, state management, live chart updates |
| **API Gateway** | Express.js REST APIs | Request routing, validation, response formatting |
| **Business Logic** | Node.js Controllers & Services | Order matching, buy/sell execution, portfolio calculation |
| **Real-Time Layer** | Socket.io | Live stock price broadcast to connected clients |
| **Data Persistence** | MongoDB + Mongoose | Schema-based document storage |
| **Security** | JWT, bcrypt, express-validator | Auth, password hashing, input sanitization |

---

## 🗂️ ER Diagram
# frontend 
<img width="3091" height="1491" alt="image" src="https://github.com/user-attachments/assets/dea800b9-6c3f-4890-85c6-e7967c3dfcdd" />


# backend
<img width="1221" height="602" alt="image" src="https://github.com/user-attachments/assets/2b1c6ca0-12ec-408b-8b9d-b9cfca50be7b" />

# Database
<img width="942" height="672" alt="image" src="https://github.com/user-attachments/assets/9ce92163-e140-40f0-a9c1-236ea5e03550" />

# stocktrading-app
<img width="984" height="710" alt="image" src="https://github.com/user-attachments/assets/32aacf6d-d85b-4d9c-8e09-9f22ba46d930" />

---

## ✨ Features

- 🔐 **Secure Authentication** — JWT-based login/signup with bcrypt password hashing
- 📊 **Real-Time Stock Prices** — Live price updates via Socket.io, no page refresh needed
- 💰 **Buy/Sell Simulation** — Execute trades against a virtual wallet balance
- 📁 **Portfolio Dashboard** — Track holdings, average buy price, profit/loss (P&L), and net worth
- 📈 **Interactive Charts** — Candlestick/line charts using Recharts / Chart.js for price history
- ⭐ **Watchlist Management** — Add/remove stocks to a personal watchlist
- 🧾 **Transaction History** — Complete ledger of every buy/sell order with timestamps
- 🔍 **Stock Search & Filter** — Search by symbol, company name, or sector
- 📱 **Fully Responsive UI** — Mobile-first design with Tailwind CSS
- 🛡️ **Role-Based Access** — Separate views for Admin (manage stocks) and User (trade stocks)
- 📉 **Market Movers Widget** — Top gainers/losers of the day
- 🌙 **Dark Mode UI** — Premium glassmorphism trading dashboard theme

---

## 👥 Roles and Responsibilities

<div align="center">

| # | Name | Role | Responsibilities |
|---|---|---|---|
| 1 | **Meenuga Bhuvaneswari** | Frontend Developer | React component architecture, UI/UX design, dashboard & charts integration |
| 2 | **Arakkonam Snehalatha** | Backend Developer | Express REST APIs, MongoDB schema design, authentication & trading logic |
| 3 | **Y Dheeraj** | Full Stack Integration | Client-server integration, Socket.io real-time engine, API testing |
| 4 | **Chemmalamarri Jayasree** | Database & Documentation | MongoDB modeling, ER diagram design, project documentation |
| 5 | **Smitha Badiga** | Testing & Deployment | Unit/integration testing, deployment (Vercel/Render), bug fixing |

</div>

> 💡 *Each member contributed across both frontend and backend during integration sprints, following an agile task-splitting approach.*

---

## 🔄 User Flow

<img width="1440" height="1968" alt="image" src="https://github.com/user-attachments/assets/884575b5-a0f0-47ec-b2a2-7c5b8bd5b462" />

---

## 🏛️ MVC Pattern & Project Folder Creation

StockPulse follows the **Model-View-Controller (MVC)** pattern on the backend:

- **Model** → Mongoose schemas (`/models`) defining data structure
- **View** → React frontend (`/client`) — decoupled, consumes REST APIs
- **Controller** → Express controllers (`/controllers`) handling business logic

### Create the Root Project Folder

```bash
mkdir stockpulse-mern
cd stockpulse-mern
mkdir client server
```

### Root Folder Structure

```
stockpulse-mern/
├── client/                 # React frontend
├── server/                 # Node + Express backend (MVC)
├── .gitignore
├── README.md
└── package.json            # root scripts (optional, for concurrently)
```

---

## 💻 Client Setup

```bash
cd client
npx create-react-app .
# OR using Vite (recommended, faster)
npm create vite@latest . -- --template react

npm install axios react-router-dom redux react-redux @reduxjs/toolkit
npm install recharts socket.io-client
npm install tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

**`client/tailwind.config.js`**
```javascript
module.exports = {
  content: ["./src/**/*.{js,jsx,ts,tsx}"],
  theme: {
    extend: {
      colors: {
        'trade-dark': '#0f0f1a',
        'trade-green': '#00ff9d',
        'trade-red': '#ff4e50',
      },
    },
  },
  plugins: [],
};
```

Run the client:
```bash
npm run dev      # if Vite
npm start        # if CRA
```

---

## 🖥️ Server Setup & Backend Structure

```bash
cd server
npm init -y
npm install express mongoose dotenv cors bcryptjs jsonwebtoken
npm install socket.io express-validator
npm install --save-dev nodemon
```

**`server/package.json`** — add scripts:
```json
{
  "scripts": {
    "start": "node server.js",
    "dev": "nodemon server.js"
  }
}
```

### Backend Folder Structure (MVC)

```
server/
├── config/
│   └── db.js                 # MongoDB connection
├── models/
│   ├── User.js
│   ├── Stock.js
│   ├── Portfolio.js
│   ├── Transaction.js
│   └── Watchlist.js
├── controllers/
│   ├── authController.js
│   ├── stockController.js
│   ├── tradeController.js
│   └── portfolioController.js
├── routes/
│   ├── authRoutes.js
│   ├── stockRoutes.js
│   ├── tradeRoutes.js
│   └── portfolioRoutes.js
├── middleware/
│   ├── authMiddleware.js
│   └── errorMiddleware.js
├── sockets/
│   └── priceSocket.js         # Real-time price broadcast
├── utils/
│   └── generateToken.js
├── .env
├── server.js                  # Entry point
└── package.json
```

---

## ⚙️ Development & Explanation — Configure MongoDB

### 1. Create `.env` File

```
PORT=5000
MONGO_URI=mongodb+srv://<username>:<password>@cluster0.mongodb.net/stockpulse
JWT_SECRET=your_jwt_secret_key_here
CLIENT_URL=http://localhost:5173
```

> 📝 Get `MONGO_URI` from **MongoDB Atlas** → Database → Connect → Drivers → Node.js.

### 2. Install dotenv config at entry point

**`server/server.js`**
```javascript
const express = require('express');
const http = require('http');
const cors = require('cors');
const dotenv = require('dotenv');
const { Server } = require('socket.io');
const connectDB = require('./config/db');

dotenv.config();
connectDB();

const app = express();
app.use(cors());
app.use(express.json());

// Routes
app.use('/api/auth', require('./routes/authRoutes'));
app.use('/api/stocks', require('./routes/stockRoutes'));
app.use('/api/trade', require('./routes/tradeRoutes'));
app.use('/api/portfolio', require('./routes/portfolioRoutes'));

const server = http.createServer(app);
const io = new Server(server, {
  cors: { origin: process.env.CLIENT_URL },
});

require('./sockets/priceSocket')(io);

const PORT = process.env.PORT || 5000;
server.listen(PORT, () => console.log(`🚀 Server running on port ${PORT}`));
```

---

## 🔗 Create Database Connection

**`server/config/db.js`**
```javascript
const mongoose = require('mongoose');

const connectDB = async () => {
  try {
    const conn = await mongoose.connect(process.env.MONGO_URI);
    console.log(`✅ MongoDB Connected: ${conn.connection.host}`);
  } catch (error) {
    console.error(`❌ MongoDB Connection Error: ${error.message}`);
    process.exit(1);
  }
};

module.exports = connectDB;
```

---

## 🧬 Create Schema and Models

**`server/models/User.js`**
```javascript
const mongoose = require('mongoose');

const userSchema = new mongoose.Schema({
  name: { type: String, required: true },
  email: { type: String, required: true, unique: true },
  password: { type: String, required: true },
  role: { type: String, enum: ['user', 'admin'], default: 'user' },
  walletBalance: { type: Number, default: 100000 }, // virtual starting cash
}, { timestamps: true });

module.exports = mongoose.model('User', userSchema);
```

**`server/models/Stock.js`**
```javascript
const mongoose = require('mongoose');

const stockSchema = new mongoose.Schema({
  symbol: { type: String, required: true, unique: true, uppercase: true },
  companyName: { type: String, required: true },
  currentPrice: { type: Number, required: true },
  previousClose: { type: Number, required: true },
  dayHigh: { type: Number },
  dayLow: { type: Number },
  sector: { type: String },
}, { timestamps: true });

module.exports = mongoose.model('Stock', stockSchema);
```

**`server/models/Portfolio.js`**
```javascript
const mongoose = require('mongoose');

const holdingSchema = new mongoose.Schema({
  stockId: { type: mongoose.Schema.Types.ObjectId, ref: 'Stock' },
  quantity: { type: Number, required: true },
  avgBuyPrice: { type: Number, required: true },
});

const portfolioSchema = new mongoose.Schema({
  userId: { type: mongoose.Schema.Types.ObjectId, ref: 'User', required: true },
  holdings: [holdingSchema],
  totalInvested: { type: Number, default: 0 },
}, { timestamps: true });

module.exports = mongoose.model('Portfolio', portfolioSchema);
```

**`server/models/Transaction.js`**
```javascript
const mongoose = require('mongoose');

const transactionSchema = new mongoose.Schema({
  userId: { type: mongoose.Schema.Types.ObjectId, ref: 'User', required: true },
  stockId: { type: mongoose.Schema.Types.ObjectId, ref: 'Stock', required: true },
  type: { type: String, enum: ['BUY', 'SELL'], required: true },
  quantity: { type: Number, required: true },
  price: { type: Number, required: true },
  totalAmount: { type: Number, required: true },
}, { timestamps: true });

module.exports = mongoose.model('Transaction', transactionSchema);
```

**`server/models/Watchlist.js`**
```javascript
const mongoose = require('mongoose');

const watchlistSchema = new mongoose.Schema({
  userId: { type: mongoose.Schema.Types.ObjectId, ref: 'User', required: true },
  stockId: { type: mongoose.Schema.Types.ObjectId, ref: 'Stock', required: true },
}, { timestamps: true });

module.exports = mongoose.model('Watchlist', watchlistSchema);
```

---

## 🎨 Frontend Structure

```
client/src/
├── components/
│   ├── Navbar.jsx
│   ├── StockCard.jsx
│   ├── PriceChart.jsx
│   ├── PortfolioSummary.jsx
│   ├── WatchlistItem.jsx
│   └── TransactionRow.jsx
├── pages/
│   ├── Login.jsx
│   ├── Signup.jsx
│   ├── Dashboard.jsx
│   ├── StockDetail.jsx
│   ├── Portfolio.jsx
│   └── Watchlist.jsx
├── redux/
│   ├── store.js
│   ├── authSlice.js
│   └── stockSlice.js
├── services/
│   ├── api.js               # Axios instance
│   └── socket.js             # Socket.io client instance
├── context/
│   └── AuthContext.jsx
├── App.jsx
├── main.jsx
└── index.css
```

---

## 🛠️ Development & Explanation — Frontend

### Axios Instance
**`client/src/services/api.js`**
```javascript
import axios from 'axios';

const API = axios.create({ baseURL: 'http://localhost:5000/api' });

API.interceptors.request.use((req) => {
  const token = localStorage.getItem('token');
  if (token) req.headers.Authorization = `Bearer ${token}`;
  return req;
});

export default API;
```

### Socket.io Client
**`client/src/services/socket.js`**
```javascript
import { io } from 'socket.io-client';

const socket = io('http://localhost:5000');
export default socket;
```

### Live Price Subscription (Dashboard.jsx snippet)
```javascript
useEffect(() => {
  socket.on('priceUpdate', (updatedStocks) => {
    setStocks((prev) =>
      prev.map((s) => updatedStocks.find((u) => u.symbol === s.symbol) || s)
    );
  });
  return () => socket.off('priceUpdate');
}, []);
```

> This keeps every connected client's stock prices in sync without polling the REST API repeatedly.

---

## ▶️ Steps for Project Execution

```bash
# 1. Clone the repository
git clone https://github.com/snehalathaArakkonam/stockpulse-mern.git
cd stockpulse-mern

# 2. Setup backend
cd server
npm install
# create .env file (see Configure MongoDB section above)
npm run dev

# 3. Setup frontend (new terminal)
cd client
npm install
npm run dev

# 4. Open in browser
# Frontend → http://localhost:5173
# Backend API → http://localhost:5000/api
```

### Quick Checklist
- [ ] MongoDB Atlas cluster created & IP whitelisted
- [ ] `.env` configured with `MONGO_URI` and `JWT_SECRET`
- [ ] Backend running on port `5000`
- [ ] Frontend running on port `5173`
- [ ] Test signup → login → buy stock → check portfolio

---
<div align="center">

## 🙏 Acknowledgements

Built with ❤️ by **Team StockPulse** as part of academic project work.
*"Markets move in cycles. So does learning — keep building, keep iterating."* 📈

---

⭐ **If you found this project helpful, don't forget to star the repo!** ⭐

</div>
