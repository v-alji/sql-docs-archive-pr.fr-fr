---
title: Supprimer des relations (SSAS tabulaire) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d40e3f05-54e8-4c4b-807a-0b06f446079b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3c63324918eb6919ce0abd65b5ee0765f9d7243b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696204"
---
# <a name="delete-relationships-ssas-tabular"></a><span data-ttu-id="b084e-102">Supprimer des relations (SSAS Tabulaire)</span><span class="sxs-lookup"><span data-stu-id="b084e-102">Delete Relationships (SSAS Tabular)</span></span>
  <span data-ttu-id="b084e-103">Vous pouvez supprimer des relations existantes à l'aide du générateur de modèles dans la vue de diagramme ou à l'aide de la boîte de dialogue Gérer les relations.</span><span class="sxs-lookup"><span data-stu-id="b084e-103">You can delete existing relationships by using the model designer in Diagram View or by using the Manage Relationships dialog box.</span></span> <span data-ttu-id="b084e-104">Pour plus d’informations sur la façon dont les relations sont utilisées dans les modèles tabulaires, consultez [Relations &#40;SSAS Tabulaire&#41;](relationships-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="b084e-104">For information about how relationships are used in tabular models, see [Relationships &#40;SSAS Tabular&#41;](relationships-ssas-tabular.md).</span></span>  
  
## <a name="considerations-for-deleting-relationships"></a><span data-ttu-id="b084e-105">Considérations à prendre en compte pour la suppression de relations</span><span class="sxs-lookup"><span data-stu-id="b084e-105">Considerations for Deleting Relationships</span></span>  
 <span data-ttu-id="b084e-106">Gardez à l'esprit les points suivants lorsque vous décidez de supprimer ou non une relation :</span><span class="sxs-lookup"><span data-stu-id="b084e-106">Keep the following issues in mind when deciding whether to delete a relationship:</span></span>  
  
-   <span data-ttu-id="b084e-107">Il n'existe aucune méthode permettant d'annuler la suppression d'une relation.</span><span class="sxs-lookup"><span data-stu-id="b084e-107">There is no way to undo the deletion of a relationship.</span></span> <span data-ttu-id="b084e-108">Vous pouvez recréer la relation, mais cette opération requiert le recalcul complet des formules dans le modèle.</span><span class="sxs-lookup"><span data-stu-id="b084e-108">You can re-create the relationship, but this action requires a complete recalculation of formulas in the model.</span></span> <span data-ttu-id="b084e-109">Par conséquent, effectuez toujours des vérifications avant de supprimer une relation utilisée dans des formules.</span><span class="sxs-lookup"><span data-stu-id="b084e-109">Therefore, always check first before deleting a relationship that is used in formulas.</span></span>  
  
-   <span data-ttu-id="b084e-110">La suppression d'une relation entre deux tables peut provoquer des erreurs dans les formules qui référencent ces tables.</span><span class="sxs-lookup"><span data-stu-id="b084e-110">Deleting a relationship between two tables can cause errors in formulas that reference these tables.</span></span>  
  
-   <span data-ttu-id="b084e-111">La fonction DAX (Data Analysis Expression) RELATED utilise les relations entre des tables pour rechercher des valeurs associées dans une autre table.</span><span class="sxs-lookup"><span data-stu-id="b084e-111">The Data Analysis Expression (DAX) RELATED function uses the relationships between tables to look up related values in another table.</span></span> <span data-ttu-id="b084e-112">Elle génèrera des résultats différents après la suppression de la relation.</span><span class="sxs-lookup"><span data-stu-id="b084e-112">It will return different results after the relationship is deleted.</span></span> <span data-ttu-id="b084e-113">Pour plus d'informations, consultez la fonction RELATED (DAX).</span><span class="sxs-lookup"><span data-stu-id="b084e-113">For more information, see the RELATED Function (DAX).</span></span>  
  
-   <span data-ttu-id="b084e-114">Outre la modification des résultats des tableaux croisés dynamiques et des formules, la création et la suppression de relations entraînent le recalcul du classeur, ce qui peut prendre du temps.</span><span class="sxs-lookup"><span data-stu-id="b084e-114">In addition to changing PivotTable and formula results, both the creation and deletion of relationships will cause the workbook to be recalculated, which can take some time.</span></span>  
  
## <a name="delete-relationships"></a><span data-ttu-id="b084e-115">Supprimer des relations</span><span class="sxs-lookup"><span data-stu-id="b084e-115">Delete Relationships</span></span>  
  
#### <a name="to-delete-a-relationship-by-using-diagram-view"></a><span data-ttu-id="b084e-116">Pour supprimer une relation à l'aide de la vue de diagramme</span><span class="sxs-lookup"><span data-stu-id="b084e-116">To delete a relationship by using Diagram View</span></span>  
  
1.  <span data-ttu-id="b084e-117">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], cliquez sur le menu **Modèle** , puis pointez sur **Vue du modèle**, et enfin sur **Vue de diagramme**.</span><span class="sxs-lookup"><span data-stu-id="b084e-117">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], click the **Model** menu, then point to **Model View**, and then click **Diagram View**.</span></span>  
  
2.  <span data-ttu-id="b084e-118">Cliquez avec le bouton droit sur une ligne de relation entre deux tables, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="b084e-118">Right-click a relationship line between two tables, and then click **Delete**.</span></span>  
  
#### <a name="to-delete-a-relationship-by-using-the-manage-relationships-dialog-box"></a><span data-ttu-id="b084e-119">Pour supprimer une relation à l'aide de la boîte de dialogue Gérer les relations.</span><span class="sxs-lookup"><span data-stu-id="b084e-119">To delete a relationship by using the Manage Relationships dialog box</span></span>  
  
1.  <span data-ttu-id="b084e-120">Dans [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], cliquez sur le menu **Table** , puis sur **Gérer les relations**.</span><span class="sxs-lookup"><span data-stu-id="b084e-120">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], click the **Table** menu, and then click **Manage Relationships**.</span></span>  
  
2.  <span data-ttu-id="b084e-121">Dans la boîte de dialogue **Gérer les relations** , sélectionnez une ou plusieurs relations dans la liste.</span><span class="sxs-lookup"><span data-stu-id="b084e-121">In the **Manage Relationships** dialog box, select one or more relationships from the list.</span></span>  
  
     <span data-ttu-id="b084e-122">Pour sélectionner plusieurs relations, maintenez la touche Ctrl enfoncée pendant que vous cliquez sur chaque relation.</span><span class="sxs-lookup"><span data-stu-id="b084e-122">To select multiple relationships, hold down CTRL while you click each relationship.</span></span>  
  
3.  <span data-ttu-id="b084e-123">Cliquez sur **Supprimer la relation**.</span><span class="sxs-lookup"><span data-stu-id="b084e-123">Click **Delete Relationship**.</span></span>  
  
4.  <span data-ttu-id="b084e-124">Dans la boîte de dialogue **Gérer les relations** , cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="b084e-124">In the **Manage Relationships** dialog box, click **Close**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b084e-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b084e-125">See Also</span></span>  
 <span data-ttu-id="b084e-126">[Relations &#40;&#41;tabulaires SSAS](relationships-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="b084e-126">[Relationships &#40;SSAS Tabular&#41;](relationships-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="b084e-127">Créer une relation entre deux tables &#40;SSAS Tabulaire&#41;</span><span class="sxs-lookup"><span data-stu-id="b084e-127">Create a Relationship Between Two Tables &#40;SSAS Tabular&#41;</span></span>](create-a-relationship-between-two-tables-ssas-tabular.md)  
  
  
