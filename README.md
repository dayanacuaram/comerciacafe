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
        <h3 class="text-xl font-semibold">Café en Grano</h3>
        <p class="text-gray-600 mt-2">Granos frescos, seleccionados y empacados al vacío.</p>
        <p class="text-lg font-bold mt-2">$20.000 COP</p>
        <button onclick="addToCart('Café en Grano', 20000)" class="mt-3 bg-[#5C4033] text-white px-4 py-2 rounded hover:bg-[#4b3321]">Añadir al carrito</button>
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
        <h3 class="text-xl font-semibold">Café al por Mayor</h3>
        <p class="text-gray-600 mt-2">Ideal para cafeterías, restaurantes y distribuidores.</p>
        <p class="text-lg font-bold mt-2">$500.000 COP</p>
        <button onclick="addToCart('Café al por Mayor', 500000)" class="mt-3 bg-[#5C4033] text-white px-4 py-2 rounded hover:bg-[#4b3321]">Añadir al carrito</button>
        <div class="mt-4 text-left text-sm">
          <button onclick="toggleSection('producto3')" class="text-blue-600">Ver más detalles</button>
          <div id="producto3" class="section-content">
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
    </div>
  </section>

  <!-- MÉTODOS DE ENVÍO -->
  <section id="metodos" class="p-10 bg-gray-100">
    <h2 class="text-3xl font-bold text-center mb-8">Métodos de Envío</h2>
    <div class="space-y-4">
      <div class="bg-white shadow-md p-6 rounded-lg">
        <h3 class="text-xl font-semibold">Envío Nacional</h3>
        <p>Realizamos envíos a todo el territorio colombiano. El tiempo estimado de entrega es de 2 a 5 días hábiles.</p>
      </div>
      <div class="bg-white shadow-md p-6 rounded-lg">
        <h3 class="text-xl font-semibold">Envío Internacional</h3>
        <p>Hacemos envíos a los Estados Unidos, México y Europa. El tiempo estimado de entrega es de 7 a 15 días hábiles.</p>
      </div>
    </div>
  </section>

  <!-- GARANTÍAS -->
  <section id="garantias" class="p-10 bg-white">
    <h2 class="text-3xl font-bold text-center mb-8">Garantías y Cuidados</h2>
    <div class="space-y-4">
      <div class="bg-white shadow-md p-6 rounded-lg">
        <h3 class="text-xl font-semibold">Garantía de Calidad</h3>
        <p>Si no estás satisfecho con la calidad del café, ofrecemos una garantía de devolución de dinero dentro de los primeros 7 días después de la compra.</p>
      </div>
      <div class="bg-white shadow-md p-6 rounded-lg">
        <h3 class="text-xl font-semibold">Instrucciones de Almacenamiento</h3>
        <p>Conservar los productos en un lugar fresco y seco, alejado de la luz solar directa. Idealmente en envases herméticos.</p>
      </div>
    </div>
  </section>

  <!-- CONTACTO -->
  <section id="contacto" class="p-10 bg-gray-100">
    <h2 class="text-3xl font-bold text-center mb-8">Contáctanos</h2>
    <div class="bg-white shadow-md p-6 rounded-lg">
      <h3 class="text-xl font-semibold">Dirección</h3>
      <p>Calle 123 #45-67, Bogotá, Colombia</p>
      <h3 class="text-xl font-semibold">Correo Electrónico</h3>
      <p>contacto@comerciacafe.com</p>
      <h3 class="text-xl font-semibold">Teléfono</h3>
      <p>+57 123 456 789</p>
    </div>
  </section>

  <!-- CARRO DE COMPRAS -->
  <section id="carrito" class="p-10 text-center">
    <h2 class="text-3xl font-bold mb-8">Carrito de Compras</h2>
    <div class="bg-white shadow-md rounded-lg p-6 mb-6">
      <p class="text-xl font-semibold mb-4">Total de tu compra: $535.000 COP</p>
      <button class="bg-[#5C4033] text-white px-6 py-3 rounded hover:bg-[#4b3321]">Ir a Pagar</button>
    </div>
  </section>

  <!-- Función JavaScript para alternar visibilidad -->
  <script>
    function toggleSection(sectionId) {
      const section = document.getElementById(sectionId);
      section.classList.toggle('show');
    }

    function addToCart(product, price) {
      console.log(product, price);
    }
  </script>

</body>
</html>

  </script>

</body>
</html>
