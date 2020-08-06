---
title: Fractionner un dataset à l’aide de la transformation de fractionnement conditionnel | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Conditional Split transformation
- splitting dataset
- datasets [Integration Services], splitting
ms.assetid: 23b3e84f-9296-4dc9-81c0-c7f06ae3f1ff
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2efbc3973db1ab1b6b61f6de879e451319b50e49
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613044"
---
# <a name="split-a-dataset-by-using-the-conditional-split-transformation"></a><span data-ttu-id="16b68-102">Fractionner un dataset à l'aide de la transformation de fractionnement conditionnel</span><span class="sxs-lookup"><span data-stu-id="16b68-102">Split a Dataset by Using the Conditional Split Transformation</span></span>
  <span data-ttu-id="16b68-103">Pour pouvoir ajouter et configurer une transformation de fractionnement conditionnel, le package doit inclure au moins une tâche de flux de données et une source.</span><span class="sxs-lookup"><span data-stu-id="16b68-103">To add and configure a Conditional Split transformation, the package must already include at least one Data Flow task and a source.</span></span>  
  
### <a name="to-conditionally-split-a-dataset"></a><span data-ttu-id="16b68-104">Pour fractionner un dataset de manière conditionnelle</span><span class="sxs-lookup"><span data-stu-id="16b68-104">To conditionally split a dataset</span></span>  
  
1.  <span data-ttu-id="16b68-105">Dans [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] contenant le package souhaité.</span><span class="sxs-lookup"><span data-stu-id="16b68-105">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="16b68-106">Dans l'Explorateur de solutions, double-cliquez sur le package pour l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="16b68-106">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="16b68-107">Cliquez sur l’onglet **Flux de données** puis, dans la **Boîte à outils**, faites glisser la transformation de fractionnement conditionnel sur l’aire de conception.</span><span class="sxs-lookup"><span data-stu-id="16b68-107">Click the **Data Flow** tab, and, from the **Toolbox**, drag the Conditional Split transformation to the design surface.</span></span>  
  
4.  <span data-ttu-id="16b68-108">Connectez la transformation de fractionnement conditionnel au flux de données en faisant glisser le connecteur à partir de la source de données ou de la transformation précédente vers la transformation de fractionnement conditionnel.</span><span class="sxs-lookup"><span data-stu-id="16b68-108">Connect the Conditional Split transformation to the data flow by dragging the connector from the data source or the previous transformation to the Conditional Split transformation.</span></span>  
  
5.  <span data-ttu-id="16b68-109">Double-cliquez sur la transformation de fractionnement conditionnel.</span><span class="sxs-lookup"><span data-stu-id="16b68-109">Double-click the Conditional Split transformation.</span></span>  
  
6.  <span data-ttu-id="16b68-110">Dans **l’Éditeur de transformation de fractionnement conditionnel**, générez les expressions à utiliser comme conditions en faisant glisser des variables, des colonnes, des fonctions et des opérateurs dans la colonne **Condition** de la grille.</span><span class="sxs-lookup"><span data-stu-id="16b68-110">In the **Conditional Split Transformation Editor**, build the expressions to use as conditions by dragging variables, columns, functions, and operators to the **Condition** column in the grid.</span></span> <span data-ttu-id="16b68-111">Vous pouvez également taper l’expression dans la colonne **Condition** .</span><span class="sxs-lookup"><span data-stu-id="16b68-111">Or, you can type the expression in the **Condition** column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="16b68-112">Une variable ou une colonne peut être utilisée dans plusieurs expressions.</span><span class="sxs-lookup"><span data-stu-id="16b68-112">A variable or column can be used in multiple expressions.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="16b68-113">Si l'expression n'est pas valide, son texte est mis en surbrillance et une info-bulle dans la colonne décrit les erreurs.</span><span class="sxs-lookup"><span data-stu-id="16b68-113">If the expression is not valid, the expression text is highlighted and a ToolTip on the column describes the errors.</span></span>  
  
7.  <span data-ttu-id="16b68-114">Si vous le souhaitez, modifiez les valeurs de la colonne **Nom de la sortie** .</span><span class="sxs-lookup"><span data-stu-id="16b68-114">Optionally, modify the values in the **Output Name** column.</span></span> <span data-ttu-id="16b68-115">Les noms par défaut sont Case 1, Case 2, etc.</span><span class="sxs-lookup"><span data-stu-id="16b68-115">The default names are Case 1, Case 2, and so forth.</span></span>  
  
8.  <span data-ttu-id="16b68-116">Pour modifier la séquence dans laquelle les conditions sont évaluées, cliquez sur les flèches haut ou bas.</span><span class="sxs-lookup"><span data-stu-id="16b68-116">To modify the sequence in which the conditions are evaluated, click the up arrow or down arrow.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="16b68-117">Placez les conditions qui ont le plus de chances d'être rencontrées en haut de la liste.</span><span class="sxs-lookup"><span data-stu-id="16b68-117">Place the conditions that are most likely to be encountered at the top of the list.</span></span>  
  
9. <span data-ttu-id="16b68-118">Si vous le souhaitez, modifiez le nom de la sortie par défaut des lignes de données qui ne correspondent à aucune condition.</span><span class="sxs-lookup"><span data-stu-id="16b68-118">Optionally, modify the name of the default output for data rows that do not match any condition.</span></span>  
  
10. <span data-ttu-id="16b68-119">Pour configurer l’affichage des erreurs, cliquez sur **Configurer l’affichage des erreurs**.</span><span class="sxs-lookup"><span data-stu-id="16b68-119">To configure an error output, click **Configure Error Output**.</span></span> <span data-ttu-id="16b68-120">Pour plus d’informations, consultez [Configurer une sortie d’erreur dans un composant de flux de données](../../configure-an-error-output-in-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="16b68-120">For more information, see [Configure an Error Output in a Data Flow Component](../../configure-an-error-output-in-a-data-flow-component.md).</span></span>  
  
11. <span data-ttu-id="16b68-121">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="16b68-121">Click **OK**.</span></span>  
  
12. <span data-ttu-id="16b68-122">Pour enregistrer le package mis à jour, cliquez sur **Enregistrer les éléments sélectionnés** dans le menu **Fichier** .</span><span class="sxs-lookup"><span data-stu-id="16b68-122">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16b68-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="16b68-123">See Also</span></span>  
 <span data-ttu-id="16b68-124">[Conditional Split Transformation](conditional-split-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="16b68-124">[Conditional Split Transformation](conditional-split-transformation.md) </span></span>  
 <span data-ttu-id="16b68-125">[Transformations Integration Services](integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="16b68-125">[Integration Services Transformations](integration-services-transformations.md) </span></span>  
 <span data-ttu-id="16b68-126">[Chemins Integration Services](../integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="16b68-126">[Integration Services Paths](../integration-services-paths.md) </span></span>  
 <span data-ttu-id="16b68-127">[Types de données d’Integration Services](../integration-services-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="16b68-127">[Integration Services Data Types](../integration-services-data-types.md) </span></span>  
 <span data-ttu-id="16b68-128">[Tâche de flux de données](../../control-flow/data-flow-task.md) </span><span class="sxs-lookup"><span data-stu-id="16b68-128">[Data Flow Task](../../control-flow/data-flow-task.md) </span></span>  
 [<span data-ttu-id="16b68-129">Expressions Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="16b68-129">Integration Services &#40;SSIS&#41; Expressions</span></span>](../../expressions/integration-services-ssis-expressions.md)  
  
  
