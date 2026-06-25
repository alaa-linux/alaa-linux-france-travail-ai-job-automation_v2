# PostgreSQL — Job Automation Assistant V2

## Base de données

Nom :

```text
jobdb
```

## Tables principales

### offres

Stocke les offres France Travail collectées.

Principaux champs :

```text
offre_id
titre
entreprise
ville
contrat
experience
description
url
score_ia
score_final
classement_final
lettre_brouillon
```

### lettres

Stocke les lettres générées.

### historique_lettres

Historique complet des lettres générées par IA.

### logs_ia

Journal technique des appels IA.

Champs :

```text
offre_id
modele_ia
score_ia
statut
type_erreur
prompt_version
date_execution
```

### prompt_versions

Historique des versions de prompts.

Exemple :

```text
prompt_analyse_ia_v1
```

### qualite_ia

Mesure de la qualité des analyses IA.

Valeurs :

```text
BONNE
MOYENNE
MAUVAISE
```

### performances_ia

Mesure des performances des appels IA.

Champs :

```text
offre_id
modele_ia
duree_ms
statut
```

## Requêtes utiles

Afficher les tables :

```sql
\dt
```

Afficher les logs IA :

```sql
SELECT *
FROM logs_ia
ORDER BY id DESC
LIMIT 20;
```

Afficher la qualité IA :

```sql
SELECT *
FROM qualite_ia
ORDER BY id DESC;
```

Afficher les performances :

```sql
SELECT *
FROM performances_ia
ORDER BY id DESC;
```
