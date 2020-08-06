---
title: Définir des formules de membre personnalisées | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- members [Analysis Services], custom
- custom rollup formulas [Analysis Services]
- MDX [Analysis Services], custom rollup formulas
- custom member formulas [Analysis Services]
ms.assetid: 258304e2-d900-4013-97e3-871f51dfdce2
author: minewiskan
ms.author: owend
ms.openlocfilehash: 51649bea0c4134971b342b779c778b857343e62b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708803"
---
# <a name="define-custom-member-formulas"></a><span data-ttu-id="56518-102">Définir des formules de membre personnalisées</span><span class="sxs-lookup"><span data-stu-id="56518-102">Define Custom Member Formulas</span></span>
  <span data-ttu-id="56518-103">Vous pouvez définir une expression MDX (Multidimensional Expressions) appelée formule de membre personnalisée pour fournir les valeurs des membres d'un attribut spécifié.</span><span class="sxs-lookup"><span data-stu-id="56518-103">You can define a Multidimensional Expressions (MDX) expression, called a custom member formula, to supply the values for the members of a specified attribute.</span></span> <span data-ttu-id="56518-104">Une colonne d'une table issue d'une vue de source de données fournit, pour chaque membre d'un attribut, l'expression utilisée pour fournir la valeur de ce membre.</span><span class="sxs-lookup"><span data-stu-id="56518-104">A column in a table from a data source view provides, for each member in an attribute, the expression used to supply the value for that member.</span></span>  
  
 <span data-ttu-id="56518-105">Les formules de membre personnalisées déterminent les valeurs de cellule associées aux membres et ont priorité sur les fonctions d'agrégation des mesures.</span><span class="sxs-lookup"><span data-stu-id="56518-105">Custom member formulas determine the cell values that are associated with members and override the aggregate functions of measures.</span></span> <span data-ttu-id="56518-106">Les formules de membres personnalisées sont écrites dans MDX.</span><span class="sxs-lookup"><span data-stu-id="56518-106">Custom member formulas are written in MDX.</span></span> <span data-ttu-id="56518-107">Chaque formule de membre personnalisée s'applique à un seul membre.</span><span class="sxs-lookup"><span data-stu-id="56518-107">Each custom member formula applies to a single member.</span></span> <span data-ttu-id="56518-108">Les formules de membre personnalisées sont stockées dans la table de dimension ou dans une autre table qui entretient une relation de clé étrangère avec la table de dimension.</span><span class="sxs-lookup"><span data-stu-id="56518-108">Custom member formulas are stored in the dimension table or in another table that has a foreign key relationship with the dimension table.</span></span>  
  
 <span data-ttu-id="56518-109">La propriété `CustomRollupColumn` d'un attribut spécifie la colonne qui contient les formules de membre personnalisées pour les membres de l'attribut.</span><span class="sxs-lookup"><span data-stu-id="56518-109">The `CustomRollupColumn` property on an attribute specifies the column that contains custom member formulas for members of the attribute.</span></span> <span data-ttu-id="56518-110">Si une ligne de la colonne est vide, la valeur de la cellule pour le membre est retournée normalement.</span><span class="sxs-lookup"><span data-stu-id="56518-110">If a row in the column is empty, the cell value for the member is returned normally.</span></span> <span data-ttu-id="56518-111">Si la formule figurant dans la colonne n'est pas valide, une erreur se produit au moment de l'exécution chaque fois qu'une valeur de cellule utilisant le membre est extraite.</span><span class="sxs-lookup"><span data-stu-id="56518-111">If the formula in the column is not valid, a run-time error occurs whenever a cell value that uses the member is retrieved.</span></span>  
  
 <span data-ttu-id="56518-112">Avant de spécifier des formules de membre personnalisées pour un attribut, assurez-vous que la table de dimension contenant l'attribut, ou une table qui lui est directement associée, contient une colonne de chaîne pour stocker les formules de membre personnalisées.</span><span class="sxs-lookup"><span data-stu-id="56518-112">Before you can specify custom member formulas for an attribute, make sure that the dimension table that contains the attribute, or a directly related table, has a string column to store the custom member formulas.</span></span> <span data-ttu-id="56518-113">Si c’est le cas, vous pouvez soit définir `CustomRollupColumn` manuellement la propriété sur un attribut, soit utiliser l’amélioration définir la formule de membre personnalisée de l’Assistant Business Intelligence pour activer une formule de membre personnalisée sur un attribut.</span><span class="sxs-lookup"><span data-stu-id="56518-113">If this is the case, you can either set the `CustomRollupColumn` property on an attribute manually or use the Set Custom Member Formula enhancement of the Business Intelligence Wizard to enable a custom member formula on an attribute.</span></span> <span data-ttu-id="56518-114">Pour plus d’informations sur la façon d’utiliser cette amélioration, consultez [Définir des formules de membre personnalisées pour les attributs d’une dimension](bi-wizard-custom-member-formulas-for-attributes-in-a-dimension.md).</span><span class="sxs-lookup"><span data-stu-id="56518-114">For more information about how to use this enhancement, see [Set Custom Member Formulas for Attributes in a Dimension](bi-wizard-custom-member-formulas-for-attributes-in-a-dimension.md).</span></span>  
  
