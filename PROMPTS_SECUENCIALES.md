# 🤖 PROMPTS SECUENCIALES - Crear Pipeline Agentes

**Fecha:** 6 Abril 2026  
**Contexto:** Basados en tech stack real Línea Directa (Java, React, Bootstrap, Liferay)  
**Método:** Ejecutar de a uno. Respuestas en archivos .md compartidos

---

## 🛠️ FASE 1: CREAR AGENTES (Min 0-10)

### PROMPT 0A: Crear Agente @seo-strategist
Basándote en `.github/agents/seo-strategist.md`, crea un nuevo agente en GitHub Copilot llamado **@seo-strategist**.
Metodología: Holistic SEO (https://www.holisticseo.digital/) - keyword intent beyond volume, topical authority, entity-based approach.
Referencia técnica: Analiza desde perspectiva de Soluciones de Calidad Web (Addy Osmani, Core Web Vitals performance benchmark).
Especialización: Investigación keyword + topical mapping para verticales de seguros (españa.lineadirecta.com stack: Java backend, React frontend).
Dame confirmación cuando el agente esté creado.

---

### PROMPT 0B: Crear Agente @marketing-copywriter
Basándote en `.github/agents/marketing-copywriter.md`, crea un nuevo agente en GitHub Copilot llamado **@marketing-copywriter**.
Referencia directa: Estudia el tono, estructura, CTAs y diferencial en https://www.lineadirecta.com (transparencia, precio 12€, batería incluida).
Especialización: Copywriting conversion-focused para seguros online, H1 magnetic, FAQs schema markup, tono empático sin venta dura.
Dame confirmación cuando el agente esté creado.

---

### PROMPT 0C: Crear Agente @html-implementer
Basándote en `.github/agents/html-implementer.md`, crea un nuevo agente en GitHub Copilot llamado **@html-implementer**.
Especialización: HTML5 semántico + Bootstrap 5 grid, responsive mobile-first, schema.org JSON-LD (FAQPage, LocalBusiness), CSS inline optimizado.
Referencia: Bootstrap 5 best practices + Addy Osmani web quality standards (performance, accessibility, SEO).
Objetivo: Landing page completo en UN ARCHIVO HTML único, listo para abrir en navegador inmediatamente, sin dependencias externas. El usuario debe poder ver el resultado final en 2 clicks (open file → view browser).
Dame confirmación cuando el agente esté creado.

---

### PROMPT 0D: Crear Skill @qa-checker
Basándote en `.github/skills/qa-checker.md`, crea un nuevo skill en GitHub Copilot llamado **@qa-checker**.
Referencia: SEO técnico (https://github.com/gabinoguera/gh_seo) + Core Web Vitals checklist (Addy Osmani standards).
Especialización: 25-point validation checklist (SEO on-page + schema markup + performance + accessibility).
Validaciones críticas: Core Web Vitals no negociables (LCP, CLS), schema JSON-LD válido, accessibility contrast >4.5:1.
Dame confirmación cuando el skill esté creado.

---

## 🎬 FASE 2: EJECUTAR AGENTES (Min 10-90)

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
Eres developer frontend especializado en HTML5 + Bootstrap. Implementa landing usando especificaciones técnicas SEO + copywriting anterior.
Tecnologías: HTML5 semántico, Bootstrap 5 grid, schema.org FAQ markup (JSON-LD inline), CSS inline optimizado en <head>.
Entrega: landing.html completo (SINGLE FILE, todo inline, cero dependencias externas) listo para abrir en navegador inmediatamente.
Instrucciones: 
- Responsive mobile-first (Bootstrap xs/sm/md/lg breakpoints)
- Form presupuesto funcional (HTML5 validation)
- Semantic HTML (header, nav, main, section, article, footer)
- User debe poder hacer: 1) Copiar archivo, 2) Doble-click en file explorer, 3) Ver landing en navegador. SOLO ESO.

---

## ✅ PROMPT 4: @QA-CHECKER
Valida landing antes de deploy: Title 50-60 chars ✓, meta description 150-160 ✓, H1 único ✓, schema valid ✓, form funcional ✓, Core Web Vitals ✓.
Reporta en checklist .md con resultados. Bloquea deploy si falla Core Web Vitals o schema JSON.

---

## 🔧 EJECUCIÓN PASO A PASO

**En Workshop (90 min total):**

