---
title: Utilisation d’écritures différées de cube (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- writeback [Analysis Services], cubes
- cubes [Analysis Services], modifying
- modifying cubes
- UPDATE CUBE statement
- cubes [Analysis Services], writeback
ms.assetid: ae2385fc-7fa0-4f8e-98d7-dcb0a5f0eeea
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3ac43e9206619117c1fc090a594ca32ccbeeeb31
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604185"
---
# <a name="using-cube-writebacks-mdx"></a><span data-ttu-id="24021-102">Utilisation de l'écriture différée de cubes (MDX)</span><span class="sxs-lookup"><span data-stu-id="24021-102">Using Cube Writebacks (MDX)</span></span>
  <span data-ttu-id="24021-103">Pour mettre à jour un cube, vous pouvez utiliser l’instruction [UPDATE CUBE](/sql/mdx/mdx-data-manipulation-update-cube) .</span><span class="sxs-lookup"><span data-stu-id="24021-103">You update a cube by using the [UPDATE CUBE](/sql/mdx/mdx-data-manipulation-update-cube) statement.</span></span> <span data-ttu-id="24021-104">Celle-ci permet de mettre à jour un tuple avec une valeur spécifique.</span><span class="sxs-lookup"><span data-stu-id="24021-104">This statement lets you update a tuple with a specific value.</span></span> <span data-ttu-id="24021-105">Pour utiliser efficacement l'instruction UPDATE CUBE afin de mettre à jour un cube, vous devez comprendre la syntaxe de l'instruction, les conditions d'erreur susceptibles de se produire, ainsi que les effets potentiels des mises à jour sur un cube.</span><span class="sxs-lookup"><span data-stu-id="24021-105">To effectively use the UPDATE CUBE statement to update a cube, you have to understand the syntax for the statement, the error conditions that can occur, and the affect that updates can have on a cube.</span></span>  
  
## <a name="update-cube-statement-syntax"></a><span data-ttu-id="24021-106">Syntaxe de l'instruction UPDATE CUBE</span><span class="sxs-lookup"><span data-stu-id="24021-106">UPDATE CUBE Statement Syntax</span></span>  
 <span data-ttu-id="24021-107">La syntaxe suivante décrit l'instruction UPDATE CUBE :</span><span class="sxs-lookup"><span data-stu-id="24021-107">The following syntax describes the UPDATE CUBE statement:</span></span>  
  
```  
UPDATE [CUBE] <Cube_Name> SET <tuple>.VALUE = <value> [,<tuple>.VALUE = <value>...]  
 [ USE_EQUAL_ALLOCATION | USE_EQUAL_INCREMENT |  
  USE_WEIGHTED_ALLOCATION [BY <weight value_expression>] |  
  USE_WEIGHTED_INCREMENT [BY <weight value_expression>] ]   
```  
  
 <span data-ttu-id="24021-108">Si un jeu complet de coordonnées n'est pas spécifié pour le tuple, les coordonnées non spécifiées utilisent le membre par défaut de la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="24021-108">If a full set of coordinates is not specified for the tuple, the unspecified coordinates will use the default member of the hierarchy.</span></span> <span data-ttu-id="24021-109">Le tuple identifié doit faire référence à une cellule agrégée avec la fonction [Sum](/sql/mdx/sum-mdx) , et ne doit pas utiliser de membre calculé comme l’une des coordonnées de la cellule.</span><span class="sxs-lookup"><span data-stu-id="24021-109">The tuple identified must reference a cell that is aggregated with the [Sum](/sql/mdx/sum-mdx) function, and must not use a calculated member as one of the cell's coordinates.</span></span>  
  
 <span data-ttu-id="24021-110">Vous pouvez considérer l'instruction UPDATE CUBE comme une sous-routine générant une série d'opérations d'écriture différée isolées sur des cellules atomiques.</span><span class="sxs-lookup"><span data-stu-id="24021-110">You can think of the UPDATE CUBE statement as a subroutine that generates a series of individual writeback operations to atomic cells.</span></span> <span data-ttu-id="24021-111">Toutes ces opérations d'écriture différée sont ensuite regroupées dans la somme spécifiée.</span><span class="sxs-lookup"><span data-stu-id="24021-111">All these individual writeback operations then roll up into the specified sum.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="24021-112">Lorsque les cellules mises à jour ne se chevauchent pas, la propriété de chaîne de connexion `Update Isolation Level` peut être utilisée pour améliorer les performances pour UPDATE CUBE.</span><span class="sxs-lookup"><span data-stu-id="24021-112">When updated cells do not overlap, the `Update Isolation Level` connection string property can be used to enhance performance for UPDATE CUBE.</span></span> <span data-ttu-id="24021-113">Pour plus d'informations, consultez <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection.ConnectionString%2A>.</span><span class="sxs-lookup"><span data-stu-id="24021-113">For more information, see <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection.ConnectionString%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="24021-114">Exemple</span><span class="sxs-lookup"><span data-stu-id="24021-114">Example</span></span>  
 <span data-ttu-id="24021-115">Pour tester l'instruction UPDATE CUBE, utilisez le groupe de mesures Cibles de ventes dans le cube Adventure Works.</span><span class="sxs-lookup"><span data-stu-id="24021-115">You can test UPDATE CUBE using the Sales Targets measure group in the Adventure Works cube.</span></span> <span data-ttu-id="24021-116">Ce groupe de mesures est constitué de mesures regroupées par SUM, qui est une condition requise pour l'instruction UPDATE CUBE.</span><span class="sxs-lookup"><span data-stu-id="24021-116">This measure group consists of measures aggregated by SUM, which is a requirement for UPDATE CUBE.</span></span>  
  
1.  <span data-ttu-id="24021-117">Activez l'écriture différée pour le groupe de mesures Cibles de ventes dans la base de données Adventure Works.</span><span class="sxs-lookup"><span data-stu-id="24021-117">Enable writeback for the Sales Targets measure group in the Adventure Works database.</span></span> <span data-ttu-id="24021-118">Dans Management Studio, cliquez avec le bouton droit sur un groupe de mesures, pointez sur **Options d’écriture différée**et sélectionnez **Activer l’écriture différée**.</span><span class="sxs-lookup"><span data-stu-id="24021-118">In Management Studio, right-click a measure group, point to **Write Back Options**, choose **Enable Writeback**.</span></span>  
  
     <span data-ttu-id="24021-119">Une nouvelle table d'écriture différée doit s'afficher dans le dossier d'écriture différée.</span><span class="sxs-lookup"><span data-stu-id="24021-119">You should see a new writeback table in the Writeback folder.</span></span> <span data-ttu-id="24021-120">Le nom de table est WriteTable_Fact Sales Quota.</span><span class="sxs-lookup"><span data-stu-id="24021-120">The table name is WriteTable_Fact Sales Quota.</span></span>  
  
2.  <span data-ttu-id="24021-121">Ouvrez une fenêtre de requête MDX.</span><span class="sxs-lookup"><span data-stu-id="24021-121">Open an MDX query window.</span></span> <span data-ttu-id="24021-122">Exécutez l'instruction SELECT ci-dessous pour afficher la valeur d'origine :</span><span class="sxs-lookup"><span data-stu-id="24021-122">Run the following select statement to view the original value:</span></span>  
  
    ```  
    SELECT [Measures].[Sales Amount Quota] on 0 ,  
    [Employee].[Employee Department].[Title].&[Sales Representative].children on 1  
    FROM [Adventure Works]  
  
    ```  
  
     <span data-ttu-id="24021-123">Les quotas sur le montant des ventes doivent s'afficher pour chaque représentant.</span><span class="sxs-lookup"><span data-stu-id="24021-123">You should see sales amount quotas for each representative.</span></span>  
  
3.  <span data-ttu-id="24021-124">Exécutez l'instruction UPDATE CUBE pour l'écriture différée d'une nouvelle valeur.</span><span class="sxs-lookup"><span data-stu-id="24021-124">Run the update cube statement to write back a new value.</span></span> <span data-ttu-id="24021-125">Dans cet exemple, nous définissons le quota du montant des ventes à 0.</span><span class="sxs-lookup"><span data-stu-id="24021-125">In this example, we are setting the sales amount quota to 0.</span></span> <span data-ttu-id="24021-126">Dans la mesure où la nouvelle valeur est 0, ne spécifiez pas de méthode d'allocation.</span><span class="sxs-lookup"><span data-stu-id="24021-126">Because the new value is 0, do not specify an allocation method.</span></span>  
  
    ```  
    UPDATE CUBE [Adventure Works]   
    SET ([Measures].[Sales Amount Quota], [Employee].[Employee Department].[Department].&[Sales]) = 0  
  
    ```  
  
4.  <span data-ttu-id="24021-127">Réexécutez l'instruction SELECT.</span><span class="sxs-lookup"><span data-stu-id="24021-127">Re-run the SELECT statement.</span></span> <span data-ttu-id="24021-128">Zéro doit s'afficher pour les quotas.</span><span class="sxs-lookup"><span data-stu-id="24021-128">You should now see zero for the quotas.</span></span>  
  
 <span data-ttu-id="24021-129">La valeur d'écriture différée est contrainte à la session active.</span><span class="sxs-lookup"><span data-stu-id="24021-129">The writeback value is constrained to the current session.</span></span> <span data-ttu-id="24021-130">Pour rendre la valeur persistante entre les utilisateurs et les sessions, traitez la table d'écriture différée.</span><span class="sxs-lookup"><span data-stu-id="24021-130">To persist the value across users and sessions, process the writeback table.</span></span> <span data-ttu-id="24021-131">Dans Management Studio, cliquez avec le bouton droit sur WriteTable_Fact Sales Quota et sélectionnez **Traiter**.</span><span class="sxs-lookup"><span data-stu-id="24021-131">In Management Studio, right-click WriteTable_Fact Sales Quota and choose **Process**.</span></span>  
  
 <span data-ttu-id="24021-132">Pour spécifier une méthode d'allocation, la nouvelle valeur doit être supérieure à zéro.</span><span class="sxs-lookup"><span data-stu-id="24021-132">To specify an allocation method, the new value must be greater than zero.</span></span> <span data-ttu-id="24021-133">Dans cet exemple, la nouvelle valeur du quota du montant des ventes est de deux millions et la méthode d'allocation distribue le montant à tous les représentants.</span><span class="sxs-lookup"><span data-stu-id="24021-133">In this example, the new value for Sales Amount Quota is two million and the allocation method distributes the amount across all sales representatives.</span></span>  
  
```  
UPDATE CUBE [Adventure Works]   
SET ([Measures].[Sales Amount Quota], [Employee].[Employee Department].[Department].&[Sales]) = 2000000   
USE_EQUAL_ALLOCATION  
```  
  
## <a name="error-conditions"></a><span data-ttu-id="24021-134">Conditions d'erreur</span><span class="sxs-lookup"><span data-stu-id="24021-134">Error Conditions</span></span>  
 <span data-ttu-id="24021-135">Le tableau suivant décrit à la fois les éléments pouvant entraîner l'échec d'écritures différées et le résultat de ces erreurs.</span><span class="sxs-lookup"><span data-stu-id="24021-135">The following table describes both what can cause writebacks to fail and the result of those errors.</span></span>  
  
|<span data-ttu-id="24021-136">Condition d'erreur</span><span class="sxs-lookup"><span data-stu-id="24021-136">Error Condition</span></span>|<span data-ttu-id="24021-137">Résultats</span><span class="sxs-lookup"><span data-stu-id="24021-137">Result</span></span>|  
|---------------------|------------|  
|<span data-ttu-id="24021-138">La mise à jour comprend les membres de la même dimension qui n'existent pas l'un avec l'autre.</span><span class="sxs-lookup"><span data-stu-id="24021-138">Update includes members from the same dimension that do not exist with one another.</span></span>|<span data-ttu-id="24021-139">La mise à jour échoue.</span><span class="sxs-lookup"><span data-stu-id="24021-139">Update will fail.</span></span> <span data-ttu-id="24021-140">L'espace du cube ne contient pas la cellule référencée.</span><span class="sxs-lookup"><span data-stu-id="24021-140">The cube space will not contain the referenced cell.</span></span>|  
|<span data-ttu-id="24021-141">La mise à jour comprend une mesure provenant d'une mesure de type non signé.</span><span class="sxs-lookup"><span data-stu-id="24021-141">Update includes a measure sourced to a measure of an unsigned type.</span></span>|<span data-ttu-id="24021-142">La mise à jour échoue.</span><span class="sxs-lookup"><span data-stu-id="24021-142">Update will fail.</span></span> <span data-ttu-id="24021-143">Les incréments exigent que la mesure puisse accepter une valeur négative.</span><span class="sxs-lookup"><span data-stu-id="24021-143">Increments require that the measure be able to take a negative value.</span></span>|  
|<span data-ttu-id="24021-144">La mise à jour comprend une mesure d'agrégation de type autre que somme.</span><span class="sxs-lookup"><span data-stu-id="24021-144">Update includes a measure that aggregates other than sum.</span></span>|<span data-ttu-id="24021-145">Une erreur est générée.</span><span class="sxs-lookup"><span data-stu-id="24021-145">An error is raised.</span></span>|  
|<span data-ttu-id="24021-146">Vous avez tenté d'exécuter la mesure sur un sous-cube.</span><span class="sxs-lookup"><span data-stu-id="24021-146">Update was tried on a subcube.</span></span>|<span data-ttu-id="24021-147">Une erreur est générée.</span><span class="sxs-lookup"><span data-stu-id="24021-147">An error is raised.</span></span>|  
  
## <a name="affect-of-cube-changes"></a><span data-ttu-id="24021-148">Effets des modifications apportées au cube</span><span class="sxs-lookup"><span data-stu-id="24021-148">Affect of Cube Changes</span></span>  
 <span data-ttu-id="24021-149">Les modifications suivantes n'ont aucun effet sur une écriture différée :</span><span class="sxs-lookup"><span data-stu-id="24021-149">The following changes will not have an effect on a writeback:</span></span>  
  
-   <span data-ttu-id="24021-150">traitement d'un cube, de ses groupes de mesures du cube ou de ses dimensions ;</span><span class="sxs-lookup"><span data-stu-id="24021-150">Processing of a cube, the cube's measure groups, or the cube's dimensions.</span></span>  
  
-   <span data-ttu-id="24021-151">ajout d'attributs à une dimension quelconque ;</span><span class="sxs-lookup"><span data-stu-id="24021-151">Adding attributes to any dimension.</span></span>  
  
-   <span data-ttu-id="24021-152">ajoute d'une nouvelle dimension ;</span><span class="sxs-lookup"><span data-stu-id="24021-152">Adding a new dimension.</span></span>  
  
-   <span data-ttu-id="24021-153">suppression d'une dimension qui ne comprend pas l'écriture différée ;</span><span class="sxs-lookup"><span data-stu-id="24021-153">Deleting a dimension that does not include the writeback.</span></span>  
  
-   <span data-ttu-id="24021-154">ajout, modification ou suppression d'une hiérarchie ;</span><span class="sxs-lookup"><span data-stu-id="24021-154">Adding, modifying, or removing a hierarchy.</span></span>  
  
-   <span data-ttu-id="24021-155">ajout d'une nouvelle mesure.</span><span class="sxs-lookup"><span data-stu-id="24021-155">Adding a new measure.</span></span>  
  
 <span data-ttu-id="24021-156">Les modifications suivantes ne peuvent pas être effectuées sans supprimer les données en écriture différée :</span><span class="sxs-lookup"><span data-stu-id="24021-156">The following changes cannot be made without removing the writeback data:</span></span>  
  
-   <span data-ttu-id="24021-157">suppression d'un attribut, de sa hiérarchie d'attribut, s'il est compris dans l'écriture différée.</span><span class="sxs-lookup"><span data-stu-id="24021-157">Deleting an attribute, or its attribute hierarchy, if the attribute is included in the writeback.</span></span> <span data-ttu-id="24021-158">Cela inclut la suppression explicite de l'attribut, ou de sa hiérarchie d'attribut, ou encore la suppression de la dimension parente de l'attribut ;</span><span class="sxs-lookup"><span data-stu-id="24021-158">This includes explicitly removing the attribute, or its attribute hierarchy, or removing the attribute's parent dimension.</span></span>  
  
-   <span data-ttu-id="24021-159">suppression d'une mesure comprise dans l'écriture différée ;</span><span class="sxs-lookup"><span data-stu-id="24021-159">Deleting a measure included in the writeback.</span></span>  
  
-   <span data-ttu-id="24021-160">ajout d'un attribut dépourvu de niveau `(All)` à une dimension comprise dans l'écriture différée ;</span><span class="sxs-lookup"><span data-stu-id="24021-160">Adding an attribute without an `(All)` level to a dimension included in the writeback.</span></span>  
  
-   <span data-ttu-id="24021-161">modification de la granularité d'une dimension comprise dans l'écriture différée.</span><span class="sxs-lookup"><span data-stu-id="24021-161">Changing the dimension granularity for a dimension included in the writeback.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24021-162">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="24021-162">See Also</span></span>  
 [<span data-ttu-id="24021-163">Modification de données &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="24021-163">Modifying Data &#40;MDX&#41;</span></span>](mdx-data-modification-modifying-data.md)  
  
  
