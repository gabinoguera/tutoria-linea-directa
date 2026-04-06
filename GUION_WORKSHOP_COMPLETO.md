# 📋 GUIÓN DE WORKSHOP: PIPELINE MULTI-AGENTE DE SEO & MARKETING PARA LÍNEA DIRECTA
**Duración:** 90 minutos
**Fecha:** 7 de Abril de 2026 | **Adaptación:** Web custom

---

## 📍 OBJETIVOS DE LA SESIÓN

- ✅ Entender qué son **Agentes IA**, **Skills** y **MCPs** y cómo trabajan juntos
- ✅ Diseñar un pipeline concreto para contenido SEO de seguros (verticales: coche, moto, hogar)
- ✅ Clonar, configurar y ejecutar el repo del workshop desde cero
- ✅ Hacer funcionar el primer agente (SEO Strategy) para un caso real de LD
- ✅ Comprender el flujo de trabajo con sesiones compartidas
- ✅ Ver cómo los MCPs informan decisiones del agente (simulación sin acceso real a GSC/GA4)

---

## ⏱️ CRONOGRAMA DETALLADO (90 MIN)

| **Tiempo** | **Módulo** | **Actividad** | **Duración** |
|---|---|---|---|
| **00:00** | 🎯 Intro + Conceptos | Welcome + problem statement | 5 min |
| **05:00** | 🧠 Conceptual | Agentes, Skills, MCPs (diagrama + analogía) | 12 min |
| **17:00** | 🏗️ Arquitectura | Estructura del pipeline + decisiones de diseño | 8 min |
| **25:00** | 💻 Setup Fase 1 | Clonar repo + primeras carpetas | 8 min |
| **33:00** | 💻 Setup Fase 2 | Configurar `.env` y `.mcp.json` (mock datos x GSC/GA4) | 8 min |
| **41:00** | 💻 Setup Fase 3 | Instalar Python deps + validar tools | 7 min |
| **48:00** | 📝 Adaptación | Crear `CLAUDE.md` para Línea Directa | 10 min |
| **58:00** | 🚀 Primera Demo | Invocar `@seo-strategist` en vivo (live demo) | 15 min |
| **73:00** | 🔍 Q&A + Decisiones | Mostrar MCPs simulados + flujo agentes | 10 min |
| **83:00** | 📚 Recursos | Repositorios Koray + AddioSmany + próximos pasos | 7 min |

**Últimos 5 min:** Resumen ejecutivo + preguntas finales

---

## 🎯 MÓDULO 1: INTRO + PROBLEM STATEMENT (5 MIN)

### Contexto Línea Directa
- **Empresa:** Aseguradora Spain, +30 años, +3.7M clientes  
- **Digital:** Web customizada (no WordPress) - veremos en `coches.lineadirecta.com`  
- **Necesidad:** Atacar búsquedas de alto intento (KW long-tail) como "seguro coche barato", "mejores coberturas moto eléctrica", "cambiarme de seguro hogar"  
- **Reto:** Sin access a GSC/GA4 reales, pero los agentes pueden usar MCPs como "oráculos" para decisiones

### La Pregunta Fundamental
> *¿Cómo generamos contenido SEO de calidad, escalable y coordinado entre múltiples roles (estrategia, copywriting, auditoría técnica) usando agentes IA?*

**La respuesta:** Pipeline multi-agente con Sesiones compartidas

---

## 🧠 MÓDULO 2: CONCEPTOS CLAVE (12 MIN)

### 2.1 ¿Qué es un AGENTE?

```
┌─────────────────────────────────────┐
│     AGENTE = Rol Especializado      │
├─────────────────────────────────────┤
│ • Instrucciones claras de qué hacer  │
│ • Acceso a herramientas / MCPs       │
│ • Contexto del proyecto (CLAUDE.md)  │
│ • Memoria de sesión compartida       │
│ • Capacidad de invocar otros agentes │
└─────────────────────────────────────┘
```

**Analogía IRL:** Equipo de marketing tradicional  
- CEO = Claude (decisiones finales, contexto global)  
- SEO Manager = `@seo-strategist` (análisis, briefs, strategy)  
- Content Writer = `@marketing-copywriter` (redacción, estructura, keywords)  
- QA Lead = `qa_checker.py` (validación, testing)  
- Developer = `@html-implementer` (deploy, outputs)  
- SEO Técnico = `@seo-tecnico` (auditoría, performance, schema)  

