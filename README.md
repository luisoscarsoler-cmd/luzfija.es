# ⚡ LuzFija.es - Comparador de Tarifas Eléctricas

Herramienta **gratuita** y **sin publicidad** para comparar tarifas de electricidad en España. Calcula una **estimación de factura** según potencia contratada (P1/P2) y consumos por periodos (punta, llano, valle), incluyendo el **PVPC (tarifa regulada)** cuando está disponible.

🔗 **Web:** https://luzfija.es

---

## 🎯 Características

- ✅ Comparación de tarifas **1P** y **3P** (discriminación horaria)
- ✅ **PVPC** incluido cuando está disponible
- ✅ Estimación con impuestos (IVA, impuesto eléctrico, etc.)
- ✅ Ranking ordenado por **precio total**
- ✅ Gráfico visual Top 5 tarifas más baratas
- ✅ Enlaces directos para contratar
- ✅ Compartir configuración por URL
- ✅ Exportar resultados a CSV
- ✅ Sin registro (y sin cookies propias)

---

## 📊 ¿Qué calculamos?

### Inputs del usuario
- Potencia contratada **P1** y **P2** (kW)
- **Días** de facturación (1–365)
- Consumo por periodos (kWh):
  - **Punta** (10h–14h y 18h–22h)
  - **Llano** (8h–10h, 14h–18h, 22h–24h)
  - **Valle** (0h–8h + fines de semana)

### Incluye (estimación)
- Término fijo (potencia × días)
- Término variable (consumo × precio por periodo)
- Conceptos/impuestos según el modelo del comparador (IVA, impuesto eléctrico, etc.)

> **Nota:** es una **estimación orientativa**. La factura real puede variar por redondeos, condiciones contractuales y cambios regulatorios.

---

## 🏆 PVPC (Tarifa Regulada) y CORS

El PVPC se consulta en `comparador.cnmc.gob.es`, pero esa API **no permite CORS** directo desde navegador.  
Por eso se usa un **Cloudflare Worker** como proxy CORS con whitelist estricta.

### Cómo se activa en el frontend
En `index.html` se define la URL del proxy:

```html
<script>
  window.PVPC_PROXY_URL = "https://TU-WORKER.workers.dev/?url=";
</script>
