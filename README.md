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
        <p>Realizamos envíos a toda Colombia a través de transportadoras reconocidas como Servientrega y Coordinadora. Los pedidos se despachan en un máximo de 24 horas y el tiempo estimado de entrega es entre 2 y 5 días hábiles, dependiendo de la ubicación del cliente.</p>
      </div>
      <div>
        <h3 class="text-2xl font-semibold">✅ Calidad Garantizada</h3>
        <p>Ofrecemos café 100% arábica, cultivado bajo prácticas sostenibles y recolectado manualmente en su punto óptimo de maduración. Nuestro proceso incluye selección cuidadosa, tueste artesanal y pruebas de catación para garantizar una experiencia única en sabor y aroma.</p>
      </div>
      <div>
        <h3 class="text-2xl font-semibold">📦 Especificaciones del Producto</h3>
        <ul class="list-disc list-inside">
          <li>Origen: Quindío, Colombia</li>
          <li>Altura: 1.600 – 1.900 m.s.n.m</li>
          <li>Variedad: Caturra y Castillo</li>
          <li>Proceso: Lavado</li>
          <li>Empaque: Bolsa con válvula desgasificadora</li>
          <li>Presentaciones: 500g, 1kg y bultos de 40kg</li>
        </ul>
      </div>
      <div>
        <h3 class="text-2xl font-semibold">💬 Atención al Cliente</h3>
        <p>Si tienes preguntas, estamos disponibles para ayudarte. Escríb
