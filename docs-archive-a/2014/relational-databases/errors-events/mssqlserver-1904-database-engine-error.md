---
title: MSSQLSERVER_1904 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1904 (Database Engine error)
ms.assetid: 2a35d57d-74e2-45a2-8f67-3f2e51d69712
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 568cfe7499c041c2ee6a8ac3698b31698171bece
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604526"
---
# <a name="mssqlserver_1904"></a><span data-ttu-id="988a2-102">MSSQLSERVER_1904</span><span class="sxs-lookup"><span data-stu-id="988a2-102">MSSQLSERVER_1904</span></span>
    
## <a name="details"></a><span data-ttu-id="988a2-103">Détails</span><span class="sxs-lookup"><span data-stu-id="988a2-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="988a2-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="988a2-104">Product Name</span></span>|<span data-ttu-id="988a2-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="988a2-105">SQL Server</span></span>|  
|<span data-ttu-id="988a2-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="988a2-106">Event ID</span></span>|<span data-ttu-id="988a2-107">1904</span><span class="sxs-lookup"><span data-stu-id="988a2-107">1904</span></span>|  
|<span data-ttu-id="988a2-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="988a2-108">Event Source</span></span>|<span data-ttu-id="988a2-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="988a2-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="988a2-110">Composant</span><span class="sxs-lookup"><span data-stu-id="988a2-110">Component</span></span>|<span data-ttu-id="988a2-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="988a2-111">SQLEngine</span></span>|  
|<span data-ttu-id="988a2-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="988a2-112">Symbolic Name</span></span>|<span data-ttu-id="988a2-113">KEYCOUNT</span><span class="sxs-lookup"><span data-stu-id="988a2-113">KEYCOUNT</span></span>|  
|<span data-ttu-id="988a2-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="988a2-114">Message Text</span></span>|<span data-ttu-id="988a2-115">Le %S_MSG '%.\*ls' sur la table '%.\*ls' a %d noms de colonnes dans la liste de clés %S_MSG.</span><span class="sxs-lookup"><span data-stu-id="988a2-115">The %S_MSG '%.\*ls' on table '%.\*ls' has %d column names in %S_MSG key list.</span></span> <span data-ttu-id="988a2-116">La limite maximale pour la liste des colonnes de clés d'index ou de statistiques est %d.</span><span class="sxs-lookup"><span data-stu-id="988a2-116">The maximum limit for index or statistics key column list is %d.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="988a2-117">Explication</span><span class="sxs-lookup"><span data-stu-id="988a2-117">Explanation</span></span>  
 <span data-ttu-id="988a2-118">La liste des colonnes de clés pour l'index ou les statistiques spécifiés dépasse le nombre maximal autorisé de colonnes.</span><span class="sxs-lookup"><span data-stu-id="988a2-118">The key column list for the specified index or statistics exceeds the maximum number of columns allowed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="988a2-119">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="988a2-119">User Action</span></span>  
 <span data-ttu-id="988a2-120">Modifiez la liste des colonnes de clés de sorte qu'elle n'inclue pas plus de colonnes que le nombre maximal spécifié.</span><span class="sxs-lookup"><span data-stu-id="988a2-120">Modify the key column list to include no more than the specified maximum number of columns.</span></span>  
  
 <span data-ttu-id="988a2-121">Pour les index non cluster, pensez à utiliser la clause INCLUDE dans l'instruction CREATE INDEX pour ajouter des colonnes à l'index en tant que colonnes non clés.</span><span class="sxs-lookup"><span data-stu-id="988a2-121">For nonclustered indexes, consider using the INCLUDE clause in the CREATE INDEX statement to add columns to the index as nonkey columns.</span></span> <span data-ttu-id="988a2-122">Cette méthode évite de dépasser la limite actuelle de taille d'index fixée à un maximum de 16 colonnes clés.</span><span class="sxs-lookup"><span data-stu-id="988a2-122">This method avoids exceeding the current index size limitation of a maximum of 16 key columns.</span></span> <span data-ttu-id="988a2-123">Pour plus d’informations, consultez [Créer des index avec colonnes incluses](../indexes/create-indexes-with-included-columns.md).</span><span class="sxs-lookup"><span data-stu-id="988a2-123">For more information, see [Create Indexes with Included Columns](../indexes/create-indexes-with-included-columns.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="988a2-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="988a2-124">See Also</span></span>  
 <span data-ttu-id="988a2-125">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="988a2-125">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span></span>  
 [<span data-ttu-id="988a2-126">CREATE STATISTICS &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="988a2-126">CREATE STATISTICS &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-statistics-transact-sql)  
  
  
