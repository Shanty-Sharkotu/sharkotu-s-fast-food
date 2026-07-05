# sharkotu's-fast-food
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Nittin's Restaurant</title>
  <link rel="stylesheet" href="style.css">
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600&display=swap" rel="stylesheet">
</head>
<body>
  <!-- Header -->
  <header>
    <div class="logo">🍴 Nittin's Restaurant</div>
    <nav>
      <ul>
        <li><a href="#home">Home</a></li>
        <li><a href="#menu">Menu</a></li>
        <li><a href="#about">About</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
    </nav>
  </header>

  <!-- Hero Section -->
  <section id="home" class="hero">
    <div class="hero-text">
      <h1>Delicious Food, Cozy Atmosphere</h1>
      <p>Experience flavors that make you smile.</p>
      <button onclick="showAlert()">Reserve a Table</button>
    </div>
  </section>

  <!-- Menu Section -->
  <section id="menu">
    <h2>Our Specialties</h2>
    <div class="menu-grid">
      <div class="menu-card">
        <img src="pizza.jpg" alt="Pizza">
        <h3>Pizza</h3>
        <p>Cheesy and fresh from the oven.</p>
      </div>
      <div class="menu-card">
        <img src="pasta.jpg" alt="Pasta">
        <h3>Pasta</h3>
        <p>Authentic Italian flavors.</p>
      </div>
      <div class="menu-card">
        <img src="biryani.jpg" alt="Biryani">
        <h3>Biryani</h3>
        <p>Spiced to perfection.</p>
      </div>
    </div>
  </section>

  <!-- About Section -->
  <section id="about">
    <h2>About Us</h2>
    <p>We are passionate about serving fresh, tasty food with love. Our chefs bring authentic recipes to life, creating unforgettable dining experiences.</p>
  </section>

  <!-- Contact Section -->
  <section id="contact">
    <h2>Contact Us</h2>
    <form>
      <input type="text" placeholder="Your Name" required>
      <input type="email" placeholder="Your Email" required>
      <textarea placeholder="Your Message"></textarea>
      <button type="submit">Send</button>
    </form>
  </section>

  <!-- Footer -->
  <footer>
    <p>&copy; 2026 Nittin's Restaurant | Designed with ❤️</p>
  </footer>

  <script src="script.js"></script>
</body>
</html>

