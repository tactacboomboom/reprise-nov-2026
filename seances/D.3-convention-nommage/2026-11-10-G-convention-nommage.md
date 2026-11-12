--- KERNEL /goedel · 2026-11-10 · REPRISE NOV 2026 · lancement séance G (convention de nommage) ---

[Contexte]
Kernel de LANCEMENT écrit par D (pilote vague 1). Problème : les lettres mélangent l'ordre et la
parenté. E et F sont des contrats parallèles lancés par D, mais nommés comme une suite (C → D → E → F).
But : une convention officielle pour nommer les séances parallèles. Type : Exécution (spec +
application). Lieu : `G:\Mon Drive\10 - Claude\TRANSVERS\REPRISE NOV 2026` (pas de git, R3).

[Décisions]
D1 : S'inspirer du fan-out / fan-in des équipes IT : CI/CD (stage → jobs parallèles, `needs:`),
Jira (story → sous-tâches `.1 .2`), git (branches → merge). Choix de Yanis, 10/11.
D2 : Proposition de départ (D), améliorable : lettre = séance pilote sur la ligne principale,
chronologique ; `Lettre.N` = contrat parallèle lancé par ce pilote (E → D.1, F → D.2) ; champ
`[Lignée] parent : … · contrats : …` dans le kernel ; fan-in = le pilote attend TOUS les findings.
D3 : Aucun renommage rétroactif des fichiers A–F : une table de correspondance suffit.

[Contraintes]
C1 : Démarrage léger : brief puis « ok » ; budget ≤ 70 % (status bar).
C2 : G écrit UNIQUEMENT son findings et, après « ok » de Yanis, les 2 skills. G NE TOUCHE PAS
`README.md` ni `CLAUDE.md` : D les modifie en parallèle et reprendra le texte prêt à coller du findings.
C3 : Montrer le diff de chaque skill avant écriture, relire après.
C4 : Compatibilité avec `/debut-session` étape 1 (choix du kernel par la date dans le NOM) :
vérifier le tri et le motif `AAAA-MM-JJ-<code>-<slug>` avec un point dans le code (`D.1`).

[Fichiers à charger]
- `README.md` (tableau Séances)
- `CLAUDE.md`
- `C:\Users\bensa\.claude\skills\goedel\SKILL.md`
- `C:\Users\bensa\.claude\skills\debut-session\SKILL.md`

[Action]
1. Spécifier la convention : codes, noms des fichiers kernels/findings, `[Lignée]`, règle fan-in,
   cas limites (contrat échoué, sous-contrat `D.1.1` ?, séance hors vague comme G).
2. Table de correspondance A–G.
3. Texte prêt à coller pour `CLAUDE.md` § Conventions et le README (colonne « Parent »).
4. Diffs de `/goedel` et `/debut-session` ; appliquer après « ok » ; relire.
5. Findings `docs/findings/2026-11-10-G-convention-nommage.md` (frontmatter `repo: —`) ; clôture
   = /goedel puis ledger (`CLAUDE.md` § Outils).

[Ouvert]
Q1 : Selon la nouvelle convention, G serait D.3 (lancé depuis D). À trancher par la séance.
Q2 : Les skills ont-ils une source canonique (Drive / `-my-claude-config`) à modifier plutôt que la
copie locale `~/.claude/skills` ? (cf. Q4 du kernel C, R10/R11.)
---
