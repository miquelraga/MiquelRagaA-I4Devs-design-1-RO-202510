# USER STORIES - Sistema ATS
## Historias de Usuario Priorizadas para MVP

---

## TIPOS DE USUARIOS IDENTIFICADOS

### 1. **Reclutador/HR Specialist**
Usuario principal del sistema. Gestiona el ciclo completo de reclutamiento: crea vacantes, revisa candidatos, evalúa, coordina entrevistas y mantiene comunicación con candidatos y managers.

### 2. **Hiring Manager**
Manager de departamento que solicita contrataciones. Aprueba vacantes, revisa candidatos preseleccionados por reclutadores y toma decisiones finales de contratación.

### 3. **Candidato**
Persona externa que busca empleo. Navega vacantes disponibles, aplica a posiciones y hace seguimiento de su proceso de selección.

### 4. **Administrador del Sistema**
Responsable técnico/administrativo. Configura el sistema, gestiona usuarios, permisos, plantillas y mantiene la seguridad y cumplimiento normativo.

---

## PRIORIZACIÓN PARA MVP

**Criterio de Priorización:**
- **P0 (Crítico)**: Esencial para MVP funcional - Sprint 1-2
- **P1 (Alto)**: Necesario para experiencia completa - Sprint 3-4
- **P2 (Medio)**: Mejora experiencia pero no bloquea lanzamiento - Sprint 5-6
- **P3 (Bajo)**: Futuras iteraciones post-MVP

**Estimación:** Puntos Fibonacci (1, 2, 3, 5, 8, 13, 21)

---

## ÉPICAS DEL SISTEMA

1. **ÉPICA 1**: Gestión de Vacantes
2. **ÉPICA 2**: Portal de Candidatos y Aplicaciones
3. **ÉPICA 3**: Evaluación y Gestión de Candidatos
4. **ÉPICA 4**: Colaboración y Flujos de Aprobación
5. **ÉPICA 5**: Comunicación y Notificaciones
6. **ÉPICA 6**: Reportes y Analytics
7. **ÉPICA 7**: Administración del Sistema

---

# SPRINT 1-2: FUNDAMENTOS DEL SISTEMA (P0)

## ÉPICA 1: Gestión de Vacantes

### US-001: Crear Vacante en Borrador
**Prioridad:** P0 | **Estimación:** 5 puntos

**Como** Reclutador,  
**Quiero** crear una nueva vacante con información básica del puesto,  
**Para que pueda** preparar la oferta de empleo antes de publicarla.

**Descripción:**  
Permitir al reclutador crear una vacante con campos obligatorios (título, departamento, ubicación, tipo de contrato, descripción) y guardarla en estado borrador para revisión posterior.

**Criterios de Aceptación:**
- Formulario con campos: título, departamento, ubicación, tipo de contrato, descripción, requisitos, rango salarial
- Validación de campos obligatorios
- Botón "Guardar como Borrador" que persiste la vacante con estado=Draft
- Confirmación visual de guardado exitoso
- Vacante no visible públicamente en estado Draft

---

### US-002: Editar Vacante en Borrador
**Prioridad:** P0 | **Estimación:** 2 puntos

**Como** Reclutador,  
**Quiero** modificar vacantes en estado borrador,  
**Para que pueda** corregir información antes de publicarla.

**Descripción:**  
Permitir edición completa de vacantes que están en estado Draft.

**Criterios de Aceptación:**
- Solo vacantes con status=Draft son editables
- Formulario pre-poblado con datos existentes
- Guardado de cambios actualiza timestamp
- Validaciones de campos obligatorios

---

### US-003: Publicar Vacante
**Prioridad:** P0 | **Estimación:** 5 puntos

**Como** Reclutador,  
**Quiero** publicar una vacante revisada,  
**Para que** los candidatos puedan verla y aplicar.

**Descripción:**  
Cambiar estado de vacante de Draft a Published, generando URL pública única y notificando al hiring manager asignado.

**Criterios de Aceptación:**
- Botón "Publicar" disponible solo en vacantes Draft
- Sistema valida campos obligatorios antes de publicar
- Cambio de estado Draft → Published
- Generación de URL pública única (/careers/job/{slug})
- Timestamp de publicación registrado
- Email de notificación enviado a hiring manager asignado
- Vacante visible en portal público inmediatamente

---

### US-004: Ver Lista de Vacantes Propias
**Prioridad:** P0 | **Estimación:** 3 puntos

**Como** Reclutador,  
**Quiero** ver todas las vacantes que he creado,  
**Para que pueda** gestionar mis procesos de reclutamiento activos.

**Descripción:**  
Dashboard que muestra todas las vacantes creadas por el reclutador con información clave y filtros.

