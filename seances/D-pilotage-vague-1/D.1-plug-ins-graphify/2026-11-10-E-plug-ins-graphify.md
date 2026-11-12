---
seance: E
date: 2026-11-10
repo: tactacboomboom/PLUG-INS + tactacboomboom/-graphify-transformer (lot « plugins et graphify »)
statut: complet
---

# Findings E — PLUG-INS + -graphify-transformer (+ diagnostic MCP graphify)

Clones : `<scratchpad>/PLUG-INS`, `<scratchpad>/graphify-transformer` (`--depth 1`, lecture seule).

## Réponses prioritaires du kernel

### P1 — Pourquoi le serveur MCP graphify échoue (CONNECTION_CLOSED)
- **Chaîne de config** : `TRANSVERS/.claude/settings.local.json:2-5` active `graphify` → défini dans
  `G:\Mon Drive\10 - Claude\.mcp.json:3-6` (aucun `.mcp.json` dans TRANSVERS, aucun `mcpServers`
  dans `~/.claude.json`). Aussi activé dans `10 - Claude/.claude/settings.json:29-31`.
- **Cause n°1 (bloquante)** : l'interpréteur nommé `C:\Users\bensa\AppData\Local\Python\pythoncore-3.14-64\python.exe`
  **n'existe plus** depuis la réinstallation. Le Python actuel est `C:\Python314\python.exe` (3.14.3).
  Claude Code lance un exécutable absent → le processus meurt → « Connection closed ».
  *Preuve :* `ls` du chemin → « No such file » ; `python -c "import sys;print(sys.executable)"`. *Confiance :* élevée.
- **Cause n°2 (latente, après correction du chemin)** : le serveur (`10 - Claude/.claude/graphify-mcp-server.py`)
  est un script stdlib qui se contente de relayer vers `python -m graphify query|explain|path`. Le
  package `graphifyy` n'est pas installé → le serveur démarrerait mais chaque outil renverrait
  « No module named graphify ». *Preuve :* `python -c "import graphify"` → ModuleNotFoundError. *Confiance :* certaine.
- **Chemin codé en dur en 3 endroits** : `.mcp.json:4`, `graphify-mcp-server.py:4` (`PY = ...`) et
  `vault/2 - CONCEPTS/graphify-out/.graphify_python` (même chemin mort). *Confiance :* certaine.
- Description périmée : `graphify-mcp-server.py:8` annonce « 90 nœuds, 143 edges » (codé en dur).
  *Confiance :* certaine.

