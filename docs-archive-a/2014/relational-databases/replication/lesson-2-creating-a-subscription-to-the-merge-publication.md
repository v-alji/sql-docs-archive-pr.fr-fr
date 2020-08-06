---
title: 'Leçon 2 : Création d’un abonnement à la publication de fusion | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: 06722baa-9065-443e-b1d5-99036cf89074
author: rothja
ms.author: jroth
ms.openlocfilehash: 2ca4f9cdf9c40d80b428d65b4201be61c2ea3eae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611026"
---
# <a name="lesson-2-creating-a-subscription-to-the-merge-publication"></a><span data-ttu-id="84e3e-102">Leçon 2 : Création d'un abonnement à la publication de fusion</span><span class="sxs-lookup"><span data-stu-id="84e3e-102">Lesson 2: Creating a Subscription to the Merge Publication</span></span>
  <span data-ttu-id="84e3e-103">Dans cette leçon, vous allez créer l’abonnement à l’aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="84e3e-103">In this lesson, you will create the subscription using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="84e3e-104">Puis, vous définirez les autorisations sur la base de données d'abonnement et génèrerez manuellement l'instantané filtré des données du nouvel abonnement.</span><span class="sxs-lookup"><span data-stu-id="84e3e-104">You will then set permissions on the subscription database and manually generate the filtered data snapshot for the new subscription.</span></span> <span data-ttu-id="84e3e-105">Pour effectuer cette leçon, vous devez avoir terminé la leçon précédente, [Leçon 1 : Publication de données à l’aide de la réplication de fusion](lesson-1-publishing-data-using-merge-replication.md).</span><span class="sxs-lookup"><span data-stu-id="84e3e-105">This lesson requires that you have completed the previous lesson, [Lesson 1: Publishing Data Using Merge Replication](lesson-1-publishing-data-using-merge-replication.md).</span></span>  
  
### <a name="to-create-the-subscription"></a><span data-ttu-id="84e3e-106">Pour créer l'abonnement</span><span class="sxs-lookup"><span data-stu-id="84e3e-106">To create the subscription</span></span>  
  
1.  <span data-ttu-id="84e3e-107">Connectez-vous à l’abonné dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], développez le nœud du serveur, développez le dossier **Réplication** , cliquez avec le bouton droit sur le dossier **Abonnements locaux** , puis choisissez **Nouvel abonnement**.</span><span class="sxs-lookup"><span data-stu-id="84e3e-107">Connect to the Subscriber in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, expand the **Replication** folder, right-click the **Local Subscriptions** folder, and then click **New Subscriptions**.</span></span>  
  
     <span data-ttu-id="84e3e-108">L'Assistant Nouvel abonnement démarre.</span><span class="sxs-lookup"><span data-stu-id="84e3e-108">The New Subscription Wizard launches.</span></span>  
  
2.  <span data-ttu-id="84e3e-109">Dans la page **Publication** , choisissez **Rechercher un serveur de publication SQL** dans la liste **Serveur de publication** .</span><span class="sxs-lookup"><span data-stu-id="84e3e-109">On the **Publication** page, click **Find SQL Server Publisher** in the **Publisher** list.</span></span>  
  
3.  <span data-ttu-id="84e3e-110">Dans la boîte de dialogue **Connect Se connecter au serveur** , entrez le nom de l’instance du serveur de publication dans la zone **Nom du serveur** , puis cliquez sur **Se connecter**.</span><span class="sxs-lookup"><span data-stu-id="84e3e-110">In the **Connect to Server** dialog box, enter the name of the Publisher instance in the **Server name** box, and click **Connect**.</span></span>  
  
4.  <span data-ttu-id="84e3e-111">Cliquez sur **AdvWorksSalesOrdersMerge**, puis sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="84e3e-111">Click **AdvWorksSalesOrdersMerge**, and click **Next**.</span></span>  
  
