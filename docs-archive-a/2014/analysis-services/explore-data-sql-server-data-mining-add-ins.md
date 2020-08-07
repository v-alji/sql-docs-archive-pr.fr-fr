---
title: Explorer des données (SQL Server des compléments d’exploration de données) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data preparation
- histogram [data mining]
- data visualization
ms.assetid: 714845a9-4c27-461a-9ba3-149e1e818386
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2572c11e92dcf99dfa3adf661603e8f65f05116e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703391"
---
# <a name="explore-data-sql-server-data-mining-add-ins"></a><span data-ttu-id="328bd-102">Explorer des données (Compléments d'exploration de données SQL Server)</span><span class="sxs-lookup"><span data-stu-id="328bd-102">Explore Data (SQL Server Data Mining Add-ins)</span></span>
  <span data-ttu-id="328bd-103">![Assistant Explorer les données](media/dmc-explore.gif "Assistant Explorer les données")</span><span class="sxs-lookup"><span data-stu-id="328bd-103">![Explore Data wizard](media/dmc-explore.gif "Explore Data wizard")</span></span>  
  
 <span data-ttu-id="328bd-104">L’Assistant **exploration des données** vous aide à comprendre le type et la quantité de données de votre table de données.</span><span class="sxs-lookup"><span data-stu-id="328bd-104">The **Explore Data** wizard helps you understand the type and amount of data in your data table.</span></span> <span data-ttu-id="328bd-105">Cet Assistant représente sous forme graphique la distribution et les valeurs des colonnes sélectionnées, une colonne à la fois.</span><span class="sxs-lookup"><span data-stu-id="328bd-105">The wizard graphs the distribution and values for the selected columns, one column at a time.</span></span> <span data-ttu-id="328bd-106">Vous pouvez ensuite essayer de changer la manière de regrouper les données ou copier le graphique qui représente le contenu dans un classeur Excel pour consultation ultérieure.</span><span class="sxs-lookup"><span data-stu-id="328bd-106">You can then experiment with changing the way that data is grouped, or copy the chart that shows the content to an Excel workbook for review.</span></span>  
  
 <span data-ttu-id="328bd-107">Si vos données contiennent des données numériques continues, vous pouvez alterner entre ces deux vues :</span><span class="sxs-lookup"><span data-stu-id="328bd-107">If your data contains continuous numeric data, you can toggle between these two views:</span></span>  
  
-   <span data-ttu-id="328bd-108">**Graphique en courbes.**</span><span class="sxs-lookup"><span data-stu-id="328bd-108">**Line graph.**</span></span> <span data-ttu-id="328bd-109">Ce graphique affiche les valeurs de données sur l'axe X et le nombre de cas sur l'axe Y.</span><span class="sxs-lookup"><span data-stu-id="328bd-109">This graph charts the data values on the X-axis and the number of cases on the y-axis.</span></span>  
  
-   <span data-ttu-id="328bd-110">**Graphique à barres.**</span><span class="sxs-lookup"><span data-stu-id="328bd-110">**Bar chart.**</span></span> <span data-ttu-id="328bd-111">Ce graphique regroupe les valeurs selon le nombre de cas pour chaque valeur.</span><span class="sxs-lookup"><span data-stu-id="328bd-111">This graph groups values by the number of cases for each value.</span></span>  
  
 <span data-ttu-id="328bd-112">Lorsque l'Assistant recherche des groupes dans les données, il utilise la distribution réelle des valeurs de données.</span><span class="sxs-lookup"><span data-stu-id="328bd-112">When the wizard finds groups in the data, it uses the actual distribution of data values.</span></span> <span data-ttu-id="328bd-113">Par conséquent, le graphique à barres ne montre pas les marqueurs standard de l'axe numérique entier tels que 10 ou 100.</span><span class="sxs-lookup"><span data-stu-id="328bd-113">Therefore, the bar chart does not show typical whole-number numeric axis markers such as 10 or 100.</span></span> <span data-ttu-id="328bd-114">À la place, les plages affichées dans le graphique à barres peuvent ressembler à 43521-55603 (pour la colonne de revenus).</span><span class="sxs-lookup"><span data-stu-id="328bd-114">Instead, the ranges shown in the bar chart might be something like 43521-55603 (for the Income column).</span></span>  
  
 <span data-ttu-id="328bd-115">Si vous souhaitez regrouper vos données dans d'autres plages, vous devez le faire dans Excel avant d'analyser les données.</span><span class="sxs-lookup"><span data-stu-id="328bd-115">If you want to group your data into other ranges, you should do this in Excel before analyzing the data.</span></span> <span data-ttu-id="328bd-116">Ou vous pouvez réétiqueter les données à l’aide de l’Assistant [réétiqueter](relabel-sql-server-data-mining-add-ins.md) .</span><span class="sxs-lookup"><span data-stu-id="328bd-116">Or, you can relabel the data by using the [Relabel](relabel-sql-server-data-mining-add-ins.md) wizard.</span></span>  
  
## <a name="using-the-explore-data-wizard"></a><span data-ttu-id="328bd-117">Utilisation de l'Assistant Explorer les données</span><span class="sxs-lookup"><span data-stu-id="328bd-117">Using the Explore Data Wizard</span></span>  
  
1.  <span data-ttu-id="328bd-118">Dans le ruban **exploration de données** , cliquez sur Explorer les **données**.</span><span class="sxs-lookup"><span data-stu-id="328bd-118">In the **Data Mining** ribbon, click **Explore Data**.</span></span>  
  
2.  <span data-ttu-id="328bd-119">Dans la boîte de dialogue **Sélectionner une source** , sélectionnez la table ou la plage de cellules qui contient vos données.</span><span class="sxs-lookup"><span data-stu-id="328bd-119">In the **Select Source** dialog box, select the table or range of cells that contains your data.</span></span>  
  
3.  <span data-ttu-id="328bd-120">Dans la boîte de dialogue **Sélectionner une colonne** , choisissez la colonne à analyser, parmi les exemples de données affichés dans le volet.</span><span class="sxs-lookup"><span data-stu-id="328bd-120">In the **Select Column** dialog box, choose the column to analyze, from the sample data displayed in the pane.</span></span>  
  
4.  <span data-ttu-id="328bd-121">Dans la boîte de dialogue **Explorer les données** , choisissez les types de graphiques pour l’affichage de la distribution des données.</span><span class="sxs-lookup"><span data-stu-id="328bd-121">In the **Explore Data** dialog box, choose the chart types for displaying the distribution of data.</span></span>  
  
5.  <span data-ttu-id="328bd-122">Le cas échéant, ajoutez de nouvelles colonnes aux données, modifiez la segmentation des données ou copiez le graphique dans Excel.</span><span class="sxs-lookup"><span data-stu-id="328bd-122">Optionally, you can add new columns to the data, change the way that the data is segmented, or copy the chart to Excel.</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="328bd-123">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="328bd-123">Requirements</span></span>  
 <span data-ttu-id="328bd-124">Pour utiliser l’Assistant **Explorer les données** , vos données doivent se trouver dans une table de données Excel.</span><span class="sxs-lookup"><span data-stu-id="328bd-124">To use the **Explore Data** wizard, your data must be in an Excel data table.</span></span>   
  
## <a name="see-also"></a><span data-ttu-id="328bd-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="328bd-125">See Also</span></span>  
 [<span data-ttu-id="328bd-126">Liste de vérification : préparation pour l'exploration de données</span><span class="sxs-lookup"><span data-stu-id="328bd-126">Checklist of Preparation for Data Mining</span></span>](checklist-of-preparation-for-data-mining.md)  
  
  
