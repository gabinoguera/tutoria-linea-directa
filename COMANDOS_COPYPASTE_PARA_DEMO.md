# 🖥️ COMANDOS COPY-PASTE PARA LIVE DEMO - WORKSHOP LÍNEA DIRECTA

## 📋 Introdución
Este archivo contiene todos los comandos que vas a ejecutar en el workshop. 
Cópialo tal cual, línea por línea. Explica cada uno mientras lo escribes.

---

## **FASE 1: Setup (25 min)**

### Step 1.1: Abrir Terminal e ir a workspace

```bash
# Comando 1
cd ~/Documents/BrainCode/LINEA\ DIRECTA

# Comando 2
pwd

# ✓ Output esperado: /Users/simba/Documents/BrainCode/LINEA DIRECTA
```

**Explanation:** Nos movemos a la carpeta donde vamos a trabajar. `pwd` muestra dónde estamos.

---

### Step 1.2: Clonar el repositorio

```bash
# Comando 3
git clone https://github.com/gabinoguera/mkt-ghen-workshop.git .

# ✓ Output esperado:
# Cloning into '.'...
# remote: Enumerating objects: 450, done.
# ...
# Receiving objects: 100% (450/450), done.
# Resolving deltas: 100% (320/320), done.
```

**Explanation:** Descargamos todo el repo. El `.` al final significa "clona AQUÍ, no en subcarpeta". Toma ~10-15 seg si Internet es buena.

**Si falla:** "GitHub down o WiFi lenta. Backup: ya tengo en USB. Copia esta carpeta."

---

### Step 1.3: Ver estructura

```bash
# Comando 4
ls -la

# ✓ Output esperado:
# total 224
# drwxr-xr-x  17 simba  staff   544 Apr  6 14:32 .
# drwxr-xr-x   5 simba  staff   160 Apr  6 14:15 ..
# drwxr-xr-x   3 simba  staff    96 Apr  6 14:25 .claude
# drwxr-xr-x   3 simba  staff    96 Apr  6 14:25 tools
# drwxr-xr-x   2 simba  staff    64 Apr  6 14:25 competitive-analysis
# drwxr-xr-x   2 simba  staff    64 Apr  6 14:25 content-briefs
# drwxr-xr-x   2 simba  staff    64 Apr  6 14:25 site-audit
# drwxr-xr-x   2 simba  staff    64 Apr  6 14:25 topical-maps
# -rw-r--r--   1 simba  staff  2105 Apr  6 14:25 .env.example
# -rw-r--r--   1 simba  staff  1450 Apr  6 14:25 .mcp.json
# -rw-r--r--   1 simba  staff 15850 Apr  6 14:25 CLAUDE.md
# -rw-r--r--   1 simba  staff 12340 Apr  6 14:25 README.md
```

**Explanation:** Aquí ves todas las carpetas que necesitamos. `.claude/` contiene agentes y skills. `tools/` contiene scripts Python.

---

### Step 1.4: Limpiar y preparar carpetas

```bash
# Comando 5
rm -rf .git

# Comando 6
mkdir -p tools/outputs/html

# Comando 7
mkdir -p .claude/sessions

# Comando 8
ls -R tools/  # Verifica estructura

# ✓ Output:
# tools/:
# __pycache__
# outputs (vacío o con algo previo)
# .venv (lo crearemos después)
# [lista de *.py files]
```

**Explanation:** Removemos git (es template). Creamos carpetas de outputs donde irán los HTMLs finales. Las sesiones irán aquí también.

---

### Step 1.5: Copiar .env desde template

```bash
# Comando 9
cp .env.example .env

# Comando 10
cat .env | head -20  # Ver primeras líneas

# ✓ Output:
# WP_URL=
# WP_USERNAME=
# WP_PASSWORD=
# WP_XML_RPC_URL=
# GEMINI_API_KEY=
# COMPANY_NAME=
```

**Explanation:** `.env` es donde guardamos credenciales (nunca en git). Por ahora está vacío. En producción, llenarías con keys reales.

---

### Step 1.6: Editar .env para Línea Directa

```bash
# Comando 11
# ABRE EN VS CODE
code .env
```

**En VS Code, escribe DENTRO del archivo:**

