# PRD - Sistema ATS (Applicant Tracking System)
## Product Requirements Document v1.0

---

## 1. DISEÑO

### 1.1 Visión del Producto
Sistema ATS que permita a empresas gestionar de manera eficiente el proceso completo de reclutamiento, desde la publicación de vacantes hasta la contratación del candidato, optimizando tiempos y mejorando la experiencia tanto de reclutadores como de candidatos.

### 1.2 Objetivos del Producto
- Centralizar todas las vacantes y candidaturas en una única plataforma
- Reducir el tiempo de contratación en un 40%
- Mejorar la colaboración entre equipos de RRHH y managers
- Proporcionar visibilidad completa del pipeline de reclutamiento
- Garantizar cumplimiento normativo (GDPR, protección de datos)

### 1.3 Alcance - MVP (Versión 1.0)
**En Scope:**
- Gestión de vacantes (crear, editar, publicar, cerrar)
- Portal de candidatos para aplicaciones
- Base de datos de candidatos
- Sistema de evaluación y scoring básico
- Flujo de aprobación de candidatos
- Notificaciones por email
- Dashboard básico de métricas

**Out of Scope (Futuras versiones):**
- Integración con LinkedIn/Indeed
- Video entrevistas integradas
- IA para screening automático
- Multi-idioma
- App móvil nativa

### 1.4 Usuarios Objetivo
1. **Reclutadores/HR Specialists**: Usuarios principales, gestionan el proceso completo
2. **Hiring Managers**: Aprueban vacantes, evalúan candidatos finales
3. **Candidatos**: Aplican a posiciones, siguen su proceso
4. **Administradores**: Configuran sistema, gestionan usuarios y permisos

### 1.5 Propuesta de Valor
- **Para Reclutadores**: Automatización de tareas repetitivas, vista unificada de todos los candidatos
- **Para Managers**: Visibilidad del pipeline, evaluación estructurada
- **Para Candidatos**: Proceso transparente, experiencia profesional
- **Para la Empresa**: Métricas de rendimiento, reducción de costes, mejor calidad de contratación

---

## 2. DOCUMENTACIÓN DE INVESTIGACIÓN

### 2.1 Análisis de Mercado

#### Competidores Principales
1. **Workday Recruiting**
   - Fortalezas: Integración con HRMS, analytics potentes
   - Debilidades: Alto coste, complejo para PyMEs
   
2. **Greenhouse**
   - Fortalezas: UX excelente, integraciones abundantes
   - Debilidades: Precio premium, curva de aprendizaje
   
3. **Lever**
   - Fortalezas: CRM integrado, colaboración
   - Debilidades: Limitado para empresas grandes

4. **BambooHR**
   - Fortalezas: Asequible, fácil de usar
   - Debilidades: Funcionalidades básicas, escalabilidad limitada

#### Oportunidad de Mercado
- Segmento objetivo: Empresas medianas (50-500 empleados)
- Nicho: ATS con énfasis en colaboración y experiencia del candidato
- Diferenciador: Simplicidad + potencia a precio competitivo

### 2.2 Investigación de Usuario

#### Metodología
- 15 entrevistas con HR Managers
- 5 sesiones de observación de procesos de reclutamiento
- Encuesta a 50 candidatos sobre su experiencia en procesos de selección

#### Hallazgos Clave
1. **Pain Points de Reclutadores:**
   - Pérdida de candidatos por procesos largos (avg. 45 días)
   - Falta de visibilidad del estado de candidatos
   - Comunicación fragmentada (email, WhatsApp, Excel)
   - Dificultad para evaluar objetivamente

2. **Pain Points de Managers:**
   - No saben cuándo deben actuar
   - Revisión de CVs consume mucho tiempo
   - Falta de contexto sobre candidatos

3. **Pain Points de Candidatos:**
   - Agujero negro: no reciben feedback
   - Formularios largos y repetitivos
   - Falta de transparencia del proceso

### 2.3 Requisitos Técnicos del Mercado
- Compatibilidad con navegadores modernos (Chrome, Firefox, Safari, Edge)
- Responsive design (móvil/tablet)
- Tiempo de carga < 3 segundos
- Disponibilidad 99.9%
- Cumplimiento GDPR y LOPD
- Cifrado de datos en tránsito y reposo

### 2.4 Tendencias del Sector
- Automatización con IA (screening, chatbots)
- Experiencia del candidato como prioridad
- Analytics predictivos (time-to-hire, quality-of-hire)
- Diversity & Inclusion features
- Remote hiring workflows

---

## 3. DOCUMENTACIÓN DE ANÁLISIS

### 3.1 Requisitos Funcionales

