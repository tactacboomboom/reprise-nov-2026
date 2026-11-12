# REPRISE NOV 2026 — index

Objectif : après la réinstallation du Custom PC (09/11/2026), analyser les repos GitHub
`tactacboomboom`, en rendre la MÉMOIRE à Yanis puis récupérer l'utile dans le setup actuel.
Règles et gabarit : `CLAUDE.md`.
Convention : lettre = pilote (chronologique) ; `Pilote.N` = contrat parallèle dont ce pilote
fait le fan-in (il peut avoir été écrit par le pilote précédent : H.1 par D) ; colonne Parent =
qui fait le fan-in. Détail : `CLAUDE.md` § Nommage des séances.

## Lancer une séance
```
cd "G:\Mon Drive\10 - Claude\TRANSVERS\REPRISE NOV 2026"
claude
/debut-session docs/kernels/<kernel de la séance>.md
```

## Séances

| Code | Parent | Vague | Objet | Kernel écrit | Findings | État |
|---|---|---|---|---|---|---|
| A | — | — | Réinstallation du Custom PC | `2026-11-09-A-reinstallation-custom-pc.md` | — | clos |
| B | A | — | Reconstruction de /debut-session v3 | `2026-11-09-B-debut-session-preparation-repos.md` | `2026-11-09-B-debut-session-r-gate.md` | clos |
| C | B | — | Architecture-des-skills + rangement + cadrage des vagues | `2026-11-09-C-pilotage-vague-1.md` | `2026-11-09-C-architecture-des-skills.md` | clos |
| D | C | pilote 1 | Lance la vague 1, juge D.1–D.3, écrit le gabarit et les kernels H.1/H.2 | `2026-11-10-D-pilotage-vague-2.md` | — | clos |
| D.1 (E) | D | 1 | PLUG-INS + -graphify-transformer (tri) | `2026-11-09-E-analyse-plug-ins-graphify.md` (lancement) | `2026-11-10-E-plug-ins-graphify.md` | findings écrit |
| D.2 (F) | D | 1 | audit-repo (tri) | `2026-11-09-F-analyse-audit-repo.md` (lancement) | `2026-11-10-F-audit-repo.md` | findings écrit |
| D.3 (G) | D | — | Convention de nommage des séances parallèles | `2026-11-10-G-convention-nommage.md` (lancement) | `2026-11-10-G-convention-nommage.md` | findings écrit |
| H | D | pilote 2 | Fan-in de la vague 2 : juge H.1/H.2, corrige le gabarit, écrit les kernels I.1/I.2 | `2026-11-10-H-pilotage-vague-3.md` | `2026-11-10-H-pilotage-vague-2.md` | clos |
| H.1 | H | 2 | PLUG-INS + -graphify-transformer, refait en fiche mémoire | `2026-11-10-H.1-memoire-plug-ins-graphify.md` (lancement) | `2026-11-10-H.1-memoire-plug-ins-graphify.html` | fiche écrite (ARCHIVER) |
| H.2 | H | 2 | audit-repo (+ skill /repo-audit), refait en fiche mémoire | `2026-11-10-H.2-memoire-audit-repo.md` (lancement) | `2026-11-10-H.2-memoire-audit-repo.html` | fiche écrite (ARCHIVER) |
| I | H | pilote 3 | Fan-in de la vague 3 : juge I.1/I.2, corrige le gabarit et les règles de kernels, écrit les kernels J.1/J.2 | `2026-11-10-H-pilotage-vague-3.md` (kernel de H, lu par I) | `2026-11-11-I-pilotage-vague-3.md` | clos |
| I.1 | I | 3 | CPE-PWF-Engine (février 2026) en fiche mémoire | `2026-11-10-I.1-memoire-cpe-pwf-engine.md` (lancement) · `contrats/2026-11-11-I.1-cloture.md` | `2026-11-10-I.1-memoire-cpe-pwf-engine.html` | fiche écrite (ARCHIVER) |
| I.2 | I | 3 | Lot « conformité Anthropic » : Architecture-des-skills-Anthropic (refait après C) + les 6 audits Anthropic (= séance « vision Anthropic » de H.2) | `2026-11-10-I.2-memoire-conformite-anthropic.md` (lancement) · `contrats/2026-11-11-I.2-cloture.md` | `2026-11-10-I.2-memoire-conformite-anthropic.html` | fiche écrite (ARCHIVER le repo ; projet à reprendre) |
| J | I | pilote 4 | Fan-in de la vague 4 : juge J.1/J.2, gabarit à 8 sections, écrit les kernels K.1/K.2 | `2026-11-11-J-pilotage-vague-4.md` (écrit par I à sa clôture) | `2026-11-11-J-pilotage-vague-4.md` | clos |
| J.1 | J | 4 | Lot Claire + claire-app (mai, descendants de CPE) en fiche mémoire | `2026-11-11-J.1-memoire-claire.md` (lancement) · `contrats/2026-11-11-J.1-cloture.md` | `2026-11-11-J.1-memoire-claire.html` | fiche écrite (ARCHIVER ×2) |
| J.2 | J | 4 | Lot « intention, janvier » : cockpit-solo + De-l-Intention-a-l-Execution + chaine-intention-artefacts (ancêtres de CPE) | `2026-11-11-J.2-memoire-intention-janvier.md` (lancement) · `contrats/2026-11-11-J.2-cloture.md` | `2026-11-11-J.2-memoire-intention-janvier.html` | fiche écrite (ARCHIVER ×3) |
| K | J | pilote 5 | Fan-in de la vague 5 : juge K.1/K.2, écrit le kernel L.1 (claude-prostheses) | `2026-11-11-K-pilotage-vague-5.md` (écrit par J à sa clôture) | — | prévu |
| K.3 | K | 5 (seul, avant K.1 ∥ K.2) | Revue d'architecture + migration du dossier : méthodes GAFAM, conformité Architecture-des-skills-Anthropic (dérogation : fichiers du pilote) | `2026-11-11-K.3-architecture-migration.md` (lancement) | à produire | prêt, à lancer EN PREMIER |
| K.1 | K | 5 | Lot « janvier, les bornes » : test-ia + CARTE-des-richesses (fiche 8 sections) | `2026-11-11-K.1-memoire-janvier-bornes.md` (lancement) | à produire (`.html`) | prêt |
| K.2 | K | 5 | Lot « mai–juin » : Anthropologie + projet-amelioration-fin-session + voyage_voyage (fiche 8 sections) | `2026-11-11-K.2-memoire-mai-juin.md` (lancement) | à produire (`.html`) | prêt |
| L.1 | L | 6 | claude-prostheses seul : fin de la lignée, le plus gros morceau (Yanis, J) | à écrire par K | — | prévu |
| — | — | — | Convergence (lettre de pilote, parent = dernier pilote) : lit toutes les fiches, décide quoi réinstaller | après la dernière vague | — | prévu |

