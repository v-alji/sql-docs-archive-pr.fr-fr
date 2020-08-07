---
title: 'Leçon 3 : traitement de la structure d’exploration de données vélo Buyer | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: e748c2cd-339d-4e82-82f1-be2d0fc41b61
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 2e3f85016b32884b9a6b809e28d20d9985f97cd9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703527"
---
# <a name="lesson-3-processing-the-bike-buyer-mining-structure"></a><span data-ttu-id="13218-102">Leçon 3 : Traitement de la structure d’exploration de données Bike Buyer</span><span class="sxs-lookup"><span data-stu-id="13218-102">Lesson 3: Processing the Bike Buyer Mining Structure</span></span>
  <span data-ttu-id="13218-103">Dans cette leçon, vous allez utiliser l’instruction INSERT INTO et la vue vTargetMail de l' [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] exemple de base de données pour traiter les structures et les modèles d’exploration de données que vous avez créés au cours de la [leçon 1 : création de la structure d’exploration de données Bike Buyer](../../2014/tutorials/lesson-1-creating-the-bike-buyer-mining-structure.md) et [leçon 2 : ajout de modèles d’exploration de données à la structure d’exploration de données Bike Buyer](../../2014/tutorials/lesson-2-adding-mining-models-to-the-bike-buyer-mining-structure.md).</span><span class="sxs-lookup"><span data-stu-id="13218-103">In this lesson, you will use the INSERT INTO statement and the vTargetMail view from the [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] sample database to process the mining structures and mining models that you created in [Lesson 1: Creating the Bike Buyer Mining Structure](../../2014/tutorials/lesson-1-creating-the-bike-buyer-mining-structure.md) and [Lesson 2: Adding Mining Models to the Bike Buyer Mining Structure](../../2014/tutorials/lesson-2-adding-mining-models-to-the-bike-buyer-mining-structure.md).</span></span>  
  
 <span data-ttu-id="13218-104">Lorsque vous traitez une structure d'exploration de données, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] lit les données sources et génère les structures qui soutiennent les modèles d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="13218-104">When you process a mining structure, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] reads the source data and builds the structures that support mining models.</span></span> <span data-ttu-id="13218-105">Lorsque vous traitez un modèle d'exploration de données, les données définies par la structure sont transmises via l'algorithme d'exploration de données de votre choix.</span><span class="sxs-lookup"><span data-stu-id="13218-105">When you process a mining model, the data defined by the mining structure is passed through the data mining algorithm that you choose.</span></span> <span data-ttu-id="13218-106">L'algorithme recherche des tendances et des modèles, puis stocke les informations recueillies dans le modèle d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="13218-106">The algorithm searches for trends and patterns, and then stores this information in the mining model.</span></span> <span data-ttu-id="13218-107">Par conséquent, le modèle d'exploration de données ne contient pas les données source réelles mais plutôt les informations recueillies par l'algorithme.</span><span class="sxs-lookup"><span data-stu-id="13218-107">The mining model, therefore, does not contain the actual source data, but instead contains the information that was discovered by the algorithm.</span></span> <span data-ttu-id="13218-108">Pour plus d’informations sur le traitement des modèles d’exploration de données, consultez [exigences et considérations relatives au traitement &#40;&#41;d’exploration de données ](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="13218-108">For more information about processing mining models, see [Processing Requirements and Considerations &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md).</span></span>  
  
 <span data-ttu-id="13218-109">Si vous modifiez une colonne de structure ou les données sources, vous devez simplement retraiter la structure d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="13218-109">You need to reprocess a mining structure only if you change a structure column or change the source data.</span></span> <span data-ttu-id="13218-110">Si vous ajoutez un modèle d'exploration de données à une structure d'exploration de données déjà traitée, vous pouvez utiliser l'instruction INSERT INTO MINING MODEL pour effectuer l'apprentissage du nouveau modèle d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="13218-110">If you add a mining model to a mining structure that has already been processed, you can use the INSERT INTO MINING MODEL statement to train the new mining model.</span></span>  
  
## <a name="train-structure-template"></a><span data-ttu-id="13218-111">Modèle de structure d'apprentissage</span><span class="sxs-lookup"><span data-stu-id="13218-111">Train Structure Template</span></span>  
 <span data-ttu-id="13218-112">Pour effectuer l’apprentissage de la structure d’exploration de données et de ses modèles d’exploration de données associés, utilisez l’instruction [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx) .</span><span class="sxs-lookup"><span data-stu-id="13218-112">In order to train the mining structure and its associated mining models, use the [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx) statement.</span></span> <span data-ttu-id="13218-113">Le code de l’instruction peut être divisé en plusieurs parties :</span><span class="sxs-lookup"><span data-stu-id="13218-113">The code in the statement can be broken into the following parts:</span></span>  
  
