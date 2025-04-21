<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Comerciacafé - Tienda Online</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <script>
    let carrito = [];

    function agregarAlCarrito(nombre, precio) {
      carrito.push({ nombre, precio });
      actualizarCarrito();
    }

    function actualizarCarrito() {
      const lista = document.getElementById("lista-carrito");
      lista.innerHTML = "";
      let total = 0;

      carrito.forEach((producto) => {
        total += producto.precio;
        const item = document.createElement("li");
        item.textContent = `${producto.nombre} - $${producto.precio.toFixed(2)}`;
        lista.appendChild(item);
      });

      document.getElementById("total-carrito").textContent = `Total: $${total.toFixed(2)}`;
    }
  </script>
</head>
<body class="bg-white text-gray-800">

  <!-- Header -->
  <header class="bg-[#5C4033] p-6 text-white flex justify-between items-center fixed w-full top-0 z-10 shadow-lg">
    <img src="logo.png" alt="Comerciacafé Logo" class="h-12">
    <h1 class="text-2xl font-bold">Comerciacafé</h1>
    <nav class="space-x-6">
      <a href="#inicio" class="hover:underline">Inicio</a>
      <a href="#productos" class="hover:underline">Productos</a>
      <a href="#nosotros" class="hover:underline">Nosotros</a>
      <a href="#contacto" class="hover:underline">Contacto</a>
      <a href="#carrito" class="hover:underline">Carrito</a>
    </nav>
  </header>

  <!-- Sección de Inicio -->
  <section id="inicio" class="pt-20 p-8 bg-gray-50 text-center">
    <h2 class="text-4xl font-bold mb-4">Bienvenidos a Comerciacafé</h2>
    <p class="text-lg">En Comerciacafé, ofrecemos café de calidad premium directamente de las montañas colombianas. ¡Prueba lo mejor del café colombiano hoy mismo!</p>
  </section>

  <!-- Sección de Productos -->
  <section id="productos" class="p-8 bg-white">
    <h2 class="text-3xl font-bold text-center mb-8">Nuestros Productos</h2>
    <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-8">
      <!-- Producto 1 -->
      <div class="border p-4 rounded-lg shadow-md">
        <h3 class="text-xl font-semibold">Café Molido 1 Libra</h3>
        <p class="mb-4">Precio: $25,000 COP</p>
        <button onclick="agregarAlCarrito('Café Molido 1 Libra', 25000)" class="bg-[#8B5E3C] text-white px-6 py-2 rounded">Añadir al Carrito</button>
      </div>
      <!-- Producto 2 -->
      <div class="border p-4 rounded-lg shadow-md">
        <h3 class="text-xl font-semibold">Café en Grano 1 Kilo</h3>
        <p class="mb-4">Precio: $40,000 COP</p>
        <button onclick="agregarAlCarrito('Café en Grano 1 Kilo', 40000)" class="bg-[#8B5E3C] text-white px-6 py-2 rounded">Añadir al Carrito</button>
      </div>
      <!-- Producto 3 -->
      <div class="border p-4 rounded-lg shadow-md">
        <h3 class="text-xl font-semibold">Bulto de Café 40 Kilos</h3>
        <p class="mb-4">Precio: $1,500,000 COP</p>
        <button onclick="agregarAlCarrito('Bulto de Café 40 Kilos', 1500000)" class="bg-[#8B5E3C] text-white px-6 py-2 rounded">Añadir al Carrito</button>
      </div>
    </div>
  </section>

  <!-- Sección de Nosotros -->
  <section id="nosotros" class="p-8 bg-gray-100 text-center">
    <h2 class="text-3xl font-bold mb-4">¿Quiénes Somos?</h2>
    <p class="text-lg max-w-3xl mx-auto">Comerciacafé comenzó hace 30 años en las montañas de Antioquia, Colombia. Desde entonces, nos hemos dedicado a cultivar el mejor café, seleccionando solo lo mejor para nuestros clientes. Hoy, expandimos nuestras fronteras, llevando el café colombiano a más partes del mundo.</p>
  </section>

  <!-- Sección de Contacto -->
  <section id="contacto" class="p-8 bg-white text-center">
    <h2 class="text-3xl font-bold mb-4">Contacto</h2>
    <p class="text-lg mb-4">Si tienes alguna pregunta o deseas más información, no dudes en ponerte en contacto con nosotros:</p>
    <ul class="text-lg">
      <li><strong>Teléfono:</strong> 316 397 7891</li>
      <li><strong>Email:</strong> contacto@comerciacafe.com</li>
    </ul>
  </section>

  <!-- Carrito -->
  <section id="carrito" class="p-8 bg-gray-100">
    <h2 class="text-3xl font-bold mb-4 text-center">Tu Carrito</h2>
    <ul id="lista-carrito" class="list-disc pl-6 mb-4"></ul>
    <p id="total-carrito" class="font-semibold text-xl">Total: $0.00</p>
  </section>

  <!-- Footer -->
  <footer class="bg-gray-100 text-center p-6 mt-8">
    <p>&copy; 2025 Comerciacafé. Todos los derechos reservados.</p>
  </footer>

</body>
</html>
