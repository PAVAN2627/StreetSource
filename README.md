# StreetSource

A modern, production-ready B2B order management platform for suppliers and vendors.

## Features
- Supplier and Vendor dashboards
- Order placement, acceptance, delivery, and status tracking
- Email notifications for order events
- Revenue and spend tracking
- Product management for suppliers
- Clean, mobile-friendly UI (Bootstrap)
- Secure login and role-based access
- Project is fully cleaned of test/debug/sample/setup files

## Project Structure
```
StreetSource/
├── index.php                # Login page
├── register.php             # Registration page
├── verify_email.php         # Email verification
├── composer.json / lock     # PHP dependencies
├── sql/                     # Database schema
├── php/                     # Core PHP logic (APIs, order logic, etc.)
├── assets/                  # CSS/JS files
├── supplier/                # Supplier dashboard
├── vendor/                  # Vendor dashboard
├── uploads/                 # File storage (product images, etc.)
```

## How to Run
1. **Requirements:**
   - PHP 7.4+
   - MySQL
   - Composer
   - XAMPP/WAMP/LAMP recommended for local development

2. **Setup:**
   - Import the SQL schema from `sql/schema.sql` into your MySQL database.
   - Copy the project to your web server root (e.g., `htdocs` for XAMPP).
   - Run `composer install` in the project root to install dependencies.
   - Configure database credentials in `php/db.php`.

3. **Start the App:**
   - Open `http://localhost/StreetSource/` in your browser.
   - Register as a supplier or vendor and start using the platform.

## Maintenance
- To remove any leftover test/debug/sample/setup files, run `final_cleanup.bat` in the project root.
- Only core production files will remain after cleanup.

## Security
- All user input is validated and sanitized.
- Role-based access control is enforced.
- Passwords are securely hashed.

## Credits
- Built with PHP, MySQL, Bootstrap, and PHPMailer.
- Developed by [Your Name/Team].

---
For any issues or contributions, please open an issue or pull request.
# 🍲 StreetSource - Raw Material Sourcing Platform

A comprehensive web application connecting street food vendors with trusted suppliers, built with PHP, MySQL, and Bootstrap.

## 🚀 Features

### For Vendors (Buyers)
- **Location-Based Supplier Discovery**: Find suppliers within 10km radius using GPS
- **Product Browsing**: View available raw materials with real-time stock levels
- **Easy Ordering**: Place orders with quantity selection and instant total calculation
- **Order Tracking**: Monitor order status from pending to delivered
- **Supplier Reviews**: Rate and review suppliers to build trust in the community
- **Mobile-Responsive**: Optimized for smartphones and tablets

### For Suppliers (Sellers)
- **Product Management**: Add, edit, and manage product listings with stock levels
- **Order Management**: Accept, process, and mark orders as delivered
- **Performance Analytics**: Track orders, revenue, and customer ratings
- **Vendor Communication**: Direct contact information for order coordination

### Technical Features
- **Geolocation Integration**: HTML5 Geolocation API with Haversine formula for distance calculation
- **Secure Authentication**: PHP session-based login with password hashing
- **Real-time Updates**: AJAX-powered interface for seamless user experience
- **Responsive Design**: Bootstrap-based UI that works on all devices
- **Review System**: Public rating and review system for supplier credibility

## 🛠 Tech Stack

| Layer | Technology |
|-------|------------|
| **Frontend** | HTML5, CSS3, JavaScript |
| **Styling** | Bootstrap 5.1.3 |
| **Backend** | PHP 8+ (Object-Oriented) |
| **Database** | MySQL 8+ |
| **Authentication** | PHP Sessions + Password Hashing |
| **Location** | HTML5 Geolocation API |
| **Server** | Apache (XAMPP/WAMP) |

## 📋 Prerequisites

- **XAMPP/WAMP** (Apache + MySQL + PHP 8+)
- **Modern Web Browser** with geolocation support
- **Internet Connection** for Bootstrap CDN

## ⚡ Quick Setup

### 1. Installation
```bash
# Clone or download to your web server directory
# For XAMPP users:
cd C:\xampp\htdocs\
# Copy the StreetSource folder here
```

