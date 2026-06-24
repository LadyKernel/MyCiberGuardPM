# 08 — Uso Responsable de IA

## Introducción

La inteligencia artificial generativa es una herramienta de trabajo legítima cuando se usa con criterio: como apoyo, no como sustituta del pensamiento propio. Esta sección documenta de forma transparente cómo se ha utilizado IA en este proyecto, qué se ha validado manualmente y por qué las decisiones finales son responsabilidad de la autora.

---

## Qué se ha hecho con IA

### Estructura y documentación

- Apoyo para estructurar las secciones del repositorio PM y definir qué debía contener cada apartado
- Propuestas iniciales de organización del índice y los README de cada sección
- Ayuda para redactar borradores de documentación base (contexto, alcance, WBS)
- Sugerencias de formato para tablas, matrices y cronogramas

### Revisión y mejora

- Revisión de la coherencia entre secciones (que el alcance no contradiga los requisitos, que los riesgos tengan su respuesta documentada)
- Propuestas de mejoras sobre el repositorio original para alinearlo con los estándares de un proyecto PM

---

## Qué se ha revisado y validado manualmente

### Validación técnica

- Comprobación de que cada comando del script funciona correctamente en entorno real
- Verificación de que la lógica anti-spam funciona como se describe (estado solo se guarda si el envío fue exitoso)
- Pruebas de que `LC_NUMERIC=C` resuelve el problema de precisión decimal en entornos con locale español
- Confirmación de que el `.env` no se incluye en el repositorio mediante `.gitignore`

### Adaptación al proyecto real

- Todos los textos generados se han revisado y adaptado al contexto específico de la herramienta (interfaz de red, vnStat, Telegram, GCP vs VPS estándar)
- Las historias de usuario se han ajustado para reflejar el comportamiento real del script, no un comportamiento genérico
- Los riesgos documentados son los que se encontraron durante el desarrollo real, no riesgos inventados

### Decisiones de proyecto

- La elección de la licencia PolyForm Noncommercial es una decisión propia y consciente
- La arquitectura en dos ramas (VPS estándar / GCP) es una decisión técnica tomada por la autora tras identificar el problema de las interfaces de red
- Las prioridades MoSCoW de cada historia de usuario reflejan el criterio propio sobre qué era imprescindible para el MVP

---

## Cómo se justifica en Project Management

El uso de IA en gestión de proyectos no es diferente al uso de plantillas, frameworks o herramientas de apoyo como Notion, Jira o Miro. Lo relevante en PM no es si se usa una herramienta, sino si quien la usa entiende lo que produce y puede defenderlo.

En este proyecto:

1. **IA como herramienta de apoyo, no de sustitución**: la autora es responsable de todas las decisiones de proyecto y puede explicar cada una
2. **Revisión crítica antes de aplicar**: ningún contenido generado por IA se ha incluido sin revisarlo y adaptarlo al contexto real
3. **Aprendizaje consciente**: el proceso de revisar y adaptar el output de la IA ha reforzado la comprensión de los conceptos de PM, no los ha reemplazado
4. **Transparencia**: este proyecto documenta explícitamente el uso de IA porque ocultarlo sería deshonesto y contrario al criterio profesional que se quiere demostrar

---

## Reflexión personal

> *[Espacio para añadir tu reflexión personal sobre cómo fue la experiencia de usar IA en el proyecto: qué fue útil, qué tuviste que corregir, qué aprendiste del proceso de revisar y validar.]*

---

*← [Volver al índice](../README.md)*