5.  <span data-ttu-id="84e3e-112">Dans la page Emplacement de l’Agent de fusion, cliquez sur **Exécuter chaque agent sur son Abonné**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="84e3e-112">On the Merge Agent Location page, click **Run each agent at its Subscriber**, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="84e3e-113">Dans la page Abonnés, sélectionnez le nom d’instance du serveur de l’Abonné, et sous **Base de données d’abonnement**sélectionnez **\<New Database>** dans la liste.</span><span class="sxs-lookup"><span data-stu-id="84e3e-113">On the Subscribers page, select the instance name of the Subscriber server, and under **Subscription Database**, select **\<New Database>** from the list.</span></span>  
  
7.  <span data-ttu-id="84e3e-114">Dans la boîte de dialogue **Nouvelle base de données** , entrez **SalesOrdersReplica** dans la zone **Nom de la base de données** , cliquez sur **OK**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="84e3e-114">In the **New Database** dialog box, enter **SalesOrdersReplica** in the **Database name** box, click **OK**, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="84e3e-115">Dans la page sécurité du Agent de fusion, cliquez sur le bouton des points de suspension (**...**), entrez \<_Machine_Name> _**\ repl_merge** dans la zone **compte de processus** , fournissez le mot de passe de ce compte, cliquez sur **OK**, sur **suivant**, puis de nouveau sur **suivant** .</span><span class="sxs-lookup"><span data-stu-id="84e3e-115">On the Merge Agent Security page, click the ellipsis (**...**) button, enter \<_Machine_Name>_**\repl_merge** in the **Process account** box, supply the password for this account, click **OK**, click **Next**, and then click **Next** again.</span></span>  
  
9. <span data-ttu-id="84e3e-116">Dans la page Initialiser les abonnements, sélectionnez **Lors de la première synchronisation** dans la liste **À quel moment** , cliquez sur **Suivant**, puis une nouvelle fois sur **Suivant** .</span><span class="sxs-lookup"><span data-stu-id="84e3e-116">On the Initialize Subscriptions page, select **At first synchronization** from the **Initialize When** list, click **Next**, and then click **Next** again.</span></span>  
  
10. <span data-ttu-id="84e3e-117">Dans la page valeurs de HOST_NAME, entrez une valeur `adventure-works\pamela0` dans la zone **valeur de HOST_NAME** , puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="84e3e-117">On the HOST_NAME Values page, enter a value of `adventure-works\pamela0` in the **HOST_NAME Value** box, and then click **Finish**.</span></span>  
  
11. <span data-ttu-id="84e3e-118">Cliquez à nouveau sur **Terminer** et, une fois l’abonnement créé, cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="84e3e-118">Click **Finish** again, and after the subscription is created, click **Close**.</span></span>  
  
### <a name="setting-database-permissions-at-the-subscriber"></a><span data-ttu-id="84e3e-119">Définition des autorisations de base de données sur l'Abonné</span><span class="sxs-lookup"><span data-stu-id="84e3e-119">Setting database permissions at the Subscriber</span></span>  
  
1.  <span data-ttu-id="84e3e-120">Connectez-vous à l’Abonné dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], développez **Bases de données**, **SalesOrdersReplica**et **Sécurité**, cliquez avec le bouton droit sur **Utilisateurs**, puis choisissez **Nouvel utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="84e3e-120">Connect to the Subscriber in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand **Databases**, **SalesOrdersReplica**, and **Security**, right-click **Users**, and then select **New User**.</span></span>  
  
2.  <span data-ttu-id="84e3e-121">Sur la page **général** , entrez \<_Machine_Name> _ **\ repl_merge** dans la zone **nom d’utilisateur** , cliquez sur le bouton de sélection (**...**), cliquez \<_Machine_Name> sur **Parcourir**, sélectionnez _ **\ repl_merge**, cliquez sur **OK**, sur **vérifier les noms**, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="84e3e-121">On the **General** page, enter \<_Machine_Name>_**\repl_merge** in the **User name** box, click the ellipsis (**...**) button, click **Browse**, select \<_Machine_Name>_**\repl_merge**, click **OK**, click **Check Names**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="84e3e-122">Dans **Appartenance au rôle de base de données**, sélectionnez **db_owner**, puis cliquez sur **OK** pour créer l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="84e3e-122">In **Database role membership**, select **db_owner**, and then click **OK** to create the user.</span></span>  
  
