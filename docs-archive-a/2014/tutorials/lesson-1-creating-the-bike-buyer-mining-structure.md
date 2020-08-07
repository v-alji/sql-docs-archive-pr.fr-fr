---
title: 'Leçon 1 : création de la structure d’exploration de données vélo Buyer | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a73ac60b-660f-458a-bd2f-993fbeba7226
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: d6384910858d87a80aa3c8f897bc88e45f4504fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703539"
---
# <a name="lesson-1-creating-the-bike-buyer-mining-structure"></a><span data-ttu-id="451d3-102">Leçon 1 : Création de la structure d’exploration de données Bike Buyer</span><span class="sxs-lookup"><span data-stu-id="451d3-102">Lesson 1: Creating the Bike Buyer Mining Structure</span></span>
  <span data-ttu-id="451d3-103">Dans cette leçon, vous allez créer une structure d'exploration de données à l'aide de laquelle vous pouvez prévoir si un acheteur potentiel de [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] est intéressé par l'achat d'un vélo.</span><span class="sxs-lookup"><span data-stu-id="451d3-103">In this lesson, you will create a mining structure that allows you to predict whether a potential customer of [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] will purchase a bicycle.</span></span> <span data-ttu-id="451d3-104">Si vous n’êtes pas familiarisé avec les structures d’exploration de données et leur rôle dans l’exploration de données, consultez structures d’exploration de données [&#40;Analysis Services-exploration de données&#41;](../../2014/analysis-services/data-mining/mining-structures-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="451d3-104">If you are unfamiliar with mining structures and their role in data mining, see [Mining Structures &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/mining-structures-analysis-services-data-mining.md).</span></span>  
  
 <span data-ttu-id="451d3-105">La structure d’exploration de données Bike Buyer que vous allez créer dans cette leçon prend en charge l’ajout de modèles d’exploration de données basés sur l’algorithme [Microsoft Clustering](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md)d’algorithmes[Microsoft Decision Trees](../../2014/analysis-services/data-mining/microsoft-decision-trees-algorithm.md).</span><span class="sxs-lookup"><span data-stu-id="451d3-105">The Bike Buyer mining structure that you will create in this lesson supports adding mining models based on the [Microsoft Clustering Algorithm](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md)[Microsoft Decision Trees Algorithm](../../2014/analysis-services/data-mining/microsoft-decision-trees-algorithm.md).</span></span> <span data-ttu-id="451d3-106">Au cours d'autres leçons, vous utiliserez les modèles d'exploration de données clustering pour examiner différentes méthodes de regroupement des clients et exploiterez les modèles d'exploration de données d'arbre de décision pour déterminer si un client potentiel est susceptible d'acheter un vélo.</span><span class="sxs-lookup"><span data-stu-id="451d3-106">In later lessons, you will use the clustering mining models to explore the different ways in which customers can be grouped, and will use decision tree mining models to predict whether or not a potential customer will purchase a bicycle.</span></span>  
  
## <a name="create-mining-structure-statement"></a><span data-ttu-id="451d3-107">Instruction CREATE MINING STRUCTURE</span><span class="sxs-lookup"><span data-stu-id="451d3-107">CREATE MINING STRUCTURE Statement</span></span>  
 <span data-ttu-id="451d3-108">Pour créer une structure d’exploration de données, vous utilisez l’instruction [Create Mining structure &#40;DMX&#41;](/sql/dmx/create-mining-structure-dmx) .</span><span class="sxs-lookup"><span data-stu-id="451d3-108">To create a mining structure, you use the [CREATE MINING STRUCTURE &#40;DMX&#41;](/sql/dmx/create-mining-structure-dmx) statement.</span></span> <span data-ttu-id="451d3-109">Le code de l’instruction peut être divisé en plusieurs parties :</span><span class="sxs-lookup"><span data-stu-id="451d3-109">The code in the statement can be broken into the following parts:</span></span>  
  
-   <span data-ttu-id="451d3-110">Attribution d'un nom à la structure.</span><span class="sxs-lookup"><span data-stu-id="451d3-110">Naming the structure.</span></span>  
  
-   <span data-ttu-id="451d3-111">Définition de la colonne clé.</span><span class="sxs-lookup"><span data-stu-id="451d3-111">Defining the key column.</span></span>  
  
-   <span data-ttu-id="451d3-112">Définition des colonnes d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="451d3-112">Defining the mining columns.</span></span>  
  
-   <span data-ttu-id="451d3-113">Définition d'un jeu de données de test facultatif.</span><span class="sxs-lookup"><span data-stu-id="451d3-113">Defining an optional testing data set.</span></span>  
  
 <span data-ttu-id="451d3-114">L'exemple générique suivant utilise l'instruction CREATE MINING STRUCTURE :</span><span class="sxs-lookup"><span data-stu-id="451d3-114">The following is a generic example of the CREATE MINING STRUCTURE statement:</span></span>  
  
```  
CREATE MINING STRUCTURE [<mining structure name>]  
(  
    <key column>,  
    <mining structure columns>  
)   
WITH HOLDOUT (<holdout specifier>)  
```  
  
 <span data-ttu-id="451d3-115">La première ligne du code définit le nom de la structure :</span><span class="sxs-lookup"><span data-stu-id="451d3-115">The first line of the code defines the name of the structure:</span></span>  
  
```  
CREATE MINING STRUCTURE [<mining structure name>]  
```  
  
 <span data-ttu-id="451d3-116">Pour plus d’informations sur l’attribution d’un nom à un objet dans les extensions DMX (Data Mining Extensions), consultez [identificateurs &#40;dmx&#41;](/sql/dmx/identifiers-dmx).</span><span class="sxs-lookup"><span data-stu-id="451d3-116">For information about naming an object in Data Mining Extensions (DMX), see [Identifiers &#40;DMX&#41;](/sql/dmx/identifiers-dmx).</span></span>  
  
 <span data-ttu-id="451d3-117">La ligne suivante du code définit la colonne clé de la structure d'exploration de données qui identifie de manière unique une entité au sein des données source :</span><span class="sxs-lookup"><span data-stu-id="451d3-117">The next line of the code defines the key column for the mining structure, which uniquely identifies an entity in the source data:</span></span>  
  
```  
<key column>,  
```  
  
 <span data-ttu-id="451d3-118">Dans la structure d'exploration de données que vous allez créer, l'identificateur du client, `CustomerKey`, définit une entité dans les données sources.</span><span class="sxs-lookup"><span data-stu-id="451d3-118">In the mining structure you will create, the customer identifier, `CustomerKey`, defines an entity in the source data.</span></span>  
  
 <span data-ttu-id="451d3-119">La ligne suivante du code permet de définir les colonnes d'exploration de données qu'utilisent les modèles d'exploration de données associés à la structure d'exploration de données :</span><span class="sxs-lookup"><span data-stu-id="451d3-119">The next line of the code is used to define the mining columns that will be used by the mining models associated with the mining structure:</span></span>  
  
```  
<mining structure columns>  
```  
  
 <span data-ttu-id="451d3-120">Vous pouvez utiliser la fonction discrétisation dans \<mining structure columns> pour discrétisationr des colonnes continues à l’aide de la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="451d3-120">You can use the DISCRETIZE function within \<mining structure columns> to discretize continuous columns by using the following syntax:</span></span>  
  
 `DISCRETIZE(<method>,<number of buckets>)`  
  
 <span data-ttu-id="451d3-121">Pour plus d’informations sur la discrétisation des colonnes, consultez [méthodes de discrétisation &#40;&#41;d’exploration de données ](../../2014/analysis-services/data-mining/discretization-methods-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="451d3-121">For more information about discretizing columns, see [Discretization Methods &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/discretization-methods-data-mining.md).</span></span> <span data-ttu-id="451d3-122">Pour plus d’informations sur les types de colonnes de structure d’exploration de données que vous pouvez définir, consultez [colonnes de structure d’exploration](../../2014/analysis-services/data-mining/mining-structure-columns.md)de données.</span><span class="sxs-lookup"><span data-stu-id="451d3-122">For more information about the types of mining structure columns that you can define, see [Mining Structure Columns](../../2014/analysis-services/data-mining/mining-structure-columns.md).</span></span>  
  
 <span data-ttu-id="451d3-123">La dernière ligne du code définit une partition facultative dans la structure d'exploration de données :</span><span class="sxs-lookup"><span data-stu-id="451d3-123">The final line of the code defines an optional partition in the mining structure:</span></span>  
  
```  
WITH HOLDOUT (<holdout specifier>)  
```  
  
 <span data-ttu-id="451d3-124">Vous spécifiez une partie des données à utiliser pour tester des modèles d'exploration de données associés à la structure, puis les données restantes sont utilisées pour l'apprentissage des modèles.</span><span class="sxs-lookup"><span data-stu-id="451d3-124">You specify some portion of the data to use for testing mining models that are related to the structure, and the remaining data is used for training the models.</span></span> <span data-ttu-id="451d3-125">Par défaut, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] crée un jeu de données de test qui contient 30 pour cent de toutes les données de cas.</span><span class="sxs-lookup"><span data-stu-id="451d3-125">By default, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] creates a test data set that contains 30 percent of all case data.</span></span> <span data-ttu-id="451d3-126">Vous ajoutez ensuite la spécification selon laquelle le jeu de données de test doit contenir 30 pour cent des cas jusqu'à un maximum de 1000 cas.</span><span class="sxs-lookup"><span data-stu-id="451d3-126">You will add the specification that the test data set should contain 30 percent of the cases up to a maximum of 1000 cases.</span></span> <span data-ttu-id="451d3-127">Si 30 pour cent des cas représente moins de 1000, le jeu de données de test contient alors la plus petite quantité.</span><span class="sxs-lookup"><span data-stu-id="451d3-127">If 30 percent of the cases is less than 1000, the test data set will contain the smaller amount.</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="451d3-128">Tâches de la leçon</span><span class="sxs-lookup"><span data-stu-id="451d3-128">Lesson Tasks</span></span>  
 <span data-ttu-id="451d3-129">Dans cette leçon, vous allez effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="451d3-129">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="451d3-130">créer une nouvelle requête vide ;</span><span class="sxs-lookup"><span data-stu-id="451d3-130">Create a new blank query.</span></span>  
  
-   <span data-ttu-id="451d3-131">Modifiez la requête pour créer la structure d’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="451d3-131">Alter the query to create the mining structure.</span></span>  
  
-   <span data-ttu-id="451d3-132">exécutez la requête.</span><span class="sxs-lookup"><span data-stu-id="451d3-132">Execute the query.</span></span>  
  
## <a name="creating-the-query"></a><span data-ttu-id="451d3-133">Création de la requête</span><span class="sxs-lookup"><span data-stu-id="451d3-133">Creating the Query</span></span>  
 <span data-ttu-id="451d3-134">La première étape consiste à se connecter à une instance de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] et à créer une nouvelle requête DMX dans [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="451d3-134">The first step is to connect to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] and create a new DMX query in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
#### <a name="to-create-a-new-dmx-query-in-sql-server-management-studio"></a><span data-ttu-id="451d3-135">Pour créer une requête DMX dans SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="451d3-135">To create a new DMX query in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="451d3-136">Ouvrez [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="451d3-136">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="451d3-137">Dans la boîte de dialogue **se connecter au serveur** , pour **type de serveur**, sélectionnez **Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="451d3-137">In the **Connect to Server** dialog box, for **Server type**, select **Analysis Services**.</span></span> <span data-ttu-id="451d3-138">Dans **nom du serveur**, tapez `LocalHost` ou tapez le nom de l’instance de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] à laquelle vous souhaitez vous connecter pour cette leçon.</span><span class="sxs-lookup"><span data-stu-id="451d3-138">In **Server name**, type `LocalHost`, or type the name of the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] that you want to connect to for this lesson.</span></span> <span data-ttu-id="451d3-139">Cliquez sur **Connecter**.</span><span class="sxs-lookup"><span data-stu-id="451d3-139">Click **Connect**.</span></span>  
  
3.  <span data-ttu-id="451d3-140">Dans l' **Explorateur d’objets**, cliquez avec le bouton droit sur l’instance de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , pointez sur **nouvelle requête**, puis cliquez sur **DMX** pour ouvrir l' **éditeur de requête** et une nouvelle requête vide.</span><span class="sxs-lookup"><span data-stu-id="451d3-140">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX** to open the **Query Editor** and a new, blank query.</span></span>  
  
## <a name="altering-the-query"></a><span data-ttu-id="451d3-141">Modification de la requête</span><span class="sxs-lookup"><span data-stu-id="451d3-141">Altering the Query</span></span>  
 <span data-ttu-id="451d3-142">L'étape suivante implique de modifier l'instruction CREATE MINING STRUCTURE décrite ci-avant en vue de créer la structure d'exploration de données Bike Buyer.</span><span class="sxs-lookup"><span data-stu-id="451d3-142">The next step is to modify the CREATE MINING STRUCTURE statement described above to create the Bike Buyer mining structure.</span></span>  
  
#### <a name="to-customize-the-create-mining-structure-statement"></a><span data-ttu-id="451d3-143">Pour personnaliser l'instruction CREATE MINING STRUCTURE</span><span class="sxs-lookup"><span data-stu-id="451d3-143">To customize the CREATE MINING STRUCTURE statement</span></span>  
  
1.  <span data-ttu-id="451d3-144">Dans l'Éditeur de requête, copiez l'exemple générique de l'instruction CREATE MINING STRUCTURE dans la requête vide.</span><span class="sxs-lookup"><span data-stu-id="451d3-144">In the Query Editor, copy the generic example of the CREATE MINING STRUCTURE statement into the blank query.</span></span>  
  
2.  <span data-ttu-id="451d3-145">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="451d3-145">Replace the following:</span></span>  
  
    ```  
    [<mining structure>]   
    ```  
  
     <span data-ttu-id="451d3-146">par :</span><span class="sxs-lookup"><span data-stu-id="451d3-146">with:</span></span>  
  
    ```  
    [Bike Buyer]  
    ```  
  
3.  <span data-ttu-id="451d3-147">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="451d3-147">Replace the following:</span></span>  
  
    ```  
    <key column>   
    ```  
  
     <span data-ttu-id="451d3-148">par :</span><span class="sxs-lookup"><span data-stu-id="451d3-148">with:</span></span>  
  
    ```  
    CustomerKey LONG KEY  
    ```  
  
4.  <span data-ttu-id="451d3-149">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="451d3-149">Replace the following:</span></span>  
  
    ```  
    <mining structure columns>   
    ```  
  
     <span data-ttu-id="451d3-150">par :</span><span class="sxs-lookup"><span data-stu-id="451d3-150">with:</span></span>  
  
    ```  
    [Age] LONG DISCRETIZED(Automatic,10),  
    [Bike Buyer] LONG DISCRETE,  
    [Commute Distance] TEXT DISCRETE,  
    [Education] TEXT DISCRETE,  
    [Gender] TEXT DISCRETE,  
    [House Owner Flag] TEXT DISCRETE,  
    [Marital Status] TEXT DISCRETE,  
    [Number Cars Owned] LONG DISCRETE,  
    [Number Children At Home] LONG DISCRETE,  
    [Occupation] TEXT DISCRETE,  
    [Region] TEXT DISCRETE,  
    [Total Children]LONG DISCRETE,  
    [Yearly Income] DOUBLE CONTINUOUS  
    ```  
  
5.  <span data-ttu-id="451d3-151">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="451d3-151">Replace the following:</span></span>  
  
    ```  
    WITH HOLDOUT (holdout specifier>)  
    ```  
  
     <span data-ttu-id="451d3-152">par :</span><span class="sxs-lookup"><span data-stu-id="451d3-152">with:</span></span>  
  
    ```  
    WITH HOLDOUT (30 PERCENT or 1000 CASES)  
    ```  
  
     <span data-ttu-id="451d3-153">L'instruction complète de la structure d'exploration de données doit se présenter comme suit :</span><span class="sxs-lookup"><span data-stu-id="451d3-153">The complete mining structure statement should now be as follows:</span></span>  
  
    ```  
    CREATE MINING STRUCTURE [Bike Buyer]  
    (  
       [Customer Key] LONG KEY,  
       [Age]LONG DISCRETIZED(Automatic,10),  
       [Bike Buyer] LONG DISCRETE,  
       [Commute Distance] TEXT DISCRETE,  
       [Education] TEXT DISCRETE,  
       [Gender] TEXT DISCRETE,  
       [House Owner Flag] TEXT DISCRETE,  
       [Marital Status] TEXT DISCRETE,  
       [Number Cars Owned]LONG DISCRETE,  
       [Number Children At Home]LONG DISCRETE,  
       [Occupation] TEXT DISCRETE,  
       [Region] TEXT DISCRETE,  
       [Total Children]LONG DISCRETE,  
       [Yearly Income] DOUBLE CONTINUOUS  
    )  
    WITH HOLDOUT (30 PERCENT or 1000 CASES)  
  
    ```  
  
6.  <span data-ttu-id="451d3-154">Dans le menu **fichier** , cliquez sur **Enregistrer DMXQuery1. DMX sous**.</span><span class="sxs-lookup"><span data-stu-id="451d3-154">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
7.  <span data-ttu-id="451d3-155">Dans la boîte de dialogue **Enregistrer sous** , accédez au dossier approprié et nommez le fichier `Bike Buyer Structure.dmx` .</span><span class="sxs-lookup"><span data-stu-id="451d3-155">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Bike Buyer Structure.dmx`.</span></span>  
  
## <a name="executing-the-query"></a><span data-ttu-id="451d3-156">Exécution de la requête</span><span class="sxs-lookup"><span data-stu-id="451d3-156">Executing the Query</span></span>  
 <span data-ttu-id="451d3-157">La dernière étape concerne l'exécution de la requête.</span><span class="sxs-lookup"><span data-stu-id="451d3-157">The final step is to execute the query.</span></span> <span data-ttu-id="451d3-158">Après avoir créé et enregistrée une requête, elle doit être exécutée.</span><span class="sxs-lookup"><span data-stu-id="451d3-158">After a query is created and saved, it needs to be executed.</span></span> <span data-ttu-id="451d3-159">Autrement dit, l'instruction doit être exécutée pour créer la structure d'exploration de données sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="451d3-159">That is, the statement needs to be run in order to create the mining structure on the server.</span></span> <span data-ttu-id="451d3-160">Pour plus d’informations sur l’exécution de requêtes dans l’éditeur de requête, consultez [moteur de base de données l’éditeur de requête &#40;SQL Server Management Studio&#41;](../relational-databases/scripting/database-engine-query-editor-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="451d3-160">For more information about executing queries in Query Editor, see [Database Engine Query Editor &#40;SQL Server Management Studio&#41;](../relational-databases/scripting/database-engine-query-editor-sql-server-management-studio.md).</span></span>  
  
#### <a name="to-execute-the-query"></a><span data-ttu-id="451d3-161">Pour exécuter la requête</span><span class="sxs-lookup"><span data-stu-id="451d3-161">To execute the query</span></span>  
  
1.  <span data-ttu-id="451d3-162">Dans l’éditeur de requête, dans la barre d’outils, cliquez sur **exécuter**.</span><span class="sxs-lookup"><span data-stu-id="451d3-162">In Query Editor, on the toolbar, click **Execute**.</span></span>  
  
     <span data-ttu-id="451d3-163">L’état de la requête s’affiche dans l’onglet **messages** en bas de l’éditeur de requête à la fin de l’exécution de l’instruction.</span><span class="sxs-lookup"><span data-stu-id="451d3-163">The status of the query is displayed in the **Messages** tab at the bottom of Query Editor after the statement finishes executing.</span></span> <span data-ttu-id="451d3-164">Les messages doivent révéler le texte suivant :</span><span class="sxs-lookup"><span data-stu-id="451d3-164">Messages should display:</span></span>  
  
    ```  
    Executing the query   
    Execution complete  
    ```  
  
     <span data-ttu-id="451d3-165">Une nouvelle structure nommée **vélo Buyer** existe désormais sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="451d3-165">A new structure named **Bike Buyer** now exists on the server.</span></span>  
  
 <span data-ttu-id="451d3-166">Dans la leçon suivante, vous allez ajouter des modèles d'exploration de données à la structure que vous venez de créer.</span><span class="sxs-lookup"><span data-stu-id="451d3-166">In the next lesson, you will add mining models to the structure you just created.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="451d3-167">Leçon suivante</span><span class="sxs-lookup"><span data-stu-id="451d3-167">Next Lesson</span></span>  
 [<span data-ttu-id="451d3-168">Leçon 2 : Ajout de modèles d’exploration de données à la structure d’exploration de données Bike Buyer</span><span class="sxs-lookup"><span data-stu-id="451d3-168">Lesson 2: Adding Mining Models to the Bike Buyer Mining Structure</span></span>](../../2014/tutorials/lesson-2-adding-mining-models-to-the-bike-buyer-mining-structure.md)  
  
  
