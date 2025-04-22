<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Comerciacafé - Tienda de Café Colombiano</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-50 text-gray-800 font-sans">

  <!-- NAVBAR -->
  <header class="bg-[#5C4033] p-4 text-white flex justify-between items-center shadow-md">
    <h1 class="text-2xl font-bold">Comerciacafé</h1>
    <nav class="space-x-4 text-sm md:text-base">
      <a href="#inicio" class="hover:underline">Inicio</a>
      <a href="#productos" class="hover:underline">Productos</a>
      <a href="#informacion" class="hover:underline">Información</a>
      <a href="#carrito" class="hover:underline">Carrito</a>
    </nav>
  </header>

  <!-- INICIO -->
  <section id="inicio" class="bg-cover bg-center h-[60vh] flex items-center justify-center text-center text-white" style="background-image: url('https://images.unsplash.com/photo-1509042239860-f550ce710b93?auto=format&fit=crop&w=1470&q=80');">
    <div class="bg-black bg-opacity-50 p-6 rounded-lg">
      <h2 class="text-4xl font-bold mb-4">Bienvenido a Comerciacafé</h2>
      <p class="text-xl">Auténtico café colombiano directo del productor a tu taza.</p>
    </div>
  </section>

  <!-- PRODUCTOS -->
  <section id="productos" class="p-10">
    <h2 class="text-3xl font-bold text-center mb-8">Nuestros Productos</h2>
    <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
      <div class="bg-white shadow-md rounded-lg p-4 text-center">
        <img src="https://images.unsplash.com/photo-1592842044709-5643a9f71f8e?auto=format&fit=crop&w=800&q=80" alt="Café Molido" class="w-full h-40 object-cover rounded mb-4">
        <h3 class="text-xl font-semibold">Café Molido</h3>
        <p class="text-gray-600 mt-2">Empaque de 500g con tueste medio.</p>
        <p class="text-lg font-bold mt-2">$15.000 COP</p>
        <button onclick="addToCart('Café Molido', 15000)" class="mt-3 bg-[#5C4033] text-white px-4 py-2 rounded hover:bg-[#4b3321]">Añadir al carrito</button>
      </div>
      <div class="bg-white shadow-md rounded-lg p-4 text-center">
        <img src="https://images.unsplash.com/photo-1612197619350-196d1df9b44e?auto=format&fit=crop&w=800&q=80" alt="Café en Grano" class="w-full h-40 object-cover rounded mb-4">
        <h3 class="text-xl font-semibold">Café en Grano</h3>
        <p class="text-gray-600 mt-2">1kg de café premium recién tostado.</p>
        <p class="text-lg font-bold mt-2">$20.000 COP</p>
        <button onclick="addToCart('Café en Grano', 20000)" class="mt-3 bg-[#5C4033] text-white px-4 py-2 rounded hover:bg-[#4b3321]">Añadir al carrito</button>
      </div>
      <div class="bg-white shadow-md rounded-lg p-4 text-center">
        <img src="https://images.unsplash.com/photo-1601758123927-196dbde0e57e?auto=format&fit=crop&w=800&q=80" alt="Café por Mayor" class="w-full h-40 object-cover rounded mb-4">
        <h3 class="text-xl font-semibold">Café al por Mayor</h3>
        <p class="text-gray-600 mt-2">Bultos de 40kg para distribuidores y cafeterías.</p>
        <p class="text-lg font-bold mt-2">$500.000 COP</p>
        <button onclick="addToCart('Café al por Mayor', 500000)" class="mt-3 bg-[#5C4033] text-white px-4 py-2 rounded hover:bg-[#4b3321]">Añadir al carrito</button>
      </div>
    </div>
  </section>

  <!-- INFORMACIÓN DETALLADA -->
  <section id="informacion" class="bg-gray-100 p-10">
    <h2 class="text-3xl font-bold text-center mb-6">Información Importante</h2>

    <div class="max-w-4xl mx-auto text-gray-700 space-y-6">
      <div>
        <h3 class="text-xl font-semibold">Sobre Nosotros</h3>
        <p>
          Comerciacafé es una empresa colombiana dedicada a la producción, tostión y comercialización de café 100% arábico cultivado en las montañas del Eje Cafetero. Nuestra misión es ofrecer una experiencia sensorial única mediante prácticas sostenibles, procesos artesanales y un profundo respeto por nuestras raíces cafeteras.
        </p>
      </div>
      <div>
        <h3 class="text-xl font-semibold">Calidad Garantizada</h3>
        <p>
          Cada grano pasa por un riguroso proceso de selección manual, secado natural y tueste controlado para garantizar un sabor auténtico y constante. Nuestros productos cuentan con certificados de calidad y origen.
        </p>
      </div>
      <div>
        <h3 class="text-xl font-semibold">Garantía y Devoluciones</h3>
        <p>
          Ofrecemos garantía de satisfacción. Si el producto no cumple tus expectativas, puedes solicitar devolución o cambio en un plazo de 7 días hábiles después de la entrega.
        </p>
      </div>
      <div>
        <h3 class="text-xl font-semibold">Transporte y Entregas</h3>
        <p>
          Enviamos a todo el territorio nacional mediante transportadoras certificadas. Entregas en 3 a 5 días hábiles. Para pedidos internacionales, contáctanos directamente.
        </p>
      </div>
      <div>
        <h3 class="text-xl font-semibold">Especificaciones del Producto</h3>
        <ul class="list-disc pl-5">
          <li>Origen: Caldas, Colombia</li>
          <li>Altura: 1.600 - 2.000 msnm</li>
          <li>Variedad: Arábica Castillo</li>
          <li>Notas: Chocolate, nuez y caramelo</li>
          <li>Presentaciones: 500g, 1kg, bultos de 40kg</li>
        </ul>
      </div>
    </div>
  </section>

  <!-- CARRITO DE COMPRAS -->
  <section id="carrito" class="p-10 bg-white">
    <h2 class="text-3xl font-bold text-center mb-6">Carrito de Compras</h2>
    <div class="max-w-2xl mx-auto">
      <div id="cart-items" class="bg-gray-100 p-4 rounded shadow-md">
        <p class="text-center">Aún no has añadido productos al carrito.</p>
      </div>
      <div class="mt-4 text-center">
        <label class="block mb-2">Selecciona tu moneda:</label>
        <select id="currency" class="px-4 py-2 rounded border">
          <option value="COP">COP (Pesos Colombianos)</option>
          <option value="USD">USD (Dólares)</option>
          <option value="EUR">EUR (Euros)</option>
        </select>
      </div>
      <div class="text-center mt-6">
        <button class="bg-green-600 text-white px-6 py-2 rounded hover:bg-green-700 cursor-pointer">Pagar</button>
      </div>
    </div>
  </section>

  <!-- FOOTER -->
  <footer class="bg-[#5C4033] text-white text-center p-4 mt-10">
    &copy; 2025 Comerciacafé. Todos los derechos reservados.
  </footer>

  <!-- SCRIPT DEL CARRITO -->
  <script>
    let cart = [];
    const exchangeRates = { USD: 0.00026, EUR: 0.00024, COP: 1 };

    function addToCart(productName, price) {
      cart.push({ productName, price });
      updateCart();
    }

    function updateCart() {
      const container = document.getElementById('cart-items');
      const currency = document.getElementById('currency').value;
      const rate = exchangeRates[currency];
      container.innerHTML = '';

      if (cart.length === 0) {
        container.innerHTML = '<p class="text-center">Aún no has añadido productos al carrito.</p>';
        return;
      }

      let total = 0;
      cart.forEach(item => {
        const convertedPrice = item.price * rate;
        total += convertedPrice;
        const row = document.createElement('div');
        row.classList.add('flex', 'justify-between', 'border-b', 'py-2');
        row.innerHTML = `<span>${item.productName}</span><span>${convertedPrice.toFixed(2)} ${currency}</span>`;
        container.appendChild(row);
      });

      const totalRow = document.createElement('div');
      totalRow.classList.add('mt-4', 'font-bold', 'text-right');
      totalRow.textContent = `Total: ${total.toFixed(2)} ${currency}`;
      container.appendChild(totalRow);
    }

    document.getElementById('currency').addEventListener('change', updateCart);
  </script>

</body>
</html>
