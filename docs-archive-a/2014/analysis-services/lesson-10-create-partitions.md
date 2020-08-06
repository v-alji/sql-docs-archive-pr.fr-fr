---
title: 'Leçon 11 : créer des partitions | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 92eb21a8-5fc4-4999-ad37-1332ce26431d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4db5edd5d47fe424ef6e6ad2a822106110209059
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600298"
---
# <a name="lesson-11-create-partitions"></a><span data-ttu-id="42e67-102">Leçon 11 : Créer des partitions</span><span class="sxs-lookup"><span data-stu-id="42e67-102">Lesson 11: Create Partitions</span></span>
  <span data-ttu-id="42e67-103">Dans cette leçon, vous allez créer des partitions pour diviser la table Internet Sales en parties logiques plus petites pouvant être traitées (actualisées) indépendamment d'autres partitions.</span><span class="sxs-lookup"><span data-stu-id="42e67-103">In this lesson, you will create partitions to divide the Internet Sales table into smaller logical parts that can be processed (Refreshed) independent of other partitions.</span></span> <span data-ttu-id="42e67-104">Par défaut, chaque table que vous incluez dans votre modèle a une partition qui inclut toutes les colonnes et lignes de la table.</span><span class="sxs-lookup"><span data-stu-id="42e67-104">By default, every table you include in your model has one partition which includes all of the table's columns and rows.</span></span> <span data-ttu-id="42e67-105">Pour la table Internet Sales, nous souhaitons diviser les données par année. une partition pour chacune des cinq années de la table.</span><span class="sxs-lookup"><span data-stu-id="42e67-105">For the Internet Sales table, we want to divide the data by year; one partition for each of the table's five years.</span></span>  <span data-ttu-id="42e67-106">Chaque partition peut ensuite être traitée indépendamment.</span><span class="sxs-lookup"><span data-stu-id="42e67-106">Each partition can then be processed independently.</span></span> <span data-ttu-id="42e67-107">Pour plus d’informations, consultez [Partitions &#40;SSAS Tabulaire&#41;](tabular-models/partitions-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="42e67-107">To learn more, see [Partitions &#40;SSAS Tabular&#41;](tabular-models/partitions-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="42e67-108">Durée estimée pour suivre cette leçon : **15 minutes**</span><span class="sxs-lookup"><span data-stu-id="42e67-108">Estimated time to complete this lesson: **15 minutes**</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="42e67-109">Prérequis</span><span class="sxs-lookup"><span data-stu-id="42e67-109">Prerequisites</span></span>  
 <span data-ttu-id="42e67-110">Cette rubrique fait partie d’un didacticiel de modélisation tabulaire, qui doit être suivi dans l’ordre prévu.</span><span class="sxs-lookup"><span data-stu-id="42e67-110">This topic is part of a tabular modeling tutorial, which should be completed in order.</span></span> <span data-ttu-id="42e67-111">Avant d’effectuer les tâches de cette leçon, vous devez avoir terminé la leçon précédente : [Leçon 10 : Créer des hiérarchies](lesson-9-create-hierarchies.md).</span><span class="sxs-lookup"><span data-stu-id="42e67-111">Before performing the tasks in this lesson, you should have completed the previous lesson: [Lesson 10: Create Hierarchies](lesson-9-create-hierarchies.md).</span></span>  
  
## <a name="create-partitions"></a><span data-ttu-id="42e67-112">Créer des partitions</span><span class="sxs-lookup"><span data-stu-id="42e67-112">Create Partitions</span></span>  
  
#### <a name="to-create-partitions-in-the-internet-sales-table"></a><span data-ttu-id="42e67-113">Pour créer des partitions dans la table Internet Sales</span><span class="sxs-lookup"><span data-stu-id="42e67-113">To create partitions in the Internet Sales table</span></span>  
  
1.  <span data-ttu-id="42e67-114">Dans le Générateur de modèles, cliquez sur la table **Internet Sales** , sur le menu **Table** , puis sur **Partitions**.</span><span class="sxs-lookup"><span data-stu-id="42e67-114">In the model designer, click on the **Internet Sales** table, then click on the **Table** menu, and then click **Partitions**.</span></span>  
  
     <span data-ttu-id="42e67-115">La boîte de dialogue **Gestionnaire de partition** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="42e67-115">The **Partition Manager** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="42e67-116">Dans la boîte de dialogue **Gestionnaire de partition** , dans **partitions**, cliquez sur la partition **Internet Sales** .</span><span class="sxs-lookup"><span data-stu-id="42e67-116">In the **Partition Manager** dialog box, in **Partitions**, click the **Internet Sales** partition.</span></span>  
  