#### RF-001: Gestión de Vacantes
- **RF-001.1**: El sistema debe permitir crear vacantes con: título, descripción, departamento, ubicación, tipo de contrato, salario, fecha límite
- **RF-001.2**: El sistema debe permitir editar vacantes en estado "Borrador"
- **RF-001.3**: El sistema debe permitir publicar vacantes (cambio de estado Borrador → Publicada)
- **RF-001.4**: El sistema debe permitir cerrar vacantes (Publicada → Cerrada)
- **RF-001.5**: El sistema debe generar URL pública única para cada vacante
- **RF-001.6**: El sistema debe permitir duplicar vacantes existentes

#### RF-002: Portal de Candidatos
- **RF-002.1**: El candidato debe poder ver todas las vacantes publicadas
- **RF-002.2**: El candidato debe poder filtrar vacantes por departamento, ubicación, tipo
- **RF-002.3**: El candidato debe poder aplicar subiendo CV (PDF, DOC, DOCX máx 5MB)
- **RF-002.4**: El candidato debe completar formulario: nombre, email, teléfono, LinkedIn
- **RF-002.5**: El sistema debe confirmar aplicación por email
- **RF-002.6**: El candidato debe poder ver el estado de sus aplicaciones

#### RF-003: Gestión de Candidatos
- **RF-003.1**: El reclutador debe ver lista de todos los candidatos por vacante
- **RF-003.2**: El sistema debe mostrar CV y datos del candidato en perfil único
- **RF-003.3**: El reclutador debe poder cambiar el estado del candidato (Nuevo → Screening → Entrevista → Oferta → Contratado/Rechazado)
- **RF-003.4**: El reclutador debe poder añadir notas privadas a cada candidato
- **RF-003.5**: El reclutador debe poder puntuar candidatos (1-5 estrellas)
- **RF-003.6**: El sistema debe permitir buscar candidatos por nombre, email, skills

#### RF-004: Colaboración y Aprobaciones
- **RF-004.1**: El reclutador debe poder asignar candidatos a managers para revisión
- **RF-004.2**: El manager debe recibir notificación de nuevos candidatos asignados
- **RF-004.3**: El manager debe poder aprobar/rechazar candidatos con comentarios
- **RF-004.4**: El sistema debe mantener historial de todas las evaluaciones

#### RF-005: Comunicación
- **RF-005.1**: El sistema debe enviar email al candidato cuando su estado cambia
- **RF-005.2**: El reclutador debe poder enviar emails personalizados a candidatos
- **RF-005.3**: El sistema debe tener plantillas de email predefinidas (rechazo, invitación entrevista, oferta)
- **RF-005.4**: El sistema debe registrar todo el historial de comunicaciones

#### RF-006: Reportes y Analytics
- **RF-006.1**: El dashboard debe mostrar: vacantes activas, candidatos totales, candidatos por etapa
- **RF-006.2**: El sistema debe calcular time-to-hire promedio
- **RF-006.3**: El sistema debe mostrar funnel de conversión por vacante
- **RF-006.4**: El sistema debe permitir exportar datos a CSV/Excel

#### RF-007: Administración
- **RF-007.1**: El admin debe poder crear usuarios (Reclutador, Manager, Admin)
- **RF-007.2**: El admin debe poder asignar permisos por rol
- **RF-007.3**: El admin debe poder configurar plantillas de email
- **RF-007.4**: El admin debe poder gestionar departamentos y ubicaciones

### 3.2 Requisitos No Funcionales

#### RNF-001: Rendimiento
- Tiempo de carga de página < 3 segundos
- Capacidad para 10,000 candidatos concurrentes
- Búsqueda de candidatos < 1 segundo

#### RNF-002: Seguridad
- Autenticación mediante usuario/contraseña (mínimo 8 caracteres, 1 mayúscula, 1 número)
- Sesiones con timeout de 30 minutos de inactividad
- HTTPS obligatorio
- Protección contra SQL Injection, XSS, CSRF
- Logs de auditoría de acciones críticas

#### RNF-003: Usabilidad
- Interfaz intuitiva, máximo 3 clics para acciones principales
- Onboarding interactivo para nuevos usuarios
- Mensajes de error claros y accionables
- Diseño responsive (móvil, tablet, desktop)

#### RNF-004: Escalabilidad
- Arquitectura que soporte 100,000 candidatos en base de datos
- Capacidad de crecimiento a 1,000 usuarios internos

#### RNF-005: Disponibilidad
- Uptime de 99.9%
- Backups diarios automatizados
- Plan de recuperación ante desastres (RPO 24h, RTO 4h)

#### RNF-006: Cumplimiento Legal
- Cumplimiento GDPR (derecho al olvido, portabilidad de datos)
- Cumplimiento LOPD España
- Consentimiento explícito para procesamiento de datos
- Retención de datos máx. 2 años después de proceso

### 3.3 Restricciones
- Presupuesto inicial limitado: enfoque en MVP
- Timeline: 6 meses hasta lanzamiento
- Equipo: 1 PM, 2 developers, 1 UX designer, 1 QA
- Debe integrarse con sistema de email corporativo (SMTP)

