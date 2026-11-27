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