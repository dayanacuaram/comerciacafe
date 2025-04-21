<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Comerciacafé - Tu tienda de café colombiano</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
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
    </nav>
  </header>

  <!-- INICIO -->
  <section id="inicio" class="bg-cover bg-center h-[60vh] flex items-center justify-center text-center text-white" style="background-image: url('https://images.unsplash.com/photo-1509042239860-f550ce710b93?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80');">
    <div class="bg-black bg-opacity-50 p-6 rounded-lg">
      <h2 class="text-4xl font-bold mb-4">Bienvenido a Comerciacafé</h2>
      <p class="text-xl">El sabor auténtico del café colombiano, directo de las montañas a tu taza.</p>
    </div>
  </section>

  <!-- PRODUCTOS Y CARRITO -->
  <section id="productos" class="p-10">
    <h2 class="text-3xl font-bold text-center mb-8">Nuestros Productos</h2>
    <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
      <div class="bg-white shadow-md rounded-lg p-4 text-center">
        <img src="https://images.unsplash.com/photo-1592842044709-5643a9f71f8e?auto=format&fit=crop&w=800&q=80" alt="Café Tostado" class="w-full h-40 object-cover rounded mb-4">
        <h3 class="text-xl font-semibold">Café Tostado y Molido</h3>
        <p class="text-gray-600 mt-2">Tueste medio perfecto para cafetera o prensa francesa.</p>
        <p class="text-lg font-bold mt-2" id="price1">15,000 COP</p>
        <button onclick="addToCart('Café Tostado y Molido', 15000)" class="mt-3 bg-[#5C4033] text-white px-4 py-2 rounded hover:bg-[#4b3321]">Añadir al carrito</button>
      </div>
      <div class="bg-white shadow-md rounded-lg p-4 text-center">
        <img src="https://images.unsplash.com/photo-1612197619350-196d1df9b44e?auto=format&fit=crop&w=800&q=80" alt="Café en Grano" class="w-full h-40 object-cover rounded mb-4">
        <h3 class="text-xl font-semibold">Café en Grano</h3>
        <p class="text-gray-600 mt-2">Granos frescos, seleccionados y empacados al vacío.</p>
        <p class="text-lg font-bold mt-2" id="price2">20,000 COP</p>
        <button onclick="addToCart('Café en Grano', 20000)" class="mt-3 bg-[#5C4033] text-white px-4 py-2 rounded hover:bg-[#4b3321]">Añadir al carrito</button>
      </div>
      <div class="bg-white shadow-md rounded-lg p-4 text-center">
        <img src="https://images.unsplash.com/photo-1601758123927-196dbde0e57e?auto=format&fit=crop&w=800&q=80" alt="Café al por Mayor" class="w-full h-40 object-cover rounded mb-4">
        <h3 class="text-xl font-semibold">Café al por Mayor</h3>
        <p class="text-gray-600 mt-2">Ideal para cafeterías, restaurantes y distribuidores.</p>
        <p class="text-lg font-bold mt-2" id="price3">500,000 COP</p>
        <button onclick="addToCart('Café al por Mayor', 500000)" class="mt-3 bg-[#5C4033] text-white px-4 py-2 rounded hover:bg-[#4b3321]">Añadir al carrito</button>
      </div>
    </div>

    <!-- Carrito y Cambio de Moneda -->
    <div id="cart-container" class="mt-8 bg-white shadow-md rounded p-6">
      <h3 class="text-2xl font-semibold mb-4">Carrito de Compras</h3>
      <div id="cart-items" class="text-left max-w-xl mx-auto">
        <p>Aún no has añadido productos al carrito.</p>
      </div>
      <div class="mt-4">
        <p class="mb-2">Selecciona tu moneda preferida:</p>
        <select id="currency" class="px-3 py-2 rounded border">
          <option value="COP">COP (Pesos Colombianos)</option>
          <option value="USD">USD (Dólares)</option>
          <option value="EUR">EUR (Euros)</option>
        </select>
      </div>
      <button onclick="alert('La opción de pago estará disponible pronto.')" class="mt-4 bg-[#5C4033] text-white px-6 py-2 rounded hover:bg-[#4b3321]">Proceder al Pago</button>
    </div>
  </section>

  <!-- FOOTER -->
  <footer class="bg-[#5C4033] text-white text-center p-4 mt-10">
    &copy; 2025 Comerciacafé. Todos los derechos reservados.
  </footer>

  <script>
    let cart = [];
    const exchangeRates = {
      COP: 1,
      USD: 0.00026, 
      EUR: 0.00024
    };

    // Función para obtener las tasas de cambio en vivo
    function getExchangeRates() {
      $.get('https://v6.exchangerate-api.com/v6/YOUR_API_KEY/latest/COP', function(data) {
        exchangeRates.USD = data.conversion_rates.USD;
        exchangeRates.EUR = data.conversion_rates.EUR;
        updateCart();
      });
    }

    function addToCart(productName, price) {
      cart.push({ productName, price });
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
        const convertedPrice = item.price * rate;
        total += convertedPrice;
        const row = document.createElement('div');
        row.classList.add('flex', 'justify-between', 'border-b', 'py-2');
        row.innerHTML = `<span>${item.productName}</span><span>${convertedPrice.toFixed(2)} ${currency}</span>`;
        container.appendChild(row);
      });

      const totalRow = document.createElement('div');
      totalRow.classList.add('mt-4', 'font-bold', 'text-right');
      totalRow.textContent = `Total: ${total.toFixed(2)} ${currency}`;
      container.appendChild(totalRow);
    }

    document.getElementById('currency').addEventListener('change', updateCart);

    // Llamar a la API de tasas de cambio al cargar la página
    getExchangeRates();
  </script>

</body>
</html>
