---
title: Boîte de dialogue source de partition (Analysis Services-données multidimensionnelles) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.partitionsourcedialog.f1
ms.assetid: c414dabe-9bad-49b7-9a3c-dfca87fef92b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6732e8f00dc0d01e0d3b708794a1d9c497ae4cf5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694747"
---
# <a name="partition-source-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="b3bf6-102">Boîte de dialogue Source de partition (Analysis Services - Données multidimensionnelles)</span><span class="sxs-lookup"><span data-stu-id="b3bf6-102">Partition Source Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="b3bf6-103">Utilisez la boîte de dialogue **Source de partition** dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] pour définir la source des données de table de faits d'une partition.</span><span class="sxs-lookup"><span data-stu-id="b3bf6-103">Use the **Partition Source** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to specify the source of fact table data for a partition.</span></span> <span data-ttu-id="b3bf6-104">Pour afficher la boîte de dialogue **Source de partition** :</span><span class="sxs-lookup"><span data-stu-id="b3bf6-104">You can display the **Partition Source** dialog box by:</span></span>  
  
-   <span data-ttu-id="b3bf6-105">cliquez sur le bouton **...** dans une cellule de la grille **Partitions** d'un groupe de mesures sélectionné dans le volet **Groupes de mesures** de l'onglet **Partitions** dans le Concepteur de cube ;</span><span class="sxs-lookup"><span data-stu-id="b3bf6-105">Clicking the **...** button on a cell from the **Partitions** grid of a selected measure group in the **Measure Groups** pane on the **Partitions** tab in Cube Designer.</span></span>  
  
-   <span data-ttu-id="b3bf6-106">cliquez sur le bouton **...** de la valeur de la propriété **Source** ou d'un objet **Partition** dans la fenêtre **Propriétés** de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b3bf6-106">Clicking the **...** button on the **Source** property value of a **Partition** object in the **Properties** window in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="b3bf6-107">Options</span><span class="sxs-lookup"><span data-stu-id="b3bf6-107">Options</span></span>  
  
|<span data-ttu-id="b3bf6-108">Option</span><span class="sxs-lookup"><span data-stu-id="b3bf6-108">Option</span></span>|<span data-ttu-id="b3bf6-109">Définition</span><span class="sxs-lookup"><span data-stu-id="b3bf6-109">Definition</span></span>|  
|------------|----------------|  
|<span data-ttu-id="b3bf6-110">**Type de liaison**</span><span class="sxs-lookup"><span data-stu-id="b3bf6-110">**Binding type**</span></span>|<span data-ttu-id="b3bf6-111">Sélectionnez le type de liaison à utiliser pour la source de la partition spécifiée.</span><span class="sxs-lookup"><span data-stu-id="b3bf6-111">Select the binding type to use for the source of the specified partition.</span></span> <span data-ttu-id="b3bf6-112">Les options suivantes sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="b3bf6-112">The following options are available:</span></span><br /><br /> <span data-ttu-id="b3bf6-113">**Liaison de table**: sélectionnez cette option pour afficher le volet Détails de la **liaison de table** et indiquez que la partition est liée au contenu d’une table dans une source de données ou une vue de source de données.</span><span class="sxs-lookup"><span data-stu-id="b3bf6-113">**Table binding**: Select to display the **Table Binding Detail** pane and indicate that the partition is bound to the contents of a table in a data source or data source view.</span></span> <span data-ttu-id="b3bf6-114">Pour plus d’informations sur le volet **Détails de la liaison de table**, consultez [Détails de la liaison de table &#40;boîte de dialogue Source de partition&#41; &#40;Analysis Services – Données multidimensionnelles&#41;](table-binding-partition-source-dialog-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="b3bf6-114">For more information about the **Table Binding Detail** pane, see [Table Binding Detail &#40;Partition Source Dialog Box&#41; &#40;Analysis Services - Multidimensional Data&#41;](table-binding-partition-source-dialog-analysis-services-multidimensional-data.md).</span></span><br /><br /> <span data-ttu-id="b3bf6-115">**Détail**: sélectionnez cette option pour afficher le volet Détails de la **liaison de requête** et indiquez que la partition est liée au contenu d’une requête exécutée sur une source de données.</span><span class="sxs-lookup"><span data-stu-id="b3bf6-115">**Detail**: Select to display the **Query Binding Detail** pane and indicate that the partition is bound to the contents of a query executed on a data source.</span></span> <span data-ttu-id="b3bf6-116">Pour plus d’informations sur le volet **Détails de la liaison de requête**, consultez [Détails de la liaison de requête &#40;boîte de dialogue Source de partition&#41; &#40;Analysis Services – Données multidimensionnelles&#41;](query-binding-partition-source-dialog-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="b3bf6-116">For more information about the **Query Binding Detail** pane, see [Query Binding Detail &#40;Partition Source Dialog Box&#41; &#40;Analysis Services - Multidimensional Data&#41;](query-binding-partition-source-dialog-analysis-services-multidimensional-data.md).</span></span>|  
|<span data-ttu-id="b3bf6-117">**Détail**</span><span class="sxs-lookup"><span data-stu-id="b3bf6-117">**Detail**</span></span>|<span data-ttu-id="b3bf6-118">Affiche la boîte de dialogue **Détails de la liaison de table** ou **Détails de la liaison de requête** en fonction de la valeur de l'option **Type de liaison** .</span><span class="sxs-lookup"><span data-stu-id="b3bf6-118">Displays either the **Table Binding Detail** dialog box or the **Query Binding Detail** dialog box, depending on the value of the **Binding type** option.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b3bf6-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b3bf6-119">See Also</span></span>  
 <span data-ttu-id="b3bf6-120">[Partitions &#40;concepteur de cube&#41; &#40;Analysis Services-données multidimensionnelles&#41;](partitions-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="b3bf6-120">[Partitions &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](partitions-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="b3bf6-121">Analysis Services les concepteurs et les boîtes de dialogue &#40;les données multidimensionnelles&#41;</span><span class="sxs-lookup"><span data-stu-id="b3bf6-121">Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;</span></span>](analysis-services-designers-and-dialog-boxes-multidimensional-data.md)  
  
  
