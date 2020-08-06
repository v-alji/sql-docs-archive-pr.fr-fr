---
title: 'Étape 6 : Ajout et configuration des transformations de recherche | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5c59f723-9707-4407-80ae-f05f483cf65f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 96b0a848508c19eb24cf1538244a39fcec57361a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605576"
---
# <a name="step-6-adding-and-configuring-the-lookup-transformations"></a><span data-ttu-id="dd666-102">Étape 6 : Ajout et configuration des transformations de recherche</span><span class="sxs-lookup"><span data-stu-id="dd666-102">Step 6: Adding and Configuring the Lookup Transformations</span></span>
  <span data-ttu-id="dd666-103">Une fois que vous avez configuré la source de fichier plat pour extraire les données du fichier source, la tâche suivante consiste à définir les transformations de recherche nécessaires pour obtenir les valeurs de **CurrencyKey** et **DateKey**.</span><span class="sxs-lookup"><span data-stu-id="dd666-103">After you have configured the Flat File source to extract data from the source file, the next task is to define the Lookup transformations needed to obtain the values for the **CurrencyKey** and **DateKey**.</span></span> <span data-ttu-id="dd666-104">Une transformation de recherche effectue une recherche en joignant les données dans la colonne d'entrée spécifiée à une colonne dans un dataset de référence.</span><span class="sxs-lookup"><span data-stu-id="dd666-104">A Lookup transformation performs a lookup by joining data in the specified input column to a column in a reference dataset.</span></span> <span data-ttu-id="dd666-105">Le dataset de référence peut être une table ou une vue existante, une nouvelle table ou le résultat d'une instruction SQL.</span><span class="sxs-lookup"><span data-stu-id="dd666-105">The reference dataset can be an existing table or view, a new table, or the result of an SQL statement.</span></span> <span data-ttu-id="dd666-106">Dans ce didacticiel, la transformation de recherche utilise un gestionnaire de connexions OLE DB pour se connecter à la base de données qui contient les données servant de source au jeu de données de référence.</span><span class="sxs-lookup"><span data-stu-id="dd666-106">In this tutorial, the Lookup transformation uses an OLE DB connection manager to connect to the database that contains the data that is the source of the reference dataset.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dd666-107">Vous pouvez également configurer la transformation de recherche afin qu'elle se connecte à un cache qui contient le jeu de données de référence.</span><span class="sxs-lookup"><span data-stu-id="dd666-107">You can also configure the Lookup transformation to connect to a cache that contains the reference dataset.</span></span> <span data-ttu-id="dd666-108">Pour plus d’informations, voir [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="dd666-108">For more information, see [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
 <span data-ttu-id="dd666-109">Dans le cadre de ce didacticiel, vous allez ajouter et configurer les deux composants de transformation de recherche suivants dans le package :</span><span class="sxs-lookup"><span data-stu-id="dd666-109">For this tutorial, you will add and configure the following two Lookup transformation components to the package:</span></span>  
  
-   <span data-ttu-id="dd666-110">Une transformation pour effectuer une recherche des valeurs à partir de la colonne **CurrencyKey** de la table de dimensions **DimCurrency** basée sur la correspondance avec les valeurs de la colonne **CurrencyID** à partir du fichier plat.</span><span class="sxs-lookup"><span data-stu-id="dd666-110">One transformation to perform a lookup of values from the **CurrencyKey** column of the **DimCurrency** dimension table based on matching **CurrencyID** column values from the flat file.</span></span>  
  
-   <span data-ttu-id="dd666-111">Une transformation pour effectuer une recherche des valeurs à partir de la colonne **DateKey** de la table de dimensions **DimDate** basée sur la correspondance avec les valeurs de la colonne **CurrencyDate** à partir du fichier plat.</span><span class="sxs-lookup"><span data-stu-id="dd666-111">One transformation to perform a lookup of values from the **DateKey** column of the **DimDate** dimension table based on matching **CurrencyDate** column values from the flat file.</span></span>  
  
 <span data-ttu-id="dd666-112">Dans les deux cas, la transformation de recherche utilise le Gestionnaire de connexions OLE DB que vous avez créé précédemment.</span><span class="sxs-lookup"><span data-stu-id="dd666-112">In both cases, the Lookup transformation will utilize the OLE DB connection manager that you previously created.</span></span>  
  
