---
title: MSSQLSERVER_601 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "601"
helpviewer_keywords:
- 601 (Database Engine error)
ms.assetid: 2039cc0a-9a43-4369-a04a-935e384388b6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 459a983d72a91e628e8cc33636d3abd81998f1d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614108"
---
# <a name="mssqlserver_601"></a><span data-ttu-id="d28b2-102">MSSQLSERVER_601</span><span class="sxs-lookup"><span data-stu-id="d28b2-102">MSSQLSERVER_601</span></span>
    
## <a name="details"></a><span data-ttu-id="d28b2-103">Détails</span><span class="sxs-lookup"><span data-stu-id="d28b2-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d28b2-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="d28b2-104">Product Name</span></span>|<span data-ttu-id="d28b2-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d28b2-105">SQL Server</span></span>|  
|<span data-ttu-id="d28b2-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="d28b2-106">Event ID</span></span>|<span data-ttu-id="d28b2-107">601</span><span class="sxs-lookup"><span data-stu-id="d28b2-107">601</span></span>|  
|<span data-ttu-id="d28b2-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="d28b2-108">Event Source</span></span>|<span data-ttu-id="d28b2-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d28b2-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d28b2-110">Composant</span><span class="sxs-lookup"><span data-stu-id="d28b2-110">Component</span></span>|<span data-ttu-id="d28b2-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="d28b2-111">SQLEngine</span></span>|  
|<span data-ttu-id="d28b2-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="d28b2-112">Symbolic Name</span></span>||  
|<span data-ttu-id="d28b2-113">Texte du message</span><span class="sxs-lookup"><span data-stu-id="d28b2-113">Message Text</span></span>|<span data-ttu-id="d28b2-114">Impossible de poursuivre l'analyse avec NOLOCK car les données ont été déplacées.</span><span class="sxs-lookup"><span data-stu-id="d28b2-114">Could not continue scan with NOLOCK due to data movement.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d28b2-115">Explication</span><span class="sxs-lookup"><span data-stu-id="d28b2-115">Explanation</span></span>  
 <span data-ttu-id="d28b2-116">Le [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] ne peut pas poursuivre l'exécution de la requête, car elle tente de lire des données qui ont été mises à jour ou supprimées par une autre transaction.</span><span class="sxs-lookup"><span data-stu-id="d28b2-116">The [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] cannot continue executing the query because it is trying to read data that was updated or deleted by another transaction.</span></span> <span data-ttu-id="d28b2-117">La requête utilise l'indicateur de verrouillage NOLOCK ou le niveau d'isolement de la transaction READ UNCOMMITTED.</span><span class="sxs-lookup"><span data-stu-id="d28b2-117">The query is using either the NOLOCK locking hint or the READ UNCOMMITTED transaction isolation level.</span></span>  
  
 <span data-ttu-id="d28b2-118">L'accès aux données qui sont modifiées par une autre transaction est généralement refusé en raison des verrous appliqués aux données.</span><span class="sxs-lookup"><span data-stu-id="d28b2-118">Typically, access to data that is being changed by another transaction is denied because of locks put on the data.</span></span> <span data-ttu-id="d28b2-119">Toutefois, l'indicateur de verrouillage NOLOCK et le niveau d'isolement de la transaction READ UNCOMMITTED permettent à une requête de lire les données qui sont verrouillées par une autre transaction.</span><span class="sxs-lookup"><span data-stu-id="d28b2-119">However, the NOLOCK locking hint and READ UNCOMMITTED transaction isolation level let a query read data that is locked by another transaction.</span></span> <span data-ttu-id="d28b2-120">Il s'agit alors d'une lecture erronée car vous êtes en mesure de lire les valeurs qui n'ont pas encore été validées et qui sont susceptibles d'être modifiées.</span><span class="sxs-lookup"><span data-stu-id="d28b2-120">This is referred to as a dirty read because you can read values that have not yet been committed and that are subject to change.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d28b2-121">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="d28b2-121">User Action</span></span>  
 <span data-ttu-id="d28b2-122">Cette erreur annule la requête.</span><span class="sxs-lookup"><span data-stu-id="d28b2-122">This error cancels the query.</span></span> <span data-ttu-id="d28b2-123">Soumettez une nouvelle fois la requête ou supprimez l'indicateur de verrouillage NOLOCK.</span><span class="sxs-lookup"><span data-stu-id="d28b2-123">Either resubmit the query or remove the NOLOCK locking hint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d28b2-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d28b2-124">See Also</span></span>  
 <span data-ttu-id="d28b2-125">[MSSQLSERVER_605](mssqlserver-605-database-engine-error.md) </span><span class="sxs-lookup"><span data-stu-id="d28b2-125">[MSSQLSERVER_605](mssqlserver-605-database-engine-error.md) </span></span>  
 <span data-ttu-id="d28b2-126">[Indicateurs de table &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-table) </span><span class="sxs-lookup"><span data-stu-id="d28b2-126">[Table Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-table) </span></span>  
 <span data-ttu-id="d28b2-127">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d28b2-127">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span></span>  
 [<span data-ttu-id="d28b2-128">SET TRANSACTION ISOLATION LEVEL &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d28b2-128">SET TRANSACTION ISOLATION LEVEL &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/set-transaction-isolation-level-transact-sql)  
  
  
