⚡ LuzFija.es — Comparador de Tarifas Eléctricas (España)Herramienta gratuita y sin publicidad para comparar tarifas de electricidad en España. Calcula una estimación de factura según potencia contratada (P1/P2), días de facturación y consumos por periodos (punta/llano/valle). Incluye PVPC (tarifa regulada) cuando está disponible (vía proxy por CORS).🔗 Web: https://luzfija.es📧 Contacto: hola@luzfija.es🎯 Características✅ Comparación de tarifas 1P y 3P (discriminación horaria)✅ PVPC incluido cuando está disponible✅ Estimación con impuestos (modelo de cálculo del comparador)✅ Ranking ordenado por precio total✅ Gráfico visual Top 5✅ Enlaces directos para contratar✅ Compartir configuración por URL✅ Exportar resultados a CSV✅ Sin registro (y sin cookies propias)📊 ¿Qué calculamos?Inputs del usuarioPotencia contratada P1 y P2 (kW)Días de facturación (1–365)Consumo por periodos (kWh):Punta (10h–14h y 18h–22h)Llano (8h–10h, 14h–18h, 22h–24h)Valle (0h–8h + fines de semana)Incluye (estimación)Término fijo (potencia × días)Término variable (consumo × precio por periodo)Conceptos/impuestos según el modelo implementado (IVA, impuesto eléctrico, etc.)Nota: Es una estimación orientativa. La factura real puede variar por redondeos, condiciones del contrato y cambios regulatorios.🏆 PVPC (Tarifa Regulada) y CORS (CNMC)El PVPC se consulta en comparador.cnmc.gob.es, pero esa API no permite CORS directo desde navegador. Por eso la web usa un Cloudflare Worker como proxy CORS con whitelist estricta.Cómo se activa en el frontendEn index.html se define la URL del proxy (ya lo tienes preparado en el <head>):<script>
  window.PVPC_PROXY_URL = "[https://TU-WORKER.workers.dev/?url=](https://TU-WORKER.workers.dev/?url=)";
</script>
Caché (para reducir llamadas)Frontend (localStorage): Caché por día (fecha ancla + inputs) y límite de entradas.Worker (edge cache): Caché de respuesta (TTL configurable; típico 1h).Diagrama:Usuario → caché local (por día)↓ (miss)Worker (caché edge)↓ (miss)CNMC📌 Referencia oficial CNMC: https://facturaluz2.cnmc.es/🛠️ TecnologíaHTML5 + CSS3 + Vanilla JavaScript (sin frameworks)Diseño responsive + modo claro/oscuroHosting estático (p.ej. Cloudflare Pages / GitHub Pages, según despliegue)PVPC vía proxy (Cloudflare Workers)📁 Estructura del proyecto (actual)luzfija.es/
├── CNAME
├── README.md
├── index.html
├── tarifas.json
├── robots.txt
├── sitemap.xml
├── google60cc5bcefe636a81.html
├── favicon.svg
├── favicon.png
├── favicon.ico
├── og.png
└── og.svg
google60cc5bcefe636a81.html: Se usa para verificación (Search Console).CNAME: Se usa para el dominio personalizado.🧪 Desarrollo localImportante: Si abres index.html con file:// puede fallar la carga de tarifas.json. Mejor levantar un servidor local:# Opción 1: Python
python -m http.server 8080

# Opción 2: Node (puerto fijo)
npx serve -l 8080

# Abrir:
# http://localhost:8080
🧾 Formato de tarifas.jsonLa app espera un JSON con esta estructura:{
  "tarifas": [
    {
      "nombre": "Comercializadora - Tarifa",
      "tipo": "1P",
      "p1": 0.123456,
      "p2": 0.123456,
      "cPunta": 0.123456,
      "cLlano": 0.123456,
      "cValle": 0.123456,
      "web": "https://url-contratar"
    }
  ]
}
La clave tarifas es obligatoria (array de objetos).🔧 Cloudflare Worker (PVPC Proxy)Características (según implementación típica del worker):✅ Whitelist estricto: solo comparador.cnmc.gob.es/api/ofertas/pvpc✅ Caché edge (TTL configurable)✅ Headers CORS completos✅ User-Agent identificable con contacto✅ Solo cachea respuestas 2xx🤝 ContribuirReportar errores: GitHub IssuesSugerir mejoras: hola@luzfija.esActualizar tarifas: Pull request con cambios en tarifas.json⚖️ Avisos LegalesDescargo de responsabilidadProyecto educativo y sin ánimo de lucro. Las estimaciones son orientativas y se obtienen consultando información pública disponible.Para información oficial y vinculante:CNMC: https://facturaluz2.cnmc.es/ESIOS (REE): https://www.esios.ree.es/es/pvpcNo afiliaciónLuzFija.es no está afiliado con CNMC, Red Eléctrica, organismos oficiales ni comercializadoras. Proyecto independiente y de código abierto.Privacidad❌ Sin cookies propias de seguimiento❌ Sin registro de usuarios✅ Solo localStorage para guardar preferencias (local)✅ Si se usa analítica del hosting (ej. Cloudflare Web Analytics), es sin cookies📅 Última actualización: Diciembre 2025 — Optimizaciones PVPC + caché
