<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Comerciacafé - Tienda de Café</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-50 text-gray-800">

  <!-- Navegación -->
  <header class="bg-[#5C4033] p-4 text-white flex justify-between items-center">
    <h1 class="text-2xl font-bold">Comerciacafé</h1>
    <nav class="space-x-4">
      <a href="#inicio" class="hover:underline">Inicio</a>
      <a href="#productos" class="hover:underline">Productos</a>
      <a href="#nosotros" class="hover:underline">Nosotros</a>
      <a href="#contacto" class="hover:underline">Contacto</a>
      <a href="#carrito" class="hover:underline">Carrito</a>
    </nav>
  </header>

  <!-- Sección de Inicio -->
  <section id="inicio" class="p-8 bg-gray-100 text-center">
    <h2 class="text-3xl font-bold mb-4">Bienvenidos a Comerciacafé</h2>
    <p class="text-lg mb-4">El mejor café de Colombia, directamente de las montañas a tu taza. Disfruta de nuestra selección de cafés de alta calidad.</p>
    <a href="#productos" class="bg-[#5C4033] text-white py-2 px-4 rounded hover:bg-[#4b3321] transition duration-300">Ver Productos</a>
  </section>

  <!-- Sección de Productos -->
  <section id="productos" class="p-8">
    <h2 class="text-3xl font-bold mb-6 text-center">Nuestros Productos</h2>
    <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-6">
      <!-- Producto 1 -->
      <div class="bg-white p-4 shadow-lg rounded-lg">
        <img src="https://via.placeholder.com/200" alt="Café Tostado y Molido" class="w-full h-32 object-cover rounded-lg mb-4">
        <h3 class="font-semibold text-lg">Café Tostado y Molido</h3>
        <p class="text-gray-600">Un café de tueste medio, ideal para disfrutar en cualquier momento del día.</p>
        <span class="font-bold mt-2">$15.000 COP</span>
        <button class="bg-[#5C4033] text-white py-2 px-4 rounded mt-2 hover:bg-[#4b3321] transition duration-300" onclick="addToCart('Café Tostado y Molido', 15000)">Añadir al carrito</button>
      </div>
      <!-- Producto 2 -->
      <div class="bg-white p-4 shadow-lg rounded-lg">
        <img src="https://via.placeholder.com/200" alt="Café en Grano" class="w-full h-32 object-cover rounded-lg mb-4">
        <h3 class="font-semibold text-lg">Café en Grano</h3>
        <p class="text-gray-600">Café en grano 100% colombiano, perfecto para los amantes del café fresco.</p>
        <span class="font-bold mt-2">$20.000 COP</span>
        <button class="bg-[#5C4033] text-white py-2 px-4 rounded mt-2 hover:bg-[#4b3321] transition duration-300" onclick="addToCart('Café en Grano', 20000)">Añadir al carrito</button>
      </div>
      <!-- Producto 3 -->
      <div class="bg-white p-4 shadow-lg rounded-lg">
        <img src="https://via.placeholder.com/200" alt="Café al por Mayor" class="w-full h-32 object-cover rounded-lg mb-4">
        <h3 class="font-semibold text-lg">Café al por Mayor</h3>
        <p class="text-gray-600">Compra café en grandes cantidades a precios competitivos. Ideal para negocios.</p>
        <span class="font-bold mt-2">$500.000 COP</span>
        <button class="bg-[#5C4033] text-white py-2 px-4 rounded mt-2 hover:bg-[#4b3321] transition duration-300" onclick="addToCart('Café al por Mayor', 500000)">Añadir al carrito</button>
      </div>
    </div>
  </section>

  <!-- Sección de Nosotros -->
  <section id="nosotros" class="p-8 bg-gray-100 text-center">
    <h2 class="text-3xl font-bold mb-4">Sobre Nosotros</h2>
    <p class="text-lg">Comerciacafé comenzó hace 30 años con un pequeño cultivo en las montañas colombianas. Con el paso del tiempo, hemos expandido nuestro negocio para ofrecer café de la más alta calidad en diferentes presentaciones. Hoy, nos enorgullece compartir el sabor de nuestra tierra con el mundo.</p>
  </section>

  <!-- Sección de Contacto -->
  <section id="contacto" class="p-8">
    <h2 class="text-3xl font-bold mb-6 text-center">Contáctanos</h2>
    <p class="text-lg text-center">Si tienes alguna duda o deseas realizar un pedido especial, no dudes en contactarnos.</p>
    <div class="text-center mt-4">
      <p><strong>Teléfono:</strong> 316 397 7891</p>
      <p><strong>Email:</strong> contacto@comerciacafe.com</p>
    </div>
  </section>

  <!-- Sección de Carrito -->
  <section id="carrito" class="p-8 bg-gray-100 text-center">
    <h2 class="text-3xl font-bold mb-4">Tu Carrito</h2>
    <div id="cart-items" class="mb-4">
      <p>Aún no has añadido productos al carrito.</p>
    </div>
    <button class="bg-[#5C4033] text-white py-2 px-4 rounded hover:bg-[#4b3321] transition duration-300" onclick="alert('El pago será procesado en el futuro, esta función no está implementada aún.')">Ir a Pagar</button>
  </section>

  <!-- Footer -->
  <footer class="bg-[#5C4033] text-center text-white p-4">
    <p>&copy; 2025 Comerciacafé. Todos los derechos reservados.</p>
  </footer>

  <script>
    let cart = [];

    // Función para añadir productos al carrito
    function addToCart(productName, price) {
      cart.push({ productName, price });
      updateCartDisplay();
    }

    // Función para actualizar el contenido del carrito
    function updateCartDisplay() {
      const cartItems = document.getElementById('cart-items');
      if (cart.length > 0) {
        cartItems.innerHTML = '';
        cart.forEach(item => {
          const div = document.createElement('div');
          div.classList.add('mb-2');
          div.innerHTML = `${item.productName} - $${item.price}`;
          cartItems.appendChild(div);
        });
      } else {
        cartItems.innerHTML = 'Aún no has añadido productos al carrito.';
      }
    }
  </script>

</body>
</html>
