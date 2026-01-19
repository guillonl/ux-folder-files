# Workflows UX Avancés - End-to-End

**Version** : 1.0
**Dernière mise à jour** : 2026-01-18

---

## 📋 Table des Matières

1. [Introduction](#introduction)
2. [Workflows End-to-End](#workflows-end-to-end)
3. [Workflows par Industrie](#workflows-par-industrie)
4. [Adaptation selon Contraintes](#adaptation-selon-contraintes)

---

## Introduction

Ce document présente des **workflows UX avancés end-to-end** combinant plusieurs agents en séquences ou parallèle pour répondre à des besoins UX complexes réels.

Chaque workflow inclut :
- Séquence agents étape par étape
- Timeline estimée
- Outputs attendus à chaque handoff
- Variations selon contraintes

---

## Workflows End-to-End

### Workflow 1 : Complete Discovery to Launch

**Contexte :** Startup lançant nouveau produit SaaS B2B, zéro user research existante

**Objectif :** De l'idée au MVP lancé avec validation utilisateurs

**Timeline :** 8-10 semaines

**Séquence Agents :**

```
PHASE 1 : RESEARCH (Semaine 1-2)
┌──────────────────────────────────────┐
│ 1. UX Research Scout (5 jours)      │
│    - Competitive analysis (3-5 comp) │
│    - Best practices industry         │
│    - Compliance requirements (GDPR)  │
│    OUTPUT : Competitive report       │
└──────────────────────────────────────┘
         ↓ (handoff : insights)
┌──────────────────────────────────────┐
│ 2. Design Thinking Facilitator      │
│    (10 jours - 5 phases)            │
│    - Empathize : 10 user interviews  │
│    - Define : POV statements         │
│    - Ideate : HMW questions, Crazy 8s│
│    - Prototype : Low-fi prototypes   │
│    - Test : 5 user tests             │
│    OUTPUT : Validated concepts       │
└──────────────────────────────────────┘

PHASE 2 : FORMALIZATION (Semaine 3-4)
         ↓ (handoff : user insights)
┌──────────────────────────────────────┐
│ 3. Persona Generator (3 jours)      │
│    - Synthesize interview data       │
│    - Create 3 data-driven personas   │
│    OUTPUT : Persona cards + profiles │
└──────────────────────────────────────┘
         ↓ (handoff : personas)
┌──────────────────────────────────────┐
│ 4. User Journey Mapper (3 jours)    │
│    - Map journeys per persona        │
│    - Identify touchpoints, emotions  │
│    OUTPUT : Journey maps (as-is +    │
│             to-be)                   │
└──────────────────────────────────────┘

PHASE 3 : ALIGNMENT (Semaine 4-5)
         ↓ (handoff : journeys + personas)
┌──────────────────────────────────────┐
│ 5. Impact Mapping Facilitator (3j)  │
│    - Link business goals → personas  │
│    - Identify key impacts            │
│    OUTPUT : Impact map, priorities   │
└──────────────────────────────────────┘
         ↓ (handoff : strategic priorities)
┌──────────────────────────────────────┐
│ 6. Story Mapping Facilitator (2j)   │
│    - Break impact map → user stories │
│    - Prioritize MVP scope            │
│    OUTPUT : Story map, backlog       │
└──────────────────────────────────────┘

PHASE 4 : VALIDATION (Semaine 6)
         ↓ (handoff : MVP scope)
┌──────────────────────────────────────┐
│ 7. Design Sprint Conductor (5j)     │
│    - Monday : Map MVP workflow       │
│    - Tuesday : Sketch solutions      │
│    - Wednesday : Decide best design  │
│    - Thursday : Prototype high-fi    │
│    - Friday : Test with 5 users     │
│    OUTPUT : Validated prototype,     │
│             GO/NO-GO decision        │
└──────────────────────────────────────┘

PHASE 5 : LAUNCH + MEASURE (Semaine 7-10)
         ↓ (if GO)
┌──────────────────────────────────────┐
│ 8. Development + Launch (3 semaines)│
│    - Build MVP                       │
│    - Launch to beta users (50)      │
└──────────────────────────────────────┘
         ↓ (post-launch)
┌──────────────────────────────────────┐
│ 9. A/B Test Analyst (ongoing)       │
│    - Test onboarding variants        │
│    - Measure adoption, activation    │
│    OUTPUT : Test results, iterations │
└──────────────────────────────────────┘
```

**Deliverables Finaux :**
- Competitive Analysis Report
- 3 Personas (data-driven)
- User Journey Maps (3 personas × as-is/to-be)
- Impact Map (business alignment)
- Story Map + MVP Backlog
- High-fi Prototype (Figma)
- A/B Test Results Post-Launch

**Success Metrics :**
- ✅ MVP validé avec vrais users (5 tests Sprint, 50 beta)
- ✅ Product-market fit indicators (retention >40%, NPS >30)

---

### Workflow 2 : Audit Complet Multi-Perspective

**Contexte :** Refonte majeure dashboard SaaS, stakeholders veulent audit exhaustif

**Objectif :** Identifier tous problèmes UX (usability, accessibility, design system)

**Timeline :** 3 semaines

**Séquence Agents :**

```
WEEK 1 : AUDITS PARALLÈLES
┌─────────────────────────────────────────────────────────┐
│ 1. UX Auditor Nielsen (2j, parallel)                   │
│    OUTPUT : Usability report (10 heuristics scored)    │
├─────────────────────────────────────────────────────────┤
│ 2. UX Auditor Bastien & Scapin (3j, parallel)          │
│    OUTPUT : Ergonomic report (18 criteria, heat maps)  │
├─────────────────────────────────────────────────────────┤
│ 3. Accessibility WCAG Checker (2j, parallel)           │
│    OUTPUT : WCAG 2.1 AA compliance report              │
├─────────────────────────────────────────────────────────┤
│ 4. Design System Auditor (3j, parallel)                │
│    OUTPUT : DS health score, consistency gaps          │
└─────────────────────────────────────────────────────────┘

WEEK 2 : CONSOLIDATION
         ↓ (handoff : 4 audit reports)
┌──────────────────────────────────────────────────────────┐
│ 5. Multi-Framework Analyzer (5j)                        │
│    - Cross-reference findings (4 perspectives)          │
│    - Identify convergences (high confidence)            │
│    - Prioritize (P0/P1/P2/P3)                          │
│    OUTPUT : Consolidated report, roadmap                │
└──────────────────────────────────────────────────────────┘

WEEK 3 : REPORTING + PLANNING
         ↓ (handoff : prioritized findings)
┌──────────────────────────────────────────────────────────┐
│ 6. Story Mapping Facilitator (2j)                       │
│    - Map fixes to user stories                          │
│    - Sequence in sprints (Sprint 1, 2, 3)              │
│    OUTPUT : Sprint backlog (3 sprints roadmap)          │
└──────────────────────────────────────────────────────────┘
         ↓
┌──────────────────────────────────────────────────────────┐
│ FINAL DELIVERABLES (3j)                                 │
│ - Executive Summary (C-level)                           │
│ - Detailed Report (design team)                         │
│ - Sprint Action Items (dev team)                        │
└──────────────────────────────────────────────────────────┘
```

**Convergence Example :**

| Issue | Nielsen | B&S | WCAG | DS | Priority |
|-------|---------|-----|------|----|----------|
| Filters complexity | ✅ H#6 | ✅ Cog load | ✅ Keyboard | ✅ | **P0** (all 4) |
| Info overload | ✅ H#8 | ✅ Density | ❌ | ✅ | **P0** (3/4) |
| Contrast issues | ❌ | ❌ | ✅ | ✅ | **P1** (2/4) |
| Inconsistent buttons | ❌ | ❌ | ❌ | ✅ | **P2** (1/4) |

**Deliverables Finaux :**
- 4 Audit Reports (Nielsen, B&S, WCAG, DS)
- Consolidated Multi-Framework Report
- Prioritized Roadmap (P0 → P3)
- 3-Sprint Action Plan

**Success Metrics :**
- ✅ Exhaustive audit (4 perspectives)
- ✅ Clear prioritization (convergence logic)
- ✅ Actionable sprint backlog

---

### Workflow 3 : Analytics-Driven Improvement

**Contexte :** Produit mature, engagement dropped 30% last quarter, need root cause

**Objectif :** Comprendre pourquoi metrics dropped + fix issues

**Timeline :** 4 semaines

**Séquence Agents :**

```
WEEK 1 : DATA COLLECTION (PARALLEL)
┌──────────────────────────────────────────────────────────┐
│ 1. Analytics Interpreter (3j, parallel)                 │
│    - GA4 funnel analysis                                 │
│    - Cohort retention analysis                           │
│    - Feature usage heatmaps                              │
│    OUTPUT : Quantitative insights (WHERE problem is)    │
├──────────────────────────────────────────────────────────┤
│ 2. Qualitative Feedback Analyzer (3j, parallel)         │
│    - Support tickets (last 3 months)                     │
│    - NPS feedback, app reviews                           │
│    - Thematic analysis                                   │
│    OUTPUT : Qualitative insights (WHY problem exists)   │
└──────────────────────────────────────────────────────────┘

WEEK 2 : SYNTHESIS
         ↓ (handoff : quant + qual findings)
┌──────────────────────────────────────────────────────────┐
│ 3. User Journey Mapper (4j)                             │
│    - Map current state (with pain points from analytics) │
│    - Emotion curve (before vs after metric drop)        │
│    - Identify critical moments of friction              │
│    OUTPUT : Journey map annotated with data             │
└──────────────────────────────────────────────────────────┘

WEEK 3 : IDEATION
         ↓ (handoff : pain points visualized)
┌──────────────────────────────────────────────────────────┐
│ 4. Design Thinking Facilitator (5j - Ideate phase only) │
│    - HMW questions based on journey pain points          │
│    - Brainstorming solutions (workshop 1 day)            │
│    - Prioritize solutions (Impact × Effort matrix)      │
│    OUTPUT : Top 3 solutions prioritized                 │
└──────────────────────────────────────────────────────────┘

WEEK 4 : VALIDATION
         ↓ (handoff : solution concepts)
┌──────────────────────────────────────────────────────────┐
│ 5. A/B Test Analyst (5j)                                │
│    - Design experiments for top 3 solutions              │
│    - Launch A/B tests                                    │
│    - Measure impact on engagement                        │
│    OUTPUT : Test results, winning variants              │
└──────────────────────────────────────────────────────────┘
         ↓
┌──────────────────────────────────────────────────────────┐
│ CONTINUOUS : Feedback Loop (ongoing)                     │
│ - Monitor metrics weekly                                 │
│ - Iterate based on data                                  │
│ - Return to Analytics Interpreter if new drops          │
└──────────────────────────────────────────────────────────┘
```

**Deliverables Finaux :**
- Root Cause Analysis (quant + qual)
- Journey Map (current state + pain points)
- 3 Prioritized Solutions
- A/B Test Results
- Engagement Recovery Plan

**Success Metrics :**
- ✅ Root cause identified (clear WHY metrics dropped)
- ✅ Engagement recovered (target +20% from baseline)

---

## Workflows par Industrie

### SaaS B2B

**Challenges spécifiques :**
- Utilisateurs experts (steep learning curve OK)
- Acheteurs ≠ utilisateurs (stakeholders multiples)
- Adoption + retention critiques

**Workflow recommandé :**
1. **Impact Mapping** (align business goals multi-stakeholders)
2. **Persona Generator** (buyer persona vs user persona)
3. **Design Thinking** (focus onboarding, activation)
4. **A/B Testing** (optimize activation funnel)

---

### E-commerce

**Challenges spécifiques :**
- Conversion critiques (checkout optimization)
- Mobile-first (50%+ traffic mobile)
- Accessibilité (large audience)

**Workflow recommandé :**
1. **Analytics Interpreter** (funnel drop-offs)
2. **User Journey Mapper** (browse → purchase)
3. **WCAG Checker** (compliance + SEO)
4. **A/B Testing** (checkout variants)

---

### Mobile Apps

**Challenges spécifiques :**
- Retention (D1, D7, D30 critical)
- Onboarding (first-time UX crucial)
- App store reviews (public feedback)

**Workflow recommandé :**
1. **Qualitative Feedback** (app reviews analysis)
2. **User Journey Mapper** (onboarding flow)
3. **Design Sprint** (rapid iteration onboarding)
4. **A/B Testing** (onboarding variants)

---

## Adaptation selon Contraintes

### Contrainte Temps (Timeline Serré)

**Standard Workflow (2 semaines) → Quick Variant (3-5 jours)**

| Standard | Quick Variant |
|----------|---------------|
| Nielsen + B&S + WCAG (10j) | Nielsen Sprint seul (2j) |
| Design Thinking 5j | Design Thinking 1-day compressed |
| Design Sprint 5j | Lightning Decision Jam (4h) |
| Full Personas (3j) | Proto-personas (4h) |

**Stratégies :**
- Parallelization max (simultaneous agents)
- Single-agent vs multi-agent
- Sprint formats (compressed)
- Proto-versions (validated later)

---

### Contrainte Budget (Ressources Limitées)

**Solutions :**
- **Free tools** : Google Optimize (vs Optimizely), Guerrilla testing (vs lab)
- **Self-service** : Templates DIY, async methods
- **Simplified workflows** : 1 agent instead of 3
- **Internal resources** : Team workshops (vs external consultants)

---

### Contrainte Compétences (Équipe Junior)

**Adaptations :**
- **Simpler agents** : Story Mapping (visual, easy) vs Impact Mapping (strategic, harder)
- **Guided templates** : Step-by-step instructions
- **Shorter workshops** : 3h instead of 3 days
- **Focus on fundamentals** : Nielsen (simple) before B&S (complex)

---

## Ressources

**Agents** : `/agents/` (18 agents)
**Frameworks** : `/frameworks/` (7 frameworks)
**Templates** : `/templates/` (10 templates)
**Orchestration Guide** : `docs/orchestration-guide.md`

---

**Version** : 1.0
**Auteurs** : UX Agents Repository Team
