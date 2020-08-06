---
title: Afficher les datasets masqués pour les valeurs de paramètres des données multidimensionnelles (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: eb01c4ca-4fd6-4629-b595-f0d2565915df
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6f9c005b6e7c8927316c19a3302e32f4407f9885
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710215"
---
# <a name="show-hidden-datasets-for-parameter-values-for-multidimensional-data-report-builder-and-ssrs"></a><span data-ttu-id="a706a-102">Afficher des datasets masqués pour les valeurs de paramètres des données multidimensionnelles (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="a706a-102">Show Hidden Datasets for Parameter Values for Multidimensional Data (Report Builder and SSRS)</span></span>
  <span data-ttu-id="a706a-103">Votre rapport peut inclure des datasets générés automatiquement (aussi appelés datasets masqués) qui n'apparaissent pas par défaut dans le volet des données de rapport.</span><span class="sxs-lookup"><span data-stu-id="a706a-103">Your report might include automatically-generated datasets (also known as hidden datasets) that do not appear by default in the Report Data pane.</span></span> <span data-ttu-id="a706a-104">La création de ces datasets s'effectue de plusieurs façons :</span><span class="sxs-lookup"><span data-stu-id="a706a-104">These datasets are created in the following ways:</span></span>  
  
-   <span data-ttu-id="a706a-105">Dans certains concepteurs de requêtes pour des bases de données multidimensionnelles, vous pouvez spécifier des champs sur lesquels appliquer un filtre dans la zone de filtre du volet de requête, et indiquer si vous voulez ou non créer un paramètre de requête pour le filtre.</span><span class="sxs-lookup"><span data-stu-id="a706a-105">In some query designers for multidimensional databases, you can specify fields to filter on in the filter area of the query pane, and select whether to create a query parameter for the filter.</span></span> <span data-ttu-id="a706a-106">Si vous sélectionnez l'option de paramètre, des datasets de rapport sont automatiquement créés pour fournir des valeurs valides pour le paramètre de rapport.</span><span class="sxs-lookup"><span data-stu-id="a706a-106">If you select the parameter option, report datasets are automatically created to provide valid values for the report parameter.</span></span>  
  
-   <span data-ttu-id="a706a-107">Si vous importez une requête basée sur des bases de données multidimensionnelles, vous pouvez également inclure des datasets masqués dans votre rapport.</span><span class="sxs-lookup"><span data-stu-id="a706a-107">If you import a query based on multidimensional databases, you might also include hidden datasets in your report.</span></span>  
  
 <span data-ttu-id="a706a-108">Les datasets masqués ne sont pas accessibles à partir d'un Assistant.</span><span class="sxs-lookup"><span data-stu-id="a706a-108">Hidden datasets are not available to use from a wizard.</span></span>  
  
 <span data-ttu-id="a706a-109">Vous pouvez modifier la vue dans le volet des données de rapport pour afficher tous les datasets dans le rapport.</span><span class="sxs-lookup"><span data-stu-id="a706a-109">You can change the view in the Report Data pane to display all datasets in the report.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-display-hidden-datasets"></a><span data-ttu-id="a706a-110">Pour afficher les datasets masqués</span><span class="sxs-lookup"><span data-stu-id="a706a-110">To display hidden datasets</span></span>  
  
-   <span data-ttu-id="a706a-111">Dans le volet des données de rapport, cliquez avec le bouton droit sur le dossier Datasets, puis cliquez sur **Afficher les datasets masqués**.</span><span class="sxs-lookup"><span data-stu-id="a706a-111">In the Report Data pane, right-click the Datasets folder, and then click **Show Hidden Datasets**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a706a-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a706a-112">See Also</span></span>  
 <span data-ttu-id="a706a-113">[Concepteurs de requêtes &#40;Générateur de rapports&#41;](../query-designers-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="a706a-113">[Query Designers &#40;Report Builder&#41;](../query-designers-report-builder.md) </span></span>  
 <span data-ttu-id="a706a-114">[Concepteurs de requêtes Reporting Services](../reporting-services-query-designers.md) </span><span class="sxs-lookup"><span data-stu-id="a706a-114">[Reporting Services Query Designers](../reporting-services-query-designers.md) </span></span>  
 <span data-ttu-id="a706a-115">[Datasets incorporés dans le rapport et datasets partagés &#40;Générateur de rapports et SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a706a-115">[Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="a706a-116">Ajouter des données à un rapport &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="a706a-116">Add Data to a Report &#40;Report Builder and SSRS&#41;</span></span>](report-datasets-ssrs.md)  
  
  
