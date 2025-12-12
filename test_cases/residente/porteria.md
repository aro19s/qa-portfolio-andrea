# Portería (visitantes) – Test Cases – TCN-RES-VIS

---

## **Validar registro de visitante con campos correctos**

| Campo                 | Detalle |
|-------                |---------|
| **ID**                | TC-RES-VIS-001 |
| **Test Condition**    | TCN-RES-VIS-001 |
| **Título**            | Registro de visitantes con campos válidos |
| **Precondiciones**    | - El residente debe estar logueado en el sistema  |
| **Pasos**             | 1. Abrir la app móvil.<br>2. Acceder al módulo "Portería".<br>3. Seleccionar "Crear".<br>4. Rellenar los campos con información válida.<br>5. Seleccionar "Aceptar". |
| **Datos de prueba**   | Nombres: Andrea<br>Apellidos: Lopez<br>Tipo de Identificación: Cédula de Ciudadanía<br>N° Identificación: 1121458789<br>Teléfono: 3201598654<br>Fecha de Entrada: 30/12/2025, 15:00<br>Fecha de Salida: 31/12/2025, 15:00 |
| **Resultado esperado**| - El sistema permite el registro del visitante. |
| **Postcondiciones**   | - El visitante queda registrado en el sistema y mostrado en lista. |

---

## **Validar error al intentar registrar visitante con campos inválidos o incompletos**

| Campo                 | Detalle |
|---------------------- |---------|
| **ID**                | TC-RES-VIS-002 |
| **Test Condition**    | TCN-RES-VIS-002 |
| **Título**            | Error al intentar registrar visitante con campos obligatorios vacíos |
| **Precondiciones**    | - El residente debe estar logueado en el sistema. |
| **Pasos**             | 1. Abrir la app móvil.<br>2. Acceder al módulo "Portería".<br>3. Seleccionar "Crear".<br>4. Dejar todos los campos obligatorios vacíos, excepto las fechas (vienen por defecto).<br>5. Seleccionar "Aceptar". |
| **Datos de prueba**   | Nombres: -<br>Apellidos: -<br>Tipo de Identificación: -<br>N° Identificación: -<br>Teléfono: -<br>Fecha de Entrada: *valor por defecto*<br>Fecha de Salida: *valor por defecto* |
| **Resultado esperado**| - El sistema muestra mensajes de error en los campos obligatorios.<br>- No permite continuar con el registro. |
| **Postcondiciones**   | - El residente permanece en el formulario |

## **Registro de visitante con horas en el pasado con respecto a la hora actual**

| Campo                | Detalle |
|----------------------|---------|
| **ID**               | TC-RES-VIS-003 |
| **Test Condition**   | TCN-RES-VIS-002 |
| **Título**           | Registro de visitante con horas en el pasado |
| **Precondiciones**   | - El residente debe estar logueado en el sistema. |
| **Pasos**            | 1. Abrir la app móvil.<br>2. Acceder al módulo "Portería".<br>3. Seleccionar "Crear".<br>4. Ingresar horas de entrada y salida que ya pasaron respecto a la hora actual.<br>5. Seleccionar "Aceptar". |
| **Datos de prueba**  | Hora actual del sistema: 19:00 <br>Hora Entrada: 9:00 <br>Hora Salida: 17:00 <br>Resto de campos válidos |
| **Resultado esperado** | - El sistema debe mostrar mensaje indicando que no es posible registrar un visitante con una hora ya pasada.
| **Postcondiciones**  | - El residente permanece en el formulario |

## **Validar longitud del número de identificación**

| Campo                 | Detalle |
|----------------------|---------|
| **ID**               | TC-RES-VIS-004 |
| **Test Condition**   | TCN-RES-VIS-002 |
| **Título**           | Validar longitud mínima y máxima del número de identificación |
| **Precondiciones**   | - El residente debe estar logueado en el sistema. |
| **Pasos**            | 1. Abrir la app móvil.<br>2. Acceder al módulo "Portería".<br>3. Seleccionar "Crear".<br>4. Ingresar el valor "N° de Identificación" según el la tabla de datos a continuación.<br>5. Completar los demás campos con datos válidos.<br>6. Seleccionar "Aceptar". |
| **Datos de prueba**   | Indicados en la tabla de datos. |
| **Resultado esperado** | - Conjuntos de datos inválidos: el sistema debe mostrar un mensaje indicando que la longitud del número de identificación no es válida.<br>- Conjuntos de datos válidos: el sistema permite continuar con el registro. |
| **Postcondiciones** | - Valores válidos: el visitante queda registrado y aparece en la lista.<br>- Valores inválidos, no se crea el registro y el usuario permanece en el formulario. |


| ID | N° Identificación                  | Validez | Notas |
|----------|------------------------------------|---------|-------|
| 1  | 10064587 (8 dígitos)               | Inválido | Menor al mínimo permitido (9) |
| 2  | 100645879 (9 dígitos)              | Válido   | Límite inferior válido |
| 3  | 100645879142536 (15 dígitos)       | Válido   | Límite superior válido |
| 4  | 1006458791425368 (16 dígitos)      | Inválido | Mayor al máximo permitido (15) |

---

## **Validar filtrado**

### Información General

| Campo                 | Detalle |
|-----------------------|---------|
| **ID**                | TC-RES-VIS-005 |
| **Test Condition**    | TCN-RES-VIS-006 |
| **Título**            | Validación de filtros de visitantes usando combinaciones de pares |
| **Precondiciones**    | - El usuario tiene visitantes registrados con diferentes nombres, apellidos  |
| **Pasos**             | 1. Abrir la app.<br>2. Ingresar al módulo PQRSDF.<br>3. Seleccionar el ícono de filtros.<br>4. Aplicar los filtros según la combinación de datos. |
| **Datos de prueba**   | Ver tabla de datos a continuación |
| **Resultado esperado**| - La lista muestra únicamente los PQRSDFs que cumplen con la combinación de filtros aplicada.|
| **Postcondiciones**   | Ninguna. |


## Tabla de Datos

| ID| Nombre | Documento | Teléfono | Rango de Fechas      |
|---|--------|-----------|----------|----------------------|
| 1 | Vacío  | Vacío     | Vacío    | Rango invertido      |
| 2 | Lleno  | Lleno     | Vacío    | Sin rango            |
| 3 | Vacío  | Lleno     | Lleno    | Rango válido         |
| 4 | Lleno  | Lleno     | Lleno    | Rango invertido      |
| 5 | Lleno  | Vacío     | Vacío    | Rango válido         |
| 6 | Vacío  | Vacío     | Lleno    | Sin rango            |