**Criterios de Aceptación:**
- Lista de vacantes mostrando: título, departamento, estado, fecha de publicación, nº de candidatos
- Filtros por: estado (Draft/Published/Closed), departamento, fecha
- Ordenamiento por fecha de creación (más reciente primero)
- Búsqueda por título de vacante
- Click en vacante abre detalle

---

## ÉPICA 2: Portal de Candidatos y Aplicaciones

### US-005: Ver Vacantes Públicas
**Prioridad:** P0 | **Estimación:** 3 puntos

**Como** Candidato,  
**Quiero** ver todas las vacantes disponibles,  
**Para que pueda** encontrar oportunidades que me interesen.

**Descripción:**  
Portal público que lista todas las vacantes en estado Published sin requerir login.

**Criterios de Aceptación:**
- Página pública accesible sin autenticación
- Solo muestra vacantes con status=Published
- Cada vacante muestra: título, departamento, ubicación, tipo de contrato
- Diseño responsive (móvil, tablet, desktop)
- SEO-friendly (meta tags, URLs limpias)

---

### US-006: Filtrar Vacantes
**Prioridad:** P0 | **Estimación:** 3 puntos

**Como** Candidato,  
**Quiero** filtrar vacantes por departamento, ubicación y tipo de contrato,  
**Para que pueda** encontrar rápidamente posiciones relevantes.

**Descripción:**  
Sistema de filtros en portal público para búsqueda eficiente.

**Criterios de Aceptación:**
- Filtros disponibles: departamento, ubicación, tipo de contrato
- Multi-selección en cada filtro
- Actualización de resultados en tiempo real
- Contador de resultados visible
- Botón "Limpiar filtros"

---

### US-007: Ver Detalle de Vacante
**Prioridad:** P0 | **Estimación:** 2 puntos

**Como** Candidato,  
**Quiero** ver información completa de una vacante,  
**Para que pueda** decidir si aplicar.

**Descripción:**  
Página de detalle mostrando descripción completa del puesto, requisitos y botón de aplicación.

**Criterios de Aceptación:**
- Muestra: título, departamento, ubicación, tipo de contrato, descripción, requisitos, rango salarial (si existe)
- Botón "Aplicar" prominente
- Información de fecha de cierre (si existe)
- Opción de compartir en redes sociales
- URL única compartible

---

### US-008: Aplicar a Vacante
**Prioridad:** P0 | **Estimación:** 8 puntos

**Como** Candidato,  
**Quiero** enviar mi candidatura a una vacante,  
**Para que** el equipo de reclutamiento considere mi perfil.

**Descripción:**  
Formulario de aplicación que captura datos del candidato y permite subir CV.

**Criterios de Aceptación:**
- Formulario con campos: nombre, apellido, email, teléfono, LinkedIn (opcional), carta de presentación (opcional)
- Upload de CV (formatos: PDF, DOC, DOCX, máx 5MB)
- Validación de formato y tamaño de archivo
- Checkbox de aceptación de términos GDPR (obligatorio)
- Prevención de aplicaciones duplicadas (mismo email + misma vacante)
- Guardado de archivo en storage seguro
- Creación de registro Candidate + Application
- Validación de email único por vacante
- Confirmación visual de aplicación exitosa

---

### US-009: Confirmación de Aplicación
**Prioridad:** P0 | **Estimación:** 3 puntos

**Como** Candidato,  
**Quiero** recibir confirmación inmediata de mi aplicación,  
**Para que** tenga certeza de que mi candidatura fue recibida.

**Descripción:**  
Sistema de confirmación mediante pantalla y email automático.

**Criterios de Aceptación:**
- Pantalla de confirmación tras envío exitoso
- Email automático enviado a candidato con:
  - Confirmación de recepción
  - Título de la vacante
  - Próximos pasos del proceso
  - Tiempo estimado de respuesta
- Registro de email en EmailLog

---

## ÉPICA 7: Administración del Sistema

### US-010: Login de Usuario
**Prioridad:** P0 | **Estimación:** 5 puntos

**Como** Usuario del sistema (Reclutador/Manager/Admin),  
**Quiero** acceder al sistema con mis credenciales,  
**Para que pueda** utilizar las funcionalidades según mi rol.

**Descripción:**  
Sistema de autenticación básico con usuario y contraseña.

**Criterios de Aceptación:**
- Formulario de login con email y contraseña
- Validación de credenciales contra base de datos
- Hashing de contraseña con bcrypt
- Generación de JWT token (expiración 24h)
- Redirección a dashboard según rol
- Mensaje de error claro si credenciales inválidas
- Sesión persistente (no cerrar al refrescar página)

---

### US-011: Crear Usuario (Admin)
**Prioridad:** P0 | **Estimación:** 5 puntos

**Como** Administrador,  
**Quiero** crear nuevos usuarios en el sistema,  
**Para que** reclutadores y managers puedan acceder.

