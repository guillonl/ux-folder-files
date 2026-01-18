# UX Agents Repository - Prompts Spécialisés pour Designers Experts

Repository de fichiers `.md` servant d'**agents spécialisés UX/UI** à utiliser avec Claude. Transformez Claude en expert pour analyses heuristiques, facilitation de workshops, analyse de données utilisateurs, génération de livrables et orchestration de workflows UX complexes.

---

## 🎯 Objectifs du Projet

Ce repository fournit une **bibliothèque d'agents UX conversationnels** pour :

✅ **Analyses Heuristiques Complètes**
- Évaluations Nielsen (10 heuristiques)
- Audits Bastien & Scapin (18 critères ergonomiques)
- Vérifications WCAG accessibilité
- Audits design systems
- Analyses multi-frameworks consolidées

✅ **Facilitation de Workshops**
- Design Thinking (5 phases Stanford d.school)
- Design Sprints (Google Ventures)
- Story Mapping
- Impact Mapping
- Lean UX Canvas

✅ **Analyse de Données Utilisateurs**
- Interprétation analytics (GA4, heatmaps, funnels)
- Analyse feedback qualitatif (verbatims, sentiment)
- Évaluation A/B tests
- Recherche UX compétitive

✅ **Génération de Livrables UX**
- Personas data-driven
- User journey maps
- Wireframes documentés
- Documentation design systems

✅ **Orchestration Multi-Agents**
- Workflows UX complexes automatisés
- Advisor conversationnel pour routing
- Coordination entre agents spécialisés

---

## 📁 Structure du Repository

```
ux-folder-files/
├── README.md                          # Ce fichier - vue d'ensemble
│
├── agents/                            # Agents spécialisés par catégorie
│   ├── analysis/                      # Agents d'analyse
│   │   ├── ux-auditor-nielsen.md           # ✅ Audit 10 heuristiques Nielsen
│   │   ├── ux-auditor-bastien-scapin.md    # ✅ Audit 18 critères Bastien & Scapin
│   │   ├── multi-framework-analyzer.md     # ✅ Consolidation Nielsen + B&S + WCAG
│   │   └── design-system-auditor.md        # ✅ Audit design systems (tokens, patterns)
│   │
│   ├── workshops/                     # Facilitateurs de workshops
│   │   ├── design-thinking-facilitator.md  # ✅ Facilitation Design Thinking (5 phases)
│   │   ├── design-sprint-conductor.md      # ✅ Conduite Design Sprint (Google Ventures)
│   │   ├── story-mapping-facilitator.md    # ✅ Story Mapping (Jeff Patton)
│   │   ├── impact-mapping-facilitator.md   # ✅ Impact Mapping (Gojko Adzic)
│   │   └── lean-ux-canvas-facilitator.md   # ✅ Lean UX Canvas (Jeff Gothelf)
│   │
│   ├── data-intelligence/             # Analystes de données
│   │   ├── analytics-interpreter.md         # ✅ Interprétation analytics (GA4, funnels)
│   │   ├── qualitative-feedback-analyzer.md # ✅ Analyse feedback qualitatif
│   │   ├── ab-test-analyst.md               # ✅ Design et analyse A/B tests
│   │   └── ux-research-scout.md             # ✅ Recherche compétitive et veille UX
│   │
│   ├── deliverables/                  # Générateurs de livrables
│   │   ├── persona-generator.md             # ✅ Personas data-driven
│   │   ├── user-journey-mapper.md           # ✅ User journey maps
│   │   └── accessibility-wcag-checker.md    # ✅ Audit accessibilité WCAG 2.1/2.2
│   │
│   └── orchestrators/                 # Orchestrateurs et meta-agents
│       ├── ux-workflow-coordinator.md       # ✅ Orchestration workflows multi-agents
│       └── conversational-ux-advisor.md     # ✅ Routing conversationnel intelligent
│
├── templates/                         # Templates de livrables standardisés
│   ├── workshops/                      # Templates workshops
│   │   ├── empathy-map-template.md         # ✅ Empathy Map (6 quadrants)
│   │   ├── pov-statement-template.md       # ✅ POV Statement (Define phase)
│   │   ├── hmw-questions-template.md       # ✅ How Might We (Ideate phase)
│   │   ├── story-map-template.md           # ✅ User Story Map (Jeff Patton)
│   │   ├── impact-map-template.md          # ✅ Impact Map (Gojko Adzic)
│   │   └── lean-ux-canvas-template.md      # ✅ Lean UX Canvas (8 boxes)
│   │
│   └── deliverables/                   # Templates livrables UX
│       ├── persona-template.md             # ✅ Persona card (1-pager + détail)
│       ├── user-journey-template.md        # ✅ User journey map (stages, touchpoints)
│       ├── empathy-map-template.md         # ✅ Empathy map (6 quadrants + insights)
│       └── wcag-checklist-template.md      # ✅ Checklist WCAG 2.1/2.2
│
├── frameworks/                        # Références méthodologiques détaillées
│   ├── nielsen-10-heuristics.md       # ✅ 10 heuristiques Nielsen complètes
│   ├── bastien-scapin-18-criteria.md  # ✅ 18 critères Bastien & Scapin détaillés
│   ├── design-thinking-reference.md   # ✅ Design Thinking (Stanford d.school, IDEO)
│   ├── design-sprint-reference.md     # ✅ Design Sprint (Google Ventures)
│   ├── ux-metrics-reference.md        # ✅ UX Metrics (HEART, NPS, retention, A/B testing)
│   ├── wcag-reference.md              # ✅ WCAG 2.1/2.2 (4 principes POUR, 78 critères)
│   └── design-systems-reference.md    # ✅ Design Systems (tokens, patterns, governance)
│
└── docs/                              # Documentation complète
    ├── getting-started.md             # ✅ Guide de démarrage complet
    ├── orchestration-guide.md         # ✅ Guide orchestration multi-agents
    ├── advanced-workflows.md          # ✅ Workflows end-to-end complexes
    └── api-usage-guide.md             # ✅ Utilisation programmatique (API)
```

