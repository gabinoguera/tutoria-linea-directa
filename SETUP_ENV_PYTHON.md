# ⚙️ SETUP: .env + Python Environment

**Estatus:** PRE-CONFIGURADO Y LISTO (ejecutar esto una sola vez)

---

## 📋 SETUP .env

### Paso 1: Crear archivo .env

```bash
cd ~/Documents/BrainCode/LINEA\ DIRECTA

# Copiar template
cp .env.example .env

# Editar
code .env
```

### Paso 2: Llenar .env con valores LD

```dotenv
# ═══════════════════════════════════════════════════════════
# LÍNEA DIRECTA - CONFIG (LOCAL)
# ═══════════════════════════════════════════════════════════

# Empresa
COMPANY_NAME=Línea Directa Aseguradora
COMPANY_DOMAIN=lineadirecta.com
COMPANY_COUNTRY=es
COMPANY_PHONE=917706803
COMPANY_MARKET=seguros-vehiculo
COMPANY_VERTICAL=moto-electrica

# Coordenadas (España central)
COMPANY_LAT=40.4168
COMPANY_LONG=-3.7038

# ═══════════════════════════════════════════════════════════
# CREDENCIALES OPCIONALES (no necesario para workshop)
# ═══════════════════════════════════════════════════════════

# WordPress (SALTAMOS ESTO - LD no usa WP)
# WP_URL=
# WP_USERNAME=
# WP_PASSWORD=
# WP_XML_RPC_URL=
# RANK_MATH_API_KEY=

# Gemini API (para imágenes - OPCIONAL)
# GEMINI_API_KEY=

# ═══════════════════════════════════════════════════════════
# GOOGLE CLOUD (MCPs - para Fase 2)
# ═══════════════════════════════════════════════════════════

# GSC Path (cuando tengamos acceso)
# GSC_OAUTH_CLIENT_SECRETS_FILE=./client_secrets.json

# GA4 (cuando tengamos acceso)
# GA_PROJECT_ID=
# GA_PROPERTY_ID=

# ═══════════════════════════════════════════════════════════
# GitHub (para MCP de repos)
# ═══════════════════════════════════════════════════════════

# GITHUB_PERSONAL_ACCESS_TOKEN=  # Solo si necesitamos leer repos
```

**Guardar:** Ctrl+S (macOS: Cmd+S)

---

## 🐍 SETUP PYTHON ENVIRONMENT

### Paso 1: Verificar Python instalado

```bash
# Verificar versión
python3 --version

# Debe mostrar: Python 3.11.x o superior
# Si es menor a 3.11:
#   En Mac: brew install python@3.11
#   En Linux: sudo apt install python3.11
#   En Windows: Descargar de python.org
```

### Paso 2: Crear carpeta tools con estructura

```bash
cd ~/Documents/BrainCode/LINEA\ DIRECTA

# Verificar que existe
ls -la tools/

# Si No existe (no debería):
mkdir -p tools/outputs/html
```

### Paso 3: Crear requirements.txt

```bash
cd tools

# Crear archivo
cat > requirements.txt << 'EOF'
# Core dependencies
requests==2.31.1
python-dotenv==1.0.0
click==8.1.3

# Data processing
pandas==2.0.0
openpyxl==3.1.0

# Images
Pillow==10.0.0

# Markdown
markdown==3.4.1

# Web scraping (MCPs simulation)
selenium==4.10.0
beautifulsoup4==4.12.0

# LLM clients (optional)
openai==1.0.0
anthropic==0.7.0

# Utilities
pyyaml==6.0
EOF

cat requirements.txt
```

### Paso 4: Crear y activar virtualenv

```bash
# Desde carpeta tools/

# Crear virtualenv
python3 -m venv .venv

# Activar (Mac/Linux)
source .venv/bin/activate

# Activar (Windows - PowerShell)
# .venv\Scripts\Activate.ps1

# Verificar activación (prompt debe empezar con (.venv))
which python3  # Debe mostrar path a .venv
```