**Descripción:**  
Panel de administración para crear usuarios con diferentes roles.

**Criterios de Aceptación:**
- Formulario con: nombre, apellido, email, rol (Admin/Recruiter/Manager), departamento
- Validación de email único
- Generación automática de contraseña temporal segura
- Email de bienvenida con credenciales
- Usuario creado con is_active=true
- Registro en AuditLog

---

### US-012: Ver Lista de Usuarios
**Prioridad:** P0 | **Estimación:** 2 puntos

**Como** Administrador,  
**Quiero** ver todos los usuarios del sistema,  
**Para que pueda** gestionar accesos y roles.

**Descripción:**  
Dashboard administrativo con lista completa de usuarios.

**Criterios de Aceptación:**
- Tabla mostrando: nombre, email, rol, departamento, estado (activo/inactivo), último login
- Búsqueda por nombre o email
- Filtro por rol
- Ordenamiento por columnas
- Paginación (50 usuarios por página)

---

# SPRINT 3-4: FUNCIONALIDADES CORE (P1)

## ÉPICA 3: Evaluación y Gestión de Candidatos

### US-013: Ver Candidatos de una Vacante
**Prioridad:** P1 | **Estimación:** 5 puntos

**Como** Reclutador,  
**Quiero** ver todos los candidatos que aplicaron a una vacante,  
**Para que pueda** gestionar el proceso de selección.

**Descripción:**  
Vista de lista de candidatos con información básica y estados.

**Criterios de Aceptación:**
- Lista de candidatos mostrando: nombre, email, fecha de aplicación, estado actual, rating
- Vista tipo tabla o cards
- Filtro por estado (New, Screening, Interview, Offer, Hired, Rejected)
- Ordenamiento por fecha de aplicación, rating, nombre
- Búsqueda por nombre o email
- Contador de candidatos por estado
- Click en candidato abre perfil detallado

---

### US-014: Ver Perfil de Candidato
**Prioridad:** P1 | **Estimación:** 5 puntos

**Como** Reclutador,  
**Quiero** ver el perfil completo de un candidato,  
**Para que pueda** evaluar su idoneidad para la posición.

**Descripción:**  
Vista detallada con toda la información del candidato y su aplicación.

**Criterios de Aceptación:**
- Muestra: datos personales, email, teléfono, LinkedIn
- Visor de CV integrado (PDF viewer en navegador)
- Botón de descarga de CV
- Carta de presentación (si existe)
- Fecha de aplicación
- Estado actual
- Rating actual (si existe)
- Historial de cambios de estado
- Notas previas de otros evaluadores
- URL persistente para compartir con manager

---

### US-015: Añadir Nota a Candidato
**Prioridad:** P1 | **Estimación:** 3 puntos

**Como** Reclutador,  
**Quiero** añadir notas privadas sobre un candidato,  
**Para que pueda** documentar mi evaluación y compartir insights con el equipo.

**Descripción:**  
Sistema de notas textuales asociadas a aplicaciones.

**Criterios de Aceptación:**
- Campo de texto para escribir nota
- Botón "Guardar nota"
- Nota asociada a application_id + user_id actual
- Timestamp automático
- Notas marcadas como privadas (no visibles para candidato)
- Visualización de autor y fecha en cada nota
- Listado cronológico de todas las notas

---

### US-016: Evaluar Candidato con Rating
**Prioridad:** P1 | **Estimación:** 3 puntos

**Como** Reclutador,  
**Quiero** asignar una puntuación al candidato,  
**Para que pueda** clasificar candidatos objetivamente.

**Descripción:**  
Sistema de rating de 1 a 5 estrellas para evaluación rápida.

**Criterios de Aceptación:**
- Selector visual de 1-5 estrellas
- Guardado inmediato al seleccionar
- Rating visible en lista de candidatos
- Posibilidad de cambiar rating en cualquier momento
- Ordenamiento de candidatos por rating

---

### US-017: Cambiar Estado de Candidato
**Prioridad:** P1 | **Estimación:** 5 puntos

**Como** Reclutador,  
**Quiero** mover candidatos entre diferentes etapas del proceso,  
**Para que pueda** reflejar el progreso en la selección.

**Descripción:**  
Workflow de estados para gestionar pipeline de candidatos.

**Criterios de Aceptación:**
- Estados disponibles: New → Screening → Interview → Offer → Hired / Rejected
- Selector de estado en perfil de candidato
- Campo opcional para comentario al cambiar estado
- Registro en ApplicationHistory (estado anterior, nuevo estado, usuario, timestamp, comentario)
- Email automático al candidato notificando cambio (excepto notas internas)
- Actualización visual inmediata

---

### US-018: Rechazar Candidato
**Prioridad:** P1 | **Estimación:** 3 puntos

