**# 📄 E-Commerce Website Documentation

## **1. Project Overview**

MyShop is a **full-stack e-commerce website** built with the MERN stack (MongoDB, Express.js, React.js, Node.js). It provides a complete online shopping experience including user authentication, product browsing, shopping cart, wishlist, order processing, and an admin panel.

The website allows users to register, login, browse products with search/filter/sort, add items to cart, save items to wishlist, write reviews, place orders, and view order history. Administrators can manage products, orders, and users through a dedicated dashboard.

---

## **2. Technologies Used**

### **Frontend:**
- **React.js** - User interface library
- **React Router DOM** - Page navigation
- **Axios** - API requests
- **Context API** - State management

### **Backend:**
- **Node.js** - Runtime environment
- **Express.js** - Web framework
- **MongoDB** - Database
- **Mongoose** - Database modeling
- **JWT** - Authentication
- **Bcrypt.js** - Password hashing

### **Development Tools:**
- VS Code, MongoDB Compass, Postman, Git, npm

---

## **3. Features Implemented**

### **User Features:**
- ✅ **Authentication** - Register, Login, Logout
- ✅ **Product Browsing** - View all products with images, prices, descriptions
- ✅ **Search & Filter** - Search by name, filter by price range
- ✅ **Sort Options** - Sort by price (low-high, high-low) and name (A-Z)
- ✅ **Product Details** - Dedicated page with full information
- ✅ **Reviews & Ratings** - Write reviews and rate products (1-5 stars)
- ✅ **Shopping Cart** - Add items, update quantities, remove items
- ✅ **Wishlist** - Save products for later
- ✅ **Checkout** - Place orders with Cash on Delivery
- ✅ **Order History** - View past orders with status tracking

### **Admin Features:**
- ✅ **Product Management** - Add, edit, delete products
- ✅ **Order Management** - View all orders, update status
- ✅ **User Management** - View users, toggle admin privileges

---

## **4. System Architecture**

The application follows a client-server architecture:

```
Frontend (React, Port 3000) → Backend API (Express, Port 5000) → MongoDB Database
```

- Frontend and backend communicate via RESTful APIs
- JWT tokens authenticate user requests
- All data is stored in MongoDB collections

---

## **5. Database Design**

### **Collections:**

| Collection | Purpose |
|------------|---------|
| **users** | Store user information (name, email, password, admin status) |
| **products** | Store product details (title, description, price, image, category) |
| **carts** | Store user shopping carts with items and quantities |
| **orders** | Store order information with items, total, status |
| **reviews** | Store product reviews with ratings and comments |
| **wishlists** | Store user wishlist items |

### **Relationships:**
- One user has one cart, one wishlist, and multiple orders
- One product has multiple reviews
- Orders contain multiple products

---

## **6. API Endpoints Summary**

| Endpoint | Method | Description | Auth |
|----------|--------|-------------|------|
| `/api/auth/register` | POST | Register new user | Public |
| `/api/auth/login` | POST | Login user | Public |
| `/api/auth/me` | GET | Get current user | Private |
| `/api/products` | GET | Get all products | Public |
| `/api/products/:id` | GET | Get single product | Public |
| `/api/products/:id/reviews` | POST | Add review | Private |
| `/api/cart` | GET | Get user cart | Private |
| `/api/cart/add` | POST | Add to cart | Private |
| `/api/cart/update/:id` | PUT | Update quantity | Private |
| `/api/cart/remove/:id` | DELETE | Remove from cart | Private |
| `/api/orders` | POST | Create order | Private |
| `/api/orders/my-orders` | GET | Get user orders | Private |
| `/api/wishlist` | GET | Get wishlist | Private |
| `/api/wishlist/add/:id` | POST | Add to wishlist | Private |
| `/api/wishlist/remove/:id` | DELETE | Remove from wishlist | Private |
| `/api/admin/products` | GET/POST | Manage products | Admin |
| `/api/admin/orders` | GET | View all orders | Admin |
| `/api/admin/users` | GET | View all users | Admin |

---

## **7. User Interface Pages**

| Page | Route | Description |
|------|-------|-------------|
| Home | `/` | Landing page with brand information |
| Products | `/products` | Product catalog with search/filter/sort |
| Product Detail | `/product/:id` | Detailed product view with reviews |
| Cart | `/cart` | Shopping cart management |
| Checkout | `/checkout` | Order placement |
| Order History | `/orders` | Past orders tracking |
| Wishlist | `/wishlist` | Saved items |
| Login | `/login` | User login |
| Register | `/register` | New user registration |
| Admin Dashboard | `/admin` | Admin panel |

### **Navigation Bar:**
- **Guests:** Home, Products, Login, Register
- **Users:** Home, Products, Cart, Orders, Wishlist, Username, Logout
- **Admins:** Additional Admin link

---

## **8. Admin Panel Features**

The admin dashboard has three tabs:

