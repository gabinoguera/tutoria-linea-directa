# 🤖 PROMPTS SECUENCIALES — Pipeline de Agentes Ingeniería

**Fecha:** 6 Abril 2026
**Input:** `BRIEF_LANDING_MOTO_ELECTRICA.md`
**Método:** Ejecutar de a uno. Cada agente genera un archivo de sesión que el siguiente lee.

---

## 🛠️ FASE 1: CREAR AGENTES (Min 20-30)

### PROMPT 0A: Crear @spec-writer

```
Crea el archivo `.github/agents/spec-writer.md` con la definición de un agente llamado spec-writer.

Rol: Convierte briefs de negocio en especificaciones técnicas y crea la GitHub Issue correspondiente.

Capacidades:
- Lee un brief en markdown y extrae objetivo, audiencia, diferenciadores y restricciones
- Genera una spec técnica con: user stories, acceptance criteria, componentes necesarios, restricciones tech
- Tech stack LD: Bootstrap 5, HTML5 semántico, sin frameworks adicionales para prototipos
- Al finalizar ejecuta: gh issue create --title "[título]" --body "[spec completa]" --label "feature"
- Guarda la spec en _SESSION_SPEC.md

Output format: spec técnica en markdown + confirmación de issue creada con número.
Próximo agente: @seo-technical
```

---

### PROMPT 0B: Crear @seo-technical

```
Crea el archivo `.github/agents/seo-technical.md` con la definición de un agente llamado seo-technical.

Rol: Enriquece specs técnicas con requisitos SEO y calidad web basados en los estándares de Addy Osmani.

Referencias:
- Web Quality Skills: https://github.com/addyosmani/web-quality-skills (skills: seo, core-web-vitals, accessibility, best-practices)
- Core Web Vitals targets: LCP <2.5s, CLS <0.1, FID <100ms
- Schema.org: FAQPage, LocalBusiness JSON-LD

Capacidades:
- Lee _SESSION_SPEC.md del agente anterior
- Define meta title (50-60 chars), meta description (150-160 chars)
- Especifica keyword primario, secundarios y LSI con densidad objetivo
- Define jerarquía de headings (H1 único, H2/H3 estructura)
- Especifica schema markup necesario (FAQPage, LocalBusiness)
- Define targets de performance (LCP, CLS) y accesibilidad (contraste >4.5:1)
- Guarda resultado en _SESSION_SEO_SPEC.md

Output format: sección SEO añadida a la spec, lista de requisitos técnicos con valores concretos.
Próximo agente: @developer
```

---

### PROMPT 0C: Crear @developer

```
Crea el archivo `.github/agents/developer.md` con la definición de un agente llamado developer.

Rol: Implementa la landing siguiendo metodología TDD — primero criterios, luego código.

Tech stack: HTML5 semántico, Bootstrap 5 CDN, CSS inline crítico, JavaScript mínimo.
Restricción: Archivo único landing.html, abre directamente en navegador sin build step.

Metodología TDD en 3 pasos:
PASO 1 — Escribe acceptance criteria antes de codificar:
  - Lista todos los criterios que el HTML debe cumplir (los "tests")
  - Basados en _SESSION_SPEC.md + _SESSION_SEO_SPEC.md
  - Guarda en _SESSION_ACCEPTANCE_CRITERIA.md

PASO 2 — Implementa HTML contra esos criterios:
  - Cada criterio de la lista debe poder marcarse como ✅ al terminar
  - HTML5 semántico (header, main, section, footer, article)
  - Bootstrap 5 grid, mobile-first
  - Schema.org JSON-LD según seo-spec
  - Form presupuesto funcional (HTML validation, no JS requerido)
  - Guarda en tools/outputs/html/landing.html

PASO 3 — Crea PR:
  - git add tools/outputs/html/landing.html _SESSION_*.md
  - git commit -m "feat: landing seguro moto eléctrica - TDD HTML"
  - gh pr create --title "feat: landing seguro moto eléctrica barato" --body con: criterios cumplidos, screenshot placeholder, link a issue

Output format: _SESSION_ACCEPTANCE_CRITERIA.md + landing.html + PR creada con número.
Próximo skill: @qa-reviewer
```

---

### PROMPT 0D: Crear @qa-reviewer

