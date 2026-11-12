# Task Plan: REPRISE NOV 2026

<!-- Gabarit /pwf (planning-with-files). Mis à jour par le PILOTE à chaque fan-in.
     Index des séances : README.md · un pilote = un dossier seances/<pilote>-<slug>/, ses contrats dedans (kernels + livrables) -->

## 🎯 Goal
Rendre à Yanis la mémoire de ses repos GitHub `tactacboomboom`, puis réinstaller l'utile dans le
setup actuel. Critère de réussite (Yanis, J, 11/11) : la mémoire est récupérée quand l'usage réel
de ses outils coïncide avec leur intention d'origine, pratique jugée par Claude (phase 4). Une fiche
n'en est pas la preuve.

## 📍 Current Phase
**Phase 1** (modulo « repos ») : vague 6 close (L.1 ; fan-in L, 12/11) ; prochaine étape : vague 7 = M.1 « où j'en étais au 23/06 » ∥ M.2 « chaîne E » (kernels écrits par L), fan-in par le pilote M.
Ordre du recouvrement de mémoire (Yanis, L, 12/11) : modulo **repos** (phases 1–2) → modulo **vault** → modulo **skills** ; aucune tâche ni projet nouveau avant.

## 🗓 Phases

### Phase 1: Vagues d'étude des repos
- [x] Vague 1 : PLUG-INS + graphify (D.1), audit-repo (D.2) : tri sans mémoire, refait en vague 2
- [x] Vague 2 : H.1 PLUG-INS + graphify (ARCHIVER) ∥ H.2 audit-repo (ARCHIVER)
- [x] Vague 3 : I.1 CPE-PWF-Engine (ARCHIVER) ∥ I.2 conformité Anthropic (ARCHIVER le repo, projet à reprendre)
- [x] Vague 4 : J.1 Claire + claire-app (ARCHIVER) ∥ J.2 cockpit-solo + De-l-Intention-a-l-Execution + chaine-intention-artefacts (ARCHIVER)
- [x] K.3 (seul, AVANT la vague 5, 12/11) : rangement par séance (`seances/<pilote>-<slug>/<Pilote.N>-<slug>/`) + repo git
  public `tactacboomboom/reprise-nov-2026` hors Drive ; Drive figé. 1er essai de la phase 4 : Yanis
  n'a pas pu décrire l'architecture Anthropic d'un dossier → écart total sur le « comment » (findings K.3)
- [x] Vague 5 (pilote K, fiche 8 sections, 12/11) : K.1 test-ia (IGNORER) + CARTE-des-richesses (ARCHIVER : 1re application
  de la méthode à un sujet extérieur) ∥ K.2 Anthropologie (RÉCUPÉRER, décision de Yanis) + projet-amelioration-fin-session
  (RÉCUPÉRER) + voyage_voyage (ARCHIVER)
  — K.4 fait (12/11, ouvert par K.2) : Anthropologie archivé en témoin documenté (README, CLAUDE.md, LICENSE, docs/ + ADR 0001),
    PR #1 mergée dans le repo étudié ; σ affichés non calculés (2 axes réels, pas 3) → `docs/limites.md` (findings K.4).
    RÉCUPÉRER s'y réduit à « récupérer la mémoire », pas reprendre l'étude (F4 de K.4)
- [x] Vague 6 (pilote L) : L.1 claude-prostheses SEUL (fin de la lignée, le plus gros morceau ; Yanis, 11/11)
  — L.1 fait (12/11, partiel, 87 %) : RÉCUPÉRER (ops_ledger.py vivant ; goedel, debut-session, fin-session nés ici).
    Repo « synthèse » de 6 sous-projets ; E (chaîne MRD → Code) a absorbé le reste, structure finie, verrouillage non
    (arrêt : voyage du 01/07). 4 contrats proposés (findings L.1 F9) ; fan-in L (12/11) : fiche conforme, Claire = ancien
    nom de claude-prostheses (DEC-16), ledger ANTÉRIEUR à `metrics/sessions.csv` (findings L)
