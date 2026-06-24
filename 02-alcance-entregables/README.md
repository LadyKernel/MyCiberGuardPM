# 02 — Alcance y Entregables del Proyecto

## Incluido en el alcance

| Componente | Descripción |
|------------|-------------|
| Script de monitorización | Herramienta CLI en Bash que lee tráfico de red mediante vnStat |
| Integración con Telegram | Alertas automáticas vía bot de Telegram con TOKEN y CHAT_ID configurables |
| Configuración por variables de entorno | Archivo `.env` con todos los parámetros ajustables por el usuario |
| Arquitecturas soportadas | Dos ramas de instalación: `/vps-estandar` (interfaz eth0) y `/gcloud` (interfaz ens4) |
| Sistema anti-spam de alertas | Memoria de estado que evita el envío de notificaciones repetidas |
| Cálculo de coste estimado de egress | Estimación del coste de tráfico de salida según precio/GB configurado |
| Documentación de instalación | Guía paso a paso para poner en marcha la herramienta |
| Documentación de configuración | Explicación de cada variable del archivo `.env` |
| Troubleshooting y FAQ | Sección de resolución de problemas comunes |
| Registro de cambios (changelog) | Historial de versiones con descripción de mejoras y correcciones |
| Lecciones aprendidas | Sección de reflexión y mejoras futuras del proyecto |

---

## Excluido del alcance

| Elemento excluido | Motivo |
|-------------------|--------|
| Interfaz gráfica (GUI) | Fuera del enfoque CLI ligero; requeriría un stack adicional no justificado |
| Integración con Prometheus, Grafana o Datadog | Herramientas de terceros con su propia complejidad; quedan como mejora futura |
| Soporte oficial para todos los proveedores cloud | Se acota a VPS estándar y GCP; otros proveedores son "posible mejora futura" |
| Gestión avanzada de seguridad | Se aplican buenas prácticas básicas (`.gitignore`, uso controlado del TOKEN); la seguridad avanzada queda fuera del MVP |
| Integración con Slack, Discord u otras plataformas | Identificado en el roadmap como mejora a medio plazo, no en el MVP |
| Dashboard web centralizado | Concepto del roadmap a largo plazo, no parte de este proyecto |

---

## Entregables del proyecto

### Entregables técnicos

| Entregable | Estado |
|------------|--------|
| Repositorio técnico funcional con código y estructura organizada | Completado — [MyIronGuard](https://github.com/LadyKernel/MyIronGuard/tree/main/network-monitor) |
| Script de monitorización para VPS estándar (`/vps-estandar`) | Completado |
| Script de monitorización para GCP (`/gcloud`) | Completado |
| Archivo `.env.example` como plantilla de configuración | Completado |
| Archivo `.gitignore` con exclusión del `.env` real | Completado |

### Entregables documentales

| Entregable | Ubicación |
|------------|-----------|
| README principal con contexto, uso y notas técnicas | Repositorio raíz |
| Guía de instalación paso a paso | Repositorio técnico |
| Guía de configuración del `.env` | Repositorio técnico |
| Registro de cambios (changelog) con versiones y mejoras | Repositorio técnico |
| Documentación PM completa (este repositorio) | MyCiberGuardPM |

---

## Estrategia de licenciamiento

El proyecto utiliza la **PolyForm Noncommercial License 1.0.0** como mecanismo de protección de autoría.

Esta elección no responde a objetivos comerciales, sino a dos razones concretas:

1. **Gobierno del producto:** Mantener el control sobre cómo y quién usa la herramienta, evitando que terceros la comercialicen sin autorización
2. **Protección de autoría:** Garantizar el reconocimiento del trabajo en un entorno open-source donde la apropiación es frecuente

El uso libre y gratuito está permitido para personas individuales, entornos de laboratorio y contextos educativos.

---

## Propuesta de valor

> *"Control estricto y en tiempo real de los costes de salida (egress) en la nube, libre de spam de alertas, configurable en un solo comando y sin penalizar el rendimiento del servidor."*

---

*← [Volver al índice](../README.md)*
