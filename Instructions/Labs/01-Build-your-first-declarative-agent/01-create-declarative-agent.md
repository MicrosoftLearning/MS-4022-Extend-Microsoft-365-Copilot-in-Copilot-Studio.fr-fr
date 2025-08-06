---
lab:
  title: "1.1\_: créer un agent déclaratif"
---

# Créer un agent déclaratif

Dans cet exercice, vous allez créer un agent déclaratif à l’aide de l’IA générative, affiner les instructions, publier l’agent sur Microsoft 365 et tester l’agent dans Microsoft 365 Copilot.

Cet exercice devrait prendre environ **20** minutes.

## Créer un agent déclaratif à l’aide de l’IA générative

Commencez par créer un agent déclaratif dans Copilot Studio. Utilisez l’IA générative pour rédiger les instructions et les propriétés de l’agent.

1. Dans un navigateur web, accédez à [Microsoft Copilot Studio](https://copilotstudio.microsoft.com/) à l’adresse `https://copilotstudio.microsoft.com`.
1. Connectez-vous à l’aide d’un compte professionnel ou scolaire avec lequel vous êtes autorisé à créer dans Copilot Studio.
1. Si vous y êtes invité sur la page **Bienvenue dans Microsoft Copilot Studio**, sélectionnez votre pays/région, puis sélectionnez **Démarrer**.
1. Si la fenêtre contextuelle **Bienvenue dans Copilot Studio !** s’affiche, sélectionnez **Ignorer**.
1. Une fois dans Copilot Studio, vous commencerez probablement par l’interface conversationnelle pour créer un agent. Cet assistant vous aide à configurer un agent *personnalisé*.  Sélectionnez **...**, puis **Annuler la création de l’agent** pour quitter cet assistant.  Sélectionnez **Quitter** pour confirmer.

    ![Capture d’écran de l’interface conversationnelle pour la création d’un agent personnalisé.](../Media/custom-agent-wizard.png)

1. Accédez à **Agents** dans le volet de navigation de gauche.
1. Sélectionnez **Microsoft 365 Copilot** dans la page des agents.
1. Dans la page de l’agent **Microsoft 365 Copilot**, sélectionnez **Ajouter** dans la section Agents.

    ![Capture d’écran de la page d’agent Microsoft 365 Copilot dans Copilot Studio.](../Media/add-copilot-agent.png)

    Vous êtes redirigé vers l’expérience de création conversationnelle dans laquelle vous pouvez décrire l’agent que vous souhaitez créer.

1. Vous êtes invité à décrire ce que vous souhaitez que votre agent fasse.  Dans la zone de texte **Tapez votre message** dans l’interface conversationnelle, entrez les éléments suivants :

    ```md
    I'd like to create a product support agent that answers questions related to Contoso Electronics products.
    ```

1. Sélectionnez **entrer** ou **envoyer** pour envoyer votre message.
1. Si vous êtes invité à suggérer un nom pour votre assistant, entrez `Product support` et envoyez votre message.
1. Sélectionnez **Ignorer pour configurer** en haut de l’interface conversationnelle pour afficher la page de vue d’ensemble de l’agent et passer en revue ce que l’IA générative a configuré jusqu’à présent.

## Configurer l’agent et définir des instructions

Ensuite, mettez à jour les propriétés et les métadonnées de l’agent manuellement.

1. Passez en revue le **nom** défini par l’Assistant d’IA générative pour votre agent. Mettez à jour le nom vers `Product support`.
1. Mettez à jour la valeur de la propriété **description** sur `A product support agent that can answer queries about Contoso Electronics products`.
1. Dans la zone de texte **Instructions**, entrez :
  
    ```md
        You are an agent tasked with answering questions about Contoso Electronics products. Start every response to the user with "Thanks for using a Copilot agent!\n\n" and then answer the questions and help the user.
    ```

1. Sélectionnez le bouton **Créer** en haut de la page pour créer l’agent.  Après quelques instants, vous êtes redirigé vers la page de vue d’ensemble de l’agent.

## Tester l’agent dans Copilot Studio

Ensuite, testez le comportement de votre agent dans le volet de test dans Copilot Studio avant de le publier sur Microsoft 365 Copilot.

1. Dans la page vue d’ensemble de l’agent **Support produit**, vous noterez dans la section **Détails de la publication** que l’agent n’est pas encore publié.

    ![Capture d’écran de la page de l’agent Support technique avant la publication.](../Media/product-support-publish-details.png)

1. Si le volet **Tester votre agent** n’est pas affiché à droite des informations de vue d’ensemble de l’agent, sélectionnez le bouton **Tester** en regard du bouton Publier pour ouvrir le volet de test.
1. Dans la zone de texte, entrez `What can you do?` et envoyez votre message.
1. Attendez la réponse. Notez comment la réponse commence par le texte « Merci d’utiliser un agent Copilot ! » comme indiqué dans les instructions que vous avez définies pour l’agent précédemment.

    ![Capture d’écran de la conversation du volet de test avec l’agent Support technique.](../Media/product-support-test-pane-1.png)

    Vous noterez également que l’agent a actuellement des instructions, mais qu’il n’a pas encore de sources de connaissances ou d’actions personnalisées. Vous n’avez pas encore configuré l’agent pour répondre aux questions sur les produits Contoso. Vous verrez cela dans le prochain exercice.

    > [!NOTE]
    > Si vous devez modifier votre agent, fermez le volet de test et sélectionnez **Modifier** dans la section **Détails** de la page de vue d’ensemble de l’agent. Avant de tester à nouveau, sélectionnez le bouton **Actualiser** à l’intérieur du volet de test pour charger les dernières modifications.

## Publier l’agent sur Microsoft 365 Copilot

Ensuite, publiez votre agent déclaratif sur Microsoft 365 Copilot. Dans la page de vue d’ensemble de l’agent **Support technique** :

1. Cliquez sur le bouton **Publier**. Vous êtes invité à entrer des informations sur votre agent qui seront visibles pour les utilisateurs dans Microsoft 365 Copilot et Microsoft Teams.

    > [!NOTE]
    > Les informations de ce formulaire sont utilisées pour remplir l’entrée de catalogue dans les catalogues Office et Teams de votre organisation et la liste des applications intégrées du Centre d’administration Microsoft. Elles ne sont pas utilisées par le modèle de langage Microsoft 365 Copilot pour appeler votre agent.

1. Dans la zone de texte **Description courte**, entrez `Answers questions about Contoso Electronics products`.
1. Acceptez les suggestions par défaut pour les champs restants.
1. Sélectionnez **Publier**.
1. Patientez jusqu’à ce que les agents soient publiés.  Ne fermez pas la fenêtre modale pendant la publication. Cela peut prendre quelques minutes.

    > [!NOTE]
    > Lorsque vous sélectionnez Publier, une ressource de bot correspondant à votre agent est provisionnée dans l’environnement Microsoft Entra ID de votre locataire. La ressource permet aux utilisateurs d’interagir avec l’agent dans Microsoft Teams.

1. Une fois l’agent publié, la fenêtre **Options de disponibilité** s’affiche.
1. Sous **Lien de partage**, sélectionnez **Copier** pour copier le lien de partage de votre agent, puis sélectionnez **Terminé**.
1. Vous noterez que la section **Détails de publication** de la page de vue d’ensemble de votre agent indique que l’agent a été publié.

    ![Capture d’écran de la section des détails de publication de l’agent de support technique dans Copilot Studio.](../Media/publish-details.png)

    Si vous avez besoin de copier à nouveau le lien de partage, sélectionnez **Options de disponibilité** dans la section **Détails de publication**.

1. Ouvrez un nouvel onglet dans votre navigateur web, collez le lien de partage dans la barre d’URL, puis sélectionnez **Entrée**. Une fenêtre modale s’affiche avec une vue d’ensemble de votre agent. Elle affiche les informations accessibles à l’utilisateur que vous avez fournies sur votre agent lors de la publication, ainsi que les autorisations requises par votre agent.

    ![Capture d’écran de la fenêtre modale fournissant des informations de vue d’ensemble pour l’agent Support technique avant son ajout à Microsoft 365 Copilot.](../Media/product-support-add-agent.png)

1. Sélectionnez **Ajouter** pour ajouter votre agent à Microsoft 365 Copilot.
1. Attendez que votre agent soit ajouté. Votre agent est lancé dans Microsoft 365 Copilot.

## Tester l’agent déclaratif dans Microsoft 365 Copilot

Ensuite, nous allons exécuter l’agent déclaratif dans Microsoft 365 Copilot et valider ses fonctionnalités dans les expériences **contextuelles** et **immersives**.

Si vous avez suivi les étapes précédentes, vous êtes actuellement dans l’expérience de l’agent **immersif**. Vous noterez dans le volet **Agents**, à droite, que **Support technique** est sélectionné en tant qu’agent avec lequel vous discutez directement.

![Capture d’écran de l’expérience immersive avec l’agent Support technique dans Microsoft 365 Copilot.](../Media/product-support-immersive.png)

1. Dans la zone de texte, entrez `What can you do?` et envoyez votre message.
1. Envoyez le message et attendez la réponse. Vous noterez que la réponse commence par le texte « Merci pour votre question ! » conformément aux instructions que vous avez fournies pour l’agent.

Continuons dans le navigateur et testons l’expérience **contextuelle**.

1. Au-dessus du volet **Agents** dans la barre latérale, sélectionnez **conversation instantanée** ou **M365 Copilot** pour quitter votre conversation immersive avec l'agent du **support produit** et discuter avec Microsoft 365 Copilot.

    ![Capture d’écran du bouton Copilot dans la barre latérale de Microsoft 365 Copilot.](../Media/select-copilot.png)

1. Dans la zone de message, entrez le symbole <kbd>@</kbd>. Le menu volant s’affiche avec une liste des agents disponibles.

    ![Capture d’écran du menu volant des agents dans Microsoft 365 Copilot dans Microsoft Edge.](../Media/copilot-agents-flyout.png)

1. Dans le menu volant, sélectionnez **Support technique**. Notez le message d’état au-dessus de la zone de message. Il affiche **Conversation avec le support technique**, ce qui signifie que vous utilisez l’expérience contextuelle de l’agent.

    ![Capture d’écran de Microsoft 365 Copilot dans Microsoft Edge. Le message d’état « Conversation avec le support technique » est mis en surbrillance.](../Media/product-support-in-context.png)

1. Dans la zone de texte, entrez `What can you do?` et envoyez votre message.

1. Attendez la réponse. Vous noterez que la réponse commence par le texte « Merci pour votre question ! » conformément aux instructions que vous avez fournies pour l’agent.

1. Pour quitter l’expérience contextuelle, sélectionnez la croix (X) dans le message d’état. Notez que le message d’état est supprimé et qu’un message s’affiche dans la fenêtre de conversation qui indique que vous ne discutez plus avec l’agent.

    ![Capture d’écran de Microsoft 365 Copilot dans Microsoft Edge. L’icône de croix dans le message d’état de l’agent est mise en surbrillance.](../Media/exit-in-context-experience.png)

Vous avez maintenant testé votre agent dans les expériences immersives et contextuelles dans Microsoft 365 Copilot.
