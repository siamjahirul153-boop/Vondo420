<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>StyleMart | Online Fashion Store</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: #f8f9fa;
            color: #333;
            line-height: 1.6;
        }
        
        /* Header Styles */
        header {
            background: linear-gradient(135deg, #6e8efb, #a777e3);
            color: white;
            padding: 15px 0;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            position: sticky;
            top: 0;
            z-index: 100;
        }
        
        .header-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        .logo {
            font-size: 28px;
            font-weight: 700;
            display: flex;
            align-items: center;
        }
        
        .logo i {
            margin-right: 10px;
        }
        
        nav ul {
            display: flex;
            list-style: none;
        }
        
        nav ul li {
            margin-left: 25px;
        }
        
        nav ul li a {
            color: white;
            text-decoration: none;
            font-weight: 500;
            transition: opacity 0.3s;
        }
        
        nav ul li a:hover {
            opacity: 0.8;
        }
        
        .header-icons {
            display: flex;
            align-items: center;
        }
        
        .header-icons div {
            margin-left: 20px;
            cursor: pointer;
            font-size: 18px;
            position: relative;
        }
        
        .cart-count {
            position: absolute;
            top: -8px;
            right: -8px;
            background: #ff4757;
            color: white;
            border-radius: 50%;
            width: 18px;
            height: 18px;
            font-size: 12px;
            display: flex;
            justify-content: center;
            align-items: center;
        }
        
        .user-info {
            display: flex;
            align-items: center;
            cursor: pointer;
            position: relative;
        }
        
        .user-info i {
            margin-right: 8px;
        }
        
        .user-dropdown {
            position: absolute;
            top: 100%;
            right: 0;
            background: white;
            border-radius: 8px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            width: 150px;
            display: none;
            z-index: 101;
            margin-top: 10px;
        }
        
        .user-dropdown.active {
            display: block;
        }
        
        .user-dropdown-item {
            padding: 12px 15px;
            color: #333;
            text-decoration: none;
            display: block;
            transition: background 0.3s;
        }
        
        .user-dropdown-item:hover {
            background: #f1f3f5;
        }
        
        .user-dropdown-item i {
            margin-right: 8px;
            color: #4a6cf7;
        }
        
        /* Main Content Styles */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }
        
        .hero {
            background: linear-gradient(rgba(0,0,0,0.6), rgba(0,0,0,0.6)), url('https://images.unsplash.com/photo-1523381210434-271e8be1f52b?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1770&q=80');
            background-size: cover;
            background-position: center;
            height: 450px;
            border-radius: 12px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            color: white;
            margin-bottom: 40px;
        }
        
        .hero h1 {
            font-size: 48px;
            margin-bottom: 20px;
        }
        
        .hero p {
            font-size: 20px;
            max-width: 700px;
            margin-bottom: 30px;
        }
        
        .btn {
            background: #4a6cf7;
            color: white;
            border: none;
            padding: 14px 30px;
            border-radius: 8px;
            font-size: 16px;
            font-weight: 600;
            cursor: pointer;
            transition: background 0.3s;
        }
        
        .btn:hover {
            background: #3a5cd6;
        }
        
        .btn-outline {
            background: transparent;
            border: 2px solid #4a6cf7;
            color: #4a6cf7;
        }
        
        .btn-outline:hover {
            background: #4a6cf7;
            color: white;
        }
        
        .section-title {
            text-align: center;
            margin: 40px 0 30px;
            color: #2c3e50;
            font-size: 32px;
        }
        
        /* Products Grid */
        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 25px;
            margin-bottom: 50px;
        }
        
        .product-card {
            background: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s;
            cursor: pointer;
        }
        
        .product-card:hover {
            transform: translateY(-5px);
        }
        
        .product-img {
            height: 200px;
            width: 100%;
            object-fit: cover;
        }
        
        .product-info {
            padding: 20px;
        }
        
        .product-title {
            font-size: 18px;
            margin-bottom: 10px;
            color: #2c3e50;
        }
        
        .product-price {
            font-size: 20px;
            font-weight: 700;
            color: #4a6cf7;
            margin-bottom: 15px;
        }
        
        .product-description {
            color: #777;
            margin-bottom: 15px;
            font-size: 14px;
        }
        
        .product-actions {
            display: flex;
            gap: 10px;
        }
        
        .add-to-cart, .buy-now {
            flex: 1;
            padding: 10px;
            border: none;
            border-radius: 6px;
            cursor: pointer;
            font-weight: 600;
            transition: background 0.3s;
        }
        
        .add-to-cart {
            background: #4a6cf7;
            color: white;
        }
        
        .add-to-cart:hover {
            background: #3a5cd6;
        }
        
        .buy-now {
            background: #ff4757;
            color: white;
        }
        
        .buy-now:hover {
            background: #ff3742;
        }
        
        /* Auth Container */
        .auth-popup {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.7);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 1000;
            display: none;
        }
        
        .auth-container {
            background: white;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
            overflow: hidden;
            width: 450px;
            max-width: 90%;
            max-height: 90vh;
            overflow-y: auto;
        }
        
        .auth-header {
            background: #4a6cf7;
            color: white;
            text-align: center;
            padding: 25px 20px;
            position: relative;
        }
        
        .close-auth {
            position: absolute;
            top: 20px;
            right: 20px;
            cursor: pointer;
            font-size: 20px;
        }
        
        .auth-header h1 {
            font-weight: 600;
            font-size: 28px;
        }
        
        .auth-form-container {
            padding: 30px;
        }
        
        /* Dashboard Container */
        .dashboard-container {
            display: none;
            margin: 30px 0;
        }
        
        .dashboard-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 30px;
            padding-bottom: 15px;
            border-bottom: 2px solid #eee;
        }
        
        .dashboard-title {
            font-size: 28px;
            color: #2c3e50;
        }
        
        .dashboard-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 25px;
        }
        
        @media (max-width: 900px) {
            .dashboard-content {
                grid-template-columns: 1fr;
            }
        }
        
        .dashboard-card {
            background: white;
            border-radius: 12px;
            padding: 25px;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.05);
        }
        
        .dashboard-card h3 {
            color: #4a6cf7;
            margin-bottom: 20px;
            padding-bottom: 10px;
            border-bottom: 2px solid #f1f3f5;
            display: flex;
            align-items: center;
        }
        
        .dashboard-card h3 i {
            margin-right: 10px;
        }
        
        /* Product Detail */
        .product-detail {
            display: none;
            background: white;
            border-radius: 15px;
            padding: 30px;
            margin: 30px 0;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.1);
        }
        
        .product-detail-content {
            display: flex;
            gap: 40px;
        }
        
        .product-detail-img {
            flex: 1;
            max-width: 400px;
            border-radius: 10px;
            overflow: hidden;
        }
        
        .product-detail-img img {
            width: 100%;
            height: auto;
            object-fit: cover;
        }
        
        .product-detail-info {
            flex: 1;
        }
        
        .product-detail-title {
            font-size: 32px;
            margin-bottom: 15px;
            color: #2c3e50;
        }
        
        .product-detail-price {
            font-size: 28px;
            color: #4a6cf7;
            margin-bottom: 20px;
            font-weight: 700;
        }
        
        .product-detail-description {
            margin-bottom: 25px;
            line-height: 1.8;
            color: #555;
        }
        
        .product-detail-actions {
            display: flex;
            gap: 15px;
            margin-top: 30px;
        }
        
        /* Reviews Section */
        .reviews-section {
            margin-top: 40px;
            padding-top: 30px;
            border-top: 1px solid #eee;
        }
        
        .reviews-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 25px;
        }
        
        .reviews-title {
            font-size: 24px;
            color: #2c3e50;
        }
        
        .review-form {
            background: #f8f9fa;
            padding: 20px;
            border-radius: 10px;
            margin-bottom: 30px;
        }
        
        .review-form h4 {
            margin-bottom: 15px;
            color: #2c3e50;
        }
        
        .rating {
            display: flex;
            margin-bottom: 15px;
        }
        
        .rating i {
            color: #ddd;
            cursor: pointer;
            font-size: 24px;
            margin-right: 5px;
            transition: color 0.3s;
        }
        
        .rating i.active {
            color: #ffc107;
        }
        
        .review-text {
            width: 100%;
            padding: 15px;
            border: 1px solid #ddd;
            border-radius: 8px;
            margin-bottom: 15px;
            resize: vertical;
            min-height: 100px;
        }
        
        .review-image-upload {
            margin-bottom: 15px;
        }
        
        .review-image-upload label {
            display: block;
            margin-bottom: 8px;
            font-weight: 500;
            color: #444;
        }
        
        .reviews-list {
            margin-top: 30px;
        }
        
        .review-item {
            padding: 20px 0;
            border-bottom: 1px solid #eee;
        }
        
        .review-header {
            display: flex;
            justify-content: space-between;
            margin-bottom: 10px;
            align-items: center;
        }
        
        .reviewer-name {
            font-weight: 600;
            color: #2c3e50;
        }
        
        .review-date {
            color: #777;
            font-size: 14px;
        }
        
        .review-rating {
            color: #ffc107;
            margin-bottom: 10px;
        }
        
        .review-content {
            color: #555;
            line-height: 1.6;
            margin-bottom: 15px;
        }
        
        .review-images {
            display: flex;
            gap: 10px;
            flex-wrap: wrap;
        }
        
        .review-image {
            width: 80px;
            height: 80px;
            object-fit: cover;
            border-radius: 8px;
        }
        
        /* Cart */
        .cart-container {
            display: none;
            background: white;
            border-radius: 15px;
            padding: 30px;
            margin: 30px 0;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.1);
        }
        
        .cart-title {
            font-size: 28px;
            margin-bottom: 25px;
            color: #2c3e50;
            padding-bottom: 15px;
            border-bottom: 2px solid #eee;
        }
        
        .cart-items {
            margin-bottom: 30px;
        }
        
        .cart-item {
            display: flex;
            align-items: center;
            padding: 20px 0;
            border-bottom: 1px solid #eee;
        }
        
        .cart-item-img {
            width: 100px;
            height: 100px;
            object-fit: cover;
            border-radius: 8px;
            margin-right: 20px;
        }
        
        .cart-item-info {
            flex: 1;
        }
        
        .cart-item-title {
            font-size: 18px;
            margin-bottom: 8px;
            color: #2c3e50;
        }
        
        .cart-item-price {
            font-size: 18px;
            color: #4a6cf7;
            font-weight: 600;
        }
        
        .cart-item-quantity {
            display: flex;
            align-items: center;
            margin: 10px 0;
        }
        
        .quantity-btn {
            width: 30px;
            height: 30px;
            background: #f1f3f5;
            border: none;
            border-radius: 4px;
            font-size: 16px;
            cursor: pointer;
        }
        
        .quantity-input {
            width: 50px;
            height: 30px;
            text-align: center;
            margin: 0 10px;
            border: 1px solid #ddd;
            border-radius: 4px;
        }
        
        .cart-item-remove {
            color: #ff4757;
            background: none;
            border: none;
            cursor: pointer;
            font-size: 14px;
        }
        
        .cart-total {
            text-align: right;
            font-size: 24px;
            margin-bottom: 25px;
            color: #2c3e50;
        }
        
        .cart-total span {
            color: #4a6cf7;
            font-weight: 700;
        }
        
        .cart-actions {
            display: flex;
            justify-content: flex-end;
            gap: 15px;
        }
        
        /* Checkout */
        .checkout-container {
            display: none;
            background: white;
            border-radius: 15px;
            padding: 30px;
            margin: 30px 0;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.1);
        }
        
        .checkout-title {
            font-size: 28px;
            margin-bottom: 25px;
            color: #2c3e50;
            padding-bottom: 15px;
            border-bottom: 2px solid #eee;
        }
        
        .checkout-form {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
        }
        
        .form-group {
            margin-bottom: 20px;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 500;
            color: #444;
        }
        
        .form-group input,
        .form-group select,
        .form-group textarea {
            width: 100%;
            padding: 14px 15px;
            border: 1px solid #ddd;
            border-radius: 8px;
            font-size: 16px;
            transition: border 0.3s;
        }
        
        .form-group input:focus,
        .form-group select:focus,
        .form-group textarea:focus {
            border-color: #4a6cf7;
            outline: none;
        }
        
        .form-group-full {
            grid-column: 1 / -1;
        }
        
        .payment-methods {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 15px;
            margin: 20px 0;
        }
        
        .payment-method {
            text-align: center;
            padding: 15px;
            border: 2px solid #eee;
            border-radius: 8px;
            cursor: pointer;
            transition: all 0.3s;
        }
        
        .payment-method.selected {
            border-color: #4a6cf7;
            background: #f0f4ff;
        }
        
        .payment-method i {
            font-size: 30px;
            margin-bottom: 10px;
            color: #4a6cf7;
        }
        
        .payment-method img {
            height: 30px;
            margin-bottom: 10px;
            object-fit: contain;
        }
        
        .checkout-summary {
            background: #f8f9fa;
            padding: 20px;
            border-radius: 8px;
            margin-top: 20px;
        }
        
        .checkout-summary h3 {
            margin-bottom: 15px;
            color: #2c3e50;
        }
        
        .checkout-item {
            display: flex;
            justify-content: space-between;
            margin-bottom: 10px;
        }
        
        .checkout-total {
            display: flex;
            justify-content: space-between;
            margin-top: 15px;
            padding-top: 15px;
            border-top: 1px solid #ddd;
            font-weight: 700;
            font-size: 18px;
        }
        
        /* Order History */
        .orders-table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 20px;
        }
        
        .orders-table th,
        .orders-table td {
            padding: 12px 15px;
            text-align: left;
            border-bottom: 1px solid #eee;
        }
        
        .orders-table th {
            background: #f8f9fa;
            font-weight: 600;
            color: #2c3e50;
        }
        
        .orders-table tr:hover {
            background: #f8f9fa;
        }
        
        .order-status {
            padding: 5px 10px;
            border-radius: 20px;
            font-size: 12px;
            font-weight: 600;
        }
        
        .status-processing {
            background: #fff4e6;
            color: #f76707;
        }
        
        .status-shipped {
            background: #dbf2fd;
            color: #0c6dfd;
        }
        
        .status-delivered {
            background: #d8f5e2;
            color: #2f9e44;
        }
        
        /* Footer Styles */
        footer {
            background: #2c3e50;
            color: white;
            padding: 40px 0 20px;
            margin-top: 60px;
        }
        
        .footer-container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
        }
        
        .footer-section h3 {
            font-size: 20px;
            margin-bottom: 20px;
            position: relative;
            padding-bottom: 10px;
        }
        
        .footer-section h3::after {
            content: "";
            position: absolute;
            bottom: 0;
            left: 0;
            width: 50px;
            height: 2px;
            background: #4a6cf7;
        }
        
        .footer-section p {
            margin-bottom: 15px;
        }
        
        .footer-section ul {
            list-style: none;
        }
        
        .footer-section ul li {
            margin-bottom: 10px;
        }
        
        .footer-section ul li a {
            color: #ddd;
            text-decoration: none;
            transition: color 0.3s;
        }
        
        .footer-section ul li a:hover {
            color: #4a6cf7;
        }
        
        .footer-bottom {
            text-align: center;
            padding-top: 30px;
            border-top: 1px solid #394c61;
            margin-top: 30px;
        }
        
        /* Responsive Styles */
        @media (max-width: 768px) {
            .header-container {
                flex-direction: column;
                text-align: center;
            }
            
            nav ul {
                margin-top: 15px;
                justify-content: center;
            }
            
            nav ul li {
                margin: 0 10px;
            }
            
            .header-icons {
                margin-top: 15px;
            }
            
            .hero h1 {
                font-size: 36px;
            }
            
            .hero p {
                font-size: 18px;
            }
            
            .product-detail-content {
                flex-direction: column;
            }
            
            .product-detail-img {
                max-width: 100%;
            }
            
            .checkout-form {
                grid-template-columns: 1fr;
            }
        }
        
        /* Include the previous auth styles here */
        .tabs {
            display: flex;
            margin-bottom: 25px;
            border-bottom: 2px solid #eee;
            justify-content: center;
        }
        
        .tab {
            padding: 12px 20px;
            cursor: pointer;
            font-weight: 600;
            color: #777;
            transition: all 0.3s;
            text-align: center;
        }
        
        .tab.active {
            color: #4a6cf7;
            border-bottom: 3px solid #4a6cf7;
        }
        
        .form {
            display: none;
        }
        
        .form.active {
            display: block;
            animation: fadeIn 0.5s;
        }
        
        .input-group {
            margin-bottom: 20px;
            position: relative;
        }
        
        .input-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 500;
            color: #444;
        }
        
        .input-group input {
            width: 100%;
            padding: 14px 15px;
            border: 1px solid #ddd;
            border-radius: 8px;
            font-size: 16px;
            transition: border 0.3s;
        }
        
        .input-group input:focus {
            border-color: #4a6cf7;
            outline: none;
        }
        
        .input-group i {
            position: absolute;
            right: 15px;
            top: 42px;
            color: #777;
        }
        
        .auth-btn {
            width: 100%;
            padding: 14px;
            background: #4a6cf7;
            color: white;
            border: none;
            border-radius: 8px;
            font-size: 16px;
            font-weight: 600;
            cursor: pointer;
            transition: background 0.3s;
        }
        
        .auth-btn:hover {
            background: #3a5cd6;
        }
        
        .message {
            padding: 15px;
            margin: 20px 0;
            border-radius: 8px;
            text-align: center;
            display: none;
        }
        
        .success {
            background: #d4edda;
            color: #155724;
            border: 1px solid #c3e6cb;
        }
        
        .error {
            background: #f8d7da;
            color: #721c24;
            border: 1px solid #f5c6cb;
        }
        
        .forgot-password {
            text-align: right;
            margin-top: -10px;
            margin-bottom: 20px;
        }
        
        .forgot-password a {
            color: #4a6cf7;
            text-decoration: none;
            font-size: 14px;
            cursor: pointer;
        }
        
        .divider {
            text-align: center;
            margin: 25px 0;
            position: relative;
        }
        
        .divider::before {
            content: "";
            position: absolute;
            left: 0;
            top: 50%;
            height: 1px;
            width: 100%;
            background: #ddd;
        }
        
        .divider span {
            background: white;
            position: relative;
            padding: 0 15px;
            color: #777;
        }
        
        .social-login {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin-bottom: 20px;
        }
        
        .social-btn {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 20px;
            cursor: pointer;
        }
        
        .facebook {
            background: #3b5998;
        }
        
        .google {
            background: #db4a39;
        }
        
        .twitter {
            background: #1da1f2;
        }
        
        .auth-footer {
            text-align: center;
            margin-top: 25px;
            color: #777;
            font-size: 14px;
        }
        
        .auth-footer a {
            color: #4a6cf7;
            text-decoration: none;
            cursor: pointer;
        }
        
        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(10px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="header-container">
            <div class="logo">
                <i class="fas fa-shopping-bag"></i> StyleMart
            </div>
            <nav>
                <ul>
                    <li><a href="#" class="nav-home">Home</a></li>
                    <li><a href="#">Products</a></li>
                    <li><a href="#">Categories</a></li>
                    <li><a href="#">Deals</a></li>
                    <li><a href="#">About</a></li>
                </ul>
            </nav>
            <div class="header-icons">
                <div class="user-info" id="auth-icon">
                    <i class="fas fa-user"></i>
                    <span id="user-status">Login</span>
                    <div class="user-dropdown" id="user-dropdown">
                        <a href="#" class="user-dropdown-item" id="view-profile">
                            <i class="fas fa-user-circle"></i> Profile
                        </a>
                        <a href="#" class="user-dropdown-item" id="logout-btn">
                            <i class="fas fa-sign-out-alt"></i> Logout
                        </a>
                    </div>
                </div>
                <div id="cart-icon">
                    <i class="fas fa-shopping-cart"></i>
                    <span class="cart-count">0</span>
                </div>
            </div>
        </div>
    </header>

    <!-- Main Content -->
    <div class="container">
        <!-- Hero Section -->
        <div class="hero">
            <h1>Summer Collection 2023</h1>
            <p>Discover the latest trends in fashion and get up to 40% off on selected items</p>
            <button class="btn">Shop Now</button>
        </div>

        <!-- Dashboard Section -->
        <div class="dashboard-container" id="dashboard-container">
            <div class="dashboard-header">
                <h2 class="dashboard-title">My Dashboard</h2>
                <button class="btn btn-outline" id="continue-shopping">Continue Shopping</button>
            </div>
            
            <div class="dashboard-content">
                <div class="dashboard-card">
                    <h3><i class="fas fa-user"></i> Personal Information</h3>
                    <p><strong>Name:</strong> <span id="infoName">-</span></p>
                    <p><strong>Email:</strong> <span id="infoEmail">-</span></p>
                    <p><strong>Member since:</strong> <span id="memberSince">-</span></p>
                    <p><strong>Total orders:</strong> <span id="total-orders">0</span></p>
                    <p><strong>Total spent:</strong> $<span id="total-spent">0</span></p>
                </div>
                
                <div class="dashboard-card">
                    <h3><i class="fas fa-shopping-bag"></i> Recent Orders</h3>
                    <div id="order-history">
                        <p class="no-orders">You haven't placed any orders yet.</p>
                    </div>
                </div>
                
                <div class="dashboard-card">
                    <h3><i class="fas fa-shopping-cart"></i> Saved Cart</h3>
                    <div id="saved-cart">
                        <p class="no-items">Your cart is empty</p>
                    </div>
                </div>
                
                <div class="dashboard-card">
                    <h3><i class="fas fa-heart"></i> Wishlist</h3>
                    <div id="wishlist">
                        <p class="no-items">Your wishlist is empty</p>
                    </div>
                </div>
            </div>
        </div>

        <!-- Featured Products -->
        <h2 class="section-title">Featured Products</h2>
        <div class="products-grid" id="products-grid">
            <!-- Products will be loaded by JavaScript -->
        </div>

        <!-- Product Detail -->
        <div class="product-detail" id="product-detail">
            <div class="product-detail-content">
                <div class="product-detail-img">
                    <img id="detail-img" src="" alt="Product Image">
                </div>
                <div class="product-detail-info">
                    <h2 class="product-detail-title" id="detail-title"></h2>
                    <p class="product-detail-price" id="detail-price"></p>
                    <p class="product-detail-description" id="detail-description"></p>
                    
                    <div class="product-detail-actions">
                        <button class="btn add-to-cart" id="detail-add-cart">Add to Cart</button>
                        <button class="btn buy-now" id="detail-buy-now">Buy Now</button>
                    </div>
                    
                    <!-- Reviews Section -->
                    <div class="reviews-section">
                        <div class="reviews-header">
                            <h3 class="reviews-title">Customer Reviews</h3>
                        </div>
                        
                        <div class="review-form">
                            <h4>Write a Review</h4>
                            <div class="rating" id="review-rating">
                                <i class="fas fa-star" data-value="1"></i>
                                <i class="fas fa-star" data-value="2"></i>
                                <i class="fas fa-star" data-value="3"></i>
                                <i class="fas fa-star" data-value="4"></i>
                                <i class="fas fa-star" data-value="5"></i>
                            </div>
                            <textarea class="review-text" placeholder="Share your experience with this product"></textarea>
                            <div class="review-image-upload">
                                <label>Upload images (optional):</label>
                                <input type="file" accept="image/*" multiple>
                            </div>
                            <button class="btn">Submit Review</button>
                        </div>
                        
                        <div class="reviews-list" id="reviews-list">
                            <div class="review-item">
                                <div class="review-header">
                                    <span class="reviewer-name">John Doe</span>
                                    <span class="review-date">October 15, 2023</span>
                                </div>
                                <div class="review-rating">
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                </div>
                                <p class="review-content">This product exceeded my expectations! The quality is outstanding and it fits perfectly. I would definitely recommend it to others.</p>
                                <div class="review-images">
                                    <img src="https://images.unsplash.com/photo-1523381210434-271e8be1f52b?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=200&q=80" alt="Review image" class="review-image">
                                </div>
                            </div>
                            
                            <div class="review-item">
                                <div class="review-header">
                                    <span class="reviewer-name">Jane Smith</span>
                                    <span class="review-date">October 10, 2023</span>
                                </div>
                                <div class="review-rating">
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                    <i class="far fa-star"></i>
                                </div>
                                <p class="review-content">Good product overall, but the sizing runs a bit small. I would recommend ordering a size up.</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <!-- Cart -->
        <div class="cart-container" id="cart-container">
            <h2 class="cart-title">Your Shopping Cart</h2>
            
            <div class="cart-items" id="cart-items">
                <!-- Cart items will be loaded by JavaScript -->
            </div>
            
            <div class="cart-total">
                Total: <span id="cart-total-amount">$0.00</span>
            </div>
            
            <div class="cart-actions">
                <button class="btn btn-outline" id="continue-shopping-cart">Continue Shopping</button>
                <button class="btn" id="proceed-checkout">Proceed to Checkout</button>
            </div>
        </div>

        <!-- Checkout -->
        <div class="checkout-container" id="checkout-container">
            <h2 class="checkout-title">Checkout</h2>
            
            <form class="checkout-form" id="checkout-form">
                <div class="form-group form-group-full">
                    <h3>Shipping Information</h3>
                </div>
                
                <div class="form-group">
                    <label for="checkout-name">Full Name</label>
                    <input type="text" id="checkout-name" required>
                </div>
                
                <div class="form-group">
                    <label for="checkout-email">Email</label>
                    <input type="email" id="checkout-email" required>
                </div>
                
                <div class="form-group">
                    <label for="checkout-phone">Phone Number</label>
                    <input type="tel" id="checkout-phone" required>
                </div>
                
                <div class="form-group form-group-full">
                    <label for="checkout-address">Shipping Address</label>
                    <textarea id="checkout-address" rows="3" required></textarea>
                </div>
                
                <div class="form-group">
                    <label for="checkout-city">City</label>
                    <input type="text" id="checkout-city" required>
                </div>
                
                <div class="form-group">
                    <label for="checkout-zip">ZIP Code</label>
                    <input type="text" id="checkout-zip" required>
                </div>
                
                <div class="form-group form-group-full">
                    <h3>Payment Method</h3>
                    <div class="payment-methods">
                        <div class="payment-method" data-method="credit-card">
                            <i class="fas fa-credit-card"></i>
                            <p>Credit Card</p>
                        </div>
                        <div class="payment-method" data-method="paypal">
                            <i class="fab fa-paypal"></i>
                            <p>PayPal</p>
                        </div>
                        <div class="payment-method" data-method="bkash">
                            <img src="https://seeklogo.com/images/B/bkash-logo-2B5A5D6403-seeklogo.com.png" alt="bKash">
                            <p>bKash</p>
                        </div>
                        <div class="payment-method" data-method="nagad">
                            <img src="https://seeklogo.com/images/N/nagad-logo-4B7D698040-seeklogo.com.png" alt="Nagad">
                            <p>Nagad</p>
                        </div>
                        <div class="payment-method" data-method="bank-transfer">
                            <i class="fas fa-university"></i>
                            <p>Bank Transfer</p>
                        </div>
                    </div>
                </div>
                
                <div class="form-group form-group-full">
                    <div class="checkout-summary">
                        <h3>Order Summary</h3>
                        <div id="checkout-summary-items">
                            <!-- Order summary will be loaded by JavaScript -->
                        </div>
                        <div class="checkout-total">
                            <span>Total:</span>
                            <span id="checkout-total-amount">$0.00</span>
                        </div>
                    </div>
                </div>
                
                <div class="form-group form-group-full">
                    <button type="submit" class="btn" style="padding: 15px; font-size: 18px;">Complete Purchase</button>
                </div>
            </form>
        </div>
    </div>

    <!-- Auth Popup -->
    <div class="auth-popup" id="auth-popup">
        <div class="auth-container">
            <div class="auth-header">
                <h1>Welcome to StyleMart</h1>
                <p>Sign up or log in to your account</p>
                <div class="close-auth" id="close-auth">
                    <i class="fas fa-times"></i>
                </div>
            </div>
            
            <div class="auth-form-container">
                <div class="tabs">
                    <div class="tab active" id="login-tab">Login</div>
                    <div class="tab" id="signup-tab">Sign Up</div>
                </div>
                
                <div class="message" id="message"></div>
                
                <form class="form active" id="login-form">
                    <div class="input-group">
                        <label for="login-email">Email</label>
                        <input type="email" id="login-email" placeholder="Enter your email" required>
                        <i class="fas fa-envelope"></i>
                    </div>
                    
                    <div class="input-group">
                        <label for="login-password">Password</label>
                        <input type="password" id="login-password" placeholder="Enter your password" required>
                        <i class="fas fa-lock"></i>
                    </div>
                    
                    <div class="forgot-password">
                        <a href="#" id="forgot-password">Forgot password?</a>
                    </div>
                    
                    <button type="submit" class="auth-btn">Login</button>
                    
                    <div class="divider">
                        <span>Or continue with</span>
                    </div>
                    
                    <div class="social-login">
                        <div class="social-btn facebook">
                            <i class="fab fa-facebook-f"></i>
                        </div>
                        <div class="social-btn google">
                            <i class="fab fa-google"></i>
                        </div>
                        <div class="social-btn twitter">
                            <i class="fab fa-twitter"></i>
                        </div>
                    </div>
                    
                    <div class="auth-footer">
                        Don't have an account? <a href="#" id="goto-signup">Sign up</a>
                    </div>
                </form>
                
                <form class="form" id="signup-form">
                    <div class="input-group">
                        <label for="signup-name">Full Name</label>
                        <input type="text" id="signup-name" placeholder="Enter your full name" required>
                        <i class="fas fa-user"></i>
                    </div>
                    
                    <div class="input-group">
                        <label for="signup-email">Email</label>
                        <input type="email" id="signup-email" placeholder="Enter your email" required>
                        <i class="fas fa-envelope"></i>
                    </div>
                    
                    <div class="input-group">
                        <label for="signup-password">Password</label>
                        <input type="password" id="signup-password" placeholder="Create a password" required>
                        <i class="fas fa-lock"></i>
                    </div>
                    
                    <div class="input-group">
                        <label for="signup-confirm">Confirm Password</label>
                        <input type="password" id="signup-confirm" placeholder="Confirm your password" required>
                        <i class="fas fa-lock"></i>
                    </div>
                    
                    <button type="submit" class="auth-btn">Create Account</button>
                    
                    <div class="auth-footer">
                        Already have an account? <a href="#" id="goto-login">Login</a>
                    </div>
                </form>
            </div>
        </div>
    </div>

    <!-- Footer -->
    <footer>
        <div class="footer-container">
            <div class="footer-section">
                <h3>About StyleMart</h3>
                <p>StyleMart is a leading online fashion retailer offering trendy clothing, accessories, and footwear for men and women.</p>
            </div>
            
            <div class="footer-section">
                <h3>Quick Links</h3>
                <ul>
                    <li><a href="#">Home</a></li>
                    <li><a href="#">Products</a></li>
                    <li><a href="#">Categories</a></li>
                    <li><a href="#">Deals</a></li>
                    <li><a href="#">About Us</a></li>
                </ul>
            </div>
            
            <div class="footer-section">
                <h3>Customer Service</h3>
                <ul>
                    <li><a href="#">Contact Us</a></li>
                    <li><a href="#">FAQs</a></li>
                    <li><a href="#">Returns & Exchanges</a></li>
                    <li><a href="#">Shipping Information</a></li>
                    <li><a href="#">Size Guide</a></li>
                </ul>
            </div>
            
            <div class="footer-section">
                <h3>Contact Info</h3>
                <p><i class="fas fa-map-marker-alt"></i> 123 Fashion Street, New York, NY</p>
                <p><i class="fas fa-phone"></i> +1 (555) 123-4567</p>
                <p><i class="fas fa-envelope"></i> support@stylemart.com</p>
            </div>
        </div>
        
        <div class="footer-bottom">
            <p>&copy; 2023 StyleMart. All rights reserved.</p>
        </div>
    </footer>

    <script>
        // Sample product data
        const products = [
            {
                id: 1,
                name: "Classic Fit T-Shirt",
                price: 29.99,
                image: "https://images.unsplash.com/photo-1525507119028-ed4c629a60a3?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8NHx8dCUyMHNoaXJ0fGVufDB8fDB8fHww&auto=format&fit=crop&w=500&q=60",
                description: "100% cotton, comfortable and stylish everyday t-shirt. Perfect for casual wear or workouts. Available in multiple colors."
            },
            {
                id: 2,
                name: "Slim Fit Jeans",
                price: 49.99,
                image: "https://images.unsplash.com/photo-1591047139829-d91aecb6caea?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8M3x8amVhbnN8ZW58MHx8MHx8fDA%3D&auto=format&fit=crop&w=500&q=60",
                description: "Comfortable stretch denim with modern fit. These jeans feature a slim fit through the hip and thigh with a tapered leg opening."
            },
            {
                id: 3,
                name: "Running Sneakers",
                price: 89.99,
                image: "https://images.unsplash.com/photo-1542291026-7eec264c27ff?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8Mnx8c2hvZXN8ZW58MHx8MHx8fDA%3D&auto=format&fit=crop&w=500&q=60",
                description: "Lightweight and comfortable running shoes with extra cushioning. Designed for maximum performance and comfort during runs."
            },
            {
                id: 4,
                name: "Classic Watch",
                price: 129.99,
                image: "https://images.unsplash.com/photo-1582142306909-195724d3a58c?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MTJ8fHdhdGNofGVufDB8fDB8fHww&auto=format&fit=crop&w=500&q=60",
                description: "Elegant timepiece with leather strap. Features a minimalist design with date function and water resistance up to 50m."
            },
            {
                id: 5,
                name: "Summer Dress",
                price: 59.99,
                image: "https://images.unsplash.com/photo-1583744946564-b52ae1c685c7?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8NHx8d29tZW4lMjBdcmVzc3xlbnwwfHwwfHx8MA%3D%3D&auto=format&fit=crop&w=500&q=60",
                description: "Flowy and comfortable summer dress with floral pattern. Perfect for warm weather and special occasions."
            },
            {
                id: 6,
                name: "Leather Handbag",
                price: 79.99,
                image: "https://images.unsplash.com/photo-1618932260643-eee4a2f652a6?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MTB8fGhhbmRiYWd8ZW58MHx8MHx8fDA%3D&auto=format&fit=crop&w=500&q=60",
                description: "Genuine leather handbag with multiple compartments. Features a spacious interior with organizational pockets."
            },
            {
                id: 7,
                name: "Formal Shirt",
                price: 39.99,
                image: "https://images.unsplash.com/photo-1600185365483-26d7a4cc7519?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MTh8fHNoaXJ0fGVufDB8fDB8fHww&auto=format&fit=crop&w=500&q=60",
                description: "Classic formal shirt for office wear. Made from high-quality cotton with a comfortable fit and crisp look."
            },
            {
                id: 8,
                name: "Designer Sunglasses",
                price: 69.99,
                image: "https://images.unsplash.com/photo-1521335629791-ce4aec67dd15?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8NTZ8fGFjY2Vzc29yaWVzfGVufDB8fDB8fHww&auto=format&fit=crop&w=500&q=60",
                description: "UV protected stylish sunglasses with polarized lenses. Features a lightweight frame and comfortable fit."
            }
        ];

        // DOM Elements
        const authPopup = document.getElementById('auth-popup');
        const dashboardContainer = document.getElementById('dashboard-container');
        const loginTab = document.getElementById('login-tab');
        const signupTab = document.getElementById('signup-tab');
        const loginForm = document.getElementById('login-form');
        const signupForm = document.getElementById('signup-form');
        const gotoLogin = document.getElementById('goto-login');
        const gotoSignup = document.getElementById('goto-signup');
        const messageEl = document.getElementById('message');
        const closeAuth = document.getElementById('close-auth');
        const authIcon = document.getElementById('auth-icon');
        const userStatus = document.getElementById('user-status');
        const userDropdown = document.getElementById('user-dropdown');
        const logoutBtn = document.getElementById('logout-btn');
        const viewProfile = document.getElementById('view-profile');
        const cartIcon = document.getElementById('cart-icon');
        const cartCount = document.querySelector('.cart-count');
        const productsGrid = document.getElementById('products-grid');
        const productDetail = document.getElementById('product-detail');
        const cartContainer = document.getElementById('cart-container');
        const checkoutContainer = document.getElementById('checkout-container');
        const checkoutForm = document.getElementById('checkout-form');
        const continueShopping = document.getElementById('continue-shopping');
        const continueShoppingCart = document.getElementById('continue-shopping-cart');
        const proceedCheckout = document.getElementById('proceed-checkout');
        const navHome = document.querySelector('.nav-home');
        const forgotPassword = document.getElementById('forgot-password');
        const reviewRating = document.getElementById('review-rating');
        const savedCart = document.getElementById('saved-cart');

        // State variables
        let currentUser = JSON.parse(localStorage.getItem('currentUser') || 'null');
        let cart = JSON.parse(localStorage.getItem('cart') || '[]');
        let orders = JSON.parse(localStorage.getItem('orders') || '[]');
        let currentProduct = null;

        // Initialize the page
        function init() {
            renderProducts();
            updateCartUI();
            checkLoggedIn();
            loadOrders();
            loadSavedCart();
            
            // Event listeners
            authIcon.addEventListener('click', toggleAuthPopup);
            closeAuth.addEventListener('click', closeAuthPopup);
            cartIcon.addEventListener('click', openCart);
            continueShopping.addEventListener('click', showHomepage);
            continueShoppingCart.addEventListener('click', showHomepage);
            proceedCheckout.addEventListener('click', openCheckout);
            navHome.addEventListener('click', showHomepage);
            forgotPassword.addEventListener('click', handleForgotPassword);
            logoutBtn.addEventListener('click', handleLogout);
            viewProfile.addEventListener('click', showDashboard);
            
            // User dropdown
            authIcon.addEventListener('click', function(e) {
                if (currentUser) {
                    e.stopPropagation();
                    userDropdown.classList.toggle('active');
                }
            });
            
            document.addEventListener('click', function() {
                userDropdown.classList.remove('active');
            });
            
            // Auth tab switching
            loginTab.addEventListener('click', () => switchAuthTab('login'));
            signupTab.addEventListener('click', () => switchAuthTab('signup'));
            gotoLogin.addEventListener('click', (e) => {
                e.preventDefault();
                switchAuthTab('login');
            });
            gotoSignup.addEventListener('click', (e) => {
                e.preventDefault();
                switchAuthTab('signup');
            });
            
            // Payment method selection
            document.querySelectorAll('.payment-method').forEach(method => {
                method.addEventListener('click', function() {
                    document.querySelectorAll('.payment-method').forEach(m => m.classList.remove('selected'));
                    this.classList.add('selected');
                });
            });
            
            // Checkout form submission
            checkoutForm.addEventListener('submit', function(e) {
                e.preventDefault();
                completePurchase();
            });
            
            // Auth form submissions
            loginForm.addEventListener('submit', handleLogin);
            signupForm.addEventListener('submit', handleSignup);
            
            // Review rating
            reviewRating.querySelectorAll('i').forEach(star => {
                star.addEventListener('click', function() {
                    const value = this.getAttribute('data-value');
                    setRating(value);
                });
            });
        }

        // Render products to the grid
        function renderProducts() {
            productsGrid.innerHTML = '';
            products.forEach(product => {
                const productCard = document.createElement('div');
                productCard.className = 'product-card';
                productCard.innerHTML = `
                    <img src="${product.image}" alt="${product.name}" class="product-img">
                    <div class="product-info">
                        <h3 class="product-title">${product.name}</h3>
                        <p class="product-price">$${product.price.toFixed(2)}</p>
                        <p class="product-description">${product.description.substring(0, 60)}...</p>
                        <div class="product-actions">
                            <button class="add-to-cart" data-id="${product.id}">Add to Cart</button>
                            <button class="buy-now" data-id="${product.id}">Buy Now</button>
                        </div>
                    </div>
                `;
                productsGrid.appendChild(productCard);
                
                // Add event listeners to the product card
                productCard.querySelector('.add-to-cart').addEventListener('click', function(e) {
                    e.stopPropagation();
                    addToCart(product.id);
                });
                
                productCard.querySelector('.buy-now').addEventListener('click', function(e) {
                    e.stopPropagation();
                    buyNow(product.id);
                });
                
                productCard.addEventListener('click', function() {
                    showProductDetail(product.id);
                });
            });
        }

        // Show product detail
        function showProductDetail(productId) {
            const product = products.find(p => p.id === productId);
            if (!product) return;
            
            currentProduct = product;
            
            document.getElementById('detail-img').src = product.image;
            document.getElementById('detail-title').textContent = product.name;
            document.getElementById('detail-price').textContent = `$${product.price.toFixed(2)}`;
            document.getElementById('detail-description').textContent = product.description;
            
            // Add event listeners to detail buttons
            document.getElementById('detail-add-cart').onclick = () => addToCart(product.id);
            document.getElementById('detail-buy-now').onclick = () => buyNow(product.id);
            
            // Hide other sections and show product detail
            hideAllSections();
            productDetail.style.display = 'block';
        }

        // Set rating stars
        function setRating(value) {
            const stars = reviewRating.querySelectorAll('i');
            stars.forEach(star => {
                const starValue = parseInt(star.getAttribute('data-value'));
                if (starValue <= value) {
                    star.classList.add('active');
                    star.classList.remove('far');
                    star.classList.add('fas');
                } else {
                    star.classList.remove('active');
                    star.classList.remove('fas');
                    star.classList.add('far');
                }
            });
        }

        // Add product to cart
        function addToCart(productId) {
            if (!currentUser) {
                showMessage('Please login to add items to cart', 'error');
                authPopup.style.display = 'flex';
                return;
            }
            
            const product = products.find(p => p.id === productId);
            if (!product) return;
            
            const existingItem = cart.find(item => item.id === productId);
            
            if (existingItem) {
                existingItem.quantity += 1;
            } else {
                cart.push({
                    id: product.id,
                    name: product.name,
                    price: product.price,
                    image: product.image,
                    quantity: 1
                });
            }
            
            // Save to localStorage
            localStorage.setItem('cart', JSON.stringify(cart));
            localStorage.setItem(`cart_${currentUser.email}`, JSON.stringify(cart));
            
            // Update UI
            updateCartUI();
            
            showMessage('Product added to cart successfully!', 'success');
        }

        // Buy now function
        function buyNow(productId) {
            if (!currentUser) {
                showMessage('Please login to purchase items', 'error');
                authPopup.style.display = 'flex';
                return;
            }
            
            // Clear cart and add only this product
            cart = [{
                id: productId,
                name: products.find(p => p.id === productId).name,
                price: products.find(p => p.id === productId).price,
                image: products.find(p => p.id === productId).image,
                quantity: 1
            }];
            
            localStorage.setItem('cart', JSON.stringify(cart));
            localStorage.setItem(`cart_${currentUser.email}`, JSON.stringify(cart));
            updateCartUI();
            openCheckout();
        }

        // Update cart UI
        function updateCartUI() {
            // Update cart count
            const totalItems = cart.reduce((total, item) => total + item.quantity, 0);
            cartCount.textContent = totalItems;
            
            // Update cart items if cart is open
            if (cartContainer.style.display === 'block') {
                renderCartItems();
            }
            
            // Update checkout summary if checkout is open
            if (checkoutContainer.style.display === 'block') {
                renderCheckoutSummary();
            }
        }

        // Load saved cart for user
        function loadSavedCart() {
            if (!currentUser) return;
            
            const savedCartData = localStorage.getItem(`cart_${currentUser.email}`);
            if (savedCartData) {
                cart = JSON.parse(savedCartData);
                localStorage.setItem('cart', JSON.stringify(cart));
                updateCartUI();
                renderSavedCart();
            }
        }

        // Render saved cart in dashboard
        function renderSavedCart() {
            if (cart.length === 0) {
                savedCart.innerHTML = '<p class="no-items">Your cart is empty</p>';
                return;
            }
            
            savedCart.innerHTML = '';
            
            cart.forEach(item => {
                const cartItem = document.createElement('div');
                cartItem.className = 'saved-cart-item';
                cartItem.innerHTML = `
                    <img src="${item.image}" alt="${item.name}" style="width: 50px; height: 50px; object-fit: cover; border-radius: 6px; margin-right: 10px;">
                    <div>
                        <div style="font-weight: 600;">${item.name}</div>
                        <div>Qty: ${item.quantity} | $${(item.price * item.quantity).toFixed(2)}</div>
                    </div>
                `;
                savedCart.appendChild(cartItem);
            });
            
            const total = cart.reduce((sum, item) => sum + (item.price * item.quantity), 0);
            const totalElement = document.createElement('div');
            totalElement.style.marginTop = '10px';
            totalElement.style.fontWeight = '600';
            totalElement.textContent = `Total: $${total.toFixed(2)}`;
            savedCart.appendChild(totalElement);
            
            const viewCartBtn = document.createElement('button');
            viewCartBtn.textContent = 'View Cart';
            viewCartBtn.className = 'btn';
            viewCartBtn.style.marginTop = '15px';
            viewCartBtn.addEventListener('click', openCart);
            savedCart.appendChild(viewCartBtn);
        }

        // Render cart items
        function renderCartItems() {
            const cartItems = document.getElementById('cart-items');
            cartItems.innerHTML = '';
            
            if (cart.length === 0) {
                cartItems.innerHTML = '<p class="no-items">Your cart is empty</p>';
                return;
            }
            
            cart.forEach(item => {
                const cartItem = document.createElement('div');
                cartItem.className = 'cart-item';
                cartItem.innerHTML = `
                    <img src="${item.image}" alt="${item.name}" class="cart-item-img">
                    <div class="cart-item-info">
                        <h3 class="cart-item-title">${item.name}</h3>
                        <p class="cart-item-price">$${item.price.toFixed(2)}</p>
                        <div class="cart-item-quantity">
                            <button class="quantity-btn decrease" data-id="${item.id}">-</button>
                            <input type="number" class="quantity-input" value="${item.quantity}" min="1" data-id="${item.id}">
                            <button class="quantity-btn increase" data-id="${item.id}">+</button>
                        </div>
                        <button class="cart-item-remove" data-id="${item.id}">Remove</button>
                    </div>
                `;
                cartItems.appendChild(cartItem);
                
                // Add event listeners
                cartItem.querySelector('.decrease').addEventListener('click', () => updateQuantity(item.id, item.quantity - 1));
                cartItem.querySelector('.increase').addEventListener('click', () => updateQuantity(item.id, item.quantity + 1));
                cartItem.querySelector('.quantity-input').addEventListener('change', (e) => updateQuantity(item.id, parseInt(e.target.value)));
                cartItem.querySelector('.cart-item-remove').addEventListener('click', () => removeFromCart(item.id));
            });
            
            // Update total
            const total = cart.reduce((sum, item) => sum + (item.price * item.quantity), 0);
            document.getElementById('cart-total-amount').textContent = `$${total.toFixed(2)}`;
        }

        // Update item quantity
        function updateQuantity(productId, newQuantity) {
            if (newQuantity < 1) newQuantity = 1;
            
            const item = cart.find(item => item.id === productId);
            if (item) {
                item.quantity = newQuantity;
                localStorage.setItem('cart', JSON.stringify(cart));
                localStorage.setItem(`cart_${currentUser.email}`, JSON.stringify(cart));
                updateCartUI();
            }
        }

        // Remove item from cart
        function removeFromCart(productId) {
            cart = cart.filter(item => item.id !== productId);
            localStorage.setItem('cart', JSON.stringify(cart));
            localStorage.setItem(`cart_${currentUser.email}`, JSON.stringify(cart));
            updateCartUI();
            renderSavedCart();
        }

        // Open cart
        function openCart() {
            if (!currentUser) {
                showMessage('Please login to view your cart', 'error');
                authPopup.style.display = 'flex';
                return;
            }
            
            hideAllSections();
            cartContainer.style.display = 'block';
            renderCartItems();
        }

        // Open checkout
        function openCheckout() {
            if (!currentUser) {
                showMessage('Please login to checkout', 'error');
                authPopup.style.display = 'flex';
                return;
            }
            
            if (cart.length === 0) {
                showMessage('Your cart is empty', 'error');
                return;
            }
            
            hideAllSections();
            checkoutContainer.style.display = 'block';
            renderCheckoutSummary();
            
            // Prefill user info if available
            if (currentUser) {
                document.getElementById('checkout-name').value = currentUser.name;
                document.getElementById('checkout-email').value = currentUser.email;
            }
        }

        // Render checkout summary
        function renderCheckoutSummary() {
            const summary = document.getElementById('checkout-summary-items');
            summary.innerHTML = '';
            
            cart.forEach(item => {
                const summaryItem = document.createElement('div');
                summaryItem.className = 'checkout-item';
                summaryItem.innerHTML = `
                    <span>${item.name} x${item.quantity}</span>
                    <span>$${(item.price * item.quantity).toFixed(2)}</span>
                `;
                summary.appendChild(summaryItem);
            });
            
            const total = cart.reduce((sum, item) => sum + (item.price * item.quantity), 0);
            document.getElementById('checkout-total-amount').textContent = `$${total.toFixed(2)}`;
        }

        // Complete purchase
        function completePurchase() {
            // Create order
            const order = {
                id: Date.now(),
                date: new Date().toLocaleDateString(),
                items: [...cart],
                total: cart.reduce((sum, item) => sum + (item.price * item.quantity), 0),
                status: 'Processing'
            };
            
            // Add to orders
            orders.push(order);
            localStorage.setItem('orders', JSON.stringify(orders));
            
            // Clear cart
            cart = [];
            localStorage.setItem('cart', JSON.stringify(cart));
            localStorage.setItem(`cart_${currentUser.email}`, JSON.stringify(cart));
            
            // Update UI
            updateCartUI();
            loadOrders();
            renderSavedCart();
            
            // Show success message
            showMessage('Order placed successfully!', 'success');
            
            // Show dashboard
            showDashboard();
        }

        // Load orders to dashboard
        function loadOrders() {
            const orderHistory = document.getElementById('order-history');
            const totalOrders = document.getElementById('total-orders');
            const totalSpent = document.getElementById('total-spent');
            
            totalOrders.textContent = orders.length;
            
            if (orders.length === 0) {
                orderHistory.innerHTML = '<p class="no-orders">You haven\'t placed any orders yet.</p>';
                totalSpent.textContent = '0';
                return;
            }
            
            // Calculate total spent
            const spent = orders.reduce((sum, order) => sum + order.total, 0);
            totalSpent.textContent = spent.toFixed(2);
            
            // Display orders in a table
            orderHistory.innerHTML = `
                <table class="orders-table">
                    <thead>
                        <tr>
                            <th>Order ID</th>
                            <th>Date</th>
                            <th>Items</th>
                            <th>Total</th>
                            <th>Status</th>
                        </tr>
                    </thead>
                    <tbody>
                        ${orders.map(order => `
                            <tr>
                                <td>#${order.id}</td>
                                <td>${order.date}</td>
                                <td>${order.items.length} items</td>
                                <td>$${order.total.toFixed(2)}</td>
                                <td><span class="order-status status-${order.status.toLowerCase()}">${order.status}</span></td>
                            </tr>
                        `).join('')}
                    </tbody>
                </table>
            `;
        }

        // Toggle auth popup
        function toggleAuthPopup() {
            if (currentUser) {
                userDropdown.classList.toggle('active');
            } else {
                authPopup.style.display = 'flex';
            }
        }

        // Close auth popup
        function closeAuthPopup() {
            authPopup.style.display = 'none';
        }

        // Switch auth tab
        function switchAuthTab(tab) {
            if (tab === 'login') {
                loginTab.classList.add('active');
                signupTab.classList.remove('active');
                loginForm.classList.add('active');
                signupForm.classList.remove('active');
            } else {
                signupTab.classList.add('active');
                loginTab.classList.remove('active');
                signupForm.classList.add('active');
                loginForm.classList.remove('active');
            }
            clearMessage();
        }

        // Show homepage
        function showHomepage() {
            hideAllSections();
            productsGrid.style.display = 'grid';
        }

        // Show dashboard
        function showDashboard() {
            if (!currentUser) {
                showMessage('Please login to view your dashboard', 'error');
                authPopup.style.display = 'flex';
                return;
            }
            
            hideAllSections();
            dashboardContainer.style.display = 'block';
            
            // Update user info
            document.getElementById('infoName').textContent = currentUser.name;
            document.getElementById('infoEmail').textContent = currentUser.email;
            
            // Set member since date (random for demo)
            const memberSince = new Date();
            memberSince.setDate(memberSince.getDate() - 127);
            document.getElementById('memberSince').textContent = memberSince.toLocaleDateString();
            
            // Load orders and saved cart
            loadOrders();
            renderSavedCart();
        }

        // Handle logout
        function handleLogout(e) {
            e.preventDefault();
            currentUser = null;
            localStorage.removeItem('currentUser');
            userStatus.textContent = 'Login';
            cart = [];
            localStorage.removeItem('cart');
            updateCartUI();
            showMessage('You have been logged out successfully', 'success');
            showHomepage();
            userDropdown.classList.remove('active');
        }

        // Hide all sections
        function hideAllSections() {
            productsGrid.style.display = 'none';
            productDetail.style.display = 'none';
            cartContainer.style.display = 'none';
            checkoutContainer.style.display = 'none';
            dashboardContainer.style.display = 'none';
        }

        // Handle login
        function handleLogin(e) {
            e.preventDefault();
            
            const email = document.getElementById('login-email').value;
            const password = document.getElementById('login-password').value;
            
            const users = JSON.parse(localStorage.getItem('users') || '[]');
            const user = users.find(u => u.email === email && u.password === password);
            
            if (user) {
                currentUser = user;
                localStorage.setItem('currentUser', JSON.stringify(user));
                
                showMessage(`Welcome back, ${user.name}!`, 'success');
                
                // Update UI
                userStatus.textContent = user.name;
                closeAuthPopup();
                
                // Clear form
                loginForm.reset();
                
                // Load saved cart for user
                loadSavedCart();
                
                // Show dashboard after login
                showDashboard();
            } else {
                showMessage('Invalid email or password', 'error');
            }
        }

        // Handle signup
        function handleSignup(e) {
            e.preventDefault();
            
            const name = document.getElementById('signup-name').value;
            const email = document.getElementById('signup-email').value;
            const password = document.getElementById('signup-password').value;
            const confirm = document.getElementById('signup-confirm').value;
            
            // Basic validation
            if (password !== confirm) {
                showMessage("Passwords don't match", 'error');
                return;
            }
            
            if (password.length < 6) {
                showMessage("Password must be at least 6 characters", 'error');
                return;
            }
            
            const users = JSON.parse(localStorage.getItem('users') || '[]');
            
            if (users.some(user => user.email === email)) {
                showMessage("User already exists with this email", 'error');
                return;
            }
            
            // Add user
            users.push({ name, email, password });
            localStorage.setItem('users', JSON.stringify(users));
            
            // Set as current user
            currentUser = { name, email };
            localStorage.setItem('currentUser', JSON.stringify(currentUser));
            
            showMessage("Account created successfully!", 'success');
            
            // Update UI
            userStatus.textContent = name;
            closeAuthPopup();
            
            // Clear form
            signupForm.reset();
            
            // Show dashboard after signup
            showDashboard();
        }

        // Handle forgot password
        function handleForgotPassword(e) {
            e.preventDefault();
            showMessage('Password reset functionality would be implemented here', 'success');
        }

        // Check if user is logged in
        function checkLoggedIn() {
            if (currentUser) {
                userStatus.textContent = currentUser.name;
            }
        }

        // Show message
        function showMessage(message, type) {
            messageEl.textContent = message;
            messageEl.classList.add(type);
            messageEl.style.display = 'block';
            
            // Remove previous message classes
            messageEl.classList.remove('success', 'error');
            messageEl.classList.add(type);
            
            // Hide message after 3 seconds
            setTimeout(() => {
                messageEl.style.display = 'none';
            }, 3000);
        }

        // Clear message
        function clearMessage() {
            messageEl.style.display = 'none';
        }

        // Initialize the app
        init();
    </script>
</body>
</html>