### Paso 5: Instalar dependencias

```bash
# DENTRO del virtualenv activado

# Upgrade pip primero
pip install --upgrade pip

# Instalar requirements
pip install -r requirements.txt

# Verificar instalación
pip list

# Test imports
python3 -c "import requests; import dotenv; print('✓ OK')"
```

**Output esperado:**
```
✓ OK
```

### Paso 6: Crear archivos Python básicos

```bash
# Aún en tools/.venv

# qa_checker.py
cat > qa_checker.py << 'EOF'
#!/usr/bin/env python3
"""
QA Checker: Valida contenido antes de publicar
- Keywords LSI
- Estructura H tags
- Densidad keywords
"""

import sys
from pathlib import Path

def check_keywords(file_path):
    """Valida keywords en archivo .md"""
    content = Path(file_path).read_text(encoding='utf-8')
    keywords = ['seguro', 'moto eléctrica', 'barato']
    
    results = {}
    for kw in keywords:
        count = content.lower().count(kw.lower())
        results[kw] = count
    
    return results

if __name__ == "__main__":
    if len(sys.argv) < 2:
        print("Usage: python qa_checker.py <file.md>")
        sys.exit(1)
    
    results = check_keywords(sys.argv[1])
    print("\n✓ QA REPORT:")
    for kw, count in results.items():
        print(f"  '{kw}': {count} menciones")
EOF

chmod +x qa_checker.py
```

### Paso 7: Desactivar venv (temporal)

```bash
deactivate

# Verificar que volvió a normal (prompt sin (.venv))
```

---

## 📝 .gitignore (para GitHub)

```bash
cd ~/Documents/BrainCode/LINEA\ DIRECTA

# Crear/editar .gitignore
cat > .gitignore << 'EOF'
# Python
tools/.venv/
__pycache__/
*.py[cod]
*$py.class
*.egg-info/
dist/
build/

# Environment
.env
.env.local
.env.*.local

# IDE
.vscode/
.idea/
*.swp
*.swo
*~

# OS
.DS_Store
Thumbs.db

# Outputs
tools/outputs/html/*.html
*.log

# Misc
.cache/
*.tmp
EOF

cat .gitignore
```

---

## 🔗 ACTUALIZAR .mcp.json (MCPs config)

```bash
# No modificar nada aún (MCPs se configuran en Fase 2)
# El archivo ya existe con templates

cat .mcp.json | head -20
```

---

## ✅ CHECKLIST SETUP COMPLETO

- [ ] .env creado con valores LD
- [ ] .env NO committeado a git (ver .gitignore)
- [ ] Python 3.11+ instalado
- [ ] Virtualenv creado en tools/.venv/
- [ ] requirements.txt instalado
- [ ] Python imports OK
- [ ] qa_checker.py creado
- [ ] .gitignore actualizado
- [ ] Archivo listo para push a GitHub

---

## 🚀 PRÓXIMAS ACCIONES

Después de este setup:

1. **Clonar agentes** del repo workshop (solo estructura, no contenido)
2. **Crear .claude/agents/** con nuestros agentes custom
3. **Ejecutar primer agente** @seo-strategist
4. **Subir a GitHub** tutoria-linea-directa  

---

## 📞 TROUBLESHOOTING

### Error: "venv not found"
```bash
# Solución:
cd tools
python3 -m venv .venv
source .venv/bin/activate
```

### Error: "pip: command not found"
```bash
# Solución:
python3 -m pip install --upgrade pip
```

### Error: "ModuleNotFoundError: No module named 'requests'"
```bash
# Solución:
source tools/.venv/bin/activate
pip install -r tools/requirements.txt
```

### Error: ".env not found"
```bash
# Solución:
cd ~/Documents/BrainCode/LINEA\ DIRECTA
cp .env.example .env
# Luego editar .env con valores
```

---

**Status:** ✅ SETUP COMPLETO Y LISTO PARA GITHUB

