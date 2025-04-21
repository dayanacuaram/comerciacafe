<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Comerciacafé - Tu tienda de café colombiano</title>
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
      <a href="#metodos" class="hover:underline">Métodos de Envío</a>
      <a href="#garantias" class="hover:underline">Garantías</a>
      <a href="#contacto" class="hover:underline">Contacto</a>
      <a href="#carrito" class="hover:underline">Carrito</a>
      <select id="language" class="bg-[#5C4033] text-white p-2 rounded hover:bg-[#4b3321]">
        <option value="es">ES</option>
        <option value="en">EN</option>
      </select>
    </nav>
  </header>

  <!-- INICIO -->
  <section id="inicio" class="bg-cover bg-center h-[60vh] flex items-center justify-center text-center text-white" style="background-image: url('https://images.unsplash.com/photo-1509042239860-f550ce710b93?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80');">
    <div class="bg-black bg-opacity-50 p-6 rounded-lg">
      <h2 class="text-4xl font-bold mb-4">Bienvenido a Comerciacafé</h2>
      <p class="text-xl">El sabor auténtico del café colombiano, directo de las montañas a tu taza.</p>
    </div>
  </section>

  <!-- PRODUCTOS -->
  <section id="productos" class="p-10">
    <h2 class="text-3xl font-bold text-center mb-8">Nuestros Productos</h2>
    <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
      <!-- Producto 1 -->
      <div class="bg-white shadow-md rounded-lg p-4 text-center">
        <img src="https://images.unsplash.com/photo-1592842044709-5643a9f71f8e?auto=format&fit=crop&w=800&q=80" alt="Café Tostado" class="w-full h-40 object-cover rounded mb-4">
        <h3 class="text-xl font-semibold">Café Tostado y Molido</h3>
        <p class="text-gray-600 mt-2">Tueste medio perfecto para cafetera o prensa francesa.</p>
        <p class="text-lg font-bold mt-2">$15.000 COP</p>
        <button onclick="addToCart('Café Tostado y Molido', 15000)" class="mt-3 bg-[#5C4033] text-white px-4 py-2 rounded hover:bg-[#4b3321]">Añadir al carrito</button>
        <div class="mt-4 text-left text-sm">
          <p><strong>Especificaciones:</strong></p>
          <ul>
            <li>Origen: Eje cafetero, Colombia</li>
            <li>Proceso: Tostado medio</li>
            <li>Ideal para: Cafetera y prensa francesa</li>
            <li>Empaque: Bolsa sellada al vacío de 250g</li>
            <li><strong>Almacenamiento:</strong> Mantener en lugar fresco y seco, alejado de la luz solar directa.</li>
            <li><strong>Duración:</strong> Consumir preferentemente antes de 6 meses desde la fecha de tostado.</li>
          </ul>
        </div>
      </div>
      <!-- Producto 2 -->
      <div class="bg-white shadow-md rounded-lg p-4 text-center">
        <img src="https://images.unsplash.com/photo-1612197619350-196d1df9b44e?auto=format&fit=crop&w=800&q=80" alt="Café en Grano" class="w-full h-40 object-cover rounded mb-4">
        <h3 class="text-xl font-semibold">Café en Grano</h3>
        <p class="text-gray-600 mt-2">Granos frescos, seleccionados y empacados al vacío.</p>
        <p class="text-lg font-bold mt-2">$20.000 COP</p>
        <button onclick="addToCart('Café en Grano', 20000)" class="mt-3 bg-[#5C4033] text-white px-4 py-2 rounded hover:bg-[#4b3321]">Añadir al carrito</button>
        <div class="mt-4 text-left text-sm">
          <p><strong>Especificaciones:</strong></p>
          <ul>
            <li>Origen: Huila, Colombia</li>
            <li>Proceso: Grano natural</li>
            <li>Ideal para: Moler según tu gusto</li>
            <li>Empaque: Bolsa sellada al vacío de 250g</li>
            <li><strong>Almacenamiento:</strong> Conservar en envase hermético para asegurar frescura.</li>
            <li><strong>Duración:</strong> 12 meses si se mantiene sellado y en condiciones ideales.</li>
          </ul>
        </div>
      </div>
      <!-- Producto 3 -->
      <div class="bg-white shadow-md rounded-lg p-4 text-center">
        <img src="https://images.unsplash.com/photo-1601758123927-196dbde0e57e?auto=format&fit=crop&w=800&q=80" alt="Café al por Mayor" class="w-full h-40 object-cover rounded mb-4">
        <h3 class="text-xl font-semibold">Café al por Mayor</h3>
        <p class="text-gray-600 mt-2">Ideal para cafeterías, restaurantes y distribuidores.</p>
        <p class="text-lg font-bold mt-2">$500.000 COP</p>
        <button onclick="addToCart('Café al por Mayor', 500000)" class="mt-3 bg-[#5C4033] text-white px-4 py-2 rounded hover:bg-[#4b3321]">Añadir al carrito</button>
        <div class="mt-4 text-left text-sm">
          <p><strong>Especificaciones:</strong></p>
          <ul>
            <li>Origen: Eje cafetero y Huila</li>
            <li>Proceso: Mezcla de granos de alta calidad</li>
            <li>Ideal para: Cafeterías, restaurantes</li>
            <li>Empaque: Bolsa de 5kg</li>
            <li><strong>Almacenamiento:</strong> Conservar en lugar fresco, seco y en envase hermético.</li>
            <li><strong>Duración:</strong> 18 meses desde la fecha de envasado.</li>
          </ul>
        </div>
      </div>
    </div>
  </section>

  <!-- NOSOTROS -->
  <section id="nosotros" class="bg-gray-100 p-10 text-center">
    <h2 class="text-3xl font-bold mb-4">Nuestra Historia</h2>
    <p class="max-w-3xl mx-auto text-lg text-gray-700">
      En **Comerciacafé**, nuestro amor por el café colombiano nació en el corazón del Eje Cafetero, una de las regiones más emblemáticas del país. Desde nuestros inicios, hemos trabajado con pasión y dedicación para ofrecerte lo mejor de la tradición cafetera de Colombia, respetando las técnicas de cultivo y procesamiento que se han transmitido de generación en generación. Seleccionamos solo los mejores granos para que disfrutes una experiencia única en cada taza.
    </p>
  </section>

  <!-- MÉTODOS DE ENVÍO -->
  <section id="metodos" class="p-10">
    <h2 class="text-3xl font-bold text-center mb-6">Métodos de Envío</h2>
    <p class="text-lg text-gray-700 mb-4">Ofrecemos diferentes opciones de envío para que recibas tu café en el tiempo y forma que más te convenga.</p>
    <ul class="space-y-4">
      <li>📦 **Envío Estándar**: 3-5 días hábiles. Costo: $10.000 COP. Envío gratuito en compras superiores a $50.000 COP.</li>
      <li>🚚 **Envío Exprés**: 1-2 días hábiles. Costo: $20.000 COP.</li>
      <li>🌍 **Envíos Internacionales**: Costo y tiempo de entrega varían según el destino. Consulta precios y tiempos de envío para tu país.</li>
    </ul>
  </section>

  <!-- GARANTÍAS -->
  <section id="garantias" class="bg-gray-100 p-10">
    <h2 class="text-3xl font-bold text-center mb-6">Garantías</h2>
    <p class="text-lg text-gray-700 mb-4">En **Comerciacafé** garantizamos la calidad de nuestros productos. Si no estás completamente satisfecho con tu compra, puedes devolverla dentro de los 30 días posteriores a la recepción para un reembolso completo. Aseguramos que nuestros productos son frescos y de la mejor calidad.</p>
    <p>En el caso de problemas con el envío o el producto, ofrecemos soporte y solución inmediata. Tu satisfacción es nuestra prioridad.</p>
  </section>

  <!-- CONTACTO -->
  <section id="contacto" class="p-10 text-center">
    <h2 class="text-3xl font-bold mb-4">Contáctanos</h2>
    <p class="text-lg">¿Tienes dudas o quieres hacer un pedido personalizado?</p>
    <p class="mt-2">📞 <strong>316 397 7891</strong> | 📧 <strong>contacto@comerciacafe.com</strong></p>
    <p>Nos encanta saber de ti, así que no dudes en escribirnos para cualquier consulta.</p>
  </section>

  <!-- CARRITO -->
  <section id="carrito" class="bg-gray-100 p-10 text-center">
    <h2 class="text-3xl font-bold mb-6">Carrito de Compras</h2>
    <div id="cart-items" class="text-left max-w-xl mx-auto bg-white shadow-md rounded p-4">
      <p>Aún no has añadido productos al carrito.</p>
    </div>
    <div class="mt-4">
      <p class="mb-2">Selecciona tu moneda preferida:</p>
      <select id="currency" class="px-3 py-2 rounded border">
        <option value="COP">COP (Pesos Colombianos)</option>
        <option value="USD">USD (Dólares)</option>
        <option value="EUR">EUR (Euros)</option>
      </select>
    </div>
    <!-- Botón de Pago -->
    <div class="mt-8">
      <button class="bg-green-500 text-white px-6 py-3 rounded-full text-lg">Pagar Ahora</button>
    </div>
  </section>

  <script>
    let cart = [];
    const exchangeRates = {
      COP: 1,
      USD: 0.25,
      EUR: 0.23
    };

    function addToCart(productName, productPrice) {
      cart.push({ name: productName, price: productPrice });
      updateCart();
    }

    function updateCart() {
      const cartItems = document.getElementById('cart-items');
      cartItems.innerHTML = '';

      if (cart.length === 0) {
        cartItems.innerHTML = '<p>Aún no has añadido productos al carrito.</p>';
      } else {
        cart.forEach(item => {
          cartItems.innerHTML += `<p>${item.name} - $${item.price}</p>`;
        });
      }
    }
  </script>
  
</body>
</html>
