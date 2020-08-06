---
title: Colonne dérivée, transformation | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.derivedcolumntrans.f1
helpviewer_keywords:
- multiple derived columns
- expressions [Integration Services], derived columns
- derived columns
- columns [Integration Services], derivations
- Derived Column transformation
ms.assetid: 8eba755e-8e48-4233-bd1e-09a46bf2692f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7bbdc46f2e67b1b859fcfa446c584373cfbeca0d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601016"
---
# <a name="derived-column-transformation"></a><span data-ttu-id="f8177-102">Transformation de colonne dérivée</span><span class="sxs-lookup"><span data-stu-id="f8177-102">Derived Column Transformation</span></span>
  <span data-ttu-id="f8177-103">La transformation de colonne dérivée crée de nouvelles valeurs de colonne en appliquant des expressions aux colonnes d'entrée de transformation.</span><span class="sxs-lookup"><span data-stu-id="f8177-103">The Derived Column transformation creates new column values by applying expressions to transformation input columns.</span></span> <span data-ttu-id="f8177-104">Une expression peut contenir toute combinaison de variables, de fonctions, d'opérateurs et de colonnes provenant de l'entrée de transformation.</span><span class="sxs-lookup"><span data-stu-id="f8177-104">An expression can contain any combination of variables, functions, operators, and columns from the transformation input.</span></span> <span data-ttu-id="f8177-105">Le résultat peut être ajouté en tant que nouvelle colonne ou inséré dans une colonne existante en tant que valeur de remplacement.</span><span class="sxs-lookup"><span data-stu-id="f8177-105">The result can be added as a new column or inserted into an existing column as a replacement value.</span></span> <span data-ttu-id="f8177-106">La transformation de colonne dérivée peut définir plusieurs colonnes dérivées, et toute variable ou colonne d'entrée peut apparaître dans plusieurs expressions.</span><span class="sxs-lookup"><span data-stu-id="f8177-106">The Derived Column transformation can define multiple derived columns, and any variable or input columns can appear in multiple expressions.</span></span>  
  
 <span data-ttu-id="f8177-107">Vous pouvez utiliser cette transformation pour réaliser les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="f8177-107">You can use this transformation to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="f8177-108">concaténer des données à partir de différentes colonnes en une colonne dérivée.</span><span class="sxs-lookup"><span data-stu-id="f8177-108">Concatenate data from different columns into a derived column.</span></span> <span data-ttu-id="f8177-109">Par exemple, vous pouvez combiner les valeurs des colonnes **FirstName** et **LastName** en une colonne dérivée unique nommée **FullName**à l’aide de l’expression `FirstName + " " + LastName`.</span><span class="sxs-lookup"><span data-stu-id="f8177-109">For example, you can combine values from the **FirstName** and **LastName** columns into a single derived column named **FullName**, by using the expression `FirstName + " " + LastName`.</span></span>  
  
-   <span data-ttu-id="f8177-110">extraire des caractères de données de chaîne à l'aide de fonctions telles que SUBSTRING, puis stocker le résultat dans une colonne dérivée.</span><span class="sxs-lookup"><span data-stu-id="f8177-110">Extract characters from string data by using functions such as SUBSTRING, and then store the result in a derived column.</span></span> <span data-ttu-id="f8177-111">Par exemple, vous pouvez extraire de la colonne **FirstName** l’initiale d’une personne à l’aide de l’expression `SUBSTRING(FirstName,1,1)`.</span><span class="sxs-lookup"><span data-stu-id="f8177-111">For example, you can extract a person's initial from the **FirstName** column, by using the expression `SUBSTRING(FirstName,1,1)`.</span></span>  
  
-   <span data-ttu-id="f8177-112">appliquer des fonctions mathématiques à des données numériques et stocker le résultat dans une colonne dérivée.</span><span class="sxs-lookup"><span data-stu-id="f8177-112">Apply mathematical functions to numeric data and store the result in a derived column.</span></span> <span data-ttu-id="f8177-113">Par exemple, vous pouvez modifier la longueur et la précision d’une colonne numérique, **SalesTax**, en un nombre à deux décimales à l’aide de l’expression `ROUND(SalesTax, 2)`.</span><span class="sxs-lookup"><span data-stu-id="f8177-113">For example, you can change the length and precision of a numeric column, **SalesTax**, to a number with two decimal places, by using the expression `ROUND(SalesTax, 2)`.</span></span>  
  
