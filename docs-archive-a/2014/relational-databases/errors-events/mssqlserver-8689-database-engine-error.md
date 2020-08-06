---
title: MSSQLSERVER_8689 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8689 (Database Engine error)
ms.assetid: 99467a32-6576-4272-a076-b16c06933f2a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2cdca0a3cd9ce47ccb39ebeaf8fd1cd260aafbd9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698220"
---
# <a name="mssqlserver_8689"></a><span data-ttu-id="5afe4-102">MSSQLSERVER_8689</span><span class="sxs-lookup"><span data-stu-id="5afe4-102">MSSQLSERVER_8689</span></span>
    
## <a name="details"></a><span data-ttu-id="5afe4-103">Détails</span><span class="sxs-lookup"><span data-stu-id="5afe4-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5afe4-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="5afe4-104">Product Name</span></span>|<span data-ttu-id="5afe4-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="5afe4-105">SQL Server</span></span>|  
|<span data-ttu-id="5afe4-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="5afe4-106">Event ID</span></span>|<span data-ttu-id="5afe4-107">8689</span><span class="sxs-lookup"><span data-stu-id="5afe4-107">8689</span></span>|  
|<span data-ttu-id="5afe4-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="5afe4-108">Event Source</span></span>|<span data-ttu-id="5afe4-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="5afe4-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="5afe4-110">Composant</span><span class="sxs-lookup"><span data-stu-id="5afe4-110">Component</span></span>|<span data-ttu-id="5afe4-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="5afe4-111">SQLEngine</span></span>|  
|<span data-ttu-id="5afe4-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="5afe4-112">Symbolic Name</span></span>|<span data-ttu-id="5afe4-113">USEPLAN_ERR_NO_DB</span><span class="sxs-lookup"><span data-stu-id="5afe4-113">USEPLAN_ERR_NO_DB</span></span>|  
|<span data-ttu-id="5afe4-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="5afe4-114">Message Text</span></span>|<span data-ttu-id="5afe4-115">La base de données '%.\*ls' spécifiée dans l'indicateur USE PLAN n'existe pas.</span><span class="sxs-lookup"><span data-stu-id="5afe4-115">Database '%.\*ls', specified in the USE PLAN hint, does not exist.</span></span> <span data-ttu-id="5afe4-116">Indiquez une base de données existante.</span><span class="sxs-lookup"><span data-stu-id="5afe4-116">Specify an existing database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5afe4-117">Explication</span><span class="sxs-lookup"><span data-stu-id="5afe4-117">Explanation</span></span>  
 <span data-ttu-id="5afe4-118">Une base de données spécifiée dans l'indicateur USE PLAN n'existe pas.</span><span class="sxs-lookup"><span data-stu-id="5afe4-118">A database that is specified in the USE PLAN hint does not exist.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5afe4-119">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="5afe4-119">User Action</span></span>  
 <span data-ttu-id="5afe4-120">Veillez à ce que toutes les bases de données spécifiées dans l'indicateur USE PLAN existent.</span><span class="sxs-lookup"><span data-stu-id="5afe4-120">Ensure all databases that are specified in the USE PLAN hint exist.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5afe4-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5afe4-121">See Also</span></span>  
 <span data-ttu-id="5afe4-122">[Indicateurs de requête &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query) </span><span class="sxs-lookup"><span data-stu-id="5afe4-122">[Query Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query) </span></span>  
 [<span data-ttu-id="5afe4-123">Repères de plan</span><span class="sxs-lookup"><span data-stu-id="5afe4-123">Plan Guides</span></span>](../performance/plan-guides.md)  
  
  