### 2. Database Setup
1. Start **XAMPP** and ensure **Apache** and **MySQL** are running
2. Open **phpMyAdmin** (http://localhost/phpmyadmin)
3. Import the database:
   ```sql
   # Navigate to sql/schema.sql and run the entire script
   # This will create the database and insert sample data
   ```

### 3. Configuration
1. Update database credentials in `php/db.php` if needed:
   ```php
   private $host = 'localhost';
   private $db_name = 'streetsource';
   private $username = 'root';
   private $password = '';
   ```

### 4. Access the Application
- **Main URL**: http://localhost/StreetSource/
- **Sample Accounts**:
  - **Vendor**: raju@chaat.com / password
  - **Supplier**: fresh@vegetables.com / password

## 📁 Project Structure

```
StreetSource/
├── index.php              # Landing page and login
├── register.php            # User registration
├── vendor/                 # Vendor dashboard and features
│   ├── dashboard.php       # Main vendor dashboard
│   ├── myorders.php        # Order history
│   └── review.php          # Review and rating system
├── supplier/               # Supplier dashboard and features
│   ├── dashboard.php       # Main supplier dashboard
│   └── orders.php          # Order management
├── php/                    # Backend logic
│   ├── db.php              # Database connection and utilities
│   ├── login.php           # Authentication handler
│   ├── place_order.php     # Order placement
│   ├── get_nearby_suppliers.php # Geolocation-based supplier search
│   ├── update_location.php  # Location update handler
│   ├── update_order_status.php # Order status management
│   └── logout.php          # Session termination
├── assets/                 # Static resources
│   ├── css/
│   │   └── style.css       # Custom styles
│   └── js/
│       └── main.js         # JavaScript functionality
└── sql/
    └── schema.sql          # Database schema and sample data
```

## 🎯 Usage Guide

### For Vendors
1. **Register** as a vendor with business details
2. **Enable location** to find nearby suppliers
3. **Browse products** from suppliers within 10km
4. **Place orders** by selecting quantity and confirming
5. **Track orders** through the order status system
6. **Review suppliers** after successful delivery

### For Suppliers
1. **Register** as a supplier with business information
2. **Add products** with prices, stock levels, and descriptions
3. **Manage orders** by accepting or declining requests
4. **Update order status** as you process and deliver
5. **Monitor performance** through ratings and reviews

## 🔧 Key Features Implementation

### Geolocation-Based Matching
- Uses HTML5 Geolocation API to get user's current position
- Implements Haversine formula for accurate distance calculation
- Filters suppliers within configurable radius (default: 10km)

### Order Management System
- Real-time stock management with automatic deduction
- Status tracking: Pending → Accepted → Delivered
- Transaction management for data consistency

### Review and Rating System
- 5-star rating system with optional text reviews
- Public display of supplier ratings and reviews
- Average rating calculation for supplier credibility

### Mobile-First Design
- Responsive grid system using Bootstrap
- Touch-friendly interface elements
- Optimized for street vendors using mobile devices

## 🎨 UI Components

### Dashboard Cards
- Statistics cards with real-time data
- Product cards with pricing and stock information
- Order cards with status indicators

### Interactive Elements
- Star rating input for reviews
- Location update buttons with loading states
- Modal dialogs for order placement and product management

### Status Indicators
- Color-coded order status badges
- Stock level warnings (low stock highlights)
- Supplier rating displays with stars

## 🔒 Security Features

- **Password Hashing**: bcrypt for secure password storage
- **Session Management**: Secure PHP sessions with role-based access
- **Input Validation**: Server-side validation for all user inputs
- **SQL Injection Prevention**: Prepared statements for database queries
- **Role-based Access Control**: Separate interfaces for vendors and suppliers

## 📊 Database Schema

### Users Table
- Stores both vendors and suppliers with role differentiation
- Includes location coordinates for geolocation features
- Contact information for order coordination

### Products Table
- Supplier-owned product listings with pricing and stock
- Active/inactive status for availability management
- Detailed descriptions and unit measurements

### Orders Table
- Complete order lifecycle from placement to delivery
- Links vendors, suppliers, and products
- Tracks pricing and quantities

### Reviews Table
- Vendor feedback on supplier performance
- Star ratings (1-5) with optional text notes
- Linked to specific orders for authenticity

## 🌟 Advanced Features

### Real-time Updates
- AJAX-powered interface for seamless experience
- Dynamic supplier loading based on location
- Instant order total calculation

### Business Intelligence
- Order statistics and revenue tracking
- Performance metrics for suppliers
- Historical data analysis

### Scalability Considerations
- Modular PHP architecture for easy extension
- Optimized database queries with proper indexing
- Responsive design for various screen sizes

## 🚀 Future Enhancements

### Potential Features
- **Push Notifications**: Real-time order alerts
- **Payment Integration**: Online payment gateway
- **Advanced Analytics**: Business intelligence dashboard
- **Multi-language Support**: Local language options
- **GPS Navigation**: Directions to supplier locations
- **Bulk Ordering**: Multiple products in single order
- **Supplier Discovery**: Advanced search and filtering
- **Mobile App**: Native Android/iOS applications

### Technical Improvements
- **Caching**: Redis/Memcached for better performance
- **API Development**: RESTful API for mobile apps
- **Real-time Communication**: WebSocket integration
- **Image Upload**: Product photos with CDN storage
- **Advanced Security**: Two-factor authentication

## 🤝 Contributing

This project serves as a foundation for connecting street food vendors with suppliers. Contributions for additional features, bug fixes, and improvements are welcome.

### Development Guidelines
- Follow PSR-4 coding standards for PHP
- Use semantic versioning for releases
- Include comprehensive documentation for new features
- Test thoroughly across different devices and browsers

## 📱 Browser Compatibility

- **Chrome 60+** ✅
- **Firefox 55+** ✅  
- **Safari 11+** ✅
- **Edge 79+** ✅
- **Mobile browsers** ✅

## 📞 Support

For issues, questions, or feature requests:
- Review the code documentation
- Check the database schema
- Test with sample data provided

## 📄 License

This project is developed as a demonstration of a real-world web application for connecting street food vendors with suppliers. Feel free to use, modify, and distribute as needed.

---

**Made with ❤️ for India's street food vendors**

*Empowering local businesses through technology*
