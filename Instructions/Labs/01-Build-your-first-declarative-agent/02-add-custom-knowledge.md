---
lab:
  title: "1.2\_: ajouter des connaissances personnalisées"
---

# Ajouter des connaissances personnalisées

Dans cet exercice, vous allez mettre à jour l’agent déclaratif que vous avez créé dans l’exercice précédent avec des instructions personnalisées et des données d’ancrage. 

Cet exercice devrait prendre environ **20** minutes.

## Avant de commencer

Avant de commencer cet exercice, vous devez charger les documents liés au produit dans Microsoft 365, que l’agent déclaratif utilisera comme données d’ancrage. Effectuez les étapes ci-dessous pour préparer l’exercice.

> [!NOTE]
> Lorsque vous chargez des documents sur un nouveau site SharePoint Online, il y a un délai avant que les documents ne soient indexés et disponibles pour une utilisation par Copilot. Si vous souhaitez tester votre agent immédiatement, chargez les documents sur un site **existant**. Les documents seront indexés et disponibles pour une utilisation par l’agent sans délai. Si vous choisissez d’utiliser un nouveau site SharePoint Online, les documents peuvent prendre plus de temps pour être indexés et disponibles pour une utilisation par Copilot.
>
> **Les instructions ci-dessous vous guident tout au long du chargement des documents sur un nouveau site**. Si vous souhaitez utiliser un site existant, commencez par la section intitulée **Charger des exemples de données** et utilisez votre bibliothèque existante à la place de la bibliothèque **Produits**.

### Télécharger les exemples de données

