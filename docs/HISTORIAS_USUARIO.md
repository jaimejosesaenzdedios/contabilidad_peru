# Historias de Usuario Completas - Contabilidad Perú

---

## SPRINT 1: Setup + Core (2 semanas)

### S1-US1 - Setup Entorno de Desarrollo

**Como** desarrollador,
**Quiero** tener el entorno de desarrollo configurado,
**Para** poder iniciar a programar rápidamente.

#### Criterios de Aceptación
- [ ] Docker-compose levanta todos los servicios
- [ ] Backend responde en localhost:8000
- [ ] Frontend responde en localhost:5173
- [ ] API docs disponible en /docs
- [ ] Tests unitarios ejecutándose
- [ ] Linting configurado (ruff/flake8)

#### Tareas Técnicas
- [ ] Verificar docker-compose.yml
- [ ] Configurar pytest en backend
- [ ] Configurar ESLint + Prettier en frontend
- [ ] Crear script de setup.sh
- [ ] Documentar instalación local

**Estimación:** 3 SP  
**Asignado:** Senior

---

### S1-US2 - Iniciar Sesión con JWT

**Como** usuario del sistema,
**Quiero** iniciar sesión con mi usuario y contraseña,
**Para** acceder a las funcionalidades del sistema.

#### Criterios de Aceptación
- [ ] Login con credenciales válidas retorna access_token y refresh_token
- [ ] Login con credenciales inválidas retorna error 401
- [ ] Access token expira en 60 minutos
- [ ] Refresh token permite obtener nuevo access_token
- [ ] Endpoint /auth/me retorna datos del usuario actual

#### Tareas Técnicas
- [ ] Implementar endpoint POST /api/auth/login
- [ ] Implementar endpoint POST /api/auth/refresh
- [ ] Implementar endpoint GET /api/auth/me
- [ ] Crear dependencia get_current_user
- [ ] Configurar CORS en FastAPI

**Estimación:** 5 SP  
**Asignado:** Senior

---

### S1-US3 - Gestionar Usuarios

**Como** administrador,
**Quiero** gestionar usuarios del sistema,
**Para** controlar el acceso de personas a la aplicación.

#### Criterios de Aceptación
- [ ] Listar todos los usuarios (solo admin)
- [ ] Crear nuevo usuario con username, email, password
- [ ] Ver detalles de un usuario
- [ ] Actualizar datos de usuario
- [ ] Eliminar usuario (soft delete)
- [ ] Asignar empresa a usuario

#### Tareas Técnicas
- [ ] Implementar GET /api/core/usuarios
- [ ] Implementar POST /api/core/usuarios
- [ ] Implementar GET /api/core/usuarios/{id}
- [ ] Implementar PUT /api/core/usuarios/{id}
- [ ] Implementar DELETE /api/core/usuarios/{id}
- [ ] Crear componente Frontend: ListaUsuarios
- [ ] Crear componente Frontend: FormUsuario

**Estimación:** 3 SP  
**Asignado:** Senior

---

### S1-US4 - Gestionar Empresas

**Como** administrador,
**Quiero** gestionar empresas (tenants),
**Para** administrar las empresas que usan el sistema.

#### Criterios de Aceptación
- [ ] Listar empresas
- [ ] Crear empresa con RUC, razón social, dirección
- [ ] Ver detalles de empresa
- [ ] Actualizar datos de empresa
- [ ] Activar/desactivar empresa
- [ ] Configurar serie de documentos

#### Tareas Técnicas
- [ ] Implementar GET /api/core/empresas
- [ ] Implementar POST /api/core/empresas
- [ ] Implementar GET /api/core/empresas/{id}
- [ ] Implementar PUT /api/core/empresas/{id}
- [ ] Implementar DELETE /api/core/empresas/{id}
- [ ] CRUD series documentales
- [ ] Crear componente Frontend: ListaEmpresas
- [ ] Crear componente Frontend: FormEmpresa

**Estimación:** 5 SP  
**Asignado:** Junior 1

---

### S1-US5 - Plan de Cuentas PCGE

**Como** contador,
**Quiero** crear y gestionar el plan de cuentas,
**Para** registrar las transacciones contables.

#### Criterios de Aceptación
- [ ] Crear cuenta contable con código, nombre, naturaleza
- [ ] Jerarquía de cuentas (padre-hijo)
- [ ] Tipos: activo, pasivo, patrimonio, resultado
- [ ] Solo cuentas nivel 6 aceptan movimientos
- [ ] Listar cuentas por empresa