```dotenv
# Remove/comment out WordPress vars (saltamos WordPress)
# WP_URL=
# WP_USERNAME=
# WP_PASSWORD=

# Gemini (optional para imágenes)
# GEMINI_API_KEY=

# Línea Directa config
COMPANY_NAME=Línea Directa Aseguradora
COMPANY_DOMAIN=lineadirecta.com
COMPANY_COUNTRY=es
COMPANY_MARKET=seguros-vehiculo
```

**Explanation:** Configuramos para que los scripts Python sepan con qué empresa estamos trabajando.

**Salva el archivo:** Ctrl+S (macOS: Cmd+S)

---

### Step 1.7: Verificar Python

```bash
# Comando 12
python3 --version

# ✓ Output esperado:
# Python 3.11.8

# Si es < 3.11, instrucciones:
# En Mac: brew install python@3.11
# En Linux: sudo apt install python3.11
# En Windows: Descarga de python.org
```

**Explanation:** Python debe ser 3.11+. Scripts usan f-strings y features recientes.

---

### Step 1.8: Setup Python venv y dependencies

```bash
# Comando 13
cd tools

# Comando 14
ls  # Verifica que ves *.py files

# ✓ Output: 
# __pycache__
# qa_checker.py
# wp_publisher.py
# local_generator.py
# serp_analyzer.py
# image_generator.py
# setup.sh
# requirements.txt
```

**Explanation:** Entramos en carpeta tools. Aquí viven los scripts Python.

---

### Step 1.9: Ejecutar setup.sh

```bash
# Comando 15
chmod +x setup.sh  # Hace executable

# Comando 16
./setup.sh

# ✓ Este paso TOMA TIEMPO (~30-60 seg). Output:
# Creating virtual environment in .venv/
# Installing Python dependencies...
# Successfully installed requests-2.31.1 python-dotenv-1.0.0 Pillow-10.0.0 ...
# Setup complete! Virtual environment ready at ./.venv/bin/activate
```

**En caso de error:**
- "pip: command not found" → `python3 -m pip --version`
- "permission denied" → `sudo chmod 755 setup.sh && ./setup.sh`

---

### Step 1.10: Activar venv y verificar

```bash
# Comando 17
source .venv/bin/activate

# ✓ Tu prompt debe cambiar a:
# (.venv) simba@mac tools %

# Comando 18
python3 -c "import requests; import dotenv; print('✓ Dependencies OK')"

# ✓ Output:
# ✓ Dependencies OK

# Comando 19
deactivate  # Salir del venv (temporal)

# ✓ Prompt vuelve a normal:
# simba@mac tools %
```

**Explanation:** Virtual environment aísla las dependencies de tu sistema. Activamos para verificar todo OK.

**Fin de FASE 1 (Setup).** [Checkpoint: ~25 min han pasado. "¿Todos llegaron aquí? ✓"]

---

## **FASE 2: Configuración de Proyecto (41 min - 48 min = 7 min)**

### Step 2.1: Volver a raíz y editar CLAUDE.md

```bash
# Comando 20
cd ..  # Volvemos a /Users/simba/Documents/BrainCode/LINEA\ DIRECTA

# Comando 21
code CLAUDE.md
```

**En VS Code, reemplaza los placeholders:**

```markdown
# [Tu estructura anterior de CLAUDE.md]
# PERO sólo muestra estos campos CLAVE:

## Datos de la Empresa

**Nombre:** Línea Directa Aseguradora  
**URL:** https://coches.lineadirecta.com  
**Verticales:** Coche, Moto Eléctrica, Hogar  
**Diferenciador:** "Te mejoramos el precio, directamente"  
**Núcleo:** Seguros low-cost + coberturas completas  

## Pillar Topics

- **Coche:** Seguro coche barato, comparar, cambiarme
- **Moto:** Moto eléctrica, asistencia 24h
- **Hogar:** Ocupación ilegal (NEW 2026)

## Palabras Clave Estratégicas

- "seguro coche barato" | 1,200/mes | Commercial High
- "moto eléctrica seguro" | 340/mes | Commercial
- "ocupación ilegal hogar" | 220/mes | Commercial + Info

## Audiencias

### Audiencia 1: "Comparador Sensible al Precio"
- Edad: 25-40
- Busca: "seguro coche barato 2026"
- CTA: "Calcula tu presupuesto en 2 min"

### Audiencia 2: "Propietario Eléctrico"
- Edad: 35-50
- Busca: "seguro coche eléctrico cobertura"
- CTA: "Líderes en eléctricos"

### Audiencia 3: "Joven Conductor"
- Edad: 18-25
- Busca: "seguro moto joven barato"
- CTA: "Asistencia nocturna INCLUIDA"

## Diferenciadores vs Competencia

| Aspecto | LD | Allianz | AXA |
|---|---|---|---|
| Precio desde | 12€ | 18€ | 15€ |
| Transparencia | "Garantizado" | ❌ | ❌ |
| Asistencia 24h | ✅ | ❌ | ✅ |

## Referencias

- Holistic SEO (repo Koray): topical authority, semantic maps
- Web Quality Skills (Addy Osmani): CWV, accesibilidad, performance
```

