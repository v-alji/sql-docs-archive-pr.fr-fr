---
title: Créer manuellement des jointures réflexives (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- self-joins
- manual joins [SQL Server]
- joins [SQL Server], self
ms.assetid: 910ed516-cb84-481b-95d0-cba3e89afdba
author: stevestein
ms.author: sstein
ms.openlocfilehash: 31e125fdfe0f7f285ea679cfe85356d1aa10353a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610949"
---
# <a name="create-self-joins-manually-visual-database-tools"></a><span data-ttu-id="f3515-102">Créer manuellement des jointures réflexives (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="f3515-102">Create Self-Joins Manually (Visual Database Tools)</span></span>
  <span data-ttu-id="f3515-103">Vous pouvez joindre une table à elle-même, même si elle ne possède pas de relation réflexive dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="f3515-103">You can join a table to itself even if the table does not have a reflexive relationship in the database.</span></span> <span data-ttu-id="f3515-104">Vous pouvez, par exemple, utiliser une jointure réflexive pour trouver des paires d'auteurs vivant dans la même ville.</span><span class="sxs-lookup"><span data-stu-id="f3515-104">For example, you can use a self-join to find pairs of authors living in the same city.</span></span>  
  
 <span data-ttu-id="f3515-105">À l'instar de toute autre jointure, une jointure réflexive nécessite au moins deux tables.</span><span class="sxs-lookup"><span data-stu-id="f3515-105">As with any join, a self-join requires at least two tables.</span></span> <span data-ttu-id="f3515-106">En revanche, elle diffère des autres jointures par le fait que vous ajoutez une seconde instance de la même table plutôt qu'une autre table à la requête.</span><span class="sxs-lookup"><span data-stu-id="f3515-106">The difference is that, instead of adding a second table to the query, you add a second instance of the same table.</span></span> <span data-ttu-id="f3515-107">Ainsi, vous pouvez comparer une colonne de la première instance de la table à la même colonne de la seconde, ce qui vous permet de comparer les valeurs d'une même colonne.</span><span class="sxs-lookup"><span data-stu-id="f3515-107">That way, you can compare a column in the first instance of the table to the same column in the second instance, which allows you to compare the values in a column to each other.</span></span> <span data-ttu-id="f3515-108">Le [Concepteur de requêtes et de vues](visual-database-tools.md) assigne un alias à la seconde instance de la table.</span><span class="sxs-lookup"><span data-stu-id="f3515-108">The [Query and View Designer](visual-database-tools.md) assigns an alias to the second instance of the table.</span></span>  
  
 <span data-ttu-id="f3515-109">Par exemple, si vous créez une jointure réflexive pour trouver toutes les paires d'auteurs résidant à Berkeley, comparez la colonne `city` de la première instance de la table à la colonne `city` de la seconde instance.</span><span class="sxs-lookup"><span data-stu-id="f3515-109">For example, if you are creating a self-join to find all pairs of authors within Berkeley, you compare the `city` column in the first instance of the table against the `city` column in the second instance.</span></span> <span data-ttu-id="f3515-110">La requête obtenue peut se présenter comme suit :</span><span class="sxs-lookup"><span data-stu-id="f3515-110">The resulting query might look like the following:</span></span>  
  
```  
SELECT   
      authors.au_fname,   
      authors.au_lname,   
      authors1.au_fname AS Expr2,   
      authors1.au_lname AS Expr3  
   FROM   
      authors   
         INNER JOIN  
         authors authors1   
            ON authors.city   
             = authors1.city  
   WHERE  
      authors.city = 'Berkeley'  
```  
  
 <span data-ttu-id="f3515-111">La création d'une jointure réflexive exige souvent plusieurs conditions de jointure.</span><span class="sxs-lookup"><span data-stu-id="f3515-111">Creating a self-join often requires multiple join conditions.</span></span> <span data-ttu-id="f3515-112">Pour en comprendre les raisons, observez le résultat de la requête précédente :</span><span class="sxs-lookup"><span data-stu-id="f3515-112">To understand why, consider the result of the preceding query:</span></span>  
  
```  
Cheryl Carson       Cheryl Carson  
Abraham Bennet      Abraham Bennet  
Cheryl Carson       Abraham Bennet  
Abraham Bennet      Cheryl Carson  
```  
  
 <span data-ttu-id="f3515-113">La première ligne est sans importance, elle indique que Cheryl Carson vit dans la même ville que Cheryl Carson.</span><span class="sxs-lookup"><span data-stu-id="f3515-113">The first row is useless; it indicates that Cheryl Carson lives in the same city as Cheryl Carson.</span></span> <span data-ttu-id="f3515-114">La deuxième est tout aussi inutile.</span><span class="sxs-lookup"><span data-stu-id="f3515-114">The second row is equally useless.</span></span> <span data-ttu-id="f3515-115">Pour éliminer les données inutiles, ajoutez une autre condition afin de ne conserver que les lignes de résultats affichant des noms d'auteur différents.</span><span class="sxs-lookup"><span data-stu-id="f3515-115">To eliminate this useless data, you add another condition retaining only those result rows in which the two author names describe different authors.</span></span> <span data-ttu-id="f3515-116">La requête obtenue peut se présenter comme suit :</span><span class="sxs-lookup"><span data-stu-id="f3515-116">The resulting query might look like this:</span></span>  
  
```  
SELECT   
      authors.au_fname,   
      authors.au_lname,   
      authors1.au_fname AS Expr2,   
      authors1.au_lname AS Expr3  
   FROM   
      authors   
         INNER JOIN  
         authors authors1   
            ON authors.city   
             = authors1.city  
            AND authors.au_id  
             <> authors1.au_id  
   WHERE  
      authors.city = 'Berkeley'  
```  
  
 <span data-ttu-id="f3515-117">Le jeu de résultats est affiné :</span><span class="sxs-lookup"><span data-stu-id="f3515-117">The result set is improved:</span></span>  
  
```  
Cheryl Carson       Abraham Bennet  
Abraham Bennet      Cheryl Carson  
```  
  
 <span data-ttu-id="f3515-118">Néanmoins, les deux lignes de résultats sont redondantes.</span><span class="sxs-lookup"><span data-stu-id="f3515-118">But the two result rows are redundant.</span></span> <span data-ttu-id="f3515-119">La première indique que Carson vit dans la même ville que Bennet et la seconde que Bennet vit dans la même ville que Carson.</span><span class="sxs-lookup"><span data-stu-id="f3515-119">The first says Carson lives in the same city as Bennet, and the second says the Bennet lives in the same city as Carson.</span></span> <span data-ttu-id="f3515-120">Pour éliminer cette redondance, vous pouvez remplacer la seconde condition de jointure « différent de » par « inférieur à ».</span><span class="sxs-lookup"><span data-stu-id="f3515-120">To eliminate this redundancy, you can alter the second join condition from "not equals" to "less than."</span></span> <span data-ttu-id="f3515-121">La requête obtenue peut se présenter comme suit :</span><span class="sxs-lookup"><span data-stu-id="f3515-121">The resulting query might look like this:</span></span>  
  
```  
SELECT   
      authors.au_fname,   
      authors.au_lname,   
      authors1.au_fname AS Expr2,   
      authors1.au_lname AS Expr3  
   FROM   
      authors   
         INNER JOIN  
         authors authors1   
            ON authors.city   
             = authors1.city  
            AND authors.au_id  
             < authors1.au_id  
   WHERE  
      authors.city = 'Berkeley'  
```  
  
 <span data-ttu-id="f3515-122">Le jeu de résultats ressemble alors à ceci :</span><span class="sxs-lookup"><span data-stu-id="f3515-122">And the result set looks like this:</span></span>  
  
```  
Cheryl Carson       Abraham Bennet  
```  
  
### <a name="to-create-a-self-join-manually"></a><span data-ttu-id="f3515-123">Pour créer manuellement une jointure réflexive</span><span class="sxs-lookup"><span data-stu-id="f3515-123">To create a self-join manually</span></span>  
  
1.  <span data-ttu-id="f3515-124">Ajoutez au [volet Schéma](diagram-pane-visual-database-tools.md) la table ou l’objet table que vous souhaitez utiliser.</span><span class="sxs-lookup"><span data-stu-id="f3515-124">Add to the [Diagram pane](diagram-pane-visual-database-tools.md) the table or table-valued object you want to work with.</span></span>  
  
2.  <span data-ttu-id="f3515-125">Ajoutez de nouveau la même table, afin que le volet Schéma affiche deux fois la même table ou le même objet table.</span><span class="sxs-lookup"><span data-stu-id="f3515-125">Add the same table again, so that the Diagram pane shows the same table or table-valued object twice within the Diagram pane.</span></span>  
  
     <span data-ttu-id="f3515-126">Le Concepteur de requêtes et de vues assigne un alias à la seconde instance en ajoutant un numéro séquentiel au nom de la table.</span><span class="sxs-lookup"><span data-stu-id="f3515-126">The Query and View Designer assigns an alias to the second instance by adding a sequential number to the table name.</span></span> <span data-ttu-id="f3515-127">Par ailleurs, il crée une ligne de jointure entre les deux occurrences de la table ou l'objet table dans le volet Schéma.</span><span class="sxs-lookup"><span data-stu-id="f3515-127">In addition, the Query and View Designer creates a join line between the two occurrences of the table or table-valued object within the Diagram pane.</span></span>  
  
3.  <span data-ttu-id="f3515-128">Cliquez avec le bouton droit sur la ligne de jointure et cliquez sur **Propriétés** dans le menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="f3515-128">Right-click the join line and choose **Properties** from the shortcut menu.</span></span>  
  
4.  <span data-ttu-id="f3515-129">Dans la fenêtre Propriétés, cliquez sur **Condition et type de jointure**, puis cliquez sur le bouton de sélection **(…)** , à droite de la propriété.</span><span class="sxs-lookup"><span data-stu-id="f3515-129">In the Properties window click **Join Condition and Type** and click the **ellipses (...)** to the right of the property.</span></span>  
  
5.  <span data-ttu-id="f3515-130">Dans la [boîte de dialogue Joindre](join-dialog-box-visual-database-tools.md) , modifiez éventuellement l’opérateur de comparaison entre les clés primaires.</span><span class="sxs-lookup"><span data-stu-id="f3515-130">In the [Join Dialog Box](join-dialog-box-visual-database-tools.md) change the comparison operator between the primary keys as required.</span></span> <span data-ttu-id="f3515-131">Indiquez par exemple l'opérateur inférieur à (<).</span><span class="sxs-lookup"><span data-stu-id="f3515-131">For example, you might change the operator to less than (<).</span></span>  
  
6.  <span data-ttu-id="f3515-132">Créez la condition de jointure supplémentaire (par exemple, authors.zip = authors1.zip) en faisant glisser le nom de la colonne de jointure primaire figurant dans la première occurrence de la table ou de l'objet table jusqu'à la colonne correspondante de la seconde occurrence.</span><span class="sxs-lookup"><span data-stu-id="f3515-132">Create the additional join condition (for example, authors.zip = authors1.zip) by dragging the name of the primary join column in the first occurrence of the table or table-valued object and dropping it on the corresponding column in the second occurrence.</span></span>  
  
7.  <span data-ttu-id="f3515-133">Spécifiez d'autres options de requête comme les colonnes de sortie, les conditions de recherche et l'ordre de tri.</span><span class="sxs-lookup"><span data-stu-id="f3515-133">Specify other options for the query such as output columns, search conditions, and sort order.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3515-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f3515-134">See Also</span></span>  
 <span data-ttu-id="f3515-135">[Créer automatiquement des jointures réflexives &#40;Visual Database Tools&#41;](create-self-joins-automatically-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="f3515-135">[Create Self-Joins Automatically &#40;Visual Database Tools&#41;](create-self-joins-automatically-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="f3515-136">Interroger avec des jointures &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="f3515-136">Query with Joins &#40;Visual Database Tools&#41;</span></span>](query-with-joins-visual-database-tools.md)  
  
  
