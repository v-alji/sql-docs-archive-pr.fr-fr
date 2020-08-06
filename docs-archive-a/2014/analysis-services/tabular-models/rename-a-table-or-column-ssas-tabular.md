---
title: Renommer une table ou une colonne (SSAS tabulaire) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.renametableorcolumn.f1
ms.assetid: 88061a39-c5aa-403d-a52b-7fdb365fc235
author: minewiskan
ms.author: owend
ms.openlocfilehash: d3a2e9a9f41434e64f9ec5ea2180861b459e8f97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706800"
---
# <a name="rename-a-table-or-column-ssas-tabular"></a><span data-ttu-id="b4c0f-102">Renommer une table ou une colonne (SSAS Tabulaire)</span><span class="sxs-lookup"><span data-stu-id="b4c0f-102">Rename a Table or Column (SSAS Tabular)</span></span>
  <span data-ttu-id="b4c0f-103">Vous pouvez modifier le nom d'une table pendant le processus d'importation en tapant un **Nom convivial** dans la page **Sélectionner des tables et des vues** de l' **Assistant Importation de table**.</span><span class="sxs-lookup"><span data-stu-id="b4c0f-103">You can change the name of a table during the import process by typing a **Friendly Name** in the **Select Tables and Views** page of the **Table Import Wizard**.</span></span> <span data-ttu-id="b4c0f-104">Vous pouvez également changer le nom des tables et des colonnes si vous importez des données en spécifiant une requête dans la page **Spécifier une requête SQL** de l' **Assistant Importation de table**.</span><span class="sxs-lookup"><span data-stu-id="b4c0f-104">You can also change table and column names if you import data by specifying a query on the **Specify a SQL Query** page of the **Table Import Wizard**.</span></span>  
  
 <span data-ttu-id="b4c0f-105">Une fois que vous avez ajouté les données au modèle, le nom (ou le titre) d'une table s'affiche sous l'onglet Table, au bas du générateur de modèles.</span><span class="sxs-lookup"><span data-stu-id="b4c0f-105">After you have added the data to the model, the name (or title) of a table appears on the table tab, at the bottom of the model designer.</span></span> <span data-ttu-id="b4c0f-106">Vous pouvez changer le nom de votre table afin de lui donner un nom plus approprié.</span><span class="sxs-lookup"><span data-stu-id="b4c0f-106">You can change the name of your table to give it a more appropriate name.</span></span> <span data-ttu-id="b4c0f-107">Vous pouvez également renommer une colonne après l’ajout de données au classeur.</span><span class="sxs-lookup"><span data-stu-id="b4c0f-107">You can also rename a column after the data has been added to the model.</span></span> <span data-ttu-id="b4c0f-108">Cette option est notamment importante lorsque vous avez importé des données à partir de plusieurs sources et souhaitez vous assurer que les colonnes dans les différentes tables ont des noms qui sont faciles à distinguer.</span><span class="sxs-lookup"><span data-stu-id="b4c0f-108">This option is especially important when you have imported data from multiple sources, and want to ensure that columns in different tables have names that are easy to distinguish.</span></span>  
  
### <a name="to-rename-a-table"></a><span data-ttu-id="b4c0f-109">Pour renommer une table</span><span class="sxs-lookup"><span data-stu-id="b4c0f-109">To rename a table</span></span>  
  
1.  <span data-ttu-id="b4c0f-110">Dans le générateur de modèles, cliquez avec le bouton droit sur l’onglet contenant la table que vous souhaitez renommer, puis sélectionnez **Renommer**.</span><span class="sxs-lookup"><span data-stu-id="b4c0f-110">In the model designer, right-click the tab that contains the table that you want to rename, and then click **Rename**.</span></span>  
  
2.  <span data-ttu-id="b4c0f-111">Tapez le nouveau nom.</span><span class="sxs-lookup"><span data-stu-id="b4c0f-111">Type the new name.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b4c0f-112">Vous pouvez modifier d'autres propriétés d'une table, notamment les mappages de colonnes et les informations de connexion, en utilisant la boîte de dialogue **Modifier les propriétés de la table** .</span><span class="sxs-lookup"><span data-stu-id="b4c0f-112">You can edit other properties of a table, including the connection information and column mappings, by using the **Edit Table Properties** dialog box.</span></span> <span data-ttu-id="b4c0f-113">Toutefois, vous ne pouvez pas changer son nom dans cette boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="b4c0f-113">However, you cannot change the name in this dialog box.</span></span>  
  
### <a name="to-rename-a-column"></a><span data-ttu-id="b4c0f-114">Pour renommer une colonne</span><span class="sxs-lookup"><span data-stu-id="b4c0f-114">To rename a column</span></span>  
  
1.  <span data-ttu-id="b4c0f-115">Dans le générateur de modèles, double-cliquez sur l’en-tête de la colonne que vous souhaitez renommer ou cliquez dessus avec le bouton droit et sélectionnez **Renommer la colonne** dans le menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="b4c0f-115">In the model designer, double-click the header of the column that you want to rename, or right-click the header and select **Rename Column** from the context menu.</span></span>  
  
2.  <span data-ttu-id="b4c0f-116">Tapez le nouveau nom.</span><span class="sxs-lookup"><span data-stu-id="b4c0f-116">Type the new name.</span></span>  
  
