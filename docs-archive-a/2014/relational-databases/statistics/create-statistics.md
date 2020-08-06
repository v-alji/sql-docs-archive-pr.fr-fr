---
title: Créer des statistiques | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
f1_keywords:
- sql12.swb.statistics.propertis.f1
- sql12.swb.statistics.filter.f1
- sql12.swb.stat.properties.f1
- sql12.swb.stat.columns.f1
helpviewer_keywords:
- creating statistics
- statistics [SQL Server], creating
ms.assetid: 95a455fb-664d-4c95-851e-c6b62d7ebe04
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 230bd4d840c3d59dc1267dd6801754b68386cb32
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613373"
---
# <a name="create-statistics"></a><span data-ttu-id="4ad06-102">Créer des statistiques</span><span class="sxs-lookup"><span data-stu-id="4ad06-102">Create Statistics</span></span>
  <span data-ttu-id="4ad06-103">Vous pouvez créer des statistiques d'optimisation de requête sur une ou plusieurs colonnes d'une table ou d'une vue indexée dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4ad06-103">You can create query optimization statistics on one or more columns of a table or indexed view in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="4ad06-104">Pour la plupart des requêtes, l'optimiseur de requête génère déjà les statistiques utiles à un plan de requête de haute qualité ; dans certains cas, vous devez créer des statistiques supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="4ad06-104">For most queries, the query optimizer already generates the necessary statistics for a high-quality query plan; in a few cases, you need to create additional statistics.</span></span>  
  
 <span data-ttu-id="4ad06-105">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="4ad06-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="4ad06-106">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="4ad06-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="4ad06-107">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="4ad06-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="4ad06-108">Sécurité</span><span class="sxs-lookup"><span data-stu-id="4ad06-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="4ad06-109">**Pour créer des statistiques, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="4ad06-109">**To create statistics, using:**</span></span>  
  
     [<span data-ttu-id="4ad06-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4ad06-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="4ad06-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4ad06-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4ad06-112">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="4ad06-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="4ad06-113">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="4ad06-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="4ad06-114">Avant de créer des statistiques avec l'instruction CREATE STATISTICS, vérifiez que l'option AUTO_CREATE_STATISTICS est définie au niveau de la base de données.</span><span class="sxs-lookup"><span data-stu-id="4ad06-114">Before creating statistics with the CREATE STATISTICS statement, verify that the AUTO_CREATE_STATISTICS option is set at the database level.</span></span> <span data-ttu-id="4ad06-115">Cela garantit que l'optimiseur de requête continue de créer régulièrement des statistiques de colonnes uniques pour les colonnes de prédicat de requête.</span><span class="sxs-lookup"><span data-stu-id="4ad06-115">This will ensure that the query optimizer continues to routinely create single-column statistics for query predicate columns.</span></span>  
  
-   <span data-ttu-id="4ad06-116">Vous pouvez afficher jusqu'à 32 colonnes par objet de statistiques.</span><span class="sxs-lookup"><span data-stu-id="4ad06-116">You can list up to 32 columns per statistics object.</span></span>  
  
-   <span data-ttu-id="4ad06-117">Vous ne pouvez pas supprimer, renommer ni modifier la définition d'une colonne de table définie dans un prédicat de statistiques filtrées.</span><span class="sxs-lookup"><span data-stu-id="4ad06-117">You cannot drop, rename, or alter the definition of a table column that is defined in a filtered statistics predicate.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4ad06-118">Sécurité</span><span class="sxs-lookup"><span data-stu-id="4ad06-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4ad06-119">Autorisations</span><span class="sxs-lookup"><span data-stu-id="4ad06-119">Permissions</span></span>  
 <span data-ttu-id="4ad06-120">Nécessite que l’utilisateur soit le propriétaire de la table ou de la vue indexée ou qu’il soit membre d’un des rôles suivants : rôle serveur fixe **sysadmin** , rôle de base de données fixe **db_owner** ou rôle de base de données fixe **db_ddladmin** .</span><span class="sxs-lookup"><span data-stu-id="4ad06-120">Requires that the user be the table or indexed view owner, or a member of one of the following roles: **sysadmin** fixed server role, **db_owner** fixed database role, or the **db_ddladmin** fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4ad06-121">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4ad06-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-statistics"></a><span data-ttu-id="4ad06-122">Pour créer des statistiques</span><span class="sxs-lookup"><span data-stu-id="4ad06-122">To create statistics</span></span>  
  
1.  <span data-ttu-id="4ad06-123">Dans l' **Explorateur d'objets**, cliquez sur le signe plus (+) pour développer la base de données dans laquelle vous souhaitez créer une nouvelle statistique.</span><span class="sxs-lookup"><span data-stu-id="4ad06-123">In **Object Explorer**, click the plus sign to expand the database in which you want to create a new statistic.</span></span>  
  
2.  <span data-ttu-id="4ad06-124">Cliquez sur le signe plus (+) pour développer le dossier **Tables** .</span><span class="sxs-lookup"><span data-stu-id="4ad06-124">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="4ad06-125">Cliquez sur le signe plus (+) pour développer la table dans laquelle vous souhaitez créer une statistique.</span><span class="sxs-lookup"><span data-stu-id="4ad06-125">Click the plus sign to expand the table in which you want to create a new statistic.</span></span>  
  
4.  <span data-ttu-id="4ad06-126">Cliquez avec le bouton droit sur le dossier **Statistiques** et sélectionnez **Nouvelles statistiques...** .</span><span class="sxs-lookup"><span data-stu-id="4ad06-126">Right-click the **Statistics** folder and select **New Statistics...**.</span></span>  
  
     <span data-ttu-id="4ad06-127">Les propriétés suivantes sont affichées dans la page **général** de la boîte de dialogue **nouvelles statistiques sur la table**_table_name_ .</span><span class="sxs-lookup"><span data-stu-id="4ad06-127">The following properties show on the **General** page in the **New Statistics on Table**_table_name_ dialog box.</span></span>  
  
     <span data-ttu-id="4ad06-128">**Nom de la table**</span><span class="sxs-lookup"><span data-stu-id="4ad06-128">**Table Name**</span></span>  
     <span data-ttu-id="4ad06-129">Affiche le nom de la table décrite par les statistiques.</span><span class="sxs-lookup"><span data-stu-id="4ad06-129">Displays the name of the table described by the statistics.</span></span>  
  
     <span data-ttu-id="4ad06-130">**Nom des statistiques**</span><span class="sxs-lookup"><span data-stu-id="4ad06-130">**Statistics Name**</span></span>  
     <span data-ttu-id="4ad06-131">Spécifie le nom de l'objet de base de données dans lequel les statistiques sont stockées.</span><span class="sxs-lookup"><span data-stu-id="4ad06-131">Displays the name of the database object where the statistics are stored.</span></span>  
  
     <span data-ttu-id="4ad06-132">**Colonnes de statistiques**</span><span class="sxs-lookup"><span data-stu-id="4ad06-132">**Statistics Columns**</span></span>  
     <span data-ttu-id="4ad06-133">Cette grille montre les colonnes décrites par ce jeu de statistiques.</span><span class="sxs-lookup"><span data-stu-id="4ad06-133">This grid shows the columns described by this set of statistics.</span></span> <span data-ttu-id="4ad06-134">Toutes les valeurs contenues dans la grille sont en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="4ad06-134">All values in the grid are read-only.</span></span>  
  
     <span data-ttu-id="4ad06-135">**Nom**</span><span class="sxs-lookup"><span data-stu-id="4ad06-135">**Name**</span></span>  
     <span data-ttu-id="4ad06-136">Affiche le nom de la colonne décrite par les statistiques.</span><span class="sxs-lookup"><span data-stu-id="4ad06-136">Displays the name of the column described by the statistics.</span></span> <span data-ttu-id="4ad06-137">Cela peut être une colonne individuelle ou une combinaison de colonnes dans une table individuelle.</span><span class="sxs-lookup"><span data-stu-id="4ad06-137">This can be a single column or a combination of columns in a single table.</span></span>  
  
     <span data-ttu-id="4ad06-138">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="4ad06-138">**Data Type**</span></span>  
     <span data-ttu-id="4ad06-139">Indique le type de données des colonnes décrites par les statistiques.</span><span class="sxs-lookup"><span data-stu-id="4ad06-139">Indicates the data type of the columns described by the statistics.</span></span>  
  
     <span data-ttu-id="4ad06-140">**Taille**</span><span class="sxs-lookup"><span data-stu-id="4ad06-140">**Size**</span></span>  
     <span data-ttu-id="4ad06-141">Indique la taille du type de données de chaque colonne.</span><span class="sxs-lookup"><span data-stu-id="4ad06-141">Displays the size of the data type for each column.</span></span>  
  
     <span data-ttu-id="4ad06-142">**Identité**</span><span class="sxs-lookup"><span data-stu-id="4ad06-142">**Identity**</span></span>  
     <span data-ttu-id="4ad06-143">Indique une colonne d'identité lorsque l'option est activée.</span><span class="sxs-lookup"><span data-stu-id="4ad06-143">Indicates an identity column when it is checked.</span></span>  
  
     <span data-ttu-id="4ad06-144">**Null autorisé**</span><span class="sxs-lookup"><span data-stu-id="4ad06-144">**Allow Nulls**</span></span>  
     <span data-ttu-id="4ad06-145">Indique si la colonne accepte les valeurs NULL.</span><span class="sxs-lookup"><span data-stu-id="4ad06-145">Indicates whether the column accepts NULL values.</span></span>  
  
     <span data-ttu-id="4ad06-146">**Ajouter**</span><span class="sxs-lookup"><span data-stu-id="4ad06-146">**Add**</span></span>  
     <span data-ttu-id="4ad06-147">Permet d'ajouter des colonnes supplémentaires de la table dans la grille des statistiques.</span><span class="sxs-lookup"><span data-stu-id="4ad06-147">Add additional columns from the table to the statistics grid.</span></span>  
  
     <span data-ttu-id="4ad06-148">**Remove**</span><span class="sxs-lookup"><span data-stu-id="4ad06-148">**Remove**</span></span>  
     <span data-ttu-id="4ad06-149">Permet de supprimer la colonne sélectionnée de la grille des statistiques.</span><span class="sxs-lookup"><span data-stu-id="4ad06-149">Remove the selected column from the statistics grid.</span></span>  
  
     <span data-ttu-id="4ad06-150">**Monter**</span><span class="sxs-lookup"><span data-stu-id="4ad06-150">**Move Up**</span></span>  
     <span data-ttu-id="4ad06-151">Permet de déplacer la colonne sélectionnée vers un emplacement antérieur dans la grille des statistiques.</span><span class="sxs-lookup"><span data-stu-id="4ad06-151">Move the selected column to an earlier location in the statistics grid.</span></span> <span data-ttu-id="4ad06-152">L'emplacement dans la grille peut affecter de manière significative l'utilité des statistiques.</span><span class="sxs-lookup"><span data-stu-id="4ad06-152">The location in the grid can substantially impact the usefulness of the statistics.</span></span>  
  
     <span data-ttu-id="4ad06-153">**Descendre**</span><span class="sxs-lookup"><span data-stu-id="4ad06-153">**Move Down**</span></span>  
     <span data-ttu-id="4ad06-154">Permet de déplacer la colonne sélectionnée vers un emplacement ultérieur dans la grille des statistiques.</span><span class="sxs-lookup"><span data-stu-id="4ad06-154">Move the selected column to a later location in the statistics grid.</span></span>  
  
     <span data-ttu-id="4ad06-155">**Les statistiques de ces colonnes ont été mises à jour la dernière fois le :**</span><span class="sxs-lookup"><span data-stu-id="4ad06-155">**Statistics for these columns were last updated:**</span></span>  
     <span data-ttu-id="4ad06-156">Indique l'ancienneté des statistiques.</span><span class="sxs-lookup"><span data-stu-id="4ad06-156">Indicates how old the statistics are.</span></span> <span data-ttu-id="4ad06-157">Les statistiques ont plus de valeur lorsqu'elles sont actuelles.</span><span class="sxs-lookup"><span data-stu-id="4ad06-157">Statistics are more valuable when they are current.</span></span> <span data-ttu-id="4ad06-158">Mettez à jour les statistiques après des modifications importantes des données ou après l'ajout de données atypiques.</span><span class="sxs-lookup"><span data-stu-id="4ad06-158">Update statistics after large changes to the data or after adding atypical data.</span></span> <span data-ttu-id="4ad06-159">Les statistiques de tables dont la distribution des données est cohérente peuvent être mises à jour moins souvent.</span><span class="sxs-lookup"><span data-stu-id="4ad06-159">Statistics for tables that have a consistent distribution of data need to be updated less frequently.</span></span>  
  
     <span data-ttu-id="4ad06-160">**Mettre à jour les statistiques pour ces colonnes**</span><span class="sxs-lookup"><span data-stu-id="4ad06-160">**Update statistics for these columns**</span></span>  
     <span data-ttu-id="4ad06-161">Activez cette option pour mettre à jour les statistiques lors de la fermeture de la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="4ad06-161">Check to update the statistics when the dialog box is closed.</span></span>  
  
     <span data-ttu-id="4ad06-162">La propriété suivante est présente dans la page **filtre** de la boîte de dialogue **nouvelles statistiques sur la table**_table_name_ .</span><span class="sxs-lookup"><span data-stu-id="4ad06-162">The following property shows on the **Filter** page in the **New Statistics on Table**_table_name_ dialog box.</span></span>  
  
     <span data-ttu-id="4ad06-163">**Expression de filtre**</span><span class="sxs-lookup"><span data-stu-id="4ad06-163">**Filter Expression**</span></span>  
     <span data-ttu-id="4ad06-164">Définit quelles lignes de données inclure dans les statistiques filtrées.</span><span class="sxs-lookup"><span data-stu-id="4ad06-164">Defines which data rows to include in the filtered statistics.</span></span> <span data-ttu-id="4ad06-165">Par exemple : `Production.ProductSubcategoryID IN ( 1,2,3 )`</span><span class="sxs-lookup"><span data-stu-id="4ad06-165">For example, `Production.ProductSubcategoryID IN ( 1,2,3 )`</span></span>  
  
5.  <span data-ttu-id="4ad06-166">Dans la boîte de dialogue **nouvelles statistiques sur la Table**_table_name_ , dans la page **général** , cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="4ad06-166">In the **New Statistics on Table**_table_name_ dialog box, on the **General** page, click **Add**.</span></span>  
  
     <span data-ttu-id="4ad06-167">Les propriétés suivantes s'affichent dans la boîte de dialogue **Sélectionner les colonnes** .</span><span class="sxs-lookup"><span data-stu-id="4ad06-167">The following properties show in the **Select Columns** dialog box.</span></span> <span data-ttu-id="4ad06-168">Ces informations sont en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="4ad06-168">This information is read-only.</span></span>  
  
     <span data-ttu-id="4ad06-169">**Nom**</span><span class="sxs-lookup"><span data-stu-id="4ad06-169">**Name**</span></span>  
     <span data-ttu-id="4ad06-170">Affiche le nom de la colonne décrite par les statistiques.</span><span class="sxs-lookup"><span data-stu-id="4ad06-170">Displays the name of the column described by the statistics.</span></span> <span data-ttu-id="4ad06-171">Cela peut être une colonne individuelle ou une combinaison de colonnes dans une table individuelle.</span><span class="sxs-lookup"><span data-stu-id="4ad06-171">This can be a single column or a combination of columns in a single table.</span></span>  
  
     <span data-ttu-id="4ad06-172">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="4ad06-172">**Data Type**</span></span>  
     <span data-ttu-id="4ad06-173">Indique le type de données des colonnes décrites par les statistiques.</span><span class="sxs-lookup"><span data-stu-id="4ad06-173">Indicates the data type of the columns described by the statistics.</span></span>  
  
     <span data-ttu-id="4ad06-174">**Taille**</span><span class="sxs-lookup"><span data-stu-id="4ad06-174">**Size**</span></span>  
     <span data-ttu-id="4ad06-175">Indique la taille du type de données de chaque colonne.</span><span class="sxs-lookup"><span data-stu-id="4ad06-175">Displays the size of the data type for each column.</span></span>  
  
     <span data-ttu-id="4ad06-176">**Identité**</span><span class="sxs-lookup"><span data-stu-id="4ad06-176">**Identity**</span></span>  
     <span data-ttu-id="4ad06-177">Indique une colonne d'identité lorsque l'option est cochée.</span><span class="sxs-lookup"><span data-stu-id="4ad06-177">Indicates an identity column when checked.</span></span>  
  
     <span data-ttu-id="4ad06-178">**Autoriser les valeurs NULL**</span><span class="sxs-lookup"><span data-stu-id="4ad06-178">**Allow NULLs**</span></span>  
     <span data-ttu-id="4ad06-179">Indique si la colonne accepte les valeurs NULL.</span><span class="sxs-lookup"><span data-stu-id="4ad06-179">Indicates whether the column accepts NULL values.</span></span>  
  
6.  <span data-ttu-id="4ad06-180">Dans la boîte de dialogue **Sélectionner les colonnes** , activez la ou les cases à cocher de chaque colonne pour laquelle vous voulez créer une statistique, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="4ad06-180">In the **Select Columns** dialog box, select the check box or check boxes of each column for which you want to create a statistic and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="4ad06-181">Dans la boîte de dialogue **nouvelles statistiques sur la Table**_table_name_ , cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="4ad06-181">In the **New Statistics on Table**_table_name_ dialog box, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4ad06-182">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4ad06-182">Using Transact-SQL</span></span>  
  
#### <a name="to-create-statistics"></a><span data-ttu-id="4ad06-183">Pour créer des statistiques</span><span class="sxs-lookup"><span data-stu-id="4ad06-183">To create statistics</span></span>  
  
1.  <span data-ttu-id="4ad06-184">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4ad06-184">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4ad06-185">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="4ad06-185">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4ad06-186">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="4ad06-186">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    -- Create new statistic object called ContactMail1  
    -- on the BusinessEntityID and EmailPromotion columns in the Person.Person table.   
  
    CREATE STATISTICS ContactMail1  
        ON Person.Person (BusinessEntityID, EmailPromotion);   
    GO  
    ```  
  
4.  <span data-ttu-id="4ad06-187">Les statistiques créées ci-dessus améliorent potentiellement les résultats de la requête suivante.</span><span class="sxs-lookup"><span data-stu-id="4ad06-187">The statistic created above potentially improves the results for the following query.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    SELECT LastName, FirstName  
    FROM Person.Person  
    WHERE EmailPromotion = 2  
    ORDER BY LastName, FirstName;   
    GO  
    ```  
  
 <span data-ttu-id="4ad06-188">Pour plus d’informations, consultez [CREATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-statistics-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4ad06-188">For more information, see [CREATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-statistics-transact-sql).</span></span>  
  
  
