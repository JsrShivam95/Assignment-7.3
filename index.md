       HTML

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Assignment 7.3 — Responsive Product Listing</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>

  <main class="page-container">
    <header class="page-header">
      <h1>Featured Products</h1>
      <p>Discover our latest gear and everyday essentials</p>
    </header>

    <!-- Step 3: Flexbox container with wrap enabled -->
    <section class="product-grid">

      <!-- Card 1 -->
      <article class="product-card">
        <div class="product-image-wrap">
          <img src="https://images.unsplash.com/photo-1505740420928-5e560c06d30e?w=500&q=80" alt="Wireless Over-Ear Headphones">
        </div>
        <div class="product-body">
          <span class="product-category">Audio</span>
          <h2 class="product-title">Studio Pro Headphones</h2>
          <p class="product-price">$199.99</p>
          <button type="button" class="btn">Add to Cart</button>
        </div>
      </article>

      <!-- Card 2 -->
      <article class="product-card">
        <div class="product-image-wrap">
          <img src="https://images.unsplash.com/photo-1523275335684-37898b6baf30?w=500&q=80" alt="Minimalist Analog Watch">
        </div>
        <div class="product-body">
          <span class="product-category">Accessories</span>
          <h2 class="product-title">Classic Minimalist Watch</h2>
          <p class="product-price">$149.00</p>
          <button type="button" class="btn">Add to Cart</button>
        </div>
      </article>

      <!-- Card 3 -->
      <article class="product-card">
        <div class="product-image-wrap">
          <img src="https://images.unsplash.com/photo-1546868871-7041f2a55e12?w=500&q=80" alt="Smart Fitness Tracker">
        </div>
        <div class="product-body">
          <span class="product-category">Wearables</span>
          <h2 class="product-title">Pulse Fitness Tracker</h2>
          <p class="product-price">$89.50</p>
          <button type="button" class="btn">Add to Cart</button>
        </div>
      </article>

      <!-- Card 4 -->
      <article class="product-card">
        <div class="product-image-wrap">
          <img src="https://images.unsplash.com/photo-1585386959984-a4155224a1ad?w=500&q=80" alt="Ceramic Coffee Mug">
        </div>
        <div class="product-body">
          <span class="product-category">Home Goods</span>
          <h2 class="product-title">Matte Ceramic Mug</h2>
          <p class="product-price">$24.00</p>
          <button type="button" class="btn">Add to Cart</button>
        </div>
      </article>

      <!-- Card 5 -->
      <article class="product-card">
        <div class="product-image-wrap">
          <img src="https://images.unsplash.com/photo-1572635196237-14b3f281503f?w=500&q=80" alt="Polarized Sunglasses">
        </div>
        <div class="product-body">
          <span class="product-category">Eyewear</span>
          <h2 class="product-title">Polarized Sunglasses</h2>
          <p class="product-price">$115.00</p>
          <button type="button" class="btn">Add to Cart</button>
        </div>
      </article>

      <!-- Card 6 -->
      <article class="product-card">
        <div class="product-image-wrap">
          <img src="https://images.unsplash.com/photo-1608231387042-66d1773070a5?w=500&q=80" alt="Canvas Daily Backpack">
        </div>
        <div class="product-body">
          <span class="product-category">Travel</span>
          <h2 class="product-title">Everyday Canvas Pack</h2>
          <p class="product-price">$78.00</p>
          <button type="button" class="btn">Add to Cart</button>
        </div>
      </article>

    </section>
  </main>

</body>
</html>


                    CSS

/* --- Global Reset & Page Setup --- */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
  background-color: #f8fafc;
  color: #1e293b;
  line-height: 1.5;
  padding: 2.5rem 1.5rem;
}

.page-container {
  max-width: 1200px;
  margin: 0 auto;
}

.page-header {
  margin-bottom: 2rem;
  text-align: center;
}

.page-header h1 {
  font-size: 2.25rem;
  font-weight: 800;
  color: #0f172a;
}

.page-header p {
  color: #64748b;
  margin-top: 0.5rem;
}

/* --- Steps 3 & 4: Flexbox Container with Wrap and Gap --- */
.product-grid {
  display: flex;             /* Step 3: Flex container */
  flex-wrap: wrap;           /* Step 3 & 6: Items wrap to next line as viewport shrinks */
  gap: 1.75rem;              /* Step 4: Spacing between flex rows and columns */
  justify-content: center;   /* Keeps cards neatly balanced if the last row isn't full */
}

/* --- Steps 1, 2 & 5: Card Sizing with Flex Grow/Shrink/Basis --- */
.product-card {
  /* Step 5:
     flex-grow: 1    -> Expand into available leftover space
     flex-shrink: 1  -> Shrink safely without breaking out of boundaries
     flex-basis: 300px -> Ideal starting reference width before wrapping */
  flex: 1 1 300px;
  max-width: 380px;          /* Prevents a solitary card on the last row from stretching too wide */

  background-color: #ffffff;
  border: 1px solid #e2e8f0;
  border-radius: 12px;
  overflow: hidden;
  box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.05);
  display: flex;
  flex-direction: column;    /* Keeps image on top and content anchored below */
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.product-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 12px 20px -3px rgba(0, 0, 0, 0.08);
}

/* Image Presentation */
.product-image-wrap {
  width: 100%;
  height: 220px;
  background-color: #f1f5f9;
}

.product-image-wrap img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
}

/* Card Body Layout */
.product-body {
  padding: 1.25rem;
  display: flex;
  flex-direction: column;
  flex-grow: 1;              /* Fills vertical height evenly across all cards */
}

.product-category {
  font-size: 0.75rem;
  text-transform: uppercase;
  letter-spacing: 0.05em;
  font-weight: 700;
  color: #2563eb;
  margin-bottom: 0.35rem;
}

.product-title {
  font-size: 1.15rem;
  font-weight: 700;
  color: #0f172a;
  margin-bottom: 0.5rem;
}

.product-price {
  font-size: 1.25rem;
  font-weight: 800;
  color: #0f172a;
  margin-bottom: 1.25rem;
}

/* Button pinned to the card bottom */
.btn {
  margin-top: auto;          /* Pushes button to bottom regardless of title length */
  width: 100%;
  padding: 0.75rem;
  font-size: 0.95rem;
  font-weight: 600;
  color: #ffffff;
  background-color: #0f172a;
  border: none;
  border-radius: 8px;
  cursor: pointer;
  transition: background-color 0.2s ease;
}

.btn:hover {
  background-color: #2563eb;
}