**Légende** : ✅ Disponible | 🚧 En cours | ⏳ À venir

---

## 🚀 Quick Start

### 1. Choisir un Agent

Naviguez dans `/agents/` et choisissez l'agent correspondant à votre besoin.

**Exemples :**
- Audit heuristique rapide → `agents/analysis/ux-auditor-nielsen.md`
- Audit ergonomique détaillé → `agents/analysis/ux-auditor-bastien-scapin.md`

### 2. Utiliser avec Claude

**Méthode Simple (Copier-Coller) :**

```
1. Ouvrez le fichier .md de l'agent choisi
2. Copiez TOUT le contenu
3. Collez dans une conversation Claude (Web, Desktop, API)
4. Ajoutez votre demande spécifique après le prompt
```

**Exemple :**

```
[Contenu complet de agents/analysis/ux-auditor-nielsen.md]

---

Maintenant que tu es configuré en tant que UX Auditor Nielsen, voici ma demande :

Je voudrais un audit de mon dashboard analytics SaaS.
Voici 3 screenshots : [images]

Contexte :
- Utilisateurs : Data analysts, usage quotidien
- Tâches critiques : Créer rapports, analyser tendances, configurer alertes
- Problème : Difficulté à trouver fonctionnalités avancées

Format : Rapport détaillé pour équipe produit
```

### 3. Interagir

L'agent posera des questions de clarification si nécessaire, puis exécutera sa tâche selon son process structuré.

---

## 📚 Documentation Complète

### Guides Principaux

👉 **[Guide de Démarrage Complet](docs/getting-started.md)**

Ce guide contient :
- ✅ Explication détaillée de chaque type d'agent
- ✅ Méthodes d'utilisation (Copier-coller, CLI, Projects Claude)
- ✅ Workflows simples (audit rapide, comparaison multi-framework)
- ✅ Workflows avancés (audit → corrections → validation, multi-pages)
- ✅ Best practices et troubleshooting
- ✅ Decision tree pour choisir le bon agent

👉 **[Orchestration Guide](docs/orchestration-guide.md)**

Guide complet d'orchestration multi-agents :
- ✅ Matrice décisionnelle (Besoin × Profondeur)
- ✅ 4 workflow patterns (Sequential Pipeline, Triangulation, Branching, Feedback Loop)
- ✅ Handoff protocols standardisés
- ✅ Use cases détaillés avec séquences d'agents

👉 **[Advanced Workflows](docs/advanced-workflows.md)**

Workflows UX end-to-end complexes :
- ✅ 3 workflows complets (Discovery to Launch, Multi-Framework Audit, Analytics-Driven)
- ✅ Workflows par industrie (SaaS B2B, E-commerce, Mobile apps)
- ✅ Adaptations selon contraintes (temps, budget, compétences)

👉 **[API Usage Guide](docs/api-usage-guide.md)**

Guide d'utilisation programmatique :
- ✅ Invocation agents via Claude API (Python, TypeScript)
- ✅ Scripts d'automation
- ✅ Intégration CI/CD
- ✅ Best practices techniques

---

## 🎓 Agents Disponibles (v1.4)

### Agents d'Analyse

#### 🔍 UX Auditor Nielsen
**Fichier :** `agents/analysis/ux-auditor-nielsen.md`

**Spécialisation :**
- Évaluation heuristique selon les 10 heuristiques de Jakob Nielsen
- Scoring 1-5 par heuristique avec justification
- Priorisation P0/P1/P2/P3 (matrice impact × fréquence)
- 3 formats de rapport : Détaillé, Executive Summary, Action Items

**Utilisation typique :**
- Audit rapide d'interface (web, mobile, desktop)
- Identification violations utilisabilité
- Quick wins (impact fort, effort faible)
- Benchmark avec best practices industrie

**Output :**
- Score global /50
- Violations par heuristique avec localisation précise
- Recommandations actionnables priorisées
- Rapport adapté audience (équipe produit, stakeholders, sprint)

**👉 Référence framework :** `frameworks/nielsen-10-heuristics.md`

---

#### 📐 UX Auditor Bastien & Scapin
**Fichier :** `agents/analysis/ux-auditor-bastien-scapin.md`

**Spécialisation :**
- Évaluation ergonomique selon 18 critères (7 dimensions) Bastien & Scapin
- Approche européenne francophone (INRIA)
- Granularité supérieure à Nielsen (18 vs 10 critères)
- Focus charge cognitive, contrôle utilisateur, signifiance
- Heat map par dimension

**Utilisation typique :**
- Audit ergonomique granulaire
- Interfaces métier complexes (forte charge cognitive)
- Complémentaire à Nielsen (perspective européenne)
- Cross-reference multi-frameworks

