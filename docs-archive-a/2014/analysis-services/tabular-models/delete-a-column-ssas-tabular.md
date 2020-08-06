---
title: Supprimer une colonne (SSAS tabulaire) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 703db83b-e554-450e-813e-23ad08c1cdad
author: minewiskan
ms.author: owend
ms.openlocfilehash: 06af0b7fd9879661db95bb2073cced545bb4eef5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610875"
---
# <a name="delete-a-column-ssas-tabular"></a><span data-ttu-id="b63a6-102">Supprimer une colonne (SSAS Tabulaire)</span><span class="sxs-lookup"><span data-stu-id="b63a6-102">Delete a Column (SSAS Tabular)</span></span>
  <span data-ttu-id="b63a6-103">Cette rubrique explique comment supprimer une colonne d'une table de modèle tabulaire.</span><span class="sxs-lookup"><span data-stu-id="b63a6-103">This topic describes how to delete a column from a tabular model table.</span></span>  
  
## <a name="delete-a-model-table-column"></a><span data-ttu-id="b63a6-104">Supprimer une colonne de table de modèle</span><span class="sxs-lookup"><span data-stu-id="b63a6-104">Delete a Model Table Column</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b63a6-105">La suppression d'une colonne d'une table de modèle ne supprime pas la colonne d'une définition de requête de partition.</span><span class="sxs-lookup"><span data-stu-id="b63a6-105">Deleting a column from a model table does not delete the column from a partition query definition.</span></span> <span data-ttu-id="b63a6-106">Si la colonne que vous supprimez fait partie d'une partition, vous devez supprimer manuellement la colonne de la définition de requête de partition.</span><span class="sxs-lookup"><span data-stu-id="b63a6-106">If the column you are deleting is part of a partition, you must manually delete the column from the partition query definition.</span></span> <span data-ttu-id="b63a6-107">Si vous ne supprimez pas la colonne de la définition de requête de partition, la colonne sera interrogée et des données retournées, mais elles ne seront pas ajoutées la table de modèle pendant le traitement des opérations.</span><span class="sxs-lookup"><span data-stu-id="b63a6-107">Failure to delete the column from the partition query definition will cause the column to be queried and data returned, but not populated to the model table, during processing operations.</span></span> <span data-ttu-id="b63a6-108">Pour plus d’informations, consultez [Partitions &#40;SSAS Tabulaire&#41;](partitions-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="b63a6-108">For more information, see [Partitions &#40;SSAS Tabular&#41;](partitions-ssas-tabular.md).</span></span>  
  
#### <a name="to-delete-a-model-table-column"></a><span data-ttu-id="b63a6-109">Pour supprimer une colonne de table de modèle</span><span class="sxs-lookup"><span data-stu-id="b63a6-109">To delete a model table column</span></span>  
  
-   <span data-ttu-id="b63a6-110">Dans le générateur de modèles, dans la table qui contient la colonne à supprimer, cliquez avec le bouton droit sur la colonne, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="b63a6-110">In the model designer, in the table that contains the column you want to delete, right-click on the column, and then click **Delete**.</span></span>  
  
#### <a name="to-delete-a-model-table-column-by-using-the-table-properties-dialog-box"></a><span data-ttu-id="b63a6-111">Pour supprimer une colonne de table de modèle à l'aide de la boîte de dialogue Propriétés de la table</span><span class="sxs-lookup"><span data-stu-id="b63a6-111">To delete a model table column by using the Table Properties dialog box</span></span>  
  
1.  <span data-ttu-id="b63a6-112">Dans le générateur de modèles, cliquez sur la table qui contient la colonne à supprimer, cliquez sur le menu **Table** , puis sur  **Propriétés de la table**.</span><span class="sxs-lookup"><span data-stu-id="b63a6-112">In the model designer, click on the table which contains the column you want to delete, then click the **Table** menu, and then click  **Table Properties**.</span></span>  
  
2.  <span data-ttu-id="b63a6-113">Dans **Origine des noms de colonnes**, sélectionnez **Modèle** (*pour utiliser les noms de colonne de la table de modèle, si différents de la source*).</span><span class="sxs-lookup"><span data-stu-id="b63a6-113">In **Column names from**, select **Model** (*to use model table column names, if different from source*).</span></span>  
  
3.  <span data-ttu-id="b63a6-114">Dans la boîte de dialogue **Modifier les propriétés de la table** , dans la fenêtre d’aperçu de la table, décochez la colonne à supprimer, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b63a6-114">In the **Edit Table Properties** dialog box, in the table preview window, uncheck the column you want to delete, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b63a6-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b63a6-115">See Also</span></span>  
 <span data-ttu-id="b63a6-116">[Ajouter des colonnes à une table &#40;&#41;SSAS tabulaire](add-columns-to-a-table-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="b63a6-116">[Add Columns to a Table &#40;SSAS Tabular&#41;](add-columns-to-a-table-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="b63a6-117">Partitions &#40;SSAS Tabulaire&#41;</span><span class="sxs-lookup"><span data-stu-id="b63a6-117">Partitions &#40;SSAS Tabular&#41;</span></span>](partitions-ssas-tabular.md)  
  
  