### 3.4 Asunciones
- Los usuarios tienen conocimientos básicos de informática
- Conexión a Internet estable
- Los candidatos tienen acceso a email
- La empresa tiene infraestructura para hosting en cloud

---

## 4. CASOS DE USO

### CU-001: Publicar una Vacante
**Actor Principal:** Reclutador  
**Precondiciones:** Usuario autenticado con rol Reclutador  
**Flujo Principal:**
1. Reclutador hace clic en "Nueva Vacante"
2. Sistema muestra formulario de creación
3. Reclutador completa campos obligatorios:
   - Título del puesto
   - Departamento
   - Ubicación
   - Tipo de contrato (Indefinido/Temporal/Prácticas)
   - Descripción del puesto
   - Requisitos
   - Rango salarial (opcional)
4. Reclutador hace clic en "Guardar como Borrador"
5. Sistema valida datos y guarda vacante con estado "Borrador"
6. Reclutador revisa y hace clic en "Publicar"
7. Sistema cambia estado a "Publicada" y genera URL pública
8. Sistema envía notificación al manager responsable

**Flujo Alternativo 3a:** Datos incompletos
- Sistema muestra errores de validación
- Reclutador corrige y reintenta

**Postcondiciones:** Vacante visible en portal público de candidatos

---

### CU-002: Aplicar a una Vacante
**Actor Principal:** Candidato  
**Precondiciones:** Vacante en estado "Publicada"  
**Flujo Principal:**
1. Candidato accede al portal público de vacantes
2. Candidato busca/filtra vacantes de interés
3. Candidato hace clic en vacante específica
4. Sistema muestra detalle completo de la vacante
5. Candidato hace clic en "Aplicar"
6. Sistema muestra formulario de aplicación
7. Candidato completa:
   - Nombre completo
   - Email
   - Teléfono
   - LinkedIn (opcional)
   - Carta de presentación (opcional)
8. Candidato sube CV (PDF/DOC/DOCX, máx 5MB)
9. Candidato acepta términos de protección de datos
10. Candidato hace clic en "Enviar Aplicación"
11. Sistema valida datos y archivo
12. Sistema crea registro de candidato asociado a vacante
13. Sistema envía email de confirmación al candidato
14. Sistema notifica al reclutador asignado

**Flujo Alternativo 8a:** Archivo inválido
- Sistema muestra error de formato/tamaño
- Candidato sube archivo correcto

**Flujo Alternativo 11a:** Email ya existe para esta vacante
- Sistema muestra mensaje "Ya has aplicado a esta posición"
- Permite actualizar aplicación existente

**Postcondiciones:** Candidato creado con estado "Nuevo"

---

### CU-003: Evaluar Candidatos
**Actor Principal:** Reclutador  
**Precondiciones:** Usuario autenticado, existen candidatos en la vacante  
**Flujo Principal:**
1. Reclutador accede a vacante específica
2. Sistema muestra lista de candidatos con filtros por estado
3. Reclutador hace clic en candidato
4. Sistema muestra perfil completo:
   - Datos personales
   - CV (visor integrado)
   - Historial de estados
   - Notas previas
5. Reclutador revisa CV y datos
6. Reclutador añade nota privada sobre el candidato
7. Reclutador asigna puntuación (1-5 estrellas)
8. Reclutador cambia estado a "Screening"
9. Sistema guarda evaluación con timestamp y usuario
10. Sistema envía email al candidato notificando avance

**Flujo Alternativo 8a:** Candidato no cumple requisitos
- Reclutador cambia estado a "Rechazado"
- Reclutador selecciona razón de rechazo
- Sistema envía email de rechazo al candidato

**Postcondiciones:** Evaluación registrada en historial del candidato

---

### CU-004: Aprobar Candidato para Entrevista
**Actor Principal:** Hiring Manager  
**Precondiciones:** Candidatos asignados al manager para revisión  
**Flujo Principal:**
1. Manager recibe email de notificación
2. Manager accede al sistema y ve candidatos pendientes de revisión
3. Manager hace clic en candidato
4. Sistema muestra perfil con evaluación del reclutador
5. Manager revisa información
6. Manager hace clic en "Aprobar para Entrevista"
7. Manager añade comentario con disponibilidad
8. Sistema cambia estado a "Entrevista"
9. Sistema notifica al reclutador
10. Sistema envía email al candidato invitando a entrevista

**Flujo Alternativo 6a:** Manager rechaza candidato
- Manager hace clic en "Rechazar"
- Manager añade motivo
- Sistema notifica a reclutador
- Reclutador decide si candidato sale del proceso

**Postcondiciones:** Candidato avanza a fase de entrevista

---

### CU-005: Generar Reporte de Vacante
**Actor Principal:** Reclutador / Manager  
**Precondiciones:** Usuario autenticado, existen vacantes con datos  
**Flujo Principal:**
1. Usuario accede a sección "Reportes"
2. Sistema muestra dashboard con métricas generales
3. Usuario selecciona vacante específica
4. Sistema genera reporte mostrando:
   - Total de aplicaciones
   - Candidatos por etapa (funnel)
   - Time-to-hire promedio
   - Tasa de conversión entre etapas
   - Fuente de candidatos
