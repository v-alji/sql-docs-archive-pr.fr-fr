---
title: Filtrer des données dans une table (SSAS tabulaire) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.customfilterdb.f1
- sql12.asvs.bidtoolset.autofiltermenu.f1
- sql12.asvs.bidtoolset.notallitemsshowing.f1
ms.assetid: 3223059d-f525-4835-bf88-ebc195d9dbdc
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3f4003457df4068713e75e6bb5c0ab78c15ac03c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696199"
---
# <a name="filter-data-in-a-table-ssas-tabular"></a><span data-ttu-id="bda7f-102">Filtrer des données dans une table (SSAS Tabulaire)</span><span class="sxs-lookup"><span data-stu-id="bda7f-102">Filter Data in a Table (SSAS Tabular)</span></span>
  <span data-ttu-id="bda7f-103">Vous pouvez appliquer des filtres quand vous importez des données pour contrôler les lignes chargées dans une table.</span><span class="sxs-lookup"><span data-stu-id="bda7f-103">You can apply filters when you import data to control the rows that are loaded into a table.</span></span> <span data-ttu-id="bda7f-104">Une fois les données importées, vous ne pouvez pas supprimer de lignes individuelles.</span><span class="sxs-lookup"><span data-stu-id="bda7f-104">After you have imported the data, you cannot delete individual rows.</span></span> <span data-ttu-id="bda7f-105">Toutefois, vous pouvez appliquer des filtres personnalisés pour contrôler la façon dont les lignes sont affichées.</span><span class="sxs-lookup"><span data-stu-id="bda7f-105">However, you can apply custom filters to control the way that rows are displayed.</span></span> <span data-ttu-id="bda7f-106">Les lignes qui ne répondent pas à ces critères de filtrage sont masquées.</span><span class="sxs-lookup"><span data-stu-id="bda7f-106">Rows that do not meet the filtering criteria are hidden.</span></span> <span data-ttu-id="bda7f-107">Vous pouvez filtrer les données sur une ou plusieurs colonnes.</span><span class="sxs-lookup"><span data-stu-id="bda7f-107">You can filter by one or more columns.</span></span> <span data-ttu-id="bda7f-108">Les filtres sont additifs, ce qui signifie que chaque filtre supplémentaire est basé sur le filtre actuel et réduit davantage le sous-ensemble de données.</span><span class="sxs-lookup"><span data-stu-id="bda7f-108">Filters are additive, which means that each additional filter is based on the current filter and further reduces the subset of data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bda7f-109">La fenêtre d'aperçu de filtre limite le nombre de valeurs différentes affichées.</span><span class="sxs-lookup"><span data-stu-id="bda7f-109">The filter preview window limits the number of different values displayed.</span></span> <span data-ttu-id="bda7f-110">Si la limite est dépassée, un message s'affiche.</span><span class="sxs-lookup"><span data-stu-id="bda7f-110">If the limit is exceeded, a message is displayed.</span></span>  
  
### <a name="to-filter-data-based-on-column-values"></a><span data-ttu-id="bda7f-111">Pour filtrer des données selon les valeurs de colonne</span><span class="sxs-lookup"><span data-stu-id="bda7f-111">To filter data based on column values</span></span>  
  
1.  <span data-ttu-id="bda7f-112">Dans le générateur de modèles, sélectionnez une table, puis cliquez sur la flèche dans l'en-tête de la colonne par laquelle vous voulez effectuer le filtrage.</span><span class="sxs-lookup"><span data-stu-id="bda7f-112">In the model designer, select a table, and then click the arrow in the header of the column that you want to filter by.</span></span>  
  
