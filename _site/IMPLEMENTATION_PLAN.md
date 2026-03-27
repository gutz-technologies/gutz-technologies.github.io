# Gutz Analytics Website - Implementation Plan

**Goal:** Build a professional, eye-catching website that positions Gutz Analytics as an established multi-omics AI platform with proven technology (scikit-bio) transitioning to clinical deployment.

**Timeline:** 2-3 weeks for complete redesign
**Tech Stack:** Jekyll (existing), Custom SCSS, Modern JavaScript for interactions

---

## Phase 1: Asset Collection & Design Preparation (Days 1-2)

### 1.1 Logos & Branding Assets

**Collect/Create:**
- [ ] **Gutz Analytics Logo** (if not already created)
  - SVG format for scalability
  - Both light and dark versions (for potential theme switching)
  - Multiple sizes: favicon (16x16, 32x32), header (150x60px), footer (smaller version)

- [ ] **Scikit-bio Logo**
  - Source: https://scikit.bio (check for downloadable assets or GitHub repo)
  - Get official logo for "Built on scikit-bio" badge
  - Request permission if needed for commercial use

- [ ] **Partner Institution Logos** (with permission)
  - NIAID logo (federal government - check usage guidelines)
  - NYU Langone Medical Center logo
  - University of Calgary logo
  - Format: PNG or SVG, transparent backgrounds

- [ ] **Nature Journal Logos**
  - Nature, Nature Neuroscience, Nature Methods, Nature Communications
  - Check Springer Nature brand guidelines for usage
  - Alternative: Simple text citations with journal colors

### 1.2 Background Images & Visual Elements

**Download/Source:**
- [ ] **Hero Section Background**
  - Option 1: Abstract biological/network visualization (royalty-free from Unsplash/Pexels)
  - Option 2: Custom-generated network diagram showing multi-omics connections
  - Recommended: Subtle, not overwhelming - let text be hero
  - Size: 1920x1080px minimum, optimized for web

- [ ] **Section Backgrounds**
  - Subtle textures or gradients
  - DNA helix, cell networks, data visualizations (abstract, not literal)
  - Low opacity overlays to maintain readability

- [ ] **Stock Photos** (if using human elements)
  - Avoid cheesy stock photos
  - Consider: Scientists at work, lab settings, data analysis screens
  - Sources: Unsplash (free, high quality), Pexels, or custom photography

**Recommended Free Image Sources:**
- Unsplash.com (search: "data visualization", "medical research", "laboratory")
- Pexels.com (similar search terms)
- Pixabay.com (CC0 license)

### 1.3 Icon Sets

**Download Icon Library:**
- [ ] **Feather Icons** or **Heroicons** (modern, clean, free)
  - Download: https://feathericons.com or https://heroicons.com
  - Use for: Technology pillars, application icons, navigation

- [ ] **Custom Icons Needed:**
  - Multi-omics integration (5 data streams merging)
  - Clinical decision support
  - Local deployment/security
  - Open-source/community

**Alternative:** Use Font Awesome Pro (paid) for medical/scientific icons

### 1.4 Color Palette Finalization

**Primary Colors:**
```scss
// Professional Blues (trust, medical, scientific)
$primary-blue: #1E3A8A;      // Deep blue
$primary-light: #3B82F6;     // Bright blue
$primary-dark: #1E293B;      // Nearly black blue

// Accent Colors
$accent-teal: #06B6D4;       // Data/tech accent
$accent-gold: #F59E0B;       // CTA buttons
$accent-green: #10B981;      // Success/validation

// Omics-specific (for diagrams)
$omics-microbiome: #10B981;  // Green
$omics-metabolome: #8B5CF6;  // Purple
$omics-proteome: #F97316;    // Orange
$omics-transcriptome: #3B82F6; // Blue
$omics-epigenome: #EC4899;   // Pink

// Neutrals
$gray-50: #F9FAFB;
$gray-100: #F3F4F6;
$gray-600: #4B5563;
$gray-900: #111827;
```

### 1.5 Typography System

**Font Selection:**
```scss
// Headings - Modern, professional, strong
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap');

// Body - Highly readable
$font-primary: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;

// Monospace (for code examples if needed)
$font-mono: 'Monaco', 'Courier New', monospace;

// Type Scale
$text-xs: 0.75rem;    // 12px
$text-sm: 0.875rem;   // 14px
$text-base: 1rem;     // 16px
$text-lg: 1.125rem;   // 18px
$text-xl: 1.25rem;    // 20px
$text-2xl: 1.5rem;    // 24px
$text-3xl: 1.875rem;  // 30px
$text-4xl: 2.25rem;   // 36px
$text-5xl: 3rem;      // 48px
```

---

## Phase 2: Custom Illustrations & Data Visualizations (Days 3-5)

### 2.1 Hero Multi-Omics Integration Diagram

