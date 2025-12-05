# ⚡ Comparador de Tarifas Eléctricas

> Herramienta profesional para comparar tarifas de electricidad en España en tiempo real. Encuentra la oferta más barata según tus consumos específicos.

![Estado](https://img.shields.io/website?url=https%3A%2F%2Fluzfija.es&label=Estado&style=flat-square)
![Tamaño](https://img.shields.io/github/repo-size/almax/luzfija.es?label=Tamaño&color=orange&style=flat-square)
![Licencia](https://img.shields.io/badge/Licencia-Gratis-green?style=flat-square)

---

## 🚀 Características

* ✅ **Cálculo instantáneo:** Resultados basados en tu consumo real.
* ✅ **Sin registro:** Úsalo directamente sin crear cuenta ni dar datos personales.
* ✅ **Datos actualizados:** Tarifas fijas verificadas diariamente.
* ✅ **Responsive:** Funciona perfectamente en móvil, tablet y ordenador.
* ✅ **Exportar CSV:** Descarga el ranking completo con un clic.
* ✅ **Sin publicidad:** Interfaz limpia, profesional y ética.
* ✅ **Código abierto:** Transparencia total (GitHub Pages + Google Apps Script).

## 🌐 Acceso

👉 **[Visita luzfija.es](https://luzfija.es)** *(O busca "luz fija es" en Google)*

---

## 📊 Cómo Funciona

1.  **Introduce tus datos:**
    * Potencia P1 y P2 (en kW).
    * Días de facturación.
    * Consumo en horas punta, llano y valle.
2.  **Obtén resultados:**
    * Ranking de tarifas ordenadas por precio final.
    * Desglose de Impuestos y Topes.
    * Diferencia de ahorro respecto a la mejor opción.
3.  **Descarga:**
    * Puedes exportar la comparativa completa a formato CSV para analizarla en Excel.

---

## 🏗️ Arquitectura

Este proyecto sigue una arquitectura **Serverless** y **Jamstack**:

### Frontend (100% Cliente)
* **Core:** HTML5 + CSS3 + JavaScript vanilla (ES6+).
* **Hosting:** GitHub Pages.
* **CDN & Analytics:** Cloudflare.
* **Estilos:** Diseño propio "Glassmorphism" + Google Fonts (Outfit).

### Backend (Datos)
* **API:** Google Apps Script (actúa como puente JSON).
* **Base de datos:** Google Sheets (gestión sencilla de tarifas).

---

## 🎨 Stack Técnico

| Componente | Tecnología |
| :--- | :--- |
| **Frontend** | HTML5, CSS3, JavaScript Vanilla |
| **Hosting** | GitHub Pages |
| **CDN** | Cloudflare |
| **API** | Google Apps Script |
| **Base de Datos** | Google Sheets |
| **Analytics** | Cloudflare Web Analytics |

---

## 📈 Performance y Eficiencia

Datos reales (Cloudflare Web Analytics):

* 🚀 **Carga de página:** 195ms (Promedio)
* ⚡ **LCP (Carga visual):** 99% Good
* 👆 **INP (Interactividad):** 77% Good
* 📐 **CLS (Estabilidad):** 86% Good

### Eficiencia y Cuotas (Google Apps Script)
* **Arquitectura eficiente:** La lógica de cálculo se ejecuta 100% en el navegador del usuario (Client-side).
* **Consumo bajo demanda (Lazy Loading):** La conexión con la API solo se activa cuando el usuario realiza el primer cálculo, no al cargar la página.
* **Caching inteligente:** Los datos se descargan una sola vez por sesión y se reutilizan para cálculos ilimitados sin consumir cuota del servidor.

---

## 🎯 Casos de Uso

1.  Comparar antes de cambiar de compañía eléctrica.
2.  Simular ahorros subiendo o bajando potencia.
3.  Comprobar si tu tarifa actual sigue siendo competitiva.
4.  Análisis rápido de ofertas del mercado.

---

## 🤝 Contribuciones y Contacto

Este es un proyecto personal de utilidad pública creado por **aLMaX**.

* **Web:** [luzfija.es](https://luzfija.es)
* **Bugs/Sugerencias:** Abre un *Issue* en este repositorio.

---

<p align="center">
  <sub>Última actualización: Diciembre 2025 • Proyecto gratuito y sin publicidad.</sub>
</p>