### <a name="to-add-and-configure-the-lookup-currency-key-transformation"></a><span data-ttu-id="dd666-113">Pour ajouter et configurer la transformation Lookup Currency Key</span><span class="sxs-lookup"><span data-stu-id="dd666-113">To add and configure the Lookup Currency Key transformation</span></span>  
  
1.  <span data-ttu-id="dd666-114">Dans la **boîte à outils SSIS**, développez **commun**, puis faites glisser **recherche** sur l’aire de conception de l’onglet de **Workflow** . Placez la recherche directement sous la source de **données extraire l’exemple de devise** .</span><span class="sxs-lookup"><span data-stu-id="dd666-114">In the **SSIS Toolbox**, expand **Common**, and then drag **Lookup** onto the design surface of the **Data Flow** tab. Place Lookup directly below the **Extract Sample Currency Data** source.</span></span>  
  
2.  <span data-ttu-id="dd666-115">Sélectionnez la source de fichier plat **Extract Sample Currency Data** et faites glisser la flèche verte vers la transformation de **recherche** que vous venez d'ajouter pour connecter les deux composants.</span><span class="sxs-lookup"><span data-stu-id="dd666-115">Click the **Extract Sample Currency Data** flat file source and drag the green arrow onto the newly added **Lookup** transformation to connect the two components.</span></span>  
  
3.  <span data-ttu-id="dd666-116">Dans l'aire de conception **Flux de données** , cliquez sur **Recherche** dans la transformation de **Recherche** , puis remplacez le nom par **Lookup Currency Key**.</span><span class="sxs-lookup"><span data-stu-id="dd666-116">On the **Data Flow** design surface, click **Lookup** in the **Lookup** transformation, and change the name to **Lookup Currency Key**.</span></span>  
  
4.  <span data-ttu-id="dd666-117">Double-cliquez sur la transformation **Lookup CurrencyKey** pour afficher l’éditeur de transformation de recherche.</span><span class="sxs-lookup"><span data-stu-id="dd666-117">Double-click the **Lookup CurrencyKey** transformation to display the Lookup Transformation Editor.</span></span>  
  
5.  <span data-ttu-id="dd666-118">Dans la page **Général** , effectuez les sélections suivantes :</span><span class="sxs-lookup"><span data-stu-id="dd666-118">On the **General** page, make the following selections:</span></span>  
  
    1.  <span data-ttu-id="dd666-119">Sélectionnez **Cache complet**.</span><span class="sxs-lookup"><span data-stu-id="dd666-119">Select **Full cache**.</span></span>  
  
    2.  <span data-ttu-id="dd666-120">Dans la zone **Type de connexion** , sélectionnez **Gestionnaire de connexions OLE DB**.</span><span class="sxs-lookup"><span data-stu-id="dd666-120">In the **Connection type** area, select **OLE DB connection manager**.</span></span>  
  
6.  <span data-ttu-id="dd666-121">Dans la page **Connexion** , effectuez les sélections suivantes :</span><span class="sxs-lookup"><span data-stu-id="dd666-121">On the **Connection** page, make the following selections:</span></span>  
  
    1.  <span data-ttu-id="dd666-122">Dans la boîte de dialogue **Gestionnaire de connexions OLE DB** , assurez-vous que **localhost.AdventureWorksDW2012** est affiché.</span><span class="sxs-lookup"><span data-stu-id="dd666-122">In the **OLE DB connection manager** dialog box, ensure that **localhost.AdventureWorksDW2012** is displayed.</span></span>  
  
    2.  <span data-ttu-id="dd666-123">Sélectionnez **Utiliser les résultats d'une requête SQL**, puis tapez ou copiez l'instruction SQL suivante :</span><span class="sxs-lookup"><span data-stu-id="dd666-123">Select **Use results of an SQL query**, and then type or copy the following SQL statement:</span></span>  
  
        ```  
        select * from (select * from [dbo].[DimCurrency]) as refTable  
        where [refTable].[CurrencyAlternateKey] = 'ARS'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'AUD'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'BRL'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'CAD'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'CNY'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'DEM'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'EUR'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'FRF'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'GBP'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'JPY'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'MXN'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'SAR'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'USD'  
        OR  
        [refTable].[CurrencyAlternateKey] = 'VEB'  
        ```  
  
