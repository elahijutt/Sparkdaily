# Sparkdaily
Spark Daily is a blogging website which provides a most authentic data of the world.
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Spark Daily</title>
    <link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600&display=swap">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Poppins', sans-serif;
            line-height: 1.6;
            background-color: #f4f7fb;
            color: #333;
        }

        a {
            text-decoration: none;
            color: inherit;
        }

        /* Navbar */
        nav {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            background-color: #1a1a1a;
            color: white;
            padding: 15px 50px;
            z-index: 100;
            opacity: 0.9;
        }

        nav .logo {
            font-size: 1.8rem;
            font-weight: 600;
            color: #FF6347;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
        }

        nav ul {
            list-style: none;
            float: right;
        }

        nav ul li {
            display: inline-block;
            margin-left: 30px;
        }

        nav ul li a {
            color: white;
            font-size: 16px;
            font-weight: 500;
            text-shadow: 1px 1px 3px rgba(0, 0, 0, 0.3);
        }

        nav ul li a:hover {
            color: #FF6347;
            border-bottom: 2px solid #FF6347;
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            background-image: linear-gradient(135deg, #333, #1a1a1a);
            background-size: cover;
            background-position: center;
            display: flex;
            justify-content: center;
            align-items: center;
            text-align: center;
            color:white;
            margin-top: 20px;
            position: relative;
            animation: fadeIn 3s ease-out, backgroundAnimation 5s infinite alternate;
        }

        @keyframes backgroundAnimation {
            0% {
                background-image: linear-gradient(135deg, #333, #1a1a1a);
            }

            50% {
                background-image: linear-gradient(135deg, #555, #2a2a2a);
            }

            100% {
                background-image: linear-gradient(135deg, #333, #1a1a1a);
            }
        }

        .hero h1 {
            font-size: 60px;
            margin-bottom: 10px;
            letter-spacing: 2px;
            text-transform: uppercase;
            text-shadow: 4px 4px 6px rgba(0, 0, 0, 0.5);
            animation: fadeInText 2s ease-in-out;
        }

        .hero p {
            font-size: 20px;
            font-weight: 300;
            margin-top: 10px;
            opacity: 0.8;
            animation: fadeInText 3s ease-in-out;
        }

        .hero .btn {
            padding: 12px 25px;
            background-color: #FF6347;
            color: white;
            font-weight: 600;
            border-radius: 30px;
            border: none;
            font-size: 18px;
            text-transform: uppercase;
            margin-top: 40px;
            transition: background-color 0.3s ease;
            z-index: 2;
            animation: bounceIn 1.5s ease-out;
        }

        .hero .btn:hover {
            background-color: #333;
            cursor: pointer;
        }

        /* Blog Section */
        .blog-container {
            display: none;
            margin: 20px;
            margin-top: 100px;
            color: red;
        }

        .blog-card {
            background-color: #fff;
            padding: 20px;
            margin: 20px 0;
            box-shadow: 0px 4px 15px rgba(0, 0, 0, 0.1);
            border-radius: 10px;
            transition: all 0.3s ease;
        }

        .blog-card:hover {
            box-shadow: 0px 6px 20px rgba(0, 0, 0, 0.2);
        }

        .blog-card img {
            width: 100%;
            height: auto;
            border-radius: 10px;
        }

        .blog-card .content {
            margin-top: 15px;
        }

        .blog-card h2 {
            font-size: 24px;
            color: #333;
            margin-bottom: 10px;
        }

        .blog-card p {
            color: #666;
            font-size: 16px;
            margin-bottom: 15px;
        }

        .blog-card a {
            color: #FF6347;
            font-weight: 600;
            text-decoration: none;
            font-size: 16px;
        }

        .blog-card a:hover {
            color: #333;
        }

        /* Login Section (Initially Hidden) */
        .login-container {
            display: none;
            background-color: #fff;
            padding: 50px;
            box-shadow: 0px 4px 15px rgba(0, 0, 0, 0.1);
            border-radius: 10px;
            margin-top: 60px;
            text-align: center;
        }

        .login-container h2 {
            font-size: 24px;
            color: #333;
            margin-bottom: 20px;
        }

        .login-container form {
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        .login-container input {
            width: 100%;
            padding: 12px;
            margin: 10px 0;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-size: 16px;
        }

        .login-container button {
            padding: 12px 25px;
            background-color: #FF6347;
            color: white;
            font-weight: 600;
            border-radius: 30px;
            border: none;
            font-size: 18px;
            cursor: pointer;
            margin-top: 20px;
        }

        .login-container button:hover {
            background-color: #333;
        }

        /* Contact Section */
        .contact-container {
            display: none;
            background-color: #fff;
            padding: 50px;
            text-align: center;
            box-shadow: 0px 4px 15px rgba(0, 0, 0, 0.1);
            border-radius: 10px;
            margin-top: 50px;
        }

        .contact-container h2 {
            font-size: 24px;
            color: #333;
            margin-bottom: 30px;
        }

        .contact-container p {
            font-size: 18px;
            color: #555;
            margin-bottom: 15px;
        }

        .contact-container a {
            color: #FF6347;
            font-weight: 600;
            font-size: 20px;
            text-decoration: none;
        }

        footer {
            background-color: #1a1a1a;
            color: white;
            text-align: center;
            padding: 40px 20px;
            margin-top: 60px;
        }

        footer p {
            font-size: 16px;
            opacity: 0.7;
        }

        /* Animations */
        @keyframes fadeIn {
            0% {
                opacity: 0;
            }

            100% {
                opacity: 1;
            }
        }

        @keyframes fadeInText {
            0% {
                opacity: 0;
                transform: translateY(20px);
            }

            100% {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes bounceIn {
            0% {
                transform: scale(0);
                opacity: 0;
            }

            60% {
                transform: scale(1.1);
                opacity: 1;
            }

            100% {
                transform: scale(1);
            }
        }

        @media (max-width: 768px) {
            .blog-card {
                width: 90%;
            }
        }
    </style>
</head>

<body>

    <!-- Navbar -->
    <nav>
        <div class="logo">Spark Daily</div>
        <ul>
            <li><a href="#" onclick="showHomePage()">Home</a></li>
            <li><a href="#" onclick="showBlogPage()">Blog</a></li>
            <li><a href="#" onclick="showContactPage()">Contact</a></li>
            <li><a href="#" onclick="showLoginPage()">Register</a></li>
        </ul>
    </nav>

    <!-- Hero Section -->
    <section id="home-page" class="hero">
        <div>
            <h1>Welcome to Spark Daily</h1>
            <p>By Ahtsham Elahi</p>
            <p>Your daily source of inspiration and knowledge</p>
            <button class="btn" id="start-reading-btn">Start Reading</button>
        </div>
    </section>

    <!-- Blog Section -->
    <section id="blog-page" class="blog-container">
        <h2>All Available Blogs</h2>

        <div class="blog-card">
            <img src="https://via.placeholder.com/600x300?text=Blog+Post+1" alt="Coding Future">
            <div class="content">
                <h2>Coding Future</h2>
                <p>Discover the evolving trends in the world of coding and programming languages that will define the future of technology.</p>
                <a href="#">Read More</a>
            </div>
        </div>

        <div class="blog-card">
            <img src="https://via.placeholder.com/600x300?text=Blog+Post+2" alt="Pakistan Economics">
            <div class="content">
                <h2>Pakistan Economics</h2>
                <p>Explore the current economic trends in Pakistan and their impact on growth and stability.</p>
                <a href="#">Read More</a>
            </div>
        </div>

        <div class="blog-card">
            <img src="https://via.placeholder.com/600x300?text=Blog+Post+3" alt="Pakistan Politics">
            <div class="content">
                <h2>Pakistan Politics</h2>
                <p>Get insights into the political landscape of Pakistan and its implications for the future.</p>
                <a href="#">Read More</a>
            </div>
        </div>
    </section>

    <!-- Login Section -->
    <section id="login-page" class="login-container">
        <h2>Login</h2>
        <form onsubmit="submitLogin(event)">
            <p>Register for updates</p>
            <input type="text" id="first-name" placeholder="First Name" required>
            <input type="text" id="last-name" placeholder="Last Name" required>
            <input type="email" id="email" placeholder="Email" required>
           
            <button type="submit">Submit</button>
        </form>
    </section>

    <!-- Contact Section -->
    <section id="contact-page" class="contact-container">
        <h2>Contact Us</h2>
        <p>Email: <a href="ahtshamelahi6660@gmail.com">sparkdaily@gmail.com</a></p>
        <p>Contact No: +92 328 9395432</p>
        <p>Follow us on:</p>
        <a href="https://www.facebook.com/profile.php?id=100093568672754" target="_blank">Facebook</a> | <a href="https://www.instagram.com/ahtsham_ellahi_randhawa/profilecard/?igsh=dHZpejN5ZTQxbTM3" target="_blank">Instagram</a>
    </section>

    <footer>
        <p>&copy; 2024 Spark Daily. All Rights Reserved.</p>
    </footer>

    <script>
        document.getElementById('start-reading-btn').addEventListener('click', function() {
            showBlogPage();
        });

        function showHomePage() {
            document.getElementById('home-page').style.display = 'flex';
            document.getElementById('blog-page').style.display = 'none';
            document.getElementById('login-page').style.display = 'none';
            document.getElementById('contact-page').style.display = 'none';
        }

        function showBlogPage() {
            document.getElementById('home-page').style.display = 'none';
            document.getElementById('blog-page').style.display = 'block';
            document.getElementById('login-page').style.display = 'none';
            document.getElementById('contact-page').style.display = 'none';
        }

        function showContactPage() {
            document.getElementById('home-page').style.display = 'none';
            document.getElementById('blog-page').style.display = 'none';
            document.getElementById('login-page').style.display = 'none';
            document.getElementById('contact-page').style.display = 'block';
        }

        function showLoginPage() {
            document.getElementById('home-page').style.display = 'none';
            document.getElementById('blog-page').style.display = 'none';
            document.getElementById('login-page').style.display = 'block';
            document.getElementById('contact-page').style.display = 'none';
        }

        function submitLogin(event) {
            event.preventDefault();
            alert('Thank you for registering!');
            showHomePage();
        }
    </script>

</body>

</html>

