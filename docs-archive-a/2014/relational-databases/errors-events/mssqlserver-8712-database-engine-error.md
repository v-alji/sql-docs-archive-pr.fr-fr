---
title: MSSQLSERVER_8712 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8712 (Database Engine error)
ms.assetid: 292fb3bc-062e-41e4-a566-b5d3d0b21977
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9285d4846cac5af2dd6e87ab55d5fd0610586d07
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615158"
---
# <a name="mssqlserver_8712"></a><span data-ttu-id="47b36-102">MSSQLSERVER_8712</span><span class="sxs-lookup"><span data-stu-id="47b36-102">MSSQLSERVER_8712</span></span>
    
## <a name="details"></a><span data-ttu-id="47b36-103">Détails</span><span class="sxs-lookup"><span data-stu-id="47b36-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="47b36-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="47b36-104">Product Name</span></span>|<span data-ttu-id="47b36-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="47b36-105">SQL Server</span></span>|  
|<span data-ttu-id="47b36-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="47b36-106">Event ID</span></span>|<span data-ttu-id="47b36-107">8712</span><span class="sxs-lookup"><span data-stu-id="47b36-107">8712</span></span>|  
|<span data-ttu-id="47b36-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="47b36-108">Event Source</span></span>|<span data-ttu-id="47b36-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="47b36-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="47b36-110">Composant</span><span class="sxs-lookup"><span data-stu-id="47b36-110">Component</span></span>|<span data-ttu-id="47b36-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="47b36-111">SQLEngine</span></span>|  
|<span data-ttu-id="47b36-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="47b36-112">Symbolic Name</span></span>|<span data-ttu-id="47b36-113">USEPLAN_ERR_NO_INDEX</span><span class="sxs-lookup"><span data-stu-id="47b36-113">USEPLAN_ERR_NO_INDEX</span></span>|  
|<span data-ttu-id="47b36-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="47b36-114">Message Text</span></span>|<span data-ttu-id="47b36-115">L'index '%.\*ls' spécifié dans l'indicateur USE PLAN n'existe pas.</span><span class="sxs-lookup"><span data-stu-id="47b36-115">Index '%.\*ls', specified in the USE PLAN hint, does not exist.</span></span> <span data-ttu-id="47b36-116">Indiquez un index existant ou créez-en un avec le nom spécifié.</span><span class="sxs-lookup"><span data-stu-id="47b36-116">Specify an existing index, or create an index with the specified name.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="47b36-117">Explication</span><span class="sxs-lookup"><span data-stu-id="47b36-117">Explanation</span></span>  
 <span data-ttu-id="47b36-118">Un index spécifié dans l'indicateur USE PLAN n'existe pas.</span><span class="sxs-lookup"><span data-stu-id="47b36-118">An index that is specified in the USE PLAN hint does not exist.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="47b36-119">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="47b36-119">User Action</span></span>  
 <span data-ttu-id="47b36-120">Veillez à ce que tous les index spécifiés dans l'indicateur USE PLAN existent.</span><span class="sxs-lookup"><span data-stu-id="47b36-120">Ensure all indexes that are specified in the USE PLAN hint exist.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47b36-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="47b36-121">See Also</span></span>  
 <span data-ttu-id="47b36-122">[Indicateurs de requête &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query) </span><span class="sxs-lookup"><span data-stu-id="47b36-122">[Query Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query) </span></span>  
 [<span data-ttu-id="47b36-123">Repères de plan</span><span class="sxs-lookup"><span data-stu-id="47b36-123">Plan Guides</span></span>](../performance/plan-guides.md)  
  
  
