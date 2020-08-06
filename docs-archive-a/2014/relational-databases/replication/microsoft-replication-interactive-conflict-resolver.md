---
title: Outil de résolution des conflits de réplication Microsoft interactif | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.replconflictviewer.interactiveresolver.f1
ms.assetid: d3d4a480-782b-4b1d-b839-565c8cf6cb24
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c8cbd2231ab1ab357321f9887bced986e182e608
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709204"
---
# <a name="microsoft-replication-interactive-conflict-resolver"></a><span data-ttu-id="300f3-102">Outil de résolution des conflits de réplication Microsoft interactif</span><span class="sxs-lookup"><span data-stu-id="300f3-102">Microsoft Replication Interactive Conflict Resolver</span></span>
  <span data-ttu-id="300f3-103">L'Outil de résolution des conflits de réplication Microsoft interactif peut s'utiliser pour les abonnements de fusion synchronisés au moyen du Gestionnaire de synchronisation Windows.</span><span class="sxs-lookup"><span data-stu-id="300f3-103">The Interactive Conflict Resolver can be used for merge subscriptions that are synchronized using Windows Synchronization Manager.</span></span> <span data-ttu-id="300f3-104">Il permet d'afficher, comparer, modifier et sélectionner les conflits dans les données des résultats.</span><span class="sxs-lookup"><span data-stu-id="300f3-104">It allows you to view, compare, edit, and select the outcome for data conflicts.</span></span> <span data-ttu-id="300f3-105">La réplication comporte également l'Outil de résolution des conflits qui permet d'afficher et de modifier les résultats des conflits après leur validation.</span><span class="sxs-lookup"><span data-stu-id="300f3-105">Replication also includes the Conflict Viewer, which allows you to view and modify conflict outcomes after they have been committed.</span></span> <span data-ttu-id="300f3-106">L'Outil de résolution des conflits interactif permet de sélectionner le résultat pendant la synchronisation.</span><span class="sxs-lookup"><span data-stu-id="300f3-106">The Interactive Conflict Resolver allows you to select the outcome during synchronization.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="300f3-107">Les conflits qui concernent des enregistrements logiques ne sont pas affichés dans le résolveur interactif.</span><span class="sxs-lookup"><span data-stu-id="300f3-107">Conflicts that involve logical records are not displayed in the Interactive Resolver.</span></span> <span data-ttu-id="300f3-108">Pour afficher des informations sur ces conflits, utilisez des procédures stockées de réplication.</span><span class="sxs-lookup"><span data-stu-id="300f3-108">To view information about these conflicts, use replication stored procedures.</span></span> <span data-ttu-id="300f3-109">Pour plus d’informations, consultez [Afficher les informations relatives aux conflits pour les publications de fusion &#40;programmation Transact-SQL de la réplication&#41;](view-conflict-information-for-merge-publications.md).</span><span class="sxs-lookup"><span data-stu-id="300f3-109">For more information, see [View Conflict Information for Merge Publications &#40;Replication Transact-SQL Programming&#41;](view-conflict-information-for-merge-publications.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="300f3-110">Options</span><span class="sxs-lookup"><span data-stu-id="300f3-110">Options</span></span>  
 <span data-ttu-id="300f3-111">**Nom de la colonne**</span><span class="sxs-lookup"><span data-stu-id="300f3-111">**Column name**</span></span>  
 <span data-ttu-id="300f3-112">Noms de toutes les colonnes de la table.</span><span class="sxs-lookup"><span data-stu-id="300f3-112">The name of all columns in the table.</span></span> <span data-ttu-id="300f3-113">Une ou plusieurs colonnes peuvent comporter des données en conflit.</span><span class="sxs-lookup"><span data-stu-id="300f3-113">One or more columns might have conflicting data.</span></span> <span data-ttu-id="300f3-114">Indépendamment des colonnes en conflit, la ligne gagnante complète remplace la totalité de la ligne perdante.</span><span class="sxs-lookup"><span data-stu-id="300f3-114">Regardless of which columns conflict, the entire winning row will overwrite the entire losing row.</span></span>  
  
 <span data-ttu-id="300f3-115">**Résolution suggérée**</span><span class="sxs-lookup"><span data-stu-id="300f3-115">**Suggested Resolution**</span></span>  
 <span data-ttu-id="300f3-116">Résolution du conflit suggérée par l'outil de résolution des conflits pour l'article.</span><span class="sxs-lookup"><span data-stu-id="300f3-116">The suggested resolution provided by the conflict resolver for the article.</span></span>  
  
 <span data-ttu-id="300f3-117">**Publisher**</span><span class="sxs-lookup"><span data-stu-id="300f3-117">**Publisher**</span></span>  
 <span data-ttu-id="300f3-118">Valeur des données du serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="300f3-118">The data value at the Publisher.</span></span>  
  
 <span data-ttu-id="300f3-119">**Abonné**</span><span class="sxs-lookup"><span data-stu-id="300f3-119">**Subscriber**</span></span>  
 <span data-ttu-id="300f3-120">Valeur des données de l'abonné.</span><span class="sxs-lookup"><span data-stu-id="300f3-120">The data value at the Subscriber.</span></span>  
  
 <span data-ttu-id="300f3-121">**Accepter la suggestion**, **Accepter le serveur de publication**et **Accepter l'Abonné**</span><span class="sxs-lookup"><span data-stu-id="300f3-121">**Accept Suggested**, **Accept Publisher**, and **Accept Subscriber**</span></span>  
 <span data-ttu-id="300f3-122">Cliquez sur l'option correspondante pour accepter la ligne qui sera appliquée par le serveur de publication ou l'abonné, en fonction du perdant du conflit.</span><span class="sxs-lookup"><span data-stu-id="300f3-122">Click to accept the row that will be applied at either the Publisher or the Subscriber, depending on which one lost the conflict.</span></span> <span data-ttu-id="300f3-123">Si le serveur de publication perd le conflit, tous les autres abonnés reçoivent la ligne gagnante lors de leur prochaine synchronisation avec le serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="300f3-123">If the Publisher lost the conflict, all other Subscribers will receive the winning row the next time they synchronize with the Publisher.</span></span>  
  
 <span data-ttu-id="300f3-124">**Résoudre automatiquement tous les conflits restants**</span><span class="sxs-lookup"><span data-stu-id="300f3-124">**Resolve remaining conflicts automatically**</span></span>  
 <span data-ttu-id="300f3-125">Résout tous les conflits restants en utilisant la résolution suggérée par l'outil de résolution des conflits pour l'article.</span><span class="sxs-lookup"><span data-stu-id="300f3-125">Resolve all remaining conflicts using the suggested resolution provided by the conflict resolver for the article.</span></span>  
  
 <span data-ttu-id="300f3-126">**Journaliser les détails de ce conflit pour future référence**</span><span class="sxs-lookup"><span data-stu-id="300f3-126">**Log the details of the conflict for later reference**</span></span>  
 <span data-ttu-id="300f3-127">Enregistre les détails du conflit dans des tables système.</span><span class="sxs-lookup"><span data-stu-id="300f3-127">Logs the details of the conflict in system tables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="300f3-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="300f3-128">See Also</span></span>  
 <span data-ttu-id="300f3-129">[Résolution interactive des conflits](merge/advanced-merge-replication-conflict-interactive-resolution.md) </span><span class="sxs-lookup"><span data-stu-id="300f3-129">[Interactive Conflict Resolution](merge/advanced-merge-replication-conflict-interactive-resolution.md) </span></span>  
 <span data-ttu-id="300f3-130">[Afficher et résoudre les conflits de données pour les publications de fusion &#40;SQL Server Management Studio&#41;](view-and-resolve-data-conflicts-for-merge-publications.md) </span><span class="sxs-lookup"><span data-stu-id="300f3-130">[View and Resolve Data Conflicts for Merge Publications &#40;SQL Server Management Studio&#41;](view-and-resolve-data-conflicts-for-merge-publications.md) </span></span>  
 <span data-ttu-id="300f3-131">[Synchroniser un abonnement à l’aide du Gestionnaire de synchronisation Windows &#40;Gestionnaire de synchronisation Windows&#41;](synchronize-a-subscription-using-windows-synchronization-manager.md) </span><span class="sxs-lookup"><span data-stu-id="300f3-131">[Synchronize a Subscription Using Windows Synchronization Manager &#40;Windows Synchronization Manager&#41;](synchronize-a-subscription-using-windows-synchronization-manager.md) </span></span>  
 [<span data-ttu-id="300f3-132">Advanced Merge Replication Conflict Detection and Resolution</span><span class="sxs-lookup"><span data-stu-id="300f3-132">Advanced Merge Replication Conflict Detection and Resolution</span></span>](merge/advanced-merge-replication-conflict-detection-and-resolution.md)  
  
  
