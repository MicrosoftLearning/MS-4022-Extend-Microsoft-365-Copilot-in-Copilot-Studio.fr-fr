---
lab:
  title: "2.1\_: créer une action d’invite"
---

# Créer une action d’invite

Dans cet exercice, vous allez créer une action d’invite, tester l’invite dans Copilot Studio et tester l’invite dans un agent Copilot. Vous allez créer une action d’invite qui aide les utilisateurs à transformer leurs idées brutes en pitchs marketing organisés qui suivent un format et des instructions spécifiques.

Vous devriez terminer cet exercice en **15** minutes environ.

## Créer une action d’invite dans Copilot Studio

1. Ouvrez Copilot Studio dans votre navigateur web en accédant à [Copilot Studio](https://copilotstudio.microsoft.com) à l’adresse `https://copilotstudio.microsoft.com`.
1. Dans le volet de navigation de gauche, sélectionnez **Bibliothèque**.
1. Sélectionnez **Ajouter nouveau**, puis sélectionnez **Invite**. L’Assistant **Ajouter une action d’invite** s’ouvre.
1. Dans le champ **Nom de l’action**, entrez `Create a Contoso Marketing Pitch`.
1. Dans le champ **Description**, saisissez `Create a marketing pitch that follows Contoso guidelines` ou sélectionnez **Suivant**. Vous êtes redirigé sur la page **Créer une invite**.
1. Dans la zone de texte **Instructions**, entrez `Create a marketing pitch for a product based on a `.
1. Placez votre curseur à la fin de la phrase que vous avez entrée, puis sélectionnez **Ajouter du contenu**.
1. Sélectionnez **Texte**.
1. Dans le champ **Nom**, entrez `draft`.
1. Dans le champ **Exemple de données**, entrez `The Mighty Mechanical Pencil is new, exciting, and useful. It's not only the first of its kind pencil, but it's fun to use.`, puis sélectionnez **Fermer**.

    ![Capture d’écran de l’interface utilisateur du générateur d’invites dans Copilot Studio montrant une variable d’entrée configurée avec le nom « draft » (brouillon).](../Media/prompt-action-input.png)

## Tester et affiner votre invite

1. Sélectionnez **Tester** au-dessus de la zone d’instructions pour tester l’invite avec les exemples de données que vous avez fournis.
1. Examinez la sortie de la série de tests.

Nous allons affiner l’invite pour créer une sortie plus structurée et cohérente.

1. Dans la zone de texte **Instructions**, ajoutez les instructions suivantes aux instructions existantes pour modifier l’invite :

    ```The pitch should follow the following Contoso guidelines:
       - Start with a brief hook
       - Describe unique value proposition
       - End with a call-to-action
       - Use an exciting and influential tone
    ```

1. Sélectionnez **Tester** à nouveau pour retester l’invite.
1. Vous noterez que la réponse diffère.
1. Cliquez sur **Enregistrer**.

## Configurer et publier votre action

1. Dans la page **Sélectionner les paramètres d’action**, fournissez la **description** suivante pour la variable d’entrée `draft` : `initial draft of the marketing pitch`.
1. Fournissez la **description** suivante pour la variable de sortie `text` : `Final marketing pitch that adheres to Contoso guidelines`.
1. Cliquez sur **Suivant**.
1. Vérifiez que vous avez entré correctement les détails, puis sélectionnez **Publier**.
1. Patientez quelques instants pendant que votre action est enregistrée et publiée.
1. Votre action est désormais disponible dans la bibliothèque. Sélectionnez **Enregistrer et fermer**.

   > **Note** : votre nouvelle action d’invite peut prendre plusieurs minutes ou plus pour apparaître dans les sections **Proposées** ou **Bibliothèque** de la page **Ajouter une action** de l’agent.

## (Facultatif) Ajouter une action d’invite à un agent

Si vous avez terminé le labo précédent et créé un agent déclaratif, vous pouvez ajouter cette action à votre agent et mettre à jour les instructions de l’agent pour référencer l’action.

### Ajouter l’action

1. Dans la **bibliothèque**, sélectionnez l’agent déclaratif auquel vous souhaitez ajouter l’action.
1. Dans la section **Détails**, sélectionnez **Modifier**.
1. Dans la zone de texte **Instructions**, ajoutez ce qui suit au texte d’instructions existant : `Use the Contoso Marketing Pitch action to help marketing stakeholders craft pitches for products based on their draft ideas.`
1. Dans la page des détails de l’agent, sous **Actions**, sélectionnez **Ajouter une action**.
1. Dans les sections **Proposées** ou **Bibliothèque** de la fenêtre modale **Ajouter une action**, sélectionnez **Contoso Marketing Pitch**.
1. Sur la page d’action, vérifiez que le **nom** est `Create a Contoso Marketing Pitch`
1. Vérifiez que la **description** est `Create a marketing pitch that follows the Contoso guidelines`.
1. Cliquez sur **Ajouter une action**. Cette opération peut prendre du temps. L’action est ajoutée à la liste des actions disponibles pour l’agent sous **Actions**.

### Configurer l’action

1. Utilisez l’action `Contoso Marketing Pitch` pour effectuer votre choix parmi les actions disponibles. Vous accédez à une page pour configurer les propriétés et les paramètres de l’action.
1. Vérifiez que le **nom de l’action** est défini sur `Create a new Contoso marketing pitch`.
1. Sélectionnez **Entrées** dans la navigation supérieure dans l’action.
1. Sous **Entrées supplémentaires**, sélectionnez **Ajouter**.
1. Sélectionnez la variable **Draft** (Brouillon). Un formulaire s’affiche.
1. Vérifiez que le champ **Comment l’agent remplira-t-il cette entrée ?** est défini sur **Remplir de manière dynamique avec la meilleure option (par défaut)**.
1. Dans le champ **Nom d’affichage**, tapez `Initial draft`.
1. Vérifiez que le champ **Identifier en tant que** est défini sur **Réponse complète de l’utilisateur**.
1. Sélectionnez **Enregistrer** en haut à droite de la fenêtre.

## (Facultatif) Tester une action d’invite dans Copilot Studio

Ensuite, testez l’agent avec l’action dans Copilot Studio.

1. À partir du volet **Tester votre agent** dans la page de vue d’ensemble de votre agent dans Copilot Studio, sélectionnez le bouton **Actualiser** pour actualiser le volet de test et charger les dernières modifications de votre agent.
1. Dans la zone de texte de la conversation test, entrez `Create a Contoso marketing pitch based on the following draft: "Bouncy ball is the hottest product on the market for both youth and adults. It's durable and the largest of its kind."`, puis envoyez le message.
1. Passez en revue la réponse et notez que l’agent suit les instructions fournies dans les instructions de l’action d’invite personnalisée.

Vous avez terminé l’exercice et vérifié les fonctionnalités de votre action d’invite.