-   <span data-ttu-id="13218-114">Identification de la structure d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="13218-114">Identifying the mining structure</span></span>  
  
-   <span data-ttu-id="13218-115">Liste des colonnes de la structure d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="13218-115">Listing the columns in the mining structure</span></span>  
  
-   <span data-ttu-id="13218-116">Définition des données d'apprentissage</span><span class="sxs-lookup"><span data-stu-id="13218-116">Defining the training data</span></span>  
  
 <span data-ttu-id="13218-117">L'exemple générique suivant utilise l'instruction INSERT INTO :</span><span class="sxs-lookup"><span data-stu-id="13218-117">The following is a generic example of the INSERT INTO statement:</span></span>  
  
```  
INSERT INTO MINING STRUCTURE [<mining structure name>]  
(  
   <mining structure columns>  
)  
OPENQUERY([<datasource>],'<SELECT statement>')  
```  
  
 <span data-ttu-id="13218-118">La première ligne du code identifie la structure d'exploration de données à apprendre :</span><span class="sxs-lookup"><span data-stu-id="13218-118">The first line of the code identifies the mining structure that you will train:</span></span>  
  
```  
INSERT INTO MINING STRUCTURE [<mining structure name>]  
```  
  
 <span data-ttu-id="13218-119">La ligne suivante du code précise les colonnes définies par la structure d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="13218-119">The next line of the code specifies the columns that are defined by the mining structure.</span></span> <span data-ttu-id="13218-120">Vous devez répertorier chaque colonne dans la structure d'exploration de données et chaque colonne doit mapper une colonne figurant dans les données de la requête source.</span><span class="sxs-lookup"><span data-stu-id="13218-120">You must list each column in the mining structure, and each column must map to a column contained within the source query data.</span></span>  
  
```  
(  
   <mining structure columns>  
)  
```  
  
 <span data-ttu-id="13218-121">La dernière ligne du code précise les données à utiliser pour l'apprentissage de la structure d'exploration de données :</span><span class="sxs-lookup"><span data-stu-id="13218-121">The final line of the code defines the data that will be used to train the mining structure:</span></span>  
  
```  
OPENQUERY([<datasource>],'<SELECT statement>')  
```  
  
 <span data-ttu-id="13218-122">Dans cette leçon, vous allez utiliser l'instruction `OPENQUERY` pour définir les données sources.</span><span class="sxs-lookup"><span data-stu-id="13218-122">In this lesson, you use `OPENQUERY` to define the source data.</span></span> <span data-ttu-id="13218-123">Pour plus d’informations sur les autres méthodes de définition de la requête source, consultez [&#60;&#62;de requête de données source ](/sql/dmx/source-data-query).</span><span class="sxs-lookup"><span data-stu-id="13218-123">For information about other methods of defining the source query, see [&#60;source data query&#62;](/sql/dmx/source-data-query).</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="13218-124">Tâches de la leçon</span><span class="sxs-lookup"><span data-stu-id="13218-124">Lesson Tasks</span></span>  
 <span data-ttu-id="13218-125">Au cours de cette leçon, vous allez effectuer la tâche suivante :</span><span class="sxs-lookup"><span data-stu-id="13218-125">You will perform the following task in this lesson:</span></span>  
  
-   <span data-ttu-id="13218-126">traiter la structure d'exploration de données Bike Buyer.</span><span class="sxs-lookup"><span data-stu-id="13218-126">Process the Bike Buyer mining structure</span></span>  
  
## <a name="processing-the-predictive-mining-structure"></a><span data-ttu-id="13218-127">Traitement de la structure d'exploration de données prédictive</span><span class="sxs-lookup"><span data-stu-id="13218-127">Processing the Predictive Mining Structure</span></span>  
  
#### <a name="to-process-the-mining-structure-by-using-insert-into"></a><span data-ttu-id="13218-128">Pour traiter la structure d'exploration de données à l'aide de l'instruction INSERT INTO</span><span class="sxs-lookup"><span data-stu-id="13218-128">To process the mining structure by using INSERT INTO</span></span>  
  
1.  <span data-ttu-id="13218-129">Dans l' **Explorateur d’objets**, cliquez avec le bouton droit sur l’instance de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , pointez sur **nouvelle requête**, puis cliquez sur **DMX**.</span><span class="sxs-lookup"><span data-stu-id="13218-129">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="13218-130">L'Éditeur de requête s'ouvre et contient une nouvelle requête vide.</span><span class="sxs-lookup"><span data-stu-id="13218-130">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="13218-131">Copiez l'exemple générique de l'instruction INSERT INTO dans la requête vide.</span><span class="sxs-lookup"><span data-stu-id="13218-131">Copy the generic example of the INSERT INTO statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="13218-132">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="13218-132">Replace the following:</span></span>  
  
    ```  
    [<mining structure name>]   
    ```  
  
     <span data-ttu-id="13218-133">par :</span><span class="sxs-lookup"><span data-stu-id="13218-133">with:</span></span>  
  
    ```  
    Bike Buyer  
    ```  
  
