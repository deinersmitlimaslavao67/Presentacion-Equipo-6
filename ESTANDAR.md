# Estándar de codificación - Equipo 6 
Lenguaje(s) del proyecto formativo: ... 
## 1. Nombrado (pendiente) 
## 2. Formato (pendiente) 
## 3. Comentarios y documentación

### ¿Cuándo y cómo comentar el código?

Para mi proyecto **Tienda SENA** (un sistema web de catálogo y carrito de compras con API en Node.js), aplicaría estas reglas:

* **Cuándo comentar:**
  * **Cuando hay reglas de negocio o lógica compleja:** por ejemplo, explicar cómo se calcula un descuento por compras al por mayor o el IVA, en lugar de dejar fórmulas sueltas sin contexto.
  * **Cuando tomo una decisión técnica no evidente:** por ejemplo, explicar por qué uso `localStorage` para guardar el carrito temporalmente antes de que el usuario inicie sesión, o por qué aplico un `setTimeout` específico en una validación.
  * **Cuando dejo tareas pendientes o advertencias:** usando etiquetas estándar como `// TODO: Conectar con la pasarela de pagos` o `// FIXME: Validar stock negativo antes de confirmar pedido`.
  * **Cuándo NO comentar:** nunca comento cosas obvias que el mismo código ya dice (por ejemplo, `// suma 1 al contador` o `// obtiene los productos`), ni dejo bloques de código viejo comentado (para eso uso Git).

* **Cómo comentar:**
  * Escribo comentarios cortos, directos y en español claro, enfocados en explicar el **porqué** (la intención detrás del código) y no el **qué** (la sintaxis).
  * Mantengo los comentarios siempre actualizados cada vez que modifico la lógica de un archivo.

---

### ¿Cómo documentar funciones?

Las funciones clave, utilidades y endpoints de la API de **Tienda SENA** se documentan usando bloques estándar como **JSDoc** (en JavaScript) justo encima de la función. Este bloque debe indicar:

1. **Descripción breve:** qué hace la función.
2. **`@param`:** qué parámetros recibe, su tipo de dato y qué representa cada uno.
3. **`@returns`:** qué valor o estructura devuelve.
4. **`@throws` (si aplica):** qué error lanza si los datos son inválidos.

**Ejemplo aplicado al proyecto:**

```javascript
/**
 * Calcula el total a pagar del carrito aplicando un descuento si supera el monto mínimo.
 *
 * @param {Array<{nombre: string, precio: number, cantidad: number}>} productos - Lista de productos en el carrito.
 * @param {number} porcentajeDescuento - Porcentaje de descuento a aplicar (ej. 10 para 10%).
 * @returns {number} El valor total final con el descuento aplicado.
 * @throws {Error} Si la lista de productos está vacía o contiene precios negativos.
 */
function calcularTotalCarrito(productos, porcentajeDescuento = 0) {
  // Se aplica descuento solo si la compra supera los $100.000 COP (regla de promoción vigente)
  const subtotal = productos.reduce((acc, item) => acc + item.precio * item.cantidad, 0);
  if (subtotal > 100000 && porcentajeDescuento > 0) {
    return subtotal - (subtotal * (porcentajeDescuento / 100));
  }
  return subtotal;
}
## 4. Estructura de carpetas

### Esquema de carpetas principales y subcarpetas


tienda-sena/
├── backend/
│   ├── src/
│   │   ├── controllers/
│   │   ├── models/
│   │   └── routes/
│   ├── .dockerignore
│   ├── Dockerfile
│   ├── package.json
│   ├── package-lock.json
│   └── server.js
├── frontend/
│   ├── public/
│   ├── src/
│   │   ├── assets/
│   │   ├── components/
│   │   ├── pages/
│   │   └── services/
│   ├── .dockerignore
│   ├── Dockerfile
│   ├── index.html
│   ├── package.json
│   ├── package-lock.json
│   └── vite.config.js
├── .gitignore
└── README.md
Breve explicación de qué va dentro de cada carpeta
tienda-sena/ (Raíz del proyecto): contiene la estructura general del repositorio, el archivo .gitignore para evitar subir archivos innecesarios o sensibles (como node_modules o .env) y el README.md con la documentación del proyecto.

backend/: aloja toda la lógica del servidor y la API REST construida con Node.js, incluyendo su Dockerfile, sus dependencias (package.json) y el punto de entrada server.js.

backend/src/routes/: define las rutas o endpoints de la API (por ejemplo, /api/productos o /api/health).

backend/src/controllers/: contiene la lógica que procesa cada petición y devuelve las respuestas al cliente.

backend/src/models/: guarda la estructura de los datos o consultas hacia la base de datos.

frontend/: contiene la aplicación web visual con la que interactúa el usuario, configurada con Vite y preparada para ejecutarse en contenedor mediante su propio Dockerfile.

frontend/public/: almacena archivos estáticos públicos como el ícono de la pestaña (favicon) o imágenes que no requieren procesamiento.

frontend/src/assets/: guarda recursos internos como hojas de estilo CSS, logotipos e ilustraciones.

frontend/src/components/: contiene piezas reutilizables de la interfaz (barra de navegación, tarjetas de producto, botón del carrito, pie de página).

frontend/src/pages/: agrupa las vistas principales de la tienda (inicio, catálogo de productos, detalle de compra).

frontend/src/services/: centraliza las funciones que se conectan con el backend mediante fetch o axios para consultar los productos y enviar pedidos.

## 5. Git: ramas, commits y pull requests (pendiente)