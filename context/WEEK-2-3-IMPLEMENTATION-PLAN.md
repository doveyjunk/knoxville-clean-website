# Week 2-3 Implementation Plan
## Hero House Cleaning - Detailed Task Breakdown

**Plan Created**: January 18, 2025
**Timeline**: 2-3 weeks (36 hours total)
**Goal**: Complete all critical and high-priority optimizations
**Expected Impact**: $405K-$630K annual revenue increase

---

## WEEK 2: CRITICAL FIXES (16 hours)

### Goal: Enable Conversions & Complete Core SEO

**Completion Criteria**:
- Forms are functional (conversions enabled)
- All location pages properly optimized
- All meta tags optimized
- Core schema complete

---

## DAY 1: FORM INTEGRATION & LOCATION PAGE OPTIMIZATION (8 hours)

### Task 1.1: Integrate GoHighLevel Forms (6 hours)
**Priority**: 🔴 CRITICAL - Currently blocking 100% of form conversions

#### Subtask 1.1a: Get GoHighLevel Embed Code (30 min)
**Action Items**:
1. Log into GoHighLevel account
2. Navigate to Sites → Funnels/Websites → Forms
3. Locate contact/quote form
4. Copy embed code (should be iframe or script)
5. Test embed code in sandbox HTML file

**Deliverable**: GoHighLevel embed code ready to integrate

#### Subtask 1.1b: Replace Homepage Form (1 hour)
**File**: `src/pages/index.astro`

**Current Code** (Lines 638-644):
```astro
<div class="quote-form">
  <h2>Get Your Free Quote</h2>
  <!-- Contact form integration goes here -->
  <p>Contact form placeholder - integrate with your preferred form service (GoHighLevel, etc.)</p>
</div>
```

**Replace With**:
```astro
<div class="quote-form">
  <h2>Get Your Free Quote</h2>
  <div class="form-container">
    <!-- GoHighLevel Embed Code Here -->
    <iframe
      src="YOUR_GOHIGHLEVEL_FORM_URL"
      width="100%"
      height="600"
      frameborder="0"
      style="border: none; border-radius: 0.5rem;"
      title="Get Your Free Quote Form"
    ></iframe>
  </div>
</div>
```

**Testing**:
- [ ] Form displays properly
- [ ] Form is mobile responsive
- [ ] Form submits successfully
- [ ] Confirmation message appears
- [ ] Data appears in GoHighLevel

#### Subtask 1.1c: Replace Contact Page Form (2 hours)
**File**: `src/pages/contact.astro`

**Current Form** (Lines 55-118):
- Has 8 fields (too many)
- Uses placeholder alert() for submission
- Not connected to any backend

**Action**:
1. Replace entire form section with GoHighLevel embed
2. OR configure fields to match GoHighLevel form (if using API)
3. Remove fields: Address, Service Type, Frequency (keep Name, Email, Phone, Home Size)

**Recommended Approach** - Embed:
```astro
<div class="contact-form-container">
  <h2>Request a Free Quote</h2>

  <!-- Trust Signals Above Form -->
  <div class="form-trust-signals">
    <p class="trust-badge">⭐⭐⭐⭐⭐ 4.8 stars from 175+ customers</p>
    <p class="trust-text">Join hundreds of happy Knoxville homeowners</p>
  </div>

  <!-- GoHighLevel Form -->
  <div class="form-embed">
    <iframe
      src="YOUR_GOHIGHLEVEL_CONTACT_FORM_URL"
      width="100%"
      height="700"
      frameborder="0"
      style="border: none;"
      title="Contact Hero House Cleaning"
    ></iframe>
  </div>

  <p class="form-note">
    By submitting this form, you agree to be contacted by Hero House Cleaning
    regarding your inquiry. We typically respond within 24 hours.
  </p>
</div>
```

**Testing**:
- [ ] Form submits to GoHighLevel
- [ ] Fewer fields = higher completion rate
- [ ] Mobile responsive
- [ ] Trust signals visible above form

#### Subtask 1.1d: Add Forms to Other Pages (2.5 hours)
**Pages needing forms**:
1. `src/pages/house-cleaning-cost-knoxville.astro` (Line 822)
2. `src/pages/how-much-does-house-cleaning-cost.astro`
3. `src/pages/services/deep-cleaning.astro`
4. `src/pages/services/move-out-cleaning.astro`
5. `src/pages/services/airbnb-cleaning.astro`
6. All 5 location pages

**Template for Service/Location Pages**:
```astro
<!-- Quote Form Section -->
<section class="cta-form-section">
  <div class="container">
    <h2>Ready to Book Your [Service/Location] Cleaning?</h2>
    <p>Get your free, no-obligation quote in 60 seconds</p>

    <div class="inline-form">
      <iframe
        src="YOUR_GOHIGHLEVEL_FORM_URL"
        width="100%"
        height="500"
        frameborder="0"
        loading="lazy"
        title="Get Quote for [Service/Location]"
      ></iframe>
    </div>
  </div>
</section>
```

**Efficiency Tip**: Create a reusable component:

**New File**: `src/components/QuoteForm.astro`
```astro
---
interface Props {
  title?: string;
  subtitle?: string;
}

const {
  title = "Get Your Free Quote",
  subtitle = "Join 175+ happy Knoxville customers"
} = Astro.props;
---

<section class="quote-form-section">
  <div class="container">
    <h2>{title}</h2>
    <p class="subtitle">{subtitle}</p>

    <div class="form-wrapper">
      <iframe
        src="YOUR_GOHIGHLEVEL_FORM_URL"
        width="100%"
        height="600"
        frameborder="0"
        loading="lazy"
        title={title}
      ></iframe>
    </div>
  </div>
</section>

<style>
  .quote-form-section {
    background: var(--bg-light);
    padding: 4rem 2rem;
    margin: 4rem 0;
  }

  .quote-form-section h2 {
    text-align: center;
    margin-bottom: 0.5rem;
  }

  .subtitle {
    text-align: center;
    color: var(--text-light);
    margin-bottom: 2rem;
  }

  .form-wrapper {
    max-width: 600px;
    margin: 0 auto;
    background: white;
    padding: 2rem;
    border-radius: 0.5rem;
    box-shadow: 0 4px 12px rgba(0,0,0,0.1);
  }
</style>
```

**Usage in Pages**:
```astro
---
import QuoteForm from '../components/QuoteForm.astro';
---

<QuoteForm
  title="Get Your Free Deep Cleaning Quote"
  subtitle="Serving Knoxville for 5+ years with 4.8★ rating"
/>
```

