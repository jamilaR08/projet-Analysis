
 Projet Pipeline Log_Analysis - ESISA 3ème Année

OBJECTIFS :
- analyser des fichiers de logs d'authentification (SSH)
- extraire les métriques clés (succès, échecs, utilisateurs invalides) 
- afficher un dashboard de visualisation


ARCHITECTURE DU PROJET/

log_analysis
|_ data/               # Fichier de logs bruts (.log, .gz)
|_ ingestion/         # Module de lecture et gestion des erreurs 
|_ processing/        # Module de nettoyage, extraction et géolocalisation
|_ serving/           # Module principal et orchestration (Dashboard / Matplotlib )
|_ storage/           # fichiers de logs d'erreurs de l'application
|_ README.md


INGESTION /:

Lecture robuste des fichiers texte et compressés .gz, avec gestion des exceptions et journalisation des erreurs dans storage/app_errors.log 

Processing /:

Utilisation des expressions régulières (re) pour extraire les dates, heures, adresses IP et classifier les événements (connexions réussies, échecs, invalid user)

Serving & Dashboard (serving/) :

 Centralisation du pipeline, agrégation des données et génération de graphiques statistiques via matplotlib (volume par jour, types d'événements, top des adresses IP).

 Lancement du projet

 pour lancer le projet et obtenir le dashbord:

 il faut executer le module serving/main.py

 pour le rapport :
 il faut executer le module serving/app.py