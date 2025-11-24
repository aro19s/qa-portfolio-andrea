# Test Analysis – Administrador

## 1. Alcance del rol

El rol Administrador corresponde a usuarios que acceden únicamente desde la aplicación web.
A este rol se le permite gestionar estadísticas, zonas comunes, unidad residencial, empleados, anuncios, notificaciones, propiedades, PQRSDF, conceptos de pago, parqueaderos, residentes, objetos perdidos y permite cambiar su contraseña.

## 2. Suposiciones

- El administrador debe haber sido creado previamente por un superadministrador.
- El administrador solo tiene acceso a su conjunto asignado.
- Los módulos web están optimizados para desktop.
- Los filtros disponibles varían por módulo (fecha, estado, tipo, usuario, etc.).
- Los gráficos del dashboard consumen datos actuales y filtrables.

## 3. Reglas de negocio aplicables

- El administrador no puede gestionar otros conjuntos residenciales diferentes al suyo.
- Para aprobar o rechazar solicitudes, debe existir un registro previo creado por un residente.
- Las notificaciones pueden ser enviadas de forma general o dirigidas a propiedades específicas.
- Eliminaciones requieren confirmaciones.
- Algunos módulos tienen dependencias entre ellos.

---

# 4. Módulos del rol Administrador

---

# 4.1 Login (TCN-ADM-LOGIN)

## Test Conditions

| ID                | Test Condition                                                     |
| ----------------- | ------------------------------------------------------------------ |
| TCN-ADM-LOGIN-001 | Validar login exitoso con credenciales válidas                     |
| TCN-ADM-LOGIN-002 | Validar error al intentar iniciar sesión con contraseña incorrecta |
| TCN-ADM-LOGIN-003 | Validar error al intentar iniciar sesión con correo no registrado  |
| TCN-ADM-LOGIN-004 | Validar que el sistema bloquee campos vacíos                       |


# 4.2 Dashboard (TCN-ADM-DB)

## Test Conditions

| ID                      | Test Condition                                                                          |
| ----------------------- | --------------------------------------------------------------------------------------- |
| TCN-ADM-DB-001          | Validar visualización del dashboard con estadísticas generales                          |
| TCN-ADM-DB-002          | Validar filtrado por períodos: diario, semanal, mensual                                 |
| TCN-ADM-DB-003          | Validar manejo de ausencia de datos (gráficos vacíos o mensajes informativos)           |

---

# 4.3 Zonas Comunes (TCN-ADM-ZC-ADM)

## 4.3.1 Administrar Zonas Comunes

| ID                           | Test Condition                                                          |
| ---------------------------- | ----------------------------------------------------------------------- |
| TCN-ADM-ZC-ADM-001           | Validar creación de zona común                                          |
| TCN-ADM-ZC-ADM-002           | Validar edición de zona común existente                                 |
| TCN-ADM-ZC-ADM-003           | Validar eliminación de zona común                                       |
| TCN-ADM-ZC-ADM-004           | Validar visualización y filtrado de zonas comunes                       |
| TCN-ADM-ZC-ADM-005           | Validar campos obligatorios                                             |

## 4.3.2 Solicitudes de Zonas Comunes (TCN-ADM-ZC-SOL)

| ID                           | Test Condition                                                          |
| ---------------------------- | ----------------------------------------------------------------------- |
| TCN-ADM-ZC-SOL-001           | Validar visualización de solicitudes de zonas comunes                   |
| TCN-ADM-ZC-SOL-002           | Validar filtrado de solicitudes                                         |
| TCN-ADM-ZC-SOL-003           | Validar aprobación de solicitud                                         |
| TCN-ADM-ZC-SOL-004           | Validar rechazo de solicitud                                            |
| TCN-ADM-ZC-SOL-005           | Validar acceso al detalle de la solicitud                               |

---

# 4.4 Unidad Residencial (TCN-ADM-UR)

| ID                      | Test Condition                                         |
| ----------------------- | ------------------------------------------------------ |
| TCN-ADM-UR-001          | Validar visualización de unidades residenciales        |
| TCN-ADM-UR-002          | Validar edición de datos de la unidad residencial      |

---

# 4.5 Empleados (TCN-ADM-EMP)

| ID                      | Test Condition                                                     |
| ----------------------- | ------------------------------------------------------------------ |
| TCN-ADM-EMP-001         | Validar visualización de empleados                                 |
| TCN-ADM-EMP-002         | Validar filtrado de empleados                                      |
| TCN-ADM-EMP-003         | Validar creación de empleado                                       |
| TCN-ADM-EMP-004         | Validar edición de información de empleado                         |
| TCN-ADM-EMP-005         | Validar eliminación de empleado                                    |

