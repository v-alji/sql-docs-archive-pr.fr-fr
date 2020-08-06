---
title: Afficher les propriétés des statistiques | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
f1_keywords:
- sql12.swb.statistics.details.f1
helpviewer_keywords:
- viewing statistics properties
- statistics [SQL Server], viewing properties
ms.assetid: 0eaa2101-006e-4015-9979-3468b50e0aaa
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 63cabc5d8844982604993acac6a791317ee36925
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613359"
---
# <a name="view-statistics-properties"></a><span data-ttu-id="82c34-102">Afficher les propriétés des statistiques</span><span class="sxs-lookup"><span data-stu-id="82c34-102">View Statistics Properties</span></span>
  <span data-ttu-id="82c34-103">Vous pouvez afficher les statistiques d'optimisation de la requête actuelle pour une table ou une vue indexée dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="82c34-103">You can display current query optimization statistics for a table or indexed view in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="82c34-104">Les objets de statistiques incluent un en-tête contenant des métadonnées sur les statistiques, un histogramme indiquant la distribution des valeurs dans la première colonne clé de l'objet des statistiques, et un vecteur de densité destiné à mesurer la corrélation entre les colonnes.</span><span class="sxs-lookup"><span data-stu-id="82c34-104">Statistics objects include a header with metadata about the statistics, a histogram with the distribution of values in the first key column of the statistics object, and a density vector to measure cross-column correlation.</span></span> <span data-ttu-id="82c34-105">Pour plus d’informations sur les histogrammes et les vecteurs de densité, consultez [DBCC SHOW_STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-show-statistics-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="82c34-105">For more information about histograms and density vectors, see [DBCC SHOW_STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-show-statistics-transact-sql)</span></span>  
  
 <span data-ttu-id="82c34-106">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="82c34-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="82c34-107">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="82c34-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="82c34-108">Sécurité</span><span class="sxs-lookup"><span data-stu-id="82c34-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="82c34-109">**Pour afficher les propriétés des statistiques, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="82c34-109">**To view statistics properties, using:**</span></span>  
  
     [<span data-ttu-id="82c34-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="82c34-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="82c34-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="82c34-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="82c34-112">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="82c34-112">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="82c34-113">Sécurité</span><span class="sxs-lookup"><span data-stu-id="82c34-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="82c34-114">Autorisations</span><span class="sxs-lookup"><span data-stu-id="82c34-114">Permissions</span></span>  
 <span data-ttu-id="82c34-115">Pour afficher l’objet des statistiques, l’utilisateur doit être propriétaire de la table ou être membre du rôle serveur fixe `sysadmin`, du rôle de base de données fixe `db_owner` ou du rôle de base de données fixe `db_ddladmin`.</span><span class="sxs-lookup"><span data-stu-id="82c34-115">In order to view the statistics object, the user must own the table or the user must be a member of the `sysadmin` fixed server role, the `db_owner` fixed database role, or the `db_ddladmin` fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="82c34-116">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="82c34-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-statistics-properties"></a><span data-ttu-id="82c34-117">Pour afficher les propriétés des statistiques</span><span class="sxs-lookup"><span data-stu-id="82c34-117">To view statistics properties</span></span>  
  
1.  <span data-ttu-id="82c34-118">Dans l' **Explorateur d'objets**, cliquez sur le signe plus (+) pour développer la base de données dans laquelle vous souhaitez créer une nouvelle statistique.</span><span class="sxs-lookup"><span data-stu-id="82c34-118">In **Object Explorer**, click the plus sign to expand the database in which you want to create a new statistic.</span></span>  
  
2.  <span data-ttu-id="82c34-119">Cliquez sur le signe plus (+) pour développer le dossier **Tables** .</span><span class="sxs-lookup"><span data-stu-id="82c34-119">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="82c34-120">Cliquez sur le signe plus (+) pour développer la table dans laquelle vous souhaitez afficher les propriétés de la statistique.</span><span class="sxs-lookup"><span data-stu-id="82c34-120">Click the plus sign to expand the table in which you want to view the statistic's properties.</span></span>  
  
4.  <span data-ttu-id="82c34-121">Cliquez sur le signe plus (+) pour développer le dossier **Statistiques** .</span><span class="sxs-lookup"><span data-stu-id="82c34-121">Click the plus sign to expand the **Statistics** folder.</span></span>  
  
5.  <span data-ttu-id="82c34-122">Cliquez avec le bouton droit sur l’objet Statistiques dont vous voulez afficher les propriétés, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="82c34-122">Right-click the Statistics object of which you want to view the properties and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="82c34-123">Dans la boîte de dialogue **Propriétés des statistiques -** _nom_statistiques_, dans le volet **Sélectionner une page** , sélectionnez **Détails**.</span><span class="sxs-lookup"><span data-stu-id="82c34-123">In the **Statistics Properties -** _statistics_name_ dialog box, in the **Select a page** pane, select **Details**.</span></span>  
  
     <span data-ttu-id="82c34-124">Les propriétés suivantes s’affichent dans la page **Détails** de la boîte de dialogue **Propriétés des statistiques -** _nom_statistiques_.</span><span class="sxs-lookup"><span data-stu-id="82c34-124">The following properties show on the **Details** page in the **Statistics Properties -** _statistics_name_ dialog box.</span></span>  
  
     <span data-ttu-id="82c34-125">**Nom de la table**</span><span class="sxs-lookup"><span data-stu-id="82c34-125">**Table Name**</span></span>  
     <span data-ttu-id="82c34-126">Affiche le nom de la table décrite par les statistiques.</span><span class="sxs-lookup"><span data-stu-id="82c34-126">Displays the name of the table described by the statistics.</span></span>  
  
     <span data-ttu-id="82c34-127">**Nom des statistiques**</span><span class="sxs-lookup"><span data-stu-id="82c34-127">**Statistics Name**</span></span>  
     <span data-ttu-id="82c34-128">Spécifie le nom de l'objet de base de données dans lequel les statistiques sont stockées.</span><span class="sxs-lookup"><span data-stu-id="82c34-128">Displays the name of the database object where the statistics are stored.</span></span>  
  
     <span data-ttu-id="82c34-129">**Statistiques de l’INDEX statistics_name**</span><span class="sxs-lookup"><span data-stu-id="82c34-129">**Statistics for INDEXstatistics_name**</span></span>  
     <span data-ttu-id="82c34-130">Cette zone de texte affiche les propriétés retournées par l'objet de statistiques.</span><span class="sxs-lookup"><span data-stu-id="82c34-130">This text box shows the properties returned from the statistics object.</span></span> <span data-ttu-id="82c34-131">Ces propriétés sont divisées en trois sections : En-tête des statistiques, vecteur de densité et histogramme.</span><span class="sxs-lookup"><span data-stu-id="82c34-131">This properties are divided into three sections: Stats Header, Density Vector, and Histogram.</span></span>  
  
     <span data-ttu-id="82c34-132">Les informations suivantes décrivent les colonnes retournées dans le jeu de résultats de l'en-tête de statistiques.</span><span class="sxs-lookup"><span data-stu-id="82c34-132">The following information describes the columns returned in the result set for the Stats Header.</span></span>  
  
     <span data-ttu-id="82c34-133">**Nom**</span><span class="sxs-lookup"><span data-stu-id="82c34-133">**Name**</span></span>  
     <span data-ttu-id="82c34-134">Nom de l'objet de statistiques.</span><span class="sxs-lookup"><span data-stu-id="82c34-134">Name of the statistics object.</span></span>  
  
     <span data-ttu-id="82c34-135">**Updated**</span><span class="sxs-lookup"><span data-stu-id="82c34-135">**Updated**</span></span>  
     <span data-ttu-id="82c34-136">Date et heure de la dernière mise à jour des statistiques.</span><span class="sxs-lookup"><span data-stu-id="82c34-136">Date and time the statistics were last updated.</span></span>  
  
     <span data-ttu-id="82c34-137">**Lignes**</span><span class="sxs-lookup"><span data-stu-id="82c34-137">**Rows**</span></span>  
     <span data-ttu-id="82c34-138">Nombre total de lignes dans la table ou la vue indexée au moment de la dernière mise à jour des statistiques.</span><span class="sxs-lookup"><span data-stu-id="82c34-138">Total number of rows in the table or indexed view when the statistics were last updated.</span></span> <span data-ttu-id="82c34-139">Si les statistiques sont filtrées ou correspondent à un index filtré, le nombre de lignes peut être inférieur à celui de la table.</span><span class="sxs-lookup"><span data-stu-id="82c34-139">If the statistics are filtered or correspond to a filtered index, the number of rows might be less than the number of rows in the table.</span></span>  
  
     <span data-ttu-id="82c34-140">**Lignes échantillonnées**</span><span class="sxs-lookup"><span data-stu-id="82c34-140">**Rows Sampled**</span></span>  
     <span data-ttu-id="82c34-141">Nombre total de lignes échantillonnées pour le calcul des statistiques.</span><span class="sxs-lookup"><span data-stu-id="82c34-141">Total number of rows sampled for statistics calculations.</span></span> <span data-ttu-id="82c34-142">Si Rows Sampled < Rows, l'histogramme et les résultats de densité affichés sont des estimations basées sur les lignes échantillonnées.</span><span class="sxs-lookup"><span data-stu-id="82c34-142">If Rows Sampled < Rows, the displayed histogram and density results are estimates based on the sampled rows.</span></span>  
  
     <span data-ttu-id="82c34-143">**Étapes**</span><span class="sxs-lookup"><span data-stu-id="82c34-143">**Steps**</span></span>  
     <span data-ttu-id="82c34-144">Nombre d'étapes dans l'histogramme.</span><span class="sxs-lookup"><span data-stu-id="82c34-144">Number of steps in the histogram.</span></span> <span data-ttu-id="82c34-145">Chaque étape couvre une plage de valeurs de colonnes suivie d'une valeur de colonne de limite supérieure.</span><span class="sxs-lookup"><span data-stu-id="82c34-145">Each step spans a range of column values followed by an upper bound column value.</span></span> <span data-ttu-id="82c34-146">Les étapes d'histogramme sont définies sur la première colonne clé des statistiques.</span><span class="sxs-lookup"><span data-stu-id="82c34-146">The histogram steps are defined on the first key column in the statistics.</span></span> <span data-ttu-id="82c34-147">Le nombre maximal d'étapes est 200.</span><span class="sxs-lookup"><span data-stu-id="82c34-147">The maximum number of steps is 200.</span></span>  
  
     <span data-ttu-id="82c34-148">**Densité**</span><span class="sxs-lookup"><span data-stu-id="82c34-148">**Density**</span></span>  
     <span data-ttu-id="82c34-149">La formule 1 / *valeurs distinctes* est utilisée pour toutes les valeurs de la première colonne clé de l’objet de statistiques, à l’exception des valeurs limites de l’histogramme.</span><span class="sxs-lookup"><span data-stu-id="82c34-149">Calculated as 1 / *distinct values* for all values in the first key column of the statistics object, excluding the histogram boundary values.</span></span> <span data-ttu-id="82c34-150">Cette valeur de densité n'est pas utilisée par l'optimiseur de requête ; elle est affichée pour la compatibilité descendante avec les versions antérieures à SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="82c34-150">This Density value is not used by the query optimizer and is displayed for backward compatibility with versions before SQL Server 2008.</span></span>  
  
     <span data-ttu-id="82c34-151">**Longueur moyenne d'une clé**</span><span class="sxs-lookup"><span data-stu-id="82c34-151">**Average Key Length**</span></span>  
     <span data-ttu-id="82c34-152">Nombre moyen d'octets par valeur pour toutes les colonnes clés de l'objet de statistiques.</span><span class="sxs-lookup"><span data-stu-id="82c34-152">Average number of bytes per value for all of the key columns in the statistics object.</span></span>  
  
     <span data-ttu-id="82c34-153">**String Index**</span><span class="sxs-lookup"><span data-stu-id="82c34-153">**String Index**</span></span>  
     <span data-ttu-id="82c34-154">La valeur Yes indique que l'objet de statistiques contient des statistiques de résumé de chaîne pour améliorer les estimations de cardinalité des prédicats de requête qui utilisent l'opérateur LIKE ; c'est le cas par exemple de `WHERE ProductName LIKE '%Bike'`.</span><span class="sxs-lookup"><span data-stu-id="82c34-154">Yes indicates the statistics object contains string summary statistics to improve the cardinality estimates for query predicates that use the LIKE operator; for example, `WHERE ProductName LIKE '%Bike'`.</span></span> <span data-ttu-id="82c34-155">Les statistiques de résumé de chaîne sont stockées à l’écart de l’histogramme et créées sur la première colonne clé de l’objet de statistiques quand il est de type **char**, **varchar**, **nchar**, **nvarchar**, **varchar(max)** , **nvarchar(max)** , **text**ou **ntext**.</span><span class="sxs-lookup"><span data-stu-id="82c34-155">String summary statistics are stored separately from the histogram and are created on the first key column of the statistics object when it is of type **char**, **varchar**, **nchar**, **nvarchar**, **varchar(max)**, **nvarchar(max)**, **text**, or **ntext**.</span></span>  
  
     <span data-ttu-id="82c34-156">**Expression de filtre**</span><span class="sxs-lookup"><span data-stu-id="82c34-156">**Filter Expression**</span></span>  
     <span data-ttu-id="82c34-157">Prédicat pour le sous-ensemble des lignes de table incluses dans l'objet de statistiques.</span><span class="sxs-lookup"><span data-stu-id="82c34-157">Predicate for the subset of table rows included in the statistics object.</span></span> <span data-ttu-id="82c34-158">NULL = statistiques non filtrées.</span><span class="sxs-lookup"><span data-stu-id="82c34-158">NULL = non-filtered statistics.</span></span>  
  
     <span data-ttu-id="82c34-159">**Lignes non filtrées**</span><span class="sxs-lookup"><span data-stu-id="82c34-159">**Unfiltered Rows**</span></span>  
     <span data-ttu-id="82c34-160">Nombre total de lignes dans la table avant l'application de l'expression de filtre.</span><span class="sxs-lookup"><span data-stu-id="82c34-160">Total number of rows in the table before applying the filter expression.</span></span> <span data-ttu-id="82c34-161">Si Expression de filtre a la valeur NULL, Lignes non filtrées est égal à Lignes.</span><span class="sxs-lookup"><span data-stu-id="82c34-161">If Filter Expression is NULL, Unfiltered Rows is equal to Rows.</span></span>  
  
     <span data-ttu-id="82c34-162">Les informations suivantes décrivent les colonnes retournées dans le jeu de résultats du vecteur de densité.</span><span class="sxs-lookup"><span data-stu-id="82c34-162">The following information describes the columns returned in the result set for the Density Vector.</span></span>  
  
     <span data-ttu-id="82c34-163">**Toutes les densités**</span><span class="sxs-lookup"><span data-stu-id="82c34-163">**All Density**</span></span>  
     <span data-ttu-id="82c34-164">La densité est calculée selon la formule 1 / *valeurs distinctes*.</span><span class="sxs-lookup"><span data-stu-id="82c34-164">Density is 1 / *distinct values*.</span></span> <span data-ttu-id="82c34-165">Les résultats affichent la densité pour chaque préfixe des colonnes de l'objet de statistiques, à raison d'une ligne par densité.</span><span class="sxs-lookup"><span data-stu-id="82c34-165">Results display density for each prefix of columns in the statistics object, one row per density.</span></span> <span data-ttu-id="82c34-166">Une valeur distincte est une liste distincte des valeurs de colonnes par ligne et par préfixe de colonne.</span><span class="sxs-lookup"><span data-stu-id="82c34-166">A distinct value is a distinct list of the column values per row and per columns prefix.</span></span> <span data-ttu-id="82c34-167">Par exemple, si l'objet de statistiques contient des colonnes clés (A, B, C), les résultats rapportent la densité des listes distinctes de valeurs dans chacun des préfixes de colonnes suivants : (A), (A,B) et (A, B, C).</span><span class="sxs-lookup"><span data-stu-id="82c34-167">For example, if the statistics object contains key columns (A, B, C), the results report the density of the distinct lists of values in each of these column prefixes: (A), (A,B), and (A, B, C).</span></span> <span data-ttu-id="82c34-168">Avec le préfixe (A, B, C), chacune des listes suivantes est une liste de valeurs distincte : (3, 5, 6), (4, 4, 6), (4, 5, 6), (4, 5, 7).</span><span class="sxs-lookup"><span data-stu-id="82c34-168">Using the prefix (A, B, C), each of these lists is a distinct value list: (3, 5, 6), (4, 4, 6), (4, 5, 6), (4, 5, 7).</span></span> <span data-ttu-id="82c34-169">Avec le préfixe (A, B) les listes de valeurs distinctes suivantes sont associées aux mêmes valeurs de colonnes : (3, 5), (4, 4) et (4, 5).</span><span class="sxs-lookup"><span data-stu-id="82c34-169">Using the prefix (A, B) the same column values have these distinct value lists: (3, 5), (4, 4), and (4, 5).</span></span>  
  
     <span data-ttu-id="82c34-170">**Longueur moyenne**</span><span class="sxs-lookup"><span data-stu-id="82c34-170">**Average Length**</span></span>  
     <span data-ttu-id="82c34-171">Longueur moyenne, en octets, pour le stockage d'une liste des valeurs de colonnes pour le préfixe de colonne.</span><span class="sxs-lookup"><span data-stu-id="82c34-171">Average length, in bytes, to store a list of the column values for the column prefix.</span></span> <span data-ttu-id="82c34-172">Par exemple, si les valeurs dans la liste (3, 5, 6) nécessitent 4 octets chacune, la longueur est égale à 12 octets.</span><span class="sxs-lookup"><span data-stu-id="82c34-172">For example, if the values in the list (3, 5, 6) each require 4 bytes the length is 12 bytes.</span></span>  
  
     <span data-ttu-id="82c34-173">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="82c34-173">**Columns**</span></span>  
     <span data-ttu-id="82c34-174">Noms des colonnes dans le préfixe dont les valeurs Toutes les densités et Longueur moyenne sont affichées.</span><span class="sxs-lookup"><span data-stu-id="82c34-174">Names of columns in the prefix for which All density and Average length are displayed.</span></span>  
  
     <span data-ttu-id="82c34-175">Les informations suivantes décrivent les colonnes retournées dans le jeu de résultats de l'histogramme.</span><span class="sxs-lookup"><span data-stu-id="82c34-175">The following information describes the columns returned in the result set for the Histogram.</span></span>  
  
     <span data-ttu-id="82c34-176">**RANGE_HI_KEY**</span><span class="sxs-lookup"><span data-stu-id="82c34-176">**RANGE_HI_KEY**</span></span>  
     <span data-ttu-id="82c34-177">Valeur de colonne de limite supérieure pour une étape d'histogramme.</span><span class="sxs-lookup"><span data-stu-id="82c34-177">Upper bound column value for a histogram step.</span></span> <span data-ttu-id="82c34-178">La valeur de colonne est également appelée « valeur de clé ».</span><span class="sxs-lookup"><span data-stu-id="82c34-178">The column value is also called a key value.</span></span>  
  
     <span data-ttu-id="82c34-179">**RANGE_ROWS**</span><span class="sxs-lookup"><span data-stu-id="82c34-179">**RANGE_ROWS**</span></span>  
     <span data-ttu-id="82c34-180">Nombre estimé de lignes dont la valeur de colonne est comprise dans une étape d'histogramme, à l'exception de la limite supérieure.</span><span class="sxs-lookup"><span data-stu-id="82c34-180">Estimated number of rows whose column value falls within a histogram step, excluding the upper bound.</span></span>  
  
     <span data-ttu-id="82c34-181">**EQ_ROWS**</span><span class="sxs-lookup"><span data-stu-id="82c34-181">**EQ_ROWS**</span></span>  
     <span data-ttu-id="82c34-182">Nombre estimé de lignes dont la valeur de colonne est égale à la limite supérieure de l'étape d'histogramme.</span><span class="sxs-lookup"><span data-stu-id="82c34-182">Estimated number of rows whose column value equals the upper bound of the histogram step.</span></span>  
  
     <span data-ttu-id="82c34-183">**DISTINCT_RANGE_ROWS**</span><span class="sxs-lookup"><span data-stu-id="82c34-183">**DISTINCT_RANGE_ROWS**</span></span>  
     <span data-ttu-id="82c34-184">Nombre estimé de lignes ayant une valeur de colonne distincte dans une étape d'histogramme, à l'exception de la limite supérieure.</span><span class="sxs-lookup"><span data-stu-id="82c34-184">Estimated number of rows with a distinct column value within a histogram step, excluding the upper bound.</span></span>  
  
     <span data-ttu-id="82c34-185">**AVG_RANGE_ROWS**</span><span class="sxs-lookup"><span data-stu-id="82c34-185">**AVG_RANGE_ROWS**</span></span>  
     <span data-ttu-id="82c34-186">Nombre moyen de lignes ayant des valeurs de colonnes dupliquées dans une étape d'histogramme, à l'exception de la limite supérieure (RANGE_ROWS / DISTINCT_RANGE_ROWS pour DISTINCT_RANGE_ROWS > 0).</span><span class="sxs-lookup"><span data-stu-id="82c34-186">Average number of rows with duplicate column values within a histogram step, excluding the upper bound (RANGE_ROWS / DISTINCT_RANGE_ROWS for DISTINCT_RANGE_ROWS > 0).</span></span>  
  
7.  <span data-ttu-id="82c34-187">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="82c34-187">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="82c34-188">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="82c34-188">Using Transact-SQL</span></span>  
  
#### <a name="to-view-statistics-properties"></a><span data-ttu-id="82c34-189">Pour afficher les propriétés des statistiques</span><span class="sxs-lookup"><span data-stu-id="82c34-189">To view statistics properties</span></span>  
  
1.  <span data-ttu-id="82c34-190">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="82c34-190">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="82c34-191">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="82c34-191">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="82c34-192">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="82c34-192">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- The following example displays all statistics information for the AK_Address_rowguid index of the Person.Address table.   
    DBCC SHOW_STATISTICS ("Person.Address", AK_Address_rowguid);   
    GO  
    ```  
  
 <span data-ttu-id="82c34-193">Pour plus d’informations, consultez [DBCC SHOW_STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-show-statistics-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="82c34-193">For more information, see [DBCC SHOW_STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-show-statistics-transact-sql).</span></span>  
  
#### <a name="to-find-all-of-the-statistics-on-a-table-or-view"></a><span data-ttu-id="82c34-194">Pour rechercher toutes les statistiques sur une table ou une vue</span><span class="sxs-lookup"><span data-stu-id="82c34-194">To find all of the statistics on a table or view</span></span>  
  
1.  <span data-ttu-id="82c34-195">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="82c34-195">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="82c34-196">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="82c34-196">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="82c34-197">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="82c34-197">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    /*Gets the following information: name and ID of the statistics, whether the statistics were created automatically or by the user, whether the statistics were created with the NORECOMPUTE option, and whether the statistics have a filter and, if so, what that filter is.  
    */  
    SELECT name AS statistics_name  
        ,stats_id  
        ,auto_created  
        ,user_created  
        ,no_recompute  
        ,has_filter  
        ,filter_definition  
    -- using the sys.stats catalog view  
    FROM sys.stats  
    -- for the Sales.SpecialOffer table  
    WHERE object_id = OBJECT_ID('Sales.SpecialOffer');  
    GO  
    ```  
  
 <span data-ttu-id="82c34-198">Pour plus d’informations, consultez [sys.stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-stats-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="82c34-198">For more information, see [sys.stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-stats-transact-sql).</span></span>  
  
  
