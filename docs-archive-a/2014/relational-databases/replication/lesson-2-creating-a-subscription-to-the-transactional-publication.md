---
title: 'Leçon 2 : Création d’un abonnement à la publication transactionnelle | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: 5995b7d2-7c06-46f5-b96c-2bee879bcda2
author: rothja
ms.author: jroth
ms.openlocfilehash: dbf40fa259302dffdd6c0b8e8717b7c35b0cf92d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601315"
---
# <a name="lesson-2-creating-a-subscription-to-the-transactional-publication"></a><span data-ttu-id="2a289-102">Leçon 2 : Création d'un abonnement à la publication transactionnelle</span><span class="sxs-lookup"><span data-stu-id="2a289-102">Lesson 2: Creating a Subscription to the Transactional Publication</span></span>
  <span data-ttu-id="2a289-103">Dans cette leçon, vous allez créer l'abonnement à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2a289-103">In this lesson, you will create a subscription using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="2a289-104">Pour effectuer cette leçon, vous devez avoir terminé la leçon précédente, [Leçon 1 : Publication de données à l’aide de la réplication transactionnelle](lesson-1-publishing-data-using-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="2a289-104">This lesson requires that you have completed the previous lesson, [Lesson 1: Publishing Data Using Transactional Replication](lesson-1-publishing-data-using-transactional-replication.md).</span></span>  
  
### <a name="to-create-the-subscription"></a><span data-ttu-id="2a289-105">Pour créer l'abonnement</span><span class="sxs-lookup"><span data-stu-id="2a289-105">To create the subscription</span></span>  
  
1.  <span data-ttu-id="2a289-106">Connectez-vous au serveur de publication dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], développez le nœud du serveur, puis le dossier **Réplication** .</span><span class="sxs-lookup"><span data-stu-id="2a289-106">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, and then expand the **Replication** folder.</span></span>  
  
2.  <span data-ttu-id="2a289-107">Dans le dossier **Publications locales** , cliquez avec le bouton droit sur la publication **AdvWorksProductTrans** , puis cliquez sur **Nouveaux abonnements**.</span><span class="sxs-lookup"><span data-stu-id="2a289-107">In the **Local Publications** folder, right-click the **AdvWorksProductTrans** publication, and then click **New Subscriptions**.</span></span>  
  
     <span data-ttu-id="2a289-108">L'Assistant Nouvel abonnement démarre.</span><span class="sxs-lookup"><span data-stu-id="2a289-108">The New Subscription Wizard launches.</span></span>  
  
3.  <span data-ttu-id="2a289-109">Dans la page Publication, sélectionnez **AdvWorksProductTrans**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="2a289-109">On the Publication page, select **AdvWorksProductTrans**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="2a289-110">Dans la page Emplacement de l’Agent de distribution, sélectionnez **Exécuter tous les agents sur le serveur de distribution**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="2a289-110">On the Distribution Agent Location page, select **Run all agents at the Distributor**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="2a289-111">Dans la page Abonnés, si le nom de l’instance de l’Abonné n’apparaît pas, cliquez sur **Ajouter un Abonné**, sur **Ajouter un Abonné SQL Server**, entrez le nom de l’instance de l’Abonné dans la boîte de dialogue **Se connecter au serveur** , puis cliquez sur **Se connecter**.</span><span class="sxs-lookup"><span data-stu-id="2a289-111">On the Subscribers page, if the name of the Subscriber instance is not displayed, click **Add Subscriber**, click **Add SQL Server Subscriber**, enter the Subscriber instance name in the **Connect to Server** dialog box, and then click **Connect**.</span></span>  
  
6.  <span data-ttu-id="2a289-112">Sur la page abonnés, sélectionnez le nom de l’instance du serveur de l’abonné, puis sélectionnez **\<New Database>** sous **base de données d’abonnement**.</span><span class="sxs-lookup"><span data-stu-id="2a289-112">On the Subscribers page, select the instance name of the Subscriber server, and select **\<New Database>** under **Subscription Database**.</span></span>  
  
7.  <span data-ttu-id="2a289-113">Dans la boîte de dialogue **Nouvelle base de données** , entrez **ProductReplica** dans la zone **Nom de la base de données** , cliquez sur **OK**, puis sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="2a289-113">On the **New Database** dialog box, enter **ProductReplica** in the **Database name** box, click **OK**, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="2a289-114">Dans la boîte de dialogue **agent de distribution sécurité** , cliquez sur le bouton des points de suspension (**...**), entrez \<_Machine_Name> _**\ Repl_distribution** dans la zone **compte de processus** , entrez le mot de passe de ce compte, cliquez sur **OK**, puis sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="2a289-114">In the **Distribution Agent Security** dialog box, click the ellipsis (**...**) button, enter \<_Machine_Name>_**\repl_distribution** in the **Process account** box, enter the password for this account, click **OK**, and then click **Next**.</span></span>  
  
9. <span data-ttu-id="2a289-115">Cliquez sur **Terminer** pour accepter les valeurs par défaut des pages restantes et terminer l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="2a289-115">Click **Finish** to accept the default values on the remaining pages and complete the wizard.</span></span>  
  
### <a name="setting-database-permissions-at-the-subscriber"></a><span data-ttu-id="2a289-116">Définition des autorisations de base de données sur l'Abonné</span><span class="sxs-lookup"><span data-stu-id="2a289-116">Setting database permissions at the Subscriber</span></span>  
  
