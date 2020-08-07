---
title: MSSQLSERVER_8649 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8649 (Database Engine error)
ms.assetid: 992dbc74-7c3a-498b-9f1b-b28387640677
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b39ed0d8ffe5f7f601b6cb1393596d0d6546e557
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611808"
---
# <a name="mssqlserver_8649"></a><span data-ttu-id="0a352-102">MSSQLSERVER_8649</span><span class="sxs-lookup"><span data-stu-id="0a352-102">MSSQLSERVER_8649</span></span>
    
## <a name="details"></a><span data-ttu-id="0a352-103">Détails</span><span class="sxs-lookup"><span data-stu-id="0a352-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0a352-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="0a352-104">Product Name</span></span>|<span data-ttu-id="0a352-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="0a352-105">SQL Server</span></span>|  
|<span data-ttu-id="0a352-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="0a352-106">Event ID</span></span>|<span data-ttu-id="0a352-107">8649</span><span class="sxs-lookup"><span data-stu-id="0a352-107">8649</span></span>|  
|<span data-ttu-id="0a352-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="0a352-108">Event Source</span></span>|<span data-ttu-id="0a352-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="0a352-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="0a352-110">Composant</span><span class="sxs-lookup"><span data-stu-id="0a352-110">Component</span></span>|<span data-ttu-id="0a352-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="0a352-111">SQLEngine</span></span>|  
|<span data-ttu-id="0a352-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="0a352-112">Symbolic Name</span></span>|<span data-ttu-id="0a352-113">COST_TOO_HIGH</span><span class="sxs-lookup"><span data-stu-id="0a352-113">COST_TOO_HIGH</span></span>|  
|<span data-ttu-id="0a352-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="0a352-114">Message Text</span></span>|<span data-ttu-id="0a352-115">La requête a été annulée parce que son coût estimé (%d) est supérieur au seuil configuré, %d.</span><span class="sxs-lookup"><span data-stu-id="0a352-115">The query has been canceled because the estimated cost of this query (%d) exceeds the configured threshold of %d.</span></span> <span data-ttu-id="0a352-116">Contactez l'administrateur système.</span><span class="sxs-lookup"><span data-stu-id="0a352-116">Contact the system administrator.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0a352-117">Explication</span><span class="sxs-lookup"><span data-stu-id="0a352-117">Explanation</span></span>  
 <span data-ttu-id="0a352-118">La requête a été annulée parce que son coût estimé est supérieur au seuil configuré pour QUERY_GOVERNOR_COST_LIMIT.</span><span class="sxs-lookup"><span data-stu-id="0a352-118">The query was canceled because the estimated cost of this query exceeds the configured threshold set for the QUERY_GOVERNOR_COST_LIMIT.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0a352-119">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="0a352-119">User Action</span></span>  
 <span data-ttu-id="0a352-120">Spécifiez une valeur supérieure pour l'option QUERY_GOVERNOR_COST_LIMIT.</span><span class="sxs-lookup"><span data-stu-id="0a352-120">Set the QUERY_GOVERNOR_COST_LIMIT option to a higher value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a352-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0a352-121">See Also</span></span>  
 [<span data-ttu-id="0a352-122">SET QUERY_GOVERNOR_COST_LIMIT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0a352-122">SET QUERY_GOVERNOR_COST_LIMIT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/set-query-governor-cost-limit-transact-sql)  
  
  