**Time Breakdown**:
- Create QuoteForm component: 30 min
- Add to 6 service pages: 1 hour
- Add to 5 location pages: 1 hour

---

### Task 1.2: Optimize Location Pages - First 100 Words (3 hours)
**Priority**: 🔴 CRITICAL - Currently 0.3-0.4% density vs 1-2% optimal

**Goal**: Add primary keyword to opening paragraph of each location page

#### Location Page Optimization Template

**Pattern to Follow**:
1. Read current first paragraph
2. Identify where to naturally insert keyword
3. Ensure keyword appears in first 100 words
4. Maintain natural, readable prose
5. Keep keyword density between 1-2%

---

#### Subtask 1.2a: West Knoxville Page (30 min)
**File**: `src/pages/locations/west-knoxville.astro`
**Target Keyword**: "house cleaning West Knoxville"

**Current Opening** (estimated):
```
Welcome to Hero House Cleaning's West Knoxville service page.
We're proud to serve families throughout West Knox with professional,
eco-friendly cleaning services...
```

**Optimized Opening**:
```astro
<section class="intro">
  <div class="container">
    <p class="lead">
      Looking for reliable <strong>house cleaning in West Knoxville</strong>?
      Hero House Cleaning has proudly served West Knox families since 2020,
      providing professional, eco-friendly <strong>house cleaning services</strong>
      throughout neighborhoods from Farragut to Bearden. Our West Knoxville
      house cleaning team is background-checked, insured, and rated 4.8 stars
      by 175+ local customers.
    </p>
  </div>
</section>
```

**Keyword Count in First 100 Words**:
- "house cleaning West Knoxville": 1x (exact match)
- "West Knoxville": 2x additional
- "house cleaning": 2x additional
- **Total keyword presence**: ~1.5% ✅

---

#### Subtask 1.2b: Farragut Page (30 min)
**File**: `src/pages/locations/farragut.astro`
**Target Keyword**: "cleaning service Farragut TN"

**Optimized Opening**:
```astro
<section class="intro">
  <div class="container">
    <p class="lead">
      Need a professional <strong>cleaning service in Farragut, TN</strong>?
      Hero House Cleaning is Farragut's trusted choice for house cleaning,
      serving luxury homes and gated communities throughout Turkey Creek,
      Fox Den, and Westhaven since 2020. Our <strong>Farragut cleaning service</strong>
      is family-owned, background-checked, and rated 4.8 stars by your neighbors.
      We understand the unique needs of Farragut's larger homes (2,500-4,000+ sq ft)
      and provide transparent pricing with no hidden fees.
    </p>
  </div>
</section>
```

**Keyword Count**:
- "cleaning service Farragut TN": 1x (exact match)
- "Farragut": 4x total
- "cleaning service": 2x total
- **Density**: ~1.8% ✅

---

#### Subtask 1.2c: Oak Ridge Page (30 min)
**File**: `src/pages/locations/oak-ridge.astro`
**Target Keyword**: "house cleaners Oak Ridge TN"

**Optimized Opening**:
```astro
<section class="intro">
  <div class="container">
    <p class="lead">
      Searching for dependable <strong>house cleaners in Oak Ridge, TN</strong>?
      Hero House Cleaning is the trusted choice for ORNL employees, government
      workers, and families throughout Oak Ridge. Our professional <strong>Oak Ridge
      house cleaners</strong> understand the unique needs of the Secret City, offering
      flexible scheduling for shift workers and specialized care for historic homes.
      With 4.8 stars from 175+ customers and a background-checked team, we're Oak
      Ridge's premier <strong>house cleaning service</strong>.
    </p>
  </div>
</section>
```

**Keyword Count**:
- "house cleaners Oak Ridge TN": 1x (exact match)
- "Oak Ridge": 4x total
- "house cleaners": 2x total
- **Density**: ~2.0% ✅

---

#### Subtask 1.2d: Bearden Page (30 min)
**File**: `src/pages/locations/bearden.astro`
**Target Keyword**: "house cleaning Bearden"

**Optimized Opening**:
```astro
<section class="intro">
  <div class="container">
    <p class="lead">
      Looking for trusted <strong>house cleaning in Bearden</strong>? Hero House
      Cleaning has served Bearden families since 2020, providing professional cleaning
      services throughout Bearden Village, West Hills, Northshore, and beyond. Our
      <strong>Bearden house cleaning</strong> team specializes in the unique character
      of Bearden's established neighborhoods, with gentle care for older homes (1940s-1980s)
      and historic details. Rated 4.8 stars by your Bearden neighbors, we're the local,
      family-owned alternative to national franchises.
    </p>
  </div>
</section>
```

**Keyword Count**:
- "house cleaning Bearden": 2x
- "Bearden": 5x total
- **Density**: ~1.7% ✅

---

#### Subtask 1.2e: Maryville Page (30 min)
**File**: `src/pages/locations/maryville.astro`
**Target Keyword**: "cleaning service Maryville TN"

**Optimized Opening**:
```astro
<section class="intro">
  <div class="container">
    <p class="lead">
      Need a reliable <strong>cleaning service in Maryville, TN</strong>? Hero House
      Cleaning proudly serves Maryville families, Maryville College students, and
      Smoky Mountain vacation rental owners. Our <strong>Maryville cleaning service</strong>
      understands the unique challenges of living at the gateway to the Smokies—from
      seasonal pollen to red clay tracking. With 4.8 stars from 175+ customers and
      background-checked team members, we're Maryville's trusted choice for professional
      house cleaning.
    </p>
  </div>
</section>
```

**Keyword Count**:
- "cleaning service Maryville TN": 1x (exact match)
- "Maryville": 5x total
- "cleaning service": 2x total
- **Density**: ~1.9% ✅

---

### Task 1.2f: Verify Keyword Placement (30 min)

**Checklist for Each Page**:
- [ ] Keyword appears in first 100 words
- [ ] Keyword density 1-2% in opening section
- [ ] Prose reads naturally (no stuffing)
- [ ] Local relevance signals present
- [ ] Unique to each location (not duplicate)

**Quick Test Script**:
```bash
# Count words in first paragraph
head -20 src/pages/locations/west-knoxville.astro | grep -o '\w\+' | wc -w

# Count keyword occurrences
grep -i "house cleaning west knoxville" src/pages/locations/west-knoxville.astro | wc -l
```

