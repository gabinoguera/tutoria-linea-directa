# Acceptance Criteria - Landing Page Seguro Moto Eléctrica 2026

## 📋 User Stories Aceptadas

### 1. Propietario de Moto Eléctrica (30-45 años)
- **Historia:** Como propietario de moto eléctrica, quiero ver claramente si la batería está cubierta en el seguro, para decidir si contratarlo.
- **Criterios:**
  - ✅ Sección de "Beneficios" con destacado sobre "Cobertura de Batería"
  - ✅ Ícono distintivo para batería incluida
  - ✅ Texto explícito: "Batería incluida" en H3
  - ✅ CTA: "Calcula presupuesto" visible en hero

### 2. Comparador de Precios (25-35 años)
- **Historia:** Como comparador de precios, quiero comparar el costo del seguro eléctrico vs gasolina, para asegurarme de que sea económico.
- **Criterios:**
  - ✅ Sección "Comparación con la Competencia" con tabla/infografía
  - ✅ Precio LD: 12€/mes vs Competencia: 15-18€
  - ✅ Diferenciadores clave: Batería, Carga pública, Asistencia
  - ✅ CTA: "Somos más baratos" o similar con llamada a presupuesto

### 3. Joven Tech (18-28 años)
- **Historia:** Como joven tech amante de motos eléctricas, quiero confirmar que hay asistencia 24h incluida, para sentirme seguro en cualquier momento.
- **Criterios:**
  - ✅ Sección de "Asistencia 24 Horas" en Beneficios
  - ✅ Texto explícito: "Asistencia 24h INCLUIDA"
  - ✅ Descripción de carga pública con asistencia
  - ✅ Bloque de audiencia "Jóvenes Aficionados a la Tecnología"
  - ✅ CTA dirigida: "Asistencia nocturna INCLUIDA"

### 4. Visitante General
- **Historia:** Como visitante general, quiero calcular un presupuesto personalizado rápidamente, para obtener una cotización instantánea.
- **Criterios:**
  - ✅ Formulario de Presupuesto funcional (HTML validation)
  - ✅ Campos: Tipo de moto, Edad, Cobertura deseada
  - ✅ Validación HTML (type="email", required, etc.)
  - ✅ Botón envío clara y visible
  - ✅ Múltiples CTAs: Hero, Beneficios, Sección Audiencia, Footer

### 5. Usuario Potencial
- **Historia:** Como usuario potencial, quiero ver diferenciadores clave contra la competencia, para entender por qué elegir LD.
- **Criterios:**
  - ✅ Tabla/Infografía: LD vs Competencia
  - ✅ Diferenciadores: Precio, Batería, Carga Pública, Asistencia, Transparencia
  - ✅ Ícanos visuales o símbolos (✅ para ✅, ❌ para ❌)

---

## 🧩 COMPONENTES TÉCNICOS - Acceptance Criteria

### HEADER
- ✅ Etiqueta semántica `<header>`
- ✅ Logo LD (SVG o texto "Línea Directa")
- ✅ Navegación con `<nav>` y menú (Inicio, Seguros, Contacto)
- ✅ Responsive: menú colapsable en móvil (Bootstrap navbar)
- ✅ Fixed o sticky en scroll (opcional, visual)

