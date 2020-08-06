---
title: Représentation des jointures par le concepteur de requêtes et de vues (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL pane [Visual Database Tools]
- joins [SQL Server], Query and View Designer
- Diagram pane [Visual Database Tools]
ms.assetid: 20a99dcb-83bd-4aa6-9139-92e2e5ba4887
author: stevestein
ms.author: sstein
ms.openlocfilehash: 55fdea533436f9fa7c2a902667b3166085c27e99
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610933"
---
# <a name="how-the-query-and-view-designer-represents-joins-visual-database-tools"></a><span data-ttu-id="d3d00-102">Représentation des jointures dans le Concepteur de requêtes et de vues (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="d3d00-102">How the Query and View Designer Represents Joins (Visual Database Tools)</span></span>
  <span data-ttu-id="d3d00-103">Dans le cas de tables jointes, le [Concepteur de requêtes et de vues](visual-database-tools.md) représente la jointure graphiquement dans le [volet Schéma](diagram-pane-visual-database-tools.md) et il utilise la syntaxe SQL dans le [volet SQL](sql-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d3d00-103">If tables are joined, the [Query and View Designer](visual-database-tools.md) represents the join graphically in the [Diagram pane](diagram-pane-visual-database-tools.md) and by using SQL syntax in the [SQL pane](sql-pane-visual-database-tools.md).</span></span>  
  
## <a name="diagram-pane"></a><span data-ttu-id="d3d00-104">Volet Schéma</span><span class="sxs-lookup"><span data-stu-id="d3d00-104">Diagram Pane</span></span>  
 <span data-ttu-id="d3d00-105">Dans le volet Schéma, le Concepteur de requêtes et de vues affiche une ligne de jointure entre les colonnes de données impliquées.</span><span class="sxs-lookup"><span data-stu-id="d3d00-105">In the Diagram pane the Query and View Designer displays a join line between the data columns involved in the join.</span></span> <span data-ttu-id="d3d00-106">Il affiche une ligne de jointure par condition de jointure.</span><span class="sxs-lookup"><span data-stu-id="d3d00-106">The Query and View Designer displays one join line for each join condition.</span></span> <span data-ttu-id="d3d00-107">Par exemple, l'illustration suivante montre une ligne de jointure entre deux tables jointes :</span><span class="sxs-lookup"><span data-stu-id="d3d00-107">For example, the following illustration shows a join line between two tables that are joined:</span></span>  
  
 <span data-ttu-id="d3d00-108">![La ligne de jointure illustre la relation entre deux tables](../../database-engine/media//dv3wbig.gif "La ligne de jointure illustre la relation entre deux tables")</span><span class="sxs-lookup"><span data-stu-id="d3d00-108">![Join line shows relationship between two tables](../../database-engine/media//dv3wbig.gif "Join line shows relationship between two tables")</span></span>  
  
 <span data-ttu-id="d3d00-109">Si des tables ont plusieurs conditions de jointure, le Concepteur de requêtes et de vues affiche plusieurs lignes de jointure, comme l'illustre l'exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="d3d00-109">If tables are joined using more than one join condition, the Query and View Designer displays multiple join lines, as in the following example:</span></span>  
  
 <span data-ttu-id="d3d00-110">![Tables jointes à l'aide de plusieurs conditions de jointure](../../database-engine/media//dv3w9n1.gif "Tables jointes à l'aide de plusieurs conditions de jointure")</span><span class="sxs-lookup"><span data-stu-id="d3d00-110">![Tables joined using more than one join condition](../../database-engine/media//dv3w9n1.gif "Tables joined using more than one join condition")</span></span>  
  
 <span data-ttu-id="d3d00-111">Si les colonnes de données jointes ne sont pas affichées (parce que, par exemple, le rectangle représentant la table ou l'objet table est réduit ou la jointure implique une expression), le Concepteur de requêtes et de vues place la ligne de jointure dans la barre de titre du rectangle représentant la table ou l'objet structuré en table.</span><span class="sxs-lookup"><span data-stu-id="d3d00-111">If the joined data columns are not displayed (for example, the rectangle representing the table or table-structured object is minimized or the join involves an expression), the Query and View Designer places the join line at the title bar of the rectangle representing the table or table-structured object.</span></span>  
  
 <span data-ttu-id="d3d00-112">La forme de l'icône au milieu de la ligne de jointure indique la façon dont les tables ou les objets structurés en table sont joints.</span><span class="sxs-lookup"><span data-stu-id="d3d00-112">The shape of the icon in the middle of the join line indicates how the tables or table-structured objects are joined.</span></span> <span data-ttu-id="d3d00-113">Si la clause de jointure utilise un autre opérateur que le signe égal (=), il apparaît dans l’icône de la ligne de jointure.</span><span class="sxs-lookup"><span data-stu-id="d3d00-113">If the join clause uses an operator other than equal (=), the operator appears in the join line icon.</span></span> <span data-ttu-id="d3d00-114">Le tableau suivant fait la liste des icônes qui apparaissent dans la ligne de jointure.</span><span class="sxs-lookup"><span data-stu-id="d3d00-114">The following table lists the icons that appear in the join line.</span></span>  
  
|<span data-ttu-id="d3d00-115">**Icône de la ligne de jointure**</span><span class="sxs-lookup"><span data-stu-id="d3d00-115">**Join line icon**</span></span>|<span data-ttu-id="d3d00-116">**Description**</span><span class="sxs-lookup"><span data-stu-id="d3d00-116">**Description**</span></span>|  
|------------------------|---------------------|  
|<span data-ttu-id="d3d00-117">![Icône Visual Database Tools](../../database-engine/media//dv3wbih.gif "Icône Visual Database Tools")</span><span class="sxs-lookup"><span data-stu-id="d3d00-117">![Visual Database Tools icon](../../database-engine/media//dv3wbih.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="d3d00-118">Jointure interne (créée avec un opérateur « égal »).</span><span class="sxs-lookup"><span data-stu-id="d3d00-118">Inner join (created using an equal sign).</span></span>|  
|<span data-ttu-id="d3d00-119">![Icône Visual Database Tools](../../database-engine/media//dv3wbii.gif "Icône Visual Database Tools")</span><span class="sxs-lookup"><span data-stu-id="d3d00-119">![Visual Database Tools icon](../../database-engine/media//dv3wbii.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="d3d00-120">Jointure interne basée sur l'opérateur « plus grand que ».</span><span class="sxs-lookup"><span data-stu-id="d3d00-120">Inner join based on the "greater than" operator.</span></span>|  
|<span data-ttu-id="d3d00-121">![Icône Visual Database Tools](../../database-engine/media//dv3wbij.gif "Icône Visual Database Tools")</span><span class="sxs-lookup"><span data-stu-id="d3d00-121">![Visual Database Tools icon](../../database-engine/media//dv3wbij.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="d3d00-122">Jointure externe dans laquelle toutes les lignes de la table représentée à gauche seront incluses, même si elles n'ont pas de correspondance dans la table en relation.</span><span class="sxs-lookup"><span data-stu-id="d3d00-122">Outer join in which all rows from the table represented on the left will be included, even if they do not have matches in the related table.</span></span>|  
|<span data-ttu-id="d3d00-123">![Icône Visual Database Tools](../../database-engine/media//dv3wbik.gif "Icône Visual Database Tools")</span><span class="sxs-lookup"><span data-stu-id="d3d00-123">![Visual Database Tools icon](../../database-engine/media//dv3wbik.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="d3d00-124">Jointure externe dans laquelle toutes les lignes de la table représentée à droite seront incluses, même si elles n'ont pas de correspondance dans la table en relation.</span><span class="sxs-lookup"><span data-stu-id="d3d00-124">Outer join in which all rows from the table represented on the right will be included, even if they do not have matches in the related table.</span></span>|  
|<span data-ttu-id="d3d00-125">![Icône Visual Database Tools](../../database-engine/media//dv3wbil.gif "Icône Visual Database Tools")</span><span class="sxs-lookup"><span data-stu-id="d3d00-125">![Visual Database Tools icon](../../database-engine/media//dv3wbil.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="d3d00-126">Jointure externe entière dans laquelle toutes les lignes des deux tables seront incluses, même si elles n'ont pas de correspondance dans la table en relation.</span><span class="sxs-lookup"><span data-stu-id="d3d00-126">Full outer join in which all rows from both tables will be included, even if they do not have matches in the related table.</span></span>|  
  
 <span data-ttu-id="d3d00-127">Les symboles présents aux extrémités de la ligne de jointure indiquent le type de jointure.</span><span class="sxs-lookup"><span data-stu-id="d3d00-127">The symbols on the ends of the join line indicate the type of join.</span></span> <span data-ttu-id="d3d00-128">Le tableau suivant fait la liste des types de jointures et des icônes affichées aux extrémités de la ligne de jointure.</span><span class="sxs-lookup"><span data-stu-id="d3d00-128">The following table lists the types of joins and the icons displayed on the ends of the join line.</span></span>  
  
|<span data-ttu-id="d3d00-129">**Icône aux extrémités de la ligne de jointure**</span><span class="sxs-lookup"><span data-stu-id="d3d00-129">**Icon on ends of join line**</span></span>|<span data-ttu-id="d3d00-130">**Type de jointure**</span><span class="sxs-lookup"><span data-stu-id="d3d00-130">**Type of join**</span></span>|  
|-----------------------------------|----------------------|  
|<span data-ttu-id="d3d00-131">![Icône Visual Database Tools](../../database-engine/media//dv3wbim.gif "Icône Visual Database Tools")</span><span class="sxs-lookup"><span data-stu-id="d3d00-131">![Visual Database Tools icon](../../database-engine/media//dv3wbim.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="d3d00-132">Jointure Un-à-un.</span><span class="sxs-lookup"><span data-stu-id="d3d00-132">One-to-one join.</span></span>|  
|<span data-ttu-id="d3d00-133">![Icône Visual Database Tools](../../database-engine/media//dv3wbin.gif "Icône Visual Database Tools")</span><span class="sxs-lookup"><span data-stu-id="d3d00-133">![Visual Database Tools icon](../../database-engine/media//dv3wbin.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="d3d00-134">Jointure Un-à-plusieurs.</span><span class="sxs-lookup"><span data-stu-id="d3d00-134">One-to-many join.</span></span>|  
|<span data-ttu-id="d3d00-135">![Icône Visual Database Tools](../../database-engine/media//dv3wbio.gif "Icône Visual Database Tools")</span><span class="sxs-lookup"><span data-stu-id="d3d00-135">![Visual Database Tools icon](../../database-engine/media//dv3wbio.gif "Visual Database Tools icon")</span></span>|<span data-ttu-id="d3d00-136">Le Concepteur de requêtes et de vues ne peut pas déterminer le type de jointure.</span><span class="sxs-lookup"><span data-stu-id="d3d00-136">Query and View Designer cannot determine the join type.</span></span> <span data-ttu-id="d3d00-137">Ce cas s'observe surtout lorsque vous avez créé une jointure manuellement.</span><span class="sxs-lookup"><span data-stu-id="d3d00-137">This situation occurs most often when you have created a join manually.</span></span>|  
  
## <a name="sql-pane"></a><span data-ttu-id="d3d00-138">volet SQL</span><span class="sxs-lookup"><span data-stu-id="d3d00-138">SQL Pane</span></span>  
 <span data-ttu-id="d3d00-139">Dans une instruction SQL, une jointure peut être exprimée de plusieurs façons différentes.</span><span class="sxs-lookup"><span data-stu-id="d3d00-139">A join can be expressed in a number of ways in an SQL statement.</span></span> <span data-ttu-id="d3d00-140">La syntaxe exacte dépend de la base de données utilisée et de la façon dont la jointure a été définie.</span><span class="sxs-lookup"><span data-stu-id="d3d00-140">The exact syntax depends on the database you are using and on how you have defined the join.</span></span>  
  
 <span data-ttu-id="d3d00-141">Pour spécifier une jointure de tables, vous disposez de plusieurs options de syntaxe :</span><span class="sxs-lookup"><span data-stu-id="d3d00-141">Syntax options for joining tables include:</span></span>  
  
-   <span data-ttu-id="d3d00-142">**Qualificateur JOIN pour la clause FROM**.</span><span class="sxs-lookup"><span data-stu-id="d3d00-142">**JOIN qualifier for the FROM clause**.</span></span>   <span data-ttu-id="d3d00-143">Les mots clés INNER et OUTER spécifient le type de jointure.</span><span class="sxs-lookup"><span data-stu-id="d3d00-143">The keywords INNER and OUTER specify the join type.</span></span> <span data-ttu-id="d3d00-144">Il s'agit de la syntaxe standard du SQL ANSI 92.</span><span class="sxs-lookup"><span data-stu-id="d3d00-144">This syntax is standard for ANSI 92 SQL.</span></span>  
  
     <span data-ttu-id="d3d00-145">Par exemple, si vous joignez les tables `publishers` et `pub_info` sur la base de la colonne `pub_id` de chaque table, vous obtenez une instruction SQL similaire à la suivante :</span><span class="sxs-lookup"><span data-stu-id="d3d00-145">For example, if you join the `publishers` and `pub_info` tables based on the `pub_id` column in each table, the resulting SQL statement might look like this:</span></span>  
  
    ```  
    SELECT *  
    FROM publishers INNER JOIN pub_info ON  
       publishers.pub_id = pub_info.pub_id  
    ```  
  
     <span data-ttu-id="d3d00-146">En cas de jointure externe, le mot INNER est remplacé par les mots LEFT OUTER ou RIGHT OUTER.</span><span class="sxs-lookup"><span data-stu-id="d3d00-146">If you create an outer join, the words LEFT OUTER or RIGHT OUTER appear in place of the word INNER.</span></span>  
  
-   <span data-ttu-id="d3d00-147">**Clause WHERE comparant des colonnes des deux tables**.</span><span class="sxs-lookup"><span data-stu-id="d3d00-147">**WHERE clause compares columns in both tables**.</span></span>   <span data-ttu-id="d3d00-148">Une clause WHERE apparaît si la base de données ne prend pas en charge la syntaxe JOIN (ou si vous l'avez entrée vous-même).</span><span class="sxs-lookup"><span data-stu-id="d3d00-148">A WHERE clause appears if the database does not support the JOIN syntax (or if you entered it yourself).</span></span> <span data-ttu-id="d3d00-149">Si la jointure est créée dans la clause WHERE, les noms des deux tables apparaissent dans la clause FROM.</span><span class="sxs-lookup"><span data-stu-id="d3d00-149">If the join is created in the WHERE clause, both table names appear in the FROM clause.</span></span>  
  
     <span data-ttu-id="d3d00-150">Par exemple, l'instruction suivante joint les tables `publishers` et `pub_info` .</span><span class="sxs-lookup"><span data-stu-id="d3d00-150">For example, the following statement joins the `publishers` and `pub_info` tables.</span></span>  
  
    ```  
    SELECT *  
    FROM publishers, pub_info  
    WHERE publishers.pub_id = pub_info.pub_id  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="d3d00-151">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d3d00-151">See Also</span></span>  
 <span data-ttu-id="d3d00-152">[Interroger avec des jointures &#40;Visual Database Tools&#41;](query-with-joins-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="d3d00-152">[Query with Joins &#40;Visual Database Tools&#41;](query-with-joins-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="d3d00-153">Boîte de dialogue Joindre &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="d3d00-153">Join Dialog Box &#40;Visual Database Tools&#41;</span></span>](join-dialog-box-visual-database-tools.md)  
  
  