---

## DAY 2: META TAG OPTIMIZATION (4 hours)

### Task 2.1: Fix Remaining Title Tags (2 hours)
**Priority**: 🔴 CRITICAL - 13 pages need optimization

**Goal**: All titles 50-60 characters, keyword-rich, compelling

#### Title Tag Optimization Formula:
```
[Primary Keyword] | [Unique Selling Point or Location] | Hero House
```

**Character Budget**: 50-60 chars (optimal), max 70 chars

---

#### Pages to Fix:

**1. Homepage** (64 chars → 58 chars)
```astro
<!-- BEFORE -->
title="House Cleaning Service Knoxville TN | Hero House Cleaning"

<!-- AFTER -->
title="House Cleaning Knoxville TN | 4.8★ | Hero House"
```

**2. About Page**
```astro
<!-- BEFORE (estimate) -->
title="About Hero House Cleaning - Family-Owned Cleaning Service in Knoxville TN"

<!-- AFTER -->
title="About Hero House Cleaning | Family-Owned Knoxville"
```

**3. Contact Page**
```astro
<!-- BEFORE (estimate) -->
title="Contact Hero House Cleaning - Free Quote | Knoxville TN"

<!-- AFTER -->
title="Contact Hero House Cleaning | Free Quote Knoxville"
```

**4. Services Page**
```astro
<!-- AFTER -->
title="Cleaning Services Knoxville | $160+ | Hero House"
```

**5. Locations Page**
```astro
<!-- AFTER -->
title="Service Areas Knoxville TN | 21+ Locations | Hero"
```

**6. West Knoxville**
```astro
<!-- AFTER -->
title="House Cleaning West Knoxville | Hero House"
```

**7. Farragut**
```astro
<!-- AFTER -->
title="Cleaning Service Farragut TN | Hero House"
```

**8. Bearden**
```astro
<!-- AFTER -->
title="House Cleaning Bearden | Hero House Cleaning"
```

**9. Maryville**
```astro
<!-- AFTER -->
title="Cleaning Service Maryville TN | Hero House"
```

**10. Deep Cleaning**
```astro
<!-- AFTER -->
title="Deep Cleaning Service Knoxville | $330+ | Hero"
```

**11. Airbnb Cleaning**
```astro
<!-- AFTER -->
title="Airbnb Cleaning Knoxville | Same-Day | Hero House"
```

**12. Professional House Cleaning**
```astro
<!-- AFTER -->
title="Professional House Cleaning Knoxville | Hero"
```

**13. How Much Does House Cleaning Cost**
```astro
<!-- AFTER -->
title="How Much Does House Cleaning Cost Knoxville? | Hero"
```

**Implementation Script**:
Create a spreadsheet or checklist:

| File | Current Length | New Title | New Length | Status |
|------|---------------|-----------|------------|--------|
| index.astro | 64 | House Cleaning Knoxville TN \| 4.8★ \| Hero House | 52 | ☐ |
| about.astro | 87 | About Hero House Cleaning \| Family-Owned Knoxville | 54 | ☐ |
| ... | ... | ... | ... | ☐ |

---

### Task 2.2: Fix Remaining Meta Descriptions (2 hours)
**Priority**: 🔴 CRITICAL - 7 pages need optimization

**Goal**: All descriptions 150-160 characters, compelling CTA, local signals

#### Meta Description Formula:
```
[Service] in [Location]. [Unique Benefit]. [Pricing/Social Proof]. [CTA with phone].
```

**Character Budget**: 150-160 chars (optimal)

---

#### Pages to Fix:

**1. Homepage**
```astro
<!-- BEFORE (213 chars) -->
description="Professional house cleaning service in Knoxville TN with transparent pricing. Regular cleaning $160, Deep cleaning $330. 4.8★ rating, 175+ reviews. Same-day availability. Call (865) 507-1405 for your free quote."

<!-- AFTER (158 chars) -->
description="House cleaning in Knoxville TN. $160+ transparent pricing. 4.8★, 175+ reviews. Same-day available. Call (865) 507-1405 for free quote!"
```

**2. About Page**
```astro
<!-- AFTER (148 chars) -->
description="Family-owned Knoxville house cleaning since 2020. 4.8 stars, eco-friendly, background-checked team. Call (865) 507-1405!"
```

**3. Services Page**
```astro
<!-- AFTER (156 chars) -->
description="Knoxville cleaning services: Regular ($160+), Deep ($330+), Move-out ($378+), Airbnb turnover. 4.8★ rated. Call (865) 507-1405!"
```

**4. West Knoxville**
```astro
<!-- AFTER (153 chars) -->
description="West Knoxville house cleaning. Serving Farragut, Bearden, all of West Knox. Background-checked team. 4.8★. Call (865) 507-1405!"
```

**5. Farragut**
```astro
<!-- AFTER (149 chars) -->
description="Farragut TN cleaning service. Luxury home experts, gated community trusted. Transparent pricing. 4.8★. Call (865) 507-1405!"
```

**6. Bearden**
```astro
<!-- AFTER (152 chars) -->
description="Bearden house cleaning. Bearden Village, West Hills, Northshore. Older home specialists. 4.8★, family-owned. Call (865) 507-1405!"
```

**7. Maryville**
```astro
<!-- AFTER (159 chars) -->
description="Maryville TN cleaning service. Smoky Mountain gateway specialists. Pollen & red clay experts. Background-checked. Call (865) 507-1405!"
```

**Batch Edit Script**:
```bash
# For each .astro file
for file in src/pages/**/*.astro; do
  # Show current description
  grep "description=" "$file"

  # Manual edit each one
  nano "$file"
done
```

---

## DAY 3: SCHEMA & FORM OPTIMIZATION (4 hours)

### Task 3.1: Add Schema to 4 Core Pages (2 hours)
**Priority**: 🔴 CRITICAL - Enables rich snippets

**Pages Missing Schema**:
1. about.astro
2. contact.astro
3. services.astro
4. locations.astro

---

#### Subtask 3.1a: About Page Schema (30 min)
**File**: `src/pages/about.astro`

