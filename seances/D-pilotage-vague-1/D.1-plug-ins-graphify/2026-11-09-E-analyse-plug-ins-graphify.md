--- KERNEL /goedel · 2026-11-09 · REPRISE NOV 2026 · séance E (vague 1, ∥ F) ---

[Contexte]
Reprise après réinstallation du Custom PC. Analyse des repos `tactacboomboom`, en vagues de 2.
Séance E = vague 1, en parallèle de la séance F (audit-repo). Type : Exploration.
Ouvrir la séance dans `G:\Mon Drive\10 - Claude\TRANSVERS\REPRISE NOV 2026` (charge le CLAUDE.md).

[Décisions]
D1 : Lecture seule, clone dans le scratchpad (CLAUDE.md § Règles).
D2 : Grille d'analyse commune en 5 sections (CLAUDE.md § Conventions) — elle sert de grille de jugement.
D3 : Séance E écrit UN SEUL fichier : `docs/findings/<date du jour>-E-plug-ins-graphify.md`.

[Contraintes]
C1 : Démarrage léger : brief puis « ok » ; budget ≤ 70 % (status bar).
C2 : Aucune installation : on recommande, Yanis décide en convergence.
C3 : Serveur MCP graphify en échec de connexion au 09/11 — c'est un objet d'analyse, pas un outil.

[Fichiers à charger]
- `docs/findings/2026-11-09-C-architecture-des-skills.md` (sections 2 et 3 seulement)

[Action]
Analyser comme UN lot (même sujet : plugins et graphify) :
1. `tactacboomboom/PLUG-INS` (configs claude-mem + graphify, CLAUDE.md, MEMORY.md)
2. `tactacboomboom/-graphify-transformer` (transformer.py + tests)
Répondre en priorité : comment réinstaller claude-mem et graphify proprement (sans symlink, R11) ?
Pourquoi le serveur MCP graphify échoue-t-il (`TRANSVERS/.claude/settings.local.json` l'active) ?

[Ouvert]
Q1 : Lien entre le repo PLUG-INS et le dossier Drive `G:\Mon Drive\10 - Claude\PLUG-INS` — doublon ?
Q2 : `~/.claude/plugins` pointe vers un dossier Drive inexistant (finding C-3) : quelle cible ?
---
