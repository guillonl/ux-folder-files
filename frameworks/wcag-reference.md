# WCAG 2.1/2.2 Reference - Web Content Accessibility Guidelines

## Vue d'Ensemble

Les **Web Content Accessibility Guidelines (WCAG)** sont les standards internationaux pour l'accessibilité web, développés par le W3C (World Wide Web Consortium). Ce document couvre WCAG 2.1 (2018) et WCAG 2.2 (2023).

### Structure Hiérarchique

```
WCAG Structure :

4 PRINCIPES (POUR)
└── 13 GUIDELINES
    └── 78 SUCCESS CRITERIA
        └── 3 NIVEAUX (A, AA, AAA)
```

### Niveaux de Conformité

| Niveau | Description | Critères | Usage |
|--------|-------------|----------|-------|
| **A** | Minimum | 30 critères | Barrières critiques éliminées |
| **AA** | Standard | 20 critères | Légalement requis (EU, US gov) |
| **AAA** | Excellence | 28 critères | Rarement requis en totalité |

**Note :** Pour être conforme à un niveau, TOUS les critères de ce niveau et des niveaux inférieurs doivent passer.

---

## Principe 1 : PERCEIVABLE (Perceptible)

**"L'information et les composants de l'interface utilisateur doivent être présentés aux utilisateurs de manière à ce qu'ils puissent les percevoir."**

L'utilisateur doit pouvoir percevoir l'information présentée (elle ne peut pas être invisible à tous ses sens).

---

### 1.1 Text Alternatives

**Objectif :** Fournir des alternatives textuelles pour tout contenu non textuel.

#### 1.1.1 Non-text Content (Niveau A)

**Critère :** Tout contenu non textuel présenté à l'utilisateur a une alternative textuelle qui remplit une fonction équivalente.

**Exceptions :**
- **Controls, Input** : Si le contenu non textuel est un contrôle ou accepte une entrée utilisateur, il a un nom qui décrit sa fonction
- **Time-based Media** : Les alternatives textuelles fournissent au moins une identification descriptive
- **Test** : Si le contenu non textuel est un test qui serait invalide avec texte
- **Sensory** : Si le contenu non textuel est principalement destiné à créer une expérience sensorielle spécifique
- **CAPTCHA** : Alternatives sont fournies qui identifient et décrivent le but
- **Decoration, Formatting, Invisible** : Implémenté de façon à être ignoré par technologies d'assistance

**Exemples de conformité :**

```html
<!-- Image informative -->
<img src="chart.png" alt="Graphique montrant une augmentation de 25% des ventes entre Q1 et Q4 2025">

<!-- Image décorative -->
<img src="decoration.png" alt="" role="presentation">

<!-- Bouton icône -->
<button aria-label="Fermer la fenêtre">
  <svg><!-- icône X --></svg>
</button>

<!-- Input avec label -->
<label for="search">Rechercher</label>
<input type="search" id="search" name="search">
```

**Violations courantes :**
- `<img>` sans attribut alt
- alt="image" ou alt="photo" (non descriptif)
- Icônes sans aria-label
- CAPTCHAs sans alternative audio

---

### 1.2 Time-based Media

**Objectif :** Fournir des alternatives pour les médias temporels.

#### 1.2.1 Audio-only and Video-only (Prerecorded) - Niveau A

**Critère :** Pour les médias préenregistrés audio seul ou vidéo seul :
- **Audio seul** : Une alternative textuelle (transcription) est fournie
- **Vidéo seul** : Une alternative (transcription ou piste audio) est fournie

#### 1.2.2 Captions (Prerecorded) - Niveau A

**Critère :** Des sous-titres sont fournis pour tout contenu audio préenregistré dans un média synchronisé.

**Exigences sous-titres :**
- Synchronisés avec la vidéo
- Incluent dialogues ET sons significatifs (musique, bruits)
- Identifient les locuteurs quand nécessaire

```html
<video controls>
  <source src="video.mp4" type="video/mp4">
  <track kind="captions" src="captions-fr.vtt" srclang="fr" label="Français" default>
  <track kind="captions" src="captions-en.vtt" srclang="en" label="English">
</video>
```

#### 1.2.3 Audio Description or Media Alternative (Prerecorded) - Niveau A

**Critère :** Une alternative pour médias temporels ou une audiodescription du contenu vidéo est fournie.

#### 1.2.4 Captions (Live) - Niveau AA

**Critère :** Des sous-titres sont fournis pour tout contenu audio en direct dans un média synchronisé.

#### 1.2.5 Audio Description (Prerecorded) - Niveau AA

