# Audit SEO Local — Chez Hélène | Saint-Ouen (93400)

**Date :** 8 mars 2026  
**Objectif :** Classement #1 pour « esthéticienne Saint-Ouen »

---

## 1. Local Schema Markup (JSON-LD)

### ✅ Points positifs
- `BeautySalon` présent sur `index.html`
- Téléphone `+33620355745` correctement renseigné
- Coordonnées géo (latitude/longitude)
- `openingHoursSpecification` présent
- Pages services : schéma `Service` avec `provider` de type `BeautySalon`

### ❌ Problèmes à corriger

| Problème | Fichier | Solution |
|----------|---------|----------|
| Adresse incomplète | `index.html`, `contact.html` | Ajouter `streetAddress`, `postalCode` (93400), `addressRegion` (Île-de-France) |
| `openingHoursSpecification` incorrect | `index.html` | Utiliser un **array** d'objets (un par jour) au lieu d'un objet unique |
| `HealthAndBeautyBusiness` | — | Compléter avec le type `HealthAndBeautyBusiness` en addition pour le Knowledge Panel |
| Code postal 93400 absent | Toutes les pages | Ajouter dans `PostalAddress` et dans le contenu visible |

### Correction recommandée pour `index.html`

```json
{
  "@context": "https://schema.org",
  "@type": ["BeautySalon", "HealthAndBeautyBusiness"],
  "name": "Chez Hélène - Institut de Beauté",
  "description": "Esthéticienne diplômée à Saint-Ouen (93400). Institut de beauté privé : soins visage, épilation définitive, cils YUMI, détatouage.",
  "url": "https://www.helenerouas.com",
  "telephone": "+33620355745",
  "email": "contact@helenerouas.com",
  "address": {
    "@type": "PostalAddress",
    "streetAddress": "[Rue et numéro — ou « Sur rendez-vous » si cabinet privé]",
    "addressLocality": "Saint-Ouen",
    "postalCode": "93400",
    "addressRegion": "Île-de-France",
    "addressCountry": "FR"
  },
  "geo": {
    "@type": "GeoCoordinates",
    "latitude": 48.9119,
    "longitude": 2.3342
  },
  "openingHoursSpecification": [
    {"@type": "OpeningHoursSpecification", "dayOfWeek": "Monday", "opens": "09:00", "closes": "19:00"},
    {"@type": "OpeningHoursSpecification", "dayOfWeek": "Tuesday", "opens": "09:00", "closes": "19:00"},
    {"@type": "OpeningHoursSpecification", "dayOfWeek": "Wednesday", "opens": "09:00", "closes": "19:00"},
    {"@type": "OpeningHoursSpecification", "dayOfWeek": "Thursday", "opens": "09:00", "closes": "19:00"},
    {"@type": "OpeningHoursSpecification", "dayOfWeek": "Friday", "opens": "09:00", "closes": "19:00"},
    {"@type": "OpeningHoursSpecification", "dayOfWeek": "Saturday", "opens": "09:00", "closes": "19:00"}
  ],
  "priceRange": "€€",
  "image": "https://www.helenerouas.com/assets/images/hero.jpg"
}
```

---

## 2. Sémantique HTML (H1–H3) & Mots-clés locaux

### ❌ Problèmes identifiés

| Page | H1 actuel | H1 recommandé | Mots-clés manquants |
|------|-----------|---------------|----------------------|
| **index.html** | « Chez Hélène » | « Esthéticienne Saint-Ouen — Institut Chez Hélène » | esthéticienne, Saint-Ouen |
| **soins-visage.html** | « Soins du Visage » | « Soin du visage Saint-Ouen — Institut Chez Hélène » | Soin du visage Saint-Ouen |
| **cils.html** | « Regard Signature : L'Excellence YUMI » | « Cils & Sourcils YUMI à Saint-Ouen — Chez Hélène » | Saint-Ouen |
| **contact.html** | « Infos & Contact » | « Contact esthéticienne Saint-Ouen (93400) » | esthéticienne, 93400 |
| **epilation-definitive.html** | (vérifier) | « Épilation définitive Saint-Ouen — Institut Chez Hélène » | Saint-Ouen |

### Recommandations

1. **Index :** Un seul H1 par page. L’ajouter/ajuster pour inclure « Esthéticienne Saint-Ouen ».
2. **Hiérarchie :** H1 → H2 → H3 respectée sur toutes les pages.
3. **Mots-clés :** Intégrer « esthéticienne Saint-Ouen », « soin du visage Saint-Ouen », « 93400 » dans au moins un H2 par page service.

---

## 3. Meta Tags (Title & Description)

### Score actuel

| Page | Title | Description | Remarques |
|------|-------|-------------|-----------|
| index | 47 car. | 155 car. | Bon. Manque « esthéticienne » |
| contact | 53 car. | 145 car. | Bon |
| soins-visage | 52 car. | 145 car. | Bon |

### Modifications recommandées pour un meilleur CTR

**index.html**

```html
<title>Esthéticienne Saint-Ouen 93400 — Institut Chez Hélène | Soins Visage & Corps</title>
<meta name="description" content="Esthéticienne diplômée à Saint-Ouen (93). Soins visage, épilation définitive, cils YUMI, Hollywood peel. Cabinet privé — RDV : 06 20 35 57 45. Plus de 15 ans d'expérience.">
```

