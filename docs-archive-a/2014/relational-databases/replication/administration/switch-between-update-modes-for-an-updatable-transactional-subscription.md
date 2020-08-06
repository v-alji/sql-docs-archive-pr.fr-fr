---
title: Basculer entre les modes de mise à jour d’un abonnement transactionnel pouvant être mis à jour | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- transactional replication, updatable subscriptions
- updatable subscriptions, update modes
- subscriptions [SQL Server replication], updatable
ms.assetid: ab5ebab1-7ee4-41f4-999b-b4f0c420c921
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c31814d1e2ab6fac64ffcde883f3cac2439828a1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615131"
---
# <a name="switch-between-update-modes-for-an-updatable-transactional-subscription"></a><span data-ttu-id="ca77e-102">Basculer entre les modes de mise à jour d'un abonnement transactionnel pouvant être mis à jour</span><span class="sxs-lookup"><span data-stu-id="ca77e-102">Switch Between Update Modes for an Updatable Transactional Subscription</span></span>
  <span data-ttu-id="ca77e-103">Cette rubrique explique comment basculer entre les modes de mise à jour d'un abonnement transactionnel pouvant être mis à jour dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ca77e-103">This topic describes how to switch between update modes for an updatable transaction subscription in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="ca77e-104">Spécifiez le mode des abonnements pouvant être mis à jour à l'aide de l'Assistant Nouvel abonnement.</span><span class="sxs-lookup"><span data-stu-id="ca77e-104">Specify the mode for updatable subscriptions using the New Subscription Wizard.</span></span> <span data-ttu-id="ca77e-105">Pour plus d’informations sur la définition de ce mode lors de l’utilisation de cet Assistant, consultez [Afficher et modifier les propriétés d’un abonnement par extraction](../view-and-modify-pull-subscription-properties.md).</span><span class="sxs-lookup"><span data-stu-id="ca77e-105">For information about setting the mode when using this wizard, see [View and Modify Pull Subscription Properties](../view-and-modify-pull-subscription-properties.md).</span></span>  
  
  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ca77e-106">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="ca77e-106">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="ca77e-107">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="ca77e-107">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="ca77e-108">Vous pouvez basculer à tout instant d’une mise à jour immédiate vers une mise à jour en file d’attente.</span><span class="sxs-lookup"><span data-stu-id="ca77e-108">You can fail over from immediate to queued updating at any time.</span></span> <span data-ttu-id="ca77e-109">Après que vous avez basculé, cependant, vous ne pouvez pas repasser en mise à jour immédiate avant que l'abonné et le serveur de publication ne soient connectés et que l'Agent de lecture de la file d'attente n'ait appliqué tous les messages en attente dans la file d'attente sur le serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="ca77e-109">After you do, however, you cannot return to immediate updating until the Subscriber and Publisher are connected and the Queue Reader Agent has applied all pending messages in the queue to the Publisher.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="ca77e-110">Recommandations</span><span class="sxs-lookup"><span data-stu-id="ca77e-110">Recommendations</span></span>  
  
-   <span data-ttu-id="ca77e-111">Lorsqu'un abonnement avec mise à jour à une publication transactionnelle prend en charge le basculement d'un mode de mise à jour vers un autre, vous pouvez basculer par programmation les modes de mise à jour pour gérer les situations où la connectivité change pendant une courte période de temps.</span><span class="sxs-lookup"><span data-stu-id="ca77e-111">When an updating subscription to a transactional publication supports failover from one updating mode to another, you can programmatically switch update modes to handle situations when connectivity changes for a short period of time.</span></span> <span data-ttu-id="ca77e-112">Le mode de mise à jour peut être défini par programmation et à la demande à l'aide de procédures stockées de réplication.</span><span class="sxs-lookup"><span data-stu-id="ca77e-112">The update mode can be set programmatically and on demand using replication stored procedures.</span></span> <span data-ttu-id="ca77e-113">Pour plus d’informations, voir [Updatable Subscriptions for Transactional Replication](../transactional/updatable-subscriptions-for-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="ca77e-113">For more information, see [Updatable Subscriptions for Transactional Replication](../transactional/updatable-subscriptions-for-transactional-replication.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ca77e-114">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ca77e-114">Using SQL Server Management Studio</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ca77e-115">Pour modifier le mode de mise à jour après que l'abonnement a été créé, vous devez affecter à la propriété **update_mode** la valeur **failover** (qui permet de basculer de la mise à jour immédiate vers la mise à jour en attente) ou **queued failover** (qui permet de basculer de la mise à jour en attente vers la mise à jour immédiate) lors de la création de l'abonnement.</span><span class="sxs-lookup"><span data-stu-id="ca77e-115">To change the update mode after the subscription is created, the **update_mode** property must be set to **failover** (which allows a switch from immediate updating to queued updating) or **queued failover** (which allows a switch from queued updating to immediate updating) when the subscription is created.</span></span> <span data-ttu-id="ca77e-116">Ces propriétés sont automatiquement définies dans l'Assistant Nouvel abonnement.</span><span class="sxs-lookup"><span data-stu-id="ca77e-116">These properties are set automatically in the New Subscription Wizard.</span></span>  
  
#### <a name="to-set-the-updating-mode-for-a-push-subscription"></a><span data-ttu-id="ca77e-117">Pour définir le mode de mise à jour d'un abonnement envoyé</span><span class="sxs-lookup"><span data-stu-id="ca77e-117">To set the updating mode for a push subscription</span></span>  
  
1.  <span data-ttu-id="ca77e-118">Connectez-vous à l'Abonné dans [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], puis développez le nœud du serveur.</span><span class="sxs-lookup"><span data-stu-id="ca77e-118">Connect to the Subscriber in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="ca77e-119">Développez le dossier **Réplication** , puis développez le dossier **Abonnements locaux** .</span><span class="sxs-lookup"><span data-stu-id="ca77e-119">Expand the **Replication** folder, and then expand the **Local Subscriptions** folder.</span></span>  
  