**Requirements:**
- 5 data streams (microbiome, metabolome, proteome, transcriptome, epigenome)
- Flowing into unified AI model
- Output: patient stratification or treatment prediction
- Style: Clean, modern, not overly complex

**Tools/Options:**

**Option A: AI-Generated (Fastest)**
- Use Midjourney/DALL-E with prompt:
  ```
  "Clean scientific illustration showing 5 colored data streams
  (microbiome in green, metabolome in purple, proteome in orange,
  transcriptome in blue, epigenome in pink) flowing into a central
  AI neural network node, outputting to patient icons stratified
  into groups. Modern, minimalist, professional medical aesthetic,
  white background, vector style"
  ```
- Refine in Figma/Illustrator

**Option B: Custom Design in Figma (Best Quality)**
- Create from scratch using shapes and paths
- Export as SVG for web scalability
- Can be updated easily later

**Option C: Hire Designer (Fiverr/Upwork)**
- Budget: $50-150 for custom illustration
- Provide detailed brief from redesign plan
- Request SVG + PNG formats

### 2.2 Accuracy Scaling Curve (Data Visualization)

**Create Using:**
- Chart.js (JavaScript library) - interactive, responsive
- Or D3.js for more custom control
- Or static: Python matplotlib → export PNG/SVG

**Data to Visualize:**
```javascript
// Example data structure
const data = {
  labels: ['1 Omic', '2 Omics', '3 Omics', '4 Omics', '5+ Omics'],
  datasets: [{
    label: 'Prediction Accuracy',
    data: [65, 75, 82, 89, 94], // Example values - replace with real data
    borderColor: '#06B6D4',
    backgroundColor: 'rgba(6, 182, 212, 0.1)',
    tension: 0.4 // Smooth curve
  }]
}
```

**Implementation:**
```html
<canvas id="accuracyChart"></canvas>
<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
<script>
  // Chart implementation (see Phase 4)
</script>
```

### 2.3 4-Step Process Flow Diagram

**Design in Figma or PowerPoint:**
1. Step 1: Multi-Omics Data Analysis
2. Step 2: Build Disease-Specific Models
3. Step 3: Local Deployment
4. Step 4: Long-Term R&D Partnership

**Visual Style:**
- Horizontal flow (left to right)
- Icons for each step
- Connecting arrows with subtle animation on scroll
- Light background boxes with shadows

**Export:** SVG for crisp rendering

### 2.4 Application Icons

**Create/Source:**
- Treatment prediction: Stethoscope + AI chip icon
- Clinical trial: Clipboard with user icons
- Clinical decision: Brain with data nodes

**Tool:** Figma or Heroicons customization

### 2.5 Scikit-bio Integration Badge

**Design:**
- Badge-style graphic: "Powered by scikit-bio"
- Scikit-bio logo + Gutz Analytics connection
- Use on Platform page and footer
- Style: Similar to "Made with ❤️ in..." badges but professional

---

## Phase 3: Jekyll Site Structure Setup (Days 5-7)

### 3.1 File Structure

```
gutz-analytics.github.io/
├── _config.yml                 # Jekyll configuration
├── _layouts/
│   ├── default.html           # Base layout
│   ├── home.html              # Homepage layout
│   ├── page.html              # Standard page layout
│   ├── platform.html          # Platform page (custom)
│   └── science.html           # Science page (custom)
├── _includes/
│   ├── header.html            # Navigation header
│   ├── footer.html            # Footer with scikit-bio badge
│   ├── hero.html              # Hero section component
│   ├── cta.html               # Call-to-action component
│   ├── proof-points.html      # Proof points section
│   └── whitepaper-form.html   # Download form
├── _sass/
│   ├── _variables.scss        # Colors, fonts, spacing
│   ├── _typography.scss       # Text styles
│   ├── _components.scss       # Reusable components
│   ├── _sections.scss         # Homepage sections
│   ├── _layout.scss           # Grid, containers
│   └── main.scss              # Import all partials
├── assets/
│   ├── css/
│   │   └── style.scss         # Compiled CSS
│   ├── js/
│   │   ├── main.js            # Custom JavaScript
│   │   └── charts.js          # Chart.js visualizations
│   ├── images/
│   │   ├── logos/             # All logos
│   │   ├── backgrounds/       # Background images
│   │   ├── illustrations/     # Custom illustrations
│   │   ├── icons/             # Icon set
│   │   └── partners/          # Partner logos
│   └── downloads/
│       └── whitepaper.pdf     # Technical whitepaper
├── index.md                   # Homepage content
├── platform.md                # Platform page
├── applications.md            # Applications page
├── science.md                 # Science/publications page
├── about.md                   # About page
└── contact.md                 # Contact page
```

### 3.2 Update _config.yml

