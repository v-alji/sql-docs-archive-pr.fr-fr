---
title: Dériver les valeurs de colonnes à l’aide de la transformation de colonne dérivée | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- columns [Integration Services]
- derived columns
- columns [Integration Services], values
- Derived Column transformation
ms.assetid: 28b07746-fc6f-42b2-b741-9de6fac3f29c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 837ec552144697b40cf649bc0403edfe4dc57a57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601017"
---
# <a name="derive-column-values-by-using-the-derived-column-transformation"></a><span data-ttu-id="9bb6c-102">Dériver les valeurs de colonnes à l'aide de la transformation de colonne dérivée</span><span class="sxs-lookup"><span data-stu-id="9bb6c-102">Derive Column Values by Using the Derived Column Transformation</span></span>
  <span data-ttu-id="9bb6c-103">Pour pouvoir ajouter et configurer une transformation de colonne dérivée, le package doit inclure au moins une tâche de flux de données et une source.</span><span class="sxs-lookup"><span data-stu-id="9bb6c-103">To add and configure a Derived Column transformation, the package must already include at least one Data Flow task and one source.</span></span>  
  
 <span data-ttu-id="9bb6c-104">La transformation Colonne dérivée utilise des expressions pour mettre à jour les valeurs de colonnes existantes ou pour ajouter des valeurs à de nouvelles colonnes.</span><span class="sxs-lookup"><span data-stu-id="9bb6c-104">The Derived Column transformation uses expressions to update the values of existing or to add values to new columns.</span></span> <span data-ttu-id="9bb6c-105">Quand vous décidez d’ajouter des valeurs à de nouvelles colonnes, la boîte de dialogue **Éditeur de transformation de colonne dérivée** évalue l’expression et définit les métadonnées des colonnes en conséquence.</span><span class="sxs-lookup"><span data-stu-id="9bb6c-105">When you choose to add values to new columns, the **Derived Column Transformation Editor** dialog box evaluates the expression and defines the metadata of the columns accordingly.</span></span> <span data-ttu-id="9bb6c-106">Par exemple, si une expression concatène deux colonnes, chacune possédant le type de données DT_WSTR et une longueur de 50, avec un espace entre les deux valeurs de colonnes, la nouvelle colonne possède le type de données DT_WSTR et une longueur de 101.</span><span class="sxs-lookup"><span data-stu-id="9bb6c-106">For example, if an expression concatenates two columns-each with the DT_WSTR data type and a length of 50-with a space between the two column values, the new column has the DT_WSTR data type and a length of 101.</span></span> <span data-ttu-id="9bb6c-107">Vous pouvez mettre à jour le type de données des nouvelles colonnes.</span><span class="sxs-lookup"><span data-stu-id="9bb6c-107">You can update the data type of new columns.</span></span> <span data-ttu-id="9bb6c-108">La seule nécessité est que le type de données soit compatible avec les données insérées.</span><span class="sxs-lookup"><span data-stu-id="9bb6c-108">The only requirement is that data type be compatible with the inserted data.</span></span> <span data-ttu-id="9bb6c-109">Par exemple, la boîte de dialogue **Éditeur de transformation de colonne dérivée** génère une erreur de validation quand vous affectez une valeur de date à une colonne contenant un type de données entier.</span><span class="sxs-lookup"><span data-stu-id="9bb6c-109">For example, the **Derived Column Transformation Editor** dialog box generates a validation error when you assign a date value to a column with an integer data type.</span></span> <span data-ttu-id="9bb6c-110">En fonction du type de données sélectionné, vous pouvez spécifier la longueur, la précision, l'échelle et la page de codes de la colonne.</span><span class="sxs-lookup"><span data-stu-id="9bb6c-110">Depending on the data type that you selected, you can specify the length, precision, scale, and code page of the column.</span></span>  
  
### <a name="to-derive-column-values"></a><span data-ttu-id="9bb6c-111">Pour dériver les valeurs de colonnes</span><span class="sxs-lookup"><span data-stu-id="9bb6c-111">To derive column values</span></span>  
  
1.  <span data-ttu-id="9bb6c-112">Dans [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] contenant le package souhaité.</span><span class="sxs-lookup"><span data-stu-id="9bb6c-112">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="9bb6c-113">Dans l'Explorateur de solutions, double-cliquez sur le package pour l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="9bb6c-113">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="9bb6c-114">Cliquez sur l’onglet **Flux de données** puis, dans la **Boîte à outils**, faites glisser la transformation de colonne dérivée sur l’aire de conception.</span><span class="sxs-lookup"><span data-stu-id="9bb6c-114">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the Derived Column transformation to the design surface.</span></span>  
  
4.  <span data-ttu-id="9bb6c-115">Connectez la transformation de colonne dérivée au flux de données en faisant glisser le connecteur à partir de la source ou de la transformation précédente vers la transformation de colonne dérivée.</span><span class="sxs-lookup"><span data-stu-id="9bb6c-115">Connect the Derived Column transformation to the data flow by dragging the connector from the source or the previous transformation to the Derived Column transformation.</span></span>  
  
5.  <span data-ttu-id="9bb6c-116">Double-cliquez sur la transformation de colonne dérivée.</span><span class="sxs-lookup"><span data-stu-id="9bb6c-116">Double-click the Derived Column transformation.</span></span>  
  