**Como** Reclutador,  
**Quiero** rechazar candidatos que no cumplen requisitos,  
**Para que pueda** mantener el pipeline limpio y dar feedback.

**Descripción:**  
Flujo específico para rechazo con razón opcional.

**Criterios de Aceptación:**
- Botón "Rechazar" en perfil de candidato
- Modal con razones predefinidas (opcional): "No cumple requisitos técnicos", "Experiencia insuficiente", "Perfil no alineado", "Otra"
- Campo de texto para razón personalizada
- Cambio de estado a "Rejected"
- Email automático al candidato con mensaje de rechazo cortés
- Candidatos rechazados filtrados por defecto en lista

---

## ÉPICA 4: Colaboración y Flujos de Aprobación

### US-019: Asignar Candidato a Manager
**Prioridad:** P1 | **Estimación:** 5 puntos

**Como** Reclutador,  
**Quiero** asignar candidatos preseleccionados a hiring managers,  
**Para que puedan** revisarlos y aprobarlos para entrevista.

**Descripción:**  
Sistema de asignación que permite al reclutador solicitar revisión del manager.

**Criterios de Aceptación:**
- Selector de manager en perfil de candidato (dropdown con managers del departamento)
- Botón "Asignar para revisión"
- Email de notificación al manager con link directo al perfil del candidato
- Estado del candidato incluye "Pendiente de revisión manager"
- Manager ve lista de candidatos asignados en su dashboard

---

### US-020: Ver Candidatos Asignados (Manager)
**Prioridad:** P1 | **Estimación:** 3 puntos

**Como** Hiring Manager,  
**Quiero** ver candidatos que me han asignado para revisión,  
**Para que pueda** evaluarlos y tomar decisiones.

**Descripción:**  
Dashboard específico para managers con candidatos pendientes de su revisión.

**Criterios de Aceptación:**
- Vista de "Candidatos Pendientes" en dashboard de manager
- Muestra: nombre del candidato, vacante, fecha de asignación, reclutador que asignó
- Ordenamiento por fecha de asignación (más antiguo primero)
- Badge con número de candidatos pendientes
- Click abre perfil completo del candidato

---

### US-021: Aprobar/Rechazar Candidato (Manager)
**Prioridad:** P1 | **Estimación:** 5 puntos

**Como** Hiring Manager,  
**Quiero** aprobar o rechazar candidatos asignados,  
**Para que** el reclutador sepa si continuar con el proceso.

**Descripción:**  
Sistema de aprobación con comentarios para feedback al reclutador.

**Criterios de Aceptación:**
- Botones "Aprobar" y "Rechazar" en perfil de candidato
- Campo obligatorio de comentario al aprobar o rechazar
- Al aprobar: estado cambia a "Interview", notificación a reclutador y candidato
- Al rechazar: notificación a reclutador con comentario, reclutador decide acción final
- Registro en ApplicationHistory con decisión del manager
- Email templates diferenciados para aprobación y rechazo

---

## ÉPICA 5: Comunicación y Notificaciones

### US-022: Enviar Email Manual a Candidato
**Prioridad:** P1 | **Estimación:** 5 puntos

**Como** Reclutador,  
**Quiero** enviar emails personalizados a candidatos,  
**Para que pueda** comunicarme de forma directa cuando sea necesario.

**Descripción:**  
Editor de email integrado para comunicación adhoc.

**Criterios de Aceptación:**
- Botón "Enviar email" en perfil de candidato
- Modal con editor de email: destinatario (pre-poblado), asunto, cuerpo
- Formato de texto enriquecido (negrita, cursiva, listas)
- Variables dinámicas: {candidate_name}, {job_title}
- Opción de usar plantillas predefinidas
- Registro en EmailLog
- Copia del email visible en historial del candidato

---

### US-023: Configurar Plantillas de Email (Admin)
**Prioridad:** P1 | **Estimación:** 5 punts

**Como** Administrador,  
**Quiero** crear y editar plantillas de email,  
**Para que** las comunicaciones sean consistentes y profesionales.

**Descripción:**  
Panel de gestión de plantillas reutilizables.

**Criterios de Aceptación:**
- Lista de plantillas existentes: Confirmación de aplicación, Rechazo, Invitación a entrevista, Oferta
- Editor de plantilla con campos: nombre, asunto, cuerpo
- Variables dinámicas disponibles: {candidate_name}, {job_title}, {company_name}, {recruiter_name}
- Vista previa de plantilla
- Activar/desactivar plantilla
- Plantilla por defecto para cada tipo de notificación

---

### US-024: Notificaciones de Email Automáticas
**Prioridad:** P1 | **Estimación:** 8 puntos

**Como** sistema,  
**Quiero** enviar emails automáticos en eventos clave,  
**Para que** usuarios y candidatos estén informados sin intervención manual.

