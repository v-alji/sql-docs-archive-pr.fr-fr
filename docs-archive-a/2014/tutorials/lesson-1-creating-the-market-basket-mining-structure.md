---
title: 'Leçon 1 : création de la structure d’exploration de données Market Basket | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a817c8d1-aff4-42b4-b194-ad9cc1c60f35
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: a6a6e123e525512a72d70bcc8ca2eba549d1347e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703540"
---
# <a name="lesson-1-creating-the-market-basket-mining-structure"></a><span data-ttu-id="1d17e-102">Leçon 1 : Création de la structure d’exploration de données Market Basket</span><span class="sxs-lookup"><span data-stu-id="1d17e-102">Lesson 1: Creating the Market Basket Mining Structure</span></span>
  <span data-ttu-id="1d17e-103">Dans cette leçon, vous allez créer une structure d'exploration de données à l'aide de laquelle vous pouvez prévoir quels produits [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] un client est susceptible d'acheter simultanément.</span><span class="sxs-lookup"><span data-stu-id="1d17e-103">In this lesson, you will create a mining structure that allows you to predict what [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] products a customer tends to purchase at the same time.</span></span> <span data-ttu-id="1d17e-104">Si vous n’êtes pas familiarisé avec les structures d’exploration de données et leur rôle dans l’exploration de données, consultez structures d’exploration de données [&#40;Analysis Services-exploration de données&#41;](../../2014/analysis-services/data-mining/mining-structures-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="1d17e-104">If you are unfamiliar with mining structures and their role in data mining, see [Mining Structures &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/mining-structures-analysis-services-data-mining.md).</span></span>  
  
 <span data-ttu-id="1d17e-105">La structure d’exploration de données d’association que vous allez créer dans cette leçon prend en charge l’ajout de modèles d’exploration de données basés sur l' [algorithme Microsoft Association](../../2014/analysis-services/data-mining/microsoft-association-algorithm.md).</span><span class="sxs-lookup"><span data-stu-id="1d17e-105">The association mining structure that you will create in this lesson supports adding mining models based on the [Microsoft Association Algorithm](../../2014/analysis-services/data-mining/microsoft-association-algorithm.md).</span></span> <span data-ttu-id="1d17e-106">Au cours d'autres leçons, vous utiliserez les modèles d'exploration de données pour prévoir les types de produits qu'un client est susceptible d'acheter en même temps (on parle dans ce cas d'analyse de panier d'achat).</span><span class="sxs-lookup"><span data-stu-id="1d17e-106">In later lessons, you will use the mining models to predict the type of products a customer tends to purchase at the same time, which is called a market basket analysis.</span></span> <span data-ttu-id="1d17e-107">Par exemple, vous découvrirez peut-être que des clients peuvent acheter en même temps des VTT, des pneus et des casques.</span><span class="sxs-lookup"><span data-stu-id="1d17e-107">For example, you may find that customers tend to buy mountain bikes, bike tires, and helmets at the same time.</span></span>  
  
 <span data-ttu-id="1d17e-108">Dans cette leçon, la structure d'exploration de données est définie à l'aide de tables imbriquées.</span><span class="sxs-lookup"><span data-stu-id="1d17e-108">In this lesson, the mining structure is defined by using nested tables.</span></span> <span data-ttu-id="1d17e-109">Les tables imbriquées sont utilisées puisque le domaine de données défini par la structure apparaît dans deux tables source différentes.</span><span class="sxs-lookup"><span data-stu-id="1d17e-109">Nested tables are used because the data domain that will be defined by the structure is contained within two different source tables.</span></span> <span data-ttu-id="1d17e-110">Pour plus d’informations sur les tables imbriquées, consultez [tables imbriquées &#40;Analysis Services-exploration de données&#41;](../../2014/analysis-services/data-mining/nested-tables-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="1d17e-110">For more information on nested tables, see [Nested Tables &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/nested-tables-analysis-services-data-mining.md).</span></span>  
  
## <a name="create-mining-structure-statement"></a><span data-ttu-id="1d17e-111">Instruction CREATE MINING STRUCTURE</span><span class="sxs-lookup"><span data-stu-id="1d17e-111">CREATE MINING STRUCTURE Statement</span></span>  
 <span data-ttu-id="1d17e-112">Pour créer une structure d’exploration de données contenant une table imbriquée, vous utilisez l’instruction [Create Mining structure &#40;DMX&#41;](/sql/dmx/create-mining-structure-dmx) .</span><span class="sxs-lookup"><span data-stu-id="1d17e-112">In order to create a mining structure containing a nested table, you use the [CREATE MINING STRUCTURE &#40;DMX&#41;](/sql/dmx/create-mining-structure-dmx) statement.</span></span> <span data-ttu-id="1d17e-113">Le code de l’instruction peut être divisé en plusieurs parties :</span><span class="sxs-lookup"><span data-stu-id="1d17e-113">The code in the statement can be broken into the following parts:</span></span>  
  
-   <span data-ttu-id="1d17e-114">Attribution d'un nom à la structure</span><span class="sxs-lookup"><span data-stu-id="1d17e-114">Naming the structure</span></span>  
  
-   <span data-ttu-id="1d17e-115">Définition de la colonne clé</span><span class="sxs-lookup"><span data-stu-id="1d17e-115">Defining the key column</span></span>  
  
-   <span data-ttu-id="1d17e-116">Définition des colonnes d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="1d17e-116">Defining the mining columns</span></span>  
  
-   <span data-ttu-id="1d17e-117">Définition des colonnes de la table imbriquée</span><span class="sxs-lookup"><span data-stu-id="1d17e-117">Defining the nested table columns</span></span>  
  
 <span data-ttu-id="1d17e-118">L'exemple générique suivant utilise l'instruction CREATE MINING STRUCTURE :</span><span class="sxs-lookup"><span data-stu-id="1d17e-118">The following is a generic example of the CREATE MINING STRUCTURE statement:</span></span>  
  
```  
CREATE MINING STRUCTURE [<Mining Structure Name>]  
(  
   <key column>,  
   <mining structure columns>,  
   <table columns>  
   (  <nested key column>,  
      <nested mining structure columns> )  
)  
  
```  
  
 <span data-ttu-id="1d17e-119">La première ligne du code définit le nom de la structure :</span><span class="sxs-lookup"><span data-stu-id="1d17e-119">The first line of the code defines the name of the structure:</span></span>  
  
```  
CREATE MINING STRUCTURE [Mining Structure Name]  
```  
  
 <span data-ttu-id="1d17e-120">Pour plus d’informations sur l’attribution d’un nom à un objet dans DMX, consultez [identificateurs &#40;dmx&#41;](/sql/dmx/identifiers-dmx).</span><span class="sxs-lookup"><span data-stu-id="1d17e-120">For information about naming an object in DMX, see [Identifiers &#40;DMX&#41;](/sql/dmx/identifiers-dmx).</span></span>  
  
 <span data-ttu-id="1d17e-121">La ligne suivante du code définit la colonne clé de la structure d'exploration de données qui identifie de manière unique une entité au sein des données source :</span><span class="sxs-lookup"><span data-stu-id="1d17e-121">The next line of the code defines the key column for the mining structure, which uniquely identifies an entity in the source data:</span></span>  
  
```  
<key column>  
```  
  
 <span data-ttu-id="1d17e-122">La ligne suivante du code permet de définir les colonnes d'exploration de données qu'utilisent les modèles d'exploration de données associés à la structure d'exploration de données :</span><span class="sxs-lookup"><span data-stu-id="1d17e-122">The next line of the code is used to define the mining columns that will be used by the mining models associated with the mining structure:</span></span>  
  
```  
<mining structure columns>  
```  
  
 <span data-ttu-id="1d17e-123">Les lignes suivantes du code définissent les colonnes de la table imbriquée :</span><span class="sxs-lookup"><span data-stu-id="1d17e-123">The next lines of the code define the nested table columns:</span></span>  
  
```  
<table columns>  
(  <nested key column>,  
   <nested mining structure columns> )  
```  
  
 <span data-ttu-id="1d17e-124">Pour plus d’informations sur les types de colonnes de structure d’exploration de données que vous pouvez définir, consultez [colonnes de structure d’exploration](../../2014/analysis-services/data-mining/mining-structure-columns.md)de données.</span><span class="sxs-lookup"><span data-stu-id="1d17e-124">For information about the types of mining structure columns that you can define, see [Mining Structure Columns](../../2014/analysis-services/data-mining/mining-structure-columns.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1d17e-125">Par défaut, [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] crée un jeu de données d'exclusion de 30 pour cent pour chaque structure d'exploration de données ; toutefois, lorsque vous utilisez DMX pour créer une structure d'exploration de données, vous devez ajouter manuellement le jeu de données d'exclusion, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="1d17e-125">By default, [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] creates a 30 percent holdout data set for each mining structure; however, when you use DMX to create a mining structure, you must manually add the holdout data set, if desired.</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="1d17e-126">Tâches de la leçon</span><span class="sxs-lookup"><span data-stu-id="1d17e-126">Lesson Tasks</span></span>  
 <span data-ttu-id="1d17e-127">Dans cette leçon, vous allez effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="1d17e-127">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="1d17e-128">créer une requête vide ;</span><span class="sxs-lookup"><span data-stu-id="1d17e-128">Create a new blank query</span></span>  
  
-   <span data-ttu-id="1d17e-129">modifier la requête pour créer la structure d'exploration de données ;</span><span class="sxs-lookup"><span data-stu-id="1d17e-129">Alter the query to create the mining structure</span></span>  
  
-   <span data-ttu-id="1d17e-130">Exécuter la requête</span><span class="sxs-lookup"><span data-stu-id="1d17e-130">Execute the query</span></span>  
  
## <a name="creating-the-query"></a><span data-ttu-id="1d17e-131">Création de la requête</span><span class="sxs-lookup"><span data-stu-id="1d17e-131">Creating the Query</span></span>  
 <span data-ttu-id="1d17e-132">La première étape consiste à se connecter à une instance de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] et à créer une nouvelle requête DMX dans [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1d17e-132">The first step is to connect to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] and create a new DMX query in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
#### <a name="to-create-a-new-dmx-query-in-sql-server-management-studio"></a><span data-ttu-id="1d17e-133">Pour créer une requête DMX dans SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1d17e-133">To create a new DMX query in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="1d17e-134">Ouvrez [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1d17e-134">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="1d17e-135">Dans la boîte de dialogue **se connecter au serveur** , pour **type de serveur**, sélectionnez **Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="1d17e-135">In the **Connect to Server** dialog box, for **Server type**, select **Analysis Services**.</span></span> <span data-ttu-id="1d17e-136">Dans **nom du serveur**, tapez `LocalHost` ou le nom de l’instance de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] à laquelle vous souhaitez vous connecter pour cette leçon.</span><span class="sxs-lookup"><span data-stu-id="1d17e-136">In **Server name**, type `LocalHost`, or the name of the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] that you want to connect to for this lesson.</span></span> <span data-ttu-id="1d17e-137">Cliquez sur **Connecter**.</span><span class="sxs-lookup"><span data-stu-id="1d17e-137">Click **Connect**.</span></span>  
  
3.  <span data-ttu-id="1d17e-138">Dans l' **Explorateur d’objets**, cliquez avec le bouton droit sur l’instance de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , pointez sur **nouvelle requête**, puis cliquez sur **DMX**.</span><span class="sxs-lookup"><span data-stu-id="1d17e-138">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="1d17e-139">L'Éditeur de requête s'ouvre et contient une nouvelle requête vide.</span><span class="sxs-lookup"><span data-stu-id="1d17e-139">Query Editor opens and contains a new, blank query.</span></span>  
  
## <a name="altering-the-query"></a><span data-ttu-id="1d17e-140">Modification de la requête</span><span class="sxs-lookup"><span data-stu-id="1d17e-140">Altering the Query</span></span>  
 <span data-ttu-id="1d17e-141">L'étape suivante implique de modifier l'instruction CREATE MINING STRUCTURE décrite ci-avant en vue de créer la structure d'exploration de données Market Basket.</span><span class="sxs-lookup"><span data-stu-id="1d17e-141">The next step is to modify the CREATE MINING STRUCTURE statement described above to create the Market Basket mining structure.</span></span>  
  
#### <a name="to-customize-the-create-mining-structure-statement"></a><span data-ttu-id="1d17e-142">Pour personnaliser l'instruction CREATE MINING STRUCTURE</span><span class="sxs-lookup"><span data-stu-id="1d17e-142">To customize the CREATE MINING STRUCTURE statement</span></span>  
  
1.  <span data-ttu-id="1d17e-143">Dans l’éditeur de requête, copiez l’exemple générique de l’instruction CREATe MINING STRUCTURE dans la requête vide.</span><span class="sxs-lookup"><span data-stu-id="1d17e-143">In Query Editor, copy the generic example of the CREATE MINING STRUCTURE statement into the blank query.</span></span>  
  
2.  <span data-ttu-id="1d17e-144">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="1d17e-144">Replace the following:</span></span>  
  
    ```  
    [mining structure name]   
    ```  
  
     <span data-ttu-id="1d17e-145">par :</span><span class="sxs-lookup"><span data-stu-id="1d17e-145">with:</span></span>  
  
    ```  
    [Market Basket]  
    ```  
  
3.  <span data-ttu-id="1d17e-146">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="1d17e-146">Replace the following:</span></span>  
  
    ```  
    <key column>  
    ```  
  
     <span data-ttu-id="1d17e-147">par :</span><span class="sxs-lookup"><span data-stu-id="1d17e-147">with:</span></span>  
  
    ```  
    OrderNumber TEXT KEY  
    ```  
  
4.  <span data-ttu-id="1d17e-148">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="1d17e-148">Replace the following:</span></span>  
  
    ```  
    <table columns>  
    (  <nested key column>,  
       <nested mining structure columns> )  
    ```  
  
     <span data-ttu-id="1d17e-149">par :</span><span class="sxs-lookup"><span data-stu-id="1d17e-149">with:</span></span>  
  
    ```  
    [Products] TABLE (  
        [Model] TEXT KEY  
    )  
    ```  
  
     <span data-ttu-id="1d17e-150">Le langage TEXT KEY précise que la colonne Model est la colonne clé de la table imbriquée.</span><span class="sxs-lookup"><span data-stu-id="1d17e-150">The TEXT KEY language specifies that the Model column is the key column for the nested table.</span></span>  
  
     <span data-ttu-id="1d17e-151">L'instruction complète de la structure d'exploration de données doit se présenter comme suit :</span><span class="sxs-lookup"><span data-stu-id="1d17e-151">The complete mining structure statement should now be as follows:</span></span>  
  
    ```  
    CREATE MINING STRUCTURE [Market Basket] (  
        OrderNumber TEXT KEY,  
        [Products] TABLE (  
            [Model] TEXT KEY  
        )  
    )  
    ```  
  
5.  <span data-ttu-id="1d17e-152">Dans le menu **fichier** , cliquez sur **Enregistrer DMXQuery1. DMX sous**.</span><span class="sxs-lookup"><span data-stu-id="1d17e-152">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
6.  <span data-ttu-id="1d17e-153">Dans la boîte de dialogue **Enregistrer sous** , accédez au dossier approprié et nommez le fichier `Market Basket Structure.dmx` .</span><span class="sxs-lookup"><span data-stu-id="1d17e-153">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Market Basket Structure.dmx`.</span></span>  
  
## <a name="executing-the-query"></a><span data-ttu-id="1d17e-154">Exécution de la requête</span><span class="sxs-lookup"><span data-stu-id="1d17e-154">Executing the Query</span></span>  
 <span data-ttu-id="1d17e-155">La dernière étape concerne l'exécution de la requête.</span><span class="sxs-lookup"><span data-stu-id="1d17e-155">The final step is to execute the query.</span></span> <span data-ttu-id="1d17e-156">Après avoir été créée et enregistrée, la requête doit être exécutée (l'instruction doit être exécutée) pour permettre la création de la structure d'exploration de données sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="1d17e-156">After a query is created and saved, it needs to be executed (that is, the statement needs to be run) in order to create the mining structure on the server.</span></span> <span data-ttu-id="1d17e-157">Pour plus d’informations sur l’exécution de requêtes dans l’éditeur de requête, consultez [moteur de base de données l’éditeur de requête &#40;SQL Server Management Studio&#41;](../relational-databases/scripting/database-engine-query-editor-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="1d17e-157">For more information about executing queries in Query Editor, see [Database Engine Query Editor &#40;SQL Server Management Studio&#41;](../relational-databases/scripting/database-engine-query-editor-sql-server-management-studio.md).</span></span>  
  
#### <a name="to-execute-the-query"></a><span data-ttu-id="1d17e-158">Pour exécuter la requête</span><span class="sxs-lookup"><span data-stu-id="1d17e-158">To execute the query</span></span>  
  
-   <span data-ttu-id="1d17e-159">Dans l’éditeur de requête, dans la barre d’outils, cliquez sur **exécuter**.</span><span class="sxs-lookup"><span data-stu-id="1d17e-159">In Query Editor, on the toolbar, click **Execute**.</span></span>  
  
     <span data-ttu-id="1d17e-160">L’état de la requête s’affiche dans l’onglet **messages** en bas de l’éditeur de requête à la fin de l’exécution de l’instruction.</span><span class="sxs-lookup"><span data-stu-id="1d17e-160">The status of the query is displayed in the **Messages** tab at the bottom of Query Editor after the statement finishes executing.</span></span> <span data-ttu-id="1d17e-161">Les messages doivent révéler le texte suivant :</span><span class="sxs-lookup"><span data-stu-id="1d17e-161">Messages should display:</span></span>  
  
    ```  
    Executing the query   
    Execution complete  
    ```  
  
     <span data-ttu-id="1d17e-162">Une nouvelle structure nommée **Market panier** existe désormais sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="1d17e-162">A new structure named **Market Basket** now exists on the server.</span></span>  
  
 <span data-ttu-id="1d17e-163">Dans la leçon suivante, vous allez ajouter des modèles d'exploration de données à la structure Market Basket que vous venez de créer.</span><span class="sxs-lookup"><span data-stu-id="1d17e-163">In the next lesson, you will add mining models to the Market Basket mining structure you just created.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="1d17e-164">Leçon suivante</span><span class="sxs-lookup"><span data-stu-id="1d17e-164">Next Lesson</span></span>  
 [<span data-ttu-id="1d17e-165">Leçon 2 : Ajout de modèles d’exploration de données à la structure d’exploration de données Market Basket</span><span class="sxs-lookup"><span data-stu-id="1d17e-165">Lesson 2: Adding Mining Models to the Market Basket Mining Structure</span></span>](../../2014/tutorials/lesson-2-adding-mining-models-to-the-market-basket-mining-structure.md)  
  
  
