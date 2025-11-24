# Test Analysis – Residente

## 1. Alcance del rol

El rol RESIDENTE corresponde a los usuarios que acceden únicamente desde la aplicación móvil. A este rol se le permite realizar operaciones relacionadas con pagos, PQRSDF, zonas comunes, visitantes, notificaciones, avisos, parqueaderos y módulos informativos.

## 2. Suposiciones

* El residente tiene acceso solo a funcionalidades asignadas a su rol.
* El residente debe estar registrado previamente por el Administrador.
* El residente solo ve información del conjunto al que pertenece.
* Los filtros se aplican por fecha, estado u otros criterios según el módulo.
* El flujo de login requiere correo y contraseña válidos.

## 3. Reglas de negocio aplicables

* Un residente no puede reserva una zona común que no requiere reserva.
* Los avisos vistos por el residente son generales, creados por el administrador.
* El residente solo puede eliminar sus propias publicaciones en Objetos Perdidos.
* El residente solo puede visualizar parqueaderos y solicitudes asociadas a su propiedad.

## 4. Módulos: Residente

# 4.1 Login (TCN-RES-LOGIN)

## Test Conditions

| ID                | Test Condition                                                     |
| ----------------- | ------------------------------------------------------------------ |
| TCN-RES-LOGIN-001 | Validar login exitoso con credenciales válidas                     |
| TCN-RES-LOGIN-002 | Validar error al intentar iniciar sesión con contraseña incorrecta |
| TCN-RES-LOGIN-003 | Validar error al intentar iniciar sesión con correo no registrado  |
| TCN-RES-LOGIN-004 | Validar que el sistema bloquee campos vacíos                       |

---

# 4.2 Pagos (TCN-RES-PAG)

## Test Conditions

| ID              | Test Condition                                              |
| --------------- | ----------------------------------------------------------- |
| TCN-RES-PAG-001 | Validar visualización de pagos asociados al residente       |
| TCN-RES-PAG-002 | Validar aplicación correcta de filtros de búsqueda          |
| TCN-RES-PAG-003 | Validar registro de un nuevo pago                           |
| TCN-RES-PAG-004 | Validar validación de campos obligatorios al registrar pago |
| TCN-RES-PAG-005 | Validar que solo se muestren conceptos de pago asignados    |

---

# 4.3 PQRSDF (TCN-RES-PQ)

## Test Conditions

| ID             | Test Condition                                  |
| -------------- | ----------------------------------------------- |
| TCN-RES-PQ-001 | Validar registro de nueva PQRSDF                |
| TCN-RES-PQ-002 | Validar filtrado por estado, fecha y tipo       |
| TCN-RES-PQ-003 | Validar visualización de PQRSDF propias         |
| TCN-RES-PQ-004 | Validar visualización del seguimiento/respuesta |

---

# 4.4 Portería (Visitantes) (TCN-RES-VIS)

## Test Conditions

| ID              | Test Condition                                  |
| --------------- | ----------------------------------------------- |
| TCN-RES-VIS-001 | Validar registro de visitante                   |
| TCN-RES-VIS-002 | Validar visualización de visitantes registrados |
| TCN-RES-VIS-003 | Validar aplicación de filtros                   |

---

# 4.5 Zonas comunes (TCN-RES-ZC)

## Test Conditions

| ID             | Test Condition                                                     |
| -------------- | ------------------------------------------------------------------ |
| TCN-RES-ZC-001 | Validar visualización de zonas comunes disponibles                 |
| TCN-RES-ZC-002 | Validar creación de reservas                                       |
| TCN-RES-ZC-003 | Validar aplicación de filtros                                      |
| TCN-RES-ZC-004 | Validar restricción: no reservar zonas que no necesiten reserva    |
| TCN-RES-ZC-005 | Validar que no se pueda reservar en horarios ocupados              |

---

# 4.6 Avisos (TCN-RES-AV)

## Test Conditions

| ID             | Test Condition                          |
| -------------- | --------------------------------------- |
| TCN-RES-AV-001 | Validar visualización de avisos general |
| TCN-RES-AV-002 | Validar aplicación de filtros           |

---

# 4.7 Parqueaderos (TCN-RES-PK)

## Test Conditions

| ID             | Test Condition                                    |
| -------------- | ------------------------------------------------- |
| TCN-RES-PK-001 | Validar visualización de parqueaderos disponibles |
| TCN-RES-PK-002 | Validar registro de solicitud                     |
| TCN-RES-PK-003 | Validar aplicación de filtros                     |

---

# 4.8 Cambio de contraseña (TCN-RES-CC)

## Test Conditions

| ID             | Test Condition                                    |
| -------------- | ------------------------------------------------- |
| TCN-RES-CC-001 | Validar cambio exitoso de contraseña              |
| TCN-RES-CC-002 | Validar error si la contraseña actual no coincide |
| TCN-RES-CC-003 | Validar validación de contraseñas débiles         |

---

# 4.9 Historial de notificaciones (TCN-RES-NOT)

## Test Conditions

| ID              | Test Condition                        |
| --------------- | ------------------------------------- |
| TCN-RES-NOT-001 | Validar visualización del historial   |
| TCN-RES-NOT-002 | Validar filtrado de notificaciones    |
| TCN-RES-NOT-003 | Validar eliminación de notificaciones |

---

# 4.10 Objetos perdidos (TCN-RES-OBJG - TCN-RES-OBJP)

## Test Conditions – Módulo General

| ID               | Test Condition                                        |
| ---------------- | ----------------------------------------------------- |
| TCN-RES-OBJG-001 | Validar visualización de objetos publicados por otros |
| TCN-RES-OBJG-002 | Validar aplicación de filtros                         |

## Test Conditions – Módulo Propias

| ID               | Test Condition                           |
| ---------------- | ---------------------------------------- |
| TCN-RES-OBJP-001 | Validar visualización de objetos propios |
| TCN-RES-OBJP-002 | Validar eliminación de objetos propios   |


