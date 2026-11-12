---
seance: K
parent: J
date: 2026-11-12
type: pilote 5 · fan-in de la vague 5 (Exploration)
statut: complet (fan-in K.3, K.1, K.2, K.4)
lieu: worktree ../reprise-nov-2026-K, branche seance/K-pilotage-vague-5 (depuis origin/main 21594b8)
---

# K — Fan-in de la vague 5

En une phrase : la vague 5 a fini les petits repos ; elle montre que la méthode de Yanis est sortie
de l'informatique beaucoup plus tôt qu'on ne le croyait, et prépare L.1 (claude-prostheses).

## 0. Lieu (contrôle de démarrage)

Le dossier principal était sur `seance/K.2-memoire-mai-juin` (déjà fusionnée, PR #4) et `main` local
en retard sur `origin/main`. K.4 tournant en parallèle (Yanis), le pilote n'a fait AUCUN `git switch`
dans le dossier partagé : worktree `../reprise-nov-2026-K` créé depuis `origin/main`. C'est la règle
née de l'incident K.1/K.2, appliquée une première fois par un pilote ; inscrite au CLAUDE.md et au README.

## 1. Jugement de K.3 (architecture + migration)

- **Migration : complète.** Contrôle par script (chemins `seances/`, `gabarits/`, `data/`, `docs/`
  cités dans CLAUDE.md, README, task_plan, gabarit et kernels de K) : 44 chemins introuvables, tous
  attendus → 38 = colonne « ancien » de la table du README (38/38 lignes ont un nouveau chemin qui
  existe), 3 dans le kernel K.3 figé (non modifié, C2 de K.3), 3 modèles (`J.N-`, `K.N-`, `L-`).
  **0 chemin mort réel.** Confiance : certaine.
- **Pratique jugée (1er essai phase 4) : verdict confirmé, « écart total » sur le « comment ».**
  Réponse de Yanis : « J'ai pas e témoignage. » Intention du repo Architecture-des-skills-Anthropic
  (savoir ranger un dossier pour Claude) ↔ compréhension actuelle = nulle sur la mécanique. Limite
  du test : une seule question ouverte, sans support → il mesure l'absence, pas ce qui manque.
  Prochain essai utile seulement après la tâche 1 (« Le comment d'Anthropic »), avec une question
  fermée (ex. : où Claude cherche-t-il les skills d'un projet ?). Confiance : élevée.
- Correction utile de K.3 : le rangement par séance aide l'humain, pas les tokens ; le levier tokens
  est `.claude/rules/` + `paths` (tâche 10).

## 2. Jugement des fiches K.1 et K.2

| Critère (gabarit, CLAUDE.md) | K.1 | K.2 |
|---|---|---|
| 8 sections, ordre respecté | ✓ | ✓ |
| Aucun `{{…}}` restant | ✓ | ✓ |
| Toutes les refs [n] → une preuve | ✓ (23) | ✓ (20) |
| Voix « Yanis » (les « tu » sont tous dans des citations) | ✓ | ✓ |
| Témoignages bruts en blockquote | ✓ (2) | ✓ (6) |
| Liens interprétés signalés comme tels | ✓ | ✓ |
| Statut | complet | complet |

**Liens de la lignée (janvier → CPE → Claire → claude-prostheses).**
- K.1 : relie janvier → CPE (CARTE → Clear Sky → CPE-PWF-Engine → cpe-sprint). Liens signalés
  « interprétés par Claude », confiance moyenne : correct.
- K.2 : relie Claire (fmath/décodeur début mai) → projets annexes. Ne nomme pas CPE : normal pour
  mai–juin. Le lien vers claude-prostheses est négatif et utile : les projets annexes NE sont PAS
  outillés par claude-prostheses.
- Écart avec le README : la note « la méthode ne s'applique qu'à elle-même » (J.2) est contredite
  par CARTE (18/01), Anthropologie (10/05), voyage_voyage (04/06). Note corrigée au README.

**Défauts relevés** (mineurs, fiches non modifiées : elles appartiennent à leur séance) :
- K.2 : verdict Anthropologie changé par Yanis (ARCHIVER → RÉCUPÉRER), correctement tracé, mais le
  verdict porte sur la suite du PROJET (rendre le repo pro) plus que sur le repo : règle du gabarit
  « Verdict = sur le REPO seul ». À trancher à la convergence, pas un rejet.
- K.2 : H5 violée (hypothèse non marquée comme pari), KR-MISS à 76 %. K.1 : 66 %, KR-OK.
- K.1 : 7 questions « à confirmer par Yanis », K.2 : 4 → à grouper pour la convergence.

**Question ouverte du kernel K, Q1 : voyage_voyage = premier projet extérieur outillé ?** Non : le
premier projet extérieur est CARTE-des-richesses (18/01, confirmé par Yanis en K.1). voyage_voyage
est la première DÉCISION DE VIE servie par la méthode (04/06). Aucun des deux n'est « outillé » par
claude-prostheses. Q2 (repos publics avec e-mail) : reste pour la convergence.

## 3. Ce que le pilote a écrit

- Kernel `seances/L-pilotage-vague-6/L.1-memoire-claude-prostheses/2026-11-12-L.1-memoire-claude-prostheses.md`.
  Mesures (12/11) : PRIVÉ, 2,3 Mo, 369 commits (232 mai, 136 juin, 1 le 09/11), 18 branches, 612
  fichiers, 10 dossiers de sprint. Repo VIVANT (`ops_ledger.py` sert à chaque clôture) → clone du
  scratchpad, jamais le clone vivant. Ordre de lecture borné par le budget.
- `task_plan.md` : vague 5 cochée, tâche 15 enrichie (critère K.2), tâches 16–18 (phase vault,
  « cloner mon cerveau », fin-session v3) ; numéro 14 laissé à la branche `chore/tache-14-branche-auto`.
  Trois décisions ajoutées.
- README : § En cours, § Lancer une séance (worktree), lignes K, K.1–K.4, L.1, deux notes de convergence.
- CLAUDE.md : règle « un worktree par séance parallèle » (demande de K.1).

## 4. Jugement de K.4 (clos pendant le fan-in, lu sur `origin/main` f3e42a6)

- **Livré : conforme à la demande recentrée de Yanis**, pas au kernel K.4 : pas de `data/`, `src/`, CI
  ni recalcul dans la page (« projet dépassé ») ; à la place, une archive qui s'explique seule (README,
  CLAUDE.md 23 lignes, LICENSE, `docs/` genèse / sources / limites, ADR 0001). L'écart prévu / fait est
  tracé dans ses findings § 1 : correct.
- **F1 (certain) = preuve concrète de H2** : les σ affichés ne viennent d'aucun calcul ; recalculés,
  2 axes après centrage (σ₁ ≈ 92 %). Confirme l'hypothèse de K.2 (marquée « interprétation »).
- **F4 règle mon défaut relevé au § 2** : RÉCUPÉRER = récupérer la MÉMOIRE (raison d'être, sources,
  genèse), pas reprendre le projet. Le verdict reste formulé sur le projet ; la convergence tranchera
  le vocabulaire (proposition : un verdict « ARCHIVER (documenté) »).
- **Contrôles du pilote** : clôture et findings présents ; ledger K.4 ajouté (45 %, KR-OK, 0 violation) ;
  ses ajouts à `task_plan.md` (sur demande de Yanis) fusionnés avec ceux du pilote (1 conflit résolu à
  la main, ma ligne de décision Anthropologie retirée au profit de la sienne).
- **Erreur répétée** : K.4 ouvert dans le dossier partagé, sur la branche de K.2 → règle worktree
  inscrite au CLAUDE.md ; le kernel L.1 nomme son worktree.
- **Trace du travail K.4** (le worktree `../reprise-nov-2026-K.4` est supprimé le 12/11 sur accord de
  Yanis, il était propre) : le travail vit dans le repo `tactacboomboom/Anthropologie` (PR #1, merge
  `4e84f69`, repo archivé sur GitHub, `isArchived: true` vérifié le 12/11) ; côté reprise : PR #5
  (`f3e42a6`), clôture et findings dans `K.4-anthropologie-pro/`, branche `seance/K.4-anthropologie-pro`
  conservée sur `origin`.
- Ouvert de K.4 : (1) `gh repo archive` Anthropologie — d'après Yanis, fait ; (2) « conforme Anthropic »
  non vérifié contre la doc officielle → tâche 9 ; (3) Weber ↔ calvinisme = interprétation de Claude.

## 5. Pour L / la convergence

- Hypothèse pour L.1 : le 1er commit de claude-prostheses (« indie-dev, pm, dev-anthropic ») reprend
  les rôles pm/ et indie-dev/ d'alirezarezvani (tâche 4). À tester, pas un fait.
