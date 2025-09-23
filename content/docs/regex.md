---
weight: 999
title: "Regex"
description: "Les regex alias expression régulière, permettent de faire des recherches complexes au sein d'un texte"
icon: "article"
date: "2025-09-23T08:19:14+02:00"
lastmod: "2025-09-23T08:19:14+02:00"
draft: false
toc: true
---

## Définition

Les regex sont un ensemble de règles qui permet de rechercher des mots phrases dans un texte.

Les regex sont utilisés un peu partout :
- En informatique (Filtrer/tester/rechercher)
- En documentation (recherche)


## Les options
### Sélecteur OU

{{< table "table-responsive table-striped-columns" >}}
| Symbole | exemple | définition |
|---------|---------|----------- |
| **`\|`**  |   **`x\|y`** | Choisie entre X ou Y |
{{< /table >}}

### Sélecteur Multiple

{{< table "table-responsive table-striped-columns" >}}
| Symbole | exemple | définition |
|---------|---------|----------- |
| **`[abc]`**  | **`[aze]`**     | choisie parmi les lettres entre crochet
| **`[a-z]`**  | **`[a-Z]`**     | Sélections tous les caractères ASCII entre éléments 'A' et 'B'
| **`[^0-9]`** | **`[^0-2]`**    | Sélections tous les caractères que ne se trouve pas entre éléments 'A' et 'B'
|  **`.`**     |   **`.`**       | caractères quelconques
{{< /table >}}

### Échappement

{{< table "table-responsive table-striped-columns" >}}
| Symbole | exemple | définition |
|---------|---------|----------- |
| **`\`**   | **`\\`**     | Échappe un caractère
{{< /table >}}

{{% alert icon="" context="warning" %}}

**Attention !** 

l'utilisation des **`\`** fait qu'on doit changer les démarqueurs des regex  
{{% /alert %}}

### Quantificateurs

{{< table "table-responsive table-striped-columns" >}}
| Symbole | exemple | définition |
|---------|---------|----------- |
| **`*`**   | **`a*`**     | Sélections **zero** ou **plusieurs** éléments **X** |
| **`+`**   | **`a+`**    | Sélections **un** ou **plusieurs** éléments **X** |
| **`?`**   | **`a?`**     | Sélections **zero** ou **un** éléments **X** |
| **`{n}`** |     **`a{5}`**    | Sélections **n** éléments **X** |
| **`{n,}`**  |   **`a{3,}`**    | Sélections minimum **n** éléments **X** |
| **`{n,m}`**   | **`a{3,7}`**     | Sélections minimum **n** à max **m** éléments **X** |


{{< /table >}}

### Groupement

{{< table "table-responsive table-striped-columns" >}}
| Symbole | exemple | définition |
|---------|---------|----------- |
| **`()`**     | **`(a\|x){5}`**     | Regroupe des conditions dans un même bloque  |
{{< /table >}}

{{% alert icon="" context="info" %}}

**Note !**

Les conditions mis derrières un groupe s'appliquent sur toute la condition exemple ici `(a\|x){5}` veulent dire 5 caractères `a` ou `x`

{{% /alert %}}

### Condition

{{< table  "table-responsive table-striped-columns" >}}
| Symbole | exemple | définition |
|---------|---------|----------- |
| **`^`**     | **`^a`**     | Doit commencer par '`X`' élément |
| **`$`**     | **`a$`**     | Doit finir par '`X`' élément |

{{< /table >}}

### Abréviation

{{< table "table-responsive table-striped-columns" >}}
| Symbole | exemple | définition |
|---------|---------|----------- |
| **`\b`**     | **`\b`**     | Séparateur de mots : espace, ponctuation |
| **`\d`**     | **`\d`**     | équivalent à [0-9] |
| **`\D`**     | **`\D`**     | équivalent à [^0-9] |
| **`\s`**     | **`\s`**     | Caractère d'espacement (espace, tabulation, saut de page, ...) équivalent à [ \f\n\r\t\v] |
| **`\S`**     | **`\S`**     | Un seul caractère sauf un espacement |
| **`\w`**     | **`\w`**     | équivalent à [A-Za-z0-9_] |
| **`\W`**     | **`\W`**     | équivalent à [^A-Za-z0-9_] |

{{< /table >}}

## Outil

[regexone.com](https://regexone.com/) outil pour tester vos règles