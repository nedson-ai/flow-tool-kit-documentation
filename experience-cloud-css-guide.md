# Experience Cloud CSS Style Guide

> **Comprehensive guide for styling Salesforce Experience Cloud sites with modern CSS practices**

## 🎯 Recommended Approach: SLDS + Modern CSS

### **Primary Resources:**

1. **Salesforce Lightning Design System (SLDS)**: https://www.lightningdesignsystem.com/
2. **Experience Cloud Developer Guide**: https://developer.salesforce.com/docs/atlas.en-us.communities_dev.meta/

## 🏗️ Architecture Strategy

### **Tier 1: SLDS Foundation (80%)**
Use SLDS for:
- ✅ **Grid System** (`slds-grid`, `slds-col`)
- ✅ **Typography** (`slds-text-heading_large`, `slds-text-body_regular`)
- ✅ **Form Elements** (`slds-form-element`, `slds-input`)
- ✅ **Buttons** (`slds-button`, `slds-button_brand`)
- ✅ **Icons** (`slds-icon`, Lightning icon library)
- ✅ **Spacing** (`slds-m-around_medium`, `slds-p-horizontal_large`)

### **Tier 2: Custom CSS Properties (15%)**
Override SLDS with:
```css
:root {
  --brand-primary: #1e3a8a;      /* Your navy blue */
  --brand-secondary: #10b981;    /* Your green */
  --sds-c-brand: var(--brand-primary);  /* SLDS brand override */
}
```

### **Tier 3: Custom Components (5%)**
Build custom components for:
- Complex layouts not covered by SLDS
- Brand-specific patterns
- Advanced interactions

## 📋 Implementation Strategies

### **Strategy 1: Theme Customization (Easiest)**
**Best for:** Basic branding, color changes, simple layouts

```css
/* In Experience Builder > Settings > Advanced > CSS */
.siteforceThemeLayoutHeaderContainer {
  background: #1e3a8a !important;
}

.slds-brand {
  --sds-c-brand: #1e3a8a;
  --sds-c-brand-accessible: #1e3a8a;
}
```

### **Strategy 2: Custom Lightning Component CSS (Recommended)**
**Best for:** Reusable components, advanced styling

```css
/* In Lightning Web Component CSS */
:host {
  --brand-primary: #1e3a8a;
}

.custom-card {
  background: white;
  border-radius: 0.75rem;
  box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
  padding: 1.5rem;
}
```

### **Strategy 3: Static Resource CSS (Most Flexible)**
**Best for:** Site-wide styles, complex design systems

Upload CSS file as Static Resource and include:
```html
<apex:stylesheet value="{!URLFOR($Resource.ExperienceCloudStyles)}" />
```

## 🎨 Design System Patterns

### **Color System**
```css
:root {
  /* Primary Brand Colors */
  --brand-primary: #1e3a8a;        /* Navy blue */
  --brand-secondary: #10b981;      /* Green */
  --brand-accent: #f59e0b;         /* Amber */
  
  /* Semantic Colors */
  --color-success: #10b981;
  --color-error: #ef4444;
  --color-warning: #f59e0b;
  --color-info: #3b82f6;
  
  /* Neutral Colors */
  --color-text: #1a202c;
  --color-text-secondary: #718096;
  --color-background: #ffffff;
  --color-background-alt: #f8fafc;
  --color-border: #e2e8f0;
}
```

### **Typography Scale**
```css
:root {
  --font-size-xs: 0.75rem;      /* 12px - Small labels */
  --font-size-sm: 0.875rem;     /* 14px - Body small */
  --font-size-base: 1rem;       /* 16px - Body text */
  --font-size-lg: 1.125rem;     /* 18px - Lead text */
  --font-size-xl: 1.25rem;      /* 20px - Small headings */
  --font-size-2xl: 1.5rem;      /* 24px - Medium headings */
  --font-size-3xl: 1.875rem;    /* 30px - Large headings */
  --font-size-4xl: 2.25rem;     /* 36px - Hero headings */
}
```

### **Spacing System (Matches SLDS)**
```css
:root {
  --spacing-xx-small: 0.25rem;  /* 4px */
  --spacing-x-small: 0.5rem;    /* 8px */
  --spacing-small: 0.75rem;     /* 12px */
  --spacing-medium: 1rem;       /* 16px */
  --spacing-large: 1.5rem;      /* 24px */
  --spacing-x-large: 2rem;      /* 32px */
  --spacing-xx-large: 3rem;     /* 48px */
}
```

## 🔧 Experience Cloud Specific Patterns

### **Header Customization**
```css
/* Custom header styling */
.siteforceThemeLayoutHeaderContainer {
  background: var(--brand-primary) !important;
  box-shadow: 0 2px 4px rgba(0,0,0,0.1);
}

.siteforceThemeLayoutHeader .navbar-brand {
  color: white !important;
  font-weight: 600;
}

/* Navigation styling */
.siteforceTheme4Navigation .navbar-nav > li > a {
  color: rgba(255, 255, 255, 0.9) !important;
  font-weight: 500;
  transition: color 0.2s ease;
}

.siteforceTheme4Navigation .navbar-nav > li > a:hover {
  color: var(--brand-secondary) !important;
}
```