**Output :**
- Score global /95 (18 critères)
- Heat map par dimension (7 visualisations)
- Matrice de scoring détaillée
- Cross-reference optionnelle avec Nielsen

**👉 Référence framework :** `frameworks/bastien-scapin-18-criteria.md`

---

#### 🔄 Multi-Framework Analyzer
**Fichier :** `agents/analysis/multi-framework-analyzer.md`

**Spécialisation :**
- Consolidation et cross-reference de multiples frameworks (Nielsen + Bastien & Scapin + WCAG)
- Identification des violations détectées par plusieurs frameworks (triangulation)
- Pondération et scoring composite multi-dimensions
- Création de roadmaps stratégiques unifiées

**Utilisation typique :**
- Audit complet nécessitant perspectives multiples
- Priorisation basée sur convergence multi-frameworks
- Rapport consolidé pour stakeholders C-level
- Identification des problèmes systémiques vs isolés

**Output :**
- Matrice de convergence (quels problèmes détectés par quels frameworks)
- Score composite pondéré (/100)
- Heat map multi-dimensions
- Roadmap stratégique par phases (Quick Wins → Core Fixes → Long-term)
- Executive summary avec métriques clés

**👉 Référence frameworks :** `frameworks/nielsen-10-heuristics.md`, `frameworks/bastien-scapin-18-criteria.md`, `frameworks/wcag-reference.md`

---

#### 🎨 Design System Auditor
**Fichier :** `agents/analysis/design-system-auditor.md`

**Spécialisation :**
- Audit complet de design systems (tokens, composants, patterns, documentation)
- Évaluation de la maturité et gouvernance
- Benchmark avec Material Design, Carbon (IBM), Polaris (Shopify)
- Analyse d'adoption et consistency cross-produits

**Utilisation typique :**
- Évaluation santé d'un design system existant
- Identification des gaps de documentation
- Audit de consistency entre produits/équipes
- Préparation d'une refonte ou migration design system

**Output :**
- Design System Health Score (/100)
- Audit par dimension (tokens, components, patterns, docs, adoption, governance)
- Gap analysis avec priorités
- Roadmap d'amélioration (Quick Wins → Foundational → Advanced)
- Benchmark comparatif avec industry standards

**👉 Référence framework :** `frameworks/design-systems-reference.md`

---

### Générateurs de Livrables

#### 👤 Persona Generator
**Fichier :** `agents/deliverables/persona-generator.md`

**Spécialisation :**
- Génération de personas data-driven basés sur recherche utilisateur
- Synthèse de données qualitatives et quantitatives
- Création de persona cards (1-pager) et profils détaillés
- Validation et itération collaborative

**Utilisation typique :**
- Transformation de données de recherche en personas actionnables
- Création de personas pour nouveau produit/feature
- Mise à jour de personas existants avec nouvelles données
- Alignement équipe sur représentation utilisateurs

**Output :**
- Persona card 1-pager (Quick View)
- Profil détaillé (goals, frustrations, behaviors, journey highlights)
- Scénarios d'usage typiques
- Matrice de mapping persona × features

**👉 Template associé :** `templates/deliverables/persona-template.md`

---

#### 🗺️ User Journey Mapper
**Fichier :** `agents/deliverables/user-journey-mapper.md`

**Spécialisation :**
- Création de user journey maps détaillées
- Mapping des touchpoints, émotions, pain points et opportunités
- Visualisation du parcours end-to-end
- Identification des moments of truth

**Utilisation typique :**
- Mapping parcours utilisateur existant (as-is)
- Design de parcours cible (to-be)
- Identification d'opportunités d'amélioration
- Communication avec stakeholders

**Output :**
- Journey map visuelle (stages, touchpoints, emotions)
- Pain points priorisés avec impact
- Opportunités avec effort estimé
- Service blueprint (backend actions, support systems)
- Action plan par phase

**👉 Template associé :** `templates/deliverables/user-journey-template.md`

---

#### ♿ Accessibility WCAG Checker
**Fichier :** `agents/deliverables/accessibility-wcag-checker.md`

**Spécialisation :**
- Audit accessibilité selon WCAG 2.1/2.2
- Évaluation des 4 principes POUR (Perceivable, Operable, Understandable, Robust)
- Vérification par niveau de conformité (A, AA, AAA)
- Recommandations techniques et design

**Utilisation typique :**
- Audit accessibilité avant lancement
- Vérification conformité légale (RGAA, Section 508, ADA)
- Identification des barrières pour utilisateurs handicapés
- Création de roadmap accessibilité

**Output :**
- Score de conformité par niveau (A, AA, AAA)
- Violations par principe POUR avec sévérité
- Checklist interactive avec statuts
- Recommandations techniques (code fixes)
- Rapport exécutif pour stakeholders

**👉 Référence framework :** `frameworks/wcag-reference.md`
**👉 Template associé :** `templates/deliverables/wcag-checklist-template.md`

---

### Facilitateurs de Workshops

#### 🎨 Design Thinking Facilitator
**Fichier :** `agents/workshops/design-thinking-facilitator.md`

**Spécialisation :**
- Facilitation des 5 phases Stanford d.school (Empathize, Define, Ideate, Prototype, Test)
- Méthodologie IDEO Design Thinking Toolkit
- Guidage interactif adapté au contexte (remote/présentiel, durée variable)
- Génération de livrables par phase

