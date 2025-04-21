<!DOCTYPE html>
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
  <section id="inicio" class="p-8 bg-gray-100">
    <h2 class="text-3xl font-bold mb-4">Bienvenidos a Comerciacafé</h2>
    <p class="mb-4">Café premium colombiano en diferentes presentaciones. Compra al por mayor desde 150 libras.</p>
    <img src="https://images.unsplash.com/photo-1511920170033-f8396924c348" alt="Cafe" class="w-full max-h-96 object-cover rounded-lg">
  </section>

  <!-- Productos -->
  <section id="productos" class="p-8">
    <h2 class="text-2xl font-semibold mb-6">Nuestros productos</h2>
    <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
      <div class="border p-4 rounded shadow">
        <h3 class="font-bold text-lg">Café Tostado y Molido</h3>
        <p>Presentaciones de 1 libra ($5) y 1 kilo ($9).</p>
        <button onclick="agregarCarrito('Café Tostado y Molido - 1 libra', 5)" class="bg-[#5C4033] text-white px-4 py-2 mt-2 rounded">Agregar ($5 USD)</button>
        <button onclick="agregarCarrito('Café Tostado y Molido - 1 kilo', 9)" class="bg-[#5C4033] text-white px-4 py-2 mt-2 rounded">Agregar ($9 USD)</button>
      </div>
      <div class="border p-4 rounded shadow">
        <h3 class="font-bold text-lg">Café en Grano</h3>
        <p>Presentaciones de 1 libra ($6), 1 kilo ($10), bulto de 40 kg ($250).</p>
        <button onclick="agregarCarrito('Café en Grano - 1 libra', 6)" class="bg-[#5C4033] text-white px-4 py-2 mt-2 rounded">Agregar ($6 USD)</button>
        <button onclick="agregarCarrito('Café en Grano - 1 kilo', 10)" class="bg-[#5C4033] text-white px-4 py-2 mt-2 rounded">Agregar ($10 USD)</button>
        <button onclick="agregarCarrito('Café en Grano - Bulto 40kg', 250)" class="bg-[#5C4033] text-white px-4 py-2 mt-2 rounded">Agregar ($250 USD)</button>
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
    <ul id="carrito-lista" class="mb-4 list-disc pl-5"></ul>
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
        li.textContent = `${item.producto} - $${item.precioUSD.toFixed(2)} USD`;
        lista.appendChild(li);
      });
      document.getElementById('total-usd').textContent = `Total: $${totalUSD.toFixed(2)} USD`;
      // Consultar tasas de cambio
      try {
        const res = await axios.get('https://api.exchangerate-api.com/v4/latest/USD');
        const cop = totalUSD * res.data.rates.COP;
        const eur = totalUSD * res.data.rates.EUR;
        document.getElementById('total-cop').textContent = `COP: $${cop.toLocaleString('es-CO', { minimumFractionDigits: 0 })}`;
        document.getElementById('total-eur').textContent = `EUR: €${eur.toFixed(2)}`;
      } catch (error) {
        console.error('Error al obtener tasas de cambio', error);
      }
    }
  </script>
