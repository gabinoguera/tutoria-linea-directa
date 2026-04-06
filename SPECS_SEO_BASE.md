# 🔍 ESPECIFICACIONES SEO BASE - LANDING MOTO ELÉCTRICA

**Proyecto:** Pipeline SEO Línea Directa  
**Objective:** Especificaciones técnicas + SEO para desarrollo landing  
**Audience:** Dev team + @html-implementer  

---

## 📌 ESPECIFICACIÓN RÁPIDA

| Item | Valor |
|---|---|
| **Keyword Principal** | seguro moto eléctrica barato |
| **URL Slug** | `/seguros/moto-electrica-barata/` |
| **Meta Title** | Seguro Moto Eléctrica Barato - Línea Directa (60 chars) |
| **Meta Description** | Coberturas completas desde 12€/mes. Batería incluida. Asistencia 24h. Calcula gratis. (160 chars) |
| **H1** | Seguro Moto Eléctrica Barato: Coberturas Completas desde 12€/mes \| Línea Directa |
| **Schema Type** | FAQPage + LocalBusiness (LD) |
| **Canonical** | https://www.lineadirecta.com/seguros/moto-electrica-barata/ |
| **Robots** | index, follow |
| **Language** | es_ES |

---

## 🎯 KEYWORDS TARGET

### Primary (Debe ranking en Top 3)
- seguro moto eléctrica barato → 340 vol/mes → Commercial

### Secondary (Debe ranking en Top 10)
- moto eléctrica seguro barato 2026 → 85 vol/mes
- coberturas seguro moto eléctrica → 95 vol/mes
- asistencia moto eléctrica 24h → 75 vol/mes
- cómo asegurar moto eléctrica → 60 vol/mes

### LSI Keywords (Mencionar en contenido natural)
- seguro motos eléctricas
- batería moto eléctrica cobertura
- robo sistema eléctrico
- asistencia 24h moto
- moto eléctrica vs gasolina precio
- carga pública asistencia
- jóvenes seguro moto barato

**Keyword Density Meta:**
- Primary keyword: 1-2% del contenido (no spam)
- LSI: 3-5 menciones naturales
- Sinonimos: "seguro" vs "asegurar" vs "cobertura"

---

## 📝 ESTRUCTURA HTML REQUERIDA

