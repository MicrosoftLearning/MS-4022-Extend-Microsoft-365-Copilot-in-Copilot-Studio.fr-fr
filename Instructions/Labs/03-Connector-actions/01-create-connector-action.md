---
lab:
  title: "3.1\_: créer une action de connecteur"
---

# Créer une action de connecteur

Dans cet exercice, vous allez configurer une action de connecteur pour un agent déclaratif dans Copilot Studio. Vous allez utiliser le connecteur « SharePoint - Liste de dossiers » pour récupérer une liste de fichiers à partir d’un dossier Produits qui contient des fichiers de prise en charge des produits.

Vous devriez terminer cet exercice en **15** minutes environ.

## Avant de commencer

Cet exercice se concentre sur l’ajout d’actions de connecteur à un agent existant. Cet exercice part des principes suivants :

1. Vous avez déjà créé un agent déclaratif **Support technique** dans Copilot Studio. Si vous avez besoin d’instructions pour créer un agent déclaratif, consultez : [Créer un agent déclaratif](../01-Build-your-first-declarative-agent/01-create-declarative-agent.md).
1. Vous disposez d’un site SharePoint intitulé **Support technique** qui contient une bibliothèque de documents nommée **Produits** contenant des fichiers avec des exemples de données produit. Pour obtenir des instructions, consultez la section intitulée **Avant de commencer** dans l’exercice : [Ajouter des connaissances personnalisées](../01-Build-your-first-declarative-agent/02-add-custom-knowledge.md).

## Créer une action de connecteur SharePoint

1. Dans votre navigateur web, accédez à [Copilot Studio](https://www.copilotstudio.microsoft.com) à l’adresse `https://www.copilotstudio.microsoft.com`.
1. Dans la **bibliothèque**, sélectionnez votre agent **Support technique**.
1. Sous **Actions**, cliquez sur **Ajouter une action**.
1. Dans la fenêtre **Ajouter une action**, entrez `SharePoint` dans la barre **Recherche**. Attendez que les actions pertinentes soient affichées dans la fenêtre.
1. Parcourez et sélectionnez l’action de connecteur **Liste de dossiers SharePoint**.
1. La fenêtre modale affiche une connexion pour le connecteur SharePoint. Une coche verte s’affiche en regard du connecteur lorsque votre connexion est active. Vous pouvez sélectionner le **...** pour afficher les détails de la connexion.
    ![Capture d’écran de l’état de la connexion SharePoint](../Media/SharePoint-connection.png)
1. Sélectionnez **Suivant** lorsque la connexion est active. Vous accédez à la page **Liste de dossiers** pour configurer les propriétés de l’action.
1. Dans la zone de texte **Nom**, entrez `List product support files`.
1. Dans la zone de texte **Description**, entrez `List product support files available in the Products folder`.
1. Vérifiez qu’**Authentification des utilisateurs finaux** est définie sur **Authentification utilisateur**.
1. Développez la section **entrées et sorties**.
1. Sélectionnez l’entrée **Adresse du site**.
1. Dans la zone de texte **Valeur**, entrez l’URL de votre site SharePoint **Support technique** au format `https://DOMAIN.sharepoint.com/sites/ProductSupport`, puis sélectionnez **Terminé**.
1. Sélectionnez l’entrée **Identificateur du fichier**.
1. Définissez **Comment l’agent remplira-t-il cette entrée ?** sur **Définir comme valeur** dans la liste déroulante, puis sélectionnez **Confirmer**.
1. Dans la zone de texte **Valeur**, entrez `Products`, puis sélectionnez **Terminé**.
1. Sélectionnez le bouton **Ajouter une action** et attendez que l’action SharePoint soit ajoutée à votre agent. L’action doit maintenant être répertoriée dans la section **Actions** de la page des détails de votre agent.

## Configurer l’action

1. Dans la section **Actions**, sélectionnez l’action **Répertorier les fichiers de support produit** pour ouvrir sa page de détails.
1. Accédez à l’onglet **Sorties**.
1. À des fins de test, sous **Choisir la façon dont le résultat de cette action s’affichera**, cochez la case intitulée **Envoyer un message immédiatement après l’exécution de l’action**. Une option de configuration supplémentaire s’affiche.
1. Sélectionnez la liste déroulante sous **Comment voulez-vous présenter les informations à l’utilisateur ?**, puis sélectionnez **Vous créez un message**. Une zone de texte s’affiche.
1. Dans la zone de texte **Message à afficher**, entrez `You used the SharePoint connector`, puis sélectionnez **Enregistrer** en haut de la page.

## Modifier les instructions de l’agent

Nous allons également mettre à jour les instructions de votre agent en fournissant des indications pour utiliser l’action du connecteur.

1. Dans la section **Détails** de votre agent **Support technique**, sélectionnez **Modifier**.
1. Dans la zone de texte **Instructions**, ajoutez ce qui suit au texte d’instructions existant : `When asked about available support resources, use the SharePoint connector to list the files in the Products folder.`
1. Cliquez sur **Enregistrer**.

## Tester votre agent avec l’action

1. Développez le volet **Tester votre agent** sur le côté droit de la page des détails de votre agent.
1. Sélectionnez le bouton **Actualiser** dans le volet de test pour charger les dernières modifications de votre agent.
1. Dans la zone de message, entrez `What product support files are available?` puis envoyez le message.
1. Vous noterez que votre agent répond avec le message « Vous avez utilisé le connecteur SharePoint », puis répertorie les fichiers disponibles dans le dossier Produits.

Vous avez vérifié que votre action de connecteur fonctionne comme prévu dans votre agent.
