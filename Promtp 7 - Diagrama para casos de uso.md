# Promtp 7 - Diagrama para casos de uso
Crea el código puml compatible exactamente para mermaid para los tres diagramas asociados a los casos de uso  Crear oferta, Revisar candidatos y Programar entrevista
***

### ✅ **Caso de uso: Crear oferta**
Aquí tienes el código **PlantUML compatible con Mermaid** para los tres diagramas de casos de uso solicitados: **Crear oferta**, **Revisar candidatos** y **Programar entrevista**. Cada uno está adaptado al formato de Mermaid (`flowchart`), que es el más cercano a la semántica de PlantUML para flujos.

***
Aquí tienes el código **PlantUML compatible con Mermaid** para los tres diagramas de casos de uso solicitados: **Crear oferta**, **Revisar candidatos** y **Programar entrevista**. Cada uno está adaptado al formato de Mermaid (`flowchart`), que es el más cercano a la semántica de PlantUML para flujos.

***

### ✅ **Caso de uso: Crear oferta**
``` Mermaid
flowchart TD
    A[Inicio] --> B[Reclutador autenticado]
    B --> C[Accede a sección Ofertas]
    C --> D[Selecciona 'Crear nueva oferta']
    D --> E[Completa título, descripción, requisitos]
    E --> F{Datos completos?}
    F -->|Sí| G[Guardar oferta en estado 'Borrador']
    F -->|No| H[Muestra error y solicita corrección]
    G --> I[Fin: Oferta creada]
    H --> D

```


***

### ✅ **Caso de uso: Revisar candidatos**
``` Mermaid
flowchart TD
    A[Inicio] --> B[Reclutador autenticado]
    B --> C[Accede a lista de candidatos]
    C --> D[Filtra por oferta o estado]
    D --> E[Selecciona candidato]
    E --> F[Muestra ficha completa]
    F --> G[Fin: Información visible]
```


***

### ✅ **Caso de uso: Programar entrevista**
``` Mermaid

flowchart TD
    A[Inicio] --> B[Reclutador autenticado]
    B --> C[Candidato en etapa 'Entrevista']
    C --> D[Selecciona fecha y hora]
    D --> E[Confirma programación]
    E --> F[Sistema envía invitación al candidato]
    F --> G[Fin: Entrevista agendada]

```