```html
<!DOCTYPE html>
<html lang="es_ES">
<head>
    <!-- Meta Básicos -->
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Seguro Moto Eléctrica Barato - Línea Directa</title>
    <meta name="description" content="Coberturas completas desde 12€/mes. Batería incluida. Asistencia 24h. Calcula gratis.">
    
    <!-- Open Graph (Social) -->
    <meta property="og:title" content="Seguro Moto Eléctrica Barato">
    <meta property="og:description" content="Coberturas completas desde 12€/mes">
    <meta property="og:image" content="/images/moto-electrica-og.jpg">
    <meta property="og:url" content="https://www.lineadirecta.com/seguros/moto-electrica-barata/">
    <meta property="og:type" content="website">
    
    <!-- Twitter Card -->
    <meta name="twitter:card" content="summary_large_image">
    <meta name="twitter:title" content="Seguro Moto Eléctrica Barato">
    <meta name="twitter:description" content="Coberturas completas desde 12€/mes">
    <meta name="twitter:image" content="/images/moto-electrica-twitter.jpg">
    
    <!-- Canonical -->
    <link rel="canonical" href="https://www.lineadirecta.com/seguros/moto-electrica-barata/">
    
    <!-- Robots -->
    <meta name="robots" content="index, follow">
    
    <!-- CSS + Fonts -->
    <link rel="stylesheet" href="/css/main.css">
    <link rel="preconnect" href="https://fonts.googleapis.com">
    
    <!-- Schema Markup (JSON-LD) -->
    <script type="application/ld+json">
    {
      "@context": "https://schema.org",
      "@type": "FAQPage",
      "mainEntity": [
        {
          "@type": "Question",
          "@id": "q1",
          "name": "¿Cuánto cuesta el seguro de moto eléctrica?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "En Línea Directa, desde 12€/mes. El precio varía según edad del conductor, potencia de la moto en W, zona geográfica e historial de siniestros."
          }
        },
        {
          "@type": "Question",
          "@id": "q2",
          "name": "¿Cubre daños a la batería?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Sí, nuestra cobertura de 'Daño Técnico Completo' incluye batería, motor, cargador y todo el sistema eléctrico."
          }
        },
        {
          "@type": "Question",
          "@id": "q3",
          "name": "¿Tiene asistencia 24 horas incluida?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Sí, siempre. Asistencia en viaje, grúa, reparación en carretera. Todo sin coste adicional."
          }
        }
        // ... 10-15 FAQs totales
      ]
    }
    </script>
    
    <!-- Local Business Schema -->
    <script type="application/ld+json">
    {
      "@context": "https://schema.org",
      "@type": "LocalBusiness",
      "name": "Línea Directa Aseguradora",
      "image": "https://www.lineadirecta.com/logo.jpg",
      "description": "Aseguradora especializada en seguros de coche, moto y hogar",
      "address": {
        "@type": "PostalAddress",
        "addressCountry": "ES"
      },
      "telephone": "+34917706803",
      "url": "https://www.lineadirecta.com"
    }
    </script>
</head>

<body>
    <!-- H1: Palabra clave + brand -->
    <h1>Seguro Moto Eléctrica Barato: Coberturas Completas desde 12€/mes | Línea Directa</h1>
    
    <!-- Introducción: Mencionar keyword en 50 primeras palabras -->
    <p>
        El seguro de moto eléctrica barato de Línea Directa te protege completo: 
        batería, motor, asistencia 24h. Desde 12€/mes sin sorpresas. 
        Calcula tu presupuesto en 2 minutos.
    </p>
    
    <!-- H2 SEO (2-3 mínimo, 5-7 óptimo) -->
    <h2>¿Por qué necesitas un seguro de moto eléctrica especial?</h2>
    
    <!-- Contenido debe incluir: H3, imágenes, listas, intención usuario -->
    
    <!-- H2: Comparativa (mencionar competencia = relevancia SEO) -->
    <h2>Seguro Moto Eléctrica LD vs Competencia: ¿Por qué somos más baratos?</h2>
    
    <!-- Tabla comparativa (buen ranking para long-tail: "vs Allianz") -->
    
    <!-- H2: FAQPage Schema -->
    <h2>Preguntas Frecuentes sobre Seguro Moto Eléctrica</h2>
    
    <!-- cada FAQ = 1 <section> con Q+A -->
    <section itemscope itemtype="https://schema.org/Question">
        <h3 itemprop="name">¿Cubre daños a la batería?</h3>
        <div itemscope itemtype="https://schema.org/Answer">
            <p itemprop="text">Sí, nuestra cobertura...</p>
        </div>
    </section>
    
    <!-- CTA buttons (mínimo 3) -->
    <a href="..." class="btn btn-primary">Calcula tu presupuesto</a>
    <a href="tel:+34917706803" class="btn btn-secondary">Llámame gratis</a>
    
    <!-- Analytics -->
    <script async src="https://www.googletagmanager.com/gtag/js?id=GA_ID"></script>
</body>
</html>
```

---

## 🔐 CHECKLIST SEO TÉCNICO

### On-Page
- [ ] **Title Tag:** <60 chars, incluye keyword + brand
- [ ] **Meta Desc:** 155-160 chars, incluye keyword, CTAs, números
- [ ] **H1:** Único, incluye keyword, seguido de contenido relevante
- [ ] **H2s:** Mínimo 3 (máximo 7), usan keywords relacionadas
- [ ] **H3s:** Sous-titres de H2s, añaden profundidad
- [ ] **Keyword en primera 100 palabras:** Sí
- [ ] **Densidad keyword:** 1-2% (natural, no spam)
- [ ] **LSI keywords:** 5-7 variaciones semánticas mencionadas
- [ ] **Legibilidad:** Párrafos <4 líneas, frases claras

