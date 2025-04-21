# comerciacafe<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Comerciacafé</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/axios/1.5.1/axios.min.js"></script>
</head>
<body class="bg-white text-gray-900">
  <!-- Header -->
  <header class="bg-brown-800 p-4 text-white flex justify-between items-center">
    <h1 class="text-2xl font-bold">Comerciacafé</h1>
    <nav class="space-x-4">
      <a href="#inicio" class="hover:underline">Inicio</a>
      <a href="#productos" class="hover:underline">Productos</a>
      <a href="#nosotros" class="hover:underline">Nosotros</a>
      <a href="#contacto" class="hover:underline">Contacto</a>
      <a href="#carrito" class="hover:underline">Carrito</a>
    </nav>
  </header>

  <!-- Inicio -->
  <section id="inicio" class="p-8 bg-gray-100">
    <h2 class="text-3xl font-bold mb-4">Bienvenidos a Comerciacafé</h2>
    <p class="mb-4">Café premium colombiano en diferentes presentaciones. Compra al por mayor desde 150 libras.</p>
    <img src="https://images.unsplash.com/photo-1511920170033-f8396924c348" alt="Cafe" class="w-full max-h-96 object-cover rounded-lg">
  </section>

  <!-- Productos -->
  <section id="productos" class="p-8">
    <h2 class="text-2xl font-semibold mb-6">Nuestros productos</h2>
    <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
      <div class="border p-4 rounded">
        <h3 class="font-bold">Café Tostado y Molido</h3>
        <p>Presentaciones de 1 libra y 1 kilo.</p>
        <button onclick="agregarCarrito('Cafe Molido', 5)" class="bg-brown-800 text-white px-4 py-2 mt-2 rounded">Agregar ($5 USD)</button>
      </div>
      <div class="border p-4 rounded">
        <h3 class="font-bold">Café en Grano</h3>
        <p>Desde 1 libra hasta bultos de 40 kilos.</p>
        <button onclick="agregarCarrito('Cafe en Grano', 8)" class="bg-brown-800 text-white px-4 py-2 mt-2 rounded">Agregar ($8 USD)</button>
      </div>
    </div>
  </section>

  <!-- Nosotros -->
  <section id="nosotros" class="p-8 bg-gray-100">
    <h2 class="text-2xl font-semibold mb-4">Nuestra historia</h2>
    <p>Hace 30 años, con unas pocas hectáreas de café, nació Comerciacafé. Hoy buscamos expandirnos a nuevos mercados manteniendo la calidad y tradición del café colombiano.</p>
  </section>

  <!-- Contacto -->
  <section id="contacto" class="p-8">
    <h2 class="text-2xl font-semibold mb-4">Contacto</h2>
    <p>Tel: 316 397 7891</p>
    <p>Email: info@comerciacafe.com</p>
  </section>

  <!-- Carrito -->
  <section id="carrito" class="p-8 bg-gray-100">
    <h2 class="text-2xl font-semibold mb-4">Carrito de compras</h2>
    <ul id="carrito-lista" class="mb-4"></ul>
    <p id="total-usd" class="font-bold">Total: $0 USD</p>
    <p id="total-cop">COP: $0</p>
    <p id="total-eur">EUR: €0</p>
    <div class="mt-4 space-x-2">
      <button class="bg-green-600 text-white px-4 py-2 rounded">PSE</button>
      <button class="bg-purple-600 text-white px-4 py-2 rounded">Nequi</button>
      <button class="bg-gray-700 text-white px-4 py-2 rounded">Pago contra entrega</button>
    </div>
  </section>

  <script>
    let carrito = [];

    function agregarCarrito(producto, precioUSD) {
      carrito.push({ producto, precioUSD });
      actualizarCarrito();
    }

    async function actualizarCarrito() {
      const lista = document.getElementById('carrito-lista');
      const totalUSD = carrito.reduce((sum, item) => sum + item.precioUSD, 0);
      lista.innerHTML = '';
      carrito.forEach(item => {
        const li = document.createElement('li');
        li.textContent = `${item.producto} - $${item.precioUSD} USD`;
        lista.appendChild(li);
      });
      document.getElementById('total-usd').textContent = `Total: $${totalUSD.toFixed(2)} USD`;
      // Consultar tasas de cambio
      try {
        const res = await axios.get('https://api.exchangerate-api.com/v4/latest/USD');
        const cop = totalUSD * res.data.rates.COP;
        const eur = totalUSD * res.data.rates.EUR;
        document.getElementById('total-cop').textContent = `COP: $${cop.toFixed(0)}`;
        document.getElementById('total-eur').textContent = `EUR: €${eur.toFixed(2)}`;
      } catch (error) {
        console.error('Error al obtener tasas de cambio');
      }
    }
  </script>
</body>
</html>
