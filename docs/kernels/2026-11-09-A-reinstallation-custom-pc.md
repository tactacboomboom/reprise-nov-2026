--- KERNEL /goedel · 2026-11-09 · retour de voyage / réinstallation du custom PC ---

[Contexte]
Yanis rentre d'environ 4 mois de voyage et a presque tout oublié de son travail. Il passe définitivement du PC portable (projets dans `C:\projects\`) au custom PC. Type de séance : Exécution. Objectif : retrouver les sources et réinstaller l'arsenal Claude Code. Il est en train de lire `G:\Mon Drive\10 - Claude\vault\analyses\bilan-retour-2026\`, en commençant par BILAN.md et PLAN.md.

[Décisions]
D1 : Les projets vont dans `C:\Users\bensa\00_MES-PROJETS\` : claude-prostheses (branche `sprint-15`) et -my-claude-config. — Raison : Yanis veut un nom explicite, et GitHub reste la source de vérité.
D2 : 17 skills perso sont installés au global dans `~/.claude/skills` (les 15 du kit, plus goedel et fin-session v2). Leur source est -my-claude-config (PR #1 fusionnée). goedel et fin-session ont été retirés de claude-prostheses, qui garde ses 12 skills Scrum en local. — Raison : un skill n'a qu'une seule maison.
D3 : Le `settings.json` et le `CLAUDE.md` du kit ne sont pas installés. Seuls ajouts : la status line (`~/.claude/statusline.ps1` + bloc `statusLine`) et l'identité Git globale. — Raison : garder les règles débutant actuelles et éviter les hooks claude-mem (incident du 31 mai).

[Contraintes]
C1 : `/recall`, `/session-restore` et `/graphify` ne marcheront pas tant que claude-mem et graphifyy ne sont pas installés. Les hooks Git de claude-prostheses ne sont pas actifs : ils ne viennent pas avec le clone.
C2 : La status line calcule le % de contexte sur 200k. Il faudra la recalibrer si la fenêtre du modèle actuel est plus grande.

[Action]
Finir la lecture du bilan. Puis écrire une page « routine de session » (ouvrir → travailler → clôturer) à partir des skills goedel et fin-session et de la section 2 de lot-3-parcours-methode.md.

[Ouvert]
Q1 : Lexique en 3 couches (environ 30 termes, à tirer de lot-3 et lot-4) : quand le démarrer ?
Q2 : Quand fusionner à la main le settings.json et le CLAUDE.md du kit et réinstaller claude-mem, et avec quelles précautions ?
Q3 : La séance s'est clôturée à 80 %, au-dessus du seuil de 70 %, après 4 h 50 sur des sujets mêlés. Il faudra découper les prochaines séances.
---
