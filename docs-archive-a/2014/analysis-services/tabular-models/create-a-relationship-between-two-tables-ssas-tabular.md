---
title: Créer une relation entre deux tables (SSAS tabulaire) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.managereldb.f1
- sql12.asvs.bidtoolset.createrelatdb.f1
ms.assetid: 052d77b7-7922-408a-a200-786016ee4d15
author: minewiskan
ms.author: owend
ms.openlocfilehash: 33481b8d50be9ca632bcade932d51df86c1910a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603667"
---
# <a name="create-a-relationship-between-two-tables-ssas-tabular"></a><span data-ttu-id="85971-102">Créer une relation entre deux tables (SSAS Tabulaire)</span><span class="sxs-lookup"><span data-stu-id="85971-102">Create a Relationship Between Two Tables (SSAS Tabular)</span></span>
  <span data-ttu-id="85971-103">S'il n'existe pas de relations entre les tables de votre source de données ou si vous ajoutez de nouvelles tables, vous pouvez utiliser les outils du générateur de modèles pour créer des relations.</span><span class="sxs-lookup"><span data-stu-id="85971-103">If the tables in your data source do not have existing relationships, or if you add new tables, you can use the tools in the model designer to create new relationships.</span></span> <span data-ttu-id="85971-104">Pour plus d’informations sur la façon dont les relations sont utilisées dans les modèles tabulaires, consultez [Relations &#40;SSAS Tabulaire&#41;](relationships-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="85971-104">For information about how relationships are used in tabular models, see [Relationships &#40;SSAS Tabular&#41;](relationships-ssas-tabular.md).</span></span>  
  
## <a name="create-a-relationship-between-two-tables"></a><span data-ttu-id="85971-105">Créer une relation entre deux tables</span><span class="sxs-lookup"><span data-stu-id="85971-105">Create a relationship between two tables</span></span>  
  
#### <a name="to-create-a-relationship-between-two-tables-in-diagram-view-click-and-drag"></a><span data-ttu-id="85971-106">Pour créer une relation entre deux tables dans la vue de diagramme (clic et glisser-déplacer)</span><span class="sxs-lookup"><span data-stu-id="85971-106">To create a relationship between two tables in Diagram View (Click and drag)</span></span>  
  
1.  <span data-ttu-id="85971-107">Dans [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], cliquez sur le menu **Modèle** , puis sur **Vue du modèle**, et enfin sur **Vue de diagramme**.</span><span class="sxs-lookup"><span data-stu-id="85971-107">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], click the **Model** menu, then click **Model View**, and then click **Diagram View**.</span></span>  
  
2.  <span data-ttu-id="85971-108">Cliquez (et maintenez le bouton de la souris enfoncé) sur une colonne dans une table, faites glisser le curseur vers une colonne de recherche associée dans une table de recherche associée, puis relâchez.</span><span class="sxs-lookup"><span data-stu-id="85971-108">Click (and hold) on a column within a table, then drag the cursor to a related lookup column in a related lookup table, and then release.</span></span> <span data-ttu-id="85971-109">La relation est automatiquement créée dans l'ordre correct.</span><span class="sxs-lookup"><span data-stu-id="85971-109">The relationship will be created in the correct order automatically.</span></span>  
  
#### <a name="to-create-a-relationship-between-two-tables-in-diagram-view-right-click"></a><span data-ttu-id="85971-110">Pour créer une relation entre deux tables dans la vue de diagramme (clic droit)</span><span class="sxs-lookup"><span data-stu-id="85971-110">To create a relationship between two tables in Diagram View (Right-click)</span></span>  
  
1.  <span data-ttu-id="85971-111">Dans [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], cliquez sur le menu **Modèle** , puis sur **Vue du modèle**, et enfin sur **Vue de diagramme**.</span><span class="sxs-lookup"><span data-stu-id="85971-111">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], click the **Model** menu, then click **Model View**, and then click **Diagram View**.</span></span>  
  
