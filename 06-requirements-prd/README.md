# 06 — Requirements / PRD

## Introducción

Este documento recoge los requisitos del producto en forma de Historias de Usuario, organizadas por épicas. Cada historia incluye su criterio de aceptación y su prioridad según el método MoSCoW.

---

## Priorización MoSCoW

| Etiqueta | Significado |
|----------|-------------|
| **Must Have** | Imprescindible para el MVP. Sin esto, el producto no funciona |
| **Should Have** | Importante, pero el MVP puede funcionar sin ello temporalmente |
| **Could Have** | Deseable si hay tiempo; añade valor pero no es crítico |
| **Won't Have** | Fuera del alcance actual; se revisa en futuras versiones |

---

## Épica 1 — Monitorización y Alertas

### HU-01 — Monitorización de tráfico de red

> **Como** administrador de sistemas,
> **quiero** que el script lea el tráfico diario y mensual de la interfaz de red configurada,
> **para** tener visibilidad del consumo sin necesidad de acceder manualmente al servidor.

| Campo | Detalle |
|-------|---------|
| **Prioridad** | Must Have |
| **Criterio de aceptación** | El script lee correctamente los datos de vnStat y los procesa sin errores en VPS estándar y en GCP |
| **Estado** | Completado — v1.0 |

---

### HU-02 — Alertas automáticas por Telegram

> **Como** administrador de sistemas,
> **quiero** recibir una alerta en Telegram cuando el tráfico supere el umbral que yo he definido,
> **para** poder actuar antes de que el coste se dispare.

| Campo | Detalle |
|-------|---------|
| **Prioridad** | Must Have |
| **Criterio de aceptación** | El mensaje llega al chat configurado con el tráfico actual, el umbral y el coste estimado, sin superar ese umbral en ningún caso sin notificación |
| **Estado** | Completado — v1.0 |

---

### HU-03 — Sistema anti-spam de alertas (memoria de estado)

> **Como** administrador de sistemas,
> **quiero** que el script recuerde que ya me envió una alerta,
> **para** no recibir el mismo aviso repetido cada vez que el cron ejecuta el script.

| Campo | Detalle |
|-------|---------|
| **Prioridad** | Must Have |
| **Criterio de aceptación** | Una vez enviada la alerta, no se vuelve a enviar hasta que el tráfico baja por debajo del umbral y vuelve a superarlo |
| **Estado** | Completado — v1.0 |

---

### HU-04 — Estado de alerta solo si el envío fue exitoso

> **Como** administrador de sistemas,
> **quiero** que el script solo marque una alerta como "ya enviada" si el envío a Telegram fue exitoso,
> **para** no perder notificaciones por problemas temporales de red.

| Campo | Detalle |
|-------|---------|
| **Prioridad** | Must Have |
| **Criterio de aceptación** | Si la llamada a la API de Telegram falla, el estado local no se actualiza y el script lo reintenta en la siguiente ejecución |
| **Estado** | Completado — v1.1 |

---

## Épica 2 — Control de Costes (FinOps)

### HU-05 — Cálculo de coste estimado de egress

> **Como** administrador de sistemas,
> **quiero** ver en la alerta de Telegram el coste estimado de tráfico de salida según mi precio por GB configurado,
> **para** evaluar el impacto económico sin necesidad de entrar al panel del proveedor.

| Campo | Detalle |
|-------|---------|
| **Prioridad** | Must Have |
| **Criterio de aceptación** | El coste en el mensaje de alerta es correcto con una desviación menor al 5% respecto al cálculo manual usando el mismo precio/GB |
| **Estado** | Completado — v1.0 |

---

### HU-06 — Precisión decimal independiente del locale

> **Como** administrador de sistemas en un sistema con idioma no inglés,
> **quiero** que los cálculos de coste sean correctos independientemente de la configuración regional de mi servidor,
> **para** evitar errores por el uso de coma como separador decimal.

| Campo | Detalle |
|-------|---------|
| **Prioridad** | Must Have |
| **Criterio de aceptación** | El script funciona correctamente en sistemas con `LC_NUMERIC` configurado en español, francés u otros locales que usan coma decimal |
| **Estado** | Completado — v1.1 (implementado con `LC_NUMERIC=C`) |

---

### HU-07 — Identificación del servidor en la alerta

> **Como** administrador de sistemas que gestiona varios VPS,
> **quiero** que la alerta de Telegram incluya el nombre del servidor (hostname),
> **para** saber de qué servidor viene la alerta sin tener que acceder por SSH.

| Campo | Detalle |
|-------|---------|
| **Prioridad** | Should Have |
| **Criterio de aceptación** | El mensaje de alerta incluye el hostname del servidor de forma legible |
| **Estado** | Completado — v1.0 |

---

## Épica 3 — Instalación y Configuración

### HU-08 — Instalación en un solo comando

> **Como** administrador de sistemas,
> **quiero** poder instalar la herramienta ejecutando un único comando,
> **para** no tener que configurar dependencias manualmente en cada servidor nuevo.

| Campo | Detalle |
|-------|---------|
| **Prioridad** | Should Have |
| **Criterio de aceptación** | El script de instalación instala vnStat, jq y curl si no están presentes, configura el crontab y deja el sistema listo para usar |
| **Estado** | Completado |

---

### HU-09 — Configuración mediante archivo `.env`

> **Como** administrador de sistemas,
> **quiero** configurar todos los parámetros del monitor en un único archivo `.env`,
> **para** no tener que editar el código del script directamente.

| Campo | Detalle |
|-------|---------|
| **Prioridad** | Must Have |
| **Criterio de aceptación** | El script lee TOKEN, CHAT_ID, umbral de tráfico y precio/GB desde el `.env` sin requerir cambios en el código |
| **Estado** | Completado |

---

## Requisitos no funcionales

| # | Requisito | Descripción |
|---|-----------|-------------|
| RNF-01 | Rendimiento | El script no debe superar el 1% de CPU en su ejecución. Tiempo de ejecución inferior a 5 segundos |
| RNF-02 | Compatibilidad | Debe funcionar en Debian, Ubuntu y CentOS. Dependencias disponibles via apt/yum |
| RNF-03 | Seguridad | El archivo `.env` con credenciales no puede estar en el repositorio público. Debe estar en `.gitignore` |
| RNF-04 | Mantenibilidad | El código debe ser legible y comentado en los puntos críticos para facilitar su mantenimiento |
| RNF-05 | Fiabilidad | El estado de alerta solo se guarda si el envío fue exitoso. No hay pérdida silenciosa de notificaciones |

---

## Definition of Done

Una historia de usuario se considera completada cuando:

- [ ] La funcionalidad está implementada y funciona en entorno real (no solo en pruebas locales)
- [ ] Ha sido probada en al menos una arquitectura (VPS estándar o GCP)
- [ ] El comportamiento en caso de error es el esperado (sin fallos silenciosos)
- [ ] Está documentada en el README o en la guía correspondiente
- [ ] No introduce regresiones en las historias ya completadas

---

*← [Volver al índice](../README.md)*
