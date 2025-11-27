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



### **Datos de prueba generales**

Conceptos de pago disponibles para el residente:

| Título               | Descripción        | Valor   |
|----------------------|--------------------|---------|
| Administración       | Pago mensual       | 120000  |
| Parqueadero          | Cuota mensual      | 80000   |
| Aseo                 | Servicio de aseo   | 40000   |
| Extra mantenimiento  | Servicio técnico   | 150000  |



***Flujo base (común para todos los escenarios):***
1. Abrir la app móvil.
2. Ingresar con un residente registrado.
3. Navegar al módulo Pagos.
4. Seleccionar el botón "Pagar".
5. Seleccionar el ícono de filtros.



### **Escenario A — Filtrar por Título con coincidencias**

| Campo | Detalle |
|-------|---------|
| **Pasos** | 1. Ejecutar el flujo base.<br>2. Ingresar "Administración" en el campo Título.<br>3. Seleccionar Aplicar. |
| **Datos de prueba** | Se utilizan los datos generales definidos arriba. |
| **Resultado esperado** | - El sistema muestra únicamente el concepto:<br>Administración / Pago mensual / 120000 |



### **Escenario B — Filtrar por Valor con coincidencias**

| Campo | Detalle |
|-------|---------|
| **Pasos** | 1. Ejecutar el flujo base.<br>2. Ingresar "80000" en el campo Valor.<br>3. Seleccionar Aplicar. |
| **Datos de prueba** | Se utilizan los datos generales definidos arriba. |
| **Resultado esperado** | - El sistema muestra únicamente el concepto:<br> • Parqueadero / Cuota mensual / 80000 |



### **Escenario C — Filtrar por Título sin coincidencias**

| Campo | Detalle |
|-------|---------|
| **Pasos** | 1. Ejecutar el flujo base.<br>2. Ingresar "Multa" en el campo Título.<br>3. Seleccionar Aplicar. |
| **Datos de prueba** | Se utilizan los datos generales definidos arriba. |
| **Resultado esperado** | - El sistema muestra el mensaje: “No se encontraron conceptos” |



### **Escenario D — Filtrar por Valor sin coincidencias**

| Campo | Detalle |
|-------|---------|
| **Pasos** | 1. Ejecutar el flujo base.<br>2. Ingresar "70000" en el campo Valor.<br>3. Seleccionar Aplicar. |
| **Datos de prueba** | Se utilizan los datos generales definidos arriba. |
| **Resultado esperado** | - El sistema muestra el mensaje: “No se encontraron conceptos” |

---

## **Validar visualización del historial de pagos realizados**

| Campo                 | Detalle |
|----------------------|---------|
| **ID**                | TC-RES-PAG-002 |
| **Test Condition**    | TCN-RES-PAG-002 |
| **Título**            | Visualización del historial de pagos realizados |
| **Precondiciones**    | - El residente tiene pagos realizados registrados en el sistema. |
| **Pasos**             | 1. Abrir la app móvil.<br>2. Ingresar a la app con un residente registrado.<br>3. Navegar al módulo Pagos. |
| **Datos de prueba**   | Pagos realizados por el residente. |
| **Resultado esperado**| - El sistema muestra la lista completa de pagos realizados por el residente y la inormación correspondiente. |
| **Postcondiciones**   | Ninguna. |

---

## **Validar redirección correcta hacia Mercado Pago**

| Campo                 | Detalle |
|----------------------|---------|
| **ID**                | TC-RES-PAG-004 |
| **Test Condition**    | TCN-RES-PAG-004 |
| **Título**            | Redirección hacia Mercado Pago con parámetros correctos |
| **Precondiciones**    | - El residente tiene al menos un concepto de pago pendiente.<br>- La app está conectada a la pasarela de pagos de Mercado Pago. |
| **Pasos**             | 1. Abrir la app móvil.<br>2. Ingresar a la app con un residente registrado.<br>3. Navegar al módulo Pagos.<br>4. Seleccionar "Pagar"<br>5. Seleccionar "Pagar" en un concepto pendiente.<br>6. Verificar que la app abra la pasarela de Mercado Pago. |
| **Datos de prueba**   | Concepto de pago pendiente:<br>- Título: Administración<br>- Valor: 120000 |
| **Resultado esperado**| - La app redirige correctamente hacia Mercado Pago.<br>- Los parámetros enviados son correctos (Los parámetros se verifican al finalizar la compra, donde Mercado Pago los hace visibles.) |
| **Postcondiciones**   | Mercado Pago queda abierto para que el usuario finalice el pago. |

> Para realizar el proceso en la pasarela, se utilizarán los datos de tarjetas de prueba proporcionados por Mercado Pago para ambientes sandbox.

---

## **Validar pago exitoso aprobado por Mercado Pago**

