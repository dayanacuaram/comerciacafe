<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Comerciacafé - Tu tienda de café colombiano</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-50 text-gray-800 font-sans">

  <!-- Navbar -->
  <header class="bg-[#5C4033] p-4 text-white flex justify-between items-center shadow-md">
    <h1 class="text-2xl font-bold">Comerciacafé</h1>
    <nav class="space-x-4">
      <a href="#inicio" class="hover:underline">Inicio</a>
      <a href="#productos" class="hover:underline">Productos</a>
      <a href="#nosotros" class="hover:underline">Nosotros</a>
      <a href="#contacto" class="hover:underline">Contacto</a>
      <a href="#carrito" class="hover:underline">Carrito</a>
    </nav>
  </header>

  <!-- INICIO -->
  <section id="inicio" class="bg-cover bg-center h-[60vh] flex items-center justify-center text-center text-white" style="background-image: url('https://images.unsplash.com/photo-1509042239860-f550ce710b93');">
    <div class="bg-black bg-opacity-50 p-6 rounded-lg">
      <h2 class="text-4xl font-bold mb-4">Bienvenido a Comerciacafé</h2>
      <p class="text-xl">El sabor auténtico del café colombiano, directo de las montañas a tu taza.</p>
    </div>
  </section>

  <!-- PRODUCTOS -->
  <section id="productos" class="p-10">
    <h2 class="text-3xl font-bold text-center mb-8">Nuestros Productos</h2>
    <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
      <!-- Producto 1 -->
      <div class="bg-white shadow-md rounded-lg p-4 text-center">
        <img src="https://images.unsplash.com/photo-1605478906336-530b9481b6f4" alt="Café Tostado" class="w-full h-40 object-cover rounded mb-4">
        <h3 class="text-xl font-semibold">Café Tostado y Molido</h3>
        <p class="text-gray-600 mt-2">Tueste medio perfecto para cafetera o prensa francesa.</p>
        <p class="text-lg font-bold mt-2">$15.000 COP</p>
        <button onclick="addToCart('Café Tostado y Molido', 15000)" class="mt-3 bg-[#5C4033] text-white px-4 py-2 rounded hover:bg-[#4b3321]">Añadir al carrito</button>
      </div>
      <!-- Producto 2 -->
      <div class="bg-white shadow-md rounded-lg p-4 text-center">
        <img src="https://images.unsplash.com/photo-1509042239860-f550ce710b93" alt="Café en Grano" class="w-full h-40 object-cover rounded mb-4">
        <h3 class="text-xl font-semibold">Café en Grano</h3>
        <p class="text-gray-600 mt-2">Granos frescos, seleccionados y empacados al vacío.</p>
        <p class="text-lg font-bold mt-2">$20.000 COP</p>
        <button onclick="addToCart('Café en Grano', 20000)" class="mt-3 bg-[#5C4033] text-white px-4 py-2 rounded hover:bg-[#4b3321]">Añadir al carrito</button>
      </div>
      <!-- Producto 3 -->
      <div class="bg-white shadow-md rounded-lg p-4 text-center">
        <img src="https://images.unsplash.com/photo-1564939558297-529eda6b7b17" alt="Café al por Mayor" class="w-full h-40 object-cover rounded mb-4">
        <h3 class="text-xl font-semibold">Café al por Mayor</h3>
        <p class="text-gray-600 mt-2">Ideal para cafeterías, restaurantes y distribuidores.</p>
        <p class="text-lg font-bold mt-2">$500.000 COP</p>
        <button onclick="addToCart('Café al por Mayor', 500000)" class="mt-3 bg-[#5C4033] text-white px-4 py-2 rounded hover:bg-[#4b3321]">Añadir al carrito</button>
      </div>
    </div>
  </section>

  <!-- NOSOTROS -->
  <section id="nosotros" class="bg-gray-100 p-10 text-center">
    <h2 class="text-3xl font-bold mb-4">Nuestra Historia</h2>
    <p class="max-w-3xl mx-auto text-lg text-gray-700">
      Comerciacafé nace en el corazón del Eje Cafetero colombiano. Durante más de 30 años, nuestras fincas han cultivado café de altura, seleccionado a mano y procesado con técnicas tradicionales y sostenibles. Hoy llevamos ese mismo sabor auténtico hasta la puerta de tu casa.
    </p>
  </section>

  <!-- CONTACTO -->
  <section id="contacto" class="p-10 text-center">
    <h2 class="text-3xl font-bold mb-4">Contáctanos</h2>
    <p class="text-lg">¿Tienes dudas o quieres hacer un pedido personalizado?</p>
    <p class="mt-2">📞 <strong>316 397 7891</strong> | 📧 <strong>contacto@comerciacafe.com</strong></p>
  </section>

  <!-- CARRITO -->
  <section id="carrito" class="bg-gray-100 p-10 text-center">
    <h2 class="text-3xl font-bold mb-6">Carrito de Compras</h2>
    <div id="cart-items" class="text-left max-w-xl mx-auto bg-white shadow-md rounded p-4">
      <p>Aún no has añadido productos al carrito.</p>
    </div>
    <button onclick="alert('La opción de pago estará disponible pronto.')" class="mt-4 bg-[#5C4033] text-white px-6 py-2 rounded hover:bg-[#4b3321]">Proceder al Pago</button>
  </section>

  <!-- FOOTER -->
  <footer class="bg-[#5C4033] text-white text-center p-4 mt-10">
    &copy; 2025 Comerciacafé. Todos los derechos reservados.
  </footer>

  <!-- SCRIPT DE CARRITO -->
  <script>
    let cart = [];

    function addToCart(productName, price) {
      cart.push({ productName, price });
      updateCart();
    }

    function updateCart() {
      const container = document.getElementById('cart-items');
      container.innerHTML = '';
      if (cart.length === 0) {
        container.innerHTML = '<p>Aún no has añadido productos al carrito.</p>';
        return;
      }
      let total = 0;
      cart.forEach(item => {
        total += item.price;
        const row = document.createElement('div');
        row.classList.add('flex', 'justify-between', 'border-b', 'py-2');
        row.innerHTML = `<span>${item.productName}</span><span>$${item.price.toLocaleString()} COP</span>`;
        container.appendChild(row);
      });
      const totalRow = document.createElement('div');
      totalRow.classList.add('mt-4', 'font-bold', 'text-right');
      totalRow.textContent = `Total: $${total.toLocaleString()} COP`;
      container.appendChild(totalRow);
    }
  </script>

