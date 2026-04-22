# Ceremonias Scrum - Contabilidad Perú

## Calendario Semanal

| Día | Ceremonia | Hora | Duración | Participantes |
|-----|-----------|------|----------|---------------|
| Lunes | Daily Standup | 09:00 | 15 min | Equipo |
| Miércoles | Daily Standup | 09:00 | 15 min | Equipo |
| Viernes | Daily Standup | 09:00 | 15 min | Equipo |
| Sprint Day 1 | Sprint Planning | 09:00 | 2 hrs | Equipo + PO |
| Sprint Day 10 | Sprint Review | 10:00 | 1 hr | Equipo + PO |
| Sprint Day 10 | Retrospective | 11:00 | 45 min | Equipo |
| Quincenal | Backlog Grooming | 14:00 | 1 hr | Equipo |

---

## Daily Standup (15 minutos)

### Formato
```
1. ¿Qué hice ayer?
2. ¿Qué voy a hacer hoy?
3. ¿Tengo algún bloqueo?
```

### Reglas
- Todos los días a las 09:00
- Máximo 2 minutos por persona
- Solo el que habla tiene la palabra
- No entrar en detalles técnicos
- Registrar bloqueos en "Parking Lot"

### Template Notion/Slack
```
**📅 Daily - [Fecha]**

**@desarrollador1**
✅ Ayer: Hice X
📅 Hoy: Haré Y
🚧 Bloqueos: Ninguno / Descripción

**@desarrollador2**
✅ Ayer: Hice X
📅 Hoy: Haré Y  
🚧 Bloqueos: Ninguno / Descripción
```

### Parking Lot (Bloqueos)
- Documentar aquí temas que necesitan discusión
- Resolver después de la daily
- Asignar responsable

---

## Sprint Planning (2 horas)

### Objetivos
- Definir Sprint Goal
- Seleccionar items del Backlog
- Crear Sprint Backlog
- Estimar effort

### Agenda

| Tiempo | Actividad |
|--------|-----------|
| 0-15 min | Review Sprint anterior |
| 15-30 min | Presentación del PO |
| 30-90 min | Planning Poker / Estimación |
| 90-120 min | Commitment y Sprint Goal |

### Sprint Goal Template
```
Como [rol], queremos [funcionalidad], 
para [beneficio].
```

### Definition of Ready (DoR)
Antes de pull a Sprint:
- [ ] Criterios de aceptación claros
- [ ] Estimación asignada
- [ ] Dependencias identificadas
- [ ] Tests de aceptación definidos

### Definition of Done (DoD)
Para considerar completo:
- [ ] Código implementado
- [ ] Tests unitarios passing
- [ ] Code review aprobado
- [ ] Validado contra criterios
- [ ] Merge a develop

---

## Sprint Review (1 hora)

### Objetivos
- Demostrar lo construido
- Obtener feedback del PO
- Actualizar backlog

### Agenda

| Tiempo | Actividad |
|--------|-----------|
| 0-10 min | Welcome + Sprint Goal |
| 10-40 min | Demo de funcionalidades |
| 40-55 min | Feedback del PO |
| 55-60 min | Actualizar backlog |

### Formato Demo
- Cada feature: 3-5 minutos
- Mostrar funcionando
- Explicar qué se resolvió
- NO mostrar código

### Feedback Form
```
**Demo Feedback**

Funcionalidad: [Nombre]
✅ Cumple criterios: Sí/No
💭 Comentarios: [ ]
⭐ Prioridad: Alta/Media/Baja
```

---

## Retrospective (45 minutos)

### Objetivos
- Reflexionar sobre el sprint
- Identificar mejoras
- Acciones concretas

### Formato "Start, Stop, Continue"

| Categoría | Pregunta |
|-----------|----------|
| **Start** | ¿Qué deberíamos empezar a hacer? |
| **Stop** | ¿Qué deberíamos dejar de hacer? |
| **Continue** | ¿Qué deberíamos seguir haciendo? |

### Template
```
**Retrospective - Sprint [N]**

🟢 CONTINUE (seguir):
- [ ] Item 1
- [ ] Item 2

🔴 STOP (detener):
- [ ] Item 1
- [ ] Item 2

🟡 START (empezar):
- [ ] Item 1
- [ ] Item 2

📝 ACCIONES PARA PRÓXIMO SPRINT:
- [ ] Acción 1 → Responsable
- [ ] Acción 2 → Responsable
```

---

## Backlog Grooming (1 hora)

### Objetivos
- Refinar historias
- Clarificar requisitos
- Estimar nuevos items
- Identificar dependencias

### Reglas
- No más de 2 por semana
- Invitar solo a necesarios
- Preparar items antes

---

## Estimación

### Planning Poker
- Usar Fibonacci: 1, 2, 3, 5, 8, 13, 21
- Senior facilita
- Todos participan

### Reference Points
| SP | Equivalencia |
|----|-------------|
| 1 | 2-4 horas |
| 2 | 4-8 horas |
| 3 | 1-2 días |
| 5 | 2-3 días |
| 8 | 1 semana |
| 13 | 2 semanas |

---

## Métricas

### Velocity
```
Velocity = Sum(SP completados en sprint)
```

### Burndown
- Gráfico de trabajo restante
- Eje X: Días del sprint
- Eje Y: Story points restantes

### Cumulative Flow
- Visualizar WIP
- Identificar bottlenecks

---

## Tools

| Herramienta | Uso |
|-------------|-----|
| Trello | Board sprint |
| Notion | Documentación |
| Slack | Comunicación |
| GitHub | Código |
| Google Meet | Videollamadas |