**Critère :** Une audiodescription est fournie pour tout contenu vidéo préenregistré.

**Audiodescription :** Narration audio décrivant les éléments visuels importants (actions, personnages, texte à l'écran).

---

### 1.3 Adaptable

**Objectif :** Créer du contenu présentable de différentes manières sans perte d'information.

#### 1.3.1 Info and Relationships - Niveau A

**Critère :** L'information, la structure et les relations véhiculées par la présentation peuvent être déterminées par programmation ou sont disponibles en texte.

**Exemples conformité :**

```html
<!-- Structure headings correcte -->
<h1>Titre principal</h1>
  <h2>Section 1</h2>
    <h3>Sous-section 1.1</h3>
  <h2>Section 2</h2>

<!-- Liste sémantique -->
<ul>
  <li>Item 1</li>
  <li>Item 2</li>
</ul>

<!-- Tableau avec headers -->
<table>
  <caption>Ventes trimestrielles</caption>
  <thead>
    <tr>
      <th scope="col">Trimestre</th>
      <th scope="col">Ventes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Q1</td>
      <td>100K€</td>
    </tr>
  </tbody>
</table>

<!-- Formulaire avec labels -->
<label for="email">Email (requis)</label>
<input type="email" id="email" required aria-describedby="email-help">
<span id="email-help">Format : exemple@domaine.com</span>
```

**Violations courantes :**
- Headings sautés (H1 → H3)
- Listes visuelles sans `<ul>/<ol>`
- Tableaux sans `<th>` ou scope
- Labels non associés (`for` manquant)

#### 1.3.2 Meaningful Sequence - Niveau A

**Critère :** Quand la séquence du contenu affecte sa signification, une séquence de lecture correcte peut être déterminée par programmation.

**Test :** Désactiver CSS et vérifier que l'ordre DOM correspond à l'ordre logique de lecture.

#### 1.3.3 Sensory Characteristics - Niveau A

**Critère :** Les instructions ne reposent pas uniquement sur caractéristiques sensorielles (forme, couleur, taille, emplacement, orientation, son).

**Non conforme :**
> "Cliquez sur le bouton vert à droite"
> "Les erreurs sont en rouge"

**Conforme :**
> "Cliquez sur le bouton 'Soumettre' (vert, à droite)"
> "Les erreurs sont marquées avec l'icône ⚠️ et en rouge"

#### 1.3.4 Orientation - Niveau AA (WCAG 2.1)

**Critère :** Le contenu ne restreint pas son affichage à une seule orientation (portrait/paysage) sauf si essentiel.

```html
<!-- Non conforme -->
<meta name="viewport" content="width=device-width, initial-scale=1, orientation=portrait">
```

#### 1.3.5 Identify Input Purpose - Niveau AA (WCAG 2.1)

**Critère :** La finalité de chaque champ de saisie d'informations personnelles peut être déterminée par programmation (autocomplete).

```html
<input type="text" name="name" autocomplete="name">
<input type="email" autocomplete="email">
<input type="tel" autocomplete="tel">
<input type="text" autocomplete="street-address">
```

**Valeurs autocomplete courantes :**
- `name`, `given-name`, `family-name`
- `email`, `tel`
- `street-address`, `postal-code`, `country`
- `cc-name`, `cc-number`, `cc-exp`
- `username`, `new-password`, `current-password`

---

### 1.4 Distinguishable

**Objectif :** Faciliter la perception du contenu, notamment séparer premier plan et arrière-plan.

#### 1.4.1 Use of Color - Niveau A

**Critère :** La couleur n'est pas utilisée comme seul moyen visuel de transmettre une information, indiquer une action, demander une réponse ou distinguer un élément.

**Non conforme :**
- Liens uniquement distingués par couleur (sans soulignement)
- Erreurs formulaire uniquement en rouge
- Graphiques avec légende couleur uniquement

**Conforme :**
- Liens colorés ET soulignés
- Erreurs : couleur + icône + texte
- Graphiques : couleur + pattern/texture + labels

#### 1.4.2 Audio Control - Niveau A

**Critère :** Si un audio joue automatiquement plus de 3 secondes, un mécanisme permet de le mettre en pause/arrêter, ou de contrôler le volume indépendamment du système.

#### 1.4.3 Contrast (Minimum) - Niveau AA

**Critère :** La présentation visuelle du texte et des images de texte a un ratio de contraste d'au moins :
- **4.5:1** pour texte normal
- **3:1** pour texte large (≥18pt ou ≥14pt bold)

**Exceptions :** Logos, texte décoratif, texte désactivé

**Outils de test :**
- WebAIM Contrast Checker
- Colour Contrast Analyser
- Chrome DevTools (Inspect element → Accessibility)

```css
/* Conforme (ratio ~8:1) */
body {
  color: #333333;
  background: #ffffff;
}

/* Non conforme (ratio ~2.5:1) */
.light-text {
  color: #999999;
  background: #ffffff;
}
```

#### 1.4.4 Resize Text - Niveau AA

**Critère :** Le texte peut être redimensionné jusqu'à 200% sans technologie d'assistance et sans perte de contenu ou fonctionnalité.

**Test :** Zoom navigateur à 200%, vérifier :
- Pas de texte tronqué
- Pas de chevauchement
- Toutes fonctionnalités accessibles

```css
/* Recommandé : unités relatives */
body {
  font-size: 1rem; /* 16px par défaut */
}

h1 {
  font-size: 2rem; /* Scale avec zoom */
}

/* Éviter : unités fixes pour le texte */
.bad {
  font-size: 14px; /* Ne scale pas bien */
}
```

#### 1.4.5 Images of Text - Niveau AA

**Critère :** Si les technologies utilisées permettent la présentation visuelle, le texte est utilisé plutôt que les images de texte.

**Exceptions :**
- Personnalisable (l'utilisateur peut ajuster l'image de texte)
- Essentiel (logo, marque)

#### 1.4.10 Reflow - Niveau AA (WCAG 2.1)

**Critère :** Le contenu peut être présenté sans perte d'information ou fonctionnalité, et sans nécessiter de défilement bidimensionnel pour :
- Contenu vertical défilant à largeur 320 CSS pixels
- Contenu horizontal défilant à hauteur 256 CSS pixels

**Test :** Viewport 320px largeur, vérifier pas de scroll horizontal.

```css
/* Responsive design */
.container {
  max-width: 100%;
  overflow-wrap: break-word;
}

img {
  max-width: 100%;
  height: auto;
}
```

#### 1.4.11 Non-text Contrast - Niveau AA (WCAG 2.1)

**Critère :** Les composants UI et objets graphiques ont un ratio de contraste d'au moins **3:1** contre les couleurs adjacentes.

**Applies to :**
- Bordures de champs de formulaire
- Boutons (bordure ou fond)
- Icônes significatives
- Focus indicators
- Graphiques/diagrammes

#### 1.4.12 Text Spacing - Niveau AA (WCAG 2.1)

**Critère :** Aucune perte de contenu ou fonctionnalité quand l'utilisateur modifie :
- Line height : 1.5× font size
- Paragraph spacing : 2× font size
- Letter spacing : 0.12× font size
- Word spacing : 0.16× font size

**Test :** Bookmarklet qui applique ces styles, vérifier pas de troncation.

#### 1.4.13 Content on Hover or Focus - Niveau AA (WCAG 2.1)

**Critère :** Quand du contenu additionnel apparaît au hover/focus, il est :
- **Dismissable** : Peut être fermé sans déplacer hover/focus (sauf erreur)
- **Hoverable** : Le pointer peut se déplacer sur le contenu sans qu'il disparaisse
- **Persistent** : Reste visible jusqu'à ce que l'utilisateur le ferme ou l'info ne soit plus valide

```css
/* Tooltip conforme */
.tooltip {
  /* Reste visible quand on hover le tooltip lui-même */
  /* Escape key le ferme */
  /* Persist jusqu'à action utilisateur */
}
```

---

## Principe 2 : OPERABLE (Utilisable)

**"Les composants de l'interface utilisateur et la navigation doivent être utilisables."**

Les utilisateurs doivent pouvoir utiliser l'interface (elle ne peut pas requérir une interaction qu'un utilisateur ne peut pas effectuer).