#### Tareas Técnicas
- [ ] Modelo PlanCuenta con jerarquía
- [ ] GET/POST /api/contabilidad/plan-cuentas
- [ ] GET/PUT/DELETE /api/contabilidad/plan-cuentas/{id}
- [ ] Validar acepta_movimiento por nivel
- [ ] Frontend: ListaCuentas
- [ ] Frontend: Arbol de cuentas

**Estimación:** 5 SP  
**Asignado:** Junior 1

---

### S1-US6 - Registrar Asientos Contables

**Como** contador,
**Quiero** registrar asientos contables,
**Para** registrar las operaciones financieras.

#### Criterios de Aceptación
- [ ] Crear asiento con fecha, número, glosa
- [ ] Agregar múltiples líneas (detalles)
- [ ] Validar partida doble (debe = haber)
- [ ] Solo cuentas nivel 6 pueden usarse
- [ ] Calcular totales automáticamente

#### Tareas Técnicas
- [ ] Modelo Asiento, DetalleAsiento
- [ ] POST /api/contabilidad/asientos
- [ ] Validación partida doble
- [ ] GET /api/contabilidad/asientos/{id}
- [ ] Frontend: FormAsiento
- [ ] Frontend: ListaAsientos

**Estimación:** 5 SP  
**Asignado:** Junior 1

---

### S1-US7 - Dashboard y Login Frontend

**Como** usuario,
**Quiero** acceder a la aplicación desde el frontend,
**Para** usar la interfaz visual.

#### Criterios de Aceptación
- [ ] Pantalla de login funcional
- [ ] Redirección después de login exitoso
- [ ] Store de autenticación (Zustand)
- [ ] Proteger rutas privadas
- [ ] Logout borra token

#### Tareas Técnicas
- [ ] Configurar vite proxy
- [ ] Actualizar api.ts endpoints
- [ ] Componente Login.tsx
- [ ] Store auth.ts con JWT
- [ ] ProtectedRoute component
- [ ] Layout principal

**Estimación:** 3 SP  
**Asignado:** Junior 3

---

## SPRINT 2: Contabilidad + Inventario (2 semanas)

### S2-US1 - Aprobar y Cerrar Asientos

**Como** contador,
**Quiero** aprobar y cerrar asientos,
**Para** validar y finalize las transacciones.

#### Criterios de Aceptación
- [ ] Aprobar asiento (cambia estado)
- [ ] Cerrar asiento (impide modificaciones)
- [ ] Solo asientos aprobados pueden cerrarse
- [ ] Registrar usuario que aprueba

#### Tareas Técnicas
- [ ] POST /api/contabilidad/asientos/{id}/aprobar
- [ ] POST /api/contabilidad/asientos/{id}/cerrar
- [ ] Validar transiciones estado
- [ ] Frontend: Botones aprobar/cerrar

**Estimación:** 3 SP  
**Asignado:** Junior 1

---

### S2-US2 - Balance de Comprobación

**Como** contador,
**Quiero** ver el balance de comprobación,
**Para** verificar que los libros estén cuadrados.

#### Criterios de Aceptación
- [ ] Reporte por fecha
- [ ] Lista de cuentas con debe/haber
- [ ] Solo asientos cerrados
- [ ] Totales debe = haber

#### Tareas Técnicas
- [ ] GET /api/contabilidad/reportes/balance_comprobacion
- [ ] Query con filtros fecha
- [ ] Cálculo de saldos
- [ ] Frontend: Tabla balance

**Estimación:** 5 SP  
**Asignado:** Junior 1

---

### S2-US3 - Libro Mayor

**Como** contador,
**Quiero** ver el mayor analítico por cuenta,
**Para** ver el detalle de movimientos.

#### Criterios de Aceptación
- [ ] Filtrar por cuenta, fecha inicio, fecha fin
- [ ] Ver todos los movimientos
- [ ] Saldo acumulado
- [ ] Solo asientos cerrados

#### Tareas Técnicas
- [ ] GET /api/contabilidad/reportes/mayor
- [ ] Query con filtros
- [ ] Calcular saldo progresivo
- [ ] Frontend: MayorCuenta

**Estimación:** 5 SP  
**Asignado:** Junior 1

