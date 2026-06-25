# Workflow n8n — Job Automation Assistant V2

## Objectif

Orchestrer automatiquement la collecte, l'analyse, le scoring, la génération de lettre et l'envoi email.

## Chaîne principale

```text
Schedule Trigger
↓
Token France Travail
↓
France Travail - Offres
↓
Suppression Doublons
↓
Tri Offres
↓
Top Offres
↓
Split Out
↓
Score Règles Candidat
↓
Filtre Score Règles
↓
Analyse IA Ollama
↓
Parser Réponse IA
↓
IF Erreur IA
↓
logs_ia
↓
Merge
↓
Qualité IA
↓
Historique Qualité IA
↓
Historique Performances IA
↓
Fusion Score Final
↓
Classement Final
↓
IF Score
↓
Préparer Prompt LM
↓
Génération LM Ollama
↓
Parser LM
↓
Merge LM
↓
Update Lettre Brouillon
↓
Insérer Version Lettre
↓
Historique LM
↓
Préparer Email Candidature
↓
Send Email

Gestion des erreurs IA

Parser Réponse IA
↓
IF Erreur IA
├── true  → Erreur IA
└── false → logs_ia


Retry automatique

Nodes configurés avec retry :

Analyse IA Ollama
France Travail - Offres
HTTP Request

Configuration :

Retry On Fail = ON
Max Tries = 3
Wait Between Tries = 2000 ms
Tables PostgreSQL utilisées
offres
lettres
historique_lettres
logs_ia
prompt_versions
qualite_ia
performances_ia