5. Usuario hace clic en "Exportar"
6. Sistema genera archivo Excel con datos detallados
7. Sistema descarga archivo

**Postcondiciones:** Reporte generado y descargado

---

### CU-006: Gestionar Usuarios (Admin)
**Actor Principal:** Administrador  
**Precondiciones:** Usuario con rol Admin  
**Flujo Principal:**
1. Admin accede a "Administración" → "Usuarios"
2. Sistema muestra lista de usuarios existentes
3. Admin hace clic en "Nuevo Usuario"
4. Admin completa formulario:
   - Nombre completo
   - Email
   - Rol (Reclutador/Manager/Admin)
   - Departamento
5. Admin hace clic en "Crear"
6. Sistema valida email único
7. Sistema crea usuario y genera contraseña temporal
8. Sistema envía email de bienvenida con credenciales
9. Sistema muestra confirmación

**Flujo Alternativo 6a:** Email duplicado
- Sistema muestra error
- Admin corrige email

**Postcondiciones:** Nuevo usuario creado y puede acceder al sistema

---

## 5. MODELADO DE DATOS

### 5.1 Entidades Principales

#### **User (Usuario)**
```
- user_id (PK, UUID)
- email (STRING, UNIQUE, NOT NULL)
- password_hash (STRING, NOT NULL)
- first_name (STRING, NOT NULL)
- last_name (STRING, NOT NULL)
- role (ENUM: Admin, Recruiter, Manager, NOT NULL)
- department_id (FK → Department)
- is_active (BOOLEAN, DEFAULT TRUE)
- last_login (TIMESTAMP)
- created_at (TIMESTAMP)
- updated_at (TIMESTAMP)
```

#### **Department (Departamento)**
```
- department_id (PK, UUID)
- name (STRING, NOT NULL)
- description (TEXT)
- created_at (TIMESTAMP)
```

#### **Location (Ubicación)**
```
- location_id (PK, UUID)
- city (STRING, NOT NULL)
- country (STRING, NOT NULL)
- is_remote (BOOLEAN, DEFAULT FALSE)
- created_at (TIMESTAMP)
```

#### **JobPosting (Vacante)**
```
- job_id (PK, UUID)
- title (STRING, NOT NULL)
- description (TEXT, NOT NULL)
- requirements (TEXT)
- department_id (FK → Department, NOT NULL)
- location_id (FK → Location, NOT NULL)
- employment_type (ENUM: FullTime, PartTime, Contract, Internship, NOT NULL)
- salary_min (DECIMAL)
- salary_max (DECIMAL)
- status (ENUM: Draft, Published, Closed, NOT NULL)
- created_by (FK → User, NOT NULL)
- hiring_manager_id (FK → User)
- application_deadline (DATE)
- public_url_slug (STRING, UNIQUE)
- created_at (TIMESTAMP)
- updated_at (TIMESTAMP)
- published_at (TIMESTAMP)
- closed_at (TIMESTAMP)
```

#### **Candidate (Candidato)**
```
- candidate_id (PK, UUID)
- first_name (STRING, NOT NULL)
- last_name (STRING, NOT NULL)
- email (STRING, NOT NULL)
- phone (STRING)
- linkedin_url (STRING)
- resume_url (STRING, NOT NULL)
- gdpr_consent (BOOLEAN, NOT NULL)
- gdpr_consent_date (TIMESTAMP)
- created_at (TIMESTAMP)
- updated_at (TIMESTAMP)

INDEX on (email)
```

#### **Application (Aplicación)**
```
- application_id (PK, UUID)
- job_id (FK → JobPosting, NOT NULL)
- candidate_id (FK → Candidate, NOT NULL)
- status (ENUM: New, Screening, Interview, Offer, Hired, Rejected, NOT NULL)
- cover_letter (TEXT)
- rating (INTEGER, 1-5)
- applied_at (TIMESTAMP, NOT NULL)
- updated_at (TIMESTAMP)

UNIQUE (job_id, candidate_id)
INDEX on (job_id, status)
```

#### **ApplicationNote (Nota de Aplicación)**
```
- note_id (PK, UUID)
- application_id (FK → Application, NOT NULL)
- user_id (FK → User, NOT NULL)
- note_text (TEXT, NOT NULL)
- is_visible_to_candidate (BOOLEAN, DEFAULT FALSE)
- created_at (TIMESTAMP)
```

#### **ApplicationHistory (Historial de Aplicación)**
```
- history_id (PK, UUID)
- application_id (FK → Application, NOT NULL)
- changed_by (FK → User, NOT NULL)
- previous_status (STRING)
- new_status (STRING, NOT NULL)
- comment (TEXT)
- created_at (TIMESTAMP, NOT NULL)

INDEX on (application_id, created_at)
```

