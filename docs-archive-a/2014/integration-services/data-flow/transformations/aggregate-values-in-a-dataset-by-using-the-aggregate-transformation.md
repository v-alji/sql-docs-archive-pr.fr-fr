---
title: Agréger les valeurs dans un dataset à l’aide de la transformation d’agrégation | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Aggregate transformation [Integration Services]
- aggregate values [Integration Services]
- datasets [Integration Services], aggregate values
ms.assetid: 01b81c0f-d5e0-483b-81b2-73800a6945ac
author: chugugrace
ms.author: chugu
ms.openlocfilehash: de918c6c2adf194d5808ccd1b64c77a94a52e357
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695884"
---
# <a name="aggregate-values-in-a-dataset-by-using-the-aggregate-transformation"></a><span data-ttu-id="252b3-102">Agréger les valeurs dans un dataset à l'aide de la transformation d'agrégation</span><span class="sxs-lookup"><span data-stu-id="252b3-102">Aggregate Values in a Dataset by Using the Aggregate Transformation</span></span>
  <span data-ttu-id="252b3-103">Pour pouvoir ajouter et configurer une transformation d'agrégation, le package doit inclure au moins une tâche de flux de données et une source.</span><span class="sxs-lookup"><span data-stu-id="252b3-103">To add and configure an Aggregate transformation, the package must already include at least one Data Flow task and one source.</span></span>  
  
### <a name="to-aggregate-values-in-a-dataset"></a><span data-ttu-id="252b3-104">Pour agréger les valeurs dans un dataset</span><span class="sxs-lookup"><span data-stu-id="252b3-104">To aggregate values in a dataset</span></span>  
  
1.  <span data-ttu-id="252b3-105">Dans [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] contenant le package souhaité.</span><span class="sxs-lookup"><span data-stu-id="252b3-105">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="252b3-106">Dans l'Explorateur de solutions, double-cliquez sur le package pour l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="252b3-106">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="252b3-107">Cliquez sur l’onglet **Flux de données** , puis dans la **Boîte à outils**, faites glisser la transformation d’agrégation sur la surface de dessin.</span><span class="sxs-lookup"><span data-stu-id="252b3-107">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the Aggregate transformation to the design surface.</span></span>  
  
4.  <span data-ttu-id="252b3-108">Connectez la transformation d'agrégation au flux de données en faisant glisser un connecteur à partir de la source ou de la transformation précédente vers la transformation d'agrégation.</span><span class="sxs-lookup"><span data-stu-id="252b3-108">Connect the Aggregate transformation to the data flow by dragging a connector from the source or the previous transformation to the Aggregate transformation.</span></span>  
  
5.  <span data-ttu-id="252b3-109">Double-cliquez sur la transformation.</span><span class="sxs-lookup"><span data-stu-id="252b3-109">Double-click the transformation.</span></span>  
  
6.  <span data-ttu-id="252b3-110">Dans la boîte de dialogue **Éditeur de transformation d’agrégation** , cliquez sur l’onglet **Agrégations** .</span><span class="sxs-lookup"><span data-stu-id="252b3-110">In the **Aggregate Transformation Editor** dialog box, click the **Aggregations** tab.</span></span>  
  
7.  <span data-ttu-id="252b3-111">Dans la liste **Colonnes d’entrée disponibles** , cochez la case des colonnes dont vous voulez agréger les valeurs.</span><span class="sxs-lookup"><span data-stu-id="252b3-111">In the **Available Input Columns** list, select the check box by the columns on which you want to aggregate values.</span></span> <span data-ttu-id="252b3-112">Les colonnes sélectionnées s'affichent dans la table.</span><span class="sxs-lookup"><span data-stu-id="252b3-112">The selected columns appear in the table.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="252b3-113">Vous pouvez sélectionner une colonne plusieurs fois afin de lui appliquer plusieurs transformations.</span><span class="sxs-lookup"><span data-stu-id="252b3-113">You can select a column multiple times, applying multiple transformations to the column.</span></span> <span data-ttu-id="252b3-114">Pour identifier les agrégations de manière unique, un numéro est ajouté au nom par défaut de l'alias de sortie de la colonne.</span><span class="sxs-lookup"><span data-stu-id="252b3-114">To uniquely identify aggregations, a number is appended to the default name of the output alias of the column.</span></span>  
  
8.  <span data-ttu-id="252b3-115">Si vous le souhaitez, modifiez la valeur des colonnes **Alias de sortie** .</span><span class="sxs-lookup"><span data-stu-id="252b3-115">Optionally, modify the value in the **Output Alias** columns.</span></span>  
  
9. <span data-ttu-id="252b3-116">Pour modifier l’opération d’agrégation par défaut, **Group by**, sélectionnez une autre opération dans la liste **Opération** .</span><span class="sxs-lookup"><span data-stu-id="252b3-116">To change the default aggregation operation, **Group by**, select a different operation in the **Operation** list.</span></span>  
  
