# Poster.ai — Générateur d'affiches visuelles par IA

Application web complète en **un seul fichier HTML** — aucune installation, aucun serveur.  
Ouvrez directement dans votre navigateur ou hébergez sur GitHub Pages.

## 🚀 Démo rapide

1. Téléchargez `poster-ai.html`
2. Ouvrez-le dans Chrome ou Firefox
3. Entrez votre clé API Anthropic
4. Générez votre première affiche

## ✨ Fonctionnalités

| Fonction | Détail |
|---|---|
| **8 styles visuels** | Moderne, Minimaliste, Futuriste, Vintage, Luxe, Événementiel, Corporate, Cyberpunk |
| **3 formats** | A4 Portrait, A4 Paysage, Bannière Web (1000×400) |
| **Import PDF** | Drag & drop — extraction côté client via PDF.js |
| **Génération IA** | Titre, sous-titre, corps, tags, pied de page via Claude |
| **Variantes** | Régénère un angle narratif différent en un clic |
| **Éditeur live** | Modifiez le contenu, le canvas se met à jour instantanément |
| **Export PNG** | Téléchargement haute résolution |

## 🔑 Clé API Anthropic

1. Créez un compte sur [console.anthropic.com](https://console.anthropic.com)
2. Générez une clé API (`sk-ant-…`)
3. Collez-la dans le champ en haut du panneau gauche
4. Elle est sauvegardée dans votre `localStorage` (reste dans votre navigateur)

## 🌐 Héberger sur GitHub Pages

1. Créez un nouveau dépôt GitHub
2. Uploadez `poster-ai.html` **et renommez-le `index.html`**
3. Allez dans `Settings → Pages → Source: main branch / root`
4. Votre app sera disponible sur `https://votre-pseudo.github.io/votre-repo`

## 🏗 Architecture

Tout est contenu dans un seul fichier HTML :

```
poster-ai.html
├── <style>          — CSS complet (dark theme, responsive)
├── HTML             — Structure UI (panneau gauche + canvas droit)
└── <script>
    ├── CONFIG       — Formats (A4, bannière) + palettes de styles
    ├── STATE        — État global de l'application
    ├── INIT         — Construction dynamique des boutons
    ├── PDF          — Extraction via PDF.js (client-side, pas de serveur)
    ├── AI           — Appels Anthropic API → contenu structuré JSON
    └── CANVAS       — Moteur de rendu HTML5 Canvas (background, typo, décor)
```

### Moteur Canvas

Le rendu est entièrement fait via `CanvasRenderingContext2D` :
- **Background** : dégradé linéaire paramétrique
- **Décor** : lignes, grille, points, ornements, burst selon le style
- **Typographie** : Playfair Display (titres) + DM Sans (corps)
- **Layout** : placement automatique adapté à chaque format
- **Mise à l'échelle** : aperçu proportionnel dans l'UI, export full resolution

## 📦 Technologies

- **HTML5 Canvas API** — rendu vectoriel et typographique
- **PDF.js 3.11** (CDN Cloudflare) — extraction PDF côté client
- **Anthropic Claude API** — génération de contenu structuré
- **Google Fonts** — Playfair Display, DM Sans, Space Mono
- Zéro dépendance npm, zéro build step

## 📝 Licence

MIT
