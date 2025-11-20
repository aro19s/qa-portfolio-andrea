
**TEST PLAN METRÓPOLIS**

**Versión:** 1.0
**Fecha:** Noviembre de 2025
**Autor:** Andrea Sofía Ríos Olmos
**Basado en buenas prácticas ISTQB Foundation Level**


## 1. Introducción

El presente Test Plan describe el enfoque, alcance, estrategia y actividades de prueba para la aplicación **Metropolis**, una plataforma web y móvil para la administración de conjuntos residenciales en Colombia.
El objetivo es asegurar la calidad funcional, técnica y de experiencia del usuario para los roles: **Administrador (web), Residente (móvil) y Portero (móvil)**.


## 2. Objetivos de la Prueba

* Validar que las funcionalidades cumplen los requerimientos especificados.
* Detectar defectos antes de la liberación.
* Garantizar que los tres roles (Administrador, Residente y Portero) accedan únicamente a las funcionalidades correspondientes.
* Validar la integración con servicios externos (ej. pasarela de pagos).
* Asegurar que la aplicación móvil funcione correctamente en Android e iOS.
* Verificar que el flujo de negocio (reservas, PQRSDF, pagos, notificaciones) funcione de manera consistente.


## 3. Alcance de las Pruebas

### **In-Scope**

Las siguientes funcionalidades serán cubiertas:

* Administración de empleados
* Administración de anuncios
* Notificaciones push (web → app, app → app)
* Administración de propiedades
* Gestión de PQRSDF
* Pagos y conceptos de pago
* Administración de parqueaderos
* Administración de residentes
* Zonas comunes (reservas, disponibilidad, conflictos)
* Roles y control de acceso
* Pruebas mobile Android (funcionales y de notificaciones)

### **Out-of-Scope**

* Pruebas de rendimiento avanzadas (stress, load).
* Pruebas de seguridad avanzadas (penetration testing).
* Pruebas backend/API profundas (solo validaciones básicas).
* Pruebas mobile IOS.
* Automatización (solo QA manual).


## 4. Estrategia de Pruebas

El enfoque se basará en pruebas funcionales:

### **4.1 Tipos de pruebas**

* Pruebas de humo** (Smoke Test)
* Pruebas funcionales por módulo
* Pruebas de regresión
* Pruebas exploratorias
* Pruebas de control de acceso (seguridad básica)
* Pruebas de integración (pagos, notificaciones)
* Pruebas mobile en Android
* Pruebas de usabilidad

### **4.2 Técnicas de diseño ISTQB utilizadas**

* Técnica basada en requisitos
* Partición de equivalencia
* Valores límite
* Pruebas basadas en casos de uso
* Pruebas por roles


## 5. Entorno de Pruebas

### **Web**

Navegadores: Chrome (versión estable), Firefox (versión estable)
Resoluciones a probar: 1366x768 (laptop), 1920x1080 (desktop)

### **Mobile**

* Android (>= 7.0, API 24)
* Notificaciones push en ambas plataformas

### **Datos**

* Cuentas de prueba por rol
* Torres, propiedades, parqueaderos dummy
* Métodos de pago en modo sandbox (MercadoPago)


## 6. Roles y Responsabilidades

| Rol           | Responsabilidad                                                            |
| ------------- | -------------------------------------------------------------------------- |
| QA Manual     | Diseño de casos de prueba, ejecución, reporte de defectos y documentación. |
| Dev           | Corrección de defectos, despliegues, soporte técnico.                      |
| Product Owner | Aclaración de requisitos y aprobación.                                     |


## 7. Criterios de Entrada

* Build estable disponible en web y mobile.
* Accesos a roles creados.
* Requerimientos funcionales definidos.
* Entorno preparado.

## 8. Criterios de Salida

* Todos los casos críticos ejecutados y aprobados.
* Defectos críticos y altos corregidos.
* Evidencias adjuntas.
* Reporte de ejecución completado.


## 9. Riesgos

| **Riesgo**                                        | **Impacto** | **Mitigación**                                          |
|---------------------------------------------------|-------------|---------------------------------------------------------|
| Fallos en notificaciones push                     | Alto        | Pruebas en Android, validación en background            |
| Problemas con pasarela de pagos                   | Alto        | Uso de sandbox, monitoreo de logs                       |
| Errores de roles y accesos no autorizados         | Alto        | Pruebas de control de acceso exhaustivas                |
| Datos inconsistentes entre Web y App              | Alto        | Pruebas de sincronización y monitoreo de base de datos  |
| Colisiones o duplicidad en reservas               | Alto        | Pruebas de reglas de negocio y validaciones de horarios |
| Información sensible expuesta                     | Alto        | Revisiones de seguridad y pruebas negativas             |
| Flujo incorrecto de PQRSDF                        | Medio       | Pruebas de estados y notificaciones asociadas           |
| Lentitud o fallos por mala conexión a Internet    | Medio       | Pruebas con diferentes redes y manejo de errores        |
| Problemas con versiones antiguas de Android       | Medio       | Pruebas de compatibilidad                               |
| Cambios de último minuto en requisitos            | Alto        | Control de alcance y priorización de pruebas            |
| Tiempo insuficiente para regresiones              | Alto        | Uso de smoke tests y priorización por riesgo            |
| Faltan datos de prueba en el ambiente QA          | Medio       | Creación de datasets dummy y respaldo de datos          |


## 10. Cronograma Estimado

| **Actividad**                                   | **Duración estimada** |
|-------------------------------------------------|-----------------------|
| Análisis de requisitos                          | 3 días                |
| Diseño de casos de prueba                       | 8 días                |
| Preparación del entorno                         | 3 días                |
| Preparación de datos de prueba                  | 4 días                |
| Ejecución de pruebas funcionales                | 13 días               |
| Ejecución de pruebas mobile (Android)           | 8 días                |
| Pruebas de integración (pagos y notificaciones) | 6 días                |
| Pruebas de regresión                            | 6 días                |
| Pruebas exploratorias                           | 5 días                |
| Reporte final y cierre                          | 2 días                |



## 11. Herramientas

* GitHub → documentación
* Google Sheets/Excel → trazabilidad
* VSCode → notas internas
* Dispositivos móviles reales
* MercadoPago sandbox


## 12. Entregables

* Test Plan
* Casos de prueba
* Matriz de trazabilidad
* Evidencia
* Reporte de ejecución
* Reporte de defectos

