# 🐙 GITHUB SETUP: tutoria-linea-directa

**Repo vacío:** https://github.com/gabinoguera/tutoria-linea-directa  
**Objetivo:** Configurar repo local + push inicial

---

## 🔑 PASO 1: Git Config Local (Primera vez)

```bash
# Configurar usuario (si no está configurado)
git config --global user.name "Tu Nombre"
git config --global user.email "tu.email@lineadirecta.com"

# Verificar
git config --list | grep user
```

---

## 📦 PASO 2: Inicializar Repo Local

```bash
cd ~/Documents/BrainCode/LINEA\ DIRECTA

# Inicializar git (si no existe .git)
git init

# Verificar
ls -la | grep .git
```

---

## 🔗 PASO 3: Conectar a GitHub

```bash
# Agregar remote (reemplazar URL por tu repo)
git remote add origin https://github.com/gabinoguera/tutoria-linea-directa.git

# Verificar
git remote -v
# Debe mostrar:
# origin  https://github.com/gabinoguera/tutoria-linea-directa.git (fetch)
# origin  https://github.com/gabinoguera/tutoria-linea-directa.git (push)
```

---

## 📝 PASO 4: Crear README.md base

```bash
cd ~/Documents/BrainCode/LINEA\ DIRECTA

cat > README.md << 'EOF'
# 🏁 Tutoría: Pipeline Agentes SEO para Línea Directa

**Proyecto:** Workshop + Lab con agentes IA para desarrollo de landings SEO  
**Equipo:** Marketing + Dev  
**Fecha Inicio:** 6 Abril 2026  

## 📚 Documentación

- **[Guión 90 min](GUION_RESUMIDO_90MIN.md)** - Flujo workshop resumido
- **[Brief Landing](BRIEF_LANDING_MOTO_ELECTRICA.md)** - Especificaciones marketing
- **[Specs SEO](SPECS_SEO_BASE.md)** - Especificaciones desarrollo
- **[Setup .env + Python](SETUP_ENV_PYTHON.md)** - Configuración inicial

## 🏗️ Estructura Proyecto

```
tutoria-linea-directa/
├── .claude/
│   ├── agents/          ← Agentes custom LD (se crean aquí)
│   ├── skills/          ← Skills invocables
│   ├── sessions/        ← Sesiones activas
│   └── doc/             ← Documentación referencia
├── tools/
│   ├── .venv/           ← Python virtualenv
│   ├── outputs/html/    ← HTMLs generados
│   └── *.py             ← Scripts Python
├── content-briefs/      ← Outputs agentes
├── landings/            ← HTMLs finales para producción
├── .env                 ← Variables config (NO COMMITEAR)
├── .mcp.json            ← MCPs config
├── CLAUDE.md            ← DNA del proyecto
└── README.md            ← Este archivo
```

## 🚀 Quick Start

```bash
# 1. Clonar este repo
git clone https://github.com/gabinoguera/tutoria-linea-directa.git
cd tutoria-linea-directa

# 2. Setup environment
cp .env.example .env
cd tools && source .venv/bin/activate

# 3. Run agente
# (instrucciones en GUION_RESUMIDO_90MIN.md)
```

## 👥 Agentes

- **@seo-strategist** - Generador briefs SEO
- **@marketing-copywriter** - Redacción de contenido
- **@html-implementer** - Generador HTML + schema

## 📊 Caso Piloto

**Landing:** Seguro Moto Eléctrica Barata  
**Keyword:** "seguro moto eléctrica barato"  
**Volumen:** 340 búsquedas/mes  
**Competencia:** AXA, Allianz, MAPFRE  

Salida esperada: Brief → Artículo → HTML en 25 minutos

## 📅 Timeline

| Fase | Fecha | Output |
|---|---|---|
| 1. Setup + Brief | 6 Abril | SEO Brief (agente 1) |
| 2. Copywriting | 13 Abril | Artículo full (agente 2) |
| 3. Implementación | 15 Abril | HTML deployed (agente 3) |
| 4. Repetir | 20+ Abril | 2+ landings adicionales |

## 🔗 Recursos

- [Holistic SEO](https://github.com/e-onsoftware/holistic-seo) - Framework topical authority
- [Web Quality Skills](https://github.com/addyosmani/web-quality-skills) - CWV + a11y
- [LD Web](https://coches.lineadirecta.com) - Sitio referencia

## 📞 Contactos

- **Instructor:** [TU NOMBRE]
- **Tech Lead:** [NOMBRE]
- **Product:** [NOMBRE]

## 📝 Notas

- Repo es TEMPLATE - copia y adapta
- No commitear .env ni outputsHTML (ver .gitignore)
- Sesiones en `.claude/sessions/` son historial trabajo agentes

EOF

cat README.md
```

