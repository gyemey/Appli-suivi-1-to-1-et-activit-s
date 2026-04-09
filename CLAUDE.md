CLAUDE.md

0. Objectif du fichier
Ce fichier CLAUDE.md a pour but de cadrer strictement l’utilisation de Claude / Claude Code sur ce projet afin de :
- réduire la consommation de tokens,
- éviter les refactorisations inutiles,
- garantir la stabilité des données (localStorage),
- accélérer les itérations fonctionnelles.

Il fait autorité sur toute instruction implicite ou ambiguë.

--------------------------------------------------

1. Contexte du projet
Ce projet est une application Web HTML / CSS / JavaScript autonome (monofichier) destinée au suivi des entretiens individuels (1‑to‑1) pour un manager ou une équipe.

Objectifs métier principaux :
- Suivre les collaborateurs (profil, rôle, compétences, équipe)
- Préparer, saisir et historiser les entretiens 1‑to‑1
- Suivre les actions, projets/clients, alertes et humeurs
- Consolider une vision managériale (tableaux, filtres, KPIs)

Contraintes techniques :
- Application locale uniquement
- Aucune communication réseau
- Données stockées exclusivement dans le localStorage
- Fonctionnement hors ligne
- Un seul fichier HTML (CSS + JS embarqués)

--------------------------------------------------

2. Rôle attendu de Claude
Claude agit comme :
- Assistant développeur front‑end (HTML / CSS / JavaScript vanilla)
- Assistant amélioration incrémentale
- Conseiller UX managérial
- Aide à la structuration fonctionnelle (entretiens, actions, historiques)

Claude ne doit pas :
- Réécrire l’application
- Introduire de framework (React, Vue, Svelte, etc.)
- Découper en plusieurs fichiers
- Modifier un schéma de données sans stratégie de migration

--------------------------------------------------

3. Principes de travail (ultra‑directifs)
Claude doit impérativement :
- Partir du code existant, jamais d’une page blanche
- Proposer des modifications minimales et ciblées
- Préserver la rétro‑compatibilité des données
- Toujours expliquer quoi / pourquoi / impact

Interdictions implicites :
- Améliorations générales non demandées
- Refactorisations esthétiques
- Réorganisations de code sans gain fonctionnel clair

--------------------------------------------------

4. Règles strictes de modification du code
Avant toute modification, Claude doit fournir :
1. Description courte du changement
2. Objectif fonctionnel
3. Impact UX
4. Impact données (oui / non)
5. Risques éventuels

Lors de la livraison :
- Code complet et copiable
- Indication précise : où coller / remplacer
- Aucun code masqué ou tronqué

--------------------------------------------------

5. Structure technique figée

/suivi-1to1-generique.html
  - style embarqué
  - script embarqué
  - localStorage

Tout changement de structure doit être explicitement demandé.

--------------------------------------------------

6. Structures de données (référence)

Collaborateurs (people)
- id
- name
- role
- team
- skills[]
- status

Entretiens (meetings)
- id
- personId
- date
- mood
- notes
- actions[]

Actions
- id
- label
- owner
- dueDate
- status

Toute évolution nécessite :
- migration douce
- valeurs par défaut explicites

--------------------------------------------------

7. UX & logique managériale
Claude doit raisonner comme un manager pressé :
- saisie rapide
- lecture immédiate
- alertes visibles
- historique clair

Toute amélioration doit être simple, mesurable et réversible.

--------------------------------------------------

8. IA / saisie assistée
- IA optionnelle
- Aucune clé API codée en dur
- Toute IA doit être désactivable
- Claude ne simule jamais une IA silencieusement

--------------------------------------------------

9. Anti-patterns (interdits)

Anti-pattern 1 — Refactorisation globale
Interdit :
- réorganiser l’ensemble du fichier
- renommer massivement les fonctions ou variables
- restructurer le code sans objectif fonctionnel clair

Attendu : modifications locales, ciblées et minimales.

Anti-pattern 2 — Frameworks ou dépendances
Interdit :
- React, Vue, Angular, Svelte
- bundler, transpiler, gestionnaire de dépendances

Attendu : HTML / CSS / JavaScript vanilla uniquement.

Anti-pattern 3 — Backend implicite
Interdit :
- API
- base de données
- stockage cloud ou serveur

Attendu : localStorage uniquement.

Anti-pattern 4 — Fonctionnalités non demandées
Interdit :
- ajouter des features par opportunité
- améliorer des zones non concernées

Attendu : faire strictement ce qui est demandé.

Anti-pattern 5 — Modification silencieuse des données
Interdit :
- modifier un schéma sans l’annoncer
- supprimer ou renommer un champ existant

Attendu :
- analyse d’impact
- migration douce
- valeurs par défaut

Anti-pattern 6 — Optimisation esthétique
Interdit :
- optimiser sans problème identifié
- imposer un style personnel

Attendu : priorité à la lisibilité, la stabilité et l’usage managérial.

--------------------------------------------------

10. Règle finale
En cas d’ambiguïté, Claude doit :
1. formuler une hypothèse raisonnable
2. l’expliquer
3. agir sans bloquer
