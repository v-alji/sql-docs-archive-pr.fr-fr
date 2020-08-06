---
title: Fenêtre Résultats spatiaux
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: c2d5a477-6496-4d01-adee-7322ebdfadf3
author: rothja
ms.author: jroth
ms.openlocfilehash: 5e018ec9f016dfc51ed1bb055ba94abf12bc878f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710544"
---
# <a name="spatial-results-window"></a><span data-ttu-id="84153-102">Fenêtre Résultats spatiaux</span><span class="sxs-lookup"><span data-stu-id="84153-102">Spatial Results Window</span></span>
  <span data-ttu-id="84153-103">La fenêtre **Résultats spatiaux** propose des outils de mappage visuel permettant d'afficher des données spatiales.</span><span class="sxs-lookup"><span data-stu-id="84153-103">The **Spatial results** window provides visual mapping tools for viewing spatial data.</span></span> <span data-ttu-id="84153-104">Pour afficher des résultats spatiaux, vos résultats de requête doivent inclure une colonne spatiale avec des données géométriques ou géographiques.</span><span class="sxs-lookup"><span data-stu-id="84153-104">To view spatial results, your query results must include a spatial column with either geometry or geography data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="84153-105">La fenêtre **Résultats spatiaux** est uniquement disponible si vos résultats sont retournés dans une grille dans la fenêtre **Résultats** .</span><span class="sxs-lookup"><span data-stu-id="84153-105">The **Spatial results** window is only available if your results are returned to a grid in the **Results** window.</span></span> <span data-ttu-id="84153-106">Si vous spécifiez que les résultats doivent être retournés sous forme de texte, cette fenêtre n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="84153-106">If you specify that your results are returned as text, this window is not available.</span></span>  
  
## <a name="options"></a><span data-ttu-id="84153-107">Options</span><span class="sxs-lookup"><span data-stu-id="84153-107">Options</span></span>  
 <span data-ttu-id="84153-108">**Sélectionner la colonne spatiale**</span><span class="sxs-lookup"><span data-stu-id="84153-108">**Select spatial column**</span></span>  
 <span data-ttu-id="84153-109">À partir des colonnes spatiales figurant dans les résultats de requête, spécifiez la colonne spatiale à afficher.</span><span class="sxs-lookup"><span data-stu-id="84153-109">Specify the spatial column you want to view from the spatial columns in the query results.</span></span> <span data-ttu-id="84153-110">Vous ne pouvez sélectionner qu'une seule colonne à la fois.</span><span class="sxs-lookup"><span data-stu-id="84153-110">Only one column can be selected at a time.</span></span>  
  
 <span data-ttu-id="84153-111">**Sélectionner la colonne d'étiquette**</span><span class="sxs-lookup"><span data-stu-id="84153-111">**Select label column**</span></span>  
 <span data-ttu-id="84153-112">À partir des colonnes retournées dans les résultats de requête, spécifiez la colonne non spatiale qui servira à étiqueter les données spatiales.</span><span class="sxs-lookup"><span data-stu-id="84153-112">Specify the non-spatial column from the columns returned in the query results to label the spatial data.</span></span> <span data-ttu-id="84153-113">Vous ne pouvez sélectionner qu'une seule colonne à la fois.</span><span class="sxs-lookup"><span data-stu-id="84153-113">Only one column can be selected at a time.</span></span>  
  
 <span data-ttu-id="84153-114">Cette option n'est pas disponible lorsque des instances de point seulement sont retournées dans une requête.</span><span class="sxs-lookup"><span data-stu-id="84153-114">This option is not available when only point instances are returned in a query.</span></span>  
  
 <span data-ttu-id="84153-115">**Sélectionner la projection**</span><span class="sxs-lookup"><span data-stu-id="84153-115">**Select projection**</span></span>  
 <span data-ttu-id="84153-116">Affichez les données géographiques selon l'une des quatre projections proposées : équirectangulaire, de Mercator, de Robinson ou de Bonne.</span><span class="sxs-lookup"><span data-stu-id="84153-116">Display geography data in one of four projections: Equirectangular, Mercator, Robinson, or Bonne.</span></span>  
  
 <span data-ttu-id="84153-117">Cette option n'est pas disponible pour les données géométriques.</span><span class="sxs-lookup"><span data-stu-id="84153-117">This option is not available for geometry data.</span></span>  
  
 <span data-ttu-id="84153-118">**Zoom**</span><span class="sxs-lookup"><span data-stu-id="84153-118">**Zoom**</span></span>  
 <span data-ttu-id="84153-119">Ajustez l'affichage du mappage sur une échelle exponentielle.</span><span class="sxs-lookup"><span data-stu-id="84153-119">Adjust the map display on an exponential scale.</span></span>  
  
 <span data-ttu-id="84153-120">**Afficher le quadrillage**</span><span class="sxs-lookup"><span data-stu-id="84153-120">**Show grid lines**</span></span>  
 <span data-ttu-id="84153-121">Activez/désactivez le quadrillage des coordonnées.</span><span class="sxs-lookup"><span data-stu-id="84153-121">Toggle coordinate gridlines on or off.</span></span>  
  
 <span data-ttu-id="84153-122">Pour les formes polygonales, l'étiquette est affichée uniquement lorsque la forme est suffisamment grande pour contenir le texte d'étiquette.</span><span class="sxs-lookup"><span data-stu-id="84153-122">For polygon shapes, the label is displayed only when the shape is large enough to hold the label text.</span></span> <span data-ttu-id="84153-123">Pour afficher les étiquettes des petites formes, ajustez le zoom.</span><span class="sxs-lookup"><span data-stu-id="84153-123">To display labels for small shapes, adjust the zoom.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="84153-124">Il est impossible d'étiqueter les instances de point.</span><span class="sxs-lookup"><span data-stu-id="84153-124">Point instances cannot be labeled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84153-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="84153-125">See Also</span></span>  
 <span data-ttu-id="84153-126">[Afficher des données spatiales dans l'Explorateur d'objets](view-spatial-data-in-object-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="84153-126">[View Spatial Data in Object Explorer](view-spatial-data-in-object-explorer.md) </span></span>  
 <span data-ttu-id="84153-127">[Données spatiales &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="84153-127">[Spatial Data &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md) </span></span>  
 <span data-ttu-id="84153-128">[Éditeur de requête du moteur de base de données &#40;SQL Server Management Studio&#41;](database-engine-query-editor-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="84153-128">[Database Engine Query Editor &#40;SQL Server Management Studio&#41;](database-engine-query-editor-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="84153-129">Éditeurs de texte et de requête &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="84153-129">Query and Text Editors &#40;SQL Server Management Studio&#41;</span></span>](query-and-text-editors-sql-server-management-studio.md)  
  
  