**Utilisation typique :**
- Ateliers Design Thinking (half-day, full-day, multi-sessions)
- Exploration de problèmes complexes centrés utilisateur
- Innovation produit/service
- Transformation d'insights en solutions testables

**Output :**
- Empathy maps (template fourni)
- POV statements (Point of View)
- HMW questions (How Might We)
- Ideation boards (Crazy 8s, SCAMPER)
- Prototypes low-fi à mid-fi
- Test findings et itérations

**👉 Référence framework :** `frameworks/design-thinking-reference.md`
**👉 Templates associés :** `templates/workshops/empathy-map-template.md`, `pov-statement-template.md`, `hmw-questions-template.md`

---

#### ⚡ Design Sprint Conductor
**Fichier :** `agents/workshops/design-sprint-conductor.md`

**Spécialisation :**
- Conduite de Design Sprints selon méthodologie Google Ventures (Jake Knapp)
- Formats : 5 jours classique, 4 jours (Sprint 2.0), 2-3 jours (condensé)
- Facilitation jour par jour avec templates et timing précis
- Adaptation remote/hybride/présentiel
- Decision-making frameworks (dot voting, supervote)

**Utilisation typique :**
- Validation rapide d'une idée produit/feature (5 jours)
- Résoudre un problème critique business
- Aligner équipe cross-fonctionnelle (product, design, dev, business)
- Tester une hypothèse avec vrais utilisateurs avant dev

**Output :**
- Sprint questions et long-term goal
- Problem map et user flow
- Solution sketches et storyboard
- Prototype haute-fidélité testable (Figma, Keynote)
- Test findings (5 interviews utilisateurs)
- Next steps et décision GO/NO-GO

**👉 Référence framework :** `frameworks/design-sprint-reference.md`

---

#### 📊 Story Mapping Facilitator
**Fichier :** `agents/workshops/story-mapping-facilitator.md`

**Spécialisation :**
- Facilitation sessions Story Mapping (méthodologie Jeff Patton)
- Construction collaborative de user story maps
- Priorisation et découpage en releases (MVP, Release 1, 2, 3)
- Identification de Walking Skeleton (parcours minimum viable)
- Adaptation Agile/Scrum/Kanban/Shape Up

**Utilisation typique :**
- Planification roadmap produit
- Priorisation backlog collaboratif
- Alignement équipe sur parcours utilisateur
- Découpage features complexes en releases

**Output :**
- User story map structurée (backbone + vertical slicing)
- Walking skeleton (parcours end-to-end minimum)
- MVP scope clairement défini
- Release roadmap priorisée (MoSCoW, RICE, Value vs Effort)
- Backlog Agile organisé

**👉 Template associé :** `templates/workshops/story-map-template.md`

---

#### 🎯 Impact Mapping Facilitator
**Fichier :** `agents/workshops/impact-mapping-facilitator.md`

**Spécialisation :**
- Création d'Impact Maps (méthodologie Gojko Adzic)
- Alignement objectifs business → acteurs → impacts → deliverables (WHY-WHO-HOW-WHAT)
- Priorisation stratégique data-driven (RICE scoring)
- Lien avec OKRs et stratégie produit
- Identification d'hypothèses critiques à valider

**Utilisation typique :**
- Planification stratégique produit
- Alignement business-produit-design-dev
- Priorisation features par impact business
- Éviter le feature bloat (features sans impact mesurable)

**Output :**
- Impact map visuelle 4 niveaux
- Objectifs business SMART clarifiés avec métriques
- Acteurs identifiés et priorisés
- Impacts mesurables par acteur (baseline → target)
- Deliverables priorisés avec RICE scores
- Hypothèses critiques et plan de validation
- Roadmap timeline (Q1-Q4)

**👉 Template associé :** `templates/workshops/impact-map-template.md`

---

#### 🚀 Lean UX Canvas Facilitator
**Fichier :** `agents/workshops/lean-ux-canvas-facilitator.md`

**Spécialisation :**
- Remplissage collaboratif Lean UX Canvas (méthodologie Jeff Gothelf)
- Transformation d'assumptions en hypothèses testables
- Définition de MVPs pour validation rapide
- Build-Measure-Learn cycles (Lean Startup)
- Hypothesis-driven design

**Utilisation typique :**
- Lancement nouveau produit/feature majeure
- Alignement cross-fonctionnel sur hypothèses
- Définition d'expérimentations mesurables
- Culture d'apprentissage rapide (fail fast)

**Output :**
- Lean UX Canvas 8 boxes complété :
  1. Business Problem
  2. Business Outcomes (lagging + leading indicators)
  3. Users & Customers
  4. User Benefits
  5. Solution Ideas
  6. Hypotheses (testables avec success criteria)
  7. Critical Learning (hypothèse la plus risquée)
  8. MVP (Minimum Viable Product pour validation)
- Plan d'expérimentation actionnable
- Decision framework (GO/ITERATE/PIVOT)

**👉 Template associé :** `templates/workshops/lean-ux-canvas-template.md`

---

### Analystes de Données Utilisateurs

#### 📊 Analytics Interpreter
**Fichier :** `agents/data-intelligence/analytics-interpreter.md`

**Spécialisation :**
- Interprétation de données analytics (GA4, Mixpanel, Amplitude)
- Analyse de funnels, cohorts, retention
- Création de dashboards et visualisations
- Identification de patterns et anomalies

