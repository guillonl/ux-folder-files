# Lean UX Canvas Template

## 📋 À propos de ce template

Le **Lean UX Canvas** (Jeff Gothelf) est un outil stratégique pour aligner les équipes produit autour d'hypothèses testables et d'apprentissage rapide. Il applique les principes du Lean Startup (Build-Measure-Learn) au design UX.

**Quand l'utiliser :**
- Lancement d'un nouveau produit ou feature majeure
- Transformation d'assumptions en expérimentations mesurables
- Définition de MVPs pour valider des hypothèses critiques
- Alignement cross-fonctionnel (Product, Design, Dev, Business)

**Durée de remplissage :** 2-4 heures (session collaborative)

---

## 🎯 Lean UX Canvas - 8 Boxes

```
┌─────────────────────────────────────────────────────────────────┐
│                      LEAN UX CANVAS                              │
│                   [Nom du Projet / Feature]                      │
│                   Date: [Date] | Team: [Participants]            │
├──────────────────────────────────┬──────────────────────────────┤
│ 1. BUSINESS PROBLEM              │ 2. BUSINESS OUTCOMES         │
│ What problem are we solving?     │ How will we know we've       │
│                                  │ succeeded?                   │
│                                  │                              │
│                                  │                              │
│                                  │                              │
│                                  │                              │
├──────────────────────────────────┼──────────────────────────────┤
│ 3. USERS & CUSTOMERS             │ 4. USER BENEFITS             │
│ Who are our users?               │ What do users get?           │
│                                  │                              │
│                                  │                              │
│                                  │                              │
│                                  │                              │
│                                  │                              │
├──────────────────────────────────┴──────────────────────────────┤
│ 5. SOLUTION IDEAS                                                │
│ What could we build?                                             │
│                                                                  │
│                                                                  │
│                                                                  │
│                                                                  │
├──────────────────────────────────────────────────────────────────┤
│ 6. HYPOTHESES                                                    │
│ What are we assuming to be true?                                 │
│                                                                  │
│                                                                  │
│                                                                  │
│                                                                  │
├──────────────────────────────────────────────────────────────────┤
│ 7. WHAT'S THE MOST IMPORTANT THING WE NEED TO LEARN FIRST?      │
│                                                                  │
│                                                                  │
│                                                                  │
├──────────────────────────────────────────────────────────────────┤
│ 8. WHAT'S THE LEAST AMOUNT OF WORK TO LEARN THE NEXT MOST       │
│    IMPORTANT THING? (MVP)                                        │
│                                                                  │
│                                                                  │
│                                                                  │
└──────────────────────────────────────────────────────────────────┘
```

---

## 📝 Box 1 : BUSINESS PROBLEM

### What business problem are we solving?

**Instructions :** Articuler clairement le problème business (WHY). Centré sur le problème, pas la solution.

**Format Problem Statement :**
```
[Utilisateur/Segment] a du mal à [Action/Tâche] ce qui cause [Conséquence business]
```

**Exemple :**
```
Les nouveaux utilisateurs freemium abandonnent après 3-7 jours sans atteindre leur "aha moment". Seulement 15% deviennent des utilisateurs actifs hebdomadaires (objectif : 40%). Cela représente une perte de 300K€/an en MRR potentiel.
```

**Votre Business Problem :**
```
[Décrivez le problème business]

Quantification:
- [Métrique actuelle]: [Valeur]
- [Impact business]: [€, users perdus, churn rate, etc.]
- [Conséquence si non résolu]: [...]
```

---

## 📝 Box 2 : BUSINESS OUTCOMES

### How will we know we've succeeded?

**Instructions :** Définir les résultats business mesurables. Outcomes (pas outputs).

**Format Outcome Statement :**
```
[Verbe d'action] [Métrique] de [Baseline] à [Target] d'ici [Timeline]
```

