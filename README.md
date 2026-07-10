<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Sharkotu's Restaurant</title>
  <style>
    :root {
      --bg: #fdf2e9;
      --card: #ffffff;
      --accent: #d9480f;
      --accent-dark: #b02a1a;
      --text: #2d2d2d;
      --muted: #6c6c6c;
      --body-bg: radial-gradient(circle at top, #fff7ed 0%, #ffe5d0 55%, #f7ede5 100%);
      --hero-image: url('https://images.unsplash.com/photo-1541544741938-0af808871cc8?auto=format&fit=crop&w=1200&q=80');
      --header-bg: rgba(255, 255, 255, 0.92);
      --card-shadow: 0 12px 30px rgba(0, 0, 0, 0.08);
      --hero-overlay: rgba(0, 0, 0, 0.3);
    }

    body.alt-theme {
      --bg: #061022;
      --card: rgba(11, 21, 34, 0.94);
      --accent: #ffb347;
      --accent-dark: #e2961a;
      --text: #f4f6ff;
      --muted: #9fb5d0;
      --body-bg: radial-gradient(circle at top, #10223b 0%, #071225 55%, #061421 100%);
      --hero-image: url('https://images.unsplash.com/photo-1522637125643-7ea3b4c9c60e?auto=format&fit=crop&w=1200&q=80');
      --header-bg: rgba(6, 17, 34, 0.93);
      --card-shadow: 0 12px 30px rgba(0, 0, 0, 0.24);
      --hero-overlay: rgba(2, 8, 22, 0.55);
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      font-family: "Segoe UI", sans-serif;
      line-height: 1.6;
      color: var(--text);
      background: var(--body-bg);
      scroll-behavior: smooth;
    }

    header {
      display: flex;
      flex-wrap: wrap;
      justify-content: space-between;
      align-items: center;
      padding: 1.5rem 2rem;
      background: var(--header-bg);
      box-shadow: 0 10px 30px rgba(0, 0, 0, 0.08);
      position: sticky;
      top: 0;
      z-index: 10;
    }

    header h1 {
      font-size: 1.5rem;
      letter-spacing: 0.02em;
      color: var(--accent-dark);
    }

    nav ul {
      display: flex;
      gap: 1rem;
      list-style: none;
      flex-wrap: wrap;
    }

    nav a {
      text-decoration: none;
      color: var(--text);
      font-weight: 600;
      transition: color 0.2s ease;
    }

    nav a:hover {
      color: var(--accent-dark);
    }

    .hero {
      min-height: 70vh;
      display: grid;
      place-items: center;
      text-align: center;
      padding: 3rem 1.5rem;
      background: var(--hero-image) center/cover no-repeat;
      position: relative;
      color: #fff;
    }

    .hero::after {
      content: '';
      position: absolute;
      inset: 0;
      background: linear-gradient(180deg, var(--hero-overlay), rgba(0, 0, 0, 0.6));
    }

    .hero * {
      position: relative;
      z-index: 1;
    }

    .hero h1 {
      font-size: clamp(2.2rem, 4vw, 3.8rem);
      margin-bottom: 1rem;
      text-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
    }

    .hero .highlight-text {
      color: #ffd6a5;
      display: inline-block;
      min-height: 1.3em;
      transition: opacity 0.4s ease;
    }

    .hero .hero-badges {
      display: flex;
      justify-content: center;
      gap: 0.7rem;
      flex-wrap: wrap;
      margin-top: 1rem;
    }

    .hero-badge {
      background: rgba(255,255,255,0.16);
      backdrop-filter: blur(6px);
      border: 1px solid rgba(255,255,255,0.2);
      padding: 0.55rem 0.9rem;
      border-radius: 999px;
      font-weight: 600;
      font-size: 0.95rem;
      animation: floatBadge 3s ease-in-out infinite;
    }

    .hero p {
      font-size: 1.1rem;
      max-width: 32rem;
      margin: 0 auto 1.5rem;
      color: #f8f1e7;
    }

    .btn,
    button {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      background: var(--accent);
      color: #fff;
      border: none;
      padding: 0.95rem 1.8rem;
      border-radius: 999px;
      text-transform: uppercase;
      letter-spacing: 0.08em;
      cursor: pointer;
      transition: transform 0.2s ease, background 0.2s ease;
      font-weight: 700;
    }

    .theme-toggle {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      padding: 0.8rem 1.2rem;
      border-radius: 999px;
      border: 1px solid rgba(255,255,255,0.2);
      color: var(--text);
      background: rgba(255,255,255,0.06);
      cursor: pointer;
      transition: background 0.2s ease, transform 0.2s ease;
      font-weight: 700;
      min-width: 140px;
    }

    .theme-toggle:hover {
      background: rgba(255,255,255,0.16);
      transform: translateY(-1px);
    }

    .btn:hover,
    button:hover {
      transform: translateY(-2px);
      background: var(--accent-dark);
    }

    main {
      padding: 3rem 1.5rem;
      max-width: 1100px;
      margin: 0 auto;
    }

    section {
      margin-bottom: 3rem;
    }

    section h2 {
      font-size: 2rem;
      margin-bottom: 1rem;
      color: var(--accent-dark);
    }

    .intro {
      text-align: center;
      max-width: 760px;
      margin: 0 auto 2rem;
      color: var(--muted);
    }

    .menu-header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 1rem;
      flex-wrap: wrap;
      margin-bottom: 1rem;
    }

    .selection-bar {
      display: flex;
      align-items: center;
      gap: 0.8rem;
      flex-wrap: wrap;
      margin-bottom: 1rem;
      padding: 0.8rem 1rem;
      border-radius: 999px;
      background: rgba(217, 72, 15, 0.08);
      color: var(--accent-dark);
      font-weight: 600;
    }

    .selection-bar button {
      padding: 0.45rem 0.8rem;
      border-radius: 999px;
      text-transform: none;
      letter-spacing: 0;
      font-size: 0.9rem;
    }

    .menu-toggle {
      display: inline-flex;
      gap: 0.6rem;
      flex-wrap: wrap;
    }

    .menu-toggle-btn {
      padding: 0.7rem 1.2rem;
      border-radius: 999px;
      border: 1px solid rgba(217, 72, 15, 0.18);
      background: rgba(217, 72, 15, 0.08);
      color: var(--accent-dark);
      text-transform: none;
      letter-spacing: 0;
    }

    .menu-toggle-btn.active {
      background: var(--accent);
      color: #fff;
    }

    .menu-grid {
      display: flex;
      gap: 1rem;
      overflow-x: auto;
      padding: 0.4rem 0.1rem 0.8rem;
      scroll-snap-type: x mandatory;
      scrollbar-width: thin;
      margin-top: 1.5rem;
      touch-action: pan-x;
      cursor: grab;
    }

    .menu-grid.dragging {
      cursor: grabbing;
      user-select: none;
    }

    .menu-grid::-webkit-scrollbar {
      height: 8px;
    }

    .menu-grid::-webkit-scrollbar-thumb {
      background: rgba(217, 72, 15, 0.3);
      border-radius: 999px;
    }

    .menu-section {
      margin-bottom: 2rem;
    }

    .menu-section h3 {
      margin-bottom: 0.6rem;
      color: var(--accent-dark);
      font-size: 1.2rem;
    }

    .menu-item {
      padding: 1.75rem;
      border-radius: 24px;
      background: var(--card);
      box-shadow: var(--card-shadow);
      border: 1px solid rgba(255, 255, 255, 0.6);
      cursor: pointer;
      min-width: 220px;
      flex-shrink: 0;
      scroll-snap-align: start;
      transition: transform 0.2s ease, box-shadow 0.2s ease;
    }

    .menu-item:hover {
      transform: translateY(-4px);
      box-shadow: 0 16px 32px rgba(217, 72, 15, 0.16);
    }

    .menu-item h4 {
      margin-bottom: 0.5rem;
      color: var(--accent);
      font-size: 1.05rem;
    }

    .menu-item p {
      color: var(--muted);
      line-height: 1.7;
      margin-bottom: 0.5rem;
    }

    .menu-badge {
      display: inline-block;
      font-size: 0.78rem;
      font-weight: 700;
      padding: 0.3rem 0.6rem;
      border-radius: 999px;
      background: rgba(217, 72, 15, 0.12);
      color: var(--accent-dark);
      margin-bottom: 0.6rem;
    }

    .menu-view[hidden] {
      display: none;
    }

    #about p,
    #contact p {
      max-width: 780px;
      color: var(--muted);
    }

    .about-card {
      background: var(--card);
      border-radius: 28px;
      padding: 2rem;
      box-shadow: var(--card-shadow);
      border: 1px solid rgba(255,255,255,0.6);
      display: grid;
      gap: 1.2rem;
      overflow: hidden;
      position: relative;
    }

    .about-card::before {
      content: '';
      position: absolute;
      inset: 0;
      background: linear-gradient(135deg, rgba(217,72,15,0.08), transparent 60%);
      pointer-events: none;
    }

    .about-hero {
      display: grid;
      grid-template-columns: 1.2fr 0.8fr;
      gap: 1.2rem;
      align-items: center;
    }

    .about-stats {
      display: grid;
      gap: 0.8rem;
      grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
      margin-top: 0.5rem;
    }

    .stat-box {
      background: rgba(217,72,15,0.08);
      border-radius: 16px;
      padding: 0.9rem;
      text-align: center;
      transition: transform 0.25s ease, background 0.25s ease;
    }

    .stat-box:hover {
      transform: translateY(-3px);
      background: rgba(217,72,15,0.14);
    }

    .stat-box strong {
      display: block;
      font-size: 1.2rem;
      color: var(--accent-dark);
    }

    .about-toggle {
      display: inline-flex;
      gap: 0.6rem;
      flex-wrap: wrap;
      margin-top: 0.4rem;
    }

    .about-toggle button {
      padding: 0.6rem 1rem;
      border-radius: 999px;
      text-transform: none;
      letter-spacing: 0;
      font-size: 0.95rem;
    }

    .about-panel {
      display: none;
      animation: fadeIn 0.35s ease;
    }

    .about-panel.active {
      display: block;
    }

    .contact-details {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
      gap: 1rem;
      margin: 1rem 0 1.5rem;
    }

    .contact-card {
      background: var(--card);
      border-radius: 18px;
      padding: 1.2rem;
      box-shadow: var(--card-shadow);
      border: 1px solid rgba(255, 255, 255, 0.6);
    }

    .contact-card h3 {
      margin-bottom: 0.4rem;
      color: var(--accent-dark);
      font-size: 1rem;
    }

    .contact-card p,
    .contact-card a {
      margin: 0;
      color: var(--muted);
      text-decoration: none;
    }

    form {
      display: grid;
      gap: 1rem;
      margin-top: 1rem;
    }

    input,
    textarea {
      width: 100%;
      padding: 1rem 1.1rem;
      border: 1px solid #e7d5c3;
      border-radius: 16px;
      font: inherit;
    }

    textarea {
      min-height: 140px;
      resize: vertical;
    }

    footer {
      text-align: center;
      padding: 1.25rem 1.5rem;
      color: var(--muted);
      font-size: 0.95rem;
    }

    .menu-item.selected {
      transform: translateY(-4px);
      border-color: rgba(217, 72, 15, 0.4);
      box-shadow: 0 18px 30px rgba(217, 72, 15, 0.18);
    }

    .nav-active {
      color: var(--accent-dark);
    }

    .back-to-top {
      position: fixed;
      right: 1.5rem;
      bottom: 1.5rem;
      width: 3.4rem;
      height: 3.4rem;
      border-radius: 50%;
      background: var(--accent);
      color: #fff;
      border: none;
      box-shadow: 0 16px 32px rgba(0, 0, 0, 0.2);
      display: grid;
      place-items: center;
      cursor: pointer;
      opacity: 0;
      visibility: hidden;
      transform: translateY(10px);
      transition: opacity 0.25s ease, transform 0.25s ease, visibility 0.25s;
      z-index: 20;
    }

    .back-to-top.show {
      opacity: 1;
      visibility: visible;
      transform: translateY(0);
    }

    .toast {
      position: fixed;
      left: 50%;
      bottom: 2.2rem;
      transform: translateX(-50%) translateY(20px);
      background: rgba(45, 45, 45, 0.94);
      color: #fff;
      padding: 0.95rem 1.4rem;
      border-radius: 999px;
      opacity: 0;
      pointer-events: none;
      transition: opacity 0.25s ease, transform 0.25s ease;
      font-size: 0.95rem;
      z-index: 30;
    }

    .toast.show {
      opacity: 1;
      transform: translateX(-50%) translateY(0);
    }

    @keyframes floatBadge {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(-4px); }
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(6px); }
      to { opacity: 1; transform: translateY(0); }
    }

    @media (max-width: 700px) {
      header {
        padding: 1rem;
      }

      nav ul {
        justify-content: center;
      }

      .hero {
        padding: 2.5rem 1rem;
      }

      main {
        padding: 2rem 1rem;
      }

      .theme-toggle {
        width: 100%;
      }
    }
  </style>
