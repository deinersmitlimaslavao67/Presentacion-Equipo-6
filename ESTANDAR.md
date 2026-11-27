# Estándar de codificación - Equipo 6 
Lenguaje(s) del proyecto formativo: ... 
## 1. Nombrado 

### 1.1. Idioma del Código
* **Código fuente (variables, funciones, clases, rutas y base de datos):** **Inglés** de forma obligatoria (ej. `userController`, `totalAmount`, `getOrderById()`). Esto evita mezclar palabras reservadas del lenguaje con términos en español.
* **Comentarios, mensajes de commit, documentación y textos de interfaz (UI):** **Español** (ej. `// Calcula el total con impuestos`).

### 1.2. Variables, Funciones, Clases y Constantes
| Elemento | Convención | Ejemplo Correcto | Ejemplo Incorrecto |
| :--- | :--- | :--- | :--- |
| **Variables** | `camelCase` | `userName`, `isActive` | `user_name`, `NombreUsuario` |
| **Funciones / Métodos** | `camelCase` (verbo + sustantivo) | `calculateTotal()`, `fetchUsers()` | `Calculate_Total()`, `usuarios()` |
| **Clases / Componentes** | `PascalCase` | `UserController`, `OrderService` | `userController`, `order_service` |
| **Constantes globales** | `UPPER_SNAKE_CASE` | `MAX_LOGIN_ATTEMPTS`, `API_URL` | `maxLoginAttempts`, `apiUrl` |

### 1.3. Archivos y Carpetas
* **Carpetas:** Usar `kebab-case` (minúsculas separadas por guiones) y en plural cuando agrupen múltiples elementos:
  * `src/controllers/`, `src/user-profiles/`, `public/assets/`
* **Archivos de código (JS, PHP, HTML, CSS):** Usar `kebab-case` en minúsculas:
  * `auth-controller.js`, `order-summary.php`, `main-styles.css`
* **Archivos de Clases / Modelos / Componentes (si el framework lo exige):** Usar `PascalCase` coincidiendo exactamente con el nombre de la clase interna:
  * `User.php`, `DatabaseConnection.java`, `ProductCard.jsx`

### 1.4. Base de Datos (Tablas y Campos)
* **Formato general:** Todo en `snake_case` (minúsculas separadas por guion bajo), sin tildes, sin espacios y sin caracteres especiales (`ñ`).
* **Tablas:** Nombres en **plural**:
  * `users`, `order_items`, `payment_methods`
* **Columnas / Campos:** Nombres en **singular**:
  * `first_name`, `created_at`, `unit_price`
* **Llaves Primarias (PK) y Foráneas (FK):**
  * Llave primaria: `id` (o `<tabla_singular>_id` según el estándar del proyecto).
  * Llave foránea: `<tabla_referenciada_singular>_id` (ej. `user_id`, `product_id`).

## 2. Formato 

Para garantizar que el código de todos los desarrolladores luzca uniforme y evitar conflictos innecesarios en los *commits* por diferencias visuales, se establecen las siguientes reglas de formato:

### 2.1. Indentación
* **Tipo y tamaño:** Usar **2 espacios** por nivel de indentación (en tecnologías web como HTML, CSS, JavaScript y JSON) o **4 espacios** (si el backend está en PHP, Java o Python).
* **Prohibido mezclar:** No utilizar tabulaciones (`Tab`) reales; el editor (VS Code) debe estar configurado con *"Insert Spaces"* para convertir automáticamente las tabulaciones en espacios.

### 2.2. Uso de Comillas
* **Código (JavaScript / PHP / Backend):** Usar **comillas simples (`' '`)** por defecto para cadenas de texto (`const role = 'admin';`).
* **Interpolación de variables:** Usar *template literals* (comillas invertidas `` ` ` ``) en JavaScript o comillas dobles (`" "`) en PHP únicamente cuando se inserten variables dentro del texto (`` `Hola, ${userName}` ``).
* **HTML y JSON:** Usar **comillas dobles (`" "`)** de forma obligatoria para atributos HTML (`<div class="card">`) y claves/valores en archivos JSON.