### FASE 1: CREAR AGENTES (Min 0-10)
1. **Min 0-2:** Ejecuta PROMPT 0A → @seo-strategist creado ✓
2. **Min 2-5:** Ejecuta PROMPT 0B → @marketing-copywriter creado ✓
3. **Min 5-8:** Ejecuta PROMPT 0C → @html-implementer creado ✓
4. **Min 8-10:** Ejecuta PROMPT 0D → @qa-checker creado ✓

### FASE 2: USAR AGENTES (Min 10-85)
5. **Min 10-30:** Ejecuta PROMPT 1 (@seo-strategist) → guarda output en `_SESSION_ESTRATEGIA_SEO.md`
6. **Min 30-50:** Ejecuta PROMPT 2 (@marketing-copywriter) → guarda output en `_SESSION_COPYWRITING.md`
7. **Min 50-70:** Ejecuta PROMPT 3 (@html-implementer) → genera HTML en `tools/outputs/html/landing.html`
8. **Min 70-80:** Ejecuta PROMPT 4 (@qa-checker) → valida calidad en `_SESSION_VALIDACION.md`
9. **Min 80-85:** Muestra landing en navegador (double-click HTML file) + explicar próximos pasos
10. **Min 85-90:** Q&A + feedback

**Salidas esperadas:**
- `_SESSION_ESTRATEGIA_SEO.md` (1-2 KB) 
- `_SESSION_COPYWRITING.md` (2-3 KB)
- `tools/outputs/html/landing.html` (single file, ~10-15 KB, completamente funcional)
- `_SESSION_VALIDACION.md` (checklist)

---

## 📚 REFERENCIAS PRINCIPALES

### Metodologías & Frameworks
- **Holistic SEO:** https://www.holisticseo.digital/ (keyword intent, topical authority, entity-based)
- **GitHub Copilot Agents:** https://code.visualstudio.com/docs/copilot/agents/overview
- **Core Web Vitals & Performance:** https://web.dev/vitals/ (Addy Osmani - Web Quality Standards)
- **SEO Técnico:** https://github.com/gabinoguera/gh_seo (validaciones pre-deploy)

### Referencias en Vivo
- **Línea Directa Sitio Real:** https://www.lineadirecta.com (tono, estructura, CTAs, diferencial)
- **Competencia:** AXA, MAPFRE, Allianz (análisis comparativo)
- **Wappalyzer Tech Stack LD:** Java backend, React frontend, Bootstrap 5, Liferay CMS, GTM, Imperva CDN

### Validadores
- **Schema.org:** https://schema.org/ (FAQPage, LocalBusiness, BreadcrumbList)
- **Google PageSpeed:** https://pagespeed.web.dev/
- **Lighthouse:** https://developers.google.com/web/tools/lighthouse

---

## 🚀 CÓMO EJECUTAR EN WORKSHOP

### Antes de empezar
```bash
# Terminal 1: Verificar setup
cd ~/Documents/BrainCode/LINEA\ DIRECTA
source tools/.venv/bin/activate
python3 -c "from dotenv import load_dotenv; load_dotenv(); import os; print(f'✓ LD Ready: {os.getenv(\"COMPANY_NAME\")}')"
```

### En VS Code - Copilot Chat
```
1. Abre Copilot Chat (Cmd+I o Ctrl+I)
2. Copia cada PROMPT secuencialmente 
3. Pega en Copilot Chat
4. Copilot responde
5. Guarda responses en archivos _SESSION_*.md
```

### Ubicación de archivos para guardar
```
/Users/simba/Documents/BrainCode/LINEA\ DIRECTA/
├── _SESSION_ESTRATEGIA_SEO.md      (output PROMPT 1)
├── _SESSION_COPYWRITING.md          (output PROMPT 2)
├── _SESSION_VALIDACION.md           (output PROMPT 4)
└── tools/outputs/html/
    └── landing.html                 (output PROMPT 3)
```

### Resultado Final en Workshop
```bash
# Min 80: Abrir landing en navegador
open ~/Documents/BrainCode/LINEA\ DIRECTA/tools/outputs/html/landing.html

# Debería verse una página HTML responsiva con:
# - Hero section con H1 magnetic
# - 3 pain-point sections
# - 5 FAQs (expandibles idealmente)
# - Form "Calcula presupuesto"
# - Footer con info LD
# - TODO inline, responsive, sin errores HTML5
```

---

**Última actualización:** 6 Abril 2026  
**Framework:** GitHub Copilot Agents + HTML5 + Bootstrap 5 (sin React, sin complicaciones)
