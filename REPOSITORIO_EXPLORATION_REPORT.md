# Exploración: .claude/ en gabinoguera/mkt-ghen-workshop

**Repositorio:** https://github.com/gabinoguera/mkt-ghen-workshop  
**Rama:** main  
**Carpeta:** `.claude/`  
**Fecha exploración:** 2026-04-06

---

## 1. ESTRUCTURA COMPLETA DE `.CLAUDE/`

```
.claude/
├── agents/
│   ├── html-implementer.md
│   ├── marketing-copywriter.md
│   ├── seo-strategist.md
│   ├── seo-tecnico.md
│   └── wp-implementer.md
├── doc/
│   └── wordpress-reference/
│       └── (directorio con referencias)
├── sessions/
│   └── TEMPLATE.md
└── skills/
    ├── copywriting/
    │   ├── SKILL.md
    │   └── references/
    ├── seo/
    │   ├── SKILL.md
    │   └── references/
    │       ├── topical-authority.md
    │       ├── semantic-seo.md
    │       ├── generative-engine-optimization.md
    │       ├── multilingual-seo.md
    │       ├── topical-map-template.md
    │       ├── geo-audit-pipeline.md
    │       └── (otros referencias)
    └── seo-tecnico/
        ├── SKILL.md
        └── references/
```

---

## 2. ARCHIVOS PRINCIPALES CON CONTENIDO REAL

### 2.1 AGENTES (5 archivos .md)

#### **marketing-copywriter.md** (775 líneas)
**Tipo:** Agent Definition  
**Propósito:** Copywriter técnico para GHEN Digital (ghendigital.com)

**FRONTMATTER YAML:**
```yaml
---
name: marketing-copywriter
description: "Technical copywriter for GHEN Digital. Writes content in Spanish for 
ghendigital.com — blog posts (Actualidad IA and Lab), page copy, and SEO meta. Works 
from SEO content briefs produced by @seo-strategist. Combines technical accuracy with 
accessible writing for the AI/dev audience."
model: sonnet
color: magenta
---
```

**Estructura del contenido:**
1. **Goal** — Escribir contenido que construya autoridad + sirva necesidades técnicas + posicione a Gabi
2. **The Platform** — Contexto WordPress (Astra Child + Gutenberg + Rank Math)
3. **Before Any Task** — Checklist de 5 pasos (leer sesión, brief SEO, contexto, metodología)
4. **Context Files** — Rutas a archivos de contexto
5. **Integration with SEO Workflow** — Pipeline: `@seo-strategist` → `@marketing-copywriter` → `@wp-implementer`
6. **Rules** — Voz, tono, contenido técnico, dos audiencias, principios, puntos probables
7. **Content Type Guidelines** — 4 tipos: Actualidad IA Posts, Lab Posts, About Page, Contacto Page
8. **Output Format** — Content Deliverable, SEO Meta, Annotations, Alternatives, Featured Image Prompt, Handoff Notes
9. **Tools** — QA Checker (validación de contenido)
10. **What This Agent Does NOT Do** — Define estrategia SEO, no implementa WP, no diseña UI
11. **Related Agents** — Links a @seo-strategist, @wp-implementer

**Fragmento real del contenido (Rules - Forbidden Patterns):**
```markdown
### Forbidden Patterns

- No exclamation points in body copy
- No "revolucionar", "transformar", "disruptivo", "potenciar", "game-changer" 
  (vacíos de significado)
- No fabricated statistics or testimonials
- No hype claims without backing ("el mejor modelo", "la única solución")
- Avoid AI-tell phrases: "En el panorama actual...", "Cabe destacar que...", 
  "Es importante señalar...", "En definitiva..."
- Don't over-explain basics to a technical audience — they'll find it condescending
```

**Fragmento real - Content Type (Lab Posts):**
```markdown
### Lab Posts (`/lab/`)

**Purpose:** Documentación de proyectos, experimentos y workflows reales.
**Length:** 1500-3000 words
**Structure:**
1. Contexto y motivación del proyecto
2. Problema o reto específico
3. Solución implementada (con código cuando aplica)
4. Resultados — incluyendo lo que no funcionó
5. Lecciones aprendidas y conclusiones
6. CTA: "Si tu empresa necesita esto, hablemos" (→ /contacto/)

**Voice:** Narrative + técnico. Documenta como un diario: proceso real, no resultado perfecto.
**Author attribution:** Gabriel Noguera (siempre)
```