**Ventaja:** Cada rol puede tener contexto diferente, archivos anexos, frameworks específicos.

---

### 2.2 ¿Qué es un SKILL?

```
SKILL = Librería de conocimiento invocable
├── Instrucciones (.instructions.md)
├── Contexto (referencias + ejemplos)
├── Archivos de referencia
└── Ejemplos de input/output
```

**En el pipeline hay 3 mains skills:**

| Skill | Propósito | Comando | References |
|---|---|---|---|
| **`/seo`** | Estrategia SEO, topical authority, GEO | `/seo [keyword/vertical]` | Holistic SEO, Core Entity, Topical Maps |
| **`/copywriting`** | Redacción SEO, estructura, frameworks | `/copywriting [formato]` | Copy frameworks, neuropsicología, transiciones |
| **`/seo-tecnico`** | Auditoría técnica, CWV, schema, a11y | `/seo-tecnico [url/file]` | Web Quality Skills (Addy Osmani), Lighthouse |

**¿Dónde vienen las referencias?**
- `@koray/holistic-seo` → Framework de autoridad topical, GEO, keyword research  
- `@addyosmani/web-quality-skills` → MIT licensed, Core Web Vitals, accessibility, performance  

---

### 2.3 ¿Qué es un MCP?

```
MCP = Model Context Protocol
= Puente entre Agente IA y Herramienta Externa
```

**Función:** Le da al agente conexión en tiempo real a datos/acciones sin esperar intervención humana.

**MCPs en el pipeline:**

| MCP | Fuente | Para qué |
|---|---|---|
| `google-search-console` | Google API | Queries reales, CTR, posiciones, trending |
| `google-analytics-4` | Google API | Comportamiento usuarios, páginas top, conversiones |
| `playwright` | Automación browser | Analizar SERPs, screenshots competence |
| `github` | GitHub API | Buscar referencias en repos (Koray, Addy) |
| `context7` | Claude | Buscar en propios documentos del workspace |
| `drawio` | Draw.io | Crear diagramas (topical maps, flujos) |
| `sequential-thinking` | Extended Thinking | Análisis reflexivo, múltiples iteraciones |

**En Línea Directa:**
- No tenemos acceso real a GSC/GA4  
- **PERO**: Vamos a simular MCPs con datos mock para enseñar decisiones informadas  
- El agente puede decir: "Basándome en GSC, la keyword 'seguro moto barato' tiene 450 búsquedas/mes, 8% CTR"

---

### 2.4 ¿Qué es un WORKFLOW con Sesiones?

```
WORKFLOW = Pipeline lineal con decisiones
Sessions = Archivo .md compartido entre agentes como "base de datos"

Anatomía de una sesión:
┌───────────────────────────────────┐
│ SESIÓN: mi-articulo-moto.md       │
├───────────────────────────────────┤
│ # Título: "Mejores Seguros Moto"   │
│                                   │
│ ## Estado: strategy → testing     │
│ ## Autor actual: @seo-strategist  │
│                                   │
│ ## Contexto                       │
│ - Keyword: seguro moto barato     │
│ - Intent: commercial              │
│ - Verticals: moto, eléctrica      │
│                                   │
│ ## Outputs (compartidos)          │
│ ### SEO Brief (seo-strategist)    │
│ [brief generado]                  │
│                                   │
│ ### Content Outline (copywriter)  │
│ [outline generado]                │
│                                   │
│ ### QA Review (qa_checker)        │
│ [validaciones]                    │
│                                   │
│ ### Decisión Implementación       │
│ → Implementation: HTML local      │
│                                   │
│ ### HTML Output (@html-impl)      │
│ [archivo output]                  │
└───────────────────────────────────┘
```

**Ventaja:** Transparencia total, cada agente ve lo que hizo el anterior, puede mejorar.

---

## 🏗️ MÓDULO 3: ARQUITECTURA DEL PIPELINE (8 MIN)

### Flujo estándar: De idea a publicación

