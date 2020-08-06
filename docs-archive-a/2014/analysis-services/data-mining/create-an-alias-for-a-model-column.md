---
title: Créer un alias pour une colonne de modèle | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining [Analysis Services], how-to topics
- mining models [Analysis Services], columns
- column names [Analysis Services]
ms.assetid: c80ebe66-a8f8-4f24-9fe8-8288de9d13bc
author: minewiskan
ms.author: owend
ms.openlocfilehash: 908c0a8d8caa810badf4b82dc3dd3f411d09f323
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601778"
---
# <a name="create-an-alias-for-a-model-column"></a><span data-ttu-id="effe7-102">Créer un alias pour une colonne du modèle</span><span class="sxs-lookup"><span data-stu-id="effe7-102">Create an Alias for a Model Column</span></span>
  <span data-ttu-id="effe7-103">Dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], vous pouvez créer un alias pour une colonne du modèle.</span><span class="sxs-lookup"><span data-stu-id="effe7-103">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], you can create an alias for a model column.</span></span> <span data-ttu-id="effe7-104">Cela peut se révéler utile lorsque le nom de la structure d'exploration de données est trop long pour l'utiliser aisément, ou lorsque vous souhaitez renommer la colonne pour que son contenu ou son utilisation dans le modèle soient mieux décrits.</span><span class="sxs-lookup"><span data-stu-id="effe7-104">This might be useful when the mining structure name is too long to easily work with, or when you want to rename the column to be more descriptive of its contents or usage in the model.</span></span> <span data-ttu-id="effe7-105">Par exemple, si vous faites une copie d'une colonne de structure, puis que vous discrétisez la colonne différemment pour un modèle particulier, vous pouvez renommer la colonne pour refléter le contenu de manière plus précise.</span><span class="sxs-lookup"><span data-stu-id="effe7-105">For example, if you make a copy of a structure column and then discretize the column differently for a particular model, you can rename the column to reflect the content more accurately.</span></span>  
  
 <span data-ttu-id="effe7-106">Pour créer un alias pour une colonne du modèle, utilisez le volet **Propriétés** et définissez la propriété [Name](https://docs.microsoft.com/bi-reference/assl/properties/name-element-assl) de la colonne.</span><span class="sxs-lookup"><span data-stu-id="effe7-106">To create an alias for a model column, you use the **Properties** pane and set the [Name](https://docs.microsoft.com/bi-reference/assl/properties/name-element-assl) property of the column.</span></span>  
  
 <span data-ttu-id="effe7-107">Sous l’onglet **Modèles d’exploration de données** du Concepteur d’exploration de données, l’alias apparaît entre parenthèses à côté de l’étiquette d’utilisation de la colonne.</span><span class="sxs-lookup"><span data-stu-id="effe7-107">On the **Mining Models** tab of Data Mining Designer, the alias appears enclosed in parentheses next to the column usage label.</span></span>  
  
 <span data-ttu-id="effe7-108">Pour plus d’informations sur la définition des propriétés d’un modèle d’exploration de données, consultez [Colonnes de modèle d’exploration de données](mining-model-columns.md).</span><span class="sxs-lookup"><span data-stu-id="effe7-108">For information about how to set the properties of a mining model, see [Mining Model Columns](mining-model-columns.md).</span></span>  
  
### <a name="to-add-an-alias-to-a-mining-model-column"></a><span data-ttu-id="effe7-109">Pour ajouter un alias à une colonne du modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="effe7-109">To add an alias to a mining model column</span></span>  
  
1.  <span data-ttu-id="effe7-110">Sous l’onglet **Modèles d’exploration de données** du Concepteur d’exploration de données, cliquez avec le bouton droit sur la cellule dans le modèle d’exploration de données de la colonne d’exploration de données à modifier, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="effe7-110">In the **Mining Models** tab in Data Mining Designer, right-click the cell in the mining model for the mining column that you want to change, and then select **Properties**.</span></span>  
  
2.  <span data-ttu-id="effe7-111">Dans la fenêtre **Propriétés** située à droite de l’écran, cliquez sur la cellule à côté de la propriété Name et supprimez la valeur actuelle.</span><span class="sxs-lookup"><span data-stu-id="effe7-111">In the **Properties** window on the right side of the screen, click the cell next to the Name property and delete the current value.</span></span> <span data-ttu-id="effe7-112">Tapez un nouveau nom pour la colonne.</span><span class="sxs-lookup"><span data-stu-id="effe7-112">Type a new name for the column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="effe7-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="effe7-113">See Also</span></span>  
 <span data-ttu-id="effe7-114">[Tâches du modèle d’exploration de données et procédures](mining-model-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="effe7-114">[Mining Model Tasks and How-tos](mining-model-tasks-and-how-tos.md) </span></span>  
 [<span data-ttu-id="effe7-115">Propriétés du modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="effe7-115">Mining Model Properties</span></span>](mining-model-properties.md)  
  
  