---

### 2.1 Keyboard Accessible

**Objectif :** Rendre toutes les fonctionnalités accessibles au clavier.

#### 2.1.1 Keyboard - Niveau A

**Critère :** Toutes les fonctionnalités du contenu sont utilisables via une interface clavier sans timing spécifique pour les frappes individuelles.

**Exception :** La fonction sous-jacente requiert un input dépendant du chemin du mouvement de l'utilisateur (ex: dessin à main levée).

**Touches clavier standard :**
- **Tab** : Focus élément suivant
- **Shift+Tab** : Focus élément précédent
- **Enter/Space** : Activer élément
- **Arrows** : Naviguer dans composants (menus, tabs)
- **Escape** : Fermer modal/dropdown

```html
<!-- Conforme : bouton natif -->
<button onclick="submit()">Submit</button>

<!-- Non conforme : div cliquable -->
<div onclick="submit()">Submit</div>

<!-- Conforme si nécessaire div custom -->
<div role="button" tabindex="0" onclick="submit()" onkeydown="handleKeydown(event)">
  Submit
</div>
```

#### 2.1.2 No Keyboard Trap - Niveau A

**Critère :** Si le focus clavier peut être déplacé vers un composant de la page, le focus peut être déplacé hors de ce composant en utilisant uniquement le clavier.