---

#### **seo-strategist.md** (800+ líneas)
**Tipo:** Agent Definition  
**Propósito:** SEO/GEO strategist basado en Holistic SEO (Koray Tugberk GUBUR)

**FRONTMATTER YAML:**
```yaml
---
name: seo-strategist
description: "SEO and GEO strategist for GHEN Digital. Designs topical maps, semantic 
content architecture, and positioning strategies for [YOUR_SITE_URL]. Optimizes for both 
traditional search engines and AI-generated responses (GEO). Research and planning only — 
never implements."
model: sonnet
color: cyan
---
```

**Estructura:**
1. **Goal** — Research, analyze, produce SEO/GEO strategies, topical maps, content architectures
2. **Before Any Task** — 5 pasos: leer sesión, leer CLAUDE.md, leer referencias, usar MCPs para datos reales, WebFetch
3. **Your Domain Expertise** — GHEN Digital specifics, URL structure, categorías, SEO Methodology (Topical Authority, Semantic Networks, Cost of Retrieval, Information Gain, GEO)
4. **Capabilities** — 10 capabilities listadas (GSC Audit, GA4 Analysis, AI Overview Detection, GEO Citation Test, Topical Map, Content Architecture, SERP Analysis, Semantic Audit, GEO Strategy, Schema Strategy, Quick Wins)
5. **Workflow** — 9 pasos desde lectura de sesión hasta output
6. **Output Format** — Para Topical Maps, Para Content Briefs, Para Audits
7. **Schema Markup Guidelines** — Tabla con tipos schema por contenido
8. **Content Type Guidelines** — Actualidad IA Posts, Lab Posts, Pillar Pages
9. **Tools** — SERP Analyzer, MCPs (GSC, GA4, Playwright)
10. **What This Agent Does NOT Do** — No escribe copy, no implementa WP, no hace decisiones de negocio

**Fragmento real - Workflow:**
```markdown
## Workflow

1. Read session file `.claude/sessions/{feature}.md` (create from TEMPLATE if new)
2. Read context (CLAUDE.md, references)
3. Identify the specific task (audit, topical map, brief, strategy)
4. Research:
   - **Datos reales (usar siempre para auditorías):**
     - `mcp__gsc__get_performance_overview` — overview 90 días
     - `mcp__gsc__get_search_analytics` dim=query/page — top queries y páginas
     - `mcp__gsc__compare_search_periods` — tendencia por periodos
     - `mcp__gsc__check_indexing_issues` — problemas de indexación
     - `mcp__google-analytics__run_report` — sesiones orgánicas, bounce, avg time
```

**Fragmento real - Domain Expertise:**
```markdown
### SEO Methodology (Holistic SEO / Koray Tugberk GUBUR)

**Topical Authority = Topical Coverage + Historical Data**

You apply these frameworks:

1. **Topical Maps** — Hierarchical semantic maps with:
   - Source Context (site purpose and monetization)
   - Central Entity (the entity present across all sections)
   - Central Search Intent (unified intent throughout)
   - Core Section (primary entity attributes)
   - Outer Section (minor attributes, trust propagation)
   - Root Documents (central hubs) and Node Documents (quality/coverage nodes)

2. **Semantic Content Networks** — Interconnected content organized by:
   - Cornerstone content (who, what, where, how)
   - Subtopic clusters with semantic relationships
   - Micro-topics addressing specific intents
   - Contextual internal linking mirroring the topical graph

3. **Cost of Retrieval** — Minimize the effort search engines and LLMs need to:
   - Crawl, understand, evaluate, index, rank, and serve content
   - Lower cost = higher ranking potential AND higher probability of AI citation

4. **Information Gain** — Every content piece must provide unique value not found in top 10 results.
   - GHEN's unique angle: real production experience + verified projects + independent technical opinion

5. **GEO (Generative Engine Optimization)** — Equal priority to traditional SEO:
   - EAV Architecture (Entity-Attribute-Value) for AI extraction
   - Definitional authority over key concepts (LLMs, prompt engineering, MCP, RAG, etc.)
   - Query Responsiveness across all query variations
   - Structured data optimized for LLM parsing
   - E-E-A-T signals demonstrable through topical coverage and author credentials
```

