---
title: Remplacer une table ou une requête nommée dans une vue de source de données (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- replacing tables
- data source views [Analysis Services], tables
- named queries [Analysis Services], replacing tables
- tables [Analysis Services], data source views
- partitions [Analysis Services], named queries
ms.assetid: 60c2a018-1299-4915-b60e-e73316524def
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2b5055de60ba757c9dcfa118e4e2c4748c6534e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611358"
---
# <a name="replace-a-table-or-a-named-query-in-a-data-source-view-analysis-services"></a><span data-ttu-id="b60f7-102">Remplacer une table ou une requête nommée dans une vue de source de données (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="b60f7-102">Replace a Table or a Named Query in a Data Source View (Analysis Services)</span></span>
  <span data-ttu-id="b60f7-103">Dans le Concepteur de vue de source de données, vous pouvez remplacer une table, une vue ou une requête nommée dans une vue de source de données (DSV) par une autre table ou vue provenant de la même source de données ou d'une source de données différente ou par une requête nommée définie dans la vue DSV.</span><span class="sxs-lookup"><span data-stu-id="b60f7-103">In Data Source View Designer, you can replace a table, view, or named query in a data source view (DSV) with a different table or view from the same or a different data source, or with a named query defined in the DSV.</span></span> <span data-ttu-id="b60f7-104">Quand vous remplacez une table, tous les autres objets qui figurent dans un projet ou une base de données [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] et qui contiennent des références à la table continuent à faire référence à la table, car l’ID d’objet de la table reste le même dans la vue DSV.</span><span class="sxs-lookup"><span data-stu-id="b60f7-104">When you replace a table, all other objects in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database or project that have references to the table continue to reference the table because the object ID for the table in the DSV does not change.</span></span> <span data-ttu-id="b60f7-105">Toutes les relations qui continuent à être pertinentes (correspondance des noms et des types de colonne) sont conservées.</span><span class="sxs-lookup"><span data-stu-id="b60f7-105">Any relationships that are still relevant (based on name and column-type matching) are retained.</span></span> <span data-ttu-id="b60f7-106">Par contre, si vous supprimez une table et que vous en ajoutez une autre, les références et les relations sont supprimées et doivent être recréées.</span><span class="sxs-lookup"><span data-stu-id="b60f7-106">In contrast, if you delete and then add a table, references and relationships are lost and must be recreated.</span></span>  
  
 <span data-ttu-id="b60f7-107">Pour pouvoir remplacer une table par une autre table, vous devez disposer d'une connexion active avec les données sources du Concepteur de vue de source de données en mode projet.</span><span class="sxs-lookup"><span data-stu-id="b60f7-107">To replace a table with another table, you must have an active connection to the source data in Data Source View Designer in project mode.</span></span>  
  
 <span data-ttu-id="b60f7-108">La plupart du temps, vous remplacez une table de la vue de source de données par une autre table de la source de données.</span><span class="sxs-lookup"><span data-stu-id="b60f7-108">You most frequently replace a table in the data source view with another table in the data source.</span></span> <span data-ttu-id="b60f7-109">Cependant, vous pouvez également remplacer une requête nommée par une table.</span><span class="sxs-lookup"><span data-stu-id="b60f7-109">However, you can also replace a named query with a table.</span></span> <span data-ttu-id="b60f7-110">Par exemple, vous pouvez avoir remplacé une table par une requête nommée et vouloir maintenant revenir à une table.</span><span class="sxs-lookup"><span data-stu-id="b60f7-110">For example, you previously replaced a table with a named query, and now want to revert to a table.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b60f7-111">Si vous renommez une table dans une source de données, suivez la procédure de remplacement d'une table et définissez la table renommée en tant que source de la table correspondante dans la vue DSV avant d'actualiser une vue DSV.</span><span class="sxs-lookup"><span data-stu-id="b60f7-111">If you rename a table in a data source, follow the steps for replacing a table and specify the renamed table as the source of the corresponding table in the DSV before you refresh a DSV.</span></span> <span data-ttu-id="b60f7-112">Le fait de mettre fin au processus de remplacement et de changement de nom permet de conserver la table, les références de la table et les relations de la table dans la vue DSV.</span><span class="sxs-lookup"><span data-stu-id="b60f7-112">Completing the replacement and renaming process preserves the table, the table's references, and the table's relationships in the DSV.</span></span> <span data-ttu-id="b60f7-113">Sinon, lorsque vous actualisez la vue DSV, la table renommée dans la source de données est considérée comme supprimée.</span><span class="sxs-lookup"><span data-stu-id="b60f7-113">Otherwise, when you refresh the DSV, a renamed table in data source is interpreted as being deleted.</span></span> <span data-ttu-id="b60f7-114">Pour plus d’informations, consultez [Actualiser le schéma dans une vue de source de données &#40;Analysis Services&#41;](refresh-the-schema-in-a-data-source-view-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="b60f7-114">For more information, see [Refresh the Schema in a Data Source View &#40;Analysis Services&#41;](refresh-the-schema-in-a-data-source-view-analysis-services.md).</span></span>  
  
##  <a name="replace-a-table-with-a-named-query"></a><a name="bkmk_nq"></a> <span data-ttu-id="b60f7-115">Remplacer une table par une requête nommée</span><span class="sxs-lookup"><span data-stu-id="b60f7-115">Replace a table with a named query</span></span>  
  
1.  <span data-ttu-id="b60f7-116">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], ouvrez le projet ou connectez-vous à la base de données qui contient la vue de source de données dans laquelle vous souhaitez remplacer une table ou une requête nommée.</span><span class="sxs-lookup"><span data-stu-id="b60f7-116">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the project or connect to the database that contains the data source view in which you want to replace a table or a named query.</span></span>  
  