**Utilisation typique :**
- Comprendre baisse soudaine de métriques
- Analyser performance de features
- Optimiser funnels de conversion
- Mesurer impact de changements design

**Output :**
- Rapport d'analyse avec visualisations
- Insights actionnables priorisés
- Recommandations d'optimisation
- Hypothèses à tester

**👉 Référence framework :** `frameworks/ux-metrics-reference.md`

---

#### 💬 Qualitative Feedback Analyzer
**Fichier :** `agents/data-intelligence/qualitative-feedback-analyzer.md`

**Spécialisation :**
- Analyse de verbatims utilisateurs (reviews, support tickets, NPS)
- Analyse de sentiment et thématique
- Extraction de pain points et feature requests
- Synthèse qualitative structurée

**Utilisation typique :**
- Comprendre le "pourquoi" derrière les métriques
- Analyser feedback post-lancement
- Identifier problèmes récurrents
- Prioriser roadmap produit basée sur voice of customer

**Output :**
- Analyse thématique (clusters de feedback)
- Sentiment analysis (positif/négatif/neutre par thème)
- Top pain points avec fréquence et impact
- Feature requests priorisés
- Verbatims représentatifs par thème

**👉 Référence framework :** `frameworks/ux-metrics-reference.md`

---

#### 🧪 A/B Test Analyst
**Fichier :** `agents/data-intelligence/ab-test-analyst.md`

**Spécialisation :**
- Design d'expérimentations A/B/n
- Calcul de sample size et durée optimale
- Analyse statistique de résultats (significance, confidence intervals)
- Recommandations de déploiement (rollout, rollback, iterate)

**Utilisation typique :**
- Valider hypothèses design
- Optimiser conversions et engagement
- Mesurer impact de features
- Décisions data-driven (ship vs iterate)

**Output :**
- Test plan (hypothèse, variants, métriques, sample size)
- Résultats d'analyse statistique
- Visualisations de performance comparative
- Recommandation GO/NO-GO avec justification
- Plan de rollout progressif

**👉 Référence framework :** `frameworks/ux-metrics-reference.md`

---

#### 🔍 UX Research Scout
**Fichier :** `agents/data-intelligence/ux-research-scout.md`

**Spécialisation :**
- Recherche compétitive et best practices
- Veille UX et tendances industrie
- Analyse de conformité (GDPR, WCAG, RGAA)
- Curation de ressources et références

**Utilisation typique :**
- Benchmarking concurrentiel
- Inspiration design (design patterns)
- Vérification compliance
- Formation équipe sur nouvelles méthodologies

**Output :**
- Rapport de competitive analysis
- Best practices par use case
- Checklist de conformité
- Ressources curatées (articles, études de cas)

**👉 Référence framework :** `frameworks/ux-metrics-reference.md`

---

### Orchestrateurs & Meta-Agents

#### 🎯 UX Workflow Coordinator
**Fichier :** `agents/orchestrators/ux-workflow-coordinator.md`

**Spécialisation :**
- Orchestration de workflows multi-agents complexes
- Sélection de séquences d'agents optimales selon contexte
- Gestion de handoffs et agrégation de résultats
- Coordination de pipelines séquentiels et parallèles

**Utilisation typique :**
- Projets UX complexes nécessitant plusieurs agents
- Workflows end-to-end (discovery → validation → launch)
- Audits multi-perspectives (Nielsen + B&S + WCAG → consolidation)
- Projets nécessitant coordination entre analyse, workshops et deliverables

