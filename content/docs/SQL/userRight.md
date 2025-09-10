+++
weight = 120
date = "2025-05-03T22:37:22+02:00"
draft = false
author = "TRAVERS Mathéo"
title = "SQL Droit utilisateurs"
icon = "rocket_launch"
toc = true
description = "Base des requêtes SQL"
publishdate = "2025-05-03T22:37:22+02:00"
tags = ["sql"]
+++

## Créations d'utilisateurs


{{% alert icon="" context="warning" %}}

ATTENTION ! 

Les requêtes sont basé sur des serveurs de type MariaDB/MySQL

Il ce peut qu'il y'es des modifications à prévoire pour PostgreSQL et les autres

{{% /alert %}}

Créer un utilisateur
```sql
CREATE USER 'nomUtilisateurs'@'localhost' IDENTIFIED BY 'motdepasse';
```

{{% alert icon="" context="info" %}}

INFO Localhost

localhost permet à l'utilisateur de ce connecter que en local c'est un équivalent moins stricte que 127.0.0.1

Voici une liste exaustive des autres modes

| Titre    | Options                | description |
|----------|------------------------|--------------------------------------------------------|
|Tous      | %                      | Toutes connexion pause des enjeux de sécuritée à évitée |
| Domaine  | monserveur.domaine.com | On peut limitée par un domaine |
|IP Stricte| 192.168.1.50           | Bloquage stricte en IP |
| IP Plage |192.168.1.%             | autorise toute les IP commençan par 192.168.1 |

{{% /alert %}}

## Changer info utilisateur

### Changer le mot de passe utilisateur

```sql
ALTER USER 'utilisateur'@'localhost' IDENTIFIED BY 'newpass';
```


### Changer le nom d'utilisateur

```sql
RENAME USER 'utilisateur'@'localhost' TO 'geralt'@'localhost';
```


## DROIT Utilisateur

### Lister les droits

{{< tabs tabTotal="2">}}
{{% tab tabName="Commande" %}}

**Commande**

```
SHOW GRANTS FOR 'utilisateur'@'localhost';
```

{{% /tab %}}
{{% tab tabName="Résulta" %}}

**Résulta**



{{% /tab %}}
{{< /tabs >}}


### Données des droits
Cette commande attribut tout les droits à l'utilisateur sur la base test_db ainsie que toutes les tables qui luis sont associer

```sql
GRANT ALL PRIVILEGES ON test_db.* TO 'utilisateur'@'localhost';
FLUSH PRIVILEGES;
```

{{% alert icon="" context="info" %}}

INFO ! 

**`FLUSH PRIVILEGES`** n'est pas une obligation il permet juste de recharger les droits sans avoir besoin de redémarée le serveur

Pour faire simple si vous voullez que les nouvelles rêgles de droit soit effectif vaut mieux le faire!


{{% /alert %}}


Pour données des droits spécifiques ont peut utilisées cette commande 

```sql
GRANT SELECT, INSERT, UPDATE, DELETE ON nom_base.* TO 'utilisateur'@'localhost';
```

{{% alert icon="" context="info" %}}

INFO ! 




{{% /alert %}}
