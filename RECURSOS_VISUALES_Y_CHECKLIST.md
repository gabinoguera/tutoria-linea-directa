# 📊 RECURSOS VISUALES Y CHECKLIST - WORKSHOP LÍNEA DIRECTA

---

## 🎨 DIAGRAMA 1: Conceptos Clave (para mostrar en slides/pizarra)

```
┌─────────────────────────────────────────────────────────────────┐
│                    ECOSISTEMA DEL PIPELINE                      │
└─────────────────────────────────────────────────────────────────┘

                          ┌──────────┐
                          │ CLAUDE   │ ← Orquestador central
                          │ (General)│ ← Lee CLAUDE.md
                          └────┬─────┘
                               │
           ┌───────────────────┼───────────────────┐
           │                   │                   │
           ▼                   ▼                   ▼
    ┌─────────────┐   ┌──────────────┐   ┌─────────────────┐
    │  AGENTES    │   │    SKILLS    │   │      MCPs       │
    │  (Roles)    │   │(Librerías)   │   │(Herr. Externas)│
    ├─────────────┤   ├──────────────┤   ├─────────────────┤
    │@seo-strat   │   │ /seo         │   │ GSC (keywords)  │
    │@copywriter  │   │ /copywriting │   │ GA4 (comporta ) │
    │@qa-reviewer │   │ /seo-tecnico │   │ GitHub (refs)   │
    │@html-impl   │   │              │   │ Playwright      │
    │@seo-tecnico │   │              │   │ DrawIO          │
    └─────────────┘   └──────────────┘   └─────────────────┘
           │                   │                   │
           └───────────────────┴───────────────────┘
                        │
                        ▼
              ┌────────────────────┐
              │  SESIÓN COMPARTIDA │ ← .md = "base de datos"
              │  (moto-electr.md)  │ ← Todos leen/escriben aquí
              └────────────────────┘
                        │
                        ▼
                   ┌─────────┐
                   │ OUTPUT  │
                   │ HTML    │
                   │ SCHEMA  │
                   └─────────┘
```

---

## 🎨 DIAGRAMA 2: Flujo de una sesión (Timeline visual)

```
TIEMPO    │                    SESIÓN: moto-electrica-barata.md
          │
T+0min    │  Crear sesión desde TEMPLATE
          │  ├─ Título: "Seguro Moto Eléctrica Barata"
          │  ├─ Keyword: "seguro moto eléctrica barato"
          │  └─ Estado: workflow-started
          │
          ▼
T+5min    │  ESTRATEGIA: @seo-strategist lanza
          │  ├─ Lee CLAUDE.md (contexto LD)
          │  ├─ Consulta MCPs: GSC, GA4, Playwright
          │  ├─ Genera: content brief, topical map, FAQs
          │  └─ Escribe en sesión: ## SEO Brief
          │
          ▼
T+10min   │  CONTENIDO: @marketing-copywriter lanza
          │  ├─ Lee sesión (brief anterior)
          │  ├─ Escribe: H1, H2s, intro, paragraphs, CTA
          │  ├─ Sienta: Tonalidad LD, keywords naturally placed
          │  └─ Append: ## Content Draft
          │
          ▼
T+15min   │  QA REVIEW: qa_checker.py ejecuta
          │  ├─ Valida: LSI keywords, estructura H tags
          │  ├─ Chequea: links density, intención usuario
          │  ├─ Genera: informe de mejoras
          │  └─ Append: ## QA Review
          │
          ▼
T+20min   │  IMPLEMENTACIÓN: @html-implementer lanza
          │  ├─ Lee content + schema recos
          │  ├─ Genera: HTML boilerplate + schema FAQPage
          │  ├─ Embebe: OG tags, structured data
          │  └─ Output: tools/outputs/html/moto-electrica.html
          │
          ▼
T+25min   │  AUDITORÍA: @seo-tecnico revisa
          │  ├─ Analiza HTML: Core Web Vitals, schema validation
          │  ├─ Lighthouse score simulado: 92
          │  ├─ A11y check: formularios accesibles
          │  └─ Append: ## SEO Technical Audit
          │
          ▼
T+30min   │  READY TO PUBLISH ✓
          │  HTML file: moto-electrica.html
          │  Session file: COMPLETO con toda la trazabilidad
          │
```