---

#### **html-implementer.md** (500+ líneas)
**Tipo:** Agent Definition  
**Propósito:** Generador static HTML con JavaScript para artículos/páginas

**FRONTMATTER YAML:**
```yaml
---
name: html-implementer
description: "Static HTML generator for GHEN Digital. Generates standalone HTML pages 
with embedded JavaScript from content briefs and copy deliverables. Creates 
self-contained, production-ready HTML files with SEO meta, schema markup, and responsive 
design. Implements plans from seo-strategist and copy from marketing-copywriter."
model: sonnet
color: blue
---
```

**Estructura:**
1. **Goal** — Generate production-ready HTML with embedded JS, complete con SEO meta, schema markup, responsive design
2. **Before Any Task** — Check implementation path (HTML local vs WordPress), read sesión, leer CLAUDE.md, leer copy deliverable, leer strategy doc
3. **Technical Implementation Details** (sección nueva):
   - HTML Output Requirements (HTML5 semantic, CSS embedded, JS vanilla, SEO Meta, Schema JSON-LD, WCAG 2.1 AA, performance)
   - Schema Markup Requirements (tabla con tipos por content type)
   - File Structure (outputs/html/{feature-name}/)
4. **Capabilities** — 8 capabilities (HTML Generation, Schema Markup, Meta Tags, Responsive Design, FAQ Sections, Featured Images, Documentation)
5. **Tools** — Local HTML Generator, Featured Image Generator (Gemini), QA Checker
6. **Output Format** — Implementation Guide, Generated HTML Summary, Pre/Post Checklist
7. **Generated HTML Structure** — Meta tags, schema markup, CSS, JS, layout, typography, accessibility
8. **What This Agent Does NOT Do** — No define estrategia SEO, no escribe copy, no deploya a producción, **no publica en WordPress**
9. **Categories Reference** — Tabla con categorías (ACTUALIDAD IA, LAB, INTELIGENCIA ARTIFICIAL, SEO, MARKETING DIGITAL, CODE, ANALYTICS, WORDPRESS, WORK, PORTFOLIO)
10. **Example Workflow** — 9 pasos detallados con comando bash exactos

**Fragmento real - Tools (Local HTML Generator):**
```bash
# Generate HTML from copy deliverable
tools/.venv/bin/python tools/local_generator.py generate \
    --file .claude/doc/{feature}/copy-deliverable.md \
    --feature-name {feature} \
    --category "Lab"

# For Actualidad IA content
tools/.venv/bin/python tools/local_generator.py generate \
    --file .claude/doc/{feature}/copy-deliverable.md \
    --feature-name {feature} \
    --category "Actualidad IA"
```

**Output structure:**
```
outputs/html/{feature}/
├── index.html          # Complete HTML with embedded CSS/JS
├── README.md           # Auto-generated documentation
└── assets/
    └── featured.jpg    # Featured image (must be generated separately)
```

**Fragmento real - Copy Deliverable Requirements:**
```markdown
## Technical Implementation Details

### Copy Deliverable Requirements

The copy deliverable **must** include a SEO Meta section with:

\`\`\`markdown
## SEO Meta

**Page title:** SEO optimized title (max 60 chars)
**Meta description:** Compelling description (max 155 chars)
**Rank Math focus keyword:** main-keyword
**Slug:** url-slug-here
**Category:** Lab
**Tags:** tag1, tag2, tag3
\`\`\`
```

---

#### **wp-implementer.md** (mencionado pero no explorado en detalle)
**Tipo:** Agent Definition  
**Propósito:** Implementación técnica en WordPress

#### **seo-tecnico.md** (mencionado pero no explorado en detalle)
**Tipo:** Agent Definition  
**Propósito:** Auditoría técnica de SEO post-implementación

---

### 2.2 SKILLS (3 directorios con SKILL.md)

#### **copywriting/SKILL.md** (500+ líneas)
**Tipo:** Skill Definition  
**Propósito:** Metodología de copywriting