#### **EmailTemplate (Plantilla de Email)**
```
- template_id (PK, UUID)
- name (STRING, NOT NULL)
- subject (STRING, NOT NULL)
- body (TEXT, NOT NULL)
- template_type (ENUM: ApplicationConfirmation, StatusUpdate, Rejection, InterviewInvite, Offer)
- created_at (TIMESTAMP)
- updated_at (TIMESTAMP)
```

#### **EmailLog (Log de Emails)**
```
- log_id (PK, UUID)
- application_id (FK → Application)
- recipient_email (STRING, NOT NULL)
- subject (STRING, NOT NULL)
- body (TEXT, NOT NULL)
- sent_at (TIMESTAMP)
- status (ENUM: Sent, Failed, NOT NULL)
```

#### **AuditLog (Log de Auditoría)**
```
- log_id (PK, UUID)
- user_id (FK → User)
- action (STRING, NOT NULL)
- entity_type (STRING, NOT NULL)
- entity_id (UUID, NOT NULL)
- details (JSON)
- ip_address (STRING)
- created_at (TIMESTAMP, NOT NULL)

INDEX on (user_id, created_at)
INDEX on (entity_type, entity_id)
```

### 5.2 Relaciones

```
User 1:N JobPosting (created_by)
User 1:N JobPosting (hiring_manager_id)
User 1:N Application (evaluaciones via ApplicationNote)
Department 1:N User
Department 1:N JobPosting
Location 1:N JobPosting
JobPosting 1:N Application
Candidate 1:N Application
Application 1:N ApplicationNote
Application 1:N ApplicationHistory
Application 1:N EmailLog
```

### 5.3 Diagrama ER Simplificado

```
┌──────────┐         ┌──────────────┐         ┌─────────────┐
│   User   │1──────N │  JobPosting  │1──────N │ Application │
└──────────┘         └──────────────┘         └─────────────┘
     │                      │                        │
     │                      │                        │1
     │1                     │N                       │
     │                      │                        │N
     N                 ┌────┴────┐            ┌─────┴──────┐
┌────┴────────┐       │Department│            │  Candidate │
│ AuditLog    │       └──────────┘            └────────────┘
└─────────────┘              │1                      
                              │N                      
                         ┌────┴────┐                  
                         │Location │                  
                         └─────────┘                  

Application 1:N ApplicationNote
Application 1:N ApplicationHistory
Application 1:N EmailLog
```

### 5.4 Reglas de Negocio en Base de Datos

1. **RN-001**: Un candidato solo puede aplicar una vez a la misma vacante (UNIQUE constraint)
2. **RN-002**: Los datos de candidatos deben eliminarse automáticamente tras 2 años de inactividad (política GDPR)
3. **RN-003**: Una vacante no puede cerrarse si tiene candidatos en proceso de "Entrevista" u "Oferta" (validación en aplicación)
4. **RN-004**: El cambio de estado de aplicación debe registrarse en ApplicationHistory (trigger)
5. **RN-005**: Los emails de candidatos deben validarse como únicos por aplicación, no globalmente
6. **RN-006**: Las notas privadas (is_visible_to_candidate=FALSE) nunca deben exponerse a candidatos

---

## 6. DISEÑO DE ALTO NIVEL

### 6.1 Arquitectura del Sistema

#### Patrón Arquitectónico: **Arquitectura de 3 Capas + Microservicios Ligeros**

```
┌─────────────────────────────────────────────────────────────┐
│                     CAPA DE PRESENTACIÓN                     │
│  ┌──────────────┐  ┌──────────────┐  ┌─────────────────┐   │
│  │   Web App    │  │  Portal      │  │  Admin Panel    │   │
│  │  (React SPA) │  │  Candidatos  │  │   (React SPA)   │   │
│  └──────────────┘  └──────────────┘  └─────────────────┘   │
└────────────────────────┬────────────────────────────────────┘
                         │ HTTPS / REST API
┌────────────────────────┴────────────────────────────────────┐
│                     CAPA DE APLICACIÓN                       │
│  ┌─────────────────────────────────────────────────────┐   │
│  │            API Gateway (Node.js/Express)             │   │
│  │         (Autenticación, Rate Limiting, CORS)         │   │
│  └─────────────────────────┬───────────────────────────┘   │
│                            │                                 │
│  ┌────────────┬────────────┼────────────┬──────────────┐   │
│  │            │            │            │              │   │
│  ▼            ▼            ▼            ▼              ▼   │
│ ┌──────┐  ┌──────┐  ┌──────┐  ┌──────┐  ┌──────────┐     │
│ │ Job  │  │ Candi│  │ User │  │Email │  │Analytics │     │
│ │Service│ │-date │  │Mgmt  │  │Service│ │ Service  │     │
│ │      │  │Service│ │Service│ │      │  │          │     │
│ └──────┘  └──────┘  └──────┘  └──────┘  └──────────┘     │
│    │         │         │         │            │            │
└────┼─────────┼─────────┼─────────┼────────────┼────────────┘
     │         │         │         │            │
┌────┴─────────┴─────────┴─────────┴────────────┴────────────┐
│                     CAPA DE DATOS                            │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐     │
│  │  PostgreSQL  │  │ File Storage │  │    Redis     │     │
│  │  (Principal) │  │    (S3/      │  │   (Caché)    │     │
│  │              │  │  Azure Blob) │  │              │     │
│  └──────────────┘  └──────────────┘  └──────────────┘     │
└─────────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────────┐
│                     SERVICIOS EXTERNOS                       │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐     │
│  │ SMTP Server  │  │   CDN        │  │  Monitoring  │     │
│  │(SendGrid/SES)│  │(CloudFlare)  │  │(Datadog/     │     │
│  │              │  │              │  │ New Relic)   │     │
│  └──────────────┘  └──────────────┘  └──────────────┘     │
└─────────────────────────────────────────────────────────────┘
```

