---
title: Synchroniser un abonnement à l’aide du gestionnaire de synchronisation Windows (gestionnaire de synchronisation Windows) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- synchronization [SQL Server replication], Windows Synchronization Manager
- Windows Synchronization Manager
ms.assetid: 80f15dd6-e84d-4f96-9866-5b34ea531f1e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: bb31c344f91c68b04e03dd218f22b09bec44830b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701022"
---
# <a name="synchronize-a-subscription-using-windows-synchronization-manager-windows-synchronization-manager"></a><span data-ttu-id="b8fb5-102">synchroniser un abonnement à l'aide du Gestionnaire de synchronisation Windows (Windows Synchronization Manager)</span><span class="sxs-lookup"><span data-stu-id="b8fb5-102">Synchronize a Subscription Using Windows Synchronization Manager (Windows Synchronization Manager)</span></span>
  <span data-ttu-id="b8fb5-103">Le Gestionnaire de synchronisation[!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows ne peut être utilisé que pour synchroniser des abonnements à des publications Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] si [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est exécuté sur le même ordinateur que le Gestionnaire de synchronisation (il peut également servir à synchroniser des fichiers hors connexion et des pages Web).</span><span class="sxs-lookup"><span data-stu-id="b8fb5-103">[!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Synchronization Manager can only be used to synchronize subscriptions to Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] publications if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running on the same computer as Synchronization Manager (it can also be used to synchronize offline files and Web pages).</span></span> <span data-ttu-id="b8fb5-104">Pour utiliser le Gestionnaire de synchronisation :</span><span class="sxs-lookup"><span data-stu-id="b8fb5-104">To use Synchronization Manager:</span></span>  
  
1.  <span data-ttu-id="b8fb5-105">Activez la synchronisation des abonnements par extraction sur le Gestionnaire de synchronisation Windows dans la boîte de dialogue **Propriétés de l’abonnement - \<Subscriber> : \<SubscriptionDatabase>** .</span><span class="sxs-lookup"><span data-stu-id="b8fb5-105">Enable the synchronization of pull subscriptions with Windows Synchronization Manager in the **Subscription Properties - \<Subscriber>: \<SubscriptionDatabase>** dialog box.</span></span> <span data-ttu-id="b8fb5-106">Pour plus d’informations sur l’accès à cette boîte de dialogue, consultez [Afficher et modifier les propriétés d’un abonnement par extraction (pull)](view-and-modify-pull-subscription-properties.md).</span><span class="sxs-lookup"><span data-stu-id="b8fb5-106">For more information about accessing this dialog box, see [View and Modify Pull Subscription Properties](view-and-modify-pull-subscription-properties.md).</span></span>  
  
2.  <span data-ttu-id="b8fb5-107">Accédez au Gestionnaire de synchronisation par le menu **Démarrer** de Windows.</span><span class="sxs-lookup"><span data-stu-id="b8fb5-107">Access Synchronization Manager through the **Start** menu in Windows.</span></span>  
  
 <span data-ttu-id="b8fb5-108">Le Gestionnaire de synchronisation vous permet d'utiliser l'outil de résolution interactive pour les abonnements de fusion.</span><span class="sxs-lookup"><span data-stu-id="b8fb5-108">Synchronization Manager allows you to use the Interactive Resolver for merge subscriptions.</span></span> <span data-ttu-id="b8fb5-109">En général, les conflits détectés pendant la synchronisation sont résolus automatiquement, mais si la résolution interactive est activée, les conflits peuvent être résolus par un utilisateur pendant la synchronisation.</span><span class="sxs-lookup"><span data-stu-id="b8fb5-109">Typically, conflicts detected during synchronization are resolved automatically, but if interactive resolution is enabled, conflicts can be resolved by a user during synchronization.</span></span> <span data-ttu-id="b8fb5-110">Si une synchronisation est effectuée en dehors du Gestionnaire de synchronisation Windows (comme une synchronisation planifiée ou à la demande dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou le Moniteur de réplication), les conflits sont résolus automatiquement sans intervention de l'utilisateur, en fonction de l'outil de résolution spécifié pour l'article.</span><span class="sxs-lookup"><span data-stu-id="b8fb5-110">If a synchronization is performed outside of Windows Synchronization Manager (as a scheduled synchronization or an on demand synchronization in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or Replication Monitor), conflicts are resolved automatically without user intervention, according to the resolver specified for the article.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b8fb5-111">À partir de [!INCLUDE[firstref_longhorn](../../includes/firstref-longhorn-md.md)] et [!INCLUDE[wiprlhlong](../../includes/wiprlhlong-md.md)], les versions 64 bits du Gestionnaire de synchronisation Windows ne peuvent pas détecter les abonnements 32 bits.</span><span class="sxs-lookup"><span data-stu-id="b8fb5-111">Beginning with [!INCLUDE[firstref_longhorn](../../includes/firstref-longhorn-md.md)] and [!INCLUDE[wiprlhlong](../../includes/wiprlhlong-md.md)], 64-bit versions of the Windows Synchronization Manager cannot detect 32-bit subscriptions.</span></span>  
  
### <a name="to-enable-the-synchronization-of-pull-subscriptions-with-windows-synchronization-manager"></a><span data-ttu-id="b8fb5-112">Pour activer la synchronisation des abonnements par extraction de données (pull) avec le Gestionnaire de synchronisation Windows</span><span class="sxs-lookup"><span data-stu-id="b8fb5-112">To enable the synchronization of pull subscriptions with Windows Synchronization Manager</span></span>  
  
1.  <span data-ttu-id="b8fb5-113">Dans la page **Général** de la boîte de dialogue **Propriétés de l’abonnement - \<Subscriber> : \<SubscriptionDatabase>** , sélectionnez la valeur **Activer** pour l’option **Utiliser le Gestionnaire de synchronisation Windows**.</span><span class="sxs-lookup"><span data-stu-id="b8fb5-113">On the **General** page of the **Subscription Properties - \<Subscriber>: \<SubscriptionDatabase>** dialog box, select a value of **Enable** for the **Use Windows Synchronization Manager** option.</span></span>  
  
2.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-synchronize-a-pull-subscription-with-synchronization-manager"></a><span data-ttu-id="b8fb5-114">Pour synchroniser un abonnement par extraction de données (pull) avec le Gestionnaire de synchronisation</span><span class="sxs-lookup"><span data-stu-id="b8fb5-114">To synchronize a pull subscription with Synchronization Manager</span></span>  
  
1.  <span data-ttu-id="b8fb5-115">Lancez le Gestionnaire de synchronisation au moyen de l'une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="b8fb5-115">Launch Synchronization Manager using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="b8fb5-116">Dans Internet Explorer, cliquez sur **Outils**, puis sur **Synchroniser**.</span><span class="sxs-lookup"><span data-stu-id="b8fb5-116">In Internet Explorer, click **Tools**, and then click **Synchronize**.</span></span>  
  
    -   <span data-ttu-id="b8fb5-117">Cliquez sur **Démarrer**, pointez sur **Programmes** ou **Tous les programmes**, puis sur **Accessoires**et cliquez sur **Synchroniser**.</span><span class="sxs-lookup"><span data-stu-id="b8fb5-117">Click **Start**, point to **Programs** or **All Programs**, point to **Accessories**, and then click **Synchronize**.</span></span>  
  
    -   <span data-ttu-id="b8fb5-118">Cliquez sur **Démarrer**, puis sur **Exécuter**</span><span class="sxs-lookup"><span data-stu-id="b8fb5-118">Click **Start**, and then click **Run.**</span></span> <span data-ttu-id="b8fb5-119">Dans la boîte de dialogue **exécuter** , tapez `mobsync.exe` dans le champ **ouvrir** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b8fb5-119">In the **Run** dialog box, type `mobsync.exe` in the **Open** field, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="b8fb5-120">Dans la boîte de dialogue **Éléments à synchroniser** , sélectionnez les abonnements à synchroniser.</span><span class="sxs-lookup"><span data-stu-id="b8fb5-120">In the **Items to Synchronize** dialog box, select the subscriptions to synchronize.</span></span> <span data-ttu-id="b8fb5-121">Les abonnements sont listés sous les instances [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installées sur l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="b8fb5-121">Subscriptions are listed under the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances installed on the computer.</span></span>  
  
3.  <span data-ttu-id="b8fb5-122">Cliquez sur **Synchroniser**.</span><span class="sxs-lookup"><span data-stu-id="b8fb5-122">Click **Synchronize**.</span></span>  
  
### <a name="to-reinitialize-a-pull-subscription-with-synchronization-manager"></a><span data-ttu-id="b8fb5-123">Pour réinitialiser un abonnement par extraction de données (pull) avec le Gestionnaire de synchronisation</span><span class="sxs-lookup"><span data-stu-id="b8fb5-123">To reinitialize a pull subscription with Synchronization Manager</span></span>  
  
1.  <span data-ttu-id="b8fb5-124">Dans la boîte de dialogue **Éléments à synchroniser** , sélectionnez un abonnement, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="b8fb5-124">In the **Items to Synchronize** dialog box, select a subscription, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="b8fb5-125">Dans la boîte de dialogue **Propriétés de l'abonnement SQL Server** , cliquez sur **Réinitialiser l'abonnement**.</span><span class="sxs-lookup"><span data-stu-id="b8fb5-125">In the **SQL Server Subscription Properties** dialog box, click **Reinitialize Subscription**.</span></span>  
  
3.  <span data-ttu-id="b8fb5-126">Cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="b8fb5-126">Click **Yes**.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="b8fb5-127">La prochaine fois qu'un abonnement est synchronisé, un nouvel instantané est appliqué par défaut sur la base de données d'abonnement.</span><span class="sxs-lookup"><span data-stu-id="b8fb5-127">The next time the subscription is synchronized, by default a new snapshot is applied to the subscription database.</span></span> <span data-ttu-id="b8fb5-128">Pour plus d’informations, consultez [Réinitialiser des abonnements](reinitialize-subscriptions.md).</span><span class="sxs-lookup"><span data-stu-id="b8fb5-128">For more information, see [Reinitialize Subscriptions](reinitialize-subscriptions.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b8fb5-129">La réplication de fusion permet aux modifications en suspens d'être chargées sur le serveur de publication avant que l'instantané ne soit appliqué, mais cette option n'est pas disponible dans le Gestionnaire de synchronisation.</span><span class="sxs-lookup"><span data-stu-id="b8fb5-129">Merge replication allows any outstanding changes to be uploaded to the Publisher before the snapshot is applied, but this option is not available from Synchronization Manager.</span></span> <span data-ttu-id="b8fb5-130">Pour charger les modifications, synchronisez l'abonnement avant de le réinitialiser.</span><span class="sxs-lookup"><span data-stu-id="b8fb5-130">To upload changes, synchronize the subscription before reinitializing it.</span></span>  
  
### <a name="to-set-properties-for-a-pull-subscription-in-synchronization-manager"></a><span data-ttu-id="b8fb5-131">Pour définir les propriétés d'un abonnement par extraction de données (pull) dans le Gestionnaire de synchronisation</span><span class="sxs-lookup"><span data-stu-id="b8fb5-131">To set properties for a pull subscription in Synchronization Manager</span></span>  
  
1.  <span data-ttu-id="b8fb5-132">Dans la boîte de dialogue **Éléments à synchroniser** , sélectionnez un abonnement, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="b8fb5-132">In the **Items to Synchronize** dialog box, select a subscription, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="b8fb5-133">Affichez et modifiez les propriétés dans les onglets suivants :</span><span class="sxs-lookup"><span data-stu-id="b8fb5-133">View and modify properties on the following tabs:</span></span>  
  
    -   <span data-ttu-id="b8fb5-134">**Identification**</span><span class="sxs-lookup"><span data-stu-id="b8fb5-134">**Identification**</span></span>  
  
    -   <span data-ttu-id="b8fb5-135">**Connexion à l'Abonné**, **Connexion au serveur de distribution**et **Connexion au serveur de publication** (pour la réplication de fusion uniquement)</span><span class="sxs-lookup"><span data-stu-id="b8fb5-135">**Subscriber Login**, **Distributor Login**, and **Publisher Login** (for merge replication only)</span></span>  
  
    -   <span data-ttu-id="b8fb5-136">**Informations sur le serveur Web** (pour les abonnements de fusion sur les abonnés exécutant SQL Server 2005 ou supérieur)</span><span class="sxs-lookup"><span data-stu-id="b8fb5-136">**Web Server Information** (for merge subscriptions on Subscribers running SQL Server 2005 or later)</span></span>  
  
    -   <span data-ttu-id="b8fb5-137">**Autres**</span><span class="sxs-lookup"><span data-stu-id="b8fb5-137">**Other**</span></span>  
  
     <span data-ttu-id="b8fb5-138">Il est recommandé d'utiliser l'authentification Windows pour toutes les connexions.</span><span class="sxs-lookup"><span data-stu-id="b8fb5-138">It is recommended to use Windows Authentication for all connections.</span></span> <span data-ttu-id="b8fb5-139">Pour plus d'informations sur les autorisations requises par l'Agent de distribution et l'Agent de fusion, consultez [Replication Agent Security Model](security/replication-agent-security-model.md).</span><span class="sxs-lookup"><span data-stu-id="b8fb5-139">For information about the permissions required by the Distribution Agent and the Merge Agent, see [Replication Agent Security Model](security/replication-agent-security-model.md).</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-remove-a-pull-subscription-from-synchronization-manager"></a><span data-ttu-id="b8fb5-140">Pour supprimer un abonnement par extraction de données (pull) à partir du Gestionnaire de synchronisation</span><span class="sxs-lookup"><span data-stu-id="b8fb5-140">To remove a pull subscription from Synchronization Manager</span></span>  
  
1.  <span data-ttu-id="b8fb5-141">Dans la boîte de dialogue **Éléments à synchroniser** , sélectionnez un abonnement, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="b8fb5-141">In the **Items to Synchronize** dialog box, select a subscription, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="b8fb5-142">Dans la boîte de dialogue **Propriétés de l'abonnement SQL Server** , cliquez sur **Supprimer l'abonnement**.</span><span class="sxs-lookup"><span data-stu-id="b8fb5-142">In the **SQL Server Subscription Properties** dialog box, click **Remove Subscription**.</span></span>  
  
3.  <span data-ttu-id="b8fb5-143">Sélectionnez une option dans la boîte de dialogue **Supprimer l'abonnement** .</span><span class="sxs-lookup"><span data-stu-id="b8fb5-143">Select an option in the **Remove Subscription** dialog box.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-use-the-interactive-resolver"></a><span data-ttu-id="b8fb5-144">Pour utiliser l'outil de résolution interactive</span><span class="sxs-lookup"><span data-stu-id="b8fb5-144">To use the Interactive Resolver</span></span>  
  
1.  <span data-ttu-id="b8fb5-145">Activez l'article et l'abonnement pour la résolution interactive.</span><span class="sxs-lookup"><span data-stu-id="b8fb5-145">Enable the article and subscription to use interactive resolution.</span></span> <span data-ttu-id="b8fb5-146">Pour plus d’informations, consultez [Spécifier la résolution interactive des conflits pour les articles de fusion](../../relational-databases/replication/publish/specify-merge-replication-properties.md#interactive-conflict-resolution).</span><span class="sxs-lookup"><span data-stu-id="b8fb5-146">For more information, see [Specify Interactive Conflict Resolution for Merge Articles](../../relational-databases/replication/publish/specify-merge-replication-properties.md#interactive-conflict-resolution).</span></span>
  
2.  <span data-ttu-id="b8fb5-147">Une fois que l'abonnement commence la synchronisation dans le Gestionnaire de synchronisation, l'outil de résolution interactive est lancé automatiquement si la résolution interactive de conflits est activée et qu'il existe des conflits pour un ou plusieurs articles.</span><span class="sxs-lookup"><span data-stu-id="b8fb5-147">After the subscription begins synchronizing in Synchronization Manager, the Interactive Resolver launches automatically if interactive conflict resolution is enabled and there are conflicts for one or more articles.</span></span> <span data-ttu-id="b8fb5-148">L'outil de résolution interactive affiche les conflits un à la fois, avec une suggestion de résolution pour chaque conflit (basée sur l'outil de résolution spécifié lors de la création de la publication et de l'abonnement).</span><span class="sxs-lookup"><span data-stu-id="b8fb5-148">The Interactive Resolver displays conflicts one at a time, with a suggested resolution for each conflict (based on the resolver specified when the publication and subscription were created).</span></span>  
  
3.  <span data-ttu-id="b8fb5-149">Modifiez au besoin toute colonne affichée dans l'outil de résolution interactive, puis cliquez sur l'un des boutons suivants pour résoudre le conflit :</span><span class="sxs-lookup"><span data-stu-id="b8fb5-149">Optionally edit any of the columns displayed in the Interactive Resolver, and then click one of the following buttons to resolve the conflict:</span></span>  
  
    -   <span data-ttu-id="b8fb5-150">**Accepter la suggestion**</span><span class="sxs-lookup"><span data-stu-id="b8fb5-150">**Accept Suggested**</span></span>  
  
    -   <span data-ttu-id="b8fb5-151">**Accepter le serveur de publication**</span><span class="sxs-lookup"><span data-stu-id="b8fb5-151">**Accept Publisher**</span></span>  
  
    -   <span data-ttu-id="b8fb5-152">**Accepter l'Abonné**</span><span class="sxs-lookup"><span data-stu-id="b8fb5-152">**Accept Subscriber**</span></span>  
  
    -   <span data-ttu-id="b8fb5-153">**Tout résoudre automatiquement** (tous les conflits actuels sont résolus sans données complémentaires)</span><span class="sxs-lookup"><span data-stu-id="b8fb5-153">**Resolve All Automatically** (all current conflicts are resolved without further input)</span></span>  
  
     <span data-ttu-id="b8fb5-154">La ligne sélectionné est ensuite appliqué au serveur de publication et/ou à l'Abonné ; elle est propagée à d'autres nœuds dans la topologie lors des synchronisations suivantes.</span><span class="sxs-lookup"><span data-stu-id="b8fb5-154">The selected row is then applied to the Publisher and/or Subscriber; it is propagated to other nodes in the topology during subsequent synchronizations.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b8fb5-155">Les modifications ne sont appliquées que si elles font partie de la ligne choisie pour la résolution.</span><span class="sxs-lookup"><span data-stu-id="b8fb5-155">Edits are only applied if they are part of the row that is chosen for resolution.</span></span> <span data-ttu-id="b8fb5-156">Par exemple, si vous effectuez des modifications sous le **Serveur de publication**, puis cliquez sur **Accepter l'Abonné**, les modifications sont ignorées.</span><span class="sxs-lookup"><span data-stu-id="b8fb5-156">For example, if you make edits under **Publisher**, and then click **Accept Subscriber**, the edits are discarded.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8fb5-157">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b8fb5-157">See Also</span></span>  
 [<span data-ttu-id="b8fb5-158">Interactive Conflict Resolution</span><span class="sxs-lookup"><span data-stu-id="b8fb5-158">Interactive Conflict Resolution</span></span>](merge/advanced-merge-replication-conflict-interactive-resolution.md)  
  