```yaml
title: 'Gutz Analytics'
description: 'Multi-Omics AI for Precision Medicine'
url: 'https://gutzanalytics.com'
baseurl: ''

# Logo configuration
logo:
  desktop: "assets/images/logos/gutz-analytics-logo.svg"
  mobile: "assets/images/logos/gutz-analytics-logo-small.svg"

# Navigation
navigation:
  main:
    - title: Platform
      url: /platform/
    - title: Applications
      url: /applications/
    - title: Science
      url: /science/
    - title: About
      url: /about/
    - title: Contact
      url: /contact/

# SEO
seo:
  title: "Gutz Analytics - Multi-Omics AI for Treatment Response Prediction"
  description: "Built on scikit-bio. Predict treatment response through multi-omics integration. De-risk Phase 3 trials with AI-powered companion diagnostics."
  keywords: "multi-omics, AI, precision medicine, companion diagnostics, treatment response, microbiome, scikit-bio"

# Social
social:
  linkedin: "company/gutz-analytics"  # Update with actual
  twitter: "@GutzAnalytics"           # Update with actual
  github: "scikit-bio/scikit-bio"     # Link to scikit-bio

# Analytics
google_analytics: "G-XXXXXXXXXX"      # Add GA4 tracking ID

# Build settings
permalink: pretty
plugins:
  - jekyll-seo-tag
  - jekyll-sitemap
```

### 3.3 Create Base Layout (_layouts/default.html)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>{{ page.title }} | {{ site.title }}</title>

  <!-- SEO -->
  {% seo %}

  <!-- Fonts -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">

  <!-- Styles -->
  <link rel="stylesheet" href="{{ '/assets/css/style.css' | relative_url }}">

  <!-- Favicon -->
  <link rel="icon" type="image/svg+xml" href="{{ '/assets/images/logos/favicon.svg' | relative_url }}">
</head>
<body class="{{ page.bodyClass }}">

  {% include header.html %}

  <main>
    {{ content }}
  </main>

  {% include footer.html %}

  <!-- Scripts -->
  <script src="{{ '/assets/js/main.js' | relative_url }}"></script>
  {% if page.charts %}
  <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
  <script src="{{ '/assets/js/charts.js' | relative_url }}"></script>
  {% endif %}

  <!-- Analytics -->
  {% if site.google_analytics %}
  <!-- Google Analytics code -->
  {% endif %}

</body>
</html>
```

---

## Phase 4: Homepage Implementation (Days 8-12)

### 4.1 Hero Section

**HTML Structure (index.md frontmatter + _includes/hero.html):**

```yaml
---
layout: home
title: "Multi-Omics AI for Precision Medicine"
hero:
  headline: "70% of patients don't respond to their first-line therapy"
  subheadline: "Current diagnostics can't predict treatment response. Phase 3 trials fail 50% of the time. The cost: billions in lost investment and millions of patients without effective treatment."
  solution: "Gutz Analytics builds AI models that approximate human biology through multi-omics integration—enabling precision prediction of treatment response before the prescription."
  cta_primary: "Download Whitepaper"
  cta_secondary: "Request Demo"
  background_image: "assets/images/backgrounds/hero-network.jpg"
---
```

**hero.html Component:**

```html
<section class="hero" style="background-image: url('{{ page.hero.background_image | relative_url }}')">
  <div class="hero__overlay"></div>
  <div class="container">
    <div class="hero__content">
      <div class="hero__text">
        <h1 class="hero__headline">{{ page.hero.headline }}</h1>
        <p class="hero__subheadline">{{ page.hero.subheadline }}</p>
        <p class="hero__solution">{{ page.hero.solution }}</p>
        <div class="hero__cta">
          <a href="#whitepaper" class="btn btn-primary">{{ page.hero.cta_primary }}</a>
          <a href="/contact/" class="btn btn-secondary">{{ page.hero.cta_secondary }}</a>
        </div>
      </div>
      <div class="hero__visual">
        <img src="{{ '/assets/images/illustrations/multi-omics-integration.svg' | relative_url }}" alt="Multi-omics integration diagram">
      </div>
    </div>
  </div>
</section>
```

**SCSS (_sass/_sections.scss):**

```scss
.hero {
  position: relative;
  min-height: 600px;
  display: flex;
  align-items: center;
  background-size: cover;
  background-position: center;
  background-attachment: fixed; // Parallax effect
  color: white;

  &__overlay {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: linear-gradient(
      135deg,
      rgba($primary-dark, 0.95) 0%,
      rgba($primary-blue, 0.85) 100%
    );
  }

  &__content {
    position: relative;
    z-index: 2;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 4rem;
    align-items: center;

    @media (max-width: 768px) {
      grid-template-columns: 1fr;
      gap: 2rem;
    }
  }

  &__headline {
    font-size: $text-5xl;
    font-weight: 700;
    line-height: 1.2;
    margin-bottom: 1.5rem;

    @media (max-width: 768px) {
      font-size: $text-3xl;
    }
  }

  &__subheadline {
    font-size: $text-lg;
    line-height: 1.6;
    margin-bottom: 1.5rem;
    opacity: 0.9;
  }

  &__solution {
    font-size: $text-xl;
    font-weight: 500;
    line-height: 1.6;
    margin-bottom: 2rem;
    padding-left: 1rem;
    border-left: 4px solid $accent-teal;
  }

  &__cta {
    display: flex;
    gap: 1rem;

    @media (max-width: 480px) {
      flex-direction: column;
    }
  }

  &__visual {
    img {
      width: 100%;
      height: auto;
      filter: drop-shadow(0 20px 40px rgba(0,0,0,0.3));
    }
  }
}