4.  <span data-ttu-id="13218-134">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="13218-134">Replace the following:</span></span>  
  
    ```  
    <mining structure columns>  
    ```  
  
     <span data-ttu-id="13218-135">par :</span><span class="sxs-lookup"><span data-stu-id="13218-135">with:</span></span>  
  
    ```  
    [Customer Key],  
    [Age],  
    [Bike Buyer],  
    [Commute Distance],  
    [Education],  
    [Gender],  
    [House Owner Flag],  
    [Marital Status],  
    [Number Cars Owned],  
    [Number Children At Home],  
    [Occupation],  
    [Region],  
    [Total Children],  
    [Yearly Income]  
    ```  
  
5.  <span data-ttu-id="13218-136">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="13218-136">Replace the following:</span></span>  
  
    ```  
    OPENQUERY([<datasource>],'<SELECT statement>')  
    ```  
  
     <span data-ttu-id="13218-137">par :</span><span class="sxs-lookup"><span data-stu-id="13218-137">with:</span></span>  
  
    ```  
    OPENQUERY([Adventure Works DW],  
       'SELECT CustomerKey, Age, BikeBuyer,  
             CommuteDistance,EnglishEducation,  
             Gender,HouseOwnerFlag,MaritalStatus,  
             NumberCarsOwned,NumberChildrenAtHome,   
             EnglishOccupation,Region,TotalChildren,  
             YearlyIncome   
        FROM dbo.vTargetMail')  
    ```  
  
     <span data-ttu-id="13218-138">L'instruction OPENQUERY référence la source de données [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] pour accéder à la vue vTargetMail.</span><span class="sxs-lookup"><span data-stu-id="13218-138">The OPENQUERY statement references the [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] data source to access the view vTargetMail.</span></span> <span data-ttu-id="13218-139">Cette vue contient les données sources à utiliser pour l'apprentissage des modèles d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="13218-139">The view contains the source data that will be used to train the mining models.</span></span>  
  
     <span data-ttu-id="13218-140">L'instruction tout entière doit se présenter comme suit :</span><span class="sxs-lookup"><span data-stu-id="13218-140">The complete statement should now be as follows:</span></span>  
  
    ```  
    INSERT INTO MINING STRUCTURE [Bike Buyer]  
    (  
       [Customer Key],  
       [Age],  
       [Bike Buyer],  
       [Commute Distance],  
       [Education],  
       [Gender],  
       [House Owner Flag],  
       [Marital Status],  
       [Number Cars Owned],  
       [Number Children At Home],  
       [Occupation],  
       [Region],  
       [Total Children],  
       [Yearly Income]     
    )  
    OPENQUERY([Adventure Works DW],  
       'SELECT CustomerKey, Age, BikeBuyer,  
             CommuteDistance,EnglishEducation,  
             Gender,HouseOwnerFlag,MaritalStatus,  
             NumberCarsOwned,NumberChildrenAtHome,   
             EnglishOccupation,Region,TotalChildren,  
             YearlyIncome   
        FROM dbo.vTargetMail')  
    ```  
  
6.  <span data-ttu-id="13218-141">Dans le menu **fichier** , cliquez sur **Enregistrer DMXQuery1. DMX sous**.</span><span class="sxs-lookup"><span data-stu-id="13218-141">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
7.  <span data-ttu-id="13218-142">Dans la boîte de dialogue **Enregistrer sous** , accédez au dossier approprié et nommez le fichier `Process Bike Buyer Structure.dmx` .</span><span class="sxs-lookup"><span data-stu-id="13218-142">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Process Bike Buyer Structure.dmx`.</span></span>  
  
8.  <span data-ttu-id="13218-143">Dans la barre d’outils, cliquez sur le bouton **exécuter** .</span><span class="sxs-lookup"><span data-stu-id="13218-143">On the toolbar, click the **Execute** button.</span></span>  
  
 <span data-ttu-id="13218-144">Dans la leçon suivante, vous allez explorer le contenu des modèles d'exploration de données que vous avez ajoutés à la structure d'exploration de données au cours de cette leçon.</span><span class="sxs-lookup"><span data-stu-id="13218-144">In the next lesson, you will explore content in the mining models you added to the mining structure in this lesson.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="13218-145">Leçon suivante</span><span class="sxs-lookup"><span data-stu-id="13218-145">Next Lesson</span></span>  
 [<span data-ttu-id="13218-146">Leçon 4 : Exploration des modèles d’exploration de données Bike Buyer</span><span class="sxs-lookup"><span data-stu-id="13218-146">Lesson 4: Browsing the Bike Buyer Mining Models</span></span>](../../2014/tutorials/lesson-4-browsing-the-bike-buyer-mining-models.md)  
  
  
