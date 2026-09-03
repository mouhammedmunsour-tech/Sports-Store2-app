# 🏋️ Sports Store Mobile App | متجر معدات رياضية

<p align="center">
  <img src="https://img.shields.io/badge/React%20Native-0.74-blue?logo=react" />
  <img src="https://img.shields.io/badge/Expo-SDK%2051-black?logo=expo" />
  <img src="https://img.shields.io/badge/Node.js-18+-green?logo=node.js" />
  <img src="https://img.shields.io/badge/PostgreSQL-15+-blue?logo=postgresql" />
  <img src="https://img.shields.io/badge/Stripe-Payments-blueviolet?logo=stripe" />
  <img src="https://img.shields.io/badge/i18n-AR%20%7C%20EN-orange" />
</p>

A full-stack mobile e-commerce application for sports equipment supporting **Arabic (RTL)** and **English (LTR)** with real-time order tracking, Stripe payments, and an admin dashboard.

---

## ✨ Features | المميزات

| Feature | Description |
|---------|-------------|
| 🏠 **Categories & Catalog** | Fitness, Football, Basketball, Water Sports, Outdoor, Gym Gear with smart filters & search |
| 📦 **Product Pages** | High-quality images, detailed descriptions, customer reviews, ratings, stock status |
| 🛒 **Shopping Cart** | Add to cart, quantity adjustments, real-time total calculation |
| 💳 **Payments** | Credit/Debit Cards, Google Pay, Cash on Delivery (COD) via Stripe |
| 👤 **User Accounts** | Email & Social login (Google), order history, wishlists, address management |
| 📍 **Order Tracking** | Real-time status: Pending → Confirmed → Shipped → Delivered |
| 📊 **Admin Dashboard** | Manage inventory, add/edit products, view orders, analytics |
| 🌐 **Bilingual** | Full Arabic (RTL) & English (LTR) support with i18next |
| 🌙 **Dark Mode** | Automatic theme switching |
| 🔒 **Security** | JWT auth, bcrypt passwords, Helmet, Rate Limiting |

---

## 🏗️ Tech Stack | التقنيات المستخدمة

### Backend
- **Node.js** + **Express.js**
- **PostgreSQL** + **Sequelize ORM**
- **JWT** authentication + **bcryptjs** hashing
- **Stripe** payment gateway
- **Cloudinary** image uploads
- **Helmet** + **Rate Limiting** security

### Frontend
- **React Native** + **Expo SDK 51**
- **React Navigation** (Stack + Bottom Tabs)
- **React Native Paper** UI components
- **i18next** + **react-i18next** for localization
- **Zustand** state management
- **TanStack Query** data fetching
- **@stripe/stripe-react-native** payments

---

## 📁 Project Structure | هيكل المشروع

```
sports-store-app/
├── backend/                    # Node.js API
│   ├── src/
│   │   ├── server.js           # Entry point
│   │   ├── config/
│   │   │   └── database.js     # DB configuration
│   │   ├── models/             # Sequelize models (8 tables)
│   │   ├── routes/             # API routes (7 endpoints)
│   │   ├── controllers/        # Business logic
│   │   ├── middleware/         # Auth, upload, error handling
│   │   └── seed.js             # Initial data seeding
│   ├── .env.example
│   └── package.json
│
└── frontend/                   # React Native app
    ├── src/
    │   ├── screens/            # All app screens
    │   ├── components/         # Reusable components
    │   ├── context/            # Auth & Theme contexts
    │   ├── i18n/               # AR & EN translations
    │   ├── utils/              # API client & helpers
    │   └── navigation/         # Navigators
    ├── App.js                  # Root component
    ├── app.json                # Expo configuration
    └── package.json
```

---

## 🚀 Getting Started | بدء التشغيل

### Prerequisites | المتطلبات
- Node.js ≥ 18
- PostgreSQL ≥ 15
- Expo CLI (`npm install -g expo-cli`)
- Stripe account (for payments)
- Cloudinary account (for images)

### 1. Clone the repository
```bash
git clone https://github.com/yourusername/sports-store-app.git
cd sports-store-app
```

### 2. Backend Setup
```bash
cd backend
cp .env.example .env
# Edit .env with your credentials
npm install
npm run seed    # Seed categories & products + create admin user
npm run dev     # Runs on http://localhost:5000
```

**Default Admin Credentials:**
- Email: `admin@sportsstore.com`
- Password: `admin123`

### 3. Frontend Setup
```bash
cd ../frontend
cp .env.example .env
# Edit .env with your API URL & Stripe keys
npm install
npx expo start
```

Press `a` for Android emulator or `i` for iOS simulator.

---

## 🔌 API Endpoints | نقاط الوصول

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/auth/register` | Register new user |
| POST | `/api/auth/login` | Login with email/password |
| POST | `/api/auth/social` | Social login (Google) |
| GET | `/api/products` | List products (with filters) |
| GET | `/api/products/:id` | Product details |
| POST | `/api/cart` | Add to cart |
| GET | `/api/cart` | Get cart items |
| POST | `/api/orders` | Place order |
| GET | `/api/orders` | Get user orders |
| GET | `/api/orders/:id/track` | Track order |
| POST | `/api/payment/intent` | Create Stripe payment intent |
| GET | `/api/admin/dashboard` | Admin dashboard stats |

---

## 🌍 Localization | التعريب

The app fully supports **Arabic (RTL)** and **English (LTR)**:
- All UI texts are managed via `i18next`
- Dynamic layout direction (`dir: rtl/ltr`)
- Arabic product names and descriptions stored in DB
- Right-to-left navigation and icon mirroring

---

## 🔒 Security Features | ميزات الأمان

- JWT token-based authentication
- Password hashing with bcrypt (12 rounds)
- Rate limiting (100 requests / 15 min)
- Helmet HTTP security headers
- Input validation with express-validator
- SQL injection protection via Sequelize parameterized queries

---

## 📝 License | الترخيص

MIT License - feel free to use for personal or commercial projects.

---

<p align="center">
  Built with ❤️ for sports enthusiasts worldwide.
</p>