- [ ] Vague 7 (pilote M) : M.1 « où j'en étais au 23/06 » (sous-projet E : statut de chaque gabarit, kernel AZ, SRD) ∥
  M.2 « la chaîne E » (nilpotence, ponçage, forges, R-gate) — kernels écrits par L (12/11)
- [ ] Vague 8 (pilote N) : N.1 « rôles + Scrum » (sous-projets B, C) ∥ N.2 « RAG + vision » (docs/vision, `7880faf`, `115af31`)
  — kernels à écrire par M. Les 4 contrats de L.1 AVANT la fin du modulo (Yanis, L)
- `-my-claude-config` : config actuelle, pas un souvenir → modulo **skills** (Yanis, L, 12/11), pas de contrat dans le modulo repos
- **Status:** in_progress

### Phase 2: Convergence (= fin du modulo « repos » : quelques séances de mise au point, conclusion, heuristiques ; à définir après la vague 8)
- [ ] Lire toutes les fiches et les notes « Pour la convergence » (README)
- [ ] Cartographier les 18 repos `tactacboomboom` : les liens entre les prothèses (lignée janvier → CPE → Claire → claude-prostheses)
- [ ] Proposer le tri / classement / rangement / organisation des repos (archived, privé, supprimé…)
- [ ] Décider quoi réinstaller
- **Status:** pending

### Phase 3: Prochain modulo (tâches dérivées des fiches)
Aucune de ces tâches n'est lancée avant la fin des phases 1 et 2.

Séances à créer :
- [ ] 1. **« Le comment d'Anthropic »** : réapprendre par cœur les 11 buckets (CAPABILITIES /
  ENCAPSULATIONS / TRANSVERSE) et l'anatomie d'un plugin. C'est le prérequis de 3 et 4. Source : fiche I.2 § 7.
- [ ] 2. **Re-audit upstream** de `anthropics/skills` (+26 commits) et `anthropics/claude-code` (+331)
  depuis mai, avant de construire quoi que ce soit (cookbook et quickstarts renommés, courses archivé).
  Source : clôture I.2, C1.
- [ ] 3. **« superpowers à l'aune de la matrice »** : projeter le plugin sur la grille
  11 buckets × S/SDK/M, sans installation. Source : I.2 § 7 (b).
- [ ] 4. **« Prothèses d'alirezarezvani à l'aune des buckets Anthropic »** : `alirezarezvani/claude-skills`
  (lecture seule). Projeter 2 ou 3 rôles (pm/, indie-dev/ en priorité) sur la grille, les confronter
  aux 8 règles Anthropic, les comparer aux persona-prothèses de Yanis. C'est 1 des 3 sources des
  chaînes Scrum ⑤–⑧ (`roles-documents-matrix.md:14`) ; son audit (audit-repo, recit.md:89-91) a été
  trié IGNORER par F pour le setup. Source : proposition de I.2 transmise par Yanis (11/11).
  → 3 ∥ 4 = contrats parallèles d'une même vague : les deux premiers tests de la grille comme outil
  pour juger une prothèse externe.
- [ ] 9. **Prothèse « architecte Anthropic »** (Yanis, K.3) : un agent spécialisé sur l'architecture
  recommandée par Anthropic, dont la source fait autorité = la doc officielle code.claude.com puis les
  repos `anthropics/*` (pas les synthèses de mai). Après les points 1 et 2. Carte des sources existantes :
  findings K.3 § 2. Utilisé pour la première fois en K.3 (fan-out de 2 experts).
- [ ] 10. **Chargement progressif de ce projet** (K.3, reporté par Yanis) : sortir de CLAUDE.md la
  convention fiche (l. 27-46) et le ledger vers `.claude/rules/` avec `paths: seances/**/*.html`
  (un `@import` ne réduit pas le coût). Après le point 2.
