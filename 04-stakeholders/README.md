# 04 — Stakeholders y Roles

## Mapa de stakeholders

Un stakeholder es cualquier persona o grupo que tiene interés en el proyecto, se ve afectado por él o puede influir en sus decisiones. Identificarlos permite anticipar necesidades, gestionar expectativas y definir canales de comunicación adecuados.

---

## Stakeholders identificados

### Promotora / Propietaria del proyecto

| Atributo | Detalle |
|----------|---------|
| **Quién** | LadyKernel (autora del proyecto) |
| **Rol PM** | Project Manager, Product Owner, desarrolladora principal y usuaria principal |
| **Nivel de influencia** | Alto — toma todas las decisiones técnicas y de producto |
| **Nivel de interés** | Alto — es la principal afectada por el resultado |
| **Necesidad** | Herramienta funcional, bien documentada y defendible académicamente |

---

### Usuario objetivo principal

| Atributo | Detalle |
|----------|---------|
| **Quién** | Administradores de sistemas, SysAdmins junior, desarrolladores independientes |
| **Perfil** | Gestiona uno o varios VPS en la nube (GCP, AWS, DigitalOcean) y le preocupa el coste de egress |
| **Nivel de influencia** | Medio — sus necesidades y feedback real orientan las prioridades del roadmap |
| **Nivel de interés** | Alto — la herramienta resuelve un problema real y frecuente |
| **Necesidad** | Alertas fiables, sin spam, instalación simple y sin impacto en el rendimiento del servidor |
| **Canal de comunicación** | GitHub (issues, stars, forks), Telegram (canal de pruebas) |

---

### Evaluador académico

| Atributo | Detalle |
|----------|---------|
| **Quién** | Profesor/a del curso de Project Management |
| **Rol** | Revisor y evaluador del proyecto como evidencia de competencias PM |
| **Nivel de influencia** | Alto en el contexto académico — define los criterios de evaluación |
| **Nivel de interés** | Medio — evalúa el enfoque de gestión, no el detalle técnico |
| **Necesidad** | Ver claramente la capa de PM: objetivos, alcance, WBS, riesgos, stakeholders, reflexión |
| **Canal de comunicación** | Repositorio GitHub (documentación PM), entrega formal del proyecto |

---

### Comunidad técnica (potencial)

| Atributo | Detalle |
|----------|---------|
| **Quién** | Otros estudiantes, profesionales técnicos, usuarios de GitHub interesados en herramientas de monitorización |
| **Nivel de influencia** | Bajo — no toman decisiones, pero su adopción valida el producto |
| **Nivel de interés** | Variable — depende de si encuentran el repositorio y lo consideran útil |
| **Necesidad** | Documentación clara, instalación sencilla y código mantenible |
| **Canal de comunicación** | GitHub (README, issues, discussions) |

---

## Matriz de poder / interés

```
ALTO INTERÉS
│
│  Evaluador ──────────── Propietaria / PM
│  académico              (gestionar de cerca)
│
│
│  Comunidad ──────────── Usuario objetivo
│  técnica                (mantener informado)
│
BAJO INTERÉS
└────────────────────────────────────────────
      BAJO PODER              ALTO PODER
```

---

## Plan de comunicación básico

| Stakeholder | Qué se le comunica | Cuándo | Cómo |
|-------------|-------------------|--------|------|
| Evaluador académico | Avances del proyecto, estructura de la documentación PM | Al cierre del proyecto | Repositorio GitHub |
| Usuario objetivo | Nuevas versiones, cambios en la API, fixes relevantes | Con cada release | Changelog en el repo |
| Comunidad técnica | Disponibilidad de nuevas versiones | Con cada release | GitHub Releases + README |

---

*← [Volver al índice](../README.md)*
