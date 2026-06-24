# 09 — Lecciones Aprendidas y Mejoras Futuras

## Introducción

Cerrar un proyecto sin reflexionar sobre él es perder la mitad de su valor. Esta sección documenta lo que se ha aprendido gestionando este proyecto — no solo técnicamente, sino como ejercicio de Project Management — y qué haría diferente una próxima iteración.

---

## Evaluación del cumplimiento de objetivos

| Objetivo específico | ¿Se ha cumplido? | Observaciones |
|--------------------|-----------------|---------------|
| OE-01 — Monitorizar tráfico diario y mensual | Sí | vnStat funciona correctamente en las dos arquitecturas |
| OE-02 — Alertas automáticas a Telegram al superar umbrales | Sí | Sistema de alertas operativo desde v1.0 |
| OE-03 — Calcular coste estimado de egress | Sí | Precisión mejorada en v1.1 con LC_NUMERIC=C |
| OE-04 — Soportar dos arquitecturas de proveedor | Sí | Ramas /vps-estandar y /gcloud funcionales |
| OE-05 — Documentar instalación, configuración y troubleshooting | Sí | Documentación completa en el repositorio técnico |

---

## Lecciones aprendidas — Gestión de proyecto

> *[Completa esta sección con tu reflexión personal. Algunas preguntas que pueden guiarte:]*

**¿Qué aprendiste gestionando este proyecto?**

> *[Por ejemplo: la importancia de definir el alcance antes de empezar a desarrollar, que los riesgos que parecen improbables ocurren en cuanto el entorno cambia, que la documentación es una parte del producto y no un añadido al final...]*

---

**¿Qué harías distinto si empezaras de cero?**

> *[Por ejemplo: empezar con la arquitectura de doble rama desde el principio en lugar de separarlo a posteriori, definir el .env antes de escribir el primer script, tener la matriz de riesgos antes de llegar a las pruebas...]*

---

**¿Qué fue más difícil: la parte técnica o la de gestión?**

> *[Esta pregunta tiene mucho valor para el evaluador porque demuestra conciencia de que gestionar un proyecto y ejecutarlo técnicamente son habilidades diferentes.]*

---

**¿Hubo algún riesgo que se materializó y cómo lo gestionaste?**

> *[El problema de LC_NUMERIC=C es un buen ejemplo: se detectó en pruebas, se documentó como riesgo retroactivamente y se resolvió en v1.1. ¿Hubo algún otro?]*

---

## Lecciones aprendidas — Parte técnica

> *[Lo que te ha enseñado el proyecto sobre Bash, vnStat, la API de Telegram o la gestión de distintos entornos Linux.]*

---

## Mejoras futuras identificadas

### A corto plazo (próxima versión)

- Fusionar las dos ramas en un instalador unificado con autodetección de interfaz de red
- Añadir soporte para notificaciones vía Slack y Discord
- Mejorar la validación del TOKEN y CHAT_ID durante la instalación para reducir errores de configuración

### A medio plazo

- Suite básica de tests automatizados para el parsing de vnStat y los cálculos de coste
- Ampliar la documentación con ejemplos reales de configuración para AWS y DigitalOcean

### A largo plazo

- Explorar el concepto de dashboard web centralizado para gestión multi-servidor
- Evaluar si tiene sentido una versión con modelo freemium para entornos empresariales

---

## Cierre del proyecto

Este proyecto nació de un repositorio técnico real y se convirtió en un ejercicio completo de Project Management: desde la definición del problema hasta el cierre con reflexión. Eso es exactamente lo que hace un PM.

Lo que queda en el repositorio no es solo código — es evidencia de que se sabe pensar un producto, gestionarlo y documentarlo de forma que otros puedan entenderlo, usarlo y mejorarlo.

---

*← [Volver al índice](../README.md)*
