# FINDINGS — Séance du 9 novembre 2026 (TRANSVERS · reconstruction de /debut-session)

> Journal des découvertes de la séance, complément du kernel /goedel du même jour : le kernel dit QUOI faire ensuite, ce fichier garde le POURQUOI et les preuves.
> Format : `F-n — énoncé — preuve — confiance`. Ne jamais supprimer ; corriger en ajoutant.

---

## A. Findings substantiels

**F1 — /debut-session avait été perdu parce qu'il n'était jamais passé par git.**
Installé directement dans `~/.claude/skills/` sur l'ancien PC (plan Sprint 6), jamais commité dans `claude-prostheses` ni dans `-my-claude-config`. Seule source survivante : le plan `claude-prostheses/docs/superpowers/plans/2026-05-28-sprint6-goedel-debut-session.md:539-617`.
*Preuve :* `git log --all -- '*debut-session*'` ne renvoie que le commit du plan (7dd7aba) ; aucune copie sur GitHub, Drive `SKILLS\` ni `~/.claude/backups` (3 juges indépendants). *Confiance : certaine.*
*Leçon :* confirme la décision « un skill n'a qu'une seule maison » → tout skill global passe par `-my-claude-config` AVANT d'être copié dans `~/.claude/skills/`.

**F2 — Le R-gate à 3 juges a réfuté les 3 « améliorations » que j'avais inventées pour la v2.**
- Motif `kernel*.md` : 0 correspondance sur les 92 kernels de `claude-prostheses` (nommés `AAAA-MM-JJ-…md`) ; jusqu'à 11 kernels le même jour.
- Plafond « 3 lectures max » : contredit l'usage (le kernel P en prescrivait 7) ET la règle réelle « le skill ne lit QUE le kernel » (`docs/pipeline/session-protocol.md:21,54`).
- Seuil 70 % fixe : le budget venait du kernel (70 %, 75 %, « dès 50 % en fan-out »).
*Preuve :* rapports des juges Git / Usage / Vault+GitHub, convergents sans se voir. *Confiance : élevée.*

**F3 — Méta : l'agent prolonge le style de Yanis et produit des ajouts plausibles mais non fondés.**
Même mécanisme que le F7 de juin (`projet-amelioration-fin-session/sprint/findings.md`) : une proposition structurée paraît solide en contexte solo ; l'altérité externe (juges froids) l'attrape. Le R-gate reste utile même pour un petit skill de 76 lignes.
*Confiance : élevée.*

**F4 — Dans l'usage réel, c'est le KERNEL qui pilotait la séance, pas le skill.**
Lectures, budget, lieu (worktree/branche), heure de début, attente du « ok » étaient portés par la contrainte C2 « démarrage léger » des kernels. La v1 du skill démarrait trop tôt et c'est le kernel qui l'a corrigée (`docs/findings/2026-06-04-P-recap-poncage-checklist-verdict-skill.md:88-89`). La v3 inscrit ces règles dans le skill.
*Confiance : élevée.*

**F5 — Les 3 artefacts de clôture ont des rôles distincts.**
Kernel (/goedel) = l'avant, < 300 mots, remplacé à chaque séance · Findings = l'arrière (pourquoi + preuves), cumulatif, lu sélectivement · Heuristiques (/fin-session) = règles « si X → faire Y » trans-séances.
/fin-session : 1,5–2 $ par run → 0,34 $ en ne relisant plus la transcription ; projet d'amélioration arrêté à E3/E4 (compression + decay non construits).
*Preuve :* `tactacboomboom/projet-amelioration-fin-session` (README, sprint/findings.md). *Confiance : élevée.*

**F6 — La chaîne MRD→BRD→PRD→SRD→Code est forgée jusqu'au terminus, mais n'a encore servi aucun vrai projet.**
Kernel AZ du 23/06 : gabarits des 5 étages en place, Code `en-poncage`, « instance inexistante ». Rejoint le F1 du bilan (réussite sur le cadrage, pas encore sur la validation de la valeur).
*Preuve :* `claude-prostheses/docs/kernels/2026-06-23-AZ-cloture-cycle-code.md`. *Confiance : élevée.*

## B. Findings d'environnement

**F7 — Deux conventions de nommage des kernels coexistent.**
`claude-prostheses/docs/kernels/AAAA-MM-JJ-<code>-<slug>.md` et `TRANSVERS/kernel-AAAA-MM-JJ-<slug>.md`. La v3 de /debut-session gère les deux (date lue dans le nom, liste de tous les kernels du jour le plus récent).
*Confiance : certaine.*

**F8 — `skill-lint.py` ne vérifie que `claude-prostheses/.claude/skills/`.**
Pour valider un skill global, il a fallu importer sa fonction `validate_skill(Path)`. Candidat : paramétrer le dossier avant de réutiliser le validateur ailleurs.
*Confiance : certaine.*

**F9 — Le serveur MCP graphify n'a pas réussi à se connecter dans cette séance** (CONNECTION_CLOSED). À vérifier avant toute analyse du vault qui en dépendrait.
*Confiance : certaine (observé une fois).*

## C. Livrables de la séance

- `/debut-session` v3 : `-my-claude-config/skills/debut-session/SKILL.md` + copie `~/.claude/skills/debut-session/` ; skill-lint OK ; PR #2 fusionnée (commit de fusion 86896ab).
- Branche `ajout-debut-session` conservée en local et sur GitHub (suppression non demandée).

## D. Métrique de séance

31 min · 65 % de contexte à la clôture (< 70 %, KR-OK) · 4,78 $. Le seuil a été respecté, contrairement à la séance précédente (80 %).

---

*Findings figés au 09/11/2026. Toute séance future peut les falsifier — c'est leur rôle.*
