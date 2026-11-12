---
seance: C
date: 2026-11-09
repo: tactacboomboom/Architecture-des-skills-Anthropic
statut: complet
---

# Findings C — Architecture-des-skills-Anthropic (+ écarts /debut-session v3 et méthode parallèle)

## 1. Contenu
Repo de documentation (25 Ko, 1 commit `e352ea9` du 27/05/2026, déployé sur Vercel) : grille
« 11 buckets Anthropic × chaîne de valeur », chaque case étiquetée S (skill) / SDK (agent piloté)
/ M (managed), déclinée pour 8 rôles + 5 « lois » (ex. « M = ce que tu veux oublier »).
*Preuve :* `README.md`, `references/matrice-chaine-valeur.md`, `matrice-generative.html`. *Confiance :* certaine.

## 2. Réutilisable
- **Inventaire plugins de l'ancien PC** (`references/roles-documents-matrix.md:178-188`) :
  superpowers, vercel, claude-mem → checklist de réinstallation (voir C-3).
- Grille S/SDK/M + 5 lois → grille de décision conceptuelle pour tout nouvel outil. Rien à installer.
- Skills cités présents : `/repo-audit`, `/fmath`, `/lineage` ✓. Absents : `/brainstorm`,
  `/writing-plans`, `/test-driven-development`, `/verification-before-completion` (plugin superpowers).
*Confiance :* certaine.

## 3. Conflits gouvernance et constats d'environnement
- **C-1 — Doublon (D1 « une seule maison »)** : `vault/matrice-generative.html` (25/05, 42 Ko,
  4 onglets) vs version du repo (8 onglets). *Preuve :* `ls -la`. *Confiance :* certaine.
- **C-2 — Doc en retard** : README et LINEAGE annoncent 4 onglets, le HTML en a 8. *Confiance :* certaine.
- **C-3 — Plugins disparus + violation R11** : `~/.claude/plugins` est un symlink vers
  `G:\Mon Drive\10 - Claude\plugins`, dossier inexistant ; aucun `enabledPlugins` dans
  `~/.claude/settings.json`. R11 bannit les symlinks. *Preuve :* `ls -la ~/.claude/plugins`. *Confiance :* certaine.
- **C-4 — Source non vérifiée** : la taxonomie 11 buckets viendrait d'un `registry.yaml` du
  cookbook Anthropic, non contrôlé. *Confiance :* moyenne.
- **C-5 — Égarés dans TRANSVERS** : `bootstrap-github.ps1` (code → hors Drive selon la grille Q1)
  et `user_setup.md` (fichier auto-memory, `originSessionId` dans son frontmatter). Signalés,
  non déplacés. *Confiance :* élevée.

## 4. Verdict
**ARCHIVER** — valeur = l'inventaire de l'ancien setup et la grille conceptuelle ; rien à copier tel quel.

## 5. Questions pour la convergence
- Réinstaller superpowers / vercel / claude-mem ? Remplacer le symlink plugins (R11) ?
- Supprimer la copie `vault/matrice-generative.html` (C-1) ?
- Où ranger `bootstrap-github.ps1` et `user_setup.md` (C-5) ?

## Annexe A — Écarts du 1er test réel de /debut-session v3 (Q1 du kernel B)
- **É-C1** : 2 kernels portaient la même date ; Yanis a voulu trancher par la date de modification.
  Le skill a refusé (règle : mtime non fiable sur Drive) et a affiché les mtimes à titre indicatif.
  Résolu structurellement par la convention codes lettres (`AAAA-MM-JJ-<code>-…`) dans
  `REPRISE NOV 2026/docs/kernels/`. L'ordre A→B est prouvé par le contenu (kernel B : « Séance 2 »).
- **É-C2** : les kernels A et B ont été renommés et déplacés ; le chemin [Fichiers à charger] du
  kernel B a été mis à jour.

## Annexe B — Méthode de parallélisation retenue (lecture claude-prostheses)
Sources : findings X, Z, AA + `docs/contrats/2026-06-05-X-runbook-sessions-paralleles.md`.
Leçons appliquées : série/parallèle = choix opérationnel (F-X1) ; à N=2 et tâches courtes la série
gagne en $, le gain est la qualité de contexte et l'apprentissage (Z-1, Z-2) ; attention de Yanis
= goulot → vagues de 2 (runbook §5-6, **choix Yanis**) ; coordination par artefacts, pas
d'orchestrateur (F-X5) ; grille de jugement écrite AVANT les livrables (AA §3 → `CLAUDE.md`) ;
chemins des kernels vérifiés avant lancement (É-AA-1).
Adaptation : pas de git sur le Drive (R3) → disjonction par « 1 séance = 1 fichier findings ».

## Annexe C — Écarts de la séance C (pour le pilote D)
- **É-C3 — Lettres de séance mal attribuées par l'agent** : les findings de cette séance (la 3ᵉ)
  avaient été nommés « B » (la lettre de la séance 2), et les lettres C et D données aux analyses.
  Détecté à la clôture, renuméroté avec l'accord de Yanis : ici = C, pilote = D, analyses = E, F.
  Leçon : la lettre se décide à l'ouverture de la séance (A = 1ʳᵉ séance), pas au fil des fichiers.
- **É-C4 — Reco agent vs choix Yanis** : l'agent recommandait des vagues de 3 ; Yanis a exigé la
  relecture de la méthode de juin puis a choisi des vagues de 2. Même famille que F3 : la reco
  contextuelle de l'agent est discutable, la source primaire tranche.
- **É-C5 — Choix de Yanis : séance pilote** : Yanis refuse le fan-out par agents invisibles ;
  une séance pilote lui donne le mode d'emploi et c'est lui qui lance les terminaux.

## Métrique de séance
Contexte à la clôture : 56 % (112k) · coût 1,89 $ · durée 1h01 (status bar fournie par Yanis).
Lectures : kernel B, findings B (A+B), repo Architecture-des-skills, gouvernance-regles (l. 11-135),
findings X, Z, AA + runbook (claude-prostheses).

## Annexe D — Ledger de séance (construit après /goedel, à la demande de Yanis)
- **Réutilisation** : `claude-prostheses/scripts/ops_ledger.py` accepte `--csv` → aucun code copié
  (D1, R3). Donnée : `data/ops-ledger.csv` ; procédure : `CLAUDE.md` § Outils. *Confiance :* certaine
  (test réel sur la status bar de C).
- **É-C6 — Deux pièges du script / skill** :
  (a) le miroir par défaut RECOPIE le CSV vers `C3-PRODUIT\ops-cost-ledger.csv` → `--mirror ""`
  obligatoire hors claude-prostheses, sinon écrasement croisé ;
  (b) `/goedel` étape 4 et le script citent `vault/3-PERSONNEL/…` ; le vrai dossier est
  `vault/3 - PERSONNEL/…` → la passe heuristiques échouerait à la lecture. *Preuve :* `find`. *Confiance :* certaine.
- **É-C7 — « 0 » de complaisance évité de justesse** : le test initial passait `--violations 0` sans
  passe heuristiques (piège H3 du skill). Corrigé : A, B, C = non évalué (champ vide).
- **Rétro-remplissage honnête** : A (ctx_close 80 % seul), B (4,78 $ · 31 min · 65 %) depuis findings B §D ;
  champs inconnus laissés vides.
