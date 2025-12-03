# 4.3 PQRSDF - Test Cases - TCN-RES-PQ

---

## **Validar registro de nueva PQRSDF**

| Campo                 | Detalle |
|---------------------- |---------|
| **ID**                | TC-RES-PQ-001 |
| **Test Condition**    | TCN-RES-PQ-001 |
| **Título**            | Registro exitoso de una nueva PQRSDF |
| **Precondiciones**    | - El usuario debe tener sesión activa.     |
| **Pasos**             | 1. Abrir la app.<br>2. Navegar al módulo de PQRSDF.<br>3. Presionar “Crear”.<br>4. Seleccionar tipo.<br>5. Ingresar descripción.<br>6. (Opcional) Seleccionar "Anónimo".<br>7. (Opcional) Adjuntar imágenes.<br>8. Presionar “Enviar”.<br>9. Presionar "Aceptar". |
| **Datos de prueba**   | - Tipo: Queja<br>- Descripción: "Ruido constante en la zona común."<br>- Adjuntos: imagen.jpg |
| **Resultado esperado**| - El sistema registra la PQRSDF correctamente.<br>- Se muestra mensaje: “PQRSDF creada exitosamente”.<br>- El usuario es redirigido al historial de PQRSDF. |
| **Postcondiciones**   | La PQRSDF queda almacenada en estado “En proceso" hasta que sea resuelto por un administrador. |

---

## **Validar error de registro de nueva PQRSDF por campos vacíos**

### Información General

| Campo                 | Detalle |
|---------------------- |---------|
| **ID**                | TC-RES-PQ-002 |
| **Test Condition**    | TCN-RES-PQ-002 |
| **Título**            | Error al intentar registrar PQRSDF con campos vacíos |
| **Precondiciones**    | El usuario debe tener sesión activa. |
| **Postcondiciones**   | El usuario permanece en el formulario. |


### Escenario A — Tipo vacío

| Campo | Detalle |
|------|---------|
| **Pasos** | 1. Abrir la app.<br>2. Navegar al módulo de PQRSDF.<br>3. Presionar "Crear".<br>4. Dejar el tipo sin seleccionar.<br>5. Ingresar una descripción.<br>6. Presionar “Enviar”.|
| **Datos de prueba** | Tipo: -<br>Descripción: “Problema con iluminación del área común.” |
| **Resultado esperado** | - El sistema no permite crear la PQRSDF.<br>- Se muestra mensaje: “Por favor corrige los errores del formulario.<br>- Se resalta el error en el formulario: "Selecciona un tipo de PQRSDF. |


### Escenario B — Descripción vacía

| Campo | Detalle |
|------|---------|
| **Pasos** | 1. Abrir la app.<br>2. Navegar al módulo de PQRSDF.<br>3. Presionar "Crear".<br>4. Seleccionar tipo.<br>5. Dejar la descripción vacía.<br>6. Presionar “Enviar”.|
| **Datos de prueba** | Tipo: Denuncia<br>Descripción: - |
| **Resultado esperado** | - El sistema no permite crear la PQRSDF.<br>- Se muestra mensaje: “Por favor corrige los errores del formulario.<br>- Se resalta el error en el formulario: "La descripción es obligatoria. |


### Escenario C — Ambos campos vacíos

| Campo | Detalle |
|------|---------|
| **Pasos** | 1. Abrir la app.<br>2. Navegar al módulo de PQRSDF.<br>3. Presionar "Crear".<br>4. Dejar el tipo sin seleccionar.<br>5. Dejar la descripción vacía.<br>6. Presionar “Enviar”.|
| **Datos de prueba** | Tipo: -<br>Descripción: - |
| **Resultado esperado** | - El sistema no permite crear la PQRSDF.<br>- Se muestra mensaje: “Por favor corrige los errores del formulario.<br>- Se resalta el error en el formulario.|

---

## **Validar filtrado**

### Información General

| Campo                 | Detalle |
|-----------------------|---------|
| **ID**                | TC-RES-PQ-003 |
| **Test Condition**    | TCN-RES-PQ-003 |
| **Título**            | Validación de filtros de PQRSDF usando combinaciones de pares |
| **Precondiciones**    | - El usuario tiene PQRSDFs registrados con diferentes tipos, descripciones, estados, fechas y anónimos. |
| **Pasos**             | 1. Abrir la app.<br>2. Ingresar al módulo PQRSDF.<br>3. Seleccionar el ícono de filtros.<br>4. Aplicar los filtros según la combinación de datos. |
| **Datos de prueba**   | Ver tabla de datos a continuación |
| **Resultado esperado**| - La lista muestra únicamente los PQRSDFs que cumplen con la combinación de filtros aplicada.|
| **Postcondiciones**   | Ninguna. |


## Tabla de Datos Pairwise (32 escenarios)

| ID | Tipo        | Texto | Estado    | Anónimo | Fecha |
|----|------------|-------|-----------|---------|-------|
| 1  | Solicitud   | Vacio | Todos     | Sí      | Llena |
| 2  | Felicitacion| Vacio | Rechazado | Todos   | Vacia |
| 3  | Peticion    | Lleno | En Proceso| No      | Vacia |
| 4  | Peticion    | Lleno | Resuelto  | Todos   | Llena |
| 5  | Peticion    | Lleno | Rechazado | Sí      | Llena |
| 6  | Reclamo     | Vacio | Rechazado | No      | Llena |
| 7  | Sugerencia  | Vacio | Resuelto  | Sí      | Vacia |
| 8  | Queja       | Vacio | Resuelto  | No      | Vacia |
| 9  | Todos       | Vacio | En Proceso| Sí      | Llena |
| 10 | Solicitud   | Lleno | En Proceso| Todos   | Vacia |
| 11 | Denuncia    | Lleno | Resuelto  | Sí      | Llena |
| 12 | Todos       | Lleno | Todos     | Todos   | Vacia |
| 13 | Todos       | Vacio | Rechazado | No      | Vacia |
| 14 | Queja       | Lleno | En Proceso| Todos   | Llena |
| 15 | Reclamo     | Lleno | En Proceso| Sí      | Vacia |
| 16 | Todos       | Lleno | Resuelto  | No      | Llena |
| 17 | Solicitud   | Lleno | Rechazado | No      | Vacia |
| 18 | Reclamo     | Vacio | Todos     | No      | Vacia |
| 19 | Felicitacion| Lleno | Resuelto  | Sí      | Llena |
| 20 | Sugerencia  | Lleno | Todos     | Todos   | Llena |
| 21 | Solicitud   | Lleno | Resuelto  | Todos   | Llena |
| 22 | Reclamo     | Vacio | Resuelto  | Todos   | Llena |
| 23 | Queja       | Lleno | Todos     | Sí      | Vacia |
| 24 | Denuncia    | Vacio | Todos     | No      | Vacia |
| 25 | Sugerencia  | Lleno | Rechazado | No      | Llena |
| 26 | Denuncia    | Lleno | Rechazado | Todos   | Vacia |
| 27 | Peticion    | Vacio | Todos     | No      | Llena |
| 28 | Queja       | Lleno | Rechazado | Sí      | Vacia |
| 29 | Felicitacion| Lleno | En Proceso| No      | Llena |
| 30 | Felicitacion| Lleno | Todos     | Sí      | Llena |
| 31 | Sugerencia  | Vacio | En Proceso| No      | Vacia |
| 32 | Denuncia    | Vacio | En Proceso| Todos   | Vacia |

---
