---
title: Ajout d’une vue de source de données avec des tables imbriquées (didacticiel sur l’exploration de données intermédiaire) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a14cd7f1-7a10-4ec6-af6a-f5f0676a0308
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: da1a9bff093e0b59e9d1166554d95bcf61aded08
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704507"
---
# <a name="adding-a-data-source-view-with-nested-tables-intermediate-data-mining-tutorial"></a><span data-ttu-id="4c4d4-102">Ajout d'une vue de source de données avec les tables imbriquées (Didacticiel intermédiaire sur l'exploration de données)</span><span class="sxs-lookup"><span data-stu-id="4c4d4-102">Adding a Data Source View with Nested Tables (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="4c4d4-103">Pour créer un modèle de panier d'achat, vous devez utiliser une vue de source de données qui prend en charge les données associatives.</span><span class="sxs-lookup"><span data-stu-id="4c4d4-103">To create a market basket model, you must use a data source view that supports associative data.</span></span> <span data-ttu-id="4c4d4-104">Cette vue de source de données sera également utilisée pour le scénario Sequence Clustering.</span><span class="sxs-lookup"><span data-stu-id="4c4d4-104">This data source view will also be used for the sequence clustering scenario.</span></span>  
  
 <span data-ttu-id="4c4d4-105">Cette vue de source de données est différente des autres que vous avez pu utiliser, car elle contient une *table imbriquée*.</span><span class="sxs-lookup"><span data-stu-id="4c4d4-105">This data source view is different from others that you may have worked with because it contains a *nested table*.</span></span> <span data-ttu-id="4c4d4-106">Une *table imbriquée* est une table qui contient plusieurs lignes d’informations sur une seule ligne dans la table de cas.</span><span class="sxs-lookup"><span data-stu-id="4c4d4-106">A *nested table* is a table that contains multiple rows of information about a single row in the case table.</span></span> <span data-ttu-id="4c4d4-107">Par exemple, si votre modèle analyse le comportement d'achat de clients, vous utilisez généralement une table qui a une ligne unique pour chaque client comme table de cas.</span><span class="sxs-lookup"><span data-stu-id="4c4d4-107">For example, if your model analyzes the purchasing behavior of customers, you would typically use a table that has a unique row for each customer as the case table.</span></span> <span data-ttu-id="4c4d4-108">Toutefois, chaque client peut faire plusieurs achats, et vous pouvez analyser la séquence des achats, ou les produits qui sont fréquemment achetés ensemble.</span><span class="sxs-lookup"><span data-stu-id="4c4d4-108">However, each customer might make multiple purchases, and you might want to analyze the sequence of purchases, or products that are frequently purchased together.</span></span> <span data-ttu-id="4c4d4-109">Pour représenter de façon logique ces achats dans votre modèle, vous ajoutez une autre table à la vue de source de données qui répertorie les achats pour chaque client.</span><span class="sxs-lookup"><span data-stu-id="4c4d4-109">To logically represent these purchases in your model, you add another table to the data source view that lists the purchases for each customer.</span></span>  
  
 <span data-ttu-id="4c4d4-110">Cette table des achats imbriquée présente une relation plusieurs-à-un avec la table des clients.</span><span class="sxs-lookup"><span data-stu-id="4c4d4-110">This nested purchases table is related to the customer table by a many-to-one relationship.</span></span> <span data-ttu-id="4c4d4-111">La table imbriquée peut contenir de nombreuses lignes pour chaque client, chaque ligne contenant un produit unique ayant été acheté, ainsi que des informations supplémentaires éventuelles sur l'ordre dans lequel les achats ont été effectués, le prix au moment de la commande ou les promotions appliquées.</span><span class="sxs-lookup"><span data-stu-id="4c4d4-111">The nested table might contain many rows for each customer, each row containing a single product that was purchased, perhaps with additional information about the order that the purchases were made, the price at the time of the order, or any promotions that applied.</span></span> <span data-ttu-id="4c4d4-112">Vous pouvez utiliser les informations dans la table imbriquée comme entrées au modèle, ou comme attribut prédictible.</span><span class="sxs-lookup"><span data-stu-id="4c4d4-112">You can use the information in the nested table as inputs to the model, or as the predictable attribute.</span></span>  
  
 <span data-ttu-id="4c4d4-113">Dans cette leçon, vous effectuez les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="4c4d4-113">In this lesson, you do the following tasks:</span></span>  
  
-   <span data-ttu-id="4c4d4-114">Vous ajoutez une vue de source de données à la [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] source de données.</span><span class="sxs-lookup"><span data-stu-id="4c4d4-114">You add a data source view to the [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] data source.</span></span>  
  