```
┌─────────┐     ┌──────────────┐     ┌────────────────┐     ┌──────────┐
│ BACKLOG │────▶│ STRATEGY     │────▶│ CONTENT BRIEF  │────▶│ COPYWRITE│
│ (ideas) │     │@seo-strategy │     │ (sesión .md)   │     │(outline) │
└─────────┘     └──────────────┘     └────────────────┘     └──────────┘
                                                                   │
                                                                   ▼
┌──────────────────────────────────────────────────────────────────┐
│  QA REVIEW (qa_checker.py)                                       │
│  ✓ Keywords + LSI                                                │
│  ✓ Estructura + H tags                                           │
│  ✓ Intención del usuario                                         │
│  ✓ Competencia resuelta                                          │
│  ✓ Densidad de links                                             │
└──────────────────────────────────────────────────────────────────┘
                           │
                ┌──────────┴─────────┐
                ▼                    ▼
        ┌─────────────────┐   ┌──────────────────┐
        │ @wp-implementer │   │ @html-implmenter │
        │ (WordPress)     │   │ (HTML local)     │
        │ [saltamos esto] │   │ [USAMOS ESTO]    │
        └─────────────────┘   └──────────────────┘
                                      │
                                      ▼
                          ┌──────────────────────┐
                          │ HTML + Schema embebido
                          │ (listos para subir)  │
                          └──────────────────────┘
                                      │
                                      ▼
                          ┌──────────────────────┐
                          │ @seo-tecnico         │
                          │ (auditoría final)    │
                          │ ✓ Lighthouse (CWV)   │
                          │ ✓ Schema markup      │
                          │ ✓ Accesibilidad      │
                          │ ✓ Performance        │
                          └──────────────────────┘
                                      │
                                      ▼
                                   DONE ✓
```

### Decisiones de diseño para Línea Directa

| Pregunta | Respuesta | Por qué |
|---|---|---|
| ¿Usamos WordPress? | **NO** | Sitio web customizado de LD |
| ¿Quién publica? | `@html-implementer` | Genera HTML + schema listos para subir |
| ¿Dónde guardamos outputs? | `./tools/outputs/html/` | Versionable, auditable |
| ¿Qué vertical primero? | Coche (mayor volumen) | +1.5M posts anuales sector |
| ¿Sin acceso GSC/GA4? | Usamos MCPs simulados | El agente "actúa" como si tuviera datos |

---

## 💻 MÓDULO 4: SETUP FASE 1 - CLONAR REPO (8 MIN)

### Paso 1: Abrir Terminal en VS Code

```bash
# Abrir VS Code en la carpeta del workspace
cd ~/Documents/BrainCode/LINEA\ DIRECTA
pwd  # Show /Users/simba/Documents/BrainCode/LINEA DIRECTA
```

### Paso 2: Clonar el repo

```bash
git clone https://github.com/gabinoguera/mkt-ghen-workshop.git .
# El `.` clona EN ESTA CARPETA (no crea subcarpeta)

# Validar estructura
ls -la
# Debers ver: .claude/, tools/, competitive-analysis/, site-audit/, etc.
```

### Paso 3: Ver estructura base

```bash
tree -L 2 -I 'node_modules|__pycache__'
# Muestra:
# .
# ├── .claude/
# │   ├── agents/
# │   ├── skills/
# │   ├── sessions/
# │   └── doc/
# ├── tools/
# ├── competitive-analysis/
# ├── content-briefs/
# ├── site-audit/
# ├── topical-maps/
# ├── .env.example
# ├── .mcp.json
# ├── CLAUDE.md
# ├── README.md
# └── WORKSHOP.md
```

### Paso 4: Limpiar y preparar

```bash
# Remover git del repo clonado (es template)
rm -rf .git

# Crear carpetas de outputs que necesitaremos
mkdir -p tools/outputs/html
mkdir -p .claude/sessions

echo "✓ Estructura lista"
```

---

## 💻 MÓDULO 5: SETUP FASE 2 - CONFIGURAR .env Y .mcp.json (8 MIN)

### Paso 1: Copiar .env desde template

```bash
cp .env.example .env
cat .env  # Ver qué variables hay
```

### Paso 2: Editar .env para Línea Directa

```bash
# Abrir en VS Code
code .env
```

**Llenar con datos de LD (ejemplos de verdad):**