### P2 — Réinstaller claude-mem et graphify proprement (sans lien, R11) — RECOMMANDATION, rien exécuté
```
ÉTAT ACTUEL                                   CIBLE
~/.claude/plugins ──JUNCTION──► Drive/plugins (absent)   ~/.claude/plugins = vrai dossier local
python3 ──► stub Microsoft Store                         C:\Python314\python.exe partout
graphifyy : absent      claude-mem : absent              installés localement, version fixée
```
1. **Supprimer la jonction** `~/.claude/plugins` (supprimer le lien seul, `rmdir` sans `/s` : la
   cible n'existe pas, rien à perdre) → laisser Claude Code recréer un dossier local réel.
   *Preuve :* `cmd /c dir C:\Users\bensa\.claude` → `<JUNCTION> plugins [\??\G:\Mon Drive\10 - Claude\plugins]`.
   Précision vs finding C-3 : c'est une **jonction** (pas un symlink), le lien est quand même banni par R11. *Confiance :* certaine.
2. **claude-mem** : `npx claude-mem install` puis `npx claude-mem status` (worker local port 37777,
   hooks écrits dans `~/.claude/settings.json`, Bun auto-installé — absent aujourd'hui). Node v24.13 ✓,
   Git Bash ✓. Rester en mode `worker` (pas server-beta).
   *Preuve :* `PLUG-INS/CLAUDE.md:16`, audit `claude-mem-analysis.html` onglet Installation (v13.2.0, mai 2026).
   *Confiance :* moyenne (commande datant de 6 mois, à revérifier sur le README actuel).
3. **graphify** : `C:\Python314\python.exe -m pip install graphifyy==<version>` (version fixée : l'audit
   recommande d'épingler, API v0.1.x instable). `C:\Python314\Scripts` est déjà dans le PATH → la
   friction PATH de l'audit ne s'applique plus. Le skill `~/.claude/skills/graphify/SKILL.md` est déjà
   présent → **ne pas** relancer `graphify install` sans comparer (il réécrirait le skill).
   *Preuve :* `graphify-analysis.html` onglet Installation ; `echo $PATH`. *Confiance :* élevée.
4. **Piège python3** : le skill graphify (`SKILL.md:~99-109`) se rabat sur `python3` puis fait
   `pip install`. Sur ce PC, `python3` = alias Microsoft Store (« Python was not found ») → l'auto-install
   du skill échouerait. Installer graphifyy à la main (étape 3) AVANT tout `/graphify`, ou désactiver
   l'alias (Paramètres > Applications > Alias d'exécution). *Preuve :* `python3 -c ...`. *Confiance :* certaine.
5. **MCP** : remplacer le chemin mort par `C:\Python314\python.exe` dans `.mcp.json:4`, et dans le
   script remplacer `PY = r"..."` par `PY = sys.executable` (une seule source de vérité). Puis
   régénérer `.graphify_python` via un `/graphify --update`. *Confiance :* élevée.

## 1. Contenu
- **PLUG-INS** : 1 commit (`eee7327`, 18/05/2026 « add graphify v0.1.14 audit »), 22 Ko.
  `CLAUDE.md` (registre + règle « /repo-audit avant tout plugin »), `MEMORY.md`, `index.html`, deux
  audits HTML (claude-mem v13.2.0, graphify v0.1.14). Aucune config réelle (pas de settings ni de JSON
  de plugin, contrairement à ce qu'annonçait le kernel) : uniquement des audits et un registre.
  État : figé depuis 6 mois. *Preuve :* `git log`, `wc -c`. *Confiance :* certaine.
- **-graphify-transformer** : 1 commit (`f1a7862`, 17/05/2026), 15 Ko. `transformer.py` (129 l.) :
  lit `~/.claude-mem/claude-mem.db` (table `observations`) → ajoute des nœuds `mem-<md5>` dans
  `vault/2 - CONCEPTS/graphify-out/graph.json`, dry-run par défaut, `--write` pour écrire. 3 `.bat`,
  `test_transformer.py` (tests d'intégration sur la vraie base et le vrai graphe). État : abandonné, prototype.
  *Confiance :* certaine.
- Défauts du transformer : (a) nœuds ajoutés **sans aucune arête** → isolés dans le graphe ;
  (b) `load_vault_conversations` (`transformer.py:75-88`) n'est jamais appelée par `main()` alors que
  le commit annonce « vault/conversations » ; (c) `datetime.utcnow()` (`:38`) est obsolète en 3.12+ ;
  (d) `__pycache__/` est commité. *Confiance :* certaine.
- Tests **non exécutés** volontairement : `sqlite3.connect(DB_PATH)` (`test_transformer.py:52`)
  **crée** une base vide si elle est absente (c'est le cas : `~/.claude-mem` n'existe pas) → ce serait
  une modification du setup (C2). *Confiance :* certaine.

## 2. Réutilisable
- Procédure de réinstallation (commandes + prérequis + points Windows) → déjà présente dans le
  Drive `G:\Mon Drive\10 - Claude\PLUG-INS\` (copie identique, voir Q1). Rien à copier.
- Règle « `/repo-audit` avant tout nouveau plugin » (`PLUG-INS/CLAUDE.md:20`) → candidate pour
  `gouvernance-regles.md` (décision de la convergence). *Confiance :* élevée.
- `transformer.py` → **rien maintenant** : dépend de claude-mem (absent). À réévaluer après réinstallation ;
  il faudrait alors au minimum générer des arêtes. *Confiance :* élevée.
- Graphe existant `vault/2 - CONCEPTS/graphify-out/graph.json` (146 Ko, 25/05) toujours présent →
  réutilisable directement par le MCP une fois réparé. *Preuve :* `ls -la graphify-out`. *Confiance :* certaine.

## 3. Conflits gouvernance
- **R11** — `~/.claude/plugins` = jonction vers un dossier Drive inexistant (voir P2.1). *Confiance :* certaine.
- **R11 (hors lot, constat d'environnement)** — `~/.claude/CLAUDE.md` est un **SYMLINK** vers
  `G:\Mon Drive\10 - Claude\CLAUDE.md`, alors que R11 prescrit un fichier local contenant
  `@G:\Mon Drive\10 - Claude\CLAUDE.md`. *Preuve :* `cmd /c dir C:\Users\bensa\.claude` →
  `<SYMLINK> CLAUDE.md`. Signalé, non modifié. *Confiance :* certaine.
- **R3** — respectée : pas de `.git` dans `Drive/PLUG-INS`. *Confiance :* certaine.
- Doublon (« une seule maison », cf. C-1) — repo PLUG-INS = copie octet pour octet du dossier Drive. *Confiance :* certaine.
- Chemins absolus machine-dépendants codés en dur (transformer, tests, MCP) → cassent à chaque
  réinstallation : c'est exactement la panne de P1. *Confiance :* certaine.

## 4. Verdict
- **PLUG-INS : ARCHIVER** — doublon intégral du dossier Drive (qui est la source : fichiers 18:26–18:37,
  push 18:39). Garder le Drive comme maison unique ; le repo n'a de valeur que comme miroir publié.
- **-graphify-transformer : ARCHIVER** — prototype mono-commit, nœuds sans arêtes, dépend d'un
  claude-mem absent. À rouvrir seulement si le combo claude-mem → graphify est voulu.

## 5. Questions pour la convergence
- **Q1 (kernel) — tranchée** : oui, doublon. `diff -q --strip-trailing-cr` sur les 4 fichiers → identiques.
  Reste à décider : archiver le repo GitHub, ou garder le Drive seul. *Confiance :* certaine.
- **Q2 (kernel) — recommandation** : **aucune cible Drive**. Les plugins sont locaux par machine
  (`PLUG-INS/CLAUDE.md:7-8` le dit lui-même) → supprimer la jonction, dossier local réel, et le Drive
  ne garde que le registre et les audits (`Drive/PLUG-INS`). *Confiance :* élevée.
- Q3 : réinstaller claude-mem ? (coût en tokens des résumés absorbé par un abonnement Max, d'après l'audit)
  Le transformer et le combo graphify en dépendent.
- Q4 : garder le serveur MCP maison (relais vers la CLI) ou utiliser le serveur MCP natif de graphify
  (l'audit en mentionne un, « MCP server stdio, 3 fonctions ») ? Non vérifié.
- Q5 : superpowers et vercel (inventaire C, section 2) ne figurent pas dans le registre PLUG-INS → registre incomplet.
- Q6 : corriger le symlink `~/.claude/CLAUDE.md` (R11) → hors périmètre de E, à arbitrer.

## Métrique de séance
- Lu : kernel, findings C (sections 2–3), les 2 repos, la config MCP, le script du serveur, l'en-tête
  d'installation du skill graphify. Aucun fichier modifié hors de ce findings.
