---
title: Transactions (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- transactions [Master Data Services], about transactions
- transactions [Master Data Services]
ms.assetid: 4cd2fa6f-9c76-4b7a-ae18-d4e5fd2f03f5
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c693b550e0c1adb8f5910d99c7125c85f41abb8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707647"
---
# <a name="transactions-master-data-services"></a><span data-ttu-id="3cb77-102">Transactions (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="3cb77-102">Transactions (Master Data Services)</span></span>
  <span data-ttu-id="3cb77-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], une transaction est enregistrée à chaque fois qu'une action est effectuée sur un membre.</span><span class="sxs-lookup"><span data-stu-id="3cb77-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], a transaction is recorded each time action is taken on a member.</span></span> <span data-ttu-id="3cb77-104">Les transactions peuvent être affichées par tous les utilisateurs et être inversées par les administrateurs.</span><span class="sxs-lookup"><span data-stu-id="3cb77-104">Transactions can be viewed by all users and reversed by administrators.</span></span> <span data-ttu-id="3cb77-105">Les transactions affichent la date, l'heure et l'utilisateur qui a effectué l'action, ainsi que d'autres détails.</span><span class="sxs-lookup"><span data-stu-id="3cb77-105">Transactions show the date, time, and user who took the action, along with other details.</span></span> <span data-ttu-id="3cb77-106">Les utilisateurs peuvent ajouter une annotation à une transaction, pour indiquer pourquoi une transaction a eu lieu.</span><span class="sxs-lookup"><span data-stu-id="3cb77-106">Users can add an annotation to a transaction, to indicate why a transaction took place.</span></span>  
  
## <a name="when-transaction-are-recorded"></a><span data-ttu-id="3cb77-107">Critères d'enregistrement des transactions</span><span class="sxs-lookup"><span data-stu-id="3cb77-107">When Transaction Are Recorded</span></span>  
 <span data-ttu-id="3cb77-108">Des transactions sont enregistrées lorsque des membres :</span><span class="sxs-lookup"><span data-stu-id="3cb77-108">Transactions are recorded when members:</span></span>  
  
-   <span data-ttu-id="3cb77-109">sont créés, supprimés ou réactivés ;</span><span class="sxs-lookup"><span data-stu-id="3cb77-109">Are created, deleted, or reactivated.</span></span>  
  
-   <span data-ttu-id="3cb77-110">ont des valeurs d'attribut modifiées ;</span><span class="sxs-lookup"><span data-stu-id="3cb77-110">Have attribute values changed.</span></span>  
  
-   <span data-ttu-id="3cb77-111">sont inclus dans une hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="3cb77-111">Are moved in a hierarchy.</span></span>  
  
 <span data-ttu-id="3cb77-112">Les transactions ne sont pas enregistrées lorsque les règles d'entreprise modifient des valeurs d'attribut.</span><span class="sxs-lookup"><span data-stu-id="3cb77-112">Transactions are not recorded when business rules change attribute values.</span></span>  
  
## <a name="view-and-manage-transactions"></a><span data-ttu-id="3cb77-113">Afficher et gérer des transactions</span><span class="sxs-lookup"><span data-stu-id="3cb77-113">View and Manage Transactions</span></span>  
 <span data-ttu-id="3cb77-114">Dans la zone fonctionnelle **Explorateur** , vous pouvez afficher et annoter les transactions (leur ajouter des commentaires) que vous avez effectuées.</span><span class="sxs-lookup"><span data-stu-id="3cb77-114">In the **Explorer** functional area, you can view and annotate (add comments to) the transactions that you made yourself.</span></span>  
  
 <span data-ttu-id="3cb77-115">Dans la zone fonctionnelle **Gestion des versions** , les administrateurs peuvent consulter toutes les transactions de tous les utilisateurs pour les modèles auxquels ils ont accès, et inverser l'une quelconque de ces transactions.</span><span class="sxs-lookup"><span data-stu-id="3cb77-115">In the **Version Management** functional area, administrators can view all transactions for all users for the models they have access to, and reverse any of these transactions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3cb77-116">Les administrateurs peuvent afficher toutes les transactions pour tous les utilisateurs tant qu’ils n’ont pas le niveau d’autorisation de lecture seule appliqué dans la zone fonctionnelle **Gestion des versions**.</span><span class="sxs-lookup"><span data-stu-id="3cb77-116">Administrators can view all transactions for all users as long as they don't have the read-only permission level applied in the **Version Management** functional area .</span></span> <span data-ttu-id="3cb77-117">Par exemple, si le niveau d’autorisation de lecture seule et de mise à jour est défini pour l’administrateur, celui-ci ne peut pas voir les autres transactions utilisateur, car l’autorisation de lecture seule est prioritaire sur l’autorisation de mise à jour.</span><span class="sxs-lookup"><span data-stu-id="3cb77-117">For example, if the read-only permission and update permission level is set for the administrator, the administrator will not be able to see other user transactions because the read-only permission will take precedence over the update permission.</span></span>