---

## 📥 PASO 5: Git Add + Commit Inicial

```bash
# Revisar qué archivos hay
git status

# Agregar TODOS EXCEPTO .env (ver .gitignore)
git add -A

# Revisar qué se va a subir
git status

# Verificar .env no está en staging
git diff --cached .env
# No debe aparecer nada (correcto)

# Commit inicial
git commit -m "Initial commit: structure + documentation

- Guión resumido (90 min)
- Brief de landing para marketing
- Especificaciones SEO para desarrollo
- Setup .env + Python
- README + estructura proyecto
"
```

---

## 🚀 PASO 6: Push a GitHub

```bash
# Subir a GitHub (rama main)
git push -u origin main

# Verificar en GitHub: https://github.com/gabinoguera/tutoria-linea-directa
```

**Primer push puede pedir autenticación:**
```bash
# Si pide usuario:
Username: <tu_github_username>

# Si pide contraseña:
# Usa PERSONAL ACCESS TOKEN (no contraseña normal)
# Settings > Developer settings > Personal access tokens > Tokens (classic)
# Genera un token con scopes: repo, write:packages
```

---

## 📂 PASO 7: Verificar Repo en GitHub

Abre: https://github.com/gabinoguera/tutoria-linea-directa

Debe mostrar:
```
✓ README.md
✓ GUION_RESUMIDO_90MIN.md
✓ BRIEF_LANDING_MOTO_ELECTRICA.md
✓ SPECS_SEO_BASE.md
✓ SETUP_ENV_PYTHON.md
✓ .gitignore
✓ (otros archivos proyecto)
```

---

## 🔄 PASO 8: Workflow git post-commit (futuro)

```bash
# Cada vez que hagas cambios en proyecto:

# 1. Ver status
git status

# 2. Agregar cambios
git add .

# 3. Commit con mensaje descriptivo
git commit -m "Agregar agente @seo-strategist"

# 4. Push
git push origin main

# En GitHub, verá:
#  [latest] Agregar agente @seo-strategist - hace 2 minutos
```

---

## 💾 BRANCHES (Opcional - Fase 2+)

```bash
# Si quieres crear branch por agente:

# Branch para agente 1
git checkout -b feature/seo-strategist
# ... hacer cambios ...
git commit -m "Add @seo-strategist agent"
git push origin feature/seo-strategist

# Crear Pull Request en GitHub UI
# Reviewer aprueba / merge a main
```

---

## 🚫 .gitignore - Archivos QUE NO SUBIR

```
Estos archivos NO suben a GitHub:
- .env                      ← Credenciales locales
- tools/.venv/              ← Virtualenv local
- __pycache__/              ← Caché Python
- tools/outputs/html/*.html ← HTMLs generados (temporales)
- *.log                     ← Logs
- .DS_Store                 ← macOS cruft
```

Si accidentalmente hiciste commit:
```bash
# Remover sin borrar local
git rm --cached .env
git commit -m "Remove .env from tracking"
git push

# Local sigue teniendo .env (correcto)
```

---

## 🔐 PROTECCIONES GitHub (Opcional - Fase 2+)

En Settings de repo:

```
Branch protection rules:
- Rama: main
- ✓ Require pull request reviews before merging
- ✓ Dismiss stale pull request approvals
- ✓ Require status checks to pass
```

---

## 📋 CHECKLIST GITHUB SETUP

- [ ] Repo clonado de GitHub en local
- [ ] git init ejecutado
- [ ] git remote add origin ...
- [ ] .gitignore creado/actualizado
- [ ] README.md escritoVer primer commit
- [ ] git add -A (sin .env)
- [ ] git commit inicial
- [ ] git push a origin main
- [ ] Verificar en GitHub.com
- [ ] Agregar colaboradores (opcional)

---

## 🎬 PRÓXIMO: Crear Agentes

Después de setup GitHub:

1. Crear `.claude/agents/seo-strategist/`
2. Crear `.instructions.md` (prompts del agente)
3. Agregar `references/` (documentos)
4. Commit y push
5. Ejecutar agente

---

**Status:** ✅ GIT SETUP COMPLETO