---

### S2-US4 - Gestionar Almacenes

**Como** almacenista,
**Quiero** gestionar almacenes,
**Para** organizar el inventario.

#### Criterios de Aceptación
- [ ] Crear almacén (código, nombre, dirección)
- [ ] Definir almacén principal
- [ ] Activar/desactivar
- [ ] Listar por empresa

#### Tareas Técnicas
- [ ] Modelo Almacen
- [ ] GET/POST /api/inventario/almacenes
- [ ] Frontend: ListaAlmacenes

**Estimación:** 2 SP  
**Asignado:** Junior 1

---

### S2-US5 - Gestionar Productos

**Como** almacenista,
**Quiero** gestionar productos,
**Para** mantener el catálogo deitems.

#### Criterios de Aceptación
- [ ] Crear producto (código, nombre, categoría)
- [ ] Unidad de medida
- [ ] Stock inicial, mínimo, máximo
- [ ] Precio costo y venta
- [ ] Afecta IGV sí/no

#### Tareas Técnicas
- [ ] Modelo Producto
- [ ] CRUD /api/inventario/productos
- [ ] Frontend: ListaProductos
- [ ] Frontend: FormProducto

**Estimación:** 5 SP  
**Asignado:** Junior 1

---

### S2-US6 - Movimientos de Inventario (Kardex)

**Como** almacenista,
**Quiero** registrar entradas y salidas,
**Para** controlar el stock.

#### Criterios de Aceptación
- [ ] Registrar entrada (compra)
- [ ] Registrar salida (venta)
- [ ] Calcular costo promedio
- [ ] Validar stock disponible en salidas
- [ ] Historial por producto

#### Tareas Técnicas
- [ ] Modelo Kardex
- [ ] POST /api/inventario/kardex
- [ ] Lógica PEPS/Promedio
- [ ] GET /api/inventario/productos/{id}/kardex
- [ ] Frontend: RegistroKardex
- [ ] Frontend: HistorialKardex

**Estimación:** 5 SP  
**Asignado:** Junior 1

---

### S2-US7 - Frontend Asientos Contables

**Como** contador,
**Quiero** ver y editar asientos desde frontend,
**Para** facilitar el trabajo diario.

#### Criterios de Aceptación
- [ ] Lista de asientos con filtros
- [ ] Ver detalle de asiento
- [ ] Estado visual (borrador/aprobado/cerrado)
- [ ] Acciones según estado

#### Tareas Técnicas
- [ ] Componente ListaAsientos
- [ ] Componente DetalleAsiento
- [ ] Integración con API
- [ ] Estilos según estado

**Estimación:** 3 SP  
**Asignado:** Junior 3

---

## SPRINT 3: Facturación Electrónica (2 semanas)

### S3-US1 - Crear Factura/Boleta

**Como** contador,
**Quiero** crear comprobantes electrónicos,
**Para** emitirlos a clientes.

#### Criterios de Aceptación
- [ ] Crear Factura (01) o Boleta (03)
- [ ] Datos cliente (RUC/DNI, nombre, dirección)
- [ ] Agregar líneas (producto, cantidad, precio)
- [ ] Calcular IGV (18%) automáticamente
- [ ] Calcular totales
- [ ] Numeración automática

#### Tareas Técnicas
- [ ] Modelo Comprobante, DetalleComprobante
- [ ] POST /api/facturacion/comprobantes
- [ ] GET /api/facturacion/comprobantes
- [ ] Cálculo automático de importes
- [ ] Frontend: FormComprobante
- [ ] Frontend: ListaComprobantes

**Estimación:** 5 SP  
**Asignado:** Junior 2

---

### S3-US2 - Crear Nota Crédito/Débito

**Como** contador,
**Quiero** crear notas de crédito y débito,
**Para** modificar o corregir comprobantes.

#### Criterios de Aceptación
- [ ] Crear Nota de Crédito (07)
- [ ] Crear Nota de Débito (08)
- [ ] Referenciar comprobante original
- [ ] Seleccionar motivo
- [ ] Validar que CPE original no esté anulado

#### Tareas Técnicas
- [ ] Agregar tipo_documento 07, 08
- [ ] Modelo DocumentoReferencia
- [ ] Validación de referencia
- [ ] Frontend: FormNotaCredito
- [ ] Frontend: FormNotaDebito