**Descripción:**  
Sistema de emails transaccionales automáticos.

**Criterios de Aceptación:**
- Email enviado al aplicar (confirmación para candidato)
- Email enviado al cambiar estado (notificación a candidato)
- Email enviado al publicar vacante (notificación a hiring manager)
- Email enviado al asignar candidato (notificación a manager)
- Email enviado al aprobar/rechazar (notificación a reclutador)
- Uso de plantillas configuradas por admin
- Queue de emails para procesamiento asíncrono
- Manejo de fallos con retry automático (3 intentos)
- Log completo en EmailLog con status

---

## ÉPICA 1: Gestión de Vacantes (Continuación)

### US-025: Cerrar Vacante
**Prioridad:** P1 | **Estimación:** 3 puntos

**Como** Reclutador,  
**Quiero** cerrar una vacante cuando se complete la contratación,  
**Para que** no aparezca en el portal público y mantenga el sistema ordenado.

**Descripción:**  
Cambio de estado de vacante a Closed.

**Criterios de Aceptación:**
- Botón "Cerrar vacante" en detalle de vacante
- Confirmación antes de cerrar
- Cambio de estado Published → Closed
- Timestamp de cierre registrado
- Vacante oculta del portal público inmediatamente
- Candidatos en proceso no afectados (pueden continuar)
- Posibilidad de reabrir vacante (future story)

---

### US-026: Duplicar Vacante
**Prioridad:** P1 | **Estimación:** 3 puntos

**Como** Reclutador,  
**Quiero** duplicar una vacante existente,  
**Para que pueda** crear vacantes similares rápidamente.

**Descripción:**  
Copiar vacante existente como base para nueva vacante.

**Criterios de Aceptación:**
- Botón "Duplicar" en detalle de vacante
- Crea nueva vacante con todos los campos copiados excepto: job_id, estado (siempre Draft), fechas
- Título incluye "(Copia)" al final
- Redirige a edición de la nueva vacante
- Confirmación visual de duplicación exitosa

---

# SPRINT 5-6: MEJORAS Y ANALYTICS (P2)

## ÉPICA 6: Reportes y Analytics

### US-027: Ver Dashboard General
**Prioridad:** P2 | **Estimación:** 8 puntos

**Como** Reclutador,  
**Quiero** ver métricas clave de mis procesos de reclutamiento,  
**Para que pueda** entender el estado general y detectar cuellos de botella.

**Descripción:**  
Dashboard con KPIs y visualizaciones.

**Criterios de Aceptación:**
- Métricas mostradas:
  - Total de vacantes activas (Published)
  - Total de candidatos en proceso
  - Candidatos por etapa (gráfico de funnel)
  - Time-to-hire promedio (días)
  - Vacantes con más candidatos
- Filtros por: rango de fechas, departamento
- Actualización automática de datos
- Gráficos visuales (barras, donut, line chart)
- Responsive design

---

### US-028: Ver Reporte de Vacante Específica
**Prioridad:** P2 | **Estimación:** 5 puntos

**Como** Reclutador,  
**Quiero** ver métricas detalladas de una vacante,  
**Para que pueda** analizar el rendimiento del proceso de selección.

**Descripción:**  
Reporte individual por vacante con métricas específicas.

**Criterios de Aceptación:**
- Accesible desde detalle de vacante
- Métricas mostradas:
  - Total de aplicaciones
  - Funnel de conversión entre etapas (con porcentajes)
  - Time-to-hire de candidatos contratados
  - Distribución de ratings
  - Timeline de aplicaciones (gráfico temporal)
- Tabla de candidatos por etapa
- Identificación de cuellos de botella (etapas con más tiempo)

---

### US-029: Exportar Datos a Excel
**Prioridad:** P2 | **Estimación:** 5 puntos

**Como** Reclutador,  
**Quiero** exportar datos de candidatos y vacantes a Excel,  
**Para que pueda** realizar análisis externos o compartir con stakeholders.

**Descripción:**  
Funcionalidad de export de datos en formato CSV/Excel.

**Criterios de Aceptación:**
- Botón "Exportar" en lista de candidatos y reportes
- Generación de archivo .xlsx
- Columnas incluidas: todos los campos relevantes de candidatos y aplicaciones
- Descarga automática del archivo
- Nombre de archivo descriptivo con timestamp
- Respeta filtros activos en la vista

---

## ÉPICA 3: Evaluación y Gestión de Candidatos (Continuación)

### US-030: Buscar Candidatos Globalmente
**Prioridad:** P2 | **Estimación:** 5 puntos

**Como** Reclutador,  
**Quiero** buscar candidatos en toda la base de datos,  
**Para que pueda** encontrar perfiles para nuevas posiciones.

**Descripción:**  
Búsqueda global de candidatos más allá de una vacante específica.

