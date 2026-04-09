Suivi 1-to-1 – Application managériale locale

OBJECTIF
Cette application est une application Web locale (HTML / CSS / JavaScript vanilla, monofichier)
destinée au suivi des entretiens individuels (1-to-1) pour un manager ou une équipe.

Elle permet de structurer, historiser et piloter les échanges managériaux sans backend ni cloud.


FONCTIONNALITES PRINCIPALES
- Gestion des collaborateurs (profil, rôle, équipe, compétences)
- Préparation et historisation des entretiens 1-to-1
- Suivi des actions issues des entretiens
- Suivi des projets / clients associés
- Gestion des humeurs et alertes
- Filtres et vues de synthèse managériales
- Import / export des données (Excel)
- Fonctionnement hors ligne


CONTRAINTES TECHNIQUES
- Application 100 % locale
- Aucun backend
- Aucune communication réseau
- Données stockées dans le localStorage du navigateur
- Un seul fichier HTML (CSS + JS embarqués)
- JavaScript vanilla uniquement


STRUCTURE DU PROJET
/suivi-1to1/
- suivi-1to1-generique.html
- CLAUDE.md
- README.md (ou README.txt)


UTILISATION
1. Télécharger ou cloner le projet
2. Ouvrir le fichier suivi-1to1-generique.html dans un navigateur moderne
3. L'application est immédiatement opérationnelle

Attention : les données sont stockées localement dans le navigateur utilisé.


PHILOSOPHIE DU PROJET
- Simplicité d'usage managérial
- Rapidité de saisie
- Lisibilité immédiate
- Robustesse des données
- Evolutions incrémentales et maîtrisées


UTILISATION AVEC CLAUDE
Un fichier CLAUDE.md est présent à la racine du projet.
Il définit les règles strictes d'utilisation de Claude / Claude Code :
- contraintes techniques
- règles de modification du code
- interdictions (frameworks, backend, refactor massif, etc.)

Toute évolution doit respecter ce fichier.
Le fichier `CLAUDE.md` inclut également une section **Anti‑patterns** définissant explicitement les comportements interdits (frameworks, backend, refactorisation globale, etc.) afin de garantir la stabilité et la cohérence du projet.


HORS PERIMETRE
- Backend ou API serveur
- Multi-utilisateur
- Synchronisation cloud
- Frameworks front-end (React, Vue, etc.)


ETAT DU PROJET
- Fonctionnel
- Stable
- Evolutif de manière contrôlée