**FRONTMATTER YAML:**
```yaml
---
name: copywriting
description: When the user wants to write, rewrite, or improve marketing copy for any 
page — including homepage, landing pages, pricing pages, feature pages, about pages, or 
product pages. Also use when the user says "write copy for," "improve this copy," 
"rewrite this page," "marketing copy," "headline help," or "CTA copy." For email copy, 
see email-sequence. For popup copy, see popup-cro.
---
```

**Estructura:**
1. **Before Writing** — Gather context (Page Purpose, Audience, Product/Offer, Context)
2. **Copywriting Principles** — Clarity Over Cleverness, Benefits Over Features, Specificity Over Vagueness, Customer Language Over Company Language, One Idea Per Section
3. **Writing Style Rules** — Core Style Principles (6 reglas) + Quick Quality Check
4. **Best Practices** — Be Direct, Use Rhetorical Questions, Use Analogies and Metaphors, Pepper in Humor
5. **Page Structure Framework** — Above the Fold (Headline formulas, Subheadline, Primary CTA, Supporting Visual), Social Proof, Problem/Pain, Solution/Benefits, How It Works, FAQ, Objection Handling, Final CTA
6. **Landing Page Section Variety** — 12 tipos de secciones + recommended mix
7. **CTA Copy Guidelines** — Weak vs Strong CTAs, CTA formula
8. **Output Format** — Page Copy, Annotations, Alternatives, Meta Content
9. **Page-Specific Guidance** — Homepage, Landing Page, Pricing Page, Feature Page, About Page
10. **Voice and Tone Considerations**
11. **Related Skills** — copy-editing, page-cro, email-sequence, popup-cro, ab-test-setup

**Fragmento real - Headline Formulas:**
```markdown
**Headline Formulas:**

**{Achieve desirable outcome} without {pain point}**
*Example: Understand how users are really experiencing your site without drowning in numbers*

**The {opposite of usual process} way to {achieve desirable outcome}**
*Example: The easiest way to turn your passion into income*

**Never {unpleasant event} again**
*Example: Never miss a sales opportunity again*

**{Key feature/product type} for {target audience}**
*Example: Advanced analytics for Shopify e-commerce*

**{Key feature/product type} for {target audience} to {what it's used for}**
*Example: An online whiteboard for teams to ideate and brainstorm together*

**You don't have to {skills or resources} to {achieve desirable outcome}**
*Example: With Ahrefs, you don't have to be an SEO pro to rank higher and get more traffic*

**{Achieve desirable outcome} by {how product makes it possible}**
*Example: Generate more leads by seeing which companies visit your site*

**{Key benefit of your product}**
*Example: Sound clear in online meetings*

**{Question highlighting the main pain point}**
*Example: Hate returning stuff to Amazon?*

**Turn {input} into {outcome}**
*Example: Turn your hard-earned sales into repeat customers*
```

**Fragmento real - CTA Copy Guidelines:**
```markdown
## CTA Copy Guidelines

**Weak CTAs (avoid):**
- Submit
- Sign Up
- Learn More
- Click Here
- Get Started

**Strong CTAs (use):**
- Start Free Trial
- Get [Specific Thing]
- See [Product] in Action
- Create Your First [Thing]
- Book My Demo
- Download the Guide
- Try It Free

**CTA formula:**
[Action Verb] + [What They Get] + [Qualifier if needed]

Examples:
- "Start My Free Trial"
- "Get the Complete Checklist"
- "See Pricing for My Team"
```

---

#### **seo/SKILL.md** (400+ líneas)
**Tipo:** Skill Definition  
**Propósito:** Framework de SEO & GEO Strategy

**FRONTMATTER YAML:**
```yaml
---
name: seo
description: When the user wants to create a topical map, plan SEO content strategy, 
audit semantic coverage, optimize for AI-generated search results (GEO), plan multilingual 
SEO, create content briefs, or analyze competitors. Also use when the user says "SEO 
strategy for," "topical map for," "content architecture," "optimize for AI Overviews," 
"semantic audit," "content brief for," or "GEO strategy."
---
```

**Estructura:**
1. **Before Starting** — Read methodology references en `.claude/skills/seo/references/`
2. **Workflow** — 5 pasos CONTEXTO → ANÁLISIS → ESTRATEGIA → EJECUCIÓN → OUTPUT
   - ANÁLISIS detalla: For existing content (audit, semantic, schema, internal links); For new content (query space, entities, SERP, Information Gain)
   - Tools priority: GSC MCP > GA4 MCP > Playwright MCP > WebSearch > WebFetch > Read