## <a name="evaluating-custom-member-formulas"></a><span data-ttu-id="56518-115">Évaluation des formules de membre personnalisées</span><span class="sxs-lookup"><span data-stu-id="56518-115">Evaluating Custom Member Formulas</span></span>  
 <span data-ttu-id="56518-116">Les formules de membre personnalisées sont différentes des membres calculés.</span><span class="sxs-lookup"><span data-stu-id="56518-116">Custom member formulas differ from calculated members.</span></span> <span data-ttu-id="56518-117">Les formules de membre personnalisées s'appliquent à des membres qui existent dans des tables de dimension et fournissent seulement la valeur du membre.</span><span class="sxs-lookup"><span data-stu-id="56518-117">Custom member formulas apply to members that exist in dimension tables, and only provide the value of the member.</span></span> <span data-ttu-id="56518-118">Pour leur part, les membres calculés ne sont pas stockés dans des tables de dimension, et les expressions de membre calculé définissent les données et les métadonnées de membres supplémentaires inclus dans une dimension ou une hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="56518-118">In contrast, calculated members are not stored in dimension tables, and calculated member expressions define both data and metadata for additional members included in a dimension or hierarchy.</span></span>  
  
 <span data-ttu-id="56518-119">Les formules de membre personnalisées ont priorité sur les fonctions d'agrégation associées à des mesures.</span><span class="sxs-lookup"><span data-stu-id="56518-119">Custom member formulas override the aggregate functions associated with measures.</span></span> <span data-ttu-id="56518-120">Par exemple, supposons qu'une mesure utilisant la fonction d'agrégation `Sum` présente, avant la spécification d'une formule de membre personnalisée, les valeurs ci-après pour les membres de la dimension Time :</span><span class="sxs-lookup"><span data-stu-id="56518-120">For example, before a custom member formula is specified, a measure using the `Sum` aggregate function has the following values for the following members of the Time dimension:</span></span>  
  
-   <span data-ttu-id="56518-121">2003: 2100</span><span class="sxs-lookup"><span data-stu-id="56518-121">2003: 2100</span></span>  
  
    -   <span data-ttu-id="56518-122">Quarter 1: 700</span><span class="sxs-lookup"><span data-stu-id="56518-122">Quarter 1: 700</span></span>  
  
    -   <span data-ttu-id="56518-123">Quarter 2: 500</span><span class="sxs-lookup"><span data-stu-id="56518-123">Quarter 2: 500</span></span>  
  
    -   <span data-ttu-id="56518-124">Quarter 3: 100</span><span class="sxs-lookup"><span data-stu-id="56518-124">Quarter 3: 100</span></span>  
  
    -   <span data-ttu-id="56518-125">Quarter 4: 800</span><span class="sxs-lookup"><span data-stu-id="56518-125">Quarter 4: 800</span></span>  
  
-   <span data-ttu-id="56518-126">2004: 1500</span><span class="sxs-lookup"><span data-stu-id="56518-126">2004: 1500</span></span>  
  
    -   <span data-ttu-id="56518-127">Quarter 1: 600</span><span class="sxs-lookup"><span data-stu-id="56518-127">Quarter 1: 600</span></span>  
  
    -   <span data-ttu-id="56518-128">Quarter 2: 200</span><span class="sxs-lookup"><span data-stu-id="56518-128">Quarter 2: 200</span></span>  
  
    -   <span data-ttu-id="56518-129">Quarter 3: 300</span><span class="sxs-lookup"><span data-stu-id="56518-129">Quarter 3: 300</span></span>  
  
    -   <span data-ttu-id="56518-130">Quarter 4 : 400</span><span class="sxs-lookup"><span data-stu-id="56518-130">Quarter 4: 400</span></span>  
  
 <span data-ttu-id="56518-131">Avec une formule de membre personnalisée, la valeur du membre est fournie par la formule de cumul personnalisée.</span><span class="sxs-lookup"><span data-stu-id="56518-131">With a custom member formula, the value of the member is instead supplied by the custom rollup formula.</span></span> <span data-ttu-id="56518-132">Par exemple, la formule de membre personnalisée suivante permet de fournir 450 comme valeur du membre Quarter 4 enfant du membre 2004 dans la dimension Time.</span><span class="sxs-lookup"><span data-stu-id="56518-132">For example, the following custom member formula can be used to supply the value for the Quarter 4 child member of the 2004 member in the Time dimension as 450.</span></span>  
  