```dotenv
# WordPress (lo saltamos, pero lo dejamos vacío por si)
WP_URL=
WP_USERNAME=
WP_PASSWORD=
WP_XML_RPC_URL=
RANK_MATH_API_KEY=

# Gemini (para generar imágenes - OCULTAR EN CLASE, SOLO MOSTRAR)
GEMINI_API_KEY=tu_key_aqui  # (explicar que es optional para la demo)

# Línea Directa config
COMPANY_NAME=Línea Directa
COMPANY_DOMAIN=lineadirecta.com
COMPANY_COUNTRY=es
```

### Paso 3: Configurar .mcp.json (MCPs simulados)

```bash
code .mcp.json
```

**Estructura a mostrar (comentada la realidad):**

```json
{
  "mcpServers": {
    "google-search-console": {
      "command": "npx",
      "args": ["@modelcontextprotocol/server-google-search-console"],
      "env": {
        "GSC_OAUTH_CLIENT_SECRETS_FILE": "./client_secrets.json",
        // En clase: "NO TENEMOS ESTO, pero el agente ACTÚA como si lo tuviera"
      }
    },
    "google-analytics-4": {
      "command": "npx",
      "args": ["@modelcontextprotocol/server-google-analytics"],
      "env": {
        "GA_PROJECT_ID": "mock-lineadirecta-ga4",
        "GA_PROPERTY_ID": "12345678",
        // SIMULAMOS: el agente dirá "según GA4, las páginas de 'moto' convertían 3.2%"
      }
    },
    "github": {
      "command": "npx",
      "args": ["@modelcontextprotocol/server-github"],
      "env": {
        "GITHUB_PERSONAL_ACCESS_TOKEN": "ghp_xxxx"  // Demo read-only
      }
    }
  }
}
```

**En la clase mostrar:** "Aunque no tengamos acceso real, el prompt del agente puede decir: 'Usar MCPs como fuente de verdad para queries, intención, tendencias. Si no está disponible, usa tus conocimientos y marca suposición.'"

---

## 💻 MÓDULO 6: SETUP FASE 3 - INSTALAR DEPS PYTHON (7 MIN)

### Paso 1: Verificar Python

```bash
python3 --version  # Debe ser 3.11+
which python3

# Si no, instalar (en Mac):
# brew install python@3.11
```

### Paso 2: Instalar tools & setup.sh

```bash
cd tools
ls  # Ver: wp_publisher.py, qa_checker.py, local_generator.py, etc.

# Ejecutar setup script
chmod +x setup.sh
./setup.sh

# Esto crea virtualenv y instala:
# - requests, python-dotenv, selenium, pillow, etc.
```

### Paso 3: Validar instalación

```bash
source .venv/bin/activate

# Probar que imports funcionan
python3 -c "import requests; import dotenv; print('✓ Basic imports OK')"

# Ver qué tools tenemos
ls *.py | head -10

deactivate  # Salir del venv
```

**En caso de error:** "Normal en primera instalación. Errors comunes: pip outdated (pip install --upgrade pip), falta de dependencies del sistema (en Mac es poco probable)."

---

## 📝 MÓDULO 7: ADAPTACIÓN - CREAR CLAUDE.md PARA LÍNEA DIRECTA (10 MIN)

### ¿Por qué es crítico CLAUDE.md?

Es el **DNA del proyecto**. Los agentes leen esto antes de tomar decisiones.

### Paso 1: Abrir CLAUDE.md base