### **Products Tab:**
- Add new products with title, description, price, image URL
- View all products in a table
- Edit existing products
- Delete products with confirmation

### **Orders Tab:**
- View all customer orders
- Update order status (pending, processing, shipped, delivered)
- See customer details and order items

### **Users Tab:**
- View all registered users
- Toggle admin privileges
- See join dates

---

## **9. Security Features**

- **Password Hashing:** All passwords encrypted with bcrypt
- **JWT Authentication:** Secure token-based authentication
- **Protected Routes:** Authentication middleware for sensitive endpoints
- **Authorization:** Admin-only routes protected
- **Input Validation:** Server-side validation for all inputs
- **Environment Variables:** Sensitive data stored in .env file

---

## **10. Installation Guide**

### **Prerequisites:**
- Node.js (v14+)
- MongoDB
- MongoDB Compass (optional)

### **Step 1: Backend Setup**
```bash
cd backend
npm install
# Create .env file with:
# PORT=5000
# MONGODB_URI=mongodb://localhost:27017/myshop
# JWT_SECRET=mysecretkey123456789
npm run dev
```

### **Step 2: Frontend Setup**
```bash
cd frontend
npm install
npm start
```

### **Step 3: Access Website**
```
http://localhost:3000
```

---

## **11. Testing Summary**

| Feature | Tested | Status |
|---------|--------|--------|
| User Registration | ✓ | Working |
| User Login | ✓ | Working |
| Product Listing | ✓ | Working |
| Search Products | ✓ | Working |
| Filter by Price | ✓ | Working |
| Sort Products | ✓ | Working |
| Add to Cart | ✓ | Working |
| Update Cart | ✓ | Working |
| Remove from Cart | ✓ | Working |
| Add to Wishlist | ✓ | Working |
| Write Reviews | ✓ | Working |
| Checkout Process | ✓ | Working |
| Order History | ✓ | Working |
| Admin Add Product | ✓ | Working |
| Admin Edit Product | ✓ | Working |
| Admin Delete Product | ✓ | Working |

---

## **12. Future Enhancements**

- Payment Integration (Stripe/PayPal)
- Product Image Upload
- Email Notifications
- Password Reset
- Product Categories
- Multiple Product Images
- Discount Coupons
- Mobile App Version

---

## **13. Conclusion**

MyShop is a **complete, functional e-commerce website** that demonstrates proficiency in full-stack web development. It successfully implements all core features required for an online shopping platform including user authentication, product management, shopping cart, wishlist, order processing, and administrative controls.

The project showcases expertise in:
- MERN stack development
- RESTful API design
- Database modeling
- Authentication & authorization
- Responsive UI design

---

## **Project Details**

| | |
|---|---|
| **Project Name** | MyShop E-Commerce Website |
| **Developer** | [Your Name] |
| **Course** | [Your Course Name] |
| **Date** | [Current Date] |
| **Technologies** | MongoDB, Express.js, React.js, Node.js |

---

**© 2024 MyShop. All Rights Reserved.**

---

This version is shorter, has clear bold headings, and uses simple paragraphs. You can now:
1. Copy this into Microsoft Word
2. Adjust font sizes (Headings 16pt, Body 12pt Times New Roman)
3. Add screenshots between sections
4. Save as DOCX**

# Getting Started with Create React App

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Available Scripts

In the project directory, you can run:

### `npm start`

Runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in your browser.

The page will reload when you make changes.\
You may also see any lint errors in the console.

### `npm test`

Launches the test runner in the interactive watch mode.\
See the section about [running tests](https://facebook.github.io/create-react-app/docs/running-tests) for more information.

### `npm run build`

Builds the app for production to the `build` folder.\
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.\
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.

### `npm run eject`

**Note: this is a one-way operation. Once you `eject`, you can't go back!**

If you aren't satisfied with the build tool and configuration choices, you can `eject` at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you're on your own.

You don't have to ever use `eject`. The curated feature set is suitable for small and middle deployments, and you shouldn't feel obligated to use this feature. However we understand that this tool wouldn't be useful if you couldn't customize it when you are ready for it.

## Learn More

You can learn more in the [Create React App documentation](https://facebook.github.io/create-react-app/docs/getting-started).

To learn React, check out the [React documentation](https://reactjs.org/).

### Code Splitting

This section has moved here: [https://facebook.github.io/create-react-app/docs/code-splitting](https://facebook.github.io/create-react-app/docs/code-splitting)

### Analyzing the Bundle Size

This section has moved here: [https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size](https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size)

### Making a Progressive Web App

This section has moved here: [https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app](https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app)

### Advanced Configuration

This section has moved here: [https://facebook.github.io/create-react-app/docs/advanced-configuration](https://facebook.github.io/create-react-app/docs/advanced-configuration)

### Deployment

This section has moved here: [https://facebook.github.io/create-react-app/docs/deployment](https://facebook.github.io/create-react-app/docs/deployment)

### `npm run build` fails to minify

This section has moved here: [https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify](https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify)