**Salva:** Cmd+S

---

### Step 2.2: Crear primera sesión

```bash
# Comando 22
code .claude/sessions/TEMPLATE.md  # Para ver qué hay

# Comando 23
cp .claude/sessions/TEMPLATE.md .claude/sessions/moto-electrica-barata.md

# Comando 24
code .claude/sessions/moto-electrica-barata.md
```

**En VS Code, escribe:**

```markdown
# Sesión: Seguro Moto Eléctrica Barata

## Título
Seguro Moto Eléctrica Barata: Coberturas Completas desde 12€/mes

## Contexto Inicial
- **Keyword:** seguro moto eléctrica barato 2026
- **Vertical:** Moto Eléctrica
- **Intent:** Commercial (buyer ready)
- **Audiencia:** Propietarios motos eléctricas, 25-45 años, tech-savvy
- **Volumen (KW Planner estimado):** 340 búsquedas/mes
- **Competencia SERP:** Baja (oportunidad)

## Estado Workflow
strategy  → copywriting → qa-review → implementation → tecnico-review → done

## Estado Actual
strategy (esperando @seo-strategist)

## Salida @seo-strategist
[El agente rellenará esto]

## Salida @marketing-copywriter
[Pendiente]

## Salida QA Checker
[Pendiente]

## HTML Output
[Pendiente]

## Auditoría Técnica
[Pendiente]
```

**Salva:** Cmd+S

---

### Step 2.3: Verificar .mcp.json

```bash
# Comando 25
cat .mcp.json | head -30

# ✓ Output (primeras líneas):
# {
#   "mcpServers": {
#     "google-search-console": {
#       "command": "npx",
#       "args": ["@modelcontextprotocol/server-google-search-console"],
#       "env": {
#         "GSC_OAUTH_CLIENT_SECRETS_FILE": "./client_secrets.json"
#       }
#     },
#     "google-analytics-4": {
#       ...
```

**Explanation:** MCPs ya están configurados en template. En producción, llenarías con OAuth keys reales.

**Fin de FASE 2 (Configuración).** [Checkpoint: 48 min. "¿OK env + CLAUDE.md + sesión?"]

---

## **FASE 3: Primera Invocación del Agente (58 min - 73 min = 15 min)**

### Step 3.1: Abre Claude Code (o editor conectado a IA)

```bash
# Comando 26
# ABRE A PARTE: Claude Code, GitHub Copilot Chat, o similar
# NO en terminal. Es editor de IA.

# Contexto: En Claude Code, pega esto en el chat:
```

**PROMPT EXACTO a pegar en Claude Code / Copilot:**

```
@seo-strategist

Lee el archivo `.claude/sessions/moto-electrica-barata.md` 
y el archivo `CLAUDE.md` (contexto de Línea Directa).

Tu tarea:
1. Analizar la keyword "seguro moto eléctrica barato" 
2. Simular consultas a MCPs:
   - GSC: Qué datos VERÍAs si tuvieras acceso (340 búsquedas/mes, CTR típica 5-8%)
   - GA4: Comportamiento usuario esperado (conversion rate ~3-4%)
   - Playwright: Top 3 competidores en SERP
3. Generar:
   - Content Brief con H1, H2s, keyword placement
   - Topical Map
   - 10-15 FAQs para schema
   - Diferenciadores LD vs competencia
4. Guardar TODO en la sesión (como si fuese una persona escribiendo)

Usa tonalidad Línea Directa: directa, clara, sin jerga.

Formato esperado:

## SEO Brief: "Seguro Moto Eléctrica Barata"

### 📊 Analysis SERP (simulado de GSC + Playwright)
- Top 3 competidores actuales
- Gap: qué NO cubren en "barato"

### 🗺️ Topical Map
(struktur léxico-semántica)

### 📄 Content Outline (estructura)
- H1: 
- H2 Level 1: 
- H2 Level 2:
- ...

### ❓ FAQPage Schema (10-15 Qs)
```json
{ ... }
```

### 💚 Diferenciadores LD
### 🎯 Recomendaciones Copywriter
```