-   <span data-ttu-id="f8177-114">créer des expressions qui comparent les colonnes d'entrée et les variables.</span><span class="sxs-lookup"><span data-stu-id="f8177-114">Create expressions that compare input columns and variables.</span></span> <span data-ttu-id="f8177-115">Par exemple, vous pouvez comparer la variable **Version** aux données de la colonne **ProductVersion**et, suivant le résultat de la comparaison, utiliser la valeur de **Version** ou de **ProductVersion**, à l’aide de l’expression `ProductVersion == @Version? ProductVersion : @Version`.</span><span class="sxs-lookup"><span data-stu-id="f8177-115">For example, you can compare the variable **Version** against the data in the column **ProductVersion**, and depending on the comparison result, use the value of either **Version** or **ProductVersion**, by using the expression `ProductVersion == @Version? ProductVersion : @Version`.</span></span>  
  
-   <span data-ttu-id="f8177-116">extraire des parties d'une valeur de date et d'heure.</span><span class="sxs-lookup"><span data-stu-id="f8177-116">Extract parts of a datetime value.</span></span> <span data-ttu-id="f8177-117">Par exemple, vous pouvez utiliser les fonctions GETDATE et DATEPART pour extraire l’année actuelle à l’aide de l’expression `DATEPART("year",GETDATE())`.</span><span class="sxs-lookup"><span data-stu-id="f8177-117">For example, you can use the GETDATE and DATEPART functions to extract the current year, by using the expression `DATEPART("year",GETDATE())`.</span></span>  
  
-   <span data-ttu-id="f8177-118">convertir des chaînes de date dans un format spécifique en utilisant une expression.</span><span class="sxs-lookup"><span data-stu-id="f8177-118">Convert date strings to a specific format using an expression.</span></span>  
  
## <a name="configuration-of-the-derived-column-transformation"></a><span data-ttu-id="f8177-119">Configuration de la transformation de colonne dérivée</span><span class="sxs-lookup"><span data-stu-id="f8177-119">Configuration of the Derived Column Transformation</span></span>  
 <span data-ttu-id="f8177-120">Vous pouvez configurer la transformation de colonne dérivée comme suit :</span><span class="sxs-lookup"><span data-stu-id="f8177-120">You can configure the Derived column transformation in the following ways:</span></span>  
  
-   <span data-ttu-id="f8177-121">Indiquez une expression pour chaque colonne d'entrée ou pour chaque nouvelle colonne à modifier.</span><span class="sxs-lookup"><span data-stu-id="f8177-121">Provide an expression for each input column or new column that will be changed.</span></span> <span data-ttu-id="f8177-122">Pour plus d’informations, consultez [Expressions Integration Services &#40;SSIS&#41;](../../expressions/integration-services-ssis-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="f8177-122">For more information, see [Integration Services &#40;SSIS&#41; Expressions](../../expressions/integration-services-ssis-expressions.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f8177-123">Si une expression référence une colonne d'entrée remplacée par la transformation de colonne dérivée, cette expression utilise la valeur d'origine de la colonne au lieu de la valeur dérivée.</span><span class="sxs-lookup"><span data-stu-id="f8177-123">If an expression references an input column that is overwritten by the Derived Column transformation, the expression uses the original value of the column, not the derived value.</span></span>  
  
