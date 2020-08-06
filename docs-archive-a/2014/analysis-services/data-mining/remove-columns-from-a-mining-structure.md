---
title: Supprimer des colonnes d’une structure d’exploration de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining structures [Analysis Services], columns
- removing columns
- deleting columns
- columns [data mining], mining structure columns
ms.assetid: 41073ffe-9351-416b-9f0c-62634bc213f9
author: minewiskan
ms.author: owend
ms.openlocfilehash: 44ad1de08d57d00fd9798e1ceeddb85d146d7111
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600342"
---
# <a name="remove-columns-from-a-mining-structure"></a><span data-ttu-id="8d9f7-102">Supprimer des colonnes d'une structure d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="8d9f7-102">Remove Columns from a Mining Structure</span></span>
  <span data-ttu-id="8d9f7-103">Vous pouvez utiliser le Concepteur d'exploration de données pour supprimer des colonnes d'une structure d'exploration de données après que la structure a été créée.</span><span class="sxs-lookup"><span data-stu-id="8d9f7-103">You can use Data Mining Designer to remove columns from a mining structure after the structure has already been created.</span></span> <span data-ttu-id="8d9f7-104">Les raisons de la suppression d'une colonne de structure d'exploration de données peuvent inclure les suivantes :</span><span class="sxs-lookup"><span data-stu-id="8d9f7-104">Reasons to remove a mining structure column might include the following:</span></span>  
  
-   <span data-ttu-id="8d9f7-105">La structure d'exploration de données contient plusieurs copies d'une colonne et vous souhaitez éviter l'utilisation de données en double dans un modèle.</span><span class="sxs-lookup"><span data-stu-id="8d9f7-105">The mining structure contains multiple copies of a column and you want to avoid the use of duplicate data in a model.</span></span>  
  
-   <span data-ttu-id="8d9f7-106">Les données doivent être protégées, mais l'extraction a été activée.</span><span class="sxs-lookup"><span data-stu-id="8d9f7-106">The data should be protected, but drillthrough has been enabled.</span></span>  
  
-   <span data-ttu-id="8d9f7-107">Les données ne sont pas utilisées dans la modélisation et ne doivent pas être traitées.</span><span class="sxs-lookup"><span data-stu-id="8d9f7-107">The data is unused in modeling and should not be processed.</span></span>  
  
 <span data-ttu-id="8d9f7-108">La suppression d'une colonne de la structure d'exploration de données ne modifie pas la colonne de la vue de source de données ou dans les données externes ; seules les métadonnées sont supprimées.</span><span class="sxs-lookup"><span data-stu-id="8d9f7-108">Deleting a column from the mining structure does not change the column in the data source view or in the external data; only metadata is deleted.</span></span> <span data-ttu-id="8d9f7-109">Toutefois, lorsque vous modifiez les colonnes utilisées dans une structure d'exploration de données, vous devez retraiter la structure et tous les modèles basés sur celle-ci.</span><span class="sxs-lookup"><span data-stu-id="8d9f7-109">However, when you change the columns used in a mining structure, you must reprocess the structure and any models based on it.</span></span>  
  
### <a name="to-remove-a-column-from-the-mining-structure"></a><span data-ttu-id="8d9f7-110">Pour supprimer une colonne d'une structure d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="8d9f7-110">To remove a column from the mining structure</span></span>  
  
1.  <span data-ttu-id="8d9f7-111">Sélectionnez l’onglet **Structure d’exploration de données** dans le Concepteur d’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="8d9f7-111">Select the **Mining Structure** tab in Data Mining Designer.</span></span>  
  
2.  <span data-ttu-id="8d9f7-112">Développez l'arborescence de la structure d'exploration de données pour afficher toutes les colonnes.</span><span class="sxs-lookup"><span data-stu-id="8d9f7-112">Expand the tree for the mining structure, to show all the columns.</span></span>  
  
3.  <span data-ttu-id="8d9f7-113">Cliquez avec le bouton droit sur la colonne à supprimer, puis sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="8d9f7-113">Right-click the column that you want to delete, and then select **Delete**.</span></span>  
  
4.  <span data-ttu-id="8d9f7-114">Dans la boîte de dialogue **Supprimer les objets** , cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8d9f7-114">In the **Delete Objects** dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d9f7-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8d9f7-115">See Also</span></span>  
 [<span data-ttu-id="8d9f7-116">Tâches de la structure d'exploration de données et procédures</span><span class="sxs-lookup"><span data-stu-id="8d9f7-116">Mining Structure Tasks and How-tos</span></span>](mining-structure-tasks-and-how-tos.md)  
  
  