2.  <span data-ttu-id="bda7f-113">Dans le menu Filtre automatique, effectuez l'une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="bda7f-113">In the AutoFilter menu, do one of the following:</span></span>  
  
    -   <span data-ttu-id="bda7f-114">Dans la liste de valeurs de colonne, sélectionnez ou désélectionnez une ou plusieurs valeurs sur lesquelles filtrer les données, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="bda7f-114">In the list of column values, select or clear one or more values to filter by, and then click **OK**.</span></span>  
  
         <span data-ttu-id="bda7f-115">Si le nombre de valeurs est très important, les éléments individuels peuvent ne pas être affichés dans la liste.</span><span class="sxs-lookup"><span data-stu-id="bda7f-115">If the number of values is extremely large, individual items might not be shown in the list.</span></span> <span data-ttu-id="bda7f-116">Le message « Trop d'éléments à afficher » sera alors affiché.</span><span class="sxs-lookup"><span data-stu-id="bda7f-116">Instead, you will see the message, "Too many items to show."</span></span>  
  
    -   <span data-ttu-id="bda7f-117">Cliquez sur **filtres de nombres** ou filtres de **texte** (selon le type de colonne), puis cliquez sur les commandes de l’opérateur de comparaison (comme **égal**à) ou cliquez sur **filtre personnalisé**.</span><span class="sxs-lookup"><span data-stu-id="bda7f-117">Click **Number Filters** or **Text Filters** (depending on the type of column), and then clicke of the comparison operator commands (such as **Equals**), or click **Custom Filter**.</span></span> <span data-ttu-id="bda7f-118">Dans la boîte de dialogue **Filtre personnalisé** , créez le filtre, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="bda7f-118">In the **Custom Filter** dialog box, create the filter, and then click **OK**.</span></span>  
  
### <a name="to-clear-a-filter-for-a-column"></a><span data-ttu-id="bda7f-119">Pour effacer le filtre d'une colonne</span><span class="sxs-lookup"><span data-stu-id="bda7f-119">To clear a filter for a column</span></span>  
  
1.  <span data-ttu-id="bda7f-120">Cliquez sur la flèche dans l'en-tête de la colonne dont vous souhaitez effacer un filtre.</span><span class="sxs-lookup"><span data-stu-id="bda7f-120">Click the arrow in the header of the column for which you want to clear a filter.</span></span>  
  
2.  <span data-ttu-id="bda7f-121">Cliquez sur \*\*effacer le \<Column Name> filtre de \*\*.</span><span class="sxs-lookup"><span data-stu-id="bda7f-121">Click **Clear Filter from \<Column Name>**.</span></span>  
  
### <a name="to-clear-all-filters-for-a-table"></a><span data-ttu-id="bda7f-122">Pour effacer tous les filtres d'une table</span><span class="sxs-lookup"><span data-stu-id="bda7f-122">To clear all filters for a table</span></span>  
  
1.  <span data-ttu-id="bda7f-123">Dans le générateur de modèles, sélectionnez la table dont vous souhaitez effacer les filtres.</span><span class="sxs-lookup"><span data-stu-id="bda7f-123">In the model designer, select the table for which you want to clear filters.</span></span>  
  
2.  <span data-ttu-id="bda7f-124">Cliquez sur le menu **Colonne** , puis sur **Effacer tous les filtres**.</span><span class="sxs-lookup"><span data-stu-id="bda7f-124">Click on the **Column** menu, and then click **Clear All Filters**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bda7f-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bda7f-125">See Also</span></span>  
 <span data-ttu-id="bda7f-126">[Filtrer et trier des données &#40;la&#41;tabulaire SSAS](../filter-and-sort-data-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="bda7f-126">[Filter and Sort Data &#40;SSAS Tabular&#41;](../filter-and-sort-data-ssas-tabular.md) </span></span>  
 <span data-ttu-id="bda7f-127">[Perspectives &#40;&#41;tabulaire SSAS](perspectives-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="bda7f-127">[Perspectives &#40;SSAS Tabular&#41;](perspectives-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="bda7f-128">Rôles &#40;SSAS Tabulaire&#41;</span><span class="sxs-lookup"><span data-stu-id="bda7f-128">Roles &#40;SSAS Tabular&#41;</span></span>](roles-ssas-tabular.md)  
  
  