1.  <span data-ttu-id="2a289-117">Connectez-vous à l’Abonné dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], développez **Bases de données**, **ProductReplica**et **Sécurité**, cliquez avec le bouton droit sur **Utilisateurs**, puis sélectionnez **Nouvel utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="2a289-117">Connect to the Subscriber in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand **Databases**, **ProductReplica**, and **Security**, right-click **Users**, and then select **New User**.</span></span>  
  
2.  <span data-ttu-id="2a289-118">Dans la page **Général** , dans la liste **Type d’utilisateur** , sélectionnez **Utilisateur Windows**.</span><span class="sxs-lookup"><span data-stu-id="2a289-118">On the **General** page, in the **User type** list, select **Windows user**.</span></span>  
  
3.  <span data-ttu-id="2a289-119">Sélectionnez la **zone nom d’utilisateur** et cliquez sur le bouton des points de suspension (...), dans la zone **Entrez le nom de l’objet à sélectionner** , tapez <Machine_Name>**\ repl_distribution**, cliquez sur **vérifier les noms**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2a289-119">Select the **User name** box and click the ellipsis (...) button, in the **Enter the object name to select** box type <Machine_Name>**\repl_distribution**, click **Check Names**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="2a289-120">Dans la page **Appartenance** , dans la zone **Appartenance au rôle de base de données** , sélectionnez **db_owner**, puis cliquez sur **OK** pour créer l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2a289-120">On the **Membership** page, in **Database role membership** area, select **db_owner**, and then click **OK** to create the user.</span></span>  
  
### <a name="to-view-the-synchronization-status-of-the-subscription"></a><span data-ttu-id="2a289-121">Pour afficher l'état de synchronisation de l'abonnement</span><span class="sxs-lookup"><span data-stu-id="2a289-121">To view the synchronization status of the subscription</span></span>  
  
1.  <span data-ttu-id="2a289-122">Connectez-vous au serveur de publication dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], développez le nœud du serveur, puis le dossier **Réplication** .</span><span class="sxs-lookup"><span data-stu-id="2a289-122">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, and then expand the **Replication** folder.</span></span>  
  
2.  <span data-ttu-id="2a289-123">Dans le dossier **Publications locales** , développez la publication **AdvWorksProductTrans** , cliquez avec le bouton droit sur l’abonnement dans la base de données **ProductReplica** , puis cliquez sur **Afficher l’état de synchronisation**.</span><span class="sxs-lookup"><span data-stu-id="2a289-123">In the **Local Publications** folder, expand the **AdvWorksProductTrans** publication, right-click the subscription in the **ProductReplica** database, and then click **View Synchronization Status**.</span></span>  
  
     <span data-ttu-id="2a289-124">L'état de synchronisation de l'abonnement s'affiche.</span><span class="sxs-lookup"><span data-stu-id="2a289-124">The current synchronization status of the subscription is displayed.</span></span>  
  
3.  <span data-ttu-id="2a289-125">Si l’abonnement n’apparaît pas sous **AdvWorksProductTrans**, appuyez sur F5 pour actualiser la liste.</span><span class="sxs-lookup"><span data-stu-id="2a289-125">If the subscription is not visible under **AdvWorksProductTrans**, press F5 to refresh the list.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="2a289-126">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="2a289-126">Next Steps</span></span>  
 <span data-ttu-id="2a289-127">Vous avez créé avec succès un abonnement à la publication transactionnelle.</span><span class="sxs-lookup"><span data-stu-id="2a289-127">You have successfully created a subscription to the transactional publication.</span></span> <span data-ttu-id="2a289-128">Comme l'Agent de distribution de cet abonnement s'exécute en permanence, l'abonnement est initialisé lors de sa création.</span><span class="sxs-lookup"><span data-stu-id="2a289-128">Because the Distribution Agent for this subscription runs continuously, the subscription is initialized when it is created.</span></span> <span data-ttu-id="2a289-129">Ensuite, vous allez utiliser les jetons de suivi pour vérifier que les modifications sont bien répliquées sur l'Abonné et pour déterminer la latence.</span><span class="sxs-lookup"><span data-stu-id="2a289-129">Next, you will use tracer tokens to verify that changes are being replicated to the Subscriber and to determine latency.</span></span> <span data-ttu-id="2a289-130">Voir [Leçon 3 : Validation de l’abonnement et mesure de la latence](lesson-3-validating-the-subscription-and-measuring-latency.md).</span><span class="sxs-lookup"><span data-stu-id="2a289-130">See [Lesson 3: Validating the Subscription and Measuring Latency](lesson-3-validating-the-subscription-and-measuring-latency.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a289-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2a289-131">See Also</span></span>  
 <span data-ttu-id="2a289-132">[Initialiser un abonnement avec un instantané](initialize-a-subscription-with-a-snapshot.md) </span><span class="sxs-lookup"><span data-stu-id="2a289-132">[Initialize a Subscription with a Snapshot](initialize-a-subscription-with-a-snapshot.md) </span></span>  
 <span data-ttu-id="2a289-133">[Create a Push Subscription](create-a-push-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="2a289-133">[Create a Push Subscription](create-a-push-subscription.md) </span></span>  
 [<span data-ttu-id="2a289-134">S'abonner à des publications</span><span class="sxs-lookup"><span data-stu-id="2a289-134">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
