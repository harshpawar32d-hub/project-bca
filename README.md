# SoleCraft — Premium Footwear E-Commerce Website

A complete, professional footwear e-commerce website built with **Node.js**, **Express**, **MongoDB (Mongoose)**, and **EJS** templating.

---

## 🚀 Features

- **Professional Homepage** with hero section, category grid, featured products, brand story, testimonials slider
- **Shop Page** with category filtering
- **Product Detail Pages** with full bio, image gallery, size/color selector, specifications
- **User Authentication** — register, login, logout (passwords hashed with bcrypt)
- **Order Placement** — checkout page with shipping details (login required)
- **My Orders Page** — view order history with status tracking
- **MongoDB Integration** — users and orders stored in MongoDB via Mongoose
- **Animations** — fade-up, slide-in, pop-in, floating hero image, testimonial auto-slider, scroll-triggered reveals, number counter
- **Toast Notifications** — popup feedback on wishlist actions
- **Fully Responsive** — mobile-friendly with hamburger menu

---

## 📁 Project Structure

```
solecraft/
├── server.js              # Main Express server
├── package.json
├── .env                   # Environment variables (create this)
├── data/
│   └── products.js        # Product catalog (6 products)
├── models/
│   ├── User.js            # Mongoose User model
│   └── Order.js           # Mongoose Order model
├── routes/
│   ├── index.js           # Home & Shop routes
│   ├── auth.js            # Login / Register / Logout
│   ├── products.js        # Product detail pages
│   └── orders.js          # Order placement & history
├── middleware/
│   └── auth.js            # requireLogin middleware
├── views/
│   ├── partials/
│   │   ├── header.ejs
│   │   └── footer.ejs
│   ├── index.ejs          # Homepage
│   ├── shop.ejs           # Shop listing
│   ├── product.ejs        # Product detail
│   ├── login.ejs          # Login page
│   ├── register.ejs       # Register page
│   ├── checkout.ejs       # Place order
│   └── orders.ejs         # Order history
└── public/
    ├── css/
    │   └── style.css
    └── js/
        └── main.js
```

---

## ⚙️ Setup Instructions

### 1. Prerequisites
- Node.js v16+
- MongoDB (local install or MongoDB Atlas cloud)

### 2. Install Dependencies
```bash
npm install
```

### 3. Configure Environment
Create a `.env` file in the root folder:
```
MONGO_URI=mongodb://localhost:27017/solecraft
PORT=3000
```

For MongoDB Atlas (cloud):
```
MONGO_URI=mongodb+srv://username:password@cluster.mongodb.net/solecraft
PORT=3000
```

### 4. Start MongoDB (if local)
```bash
mongod
```

### 5. Run the Server
```bash
# Production
npm start

# Development (with auto-restart)
npm run dev
```

### 6. Open in Browser
```
http://localhost:3000
```

---

## 🗄️ MongoDB Collections

### `users`
| Field | Type | Description |
|-------|------|-------------|
| name | String | Full name |
| email | String | Unique email |
| password | String | bcrypt hashed |
| createdAt | Date | Auto timestamp |

### `orders`
| Field | Type | Description |
|-------|------|-------------|
| user | ObjectId | Ref to User |
| items | Array | Product details |
| total | Number | Order total (₹) |
| status | String | confirmed/shipped/delivered |
| shippingAddress | Object | Street, city, state, zip |
| orderId | String | Unique order ID (SC...) |
| createdAt | Date | Auto timestamp |

---

## 🛒 User Flow

1. Browse homepage / shop without logging in
2. Click **"Buy Now"** or **"Order Now"** → redirected to login
3. Login or Register
4. Fill checkout form with size, quantity, shipping address
5. Order confirmed → redirected to **My Orders** page
6. View full order history at `/orders`

---

## 🎨 Design

- **Typography**: Playfair Display (headings) + DM Sans (body)
- **Color Palette**: Deep black `#0a0a0a`, warm gold `#c9a84c`, accent red `#e63946`
- **Aesthetic**: Luxury editorial — dark backgrounds, golden accents, generous whitespace
- **Animations**: CSS keyframes + IntersectionObserver for scroll-triggered reveals

---

## 📦 Dependencies

| Package | Purpose |
|---------|---------|
| express | Web framework |
| mongoose | MongoDB ODM |
| ejs | Template engine |
| bcryptjs | Password hashing |
| express-session | Session management |
| connect-mongo | MongoDB session store |

---

Built with ❤️ — SoleCraft Premium Footwear