3. **Core Principles (Always Apply)** — Topical Authority, Semantic SEO, Cost of Retrieval, Information Gain, GEO, Publishing Cadence
4. **Content Type Templates** — Pillar Page, Cluster Page, Micro-Topic Page, Glossary/Definition Page
5. **GHEN Digital Content Types** — Tabla con Sección | Tipo | Schema Rank Math | Schema Spectra

**Fragmento real - Tools (ANÁLISIS section):**
```markdown
**Tools to use (en orden de prioridad):**
- **GSC MCP** (`mcp__gsc__*`) — datos reales: queries, páginas, CTR, posición, indexación.
  Site: `sc-domain:[YOUR_DOMAIN]`
- **GA4 MCP** (`mcp__google-analytics__*`) — engagement real: sesiones, bounce, tiempo. 
  Property ID: `<YOUR_GA4_PROPERTY_ID>`
- **Playwright MCP** (`mcp__playwright__*`) — verificar citación en ChatGPT, Perplexity, Claude.ai
- WebSearch — análisis de SERPs y competidores
- WebFetch — auditoría de contenido de páginas concretas
- Read — referencias de metodología en `.claude/skills/seo/references/`
```

**Fragmento real - Core Principles:**
```markdown
### GEO (Generative Engine Optimization)

- AI systems select sources similarly to topical authority evaluation
- EAV triples make content extractable by LLMs
- Definitional authority influences generated answers
- Structured, machine-friendly content gets cited more

### Publishing Cadence

- **Consistency > volume** — better 2 posts/week than 10 posts then silence
- **Actualidad IA:** Higher cadence possible (news-driven), 2-4 posts/week
- **Lab:** Quality over quantity, 1-2 posts/week (deeper, technical content)
- Minimum viable cadence: 2 quality posts per week across both sections
```

**Fragmento real - Content Type Templates (table):**
```markdown
## GHEN Digital Content Types

| Sección | Tipo | Schema Rank Math | Schema Spectra |
|---------|------|-----------------|----------------|
| Actualidad IA | BlogPosting | Article | FAQPage (optional) |
| Lab | BlogPosting | Article | FAQPage, HowTo |
| Inteligencia Artificial | Article | Article | FAQPage |
| About | WebPage | WebPage + Person | — |
| Contacto | WebPage | WebPage | — |
```

---

### 2.3 SESSIONS

#### **TEMPLATE.md** (250+ líneas)
**Tipo:** Session Document Template  
**Propósito:** Documento compartido entre agentes para coordinar workflow