**Explanation:** Este prompt le dice al agente EXACTAMENTE qué hacer. El agente va a:
- Leer archivos del workspace
- Simular MCPs (sin tener acceso real)
- Generar estructura SEO
- Pensar como si fuera SEO strategist de LD

**ESPERA:** El agente tardará 2-3 minutos en procesar. Silencio absoluto en aula. Déjalo hacer.

---

### Step 3.2: Cuando el agente tenga OUTPUT...

**El output debe parecer así (EJEMPLO):**

```markdown
## SEO Brief: "Seguro Moto Eléctrica Barata"

### 📊 Analysis SERP (simulado de GSC + Playwright)

**Consulta MCP (simulada):**
- GSC data would show: 340 búsquedas/mes ("seguro moto eléctrica barato")
- CTR media SERP: 7.2%
- Top 3 posiciones sin cubrir "barato" explícitamente → **OPORTUNIDAD**

**Top 3 competidores (Playwright simulado):**
1. **AXA Seguros** - "Moto Eléctrica: Líderes en Protección"
   - Palabras: "seguro", "moto", "eléctrica", pero NO menciona "barato"
   - H1: demasiado genérico
2. **Allianz** - "Seguro Moto Líderes en Innovación"
   - Fuerte enfoque en features técnicas (batería, carga)
   - NO habla de precio
3. **MAPFRE** - "Protege tu Moto Eléctrica desde..."
   - Menciona precio pero "desde 18€", no ataca keyword "barato"

**GAP IDENTIFICADO:** Nadie dice explícitamente "barato" en H1/H2. Línea Directa puede ser primero.

---

### 🗺️ Topical Map

```
Seguro Moto Eléctrica Barato (Core)
│
├─ [Cluster 1] Coberturas Específicas
│  ├─ Daño a batería
│  ├─ Robo sistema eléctrico
│  └─ Carga pública (infraestructura)
│
├─ [Cluster 2] Modelos de Motos (Context)
│  ├─ Freno regenerativo (impact price)
│  ├─ Autonomía en KM (usage pattern)
│  └─ Potencia en Watios (insurance factor)
│
└─ [Cluster 3] Factores Precio
   ├─ Edad conductor (young = caro)
   ├─ Zona geográfica (urban = less expensive)
   └─ Historial siniestros (risk factor)