.btn {
  display: inline-block;
  padding: 1rem 2rem;
  font-size: $text-base;
  font-weight: 600;
  text-decoration: none;
  border-radius: 8px;
  transition: all 0.3s ease;
  text-align: center;

  &-primary {
    background: $accent-gold;
    color: white;

    &:hover {
      background: darken($accent-gold, 10%);
      transform: translateY(-2px);
      box-shadow: 0 10px 20px rgba($accent-gold, 0.3);
    }
  }

  &-secondary {
    background: transparent;
    color: white;
    border: 2px solid white;

    &:hover {
      background: white;
      color: $primary-blue;
    }
  }
}
```

### 4.2 Technology Platform Section (5 Pillars)

**HTML:**

```html
<section class="platform">
  <div class="container">
    <div class="section-header">
      <h2>Multi-Omics AI That Understands Biology</h2>
      <p>Traditional approaches analyze single data types in isolation. Gutz Analytics integrates orthogonal high-dimensional datasets—microbiome, metabolome, proteome, transcriptome, epigenome—to build models that approximate how human biology actually works.</p>
    </div>

    <div class="pillars">
      <div class="pillar">
        <div class="pillar__icon">
          <img src="{{ '/assets/images/icons/clinical-actionability.svg' | relative_url }}" alt="Clinical Actionability">
        </div>
        <h3 class="pillar__title">Clinical Actionability</h3>
        <p class="pillar__description">Predictions that directly inform clinical decisions—patient subtyping, pathway identification, and treatment selection</p>
      </div>

      <div class="pillar">
        <div class="pillar__icon">
          <img src="{{ '/assets/images/icons/orthogonality.svg' | relative_url }}" alt="Orthogonality Advantage">
        </div>
        <h3 class="pillar__title">Orthogonality Advantage</h3>
        <p class="pillar__description">Independent data sources yield exponential improvements. Our multi-omics approach outperforms single-omic methods by orders of magnitude</p>
      </div>

      <div class="pillar">
        <div class="pillar__icon">
          <img src="{{ '/assets/images/icons/biological-approximation.svg' | relative_url }}" alt="Biological Approximation">
        </div>
        <h3 class="pillar__title">Biological Approximation</h3>
        <p class="pillar__description">Models that represent biological mechanisms, not just statistical correlations. Predictions you can trust and understand</p>
      </div>

      <div class="pillar">
        <div class="pillar__icon">
          <img src="{{ '/assets/images/icons/local-deployment.svg' | relative_url }}" alt="Local Deployment">
        </div>
        <h3 class="pillar__title">Local Deployment</h3>
        <p class="pillar__description">Privacy-preserving AI trained on your proprietary data, deployed in your environment. No data sharing required</p>
      </div>

      <div class="pillar">
        <div class="pillar__icon">
          <img src="{{ '/assets/images/icons/scikit-bio.svg' | relative_url }}" alt="Battle-Tested Foundation">
        </div>
        <h3 class="pillar__title">Battle-Tested Foundation</h3>
        <p class="pillar__description">Built on <a href="https://scikit.bio" target="_blank" class="link-scikit-bio">scikit-bio</a>, our DOE-funded open-source platform with thousands of users worldwide—proven, reproducible, scientifically validated</p>
      </div>
    </div>

    <!-- Accuracy Scaling Chart -->
    <div class="chart-container">
      <h3>Exponential Accuracy Gains with Multi-Omics Integration</h3>
      <canvas id="accuracyChart"></canvas>
    </div>
  </div>
</section>
```

**SCSS:**

```scss
.platform {
  padding: 6rem 0;
  background: $gray-50;
}

.section-header {
  text-align: center;
  max-width: 800px;
  margin: 0 auto 4rem;

  h2 {
    font-size: $text-4xl;
    font-weight: 700;
    color: $primary-dark;
    margin-bottom: 1rem;
  }

  p {
    font-size: $text-lg;
    color: $gray-600;
    line-height: 1.7;
  }
}

.pillars {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 2rem;
  margin-bottom: 4rem;
}

