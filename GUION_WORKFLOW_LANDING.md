# 🚀 Guion Workflow: Landing Page con Agentes GitHub Copilot

**Fecha:** 6 Abril 2026  
**Objetivo:** Generar landing page completa desde ticket de marketing hasta deploy  
**Duración:** 45-60 minutos  
**Herramientas:** GitHub Copilot Agents + MCPs + GitHub CLI

---

## 📋 PASO 1: Recibir Ticket de Marketing

### Input Inicial
- **Ticket de Marketing**: "Crear landing para 'Seguros Moto Eléctrica 2026'"
- **Brief básico**: Keyword target, público objetivo, CTAs principales
- **Deadline**: 2 horas para primera versión

### Acción Inicial
```bash
# Crear issue en GitHub como documentación viva
gh issue create \
  --title "LANDING: Seguros Moto Eléctrica 2026" \
  --body "Brief: $(cat BRIEF_LANDING_MOTO_ELECTRICA.md)" \
  --label "marketing,landing,urgent"
```

---

## 📋 PASO 2: Crear Spec y Issue en GitHub

### Spec Inicial (Template)
```markdown
## 🎯 Spec: Landing Moto Eléctrica

### Keyword Target
- Primary: "seguros moto eléctrica"
- Secondary: "seguro scooter eléctrico", "seguros moto 2026"

### Público Objetivo
- Edad: 25-45 años
- Perfil: Urbanita, tech-savvy, preocupado por sostenibilidad

### Requisitos Técnicos
- HTML5 + Bootstrap 5
- Schema.org JSON-LD
- Core Web Vitals optimizado
- Mobile-first responsive

### CTAs
- "Cotizar seguro" (primary)
- "Comparar precios" (secondary)
- "Llamar ahora" (tertiary)
```

### Issue como Documentación Viva
- **Issue #X**: Contiene spec inicial
- **Asignar labels**: `marketing`, `landing`, `urgent`
- **Mencionar stakeholders**: @marketing-team, @dev-team

---

## 📋 PASO 3: Agente SEO Completa la Issue

### Invocar Agente SEO
```bash
# En GitHub Copilot Chat
@seo-strategist analizar keyword "seguros moto eléctrica" y completar issue #X
```

### Conocimiento SEO que Añade
- **Topical Map**: Pillar content + cluster keywords
- **Search Intent**: Informational → Commercial → Transactional
- **Competencia**: Análisis de SERP (AXA, MAPFRE, etc.)
- **Datos MCP**: Volúmenes de búsqueda reales, CTR, competencia

### Resultado en Issue
```markdown
## SEO Analysis by @seo-strategist

### Topical Authority Map
- **Pillar**: Seguros moto eléctrica España
  - Cluster 1: Precios seguros moto 2026
  - Cluster 2: Coberturas scooter eléctrico
  - Cluster 3: Comparador seguros moto

### Search Data (MCP GSC)
- Volume: 2,400 búsquedas/mes
- Competition: Medium
- CTR potencial: 3.2%

### FAQ Schema Candidates
- ¿Cuánto cuesta seguro moto eléctrica?
- ¿Qué cubre seguro scooter?
- ¿Dónde contratar seguro moto 2026?
```

---

## 📋 PASO 4: Agente Developer Implementa (TDD)

### Crear Branch y Empezar TDD
```bash
# Crear branch para desarrollo
gh issue develop X --checkout

# Agente developer inicia TDD
@html-implementer implementar landing siguiendo spec de issue #X
```

### Ciclo TDD del Agente
1. **RED**: Escribir test fallido (ej: "debe mostrar CTA principal")
2. **GREEN**: Implementar HTML mínimo que pase test
3. **REFACTOR**: Optimizar código manteniendo funcionalidad

### Implementación Técnica
- **HTML5 semántico** con Bootstrap 5
- **Schema.org** inline (FAQPage, LocalBusiness)
- **Core Web Vitals** optimizado (LCP <2.5s, CLS <0.1)
- **Datos MCP**: Precios reales de LD, cobertura geográfica

