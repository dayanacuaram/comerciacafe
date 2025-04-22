<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Comerciacafé - Tu tienda de café colombiano</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <style>
    .section-content {
      display: none;
    }
    .section-content.show {
      display: block;
    }
  </style>
</head>
<body class="bg-gray-50 text-gray-800 font-sans">

  <!-- Navbar -->
  <header class="bg-[#5C4033] p-4 text-white flex justify-between items-center shadow-md">
    <h1 class="text-2xl font-bold" id="navbar-title">Comerciacafé</h1>
    <nav class="space-x-4">
      <a href="#inicio" id="nav-inicio" class="hover:underline">Inicio</a>
      <a href="#productos" id="nav-productos" class="hover:underline">Productos</a>
      <a href="#nosotros" id="nav-nosotros" class="hover:underline">Nosotros</a>
      <a href="#metodos" id="nav-metodos" class="hover:underline">Métodos de Envío</a>
      <a href="#garantias" id="nav-garantias" class="hover:underline">Garantías</a>
      <a href="#contacto" id="nav-contacto" class="hover:underline">Contacto</a>
      <a href="#carrito" id="nav-carrito" class="hover:underline">Carrito</a>
      <select id="language" class="bg-[#5C4033] text-white p-2 rounded hover:bg-[#4b3321]" onchange="changeLanguage()">
        <option value="es">ES</option>
        <option value="en">EN</option>
      </select>
    </nav>
  </header>

  <!-- INICIO -->
  <section id="inicio" class="bg-cover bg-center h-[60vh] flex items-center justify-center text-center text-white" style="background-image: url('https://images.unsplash.com/photo-1509042239860-f550ce710b93?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80');">
    <div class="bg-black bg-opacity-50 p-6 rounded-lg">
      <h2 class="text-4xl font-bold mb-4" id="inicio-title">Bienvenido a Comerciacafé</h2>
      <p class="text-xl" id="inicio-description">El sabor auténtico del café colombiano, directo de las montañas a tu taza.</p>
    </div>
  </section>

  <!-- PRODUCTOS -->
  <section id="productos" class="p-10">
    <h2 class="text-3xl font-bold text-center mb-8" id="productos-title">Nuestros Productos</h2>
    <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
      <!-- Producto 1 -->
      <div class="bg-white shadow-md rounded-lg p-4 text-center">
        <img src="https://images.unsplash.com/photo-1592842044709-5643a9f71f8e?auto=format&fit=crop&w=800&q=80" alt="Café Tostado" class="w-full h-40 object-cover rounded mb-4">
        <h3 class="text-xl font-semibold" id="producto1-title">Café Tostado y Molido</h3>
        <p class="text-gray-600 mt-2" id="producto1-description">Tueste medio perfecto para cafetera o prensa francesa.</p>
        <p class="text-lg font-bold mt-2" id="producto1-price">$15.000 COP</p>
        <label for="cantidad1" class="mt-3">Cantidad:</label>
        <input type="number" id="cantidad1" class="text-center p-2 mt-1" min="0" value="0" onchange="updateTotal()">
        <button onclick="addToCart('Café Tostado y Molido', 15000, 'cantidad1')" class="mt-3 bg-[#5C4033] text-white px-4 py-2 rounded hover:bg-[#4b3321]">Añadir al carrito</button>
        <div class="mt-4 text-left text-sm">
          <button onclick="toggleSection('producto1')" class="text-blue-600">Ver más detalles</button>
          <div id="producto1" class="section-content">
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
      </div>
      <!-- Producto 2 -->
      <div class="bg-white shadow-md rounded-lg p-4 text-center">
        <img src="https://images.unsplash.com/photo-1612197619350-196d1df9b44e?auto=format&fit=crop&w=800&q=80" alt="Café en Grano" class="w-full h-40 object-cover rounded mb-4">
        <h3 class="text-xl font-semibold" id="producto2-title">Café en Grano</h3>
        <p class="text-gray-600 mt-2" id="producto2-description">Granos frescos, seleccionados y empacados al vacío.</p>
        <p class="text-lg font-bold mt-2" id="producto2-price">$20.000 COP</p>
        <label for="cantidad2" class="mt-3">Cantidad:</label>
        <input type="number" id="cantidad2" class="text-center p-2 mt-1" min="0" value="0" onchange="updateTotal()">
        <button onclick="addToCart('Café en Grano', 20000, 'cantidad2')" class="mt-3 bg-[#5C4033] text-white px-4 py-2 rounded hover:bg-[#4b3321]">Añadir al carrito</button>
        <div class="mt-4 text-left text-sm">
          <button onclick="toggleSection('producto2')" class="text-blue-600">Ver más detalles</button>
          <div id="producto2" class="section-content">
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
      </div>
      <!-- Producto 3 -->
      <div class="bg-white shadow-md rounded-lg p-4 text-center">
        <img src="https://images.unsplash.com/photo-1601758123927-196dbde0e57e?auto=format&fit=crop&w=800&q=80" alt="Café al por Mayor" class="w-full h-40 object-cover rounded mb-4">
        <h3 class="text-xl font-semibold" id="producto3-title">Café al por Mayor</h3>
        <p class="text-gray-600 mt-2" id="producto3-description">Ideal para cafeterías, restaurantes y distribuidores.</p>
        <p class="text-lg font-bold mt-2" id="producto3-price">$500.000 COP</p>
        <label for="cantidad3" class="mt-3">Cantidad:</label>
        <input type="number" id="cantidad3" class="text-center p-2 mt-1" min="0" value="0" onchange="updateTotal()">
        <button onclick="addToCart('Café al por Mayor', 500000, 'cantidad3')" class="mt-3 bg-[#5C4033] text-white px-4 py-2 rounded hover:bg-[#4b3321]">Añadir al carrito</button>
        <div class="mt-4 text-left text-sm">
          <button onclick="toggleSection('producto3')" class="text-blue-600">Ver más detalles</button>
          <div id="producto3" class="section-content">
            <p><strong>Especificaciones:</strong></p>
            <ul>
              <li>Origen: Variado, de las mejores fincas de Colombia</li>
              <li>Proceso: Grano seleccionado para calidad premium</li>
              <li>Ideal para: Empresas, restaurantes y cafeterías</li>
              <li>Empaque: Bultos de 40 kg sellados</li>
              <li><strong>Almacenamiento:</strong> Conservar en lugar seco y fresco para asegurar la calidad.</li>
              <li><strong>Duración:</strong> Mantener la frescura y sabor hasta 6 meses.</li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Carrito de Compras -->
  <section id="carrito" class="p-10 bg-gray-100">
    <h2 class="text-3xl font-bold mb-6" id="carrito-title">Carrito de Compras</h2>
    <div id="cart-items" class="mb-6"></div>
    <p class="text-lg font-bold" id="carrito-total">Total de tu compra: $0 COP</p>
    <button class="mt-4 bg-[#5C4033] text-white px-6 py-3 rounded-lg">Proceder al pago</button>
  </section>

  <script>
    let cart = [];
    let totalPrice = 0;

    function addToCart(product, price, quantityId) {
      const quantity = parseInt(document.getElementById(quantityId).value);
      if (quantity > 0) {
        const item = { product, price, quantity };
        cart.push(item);
        totalPrice += price * quantity;
        updateCart();
      }
    }

    function updateCart() {
      const cartItems = document.getElementById('cart-items');
      cartItems.innerHTML = '';
      cart.forEach(item => {
        const itemElement = document.createElement('div');
        itemElement.innerHTML = `${item.product} - ${item.quantity} x $${item.price} = $${item.price * item.quantity}`;
        cartItems.appendChild(itemElement);
      });
      document.getElementById('carrito-total').innerText = `Total de tu compra: $${totalPrice} COP`;
    }

    function toggleSection(id) {
      const element = document.getElementById(id);
      element.classList.toggle('show');
    }

    function changeLanguage() {
      const language = document.getElementById('language').value;
      const translations = {
        es: {
          'inicio-title': 'Bienvenido a Comerciacafé',
          'inicio-description': 'El sabor auténtico del café colombiano, directo de las montañas a tu taza.',
          'productos-title': 'Nuestros Productos',
          'producto1-title': 'Café Tostado y Molido',
          'producto1-description': 'Tueste medio perfecto para cafetera o prensa francesa.',
          'producto1-price': '$15.000 COP',
          'producto2-title': 'Café en Grano',
          'producto2-description': 'Granos frescos, seleccionados y empacados al vacío.',
          'producto2-price': '$20.000 COP',
          'producto3-title': 'Café al por Mayor',
          'producto3-description': 'Ideal para cafeterías, restaurantes y distribuidores.',
          'producto3-price': '$500.000 COP',
          'nosotros-title': 'Nosotros',
          'nosotros-subtitle': 'Quiénes somos',
          'nosotros-description': 'Comerciacafé es una empresa colombiana dedicada a la comercialización de café de alta calidad...',
          'metodos-title': 'Métodos de Envío',
          'envio-nacional-title': 'Envío Nacional',
          'envio-nacional-description': 'Realizamos envíos a todo el territorio colombiano...',
          'envio-internacional-title': 'Envío Internacional',
          'envio-internacional-description': 'Hacemos envíos a los Estados Unidos, México y Europa...',
          'garantias-title': 'Garantías y Cuidados',
          'garantia-calidad-title': 'Garantía de Calidad',
          'garantia-calidad-description': 'Si no estás satisfecho con la calidad del café...',
          'carrito-title': 'Carrito de Compras',
          'carrito-total': 'Total de tu compra: $535.000 COP',
        },
        en: {
          'inicio-title': 'Welcome to Comerciacafé',
          'inicio-description': 'The authentic taste of Colombian coffee, directly from the mountains to your cup.',
          'productos-title': 'Our Products',
          'producto1-title': 'Toasted and Ground Coffee',
          'producto1-description': 'Perfect medium roast for coffee makers or French press.',
          'producto1-price': '$15.000 COP',
          'producto2-title': 'Coffee Beans',
          'producto2-description': 'Fresh beans, selected and vacuum packed.',
          'producto2-price': '$20.000 COP',
          'producto3-title': 'Wholesale Coffee',
          'producto3-description': 'Ideal for cafes, restaurants, and distributors.',
          'producto3-price': '$500.000 COP',
          'nosotros-title': 'About Us',
          'nosotros-subtitle': 'Who We Are',
          'nosotros-description': 'Comerciacafé is a Colombian company dedicated to the commercialization of high-quality coffee...',
          'metodos-title': 'Shipping Methods',
          'envio-nacional-title': 'National Shipping',
          'envio-nacional-description': 'We ship throughout Colombia...',
          'envio-internacional-title': 'International Shipping',
          'envio-internacional-description': 'We ship to the United States, Mexico, and Europe...',
          'garantias-title': 'Guarantees and Care',
          'garantia-calidad-title': 'Quality Guarantee',
          'garantia-calidad-description': 'If you are not satisfied with the coffee quality...',
          'carrito-title': 'Shopping Cart',
          'carrito-total': 'Your total purchase: $535.000 COP',
        }
      };

      const selectedLang = translations[language];
      for (const [key, value] of Object.entries(selectedLang)) {
        document.getElementById(key).innerText = value;
      }
    }
  </script>

</body>
</html>
