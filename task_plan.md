# Task Plan: REPRISE NOV 2026

<!-- Gabarit /pwf (planning-with-files). Mis à jour par le PILOTE à chaque fan-in.
     Index des séances : README.md · une séance = un dossier seances/<code>-<slug>/ (kernels + livrables) -->

## 🎯 Goal
Rendre à Yanis la mémoire de ses repos GitHub `tactacboomboom`, puis réinstaller l'utile dans le
setup actuel. Critère de réussite (Yanis, J, 11/11) : la mémoire est récupérée quand l'usage réel
de ses outils coïncide avec leur intention d'origine, pratique jugée par Claude (phase 4). Une fiche
n'en est pas la preuve.

## 📍 Current Phase
**Phase 1** : K.3 fait (12/11 : repo git `tactacboomboom/reprise-nov-2026`, rangement par séance) ; prochaine étape : vague 5 (K.1 ∥ K.2), fan-in par le pilote K.

## 🗓 Phases

### Phase 1: Vagues d'étude des repos
- [x] Vague 1 : PLUG-INS + graphify (D.1), audit-repo (D.2) : tri sans mémoire, refait en vague 2
- [x] Vague 2 : H.1 PLUG-INS + graphify (ARCHIVER) ∥ H.2 audit-repo (ARCHIVER)
- [x] Vague 3 : I.1 CPE-PWF-Engine (ARCHIVER) ∥ I.2 conformité Anthropic (ARCHIVER le repo, projet à reprendre)
- [x] Vague 4 : J.1 Claire + claire-app (ARCHIVER) ∥ J.2 cockpit-solo + De-l-Intention-a-l-Execution + chaine-intention-artefacts (ARCHIVER)
- [x] K.3 (seul, AVANT la vague 5, 12/11) : rangement par séance (`seances/<code>-<slug>/`) + repo git
  public `tactacboomboom/reprise-nov-2026` hors Drive ; Drive figé. 1er essai de la phase 4 : Yanis
  n'a pas pu décrire l'architecture Anthropic d'un dossier → écart total sur le « comment » (findings K.3)
- [ ] Vague 5 (pilote K, fiche 8 sections) : K.1 test-ia + CARTE-des-richesses (janvier) ∥ K.2 Anthropologie + projet-amelioration-fin-session + voyage_voyage (mai–juin)
- [ ] Vague 6 (pilote L) : L.1 claude-prostheses SEUL (fin de la lignée, le plus gros morceau ; Yanis, 11/11)
- `-my-claude-config` : config actuelle, pas étudiée comme souvenir, mais placée sur la carte
- **Status:** in_progress

### Phase 2: Convergence
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

Décisions en attente :
- [ ] 5. **Les 8 règles Anthropic** (fiche I.2 § 7) : où les ranger, dans la graine de
  `SKILLS\architecture-anthropic\` ou dans une annexe de `G:\Mon Drive\10 - Claude\TRANSVERS\gouvernance-regles.md` ? Une seule a été
  revérifiée le 11/11 ; à trancher après le point 2. Premier cas d'application : l'en-tête de `/pwf`
  porte `type`, `version`, `allowed-tools`… au lieu de `name` + `description` seuls (relevé par I, 11/11).
- [ ] 6. **archi-mao** (`SKILLS/architecture-multi-agent-orchestration`, 20/05) : en-tête non conforme
  (R4), absent du local (R10). Le mettre en conformité puis l'activer, ou le laisser dormir ?
- [ ] 7. **Juges R-gate = persona-prothèses** : la vision de Yanis relève du travail de la séance B
  (`seances/B-debut-session/2026-11-09-B-debut-session-r-gate.md`), à y rattacher.
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
| Rangement par séance `seances/<code>-<slug>/`, noms de fichiers inchangés (Yanis, K.3, 12/11) | Un contrat = 1 dossier au lieu de 3 ; aide surtout l'humain (Claude ne lit pas un sous-dossier tout seul : expert Anthropic) ; modèle « package » de Google/Bazel |
| Repo git créé MAINTENANT (lève D3 de K.3) : `C:\Users\bensa\00_MES-PROJETS\reprise-nov-2026`, public, Drive figé + note (Yanis, K.3, 12/11) | « Quitte à faire le travail, autant bien le faire maintenant » ; `git mv` garde la trace des déplacements |
| PR faites par Claude à la demande de Yanis ; la première fusion se fait ensemble (Yanis, K.3) | Projet solo : pas de CODEOWNERS, cycle ticket → PR → merge léger |
| Préparation git : `.gitattributes` (LF) fait ; modèle de PR et convention de commits `<code>: <verbe> …` à décider plus tard (K.3) | Sans sur-ingénierie pour un solo (spécialiste GAFAM) |

## 🚨 Errors Encountered
| Error | Attempt | Resolution |
| :--- | :--- | :--- |
| `grep -ril` avec plusieurs `-e` ou `-F` : 0 résultat sans erreur (faux négatif, É-I2-1) | I.2 | Chercher terme par terme et tester d'abord un terme connu (inscrit dans les kernels J.1/J.2) |
| Violation H1 : « persona = plugin = sous-agent » proposé sans tester les axes | I.2 | Corrigé dans la fiche I.2 § 4 à la clôture |
| `grep` de Git Bash « Aborted » sur le Drive (même avec `LC_ALL=C`) : tout sort faux négatif | J | Utiliser l'outil Grep intégré ; toujours tester un terme connu d'abord |
| Clôture J.2 à 80 % du contexte (KR-MISS) : lot de 3 repos + schéma riche | J.2 | Lots plus petits ; vague 5 : ≤ 3 petits repos par contrat |
| `git mv` : « destination exists » pour G et J (kernel et findings de même nom) | K.3 | Findings suffixés `-findings` ; règle ajoutée au CLAUDE.md |
| `sed` + chemins Windows (`\U`, `\0` interprétés) : 3 remplacements refusés ; `python -I` ignore `PYTHONIOENCODING` | K.3 | Remplacements par script Python (`str.replace`) lancé avec `-X utf8` |
