# 03 — Estructura de Trabajo (WBS/EDT) y Cronograma

## Work Breakdown Structure (WBS / EDT simplificada)

La siguiente estructura descompone el proyecto en bloques manejables de trabajo, organizados por fases lógicas de menor a mayor complejidad.

---

### Fase 1 — Inicio

| Tarea | Descripción |
|-------|-------------|
| 1.1 | Definición del contexto y el problema a resolver |
| 1.2 | Identificación de objetivos generales y específicos del proyecto |
| 1.3 | Selección y revisión del repositorio técnico base (MyIronGuard) |
| 1.4 | Definición del alcance: qué entra y qué no entra en el MVP |

### Fase 2 — Análisis y Diseño

| Tarea | Descripción |
|-------|-------------|
| 2.1 | Análisis de requisitos funcionales: monitorización, alertas, cálculo de costes |
| 2.2 | Análisis de restricciones técnicas: distintos proveedores, interfaces de red, herramientas disponibles |
| 2.3 | Diseño de la arquitectura en dos versiones: VPS estándar y GCP |
| 2.4 | Diseño del archivo `.env` y definición de las variables clave |
| 2.5 | Identificación de riesgos técnicos y de gestión |

### Fase 3 — Desarrollo y Configuración

| Tarea | Descripción |
|-------|-------------|
| 3.1 | Implementación del script de monitorización (lectura de tráfico vía vnStat) |
| 3.2 | Implementación de la lógica de alertas y sistema de memoria de estado |
| 3.3 | Integración con Telegram: bot, chat ID y formato del mensaje de alerta |
| 3.4 | Implementación del cálculo de coste de egress por GB configurado |
| 3.5 | Configuración de vnStat, jq y curl en distintos entornos Linux |

### Fase 4 — Pruebas y Validación

| Tarea | Descripción |
|-------|-------------|
| 4.1 | Pruebas de lectura de tráfico y parsing del JSON de vnStat |
| 4.2 | Pruebas de cálculo de costes con distintos valores de configuración |
| 4.3 | Pruebas de envío de alertas: casos de éxito y fallo de conexión |
| 4.4 | Pruebas en distintos proveedores o entornos (VPS estándar, GCP) |
| 4.5 | Validación del bajo consumo de recursos del script |
| 4.6 | Corrección de errores detectados durante las pruebas |

### Fase 5 — Despliegue y Documentación

| Tarea | Descripción |
|-------|-------------|
| 5.1 | Preparación del repositorio público (estructura, `.gitignore`, licencia) |
| 5.2 | Redacción del README principal con contexto, uso y notas técnicas |
| 5.3 | Redacción de la guía de instalación paso a paso |
| 5.4 | Redacción de la guía de configuración del `.env` |
| 5.5 | Documentación de troubleshooting y preguntas frecuentes |
| 5.6 | Redacción del changelog con versiones y descripción de cambios |

### Fase 6 — Cierre y Lecciones Aprendidas

| Tarea | Descripción |
|-------|-------------|
| 6.1 | Evaluación del cumplimiento de los objetivos específicos |
| 6.2 | Identificación de mejoras futuras y próximas versiones |
| 6.3 | Reflexión sobre el uso de IA en el proyecto |
| 6.4 | Cierre formal del proyecto hilo conductor |

---

## Cronograma básico

| Semana | Fase | Tareas principales | Hito |
|--------|------|--------------------|------|
| Semana 1 | Inicio y Análisis | Definir problema, objetivos, alcance y riesgos iniciales | Alcance validado |
| Semana 2 | Análisis y Diseño | Diseñar arquitectura, definir variables del `.env`, revisar el repositorio técnico base | Diseño listo |
| Semana 3 | Desarrollo | Implementar script principal, lógica de alertas e integración con Telegram | Script funcional v1.0 |
| Semana 4 | Pruebas y Correcciones | Validar lectura de tráfico, cálculos, alertas y rendimiento. Corregir errores | v1.1 estable |
| Semana 5 | Documentación | README, guía de instalación, guía de `.env`, troubleshooting y changelog | Repo público listo |
| Semana 6 | Cierre | Lecciones aprendidas, evaluación de objetivos y presentación del proyecto | Proyecto cerrado |

> **Nota:** El cronograma refleja el orden lógico del trabajo. Las fechas exactas pueden ajustarse según las iteraciones reales del proyecto.

---

## Control de versiones — Hitos técnicos

| Versión | Cambio principal | Motivación |
|---------|-----------------|------------|
| v1.0 | Script inicial con monitorización básica y alertas Telegram | Primera versión funcional del MVP |
| v1.1 | Corrección de precisión decimal (`LC_NUMERIC=C`) y robustez en el envío de alertas | Detectados errores en entornos con locale no inglés y fallos silenciosos en el envío |

---

*← [Volver al índice](../README.md)*
