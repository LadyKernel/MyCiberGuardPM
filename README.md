# MyCiberGuardPM
<p align="center">
<img src="assets/logo.jpg" alt="MyCiberGuardPM Banner" />
</p>
> Caso de estudio de Project Management — Network Monitor CLI

Monitor ligero de tráfico de red con alertas automáticas vía Telegram para servidores VPS y cloud (GCP, AWS, DigitalOcean).

Repositorio técnico: [LadyKernel/MyIronGuard](https://github.com/LadyKernel/MyIronGuard/tree/main/network-monitor)

---

## Índice del proyecto

| # | Sección | Descripción |
|---|---------|-------------|
| 01 | [Contexto y Objetivo](./01-contexto-objetivo/README.md) | Por qué existe el proyecto, qué problema resuelve y qué define el éxito |
| 02 | [Alcance y Entregables](./02-alcance-entregables/README.md) | Qué está dentro del proyecto, qué está fuera y qué se produce |
| 03 | [Estructura de Trabajo](./03-estructura-trabajo/README.md) | WBS/EDT y cronograma por fases |
| 04 | [Stakeholders](./04-stakeholders/README.md) | Quién está implicado y qué rol tiene |
| 05 | [Matriz de Riesgos](./05-matriz-riesgos/README.md) | Riesgos identificados, probabilidad, impacto y plan de respuesta |
| 06 | [Requirements / PRD](./06-requirements-prd/README.md) | Épicas, historias de usuario y criterios de aceptación |
| 07 | [Roadmap y Métricas](./07-roadmap-metricas/README.md) | Evolución futura del producto y KPIs de éxito |
| 08 | [Uso Responsable de IA](./08-uso-responsable-ia/README.md) | Cómo se ha utilizado IA en este proyecto |
| 09 | [Lecciones Aprendidas](./09-lecciones-aprendidas/README.md) | Reflexión y mejoras futuras |

---

## Resumen ejecutivo

**Problema:** Los proveedores cloud no alertan de forma inmediata ante picos de tráfico de salida (*egress*). El usuario descubre el problema cuando recibe la factura.

**Solución:** Herramienta CLI ligera instalable con un solo comando, sin consumo notable de recursos, que envía alertas a Telegram únicamente cuando el tráfico supera umbrales críticos configurados por el usuario.

**Tecnología:** Bash · vnStat · jq · curl · API Telegram

**Licencia:** PolyForm Noncommercial License 1.0.0

---

*Proyecto desarrollado como hilo conductor del curso de Project Management — 2026*
*Autora: LadyKernel*
