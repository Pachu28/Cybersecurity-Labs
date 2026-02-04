# Práctica OSINT – theHarvester

En esta práctica utilizo **theHarvester** como herramienta de **OSINT (Open Source Intelligence)** para la recolección pasiva de información pública.

El objetivo no es atacar ni interactuar con sistemas, sino entender cuánta información puede obtenerse únicamente a partir de fuentes abiertas.

> ⚠️ Todos los dominios utilizados son **de ejemplo** o deben ser **objetivos previamente autorizados**.

---

## 1️⃣ ¿Qué es theHarvester?

**theHarvester** es una herramienta de OSINT diseñada para recopilar información pública disponible en internet, como:

- Correos electrónicos
- Subdominios
- Hosts
- Direcciones IP asociadas
- Metadatos

📌 No explota vulnerabilidades  
📌 No envía paquetes al objetivo  
📌 Utiliza fuentes públicas (Google, Bing, crt.sh, Shodan, etc.)

Por esta razón, es una herramienta utilizada de forma habitual en **empresas y auditorías de seguridad** durante las primeras fases de análisis.

---

## 2️⃣ ¿Cuándo se usa en un pentesting?

theHarvester se emplea normalmente en la **fase 1: Reconocimiento**.

Un flujo real de trabajo sería:

1. OSINT con theHarvester  
2. Validación de hosts encontrados  
3. Escaneo con Nmap  
4. Enumeración de servicios  
5. Elaboración del reporte  

Este orden es importante porque reduce ruido, errores y escaneos innecesarios.

---

## 3️⃣ Sintaxis básica

```bash
theHarvester -d DOMINIO -b FUENTE