- [ ] 11. **Skill de projet `/cloture`** (K.3) : `.claude/skills/cloture/SKILL.md` dans le repo ; enchaîne
  findings → task_plan/README → /goedel → ledger → commit → push → PR. Le merge reste à Yanis (= validation).
- [ ] 12. **Status bar lue par Claude** (K.3) : le script `statusLine` de `settings.json` écrit aussi ses
  valeurs (coût, contexte, durée) dans un fichier lu par `/cloture` ; plus de copier-coller. Modifie le setup → séance dédiée.
- [ ] 13. **`progress.md` par séance** (K.3, Yanis) : le fil écrit PENDANT la séance (blocages en cours, essais
  ratés, signaux d'heuristique) ; survit à une coupure, nourrit /fin-session et les findings. Seul fichier écrit en cours de séance.
- [ ] 15. **« Le système appliqué aux projets annexes »** (Yanis, K.1, 12/11) : Yanis applique son système en
  bootstrap, sans attendre qu'il soit fini, et pense y voir s'améliorer sa manière de travailler. Corpus : CARTE-des-richesses
  (01/2026), `G:\Mon Drive\10 - Claude\C1-PERSO\PARIS-MONGOLIE\` (06/2026, PWF), voyage_voyage (K.2), autres projets à lister
  par Yanis. Même grille pour tous : Goal ? backlog ≤ 5 ? DoD binaire VÉRIFIÉE ? juge extérieur ? non-goals ? mémoire sur
  disque ? livré / abandonné ? Croise la phase 4. Source : fiche K.1 § 8. Ajout K.2 : corpus + Anthropologie ;
  critère simple = l'évolution de la VÉRIFICATION (10/05 formalisme non vérifié → 04/06 « rien d'asserté » →
  27/06 3 juges sur les faits). Patron réutilisable : `mongolie-atlas/docs/QUALITY-REPORT.md` (fiche K.2 § 8).
- [ ] 16. **Phase vault après les repos** (K.2) : superposer, datés, les repos et les conversations découpées par
  /n1n4 (claude.ai, Meta AI, ChatGPT) ; une partie de la pensée n'est pas dans les repos (conversation SVD du
  22/04, 18 jours avant Anthropologie). Hypothèse à tester : la superposition rend l'état d'esprit d'avant le départ.
  Au démarrage : passe heuristiques du modulo « contrats repo » (D à L + convergence ; ledger, findings, KR-MISS).
- [ ] 17. **Repos du projet « cloner mon cerveau »** (n1n4 automatisé + graphify) : les repérer parmi les 18 (K.2) → convergence.
- [ ] 18. **fin-session v3** (K.2, exécution, hors reprise) : reprendre le kernel S02 du repo
  projet-amelioration-fin-session (T1 lexical, A4 dé-hardcodage des chemins `G:\`, E3 `--compress`, E4 decay).
  Décider d'abord : reprendre E3/E4 ou les abandonner (question ouverte de la fiche K.2).
  (Le point K.2 (e), ops-ledger ← `metrics/sessions.csv`, est confié à L.1.)
- [ ] 19. **Privatiser les repos `tactacboomboom`** (Yanis, L, 12/11) : « ça devient sensible » (la fiche L.1, publique, cite
  forfait, voyage, coûts, témoignages). À faire à la FIN du modulo (reprise-nov-2026 inclus ?, à confirmer par Yanis).
- [ ] 20. **Essai d'usage de claude-prostheses sur un projet annexe** (proposé par L.1 F8/F9) : « pas un petit morceau »
  (Yanis, L) → APRÈS les modulos repos, vault, skills ; c'est un projet, pas un contrat de mémoire.

Décisions en attente :
- [ ] 5. **Les 8 règles Anthropic** (fiche I.2 § 7) : où les ranger, dans la graine de
  `SKILLS\architecture-anthropic\` ou dans une annexe de `G:\Mon Drive\10 - Claude\TRANSVERS\gouvernance-regles.md` ? Une seule a été
  revérifiée le 11/11 ; à trancher après le point 2. Premier cas d'application : l'en-tête de `/pwf`
  porte `type`, `version`, `allowed-tools`… au lieu de `name` + `description` seuls (relevé par I, 11/11).
- [ ] 6. **archi-mao** (`SKILLS/architecture-multi-agent-orchestration`, 20/05) : en-tête non conforme
  (R4), absent du local (R10). Le mettre en conformité puis l'activer, ou le laisser dormir ?
- [ ] 7. **Juges R-gate = persona-prothèses** : la vision de Yanis relève du travail de la séance B
  (`seances/B-debut-session/2026-11-09-B-debut-session-r-gate.md`), à y rattacher.
  L.1 : R-gate né dans claude-prostheses le 03/06 ; `c717e16` « Reviewer = Scrum Master via R-gate » (findings L.1 F6).
- [ ] 8. **Dossiers du vault Clear Sky et SaaS-Traduction** (`vault/protocole/CPE/sources/`, 21 et 15
  fichiers) : les sources primaires de CPE, plus complètes que le repo. Faut-il les lire ?
- **Status:** pending

### Phase 4: Pratique jugée (preuve de la récupération)
- [ ] Yanis applique ses outils (/cpe-sprint, /pwf, prothèses…) sur un vrai projet, Claude juge
  l'écart entre l'usage réel et l'intention d'origine (fiches § 2 et § 6 « Prévu / Réel »)
- [ ] Répéter jusqu'à coïncidence ; candidat naturel : REPRISE NOV 2026 lui-même (proposition J.1 (d))
- **Status:** pending

---
## 🛠 Decisions Made
| Décision | Rationnel |
| :--- | :--- |
| Livrable des contrats = fiche mémoire HTML (D, 10/11) | La vague 1 a trié sans rendre la mémoire des repos |
| Diffs `/goedel` et `/debut-session` (findings G § 6) appliqués seulement après plusieurs vagues rodées (Yanis, 10/11) | Roder la convention avant de toucher les skills |
| claude-mem non réinstallé (Yanis, H.1) | Choix de Yanis ; le tri « RÉCUPÉRER claude-mem » de F/H.2 est périmé |
| Vague 4 = J.1 Claire + claire-app ∥ J.2 trois repos de janvier (Yanis, 11/11) | Lots par lignée : descendants et ancêtres de CPE (fiche I.1) |
| Un kernel porte le code de la séance qui s'ouvre avec lui ; les clôtures des contrats vont dans un dossier dédié, depuis K.3 le dossier de leur séance (Yanis, 11/11) | Ouvrir J avec le kernel J, sans copier-coller les kernels des contrats |
| Gabarit : voix « Yanis », témoignage brut en blockquote, verdict sur le repo, fiche lisible sans le kernel (I, 11/11) | Écarts constatés entre les fiches I.1 et I.2 |
| Finir les vagues d'étude des repos puis la convergence avant toute tâche dérivée (Yanis, 11/11) | Éviter que les tâches s'accumulent pendant l'étude |
| Les tâches vivent dans `task_plan.md`, pas dans le README (Yanis, 11/11) | README = index ; règle Anthropic n° 6 (I.2) : liste de tâches dédiée + passation sur disque |
| Gabarit à 8 sections : nouvelle § 4 « Évolution de la pensée » (Yanis, J, 11/11) | Le schéma d'évolution de J.2 est le cœur de la reprise ; J.1 et J.2 le rangeaient à deux endroits |
| Vague 5 = passe complète des petits repos restants, puis vague 6 = claude-prostheses seul (Yanis, J, 11/11) | Finir par le plus gros morceau ; avoir tous les repos pour la carte et le rangement |
| Exception à « vagues d'abord » : K.3 architecture + migration avant la vague 5 ; repo git dédié au dossier « bientôt », pas maintenant (Yanis, J, 11/11) | Migrer à 41 fichiers coûte moins qu'à 55 ; reprendre ses automatismes commit/PR |
| Récupération de la mémoire = pratique jugée, pas une fiche (Yanis, J, 11/11) | « Un jugement sur ma mémoire n'est pas une preuve de sa récupération » |
| Rangement par séance, contrats imbriqués dans leur pilote `seances/<pilote>-<slug>/<Pilote.N>-<slug>/`, noms de fichiers inchangés (Yanis, K.3, 12/11) | Un contrat = 1 dossier au lieu de 3 ; imbriqué pour rester lisible quand les séances se multiplient (Yanis) ; aide surtout l'humain (Claude ne lit pas un sous-dossier tout seul : expert Anthropic) ; modèle « package » de Google/Bazel |
| Repo git créé MAINTENANT (lève D3 de K.3) : `C:\Users\bensa\00_MES-PROJETS\reprise-nov-2026`, public, Drive figé + note (Yanis, K.3, 12/11) | « Quitte à faire le travail, autant bien le faire maintenant » ; `git mv` garde la trace des déplacements |
| PR faites par Claude à la demande de Yanis ; la première fusion se fait ensemble (Yanis, K.3) | Projet solo : pas de CODEOWNERS, cycle ticket → PR → merge léger |
| Préparation git : `.gitattributes` (LF) fait ; modèle de PR et convention de commits `<code>: <verbe> …` à décider plus tard (K.3) | Sans sur-ingénierie pour un solo (spécialiste GAFAM) |
| L'état (en cours / clos) vit dans le README § En cours, jamais dans les chemins ; pas de `_OLD` avant la convergence (Yanis, K.3) | Un chemin qui change à chaque fan-in casse les kernels qui citent les fiches passées |
| Exception « lecture seule » pour Anthropologie : RÉCUPÉRER = archiver en témoin documenté (mémoire K.2, sources, limites), pas reprendre l'étude ; commit/PR/merge faits dans le repo étudié (Yanis, K.4, 12/11) | « Ce projet est dépassé » ; un repo fini doit expliquer seul sa raison d'être |
| Contrats parallèles = un worktree git chacun (`../reprise-nov-2026-<code>`), nommé dans le kernel de lancement ; au démarrage, vérifier `git branch --show-current` (Yanis, K.1, 12/11) | K.1 et K.2 partageaient un dossier : le checkout de K.2 a changé la branche de K.1. « Il ne faut pas que ça se reproduise » |
| Passe heuristiques : pas séance par séance pendant les contrats repo ; UNE passe sur tout le modulo « contrats repo » au passage au vault (tâche 16) : ce qu'on a appris, quelles heuristiques en déduire ; d'ici là `--violations` omis au ledger (Yanis, K, 12/11) | Yanis sait quand la faire : le sujet actuel est sa mémoire des repos, le prochain modulo est le vault |
| Règle worktree inscrite au CLAUDE.md et au README (§ Lancer une séance) ; le pilote K l'applique lui-même (`../reprise-nov-2026-K`) (K, 12/11) | K.4 a répété l'erreur (ouvert sur la branche de K.2) : le kernel L.1 nomme son worktree |
| Vague 6 : L.1 en lecture seule sur un clone du scratchpad, jamais sur le clone vivant `00_MES-PROJETS\claude-prostheses` ; repo privé → la fiche (repo public) cite structure et décisions, pas de contenu sensible (K, 12/11) | `ops_ledger.py` y sert encore à chaque clôture ; reprise-nov-2026 est public |
| Les 4 contrats de L.1 sont faits AVANT la convergence : vague 7 (M.1 ∥ M.2) puis vague 8 (N.1 ∥ N.2) ; remplace D1 du kernel L (« convergence juste après L ») (Yanis, L, 12/11) | « Je veux d'abord terminer mon recouvrement de mémoire » ; repo trop gros pour une séance (findings L.1 F9) |
| Contrats proposés par L.1 renumérotés : un contrat porte la lettre du pilote qui fait son fan-in (L.2 → M.1, L.3 → M.2, L.4 → N.1, L.5 → N.2) (L, 12/11) | Le pilote L se clôt avant eux ; règle « Parent = la séance qui fait le fan-in » (CLAUDE.md) |
| Ordre : modulo repos → modulo vault (plusieurs contrats) → modulo skills (dont my-claude-config) ; tâches et projets (essai d'usage compris) seulement après (Yanis, L, 12/11) | Recouvrement de mémoire d'abord ; l'essai d'usage « n'est pas un petit morceau » |
| Privatiser les repos à la fin du modulo (tâche 19) ; d'ici là la fiche L.1 reste publique telle quelle (Yanis, L, 12/11) | « Ça devient sensible » |

## 🚨 Errors Encountered
| Error | Attempt | Resolution |
| :--- | :--- | :--- |
| `grep -ril` avec plusieurs `-e` ou `-F` : 0 résultat sans erreur (faux négatif, É-I2-1) | I.2 | Chercher terme par terme et tester d'abord un terme connu (inscrit dans les kernels J.1/J.2) |
| Violation H1 : « persona = plugin = sous-agent » proposé sans tester les axes | I.2 | Corrigé dans la fiche I.2 § 4 à la clôture |
| `grep` de Git Bash « Aborted » sur le Drive (même avec `LC_ALL=C`) : tout sort faux négatif | J | Utiliser l'outil Grep intégré ; toujours tester un terme connu d'abord |
| Clôture J.2 à 80 % du contexte (KR-MISS) : lot de 3 repos + schéma riche | J.2 | Lots plus petits ; vague 5 : ≤ 3 petits repos par contrat |
| `git mv` : « destination exists » pour G et J (kernel et findings de même nom) | K.3 | Findings suffixés `-findings` ; règle ajoutée au CLAUDE.md |
| `sed` + chemins Windows (`\U`, `\0` interprétés) : 3 remplacements refusés ; `python -I` ignore `PYTHONIOENCODING` | K.3 | Remplacements par script Python (`str.replace`) lancé avec `-X utf8` |
| K.1 ouvert sur sa branche, mais `git branch --show-current` = `seance/K.2-…` : K.2 a fait un checkout dans le même dossier | K.1 | Détecté par /debut-session avant toute écriture ; `git worktree add ../reprise-nov-2026-K1` ; mémoire projet + décision ci-dessus |
| K.4 ouvert dans le dossier partagé, sur la branche de K.2 (kernel sans worktree nommé) | K.4 | Rien écrit avant `git worktree add ../reprise-nov-2026-K.4` ; le kernel de lancement doit nommer le worktree |
| `numpy` absent : SVD impossible en une ligne ; contrôle de liens par regex `[^)h#]` qui excluait tout lien contenant « h » (faux négatif silencieux) | K.4 | SVD en Python standard (Jacobi) ; lien vérifié à la main ; tester le filtre sur un cas connu |
| L.1 : budget dépassé (77 % → 87 %), fiche écrite sans relevé de status bar | L.1 | Fiche `partiel` ; demander la status bar avant la fiche, découper en contrats dès 70 % |
| PR #8 (L.1) fusionnée AVANT le contrôle « contenu sensible » que le kernel L confiait au pilote (C2) | L | Relu après coup : aucun secret ; éléments personnels acceptés par Yanis → tâche 19. Pour M.1/M.2 : contrôle par le contrat lui-même avant commit |
| `/debut-session` lancé sur la CLÔTURE de L.1 au lieu du kernel d'ouverture de L : lieu (worktree) et [Fichiers à charger] absents du brief | L | Kernel L trouvé dans `seances/L-pilotage-vague-6/` et appliqué ; ouvrir un pilote avec SON kernel |