---

# 4.6 Anuncios (TCN-ADM-AN)

| ID                      | Test Condition                                    |
| ----------------------- | ------------------------------------------------- |
| TCN-ADM-AN-001          | Validar creación de anuncio                       |
| TCN-ADM-AN-002          | Validar visualización y filtrado de anuncios      |
| TCN-ADM-AN-003          | Validar edición de anuncio                        |
| TCN-ADM-AN-004          | Validar eliminación de anuncio                    |

---

# 4.7 Notificaciones (TCN-ADM-NOT)

| ID                      | Test Condition                                                               |
| ----------------------- | ---------------------------------------------------------------------------- |
| TCN-ADM-NOT-001         | Validar creación de notificación general                                     |
| TCN-ADM-NOT-002         | Validar creación de notificación dirigida a propiedades específicas          |
| TCN-ADM-NOT-003         | Validar visualización y filtrado de notificaciones                           |
| TCN-ADM-NOT-004         | Validar edición de notificación                                              |
| TCN-ADM-NOT-005         | Validar eliminación de notificación                                          |

---

# 4.8 Propiedades (TCN-ADM-PROP)

| ID                      | Test Condition                                  |
| ----------------------- | ----------------------------------------------- |
| TCN-ADM-PROP-001        | Validar creación de propiedad                   |
| TCN-ADM-PROP-002        | Validar visualización y filtrado de propiedades |
| TCN-ADM-PROP-003        | Validar edición de propiedad                    |
| TCN-ADM-PROP-004        | Validar eliminación de propiedad                |

---

# 4.9 PQRSDF (TCN-ADM-PQ)

| ID                      | Test Condition                                                              |
| ----------------------- | --------------------------------------------------------------------------- |
| TCN-ADM-PQ-001          | Validar visualización de PQRSDF                                             |
| TCN-ADM-PQ-002          | Validar filtrado de PQRSDF                                                  |
| TCN-ADM-PQ-003          | Validar acceso al detalle de una solicitud                                  |
| TCN-ADM-PQ-004          | Validar respuesta a PQRSDF                                                  |

---

# 4.10 Conceptos de Pago (TCN-ADM-CP)

| ID                      | Test Condition                                                         |
| ----------------------- | ---------------------------------------------------------------------- |
| TCN-ADM-CP-001          | Validar creación de concepto de pago global                            |
| TCN-ADM-CP-002          | Validar creación de concepto de pago específico por residente          |
| TCN-ADM-CP-003          | Validar visualización de conceptos de pago                             |
| TCN-ADM-CP-004          | Validar eliminación de concepto                                        |

---

# 4.11 Parqueaderos (TCN-ADM-PK)

| ID                      | Test Condition                                        |
| ----------------------- | ----------------------------------------------------- |
| TCN-ADM-PK-001          | Validar creación de parqueadero                       |
| TCN-ADM-PK-002          | Validar visualización y filtrado                      |
| TCN-ADM-PK-003          | Validar edición de parqueadero                        |
| TCN-ADM-PK-004          | Validar eliminación de parqueadero                    |

---

# 4.12 Residentes (TCN-ADM-RES)

| ID                      | Test Condition                                        |
| ----------------------- | ----------------------------------------------------- |
| TCN-ADM-RES-001         | Validar creación de residente                         |
| TCN-ADM-RES-002         | Validar visualización y filtrado                      |
| TCN-ADM-RES-003         | Validar edición de residente                          |
| TCN-ADM-RES-004         | Validar eliminación de residente                      |

---

# 4.13 Objetos Perdidos (TCN-ADM-OBJ)

| ID                      | Test Condition                                            |
| ----------------------- | --------------------------------------------------------- |
| TCN-ADM-OBJ-001         | Validar creación de objeto perdido                        |
| TCN-ADM-OBJ-002         | Validar visualización y filtrado de objetos perdidos      |
| TCN-ADM-OBJ-003         | Validar edición de objeto perdido                         |
| TCN-ADM-OBJ-004         | Validar eliminación de objeto perdido                     |

---

# 4.14 Cambiar Contraseña (TCN-ADM-CC)

| ID                      | Test Condition                                          |
| ----------------------- | ------------------------------------------------------- |
| TCN-ADM-CC-001          | Validar cambio exitoso de contraseña                    |
| TCN-ADM-CC-002          | Validar error por contraseña actual incorrecta          |
| TCN-ADM-CC-003          | Validar validaciones de campo (mínimo caracteres, etc.) |