- Action : « Prenez RDV », numéro de téléphone
- Local : Saint-Ouen, 93
- Confiance : 15 ans d’expérience

**soins-visage.html**

```html
<title>Soin du Visage Saint-Ouen — Microneedling, Bio & Radiofréquence | Chez Hélène</title>
<meta name="description" content="Soins du visage à Saint-Ouen : microneedling, soins bio Phyt's, radiofréquence. Esthéticienne diplômée — dès 69€. Réservez votre consultation.">
```

---

## 4. Optimisation des images

### État actuel

- **Aucune balise `<img>`** : uniquement des `div` avec classe `placeholder-img` et du texte.
- Aucun attribut `alt` exploitable pour le SEO.

### Recommandations pour les futures images

1. **Alt descriptifs et localisés :**
   - `alt="Soins du visage et microneedling à Saint-Ouen chez l'esthéticienne Hélène"`
   - `alt="Institut de beauté Chez Hélène à Saint-Ouen (93400)"`
   - `alt="Épilation laser définitive - Cabinet esthétique Saint-Ouen"`
2. **Compression :** WebP, max 80 % qualité pour les visuels.
3. **Dimensions :** Largeur max 1200–1600 px pour les photos de service.
4. **Lazy loading :** `loading="lazy"` sur les images hors viewport.
5. **Noms de fichiers :** ex. `soins-visage-saint-ouen.jpg`, `epilation-definitive-helene.jpg`.

---

## 5. NAP (Name, Address, Phone)

### Incohérences

| Élément | Index | Contact | Schema | Recommandation |
|---------|-------|---------|--------|----------------|
| **Nom** | « Chez Hélène » | « Chez Hélène » | « Chez Hélène - Institut Privé » | Harmoniser : « Chez Hélène - Institut de Beauté » |
| **Adresse** | « Saint-Ouen » | « Cabinet privé à Saint-Ouen » | `addressLocality: Saint-Ouen` | Ajouter **93400** partout. Si adresse complète impossible, indiquer « Saint-Ouen (93400) ». |
| **Téléphone** | 06 20 35 57 45 | 06 20 35 57 45 | +33620355745 | ✅ Cohérent |

### Format recommandé pour Google

- **Nom :** Chez Hélène — Institut de Beauté
- **Adresse :** Saint-Ouen 93400 (ou adresse complète si possible)
- **Téléphone :** +33 6 20 35 57 45 (format international) et 06 20 35 57 45 (affichage FR)

Important : le code postal **93400** doit apparaître en texte visible (footer, contact, schema) pour renforcer le signal local.

---

## 6. Mobile & Core Web Vitals

### Points positifs

- `viewport` meta présent
- Scroll listeners en `passive: true`
- `IntersectionObserver` pour les animations
- Media queries responsive (Tailwind)
- `prefers-reduced-motion` pris en compte

### Points d’attention

| Problème | Impact | Correction |
|----------|--------|------------|
| Tailwind via CDN | FCP, LCP | Précompiler Tailwind et servir un fichier statique minifié |
| `@import` Google Fonts dans CSS | Render-blocking | Utiliser `<link rel="preconnect">` + chargement asynchrone des polices |
| Bouton « Voir comparaison polices » (`font-compare.html`) | Bruit, liens inutiles | Retirer en production |
| Aucun `preload` | LCP | Preload de la font critique et du hero si image réelle |

### Exemple de corrections

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
```

---

## 7. Plan d’action pour « esthéticienne Saint-Ouen »

### Priorité haute

1. Inclure « **Esthéticienne Saint-Ouen** » dans le H1 de `index.html`.
2. Corriger le JSON-LD : adresse complète, 93400, `openingHoursSpecification` en array.
3. Harmoniser le NAP : toujours « Saint-Ouen (93400) » et nom unique.
4. Optimiser le meta title de la page d’accueil avec « Esthéticienne Saint-Ouen 93400 ».

### Priorité moyenne

5. Intégrer « esthéticienne » et « Saint-Ouen » dans au moins un H2 sur chaque page service.
6. Créer une section « Esthéticienne à Saint-Ouen » sur la page d’accueil.
7. Retirer le lien vers `font-compare.html` en production.
8. Optimiser le chargement des polices (preconnect + async).

### Priorité basse

9. Remplacer les placeholders par des images réelles avec alt descriptifs.
10. Mettre en place un fichier `robots.txt` si absent.
11. Vérifier l’indexation dans la Google Search Console.
12. Créer / optimiser la fiche Google Business Profile pour Saint-Ouen (93400).

---

## 8. Fichiers à modifier en priorité

1. **index.html** — Schema, H1, meta, NAP, retrait du lien font-compare
2. **contact.html** — Schema PostalAddress, H1, NAP (93400)
3. **soins-visage.html** — H1, meta title
4. **cils.html** — H1
5. **epilation-definitive.html** — H1, meta
6. **css/custom.css** — Chargement des polices
7. **Tous les footers** — Ajout systématique de « Saint-Ouen (93400) »

---

*Audit réalisé pour le référencement local de Chez Hélène, esthéticienne à Saint-Ouen (93400).*
