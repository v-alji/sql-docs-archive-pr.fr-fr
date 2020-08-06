---
title: 'Leçon 2 : ajout de modèles d’exploration de données à la structure d’exploration de données Market panier | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d96a7a7d-35d7-4b34-abb5-f0822c256253
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: b9573d9359983e33cf23533787c26039572710ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702207"
---
# <a name="lesson-2-adding-mining-models-to-the-market-basket-mining-structure"></a><span data-ttu-id="291f6-102">Leçon 2 : Ajout de modèles d’exploration de données à la structure d’exploration de données Market Basket</span><span class="sxs-lookup"><span data-stu-id="291f6-102">Lesson 2: Adding Mining Models to the Market Basket Mining Structure</span></span>
  <span data-ttu-id="291f6-103">Dans cette leçon, vous allez ajouter deux modèles d’exploration de données à la structure d’exploration de données Market panier que vous avez créée au cours de [la leçon 1 : création de la structure d’exploration de données Market panier](../../2014/tutorials/lesson-1-creating-the-market-basket-mining-structure.md).</span><span class="sxs-lookup"><span data-stu-id="291f6-103">In this lesson, you will add two mining models to the Market Basket mining structure that you created in [Lesson 1: Creating the Market Basket Mining Structure](../../2014/tutorials/lesson-1-creating-the-market-basket-mining-structure.md).</span></span> <span data-ttu-id="291f6-104">Ces modèles d'exploration de données vous permettent de créer des prédictions.</span><span class="sxs-lookup"><span data-stu-id="291f6-104">These mining models will allow you to create predictions.</span></span>  
  
 <span data-ttu-id="291f6-105">Pour prédire les types de produits que les clients ont tendance à acheter en même temps, vous allez créer deux modèles d’exploration de données à l’aide de l' [algorithme Microsoft Association](../../2014/analysis-services/data-mining/microsoft-association-algorithm.md) et deux valeurs différentes pour le paramètre *MINIMUM_PROBABILTY* .</span><span class="sxs-lookup"><span data-stu-id="291f6-105">To predict the types of products that customers tend to purchase at the same time, you will create two mining models using the [Microsoft Association Algorithm](../../2014/analysis-services/data-mining/microsoft-association-algorithm.md) and two different values for the *MINIMUM_PROBABILTY* parameter.</span></span>  
  
 <span data-ttu-id="291f6-106">*MINIMUM_PROBABILTY* est un [!INCLUDE[msCoName](../includes/msconame-md.md)] paramètre d’algorithme d’association qui permet de déterminer le nombre de règles qu’un modèle d’exploration de données contiendra en spécifiant la probabilité minimale qu’une règle doit avoir.</span><span class="sxs-lookup"><span data-stu-id="291f6-106">*MINIMUM_PROBABILTY* is a [!INCLUDE[msCoName](../includes/msconame-md.md)] Association algorithm parameter that helps to determine the number of rules that a mining model will contain by specifying the minimum probability that a rule must have.</span></span> <span data-ttu-id="291f6-107">Par exemple, la valeur 0,4 spécifie qu'une règle peut être générée uniquement si la combinaison des produits que la règle décrit présente une probabilité d'occurrence d'au moins quarante pour cent.</span><span class="sxs-lookup"><span data-stu-id="291f6-107">For example, setting this value to 0.4 specifies that a rule can be generated only if the combination of products that the rule describes has at least a forty percent probability of occurring.</span></span>  
  
 <span data-ttu-id="291f6-108">Vous allez voir l’effet de la modification du paramètre *MINIMUM_PROBABILTY* dans une leçon ultérieure.</span><span class="sxs-lookup"><span data-stu-id="291f6-108">You will view the effect of changing the *MINIMUM_PROBABILTY* parameter in a later lesson.</span></span>  
  