### **Footer Customization**
```css
.siteforceThemeLayoutFooter {
  background: #1a202c !important;
  color: white;
  padding: 3rem 0 2rem;
}

.siteforceThemeLayoutFooter .container {
  max-width: 1200px;
  margin: 0 auto;
}
```

### **Community Page Overrides**
```css
/* Remove default community styling */
.cCommunityThemeLayout .themeLayout {
  background: var(--color-background);
}

/* Custom page container */
.siteforceContentArea {
  padding: var(--spacing-x-large) var(--spacing-medium);
  max-width: 1200px;
  margin: 0 auto;
}
```

## 📱 Responsive Design Patterns

### **Breakpoint System**
```css
/* Mobile-first approach */
.ec-container {
  padding: var(--spacing-medium);
}

/* Tablet */
@media (min-width: 768px) {
  .ec-container {
    padding: var(--spacing-large);
  }
}

/* Desktop */
@media (min-width: 1024px) {
  .ec-container {
    padding: var(--spacing-x-large);
    max-width: 1200px;
    margin: 0 auto;
  }
}
```

### **Grid Patterns**
```css
/* Responsive feature grid */
.ec-features {
  display: grid;
  grid-template-columns: 1fr;
  gap: var(--spacing-large);
}

@media (min-width: 768px) {
  .ec-features {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (min-width: 1024px) {
  .ec-features {
    grid-template-columns: repeat(3, 1fr);
  }
}
```

## 🎯 Flow Tool Kit Integration

### **Form Styling for Flow Tool Kit**
```css
/* Custom form styling that works with Flow Tool Kit */
.flow-toolkit-form .slds-form-element {
  margin-bottom: var(--spacing-large);
}

.flow-toolkit-form .slds-input,
.flow-toolkit-form .slds-textarea {
  border-radius: var(--border-radius-md);
  border-color: var(--color-border);
  transition: border-color 0.2s ease, box-shadow 0.2s ease;
}

.flow-toolkit-form .slds-input:focus,
.flow-toolkit-form .slds-textarea:focus {
  border-color: var(--brand-secondary);
  box-shadow: 0 0 0 2px rgba(16, 185, 129, 0.2);
}

/* Custom button styling */
.flow-toolkit-form .slds-button_brand {
  background-color: var(--brand-secondary);
  border-color: var(--brand-secondary);
}

.flow-toolkit-form .slds-button_brand:hover {
  background-color: color-mix(in srgb, var(--brand-secondary) 85%, black);
}
```

## 🏆 Best Practices

### **1. Performance**
- ✅ **Use SLDS classes** when possible (already optimized)
- ✅ **Minimize custom CSS** (faster loading)
- ✅ **Use CSS custom properties** for theming
- ✅ **Avoid !important** unless overriding platform styles

### **2. Maintainability**
- ✅ **Follow BEM naming** for custom components
- ✅ **Use semantic class names** (.ec-card vs .blue-box)
- ✅ **Group related styles** together
- ✅ **Comment complex selectors**

### **3. Accessibility**
- ✅ **Maintain SLDS focus states**
- ✅ **Use proper color contrast** (4.5:1 minimum)
- ✅ **Support reduced motion preferences**
- ✅ **Test with screen readers**

### **4. Brand Consistency**
- ✅ **Use design tokens** (CSS custom properties)
- ✅ **Create reusable components**
- ✅ **Document brand colors and usage**
- ✅ **Test on multiple screen sizes**

## 🚀 Implementation Checklist

### **Phase 1: Foundation**
- [ ] Set up SLDS base styles
- [ ] Define brand color variables
- [ ] Test responsive breakpoints
- [ ] Implement basic typography scale

### **Phase 2: Components**
- [ ] Style header/navigation
- [ ] Create custom card components
- [ ] Style forms and buttons
- [ ] Add hover/focus states

### **Phase 3: Enhancement**
- [ ] Add animations and transitions
- [ ] Implement dark mode (if needed)
- [ ] Optimize for performance
- [ ] Test accessibility

### **Phase 4: Integration**
- [ ] Style Flow Tool Kit components
- [ ] Test with actual content
- [ ] Cross-browser testing
- [ ] Mobile optimization

## 📚 Additional Resources

### **Official Documentation**
- **SLDS**: https://www.lightningdesignsystem.com/
- **Experience Cloud Branding**: https://help.salesforce.com/s/articleView?id=sf.community_designer_brand.htm
- **Lightning Components CSS**: https://developer.salesforce.com/docs/component-library/documentation/en/lwc/lwc.create_components_css

### **Tools**
- **SLDS Validator**: Check SLDS compliance
- **Accessibility Checker**: WAVE, axe-core
- **Performance**: Lighthouse, PageSpeed Insights

### **Community Resources**
- **Trailblazer Community**: Experience Cloud Design group
- **GitHub**: SLDS design tokens and examples
- **CodePen**: SLDS component examples

This approach ensures your Experience Cloud site is professional, performant, and perfectly integrated with Salesforce while maintaining your unique brand identity.