```markdown
# 🚗 Línea Directa: Pipeline SEO Multi-Agente

## Datos de la Empresa

**Nombre:** Línea Directa Aseguradora  
**URL:** https://coches.lineadirecta.com (y dominios hermanos)  
**País:** España  
**Audiencia:** Compradores de seguros car/moto/home, principalmente 25-55 años  
**Verticales:** Coche, Moto, Hogar (nos enfocamos en Coche + Moto eléctrica)  
**Diferenciador:** "Te mejoramos el precio, directamente" + 30 años en mercado, +3.7M clientes  
**Núcleo de Negocio:** Seguros low-cost con ser vice completas

---

## Estrategia de Contenido

### Pillar Topics (Core Entities)
- **Coche:** Seguro coche barato, comparar seguros coche, cambiarme de aseguradora
- **Moto:** Seguro moto barato, moto eléctrica, asistencia 24h
- **Hogar:** Ocupación ilegal (NUEVA COBERTURA), alarma hogar, robo

### Palabras Clave Estratégicas (Mock de GSC/GA4)
```
Volumen estimado (Google Keyword Planner):
- "seguro coche barato" → 1,200 búsquedas/mes | Commercial High
- "cambiar seguro coche" → 780 búsquedas/mes | Commercial High  
- "moto eléctrica seguro" → 340 búsquedas/mes | Commercial High
- "ocupación ilegal hogar" → 220 búsquedas/mes | Commercial + Informational
```

### Intent Mapping
- **Commercial:** Compradores listos → Comparadores, calculadora presupuestos, testimonios
- **Informational:** Educación → Guías, FAQs, tipos de cobertura
- **Navigational:** Ya decide → Cómo contratar, cambiarme, mi área cliente

---

## Estructura Sitio Web

```
coches.lineadirecta.com/
├── /seguro-coche/ [PILAR]
│   ├── /seguro-coche-barato/ [cluster]
│   ├── /seguro-coche-joven/ [cluster]
│   └── /comparar-seguros-coche/ [cluster]
├── /seguro-moto/ [PILAR]
│   ├── /moto-electrica/ [cluster]
│   └── /asistencia-moto/ [cluster]
├── /seguro-hogar/ [PILAR]
│   ├── /ocupacion-ilegal/ [cluster]
│   └── /robo-hogar/ [cluster]
└── /blog/ [contenido editorial]
```

---

## Audiencias

### Audiencia 1: "Comparador Sensible al Precio"
- Edad: 25-40, empleados
- Búsqueda típica: "seguro coche barato 2026"
- Necesidad: Calcular presupuesto rápido
- Call-to-Action: "Calcula tu presupuesto en 2 minutos"

### Audiencia 2: "Propietario de Eléctrico"
- Edad: 35-50, higher income
- Búsqueda típica: "seguro coche eléctrico cobertura"
- Necesidad: Entender coberturas específicas (batería, carga)
- Call-to-Action: "Somos líderes en eléctricos + coberturas mejores"

### Audiencia 3: "Joven Conductora"
- Edad: 18-25, first-time buyers
- Búsqueda típica: "seguro moto joven barato"
- Necesidad: Confianza, asistencia 24h
- Call-to-Action: "Asistencia nocturna INCLUIDA"

---

## Información de Competencia (Holistic SEO Context)

### Competidores Principales SERP
1. **Allianz:** Fuerte en brand, muchos backlinks, contenido técnico
2. **AXA:** SEO más agresivo, más páginas temáticas
3. **MAPFRE:** Tráfico orgánico similar a LD, pero menos nicho
4. **Seguros Baratos:** Low-cost, intent similar

### Diferenciación de LD
- Mayor transparencia ("precio garantizado")
- Mejor servicio al cliente (ratings)
- Especialización en eléctricos/jóvenes
- Cobertura de ocupación ilegal (única en 2026)

---

## Referencias y Frameworks

### SEO Strategy
- Autoridad Topical (Holistic SEO framework - repo Koray)
- Mapeos semánticos: "seguro coche" vs "aseguranza coche" vs "póliza coche"
- Potencial GEO (aunque es nacional, sin ramificación por ciudades en esta fase)

### Copywriting
- Ángulo: "Mejor Precio + Mejor Servicio" (vs low-cost puro)
- Tonalidad: Directa, clara, sin jerga aseguradora
- CTAs: Calculadora, llamada gratis, área cliente

### Calidad Web (Web Quality Skills - Addy Osmani)
- Core Web Vitals: INP <200ms crítico para formularios de calculadora
- Accesibilidad: Calculadora debe ser 100% keyboard-accessible
- Performance: Lighthouse score mínimo 75

---

## Estado Actual del Proyecto

**Fase:** Setup y primer piloto  
**Objetivo Piloto:** 1 artículo "Seguro Moto Eléctrica Barato" end-to-end  
**Timeline:** 1 sesión de workshop  
**Outputs esperados:** HTML file + schema markup embebido

```

### Paso 2: Guardar en workspace

```bash
# En VS Code, File > Save
# Ubicación: ~/Documents/BrainCode/LINEA\ DIRECTA/CLAUDE.md
```

---

## 🚀 MÓDULO 8: PRIMERA DEMO EN VIVO - @seo-strategist (15 MIN)

### Setup Pre-Demo

**Crear sesión para el demo:**

```bash
cp .claude/sessions/TEMPLATE.md .claude/sessions/moto-electrica-barata.md
```

