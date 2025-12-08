---
lab:
  title: "3.1\_: créer un outil de connecteur"
---

# Créer un outil de connecteur

Dans cet exercice, vous allez configurer un outil de connecteur pour un agent déclaratif dans Copilot Studio. Vous allez utiliser le connecteur « SharePoint - Liste de dossiers » pour récupérer une liste de fichiers à partir d’un dossier Produits qui contient des fichiers de prise en charge des produits.

Vous devriez terminer cet exercice en **15** minutes environ.

## Avant de commencer

Cet exercice se concentre sur l’ajout d’outils de connecteur à un agent existant. Cet exercice part des principes suivants :

1. Vous avez déjà créé un agent déclaratif **Support technique** dans Copilot Studio. Si vous avez besoin d’instructions pour créer un agent déclaratif, consultez : [Créer un agent déclaratif](../01-Build-your-first-declarative-agent/01-create-declarative-agent.md).
1. Vous disposez d’un site SharePoint intitulé **Support technique** qui contient une bibliothèque de documents nommée **Produits** contenant des fichiers avec des exemples de données produit. Pour obtenir des instructions, consultez la section intitulée **Avant de commencer** dans l’exercice : [Ajouter des connaissances personnalisées](../01-Build-your-first-declarative-agent/02-add-custom-knowledge.md).

## Créer un outil de connecteur SharePoint à partir d’un connecteur prédéfini

Créez un outil de connecteur à l’aide du connecteur prédéfini du dossier de listes SharePoint et ajoutez-le à l’agent.

1. Dans votre navigateur web, accédez à [Copilot Studio](https://www.copilotstudio.microsoft.com) à l’adresse `https://www.copilotstudio.microsoft.com`.
1. Dans la barre latérale , sélectionnez **Agents**.
1. Sélectionnez **Microsoft 365 Copilot**.
1. Sous **Agents**, sélectionnez votre agent de **support produit**.
1. Sous **Outils**, sélectionnez **Ajouter un outil**.
1. Dans la fenêtre **Ajouter un outil**, sélectionnez le bouton **Connecteur** pour filtrer les outils Connecteur, puis entrez `SharePoint` dans la barre **Rechercher** et sélectionnez **Rechercher**. Attendez que les connecteurs appropriés s’affichent dans la fenêtre.
1. Parcourez et sélectionnez le connecteur SharePoint **Dossier de listes**.
    ![Capture d’écran de la fenêtre Ajouter un outil mettant en évidence le connecteur Dossier de liste.](../Media/add-tool-list-folder.png)
1. La fenêtre modale affiche une connexion pour le connecteur SharePoint. Une coche verte s’affiche en regard du connecteur lorsque votre connexion est active. Vous pouvez sélectionner le **...** pour afficher les détails de la connexion. Si l’état est `Not connected`, sélectionnez la liste déroulante en regard de **Non connecté** et sélectionnez **Créer une connexion**.
    ![Capture d’écran de la fenêtre Ajouter un outil mettant en évidence le bouton Créer une nouvelle connexion.](../Media/create-new-connection.png)
1. Sur la page **Se connecter à SharePoint**, sélectionnez **Se connecter directement (services cloud)**, puis sélectionnez **Créer**.
1. Vous êtes invité à vous connecter. Connectez-vous à l’aide du compte M365 que vous utilisez pour l’exercice.
1. Sur la page **Ajouter un outil**, une fois la connexion établie, sélectionnez **Ajouter et configurer** pour ajouter l’outil à votre assistant.
1. Confirmez que l’outil **Dossier de liste - connecteur** figure dans la section **Outils** de votre assistant.
    ![Capture d’écran de la section Outils de l’assistant Support produit après l’ajout de l’outil connecteur.](../Media/connector-tool-added.png)

## Configurer l’outil connecteur pour votre agent

Configurez les propriétés de l’outil connecteur pour l’agent.

1. Dans la page de l’agent **Support produit**, sous **Outils**, sélectionnez l’outil **Dossier de listes : connecteur** que vous avez ajouté dans la section précédente.
1. Dans la zone de texte **Nom**, entrez `List product support files`.
1. Dans la zone de texte **Description**, entrez `List product support files available in the Products folder`.
1. Sélectionnez le bouton bascule en regard de **Détails supplémentaires** pour afficher des propriétés supplémentaires.
1. Dans la zone de texte **Description** de la section **Détails supplémentaires**, entrez « Veuillez vous connecter pour accéder au site SharePoint Support produit. »
1. Dans la section **Entrée**, recherchez l’entrée **Adresse du site**. Dans la zone de texte **Valeur**, entrez l’URL de votre site SharePoint **Support technique** au format `https://DOMAIN.sharepoint.com/sites/ProductSupport`, puis sélectionnez **Terminé**.
1. Ensuite, recherchez l’entrée **Identificateur de fichier**. Définissez le champ **Remplir à l’aide de** sur **Valeur personnalisée** dans la liste déroulante.
1. Dans la zone de texte **Valeur** de **Identificateur de fichier**, entrez `Products`.
1. Sélectionnez **Enregistrer** en haut de la page pour enregistrer vos modifications.
   
## Modifier les instructions de l’agent

Nous allons également mettre à jour les instructions de votre agent, en fournissant des conseils à l’agent pour savoir comment utiliser l’outil connecteur.

1. Dans la section **Détails** de votre assistant **Support produit** dans Copilot Studio, sélectionnez **Modifier**.
1. Dans la zone de texte **Instructions**, ajoutez ce qui suit au texte d’instructions existant : `When asked about available support resources, use the SharePoint connector to list the files in the Products folder and let the user know the SharePoint Connector was used.`
1. Cliquez sur **Enregistrer**.

## Tester votre agent avec l’outil

1. Développez le volet **Tester votre agent** sur le côté droit de la page des détails de votre agent.
1. Sélectionnez le bouton **Démarrer une nouvelle session de test** dans le volet de test pour charger les dernières modifications de votre assistant.
1. Dans la zone de message, entrez `What product support files are available?` puis envoyez le message.
1. Notez que votre assistant répond par un commentaire sur le connecteur utilisé, comme indiqué, et répertorie les fichiers disponibles dans le dossier Produits.
    ![Capture d’écran des résultats du volet de test lors du test du connecteur de dossier de liste.](../Media/test-agent-connector.png)

Vous avez vérifié que votre outil de connecteur fonctionne comme prévu dans votre assistant et vous avez terminé cet exercice.
