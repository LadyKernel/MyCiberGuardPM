# 01 — Contexto y Objetivo del Proyecto

## Título del proyecto

**Monitor ligero de tráfico de red con alertas en Telegram para VPS y cloud**

---

## Contexto

Los servidores en la nube generan costes variables difíciles de predecir. Uno de los más problemáticos es el **tráfico de salida (egress traffic)**: cada GB que sale del servidor hacia internet tiene un coste que varía según el proveedor (GCP, AWS, Azure, DigitalOcean).

Los paneles de control de estos proveedores no siempre ofrecen alertas en tiempo real ni granularidad suficiente para detectar picos anómalos o consumos inesperados. Un administrador de sistemas que gestiona varios VPS puede no enterarse de un problema hasta que recibe la factura a fin de mes.

A esto se suma que las herramientas profesionales de monitorización (Datadog, Prometheus, Grafana) tienen un coste y una complejidad de configuración desproporcionados para entornos pequeños o individuales.

---

## Problema que resuelve

> Falta de visibilidad y alertas tempranas sobre el tráfico de red en servidores Linux, que puede provocar **facturas inesperadas** o no detectar **ataques / picos anómalos** hasta que ya han causado daño económico.

Los síntomas concretos del problema:

- Picos de tráfico por scripts mal optimizados, ataques DDoS o descargas masivas pasan desapercibidos
- El proveedor cloud no notifica en tiempo real: la alerta llega con la factura
- Las herramientas existentes son complejas, caras o consumen demasiados recursos para un VPS pequeño
- No hay diferenciación entre proveedores cloud con distintas estructuras de coste de egress

---

## Objetivo general

Diseñar, implementar y documentar una herramienta ligera de monitorización de tráfico de red para servidores Linux, con alertas automáticas vía Telegram y control básico de costes de egress, que sea instalable con un solo comando y configurable sin conocimientos avanzados.

---

## Objetivos específicos

| # | Objetivo | Indicador de cumplimiento |
|---|----------|--------------------------|
| OE-01 | Monitorizar tráfico diario y mensual por interfaz de red | El script lee y procesa correctamente la salida de vnStat |
| OE-02 | Enviar alertas automáticas a Telegram al superar umbrales configurables | Mensaje recibido en el canal configurado cuando se supera el límite |
| OE-03 | Calcular coste estimado de tráfico de salida según precio/GB | El cálculo en el mensaje de alerta coincide con el precio configurado en .env |
| OE-04 | Soportar al menos dos arquitecturas de proveedor (VPS estándar y GCP) | Las ramas `/vps-estandar` y `/gcloud` funcionan de forma independiente |
| OE-05 | Documentar instalación, configuración y troubleshooting de forma clara | Un usuario sin contexto previo puede instalar y configurar la herramienta siguiendo la guía |

---

## Definición de éxito

El proyecto se considera exitoso cuando:

1. Un administrador de sistemas puede instalar y configurar la herramienta en menos de 10 minutos
2. Las alertas llegan a Telegram antes de que el tráfico supere el umbral definido
3. El coste estimado en la alerta tiene una desviación menor al 5% respecto al coste real del proveedor
4. El script funciona de forma estable en segundo plano sin impacto notable en el rendimiento del servidor

---

## User Persona

**Nombre:** Carlos / Elena

**Perfil:** Administrador/a de Sistemas o profesional técnico que gestiona servidores propios o de clientes en entornos cloud (Google Cloud, AWS, DigitalOcean).

**Miedo principal:** Costes ocultos y sorpresas en la facturación mensual por tráfico de salida. No tiene tiempo ni presupuesto para configurar herramientas complejas y caras para un entorno pequeño.

**Necesidad:** Una herramienta que haga una sola cosa bien — avisar cuando algo va mal — sin tener que aprender una plataforma nueva ni pagar por ella.

---

*← [Volver al índice](../README.md)*