3.  <span data-ttu-id="ca77e-120">Cliquez avec le bouton droit sur l'abonnement dont vous voulez définir le mode de mise à jour puis cliquez sur **Définir la méthode de mise à jour**.</span><span class="sxs-lookup"><span data-stu-id="ca77e-120">Right-click the subscription for which you want to set the update mode, and then click **Set Update Method**.</span></span>  
  
4.  <span data-ttu-id="ca77e-121">Dans la boîte de dialogue **Définir la méthode de mise à jour - \<Subscriber> : \<SubscriptionDatabase>** , sélectionnez **Mise à jour immédiate** ou **Mise à jour en attente**.</span><span class="sxs-lookup"><span data-stu-id="ca77e-121">In the **Set Update Method - \<Subscriber>: \<SubscriptionDatabase>** dialog box, select **Immediate updating** or **Queued updating**.</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
#### <a name="to-set-the-updating-mode-for-a-pull-subscription"></a><span data-ttu-id="ca77e-122">Pour définir le mode de mise à jour d'un abonnement extrait</span><span class="sxs-lookup"><span data-stu-id="ca77e-122">To set the updating mode for a pull subscription</span></span>  
  
1.  <span data-ttu-id="ca77e-123">Dans la boîte de dialogue **Propriétés de l’abonnement - \<Publisher> : \<PublicationDatabase>** , sélectionnez la valeur **Répliquer les modifications immédiatement** ou **Mettre les modifications en file d’attente** pour l'option **Méthode de mise à jour de l’Abonné**.</span><span class="sxs-lookup"><span data-stu-id="ca77e-123">In the **Subscription Properties - \<Publisher>: \<PublicationDatabase>** dialog box, select a value of **Immediately replicate changes** or **Queue changes** for the **Subscriber update method** option.</span></span>  
  
2.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
 <span data-ttu-id="ca77e-124">Pour plus d’informations sur l’accès à la boîte de dialogue **Propriétés de l’abonnement - \<Publisher> : \<PublicationDatabase>** , consultez [Afficher et modifier les propriétés d’un abonnement par extraction](../view-and-modify-pull-subscription-properties.md).</span><span class="sxs-lookup"><span data-stu-id="ca77e-124">For more information about accessing the **Subscription Properties - \<Publisher>: \<PublicationDatabase>** dialog box, see [View and Modify Pull Subscription Properties](../view-and-modify-pull-subscription-properties.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="ca77e-125">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ca77e-125">Using Transact-SQL</span></span>  
  
#### <a name="to-switch-between-update-modes"></a><span data-ttu-id="ca77e-126">Pour basculer d'un mode de mise à jour vers un autre</span><span class="sxs-lookup"><span data-stu-id="ca77e-126">To switch between update modes</span></span>  
  
1.  <span data-ttu-id="ca77e-127">Vérifiez que l'abonnement prend en charge le basculement en exécutant [sp_helppullsubscription](/sql/relational-databases/system-stored-procedures/sp-helppullsubscription-transact-sql) pour un abonnement par extraction ou [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql) pour un abonnement par émission de données.</span><span class="sxs-lookup"><span data-stu-id="ca77e-127">Verify that the subscription supports failover by executing [sp_helppullsubscription](/sql/relational-databases/system-stored-procedures/sp-helppullsubscription-transact-sql) for a pull subscription or [sp_helpsubscription](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql) for a push subscription.</span></span> <span data-ttu-id="ca77e-128">Si la valeur de **mode de mise à jour** dans le jeu de résultats est **3** ou **4**, le basculement est pris en charge.</span><span class="sxs-lookup"><span data-stu-id="ca77e-128">If the value of **update mode** in the result set is **3** or **4**, failover is supported.</span></span>  
  
2.  <span data-ttu-id="ca77e-129">Sur l'Abonné de la base de données d'abonnement, exécutez [sp_setreplfailovermode](/sql/relational-databases/system-stored-procedures/sp-setreplfailovermode-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ca77e-129">At the Subscriber on the subscription database, execute [sp_setreplfailovermode](/sql/relational-databases/system-stored-procedures/sp-setreplfailovermode-transact-sql).</span></span> <span data-ttu-id="ca77e-130">Spécifiez **@publisher** ,, **@publisher_db** et l' **@publication** une des valeurs suivantes pour **@failover_mode** :</span><span class="sxs-lookup"><span data-stu-id="ca77e-130">Specify **@publisher**, **@publisher_db**, **@publication**, and one of the following values for **@failover_mode**:</span></span>  
  
    -   <span data-ttu-id="ca77e-131">**mis en file d'attente** - basculement sur la mise à jour en attente lorsque la connectivité a été perdue temporairement.</span><span class="sxs-lookup"><span data-stu-id="ca77e-131">**queued** - fail over to queued updating when connectivity has been temporarily lost.</span></span>  
  
    -   <span data-ttu-id="ca77e-132">**immédiat** - basculement sur la mise à jour immédiate lorsque la connectivité a été restaurée.</span><span class="sxs-lookup"><span data-stu-id="ca77e-132">**immediate** - fail over to immediate updating when connectivity has been restored.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca77e-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ca77e-133">See Also</span></span>  
 [<span data-ttu-id="ca77e-134">Updatable Subscriptions for Transactional Replication</span><span class="sxs-lookup"><span data-stu-id="ca77e-134">Updatable Subscriptions for Transactional Replication</span></span>](../transactional/updatable-subscriptions-for-transactional-replication.md)  
  
  
