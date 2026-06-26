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

**¿Qué aprendiste gestionando este proyecto?**

Lo más importante fue entender que un proyecto no es solo hacer que algo funcione — es saber explicarlo, estructurarlo y documentarlo de forma que otra persona pueda entenderlo, usarlo y continuarlo. Tenía el script funcionando, pero sin estructura de proyecto era solo código en GitHub. El proceso de aplicar PM me obligó a leer bien cómo se organiza un proyecto, a poner por escrito el problema real, los requisitos, los riesgos y el alcance. Eso cambia cómo piensas lo que estás construyendo.

---

**¿Qué harías distinto si empezaras de cero?**

Intentaría planificarlo antes de escribir la primera línea de código. Este proyecto nació como un script personal para controlar mis gastos en VPS —algo que monté sobre la marcha a medida que aprendía— y la estructura PM llegó después. Si hubiera partido de los requisitos, del usuario objetivo y del alcance definido desde el principio, habría tomado decisiones técnicas más sólidas desde el inicio: la doble arquitectura VPS/GCP, el formato del `.env`, la lógica anti-spam. Todo eso lo fui resolviendo sobre la marcha en lugar de haberlo pensado antes.

---

**¿Qué fue más difícil: la parte técnica o la de gestión?**

Las dos tuvieron su dificultad, pero por razones distintas. En la parte técnica, aunque tengo base en entornos Linux y sabía lo que quería conseguir, la programación en Bash me costó: la sintaxis, la gestión de errores, hacer que el script se comportara correctamente en distintos entornos. Fui aprendiendo a base de prueba, error y entender por qué fallaba cada cosa.

La parte de gestión fue difícil de otra manera: no es un problema técnico que se resuelve ejecutando un comando. Requiere estructurar el pensamiento, saber qué documentar y cómo expresarlo con criterio de proyecto. Para alguien que viene del mundo técnico, esa capa de abstracción —pensar en stakeholders, en alcance, en riesgos como categorías formales— no es natural al principio. Eso fue lo que más me exigió.

---

**¿Hubo algún riesgo que se materializó y cómo lo gestionaste?**

Sí, el más claro fue el problema de precisión decimal documentado como R04. En entornos con locale español (`es_ES.UTF-8`), Bash interpreta los números decimales con coma, lo que rompía los cálculos de coste de egress. Se detectó durante las pruebas reales en mi servidor, se identificó la causa raíz y se resolvió añadiendo `LC_NUMERIC=C` al script en la versión v1.1. Es un buen ejemplo de un riesgo que parece improbable hasta que el entorno lo activa — exactamente el tipo de cosa que una matriz de riesgos bien hecha debería anticipar.

---

## Lecciones aprendidas — Parte técnica

Este proyecto me enseñó más de lo que esperaba en el lado técnico. Aprendí a configurar correctamente un servidor VPS desde cero —incluyendo la parte de red, que tiene más matices de los que parecen cuando gestionas varios proveedores con interfaces distintas. Aprendí a programar un script funcional en Bash que resuelve un problema real: monitorizar el tráfico de egress y calcular el coste estimado para no tener sorpresas en la factura mensual.

También aprendí que los entornos importan: el mismo script necesita adaptaciones distintas en un VPS estándar y en Google Cloud, no porque la lógica cambie, sino porque la interfaz de red, el nombre del dispositivo y el comportamiento del sistema difieren entre proveedores. Eso derivó en la arquitectura de doble rama que tiene el repositorio técnico.

Paralelamente, mantengo un repositorio privado con más scripts y un dashboard de uso personal para monitorizar mis propios sistemas. Este proyecto fue parte de ese aprendizaje continuo — la diferencia es que aquí lo documenté con criterio de proyecto en lugar de dejarlo como código sin contexto.

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
