---
title: Filtrer une règle dans un modèle de règles d’association | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- filtering rules [Analysis Services]
- Mining Model Viewer [Analysis Services], rules
- Rules Viewer
ms.assetid: 26cdba5b-5bf1-439e-80a3-8759774e918b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3c904713acc6eaf132e7cb1195186165f21d971a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611406"
---
# <a name="filter-a-rule-in-an-association-rules-model"></a><span data-ttu-id="db01b-102">Filtrer une règle dans un modèle de règles d'association</span><span class="sxs-lookup"><span data-stu-id="db01b-102">Filter a Rule in an Association Rules Model</span></span>
  <span data-ttu-id="db01b-103">Vous pouvez utiliser le filtrage avec des modèles d'association pour restreindre les résultats aux associations qui vous intéressent.</span><span class="sxs-lookup"><span data-stu-id="db01b-103">You can use filtering with association models to restrict the results to just the associations that interest you.</span></span> <span data-ttu-id="db01b-104">Par exemple, vous pouvez filtrer les règles pour afficher uniquement celles qui incluent un produit spécifique.</span><span class="sxs-lookup"><span data-stu-id="db01b-104">For example, you might filter the rules to show only those that include a specific product.</span></span>  
  
 <span data-ttu-id="db01b-105">Dans le Concepteur d’exploration de données, vous pouvez utiliser les contrôles sur l’onglet **Règles** de la Visionneuse de l’algorithme MAR (Microsoft Association Rules) [!INCLUDE[msCoName](../../includes/msconame-md.md)] pour filtrer les règles affichées.</span><span class="sxs-lookup"><span data-stu-id="db01b-105">In Data Mining Designer, you use the controls on the **Rules** tab of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Association Rules Viewer to filter the rules that are displayed.</span></span>  <span data-ttu-id="db01b-106">Vous pouvez également créer une requête sur le modèle pour voir uniquement le jeu d’éléments contenant une valeur particulière.</span><span class="sxs-lookup"><span data-stu-id="db01b-106">You can also create a query on the model to see only itemset that contains a particular value.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="db01b-107">Cette option est disponible uniquement pour les modèles d'exploration de données créés à l'aide de l'algorithme Microsoft Association.</span><span class="sxs-lookup"><span data-stu-id="db01b-107">This option is available only for mining models that have been created by using the Microsoft Association Algorithm.</span></span>  
  
### <a name="filter-a-rule-in-an-association-model"></a><span data-ttu-id="db01b-108">Filtrer une règle dans un modèle d'association</span><span class="sxs-lookup"><span data-stu-id="db01b-108">Filter a rule in an association model</span></span>  
  
1.  <span data-ttu-id="db01b-109">Ouvrez le modèle d'exploration de données à l'aide de la **Visionneuse de l'algorithme MAR (Microsoft Association Rules)**.</span><span class="sxs-lookup"><span data-stu-id="db01b-109">Open the mining model by using the **Association Rules Viewer**.</span></span> <span data-ttu-id="db01b-110">Pour ce faire, dans SQL Server Management Studio, cliquez avec le bouton droit sur le nom du modèle, puis sélectionnez **Parcourir**.</span><span class="sxs-lookup"><span data-stu-id="db01b-110">To do this in SQL Server Management Studio, right click the model name and select **Browse**.</span></span> <span data-ttu-id="db01b-111">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], double-cliquez sur la structure d’exploration de données qui contient le modèle, puis cliquez sur l’onglet **Visionneuse de modèle d’exploration de données** du **Concepteur d’exploration de données**.</span><span class="sxs-lookup"><span data-stu-id="db01b-111">To do this in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], double-click the mining structure that contains the model, and then click the **Mining Model Viewer** tab of **Data Mining Designer**.</span></span>  
  
2.  <span data-ttu-id="db01b-112">Cliquez sur l'onglet **Règles** de la **Visionneuse de l'algorithme MAR (Microsoft Association Rules)**.</span><span class="sxs-lookup"><span data-stu-id="db01b-112">Click the **Rules** tab of the **Association Rules Viewer**.</span></span>  
  
3.  <span data-ttu-id="db01b-113">Tapez une condition de règle dans la zone **Filtrer la règle** .</span><span class="sxs-lookup"><span data-stu-id="db01b-113">Type a rule condition into the **Filter Rule** box.</span></span> <span data-ttu-id="db01b-114">Voici par exemple une condition de règle « Bike Stand », qui retourne également « Bike Stands ».</span><span class="sxs-lookup"><span data-stu-id="db01b-114">For example, a rule condition might be "Bike Stand", which also returns "Bike Stands".</span></span>  
  
     <span data-ttu-id="db01b-115">La zone de texte **Filtrer la règle** prend en charge les expressions régulières définies par le langage .NET.</span><span class="sxs-lookup"><span data-stu-id="db01b-115">The **Filter Rule** text box supports regular expressions as defined by the .NET language.</span></span> <span data-ttu-id="db01b-116">Par conséquent, vous pouvez utiliser des expressions telles que `((.Helmets.*Fenders.*)|(.*Fenders.*Helmets.*))`.</span><span class="sxs-lookup"><span data-stu-id="db01b-116">Therefore, you can use expressions such as the following: `((.Helmets.*Fenders.*)|(.*Fenders.*Helmets.*))`.</span></span> <span data-ttu-id="db01b-117">Cette expression retourne les jeux d'éléments qui incluent des attributs avec les mots Helmets et Fenders, dans n'importe quel ordre.</span><span class="sxs-lookup"><span data-stu-id="db01b-117">This expression would return any itemsets that include attributes with the words Helmets and Fenders, in any order.</span></span>  
  
