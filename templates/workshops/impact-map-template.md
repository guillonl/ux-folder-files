# Impact Map Template

## 📋 À propos de ce template

L'**Impact Map** est un outil de planification stratégique créé par Gojko Adzic qui relie clairement les objectifs business (WHY) aux acteurs (WHO), impacts comportementaux (HOW) et deliverables (WHAT). Elle évite de construire des features sans impact business mesurable.

**Quand l'utiliser :**
- Planification roadmap produit stratégique
- Alignement business-produit-design-dev
- Priorisation data-driven des deliverables
- Identification d'hypothèses critiques à valider

**Durée de création :** 3-4 heures (session collaborative)

---

## 🎯 Structure Impact Map (4 Niveaux)

```
GOAL (WHY - Objectif business)
  │
  ├─ ACTOR 1 (WHO - Qui peut influencer le goal)
  │    │
  │    ├─ IMPACT 1.1 (HOW - Changement comportemental)
  │    │    │
  │    │    ├─ DELIVERABLE 1.1.1 (WHAT - Feature/Produit)
  │    │    ├─ DELIVERABLE 1.1.2
  │    │    └─ DELIVERABLE 1.1.3
  │    │
  │    └─ IMPACT 1.2
  │         │
  │         └─ DELIVERABLE 1.2.1
  │
  ├─ ACTOR 2
  │    │
  │    └─ IMPACT 2.1
  │         │
  │         ├─ DELIVERABLE 2.1.1
  │         └─ DELIVERABLE 2.1.2
  │
  └─ ACTOR 3
       └─ IMPACT 3.1
            └─ DELIVERABLE 3.1.1
```

---

## 📊 Niveau 1 : GOAL (WHY - Objectif Business)

### Instructions

Définir **1 objectif business principal** clair, mesurable et aligné avec la stratégie.

**Format SMART :**
```
[Verbe d'action] [Métrique] [Cible] d'ici [Date]
```

**Exemples :**
- Augmenter le taux de rétention à 30 jours de 45% à 65% d'ici Q3 2026
- Réduire le taux d'abandon panier de 75% à 60% d'ici Q2 2026
- Atteindre 100K utilisateurs actifs mensuels d'ici fin 2026

---

### Votre Goal

**Goal principal :**
```
[Verbe d'action] [Métrique] [Cible] d'ici [Date]
```

**Métriques de succès :**
- **Baseline (situation actuelle) :** [Valeur actuelle]
- **Target (cible) :** [Valeur cible]
- **Timeline :** [Horizon temporel]
- **Méthode de mesure :** [Outil - ex: Google Analytics, Mixpanel]

**Alignment stratégique :**
- **OKR associé (si applicable) :** [Lien avec OKR]
- **Stratégie produit :** [Lien avec stratégie]
- **Stakeholder sponsor :** [Nom]

---

## 📊 Niveau 2 : ACTORS (WHO - Acteurs Clés)

### Instructions

Identifier **tous les acteurs** (personnes, groupes, systèmes) qui peuvent influencer l'atteinte du goal, positivement ou négativement.

**Types d'acteurs :**
- **Acteurs primaires** : Utilisateurs directs du produit
- **Acteurs secondaires** : Stakeholders indirects (partenaires, support)
- **Acteurs tertiaires** : Influenceurs externes (régulateurs, médias)
- **Systèmes** : APIs, plateformes, legacy systems

---

### Vos Acteurs

