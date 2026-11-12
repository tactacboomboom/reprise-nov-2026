# REPRISE NOV 2026 — index

Objectif : après la réinstallation du Custom PC (09/11/2026), analyser les repos GitHub
`tactacboomboom`, en rendre la MÉMOIRE à Yanis puis récupérer l'utile dans le setup actuel.
Règles et gabarit : `CLAUDE.md`.
Convention : lettre = pilote (chronologique) ; `Pilote.N` = contrat parallèle dont ce pilote
fait le fan-in (il peut avoir été écrit par le pilote précédent : H.1 par D) ; colonne Parent =
qui fait le fan-in. Détail : `CLAUDE.md` § Nommage des séances.

## En cours
<!-- Mis à jour par le pilote à chaque fan-in. L'état vit ici, jamais dans les chemins. -->
- **Pilote K (vague 5)** : `seances/K-pilotage-vague-5/` — K.3 ✓ · K.1 ✓ · K.2 ✓ · K.4 ✓ (Anthropologie archivé en témoin, ouvert par K.2) · fan-in fait (12/11)
- **Ensuite** : L.1 claude-prostheses (vague 6, kernel écrit par K) → pilote L → convergence

## Lancer une séance
Une séance = un worktree (séances parallèles : jamais deux séances dans le même dossier) :
```
cd "C:\Users\bensa\00_MES-PROJETS\reprise-nov-2026"
git fetch
git worktree add ../reprise-nov-2026-<code> -b seance/<code>-<slug> --no-track origin/main
cd ../reprise-nov-2026-<code>
claude
/debut-session seances/<pilote>-<slug>/[<Pilote.N>-<slug>/]<kernel de la séance>.md
```
Toujours donner le chemin du kernel : `/debut-session` sans argument cherche encore l'ancien
dossier des kernels (diff du skill recommandé, non appliqué). Le dossier `REPRISE NOV 2026` du Drive
est FIGÉ au 12/11 : on ne travaille plus dedans.

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
| I.1 | I | 3 | CPE-PWF-Engine (février 2026) en fiche mémoire | `2026-11-10-I.1-memoire-cpe-pwf-engine.md` (lancement) · `2026-11-11-I.1-cloture.md` | `2026-11-10-I.1-memoire-cpe-pwf-engine.html` | fiche écrite (ARCHIVER) |
| I.2 | I | 3 | Lot « conformité Anthropic » : Architecture-des-skills-Anthropic (refait après C) + les 6 audits Anthropic (= séance « vision Anthropic » de H.2) | `2026-11-10-I.2-memoire-conformite-anthropic.md` (lancement) · `2026-11-11-I.2-cloture.md` | `2026-11-10-I.2-memoire-conformite-anthropic.html` | fiche écrite (ARCHIVER le repo ; projet à reprendre) |
| J | I | pilote 4 | Fan-in de la vague 4 : juge J.1/J.2, gabarit à 8 sections, écrit les kernels K.1/K.2 | `2026-11-11-J-pilotage-vague-4.md` (écrit par I à sa clôture) | `2026-11-11-J-pilotage-vague-4.md` | clos |
| J.1 | J | 4 | Lot Claire + claire-app (mai, descendants de CPE) en fiche mémoire | `2026-11-11-J.1-memoire-claire.md` (lancement) · `2026-11-11-J.1-cloture.md` | `2026-11-11-J.1-memoire-claire.html` | fiche écrite (ARCHIVER ×2) |
| J.2 | J | 4 | Lot « intention, janvier » : cockpit-solo + De-l-Intention-a-l-Execution + chaine-intention-artefacts (ancêtres de CPE) | `2026-11-11-J.2-memoire-intention-janvier.md` (lancement) · `2026-11-11-J.2-cloture.md` | `2026-11-11-J.2-memoire-intention-janvier.html` | fiche écrite (ARCHIVER ×3) |
| K | J | pilote 5 | Fan-in de la vague 5 : juge K.3/K.1/K.2, écrit le kernel L.1 (claude-prostheses) | `2026-11-11-K-pilotage-vague-5.md` (écrit par J à sa clôture) | `2026-11-12-K-pilotage-vague-5-findings.md` | fan-in fait |
| K.3 | K | 5 (seul, avant K.1 ∥ K.2) | Revue d'architecture + migration du dossier : méthodes GAFAM, conformité Architecture-des-skills-Anthropic (dérogation : fichiers du pilote) | `2026-11-11-K.3-architecture-migration.md` (lancement) · `2026-11-12-K.3-cloture.md` | `2026-11-12-K.3-architecture-migration-findings.md` | migration faite (repo git, 0 chemin mort) |
| K.1 | K | 5 | Lot « janvier, les bornes » : test-ia + CARTE-des-richesses (fiche 8 sections) | `2026-11-11-K.1-memoire-janvier-bornes.md` (lancement) · `2026-11-11-K.1-cloture.md` | `2026-11-11-K.1-memoire-janvier-bornes.html` | fiche écrite (IGNORER, ARCHIVER) |
| K.2 | K | 5 | Lot « mai–juin » : Anthropologie + projet-amelioration-fin-session + voyage_voyage (fiche 8 sections) | `2026-11-11-K.2-memoire-mai-juin.md` (lancement) · `2026-11-11-K.2-cloture.md` | `2026-11-11-K.2-memoire-mai-juin.html` | fiche écrite (RÉCUPÉRER, ARCHIVER, RÉCUPÉRER) |
| K.4 | K | 5 (ouvert par K.2) | Exécution : mettre le repo privé Anthropologie aux bonnes pratiques (SVD calculée) | `2026-11-12-K.4-anthropologie-pro.md` (lancement, écrit par K.2) · `2026-11-12-K.4-cloture.md` | `2026-11-12-K.4-anthropologie-pro-findings.md` | fait (repo étudié : PR #1 mergée, archivé en témoin) |
| L.1 | L | 6 | claude-prostheses seul : fin de la lignée, le plus gros morceau (Yanis, J) | `2026-11-12-L.1-memoire-claude-prostheses.md` (lancement, écrit par K) | — | prêt |
| — | — | — | Convergence (lettre de pilote, parent = dernier pilote) : lit toutes les fiches, décide quoi réinstaller | après la dernière vague | — | prévu |

## Rangement (K.3, 12/11)
Un dossier par pilote `seances/<pilote>-<slug>/`, et dedans un sous-dossier par contrat
`<Pilote.N>-<slug>/` (kernel de lancement + livrable + clôture ; 1 niveau, pas de D.1.1). Les
noms de fichiers sont inchangés (sauf 2 doublons suffixés `-findings`). La note d'un pilote est
rangée dans le dossier de celui qui l'ÉCRIT, pas dans celui de la vague qu'elle juge
(ex. `H-pilotage-vague-2/…-H-pilotage-vague-2.md` = le fan-in de la vague de D).

Correspondance avec les méthodes des équipes dev (spécialiste GAFAM, K.3) :

| Méthode dev | Ici | Juste ou forcé |
|---|---|---|
| Ticket / issue | kernel de lancement | juste |
| Package / dossier `OWNERS` (Google, Bazel) | `seances/<pilote>-<slug>/` et ses contrats (permanent) | juste |
| Branche (temporaire, supprimée après merge) | `seance/<code>-<slug>` dans git | juste depuis git |
| Pull request (+ description) | fiche + kernel de clôture | juste |
| Revue + merge | fan-in du pilote | juste |
| CODEOWNERS | « réservé au pilote » (CLAUDE.md) ; pas de fichier CODEOWNERS en solo | juste |
| Journal de décisions (≠ ADR) | tableau « Decisions Made » de `task_plan.md` | ADR seulement si une décision en remplace une autre |

<details><summary>Table ancien → nouveau chemin (38 fichiers, migration K.3 du 12/11)</summary>

| Ancien chemin | Nouveau chemin |
|---|---|
| `docs/kernels/2026-11-09-A-reinstallation-custom-pc.md` | `seances/A-reinstallation-custom-pc/2026-11-09-A-reinstallation-custom-pc.md` |
| `docs/kernels/2026-11-09-B-debut-session-preparation-repos.md` | `seances/B-debut-session/2026-11-09-B-debut-session-preparation-repos.md` |
| `docs/kernels/2026-11-09-C-pilotage-vague-1.md` | `seances/C-architecture-des-skills/2026-11-09-C-pilotage-vague-1.md` |
| `docs/kernels/2026-11-09-E-analyse-plug-ins-graphify.md` | `seances/D-pilotage-vague-1/D.1-plug-ins-graphify/2026-11-09-E-analyse-plug-ins-graphify.md` |
| `docs/kernels/2026-11-09-F-analyse-audit-repo.md` | `seances/D-pilotage-vague-1/D.2-audit-repo/2026-11-09-F-analyse-audit-repo.md` |
| `docs/kernels/2026-11-10-D-pilotage-vague-2.md` | `seances/D-pilotage-vague-1/2026-11-10-D-pilotage-vague-2.md` |
| `docs/kernels/2026-11-10-G-convention-nommage.md` | `seances/D-pilotage-vague-1/D.3-convention-nommage/2026-11-10-G-convention-nommage.md` |
| `docs/kernels/2026-11-10-H-pilotage-vague-3.md` | `seances/H-pilotage-vague-2/2026-11-10-H-pilotage-vague-3.md` |
| `docs/kernels/2026-11-10-H.1-memoire-plug-ins-graphify.md` | `seances/H-pilotage-vague-2/H.1-memoire-plug-ins-graphify/2026-11-10-H.1-memoire-plug-ins-graphify.md` |
| `docs/kernels/2026-11-10-H.2-memoire-audit-repo.md` | `seances/H-pilotage-vague-2/H.2-memoire-audit-repo/2026-11-10-H.2-memoire-audit-repo.md` |
| `docs/kernels/2026-11-10-I.1-memoire-cpe-pwf-engine.md` | `seances/I-pilotage-vague-3/I.1-memoire-cpe-pwf-engine/2026-11-10-I.1-memoire-cpe-pwf-engine.md` |
| `docs/kernels/2026-11-10-I.2-memoire-conformite-anthropic.md` | `seances/I-pilotage-vague-3/I.2-memoire-conformite-anthropic/2026-11-10-I.2-memoire-conformite-anthropic.md` |
| `docs/kernels/2026-11-11-J-pilotage-vague-4.md` | `seances/J-pilotage-vague-4/2026-11-11-J-pilotage-vague-4.md` |
| `docs/kernels/2026-11-11-J.1-memoire-claire.md` | `seances/J-pilotage-vague-4/J.1-memoire-claire/2026-11-11-J.1-memoire-claire.md` |
| `docs/kernels/2026-11-11-J.2-memoire-intention-janvier.md` | `seances/J-pilotage-vague-4/J.2-memoire-intention-janvier/2026-11-11-J.2-memoire-intention-janvier.md` |
| `docs/kernels/2026-11-11-K-pilotage-vague-5.md` | `seances/K-pilotage-vague-5/2026-11-11-K-pilotage-vague-5.md` |
| `docs/kernels/2026-11-11-K.1-memoire-janvier-bornes.md` | `seances/K-pilotage-vague-5/K.1-memoire-janvier-bornes/2026-11-11-K.1-memoire-janvier-bornes.md` |
| `docs/kernels/2026-11-11-K.2-memoire-mai-juin.md` | `seances/K-pilotage-vague-5/K.2-memoire-mai-juin/2026-11-11-K.2-memoire-mai-juin.md` |
| `docs/kernels/2026-11-11-K.3-architecture-migration.md` | `seances/K-pilotage-vague-5/K.3-architecture-migration/2026-11-11-K.3-architecture-migration.md` |
| `docs/kernels/contrats/2026-11-11-I.1-cloture.md` | `seances/I-pilotage-vague-3/I.1-memoire-cpe-pwf-engine/2026-11-11-I.1-cloture.md` |
| `docs/kernels/contrats/2026-11-11-I.2-cloture.md` | `seances/I-pilotage-vague-3/I.2-memoire-conformite-anthropic/2026-11-11-I.2-cloture.md` |
| `docs/kernels/contrats/2026-11-11-J.1-cloture.md` | `seances/J-pilotage-vague-4/J.1-memoire-claire/2026-11-11-J.1-cloture.md` |
| `docs/kernels/contrats/2026-11-11-J.2-cloture.md` | `seances/J-pilotage-vague-4/J.2-memoire-intention-janvier/2026-11-11-J.2-cloture.md` |
| `docs/findings/2026-11-09-B-debut-session-r-gate.md` | `seances/B-debut-session/2026-11-09-B-debut-session-r-gate.md` |
| `docs/findings/2026-11-09-C-architecture-des-skills.md` | `seances/C-architecture-des-skills/2026-11-09-C-architecture-des-skills.md` |
| `docs/findings/2026-11-10-E-plug-ins-graphify.md` | `seances/D-pilotage-vague-1/D.1-plug-ins-graphify/2026-11-10-E-plug-ins-graphify.md` |
| `docs/findings/2026-11-10-F-audit-repo.md` | `seances/D-pilotage-vague-1/D.2-audit-repo/2026-11-10-F-audit-repo.md` |
| `docs/findings/2026-11-10-G-convention-nommage.md` | `seances/D-pilotage-vague-1/D.3-convention-nommage/2026-11-10-G-convention-nommage-findings.md` |
| `docs/findings/2026-11-10-H-pilotage-vague-2.md` | `seances/H-pilotage-vague-2/2026-11-10-H-pilotage-vague-2.md` |
| `docs/findings/2026-11-10-H.1-memoire-plug-ins-graphify.html` | `seances/H-pilotage-vague-2/H.1-memoire-plug-ins-graphify/2026-11-10-H.1-memoire-plug-ins-graphify.html` |
| `docs/findings/2026-11-10-H.2-memoire-audit-repo.html` | `seances/H-pilotage-vague-2/H.2-memoire-audit-repo/2026-11-10-H.2-memoire-audit-repo.html` |
| `docs/findings/2026-11-10-I.1-memoire-cpe-pwf-engine.html` | `seances/I-pilotage-vague-3/I.1-memoire-cpe-pwf-engine/2026-11-10-I.1-memoire-cpe-pwf-engine.html` |
| `docs/findings/2026-11-10-I.2-memoire-conformite-anthropic.html` | `seances/I-pilotage-vague-3/I.2-memoire-conformite-anthropic/2026-11-10-I.2-memoire-conformite-anthropic.html` |
| `docs/findings/2026-11-11-I-pilotage-vague-3.md` | `seances/I-pilotage-vague-3/2026-11-11-I-pilotage-vague-3.md` |
| `docs/findings/2026-11-11-J-pilotage-vague-4.md` | `seances/J-pilotage-vague-4/2026-11-11-J-pilotage-vague-4-findings.md` |
| `docs/findings/2026-11-11-J.1-memoire-claire.html` | `seances/J-pilotage-vague-4/J.1-memoire-claire/2026-11-11-J.1-memoire-claire.html` |
| `docs/findings/2026-11-11-J.2-memoire-intention-janvier.html` | `seances/J-pilotage-vague-4/J.2-memoire-intention-janvier/2026-11-11-J.2-memoire-intention-janvier.html` |
| `docs/gabarits/fiche-memoire.html` | `gabarits/fiche-memoire.html` |

</details>

## Plan et tâches
Le plan de travail et les tâches dérivées vivent dans `task_plan.md` (gabarit /pwf), mis à jour par
le pilote à chaque fan-in. Ce README reste l'index des séances.

## Métriques de séance
`data/ops-ledger.csv` : 1 ligne par séance (coût, durée, contexte à la clôture…), ajoutée à la
clôture avec la commande inscrite dans `CLAUDE.md` § Outils.

Kernels de LANCEMENT (pas de clôture) : E, F écrits par C ; G, H.1, H.2 écrits par D. Parent =
celui qui fait le fan-in (D pour E, F, G ; H pour H.1, H.2), pas l'auteur du kernel.
Depuis la vague 2 : livrable = fiche mémoire HTML (`gabarits/fiche-memoire.html`) — la vague 1
a trié sans rendre la mémoire des repos (constat de D, 10/11).
Skills `/goedel` et `/debut-session` : diffs prêts dans le findings G § 6. La convention a tenu sur
la vague 2, mais on ne les applique dans `-my-claude-config` qu'après PLUSIEURS vagues rodées
(décision Yanis, 10/11).
Entre deux vagues : le pilote relit les findings et corrige le gabarit si besoin (H, 10/11 :
prévu/réel en § 5, preuve « témoignage de Yanis », puce « Proposition au pilote » en § 7 ; I, 11/11 :
voix « Yanis », témoignage brut en blockquote dans les Preuves, verdict sur le repo, fiche lisible
sans le kernel).
Depuis I (11/11, demande de Yanis) : un kernel porte le code de la séance qui s'ouvre avec lui (on
ouvre J avec le kernel J). Les contrats écrivent leur kernel de clôture dans le dossier de leur
séance ; le kernel du pilote les liste dans [Fichiers à charger], donc plus de copier-coller.

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
- **La méthode sort de l'IT tôt** (K.1, K.2) : la note « la méthode ne s'applique qu'à elle-même »
  ci-dessus est contredite par les traces : CARTE-des-richesses (18/01, 6 jours après la méthode),
  Anthropologie (10/05), voyage_voyage (04/06, une décision de vie). Applications ponctuelles, non
  outillées par claude-prostheses. Lignée de janvier = 3 étapes + 1 application (CARTE) + 1 borne vide (test-ia).
  Signe d'amélioration : la VÉRIFICATION progresse (formalisme non vérifié 10/05 → « rien d'asserté »
  04/06 → 3 juges sur les faits 27/06). Une partie de la pensée vit dans les conversations, pas les repos.
- **Piège du nom ornemental** (H2 de /fin-session) : Anthropologie (σ écrits à la main ; K.4 recalcule :
  2 axes réels, σ₁ ≈ 92 %, pas 3 ; 6 dimensions chiffrées sur 8), fin-session
  (troncateur « d'Eckart-Young » réfuté), peut-être Claire → à suivre sur la carte.
- **Circuit des audits** : `PLUG-INS/<nom>/` sur le Drive = seule maison (R13) ; vitrine
  audit-repo/Vercel redondante (H.1 Q4 + H.2 Q1, recommandation de H).
