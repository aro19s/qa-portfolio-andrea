# 4.1 Login – Test Cases – TCN-RES-LOGIN


---

## **Login exitoso con credenciales válidas**

| Campo                 | Detalle |
|-------                |---------|
| **ID**                | TC-RES-LOGIN-001 |
| **Test Condition**    | TCN-RES-LOGIN-001 |
| **Título**            | Login con credenciales válidas |
| **Precondiciones**    | - El usuario residente debe estar registrado en el sistema.|
| **Pasos**             | 1. Abrir la app móvil.<br>2. Ingresar correo válido registrado.<br>3. Ingresar la contraseña correcta. <br>4. Presionar el botón “Iniciar sesión”. |
| **Datos de prueba**   | correo: residentemetropolis@gmail.com<br>contraseña: password |
| **Resultado esperado**| - El sistema permite el acceso.<br>- El usuario es redirigido al Dashboard del residente.<br>- No se muestra ningún mensaje de error. |
| **Postcondiciones**   | El usuario queda con sesión activa. |

---

## **Error por contraseña incorrecta**

| Campo | Detalle |
|-------|---------|
| **ID** | TC-RES-LOGIN-002 |
| **Test Condition** | TCN-RES-LOGIN-002 |
| **Título** | Login con contraseña incorrecta |
| **Precondiciones** | - El usuario debe estar registrado en el sistema. |
| **Pasos** | 1. Abrir la app móvil.<br>2. Ingresar correo válido registrado.<br>3. Ingresar una contraseña incorrecta.<br>4. Presionar “Iniciar sesión”. |
| **Datos de prueba** | correo: residentemetropolis@gmail.com<br>contraseña: Pasword |
| **Resultado esperado** | - El sistema no permite el acceso.<br>- Se muestra mensaje: “Las credenciales no coinciden con nuestros registros”. |
| **Postcondiciones** | El usuario permanece en la pantalla de Login. |

---

## **Error por correo no registrado**

| Campo | Detalle |
|-------|---------|
| **ID** | TC-RES-LOGIN-003 |
| **Test Condition** | TCN-RES-LOGIN-003 |
| **Título** | Login con correo no registrado |
| **Precondiciones** | El correo ingresado no debe existir en la base de datos. |
| **Pasos** | 1. Abrir la app móvil.<br>2. Ingresar correo no registrado en la base de datos.<br>3. Ingresar la contraseña correcta.<br>4. Presionar “Iniciar sesión”. |
| **Datos de prueba** | correo: noexiste@gmail.com<br>contraseña: password |
| **Resultado esperado** | - El sistema no permite el acceso.<br>- Se muestra mensaje: “Las credenciales no coinciden con nuestros registros”. |
| **Postcondiciones** | El usuario permanece en la pantalla de Login. |

---

## **Error por formato de correo inválido**

| Campo | Detalle |
|-------|---------|
| **ID** | TC-RES-LOGIN-004 |
| **Test Condition** | TCN-RES-LOGIN-004 |
| **Título** | Login con formato de correo inválido |
| **Precondiciones** | Ninguna. |
| **Pasos** | 1. Abrir la app.<br>2. Ingresar correo con formato inválido.<br>3. Ingresar contraseña.<br>4. Presionar “Iniciar sesión”. |
| **Datos de prueba** | 1. Correo: residente.com<br> Contraseña: password<br><br>2. Correo: residente@gmail<br>Contraseña: password<br><br>3. Correo: residente.gmail.com<br>Contraseña: password<br>|
| **Resultado esperado** | - El sistema no permite el acceso.<br>- Se muestra mensaje: “Correo electrónico inválido”. |
| **Postcondiciones** | El usuario permanece en pantalla de Login. |

---

## **TC-RES-LOGIN-005 – Validar bloqueo por campos vacíos**

| Campo | Detalle |
|-------|---------|
| **ID** | TC-RES-LOGIN-005 |
| **Test Condition** | TCN-RES-LOGIN-005 |
| **Título** | Validar que el sistema bloquee el login si hay campos vacíos |
| **Precondiciones** | Ninguna. |
| **Pasos** | **Escenario A:** Campo correo vacío<br>1. Abrir la app.<br>2. Dejar el campo correo vacío.<br>3. Ingresar contraseña válida.<br>4. Presionar “Iniciar sesión”.<br><br>**Escenario B:** Campo contraseña vacío<br>1. Abrir la app.<br>2. Ingresar correo válido.<br>3. Dejar contraseña vacía.<br>4. Presionar “Iniciar sesión”.<br><br>**Escenario C:** Ambos campos vacíos<br>1. Abrir la app.<br>2. Dejar ambos campos vacíos.<br>3. Presionar “Iniciar sesión”. |
| **Datos de prueba** | correo: “”<br>contraseña: “” |
| **Resultado esperado** | - El botón “Iniciar sesión” puede estar deshabilitado **o** generar mensaje de “Campos requeridos”.<br>- No se permite avanzar. |
| **Postcondiciones** | El usuario permanece en pantalla de Login. |