| # | Acteur | Type | Description | Influence | Priorité |
|---|--------|------|-------------|-----------|----------|
| 1 | [Ex: Utilisateurs freemium inactifs] | Primary | [Users n'ayant pas engagé sur 30j] | High | ⭐⭐⭐ |
| 2 | [...] | Primary/Secondary/Tertiary | [...] | High/Medium/Low | ⭐⭐⭐/⭐⭐/⭐ |
| 3 | [...] | [...] | [...] | [...] | [...] |
| 4 | [...] | [...] | [...] | [...] | [...] |
| 5 | [...] | [...] | [...] | [...] | [...] |

**Top 3-5 acteurs priorisés :**
1. [Acteur 1] - Influence: High - Priorité: ⭐⭐⭐
2. [Acteur 2] - Influence: High - Priorité: ⭐⭐⭐
3. [Acteur 3] - Influence: Medium - Priorité: ⭐⭐

---

## 📊 Niveau 3 : IMPACTS (HOW - Changements Comportementaux)

### Instructions

Pour chaque acteur prioritaire, définir **comment** ils peuvent contribuer au goal via des changements comportementaux **observables et mesurables**.

**Format Impact :**
```
[Acteur] + [Verbe d'action comportemental] + [Contexte/Fréquence]
```

**Exemples :**
- Utilisateurs freemium → Se connectent au moins 3x/semaine
- Support team → Résout les tickets en < 24h (vs 48h actuellement)
- Partenaires → Recommandent activement notre solution (NPS > 8)

---

### Acteur 1 : [Nom de l'acteur 1]

**Type :** Primary | **Influence :** High | **Priorité :** ⭐⭐⭐

#### Impacts Comportementaux

| Impact | Description | Métrique Actuelle | Métrique Cible | Priorité | Value | Effort |
|--------|-------------|-------------------|----------------|----------|-------|--------|
| 1.1 | [Ex: Se connectent 3x/semaine] | 12% | 35% | ⭐⭐⭐ | High | Low |
| 1.2 | [Ex: Complètent leur profil 100%] | 30% | 70% | ⭐⭐⭐ | High | Medium |
| 1.3 | [Ex: Invitent 2+ collègues] | 10% | 35% | ⭐⭐ | Medium | Low |

---

### Acteur 2 : [Nom de l'acteur 2]

**Type :** [...] | **Influence :** [...] | **Priorité :** [...]

#### Impacts Comportementaux

| Impact | Description | Métrique Actuelle | Métrique Cible | Priorité | Value | Effort |
|--------|-------------|-------------------|----------------|----------|-------|--------|
| 2.1 | [...] | [...] | [...] | [...] | [...] | [...] |
| 2.2 | [...] | [...] | [...] | [...] | [...] | [...] |

---

### Acteur 3 : [Nom de l'acteur 3]

[Répéter la structure ci-dessus]

---

## 📊 Niveau 4 : DELIVERABLES (WHAT - Solutions)

### Instructions

Pour chaque impact prioritaire, identifier les **deliverables** (fonctionnalités, produits, services) qui pourraient supporter cet impact.

**Types de deliverables :**
- Features produit
- Contenus (guides, tutoriels)
- Services (support, onboarding)
- Intégrations (APIs)
- Process changes

**Priorisation RICE :**
- **R**each : Combien d'utilisateurs touchés ?
- **I**mpact : Quel impact par utilisateur ? (0.25 - 3)
- **C**onfidence : Quelle confiance ? (0-100%)
- **E**ffort : Combien de person-months ?

**RICE Score = (R × I × C) / E**

---

### Impact 1.1 : [Nom de l'impact 1.1]

**Acteur :** [Acteur 1] | **Métrique cible :** [Ex: 35% se connectent 3x/sem]

#### Deliverables

| # | Deliverable | Type | Description | Effort | RICE | Priorité | Hypothèse critique |
|---|-------------|------|-------------|--------|------|----------|--------------------|
| 1.1.1 | [Ex: Email reminder H+2] | Content | [Envoi auto email CTA] | S (1 sem) | 8000 | ⭐⭐⭐ | ⚠️ [Email augmente connexion de 55% à 75%] |
| 1.1.2 | [...] | Feature/Content/Service | [...] | S/M/L/XL | [...] | ⭐⭐⭐/⭐⭐/⭐ | ⚠️ [...] ou ✅ Validé |
| 1.1.3 | [...] | [...] | [...] | [...] | [...] | [...] | [...] |

---

### Impact 1.2 : [Nom de l'impact 1.2]

[Répéter la structure ci-dessus pour chaque impact]

---

### Impact 2.1 : [Nom de l'impact 2.1]

[Répéter la structure]

---

## 🎯 Roadmap Priorisée

### Instructions

Séquencer les deliverables prioritaires sur la timeline (Q1-Q4 ou autre horizon).

**Principes de séquencement :**
- **RICE score élevé** : Prioriser
- **Quick Wins** : High Value + Low Effort → Q1
- **Strategic Bets** : High Value + High Effort → Q2-Q3
- **Hypothèses critiques** : Valider en premier (prototypes, MVPs)

---

### Q1 [Année] - VALIDATE & QUICK WINS

| Deliverable | Impact supporté | Effort | RICE | Priorité | Owner | Hypothèse critique |
|-------------|-----------------|--------|------|----------|-------|--------------------|
| [Deliverable 1] | [Impact X.X] | S (2 sem) | 8000 | ⭐⭐⭐ | [Nom] | ⚠️ [À valider] |
| [Deliverable 2] | [Impact Y.Y] | M (4 sem) | 6500 | ⭐⭐⭐ | [Nom] | ✅ Validé |
| [Deliverable 3] | [Impact Z.Z] | S (1 sem) | 5000 | ⭐⭐ | [Nom] | - |

---

### Q2 [Année] - BUILD CORE FEATURES

| Deliverable | Impact supporté | Effort | RICE | Priorité | Owner | Hypothèse critique |
|-------------|-----------------|--------|------|----------|-------|--------------------|
| [...] | [...] | [...] | [...] | [...] | [...] | [...] |

---

### Q3 [Année] - SCALE & OPTIMIZE

| Deliverable | Impact supporté | Effort | RICE | Priorité | Owner | Hypothèse critique |
|-------------|-----------------|--------|------|----------|-------|--------------------|
| [...] | [...] | [...] | [...] | [...] | [...] | [...] |

---

### Q4 [Année] - MEASURE & ITERATE

**Goal check :**
- [ ] Goal atteint ? [Métrique] = [Target] ?
- [ ] Impacts mesurés réalisés ?
- [ ] Learnings et pivots nécessaires ?

---

## 📈 Metrics Dashboard

### Goal Metric (Lagging Indicator)

- **Métrique :** [Ex: Retention à 30 jours]
- **Baseline :** [Ex: 45%]
- **Target :** [Ex: 65%]
- **Current (live tracking) :** [À mettre à jour régulièrement]
- **Trend :** ↗️ Improving / → Stable / ↘️ Declining

---

### Leading Indicators (Impacts)

| Impact Metric | Baseline | Target | Current | Trend | Owner |
|---------------|----------|--------|---------|-------|-------|
| [Impact 1.1 - Se connectent 3x/sem] | 12% | 35% | [X]% | [↗️/→/↘️] | [Nom] |
| [Impact 1.2 - Profil 100% complété] | 30% | 70% | [X]% | [...] | [Nom] |
| [Impact 2.1 - ...] | [...] | [...] | [...] | [...] | [Nom] |

---

### Lagging Indicators (Deliverables)

| Deliverable Metric | Target | Current | Trend | Owner |
|--------------------|--------|---------|-------|-------|
| [Deliverable 1 - Email open rate] | 40% | [X]% | [↗️/→/↘️] | [Nom] |
| [Deliverable 2 - Feature adoption] | 60% | [X]% | [...] | [Nom] |

---

## ⚠️ Hypothèses Critiques & Plan de Validation

### Instructions

Identifier les hypothèses critiques (⚠️) et définir un plan de validation **avant** de développer.

**Format :**
```
Deliverable: [Nom]
Hypothèse: [Énoncé de l'hypothèse]
Risque: High/Medium/Low
Plan de validation: [Méthode - prototype, A/B test, interviews]
Success criteria: [Seuil de validation]
```

---

### Hypothèse 1 : [Énoncé hypothèse]

**Deliverable associé :** [Nom deliverable]
**Impact supporté :** [Nom impact]
**Risque si fausse :** HIGH / MEDIUM / LOW

**Hypothèse :**
```
Nous croyons que [doing X] pour [users Y] permettra d'atteindre [outcome Z]
```

**Plan de validation :**
1. **Phase Discovery (Sem 1) :** [Ex: 5 user interviews]
2. **Phase Prototype (Sem 2-3) :** [Ex: Prototype Figma + 5 user tests]
3. **Phase MVP (Sem 4-6) :** [Ex: A/B test 50/50 traffic]
4. **Decision (Sem 7) :** [Critères GO/ITERATE/PIVOT]

**Success criteria :**
- ✅ GO: [Métrique] ≥ [Seuil] (ex: Task completion > 80%)
- ⚠️ ITERATE: [Métrique] entre [X] et [Y]
- ❌ PIVOT: [Métrique] < [Seuil]

**Budget :** [Effort + coût]
**Owner :** [Nom]

---

### Hypothèse 2-N : [Répéter pour chaque hypothèse critique]

---

## ✅ Validation Impact Map

### Checklist de qualité

- [ ] **Goal SMART** : Specific, Measurable, Achievable, Relevant, Time-bound
- [ ] **Acteurs priorisés** : Top 3-5 acteurs avec influence High
- [ ] **Impacts mesurables** : Baseline → Target définis avec métriques
- [ ] **Deliverables reliés** : Chaque deliverable trace jusqu'au goal
- [ ] **RICE scores calculés** : Priorisation data-driven (pas opinions)
- [ ] **Hypothèses identifiées** : Assumptions critiques avec plan de validation
- [ ] **Roadmap séquencée** : Timeline réaliste avec owners assignés
- [ ] **Metrics dashboard** : Goal + leading/lagging indicators définis

---

### Questions de validation

1. **La logique causale tient-elle ?**
   - Si nous construisons [Deliverable X] → [Impact Y] se réalise → [Goal Z] atteint ?

2. **Les priorités sont-elles data-driven ?**
   - RICE scores basés sur data réelles (pas opinions) ?

3. **Le scope est-il réaliste ?**
   - Effort total ≤ Capacité disponible ?

---

## 📎 Métadonnées

**Goal principal :** [Résumé 1 phrase]
**Timeline :** [Horizon temporel - ex: 6 mois, Q1-Q3 2026]
**Date de création :** [Date]
**Créé par :** [Équipe/Participants]
**Dernière mise à jour :** [Date]
**Prochaine review :** [Date - ex: Monthly review le 15 de chaque mois]

---

## 🔗 Next Steps

Après avoir créé votre impact map :

1. **Valider avec stakeholders** (alignment business-produit)
2. **Setup metrics tracking** (GA, Mixpanel, dashboards)
3. **Kick-off deliverables prioritaires** (Q1 roadmap)
4. **Valider hypothèses critiques** (prototypes, MVPs, A/B tests)
5. **Rituels de suivi** : Weekly check-in, Monthly metrics review, Quarterly goal review

---

## 📚 Ressources

- **Méthodologie** : Gojko Adzic - "Impact Mapping" (livre)
- **Site officiel** : https://www.impactmapping.org/
- **Templates gratuits** : https://www.impactmapping.org/templates.html
- **Tool** : Miro Impact Map template (gratuit)

---

**Template version** : 1.0 | **Dernière mise à jour** : Janvier 2026