### Images
- [ ] **Imágenes:** Mínimo 3 (moto, coberturas, testimonial)
- [ ] **Alt text:** Descriptivo, incluye keyword 1x por image (máx)
- [ ] **Tamaño:** Optimizado para web (<200KB)
- [ ] **OG image:** 1200x630px (para social sharing)

### Internal Linking
- [ ] **Links internos:** 2-3 a otras páginas LD (natural)
- [ ] **Anchor text:** Descriptivo ("Seguro coche" no "click aquí")
- [ ] **No orphan pages:** Cada página linkada desde otra

### External Linking
- [ ] **Links externos:** 1-2 a autoridad alta (ej: noticia eléctricos)
- [ ] **Autoridad:** sitios .edu, .gov, o dominio de +30 años
- [ ] **Contexto:** Link relevante al contenido (no forzado)

### Schema Markup
- [ ] **FAQPage:** 10-15 QA pairs, válido en schema.org validator
- [ ] **LocalBusiness:** Nombre, teléfono, URL
- [ ] **BreadcrumbList:** Si hay categorías (opcional hier)
- [ ] **Validación:** https://schema.org/validator

### Technical
- [ ] **Canonical URL:** Present, no auto-generated slugs
- [ ] **Robots Meta:** index, follow (no noindex)
- [ ] **Hreflang:** Si hay versiones en otros idiomas (aqui no)
- [ ] **Viewport:** mobile responsive
- [ ] **Page Speed:** LCP <2.5s, CLS <0.1, INP <200ms

### Mobile
- [ ] **Responsive:** Design adapta tablets + mobile
- [ ] **Touch targets:** Botones >48x48px
- [ ] **Font size:** Mínimo 16px
- [ ] **Viewport meta tag:** Present

### Accessibility
- [ ] **Color contrast:** WCAG AA (4.5:1 text vs background)
- [ ] **Images alt text:** Todos tienen descripción
- [ ] **Formulario:** Labels claros, accessible
- [ ] **Keyboard nav:** Tab order lógico

---

## 🎨 CONTENIDO REQUERIDO

### Estructura Contenido
```
Intro (100-150 words)
├─ Hook: "¿Crónica de moto eléctrica?"
├─ Problem: "Batería + aseguradora = inseguridad"
├─ Solution: "LD cubre COMPLETO"
└─ CTA soft: "Ahora te mostramos cómo"

Section 1: Riesgos (250-300 words)
├─ H3: "Qué riesgos tiene una moto eléctrica"
├─ Punto 1: Batería (caro, crítico)
├─ Punto 2: Sistema eléctrico (diferente a gasolina)
└─ Punto 3: Carga pública (infraestructura nueva)

Section 2: Coberturas (300 words)
├─ H3: "Lo que cubre LD (y competencia no)"
├─ Tabla: LD vs otros
├─ Destacar: Batería, asistencia, jóvenes
└─ CTA: "Mira diferencias"

Section 3: Precio (200 words)
├─ H3: "¿Cuánto cuesta?"
├─ Statement: "Desde 12€/mes, más barato que gasolina"
├─ Factores: Edad, potencia, zona, historial
└─ Form: Calculadora presupuesto

Section 4: Comparativa (300 words)
├─ Tabla: LD vs AXA vs Allianz vs MAPFRE
├─ Nota: Precio + coberturas + servicio
└─ CTA: "Cambiarme a LD"

Section 5: FAQs (Expandible)
├─ 10-15 Q&As
├─ Cada Q: ~80-100 palabras respuesta
└─ Schema FAQPage embebido

Section 6: CTA Final (100 words)
├─ Resumen beneficios
├─ Social proof (ratings 9.2/10)
└─ 3 CTAs: Calc, llamar, área cliente
```

### Elementos Multimedia
- [ ] **Imagen 1:** Moto eléctrica moderna (hero)
- [ ] **Imagen 2:** Tabla/gráfico coberturas
- [ ] **Imagen 3:** Logo Línea Directa + rating eKomi
- [ ] **Video (opcional):** Cómo cambiarme a LD (~2 min)

