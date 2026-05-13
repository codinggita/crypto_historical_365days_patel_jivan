# 🪙 Crypto Market Analytics — Full Stack Dashboard

A full-stack cryptocurrency analytics platform built with **Node.js**, **Express**, **MongoDB**, and **React**. Provides **50+ RESTful API endpoints** for comprehensive crypto market data analysis, featuring an admin/user dashboard with real-time data visualization, authentication, and advanced analytics.

---

## 🛠️ Tech Stack

### Backend
| Technology | Purpose |
|---|---|
| **Node.js** | Runtime environment |
| **Express.js** | Web framework |
| **MongoDB** | NoSQL database |
| **Mongoose** | MongoDB ODM |
| **JWT** | Authentication tokens |
| **bcrypt** | Password hashing |
| **dotenv** | Environment variables |
| **cors** | Cross-origin requests |

### Frontend
| Technology | Purpose |
|---|---|
| **Vite** | Build tool & dev server |
| **React** | UI library |
| **Redux Toolkit** | State management |
| **Tailwind CSS** | Utility-first styling |
| **MUI (Material UI)** | Component library |
| **Axios** | HTTP client |
| **React Router** | Client-side routing |
| **Formik + Yup** | Form handling & validation |
| **React Helmet** | SEO metadata |

---

## ✨ Features

### Backend Features
- Full **CRUD** operations (Create, Read, Update, Delete)
- **Bulk operations** (bulk create, update, delete)
- **JWT authentication** with role-based access (admin/user)
- Advanced **search, filter, sort, and pagination**
- **Aggregation pipeline** for analytics
- **Coin comparison** (2-way and 3-way)
- Performance, volatility, volume, and returns analytics
- **Middleware system** — logging, auth, error handling, rate limiting
- Consistent **API response standardization**
- **MVC architecture** with clean separation of concerns

### Frontend Features
- **Admin & User dashboards** with sidebar navigation
- Real-time **data visualization** with charts
- CRUD interface with **modals and forms**
- **Dark/Light theme** toggle
- **Pagination, filtering, and search** connected to backend
- **Protected routes** with JWT auth flow
- Skeleton loaders, empty states, and error states
- **SEO optimization** with React Helmet
- Fully **responsive** design (desktop-first)

---

## 📊 Dataset Information