### 2.3. Largo Máximo de Línea
* **Límite:** **100 caracteres** por línea como máximo.
* **Salto de línea:** Si una instrucción, cadena de texto, lista de parámetros o consulta SQL supera los 100 caracteres, debe dividirse en múltiples líneas de forma limpia e indentada para evitar el desplazamiento horizontal (*scroll*) en el editor.

### 2.4. Estilo de Llaves `{ }`
* **Convención:** Utilizar el estilo **K&R / 1TBS (One True Brace Style)**, donde la llave de apertura `{` se coloca en la **misma línea** de la declaración (funciones, condicionales `if/else`, bucles `for/while` y clases), separada por un espacio.
* **Llave de cierre:** Se coloca en una nueva línea alineada verticalmente con el inicio de la declaración.
* **Bloques obligatorios:** Siempre usar llaves `{ }` incluso en condicionales `if` o bucles de una sola línea.

**Ejemplo correcto:**
```javascript
if (isActive && userRole === 'admin') {
  grantAccess(userId);
} else {
  denyAccess();
}

## 3. Comentarios y documentación (pendiente)
## 4. Estructura de carpetas (pendiente) 
## 5. Git: ramas, commits y pull requests 

Para mantener un historial de cambios limpio, ordenado y evitar conflictos al trabajar en equipo, todos los integrantes deben seguir estrictamente estas reglas de control de versiones:

### 5.1. Convención para Nombres de Ramas
* **Rama principal (`main`):** Contiene únicamente código estable y probado. **Está estrictamente prohibido hacer `push` directo a `main`.**
* **Ramas de trabajo:** Deben crearse a partir de `main` usando `kebab-case` (todo en minúsculas y separado por guiones, sin tildes ni caracteres especiales) y comenzando con un prefijo según el tipo de tarea:
  * `feature/<nombre-tarea>`: Para nuevas funcionalidades o módulos (ej. `feature/login-usuario`, `feature/carrito-compras`).
  * `fix/<nombre-error>`: Para corrección de errores o fallos (ej. `fix/ortografia-readme`, `fix/validacion-formulario`).
  * `docs/<nombre-doc>`: Para cambios exclusivos en documentación (ej. `docs/guia-instalacion`).
  * `refactor/<nombre-mejora>`: Para reestructurar o limpiar código sin cambiar su comportamiento (ej. `refactor/conexion-bd`).

### 5.2. Formato de los Mensajes de Commit
Se utilizará el estándar **Conventional Commits** en español, redactado en tiempo presente e imperativo, con un máximo de 72 caracteres en la primera línea:

`<tipo>: <descripción breve del cambio>`

* **Tipos permitidos:**
  * `feat:` Nueva funcionalidad añadida al proyecto.
  * `fix:` Corrección de un error (*bug*).
  * `docs:` Cambios en archivos de documentación (`README.md`, comentarios).
  * `style:` Cambios de formato (espacios, comillas, indentación) que no afectan la lógica.
  * `refactor:` Mejora o reorganización interna del código.
  * `chore:` Tareas de configuración, dependencias o mantenimiento.

**Ejemplos correctos:**
* `feat: agrega endpoint para registrar usuarios`
* `fix: corrige error de ortografía en el README`
* `docs: actualiza sección de reglas de nombrado`

### 5.3. Reglas y Requisitos para Aprobar Pull Requests (PR)
Ningún cambio pasará a `main` sin antes pasar por un **Pull Request** en GitHub y cumplir con estos requisitos:

1. **Rama actualizada:** Antes de abrir el PR, el autor debe sincronizar su rama con los últimos cambios de `main` (`git pull origin main`) y resolver cualquier conflicto localmente.
2. **Descripción clara:** El PR debe tener un título descriptivo, explicar qué se hizo y referenciar el número del *Issue* correspondiente (ej. `Closes #28`).
3. **Código limpio y funcional:** El código debe respetar las reglas de nombrado y formato del proyecto, compilar/ejecutar sin errores y no incluir archivos temporales o credenciales (`.env`, `node_modules`).
4. **Revisión obligatoria:** Al menos **1 compañero del equipo** (distinto al autor) debe revisar el código y aprobar el PR antes de realizar el *Merge* hacia `main`.
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
