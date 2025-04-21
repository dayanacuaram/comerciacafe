<!DOCTYPE html>
<html lang="es">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Comerciacafé</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <script>
    let carrito = [];

    function agregarAlCarrito(nombre, precio) {
      const producto = { nombre, precio };
      carrito.push(producto);
      actualizarCarrito();
    }

    function actualizarCarrito() {
      const lista = document.getElementById("lista-carrito");
      lista.innerHTML = "";
      let total = 0;
      carrito.forEach((producto, index) => {
        total += producto.precio;
        const item = document.createElement("li");
        item.className = "mb-2";
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
      <a href="productos.html" class="hover:underline">Productos</a>
      <a href="nosotros.html" class="hover:underline">Nosotros</a>
      <a href="contacto.html" class="hover:underline">Contacto</a>
      <a href="carrito.html" class="hover:underline font-bold">Carrito</a>
    </nav>
  </header>

  <!-- Sección de Inicio -->
  <section class="p-8 text-center">
    <h2 class="text-3xl font-bold mb-4">Bienvenido a Comerciacafé</h2>
    <p class="text-lg">Comerciacafé es una empresa colombiana con más de 30 años en la industria del café. Desde nuestras pequeñas hectáreas de cultivo, hemos logrado ofrecer el mejor café de la región a nivel nacional e internacional. Nuestra misión es expandirnos a nuevos mercados, llevando la excelencia de nuestros productos a más consumidores.</p>
  </section>

  <!-- Productos -->
  <section class="p-8">
    <h2 class="text-2xl font-bold mb-4">Nuestros Productos</h2>
    <p class="text-lg mb-6">Ofrecemos café de alta calidad en diferentes presentaciones. Ya sea que estés buscando café tostado y molido, en grano o en grandes cantidades para empaquetar, tenemos el producto ideal para ti.</p>
    
    <!-- Productos en Grid -->
    <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
      <button onclick="agregarAlCarrito('Café Molido 1 libra', 25000)" class="bg-[#8B5E3C] text-white px-4 py-2 rounded">Añadir Café Molido 1 libra</button>
      <button onclick="agregarAlCarrito('Café en grano 1 kilo', 40000)" class="bg-[#8B5E3C] text-white px-4 py-2 rounded">Añadir Café en grano 1 kilo</button>
      <button onclick="agregarAlCarrito('Bulto Café 40 kilos', 1500000)" class="bg-[#8B5E3C] text-white px-4 py-2 rounded">Añadir Bulto Café 40 kilos</button>
    </div>
  </section>

  <!-- Carrito -->
  <section class="p-8">
    <h2 class="text-2xl font-bold mb-4">Carrito de Compras</h2>
    <ul id="lista-carrito" class="mb-4"></ul>
    <p id="total-carrito" class="font-semibold"></p>
  </section>

  <!-- Sección Nosotros -->
  <section class="p-8 bg-gray-100">
    <h2 class="text-2xl font-bold mb-4">Nuestra Historia</h2>
    <p class="text-lg">Hace más de tres décadas, nuestra empresa comenzó con una pequeña plantación de café en las montañas de Colombia. Aunque contábamos con pocas hectáreas, nuestra dedicación y amor por el café nos permitieron crecer y convertirnos en una marca reconocida. Hoy, estamos listos para llevar nuestra pasión a nuevos mercados, buscando ofrecer lo mejor de nuestra tierra en cada taza.</p>
  </section>

  <!-- Sección de Contacto -->
  <section class="p-8">
    <h2 class="text-2xl font-bold mb-4">Contacto</h2>
    <p class="text-lg">Si tienes alguna consulta, no dudes en contactarnos. Puedes llamarnos al 316 397 7891 o escribirnos al correo <a href="mailto:info@comerciacafe.com" class="text-[#5C4033]">info@comerciacafe.com</a>.</p>
  </section>

  <!-- Footer -->
  <footer class="bg-gray-100 text-center p-4 mt-8">
    <p>&copy; 2025 Comerciacafé. Todos los derechos reservados.</p>
  </footer>

</body>

</html>
