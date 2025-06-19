<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>S.L.E.E.K</title>
  <link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet">
  <link href="https://unpkg.com/aos@2.3.4/dist/aos.css" rel="stylesheet">
  <style>
    html {
      scroll-behavior: smooth;
    }
    .sticky-nav {
      position: sticky;
      top: 0;
      z-index: 50;
      background: white;
    }
  </style>
</head>
<body class="bg-white text-gray-800">

  <!-- Sticky Navbar -->
  <nav class="sticky-nav shadow-md py-4 px-6 flex justify-between items-center">
    <img src="sleek-logo.png" alt="SLEEK Logo" class="h-10">
    <div class="space-x-4 text-sm">
      <a href="#home" class="text-green-600">Home</a>
      <a href="#about" class="text-green-600">About</a>
      <a href="#services" class="text-green-600">Services</a>
      <a href="#shop" class="text-green-600">Shop</a>
      <a href="#upload" class="text-green-600">Upload</a>
      <a href="#contact" class="text-green-600">Contact</a>
    </div>
  </nav>

  <!-- Hero Section -->
  <section id="home" class="h-screen flex items-center justify-center bg-green-100" data-aos="fade-up">
    <div class="text-center px-4">
      <h2 class="text-4xl font-bold mb-4 text-green-700">Welcome to S.L.E.E.K</h2>
      <p class="text-lg mb-6">Style for Every Story: From Luxury to Everyday</p>
      <a href="#shop" class="bg-green-600 text-white px-6 py-3 rounded-full">Shop Now</a>
    </div>
  </section>

  <!-- About Section -->
  <section id="about" class="py-16 px-6 bg-white" data-aos="fade-up">
    <h3 class="text-2xl font-semibold mb-4">About Us</h3>
    <p>S.L.E.E.K offers stylish fashion and accessories for everyone, from luxury collections to everyday essentials. Shop trendy clothes, bags, jewelry, and more with seamless WhatsApp ordering.</p>
  </section>

  <!-- Services Section -->
  <section id="services" class="py-16 px-6 bg-green-50" data-aos="fade-up">
    <h3 class="text-2xl font-semibold mb-6">Our Services</h3>
    <ul class="list-disc list-inside space-y-2">
      <li>Personalized styling advice</li>
      <li>Wide range of sizes and styles</li>
      <li>Fast delivery via WhatsApp</li>
    </ul>
  </section>

  <!-- Shop Section -->
  <section id="shop" class="py-16 px-6 bg-white" data-aos="fade-up">
    <h3 class="text-2xl font-semibold mb-6">Shop Items</h3>
    <div id="product-grid" class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 gap-4"></div>
    <div id="pagination" class="mt-6 text-center"></div>
  </section>

  <!-- Upload Section -->
  <section id="upload" class="py-16 px-6 bg-green-50" data-aos="fade-up">
    <h3 class="text-2xl font-semibold mb-6">Add Your Product</h3>
    <form id="product-form" class="space-y-4">
      <input type="text" id="product-name" placeholder="Product Name" class="w-full p-2 border rounded" required>
      <input type="file" id="product-image" accept="image/*" class="w-full p-2 border rounded">
      <input type="text" id="product-whatsapp" placeholder="WhatsApp Order Text" class="w-full p-2 border rounded">
      <button type="submit" class="bg-green-600 text-white px-4 py-2 rounded">Upload Product</button>
    </form>
    <div class="mt-8">
      <h4 class="text-xl font-semibold mb-4">Your Uploaded Products</h4>
      <div id="custom-products" class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 gap-4"></div>
    </div>
  </section>

  <!-- Contact Section -->
  <section id="contact" class="py-16 px-6 bg-white" data-aos="fade-up">
    <h3 class="text-2xl font-semibold mb-6">Contact Us</h3>
    <form action="https://formspree.io/f/xayraoqz" method="POST" class="space-y-4">
      <input type="text" name="name" placeholder="Your Name" class="w-full p-2 border rounded" required>
      <input type="email" name="email" placeholder="Your Email" class="w-full p-2 border rounded" required>
      <textarea name="message" placeholder="Your Message" class="w-full p-2 border rounded" required></textarea>
      <button type="submit" class="bg-green-600 text-white px-4 py-2 rounded">Send Message</button>
    </form>
    <div class="mt-4">
      <a href="https://wa.me/2348100123242" class="text-green-600 underline">Order via WhatsApp</a>
    </ contest
  </section>

  <!-- Footer -->
  <footer id="footer" class="py-6 text-center bg-green-100">
    <p>© 2025 S.L.E.E.K. All rights reserved.</p>
  </footer>

  <!-- WhatsApp Floating Button -->
  <a href="https://wa.me/2348100123242" class="fixed bottom-4 right-4 bg-green-500 text-white p-3 rounded-full shadow-lg hover:bg-green-600 transition">
    💬
  </a>

  <!-- Search Bar -->
  <div class="fixed bottom-4 left-4 bg-white border rounded-full shadow-md flex items-center px-3 py-1 w-60">
    <input type="text" id="search-input" placeholder="Search products..." class="outline-none flex-1 p-1 text-sm">
  </div>

  <!-- Scripts -->
  <script src="https://unpkg.com/aos@2.3.4/dist/aos.js"></script>
  <script>
    AOS.init();

    // Unified products array with placeholder images
    const products = [
      { name: "Item 1", link: "https://wa.me/2348100123242?text=Hi%2C%20I'm%20interested%20in%20Item%201", img: "https://via.placeholder.com/150" },
      { name: "Item 2", link: "https://wa.me/2348100123242?text=Hi%2C%20I'm%20interested%20in%20Item%202", img: "https://via.placeholder.com/150" },
      { name: "Item 3", link: "https://wa.me/2348100123242?text=Hi%2C%20I'm%20interested%20in%20Item%203", img: "https://via.placeholder.com/150" },
      { name: "Item 4", link: "https://wa.me/2348100123242?text=Hi%2C%20I'm%20interested%20in%20Item%204", img: "https://via.placeholder.com/150" },
      { name: "Item 5", link: "https://wa.me/2348100123242?text=Hi%2C%20I'm%20interested%20in%20Item%205", img: "https://via.placeholder.com/150" },
      { name: "Item 6", link: "https://wa.me/2348100123242?text=Hi%2C%20I'm%20interested%20in%20Item%206", img: "https://via.placeholder.com/150" },
      { name: "Item 7", link: "https://wa.me/2348100123242?text=Hi%2C%20I'm%20interested%20in%20Item%207", img: "https://via.placeholder.com/150" },
      { name: "Item 8", link: "https://wa.me/2348100123242?text=Hi%2C%20I'm%20interested%20in%20Item%208", img: "https://via.placeholder.com/150" },
      { name: "Item 9", link: "https://wa.me/2348100123242?text=Hi%2C%20I'm%20interested%20in%20Item%209", img: "https://via.placeholder.com/150" },
      { name: "Item 10", link: "https://wa.me/2348100123242?text=Hi%2C%20I'm%20interested%20in%20Item%2010", img: "https://via.placeholder.com/150" },
      { name: "Item 11", link: "https://wa.me/2348100123242?text=Hi%2C%20I'm%20interested%20in%20Item%2011", img: "https://via.placeholder.com/150" },
      { name: "Item 12", link: "https://wa.me/2348100123242?text=Hi%2C%20I'm%20interested%20in%20Item%2012", img: "https://via.placeholder.com/150" },
      { name: "Item 13", link: "https://wa.me/2348100123242?text=Hi%2C%20I'm%20interested%20in%20Item%2013", img: "https://via.placeholder.com/150" },
      { name: "Item 14", link: "https://wa.me/2348100123242?text=Hi%2C%20I'm%20interested%20in%20Item%2014", img: "https://via.placeholder.com/150" },
      { name: "Item 15", link: "https://wa.me/2348100123242?text=Hi%2C%20I'm%20interested%20in%20Item%2015", img: "https://via.placeholder.com/150" },
      { name: "Item 16", link: "https://wa.me/2348100123242?text=Hi%2C%20I'm%20interested%20in%20Item%2016", img: "https://via.placeholder.com/150" },
      { name: "Item 17", link: "https://wa.me/2348100123242?text=Hi%2C%20I'm%20interested%20in%20Item%2017", img: "https://via.placeholder.com/150" },
      { name: "Item 18", link: "https://wa.me/2348100123242?text=Hi%2C%20I'm%20interested%20in%20Item%2018", img: "https://via.placeholder.com/150" },
      { name: "Item 19", link: "https://wa.me/2348100123242?text=Hi%2C%20I'm%20interested%20in%20Item%2019", img: "https://via.placeholder.com/150" },
      { name: "Item 20", link: "https://wa.me/2348100123242?text=Hi%2C%20I'm%20interested%20in%20Item%2020", img: "https://via.placeholder.com/150" }
    ];

    const productsPerPage = 8;
    let currentPage = 1;

    // Search functionality
    document.getElementById('search-input').addEventListener('input', function(e) {
      const searchValue = e.target.value.toLowerCase();
      const items = document.querySelectorAll('#product-grid > div');
      items.forEach(item => {
        const text = item.textContent.toLowerCase();
        item.style.display = text.includes(searchValue) ? 'block' : 'none';
      });
    });

    // Display products with pagination
    function displayProducts(page) {
      const grid = document.getElementById('product-grid');
      grid.innerHTML = "";
      const start = (page - 1) * productsPerPage;
      const end = start + productsPerPage;
      const paginatedItems = products.slice(start, end);

      paginatedItems.forEach(p => {
        const div = document.createElement('div');
        div.className = 'p-4 border rounded shadow hover:shadow-lg';
        div.innerHTML = `<img src="${p.img}" class="h-32 w-full object-cover mb-2 rounded">
                         <h4 class="font-semibold mb-2">${p.name}</h4>
                         <a href="${p.link}" target="_blank" class="text-green-600 underline">Order via WhatsApp</a>`;
        grid.appendChild(div);
      });

      renderPagination();
    }

    // Render pagination buttons
    function renderPagination() {
      const pagination = document.getElementById('pagination');
      pagination.innerHTML = "";
      const pageCount = Math.ceil(products.length / productsPerPage);
      for (let i = 1; i <= pageCount; i++) {
        const btn = document.createElement('button');
        btn.textContent = i;
        btn.className = 'mx-1 px-3 py-1 rounded border ' + (i === currentPage ? 'bg-green-600 text-white' : 'bg-white');
        btn.setAttribute('aria-label', `Go to page ${i}`);
        btn.onclick = () => {
          currentPage = i;
          displayProducts(currentPage);
        };
        pagination.appendChild(btn);
      }
    }

    // Load custom products
    function loadCustomProducts() {
      const container = document.getElementById('custom-products');
      container.innerHTML = "";
      const items = JSON.parse(localStorage.getItem('custom-products') || '[]');
      items.forEach(p => {
        const div = document.createElement('div');
        div.className = 'p-4 border rounded shadow hover:shadow-lg';
        div.innerHTML = `<img src="${p.img}" class="h-32 w-full object-cover mb-2 rounded">
                         <h4 class="font-semibold mb-1">${p.name}</h4>
                         <a href="https://wa.me/2348100123242?text=${encodeURIComponent(p.whatsapp)}" target="_blank" class="text-green-600 underline">Order</a>`;
        container.appendChild(div);
      });
    }

    // Handle product form submission
    document.getElementById('product-form').addEventListener('submit', function(e) {
      e.preventDefault();
      const name = document.getElementById('product-name').value;
      const whatsapp = document.getElementById('product-whatsapp').value || name;
      const imgFile = document.getElementById('product-image').files[0];

      const reader = new FileReader();
      reader.onload = function() {
        const imgData = reader.result;
        const products = JSON.parse(localStorage.getItem('custom-products') || '[]');
        products.push({ name, whatsapp, img: imgData });
        localStorage.setItem('custom-products', JSON.stringify(products));
        loadCustomProducts();
        document.getElementById('product-form').reset();
      };
      if (imgFile) {
        reader.readAsDataURL(imgFile);
      } else {
        const products = JSON.parse(localStorage.getItem('custom-products') || '[]');
        products.push({ name, whatsapp, img: "https://via.placeholder.com/150" });
        localStorage.setItem('custom-products', JSON.stringify(products));
        loadCustomProducts();
        document.getElementById('product-form').reset();
      }
    });

    // Combined window.onload
    window.addEventListener('load', function() {
      displayProducts(currentPage);
      loadCustomProducts();
    });
  </script>
</body>
</html>
