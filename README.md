# ArtisanConnect — Outil IA d’analyse de sentiment (Mistral) — Notebook OC

Notebook réalisé dans le cadre du projet OpenClassrooms **“Intégrez les règles RGPD / sécurité digitale”** (ArtisanConnect) : développement d’un **POC d’analyse de sentiment** sur des avis clients, afin de **prioriser** le traitement des retours et d’alimenter un pilotage (ex. Looker Studio).

## Objectifs
- Tester une intégration avec l’API **Mistral AI** depuis Google Colab.
- Classifier les commentaires d’avis en **Positif / Neutre / Négatif**.
- Produire un fichier CSV exportable contenant la prédiction (ex. `sentiment_predit_mistral`).
- Documenter les limites de l’IA (ironie, ambiguïté) et les points RGPD.
- Ajouter un contrôle qualité : **incohérence “note vs IA”** (cas “à vérifier”).

## Contenu du repo
- `Outil_IA_analyse_de_sentiment.ipynb` : notebook complet (exécution + commentaires + exports).
- `avis_clients.csv` (optionnel) : dataset simulé (à ne pas publier si données sensibles / PII).
- `avis_echantillon_avec_sentiment.csv` : export d’échantillon enrichi (facultatif).

> Recommandation : éviter de versionner des données contenant de la PII. Préférer un dataset anonymisé ou un échantillon réduit sans identifiants.

## Pré-requis
- Un compte Mistral AI + une **clé API**.
- Google Colab (recommandé) ou un environnement Python 3.
- Librairies : `mistralai`, `pandas`.

## Installation / exécution rapide (Google Colab)
1. Ouvrir le notebook dans Colab :
   - Google Drive → clic droit → **Ouvrir avec → Google Colaboratory**
2. Ajouter la clé API dans **Colab Secrets** :
   - Nom : `MISTRAL_API_KEY`
3. Exécuter les cellules **dans l’ordre** :
   - Installation des dépendances
   - Récupération de la clé via `userdata.get('MISTRAL_API_KEY')`
   - Import du fichier `avis_clients.csv`
   - Test unitaire (1 avis) puis analyse d’un échantillon

### Dépendances (si exécution locale)
```bash
pip install mistralai pandas