4.  <span data-ttu-id="db01b-118">Pour **Probabilité minimale**, augmentez la valeur de probabilité afin de voir moins de règles ou réduisez cette valeur afin de voir davantage de règles.</span><span class="sxs-lookup"><span data-stu-id="db01b-118">For **Minimum probability**, increase the value of probability to see fewer rules, or decrease the value to see more rules.</span></span>  
  
5.  <span data-ttu-id="db01b-119">Pour **Importance minimale**, augmentez la valeur d'importance afin de voir moins de règles ou réduisez cette valeur afin de voir davantage de règles.</span><span class="sxs-lookup"><span data-stu-id="db01b-119">For **Minimum importance**, increase the value of importance to see fewer rules, or decrease the value to see more rules.</span></span>  
  
6.  <span data-ttu-id="db01b-120">Pour **Afficher**, sélectionnez l'une des options suivantes : **Afficher le nom et la valeur de l'attribut**, **Afficher le nom de l'attribut uniquement**ou **Afficher la valeur de l'attribut uniquement**.</span><span class="sxs-lookup"><span data-stu-id="db01b-120">For **Show**, select one of the following options: **Show attribute name and value**, **Show attribute name only**, or **Show attribute value only**.</span></span>  
  
7.  <span data-ttu-id="db01b-121">Pour **Lignes au maximum**, augmentez la valeur afin d'augmenter le nombre total de règles répondant aux conditions spécifiées ou réduisez la valeur afin de limiter le nombre de règles retournées.</span><span class="sxs-lookup"><span data-stu-id="db01b-121">For **Maximum rows**, increase the value to increase the total number of rules that meet the specified conditions, or decrease the value to limit the number of rules returned.</span></span> <span data-ttu-id="db01b-122">Les règles sont classées par ordre de probabilité ; par conséquent, vous risquez d'éliminer des règles supplémentaires qui répondent aux conditions spécifiées pour la probabilité ou l'importance.</span><span class="sxs-lookup"><span data-stu-id="db01b-122">Rules are ordered by probability, so you might eliminate additional rules that meet the specified conditions for probability or importance.</span></span>  
  
8.  <span data-ttu-id="db01b-123">Activez ou désactivez la case à cocher **Afficher le nom long** pour basculer entre les modes d'affichage des noms de règles.</span><span class="sxs-lookup"><span data-stu-id="db01b-123">Select or deselect the **Show long name** check box to toggle the way that the rules names are displayed.</span></span>  
  
     <span data-ttu-id="db01b-124">Les règles sont alors filtrées afin d'afficher uniquement celles qui contiennent l'élément indiqué.</span><span class="sxs-lookup"><span data-stu-id="db01b-124">The rules are now filtered to only display rules that contain the indicated item.</span></span> <span data-ttu-id="db01b-125">La condition de filtre s'applique aux valeurs d'attributs avant ou après le délimiteur de règle, « -> ».</span><span class="sxs-lookup"><span data-stu-id="db01b-125">The filter condition applies to attribute values either before or after the rule delimiter, "->".</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="db01b-126">La visionneuse met en cache la liste initiale des règles, en fonction d'une requête portant sur le modèle d'exploration de données ; en outre, elle n'actualise pas la liste des règles tant que vous ne modifiez pas les conditions de la requête en définissant les lignes maximales, la probabilité, l'importance ou l'affichage des noms longs.</span><span class="sxs-lookup"><span data-stu-id="db01b-126">The viewer caches the initial list of rules, based on a query to the mining model, and does not refresh the list of rules unless you change the conditions of the query by setting the maximum rows, the probability, importance, or the display of long names.</span></span> <span data-ttu-id="db01b-127">Par conséquent, si vous tapez une condition et si l'affichage n'est pas immédiatement actualisé, vous pouvez forcer la visionneuse à actualiser les données en activant, puis en désactivant la case à cocher **Afficher le nom long** .</span><span class="sxs-lookup"><span data-stu-id="db01b-127">Therefore, if you type a condition and the display does not immediately refresh, you can force the viewer to refresh the data by selecting and then deselecting the **Show long names** check box.</span></span>  
  
### <a name="create-a-query-on-the-itemsets-in-an-association-model"></a><span data-ttu-id="db01b-128">Créer une requête sur les jeux d'éléments dans un modèle d'association</span><span class="sxs-lookup"><span data-stu-id="db01b-128">Create a query on the itemsets in an association model</span></span>  
  
-   [<span data-ttu-id="db01b-129">Exemples de requêtes de modèle d'association</span><span class="sxs-lookup"><span data-stu-id="db01b-129">Association Model Query Examples</span></span>](association-model-query-examples.md)  
  
## <a name="see-also"></a><span data-ttu-id="db01b-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="db01b-130">See Also</span></span>  
 <span data-ttu-id="db01b-131">[Tâches de la visionneuse de modèle d’exploration de données et procédures](mining-model-viewer-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="db01b-131">[Mining Model Viewer Tasks and How-tos](mining-model-viewer-tasks-and-how-tos.md) </span></span>  
 <span data-ttu-id="db01b-132">[Parcourir un modèle à l’aide de la visionneuse des règles d’association Microsoft](browse-a-model-using-the-microsoft-association-rules-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="db01b-132">[Browse a Model Using the Microsoft Association Rules Viewer](browse-a-model-using-the-microsoft-association-rules-viewer.md) </span></span>  
 [<span data-ttu-id="db01b-133">Leçon 3 : Génération d’un scénario de panier d’achat &#40;Didacticiel sur l’exploration de données intermédiaire&#41;</span><span class="sxs-lookup"><span data-stu-id="db01b-133">Lesson 3: Building a Market Basket Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../tutorials/lesson-3-building-a-market-basket-scenario-intermediate-data-mining-tutorial.md)  
  
  
