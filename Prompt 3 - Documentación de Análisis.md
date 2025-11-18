##  Prompt 3 - Documentación de Análisis

Crea un análisis detallado para la primera versión de un ATS. Incluye objetivos del producto, alcance funcional, restricciones técnicas, y criterios de éxito. Presenta un mapa de stakeholders y sus necesidades principales. Prioriza funcionalidades usando MoSCoW (Must, Should, Could, Won’t).
***
Aquí tienes un análisis detallado para la **primera versión de un ATS**:
***

## ✅ **1. Objetivos del Producto**

*   **Optimizar el proceso de reclutamiento** reduciendo tiempo y esfuerzo manual.
*   **Mejorar la experiencia del candidato** con procesos simples y transparentes.
*   **Facilitar la colaboración interna** entre reclutadores y managers.
*   **Garantizar cumplimiento normativo** (GDPR, EEOC).
*   **Escalabilidad** para crecer con nuevas funcionalidades (IA, analítica).

***

## ✅ **2. Alcance Funcional (MVP)**

*   **Gestión de ofertas**: Crear, publicar y cerrar posiciones.
*   **Gestión de candidatos**: Base de datos, búsqueda, notas y etiquetas.
*   **Pipeline visual**: Kanban para mover candidatos entre etapas.
*   **Panel de reclutadores**: Dashboard con métricas y tareas.
*   **Comunicación básica**: Notificaciones y comentarios internos.
*   **Cumplimiento básico**: Consentimiento y almacenamiento seguro.

***

## ✅ **3. Restricciones Técnicas**

*   **Integración inicial limitada**: Solo exportación CSV y conexión con LinkedIn.
*   **Infraestructura cloud**: AWS o Azure, con base de datos relacional (PostgreSQL).
*   **Escalabilidad modular**: Arquitectura orientada a microservicios en fases posteriores.
*   **Compatibilidad**: Web responsive, sin app móvil en la primera versión.
*   **Seguridad**: Encriptación de datos en tránsito y reposo, autenticación OAuth2.

***

## ✅ **4. Criterios de Éxito**

*   **Adopción interna**: 80% de reclutadores usan el sistema en 3 meses.
*   **Reducción de tiempo de contratación**: -20% en comparación con el proceso manual.
*   **Satisfacción del candidato**: ≥4/5 en encuestas post-proceso.
*   **Cumplimiento normativo**: 0 incidencias en auditorías.

***

## ✅ **5. Mapa de Stakeholders y Necesidades**

| Stakeholder         | Necesidades principales                                |
| ------------------- | ------------------------------------------------------ |
| **Reclutadores**    | Rapidez, menos tareas manuales, colaboración, reportes |
| **Hiring Managers** | Visibilidad del pipeline, feedback fácil               |
| **Candidatos**      | Proceso simple, comunicación clara, privacidad         |
| **Equipo Legal**    | Cumplimiento GDPR/EEOC, trazabilidad                   |
| **IT**              | Seguridad, escalabilidad, mantenimiento sencillo       |

***

## ✅ **6. Priorización MoSCoW**

**Must Have**:

*   Crear y publicar ofertas.
*   Base de datos de candidatos.
*   Pipeline Kanban.
*   Dashboard básico.
*   Cumplimiento GDPR.

**Should Have**:

*   Búsqueda avanzada de candidatos.
*   Notificaciones internas.
*   Exportación de datos.

**Could Have**:

*   Integración con calendarios.
*   Chatbot para candidatos.
*   Reportes avanzados.

**Won’t Have (por ahora)**:

*   App móvil.
*   IA para screening.
*   Integración con payroll.