**Estructura:**
```markdown
# Feature: {feature_name}

> Documento de sesión compartido entre agentes. Cada agente lee TODO el documento
> antes de trabajar y rellena SU sección al terminar. Los deliverables completos
> van en `.claude/doc/{feature_name}/`.

**Estado:** `backlog` → `strategy` → `copy` → `qa-review` → `implementation` → 
`tecnico-review` → `done`

**Estado actual:** `backlog`

**Fecha inicio:** YYYY-MM-DD
**Última actualización:** YYYY-MM-DD

---

## Decisiones estratégicas
// Rellena: @seo-strategist
// Deliverable completo: `.claude/doc/{feature_name}/seo-strategy.md`

- **Target query principal:**
- **Queries secundarias:**
- **Intent:** informational | commercial | transactional | navigational
- **Tipo de contenido:** blog post | landing page | pillar page | micro-topic
- **URL slug:** `/`
- **Word count orientativo:**
- **Schema recomendado:**
  - Rank Math (page-level):
  - Spectra (block-level):
- **Information Gain angle:**
- **Competidores analizados:** (URLs o referencia a `competitive-analysis/`)
- **Internal links recomendados:**
  - [anchor text](URL destino)
- **Notas para copywriter:**

---

## Decisiones de copy
// Rellena: @marketing-copywriter
// Deliverable completo: `.claude/doc/{feature_name}/copy-deliverable.md`

- **H1 elegido:**
- **Audiencia principal:** writers B2C | editorial B2B
- **SEO meta:**
  - Title (≤60):
  - Description (≤155):
  - Focus keyword:
- **Prompt imagen destacada:**
  \`\`\`
  (prompt en inglés, ~60-80 palabras)
  \`\`\`
- **QA score:** /100
- **Secciones con Spectra blocks:**
  - FAQ: sí/no
  - How-To: sí/no
  - Review: sí/no
- **Notas para implementer:**

---

## Implementación
// Rellena: @wp-implementer | @html-implementer
// Deliverable completo: `.claude/doc/{feature_name}/wp-implementation.md` 
//                        o `.claude/doc/{feature_name}/html-implementation.md`

- **Post ID:**
- **Post URL:**
- **Estado WP:** draft | publish
- **Categoría:**
- **Tags:**
- **Imagen destacada:**
  - Media ID:
  - Archivo: `outputs/`
- **Rank Math meta aplicado:** sí/no
- **Schema verificado:** sí/no
- **Verificaciones:**
  - [ ] Post visible en preview
  - [ ] Schema válido (Rich Results Test)
  - [ ] Meta tags correctos (inspeccionar fuente)
  - [ ] Imagen destacada visible
  - [ ] Internal links funcionan
- **Notas / incidencias:**
- **Notas para seo-tecnico:**

---

## Diagnóstico técnico SEO
// (OPCIONAL - solo cuando interviene @seo-tecnico)

- **URL(s) auditada(s):**
- **Modo:** standalone | post-implementación | cross-consult
- **Indexación:** indexada | no indexada | excluida (motivo)
- **Canonical declarado:**
- **Canonical seleccionado por Google:**
- **Core Web Vitals:**
  - LCP: — (lab) | — (field)
  - INP: — (lab) | — (field)
  - CLS: — (lab) | — (field)
- **Schema válido:** sí | no | parcial
- **Issues críticos:**
- **Issues altos:**
- **Issues medios:**
- **Acciones para @wp-implementer:**
- **Notas para @seo-strategist:**
```

---

## 3. ESTRUCTURA DE FRONTMATTER YAML

**Patrón para AGENTS:**
```yaml
---
name: [agent-name]
description: "[Brief description of what this agent does, when to use it, what keywords trigger it]"
model: sonnet
color: [color-name]
---
```

**Patrón para SKILLS:**
```yaml
---
name: [skill-name]
description: "[When to use this skill, what tasks it handles, alternative phrasings/keywords]"
---
```

**Notas:**
- Los agentes usan `model:` y `color:` (visualización)
- Los skills NO incluyen `model:` o `color:`
- Las `description` son descriptivas de casos de uso, no solo definiciones
- Los nombres usan kebab-case: `marketing-copywriter`, `seo-strategist`, `html-implementer`

---

## 4. CONVENCIONES DE NOMBRES

### Agentes:
- `marketing-copywriter.md` — Copywriter técnico
- `seo-strategist.md` — Estratega SEO/GEO
- `html-implementer.md` — Generador HTML static
- `wp-implementer.md` — Implementador WordPress
- `seo-tecnico.md` — Auditor técnico de SEO

**Patrón:** `[rol-descriptivo].md` (kebab-case, descriptivo del rol)

### Skills:
- `copywriting/SKILL.md` — Metodología de copywriting
- `seo/SKILL.md` — Framework SEO & GEO
- `seo-tecnico/SKILL.md` — Framework técnico SEO

**Patrón:** `[ámbito]/SKILL.md` (nombrado siempre SKILL.md, dentro de carpeta temática)

### Sessions:
- `TEMPLATE.md` — Plantilla de sesión

**Patrón:** `TEMPLATE.md` (mayúsculas, singular)

---

## 5. REFERENCIAS EXTERNAS (URLs Y FUENTES)

### En `.claude/skills/seo/references/`:
- `topical-authority.md` — Koray Tugberk GUBUR's Topical Authority framework
- `semantic-seo.md` — Semantic SEO methodology
- `generative-engine-optimization.md` — GEO for AI-generated search
- `multilingual-seo.md` — SEO for multilingual content
- `topical-map-template.md` — Template para topical maps
- `geo-audit-pipeline.md` — Full pipeline para GEO audits

