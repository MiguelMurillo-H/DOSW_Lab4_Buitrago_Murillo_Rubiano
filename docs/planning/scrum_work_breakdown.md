# Planeación del Sistema

## Desglose de trabajo: Épicas, Historias de Usuario y Tareas

La implementación de los requerimientos identificados de TechCup se desglosa de la siguiente manera:

### 1. Épica:

| Campo | Descripción |
|------|-------------|
| **IDENTIFICACIÓN** | SCRUM-6 |
| **Título** | Gestión de Torneos e Inscripción de Equipos |
| **Descripción** | Permite a los organizadores crear y administrar torneos de fútbol, a los capitanes inscribir sus equipos y pagar mediante PSE, y a la Decanatura recibir los reportes de ingresos. |
| **Tenedor de apuestas** | Decanatura del programa de Ingeniería de Sistemas y Organizadores |

### 2. Historias de usuario:

| Campo | Descripción |
|------|-------------|
| **IDENTIFICACIÓN** | SCRUM-7 |
| **Título** | Creación y administración de torneos |
| **Descripción** | Como organizador del torneo quiero crear un torneo con su ID único de 5 dígitos, fechas y reglas para habilitar las inscripciones. |
| **Prioridad** | Alta |
| **Justificación de prioridad** | Es la funcionalidad base del sistema: sin poder crear y configurar un torneo, ninguna otra funcionalidad (inscripciones, pagos, reportes) puede operar. |
| **Estimación** | Pendiente |

| Campo | Descripción |
|------|-------------|
| **IDENTIFICACIÓN** | SCRUM-8 |
| **Título** | Registro de equipos en el torneo activo |
| **Descripción** | Como capitán de equipo quiero inscribir a mi equipo en el torneo activo para asegurar la participación del grupo. |
| **Prioridad** | Alta |
| **Justificación de prioridad** | Es la funcionalidad núcleo del MVP: permite que los equipos participen en el torneo, cumpliendo el objetivo principal de esta primera versión del sistema. |
| **Estimación** | Pendiente |