</head>
<body>
  <header>
    <h1>Sharkotu's Restaurant</h1>
    <nav>
      <ul>
        <li><a href="#home">Home</a></li>
        <li><a href="#menu">Menu</a></li>
        <li><a href="#about">About Us</a></li>
        <li><a href="./help.html">Help Centre</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
    </nav>
    <button class="theme-toggle" type="button" onclick="toggleTheme()">Switch Style</button>
  </header>

  <main>
    <section id="home" class="hero">
      <div>
        <h1>Welcome to <span class="highlight-text" id="hero-highlight">Sharkotu’s Restaurant</span></h1>
        <p>Delicious food, cozy atmosphere, and great service.</p>
        <a href="#menu" class="btn">View Menu</a>
        <div class="hero-badges">
          <span class="hero-badge">Freshly Prepared</span>
          <span class="hero-badge">Fast Service</span>
          <span class="hero-badge">Taste of Comfort</span>
        </div>
      </div>
    </section>

    <section class="intro">
      <h2>Delicious Food, Cozy Atmosphere</h2>
      <p>Book a table today and enjoy freshly made dishes crafted with passion.</p>
      <button onclick="showAlert()">Book a Table</button>
    </section>

    <section id="menu">
      <div class="menu-header">
        <h2>Our Menu</h2>
        <div class="menu-toggle" role="tablist" aria-label="Menu view toggle">
          <button class="menu-toggle-btn active" type="button" data-view="veg">Veg Menu</button>
          <button class="menu-toggle-btn" type="button" data-view="nonveg">Non-Veg Menu</button>
        </div>
      </div>
      <div class="selection-bar">
        <span id="selected-count">0</span> item(s) selected
        <span id="total-price">Total: ₹0</span>
        <button type="button" id="clear-selection">Clear</button>
      </div>

      <div id="veg-menu" class="menu-view">
        <div class="menu-section">
          <h3>Prantha</h3>
          <div class="menu-grid">
            <div class="menu-item">
              <span class="menu-badge">Veg</span>
              <h4>Plain Prantha</h4>
              <p>₹30</p>
            </div>
            <div class="menu-item">
              <span class="menu-badge">Veg</span>
              <h4>Aloo Prantha</h4>
              <p>₹40</p>
            </div>
            <div class="menu-item">
              <span class="menu-badge">Veg</span>
              <h4>Paneer Prantha</h4>
              <p>₹50</p>
            </div>
            <div class="menu-item">
              <span class="menu-badge">Veg</span>
              <h4>Chinese Prantha</h4>
              <p>₹100</p>
            </div>
          </div>
        </div>

        <div class="menu-section">
          <h3>Chowmein / Thupka</h3>
          <div class="menu-grid">
            <div class="menu-item">
              <span class="menu-badge">Veg</span>
              <h4>Veg. Chowmein</h4>
              <p>Half / Full: ₹50 / ₹90</p>
            </div>
            <div class="menu-item">
              <span class="menu-badge">Veg</span>
              <h4>Veg. Thupka</h4>
              <p>Half / Full: ₹50 / ₹90</p>
            </div>
          </div>
        </div>

        <div class="menu-section">
          <h3>Momos</h3>
          <div class="menu-grid">
            <div class="menu-item">
              <span class="menu-badge">Veg</span>
              <h4>Veg. Momos</h4>
              <p>Half / Full: ₹50 / ₹100</p>
            </div>
            <div class="menu-item">
              <span class="menu-badge">Veg</span>
              <h4>Veg. Fried Momos</h4>
              <p>Half / Full: ₹60 / ₹120</p>
            </div>
          </div>
        </div>

        <div class="menu-section">
          <h3>Burger</h3>
          <div class="menu-grid">
            <div class="menu-item">
              <span class="menu-badge">Veg</span>
              <h4>Veg. Burger</h4>
              <p>₹30</p>
            </div>
          </div>
        </div>

        <div class="menu-section">
          <h3>Roll</h3>
          <div class="menu-grid">
            <div class="menu-item">
              <span class="menu-badge">Veg</span>
              <h4>Paneer Roll</h4>
              <p>₹60</p>
            </div>
          </div>
        </div>

        <div class="menu-section">
          <h3>Pasta</h3>
          <div class="menu-grid">
            <div class="menu-item">
              <span class="menu-badge">Veg</span>
              <h4>Red Sauce Pasta</h4>
              <p>₹120</p>
            </div>
            <div class="menu-item">
              <span class="menu-badge">Veg</span>
              <h4>White Sauce Pasta</h4>
              <p>₹120</p>
            </div>
          </div>
        </div>

        <div class="menu-section">
          <h3>Thalli</h3>
          <div class="menu-grid">
            <div class="menu-item">
              <span class="menu-badge">Veg</span>
              <h4>Veg. Thalli</h4>
              <p>₹100</p>
            </div>
          </div>
        </div>

        <div class="menu-section">
          <h3>Sandwich</h3>
          <div class="menu-grid">
            <div class="menu-item">
              <span class="menu-badge">Veg</span>
              <h4>Veg. Sandwich</h4>
              <p>₹50</p>
            </div>
            <div class="menu-item">
              <span class="menu-badge">Veg</span>
              <h4>Veg. Grilled Sandwich</h4>
              <p>₹60</p>
            </div>
          </div>
        </div>

        <div class="menu-section">
          <h3>Rice</h3>
          <div class="menu-grid">
            <div class="menu-item">
              <span class="menu-badge">Veg</span>
              <h4>Veg. Fried Rice</h4>
              <p>₹60</p>
            </div>
            <div class="menu-item">
              <span class="menu-badge">Veg</span>
              <h4>Veg. Biryani</h4>
              <p>₹120</p>
            </div>
          </div>
        </div>

        <div class="menu-section">
          <h3>Snacks</h3>
          <div class="menu-grid">
            <div class="menu-item">
              <span class="menu-badge">Veg</span>
              <h4>Chilly Paneer</h4>
              <p>₹120</p>
            </div>
            <div class="menu-item">
              <span class="menu-badge">Veg</span>
              <h4>Mushroom Duplex</h4>
              <p>₹160</p>
            </div>
          </div>
        </div>

        <div class="menu-section">
          <h3>Beverages</h3>
          <div class="menu-grid">
            <div class="menu-item">
              <span class="menu-badge">Veg</span>
              <h4>Tea</h4>
              <p>₹10</p>
            </div>
            <div class="menu-item">
              <span class="menu-badge">Veg</span>
              <h4>Coffee</h4>
              <p>₹30</p>
            </div>
            <div class="menu-item">
              <span class="menu-badge">Veg</span>
              <h4>Cold Coffee</h4>
              <p>₹40</p>
            </div>
            <div class="menu-item">
              <span class="menu-badge">Veg</span>
              <h4>Milk</h4>
              <p>₹40</p>
            </div>
            <div class="menu-item">
              <span class="menu-badge">Veg</span>
              <h4>Lassi</h4>
              <p>₹30</p>
            </div>
            <div class="menu-item">
              <span class="menu-badge">Veg</span>
              <h4>Mango Shake</h4>
              <p>₹50</p>
            </div>
            <div class="menu-item">
              <span class="menu-badge">Veg</span>
              <h4>Banana Shake</h4>
              <p>₹50</p>
            </div>
            <div class="menu-item">
              <span class="menu-badge">Veg</span>
              <h4>Fresh Lime Water</h4>
              <p>₹40</p>
            </div>
            <div class="menu-item">
              <span class="menu-badge">Veg</span>
              <h4>Fresh Lime Soda</h4>
              <p>₹40</p>
            </div>
          </div>
        </div>
      </div>

      <div id="nonveg-menu" class="menu-view" hidden>
        <div class="menu-section">
          <h3>Prantha</h3>
          <div class="menu-grid">
            <div class="menu-item">
              <span class="menu-badge">Non-Veg</span>
              <h4>Egg Prantha</h4>
              <p>₹60</p>
            </div>
          </div>
        </div>

        <div class="menu-section">
          <h3>Omelete</h3>
          <div class="menu-grid">
            <div class="menu-item">
              <span class="menu-badge">Non-Veg</span>
              <h4>Plain Omelete</h4>
              <p>₹50</p>
            </div>
            <div class="menu-item">
              <span class="menu-badge">Non-Veg</span>
              <h4>Bread Omelete</h4>
              <p>₹60</p>
            </div>
            <div class="menu-item">
              <span class="menu-badge">Non-Veg</span>
              <h4>Egg Bhurji</h4>
              <p>₹60</p>
            </div>
          </div>
        </div>

        <div class="menu-section">
          <h3>Chowmein / Thupka</h3>
          <div class="menu-grid">
            <div class="menu-item">
              <span class="menu-badge">Non-Veg</span>
              <h4>Egg Chowmein</h4>
              <p>Half / Full: ₹70 / ₹110</p>
            </div>
            <div class="menu-item">
              <span class="menu-badge">Non-Veg</span>
              <h4>Chicken Chowmein</h4>
              <p>Half / Full: ₹80 / ₹120</p>
            </div>
            <div class="menu-item">
              <span class="menu-badge">Non-Veg</span>
              <h4>Chicken Thupka</h4>
              <p>Half / Full: ₹70 / ₹110</p>
            </div>
          </div>
        </div>

        <div class="menu-section">
          <h3>Momos</h3>
          <div class="menu-grid">
            <div class="menu-item">
              <span class="menu-badge">Non-Veg</span>
              <h4>Chicken Momos</h4>
              <p>Half / Full: ₹80 / ₹150</p>
            </div>
            <div class="menu-item">
              <span class="menu-badge">Non-Veg</span>
              <h4>Chicken Fried Momos</h4>
              <p>Half / Full: ₹100 / ₹180</p>
            </div>
          </div>
        </div>

        <div class="menu-section">
          <h3>Burger</h3>
          <div class="menu-grid">
            <div class="menu-item">
              <span class="menu-badge">Non-Veg</span>
              <h4>Chicken Burger</h4>
              <p>₹50</p>
            </div>
          </div>
        </div>

        <div class="menu-section">
          <h3>Roll</h3>
          <div class="menu-grid">
            <div class="menu-item">
              <span class="menu-badge">Non-Veg</span>
              <h4>Egg Roll</h4>
              <p>₹80</p>
            </div>
            <div class="menu-item">
              <span class="menu-badge">Non-Veg</span>
              <h4>Chicken Roll</h4>
              <p>₹100</p>
            </div>
          </div>
        </div>

        <div class="menu-section">
          <h3>Thalli</h3>
          <div class="menu-grid">
            <div class="menu-item">
              <span class="menu-badge">Non-Veg</span>
              <h4>Non-Veg Thalli</h4>
              <p>₹150</p>
            </div>
          </div>
        </div>

        <div class="menu-section">
          <h3>Sandwich</h3>
          <div class="menu-grid">
            <div class="menu-item">
              <span class="menu-badge">Non-Veg</span>
              <h4>Egg Sandwich</h4>
              <p>₹80</p>
            </div>
            <div class="menu-item">
              <span class="menu-badge">Non-Veg</span>
              <h4>Chicken Sandwich</h4>
              <p>₹100</p>
            </div>
          </div>
        </div>

        <div class="menu-section">
          <h3>Rice</h3>
          <div class="menu-grid">
            <div class="menu-item">
              <span class="menu-badge">Non-Veg</span>
              <h4>Egg Fried Rice</h4>
              <p>₹90</p>
            </div>
            <div class="menu-item">
              <span class="menu-badge">Non-Veg</span>
              <h4>Chicken Fried Rice</h4>
              <p>₹120</p>
            </div>
            <div class="menu-item">
              <span class="menu-badge">Non-Veg</span>
              <h4>Chicken Biryani</h4>
              <p>₹180</p>
            </div>
          </div>
        </div>

        <div class="menu-section">
          <h3>Snacks</h3>
          <div class="menu-grid">
            <div class="menu-item">
              <span class="menu-badge">Non-Veg</span>
              <h4>Chilly Chicken</h4>
              <p>₹150</p>
            </div>
            <div class="menu-item">
              <span class="menu-badge">Non-Veg</span>
              <h4>Chicken Pakora</h4>
              <p>₹150</p>
            </div>
            <div class="menu-item">
              <span class="menu-badge">Non-Veg</span>
              <h4>Chicken Lollipop</h4>
              <p>₹180</p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section id="about">
      <h2>About Us</h2>
      <div class="about-card">
        <div class="about-hero">
          <div>
            <p>Welcome to Sharkotu's Restaurant, where comfort food meets warm hospitality. We create memorable dining experiences with fresh ingredients, rich flavors, and a welcoming atmosphere for every guest.</p>
            <div class="about-toggle">
              <button type="button" class="about-btn active" data-target="story">Our Story</button>
              <button type="button" class="about-btn" data-target="vision">Our Vision</button>
              <button type="button" class="about-btn" data-target="promise">Our Promise</button>
            </div>
            <div id="story" class="about-panel active">
              <p>From family recipes to modern favorites, we bring together tradition and creativity on every plate.</p>
            </div>
            <div id="vision" class="about-panel">
              <p>We aim to become the go-to destination for wholesome meals, friendly service, and unforgettable taste.</p>
            </div>
            <div id="promise" class="about-panel">
              <p>Every dish is prepared with care, freshness, and passion to make each visit special.</p>
            </div>
          </div>
          <div class="about-stats">
            <div class="stat-box"><strong>20+</strong><span>Signature Items</span></div>
            <div class="stat-box"><strong>100%</strong><span>Fresh Ingredients</span></div>
            <div class="stat-box"><strong>24/7</strong><span>Friendly Support</span></div>
          </div>
        </div>
      </div>
    </section>

    <section id="contact">
      <h2>Contact Us</h2>
      <div class="contact-details">
        <div class="contact-card">
          <h3>Phone</h3>
          <p><a href="tel:+918278702754">+91 8278702754</a></p>
        </div>
        <div class="contact-card">
          <h3>Email</h3>
          <p><a href="mailto:nittinsharotu2@gmail.com">nittinsharotu2@gmail.com</a></p>
        </div>
        <div class="contact-card">
          <h3>Address</h3>
          <p>Rohru-Rampur Road (Via Taklech), Narain,</p>
        </div>
        <div class="contact-card">
          <h3>Opening Hours</h3>
          <p>Daily: 9:00 AM - 10:00 PM</p>
        </div>
      </div>
      
    </section>

  </main>

  <footer>
    <p>&copy; <span id="year">2026</span> Sharkotu's Restaurant. All rights reserved.</p>
  </footer>

  <button class="back-to-top" aria-label="Back to top" type="button">↑</button>
  <div class="toast" role="status" aria-live="polite"></div>

  <script>
    const navLinks = document.querySelectorAll('nav a');
    const sections = document.querySelectorAll('main section[id]');
    const backToTop = document.querySelector('.back-to-top');
    const toast = document.querySelector('.toast');

    function showAlert(message = "Thanks for choosing Sharkotu's restaurant! Hang there... We will reach out soon.") {
      if (toast) {
        toast.textContent = message;
        toast.classList.add('show');
        setTimeout(() => toast.classList.remove('show'), 2200);
        return;
      }
      alert(message);
    }

    function updateActiveNav() {
      const currentPosition = window.scrollY + 120;

      sections.forEach(section => {
        const top = section.offsetTop;
        const height = section.offsetHeight;
        const link = document.querySelector(`nav a[href="#${section.id}"]`);

        if (currentPosition >= top && currentPosition < top + height) {
          link?.classList.add('nav-active');
        } else {
          link?.classList.remove('nav-active');
        }
      });
    }

    function toggleBackToTop() {
      if (window.scrollY > 400) {
        backToTop.classList.add('show');
      } else {
        backToTop.classList.remove('show');
      }
    }

    function getItemPrice(item) {
      const text = item.textContent || '';
      const matches = [...text.matchAll(/₹(\d+)/g)].map(match => Number(match[1]));
      return matches.length ? matches[matches.length - 1] : 0;
    }

    function initMenuInteraction() {
      const selectedCount = document.getElementById('selected-count');
      const totalPrice = document.getElementById('total-price');
      const clearButton = document.getElementById('clear-selection');
      let count = 0;
      let total = 0;

      function updateSummary() {
        if (selectedCount) {
          selectedCount.textContent = count;
        }
        if (totalPrice) {
          totalPrice.textContent = `Total: ₹${total}`;
        }
      }

      document.querySelectorAll('.menu-item').forEach(item => {
        item.addEventListener('click', () => {
          const title = item.querySelector('h4').textContent;
          const price = getItemPrice(item);

          if (item.classList.contains('selected')) {
            item.classList.remove('selected');
            count = Math.max(0, count - 1);
            total = Math.max(0, total - price);
            showAlert(`${title} removed from your selection.`);
          } else {
            item.classList.add('selected');
            count += 1;
            total += price;
            showAlert(`${title} added to your preferred menu!`);
          }

          updateSummary();
        });
      });

      if (clearButton) {
        clearButton.addEventListener('click', () => {
          document.querySelectorAll('.menu-item.selected').forEach(item => {
            item.classList.remove('selected');
          });
          count = 0;
          total = 0;
          updateSummary();
          showAlert('Your menu selection has been cleared.');
        });
      }

      updateSummary();
    }

    function initMenuViewToggle() {
      const buttons = document.querySelectorAll('.menu-toggle-btn');
      const views = {
        veg: document.getElementById('veg-menu'),
        nonveg: document.getElementById('nonveg-menu')
      };

      buttons.forEach(button => {
        button.addEventListener('click', () => {
          buttons.forEach(btn => btn.classList.remove('active'));
          button.classList.add('active');

          const view = button.dataset.view;
          Object.entries(views).forEach(([key, element]) => {
            element.hidden = key !== view;
          });
        });
      });
    }

    function initSwipeMenu() {
      document.querySelectorAll('.menu-grid').forEach(grid => {
        let isDragging = false;
        let startX = 0;
        let scrollLeft = 0;

        grid.addEventListener('pointerdown', (event) => {
          isDragging = true;
          grid.classList.add('dragging');
          grid.setPointerCapture(event.pointerId);
          startX = event.pageX - grid.offsetLeft;
          scrollLeft = grid.scrollLeft;
        });

        grid.addEventListener('pointerleave', () => {
          isDragging = false;
          grid.classList.remove('dragging');
        });

        grid.addEventListener('pointerup', () => {
          isDragging = false;
          grid.classList.remove('dragging');
        });

        grid.addEventListener('pointercancel', () => {
          isDragging = false;
          grid.classList.remove('dragging');
        });

        grid.addEventListener('pointermove', (event) => {
          if (!isDragging) return;
          event.preventDefault();
          const x = event.pageX - grid.offsetLeft;
          const walk = (x - startX) * 1.2;
          grid.scrollLeft = scrollLeft - walk;
        });
      });
    }

    function initFooterYear() {
      const yearEl = document.getElementById('year');
      if (yearEl) {
        yearEl.textContent = new Date().getFullYear();
      }
    }

    function initAboutSection() {
      const buttons = document.querySelectorAll('.about-btn');
      const panels = document.querySelectorAll('.about-panel');

      buttons.forEach(button => {
        button.addEventListener('click', () => {
          buttons.forEach(btn => btn.classList.remove('active'));
          panels.forEach(panel => panel.classList.remove('active'));

          button.classList.add('active');
          const target = document.getElementById(button.dataset.target);
          target?.classList.add('active');
        });
      });
    }

    function initHeroAnimation() {
      const highlight = document.getElementById('hero-highlight');
      if (!highlight) return;

      const phrases = ['Sharkotu’s Restaurant', 'Spicy Comfort Food', 'Great Family Dining', 'Your Favorite Flavors'];
      let index = 0;

      setInterval(() => {
        highlight.style.opacity = '0';
        setTimeout(() => {
          index = (index + 1) % phrases.length;
          highlight.textContent = phrases[index];
          highlight.style.opacity = '1';
        }, 250);
      }, 2600);
    }

    window.addEventListener('scroll', () => {
      updateActiveNav();
      toggleBackToTop();
    });

    backToTop.addEventListener('click', () => {
      window.scrollTo({ top: 0, behavior: 'smooth' });
    });

    function toggleTheme() {
      document.body.classList.toggle('alt-theme');
    }

    initMenuInteraction();
    initMenuViewToggle();
    initSwipeMenu();
    initFooterYear();
    initAboutSection();
    initHeroAnimation();
  </script>
</body>
</html>