**Types de outcomes :**
- Revenue (MRR, ARPU, conversion)
- Engagement/Retention (WAUs, retention 30j, churn)
- Acquisition (signups, CAC)
- Efficiency (support tickets, time to resolution)
- Satisfaction (NPS, CSAT, SUS)

---

### Vos Business Outcomes

**Primary Outcomes (Lagging Indicators) :**

| Métrique | Baseline | Target | Timeline | Méthode de mesure |
|----------|----------|--------|----------|-------------------|
| [Ex: Taux d'activation 7j] | 15% | 40% | 6 mois | Mixpanel |
| [Ex: Retention 30j] | 25% | 50% | 6 mois | Google Analytics |

**Secondary Outcomes (Leading Indicators) :**

| Métrique | Baseline | Target | Timeline | Méthode de mesure |
|----------|----------|--------|----------|-------------------|
| [Ex: Onboarding completion] | 30% | 70% | 3 mois | Mixpanel |
| [Ex: Invitations teammates] | 10% | 35% | 3 mois | Analytics |
| [Ex: Time to first value] | 5 jours | < 2 jours | 3 mois | Analytics |

---

## 📝 Box 3 : USERS & CUSTOMERS

### Who are our users and customers?

**Instructions :** Identifier les segments utilisateurs cibles (2-4 segments max). Distinguer users vs customers si applicable (B2B).

**Segmentation :**
- Démographique (âge, genre, localisation)
- Psychographique (valeurs, motivations)
- Comportemental (fréquence usage, niveau expertise)
- Firmographique B2B (taille entreprise, industrie)

---

### Vos Segments Utilisateurs

**Segment 1 : [Nom du segment]**
- **Type :** Primary / Secondary / Tertiary
- **Description :** [Qui sont-ils ? Caractéristiques clés]
- **Taille :** [% de user base ou nombre absolu]
- **Priorité :** HIGH / MEDIUM / LOW
- **Justification :** [Pourquoi ce segment est critique]

**Segment 2 : [Nom du segment]**
- **Type :** [...]
- **Description :** [...]
- **Taille :** [...]
- **Priorité :** [...]
- **Justification :** [...]

**Segment 3 : [Nom du segment]** (optionnel)
- **Type :** [...]
- **Description :** [...]
- **Taille :** [...]
- **Priorité :** [...]
- **Justification :** [...]

**Non-target :** [Qui NE sont PAS nos utilisateurs cibles]

---

## 📝 Box 4 : USER BENEFITS

### What do users get out of this?

**Instructions :** Articuler ce que les utilisateurs gagnent (user outcomes). User Benefits doivent supporter Business Outcomes.

**Types de user benefits :**
- Time saved (gagner X heures/semaine)
- Effort reduced (simplifier un processus complexe)
- Quality improved (meilleurs résultats)
- Confidence increased (réduire anxiété)
- Revenue/Income increased (gagner plus)
- Status/Recognition (reconnaissance)
- Control/Autonomy (sentiment de maîtrise)

**Format JTBD (Jobs to be Done) :**
```
Quand [situation], je veux [motivation], afin de [outcome attendu]
```

---

### Vos User Benefits

**Primary Benefits (Segment prioritaire) :**

1. **[Benefit 1]** :
   - Description : [Ex: Gagner 2h/semaine sur gestion admin projets]
   - Lien avec business outcome : [Ex: → Plus de temps disponible → Usage accru → Retention]

2. **[Benefit 2]** :
   - Description : [Ex: Ne jamais manquer une deadline grâce aux rappels auto]
   - Lien avec business outcome : [Ex: → Réduire stress → Satisfaction → NPS élevé]

3. **[Benefit 3]** :
   - Description : [Ex: Impressionner clients avec livrables professionnels]
   - Lien avec business outcome : [Ex: → Image pro → Word-of-mouth → Acquisition]

**Secondary Benefits :**

4. [Benefit 4]
5. [Benefit 5]

**Job to be Done :**
```
Quand [situation],
je veux [motivation],
afin de [outcome attendu]
```

---

## 📝 Box 5 : SOLUTION IDEAS

### What could we build or create?

**Instructions :** Brainstormer largement des solutions possibles. Diverger avant de converger.

**Types de solutions :**
- Features produit
- Nouveaux produits
- Contenus (guides, tutoriels, templates)
- Services (onboarding, support, consulting)
- Intégrations (APIs, automations)
- Process changes

**Techniques de brainstorming :**
- Crazy 8s (8 idées en 8 minutes)
- SCAMPER (Substitute, Combine, Adapt, Modify, Put to another use, Eliminate, Reverse)
- HMW questions (How Might We)

---

### Vos Solution Ideas

**Brainstormed Solutions (10-20 idées) :**

1. [Solution 1]
2. [Solution 2]
3. [Solution 3]
4. [Solution 4]
5. [Solution 5]
6. [Solution 6]
7. [Solution 7]
8. [Solution 8]
9. [Solution 9]
10. [Solution 10]
[... 11-20 ...]

**Clustering par thème :**
- **Thème 1 : [Ex: Onboarding UX]** → Solutions #1, #3, #7
- **Thème 2 : [Ex: Content/Education]** → Solutions #2, #5, #9
- **Thème 3 : [Ex: Notifications]** → Solutions #4, #6, #10

**Top 5 Solutions Sélectionnées (Dot Voting) :**

| # | Solution | Type | Votes | Priorité |
|---|----------|------|-------|----------|
| 1 | [Solution X] | Feature | 12 votes | ⭐⭐⭐ Strategic Bet |
| 2 | [Solution Y] | Content | 10 votes | ⭐⭐⭐ Quick Win |
| 3 | [Solution Z] | Feature | 8 votes | ⭐⭐ Strategic Bet |
| 4 | [Solution W] | Service | 7 votes | ⭐⭐ Quick Win |
| 5 | [Solution V] | Integration | 5 votes | ⭐ Experiment |

---

## 📝 Box 6 : HYPOTHESES

### What are we assuming to be true?

**Instructions :** Transformer les solutions sélectionnées en hypothèses testables.

**Format Hypothesis Statement (Jeff Gothelf) :**
```
We believe [doing this / building this feature]
For [these users / personas]
Will achieve [this outcome / business result]
We will know we're right when we see [this measurable signal / metric]
```

**En français :**
```
Nous croyons que [faire ceci / construire cette feature]
Pour [ces utilisateurs / personas]
Permettra d'atteindre [ce résultat / business outcome]
Nous saurons que nous avons raison quand nous verrons [ce signal mesurable / métrique]
```

---

### Vos Hypothèses

#### HYPOTHESIS 1 : [Nom hypothèse] ⚠️ CRITICAL

**Solution :** [Solution X de Box 5]

**Hypothesis Statement :**
```
Nous croyons que [doing X]
Pour [users Y]
Permettra d'atteindre [outcome Z]
Nous saurons que nous avons raison quand:
  - [Métrique 1] ≥ [Seuil]
  - [Métrique 2] ≥ [Seuil]
  - [Métrique 3] ≥ [Seuil]
```

**Metadata :**
- **Confiance :** [0-100%] (ex: 50% = Medium)
- **Risque si fausse :** HIGH / MEDIUM / LOW
- **Effort :** [Person-weeks - ex: 5 person-weeks]
- **Priorité :** TEST FIRST / TEST SECOND / TEST LATER

---

#### HYPOTHESIS 2 : [Nom hypothèse]

[Répéter la structure ci-dessus]

---

#### HYPOTHESIS 3 : [Nom hypothèse]

[Répéter la structure ci-dessus]

---

#### HYPOTHESIS 4-5 : [Optionnel]

---

**Priorisation Hypotheses (Risk vs Importance Matrix) :**

```
Importance (Impact)
  ↑
H │  [Hypothesis 3]  │ [Hypothesis 1] ⚠️
  │  Test later      │ TEST FIRST
  │──────────────────┼────────────────
L │  [Hypothesis 4]  │ [Hypothesis 2]
  │  Don't test      │ Test if capacity
  └──────────────────┴────────────────→
      Low              High       Risk
```

---

## 📝 Box 7 : WHAT'S THE MOST IMPORTANT THING WE NEED TO LEARN FIRST?

### Critical Learning Priority

**Instructions :** Identifier l'apprentissage critique - quelle hypothèse, si fausse, fait tout s'effondrer ?

**Critères :**
- High Risk (si fausse, conséquence grave)
- High Uncertainty (confiance < 50%)
- Foundational (bloque les autres hypothèses)
- Blocking impact (débloque décisions futures)

---

### Votre Critical Learning

**Hypothèse critique :** [Hypothesis #X - nom]

**Énoncé de l'apprentissage :**
```
Nous devons apprendre si [hypothèse clé]
Parce que:
  - Si VRAI: [Conséquence positive]
  - Si FAUX: [Conséquence négative + nécessité de pivot]
```

**Exemple :**
```
Nous devons apprendre si simplifier l'onboarding de 7 à 3 étapes augmentera réellement le taux de completion de 30% à 70%+

Parce que:
  - Si VRAI:
    → On peut investir 5 sem dev sur wizard complet
    → On atteint notre business outcome (activation 15% → 35%+)

  - Si FAUX:
    → Le problème n'est PAS la longueur de l'onboarding
    → Peut-être incompréhension value prop ou manque motivation
    → On évite de gaspiller 5 sem dev
    → On doit pivoter vers autre hypothèse (templates, education)
```

**Risk Assessment :**
- **Risque si fausse :** HIGH / MEDIUM / LOW
- **Confiance actuelle :** [0-100%]
- **Blocking impact :** YES / NO

---

## 📝 Box 8 : WHAT'S THE LEAST AMOUNT OF WORK TO LEARN?

### MVP Definition

**Instructions :** Définir le **MVP (Minimum Viable Product)** pour valider l'hypothèse critique avec minimum effort.

**Principe :** "Build the lightest thing to test the riskiest assumption"

**Types de MVPs (du moins au plus d'effort) :**
1. **Pretotyping / Fake Door** : Tester l'intérêt (1-3 jours)
2. **Concierge MVP** : Service manuel (1-2 semaines)
3. **Wizard of Oz MVP** : Fake automation (2-3 semaines)
4. **Prototype interactif** : Figma haute-fidélité + user tests (1-2 semaines)
5. **Functional MVP / A/B Test** : Version simplifiée en production (3-6 semaines)

---

### Votre MVP

**MVP Type :** [Pretotype / Concierge / Wizard of Oz / Prototype / Functional]

**Description :**
```
What we'll build:
[Décrire précisément le MVP - 3-5 phrases]
```

**Exemple :**
```
MVP Type: Prototype interactif Figma + User tests modérés (5 users)

What we'll build:
- Prototype Figma haute-fidélité du wizard 3-step avec interactions
- Step 1: "Create first project" (nom, type, deadline)
- Step 2: "Invite team" (optional, skip allowed)
- Step 3: "Set up workflow" (template choice)
- Testable en 5-10 minutes avec 5 designers freelance
```

---

### Validation Metrics

**Primary Metric :**
- **Métrique :** [Ex: Task completion rate]
- **Success (✅ GO)** : ≥ [Ex: 80%] → Build functional MVP
- **Gray zone (⚠️ ITERATE)** : [Ex: 50-80%] → Improve design, re-test
- **Fail (❌ PIVOT)** : < [Ex: 50%] → Hypothesis invalidated, try other solution

**Secondary Metrics :**
- **Métrique 2 :** [Ex: Time to complete]
  - Success : < [Ex: 5 min]
  - Fail : > [Ex: 10 min]

- **Métrique 3 :** [Ex: SUS score (System Usability Scale)]
  - Success : > [Ex: 70]
  - Fail : < [Ex: 50]

**Qualitative Metrics :**
- **User sentiment post-test**
  - Success : [Ex: 4+ users say "easy, intuitive"]
  - Fail : [Ex: 3+ users say "confusing, frustrating"]

---

### Timeline & Budget

**Timeline :**
- **Week 1-2 :** [Ex: Design prototype Figma]
- **Week 3 :** [Ex: Recruit + moderate 5 user tests]
- **Week 4 :** [Ex: Synthesis + decision]
- **Total :** [Ex: 4 weeks]

**Budget :**
- **Resources :** [Ex: 1 designer (2 weeks), 1 PM (1 week)]
- **Cost :** [Ex: User incentives 5 × 50€ = 250€]
- **Total cost :** [Ex: 250€ + internal resources]

**Owner :** [Nom du responsable]

---

### Decision Framework

```
IF [Primary metric] ≥ [Success threshold] AND [Secondary metrics OK]
  → GO: Build functional MVP / A/B test
  → Invest [X weeks] dev

ELSE IF [Primary metric] in gray zone ([X-Y%])
  → ITERATE: Improve design based on friction points
  → Re-test with [N] new users ([X] weeks)

ELSE IF [Primary metric] < [Fail threshold]
  → PIVOT: Hypothesis invalidated
  → Explore alternative hypotheses (Box 6 - Hypothesis 2 or 3)
  → Post-mortem: Why did it fail? What insights?
```

---

## ✅ Validation Lean UX Canvas

### Checklist de qualité

- [ ] **Business Problem** clair et quantifié (pas une solution déguisée)
- [ ] **Business Outcomes** mesurables avec baseline → target → timeline
- [ ] **Users & Customers** segmentés et priorisés (2-4 segments max)
- [ ] **User Benefits** articulés avec lien vers business outcomes
- [ ] **Solution Ideas** brainstormées (10+ idées), top 5 sélectionnées
- [ ] **Hypotheses** formulées avec success criteria clairs (3-5 hypothèses)
- [ ] **Critical Learning** identifié (1 hypothèse la plus risquée)
- [ ] **MVP** défini avec type, metrics, timeline, decision framework
- [ ] **Alignment cross-fonctionnel** : Product, Design, Dev, Business impliqués

---

## 📎 Métadonnées

**Projet / Feature :** [Nom]
**Date de création :** [Date]
**Créé par :** [Équipe / Participants]
**Dernière mise à jour :** [Date]
**Phase :** Discovery / Validation / Build / Measure / Learn
**Statut :** Draft / In Progress / Validated / Pivoted

---

## 🔗 Next Steps

Après avoir complété le Lean UX Canvas :

1. **Recruter users** pour MVP test (si applicable)
2. **Créer MVP** selon Box 8 (prototype, concierge, functional)
3. **Lancer expérimentation** (user tests, A/B test, etc.)
4. **Mesurer résultats** (metrics tracking rigoureux)
5. **Décision** : GO / ITERATE / PIVOT basé sur decision framework
6. **Update canvas** : Ajuster hypothèses basé sur learnings

**Build-Measure-Learn Cycle :**
- BUILD : [MVP défini]
- MEASURE : [Metrics définies]
- LEARN : [Décision GO/ITERATE/PIVOT]
- Durée cycle : [X semaines]

**Rituels de suivi :**
- Weekly standup : Progression MVP, blockers
- Post-MVP review : Analyse résultats, décision
- Canvas update : Ajuster hypothèses, itérer

---

## 📚 Ressources

- **Méthodologie** : Jeff Gothelf - "Lean UX" (livre)
- **Site officiel** : https://www.jeffgothelf.com/lean-ux-canvas
- **Template gratuit** : https://www.jeffgothelf.com/blog/leanuxcanvas-v2
- **Livre** : "Lean UX: Designing Great Products with Agile Teams" (2021)
- **Related** : Eric Ries - "Lean Startup" (Build-Measure-Learn)

---

**Template version** : 1.0 | **Dernière mise à jour** : Janvier 2026
