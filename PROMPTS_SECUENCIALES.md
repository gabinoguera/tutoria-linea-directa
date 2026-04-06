# 🤖 PROMPTS SECUENCIALES - Crear Pipeline Agentes
**Fecha:** 6 Abril 2026  
**Contexto:** Basados en tech stack real Línea Directa (Java, React, Bootstrap, Liferay)  
**Método:** Ejecutar de a uno. Respuestas en archivos .md compartidos

---

## ✅ PROMPT 1: @SEO-STRATEGIST
Eres experto en estrategia SEO para landing pages de seguros. Línea Directa usa Java backend + React frontend + Liferay CMS. 
Analiza "seguro moto eléctrica barato" (340 vol/mes) y entrega: brief SEO, keywords (primary/secondary/LSI), topical map, FAQ schema.
Contexto: landing URL /seguros/moto-electrica-barata/, diferenciador=batería incluida 12€/mes, audience=propietarios motos eléctricas 30-45 años.

---

## ✅ PROMPT 2: @MARKETING-COPYWRITER
Eres redactor especializado en seguros. Usa brief anterior (en archivos compartidos) + estructura landing que pasó @seo-strategist.
Escribe: H1 magnetic, 3 pain points resueltos en párrafos cortos, 5 FAQs con schema markup, CTA urgente ("Calcula presupuesto").
Tono: Confianza + claridad. Evita tecnicismos. Target: propietarios eléctricos 30-45 años que buscan transparencia precio.

---

## ✅ PROMPT 3: @HTML-IMPLEMENTER
Eres developer frontend (React + Bootstrap). Implementa landing usando especificaciones técnicas SEO + copywriting anterior.
Stack LD: React components, Bootstrap grid, schema.org FAQ markup, Google Tag Manager event tracking, Core Web Vitals optimization.
Entrega: HTML + CSS inline optimizado, form presupuesto con validación, imagen hero optimizada WebP, tests Lighthouse >90.

---

## ✅ SKILL: @qa-checker
Valida landing antes de deploy: Title 50-60 chars ✓, meta description 150-160 ✓, H1 único ✓, schema valid ✓, form funcional ✓, Core Web Vitals ✓.
Reporta en checklist .md con resultados. Bloquea deploy si falla Core Web Vitals o schema JSON.

---

## ✅ MCP: @DATA-LINEADIRECTA (Simulated)
Simula las APIs de LD: premia por código postal, cobertura según modelo moto (batería KWh), datos competencia (AXA, MAPFRE).
Endpoints mock: GET /pricing?zipcode=28001&battery_kwh=50 → JSON con precio, GET /competitors → ranking comparativo.

---

## 🔧 EJECUCIÓN PASO A PASO

**En Workshop (90 min):**

1. **Min 35:** Ejecuta PROMPT 1 (@seo-strategist) → guarda output en `_SESSION_ESTRATEGIA_SEO.md`
2. **Min 50:** Ejecuta PROMPT 2 (@marketing-copywriter) → guarda output en `_SESSION_COPYWRITING.md`
3. **Min 65:** Ejecuta PROMPT 3 (@html-implementer) → genera HTML en `tools/outputs/html/landing.html`
4. **Min 75:** Ejecuta @qa-checker → valida calidad en `_SESSION_VALIDACION.md`
5. **Min 85:** Muestra landing en navegador + explicar próximos pasos

**Salidas esperadas:**
- `_SESSION_ESTRATEGIA_SEO.md` (1-2 KB) 
- `_SESSION_COPYWRITING.md` (2-3 KB)
- `tools/outputs/html/landing.html` (5-8 KB)
- `_SESSION_VALIDACION.md` (checklist)

---

## 📚 REFERENCIAS
- [GitHub Copilot Agents Docs](https://code.visualstudio.com/docs/copilot/agents/overview)
- Tech Stack LD: Java, React, Bootstrap, Liferay CMS
- Schema Reference: https://schema.org/FAQPage, https://schema.org/LocalBusiness
- Core Web Vitals: https://web.dev/vitals/
