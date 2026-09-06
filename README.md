# bm-developpement

Feuille de styles personnalisée pour le site de **BMDéveloppement**, promoteur
immobilier de la région Auvergne-Rhône-Alpes (siège à Dardilly, 69). Le fichier
était destiné au panneau « CSS personnalisé » de Squarespace : il surchargeait
le thème pour installer la typographie Gotham, une grille de galerie en mosaïque
pour les réalisations, un bouton mis en avant et des champs de formulaire sur
mesure.

**Année de réalisation / livraison : d'après les ressources liées (polices et
images hébergées sur le CDN Squarespace, horodatées fin novembre 2016) : 2016.**

> **Cette feuille de styles correspond à une version antérieure du site, aujourd'hui
> remplacée.**

## Contenu

- `styles.less` — l'intégralité du CSS personnalisé injecté dans l'ancien site
  Squarespace. Un seul fichier, 444 lignes.

Détail des blocs de `styles.less` :

- `@font-face` — déclaration de la police `Gotham` (Book, poids 400 ; Bold,
  poids 700), fichiers `.otf` hébergés sur `static1.squarespace.com`.
- `#siteWrapper, p, a, h1…h3` — application de `Gotham` à tout le site (`!important`).
- `#sidecarNav`, `.mobile-nav-open #titres` — ajustements de la navigation
  latérale et du glissement du contenu à l'ouverture du menu mobile.
- `#mainNavigation .collection` — espacement, transition d'opacité au survol et
  soulignement de l'entrée active dans la navigation principale.
- `#page`, `#titres`, `.transparent-header … .banner-thumbnail-wrapper` — mise en
  page de l'en-tête et des titres de bannière.
- `/* Bouton Demoreel */` — style du dernier `.desc-wrapper` (bouton centré,
  bordure au survol). Le libellé « Demoreel » provient du gabarit Squarespace
  d'origine (thème de portfolio).
- `.sqs-gallery-… thumbnails-per-row-4` et `-per-row-5` — grilles de galerie
  retravaillées en mosaïque asymétrique (règles `:nth-of-type`), avec voile
  blanc et titre de l'image révélés au survol. Réservées aux écrans ≥ 641 px.
- `.desc-wrapper … a`, `.sqs-block-button-element`, `.button.sqs-system-button` —
  boutons à bordure, texte en capitales.
- `.form-wrapper .field-list` — champs et `select` de formulaire sur fond
  transparent ; flèche du `select` remplacée par une image (`bande8.png`).
- `#footer .footer-inner` — marges, filet horizontal blanc, dimension du logo.

## Stack technique

- Site hébergé sur **Squarespace** ; ce dépôt ne contient que la surcouche CSS,
  pas le template ni le contenu.
- CSS imbriqué avec `&` et sélecteurs parent : syntaxe **LESS** de l'éditeur CSS
  personnalisé de Squarespace (compilée par la plateforme).
- Nombreux préfixes constructeur (`-webkit-`, `-moz-`, `-ms-`, `-o-`) sur les
  `transform` et `transition`.
- Cible les classes système Squarespace (`sqs-gallery-*`, `sqs-block-*`,
  `form-wrapper`, `sidecarNav`, `mainNavigation`, `transparent-header`,
  `mobile-nav-open`).
- Aucune dépendance, aucun gestionnaire de paquets, aucun bundler.

## Développement

Prérequis : un compte Squarespace disposant des droits d'édition sur le site.

Il n'y a pas de build : le contenu de `styles.less` se colle dans
**Design → CSS personnalisé** (ou `Custom CSS`) de l'administration Squarespace,
qui se charge de la compilation et de la minification.

Pour travailler le fichier hors ligne, n'importe quel éditeur suffit ; un
compilateur LESS local peut aider à repérer les erreurs de syntaxe, mais la
plateforme reste la référence.

Notes :

- Les URL de polices et d'images pointent vers le CDN
  `static1.squarespace.com/static/583411bd725e25d98aacd19f/…` et ne répondent
  plus. Pour réutiliser ce style il faut re-téléverser les fichiers sur le site
  cible et remplacer les URL.
- Les grilles de galerie personnalisées supposent des galeries configurées à 4
  ou 5 vignettes par rangée, format carré, design « grid ».

## Crédits

- **Direction artistique** — Big Company
- **Développement** — Olivier Charvoz
- **Commanditaire** — BMDéveloppement (SAS, RCS Lyon 528 355 159, Dardilly)

## Licence

Tous droits réservés.