</body>
</html>
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
  <section id="inicio" class="p-8 bg-gray-100">
    <h2 class="text-3xl font-bold mb-4">Bienvenidos a Comerciacafé</h2>
    <p class="mb-4">Café premium colombiano en diferentes presentaciones. Compra al por mayor desde 150 libras.</p>
    <img src="https://images.unsplash.com/photo-1511920170033-f8396924c348" alt="Cafe" class="w-full max-h-96 object-cover rounded-lg">
  </section>

  <!-- Productos -->
  <section id="productos" class="p-8">
    <h2 class="text-2xl font-semibold mb-6">Nuestros productos</h2>
    <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
      <div class="border p-4 rounded shadow">
        <h3 class="font-bold text-lg">Café Tostado y Molido</h3>
        <p>Presentaciones de 1 libra ($5) y 1 kilo ($9).</p>
        <button onclick="agregarCarrito('Café Tostado y Molido - 1 libra', 5)" class="bg-[#5C4033] text-white px-4 py-2 mt-2 rounded">Agregar ($5 USD)</button>
        <button onclick="agregarCarrito('Café Tostado y Molido - 1 kilo', 9)" class="bg-[#5C4033] text-white px-4 py-2 mt-2 rounded">Agregar ($9 USD)</button>
      </div>
      <div class="border p-4 rounded shadow">
        <h3 class="font-bold text-lg">Café en Grano</h3>
        <p>Presentaciones de 1 libra ($6), 1 kilo ($10), bulto de 40 kg ($250).</p>
        <button onclick="agregarCarrito('Café en Grano - 1 libra', 6)" class="bg-[#5C4033] text-white px-4 py-2 mt-2 rounded">Agregar ($6 USD)</button>
        <button onclick="agregarCarrito('Café en Grano - 1 kilo', 10)" class="bg-[#5C4033] text-white px-4 py-2 mt-2 rounded">Agregar ($10 USD)</button>
        <button onclick="agregarCarrito('Café en Grano - Bulto 40kg', 250)" class="bg-[#5C4033] text-white px-4 py-2 mt-2 rounded">Agregar ($250 USD)</button>
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
    <ul id="carrito-lista" class="mb-4 list-disc pl-5"></ul>
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
        li.textContent = `${item.producto} - $${item.precioUSD.toFixed(2)} USD`;
        lista.appendChild(li);
      });
      document.getElementById('total-usd').textContent = `Total: $${totalUSD.toFixed(2)} USD`;
      // Consultar tasas de cambio
      try {
        const res = await axios.get('https://api.exchangerate-api.com/v4/latest/USD');
        const cop = totalUSD * res.data.rates.COP;
        const eur = totalUSD * res.data.rates.EUR;
        document.getElementById('total-cop').textContent = `COP: $${cop.toLocaleString('es-CO', { minimumFractionDigits: 0 })}`;
        document.getElementById('total-eur').textContent = `EUR: €${eur.toFixed(2)}`;
      } catch (error) {
        console.error('Error al obtener tasas de cambio', error);
      }
    }
  </script>
</body>
</html>
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

<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Inicio - Comerciacafé</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-white text-gray-800">
  <header class="bg-[#5C4033] p-6 text-white">
    <h1 class="text-3xl font-bold">Comerciacafé</h1>
  </header>

  <main class="p-8">
    <h2 class="text-2xl font-bold mb-4">Café Colombiano Premium</h2>
    <p class="mb-4">Ofrecemos café tostado y molido, así como café en grano en presentaciones de libra, kilo y bultos de 40 kilos. Contamos con precios especiales para compras al por mayor a partir de 150 libras.</p>
    <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
      <img src="https://images.unsplash.com/photo-1509042239860-f550ce710b93" alt="Presentación de café" class="rounded-lg shadow">
      <img src="https://images.unsplash.com/photo-1504639725590-34d0984388bd" alt="Café en grano" class="rounded-lg shadow">
      <img src="https://images.unsplash.com/photo-1536520002442-39764a41e7c1" alt="Empaque de café" class="rounded-lg shadow">
    </div>
  </main>

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
  <script>
    function agregarAlCarrito(nombre, precioCOP) {
      const carrito = JSON.parse(localStorage.getItem('carrito')) || [];
      carrito.push({ nombre, precioCOP });
      localStorage.setItem('carrito', JSON.stringify(carrito));
      alert(`Has agregado "${nombre}" al carrito.`);
    }
  </script>
