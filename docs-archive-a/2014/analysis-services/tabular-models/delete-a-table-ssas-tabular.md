---
title: Supprimer une table (SSAS tabulaire) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: be4ed45f-fde3-466c-9869-49bd3ddb505e
author: minewiskan
ms.author: owend
ms.openlocfilehash: c72fa90426440c1be84318a15cf0d761ef16aca8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612471"
---
# <a name="delete-a-table-ssas-tabular"></a><span data-ttu-id="1aeb1-102">Supprimer une table (SSAS Tabulaire)</span><span class="sxs-lookup"><span data-stu-id="1aeb1-102">Delete a Table (SSAS Tabular)</span></span>
  <span data-ttu-id="1aeb1-103">Dans le générateur de modèles, vous pouvez supprimer des tables dont vous n'avez plus besoin dans votre base de données model de l'espace de travail.</span><span class="sxs-lookup"><span data-stu-id="1aeb1-103">In the model designer, you can delete tables in your model workspace database that you no longer need.</span></span> <span data-ttu-id="1aeb1-104">La suppression d’une table n’affecte pas les données sources d’origine, mais uniquement les données que vous avez importées et que vous utilisiez.</span><span class="sxs-lookup"><span data-stu-id="1aeb1-104">Deleting a table does not affect the original source data, only the data that you imported and were working with.</span></span> <span data-ttu-id="1aeb1-105">Vous ne pouvez pas annuler la suppression d'une table.</span><span class="sxs-lookup"><span data-stu-id="1aeb1-105">You cannot undo the deletion of a table.</span></span>  
  
### <a name="to-delete-a-table"></a><span data-ttu-id="1aeb1-106">Pour supprimer une table</span><span class="sxs-lookup"><span data-stu-id="1aeb1-106">To delete a table</span></span>  
  
-   <span data-ttu-id="1aeb1-107">Cliquez avec le bouton droit sur l’onglet situé au bas du générateur de modèles pour la table à supprimer, puis sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="1aeb1-107">Right-click the tab at the bottom of the model designer for the table that you want to delete, and then click **Delete**.</span></span>  
  
## <a name="considerations-when-deleting-tables"></a><span data-ttu-id="1aeb1-108">Considérations à prendre en compte lors de la suppression de tables</span><span class="sxs-lookup"><span data-stu-id="1aeb1-108">Considerations when Deleting Tables</span></span>  
  
-   <span data-ttu-id="1aeb1-109">Lorsque vous supprimez une table, l'onglet tout entier sur lequel se trouvait la table est supprimé.</span><span class="sxs-lookup"><span data-stu-id="1aeb1-109">When you delete a table, the entire tab that the table was on is deleted.</span></span>  
  
-   <span data-ttu-id="1aeb1-110">Si des mesures étaient associées à cette table, la définition de la mesure est également supprimée.</span><span class="sxs-lookup"><span data-stu-id="1aeb1-110">If any measures were associated with that table, the definition of the measure will also be deleted.</span></span>  
  
-   <span data-ttu-id="1aeb1-111">Si vous avez créé des colonnes calculées à l'aide de cette table, les colonnes de cette table sont également supprimées ; toutes les colonnes calculées dans d'autres tables qui utilisent les colonnes de la table supprimée affichent une erreur.</span><span class="sxs-lookup"><span data-stu-id="1aeb1-111">If you created any calculated columns using that table, columns in that table are also deleted; any calculated columns in other tables that use columns from the deleted table will display an error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1aeb1-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1aeb1-112">See Also</span></span>  
 [<span data-ttu-id="1aeb1-113">Tables et colonnes &#40;SSAS Tabulaire&#41;</span><span class="sxs-lookup"><span data-stu-id="1aeb1-113">Tables and Columns &#40;SSAS Tabular&#41;</span></span>](tables-and-columns-ssas-tabular.md)  
  
  
