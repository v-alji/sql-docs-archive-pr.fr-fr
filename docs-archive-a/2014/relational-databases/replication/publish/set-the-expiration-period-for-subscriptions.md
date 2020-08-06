---
title: Définir la période d’expiration des abonnements | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- subscriptions [SQL Server replication], expiration
- expiration [SQL Server replication]
- retention periods [SQL Server replication]
- deactivating subscriptions
ms.assetid: 542f0613-5817-42d0-b841-fb2c94010665
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: bc0ecb449af64b88cf3ded032c78c2e399dd4234
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610603"
---
# <a name="set-the-expiration-period-for-subscriptions"></a><span data-ttu-id="55d1b-102">Définir la période d'expiration des abonnements</span><span class="sxs-lookup"><span data-stu-id="55d1b-102">Set the Expiration Period for Subscriptions</span></span>
  <span data-ttu-id="55d1b-103">Cette rubrique explique comment définir la période d'expiration des abonnements dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="55d1b-103">This topic describes how to set the expiration period for subscriptions in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="55d1b-104">La période d'expiration des abonnements détermine le temps qui précède l'expiration et la suppression d'un abonnement.</span><span class="sxs-lookup"><span data-stu-id="55d1b-104">The expiration period for subscriptions determines the period of time before a subscription expires and is removed.</span></span> <span data-ttu-id="55d1b-105">Pour plus d’informations, voir [Subscription Expiration and Deactivation](../subscription-expiration-and-deactivation.md).</span><span class="sxs-lookup"><span data-stu-id="55d1b-105">For more information, see [Subscription Expiration and Deactivation](../subscription-expiration-and-deactivation.md).</span></span>  
  
 <span data-ttu-id="55d1b-106">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="55d1b-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="55d1b-107">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="55d1b-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="55d1b-108">Recommandations</span><span class="sxs-lookup"><span data-stu-id="55d1b-108">Recommendations</span></span>](#Recommendations)  
  
-   <span data-ttu-id="55d1b-109">**Pour définir la période d'expiration des abonnements à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="55d1b-109">**To set the expiration period for subscriptions, using:**</span></span>  
  
     [<span data-ttu-id="55d1b-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="55d1b-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="55d1b-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="55d1b-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="55d1b-112">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="55d1b-112">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="55d1b-113">Recommandations</span><span class="sxs-lookup"><span data-stu-id="55d1b-113">Recommendations</span></span>  
  
-   <span data-ttu-id="55d1b-114">La période d'expiration de l'abonnement est également nommée *période de rétention de la publication*.</span><span class="sxs-lookup"><span data-stu-id="55d1b-114">The subscription expiration period is also referred to as the *publication retention period*.</span></span> <span data-ttu-id="55d1b-115">Le nettoyage des métadonnées des réplications de fusion dépend de ce paramètre :</span><span class="sxs-lookup"><span data-stu-id="55d1b-115">Cleanup of merge replication metadata is dependent on this setting:</span></span>  
  
    -   <span data-ttu-id="55d1b-116">La réplication ne peut pas nettoyer les métadonnées dans les bases de données de publication et d'abonnement tant que la période de rétention n'est pas achevée.</span><span class="sxs-lookup"><span data-stu-id="55d1b-116">Replication cannot clean up metadata in the publication and subscription databases until the retention period is reached.</span></span> <span data-ttu-id="55d1b-117">Soyez prudent si vous spécifiez une longue période de rétention, car cela peut affecter négativement les performances de réplication.</span><span class="sxs-lookup"><span data-stu-id="55d1b-117">Use caution in specifying a high value for the retention period, because it can negatively impact replication performance.</span></span> <span data-ttu-id="55d1b-118">Vous avez intérêt à spécifier une valeur faible si vous êtes certain que tous les Abonnés procéderont régulièrement à la synchronisation dans ce délai.</span><span class="sxs-lookup"><span data-stu-id="55d1b-118">It is recommended that you use a lower setting if you can reliably predict that all Subscribers will synchronize regularly within that time period.</span></span>  
  
         <span data-ttu-id="55d1b-119">La période de rétention pour les publications de fusion offre un délai de grâce de 24 heures pour tenir compte des Abonnés situés dans différents fuseaux horaires.</span><span class="sxs-lookup"><span data-stu-id="55d1b-119">The retention period for merge publications has a 24-hour grace period to accommodate Subscribers in different time zones.</span></span> <span data-ttu-id="55d1b-120">Si, par exemple, vous définissez une période de rétention d'un jour, la période de rétention réelle est de 48 heures.</span><span class="sxs-lookup"><span data-stu-id="55d1b-120">If, for example, you set a retention period of one day, the actual retention period is 48 hours.</span></span>  
  
    -   <span data-ttu-id="55d1b-121">Il est possible de spécifier que les abonnements n'expirent jamais, mais ceci est fortement déconseillé car les métadonnées ne pourront pas être nettoyées.</span><span class="sxs-lookup"><span data-stu-id="55d1b-121">It is possible to specify that subscriptions never expire, but it is strongly recommended that you do not use this value, because metadata cannot be cleaned up.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="55d1b-122">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="55d1b-122">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="55d1b-123">Définissez la période d’expiration des abonnements dans la page **Général** de la boîte de dialogue **Propriétés de la publication - \<Publication>** .</span><span class="sxs-lookup"><span data-stu-id="55d1b-123">Set the expiration period for subscriptions on the **General** page of the **Publication Properties - \<Publication>** dialog box.</span></span> <span data-ttu-id="55d1b-124">Pour plus d'informations sur l'accès à cette boîte de dialogue, consultez [Afficher et modifier les propriétés d’un serveur de publication](view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="55d1b-124">For more information about accessing this dialog box, see [View and Modify Publication Properties](view-and-modify-publication-properties.md).</span></span>  
  
#### <a name="to-set-the-expiration-period-for-subscriptions"></a><span data-ttu-id="55d1b-125">Pour définir la période d'expiration des abonnements</span><span class="sxs-lookup"><span data-stu-id="55d1b-125">To set the expiration period for subscriptions</span></span>  
  
1.  <span data-ttu-id="55d1b-126">Dans la section **Expiration de l’abonnement** de la page **Général** de la boîte de dialogue **Propriétés de la publication - \<Publication>** , spécifiez si l’abonnement doit expirer.</span><span class="sxs-lookup"><span data-stu-id="55d1b-126">In the **Subscription expiration** section on the **General** page of the **Publication Properties - \<Publication>** dialog box, specify whether subscriptions should expire.</span></span>  
  
2.  <span data-ttu-id="55d1b-127">S'il doit expirer, spécifiez un délai d'expiration.</span><span class="sxs-lookup"><span data-stu-id="55d1b-127">If they should expire, specify an expiration time period.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="55d1b-128">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="55d1b-128">Using Transact-SQL</span></span>  
 <span data-ttu-id="55d1b-129">Vous pouvez utiliser des procédures stockées de réplication pour définir cette valeur lorsqu'une publication est créée ou pour modifier cette valeur ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="55d1b-129">You can use replication stored procedures to either set this value when a publication is created or modify this value at a later time.</span></span>  
  
#### <a name="to-set-the-expiration-period-for-a-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="55d1b-130">Pour définir la période d'expiration d'un abonnement à une publication transactionnelle ou d'instantané</span><span class="sxs-lookup"><span data-stu-id="55d1b-130">To set the expiration period for a subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="55d1b-131">Sur le serveur de publication, exécutez [sp_addpublication](/sql/relational-databases/system-stored-procedures/sp-addpublication-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="55d1b-131">At the Publisher, execute [sp_addpublication](/sql/relational-databases/system-stored-procedures/sp-addpublication-transact-sql).</span></span> <span data-ttu-id="55d1b-132">Spécifiez la période de l’expiration de l’abonnement souhaitée, en heures, pour **\@retention**.</span><span class="sxs-lookup"><span data-stu-id="55d1b-132">Specify the desired subscription expiration period, in hours, for **\@retention**.</span></span> <span data-ttu-id="55d1b-133">La période d'expiration par défaut est de 336 heures.</span><span class="sxs-lookup"><span data-stu-id="55d1b-133">The default expiration period is 336 hours.</span></span> <span data-ttu-id="55d1b-134">Pour plus d’informations, voir [Create a Publication](create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="55d1b-134">For more information, see [Create a Publication](create-a-publication.md).</span></span>  
  
#### <a name="to-set-the-expiration-period-for-a-subscription-to-a-merge-publication"></a><span data-ttu-id="55d1b-135">Pour définir la période d'expiration d'un abonnement à une publication de fusion</span><span class="sxs-lookup"><span data-stu-id="55d1b-135">To set the expiration period for a subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="55d1b-136">Sur le serveur de publication, exécutez [sp_addmergepublication](/sql/relational-databases/system-stored-procedures/sp-addmergepublication-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="55d1b-136">At the Publisher, execute [sp_addmergepublication](/sql/relational-databases/system-stored-procedures/sp-addmergepublication-transact-sql).</span></span> <span data-ttu-id="55d1b-137">Spécifiez la période d’expiration de l’abonnement en affectant la valeur de votre choix à **\@retention**.</span><span class="sxs-lookup"><span data-stu-id="55d1b-137">Specify the desired value for the subscription expiration period for **\@retention**.</span></span> <span data-ttu-id="55d1b-138">Spécifiez les unités dans lesquelles la période d’expiration est exprimée pour **\@retention_period_unit**. Les unités possibles sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="55d1b-138">Specify the units in which the expiration period is expressed for **\@retention_period_unit**, which can be one of the following:</span></span>  
  
    -   <span data-ttu-id="55d1b-139">**1** = semaine</span><span class="sxs-lookup"><span data-stu-id="55d1b-139">**1** = week</span></span>  
  
    -   <span data-ttu-id="55d1b-140">**2** = mois</span><span class="sxs-lookup"><span data-stu-id="55d1b-140">**2** = month</span></span>  
  
    -   <span data-ttu-id="55d1b-141">**3** = année</span><span class="sxs-lookup"><span data-stu-id="55d1b-141">**3** = year</span></span>  
  
     <span data-ttu-id="55d1b-142">La période d'expiration par défaut est de 14 jours.</span><span class="sxs-lookup"><span data-stu-id="55d1b-142">The default expiration period is 14 days.</span></span> <span data-ttu-id="55d1b-143">Pour plus d’informations, voir [Create a Publication](create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="55d1b-143">For more information, see [Create a Publication](create-a-publication.md).</span></span>  
  
#### <a name="to-change-the-expiration-period-for-a-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="55d1b-144">Pour modifier la période d'expiration d'un abonnement à une publication transactionnelle ou d'instantané</span><span class="sxs-lookup"><span data-stu-id="55d1b-144">To change the expiration period for a subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="55d1b-145">Sur le serveur de publication, exécutez [sp_changepublication](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="55d1b-145">At the Publisher, execute [sp_changepublication](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql).</span></span> <span data-ttu-id="55d1b-146">Spécifiez **retention** pour **\@property** et la nouvelle période d’expiration de l’abonnement, en heures, pour **\@value**.</span><span class="sxs-lookup"><span data-stu-id="55d1b-146">Specify **retention** for **\@property** and the new subscription expiration period, in hours, for **\@value**.</span></span>  
  
#### <a name="to-change-the-expiration-period-for-a-subscription-to-a-merge-publication"></a><span data-ttu-id="55d1b-147">Pour modifier la période d'expiration d'un abonnement à une publication de fusion</span><span class="sxs-lookup"><span data-stu-id="55d1b-147">To change the expiration period for a subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="55d1b-148">Sur le serveur de publication, exécutez [sp_helpmergepublication](/sql/relational-databases/system-stored-procedures/sp-helpmergepublication-transact-sql), en spécifiant **\@publication** et **\@publisher**.</span><span class="sxs-lookup"><span data-stu-id="55d1b-148">At the Publisher, execute [sp_helpmergepublication](/sql/relational-databases/system-stored-procedures/sp-helpmergepublication-transact-sql), specifying **\@publication** and **\@publisher**.</span></span> <span data-ttu-id="55d1b-149">Notez la valeur de **retention_period_unit** dans le jeu de résultats ; elle peut correspondre à l'une des valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="55d1b-149">Note the value of **retention_period_unit** in the result set, which can be one of the following:</span></span>  
  
    -   <span data-ttu-id="55d1b-150">**0** = jour</span><span class="sxs-lookup"><span data-stu-id="55d1b-150">**0** = day</span></span>  
  
    -   <span data-ttu-id="55d1b-151">**1** = semaine</span><span class="sxs-lookup"><span data-stu-id="55d1b-151">**1** = week</span></span>  
  
    -   <span data-ttu-id="55d1b-152">**2** = mois</span><span class="sxs-lookup"><span data-stu-id="55d1b-152">**2** = month</span></span>  
  
    -   <span data-ttu-id="55d1b-153">**3** = année</span><span class="sxs-lookup"><span data-stu-id="55d1b-153">**3** = year</span></span>  
  
2.  <span data-ttu-id="55d1b-154">Sur le serveur de publication, exécutez [sp_changemergepublication](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="55d1b-154">At the Publisher, execute [sp_changemergepublication](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql).</span></span> <span data-ttu-id="55d1b-155">Spécifiez **retention** pour **\@property** et la nouvelle période d’expiration de l’abonnement, sous forme de texte basé sur l’unité de période de rétention définie à l’étape 1, pour **\@value**.</span><span class="sxs-lookup"><span data-stu-id="55d1b-155">Specify **retention** for **\@property** and the new subscription expiration period, as text based on the retention period unit from step 1, for **\@value**.</span></span>  
  
3.  <span data-ttu-id="55d1b-156">(Facultatif) Sur le serveur de publication, exécutez [sp_changemergepublication](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="55d1b-156">(Optional) At the Publisher, execute [sp_changemergepublication](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql).</span></span> <span data-ttu-id="55d1b-157">Spécifiez **retention_period_unit** pour **\@property** et une nouvelle unité pour la période d’expiration de l’abonnement pour **\@value**.</span><span class="sxs-lookup"><span data-stu-id="55d1b-157">Specify **retention_period_unit** for **\@property** and a new unit for the subscription expiration period for **\@value**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55d1b-158">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="55d1b-158">See Also</span></span>  
 <span data-ttu-id="55d1b-159">[Concepts liés aux procédures stockées système de réplication](../concepts/replication-system-stored-procedures-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="55d1b-159">[Replication System Stored Procedures Concepts](../concepts/replication-system-stored-procedures-concepts.md) </span></span>  
 [<span data-ttu-id="55d1b-160">Expiration et désactivation des abonnements</span><span class="sxs-lookup"><span data-stu-id="55d1b-160">Subscription Expiration and Deactivation</span></span>](../subscription-expiration-and-deactivation.md)  
  
  
