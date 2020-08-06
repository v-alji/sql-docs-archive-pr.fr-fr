---
title: MSSQLSERVER_41399 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41399 (Database Engine error)
ms.assetid: 5e5acb07-16ca-4329-8210-cd2bab0c904f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2e134cbc8b39a3c65d9c515183243f0b4caed434
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604023"
---
# <a name="mssqlserver_41399"></a><span data-ttu-id="cef96-102">MSSQLSERVER_41399</span><span class="sxs-lookup"><span data-stu-id="cef96-102">MSSQLSERVER_41399</span></span>
    
## <a name="details"></a><span data-ttu-id="cef96-103">Détails</span><span class="sxs-lookup"><span data-stu-id="cef96-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cef96-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="cef96-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="cef96-105">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="cef96-105">Event ID</span></span>|<span data-ttu-id="cef96-106">41399</span><span class="sxs-lookup"><span data-stu-id="cef96-106">41399</span></span>|  
|<span data-ttu-id="cef96-107">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="cef96-107">Event Source</span></span>|<span data-ttu-id="cef96-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="cef96-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="cef96-109">Composant</span><span class="sxs-lookup"><span data-stu-id="cef96-109">Component</span></span>|<span data-ttu-id="cef96-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="cef96-110">SQLEngine</span></span>|  
|<span data-ttu-id="cef96-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="cef96-111">Symbolic Name</span></span>|<span data-ttu-id="cef96-112">MAX_SORT_ROW_WIDTH_EXCEEDED</span><span class="sxs-lookup"><span data-stu-id="cef96-112">MAX_SORT_ROW_WIDTH_EXCEEDED</span></span>|  
|<span data-ttu-id="cef96-113">Texte du message</span><span class="sxs-lookup"><span data-stu-id="cef96-113">Message Text</span></span>|<span data-ttu-id="cef96-114">L'opération de tri est trop complexe.</span><span class="sxs-lookup"><span data-stu-id="cef96-114">The sort operation is too complex.</span></span> <span data-ttu-id="cef96-115">Consultez la documentation en ligne de SQL Server pour plus d'informations.</span><span class="sxs-lookup"><span data-stu-id="cef96-115">Consult SQL Server Books Online for more information.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="cef96-116">Explication</span><span class="sxs-lookup"><span data-stu-id="cef96-116">Explanation</span></span>  
 <span data-ttu-id="cef96-117">Le tri des résultats des opérations de jointure et d'agrégation augmente la complexité de l'opération de tri en accroissant la taille de la ligne dans le tampon de tri.</span><span class="sxs-lookup"><span data-stu-id="cef96-117">Sorting the result of join and aggregation operations increases the complexity of the sort operation by increasing the size of the row in the sort buffer.</span></span> <span data-ttu-id="cef96-118">Cette erreur indique que la taille de la ligne dépasse la taille maximale prise en charge par l'opérateur de tri dans des procédures stockées compilées en mode natif.</span><span class="sxs-lookup"><span data-stu-id="cef96-118">This error means that the size of the row is larger than the maximum size supported by the sort operator in natively compiled stored procedures.</span></span> <span data-ttu-id="cef96-119">Notez que la taille d'une ligne dans le tampon de tri est déterminée uniquement par le nombre de jointures et le nombre et le type de fonctions d'agrégation.</span><span class="sxs-lookup"><span data-stu-id="cef96-119">Note that the size of a row in the sort buffer is determined solely by the number of joins and the number and type of aggregate functions.</span></span> <span data-ttu-id="cef96-120">La taille des lignes dans les tables de base n'affecte pas la taille de la ligne dans le tampon.</span><span class="sxs-lookup"><span data-stu-id="cef96-120">The size of the rows in the base tables does not affect the size of the row in the buffer.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cef96-121">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="cef96-121">User Action</span></span>  
 <span data-ttu-id="cef96-122">Réduisez la complexité de la requête en supprimant des jointures ou des fonctions d'agrégation.</span><span class="sxs-lookup"><span data-stu-id="cef96-122">Decrease the complexity of the query by removing joins or aggregate functions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cef96-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cef96-123">See Also</span></span>  
 [<span data-ttu-id="cef96-124">OLTP en mémoire &#40;Optimisation en mémoire&#41;</span><span class="sxs-lookup"><span data-stu-id="cef96-124">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