-   <span data-ttu-id="4c4d4-115">Vous ajoutez à cette vue la table de cas et la table imbriquée.</span><span class="sxs-lookup"><span data-stu-id="4c4d4-115">You add the case and nested tables to this view.</span></span>  
  
-   <span data-ttu-id="4c4d4-116">Vous spécifiez la relation plusieurs-à-un entre la table de cas et la table imbriquée.</span><span class="sxs-lookup"><span data-stu-id="4c4d4-116">You specify the many-to-one relationship between the case and nested table.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4c4d4-117">.</span><span class="sxs-lookup"><span data-stu-id="4c4d4-117">.</span></span> <span data-ttu-id="4c4d4-118">Il est essentiel de suivre exactement la procédure décrite, afin de spécifier correctement la relation entre la table de cas et la table imbriquée, et ainsi éviter les erreurs lorsque vous traiterez le modèle.</span><span class="sxs-lookup"><span data-stu-id="4c4d4-118">It is important that you follow the described procedure exactly, to correctly specify the relationship between the case table and the nested table and to avoid errors when you process the model.</span></span>  
  
-   <span data-ttu-id="4c4d4-119">Vous définissez le mode d'utilisation des colonnes de données dans le modèle.</span><span class="sxs-lookup"><span data-stu-id="4c4d4-119">You define how the columns of data are used in the model.</span></span>  
  
 <span data-ttu-id="4c4d4-120">Pour plus d’informations sur l’utilisation des tables de cas et imbriquées, ainsi que sur la façon de choisir une clé de table imbriquée, consultez [tables imbriquées &#40;Analysis Services-exploration de données&#41;](../../2014/analysis-services/data-mining/nested-tables-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="4c4d4-120">For more information about working with case and nested tables, and how to choose a nested table key, see [Nested Tables &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/nested-tables-analysis-services-data-mining.md).</span></span>  
  
### <a name="to-add-a-data-source-view"></a><span data-ttu-id="4c4d4-121">Pour ajouter une vue de source de données</span><span class="sxs-lookup"><span data-stu-id="4c4d4-121">To add a data source view</span></span>  
  
1.  <span data-ttu-id="4c4d4-122">Dans Explorateur de solutions, cliquez avec le bouton droit sur **vues de source de données**, puis sélectionnez **nouvelle vue de source de données**.</span><span class="sxs-lookup"><span data-stu-id="4c4d4-122">In Solution Explorer, right-click **Data Source Views**, and then select **New Data Source View**.</span></span>  
  
     <span data-ttu-id="4c4d4-123">L'Assistant Vue de source de données s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="4c4d4-123">The Data Source View Wizard opens.</span></span>  
  
2.  <span data-ttu-id="4c4d4-124">Sur la page **Bienvenue dans l'Assistant Sources de données** , cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="4c4d4-124">On the **Welcome to the Data Source View Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="4c4d4-125">Dans la page **Sélectionner une source de données** , sous **sources de données relationnelles**, sélectionnez la [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] source de données que vous avez créée dans le didacticiel sur l’exploration de données de base.</span><span class="sxs-lookup"><span data-stu-id="4c4d4-125">On the **Select a Data Source** page, under **Relational data sources**, select the [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] data source that you created in the Basic Data Mining Tutorial.</span></span> <span data-ttu-id="4c4d4-126">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="4c4d4-126">Click **Next**.</span></span>  
  
4.  <span data-ttu-id="4c4d4-127">Dans la page **Sélectionner des tables et des vues** , sélectionnez les tables suivantes, puis cliquez sur la flèche droite pour les inclure dans la nouvelle vue de source de données :</span><span class="sxs-lookup"><span data-stu-id="4c4d4-127">On the **Select Tables and Views** page, select the following tables, and then click the right arrow to include them in the new data source view:</span></span>  
  
    -   `vAssocSeqOrders`  
  
    -   `vAssocSeqLineItems`  
  
5.  <span data-ttu-id="4c4d4-128">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="4c4d4-128">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="4c4d4-129">Dans la page **fin de l’Assistant** , la vue de source de données est nommée par défaut [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4c4d4-129">On the **Completing the Wizard** page, by default the data source view is named [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)].</span></span> <span data-ttu-id="4c4d4-130">Remplacez le nom par `Orders` , puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="4c4d4-130">Change the name to `Orders`, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="4c4d4-131">Le concepteur de vue de source de données s’ouvre et la `Orders` vue de source de données s’affiche.</span><span class="sxs-lookup"><span data-stu-id="4c4d4-131">Data Source View Designer opens and the `Orders` data source view appears.</span></span>  
  
### <a name="to-create-a-relationship-between-tables"></a><span data-ttu-id="4c4d4-132">Pour créer une relation entre des tables</span><span class="sxs-lookup"><span data-stu-id="4c4d4-132">To create a relationship between tables</span></span>  
  
1.  <span data-ttu-id="4c4d4-133">Dans le Concepteur de vue de source de données, positionnez les deux tables afin que les tables soient alignées horizontalement, avec la table vAssocSeqLineItems sur le côté gauche et la table vAssocSeqOrders sur le côté droit.</span><span class="sxs-lookup"><span data-stu-id="4c4d4-133">In Data Source View Designer, position the two tables so that the tables are aligned horizontally, with the vAssocSeqLineItems table on the left side and the vAssocSeqOrders table on the right side.</span></span>  
  
2.  <span data-ttu-id="4c4d4-134">Sélectionnez la colonne **OrderNumber** dans la table vAssocSeqLineItems.</span><span class="sxs-lookup"><span data-stu-id="4c4d4-134">Select the **OrderNumber** column in the vAssocSeqLineItems table.</span></span>  
  
3.  <span data-ttu-id="4c4d4-135">Faites glisser la colonne vers la table vAssocSeqOrders et placez-la sur la colonne **OrderNumber** .</span><span class="sxs-lookup"><span data-stu-id="4c4d4-135">Drag the column to the vAssocSeqOrders table, and put it on the **OrderNumber** column.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="4c4d4-136">Veillez à faire glisser la colonne **OrderNumber** de la table imbriquée vAssocSeqLineItems, qui représente le côté « plusieurs » de la jointure, vers la table de cas vAssocSeqOrders, qui représente le côté « un » de la jointure.</span><span class="sxs-lookup"><span data-stu-id="4c4d4-136">Make sure to drag the **OrderNumber** column from the vAssocSeqLineItems nested table, which represents the many side of the join, to the vAssocSeqOrders case table, which represents the one side of the join.</span></span>  
  
     <span data-ttu-id="4c4d4-137">Une nouvelle *relation plusieurs-à-un* existe désormais entre les tables VAssocSeqLineItems et vAssocSeqOrders.</span><span class="sxs-lookup"><span data-stu-id="4c4d4-137">A new *many-to-one relationship* now exists between the vAssocSeqLineItems and vAssocSeqOrders tables.</span></span> <span data-ttu-id="4c4d4-138">Si vous avez joint les tables correctement, la vue de source de données doit apparaître comme suit :</span><span class="sxs-lookup"><span data-stu-id="4c4d4-138">If you have joined the tables correctly, the data source view should appear as follows:</span></span>  
  
     <span data-ttu-id="4c4d4-139">![jointure plusieurs-à-un attendue sur des tables imbriquées et des tables de cas](../../2014/tutorials/media/dsv-nestedjoin-illustration.gif "jointure plusieurs-à-un attendue sur des tables imbriquées et des tables de cas")</span><span class="sxs-lookup"><span data-stu-id="4c4d4-139">![expected many-to-one join on nested and case table](../../2014/tutorials/media/dsv-nestedjoin-illustration.gif "expected many-to-one join on nested and case table")</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="4c4d4-140">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="4c4d4-140">Next Task in Lesson</span></span>  
 [<span data-ttu-id="4c4d4-141">Création d’une structure et d’un modèle de panier d’évolution &#40;didacticiel sur l’exploration de données intermédiaire&#41;</span><span class="sxs-lookup"><span data-stu-id="4c4d4-141">Creating a Market Basket Structure and Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-market-basket-structure-and-model-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="4c4d4-142">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4c4d4-142">See Also</span></span>  
 <span data-ttu-id="4c4d4-143">[Didacticiel sur l’exploration de données intermédiaire &#40;Analysis Services d’exploration de données&#41;](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="4c4d4-143">[Intermediate Data Mining Tutorial &#40;Analysis Services - Data Mining&#41;](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="4c4d4-144">[Structures d’exploration de données &#40;Analysis Services d’exploration de données&#41;](../../2014/analysis-services/data-mining/mining-structures-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="4c4d4-144">[Mining Structures &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/mining-structures-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="4c4d4-145">Modèles d’exploration de données &#40;Analysis Services - Exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="4c4d4-145">Mining Models &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/mining-models-analysis-services-data-mining.md)  
  
  
