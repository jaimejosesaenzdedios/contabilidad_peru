# Template Historia de Usuario

```markdown
## [ID] - [Título]

**Como** [rol de usuario],
**Quiero** [acción que desea realizar],
**Para** [beneficio/razón].

### Criterios de Aceptación

- [ ] [Criterio 1]
- [ ] [Criterio 2]
- [ ] [Criterio 3]

### Tareas Técnicas

- [ ] [Tarea 1]
- [ ] [Tarea 2]

### Estimación
**Story Points:** [1, 2, 3, 5, 8, 13]

### Notas Técnicas
[Información relevante para devs]

### Definition of Done
- [ ] Código implementado
- [ ] Tests unitarios passing
- [ ] Code review aprobado
- [ ] Validado contra criterios
- [ ] Merge a develop
```

---

## Ejemplo Completado

```markdown
## S1-US2 - Iniciar sesión con JWT

**Como** usuario del sistema,
**Quiero** iniciar sesión con mi usuario y contraseña,
**Para** acceder a las funcionalidades del sistema.

### Criterios de Aceptación

- [ ] Login con credenciales válidas retorna token JWT
- [ ] Login con credenciales inválidas retorna error 401
- [ ] Token expira después de 60 minutos
- [ ] Refresh token permite obtener nuevo access token

### Tareas Técnicas

- [ ] Implementar endpoint POST /api/auth/login
- [ ] Implementar endpoint POST /api/auth/refresh
- [ ] Crear dependencia get_current_user
- [ ] Configurar CORS en FastAPI
- [ ] Actualizar frontend para manejar token

### Estimación
**Story Points:** 5

### Notas Técnicas
- Usar python-jose para JWT
- Hash de passwords con bcrypt
- Access token: 60 min, Refresh token: 7 días

### Definition of Done
- [ ] Código implementado
- [ ] Tests unitarios passing
- [ ] Code review aprobado por Senior
- [ ] Validado contra criterios
- [ ] Merge a develop
```

---

## Checklist Sprint

| Item | Sprint 1 | Sprint 2 | Sprint 3 | Sprint 4 |
|------|----------|----------|----------|----------|
| Planning | ⬜ | ⬜ | ⬜ | ⬜ |
| Development | ⬜ | ⬜ | ⬜ | ⬜ |
| Code Review | ⬜ | ⬜ | ⬜ | ⬜ |
| Testing | ⬜ | ⬜ | ⬜ | ⬜ |
| Demo | ⬜ | ⬜ | ⬜ | ⬜ |
| Retrospective | ⬜ | ⬜ | ⬜ | ⬜ |
