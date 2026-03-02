# Flow Tool Kit - GitBook Setup Guide

## 📋 ACCOUNT SETUP CHECKLIST
- [ ] Go to gitbook.com
- [ ] Click "Sign up with GitHub" 
- [ ] Authorize GitBook to access your repositories
- [ ] Select "flow-tool-kit-documentation" repository

## 🎨 BRANDING SETTINGS
### Colors (Common-Unite Brand)
- **Primary**: #1e3a8a (Navy Blue)
- **Secondary**: #10b981 (Green)
- **Background**: #ffffff (White)

### Logo/Favicon
- Upload Common-Unite logo
- Set site title: "Flow Tool Kit Documentation"
- Tagline: "Enterprise Data Collection for Nonprofits"

## 📁 INITIAL PAGE STRUCTURE
Create these pages in GitBook:

### 🎯 Getting Started
**Page: "Overview"**
- Embed hero video: Flow Tool Kit Demo
- Quick benefits list
- "Try Flow Tool Kit" CTA button

**Page: "For Decision Makers"**  
- ROI calculator
- Success stories
- Pricing information

### 📚 Feature Guides
**Page: "Form Components"**
- Video: Advanced Form Building (15min)
- Expandable: Technical specifications
- Expandable: Configuration guide

**Page: "Data Tables"**
- Video: Data Table Demo (12min)
- Expandable: Advanced queries
- Expandable: Performance tips

**Page: "Digital Signatures"**
- Video: Signature Component Demo
- Expandable: Implementation steps
- Expandable: Security considerations

### 🔧 Technical Reference
**Page: "API Documentation"**
- Component reference
- Integration examples
- Authentication

**Page: "Installation Guide"**
- System requirements
- Step-by-step setup
- Troubleshooting

## 📹 VIDEO EMBEDDING FORMAT
For each feature page, use this structure:

```markdown
# Feature Name

## Demo Video
[Embed video here - GitBook supports YouTube, Vimeo, Loom]

## Quick Benefits
- Benefit 1
- Benefit 2  
- Benefit 3

{% content-ref url="technical-specs.md" %}
technical-specs.md
{% endcontent-ref %}

## Implementation
<details>
<summary>📋 Technical Specifications</summary>

[Detailed technical content here]

</details>
```

## 🚀 IMPORT SETTINGS
### Repository Connection
- **Repository**: nedson-ai/flow-tool-kit-documentation
- **Branch**: main
- **Root Path**: / (use entire repo)
- **Auto-sync**: Enabled

### Domain Settings  
- **Subdomain**: flowToolKit (or your preference)
- **Custom domain**: docs.commonunite.com (when ready)

## 📊 ANALYTICS SETUP
- Enable GitBook analytics
- Add Google Analytics (if you have account)
- Track popular pages and search terms

## 🔗 NAVIGATION STRUCTURE
```
🏠 Home
├── 🎯 Getting Started
│   ├── Overview  
│   ├── For Decision Makers
│   └── Quick Start Guide
├── 📚 Feature Guides
│   ├── Form Components
│   ├── Data Tables
│   ├── Digital Signatures
│   ├── Responsive Design
│   └── Advanced Features
├── 🔧 Technical Reference
│   ├── API Documentation
│   ├── Installation Guide
│   └── System Requirements
└── 💡 Support
    ├── FAQ
    ├── Troubleshooting  
    └── Contact Information
```

## ✅ LAUNCH CHECKLIST
- [ ] Account created and repository connected
- [ ] Branding applied (colors, logo)
- [ ] 5 key pages created with video embeds
- [ ] Navigation structure configured
- [ ] First video successfully embedded and tested
- [ ] Mobile responsive preview checked
- [ ] Share test link with team for feedback

---
**Next Steps After Setup:**
1. Upload and organize your 58 training videos
2. Create expandable technical sections
3. Add search functionality testing
4. Configure custom domain (docs.commonunite.com)