### URLs mencionadas en contenido:
- **WordPress:** `https://ghendigital.com/` (live site)
- **Platform stack:** WordPress + Astra Child + Gutenberg + Rank Math + Spectra
- **Tools & MCPs:**
  - `mcp__gsc__*` — Google Search Console MCP
  - `mcp__google-analytics__*` — GA4 MCP
  - `mcp__playwright__*` — Playwright MCP (for GEO citation testing)
  - WebSearch, WebFetch (built-in)

### Repositorios referenciadosmconados:
- `addyosmani/web-quality-skills` — Referencia para `seo-tecnico` skill

---

## 6. PATRONES Y CONVENCIONES DE FORMATO

### Markdown:
- **Headings:** `#` H1, `##` H2, `###` H3, `####` H4, ningún H5 o H6
- **Bold:** `**texto**` para énfasis
- **Code blocks:** ````language` para bloques ejecutables
- **Tables:** Markdown tables para datos estructurados
- **Lists:** `- ítem` para listas, `1.` para numeradas

### YAML Frontmatter:
```yaml
---
name: valor
description: "cadena multilínea permitida"
model: sonnet (solo en agents)
color: nombre-color (solo en agents)
---
```

### Estructura de secciones típica:
1. **Meta (frontmatter YAML)**
2. **Descripción ejecutiva / Propósito**
3. **Before [Task] / Preliminares**
4. **Core Content / Metodología / Workflow**
5. **Output Format / Deliverables**
6. **Tools / Recursos**
7. **What [Agent] Does NOT Do / Limitaciones**
8. **Rules / Normas**
9. **Related [Agents/Skills] / Links cruzados**

### Convención de rutas:
- `.claude/doc/{feature_name}/` — Carpeta por feature
- `.claude/doc/{feature_name}/seo-strategy.md` — Output de @seo-strategist
- `.claude/doc/{feature_name}/copy-deliverable.md` — Output de @marketing-copywriter
- `.claude/doc/{feature_name}/wp-implementation.md` — Output de @wp-implementer
- `.claude/doc/{feature_name}/html-implementation.md` — Output de @html-implementer
- `.claude/doc/{feature_name}/tech-seo-audit.md` — Output de @seo-tecnico
- `outputs/html/{feature}/index.html` — HTML generado final

---

## 7. CONEXIONES Y WORKFLOWS

### Flujo de contenido (Pipeline gh_seo):
```
@seo-strategist
    ↓ (produce: seo-strategy.md)
@marketing-copywriter
    ↓ (produce: copy-deliverable.md)
@wp-implementer OR @html-implementer
    ↓ (produce: wp-implementation.md O html-implementation.md)
@seo-tecnico (opcional, post-implementación)
    ↓ (produce: tech-seo-audit.md)