### 6.2 Componentes Principales

#### **6.2.1 Frontend - Web Application (React)**

**Tecnologías:**
- React 18 + TypeScript
- Redux Toolkit (gestión de estado)
- React Router (navegación)
- Material-UI / Tailwind CSS (UI components)
- Axios (HTTP client)
- React Query (caché y sincronización de datos)

**Módulos principales:**
1. **Dashboard Module**: Vista general de métricas y vacantes activas
2. **Jobs Module**: CRUD de vacantes, listado, filtros
3. **Candidates Module**: Listado, perfil, evaluación, notas
4. **Applications Module**: Pipeline kanban de candidatos por vacante
5. **Reports Module**: Gráficos y exportación de datos
6. **Admin Module**: Gestión de usuarios, configuración

**Características:**
- SPA (Single Page Application) para mejor UX
- Lazy loading de módulos
- PWA capabilities para uso offline básico
- Responsive design (mobile-first)

#### **6.2.2 Backend - API Gateway & Services**

**API Gateway (Node.js + Express)**
- Punto único de entrada para todas las requests
- Autenticación JWT
- Rate limiting (100 requests/min por usuario)
- CORS configuration
- Request logging
- Error handling centralizado

**Microservicios:**

**1. Job Service**
- Responsabilidades:
  - CRUD de vacantes
  - Cambios de estado (Draft → Published → Closed)
  - Generación de URLs públicas
  - Búsqueda y filtrado de vacantes
- Endpoints principales:
  - `POST /api/jobs` - Crear vacante
  - `GET /api/jobs/:id` - Obtener vacante
  - `PUT /api/jobs/:id` - Actualizar vacante
  - `PATCH /api/jobs/:id/publish` - Publicar
  - `GET /api/jobs/public` - Listar vacantes públicas

**2. Candidate Service**
- Responsabilidades:
  - Gestión de perfiles de candidatos
  - Subida y almacenamiento de CVs
  - Búsqueda de candidatos
  - Validación de datos GDPR
- Endpoints principales:
  - `POST /api/candidates` - Crear candidato
  - `GET /api/candidates/:id` - Obtener candidato
  - `GET /api/candidates/search` - Buscar
  - `DELETE /api/candidates/:id` - Eliminar (GDPR)

**3. Application Service**
- Responsabilidades:
  - Gestión de aplicaciones
  - Cambios de estado de candidatos
  - Notas y evaluaciones
  - Historial de cambios
- Endpoints principales:
  - `POST /api/applications` - Crear aplicación
  - `GET /api/applications?job_id=X` - Listar por vacante
  - `PATCH /api/applications/:id/status` - Cambiar estado
  - `POST /api/applications/:id/notes` - Añadir nota
  - `GET /api/applications/:id/history` - Historial

**4. Email Service**
- Responsabilidades:
  - Envío de emails transaccionales
  - Gestión de plantillas
  - Logging de emails enviados
  - Queue de emails
- Implementación:
  - Background worker (Bull + Redis)
  - Integración con SendGrid/AWS SES
- Eventos que disparan emails:
  - Aplicación recibida
  - Cambio de estado
  - Asignación a manager
  - Invitación a entrevista

**5. User Management Service**
- Responsabilidades:
  - CRUD de usuarios
  - Autenticación (login/logout)
  - Gestión de roles y permisos
  - Password reset
- Endpoints principales:
  - `POST /api/auth/login`
  - `POST /api/auth/logout`
  - `POST /api/auth/forgot-password`
  - `POST /api/users` - Crear usuario (Admin only)
  - `GET /api/users` - Listar usuarios

**6. Analytics Service**
- Responsabilidades:
  - Cálculo de métricas
  - Generación de reportes
  - Exportación de datos
- Métricas clave:
  - Time-to-hire
  - Candidates por etapa (funnel)
  - Tasa de conversión
  - Fuentes de candidatos
