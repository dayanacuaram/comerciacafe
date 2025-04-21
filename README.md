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
      <a href="index.html" class="hover:underline">Inicio</a>
      <a href="productos.html" class="hover:underline">Productos</a>
      <a href="nosotros.html" class="hover:underline">Nosotros</a>
      <a href="contacto.html" class="hover:underline">Contacto</a>
      <a href="carrito.html" class="hover:underline">Carrito</a>
    </nav>
  </header>

  <!-- Sección de Inicio -->
  <section id="inicio" class="p-8">
    <h2 class="text-3xl font-bold mb-4">Bienvenidos a Comerciacafé</h2>
    <p class="text-lg">Comerciacafé es una empresa colombiana con más de 30 años de experiencia en la producción de café premium. Ofrecemos productos de alta calidad con el mejor sabor para nuestros clientes. ¡Descubre nuestras opciones y haz tu compra hoy!</p>
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
  <title>Productos - Comerciacafé</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <style>
    body {
      font-family: Arial, sans-serif;
    }
  </style>
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
  <!-- Navegación -->
  <header class="bg-[#5C4033] p-4 text-white flex justify-between items-center">
    <h1 class="text-2xl font-bold">Comerciacafé</h1>
    <nav class="space-x-4">
      <a href="index.html" class="hover:underline">Inicio</a>
      <a href="productos.html" class="hover:underline">Productos</a>
      <a href="nosotros.html" class="hover:underline">Nosotros</a>
      <a href="contacto.html" class="hover:underline">Contacto</a>
      <a href="carrito.html" class="hover:underline">Carrito</a>
    </nav>
  </header>

  <!-- Sección de Productos -->
  <section id="productos" class="p-8">
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
  <title>Nosotros - Comerciacafé</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-white text-gray-800">
  <!-- Navegación -->
  <header class="bg-[#5C4033] p-4 text-white flex justify-between items-center">
    <h1 class="text-2xl font-bold">Comerciacafé</h1>
    <nav class="space-x-4">
      <a href="index.html" class="hover:underline">Inicio</a>
      <a href="productos.html" class="hover:underline">Productos</a>
      <a href="nosotros.html" class="hover:underline">Nosotros</a>
      <a href="contacto.html" class="hover:underline">Contacto</a>
      <a href="carrito.html" class="hover:underline">Carrito</a>
    </nav>
  </header>

  <!-- Sección de Nosotros -->
  <section id="nosotros" class="p-8 bg-gray-100">
    <h2 class="text-2xl font-bold mb-4">¿Quiénes Somos?</h2>
    <p>Comerciacafé nació hace 30 años en Antioquia, Colombia, con la idea de ofrecer café de la mejor calidad. Hoy somos una empresa que lleva el sabor de Colombia al mundo, ofreciendo café premium en diferentes presentaciones para todos nuestros clientes.</p>
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
  <title>Contacto - Comerciacafé</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-white text-gray-800">
  <!-- Navegación -->
  <header class="bg-[#5C4033] p-4 text-white flex justify-between items-center">
    <h1 class="text-2xl font-bold">Comerciacafé</h1>
    <nav class="space-x-4">
      <a href="index.html" class="hover:underline">Inicio</a>
      <a href="productos.html" class="hover:underline">Productos</a>
      <a href="nosotros.html" class="hover:underline">Nosotros</a>
      <a href="contacto.html" class="hover:underline">Contacto</a>
      <a href="carrito.html" class="hover:underline">Carrito</a>
    </nav>
  </header>

  <!-- Sección de Contacto -->
  <section id="contacto" class="p-8">
    <h2 class="text-2xl font-bold mb-4">Contacto</h2>
    <p>Si tienes preguntas, no dudes en contactarnos:</p>
    <ul>
      <li><strong>Teléfono:</strong> 316 397 7891</li>
      <li><strong>Email:</strong> contacto@comerciacafe.com</li>
    </ul>
  </section>

  <!-- Footer -->
  <footer class="bg-gray-100 text-center p-4 mt-8">
    <p>&copy; 2025 Comerciacafé. Todos los derechos reservados.</p>
  </footer><!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Carrito - Comerciacafé</title>
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

    function finalizarCompra() {
      if (carrito.length === 0) {
        alert("El carrito está vacío. Añade productos para continuar.");
      } else {
        alert("Compra realizada con éxito.");
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
    <nav class="space

</body>
</html>