---

## 🎨 DIAGRAMA 3: Estructura de Decision (WordPress vs HTML)

```
                    ┌──────────────────┐
                    │ QA Review PASSED │
                    └────────┬─────────┘
                             │
                ┌────────────┴────────────┐
                │ "¿Dónde publicamos?"    │
                └────┬───────────────┬───┘
                     │               │
         ┌───────────▼──┐     ┌─────▼──────────┐
         │  WordPress?  │     │  HTML Local?   │
         │   (saltamos) │     │  (USAMOS ESTO) │
         └──────────────┘     └────────┬──────┘
                                       │
                          ┌────────────▼─────────────┐
                          │ @html-implementer         │
                          ├───────────────────────────┤
                          │ ✓ Genera index.html       │
                          │ ✓ Embebe schema (FAQPage) │
                          │ ✓ OG tags para social     │
                          │ ✓ Copy-paste ready        │
                          └─────────────┬─────────────┘
                                        │
                          ┌─────────────▼──────────────┐
                          │ tools/outputs/html/        │
                          │ moto-electrica.html        │
                          └────────────────────────────┘
```

---

## 🎨 DIAGRAMA 4: Diferencia: Sin MCPs vs Con MCPs

```
SIN MCPs:
┌─────────────────────────────────────────────────────────────┐
│ Agente: "Voy a escribir sobre seguro moto eléctrica barato" │
│ Suposición: Probablemente hay 500-1000 búsquedas/mes        │
│ Output: Genérico, sin anclaje en datos reales               │
└─────────────────────────────────────────────────────────────┘

CON MCPs:
┌─────────────────────────────────────────────────────────────┐
│ Agente: Consulto MCPs...                                     │
│ GSC MCP: "REAL: 340 búsquedas/mes exactas"                   │
│ GA4 MCP: "REAL: 3.2% conversion rate en landing de moto"     │
│ Playwright MCP: "REAL: Competidores en posición 1-3"         │
│                                                              │
│ Decisión informada:                                          │
│ "H2 muy claro sobre PRECIO porque GSC mostró intención"      │
│ "Cliente muy listo: 3.2% conversion, luego ROI alto"         │
│ "Diferenciadores vs competencia: X, Y, Z (verificados)"      │
│                                                              │
│ Output: Específico, data-driven, ROI predecible              │
└─────────────────────────────────────────────────────────────┘
```

---

## ✅ CHECKLIST PRE-WORKSHOP (Día antes)

### Preparación Técnica (Instructor)

- [ ] **VS Code instalado** en máquina de demostración
- [ ] **Python 3.11+** verificado (`python3 --version`)
- [ ] **Repo clonado** en local (en máquina del instructor)
- [ ] **Dependencias instaladas** (`cd tools && ./setup.sh`)
- [ ] **.env configurado** con datos ficticios (sin exponer secrets)
- [ ] **.mcp.json visible** pero explicado que es simulado
- [ ] **CLAUDE.md lleno** con datos Línea Directa
- [ ] **Primera sesión preparada** (`moto-electrica-barata.md`)
- [ ] **Terminal lista** para live demo
- [ ] **Conexión a internet** verificada (para fetch de repos/docs)

### Preparación Material

- [ ] **Guión impreso** o en segundo monitor
- [ ] **Diagramas impresos** o en slides (diagrams 1-4 arriba)
- [ ] **Laptop para CADA ASISTENTE** (idealmente)
- [ ] **USB con repo pre-clonado** (backup si WiFi falla)
- [ ] **Link GitHub del repo** en chat/email previo

### Equipos Asistentes

