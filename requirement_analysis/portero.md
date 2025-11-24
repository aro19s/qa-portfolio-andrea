# Test Analysis – Portero

## 1. Alcance del rol

El rol PORTERO corresponde a los usuarios que acceden únicamente desde la aplicación móvil. Se permite a este rol registrar y visualizar alertas, revisar visitas, consultar avisos, revisar mantenimientos de zonas comunes y visualizar parqueaderos disponibles.

## 2. Suposiciones

* El portero tiene acceso solo a funcionalidades asignadas a su rol.
* El portero debe estar registrado previamente por el Administrador.
* Los filtros se aplican por fecha, estado u otros criterios según módulo.
* El flujo de login requiere correo y contraseña válidos.
* El portero no puede editar información de residentes ni propiedades.

## 3. Reglas de negocio aplicables

* El portero únicamente puede enviar alertas dirigidas a una sola residencia, no de forma general.
* El portero solo puede visualizar la información restringida al conjunto residencial asignado.
* El portero no puede registrar visitas; solo visualizarlas y filtrarlas.

## 4. Módulos del rol Portero

# 4.1 Login (TCN-POR-LOGIN)

## Test Conditions

| ID                 | Test Condition                                                     |
| ------------------ | ------------------------------------------------------------------ |
| TCN-POR-LOGIN-001  | Validar login exitoso con credenciales válidas                     |
| TCN-POR-LOGIN-002  | Validar error al iniciar sesión con contraseña incorrecta          |
| TCN-POR-LOGIN-003  | Validar error al iniciar sesión con correo no registrado           |
| TCN-POR-LOGIN-004  | Validar que el sistema bloquee campos vacíos                       |

---

# 4.2 Alertas (TCN-POR-ALT)

## Test Conditions

| ID                  | Test Condition                                                                |
| ------------------- | ----------------------------------------------------------------------------- |
| TCN-POR-ALT-001     | Validar creación de alerta para una residencia específica                     |
| TCN-POR-ALT-002     | Validar validación de campos obligatorios al crear alerta                     |
| TCN-POR-ALT-003     | Validar que no permita enviar alerta sin residencia seleccionada              |
| TCN-POR-ALT-004     | Validar visualización de alertas enviadas                                     |
| TCN-POR-ALT-005     | Validar aplicación de filtros                                                 |

---

# 4.3 Visitas (TCN-POR-VIS)

## Test Conditions

| ID                  | Test Condition                                                      |
| ------------------- | ------------------------------------------------------------------- |
| TCN-POR-VIS-001     | Validar visualización de visitas registradas por los residentes     |
| TCN-POR-VIS-002     | Validar acceso al detalle de una visita                             |
| TCN-POR-VIS-003     | Validar aplicación de filtros                                       |

---

# 4.4 Avisos (TCN-POR-AV)

## Test Conditions

| ID                  | Test Condition                                    |
| ------------------- | ------------------------------------------------- |
| TCN-POR-AV-001      | Validar visualización de avisos                   |
| TCN-POR-AV-002      | Validar aplicación de filtros                     |

---

# 4.5 Mantenimiento de zonas comunes (TCN-POR-MZC)

## Test Conditions

| ID                   | Test Condition                                           |
| -------------------- | -------------------------------------------------------- |
| TCN-POR-MZC-001      | Validar visualización de mantenimientos agendados        |
| TCN-POR-MZC-002      | Validar aplicación de filtros (zona, fecha, estado)      |

---

# 4.6 Parqueaderos (TCN-POR-PK)

## Test Conditions

| ID                   | Test Condition                                    |
| -------------------- | ------------------------------------------------- |
| TCN-POR-PK-001       | Validar visualización de parqueaderos disponibles |
| TCN-POR-PK-002       | Validar aplicación de filtros                     |