3.  <span data-ttu-id="42e67-117">Dans **nom**de la partition, remplacez le nom par `Internet Sales 2005` .</span><span class="sxs-lookup"><span data-stu-id="42e67-117">In **Partition Name**, change the name to `Internet Sales 2005`.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="42e67-118">Avant de passer à l'étape suivante, notez que les noms des colonnes dans la fenêtre d'aperçu de la table affichent les colonnes incluses dans la table modèle (activée) avec les noms des colonnes de la source.</span><span class="sxs-lookup"><span data-stu-id="42e67-118">Before continuing to the next step, notice the column names in the Table Preview window display those columns included in the model table (checked) with the column names from the source.</span></span> <span data-ttu-id="42e67-119">Cela est dû au fait que la fenêtre d'aperçu de la table affiche les colonnes de la table source, pas de la table modèle.</span><span class="sxs-lookup"><span data-stu-id="42e67-119">This is because the Table Preview window displays columns from the source table, not from the model table.</span></span>  
  
4.  <span data-ttu-id="42e67-120">Sélectionnez le bouton **Éditeur de requête** au-dessus du côté droit de la fenêtre d’aperçu.</span><span class="sxs-lookup"><span data-stu-id="42e67-120">Select the **Query Editor** button just above the right side of the preview window.</span></span>  
  
     <span data-ttu-id="42e67-121">Étant donné que vous souhaitez que la partition inclue uniquement les lignes appartenant à une certaine période, vous devez inclure une clause WHERE.</span><span class="sxs-lookup"><span data-stu-id="42e67-121">Because you want the partition to include only those rows within a certain period, you must include a WHERE clause.</span></span> <span data-ttu-id="42e67-122">Vous pouvez créer une clause WHERE uniquement à l'aide d'une instruction SQL.</span><span class="sxs-lookup"><span data-stu-id="42e67-122">You can only create a WHERE clause by using a SQL Statement.</span></span>  
  
5.  <span data-ttu-id="42e67-123">Dans le champ **Instruction SQL** , remplacez l’instruction existante en collant l’instruction suivante :</span><span class="sxs-lookup"><span data-stu-id="42e67-123">In the **SQL Statement** field, replace the existing statement by pasting in the following statement:</span></span>  
  
    ```  
    SELECT   
    [dbo].[FactInternetSales].[ProductKey],  
    [dbo].[FactInternetSales].[CustomerKey],  
    [dbo].[FactInternetSales].[PromotionKey],  
    [dbo].[FactInternetSales].[CurrencyKey],  
    [dbo].[FactInternetSales].[SalesTerritoryKey],  
    [dbo].[FactInternetSales].[SalesOrderNumber],  
    [dbo].[FactInternetSales].[SalesOrderLineNumber],  
    [dbo].[FactInternetSales].[RevisionNumber],  
    [dbo].[FactInternetSales].[OrderQuantity],  
    [dbo].[FactInternetSales].[UnitPrice],  
    [dbo].[FactInternetSales].[ExtendedAmount],  
    [dbo].[FactInternetSales].[UnitPriceDiscountPct],  
    [dbo].[FactInternetSales].[DiscountAmount],  
    [dbo].[FactInternetSales].[ProductStandardCost],  
    [dbo].[FactInternetSales].[TotalProductCost],  
    [dbo].[FactInternetSales].[SalesAmount],  
    [dbo].[FactInternetSales].[TaxAmt],  
    [dbo].[FactInternetSales].[Freight],  
    [dbo].[FactInternetSales].[CarrierTrackingNumber],  
    [dbo].[FactInternetSales].[CustomerPONumber],  
    [dbo].[FactInternetSales].[OrderDate],  
    [dbo].[FactInternetSales].[DueDate],  
    [dbo].[FactInternetSales].[ShipDate]   
    FROM [dbo].[FactInternetSales]  
    WHERE (([OrderDate] >= N'2005-01-01 00:00:00') AND ([OrderDate] < N'2006-01-01 00:00:00'))  
    ```  
  
     <span data-ttu-id="42e67-124">Cette instruction spécifie que la partition doit inclure toutes les données des lignes où OrderDate correspond à l'année calendaire 2005 tel que spécifié dans la clause WHERE.</span><span class="sxs-lookup"><span data-stu-id="42e67-124">This statement specifies the partition should include all of the data in those rows where the OrderDate is for the 2005 calendar year as specified in the WHERE clause.</span></span>  
  
