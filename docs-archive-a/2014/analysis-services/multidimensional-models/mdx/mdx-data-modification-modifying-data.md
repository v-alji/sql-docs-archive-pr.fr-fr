---
title: Modification des données (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- modifying data [MDX]
- Multidimensional Expressions [Analysis Services], data modifications
- MDX [Analysis Services], data modifications
- data modifications [MDX]
ms.assetid: 363b662c-b839-4971-bbd7-1842f73ce141
author: minewiskan
ms.author: owend
ms.openlocfilehash: 01df67471753922e3e7db39c56a9ed50aae900dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610879"
---
# <a name="modifying-data-mdx"></a><span data-ttu-id="26ea9-102">Modification de données (MDX)</span><span class="sxs-lookup"><span data-stu-id="26ea9-102">Modifying Data (MDX)</span></span>
  <span data-ttu-id="26ea9-103">Outre l’utilisation de la syntaxe MDX (Multidimensional Expressions) pour récupérer et gérer les données de dimensions et de cubes, vous pouvez utiliser MDX pour mettre à jour les données de la dimension ou du cube, ou encore pour procéder à leur *écriture différée* .</span><span class="sxs-lookup"><span data-stu-id="26ea9-103">Besides using Multidimensional Expressions (MDX) to retrieve and handle data from dimensions and cubes, you can use MDX to update or *writeback* dimension and cube data.</span></span> <span data-ttu-id="26ea9-104">Ces mises à jour peuvent être temporaires (comme pour l'analyse spéculative, du type « Que se passe-t-il si ») ou permanentes (comme lorsque des modifications doivent être apportées en fonction de l'analyse de données).</span><span class="sxs-lookup"><span data-stu-id="26ea9-104">These updates can be temporary, as with speculative, or "what if", analysis, or permanent, as when changes must occur based upon data analysis.</span></span>  
  
 <span data-ttu-id="26ea9-105">Les mises à jour de données se produisent au niveau de la dimension ou du cube :</span><span class="sxs-lookup"><span data-stu-id="26ea9-105">Updates to data can occur at the dimension or cube level:</span></span>  
  
 <span data-ttu-id="26ea9-106">**Écriture différée de dimensions**</span><span class="sxs-lookup"><span data-stu-id="26ea9-106">**Dimension writebacks**</span></span>  
 <span data-ttu-id="26ea9-107">L’instruction [ALTER CUBE Statement (MDX)](/sql/mdx/mdx-data-definition-alter-cube) permet de modifier les données d’une dimension activée en écriture, tandis que l’instruction [REFRESH CUBE Statement (MDX)](/sql/mdx/mdx-data-definition-refresh-cube) sert à illustrer les processus de suppression, création et mise à jour des valeurs d’attributs.</span><span class="sxs-lookup"><span data-stu-id="26ea9-107">You use the [ALTER CUBE Statement (MDX)](/sql/mdx/mdx-data-definition-alter-cube) statement to change a write-enabled dimension's data and the [REFRESH CUBE Statement (MDX)](/sql/mdx/mdx-data-definition-refresh-cube) to reflect the deletion, creation, and updating of attribute values.</span></span> <span data-ttu-id="26ea9-108">Il est également possible d'utiliser l'instruction ALTER CUBE pour effectuer des opérations complexes, notamment la suppression de l'intégralité d'une sous-arborescence dans une hiérarchie et la promotion des enfants d'un membre supprimé.</span><span class="sxs-lookup"><span data-stu-id="26ea9-108">You can also use the ALTER CUBE statement to perform complex operations, such as deleting a whole sub-tree in a hierarchy and promoting the children of a deleted member.</span></span>  
  
 <span data-ttu-id="26ea9-109">**Écriture différée de cubes**</span><span class="sxs-lookup"><span data-stu-id="26ea9-109">**Cube writebacks**</span></span>  
 <span data-ttu-id="26ea9-110">Pour effectuer des mises à jour d’un cube activé en écriture, vous devez utiliser l’instruction [UPDATE CUBE](/sql/mdx/mdx-data-manipulation-update-cube) .</span><span class="sxs-lookup"><span data-stu-id="26ea9-110">You use the [UPDATE CUBE](/sql/mdx/mdx-data-manipulation-update-cube) statement to make updates to a write-enabled cube.</span></span> <span data-ttu-id="26ea9-111">L’instruction UPDATE CUBE permet de mettre à jour un tuple avec une valeur spécifique.</span><span class="sxs-lookup"><span data-stu-id="26ea9-111">The UPDATE CUBE statement lets you update a tuple with a specific value.</span></span> <span data-ttu-id="26ea9-112">L’instruction [REFRESH CUBE (MDX)](/sql/mdx/mdx-data-definition-refresh-cube) permet d’actualiser les données d’une session client avec les données mises à jour du serveur.</span><span class="sxs-lookup"><span data-stu-id="26ea9-112">You use the [REFRESH CUBE Statement (MDX)](/sql/mdx/mdx-data-definition-refresh-cube) to refresh data in a client session with updated data from the server.</span></span>  
  
 <span data-ttu-id="26ea9-113">Pour plus d’informations, consultez [Utilisation de l’écriture différée de cubes à l’aide de &#40;MDX&#41;](mdx-data-modification-using-cube-writebacks.md).</span><span class="sxs-lookup"><span data-stu-id="26ea9-113">For more information, see [Using Cube Writebacks &#40;MDX&#41;](mdx-data-modification-using-cube-writebacks.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26ea9-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="26ea9-114">See Also</span></span>  
 [<span data-ttu-id="26ea9-115">Principes de base des requêtes MDX &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="26ea9-115">MDX Query Fundamentals &#40;Analysis Services&#41;</span></span>](mdx-query-fundamentals-analysis-services.md)  
  
  