- [ ] **Acceso a VS Code** instalado
- [ ] **Python 3.11+** (si no, instrucciones pre-clase)
- [ ] **Git instalado** (para clonar)
- [ ] **Acceso a terminal / CLI**
- [ ] **Editor de código favorito** (VS Code ideal)

### Ambiente Classroom

- [ ] **Proyector/Screen** funciona
- [ ] **WiFi testado** (WiFi firme para descargas)
- [ ] **Slack/Teams** abierto para Q&A en directo
- [ ] **Reloj visible** para timing
- [ ] **Agua/snacks** disponibles

---

## 💬 TALKING POINTS por Segmento (notas rápidas para instructor)

### Intro (5 min)
- **Punto Clave:** "Antes, 1 artículo SEO = 3-5 horas. Con pipeline = 25 minutos, 10x mejor calidad"
- **Conectar:** "Línea Directa ya tiene 3.7M clientes. Imagina 3.7M clicks de contenido SEO nuevo."

### Agentes (12 min)
- **Metáfora:** "Si tu equipo fuera un órgano, los agentes son células especializadas. Cerebro = Claude, oído = SEO strategist, mano = HTML implementer."
- **Pausar aquí:** "¿Preguntas sobre agentes?" (5 sec for hands)

### Skills (dentro de Agentes)
- **Clave:** "Skills = libros de referencia que los agentes **leen automáticamente**. Holistic SEO = framework SEO destilado. Web Quality = guía de performance."
- **Referencia:** "Koray y Addy Osmani = expertos, pero ahora viven en tu repo. El agente accede en 0.1 segundos."

### MCPs (dentro de Agentes)
- **Analogía:** "Los MCPs son como botón 'press to consult Google'. Agente puede preguntar en tiempo real."
- **Dato:** "Sin MCPs, tasa de acierto = 70%. Con MCPs, tasa de acierto = 95%+."
- **En LD:** "No tenemos GSC/GA4 reales. Pero mostraremos cómo el agente **actuaría** si lo tuviera. En Fase 2, conectamos OAuth real."

### Setup (23 min total)
- **Go slow:** "Primera instalación siempre tiene pequeños bumps. Normal. Levanta la mano si algo no funciona."
- **Command by command:** No hagas dry-run completo. Escribe lentamente, explica cada línea.
- **Checkpoint:** Después de cada fase, pide "levanten mano si llegaron aquí ✓"

### Demo (15 min)
- **Drama:** "Ahora voy a invocar el agente. Veremos cómo EN VIVO genera una estrategia SEO real para Línea Directa."
- **Durante:** Silencio en aula (el agente debe "pensar"). Espera 2-3 minutos sin interrupciones.
- **Post-demo:** "Esto QUE VEN = 25 minutos de trabajo manual, hecho por IA."

### Q&A (10 min)
- **Esperadas:** 
  - "¿Cuánto cuesta la IA?" → Depende si es Claude Code ($20/month) o Copilot ($10/month)
  - "¿Esto reemplaza mi equipo?" → **NO**. Reemplaza tareas repetitivas, libera equipo para estrategia y decisiones.
  - "¿Garantiza rankings?" → NO. Garantiza calidad + velocidad. Rankings dependen de autoridad, backlinks, UX.

### Close (7 min)
- **Energía:** "Vamos a hacer esto 10 veces. Probamos, iteramos, mejoramos. Es un MVP."
- **Siguiente fase:** "Próxima sesión: Copywriter genera el artículo full. Semana siguiente: Publicamos."

---

## 📞 Contacts & Links para compartir post-workshop

