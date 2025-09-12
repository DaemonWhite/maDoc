---
weight: 0
title: "Contributor"
description: ""
icon: "article"
date: "2025-09-10T12:09:58+02:00"
lastmod: "2025-09-10T12:09:58+02:00"
draft: false
toc: true
---

## Bienvenue jeune contributeur

Il existe plusieurs moyen de contribuer au projet.

1. Faire des Issues(ticket) en demendant (Ajout/Correction/Modification)
2. La seconde méthode plus ardue mais plus généreuse consiste à donnez participer au code

## Méthode Issue 1

### Avant tout

Cette méthode elle est la plus feignante elle sonsite à déposée un Ticket sur la page du projet



## Méthode Contribution 2

### Prérequis

- Un éditeur de texte de votre choix (VSCode, notepad)
- GIT
- HUGO

Pour l'éditeur de texte je vous laisse le choix, c'est qu'une question de goût

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
Ouvrez un terminal est tapé

{{% alert="warning" context="warning" %}}

N'installée surtout pas, c'est dépendance si vous les avez installées d'une autre manière (à titre individuel)

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


N'oubliez pas de configurer git pour qu'il puisse marcher avec votre compte Gitlab Documentation [ICI](https://docs.gitlab.com/user/ssh/)

{{% /alert %}}

## Créer un fork

Rendez-vous sur [gitlab](https://gitlab.siovhb.lycee-basch.fr/matheo.travers/madoc) et chercher le projet maDoc (le lien vous y amène directement)

<img src="/contributor/gitlab.png" alt="page gitlab">

En haut à droite cliquez sur FORK

Vous devrez arriver sur cette page.
À part le namespace vous n'avez rien besoin de changer
<img src="/contributor/fork_info.png" alt="page fork">

### Déployer en local

Une fois le fork créé, pensez bien à cloner le dépôt sur votre machine, la commande et la suivante

{{% alert="warning" context="warning" %}}

N'oubliez pas de rajouter **`--recurse-submodules`** au risque d'avoir quelque petit problème

{{% /alert %}}

Éxample de commande
```bash
git clone --recurse-submodules git@gitlab.siovhb.lycee-basch.fr:your.space/fork
```

{{% alert="warning" context="warning" %}}

Je vous recomande de créer votre propre banche ou d'utiliser la branche dev

{{% /alert %}}

{{< tabs tabTotal="2">}}
{{% tab tabName="Créé votre branch" %}}

```sh
git branch nomDeVotreBranche
git switch nomDeVotreBranche
git push --set-upstream origin nomDeVotreBranche 
```

{{% /tab %}}
{{% tab tabName="Utilisée la brancge dev" %}}


```sh
git switch dev
```

{{% /tab %}}
{{< /tabs >}}



Une fois clonée, ouvrez un terminal dans le dossier qui correspond à votre dépôt et tapez

```sh
hugo server -D # Le tiret -D active les brouillons
```
Allez à l'adresse [http://localhost:1313/](http://localhost:1313/)



## Modifier le projet BASE

Tous les contenus sont stockés dans /content/docs/

C'est écris en markdown par défaut un petit guide si besoin [ici](https://www.markdownguide.org/getting-started/)

si vous voulez créer une nouvelle page il faut faire comme ceci

```sh
hugo new docs/paPage.md
```

Si vous voulez créer plusieurs pages sur un même thème, il faut faire comme-suit

```sh
hugo new docs/monTheme/_index.md
hugo new docs/paPage1.md
hugo new docs/paPage2.md
```

Pour le reste vous pouvez soit regardez comment les autre on fait ou vous référer à la doc [officiel](https://lotusdocs.dev/docs/features/syntax-highlighting/)

## Proposer votre travail

Pour proposer votre travail il suffit de créer une merge request en allant sur le projet d'origine

Et de le redirigé sur le dépo originel