## Plan et tâches
Le plan de travail et les tâches dérivées vivent dans `task_plan.md` (gabarit /pwf), mis à jour par
le pilote à chaque fan-in. Ce README reste l'index des séances.

## Métriques de séance
`data/ops-ledger.csv` : 1 ligne par séance (coût, durée, contexte à la clôture…), ajoutée à la
clôture avec la commande inscrite dans `CLAUDE.md` § Outils.

Kernels de LANCEMENT (pas de clôture) : E, F écrits par C ; G, H.1, H.2 écrits par D. Parent =
celui qui fait le fan-in (D pour E, F, G ; H pour H.1, H.2), pas l'auteur du kernel.
Depuis la vague 2 : livrable = fiche mémoire HTML (`docs/gabarits/fiche-memoire.html`) — la vague 1
a trié sans rendre la mémoire des repos (constat de D, 10/11).
Skills `/goedel` et `/debut-session` : diffs prêts dans le findings G § 6. La convention a tenu sur
la vague 2, mais on ne les applique dans `-my-claude-config` qu'après PLUSIEURS vagues rodées
(décision Yanis, 10/11).
Entre deux vagues : le pilote relit les findings et corrige le gabarit si besoin (H, 10/11 :
prévu/réel en § 5, preuve « témoignage de Yanis », puce « Proposition au pilote » en § 7 ; I, 11/11 :
voix « Yanis », témoignage brut en blockquote dans les Preuves, verdict sur le repo, fiche lisible
sans le kernel).
Depuis I (11/11, demande de Yanis) : un kernel porte le code de la séance qui s'ouvre avec lui (on
ouvre J avec le kernel J). Les contrats écrivent leur kernel de clôture dans `docs/kernels/contrats/` ;
le kernel du pilote les liste dans [Fichiers à charger], donc plus de copier-coller.

## Pour la convergence (notes des pilotes)
- **Carte de l'arsenal de mai** : chaque fiche montre un repo ; le sens était dans les liens.
  Témoignage de Yanis (10/11) : des « prothèses agentiques » partout, chaque agent étant le clone de
  quelque chose (concepts, conformité Anthropic, PhD IA, scrum solo, mémoire externe, bibliographie
  sémantique, méthodes), en bootstrap, sans prof, avec sa tête comme seul lien → à dessiner en convergence.
- **rag_concepts** : couvert par H.1 (1 commit, `graph.html` seul, aucun code de RAG). Pas de contrat
  dédié (Yanis, 10/11). Reste ouvert : il est public alors que le vault est privé.
- **claude-mem** : non réinstallé (décision Yanis, H.1). Le tri « RÉCUPÉRER claude-mem » de F/H.2
  est périmé.
- **Lignée de l'intention** (I.1) : 5 repos de janvier → CPE-PWF-Engine (02/02) → Claire (mai) →
  claude-prostheses. Fils : chaîne « nilpotente », « plusieurs avis → les biais s'annulent »
  (binômes de /cpe-sprint ?). Sources primaires du vault : voir `task_plan.md`, phase 3, point 8.
- **Persona-prothèses = plugins** (I.2, Yanis, 11/11) : architecture-anthropic à reprendre sous cette
  forme (vraie pour l'emballage, pas pour l'enrichissement dans le temps). Suites : `task_plan.md`,
  phase 3, points 1–7.
- **Lignée de l'intention, en 8 étapes** (J.2 § 4 A, J.1) : cockpit-solo 08/01 → De-l-Intention
  12/01 → chaîne 14/01 → CPE 02/02 → Claire mai → claude-prostheses. Motif : la méthode ne s'applique
  qu'à elle-même. Deux dates de J.1 à rectifier (μA ≥ 0,5 et Scrum datent de janvier) : findings J § 2.
- **Carte et rangement des 18 repos** (Yanis, J) : la convergence propose le tri / classement /
  rangement de tous les repos `tactacboomboom` (`-my-claude-config` inclus sur la carte).
- **Circuit des audits** : `PLUG-INS/<nom>/` sur le Drive = seule maison (R13) ; vitrine
  audit-repo/Vercel redondante (H.1 Q4 + H.2 Q1, recommandation de H).