.pillar {
  background: white;
  padding: 2rem;
  border-radius: 12px;
  box-shadow: 0 4px 6px rgba(0,0,0,0.05);
  transition: all 0.3s ease;

  &:hover {
    transform: translateY(-8px);
    box-shadow: 0 12px 24px rgba(0,0,0,0.1);
  }

  &__icon {
    width: 64px;
    height: 64px;
    margin-bottom: 1.5rem;

    img {
      width: 100%;
      height: 100%;
    }
  }

  &__title {
    font-size: $text-xl;
    font-weight: 600;
    color: $primary-blue;
    margin-bottom: 1rem;
  }

  &__description {
    font-size: $text-base;
    color: $gray-600;
    line-height: 1.6;
  }
}

.link-scikit-bio {
  color: $accent-teal;
  text-decoration: none;
  font-weight: 600;
  border-bottom: 2px solid transparent;
  transition: border-color 0.2s;

  &:hover {
    border-bottom-color: $accent-teal;
  }
}

.chart-container {
  max-width: 800px;
  margin: 0 auto;
  padding: 3rem;
  background: white;
  border-radius: 12px;
  box-shadow: 0 4px 6px rgba(0,0,0,0.05);

  h3 {
    text-align: center;
    font-size: $text-2xl;
    font-weight: 600;
    color: $primary-dark;
    margin-bottom: 2rem;
  }
}
```

### 4.3 JavaScript for Charts (assets/js/charts.js)

```javascript
document.addEventListener('DOMContentLoaded', function() {
  const ctx = document.getElementById('accuracyChart');

  if (ctx) {
    new Chart(ctx, {
      type: 'line',
      data: {
        labels: ['1 Omic', '2 Omics', '3 Omics', '4 Omics', '5+ Omics'],
        datasets: [{
          label: 'Prediction Accuracy (%)',
          data: [65, 75, 82, 89, 94], // Replace with actual data
          borderColor: '#06B6D4',
          backgroundColor: 'rgba(6, 182, 212, 0.1)',
          borderWidth: 3,
          tension: 0.4,
          fill: true,
          pointRadius: 6,
          pointHoverRadius: 8,
          pointBackgroundColor: '#06B6D4',
          pointBorderColor: '#fff',
          pointBorderWidth: 2
        }]
      },
      options: {
        responsive: true,
        maintainAspectRatio: true,
        plugins: {
          legend: {
            display: false
          },
          tooltip: {
            backgroundColor: '#1E293B',
            padding: 12,
            titleFont: {
              size: 14,
              weight: 'bold'
            },
            bodyFont: {
              size: 13
            },
            callbacks: {
              label: function(context) {
                return context.parsed.y + '% accuracy';
              }
            }
          }
        },
        scales: {
          y: {
            beginAtZero: true,
            max: 100,
            ticks: {
              callback: function(value) {
                return value + '%';
              }
            },
            grid: {
              color: '#F3F4F6'
            }
          },
          x: {
            grid: {
              display: false
            }
          }
        }
      }
    });
  }
});
```

### 4.4 Proof Points Section

```html
<section class="proof-points">
  <div class="container">
    <div class="section-header">
      <h2>Academic Validation Meets Clinical Deployment</h2>
    </div>

    <div class="proof-grid">
      <!-- Proof Point 1: Collaborations -->
      <div class="proof-card">
        <div class="proof-card__header">
          <h3>Active Research Collaborations</h3>
        </div>
        <ul class="proof-list">
          <li>
            <strong>NIAID:</strong> COVID-19 treatment response prediction
            <span class="status">Manuscript in submission</span>
          </li>
          <li>
            <strong>NYU Langone:</strong> Lung cancer immunotherapy response
            <span class="status">Manuscript in preparation</span>
          </li>
          <li>
            <strong>University of Calgary:</strong> UC patient stratification
            <span class="status">Analysis in progress</span>
          </li>
        </ul>
        <div class="partner-logos">
          <img src="{{ '/assets/images/partners/niaid-logo.png' | relative_url }}" alt="NIAID">
          <img src="{{ '/assets/images/partners/nyu-logo.png' | relative_url }}" alt="NYU Langone">
          <img src="{{ '/assets/images/partners/calgary-logo.png' | relative_url }}" alt="University of Calgary">
        </div>
      </div>

      <!-- Proof Point 2: Dataset -->
      <div class="proof-card">
        <div class="proof-card__header">
          <h3>Proprietary Multi-Omics Database</h3>
        </div>
        <div class="stat-highlight">
          <div class="stat-number">1,000,000+</div>
          <div class="stat-label">Curated Samples</div>
        </div>
        <ul class="proof-list">
          <li>5+ years of database curation and validation</li>
          <li>Spanning infectious disease, oncology, autoimmune, neurological disorders</li>
          <li>Validated across independent cohorts</li>
        </ul>
      </div>

      <!-- Proof Point 3: Publications & Platform -->
      <div class="proof-card">
        <div class="proof-card__header">
          <h3>Proven Platform with Global User Base</h3>
        </div>
        <div class="scikit-bio-highlight">
          <img src="{{ '/assets/images/logos/scikit-bio-logo.svg' | relative_url }}" alt="scikit-bio" class="scikit-logo">
          <p><strong>Thousands of active users worldwide</strong></p>
          <p>DOE-funded open-source platform</p>
        </div>
        <div class="publications">
          <h4>Nature Publications:</h4>
          <ul class="publication-list">
            <li><a href="https://www.nature.com/articles/s41593-023-01361-0" target="_blank">Nature Neuroscience (2023)</a></li>
            <li><a href="https://www.nature.com/articles/s41592-019-0616-3" target="_blank">Nature Methods (2019)</a></li>
            <li><a href="https://www.nature.com/articles/s41467-019-10656-5" target="_blank">Nature Communications (2019)</a></li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</section>
