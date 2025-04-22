<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Comerciacafé</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-50 text-gray-800 font-sans">

  <!-- Navbar -->
  <header class="bg-[#5C4033] p-4 text-white flex justify-between items-center shadow-md">
    <h1 class="text-2xl font-bold">Comerciacafé</h1>
    <nav class="space-x-4">
      <a href="#inicio" class="hover:underline">Inicio</a>
      <a href="#productos" class="hover:underline">Productos</a>
      <a href="#nosotros" class="hover:underline">Nosotros</a>
      <a href="#info" class="hover:underline">Información</a>
      <a href="#carrito" class="hover:underline">Carrito</a>
    </nav>
  </header>

  <!-- Inicio -->
  <section id="inicio" class="bg-cover bg-center h-[60vh] flex items-center justify-center text-white text-center" style="background-image: url('https://images.unsplash.com/photo-1509042239860-f550ce710b93');">
    <div class="bg-black bg-opacity-60 p-6 rounded">
      <h2 class="text-4xl font-bold mb-4">Bienvenido a Comerciacafé</h2>
      <p class="text-xl">Café colombiano auténtico directo de nuestras fincas a tu taza.</p>
    </div>
  </section>

  <!-- Productos -->
  <section id="productos" class="p-10">
    <h2 class="text-3xl font-bold text-center mb-8">Nuestros Productos</h2>
    <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
      <div class="bg-white shadow-md rounded-lg p-4 text-center">
        <img src="https://images.unsplash.com/photo-1592842044709-5643a9f71f8e?auto=format&fit=crop&w=800&q=80" alt="Café Tostado" class="w-full h-40 object-cover rounded mb-4">
        <h3 class="text-xl font-semibold">Café Tostado y Molido</h3>
        <p class="text-gray-600 mt-2">Tueste medio, ideal para cafetera o prensa.</p>
        <p class="text-lg font-bold mt-2">$15.000 COP</p>
        <button onclick="addToCart('Café Tostado y Molido', 15000)" class="mt-3 bg-[#5C4033] text-white px-4 py-2 rounded">Añadir</button>
      </div>
      <div class="bg-white shadow-md rounded-lg p-4 text-center">
        <img src="https://images.unsplash.com/photo-1612197619350-196d1df9b44e?auto=format&fit=crop&w=800&q=80" alt="Café en Grano" class="w-full h-40 object-cover rounded mb-4">
        <h3 class="text-xl font-semibold">Café en Grano</h3>
        <p class="text-gray-600 mt-2">Fresco y empacado al vacío para conservar aroma.</p>
        <p class="text-lg font-bold mt-2">$20.000 COP</p>
        <button onclick="addToCart('Café en Grano', 20000)" class="mt-3 bg-[#5C4033] text-white px-4 py-2 rounded">Añadir</button>
      </div>
      <div class="bg-white shadow-md rounded-lg p-4 text-center">
        <img src="https://images.unsplash.com/photo-1601758123927-196dbde0e57e?auto=format&fit=crop&w=800&q=80" alt="Mayorista" class="w-full h-40 object-cover rounded mb-4">
        <h3 class="text-xl font-semibold">Café al por Mayor</h3>
        <p class="text-gray-600 mt-2">Ideal para cafeterías y distribuidores.</p>
        <p class="text-lg font-bold mt-2">$500.000 COP</p>
        <button onclick="addToCart('Café al por Mayor', 500000)" class="mt-3 bg-[#5C4033] text-white px-4 py-2 rounded">Añadir</button>
      </div>
    </div>
  </section>

  <!-- Nosotros -->
  <section id="nosotros" class="bg-gray-100 p-10 text-center">
    <h2 class="text-3xl font-bold mb-4">Sobre Nosotros</h2>
    <p class="max-w-4xl mx-auto text-lg text-gray-700">
      Comerciacafé nace en el corazón del Eje Cafetero colombiano, con la misión de llevar a cada hogar el auténtico sabor del café de altura. Con más de 30 años de experiencia, nuestras fincas cultivan granos seleccionados a mano y procesados con técnicas tradicionales que respetan el medio ambiente. Nos enorgullece ofrecer un café artesanal que respeta el origen, apoya a nuestros caficultores y deleita a nuestros clientes en cada sorbo.
    </p>
  </section>

  <!-- Información adicional -->
  <section id="info" class="p-10">
    <h2 class="text-3xl font-bold text-center mb-6">Información Importante</h2>
    <div class="max-w-5xl mx-auto space-y-6 text-gray-700">
      <div>
        <h3 class="text-2xl font-semibold">🚚 Métodos de Transporte</h3>
        <p>Enviamos a toda Colombia con transportadoras confiables como Servientrega y Coordinadora. Tiempos de entrega: entre 2 y 5 días hábiles.</p>
      </div>
      <div>
        <h3 class="text-2xl font-semibold">✅ Calidad Garantizada</h3>
        <p>Todos nuestros cafés son 100% arábicos, cultivados sin agroquímicos y sometidos a rigurosos controles de calidad. Cada lote se cata antes del envío.</p>
      </div>
      <div>
        <h3 class="text-2xl font-semibold">📦 Especificaciones del Producto</h3>
        <ul class="list-disc list-inside">
          <li>Origen: Quindío, Colombia</li>
          <li>Altura: 1.600 – 1.900 m.s.n.m</li>
          <li>Variedad: Caturra y Castillo</li>
          <li>Empaque: Bolsa hermética con válvula desgasificadora</li>
        </ul>
      </div>
      <div>
        <h3 class="text-2xl font-semibold">💬 Atención al Cliente</h3>
        <p>Escríbenos por WhatsApp al <strong>+57 316 397 7891</strong> o por correo a <strong>contacto@comerciacafe.com</strong>. Respondemos de lunes a sábado de 8 a.m. a 6 p.m.</p>
      </div>
      <div>
        <h3 class="text-2xl font-semibold">🔒 Garantía</h3>
        <p>Si tu pedido llega en mal estado, te enviamos uno nuevo sin costo adicional o te devolvemos tu dinero.</p>
      </div>
    </div>
  </section>

  <!-- Carrito -->
  <section id="carrito" class="bg-gray-100 p-10 text-center">
    <h2 class="text-3xl font-bold mb-6">🛒 Carrito de Compras</h2>
    <div class="max-w-2xl mx-auto bg-white p-4 rounded shadow-md text-left" id="cart-items">
      <p>No has añadido productos al carrito.</p>
    </div>

    <div class="mt-6">
      <label class="block mb-2 font-medium">Selecciona tu moneda:</label>
      <select id="currency" class="px-4 py-2 border rounded">
        <option value="COP">COP - Peso Colombiano</option>
        <option value="USD">USD - Dólar</option>
        <option value="EUR">EUR - Euro</option>
      </select>
    </div>

    <button class="mt-8 bg-green-600 hover:bg-green-700 text-white px-6 py-3 rounded text-lg">Pagar</button>
  </section>

  <!-- Footer -->
  <footer class="bg-[#5C4033] text-white text-center p-4 mt-10">
    &copy; 2025 Comerciacafé. Todos los derechos reservados.
  </footer>

  <!-- Script Carrito -->
  <script>
    let cart = [];
    const exchangeRates = { COP: 1, USD: 0.00026, EUR: 0.00024 };

    function addToCart(name, price) {
      cart.push({ name, price });
      updateCart();
    }

    function updateCart() {
      const container = document.getElementById('cart-items');
      const currency = document.getElementById('currency').value;
      const rate = exchangeRates[currency];
      container.innerHTML = '';

      if (cart.length === 0) {
        container.innerHTML = '<p>No has añadido productos al carrito.</p>';
        return;
      }

      let total = 0;
      cart.forEach(item => {
        const converted = item.price * rate;
        total += converted;
        const row = document.createElement('div');
        row.className = 'flex justify-between border-b py-2';
        row.innerHTML = `<span>${item.name}</span><span>${converted.toFixed(2)} ${currency}</span>`;
        container.appendChild(row);
      });

      const totalRow = document.createElement('div');
      totalRow.className = 'mt-4 font-bold text-right';
      totalRow.textContent = `Total: ${total.toFixed(2)} ${currency}`;
      container.appendChild(totalRow);
    }

    document.getElementById('currency').addEventListener('change', updateCart);
  </script>

</body>
</html>