### HERO SECTION
- ✅ Etiqueta `<section>` semántica con id="hero"
- ✅ H1 ÚNICO: "Seguro para Moto Eléctrica 2026 - Completo y Barato"
- ✅ Subtítulo: Descriptivo sobre completitud + precio
- ✅ Imagen de hero (moto eléctrica) con alt text
- ✅ CTA primario: Botón "Calcula tu Presupuesto" (#formulario)
- ✅ Gradient o fondo visual inspirado en LD
- ✅ Responsive: texto y botón escalables, imagen responsive

### SECCIÓN BENEFICIOS
- ✅ Etiqueta `<section>` con id="beneficios"
- ✅ H2: "Beneficios del Seguro"
- ✅ 4 bloques de beneficio (grid Bootstrap col-md):
  1. **Cobertura de Batería**
     - ✅ H3: "Cobertura de Batería"
     - ✅ Ícono batería
     - ✅ Descripción: "Incluida en tu póliza, sin costes adicionales"
  2. **Precio Competitivo**
     - ✅ H3: "Precio Competitivo"
     - ✅ Ícono moneda/euro
     - ✅ Descripción: "Desde 12€/mes, el más barato del mercado"
  3. **Asistencia 24 Horas**
     - ✅ H3: "Asistencia 24 Horas"
     - ✅ Ícono reloj/teléfono
     - ✅ Descripción: "Apoyo 24/7 en cualquier emergencia"
  4. **Carga Pública con Asistencia**
     - ✅ H3: "Carga Pública con Asistencia"
     - ✅ Ícono cargador/electricidad
     - ✅ Descripción: "Cobertura en puntos de carga pública"
- ✅ Cada bloque con ícono (emoji, SVG, o unicode)
- ✅ Responsive: 1 columna móvil, 2 tablet, 4 desktop

### SECCIÓN COMPARACIÓN
- ✅ Etiqueta `<section>` con id="comparacion"
- ✅ H2: "Comparación con la Competencia"
- ✅ Tabla HTML `<table>` con:
  - ✅ Cabecera: Aspecto | Línea Directa | Competencia
  - ✅ 5 filas de comparación:
    1. Precio desde: 12€/mes | 15-18€
    2. Batería incluida: ✅ | ❌
    3. Carga pública: ✅ Con asistencia | ❌
    4. Asistencia 24h: ✅ | Parcial
    5. Transparencia: ✅ Garantizado | ❌ Sorpresas
  - ✅ Estilos: filas alternadas, LD resaltada
  - ✅ Responsive: scroll horizontal en móvil
- ✅ Accesibilidad: `<thead>`, `<tbody>`, scope attr

### SECCIÓN AUDIENCIA
- ✅ Etiqueta `<section>` con id="audiencia"
- ✅ H2: "Para Quién es Este Seguro"
- ✅ 3 bloques de audiencia (Bootstrap grid):

  **1. Propietarios de Moto Eléctrica**
  - ✅ H3: "Propietarios de Moto Eléctrica"
  - ✅ Descripción targeteada: "30-45 años, seguro completo para tu moto"
  - ✅ CTA: "Calcula presupuesto para propietarios"
  - ✅ Icono/Badge

  **2. Comparadores de Precio**
  - ✅ H3: "Comparadores de Precio"
  - ✅ Descripción targeteada: "25-35 años, mejor relación calidad-precio"
  - ✅ CTA: "Somos más baratos, compruébalo"
  - ✅ Icono/Badge

  **3. Jóvenes Aficionados a la Tecnología**
  - ✅ H3: "Jóvenes Aficionados a la Tecnología"
  - ✅ Descripción targeteada: "18-28 años, asistencia nocturna incluida"
  - ✅ CTA: "Asistencia 24h para ti"
  - ✅ Icono/Badge

- ✅ Responsive: 1 columna móvil, 3 desktop
- ✅ Cada bloque con color/icono distintivo

### SECCIÓN FORMULARIO
- ✅ Etiqueta `<section>` con id="formulario"
- ✅ H2: "Calcula tu Presupuesto"
- ✅ Formulario `<form>` funcional:
  - ✅ Campo 1: "Tipo de Moto" (select: Tipo A, Tipo B, Tipo C)
    - `<label>`, `<select>`, `required`
  - ✅ Campo 2: "Tu Edad" (input number, min 18, max 120)
    - `<label>`, `<input type="number">`, `required`
  - ✅ Campo 3: "Email" (input email)
    - `<label>`, `<input type="email">`, `required`
  - ✅ Campo 4: "Cobertura Deseada" (radio: Básica, Completa)
    - `<fieldset>`, `<legend>`, `<input type="radio">`, `required`
  - ✅ Botón Envío: `<button type="submit">` "Calcula tu Presupuesto"
  - ✅ Validación HTML (no JS requerido)
  - ✅ Mensaje de éxito simulado (placeholder o alert HTML)
- ✅ Responsive: 1 columna, ancho completo en móvil

### FOOTER
- ✅ Etiqueta semántica `<footer>`
- ✅ Secciones:
  - ✅ Información de contacto: Teléfono, Email
  - ✅ Enlaces legales: Términos, Privacidad, Cookies
  - ✅ Redes sociales: Links a Twitter, Facebook, Instagram (iconos)
  - ✅ Copyright: "© 2026 Línea Directa. Todos los derechos reservados."
- ✅ Responsive: Grid columnas adaptadas, mobile-friendly
- ✅ Accesibilidad: Links con title, iconos con alt

---

## 🔍 SEO & META TAGS

### Meta Tags
- ✅ Meta Title (58 caracteres): "Seguro Moto Eléctrica 2026 - Completo y Barato | Línea Directa"
- ✅ Meta Description (152 caracteres): "Descubre el seguro completo para moto eléctrica 2026 de Línea Directa: batería incluida, asistencia 24h y precio desde 12€/mes. Calcula tu presupuesto ahora."
- ✅ Meta Charset: UTF-8
- ✅ Meta Viewport: responsive (width=device-width, initial-scale=1.0)
- ✅ Meta Theme Color: Marca LD (rojo/azul)
- ✅ OG Tags: og:title, og:description, og:type, og:url (simulado con placeholder)

### Keywords Optimization
- ✅ Keyword primario "seguro moto eléctrica" density 1.5-2% en contenido
- ✅ Keywords secundarios incluidos: "seguro moto 2026", "cobertura batería moto eléctrica", "precio seguro moto eléctrica"
- ✅ Keywords LSI: "asistencia 24h moto", "seguro moto vs gasolina", "batería incluida seguro", "carga pública moto eléctrica", "seguro transparente moto"

### Jerarquía de Headings
- ✅ H1 ÚNICO: "Seguro para Moto Eléctrica 2026 - Completo y Barato"
- ✅ H2 (secciones principales):
  1. "Beneficios del Seguro"
  2. "Comparación con la Competencia"
  3. "Para Quién es Este Seguro"
  4. "Calcula tu Presupuesto"
- ✅ H3 (subsecciones):
  - Bajo Beneficios: "Cobertura de Batería", "Precio Competitivo", "Asistencia 24h", "Carga Pública con Asistencia"
  - Bajo Audiencia: "Propietarios de Moto Eléctrica", "Comparadores de Precio", "Jóvenes Aficionados a la Tecnología"

### Schema.org JSON-LD
- ✅ FAQPage Schema:
  ```json
  {
    "@context": "https://schema.org",
    "@type": "FAQPage",
    "mainEntity": [
      {
        "@type": "Question",
        "name": "¿Está cubierta la batería en el seguro?",
        "acceptedAnswer": {"@type": "Answer", "text": "Sí, la batería está incluida en todas nuestras pólizas sin costes adicionales."}
      },
      {
        "@type": "Question",
        "name": "¿Hay asistencia 24h?",
        "acceptedAnswer": {"@type": "Answer", "text": "Sí, tenemos asistencia 24 horas incluida para emergencias."}
      },
      {
        "@type": "Question",
        "name": "¿Cuál es el precio desde?",
        "acceptedAnswer": {"@type": "Answer", "text": "Desde 12€/mes, el más competitivo del mercado."}
      }
    ]
  }
  ```
- ✅ LocalBusiness Schema:
  ```json
  {
    "@context": "https://schema.org",
    "@type": "LocalBusiness",
    "name": "Línea Directa",
    "url": "https://www.lineadirecta.com",
    "telephone": "+34XXX", 
    "address": {"@type": "PostalAddress", "addressCountry": "ES"},
    "sameAs": ["https://www.facebook.com/LineaDirecta", "https://twitter.com/LineaDirecta"]
  }
  ```

---

## 🎨 ESTILOS & DISEÑO

### Colors
- ✅ Primary: Rojo Línea Directa (inspirado en lineadirecta.com)
- ✅ Secondary: Azul o gris claro (contraste)
- ✅ Accent: Verde (éxito, beneficios)
- ✅ Background: Blanco o gris muy claro
- ✅ Text: Gris oscuro o negro (>4.5:1 contraste)

### Typography
- ✅ Font Family: Arial, Helvetica, sans-serif (o similar con Google Fonts para peso)
- ✅ Heading Size: H1 3-4rem, H2 2-2.5rem, H3 1.5-2rem responsive
- ✅ Body Font Size: 16px base, escalable
- ✅ Line Height: 1.5-1.6 para legibilidad

### CSS Inline Crítico
- ✅ CSS crítico para LCP <2.5s inline en `<head>`
- ✅ Bootstrap 5 CDN para componentes responsive
- ✅ Media queries para responsive design

### Bootstrap 5 Grid
- ✅ Container: `.container` o `.container-fluid`
- ✅ Beneficios: `col-12 col-md-6 col-lg-3`
- ✅ Audiencia: `col-12 col-lg-4`
- ✅ Tabla: responsive con overflow en móvil
- ✅ Formulario: `col-12`, inputs full width

---

## ♿ ACCESIBILIDAD - WCAG AA

### Color & Contrast
- ✅ Contraste texto/fondo: >4.5:1 (WCAG AA)
- ✅ No depender únicamente de color (iconos + texto)
- ✅ Links diferenciados visualmente (subrayado, color, etc.)

### Estructura Semántica
- ✅ `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<footer>`
- ✅ Landmarks ARIA (role="contentinfo" si es necesario)
- ✅ Etiquetas `<label>` asociadas a inputs (for/id)
- ✅ Fieldset y legend para radio/checkbox

### Navegación por Teclado
- ✅ Todos los botones y links focusables con Tab
- ✅ Focus visible (outline o box-shadow)
- ✅ Orden lógico de tabs: header → hero → beneficios → comparación → audiencia → formulario → footer
- ✅ Enter activa botones, formulario submittable con Enter

### Imágenes & Multimedia
- ✅ Todas las imágenes con `alt` descriptivo
- ✅ Alt text: "Moto eléctrica moderna de Línea Directa", "Icono de batería incluida", etc.
- ✅ Iconos puramente decorativos: `aria-hidden="true"`

### Formulario Accesible
- ✅ `<label>` vinculada a cada input (for="input-id")
- ✅ Form validation con texto de error accesible
- ✅ Placeholder no reemplaza label
- ✅ Inputs con type correcto (email, number, etc.)

### Responsive & Text
- ✅ Zoom mínimo 2x sin horizontal scroll
- ✅ Texto resizable (no fixed font size absoluto)
- ✅ Line spacing 1.5x para readability

---

## 🚀 RENDIMIENTO - Core Web Vitals

### LCP (Largest Contentful Paint) <2.5s
- ✅ CSS crítico inline
- ✅ Imagen hero optimizada (tamaño <100KB)
- ✅ Bootstrap CDN versión minificada
- ✅ Sin JavaScript render-blocking

### CLS (Cumulative Layout Shift) <0.1
- ✅ Dimensiones definidas para hero imagen (aspect-ratio)
- ✅ Espacios reservados para publicidad/embeds (si aplica)
- ✅ Fuentes: size-adjust o font-display:swap
- ✅ Sin movimientos inesperados de elementos

### FID (First Input Delay) <100ms
- ✅ JavaScript mínimo (validación HTML nativa)
- ✅ Interactividad inmediata (botones, links, formulario)
- ✅ Sin scripts pesados o main thread bloqueado

### Page Weight
- ✅ Total <500KB (incluido HTML, CSS, imágenes)
- ✅ HTML <50KB
- ✅ CSS inline <20KB crítico + CDN Bootstrap minificared
- ✅ <2 imágenes, optimizadas (WebP o JPEG optimizado)

---

## 📱 RESPONSIVE REQUIREMENTS

### Breakpoints Bootstrap 5
- ✅ XS (<576px): 1 columna, tipografía reducida
- ✅ SM (≥576px): Ajustes menores
- ✅ MD (≥768px): 2 columnas donde aplica
- ✅ LG (≥992px): 3-4 columnas, layout desktop
- ✅ XL (≥1200px): Full desktop

### Mobile Optimizations
- ✅ Touch targets: >44x44px (botones, links)
- ✅ Padding/margin adecuado entre elementos
- ✅ Menú colapsable (hamburguesa)
- ✅ Formulario campos full-width
- ✅ Tabla scroll horizontal si es necesario

### Desktop Optimization
- ✅ Hero: máximo 1200px ancho
- ✅ Márgenes laterales en pantallas >1400px
- ✅ Layout grid 4 columnas en beneficios
- ✅ Botones con hover state (pointer)

---

## ✨ DIFERENCIADORES DE CONVERSIÓN

### CTAs Multiple Estratégicos
- ✅ Hero CTA: "Calcula tu Presupuesto" (primario)
- ✅ Beneficios CTA: Opcional, reinforcement
- ✅ Audiencia CTAs: 3 variantes por segmento (Propietarios, Comparadores, Tech)
- ✅ Formulario: CTA envío claro
- ✅ Footer: Link formulario para navegación

### Messaging Personalizado
- ✅ Beneficios section: Enfoque en cobertura + precio + asistencia
- ✅ Comparación: LD vs Competencia clara
- ✅ Audiencia: Pain points + soluciones específicas
- ✅ Formulario: Confianza mediante validación clara

### Trust Signals
- ✅ Logo Línea Directa en header/hero
- ✅ Distinción clara vs competencia
- ✅ Comparación transparente (precio desde 12€)
- ✅ Diferenciadores concretos (batería, asistencia)

---

## 📊 CONVERSIÓN TARGET

- ✅ Meta: 3%+ de clics al formulario
- ✅ Rastreable: Botones con id/class para tracking
- ✅ Formulario presupuesto: Primera conversión medida

---

## ✅ CHECKLIST FINAL DE CUMPLIMIENTO

- [ ] Meta Title: 58 caracteres exactos
- [ ] Meta Description: 152 caracteres exactos
- [ ] H1 único presente
- [ ] H2 para cada sección principal (4 total)
- [ ] H3 para subsecciones (4 en beneficios + 3 en audiencia)
- [ ] Keyword "seguro moto eléctrica" densidad 1.5-2%
- [ ] Keywords secundarios y LSI incluidos
- [ ] Schema FAQPage JSON-LD
- [ ] Schema LocalBusiness JSON-LD
- [ ] 7 componentes presentes: Header, Hero, Beneficios, Comparación, Audiencia, Formulario, Footer
- [ ] Formulario con 4+ campos y validación HTML
- [ ] Bootstrap 5 responsive (col-md, col-lg, etc.)
- [ ] HTML5 semántico (header, main, section, footer, nav, etc.)
- [ ] Tabla comparación 5x3
- [ ] 4 beneficios con iconos
- [ ] 3 audiencias con CTAs específicas
- [ ] CSS inline crítico para LCP <2.5s
- [ ] Contraste >4.5:1 WCAG AA
- [ ] Navegación por teclado completa
- [ ] Alt text en todas las imágenes
- [ ] Abre directamente en navegador sin build
- [ ] Archivo único: landing.html

---

## 📝 NOTAS TÉCNICAS

- Abre directamente en navegador: `file:///path/landing.html`
- No requiere servidor local
- Bootstrap 5 desde CDN: `<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">`
- CSS inline en `<style>` tag en `<head>` para crítico
- Imágenes: placeholder o SVG simple (no externa si se requiere offline)
- Iconos: emoji o UTF-8 unicode (no Font Awesome si requiere CDN adicional)