**Editar sesión:**

```markdown
# Sesión: "Seguro Moto Eléctrica Barata"

## Título: Seguro Moto Eléctrica Barata

## Contexto Inicial
- **Keyword Principal:** "seguro moto eléctrica barato 2026"
- **Vertical:** Moto eléctrica
- **Intent:** Commercial (buyer)
- **Audiencia:** Propietarios de motos eléctricas, 25-45 años, Tech-savvy
- **Volumen estimado (Keyword Planner):** 340 búsquedas/mes
- **Intención analizada:** Busco seguro barato, pero con coberturas completas (batería, carga)

## Estado: strategy

## Salida @seo-strategist
[El agente rellenará esto en tiempo real]
```

### Demo Actual de Invocación

**En Claude Code (o similar):**

```
@seo-strategist

Lee el archivo `.claude/sessions/moto-electrica-barata.md` y analiza la keyword "seguro moto eléctrica barato".

Tu tarea:
1. Analizar competencia en SERP (simulado)
2. Definir topical map: qué subtemas cubrir
3. Generar content brief con H1, H2s, keyword placement
4. Listar FAQs que debe cubrir
5. Mostrar diferenciadores de Línea Directa vs competencia

Usa el contexto de CLAUDE.md (Línea Directa).

Ten en cuenta:
- MCPs simulados: Si preguntarías a GSC/GA4, describe qué VERÍAN los datos
- Referencias: Holistic SEO (topical authority), GEO framework
- Output: Guarda el brief en la sesión

Formato esperado:
## SEO Brief: "Seguro Moto Eléctrica Barata"

### Análisis Competencia SERP
(3-4 competidores principales)

### Topical Map
(diagrama o bullet points)

### Content Outline
(H1, H2s, estructura)

### FAQPage Schema
(10-15 FAQs)

### Diferenciadores LD
(vs Allianz, AXA, MAPFRE)
```

### Qué veremos en la Demo (Simulado)

**Output esperado (3-5 min de ejecución):**

```markdown
## SEO Brief: "Seguro Moto Eléctrica Barata"

### 📊 Análisis Competencia SERP

Posiciones actuales (simuladas de GSC):
1. **AXA Seguros** - Seguro Moto Líderes en Eléctricos
2. **Allianz** - Moto Eléctrica 
3. **MAPFRE** - Protege tu Moto Electrónica
4. **Seguros Baratos** - Moto E a partir de 15€/mes

**Observation:** Competencia BAJA, no hay un dominante en "barato"

### 🗺️ Topical Map

```
Seguro Moto Eléctrica Barata (Core)
├── Cobertura específica
│   ├── Daño a batería
│   ├── Robo de sistema eléctrico
│   └── Carga pública
├── Modelos (contexto)
│   ├── Freno regenerativo
│   ├── Autonomía (impacto en uso)
│   └── Velocidad máxima
└── Factores precio
    ├── Edad conductor
    ├── Zona geográfica
    └── Potencia en W
```

### 📄 Content Outline

**H1:** "Seguro Moto Eléctrica Barato: Coberturas Completas desde 12€/mes"

**H2-Level Clusters:**
1. **¿Por qué contratar un seguro para moto eléctrica?**
   - H3: Riesgos únicos de motos eléctricas
   - H3: Qué cobertura NO te protege en eléctricos

2. **Mejores seguros de moto eléctrica baratos (2026)**
   - H3: Coberturas que te importan
   - H3: Línea Directa vs competencia

3. **¿Cuál es el precio de un seguro de moto eléctrica?**
   - H3: Factores que afectan el precio
   - H3: Calculadora presupuesto

4. **FAQs: Seguro Moto Eléctrica**
   - H3: Schema markup (FAQPage)

---

**Keyword Placement:**
- H1: 1x "seguro moto eléctrica barato"
- Intro: mention "seguro moto eléctrica barato 2026"
- H2[2]: "mejores seguros de moto eléctrica baratos"
- Meta: "Seguro moto eléctrica barato - Línea Directa"

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
      "name": "¿Cuál es el precio de un seguro moto eléctrica?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "En Línea Directa, desde 12€/mes. El precio varía por edad, potencia en W, zone..."
      }
    },
    {
      "@type": "Question",
      "@id": "q2",
      "name": "¿Cubre roturas de batería?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Sí, nuestra cobertura de 'Daño Técnico' incluye batería, motor, cargador..."
      }
    },
    // ... 8 más
  ]
}
```

