---
title: Supprimer une vue de source de données (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- deleting data source views
- data source views [Analysis Services], deleting
- removing data source views
ms.assetid: ae3f5ca0-ecbf-4b52-8386-eb457719d854
author: minewiskan
ms.author: owend
ms.openlocfilehash: 24b587e8d8961161ea803915c31d117c11f7cf2f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614205"
---
# <a name="delete-a-data-source-view-analysis-services"></a><span data-ttu-id="1275a-102">Supprimer une vue de source de données (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="1275a-102">Delete a Data Source View (Analysis Services)</span></span>
  <span data-ttu-id="1275a-103">Si vous n’utilisez plus de vue de source de données (DSV) dans un projet OLAP, vous pouvez la supprimer du projet dans [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1275a-103">If you are no longer using a data source view (DSV) in an OLAP project, you can delete it from the project in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="1275a-104">La suppression d'une vue DSV est définitive.</span><span class="sxs-lookup"><span data-stu-id="1275a-104">Deleting a DSV is permanent.</span></span> <span data-ttu-id="1275a-105">Vous ne pouvez pas restaurer une vue DSV supprimée dans un projet ou une base de données [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1275a-105">You cannot restore a deleted DSV to a [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project or database.</span></span>  
  
 <span data-ttu-id="1275a-106">Les vues de source de données (DSV) dont dépendent d’autres objets ne peuvent pas être supprimées d’une base de données [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ouverte par [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] en mode en ligne.</span><span class="sxs-lookup"><span data-stu-id="1275a-106">DSVs that other objects depend on cannot be deleted from an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database opened by [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] in online mode.</span></span> <span data-ttu-id="1275a-107">Pour supprimer une vue DSV d'un projet qui est connecté à une base de données s'exécutant sur un serveur, vous devez d'abord supprimer tous les objets de la base de données [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] qui dépendent de cette vue DSV avant de supprimer la vue DSV elle-même.</span><span class="sxs-lookup"><span data-stu-id="1275a-107">To delete a DSV from a project that is connected o a database running on a server, you must first delete all objects in the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database that depend on that DSV before deleting the DSV itself.</span></span>  
  
 <span data-ttu-id="1275a-108">La suppression d'une vue DSV invalidera d'autres objets [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] qui dépendent d'elle ; par conséquent, avant de supprimer la vue DSV, vous verrez la liste des objets qui deviendront non valides une fois la vue DSV supprimée.</span><span class="sxs-lookup"><span data-stu-id="1275a-108">Deleting a DSV will invalidate other [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects that depend on it, so before you delete the DSV, you will see the list of objects that will become invalid once the DSV is removed.</span></span> <span data-ttu-id="1275a-109">Examinez cette liste avec soin pour vous assurer qu'elle n'inclut pas les objets que vous vous attendez toujours à utiliser.</span><span class="sxs-lookup"><span data-stu-id="1275a-109">Review this list carefully to be sure that it does not include objects you still expect to use.</span></span>  
  
 <span data-ttu-id="1275a-110">![Supprimer des objets (boîte de dialogue)](../media/ssas-olapdsv-deleteobjects.gif "Supprimer des objets (boîte de dialogue)")</span><span class="sxs-lookup"><span data-stu-id="1275a-110">![Delete Objects dialog box](../media/ssas-olapdsv-deleteobjects.gif "Delete Objects dialog box")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1275a-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1275a-111">See Also</span></span>  
 <span data-ttu-id="1275a-112">[Vues de sources de données dans les modèles multidimensionnels](data-source-views-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="1275a-112">[Data Source Views in Multidimensional Models](data-source-views-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="1275a-113">Modifier les propriétés d’une vue de source de données &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="1275a-113">Change Properties in a Data Source View &#40;Analysis Services&#41;</span></span>](change-properties-in-a-data-source-view-analysis-services.md)  
  
  
