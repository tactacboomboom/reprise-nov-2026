---
seance: G (code canonique D.3)
parent: D
date: 2026-11-10
repo: —
statut: complet
---

# G (D.3) — Convention de nommage des séances parallèles

Séance hors repo : format libre fixé par son kernel (`CLAUDE.md` § Conventions, dernière puce).
Destinataire : séance D (pilote), qui reprend les blocs « prêt à coller » avant sa clôture.

## 1. Décisions prises en séance (Yanis, 10/11)

- **Q1 tranchée : G = D.3.** G est lancée par D et D fait son fan-in (reprise du texte).
- **Vague 2 = contrats H.1 et H.2** : kernels de lancement écrits par D, mais **parent = H**
  (le prochain pilote, qui attend leurs findings). Règle : parent = celui qui fait le fan-in.
- **Skills NON modifiés** par G : conforme à `CLAUDE.md` § Règles (« on RECOMMANDE »). Diffs
  fournis en § 6, à appliquer (ou non) par D + Yanis après test sur la vague 2.

## 2. La convention

```
ligne principale (pilotes, chronologique)
A ── B ── C ── D ─────────────────(fan-in)── D clôt ── H ── …
               │ fan-out                  ▲
               ├── D.1 (ex-E) ── findings ┤
               ├── D.2 (ex-F) ── findings ┤
               └── D.3 (ex-G) ── findings ┘
```

| Élément | Règle |
|---|---|
| Pilote | 1 lettre, ordre chronologique ; après Z → AA (comme le ledger claude-prostheses). Une lettre utilisée n'est **jamais réutilisée** : E, F, G grillées → prochain pilote **H**. |
| Contrat | `Pilote.N`, N = ordre de lancement, jamais réutilisé. |
| Parent | La séance qui fait le **fan-in**, pas forcément l'auteur du kernel (C a écrit E et F, D les attend → D.1, D.2). |
| Fan-in | Le pilote ne clôt pas avant d'avoir un findings de chaque contrat (≈ `needs:` CI/CD). Un findings `échoué` compte comme reçu. |
| Fichiers | `AAAA-MM-JJ-<code>-<slug>.<ext>` (ex. `2026-11-10-D.1-plug-ins.md`). Kernel de lancement d'un contrat : écrit par le pilote, porte le code du contrat. Kernel de clôture d'un pilote : porte son propre code. |
| `[Lignée]` | 1 ligne en tête du kernel, avant `[Contexte]` (voir § 2.1). |

### 2.1 Champ `[Lignée]`
```
[Lignée] code : D.1 · parent : D · type : lancement · contrats : —
[Lignée] code : D · parent : C · type : clôture · contrats : D.1 ✓, D.2 ✓, D.3 ✓
[Lignée] code : D.4 · parent : D · type : lancement · contrats : — · relance de : D.1
```
`type` lève l'ambiguïté historique : un kernel de pilote = clôture ; un kernel de contrat = lancement.

### 2.2 Cas limites
- **Sous-contrat `D.1.1` : interdit** (profondeur 1). Un contrat n'écrit que son findings, il ne
  lance rien. Besoin de découper → il le dit dans son findings, le pilote lance `D.N+1`.
- **Contrat échoué** : findings `statut : échoué` (nouvelle valeur, à côté de complet / partiel).
  Relance = nouveau numéro + `relance de : D.x`.
- **Contrat annulé avant lancement** : « annulé » dans le README ; le fan-in ne l'attend plus.
- **Séance lancée par un pilote hors vague** (cas G) : contrat de ce pilote (G = D.3).
- **Séance sans pilote** (lancée par Yanis, ex. A, B) ou **convergence** : lettre de pilote,
  parent = dernier pilote.
- **Limite** : ≤ 9 contrats par pilote (`D.10` se trie avant `D.2`). Sans effet en vagues de 2.

### 2.3 Compatibilité vérifiée (C4)
- `/debut-session` étape 1 lit la date dans les 10 premiers caractères du nom → le point du code
  ne gêne pas. *Preuve :* `debut-session/SKILL.md` étape 1.3. *Confiance :* certaine.
- Tri : `-` (0x2D) < `.` (0x2E) → `D-…` < `D.1-…` < `D.2-…` < `E-…` : le pilote précède ses
  contrats. *Preuve :* `printf … | LC_ALL=C sort` en séance. *Confiance :* certaine.