</head>
<body class="bg-white text-gray-800">
  <header class="bg-[#5C4033] p-6 text-white">
    <h1 class="text-3xl font-bold">Nuestros Productos</h1>
  </header>

  <main class="p-8">
    <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
      <!-- Producto 1 -->
      <div class="border rounded-lg p-4 shadow">
        <h3 class="text-xl font-bold">Café Tostado y Molido - 1 libra</h3>
        <p class="mb-2">Precio: $25.000 COP</p>
        <button onclick="agregarAlCarrito('Café Tostado y Molido - 1 libra', 25000)" class="bg-[#5C4033] text-white px-4 py-2 rounded">Agregar al carrito</button>
      </div>

      <!-- Producto 2 -->
      <div class="border rounded-lg p-4 shadow">
        <h3 class="text-xl font-bold">Café en Grano - 1 kilo</h3>
        <p class="mb-2">Precio: $48.000 COP</p>
        <button onclick="agregarAlCarrito('Café en Grano - 1 kilo', 48000)" class="bg-[#5C4033] text-white px-4 py-2 rounded">Agregar al carrito</button>
      </div>

      <!-- Producto 3 -->
      <div class="border rounded-lg p-4 shadow">
        <h3 class="text-xl font-bold">Bulto de Café en Grano - 40 kilos</h3>
        <p class="mb-2">Precio: $1.600.000 COP</p>
        <button onclick="agregarAlCarrito('Bulto de Café en Grano - 40 kilos', 1600000)" class="bg-[#5C4033] text-white px-4 py-2 rounded">Agregar al carrito</button>
      </div>
    </div>
  </main>

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
  <header class="bg-[#5C4033] p-6 text-white">
    <h1 class="text-3xl font-bold">Sobre Nosotros</h1>
  </header>

  <main class="p-8 max-w-3xl mx-auto text-justify">
    <p class="mb-4">Hace 30 años, en una pequeña finca cafetera ubicada en las montañas de Colombia, nació Comerciacafé. Lo que empezó como un sueño familiar con apenas unas hectáreas de cultivo, hoy es una empresa con proyección internacional, dedicada a ofrecer café de alta calidad a clientes exigentes que valoran el sabor, la historia y el compromiso con el medio ambiente.</p>

    <p class="mb-4">A lo largo de estas tres décadas, hemos perfeccionado nuestras técnicas de cultivo, tostado y selección de granos, posicionándonos como una marca reconocida por su autenticidad y responsabilidad social. Queremos seguir creciendo y llevar nuestro café colombiano a cada rincón del mundo.</p>

    <p>¡Gracias por ser parte de nuestra historia!</p>
  </main>

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
  <header class="bg-[#5C4033] p-6 text-white">
    <h1 class="text-3xl font-bold">Contacto</h1>
  </header>

  <main class="p-8 max-w-2xl mx-auto">
    <p class="mb-6">¿Tienes preguntas o deseas obtener más información sobre nuestros productos o ventas al por mayor? Contáctanos:</p>

    <div class="bg-gray-100 p-6 rounded-lg shadow">
      <p class="mb-2 font-semibold">Teléfono:</p>
      <p class="mb-4">📞 316 397 7891</p>

      <p class="mb-2 font-semibold">Correo electrónico:</p>
      <p class="mb-4">📧 info@comerciacafe.com</p>

      <p class="mb-2 font-semibold">Dirección:</p>
      <p>Calle 123 #45-67, Manizales, Caldas, Colombia</p>
    </div>
  </main>

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
  <title>Carrito - Comerciacafé</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <script>
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

    window.onload = mostrarCarrito;
  </script>
</head>
<body class="bg-white text-gray-800">
  <header class="bg-[#5C4033] p-6 text-white">
    <h1 class="text-3xl font-bold">Tu Carrito</h1>
  </header>

  <main class="p-8 max-w-4xl mx-auto">
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
  </main>

  <footer class="bg-gray-100 text-center p-4 mt-8">
    <p>&copy; 2025 Comerciacafé. Todos los derechos reservados.</p>
  </footer>
</body>
</html>
