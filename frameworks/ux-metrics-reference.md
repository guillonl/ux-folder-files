# UX Metrics Reference Framework

## Introduction

Ce framework détaille les métriques UX essentielles pour mesurer et optimiser l'expérience utilisateur de manière data-driven. Il couvre le framework HEART de Google, les métriques comportementales, attitudinales, de succès des tâches, et les KPIs par objectif business.

**Utilisation :** Référence pour sélectionner les bonnes métriques selon vos objectifs, interpréter les résultats et benchmarker vs industrie.

---

## 1. HEART Framework (Google)

Développé par Google HEART, ce framework couvre 5 dimensions de l'expérience utilisateur de manière holistique.

### H - Happiness (Satisfaction)

**Définition :** Attitudes subjectives des utilisateurs envers le produit.

**Métriques :**

**NPS (Net Promoter Score)**
- **Question :** "Sur une échelle de 0-10, recommanderiez-vous [produit] à un ami ou collègue ?"
- **Calcul :** % Promoters (9-10) - % Detractors (0-6)
- **Échelle :** -100 à +100
- **Benchmarks :**
  - NPS > 50 : Excellent (world-class)
  - NPS 30-50 : Good (above average)
  - NPS 0-30 : Needs improvement
  - NPS < 0 : Critical (plus de detractors que promoters)
- **Quand mesurer :** Post-milestone (onboarding complété, premier achat, après 30j utilisation)
- **Best practice :** Poser question follow-up ouverte "Pourquoi cette note ?" pour insights qualitatifs

**CSAT (Customer Satisfaction Score)**
- **Question :** "Comment évaluez-vous votre expérience avec [produit/feature] ?"
- **Échelle :** 1-5 étoiles ou Very Dissatisfied → Very Satisfied
- **Calcul :** (Satisfied 4-5 / Total responses) × 100
- **Benchmarks :**
  - CSAT > 80% : Excellent
  - CSAT 70-80% : Good
  - CSAT < 70% : Needs improvement
- **Quand mesurer :** Post-interaction spécifique (support ticket résolu, feature utilisée, checkout complété)
- **Avantage vs NPS :** Plus granulaire (mesure satisfaction feature spécifique, pas produit global)

**SUS (System Usability Scale)**
- **Format :** Questionnaire standardisé 10 items (Likert scale 1-5)
- **Items exemples :**
  1. "I think I would like to use this system frequently"
  2. "I found the system unnecessarily complex"
  3. "I thought the system was easy to use"
  4. [... 7 autres items]
- **Calcul :** Score 0-100 (formule spécifique, alternance items positifs/négatifs)
- **Benchmarks :**
  - SUS > 80 : Grade A (Excellent)
  - SUS 68-80 : Grade B (Good) — 68 = moyenne industrie
  - SUS 51-68 : Grade C (OK, needs improvement)
  - SUS < 51 : Grade F (Poor, critical usability issues)
- **Quand utiliser :**
  - Baseline UX score (avant redesign)
  - Post-redesign (mesurer amélioration)
  - Competitive benchmarking (votre produit vs concurrents)
- **Avantage :** Standardisé (comparable cross-products, cross-industries)

**Sentiment Analysis (Verbatims)**
- **Sources :** NPS comments, support tickets, reviews (App Store, Google Play, G2, Trustpilot), surveys verbatims, social media
- **Méthode :** NLP sentiment analysis (positive/neutral/negative)
- **Tools :** MonkeyLearn, Lexalytics, Google Cloud Natural Language API
- **Output :**
  - Sentiment score : -1 (très négatif) à +1 (très positif)
  - Thèmes principaux par sentiment (ex: "slow performance" = -0.8, "great support" = +0.9)
  - Évolution sentiment over time (trending up/down)
- **Best practice :** Combiner avec métriques quantitatives (ex: NPS -10, sentiment analysis révèle "pricing too high" = insight actionnable)

---

### E - Engagement (Niveau d'utilisation)

**Définition :** Intensité et fréquence d'utilisation du produit.

**Métriques :**

**DAU / MAU / WAU (Daily/Monthly/Weekly Active Users)**
- **Définition :**
  - DAU : Users actifs au moins 1x par jour
  - WAU : Users actifs au moins 1x par semaine
  - MAU : Users actifs au moins 1x par mois
