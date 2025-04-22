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
  <section id="productos" class="p-10 bg-white border-t border-gray-300">
    <h2 class="text-3xl font-bold text-center mb-8 text-[#5C4033]">Nuestros Productos</h2>
    <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
      <!-- Producto 1 -->
      <!-- Producto 2 -->
      <!-- Producto 3 -->
    </div>
  </section>

  <!-- INFORMACIÓN DETALLADA -->
  <section id="informacion" class="bg-gray-100 p-10 border-t border-gray-300">
    <h2 class="text-3xl font-bold text-center mb-6 text-[#5C4033]">Información Importante</h2>
    <div class="max-w-4xl mx-auto text-gray-700 space-y-10">
      <!-- SOBRE NOSOTROS -->
      <div>
        <h3 class="text-2xl font-semibold mb-2">Sobre Nosotros</h3>
        <p class="leading-relaxed">
          Comerciacafé es una empresa 100% colombiana que nace del amor por el campo y la pasión por el café. Nos dedicamos a producir, tostar y comercializar café especial de alta calidad, cultivado en las fértiles montañas del Eje Cafetero. Trabajamos directamente con caficultores locales, asegurando prácticas sostenibles y comercio justo, para que cada taza que llegue a tu hogar cuente una historia auténtica de origen.
        </p>
      </div>

      <!-- CALIDAD GARANTIZADA -->
      <div>
        <h3 class="text-2xl font-semibold mb-2">Calidad Garantizada</h3>
        <p class="leading-relaxed">
          Nuestro café es cuidadosamente seleccionado a mano, pasa por un proceso de secado natural y tostión artesanal que resalta las notas características de cada grano. Contamos con certificaciones que respaldan nuestro compromiso con la calidad, frescura y sabor. Cada lote es probado por catadores expertos para asegurar un perfil sensorial óptimo.
        </p>
      </div>

      <!-- GARANTÍA Y DEVOLUCIONES -->
      <div>
        <h3 class="text-2xl font-semibold mb-2">Garantía y Devoluciones</h3>
        <p class="leading-relaxed">
          Si por alguna razón no estás satisfecho con tu compra, ofrecemos la posibilidad de cambio o devolución dentro de los 7 días hábiles siguientes a la recepción del producto. Nuestra prioridad es tu confianza y satisfacción.
        </p>
      </div>

      <!-- TRANSPORTE Y ENVÍOS -->
      <div>
        <h3 class="text-2xl font-semibold mb-2">Transporte y Envíos</h3>
        <p class="leading-relaxed">
          Hacemos envíos a toda Colombia mediante empresas de transporte confiables como Servientrega, Coordinadora y Envía. Los tiempos de entrega varían entre 3 y 5 días hábiles dependiendo de la ubicación. Para pedidos internacionales, puedes escribirnos directamente y te ayudaremos con el proceso logístico.
        </p>
      </div>

      <!-- ESPECIFICACIONES DEL PRODUCTO -->
      <div>
        <h3 class="text-2xl font-semibold mb-2">Especificaciones del Producto</h3>
        <ul class="list-disc pl-6 space-y-1">
          <li>Origen: Caldas, Colombia</li>
          <li>Altura de cultivo: 1.600 - 2.000 msnm</li>
          <li>Variedad: Arábica Castillo</li>
          <li>Notas de cata: Chocolate, nuez y caramelo</li>
          <li>Presentaciones disponibles: 500g, 1kg, bultos de 40kg</li>
          <li>Empaque: Bolsa hermética con válvula desgasificadora</li>
          <li>Conservación: Hasta 12 meses en lugar fresco y seco</li>
        </ul>
      </div>
    </div>
  </section>

  <!-- CARRITO -->
  <section id="carrito" class="p-10 bg-white border-t border-gray-300">
    <h2 class="text-3xl font-bold text-center mb-6 text-[#5C4033]">Carrito de Compras</h2>
    <!-- CONTENIDO DINÁMICO DEL CARRITO SE INSERTA AQUÍ -->
  </section>

  <!-- FOOTER -->
  <footer class="bg-[#5C4033] text-white text-center p-4 mt-10">
    &copy; 2025 Comerciacafé. Todos los derechos reservados.
  </footer>

  <!-- SCRIPTS -->
  <script>
    // Código del carrito e intercambio de monedas
  </script>

</body>
</html>