**Criterios de Aceptación:**
- Buscador global accesible desde menú principal
- Búsqueda por: nombre, email, skills (en carta de presentación)
- Full-text search en PostgreSQL
- Resultados muestran: nombre, email, vacantes a las que aplicó, fecha de última aplicación
- Filtros por: fecha de aplicación, estado de última aplicación
- Click en resultado abre perfil de candidato

---

### US-031: Ver Historial Completo de Candidato
**Prioridad:** P2 | **Estimación:** 3 puntos

**Como** Reclutador,  
**Quiero** ver todas las interacciones históricas con un candidato,  
**Para que pueda** tener contexto completo antes de tomar decisiones.

**Descripción:**  
Timeline completa de actividad de un candidato en el sistema.

**Criterios de Aceptación:**
- Sección "Historial" en perfil de candidato
- Timeline mostrando:
  - Aplicaciones a diferentes vacantes
  - Cambios de estado en cada proceso
  - Notas añadidas
  - Emails enviados
  - Evaluaciones recibidas
- Ordenamiento cronológico inverso (más reciente primero)
- Filtro por tipo de evento

---

## ÉPICA 2: Portal de Candidatos (Continuación)

### US-032: Ver Estado de Aplicación (Candidato)
**Prioridad:** P2 | **Estimación:** 8 puntos

**Como** Candidato,  
**Quiero** consultar el estado de mis aplicaciones,  
**Para que pueda** saber en qué fase del proceso estoy.

**Descripción:**  
Portal de seguimiento para candidatos.

**Criterios de Aceptación:**
- Link en email de confirmación a portal de seguimiento
- Acceso mediante email + código único (no requiere cuenta)
- Lista de aplicaciones del candidato mostrando:
  - Vacante aplicada
  - Fecha de aplicación
  - Estado actual (en lenguaje amigable)
  - Fecha de última actualización
- Indicador visual de progreso (steps: Aplicado → En revisión → Entrevista → Decisión final)
- Mensaje de próximos pasos según el estado
- Responsive design

---

## ÉPICA 7: Administración del Sistema (Continuación)

### US-033: Desactivar Usuario
**Prioridad:** P2 | **Estimación:** 2 puntos

**Como** Administrador,  
**Quiero** desactivar usuarios que ya no trabajan en la empresa,  
**Para que** no puedan acceder al sistema manteniendo su historial.

**Descripción:**  
Soft delete de usuarios.

**Criterios de Aceptación:**
- Botón "Desactivar" en listado de usuarios
- Cambio de is_active=false
- Usuario no puede hacer login
- Historial y acciones pasadas del usuario permanecen visibles
- Posibilidad de reactivar usuario
- Registro en AuditLog

---

### US-034: Gestionar Departamentos
**Prioridad:** P2 | **Estimación:** 3 puntos

**Como** Administrador,  
**Quiero** crear y editar departamentos,  
**Para que** los reclutadores puedan asociar vacantes correctamente.

**Descripción:**  
CRUD de catálogo de departamentos.

**Criterios de Aceptación:**
- Lista de departamentos existentes
- Formulario para crear: nombre, descripción
- Editar departamentos existentes
- No permitir eliminar departamento si tiene vacantes o usuarios asociados
- Validación de nombre único

---

### US-035: Gestionar Ubicaciones
**Prioridad:** P2 | **Estimación:** 3 puntos

**Como** Administrador,  
**Quiero** gestionar ubicaciones disponibles,  
**Para que** las vacantes reflejen las localizaciones correctas.

**Descripción:**  
CRUD de catálogo de ubicaciones.

**Criterios de Aceptación:**
- Lista de ubicaciones existentes
- Formulario para crear: ciudad, país, remoto (checkbox)
- Editar ubicaciones existentes
- No permitir eliminar ubicación si tiene vacantes asociadas
- Validación de combinación ciudad+país única

---

### US-036: Cambiar Contraseña
**Prioridad:** P2 | **Estimación:** 3 puntos

**Como** Usuario,  
**Quiero** cambiar mi contraseña,  
**Para que pueda** mantener mi cuenta segura.

**Descripción:**  
Funcionalidad de cambio de contraseña dentro del sistema.

**Criterios de Aceptación:**
- Accesible desde perfil de usuario
- Formulario: contraseña actual, nueva contraseña, confirmar nueva contraseña
- Validación de contraseña actual correcta
- Validación de contraseña nueva (min 8 caracteres, 1 mayúscula, 1 número)
- Hashing con bcrypt
- Confirmación visual de cambio exitoso
- Registro en AuditLog

---

# POST-MVP (P3) - FUTURAS ITERACIONES

## ÉPICA 4: Colaboración (Futura)

### US-037: Comentarios Colaborativos
**Prioridad:** P3 | **Estimación:** 8 puntos