</body>
</html>
<!-- SCRIPT DE CARRITO MEJORADO -->
<script>
  let cart = [];
  const exchangeRates = { USD: 0.00026, EUR: 0.00024, COP: 1 };

  function addToCart(productName, price) {
    const existing = cart.find(item => item.productName === productName);
    if (existing) {
      existing.quantity += 1;
    } else {
      cart.push({ productName, price, quantity: 1 });
    }
    updateCart();
  }

  function updateCart() {
    const container = document.getElementById('cart-items');
    const currency = document.getElementById('currency').value;
    const rate = exchangeRates[currency];
    container.innerHTML = '';

    if (cart.length === 0) {
      container.innerHTML = '<p>Aún no has añadido productos al carrito.</p>';
      return;
    }

    let total = 0;
    cart.forEach(item => {
      const convertedPrice = item.price * rate * item.quantity;
      total += convertedPrice;

      const row = document.createElement('div');
      row.classList.add('flex', 'justify-between', 'border-b', 'py-2');
      row.innerHTML = `
        <span>${item.productName} x${item.quantity}</span>
        <span>${convertedPrice.toFixed(2)} ${currency}</span>
      `;
      container.appendChild(row);
    });

    const totalRow = document.createElement('div');
    totalRow.classList.add('mt-4', 'font-bold', 'text-right');
    totalRow.textContent = `Total: ${total.toFixed(2)} ${currency}`;
    container.appendChild(totalRow);
  }

  document.getElementById('currency').addEventListener('change', updateCart);
</script>
