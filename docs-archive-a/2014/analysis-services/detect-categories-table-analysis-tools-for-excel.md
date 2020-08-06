---
title: Détecter les catégories (outils d’analyse de table pour Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Table Analysis tools
- clustering [data mining]
- mining model, decision tree
- category detection
ms.assetid: 3c7e9ebb-d0c9-498e-a9ba-cc13eaa43520
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4874c85d7e4ab65716741e8ae9433406dfb08b74
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705696"
---
# <a name="detect-categories-table-analysis-tools-for-excel"></a><span data-ttu-id="6e34c-102">Détecter les catégories (Outils d'analyse de table pour Excel)</span><span class="sxs-lookup"><span data-stu-id="6e34c-102">Detect Categories (Table Analysis Tools for Excel)</span></span>
  <span data-ttu-id="6e34c-103">![Bouton Détecter les catégories sur le ruban](media/tat-detectcat.gif "Bouton Détecter les catégories sur le ruban")</span><span class="sxs-lookup"><span data-stu-id="6e34c-103">![Detect Categories button in ribbon](media/tat-detectcat.gif "Detect Categories button in ribbon")</span></span>

 <span data-ttu-id="6e34c-104">L’outil **détecter les catégories** détecte automatiquement les lignes d’une table qui présentent des caractéristiques similaires.</span><span class="sxs-lookup"><span data-stu-id="6e34c-104">The **Detect Categories** tool automatically finds rows in a table that have similar characteristics.</span></span>

 <span data-ttu-id="6e34c-105">Lorsque l'outil a terminé, il crée un rapport répertoriant les catégories identifiées ainsi que leurs caractéristiques distinctives.</span><span class="sxs-lookup"><span data-stu-id="6e34c-105">When the tool finishes, it creates a report that lists the categories it found, together with their distinguishing characteristics.</span></span> <span data-ttu-id="6e34c-106">Par défaut, il ajoute une nouvelle colonne à la table de données contenant la catégorie proposée pour chaque ligne de données.</span><span class="sxs-lookup"><span data-stu-id="6e34c-106">By default, it adds a new column to the data table that contains the proposed category for each row of your data.</span></span> <span data-ttu-id="6e34c-107">Vous pouvez ensuite passer les catégories en revue et les renommer.</span><span class="sxs-lookup"><span data-stu-id="6e34c-107">You can then review the categories and rename them.</span></span>

## <a name="using-the-detect-categories-tool"></a><span data-ttu-id="6e34c-108">Utilisation de l'outil Détecter les catégories</span><span class="sxs-lookup"><span data-stu-id="6e34c-108">Using the Detect Categories Tool</span></span>

1.  <span data-ttu-id="6e34c-109">Ouvrez un tableau Excel.</span><span class="sxs-lookup"><span data-stu-id="6e34c-109">Open an Excel table.</span></span>

2.  <span data-ttu-id="6e34c-110">Cliquez sur **détecter les catégories**.</span><span class="sxs-lookup"><span data-stu-id="6e34c-110">Click **Detect Categories**.</span></span>

3.  <span data-ttu-id="6e34c-111">Spécifiez les colonnes à utiliser dans l'analyse.</span><span class="sxs-lookup"><span data-stu-id="6e34c-111">Specify the columns to use in analysis.</span></span> <span data-ttu-id="6e34c-112">Vous pouvez désélectionner les colonnes qui contiennent des valeurs distinctes, comme des noms de personnes ou des ID d'enregistrement, car ces colonnes ne sont pas utiles pour l'analyse.</span><span class="sxs-lookup"><span data-stu-id="6e34c-112">You can deselect columns that have distinct values, such as personal names or record IDs, because these columns might not be useful for analysis.</span></span>

4.  <span data-ttu-id="6e34c-113">Si vous le souhaitez, spécifiez le nombre maximum de catégories à créer.</span><span class="sxs-lookup"><span data-stu-id="6e34c-113">Optionally, specify the maximum number of categories to create.</span></span> <span data-ttu-id="6e34c-114">Par défaut, l'outil crée automatiquement autant de catégories que nécessaire.</span><span class="sxs-lookup"><span data-stu-id="6e34c-114">By default, the tool automatically creates as many categories as it finds.</span></span>

5.  <span data-ttu-id="6e34c-115">Cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="6e34c-115">Click **Run**.</span></span>

6.  <span data-ttu-id="6e34c-116">L'outil crée une nouvelle feuille de calcul, nommée Rapport de catégories, qui contient la liste des catégories et leurs caractéristiques.</span><span class="sxs-lookup"><span data-stu-id="6e34c-116">The tool creates a new worksheet, named Categories Report, which contains the list of categories and their characteristics.</span></span>

 <span data-ttu-id="6e34c-117">Pour plus d’informations sur la façon de spécifier les options de l’outil, consultez [boîte de dialogue détecter les catégories (outils d’analyse de table pour Excel)](detect-categories-table-analysis-tools-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="6e34c-117">For more information about how to specify options for the tool, see [Detect Categories Dialog Box (Table Analysis Tools for Excel)](detect-categories-table-analysis-tools-for-excel.md).</span></span>

## <a name="understanding-the-categories-report"></a><span data-ttu-id="6e34c-118">Présentation du Rapport de catégories</span><span class="sxs-lookup"><span data-stu-id="6e34c-118">Understanding the Categories Report</span></span>
 <span data-ttu-id="6e34c-119">Le **rapport catégories** contient deux tables, **la liste des catégories** et les **caractéristiques**des catégories, ainsi qu’un graphique profils de **catégorie** .</span><span class="sxs-lookup"><span data-stu-id="6e34c-119">The **Categories Report** contains two tables, **Category List** and **Category Characteristics**, and a **Category Profiles** chart.</span></span>

### <a name="category-list"></a><span data-ttu-id="6e34c-120">Liste des catégories</span><span class="sxs-lookup"><span data-stu-id="6e34c-120">Category List</span></span>
 <span data-ttu-id="6e34c-121">Le premier tableau répertorie les catégories trouvées.</span><span class="sxs-lookup"><span data-stu-id="6e34c-121">The first table lists the categories that were found.</span></span> <span data-ttu-id="6e34c-122">La colonne **nombre** de lignes indique le nombre de lignes de données qui ont été affectées à chaque catégorie.</span><span class="sxs-lookup"><span data-stu-id="6e34c-122">The **Row Count** column indicates how many rows of data were assigned to each category.</span></span>

 <span data-ttu-id="6e34c-123">Le modèle crée des noms temporaires pour chaque catégorie, mais vous pouvez renommer les catégories à votre convenance.</span><span class="sxs-lookup"><span data-stu-id="6e34c-123">The model creates temporary names for each category, but you can rename the categories as you like.</span></span> <span data-ttu-id="6e34c-124">Par exemple, dans l’exemple suivant, la première catégorie a été renommée **revenu faible**, car il s’agissait de l’attribut supérieur du cluster.</span><span class="sxs-lookup"><span data-stu-id="6e34c-124">For example, in the following example, the first category has been renamed **Low Income**, because that was the top attribute of the cluster.</span></span>

 <span data-ttu-id="6e34c-125">![rapport créé par l'outil Détecter les catégories](media/dm13-tat-detectcat-report1.gif "rapport créé par l'outil Détecter les catégories")</span><span class="sxs-lookup"><span data-stu-id="6e34c-125">![report created by Detect Categories tool](media/dm13-tat-detectcat-report1.gif "report created by Detect Categories tool")</span></span>

 <span data-ttu-id="6e34c-126">Lorsque vous tapez la nouvelle étiquette, le changement est propagé à tous les autres graphiques, ainsi qu'à la liste des catégories ajoutées dans la feuille de calcul des données source.</span><span class="sxs-lookup"><span data-stu-id="6e34c-126">As soon as you type the new label, the change is propagated to all the other charts as well as to the category list added in the source data worksheet.</span></span>

### <a name="category-characteristics"></a><span data-ttu-id="6e34c-127">Caractéristiques de la catégorie</span><span class="sxs-lookup"><span data-stu-id="6e34c-127">Category Characteristics</span></span>
 <span data-ttu-id="6e34c-128">La deuxième table, **caractéristiques**de la catégorie, affiche des détails sur la composition de chaque catégorie.</span><span class="sxs-lookup"><span data-stu-id="6e34c-128">The second table, **Category Characteristics**, shows details about the makeup of each category.</span></span> <span data-ttu-id="6e34c-129">Cliquez sur le bouton **filtre** en haut de la colonne **catégorie** pour voir le focus sur une ou plusieurs catégories.</span><span class="sxs-lookup"><span data-stu-id="6e34c-129">Click the **Filter** button at the top of the **Category** column to see focus on one or just a few categories.</span></span>

 <span data-ttu-id="6e34c-130">![rapport créé par l'outil Détecter les catégories](media/dm13-tat-detectcat-report2.gif "rapport créé par l'outil Détecter les catégories")</span><span class="sxs-lookup"><span data-stu-id="6e34c-130">![report created by Detect Categories tool](media/dm13-tat-detectcat-report2.gif "report created by Detect Categories tool")</span></span>

 <span data-ttu-id="6e34c-131">L’ombrage dans la colonne, **importance relative**, indique l’importance de la combinaison de l’attribut et de la valeur en tant que facteur distinctif.</span><span class="sxs-lookup"><span data-stu-id="6e34c-131">The shading in the column, **Relative Importance**, indicates how important that combination of attribute and value is as a distinguishing factor.</span></span> <span data-ttu-id="6e34c-132">Plus la barre est longue, plus il est probable que l'attribut est fortement représentatif de cette catégorie.</span><span class="sxs-lookup"><span data-stu-id="6e34c-132">The longer the bar, the more likely it is that this attribute is strongly representative of this category.</span></span>

### <a name="categories-profile-chart"></a><span data-ttu-id="6e34c-133">Graphique des profils de catégories</span><span class="sxs-lookup"><span data-stu-id="6e34c-133">Categories Profile Chart</span></span>
 <span data-ttu-id="6e34c-134">Le graphique final dans la feuille de calcul **rapport de catégories** , **profils de catégorie**, est un **graphique croisé dynamique** interactif que vous pouvez utiliser pour réorganiser et masquer des champs, filtrer sur des valeurs et personnaliser l’apparence du graphique.</span><span class="sxs-lookup"><span data-stu-id="6e34c-134">The final chart in the **Categories Report** worksheet, **Category Profiles**, is an interactive **Pivot Chart** that you can use to rearrange and hide fields, filter on values, and customize the chart's appearance.</span></span>

 <span data-ttu-id="6e34c-135">Excel 2013 fournit désormais des **styles de graphique** et des contrôles d’éléments de **graphique** directement dans l’aire de conception qui facilitent l’amélioration de la conception du graphique.</span><span class="sxs-lookup"><span data-stu-id="6e34c-135">Excel 2013 now provides **Chart Styles** and **Chart Elements** controls right in the design surface that make it easy to improve the chart design.</span></span>

 <span data-ttu-id="6e34c-136">![rapport créé par l'outil Détecter les catégories](media/dm13-tat-detectcat-report3.gif "rapport créé par l'outil Détecter les catégories")</span><span class="sxs-lookup"><span data-stu-id="6e34c-136">![report created by Detect Categories tool](media/dm13-tat-detectcat-report3.gif "report created by Detect Categories tool")</span></span>

## <a name="requirements"></a><span data-ttu-id="6e34c-137">Spécifications</span><span class="sxs-lookup"><span data-stu-id="6e34c-137">Requirements</span></span>
 <span data-ttu-id="6e34c-138">L’outil **détecter les catégories** n’est pas requis pour la quantité ou le type de données.</span><span class="sxs-lookup"><span data-stu-id="6e34c-138">The **Detect Categories** tool has no requirements for the amount or type of data.</span></span>

> [!NOTE]
>  <span data-ttu-id="6e34c-139">Lorsque vous utilisez l’outil **détecter les catégories** , il crée une nouvelle colonne, catégorie, dans la table de données d’origine.</span><span class="sxs-lookup"><span data-stu-id="6e34c-139">When you use the **Detect Categories** tool, it creates a new column, Category, in the original data table.</span></span> <span data-ttu-id="6e34c-140">Si vous laissez cette colonne dans la table de données et que vous effectuez ensuite d'autres opérations d'exploration de données, la présence de cette colonne peut affecter vos résultats.</span><span class="sxs-lookup"><span data-stu-id="6e34c-140">If you leave this column in the data table and then perform subsequent data mining operations, the presence of this column could influence your results.</span></span> <span data-ttu-id="6e34c-141">Pour éviter que cela n'arrive, nous vous recommandons de faire une copie de la table de données sans la colonne Catégorie avant d'utiliser d'autres outils d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="6e34c-141">To ensure that this does not affect other operations, you should make a copy of the data table without the Category column before using other data mining tools.</span></span>

## <a name="related-tools"></a><span data-ttu-id="6e34c-142">Outils connexes</span><span class="sxs-lookup"><span data-stu-id="6e34c-142">Related Tools</span></span>
 <span data-ttu-id="6e34c-143">Lorsque l’outil **détecter les catégories** analyse vos données, il crée une structure d’exploration de données et un modèle d’exploration de données à l’aide de l' [!INCLUDE[msCoName](../includes/msconame-md.md)] algorithme de clustering.</span><span class="sxs-lookup"><span data-stu-id="6e34c-143">When the **Detect Categories** tool analyzes your data, it creates a data mining structure and data mining model by using the [!INCLUDE[msCoName](../includes/msconame-md.md)] Clustering algorithm.</span></span>

 <span data-ttu-id="6e34c-144">Une fois que vous avez créé un modèle d’exploration de données à l’aide de l’outil **analyser les influenceurs clés** , vous pouvez utiliser le client d’exploration de données pour Excel pour parcourir le modèle et explorer les relations de manière plus détaillée.</span><span class="sxs-lookup"><span data-stu-id="6e34c-144">After you have created a data mining model by using the **Analyze Key Influencers** tool, you can use the Data Mining Client for Excel to browse the model and explore relationships in more detail.</span></span> <span data-ttu-id="6e34c-145">Le client d'exploration de données pour Excel est un complément séparé qui fournit des fonctionnalités d'exploration de données plus avancées.</span><span class="sxs-lookup"><span data-stu-id="6e34c-145">The Data Mining Client for Excel is a separate add-in that provides more advanced data mining functionality.</span></span> <span data-ttu-id="6e34c-146">Pour plus d’informations, consultez [navigation dans les modèles dans Excel &#40;SQL Server les compléments d’exploration de données&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="6e34c-146">For information, see [Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md).</span></span>

 <span data-ttu-id="6e34c-147">Pour plus d’informations sur l’utilisation des fonctionnalités de modélisation des données dans le client d’exploration de données pour Excel, consultez [création d’un modèle d’exploration de données](creating-a-data-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="6e34c-147">For more information about using the data modeling capabilities in the Data Mining Client for Excel, see [Creating a Data Mining Model](creating-a-data-mining-model.md).</span></span>

 <span data-ttu-id="6e34c-148">Pour plus d’informations sur l’algorithme utilisé par l’outil **détecter les catégories** , consultez la rubrique « algorithme de clustering Microsoft » dans la [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] documentation en ligne de.</span><span class="sxs-lookup"><span data-stu-id="6e34c-148">For more information about the algorithm used by the **Detect Categories** tool, see the topic "Microsoft Clustering Algorithm" in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Books Online.</span></span>

## <a name="see-also"></a><span data-ttu-id="6e34c-149">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6e34c-149">See Also</span></span>
 [<span data-ttu-id="6e34c-150">Outils d'analyse de table pour Excel</span><span class="sxs-lookup"><span data-stu-id="6e34c-150">Table Analysis Tools for Excel</span></span>](table-analysis-tools-for-excel.md)