10. <span data-ttu-id="252b3-117">Pour modifier la comparaison par défaut, sélectionnez les indicateurs de comparaison individuels répertoriés dans la colonne **Indicateurs de comparaison** .</span><span class="sxs-lookup"><span data-stu-id="252b3-117">To change the default comparison, select the individual comparison flags listed in the **Comparison Flags** column.</span></span> <span data-ttu-id="252b3-118">Par défaut, une comparaison ignore la casse, les caractères de type Kana, les caractères de non-espacement et la largeur des caractères.</span><span class="sxs-lookup"><span data-stu-id="252b3-118">By default, a comparison ignores case, kana type, non-spacing characters, and character width.</span></span>  
  
11. <span data-ttu-id="252b3-119">Si vous le souhaitez, pour l’agrégation **Count distinct** , indiquez le nombre exact de valeurs distinctes dans la colonne **Nombre de clés distinctes** ou sélectionnez un nombre approximatif dans la colonne **Échelle de nombre des valeurs distinctes** .</span><span class="sxs-lookup"><span data-stu-id="252b3-119">Optionally, for the **Count distinct** aggregation, specify an exact number of distinct values in the **Count Distinct Keys** column, or select an approximate count in the **Count Distinct Scale** column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="252b3-120">La fourniture du nombre de valeurs distinctes, exact ou approximatif, optimise les performances, car la transformation peut préallouer la quantité de mémoire appropriée pour effectuer son travail.</span><span class="sxs-lookup"><span data-stu-id="252b3-120">Providing the number of distinct values, exact or approximate, optimizes performance, because the transformation can preallocate an appropriate amount of memory to do its work.</span></span>  
  
12. <span data-ttu-id="252b3-121">Si vous le souhaitez, cliquez sur **Avancé** et mettez à jour le nom de la sortie de la transformation d’agrégation.</span><span class="sxs-lookup"><span data-stu-id="252b3-121">Optionally, click **Advanced** and update the name of the Aggregate transformation output.</span></span> <span data-ttu-id="252b3-122">Si les agrégations incluent une `Group By` opération, vous pouvez sélectionner un nombre approximatif de valeurs de clé de regroupement dans la **colonne échelle de clés** ou spécifier un nombre exact de valeurs de clé de regroupement dans la colonne **clés** .</span><span class="sxs-lookup"><span data-stu-id="252b3-122">If the aggregations include a `Group By` operation, you can select an approximate count of grouping key values in the **Keys Scale** column or specify an exact number of grouping key values in the **Keys** column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="252b3-123">La fourniture du nombre de valeurs distinctes, exact ou approximatif, optimise les performances, car la transformation peut préallouer la quantité de mémoire appropriée pour effectuer son travail.</span><span class="sxs-lookup"><span data-stu-id="252b3-123">Providing the number of distinct values, exact or approximate, optimizes performance, because the transformation can preallocate an appropriate amount of memory to do its work.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="252b3-124">Les options **Redéfinir le nombre de clés** et **Clés** s’excluent mutuellement.</span><span class="sxs-lookup"><span data-stu-id="252b3-124">The **Keys Scale** and **Keys** options are mutually exclusive.</span></span> <span data-ttu-id="252b3-125">Si vous tapez des valeurs dans les deux colonnes, la valeur la plus grande de la colonne **Redéfinir le nombre de clés** ou **Clés** est utilisée.</span><span class="sxs-lookup"><span data-stu-id="252b3-125">If you enter values in both columns, the larger value in either **Keys Scale** or **Keys** is used.</span></span>  
  
13. <span data-ttu-id="252b3-126">Si vous le souhaitez, cliquez sur l’onglet **Avancé** et définissez les attributs qui s’appliquent à l’optimisation de toutes les opérations réalisées par la transformation d’agrégation.</span><span class="sxs-lookup"><span data-stu-id="252b3-126">Optionally, click the **Advanced** tab and set the attributes that apply to optimizing all the operations that the Aggregate transformation performs.</span></span>  
  
14. <span data-ttu-id="252b3-127">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="252b3-127">Click **OK**.</span></span>  
  
15. <span data-ttu-id="252b3-128">Pour enregistrer le package mis à jour, cliquez sur **Enregistrer les éléments sélectionnés** dans le menu **Fichier** .</span><span class="sxs-lookup"><span data-stu-id="252b3-128">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="252b3-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="252b3-129">See Also</span></span>  
 <span data-ttu-id="252b3-130">[Transformation d'agrégation](aggregate-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="252b3-130">[Aggregate Transformation](aggregate-transformation.md) </span></span>  
 <span data-ttu-id="252b3-131">[Transformations Integration Services](integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="252b3-131">[Integration Services Transformations](integration-services-transformations.md) </span></span>  
 <span data-ttu-id="252b3-132">[Chemins Integration Services](../integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="252b3-132">[Integration Services Paths](../integration-services-paths.md) </span></span>  
 [<span data-ttu-id="252b3-133">tâche de flux de données</span><span class="sxs-lookup"><span data-stu-id="252b3-133">Data Flow Task</span></span>](../../control-flow/data-flow-task.md)  
  
  
