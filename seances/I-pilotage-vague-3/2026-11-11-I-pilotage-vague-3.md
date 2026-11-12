---
seance: I
parent: H
date: 2026-11-11
type: pilote (fan-in vague 3)
statut: complet
---

# Findings I — Fan-in de la vague 3 (I.1, I.2)

## 1. Jugement des fiches
Les 2 fiches existent, `statut : complet`, 7 sections dans l'ordre. Les kernels de clôture ont été
collés dans le chat par Yanis, puis rangés par I dans `docs/kernels/contrats/`.

| Critère | I.1 CPE-PWF-Engine | I.2 Conformité Anthropic |
|---|---|---|
| 7 sections, ordre | ✓ | ✓ |
| § 5 prévu / réel | ✓ | ✓ (2 + 2) |
| Témoignage de Yanis en preuve | ✓ [22], verbatim | ✓ [20], verbatim |
| Puce « Proposition au pilote » | ✓ 3 propositions | ⚠ suivie d'un bloc « Suite de ce lot » hors des puces |
| Mémoire rendue (d'après les témoignages des clôtures) | Oui : déclencheur (intention brouillonne, maths + Coran comme profs de remplacement) et arrêt (« une semaine sans y toucher = tout oublié ») | Le POURQUOI, pas le COMMENT : Yanis a oublié les 11 buckets |
| Liens révélés (C2) | Lignée janvier → CPE → Claire → claude-prostheses ; binômes /cpe-sprint ↔ « les biais s'annulent » | 4 chantiers de mai reliés par la seule tête ; persona-prothèse = plugin (forme seulement) ; juges R-gate |
| Verdict | ARCHIVER | ARCHIVER le repo, projet à reprendre |

## 2. Écarts
- **É-I1 — Gabarit, écarts entre les 2 fiches** : voix « Yanis » (I.1) contre « tu » (I.2) ; témoignage
  brut placé par les 2 fiches dans les Preuves sans que ce soit prévu ; verdict repo / projet confondus ;
  « Réponse à la question 1 du kernel » (I.1). → Gabarit corrigé : voix « Yanis », verbatim en
  `<blockquote>` dans les Preuves, « Verdict (sur le repo) », fiche lisible sans le kernel.
  Non retenu par Yanis : sortir métriques et écarts de méthode du pied de page (G4).
- **É-I2 — Ouvrir un fan-in avec le kernel d'un autre code** : I s'est ouvert avec le kernel nommé H,
  et les clôtures des contrats arrivaient collées dans le chat. → Nouvelle règle (Yanis) : un kernel
  porte le code de la séance qui s'ouvre avec lui ; les contrats écrivent leur clôture dans
  `docs/kernels/contrats/` ; le kernel du pilote les liste dans [Fichiers à charger].
- **É-I3 — Tâches rangées dans le README** : I y avait mis une section « Prochain modulo ». Yanis a
  relevé que ce n'était sans doute pas conforme. Règle Anthropic n° 6 (fiche I.2, non revérifiée) :
  liste de tâches dédiée + passation sur disque. → `task_plan.md` créé (gabarit /pwf), README allégé.
- **É-I4 — Schéma trompeur du pilote** : I a dessiné `J-pilotage-vague-4.md` parmi les fichiers écrits
  alors qu'il n'existait pas encore (question de Yanis : « où est J-pilotage-vague-4 ? »). Corrigé à l'oral :
  ce kernel naît à la clôture. Leçon : distinguer « écrit » et « à écrire » dans un schéma.
- **É-I5 — « Contrat B »** (clôture I.2, Q2) : B est une séance, pas un contrat. Routé dans
  `task_plan.md`, phase 3, point 7.
- **É-I6 — Lot J.2 lourd** : ~138 commits sur 3 repos (De-l-Intention : 109). Le kernel J.2 prévoit un
  repli : abandonner cockpit-solo et rendre la fiche en statut partiel.
- **É-I7 — Lieu au démarrage** : la séance a démarré dans `TRANSVERS` et non dans `REPRISE NOV 2026`
  (signalé dans le brief, sans effet).
- **É-I8 — `/pwf` non conforme** : son en-tête porte `type`, `version`, `allowed-tools`… (règles 1 et 7
  de I.2). Inscrit dans `task_plan.md`, phase 3, point 5.

## 3. Décisions de Yanis (11/11)
- Vague 4 : J.1 Claire + claire-app ∥ J.2 cockpit-solo + De-l-Intention-a-l-Execution + chaine-intention-artefacts.
- Finir les vagues « étude des repos » puis la convergence ; toutes les tâches dérivées (comment
  d'Anthropic, re-audit upstream, superpowers × matrice, alirezarezvani × matrice, 8 règles, archi-mao,
  juges R-gate, Clear Sky / SaaS-Traduction) attendent le prochain modulo.
- Proposition de I.2 « Prothèses d'alirezarezvani à l'aune des buckets Anthropic » : acceptée comme
  tâche du prochain modulo, en parallèle de superpowers.
- Corrections appliquées : gabarit (voix, témoignage, verdict, fiche autonome) et CLAUDE.md (prochain pilote J).
- Les tâches vivent dans `task_plan.md`, jamais dans le README.

## 4. Témoignage de Yanis (11/11, verbatim)
> « Je n'aime pas le fait que pour ouvrir une session fan-in je doives mettre le kernel H alors que les
> sous tâches étaient des I.1, I.2. Je préfère ouvrir avec le I. Donc il faut modifier les règles.
> De plus, les kernels généré par les sous-tâches I.1, I.2 restent in-line. J'aimerais mieux les
> organiser en les rangeant dans un sous dossier pour sous-tâches. Comme ça la session in-lin peut
> allez les chercher elle-même sans que j'ai à le faire à la mano. »

> « Non, je veux terminer les vagues "étude des repo". Et les nouvelles tâches qui en découlent on les
> traitera lors du prochain modulo. »

## 5. Fichiers écrits par I
`docs/kernels/contrats/2026-11-11-I.1-cloture.md` et `…-I.2-cloture.md` (kernels collés par Yanis,
rangés tels quels) · `docs/kernels/2026-11-11-J.1-memoire-claire.md` ·
`docs/kernels/2026-11-11-J.2-memoire-intention-janvier.md` · `docs/gabarits/fiche-memoire.html`
(4 corrections) · `CLAUDE.md` (dossier `contrats/`, règle de nommage des kernels, contrat = 2
fichiers, fan-in, prochain pilote J, `task_plan.md`) · `README.md` (lignes I, I.1, I.2, J, J.1, J.2 ;
§ Plan et tâches ; notes de convergence) · `task_plan.md` (création) · ce findings ·
`docs/kernels/2026-11-11-J-pilotage-vague-4.md` (/goedel, à la clôture).

## Métrique de séance
Status bar à la clôture : `🧠 65% (130k) · 💰 $2.07 · ⏱ 1h29m · api 8m · Δ +264/-22`.
Début : 09:11. Ledger : `data/ops-ledger.csv`, ligne I → KR-OK (< 70 %) · violations H1 (agent : correspondance PWF ↔ projet
findings ≈ fiches, progress ≈ kernels, posée sans tester les axes).
