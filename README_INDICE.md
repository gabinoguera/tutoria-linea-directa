# 📑 ÍNDICE DE DOCUMENTACIÓN v2 - WORKSHOP LÍNEA DIRECTA

**Fecha:** 6 Abril 2026 (ACTUALIZADO)  
**Evento:** Workshop: Pipeline Multi-Agente SEO para Línea Directa  
**Duración:** 90 minutos  
**Enfoque:** Resumido, actionable, divisido por roles

---

## 🎯 CAMBIOS PRINCIPALES (v2)

✅ **NO clonar repo del workshop** → Crearemos uno propio (tutoria-linea-directa)  
✅ **Guión reducido a 90 min** → Max 3 páginas, sin WordPress  
✅ **Separación por roles:** Marketing + Development  
✅ **Pre-setup .env + Python** → No perder tiempo en clase  
✅ **Agentes desde cero** → No templates, solo estructura  

---

## 📚 DOCUMENTOS CREADOS (5 TOTAL)

### 1️⃣ **GUION_RESUMIDO_90MIN.md** ← 👈 EMPIEZA AQUÍ
**Tamaño:** 3 páginas (condensado)  
**Enfoque:** Timeline clara, sin fluff

**Qué contiene:**
- ⏱️ Timeline 90 min (10 módulos, máximo 10 líneas cada uno)
- 🧠 Conceptos 3 agentes sin WordPress
- 💻 Setup .env + Python (PRE-HECHO)
- 🚀 Demo en vivo @seo-strategist
- 🔗 Flujo agentes mediante sesiones .md
- 📚 Q&A rápido + recursos

**👉 USAR CUANDO:** Facilitar workshop, guía del instructor (leer en clase)

---

### 2️⃣ **BRIEF_LANDING_MOTO_ELECTRICA.md** ← 📄 PARA MARKETING
**Tamaño:** 8 páginas  
**Audiencia:** Marketing Team  

**Qué contiene:**
- 👥 Audiencia segmentada (3 personas tipo)
- 📊 Keyword research (primary + secondary + LSI)
- 🏆 Diferenciadores LD vs competencia
- 📄 Estructura landing (H1 → H6)
- 🔐 Copy prompts para agente copywriter
- 📏 Especificaciones técnicas (SEO basics)
- 📈 Objetivos post-lanzamiento (métricas)
- ✅ Checklist antes de copywriting

**👉 USAR CUANDO:** Marketing define qué landing crear + pasa a agente 2

---

### 3️⃣ **SPECS_SEO_BASE.md** ← 🔍 PARA DESARROLLO
**Tamaño:** 10 páginas  
**Audiencia:** Dev Team + @html-implementer  

**Qué contiene:**
- 📌 Especificación rápida (tabla)
- 🎯 Keywords target (primary + secondary + LSI)
- 📝 Estructura HTML requerida (meta, og, schema)
- 🔐 Checklist SEO técnico (15+ items)
- 🎨 Contenido requerido (estructura completa)
- 📊 Content metrics (word count, H tags, etc)
- 🔗 Internal linking map
- 📋 Validación pre-publicación
- 🚀 Deployment checklist

**👉 USAR CUANDO:** Dev implementa HTML + schema + validación Lighthouse

---

### 4️⃣ **SETUP_ENV_PYTHON.md** ← ⚙️ CONFIGURACIÓN LOCAL
**Tamaño:** 5 páginas  
**Propósito:** PRE-SETUP (ejecutar antes del workshop)

**Qué contiene:**
- 📋 .env completo para LD (valores reales)
- 🐍 Python venv + requirements.txt
- 📦 Instalación dependencias (pip)
- 📝 Creación qa_checker.py básico
- 🚫 .gitignore correcto
- ✅ Checklist setup completo
- 🆘 Troubleshooting común

**👉 USAR CUANDO:** Setup inicial (antes del 6 de Abril, no durante clase)

---

### 5️⃣ **GITHUB_SETUP.md** ← 🐙 GIT + GITHUB
**Tamaño:** 5 páginas  
**Propósito:** Setup repo tutoria-linea-directa

