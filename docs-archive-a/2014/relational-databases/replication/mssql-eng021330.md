---
title: MSSQL_ENG021330 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG021330 error
ms.assetid: e2bb2e21-62a7-4689-b68b-bdfba3fdd985
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4338756a641b23bfc6f52da6b3de296bb6415756
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697943"
---
# <a name="mssql_eng021330"></a><span data-ttu-id="e8ad4-102">MSSQL_ENG021330</span><span class="sxs-lookup"><span data-stu-id="e8ad4-102">MSSQL_ENG021330</span></span>
    
## <a name="message-details"></a><span data-ttu-id="e8ad4-103">Détails du message</span><span class="sxs-lookup"><span data-stu-id="e8ad4-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e8ad4-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="e8ad4-104">Product Name</span></span>|<span data-ttu-id="e8ad4-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e8ad4-105">SQL Server</span></span>|  
|<span data-ttu-id="e8ad4-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="e8ad4-106">Event ID</span></span>|<span data-ttu-id="e8ad4-107">21330</span><span class="sxs-lookup"><span data-stu-id="e8ad4-107">21330</span></span>|  
|<span data-ttu-id="e8ad4-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="e8ad4-108">Event Source</span></span>|<span data-ttu-id="e8ad4-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e8ad4-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e8ad4-110">Composant</span><span class="sxs-lookup"><span data-stu-id="e8ad4-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="e8ad4-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="e8ad4-111">Symbolic Name</span></span>||  
|<span data-ttu-id="e8ad4-112">Texte du message</span><span class="sxs-lookup"><span data-stu-id="e8ad4-112">Message Text</span></span>|<span data-ttu-id="e8ad4-113">Impossible de créer un sous-répertoire dans le répertoire de travail de la réplication.(%1!)</span><span class="sxs-lookup"><span data-stu-id="e8ad4-113">Failed to create a sub-directory under the replication working directory.(%ls)</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e8ad4-114">Explication</span><span class="sxs-lookup"><span data-stu-id="e8ad4-114">Explanation</span></span>  
 <span data-ttu-id="e8ad4-115">Cette erreur peut se produire quand un abonnement est initialisé manuellement et qu'il y a un problème de création du répertoire où les scripts de réplication sont stockés.</span><span class="sxs-lookup"><span data-stu-id="e8ad4-115">This error can occur when a subscription is initialized manually, and there is a problem creating the directory in which replication scripts are stored.</span></span> <span data-ttu-id="e8ad4-116">L'erreur peut être due à un problème d'autorisations : lorsqu'un abonnement est initialisé sans utiliser d'instantané, le compte sous lequel le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] s'exécute sur le serveur de publication doit disposer d'autorisations en écriture sur le dossier d'instantané hébergé sur le serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="e8ad4-116">The error can be caused by a permissions issue: when a subscription is initialized without using a snapshot, the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs at the Publisher must have write permissions on the snapshot folder at the Distributor.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e8ad4-117">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="e8ad4-117">User Action</span></span>  
 <span data-ttu-id="e8ad4-118">Vérifiez que le chemin d'accès correct a été spécifié pour le dossier d'instantané et que le compte sous lequel le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] s'exécute sur le serveur de publication a des autorisations suffisantes.</span><span class="sxs-lookup"><span data-stu-id="e8ad4-118">Ensure that the correct path has been specified for the snapshot folder and that the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs at the Publisher has sufficient permissions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8ad4-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e8ad4-119">See Also</span></span>  
 <span data-ttu-id="e8ad4-120">[Spécifier l’emplacement par défaut des instantanés](snapshot-options.md#snapshot-folder-locations) </span><span class="sxs-lookup"><span data-stu-id="e8ad4-120">[Specify the Default Snapshot Location](snapshot-options.md#snapshot-folder-locations) </span></span>  
 <span data-ttu-id="e8ad4-121">[Guide de référence des erreurs et des événements &#40;réplication&#41;](errors-and-events-reference-replication.md) </span><span class="sxs-lookup"><span data-stu-id="e8ad4-121">[Errors and Events Reference &#40;Replication&#41;](errors-and-events-reference-replication.md) </span></span>  
 [<span data-ttu-id="e8ad4-122">Initialiser un abonnement transactionnel sans instantané</span><span class="sxs-lookup"><span data-stu-id="e8ad4-122">Initialize a Transactional Subscription Without a Snapshot</span></span>](initialize-a-transactional-subscription-without-a-snapshot.md)  
  
  
