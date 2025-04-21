<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Comerciacafé</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <script>
    const productos = [
      { nombre: "Café Tostado - 1 libra", precioCOP: 25000 },
      { nombre: "Café Molido - 1 kilo", precioCOP: 45000 },
      { nombre: "Café en grano - Bulto 40kg", precioCOP: 1500000 },
    ];

    function agregarAlCarrito(producto) {
      const carrito = JSON.parse(localStorage.getItem('carrito')) || [];
      carrito.push(producto);
      localStorage.setItem('carrito', JSON.stringify(carrito));
      alert(`${producto.nombre} agregado al carrito.`);
    }

    function mostrarCarrito() {
      const carrito = JSON.parse(localStorage.getItem('carrito')) || [];
      const tbody = document.getElementById('carrito-body');
      let total = 0;

      carrito.forEach(item => {
        total += item.precioCOP;
        const fila = `<tr>
                        <td class="border px-4 py-2">${item.nombre}</td>
                        <td class="border px-4 py-2">$${item.precioCOP.toLocaleString()} COP</td>
                      </tr>`;
        tbody.innerHTML += fila;
      });

      document.getElementById('total-cop').textContent = `$${total.toLocaleString()} COP`;
    }

    function simularPago() {
      alert('Simulando pago con pasarela PayU...');
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

  <!-- Inicio -->
  <section id="inicio" class="p-8 text-center">
    <h2 class="text-3xl font-bold mb-4">Bienvenido a Comerciacafé</h2>
    <p class="mb-4 text-lg">Somos una empresa cafetera 100% colombiana dedicada a la producción, comercialización y exportación de café premium. Con más de 30 años de experiencia, brindamos calidad, sabor y tradición a nuestros clientes en todo el mundo.</p>
    <img src="https://images.unsplash.com/photo-1511920170033-f8396924c348" alt="Café colombiano" class="w-full max-h-96 object-cover rounded-lg mx-auto">
  </section>

  <!-- Productos -->
  <section id="productos" class="p-8 bg-gray-50">
    <h2 class="text-2xl font-bold mb-6 text-center">Nuestros Productos</h2>
    <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
      <div class="bg-white p-4 rounded shadow">
        <h3 class="text-xl font-semibold mb-2">Café Tostado - 1 libra</h3>
        <p class="mb-2">$25.000 COP</p>
        <button onclick='agregarAlCarrito(productos[0])' class="bg-green-600 text-white px-4 py-2 rounded">Agregar al carrito</button>
      </div>
      <div class="bg-white p-4 rounded shadow">
        <h3 class="text-xl font-semibold mb-2">Café Molido - 1 kilo</h3>
        <p class="mb-2">$45.000 COP</p>
        <button onclick='agregarAlCarrito(productos[1])' class="bg-green-600 text-white px-4 py-2 rounded">Agregar al carrito</button>
      </div>
      <div class="bg-white p-4 rounded shadow">
        <h3 class="text-xl font-semibold mb-2">Café en grano - Bulto 40kg</h3>
        <p class="mb-2">$1.500.000 COP</p>
        <button onclick='agregarAlCarrito(productos[2])' class="bg-green-600 text-white px-4 py-2 rounded">Agregar al carrito</button>
      </div>
    </div>
  </section>

  <!-- Nosotros -->
  <section id="nosotros" class="p-8">
    <h2 class="text-2xl font-bold mb-4 text-center">Sobre Nosotros</h2>
    <p class="max-w-3xl mx-auto text-justify">Hace 30 años, en una pequeña finca cafetera ubicada en las montañas de Colombia, nació Comerciacafé. Lo que empezó como un sueño familiar con apenas unas hectáreas de cultivo, hoy es una empresa con proyección internacional, dedicada a ofrecer café de alta calidad a clientes exigentes que valoran el sabor, la historia y el compromiso con el medio ambiente. A lo largo de estas tres décadas, hemos perfeccionado nuestras técnicas de cultivo, tostado y selección de granos, posicionándonos como una marca reconocida por su autenticidad y responsabilidad social. Queremos seguir creciendo y llevar nuestro café colombiano a cada rincón del mundo.</p>
  </section>

  <!-- Contacto -->
  <section id="contacto" class="p-8 bg-gray-50">
    <h2 class="text-2xl font-bold mb-4 text-center">Contacto</h2>
    <div class="max-w-2xl mx-auto bg-white p-6 rounded shadow">
      <p><strong>Teléfono:</strong> 316 397 7891</p>
      <p><strong>Correo:</strong> info@comerciacafe.com</p>
      <p><strong>Dirección:</strong> Calle 123 #45-67, Manizales, Caldas, Colombia</p>
    </div>
  </section>

  <!-- Carrito -->
  <section id="carrito" class="p-8">
    <h2 class="text-2xl font-bold mb-4 text-center">Tu Carrito</h2>
    <table class="table-auto w-full border mt-4">
      <thead>
        <tr class="bg-gray-200">
          <th class="border px-4 py-2">Producto</th>
          <th class="border px-4 py-2">Precio</th>
        </tr>
      </thead>
      <tbody id="carrito-body"></tbody>
    </table>

    <div class="text-right mt-6">
      <p class="text-xl font-semibold">Total: <span id="total-cop"></span></p>
      <button onclick="simularPago()" class="mt-4 bg-green-600 text-white px-6 py-3 rounded">Pagar con PayU</button>
    </div>
  </section>

  <!-- Footer -->
  <footer class="bg-gray-100 text-center p-4 mt-8">
    <p>&copy; 2025 Comerciacafé. Todos los derechos reservados.</p>
  </footer>

  <script>
    if (location.hash === '#carrito') mostrarCarrito();
  </script>
</body>
</html>