**Estimación:** 5 SP  
**Asignado:** Junior 2

---

### S3-US3 - Generar XML CPE

**Como** contador,
**Quiero** generar el XML del comprobante,
**Para** prepararlo para firma.

#### Criterios de Aceptación
- [ ] Generar XML según formato SUNAT
- [ ] Estructura UBL 2.1
- [ ] Incluir información del emisor
- [ ] Incluir detalles del comprobante
- [ ] Generar hash (igestion)

#### Tareas Técnicas
- [ ] Función generar_xml(comprobante_id)
- [ ] Templates XML UBL
- [ ] POST /api/facturacion/comprobantes/{id}/generar
- [ ] Guardar xml_firmado (vacío por ahora)
- [ ] Calcular hash

**Estimación:** 8 SP  
**Asignado:** Junior 2

---

### S3-US4 - Firmar CPE (Stub)

**Como** contador,
**Quiero** firmar digitalmente el CPE,
**Para** cumplir requisitos SUNAT.

#### Criterios de Aceptación
- [ ] stub que simula firma
- [ ] Actualizar estado a "firmado"
- [ ] Marcar tiempo de firma

#### Tareas Técnicas
- [ ] Función firmar_xml(comprobante_id)
- [ ] POST /api/facturacion/comprobantes/{id}/firmar
- [ ] stub ( retorna ok)
- [ ] NOTA: Implementar con xmlsec después

**Estimación:** 5 SP  
**Asignado:** Senior

---

### S3-US5 - Enviar a SUNAT (Stub)

**Como** contador,
**Quiero** enviar el CPE a SUNAT,
**Para** obtener aceptación.

#### Criterios de Aceptación
- [ ] stub que simula envío
- [ ] Guardar CDR de respuesta
- [ ] Actualizar estado según respuesta
- [ ] Historial de envios

#### Tareas Técnicas
- [ ] Función enviar_sunat(comprobante_id)
- [ ] POST /api/facturacion/comprobantes/{id}/enviar_sunat
- [ ] stub (retorna aceptado)
- [ ] Guardar en HistorialEnvio
- [ ] NOTA: Implementar integración real después

**Estimación:** 5 SP  
**Asignado:** Junior 2

---

### S3-US6 - Frontend Facturación

**Como** contador,
**Quiero** gestionar comprobantes desde frontend,
**Para** facilitar el trabajo.

#### Criterios de Aceptación
- [ ] Lista de comprobantes con filtros
- [ ] Ver detalle
- [ ] Acciones: generar, firmar, enviar
- [ ] Indicador de estado visual

#### Tareas Técnicas
- [ ] Componente ListaComprobantes
- [ ] Componente DetalleComprobante
- [ ] Botones de acción
- [ ] Estados con colores

**Estimación:** 5 SP  
**Asignado:** Junior 3

---

### S3-US7 - Anular Comprobante

**Como** contador,
**Quiero** anular un comprobante,
**Para** corregir errores.

#### Criterios de Aceptación
- [ ] Solo comprobantes aceptados pueden anularse
- [ ] Cambiar estado a "anulado"
- [ ] Registrar motivo
- [ ] No permite modificaciones después

#### Tareas Técnicas
- [ ] POST /api/facturacion/comprobantes/{id}/anular
- [ ] Validar estado actual
- [ ] Frontend: Botón anular

**Estimación:** 3 SP  
**Asignado:** Junior 2

---

## SPRINT 4: Nómina + Mejoras (2 semanas)

### S4-US1 - Gestionar Empleados

**Como** RRHH,
**Quiero** gestionar empleados,
**Para** mantener el registro del personal.

#### Criterios de Aceptación
- [ ] Crear empleado (datos personales, laborales)
- [ ] Tipo documento: DNI, RUC, CE
- [ ] Datos laborales: cargo, área, fecha ingreso
- [ ] Estado activo/inactivo
- [ ] Fecha de cese

#### Tareas Técnicas
- [ ] Modelo Empleado
- [ ] CRUD /api/nomina/empleados
- [ ] Frontend: ListaEmpleados
- [ ] Frontend: FormEmpleado

**Estimación:** 5 SP  
**Asignado:** Junior 2

---

### S4-US2 - Generar Planilla

**Como** RRHH,
**Quiero** generar la planilla mensual,
**Para** calcular remuneraciones.

