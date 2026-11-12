--- KERNEL /goedel · 2026-11-11 · REPRISE NOV 2026 · clôture I → pilote J ---

[Lignée] code : J · parent : I · type : lancement · contrats : J.1, J.2

[Contexte]
Reprise des repos `tactacboomboom`. I a jugé la vague 3 (I.1, I.2 : ARCHIVER), corrigé le gabarit,
écrit J.1/J.2 et créé `task_plan.md`. Séance J = pilote 4 : fan-in de la vague 4. Type : Exploration.
Lieu : `G:\Mon Drive\10 - Claude\TRANSVERS\REPRISE NOV 2026` (pas de git).

[Décisions]
D1 : Un kernel porte le code de la séance qui s'ouvre avec lui ; les contrats écrivent leur clôture
dans `docs/kernels/contrats/` — Raison : demande de Yanis, plus de copier-coller.
D2 : Finir les vagues d'étude des repos, puis la convergence ; les tâches dérivées attendent en
`task_plan.md` phase 3 — Raison : décision de Yanis.
D3 : Les tâches vivent dans `task_plan.md` (gabarit /pwf), jamais dans le README — Raison : README = index.

[Contraintes]
C1 : Démarrage léger : brief puis « ok » ; budget ≤ 70 % (status bar). Le pilote ne lance rien.
C2 : Juger chaque fiche aussi sur les LIENS qu'elle révèle (lignée janvier → CPE → Claire → claude-prostheses).

[Fichiers à charger]
- `task_plan.md`
- `docs/gabarits/fiche-memoire.html`
- `docs/kernels/contrats/2026-11-11-J.1-cloture.md` et `…-J.2-cloture.md` (absents → contrat non clos : attendre)
- `docs/findings/2026-11-11-J.1-memoire-claire.html` et `…-J.2-memoire-intention-janvier.html` (§ 4 et § 7)

[Action]
1. Juger les 2 fiches (gabarit corrigé par I + « ai-je retrouvé la mémoire ? »).
2. Avec Yanis : reste-t-il des repos à étudier (`gh repo list tactacboomboom` contre le README) ?
   Oui → kernels de la vague 5 ; non → kernel de la convergence.
3. Mettre à jour `task_plan.md` et le README ; clôture = findings + /goedel + ledger.

[Ouvert]
Q1 : Violation H1 (agent, I) : correspondance PWF ↔ projet (findings ≈ fiches, progress ≈ kernels)
posée sans tester les axes ; à revoir si `task_plan.md` doublonne les kernels.
Q2 : Diffs `/goedel` et `/debut-session` (findings G § 6), plus la nouvelle règle des kernels : à appliquer après rodage.
---