6.  <span data-ttu-id="42e67-125">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="42e67-125">Click **Validate**.</span></span>  
  
     <span data-ttu-id="42e67-126">Notez qu'un avertissement s'affiche indiquant que certaines colonnes ne sont pas présentes dans la source.</span><span class="sxs-lookup"><span data-stu-id="42e67-126">Notice a warning is displayed stating that certain columns are not present in source.</span></span> <span data-ttu-id="42e67-127">En effet, dans la [leçon 3 : renommer des colonnes](rename-columns.md), vous avez renommé les colonnes de la table Internet Sales dans le modèle afin qu’elles soient différentes de celles de la source.</span><span class="sxs-lookup"><span data-stu-id="42e67-127">This is because in [Lesson 3: Rename Columns](rename-columns.md), you renamed those columns in the Internet Sales table in the model to be different from those same columns at the source.</span></span>  
  
#### <a name="to-create-a-partition-for-the-2006-year-in-the-internet-sales-table"></a><span data-ttu-id="42e67-128">Pour créer une partition pour l’année 2006 dans la table Internet Sales</span><span class="sxs-lookup"><span data-stu-id="42e67-128">To create a partition for the 2006 year in the Internet Sales table</span></span>  
  
1.  <span data-ttu-id="42e67-129">Dans la boîte de dialogue **Gestionnaire de partition** , dans **partitions**, cliquez sur la `Internet Sales 2005` partition que vous venez de créer, puis sur **copier**.</span><span class="sxs-lookup"><span data-stu-id="42e67-129">In the **Partition Manager** dialog box, in **Partitions**, click the `Internet Sales 2005` partition you just created, and then **Copy**.</span></span>  
  
2.  <span data-ttu-id="42e67-130">Dans **nom**de la partition, tapez `Internet Sales 2006` .</span><span class="sxs-lookup"><span data-stu-id="42e67-130">In **Partition Name**, type `Internet Sales 2006`.</span></span>  
  
3.  <span data-ttu-id="42e67-131">Dans l’instruction SQL, pour que la partition inclue uniquement les lignes de l’année 2006, remplacez la clause WHERE par ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="42e67-131">In the SQL Statement, in-order for the partition to include only those rows for the 2006 year, replace the WHERE clause with the following:</span></span>  
  
    ```  
    WHERE (([OrderDate] >= N'2006-01-01 00:00:00') AND ([OrderDate] < N'2007-01-01 00:00:00'))  
    ```  
  
#### <a name="to-create-a-partition-for-the-2007-year-in-the-internet-sales-table"></a><span data-ttu-id="42e67-132">Pour créer une partition pour l’année 2007 dans la table Internet Sales</span><span class="sxs-lookup"><span data-stu-id="42e67-132">To create a partition for the 2007 year in the Internet Sales table</span></span>  
  
1.  <span data-ttu-id="42e67-133">Dans la boîte de dialogue **Gestionnaire de partition** , cliquez sur **Copier**.</span><span class="sxs-lookup"><span data-stu-id="42e67-133">In the **Partition Manager** dialog box, click **Copy**.</span></span>  
  
2.  <span data-ttu-id="42e67-134">Dans **nom**de la partition, tapez `Internet Sales 2007` .</span><span class="sxs-lookup"><span data-stu-id="42e67-134">In **Partition Name**, type `Internet Sales 2007`.</span></span>  
  
3.  <span data-ttu-id="42e67-135">Dans **basculer vers**, sélectionnez **éditeur de requête**.</span><span class="sxs-lookup"><span data-stu-id="42e67-135">In **Switch To**, select **Query Editor**.</span></span>  
  