## <a name="system-settings"></a><span data-ttu-id="3cb77-118">Paramètres système</span><span class="sxs-lookup"><span data-stu-id="3cb77-118">System Settings</span></span>  
 <span data-ttu-id="3cb77-119">Il existe un paramètre dans le [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] qui détermine si les transactions sont enregistrées ou non lors de l'organisation des enregistrements.</span><span class="sxs-lookup"><span data-stu-id="3cb77-119">There is a setting in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] that affects whether or not transactions are recorded when records are staged.</span></span> <span data-ttu-id="3cb77-120">Ce paramètre affecte SQL Server 2008 R2 uniquement.</span><span class="sxs-lookup"><span data-stu-id="3cb77-120">This setting affects SQL Server 2008 R2 only.</span></span> <span data-ttu-id="3cb77-121">Vous pouvez ajuster ce paramètre dans le [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] ou directement dans la table Paramètres système de la base de données [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3cb77-121">You can adjust this setting in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] or directly in the System Settings table in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="3cb77-122">Pour plus d’informations, consultez [Paramètres système &#40;Master Data Services&#41;](system-settings-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="3cb77-122">For more information, see [System Settings &#40;Master Data Services&#41;](system-settings-master-data-services.md).</span></span>  
  
 <span data-ttu-id="3cb77-123">Lors de l'importation de données dans cette version de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], vous pouvez spécifier s'il faut enregistrer les transactions lors de l'initialisation de la procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="3cb77-123">When importing data in this version of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], you can specify whether or not to log transactions when initiating the stored procedure.</span></span> <span data-ttu-id="3cb77-124">Pour plus d’informations, consultez [Procédure stockée de mise en lots &#40;Master Data Services&#41;](../../2014/master-data-services/staging-stored-procedure-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="3cb77-124">For more information, see [Staging Stored Procedure &#40;Master Data Services&#41;](../../2014/master-data-services/staging-stored-procedure-master-data-services.md).</span></span>  
  
## <a name="concurrency"></a><span data-ttu-id="3cb77-125">Accès concurrentiel</span><span class="sxs-lookup"><span data-stu-id="3cb77-125">Concurrency</span></span>  
 <span data-ttu-id="3cb77-126">Si une valeur d'entité spécifique est affichée simultanément dans plusieurs sessions de l'Explorateur, les modifications simultanées d'une même valeur sont possibles.</span><span class="sxs-lookup"><span data-stu-id="3cb77-126">If a particular entity value is shown simultaneously in more than one Explorer session, concurrent edits to the same value are possible.</span></span> <span data-ttu-id="3cb77-127">Les modifications simultanées ne sont pas détectées automatiquement par MDS.</span><span class="sxs-lookup"><span data-stu-id="3cb77-127">Concurrent edits will not be detected automatically by MDS.</span></span> <span data-ttu-id="3cb77-128">Cela peut se produire lorsque plusieurs utilisateurs utilisent plusieurs sessions de l'explorateur MDS dans le navigateur Web, par exemple sur plusieurs ordinateurs, sous plusieurs onglets de navigateur ou dans plusieurs fenêtres, ou avec plusieurs comptes utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3cb77-128">This can occur when multiple users use the MDS Explorer in the Web browser from multiple sessions, for example from multiple computers, multiple browser tabs or windows, or multiple user accounts.</span></span>  
  
 <span data-ttu-id="3cb77-129">Plusieurs utilisateurs peuvent mettre à jour les mêmes valeurs d'entité sans erreur malgré les transactions activées.</span><span class="sxs-lookup"><span data-stu-id="3cb77-129">More than one user can update the same entity values without error despite transactions being enabled.</span></span> <span data-ttu-id="3cb77-130">En général, la dernière modification de la valeur dans un même intervalle de temps prévaut.</span><span class="sxs-lookup"><span data-stu-id="3cb77-130">Typically the last edit to the value in a sequence of time will take precedence.</span></span> <span data-ttu-id="3cb77-131">Les conflits de modifications en double peuvent être observés dans l'historique des transactions et peuvent être corrigés manuellement par l'administrateur.</span><span class="sxs-lookup"><span data-stu-id="3cb77-131">The duplicate edit conflict can be manually observed in the transaction history and can be reversed manually by the administrator.</span></span> <span data-ttu-id="3cb77-132">L'historique des transactions affiche les transactions individuelles pour **Valeur précédente** et **Nouvelle valeur** pour l'attribut en question dans chaque session, mais ne corrige pas automatiquement le conflit lorsque plusieurs **Nouvelles valeurs** existent pour la même valeur de départ.</span><span class="sxs-lookup"><span data-stu-id="3cb77-132">The transaction history will show the individual transactions for the **Prior value** and **New value** for the attribute in question from each session, but will not automatically resolve the conflict when multiple **New Values** exist for the same old value.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="3cb77-133">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="3cb77-133">Related Tasks</span></span>  
  
|<span data-ttu-id="3cb77-134">Description de la tâche</span><span class="sxs-lookup"><span data-stu-id="3cb77-134">Task Description</span></span>|<span data-ttu-id="3cb77-135">Rubrique</span><span class="sxs-lookup"><span data-stu-id="3cb77-135">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="3cb77-136">Annuler une action en inversant une transaction (administrateurs uniquement)</span><span class="sxs-lookup"><span data-stu-id="3cb77-136">Undo an action by reversing a transaction (administrators only).</span></span>|[<span data-ttu-id="3cb77-137">Inverser une transaction &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="3cb77-137">Reverse a Transaction &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/reverse-a-transaction-master-data-services.md)|  
  
## <a name="related-content"></a><span data-ttu-id="3cb77-138">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="3cb77-138">Related Content</span></span>  
  
-   [<span data-ttu-id="3cb77-139">Administrateurs &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="3cb77-139">Administrators &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/administrators-master-data-services.md)  
  
-   [<span data-ttu-id="3cb77-140">Annotations &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="3cb77-140">Annotations &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/annotations-master-data-services.md)  
  
  
