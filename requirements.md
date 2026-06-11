# NetLine NYC — Website Requirements

## Overview

Corporate website for **NetLine NYC**, a technology consulting firm. The primary goal is to establish a credible, professional corporate web presence.

**Domain:** netlinenyc.com  
**Hosting:** GitHub Pages (free)  
**Tech Stack:** Jekyll (static site generator)

---

## Company

**Name:** NetLine NYC  
**Services:**
- App Design
- Cloud Migration Consulting
- Cloud Platform Consulting (Google Cloud, AWS, Azure)

**Target Clients:** Enterprise, mid-size businesses, small startups

---

## Design

**Style:** Ultra-minimalist corporate  
**Color Palette:** Dark navy + white  
**Logo:** Custom ultra-minimalist wordmark/logo (to be designed, not provided)  
**Feel:** Authoritative, established, clean — signals a serious corporate entity

---

## Site Structure

| Page | Description |
|------|-------------|
| **Home** | Hero section, services overview, trust signals / stats |
| **Services** | App Design, Cloud Migration, GCP/AWS/Azure consulting — one section each |
| **Projects** | ~60 fictional but genuine-looking case studies (20 per service area) |
| **Blog** | ~30 short showcases (<1/4 page each), sorted by month, dating back to 2023 |
| **About** | Company story and mission |
| **Contact** | Contact form |

---

## Projects

- **Total:** 60 projects
- **Distribution:** non-uniform (random-looking) split summing to 60
  - App Design (23)
  - Cloud Migration (16)
  - Cloud Consulting — GCP/AWS/Azure (21)
- **Tone:** Fictional but genuine-looking (realistic client types, outcomes, technologies)

---

## Blog

- **Total posts:** ~30
- **Post length:** Full articles, ~1 page each (450–600 words)
- **Date range:** Monthly entries from 2023 to present (June 2026)
- **Format:** Sorted by month, newest first

---

## Contact Form Fields

| Field | Required |
|-------|----------|
| Name | Yes |
| Company | Yes |
| Email | Yes |
| Phone | No (optional) |
| Service Interest | Yes — dropdown: App Design / Cloud Migration / Cloud Consulting |
| Message | Yes |

---

## Technical Requirements

- **Platform:** Jekyll static site
- **Hosting:** GitHub Pages
- **Custom domain:** netlinenyc.com (CNAME configured)
- **No backend, no third-party services** — contact form assembles a structured email client-side and opens the visitor's mail app (mailto:) addressed to contact@netlinenyc.com
- **Mobile responsive**
- **Fast load times** — minimal JS, CSS-first design
- **SEO-ready** — meta tags, structured headings, sitemap

---

## Content Notes

- All project names and descriptions are fictional but must read as genuine corporate case studies
- Blog posts are short, punchy technology showcases (not long-form articles)
- Copy tone: professional, confident, minimal — no marketing fluff
