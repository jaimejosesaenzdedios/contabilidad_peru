# Sprint Backlog - Contabilidad Perú

## Equipo

| Rol | Asignación |
|-----|-------------|
| **PO** | Usuario externo |
| **Scrum Master** | Senior |
| **Senior** | Dev 1 |
| **Junior 1** | Dev 2 - Contabilidad + Inventario |
| **Junior 2** | Dev 3 - Facturación + Nomina |
| **Junior 3** | Dev 4 - Frontend + Testing |

---

## Sprint 1: Setup + Core (2 semanas)

### Objetivos
- Entorno de desarrollo configurado
- Autenticación JWT funcionando
- CRUD básico de usuarios y empresas
- Plan de cuentas funcional

| ID | Story | Tarea | Asignado | SP | Estado |
|----|-------|-------|----------|-----|--------|
| S1-US1 | Como dev, quiero el entorno configurado | Configurar docker-compose, pytest, lint | Senior | 3 | ⬜ |
| S1-US2 | Como usuario, quiero iniciar sesión | Implementar JWT login/refresh | Senior | 5 | ⬜ |
| S1-US3 | Como admin, quiero gestionar usuarios | CRUD usuarios API + Frontend | Senior | 3 | ⬜ |
| S1-US4 | Como admin, quiero gestionar empresas | CRUD empresas API + Frontend | Junior 1 | 5 | ⬜ |
| S1-US5 | Como contador, quiero crear plan de cuentas | API plan de cuentas PCGE | Junior 1 | 5 | ⬜ |
| S1-US6 | Como contador, quiero registrar asientos | API asientos contables | Junior 1 | 5 | ⬜ |
| S1-US7 | Como usuario, quiero ver dashboard | Setup frontend + Login | Junior 3 | 3 | ⬜ |

**Total SP: 29**

---

## Sprint 2: Contabilidad + Inventario (2 semanas)

### Objetivos
- Asientos contables completos
- Reportes contables básicos
- Gestión de inventario

| ID | Story | Tarea | Asignado | SP | Estado |
|----|-------|-------|----------|-----|--------|
| S2-US1 | Como contador, quiero aprobar asientos | Endpoint aprobar/cerrar | Junior 1 | 3 | ⬜ |
| S2-US2 | Como contador, quiero ver balance | Reporte balance comprobación | Junior 1 | 5 | ⬜ |
| S2-US3 | Como contador, quiero ver mayor analítico | Reporte mayor por cuenta | Junior 1 | 5 | ⬜ |
| S2-US4 | Como almacenista, quiero gestionar almacenes | CRUD almacenes API | Junior 1 | 2 | ⬜ |
| S2-US5 | Como almacenista, quiero gestionar productos | CRUD productos API + Frontend | Junior 1 | 5 | ⬜ |
| S2-US6 | Como almacenista, quiero registrar movimientos | Kardex - entradas/salidas | Junior 1 | 5 | ⬜ |
| S2-US7 | Como usuario, quiero ver lista de asientos | Frontend asientos contables | Junior 3 | 3 | ⬜ |

**Total SP: 28**

---

## Sprint 3: Facturación Electrónica (2 semanas)

### Objetivos
- Crear comprobantes electrónicos
- Integración con SUNAT (mock)
- Generación XML

| ID | Story | Tarea | Asignado | SP | Estado |
|----|-------|-------|----------|-----|--------|
| S3-US1 | Como contador, quiero crear factura | API comprobantes (01, 03) | Junior 2 | 5 | ⬜ |
| S3-US2 | Como contador, quiero crear nota crédito/débito | API NC (07) / ND (08) | Junior 2 | 5 | ⬜ |
| S3-US3 | Como contador, quiero generar XML | Generar XML CPE | Junior 2 | 8 | ⬜ |
| S3-US4 | Como contador, quiero firmar CPE | Firma digital (stub) | Senior | 5 | ⬜ |
| S3-US5 | Como contador, quiero enviar a SUNAT | Integración SUNAT (stub) | Junior 2 | 5 | ⬜ |
| S3-US6 | Como contador, quiero ver mis comprobantes | Frontend facturación | Junior 3 | 5 | ⬜ |
| S3-US7 | Como contador, quiero anular comprobante | Anular CPE | Junior 2 | 3 | ⬜ |

**Total SP: 36**

---

## Sprint 4: Nómina + Mejoras (2 semanas)

### Objetivos
- Gestión de empleados
- Generación de planillas
- Mejoras y fixes

| ID | Story | Tarea | Asignado | SP | Estado |
|----|-------|-------|----------|-----|--------|
| S4-US1 | Como RRHH, quiero gestionar empleados | CRUD empleados API | Junior 2 | 5 | ⬜ |
| S4-US2 | Como RRHH, quiero generar planilla | Generación automática planilla | Junior 2 | 8 | ⬜ |
| S4-US3 | Como RRHH, quiero exportar PLAME | Exportar archivo PLAME | Junior 2 | 5 | ⬜ |
| S4-US4 | Como usuario, quiero gestionar asistencia | Registro asistencia | Junior 2 | 3 | ⬜ |
| S4-US5 | Como usuario, quiero ver reportes nomina | Dashboard nomina frontend | Junior 3 | 3 | ⬜ |
| S4-US6 | Como equipo, queremos mejorar UX | Mejoras UI/UX generales | Junior 3 | 5 | ⬜ |
| S4-US7 | Como equipo, queremos tests coverage | Tests unitarios + coverage > 70% | Todos | 8 | ⬜ |

**Total SP: 37**

---

## Pendientes (Backlog)

| ID | Story | Prioridad | SP |
|----|-------|-----------|-----|
| BP-US1 | Integración real SUNAT | Alta | 13 |
| BP-US2 | Generación PDF comprobantes | Alta | 8 |
| BP-US3 | PLE mensual | Media | 8 |
| BP-US4 | Migración datos legacy | Media | 5 |
| BP-US5 | Despliegue producción | Alta | 5 |
| BP-US6 | Documentación usuario | Baja | 3 |
| BP-US7 | Módulo CTS | Baja | 5 |
| BP-US8 | Módulo Gratificaciones | Baja | 5 |

---

## Definition of Ready

- [ ] Criterios de aceptación claros
- [ ] Estimación asignada (SP)
- [ ] Dependencias identificadas
- [ ] wireframes/diseño si aplica

## Definition of Done

- [ ] Código implementado
- [ ] Tests unitarios passing
- [ ] Code review aprobado
- [ ] Validado contra criterios
- [ ] Merge a develop

---

## Métricas

| Métrica | Objetivo |
|---------|----------|
| Velocidad Sprint 1 | 29 SP |
| Code Coverage | > 70% |
| Bugs en producción | < 5 |
| Sprint Completion | 100% |

---

## Conventions

### Git
- Rama develop para integración
- Feature branches: `feature/TICKET-ID-descripcion`
- Commits: `TICKET-ID: descripción`

### Código
- PEP 8 para Python
- ESLint + Prettier para JS/TS
- TypeScript strict mode

### API REST
- Nombres plurales: `/api/usuarios`
- Métodos HTTP estándar
- Códigos de estado correctos
