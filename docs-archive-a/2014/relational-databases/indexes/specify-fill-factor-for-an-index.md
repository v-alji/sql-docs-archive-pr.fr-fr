---
title: Spécifier un facteur de remplissage pour un index | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- fill factor [SQL Server]
- page splits [SQL Server]
ms.assetid: 237a577e-b42b-4adb-90cf-aa7fb174f3ab
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ac54f2b22de55ed74c4635ec0f86d008c7624a42
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707520"
---
# <a name="specify-fill-factor-for-an-index"></a><span data-ttu-id="8168c-102">Spécifier un facteur de remplissage pour un index</span><span class="sxs-lookup"><span data-stu-id="8168c-102">Specify Fill Factor for an Index</span></span>
  <span data-ttu-id="8168c-103">Cette rubrique explique ce qu'est le facteur de remplissage et comment spécifier une valeur de facteur de remplissage sur un index dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8168c-103">This topic describes what fill factor is and how to specify a fill factor value on an index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="8168c-104">L'option de facteur de remplissage permet de paramétrer précisément les performances et le stockage des données d'index.</span><span class="sxs-lookup"><span data-stu-id="8168c-104">The fill-factor option is provided for fine-tuning index data storage and performance.</span></span> <span data-ttu-id="8168c-105">Lorsqu'un index est créé ou régénéré, la valeur du facteur de remplissage détermine le pourcentage d'espace sur chaque page de niveau feuille à remplir de données, réservant ainsi le reste de chaque page comme espace disponible pour une croissance future.</span><span class="sxs-lookup"><span data-stu-id="8168c-105">When an index is created or rebuilt, the fill-factor value determines the percentage of space on each leaf-level page to be filled with data, reserving the remainder on each page as free space for future growth.</span></span> <span data-ttu-id="8168c-106">Par exemple, une valeur de facteur de remplissage de 80 signifie que 20 pour cent de chaque page de niveau feuille reste vide afin que les index puissent s'étendre à mesure que des données sont ajoutées à la table sous-jacente.</span><span class="sxs-lookup"><span data-stu-id="8168c-106">For example, specifying a fill-factor value of 80 means that 20 percent of each leaf-level page will be left empty, providing space for index expansion as data is added to the underlying table.</span></span> <span data-ttu-id="8168c-107">L'espace vide est réservé entre les lignes d'index plutôt qu'à la fin de l'index.</span><span class="sxs-lookup"><span data-stu-id="8168c-107">The empty space is reserved between the index rows rather than at the end of the index.</span></span>  
  
 <span data-ttu-id="8168c-108">La valeur du facteur de remplissage est un pourcentage de 1 à 100 et la valeur par défaut à l'échelle du serveur est 0, ce qui signifie que les pages de niveau feuille sont entièrement remplies.</span><span class="sxs-lookup"><span data-stu-id="8168c-108">The fill-factor value is a percentage from 1 to 100, and the server-wide default is 0 which means that the leaf-level pages are filled to capacity.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8168c-109">Les valeurs du facteur de remplissage 0 et 100 sont identiques à tous les égards.</span><span class="sxs-lookup"><span data-stu-id="8168c-109">Fill-factor values 0 and 100 are the same in all respects.</span></span>  
  
 <span data-ttu-id="8168c-110">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="8168c-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="8168c-111">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="8168c-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="8168c-112">Considérations relatives aux performances</span><span class="sxs-lookup"><span data-stu-id="8168c-112">Performance Considerations</span></span>](#Performance)  
  
     [<span data-ttu-id="8168c-113">Sécurité</span><span class="sxs-lookup"><span data-stu-id="8168c-113">Security</span></span>](#Security)  
  
-   <span data-ttu-id="8168c-114">**Pour spécifier un taux de remplissage dans un index, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="8168c-114">**To specify a fill factor in an index, using:**</span></span>  
  
     [<span data-ttu-id="8168c-115">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8168c-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="8168c-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8168c-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8168c-117">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="8168c-117">Before You Begin</span></span>  
  
###  <a name="performance-considerations"></a><a name="Performance"></a> <span data-ttu-id="8168c-118">Considérations relatives aux performances</span><span class="sxs-lookup"><span data-stu-id="8168c-118">Performance Considerations</span></span>  
  
#### <a name="page-splits"></a><span data-ttu-id="8168c-119">Fractionnements de pages</span><span class="sxs-lookup"><span data-stu-id="8168c-119">Page Splits</span></span>  
 <span data-ttu-id="8168c-120">Une valeur de facteur de remplissage correctement choisie peut réduire les risques de fractionnements de pages en fournissant suffisamment d'espace pour l'extension des index à mesure que des données sont ajoutées à la table sous-jacente. Lorsqu'une nouvelle ligne est ajoutée à une page d'index complète, le [!INCLUDE[ssDE](../../includes/ssde-md.md)] déplace environ la moitié des lignes vers une nouvelle page afin de faire de la place pour la nouvelle ligne.</span><span class="sxs-lookup"><span data-stu-id="8168c-120">A correctly chosen fill-factor value can reduce potential page splits by providing enough space for index expansion as data is added to the underlying table.When a new row is added to a full index page, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] moves approximately half the rows to a new page to make room for the new row.</span></span> <span data-ttu-id="8168c-121">Ce type de réorganisation est désigné par l'expression « fractionnement de pages ».</span><span class="sxs-lookup"><span data-stu-id="8168c-121">This reorganization is known as a page split.</span></span> <span data-ttu-id="8168c-122">Un fractionnement de pages fait de la place pour de nouveaux enregistrements, mais cette opération peut prendre du temps et est gourmande en ressources.</span><span class="sxs-lookup"><span data-stu-id="8168c-122">A page split makes room for new records, but can take time to perform and is a resource intensive operation.</span></span> <span data-ttu-id="8168c-123">En outre, il peut causer une fragmentation qui accroît les opérations d'E/S.</span><span class="sxs-lookup"><span data-stu-id="8168c-123">Also, it can cause fragmentation that causes increased I/O operations.</span></span> <span data-ttu-id="8168c-124">Lorsque des fractionnements de pages se produisent fréquemment, vous pouvez régénérer l'index à l'aide d'une valeur de facteur de remplissage nouvelle ou existante afin de redistribuer les données.</span><span class="sxs-lookup"><span data-stu-id="8168c-124">When frequent page splits occur, the index can be rebuilt by using a new or existing fill-factor value to redistribute the data.</span></span> <span data-ttu-id="8168c-125">Pour plus d’informations, consultez [Réorganiser et reconstruire des index](reorganize-and-rebuild-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="8168c-125">For more information, see [Reorganize and Rebuild Indexes](reorganize-and-rebuild-indexes.md).</span></span>  
  
 <span data-ttu-id="8168c-126">Bien qu'une faible valeur de facteur de remplissage, différente de 0, puisse réduire la nécessité de fractionner les pages à mesure que l'index s'étend, ce dernier a besoin de davantage d'espace de stockage et peut diminuer les performances de lecture.</span><span class="sxs-lookup"><span data-stu-id="8168c-126">Although a low, nonzero fill-factor value may reduce the requirement to split pages as the index grows, the index will require more storage space and can decrease read performance.</span></span> <span data-ttu-id="8168c-127">Même pour une application orientée vers de nombreuses opérations d'insertion et de mise à jour, le nombre de lectures effectuées dans la base de données est généralement 5 à 10 fois plus élevé que le nombre d'écritures.</span><span class="sxs-lookup"><span data-stu-id="8168c-127">Even for an application oriented for many insert and update operations, the number of database reads typically outnumber database writes by a factor of 5 to 10.</span></span> <span data-ttu-id="8168c-128">Par conséquent, la spécification d'un facteur de remplissage différent de la valeur par défaut peut diminuer les performances de lecture dans la base de données selon un coefficient inversement proportionnel au facteur de remplissage défini.</span><span class="sxs-lookup"><span data-stu-id="8168c-128">Therefore, specifying a fill factor other than the default can decrease database read performance by an amount inversely proportional to the fill-factor setting.</span></span> <span data-ttu-id="8168c-129">Par exemple, un facteur de remplissage de 50 peut diminuer de moitié les performances de lecture dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="8168c-129">For example, a fill-factor value of 50 can cause database read performance to decrease by two times.</span></span> <span data-ttu-id="8168c-130">Les performances de lecture diminuent, car l'index contient davantage de pages, ce qui augmente le nombre d'opérations d'E/S disque nécessaires à la récupération des données.</span><span class="sxs-lookup"><span data-stu-id="8168c-130">Read performance is decreased because the index contains more pages, therefore increasing the disk IO operations required to retrieve the data.</span></span>  
  
#### <a name="adding-data-to-the-end-of-the-table"></a><span data-ttu-id="8168c-131">Ajout de données à la fin de la table</span><span class="sxs-lookup"><span data-stu-id="8168c-131">Adding Data to the End of the Table</span></span>  
 <span data-ttu-id="8168c-132">Un facteur de remplissage différent de 0 ou 100 peut être bénéfique pour les performances si les nouvelles données sont réparties de manière égale dans l'ensemble de la table.</span><span class="sxs-lookup"><span data-stu-id="8168c-132">A nonzero fill factor other than 0 or 100 can be good for performance if the new data is evenly distributed throughout the table.</span></span> <span data-ttu-id="8168c-133">Toutefois, si toutes les données sont ajoutées à la fin de la table, l'espace vide dans les pages d'index n'est pas rempli.</span><span class="sxs-lookup"><span data-stu-id="8168c-133">However, if all the data is added to the end of the table, the empty space in the index pages will not be filled.</span></span> <span data-ttu-id="8168c-134">Par exemple, si la colonne clé de l'index est une colonne IDENTITY, la clé des nouvelles lignes augmente sans cesse et les lignes d'index sont ajoutées logiquement à la fin de l'index.</span><span class="sxs-lookup"><span data-stu-id="8168c-134">For example, if the index key column is an IDENTITY column, the key for new rows is always increasing and the index rows are logically added to the end of the index.</span></span> <span data-ttu-id="8168c-135">Si les lignes existantes sont mises à jour avec des données qui font augmenter la taille des lignes, utilisez un facteur de remplissage inférieur à 100.</span><span class="sxs-lookup"><span data-stu-id="8168c-135">If existing rows will be updated with data that lengthens the size of the rows, use a fill factor of less than 100.</span></span> <span data-ttu-id="8168c-136">Les octets supplémentaires de chaque page permettent de réduire les fractionnements de pages provoqués par l'augmentation de la taille des lignes.</span><span class="sxs-lookup"><span data-stu-id="8168c-136">The extra bytes on each page will help to minimize page splits caused by extra length in the rows.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8168c-137">Sécurité</span><span class="sxs-lookup"><span data-stu-id="8168c-137">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8168c-138">Autorisations</span><span class="sxs-lookup"><span data-stu-id="8168c-138">Permissions</span></span>  
 <span data-ttu-id="8168c-139">Nécessite une autorisation ALTER sur la table ou la vue.</span><span class="sxs-lookup"><span data-stu-id="8168c-139">Requires ALTER permission on the table or view.</span></span> <span data-ttu-id="8168c-140">L’utilisateur doit être membre du rôle serveur fixe **sysadmin** ou des rôles de base de données fixes **db_ddladmin** et **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="8168c-140">User must be a member of the **sysadmin** fixed server role or the **db_ddladmin** and **db_owner** fixed database roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8168c-141">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8168c-141">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-specify-a-fill-factor-by-using-table-designer"></a><span data-ttu-id="8168c-142">Pour spécifier un facteur de remplissage à l'aide du Concepteur de tables</span><span class="sxs-lookup"><span data-stu-id="8168c-142">To specify a fill factor by using Table Designer</span></span>  
  
1.  <span data-ttu-id="8168c-143">Dans l’Explorateur d’objets, cliquez sur le signe plus (+) pour développer la base de données qui contient la table sur laquelle vous souhaitez spécifier un facteur de remplissage d’index.</span><span class="sxs-lookup"><span data-stu-id="8168c-143">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to specify an index's fill factor.</span></span>  
  
2.  <span data-ttu-id="8168c-144">Cliquez sur le signe plus (+) pour développer le dossier **Tables** .</span><span class="sxs-lookup"><span data-stu-id="8168c-144">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="8168c-145">Cliquez avec le bouton droit sur la table sur laquelle vous souhaitez spécifier un facteur de remplissage d’index et sélectionnez **Conception**.</span><span class="sxs-lookup"><span data-stu-id="8168c-145">Right-click the table on which you want to specify an index's fill factor and select **Design**.</span></span>  
  
4.  <span data-ttu-id="8168c-146">Dans le menu **Concepteur de tables** , cliquez sur **Index/Clés**.</span><span class="sxs-lookup"><span data-stu-id="8168c-146">On the **Table Designer** menu, click **Indexes/Keys**.</span></span>  
  
5.  <span data-ttu-id="8168c-147">Sélectionnez l'index avec le facteur de remplissage que vous souhaitez spécifier.</span><span class="sxs-lookup"><span data-stu-id="8168c-147">Select the index with the fill factor that you want to specify.</span></span>  
  
6.  <span data-ttu-id="8168c-148">Développez **Spécification du remplissage**, sélectionnez la ligne **Facteur de remplissage** et entrez le facteur de remplissage que vous souhaitez dans la ligne.</span><span class="sxs-lookup"><span data-stu-id="8168c-148">Expand **Fill Specification**, select the **Fill Factor** row and enter the fill factor you want in the row.</span></span>  
  
7.  <span data-ttu-id="8168c-149">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="8168c-149">Click **Close**.</span></span>  
  
8.  <span data-ttu-id="8168c-150">Dans le menu **Fichier** , sélectionnez **Enregistrer**_nom_table_.</span><span class="sxs-lookup"><span data-stu-id="8168c-150">On the **File** menu, select **Save**_table_name_.</span></span>  
  
#### <a name="to-specify-a-fill-factor-in-an-index-by-using-object-explorer"></a><span data-ttu-id="8168c-151">Pour spécifier un facteur de remplissage dans un index à l'aide de l'Explorateur d'objets</span><span class="sxs-lookup"><span data-stu-id="8168c-151">To specify a fill factor in an index by using Object Explorer</span></span>  
  
1.  <span data-ttu-id="8168c-152">Dans l’Explorateur d’objets, cliquez sur le signe plus (+) pour développer la base de données qui contient la table sur laquelle vous souhaitez spécifier un facteur de remplissage d’index.</span><span class="sxs-lookup"><span data-stu-id="8168c-152">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to specify an index's fill factor.</span></span>  
  
2.  <span data-ttu-id="8168c-153">Cliquez sur le signe plus (+) pour développer le dossier **Tables** .</span><span class="sxs-lookup"><span data-stu-id="8168c-153">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="8168c-154">Cliquez sur le signe plus (+) pour développer la table sur laquelle vous souhaitez spécifier un facteur de remplissage d’index.</span><span class="sxs-lookup"><span data-stu-id="8168c-154">Click the plus sign to expand the table on which you want to specify an index's fill factor.</span></span>  
  
4.  <span data-ttu-id="8168c-155">Cliquez sur le signe plus (+) pour développer le dossier **Index** .</span><span class="sxs-lookup"><span data-stu-id="8168c-155">Click the plus sign to expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="8168c-156">Cliquez avec le bouton droit sur l’index avec le facteur de remplissage que vous souhaitez spécifier et sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="8168c-156">Right-click the index with the fill factor that you want to specify and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="8168c-157">Sous **Sélectionner une page**, sélectionnez **Options**.</span><span class="sxs-lookup"><span data-stu-id="8168c-157">Under **Select a page**, select **Options**.</span></span>  
  
7.  <span data-ttu-id="8168c-158">Dans la ligne **Facteur de remplissage** , entrez le facteur de remplissage souhaité.</span><span class="sxs-lookup"><span data-stu-id="8168c-158">In the **Fill factor** row, enter the fill factor that you want.</span></span>  
  
8.  <span data-ttu-id="8168c-159">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8168c-159">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="8168c-160">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8168c-160">Using Transact-SQL</span></span>  
  
#### <a name="to-specify-a-fill-factor-in-an-existing-index"></a><span data-ttu-id="8168c-161">Pour spécifier un taux de remplissage dans un index existant</span><span class="sxs-lookup"><span data-stu-id="8168c-161">To specify a fill factor in an existing index</span></span>  
  
1.  <span data-ttu-id="8168c-162">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8168c-162">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="8168c-163">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="8168c-163">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8168c-164">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="8168c-164">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="8168c-165">L'exemple reconstruit un index existant et applique le facteur de remplissage spécifié pendant l'opération de reconstruction.</span><span class="sxs-lookup"><span data-stu-id="8168c-165">The example rebuilds an existing index and applies the specified fill factor during the rebuild operation.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Rebuilds the IX_Employee_OrganizationLevel_OrganizationNode index   
    -- with a fill factor of 80 on the HumanResources.Employee table.  
  
    ALTER INDEX IX_Employee_OrganizationLevel_OrganizationNode ON HumanResources.Employee  
    REBUILD WITH (FILLFACTOR = 80);   
    GO  
    ```  
  
#### <a name="another-way-to-specify-a-fill-factor-in-an-index"></a><span data-ttu-id="8168c-166">Autre méthode permettant de spécifier un facteur de remplissage dans un index</span><span class="sxs-lookup"><span data-stu-id="8168c-166">Another way to specify a fill factor in an index</span></span>  
  
1.  <span data-ttu-id="8168c-167">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8168c-167">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="8168c-168">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="8168c-168">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8168c-169">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="8168c-169">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    /* Drops and re-creates the IX_Employee_OrganizationLevel_OrganizationNode index on the HumanResources.Employee table with a fill factor of 80.  
    */  
  
    CREATE INDEX IX_Employee_OrganizationLevel_OrganizationNode ON HumanResources.Employee  
       (OrganizationLevel, OrganizationNode)   
    WITH (DROP_EXISTING = ON, FILLFACTOR = 80);   
    GO  
    ```  
  
 <span data-ttu-id="8168c-170">Pour plus d’informations, consultez [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8168c-170">For more information, see [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
  