4.  <span data-ttu-id="42e67-136">Dans l’instruction SQL, pour que la partition inclue uniquement les lignes de l’année 2007, remplacez la clause WHERE par ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="42e67-136">In the SQL Statement, in-order for the partition to include only those rows for the 2007 year, replace the WHERE clause with the following:</span></span>  
  
    ```  
    WHERE (([OrderDate] >= N'2007-01-01 00:00:00') AND ([OrderDate] < N'2008-01-01 00:00:00'))  
    ```  
  
#### <a name="to-create-a-partition-for-the-2008-year-in-the-internet-sales-table"></a><span data-ttu-id="42e67-137">Pour créer une partition pour l’année 2008 dans la table Internet Sales</span><span class="sxs-lookup"><span data-stu-id="42e67-137">To create a partition for the 2008 year in the Internet Sales table</span></span>  
  
1.  <span data-ttu-id="42e67-138">Dans la boîte de dialogue **Gestionnaire de partition** , cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="42e67-138">In the **Partition Manager** dialog box, click **New**.</span></span>  
  
2.  <span data-ttu-id="42e67-139">Dans **nom**de la partition, tapez `Internet Sales 2008` .</span><span class="sxs-lookup"><span data-stu-id="42e67-139">In **Partition Name**, type `Internet Sales 2008`.</span></span>  
  
3.  <span data-ttu-id="42e67-140">Dans **basculer vers**, sélectionnez **éditeur de requête**.</span><span class="sxs-lookup"><span data-stu-id="42e67-140">In **Switch To**, select **Query Editor**.</span></span>  
  
4.  <span data-ttu-id="42e67-141">Dans l’instruction SQL, pour que la partition inclue uniquement les lignes de l’année 2008, remplacez la clause WHERE par ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="42e67-141">In the SQL Statement, in-order for the partition to include only those rows for the 2008 year, replace the WHERE clause with the following:</span></span>  
  
    ```  
    WHERE (([OrderDate] >= N'2008-01-01 00:00:00') AND ([OrderDate] < N'2009-01-01 00:00:00'))  
    ```  
  
#### <a name="to-create-a-partition-for-the-2009-year-in-the-internet-sales-table"></a><span data-ttu-id="42e67-142">Pour créer une partition pour l'année 2009 dans la table Internet Sales</span><span class="sxs-lookup"><span data-stu-id="42e67-142">To create a partition for the 2009 year in the Internet Sales table</span></span>  
  
1.  <span data-ttu-id="42e67-143">Dans la boîte de dialogue **Gestionnaire de partition** , cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="42e67-143">In the **Partition Manager** dialog box, click **New**.</span></span>  
  
2.  <span data-ttu-id="42e67-144">Dans **nom**de la partition, tapez `Internet Sales 2009` .</span><span class="sxs-lookup"><span data-stu-id="42e67-144">In **Partition Name**, type `Internet Sales 2009`.</span></span>  
  
3.  <span data-ttu-id="42e67-145">Dans **basculer vers**, sélectionnez **éditeur de requête**.</span><span class="sxs-lookup"><span data-stu-id="42e67-145">In **Switch To**, select **Query Editor**.</span></span>  
  
4.  <span data-ttu-id="42e67-146">Dans l'instruction SQL, pour que la partition inclue uniquement les lignes pour l'année 2009, remplacez la clause WHERE par :</span><span class="sxs-lookup"><span data-stu-id="42e67-146">In the SQL Statement, in-order for the partition to include only those rows for the 2009 year, replace the WHERE clause with the following:</span></span>  
  
    ```  
    WHERE (([OrderDate] >= N'2009-01-01 00:00:00') AND ([OrderDate] < N'2010-01-01 00:00:00'))  
    ```  
  