```markdown
### Repositorios Clave

1. **mkt-ghen-workshop** (el que usamos)
   https://github.com/gabinoguera/mkt-ghen-workshop
   
2. **Holistic SEO** (Koray / E-Online)
   https://github.com/e-onsoftware/holistic-seo
   (Archivo: .claude/skills/seo/references/)
   
3. **Web Quality Skills** (Addy Osmani)
   https://github.com/addyosmani/web-quality-skills
   (Archivo: .claude/skills/seo-tecnico/references/)

### Documentación que Leer Después

- README.md del repo (3 min read)
- CLAUDE.md adaptado a tu proyecto (5 min read)
- WORKSHOP.md (alternativa pedagogical guide)

### Contactos para Soporte

**Instructor:** [Tu nombre/email/Slack]
**Repo maintainer:** gabi.noguera [at] e-online.es
**Community:** [Link Slack/Discord del workshop]

### Próximos Pasos (después del workshop)

- [ ] Cada uno clona el repo en su máquina
- [ ] Intenta hacer 1 sesión solo (30 min máximo)
- [ ] Anota qué falló o qué fue confuso
- [ ] Sesión grupal siguiente: Martes 13 Abril (confirmar)
```

---

## 🎯 TIPS para Facilitar el Workshop Smooth

### Gestión del Tiempo
- **Usa timer visible** (mostrar en pantalla): "Quedan 5 min en este segmento"
- **Cut scope si necesario:** Si el setup lleva 15 min extra, salta Q&A general, hazlo 1-on-1 despues
- **Demo pre-grabado backup:** Si la demo live falla, ten un video de 2 min del output esperado

### Inclusividad Técnica
- **No asumar nivel Python:** Muestra comandos, explica qué hace cada uno
- **Pair programming:** Si alguien se queda atrás, empareja con alguien rápido
- **"Hands on" vs "watch":** Decide si todos escriben o solo miran. Recomendación: solo el instructor escribe, asistentes leen README después

### Gestión de Expectativas
- **Antes de seguir a Setup:** "Este es Fase 1 de 5. Hoy hacemos setup + primer brief. No vamos a publicar HTML hoy."
- **Sobre errors:** "Si git clone falla, es Internet. Si Python falla, es dependency. Ninguno es culpa tuya."
- **Sobre calidad AI:** "El contenido que genera es 70-80% ready. El 20% final es únice de tu editor SEO."

### Preguntas Que Pueden Surgir (canned responses)

**P: ¿Esto funciona en Mac/Linux/Windows?**  
R: Sí, Python es cross-platform. El único gotcha es el path. En Mac/Linux usas `/` y en Windows `\`. Aquí mostramos Max, pero el proceso es idéntico.

**P: ¿Necesitamos OpenAI o solo Claude?**  
R: Solo Claude (a través de Claude Code o GitHub Copilot). Los agentes corren EN Claude. No es code que escribimos; es prompts que diseñamos.

**P: ¿Si la IA genera algo malo, quién es responsable legalmente?**  
R: Buen pregunta. La IA es draft. Tú (editor) eres responsable del output final. Por eso hay QA phase.

**P: ¿Cuánto tarda todo el pipeline completo?**  
R: De idea a HTML publicado: ~25-30 minutos. De HTML a ranking en Google: esto es variable (weeks a months, depende autoridad del site).

---

## 📋 Script de Cierre (último 5 min)

```
"Hemos hecho mucho en 90 minutos:

✅ Entendieron qué son agentes, skills, MCPs
✅ Clonaron un repo real de producción
✅ Configuraron variables de entorno
✅ Instalaron dependencias Python
✅ Crearon Línea Directa CLAUDE.md
✅ Ejecutaron primer agente en vivo
✅ Vieron cómo fluye información entre roles

Eso que ven EN ESE OUTPUT = 25 horas de trabajo manual.

Ahora, es vuestro turno. Llévense el repo, intenten una sesión 
ustedes solos. Van a fallar en algo. Cuando fallen, van a aprender.

Siguiente paso: Juntamos el lunes para copywriting + QA.

¿Preguntas antes de irte?"

[Espera 60 seg]

"Gracias a todos. Slack abierto para dudas. ¡Nos vemos el lunes!"
```

---

**Última actualización:** 6 Abril 2026  
**Preparado para:** Workshop Línea Directa (90 min)

