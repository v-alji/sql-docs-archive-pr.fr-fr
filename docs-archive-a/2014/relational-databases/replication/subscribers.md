---
title: Abonnés | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newsubwizard.subscribers.f1
helpviewer_keywords:
- Subscribers [SQL Server replication]
ms.assetid: 43fb2454-c220-4d25-a826-83c332eb00d2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8c5281a53b755bc171cdf96e7856e38ee6a54a1e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603370"
---
# <a name="subscribers"></a><span data-ttu-id="8545b-102">Abonnés</span><span class="sxs-lookup"><span data-stu-id="8545b-102">Subscribers</span></span>
  <span data-ttu-id="8545b-103">Spécifiez le [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou les [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] abonnés non-qui vont recevoir un abonnement à la publication sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="8545b-103">Specify the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or non-[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Subscribers that will receive a subscription to the selected publication.</span></span>  
  
## <a name="options"></a><span data-ttu-id="8545b-104">Options</span><span class="sxs-lookup"><span data-stu-id="8545b-104">Options</span></span>  
 <span data-ttu-id="8545b-105">**Abonnés**</span><span class="sxs-lookup"><span data-stu-id="8545b-105">**Subscribers**</span></span>  
 <span data-ttu-id="8545b-106">Activez la case à cocher dans la grille pour activer la source de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou non-[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] correspondante sous la forme d'un abonné à la publication sélectionnée dans la page **Publication** .</span><span class="sxs-lookup"><span data-stu-id="8545b-106">Select the check box in the grid to enable the corresponding [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or non-[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data source as a Subscriber to the publication chosen on the **Publication** page.</span></span> <span data-ttu-id="8545b-107">Si l'Abonné ne figure pas dans la liste, cliquez sur **Ajouter un abonné** ou **Ajouter un abonné SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="8545b-107">If the Subscriber is not listed, click **Add Subscriber** or **Add SQL Server Subscriber**.</span></span>  
  
 <span data-ttu-id="8545b-108">**Base de données d'abonnement**</span><span class="sxs-lookup"><span data-stu-id="8545b-108">**Subscription database**</span></span>  
 <span data-ttu-id="8545b-109">Les informations affichées et les actions disponibles dépendent du type d'abonné sélectionné dans la colonne **Abonnés** :</span><span class="sxs-lookup"><span data-stu-id="8545b-109">The information displayed in and actions available from this column depend on the type of Subscriber listed in the **Subscribers** column:</span></span>  
  
-   <span data-ttu-id="8545b-110">Pour les abonnés [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , sélectionnez une base de données d'abonnement dans la liste **Base de données d'abonnement** ou créez une base de données en sélectionnant la commande **Nouvelle base de données** dans la même liste.</span><span class="sxs-lookup"><span data-stu-id="8545b-110">For [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Subscribers, select a subscription database from the **Subscription Database** list or create a new database by selecting the **New database** command from the same list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8545b-111">Si vous activez le serveur de publication en tant qu'abonné, la base de données d'abonnement doit être différente de la base de données de publication.</span><span class="sxs-lookup"><span data-stu-id="8545b-111">If you are enabling the Publisher as a Subscriber, the subscription database must be different from the publication database.</span></span>  
  
-   <span data-ttu-id="8545b-112">Pour les abonnés[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , la base de données d'abonnement n'est pas affichée.</span><span class="sxs-lookup"><span data-stu-id="8545b-112">For non-[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Subscribers, the subscription database is not displayed.</span></span> <span data-ttu-id="8545b-113">Définissez la base de données, ainsi que les autres informations de connexion, dans le champ **Nom de la source de données** de la boîte de dialogue **Ajouter un Abonné non-SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="8545b-113">Specify the database, along with other connection information, in the **Data source name** field of the **Add Non-SQL Server** dialog box.</span></span> <span data-ttu-id="8545b-114">Cette boîte de dialogue est disponible en cliquant sur **Ajouter un abonné** et sur **Ajouter un Abonné non-SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="8545b-114">This dialog box is available by clicking **Add Subscriber** and then clicking **Add Non-SQL Server Subscriber**.</span></span>  
  
 <span data-ttu-id="8545b-115">**Ajouter un abonné**</span><span class="sxs-lookup"><span data-stu-id="8545b-115">**Add Subscriber**</span></span>  
 <span data-ttu-id="8545b-116">Ajoute un serveur à la liste des serveurs pouvant être activés comme abonnés.</span><span class="sxs-lookup"><span data-stu-id="8545b-116">Add a server to the list of servers that can be enabled as Subscribers.</span></span> <span data-ttu-id="8545b-117">Ce bouton s'affiche lorsque toutes les conditions suivantes sont vraies :</span><span class="sxs-lookup"><span data-stu-id="8545b-117">This button is displayed when all of the following conditions are true:</span></span>  
  
-   <span data-ttu-id="8545b-118">La publication que vous avez sélectionnée est un instantané ou une publication transactionnelle qui ne prend pas en charge la mise à jour des abonnements.</span><span class="sxs-lookup"><span data-stu-id="8545b-118">The publication you selected is a snapshot or transactional publication that does not support updating subscriptions.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8545b-119">Si la publication à laquelle vous vous abonnez a des abonnements [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et qu'elle n'est pas déjà activée pour les abonnements non-[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , vous ne pouvez pas ajouter d'abonnement non-[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8545b-119">If the publication you are subscribing to has [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] subscriptions and the publication is not already enabled for non-[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Subscribers, you cannot add a non-[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] subscription.</span></span>  
  
-   <span data-ttu-id="8545b-120">L'abonnement est un abonnement par envoi de données (push).</span><span class="sxs-lookup"><span data-stu-id="8545b-120">The subscription is a push subscription.</span></span>  
  
-   <span data-ttu-id="8545b-121">Le serveur de la publication sélectionnée est [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] ou une version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="8545b-121">The Publisher of the selected publication is [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or later.</span></span>  
  
 <span data-ttu-id="8545b-122">Cliquez sur **Ajouter un abonné** pour afficher un menu contenant deux options : **Ajouter un Abonné SQL Server** et **Ajouter un Abonné non-SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="8545b-122">Clicking **Add Subscriber** shows a menu with two choices: **Add SQL Server Subscriber** and **Add Non-SQL Server Subscriber**.</span></span> <span data-ttu-id="8545b-123">Cliquez sur **Ajouter un Abonné non-SQL Server** pour ajouter un abonné Oracle ou IBM DB2.</span><span class="sxs-lookup"><span data-stu-id="8545b-123">Click **Add Non-SQL Server Subscriber** to add an Oracle or IBM DB2 Subscriber.</span></span>  
  
 <span data-ttu-id="8545b-124">**Ajouter un abonné SQL Server**</span><span class="sxs-lookup"><span data-stu-id="8545b-124">**Add SQL Server Subscriber**</span></span>  
 <span data-ttu-id="8545b-125">Ajoute un serveur à la liste des serveurs pouvant être activés comme abonnés.</span><span class="sxs-lookup"><span data-stu-id="8545b-125">Add a server to the list of servers that can be enabled as Subscribers.</span></span> <span data-ttu-id="8545b-126">Ce bouton s'affiche lorsqu'au moins une des conditions suivantes est vraie :</span><span class="sxs-lookup"><span data-stu-id="8545b-126">This button is displayed when one or more of the following conditions is true:</span></span>  
  
-   <span data-ttu-id="8545b-127">La publication que vous avez sélectionnée est une publication de fusion, un instantané ou une publication transactionnelle qui prend en charge la mise à jour des abonnements.</span><span class="sxs-lookup"><span data-stu-id="8545b-127">The publication you selected is a merge publication, or a snapshot or transactional publication that supports updating subscriptions.</span></span>  
  
-   <span data-ttu-id="8545b-128">L'abonnement est un abonnement par extraction de données (pull).</span><span class="sxs-lookup"><span data-stu-id="8545b-128">The subscription is a pull subscription.</span></span>  
  
-   <span data-ttu-id="8545b-129">Le serveur de la publication sélectionnée est antérieure à la version [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8545b-129">The Publisher of the selected publication is earlier than [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="8545b-130">Pour les versions antérieures, le bouton s'affiche uniquement si l'une des conditions suivantes est vraie :</span><span class="sxs-lookup"><span data-stu-id="8545b-130">For earlier versions, the button is displayed only if one or more of the following conditions is true:</span></span>  
  
    -   <span data-ttu-id="8545b-131">Vous êtes membre du rôle serveur fixe **sysadmin** sur le serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="8545b-131">You are a member of the **sysadmin** fixed server role at the Publisher.</span></span>  
  
    -   <span data-ttu-id="8545b-132">L'Abonné a été ajouté à la page **Abonnés** de la boîte de dialogue **Propriétés du serveur de publication** .</span><span class="sxs-lookup"><span data-stu-id="8545b-132">The Subscriber has been added on the **Subscribers** page of the **Publisher Properties** dialog box.</span></span>  
  
    -   <span data-ttu-id="8545b-133">La publication autorise les abonnements anonymes.</span><span class="sxs-lookup"><span data-stu-id="8545b-133">The publication allows anonymous subscriptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8545b-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8545b-134">See Also</span></span>  
 <span data-ttu-id="8545b-135">[Create a Pull Subscription](create-a-pull-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="8545b-135">[Create a Pull Subscription](create-a-pull-subscription.md) </span></span>  
 <span data-ttu-id="8545b-136">[Create a Push Subscription](create-a-push-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="8545b-136">[Create a Push Subscription](create-a-push-subscription.md) </span></span>  
 <span data-ttu-id="8545b-137">[Non-SQL Server Subscribers](non-sql/non-sql-server-subscribers.md) </span><span class="sxs-lookup"><span data-stu-id="8545b-137">[Non-SQL Server Subscribers](non-sql/non-sql-server-subscribers.md) </span></span>  
 [<span data-ttu-id="8545b-138">S'abonner à des publications</span><span class="sxs-lookup"><span data-stu-id="8545b-138">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