## <a name="process-partitions"></a><span data-ttu-id="42e67-147">Traiter les partitions</span><span class="sxs-lookup"><span data-stu-id="42e67-147">Process Partitions</span></span>  
 <span data-ttu-id="42e67-148">Dans la boîte de dialogue **Gestionnaire de partition** , notez l’astérisque (**\***) en regard des noms de partition pour chacune des partitions que vous venez de créer.</span><span class="sxs-lookup"><span data-stu-id="42e67-148">In the **Partition Manager** dialog box, notice the asterisk (**\***) next to the partition names for each of the new partitions you just created.</span></span> <span data-ttu-id="42e67-149">Cela indique que la partition n'a pas été traitée (actualisée).</span><span class="sxs-lookup"><span data-stu-id="42e67-149">This indicates that the partition has not been processed (refreshed).</span></span> <span data-ttu-id="42e67-150">Lorsque vous créez de nouvelles partitions, vous devez exécuter une opération « Traiter les partitions » ou « Traiter la table » pour actualiser les données dans ces partitions.</span><span class="sxs-lookup"><span data-stu-id="42e67-150">When you create new partitions, you should run a Process Partitions or Process Table operation to refresh the data in those partitions.</span></span>  
  
#### <a name="to-process-internet-sales-partitions"></a><span data-ttu-id="42e67-151">Pour traiter les partitions Internet Sales</span><span class="sxs-lookup"><span data-stu-id="42e67-151">To process Internet Sales partitions</span></span>  
  
1.  <span data-ttu-id="42e67-152">Cliquez sur **OK** pour fermer la boîte de dialogue **Gestionnaire de partition** .</span><span class="sxs-lookup"><span data-stu-id="42e67-152">Click **OK** to close the **Partition Manager** dialog box.</span></span>  
  
2.  <span data-ttu-id="42e67-153">Dans le Concepteur de modèles, cliquez sur la table **Internet Sales** , cliquez sur le menu **Modèle** , puis pointez sur **Traiter** (Actualiser) et enfin, cliquez sur **Traiter les partitions**.</span><span class="sxs-lookup"><span data-stu-id="42e67-153">In the model designer, click the **Internet Sales** table, then click the **Model** menu, then point to **Process** (Refresh), and then click **Process Partitions**.</span></span>  
  
3.  <span data-ttu-id="42e67-154">Dans la boîte de dialogue **Traiter les partitions** , vérifiez que le **Mode** est défini sur **Traiter par défaut**.</span><span class="sxs-lookup"><span data-stu-id="42e67-154">In the **Process Partitions** dialog box, verify the **Mode** is set to **Process Default**.</span></span>  
  
4.  <span data-ttu-id="42e67-155">Cochez la case située dans la colonne **Processus** pour chacune des cinq partitions que vous avez créées, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="42e67-155">Select the checkbox in the **Process** column for each of the five partitions you created, and then click **OK**.</span></span>  
  
     <span data-ttu-id="42e67-156">Si vous êtes invité à fournir les informations d'emprunt d'identité, entrez le nom d'utilisateur Windows et le mot de passe spécifiés dans la leçon 2, étape 6.</span><span class="sxs-lookup"><span data-stu-id="42e67-156">If you are prompted for Impersonation credentials, enter the Windows user name and password you specified in Lesson 2, step 6.</span></span>  
  
     <span data-ttu-id="42e67-157">La boîte de dialogue **traitement des données** apparaît et affiche les détails du processus pour chaque partition.</span><span class="sxs-lookup"><span data-stu-id="42e67-157">The **Data Process** dialog box then appears and displays process details for each partition.</span></span> <span data-ttu-id="42e67-158">Notez qu'un nombre de lignes différent est transféré pour chaque partition.</span><span class="sxs-lookup"><span data-stu-id="42e67-158">Notice that a different number of rows for each partition are transferred.</span></span> <span data-ttu-id="42e67-159">Cela est dû au fait que chaque partition contient uniquement les lignes de l'année spécifiée dans la clause WHERE dans l'instruction SQL.</span><span class="sxs-lookup"><span data-stu-id="42e67-159">This is because each partition includes only those rows for the year specified in the WHERE clause in the SQL Statement.</span></span> <span data-ttu-id="42e67-160">Il n'y a pas de données pour l'année 2010.</span><span class="sxs-lookup"><span data-stu-id="42e67-160">There is no data for the 2010 year.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="42e67-161">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="42e67-161">Next Steps</span></span>  
 <span data-ttu-id="42e67-162">Pour continuer ce didacticiel, passez à la leçon suivante : [Leçon 12 : Créer des rôles](lesson-11-create-roles.md).</span><span class="sxs-lookup"><span data-stu-id="42e67-162">To continue this tutorial, go to the next lesson: Lesson: [Lesson 12: Create Roles](lesson-11-create-roles.md).</span></span>  
  
  