- Ledger : `--seance` est une chaîne libre → `D.1` accepté. *Preuve :*
  `claude-prostheses/scripts/ops_ledger.py:364`. *Confiance :* certaine.

## 3. Table de correspondance (D3 : aucun fichier renommé)

| Lettre (fichiers) | Code canonique | Parent | Rôle |
|---|---|---|---|
| A | A | — | pilote |
| B | B | A | pilote |
| C | C | B | pilote (auteur des kernels E, F) |
| D | D | C | pilote vague 1 |
| E | D.1 | D | contrat |
| F | D.2 | D | contrat |
| G | D.3 | D | contrat (convention) |
| — | H | D | prochain pilote |
| — | H.1, H.2 | H | contrats vague 2 (kernels écrits par D) |

## 4. Prêt à coller — `CLAUDE.md`

Ligne 5, remplacer `code = lettre de séance` par :
```
code = lettre du pilote ou `Pilote.N` pour un contrat — voir § Nommage des séances
```

Nouvelle section, à insérer avant `## Outils` :
```
## Nommage des séances (fan-out / fan-in, fixé par G = D.3)
- Pilote = 1 lettre, chronologique, jamais réutilisée (E, F, G grillées → prochain pilote H).
- Contrat parallèle = `Pilote.N` (D.1, D.2…), N jamais réutilisé. Pas de sous-contrat (D.1.1).
- Parent = la séance qui fait le fan-in (pas forcément l'auteur du kernel).
- Fan-in : le pilote ne clôt pas avant d'avoir le findings de CHAQUE contrat (`échoué` compte).
- Tout kernel commence par :
  `[Lignée] code : … · parent : … · type : lancement|clôture · contrats : … [· relance de : …]`
- Contrat échoué → findings `statut : échoué` ; relance = nouveau numéro.
- Fichiers A–G non renommés : correspondance E = D.1, F = D.2, G = D.3 (README).
```

Frontmatter des fiches / findings : ajouter `parent`, et `statut` accepte `échoué` :
```
Frontmatter : `seance`, `parent`, `date`, `repo`, `statut` (complet / partiel / échoué).
```

## 5. Prêt à coller — `README.md`

Ligne 5–6, remplacer la phrase « Convention : 1 lettre = 1 séance… » par :
```
Convention : lettre = pilote (chronologique) ; `Pilote.N` = contrat parallèle lancé par ce
pilote ; colonne Parent = qui fait le fan-in. Détail : `CLAUDE.md` § Nommage des séances.
```

Tableau Séances :
```
| Code | Parent | Vague | Objet | Kernel écrit | Findings | État |
|---|---|---|---|---|---|---|
| A | — | — | Réinstallation du Custom PC | `2026-11-09-A-reinstallation-custom-pc.md` | — | clos |
| B | A | — | Reconstruction de /debut-session v3 | `2026-11-09-B-debut-session-preparation-repos.md` | `2026-11-09-B-debut-session-r-gate.md` | clos |
| C | B | — | Architecture-des-skills + rangement + cadrage des vagues | `2026-11-09-C-pilotage-vague-1.md` | `2026-11-09-C-architecture-des-skills.md` | clos |
| D | C | pilote 1 | Lance la vague 1, juge D.1–D.3, écrit les kernels H.1/H.2 | (à sa clôture) | — | en cours |
| D.1 (E) | D | 1 | PLUG-INS + -graphify-transformer | `2026-11-09-E-analyse-plug-ins-graphify.md` (lancement) | `2026-11-10-E-plug-ins-graphify.md` | findings écrit |
| D.2 (F) | D | 1 | audit-repo | `2026-11-09-F-analyse-audit-repo.md` (lancement) | `2026-11-10-F-audit-repo.md` | findings écrit |
| D.3 (G) | D | — | Convention de nommage des séances parallèles | `2026-11-10-G-convention-nommage.md` (lancement) | `2026-11-10-G-convention-nommage.md` | findings écrit |
| H | D | pilote 2 | Fan-in de la vague 2 | (à sa clôture) | — | prévu |
| H.1 | H | 2 | CPE-PWF-Engine | écrit par D | — | prévu |
| H.2 | H | 2 | rag_concepts | écrit par D | — | prévu |
| — | — | 3 | Claire ∥ chaine-intention-artefacts + De-l-Intention-a-l-Execution | codes fixés par le pilote de la vague 3 | — | prévu |
| — | — | — | Convergence (lettre de pilote, parent = dernier pilote) | après la vague 3 | — | prévu |
```
Ligne 34 (« Les kernels E et F sont des kernels de LANCEMENT (écrits par C) ») : ajouter
« — parent D (fan-in), pas C ».

