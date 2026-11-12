---
seance: F
date: 2026-11-10
repo: tactacboomboom/audit-repo
statut: complet
---

# Findings F — audit-repo (verdict de réinstallation : 4 outils)

## 1. Contenu
- Recueil de 10 audits de repos (et non 8) : 6 repos Anthropic, plus obra-superpowers, thedotmack-claude-mem,
  othmanadi-planning-with-files, alirezarezvani-claude-skills, et 2 dossiers « contexte persona »
  (`indie-dev/`, `pm/` : `*_context_T1/T2.md` + un script Python). Site statique prévu pour Vercel (`index.html`).
  *Preuve :* `find . -type f` sur le clone ; *Confiance :* certaine.
- Dernier commit : 2026-05-26, « audit #10 alirezarezvani ». Taille : 878 Ko hors `.git`
  (le kernel annonçait 264 Ko). Projet figé depuis 5,5 mois : archive de travaux, pas un outil vivant.
  *Preuve :* `git log -1`, `du -sh` ; *Confiance :* certaine.
- Le README n'est plus à jour : il annonce « 8 audits » et sa table ne liste pas claude-mem, alirezarezvani, indie-dev ni pm.
  *Preuve :* `README.md:3,15-24` ; *Confiance :* certaine.

## 2. Réutilisable — verdict par outil (priorité du kernel)

**État actuel du setup (vérifié en lecture seule) :** aucun plugin installé (`~/.claude/plugins/plugins` est vide),
aucun hook dans `settings.json`, pas de `~/.claude-mem`. Les skills maison `/recall` et `/session-restore`
appellent claude-mem : **ils sont donc cassés aujourd'hui.**
*Preuve :* `ls ~/.claude/plugins/plugins`, `grep hook settings.json` (0 résultat), `skills/recall/SKILL.md:3,19,36`,
`skills/session-restore/SKILL.md:4` ; *Confiance :* certaine.

