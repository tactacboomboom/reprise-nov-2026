# REPRISE NOV 2026
Reprise après réinstallation du Custom PC (09/11/2026) : analyser les repos GitHub
`tactacboomboom` pour récupérer l'utile dans le setup actuel. Séances parallèles en vagues de 2,
pilotées par kernels. Index des séances : `README.md`.
- `task_plan.md` : le plan (phases, tâches dérivées, décisions ; gabarit /pwf), mis à jour par le
  pilote à chaque fan-in ; jamais de tâches dans le README
- `seances/<code>-<slug>/` : UN dossier par séance (depuis K.3, 12/11), à plat. Il contient le
  kernel d'OUVERTURE (`AAAA-MM-JJ-<code>-<slug>.md`, code = celui de la séance qui s'ouvre avec :
  lettre du pilote ou `Pilote.N` — voir § Nommage des séances), le livrable (fiche mémoire HTML
  `AAAA-MM-JJ-<code>-<slug>.html` depuis la vague 2 ; findings `.md` avant et pour les pilotes) et,
  pour un contrat, son kernel de CLÔTURE `AAAA-MM-JJ-<Pilote.N>-cloture.md`. Un fichier va dans le
  dossier du code écrit dans son nom (E, F, G → D.1, D.2, D.3). Même nom kernel/findings → suffixe `-findings`
- `gabarits/fiche-memoire.html` : le modèle de fiche, fixé avant la vague 2
- Règles de rangement : `G:\Mon Drive\10 - Claude\TRANSVERS\gouvernance-regles.md` (R1–R13)

## Règles
- Une séance = un kernel = un repo (ou un lot nommé). Rien hors de ce périmètre.
- Repos en LECTURE SEULE : `gh repo clone <repo> <scratchpad>/<nom>` — clone COMPLET (pas de
  `--depth 1` : l'historique des commits est la matière première). Jamais de clone ni de git dans
  le Drive (R3). Aucun push, aucune issue, aucune PR sur les repos ÉTUDIÉS.
- Ce dossier est le repo git `tactacboomboom/reprise-nov-2026` (public, depuis K.3). Le dossier
  `REPRISE NOV 2026` du Drive est FIGÉ au 12/11. Une séance travaille sur une branche
  `seance/<code>-<slug>` ; commit et PR seulement à la demande de Yanis ; merge = Yanis (ou sur sa demande).
- Un contrat écrit DEUX fichiers dans son dossier `seances/<code>-<slug>/` : sa fiche mémoire HTML
  et, à la clôture, son kernel /goedel (plus de kernel collé dans le chat). Ne jamais modifier les fichiers d'une
  autre séance, ni le README, ni `task_plan.md`, ni ce CLAUDE.md, ni le gabarit (réservés au pilote).
- Budget : ≤ 70 % mesuré sur la status bar. Au-delà : écrire la fiche telle quelle, statut `partiel`.
- Aucune installation ni modification du setup (~/.claude, settings, plugins) : on RECOMMANDE.

## Conventions — fiche mémoire (fixée AVANT les séances, sert de grille de jugement)
But : rendre à Yanis la MÉMOIRE du repo (pourquoi il l'a fait, comment il vivait dans son
arsenal), puis le trier. Copier `gabarits/fiche-memoire.html` et remplir ses 8 sections,
sans en ajouter, retirer ni réordonner (8 depuis J, 11/11 ; fiches A–J : 7 sections) :
1. **Déclencheur** · 2. **Objectif** · 3. **Frise des commits** (TOUS, en 2–5 phases : quoi →
pourquoi → bénéfice) · 4. **Évolution de la pensée** (étapes en schéma, difficulté → réponse →
suite, ce que les traces ajoutent au souvenir ; modèle : fiche J.2 § 4) · 5. **Place dans
l'arsenal** · 6. **Ce qui déclenchait l'usage** · 7. **Où je me suis arrêté** · 8. **Tri et
questions** (verdict RÉCUPÉRER / ARCHIVER / IGNORER, réutilisable → chemin, conflits gouvernance,
à confirmer par Yanis, pour la convergence).
- Une fiche n'est pas la preuve que la mémoire est revenue : la preuve sera la pratique jugée
  (phase 4 de `task_plan.md`). Le § 6 « Prévu / Réel » prépare cette comparaison.
- Sources : `git log` complet (`--stat` si utile), README/CLAUDE.md du repo, skills et settings
  qui l'appelaient, notes du vault, findings des autres séances.
- Langage simple. Chaque affirmation renvoie à une preuve [n] (commande, fichier:ligne, hash) avec
  sa confiance (certaine / élevée / moyenne). Rien trouvé → « à confirmer par Yanis », jamais inventé.
- Conflits gouvernance : lire `G:\Mon Drive\10 - Claude\TRANSVERS\gouvernance-regles.md` AVANT de citer une règle.
- Chiffres du kernel de lancement (taille, contenu) = hypothèses à vérifier, pas des faits.
- Séances hors repo (pilote, méthode — ex. G) : findings `.md`, format fixé par leur kernel.
- En-tête de la fiche : séance, parent, date, statut (complet / partiel / échoué).

## Nommage des séances (fan-out / fan-in, fixé par G = D.3)
- Pilote = 1 lettre, chronologique, jamais réutilisée (A–J grillées → prochain pilote K).
- Un kernel porte le code de la séance qui S'OUVRE avec lui (règle de I, 11/11). La clôture d'un
  pilote = le kernel d'ouverture du pilote suivant : I écrit `…-J-pilotage-vague-4.md`
  (`code : J · parent : I · type : lancement`). Ce kernel liste dans [Fichiers à charger] les
  clôtures `seances/J.N-<slug>/…-J.N-cloture.md` et les fiches des contrats : `/debut-session`
  les lit sans copier-coller. (Exception historique : I s'est ouvert avec le kernel nommé H.)
- Contrat parallèle = `Pilote.N` (D.1, D.2…), N jamais réutilisé. Pas de sous-contrat (D.1.1).
- Parent = la séance qui fait le fan-in (pas forcément l'auteur du kernel).
- Fan-in : le pilote ne clôt pas avant d'avoir la fiche ET le kernel de clôture de CHAQUE contrat
  (`échoué` compte).
- Tout kernel commence par :
  `[Lignée] code : … · parent : … · type : lancement|clôture · contrats : … [· relance de : …]`
- Contrat échoué → findings `statut : échoué` ; relance = nouveau numéro.
- Fichiers A–G non renommés : correspondance E = D.1, F = D.2, G = D.3 (README).

## Outils
- `gh repo view` / `gh repo clone` / `gh api repos/<repo>/commits` / `git log` (lecture)
- Bash (Git Bash) pour lire ; Write pour la fiche (pas `Set-Content -Encoding utf8` : BOM, F-X4)
- **Clôture = /goedel PUIS 1 ligne au ledger** `data/ops-ledger.csv` (status bar collée par Yanis) :
  `python C:\Users\bensa\00_MES-PROJETS\claude-prostheses\scripts\ops_ledger.py append --bar "<status bar>"`
  `--seance <lettre> --date <AAAA-MM-JJ> --phase reprise --measure-point avant_queue --ctx-close <ctx %>`
  `--csv data/ops-ledger.csv --mirror ""` — `--mirror ""` OBLIGATOIRE (sinon écrase le CSV C3-PRODUIT).
  `--violations` seulement après une vraie passe heuristiques, sinon l'omettre (jamais « 0 » par défaut).
