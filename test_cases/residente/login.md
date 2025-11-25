# 4.1 Login – Test Cases
(Basado en TCN-RES-LOGIN)

---

## **TC-RES-LOGIN-001 – Login exitoso con credenciales válidas**

| Campo                 | Detalle |
|-------                |---------|
| **ID**                | TC-RES-LOGIN-001 |
| **Test Condition**    | TCN-RES-LOGIN-001 |
| **Título**            | Validar login exitoso con credenciales válidas |
| **Precondiciones**    | - El usuario residente debe estar registrado.<br>- Debe existir una contraseña válida. |
| **Pasos**             | 1. Abrir la app móvil.  2. Navegar a la pantalla de Login.  3. Ingresar correo válido registrado.  4. Ingresar la contraseña correcta.  5. Presionar el botón “Iniciar sesión”. |
| **Datos de prueba**   | correo: usuario@correo.com<br>contraseña: Contraseña123 |
| **Resultado esperado**| - El sistema permite el acceso.<br>- El usuario es redirigido al Dashboard del residente.<br>- No se muestra ningún mensaje de error. |
| **Postcondiciones**   | El usuario queda con sesión activa. |

---

## **TC-RES-LOGIN-002 – Error por contraseña incorrecta**

| Campo | Detalle |
|-------|---------|
| **ID** | TC-RES-LOGIN-002 |
| **Test Condition** | TCN-RES-LOGIN-002 |
| **Título** | Validar error al iniciar sesión con contraseña incorrecta |
| **Precondiciones** | Usuario registrado en el sistema. |
| **Pasos** | 1. Abrir la app móvil.<br>2. Ir a la pantalla de Login.<br>3. Ingresar correo válido registrado.<br>4. Ingresar una contraseña incorrecta.<br>5. Presionar “Iniciar sesión”. |
| **Datos de prueba** | correo: usuario@correo.com<br>contraseña: ABC123 |
| **Resultado esperado** | - El sistema no permite el acceso.<br>- Se muestra mensaje: “Contraseña incorrecta” o equivalente. |
| **Postcondiciones** | El usuario permanece en la pantalla de Login. |

---

## **TC-RES-LOGIN-003 – Error por correo no registrado**

| Campo | Detalle |
|-------|---------|
| **ID** | TC-RES-LOGIN-003 |
| **Test Condition** | TCN-RES-LOGIN-003 |
| **Título** | Validar error al iniciar sesión con correo no registrado |
| **Precondiciones** | El correo ingresado **no debe existir** en la base de datos. |
| **Pasos** | 1. Abrir la app móvil.<br>2. Ir a la pantalla de Login.<br>3. Ingresar un correo no registrado.<br>4. Ingresar una contraseña cualquiera.<br>5. Presionar “Iniciar sesión”. |
| **Datos de prueba** | correo: noexiste@correo.com<br>contraseña: 123456 |
| **Resultado esperado** | - El sistema no permite el acceso.<br>- Se muestra mensaje: “El correo no se encuentra registrado” o equivalente. |
| **Postcondiciones** | El usuario permanece en la pantalla de Login. |

---

## **TC-RES-LOGIN-004 – Validar bloqueo por campos vacíos**

| Campo | Detalle |
|-------|---------|
| **ID** | TC-RES-LOGIN-004 |
| **Test Condition** | TCN-RES-LOGIN-004 |
| **Título** | Validar que el sistema bloquee el login si hay campos vacíos |
| **Precondiciones** | Ninguna. |
| **Pasos** | **Escenario A:** Campo correo vacío<br>1. Abrir la app.<br>2. Dejar el campo correo vacío.<br>3. Ingresar contraseña válida.<br>4. Presionar “Iniciar sesión”.<br><br>**Escenario B:** Campo contraseña vacío<br>1. Abrir la app.<br>2. Ingresar correo válido.<br>3. Dejar contraseña vacía.<br>4. Presionar “Iniciar sesión”.<br><br>**Escenario C:** Ambos campos vacíos<br>1. Abrir la app.<br>2. Dejar ambos campos vacíos.<br>3. Presionar “Iniciar sesión”. |
| **Datos de prueba** | correo: “”<br>contraseña: “” |
| **Resultado esperado** | - El botón “Iniciar sesión” puede estar deshabilitado **o** generar mensaje de “Campos requeridos”.<br>- No se permite avanzar. |
| **Postcondiciones** | El usuario permanece en pantalla de Login. |


