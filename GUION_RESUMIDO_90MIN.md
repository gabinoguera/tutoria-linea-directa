# ⚡ GUIÓN RESUMIDO: Pipeline Agentes SEO (90 min)

**Fecha:** 6 Abril 2026 | **Asistentes:** Equipo Marketing + Tech LD  
**Objetivo:** De cero a primer agente funcionando generando estrategia SEO

---

## 📍 TIMELINE (90 min total)

| Min | Módulo | Qué | 
|---|---|---|
| 0-10 | Intro | Problem statement + conceptos 3 agentes |
| 10-20 | Setup | .env + Python venv (PRE-CONFIGURADO) |
| 20-35 | Agentes | Explicar @seo-strategist, @copywriter, @html-impl |
| 35-65 | Demo Vivo | Invocar @seo-strategist y generar brief |
| 65-80 | Flujo | Cómo se comunican agentes vía sesiones .md |
| 80-90 | Q&A | Preguntas + recursos + próximos pasos |

---

## 🎯 INTRO (0-10 MIN)

### El Reto
- LD tiene 3.7M clientes, miles de keywords sin atacar
- Contenido SEO manual = 3-5 horas X artículo
- **Solución:** Sistema de agentes IA basado en prompts + contexto

### Lo que haremos HOY
1. Entender 3 agentes clave
2. Ejecutar agente 1 ([`@seo-strategist`]) que genere un brief de landing
3. Ver cómo se comunican agentes vía archivos compartidos

### Resultado esperado
- Brief SEO + topical map + keywords recomendadas para landing "Seguro Moto Eléctrica Barata"
- 25 min de trabajo manual = 3 min con agentes

---

## 🧠 CONCEPTOS (10-20 MIN)

### 3 Agentes en el Pipeline

```
AGENTE 1: @seo-strategist
└─ INPUT: Keyword + contexto (CLAUDE.md)
└─ OUTPUT: Brief SEO, topical map, FAQs, keywords
└─ TAREA: Análisis competencia, estructura contenido

AGENTE 2: @marketing-copywriter  
└─ INPUT: Brief anterior + archivo de sesión
└─ OUTPUT: Artículo full, landings, copy optimizado
└─ TAREA: Redactar siguiendo estructura + keywords

AGENTE 3: @html-implementer
└─ INPUT: Contenido validado
└─ OUTPUT: HTML + schema FAQPage + OG tags
└─ TAREA: Generar archivo .html listo para subir
```

### Conexión entre Agentes: SESIONES

```
📄 archivo-sesion.md = "base de datos" compartida

@seo-strategist ESCRIBE:
  ## SEO Brief
  [brief generado]

@marketing-copywriter LEE lo anterior, ESCRIBE:
  ## Content Draft
  [contenido generado]

@html-implementer LEE lo anterior, ESCRIBE:
  ## HTML Output
  [archivo html]

✅ Todo es versionable + auditable
```

### MCPs: Los "Oráculos" de Datos
- GSC: "¿Cuántas búsquedas tiene esta keyword?"
- GA4: "¿Qué % de usuarios convierten?"
- Playwright: "¿Qué dice la competencia en su H1?"

**En esta clase:** Simulamos MCPs (sin acceso real a Google)

---

## 💻 SETUP (20-35 MIN)

### Paso 1: Verificar .env (PRE-LISTO)

```bash
cd ~/Documents/BrainCode/LINEA\ DIRECTA
cat .env

# Debe mostrar (editado ya):
# COMPANY_NAME=Línea Directa
# COMPANY_DOMAIN=lineadirecta.com
# COMPANY_VERTICAL=seguros-vehiculo
```

### Paso 2: Activar Python venv (PRE-LISTO)

```bash
cd tools
source .venv/bin/activate

# Verificar
python3 -c "import requests; print('✓ Python OK')"

deactivate
```

### Paso 3: Verificar estructura

```bash
cd ..
ls -la

# Debe mostrar:
# .claude/          ← Agentes + skills
# tools/            ← Scripts Python
# .env              ← Variables config
# .mcp.json         ← MCPs config
```

---

## 🚀 AGENTES EN DETALLE (35-65 MIN)

### Agente 1: @seo-strategist (DEMO EN VIVO)

**Rol:** SEO Manager que analiza competencia y propone estrategia

**INPUT:** 
- Keyword: "seguro moto eléctrica barato"
- Vertical: Moto eléctrica
- Contexto: CLAUDE.md (datos LD)

**PROMPT que ejecutaremos:**

```
@seo-strategist

Analiza la keyword "seguro moto eléctrica barato 2026".

Tu tarea:
1. Simular datos de GSC: ¿Cuántas búsquedas/mes? ¿CTR típica? ¿Intent?
2. Simular Playwright: ¿Qué dice la competencia (AXA, Allianz, MAPFRE)?
3. Generar:
   - Content Brief (H1, H2s propuestos)
   - Topical Map (clusters semánticos)
   - FAQs (10-15 preguntas clave)
   - Keywords LSI (palabras relacionadas)
   - Diferenciadores LD vs competencia

Tone: Directo, claro, orientado a seguros. No jerga técnica.
```

