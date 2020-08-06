---
title: Étendre un dataset à l’aide de la transformation de jointure de fusion | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Merge Join transformation
- datasets [Integration Services], joining
- datasets [Integration Services], extending
- joining datasets [Integration Services]
ms.assetid: 9e512c3c-f89b-45f3-8281-cdb8f35a2b1f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a387c4ad840eb739d36023be9323c063dcb9a68e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602229"
---
# <a name="extend-a-dataset-by-using-the-merge-join-transformation"></a><span data-ttu-id="bf117-102">Étendre un dataset à l'aide de la transformation de jointure de fusion</span><span class="sxs-lookup"><span data-stu-id="bf117-102">Extend a Dataset by Using the Merge Join Transformation</span></span>
  <span data-ttu-id="bf117-103">Pour pouvoir ajouter et configurer une transformation de jointure de fusion, le package doit inclure au moins une tâche de flux de données et deux composants de flux de données qui fournissent des entrées à la transformation de jointure de fusion.</span><span class="sxs-lookup"><span data-stu-id="bf117-103">To add and configure a Merge Join transformation, the package must already include at least one Data Flow task and two data flow components that provide inputs to the Merge Join transformation.</span></span>  
  
 <span data-ttu-id="bf117-104">La transformation de jointure de fusion requiert deux entrées triées.</span><span class="sxs-lookup"><span data-stu-id="bf117-104">The Merge Join transformation requires two sorted inputs.</span></span> <span data-ttu-id="bf117-105">Pour plus d’informations, consultez [Trier des données pour les transformations de fusion et de jointure de fusion](sort-data-for-the-merge-and-merge-join-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="bf117-105">For more information, see [Sort Data for the Merge and Merge Join Transformations](sort-data-for-the-merge-and-merge-join-transformations.md).</span></span>  
  
### <a name="to-extend-a-dataset"></a><span data-ttu-id="bf117-106">Pour étendre un dataset</span><span class="sxs-lookup"><span data-stu-id="bf117-106">To extend a dataset</span></span>  
  
1.  <span data-ttu-id="bf117-107">Dans [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] contenant le package souhaité.</span><span class="sxs-lookup"><span data-stu-id="bf117-107">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="bf117-108">Dans l'Explorateur de solutions, double-cliquez sur le package pour l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="bf117-108">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="bf117-109">Cliquez sur l’onglet **Flux de données** , puis dans la **Boîte à outils**, faites glisser la transformation de jointure de fusion vers la surface de dessin.</span><span class="sxs-lookup"><span data-stu-id="bf117-109">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the Merge Join transformation to the design surface.</span></span>  
  
4.  <span data-ttu-id="bf117-110">Connectez la transformation de jointure de fusion au flux de données en faisant glisser le connecteur à partir d'une source de données ou d'une transformation précédente vers la transformation de jointure de fusion.</span><span class="sxs-lookup"><span data-stu-id="bf117-110">Connect the Merge Join transformation to the data flow by dragging the connector from a data source or a previous transformation to the Merge Join transformation.</span></span>  
  
5.  <span data-ttu-id="bf117-111">Double-cliquez sur la transformation de jointure de fusion.</span><span class="sxs-lookup"><span data-stu-id="bf117-111">Double-click the Merge Join transformation.</span></span>  
  
6.  <span data-ttu-id="bf117-112">Dans la boîte de dialogue **Éditeur de transformation de jointure de fusion** , sélectionnez le type de jointure à utiliser dans la liste **Type de jointure** .</span><span class="sxs-lookup"><span data-stu-id="bf117-112">In the **Merge Join Transformation Editor** dialog box, select the type of join to use in the **Join type** list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bf117-113">Si vous sélectionnez **Jointure externe gauche** , vous pouvez cliquer sur **Échanger les entrées** pour échanger les entrées et convertir la jointure externe gauche en jointure externe droite.</span><span class="sxs-lookup"><span data-stu-id="bf117-113">If you select the **Left outer join** type, you can click **Swap Inputs** to switch the inputs and convert the left outer join to a right outer join.</span></span>  
  
7.  <span data-ttu-id="bf117-114">Faites glisser des colonnes de l'entrée de gauche vers des colonnes de l'entrée de droite afin de spécifier les colonnes de jointure.</span><span class="sxs-lookup"><span data-stu-id="bf117-114">Drag columns in the left input to columns in the right input to specify the join columns.</span></span> <span data-ttu-id="bf117-115">Si les colonnes portent le même nom, vous pouvez cocher la case **Clé de jointure** afin que la transformation de jointure de fusion crée la jointure.</span><span class="sxs-lookup"><span data-stu-id="bf117-115">If the columns have the same name, you can select the **Join Key** check box and the Merge Join transformation automatically creates the join.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bf117-116">Vous pouvez créer des jointures uniquement entre des colonnes ayant la même position de tri et les jointures doivent être créées dans l'ordre spécifié par la position de tri.</span><span class="sxs-lookup"><span data-stu-id="bf117-116">You can create joins only between columns that have the same sort position, and the joins must be created in the order specified by the sort position.</span></span> <span data-ttu-id="bf117-117">Si vous essayez de créer des jointures dans le désordre, **l’Éditeur de transformation de jointure de fusion** vous demande de créer des jointures supplémentaires pour les positions d’ordre de tri ignorées.</span><span class="sxs-lookup"><span data-stu-id="bf117-117">If you attempt to create the joins out of order, the **Merge Join Transformation Editor** prompts you to create additional joins for the skipped sort order positions.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bf117-118">Par défaut, la sortie est triée sur les colonnes de jointure.</span><span class="sxs-lookup"><span data-stu-id="bf117-118">By default, the output is sorted on the join columns.</span></span>  
  
8.  <span data-ttu-id="bf117-119">Dans les entrées de gauche et de droite, activez les cases à cocher des colonnes supplémentaires à inclure dans la sortie.</span><span class="sxs-lookup"><span data-stu-id="bf117-119">In the left and right inputs, select the check boxes of additional columns to include in the output.</span></span> <span data-ttu-id="bf117-120">Les colonnes de jointure sont incluses par défaut.</span><span class="sxs-lookup"><span data-stu-id="bf117-120">Join columns are included by default.</span></span>  
  
9. <span data-ttu-id="bf117-121">Mettez éventuellement à jour les noms des colonnes de sortie dans la colonne **Alias de sortie** .</span><span class="sxs-lookup"><span data-stu-id="bf117-121">Optionally, update the names of output columns in the **Output Alias** column.</span></span>  
  
10. <span data-ttu-id="bf117-122">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="bf117-122">Click **OK**.</span></span>  
  
11. <span data-ttu-id="bf117-123">Pour enregistrer le package mis à jour, cliquez sur **Enregistrer les éléments sélectionnés** dans le menu **Fichier** .</span><span class="sxs-lookup"><span data-stu-id="bf117-123">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf117-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bf117-124">See Also</span></span>  
 <span data-ttu-id="bf117-125">[Transformation de jointure de fusion](merge-join-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="bf117-125">[Merge Join Transformation](merge-join-transformation.md) </span></span>  
 <span data-ttu-id="bf117-126">[Transformations Integration Services](integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="bf117-126">[Integration Services Transformations](integration-services-transformations.md) </span></span>  
 <span data-ttu-id="bf117-127">[Chemins Integration Services](../integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="bf117-127">[Integration Services Paths](../integration-services-paths.md) </span></span>  
 [<span data-ttu-id="bf117-128">tâche de flux de données</span><span class="sxs-lookup"><span data-stu-id="bf117-128">Data Flow Task</span></span>](../../control-flow/data-flow-task.md)  
  
  
