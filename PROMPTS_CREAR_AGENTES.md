# 🔧 PROMPTS PARA CREAR AGENTES - GitHub Copilot (via .github/)

**Propósito:** Prompts para DEFINIR/REGISTRAR los agentes en GitHub Copilot  
**Ubicación:** `.github/agents/` y `.github/skills/`  
**Framework:** GitHub Copilot Agents (basado en https://code.visualstudio.com/docs/copilot/agents/overview)

---

## 📁 ESTRUCTURA `.github/`

```
.github/
├── agents/
│   ├── seo-strategist.md          ← Agente 1: Estrategia SEO
│   ├── marketing-copywriter.md    ← Agente 2: Copywriting
│   └── html-implementer.md        ← Agente 3: Frontend React
├── skills/
│   └── qa-checker.md              ← Skill: Validación pre-deploy
└── references/
    └── EXTERNAL_SOURCES.md        ← Fuentes externas (URLs, metodologías)
```

---

## 🎯 PROMPT A: Crear Agente @seo-strategist

**Ubicación:** `.github/agents/seo-strategist.md`  
**Tipo:** Agent (model: sonnet)  
**Referencia:** Holistic SEO + Línea Directa

```markdown
Lee `.github/agents/seo-strategist.md`

Tu rol es ESTRATEGIA SEO HOLÍSTICA:
- Investigación keyword + intent classification
- Topical mapping (silos, clusters semánticos)
- Competitive analysis (tabla diferencial vs AXA/MAPFRE/Allianz)
- FAQ generation con search intent
- SERP features analysis

INPUT: Keyword primario + brief inicial
OUTPUT: Estructurado (JSON keys + topical tree + FAQs)

Referencias clave:
- Holistic SEO: https://www.holisticseo.digital/
- Caso: Seguros moto eléctrica España (LD diferencial = batería 12€/mes)
- Tech: Java backend, React, Liferay CMS (LD stack)
```

---

## 🎯 PROMPT B: Crear Agente @marketing-copywriter

**Ubicación:** `.github/agents/marketing-copywriter.md`  
**Tipo:** Agent (model: sonnet)  
**Referencia:** Línea Directa sitio real + psicología conversión

```markdown
Lee `.github/agents/marketing-copywriter.md`

Tu rol es COPYWRITER SEO + CONVERSION:
- H1 magnético (keyword + diferencial + urgencia suave)
- Body copy (3-5 párrafos cortos, 6to grado lectura)
- FAQs con schema JSON-LD
- CTAs psychology (reassurance + urgencia)
- Tono LD (transparencia, sin venta dura)

INPUT: Estrategia SEO anterior + specs técnicas
OUTPUT: Copy clean + FAQs schema + A/B suggestions

Referencia: 
- Sitio LD: https://www.lineadirecta.com (tono, CTAs structure)
- Competencia: AXA (caro), MAPFRE (complejo), Allianz (lento)
- Target: Propietarios eléctricos 30-45 años + comparadores precio
```

---

## 🎯 PROMPT C: Crear Agente @html-implementer

**Ubicación:** `.github/agents/html-implementer.md`  
**Tipo:** Agent (model: sonnet)  
**Referencia:** React + Bootstrap + Core Web Vitals

```markdown
Lee `.github/agents/html-implementer.md`

Tu rol es FRONTEND REACT OPTIMIZADO:
- React components + hooks (funcionales)
- Bootstrap 5 grid + responsive (xs/sm/md/lg/xl)
- Schema.org JSON-LD (FAQPage, LocalBusiness)
- Google Tag Manager integration
- Core Web Vitals optimization (LCP <2.5s, FID <100ms, CLS <0.1)
- Lighthouse >90 scores

INPUT: Specs SEO (URL, meta, schema) + Copy (H1, body, FAQs)
OUTPUT: landing.html (single file component, optimized)

Stack LD (referencia):
- Frontend: React, Bootstrap 5, Preact
- Analytics: GTM, Google Analytics, Microsoft Clarity
- CDN: Imperva (HSTS)
- Performance targets: LCP <2.5s, Lighthouse >90

Referencia: https://web.dev/vitals/
```

---

## 🎯 PROMPT D: Crear Skill @qa-checker

**Ubicación:** `.github/skills/qa-checker.md`  
**Tipo:** Skill (validador, no agente completo)  
**Referencia:** SEO técnico + Core Web Vitals + accesibilidad

```markdown
Lee `.github/skills/qa-checker.md`

Tu rol es QA VALIDACIÓN PRE-DEPLOY:
- 25-point checklist (SEO + schema + performance + accessibility)
- Core Web Vitals verification (no negociables: LCP <2.5s, CLS <0.1)
- Schema JSON-LD validation
- Lighthouse scoring
- WCAG 2.1 AA accessibility

INPUT: Landing HTML (del @html-implementer)
OUTPUT: Reporte con ✓ pass / ⚠ warning / ✗ fail

Referencias: 
- SEO técnico: https://github.com/gabinoguera/gh_seo
- Core Web Vitals: https://web.dev/vitals/
- Schema validator: https://schema.org/validator
- Lighthouse: https://pagespeed.web.dev/

BLOQUEOS CRÍTICOS:
- Core Web Vitals > límite → Deploy BLOCKED
- Schema JSON inválido → Deploy BLOCKED
- Accessibility contrast fail → Deploy BLOCKED
```

---

## 📌 CÓMO CREAR AGENTES EN GITHUB COPILOT

### Opción 1: VS Code GUI (Recomendado para demo)
```
1. Abre VS Code + Copilot Chat
2. Escribe: "@new-agent"
3. Pega el PROMPT A/B/C/D
4. Copilot pregunta parámetros (name, description, capabilities)
5. Agente creado ✓
```

### Opción 2: Crear desde `.github/` files (Reproducible)
```bash
# Los archivos ya existen en .github/agents/ y .github/skills/
# GitHub Copilot los auto-detecta al hacer referencia

# En Copilot Chat:
@seo-strategist        # Usa archivo .github/agents/seo-strategist.md
@marketing-copywriter  # Usa archivo .github/agents/marketing-copywriter.md
@html-implementer      # Usa archivo .github/agents/html-implementer.md
@qa-checker           # Usa archivo .github/skills/qa-checker.md
```

---

## 🔄 SECUENCIA CREACIÓN (Workshop)

### Min 0-5: Setup
- Verificar `.github/` folder (agents + skills + references)
- Abrir Copilot Chat en VS Code

### Min 5-10: Crear @seo-strategist
```
Copilot Chat:
"Lee .github/agents/seo-strategist.md y crea agente con esos parámetros"
```

### Min 10-15: Crear @marketing-copywriter
```
Copilot Chat:
"Lee .github/agents/marketing-copywriter.md y crea agente"
```

### Min 15-20: Crear @html-implementer
```
Copilot Chat:
"Lee .github/agents/html-implementer.md y crea agente"
```

### Min 20-23: Crear @qa-checker Skill
```
Copilot Chat:
"Lee .github/skills/qa-checker.md y crea skill"
```

### Min 23-25: Verificar agentes
```bash
# En VS Code Copilot Chat, prueba:
@seo-strategist hola
@marketing-copywriter hola
@html-implementer hola
@qa-checker hola
# Deben responder mostrando identidad
```

✅ **Resultado:** 3 Agents + 1 Skill listos para ejecutar

---

## 📚 REFERENCIAS PRINCIPALES

- **GitHub Copilot Agents:** https://code.visualstudio.com/docs/copilot/agents/overview
- **Holistic SEO:** https://www.holisticseo.digital/
- **Línea Directa:** https://www.lineadirecta.com
- **SEO Técnico:** https://github.com/gabinoguera/gh_seo
- **Core Web Vitals:** https://web.dev/vitals/
- **Schema.org:** https://schema.org/
- **Bootstrap 5:** https://getbootstrap.com/
- **React Docs:** https://react.dev/

---

## 📁 ARCHIVOS RELACIONADOS

Ver también:
- `PROMPTS_SECUENCIALES.md` - Prompts para USAR agentes (post-creación)
- `.github/references/EXTERNAL_SOURCES.md` - Todas las URLs de referencia
- `GUION_RESUMIDO_90MIN.md` - Timeline workshop
- `README_INDICE.md` - Índice completo

---

**Última actualización:** 6 Abril 2026  
**Framework:** GitHub Copilot Agents + .github/ structure
