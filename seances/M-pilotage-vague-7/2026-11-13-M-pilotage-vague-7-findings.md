---
seance: M
parent: L
date: 2026-11-13
type: pilote 7 · fan-in de la vague 7 (Exploration)
statut: complet (fan-in M.1, M.2)
lieu: worktree ../reprise-nov-2026-M, branche seance/M-pilotage-vague-7 (depuis origin/main c14b5f9)
---

# M — Fan-in de la vague 7

En une phrase : M.2 a rendu COMMENT la chaîne E a été construite, M.1 OÙ et POURQUOI elle a buté ;
les deux aboutissent au même mur, « cohérent ≠ vrai », que seul un vrai projet peut lever.

## 0. Lieu (contrôle de démarrage)

Le kernel M nommait le worktree `../reprise-nov-2026-M` : il n'existait pas, la séance s'est ouverte dans
le dossier partagé sur `main` (en retard de 2 merges). Créé après le « ok », avant toute écriture. Les
worktrees `-M1` et `-M2` (branches mergées, propres) ont été supprimés sur demande de Yanis.

## 1. Jugement de M.1 et M.2

| Critère | M.1 (état au 23/06) | M.2 (chaîne E) |
|---|---|---|
| 8 sections, ordre | ✓ | ✓ |
| Preuves | 43 renvois, 26 sources | 57 renvois, 33 sources |
| Demande du kernel M | tableau gabarit × statut (§ 7) ✓ | « nilpotent » expliqué simplement (§ 4 A) ✓ |
| Verdict | RÉCUPÉRER « comme carte, pas comme chantier » | RÉCUPÉRER R-gate + « générer librement, vérifier mécaniquement » + boucle échec → mécaniser ; ARCHIVER la chaîne à 5 documents |
| Statut | complet (ctx 71 %) | complet (ctx 111 %) |

Défaut mineur (clôture non modifiée, elle appartient à M.2) : en-tête `code : M · parent : M`, il fallait `code : M.2`.

Ce que la vague apporte (lecture du pilote) :

```
M.2  comment (30/05 → 11/06)          M.1  où et pourquoi (20/06 → 23/06)
 maths → machine → juges → hook        NFR sans parent → SRD attend le PRD
 → « cohérent ≠ vrai » (08/06)          → Code plafonné → « la théorie s'arrête
                                           là où commence le réel »
                    ╲                  ╱
                     ANCRAGE : une racine = l'intention d'un humain
                     (Team Charter prévu puis sauté, M.2 F8) → vague 8 (N.2)
```

## 2. Contenu sensible (C2 du kernel M)

PR #10 (M.2) et #11 (M.1) mergées AVANT le contrôle du pilote (même incident que L, PR #8). Relecture
après coup : aucun e-mail, secret ni token ; « bensa » n'apparaît que dans des chemins Windows des kernels.
Éléments personnels : témoignages verbatim, coûts (~336 $), « l'histoire de sa vie ». Yanis : on garde,
tâche 19.

## 3. Décisions de Yanis

- Status bar : « je suis le seul maître de la status bar » → plus aucune consigne de relevé dans les
  kernels (mémoire `priorite-memoire-pas-status-bar` mise à jour).
- « Test hypothétique » (proposé par M.2) : « de la théorisation sous conditions, une vue de l'esprit,
  pour mieux cartographier ce qui restera à faire » → tâche 21, en phase 2 (convergence), pas un projet.
- Ordre réel de la vague : Yanis a fait M.2 AVANT M.1 : « j'ai dû d'abord me souvenir de comment c'était
  construit, puis j'ai attaqué le morceau de pourquoi je me suis arrêté là ». Patron conseillé aux contrats N.
- Questions des contrats N : proposées par le pilote, écrites dans les kernels ; Yanis « avisera » dans les séances.

## 4. Contrats N (kernels écrits)

- N.1 « rôles + Scrum » : QUI devait faire avancer la chaîne (4 personas, salle virtuelle, cérémonies,
  26–27/05, mis de côté le 01/06). Complète M.2 F7 « chaîne × persona : commencé, pas assemblé ».
- N.2 « RAG + vision » : POURQUOI tout cela existait (vision du 26/05, RAG jamais construit). Répond à
  l'ANCRAGE de M.1/M.2.
- La vague 8 remonte le temps (26/05, avant la chaîne) : la mémoire se reconstruit de l'arrêt vers l'origine.

## 5. Questions transmises

- Q1 (SRD verrouillable ?), Q2 (`/rgate` global ?), Q3 (vocabulaire ARCHIVER) → convergence, via le kernel N.
- Q2 de L.1 (RAG abandonné ou reporté ?) → N.2. Tâche 7 (juges = personas ?) → N.1 Q1.

## Erreurs

- Worktree du pilote absent au démarrage (kernel M l'annonçait « à créer » implicitement) : rattrapé avant écriture.
- C2 contourné une 3e fois (merge avant contrôle) : le contrôle est désormais confié au contrat, qui le fait avant commit.
- Le pilote a demandé la status bar (C1 du kernel M) alors que la mémoire le déconseillait : corrigé par Yanis.