-   <span data-ttu-id="f8177-124">Si les résultats sont insérés dans de nouvelles colonnes et que le type de données est `string`, spécifiez une page de codes.</span><span class="sxs-lookup"><span data-stu-id="f8177-124">If adding results to new columns and the data type is `string`, specify a code page.</span></span> <span data-ttu-id="f8177-125">Pour plus d'informations, voir [Comparing String Data](../comparing-string-data.md).</span><span class="sxs-lookup"><span data-stu-id="f8177-125">For more information, see [Comparing String Data](../comparing-string-data.md).</span></span>  
  
 <span data-ttu-id="f8177-126">La transformation de colonne dérivée inclut la propriété personnalisée FriendlyExpression.</span><span class="sxs-lookup"><span data-stu-id="f8177-126">The Derived Column transformation includes the FriendlyExpression custom property.</span></span> <span data-ttu-id="f8177-127">La propriété peut être mise à jour par une expression de propriété lors du chargement du package.</span><span class="sxs-lookup"><span data-stu-id="f8177-127">This property can be updated by a property expression when the package is loaded.</span></span> <span data-ttu-id="f8177-128">Pour plus d’informations, consultez [Expressions de propriété dans des packages](../../expressions/use-property-expressions-in-packages.md)et [Propriétés personnalisées des transformation](transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="f8177-128">For more information, see [Use Property Expressions in Packages](../../expressions/use-property-expressions-in-packages.md), and [Transformation Custom Properties](transformation-custom-properties.md).</span></span>  
  
 <span data-ttu-id="f8177-129">Cette transformation a une entrée, une sortie standard et une sortie d'erreur.</span><span class="sxs-lookup"><span data-stu-id="f8177-129">This transformation has one input, one regular output, and one error output.</span></span>  
  
 <span data-ttu-id="f8177-130">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] ou par programmation.</span><span class="sxs-lookup"><span data-stu-id="f8177-130">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="f8177-131">Pour plus d’informations sur les propriétés définissables dans la boîte de dialogue **Éditeur de transformation de colonne dérivée** , consultez [Éditeur de transformation de colonne dérivée](../../derived-column-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="f8177-131">For more information about the properties that you can set in the **Derived Column Transformation Editor** dialog box, see [Derived Column Transformation Editor](../../derived-column-transformation-editor.md).</span></span>  
  
 <span data-ttu-id="f8177-132">La boîte de dialogue **Éditeur avancé** reflète les propriétés qui peuvent être définies par programmation.</span><span class="sxs-lookup"><span data-stu-id="f8177-132">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="f8177-133">Pour plus d'informations sur les propriétés définissables dans la boîte de dialogue **Éditeur avancé** ou par programmation, cliquez sur l'une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="f8177-133">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="f8177-134">Propriétés communes</span><span class="sxs-lookup"><span data-stu-id="f8177-134">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="f8177-135">Propriétés personnalisées des transformations</span><span class="sxs-lookup"><span data-stu-id="f8177-135">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
 <span data-ttu-id="f8177-136">Pour plus d'informations sur la définition des propriétés, cliquez sur l'une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="f8177-136">For more information about how to set properties, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="f8177-137">Définir les propriétés d’un composant de flux de données</span><span class="sxs-lookup"><span data-stu-id="f8177-137">Set the Properties of a Data Flow Component</span></span>](../set-the-properties-of-a-data-flow-component.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="f8177-138">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="f8177-138">Related Tasks</span></span>  
  
-   [<span data-ttu-id="f8177-139">Dériver les valeurs de colonnes à l'aide de la transformation de colonne dérivée</span><span class="sxs-lookup"><span data-stu-id="f8177-139">Derive Column Values by Using the Derived Column Transformation</span></span>](derived-column-transformation.md)  
  
## <a name="related-content"></a><span data-ttu-id="f8177-140">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="f8177-140">Related Content</span></span>  
 <span data-ttu-id="f8177-141">Article technique, [SSIS Expression Examples](https://go.microsoft.com/fwlink/?LinkId=220761), sur social.technet.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="f8177-141">Technical article, [SSIS Expression Examples](https://go.microsoft.com/fwlink/?LinkId=220761), on social.technet.microsoft.com</span></span>  
  
 <span data-ttu-id="f8177-142">Blog, [comment fractionner des données de colonne à l’aide de SSIS](https://microsoft-ssis.blogspot.com/2012/10/split-multi-value-column-into-multiple.html).</span><span class="sxs-lookup"><span data-stu-id="f8177-142">Blog, [How to Split Column Data using SSIS](https://microsoft-ssis.blogspot.com/2012/10/split-multi-value-column-into-multiple.html).</span></span>  
  
  
