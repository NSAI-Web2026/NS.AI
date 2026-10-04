# NS.AI — Web

Version web Streamlit de NS.AI.

## Fonctionnalités

- Chat IA
- Mode automatique / rapide / complexe
- Recherche Web avec Google Search grounding
- Analyse d'images envoyées par l'utilisateur
- Analyse de PDF, TXT, MD, CSV et DOCX
- Quotas locaux + coupe-circuit serveur
- Aucune génération d'images ou de vidéos
- Aucune clé API demandée à l'utilisateur
- Secrets conservés côté serveur

## Configuration locale

Créer `.streamlit/secrets.toml` :

```toml
GEMINI_API_KEY = "TA_CLE_ICI"
NSAI_MODEL = "gemini-2.5-flash"
NSAI_COMPLEX_MODEL = "gemini-2.5-pro"
NSAI_DAILY_LIMIT = 20
NSAI_COMPLEX_LIMIT = 5
NSAI_SEARCH_LIMIT = 8
NSAI_SERVER_DAILY_LIMIT = 1000
```

Ne publie jamais ce fichier dans GitHub.

Lancer :

```bash
pip install -r requirements.txt
streamlit run app.py
```

## Publication

Sur Streamlit Community Cloud, mettre `app.py`, `requirements.txt` et `NS_AI_LOGO.png`
dans un dépôt GitHub. Ajouter `GEMINI_API_KEY` dans les Secrets de l'application,
pas dans le code.

## Important

Cette version protège les secrets en ne les affichant jamais dans l'interface.
Les quotas de `session_state` sont adaptés au prototype, mais pour un service
public à grande échelle il faudra une authentification et une base de données
distante pour imposer des quotas réellement par utilisateur.

NS.AI+ est uniquement préparé dans l'interface : aucun paiement réel n'est
activé dans cette version.