2.  <span data-ttu-id="b60f7-117">Dans l’Explorateur de solutions, développez le dossier **Vues des sources de données** , puis double-cliquez sur la vue de source de données.</span><span class="sxs-lookup"><span data-stu-id="b60f7-117">In Solution Explorer, expand the **Data Source Views** folder, and then double-click the data source view.</span></span>  
  
3.  <span data-ttu-id="b60f7-118">Ouvrez la boîte de dialogue **Créer une requête nommée** .</span><span class="sxs-lookup"><span data-stu-id="b60f7-118">Open the **Create Named Query** dialog box.</span></span> <span data-ttu-id="b60f7-119">Dans le volet **Tables** ou **Diagramme** , cliquez avec le bouton droit sur la table que vous souhaitez remplacer, pointez sur **Remplacer la table** , puis cliquez sur **Par la nouvelle requête nommée**.</span><span class="sxs-lookup"><span data-stu-id="b60f7-119">In either **Tables** or **Diagram** pane, right-click the table that you wish to replace, point to **Replace Table** and then click **With New Named Query**.</span></span>  
  
4.  <span data-ttu-id="b60f7-120">Dans la boîte de dialogue **Créer une requête nommée** , définissez la requête nommée, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b60f7-120">In the **Create Named Query** dialog box, define the named query and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="b60f7-121">Enregistrez la vue de source de données modifiée.</span><span class="sxs-lookup"><span data-stu-id="b60f7-121">Save the modified data source view.</span></span>  
  
## <a name="replace-a-table-or-named-query-with-a-table"></a><span data-ttu-id="b60f7-122">Remplacer une table ou une requête nommée par une table</span><span class="sxs-lookup"><span data-stu-id="b60f7-122">Replace a table or named query with a table</span></span>  
  
1.  <span data-ttu-id="b60f7-123">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], ouvrez le projet ou connectez-vous à la base de données qui contient la vue de source de données dans laquelle vous souhaitez remplacer une table ou une requête nommée.</span><span class="sxs-lookup"><span data-stu-id="b60f7-123">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the project or connect to the database that contains the data source view in which you want to replace a table or a named query.</span></span>  
  
2.  <span data-ttu-id="b60f7-124">Dans l’Explorateur de solutions, développez le dossier **Vues des sources de données** , puis double-cliquez sur la vue de source de données.</span><span class="sxs-lookup"><span data-stu-id="b60f7-124">In Solution Explorer, expand the **Data Source Views** folder, and then double-click the data source view.</span></span>  
  
3.  <span data-ttu-id="b60f7-125">Ouvrez la boîte de dialogue **Remplacer la table par une autre table** .</span><span class="sxs-lookup"><span data-stu-id="b60f7-125">Open the **Replace Table with Other Table** dialog box.</span></span> <span data-ttu-id="b60f7-126">Dans le volet **Tables** ou **Diagramme** , cliquez avec le bouton droit sur la table ou la requête nommée que vous souhaitez remplacer, pointez sur **Remplacer la table** , puis cliquez sur **Par une autre table**.</span><span class="sxs-lookup"><span data-stu-id="b60f7-126">In either **Tables** or **Diagram** pane, right-click the table or named query that you wish to replace, point to **Replace Table** and then click **With Other Table**.</span></span>  
  
4.  <span data-ttu-id="b60f7-127">Dans la boîte de dialogue **Remplacer la table par une autre table** :</span><span class="sxs-lookup"><span data-stu-id="b60f7-127">In the **Replace Table with Other Table** dialog box:</span></span>  
  
    1.  <span data-ttu-id="b60f7-128">Dans la zone de liste déroulante **Source de données** , sélectionnez la source de données souhaitée.</span><span class="sxs-lookup"><span data-stu-id="b60f7-128">In the **DataSource** drop-down list box, select the desired data source</span></span>  
  
    2.  <span data-ttu-id="b60f7-129">Sélectionnez la table par laquelle vous souhaitez remplacer la table ou la requête nommée</span><span class="sxs-lookup"><span data-stu-id="b60f7-129">Select the table with which you wish to replace the table or named query</span></span>  
  
5.  <span data-ttu-id="b60f7-130">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b60f7-130">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="b60f7-131">Enregistrez la vue de source de données modifiée.</span><span class="sxs-lookup"><span data-stu-id="b60f7-131">Save the modified data source view.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b60f7-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b60f7-132">See Also</span></span>  
 [<span data-ttu-id="b60f7-133">Vues de sources de données dans les modèles multidimensionnels</span><span class="sxs-lookup"><span data-stu-id="b60f7-133">Data Source Views in Multidimensional Models</span></span>](data-source-views-in-multidimensional-models.md)  
  
  
