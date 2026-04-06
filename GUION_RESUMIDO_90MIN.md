# ⚡ GUIÓN RESUMIDO: Pipeline Agentes GitHub Copilot de SEO, marketing y HTML (90 min)

**Fecha:** 6 Abril 2026 | **Asistentes:** Equipo Marketing + Tech LD  
**Objetivo:** De cero a primer agente funcionando generando estrategia SEO  
**Framework:** GitHub Copilot Agents (no Carlo/Claude) | **Referencia:** https://code.visualstudio.com/docs/copilot/agents/overview

---

## 📍 TIMELINE (90 min total)

| Min | Módulo | Qué | 
|---|---|---|
| 0-10 | Intro | Problem statement + conceptos 3 agentes GitHub Copilot |
| 10-20 | Setup | .env + Python venv (PRE-CONFIGURADO) |
| 20-35 | Agentes | Explicar @seo-strategist, @copywriter, @html-implementer |
| 35-65 | Demo Vivo | Invocar agentes desde PROMPTS_SECUENCIALES.md |
| 65-80 | Flujo | Cómo se comunican agentes vía sesiones .md |
| 80-90 | Q&A | Preguntas + recursos + próximos pasos |

---

## 🎯 INTRO (0-10 MIN)

### El Reto
- LD tiene 3.7M clientes, miles de keywords sin atacar
- Contenido SEO manual = 3-5 horas X artículo  
- **Solución:** Sistema de agentes IA (GitHub Copilot) basado en prompts + contexto

### Lo que haremos HOY
1. Entender 3 agentes GitHub Copilot
2. Ejecutar @seo-strategist que genere brief de landing  
3. Ver cómo se comunican agentes vía archivos compartidos (.md)

### Resultado esperado
- Brief SEO + topical map + keywords de "Seguro Moto Eléctrica Barata"
- 25 min de trabajo manual ≈ 3 min con GitHub Copilot Agents

---

## 🧠 CONCEPTOS

### ¿Qué es GitHub Copilot Agents?
- Agentes: Tareas autónomas + contexto compartido
- Skills: Funciones reutilizables (ej: @qa-checker)
- MCPs: APIs simuladas (ej: @DATA-LINEADIRECTA)
- Reference: https://code.visualstudio.com/docs/copilot/agents/overview

---

### 3 Agentes en el Pipeline

```
AGENTE 1: @seo-strategist (GitHub Copilot)
└─ INPUT: Keyword + brief inicial (BRIEF_LANDING_MOTO_ELECTRICA.md)
└─ OUTPUT: SPECS_SEO_BASE.md actualizado, topical map, FAQs, keywords
└─ TAREA: Análisis competencia, estructura contenido

AGENTE 2: @marketing-copywriter (GitHub Copilot)
└─ INPUT: Estrategia SEO anterior + audiencias
└─ OUTPUT: H1 magnetic, body copy, FAQs, CTAs
└─ TAREA: Redacción para conversión presupuesto

AGENTE 3: @html-implementer (GitHub Copilot)
└─ INPUT: Especificaciones SEO + copywriting
└─ OUTPUT: HTML landing (HTML + Bootstrap + schema markup)
└─ TAREA: Desarrollo, Core Web Vitals, tracking GTM
```

### ¿Por qué GitHub Copilot Agents?
- ✅ Integrado en VS Code (sin herramientas externas)
- ✅ Prompts simples (<5 líneas) = máxima claridad
- ✅ Agentes = reutilizables en otros proyectos LD
- ✅ MCPs simulados = simular APIs sin código real

---

## 🚀 AGENTES GITHUB COPILOT

### Explicar cada agente

**@seo-strategist**
- Rol: Experto SEO
- Input: Keyword + diferenciadores LD
- Output: Estrategia, keywords, topical map
- Prompt: Max 5 líneas (ver PROMPTS_SECUENCIALES.md)

**@marketing-copywriter**
- Rol: Redactor especializado seguros
- Input: Estrategia SEO anterior
- Output: Copy persuasivo + FAQs + schema markup
- Prompt: Max 5 líneas

**@html-implementer**
- Rol: Dev frontend (HTML+ Bootstrap)
- Input: Specs SEO + copywriting
- Output: landing.html con validación Lighthouse
- Prompt: Max 5 líneas

---

## 🎬 DEMO VIVO (35-65 MIN)

### PASO 1: Abrir PROMPTS_SECUENCIALES.md
- Muestra estructura: 4 prompts simples
- Explain: cada agente hace UNA cosa bien

### PASO 2: Ejecutar @seo-strategist
```
Copilot Chat → PROMPT 1 (de PROMPTS_SECUENCIALES.md)
Output → guarda en _SESSION_ESTRATEGIA_SEO.md
Tiempo: 10 min
```

### PASO 3: Ejecutar @marketing-copywriter
```
Copilot Chat → PROMPT 2 
Input: archivo _SESSION_ESTRATEGIA_SEO.md anterior
Output → _SESSION_COPYWRITING.md
Tiempo: 10 min
```

### PASO 4: Ejecutar @html-implementer
```
Copilot Chat → PROMPT 3
Input: SPECS_SEO_BASE.md actualizado + _SESSION_COPYWRITING.md
Output → tools/outputs/html/landing.html
Tiempo: 10 min
```

### PASO 5: Validar con @qa-checker
```
Copilot Chat → PROMPT 4 (qa-checker skill)
Validaciones: Title, meta, schema, Core Web Vitals
Output → _SESSION_VALIDACION.md
Tiempo: 5 min
```

### PASO 6: Mostrar resultado en navegador
```bash
open tools/outputs/html/landing.html
```

---

## 🔗 FLUJO AGENTES (65-80 MIN)

### Cómo se comunican
```
brief.md → @seo-strategist → _SESSION_ESTRATEGIA_SEO.md
                ↓
_SESSION_ESTRATEGIA_SEO.md → @marketing-copywriter → _SESSION_COPYWRITING.md
                ↓
SPECS_SEO_BASE.md + _SESSION_COPYWRITING.md → @html-implementer → landing.html
```

### Patrón de sesión compartida
1. Agente 1 genera `.md` compartido
2. Agentes siguientes LEEN ese `.md`
3. Escriben su propio `.md`
4. Próximo agente lo consume
5. Final: archivo HTML en `tools/outputs/html/`


## ❓ Q&A 

### Próximos pasos
1. Crear más landings (motos, vivienda, seguros hogar)
2. Integrar MCPs reales (GSC, Analytics, pricing engine LD)
3. Deploy automático con GitHub Actions
4. Reportes semanales vía agente

### Recursos
- GitHub Copilot Agents: https://code.visualstudio.com/docs/copilot/agents/overview
- Tech LD: HTML + Bootstrap + Liferay
- docs: README_INDICE.md + PROMPTS_SECUENCIALES.md

---

**Notas para instructor:**
- Tener PROMPTS_SECUENCIALES.md abierto en VS Code
- Copilot Chat debe estar habilitado (GitHub Copilot subscription)
- Archivos de sesión (_SESSION_*.md) se guardan automáticamente
- Si falla un agente: reintentar con prompt más específico