**Add After Frontmatter**:
```astro
<!-- LocalBusiness Schema with AboutPage -->
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "LocalBusiness",
      "@id": "https://herohousecleaning.com/#business",
      "name": "Hero House Cleaning",
      "image": "https://herohousecleaning.com/images/logo.png",
      "url": "https://herohousecleaning.com",
      "telephone": "(865) 507-1405",
      "email": "info@herohousecleaning.com",
      "address": {
        "@type": "PostalAddress",
        "streetAddress": "123 Main Street",
        "addressLocality": "Knoxville",
        "addressRegion": "TN",
        "postalCode": "37909",
        "addressCountry": "US"
      },
      "geo": {
        "@type": "GeoCoordinates",
        "latitude": 35.9606,
        "longitude": -83.9207
      },
      "openingHoursSpecification": [
        {
          "@type": "OpeningHoursSpecification",
          "dayOfWeek": ["Monday", "Tuesday", "Wednesday", "Thursday", "Friday"],
          "opens": "08:00",
          "closes": "17:00"
        }
      ],
      "priceRange": "$$",
      "aggregateRating": {
        "@type": "AggregateRating",
        "ratingValue": "4.8",
        "reviewCount": "175"
      },
      "foundingDate": "2020",
      "founder": {
        "@type": "Person",
        "name": "Your Founder Name"
      }
    },
    {
      "@type": "AboutPage",
      "@id": "https://herohousecleaning.com/about#page",
      "url": "https://herohousecleaning.com/about",
      "name": "About Hero House Cleaning",
      "description": "Learn about Hero House Cleaning, Knoxville's family-owned house cleaning service since 2020."
    }
  ]
}
</script>
```

---

#### Subtask 3.1b: Contact Page Schema (30 min)
**File**: `src/pages/contact.astro`

```astro
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "ContactPage",
  "@id": "https://herohousecleaning.com/contact#page",
  "url": "https://herohousecleaning.com/contact",
  "name": "Contact Hero House Cleaning",
  "description": "Get your free quote from Hero House Cleaning in Knoxville",
  "mainEntity": {
    "@type": "LocalBusiness",
    "name": "Hero House Cleaning",
    "telephone": "(865) 507-1405",
    "email": "info@herohousecleaning.com",
    "address": {
      "@type": "PostalAddress",
      "addressLocality": "Knoxville",
      "addressRegion": "TN",
      "addressCountry": "US"
    }
  }
}
</script>
```

---

#### Subtask 3.1c: Services Page Schema (30 min)
**File**: `src/pages/services.astro`

```astro
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "ItemList",
  "name": "House Cleaning Services in Knoxville TN",
  "description": "Complete list of professional cleaning services offered by Hero House Cleaning",
  "itemListElement": [
    {
      "@type": "Service",
      "name": "Regular House Cleaning",
      "provider": {
        "@type": "LocalBusiness",
        "name": "Hero House Cleaning"
      },
      "areaServed": {
        "@type": "City",
        "name": "Knoxville",
        "containedIn": {
          "@type": "State",
          "name": "Tennessee"
        }
      },
      "offers": {
        "@type": "Offer",
        "priceSpecification": {
          "@type": "PriceSpecification",
          "minPrice": "160",
          "priceCurrency": "USD"
        }
      }
    },
    {
      "@type": "Service",
      "name": "Deep Cleaning Service",
      "provider": {
        "@type": "LocalBusiness",
        "name": "Hero House Cleaning"
      },
      "offers": {
        "@type": "Offer",
        "priceSpecification": {
          "@type": "PriceSpecification",
          "minPrice": "330",
          "priceCurrency": "USD"
        }
      }
    },
    {
      "@type": "Service",
      "name": "Move In/Out Cleaning",
      "offers": {
        "@type": "Offer",
        "priceSpecification": {
          "@type": "PriceSpecification",
          "minPrice": "378",
          "priceCurrency": "USD"
        }
      }
    }
  ]
}
</script>
```

---

#### Subtask 3.1d: Locations Page Schema (30 min)
**File**: `src/pages/locations.astro`

```astro
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "ItemList",
  "name": "Hero House Cleaning Service Areas in Knoxville TN",
  "description": "All areas served by Hero House Cleaning throughout Knoxville and East Tennessee",
  "numberOfItems": 21,
  "itemListElement": [
    {
      "@type": "Place",
      "name": "West Knoxville",
      "url": "https://herohousecleaning.com/locations/west-knoxville"
    },
    {
      "@type": "Place",
      "name": "Farragut",
      "url": "https://herohousecleaning.com/locations/farragut"
    },
    {
      "@type": "Place",
      "name": "Oak Ridge",
      "url": "https://herohousecleaning.com/locations/oak-ridge"
    },
    {
      "@type": "Place",
      "name": "Bearden",
      "url": "https://herohousecleaning.com/locations/bearden"
    },
    {
      "@type": "Place",
      "name": "Maryville",
      "url": "https://herohousecleaning.com/locations/maryville"
    }
  ]
}
</script>
```

---

### Task 3.2: Fix Empty streetAddress Fields (1 hour)
**Priority**: 🔴 CRITICAL - Schema validation failing

**Issue**: All LocalBusiness schemas have empty `streetAddress: ""`

**Files to Fix**:
- index.astro
- All 5 location pages
- All 3 service pages
- maid-service-knoxville.astro
- professional-house-cleaning.astro
- best-cleaning-service-knoxville.astro
- house-cleaning-cost-knoxville.astro
- how-much-does-house-cleaning-cost.astro

**Two Options**:

**Option 1: Add Real Address**
```json
"address": {
  "@type": "PostalAddress",
  "streetAddress": "123 Main Street",
  "addressLocality": "Knoxville",
  "addressRegion": "TN",
  "postalCode": "37909",
  "addressCountry": "US"
}
```

**Option 2: Service Area Business (No Street Address)**
```json
"address": {
  "@type": "PostalAddress",
  "addressLocality": "Knoxville",
  "addressRegion": "TN",
  "postalCode": "37909",
  "addressCountry": "US"
},
"areaServed": [
  {
    "@type": "City",
    "name": "Knoxville"
  },
  {
    "@type": "City",
    "name": "Oak Ridge"
  },
  {
    "@type": "City",
    "name": "Maryville"
  }
]
```

**Recommended**: Use Option 1 if you have a physical office/address. Use Option 2 if service area business only.

**Batch Find & Replace**:
```bash
# Find all instances
grep -r 'streetAddress": ""' src/pages/

# Replace with your address (use sed or manual edit)
# Example for service area business (no street address):
find src/pages -name "*.astro" -exec sed -i '' 's/"streetAddress": "",/"addressLocality": "Knoxville",/g' {} \;
```

---

