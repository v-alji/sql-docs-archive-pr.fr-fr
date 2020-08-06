---
title: Faire une copie d’un modèle d’exploration de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models [Analysis Services], copying
- mining models [Analysis Services], creating
- mining models [Analysis Services], how-to topics
- copying mining models
ms.assetid: 7975bb02-f188-49a0-b7de-5b9b216254ad
author: minewiskan
ms.author: owend
ms.openlocfilehash: a05eb75210ce9f601aeca515cd299f4204908705
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600352"
---
# <a name="make-a-copy-of-a-mining-model"></a><span data-ttu-id="16b31-102">Créer une copie d'un modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="16b31-102">Make a Copy of a Mining Model</span></span>
  <span data-ttu-id="16b31-103">La création d'une copie d'un modèle d'exploration de données est utile lorsque vous souhaitez créer rapidement plusieurs modèles d'exploration de données basés sur les mêmes données.</span><span class="sxs-lookup"><span data-stu-id="16b31-103">Creating a copy of a mining model is useful when you want to quickly create several mining models that are based on the same data.</span></span> <span data-ttu-id="16b31-104">Après avoir copié le modèle, vous pouvez ensuite changer la copie du modèle en modifiant des paramètres ou en ajoutant un filtre.</span><span class="sxs-lookup"><span data-stu-id="16b31-104">After you copy the model, you can then edit the new copy by changing parameters or adding a filter.</span></span>  
  
 <span data-ttu-id="16b31-105">Par exemple, si vous avez une table de clients liée à une table d’achats, vous pouvez créer des copies pour générer des modèles d’exploration de données distincts pour chaque client en filtrant sur des informations démographiques, telles que des attributs d’âge ou de région.</span><span class="sxs-lookup"><span data-stu-id="16b31-105">For example, if you have a Customers table that is linked to a table of purchases, you could create copies to generate separate mining models for each customer demographic, filtering on attributes such as age or region.</span></span>  
  
 <span data-ttu-id="16b31-106">Pour plus d’informations sur la copie du contenu du modèle (tel que la représentation graphique ou les schémas de modèles) dans le Presse-papiers pour une utilisation dans d’autres programmes, consultez [Copier une vue d’un modèle d’exploration de données](copy-a-view-of-a-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="16b31-106">For information about how to copy the content of the model (such as the graphical representation or the model patterns) to the Clipboard for use in other programs, see [Copy a View of a Mining Model](copy-a-view-of-a-mining-model.md).</span></span>  
  
### <a name="to-create-a-related-mining-model"></a><span data-ttu-id="16b31-107">Pour créer un modèle d'exploration de données connexe</span><span class="sxs-lookup"><span data-stu-id="16b31-107">To create a related mining model</span></span>  
  
1.  <span data-ttu-id="16b31-108">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], dans l’Explorateur de solutions, cliquez sur la structure d’exploration de données qui contient le modèle d’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="16b31-108">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], in Solution Explorer, click the mining structure that contains the mining model.</span></span>  
  
2.  <span data-ttu-id="16b31-109">Cliquez sur l'onglet **Modèles d'exploration de données** .</span><span class="sxs-lookup"><span data-stu-id="16b31-109">Click the **Mining Models** tab.</span></span>  
  
3.  <span data-ttu-id="16b31-110">Sélectionnez le modèle et cliquez avec le bouton droit pour ouvrir le menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="16b31-110">Select the model, and right-click to open the shortcut menu.</span></span>  
  
     <span data-ttu-id="16b31-111">-ou-</span><span class="sxs-lookup"><span data-stu-id="16b31-111">-or-</span></span>  
  
     <span data-ttu-id="16b31-112">Sélectionnez le modèle.</span><span class="sxs-lookup"><span data-stu-id="16b31-112">Select the model.</span></span> <span data-ttu-id="16b31-113">Dans le menu **Modèle d’exploration de données** , sélectionnez **Nouveau modèle d’exploration de données**.</span><span class="sxs-lookup"><span data-stu-id="16b31-113">On the **Mining Model** menu, select **New Mining Model**.</span></span>  
  
4.  <span data-ttu-id="16b31-114">Tapez un nom pour le nouveau modèle d'exploration de données et sélectionnez un algorithme.</span><span class="sxs-lookup"><span data-stu-id="16b31-114">Type a name for the new mining model, and select an algorithm.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-edit-the-filter-on-the-copied-mining-model"></a><span data-ttu-id="16b31-115">Pour modifier le filtre sur le modèle d'exploration de données copié</span><span class="sxs-lookup"><span data-stu-id="16b31-115">To edit the filter on the copied mining model</span></span>  
  
1.  <span data-ttu-id="16b31-116">Sélectionnez le modèle d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="16b31-116">Select the mining model.</span></span>  
  
2.  <span data-ttu-id="16b31-117">Dans la fenêtre **Propriétés** , cliquez sur la zone de texte correspondant à la propriété **filtre** , puis cliquez sur le bouton Générer **(...)** .</span><span class="sxs-lookup"><span data-stu-id="16b31-117">In the **Properties** window, click the text box for the **Filter** property, and the click the build **(...)** button.</span></span>  
  
3.  <span data-ttu-id="16b31-118">Modifiez les conditions de filtre.</span><span class="sxs-lookup"><span data-stu-id="16b31-118">Change the filter conditions.</span></span>  
  
     <span data-ttu-id="16b31-119">Pour plus d’informations sur l’utilisation des boîtes de dialogue de l’éditeur de filtre, consultez [Appliquer un filtre à un modèle d’exploration de données](apply-a-filter-to-a-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="16b31-119">For more information about how to use the filter editor dialog boxes, see [Apply a Filter to a Mining Model](apply-a-filter-to-a-mining-model.md).</span></span>  
  
4.  <span data-ttu-id="16b31-120">Dans la fenêtre **Propriétés** , dans la `AlgorithmParameters` zone de texte, cliquez sur **paramètres de définir**et modifiez les paramètres d’algorithme, si vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="16b31-120">In the **Properties** window, in the `AlgorithmParameters` text box, click **Setalgorithm parameters**, and change algorithm parameters, if desired.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="16b31-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="16b31-121">See Also</span></span>  
 <span data-ttu-id="16b31-122">[Filtres pour les modèles d’exploration de données &#40;Analysis Services d’exploration de données&#41;](mining-models-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="16b31-122">[Filters for Mining Models &#40;Analysis Services - Data Mining&#41;](mining-models-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="16b31-123">[Tâches du modèle d’exploration de données et procédures](mining-model-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="16b31-123">[Mining Model Tasks and How-tos](mining-model-tasks-and-how-tos.md) </span></span>  
 [<span data-ttu-id="16b31-124">Supprimer un filtre d'un modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="16b31-124">Delete a Filter from a Mining Model</span></span>](delete-a-filter-from-a-mining-model.md)  
  
  