### 💚 Diferenciadores LD

| Aspecto | LD | Allianz | AXA |
|---|---|---|---|
| **Precio desde** | 12€ | 18€ | 15€ |
| **Batería** | ✅ Included | ✅ Optional +5€ | ✅ Included |
| **Asistencia 24h** | ✅ Sí | ❌ No | ✅ Sí |
| **Cargador** | ✅ Covered | ❌ No | ❌ No |
| **Transparencia** | "Precio Garantizado" | ❌ | ❌ |

### 🎯 Recomendaciones para el Copywriter
- **Ángulo:** Seguro COMPLETO, no vaya a faltar nada
- **Pain points:** Motos eléctricas = nuevos riesgos (batería, carga)
- **CTA:** "Calcula tu presupuesto en 2 min" + "Cobertura de batería INCLUIDA"
```

### Lo importante a resaltar en la demo:

1. **El agente leyó CLAUDE.md** → Sabe de LD, verticales, audiencias
2. **El agente usó MCPs simulados** → "Analice GSC" (sin tener acceso real)
3. **El agente generó estructura SEO** → H1, H2, schema FAQPage
4. **El agente pasó contexto al siguiente rol** → Copywriter sabe qué hacer
5. **Todo está en la sesión compartida** → Trazabilidad 100%

---

## 🔍 MÓDULO 9: Q&A + MCPs SIMULADOS + FLUJO AGENTES (10 MIN)

### Explicación: Por qué MCPs son clave

**Sin MCPs:** Agente genera contenido especulativo  
**Con MCPs:** Agente toma decisiones basadas en datos reales

**Simulación en clase:**

"El agente tuvo acceso a MCPs que dijeron:
- **GSC:** Keyword 'seguro moto eléctrica barato' = 340 búsquedas/mes, intención commercial
- **GA4:** Usuarios en landing de 'moto' convertían 3.2% a forma de presupuesto
- **Playwright:** Competidores en posición 1-3 no hablan de 'barato', oportunidad

Decisión del agente: 'Voy a hacer un H2 muy claro: 'Mejores seguros moto eléctrica baratos''"

### Próximos pasos: Qué pasaría después

**Si continuásemos el flujo (que NO haremos en 90 min):**

```
1. @marketing-copywriter
   Input: SEO Brief (brief anterior)
   Tarea: Escribir artículo full + expandir FAQs
   Output: Markdown con contenido

2. qa_checker.py
   Input: Markdown
   Validate: Keywords, estructura, links, densidad
   Output: Report con recomendaciones

3. @html-implementer
   Input: Markdown validado
   Tarea: Generar boilerplate HTML + schema embebido
   Output: index.html (copy-paste ready)

4. @seo-tecnico
   Input: HTML
   Tarea: Auditoría Lighthouse, schema, a11y
   Output: Report + mejoras
```

### Preguntas típicas que pueden surgir

**P: ¿Qué pasa si dos agentes quieren hacer cosas diferentes?**  
R: La sesión es la fuente de verdad. Cada agente lee OUTPUT anterior, puede comentar o sugerir mejoras antes de proseguir. Control de versiones en .md.

**P: ¿Cuánto tiempo tarda cada agente?**  
R: ~3-5 min por paso (depende complejidad). Para 1 artículo full: ~20-25 min.

**P: ¿Si falta acceso a GSC/GA4, cómo mejoramos?**  
R: Podemos:
- Agregar MCPs reales en el futuro (autenticarse con OAuth)
- Mientras, el agente "aprende" del análisis manual que le pasamos
- O usar tools como SEMrush/Ahrefs via MCP custom

**P: ¿Podemos usar esto en WordPress?**  
R: Sí, hay lógica `@wp-implementer` que publica via REST API. No la usamos en demo porque LD no tiene WP.

---

## 📚 MÓDULO 10: RECURSOS + PRÓXIMOS PASOS (7 MIN)

### Repositorios clave mencionados

#### 1. **Koray / Holistic SEO**
```
Repo: github.com/e-onsoftware/holistic-seo
Uso en workshop: Frameworks de autoridad topical, mapeos semánticos
Fichero: .claude/skills/seo/references/holistic-seo/
Ejemplos:
- Core Entity Definition
- Topical Maps (clusters + pillar)
- Geographic SEO (multilenguaje)
```

**Instalación/Acceso en clase:**
```bash
# El repo ya está en .claude/skills/seo/references/
# Los agentes lo leen automáticamente cuando invocas /seo

