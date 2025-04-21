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
      <a href="#contacto" class="hover:underline">Contacto</a>
      <a href="#carrito" class="hover:underline">Carrito</a>
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
      <div class="bg-white shadow-md rounded-lg p-4 text-center">
        <img src="https://images.unsplash.com/photo-1592842044709-5643a9f71f8e?auto=format&fit=crop&w=800&q=80" alt="Café Tostado" class="w-full h-40 object-cover rounded mb-4">
        <h3 class="text-xl font-semibold">Café Tostado y Molido</h3>
        <p class="text-gray-600 mt-2">Tueste medio perfecto para cafetera o prensa francesa.</p>
        <p class="text-lg font-bold mt-2">$15.000 COP</p>
        <button onclick="addToCart('Café Tostado y Molido', 15000)" class="mt-3 bg-[#5C4033] text-white px-4 py-2 rounded hover:bg-[#4b3321]">Añadir al carrito</button>
      </div>
      <div class="bg-white shadow-md rounded-lg p-4 text-center">
        <img src="https://images.unsplash.com/photo-1612197619350-196d1df9b44e?auto=format&fit=crop&w=800&q=80" alt="Café en Grano" class="w-full h-40 object-cover rounded mb-4">
        <h3 class="text-xl font-semibold">Café en Grano</h3>
        <p class="text-gray-600 mt-2">Granos frescos, seleccionados y empacados al vacío.</p>
        <p class="text-lg font-bold mt-2">$20.000 COP</p>
        <button onclick="addToCart('Café en Grano', 20000)" class="mt-3 bg-[#5C4033] text-white px-4 py-2 rounded hover:bg-[#4b3321]">Añadir al carrito</button>
      </div>
      <div class="bg-white shadow-md rounded-lg p-4 text-center">
        <img src="https://images.unsplash.com/photo-1601758123927-196dbde0e57e?auto=format&fit=crop&w=800&q=80" alt="Café al por Mayor" class="w-full h-40 object-cover rounded mb-4">
        <h3 class="text-xl font-semibold">Café al por Mayor</h3>
        <p class="text-gray-600 mt-2">Ideal para cafeterías, restaurantes y distribuidores.</p>
        <p class="text-lg font-bold mt-2">$500.000 COP</p>
        <button onclick="addToCart('Café al por Mayor', 500000)" class="mt-3 bg-[#5C4033] text-white px-4 py-2 rounded hover:bg-[#4b3321]">Añadir al carrito</button>
      </div>
    </div>
  </section>

  <!-- NOSOTROS -->
  <section id="nosotros" class="bg-gray-100 p-10 text-center">
    <h2 class="text-3xl font-bold mb-4">Nuestra Historia</h2>
    <p class="max-w-3xl mx-auto text-lg text-gray-700">
      En **Comerciacafé**, nuestro amor por el café colombiano nació en el corazón del Eje Cafetero, una de las regiones más emblemáticas del país. Desde nuestros inicios, hemos trabajado con pasión y dedicación para ofrecerte lo mejor de la tradición cafetera de Colombia, respetando las técnicas de cultivo y procesamiento que se han transmitido de generación en generación.
    </p>
    <p class="max-w-3xl mx-auto text-lg text-gray-700 mt-4">
      **Comerciacafé** es una empresa familiar, comprometida con la calidad, la sostenibilidad y el comercio justo. Trabajamos directamente con pequeños productores de café en las montañas de Colombia, garantizando que cada grano que llega a tu taza sea el resultado de un proceso meticuloso y cuidadoso. Nos enorgullece ser parte de una cadena productiva que beneficia tanto a nuestros agricultores como a nuestros clientes, brindándoles un café fresco y de calidad superior.
    </p>
    <p class="max-w-3xl mx-auto text-lg text-gray-700 mt-4">
      Nuestro café es más que solo una bebida; es una experiencia que conecta a las personas con la esencia misma de Colombia. Desde el proceso de recolección manual de los granos hasta su tostado y empaque, nos aseguramos de preservar los sabores únicos de cada región cafetera, ofreciendo una variedad de productos que van desde el café tostado y molido hasta el café en grano y presentaciones al por mayor para empresas.
    </p>
    <p class="max-w-3xl mx-auto text-lg text-gray-700 mt-4">
      Pero más allá de la calidad de nuestro café, en **Comerciacafé** también estamos comprometidos con la sostenibilidad. Trabajamos para minimizar nuestro impacto ambiental, utilizando prácticas responsables en todo el proceso de producción y distribución. Queremos que, al disfrutar de una taza de nuestro café, también estés apoyando un futuro más verde y justo para las comunidades cafetaleras de Colombia.
    </p>
    <p class="max-w-3xl mx-auto text-lg text-gray-700 mt-4">
      Hoy, nos enorgullece llevar la magia del café colombiano a más hogares alrededor del mundo, ofreciendo productos frescos, auténticos y con el sabor único que solo el café de Colombia puede ofrecer. En **Comerciacafé**, cada taza de café cuenta una historia, y nos sentimos honrados de ser parte de la tuya.
    </p>
  </section>

  <!-- CONTACTO -->
  <section id="contacto" class="p-10 text-center">
    <h2 class="text-3xl font-bold mb-4">Contáctanos</h2>
    <p class="text-lg">¿Tienes dudas o quieres hacer un pedido personalizado?</p>
    <p class="mt-2">📞 <strong>316 397 7891</strong> | 📧 <strong>contacto@comerciacafe.com</strong></p>
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
      const cartContainer = document.getElementById("cart-items");
      const currency = document.getElementById("currency").value;
      let totalPrice = 0;
      cartContainer.innerHTML = cart.map(item => {
        totalPrice += item.price * exchangeRates[currency];
        return `
          <p>${item.name} - ${formatCurrency(item.price, currency)}</p>
        `;
      }).join('');
      cartContainer.innerHTML += `<hr><p class="font-bold">Total: ${formatCurrency(totalPrice, currency)}</p>`;
    }

    function formatCurrency(amount, currency) {
      switch (currency) {
        case "USD":
          return `$${(amount * exchangeRates.USD).toFixed(2)}`;
        case "EUR":
          return `€${(amount * exchangeRates.EUR).toFixed(2)}`;
        default:
          return `${amount} COP`;
      }
    }

    document.getElementById("currency").addEventListener("change", updateCart);
  </script>

</body>
</html>