```

**SCSS:**

```scss
.proof-points {
  padding: 6rem 0;
  background: white;
}

.proof-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
  gap: 2rem;
}

.proof-card {
  background: $gray-50;
  border-radius: 12px;
  padding: 2.5rem;
  border: 2px solid transparent;
  transition: all 0.3s ease;

  &:hover {
    border-color: $accent-teal;
    box-shadow: 0 8px 16px rgba($accent-teal, 0.1);
  }

  &__header {
    margin-bottom: 1.5rem;

    h3 {
      font-size: $text-2xl;
      font-weight: 600;
      color: $primary-blue;
    }
  }
}

.proof-list {
  list-style: none;
  padding: 0;

  li {
    padding: 0.75rem 0;
    border-bottom: 1px solid lighten($gray-600, 40%);

    &:last-child {
      border-bottom: none;
    }

    strong {
      color: $primary-dark;
      font-weight: 600;
    }
  }
}

.status {
  display: inline-block;
  margin-left: 0.5rem;
  padding: 0.25rem 0.75rem;
  background: $accent-green;
  color: white;
  font-size: $text-xs;
  border-radius: 12px;
  font-weight: 600;
}

.partner-logos {
  display: flex;
  gap: 1.5rem;
  margin-top: 2rem;
  flex-wrap: wrap;

  img {
    height: 40px;
    width: auto;
    opacity: 0.7;
    transition: opacity 0.2s;

    &:hover {
      opacity: 1;
    }
  }
}

.stat-highlight {
  text-align: center;
  padding: 2rem;
  background: linear-gradient(135deg, $primary-blue, $accent-teal);
  border-radius: 8px;
  margin-bottom: 1.5rem;

  .stat-number {
    font-size: $text-5xl;
    font-weight: 700;
    color: white;
    line-height: 1;
  }

  .stat-label {
    font-size: $text-lg;
    color: rgba(white, 0.9);
    margin-top: 0.5rem;
  }
}

.scikit-bio-highlight {
  text-align: center;
  padding: 1.5rem;
  background: white;
  border-radius: 8px;
  margin-bottom: 1.5rem;

  .scikit-logo {
    height: 60px;
    margin-bottom: 1rem;
  }

  p {
    margin: 0.5rem 0;
    color: $gray-600;
  }
}

.publications {
  h4 {
    font-size: $text-lg;
    font-weight: 600;
    color: $primary-dark;
    margin-bottom: 1rem;
  }
}

.publication-list {
  list-style: none;
  padding: 0;

  li {
    padding: 0.5rem 0;

    a {
      color: $accent-teal;
      text-decoration: none;
      font-weight: 500;

      &:hover {
        text-decoration: underline;
      }
    }
  }
}
```

---

## Phase 5: Additional Pages (Days 13-15)

### 5.1 Platform Page (platform.md)

- Detailed technical content from redesign plan
- Lead with scikit-bio foundation
- Interactive elements if possible
- Link to scikit-bio documentation

### 5.2 Applications Page (applications.md)

- Expandable sections for each application
- Real research examples (NYU, NIAID, Calgary)
- Visual icons for each application type

### 5.3 Science Page (science.md)

- Full publication list with links
- Active research programs
- Collaboration map
- Downloadable PDFs or links to papers

### 5.4 Contact Page (contact.md)

- Clean contact form
- Multiple contact options
- "For Pharma" vs "For Investors" path selection

---

## Phase 6: Polish & Optimization (Days 16-18)

### 6.1 Mobile Responsiveness

**Test on:**
- [ ] iPhone (Safari)
- [ ] Android (Chrome)
- [ ] iPad (Safari)
- [ ] Various screen sizes (320px to 1920px)

**Key Checks:**
- [ ] Navigation hamburger menu works
- [ ] Hero section readable on mobile
- [ ] Charts render properly
- [ ] Forms are usable
- [ ] Touch targets are large enough (44x44px minimum)

### 6.2 Performance Optimization

**Images:**
```bash
# Install image optimization tools
npm install -g imagemin-cli imagemin-webp

