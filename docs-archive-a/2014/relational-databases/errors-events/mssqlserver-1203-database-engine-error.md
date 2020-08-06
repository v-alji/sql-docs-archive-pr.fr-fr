---
title: MSSQLSERVER_1203 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1203 (Database Engine error)
ms.assetid: 33a35f00-98c8-46c6-b432-544b326b6117
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3cea816a60ccd1b90d849194766edebd2d64d0b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612393"
---
# <a name="mssqlserver_1203"></a><span data-ttu-id="bbb71-102">MSSQLSERVER_1203</span><span class="sxs-lookup"><span data-stu-id="bbb71-102">MSSQLSERVER_1203</span></span>
    
## <a name="details"></a><span data-ttu-id="bbb71-103">Détails</span><span class="sxs-lookup"><span data-stu-id="bbb71-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bbb71-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="bbb71-104">Product Name</span></span>|<span data-ttu-id="bbb71-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="bbb71-105">SQL Server</span></span>|  
|<span data-ttu-id="bbb71-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="bbb71-106">Event ID</span></span>|<span data-ttu-id="bbb71-107">1203</span><span class="sxs-lookup"><span data-stu-id="bbb71-107">1203</span></span>|  
|<span data-ttu-id="bbb71-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="bbb71-108">Event Source</span></span>|<span data-ttu-id="bbb71-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="bbb71-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="bbb71-110">Composant</span><span class="sxs-lookup"><span data-stu-id="bbb71-110">Component</span></span>|<span data-ttu-id="bbb71-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="bbb71-111">SQLEngine</span></span>|  
|<span data-ttu-id="bbb71-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="bbb71-112">Symbolic Name</span></span>|<span data-ttu-id="bbb71-113">LK_NOT</span><span class="sxs-lookup"><span data-stu-id="bbb71-113">LK_NOT</span></span>|  
|<span data-ttu-id="bbb71-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="bbb71-114">Message Text</span></span>|<span data-ttu-id="bbb71-115">L'ID de processus %d a essayé de déverrouiller une ressource qu'il ne possède pas :%.\*ls.</span><span class="sxs-lookup"><span data-stu-id="bbb71-115">Process ID %d attempted to unlock a resource it does not own: %.\*ls.</span></span> <span data-ttu-id="bbb71-116">Réessayez la transaction, car cette erreur est peut-être provoquée par une condition basée sur le temps.</span><span class="sxs-lookup"><span data-stu-id="bbb71-116">Retry the transaction, because this error may be caused by a timing condition.</span></span> <span data-ttu-id="bbb71-117">Si le problème persiste, contactez l'administrateur de base de données.</span><span class="sxs-lookup"><span data-stu-id="bbb71-117">If the problem persists, contact the database administrator.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="bbb71-118">Explication</span><span class="sxs-lookup"><span data-stu-id="bbb71-118">Explanation</span></span>  
 <span data-ttu-id="bbb71-119">Cette erreur se produit lorsque [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est engagé dans une activité autre que le nettoyage de post-traitement standard et que la page qu'il est en train d'essayer de déverrouiller est déjà déverrouillée.</span><span class="sxs-lookup"><span data-stu-id="bbb71-119">This error occurs when [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is engaged in some activity other than ordinary post-processing cleanup and it finds that a particular page that it is trying to unlock is already unlocked.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="bbb71-120">Causes possibles</span><span class="sxs-lookup"><span data-stu-id="bbb71-120">Possible Causes</span></span>  
 <span data-ttu-id="bbb71-121">La cause sous-jacente de cette erreur peut être liée à des problèmes structurels au sein de la base de données concernée.</span><span class="sxs-lookup"><span data-stu-id="bbb71-121">The underlying cause of this error may be related to structural problems within the affected database.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="bbb71-122">gère l'acquisition et la libération de pages pour maintenir le contrôle de simultanéité dans l'environnement multi-utilisateur.</span><span class="sxs-lookup"><span data-stu-id="bbb71-122">manages the acquisition and release of pages to maintain concurrency control in the multiuser environment.</span></span> <span data-ttu-id="bbb71-123">Ce mécanisme est géré à l'aide de diverses structures de verrous internes qui identifient la page et le type de verrou présent.</span><span class="sxs-lookup"><span data-stu-id="bbb71-123">This mechanism is maintained by using various internal lock structures that identify the page and the type of lock present.</span></span> <span data-ttu-id="bbb71-124">Les verrous sont acquis pour le traitement des pages concernées, puis libérés une fois le traitement terminé.</span><span class="sxs-lookup"><span data-stu-id="bbb71-124">Locks are acquired for processing of affected pages and released when the processing is finished.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bbb71-125">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="bbb71-125">User Action</span></span>  
 <span data-ttu-id="bbb71-126">Exécutez DBCC CHECKDB sur la base de données à laquelle appartient l'objet.</span><span class="sxs-lookup"><span data-stu-id="bbb71-126">Execute DBCC CHECKDB against the database in which the object belongs.</span></span> <span data-ttu-id="bbb71-127">Si DBCC CHECKDB n'indique aucune erreur, essayez de rétablir la connexion et d'exécuter la commande.</span><span class="sxs-lookup"><span data-stu-id="bbb71-127">If DBCC CHECKDB reports no errors, try to reestablish the connection and execute the command.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="bbb71-128">Si l'exécution de DBCC CHECKDB avec l'une des clauses REPAIR ne résout pas le problème d'index ou si vous ne savez pas quelles conséquences l'exécution de DBCC CHECKDB avec une clause REPAIR peut avoir sur vos données, contactez votre fournisseur d'assistance principal.</span><span class="sxs-lookup"><span data-stu-id="bbb71-128">If you are executing DBCC CHECKDB with one of the REPAIR clauses does not correct the index problem, or if you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider.</span></span>  
  
  