6.  <span data-ttu-id="9bb6c-117">Dans la boîte de dialogue **Éditeur de transformation de colonne dérivée** , générez les expressions à utiliser comme conditions en faisant glisser des variables, des colonnes, des fonctions et des opérateurs dans la colonne **Expression** de la grille.</span><span class="sxs-lookup"><span data-stu-id="9bb6c-117">In the **Derived Column Transformation Editor** dialog box, build the expressions to use as conditions by dragging variables, columns, functions, and operators to the **Expression** column in the grid.</span></span> <span data-ttu-id="9bb6c-118">Vous pouvez également taper l’expression dans la colonne **Expression** .</span><span class="sxs-lookup"><span data-stu-id="9bb6c-118">Alternatively, you can type the expression in the **Expression** column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9bb6c-119">Si l'expression n'est pas valide, son texte est mis en surbrillance et une info-bulle dans la colonne décrit les erreurs.</span><span class="sxs-lookup"><span data-stu-id="9bb6c-119">If the expression is not valid, the expression text is highlighted and a ToolTip on the column describes the errors.</span></span>  
  
7.  <span data-ttu-id="9bb6c-120">Dans la liste **Colonne dérivée**, sélectionnez **\<add as new column>** pour écrire le résultat d’évaluation de l’expression dans une nouvelle colonne ou sélectionnez une colonne existante à mettre à jour avec le résultat de l’évaluation.</span><span class="sxs-lookup"><span data-stu-id="9bb6c-120">In the **Derived Column** list, select **\<add as new column>** to write the evaluation result of the expression to a new column, or select an existing column to update with the evaluation result.</span></span>  
  
     <span data-ttu-id="9bb6c-121">Si vous choisissez d’utiliser une nouvelle colonne, la boîte de dialogue **Éditeur de transformation de colonne dérivée** évalue l’expression et affecte un type de données à la colonne en fonction du type de données, de la longueur, de la précision, de l’échelle et de la page de codes.</span><span class="sxs-lookup"><span data-stu-id="9bb6c-121">If you chose to use a new column, the **Derived Column Transformation Editor** dialog box evaluates the expression and assigns a data type to the column, depending on the data type, length, precisions, scale, and code page.</span></span>  
  
8.  <span data-ttu-id="9bb6c-122">Si vous utilisez une nouvelle colonne, sélectionnez un type de données dans la liste **Type de données** .</span><span class="sxs-lookup"><span data-stu-id="9bb6c-122">If using a new column, select a data type in the **Data Type** list.</span></span> <span data-ttu-id="9bb6c-123">En fonction du type de données sélectionné et si vous le souhaitez, mettez à jour les valeurs des colonnes **Longueur**, **Précision**, **Échelle**et **Page de codes** .</span><span class="sxs-lookup"><span data-stu-id="9bb6c-123">Depending on the selected data type, optionally update the values in the **Length**, **Precision**, **Scale**, and **Code Page** columns.</span></span> <span data-ttu-id="9bb6c-124">Les métadonnées des colonnes existantes ne peuvent pas être modifiées.</span><span class="sxs-lookup"><span data-stu-id="9bb6c-124">Metadata of existing columns cannot be changed.</span></span>  
  
9. <span data-ttu-id="9bb6c-125">Si vous le souhaitez, modifiez les valeurs de la colonne **Nom de la colonne dérivée** .</span><span class="sxs-lookup"><span data-stu-id="9bb6c-125">Optionally, modify the values in the **Derived Column Name** column.</span></span>  
  
10. <span data-ttu-id="9bb6c-126">Pour configurer la sortie d’erreur, cliquez sur **Configurer la sortie d’erreur**.</span><span class="sxs-lookup"><span data-stu-id="9bb6c-126">To configure the error output, click **Configure Error Output**.</span></span> <span data-ttu-id="9bb6c-127">Pour plus d’informations, consultez [Configurer une sortie d’erreur dans un composant de flux de données](../../configure-an-error-output-in-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="9bb6c-127">For more information, see [Configure an Error Output in a Data Flow Component](../../configure-an-error-output-in-a-data-flow-component.md).</span></span>  
  
11. <span data-ttu-id="9bb6c-128">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="9bb6c-128">Click **OK**.</span></span>  
  
12. <span data-ttu-id="9bb6c-129">Pour enregistrer le package mis à jour, cliquez sur **Enregistrer les éléments sélectionnés** dans le menu **Fichier** .</span><span class="sxs-lookup"><span data-stu-id="9bb6c-129">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bb6c-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9bb6c-130">See Also</span></span>  
 <span data-ttu-id="9bb6c-131">[Derived Column Transformation](derived-column-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="9bb6c-131">[Derived Column Transformation](derived-column-transformation.md) </span></span>  
 <span data-ttu-id="9bb6c-132">[Types de données d’Integration Services](../integration-services-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="9bb6c-132">[Integration Services Data Types](../integration-services-data-types.md) </span></span>  
 <span data-ttu-id="9bb6c-133">[Transformations Integration Services](integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="9bb6c-133">[Integration Services Transformations](integration-services-transformations.md) </span></span>  
 <span data-ttu-id="9bb6c-134">[Chemins Integration Services](../integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="9bb6c-134">[Integration Services Paths](../integration-services-paths.md) </span></span>  
 <span data-ttu-id="9bb6c-135">[Tâche de flux de données](../../control-flow/data-flow-task.md) </span><span class="sxs-lookup"><span data-stu-id="9bb6c-135">[Data Flow Task](../../control-flow/data-flow-task.md) </span></span>  
 [<span data-ttu-id="9bb6c-136">Expressions Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="9bb6c-136">Integration Services &#40;SSIS&#41; Expressions</span></span>](../../expressions/integration-services-ssis-expressions.md)  
  
  
