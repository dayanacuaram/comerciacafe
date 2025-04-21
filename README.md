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
    tbody.innerHTML = ""; // Limpiar contenido previo del carrito
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

  // Mostrar carrito automáticamente si el hash es #carrito
  window.addEventListener('DOMContentLoaded', () => {
    if (location.hash === '#carrito') {
      mostrarCarrito();
    }
  });
</script>

