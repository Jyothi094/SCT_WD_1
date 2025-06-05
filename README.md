<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Responsive Landing Page</title>
  <style>
    /* Basic Reset */
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Segoe UI', sans-serif;
      line-height: 1.6;
    }

    /* Navigation Menu */
    nav {
      position: fixed;
      width: 100%;
      top: 0;
      left: 0;
      background-color: transparent;
      transition: background-color 0.3s ease, box-shadow 0.3s ease;
      z-index: 1000;
      padding: 15px 30px;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    nav.scrolled {
      background-color: #fff;
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    }

    .logo {
      font-size: 1.5rem;
      font-weight: bold;
      color: #333;
    }

    .menu {
      display: flex;
      gap: 25px;
    }

    .menu a {
      text-decoration: none;
      color: #333;
      font-weight: 500;
      position: relative;
    }

    .menu a:hover {
      color: #007BFF;
    }

    .menu a::after {
      content: "";
      display: block;
      width: 0;
      height: 2px;
      background: #007BFF;
      transition: width 0.3s;
      position: absolute;
      bottom: -5px;
      left: 0;
    }

    .menu a:hover::after {
      width: 100%;
    }

    /* Landing Page Content */
    header {
      height: 100vh;
      background: linear-gradient(to right, #6a11cb, #2575fc);
      color: #fff;
      display: flex;
      justify-content: center;
      align-items: center;
      text-align: center;
      padding: 0 20px;
    }

    header h1 {
      font-size: 3rem;
    }

    /* Responsive */
    @media (max-width: 768px) {
      .menu {
        flex-direction: column;
        background: #fff;
        position: absolute;
        top: 60px;
        right: 30px;
        display: none;
        padding: 10px;
        box-shadow: 0 4px 8px rgba(0,0,0,0.1);
      }

      .menu.open {
        display: flex;
      }

      .menu a {
        color: #333;
      }

      .menu-toggle {
        display: block;
        cursor: pointer;
        font-size: 1.5rem;
      }
    }

    .menu-toggle {
      display: none;
    }
  </style>
</head>
<body>

  <nav id="navbar">
    <div class="logo">MySite</div>
    <div class="menu-toggle" onclick="toggleMenu()">☰</div>
    <div class="menu" id="menu">
      <a href="#">Home</a>
      <a href="#">About</a>
      <a href="#">Services</a>
      <a href="#">Contact</a>
    </div>
  </nav>

  <header>
    <div>
      <h1>Welcome to My Landing Page</h1>
      <p>Scroll down to see the navigation menu effect</p>
    </div>
  </header>

  <section style="padding: 100px 30px;">
    <h2>Section 1</h2>
    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Proin vel libero vitae justo luctus feugiat.</p>
  </section>

  <script>
    const navbar = document.getElementById('navbar');

    window.addEventListener('scroll', () => {
      if (window.scrollY > 50) {
        navbar.classList.add('scrolled');
      } else {
        navbar.classList.remove('scrolled');
      }
    });

    function toggleMenu() {
      const menu = document.getElementById('menu');
      menu.classList.toggle('open');
    }
  </script>

</body>
</html>