## <a name="alter-mining-structure-statement"></a><span data-ttu-id="291f6-109">Instruction ALTER MINING STRUCTURE</span><span class="sxs-lookup"><span data-stu-id="291f6-109">ALTER MINING STRUCTURE Statement</span></span>  
 <span data-ttu-id="291f6-110">Pour ajouter un modèle d’exploration de données qui contient une table imbriquée à une structure d’exploration de données, vous utilisez l’instruction [ALTER Mining structure &#40;DMX&#41;](/sql/dmx/alter-mining-structure-dmx?view=sql-server-2016) .</span><span class="sxs-lookup"><span data-stu-id="291f6-110">To add a mining model that contains a nested table to a mining structure, you use the [ALTER MINING STRUCTURE &#40;DMX&#41;](/sql/dmx/alter-mining-structure-dmx?view=sql-server-2016) statement.</span></span> <span data-ttu-id="291f6-111">Le code de l’instruction peut être divisé en plusieurs parties :</span><span class="sxs-lookup"><span data-stu-id="291f6-111">The code in the statement can be broken into the following parts:</span></span>  
  
-   <span data-ttu-id="291f6-112">Identification de la structure d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="291f6-112">Identifying the mining structure</span></span>  
  
-   <span data-ttu-id="291f6-113">Attribution d'un nom au modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="291f6-113">Naming the mining model</span></span>  
  
-   <span data-ttu-id="291f6-114">Définition de la colonne clé</span><span class="sxs-lookup"><span data-stu-id="291f6-114">Defining the key column</span></span>  
  
-   <span data-ttu-id="291f6-115">Définition des colonnes d'entrée et des colonnes prédictibles</span><span class="sxs-lookup"><span data-stu-id="291f6-115">Defining the input and predictable columns</span></span>  
  
-   <span data-ttu-id="291f6-116">Définition des colonnes de la table imbriquée</span><span class="sxs-lookup"><span data-stu-id="291f6-116">Defining the nested table columns</span></span>  
  
-   <span data-ttu-id="291f6-117">Identification des modifications d'algorithme et de paramètre</span><span class="sxs-lookup"><span data-stu-id="291f6-117">Identifying the algorithm and parameter changes</span></span>  
  
 <span data-ttu-id="291f6-118">L'exemple générique suivant utilise l'instruction `ALTER MINING STRUCTURE` qui ajoute un modèle d'exploration de données à une structure comportant des colonnes de tables imbriquées :</span><span class="sxs-lookup"><span data-stu-id="291f6-118">The following is a generic example of the `ALTER MINING STRUCTURE` statement that adds a mining model to a structure that includes nested table columns:</span></span>  
  
```  
ALTER MINING STRUCTURE [<Mining Structure Name>]  
ADD MINING MODEL [<Mining Model Name>]  
(  
    [<key column>],  
    <mining model column> <usage>,  
    <table columns>  
    (  [<nested key column>],  
       <nested mining model columns> )  
) USING <algorithm>( <algorithm parameters> )  
```  
  
 <span data-ttu-id="291f6-119">La première ligne du code identifie la structure d'exploration de données existante à laquelle le modèle d'exploration de données sera ajouté :</span><span class="sxs-lookup"><span data-stu-id="291f6-119">The first line of the code identifies the existing mining structure to which the mining model will be added:</span></span>  
  
```  
ALTER MINING STRUCTURE [<mining structure name>]  
```  
  
 <span data-ttu-id="291f6-120">La ligne suivante du code désigne le modèle d'exploration de données qui sera ajouté à la structure d'exploration de données :</span><span class="sxs-lookup"><span data-stu-id="291f6-120">The next line of the code names the mining model that will be added to the mining structure:</span></span>  
  
```  
ADD MINING MODEL [<mining model name>]  
```  
  
 <span data-ttu-id="291f6-121">Pour plus d’informations sur l’attribution d’un nom à un objet dans les extensions DMX (Data Mining Extensions), consultez [identificateurs &#40;dmx&#41;](/sql/dmx/identifiers-dmx).</span><span class="sxs-lookup"><span data-stu-id="291f6-121">For information about naming an object in Data Mining Extensions (DMX), see [Identifiers &#40;DMX&#41;](/sql/dmx/identifiers-dmx).</span></span>  
  
 <span data-ttu-id="291f6-122">Les lignes suivantes du code définissent les colonnes de la structure d’exploration de données qui seront utilisées par le modèle d’exploration de données :</span><span class="sxs-lookup"><span data-stu-id="291f6-122">The next lines of the code define the columns in the mining structure that will be used by the mining model:</span></span>  
  
```  
[<key column>],  
<mining model columns> <usage>,  
```  
  
 <span data-ttu-id="291f6-123">Vous pouvez utiliser uniquement des colonnes qui existent déjà dans la structure d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="291f6-123">You can only use columns that already exist in the mining structure.</span></span>  
  
 <span data-ttu-id="291f6-124">La première colonne dans la liste de colonnes de modèle d'exploration de données doit être la colonne clé dans la structure d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="291f6-124">The first column in the list of mining model columns must be the key column in the mining structure.</span></span> <span data-ttu-id="291f6-125">Toutefois, il n’est pas nécessaire de taper `KEY` après la colonne clé pour spécifier l’utilisation.</span><span class="sxs-lookup"><span data-stu-id="291f6-125">However, you do not have to type `KEY` after the key column to specify usage.</span></span> <span data-ttu-id="291f6-126">En effet, vous avez déjà défini la colonne en tant que clé lorsque vous avez créé la structure d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="291f6-126">That is because you have already defined the column as a key when you created the mining structure.</span></span>  
  
 <span data-ttu-id="291f6-127">Les lignes restantes spécifient l'utilisation des colonnes dans le nouveau modèle d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="291f6-127">The remaining lines specify the usage of the columns in the new mining model.</span></span> <span data-ttu-id="291f6-128">Vous pouvez spécifier qu’une colonne dans le modèle d’exploration de données sera utilisée pour la prédiction à l’aide de la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="291f6-128">You can specify that a column in the mining model will be used for prediction by using the following syntax:</span></span>  
  
```  
<column name> PREDICT,  
```  
  
 <span data-ttu-id="291f6-129">Si vous ne spécifiez pas d'utilisation, vous n'avez pas besoin d'inclure une colonne de structure d'exploration de données dans la liste.</span><span class="sxs-lookup"><span data-stu-id="291f6-129">If you do not specify usage, you do not have to include a data mining structure column in the list.</span></span> <span data-ttu-id="291f6-130">Toutes les colonnes utilisées par la structure d'exploration de données référencée sont automatiquement mises à la disposition des modèles d'exploration de données basés sur cette structure.</span><span class="sxs-lookup"><span data-stu-id="291f6-130">All columns that are used by the referenced data mining structure are automatically available for use by the mining models that are based on that structure.</span></span> <span data-ttu-id="291f6-131">Toutefois, le modèle n'utilisera pas les colonnes pour la formation à moins que vous ne spécifiiez l'utilisation.</span><span class="sxs-lookup"><span data-stu-id="291f6-131">However, the model will not use the columns for training unless you specify the usage.</span></span>  
  
 <span data-ttu-id="291f6-132">La dernière ligne du code définit l'algorithme et les paramètres d'algorithme employés pour générer le modèle d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="291f6-132">The last line in the code defines the algorithm and algorithm parameters that will be used to generate the mining model.</span></span>  
  
```  
) USING <algorithm>( <algorithm parameters> )  
```  
  
## <a name="lesson-tasks"></a><span data-ttu-id="291f6-133">Tâches de la leçon</span><span class="sxs-lookup"><span data-stu-id="291f6-133">Lesson Tasks</span></span>  
 <span data-ttu-id="291f6-134">Dans cette leçon, vous allez effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="291f6-134">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="291f6-135">ajouter un modèle d'exploration de données Association à la structure à l'aide de la probabilité par défaut ;</span><span class="sxs-lookup"><span data-stu-id="291f6-135">Add an association mining model to the structure using the default probability</span></span>  
  
-   <span data-ttu-id="291f6-136">ajouter un modèle d'exploration de données Association à la structure à l'aide d'une probabilité modifiée.</span><span class="sxs-lookup"><span data-stu-id="291f6-136">Add an association mining model to the structure using a modified probability</span></span>  
  
## <a name="adding-an-association-mining-model-to-the-structure-using-the-default-minimum_probability"></a><span data-ttu-id="291f6-137">Ajout d'un modèle d'exploration de données Association à la structure en utilisant le paramètre MINIMUM_PROBABILITY par défaut</span><span class="sxs-lookup"><span data-stu-id="291f6-137">Adding an Association Mining Model to the Structure Using the Default MINIMUM_PROBABILITY</span></span>  
 <span data-ttu-id="291f6-138">La première tâche consiste à ajouter un nouveau modèle d’exploration de données à la structure d’exploration de données Market panier basée sur l' [!INCLUDE[msCoName](../includes/msconame-md.md)] algorithme d’association, en utilisant la valeur par défaut pour *MINIMUM_PROBABILITY*.</span><span class="sxs-lookup"><span data-stu-id="291f6-138">The first task is to add a new mining model to the Market Basket mining structure based on the [!INCLUDE[msCoName](../includes/msconame-md.md)] Association algorithm using the default value for *MINIMUM_PROBABILITY*.</span></span>  
  
#### <a name="to-add-an-association-mining-model"></a><span data-ttu-id="291f6-139">Pour ajouter un modèle d'exploration de données Association</span><span class="sxs-lookup"><span data-stu-id="291f6-139">To add an Association mining model</span></span>  
  
1.  <span data-ttu-id="291f6-140">Dans l' **Explorateur d’objets**, cliquez avec le bouton droit sur l’instance de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , pointez sur **nouvelle requête**, puis cliquez sur **DMX**.</span><span class="sxs-lookup"><span data-stu-id="291f6-140">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="291f6-141">L'Éditeur de requête s'ouvre et contient une nouvelle requête vide.</span><span class="sxs-lookup"><span data-stu-id="291f6-141">Query Editor opens and contains a new, blank query.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="291f6-142">Pour créer une requête DMX sur une base de données [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] spécifique, cliquez avec le bouton droit sur la base de données au lieu de l'instance.</span><span class="sxs-lookup"><span data-stu-id="291f6-142">To create a DMX query against a specific [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database, right-click the database instead of the instance.</span></span>  
  
2.  <span data-ttu-id="291f6-143">Copiez l'exemple générique de l'instruction `ALTER MINING STRUCTURE` dans la requête vide.</span><span class="sxs-lookup"><span data-stu-id="291f6-143">Copy the generic example of the `ALTER MINING STRUCTURE` statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="291f6-144">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="291f6-144">Replace the following:</span></span>  
  
    ```  
    <mining structure name>   
    ```  
  
     <span data-ttu-id="291f6-145">par :</span><span class="sxs-lookup"><span data-stu-id="291f6-145">with:</span></span>  
  
    ```  
    [Market Basket]  
    ```  
  
4.  <span data-ttu-id="291f6-146">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="291f6-146">Replace the following:</span></span>  
  
    ```  
    <mining model name>   
    ```  
  
     <span data-ttu-id="291f6-147">par :</span><span class="sxs-lookup"><span data-stu-id="291f6-147">with:</span></span>  
  
    ```  
    [Default Association]  
    ```  
  
5.  <span data-ttu-id="291f6-148">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="291f6-148">Replace the following:</span></span>  
  
    ```  
    [<key column>],  
    <mining model columns>,  
    <table columns>  
    (  [<nested key column>],  
       <nested mining model columns> )  
    ```  
  
     <span data-ttu-id="291f6-149">par :</span><span class="sxs-lookup"><span data-stu-id="291f6-149">with:</span></span>  
  
    ```  
    OrderNumber,  
        [Products] PREDICT (  
            [Model]  
        )  
    ```  
  
     <span data-ttu-id="291f6-150">Dans ce cas, la table `[Products]` a été désignée comme colonne prédictible `.`. Par ailleurs, la colonne `[Model]` est incluse dans la liste des colonnes de la table imbriquée car il s'agit de la colonne clé de la table imbriquée.</span><span class="sxs-lookup"><span data-stu-id="291f6-150">In this case, the `[Products]` table has been designated as the predictable column`.` Also, the `[Model]` column is included in the list of nested table columns because it is the key column of the nested table.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="291f6-151">N'oubliez pas qu'une clé imbriquée est différente d'une clé de cas.</span><span class="sxs-lookup"><span data-stu-id="291f6-151">Remember that a nested key is different from a case key.</span></span> <span data-ttu-id="291f6-152">Une clé de cas est un identificateur unique du cas, alors que la clé imbriquée est un attribut que vous souhaitez modéliser.</span><span class="sxs-lookup"><span data-stu-id="291f6-152">A case key is a unique identifier of the case, whereas the nested key is an attribute that you want to model.</span></span>  
  
6.  <span data-ttu-id="291f6-153">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="291f6-153">Replace the following:</span></span>  
  
    ```  
    USING <algorithm>( <algorithm parameters> )  
    ```  
  
     <span data-ttu-id="291f6-154">par :</span><span class="sxs-lookup"><span data-stu-id="291f6-154">with:</span></span>  
  
    ```  
    Using Microsoft_Association_Rules  
    ```  
  
     <span data-ttu-id="291f6-155">L'instruction obtenue doit se présenter comme suit :</span><span class="sxs-lookup"><span data-stu-id="291f6-155">The resulting statement should now be as follows:</span></span>  
  
    ```  
    ALTER MINING STRUCTURE [Market Basket]  
    ADD MINING MODEL [Default Association]  
    (  
        OrderNumber,  
        [Products] PREDICT (  
            [Model]  
        )  
    )  
    Using Microsoft_Association_Rules  
    ```  
  
7.  <span data-ttu-id="291f6-156">Dans le menu **fichier** , cliquez sur **Enregistrer DMXQuery1. DMX sous**.</span><span class="sxs-lookup"><span data-stu-id="291f6-156">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
8.  <span data-ttu-id="291f6-157">Dans la boîte de dialogue **Enregistrer sous** , accédez au dossier approprié et nommez le fichier `Default_Association_Model.dmx` .</span><span class="sxs-lookup"><span data-stu-id="291f6-157">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Default_Association_Model.dmx`.</span></span>  
  
9. <span data-ttu-id="291f6-158">Dans la barre d’outils, cliquez sur le bouton **exécuter** .</span><span class="sxs-lookup"><span data-stu-id="291f6-158">On the toolbar, click the **Execute** button.</span></span>  
  
## <a name="adding-an-association-mining-model-to-the-structure-changing-the-default-minimum_probability"></a><span data-ttu-id="291f6-159">Ajout d'un modèle d'exploration de données Association à la structure en modifiant le paramètre MINIMUM_PROBABILITY par défaut</span><span class="sxs-lookup"><span data-stu-id="291f6-159">Adding an Association Mining Model to the Structure Changing the Default MINIMUM_PROBABILITY</span></span>  
 <span data-ttu-id="291f6-160">La tâche suivante consiste à ajouter un nouveau modèle d'exploration de données à la structure d'exploration de données Market Basket en partant de l'algorithme [!INCLUDE[msCoName](../includes/msconame-md.md)] Association, puis en attribuant la valeur par défaut 0,01 au paramètre MINIMUM_PROBABILITY.</span><span class="sxs-lookup"><span data-stu-id="291f6-160">The next task is to add a new mining model to the Market Basket mining structure based on the [!INCLUDE[msCoName](../includes/msconame-md.md)] Association algorithm, and change the default value for MINIMUM_PROBABILITY to 0.01.</span></span> <span data-ttu-id="291f6-161">La modification du paramètre force alors l'algorithme [!INCLUDE[msCoName](../includes/msconame-md.md)] Association à créer d'autres règles.</span><span class="sxs-lookup"><span data-stu-id="291f6-161">Changing the parameter will cause the [!INCLUDE[msCoName](../includes/msconame-md.md)] Association algorithm to create more rules.</span></span>  
  
#### <a name="to-add-an-association-mining-model"></a><span data-ttu-id="291f6-162">Pour ajouter un modèle d'exploration de données Association</span><span class="sxs-lookup"><span data-stu-id="291f6-162">To add an Association mining model</span></span>  
  
1.  <span data-ttu-id="291f6-163">Dans l' **Explorateur d’objets**, cliquez avec le bouton droit sur l’instance de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , pointez sur **nouvelle requête**, puis cliquez sur **DMX**.</span><span class="sxs-lookup"><span data-stu-id="291f6-163">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="291f6-164">L'Éditeur de requête s'ouvre et contient une nouvelle requête vide.</span><span class="sxs-lookup"><span data-stu-id="291f6-164">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="291f6-165">Copiez l'exemple générique de l'instruction `ALTER MINING STRUCTURE` dans la requête vide.</span><span class="sxs-lookup"><span data-stu-id="291f6-165">Copy the generic example of the `ALTER MINING STRUCTURE` statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="291f6-166">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="291f6-166">Replace the following:</span></span>  
  
    ```  
    <mining structure name>   
    ```  
  
     <span data-ttu-id="291f6-167">par :</span><span class="sxs-lookup"><span data-stu-id="291f6-167">with:</span></span>  
  
    ```  
    Market Basket  
    ```  
  
4.  <span data-ttu-id="291f6-168">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="291f6-168">Replace the following:</span></span>  
  
    ```  
    <mining model name>   
    ```  
  
     <span data-ttu-id="291f6-169">par :</span><span class="sxs-lookup"><span data-stu-id="291f6-169">with:</span></span>  
  
    ```  
    [Modified Association]  
    ```  
  
5.  <span data-ttu-id="291f6-170">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="291f6-170">Replace the following:</span></span>  
  
    ```  
    <mining model columns>,  
    <table columns>  
    (  [<nested key column>],  
       <nested mining model columns> )  
    ```  
  
     <span data-ttu-id="291f6-171">par :</span><span class="sxs-lookup"><span data-stu-id="291f6-171">with:</span></span>  
  
    ```  
    OrderNumber,  
    [Products] PREDICT (  
            [Model]  
        )  
    ```  
  
     <span data-ttu-id="291f6-172">Dans ce cas, la table `[Products]` est désignée en tant que colonne prédictible.</span><span class="sxs-lookup"><span data-stu-id="291f6-172">In this case, the `[Products]` table has been designated as the predictable column.</span></span> <span data-ttu-id="291f6-173">Par ailleurs, la colonne `[MODEL]` est incluse dans la liste car il s'agit de la colonne clé dans la table imbriquée.</span><span class="sxs-lookup"><span data-stu-id="291f6-173">Also, the `[MODEL]` column is included in the list because it is the key column in the nested table.</span></span>  
  
6.  <span data-ttu-id="291f6-174">Remplacez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="291f6-174">Replace the following:</span></span>  
  
    ```  
    USING <algorithm>( <algorithm parameters> )  
    ```  
  
     <span data-ttu-id="291f6-175">par :</span><span class="sxs-lookup"><span data-stu-id="291f6-175">with:</span></span>  
  
    ```  
    USING Microsoft_Association_Rules (Minimum_Probability = 0.1)  
    ```  
  
     <span data-ttu-id="291f6-176">L'instruction obtenue doit se présenter comme suit :</span><span class="sxs-lookup"><span data-stu-id="291f6-176">The resulting statement should now be as follows:</span></span>  
  
    ```  
    ALTER MINING STRUCTURE [Market Basket]  
    ADD MINING MODEL [Modified Assocation]  
    (  
        OrderNumber,  
        [Products] PREDICT (  
            [Model]  
        )  
    )  
    USING Microsoft_Association_Rules (Minimum_Probability = 0.1)  
    ```  
  
7.  <span data-ttu-id="291f6-177">Dans le menu **fichier** , cliquez sur **Enregistrer DMXQuery1. DMX sous**.</span><span class="sxs-lookup"><span data-stu-id="291f6-177">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
8.  <span data-ttu-id="291f6-178">Dans la boîte de dialogue **Enregistrer sous** , accédez au dossier approprié et nommez le fichier `Modified Association_Model.dmx` .</span><span class="sxs-lookup"><span data-stu-id="291f6-178">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Modified Association_Model.dmx`.</span></span>  
  
9. <span data-ttu-id="291f6-179">Dans la barre d’outils, cliquez sur le bouton **exécuter** .</span><span class="sxs-lookup"><span data-stu-id="291f6-179">On the toolbar, click the **Execute** button.</span></span>  
  
 <span data-ttu-id="291f6-180">Dans la leçon suivante, vous allez traiter la structure d'exploration de données Market Basket et ses modèles d'exploration de données associés.</span><span class="sxs-lookup"><span data-stu-id="291f6-180">In this next lesson you will process the Market Basket mining structure together with its associated mining models.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="291f6-181">Leçon suivante</span><span class="sxs-lookup"><span data-stu-id="291f6-181">Next Lesson</span></span>  
 [<span data-ttu-id="291f6-182">Leçon 3 : Traitement de la structure d'exploration de données Market Basket</span><span class="sxs-lookup"><span data-stu-id="291f6-182">Lesson 3: Processing the Market Basket Mining Structure</span></span>](../../2014/tutorials/lesson-3-processing-the-market-basket-mining-structure.md)  
  
  
