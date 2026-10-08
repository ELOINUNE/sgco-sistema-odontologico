# SGCO — Sistema de Gestión para Centro Odontológico

## Descripción

El SGCO es una plataforma digital para apoyar la operación diaria de un centro odontológico: registro y consulta de pacientes, programación y seguimiento de citas, historial clínico con odontograma digital, facturación de tratamientos y generación de reportes de actividad.

Proyecto desarrollado como trabajo de la asignatura **Ingeniería de Software I** (sección ISW-201), Universidad Abierta Para Adultos (UAPA), a partir del sistema trabajado previamente en la asignatura Diseño de Interfaz de Usuario.

## Metodología

Desarrollo organizado bajo un enfoque ágil con tablero **Kanban**, gestionado en GitHub Projects, dado que el sistema está compuesto por módulos funcionalmente independientes que se desarrollan e incorporan de forma incremental.

## Módulos principales

- Registro y gestión de pacientes
- Agenda y gestión de citas
- Historial clínico y odontograma
- Facturación y pagos
- Notificaciones y recordatorios
- Reportes y estadísticas

## Arquitectura

Arquitectura en capas (Presentación / Aplicación / Persistencia) con el patrón MVC aplicado en el frontend, separando interfaz, lógica de negocio y base de datos.

## Organización Frontend / Backend

El sistema se organiza en dos grandes bloques que se comunican entre sí mediante peticiones de datos (API):

**Frontend (capa de Presentación)**
- Responsable de mostrar la agenda, el historial clínico, la facturación y los reportes al usuario (recepcionista, odontólogo, paciente o administrador).
- Captura las acciones del usuario (agendar una cita, registrar un tratamiento, consultar una factura) y las envía al backend.
- No contiene lógica de negocio: solo presenta datos y valida el formato básico de los formularios antes de enviarlos.

**Backend (capas de Aplicación y Persistencia)**
- **Autenticación:** gestiona el inicio de sesión y valida el rol de cada usuario antes de autorizar una acción.
- **Lógica de Negocio:** procesa las reglas del sistema — validar disponibilidad de horario antes de agendar, calcular el estado de una factura, generar reportes — y es el único punto de acceso a la Base de Datos.
- **Servicios:** ejecuta tareas de apoyo como el envío de recordatorios automáticos y la generación de reportes.
- **Base de Datos:** almacena de forma centralizada pacientes, citas, historiales clínicos, facturas y empleados.

**Comunicación:** el frontend solicita y envía datos al backend mediante peticiones HTTP (API REST); el backend responde con los datos procesados o con la confirmación de la acción, sin que el frontend acceda nunca directamente a la base de datos.

## Herramientas utilizadas

- **GitHub Projects** — tablero Kanban y seguimiento de tareas
- **GitHub Issues** — registro de historias de usuario, requisitos y tareas técnicas
- **Visual Paradigm Online** (modo VPasCode / PlantUML) — modelado UML y diagrama arquitectónico

## Estado del proyecto

Versión actual: **v1.0 — Cierre de fase de organización técnica.** Planificación, especificación de requisitos, modelado UML y diseño arquitectónico completados; implementación de módulos en curso. Ver el tablero de [GitHub Projects](https://github.com/users/ELOINUNE/projects) del repositorio para el estado actual de cada tarea, y la sección de [Issues](https://github.com/ELOINUNE/sgco-sistema-odontologico/issues) para el seguimiento de incidencias y tareas pendientes.

## Registro de cambios

| Fecha | Cambio |
|---|---|
| Sep 2026 | Definición de requisitos funcionales y no funcionales (RF-01 a RF-05, RNF-01, RNF-02). |
| Sep 2026 | Elaboración de los 4 diagramas UML (casos de uso, clases, secuencia, actividades) en Visual Paradigm Online. |
| Sep 2026 | Diseño de la arquitectura en capas con patrón MVC y diagrama de componentes. |
| Oct 2026 | Organización del tablero técnico en GitHub Projects con 22+ tareas clasificadas por tipo, prioridad y responsable. |
| Oct 2026 | Publicación del repositorio y del tablero en modo público, y documentación de la organización frontend/backend en este README. |

## Autor

Abraham Cabral Morffe — Matrícula 100090630