- Endpoints principales:
  - `GET /api/analytics/dashboard`
  - `GET /api/analytics/job/:id/funnel`
  - `GET /api/analytics/export?format=csv`

### 6.3 Base de Datos

**PostgreSQL 14+**
- Base de datos relacional principal
- JSON support para campos flexibles (detalles en AuditLog)
- Full-text search para búsqueda de candidatos
- Replicación master-slave para alta disponibilidad

**Esquema de particionado:**
- Tabla `ApplicationHistory` particionada por fecha (mensual)
- Tabla `AuditLog` particionada por fecha (mensual)
- Política de retención: 2 años para datos de candidatos inactivos

### 6.4 Almacenamiento de Archivos

**AWS S3 / Azure Blob Storage**
- Almacenamiento de CVs de candidatos
- Estructura de carpetas: `/resumes/{candidate_id}/{filename}`
- Pre-signed URLs para acceso seguro (expiración 1 hora)
- Política de retención: alineada con datos GDPR (2 años)

### 6.5 Caché

**Redis**
- Caché de sesiones de usuario
- Caché de vacantes públicas (TTL 5 minutos)
- Queue para procesamiento de emails
- Rate limiting storage

### 6.6 Seguridad

#### Autenticación y Autorización
- **JWT (JSON Web Tokens)** para autenticación stateless
- Token expiration: 24 horas
- Refresh tokens: 7 días
- RBAC (Role-Based Access Control):
  - Admin: acceso completo
  - Recruiter: CRUD vacantes, gestión candidatos
  - Manager: solo lectura y evaluación de candidatos asignados

#### Protección de Datos
- HTTPS obligatorio (TLS 1.3)
- Encriptación de datos en reposo (AES-256)
- Hashing de contraseñas (bcrypt, cost factor 12)
- Sanitización de inputs (prevención SQL Injection, XSS)
- CSRF tokens en formularios
- Validación de file uploads (tipo MIME, tamaño, virus scan)

#### Cumplimiento GDPR
- Consentimiento explícito al aplicar
- Derecho al olvido (endpoint DELETE candidate)
- Portabilidad de datos (export all candidate data)
- Logs de auditoría de acceso a datos personales
- DPO (Data Protection Officer) designado
- Privacy by Design

### 6.7 Escalabilidad

#### Horizontal Scaling
- API Gateway y Microservicios stateless → fácil escalado horizontal
- Load Balancer (AWS ALB / NGINX) distribuyendo tráfico
- Auto-scaling basado en CPU/memoria (>70% → scale up)

#### Vertical Scaling
- Base de datos: escalado vertical inicial, replicación después
- Redis: Redis Cluster para alta disponibilidad

#### Optimizaciones
- Paginación en todas las listas (máx 50 items por página)
- Índices en campos de búsqueda frecuente
- Caché de queries costosas
- CDN para assets estáticos
- Lazy loading de imágenes y archivos

### 6.8 Monitorización y Logs

**Application Performance Monitoring (APM)**
- Herramienta: Datadog / New Relic
- Métricas monitorizadas:
  - Response time de endpoints
  - Error rate
  - Throughput (requests/sec)
  - Database query performance

**Logging**
- Centralización con ELK Stack (Elasticsearch, Logstash, Kibana)
- Niveles: ERROR, WARN, INFO, DEBUG
- Logs estructurados (JSON format)
- Retención: 90 días

**Alertas**
- Error rate > 5% → notificación inmediata
- Response time > 5s → alerta
- Disco BD > 80% → alerta
- Disponibilidad < 99.9% → alerta crítica

### 6.9 CI/CD Pipeline

```
Developer → Git Push → GitHub
                         │
                         ▼
                   ┌─────────────┐
                   │   GitHub    │
                   │   Actions   │
                   └─────────────┘
                         │
         ┌───────────────┼───────────────┐
         ▼               ▼               ▼
    ┌────────┐     ┌────────┐     ┌─────────┐
    │  Lint  │     │  Test  │     │  Build  │
    │(ESLint)│     │ (Jest) │     │ (Docker)│
    └────────┘     └────────┘     └─────────┘
                         │
                         ▼
                   ┌──────────┐
                   │  Deploy  │
                   │   to     │
                   │ Staging  │
                   └──────────┘
                         │
                         ▼
                   ┌──────────┐
                   │ E2E Tests│
                   │(Cypress) │
                   └──────────┘
                         │
                   Manual Approval
                         │
                         ▼
                   ┌──────────┐
                   │  Deploy  │
                   │   to     │
                   │Production│
                   └──────────┘
```

**Estrategia de Deployment:**
- Blue-Green Deployment para zero downtime
- Rollback automático si health check falla
- Feature flags para activar/desactivar funcionalidades

### 6.10 Entornos

1. **Development**: Local en máquina del developer
2. **Staging**: Clon de producción, para testing pre-release
3. **Production**: Entorno live de usuarios

### 6.11 Tecnologías Recomendadas