**Output :**
- Workflow plan (séquence d'agents avec dépendances)
- Rapport consolidé unifié (agrégation de tous les agents)
- Roadmap d'actions priorisées
- Next steps recommandés

**Process :**
- Discovery : Clarifier besoin, contraintes, profondeur souhaitée
- Workflow Selection : Choix via matrice décisionnelle (Besoin × Profondeur)
- Agent Sequencing : Ordonnancement optimal (séquentiel/parallèle)
- Execution : Lancement des agents avec handoffs
- Aggregation : Consolidation des outputs
- Synthesis : Rapport final avec recommandations

**👉 Documentation associée :** `docs/orchestration-guide.md`, `docs/advanced-workflows.md`

---

#### 💡 Conversational UX Advisor
**Fichier :** `agents/orchestrators/conversational-ux-advisor.md`

**Spécialisation :**
- Conseiller conversationnel pour routing intelligent vers agents
- Diagnostic de besoins UX via questions stratégiques
- Recommandations personnalisées d'agents et workflows
- Guidance méthodologique et pédagogie UX

**Utilisation typique :**
- Point d'entrée pour utilisateurs ne sachant pas quel agent utiliser
- Clarification de besoins UX complexes ou ambigus
- Apprentissage des méthodologies UX disponibles
- Guidance pour utilisateurs débutants ou intermédiaires

**Output :**
- Recommendation report (agent(s) recommandé(s) avec justification)
- Quick start guide (étapes immédiates pour commencer)
- Learning path (ressources pour approfondir)
- Alternatives selon contraintes (temps, budget, expertise)

**Process :**
- Listening : Questions ouvertes pour comprendre besoin
- Diagnosis : Catégorisation via decision tree (AUDIT/EXPLORE/VALIDATE/EXECUTE/MEASURE/LEARN)
- Recommendation : Proposition avec justification
- Alternatives : Options selon contraintes
- Guidance : Accompagnement pendant exécution

**👉 Documentation associée :** `docs/orchestration-guide.md`

---

## 🔧 Frameworks de Référence

### 📖 Nielsen 10 Heuristiques
**Fichier :** `frameworks/nielsen-10-heuristics.md`

Référence complète des 10 heuristiques d'utilisabilité :
1. Visibility of System Status
2. Match Between System and the Real World
3. User Control and Freedom
4. Consistency and Standards
5. Error Prevention
6. Recognition Rather Than Recall
7. Flexibility and Efficiency of Use
8. Aesthetic and Minimalist Design
9. Help Users Recognize, Diagnose, and Recover from Errors
10. Help and Documentation

Pour chaque heuristique :
- ✅ Principe détaillé
- ✅ Critères de vérification
- ✅ Exemples de violations
- ✅ Bonnes pratiques
- ✅ Grille de scoring 1-5

---

### 📖 Bastien & Scapin 18 Critères
**Fichier :** `frameworks/bastien-scapin-18-criteria.md`

Référence complète des 18 critères ergonomiques (7 dimensions) :

**Dimension 1 : GUIDAGE** (5 critères)
- 1.1 Incitation
- 1.2 Groupement/Distinction par Localisation
- 1.3 Groupement/Distinction par Format
- 1.4 Feedback Immédiat
- 1.5 Lisibilité

**Dimension 2 : CHARGE DE TRAVAIL** (3 critères)
- 2.1 Brièveté - Concision
- 2.2 Brièveté - Actions Minimales
- 2.3 Densité Informationnelle

**Dimension 3 : CONTRÔLE EXPLICITE** (2 critères)
- 3.1 Actions Explicites
- 3.2 Contrôle Utilisateur

**Dimension 4 : ADAPTABILITÉ** (2 critères)
- 4.1 Flexibilité
- 4.2 Prise en Compte de l'Expérience Utilisateur

**Dimension 5 : GESTION DES ERREURS** (3 critères)
- 5.1 Protection contre les Erreurs
- 5.2 Qualité des Messages d'Erreur
- 5.3 Correction des Erreurs

**Dimension 6 : HOMOGÉNÉITÉ/COHÉRENCE** (2 critères)
- 6.1 Cohérence Interne
- 6.2 Cohérence Externe

**Dimension 7 : SIGNIFIANCE DES CODES** (2 critères)
- 7.1 Signifiance des Labels et Intitulés
- 7.2 Signifiance des Informations Affichées

Pour chaque critère :
- ✅ Principe et critères d'évaluation
- ✅ Violations courantes
- ✅ Scoring 1-5
- ✅ Exemples concrets

---

### 📖 Design Thinking Reference
**Fichier :** `frameworks/design-thinking-reference.md`

Référence complète de la méthodologie Design Thinking (Stanford d.school + IDEO) :

**5 Phases Détaillées :**
1. **Empathize** : Empathy interviews, observation terrain, immersion utilisateur
2. **Define** : POV statements, problem synthesis, HMW questions
3. **Ideate** : Brainstorming, Crazy 8s, SCAMPER, divergent thinking
4. **Prototype** : Rapid prototyping, low-fi to mid-fi, fail fast
5. **Test** : User testing, feedback loops, iteration

Pour chaque phase :
- ✅ Objectifs et livrables
- ✅ Techniques et outils recommandés
- ✅ Timing et facilitation best practices
- ✅ Templates et exemples concrets
- ✅ Remote vs présentiel adaptations

**Quand utiliser** : Innovation produit/service, exploration problèmes complexes, transformation insights en solutions testables

**Liens** : Utilisé par agent `design-thinking-facilitator.md`

---

### 📖 Design Sprint Reference
**Fichier :** `frameworks/design-sprint-reference.md`

Référence complète de la méthodologie Design Sprint (Google Ventures - Jake Knapp) :

**Structure 5 Jours (Classic Sprint) :**
- **Monday - Map** : Long-term goal, sprint questions, problem map, expert interviews
- **Tuesday - Sketch** : Lightning demos, 4-step sketching (notes → ideas → Crazy 8s → solution sketch)
- **Wednesday - Decide** : Art museum, heat map, speed critique, straw poll, supervote
- **Thursday - Prototype** : Asset collection, building (Figma/Keynote), trial run
- **Friday - Test** : 5 user interviews, pattern observation, synthesis, next steps

**Variations :**
- Design Sprint 2.0 (4 jours) : Merge Monday-Tuesday
- Sprint condensé (2-3 jours) : Cas urgents
- Remote facilitation : Miro, FigJam, Zoom best practices

Pour chaque jour :
- ✅ Agenda détaillé avec timing
- ✅ Rôles et responsabilités (Decider, Facilitator, Participants)
- ✅ Materials checklist (outils, supplies)
- ✅ Templates jour par jour
- ✅ Common pitfalls et solutions

**Quand utiliser** : Validation rapide idée produit/feature (5 jours), résoudre problème critique business, aligner équipe cross-fonctionnelle

**Liens** : Utilisé par agent `design-sprint-conductor.md`

---

### 📖 WCAG 2.1/2.2 Reference
**Fichier :** `frameworks/wcag-reference.md`

Référence complète des Web Content Accessibility Guidelines :

**4 Principes POUR :**
1. **Perceivable** : Contenu présentable de manière perceptible (alternatives textuelles, adaptable, distinguable)
2. **Operable** : Interface utilisable (clavier, timing, navigation, saisie)
3. **Understandable** : Contenu compréhensible (lisible, prévisible, assistance)
4. **Robust** : Contenu robuste et compatible (parsing, nom/rôle/valeur)

**Structure :**
- 13 guidelines (directives)
- 78 success criteria
- 3 niveaux de conformité : A (minimum), AA (standard), AAA (optimal)

Pour chaque critère :
- ✅ Description et objectif
- ✅ Niveau de conformité (A, AA, AAA)
- ✅ Exemples de violations
- ✅ Techniques de remédiation
- ✅ Testing methods

**Liens** : Utilisé par agents `accessibility-wcag-checker.md`, `multi-framework-analyzer.md`

---

### 📖 Design Systems Reference
**Fichier :** `frameworks/design-systems-reference.md`

Référence complète pour l'audit et la construction de design systems :

**Taxonomie Design Tokens :**
- Colors (primitives, semantic, component-level)
- Typography (type scale, font stacks, line heights)
- Spacing (grid, margins, padding scales)
- Elevation (shadows, z-index layers)
- Motion (durations, easings, keyframes)

**Component Patterns :**
- Buttons, Forms, Navigation, Data Display
- API standards et props conventions
- States (default, hover, focus, disabled, error)
- Accessibility requirements par composant

**Governance & Documentation :**
- Versioning strategies (SemVer)
- Contribution workflows
- Documentation standards
- Adoption metrics

**Benchmarks** : Material Design (Google), Carbon (IBM), Polaris (Shopify), Lightning (Salesforce)

**Liens** : Utilisé par agent `design-system-auditor.md`

---

## 🎯 Use Cases

### Use Case 1 : Audit Rapide pour Sprint Planning

**Contexte :** Équipe produit veut prioriser corrections UX pour prochain sprint

**Solution :**
1. Utiliser `ux-auditor-nielsen.md`
2. Fournir screenshots de l'interface actuelle
3. Demander format **Action Items**
4. Obtenir liste priorisée P0/P1 avec effort estimé
5. Intégrer directement dans sprint backlog

**Temps :** 15 minutes

---

### Use Case 2 : Audit Complet Multi-Framework

**Contexte :** Refonte majeure, besoin d'analyse approfondie avec perspectives complémentaires

**Solution :**
1. Audit Nielsen → Vision globale utilisabilité
2. Audit Bastien & Scapin → Granularité charge cognitive
3. Cross-reference → Violations détectées par les 2 = **critiques**
4. Rapport consolidé avec recommandations stratégiques

**Temps :** 40 minutes

---

### Use Case 3 : Validation Post-Corrections

**Contexte :** Corrections UX implémentées, vérifier résolution des problèmes

**Solution :**
1. Audit initial (avant corrections) → Score X/50
2. Implémentation corrections P0/P1
3. Audit validation (après corrections) → Score Y/50
4. Rapport comparatif avant/après
5. Mesure ROI : amélioration mesurable du score

**Temps :** 2-3 jours (incluant design)

---

## 📊 Roadmap

### ✅ Version 1.0 (Sprint 1 - Complété)
- [x] Structure de dossiers complète
- [x] Agent UX Auditor Nielsen
- [x] Agent UX Auditor Bastien & Scapin
- [x] Framework Nielsen 10 heuristiques
- [x] Framework Bastien & Scapin 18 critères
- [x] Documentation Getting Started

### ✅ Version 1.1 (Sprint 2 - Complété - Workshop Facilitators)
- [x] Agent Design Thinking Facilitator (5 phases Stanford d.school)
- [x] Agent Design Sprint Conductor (Google Ventures)
- [x] Agent Story Mapping Facilitator (Jeff Patton)
- [x] Agent Impact Mapping Facilitator (Gojko Adzic)
- [x] Agent Lean UX Canvas Facilitator (Jeff Gothelf)
- [x] Framework Design Thinking Reference
- [x] Framework Design Sprint Reference
- [x] Templates workshops (6 templates) : Empathy Map, POV Statement, HMW Questions, Story Map, Impact Map, Lean UX Canvas

### ✅ Version 1.2 (Sprint 3 - Complété - Data Intelligence)
- [x] Agent Analytics Interpreter (Interprétation GA4, funnels, retention)
- [x] Agent Qualitative Feedback Analyzer (Analyse verbatims, sentiment)
- [x] Agent A/B Test Analyst (Design expérimentations, analyse statistique)
- [x] Agent UX Research Scout (Competitive analysis, best practices, compliance)
- [x] Framework UX Metrics Reference (HEART, NPS, retention, A/B testing benchmarks)

### ✅ Version 1.3 (Sprint 4 - Complété - Deliverables & Advanced)
- [x] Agent Persona Generator (Personas data-driven)
- [x] Agent User Journey Mapper (Journey maps détaillées)
- [x] Agent Accessibility WCAG Checker (Audit WCAG 2.1/2.2)
- [x] Agent Multi-Framework Analyzer (Consolidation Nielsen + B&S + WCAG)
- [x] Agent Design System Auditor (Audit design systems)
- [x] Framework WCAG Reference (4 principes POUR, 78 critères)
- [x] Framework Design Systems Reference (tokens, patterns, governance)
- [x] Templates deliverables (4 templates) : Persona, User Journey, Empathy Map, WCAG Checklist

### ✅ Version 1.4 (Sprint 5 - Complété - Orchestration)
- [x] Agent UX Workflow Coordinator (Orchestration workflows multi-agents)
- [x] Agent Conversational UX Advisor (Routing conversationnel intelligent)
- [x] Documentation Orchestration Guide (Decision matrix, workflow patterns, handoffs)
- [x] Documentation Advanced Workflows (3 workflows end-to-end, adaptations industrie)
- [x] Documentation API Usage Guide (Python/TypeScript, automation, CI/CD)

---

## 🤝 Contribution

Ce projet est conçu pour évoluer avec les besoins de la communauté UX.

### Comment Contribuer

**1. Améliorer un Agent Existant**
- Tester l'agent sur vrais projets
- Identifier limites ou bugs
- Proposer améliorations via Pull Request

**2. Créer un Nouveau Agent**
- Utiliser la structure standard d'agent (voir `agents/analysis/ux-auditor-nielsen.md` comme template)
- Respecter principes de design :
  - ✅ Pour designers experts (pas de sur-explication)
  - ✅ Conversationnel (demande clarifications)
  - ✅ Multi-format outputs (adaptatif)
  - ✅ Orchestrable (peut se chaîner)
  - ✅ Recherche web sur demande uniquement
- Documenter clairement : role, process, inputs, outputs

**3. Enrichir les Frameworks**
- Ajouter exemples concrets
- Compléter avec références récentes
- Traduire/adapter frameworks internationaux

**4. Partager Workflows**
- Documenter workflows personnalisés
- Cas d'usage spécifiques industries/domaines
- Patterns d'orchestration multi-agents

### Guidelines de Contribution

**Structure Standard d'un Agent :**
```markdown
# [Agent Name]

## Role & Expertise
[Role clair, spécialisation]

## Core Responsibilities
[3-5 responsabilités principales]

## Process
[Méthodologie étape par étape]

## Inputs Required
[Informations nécessaires]

## Output Format
[Template de sortie structuré]

## Conversation Flow
[Comment l'agent interagit]

## Edge Cases
[Gestion scénarios spéciaux]

## Related Agents
[Liens vers agents complémentaires pour orchestration]
```

**Qualité attendue :**
- Expertise : Contenu reflétant best practices industrie
- Clarté : Structure logique, sections bien définies
- Actionnabilité : Outputs directement utilisables
- Testabilité : Exemples de prompts utilisateur fournis

---

## 📞 Support & Contact

### Documentation
- **Getting Started** : `docs/getting-started.md`
- **Frameworks** : `frameworks/`
- **Agents** : `agents/` (chaque agent documente son usage)

### Ressources Externes
- **Nielsen Norman Group** : https://www.nngroup.com
- **INRIA (Bastien & Scapin)** : https://www.lamsade.dauphine.fr/~manouvri/IHM/Bastien-Scapin.pdf
- **WCAG** : https://www.w3.org/WAI/WCAG21/quickref/

### Questions & Issues
- **GitHub Issues** : [Lien à ajouter]
- **Discussions** : [Lien à ajouter]

---

## 📜 Licence

[À définir - MIT, Apache 2.0, ou autre]

---

## 🙏 Remerciements

Ce repository s'appuie sur les travaux de recherche et méthodologies de :
- **Jakob Nielsen** et le Nielsen Norman Group (10 heuristiques)
- **Bastien & Scapin (INRIA)** (18 critères ergonomiques)
- **W3C** (WCAG guidelines)
- **Stanford d.school** (Design Thinking)
- **Google Ventures** (Design Sprint)

Merci à la communauté UX/UI pour les retours et contributions continues.

---

## 📈 Statistiques

- **Agents disponibles** : 18
  - Analyse : 4 (Nielsen, Bastien & Scapin, Multi-Framework Analyzer, Design System Auditor)
  - Workshops : 5 (Design Thinking, Design Sprint, Story Mapping, Impact Mapping, Lean UX Canvas)
  - Data Intelligence : 4 (Analytics Interpreter, Qualitative Feedback, A/B Test Analyst, UX Research Scout)
  - Deliverables : 3 (Persona Generator, User Journey Mapper, Accessibility WCAG Checker)
  - Orchestrateurs : 2 (UX Workflow Coordinator, Conversational UX Advisor)
- **Frameworks** : 7
  - Analyse : 2 (Nielsen 10 heuristiques, Bastien & Scapin 18 critères)
  - Workshops : 2 (Design Thinking, Design Sprint)
  - Data Intelligence : 1 (UX Metrics Reference - HEART, NPS, retention)
  - Advanced : 2 (WCAG 2.1/2.2 Reference, Design Systems Reference)
- **Templates** : 10
  - Workshops : 6 (Empathy Map, POV Statement, HMW Questions, Story Map, Impact Map, Lean UX Canvas)
  - Deliverables : 4 (Persona, User Journey, Empathy Map, WCAG Checklist)
- **Documentation** : 5
  - Getting Started Guide
  - Orchestration Guide
  - Advanced Workflows
  - API Usage Guide
  - Plan de Travail
- **Critères d'évaluation** : 106 (10 Nielsen + 18 Bastien & Scapin + 78 WCAG)
- **Workflows documentés** : 30+
- **Version** : 1.4 (Sprint 5 complété - Orchestration & Meta-Agents)

---

**Transformez Claude en expert UX et accélérez votre pratique du design ! 🚀**

*Repository maintenu et mis à jour régulièrement. Dernière mise à jour : 2026-01-18 (Sprint 5 - Orchestration & Meta-Agents)*
