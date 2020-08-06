---
title: Exclure une colonne d’un modèle d’exploration de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- excluding mining model columns
- mining models [Analysis Services], columns
- columns [data mining], excluding
ms.assetid: 404fe5fe-3ba2-4b9b-8780-0d02343d467f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 30affebc143184c6287858f60b5d4f5d089c322a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603723"
---
# <a name="exclude-a-column-from-a-mining-model"></a><span data-ttu-id="bd7b5-102">Exclure une colonne d'un modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="bd7b5-102">Exclude a Column from a Mining Model</span></span>
  <span data-ttu-id="bd7b5-103">Lorsque vous créez un modèle d'exploration de données, vous pouvez décider de ne pas utiliser toutes les colonnes qui existent dans la structure d'exploration de données sur laquelle le modèle repose.</span><span class="sxs-lookup"><span data-stu-id="bd7b5-103">When you create a new mining model, you may not want to use all the columns that exist in the mining structure on which the model is based.</span></span> <span data-ttu-id="bd7b5-104">Par exemple, vous avez peut-être ajouté une colonne nom du client pour l’extraction, mais vous ne souhaitez pas l’utiliser pour la modélisation.</span><span class="sxs-lookup"><span data-stu-id="bd7b5-104">For example, you might have added a customer name column for drillthrough, but don't want to use it for modeling.</span></span> <span data-ttu-id="bd7b5-105">Ou, vous pouvez décider de créer plusieurs copies d'une colonne avec différentes discrétisations, et utiliser uniquement une des copies dans chaque modèle, et ignorer les autres.</span><span class="sxs-lookup"><span data-stu-id="bd7b5-105">Or, you might decide to create multiple copies of a column with different discretizations, and use only one of the copies in each model, and ignore the rest.</span></span> <span data-ttu-id="bd7b5-106">Vous pouvez également ajouter de manière sélective des colonnes d'entrée dans différents modèles pour voir de quelle façon la variable ajoutée affecte la colonne de sortie.</span><span class="sxs-lookup"><span data-stu-id="bd7b5-106">You could also selectively add input columns in several different models to see how the added variable affects the output column.</span></span>  
  
 <span data-ttu-id="bd7b5-107">Vous n'avez pas besoin de créer une nouvelle structure d'exploration de données pour chaque combinaison de colonnes ; à la place, vous pouvez simplement marquer une colonne comme n'étant pas utilisée dans un modèle particulier.</span><span class="sxs-lookup"><span data-stu-id="bd7b5-107">You do not need to create a new mining structure for each combination of columns; instead, you can simply flag a column as not being used in a particular model.</span></span>  
  
### <a name="to-exclude-a-column-from-a-mining-model"></a><span data-ttu-id="bd7b5-108">Pour exclure une colonne d'un modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="bd7b5-108">To exclude a column from a mining model</span></span>  
  
1.  <span data-ttu-id="bd7b5-109">Sous l’onglet **Modèles d’exploration de données** du Concepteur d’exploration de données dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], sélectionnez la cellule qui correspond à la colonne à exclure sous le modèle d’exploration de données approprié.</span><span class="sxs-lookup"><span data-stu-id="bd7b5-109">In the **Mining Models** tab of Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], select the cell that corresponds to the column you want to exclude, under the appropriate mining model.</span></span>  
  
2.  <span data-ttu-id="bd7b5-110">Sélectionnez **Ignorer** dans la zone de liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="bd7b5-110">Select **Ignore** from the drop-down list box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd7b5-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bd7b5-111">See Also</span></span>  
 [<span data-ttu-id="bd7b5-112">Tâches du modèle d'exploration de données et procédures</span><span class="sxs-lookup"><span data-stu-id="bd7b5-112">Mining Model Tasks and How-tos</span></span>](mining-model-tasks-and-how-tos.md)  
  
  
