<p align="center">
  <img src="assets/logo.jpg" alt="MyCiberGuardPM Banner" width="700" />
</p>

<h1 align="center">MyCiberGuardPM</h1>

<p align="center">
  <strong>Caso de estudio integral de Project Management y Agile Management</strong><br>
  <em>Diseño, gobernanza y ciclo de vida de la herramienta Network Monitor CLI</em>
</p>

<p align="center">
  <a href="LICENSE"><img src="https://img.shields.io/badge/Licencia-PolyForm%20Noncommercial%201.0.0-blue.svg" alt="Licencia PolyForm" /></a>
  <img src="https://img.shields.io/badge/Tipo-Caso%20de%20Estudio%20Académico-purple.svg" alt="Caso de Estudio" />
  <img src="https://img.shields.io/badge/Estado-Finalizado%20%2F%20Inmutable-success.svg" alt="Estado Finalizado" />
  <img src="https://img.shields.io/badge/Autoría-LadyKernel%20(2026)-orange.svg" alt="Autoría LadyKernel" />
</p>

---

> [!IMPORTANT]
> **Aviso de Propiedad Intelectual y Alcance Documental**
> * **Naturaleza del repositorio:** Este proyecto contiene **únicamente documentación técnica y de gestión (PM/Agile)**. Constituye una entrega académica cerrada y evaluada.
> * **Código fuente:** La implementación funcional del script Bash reside de forma desacoplada en [`LadyKernel/MyIronGuard — /network-monitor`](https://github.com/LadyKernel/MyIronGuard/tree/main/network-monitor).
> * **Términos de uso:** Material protegido bajo **PolyForm Noncommercial License 1.0.0**. Queda prohibida su reproducción sin atribución o cualquier uso con fines comerciales. No se aceptan contribuciones que alteren el marco metodológico o el contenido del estudio.

---

## 📌 Contexto general

**MyCiberGuardPM** es el caso de estudio de Project Management del script **Network Monitor CLI** — una herramienta Bash para monitorizar tráfico de egress en servidores Linux y enviar alertas automáticas a Telegram.

Este repositorio contiene únicamente la documentación PM (contexto, requisitos, riesgos, roadmap…). El código fuente está en un repositorio separado: [LadyKernel/MyIronGuard — /network-monitor](https://github.com/LadyKernel/MyIronGuard/tree/main/network-monitor).

---

## 💡 El problema (The FinOps Problem)

En el entorno cloud actual (GCP, AWS, Azure), el tráfico de salida (*egress traffic*) es uno de los costes más variables e impredecibles para administradores de sistemas y desarrolladores independientes. Un pico inesperado —ataque, bucle mal gestionado o despliegue defectuoso— puede inflar la factura mensual en horas sin que el proveedor alerte en tiempo real.

**Network Monitor CLI** es una herramienta ligera instalable con un solo comando en cualquier servidor Linux. Monitoriza el tráfico de red, calcula el coste estimado de egress y envía alertas a Telegram únicamente cuando se superan los umbrales configurados — sin spam, sin agentes externos, sin coste adicional de infraestructura.

**Usuario objetivo:** Administradores de sistemas y desarrolladores que gestionan instancias VPS o cloud (GCP, DigitalOcean, AWS Free Tier) y necesitan visibilidad de costes sin la complejidad de herramientas como Datadog o Prometheus.

---

## 📊 Resumen ejecutivo

| Dimensión | Detalle |
|---|---|
| **Problema** | Falta de visibilidad inmediata del tráfico de egress → coste oculto descubierto en factura |
| **Solución** | CLI ligera: monitorización en tiempo real + alertas Telegram sin spam |
| **Stack** | Bash · vnStat · jq · curl · API Telegram |
| **Arquitecturas** | VPS estándar (`/vps-estandar`) · Google Cloud (`/gcloud`) |
| **Licencia** | [PolyForm Noncommercial License 1.0.0](LICENSE) |
| **Marco metodológico** | Project Management tradicional + Prácticas Agile (Scrum / Kanban) |

---

## 📂 Documentación de gestión de proyecto (PM)

Este repositorio aplica un marco de Project Management completo sobre el desarrollo real del script, como hilo conductor del curso. Desde la definición del problema hasta el cierre con reflexión y lecciones aprendidas.

| # | Sección | Entregables principales | Enlace |
|:---:|:---|:---|:---:|
| **01** | **Contexto y Objetivo** | Justificación del problema FinOps, definición de éxito y objetivos SMART | [Ver sección](./01-contexto-objetivo/README.md) |
| **02** | **Alcance y Entregables** | Alcance dentro/fuera de alcance, límites arquitectónicos y matriz MoSCoW | [Ver sección](./02-alcance-entregables/README.md) |
| **03** | **Estructura de Trabajo** | Desglose WBS/EDT, cronograma por fases e hitos clave | [Ver sección](./03-estructura-trabajo/README.md) |
| **04** | **Stakeholders** | Matriz RACI, mapa de interesados y estrategia de comunicación | [Ver sección](./04-stakeholders/README.md) |
| **05** | **Matriz de Riesgos** | Identificación de riesgos técnicos/cloud, probabilidad, impacto y mitigación | [Ver sección](./05-matriz-riesgos/README.md) |
| **06** | **Requirements / PRD** | Product Requirement Document: épicas, historias de usuario y criterios de aceptación | [Ver sección](./06-requirements-prd/README.md) |
| **07** | **Roadmap y Métricas** | Evolución del producto (Q1-Q4), OKRs de adopción y KPIs de rendimiento | [Ver sección](./07-roadmap-metricas/README.md) |
| **08** | **Uso Responsable de IA** | Registro de prompts, asistencia en arquitectura y gobernanza ética | [Ver sección](./08-uso-responsable-ia/README.md) |
| **09** | **Lecciones Aprendidas** | Retrospectiva final, deuda técnica identificada y mejoras metodológicas | [Ver sección](./09-lecciones-aprendidas/README.md) |

---

## 🔒 Integridad del repositorio y políticas

- **Reporte de incidencias o seguridad:** Consulta [SECURITY.md](./SECURITY.md) para el canal privado de reporte de vulnerabilidades.
- **Políticas de contribución:** Consulta [CONTRIBUTING.md](./CONTRIBUTING.md) antes de abrir cualquier interacción en este repositorio.

---

<p align="center">
  <sub>Caso de estudio desarrollado por <strong>LadyKernel</strong> — Curso de Project Management & Agile Management, 2026</sub>
</p>