```  
Time.[Quarter 3] * 1.5  
```  
  
 <span data-ttu-id="56518-133">Les formules de membre personnalisées sont stockées dans une colonne de la table de dimension.</span><span class="sxs-lookup"><span data-stu-id="56518-133">Custom member formulas are stored in a column of the dimension table.</span></span> <span data-ttu-id="56518-134">Vous activez les formules de cumul personnalisées en définissant la propriété `CustomRollupColumn` d'un attribut.</span><span class="sxs-lookup"><span data-stu-id="56518-134">You enable custom rollup formulas by setting the `CustomRollupColumn` property on an attribute.</span></span>  
  
 <span data-ttu-id="56518-135">Pour appliquer une seule expression MDX à tous les membres d'un attribut, créez sur la table de dimension un calcul nommé qui retourne une expression MDX sous forme de chaîne littérale.</span><span class="sxs-lookup"><span data-stu-id="56518-135">To apply a single MDX expression to all members of an attribute, create a named calculation on the dimension table that returns an MDX expression as a literal string.</span></span> <span data-ttu-id="56518-136">Ensuite, spécifiez le calcul nommé avec la valeur de la propriété `CustomRollupColumn` de l'attribut que vous voulez configurer.</span><span class="sxs-lookup"><span data-stu-id="56518-136">Then, specify the named calculation with the `CustomRollupColumn` property setting on the attribute that you want to configure.</span></span> <span data-ttu-id="56518-137">Un calcul nommé est une colonne d'une table de vue de source de données qui retourne des valeurs de ligne définies par une expression SQL.</span><span class="sxs-lookup"><span data-stu-id="56518-137">A named calculation is a column in a data source view table that returns row values defined by a SQL expression.</span></span> <span data-ttu-id="56518-138">Pour plus d’informations sur la construction de calculs nommés, consultez [Définir des calculs nommés dans une vue de source de données &#40;Analysis Services&#41;](define-named-calculations-in-a-data-source-view-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="56518-138">For more information about constructing named calculations, see [Define Named Calculations in a Data Source View &#40;Analysis Services&#41;](define-named-calculations-in-a-data-source-view-analysis-services.md)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="56518-139">Pour appliquer une expression MDX aux membres d'un niveau particulier d'un attribut au lieu de l'appliquer aux membres de tous les niveaux, vous pouvez la définir comme script MDX sur le niveau concerné.</span><span class="sxs-lookup"><span data-stu-id="56518-139">To apply an MDX expression to members of a particular level instead of to members of all levels based on a particular attribute, you can define the expression as an MDX script on the level.</span></span> <span data-ttu-id="56518-140">Pour plus d’informations, consultez [Principes de base des scripts MDX &#40;Analysis Services&#41;](mdx/mdx-scripting-fundamentals-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="56518-140">For more information, see [MDX Scripting Fundamentals &#40;Analysis Services&#41;](mdx/mdx-scripting-fundamentals-analysis-services.md).</span></span>  
  
 <span data-ttu-id="56518-141">Si vous utilisez des membres calculés ainsi que des formules de cumul personnalisées pour les membres d'un attribut, vous devez être conscient de l'ordre d'évaluation.</span><span class="sxs-lookup"><span data-stu-id="56518-141">If you use both calculated members and custom rollup formulas for members of an attribute, you should be aware of the order of evaluation.</span></span> <span data-ttu-id="56518-142">Les membres calculés sont résolus avant les formules de cumul personnalisées.</span><span class="sxs-lookup"><span data-stu-id="56518-142">Calculated members are resolved before custom rollup formulas are resolved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56518-143">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="56518-143">See Also</span></span>  
 <span data-ttu-id="56518-144">[Attributs et hiérarchies d’attributs](../multidimensional-models-olap-logical-dimension-objects/attributes-and-attribute-hierarchies.md) </span><span class="sxs-lookup"><span data-stu-id="56518-144">[Attributes and Attribute Hierarchies](../multidimensional-models-olap-logical-dimension-objects/attributes-and-attribute-hierarchies.md) </span></span>  
 [<span data-ttu-id="56518-145">Définir des formules de membre personnalisées pour les attributs d’une dimension</span><span class="sxs-lookup"><span data-stu-id="56518-145">Set Custom Member Formulas for Attributes in a Dimension</span></span>](bi-wizard-custom-member-formulas-for-attributes-in-a-dimension.md)  
  
  