## 6. Recommandation — diffs des skills (NON appliqués)

**Source canonique (Q2) :** `C:\Users\bensa\00_MES-PROJETS\-my-claude-config\skills\` (repo git,
dernier commit `86896ab` 2026-11-09) ; `install.sh` copie vers `~/.claude/skills`. Contenu
identique à la copie locale, seules les fins de ligne diffèrent (CRLF côté repo). → Modifier le
repo, puis recopier. *Preuve :* `diff --strip-trailing-cr -q` + `file` en séance. *Confiance :* certaine.

Quand : après test de la convention sur la vague 2 (convention neuve, skills transverses à tous
les projets).

### `/goedel` (`skills/goedel/SKILL.md`)
~~~diff
 ## Étape 2 — COMPRESS
 Mapper les éléments extraits vers les 5 types d'axiomes :
 ```
+[Lignée]     code · parent · type (lancement / clôture) · contrats — si le projet nomme ses séances
 [Contexte]    Projet · phase · type de session (Exploration / Exécution)
@@
 Contraintes strictes : ≤ 300 mots total · ≤ 10 items · zéro redondance entre sections.
+Lignée : pilote = 1 lettre chronologique jamais réutilisée ; contrat parallèle = `Pilote.N`
+(pas de `D.1.1`) ; parent = la séance qui fait le fan-in. Kernel de lancement d'un contrat →
+fichier `AAAA-MM-JJ-<Pilote.N>-<slug>.md`.
@@ ## Étape 3 — TEST
+**Gate fan-in (pilote uniquement) :** chaque contrat listé dans `[Lignée]` a un état
+(✓ findings reçu, échoué, annulé). Un contrat sans état → ne pas clôturer.
@@ ## Format de sortie
 --- KERNEL /goedel · {YYYY-MM-DD} · {projet} ---
 
+[Lignée] code : … · parent : … · type : lancement|clôture · contrats : …
+
 [Contexte]
~~~

### `/debut-session` (`skills/debut-session/SKILL.md`)
~~~diff
 ## Étape 1 — LOAD
-   alphabétique n'est pas l'ordre chronologique. Ne rien charger sans son choix.
+   alphabétique n'est pas l'ordre chronologique. Le code après la date indique la lignée :
+   `D` = pilote, `D.N` = contrat parallèle de D. Ne rien charger sans son choix.
@@ ## Étape 2 — DERIVE
+| [Lignée] *(optionnelle)* | Code de la séance, parent, type ; pour un pilote : contrats à attendre (fan-in) |
 | [Contexte] | Projet, phase, type de séance ; ... |
@@ ## Étape 4 — CHECK
+- Fan-in : si `[Lignée]` liste des contrats, chacun a-t-il un findings dans `docs/findings/`
+  (motif `*-<code>-*`) ? Manquant → alerte. Si la séance est un contrat : elle ne lance rien.
@@ ## Étape 5 — BRIEF
-[debut-session] Kernel chargé · {date kernel} · {projet}
+[debut-session] Kernel chargé · {date kernel} · {projet} · {code} ← {parent}
~~~

## 7. Questions pour D / la convergence

- **D** : reprendre § 4 et § 5 dans `CLAUDE.md` et `README.md` ; écrire les kernels de
  lancement de la vague 2 sous `2026-11-1x-H.1-…` / `H.2-…` avec `[Lignée] parent : H`.
- **Yanis + D** : appliquer § 6 dans `-my-claude-config` (puis recopier) après la vague 2, ou
  garder la convention seulement dans le CLAUDE.md du projet ?
- **Pilote vague 3** : fixer les codes (contrats de H, ou nouveau pilote I ?) selon qui fait le fan-in.