# Optimize PNGs
imagemin assets/images/**/*.png --out-dir=assets/images --plugin=pngquant

# Convert to WebP for modern browsers
imagemin assets/images/**/*.{jpg,png} --out-dir=assets/images --plugin=webp
```

**Use responsive images:**
```html
<picture>
  <source srcset="image-large.webp" type="image/webp" media="(min-width: 1200px)">
  <source srcset="image-medium.webp" type="image/webp" media="(min-width: 768px)">
  <source srcset="image-small.webp" type="image/webp">
  <img src="image-fallback.jpg" alt="Description">
</picture>
```

**Lazy Loading:**
```html
<img src="image.jpg" loading="lazy" alt="Description">
```

### 6.3 SEO Optimization

**Add to each page frontmatter:**
```yaml
---
title: "Platform - Multi-Omics AI Integration"
description: "Built on scikit-bio. Learn how our multi-omics platform integrates microbiome, metabolome, proteome, transcriptome, and epigenome data."
keywords: "multi-omics, AI platform, scikit-bio, microbiome analysis"
og_image: "/assets/images/og-image-platform.jpg"
---
```

**Create Open Graph images** (1200x630px) for social sharing

**Install jekyll-seo-tag:**
```ruby
# Gemfile
gem 'jekyll-seo-tag'
```

### 6.4 Accessibility (a11y)

**Checklist:**
- [ ] All images have alt text
- [ ] Color contrast ratios meet WCAG AA (4.5:1 minimum)
- [ ] Keyboard navigation works throughout
- [ ] Focus indicators are visible
- [ ] Form labels are properly associated
- [ ] Heading hierarchy is logical (h1 → h2 → h3)
- [ ] ARIA labels where needed

**Test with:**
- Screen reader (VoiceOver on Mac, NVDA on Windows)
- Lighthouse audit in Chrome DevTools
- axe DevTools browser extension

---

## Phase 7: Whitepaper & Download Functionality (Days 18-19)

### 7.1 Create Technical Whitepaper

**Content Outline:**
1. Executive Summary
2. The Multi-Omics Imperative
3. Platform Architecture (scikit-bio foundation)
4. Methodology (DVAE, Factor-IV, etc.)
5. Validation Results
6. Case Studies (anonymized)
7. Deployment Options
8. Regulatory Considerations
9. Conclusion

**Design:**
- Professional PDF layout
- Branded with Gutz Analytics + scikit-bio mention
- Data visualizations
- Citations to Nature publications

**Tool:** LaTeX, Adobe InDesign, or Canva Pro

### 7.2 Implement Download Form

**Form HTML (_includes/whitepaper-form.html):**

```html
<div class="whitepaper-section" id="whitepaper">
  <div class="container">
    <div class="whitepaper-container">
      <div class="whitepaper-info">
        <h2>Download Our Technical Whitepaper</h2>
        <p>Deep dive into our multi-omics integration methodology, case studies, and deployment architecture.</p>
        <ul class="whitepaper-includes">
          <li>Multi-omics platform architecture</li>
          <li>Validation results across therapeutic areas</li>
          <li>Case studies with prediction improvements</li>
          <li>Technical specifications for local deployment</li>
        </ul>
      </div>

      <div class="whitepaper-form">
        <form id="downloadForm" action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
          <div class="form-group">
            <label for="name">Full Name *</label>
            <input type="text" id="name" name="name" required>
          </div>

          <div class="form-group">
            <label for="email">Email *</label>
            <input type="email" id="email" name="email" required>
          </div>

          <div class="form-group">
            <label for="organization">Organization *</label>
            <input type="text" id="organization" name="organization" required>
          </div>

          <div class="form-group">
            <label for="role">Role</label>
            <select id="role" name="role">
              <option value="">Select...</option>
              <option value="researcher">Researcher</option>
              <option value="clinician">Clinician</option>
              <option value="executive">Executive</option>
              <option value="investor">Investor</option>
              <option value="other">Other</option>
            </select>
          </div>

          <div class="form-group">
            <label for="therapeutic-area">Therapeutic Area of Interest</label>
            <select id="therapeutic-area" name="therapeutic_area">
              <option value="">Select...</option>
              <option value="oncology">Oncology</option>
              <option value="autoimmune">Autoimmune/Inflammatory</option>
              <option value="neurological">Neurological</option>
              <option value="infectious">Infectious Disease</option>
              <option value="other">Other</option>
            </select>
          </div>

          <button type="submit" class="btn btn-primary btn-block">Download Whitepaper</button>
        </form>
      </div>
    </div>
  </div>
