---
title: 'Leçon 4 : exploration des modèles d’exploration de données Bike Buyer | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 8de3c500-f881-42da-a096-b6c03300d58d
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 709df371d840d4b24e420b4fcd08750fd31e8075
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604329"
---
# <a name="lesson-4-browsing-the-bike-buyer-mining-models"></a><span data-ttu-id="b6511-102">Leçon 4 : Exploration des modèles d’exploration de données Bike Buyer</span><span class="sxs-lookup"><span data-stu-id="b6511-102">Lesson 4: Browsing the Bike Buyer Mining Models</span></span>
  <span data-ttu-id="b6511-103">Dans cette leçon, vous allez utiliser l’instruction [Select (DMX)](/sql/dmx/select-dmx) pour explorer le contenu des modèles d’exploration de données d’arbre de décision et de clustering que vous avez créés au cours de la [leçon 2 : ajout de modèles d’exploration de données à la structure d’exploration de données prédictive](../../2014/tutorials/lesson-2-adding-mining-models-to-the-bike-buyer-mining-structure.md).</span><span class="sxs-lookup"><span data-stu-id="b6511-103">In this lesson, you will use the [SELECT (DMX)](/sql/dmx/select-dmx) statement to explore the content in the decision tree and clustering mining models that you created in [Lesson 2: Adding Mining Models to the Predictive Mining Structure](../../2014/tutorials/lesson-2-adding-mining-models-to-the-bike-buyer-mining-structure.md).</span></span>  
  
 <span data-ttu-id="b6511-104">Les colonnes figurant dans un modèle d'exploration de données ne sont pas les colonnes définies par la structure d'exploration de données ; elles forment plutôt un ensemble spécifique de colonnes décrivant des tendances et des modèles identifiés par l'algorithme.</span><span class="sxs-lookup"><span data-stu-id="b6511-104">The columns contained in a mining model are not the columns defined by the mining structure, but instead are a specific set of columns that describe the trends and patterns that are found by the algorithm.</span></span> <span data-ttu-id="b6511-105">Ces colonnes de modèle d’exploration de données sont décrites dans l’ensemble de lignes de schéma d' [ensemble de lignes DMSCHEMA_MINING_MODEL_CONTENT](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-model-content-rowset) .</span><span class="sxs-lookup"><span data-stu-id="b6511-105">These mining model columns are described in the [DMSCHEMA_MINING_MODEL_CONTENT Rowset](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-model-content-rowset) schema rowset.</span></span> <span data-ttu-id="b6511-106">Par exemple, la colonne MODEL_NAME située dans l'ensemble de lignes du schéma contient le nom du modèle d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="b6511-106">For example, the MODEL_NAME column in the content schema rowset contains the name of the mining model.</span></span> <span data-ttu-id="b6511-107">Dans le cadre d'un modèle d'exploration de données clustering, la colonne NODE_CAPTION renferme le nom de chaque cluster et la colonne NODE_DESCRIPTION contient une description des caractéristiques de chacun de ces clusters.</span><span class="sxs-lookup"><span data-stu-id="b6511-107">For a clustering mining model, the NODE_CAPTION column contains the name of each cluster, and the NODE_DESCRIPTION column contains a description of the characteristics of each cluster.</span></span> <span data-ttu-id="b6511-108">Vous pouvez parcourir ces colonnes à l’aide de l’option SELECT FROM \<model> . Instruction CONTENT dans DMX.</span><span class="sxs-lookup"><span data-stu-id="b6511-108">You can browse these columns by using the SELECT FROM \<model>.CONTENT statement in DMX.</span></span> <span data-ttu-id="b6511-109">Le recours à cette instruction est également possible si vous souhaitez explorer les données utilisées pour la création du modèle d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="b6511-109">You can also use this statement to explore the data that was used to create the mining model.</span></span> <span data-ttu-id="b6511-110">Pour utiliser cette instruction, vous devez activer la fonction d'extraction dans la structure d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="b6511-110">Drillthrough must be enabled on the mining structure in order to use this statement.</span></span> <span data-ttu-id="b6511-111">Pour plus d’informations sur l’instruction, consultez [SELECT FROM &#60;model&#62;. CAS &#40;&#41;DMX ](/sql/dmx/select-from-model-content-dmx).</span><span class="sxs-lookup"><span data-stu-id="b6511-111">For more information about the statement, see [SELECT FROM &#60;model&#62;.CASES &#40;DMX&#41;](/sql/dmx/select-from-model-content-dmx).</span></span>  
  
 <span data-ttu-id="b6511-112">Vous pouvez également afficher tous les états d'une colonne discrète par le biais de l'instruction SELECT DISTINCT.</span><span class="sxs-lookup"><span data-stu-id="b6511-112">You can also return all the states of a discrete column by using the SELECT DISTINCT statement.</span></span> <span data-ttu-id="b6511-113">Par exemple, si vous effectuez cette opération sur une colonne Sexe, la requête retourne les valeurs `male` et `female`.</span><span class="sxs-lookup"><span data-stu-id="b6511-113">For example, if you perform this operation on a gender column, the query will return `male` and `female`.</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="b6511-114">Tâches de la leçon</span><span class="sxs-lookup"><span data-stu-id="b6511-114">Lesson Tasks</span></span>  
 <span data-ttu-id="b6511-115">Dans cette leçon, vous allez effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="b6511-115">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="b6511-116">explorer le contenu des modèles d'exploration de données ;</span><span class="sxs-lookup"><span data-stu-id="b6511-116">Explore the content contained within the mining models</span></span>  
  
-   <span data-ttu-id="b6511-117">retourner les cas des données source utilisées pour l'apprentissage des modèles d'exploration de données ;</span><span class="sxs-lookup"><span data-stu-id="b6511-117">Return the cases from the source data that was used to train the mining models</span></span>  
  
-   <span data-ttu-id="b6511-118">explorer les différents états disponibles pour une colonne discrète donnée.</span><span class="sxs-lookup"><span data-stu-id="b6511-118">Explore the different states available for a specific discrete column</span></span>  
  
## <a name="returning-the-content-of-a-mining-model"></a><span data-ttu-id="b6511-119">Retour du contenu d'un modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="b6511-119">Returning the Content of a Mining Model</span></span>  
 <span data-ttu-id="b6511-120">Dans cette leçon, vous allez utiliser le [&#62; de modèle SELECT FROM &#60;. Instruction CONTENT &#40;DMX&#41;](/sql/dmx/select-from-model-dimension-content-dmx) pour retourner le contenu du modèle de clustering.</span><span class="sxs-lookup"><span data-stu-id="b6511-120">In this lesson, you use the [SELECT FROM &#60;model&#62;.CONTENT &#40;DMX&#41;](/sql/dmx/select-from-model-dimension-content-dmx) statement to return the contents of the clustering model.</span></span>  
  
 <span data-ttu-id="b6511-121">Voici un exemple générique de l’option SELECT FROM \<model> . Instruction de contenu :</span><span class="sxs-lookup"><span data-stu-id="b6511-121">The following is a generic example of the SELECT FROM \<model>.CONTENT statement:</span></span>  
  
```  
SELECT <select list> FROM [<mining model>].CONTENT  
WHERE <where clause>  
```  
  
 <span data-ttu-id="b6511-122">La première ligne du code définit les colonnes à retourner à partir du contenu du modèle d'exploration de données et le modèle d'exploration de données auquel elles sont associées :</span><span class="sxs-lookup"><span data-stu-id="b6511-122">The first line of the code defines the columns to return from the mining model content, and the mining model they are associated with:</span></span>  
  
```  
SELECT <select list> FROM [<mining model].CONTENT  
```  
  
 <span data-ttu-id="b6511-123">La clause .CONTENT en regard du nom du modèle d'exploration de données précise que le contenu est retourné à partir du modèle d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="b6511-123">The .CONTENT clause next to the name of the mining model specifies that you are returning content from the mining model.</span></span> <span data-ttu-id="b6511-124">Pour plus d’informations sur les colonnes contenues dans le modèle d’exploration de données, consultez [DMSCHEMA_MINING_MODEL_CONTENT rowset](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-model-content-rowset).</span><span class="sxs-lookup"><span data-stu-id="b6511-124">For more information about the columns contained in the mining model, see [DMSCHEMA_MINING_MODEL_CONTENT Rowset](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-model-content-rowset).</span></span>  
  
 <span data-ttu-id="b6511-125">Vous pouvez éventuellement exploiter la dernière ligne du code pour filtrer les résultats retournés par l'instruction :</span><span class="sxs-lookup"><span data-stu-id="b6511-125">You can optionally use the final line of the code to filter the results returned by the statement:</span></span>  
  
```  
WHERE <where clause>  
```  
  
 <span data-ttu-id="b6511-126">Par exemple, si vous souhaitez restreindre les résultats de la requête uniquement aux clusters abritant un grand nombre de cas, vous pouvez ajouter la clause WHERE suivante à l'instruction SELECT :</span><span class="sxs-lookup"><span data-stu-id="b6511-126">For example, if you want to restrict the results of the query to only the clusters that contain a high number of cases, you can add the following WHERE clause to the SELECT statement:</span></span>  
  
```  
WHERE NODE_SUPPORT > 100  
```  
  
 <span data-ttu-id="b6511-127">Pour plus d’informations sur l’utilisation de l’instruction WHERE, consultez [SELECT &#40;DMX&#41;](/sql/dmx/select-dmx).</span><span class="sxs-lookup"><span data-stu-id="b6511-127">For more information about using the WHERE statement, see [SELECT &#40;DMX&#41;](/sql/dmx/select-dmx).</span></span>  
  
#### <a name="to-return-the-content-of-the-clustering-mining-model"></a><span data-ttu-id="b6511-128">Pour retourner le contenu du modèle d'exploration de données clustering</span><span class="sxs-lookup"><span data-stu-id="b6511-128">To return the content of the clustering mining model</span></span>  
  
1.  <span data-ttu-id="b6511-129">Dans l' **Explorateur d’objets**, cliquez avec le bouton droit sur l’instance de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , pointez sur **nouvelle requête**, puis cliquez sur **DMX**.</span><span class="sxs-lookup"><span data-stu-id="b6511-129">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="b6511-130">L'Éditeur de requête s'ouvre et contient une nouvelle requête vide.</span><span class="sxs-lookup"><span data-stu-id="b6511-130">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="b6511-131">Copiez l’exemple générique de SELECT FROM \<model> . Instruction CONTENT dans la requête vide.</span><span class="sxs-lookup"><span data-stu-id="b6511-131">Copy the generic example of the SELECT FROM \<model>.CONTENT statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="b6511-132">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="b6511-132">Replace the following:</span></span>  
  
    ```  
    <select list>   
    ```  
  
     <span data-ttu-id="b6511-133">par :</span><span class="sxs-lookup"><span data-stu-id="b6511-133">with:</span></span>  
  
    ```  
    *  
    ```  
  
     <span data-ttu-id="b6511-134">Vous pouvez également remplacer \* par la liste des colonnes contenues dans l’ensemble de [lignes DMSCHEMA_MINING_MODEL_CONTENT](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-model-content-rowset).</span><span class="sxs-lookup"><span data-stu-id="b6511-134">You can also replace \* with a list of any of the columns contained within the [DMSCHEMA_MINING_MODEL_CONTENT Rowset](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-model-content-rowset).</span></span>  
  
4.  <span data-ttu-id="b6511-135">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="b6511-135">Replace the following:</span></span>  
  
    ```  
    [<mining model>]   
    ```  
  
     <span data-ttu-id="b6511-136">par :</span><span class="sxs-lookup"><span data-stu-id="b6511-136">with:</span></span>  
  
    ```  
    [Clustering]  
    ```  
  
     <span data-ttu-id="b6511-137">L'instruction tout entière doit se présenter comme suit :</span><span class="sxs-lookup"><span data-stu-id="b6511-137">The complete statement should now be as follows:</span></span>  
  
    ```  
    SELECT * FROM [Clustering].CONTENT  
    ```  
  
5.  <span data-ttu-id="b6511-138">Dans le menu **fichier** , cliquez sur **Enregistrer DMXQuery1. DMX sous**.</span><span class="sxs-lookup"><span data-stu-id="b6511-138">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
6.  <span data-ttu-id="b6511-139">Dans la boîte de dialogue **Enregistrer sous** , accédez au dossier approprié et nommez le fichier `SELECT_CONTENT.dmx` .</span><span class="sxs-lookup"><span data-stu-id="b6511-139">In the **Save As** dialog box, browse to the appropriate folder, and name the file `SELECT_CONTENT.dmx`.</span></span>  
  
7.  <span data-ttu-id="b6511-140">Dans la barre d’outils, cliquez sur le bouton **exécuter** .</span><span class="sxs-lookup"><span data-stu-id="b6511-140">On the toolbar, click the **Execute** button.</span></span>  
  
     <span data-ttu-id="b6511-141">La requête retourne le contenu du modèle d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="b6511-141">The query returns the content of the mining model.</span></span>  
  
## <a name="use-drillthrough"></a><span data-ttu-id="b6511-142">Utilisation de la fonction d'extraction</span><span class="sxs-lookup"><span data-stu-id="b6511-142">Use Drillthrough</span></span>  
 <span data-ttu-id="b6511-143">L'étape suivante consiste à utiliser l'instruction d'extraction pour retourner un éventail de cas utilisés pour l'apprentissage du modèle d'exploration de données d'arbre de décision.</span><span class="sxs-lookup"><span data-stu-id="b6511-143">The next step is to use the drillthrough statement to return a sampling of the cases that were used to train the decision tree mining model.</span></span> <span data-ttu-id="b6511-144">Dans cette leçon, vous allez utiliser le [&#62; de modèle SELECT FROM &#60;. CAS &#40;instruction DMX&#41;](/sql/dmx/select-from-model-content-dmx) pour retourner le contenu du modèle d’arbre de décision.</span><span class="sxs-lookup"><span data-stu-id="b6511-144">In this lesson, you use the [SELECT FROM &#60;model&#62;.CASES &#40;DMX&#41;](/sql/dmx/select-from-model-content-dmx) statement to return the contents of the decision tree model.</span></span>  
  
 <span data-ttu-id="b6511-145">Voici un exemple générique de l’option SELECT FROM \<model> . Instruction CASES :</span><span class="sxs-lookup"><span data-stu-id="b6511-145">The following is a generic example of the SELECT FROM \<model>.CASES statement:</span></span>  
  
```  
SELECT <select list>   
FROM [<mining model>].CASES  
WHERE IsInNode('<node id>')  
```  
  
 <span data-ttu-id="b6511-146">La première ligne du code définit les colonnes à retourner depuis les données source et le modèle d'exploration de données qui les contient :</span><span class="sxs-lookup"><span data-stu-id="b6511-146">The first line of the code defines the columns to return from the source data, and the mining model they are contained within:</span></span>  
  
```  
SELECT <select list> FROM [<mining model>].CASES  
```  
  
 <span data-ttu-id="b6511-147">La clause .CASES indique que vous exécutez une requête d'extraction.</span><span class="sxs-lookup"><span data-stu-id="b6511-147">The .CASES clause specifies that you are performing a drillthrough query.</span></span> <span data-ttu-id="b6511-148">Pour recourir à l'extraction, vous devez l'activer au moment de créer le modèle d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="b6511-148">In order to use drillthrough you must enable drillthrough when you create the mining model.</span></span>  
  
 <span data-ttu-id="b6511-149">La dernière ligne de code est facultative et spécifie le nœud du modèle d'exploration de données duquel vous souhaitez obtenir les cas :</span><span class="sxs-lookup"><span data-stu-id="b6511-149">The final line of the code is optional and specifies the node in the mining model that you are requesting cases from:</span></span>  
  
```  
WHERE IsInNode('<node id>')  
```  
  
 <span data-ttu-id="b6511-150">Pour plus d’informations sur l’utilisation de l’instruction WHERE avec IsInNode, consultez [SELECT FROM &#60;model&#62;. CAS &#40;&#41;DMX ](/sql/dmx/select-from-model-content-dmx).</span><span class="sxs-lookup"><span data-stu-id="b6511-150">For more information about using the WHERE statement with IsInNode, see [SELECT FROM &#60;model&#62;.CASES &#40;DMX&#41;](/sql/dmx/select-from-model-content-dmx).</span></span>  
  
#### <a name="to-return-the-cases-that-were-used-to-train-the-mining-model"></a><span data-ttu-id="b6511-151">Pour retourner les cas utilisés pour l'apprentissage du modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="b6511-151">To return the cases that were used to train the mining model</span></span>  
  
1.  <span data-ttu-id="b6511-152">Dans l' **Explorateur d’objets**, cliquez avec le bouton droit sur l’instance de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , pointez sur **nouvelle requête**, puis cliquez sur **DMX**.</span><span class="sxs-lookup"><span data-stu-id="b6511-152">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="b6511-153">L'Éditeur de requête s'ouvre et contient une nouvelle requête vide.</span><span class="sxs-lookup"><span data-stu-id="b6511-153">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="b6511-154">Copiez l’exemple générique de SELECT FROM \<model> . Instruction CASES dans la requête vide.</span><span class="sxs-lookup"><span data-stu-id="b6511-154">Copy the generic example of the SELECT FROM \<model>.CASES statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="b6511-155">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="b6511-155">Replace the following:</span></span>  
  
    ```  
    <select list>   
    ```  
  
     <span data-ttu-id="b6511-156">par :</span><span class="sxs-lookup"><span data-stu-id="b6511-156">with:</span></span>  
  
    ```  
    *  
    ```  
  
     <span data-ttu-id="b6511-157">Vous pouvez remplacer \* par une liste de colonnes issues des sources de données (par exemple, [Bike Buyer]).</span><span class="sxs-lookup"><span data-stu-id="b6511-157">You can also replace \* with a list of any of the columns contained within the source data (such as [Bike Buyer]).</span></span>  
  
4.  <span data-ttu-id="b6511-158">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="b6511-158">Replace the following:</span></span>  
  
    ```  
    [<mining model>]   
    ```  
  
     <span data-ttu-id="b6511-159">par :</span><span class="sxs-lookup"><span data-stu-id="b6511-159">with:</span></span>  
  
    ```  
    [Decision Tree]  
    ```  
  
     <span data-ttu-id="b6511-160">L'instruction tout entière doit se présenter comme suit :</span><span class="sxs-lookup"><span data-stu-id="b6511-160">The complete statement should now be as follows:</span></span>  
  
    ```  
    SELECT *   
    FROM [Decision Tree].CASES  
    ```  
  
5.  <span data-ttu-id="b6511-161">Dans le menu **fichier** , cliquez sur **Enregistrer DMXQuery1. DMX sous**.</span><span class="sxs-lookup"><span data-stu-id="b6511-161">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
6.  <span data-ttu-id="b6511-162">Dans la boîte de dialogue **Enregistrer sous** , accédez au dossier approprié et nommez le fichier `SELECT_DRILLTHROUGH.dmx` .</span><span class="sxs-lookup"><span data-stu-id="b6511-162">In the **Save As** dialog box, browse to the appropriate folder, and name the file `SELECT_DRILLTHROUGH.dmx`.</span></span>  
  
7.  <span data-ttu-id="b6511-163">Dans la barre d’outils, cliquez sur le bouton **exécuter** .</span><span class="sxs-lookup"><span data-stu-id="b6511-163">On the toolbar, click the **Execute** button.</span></span>  
  
     <span data-ttu-id="b6511-164">La requête retourne les données source utilisées pour l'apprentissage du modèle d'exploration de données d'arbre de décision.</span><span class="sxs-lookup"><span data-stu-id="b6511-164">The query returns the source data that was used to train the decision tree mining model.</span></span>  
  
## <a name="return-the-states-of-a-discrete-mining-model-column"></a><span data-ttu-id="b6511-165">Retour des états d'une colonne discrète du modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="b6511-165">Return the States of a Discrete Mining Model Column</span></span>  
 <span data-ttu-id="b6511-166">L'étape suivante consiste à utiliser l'instruction SELECT DISTINCT pour retourner les différents états possibles dans la colonne de modèle d'exploration de données spécifiée.</span><span class="sxs-lookup"><span data-stu-id="b6511-166">The next step is to use the SELECT DISTINCT statement to return the different possible states in the specified mining model column.</span></span>  
  
 <span data-ttu-id="b6511-167">L'exemple générique suivant utilise l'instruction SELECT DISTINCT :</span><span class="sxs-lookup"><span data-stu-id="b6511-167">The following is a generic example of the SELECT DISTINCT statement:</span></span>  
  
```  
SELECT DISTINCT [<column>]   
FROM [<mining model>]  
```  
  
 <span data-ttu-id="b6511-168">La première ligne du code définit les colonnes du modèle d'exploration de données pour lesquelles les états sont retournés :</span><span class="sxs-lookup"><span data-stu-id="b6511-168">The first line of the code defines the mining model columns for which the states are returned:</span></span>  
  
```  
SELECT DISTINCT [<column>]   
```  
  
 <span data-ttu-id="b6511-169">Vous devez inclure l'instruction DISTINCT pour être en mesure de retourner tous les états de la colonne.</span><span class="sxs-lookup"><span data-stu-id="b6511-169">You must include DISTINCT in order to return all of the states of the column.</span></span> <span data-ttu-id="b6511-170">Si vous l'excluez, l'instruction DISTINCT complète se transforme en un raccourci de création de prédiction et retourne l'état le plus probable de la colonne spécifiée.</span><span class="sxs-lookup"><span data-stu-id="b6511-170">If you exclude DISTINCT, then the full statement becomes a shortcut for a prediction and returns the most likely state of the specified column.</span></span> <span data-ttu-id="b6511-171">Pour plus d’informations, consultez [SELECT &#40;DMX&#41;](/sql/dmx/select-dmx).</span><span class="sxs-lookup"><span data-stu-id="b6511-171">For more information, see [SELECT &#40;DMX&#41;](/sql/dmx/select-dmx).</span></span>  
  
#### <a name="to-return-the-states-of-a-discrete-column"></a><span data-ttu-id="b6511-172">Pour retourner les états d'une colonne discrète</span><span class="sxs-lookup"><span data-stu-id="b6511-172">To return the states of a discrete column</span></span>  
  
1.  <span data-ttu-id="b6511-173">Dans l' **Explorateur d’objets**, cliquez avec le bouton droit sur l’instance de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , pointez sur **nouvelle requête**, puis cliquez sur **DMX**.</span><span class="sxs-lookup"><span data-stu-id="b6511-173">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="b6511-174">L'Éditeur de requête s'ouvre et contient une nouvelle requête vide.</span><span class="sxs-lookup"><span data-stu-id="b6511-174">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="b6511-175">Copiez l'exemple générique de l'instruction SELECT DISTINCT dans la requête vide.</span><span class="sxs-lookup"><span data-stu-id="b6511-175">Copy the generic example of the SELECT Distinct statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="b6511-176">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="b6511-176">Replace the following:</span></span>  
  
    ```  
    [<column,name>   
    ```  
  
     <span data-ttu-id="b6511-177">par :</span><span class="sxs-lookup"><span data-stu-id="b6511-177">with:</span></span>  
  
    ```  
    [Bike Buyer]  
    ```  
  
4.  <span data-ttu-id="b6511-178">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="b6511-178">Replace the following:</span></span>  
  
    ```  
    [<mining model>]   
    ```  
  
     <span data-ttu-id="b6511-179">par :</span><span class="sxs-lookup"><span data-stu-id="b6511-179">with:</span></span>  
  
    ```  
    [Decision Tree]  
    ```  
  
     <span data-ttu-id="b6511-180">L'instruction tout entière doit se présenter comme suit :</span><span class="sxs-lookup"><span data-stu-id="b6511-180">The complete statement should now be as follows:</span></span>  
  
    ```  
    SELECT DISTINCT [Bike Buyer]   
    FROM [Decision Tree]  
    ```  
  
5.  <span data-ttu-id="b6511-181">Dans le menu **fichier** , cliquez sur **Enregistrer DMXQuery1. DMX sous**.</span><span class="sxs-lookup"><span data-stu-id="b6511-181">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
6.  <span data-ttu-id="b6511-182">Dans la boîte de dialogue **Enregistrer sous** , accédez au dossier approprié et nommez le fichier `SELECT_DISCRETE.dmx` .</span><span class="sxs-lookup"><span data-stu-id="b6511-182">In the **Save As** dialog box, browse to the appropriate folder, and name the file `SELECT_DISCRETE.dmx`.</span></span>  
  
7.  <span data-ttu-id="b6511-183">Dans la barre d’outils, cliquez sur le bouton **exécuter** .</span><span class="sxs-lookup"><span data-stu-id="b6511-183">On the toolbar, click the **Execute** button.</span></span>  
  
     <span data-ttu-id="b6511-184">La requête retourne les états possibles de la colonne Bike Buyer.</span><span class="sxs-lookup"><span data-stu-id="b6511-184">The query returns the possible states of the Bike Buyer column.</span></span>  
  
 <span data-ttu-id="b6511-185">Au cours de la leçon suivante, vous allez évaluer si des clients potentiels sont des acheteurs de vélos à l'aide du modèle d'exploration de données d'arbre de décision.</span><span class="sxs-lookup"><span data-stu-id="b6511-185">In the next lesson, you will predict whether potential customers will be bike buyers by using the decision tree mining model.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="b6511-186">Leçon suivante</span><span class="sxs-lookup"><span data-stu-id="b6511-186">Next Lesson</span></span>  
 [<span data-ttu-id="b6511-187">Leçon 5 : Exécution des requêtes de prédiction</span><span class="sxs-lookup"><span data-stu-id="b6511-187">Lesson 5: Executing Prediction Queries</span></span>](../../2014/tutorials/lesson-5-executing-prediction-queries.md)  
  
  
