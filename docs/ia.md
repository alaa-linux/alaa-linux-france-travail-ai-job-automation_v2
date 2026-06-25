# IA — Job Automation Assistant V2

## Objectif

L'IA locale est utilisée pour :

- analyser les offres France Travail ;
- calculer un score IA ;
- détecter les compétences ;
- générer des lettres de motivation ;
- préparer les emails de candidature.

---

## Moteur IA

Ollama

---

## Modèles utilisés

### Analyse offres

```text
gemma3:1b
```

### Génération lettre motivation

```text
phi4
```

---

## Prompt versionné

Version actuelle :

```text
prompt_analyse_ia_v1
```

Table PostgreSQL :

```text
prompt_versions
```

---

## Gestion erreurs IA

Erreurs détectées :

```text
JSON_INVALIDE
REPONSE_VIDE
TIMEOUT
```

Gestion :

```text
IF Erreur IA
```

---

## Retry automatique

Nodes protégés :

```text
Analyse IA Ollama
France Travail - Offres
HTTP Request
```

Configuration :

```text
Retry On Fail = ON
Max Tries = 3
Wait Between Tries = 2000 ms
```

---

## Logs IA

Table :

```text
logs_ia
```

Informations enregistrées :

```text
offre_id
modele_ia
score_ia
statut
type_erreur
prompt_version
reponse_ia
```

---

## Qualité IA

Table :

```text
qualite_ia
```

Niveaux :

```text
BONNE
MOYENNE
MAUVAISE
```

---

## Performances IA

Table :

```text
performances_ia
```

Mesures :

```text
temps réponse
statut
modèle
```
