---
seance: H
parent: D
date: 2026-11-10
type: pilote (fan-in vague 2)
statut: complet
---

# Findings H — Fan-in de la vague 2 (H.1, H.2)

## 1. Jugement des fiches
Les 2 fiches existent, `statut : complet`, 7 sections dans l'ordre, en-tête `[Lignée]` et parent
corrects dans leurs kernels de clôture → la convention de nommage (G) a tenu sur la vague 2.

| Critère du gabarit | H.1 PLUG-INS + transformer | H.2 audit-repo |
|---|---|---|
| Déclencheur / objectif | ✓ concrets (graphe à 0 lien, réinstaller les plugins) | ✓ très vivant (timeout du 20/05, « consulter sur mon tel ») |
| Frise : tous les commits | ✓ 6/6, 2 pistes + branche jamais fusionnée | ✓ 9/9, 4 phases |
| Arsenal / usage | ✓ meilleur apport : usage PRÉVU (transformer) ≠ usage RÉEL (`/n1n4` → vault → graphify) | ✓ `/repo-audit` décrit comme « ta façon d'apprendre » |
| Où je me suis arrêté | ✓ + découverte : graphe abîmé le 25/05 | ✓ `architecture-anthropic` jamais construit |
| Preuves [n] + confiance | ✓ 25 preuves | ✓ 17 (phrase d'accroche sans preuve : mineur) |

**Verdict de Yanis (critère « ai-je retrouvé la mémoire du repo ? ») : oui — « on avance très bien ».**
Les deux fiches rendent la mémoire, nettement mieux que E et F (vague 1, tri seul).

## 2. Écarts
- **É-H1 — Contradiction entre fiches** : H.2 reprend le tri de F « RÉCUPÉRER claude-mem
  (priorité 1) » ; H.1 rapporte la décision de Yanis : claude-mem n'est PAS réinstallé (capture
  passive, sans artefact utile ; remplacé par `/n1n4` + `/debut-session` + `/goedel`). Le tri de
  F/H.2 est périmé sur ce point. Noté au README § Pour la convergence.
- **É-H2 — § 7 « fourre-tout »** : dans les 2 fiches, « Pour la convergence » a reçu du hors
  périmètre (rag_concepts dans H.1 ; séance « vision Anthropic », état du PC dans H.2).
  → Gabarit corrigé : puce « Proposition au pilote » en § 7, § 5 en prévu/réel, preuve
  « témoignage de Yanis (date) · certaine (déclaratif) » — déjà utilisée par les 2 fiches sans
  être prévue.
- **É-H3 — `README.md:6`** : `Pilote.N` défini comme « contrat lancé par ce pilote », alors que
  la pratique le nomme d'après le pilote qui fait le FAN-IN (H.1 écrit par D). Corrigé.
  Même trace dans `CLAUDE.md` § Nommage (« prochain pilote H ») : non corrigé, en attente de Yanis.
- **É-H4 — Clone partiel de C** : C a compté 1 commit sur Architecture-des-skills-Anthropic ;
  `gh api repos/…/commits` en compte 4. Probable clone `--depth 1`. À vérifier par I.2.
  *Confiance :* élevée.
- **É-H5 — CPE-PWF-Engine est antérieur à mai** : `gh repo view` + `gh api` → créé le 02/02/2026,
  31 commits, 75 Ko, public. Possible 1re prothèse. À vérifier par I.1. *Confiance :* certaine (dates).
- **É-H6 — Findings oublié à la clôture** : kernel + ledger produits sans findings ; rattrapé à la
  demande de Yanis (« Avant quand je clôturais une session tu générais kernel + findings »).
  Règle : clôture = kernel + findings, toujours, même pour un pilote.

## 3. Décisions de Yanis (10/11)
- rag_concepts : pas de contrat dédié (« ok pas besoin ») ; reste ouvert : public alors que le vault est privé.
- Vague 3 : I.1 CPE-PWF-Engine ∥ I.2 lot « conformité Anthropic » (repo Architecture-des-skills-
  Anthropic + les 6 audits Anthropic = séance « vision Anthropic » proposée par H.2).
- Diffs de G § 6 (`/goedel`, `/debut-session`) : PAS maintenant — « le moment où on aura rodé
  plusieurs fois on le fera ».
- Circuit des audits : `PLUG-INS/<nom>/` sur le Drive = seule maison (recommandation de H, non contestée).

## 4. Témoignage de Yanis (10/11, verbatim) — matière de la carte de l'arsenal
> « En fait je me souviens de mieux en mieux l'état d'esprit dans lequel j'étais. En fait, j'étais
> en train de construire des prothèse agentique de toute part. Chaque agent allait devenir un clone
> de quelque chose : mes concepts, la conformité anthropic, un PhD IA, etc etc. D'ailleurs, cela est
> relié à un repo nommé "https://github.com/tactacboomboom/Architecture-des-skills-Anthropic".
> Pour répondre à ta question : on avance très bien. Peu à peu je réalise l'étendu de mes travaux.
> Les liens qu'ils avaient entre eux. J'étais en train de constuire des clones de partout, de la
> bibliographie sémantique, des archives, de la mémoire externe, des méthode / process / skill. Une
> équipe scrum pour dev solo etc etc. Le tout en boostrap. C'était un travail colossal qui
> nécessitait une concentration constente jour à près jour car c'était mon cerveau qui retenait tout
> en même temps simultanément. Sachant que j'étais aussi apprenti donc je devais combattre contre mon
> ignorance et je n'ai pas de prof donc contre mes propres biais. »

Lecture du pilote : chaque fiche montre UN repo ; le sens était dans les LIENS entre repos, tenus
par la seule tête de Yanis. → À la convergence : dessiner la carte de l'arsenal (quel clone,
quels repos, quels liens). Inscrit dans les kernels I.1, I.2, H et au README.

## 5. Fichiers écrits par H
`docs/gabarits/fiche-memoire.html` (3 corrections) · `docs/kernels/2026-11-10-I.1-memoire-cpe-pwf-engine.md` ·
`docs/kernels/2026-11-10-I.2-memoire-conformite-anthropic.md` · `docs/kernels/2026-11-10-H-pilotage-vague-3.md` ·
`README.md` (lignes H, H.1, H.2, I, I.1, I.2 ; définition `Pilote.N` ; § Pour la convergence) · ce findings.

## Métrique de séance
Status bar à la clôture : `🧠 50% (100k) · 💰 $1.15 · ⏱ 6h11m · api 3m · Δ +134/-10`.
Ledger : `data/ops-ledger.csv`, ligne H → KR-OK (< 70 %).
Passe heuristiques (pool H1–H5, H7) : 0 violation. H3 non déclenché (Yanis a tranché lui-même) ;
H1 possible sur la fusion repo + audits en I.2, chronologie gardée distincte ; H4 écarté
(rag_concepts retranché) ; H7 : l'écart É-H4 ne touche que C (E et F refaits en clone complet).
Rédigé après le ledger (É-H6).
