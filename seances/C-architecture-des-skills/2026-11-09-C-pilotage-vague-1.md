--- KERNEL /goedel · 2026-11-09 · REPRISE NOV 2026 · séance C → séance D (pilotage vague 1) ---

[Contexte]
Reprise après réinstallation du Custom PC. Séance C (09/11) : Architecture-des-skills analysé
(ARCHIVER), artefacts du 09/11 rangés dans `TRANSVERS\REPRISE NOV 2026\`, méthode parallèle de
claude-prostheses relue, vague 1 préparée. Séance D = pilotage de la vague 1. Type : Exploration.
Lieu : `G:\Mon Drive\10 - Claude\TRANSVERS\REPRISE NOV 2026` (pas de git, R3).

[Décisions]
D1 : Vagues de 2 séances parallèles (choix Yanis) — Raison : attention de Yanis = goulot ; gain =
qualité de contexte et apprentissage, pas le coût (claude-prostheses, findings X, Z, AA).
D2 : 1 lettre = 1 séance, chronologique ; chaque séance écrit UN SEUL findings, repos en lecture
seule clonés dans le scratchpad — Raison : séances disjointes sans git.
D3 : Grille d'analyse en 5 sections fixée dans `CLAUDE.md` AVANT les livrables ; elle sert de
grille de jugement — Raison : juge non contaminé (finding AA §3).

[Contraintes]
C1 : Démarrage léger : brief puis « ok » ; budget ≤ 70 % (status bar).
C2 : Le pilote ne lance aucune séance lui-même (aucun agent) : c'est Yanis qui ouvre les terminaux.

[Fichiers à charger]
- `README.md`

[Action]
1. Donner à Yanis ce mode d'emploi, tel quel :
   Ouvre deux terminaux et tape dans chacun :
   cd "G:\Mon Drive\10 - Claude\TRANSVERS\REPRISE NOV 2026"
   claude
   /debut-session docs/kernels/2026-11-09-E-analyse-plug-ins-graphify.md   ← terminal 1
   /debut-session docs/kernels/2026-11-09-F-analyse-audit-repo.md          ← terminal 2
2. Attendre que Yanis annonce la fin de E et F.
3. Lire les 2 findings ; juger leur conformité à la grille ; noter les défauts du gabarit.
4. Corriger le gabarit si besoin ; écrire les kernels vague 2 (CPE-PWF-Engine ∥ rag_concepts) ;
   mettre à jour le README.

[Ouvert]
Q1 : Vague 3 (Claire ∥ chaine-intention-artefacts + De-l-Intention-a-l-Execution) et séance de
convergence : kernels à écrire après la vague 2.
Q2 : Signalés, non tranchés : `bootstrap-github.ps1`, `user_setup.md`, symlink plugins (R11),
doublon `vault/matrice-generative.html` (findings C-1, C-3, C-5).
Q3 : Hérité du kernel B : réparer graphify avant le vault ; branche `ajout-debut-session` ;
lexique 3 couches ; fusion settings/claude-mem ; page « routine de session ».
Q4 : Ledger créé (`data/ops-ledger.csv`, procédure de clôture dans `CLAUDE.md`). v2 à faire
via `-my-claude-config` + juges : étape 4 de /goedel pour tout projet ayant `data/ops-ledger.csv`,
et corriger le chemin des heuristiques (`vault/3 - PERSONNEL/`, avec espaces) — findings C, É-C6.
---