7.  <span data-ttu-id="dd666-124">Dans la page **Colonnes** , effectuez les sélections suivantes :</span><span class="sxs-lookup"><span data-stu-id="dd666-124">On the **Columns** page, make the following selections:</span></span>  
  
    1.  <span data-ttu-id="dd666-125">Dans le volet **Colonnes d'entrée disponibles** , faites glisser **CurrencyID** vers le volet **Colonnes de recherche disponibles** et déposez cet élément sur **CurrencyAlternateKey**.</span><span class="sxs-lookup"><span data-stu-id="dd666-125">In the **Available Input Columns** panel, drag **CurrencyID** to the **Available Lookup Columns** panel and drop it on **CurrencyAlternateKey**.</span></span>  
  
    2.  <span data-ttu-id="dd666-126">Dans la liste **Colonnes de recherche disponibles** , activez la case à cocher située à gauche de **CurrencyKey**.</span><span class="sxs-lookup"><span data-stu-id="dd666-126">In the **Available Lookup Columns** list, select the check box to the left of **CurrencyKey**.</span></span>  
  
8.  <span data-ttu-id="dd666-127">Cliquez sur **OK** pour revenir à l'aire de conception **Flux de données** .</span><span class="sxs-lookup"><span data-stu-id="dd666-127">Click **OK** to return to the **Data Flow** design surface.</span></span>  
  
9. <span data-ttu-id="dd666-128">Double-cliquez sur la transformation Lookup Currency Key, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="dd666-128">Right-click the Lookup Currency Key transformation, click **Properties**.</span></span>  
  
10. <span data-ttu-id="dd666-129">Dans la Fenêtre Propriétés, vérifiez que la `LocaleID` propriété est définie sur **anglais (États-Unis)** et que la propriété **DefaultCodePage** est définie sur **1252**.</span><span class="sxs-lookup"><span data-stu-id="dd666-129">In the Properties window, verify that the `LocaleID` property is set to **English (United States)** and the **DefaultCodePage** property is set to **1252**.</span></span>  
  
### <a name="to-add-and-configure-the--lookup-datekey-transformation"></a><span data-ttu-id="dd666-130">Pour ajouter et configurer la transformation Lookup Date Key</span><span class="sxs-lookup"><span data-stu-id="dd666-130">To add and configure the  Lookup DateKey transformation</span></span>  
  
1.  <span data-ttu-id="dd666-131">Dans la **Boîte à outils SSIS**, faites glisser **Recherche** vers l'aire de conception **Flux de données** .</span><span class="sxs-lookup"><span data-stu-id="dd666-131">In the **SSIS Toolbox**, drag **Lookup** onto the **Data Flow** design surface.</span></span> <span data-ttu-id="dd666-132">Placez la recherche directement sous la transformation **Lookup Currency Key** .</span><span class="sxs-lookup"><span data-stu-id="dd666-132">Place Lookup directly below the **Lookup Currency Key** transformation.</span></span>  
  
2.  <span data-ttu-id="dd666-133">Sélectionnez la transformation **Lookup Currency Key** et faites glisser la flèche verte vers la transformation de **recherche** que vous venez d'ajouter pour connecter les deux composants.</span><span class="sxs-lookup"><span data-stu-id="dd666-133">Click the **Lookup Currency Key** transformation and drag the green arrow onto the newly added **Lookup** transformation to connect the two components.</span></span>  
  
3.  <span data-ttu-id="dd666-134">Dans la boîte de dialogue **Sélection entrée et sortie** , cliquez sur **Sortie de recherche avec correspondance** dans la zone de liste de **Sortie** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="dd666-134">In the **Input Output Selection** dialog box, click **Lookup Match Output** in the **Output** list box, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="dd666-135">Dans l'aire de conception **Flux de données** , cliquez sur **Recherche** dans la transformation **Recherche** que vous venez d'ajouter, puis remplacez le nom par **Lookup Date Key**.</span><span class="sxs-lookup"><span data-stu-id="dd666-135">On the **Data Flow** design surface, click **Lookup** in the newly added **Lookup** transformation, and change the name to **Lookup Date Key**.</span></span>  
  
5.  <span data-ttu-id="dd666-136">Double-cliquez sur la transformation **Lookup Date Key** .</span><span class="sxs-lookup"><span data-stu-id="dd666-136">Double-click the **Lookup Date Key** transformation.</span></span>  
  