**Violations courantes :**
- Modals sans gestion focus (trap sans escape)
- Widgets custom (date pickers, dropdowns)
- Iframe sans échappement

```javascript
// Modal accessible : trap focus mais permet Escape
document.addEventListener('keydown', function(e) {
  if (e.key === 'Escape') {
    closeModal();
    returnFocusToTrigger();
  }
});
```

#### 2.1.4 Character Key Shortcuts - Niveau A (WCAG 2.1)

**Critère :** Si un raccourci clavier utilisant uniquement des lettres, chiffres, ponctuation ou symboles existe, alors au moins une des conditions est vraie :
- **Turn off** : Mécanisme pour désactiver le raccourci
- **Remap** : Mécanisme pour remapper vers une touche non imprimable (Ctrl, Alt)
- **Active only on focus** : Le raccourci n'est actif que quand le composant a le focus

---

### 2.2 Enough Time

**Objectif :** Fournir assez de temps aux utilisateurs pour lire et utiliser le contenu.

#### 2.2.1 Timing Adjustable - Niveau A

**Critère :** Pour chaque limite de temps fixée par le contenu, au moins une des conditions est vraie :
- **Turn off** : L'utilisateur peut désactiver la limite avant de la rencontrer
- **Adjust** : L'utilisateur peut ajuster la limite (au moins 10× la durée par défaut)
- **Extend** : L'utilisateur est averti et a au moins 20 secondes pour prolonger avec une action simple

**Exceptions :** Temps réel (enchères), essentiel, 20+ heures.

#### 2.2.2 Pause, Stop, Hide - Niveau A

**Critère :** Pour les informations en mouvement, clignotantes, défilantes ou mises à jour automatiquement :
- **Moving, blinking, scrolling** qui démarre automatiquement, dure >5 secondes, et est présenté en parallèle d'autre contenu → mécanisme pause/stop/hide
- **Auto-updating** qui démarre automatiquement et présenté avec autre contenu → mécanisme pause/stop/hide OU contrôle fréquence

```html
<!-- Carrousel conforme -->
<div class="carousel">
  <button aria-label="Pause le carrousel">⏸</button>
  <!-- slides -->
</div>
```

---

### 2.3 Seizures and Physical Reactions

**Objectif :** Ne pas concevoir de contenu pouvant provoquer des crises.

#### 2.3.1 Three Flashes or Below Threshold - Niveau A

**Critère :** Les pages web ne contiennent rien qui clignote plus de trois fois par seconde, ou le clignotement est sous les seuils de flash général et de flash rouge.

**Test :** Photosensitive Epilepsy Analysis Tool (PEAT)

---

### 2.4 Navigable

**Objectif :** Fournir des moyens pour aider les utilisateurs à naviguer, trouver le contenu, et déterminer où ils sont.

#### 2.4.1 Bypass Blocks - Niveau A

**Critère :** Un mécanisme permet de contourner les blocs de contenu répétés sur plusieurs pages.

```html
<!-- Skip link -->
<a href="#main-content" class="skip-link">Aller au contenu principal</a>

<nav><!-- Navigation répétée --></nav>

<main id="main-content">
  <!-- Contenu principal -->
</main>
```

```css
.skip-link {
  position: absolute;
  left: -9999px;
}

.skip-link:focus {
  position: static;
  /* Visible quand focus */
}
```

#### 2.4.2 Page Titled - Niveau A

**Critère :** Les pages web ont des titres qui décrivent le sujet ou la finalité.

```html
<!-- Conforme -->
<title>Panier d'achat - Mon Site E-commerce</title>
<title>Contact - Mon Site E-commerce</title>

<!-- Non conforme -->
<title>Page</title>
<title>Mon Site E-commerce</title> <!-- Même titre partout -->
```

#### 2.4.3 Focus Order - Niveau A

**Critère :** Si une page peut être naviguée séquentiellement et que les séquences de navigation affectent la signification ou l'opération, les composants focusables reçoivent le focus dans un ordre qui préserve signification et opérabilité.

**Test :** Tab à travers la page, vérifier ordre logique (haut→bas, gauche→droite).

#### 2.4.4 Link Purpose (In Context) - Niveau A

