---
weight: 999
title: "SSH"
description: "Ce connecter avec git en SSH avec GitHub/GitLab"
icon: "publish"
date: "2025-09-23T10:48:38+02:00"
lastmod: "2025-09-23T10:48:38+02:00"
draft: false
toc: true
---

## Contexte

SSH est un outil qui permet de se connecter à un shell de manières sécurisé à distance. 
Mais il peut aussi êtres utilisés pour transférer des données.

Par défaut le système GIT utilise le protocole `SSH` que `HTTP`.

Pour pouvoir utiliser `SSH` il faut créer notre clef privée et publique


{{% alert icon="" context="warning" %}}

**Prérequis !**

Il vous faut un système idéalement à jours Linux ou Mac.

Pour Windows il vous faut au minimum `windows 10 22h2` ou `windows 11 22h2` (Note les entreprises peuvent désactiver les outils SSH)
Pour les systèmes Windows antérieur, vous pouvez utiliser `GIT Bash` ou `MSYS2`

{{% /alert %}}

## Création de la clef SSH

Ouvrez un terminal (git bash ou msys2 sur Windows)

{{% alert icon="" context="warning" %}}

Utilisée l'adresse mail de votre compte github/gitlab

{{% /alert %}}

```sh
ssh-keygen -t ed25519 -C "votre_adresse_mail@example.com"
```

{{% alert icon="" context="info" %}}

**NOTE !**
Pour les vieux systèmes utilisés cette commande

```sh
ssh-keygen -t rsa -b 4096 -C "votre_adresse_mail@example.com"
```

{{% /alert %}}

## Ajouter la clef à la plateforme de centralisation

{{< tabs tabTotal="2">}}
{{% tab tabName="GitLab" %}}

**GitLab**

> Rendez-vous sur la page de votre instance GitKab > préférences > SSH Keys

<img src="/git/ssh_gitlab.png" alt="ppage des clef ssh gitlab">

> dans votre terminal taper:
> ```sh
> cat ~/.ssh/id_ed25519.pub  # Sur Linux/Mac
> type ~\.ssh\id_ed25519.pub # Sur Windows
>```

{{% alert icon="" context="danger" %}}

> Ne copiez surtout pas votre clef privée `id_ed25519`

{{% /alert %}}


> Cliquez après sur add new key est complété les options.
> Vous deverez avoir quelque chose de similaire

<img src="/git/ssh_gitlab2.png" alt="page clef ssh gitlab">

```sh
ssh -T git@gitlab.siovhb.lycee-basch.fr
```

{{% alert icon="" context="success" %}}

Si tout s'est bien passé la commande devrait retourner votre nom d'utilisateurs

{{% /alert %}}

{{% /tab %}}
{{% tab tabName="Github" %}}

**Github**

> Rendez-vous sur votre dans les préférences de votre compte [github](https://github.com/settings/keys) > SSH and GPG Keys

<img src="/git/ssh_github.png" alt="page des clef ssh github">

> dans votre terminal taper les commandes suivantes
>
> ```sh
> cat ~/.ssh/id_ed25519.pub  # Sur Linux/Mac
> type ~\.ssh\id_ed25519.pub # Sur Windows
> ```

{{% alert icon="" context="danger" %}}

Ne copiez surtout pas votre clef privée `id_ed25519`

{{% /alert %}}

> Cliquez après sur `new SSH key` est complété les options.
> Vous deverez avoir quelque chose de similaire

<img src="/git/ssh_github2.png" alt="page ssh github">

```sh
ssh -T git@github.com
```

{{% alert icon="" context="success" %}}

Si tout s'est bien passé la commande devrait retourner votre nom d'utilisateurs

{{% /alert %}}

{{% /tab %}}
{{< /tabs >}}