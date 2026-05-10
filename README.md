# Pristine Patagonia — Site Web

Tour opérateur exclusif en Patagonie chilienne.

## Stack
- HTML / CSS / JS vanilla (multipage)
- Decap CMS pour la gestion du contenu
- GitHub → Vercel (auto-deploy)
- 4 langues : FR / EN / ES / PT

## Structure
```
/
├── index.html              Accueil
├── programmes.html         Programmes
├── contact.html            Contact
├── admin/
│   ├── index.html          Interface Decap CMS
│   └── config.yml          Configuration CMS
├── content/
│   ├── programmes/         Fichiers .md des programmes
│   └── settings/           Paramètres du site
└── assets/
    ├── css/style.css
    ├── js/
    │   ├── i18n.js         Système de traduction
    │   ├── main.js         Navigation, animations
    │   └── programmes.js   Données fallback
    └── images/
        ├── logo.png        Logo principal
        └── programmes/     Photos des programmes
```

## Ajouter des photos

### Hero (page d'accueil)
Dans `index.html`, décommenter dans `.hero-bg` :
```html
<img src="assets/images/hero.jpg" alt="Patagonia" />
```

### Section intro
Dans `index.html`, remplacer le placeholder par :
```html
<img src="assets/images/intro.jpg" alt="Patagonia" />
```

### Photos des programmes
Déposer dans `assets/images/programmes/` avec le nom correspondant au slug :
- `parc-patagonia.jpg`
- `fjords-aysen.jpg`
- `carretera-austral.jpg`
- `lago-general-carrera.jpg`

## Configuration Decap CMS (admin)

### 1. Créer une GitHub OAuth App
Aller sur https://github.com/settings/developers → OAuth Apps → New OAuth App
- Application name: Pristine Patagonia CMS
- Homepage URL: https://pristinepatagonia.cl
- Callback URL: https://pristinepatagonia.cl/admin/

### 2. Mettre à jour admin/config.yml
Remplacer `YOUR_GITHUB_OAUTH_CLIENT_ID` par le Client ID obtenu.

### 3. Accéder au CMS
Une fois déployé : https://pristinepatagonia.cl/admin/

## Développement local
```bash
python3 -m http.server 8080
# Ouvrir http://localhost:8080
```

## Déploiement
Push sur `main` → Vercel déploie automatiquement.
