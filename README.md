# Anti Brain Fry

[English version](README.en.md)

**Chaque fin de tâche de ton agent IA devient une carte de 5 secondes : pourquoi tu l'avais lancé, ce qui est fait, une seule décision.**

Par Major. Gratuit et open source.

Tu as 10 agents qui tournent. Quand l'un d'eux a fini, tu ouvres l'onglet et tu tombes sur un pavé : fichiers modifiés, 140 lignes de code, trois options techniques et deux questions. Tu ne sais plus pourquoi tu l'avais lancé. Tu refermes en te disant « plus tard ». Le soir, tu as le cerveau grillé : c'est le « brain fry ».

Ce skill transforme la fin de chaque tâche en une carte. Tu tapes 1 ou 2, c'est clos.

## Avant / après

Il est 16 h 30. Tu rouvres un onglet lancé à 14 h pour un bug de paiement. Entre-temps, tu as géré 8 autres sujets.

**Avant**

> J'ai terminé l'analyse du fichier `webhook-handler.ts` ainsi que des dépendances dans `/utils/retry.js`. Voici les modifications apportées : 1. J'ai remplacé la boucle `while` par un système de backoff exponentiel pour éviter les erreurs 429 côté API. 2. J'ai ajouté un logger intermédiaire dans la table `events_log`... [140 lignes de code] Quelle approche préfères-tu pour la gestion du cache, et veux-tu que je lance les tests unitaires sur staging ou que je modifie d'abord le schéma de base de données ?

**Après**

🎯 **Pourquoi tu m'as lancé (il y a 2 h) :** ne plus perdre de ventes quand le paiement plante au premier essai.

⚡ **Ce qui est fait :** le système réessaie maintenant automatiquement 3 fois en arrière-plan, sans bloquer le client.

❓ **L'unique décision :** si ça plante encore après 3 essais, j'envoie au client un email avec un lien de paiement de secours ?

**[ 1 : Oui, envoie l'email ]**   |   **[ 2 : Non, alerte-moi sur Slack ]**

4 secondes de lecture. Tu tapes 1. Le sujet est clos.

## Ce que fait le skill

| | |
|---|---|
| **Te remet dans le contexte** | Une phrase sur le pourquoi, côté bénéfice. Tu n'as plus à relire l'historique. |
| **Te donne le résultat** | Ce que tu verras, pas la façon dont c'est codé. |
| **Une seule décision** | L'agent tranche lui-même ce qui est réversible et ne te remonte que ce qui t'engage : argent, client, publication, suppression. |
| **Deux réponses** | La recommandation de l'agent en 1, l'autre option en 2. |
| **Zéro pavé** | Code, fichiers et logs restent accessibles par lien, jamais collés dans ta fenêtre. |

## Installation

**Claude Code, Codex, Cursor et les autres agents (skills.sh)**

```bash
npx skills add MAJOR-AGV/anti-brain-fry --skill anti-brain-fry-fr
```

**Hermes Agent**

```bash
hermes skills install MAJOR-AGV/anti-brain-fry/skills/anti-brain-fry-fr
```

## L'activer sur toutes tes tâches

Un skill se déclenche quand l'agent le juge utile. Pour qu'il s'applique à chaque fin de tâche, ajoute cette ligne dans ton `CLAUDE.md` (Claude Code) ou ton `AGENTS.md` (Codex, Cursor et les autres) :

```
À la fin de chaque tâche, applique le skill anti-brain-fry-fr.
```

## À propos de Major

Major (Anthony Gonnet Vandepoorte) crée et pilote des entreprises avec des agents IA.

[YouTube](https://www.youtube.com/@major-agv) · [Instagram](https://www.instagram.com/major_agv) · [X](https://x.com/majoragv) · [LinkedIn](https://www.linkedin.com/in/anthonygonnetvandepoorte)

Si ce skill t'a rendu un peu d'énergie, **mets une étoile au dépôt**. Ça aide d'autres fondateurs à le trouver.