2.  <span data-ttu-id="85971-112">Cliquez avec le bouton droit sur un en-tête ou une colonne de table, puis sélectionnez **Créer une relation**.</span><span class="sxs-lookup"><span data-stu-id="85971-112">Right-click a table heading or column, and then click **Create Relationship**.</span></span>  
  
3.  <span data-ttu-id="85971-113">Dans la boîte de dialogue **Créer une relation** , pour **Table**, cliquez sur la touche Flèche bas et sélectionnez une table dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="85971-113">In the **Create Relationship** dialog box, click the down arrow for **Table**, and select a table from the dropdown list.</span></span>  
  
     <span data-ttu-id="85971-114">Dans une relation « un à plusieurs », cette table doit être du côté « plusieurs ».</span><span class="sxs-lookup"><span data-stu-id="85971-114">In a "one-to-many" relationship, this table should be on the "many" side.</span></span>  
  
4.  <span data-ttu-id="85971-115">Pour **Colonne**, sélectionnez la colonne qui contient les données mises en rapport avec **Colonne de recherche associée**.</span><span class="sxs-lookup"><span data-stu-id="85971-115">For **Column**, select the column that contains the data that is related to **Related Lookup Column**.</span></span> <span data-ttu-id="85971-116">La colonne est sélectionnée automatiquement si vous avez cliqué avec le bouton droit sur une colonne pour créer la relation.</span><span class="sxs-lookup"><span data-stu-id="85971-116">The column is automatically selected if you right-clicked on a column to create the relationship.</span></span>  
  
5.  <span data-ttu-id="85971-117">Pour **Table de recherche associée**, sélectionnez une table qui comporte au moins une colonne de données mise en rapport avec la table que vous venez de sélectionner pour **Table**.</span><span class="sxs-lookup"><span data-stu-id="85971-117">For **Related Lookup Table**, select a table that has at least one column of data that is related to the table you just selected for **Table**.</span></span>  
  
     <span data-ttu-id="85971-118">Dans une relation « un-à-plusieurs », cette table doit être sur côté « un », c'est-à-dire que les valeurs dans la colonne sélectionnée ne contiennent pas de doublons.</span><span class="sxs-lookup"><span data-stu-id="85971-118">In a "one-to-many" relationship, this table should be on the "one" side, meaning that the values in the selected column do not contain duplicates.</span></span> <span data-ttu-id="85971-119">Si vous essayez de créer la relation dans l’ordre incorrect (un-à-plusieurs au lieu de plusieurs-à-un), une icône apparaît en regard du champ **Colonne de recherche associée** .</span><span class="sxs-lookup"><span data-stu-id="85971-119">If you attempt to create the relationship in the wrong order (one-to-many instead of many-to-one), an icon will appear next to the **Related Lookup Column** field.</span></span> <span data-ttu-id="85971-120">Inversez l'ordre pour créer une relation valide.</span><span class="sxs-lookup"><span data-stu-id="85971-120">Reverse the order to create a valid relationship.</span></span>  
  
6.  <span data-ttu-id="85971-121">Pour **Colonne de recherche associée**, sélectionnez une colonne qui comporte des valeurs uniques qui correspondent aux valeurs dans la colonne que vous avez sélectionnée pour **Colonne**.</span><span class="sxs-lookup"><span data-stu-id="85971-121">For **Related Lookup Column**, select a column that has unique values that match the values in the column you selected for **Column**.</span></span>  
  
7.  <span data-ttu-id="85971-122">Cliquez sur **Créer**.</span><span class="sxs-lookup"><span data-stu-id="85971-122">Click **Create**.</span></span>  
  
#### <a name="to-create-a-relationship-between-two-tables-in-data-view"></a><span data-ttu-id="85971-123">Pour créer une relation entre deux tables dans la vue de données</span><span class="sxs-lookup"><span data-stu-id="85971-123">To create a relationship between two tables in Data View</span></span>  
  
