# Project Responsive Web Design using Bootstrap
# Date:
# AIM:
To create a simplified clone of Dribbble (https://dribbble.com/) landing page.

# DESIGN STEPS:
## Step 1:
Clone the repository from GitHub.

## Step 2:
Create Django Admin project.

## Step 3:
Create a New App under the Django Admin project.

## Step 4:
Insert the necessary CSS and JavaScript files as external in order to use Bootstrap.

## Step 5:
Create a HTML file and include the needed Bootstrap components.

## Step 6:
Publish the website in the LocalHost.

# PROGRAM :
```
<script type="text/javascript">
        var gk_isXlsx = false;
        var gk_xlsxFileLookup = {};
        var gk_fileData = {};
        function filledCell(cell) {
          return cell !== '' && cell != null;
        }
        function loadFileData(filename) {
        if (gk_isXlsx && gk_xlsxFileLookup[filename]) {
            try {
                var workbook = XLSX.read(gk_fileData[filename], { type: 'base64' });
                var firstSheetName = workbook.SheetNames[0];
                var worksheet = workbook.Sheets[firstSheetName];

                // Convert sheet to JSON to filter blank rows
                var jsonData = XLSX.utils.sheet_to_json(worksheet, { header: 1, blankrows: false, defval: '' });
                // Filter out blank rows (rows where all cells are empty, null, or undefined)
                var filteredData = jsonData.filter(row => row.some(filledCell));

                // Heuristic to find the header row by ignoring rows with fewer filled cells than the next row
                var headerRowIndex = filteredData.findIndex((row, index) =>
                  row.filter(filledCell).length >= filteredData[index + 1]?.filter(filledCell).length
                );
                // Fallback
                if (headerRowIndex === -1 || headerRowIndex > 25) {
                  headerRowIndex = 0;
                }

                // Convert filtered JSON back to CSV
                var csv = XLSX.utils.aoa_to_sheet(filteredData.slice(headerRowIndex)); // Create a new sheet from filtered array of arrays
                csv = XLSX.utils.sheet_to_csv(csv, { header: 1 });
                return csv;
            } catch (e) {
                console.error(e);
                return "";
            }
        }
        return gk_fileData[filename] || "";
        }
        </script><!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cricket Sports Shop</title>
    <!-- Bootstrap CSS -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-QWTKZyjpPEjISv5WaRU9OFeRpok6YctnYmDr5pNlyT2bRjXh0JMhjY6hW+ALEwIH" crossorigin="anonymous">
    <!-- Custom CSS -->
    <style>
        body {
            font-family: 'Arial', sans-serif;
        }
        .navbar-brand {
            font-weight: bold;
            color: #28a745 !important;
        }
        .hero-section {
            background: linear-gradient(rgba(0,0,0,0.5), rgba(0,0,0,0.5)), url('https://via.placeholder.com/1200x400?text=Cricket+Banner');
            background-size: cover;
            color: white;
            padding: 80px 0;
            text-align: center;
        }
        .hero-section h1 {
            font-size: 3rem;
            font-weight: 700;
        }
        .product-card {
            transition: transform 0.2s;
        }
        .product-card:hover {
            transform: scale(1.05);
        }
        .about-section {
            background-color: #f8f9fa;
            padding: 60px 0;
        }
        .testimonial-section {
            padding: 60px 0;
            background-color: #fff;
        }
        .newsletter-section {
            background-color: #28a745;
            color: white;
            padding: 60px 0;
        }
        .footer {
            background-color: #1a1a1a;
            color: #ccc;
            padding: 40px 0;
        }
        .footer a {
            color: #ccc;
            text-decoration: none;
        }
        .footer a:hover {
            color: #fff;
        }
    </style>
</head>
<body>
    <!-- Navigation Bar -->
    <nav class="navbar navbar-expand-lg bg-light shadow-sm">
        <div class="container">
            <a class="navbar-brand" href="#">Cricket Sports Shop</a>
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarNav">
                <ul class="navbar-nav me-auto mb-2 mb-lg-0">
                    <li class="nav-item">
                        <a class="nav-link" href="#home">Home</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="#products">Products</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="#about">About</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="#testimonials">Testimonials</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="#contact">Contact</a>
                    </li>
                </ul>
                <div class="d-flex">
                    <a href="#cart" class="btn btn-outline-success me-2">Cart</a>
                    <a href="#login" class="btn btn-success">Login</a>
                </div>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <section id="home" class="hero-section">
        <div class="container">
            <h1>Gear Up for Cricket!</h1>
            <p class="lead mb-4">Discover top-quality cricket bats, balls, gloves, and more.</p>
            <a href="#products" class="btn btn-success btn-lg">Shop Now</a>
        </div>
    </section>

    <!-- Products Section -->
    <section id="products" class="py-5">
        <div class="container">
            <h2 class="text-center mb-5">Our Products</h2>
            <div class="row row-cols-1 row-cols-md-3 g-4">
                <div class="col">
                    <div class="card product-card h-100">
                        <img src="C:\Users\MALLIGESH\Documents\webproject\Bat.jpg" class="card-img-top" alt="Cricket Bat">
                        <div class="card-body">
                            <h5 class="card-title">Premium Cricket Bat</h5>
                            <p class="card-text">High-quality willow bat for professional performance.</p>
                            <p class="fw-bold">₹7,499</p>
                            <a href="#buy" class="btn btn-success">Add to Cart</a>
                        </div>
                    </div>
                </div>
                <div class="col">
                    <div class="card product-card h-100">
                        <img src="C:\Users\MALLIGESH\Documents\webproject\Ball.jpg" class="card-img-top" alt="Cricket Ball">
                        <div class="card-body">
                            <h5 class="card-title">Leather Cricket Ball</h5>
                            <p class="card-text">Durable ball for matches and practice.</p>
                            <p class="fw-bold">₹1,499</p>
                            <a href="#buy" class="btn btn-success">Add to Cart</a>
                        </div>
                    </div>
                </div>
                <div class="col">
                    <div class="card product-card h-100">
                        <img src="C:\Users\MALLIGESH\Documents\webproject\gloves.jpg" class="card-img-top" alt="Cricket Gloves">
                        <div class="card-body">
                            <h5 class="card-title">Batting Gloves</h5>
                            <p class="card-text">Comfortable gloves with superior grip.</p>
                            <p class="fw-bold">₹3,799</p>
                            <a href="#buy" class="btn btn-success">Add to Cart</a>
                        </div>
                    </div>
                </div>
                <div class="col">
                    <div class="card product-card h-100">
                        <img src="C:\Users\MALLIGESH\Documents\webproject\pads.jpg" class="card-img-top" alt="Cricket Pads">
                        <div class="card-body">
                            <h5 class="card-title">Batting Pads</h5>
                            <p class="card-text">Lightweight pads for maximum protection.</p>
                            <p class="fw-bold">₹4,999</p>
                            <a href="#buy" class="btn btn-success">Add to Cart</a>
                        </div>
                    </div>
                </div>
                <div class="col">
                    <div class="card product-card h-100">
                        <img src="C:\Users\MALLIGESH\Documents\webproject\helmet.jpg" class="card-img-top" alt="Cricket Helmet">
                        <div class="card-body">
                            <h5 class="card-title">Cricket Helmet</h5>
                            <p class="card-text">High-impact resistant helmet for safety.</p>
                            <p class="fw-bold">₹5,499</p>
                            <a href="#buy" class="btn btn-success">Add to Cart</a>
                        </div>
                    </div>
                </div>
                <div class="col">
                    <div class="card product-card h-100">
                        <img src="C:\Users\MALLIGESH\Documents\webproject\kitbag.jpg" class="card-img-top" alt="Cricket Kit Bag">
                        <div class="card-body">
                            <h5 class="card-title">Cricket Kit Bag</h5>
                            <p class="card-text">Spacious bag for all your cricket gear.</p>
                            <p class="fw-bold">₹2,999</p>
                            <a href="#buy" class="btn btn-success">Add to Cart</a>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="about-section text-center">
        <div class="container">
            <h2>About Us</h2>
            <p class="lead mb-4">Cricket Sports Shop is your one-stop destination for premium cricket gear. We offer a wide range of equipment for players of all levels, ensuring quality and performance on the field.</p>
            <a href="#contact" class="btn btn-outline-success">Contact Us</a>
        </div>
    </section>

    <!-- Testimonial Section -->
    <section id="testimonials" class="testimonial-section">
        <div class="container">
            <h2 class="text-center mb-5">What Our Customers Say</h2>
            <div class="row row-cols-1 row-cols-md-3 g-4">
                <div class="col">
                    <div class="card h-100">
                        <div class="card-body text-center">
                            <p class="card-text">"The best cricket bat I've ever used! Excellent quality and fast delivery."</p>
                            <h6 class="card-title">Rahul Sharma</h6>
                        </div>
                    </div>
                </div>
                <div class="col">
                    <div class="card h-100">
                        <div class="card-body text-center">
                            <p class="card-text">"Affordable prices and durable gear. My go-to shop for cricket equipment."</p>
                            <h6 class="card-title">Priya Patel</h6>
                        </div>
                    </div>
                </div>
                <div class="col">
                    <div class="card h-100">
                        <div class="card-body text-center">
                            <p class="card-text">"The helmet fits perfectly and feels very secure. Highly recommend!"</p>
                            <h6 class="card-title">Arjun Singh</h6>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Newsletter Section -->
    <section id="newsletter" class="newsletter-section text-center">
        <div class="container">
            <h2>Stay Updated</h2>
            <p class="lead mb-4">Subscribe to our newsletter for exclusive offers and updates.</p>
            <div class="row justify-content-center">
                <div class="col-md-6">
                    <div class="input-group mb-3">
                        <input type="email" class="form-control" placeholder="Enter your email" aria-label="Email">
                        <button class="btn btn-light" type="button">Subscribe</button>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer id="contact" class="footer">
        <div class="container">
            <div class="row">
                <div class="col-md-4 mb-3">
                    <h5>Cricket Sports Shop</h5>
                    <p>Your trusted source for cricket equipment.</p>
                </div>
                <div class="col-md-2 mb-3">
                    <h5>Shop</h5>
                    <ul class="list-unstyled">
                        <li><a href="#products">Bats</a></li>
                        <li><a href="#products">Balls</a></li>
                        <li><a href="#products">Accessories</a></li>
                    </ul>
                </div>
                <div class="col-md-2 mb-3">
                    <h5>Support</h5>
                    <ul class="list-unstyled">
                        <li><a href="#faq">FAQ</a></li>
                        <li><a href="#returns">Returns</a></li>
                        <li><a href="#contact">Contact</a></li>
                    </ul>
                </div>
                <div class="col-md-4 mb-3">
                    <h5>Contact Us</h5>
                    <ul class="list-unstyled">
                        <li>Email: support@cricketsportsshop.com</li>
                        <li>Phone: +1-800-123-4567</li>
                        <li>Address: 123 Cricket Lane, Sports City</li>
                    </ul>
                </div>
            </div>
            <div class="text-center mt-4">
                <p>© 2025 Cricket Sports Shop. All rights reserved. | Designed by Malligesh 212223230119</p>
            </div>
        </div>
    </footer>

    <!-- Bootstrap JS -->
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js" integrity="sha384-YvpcrYf0tY3lHB60NNkmXc5s9fDVZLESaAA55NDzOxhy9GkcIdslK1eN7N6jIeHz" crossorigin="anonymous"></script>
</body>
</html>
```
# OUTPUT:
![Screenshot 2025-05-13 142030](https://github.com/user-attachments/assets/0488297f-c101-472c-8603-f4b46fd51bcd)

![Screenshot 2025-05-13 142038](https://github.com/user-attachments/assets/ce8f61d3-0ed8-495a-9310-9e9e2f9e45bb)


![Screenshot 2025-05-13 142103](https://github.com/user-attachments/assets/40b0ec96-2c36-4f60-8e0c-f504da182d00)


# RESULT:
The Project for responsive web design using Bootstrap is completed successfully.