| Property | Details |
|---|---|
| **Records** | 235,000+ cryptocurrency daily records |
| **Coverage** | 365-day historical data |
| **Format** | JSON / MongoDB collection |
| **Google Drive** | [Download Dataset](https://drive.google.com/file/d/1Kwz2f4QDRj2AcyaYG87kdnRm3EPfUNaH/view?usp=drive_link) |

### Core Data Fields
```
coin_id          — Unique identifier (e.g., "bitcoin")
coin_name        — Full name (e.g., "Bitcoin")
symbol           — Trading symbol (e.g., "BTC")
market_cap_rank  — Rank by market cap
timestamp        — Full timestamp
date             — YYYY-MM-DD format
price            — Current price (USD)
market_cap       — Total market capitalization
volume           — 24h trading volume
daily_return     — Daily percentage return
price_ma7        — 7-day moving average
price_ma30       — 30-day moving average
volatility_7d    — 7-day volatility percentage
cumulative_return — Cumulative return percentage
month            — YYYY-MM format
```

---

## 🔗 API Endpoints Overview

### Basic CRUD Routes
| Method | Endpoint | Description |
|:---|:---|:---|
| `GET` | `/coins` | Fetch all cryptocurrency records |
| `GET` | `/coins/:id` | Fetch single cryptocurrency record |
| `POST` | `/coins` | Add a new cryptocurrency record |
| `PUT` | `/coins/:id` | Replace complete cryptocurrency record |
| `PATCH` | `/coins/:id` | Update specific cryptocurrency fields |
| `DELETE` | `/coins/:id` | Remove cryptocurrency record |
| `GET` | `/coins/exists/:id` | Check whether coin record exists |
| `POST` | `/coins/bulk-create` | Insert multiple records together |
| `PATCH` | `/coins/bulk-update` | Update multiple records |
| `DELETE` | `/coins/bulk-delete` | Delete multiple records |

### Coin Information Routes
| Method | Endpoint | Description |
|:---|:---|:---|
| `GET` | `/coins/name/:coinName` | Fetch coin by name |
| `GET` | `/coins/symbol/:symbol` | Fetch coin by trading symbol |
| `GET` | `/coins/rank/:rank` | Fetch coins by market cap rank |
| `GET` | `/coins/month/:month` | Fetch records for specific month |
| `GET` | `/coins/date/:date` | Fetch records for a specific date |
| `GET` | `/coins/latest` | Fetch latest market records |
| `GET` | `/coins/history/:coinId` | Fetch complete historical data |
| `GET` | `/coins/top-market-cap` | Fetch highest market cap coins |
| `GET` | `/coins/top-volume` | Fetch top traded coins |
| `GET` | `/coins/top-gainers` | Fetch top gaining coins |
| `GET` | `/coins/top-losers` | Fetch highest losing coins |
| `GET` | `/coins/oldest` | Fetch oldest available records |
| `GET` | `/coins/newest` | Fetch newest available records |
| `GET` | `/coins/trending` | Fetch currently trending coins |
| `GET` | `/coins/recent` | Fetch recently updated records |

### Route Parameters
| Method | Endpoint | Description |
|:---|:---|:---|
| `GET` | `/coins/performance/:coinId` | Performance analytics |
| `GET` | `/coins/volatility/:coinId` | Volatility analytics |
| `GET` | `/coins/market-cap/:coinId` | Market capitalization details |
| `GET` | `/coins/volume/:coinId` | Trading volume details |
| `GET` | `/coins/returns/:coinId` | Returns analytics |
| `GET` | `/coins/compare/:coin1/:coin2` | Compare two cryptocurrencies |
| `GET` | `/coins/compare/:coin1/:coin2/:coin3` | Compare three cryptocurrencies |
| `GET` | `/coins/price/:coinId` | Current price of coin |
| `GET` | `/coins/history/:coinId/:month` | Historical monthly records |

### Query Parameters
| Method | Endpoint | Description |
|:---|:---|:---|
| `GET` | `/coins?price=100` | Filter by exact price |
| `GET` | `/coins?minPrice=100&maxPrice=500` | Filter by price range |
| `GET` | `/coins?volume=1000000` | Filter by volume |
| `GET` | `/coins?rank=50` | Filter by market rank |
| `GET` | `/coins?month=2024-12` | Filter by month |
| `GET` | `/coins?dailyReturn=5` | Filter by daily return |
| `GET` | `/coins?volatility=10` | Filter by volatility |
| `GET` | `/coins?marketCap=5000000` | Filter by market cap |
| `GET` | `/coins?symbol=BTC` | Filter by coin symbol |
| `GET` | `/coins?sort=price` | Sort by price |
| `GET` | `/coins?sort=volume` | Sort by volume |
| `GET` | `/coins?sort=marketCap` | Sort by market cap |
| `GET` | `/coins?page=1&limit=10` | Apply pagination |

### Pagination Routes
| Method | Endpoint | Description |
|:---|:---|:---|
| `GET` | `/coins?page=1&limit=10` | Paginated records |
| `GET` | `/coins/latest?page=1&limit=5` | Paginate latest records |
| `GET` | `/coins/top-market-cap?page=1&limit=10` | Paginate top market cap |
| `GET` | `/coins/top-volume?page=1&limit=10` | Paginate top volume |
| `GET` | `/coins/history/aave?page=1&limit=30` | Paginate historical records |
| `GET` | `/coins/trending?page=2&limit=15` | Paginate trending coins |
| `GET` | `/coins/top-gainers?page=1&limit=10` | Paginate top gainers |
| `GET` | `/coins/top-losers?page=1&limit=10` | Paginate top losers |

### Sorting Routes
| Method | Endpoint | Description |
|:---|:---|:---|
| `GET` | `/coins?sort=price` | Sort by price |
| `GET` | `/coins?sort=marketCap` | Sort by market capitalization |
| `GET` | `/coins?sort=volume` | Sort by trading volume |
| `GET` | `/coins?sort=rank` | Sort by market rank |
| `GET` | `/coins?sort=dailyReturn` | Sort by daily return |
| `GET` | `/coins?sort=volatility` | Sort by volatility |
| `GET` | `/coins/sort/price-asc` | Sort price ascending |
| `GET` | `/coins/sort/price-desc` | Sort price descending |
| `GET` | `/coins/sort/volume-desc` | Sort highest volume first |
| `GET` | `/coins/sort/rank-asc` | Sort top ranked first |
| `GET` | `/coins/sort/return-desc` | Sort highest return first |

### Search Routes
| Method | Endpoint | Description |
|:---|:---|:---|
| `GET` | `/search/coins?q=bitcoin` | Search by keyword |
| `GET` | `/search/coins?q=btc` | Search by symbol |
| `GET` | `/search/coins?q=2024-12` | Search by month |
| `GET` | `/search/coins?q=market-cap` | Search market cap records |
| `GET` | `/search/coins?q=high-volume` | Search high volume records |
| `GET` | `/search/coins?q=top-gainers` | Search gainers |
| `GET` | `/search/coins?q=top-losers` | Search losers |
| `GET` | `/search/coins?q=analytics` | Search analytics data |
| `GET` | `/search/coins?q=trending` | Search trending records |

### Filtering Routes
| Method | Endpoint | Description |
|:---|:---|:---|
| `GET` | `/coins/filter/high-price` | Highly priced coins |
| `GET` | `/coins/filter/low-price` | Low priced coins |
| `GET` | `/coins/filter/high-volume` | Highly traded coins |
| `GET` | `/coins/filter/low-volume` | Low traded coins |
| `GET` | `/coins/filter/high-market-cap` | High market cap coins |
| `GET` | `/coins/filter/low-market-cap` | Low market cap coins |
| `GET` | `/coins/filter/high-volatility` | Highly volatile coins |
| `GET` | `/coins/filter/low-volatility` | Low volatility coins |
| `GET` | `/coins/filter/high-return` | High return coins |
| `GET` | `/coins/filter/negative-return` | Negative return coins |
| `GET` | `/coins/filter/bullish` | Bullish trend coins |
| `GET` | `/coins/filter/bearish` | Bearish trend coins |
| `GET` | `/coins/filter/profitable` | Profitable coins |
| `GET` | `/coins/filter/loss-making` | Loss making coins |

### Analytics Routes
| Method | Endpoint | Description |
|:---|:---|:---|
| `GET` | `/analytics/price/highest` | Highest priced coin |
| `GET` | `/analytics/price/lowest` | Lowest priced coin |
| `GET` | `/analytics/price/average` | Average market price |
| `GET` | `/analytics/price/history/:coinId` | Price history |
| `GET` | `/analytics/price/trend` | Market trend analysis |
| `GET` | `/analytics/price/growth` | Price growth analysis |
| `GET` | `/analytics/price/drop` | Price drop analysis |
| `GET` | `/analytics/volume/highest` | Highest traded coins |
| `GET` | `/analytics/volume/lowest` | Lowest traded coins |
| `GET` | `/analytics/volume/average` | Average trading volume |
| `GET` | `/analytics/volume/spike` | Volume spike detection |
| `GET` | `/analytics/returns/top` | Highest return coins |
| `GET` | `/analytics/returns/negative` | Negative return coins |
| `GET` | `/analytics/returns/cumulative` | Cumulative returns |
| `GET` | `/analytics/volatility/high` | High volatility analysis |

### Statistics Routes
| Method | Endpoint | Description |
|:---|:---|:---|
| `GET` | `/stats/market-cap` | Total market capitalization |
| `GET` | `/stats/average-price` | Average market price |
| `GET` | `/stats/average-volume` | Average trading volume |
| `GET` | `/stats/highest-market-cap` | Highest market cap coin |
| `GET` | `/stats/highest-volume` | Highest traded coin |
| `GET` | `/stats/top-gainers` | Top gainers |
| `GET` | `/stats/top-losers` | Top losers |
| `GET` | `/stats/monthly-analysis` | Monthly market trends |
| `GET` | `/stats/coin-count` | Total unique coins |
| `GET` | `/stats/rank-distribution` | Rank distribution |
| `GET` | `/stats/price-distribution` | Price distribution |
| `GET` | `/stats/market-summary` | Overall market summary |
| `GET` | `/stats/daily-analysis` | Daily analytics |
| `GET` | `/stats/yearly-analysis` | Yearly analytics |

### Authentication Routes
| Method | Endpoint | Description |
|:---|:---|:---|
| `POST` | `/auth/register` | Register new user |
| `POST` | `/auth/login` | Login user |
| `POST` | `/auth/logout` | Logout user |
| `GET` | `/auth/profile` | Fetch user profile |
| `PATCH` | `/auth/profile` | Update profile |
| `DELETE` | `/auth/profile` | Delete profile |
| `POST` | `/auth/forgot-password` | Request password reset |
| `POST` | `/auth/reset-password` | Reset password |
| `POST` | `/auth/change-password` | Change password |
| `POST` | `/auth/verify-email` | Verify email |

### JWT Authentication Routes
| Method | Endpoint | Description |
|:---|:---|:---|
| `GET` | `/jwt/profile` | JWT protected profile |
| `GET` | `/jwt/dashboard` | JWT protected dashboard |
| `POST` | `/jwt/generate-token` | Generate JWT token |
| `POST` | `/jwt/verify-token` | Verify JWT token |
| `GET` | `/jwt/admin` | Admin protected route |
| `POST` | `/jwt/refresh-token` | Refresh JWT token |
| `DELETE` | `/jwt/revoke-token` | Revoke JWT token |

### Middleware Routes
| Method | Endpoint | Description |
|:---|:---|:---|
| `GET` | `/admin/coins` | Admin protected route |
| `GET` | `/admin/stats` | Admin analytics dashboard |
| `GET` | `/admin/users` | Fetch all users |
| `POST` | `/protected/coins` | Protected coin creation |
| `PATCH` | `/protected/coins/:id` | Protected update route |
| `DELETE` | `/protected/coins/:id` | Protected delete route |

### Advanced Routes
| Method | Endpoint | Description |
|:---|:---|:---|
| `GET` | `/coins/random` | Random cryptocurrency record |
| `GET` | `/coins/recommendations` | Coin recommendations |
| `GET` | `/coins/predictions` | Market trend predictions |
| `GET` | `/coins/portfolio/simulate` | Portfolio simulation |
| `GET` | `/coins/heatmap` | Market heatmap |
| `GET` | `/coins/market-status` | Overall market condition |
| `GET` | `/coins/performance/top-monthly` | Top monthly performers |
| `GET` | `/coins/performance/top-yearly` | Top yearly performers |
| `GET` | `/coins/alerts/high-volatility` | High volatility alerts |
| `GET` | `/coins/alerts/market-drop` | Market drop alerts |
| `GET` | `/coins/system/health` | API health status |
| `GET` | `/coins/system/version` | API version details |

### HEAD & OPTIONS Routes
| Method | Endpoint | Description |
|:---|:---|:---|
| `HEAD` | `/coins` | Headers for collection |
| `HEAD` | `/coins/:coinId` | Headers for single resource |
| `HEAD` | `/coins/history/:coinId` | Headers for historical records |
| `HEAD` | `/stats/market-cap` | Market cap stats metadata |
| `HEAD` | `/coins/system/health` | API health headers |
| `OPTIONS` | `/coins` | Supported methods for coins |
| `OPTIONS` | `/auth/login` | Allowed methods for login |
| `OPTIONS` | `/admin/coins` | Supported admin methods |
| `OPTIONS` | `/search/coins` | Supported search methods |

---

## 📁 Project Structure

```
crypto_historical_365days/
│
├── backend/
│   ├── src/
│   │   ├── config/
│   │   │   └── db.js                 # MongoDB connection
│   │   │
│   │   ├── models/
│   │   │   ├── coin.model.js         # Mongoose coin schema
│   │   │   └── user.model.js         # Mongoose user schema
│   │   │
│   │   ├── controllers/
│   │   │   ├── coin.controller.js    # Coin CRUD + analytics logic
│   │   │   └── auth.controller.js    # Authentication logic
│   │   │
│   │   ├── routes/
│   │   │   ├── coin.routes.js        # All coin endpoints
│   │   │   └── auth.routes.js        # Auth endpoints
│   │   │
│   │   ├── middlewares/
│   │   │   ├── auth.middleware.js     # JWT verification
│   │   │   ├── error.middleware.js    # Global error handling
│   │   │   └── logger.middleware.js   # Request logging
│   │   │
│   │   ├── app.js                    # Express setup + middleware
│   │   └── index.js                  # Server entry point
│   │
│   ├── .env
│   ├── .env.example
│   ├── .gitignore
│   └── package.json
│
├── frontend/
│   ├── src/
│   │   ├── components/               # Reusable UI components
│   │   ├── pages/                    # Route-based pages
│   │   ├── features/                 # Feature modules
│   │   ├── hooks/                    # Custom React hooks
│   │   ├── services/                 # API layer (Axios)
│   │   └── store/                    # Redux Toolkit store
│   │
│   ├── public/
│   ├── .env
│   ├── tailwind.config.js
│   ├── vite.config.js
│   └── package.json
│
└── README.md
```

---

## 🚀 Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) (v18 or higher)
- [MongoDB Atlas](https://www.mongodb.com/atlas) account or local MongoDB
- [Git](https://git-scm.com/)

### Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd crypto_historical_365days
   ```

2. **Setup Backend**
   ```bash
   cd backend
   npm install
   ```

3. **Setup Frontend**
   ```bash
   cd ../frontend
   npm install
   ```

### Environment Variables

Create a `.env` file in the `backend/` directory:

| Variable | Description | Example |
|---|---|---|
| `PORT` | Server port | `5000` |
| `MONGO_URI` | MongoDB connection string | `mongodb+srv://user:pass@cluster.mongodb.net/Crypto` |
| `JWT_SECRET` | Secret key for JWT tokens | `your_jwt_secret_key` |
| `NODE_ENV` | Environment mode | `development` |

```env
PORT=5000
MONGO_URI=mongodb+srv://your_connection_string
JWT_SECRET=your_jwt_secret_key
NODE_ENV=development
```

### Running the Project

**Start Backend Server**
```bash
cd backend
npm run dev
```
> Backend runs on `http://localhost:5000`

**Start Frontend Dev Server**
```bash
cd frontend
npm run dev
```
> Frontend runs on `http://localhost:5173`

---

## 📜 License

This project is licensed under the [MIT License](LICENSE).