```
Crea el archivo `.github/skills/qa-reviewer.md` con la definición de un skill llamado qa-reviewer.

Rol: Revisa la PR contra la spec original y los criterios de aceptación. Posta un review comentado en GitHub.

Capacidades:
- Lee _SESSION_ACCEPTANCE_CRITERIA.md, _SESSION_SPEC.md, _SESSION_SEO_SPEC.md
- Lee el contenido de landing.html de la PR
- Valida punto por punto cada acceptance criterion: ✅ PASS / ❌ FAIL / ⚠️ WARNING
- Categorías de validación: SEO técnico, Core Web Vitals (estático), Schema markup, Accesibilidad, Funcionalidad form, Responsive
- Ejecuta: gh pr review [PR_NUMBER] --comment --body "[reporte completo]"
- Si hay FAILs críticos: gh pr review [PR_NUMBER] --request-changes

Criterios de bloqueo (request-changes):
- Meta title o description ausentes o fuera de rango de caracteres
- H1 ausente o múltiple
- Schema JSON-LD inválido o ausente
- Form sin campos obligatorios
- Contraste de color no verificable (<4.5:1 estimado)

Output format: comentario en PR con tabla de resultados por categoría + decisión APPROVE / REQUEST CHANGES.
```

---

## 🎬 FASE 2: EJECUTAR PIPELINE (Min 30-75)

---

## ✅ PROMPT 1: @spec-writer — Analiza el Brief

```
@spec-writer Lee el archivo BRIEF_LANDING_MOTO_ELECTRICA.md y genera la especificación técnica de la landing.

Incluye:
- Objetivo de negocio y métrica de éxito (conversion rate)
- 3 user stories (una por segmento de audiencia del brief)
- Acceptance criteria técnicos (mínimo 10 criterios concretos y verificables)
- Componentes necesarios: hero, diferenciadores, form presupuesto, FAQs, footer
- Restricciones técnicas: HTML5 + Bootstrap 5, archivo único, sin React

Al finalizar: crea la GitHub Issue con gh issue create y confirma el número de issue creada.
Guarda todo en _SESSION_SPEC.md
```

---

## ✅ PROMPT 2: @seo-technical — Enriquece la Spec

```
@seo-technical Lee _SESSION_SPEC.md y el brief original BRIEF_LANDING_MOTO_ELECTRICA.md.

Añade a la spec los requisitos SEO técnicos:

1. Meta tags:
   - Meta title (escríbelo ya, 50-60 chars, incluye keyword + marca)
   - Meta description (escríbela ya, 150-160 chars, incluye CTA)

2. Keywords:
   - Primario: "seguro moto eléctrica barato"
   - Secundarios: al menos 3 relacionados con intención comercial
   - Densidad objetivo: 1-2% keyword primario, mención natural secundarios

3. Estructura headings:
   - H1: escríbelo ya (único, keyword primario, magnético)
   - H2s propuestos para cada sección

4. Schema markup a implementar:
   - FAQPage JSON-LD (mínimo 3 preguntas con búsqueda real)
   - LocalBusiness con datos de Línea Directa

5. Core Web Vitals (restricciones para el developer):
   - No usar imágenes sin lazy loading
   - CSS crítico inline, resto diferido
   - Sin JavaScript bloqueante en <head>

6. Accesibilidad mínima:
   - Contraste texto/fondo: usar colores LD con ratio >4.5:1
   - Todos los inputs con label asociado
   - Alt text en imágenes

Guarda en _SESSION_SEO_SPEC.md
```

---

## ✅ PROMPT 3: @developer — TDD: Criterios + Implementación + PR

