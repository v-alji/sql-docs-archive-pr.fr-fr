---
title: Créer des requêtes Insert Values (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- inserting values
- queries [SQL Server], types
- adding values
- row additions [SQL Server], Insert Values query
- inserting rows
- Insert Values query
- adding rows
- table values [SQL Server]
ms.assetid: 2d4b2f6d-cc09-434b-8a0e-ccce40628064
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2fc71b0148ee8a7e92c517fe75b56c329b3c88f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699113"
---
# <a name="create-insert-values-queries-visual-database-tools"></a><span data-ttu-id="9af63-102">Créer des requêtes Insert Values (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="9af63-102">Create Insert Values Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="9af63-103">Vous pouvez créer une nouvelle ligne dans la table active à l'aide d'une requête Insert Values.</span><span class="sxs-lookup"><span data-stu-id="9af63-103">You can create a new row in the current table using an Insert Values query.</span></span> <span data-ttu-id="9af63-104">Lorsque vous créez une requête Insert Values, spécifiez :</span><span class="sxs-lookup"><span data-stu-id="9af63-104">When you create an Insert Values query, you specify:</span></span>  
  
-   <span data-ttu-id="9af63-105">la table de base de données à laquelle ajouter la ligne ;</span><span class="sxs-lookup"><span data-stu-id="9af63-105">The database table to add the row to.</span></span>  
  
-   <span data-ttu-id="9af63-106">les colonnes dont vous souhaitez ajouter le contenu ;</span><span class="sxs-lookup"><span data-stu-id="9af63-106">The columns whose contents you want to add.</span></span>  
  
-   <span data-ttu-id="9af63-107">la valeur ou l'expression à insérer dans les colonnes individuelles.</span><span class="sxs-lookup"><span data-stu-id="9af63-107">The value or expression to insert into the individual columns.</span></span>  
  
 <span data-ttu-id="9af63-108">Dans l'exemple ci-dessous, la requête ajoute une ligne à la table `titles` , précisant des valeurs pour le titre, le type, l'éditeur et le prix :</span><span class="sxs-lookup"><span data-stu-id="9af63-108">For example, the following query adds a row to the `titles` table, specifying values for the title, type, publisher, and price:</span></span>  
  
```  
INSERT INTO titles  
         (title_id, title, type, pub_id, price)  
VALUES   ('BU9876', 'Creating Web Pages', 'business', '1389', '29.99')  
```  
  
 <span data-ttu-id="9af63-109">Lorsque vous créez une requête Insert Values, le volet Critères change afin de refléter les seules options d'insertion d'une nouvelle ligne disponibles : le nom de la colonne et la valeur à insérer.</span><span class="sxs-lookup"><span data-stu-id="9af63-109">When you create an Insert Values query, the Criteria pane changes to reflect the only options available for inserting a new row: the column name and the value to insert.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="9af63-110">Il est impossible d'annuler l'action entraînée par l'exécution d'une requête Insert Values.</span><span class="sxs-lookup"><span data-stu-id="9af63-110">You cannot undo the action of executing an Insert Values query.</span></span> <span data-ttu-id="9af63-111">Par sécurité, sauvegardez vos données avant d'exécuter la requête.</span><span class="sxs-lookup"><span data-stu-id="9af63-111">As a precaution, back up your data before executing the query.</span></span>  
  
### <a name="to-create-an-insert-values-query"></a><span data-ttu-id="9af63-112">Pour créer une requête Insert Values</span><span class="sxs-lookup"><span data-stu-id="9af63-112">To create an Insert Values query</span></span>  
  
1.  <span data-ttu-id="9af63-113">Ajoutez la table à mettre à jour dans le volet Schéma.</span><span class="sxs-lookup"><span data-stu-id="9af63-113">Add the table you want to update to the Diagram pane.</span></span>  
  
2.  <span data-ttu-id="9af63-114">Dans le menu **Concepteur de requêtes** , pointez sur **Modifier le type**, puis cliquez sur **Insérer les valeurs**.</span><span class="sxs-lookup"><span data-stu-id="9af63-114">From the **Query Designer** menu point to **Change Type**, and then click **Insert Values**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9af63-115">Si plusieurs tables apparaissent dans le volet Schéma quand vous commencez la requête Insert Values, le Concepteur de requêtes et de vues affiche la boîte de dialogue [Choisir la table cible pour Insert Values](visual-database-tools.md) qui vous invite à indiquer le nom de la table à mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="9af63-115">If more than one table is displayed in the Diagram pane when you start the Insert Values query, the Query and View Designer displays the [Choose Target Table for Insert Values Dialog Box](visual-database-tools.md) to prompt you for the name of the table to update.</span></span>  
  
3.  <span data-ttu-id="9af63-116">Dans le volet Schéma, cliquez sur la case à cocher en regard de chaque colonne pour laquelle vous souhaitez fournir de nouvelles valeurs.</span><span class="sxs-lookup"><span data-stu-id="9af63-116">In the Diagram pane, click the check box for each column for which you want to supply new values.</span></span> <span data-ttu-id="9af63-117">Ces colonnes s'affichent dans le volet Critères.</span><span class="sxs-lookup"><span data-stu-id="9af63-117">Those columns will show in the Criteria pane.</span></span> <span data-ttu-id="9af63-118">Les colonnes ne seront mises à jour que si vous les ajoutez à la requête.</span><span class="sxs-lookup"><span data-stu-id="9af63-118">Columns will be updated only if you add them to the query.</span></span>  
  
4.  <span data-ttu-id="9af63-119">Dans la colonne **Nouvelle valeur** du volet Critères, entrez la nouvelle valeur pour la colonne.</span><span class="sxs-lookup"><span data-stu-id="9af63-119">In the **New Value** column of the Criteria pane, enter the new value for the column.</span></span> <span data-ttu-id="9af63-120">Vous pouvez entrer des valeurs littérales, des noms de colonnes ou des expressions.</span><span class="sxs-lookup"><span data-stu-id="9af63-120">You can enter literal values, column names, or expressions.</span></span> <span data-ttu-id="9af63-121">La valeur doit correspondre (ou être compatible) au type de données de la colonne mise à jour.</span><span class="sxs-lookup"><span data-stu-id="9af63-121">The value must match (or be compatible with) the data type of the column you are updating.</span></span>  
  
    > [!CAUTION]  
    >  <span data-ttu-id="9af63-122">Le Concepteur de requêtes et de vues ne peut pas vérifier si une valeur est adaptée à la longueur de la colonne que vous insérez.</span><span class="sxs-lookup"><span data-stu-id="9af63-122">The Query and View Designer cannot check that a value fits within the length of the column you are inserting.</span></span> <span data-ttu-id="9af63-123">Si la valeur est trop longue, elle est susceptible d'être tronquée sans avertissement.</span><span class="sxs-lookup"><span data-stu-id="9af63-123">If you provide a value that is too long, it might be truncated without warning.</span></span> <span data-ttu-id="9af63-124">Par exemple, si une colonne `name` possède 20 caractères mais que vous spécifiez une valeur à insérer de 25 caractères, les 5 derniers caractères risquent d'être tronqués.</span><span class="sxs-lookup"><span data-stu-id="9af63-124">For example, if a `name` column is 20 characters long but you specify an insert value of 25 characters, the last 5 characters might be truncated.</span></span>  
  
 <span data-ttu-id="9af63-125">Quand vous exécutez une requête Insert Values, aucun résultat n’apparaît dans le [volet Résultats](results-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9af63-125">When you execute an Insert Values query, no results are reported in the [Results Pane](results-pane-visual-database-tools.md).</span></span> <span data-ttu-id="9af63-126">En fait, un message indiquant le nombre de lignes modifiées s'affiche.</span><span class="sxs-lookup"><span data-stu-id="9af63-126">Instead, a message appears indicating how many rows were changed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9af63-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9af63-127">See Also</span></span>  
 <span data-ttu-id="9af63-128">[Types de requêtes pris en charge &#40;Visual Database Tools&#41;](supported-query-types-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="9af63-128">[Supported Query Types &#40;Visual Database Tools&#41;](supported-query-types-visual-database-tools.md) </span></span>  
 <span data-ttu-id="9af63-129">[Rubriques de procédures relatives à la conception de requêtes et de vues &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="9af63-129">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="9af63-130">Effectuer des opérations de base concernant les requêtes &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="9af63-130">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