**Qué contiene:**
- 🔑 Git config (usuario + email)
- 📦 Init repo local + conectar GitHub
- 📝 README.md base
- 📥 Git add/commit/push inicial
- 🚀 Verificación en GitHub
- 🔄 Workflow git (commits futuros)
- 💾 .gitignore (qué NO subir)
- 📋 Checklist GitHub setup

**👉 USAR CUANDO:** Después de SETUP_ENV_PYTHON, antes de crear agentes

---

---

## 📖 FLUJO RECOMENDADO POR ROL

### 👨‍💼 INSTRUCTOR / PRODUCT MANAGER

1. **Día anterior (Setup):**
   - Lee: GUION_RESUMIDO_90MIN.md (3 min)
   - Ejecuta: SETUP_ENV_PYTHON.md (10 min) + GITHUB_SETUP.md (10 min)
   - Verifica todo está listo en repo

2. **Día clase (90 min):**
   - Sigue GUION_RESUMIDO_90MIN.md línea por línea
   - Muestra outputs en pantalla
   - Maneja Q&A con brief de agentes

### 📊 MARKETING TEAM

1. **Pre-workshop:**
   - Lee: BRIEF_LANDING_MOTO_ELECTRICA.md (15 min)
   - Aprueba diferenciadores + tonalidad

2. **Post-workshop:**
   - Recibe agente @marketing-copywriter output
   - Valida contexto brief vs artículo generado

### 💻 DEV TEAM

1. **Pre-workshop:**
   - Lee: SPECS_SEO_BASE.md (20 min)
   - Entiende keywords, schema, checklists

2. **Post-workshop:**
   - Recibe agente @html-implementer output
   - Valida HTML, Lighthouse, schema
   - Deploy a producción

---

## 🎯 CÓMO USAR ESTOS DOCUMENTOS

### 📅 TIMELINE DE USO

| Fase | Documento | Acción |
|---|---|---|
| **PRE-SETUP** | SETUP_ENV_PYTHON.md | Ejecutar setup (una sola vez) |
| **PRE-GITHUB** | GITHUB_SETUP.md | Config repo tutoria-linea-directa |
| **PRE-CLASE** | GUION_RESUMIDO_90MIN.md | Leer overview (instructor) |
| **DURANTE CLASE** | GUION_RESUMIDO_90MIN.md | Facilitar workshop |
| **MARKETING PREP** | BRIEF_LANDING_MOTO_ELECTRICA.md | Definir landing |
| **DEV PREP** | SPECS_SEO_BASE.md | Especificaciones técnicas |

---

## 🎯 FLUJO RECOMENDADO PARA EL INSTRUCTOR

### Preparación (Día anterior)

1. **Lee:** [GUION_WORKSHOP_COMPLETO.md](GUION_WORKSHOP_COMPLETO.md) → Entender todo el flujo
2. **Consulta:** [RECURSOS_VISUALES_Y_CHECKLIST.md](RECURSOS_VISUALES_Y_CHECKLIST.md) → Checklist de preparación
3. **Setup técnico:** Sigue [COMANDOS_COPYPASTE_PARA_DEMO.md](COMANDOS_COPYPASTE_PARA_DEMO.md) fases 1-3 TÚ MISMO
   - Clonas el repo
   - Instalas Python deps
   - Creas CLAUDE.md con datos LD
   - Preparas primera sesión

### Día del Workshop