| Campo | Descripción |
|-------|-------------|
| **IDENTIFICACIÓN** | SCRUM-9 |
| **Título** | Pago de inscripción mediante PSE |
| **Descripción** | Como capitán de equipo quiero pagar la tarifa de inscripción mediante la pasarela PSE para completar el proceso de registro. |
| **Prioridad** | Media |
| **Justificación de prioridad** | Es necesaria para completar la inscripción, pero depende de que el torneo y el registro de equipos ya existan; puede iterarse una vez el flujo base de inscripción esté funcionando. |
| **Video** | [Ver video](https://youtu.be/MxA-YT__oT8?feature=shared) |


| Campo | Descripción |
|------|-------------|
| **IDENTIFICACIÓN** | SCRUM-10 |
| **Título** | Generación de reportes y envío a Decanatura |
| **Descripción** | Como organizador quiero generar reportes de ingresos y enviar el informe de pagos en formato JSON a la Decanatura para auditar el evento. |
| **Prioridad** | Baja |
| **Justificación de prioridad** | Es un valor agregado de auditoría y transparencia hacia la Decanatura; no bloquea el flujo operativo principal de creación de torneos e inscripción de equipos. |
| **Estimación** | Pendiente |

### 3. Tareas:

| Campo | Descripción |
|------|-------------|
| **ID** | SCRUM-12 |
| **Título** | Diseñar el modelo de datos para torneos y sus estados |
| **ID de la Historia de Usuario asociada** | SCRUM-7 |
| **Descripción** | Definir las entidades, atributos y transiciones de estado (Pending, Active, In Progress, Closed, Cancelled) necesarias para representar un torneo. |
| **Tareas requisito** | Ninguna |

| Campo | Descripción |
|------|-------------|
| **ID** | SCRUM-13 |
| **Título** | Crear la interfaz para la creación de torneos |
| **ID de la Historia de Usuario asociada** | SCRUM-7 |
| **Descripción** | Construir el formulario/endpoint que permita al organizador ingresar fechas, tarifa y reglas básicas para crear un torneo. |
| **Tareas requisito** | SCRUM-12 |

| Campo | Descripción |
|------|-------------|
| **ID** | SCRUM-14 |
| **Título** | Validar el ID único de 5 dígitos del torneo |
| **ID de la Historia de Usuario asociada** | SCRUM-7 |
| **Descripción** | Implementar la validación que genera y verifica el ID de 5 dígitos (año + semestre) y que impide duplicados o torneos activos simultáneos. |
| **Tareas requisito** | SCRUM-12 |

| Campo | Descripción |
|------|-------------|
| **ID** | SCRUM-15 |
| **Título** | Diseñar la interfaz de registro de equipos |
| **ID de la Historia de Usuario asociada** | SCRUM-8 |
| **Descripción** | Construir el formulario/endpoint que permita a un capitán crear su equipo e inscribirlo en el torneo activo. |
| **Tareas requisito** | SCRUM-13 |

| Campo | Descripción |
|------|-------------|
| **ID** | SCRUM-16 |
| **Título** | Validar estado del torneo para permitir inscripciones |
| **ID de la Historia de Usuario asociada** | SCRUM-8 |
| **Descripción** | Implementar la regla de negocio que solo permite inscribir equipos cuando el torneo está en estado Activo. |
| **Tareas requisito** | SCRUM-14 |

| Campo | Descripción |
|------|-------------|
| **ID** | SCRUM-17 |
| **Título** | Crear vista de lista de equipos inscritos |
| **ID de la Historia de Usuario asociada** | SCRUM-8 |
| **Descripción** | Construir la vista donde el organizador puede consultar todos los equipos registrados en un torneo específico. |
| **Tareas requisito** | SCRUM-15 |

| Campo | Descripción |
|------|-------------|
| **ID** | SCRUM-18 |
| **Título** | Integrar la pasarela de pagos PSE |
| **ID de la Historia de Usuario asociada** | SCRUM-9 |
| **Descripción** | Conectar el sistema con la pasarela de pagos PSE para procesar el pago de la tarifa de inscripción de un equipo. |
| **Tareas requisito** | SCRUM-15 |

| Campo | Descripción |
|------|-------------|
| **ID** | SCRUM-19 |
| **Título** | Crear módulo de verificación de pagos |
| **ID de la Historia de Usuario asociada** | SCRUM-9 |
| **Descripción** | Implementar la funcionalidad que permite al organizador consultar y validar el estado del pago asociado a la inscripción de un equipo. |
| **Tareas requisito** | SCRUM-18 |

| Campo | Descripción |
|------|-------------|
| **ID** | SCRUM-20 |
| **Título** | Notificaciones de confirmación de pago |
| **ID de la Historia de Usuario asociada** | SCRUM-9 |
| **Descripción** | Enviar una notificación al capitán confirmando que el pago de inscripción fue recibido y validado. |
| **Tareas requisito** | SCRUM-19 |

| Campo | Descripción |
|------|-------------|
| **ID** | SCRUM-21 |
| **Título** | Desarrollar lógica para reporte de ingresos |
| **ID de la Historia de Usuario asociada** | SCRUM-10 |
| **Descripción** | Implementar el cálculo de los ingresos totales obtenidos por concepto de tarifas de inscripción para un torneo. |
| **Tareas requisito** | SCRUM-19 |

| Campo | Descripción |
|------|-------------|
| **ID** | SCRUM-22 |
| **Título** | Formatear reporte de inscripciones en formato JSON |
| **ID de la Historia de Usuario asociada** | SCRUM-10 |
| **Descripción** | Estructurar el reporte de equipos inscritos y pagos en formato JSON según lo requerido por la Decanatura. |
| **Tareas requisito** | SCRUM-21 |

| Campo | Descripción |
|------|-------------|
| **ID** | SCRUM-23 |
| **Título** | Implementar servicio de envío a Decanatura |
| **ID de la Historia de Usuario asociada** | SCRUM-10 |
| **Descripción** | Construir el servicio que envía el reporte JSON de inscripciones y pagos a la Decanatura de forma automática. |
| **Tareas requisito** | SCRUM-22 |


