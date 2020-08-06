---
title: 'Leçon 3 : traitement de la structure d’exploration de données Market panier | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 095a043f-cf6f-45bb-a021-ae4e1b535c65
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: ce2c2e6944d524a38edc331d2cd128ca7cf7d419
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694879"
---
# <a name="lesson-3-processing-the-market-basket-mining-structure"></a><span data-ttu-id="d48be-102">Leçon 3 : Traitement de la structure d'exploration de données Market Basket</span><span class="sxs-lookup"><span data-stu-id="d48be-102">Lesson 3: Processing the Market Basket Mining Structure</span></span>
  <span data-ttu-id="d48be-103">Dans cette leçon, vous allez utiliser l’instruction [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx) et VAssocSeqLineItems et vAssocSeqOrders de l' [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] exemple de base de données pour traiter les structures d’exploration de données et les modèles d’exploration de données que vous avez créés au cours de la [leçon 1 : création de la structure d’exploration](../../2014/tutorials/lesson-1-creating-the-market-basket-mining-structure.md) de données de panier d’exploitation et [leçon 2 : ajout de modèles d’exploration de données à la structure d’exploration de](../../2014/tutorials/lesson-2-adding-mining-models-to-the-market-basket-mining-structure.md)</span><span class="sxs-lookup"><span data-stu-id="d48be-103">In this lesson, you will use the [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx) statement and the vAssocSeqLineItems and vAssocSeqOrders from the [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] sample database to process the mining structures and mining models that you created in [Lesson 1: Creating the Market Basket Mining Structure](../../2014/tutorials/lesson-1-creating-the-market-basket-mining-structure.md) and [Lesson 2: Adding Mining Models to the Market Basket Mining Structure](../../2014/tutorials/lesson-2-adding-mining-models-to-the-market-basket-mining-structure.md).</span></span>  
  
 <span data-ttu-id="d48be-104">Lorsque vous traitez une structure d'exploration de données, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] lit les données sources et génère les structures qui soutiennent les modèles d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="d48be-104">When you process a mining structure, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] reads the source data and builds the structures that support mining models.</span></span> <span data-ttu-id="d48be-105">Lorsque vous traitez un modèle d’exploration de données, les données définies par la structure d’exploration de données sont transmises via l’algorithme d’exploration de données que vous avez choisi.</span><span class="sxs-lookup"><span data-stu-id="d48be-105">When you process a mining model, the data defined by the mining structure is passed through the data mining algorithm that you chose.</span></span> <span data-ttu-id="d48be-106">L'algorithme recherche des tendances et des modèles, puis stocke les informations recueillies dans le modèle d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="d48be-106">The algorithm searches for trends and patterns, and then stores this information in the mining model.</span></span> <span data-ttu-id="d48be-107">Par conséquent, le modèle d'exploration de données ne contient pas les données source réelles mais plutôt les informations recueillies par l'algorithme.</span><span class="sxs-lookup"><span data-stu-id="d48be-107">The mining model, therefore, does not contain the actual source data, but instead contains the information that was discovered by the algorithm.</span></span> <span data-ttu-id="d48be-108">Pour plus d’informations sur le traitement des modèles d’exploration de données, consultez [exigences et considérations relatives au traitement &#40;&#41;d’exploration de données ](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="d48be-108">For more information about processing mining models, see [Processing Requirements and Considerations &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md).</span></span>  
  
 <span data-ttu-id="d48be-109">Si vous modifiez une colonne de structure ou les données source, vous devez simplement retraiter la structure d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="d48be-109">You only have to reprocess a mining structure if you change a structure column or change the source data.</span></span> <span data-ttu-id="d48be-110">Si vous ajoutez un modèle d'exploration de données à une structure d'exploration de données déjà traitée, vous pouvez utiliser l'instruction `INSERT INTO MINING MODEL` pour effectuer l'apprentissage du nouveau modèle d'exploration de données sur les données existantes.</span><span class="sxs-lookup"><span data-stu-id="d48be-110">If you add a mining model to a mining structure that has already been processed, you can use the `INSERT INTO MINING MODEL` statement to train the new mining model on the existing data.</span></span>  
  
 <span data-ttu-id="d48be-111">Comme la structure d'exploration de données Market Basket contient une table imbriquée, vous devez définir les colonnes d'exploration de données sur lesquelles effectuer l'apprentissage à l'aide de la structure de la table imbriquée et utiliser la commande `SHAPE` pour définir les requêtes chargées d'extraire les données d'apprentissage à partir des tables source.</span><span class="sxs-lookup"><span data-stu-id="d48be-111">Because the Market Basket mining structure contains a nested table, you will have to define the mining columns to be trained using the nested table structure, and use the `SHAPE` command to define the queries that pull the training data from the source tables.</span></span>  
  
## <a name="insert-into-statement"></a><span data-ttu-id="d48be-112">Instruction INSERT INTO</span><span class="sxs-lookup"><span data-stu-id="d48be-112">INSERT INTO Statement</span></span>  
 <span data-ttu-id="d48be-113">Afin d’effectuer l’apprentissage de la structure d’exploration de données Market panier et de ses modèles d’exploration de données associés, utilisez l’instruction [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx) .</span><span class="sxs-lookup"><span data-stu-id="d48be-113">In order to train the Market Basket mining structure and its associated mining models, use the [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx) statement.</span></span> <span data-ttu-id="d48be-114">Le code de cette instruction peut être divisé selon les sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="d48be-114">The code in the statement can be broken into the following parts.</span></span>  
  
-   <span data-ttu-id="d48be-115">Identification de la structure d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="d48be-115">Identifying the mining structure</span></span>  
  
-   <span data-ttu-id="d48be-116">Liste des colonnes de la structure d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="d48be-116">Listing the columns in the mining structure</span></span>  
  
-   <span data-ttu-id="d48be-117">Définition des données d'apprentissage à l'aide de l'instruction `SHAPE`</span><span class="sxs-lookup"><span data-stu-id="d48be-117">Defining the training data using `SHAPE`</span></span>  
  
 <span data-ttu-id="d48be-118">L'exemple générique suivant utilise l'instruction `INSERT INTO` :</span><span class="sxs-lookup"><span data-stu-id="d48be-118">The following is a generic example of the `INSERT INTO` statement:</span></span>  
  
```  
INSERT INTO MINING STRUCTURE [<mining structure name>]  
(  
   <mining structure columns>  
   [<nested table>]  
   ( SKIP, <skipped column> )  
)  
SHAPE {  
  OPENQUERY([<datasource>],'<SELECT statement>') }  
APPEND  
(   
  {OPENQUERY([<datasource>],'<nested SELECT statement>')  
}  
RELATE [<case key>] TO [<foreign key>]  
) AS [<nested table>]  
```  
  
 <span data-ttu-id="d48be-119">La première ligne du code identifie la structure d'exploration de données à apprendre :</span><span class="sxs-lookup"><span data-stu-id="d48be-119">The first line of the code identifies the mining structure that you will train:</span></span>  
  
```  
INSERT INTO MINING STRUCTURE [<mining structure name>]  
```  
  
 <span data-ttu-id="d48be-120">Les lignes suivantes du code précisent les colonnes définies par la structure d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="d48be-120">The next lines of the code specify the columns that are defined by the mining structure.</span></span> <span data-ttu-id="d48be-121">Vous devez répertorier chaque colonne dans la structure d'exploration de données et chaque colonne doit mapper une colonne figurant dans les données de la requête source.</span><span class="sxs-lookup"><span data-stu-id="d48be-121">You must list each column in the mining structure, and each column must map to a column contained within the source query data.</span></span> <span data-ttu-id="d48be-122">Vous pouvez utiliser la commande `SKIP` pour ignorer les colonnes qui existent dans les données source, mais non dans la structure d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="d48be-122">You can use `SKIP` to ignore columns that exist in the source data but do not exist in the mining structure.</span></span> <span data-ttu-id="d48be-123">Pour plus d’informations sur l’utilisation de `SKIP` , consultez [insérer dans &#40;&#41;DMX ](/sql/dmx/insert-into-dmx).</span><span class="sxs-lookup"><span data-stu-id="d48be-123">For more information about how to use `SKIP`, see [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx).</span></span>  
  
```  
(  
   <mining structure columns>  
   [<nested table>]  
   ( SKIP, <skipped column> )  
)  
```  
  
 <span data-ttu-id="d48be-124">Les dernières lignes du code précisent les données à utiliser pour l'apprentissage de la structure d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="d48be-124">The final lines of the code define the data that will be used to train the mining structure.</span></span> <span data-ttu-id="d48be-125">Comme les données source figurent dans deux tables, vous allez faire appel à l'instruction `SHAPE` pour relier les tables.</span><span class="sxs-lookup"><span data-stu-id="d48be-125">Because the source data is contained within two tables, you will use `SHAPE` to relate the tables.</span></span>  
  
```  
SHAPE {  
  OPENQUERY([<datasource>],'<SELECT statement>') }  
APPEND  
(   
  {OPENQUERY([<datasource>],''<nested SELECT statement>'')  
}  
RELATE [<case key>] TO [<foreign key>]  
) AS [<nested table>]  
```  
  
 <span data-ttu-id="d48be-126">Dans cette leçon, vous allez utiliser l'instruction `OPENQUERY` pour définir les données sources.</span><span class="sxs-lookup"><span data-stu-id="d48be-126">In this lesson, you use `OPENQUERY` to define the source data.</span></span> <span data-ttu-id="d48be-127">Pour plus d’informations sur les autres méthodes de définition d’une requête sur les données sources, consultez [&#60;&#62;de requête de données source ](/sql/dmx/source-data-query).</span><span class="sxs-lookup"><span data-stu-id="d48be-127">For information about other methods of defining a query on the source data, see [&#60;source data query&#62;](/sql/dmx/source-data-query).</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="d48be-128">Tâches de la leçon</span><span class="sxs-lookup"><span data-stu-id="d48be-128">Lesson Tasks</span></span>  
 <span data-ttu-id="d48be-129">Au cours de cette leçon, vous allez effectuer la tâche suivante :</span><span class="sxs-lookup"><span data-stu-id="d48be-129">You will perform the following task in this lesson:</span></span>  
  
-   <span data-ttu-id="d48be-130">traiter la structure d'exploration de données Market Basket.</span><span class="sxs-lookup"><span data-stu-id="d48be-130">Process the Market Basket mining structure</span></span>  
  
## <a name="processing-the-market-basket-mining-structure"></a><span data-ttu-id="d48be-131">Traitement de la structure d'exploration de données Market Basket</span><span class="sxs-lookup"><span data-stu-id="d48be-131">Processing the Market Basket Mining Structure</span></span>  
  
#### <a name="to-process-the-mining-structure-by-using-insert-into"></a><span data-ttu-id="d48be-132">Pour traiter la structure d'exploration de données à l'aide de l'instruction INSERT INTO</span><span class="sxs-lookup"><span data-stu-id="d48be-132">To process the mining structure by using INSERT INTO</span></span>  
  
1.  <span data-ttu-id="d48be-133">Dans l' **Explorateur d’objets**, cliquez avec le bouton droit sur l’instance de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , pointez sur **nouvelle requête**, puis cliquez sur **DMX**.</span><span class="sxs-lookup"><span data-stu-id="d48be-133">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="d48be-134">L'Éditeur de requête s'ouvre et contient une nouvelle requête vide.</span><span class="sxs-lookup"><span data-stu-id="d48be-134">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="d48be-135">Copiez l'exemple générique de l'instruction INSERT INTO dans la requête vide.</span><span class="sxs-lookup"><span data-stu-id="d48be-135">Copy the generic example of the INSERT INTO statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="d48be-136">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="d48be-136">Replace the following:</span></span>  
  
    ```  
    [<mining structure>]  
    ```  
  
     <span data-ttu-id="d48be-137">par :</span><span class="sxs-lookup"><span data-stu-id="d48be-137">with:</span></span>  
  
    ```  
    Market Basket  
    ```  
  
4.  <span data-ttu-id="d48be-138">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="d48be-138">Replace the following:</span></span>  
  
    ```  
    <mining structure columns>  
    [<nested table>]  
    ( SKIP, <skipped column> )  
    ```  
  
     <span data-ttu-id="d48be-139">par :</span><span class="sxs-lookup"><span data-stu-id="d48be-139">with:</span></span>  
  
    ```  
    [OrderNumber],  
    [Products]   
    (SKIP, [Model])  
    ```  
  
     <span data-ttu-id="d48be-140">Dans l'instruction, `Products` fait référence à la table Products définie par l'instruction SHAPE.</span><span class="sxs-lookup"><span data-stu-id="d48be-140">In the statement, `Products` refers to the Products table defined by the SHAPE statement.</span></span> <span data-ttu-id="d48be-141">`SKIP` est utilisé pour ignorer la colonne du modèle, qui existe dans les données sources comme clé, mais n'est pas utilisée par la structure d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="d48be-141">`SKIP` is used to ignore the Model column, which exists in the source data as a key, but is not used by the mining structure.</span></span>  
  
5.  <span data-ttu-id="d48be-142">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="d48be-142">Replace the following:</span></span>  
  
    ```  
    SHAPE {  
      OPENQUERY([<datasource>],'<SELECT statement>') }  
    APPEND  
    (   
      {OPENQUERY([<datasource>],'<nested SELECT statement>')  
    }  
    RELATE [<case key>] TO [<foreign key>]  
    ) AS [<nested table>]  
    ```  
  
     <span data-ttu-id="d48be-143">par :</span><span class="sxs-lookup"><span data-stu-id="d48be-143">with:</span></span>  
  
    ```  
    SHAPE {  
      OPENQUERY([Adventure Works DW],'SELECT OrderNumber  
                FROM vAssocSeqOrders ORDER BY OrderNumber')}  
    APPEND  
    (   
      {OPENQUERY([Adventure Works DW],'SELECT OrderNumber, Model FROM   
        dbo.vAssocSeqLineItems ORDER BY OrderNumber, Model')  
    }  
    RELATE OrderNumber to OrderNumber   
    ) AS [Products]  
    ```  
  
     <span data-ttu-id="d48be-144">La requête source fait référence [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] à la source de données définie dans l' [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] exemple de projet.</span><span class="sxs-lookup"><span data-stu-id="d48be-144">The source query references the [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] data source defined in the [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] sample project.</span></span> <span data-ttu-id="d48be-145">Elle utilise la source de données pour accéder aux vues vAssocSeqLineItems et vAssocSeqOrders.</span><span class="sxs-lookup"><span data-stu-id="d48be-145">It uses this data source to access the vAssocSeqLineItems and vAssocSeqOrders views.</span></span> <span data-ttu-id="d48be-146">Ces vues renferment les données source à utiliser pour effectuer l'apprentissage du modèle d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="d48be-146">These views contain the source data that will be used to train the mining model.</span></span> <span data-ttu-id="d48be-147">Si vous n’avez pas créé ce projet ou ces vues, consultez le didacticiel sur l' [exploration de données de base](../../2014/tutorials/basic-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="d48be-147">If you have not created this project or these views, see [Basic Data Mining Tutorial](../../2014/tutorials/basic-data-mining-tutorial.md).</span></span>  
  
     <span data-ttu-id="d48be-148">Dans la commande `SHAPE`, vous allez utiliser `OPENQUERY` pour définir deux requêtes.</span><span class="sxs-lookup"><span data-stu-id="d48be-148">Within the `SHAPE` command, you will use `OPENQUERY` to define two queries.</span></span> <span data-ttu-id="d48be-149">La première requête définit la table parente, la deuxième définit la table imbriquée.</span><span class="sxs-lookup"><span data-stu-id="d48be-149">The first query defines the parent table, and the second query defines the nested table.</span></span> <span data-ttu-id="d48be-150">Les deux tables sont associées par le biais de la colonne OrderNumber présente dans les deux tables.</span><span class="sxs-lookup"><span data-stu-id="d48be-150">The two tables are related using the OrderNumber column, which exists in both tables.</span></span>  
  
     <span data-ttu-id="d48be-151">L'instruction tout entière doit se présenter comme suit :</span><span class="sxs-lookup"><span data-stu-id="d48be-151">The complete statement should now be as follows:</span></span>  
  
    ```  
    INSERT INTO MINING STRUCTURE [Market Basket]  
    (  
       [OrderNumber],[Products] (SKIP, [Model])  
    )  
    SHAPE {  
      OPENQUERY([Adventure Works DW],'SELECT OrderNumber  
                FROM vAssocSeqOrders ORDER BY OrderNumber')}  
    APPEND  
    (   
      {OPENQUERY([Adventure Works DW],'SELECT OrderNumber, Model FROM   
        dbo.vAssocSeqLineItems ORDER BY OrderNumber, Model')  
    }  
    RELATE OrderNumber to OrderNumber   
    ) AS [Products]  
    ```  
  
6.  <span data-ttu-id="d48be-152">Dans le menu **fichier** , cliquez sur **Enregistrer DMXQuery1. DMX sous**.</span><span class="sxs-lookup"><span data-stu-id="d48be-152">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
7.  <span data-ttu-id="d48be-153">Dans la boîte de dialogue **Enregistrer sous** , accédez au dossier approprié et nommez le fichier `Process Market Basket.dmx` .</span><span class="sxs-lookup"><span data-stu-id="d48be-153">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Process Market Basket.dmx`.</span></span>  
  
8.  <span data-ttu-id="d48be-154">Dans la barre d’outils, cliquez sur le bouton **exécuter** .</span><span class="sxs-lookup"><span data-stu-id="d48be-154">On the toolbar, click the **Execute** button.</span></span>  
  
 <span data-ttu-id="d48be-155">Après avoir terminé d'exécuter la requête, vous pouvez consulter les modèles et les jeux d'éléments trouvés, consulter les associations ou filtrer par jeu d'éléments, probabilité ou importance.</span><span class="sxs-lookup"><span data-stu-id="d48be-155">After the query has finished running, you can view the patterns and itemsets that were found, view associations, or filter by itemset, probability, or importance.</span></span> <span data-ttu-id="d48be-156">Pour afficher ces informations, dans [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] , cliquez avec le bouton droit sur le nom du modèle de données, puis cliquez sur **Parcourir**.</span><span class="sxs-lookup"><span data-stu-id="d48be-156">To view this information, in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], right-click the name of the data model, and then click **Browse**.</span></span>  
  
 <span data-ttu-id="d48be-157">Dans la leçon suivante, vous allez créer plusieurs prédictions fondées sur les modèles d'exploration de données que vous avez ajoutés à la structure Market Basket.</span><span class="sxs-lookup"><span data-stu-id="d48be-157">In the next lesson, you will create several predictions based on the mining models that you added to the Market Basket structure.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="d48be-158">Leçon suivante</span><span class="sxs-lookup"><span data-stu-id="d48be-158">Next Lesson</span></span>  
 [<span data-ttu-id="d48be-159">Leçon 4 : Exécution de prédictions Market Basket</span><span class="sxs-lookup"><span data-stu-id="d48be-159">Lesson 4: Executing Market Basket Predictions</span></span>](../../2014/tutorials/lesson-4-executing-market-basket-predictions.md)  
  
  