**Critère :** La finalité de chaque lien peut être déterminée par le texte du lien seul ou par le texte du lien avec son contexte déterminable par programmation.

```html
<!-- Non conforme -->
<a href="/products">Cliquez ici</a>
<a href="/docs/spec.pdf">Lire plus</a>

<!-- Conforme -->
<a href="/products">Voir tous les produits</a>
<a href="/docs/spec.pdf">Télécharger les spécifications (PDF, 2MB)</a>

<!-- Conforme avec contexte -->
<p>Notre nouveau produit révolutionne le marché. <a href="/products/new">En savoir plus sur le nouveau produit</a></p>
```

#### 2.4.5 Multiple Ways - Niveau AA

**Critère :** Plus d'une façon est disponible pour localiser une page dans un ensemble de pages.

**Exemples :**
- Navigation principale + recherche
- Navigation + plan du site
- Navigation + breadcrumbs
- Navigation + liens connexes

#### 2.4.6 Headings and Labels - Niveau AA

**Critère :** Les titres (headings) et labels décrivent le sujet ou la finalité.

#### 2.4.7 Focus Visible - Niveau AA

**Critère :** Toute interface utilisateur opérable au clavier a un mode d'opération où l'indicateur de focus clavier est visible.

```css
/* Conforme : focus visible */
:focus {
  outline: 2px solid #005fcc;
  outline-offset: 2px;
}

/* Non conforme : suppression focus */
:focus {
  outline: none; /* INTERDIT sans alternative */
}

/* Alternative acceptable */
:focus:not(:focus-visible) {
  outline: none;
}

:focus-visible {
  outline: 2px solid #005fcc;
}
```

#### 2.4.11 Focus Not Obscured (Minimum) - Niveau AA (WCAG 2.2)

**Critère :** Quand un composant UI reçoit le focus clavier, le composant n'est pas entièrement caché par du contenu créé par l'auteur.

**Violations courantes :**
- Sticky headers couvrant le focus
- Cookie banners couvrant contenu
- Chat widgets couvrant navigation

---

### 2.5 Input Modalities

**Objectif :** Faciliter l'utilisation de différentes modalités d'entrée au-delà du clavier.

#### 2.5.1 Pointer Gestures - Niveau A (WCAG 2.1)

**Critère :** Toute fonctionnalité utilisant des gestes multipoint ou basés sur un chemin peut être opérée avec un pointeur simple sans geste basé sur chemin.

**Exemples :**
- Pinch-to-zoom → Boutons +/-
- Swipe → Boutons suivant/précédent
- Drag → Click + move + click

#### 2.5.2 Pointer Cancellation - Niveau A (WCAG 2.1)

**Critère :** Pour fonctionnalités opérées via single pointer, au moins une condition :
- **No Down-Event** : L'action n'est pas exécutée sur le down-event
- **Abort or Undo** : Complétion sur up-event, avec mécanisme pour abort ou undo
- **Up Reversal** : Up-event inverse tout effet du down-event
- **Essential** : Complétion sur down-event est essentielle

#### 2.5.3 Label in Name - Niveau A (WCAG 2.1)

**Critère :** Pour composants UI avec labels incluant texte ou images de texte, le nom contient le texte présenté visuellement.

```html
<!-- Conforme : aria-label contient le texte visible -->
<button aria-label="Rechercher dans le catalogue">Rechercher</button>

<!-- Non conforme : aria-label ne contient pas "Rechercher" -->
<button aria-label="Find items">Rechercher</button>
```

#### 2.5.4 Motion Actuation - Niveau A (WCAG 2.1)

**Critère :** Fonctionnalités opérées par device motion ou user motion peuvent aussi être opérées par composants UI, et réponse au motion peut être désactivée.

**Exemples :**
- Shake to undo → Bouton undo
- Tilt to scroll → Scroll standard

#### 2.5.7 Dragging Movements - Niveau AA (WCAG 2.2)

**Critère :** Toute fonctionnalité utilisant un mouvement de glissement a une alternative single pointer.

**Exemples :**
- Drag-and-drop liste → Boutons monter/descendre
- Slider → Input numérique

#### 2.5.8 Target Size (Minimum) - Niveau AA (WCAG 2.2)

**Critère :** La taille de la cible pour les entrées pointer est au moins 24×24 CSS pixels.

**Exceptions :**
- **Spacing** : Target non conforme mais spacing suffisant
- **Equivalent** : Alternative conforme existe
- **Inline** : Target dans phrase/bloc texte
- **User agent control** : Contrôlé par user agent
- **Essential** : Présentation essentielle