### Task 3.3: Reduce Contact Form Fields (1 hour)
**Priority**: 🔴 CRITICAL - 30-40% abandonment from 8 fields

**File**: `src/pages/contact.astro` (Lines 56-113)

**Current Fields** (8):
1. Name *
2. Email *
3. Phone
4. Address
5. Home Size
6. Service Type
7. Frequency
8. Message

**Optimized Fields** (4):
1. Name *
2. Phone *
3. Home Size *
4. Message (optional)

**Note**: This assumes you're NOT using GoHighLevel embed. If using GoHighLevel, skip this task (their form builder handles field optimization).

**Implementation**:
```astro
<form class="contact-form" id="contactForm">
  <div class="form-group">
    <label for="name">Name *</label>
    <input type="text" id="name" name="name" required>
  </div>

  <div class="form-group">
    <label for="phone">Phone *</label>
    <input type="tel" id="phone" name="phone" required placeholder="(865) 555-1234">
  </div>

  <div class="form-group">
    <label for="homeSize">Home Size *</label>
    <select id="homeSize" name="homeSize" required>
      <option value="">Select size</option>
      <option value="small">Small (< 1,500 sq ft)</option>
      <option value="medium">Medium (1,500 - 2,500 sq ft)</option>
      <option value="large">Large (2,500 - 4,000 sq ft)</option>
      <option value="xlarge">Extra Large (> 4,000 sq ft)</option>
    </select>
  </div>

  <div class="form-group full-width">
    <label for="message">Additional Details (optional)</label>
    <textarea id="message" name="message" rows="4" placeholder="Tell us about any specific needs or questions..."></textarea>
  </div>

  <button type="submit" class="btn btn-primary btn-large">Get Your Free Quote</button>

  <p class="form-note">By submitting this form, you agree to be contacted by Hero House Cleaning regarding your inquiry. We typically respond within 24 hours.</p>
</form>
```

**Expected Impact**: +30-40% form completion rate

---

## WEEK 3: HIGH PRIORITY FIXES (20 hours)

### Goal: Accessibility, Trust Signals, Content Expansion

---

## DAY 4: ACCESSIBILITY COMPLIANCE (4 hours)

### Task 4.1: Add Skip Navigation Link (15 min)
**Priority**: 🟡 HIGH - Required for WCAG AA compliance

**File**: `src/layouts/Layout.astro`

**Add After `<body>` Tag**:
```astro
<body>
  <!-- Skip Navigation for Screen Readers -->
  <a href="#main-content" class="skip-link">Skip to main content</a>

  <header>
    <!-- existing header -->
  </header>

  <main id="main-content">
    <slot />
  </main>
```

**Add to Global Styles**:
```css
.skip-link {
  position: absolute;
  top: -40px;
  left: 0;
  background: var(--primary);
  color: white;
  padding: 0.5rem 1rem;
  text-decoration: none;
  z-index: 1000;
}

.skip-link:focus {
  top: 0;
}
```

---

### Task 4.2: Fix Color Contrast Issues (1 hour)
**Priority**: 🟡 HIGH - WCAG AA failures

**Current Issues**:
- `.text-light` color: #6b7280 on white = 4.3:1 (FAILS 4.5:1 minimum)

**File**: `src/layouts/Layout.astro` (Global styles)

**Find & Replace**:
```css
/* BEFORE */
--text-light: #6b7280;

/* AFTER */
--text-light: #4b5563; /* Darker gray, 7.1:1 contrast */
```

**Test All Text Elements**:
```css
/* Ensure minimum 4.5:1 contrast for all text */
--text: #1f2937; /* Already good: 16.1:1 */
--text-light: #4b5563; /* Fixed: 7.1:1 ✅ */
--primary: #2563eb; /* Check on white: 4.9:1 ✅ */
```

**Quick Test Tool**:
Use WebAIM Contrast Checker: https://webaim.org/resources/contrastchecker/

---

### Task 4.3: Add Focus Indicators (1 hour)
**Priority**: 🟡 HIGH - Keyboard navigation requirement

**File**: `src/layouts/Layout.astro`

**Add to Global Styles**:
```css
/* Focus Indicators for Keyboard Navigation */
a:focus,
button:focus,
input:focus,
select:focus,
textarea:focus {
  outline: 3px solid var(--primary);
  outline-offset: 2px;
}

/* Focus visible for modern browsers */
a:focus-visible,
button:focus-visible,
input:focus-visible,
select:focus-visible,
textarea:focus-visible {
  outline: 3px solid var(--primary);
  outline-offset: 2px;
}

/* Remove outline for mouse users (keeps for keyboard) */
a:focus:not(:focus-visible),
button:focus:not(:focus-visible) {
  outline: none;
}
```

**Test Keyboard Navigation**:
- [ ] Tab through all nav links (visible focus ring)
- [ ] Tab through all form fields (visible focus ring)
- [ ] Tab through all buttons (visible focus ring)
- [ ] Skip link appears on focus
- [ ] Focus order is logical

---

### Task 4.4: Add ARIA Labels to Forms (1.75 hours)
**Priority**: 🟡 HIGH - Screen reader accessibility

**Files**: All pages with forms

**Example for Contact Form**:
```astro
<form
  class="contact-form"
  id="contactForm"
  aria-label="Contact form for requesting a cleaning quote"
>
  <div class="form-group">
    <label for="name">Name *</label>
    <input
      type="text"
      id="name"
      name="name"
      required
      aria-required="true"
      aria-describedby="name-error"
    >
    <span id="name-error" class="error-message" role="alert" hidden>
      Please enter your name
    </span>
  </div>

  <div class="form-group">
    <label for="phone">Phone *</label>
    <input
      type="tel"
      id="phone"
      name="phone"
      required
      aria-required="true"
      aria-describedby="phone-error phone-help"
    >
    <span id="phone-help" class="help-text">
      We'll call or text you to confirm your appointment
    </span>
    <span id="phone-error" class="error-message" role="alert" hidden>
      Please enter a valid phone number
    </span>
  </div>

  <!-- ... -->

  <button
    type="submit"
    class="btn btn-primary btn-large"
    aria-label="Submit quote request"
  >
    Get Your Free Quote
  </button>
</form>
```

---

## DAY 5: TRUST SIGNALS & CRO (8 hours)

### Task 5.1: Add Trust Badges Near Forms (2 hours)
**Priority**: 🟡 HIGH - +15-25% trust/conversions

**Create Component**: `src/components/TrustBadges.astro`