1. **Previa (15 min antes):** Verifica checklist (RECURSOS_VISUALES)
2. **Intro (0-5 min):** Abre [GUION_WORKSHOP_COMPLETO.md](GUION_WORKSHOP_COMPLETO.md#módulo-1-intro--problem-statement-5-min) - Módulo 1
3. **Conceptos (5-17 min):** Sigue [GUION_WORKSHOP_COMPLETO.md](GUION_WORKSHOP_COMPLETO.md#módulo-2-conceptos-clave-12-min) Módulo 2, muestra diagramas de RECURSOS_VISUALES
4. **Setup (25-48 min):** Ejecuta [COMANDOS_COPYPASTE_PARA_DEMO.md](COMANDOS_COPYPASTE_PARA_DEMO.md) FASE 1, 2, 3
5. **Demo (58-73 min):** Sigue [COMANDOS_COPYPASTE_PARA_DEMO.md](COMANDOS_COPYPASTE_PARA_DEMO.md) FASE 3 (Prompt @seo-strategist)
6. **MCPs + Flujo (73-83 min):** Consulta [GUION_WORKSHOP_COMPLETO.md](GUION_WORKSHOP_COMPLETO.md#módulo-9-qa--mcps-simulados--flujo-agentes-10-min) Módulo 9
7. **Cierre (83-90 min):** Lee script de [RECURSOS_VISUALES_Y_CHECKLIST.md](RECURSOS_VISUALES_Y_CHECKLIST.md#-script-de-cierre-último-5-min)

---

## 📖 LECTURA RÁPIDA (Si tienes 5 min)

### Para entender QUÉ es el pipeline
→ Lee [GUION_WORKSHOP_COMPLETO.md](GUION_WORKSHOP_COMPLETO.md#módulo-2-conceptos-clave-12-min), Módulo 2

### Para ver diagramas visuales
→ Abre [RECURSOS_VISUALES_Y_CHECKLIST.md](RECURSOS_VISUALES_Y_CHECKLIST.md#-diagrama-1-conceptos-clave-para-mostrar-en-slidespizarra), Diagramas 1-4

### Para entender setup técnico completo
→ Consulta [COMANDOS_COPYPASTE_PARA_DEMO.md](COMANDOS_COPYPASTE_PARA_DEMO.md#-fase-1-setup-25-min), FASE 1 completa

### Para ver cómo invocas el agente
→ Ve a [COMANDOS_COPYPASTE_PARA_DEMO.md](COMANDOS_COPYPASTE_PARA_DEMO.md#-fase-3-primera-invocación-del-agente-58-min---73-min--15-min), FASE 3

### Para ejemplo de OUTPUT esperado
→ Ver [COMANDOS_COPYPASTE_PARA_DEMO.md](COMANDOS_COPYPASTE_PARA_DEMO.md#step-32-cuando-el-agente-tenga-output), Step 3.2 (25 KB de ejemplo real)

---

## 🎓 REFERENCIAS INTRA-DOCUMENTOS

### Dentro de GUION_WORKSHOP_COMPLETO.md
- Secciones anclas: Cada módulo tiene `### MÓDULO X:`
- Ejemplos: CLAUDE.md template, sesión template, prompt del agente
- Diagramas: ASCII art embebido

### Dentro de RECURSOS_VISUALES_Y_CHECKLIST.md
- 4 Diagramas completos (ecosistema, timeline, decisión, MCPs)
- 97 items del checklist
- 20+ talking points
- 5 preguntas esperadas + respuestas

### Dentro de COMANDOS_COPYPASTE_PARA_DEMO.md
- 31 comandos numerados (Comando 1 - Comando 31)
- Output esperado para cada comando
- Explicación de contexto
- Troubleshooting para cada fase

---

## 🚨 ERRORES COMUNES + SOLUCIONES

### "No sé por dónde empezar"
→ Abre **GUION_WORKSHOP_COMPLETO.md** primero. Lee línea 1 a 100.

### "Necesito los diagramas en visual"
→ **RECURSOS_VISUALES_Y_CHECKLIST.md** tiene 4 diagramas ASCII listos para mostrar en pantalla

### "¿Qué comando ejecuto ahora?"
→ Abre **COMANDOS_COPYPASTE_PARA_DEMO.md**, busca "Comando X" (donde X = número)

### "¿Qué timing tengo en cada módulo?"
→ **GUION_WORKSHOP_COMPLETO.md** tiene tabla cronograma línea 25-30

### "¿Qué digo cuando alguien pregunta por MCPs?"
→ **RECURSOS_VISUALES_Y_CHECKLIST.md**, sección Talking Points, busca "MCP"

### "Se me olvidó cómo terminar la clase"
→ **RECURSOS_VISUALES_Y_CHECKLIST.md**, sección "Script de Cierre"

---

## 🎬 CASE STUDY DENTRO DEL WORKSHOP

**Tema:** Seguro Moto Eléctrica Barata  
**Vertical:** Moto (LD especialista eléctricos)  
**Keyword:** "seguro moto eléctrica barato 2026"  
**Intent:** Commercial (buyer ready)  
**Volumen:** 340 búsquedas/mes (estimado Google Keyword Planner)  
**Competencia:** AXA, Allianz, MAPFRE = BAJA (oportunidad)

**Salida esperada del agente:**
- Content Brief (H1, H2s structure)
- Topical Map
- 10-15 FAQs (schema FAQPage)
- Diferenciadores vs competencia
- Recomendaciones para copywriter

**Ejemplo output:** Ver [COMANDOS_COPYPASTE_PARA_DEMO.md](COMANDOS_COPYPASTE_PARA_DEMO.md#step-32-cuando-el-agente-tenga-output), Step 3.2

---

## 🔗 ENLACES EXTERNOS MENCIONADOS

1. **Repo principal (lo que usamos)**
   https://github.com/gabinoguera/mkt-ghen-workshop

2. **Holistic SEO (Koray/E-Online)**
   https://github.com/e-onsoftware/holistic-seo
   Ubicación en repo: `.claude/skills/seo/references/`

3. **Web Quality Skills (Addy Osmani - MIT)**
   https://github.com/addyosmani/web-quality-skills
   Ubicación en repo: `.claude/skills/seo-tecnico/references/`

4. **Sitio de Línea Directa (caso real)**
   https://coches.lineadirecta.com/linea-directa-mejor-precio-garantizado/

---

## 📋 CHECKLIST DE ANTES DE EMPEZAR

**Instructor:**
- [ ] Leíste GUION_WORKSHOP_COMPLETO.md (al menos Módulo 1-3)
- [ ] Practicaste los comandos de FASE 1-3 tú mismo (setup)
- [ ] Creaste CLAUDE.md con datos LD ficticios
- [ ] Preparaste la sesión `moto-electrica-barata.md`
- [ ] Tienes RECURSOS_VISUALES_Y_CHECKLIST abierto en segundo monitor
- [ ] Verificaste Python 3.11+ en tu máquina

**Asistentes (pre-clase):**
- [ ] Bajaron VS Code
- [ ] Tienen Python 3.11+ instalado (o instrucciones)
- [ ] Acceso a terminal/CLI
- [ ] Bajaron el repo o tienen USB copy

**Ambiente:**
- [ ] Proyector funciona
- [ ] WiFi probado
- [ ] Slack/Teams para Q&A en vivo

---

## 💾 BACKUPS & DISTRIBUCIÓN

**Para compartir con asistentes:**
```
Envía por mail/Slack:
1. GUION_WORKSHOP_COMPLETO.md (lectura previa opcional)
2. COMANDOS_COPYPASTE_PARA_DEMO.md (para que sigan en vivo)
3. RECURSOS_VISUALES_Y_CHECKLIST.md (referencia post-clase)
4. Link GitHub: https://github.com/gabinoguera/mkt-ghen-workshop
```

**Backup USB (si WiFi falla):**
```
Copia en USB:
- Repo clonado (carpeta completa: 50 MB)
- Los 3 documentos .md
- Python installer para macOS (si necesario)
```

---

## 🎓 Próximos Workshops (Roadmap)

| Fecha | Tema | Agente Principal |
|---|---|---|
| 6 Abril | **HOY** - Setup + @seo-strategist | SEO Strategy |
| 13 Abril | Copywriting + QA | @marketing-copywriter |
| 15 Abril | Implementación + Auditoría | @html-implementer |
| 20-24 Abril | Repetir x 2 capitales más | Todos agentes |

---

## 🆘 SOPORTE POST-WORKSHOP

**Si algo falla después:**
1. Consulta [COMANDOS_COPYPASTE_PARA_DEMO.md](COMANDOS_COPYPASTE_PARA_DEMO.md#-comandos-rápidos-de-referencia), sección "Comandos rápidos"
2. Abre [RECURSOS_VISUALES_Y_CHECKLIST.md](RECURSOS_VISUALES_Y_CHECKLIST.md#-tips-para-facilitar-el-workshop-smooth), sección Gestión de Errores
3. Lee README.md del repo (https://github.com/gabinoguera/mkt-ghen-workshop)

---

## ✅ ESTADO DEL DOCUMENTO

**Fecha creación:** 6 Abril 2026  
**Status:** Listo para usar  
**Validado:** Sí (workflow completo probado)  
**Versión:** 1.0  

---

**¡Que disfrutes el workshop! 🚀**

