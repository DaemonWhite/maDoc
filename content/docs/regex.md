---
weight: 999
title: "Regex"
description: ""
icon: "article"
date: "2025-09-23T08:19:14+02:00"
lastmod: "2025-09-23T08:19:14+02:00"
draft: false
toc: true
---


## Les options
### Selecteur OU

{{< table >}}
| Symbole | example | definition |
|---------|---------|----------- |
| **`\|`**  |   **`x\|y`** | Choisie entre X ou Y |
{{< /table >}}

### Selecteur Multible

{{< table >}}
| Symbole | example | definition |
|---------|---------|----------- |
| **`[abc]`**  | **`[aze]`**     | choisie parmi les lettres entre crochet
| **`[a-z]`**  | **`[a-Z]`**     | Selectionne tout les caractéres ASCII entre éléments 'A' et 'B'
| **`[^0-9]`** | **`[^0-2]`**     | Selectionne tout les caractères que ne ce trouve pas entre éléments 'A' et 'B'
|  .      |   .        | Carctéres quelconques
{{< /table >}}

### Echapement

{{< table >}}
| Symbole | example | definition |
|---------|---------|----------- |
| **`\`**   | **`\\`**     | Echape un charactères
{{< /table >}}

{{% alert icon="" context="warning" %}}

**Attention !** 

l'utilisation des **`\`** fait qu'on dois changer les démarqueurs des regex  
{{% /alert %}}

### Quantificateurs

{{< table >}}
| Symbole | example | definition |
|---------|---------|----------- |
| **`*`**   | **`a*`**     | Selectione **zero** ou **plusieurs** éléments **X** |
| **`+`**   | **`a+`**    | Selectione **un** ou **plusieurs** éléments **X** |
| **`?`**   | **`a?`**     | Selectione **zero** ou **un** éléments **X** |
| **`{n}`** |     **`a{5}`**    | Selectione **n** éléments **X** |
| **`{n,}`**  |   **`a{3,}`**    | Selectione minimum **n** éléments **X** |
| **`{n,m}`**   | **`a{3,7}`**     | Selectione minimum **n** à max **m** éléments **X** |


{{< /table >}}

### Groupement

{{< table >}}
| Symbole | example | definition |
|---------|---------|----------- |
| **`()`**     | **`(a\|x){5}`**     | Regroupe des conditions dans un même bloque
{{< /table >}}

{{% alert icon="" context="info" %}}

**Note !**

Les condition mis derrières un groupe s'applique sur toute la contion example ici `(a\|x){5}` veut dire 5 caractère `a` ou `x`

{{% /alert %}}