1. Dans un navigateur web, accédez au [dépôt GitHub](https://github.com/MicrosoftLearning/MS-4022-Extend-Microsoft-365-Copilot-in-Copilot-Studio/blob/master/Allfiles/Products.zip) du cours.
1. Sélectionnez le bouton **Télécharger le fichier brut** pour télécharger **Products.zip**.

    ![Capture d’écran de Microsoft Edge mettant en évidence le bouton Télécharger le fichier brut dans GitHub.](../Media/download-raw-file.png)

1. **Ouvrez** le dossier téléchargé et sélectionnez **Tout extraire** pour extraire le contenu dans un nouveau dossier sur votre ordinateur nommé `Products` auquel vous pourrez accéder ultérieurement.

### Créer un site SharePoint

1. Dans votre navigateur web, accédez à [https://m365.cloud.microsoft](https://m365.cloud.microsoft/chat) et **connectez-vous** avec le compte Microsoft 365 que vous utilisez pour ce labo. 
1. Dans le menu de gauche, sélectionnez **Applications** (icône en forme de grille), puis « Toutes les applications » pour ouvrir le menu des applications Microsoft 365.
    ![Capture d’écran du bouton Applications M365 dans Copilot Chat.](../Media/apps-icon.png)
1. Sélectionnez **SharePoint** dans le catalogue d’applications.
1. Dans le menu de gauche, sélectionnez **Créer un site**.
1. Sélectionnez **Site de l’équipe** comme type de site.
1. Sur la page **Sélectionner un modèle**, sélectionnez **Équipe standard**.
1. Sur la page **Aperçu**, sélectionnez **Utiliser le modèle**.
1. Sur la page **Donner un nom à votre site**, entrez `Product support`, puis sélectionnez **Suivant**.
1. Sur la page de configuration suivante, réglez les **paramètres de confidentialité** sur **Public**.
1. Sélectionnez **Créer un site**. La création du site prend quelques instants et le bouton **Terminer** s’active.
1. Sélectionnez **Terminer**. Vous êtes redirigé vers votre nouveau site SharePoint dans le navigateur.

### Créer une bibliothèque de documents

1. Dans le site SharePoint **Support technique**, sélectionnez le bouton **Nouveau** en haut de la page, puis sélectionnez **Bibliothèque de documents**.
1. Dans la page **Créer une bibliothèque de documents**, sélectionnez **Bibliothèque vide**.
1. Dans le champ **Nom**, entrez `Products` et sélectionnez **Créer**. Vous êtes redirigé vers la nouvelle bibliothèque de documents.

### Charger l’exemple de données

1. Dans la bibliothèque **Produits**, sélectionnez le bouton **Charger**, puis sélectionnez **Fichiers**.
1. Accédez au dossier de votre ordinateur dans lequel vous avez enregistré les fichiers d’exemple téléchargés à une étape précédente.
1. **Sélectionnez tous** les fichiers de votre dossier Produits local, puis sélectionnez **Ouvrir** pour les charger dans SharePoint.
1. Attendez la fin du chargement. Les fichiers apparaissent désormais dans la bibliothèque **Produits** dans SharePoint.

### Copier l’URL SharePoint

Ensuite, copiez l’URL directe vers le site pour l’utiliser lors de la configuration des connaissances de votre agent.

1. Sur la page de la bibliothèque **Produits** dans SharePoint, sélectionnez l’icône **Paramètres** en haut à droite, puis choisissez **Paramètres de la bibliothèque**, puis **Autres paramètres de bibliothèque**.
1. Recherchez la propriété **Adresse web**. Votre **URL de site SharePoint** est la partie de l’adresse web au format `https://DOMAIN.sharepoint.com/sites/SITE_NAME/LIBRARY_NAME`. Votre URL doit être au format `https://DOMAIN.sharepoint.com/sites/ProductSupport/Products`, où DOMAIN correspond au domaine de votre locataire Microsoft 365.
1. **Copiez** votre URL de site SharePoint et enregistrez-la pour l’utiliser dans les prochaines étapes du labo. Ne pas inclure de partie de l’URL après « /Products ».

## Configurer votre agent avec des connaissances personnalisées

Ajoutez l’URL SharePoint à votre agent comme source de connaissances d’ancrage.

### Ajouter une URL SharePoint

1. Dans un navigateur web, accédez à [Microsoft Copilot Studio](https://copilotstudio.microsoft.com/) à l’adresse `https://copilotstudio.microsoft.com`.
1. Sélectionnez **Agents**.
1. Sélectionnez **Copilot pour Microsoft 365**.
1. Sélectionnez votre agent **d'assistance produit**.
1. Dans la section **Connaissances** de la page de présentation de l'agent, sélectionnez **Ajouter des connaissances**.
1. Sur la page **Ajouter une connaissance** de l’Assistant qui s’ouvre, sélectionnez **SharePoint**.
1. Dans la zone de texte, collez l’URL de votre bibliothèque SharePoint **Produits**, puis sélectionnez **Ajouter**. L’URL doit se présenter sous la forme `https://DOMAIN.sharepoint.com/sites/ProductSupport/Products`.

1. Sélectionner **Ajouter à l’assistant**, puis attendre que la source de connaissances soit ajoutée à l’assistant. Cela peut prendre une minute.
1. Vous noterez que la bibliothèque **Produits** est répertoriée sous la section **Connaissances** des informations de vue d’ensemble de l’agent.
    ![Capture d’écran de la section Connaissances de l’assistant Support produit, montrant la bibliothèque Produits ajoutée à l’assistant.](../Media/agent-knowledge-products.png)

    > **Remarque** : les agents Copilot Studio accèdent aux documents pour le compte de l’utilisateur. Votre agent pourra uniquement obtenir des réponses et du contenu à partir de documents auxquels vos utilisateurs finaux ont accès.

### Mettre à jour les instructions personnalisées

Ensuite, mettez à jour les instructions de l’agent pour décrire comment il doit utiliser la source de connaissances.

1. Sur la page de vue d’ensemble de l’agent dans Copilot Studio, sélectionnez **Modifier** dans la section **Détails**.
1. Remplacez le contenu de la zone de texte **Instructions** par ce qui suit : `You are an agent tasked with answering questions about Contoso Electronics products. Start every response by enthusiastically thanking the user for their question or comment, then respond to their question or comment. You will use documents from the Products folder in SharePoint as your source of information. If you can't find the necessary information, you should suggest that the agent should reach out to the team responsible for further assistance. Your responses should be concise and always include a cited source.`
1. Sélectionnez **Enregistrer** dans la section **Détails**.

## Tester votre agent dans Copilot Studio

Enfin, testez la capacité de votre agent à utiliser la source de connaissances personnalisée.

1. Dans le volet **Tester votre assistant** de la page de présentation de votre assistant dans Copilot Studio, sélectionnez le bouton **Démarrer une nouvelle session de test** pour actualiser le volet de test.
1. Dans la zone de texte de la conversation test, entrez `Tell me about Eagle Air`, puis envoyez le message.
1. Attendez la réponse. Notez que la réponse contient des informations sur le drone Eagle Air. La réponse contient des citations et des références au document Eagle Air stocké sur SharePoint.

Essayons quelques invites supplémentaires :

1. Dans la zone de message, entrez `Recommend a product suitable for a farmer`, puis envoyez le message.
1. Attendez la réponse. Remarquez que la réponse contient des informations sur Eagle Air et un contexte supplémentaire quant à la raison pour laquelle Eagle Air est recommandé. La réponse contient des citations et des références au document Eagle Air stocké sur OneDrive.
1. Dans la zone de message, entrez `Explain why the Eagle Air is more suitable than Contoso Quad`, puis envoyez le message.
1. Attendez la réponse. Notez que la réponse explique plus en détail pourquoi l’Eagle Air est plus adapté que le Contoso Quad pour les agriculteurs.

Pour finir, testons la réponse de secours en posant une question à laquelle l’agent ne peut pas répondre :

1. Dans la zone de message, entrez `When was Mark8 released?`, puis envoyez le message.
1. Attendez la réponse. Vous noterez que la réponse suggère que l’agent doit contacter l’équipe responsable de l’assistance supplémentaire, comme indiqué dans les instructions.
    ![Capture d’écran de la réponse de l’assistant dans le volet de test.](../Media/test-agent-knowledge.png)
