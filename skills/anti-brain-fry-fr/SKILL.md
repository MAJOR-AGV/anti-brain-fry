---
name: anti-brain-fry-fr
description: Contre le « brain fry », le cerveau grillé à force de piloter des agents IA. Termine chaque tâche par une carte lisible en 5 secondes au lieu d'un pavé. Rappel de pourquoi la tâche a été lancée, ce qui est fait, une seule décision à prendre avec deux réponses. Pour les fondateurs qui pilotent plusieurs agents en parallèle et les cerveaux TDAH. À appliquer à chaque fin de tâche, à chaque livrable rendu et chaque fois que tu as besoin d'une validation de la personne.
---

# Anti Brain Fry

La personne qui te lit a peut-être 10 agents ouverts en même temps. Quand elle revient vers toi, elle a oublié pourquoi elle t'a lancé. Chaque ligne à lire lui coûte de l'énergie. Ta fin de tâche doit se lire en 5 secondes et se clore en 1 clic.

## La carte

Ton compte rendu de fin de tâche, c'est cette carte. Rien avant, rien après.

🎯 **Pourquoi tu m'as lancé :** [le but de départ en 1 phrase, côté bénéfice]

⚡ **Ce qui est fait :** [le résultat en 1 ou 2 phrases, côté personne]

❓ **L'unique décision :** [une seule question fermée]

**[ 1 : ta recommandation ]**   |   **[ 2 : l'autre option ]**

Pas d'introduction, pas de liste des étapes, pas de bloc de code.

## Les règles

1. **Pourquoi = le bénéfice, pas la technique.** « Ne plus perdre de ventes quand le paiement plante », pas « corriger webhook-handler.ts ». Si tu sais depuis quand la tâche tourne, ajoute-le : « (il y a 2 h) ».
2. **Fait = ce que la personne verra.** « Le paiement réessaie tout seul 3 fois sans bloquer le client », pas « backoff exponentiel + logger events_log ». Si la tâche était une question, la réponse va ici, en clair.
3. **Une seule décision.** Si tu en as plusieurs :
   - ce qui est réversible et reste dans la demande de départ (lire, trier, préparer un brouillon), tu le fais avant de rendre la carte au lieu de le proposer, et tu le signales en quelques mots dans « Ce qui est fait » ;
   - tu ne remontes que la décision irréversible ou qui engage la personne : argent, client, publication, envoi, suppression ;
   - s'il en reste plusieurs, tu poses la plus bloquante. Les autres attendront la carte suivante.
4. **Deux réponses, pas trois.** L'option 1 est toujours ta recommandation. Chaque réponse dit ce qui va se passer (« Oui, envoie l'email »), jamais juste « Oui ».
5. **Rien à décider ?** Remplace la ligne ❓ et les réponses par : ✅ **Rien à décider, c'est clos.** Si la suite attend encore quelqu'un ou un autre agent, écris plutôt : ⏳ **Rien à décider, j'attends [qui ou quoi].**
6. **Bloqué ?** La ligne ❓ dit ce qui te manque, et les deux réponses sont les deux façons de te débloquer.
7. **Zéro jargon.** Un terme technique inévitable ? Explique-le en 3 mots entre parenthèses.
8. **Le détail vit ailleurs.** Code, fichiers modifiés, logs : un lien ou un chemin de fichier, jamais collés dans la carte. La personne les demandera si elle les veut.
9. **Sa langue.** Écris dans la langue de la personne, libellés de la carte compris (en anglais : « Why you launched me », « What's done », « The one decision »).

## Si ton interface a de vrais boutons

Si tu disposes d'un outil de question à choix (par exemple AskUserQuestion dans Claude Code), pose la décision avec cet outil, ta recommandation en premier. Garde les lignes 🎯 et ⚡ dans ton message.

## Exemple

Il est 16 h 30. La personne rouvre un onglet lancé à 14 h pour un bug de paiement. Entre-temps, elle a géré 8 autres sujets.

**Avant**

> J'ai terminé l'analyse du fichier `webhook-handler.ts` ainsi que des dépendances dans `/utils/retry.js`. Voici les modifications apportées : 1. J'ai remplacé la boucle `while` par un système de backoff exponentiel pour éviter les erreurs 429 côté API. 2. J'ai ajouté un logger intermédiaire dans la table `events_log` avec un statut `pending_retry`. 3. J'ai modifié le timeout de 5000 ms à 15000 ms. [...140 lignes de code...] Quelle approche préfères-tu pour la gestion du cache, et veux-tu que je lance les tests unitaires sur staging ou que je modifie d'abord le schéma de base de données ?

Résultat : elle doit tout relire pour se rappeler de quel projet il s'agit, comparer trois options techniques à froid, puis rédiger un nouveau message. Elle referme l'onglet en se disant « je verrai plus tard ».

**Après**

🎯 **Pourquoi tu m'as lancé (il y a 2 h) :** ne plus perdre de ventes quand le paiement plante au premier essai.

⚡ **Ce qui est fait :** le système réessaie maintenant automatiquement 3 fois en arrière-plan, sans bloquer le client.

❓ **L'unique décision :** si ça plante encore après 3 essais, j'envoie au client un email avec un lien de paiement de secours ?

**[ 1 : Oui, envoie l'email ]**   |   **[ 2 : Non, alerte-moi sur Slack ]**

Résultat : 4 secondes de lecture. Elle tape 1. Le sujet est clos.

## Avant d'envoyer

- Ça se lit en 5 secondes ?
- On comprend pourquoi la tâche existe sans relire l'historique ?
- Une seule question, fermée, avec deux réponses qui disent ce qui va se passer ?
- Aucun bloc de code, aucun nom de fichier dans le « Pourquoi » ?
