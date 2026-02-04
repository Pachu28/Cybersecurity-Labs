# The Harvester – Recolección de Información OSINT

## Descripción general

**The Harvester** es una herramienta de línea de comandos utilizada durante la fase de **reconocimiento** en ciberseguridad. Su función principal es recopilar información **pública** a partir de fuentes OSINT, permitiendo obtener datos relacionados con un dominio específico sin interactuar directamente con sus sistemas.

Entre la información que puede recolectar se encuentran:
- Subdominios y nombres de servidores
- Direcciones IP asociadas
- Correos electrónicos visibles públicamente
- Información básica sobre empleados y sus cargos (según la fuente utilizada)

El uso de esta herramienta es pasivo y se apoya exclusivamente en información expuesta en internet.

---

## Reconocimiento inicial usando Google

Un primer acercamiento común consiste en utilizar **Google** como fuente de datos para identificar información básica del dominio objetivo.

```bash
theharvester -d google.com -l 100 -b google

En este comando:

Se indica el dominio objetivo (google.com)

Se limita la salida a un máximo de 100 resultados

Se define Google como fuente de información

Este tipo de búsqueda no siempre devuelve grandes volúmenes de datos, pero resulta útil para obtener una primera visión de la superficie pública del dominio, como subdominios visibles o direcciones IP relacionadas.