| Campo                 | Detalle |
|----------------------|---------|
| **ID**                | TC-RES-PAG-005 |
| **Test Condition**    | TCN-RES-PAG-005 |
| **Título**            | Pago exitoso: registro, confirmación y actualización de estado |
| **Precondiciones**    | - El residente tiene al menos un concepto de pago pendiente.<br>- La app está conectada a la pasarela de pagos de Mercado Pago. |
| **Pasos**             | 1. Abrir la app móvil.<br>2. Ingresar a la app con un residente registrado.<br>3. Navegar al módulo Pagos.<br>4. Seleccionar "Pagar"<br>5. Seleccionar "Pagar" en un concepto pendiente.<br>6. Completar el pago en Mercado Pago con un método aprobado.<br>7. Retornar manualmente al módulo Pagos. |
| **Datos de prueba**   | Concepto:<br>- Aseo — 40.000 |
| **Resultado esperado**| - El sistema registra el pago con estado Aprobado.<br>- El concepto pagado ya no aparece como “Pendiente”.<br>- El pago se refleja en el Historial de Pagos. |
| **Postcondiciones**   | El concepto queda marcado como Pagado y se mantiene el registro en el historial. |

---

## **Validar manejo de pago pendiente**

| Campo                 | Detalle |
|----------------------|---------|
| **ID**                | TC-RES-PAG-006 |
| **Test Condition**    | TCN-RES-PAG-006 |
| **Título**            | Pago pendiente: mensaje, registro y restricción de reintento |
| **Precondiciones**    | - El residente tiene al menos un concepto de pago pendiente.<br>- La app está conectada a la pasarela de pagos de Mercado Pago. |
| **Pasos**             | 1. Abrir la app móvil.<br>2. Ingresar a la app con un residente registrado.<br>3. Navegar al módulo Pagos.<br>4. Seleccionar "Pagar"<br>5. Seleccionar "Pagar" en un concepto pendiente.<br>Completar el pago en Mercado Pago usando un método que devuelva estado Pending. |
| **Datos de prueba**   | Concepto:<br>- Extra mantenimiento — 150000 |
| **Resultado esperado**| - El sistema registra el pago con estado Pendiente.<br>- No se permite realizar un nuevo intento inmediato de pago para ese concepto.<br>- El pago aparecerá en el historial de pagos con estado Pendiente. |
| **Postcondiciones**   | - El pago queda en estado Pendiente hasta recibir actualización de Mercado Pago. |

---

## **Validar manejo de pago rechazado**

| Campo                 | Detalle |
|----------------------|---------|
| **ID**                | TC-RES-PAG-007 |
| **Test Condition**    | TCN-RES-PAG-007 |
| **Título**            | Pago rechazado: mensaje, registro y disponibilidad de reintento |
| **Precondiciones**    | - El residente tiene al menos un concepto de pago pendiente.<br>- La app está conectada a la pasarela de pagos de Mercado Pago.<br>- Mercado Pago cuenta con un método de pago de prueba configurado para devolver estado Rejected. |
| **Pasos**             | 1. Abrir la app móvil.<br>2. Ingresar a la app con un residente registrado.<br>3. Navegar al módulo Pagos.<br>4. Seleccionar “Pagar”.<br>5. Seleccionar un concepto de pago pendiente.<br>6. Completar el proceso de pago en Mercado Pago.<br>7. Regresar a la app. |
| **Datos de prueba**   | Concepto:<br>- Parqueadero — 80.000 |
| **Resultado esperado**| - El sistema registra el intento con estado Rechazado (internamente).<br>- El concepto de pago continúa en estado “Pendiente”.<br>- Se habilita el botón “Borrar pago”.<br>- El usuario puede volver a intentar el pago. |
| **Postcondiciones**   | El concepto permanece en estado Pendiente hasta que el usuario lo elimine y realice un nuevo pago. |

---

## **Manejo de errores cuando Mercado Pago no responde**

### Información General

| Campo                 | Detalle |
|---------------------- |---------|
| **ID**                | TC-RES-PAG-010 |
| **Test Condition**    | TCN-RES-PAG-010 |
| **Título**            | Manejo de errores en Mercado Pago |
| **Precondiciones**    | - El usuario tiene al menos un concepto de pago disponible.<br>- Conexión simulada para forzar error por Mercado Pago. |
| **Pasos**             | 1. Abrir la app móvil.<br>2. Ingresar a la app con un residente registrado.<br>3. Navegar al módulo Pagos.<br>4. Seleccionar “Pagar”.<br>5. Seleccionar un concepto de pago pendiente.<br>6. Forzar una condición donde Mercado Pago no responda. |
| **Datos de prueba**   | - Concepto:<br>- Parqueadero — 80.000 |
| **Resultado esperado**| - La app detecta que Mercado Pago no respondió.<br>- El usuario retorna a la pantalla de pagos sin que la app se bloquee.<br>- Se muestra mensaje de error o estado de pago no completado. |
| **Postcondiciones**   | - El pago queda en estado pendiente.<br>- Se habilita la opción de borrar el pago. |

---
