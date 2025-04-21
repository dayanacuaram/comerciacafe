<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Comerciacafé</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <style>
    body {
      font-family: Arial, sans-serif;
    }
  </style>
  <script>
    // Arreglo donde se guardan los productos del carrito
    let carrito = [];

    // Función para agregar productos al carrito
    function agregarAlCarrito(nombre, precio) {
      const producto = { nombre, precio };
      carrito.push(producto); // Se agrega el producto al carrito
      actualizarCarrito(); // Actualizamos la vista del carrito
    }

    // Función para actualizar el carrito
    function actualizarCarrito() {
      const lista = document.getElementById("lista-carrito");
      lista.innerHTML = ""; // Limpiamos la lista
      let total = 0;

      carrito.forEach((producto, index) => {
        total += producto.precio;
        const item = document.createElement("li");
        item.textContent = `${producto.nombre} - $${producto.precio.toFixed(2)}`;
        lista.appendChild(item);
      });

      document.getElementById("total-carrito").textContent = `Total: $${total.toFixed(2)}`;
    }

    // Finalizar compra (solo muestra mensaje)
    function finalizarCompra() {
      if (carrito.length === 0) {
        alert("Tu carrito está vacío. Añade productos para continuar.");
      } else {
        alert("Compra realizada con éxito. ¡Gracias por tu pedido!");
        carrito = []; // Limpiamos el carrito
        actualizarCarrito(); // Actualizamos la vista del carrito
      }
    }
  </script>
</head>
<body class="bg-white text-gray-800">
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
  <section id="inicio" class="p-8">
    <h2 class="text-3xl font-bold mb-4">Bienvenidos a Comerciacafé</h2>
    <p class="text-lg">Comerciacafé es una empresa de café de origen colombiano que comenzó hace 30 años en la región montañosa de Antioquia. Con el tiempo, nuestra pasión por el café de alta calidad nos ha permitido expandirnos a nuevos mercados internacionales, ofreciendo productos frescos y de alta calidad. ¡Conoce nuestros productos y haz tu compra hoy mismo!</p>
  </section>

  <!-- Sección de Productos -->
  <section id="productos" class="p-8">
    <h2 class="text-2xl font-bold mb-4">Nuestros Productos</h2>
    <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-6">
      <!-- Producto 1 -->
      <div class="border p-4 rounded shadow">
        <h3 class="font-semibold">Café Molido 1 Libra</h3>
        <p>Precio: $25,000 COP</p>
        <button onclick="agregarAlCarrito('Café Molido 1 Libra', 25000)" class="bg-[#8B5E3C] text-white px-4 py-2 rounded mt-4">Añadir al Carrito</button>
      </div>
      <!-- Producto 2 -->
      <div class="border p-4 rounded shadow">
        <h3 class="font-semibold">Café en Grano 1 Kilo</h3>
        <p>Precio: $40,000 COP</p>
        <button onclick="agregarAlCarrito('Café en Grano 1 Kilo', 40000)" class="bg-[#8B5E3C] text-white px-4 py-2 rounded mt-4">Añadir al Carrito</button>
      </div>
      <!-- Producto 3 -->
      <div class="border p-4 rounded shadow">
        <h3 class="font-semibold">Bulto de Café 40 Kilos</h3>
        <p>Precio: $1,500,000 COP</p>
        <button onclick="agregarAlCarrito('Bulto de Café 40 Kilos', 1500000)" class="bg-[#8B5E3C] text-white px-4 py-2 rounded mt-4">Añadir al Carrito</button>
      </div>
    </div>
  </section>

  <!-- Sección Nosotros -->
  <section id="nosotros" class="p-8 bg-gray-100">
    <h2 class="text-2xl font-bold mb-4">¿Quiénes Somos?</h2>
    <p>Comerciacafé nació hace 30 años en las montañas de Antioquia, Colombia. Con una pequeña finca y mucha pasión por el café, empezamos a ofrecer nuestro producto en la región. Hoy en día, somos una empresa que exporta a varios países y se dedica a ofrecer café de la más alta calidad. Nos enorgullece compartir nuestro legado con el mundo y expandir nuestra presencia en nuevos mercados internacionales.</p>
  </section>

  <!-- Sección de Contacto -->
  <section id="contacto" class="p-8">
    <h2 class="text-2xl font-bold mb-4">Contacto</h2>
    <p>Si tienes preguntas o necesitas más información, no dudes en contactarnos.</p>
    <ul>
      <li><strong>Teléfono:</strong> 316 397 7891</li>
      <li><strong>Email:</strong> contacto@comerciacafe.com</li>
    </ul>
  </section>

  <!-- Carrito de Compras -->
  <section id="carrito" class="p-8">
    <h2 class="text-2xl font-bold mb-4">Carrito de Compras</h2>
    <ul id="lista-carrito" class="list-disc pl-5"></ul>
    <p id="total-carrito" class="font-semibold">Total: $0.00</p>
    <button onclick="finalizarCompra()" class="bg-[#8B5E3C] text-white px-6 py-2 rounded mt-4">Finalizar Compra</button>
  </section>

  <!-- Footer -->
  <footer class="bg-gray-100 text-center p-4 mt-8">
    <p>&copy; 2025 Comerciacafé. Todos los derechos reservados.</p>
  </footer>
</body>
</html>
