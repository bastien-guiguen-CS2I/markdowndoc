---
icon: lucide/link-2
title: Liens et images
---

# Liens et images

## Vue d'ensemble

Les liens et images sont essentiels pour une documentation riche et navigable. Zensical traite automatiquement:
- **Liens relatifs** : Navigation interne entre pages
- **Liens externes** : Vers des ressources externes
- **Images** : Gestion des assets avec texte alternatif
- **Lazy loading** : Optimisation des performances

## Syntaxe des liens

### 1. Lien simple

```markdown
[Texte visible](https://example.com)
```

Rendu:
> [Texte visible](https://example.com)

### 2. Lien avec titre/tooltip

```markdown
[Consulter la documentation](https://zensical.org "Cliquez ici pour plus d'info")
```

### 3. Lien interne (vers autre page)

Utilisez les chemins relatifs pour la navigation interne:

```markdown
[Voir le guide sur les en-têtes](markdown-en-tetes.md)
[Retour à l'accueil](index.md)
```

!!! warning
    Zensical transforme automatiquement les `.md` en `/` pour les URLs finales.
    `markdown-en-tetes.md` devient `markdown-en-tetes/` en production.

### 4. Lien vers une section (ancre)

Référencez une section par son en-tête:

```markdown
Voir la [section sur les exposants](#syntaxe-des-images)
```

## Syntaxe des images

### 1. Image simple

```markdown
![Texte alternatif](images/screenshot.png)
```

### 2. Image avec titre

```markdown
![Logo Zensical](images/logo.png "Cliquez pour agrandir")
```

### 3. Image en lien (cliquable)

```markdown
[![Logo](images/logo.png "Cliquez")](https://zensical.org)
```

## Bonnes pratiques pour les images

### 1. Toujours fournir un texte alternatif

```markdown
✅ BON
![Diagramme d'architecture montrant les composants du système](images/arch.png)

❌ MAUVAIS
![image](images/arch.png)
![screenshot](images/arch.png)
```

Le texte alternatif:
- Aide les malvoyants (lecteurs d'écran)
- S'affiche si l'image ne charge pas
- Améliore le SEO
- Rend votre doc plus accessible

### 2. Organiser les assets

Structure recommandée:
```
docs/
├── index.md
├── markdown-en-tetes.md
├── assets/
│   ├── images/
│   │   ├── logo.png
│   │   ├── diagram-arch.png
│   │   └── screenshot-ui.png
│   └── files/
│       └── template.zip
```

### 3. Chemins relatifs

```markdown
✅ BON (relatif)
![Logo](assets/images/logo.png)

❌ MAUVAIS (absolu, ne fonctionne pas)
![Logo](/absolute/path/logo.png)

❌ MAUVAIS (dépendant de la structure)
![Logo](../../../images/logo.png)
```

### 4. Taille et format

```markdown
✅ Pour web:
- PNG (images avec transparence)
- JPG (photos)
- WebP (moderne, meilleure compression)
- SVG (diagrammes, icônes)

❌ Évitez:
- BMP (trop volumineux)
- TIFF (format d'archivage)
```

## Diagramme: Flux de navigation interne

```mermaid
graph TD
    A["📄 Votre documentation"] --> B["🔗 Liens internes"]
    A --> C["🖼️ Images/Assets"]
    
    B -->|markdown-page.md| D["Navigation Zensical"]
    B -->|#section| E["Ancres/Fragments"]
    
    C -->|assets/images| F["Gestion d'assets"]
    C -->|texte alternatif| G["Accessibilité SEO"]
    
    D -->|transformé en URL| H["📍 /page/"]
    E -->|généré automatique| I["#section-heading"]
    F -->|chemin relatif| J["✅ Fonctionne"]
    G -->|screen reader| K["♿ Accessible"]
    
    style A fill:#E3F2FD
    style H fill:#C8E6C9
    style K fill:#C8E6C9
    style J fill:#C8E6C9
```

## Cas d'usage avancés

### 1. Galerie d'images

```markdown
## Galerie d'exemples

![Exemple 1](assets/images/ex1.png)
![Exemple 2](assets/images/ex2.png)
![Exemple 3](assets/images/ex3.png)
```

### 2. Images cliquables

```markdown
[![Voir le screencast](assets/images/thumbnail.png "Cliquez pour voir la vidéo")](https://youtube.com/...)
```

### 3. Références de liens centralisées

Au lieu de répéter les URLs, définissez-les une fois:

```markdown
Consultez la [documentation officielle][zensical-docs] et le [code source][github].

[zensical-docs]: https://zensical.org/docs/
[github]: https://github.com/zensical/zensical
```

## Tableau récapitulatif

| Élément | Syntaxe | Exemple |
|---------|---------|---------|
| Lien simple | `[texte](url)` | `[Google](https://google.com)` |
| Lien avec titre | `[texte](url "titre")` | `[Google](https://google.com "Moteur de recherche")` |
| Lien interne | `[texte](page.md)` | `[Accueil](index.md)` |
| Ancre | `[texte](#section)` | `[Voir plus](#advanced)` |
| Image | `![alt](url)` | `![Logo](logo.png)` |
| Image cliquable | `[![alt](url)](lien)` | `[![Logo](logo.png)](home.md)` |
| Lien référencé | `[texte][ref]` + `[ref]: url` | Voir exemple ci-dessus |

## Performance: Optimisation des images

Zensical supporte le **lazy loading** automatiquement. Les images se chargent seulement quand elles entrent dans le viewport (visible sur l'écran).

```mermaid
flowchart LR
    A["Page chargée"] --> B["Images en viewport"]
    A --> C["Images hors viewport"]
    
    B --> D["Chargement immédiat"]
    C --> E["Chargement lazy"]
    
    E --> F["Au scroll: chargement"]
    
    style D fill:#C8E6C9
    style F fill:#FFF9C4
```

## Exemple complet

```markdown
---
icon: lucide/image
title: Guide des images
---

# Guide des images

![Bannière du site](assets/images/banner.png)

## Types d'images supportées

Voir plus de détails: [formats d'image recommandés](markdown-liens-images.md#performance-optimisation-des-images)

## Galerie

![Exemple 1 - Architecture simple](assets/images/arch-simple.png "Cliquez pour zoomer")
![Exemple 2 - Architecture distribuée](assets/images/arch-dist.png)

[Voir plus d'exemples](assets/examples.md)
```