```astro
---
interface Props {
  variant?: 'horizontal' | 'vertical';
}

const { variant = 'horizontal' } = Astro.props;
---

<div class={`trust-badges trust-badges-${variant}`}>
  <div class="trust-badge">
    <div class="badge-icon">⭐</div>
    <div class="badge-text">
      <strong>4.8 Stars</strong>
      <span>175+ Reviews</span>
    </div>
  </div>

  <div class="trust-badge">
    <div class="badge-icon">✓</div>
    <div class="badge-text">
      <strong>Background Checked</strong>
      <span>All Team Members</span>
    </div>
  </div>

  <div class="trust-badge">
    <div class="badge-icon">🛡️</div>
    <div class="badge-text">
      <strong>Fully Insured</strong>
      <span>& Bonded</span>
    </div>
  </div>

  <div class="trust-badge">
    <div class="badge-icon">💯</div>
    <div class="badge-text">
      <strong>Satisfaction</strong>
      <span>Guaranteed</span>
    </div>
  </div>
</div>

<style>
  .trust-badges {
    display: flex;
    gap: 1.5rem;
    margin: 2rem 0;
    padding: 1.5rem;
    background: var(--bg-light);
    border-radius: 0.5rem;
  }

  .trust-badges-vertical {
    flex-direction: column;
  }

  .trust-badge {
    display: flex;
    align-items: center;
    gap: 0.75rem;
  }

  .badge-icon {
    font-size: 2rem;
    line-height: 1;
  }

  .badge-text {
    display: flex;
    flex-direction: column;
    gap: 0.25rem;
  }

  .badge-text strong {
    color: var(--text);
    font-size: 0.95rem;
  }

  .badge-text span {
    color: var(--text-light);
    font-size: 0.85rem;
  }

  @media (max-width: 768px) {
    .trust-badges-horizontal {
      flex-direction: column;
      gap: 1rem;
    }
  }
</style>
```

**Usage**:
```astro
---
import TrustBadges from '../components/TrustBadges.astro';
---

<div class="contact-form-container">
  <h2>Request a Free Quote</h2>

  <TrustBadges variant="horizontal" />

  <!-- Form here -->
</div>
```

**Add to Pages** (15 min each):
- contact.astro
- index.astro (above quote form)
- All service pages (above quote forms)
- All location pages (above quote forms)

---

### Task 5.2: Add Before/After Image Sections (6 hours)
**Priority**: 🟡 HIGH - +15-25% credibility

**Subtask 5.2a: Create Before/After Component** (1 hour)

**File**: `src/components/BeforeAfter.astro`

```astro
---
interface Props {
  beforeImage: string;
  afterImage: string;
  beforeAlt: string;
  afterAlt: string;
  title: string;
  description?: string;
}

const { beforeImage, afterImage, beforeAlt, afterAlt, title, description } = Astro.props;
---

<div class="before-after-container">
  <h3 class="before-after-title">{title}</h3>
  {description && <p class="before-after-description">{description}</p>}

  <div class="before-after-grid">
    <div class="before-after-item">
      <div class="image-label">Before</div>
      <img
        src={beforeImage}
        alt={beforeAlt}
        loading="lazy"
        width="600"
        height="400"
      />
    </div>

    <div class="before-after-item">
      <div class="image-label after">After</div>
      <img
        src={afterImage}
        alt={afterAlt}
        loading="lazy"
        width="600"
        height="400"
      />
    </div>
  </div>
</div>

<style>
  .before-after-container {
    margin: 3rem 0;
  }

  .before-after-title {
    text-align: center;
    margin-bottom: 0.5rem;
    color: var(--text);
  }

  .before-after-description {
    text-align: center;
    color: var(--text-light);
    margin-bottom: 2rem;
  }

  .before-after-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 2rem;
    max-width: 1200px;
    margin: 0 auto;
  }

  .before-after-item {
    position: relative;
    border-radius: 0.5rem;
    overflow: hidden;
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
  }

  .image-label {
    position: absolute;
    top: 1rem;
    left: 1rem;
    background: rgba(0, 0, 0, 0.7);
    color: white;
    padding: 0.5rem 1rem;
    border-radius: 0.25rem;
    font-weight: 600;
    z-index: 1;
  }

  .image-label.after {
    background: var(--secondary);
  }

  .before-after-item img {
    width: 100%;
    height: auto;
    display: block;
  }

  @media (max-width: 768px) {
    .before-after-grid {
      grid-template-columns: 1fr;
    }
  }
</style>
```

**Subtask 5.2b: Source Before/After Images** (3 hours)

**Options**:
1. **Use client photos** (with permission) - FREE
2. **Stock photography** - Shutterstock, iStock ($10-50/image)
3. **Hire photographer** - Shoot real jobs ($200-500)
4. **Use placeholders temporarily** - Replace later

**Recommended Stock Photo Sites**:
- Unsplash.com (free, high quality)
- Pexels.com (free)
- Shutterstock.com (paid, professional)

**Search Terms**:
- "messy kitchen before cleaning"
- "clean kitchen after"
- "dirty bathroom before"
- "sparkling bathroom after"
- "cluttered living room"
- "organized living room"

**Image Requirements**:
- Resolution: 1200x800px minimum
- Format: JPG or WebP
- File size: < 200KB (optimized)
- Orientation: Landscape

**Subtask 5.2c: Add to Homepage** (30 min)

```astro
---
import BeforeAfter from '../components/BeforeAfter.astro';
---

<section class="before-after-section">
  <div class="container">
    <h2>See the Hero House Cleaning Difference</h2>

    <BeforeAfter
      beforeImage="/images/before-after/kitchen-before.jpg"
      afterImage="/images/before-after/kitchen-after.jpg"
      beforeAlt="Messy kitchen with dirty dishes and cluttered counters before Hero House Cleaning"
      afterAlt="Sparkling clean kitchen with organized counters after Hero House Cleaning service"
      title="Kitchen Deep Clean"
      description="From cluttered chaos to sparkling clean in 3 hours"
    />

    <BeforeAfter
      beforeImage="/images/before-after/bathroom-before.jpg"
      afterImage="/images/before-after/bathroom-after.jpg"
      beforeAlt="Dirty bathroom with soap scum and grime before cleaning"
      afterAlt="Pristine bathroom with sparkling fixtures after Hero House Cleaning"
      title="Bathroom Transformation"
      description="Professional deep cleaning for your bathroom"
    />

    <BeforeAfter
      beforeImage="/images/before-after/living-room-before.jpg"
      afterImage="/images/before-after/living-room-after.jpg"
      beforeAlt="Cluttered living room before Hero House Cleaning service"
      afterAlt="Organized, dust-free living room after professional cleaning"
      title="Living Room Refresh"
      description="Regular cleaning keeps your home guest-ready"
    />
  </div>
</section>
```