6.  <span data-ttu-id="dd666-137">Dans la page **Général** , sélectionnez **Cache partiel**.</span><span class="sxs-lookup"><span data-stu-id="dd666-137">On the **General** page, select **Partial cache**.</span></span>  
  
7.  <span data-ttu-id="dd666-138">Dans la page **Connexion** , effectuez les sélections suivantes :</span><span class="sxs-lookup"><span data-stu-id="dd666-138">On the **Connection** page, make the following selections:</span></span>  
  
    1.  <span data-ttu-id="dd666-139">Dans la boîte de dialogue **Gestionnaire de connexions OLE DB** , vérifiez que **localhost.AdventureWorksDW2012** est affiché.</span><span class="sxs-lookup"><span data-stu-id="dd666-139">In the **OLEDB connection manager** dialog box, ensure that **localhost.AdventureWorksDW2012** is displayed.</span></span>  
  
    2.  <span data-ttu-id="dd666-140">Dans la zone **Utiliser une table ou une vue** , tapez ou sélectionnez **[dbo].[DimDate]**.</span><span class="sxs-lookup"><span data-stu-id="dd666-140">In the **Use a table or view** box, type or select **[dbo].[DimDate]**.</span></span>  
  
8.  <span data-ttu-id="dd666-141">Dans la page **Colonnes** , effectuez les sélections suivantes :</span><span class="sxs-lookup"><span data-stu-id="dd666-141">On the **Columns** page, make the following selections:</span></span>  
  
    1.  <span data-ttu-id="dd666-142">Dans le volet **Colonnes d'entrée disponibles** , faites glisser **CurrencyDate** vers le volet **Colonnes de recherche disponibles** et déposez cet élément sur **FullDateAlternateKey**.</span><span class="sxs-lookup"><span data-stu-id="dd666-142">In the **Available Input Columns** panel, drag **CurrencyDate** to the **Available Lookup Columns** panel and drop it on **FullDateAlternateKey**.</span></span>  
  
    2.  <span data-ttu-id="dd666-143">Dans la liste **Colonnes de recherche disponibles** , activez la case à cocher située à gauche de **DateKey**.</span><span class="sxs-lookup"><span data-stu-id="dd666-143">In the **Available Lookup Columns** list, select the check box to the left of **DateKey**.</span></span>  
  
9. <span data-ttu-id="dd666-144">Dans la page **Avancé** , examinez les options de mise en cache.</span><span class="sxs-lookup"><span data-stu-id="dd666-144">On the **Advanced** page, review the caching options.</span></span>  
  
10. <span data-ttu-id="dd666-145">Cliquez sur **OK** pour revenir à l'aire de conception **Flux de données** .</span><span class="sxs-lookup"><span data-stu-id="dd666-145">Click **OK** to return to the **Data Flow** design surface.</span></span>  
  
11. <span data-ttu-id="dd666-146">Double-cliquez sur la transformation Lookup Date Key, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="dd666-146">Right-click the Lookup Date Key transformation and click **Properties.**</span></span>  
  
12. <span data-ttu-id="dd666-147">Dans la Fenêtre Propriétés, vérifiez que la `LocaleID` propriété est définie sur **anglais (États-Unis)** et que la propriété **DefaultCodePage** est définie sur **1252**.</span><span class="sxs-lookup"><span data-stu-id="dd666-147">In the Properties window, verify that the `LocaleID` property is set to **English (United States)** and the **DefaultCodePage** property is set to **1252**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="dd666-148">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="dd666-148">Next Task in Lesson</span></span>  
 [<span data-ttu-id="dd666-149">Étape 7 : Ajout et configuration de la destination OLE DB</span><span class="sxs-lookup"><span data-stu-id="dd666-149">Step 7: Adding and Configuring the OLE DB Destination</span></span>](lesson-1-7-adding-and-configuring-the-ole-db-destination.md)  
  
## <a name="see-also"></a><span data-ttu-id="dd666-150">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="dd666-150">See Also</span></span>  
 [<span data-ttu-id="dd666-151">Transformation de recherche</span><span class="sxs-lookup"><span data-stu-id="dd666-151">Lookup Transformation</span></span>](data-flow/transformations/lookup-transformation.md)  
  
  
