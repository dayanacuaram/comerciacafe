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
</head>

<body class="bg-white text-gray-800">
  <!-- Navegación -->
  <header class="bg-[#5C4033] p-4 text-white flex justify-between items-center">
    <h1 class="text-2xl font-bold">Comerciacafé</h1>
    <nav class="space-x-4">
      <a href="inicio.html" class="hover:underline">Inicio</a>
      <a href="productos.html" class="hover:underline">Productos</a>
      <a href="nosotros.html" class="hover:underline">Nosotros</a>
      <a href="contacto.html" class="hover:underline">Contacto</a>
      <a href="carrito.html" class="hover:underline font-bold">Carrito</a>
    </nav>
  </header>

  <!-- Sección de Inicio -->
  <section class="p-8 text-center">
    <h2 class="text-3xl font-bold mb-4">Bienvenido a Comerciacafé</h2>
    <p class="text-lg mb-4">Disfruta de nuestro delicioso café de la región, con la mejor calidad y sabor. Navega por nuestras opciones y haz tu pedido en línea.</p>
    <a href="productos.html" class="bg-[#8B5E3C] text-white px-6 py-2 rounded">Ver Productos</a>
  </section>

  <!-- Footer -->
  <footer class="bg-gray-100 text-center p-4 mt-8">
    <p>&copy; 2025 Comerciacafé. Todos los derechos reservados.</p>
  </footer>

</body>

</html>
<!DOCTYPE html>
<html lang="es">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Comerciacafé - Productos</title>
  <script src="https://cdn.tailwindcss.com"></script>
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
  <!-- Navegación -->
  <header class="bg-[#5C4033] p-4 text-white flex justify-between items-center">
    <h1 class="text-2xl font-bold">Comerciacafé</h1>
    <nav class="space-x-4">
      <a href="inicio.html" class="hover:underline">Inicio</a>
      <a href="productos.html" class="hover:underline font-bold">Productos</a>
      <a href="nosotros.html" class="hover:underline">Nosotros</a>
      <a href="contacto.html" class="hover:underline">Contacto</a>
      <a href="carrito.html" class="hover:underline">Carrito</a>
    </nav>
  </header>

  <!-- Sección de Productos -->
  <section class="p-8">
    <h2 class="text-2xl font-bold mb-4">Nuestros Productos</h2>
    <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-6">
      <div class="border p-4 rounded shadow">
        <h3 class="font-semibold">Café Molido 1 Libra</h3>
        <p>Precio: $25,000 COP</p>
        <button onclick="agregarAlCarrito('Café Molido 1 Libra', 25000)" class="bg-[#8B5E3C] text-white px-4 py-2 rounded mt-4">Añadir al Carrito</button>
      </div>
      <div class="border p-4 rounded shadow">
        <h3 class="font-semibold">Café en Grano 1 Kilo</h3>
        <p>Precio: $40,000 COP</p>
        <button onclick="agregarAlCarrito('Café en Grano 1 Kilo', 40000)" class="bg-[#8B5E3C] text-white px-4 py-2 rounded mt-4">Añadir al Carrito</button>
      </div>
      <div class="border p-4 rounded shadow">
        <h3 class="font-semibold">Bulto de Café 40 Kilos</h3>
        <p>Precio: $1,500,000 COP</p>
        <button onclick="agregarAlCarrito('Bulto de Café 40 Kilos', 1500000)" class="bg-[#8B5E3C] text-white px-4 py-2 rounded mt-4">Añadir al Carrito</button>
      </div>
    </div>
  </section>

  <!-- Carrito de compras -->
  <section class="p-8">
    <h2 class="text-2xl font-bold mb-4">Carrito</h2>
    <ul id="lista-carrito"></ul>
    <p id="total-carrito">Total: $0.00</p>
  </section>

  <!-- Footer -->
  <footer class="bg-gray-100 text-center p-4 mt-8">
    <p>&copy; 2025 Comerciacafé. Todos los derechos reservados.</p>
  </footer>
</body>

</html>
<!DOCTYPE html>
<html lang="es">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Comerciacafé - Carrito</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <script>
    // Arreglo donde se guardan los productos del carrito
    let carrito = [];

    // Función para agregar productos al carrito
    function agregarAlCarrito(nombre, precio) {
      const producto = { nombre, precio };
      carrito.push(producto);
      actualizarCarrito();
    }

    // Función para actualizar el carrito
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

    // Finalizar compra
    function finalizarCompra() {
      if (carrito.length === 0) {
        alert("Tu carrito está vacío. Añade productos para continuar.");
      } else {
        alert("Compra realizada con éxito. ¡Gracias por tu pedido!");
        carrito = [];
        actualizarCarrito();
      }
    }
  </script>
</head>

<body class="bg-white text-gray-800">
  <!-- Navegación -->
  <header class="bg-[#5C4033] p-4 text-white flex justify-between items-center">
    <h1 class="text-2xl font-bold">Comerciacafé</h1>
    <nav class="space-x-4">
      <a href="inicio.html" class="hover:underline">Inicio</a>
      <a href="productos.html" class="hover:underline">Productos</a>
      <a href="nosotros.html" class="hover:underline">Nosotros</a>
      <a href="contacto.html" class="hover:underline">Contacto</a>
      <a href="carrito.html" class="hover:underline font-bold">Carrito</a>
    </nav>
  </header>

  <!-- Sección de Carrito -->
  <section class="p-8">
    <h2 class="text-2xl font-bold mb-4">Carrito de Compras</h2>
    <ul id="lista-carrito"></ul>
    <p id="total-carrito">Total: $0.00</p>
    <button onclick="finalizarCompra()" class="bg-[#8B5E3C] text-white px-6 py-2 rounded mt-4">Finalizar Compra</button>
  </section>

  <!-- Footer -->
  <footer class="bg-gray-100 text-center p-4 mt-8">
    <p>&copy;