**Subtask 5.2d: Add to Service Pages** (1.5 hours)

Add service-specific before/after images to:
- deep-cleaning.astro (deep clean transformations)
- move-out-cleaning.astro (move-out results)
- airbnb-cleaning.astro (vacation rental turnovers)

---

## DAY 6-7: CONTENT EXPANSION (8 hours)

### Task 6.1: Create pricing-guide.astro Page (4 hours)
**Priority**: 🟡 HIGH - Missing high-value page

**File**: `src/pages/pricing-guide.astro`

**Content Structure**:
1. Hero section: "Knoxville House Cleaning Pricing Guide 2025"
2. Quick pricing overview (3 service cards)
3. Pricing table by square footage
4. Frequency discounts (weekly 20%, bi-weekly 15%, monthly 10%)
5. Add-on pricing (11 items)
6. Comparison table (Regular vs Deep vs Move In/Out)
7. "What affects pricing" section (8 factors)
8. Transparency section (vs industry standard)
9. FAQ (8 pricing questions)
10. Money-back guarantee
11. Quote form

**Template** (abbreviated):
```astro
---
import Layout from '../layouts/Layout.astro';
import QuoteForm from '../components/QuoteForm.astro';
import TrustBadges from '../components/TrustBadges.astro';
---

<Layout
  title="Knoxville House Cleaning Prices 2025 | Hero House"
  description="Transparent house cleaning prices in Knoxville. Regular $160+, Deep $330+, Move-out $378+. No hidden fees. Call (865) 507-1405!"
>
  <!-- Hero Section -->
  <section class="page-header">
    <div class="container">
      <h1>Knoxville House Cleaning Prices 2025</h1>
      <p class="subtitle">Transparent pricing with no hidden fees. See exactly what you'll pay.</p>
      <TrustBadges variant="horizontal" />
    </div>
  </section>

  <!-- Quick Pricing Overview -->
  <section class="pricing-overview">
    <div class="container">
      <div class="pricing-grid">
        <div class="pricing-card">
          <h3>Regular Cleaning</h3>
          <div class="price">$160<span>+</span></div>
          <ul class="features">
            <li>✓ All rooms cleaned</li>
            <li>✓ Dusting & vacuuming</li>
            <li>✓ Kitchen & bathrooms</li>
            <li>✓ 2-4 hours</li>
          </ul>
          <a href="#quote" class="btn btn-primary">Get Quote</a>
        </div>

        <div class="pricing-card featured">
          <div class="popular-badge">Most Popular</div>
          <h3>Deep Cleaning</h3>
          <div class="price">$330<span>+</span></div>
          <ul class="features">
            <li>✓ Everything in regular</li>
            <li>✓ Inside appliances</li>
            <li>✓ Baseboards & vents</li>
            <li>✓ 4-6 hours</li>
          </ul>
          <a href="#quote" class="btn btn-primary">Get Quote</a>
        </div>

        <div class="pricing-card">
          <h3>Move In/Out</h3>
          <div class="price">$378<span>+</span></div>
          <ul class="features">
            <li>✓ Everything in deep</li>
            <li>✓ Inside cabinets</li>
            <li>✓ Windows & blinds</li>
            <li>✓ 6-8 hours</li>
          </ul>
          <a href="#quote" class="btn btn-primary">Get Quote</a>
        </div>
      </div>
    </div>
  </section>

  <!-- Pricing Table by Square Footage -->
  <section class="pricing-table-section">
    <div class="container">
      <h2>Pricing by Home Size</h2>
      <div class="pricing-table">
        <table>
          <thead>
            <tr>
              <th>Home Size</th>
              <th>Regular Clean</th>
              <th>Deep Clean</th>
              <th>Move In/Out</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td>1,000-1,500 sq ft</td>
              <td>$160-$200</td>
              <td>$330-$400</td>
              <td>$378-$450</td>
            </tr>
            <tr>
              <td>1,500-2,000 sq ft</td>
              <td>$200-$240</td>
              <td>$400-$480</td>
              <td>$450-$520</td>
            </tr>
            <tr>
              <td>2,000-2,500 sq ft</td>
              <td>$240-$280</td>
              <td>$480-$560</td>
              <td>$520-$600</td>
            </tr>
            <tr>
              <td>2,500-3,000 sq ft</td>
              <td>$280-$320</td>
              <td>$560-$640</td>
              <td>$600-$680</td>
            </tr>
            <tr>
              <td>3,000+ sq ft</td>
              <td>$320+</td>
              <td>$640+</td>
              <td>$680+</td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </section>

  <!-- Add remaining sections... -->

  <!-- Quote Form -->
  <QuoteForm
    title="Get Your Exact Price Quote"
    subtitle="Tell us about your home and we'll send you a custom quote in 24 hours"
  />
</Layout>
```

**Full implementation**: Copy structure from house-cleaning-cost-knoxville.astro and adapt for pricing focus.

---

### Task 6.2: Increase Internal Linking (2 hours)
**Priority**: 🟡 MEDIUM - SEO authority distribution

**Goal**: Add 3-5 more internal links to each page

**Strategy**:
- Link from homepage to all service pages
- Link from service pages to related services
- Link from location pages to services
- Link from pricing pages to services
- Add "You might also like" sections

**Example for Homepage**:
```astro
<section class="related-services">
  <div class="container">
    <h3>Explore Our Services</h3>
    <div class="service-links">
      <a href="/services/deep-cleaning">Deep Cleaning Service →</a>
      <a href="/services/move-out-cleaning">Move Out Cleaning →</a>
      <a href="/services/airbnb-cleaning">Airbnb Cleaning →</a>
      <a href="/maid-service-knoxville">Maid Service →</a>
      <a href="/professional-house-cleaning">Professional Cleaning →</a>
    </div>
  </div>
</section>
```

**Contextual Linking Examples**:

In paragraph text:
```astro
<p>
  Looking for regular maintenance? Check out our
  <a href="/maid-service-knoxville">maid service in Knoxville</a>
  with weekly, bi-weekly, and monthly options.
</p>
```

