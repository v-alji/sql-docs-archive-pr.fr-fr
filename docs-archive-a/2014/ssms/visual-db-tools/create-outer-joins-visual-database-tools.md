---
title: Créer des jointures externes (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- outer joins
- joins [SQL Server], outer
ms.assetid: 18de47b1-f936-427d-b852-fe6d20334f71
author: stevestein
ms.author: sstein
ms.openlocfilehash: f02c0be049e2e75e1a657bb3c027d20430d562cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708888"
---
# <a name="create-outer-joins-visual-database-tools"></a><span data-ttu-id="62e3d-102">Créer des jointures externes (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="62e3d-102">Create Outer Joins (Visual Database Tools)</span></span>
  <span data-ttu-id="62e3d-103">Par défaut, le [Concepteur de requêtes et de vues](visual-database-tools.md) crée une jointure interne entre des tables.</span><span class="sxs-lookup"><span data-stu-id="62e3d-103">By default, the [Query and View Designer](visual-database-tools.md) creates an inner join between tables.</span></span> <span data-ttu-id="62e3d-104">Les jointures internes éliminent les lignes qui ne correspondent pas à une ligne de l'autre table.</span><span class="sxs-lookup"><span data-stu-id="62e3d-104">Inner joins eliminate the rows that do not match with a row from the other table.</span></span> <span data-ttu-id="62e3d-105">Quant aux jointures externes, elles retournent toutes les lignes d'au moins une des tables ou vues mentionnées dans la clause FROM, pour autant que ces lignes répondent à une des conditions de recherche WHERE ou HAVING.</span><span class="sxs-lookup"><span data-stu-id="62e3d-105">Outer joins, however, return all rows from at least one of the tables or views mentioned in the FROM clause, as long as those rows meet any WHERE or HAVING search conditions.</span></span> <span data-ttu-id="62e3d-106">Pour inclure, dans l'ensemble de résultats, des lignes de données qui n'ont pas de correspondances dans la table jointe, vous pouvez créer une jointure externe.</span><span class="sxs-lookup"><span data-stu-id="62e3d-106">If you want to include data rows in the result set that do not have a match in the joined table, you can create an outer join.</span></span>  
  
 <span data-ttu-id="62e3d-107">Lorsque vous créez une jointure externe, l'ordre d'affichage des tables dans l'instruction SQL (c.-à-d. telles qu'elles apparaissent dans le volet SQL) est important.</span><span class="sxs-lookup"><span data-stu-id="62e3d-107">When you create an outer join, the order in which tables appear in the SQL statement (as reflected in the SQL pane) is significant.</span></span> <span data-ttu-id="62e3d-108">La première table que vous ajoutez devient la table « de gauche » et la seconde la table « de droite ».</span><span class="sxs-lookup"><span data-stu-id="62e3d-108">The first table you add becomes the "left" table and the second table becomes the "right" table.</span></span> <span data-ttu-id="62e3d-109">(En revanche, l’ordre d’apparition des tables dans le [volet Schéma](diagram-pane-visual-database-tools.md) importe peu.) Quand vous spécifiez une jointure externe droite ou gauche, vous faites référence à l’ordre dans lequel les tables ont été ajoutées à la requête et à celui dans lequel elles apparaissent dans l’instruction SQL du [volet SQL](sql-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="62e3d-109">(The actual order in which the tables appear in the [Diagram pane](diagram-pane-visual-database-tools.md) is not significant.) When you specify a left or right outer join, you are referring to the order in which the tables were added to the query and to the order in which they appear in the SQL statement in the [SQL pane](sql-pane-visual-database-tools.md).</span></span>  
  
### <a name="to-create-an-outer-join"></a><span data-ttu-id="62e3d-110">Pour créer une jointure externe</span><span class="sxs-lookup"><span data-stu-id="62e3d-110">To create an outer join</span></span>  
  
1.  <span data-ttu-id="62e3d-111">Créez la jointure, soit automatiquement, soit manuellement.</span><span class="sxs-lookup"><span data-stu-id="62e3d-111">Create the join, either automatically or manually.</span></span> <span data-ttu-id="62e3d-112">Pour plus d’informations, consultez [Joindre automatiquement des tables &#40;Visual Database Tools&#41;](join-tables-automatically-visual-database-tools.md) ou [Joindre manuellement des tables &#40;Visual Database Tools&#41;](join-tables-manually-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="62e3d-112">For details, see [Join Tables Automatically &#40;Visual Database Tools&#41;](join-tables-automatically-visual-database-tools.md) or [Join Tables Manually &#40;Visual Database Tools&#41;](join-tables-manually-visual-database-tools.md).</span></span>  
  
2.  <span data-ttu-id="62e3d-113">Sélectionnez la ligne de jointure dans le volet Schéma, puis dans le menu **Concepteur de requêtes**, choisissez **Sélectionner toutes les lignes de \<tablename>** , en sélectionnant la commande qui ajoute la table dont vous voulez inclure les lignes supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="62e3d-113">Select the join line in the Diagram pane, and then from the **Query Designer** menu, choose **Select All Rows from \<tablename>**, selecting the command that includes the table whose extra rows you want to include.</span></span>  
  
    -   <span data-ttu-id="62e3d-114">Choisissez la première table pour créer une jointure externe gauche.</span><span class="sxs-lookup"><span data-stu-id="62e3d-114">Choose the first table to create a left outer join.</span></span>  
  
    -   <span data-ttu-id="62e3d-115">Choisissez la seconde table pour créer une jointure externe droite.</span><span class="sxs-lookup"><span data-stu-id="62e3d-115">Choose the second table to create a right outer join.</span></span>  
  
    -   <span data-ttu-id="62e3d-116">Choisissez les deux tables pour créer une jointure externe entière.</span><span class="sxs-lookup"><span data-stu-id="62e3d-116">Choose both tables to create a full outer join.</span></span>  
  
 <span data-ttu-id="62e3d-117">Lorsque vous spécifiez une jointure externe, le Concepteur de requêtes et de vues modifie la ligne de jointure pour indiquer qu'il s'agit d'une jointure externe.</span><span class="sxs-lookup"><span data-stu-id="62e3d-117">When you specify an outer join, the Query and View Designer modifies the join line to indicate an outer join.</span></span>  
  
 <span data-ttu-id="62e3d-118">En outre, il modifie l'instruction SQL du volet SQL pour refléter la modification du type de jointure, comme l'illustre l'instruction suivante :</span><span class="sxs-lookup"><span data-stu-id="62e3d-118">In addition, the Query and View Designer modifies the SQL statement in the SQL pane to reflect the change in join type, as shown in the following statement:</span></span>  
  
```  
SELECT employee.job_id, employee.emp_id,  
   employee.fname, employee.minit, jobs.job_desc  
FROM employee LEFT OUTER JOIN jobs ON   
    employee.job_id = jobs.job_id  
```  
  
 <span data-ttu-id="62e3d-119">Dans la mesure où une jointure externe comprend des lignes sans correspondance, vous pouvez l'utiliser pour trouver des lignes qui ne respectent pas les contraintes de clé étrangère.</span><span class="sxs-lookup"><span data-stu-id="62e3d-119">Because an outer join includes unmatched rows, you can use it to find rows that violate foreign key constraints.</span></span> <span data-ttu-id="62e3d-120">Pour ce faire, créez une jointure externe, puis ajoutez une condition de recherche afin de rechercher les lignes dans lesquelles la colonne clé primaire de la table à l'extrême droite a la valeur null.</span><span class="sxs-lookup"><span data-stu-id="62e3d-120">To do so, you create an outer join and then add a search condition to find rows in which the primary key column of the rightmost table is null.</span></span> <span data-ttu-id="62e3d-121">Dans l'exemple, la jointure externe ci-dessous trouve des lignes de la table `employee` qui ne possèdent pas de lignes correspondantes dans la table `jobs` :</span><span class="sxs-lookup"><span data-stu-id="62e3d-121">For example, the following outer join finds rows in the `employee` table that do not have corresponding rows in the `jobs` table:</span></span>  
  
```  
SELECT employee.emp_id, employee.job_id  
FROM employee LEFT OUTER JOIN jobs   
   ON employee.job_id = jobs.job_id  
WHERE (jobs.job_id IS NULL)  
```  
  
## <a name="see-also"></a><span data-ttu-id="62e3d-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="62e3d-122">See Also</span></span>  
 <span data-ttu-id="62e3d-123">[Interroger avec des jointures &#40;Visual Database Tools&#41;](query-with-joins-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="62e3d-123">[Query with Joins &#40;Visual Database Tools&#41;](query-with-joins-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="62e3d-124">Boîte de dialogue Joindre &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="62e3d-124">Join Dialog Box &#40;Visual Database Tools&#41;</span></span>](join-dialog-box-visual-database-tools.md)  
  
  
