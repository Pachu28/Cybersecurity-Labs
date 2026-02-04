<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Práctica OSINT – theHarvester</title>
  <style>
    body {
      font-family: Arial, Helvetica, sans-serif;
      line-height: 1.6;
      max-width: 900px;
      margin: 40px auto;
      padding: 0 20px;
      color: #222;
    }
    h1, h2, h3 {
      color: #1f2937;
    }
    h2 {
      margin-top: 40px;
      border-bottom: 2px solid #e5e7eb;
      padding-bottom: 6px;
    }
    code {
      background: #f3f4f6;
      padding: 2px 6px;
      border-radius: 4px;
      font-size: 0.95em;
    }
    pre {
      background: #0f172a;
      color: #e5e7eb;
      padding: 16px;
      border-radius: 8px;
      overflow-x: auto;
    }
    ul {
      margin-left: 20px;
    }
    .note {
      background: #fff7ed;
      border-left: 4px solid #fb923c;
      padding: 12px;
      margin: 20px 0;
    }
    .img-placeholder {
      margin: 20px 0;
      padding: 14px;
      background: #f9fafb;
      border: 2px dashed #9ca3af;
      color: #374151;
      font-style: italic;
    }
  </style>
</head>

<body>

<h1>Práctica OSINT – theHarvester</h1>

<p>
  Esta práctica documenta el uso de <strong>theHarvester</strong> como herramienta de
  <strong>OSINT (Open Source Intelligence)</strong> para la recolección pasiva de información pública.
</p>

<p>
  El objetivo es comprender cómo, sin interactuar ni atacar sistemas, es posible obtener datos
  relevantes a partir de fuentes abiertas, y por qué esto representa un riesgo si no se gestiona correctamente.
</p>

<div class="note">
  ⚠️ Los dominios utilizados son de ejemplo o deben ser objetivos previamente autorizados.
</div>

<h2>1️⃣ ¿Qué es theHarvester?</h2>

<p>
  <strong>theHarvester</strong> es una herramienta utilizada en la fase de reconocimiento para recopilar
  información pública disponible en internet, como:
</p>

<ul>
  <li>Correos electrónicos</li>
  <li>Subdominios</li>
  <li>Hosts</li>
  <li>Direcciones IP asociadas</li>
  <li>Metadatos</li>
</ul>

<p>
  A diferencia de herramientas activas, theHarvester <strong>no explota vulnerabilidades ni interactúa
  directamente con los sistemas objetivo</strong>, ya que se apoya únicamente en fuentes públicas.
</p>

<div class="img-placeholder">
  📸 Captura pendiente: ejecución inicial de theHarvester en la terminal
</div>

<h2>2️⃣ Uso de theHarvester en un proceso de pentesting</h2>

<p>
  Dentro de un proceso de evaluación de seguridad, theHarvester se utiliza en la
  <strong>fase inicial de reconocimiento (OSINT)</strong>.
</p>

<p>Flujo de trabajo realista:</p>

<ul>
  <li>Recolección pasiva de información con theHarvester</li>
  <li>Validación manual de los activos encontrados</li>
  <li>Escaneo activo con herramientas como Nmap</li>
  <li>Enumeración de servicios</li>
  <li>Análisis y elaboración del reporte</li>
</ul>

<div class="img-placeholder">
  📸 Captura pendiente: diagrama del flujo OSINT → Nmap → Reporte
</div>

<h2>3️⃣ Sintaxis básica de la herramienta</h2>

<pre><code>theHarvester -d DOMINIO -b FUENTE</code></pre>

<p>Donde:</p>

<ul>
  <li><code>-d</code> indica el dominio objetivo</li>
  <li><code>-b</code> especifica la fuente de información</li>
</ul>

<p>
  Esta sintaxis permite consultar diferentes fuentes sin realizar interacción directa
  con los sistemas analizados.
</p>

<div class="img-placeholder">
  📸 Captura pendiente: ejemplo del comando escrito en la terminal
</div>

<h2>4️⃣ Ejecución básica (primer comando)</h2>

<pre><code>theHarvester -d example.com -b google</code></pre>

<p>
  Este comando realiza una búsqueda pasiva en Google para identificar información pública asociada
  al dominio.
</p>

<div class="img-placeholder">
  📸 Captura pendiente: ejecución del comando theHarvester con Google
</div>

<h2>5️⃣ Análisis de los resultados obtenidos</h2>

<ul>
  <li>Identificar correos electrónicos expuestos públicamente</li>
  <li>Detectar subdominios indexados</li>
  <li>Tener una primera visión de la superficie pública del dominio</li>
</ul>

<div class="img-placeholder">
  📸 Captura pendiente: resultados mostrados por theHarvester
</div>

<h2>6️⃣ Uso de múltiples fuentes de información</h2>

<pre><code>theHarvester -d example.com -b bing,duckduckgo,yahoo</code></pre>

<p>
  El uso de múltiples fuentes aumenta la probabilidad de encontrar información que no aparece
  en un solo buscador, manteniendo siempre un enfoque pasivo.
</p>

<div class="img-placeholder">
  📸 Captura pendiente: ejecución con varias fuentes de búsqueda
</div>

<h2>7️⃣ Descubrimiento de subdominios mediante certificados SSL (crt.sh)</h2>

<pre><code>theHarvester -d example.com -b crtsh</code></pre>

<p>
  La fuente <code>crtsh</code> consulta certificados SSL públicos, lo que permite descubrir
  subdominios no indexados en buscadores tradicionales.
</p>

<div class="img-placeholder">
  📸 Captura pendiente: subdominios descubiertos a través de crt.sh
</div>

<h2>8️⃣ Uso de Shodan como fuente OSINT</h2>

<div class="note">
  ⚠️ Este método requiere una API key válida de Shodan.
</div>

<pre><code>theHarvester -d example.com -b shodan</code></pre>

<ul>
  <li>Direcciones IP públicas</li>
  <li>Servicios expuestos</li>
  <li>Banners de servicios visibles</li>
</ul>

<div class="img-placeholder">
  📸 Captura pendiente: información obtenida usando Shodan
</div>

<h2>9️⃣ Limitación de resultados</h2>

<pre><code>theHarvester -d example.com -b google -l 200</code></pre>

<p>
  El parámetro <code>-l</code> permite limitar la cantidad de resultados y mantener el análisis enfocado.
</p>

<h2>🔟 Guardado de resultados para documentación</h2>

<pre><code>theHarvester -d example.com -b google -f reporte_example</code></pre>

<ul>
  <li>HTML</li>
  <li>XML</li>
</ul>

<p>
  Estos archivos son útiles para documentación técnica, reportes y evidencia de análisis OSINT.
</p>

<div class="img-placeholder">
  📸 Captura pendiente: archivos HTML y XML generados
</div>

<h2>1️⃣1️⃣ Identificación de activos relevantes</h2>

<ul>
  <li><code>mail.example.com</code></li>
  <li><code>vpn.example.com</code></li>
  <li><code>dev.example.com</code></li>
  <li><code>test.example.com</code></li>
</ul>

<p>
  Los entornos de desarrollo y prueba suelen ser más propensos a configuraciones débiles si no se gestionan correctamente.
</p>

</body>
</html>