1.  <span data-ttu-id="85971-124">Dans [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], cliquez sur le menu **Table** , puis sur **Créer des relations**.</span><span class="sxs-lookup"><span data-stu-id="85971-124">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], click the **Table** menu, and then click **Create Relationships**.</span></span>  
  
2.  <span data-ttu-id="85971-125">Dans la boîte de dialogue **Créer une relation** , pour **Table**, cliquez sur la touche Flèche bas et sélectionnez une table dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="85971-125">In the **Create Relationship** dialog box, click the down arrow for **Table**, and select a table from the dropdown list.</span></span>  
  
     <span data-ttu-id="85971-126">Dans une relation « un à plusieurs », cette table doit être du côté « plusieurs ».</span><span class="sxs-lookup"><span data-stu-id="85971-126">In a "one-to-many" relationship, this table should be on the "many" side.</span></span>  
  
3.  <span data-ttu-id="85971-127">Pour **Colonne**, sélectionnez la colonne qui contient les données mises en rapport avec **Colonne de recherche associée**.</span><span class="sxs-lookup"><span data-stu-id="85971-127">For **Column**, select the column that contains the data that is related to **Related Lookup Column**.</span></span>  
  
4.  <span data-ttu-id="85971-128">Pour **Table de recherche associée**, sélectionnez une table qui comporte au moins une colonne de données mise en rapport avec la table que vous venez de sélectionner pour **Table**.</span><span class="sxs-lookup"><span data-stu-id="85971-128">For **Related Lookup Table**, select a table that has at least one column of data that is related to the table you just selected for **Table**.</span></span>  
  
     <span data-ttu-id="85971-129">Dans une relation « un-à-plusieurs », cette table doit être sur côté « un », c'est-à-dire que les valeurs dans la colonne sélectionnée ne contiennent pas de doublons.</span><span class="sxs-lookup"><span data-stu-id="85971-129">In a "one-to-many" relationship, this table should be on the "one" side, meaning that the values in the selected column do not contain duplicates.</span></span> <span data-ttu-id="85971-130">Si vous essayez de créer la relation dans l’ordre incorrect (un-à-plusieurs au lieu de plusieurs-à-un), une icône apparaît en regard du champ **Colonne de recherche associée** .</span><span class="sxs-lookup"><span data-stu-id="85971-130">If you attempt to create the relationship in the wrong order (one-to-many instead of many-to-one), an icon will appear next to the **Related Lookup Column** field.</span></span> <span data-ttu-id="85971-131">Inversez l'ordre pour créer une relation valide.</span><span class="sxs-lookup"><span data-stu-id="85971-131">Reverse the order to create a valid relationship.</span></span>  
  
5.  <span data-ttu-id="85971-132">Pour **Colonne de recherche associée**, sélectionnez une colonne qui comporte des valeurs uniques qui correspondent aux valeurs dans la colonne que vous avez sélectionnée pour **Colonne**.</span><span class="sxs-lookup"><span data-stu-id="85971-132">For **Related Lookup Column**, select a column that has unique values that match the values in the column you selected for **Column**.</span></span>  
  
6.  <span data-ttu-id="85971-133">Cliquez sur **Créer**.</span><span class="sxs-lookup"><span data-stu-id="85971-133">Click **Create**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85971-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="85971-134">See Also</span></span>  
 <span data-ttu-id="85971-135">[Supprimer des relations &#40;&#41;tabulaire SSAS](delete-relationships-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="85971-135">[Delete Relationships &#40;SSAS Tabular&#41;](delete-relationships-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="85971-136">Relations &#40;SSAS Tabulaire&#41;</span><span class="sxs-lookup"><span data-stu-id="85971-136">Relationships &#40;SSAS Tabular&#41;</span></span>](relationships-ssas-tabular.md)  
  
  