**Frontend:**
- React 18 + TypeScript
- Material-UI o Tailwind CSS
- Redux Toolkit
- React Query
- Axios

**Backend:**
- Node.js 18+ con Express
- TypeScript
- Prisma ORM (para PostgreSQL)
- Bull (job queue)
- Jest (testing)

**Base de Datos:**
- PostgreSQL 14+
- Redis 7+

**Infraestructura:**
- Docker + Docker Compose
- Kubernetes (para escalado futuro)
- AWS / Azure Cloud
- GitHub Actions (CI/CD)

**Monitorización:**
- Datadog / New Relic
- ELK Stack
- Sentry (error tracking)

---

## 7. ROADMAP Y FASES DE IMPLEMENTACIÓN

### Fase 1: MVP Core (Meses 1-3)
**Objetivo:** Sistema funcional básico para gestión de vacantes y candidatos

**Sprints:**
- **Sprint 1-2**: Setup proyecto, DB schema, autenticación
- **Sprint 3-4**: CRUD vacantes, portal público
- **Sprint 5-6**: Aplicaciones de candidatos, gestión básica

**Entregables:**
- ✓ Usuarios pueden crear vacantes
- ✓ Candidatos pueden aplicar
- ✓ Reclutadores pueden ver y evaluar candidatos
- ✓ Sistema de notificaciones por email básico

### Fase 2: Colaboración y Workflows (Meses 4-5)
**Objetivo:** Flujos de aprobación y colaboración entre equipos

**Entregables:**
- ✓ Asignación de candidatos a managers
- ✓ Cambios de estado con workflows
- ✓ Notas y comentarios
- ✓ Historial de evaluaciones

### Fase 3: Analytics y Admin (Meses 5-6)
**Objetivo:** Reportes, métricas y panel de administración

**Entregables:**
- ✓ Dashboard con métricas clave
- ✓ Reportes de funnels por vacante
- ✓ Exportación de datos
- ✓ Panel de administración completo
- ✓ Testing completo y preparación para lanzamiento

---

## 8. MÉTRICAS DE ÉXITO

### KPIs del Producto (post-lanzamiento)

**Métricas de Adopción:**
- 80% de vacantes gestionadas en el sistema (vs Excel/Email) en 3 meses
- 90% de reclutadores activos semanalmente
- NPS (Net Promoter Score) > 40

**Métricas de Eficiencia:**
- Reducción de time-to-hire en 30% vs. proceso anterior
- 50% menos tiempo en tareas administrativas para reclutadores
- 90% de candidatos reciben feedback en < 48h

**Métricas de Experiencia de Usuario:**
- Satisfaction score de candidatos > 4/5
- Tasa de abandono de aplicación < 20%
- < 3 clics para acciones principales

**Métricas Técnicas:**
- Uptime > 99.9%
- Response time p95 < 2 segundos
- Error rate < 1%

---

## 9. RIESGOS Y MITIGACIÓN

| Riesgo | Probabilidad | Impacto | Mitigación |
|--------|--------------|---------|------------|
| Baja adopción por usuarios | Media | Alto | Onboarding robusto, training, change management |
| Problemas de rendimiento con muchos candidatos | Media | Medio | Load testing, optimización DB, caché |
| Incumplimiento GDPR | Baja | Crítico | Auditoría legal, DPO, privacy by design |
| Dependencia de servicios externos (email) | Media | Medio | Fallback SMTP, queue con retry |
| Retrasos en desarrollo | Alta | Medio | Buffer en timeline, MVP scope control |
| Fuga de datos de candidatos | Baja | Crítico | Penetration testing, auditorías seguridad |

---

## 10. DEPENDENCIAS Y STAKEHOLDERS

### Stakeholders Clave
- **Sponsor**: Director de RRHH
- **Product Owner**: Tú (Product Manager)
- **Development Team**: 2 developers, 1 UX designer, 1 QA
- **Key Users**: Reclutadores (5), Hiring Managers (10)
- **Legal/Compliance**: DPO, Legal Counsel

### Dependencias Externas
- Proveedor de hosting cloud (AWS/Azure)
- Servicio de email (SendGrid/SES)
- Aprobación legal para tratamiento de datos
- Integración con sistema de email corporativo (SMTP)

---

## ANEXOS

### A. Glosario
- **ATS**: Applicant Tracking System
- **Time-to-hire**: Días desde publicación de vacante hasta aceptación de oferta
- **Funnel**: Embudo de conversión de candidatos entre etapas
- **GDPR**: General Data Protection Regulation
- **MVP**: Minimum Viable Product
- **RBAC**: Role-Based Access Control

### B. Referencias
- GDPR Compliance Guidelines: https://gdpr.eu
- ATS Industry Best Practices: Greenhouse Blog
- UI/UX Patterns for Recruitment: Nielsen Norman Group

---

**Documento Versión:** 1.0  
**Última Actualización:** 26 Noviembre 2025  
**Próxima Revisión:** Post-MVP (Mes 7)

