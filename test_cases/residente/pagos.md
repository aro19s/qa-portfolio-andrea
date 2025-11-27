# Pagos – Test Cases – TCN-RES-PAG

---

## **Validar visualización de pagos pendientes asociados al residente**

| Campo                 | Detalle |
|-------                |---------|
| **ID**                | TC-RES-PAG-001 |
| **Test Condition**    | TCN-RES-PAG-001 |
| **Título**            | Visualización de pagos pendientes del residente |
| **Precondiciones**    | - El residente tiene conceptos de pago previamente asignados por un administrador en el sistema.|
| **Pasos**             | 1. Abrir la app móvil.<br>2. Ingresar a la app con un residente registrado.<br>3. Navegar al módulo Pagos.<br>4. Seleccionar el botón "pagar".<br>5. Verificar la lista de conceptos de pago mostrados. |
| **Datos de prueba**   | Usuario: Residente con conceptos de pago asignados |
| **Resultado esperado**| - Se muestran únicamente los pagos pendientes asignados al residente autenticado.<br>- Se muestra: título, descripción, valor y botón "pagar". |
| **Postcondiciones**   | Ninguna. |

---

## **Validar aplicación correcta de filtros de búsqueda**

| Campo                 | Detalle |
|-------                |---------|
| **ID**                | TC-RES-PAG-003 |
| **Test Condition**    | TCN-RES-PAG-003 |
| **Título**            | Aplicación de filtros en pagos |
| **Precondiciones**    | - El residente tiene varios pagos pendientes registrados con distintos títulos, descripciones y valores. |
| **Postcondiciones**   | Ninguna. |

### Escenario A — Filtrar por Título

| Campo | Detalle |
|------|---------|
| **Pasos** | 1. Abrir la app móvil.<br>2. Ingresar a la app con un residente registrado.<br>3. Navegar al módulo Pagos.<br>4. Seleccionar el botón "pagar".<br>5. Seleccionar el ícono de filtros.<br>6. Ingresar "Administración" en el campo "Título".<br>7. Seleccionar "Aplicar". |
| **Datos de prueba** | Usuario con 4 conceptos de pago:<br>1. Título: Administración — Descripción: Pago mensual — Valor: 120000<br>2. Título: Parqueadero — Descripción: Cuota mensual — Valor: 80000<br>3. Título: Aseo — Descripción: Servicio de aseo — Valor: 40000<br>
4. Título: Extra mantenimiento — Descripción: Servicio técnico — Valor: 150000 |
| **Resultado esperado** | - El sistema mostrará únicamente el concepto:<br> Título: Administración — Descripción: Pago mensual — Valor: 120000 |

### Escenario B — Filtrar por Valor

| Campo | Detalle |
|------|---------|
| **Pasos** | 1. Abrir la app móvil.<br>2. Ingresar a la app con un residente registrado.<br>3. Navegar al módulo Pagos.<br>4. Seleccionar el botón "pagar".<br>5. Seleccionar el ícono de filtros.<br>6. Ingresar "80000" en el campo "Valor".<br>7. Seleccionar "Aplicar". |
| **Datos de prueba** | Usuario con 4 conceptos de pago:<br>1. Título: Administración — Descripción: Pago mensual — Valor: 120000<br>2. Título: Parqueadero — Descripción: Cuota mensual — Valor: 80000<br>3. Título: Aseo — Descripción: Servicio de aseo — Valor: 40000<br>
4. Título: Extra mantenimiento — Descripción: Servicio técnico — Valor: 150000 |
| **Resultado esperado** | - El sistema mostrará únicamente el concepto:<br> Título: Parqueadero — Descripción: Cuota mensual — Valor: 80000 |
