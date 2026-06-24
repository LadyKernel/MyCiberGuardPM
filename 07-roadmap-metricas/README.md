# 07 — Roadmap y Métricas

## North Star Metric

> **Número de servidores activos que reciben alertas de tráfico de forma fiable cada semana**

Esta es la métrica central del producto. Todo lo demás (descargas, stars, forks) son señales de adopción, pero la North Star mide si el producto cumple su propósito real: que administradores de sistemas estén siendo avisados cuando lo necesitan.

---

## Product Roadmap

### Horizonte actual — MVP (completado)

| Feature | Estado | Versión |
|---------|--------|---------|
| Monitorización de tráfico diario y mensual | Completado | v1.0 |
| Alertas automáticas a Telegram con umbral configurable | Completado | v1.0 |
| Cálculo de coste estimado de egress | Completado | v1.0 |
| Sistema anti-spam con memoria de estado | Completado | v1.0 |
| Arquitectura en dos ramas: VPS estándar y GCP | Completado | v1.0 |
| Corrección de precisión decimal (LC_NUMERIC=C) | Completado | v1.1 |
| Fiabilidad en el guardado del estado de alerta | Completado | v1.1 |

---

### Corto plazo — 3 meses

| Feature | Descripción | Prioridad |
|---------|-------------|-----------|
| Integración con Slack | Alertas vía Webhook de Slack como canal alternativo a Telegram | Should Have |
| Integración con Discord | Alertas vía Webhook de Discord | Could Have |
| Soporte para más interfaces de red | Documentar y soportar ens3, enp0s3 y otros nombres de interfaz comunes | Should Have |

---

### Medio plazo — 6 meses

| Feature | Descripción | Prioridad |
|---------|-------------|-----------|
| Instalador unificado con autodetección | Fusionar las ramas `/vps-estandar` y `/gcloud` en un único instalador que detecte automáticamente la interfaz de red activa | Must Have |
| Soporte para más proveedores | Ampliar a Hetzner, Vultr, Linode con documentación específica | Should Have |
| Tests automatizados | Suite básica de pruebas para validar parsing de vnStat, cálculos y envío de alertas | Could Have |

---

### Largo plazo — 12 meses

| Feature | Descripción | Prioridad |
|---------|-------------|-----------|
| Dashboard web centralizado | Panel tipo SaaS (concepto: "MyCiberGuardPM Dashboard") para centralizar lecturas de varios servidores en un único punto | Could Have |
| API REST básica | Exponer los datos de tráfico vía API para integración con otras herramientas | Won't Have (MVP) |
| Soporte multi-servidor en una sola instalación | Gestionar varios VPS desde un único script maestro | Could Have |

---

## KPIs de éxito

### Métricas de adopción

| KPI | Descripción | Frecuencia de medición |
|-----|-------------|----------------------|
| Clones semanales del repositorio técnico | Indica cuántos usuarios están probando la herramienta | Semanal |
| GitHub Stars acumuladas | Validador de interés de la comunidad técnica | Mensual |
| Forks del repositorio | Indica que usuarios quieren modificar o adaptar la herramienta | Mensual |
| Issues abiertos | Señal de uso activo (los usuarios que no usan no reportan bugs) | Continuo |

### Métricas de calidad y retención

| KPI | Descripción | Objetivo |
|-----|-------------|---------|
| Tasa de falsos positivos en cálculo de bytes | % de alertas con cálculo de coste incorrecto | < 5% |
| Tiempo medio de resolución de bugs reportados | Días desde que se abre un issue hasta que se cierra con fix | < 7 días |
| Tasa de éxito en envío de alertas | % de alertas que llegan correctamente a Telegram | > 99% |
| Versiones con regresiones | Número de versiones que introducen errores en funcionalidad ya probada | 0 |

### Métricas académicas (contexto del curso)

| KPI | Descripción |
|-----|-------------|
| Cobertura de secciones PM | 9 de 9 secciones del hilo conductor completadas |
| Historias de usuario con criterio de aceptación | 9 de 9 historias con criterio definido |
| Riesgos documentados con plan de respuesta | 6 de 6 riesgos con mitigación documentada |

---

## Análisis competitivo

| Herramienta | Coste | Complejidad | Alertas en tiempo real | Foco en egress cloud |
|-------------|-------|------------|----------------------|---------------------|
| **Network Monitor CLI** | Gratuito | Baja (un comando) | Sí (Telegram) | Sí |
| Datadog | Desde 15$/host/mes | Alta | Sí | Parcial |
| Prometheus + Grafana | Gratuito (self-hosted) | Muy alta | Con configuración | No específico |
| Panel del proveedor cloud | Incluido | Media | Limitado | Sí, pero sin alertas automáticas |
| Netdata | Gratuito (Community) | Media | Sí | No específico |

**Ventaja diferencial:** La única herramienta de la comparativa que es gratuita, ligera, instalable en un comando y con alertas automáticas en Telegram con foco explícito en el coste de egress.

---

*← [Volver al índice](../README.md)*