```css
/* Conforme */
button, a {
  min-width: 44px; /* 44px recommandé, 24px minimum */
  min-height: 44px;
  padding: 12px;
}
```

---

## Principe 3 : UNDERSTANDABLE (Compréhensible)

**"L'information et l'utilisation de l'interface utilisateur doivent être compréhensibles."**

Les utilisateurs doivent pouvoir comprendre l'information et l'opération de l'interface.

---

### 3.1 Readable

**Objectif :** Rendre le contenu textuel lisible et compréhensible.

#### 3.1.1 Language of Page - Niveau A

**Critère :** La langue par défaut de chaque page web peut être déterminée par programmation.

```html
<html lang="fr">
```

#### 3.1.2 Language of Parts - Niveau AA

**Critère :** La langue de chaque passage ou phrase peut être déterminée par programmation.

```html
<html lang="fr">
<body>
  <p>Bienvenue sur notre site.</p>
  <p lang="en">This paragraph is in English.</p>
  <p>Retour au français.</p>
</body>
</html>
```

---

### 3.2 Predictable

**Objectif :** Faire fonctionner les pages de manière prévisible.

#### 3.2.1 On Focus - Niveau A

**Critère :** Quand un composant reçoit le focus, il n'initie pas de changement de contexte.

**Changement de contexte :** Navigation vers autre page, ouverture nouvelle fenêtre, déplacement focus significatif, changement majeur du contenu.

**Non conforme :**
- Select qui navigue automatiquement on change
- Focus sur champ qui ouvre popup

#### 3.2.2 On Input - Niveau A

**Critère :** Changer le paramètre d'un composant UI ne provoque pas automatiquement un changement de contexte sauf si l'utilisateur a été informé avant utilisation.

```html
<!-- Non conforme : soumission auto -->
<select onchange="this.form.submit()">
  <option>Choisir pays</option>
</select>

<!-- Conforme : bouton explicite -->
<select>
  <option>Choisir pays</option>
</select>
<button type="submit">Valider</button>
```

#### 3.2.3 Consistent Navigation - Niveau AA

**Critère :** Les mécanismes de navigation répétés sur plusieurs pages apparaissent dans le même ordre relatif chaque fois qu'ils sont répétés.

#### 3.2.4 Consistent Identification - Niveau AA

**Critère :** Les composants ayant la même fonctionnalité dans un ensemble de pages sont identifiés de manière cohérente.

**Non conforme :** "Rechercher" sur une page, "Trouver" sur une autre, "Search" sur une troisième.

---

### 3.3 Input Assistance

**Objectif :** Aider les utilisateurs à éviter et corriger les erreurs.

#### 3.3.1 Error Identification - Niveau A

**Critère :** Si une erreur de saisie est automatiquement détectée, l'item en erreur est identifié et l'erreur décrite à l'utilisateur en texte.

```html
<label for="email">Email</label>
<input type="email" id="email" aria-invalid="true" aria-describedby="email-error">
<span id="email-error" role="alert">Format email invalide. Exemple : nom@domaine.com</span>
```

#### 3.3.2 Labels or Instructions - Niveau A

**Critère :** Des labels ou instructions sont fournis quand le contenu requiert une saisie utilisateur.

```html
<!-- Label explicite -->
<label for="phone">Téléphone (format : 06 XX XX XX XX)</label>
<input type="tel" id="phone" placeholder="06 XX XX XX XX">

<!-- Instructions supplémentaires -->
<fieldset>
  <legend>Mot de passe (min 8 caractères, 1 majuscule, 1 chiffre)</legend>
  <input type="password" aria-describedby="pwd-requirements">
  <ul id="pwd-requirements">
    <li>Minimum 8 caractères</li>
    <li>Au moins 1 majuscule</li>
    <li>Au moins 1 chiffre</li>
  </ul>
</fieldset>
```

#### 3.3.3 Error Suggestion - Niveau AA

**Critère :** Si une erreur de saisie est détectée et des suggestions de correction sont connues, elles sont fournies à l'utilisateur.

**Non conforme :** "Email invalide"
**Conforme :** "Email invalide. Avez-vous voulu dire : jean@gmail.com ?"

#### 3.3.4 Error Prevention (Legal, Financial, Data) - Niveau AA

**Critère :** Pour pages causant des engagements légaux, transactions financières, modification/suppression données utilisateur, ou soumission réponses test, au moins une condition :
- **Reversible** : Soumissions sont réversibles
- **Checked** : Données vérifiées pour erreurs, possibilité correction
- **Confirmed** : Mécanisme review, confirm, correct avant finalisation

