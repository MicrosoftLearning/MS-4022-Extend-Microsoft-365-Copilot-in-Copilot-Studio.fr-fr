---
lab:
  title: "2.1\_: créer une action d’invite"
---

# Créer une action d’invite

Dans cet exercice, vous allez créer une action d’invite, tester l’invite dans Copilot Studio et tester l’invite dans un agent Copilot. Vous allez créer une action d’invite qui aide les utilisateurs à transformer leurs idées brutes en pitchs marketing organisés qui suivent un format et des instructions spécifiques.

Vous devriez terminer cet exercice en **15** minutes environ.

## Créer une invite personnalisée dans Copilot Studio

1. Ouvrez Copilot Studio dans votre navigateur web en accédant à [Copilot Studio](https://copilotstudio.microsoft.com) à l’adresse `https://copilotstudio.microsoft.com`.
1. Sélectionnez **Outils** dans le menu de navigation à gauche.
1. Sélectionnez **Nouvel outil**.
1. Dans la fenêtre contextuelle Nouvel outil, sélectionnez **Invite**. Vous accédez à l’interface utilisateur du générateur d’invites.
1. Dans la zone de texte **Instructions**, entrez `Create a marketing pitch for a product based on a `.
1. Placez votre curseur à la fin de la phrase que vous avez entrée, puis sélectionnez **Ajouter du contenu**.
1. Sélectionnez **Texte**.
1. Dans le champ **Nom**, entrez `draft`.
1.  Dans le champ **Exemple de données**, entrez `The Mighty Mechanical Pencil is new, exciting, and useful. It's not only the first of its kind pencil, but it's fun to use.`, puis sélectionnez **Fermer**.

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

## Configurez et publiez votre invite

Après avoir enregistré votre invite, la fenêtre Configurer pour une utilisation dans la **fenêtre Agent** s’affiche.

1. Dans le champ **Nom**, entrez `Create a Contoso Marketing Pitch`.
1. Dans la **description de l’agent pour savoir quand utiliser ce champ d’outil** , entrez `Create a marketing pitch that follows Contoso guidelines` , puis sélectionnez **Suivant**. Vous êtes redirigé sur la page **Créer une invite**.
1. Sélectionnez **Ajouter**.

## (Facultatif) Ajouter une action d’invite à un agent

Si vous avez terminé le labo précédent et créé un agent déclaratif, vous pouvez ajouter cette action à votre agent et mettre à jour les instructions de l’agent pour référencer l’action.

### Ajoutez l’outil d’invite

1. Dans la barre latérale de Copilot Studio, sélectionnez **Agents**.
1. Sélectionnez **Microsoft 365 Copilot**.
1. Sous **Agents**, sélectionnez l’agent **de support technique** auquel vous souhaitez ajouter l’action.
1. Dans la section **Outils** de la page, sélectionnez **Ajouter un outil**.
1. Sélectionnez le filtre **Invite**.
1. Sélectionnez l’invite **Créer un pitch marketing Contoso**.
1. Sélectionnez **Ajouter à l’agent**. L’outil est maintenant répertorié dans les **outils** de l’agent de support technique.

### Mettez à jour les instructions de l’agent

Mettez à jour les instructions de l’agent pour fournir des conseils sur l’utilisation de l’invite.

1. Dans la zone de texte **Instructions**, ajoutez ce qui suit au texte d’instructions existant : `Use the Contoso Marketing Pitch action to help marketing stakeholders craft pitches for products based on their draft ideas.`

Vous avez terminé l’exercice et créé un outil d’invite pour votre agent.
