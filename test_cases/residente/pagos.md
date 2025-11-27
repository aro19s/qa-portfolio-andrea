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

| Campo               | Detalle |
|--------------------|---------|
| **ID**             | TC-RES-PAG-003 |
| **Test Condition** | TCN-RES-PAG-003 |
| **Título**         | Aplicación de filtros en pagos |
| **Precondiciones** | - El residente tiene varios pagos pendientes registrados con distintos títulos, descripciones y valores. |
| **Postcondiciones**| Ninguna. |

---

## **Datos de prueba generales**

Conceptos de pago disponibles para el residente:

| Título               | Descripción        | Valor   |
|----------------------|--------------------|---------|
| Administración       | Pago mensual       | 120000  |
| Parqueadero          | Cuota mensual      | 80000   |
| Aseo                 | Servicio de aseo   | 40000   |
| Extra mantenimiento  | Servicio técnico   | 150000  |

---

> **Flujo base (común para todos los escenarios):**
> 1. Abrir la app móvil.  
> 2. Ingresar con un residente registrado.  
> 3. Navegar al módulo Pagos.  
> 4. Seleccionar el botón "Pagar".  
> 5. Seleccionar el ícono de filtros.

---

# **Escenario A — Filtrar por Título con coincidencias**

| Campo | Detalle |
|-------|---------|
| **Pasos** | 1. Ejecutar el flujo base.<br>2. Ingresar **"Administración"** en el campo Título.<br>3. Seleccionar **Aplicar**. |
| **Datos de prueba** | Se utilizan los datos generales definidos arriba. |
| **Resultado esperado** | - El sistema muestra únicamente el concepto:<br> • **Administración / Pago mensual / 120000** |

---

# **Escenario B — Filtrar por Valor con coincidencias**

| Campo | Detalle |
|-------|---------|
| **Pasos** | 1. Ejecutar el flujo base.<br>2. Ingresar **"80000"** en el campo Valor.<br>3. Seleccionar **Aplicar**. |
| **Datos de prueba** | Se utilizan los datos generales definidos arriba. |
| **Resultado esperado** | - El sistema muestra únicamente el concepto:<br> • **Parqueadero / Cuota mensual / 80000** |

---

# **Escenario C — Filtrar por Título sin coincidencias**

| Campo | Detalle |
|-------|---------|
| **Pasos** | 1. Ejecutar el flujo base.<br>2. Ingresar **"Multa"** en el campo Título.<br>3. Seleccionar **Aplicar**. |
| **Datos de prueba** | Se utilizan los datos generales definidos arriba. |
| **Resultado esperado** | - El sistema muestra el mensaje: **“No se encontraron conceptos”** |

---

# **Escenario D — Filtrar por Valor sin coincidencias**

| Campo | Detalle |
|-------|---------|
| **Pasos** | 1. Ejecutar el flujo base.<br>2. Ingresar **"70000"** en el campo Valor.<br>3. Seleccionar **Aplicar**. |
| **Datos de prueba** | Se utilizan los datos generales definidos arriba. |
| **Resultado esperado** | - El sistema muestra el mensaje: **“No se encontraron conceptos”** |
