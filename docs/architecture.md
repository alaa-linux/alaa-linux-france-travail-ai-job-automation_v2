# Architecture Job Automation Assistant V2

France Travail API
        |
        v
      n8n
        |
        +------------------+
        |                  |
        v                  v
 Analyse IA          Génération LM
 (Ollama)            (Ollama)
        |                  |
        +--------+---------+
                 |
                 v
            PostgreSQL
                 |
                 v
              Email