```html
<!-- Page confirmation avant achat -->
<h2>Vérifier votre commande</h2>
<p>Total : 99€</p>
<button type="button">Modifier le panier</button>
<button type="submit">Confirmer et payer</button>
```

#### 3.3.7 Redundant Entry - Niveau A (WCAG 2.2)

**Critère :** L'information précédemment entrée par ou fournie à l'utilisateur qui est requise à nouveau dans le même processus est soit :
- Auto-populated
- Disponible pour sélection

**Exemple :** Si adresse de livraison saisie, proposer "Identique à adresse de livraison" pour facturation.

#### 3.3.8 Accessible Authentication (Minimum) - Niveau AA (WCAG 2.2)

**Critère :** Un test de fonction cognitive n'est pas requis pour aucune étape d'authentification sauf si :
- **Alternative** : Autre méthode sans test cognitif disponible
- **Mechanism** : Mécanisme aide à compléter le test (copy-paste autorisé)
- **Object Recognition** : Test reconnaître objets
- **Personal Content** : Test identifier contenu personnel fourni par utilisateur

**Non conforme :** CAPTCHA texte sans alternative
**Conforme :** Passkeys, WebAuthn, SMS OTP avec paste autorisé

---

## Principe 4 : ROBUST (Robuste)

**"Le contenu doit être suffisamment robuste pour être interprété de manière fiable par une grande variété d'agents utilisateurs, y compris les technologies d'assistance."**

---

### 4.1 Compatible

**Objectif :** Maximiser la compatibilité avec les agents utilisateurs actuels et futurs, incluant technologies d'assistance.

#### 4.1.1 Parsing - Niveau A (Obsolète WCAG 2.2)

**Note :** Ce critère est obsolète dans WCAG 2.2 car les navigateurs modernes gèrent les erreurs HTML.

#### 4.1.2 Name, Role, Value - Niveau A

**Critère :** Pour tous composants UI, le nom et rôle peuvent être déterminés par programmation ; états, propriétés, et valeurs peuvent être définis par programmation ; notification des changements est disponible aux agents utilisateurs.

```html
<!-- Composant custom accessible -->
<div role="button"
     tabindex="0"
     aria-pressed="false"
     aria-label="Ajouter aux favoris">
  ♡
</div>

<!-- Toggle conforme -->
<button aria-pressed="false" onclick="toggle(this)">
  Mode sombre
</button>

<!-- Tab panel conforme -->
<div role="tablist">
  <button role="tab" aria-selected="true" aria-controls="panel1">Tab 1</button>
  <button role="tab" aria-selected="false" aria-controls="panel2">Tab 2</button>
</div>
<div role="tabpanel" id="panel1">Contenu 1</div>
<div role="tabpanel" id="panel2" hidden>Contenu 2</div>
```

**ARIA Roles courants :**
- `button`, `link`, `checkbox`, `radio`
- `tab`, `tablist`, `tabpanel`
- `menu`, `menuitem`, `menubar`
- `dialog`, `alertdialog`
- `navigation`, `main`, `banner`, `contentinfo`

**ARIA States/Properties courants :**
- `aria-expanded`, `aria-pressed`, `aria-checked`
- `aria-selected`, `aria-current`
- `aria-hidden`, `aria-disabled`
- `aria-label`, `aria-labelledby`, `aria-describedby`
- `aria-live`, `aria-atomic`

#### 4.1.3 Status Messages - Niveau AA (WCAG 2.1)

**Critère :** Dans contenu implémenté avec markup, les messages de statut peuvent être déterminés par programmation via rôle ou propriétés tels qu'ils peuvent être présentés à l'utilisateur par technologies d'assistance sans recevoir le focus.

```html
<!-- Message statut annoncé -->
<div role="status" aria-live="polite">
  Article ajouté au panier
</div>

<!-- Erreur annoncée -->
<div role="alert" aria-live="assertive">
  Erreur : Connexion impossible
</div>

<!-- Progress annoncé -->
<div role="progressbar" aria-valuenow="50" aria-valuemin="0" aria-valuemax="100">
  50% complété
</div>
```

**aria-live values :**
- `polite` : Attend pause utilisateur (status, notifications non urgentes)
- `assertive` : Interrompt immédiatement (erreurs critiques, alertes)
- `off` : Pas d'annonce

---

## Testing Checklist

### Tests Automatisés (~30% issues)

