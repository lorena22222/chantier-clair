# Chantier Clair

Site vitrine statique — plomberie & électricité, Paris & proche banlieue.
Paiement sécurisé, artisans vérifiés (SIRET, Kbis, assurance décennale).

## Structure

```
chantier-clair/
├── index.html      # page unique, toutes les sections (hero, illustration, histoire,
│                    # comment ça marche, confiance, profils artisans, zone Paris, CTA)
├── css/
│   └── style.css    # feuille de style (identique à la maquette d'origine)
├── favicon.svg       # icône d'onglet (logo Chantier Clair)
├── package.json
└── README.md
```

Aucun build : c'est du HTML/CSS/JS statique. Chargés depuis des CDN publics :
les polices Bricolage Grotesque, Space Grotesk et Source Serif 4 (Google
Fonts), et [Leaflet](https://leafletjs.com/) + les tuiles OpenStreetMap pour
la carte interactive de la zone couverte (aucune clé API requise).

## Aperçu en local

Avec Node.js installé :

```bash
npx serve . -l 3000
```

puis ouvrir http://localhost:3000

Ou plus simplement, sans rien installer, ouvrir directement `index.html`
dans un navigateur.

## Mise en ligne

Le dossier est prêt à être déployé tel quel sur n'importe quel hébergeur
statique, sans configuration :

- **Netlify / Vercel** : glisser-déposer le dossier, ou connecter le dépôt Git
- **GitHub Pages** : pousser le dossier sur une branche et l'activer dans
  Settings → Pages
- **Cloudflare Pages, Firebase Hosting, OVH, o2switch…** : uploader le
  contenu du dossier à la racine du site

## Personnalisation

Toutes les couleurs et variables de design sont centralisées en haut de
`css/style.css` :

```css
:root {
  --paper: #F4F0E6;   /* fond crème */
  --ink:   #14203D;   /* bleu encre */
  --gold:  #C68A2E;   /* doré */
  ...
}
```

Les liens `#` (nav, boutons "Trouver un artisan", etc.) sont à connecter
aux vraies pages/actions (formulaire, prise de contact, back-office) au
fur et à mesure du développement du produit.

Les photos des artisans (Karim B., Nadia F., Julien T.) utilisent pour
l'instant des portraits de démonstration (`randomuser.me/api/portraits`),
le temps d'avoir de vraies photos des artisans partenaires — il suffit de
remplacer les URLs `src="https://randomuser.me/..."` dans `index.html`
par les vraies photos une fois disponibles.
