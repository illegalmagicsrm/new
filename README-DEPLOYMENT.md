# 🚀 Deployment Guide - Maliha's Miracle E-commerce

## Quick Setup for Hostever (PHP + MySQL)

### 1. Database Setup
1. Create a MySQL database in your Hostever control panel
2. Import the SQL file: `database/create_orders_table.sql`
3. Note down your database credentials

### 2. Upload Files
Upload these files to your hosting:
```
/public_html/
├── api/
│   ├── submit-order.php
│   └── config.php
├── database/
│   └── create_orders_table.sql
└── (your React build files)
```

### 3. Configure Database
Edit `api/config.php` with your actual credentials:
```php
define('DB_HOST', 'localhost');
define('DB_NAME', 'your_actual_database_name');
define('DB_USER', 'your_actual_username');
define('DB_PASS', 'your_actual_password');
```

### 4. Update Domain
Replace `mydomain.com` with your actual domain in:
- `api/config.php`
- `src/components/Checkout.tsx` (if not already done)

### 5. Test the API
Test your endpoint:
```bash
curl -X POST https://yourdomain.com/api/submit-order.php \
  -H "Content-Type: application/json" \
  -d '{"test": "data"}'
```

## 📧 Email Configuration

The system sends emails to:
- **Customer**: Order confirmation with details
- **Admin**: Alert emails to sales@mydomain.com and manager@mydomain.com

Make sure your hosting supports PHP `mail()` function or configure SMTP if needed.

## 🔒 Security Features

✅ **CORS Protection**: Only allows requests from your domain
✅ **SQL Injection Protection**: Uses PDO prepared statements  
✅ **Input Validation**: Validates all required fields
✅ **Error Handling**: Proper error responses
✅ **JSON Validation**: Validates incoming JSON data

## 📊 Database Schema

The `orders` table includes:
- Customer information (name, email, phone, address)
- Shipping details and costs
- Payment method and amounts
- Cart items (stored as JSON)
- Order status and timestamps
- Proper indexing for performance

## 🎯 Payment Integration

Ready for UddoktaPay integration:
1. Get your UddoktaPay credentials
2. Update `config.php` with API keys
3. Implement payment redirect logic
4. Handle payment callbacks

## 📱 Features

✅ **Order Management**: Complete order tracking
✅ **Email Notifications**: Customer + Admin alerts  
✅ **Mobile Responsive**: Works on all devices
✅ **Error Handling**: Graceful error management
✅ **Security**: Production-ready security measures

## 🚀 Go Live Checklist

- [ ] Database created and configured
- [ ] Files uploaded to hosting
- [ ] Config file updated with real credentials
- [ ] Domain updated in all files
- [ ] Test order placed successfully
- [ ] Email notifications working
- [ ] SSL certificate active
- [ ] UddoktaPay integration (when ready)

## 📞 Support

If you need help:
- Check error logs in your hosting control panel
- Test the API endpoint directly
- Verify database connection
- Ensure email function is working

**You're ready to launch! 🎉**