**OUTPUT esperado:** (3-5 min de ejecución)
- H1: "Seguro Moto Eléctrica Barato: Coberturas Completas desde 12€/mes | Línea Directa"
- Estructura H2s, FAQs, keywords de cola larga
- Gap competitivo: "Nadie menciona BARATO en H1 explícito"

---

### Agente 2: @marketing-copywriter (EXPLICACIÓN)

**INPUT:** Output del agente 1 (brief anterior)

**TAREA:** 
- Escribir H1, intro, 5-7 secciones con copy SEO
- Expandir FAQs 
- Incluir CTAs ("Calcula tu presupuesto", "Cambiarme a LD")
- Keyword placement natural

**OUTPUT:** Markdown listo para HTML

---

### Agente 3: @html-implementer (EXPLICACIÓN)

**INPUT:** Contenido validado

**TAREA:**
- Convertir markdown a HTML+CSS boilerplate
- Embeber schema FAQPage
- OG tags (social preview)
- Accesibilidad básica

**OUTPUT:** `moto-electrica.html` en `tools/outputs/html/`

---

## 🔗 FLUJO AGENTES (65-80 MIN)

```
SESIÓN: moto-electrica.md (compartida por todos)

T+0min:   @seo-strategist genera BRIEF
          └─ Append a sesión: ## SEO Brief

T+3min:   Revisamos output + tomamos decisión

T+5min:   @marketing-copywriter genera CONTENT
          └─ Lee brief, escribe artículo
          └─ Append: ## Content Draft

T+10min:  qa_checker.py valida
          └─ Keywords LSI, estructura, densidad
          └─ Append: ## QA Report

T+15min:  @html-implementer genera HTML
          └─ Embed schema, OG tags
          └─ Output: tools/outputs/html/

✅ TODO EN 25 MIN (manual = 3-5 horas)
```

---

## 📌 CREAR AGENTES DESDE CERO

**En el repo crearemos:**

```
.claude/agents/
├── seo-strategist/
│   ├── .instructions.md       ← Prompts llenos de instrucciones
│   └── references/            ← Documentos de contexto
├── marketing-copywriter/
│   ├── .instructions.md
│   └── references/
└── html-implementer/
    ├── .instructions.md
    └── references/
```

**NO copiamos del otro workshop.** Creamos desde cero con CLAUDE.md como fundación.

---

## 📂 ESTRUCTURA DEL REPO FINAL

```
tutoria-linea-directa/
├── .claude/
│   ├── agents/                ← Los 3 agentes custom LD
│   ├── skills/                ← Skills invocables (/seo, /copywriting)
│   ├── sessions/              ← Sesiones activas del proyecto
│   └── doc/                   ← Documentos referencia
├── tools/
│   ├── .venv/                 ← Python virtualenv (PRE-LISTO)
│   ├── outputs/html/          ← HTML files generados
│   └── *.py                   ← Scripts (qa, generator, etc.)
├── content-briefs/            ← Outputs de agentes (guardar aquí)
├── landings/                  ← HTMLs finales
├── .env                       ← Config (PRE-LISTO)
├── .mcp.json                  ← MCPs config
├── CLAUDE.md                  ← DNA del proyecto
├── README.md                  ← Documentación repo
└── GUION_RESUMIDO_90MIN.md    ← Este archivo
```

---

## ❓ PREGUNTAS ESPERADAS

**P: ¿PDF sin acceso real a GSC/GA4?**  
R: Exacto. El agente "simula" datos realistas. En Fase 2, conectaremos OAuth real.

**P: ¿Esto reemplaza al equipo marketing?**  
R: No. Reemplaza lo tedioso (análisis competencia, H1/H2 estructuras). El equipo elige estrategia.

**P: ¿Garantiza rankings?**  
R: No. Garantiza calidad 7/10 (vs 4/10 manual). Rankings dependen de autoridad + backlinks.

**P: ¿En qué monitor ejecutei Claude?**  
R: GitHub Copilot Chat (en VS Code) O Claude Code (IDE web) O ChatGPT con archivos.

---

## 📚 RECURSOS POST-WORKSHOP

1. **Brief de Landing:** `BRIEF_LANDING_MOTO_ELECTRICA.md` (en repo)
2. **Specs SEO:** `SPECS_SEO_BASE.md` (en repo)
3. **Repo GitHub:** https://github.com/gabinoguera/tutoria-linea-directa

---

## 🎬 PRÓXIMOS WORKSHOPS

- **Lunes:** Agente 2 (copywriting) + validación
- **Miércoles:** Agente 3 (HTML) + deploy producción
- **Semana siguiente:** Repetir x 2 verticales más (coche, hogar)

---

**¡Empecemos! Abrimos Claude Code / GitHub Copilot Chat y ejecutamos el agente.** 🚀