```

---

### 📄 Content Outline

**H1:** "Seguro Moto Eléctrica Barato: Coberturas Completas desde 12€/mes | Línea Directa"
- Keyword density: 2 menciones naturales
- Marque benefit: "coberturas completas" (differentiation)

**H2-1:** "¿Por qué contratar un seguro de moto eléctrica?"
- Subheaders (H3s):
  - "Riesgos únicos de motos eléctricas"
  - "Qué cobertura NO te protege"
  - CTA soft: "Descubre nuestras coberturas"

**H2-2:** "Mejores seguros de moto eléctrica baratos en 2026"
- Subheaders (H3s):
  - "Coberturas que necesitas (batería, carga, robo)"
  - "Línea Directa vs AXA vs MAPFRE: comparativa"
  - CTA: "Calcula tu presupuesto en 2 min"

**H2-3:** "¿Cuánto cuesta un seguro de moto eléctrica?"
- Subheaders (H3s):
  - "Factores que afectan el precio"
  - "Calculadora: simula tu presupuesto"

**H2-4:** "FAQs - Seguro Moto Eléctrica"
- Schema: FAQPage con 12 Qs (ver abajo)

---

### ❓ FAQPage Schema (10-15 Qs)

```json
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {
      "@type": "Question",
      "@id": "q1",
      "name": "¿Cuál es el precio de un seguro de moto eléctrica?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "En Línea Directa, desde 12€/mes. El precio varía según age, power (W), location. Calcula gratis en nuestra web."
      }
    },
    {
      "@type": "Question",
      "@id": "q2",
      "name": "¿Cubre roturas de batería?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Sí, nuestra cobertura de 'Daño Técnico Completo' incluye batería, motor, cargador y sistema eléctrico."
      }
    },
    {
      "@type": "Question",
      "@id": "q3",
      "name": "¿Protege contra robo del sistema eléctrico?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Sí. Nuestro seguro cubre robo de motor eléctrico, batería y accesorios (cargador, sensor)."
      }
    },
    {
      "@type": "Question",
      "@id": "q4",
      "name": "¿Tiene asistencia 24h incluida?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Sí, siempre. Asistencia en viaje, grúa, reparación en carretera. Disponible 24/7 sin coste adicional."
      }
    },
    {
      "@type": "Question",
      "@id": "q5",
      "name": "¿Qué edad mínima para asegurarse?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "18 años. Conductores jóvenes: asistencia nocturna INCLUIDA."
      }
    },
    {
      "@type": "Question",
      "@id": "q6",
      "name": "¿Cubre daños por falta de carga (batería agotada en viaje)?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Nuestra cobertura de 'Asistencia por Falta de Carga' te transporta a punto de recarga más cercano."
      }
    },
    {
      "@type": "Question",
      "@id": "q7",
      "name": "¿Qué documentos necesito para contratar?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "DNI, permiso de conducir, documentación moto (matrícula). Proceso 100% online, <2 min."
      }
    },
    {
      "@type": "Question",
      "@id": "q8",
      "name": "¿Cómo cambiarme de aseguradora a Línea Directa?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Nosotros nos encargamos. Puedes solicitar cambio sin penalización. Te mejoramos el precio hasta fin de tu póliza actual."
      }
    },
    {
      "@type": "Question",
      "@id": "q9",
      "name": "¿Hay descuentos para conductores nuevos o first-time eléctrico?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Sí. Descuento 'First Eléctrico' 15%. Descuento 'Conductor Joven' 10%. Acumulables."
      }
    },
    {
      "@type": "Question",
      "@id": "q10",
      "name": "¿Puedo cambiar coberturas después de contratar?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Sí, flexible. Cualquier momento, sin penalización. Puedes añadir/quitar coberturas."
      }
    }
  ]
}
```

---

### 💚 Diferenciadores Línea Directa

| Aspecto | Línea Directa | Allianz | AXA | MAPFRE |
|---|---|---|---|---|
| **Precio desde** | 12€ | 18€ | 15€ | 17€ |
| **Batería** | ✅ Included | ✅ +5€ extra | ✅ Included | ✅ +7€ |
| **Carga Pública** | ✅ Asistencia | ❌ No | ✅ Included | ❌ No |
| **Robo Sistema Eléctrico** | ✅ Included | ✅ +3€ | ✅ Included | ✅ +4€ |
| **Asistencia 24h** | ✅ Sí | ❌ No | ✅ Sí | ✅ Sí |
| **Asistencia Nocturna (jóvenes)** | ✅ **INCLUIDA** | ❌ Extra | ✅ Included | ❌ No |
| **Transparencia de Precio** | ✅ "Garantizado" | ❌ Oculto | ⚠️ Parcial | ❌ Oculto |

**Ángulo Editorial:**
- Somos los ÚNICOS que hacemos "seguro moto eléctrica barato" SIN sacrificar coberturas
- Jóvenes: asistencia nocturna INCLUIDA (competencia cobra extra o no tiene)

---

### 🎯 Recomendaciones para @marketing-copywriter

1. **Ángulo:** Seguro COMPLETO, no habrá sorpresas
2. **Pain points:** Motos eléctricas = riesgos nuevos (batería, carga, electricidad)
3. **Tono:** Directo, accesible, joven (si audiencia es 25-40)
4. **CTAs:**
   - Primary: "Calcula tu presupuesto en 2 minutos" (call to action)
   - Secondary: "Cambiarme a Línea Directa" (ya cliente de otro)
   - Tertiary: "Llámame gratis 917 706 803" (fono LD real)
5. **Keyword placement:**
   - H1: 1x "seguro moto eléctrica barato"
   - First para: 1x "2026" (recency)
   - H2: "mejores seguros moto eléctrica baratos"
   - Meta title: "Seguro Moto Eléctrica Barato - Línea Directa"
   - Meta desc: "Coberturas completas desde 12€/mes. Batería incluida. Asistencia 24h. Calcula gratis."
6. **Estructura Copy:**
   - Intro (hook): "¿Crónica de moto eléctrica? Te protegemos completo y barato"
   - Benefit bullets: Qué cubre
   - Social proof: "3.7M clientes confían en nosotros"
   - CTA: Botón calculadora

---

**Final:** El agente ha generado en ~3 min lo que tomaría 2 horas manual.

```

