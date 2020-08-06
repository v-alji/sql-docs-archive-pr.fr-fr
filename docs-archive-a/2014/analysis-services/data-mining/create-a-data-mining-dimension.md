---
title: Créer une dimension d’exploration de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining structures [Analysis Services], dimensions
ms.assetid: 9f0c39e5-3516-43ab-b203-f3f6dbcff89a
author: minewiskan
ms.author: owend
ms.openlocfilehash: 265cf671bbc825258f0b2bd6627690e8c52f252b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694835"
---
# <a name="create-a-data-mining-dimension"></a><span data-ttu-id="b4d8f-102">Créer une dimension d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="b4d8f-102">Create a Data Mining Dimension</span></span>
  <span data-ttu-id="b4d8f-103">Si la structure d'exploration de données repose sur un cube OLAP, vous pouvez créer une dimension qui contient le contenu du modèle d'exploration de données, puis</span><span class="sxs-lookup"><span data-stu-id="b4d8f-103">If your mining structure is based on an OLAP cube, you can create a dimension that contains the content of the mining model.</span></span> <span data-ttu-id="b4d8f-104">réintégrer la dimension dans le cube source.</span><span class="sxs-lookup"><span data-stu-id="b4d8f-104">You can then incorporate the dimension back into the source cube.</span></span>  
  
 <span data-ttu-id="b4d8f-105">Vous pouvez également parcourir la dimension, l'utiliser pour explorer les résultats du modèle ou interroger la dimension à l'aide de MDX.</span><span class="sxs-lookup"><span data-stu-id="b4d8f-105">You can also browse the dimension, use it to explore the model results, or query the dimension using MDX.</span></span>  
  
### <a name="to-create-a-data-mining-dimension"></a><span data-ttu-id="b4d8f-106">Pour créer une dimension d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="b4d8f-106">To create a data mining dimension</span></span>  
  
1.  <span data-ttu-id="b4d8f-107">Dans le Concepteur d’exploration de données de [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], sélectionnez l’onglet **Structure d’exploration de données** ou l’onglet **Modèles d’exploration de données** .</span><span class="sxs-lookup"><span data-stu-id="b4d8f-107">In Data Mining Designer in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], select either the **Mining Structure** tab or the **Mining Models** tab.</span></span>  
  
2.  <span data-ttu-id="b4d8f-108">Dans le menu **Modèle d’exploration de données** , sélectionnez **Créer une dimension d’exploration de données**.</span><span class="sxs-lookup"><span data-stu-id="b4d8f-108">From the **Mining Model** menu, select **Create a Data Mining Dimension**.</span></span>  
  
     <span data-ttu-id="b4d8f-109">La boîte de dialogue **Créer une dimension d’exploration de données** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="b4d8f-109">The **Create Data Mining Dimension** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="b4d8f-110">Dans la liste **Nom du modèle** de la boîte de dialogue **Créer une dimension d’exploration de données** , sélectionnez un modèle d’exploration de données OLAP.</span><span class="sxs-lookup"><span data-stu-id="b4d8f-110">In the **Model name** list of the **Create Data Mining Dimension** dialog box, select an OLAP mining model.</span></span>  
  
4.  <span data-ttu-id="b4d8f-111">Dans la zone **Nom de la dimension** , entrez le nom de la nouvelle dimension d’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="b4d8f-111">In the **Dimension name** box, enter a name for the new data mining dimension.</span></span>  
  
5.  <span data-ttu-id="b4d8f-112">Si vous voulez créer un cube contenant cette nouvelle dimension, sélectionnez **Créer un cube**.</span><span class="sxs-lookup"><span data-stu-id="b4d8f-112">If you want to create a cube that includes the new data mining dimension, select **Create cube**.</span></span> <span data-ttu-id="b4d8f-113">Après avoir sélectionné **Créer un cube**, vous pouvez entrer le nom du nouveau cube.</span><span class="sxs-lookup"><span data-stu-id="b4d8f-113">After you select **Create cube**, you can enter a new name for the cube.</span></span>  
  
6.  <span data-ttu-id="b4d8f-114">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b4d8f-114">Click **OK**.</span></span>  
  
     <span data-ttu-id="b4d8f-115">La dimension d’exploration de données est créée et ajoutée au dossier **Dimensions** dans l’Explorateur de solutions.</span><span class="sxs-lookup"><span data-stu-id="b4d8f-115">The data mining dimension is created and is added to the **Dimensions** folder in Solution Explorer.</span></span> <span data-ttu-id="b4d8f-116">Si vous avez sélectionné **Créer un cube**, un cube est créé et ajouté au dossier **Cubes** .</span><span class="sxs-lookup"><span data-stu-id="b4d8f-116">If you selected **Create cube**, a new cube is also created and is added to the **Cubes** folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4d8f-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b4d8f-117">See Also</span></span>  
 [<span data-ttu-id="b4d8f-118">Tâches de la structure d'exploration de données et procédures</span><span class="sxs-lookup"><span data-stu-id="b4d8f-118">Mining Structure Tasks and How-tos</span></span>](mining-structure-tasks-and-how-tos.md)  
  
  