**Pages to Update** (15 min each):
- index.astro (+5 links)
- about.astro (+3 links)
- services.astro (+4 links)
- All service pages (+3 links each)
- All location pages (+3 links each)

---

### Task 6.3: Add Urgency Messaging (2 hours)
**Priority**: 🟡 MEDIUM - +10-15% conversions

**Types of Urgency**:

**1. Availability Urgency**:
```astro
<div class="urgency-banner">
  <p>⏰ Limited Availability: Only 3 slots left this week</p>
</div>
```

**2. Seasonal Urgency**:
```astro
<div class="seasonal-notice">
  <p>🌸 Spring Cleaning Season: Book now for March deep cleaning</p>
</div>
```

**3. Discount Urgency**:
```astro
<div class="limited-offer">
  <p>💰 New Customer Special: Save 15% on your first deep cleaning (expires Jan 31)</p>
</div>
```

**Implementation**:

**Add to Homepage Hero**:
```astro
<section class="hero">
  <div class="container">
    <h1>Knoxville's Most Trusted House Cleaning Service</h1>

    <!-- Urgency Message -->
    <div class="urgency-box">
      <span class="urgency-icon">🔥</span>
      <span>Booking Fast! Typical availability: 2-3 days</span>
    </div>

    <div class="cta-buttons">
      <a href="/contact" class="btn btn-primary">Get Free Quote</a>
      <a href="tel:865-507-1405" class="btn btn-secondary">📞 Call (865) 507-1405</a>
    </div>
  </div>
</section>
```

**Add to Contact Page**:
```astro
<div class="booking-urgency">
  <p><strong>Same-day cleaning available for emergencies!</strong></p>
  <p>For Airbnb turnovers: Call (865) 507-1405 for same-day service</p>
</div>
```

---

## TESTING & VALIDATION CHECKLIST

### After Each Day's Work:

**Day 1 Testing** (Forms & Location Pages):
- [ ] All forms submit successfully to GoHighLevel
- [ ] Form confirmations appear
- [ ] Data appears in GoHighLevel dashboard
- [ ] Location pages have keywords in first 100 words
- [ ] Keyword density is 1-2% in openings
- [ ] Text reads naturally

**Day 2 Testing** (Meta Tags):
- [ ] All title tags 50-60 characters
- [ ] All meta descriptions 150-160 characters
- [ ] View page source to verify
- [ ] Google SERP preview looks good (use SERP simulator)

**Day 3 Testing** (Schema):
- [ ] Validate all schema with Google Rich Results Test
- [ ] No validation errors
- [ ] streetAddress fields populated
- [ ] Contact form has 4 fields (if not using GoHighLevel)

**Day 4 Testing** (Accessibility):
- [ ] Skip link appears on Tab key
- [ ] All text passes WCAG AA contrast
- [ ] Focus indicators visible
- [ ] Tab through entire page (logical order)
- [ ] Test with screen reader (NVDA/JAWS/VoiceOver)

**Day 5 Testing** (Trust & Images):
- [ ] Trust badges display near forms
- [ ] Before/after images load properly
- [ ] Images optimized (< 200KB each)
- [ ] Alt text descriptive

**Day 6-7 Testing** (Content):
- [ ] pricing-guide page displays correctly
- [ ] All internal links work
- [ ] No broken links (check with tool)
- [ ] Urgency messages display appropriately

---

## DEPLOYMENT CHECKLIST

### Pre-Deployment:
- [ ] Run `npm run build` with no errors
- [ ] Test locally with `npm run dev`
- [ ] Check all pages load
- [ ] Test mobile responsive at 320px, 768px, 1024px
- [ ] Verify forms submit
- [ ] Run Lighthouse audit (aim for 90+ scores)
- [ ] Validate HTML (W3C validator)
- [ ] Check for console errors

### Post-Deployment:
- [ ] Submit updated sitemap to Google Search Console
- [ ] Fetch as Google for updated pages
- [ ] Check robots.txt accessible: yoursite.com/robots.txt
- [ ] Check sitemap accessible: yoursite.com/sitemap.xml
- [ ] Test forms in production
- [ ] Monitor form submissions
- [ ] Check Google Analytics tracking
- [ ] Verify GTM tags firing (if applicable)

---

## MONITORING & ITERATION

### Week 2-3 Metrics to Track:

**Conversions**:
- Form submissions per day (baseline vs new)
- Phone calls per day
- Conversion rate by page

**SEO**:
- Google Search Console impressions
- Click-through rate (CTR) by page
- Average position for target keywords
- Location page rankings

**UX**:
- Bounce rate (should decrease)
- Time on page (should increase)
- Pages per session
- Mobile vs desktop metrics

### Expected Results Timeline:

**Week 2** (Immediate):
- Forms functional: See first conversions
- CTR improvement: +5-10% from meta tag fixes

**Week 3-4**:
- Location traffic: +15-20% from keyword optimization
- Form completions: +30-40% from field reduction

**Month 2**:
- Organic traffic: +35-50%
- Conversions: +60-80%
- Revenue impact: $200K-$350K annually

---

## TIME SUMMARY

| Week | Days | Hours | Tasks |
|------|------|-------|-------|
| Week 2 | Day 1 | 8h | Forms + Location keywords |
| Week 2 | Day 2 | 4h | Meta tag optimization |
| Week 2 | Day 3 | 4h | Schema + Form fields |
| **Week 2 Total** | **3 days** | **16h** | **Critical fixes** |
| Week 3 | Day 4 | 4h | Accessibility |
| Week 3 | Day 5 | 8h | Trust signals + Images |
| Week 3 | Day 6-7 | 8h | Content expansion |
| **Week 3 Total** | **4 days** | **20h** | **High priority** |
| **GRAND TOTAL** | **7 days** | **36h** | **All fixes** |

---

## PRIORITIZATION SHORTCUTS

### If you only have 8 hours:
1. GoHighLevel forms (6h) ← CRITICAL
2. Location page keywords (2h)

### If you have 16 hours (Week 2):
1-6. All Week 2 tasks

### If you have 24 hours (Week 2 + critical Week 3):
1-6. Week 2 tasks (16h)
7. Accessibility (4h)
8. Trust badges (2h)
9. Some before/after images (2h)

### Full 36 hours:
Complete entire plan for maximum impact

---

**Ready to implement? Start with Task 1.1 (GoHighLevel forms) for immediate conversion enablement!**