DONE
```

### Estado workflow (en session files):
```
backlog → strategy → copy → qa-review → implementation → tecnico-review → done
```

### Referencias cruzadas de agentes:
- `@seo-strategist` lee outputs de sesiones previas, produce strategy
- `@marketing-copywriter` lee strategy + sesión, produce copy
- `@wp-implementer` O `@html-implementer` leen copy + strategy + sesión, implementan
- `@seo-tecnico` audita post-implementación

---

## 8. CARACTERÍSTICAS DESTACADAS DEL REPOSITORIO

### Enfoque GEO (Generative Engine Optimization):
- Prioridad IGUAL a SEO tradicional
- EAV Architecture (Entity-Attribute-Value) para extracción AI
- Detección de AI Overviews (CTR < 0.5% + posición < 10 + avg time < 60s)
- Pipeline completo de detección → reescritura → testing

### Uso de MCPs (Model Context Protocol):
- GSC MCP para queries reales, clicks, posición, indexación
- GA4 MCP para sesiones, bounce, tiempo
- Playwright MCP para verificación de citación en ChatGPT/Perplexity/Claude

### Dos líneas editoriales paralelas:
- **Actualidad IA** (`/actualidad-ia/`) — 2-4 posts/week (news-driven)
- **Lab** (`/lab/`) — 1-2 posts/week (deep, technical projects)

### Output múltiple:
- WordPress implementation (via @wp-implementer)
- HTML static generation (via @html-implementer)
- Ambos con schema markup, SEO meta, responsive design

### Voz y posicionamiento:
- "Experto accesible" — técnico sin ser pedante, honesto sin ser arrogante
- Real production experience + verified projects (Archivo Final, Data Hub Google)
- No es evangelista IA, no es vendedor de cursos, no es blogger clickbait
- "Colega senior que ha peleado con los mismos problemas en producción"

---

## 9. LENGUAJE Y LOCALIZACIÓN

- **Idioma de contenido:** Spanish (Spain) — "tú", "España"
- **Idioma de código/variables:** English — nombres de archivos, variables, funciones
- **Términos técnicos:** Inglés estándar (LLM, prompt, RAG, MCP, token, inferencia), NO traducir forzadamente
- **Dirección:** "Gabriel" o "Gabi" (nunca formal)

---

## 10. ANÁLISIS COMPARATIVO: AGENTS vs SKILLS

| Aspecto | AGENTS | SKILLS |
|---------|--------|--------|
| **Ubicación** | `.claude/agents/` | `.claude/skills/{tema}/` |
| **Nombre de archivo** | `[rol].md` (varios) | `SKILL.md` (singular) |
| **YAML meta** | ✓ name, description, model, color | ✓ name, description (sin model/color) |
| **Público objetivo** | Gabriel u otros usuarios directo | Agentes (referencia interna) |
| **Propósito** | Define un rol/persona activo | Define metodología/framework |
| **Contenido** | Goal, Before Task, Workflow paso a paso, Tools, Rules | Before Starting, Core Principles, Methodologies, Examples, Related Skills |
| **Output** | Ejecutable, produce deliverables | Input para agents o usuarios |
| **Longitud típica** | 500-800 líneas | 300-500 líneas |
| **Interconexión** | "Related Agents" al final | "Related Skills" al final |

---

## 11. EJEMPLOS DE PATRONES DETECTADOS

### Patrón 1: Frontmatter + Descripción ejecutiva
```markdown
---
name: marketing-copywriter
description: "Technical copywriter for GHEN Digital..."
model: sonnet
color: magenta
---

You are the copywriter for **GHEN Digital** (ghendigital.com)...
```

### Patrón 2: Secciones "Before Any Task"
```markdown
## Before Any Task

1. **Read** the shared session file `.claude/sessions/{feature}.md`.
   - Read ALL sections — especially "Decisiones estratégicas" from `@seo-strategist`.
   - If Estado is not `copy`, check with Gabriel before proceeding.
2. **Read** the SEO brief `.claude/doc/{feature_name}/seo-strategy.md`...
3. **Read** `.claude/product-marketing-context.md`...
```

### Patrón 3: Tablas de capabilities/content types
```markdown
| Capability | Description |
|-----------|-------------|
| **GSC Audit** | Extraer queries, páginas, CTR... |
| **GA4 Analysis** | Extraer sesiones, bounce... |
...
```

### Patrón 4: Bash scripts para tools
```bash
# Comando estructurado con variables
tools/.venv/bin/python tools/qa_checker.py check --file \
    .claude/doc/{feature}/copy-deliverable.md \
    --keywords "kw1,kw2"
```

### Patrón 5: Listas de "What This Agent Does NOT Do"
```markdown
## What This Agent Does NOT Do

- Does not define SEO strategy (that's `@seo-strategist`)
- Does not implement WordPress changes (that's `@wp-implementer`)
- Does not design UI layouts or configure plugins
- Does not make business decisions...
```

---

## CONCLUSIONES Y RECOMENDACIONES

Este sistema `.claude/` es **altamente estructurado** y pensado para:
1. **Colaboración multi-agente** — workflow secuencial con handoffs claros
2. **Reproducibilidad** — metodología documentada, no improvisación
3. **Flexibilidad de output** — WordPress O HTML static (no ambos obligatorios)
4. **GEO-first** — prepara contenido para LLMs, no solo para Google
5. **Production-ready** — automación (schema, meta, validation) desde día 1

**Para tu proyecto LINEA DIRECTA**, podrías adaptar:
- La estructura de carpetas (agents, skills, sessions)
- El patrón de YAML frontmatter
- El flujo de estados (backlog → strategy → copy → implementation → done)
- Las metodologías de SEO/copywriting como referencia
- El uso de references/ para frameworks reutilizables