#### Criterios de Aceptación
- [ ] Seleccionar período (YYYY-MM)
- [ ] Calcular ingresos (básico, bonificaciones)
- [ ] Calcular descuentos (AFP, ONP, faltas)
- [ ] Calcular neto a pagar
- [ ] Resumen por empleado

#### Tareas Técnicas
- [ ] Modelo Remuneracion, Descuento
- [ ] POST /api/nomina/planillas/{id}/generar_planilla
- [ ] Lógica cálculo AFP (10% + 0.5% + 1.35%)
- [ ] Frontend: VistaPlanilla

**Estimación:** 8 SP  
**Asignado:** Junior 2

---

### S4-US3 - Exportar PLAME

**Como** RRHH,
**Quiero** exportar archivo PLAME,
**Para** declarar a SUNAT.

#### Criterios de Aceptación
- [ ] Generar archivo texto formato PLAME
- [ ] Incluir todos los empleados
- [ ] Formato según SUNAT
- [ ] Descargar archivo

#### Tareas Técnicas
- [ ] Función generar_plame(planilla_id)
- [ ] GET /api/nomina/planillas/{id}/generar_plame
- [ ] Formato: 7.1, 7.2, 7.3
- [ ] Frontend: Botón descargar

**Estimación:** 5 SP  
**Asignado:** Junior 2

---

### S4-US4 - Registro de Asistencia

**Como** RRHH,
**Quiero** registrar asistencia de empleados,
**Para** controlar llegadas tarde y faltas.

#### Criterios de Aceptación
- [ ] Registrar hora entrada
- [ ] Registrar hora salida
- [ ] Calcular horas trabajadas
- [ ] Registrar falta
- [ ] Registrar permiso

#### Tareas Técnicas
- [ ] Modelo Asistencia
- [ ] GET/POST /api/nomina/asistencias
- [ ] Cálculo horas trabajadas
- [ ] Frontend: RegistroAsistencia
- [ ] Frontend: ResumenAsistencia

**Estimación:** 3 SP  
**Asignado:** Junior 2

---

### S4-US5 - Dashboard Nómina

**Como** RRHH,
**Quiero** ver dashboard de nómina,
**Para** visualizar indicadores.

#### Criterios de Aceptación
- [ ] Total empleados activos
- [ ] Planilla del mes actual
- [ ] Indicadores de asistencia
- [ ] Gráficos básicos

#### Tareas Técnicas
- [ ] Componente DashboardNómina
- [ ] KPIs: empleados, payroll
- [ ] Gráficos (recharts/charjs)
- [ ] Integración con APIs

**Estimación:** 3 SP  
**Asignado:** Junior 3

---

### S4-US6 - Mejoras UI/UX

**Como** usuario,
**Quiero** mejor experiencia de usuario,
**Para** trabajar más cómodo.

#### Criterios de Aceptación
- [ ] Mejoras de diseño general
- [ ] Feedback visual de acciones
- [ ] Loading states
- [ ] Mensajes de error claros
- [ ] Responsive design

#### Tareas Técnicas
- [ ] Revisión UI general
- [ ] Agregar loaders
- [ ] Toast notifications
- [ ] Mejoras responsive

**Estimación:** 5 SP  
**Asignado:** Junior 3

---

### S4-US7 - Cobertura de Tests

**Como** equipo,
**Quiero** tener tests unitarios,
**Para** asegurar calidad.

#### Criterios de Aceptación
- [ ] Coverage > 70%
- [ ] Tests en APIs críticas
- [ ] Tests en lógica de negocio
- [ ] Tests en componentes frontend

#### Tareas Técnicas
- [ ] Configurar coverage
- [ ] Tests auth
- [ ] Tests contabilidad
- [ ] Tests facturación
- [ ] Tests componentes React

**Estimación:** 8 SP  
**Asignado:** Todos

---

## BACKLOG PENDIENTE

| ID | Story | Prioridad |
|----|-------|-----------|
| BP-US1 | Integración real SUNAT | Alta |
| BP-US2 | Generación PDF comprobantes | Alta |
| BP-US3 | PLE mensual | Media |
| BP-US4 | Migración datos legacy | Media |
| BP-US5 | Despliegue producción | Alta |
| BP-US6 | Documentación usuario | Baja |
| BP-US7 | Módulo CTS | Baja |
| BP-US8 | Módulo Gratificaciones | Baja |