**Como** Reclutador o Manager,  
**Quiero** tener conversaciones tipo chat sobre candidatos,  
**Para que** el equipo pueda colaborar en tiempo real.

**Descripción:**  
Sistema de comentarios estilo thread para discusión de candidatos.

---

### US-038: Menciones en Notas
**Prioridad:** P3 | **Estimación:** 5 puntos

**Como** Reclutador,  
**Quiero** mencionar a otros usuarios en notas (@usuario),  
**Para que** reciban notificaciones y se involucren en la evaluación.

---

## ÉPICA 5: Comunicación (Futura)

### US-039: Programar Entrevistas
**Prioridad:** P3 | **Estimación:** 13 puntos

**Como** Reclutador,  
**Quiero** programar entrevistas con integración de calendario,  
**Para que** candidatos y managers reciban invitaciones automáticas.

**Descripción:**  
Integración con Google Calendar / Outlook para scheduling.

---

### US-040: Recordatorios Automáticos
**Prioridad:** P3 | **Estimación:** 5 puntos

**Como** Reclutador,  
**Quiero** recibir recordatorios de candidatos sin actividad,  
**Para que** no se queden estancados en el proceso.

**Descripción:**  
Sistema de alertas automáticas para candidatos inactivos > 7 días.

---

## ÉPICA 6: Reportes (Futura)

### US-041: Dashboard para Executives
**Prioridad:** P3 | **Estimación:** 13 puntos

**Como** Director de RRHH,  
**Quiero** ver métricas ejecutivas de reclutamiento,  
**Para que pueda** tomar decisiones estratégicas.

**Descripción:**  
Dashboard con KPIs agregados: cost-per-hire, source of hire, diversity metrics.

---

### US-042: Análisis de Fuentes de Candidatos
**Prioridad:** P3 | **Estimación:** 8 puntos

**Como** Reclutador,  
**Quiero** saber de dónde vienen los mejores candidatos,  
**Para que pueda** optimizar estrategias de sourcing.

**Descripción:**  
Tracking de origen de aplicaciones (directo, LinkedIn, Indeed, referral).

---

## ÉPICA 2: Portal de Candidatos (Futura)

### US-043: Perfil de Candidato Reutilizable
**Prioridad:** P3 | **Estimación:** 13 puntos

**Como** Candidato,  
**Quiero** crear un perfil en el sistema,  
**Para que pueda** aplicar a múltiples vacantes sin reintroducir datos.

---

### US-044: Alertas de Nuevas Vacantes
**Prioridad:** P3 | **Estimación:** 8 puntos

**Como** Candidato,  
**Quiero** suscribirme a alertas de nuevas vacantes,  
**Para que** me notifiquen cuando haya posiciones relevantes.

---

## ÉPICA 7: Administración (Futura)

### US-045: Cumplimiento GDPR - Derecho al Olvido
**Prioridad:** P3 | **Estimación:** 8 puntos

**Como** Candidato,  
**Quiero** solicitar eliminación de mis datos,  
**Para que** la empresa cumpla con regulaciones de protección de datos.

**Descripción:**  
Endpoint y workflow para eliminar completamente datos de un candidato.

---

### US-046: Auditoría de Accesos
**Prioridad:** P3 | **Estimación:** 5 puntos

**Como** Administrador,  
**Quiero** ver logs de acceso a datos de candidatos,  
**Para que** pueda auditar cumplimiento de privacidad.

---

### US-047: Roles y Permisos Granulares
**Prioridad:** P3 | **Estimación:** 13 puntos

**Como** Administrador,  
**Quiero** configurar permisos específicos por usuario,  
**Para que** pueda controlar accesos de forma granular.

**Descripción:**  
Sistema RBAC avanzado con permisos a nivel de acción.

---

# RESUMEN DE ESTIMACIÓN POR SPRINT

## Sprint 1-2 (P0 - Fundamentos)
**User Stories:** US-001 a US-012  
**Puntos Totales:** 54 puntos  
**Enfoque:** Autenticación, gestión básica de vacantes, aplicaciones de candidatos

| US | Título | Puntos |
|----|--------|--------|
| US-001 | Crear Vacante en Borrador | 5 |
| US-002 | Editar Vacante en Borrador | 2 |
| US-003 | Publicar Vacante | 5 |
| US-004 | Ver Lista de Vacantes Propias | 3 |
| US-005 | Ver Vacantes Públicas | 3 |
| US-006 | Filtrar Vacantes | 3 |
| US-007 | Ver Detalle de Vacante | 2 |
| US-008 | Aplicar a Vacante | 8 |
| US-009 | Confirmación de Aplicación | 3 |
| US-010 | Login de Usuario | 5 |
| US-011 | Crear Usuario (Admin) | 5 |
| US-012 | Ver Lista de Usuarios | 2 |

---