## <a name="naming-requirements-for-columns-and-tables"></a><span data-ttu-id="b4c0f-117">Exigences concernant l'affectation de noms pour les colonnes et les tables</span><span class="sxs-lookup"><span data-stu-id="b4c0f-117">Naming Requirements for Columns and Tables</span></span>  
 <span data-ttu-id="b4c0f-118">Les mots et caractères suivants ne peuvent pas être utilisés dans le nom d'une table ou d'une colonne :</span><span class="sxs-lookup"><span data-stu-id="b4c0f-118">The following words and characters cannot be used in the name of a table or column:</span></span>  
  
-   <span data-ttu-id="b4c0f-119">Espaces à gauche ou à droite</span><span class="sxs-lookup"><span data-stu-id="b4c0f-119">Leading or trailing spaces</span></span>  
  
-   <span data-ttu-id="b4c0f-120">Caractères de contrôle</span><span class="sxs-lookup"><span data-stu-id="b4c0f-120">Control characters</span></span>  
  
-   <span data-ttu-id="b4c0f-121">Les caractères suivants (qui ne sont pas valides dans les noms des objets Analysis Services) :.,; ':/ \\ \*|? &% $ ! + = () [] {}<></span><span class="sxs-lookup"><span data-stu-id="b4c0f-121">The following characters (which are not valid in the names of Analysis Services objects): .,;':/\\*|?&%$!+=()[]{}<></span></span>  
  
-   <span data-ttu-id="b4c0f-122">Mots clés réservés Analysis Services, notamment les opérateurs et les noms de fonction MDX et DMX.</span><span class="sxs-lookup"><span data-stu-id="b4c0f-122">Analysis Services reserved keywords, including Multidimensional Expressions (MDX) and Data Mining Extensions (DMX) function names and operators.</span></span>  
  
## <a name="effect-of-renaming-on-existing-tables-columns-and-calculations"></a><span data-ttu-id="b4c0f-123">Effet de l'attribution d'un nouveau nom sur les tables existantes, les colonnes et les calculs</span><span class="sxs-lookup"><span data-stu-id="b4c0f-123">Effect of Renaming on Existing Tables, Columns, and Calculations</span></span>  
 <span data-ttu-id="b4c0f-124">Chaque fois que vous modifiez le nom d'une table, vous modifiez le nom de l'objet de table sous-jacente, qui peut contenir plusieurs colonnes ou mesures.</span><span class="sxs-lookup"><span data-stu-id="b4c0f-124">Whenever you change the name of a table, you change the name of the underlying table object, which may contain multiple columns or measures.</span></span> <span data-ttu-id="b4c0f-125">Par conséquent, toutes les colonnes qui figurent dans la table, ainsi que toutes les relations qui utilisent la table, doivent être mises à jour pour utiliser le nouveau nom dans leurs définitions.</span><span class="sxs-lookup"><span data-stu-id="b4c0f-125">Therefore, any columns that are in the table, and any relationships that use the table, must be updated to use the new name in their definitions.</span></span> <span data-ttu-id="b4c0f-126">Cette mise à jour se produit automatiquement dans certains cas.</span><span class="sxs-lookup"><span data-stu-id="b4c0f-126">This update happens automatically in some cases.</span></span> <span data-ttu-id="b4c0f-127">Les mesures ne sont pas mises à jour automatiquement.</span><span class="sxs-lookup"><span data-stu-id="b4c0f-127">Measures are not updated automatically.</span></span>  
  
 <span data-ttu-id="b4c0f-128">De plus, tous les calculs qui utilisent la table renommée, ou qui utilisent des colonnes de la table que vous avez renommée, doivent également être mis à jour, et les données dérivées de ces calculs doivent être actualisées et recalculées.</span><span class="sxs-lookup"><span data-stu-id="b4c0f-128">Moreover, any calculations that use the renamed table, or that use columns from the renamed table, must also be updated, and the data derived from those calculations must be refreshed and recalculated.</span></span> <span data-ttu-id="b4c0f-129">Selon le nombre de tables et de calculs affectés, cette opération peut prendre quelque temps.</span><span class="sxs-lookup"><span data-stu-id="b4c0f-129">Depending on how many tables and calculations are affected, this can take some time to complete.</span></span> <span data-ttu-id="b4c0f-130">Par conséquent, le meilleur moment pour renommer des tables est soit pendant le processus d'importation, soit avant de commencer à générer des relations et des calculs complexes.</span><span class="sxs-lookup"><span data-stu-id="b4c0f-130">Therefore, the best time to rename tables is either during the import process, or before you start to build complex relationships and calculations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4c0f-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b4c0f-131">See Also</span></span>  
 <span data-ttu-id="b4c0f-132">[Tables et colonnes &#40;SSAS tabulaire&#41;](tables-and-columns-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="b4c0f-132">[Tables and Columns &#40;SSAS Tabular&#41;](tables-and-columns-ssas-tabular.md) </span></span>  
 <span data-ttu-id="b4c0f-133">[Importer à partir de PowerPivot &#40;&#41;tabulaires SSAS](import-from-power-pivot-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="b4c0f-133">[Import from PowerPivot &#40;SSAS Tabular&#41;](import-from-power-pivot-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="b4c0f-134">Importer à partir d’Analysis Services &#40;SSAS Tabulaire&#41;</span><span class="sxs-lookup"><span data-stu-id="b4c0f-134">Import from Analysis Services &#40;SSAS Tabular&#41;</span></span>](import-from-analysis-services-ssas-tabular.md)  
  
  