---

## 📊 CONTENT METRICS

| Métrica | Target |
|---|---|
| **Word count** | 1,500-2,000 palabras |
| **H1 count** | Exactamente 1 |
| **H2 count** | 5-7 |
| **H3 count** | 2-3 per H2 (10-15 total) |
| **Imágenes** | 3-5 mínimo |
| **Internal links** | 2-3 |
| **External links** | 1-2 |
| **Lists** | 2-3 (bullet o numbered) |
| **Tables** | 1-2 (comparativa) |
| **Reading time** | 5-7 minutos |

---

## 🔗 INTERNAL LINKING MAP

Esta landing enlaza a:
```
/seguros/moto-electrica-barata/ (ESTA PÁGINA)
├─ → /seguros/moto/ (Pilar: Todos seguros moto)
├─ → /blog/moto-electrica-ventajas/ (Blog: context)
├─ → /area-cliente/ (CTA: Cambiarme)
└─ → /politica-privacidad/ (Footer: legal)

Que enlazan AQUÍ:
├─ /seguros/moto/ 
│   └─ "Moto eléctrica barata"
├─ /seguros/coche-electrico/
│   └─ "También aseguramos coches eléctricos"
└─ /blog/
    └─ "Seguro moto eléctrica: guía completa"
```

---

## 📋 VALIDACIÓN PRE-PUBLICACIÓN

### Dev Checklist
- [ ] HTML valida en W3C validator (sin errores)
- [ ] Lighthouse score ≥75 (Mobile + Desktop)
- [ ] Core Web Vitals verdes (LCP, CLS, INP)
- [ ] Mobile responsive (breakpoints: 320px, 768px, 1024px)
- [ ] Schema.org FAQPage valida en schema validator
- [ ] Imágenes optimizadas (<200KB)
- [ ] No 404s en links internos
- [ ] SSL certificado (HTTPS)
- [ ] Robots.txt permite página
- [ ] Sitemap.xml incluye URL

### SEO Checklist
- [ ] Keyword research validado
- [ ] Title Tag <60 chars
- [ ] Meta Desc 155-160 chars
- [ ] H1 único + keyword
- [ ] LSI keywords presentes
- [ ] Contenido 1,500-2,000 palabras
- [ ] FAQPage schema embebido
- [ ] Internal links (2-3)
- [ ] External links (1-2)
- [ ] Imágenes alt text (todos)

### Copy Checklist
- [ ] Tono directo (no jerga)
- [ ] Diferenciadores claros vs competencia
- [ ] CTAs claros (3 mínimo)
- [ ] Beneficios destacados
- [ ] Social proof (ratings, clientes)
- [ ] Calls to action botones verdes

---

## 🚀 DEPLOYMENT CHECKLIST

### Pre-Launch
- [ ] Testing en staging (no producción)
- [ ] Probar calculadora presupuesto (form)
- [ ] Probar links (internos + externos)
- [ ] A/B test: H1 copy? (opcional)

### Launch Day
- [ ] Publicar en producción
- [ ] Google Search Console: indexación manual pedida
- [ ] Google Analytics: tagging verificado
- [ ] Monitoreo 404s (primeras 24h)
- [ ] Slack alert si Lighthouse <75

### Post-Launch (Semana 1)
- [ ] Monitoring rankings: "seguro moto eléctrica barato"
- [ ] Pagespeed insights: monitoreo
- [ ] Conversion rate: forma presupuesto
- [ ] Bounce rate: <60%

---

## 📞 CONTACTOS RELEVANTES

- **Dev Lead:** [nombre] - HTML/CSS/JS
- **QA:** [nombre] - Validación Lighthouse
- **Product:** [nombre] - Cambios contenido
- **Marketing:** [nombre] - Copywriting final

---

**Creado por:** @seo-strategist (especificación)  
**Versión:** 1.0  
**Status:** Listo para @html-implementer

