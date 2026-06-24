# 05 — Matriz de Riesgos

## Introducción

Un riesgo es un evento incierto que, si ocurre, tiene un impacto positivo o negativo en el proyecto. Identificarlos con antelación no garantiza que no ocurran, pero permite tener un plan de respuesta y no improvisar cuando algo sale mal.

La siguiente matriz recoge los riesgos identificados durante el proyecto, su valoración y las acciones tomadas o previstas para mitigarlos.

---

## Escala de valoración

| Probabilidad | Descripción |
|---|---|
| Baja | Poco probable que ocurra en condiciones normales |
| Media | Puede ocurrir en algunos entornos o configuraciones |
| Alta | Es habitual encontrar este problema en la práctica |

| Impacto | Descripción |
|---|---|
| Bajo | Afecta a una funcionalidad menor; el proyecto sigue adelante |
| Medio | Afecta a funcionalidades importantes; requiere trabajo adicional |
| Alto | Bloquea funcionalidades críticas o compromete el resultado |
| Muy alto | Puede comprometer la seguridad del usuario o del proyecto |

---

## Registro de riesgos

### Riesgo 01 — Cambio en la salida JSON de vnStat

| Campo | Detalle |
|-------|---------|
| **Descripción** | Una actualización de vnStat modifica la estructura de su salida JSON, rompiendo el parsing del script |
| **Probabilidad** | Media |
| **Impacto** | Alto — alertas y cálculos de coste dejarían de funcionar correctamente |
| **Respuesta** | Diseñar la lectura del JSON con selectores robustos (`jq`) y documentar las versiones de vnStat compatibles. Incluir la validación de la salida como paso del troubleshooting |
| **Estado** | Mitigado — documentado en la guía de troubleshooting |

---

### Riesgo 02 — Fallos en el envío de alertas a Telegram

| Campo | Detalle |
|-------|---------|
| **Descripción** | La alerta no llega al usuario por problemas de red, TOKEN incorrecto, CHAT_ID erróneo o limitaciones de la API de Telegram |
| **Probabilidad** | Alta — especialmente durante la configuración inicial |
| **Impacto** | Medio-Alto — el usuario no recibe los avisos que necesita |
| **Respuesta** | Implementar sistema de memoria de estado: el script solo guarda el estado de "alerta enviada" si la llamada a la API de Telegram devuelve éxito. Documentar en detalle la obtención del TOKEN y el CHAT_ID en la guía de configuración |
| **Estado** | Mitigado — implementado en v1.1 |

---

### Riesgo 03 — Exposición accidental del archivo `.env` en el repositorio público

| Campo | Detalle |
|-------|---------|
| **Descripción** | El usuario sube el archivo `.env` con el TOKEN de Telegram y el CHAT_ID al repositorio público de GitHub |
| **Probabilidad** | Baja |
| **Impacto** | Muy alto — exposición de credenciales; cualquier persona podría enviar mensajes a través del bot |
| **Respuesta** | Incluir el `.env` en el `.gitignore` desde el inicio. Proporcionar un `.env.example` como plantilla. Añadir un aviso prominente en la documentación. Documentar cómo revisar el historial de commits si hay dudas |
| **Estado** | Mitigado — `.gitignore` en su lugar desde la primera versión |

---

### Riesgo 04 — Errores de precisión decimal por configuración regional del sistema

| Campo | Detalle |
|-------|---------|
| **Descripción** | En sistemas con locale no inglés, el separador decimal puede ser una coma en lugar de un punto, causando errores en los cálculos de coste de egress |
| **Probabilidad** | Media — depende de la configuración regional del servidor |
| **Impacto** | Alto — cálculos de coste incorrectos o script que falla silenciosamente |
| **Respuesta** | Forzar `LC_NUMERIC=C` en el script para garantizar el uso del punto como separador decimal independientemente del locale del sistema |
| **Estado** | Resuelto — implementado en v1.1 |

---

### Riesgo 05 — Consumo excesivo de recursos en VPS de baja capacidad

| Campo | Detalle |
|-------|---------|
| **Descripción** | El script ejecutándose en segundo plano mediante cron consume más recursos de los esperados en VPS con poca RAM o CPU |
| **Probabilidad** | Baja |
| **Impacto** | Medio — degradación del rendimiento del servidor |
| **Respuesta** | Optimizar el script para mínimo consumo. Documentar el impacto esperado. Permitir al usuario ajustar la frecuencia de ejecución en el crontab según sus necesidades |
| **Estado** | Mitigado — documentado en la guía de instalación |

---

### Riesgo 06 — Diferencias en la interfaz de red según el proveedor

| Campo | Detalle |
|-------|---------|
| **Descripción** | El nombre de la interfaz de red varía según el proveedor (eth0, ens4, ens3, enp0s3...), haciendo que el script falle si está codificada de forma rígida |
| **Probabilidad** | Alta — cada proveedor usa convenciones distintas |
| **Impacto** | Alto — el script no monitoriza el tráfico correcto |
| **Respuesta** | Separar el proyecto en dos ramas especializadas: `/vps-estandar` (eth0) y `/gcloud` (ens4). Documentar en la guía qué interfaz usar según el proveedor. Incluir instrucciones para verificar la interfaz activa |
| **Estado** | Mitigado — arquitectura de doble rama implementada |

---

## Resumen visual

| # | Riesgo | Probabilidad | Impacto | Estado |
|---|--------|-------------|---------|--------|
| R01 | Cambio en salida JSON de vnStat | Media | Alto | Mitigado |
| R02 | Fallos en envío de alertas Telegram | Alta | Medio-Alto | Mitigado v1.1 |
| R03 | Exposición del `.env` en repositorio público | Baja | Muy alto | Mitigado |
| R04 | Errores de precisión decimal por locale | Media | Alto | Resuelto v1.1 |
| R05 | Consumo excesivo de recursos | Baja | Medio | Mitigado |
| R06 | Diferencias de interfaz de red por proveedor | Alta | Alto | Mitigado |

---

*← [Volver al índice](../README.md)*
