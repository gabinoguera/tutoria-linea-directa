# ✅ CHECKLIST PRE-WORKSHOP (6 Abril 2026)

## 🎯 Setup Completado
- ✓ Python venv en `tools/.venv/`
- ✓ `.env` con datos LD configurado
- ✓ requirements.txt instalados
- ✓ `.github/` structure creado (agents, skills, references)
- ✓ PROMPTS_SECUENCIALES.md con 8 prompts totales
- ✓ GitHub repositorio actualizado

---

## 📋 PROMPTS LISTOS (en PROMPTS_SECUENCIALES.md)

### FASE 1: Crear Agentes (Min 0-10)
```
PROMPT 0A: @seo-strategist          ← Holistic SEO ref
PROMPT 0B: @marketing-copywriter    ← lineadirecta.com ref  
PROMPT 0C: @html-implementer        ← Core Web Vitals / Addy Osmani ref
PROMPT 0D: @qa-checker              ← SEO técnico repo ref
```

### FASE 2: Ejecutar Agentes (Min 10-85)
```
PROMPT 1: @seo-strategist           → _SESSION_ESTRATEGIA_SEO.md
PROMPT 2: @marketing-copywriter     → _SESSION_COPYWRITING.md
PROMPT 3: @html-implementer         → tools/outputs/html/landing.html
PROMPT 4: @qa-checker               → _SESSION_VALIDACION.md
```

---

## 📚 Referencias Integradas en Prompts

| Prompt | Referencias |
|--------|------------|
| **PROMPT 0A** | Holistic SEO (https://www.holisticseo.digital/) + Addy Osmani |
| **PROMPT 0B** | lineadirecta.com (página real LD, tono, CTAs) |
| **PROMPT 0C** | Core Web Vitals (https://web.dev/vitals/) + Addy Osmani standards |
| **PROMPT 0D** | GitHub SEO técnico (https://github.com/gabinoguera/gh_seo) |
| **PROMPT 1** | Holistic SEO methodology |
| **PROMPT 2** | LD diferencial + audiencias reales |
| **PROMPT 3** | React + Bootstrap + performance LD stack |
| **PROMPT 4** | Pre-deploy checklist |

---

## 🚀 Inicio Día 6 Abril

```bash
# Terminal: Setup inicial (5 min antes)
cd ~/Documents/BrainCode/LINEA\ DIRECTA
source tools/.venv/bin/activate
python3 -c "from dotenv import load_dotenv; load_dotenv(); import os; print(f'✓ LD Ready: {os.getenv(\"COMPANY_NAME\")}')"

# Resultado esperado: ✓ LD Ready: Línea Directa Aseguradora
```

---

## 📁 Archivos Clave

| Archivo | Propósito |
|---------|----------|
| **PROMPTS_SECUENCIALES.md** | 📌 DOCUMENTO PRINCIPAL (8 prompts) |
| **README_INDICE.md** | Índice general + instrucciones |
| **GUION_RESUMIDO_90MIN.md** | Timeline slide instructor |
| **BRIEF_LANDING_MOTO_ELECTRICA.md** | Brief inicial marketing |
| **SPECS_SEO_BASE.md** | Template specs (agents modifican) |
| **.github/agents/\*.md** | Definiciones agentes |
| **.github/skills/\*.md** | Definiciones skills |
| **tools/requirements.txt** | Dependencias Python |
| **.env** | Config LD (protegido .gitignore) |

---

## ⏱️ Timeline Workshop

```
Min 0-10:   Intro + crear agentes (PROMPT 0A-0D)
Min 10-30:  Ejecutar @seo-strategist (PROMPT 1)
Min 30-50:  Ejecutar @marketing-copywriter (PROMPT 2)
Min 50-70:  Ejecutar @html-implementer (PROMPT 3)
Min 70-80:  Ejecutar @qa-checker (PROMPT 4)
Min 80-90:  Mostrar resultado + Q&A
```

---

## 📌 Workflow Día del Workshop

1. **Min -5:** Setup terminal + verificar venv
2. **Min 0:** Abrir VS Code + Copilot Chat
3. **Min 0-10:** Copiar PROMPT 0A/0B/0C/0D secuencialmente
4. **Min 10-70:** Copiar PROMPT 1/2/3/4 secuencialmente (outputs → _SESSION_*.md)
5. **Min 70:** Open `tools/outputs/html/landing.html` en navegador
6. **Min 80-90:** Discusión + próximos pasos

---

✅ **Status:** LISTO PARA WORKSHOP 6 ABRIL 2026

**Ref repos:**
- Holistic SEO: https://www.holisticseo.digital/
- Línea Directa: https://www.lineadirecta.com
- GitHub Copilot Agents: https://code.visualstudio.com/docs/copilot/agents/overview
- Core Web Vitals: https://web.dev/vitals/
- SEO Técnico: https://github.com/gabinoguera/gh_seo