</div>
```

**Form Service Options:**
- **Formspree** (easiest, free tier available)
- **Netlify Forms** (if hosting on Netlify)
- **Custom backend** with email notifications

**JavaScript for form handling (assets/js/main.js):**

```javascript
document.getElementById('downloadForm')?.addEventListener('submit', async function(e) {
  e.preventDefault();

  const formData = new FormData(this);
  const button = this.querySelector('button[type="submit"]');
  const originalText = button.textContent;

  button.textContent = 'Submitting...';
  button.disabled = true;

  try {
    const response = await fetch(this.action, {
      method: 'POST',
      body: formData,
      headers: {
        'Accept': 'application/json'
      }
    });

    if (response.ok) {
      // Success - trigger download
      window.location.href = '/assets/downloads/gutz-analytics-whitepaper.pdf';

      // Show success message
      this.innerHTML = '<p class="success-message">✓ Thank you! Your download will begin shortly.</p>';
    } else {
      throw new Error('Form submission failed');
    }
  } catch (error) {
    alert('There was an error. Please try again or contact us directly.');
    button.textContent = originalText;
    button.disabled = false;
  }
});
```

---

## Phase 8: Testing & Launch (Days 20-21)

### 8.1 Pre-Launch Checklist

**Content:**
- [ ] All copy is proofread and accurate
- [ ] Publication links work
- [ ] Partner names/logos have permission
- [ ] No placeholder text ("Lorem ipsum")
- [ ] Contact information is correct

**Technical:**
- [ ] All links work (no 404s)
- [ ] Forms submit successfully
- [ ] Images load properly
- [ ] Site works on all major browsers (Chrome, Firefox, Safari, Edge)
- [ ] Mobile responsive
- [ ] Page load time < 3 seconds
- [ ] SEO meta tags present
- [ ] Google Analytics installed and working
- [ ] Favicon displays correctly

**Legal:**
- [ ] Privacy policy page (if collecting emails)
- [ ] Cookie notice (if required by GDPR/CCPA)
- [ ] Copyright notice in footer
- [ ] Terms of use (optional but recommended)

### 8.2 Launch

**Steps:**
1. Final build: `bundle exec jekyll build`
2. Test built site in `_site/` directory
3. Commit all changes to git
4. Push to GitHub: `git push origin main`
5. Verify live site at gutzanalytics.com
6. Test contact forms on live site
7. Check Google Analytics is receiving data

### 8.3 Post-Launch

**Announce:**
- [ ] Update LinkedIn company page
- [ ] Post on relevant social media
- [ ] Email existing contacts/collaborators
- [ ] Reach out to scikit-bio community (mention the foundation)

**Monitor:**
- [ ] Google Analytics for traffic
- [ ] Form submissions
- [ ] Any error reports
- [ ] Page performance (Google PageSpeed Insights)

---

## Asset Download Checklist

### Required Downloads/Creation:

**Logos:**
- [ ] Gutz Analytics logo (SVG + PNG)
- [ ] Scikit-bio logo (from https://scikit.bio or GitHub)
- [ ] NIAID logo (check usage guidelines)
- [ ] NYU Langone logo (request permission)
- [ ] University of Calgary logo (request permission)
- [ ] Nature journal logos (check Springer Nature guidelines)

**Images:**
- [ ] Hero background image (network/biological visualization)
- [ ] Multi-omics integration illustration (custom or AI-generated)
- [ ] Section backgrounds (subtle textures)
- [ ] Team photos (if using About page)

**Icons:**
- [ ] Download Feather Icons or Heroicons pack
- [ ] Create custom icons for 5 technology pillars
- [ ] Application icons (treatment, trials, decision support)

**Fonts:**
- [ ] Inter (Google Fonts - already linked in code)

**Whitepaper:**
- [ ] Create PDF whitepaper document

---

## Quick Start Commands

```bash
# Install dependencies
bundle install

# Run local development server
bundle exec jekyll serve --watch --livereload

# Build for production
bundle exec jekyll build

# Test built site
cd _site && python -m http.server 8000
```

---

## Budget Estimate (Optional)

**If hiring help:**
- Custom illustrations: $100-300 (Fiverr/Upwork)
- Whitepaper design: $150-400 (if professional layout needed)
- Stock photos: $0 (using Unsplash) or $50-100 (premium)
- Total: $250-800

**DIY:** $0-50 (just tools/software if needed)

---

## Success Criteria

**Week 1 Post-Launch:**
- [ ] 50+ unique visitors
- [ ] 5+ whitepaper downloads
- [ ] 1+ demo request
- [ ] Average time on site > 2 minutes
- [ ] Bounce rate < 60%

**Month 1:**
- [ ] 200+ unique visitors
- [ ] 20+ whitepaper downloads
- [ ] 5+ qualified leads
- [ ] Positive feedback from at least one collaboration partner

---

This implementation plan is ready to execute. Start with Phase 1 (asset collection) and work through sequentially. The entire redesign can be completed in 2-3 weeks working part-time, or 1 week full-time.

Ready to start? Let me know which phase you want to tackle first, or if you need help with any specific section!
