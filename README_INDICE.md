# 📑 ÍNDICE DE DOCUMENTACIÓN v3 - WORKSHOP LÍNEA DIRECTA

**Fecha:** 6 Abril 2026 (ACTUALIZADO)  
**Evento:** Workshop: Pipeline Multi-Agente SEO para Línea Directa  
**Duración:** 90 minutos  
**Enfoque:** Agentes GitHub Copilot, resumido, actionable, divisido por roles
**Tech Stack LD:** Java backend, React frontend, Bootstrap, Liferay CMS, Google Analytics

---

### 1️⃣ **GUION_RESUMIDO_90MIN.md** ← 👈 EMPIEZA AQUÍ
**Tamaño:** 3 páginas (condensado)  
**Enfoque:** Timeline clara, sin fluff, basada en GitHub Copilot Agents

**Qué contiene:**
- ⏱️ Timeline 90 min (10 módulos)
- 🧠 Conceptos 3 agentes GitHub Copilot (@seo-strategist, @marketing-copywriter, @html-implementer)
- 💻 Setup .env + Python (PRE-HECHO)
- 🚀 Demo en vivo con agentes
- 🔗 Flujo agentes mediante sesiones .md compartidas
- 📚 Q&A rápido + recursos

**👉 USA CUANDO:** Facilitar el workshop (guía del instructor en clase)

---

### 2️⃣ **BRIEF_LANDING_MOTO_ELECTRICA.md** ← 📄 PARA MARKETING
**Tamaño:** 2 páginas (simplificado)  
**Audiencia:** Marketing Team + punto de partida para @seo-strategist

**Qué contiene:**
- 🎯 Objetivo del landing (conversión presupuesto)
- 👥 Audiencia en 3 segmentos
- 🔑 Diferenciadores LD vs competencia (tabla)
- 📝 CTAs recomendados
- ✅ Próximos pasos (flujo con agentes)

**IMPORTANTE:** La investigación SEO detallada (keywords, competitors, topical map) **la hace el @seo-strategist agent**, NO está aquí.

**👉 USA CUANDO:** Marketing briefing inicial + pasa a agentes para desarrollo

---

### 3️⃣ **PROMPTS_SECUENCIALES.md** ← 🤖 PARA EJECUTAR AGENTES
**Tamaño:** 1 página  
**Audiencia:** Instructor + participantes técnicos

**Qué contiene:**
- 4 prompts de máximo 5 líneas cada uno (máxima claridad)
- @seo-strategist → genera estrategia SEO
- @marketing-copywriter → redacta copy basado en estrategia
- @html-implementer → desarrolla landing con React + Bootstrap
- @qa-checker skill → valida calidad antes de deploy
- MCP simulado → datos de precios/competencia

**Salidas esperadas:** Archivos .md compartidos en sesión

**👉 USA CUANDO:** Ejecutar agentes uno por uno durante el workshop

---

### 4️⃣ **SPECS_SEO_BASE.md** ← 🔍 TEMPLATE PARA AGENTE
**Tamaño:** 10 páginas (TEMPLATE editable)  
**Audiencia:** Dev Team + @html-implementer + @seo-strategist

**Qué contiene:**
- 📌 Especificación rápida (meta title, description, H1, schema)
- 🎯 Keywords (primary/secondary/LSI) 
- ✅ Checklist técnico SEO
- 🎨 Requerimientos visuales

**IMPORTANTE:** El @seo-strategist **MODIFICA/COMPLETA** este template con descubrimientos, el @html-implementer lo usa para desarrollo.

**👉 USA CUANDO:** Devs necesitan saber qué especificaciones aplicar

---

### 5️⃣ **00_RESUMEN_EJECUTIVO.md** ← 📊 CONTEXT + SEQUENCING
**Tamaño:** 1 página  
**Audiencia:** Ejecutivos + coordinador del workshop  

**Qué contiene:**
- 🗺️ Mapa de documentos
- ⏰ Sequencing exacto (HOY/Próximas semanas)
- 🎯 Resultados esperados

**👉 USA CUANDO:** Entender contexto general + timeline del proyecto

---

## 🤖 ARQUITECTURA AGENTES (GitHub Copilot)

### Agentes Principales
```
@seo-strategist
├─ INPUT: Brief + keyword target
├─ OUTPUT: SPECS_SEO_BASE.md actualizado + topical map + FAQs
└─ FLOW: Sesión guardada en _SESSION_ESTRATEGIA_SEO.md

@marketing-copywriter
├─ INPUT: Estrategia SEO anterior + audiencias
├─ OUTPUT: H1 + body copy + FAQs
└─ FLOW: Sesión guardada en _SESSION_COPYWRITING.md

@html-implementer
├─ INPUT: Especificaciones SEO + copywriting
├─ OUTPUT: landing.html (React + Bootstrap + schema markup)
└─ FLOW: Archivo en tools/outputs/html/landing.html
```

### Skills
- **@qa-checker:** Valida antes de deploy (SEO + Core Web Vitals + schema)

### MCPs (Simulados)
- **@DATA-LINEADIRECTA:** Precios por zipcode, coberturas, datos competidores

---

## 📚 REFERENCIAS

- **GitHub Copilot Agents:** https://code.visualstudio.com/docs/copilot/agents/overview
- **VS Code Extension Marketplace:** https://marketplace.visualstudio.com
- **Tech Stack LD:** Java, React, Bootstrap, Liferay CMS, Google Analytics
- **Schema.org:** https://schema.org/FAQPage, https://schema.org/LocalBusiness
- **Core Web Vitals:** https://web.dev/vitals/

---

## 🗂️ ESTRUCTURA ARCHIVOS

```
~/Documents/BrainCode/LINEA DIRECTA/
├── README_INDICE.md (esto)
├── GUION_RESUMIDO_90MIN.md
├── PROMPTS_SECUENCIALES.md ← PARA EJECUTAR AGENTES
├── BRIEF_LANDING_MOTO_ELECTRICA.md
├── SPECS_SEO_BASE.md (template editable)
├── 00_RESUMEN_EJECUTIVO.md
├── _SESSION_ESTRATEGIA_SEO.md (generado por @seo-strategist)
├── _SESSION_COPYWRITING.md (generado por @marketing-copywriter)
├── _SESSION_VALIDACION.md (generado por @qa-checker)
├── .env (configuración LD)
├── .gitignore
├── tools/
│   ├── .venv/ (Python virtualenv)
│   ├── requirements.txt
│   └── outputs/html/
│       └── landing.html (generado por @html-implementer)
└── .git/
    └── ... (GitHub repo)
```

---

## 🚀 CÓMO EMPEZAR (6 Abril 2026)

1. Lee **GUION_RESUMIDO_90MIN.md** (5 min)
2. Verifica setup: `.env` + `tools/.venv/` + `requirements.txt`
3. Abre **PROMPTS_SECUENCIALES.md**
4. Ejecuta agentes con GitHub Copilot Chat en VS Code
5. Outputs se guardan en archivos compartidos (`_SESSION_*.md`)

---

**Última actualización:** 6 Abril 2026 - Actualizado con GitHub Copilot Agents + PROMPTS_SECUENCIALES.md
