---
title: Afficher des données spatiales dans l'Explorateur d'objets
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 59cca562-e3f5-4257-b868-adcbcc0142cc
author: rothja
ms.author: jroth
ms.openlocfilehash: 881adf69ee83ee4b7536afae0b190fbec90f132c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610576"
---
# <a name="view-spatial-data-in-object-explorer"></a><span data-ttu-id="8f356-102">Afficher des données spatiales dans l'Explorateur d'objets</span><span class="sxs-lookup"><span data-stu-id="8f356-102">View Spatial Data in Object Explorer</span></span>
  <span data-ttu-id="8f356-103">La fenêtre **Résultats spatiaux** de l'Éditeur de requête propose des outils de mappage visuel permettant d'afficher des résultats de données spatiales en plus des données affichées au format grille dans la fenêtre **Résultats** .</span><span class="sxs-lookup"><span data-stu-id="8f356-103">The **Spatial results** window in Query Editor provides visual mapping tools for viewing spatial data results in addition to the data displayed in grid format in the **Results** window.</span></span> <span data-ttu-id="8f356-104">Pour afficher des données spatiales dans la fenêtre **Résultats spatiaux** , vos résultats de requête doivent contenir au moins une colonne de données spatiales avec des données géométriques ou géographiques.</span><span class="sxs-lookup"><span data-stu-id="8f356-104">To display spatial data in the **Spatial Results** window, your query results must contain at least one spatial data column with either geometry or geography data.</span></span>  
  
### <a name="to-view-spatial-data-in-the-spatial-results-window"></a><span data-ttu-id="8f356-105">Pour afficher des données spatiales dans la fenêtre Résultats spatiaux</span><span class="sxs-lookup"><span data-stu-id="8f356-105">To view spatial data in the Spatial results window</span></span>  
  
1.  <span data-ttu-id="8f356-106">Dans l'Éditeur de requête, cliquez sur l'onglet **Résultats spatiaux** .</span><span class="sxs-lookup"><span data-stu-id="8f356-106">In Query Editor, click the **Spatial results** tab.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8f356-107">Cette fenêtre n'est pas disponible si vos résultats de requête ne contiennent pas de données spatiales ou si vous spécifiez que les résultats doivent être retournés sous forme de texte.</span><span class="sxs-lookup"><span data-stu-id="8f356-107">This window is not available if your query results do not contain spatial data or if you specify that your results are returned as text.</span></span>  
  
2.  <span data-ttu-id="8f356-108">Sélectionnez la colonne à afficher dans la liste **Sélectionner la colonne spatiale** .</span><span class="sxs-lookup"><span data-stu-id="8f356-108">Select the column you want to view from the **Select spatial column** list.</span></span> <span data-ttu-id="8f356-109">Si votre table ne contient qu'une seule colonne spatiale, celle-ci constitue l'option par défaut dans la liste.</span><span class="sxs-lookup"><span data-stu-id="8f356-109">If there is only one spatial column in your table, this column is the default option in the list.</span></span>  
  
3.  <span data-ttu-id="8f356-110">Sélectionnez la colonne non spatiale à utiliser comme étiquettes de données dans la liste **Sélectionner la colonne d’étiquette** .</span><span class="sxs-lookup"><span data-stu-id="8f356-110">Select the non-spatial column you want to use as data labels from the **Select label columns** list.</span></span>  
  
4.  <span data-ttu-id="8f356-111">Sélectionnez la projection voulue pour les données géographiques dans la liste **Sélectionner la projection** .</span><span class="sxs-lookup"><span data-stu-id="8f356-111">Select the projection you want for geography data from the **Select projection** list.</span></span> <span data-ttu-id="8f356-112">La projection par défaut est équirectangulaire ; les autres projections possibles sont les projections de Mercator, de Robinson ou de Bonne.</span><span class="sxs-lookup"><span data-stu-id="8f356-112">The default projection is Equirectangular; other projections available are Mercator, Robinson, or Bonne.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8f356-113">**Sélectionner la projection** n’est pas disponible si votre colonne spatiale contient des données géométriques.</span><span class="sxs-lookup"><span data-stu-id="8f356-113">**Select projection** is not available if your spatial column contains geometry data.</span></span>  
  
5.  <span data-ttu-id="8f356-114">Ajustez le curseur **Zoom** pour augmenter la taille visuelle des éléments mappés.</span><span class="sxs-lookup"><span data-stu-id="8f356-114">Adjust the **Zoom** slider to increase the visual size of mapped elements.</span></span> <span data-ttu-id="8f356-115">Pour les formes polygonales, l'étiquette est visible uniquement lorsque la forme est suffisamment grande pour contenir le texte d'étiquette.</span><span class="sxs-lookup"><span data-stu-id="8f356-115">For polygon shapes, the label is visible only when the shape is large enough to hold the label text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f356-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8f356-116">See Also</span></span>  
 <span data-ttu-id="8f356-117">[Fenêtre Résultats spatiaux](spatial-results-window.md) </span><span class="sxs-lookup"><span data-stu-id="8f356-117">[Spatial Results Window](spatial-results-window.md) </span></span>  
 <span data-ttu-id="8f356-118">[Éditeur de requête du moteur de base de données &#40;SQL Server Management Studio&#41;](database-engine-query-editor-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="8f356-118">[Database Engine Query Editor &#40;SQL Server Management Studio&#41;](database-engine-query-editor-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="8f356-119">Éditeurs de texte et de requête &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="8f356-119">Query and Text Editors &#40;SQL Server Management Studio&#41;</span></span>](query-and-text-editors-sql-server-management-studio.md)  
  
  