### Crear PR
```bash
# Commit y push
git add tools/outputs/html/landing-moto-electrica.html
git commit -m "feat: landing moto eléctrica completa con TDD

- HTML5 + Bootstrap responsive
- Schema.org FAQ y LocalBusiness
- Core Web Vitals optimizado
- Tests passing: 12/12

Closes #X"

# Crear PR
gh pr create --fill --draft
```

---

## 📋 PASO 5: Agente QA Revisa la PR

### Invocar Agente QA
```bash
# En GitHub Copilot Chat
@qa-checker revisar PR #Y para landing moto eléctrica
```

### Checklist QA (25 puntos)
- ✅ **Funcional**: CTAs funcionan, forms válidos
- ✅ **SEO**: Meta tags, schema markup, alt texts
- ✅ **Performance**: Core Web Vitals < thresholds
- ✅ **Accesibilidad**: WCAG AA compliance
- ✅ **Mobile**: Responsive en todos breakpoints
- ✅ **Código**: HTML válido, Bootstrap correcto

### Comentarios en PR
```markdown
## QA Review by @qa-checker ✅ APPROVED

### Passed (23/25)
- ✅ HTML válido
- ✅ Schema.org correcto
- ✅ Mobile responsive
- ✅ Core Web Vitals: LCP 1.8s, CLS 0.05

### Minor Issues (2/25)
- ⚠️ Missing alt text en imagen hero
- ⚠️ Color contrast en botón secondary

### Recommendation: READY FOR MERGE
All critical issues resolved. Minor accessibility fixes can be addressed in follow-up.
```

---

## 📋 PASO 6: Ver Landing en Browser

### Merge y Deploy
```bash
# Merge PR si QA aprueba
gh pr merge Y --merge

# Ver resultado final
open tools/outputs/html/landing-moto-electrica.html
```

### Resultado Final
- **Landing visible** en navegador local
- **Funcional completa**: CTAs, forms, schema markup
- **Optimizada**: SEO + performance + accesibilidad
- **Documentada**: Issue completa con análisis SEO
- **Probada**: TDD + QA checklist

---

## 🔄 Workflow Completo Visual

```
Ticket Marketing
       ↓
   Crear Issue (#X)
       ↓
@seo-strategist → Completar con análisis SEO + MCP data
       ↓
@html-implementer → Implementar con TDD → Crear PR (#Y)
       ↓
@qa-checker → Revisar PR → Aprobar/merge
       ↓
   Landing en Browser ✅
```

---

## 📊 Métricas de Éxito

### Tiempo
- **Total**: 45-60 min desde ticket hasta landing
- **SEO Analysis**: 10 min
- **Development**: 25 min (TDD)
- **QA Review**: 10 min

### Calidad
- **SEO Score**: Topical authority coverage >80%
- **Performance**: Core Web Vitals all green
- **Accesibilidad**: WCAG AA compliant
- **Código**: HTML válido, tests passing

### Automatización
- **MCP Usage**: Datos reales de GSC, Analytics, precios LD
- **GitHub Integration**: Issues, PRs, branches automáticos
- **Documentation**: Todo trazado en GitHub

---

## 🎯 Próximos Pasos (Post-Workshop)

### Escalabilidad
- **Múltiples landings**: Pipeline paralelo para 10+ keywords
- **Auto-deploy**: GitHub Actions para deploy automático
- **Analytics**: Tracking de conversiones post-deploy
- **Iteración**: A/B testing basado en datos MCP

### Integración MCP
- **GSC**: Volúmenes reales, competencia SERP
- **Google Analytics**: Perfiles usuario, comportamiento
- **LD APIs**: Precios dinámicos, cobertura geográfica
- **Browser MCP**: Testing cross-browser automático

---

**Fin del Guion**

Este workflow demuestra cómo agentes especializados + MCPs + GitHub pueden convertir un ticket de marketing en una landing optimizada en menos de 1 hora, con trazabilidad completa y calidad garantizada.