### <a name="to-create-the-filtered-data-snapshot-for-the-subscription"></a><span data-ttu-id="84e3e-123">Pour créer l'instantané filtré des données de l'abonnement</span><span class="sxs-lookup"><span data-stu-id="84e3e-123">To create the filtered data snapshot for the subscription</span></span>  
  
1.  <span data-ttu-id="84e3e-124">Connectez-vous au serveur de publication dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], développez le nœud du serveur, puis le dossier **Réplication** .</span><span class="sxs-lookup"><span data-stu-id="84e3e-124">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, and then expand the **Replication** folder.</span></span>  
  
2.  <span data-ttu-id="84e3e-125">Dans le dossier **Publications locales** , cliquez avec le bouton droit sur la publication **AdvWorksSalesOrdersMerge** , puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="84e3e-125">In the **Local Publications** folder, right-click the **AdvWorksSalesOrdersMerge** publication, and then click **Properties**.</span></span>  
  
     <span data-ttu-id="84e3e-126">La boîte de dialogue **Propriétés de la publication** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="84e3e-126">The **Publication Properties** dialog box is displayed.</span></span>  
  
3.  <span data-ttu-id="84e3e-127">Sélectionnez la page **Partitions de données** , puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="84e3e-127">Select the **Data Partitions** page, and click **Add**.</span></span>  
  
4.  <span data-ttu-id="84e3e-128">Dans la boîte de dialogue **Ajouter une partition de données** , tapez `adventure-works\pamela0` dans la zone **HOST_NAME valeur** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="84e3e-128">In the **Add Data Partition** dialog box, type `adventure-works\pamela0` in the **HOST_NAME Value** box, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="84e3e-129">Sélectionnez la partition nouvellement ajoutée, cliquez sur **Générer les instantanés sélectionnés maintenant**, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="84e3e-129">Select the newly added partition, click **Generate the selected snapshots now**, and then click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="84e3e-130">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="84e3e-130">Next Steps</span></span>  
 <span data-ttu-id="84e3e-131">Vous avez créé avec succès un abonnement à la publication de fusion et généré l'instantané filtré pour la partition de données du nouvel abonnement de telle sorte qu'il soit disponible lors de l'initialisation de l'abonnement.</span><span class="sxs-lookup"><span data-stu-id="84e3e-131">You have successfully created a subscription to the merge publication and generated the filtered snapshot for the new subscription's data partition so that it will be available when the subscription is initialized.</span></span> <span data-ttu-id="84e3e-132">Ensuite, vous allez accorder des droits à l'Agent de fusion sur la base de données d'abonnement et exécuter l'Agent de fusion pour démarrer la synchronisation et initialiser l'abonnement.</span><span class="sxs-lookup"><span data-stu-id="84e3e-132">Next, you will grant rights to the Merge Agent on the subscription database and run the Merge Agent to start synchronization and initialize the subscription.</span></span> <span data-ttu-id="84e3e-133">Consultez [Leçon 3 : Synchronisation de l’abonnement et de la publication de fusion](lesson-3-synchronizing-the-subscription-to-the-merge-publication.md).</span><span class="sxs-lookup"><span data-stu-id="84e3e-133">See [Lesson 3: Synchronizing the Subscription to the Merge Publication](lesson-3-synchronizing-the-subscription-to-the-merge-publication.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84e3e-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="84e3e-134">See Also</span></span>  
 <span data-ttu-id="84e3e-135">[S’abonner aux Publications](subscribe-to-publications.md) </span><span class="sxs-lookup"><span data-stu-id="84e3e-135">[Subscribe to Publications](subscribe-to-publications.md) </span></span>  
 <span data-ttu-id="84e3e-136">[Create a Pull Subscription](create-a-pull-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="84e3e-136">[Create a Pull Subscription](create-a-pull-subscription.md) </span></span>  
 [<span data-ttu-id="84e3e-137">Instantanés des publications de fusion avec des filtres paramétrés</span><span class="sxs-lookup"><span data-stu-id="84e3e-137">Snapshots for Merge Publications with Parameterized Filters</span></span>](snapshots-for-merge-publications-with-parameterized-filters.md)  
  
  