---

### Step 3.3: Copiar OUTPUT a la sesión

```bash
# Comando 27
code .claude/sessions/moto-electrica-barata.md
```

**En VS Code, reemplaza `[El agente rellenará esto]` con el output del agente.**

Básicamente: Copia lo que generó Claude y pégalo en la sesión bajo "## Salida @seo-strategist"

**Salva:** Cmd+S

**Fin de FASE 3 (Primera Demo).** [Demo terminada. "¿Ven? Esto que ven en sesión = contenido producido en 3 min, no 2 horas."]

---

## **FASE 4: Explicación MCPs + Flujo Agentes (73 min - 83 min = 10 min)**

### Step 4.1: Mostrar tabla de decisiones

**NO es un comando, es una explicación. Muestra en pantalla:**

```
Decisión: "¿Cómo el agente supo hacer esto?"

SIN MCPs:
- Agente: "Será importante mencionar rodillo regenerativo"
- Output: Genérico

CON MCPs (lo que pasó aquí):
- Agente consulta Playwright MCP: "¿Qué dice AXA en H1?"
- Playwright: "AXA dice 'Moto Eléctrica: Líderes en Protección', NO menciona 'barato'"
- Agente decide: "GAP: nadie dice 'barato' explícito. Yo pongo 'Barato' en H1"
- Output: Data-driven

RESULTADO: H1 optimizado porque MCP mostró lo que competencia NO está haciendo.
```

---

### Step 4.2: Explicar flujo agentes

**De pizarra / slides:**

```
Flujo que haríamos si continuásemos:

moto-electrica-barata.md (sesión compartida)
         │
         ├─ @seo-strategist INPUT → OUTPUT (ya hecho)
         │
         ├─ @marketing-copywriter INPUT (lee brief anterior) → OUTPUT
         │  "Crea artículo full, expandiendo FAQs, CTA claro"
         │
         ├─ qa_checker.py INPUT → OUTPUT
         │  "Valida keywords LSI, estructura H tags, densidad"
         │
         ├─ @html-implementer INPUT → OUTPUT
         │  "Convierte Markdown a HTML, embebe schema FAQPage"
         │
         ├─ @seo-tecnico INPUT (HTML file) → OUTPUT
         │  "Audita: Lighthouse score, schema validation, a11y"
         │
         └─ ✅ DONE: HTML publicable en 30 min
```

---

### Step 4.3: Mostrar el archivo de sesión actual

```bash
# Comando 28 (en terminal)
cat .claude/sessions/moto-electrica-barata.md | head -50

# ✓ Output: Verá el contenido de la sesión con el brief que @seo-strategist generó

# PUNTO IMPORTANTE mostrar aquí:
# "Todo lo que hizo el agente está AQUÍ. Próximo agente (copywriter) va a leer esto.
# Trazabilidad 100%. Si algo está mal, el siguiente agente puede comentar y mejorar.
# Es como un Google Doc compartido pero versionado en Markdown."
```

---

### Step 4.4: Mencionar recursos del workspace

```bash
# Comando 29
ls -la .claude/skills/

# ✓ Output:
# total 56
# drwxr-xr-x  4 simba  staff  128 Apr  6 14:32 .
# drwxr-xr-x  5 simba  staff  160 Apr  6 14:32 ..
# drwxr-xr-x 12 simba  staff  384 Apr  6 14:32 copywriting
# drwxr-xr-x 15 simba  staff  480 Apr  6 14:32 seo
# drwxr-xr-x  8 simba  staff  256 Apr  6 14:32 seo-tecnico

# Comando 30
ls -la .claude/skills/seo/references/ | head -10

# ✓ Output: Lista de recursos SEO
# -rw-r--r--  1 simba  staff  15420 Apr  6 14:32 holistic-seo-guide.md
# -rw-r--r--  1 simba  staff   8900 Apr  6 14:32 core-entity-definition.md
# -rw-r--r--  1 simba  staff  12300 Apr  6 14:32 topical-authority-mapping.md
# ... (más ficheros de Koray)

# Comando 31
ls -la .claude/skills/seo-tecnico/references/ | head -10

# ✓ Output: CWV, Lighthouse, a11y (de Addy Osmani)
# -rw-r--r--  1 simba  staff  18900 Apr  6 14:32 core-web-vitals-guide.md
# -rw-r--r--  1 simba  staff  12400 Apr  6 14:32 lighthouse-best-practices.md
# -rw-r--r--  1 simba  staff   9200 Apr  6 14:32 accessibility-wcag.md
# ... (MIT licensed)
```