## Sprint 3-4 (P1 - Core Features)
**User Stories:** US-013 a US-026  
**Puntos Totales:** 66 puntos  
**Enfoque:** Evaluación de candidatos, colaboración, notificaciones

| US | Título | Puntos |
|----|--------|--------|
| US-013 | Ver Candidatos de una Vacante | 5 |
| US-014 | Ver Perfil de Candidato | 5 |
| US-015 | Añadir Nota a Candidato | 3 |
| US-016 | Evaluar Candidato con Rating | 3 |
| US-017 | Cambiar Estado de Candidato | 5 |
| US-018 | Rechazar Candidato | 3 |
| US-019 | Asignar Candidato a Manager | 5 |
| US-020 | Ver Candidatos Asignados (Manager) | 3 |
| US-021 | Aprobar/Rechazar Candidato (Manager) | 5 |
| US-022 | Enviar Email Manual a Candidato | 5 |
| US-023 | Configurar Plantillas de Email (Admin) | 5 |
| US-024 | Notificaciones de Email Automáticas | 8 |
| US-025 | Cerrar Vacante | 3 |
| US-026 | Duplicar Vacante | 3 |

---

## Sprint 5-6 (P2 - Analytics & Mejoras)
**User Stories:** US-027 a US-036  
**Puntos Totales:** 52 puntos  
**Enfoque:** Reportes, búsqueda avanzada, portal de candidatos, administración

| US | Título | Puntos |
|----|--------|--------|
| US-027 | Ver Dashboard General | 8 |
| US-028 | Ver Reporte de Vacante Específica | 5 |
| US-029 | Exportar Datos a Excel | 5 |
| US-030 | Buscar Candidatos Globalmente | 5 |
| US-031 | Ver Historial Completo de Candidato | 3 |
| US-032 | Ver Estado de Aplicación (Candidato) | 8 |
| US-033 | Desactivar Usuario | 2 |
| US-034 | Gestionar Departamentos | 3 |
| US-035 | Gestionar Ubicaciones | 3 |
| US-036 | Cambiar Contraseña | 3 |

---

## Post-MVP (P3 - Futuras Iteraciones)
**User Stories:** US-037 a US-047  
**Puntos Estimados:** ~100 puntos  
**Enfoque:** Colaboración avanzada, scheduling, analytics ejecutivos, GDPR, permisos granulares

---

# VELOCIDAD ESTIMADA Y PLANIFICACIÓN

**Asumiendo:**
- Equipo: 2 developers full-time
- Velocidad: ~20-25 puntos por sprint (2 semanas)
- 6 sprints para MVP completo

**Planificación:**
- **Sprints 1-2**: 54 puntos → 3 sprints necesarios
- **Sprints 3-4**: 66 puntos → 3 sprints necesarios  
- **Sprints 5-6**: 52 puntos → 2-3 sprints necesarios

**Total MVP: ~8-9 sprints (4-4.5 meses)**

---

# DEPENDENCIAS CRÍTICAS

```
US-010 (Login) → TODAS las demás US internas
US-001, US-003 (Vacantes) → US-005, US-007, US-008 (Portal candidatos)
US-008 (Aplicar) → US-013, US-014 (Ver candidatos)
US-014 (Perfil candidato) → US-015, US-016, US-017 (Evaluación)
US-017 (Cambiar estado) → US-024 (Notificaciones)
US-011 (Crear usuario) → US-019, US-020, US-021 (Colaboración managers)
US-023 (Plantillas) → US-024 (Notificaciones automáticas)
```

---

# CRITERIOS DE ÉXITO DEL MVP

Al finalizar Sprint 6, el sistema debe permitir:

✅ **Reclutador puede:**
- Crear, publicar y cerrar vacantes
- Ver todos los candidatos aplicados
- Evaluar candidatos con notas y ratings
- Cambiar estados de candidatos
- Asignar candidatos a managers
- Enviar emails manuales
- Ver métricas básicas en dashboard

✅ **Manager puede:**
- Ver candidatos asignados
- Aprobar o rechazar candidatos
- Añadir comentarios de evaluación

✅ **Candidato puede:**
- Ver vacantes publicadas con filtros
- Aplicar subiendo CV y datos
- Recibir confirmación y notificaciones de cambios
- Ver estado de sus aplicaciones

✅ **Admin puede:**
- Crear y gestionar usuarios
- Configurar plantillas de email
- Gestionar departamentos y ubicaciones

✅ **Sistema:**
- Autenticación segura con JWT
- Emails automáticos en eventos clave
- Almacenamiento seguro de CVs
- Logs de auditoría
- Cumplimiento GDPR básico

---

**Documento Versión:** 1.0  
**Fecha:** 26 Noviembre 2025  
**Próxima Revisión:** Post Sprint 2 (refinamiento de backlog)
