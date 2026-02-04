# Práctica OSINT – theHarvester

Esta práctica documenta el uso de **theHarvester** como herramienta de **OSINT (Open Source Intelligence)** para la recolección **pasiva** de información pública.

El objetivo es comprender cómo, **sin interactuar ni atacar sistemas**, es posible obtener datos relevantes a partir de fuentes abiertas, y por qué esto representa un riesgo si no se gestiona correctamente.

> ⚠️ Nota ética: los dominios utilizados son de ejemplo o deben ser objetivos previamente autorizados.

---

## 1️⃣ ¿Qué es theHarvester?

theHarvester es una herramienta utilizada en la fase de reconocimiento para recopilar información pública disponible en internet, como:

- Correos electrónicos
- Subdominios
- Hosts
- Direcciones IP asociadas
- Metadatos

A diferencia de herramientas activas, theHarvester no explota vulnerabilidades ni interactúa directamente con los sistemas objetivo, ya que se apoya únicamente en fuentes públicas como buscadores y bases de datos abiertas (Google, Bing, crt.sh, Shodan, entre otras).

![Vista general de theHarvester](images/01-theharvester-overview.png)

---

## 2️⃣ Uso de theHarvester en un proceso de pentesting

Dentro de un proceso de evaluación de seguridad, theHarvester se utiliza en la fase inicial de reconocimiento (OSINT).

Un flujo de trabajo realista sería:

1. Recolección pasiva de información con theHarvester
2. Validación manual de los activos encontrados
3. Escaneo activo con herramientas como Nmap
4. Enumeración de servicios
5. Análisis y elaboración del reporte

Este orden permite reducir ruido, evitar escaneos innecesarios y enfocarse en activos realmente relevantes.

![Flujo de reconocimiento OSINT](images/02-flujo-osint.png)

---

## 3️⃣ Sintaxis básica de la herramienta

```bash
theHarvester -d DOMINIO -b FUENTE
