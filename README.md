# STAQ — Sistema de Triaje Inteligente de A&G

> Documento de Visión del Producto · v1.1 · Ingeniería de Requisitos · UTPL

Solución de software para el triaje de **Apelaciones, Quejas y Reclamaciones (A&G)** en una aseguradora de salud, desarrollada por **Cognizant** como proveedor tecnológico.

---

## Tabla de contenidos

- [Contexto del problema](#contexto-del-problema)
- [Visión del producto](#visión-del-producto)
- [Objetivos de negocio](#objetivos-de-negocio)
- [Alcance](#alcance)
- [Stakeholders](#stakeholders)
- [Características principales](#características-principales)
- [Restricciones y suposiciones](#restricciones-y-suposiciones)
- [Riesgos de requisitos](#riesgos-de-requisitos)
- [Criterios de éxito](#criterios-de-éxito)
- [Información del documento](#información-del-documento)

---

## Contexto del problema

La aseguradora gestiona un volumen elevado y creciente de casos A&G recibidos por múltiples canales (portal, correo, teléfono, formularios). El proceso actual es **mayoritariamente manual**, con información dispersa en sistemas heterogéneos y clasificación basada en criterio individual del analista. Esto genera:

- Atrasos sistemáticos en los tiempos de respuesta comprometidos con afiliados y proveedores
- Incremento sostenido de costos administrativos por uso intensivo de personal especializado
- Riesgo regulatorio por incumplimiento de plazos establecidos por la normativa de salud
- Variabilidad en la calidad del triaje que genera reprocesos y decisiones contradictorias
- Falta de trazabilidad que dificulta auditorías internas y revisiones de calidad

---

## Visión del producto

> *Para los analistas de triaje, supervisores y directivos de operaciones de la aseguradora de salud, que requieren gestionar de forma eficiente y trazable un volumen elevado de A&G, el **STAQ** es una plataforma web interna de gestión de casos que integra automáticamente información multicanal, apoya la clasificación preliminar con reglas y NLP, detecta duplicidades y facilita la derivación inicial con trazabilidad completa. A diferencia del proceso actual basado en revisión manual de sistemas dispersos, el STAQ estandariza y acelera el triaje, libera al personal especializado para tareas de mayor valor agregado y proporciona la visibilidad operativa necesaria para cumplir compromisos regulatorios y de servicio.*

---

## Objetivos de negocio

| ID | Objetivo | Métrica de éxito | Plazo |
|----|----------|-----------------|-------|
| OB-01 | Reducir el tiempo de triaje inicial en ≥ 50% | Tiempo promedio de triaje < X horas (línea base pre-lanzamiento) | 3 meses post-lanzamiento |
| OB-02 | Alcanzar tasa de clasificación correcta ≥ 90% | % de casos sin reclasificación posterior (muestra mensual) | 6 meses post-lanzamiento |
| OB-03 | Detectar automáticamente ≥ 85% de casos duplicados | Tasa de detección validada por revisión de muestra mensual | 3 meses post-lanzamiento |
| OB-04 | Reducir en 40% reprocesos y reasignaciones por triaje incorrecto | N.° de reasignaciones por error de clasificación en el sistema | 6 meses post-lanzamiento |
| OB-05 | Visibilidad en tiempo real para el 100% de supervisores | ≥ 90% de supervisores usando el panel en el primer mes | 1 mes post-lanzamiento |
| OB-06 | Trazabilidad completa para auditorías sin requerimientos manuales | Cero observaciones por falta de evidencia en primera auditoría | 12 meses post-lanzamiento |

---

## Alcance

### Dentro del alcance

- Registro y recepción de casos A&G por múltiples canales (portal, email, teléfono, formulario)
- Consolidación automática de información de sistemas internos (pólizas, historiales, eventos asistenciales)
- Clasificación preliminar asistida por reglas y NLP: tipo, subtipo, categoría y nivel de prioridad
- Detección automática de duplicidades y casos relacionados
- Derivación inicial al área, rol o especialista con visibilidad de carga operativa
- Seguimiento del estado del caso durante la fase de triaje con alertas de SLA
- Trazabilidad completa de todas las acciones significativas sobre cada expediente
- Controles de acceso por perfil (RBAC) y cifrado de datos sensibles de salud

### Fuera del alcance

- Proceso completo de investigación y resolución de apelaciones y reclamaciones
- Módulos de pago y liquidación de reclamaciones
- Sistemas de contratación, emisión y renovación de pólizas
- Portales de autoatención para afiliados o proveedores
- Integración con sistemas de facturación médica
- Análisis post-resolución y gestión de calidad de fallos
- Migración de expedientes históricos anteriores a la implementación
- Módulos de reportería estratégica avanzada (Business Intelligence)

---

## Stakeholders

| ID | Grupo | Rol | Poder | Interés | Estrategia |
|----|-------|-----|-------|---------|------------|
| ST-01 | Director de Operaciones | Patrocinador | Alto | Alto | Gestionar de cerca |
| ST-02 | Analistas de triaje | Usuarios primarios del STAQ | Bajo | Alto | Mantener informados y comprometidos |
| ST-03 | Supervisores operativos | Supervisión y KPIs | Medio | Alto | Colaborar activamente |
| ST-04 | Equipo de Compliance / Legal | Validadores de trazabilidad | Alto | Alto | Mantener satisfecho |
| ST-05 | Equipo de Desarrollo / Cognizant | Construye e integra el sistema | Medio | Alto | Colaborar activamente |
| ST-06 | Ente Regulador de Salud | Control normativo externo | Alto | Bajo | Mantener satisfecho |
| ST-07 | Afiliados y Proveedores | Beneficiarios indirectos | Bajo | Alto | Mantener informados |
| ST-08 | Equipo de TI Interno | Infraestructura y seguridad | Medio | Medio | Colaborar en integración |

---

## Características principales

| ID | Característica | Prioridad |
|----|---------------|-----------|
| C-01 | Recepción multicanal | Alta |
| C-02 | Consolidación inteligente de información | Alta |
| C-03 | Clasificación asistida por reglas y NLP | Alta |
| C-04 | Detección de duplicidades y relaciones | Alta |
| C-05 | Derivación y asignación inicial | Alta |
| C-06 | Seguimiento en tiempo real y alertas de SLA | Alta |
| C-07 | Trazabilidad y auditoría | Alta |
| C-08 | Gestión de acceso y seguridad (RBAC) | Alta |
| C-09 | Adaptabilidad de reglas y categorías | Media |
| C-10 | Interfaz clara y consistente | Media |

---

## Restricciones y suposiciones

### Restricciones

| ID | Tipo | Descripción |
|----|------|-------------|
| R-01 | Tecnológica | Accesible desde Chrome, Firefox y Edge sin instalación adicional |
| R-02 | Legal/Normativa | Cumplimiento HIPAA / LOPDP: cifrado en tránsito y reposo, control de acceso y auditoría |
| R-03 | Integración | Integración vía APIs con sistemas internos definidos por TI de la aseguradora |
| R-04 | Seguridad | Sin almacenamiento de datos sensibles fuera del perímetro controlado |
| R-05 | Tiempo | Implementación por fases sin interrumpir la operación actual de triaje |
| R-06 | Usabilidad | Interfaz operativa en pantallas ≥ 1366×768 px para usuarios con distintos niveles técnicos |
| R-07 | Adaptabilidad | Reglas y categorías actualizables por administrador funcional sin modificar código fuente |

### Suposiciones clave

- `SA-01` La aseguradora proveerá acceso a APIs de sistemas internos antes del inicio del desarrollo de integraciones
- `SA-02` Los usuarios disponen de acceso a internet de banda ancha y equipos estándar
- `SA-04` Los interesados clave estarán disponibles ≥ 2 h/semana durante la fase de requisitos
- `SA-05` La aseguradora designará un representante funcional por área para validar reglas de clasificación
- `SA-07` La normativa regulatoria de SLAs permanecerá estable durante el desarrollo

---

## Riesgos de requisitos

| ID | Riesgo | Prob. | Impacto | Nivel | Mitigación |
|----|--------|-------|---------|-------|------------|
| RR-01 | Falta de involucramiento de usuarios clave | Alta | Alta | Crítico | Acuerdos formales de participación; representante de usuario por área |
| RR-02 | Reglas de clasificación no documentadas o inconsistentes | Alta | Alta | Crítico | Talleres de elicitación con Compliance antes del diseño del motor |
| RR-03 | Requisitos ambiguos por diversidad de canales y tipos de caso | Alta | Alta | Crítico | Plantillas de especificación + prototipado rápido para validación temprana |
| RR-04 | Scope creep hacia la resolución completa de casos | Media | Alta | Alto | Gestión formal de cambios; extensiones requieren aprobación del patrocinador |
| RR-05 | Conflicto entre interesados sobre prioridades de clasificación | Media | Media | Medio | Talleres de priorización facilitados por el BA |
| RR-06 | Datos de sistemas legados insuficientemente estructurados | Media | Alta | Alto | Inventario técnico de fuentes de datos antes del diseño de integraciones |
| RR-07 | Cambios regulatorios que alteren SLAs o trazabilidad | Baja | Alta | Medio | Monitoreo normativo periódico; diseño configurable de reglas |
| RR-08 | Resistencia al cambio del personal operativo | Media | Media | Medio | Gestión del cambio: comunicación temprana, pruebas piloto y capacitación progresiva |

---

## Criterios de éxito

| ID | Criterio | Medición | OB |
|----|----------|----------|----|
| CE-01 | Tiempo de triaje reducido ≥ 50% en los primeros 3 meses | Logs del sistema pre/post implementación | OB-01 |
| CE-02 | Tasa de clasificación correcta ≥ 90% a los 6 meses | % casos sin reclasificación (muestra mensual) | OB-02 |
| CE-03 | ≥ 85% de duplicados detectados automáticamente al registro | Auditoría mensual de muestra | OB-03 |
| CE-04 | Reprocesos por error de triaje reducidos en 40% a los 6 meses | Conteo de reasignaciones con causa 'error de triaje' | OB-04 |
| CE-05 | ≥ 90% de supervisores usan el panel de seguimiento diariamente en el primer mes | Tasa de uso por perfil (módulo de analítica) | OB-05 |
| CE-06 | Cero observaciones por falta de trazabilidad en primera auditoría | Informe de auditoría interna (primeros 12 meses) | OB-06 |
| CE-07 | ≥ 80% de analistas adoptan el STAQ como herramienta principal en el primer mes | Sesiones activas por perfil de analista | OB-01, OB-02 |
| CE-08 | Disponibilidad del sistema ≥ 99% en horario operativo | Monitoreo de infraestructura del proveedor (Cognizant) | Todos |

---

## Información del documento

| Campo | Valor |
|-------|-------|
| Proyecto | Solución de software para el triaje de A&G en aseguradora de salud |
| Versión | 1.1 |
| Fecha | 29/04/2026 |
| Responsable (BA) | Josué Pardo y Anthony Romero |
| Patrocinador | Dirección de Operaciones – Aseguradora de Salud |
| Organización | Aseguradora de Salud (Cliente Contratante) / Cognizant (Proveedor) |
| Estado | Borrador |
| Clasificación | Confidencial |

> **Estándares de referencia:** IEEE Std 830-1998 · BABOK v3 (IIBA, 2015) · Wiegers & Beatty (2013) · Gottesdiener (2005)