**Explanation:** "Estos archivos son referencias. Los agentes los leen automáticamente. Holistic SEO (Koray) sabe de topical authority. Addy Osmani sabe de performance. Están DENTRO del repo, así que siempre están disponibles."

---

**Fin de FASE 4 (Explicación MCPs + Flujo).** [83 min. "Preguntas antes de cerrar?"]

---

## **FASE 5: Cierre + Recursos (83 min - 90 min = 7 min)**

### Step 5.1: Recap visual

```bash
# Comando 32 (para mostrar archivos de output)
ls -la tools/outputs/

# ✓ En producción, aquí estarían los HTMLs listos para publicar:
# -rw-r--r--  1 simba  staff   45230 Apr  6 18:00 moto-electrica.html
# -rw-r--r--  1 simba  staff   52100 Apr  6 18:05 coche-barato.html
# -rw-r--r--  1 simba  staff   38940 Apr  6 18:10 hogar-ocupacion.html
```

---

### Step 5.2: Mostrar repo README

```bash
# Comando 33
head -30 README.md

# ✓ Output: Descripción del pipeline, contexto general
```

---

### Step 5.3: Links para compartir

**Pega en chat/email post-workshop:**

```markdown
### 🔗 Repositorios & Recursos

1. **Workshop Pipeline** (lo que usamos hoy)
   https://github.com/gabinoguera/mkt-ghen-workshop

2. **Holistic SEO** (Koray/E-Online - framework topical authority)
   https://github.com/e-onsoftware/holistic-seo
   
3. **Web Quality Skills** (Addy Osmani - CWV, a11y, performance)
   https://github.com/addyosmani/web-quality-skills

### 📧 Próximos Pasos

- [ ] Clona repo en tu máquina
- [ ] Intenta sesión 1 (30 min máximo)
- [ ] Anota qué falta / qué confundió
- [ ] Siguiente workshop: **Lunes 13 Abril**, copywriting + QA

### 💬 Dudas en Slack
[enlace a canal Slack privado de LD]
```

---

### Step 5.4: End-of-class script (dilo en voz alta)

```
"Hemos hecho MUCHO en 90 minutos.

Clonamos un repo real. Instalamos Python. Configuramos project context.
Y vimos cómo un agente IA, en 3 minutos, generó una estrategia SEO 
que a un equipo humano le tomaría 2 horas.

La magia no es la IA. La magia es:
✓ Arquitectura clara (agentes, skills, MCPs)
✓ Context compartido (CLAUDE.md, sesiones)
✓ Feedback loops (cada agente mejora lo anterior)
✓ Escala (podés hacer 100 artículos sin burnout)

Llévense el repo. Intenten. Van a fallar en algo. Cuando fallen, 
van a aprender. Eso es normal.

Slack abierto para dudas. Nos vemos el lunes para copywriting.

¡Gracias! 🚀"
```

---

## **COMANDOS RÁPIDOS DE REFERENCIA**

Guarda estos para troubleshooting rápido:

```bash
# Ver dónde estoy
pwd

# Ver estructura completa
tree -L 3 -I '__pycache__|.venv'

# Activar Python venv
cd tools && source .venv/bin/activate

# Desactivar venv
deactivate

# Ver vars de entorno
cat .env | grep -i company

# Ver MCPs
cat .mcp.json | jq '.mcpServers | keys'

# Ver sesiones actuales
ls .claude/sessions/

# Ver outputs HTML generados
ls tools/outputs/html/

# Limpiar caché
find . -type d -name '__pycache__' -exec rm -rf {} +  2>/dev/null

# Ver logs si algo falla
tail -50 tools/*.log  2>/dev/null

# Cambiar permisos ejecución
chmod +x tools/*.sh
```

---

**FINAL:** ¡Ya tienes todos los comandos necesarios para llevar cabo el workshop sin improvisaciones!

Timing estimado:
- Setup: 25 min
- Config: 7 min
- Demo: 15 min
- MCPs + Flujo: 10 min
- Cierre: 7 min

**Total: 64 min workshops + 26 min buffer para Q&A, errors, slower systems = 90 min. ✓**

Buena suerte 🚀