```
@developer Lee _SESSION_SPEC.md y _SESSION_SEO_SPEC.md.

PASO 1 — Escribe los acceptance criteria ANTES de codificar:
Lista todos los criterios que el HTML debe cumplir. Formato:
- [ ] Meta title presente, 50-60 chars
- [ ] Meta description presente, 150-160 chars
- [ ] H1 único con keyword primario
- [ ] Schema FAQPage JSON-LD presente y válido
- [ ] Form con campos: nombre, teléfono, modelo moto, submit
- [ ] Bootstrap grid, 2 columnas desktop / 1 columna mobile
- [ ] Sección diferenciadores LD (batería incluida, precio, asistencia 24h)
- [ ] CTA principal visible en above-the-fold
... (añade todos los que surjan de la spec)

Guarda en _SESSION_ACCEPTANCE_CRITERIA.md antes de escribir una línea de HTML.

PASO 2 — Implementa la landing:
- HTML5 semántico, Bootstrap 5 CDN, CSS inline crítico
- Archivo único: tools/outputs/html/landing.html
- Marca cada criterio como ✅ al implementarlo

PASO 3 — Crea la PR:
gh pr create \
  --title "feat: landing seguro moto eléctrica barato" \
  --body "Closes #[ISSUE_NUMBER]

## Criterios implementados
[lista de criterios con checkmarks]

## Archivos
- tools/outputs/html/landing.html
- _SESSION_SPEC.md
- _SESSION_SEO_SPEC.md
- _SESSION_ACCEPTANCE_CRITERIA.md"

Confirma el número de PR creada.
```

---

## ✅ PROMPT 4: @qa-reviewer — Revisa la PR

```
@qa-reviewer Revisa la PR recién creada.

Lee:
- _SESSION_ACCEPTANCE_CRITERIA.md (criterios definidos por el developer)
- _SESSION_SEO_SPEC.md (requisitos SEO técnicos)
- tools/outputs/html/landing.html (implementación)

Valida punto por punto cada acceptance criterion y cada requisito SEO.
Estructura el review en categorías: SEO técnico, Schema, Performance (estático), Accesibilidad, Funcionalidad, Responsive.

Ejecuta el review en GitHub:
gh pr review [PR_NUMBER] --comment --body "[tu reporte]"

Si todos los criterios críticos pasan: gh pr review [PR_NUMBER] --approve
Si hay fallos críticos: gh pr review [PR_NUMBER] --request-changes
```

---

## 🔧 EJECUCIÓN PASO A PASO

### FASE 1: CREAR AGENTES (Min 20-30)
1. **Min 20-22:** Ejecuta PROMPT 0A → crea `.github/agents/spec-writer.md` ✓
2. **Min 22-24:** Ejecuta PROMPT 0B → crea `.github/agents/seo-technical.md` ✓
3. **Min 24-27:** Ejecuta PROMPT 0C → crea `.github/agents/developer.md` ✓
4. **Min 27-30:** Ejecuta PROMPT 0D → crea `.github/skills/qa-reviewer.md` ✓

### FASE 2: EJECUTAR PIPELINE (Min 30-75)
5. **Min 30-35:** PROMPT 1 → `_SESSION_SPEC.md` + Issue #XX creada
6. **Min 35-42:** PROMPT 2 → `_SESSION_SEO_SPEC.md`
7. **Min 42-65:** PROMPT 3 → `_SESSION_ACCEPTANCE_CRITERIA.md` + `landing.html` + PR #YY creada
8. **Min 65-75:** PROMPT 4 → Review comentado en PR #YY

### FASE 3: DEMO (Min 75-85)
9. **Min 75-80:** Abrir `landing.html` en navegador
10. **Min 80-85:** Ver la PR y el review en GitHub
11. **Min 85-90:** Q&A + próximos pasos

### Salidas esperadas
```
_SESSION_SPEC.md                    (1-2 KB)
_SESSION_SEO_SPEC.md                (1-2 KB)
_SESSION_ACCEPTANCE_CRITERIA.md     (1 KB)
tools/outputs/html/landing.html     (5-8 KB)
GitHub Issue #XX                    (spec completa)
GitHub PR #YY                       (feat: landing)
GitHub PR Review                    (QA report)
```

---

## 📚 REFERENCIAS

- **Web Quality Skills (Addy Osmani):** https://github.com/addyosmani/web-quality-skills
- **Core Web Vitals:** https://web.dev/vitals/
- **Schema.org:** https://schema.org/
- **GitHub CLI:** https://cli.github.com/
- **GitHub Copilot Agents:** https://code.visualstudio.com/docs/copilot/agents/overview
- **Línea Directa:** https://www.lineadirecta.com

---

**Última actualización:** 6 Abril 2026
**Framework:** GitHub Copilot Agents + TDD + Web Quality Skills (Addy Osmani)
