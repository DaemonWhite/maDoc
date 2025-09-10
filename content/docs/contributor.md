---
weight: 0
title: "Contributor"
description: ""
icon: "article"
date: "2025-09-10T12:09:58+02:00"
lastmod: "2025-09-10T12:09:58+02:00"
draft: true
toc: true
---

## Bienvenue jeune contrinuteur

Passon pas par quatres chemin ton temps est précieurs.

Avant toute choes il faut que vous installiez les prérequis

### Prérequis

- Un éditeur de texte de votre choix (VSCode, notepad)
- GIT
- HUGO

Pour l'éditeur de texte je vous laisse le choix c'est qu'une question de goût

{{< tabs tabTotal="3">}}
{{% tab tabName="Debian/Ubuntu/Mint" %}}

**Debian/Ubuntu/Mint**

```sh
sudo apt install hugo
```

{{% /tab %}}
{{% tab tabName="Arch linux" %}}

**Arch linux**

```sh
sudo pacman -S hugo
```

{{% /tab %}}
{{% tab tabName="Windows" %}}

**Windows**
Ouvrez un terminal est tapée

{{% alert="warning" context="warning" %}}

N'installée surtout pas, c'est dépendance si vous les avez installée d'une autre manière (a titre individuel)

{{% /alert %}}

```ps1
winget install Hugo.Hugo.Extended
winget install -e --id Git.Git
winget install -e --id GoLang.Go.1.18
winget install -e --id Gekorm.Dart
```

{{% /tab %}}
{{< /tabs >}}

{{% alert="warning" context="warning" %}}


N'oublier pas de configurer git pour qu'il puisse marcher avec votre compte Gitlab Documentation [ICI](https://docs.gitlab.com/user/ssh/)

{{% /alert %}}

## Créer un fork

Rendez-vous sur [gitlab](https://gitlab.siovhb.lycee-basch.fr/matheo.travers/madoc) et chercher le projet maDoc (le lien vous y améne directement)

<img src="/contributor/gitlab.png" alt="page gitlab">

En haut à droite cliquez sur FORK

Vous deverez arrivée sur cette page.
A part le namespace vous n'avez rien besoin de changer
<img src="/contributor/fork_info.png" alt="page fork">

### Déployer en local

Une fois le fork créer pennsez bien à clonez le dépot sur votre machine la commande et la suivante

{{% alert="warning" context="warning" %}}

Oubliez pas de rajoutez **`--recurse-submodules`** au risque d'avoir quelque petit problème

{{% /alert %}}

Example de commande
```bash
git clone --recurse-submodules git@gitlab.siovhb.lycee-basch.fr:your.space/fork
```

une fois clonée ouvrer un terminal dans le dossier qui correspond à votre dépo et taper 

```sh
hugo server -D
```
allez à l'adresse [http://localhost:1313/](http://localhost:1313/)



## Modifier le projet BASE

Tout les contenues sont stoquer dans /content/docs/

C'est écris en markdown par défaut un petit guide si besoin [ici](https://www.markdownguide.org/getting-started/)

si vous voulez créer une nouvelle page il faut faire comme ceci

```sh
hugo new docs/paPage.md
```

Si vouslez créer plusieurs page sur un même théme il faut faire comme-suit

```sh
hugo new docs/monTheme/_index.md
hugo new docs/paPage1.md
hugo new docs/paPage2.md
```

Pour le reste vous pouvez soit regardez comment les autre on fait ou vous référer à la doc [officiel](https://lotusdocs.dev/docs/features/syntax-highlighting/)

## Proposer votre travail

Pour proposer votre travail il suffit de créer une merge request en allant sur le projet d'origine