| Outil | Type | Gratuit | Intégration |
|-------|------|---------|-------------|
| axe DevTools | Extension | Oui | Chrome, Firefox |
| WAVE | Extension/Web | Oui | Chrome, Firefox |
| Lighthouse | Built-in | Oui | Chrome DevTools |
| Pa11y | CLI | Oui | Node.js, CI/CD |
| axe-core | Library | Oui | Jest, Cypress |

### Tests Manuels (~70% issues)

**Checklist essentielle :**

- [ ] **Keyboard** : Tab through entire page, verify all interactive elements reachable
- [ ] **Focus visible** : Focus indicator visible on all elements
- [ ] **Focus order** : Logical top-to-bottom, left-to-right
- [ ] **Screen reader** : Test with NVDA/VoiceOver, content announced correctly
- [ ] **Headings** : Logical hierarchy (H1→H2→H3), no skips
- [ ] **Alt text** : All images have appropriate alt (or alt="" for decorative)
- [ ] **Links** : Descriptive text, not "click here"
- [ ] **Forms** : Labels associated, errors identified, required marked
- [ ] **Color contrast** : 4.5:1 text, 3:1 UI components
- [ ] **Color alone** : Information not conveyed by color alone
- [ ] **Zoom** : Content readable at 200%, no horizontal scroll at 320px
- [ ] **Motion** : Animations pausable, no flashing >3/sec

---

## Common Violations & Fixes

### 1. Images sans Alt

**Problème :**
```html
<img src="product.jpg">
```

**Fix :**
```html
<!-- Image informative -->
<img src="product.jpg" alt="iPhone 15 Pro, couleur noir titane">

<!-- Image décorative -->
<img src="decoration.jpg" alt="" role="presentation">
```

### 2. Contraste Insuffisant

**Problème :**
```css
color: #999; background: #fff; /* Ratio 2.85:1 */
```

**Fix :**
```css
color: #595959; background: #fff; /* Ratio 7:1 */
```

### 3. Focus Supprimé

**Problème :**
```css
:focus { outline: none; }
```

**Fix :**
```css
:focus-visible {
  outline: 2px solid #005fcc;
  outline-offset: 2px;
}
```

### 4. Labels Manquants

**Problème :**
```html
<input type="email" placeholder="Email">
```

**Fix :**
```html
<label for="email">Email</label>
<input type="email" id="email" placeholder="exemple@domaine.com">
```

### 5. Liens Non Descriptifs

**Problème :**
```html
<a href="/products">Cliquez ici</a>
```

**Fix :**
```html
<a href="/products">Voir tous les produits</a>
```

### 6. Missing Language

**Problème :**
```html
<html>
```

**Fix :**
```html
<html lang="fr">
```

### 7. Heading Hierarchy Broken

**Problème :**
```html
<h1>Title</h1>
<h3>Section</h3> <!-- H2 manquant -->
```

**Fix :**
```html
<h1>Title</h1>
<h2>Section</h2>
```

### 8. Keyboard Trap

**Problème :**
```javascript
// Modal sans gestion Escape
```

**Fix :**
```javascript
modal.addEventListener('keydown', (e) => {
  if (e.key === 'Escape') closeModal();
});
```

---

## Resources

### Official Standards
- [WCAG 2.1](https://www.w3.org/TR/WCAG21/)
- [WCAG 2.2](https://www.w3.org/TR/WCAG22/)
- [WAI-ARIA 1.2](https://www.w3.org/TR/wai-aria-1.2/)
- [ARIA Authoring Practices](https://www.w3.org/WAI/ARIA/apg/)

### Regulatory
- [RGAA 4.1 (France)](https://accessibilite.numerique.gouv.fr/)
- [Section 508 (US)](https://www.section508.gov/)
- [EN 301 549 (EU)](https://www.etsi.org/deliver/etsi_en/301500_301599/301549/)

### Learning
- [WebAIM](https://webaim.org/)
- [Deque University](https://dequeuniversity.com/)
- [A11y Project](https://www.a11yproject.com/)
- [MDN Accessibility](https://developer.mozilla.org/en-US/docs/Web/Accessibility)

### Testing Tools
- [axe DevTools](https://www.deque.com/axe/devtools/)
- [WAVE](https://wave.webaim.org/)
- [Colour Contrast Analyser](https://www.tpgi.com/color-contrast-checker/)
- [NVDA Screen Reader](https://www.nvaccess.org/)

---

## Version

- **Framework** : WCAG 2.1 (2018) + WCAG 2.2 (2023)
- **Document version** : 1.0
- **Dernière mise à jour** : 2026-01
- **Source** : W3C Web Accessibility Initiative (WAI)

---

**Note :** Ce document est une référence. Pour l'audit complet, utilisez l'agent `accessibility-wcag-checker.md`.
