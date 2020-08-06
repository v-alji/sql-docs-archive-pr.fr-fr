---
title: Créer des requêtes Update (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- tables [SQL Server], updating
- queries [SQL Server], types
- Update query
- updating tables
ms.assetid: 178b7b75-8078-4e61-b2a8-4719b9d8033d
author: stevestein
ms.author: sstein
ms.openlocfilehash: bbea575d544875dba73de923474cc11bbcb46a9b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610944"
---
# <a name="create-update-queries-visual-database-tools"></a><span data-ttu-id="14069-102">Créer des requêtes Update (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="14069-102">Create Update Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="14069-103">Vous pouvez modifier le contenu de plusieurs lignes en une seule opération à l'aide d'une requête Update.</span><span class="sxs-lookup"><span data-stu-id="14069-103">You can change the contents of multiple rows in one operation by using an Update query.</span></span> <span data-ttu-id="14069-104">Dans une table `titles` par exemple, vous pouvez recourir à une requête Update pour augmenter de 10% le prix de tous les livres d'un éditeur donné.</span><span class="sxs-lookup"><span data-stu-id="14069-104">For example, in a `titles` table you can use an Update query to add 10% to the price of all books for a particular publisher.</span></span>  
  
 <span data-ttu-id="14069-105">Lorsque vous créez une requête Update, spécifiez :</span><span class="sxs-lookup"><span data-stu-id="14069-105">When you create an Update query, you specify:</span></span>  
  
-   <span data-ttu-id="14069-106">la table à mettre à jour ;</span><span class="sxs-lookup"><span data-stu-id="14069-106">The table to update.</span></span>  
  
-   <span data-ttu-id="14069-107">les colonnes dont vous voulez mettre à jour le contenu ;</span><span class="sxs-lookup"><span data-stu-id="14069-107">The columns whose contents you want to update.</span></span>  
  
-   <span data-ttu-id="14069-108">la valeur ou l'expression utilisée pour mettre à jour les colonnes individuelles ;</span><span class="sxs-lookup"><span data-stu-id="14069-108">The value or expression to use to update the individual columns.</span></span>  
  
-   <span data-ttu-id="14069-109">les conditions de recherche afin de définir les lignes à mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="14069-109">Search conditions to define the rows you want to update.</span></span>  
  
 <span data-ttu-id="14069-110">À titre d'exemple, la requête suivante met à jour la table `titles` en augmentant de 10% le prix de tous les titres d'un éditeur :</span><span class="sxs-lookup"><span data-stu-id="14069-110">For example, the following query updates the `titles` table by adding 10% to the price of all titles for one publisher:</span></span>  
  
```  
UPDATE titles  
SET price = price * 1.1  
WHERE (pub_id = '0766')  
```  
  
> [!CAUTION]  
>  <span data-ttu-id="14069-111">Il est impossible d'annuler l'action entraînée par l'exécution d'une requête Update.</span><span class="sxs-lookup"><span data-stu-id="14069-111">You cannot undo the action of executing an Update query.</span></span> <span data-ttu-id="14069-112">Par sécurité, sauvegardez vos données avant d'exécuter la requête.</span><span class="sxs-lookup"><span data-stu-id="14069-112">As a precaution, back up your data before executing the query.</span></span>  
  
### <a name="to-create-an-update-query"></a><span data-ttu-id="14069-113">Pour créer une requête Update</span><span class="sxs-lookup"><span data-stu-id="14069-113">To create an Update query</span></span>  
  
1.  <span data-ttu-id="14069-114">Ajoutez la table à mettre à jour dans le volet Schéma.</span><span class="sxs-lookup"><span data-stu-id="14069-114">Add the table you want to update to the Diagram pane.</span></span>  
  
2.  <span data-ttu-id="14069-115">Dans le menu **Concepteur de requêtes** , pointez sur **Modifier le type**, puis cliquez sur **Mettre à jour**.</span><span class="sxs-lookup"><span data-stu-id="14069-115">From the **Query Designer** menu point to **Change Type**, and then click **Update**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="14069-116">Si plusieurs tables apparaissent dans le volet Schéma quand vous commencez la requête Update, le Concepteur de requêtes et de vues affiche la boîte de dialogue [Choisir la table cible pour Insert Values](visual-database-tools.md) qui vous invite à indiquer le nom de la table à mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="14069-116">If more than one table is displayed in the Diagram pane when you start the Update query, the Query and View Designer displays the [Choose Target Table for Insert Values Dialog Box](visual-database-tools.md) to prompt you for the name of the table to update.</span></span>  
  
3.  <span data-ttu-id="14069-117">Dans le volet Schéma, cliquez sur la case à cocher en regard de chaque colonne pour laquelle vous souhaitez fournir de nouvelles valeurs.</span><span class="sxs-lookup"><span data-stu-id="14069-117">In the Diagram pane, click the check box for each column for which you want to supply new values.</span></span> <span data-ttu-id="14069-118">Ces colonnes s'affichent dans le volet Critères.</span><span class="sxs-lookup"><span data-stu-id="14069-118">Those columns will show in the Criteria pane.</span></span> <span data-ttu-id="14069-119">Les colonnes ne seront mises à jour que si vous les ajoutez à la requête.</span><span class="sxs-lookup"><span data-stu-id="14069-119">Columns will be updated only if you add them to the query.</span></span>  
  
4.  <span data-ttu-id="14069-120">Dans la colonne **Nouvelle valeur** du volet Critères, entrez la valeur mise à jour de la colonne.</span><span class="sxs-lookup"><span data-stu-id="14069-120">In the **New Value** column of the Criteria pane, enter the update value for the column.</span></span> <span data-ttu-id="14069-121">Vous pouvez entrer des valeurs littérales, des noms de colonnes ou des expressions.</span><span class="sxs-lookup"><span data-stu-id="14069-121">You can enter literal values, column names, or expressions.</span></span> <span data-ttu-id="14069-122">La valeur doit correspondre (ou être compatible) au type de données de la colonne mise à jour.</span><span class="sxs-lookup"><span data-stu-id="14069-122">The value must match (or be compatible with) the data type of the column you are updating.</span></span>  
  
    > [!CAUTION]  
    >  <span data-ttu-id="14069-123">Le Concepteur de requêtes et de vues ne peut pas vérifier si une valeur est adaptée à la longueur de la colonne que vous mettez à jour.</span><span class="sxs-lookup"><span data-stu-id="14069-123">The Query and View Designer cannot check that a value fits within the length of the column you are updating.</span></span> <span data-ttu-id="14069-124">Si la valeur est trop longue, elle est susceptible d'être tronquée sans avertissement.</span><span class="sxs-lookup"><span data-stu-id="14069-124">If you provide a value that is too long, it might be truncated without warning.</span></span> <span data-ttu-id="14069-125">Par exemple, si une colonne `name` possède 20 caractères mais que vous spécifiez une valeur de mise à jour de 25 caractères, les derniers 5 caractères risquent d'être tronqués.</span><span class="sxs-lookup"><span data-stu-id="14069-125">For example, if a `name` column is 20 characters long but you specify an update value of 25 characters, the last 5 characters might be truncated.</span></span>  
  
5.  <span data-ttu-id="14069-126">Définissez les lignes à mettre à jour en entrant des conditions de recherche dans la colonne **Filtre**.</span><span class="sxs-lookup"><span data-stu-id="14069-126">Define the rows to update by entering search conditions in the **Filter** column.</span></span> <span data-ttu-id="14069-127">Pour plus d’informations, consultez [Spécifier des critères de recherche &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="14069-127">For details, see [Specify Search Criteria &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md).</span></span>  
  
     <span data-ttu-id="14069-128">Si vous ne spécifiez pas de condition de recherche, toutes les lignes de la table spécifiée sont mises à jour.</span><span class="sxs-lookup"><span data-stu-id="14069-128">If you do not specify a search condition, all rows in the specified table will be updated.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="14069-129">Quand vous ajoutez une colonne dans le volet Critères afin de l'utiliser dans une condition de recherche, le Concepteur de requêtes et de vues l'ajoute aussi à la liste des colonnes à mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="14069-129">When you add a column to the Criteria pane for use in a search condition, the Query and View Designer also adds it to the list of columns to be updated.</span></span> <span data-ttu-id="14069-130">Si vous souhaitez utiliser une colonne dans une condition de recherche sans toutefois la mettre à jour, désactivez la case à cocher en regard du nom de la colonne dans le rectangle représentant la table ou l'objet table.</span><span class="sxs-lookup"><span data-stu-id="14069-130">If you want to use a column for a search condition but not update it, clear the check box next to the column name in the rectangle representing the table or table-valued object.</span></span>  
  
 <span data-ttu-id="14069-131">Quand vous exécutez une requête Update, aucun résultat n’apparaît dans le [volet Résultats](results-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="14069-131">When you execute an Update query, no results are reported in the [Results Pane](results-pane-visual-database-tools.md).</span></span> <span data-ttu-id="14069-132">En fait, un message indiquant le nombre de lignes modifiées s'affiche.</span><span class="sxs-lookup"><span data-stu-id="14069-132">Instead, a message appears indicating how many rows were changed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14069-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="14069-133">See Also</span></span>  
 <span data-ttu-id="14069-134">[Types de requêtes pris en charge &#40;Visual Database Tools&#41;](supported-query-types-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="14069-134">[Supported Query Types &#40;Visual Database Tools&#41;](supported-query-types-visual-database-tools.md) </span></span>  
 <span data-ttu-id="14069-135">[Rubriques de procédures relatives à la conception de requêtes et de vues &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="14069-135">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="14069-136">Effectuer des opérations de base concernant les requêtes &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="14069-136">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