- **"Actif" = ?** Dépend du produit (ex: login, core action performed, session > 10s)
- **Benchmarks (SaaS) :**
  - DAU/MAU ratio (Stickiness) :
    - 20%+ : Excellent (Facebook ~60%, WhatsApp ~70%)
    - 10-20% : Good
    - <10% : Poor (users don't return daily)

**DAU/MAU Ratio (Stickiness)**
- **Calcul :** (DAU / MAU) × 100
- **Interprétation :** % de users monthly qui reviennent daily
- **Exemple :**
  - MAU = 100,000 users
  - DAU = 25,000 users
  - Stickiness = 25% (bon)
- **Benchmarks par type produit :**
  - Social media : 50-70% (très sticky)
  - Productivity tools : 20-40%
  - E-commerce : 5-15% (moins fréquent, mais normal)

**Session Duration (Durée moyenne par session)**
- **Définition :** Temps moyen passé par session
- **Interprétation :** Dépend du produit
  - Long = bon : Content platforms, social media (engagement deep)
  - Short = bon : Productivity tools (task completed quickly = efficient)
- **Benchmarks :**
  - Mobile apps : 3-7 min moyenne
  - Web apps : 5-15 min
  - Content platforms : 15-30 min (Netflix, YouTube)

**Session Frequency (Nombre de sessions par user)**
- **Calcul :** Total sessions / Total users (sur période)
- **Exemple :** 10,000 users, 50,000 sessions/mois = 5 sessions/user/mois
- **Benchmarks :**
  - Daily use apps : 20-30 sessions/month
  - Weekly use apps : 4-8 sessions/month

**Feature Adoption Rate**
- **Calcul :** (Users who used feature X / Total users) × 100
- **Exemple :** 1,000 users tried new "AI assistant" feature / 10,000 total users = 10% adoption
- **Benchmarks :**
  - 30%+ adoption (30j post-launch) : Success
  - 10-30% : Moderate
  - <10% : Low (feature not discoverable or not valuable)
- **Track over time :** Adoption curve (should grow, plateau or decline ?)

**Pages per Session (Profondeur d'engagement)**
- **Définition :** Nombre moyen de pages/screens vues par session
- **Benchmarks :**
  - E-commerce : 5-10 pages (browse products)
  - Content sites : 2-4 pages (read articles)
  - SaaS dashboards : 3-8 pages (navigate features)

**Quand mesurer :** Analytics continu (GA4, Mixpanel, Amplitude)

---

### A - Adoption (Nouveaux utilisateurs)

**Définition :** Acquisition et onboarding de nouveaux utilisateurs.

**Métriques :**

**Signup Conversion Rate**
- **Calcul :** (Signups / Landing page visitors) × 100
- **Funnel :** Visitor → Landing page → Signup
- **Benchmarks :**
  - B2C : 2-5%
  - B2B SaaS : 5-10%
  - Freemium : 10-25%
- **Facteurs d'influence :** Value prop clarity, form friction, trust signals

**Activation Rate**
- **Définition :** % users qui atteignent le "aha moment" (première valeur)
- **Exemple aha moment :**
  - Slack : Envoyer 2,000 messages en équipe
  - Dropbox : Sauvegarder 1 fichier
  - Facebook : Ajouter 7 amis en 10 jours
  - Airbnb : Compléter 1 booking (guest) ou recevoir 1 booking (host)
- **Calcul :** (Users qui atteignent aha moment / Total signups) × 100
- **Benchmarks :**
  - 40-60% : Good
  - 60%+ : Excellent
  - <40% : Onboarding needs improvement
- **Best practice :** Identifier votre aha moment (correlate early actions with retention D30)

**Time to First Value (TTFV)**
- **Définition :** Temps écoulé entre signup et premier moment de valeur
- **Exemple :**
  - Dropbox : <5 min (install app, save first file)
  - Slack : <10 min (invite teammates, send messages)
  - Stripe : <30 min (setup payment, receive first test transaction)
- **Benchmarks :**
  - <10 min : Excellent (instant gratification)
  - 10-30 min : Good
  - >1h : Too long (users churn before experiencing value)
- **Best practice :** Réduire TTFV = priorité #1 onboarding (remove friction, guide to aha moment)

**Onboarding Completion Rate**
- **Calcul :** (Users qui complètent onboarding / Total signups) × 100
- **Benchmarks :**
  - 50-70% : Good
  - 70%+ : Excellent
  - <50% : Friction majeure dans onboarding
- **Optimization :**
  - Réduire steps (5+ steps = high drop-off)
  - Progress indicator (users savent combien reste)
  - Optional vs required steps (minimize required)

---

### R - Retention (Fidélisation)

**Définition :** Retour des utilisateurs sur le temps.

**Métriques :**

**Retention Rate (Day 1, 7, 30, 90)**
- **Calcul :** (Users actifs Day X / Users signups Day 0) × 100
- **Exemple :**
  - Cohort Jan 1 : 1,000 signups
  - Day 1 : 550 actifs = 55% retention D1
  - Day 7 : 350 actifs = 35% retention D7
  - Day 30 : 180 actifs = 18% retention D30
- **Benchmarks (Mobile apps) :**
  - D1 : 40-50% (good), 25-40% (average), <25% (poor)
  - D7 : 30-40% (good), 15-30% (average), <15% (poor)
  - D30 : 20-30% (good), 10-20% (average), <10% (poor)
- **Benchmarks (SaaS B2B) :**
  - D30 : 40-60% (good), 60%+ (excellent)
  - M3 (Month 3) : 60-80%
  - M12 : 70-90% (mature SaaS)
- **Forme de la curve :**
  - Ideal : Steep drop initial puis plateau (flattening)
  - Bad : Decline continue sans plateau (leaky bucket)

**Churn Rate**
- **Définition :** % users qui cessent d'utiliser le produit
- **Calcul :** (Users churned this month / Total users start of month) × 100
- **Exemple :**
  - Start month : 10,000 users
  - End month : 9,200 users (800 churned)
  - Churn rate : 8% monthly
- **Benchmarks (SaaS) :**
  - <5% monthly : Excellent
  - 5-7% : Good
  - 7-10% : Average
  - >10% : High churn (problème retention)
- **Annual churn :**
  - <20% : Excellent
  - 20-40% : Good
  - >40% : Critical
- **Relation :** Retention = 100% - Churn

**Cohort Analysis**
- **Définition :** Retention par cohorte d'inscription (grouper users par signup week/month)
- **Exemple :**
  ```
  Cohort    | D1   | D7   | D30  | D90
  ----------|------|------|------|-----
  Jan 2026  | 55%  | 35%  | 18%  | 12%
  Feb 2026  | 60%  | 40%  | 22%  | 15% ← Amélioration
  Mar 2026  | 58%  | 38%  | 25%  | 18% ← Amélioration continue
  ```
- **Insights :** Si cohorts récentes ont meilleure retention → Product improvements fonctionnent

**Product-Market Fit Score (Retention-Based)**
- **Métrique :** Retention D30 ou D90
- **Benchmark (Sean Ellis - PMF Survey) :**
  - D30 retention >40% = Strong PMF signal
  - D30 <20% = Weak PMF (users ne voient pas valeur long-term)
- **Alternative PMF metric :** "How would you feel if you could no longer use [product] ?"
  - >40% answer "Very disappointed" = PMF achieved

**Resurrection Rate**
- **Définition :** % churned users qui reviennent
- **Calcul :** (Churned users who returned / Total churned users) × 100
- **Exemple :**
  - 1,000 users churned last month
  - 150 returned this month
  - Resurrection rate : 15%
- **Drivers :** Win-back campaigns, new features announcements, re-engagement emails

---

### T - Task Success (Efficacité des tâches)

**Définition :** Capacité des utilisateurs à accomplir leurs objectifs.

**Métriques :**

**Task Completion Rate**
- **Calcul :** (Tasks completed successfully / Total tasks attempted) × 100
- **Exemple :**
  - 100 users tentent checkout
  - 75 complètent (paiement réussi)
  - Completion rate : 75%
- **Benchmarks :**
  - Critical flows (checkout, signup) : 80%+ expected
  - Secondary flows : 60%+ acceptable
  - Complex tasks (first-time) : 40-60% acceptable

**Time on Task**
- **Définition :** Temps moyen pour compléter une tâche
- **Mesure :** Start (first action) → End (goal achieved)
- **Exemple :**
  - Checkout : Objectif <3 min, measured 4.5 min → Too slow
- **Analyse :**
  - Comparer expected time vs actual
  - Identifier outliers (users bloqués > 10 min = friction majeure)
  - Track improvement over time (learnability : 2nd attempt should be faster)
- **Benchmarks :**
  - E-commerce checkout : 2-4 min
  - Form signup : 1-3 min
  - Software installation : 5-10 min

**Error Rate**
- **Types d'erreurs :**
  - **Form errors :** Validation errors, format incorrect (email, phone, credit card)
  - **Navigation errors :** Clicks incorrects, back button usage (confusion)
  - **System errors :** 404, 500, timeouts (technical issues)
- **Calcul :** (Errors / Total tasks) ou (Users who encountered error / Total users) × 100
- **Benchmarks :**
  - <5% error rate : Excellent
  - 5-10% : Acceptable
  - >10% : High friction (fix prioritaire)
- **Error recovery time :** Temps pour corriger erreur (should be <30s)

**Efficiency (Task Success / Time)**
- **Calcul :** (Task Completion Rate × 100) / (Time on Task en secondes)
- **Exemple :**
  - Completion : 80%
  - Time : 120 seconds
  - Efficiency : 80 / 120 = 0.67
- **Utilité :** Compare efficiency entre designs (variant A vs B)

**Learnability (Amélioration over time)**
- **Définition :** Réduction du Time on Task entre première et Nième utilisation
- **Mesure :**
  - Time on Task (1st attempt) : 5 min
  - Time on Task (5th attempt) : 2 min
  - Learnability : 60% réduction (bon)
- **Benchmarks :** 30-50% réduction entre 1st et 5th attempt

**Quand mesurer :** User testing (qualitative), session recordings analysis (quantitative via analytics)

---

## 2. Behavioral Metrics (Engagement & Retention)

### Engagement Metrics

**Active Users (DAU, WAU, MAU)**
- Voir section HEART - Engagement

**Stickiness (DAU/MAU)**
- **Calcul :** (DAU / MAU) × 100
- **Benchmarks :**
  - 20%+ : Excellent (daily habit)
  - 10-20% : Good
  - <10% : Poor (users don't return frequently)

**L28 (Active Days in 28)**
- **Définition :** Nombre de jours actifs sur 28 jours glissants
- **Exemple :**
  - User A : Actif 20 jours / 28 = L28 = 71% (power user)
  - User B : Actif 5 jours / 28 = L28 = 18% (casual)
- **Benchmarks :**
  - L28 > 50% : Power users
  - L28 20-50% : Regular users
  - L28 < 20% : Casual users (at-risk churn)

**Feature Engagement Rate**
- **Calcul :** (Users who used feature X in last 30 days / Total users) × 100
- **Exemple :**
  - Feature "Export PDF" : 4,000 users / 10,000 total = 40% engagement
- **Segmentation :** Par persona, plan (free vs paid), tenure (new vs veteran)

### Retention Metrics

**Retention Curves**
- **Classic Retention :** Plateau at 20-40% (good PMF)
- **Flattening Retention :** Steep drop puis plateau (typical SaaS)
- **Declining Retention :** Pas de plateau (leaky bucket, bad PMF)

**Cohort Retention**
- **Définition :** Retention par cohorte signup (Week 0, 1, 2, 4, 8, 12...)
- Voir section HEART - Retention

**Resurrection Rate**
- Voir section HEART - Retention

### Conversion Metrics

**Funnel Conversion**
- **Définition :** Conversion step-by-step dans un funnel
- **Exemple :**
  ```
  Landing → Signup → Onboarding → Activation → Paid
  100%   →  10%    →    7%       →    5%       → 2%

  Overall conversion : 2% (Landing → Paid)
  ```
- **Analyse :** Identifier biggest drop-offs (optimize priorité)

**Drop-off Rate**
- **Calcul :** (Users who dropped at step X / Users who reached step X) × 100
- **Exemple :**
  - Step 2 : 1,000 users
  - Step 3 : 700 users
  - Drop-off Step 2→3 : 30%

**Micro-conversions**
- **Définition :** Conversions intermédiaires (pas final goal, mais progress)
- **Exemples :**
  - Signup (micro) → Activation (micro) → Paid (macro conversion)
  - Add to cart (micro) → Checkout started (micro) → Purchase (macro)

---

## 3. Attitudinal Metrics (Satisfaction & Sentiment)

### Net Promoter Score (NPS)

**Question :** "Sur une échelle de 0-10, recommanderiez-vous [produit] à un ami ?"

**Classification :**
- **Promoters (9-10) :** Enthusiasts, will recommend
- **Passives (7-8) :** Satisfied but not enthusiastic
- **Detractors (0-6) :** Unhappy, may churn or spread negative WOM

**Calcul :** % Promoters - % Detractors

**Exemple :**
```
100 réponses :
- 50 Promoters (9-10) = 50%
- 30 Passives (7-8) = 30% (excluded from calculation)
- 20 Detractors (0-6) = 20%

NPS = 50% - 20% = +30
```

**Benchmarks :**
- NPS > 50 : Excellent (world-class, e.g. Apple ~60, Tesla ~90)
- NPS 30-50 : Good (above average)
- NPS 0-30 : Needs improvement
- NPS < 0 : Critical (more detractors than promoters)

**Benchmarks par industrie :**
- SaaS B2B : 30-40 (average)
- E-commerce : 45-60
- Consumer apps : 20-40
- Banking : 20-30

**Best Practices :**
- Poser après milestone (onboarding, purchase, 30j usage)
- Follow-up ouvert : "Pourquoi cette note ?" (insights qualitatifs)
- Segmenter : Par persona, plan, tenure (different NPS per segment)
- Close the loop : Contacter Detractors (understand pain, fix issues)

---

### Customer Satisfaction Score (CSAT)

**Question :** "Comment évaluez-vous votre expérience ?" (1-5 stars)

**Calcul :** (Satisfied 4-5 / Total responses) × 100

**Benchmarks :**
- CSAT > 80% : Excellent
- CSAT 70-80% : Good
- CSAT < 70% : Needs improvement

**Différence vs NPS :**
- CSAT : Satisfaction feature/interaction spécifique (granular)
- NPS : Loyalty global produit (holistic)

**Quand utiliser :**
- Post-support interaction
- Post-feature usage
- Post-checkout
- Post-onboarding

---

### System Usability Scale (SUS)

**Questionnaire 10 items** (1-5 Likert scale, alternance positive/negative).

**Items (exemples) :**
1. I think I would like to use this system frequently
2. I found the system unnecessarily complex (negative)
3. I thought the system was easy to use
4. I think I would need support to use this system (negative)
5. I found the various functions well integrated
6. [... 5 autres]

**Calcul :**
- Items impairs (1,3,5,7,9) : score = position - 1
- Items pairs (2,4,6,8,10) : score = 5 - position
- SUS = (Somme scores) × 2.5
- Range : 0-100

**Benchmarks :**
- SUS > 80 : Grade A (Excellent)
- SUS 68-80 : Grade B (Good) — 68 = moyenne industrie
- SUS 51-68 : Grade C (OK)
- SUS < 51 : Grade F (Poor)

**Quand utiliser :**
- Baseline (avant redesign)
- Post-redesign (measure improvement)
- Competitive benchmarking

**Avantage :** Standardisé, comparable cross-products

---

### Sentiment Analysis

**Sources :** Verbatims (NPS comments, support tickets, reviews, surveys, social media)

**Méthode :** NLP sentiment analysis (ML models : BERT, GPT)

**Output :**
- Sentiment score : -1 (très négatif) à +1 (très positif)
- % Positive / Neutral / Negative
- Thèmes par sentiment :
  - Positive : "great support", "intuitive UI", "fast performance"
  - Negative : "slow loading", "confusing navigation", "expensive"

**Tools :**
- MonkeyLearn, Lexalytics, Google Cloud NLP
- Custom : Python (TextBlob, VADER, Transformers)

**Best Practice :** Combiner avec NPS (ex: NPS -10, sentiment reveals "pricing concerns" → Actionable)

---

## 4. Task Success Metrics (Performance & Errors)

### Task Completion Rate

**Calcul :** (Completed tasks / Total attempted) × 100

**Benchmarks :**
- Critical flows : 80%+
- Secondary flows : 60%+

**Analyse :** Funnel analysis (identify step with highest drop-off)

---

### Time on Task

**Mesure :** Temps moyen pour compléter tâche

**Analyse :**
- Comparer expected vs actual
- Identifier outliers (blocked users)
- Track learnability (improvement over time)

---

### Error Rate

**Types :**
- Form validation errors
- Navigation errors (wrong clicks)
- System errors (404, 500, timeout)

**Calcul :** (Errors / Total tasks) × 100

**Benchmarks :**
- <5% : Excellent
- 5-10% : Acceptable
- >10% : High friction

---

### Efficiency Metrics

**Clicks to Complete**
- **Définition :** Nombre de clicks pour atteindre goal
- **Benchmark :** Minimize (3-click rule pour e-commerce)

**Scroll Depth**
- **Définition :** % page scrollée
- **Benchmark :** CTA should be visible <50% scroll (above fold)

**Dead Clicks**
- **Définition :** Clicks sur éléments non-cliquables
- **Signal :** Confusion affordance (looks clickable but isn't)

**Rage Clicks**
- **Définition :** Clicks répétés rapides (3+ clicks rapides même zone)
- **Signal :** Frustration (élément cassé, loading lent, bug)

---

## 5. UX KPIs par Objectif Business

### Objectif : Acquisition

**UX Metrics :**
- Landing page bounce rate : <60% (good), <40% (excellent)
- Signup conversion rate :
  - B2C : 2-5%
  - B2B SaaS : 5-10%
  - Freemium : 10-25%
- Time to signup : <3 minutes (ideal)
- Form abandonment rate : <30%

**Optimizations :**
- Clarify value prop (reduce bounce)
- Reduce form fields (increase conversion)
- Add trust signals (increase conversion)

---

### Objectif : Activation (Onboarding)

**UX Metrics :**
- Activation rate : 40-60% (good), 60%+ (excellent)
- Time to first value (TTFV) : <10 min (ideal)
- Onboarding completion rate : 50-70% (good)
- Aha moment achievement : 70%+

**Optimizations :**
- Reduce onboarding steps (increase completion)
- Guide to aha moment faster (reduce TTFV)
- Progress indicator (reduce abandonment)

---

### Objectif : Retention

**UX Metrics :**
- Day 1 retention : 40-50% (good)
- Day 7 retention : 30-40% (good)
- Day 30 retention : 20-30% (good)
- Feature usage frequency : Weekly active users per feature

**Optimizations :**
- Habit formation (push notifications, email reminders)
- Feature discovery (in-app tooltips)
- Continuous value delivery (new content, features)

---

### Objectif : Revenue (Monetization)

**UX Metrics :**
- Trial to paid conversion :
  - SaaS : 20-40%
  - Freemium : 2-5%
- Upgrade rate (free to premium) : 2-5%
- Checkout abandonment : <70% (e-commerce average 70%)
- Payment method errors : <5%

**Optimizations :**
- Value demonstration (show ROI before paywall)
- Frictionless checkout (guest checkout, multiple payment methods)
- Trust signals at payment (reduce abandonment)

---

### Objectif : Referral (Viral Growth)

**UX Metrics :**
- NPS : >50 (strong referral potential)
- Invite sent rate : % users sending invite
- Invite acceptance rate : 20-40%
- Viral coefficient (K) : >1.0 (viral growth)
  - Calculation : K = (invites sent per user) × (invite acceptance rate)
  - K > 1 : Viral (exponential growth)
  - K < 1 : Non-viral (paid acquisition needed)

**Optimizations :**
- Incentivize referrals (both sides win)
- Easy sharing (one-click, pre-filled message)
- Social proof (show friends using product)

---

## 6. North Star Metric (NSM)

**Définition :** LA métrique unique qui capture la valeur core pour users ET business.

**Exemples par industrie :**
- **Airbnb :** Nights Booked
- **Facebook :** Daily Active Users (DAU)
- **Spotify :** Time Spent Listening
- **Slack :** Messages Sent by Teams
- **Dropbox :** Files Saved
- **Medium :** Total Reading Time
- **Uber :** Rides Completed
- **Amazon :** Purchases per Month

**Critères d'un bon NSM :**
1. ✅ Reflète valeur core pour users (users get value)
2. ✅ Mesurable facilement (data available)
3. ✅ Actionnable (équipe peut influencer)
4. ✅ Leading indicator (prédit revenue future)
5. ✅ Compréhensible par tous (exec, product, eng, design)

**Trouver votre NSM :**
```
Question : "Si vous ne pouviez tracker qu'UNE SEULE métrique, laquelle ?"

Mauvaises réponses (vanity metrics) :
❌ Total signups (ne mesure pas usage réel)
❌ Page views (ne mesure pas valeur)

Bonnes réponses (value-driven) :
✅ Active users (utilisation réelle)
✅ Transactions completed (valeur échangée)
✅ Content consumed (engagement meaningful)
```

---

## 7. Métriques par Type d'Application

### SaaS B2B

**Priorité :**
- Activation rate (onboarding critical)
- Weekly active users (engagement business)
- Feature adoption rate (differentiation)
- Time to value (TTFV) (reduce friction)
- NPS & CSAT (B2B = relationship business)
- Churn rate (<5% monthly = good)

**NSM typique :** Weekly Active Teams, ARR (Annual Recurring Revenue)

---

### E-commerce

**Priorité :**
- Add to cart rate (intent to purchase)
- Checkout abandonment rate (70% avg, reduce to <60%)
- Time to purchase (minimize friction)
- Product findability (search success rate)
- Return rate (<10% good)
- Repeat purchase rate (loyalty)

**NSM typique :** Orders per Month, GMV (Gross Merchandise Value)

---

### Mobile Apps

**Priorité :**
- App opens per week (engagement)
- Session length (depth)
- Retention (D1, D7, D30) (loyalty)
- Crash rate (<1%) (quality)
- App store rating (4.5+ stars) (acquisition)

**NSM typique :** Daily Active Users, Session Duration

---

### Content Platforms (Media, Social)

**Priorité :**
- Time spent in app/site (engagement deep)
- Content consumption rate (articles read, videos watched)
- Engagement rate (likes, comments, shares) (participation)
- Creator metrics (content uploaded) (supply side)
- Retention (come back for more content)

**NSM typique :** Total Time Spent, Content Consumed

---

## 8. Dashboards & Reporting

### Executive Dashboard (Stakeholders)

**Métriques clés :**
- North Star Metric (trend month-over-month)
- HEART scores (monthly rollup)
- NPS trend (quarterly)
- Key conversion funnels (acquisition, activation, monetization)
- Business impact (revenue, churn, LTV)

**Format :** High-level visuals, % change MoM/YoY, traffic light (red/yellow/green)

**Frequency :** Weekly review, monthly deep dive

---

### Product Team Dashboard (Weekly)

**Métriques clés :**
- Feature adoption rates (new features launched)
- Funnel drop-offs (identify friction points)
- Task completion rates (usability)
- Error rates (bugs, UX issues)
- User feedback themes (top 5 pain points)

**Format :** Actionnable insights, drill-down capability, segmentation (by persona, device, geo)

**Frequency :** Daily monitoring, weekly review

---

### UX Researcher Dashboard (Continuous)

**Métriques clés :**
- User testing task success rates (benchmark <80% = usability issue)
- SUS scores (track improvement post-redesign)
- Sentiment analysis (themes by sentiment)
- Session recordings insights (friction patterns)
- Support tickets categorization (top issues)

**Format :** Qualitative + quantitative synthesis, annotations (screenshots, quotes)

**Frequency :** Continuous collection, bi-weekly synthesis

---

## 9. Tools & Platforms

### Analytics Platforms

**Google Analytics 4 (GA4)**
- Web analytics standard (free)
- Funnels, cohorts, events tracking
- Limitations : Échantillonnage si > 10M events

**Mixpanel**
- Product analytics (SaaS focus)
- Retention, funnel, A/B testing
- Pricing : Free tier 100K users, puis paid

**Amplitude**
- Behavioral analytics, user journeys
- Advanced cohorts, predictive analytics
- Pricing : Free tier 10M events/month

**Heap**
- Auto-capture analytics (no code tracking)
- Retroactive analysis (define events after fact)

**Pendo**
- Product analytics + in-app guidance
- Feature adoption, NPS, walkthroughs

---

### Heatmaps & Session Recordings

**Hotjar**
- Heatmaps (click, scroll, move maps)
- Session recordings
- Surveys (NPS, CSAT)
- Pricing : Free tier 35 sessions/day

**FullStory**
- Session replay (high fidelity)
- Frustration signals (rage clicks, dead clicks)
- Search by user action (find users who...)

**Microsoft Clarity**
- Free heatmaps & session recordings
- Integrates with GA4

---

### User Testing

**UserTesting.com**
- Remote user testing (video + audio)
- Recruit participants (or use your users)
- Pricing : $49/video

**Maze**
- Rapid prototype testing with metrics
- Task completion, misclick rate, time on task
- Integrates with Figma

**Lookback**
- User interviews & testing
- Live or self-test

---

### Surveys & Feedback

**Qualtrics**
- Enterprise surveys (NPS, CSAT, SUS)
- Advanced analytics, text analysis

**SurveyMonkey**
- Standard surveys
- Templates NPS, CSAT

**Typeform**
- Engaging forms (conversational UI)
- Good response rates

**Delighted**
- NPS tracking (automated)
- Integrates with CRM

---

## 10. Best Practices

### 1. Choisir les Bonnes Métriques

✅ **DO :**
- Aligner metrics avec business objectives (revenue, retention, acquisition)
- Combiner quantitatif + qualitatif (HEART framework)
- Tracked leading indicators (predictive : activation → retention → revenue)
- Segmenter par persona, plan, cohort (insights actionnables)

❌ **DON'T :**
- Vanity metrics (total signups sans activation = meaningless)
- Metrics non actionnables (cannot influence)
- Too many metrics (focus top 5-10 max)

---

### 2. Établir Baselines

- Mesurer état actuel AVANT changements (baseline)
- Documenter méthodologie de mesure (ensure consistency)
- Définir targets réalistes (benchmarks industry)
- Example : "Current NPS = 25, Target = 40 (12 months)"

---

### 3. Continuous Monitoring

- Dashboards temps réel (weekly review minimum)
- Alertes sur anomalies (sudden drop conversion = investigate)
- Cohort analysis pour retention (identify trends)
- A/B testing pour validation causale (correlation ≠ causation)

---

### 4. Storytelling avec Data

- Lier metrics à user stories ("NPS dropped because..." + user quote)
- Visualiser trends over time (line charts, not just single number)
- Segmentation insights ("Power users NPS = 60, casual users = 10 → different needs")
- Actionnable recommendations ("To improve NPS from 25 to 40, we should...")

---

### 5. Éviter les Pièges

**Correlation ≠ Causation**
- Example : Ice cream sales correlate with drowning (both caused by summer, not causal)
- Solution : A/B testing pour prouver causalité

**Survivorship Bias**
- Example : Analyser uniquement retained users (ignorer churned = miss insights)
- Solution : Analyser churned users aussi (exit surveys)

**Seasonality**
- Example : E-commerce spike Nov-Dec (holidays, pas amélioration UX)
- Solution : Compare YoY (Dec 2025 vs Dec 2024)

**Simpson's Paradox**
- Example : Overall metric improves, mais chaque segment décline
- Solution : Analyze segments separately

---

## Ressources

### Lectures Recommandées

**Livres :**
- **"Measuring the User Experience"** - Tullis & Albert (bible UX metrics)
- **"Lean Analytics"** - Croll & Yoskovitz (startup metrics)
- **"The Lean Startup"** - Eric Ries (Build-Measure-Learn)
- **"Hooked"** - Nir Eyal (engagement loops, habit formation)

**Articles & Papers :**
- **Google HEART Framework** - Kerry Rodden et al.
- **AARRR Pirate Metrics** - Dave McClure (Acquisition, Activation, Retention, Revenue, Referral)
- **Nielsen Norman Group** : "UX Metrics" articles

---

### Outils de Calcul

**Sample Size Calculators (A/B tests) :**
- Evan Miller : https://www.evanmiller.org/ab-testing/
- Optimizely : https://www.optimizely.com/sample-size-calculator/

**NPS Calculator :**
- Delighted : https://delighted.com/nps-calculator

**SUS Score Calculator :**
- MeasuringU : https://measuringu.com/sus/

**Cohort Retention Analysis Templates :**
- Amplitude templates
- Mixpanel templates

---

### Benchmarks Sources

**Industry Benchmarks :**
- **Mixpanel Product Benchmarks** : https://mixpanel.com/benchmarks/
- **Amplitude Benchmarks** : Retention, engagement by industry
- **Baymard Institute** : E-commerce UX benchmarks

**App Store Ratings :**
- **Average rating :** 4.0-4.5 (good), 4.5+ (excellent)

**NPS Benchmarks :**
- **Retently** : NPS benchmarks by industry

---

## 11. Templates & Examples

### Template : Metrics Selection Matrix

```
Objectif Business : Increase Retention

| Métrique | Priorité | Current | Target | Track Frequency | Owner |
|----------|----------|---------|--------|-----------------|-------|
| D7 Retention | P0 | 25% | 35% | Weekly | Product |
| D30 Retention | P0 | 12% | 20% | Weekly | Product |
| Feature Adoption (X) | P1 | 15% | 30% | Weekly | Growth |
| NPS | P1 | 20 | 40 | Monthly | CX |
| Session Frequency | P2 | 3/month | 6/month | Weekly | Product |
```

---

### Example : HEART Metrics Dashboard (SaaS)

```
Product : Acme CRM (SaaS B2B)

HEART Metrics (Current Month vs Last Month)

H - Happiness
├─ NPS : 35 (↑ +5 vs last month) ✅
├─ CSAT : 78% (↑ +3pp)
└─ Support tickets : 120 (↓ -15)

E - Engagement
├─ DAU/MAU : 22% (↑ +2pp) ✅
├─ WAU : 3,500 (↑ +200)
├─ Session duration : 18 min (→ flat)
└─ Feature "Reports" adoption : 35% (↑ +10pp) 🎉

A - Adoption
├─ Signups : 450 (↑ +50)
├─ Activation rate : 55% (↑ +5pp) ✅
├─ TTFV : 12 min (↓ -3 min improvement) ✅
└─ Onboarding completion : 68% (↑ +8pp)

R - Retention
├─ D7 : 42% (→ flat)
├─ D30 : 28% (↑ +3pp) ✅
├─ Churn : 6.5% (↓ -0.5pp) ✅
└─ Cohort Feb 2026 : Retention curve flattening ✅

T - Task Success
├─ Report creation success : 85% (↑ +5pp)
├─ Data export errors : 3% (↓ -2pp) ✅
└─ Avg time to create report : 4 min (↓ -1 min)

North Star Metric : Weekly Active Teams = 850 (↑ +50, +6.3% MoM) 🎉

Key Insights :
✅ Engagement up (DAU/MAU +2pp)
✅ Activation improving (TTFV reduced, onboarding completion up)
✅ Retention D30 growing (+3pp)
⚠️ D7 retention flat (investigate)

Recommendations :
1. Focus on D7 retention (identify drop-off point Week 1)
2. Scale "Reports" feature adoption (35% → 50% target, high engagement correlation)
3. Continue optimizing onboarding (TTFV <10 min goal)
```

---

**Dernière mise à jour :** Janvier 2026 (v1.0)
**Auteur :** UX Metrics Reference Framework
**Sources :** Google HEART Framework, Mixpanel Benchmarks, Nielsen Norman Group, Baymard Institute, Lean Analytics