# Si quieres explorar:
ls .claude/skills/seo/references/
cat .claude/skills/seo/references/holistic-seo-guide.md  # Overview
```

#### 2. **Addy Osmani / Web Quality Skills**
```
Repo: github.com/addyosmani/web-quality-skills
Licencia: MIT
Uso en workshop: Core Web Vitals, accesibilidad, performance
Fichero: .claude/skills/seo-tecnico/references/

Topics:
- Lighthouse audits
- Core Web Vitals (LCP, INP, CLS)
- Accesibilidad (WCAG)
- Performance best practices
- SEO técnico (schema, canonicals, indexación)
```

**Acceso:**
```bash
# El contenido ya está en skills/seo-tecnico/references/
# Cuando invocas /seo-tecnico, el agente lee automáticamente

# Explorar stats:
find .claude/skills/seo-tecnico/references -name "*.md" | wc -l
# → Aprox 30+ documentos de referencia
```

### Próximos pasos en Línea Directa

#### Siguiente Workshop
1. **Día 1:** Setup + Primer artículo piloto end-to-end (moto eléctrica)
2. **Día 2:** Iterar feedback + hacer 2 artículos más (coche barato + hogar ocupación ilegal)
3. **Día 3:** Auditoría CWV + deployment a producción

#### Mejoras Futuras
- [ ] Conectar MCP real a GSC/GA4 (requiere OAuth de Google)
- [ ] MCP custom: SEMrush/Ahrefs API para keyword research avanzado
- [ ] Agente adicional: `@keyword-researcher` (pre-strategy)
- [ ] Integración con WordPress (si lo adoptan en futuro)
- [ ] Analytics dashboard: Seguimiento diario de rankings, tráfico

#### Roles para Línea Directa
- **Product Manager:** Oversee sessions, prioridad de verticales
- **Google Cloud Admin:** Setup autenticación GSC/GA4
- **Developer:** Integración deploy a producción, monitoreo
- **Content Lead:** Validación briefs antes de copywriter
- **SEO Lead:** Auditoría final @seo-tecnico

---

## 🎓 Conclusiones

### Lo que hemos construido en 90 min

✅ **Conceptos:** Agentes, Skills, MCPs, Workflows  
✅ **Setup:** Repo clonado, Python instalado, configuración  
✅ **Primer agente:** @seo-strategist generó SEO brief real  
✅ **Caso de uso:** Línea Directa, palabra clave real, output usable  
✅ **Recursos:** Holistic SEO + Web Quality Skills accesibles

### Por qué esto va a cambiar tu SEO

- **Velocidad:** 25min para 1 artículo SEO end-to-end (vs 3-5 horas manual)
- **Coherencia:** Todos los agentes hablan el mismo "idioma" (CLAUDE.md)
- **Escalabilidad:** Puedes hacer 10, 50, 100 artículos sin burnout
- **Calidad:** Cada paso tiene QA, referencias, best practices embebidas
- **Auditoría:** Todo es versionable, transparent, mejoreable

### Preguntas finales

- ¿Dudas sobre el pipeline?
- ¿Alguien quiere ver cómo cambiar a vertical "Coche"?
- ¿Cómo nos comunicamos cuando vuelva el siguiente workshop?

---

## 📎 Anexos: Comandos rápidos para recordar

```bash
# Iniciar sesión
cp .claude/sessions/TEMPLATE.md .claude/sessions/mi-topic.md

# Activar Python venv
cd tools && source .venv/bin/activate

# Ver outputs HTML generados
ls -la tools/outputs/html/

# Subir cambios a git (si es necesario)
git add -A && git commit -m "Piloto: artículo moto eléctrica barata"

# Limpiar outputs
rm tools/outputs/html/*.html  # Cuidado!

# Ver logs si algo falla
tail -100 tools/qa_checker.log
```

---

**Creado:** 6 Abril 2026  
**Workshop:** Línea Directa (90 min)  
**Objetivo:** Desde cero a primer pipeline multi-agente SEO funcional  

¡Que disfrutes la sesión! 🚀

