# Guide d'Orchestration Multi-Agents UX

**Version** : 1.0
**Dernière mise à jour** : 2026-01-18

---

## 📋 Table des Matières

1. [Introduction](#introduction)
2. [Decision Matrix](#decision-matrix)
3. [Workflow Patterns](#workflow-patterns)
4. [Handoff Protocols](#handoff-protocols)
5. [Use Cases Détaillés](#use-cases-détaillés)
6. [Best Practices](#best-practices)

---

## Introduction

### Qu'est-ce que l'Orchestration Multi-Agents ?

L'orchestration multi-agents consiste à **coordonner plusieurs agents UX spécialisés** en séquence ou en parallèle pour résoudre des problèmes UX complexes nécessitant plusieurs perspectives ou expertises.

**Pourquoi orchestrer ?**

1. **Problèmes complexes** nécessitent expertise multiple (audit + research + design)
2. **Triangulation** augmente confiance (même finding détecté par 3 agents = high confidence)
3. **Efficacité** via parallelization (agents indépendants en simultané)
4. **Complétude** (360° view vs single perspective)

**Quand orchestrer ?**

- ✅ Audit multi-framework (Nielsen + Bastien & Scapin + WCAG)
- ✅ Discovery complet (Research → Design Thinking → Personas → Journey)
- ✅ Data-driven improvement (Analytics + Feedback → Journey Map → Solutions)
- ❌ Besoin simple (1 agent suffit - pas d'orchestration)

---

## Decision Matrix

### Matrice Workflow Selection (Besoin × Profondeur)

Cette matrice guide le choix du workflow optimal selon **type de besoin** et **profondeur souhaitée**.

```
┌──────────────┬──────────────┬──────────────┬──────────────┬───────────────────┐
│ BESOIN       │ QUICK        │ STANDARD     │ DEEP         │ COMPLETE          │
│              │ (1-2 jours)  │ (1 semaine)  │ (2-3 sem)    │ (4+ semaines)     │
├──────────────┼──────────────┼──────────────┼──────────────┼───────────────────┤
│ AUDIT        │ Nielsen      │ Nielsen +    │ Multi-       │ Multi-Framework + │
│ (évaluer     │ Sprint       │ Bastien &    │ Framework    │ DS Auditor +      │
│ existant)    │ (1j)         │ Scapin (5j)  │ (N+B&S+WCAG) │ User Testing      │
│              │              │              │ (10j)        │ (20j+)            │
├──────────────┼──────────────┼──────────────┼──────────────┼───────────────────┤
│ EXPLORE      │ 1-day DT     │ 3-day DT     │ 5-day DT +   │ Research Scout +  │
│ (nouvelle    │ (compressed) │ (standard)   │ Research     │ Full DT + Sprint  │
│ feature)     │              │              │ (12j)        │ + A/B (25j)       │
├──────────────┼──────────────┼──────────────┼──────────────┼───────────────────┤
│ VALIDATE     │ Quick User   │ A/B Test +   │ Design       │ Sprint + A/B +    │
│ (tester      │ Test (5      │ User Journey │ Sprint 5j    │ Analytics +       │
│ solution)    │ users, 2j)   │ (5j)         │              │ Feedback (15j)    │
├──────────────┼──────────────┼──────────────┼──────────────┼───────────────────┤
│ EXECUTE      │ Story Map    │ Impact Map + │ Lean UX      │ Complete DT →     │
│ (planifier   │ (features)   │ Story Map    │ Canvas +     │ Personas →        │
│ roadmap)     │ (2j)         │ (5j)         │ Both (8j)    │ Journey → Impact  │
│              │              │              │              │ → Story (18j)     │
├──────────────┼──────────────┼──────────────┼──────────────┼───────────────────┤
│ MEASURE      │ Analytics    │ Analytics +  │ Analytics +  │ Full Analytics +  │
│ (comprendre  │ Interpreter  │ Qualitative  │ Qualitative  │ Qualitative +     │
│ performance) │ (2j)         │ Feedback (4j)│ + Journey    │ Personas Update + │
│              │              │              │ (8j)         │ A/B Tests (15j)   │
└──────────────┴──────────────┴──────────────┴──────────────┴───────────────────┘
```

### Comment Utiliser la Matrice

**Étape 1 : Identifier votre besoin** (ligne)
- AUDIT : Problème existe, besoin diagnostiquer
- EXPLORE : Nouveau projet/feature, besoin découvrir
- VALIDATE : Solution existe, besoin tester
- EXECUTE : Besoin planifier, prioriser
- MEASURE : Produit live, besoin comprendre performance

**Étape 2 : Évaluer profondeur souhaitée** (colonne)
- QUICK : Urgence, insights rapides suffisent
- STANDARD : Délai normal, besoin actionnable
- DEEP : Temps disponible, besoin complet
- COMPLETE : Projet critique, all-in analysis

**Étape 3 : Sélectionner workflow** (intersection ligne × colonne)

**Exemple :**
- Besoin = AUDIT
- Profondeur = STANDARD (1 semaine disponible)
- → Workflow recommandé : **Nielsen + Bastien & Scapin** (5 jours)

---

## Workflow Patterns

Les workflows multi-agents suivent 4 patterns principaux.

### Pattern 1 : Sequential Pipeline

**Structure :** Agent A → Agent B → Agent C → Agent D

**Quand utiliser :**
- Outputs sont **cumulatifs** (B needs A output, C needs B output)
- Apprentissage progressif (chaque agent affine compréhension)

**Avantages :**
- ✅ Clarté (flow linéaire)
- ✅ Chaque agent enrichit le précédent
- ✅ Context preserved (chain of reasoning)

**Inconvénients :**
- ❌ Plus lent (pas de parallelization)
- ❌ Blocking (si Agent B retardé, tout workflow retardé)

**Exemple : Discovery to Design**

```
1. UX Research Scout
   ↓ (competitive insights)
2. Design Thinking Facilitator
   ↓ (empathy insights)
3. Persona Generator
   ↓ (formal personas)
4. User Journey Mapper
   ↓ (journey maps)
5. Impact Mapping Facilitator
   ↓ (business goals aligned)
   → Final Roadmap
```

**Handoff Protocol :**
- Chaque agent reçoit output précédent + context document
- Format standardisé (voir Handoff Protocols section)

---

### Pattern 2 : Triangulation Convergence

**Structure :**
```
Agent A ──┐
Agent B ──┤→ Consolidation Agent → Decision
Agent C ──┘
```

**Quand utiliser :**
- Besoin **multiple perspectives** sur même problème
- Augmenter **confiance** via convergence
- Identifier **problèmes systémiques** (détectés par tous)

**Avantages :**
- ✅ High confidence (cross-validation)
- ✅ Détecte blind spots (A voit ce que B manque)
- ✅ Parallelization possible (A, B, C simultanés)

**Inconvénients :**
- ❌ Requiert agent de consolidation
- ❌ Potential contradictions (à résoudre)

**Exemple : Multi-Framework Audit**

```
UX Auditor Nielsen ──────────┐
                             │
UX Auditor Bastien & Scapin ─┤→ Multi-Framework Analyzer → Prioritized Roadmap
                             │
Accessibility WCAG Checker ──┘
```

**Convergence Logic :**
- **Finding détecté par 3 agents** = P0 (high confidence, critical)
- **Finding détecté par 2 agents** = P1 (important)
- **Finding détecté par 1 agent** = P2 (monitor, lower confidence)

---

### Pattern 3 : Branching Workflows

**Structure :**
```
Start → Diagnostic Agent
            ├─→ Branch A (if condition X)
            ├─→ Branch B (if condition Y)
            └─→ Branch C (if condition Z)
```

**Quand utiliser :**
- Besoin initial **vague** (routing needed)
- **Différents chemins** selon diagnostic
- **Adaptive** workflows (ajuste selon feedback)

**Avantages :**
- ✅ Efficient (pas de wasted effort sur wrong path)
- ✅ Personalized (adapté au cas spécifique)

**Inconvénients :**
- ❌ Requiert bon diagnostic initial
- ❌ Complexité de routing

**Exemple : Conversational UX Advisor Routing**

```
User Need (vague: "UX help")
    ↓
Conversational UX Advisor (diagnose)
    ├─→ If AUDIT needed → Nielsen/B&S
    ├─→ If EXPLORE needed → Design Thinking
    ├─→ If VALIDATE needed → A/B Test
    └─→ If MEASURE needed → Analytics + Feedback
```

---

### Pattern 4 : Feedback Loop

**Structure :**
```
Execute → Measure → Analyze → Improve → Execute (repeat)
```

**Quand utiliser :**
- **Continuous improvement** (pas one-shot project)
- **Iterative design** (launch → test → iterate)
- **Product en vie** (metrics monitoring ongoing)

**Avantages :**
- ✅ Continuous learning
- ✅ Data-driven iterations
- ✅ Adaptability

**Inconvénients :**
- ❌ Time-intensive (ongoing effort)
- ❌ Requiert discipline (loop consistency)

**Exemple : Feature Launch with Validation Loop**

```
1. Design Thinking → Feature concept
2. Design Sprint → Prototype + Test
3. Launch → Feature live
4. A/B Test Analyst → Measure performance
5. Analytics Interpreter → Understand metrics
6. Qualitative Feedback → Why metrics are X
7. User Journey Mapper → Visualize pain points
8. → Iterate design (back to step 1 or 2)
```

**Loop Cadence :**
- **Weekly** : Quick iterations (A/B tests)
- **Monthly** : Feature-level improvements
- **Quarterly** : Strategic UX audits

---

## Handoff Protocols

### Standard Handoff Template

Chaque transition Agent A → Agent B utilise ce template standardisé.

```markdown
## Handoff : [Agent Source] → [Agent Destination]

### Context Preserved
**Project :** [Product name, phase, objectives]
**Users :** [Target audience, segments, key characteristics]
**Constraints :** [Time, budget, scope limitations]
**Stakeholders :** [Who's involved, decision-makers]

### Output from [Agent Source]
**Key Findings :**
- [Finding 1 - brief]
- [Finding 2 - brief]
- [Finding 3 - brief]

**Artifacts :**
- [Link to full report]
- [Screenshots / data files]
- [Quotes / evidence]

**Recommendations for Next Agent :**
- [What to focus on]
- [Questions to answer]

### Input for [Agent Destination]
**Focus Areas :**
1. [Priority 1 - based on previous findings]
2. [Priority 2]

**Open Questions :**
- [Question 1 that Agent Destination should answer]
- [Question 2]

**Success Criteria :**
- [What good looks like]
- [Expected output format]

### Timeline
- [Agent Source] completed : [Date]
- [Agent Destination] start : [Date]
- [Agent Destination] deadline : [Date]
```

### Handoff Example : Analytics → Qualitative

```markdown
## Handoff : Analytics Interpreter → Qualitative Feedback Analyzer

### Context Preserved
**Project :** SaaS B2B Dashboard Redesign
**Users :** Data analysts, daily users, 500 active users
**Constraints :** 2-week timeline, Q2 launch, limited budget
**Stakeholders :** Design team, Product Manager, CTO

### Output from Analytics Interpreter
**Key Findings :**
- 68% drop-off at "Advanced Filters" step (critical funnel issue)
- Power users (20%) use 5+ features, Casual users (60%) use 2 features max
- Mobile usage <5% (desktop-dominant product)
- Session duration : Power 45min avg, Casual 8min avg

**Artifacts :**
- GA4 funnel report (attached)
- Cohort analysis spreadsheet
- Feature usage heatmaps

**Recommendations for Next Agent :**
- Investigate WHY 68% drop-off at Advanced Filters
- Understand power user mental models (what makes them successful)

### Input for Qualitative Feedback Analyzer
**Focus Areas :**
1. **Priority 1** : Analyze support tickets + user feedback about "filters", "advanced features", "complexity"
2. **Priority 2** : Extract themes about learning curve, onboarding gaps

**Open Questions :**
- Is 68% drop-off due to UI confusion or feature complexity itself?
- What workarounds do users mention for filter functionality?
- Do power users vs casual users describe different pain points?

**Success Criteria :**
- Clear themes explaining drop-off (3-5 themes minimum)
- Actionable quotes for design team
- Recommendations aligned with quantitative findings

### Timeline
- Analytics Interpreter completed : Jan 15
- Qualitative Feedback Analyzer start : Jan 16
- Deadline : Jan 18
```

---

## Use Cases Détaillés

### Use Case 1 : Quick Audit for Sprint Planning

**Context :**
- Équipe produit planning prochain sprint (2 semaines)
- Besoin prioriser corrections UX
- Timeline : 2 jours max pour insights

**Workflow : Nielsen Sprint (Quick Audit)**

```
Day 1 (3h) :
└─ UX Auditor Nielsen (Sprint mode)
   - Kickoff : Collect screenshots, brief context (30min)
   - Audit : Evaluate against 10 heuristics (2h)
   - Output : Quick findings (30min)

Day 2 (2h) :
└─ Nielsen Audit (continued)
   - Prioritization : Impact × Frequency matrix (1h)
   - Action Items : P0/P1/P2 list for sprint (1h)
   - Delivery : Sprint-ready backlog items
```

**Deliverable :**
- Action Items Report (format sprint)
  - P0 (Must Fix This Sprint) : 3-5 items
  - P1 (Should Fix Next Sprint) : 5-8 items
  - P2 (Backlog) : 10+ items
- Effort estimate per item (S/M/L)

**Success Metrics :**
- ✅ Team has clear P0 list for sprint planning
- ✅ Delivered within 2 days
- ✅ Actionable (not theoretical)

---

### Use Case 2 : Complete Multi-Framework Audit

**Context :**
- Refonte majeure (dashboard SaaS B2B)
- Besoin analyse complète multi-perspectives
- Timeline : 2 semaines
- Audience : Design team + Stakeholders C-level

**Workflow : Multi-Framework Triangulation + Consolidation**

```
Week 1 :
├─ Day 1-2 : UX Auditor Nielsen (parallel)
│           10 heuristics, quick scan
│
├─ Day 2-3 : UX Auditor Bastien & Scapin (parallel)
│           18 critères, cognitive load focus
│
└─ Day 3-4 : Accessibility WCAG Checker (parallel)
            WCAG 2.1 AA compliance

Week 2 :
├─ Day 5-7 : Multi-Framework Analyzer
│           Consolidate 3 audits
│           Cross-reference findings
│           Prioritization matrix
│
└─ Day 8-9 : Final Reports
            - Detailed (design team)
            - Executive Summary (C-level)
            - Sprint Action Items (dev team)
```

**Convergence Analysis :**

| Finding | Nielsen | B&S | WCAG | Priority |
|---------|---------|-----|------|----------|
| Advanced Filters Complexity | ✅ Violates H#6 | ✅ High cognitive load | ✅ Keyboard nav broken | **P0** |
| Info Overload Dashboard | ✅ H#8 violation | ✅ Density issue | ❌ | **P0** |
| Color Contrast Issues | ❌ | ❌ | ✅ 12 violations AA | **P1** |

**Deliverables :**
1. **Detailed Report** (30 pages) : Findings per framework, screenshots, recommendations
2. **Executive Summary** (2 pages) : Top 3 issues, ROI estimate, timeline
3. **Sprint Action Items** (1 page) : Backlog-ready P0/P1

**Success Metrics :**
- ✅ High confidence findings (triangulated)
- ✅ Clear prioritization (P0/P1/P2)
- ✅ Multi-audience deliverables

---

### Use Case 3 : Discovery to Launch Workflow

**Context :**
- Startup launching nouveau produit SaaS
- Pas de user research existante
- Timeline : 6 semaines (discovery → design → validate)

**Workflow : Sequential Pipeline (Research → DT → Personas → Journey → Sprint → A/B)**

```
Week 1 : Research
└─ UX Research Scout
   - Competitive analysis (3 competitors)
   - Best practices gathering
   - Compliance requirements check

Week 2-3 : Discovery + Definition
├─ Design Thinking Facilitator (5 phases, 2 weeks compressed)
│  ├─ Empathize (3 days) : User interviews (10 users)
│  ├─ Define (2 days) : POV statements, HMW questions
│  ├─ Ideate (2 days) : Brainstorming, Crazy 8s
│  ├─ Prototype (3 days) : Low-fi prototypes
│  └─ Test (2 days) : 5 user tests
│
└─ Handoff : Insights → Personas

Week 3-4 : Formalization
├─ Persona Generator
│  - Transform DT insights into formal personas (3 personas)
│
└─ User Journey Mapper
   - Map journeys for each persona (as-is + to-be)

Week 5 : Validation Sprint
└─ Design Sprint Conductor (5 days)
   - Refine prototype (high-fi Figma)
   - Test with 5 new users
   - GO/NO-GO decision

Week 6 : Launch + Measure
├─ Launch MVP
└─ A/B Test Analyst
   - Setup experiments (onboarding flow variants)
   - Measure adoption
```

**Handoffs Critiques :**
1. Research Scout → Design Thinking : Competitive insights inform empathy phase
2. Design Thinking → Personas : User interview insights → formal personas
3. Personas → Journey Mapper : Personas drive journey mapping
4. Journey → Design Sprint : Journeys identify critical moments to prototype

**Deliverables Finaux :**
- 3 Data-driven Personas
- User Journey Maps (as-is + to-be)
- High-fi Prototype (Figma)
- A/B Test Results (Week 6+)
- GO/PIVOT Decision

**Success Metrics :**
- ✅ User-validated product (not assumptions)
- ✅ Clear personas guiding design
- ✅ Data-driven iteration post-launch

---

### Use Case 4 : Analytics-Driven Improvement

**Context :**
- Produit mature (2 ans live)
- Engagement metrics dropped 30% last quarter
- Besoin comprendre pourquoi + fix

**Workflow : Parallel Quant+Qual → Journey Mapping → Solutions**

```
Week 1 : Data Collection (Parallel)
├─ Analytics Interpreter
│  - GA4 analysis : Funnels, drop-offs, cohorts
│  - Identify where metrics dropped
│
└─ Qualitative Feedback Analyzer (parallel)
   - Support tickets analysis (last 3 months)
   - NPS feedback, app store reviews
   - Identify themes

Week 2 : Synthesis
├─ Triangulation : Quant + Qual insights
│  - Where analytics show drop → What users say
│
└─ User Journey Mapper
   - Visualize pain points
   - Emotion curve (before vs after metric drop)

Week 3 : Ideation
└─ Design Thinking Facilitator (Ideate phase only)
   - HMW questions based on journey pain points
   - Solution ideation workshop (1 day)
   - Prioritize solutions (Impact × Effort)

Week 4 : Validation
└─ A/B Test Analyst
   - Design experiments for top 3 solutions
   - Launch tests
   - Measure impact on engagement

Week 5+ : Feedback Loop
└─ Monitor metrics → Iterate
```

**Deliverables :**
- Root Cause Analysis (why 30% drop)
- Journey Maps (current state with pain points)
- Prioritized Solutions Roadmap
- A/B Test Results

**Success Metrics :**
- ✅ Engagement recovered (target : +20% from baseline)
- ✅ Clear understanding of root cause
- ✅ Data-driven solutions (not guesses)

---

## Best Practices

### DO ✅

1. **Start with diagnostic BEFORE selecting workflow**
   - Understand problem first
   - Then choose workflow (pas l'inverse)

2. **Parallelize when agents are independent**
   - Nielsen + B&S + WCAG can run simultaneously
   - Gain time (3 days instead of 9)

3. **Preserve context across handoffs**
   - Use standardized handoff template
   - Document decisions and rationale

4. **Identify convergences (high confidence)**
   - Finding detected by 3 agents = priorité haute
   - Triangulation = validation

5. **Adapt workflow si blockers**
   - Workflow not rigid
   - If Agent B blocked, skip or replace

6. **Communicate progress regularly**
   - User updates (Day 2, 4, 6)
   - Avoid "black box" feeling

7. **Consolidate findings (pas juxtaposition)**
   - Synthesis > List of separate reports
   - Tell unified story

8. **Match deliverable format to audience**
   - Execs → Executive Summary
   - Design team → Detailed Report
   - Dev team → Sprint Action Items

### DON'T ❌

1. **Don't over-orchestrate simple needs**
   - 1 agent suffit ? Don't use 5 agents

2. **Don't ignore dependencies**
   - Agent B needs Agent A output → Sequential obligatoire
   - Pas de parallelization si dépendance

3. **Don't lose global context**
   - Maintain narrative cohérente
   - Not "silos" (each agent isolated)

4. **Don't skip handoff documentation**
   - Next agent MUST have context
   - Pas de "figure it out yourself"

5. **Don't ignore contradictions between agents**
   - Agent A vs B disagree → Analyze why
   - Resolve, don't hide

6. **Don't under-estimate timing**
   - Agents take time (respect process)
   - Handoffs take time (documentation)

7. **Don't force rigid workflow if context changes**
   - Adapt if new info emerges
   - Flexibility > dogmatisme

---

## Ressources

**Agents Orchestrables :**
- Voir `/agents/` (18 agents disponibles)
- `ux-workflow-coordinator.md` - Meta-orchestrateur
- `conversational-ux-advisor.md` - Routing intelligent

**Workflows Avancés :**
- `docs/advanced-workflows.md` - Workflows end-to-end détaillés

**Frameworks de Référence :**
- `/frameworks/` (7 frameworks)

**Templates :**
- `/templates/` (10 templates)

---

**Version** : 1.0
**Auteurs** : UX Agents Repository Team
**Licence** : [À définir]
