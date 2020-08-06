---
title: Utiliser des jeux de colonnes | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- sparse columns, column sets
- column sets
ms.assetid: a4f9de95-dc8f-4ad8-b957-137e32bfa500
author: stevestein
ms.author: sstein
ms.openlocfilehash: 9cb496137c3986b78a55862e434c153d354a42ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614463"
---
# <a name="use-column-sets"></a><span data-ttu-id="904e1-102">Utiliser des jeux de colonnes</span><span class="sxs-lookup"><span data-stu-id="904e1-102">Use Column Sets</span></span>
  <span data-ttu-id="904e1-103">Les tables qui utilisent des colonnes éparses peuvent désigner un jeu de colonnes pour retourner toutes les colonnes éparses dans la table.</span><span class="sxs-lookup"><span data-stu-id="904e1-103">Tables that use sparse columns can designate a column set to return all sparse columns in the table.</span></span> <span data-ttu-id="904e1-104">Un jeu de colonnes est une représentation XML non typée qui combine toutes les colonnes éparses d'une table dans une sortie structurée.</span><span class="sxs-lookup"><span data-stu-id="904e1-104">A column set is an untyped XML representation that combines all the sparse columns of a table into a structured output.</span></span> <span data-ttu-id="904e1-105">Un jeu de colonnes est semblable à une colonne calculée, dans la mesure où le jeu de colonnes n'est pas stocké physiquement dans la table.</span><span class="sxs-lookup"><span data-stu-id="904e1-105">A column set is like a calculated column in that the column set is not physically stored in the table.</span></span> <span data-ttu-id="904e1-106">Un jeu de colonnes diffère d'une colonne calculée, dans le sens où le jeu de colonnes est peut être mis à jour directement.</span><span class="sxs-lookup"><span data-stu-id="904e1-106">A column set differs from a calculated column in that the column set is directly updatable.</span></span>  
  
 <span data-ttu-id="904e1-107">Vous devez envisager d'utiliser des jeux de colonnes lorsque le nombre de colonnes dans une table est élevé et qu'il serait trop long d'opérer individuellement sur chacune d'elles.</span><span class="sxs-lookup"><span data-stu-id="904e1-107">You should consider using column sets when the number of columns in a table is large, and operating on them individually is cumbersome.</span></span> <span data-ttu-id="904e1-108">Les applications peuvent présenter une amélioration des performances lorsqu'elles sélectionnent et insèrent des données à l'aide de jeux de colonnes sur des tables qui contiennent de nombreuses colonnes.</span><span class="sxs-lookup"><span data-stu-id="904e1-108">Applications might see some performance improvement when they select and insert data by using column sets on tables that have lots of columns.</span></span> <span data-ttu-id="904e1-109">Toutefois, les performances des jeux de colonnes peuvent être réduites lorsque de nombreux index sont définis sur les colonnes de la table.</span><span class="sxs-lookup"><span data-stu-id="904e1-109">However, the performance of column sets can be reduced when many indexes are defined on the columns in the table.</span></span> <span data-ttu-id="904e1-110">Cela est dû au fait que la quantité de mémoire requise pour un plan d'exécution augmente.</span><span class="sxs-lookup"><span data-stu-id="904e1-110">This is because the amount of memory that is required for an execution plan increases.</span></span>  
  
 <span data-ttu-id="904e1-111">Pour définir un jeu de colonnes, utilisez les mots clés *<nom_jeu_colonnes>* FOR ALL_SPARSE_COLUMNS dans les instructions [CREATE TABLE](/sql/t-sql/statements/create-table-transact-sql) ou [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="904e1-111">To define a column set, use the *<column_set_name>* FOR ALL_SPARSE_COLUMNS keywords in the[CREATE TABLE](/sql/t-sql/statements/create-table-transact-sql) or [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) statements.</span></span>  
  
## <a name="guidelines-for-using-column-sets"></a><span data-ttu-id="904e1-112">Indications pour utiliser des jeux de colonnes</span><span class="sxs-lookup"><span data-stu-id="904e1-112">Guidelines for Using Column Sets</span></span>  
 <span data-ttu-id="904e1-113">Lorsque vous utilisez des jeux de colonnes, considérez les indications suivantes :</span><span class="sxs-lookup"><span data-stu-id="904e1-113">When you use column sets, consider the following guidelines:</span></span>  
  
-   <span data-ttu-id="904e1-114">Les colonnes éparses et un jeu de colonnes peuvent être ajoutés dans le cadre de la même instruction.</span><span class="sxs-lookup"><span data-stu-id="904e1-114">Sparse columns and a column set can be added as part of the same statement.</span></span>  
  
-   <span data-ttu-id="904e1-115">Le jeu de colonnes ne peut pas être modifié.</span><span class="sxs-lookup"><span data-stu-id="904e1-115">The column set cannot be changed.</span></span> <span data-ttu-id="904e1-116">Pour modifier un jeu de colonnes, vous devez le supprimer et le recréer.</span><span class="sxs-lookup"><span data-stu-id="904e1-116">To change a column set, you must delete and re-create the column set.</span></span>  
  
-   <span data-ttu-id="904e1-117">Un jeu de colonnes ne peut pas être ajouté à une table si celle-ci contient déjà des colonnes éparses.</span><span class="sxs-lookup"><span data-stu-id="904e1-117">A column set cannot be added to a table if that table already contains sparse columns.</span></span>  
  
-   <span data-ttu-id="904e1-118">Un jeu de colonnes peut être ajouté à une table qui n'inclut pas de colonnes éparses.</span><span class="sxs-lookup"><span data-stu-id="904e1-118">A column set can be added to a table that does not include any sparse columns.</span></span> <span data-ttu-id="904e1-119">Si des colonnes éparses sont ajoutées ultérieurement à la table, elles apparaîtront dans le jeu de colonnes.</span><span class="sxs-lookup"><span data-stu-id="904e1-119">If sparse columns are later added to the table, they will appear in the column set.</span></span>  
  
-   <span data-ttu-id="904e1-120">Un seul jeu de colonnes est autorisé par table.</span><span class="sxs-lookup"><span data-stu-id="904e1-120">Only one column set is allowed per table.</span></span>  
  
-   <span data-ttu-id="904e1-121">Un jeu de colonnes est facultatif et n'est pas nécessaire pour pouvoir utiliser des colonnes éparses.</span><span class="sxs-lookup"><span data-stu-id="904e1-121">A column set is optional and is not required to use sparse columns.</span></span>  
  
-   <span data-ttu-id="904e1-122">Il est impossible de définir des contraintes ou des valeurs par défaut sur un jeu de colonnes.</span><span class="sxs-lookup"><span data-stu-id="904e1-122">Constraints or default values cannot be defined on a column set.</span></span>  
  
-   <span data-ttu-id="904e1-123">Les colonnes calculées ne peuvent pas contenir de colonnes de jeu de colonnes.</span><span class="sxs-lookup"><span data-stu-id="904e1-123">Computed columns cannot contain column set columns.</span></span>  
  
-   <span data-ttu-id="904e1-124">Les requêtes distribuées ne sont pas prises en charge sur les tables qui contiennent des jeux de colonnes.</span><span class="sxs-lookup"><span data-stu-id="904e1-124">Distributed queries are not supported on tables that contain column sets.</span></span>  
  
-   <span data-ttu-id="904e1-125">La réplication ne prend pas en charge les jeux de colonnes.</span><span class="sxs-lookup"><span data-stu-id="904e1-125">Replication does not support column sets.</span></span>  
  
-   <span data-ttu-id="904e1-126">La capture de données modifiées ne prend pas en charge les jeux de colonnes.</span><span class="sxs-lookup"><span data-stu-id="904e1-126">Change data capture does not support column sets.</span></span>  
  
-   <span data-ttu-id="904e1-127">Un jeu de colonnes ne peut faire partie d'aucun type d'index.</span><span class="sxs-lookup"><span data-stu-id="904e1-127">A column set cannot be part of any kind of index.</span></span> <span data-ttu-id="904e1-128">Cela inclut les index XML, les index de recherche en texte intégral et les vues indexées.</span><span class="sxs-lookup"><span data-stu-id="904e1-128">This includes XML indexes, full-text indexes, and indexed views.</span></span> <span data-ttu-id="904e1-129">Un jeu de colonnes ne peut pas être ajouté en tant que colonne incluse dans un index.</span><span class="sxs-lookup"><span data-stu-id="904e1-129">A column set cannot be added as an included column in any index.</span></span>  
  
-   <span data-ttu-id="904e1-130">Un jeu de colonnes ne peut pas être utilisé dans l'expression de filtre d'un index filtré ou de statistiques filtrées.</span><span class="sxs-lookup"><span data-stu-id="904e1-130">A column set cannot be used in the filter expression of a filtered index or filtered statistics.</span></span>  
  
-   <span data-ttu-id="904e1-131">Lorsqu'une vue inclut un jeu de colonnes, celui-ci apparaît dans la vue comme une colonne XML.</span><span class="sxs-lookup"><span data-stu-id="904e1-131">When a view includes a column set, the column set appears in the view as an XML column.</span></span>  
  
-   <span data-ttu-id="904e1-132">Un jeu de colonnes ne peut pas être inclus dans une définition de vue indexée.</span><span class="sxs-lookup"><span data-stu-id="904e1-132">A column set cannot be included in an indexed view definition.</span></span>  
  
-   <span data-ttu-id="904e1-133">Les vues partitionnées qui incluent des tables qui contiennent des jeux de colonnes peuvent être mises à jour lorsque la vue partitionnée spécifie les colonnes éparses par nom.</span><span class="sxs-lookup"><span data-stu-id="904e1-133">Partitioned views that include tables that contain column sets are updatable when the partitioned view specifies the sparse columns by name.</span></span> <span data-ttu-id="904e1-134">Une vue partitionnée ne peut pas être mise à jour lorsqu'elle fait référence au jeu de colonnes.</span><span class="sxs-lookup"><span data-stu-id="904e1-134">A partitioned view is not updatable when it references the column set.</span></span>  
  
-   <span data-ttu-id="904e1-135">Les notifications de requêtes qui renvoient à des jeux de colonnes ne sont pas autorisées.</span><span class="sxs-lookup"><span data-stu-id="904e1-135">Query notifications that refer to column sets are not permitted.</span></span>  
  
-   <span data-ttu-id="904e1-136">Les données XML ont une limite de taille de 2 Go.</span><span class="sxs-lookup"><span data-stu-id="904e1-136">XML data has a size limit of 2 GB.</span></span> <span data-ttu-id="904e1-137">Si les données combinées de toutes les colonnes éparses non nulles dans une ligne dépassent cette limite, la requête ou opération DML génère une erreur.</span><span class="sxs-lookup"><span data-stu-id="904e1-137">If the combined data of all the nonnull sparse columns in a row exceeds this limit, the query or DML operation will produce an error.</span></span>  
  
-   <span data-ttu-id="904e1-138">Pour plus d’informations sur les données retournées par la fonction COLUMNS_UPDATED, consultez [Utiliser des colonnes éparses](use-sparse-columns.md).</span><span class="sxs-lookup"><span data-stu-id="904e1-138">For information about the data that is returned by the COLUMNS_UPDATED function, see [Use Sparse Columns](use-sparse-columns.md).</span></span>  
  
## <a name="guidelines-for-selecting-data-from-a-column-set"></a><span data-ttu-id="904e1-139">Indications pour la sélection de données dans un jeu de colonnes</span><span class="sxs-lookup"><span data-stu-id="904e1-139">Guidelines for Selecting Data from a Column Set</span></span>  
 <span data-ttu-id="904e1-140">Considérez les indications suivantes lors de la sélection de données dans un jeu de colonnes :</span><span class="sxs-lookup"><span data-stu-id="904e1-140">Consider the following guidelines for selecting data from a column set:</span></span>  
  
-   <span data-ttu-id="904e1-141">D'un point de vue conceptuel, un jeu de colonnes est un type de colonne XML calculé pouvant être mis à jour, qui regroupe un jeu de colonnes relationnelles sous-jacentes dans une représentation XML unique.</span><span class="sxs-lookup"><span data-stu-id="904e1-141">Conceptually, a column set is a type of updatable, computed XML column that aggregates a set of underlying relational columns into a single XML representation.</span></span> <span data-ttu-id="904e1-142">Le jeu de colonnes prend en charge uniquement la propriété ALL_SPARSE_COLUMNS.</span><span class="sxs-lookup"><span data-stu-id="904e1-142">The column set only supports the ALL_SPARSE_COLUMNS property.</span></span> <span data-ttu-id="904e1-143">Cette propriété est utilisée pour regrouper toutes les valeurs non nulles de toutes les colonnes éparses pour une ligne particulière.</span><span class="sxs-lookup"><span data-stu-id="904e1-143">This property is used to aggregate all nonnull values from all sparse columns for a particular row.</span></span>  
  
-   <span data-ttu-id="904e1-144">Dans l'éditeur de tables [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , les jeux de colonnes sont affichés sous forme de champ XML modifiable.</span><span class="sxs-lookup"><span data-stu-id="904e1-144">In the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] table editor, column sets are displayed as an editable XML field.</span></span> <span data-ttu-id="904e1-145">Définissez les jeux de colonnes au format suivant :</span><span class="sxs-lookup"><span data-stu-id="904e1-145">Define column sets in the format:</span></span>  
  
    ```  
    <column_name_1>value1</column_name_1><column_name_2>value2</column_name_2>...  
    ```  
  
     <span data-ttu-id="904e1-146">Voici quelques exemples de valeurs de jeu de colonnes :</span><span class="sxs-lookup"><span data-stu-id="904e1-146">Examples of column set values are as follows:</span></span>  
  
    -   `<sparseProp1>10</sparseProp1><sparseProp3>20</sparseProp3>`  
  
    -   `<DocTitle>Bicycle Parts List</DocTitle><Region>West</Region>`  
  
-   <span data-ttu-id="904e1-147">Les colonnes éparses qui contiennent des valeurs NULL sont omises de la représentation XML pour le jeu de colonnes.</span><span class="sxs-lookup"><span data-stu-id="904e1-147">Sparse columns that contain null values are omitted from the XML representation for the column set.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="904e1-148">L'ajout d'un jeu de colonnes modifie le comportement des requêtes SELECT \*.</span><span class="sxs-lookup"><span data-stu-id="904e1-148">Adding a column set changes the behavior of SELECT \* queries.</span></span> <span data-ttu-id="904e1-149">La requête retournera le jeu de colonnes sous forme de colonne XML et ne retournera pas les colonnes éparses individuelles.</span><span class="sxs-lookup"><span data-stu-id="904e1-149">The query will return the column set as an XML column and not return the individual sparse columns.</span></span> <span data-ttu-id="904e1-150">Les concepteurs de schémas et développeurs de logiciels doivent prendre soin de ne pas arrêter les applications existantes.</span><span class="sxs-lookup"><span data-stu-id="904e1-150">Schema designers and software developers must be careful not to break existing applications.</span></span>  
  
## <a name="inserting-or-modifying-data-in-a-column-set"></a><span data-ttu-id="904e1-151">Insertion ou modification de données dans un jeu de colonnes</span><span class="sxs-lookup"><span data-stu-id="904e1-151">Inserting or Modifying Data in a Column Set</span></span>  
 <span data-ttu-id="904e1-152">La manipulation des données d'une colonne éparse peut s'effectuer en utilisant le nom de chaque colonne ou en faisant référence au nom du jeu de colonnes et en spécifiant les valeurs du jeu de colonnes à l'aide du format XML du jeu de colonnes.</span><span class="sxs-lookup"><span data-stu-id="904e1-152">Data manipulation of a sparse column can be performed by using the name of the individual columns, or by referencing the name of the column set and specifying the values of the column set by using the XML format of the column set.</span></span> <span data-ttu-id="904e1-153">Les colonnes éparses peuvent apparaître dans n'importe quel ordre dans la colonne XML.</span><span class="sxs-lookup"><span data-stu-id="904e1-153">Sparse columns can appear in any order in the XML column.</span></span>  
  
 <span data-ttu-id="904e1-154">Lorsque des valeurs de colonnes éparses sont insérées ou mises à jour à l'aide du jeu de colonnes XML, les valeurs insérées dans les colonnes éparses sous-jacentes sont converties implicitement à partir du type de données `xml`.</span><span class="sxs-lookup"><span data-stu-id="904e1-154">When sparse column values are inserted or updated by using the XML column set, the values that are inserted into the underlying sparse columns are implicitly converted from the `xml` data type.</span></span> <span data-ttu-id="904e1-155">Dans le cas des colonnes numériques, une valeur vierge dans le XML pour la colonne numérique est convertie en chaîne vide.</span><span class="sxs-lookup"><span data-stu-id="904e1-155">In the case of numeric columns, a blank value in the XML for the numeric column converts to an empty string.</span></span> <span data-ttu-id="904e1-156">Cela provoque l'insertion d'un zéro dans la colonne numérique, comme illustré dans l'exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="904e1-156">This causes a zero to be inserted into the numeric column as shown in the following example.</span></span>  
  
```  
CREATE TABLE t (i int SPARSE, cs xml column_set FOR ALL_SPARSE_COLUMNS);  
GO  
INSERT t(cs) VALUES ('<i/>');  
GO  
SELECT i FROM t;  
GO  
```  
  
 <span data-ttu-id="904e1-157">Dans cet exemple, aucune valeur n'a été spécifiée pour le `i`de colonne, mais la valeur `0` a été insérée.</span><span class="sxs-lookup"><span data-stu-id="904e1-157">In this example, no value was specified for the column `i`, but the value `0` was inserted.</span></span>  
  
## <a name="using-the-sql_variant-data-type"></a><span data-ttu-id="904e1-158">Utilisation du Type de données sql_variant</span><span class="sxs-lookup"><span data-stu-id="904e1-158">Using the sql_variant Data Type</span></span>  
 <span data-ttu-id="904e1-159">Le type de données `sql_variant` peut stocker plusieurs types de données différents, tels que `int`, `char` et `date`.</span><span class="sxs-lookup"><span data-stu-id="904e1-159">The `sql_variant` date type can store multiple different data types, such as `int`, `char`, and `date`.</span></span> <span data-ttu-id="904e1-160">Les jeux de colonnes retournent les informations de type de données telles que l'échelle, la précision et les informations relatives aux paramètres régionaux associées à une valeur `sql_variant` sous la forme d'attributs dans la colonne XML générée.</span><span class="sxs-lookup"><span data-stu-id="904e1-160">Column sets output the data type information such as scale, precision, and locale information that is associated with a `sql_variant` value as attributes in the generated XML column.</span></span> <span data-ttu-id="904e1-161">Si vous essayez de fournir ces attributs dans une instruction XML générée de manière personnalisée en tant qu'entrée pour une opération d'insertion ou de mise à jour sur un jeu de colonnes, certains de ces attributs sont requis et une valeur par défaut est assignée à certains d'entre eux.</span><span class="sxs-lookup"><span data-stu-id="904e1-161">If you try to provide these attributes in a custom-generated XML statement as an input for an insert or update operation on a column set, some of these attributes are required and some of them are assigned a default value.</span></span> <span data-ttu-id="904e1-162">Le tableau suivant répertorie les types de données et les valeurs par défaut générées par le serveur lorsque la valeur n'est pas fournie.</span><span class="sxs-lookup"><span data-stu-id="904e1-162">The following table lists the data types and the default values that the server generates when the value is not provided.</span></span>  
  
|<span data-ttu-id="904e1-163">Type de données</span><span class="sxs-lookup"><span data-stu-id="904e1-163">Data type</span></span>|<span data-ttu-id="904e1-164">localeID\*</span><span class="sxs-lookup"><span data-stu-id="904e1-164">localeID\*</span></span>|<span data-ttu-id="904e1-165">sqlCompareOptions</span><span class="sxs-lookup"><span data-stu-id="904e1-165">sqlCompareOptions</span></span>|<span data-ttu-id="904e1-166">sqlCollationVersion</span><span class="sxs-lookup"><span data-stu-id="904e1-166">sqlCollationVersion</span></span>|<span data-ttu-id="904e1-167">SqlSortId</span><span class="sxs-lookup"><span data-stu-id="904e1-167">SqlSortId</span></span>|<span data-ttu-id="904e1-168">Longueur maximale</span><span class="sxs-lookup"><span data-stu-id="904e1-168">Maximum length</span></span>|<span data-ttu-id="904e1-169">Precision</span><span class="sxs-lookup"><span data-stu-id="904e1-169">Precision</span></span>|<span data-ttu-id="904e1-170">Scale</span><span class="sxs-lookup"><span data-stu-id="904e1-170">Scale</span></span>|  
|---------------|----------------|-----------------------|-------------------------|---------------|--------------------|---------------|-----------|  
|<span data-ttu-id="904e1-171">`char`, `varchar`, `binary`</span><span class="sxs-lookup"><span data-stu-id="904e1-171">`char`, `varchar`, `binary`</span></span>|<span data-ttu-id="904e1-172">-1</span><span class="sxs-lookup"><span data-stu-id="904e1-172">-1</span></span>|<span data-ttu-id="904e1-173">'Par défaut'</span><span class="sxs-lookup"><span data-stu-id="904e1-173">'Default'</span></span>|<span data-ttu-id="904e1-174">0</span><span class="sxs-lookup"><span data-stu-id="904e1-174">0</span></span>|<span data-ttu-id="904e1-175">0</span><span class="sxs-lookup"><span data-stu-id="904e1-175">0</span></span>|<span data-ttu-id="904e1-176">8000</span><span class="sxs-lookup"><span data-stu-id="904e1-176">8000</span></span>|<span data-ttu-id="904e1-177">Non applicable\*\*</span><span class="sxs-lookup"><span data-stu-id="904e1-177">Not applicable\*\*</span></span>|<span data-ttu-id="904e1-178">Non applicable</span><span class="sxs-lookup"><span data-stu-id="904e1-178">Not applicable</span></span>|  
|`nvarchar`|<span data-ttu-id="904e1-179">-1</span><span class="sxs-lookup"><span data-stu-id="904e1-179">-1</span></span>|<span data-ttu-id="904e1-180">'Par défaut'</span><span class="sxs-lookup"><span data-stu-id="904e1-180">'Default'</span></span>|<span data-ttu-id="904e1-181">0</span><span class="sxs-lookup"><span data-stu-id="904e1-181">0</span></span>|<span data-ttu-id="904e1-182">0</span><span class="sxs-lookup"><span data-stu-id="904e1-182">0</span></span>|<span data-ttu-id="904e1-183">4000</span><span class="sxs-lookup"><span data-stu-id="904e1-183">4000</span></span>|<span data-ttu-id="904e1-184">Non applicable</span><span class="sxs-lookup"><span data-stu-id="904e1-184">Not applicable</span></span>|<span data-ttu-id="904e1-185">Non applicable</span><span class="sxs-lookup"><span data-stu-id="904e1-185">Not applicable</span></span>|  
|<span data-ttu-id="904e1-186">`decimal`, `float`, `real`</span><span class="sxs-lookup"><span data-stu-id="904e1-186">`decimal`, `float`, `real`</span></span>|<span data-ttu-id="904e1-187">Non applicable</span><span class="sxs-lookup"><span data-stu-id="904e1-187">Not applicable</span></span>|<span data-ttu-id="904e1-188">Non applicable</span><span class="sxs-lookup"><span data-stu-id="904e1-188">Not applicable</span></span>|<span data-ttu-id="904e1-189">Non applicable</span><span class="sxs-lookup"><span data-stu-id="904e1-189">Not applicable</span></span>|<span data-ttu-id="904e1-190">Non applicable</span><span class="sxs-lookup"><span data-stu-id="904e1-190">Not applicable</span></span>|<span data-ttu-id="904e1-191">Non applicable</span><span class="sxs-lookup"><span data-stu-id="904e1-191">Not applicable</span></span>|<span data-ttu-id="904e1-192">18</span><span class="sxs-lookup"><span data-stu-id="904e1-192">18</span></span>|<span data-ttu-id="904e1-193">0</span><span class="sxs-lookup"><span data-stu-id="904e1-193">0</span></span>|  
|<span data-ttu-id="904e1-194">`integer`, `bigint`, `tinyint`, `smallint`</span><span class="sxs-lookup"><span data-stu-id="904e1-194">`integer`, `bigint`, `tinyint`, `smallint`</span></span>|<span data-ttu-id="904e1-195">Non applicable</span><span class="sxs-lookup"><span data-stu-id="904e1-195">Not applicable</span></span>|<span data-ttu-id="904e1-196">Non applicable</span><span class="sxs-lookup"><span data-stu-id="904e1-196">Not applicable</span></span>|<span data-ttu-id="904e1-197">Non applicable</span><span class="sxs-lookup"><span data-stu-id="904e1-197">Not applicable</span></span>|<span data-ttu-id="904e1-198">Non applicable</span><span class="sxs-lookup"><span data-stu-id="904e1-198">Not applicable</span></span>|<span data-ttu-id="904e1-199">Non applicable</span><span class="sxs-lookup"><span data-stu-id="904e1-199">Not applicable</span></span>|<span data-ttu-id="904e1-200">Non applicable</span><span class="sxs-lookup"><span data-stu-id="904e1-200">Not applicable</span></span>|<span data-ttu-id="904e1-201">Non applicable</span><span class="sxs-lookup"><span data-stu-id="904e1-201">Not applicable</span></span>|  
|`datetime2`|<span data-ttu-id="904e1-202">Non applicable</span><span class="sxs-lookup"><span data-stu-id="904e1-202">Not applicable</span></span>|<span data-ttu-id="904e1-203">Non applicable</span><span class="sxs-lookup"><span data-stu-id="904e1-203">Not applicable</span></span>|<span data-ttu-id="904e1-204">Non applicable</span><span class="sxs-lookup"><span data-stu-id="904e1-204">Not applicable</span></span>|<span data-ttu-id="904e1-205">Non applicable</span><span class="sxs-lookup"><span data-stu-id="904e1-205">Not applicable</span></span>|<span data-ttu-id="904e1-206">Non applicable</span><span class="sxs-lookup"><span data-stu-id="904e1-206">Not applicable</span></span>|<span data-ttu-id="904e1-207">Non applicable</span><span class="sxs-lookup"><span data-stu-id="904e1-207">Not applicable</span></span>|<span data-ttu-id="904e1-208">7</span><span class="sxs-lookup"><span data-stu-id="904e1-208">7</span></span>|  
|`datetime offset`|<span data-ttu-id="904e1-209">Non applicable</span><span class="sxs-lookup"><span data-stu-id="904e1-209">Not applicable</span></span>|<span data-ttu-id="904e1-210">Non applicable</span><span class="sxs-lookup"><span data-stu-id="904e1-210">Not applicable</span></span>|<span data-ttu-id="904e1-211">Non applicable</span><span class="sxs-lookup"><span data-stu-id="904e1-211">Not applicable</span></span>|<span data-ttu-id="904e1-212">Non applicable</span><span class="sxs-lookup"><span data-stu-id="904e1-212">Not applicable</span></span>|<span data-ttu-id="904e1-213">Non applicable</span><span class="sxs-lookup"><span data-stu-id="904e1-213">Not applicable</span></span>|<span data-ttu-id="904e1-214">Non applicable</span><span class="sxs-lookup"><span data-stu-id="904e1-214">Not applicable</span></span>|<span data-ttu-id="904e1-215">7</span><span class="sxs-lookup"><span data-stu-id="904e1-215">7</span></span>|  
|<span data-ttu-id="904e1-216">`datetime`, `date`, `smalldatetime`</span><span class="sxs-lookup"><span data-stu-id="904e1-216">`datetime`, `date`, `smalldatetime`</span></span>|<span data-ttu-id="904e1-217">Non applicable</span><span class="sxs-lookup"><span data-stu-id="904e1-217">Not applicable</span></span>|<span data-ttu-id="904e1-218">Non applicable</span><span class="sxs-lookup"><span data-stu-id="904e1-218">Not applicable</span></span>|<span data-ttu-id="904e1-219">Non applicable</span><span class="sxs-lookup"><span data-stu-id="904e1-219">Not applicable</span></span>|<span data-ttu-id="904e1-220">Non applicable</span><span class="sxs-lookup"><span data-stu-id="904e1-220">Not applicable</span></span>|<span data-ttu-id="904e1-221">Non applicable</span><span class="sxs-lookup"><span data-stu-id="904e1-221">Not applicable</span></span>|<span data-ttu-id="904e1-222">Non applicable</span><span class="sxs-lookup"><span data-stu-id="904e1-222">Not applicable</span></span>|<span data-ttu-id="904e1-223">Non applicable</span><span class="sxs-lookup"><span data-stu-id="904e1-223">Not applicable</span></span>|  
|<span data-ttu-id="904e1-224">`money`, `smallmoney`</span><span class="sxs-lookup"><span data-stu-id="904e1-224">`money`, `smallmoney`</span></span>|<span data-ttu-id="904e1-225">Non applicable</span><span class="sxs-lookup"><span data-stu-id="904e1-225">Not applicable</span></span>|<span data-ttu-id="904e1-226">Non applicable</span><span class="sxs-lookup"><span data-stu-id="904e1-226">Not applicable</span></span>|<span data-ttu-id="904e1-227">Non applicable</span><span class="sxs-lookup"><span data-stu-id="904e1-227">Not applicable</span></span>|<span data-ttu-id="904e1-228">Non applicable</span><span class="sxs-lookup"><span data-stu-id="904e1-228">Not applicable</span></span>|<span data-ttu-id="904e1-229">Non applicable</span><span class="sxs-lookup"><span data-stu-id="904e1-229">Not applicable</span></span>|<span data-ttu-id="904e1-230">Non applicable</span><span class="sxs-lookup"><span data-stu-id="904e1-230">Not applicable</span></span>|<span data-ttu-id="904e1-231">Non applicable</span><span class="sxs-lookup"><span data-stu-id="904e1-231">Not applicable</span></span>|  
|`time`|<span data-ttu-id="904e1-232">Non applicable</span><span class="sxs-lookup"><span data-stu-id="904e1-232">Not applicable</span></span>|<span data-ttu-id="904e1-233">Non applicable</span><span class="sxs-lookup"><span data-stu-id="904e1-233">Not applicable</span></span>|<span data-ttu-id="904e1-234">Non applicable</span><span class="sxs-lookup"><span data-stu-id="904e1-234">Not applicable</span></span>|<span data-ttu-id="904e1-235">Non applicable</span><span class="sxs-lookup"><span data-stu-id="904e1-235">Not applicable</span></span>|<span data-ttu-id="904e1-236">Non applicable</span><span class="sxs-lookup"><span data-stu-id="904e1-236">Not applicable</span></span>|<span data-ttu-id="904e1-237">Non applicable</span><span class="sxs-lookup"><span data-stu-id="904e1-237">Not applicable</span></span>|<span data-ttu-id="904e1-238">7</span><span class="sxs-lookup"><span data-stu-id="904e1-238">7</span></span>|  
  
 <span data-ttu-id="904e1-239">\*  localeID -1 correspond aux paramètres régionaux par défaut.</span><span class="sxs-lookup"><span data-stu-id="904e1-239">\*  localeID -1 means the default locale.</span></span> <span data-ttu-id="904e1-240">Les paramètres régionaux pour l'anglais sont 1033.</span><span class="sxs-lookup"><span data-stu-id="904e1-240">The English locale is 1033.</span></span>  
  
 <span data-ttu-id="904e1-241">\*\* Non applicable = Aucune valeur n’est sortie pour ces attributs durant une opération de sélection sur le jeu de colonnes.</span><span class="sxs-lookup"><span data-stu-id="904e1-241">\*\*  Not applicable = No values are output for these attributes during a select operation on the column set.</span></span> <span data-ttu-id="904e1-242">Génère une erreur lorsqu'une valeur est spécifiée pour cet attribut par l'appelant dans la représentation XML fournie pour un jeu de colonnes dans une opération d'insertion ou de mise à jour.</span><span class="sxs-lookup"><span data-stu-id="904e1-242">Generates an error when a value is specified for this attribute by the caller in the XML representation provided for a column set in an insert or update operation.</span></span>  
  
## <a name="security"></a><span data-ttu-id="904e1-243">Sécurité</span><span class="sxs-lookup"><span data-stu-id="904e1-243">Security</span></span>  
 <span data-ttu-id="904e1-244">Le modèle de sécurité pour un jeu de colonnes fonctionne de manière semblable au modèle de sécurité qui existe entre la table et les colonnes.</span><span class="sxs-lookup"><span data-stu-id="904e1-244">The security model for a column set works similar to the security model that exists between table and columns.</span></span> <span data-ttu-id="904e1-245">Les jeux de colonnes peuvent être visualisés comme une minitable et une opération de sélection est semblable à uneopération SELECT \* sur cette minitable.</span><span class="sxs-lookup"><span data-stu-id="904e1-245">Column sets can be visualized as a minitable and a select operation is like a SELECT \* operation on this minitable.</span></span> <span data-ttu-id="904e1-246">Mais la relation entre le jeu de colonnes et les colonnes éparses est une relation de regroupement plutôt qu'un conteneur strict.</span><span class="sxs-lookup"><span data-stu-id="904e1-246">But, the relationship between column set to sparse columns is a grouping relationship instead of strictly a container.</span></span> <span data-ttu-id="904e1-247">Le modèle de sécurité vérifie la sécurité sur la colonne de jeu de colonnes et honore les opérations DENY sur les colonnes éparses sous-jacentes.</span><span class="sxs-lookup"><span data-stu-id="904e1-247">The security model checks the security on the column set column, and honors the DENY operations on the underlying sparse columns.</span></span> <span data-ttu-id="904e1-248">Les caractéristiques supplémentaires du modèle de sécurité sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="904e1-248">Additional characteristics of the security model are as follows:</span></span>  
  
-   <span data-ttu-id="904e1-249">Des autorisations de sécurité peuvent être accordées et révoquées pour la colonne de jeu de colonnes, comme pour toute autre colonne dans la table.</span><span class="sxs-lookup"><span data-stu-id="904e1-249">Security permissions can be granted and revoked from the column set column, similar to any other column in the table.</span></span>  
  
-   <span data-ttu-id="904e1-250">Une valeur GRANT ou REVOKE d'autorisation SELECT, INSERT, UPDATE, DELETE et REFERENCES sur une colonne de jeu de colonnes n'est pas propagée aux colonnes membres sous-jacentes de ce jeu.</span><span class="sxs-lookup"><span data-stu-id="904e1-250">A GRANT or REVOKE of SELECT, INSERT, UPDATE, DELETE, and REFERENCES permission on a column set column does not propagate to the underlying member columns of that set.</span></span> <span data-ttu-id="904e1-251">Elle s'applique uniquement à l'utilisation de la colonne de jeu de colonnes.</span><span class="sxs-lookup"><span data-stu-id="904e1-251">It applies only to the usage of the column set column.</span></span> <span data-ttu-id="904e1-252">L'autorisation DENY sur un jeu de colonnes est propagée aux colonnes éparses sous-jacentes de la table.</span><span class="sxs-lookup"><span data-stu-id="904e1-252">DENY permission on a column set does propagate to the underlying sparse columns of the table.</span></span>  
  
-   <span data-ttu-id="904e1-253">L'exécution d'instructions SELECT, INSERT, UPDATE et DELETE sur la colonne de jeu de colonnes requiert que l'utilisateur ait des autorisations correspondantes sur la colonne de jeu de colonnes et également l'autorisation correspondante sur toutes les colonnes éparses dans la table.</span><span class="sxs-lookup"><span data-stu-id="904e1-253">Executing SELECT, INSERT, UPDATE, and DELETE statements on the column set column require that the user has corresponding permissions on the column set column, and also the corresponding permission on all the sparse columns in the table.</span></span> <span data-ttu-id="904e1-254">Étant donné que le jeu de colonnes représente toutes les colonnes éparses dans la table, vous devez avoir l'autorisation sur toutes les colonnes éparses, y compris celles que vous ne modifierez peut-être pas.</span><span class="sxs-lookup"><span data-stu-id="904e1-254">Because the column set represents all the sparse columns in the table, you must have permission on all the sparse columns, and this includes sparse columns that you might not be changing.</span></span>  
  
-   <span data-ttu-id="904e1-255">L'exécution d'une instruction REVOKE sur une colonne éparse ou un jeu de colonnes provoque l'application par défaut de la sécurité à leur objet parent.</span><span class="sxs-lookup"><span data-stu-id="904e1-255">Executing a REVOKE statement on a sparse column or column set defaults the security to their parent object.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="904e1-256">Exemples</span><span class="sxs-lookup"><span data-stu-id="904e1-256">Examples</span></span>  
 <span data-ttu-id="904e1-257">Dans les exemples suivants, une table de documents contient le jeu de colonnes commun `DocID` et `Title`.</span><span class="sxs-lookup"><span data-stu-id="904e1-257">In the following examples, a document table contains the common set of columns `DocID` and `Title`.</span></span> <span data-ttu-id="904e1-258">Le groupe Production souhaite avoir une colonne `ProductionSpecification` et `ProductionLocation` pour tous les documents de production.</span><span class="sxs-lookup"><span data-stu-id="904e1-258">The Production group wants a `ProductionSpecification` and `ProductionLocation` column for all production documents.</span></span> <span data-ttu-id="904e1-259">Le groupe Marketing souhaite avoir une colonne `MarketingSurveyGroup` pour les documents de marketing.</span><span class="sxs-lookup"><span data-stu-id="904e1-259">The Marketing group wants a `MarketingSurveyGroup` column for marketing documents.</span></span>  
  
### <a name="a-creating-a-table-that-has-a-column-set"></a><span data-ttu-id="904e1-260">R.</span><span class="sxs-lookup"><span data-stu-id="904e1-260">A.</span></span> <span data-ttu-id="904e1-261">Création d'une table qui a un jeu de colonnes</span><span class="sxs-lookup"><span data-stu-id="904e1-261">Creating a table that has a column set</span></span>  
 <span data-ttu-id="904e1-262">L'exemple suivant crée la table qui utilise des colonnes éparses et inclut le jeu de colonnes `SpecialPurposeColumns`.</span><span class="sxs-lookup"><span data-stu-id="904e1-262">The following example creates the table that uses sparse columns and includes the column set `SpecialPurposeColumns`.</span></span> <span data-ttu-id="904e1-263">L'exemple insère deux lignes dans la table, puis sélectionne des données de la table.</span><span class="sxs-lookup"><span data-stu-id="904e1-263">The example inserts two rows into the table, and then selects data from the table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="904e1-264">Cette table ne possède que cinq colonnes, de manière à simplifier son affichage et sa lecture.</span><span class="sxs-lookup"><span data-stu-id="904e1-264">This table has only five columns to make it easier to display and read.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
  
CREATE TABLE DocumentStoreWithColumnSet  
    (DocID int PRIMARY KEY,  
     Title varchar(200) NOT NULL,  
     ProductionSpecification varchar(20) SPARSE NULL,  
     ProductionLocation smallint SPARSE NULL,  
     MarketingSurveyGroup varchar(20) SPARSE NULL,  
     MarketingProgramID int SPARSE NULL,  
     SpecialPurposeColumns XML COLUMN_SET FOR ALL_SPARSE_COLUMNS);  
GO  
```  
  
### <a name="b-inserting-data-to-a-table-by-using-the-names-of-the-sparse-columns"></a><span data-ttu-id="904e1-265">B.</span><span class="sxs-lookup"><span data-stu-id="904e1-265">B.</span></span> <span data-ttu-id="904e1-266">Insertion de données dans une table en utilisant les noms des colonnes éparses</span><span class="sxs-lookup"><span data-stu-id="904e1-266">Inserting data to a table by using the names of the sparse columns</span></span>  
 <span data-ttu-id="904e1-267">Les exemples suivants insèrent deux lignes dans la table créée dans l'exemple A. Les exemples utilisent les noms des colonnes éparses et ne font pas référence au jeu de colonnes.</span><span class="sxs-lookup"><span data-stu-id="904e1-267">The following examples insert two rows into the table that is created in example A. The examples use the names of the sparse columns and do not reference the column set.</span></span>  
  
```  
INSERT DocumentStoreWithColumnSet (DocID, Title, ProductionSpecification, ProductionLocation)  
VALUES (1, 'Tire Spec 1', 'AXZZ217', 27);  
GO  
  
INSERT DocumentStoreWithColumnSet (DocID, Title, MarketingSurveyGroup)  
VALUES (2, 'Survey 2142', 'Men 25 - 35');  
GO  
```  
  
### <a name="c-inserting-data-to-a-table-by-using-the-name-of-the-column-set"></a><span data-ttu-id="904e1-268">C.</span><span class="sxs-lookup"><span data-stu-id="904e1-268">C.</span></span> <span data-ttu-id="904e1-269">Insertion de données dans une table en utilisant le nom du jeu de colonnes</span><span class="sxs-lookup"><span data-stu-id="904e1-269">Inserting data to a table by using the name of the column set</span></span>  
 <span data-ttu-id="904e1-270">L'exemple suivant insère une troisième ligne dans la table créée dans l'exemple A. Cette fois, les noms des colonnes éparses ne sont pas utilisés.</span><span class="sxs-lookup"><span data-stu-id="904e1-270">The following example inserts a third row into the table that is created in example A. This time the names of the sparse columns are not used.</span></span> <span data-ttu-id="904e1-271">Au lieu de cela, le nom du jeu de colonnes est utilisé et l'insertion fournit les valeurs pour deux des quatre colonnes éparses au format XML.</span><span class="sxs-lookup"><span data-stu-id="904e1-271">Instead, the name of the column set is used, and the insert provides the values for two of the four sparse columns in XML format.</span></span>  
  
```  
INSERT DocumentStoreWithColumnSet (DocID, Title, SpecialPurposeColumns)  
VALUES (3, 'Tire Spec 2', '<ProductionSpecification>AXW9R411</ProductionSpecification><ProductionLocation>38</ProductionLocation>');  
GO  
```  
  
### <a name="d-observing-the-results-of-a-column-set-when-select--is-used"></a><span data-ttu-id="904e1-272">D.</span><span class="sxs-lookup"><span data-stu-id="904e1-272">D.</span></span> <span data-ttu-id="904e1-273">Observation des résultats d'un jeu de colonnes lorsque SELECT \* est utilisé</span><span class="sxs-lookup"><span data-stu-id="904e1-273">Observing the results of a column set when SELECT \* is used</span></span>  
 <span data-ttu-id="904e1-274">L'exemple suivant sélectionne toutes les colonnes de la table qui contient un jeu de colonnes.</span><span class="sxs-lookup"><span data-stu-id="904e1-274">The following example selects all the columns from the table that contains a column set.</span></span> <span data-ttu-id="904e1-275">Il retourne une colonne XML avec les valeurs combinées des colonnes éparses.</span><span class="sxs-lookup"><span data-stu-id="904e1-275">It returns an XML column with the combined values of the sparse columns.</span></span> <span data-ttu-id="904e1-276">Il ne retourne pas les colonnes éparses individuellement.</span><span class="sxs-lookup"><span data-stu-id="904e1-276">It does not return the sparse columns individually.</span></span>  
  
```  
SELECT DocID, Title, SpecialPurposeColumns FROM DocumentStoreWithColumnSet ;  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `DocID Title        SpecialPurposeColumns`  
  
 `1      Tire Spec 1  <ProductionSpecification>AXZZ217</ProductionSpecification><ProductionLocation>27</ProductionLocation>`  
  
 `2      Survey 2142  <MarketingSurveyGroup>Men 25 - 35</MarketingSurveyGroup>`  
  
 `3      Tire Spec 2  <ProductionSpecification>AXW9R411</ProductionSpecification><ProductionLocation>38</ProductionLocation>`  
  
### <a name="e-observing-the-results-of-selecting-the-column-set-by-name"></a><span data-ttu-id="904e1-277">E.</span><span class="sxs-lookup"><span data-stu-id="904e1-277">E.</span></span> <span data-ttu-id="904e1-278">Observation des résultats de la sélection du jeu de colonnes par nom</span><span class="sxs-lookup"><span data-stu-id="904e1-278">Observing the results of selecting the column set by name</span></span>  
 <span data-ttu-id="904e1-279">Le département Production ne s'intéressant pas aux données de marketing, cet exemple ajoute une clause `WHERE` afin de restreindre la sortie.</span><span class="sxs-lookup"><span data-stu-id="904e1-279">Because the Production department is not interested in the marketing data, this example adds a `WHERE` clause to restrict the output.</span></span> <span data-ttu-id="904e1-280">L'exemple utilise le nom du jeu de colonnes.</span><span class="sxs-lookup"><span data-stu-id="904e1-280">The example uses the name of the column set.</span></span>  
  
```  
SELECT DocID, Title, SpecialPurposeColumns  
FROM DocumentStoreWithColumnSet  
WHERE ProductionSpecification IS NOT NULL ;  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `DocID Title        SpecialPurposeColumns`  
  
 `1     Tire Spec 1  <ProductionSpecification>AXZZ217</ProductionSpecification><ProductionLocation>27</ProductionLocation>`  
  
 `3     Tire Spec 2  <ProductionSpecification>AXW9R411</ProductionSpecification><ProductionLocation>38</ProductionLocation>`  
  
### <a name="f-observing-the-results-of-selecting-sparse-columns-by-name"></a><span data-ttu-id="904e1-281">F.</span><span class="sxs-lookup"><span data-stu-id="904e1-281">F.</span></span> <span data-ttu-id="904e1-282">Observation des résultats de la sélection des colonnes éparses par nom</span><span class="sxs-lookup"><span data-stu-id="904e1-282">Observing the results of selecting sparse columns by name</span></span>  
 <span data-ttu-id="904e1-283">Lorsqu'une table contient un jeu de colonnes, vous pouvez tout de même interroger la table en utilisant les noms de colonnes individuellement, comme illustré dans l'exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="904e1-283">When a table contains a column set, you can still query the table by using the individual column names as shown in the following example.</span></span>  
  
```  
SELECT DocID, Title, ProductionSpecification, ProductionLocation   
FROM DocumentStoreWithColumnSet  
WHERE ProductionSpecification IS NOT NULL ;  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `DocID Title        ProductionSpecification ProductionLocation`  
  
 `1     Tire Spec 1  AXZZ217                 27`  
  
 `3     Tire Spec 2  AXW9R411                38`  
  
### <a name="g-updating-a-table-by-using-a-column-set"></a><span data-ttu-id="904e1-284">G.</span><span class="sxs-lookup"><span data-stu-id="904e1-284">G.</span></span> <span data-ttu-id="904e1-285">Mise à jour d'une table en utilisant un jeu de colonnes</span><span class="sxs-lookup"><span data-stu-id="904e1-285">Updating a table by using a column set</span></span>  
 <span data-ttu-id="904e1-286">L'exemple suivant met à jour le troisième enregistrement avec les nouvelles valeurs pour les deux colonnes éparses utilisées par cette ligne.</span><span class="sxs-lookup"><span data-stu-id="904e1-286">The following example updates the third record with new values for both sparse columns that are used by that row.</span></span>  
  
```  
UPDATE DocumentStoreWithColumnSet  
SET SpecialPurposeColumns = '<ProductionSpecification>ZZ285W</ProductionSpecification><ProductionLocation>38</ProductionLocation>'  
WHERE DocID = 3 ;  
GO  
```  
  
> [!IMPORTANT]  
>  <span data-ttu-id="904e1-287">Une instruction UPDATE qui utilise un jeu de colonnes met à jour toutes les colonnes éparses dans la table.</span><span class="sxs-lookup"><span data-stu-id="904e1-287">An UPDATE statement that uses a column set updates all the sparse columns in the table.</span></span> <span data-ttu-id="904e1-288">Les colonnes éparses qui ne sont pas référencées sont mises à jour avec la valeur NULL.</span><span class="sxs-lookup"><span data-stu-id="904e1-288">Sparse columns that are not referenced are updated to NULL.</span></span>  
  
 <span data-ttu-id="904e1-289">L'exemple suivant met à jour le troisième enregistrement, mais spécifie uniquement la valeur d'une des deux colonnes remplies.</span><span class="sxs-lookup"><span data-stu-id="904e1-289">The following example updates the third record, but only specifies the value of one of the two populated columns.</span></span> <span data-ttu-id="904e1-290">La deuxième colonne `ProductionLocation` n'est pas incluse dans l'instruction `UPDATE` et est mise à jour avec la valeur NULL.</span><span class="sxs-lookup"><span data-stu-id="904e1-290">The second column `ProductionLocation` is not included in the `UPDATE` statement and is updated to NULL.</span></span>  
  
```  
UPDATE DocumentStoreWithColumnSet  
SET SpecialPurposeColumns = '<ProductionSpecification>ZZ285W</ProductionSpecification>'  
WHERE DocID = 3 ;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="904e1-291">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="904e1-291">See Also</span></span>  
 [<span data-ttu-id="904e1-292">Utiliser des colonnes éparses</span><span class="sxs-lookup"><span data-stu-id="904e1-292">Use Sparse Columns</span></span>](use-sparse-columns.md)  
  
  
