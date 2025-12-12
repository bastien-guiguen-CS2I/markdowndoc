---
icon: simple/markdown
title: Markdown et Zensical — Guide complet
---

# Markdown avec Zensical (guide détaillé)

Ce guide reprend les éléments de base du Markdown et ajoute des conseils et exemples spécifiques à Zensical (admonitions, blocs de code annotés, footnotes, etc.). Pour plus de détails techniques, voir la documentation officielle: https://zensical.org/docs/.

## Sommaire
- [En-têtes](#en-tetes)
- [Mise en forme du texte](#mise-en-forme-du-texte)
- [Liens et images](#liens-et-images)
- [Listes](#listes)
- [Citations (blockquotes)](#citations-blockquotes)
- [Blocs de code](#blocs-de-code)
- [Tables](#tables)
- [Règles horizontales](#regles-horizontales)
- [Listes de tâches](#listes-de-taches)
- [Notes de bas de page (footnotes)](#notes-de-bas-de-page-footnotes)
- [Admonitions & détails](#admonitions--details)
- [Frontmatter et métadonnées Zensical](#frontmatter-et-metadonnees-zensical)
- [Bonnes pratiques](#bonnes-pratiques)

---

## En-têtes
Les en-têtes structurent votre document et sont importants pour l'accessibilité et le référencement. N'utilisez qu'un seul `#` pour le titre principal de la page (Zensical en fait souvent le titre affiché dans la navigation).

Exemples:
```
# Titre principal (H1)
## Section (H2)
### Sous-section (H3)
```

## Mise en forme du texte
Les balises usuelles sont supportées: gras, italique, barré et code inline. Zensical permet aussi des formats supplémentaires (surbrillance, indices, exposants) et met en valeur la lisibilité.

Exemples:
```
**texte en gras**
*texte en italique*
***gras et italique***
~~barré~~
`inline code`
H~2~O  (indice)
A^T^A  (exposant)
```

## Liens et images
Liens externes et internes: préférez des liens relatifs pour la navigation interne (`[nom](autre-page.md)`). Pour les images, fournissez toujours un texte alternatif utile (accessibilité).

Exemples:
```
[Lien externe](https://example.com)
[Lien interne vers la doc](index.md)
![Texte alternatif descriptif](assets/images/example.png "Titre de l'image")
```

Conseil Zensical: conservez vos images dans `docs/assets/images` (ou `docs/images`) et référencez-les par chemin relatif pour que le builder les copie correctement.

## Listes
Listes non ordonnées, ordonnées et imbriquées sont prises en charge. Utilisez l'indentation par deux espaces pour imbriquer proprement.

Exemple:
```
- Item 1
- Item 2
  - Item imbriqué

1. Premier
2. Deuxième
3. Troisième
```

## Citations (blockquotes)
Utilisez `>` pour citer du texte ou créer des encadrés de citation.

```
> Ceci est une citation
> sur plusieurs lignes
```

## Blocs de code
Zensical prend en charge les blocs de code avec langage, titres, lignes surlignées et boutons (copier/selection) si activés dans `zensical.toml` (`content.code.copy`, `content.code.select`, `content.code.annotate`).

Exemple JavaScript:
```javascript title="hello.js"
function hello() {
  console.log("Hello, world!");
}

hello();
```

Pour ajouter une annotation à une ligne (UI fournie par Zensical) ou surligner des lignes, consultez la doc: https://zensical.org/docs/authoring/code-blocks/

## Tables
Les tables Markdown standard (pipes) sont supportées. Évitez les tables trop larges sur mobile.

Exemple rendu:

| En-tête 1 | En-tête 2 | En-tête 3 |
|----------:|:---------:|:---------|
| Alignée à droite | Centrée | Gauche |
| Donnée | Donnée | Donnée |

Syntaxe:
```markdown
| En-tête 1 | En-tête 2 | En-tête 3 |
|----------:|:---------:|:---------|
| Alignée à droite | Centrée | Gauche |
| Donnée | Donnée | Donnée |
```

## Règles horizontales
Séparateurs visuels simples:
```
---
***
___
```

## Listes de tâches
Syntaxe pratique pour suivre des actions dans la documentation:
```
- [x] Tâche faite
- [ ] Tâche à faire
```

## Notes de bas de page (footnotes)
Zensical peut rendre les footnotes en tooltips si `content.footnote.tooltips` est activé. Utilisez la syntaxe standard Markdown:

```
Voici une phrase avec une note.[^1]

[^1]: Contenu de la note.
```

## Admonitions & détails
Zensical propose une syntaxe simple pour les admonitions (notes, warnings, tips) et les blocs repliables.

Exemples:

```
!!! note

    Ceci est une note d'information.

!!! warning "Attention"

    Ceci est un avertissement.

??? info "Cliquez pour ouvrir"

    Contenu repliable, pratique pour les FAQ.
```

## Frontmatter et métadonnées Zensical
Le frontmatter en YAML en tête de fichier vous permet de configurer l'icône, le titre, la langue, un résumé, des tags et plus encore. Exemple minimal:

```
---
icon: simple/markdown
title: "Markdown et Zensical — Guide"
summary: "Référence rapide et conseils pour écrire du markdown avec Zensical."
---
```

Certaines options (icônes, palette, fonctionnalités) sont contrôlées globalement dans `zensical.toml` (par ex. activer `content.code.copy` pour un bouton copier dans les blocs de code).

## Bonnes pratiques
- Écrivez des titres courts et descriptifs.
- Toujours fournir un `alt` pour les images.
- Préférez les liens relatifs pour la doc interne.
- Divisez une page longue en sections et pages lorsque c'est pertinent.

---

Si tu veux, je peux: ajouter des exemples supplémentaires (admonitions, tableaux complexes), traduire tout en français ou générer une page d'exemples séparée `docs/markdown-examples.md`. Veux-tu que je crée une page d'exemples ?