| Outil | Verdict réinstallation | Pourquoi |
|---|---|---|
| **claude-mem** | **OUI — en priorité 1**, version épinglée (`npx claude-mem@13.3.0 install`, ou la dernière stable vérifiée) | Deux skills existants en dépendent (`/recall`, `/session-restore`). Il était déjà installé sur l'ancien PC. Score 8,6. Risque principal : le Worker Bun perd des observations sans prévenir quand il tombe → prévoir une vérification de santé (port 37777). |
| **superpowers** | **OUI, mais en sélection** (plugin épinglé v5.1.0, ou extraction de 4 skills) | Il était sur l'ancien PC, et 4 skills cités par le setup sont absents (`/brainstorm`, `/writing-plans`, `/test-driven-development`, `/verification-before-completion`, cf. findings C § 2). Risques : breaking changes tous les 4 à 6 mois, et des hooks qui peuvent disparaître sans le signaler. |
| **planning-with-files** | **NON** (le plugin d'origine) — garder `/pwf` | `/pwf` en est déjà une version allégée sans hooks (voir Q2). Les hooks d'origine coûtent environ 890k tokens par session longue (un `preToolUse` sans matcher représente à lui seul environ 750k). Seul élément à récupérer éventuellement : `session-catchup.py` (reprise de contexte à partir de la trace de session), mais il fait doublon avec claude-mem s'il est réinstallé. |
| **alirezarezvani claude-skills** | **NON en masse** — extraction ciblée plus tard | 329 skills sans filtre, beaucoup de bruit, une release environ tous les 3 jours, frontmatter hors standard. L'audit lui-même recommande d'extraire « Agile PO + PM Toolkit + Engineering » vers les personas `claude-prostheses`. Ce n'est pas du setup : c'est un chantier produit. |

*Preuves :* `thedotmack-claude-mem/verdict.md:16,37-41,88` · `obra-superpowers/verdict.md:16,37-41,84` ·
`othmanadi-planning-with-files/NOTES.md:132-143,161-176` · `alirezarezvani-claude-skills/verdict.md:22,36-37,83`.
*Confiance :* élevée pour les verdicts (scores et risques tirés des audits de mai 2026, versions à revérifier avant installation).

**Autres éléments récupérables :**
- `othmanadi-planning-with-files/NOTES.md` § 6.2 « pwf-lite » (4 hooks, environ 7k tokens par session) → n'est utile **que si**
  Yanis veut un jour réactiver des hooks pwf. Destination : `~/.claude/settings.json`. Sinon, rien à faire.
  *Preuve :* `NOTES.md:145-159` ; *Confiance :* élevée (le chiffrage vient de l'audit et n'a pas été remesuré).
- Les leçons consignées dans le fichier « fin de session 20 05 » sont déjà appliquées dans la méthode actuelle :
  séances en série ou parallèles pilotées par kernel, pas de fan-out synchrone de sous-agents. Il reste une seule leçon
  pratique : `run_in_background: true` pour tout fan-out d'agents.
  *Preuve :* `fin de session…:173-192` ; *Confiance :* élevée.
- `indie-dev/`, `pm/` : contextes de personas → ils concernent `claude-prostheses` (hors du périmètre F, non approfondis).

## 3. Conflits gouvernance
- **R10 (source canonique sur le Drive)** : le README déclare comme source `G:\Mon Drive\10 - Claude\SKILLS\architecture-anthropic\repos\`,
  mais ce dossier ne contient que les **6 audits Anthropic**. Les audits pwf, superpowers, claude-mem,
  alirezarezvani, indie-dev et pm n'existent donc **que sur GitHub** : copie unique, à l'inverse de R10/R13.
  *Preuve :* `README.md:28-29` + `ls …/architecture-anthropic/repos/` ; *Confiance :* certaine (pour le constat ;
  je n'ai pas relu le libellé exact de R10/R13 dans `gouvernance-regles.md`).
- Un fichier sans extension (« fin de session 20 05… (a supr quand lu) ») est versionné : c'est une note de session
  déposée dans un repo de déploiement. *Confiance :* élevée.
- L'hétérogénéité des formats (HTML 4 onglets pour certains dossiers, markdown seul pour d'autres) est connue
  et documentée. *Preuve :* `fin de session…:252-265`.

## 4. Verdict
**ARCHIVER** le repo (lecture de référence, aucun code à exécuter). Sur les outils qu'il audite :
**RÉCUPÉRER claude-mem** (priorité 1, il débloque `/recall` et `/session-restore`), puis **superpowers** en sélection ;
**IGNORER** planning-with-files (couvert par `/pwf`) et alirezarezvani pour le setup (à garder pour un chantier personas).

## 5. Questions pour la convergence
- **Q1 (kernel)** : le fichier « fin de session 20 05… » a été **lu**. Son contenu utile est résumé en § 2.
  Suppression **recommandée**, mais c'est une écriture dans le repo GitHub (push) : décision de Yanis, hors séance F.
- **Q2 (kernel)** : **oui, `/pwf` recoupe planning-with-files**. Il en reprend le cœur (les 3 fichiers, la règle des 2 actions,
  le protocole 3-strikes, le test de reboot) **sans aucun hook**, ce qui est le bon choix. Il manque seulement `session-catchup.py`,
  dont claude-mem couvre le rôle. *Preuve :* `~/.claude/skills/pwf/SKILL.md:12-134` (sections) ; *Confiance :* élevée.
- Q3 : réinstaller superpowers en **plugin complet** (risque de hooks invisibles, d'upgrades cassants) ou **extraire
  4 skills** dans `~/.claude/skills/` (stable, mais sans les mises à jour) ? → à croiser avec la séance E (PLUG-INS).
- Q4 : faut-il rapatrier les 6 audits absents du Drive vers `SKILLS\architecture-anthropic\repos\` (R10) ?
- Q5 : claude-mem sous Windows nécessite Bun et Git Bash. Faut-il valider la version actuelle (la v13.3.0 date de mai 2026)
  avant d'épingler ? → séance E ou convergence.

## Métrique de séance
Lectures : README, la note « fin de session », 3 `verdict.md`, `NOTES.md` pwf § 6-7, `~/.claude/skills/pwf`
(sections), `/recall` et `/session-restore` (grep). Les fichiers HTML et fmaths n'ont pas été lus (hors du besoin).
