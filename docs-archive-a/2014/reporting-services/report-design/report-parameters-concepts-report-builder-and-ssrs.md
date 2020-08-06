---
title: Concept des paramètres de rapport (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: b0aa2159-4e49-4713-8824-5ef9a9edbc62
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4b740362daea83b50a62f0b4453ce818ab21ace7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697531"
---
# <a name="report-parameters-concept-report-builder-and-ssrs"></a><span data-ttu-id="00191-102">Concept des paramètres de rapport (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="00191-102">Report Parameters Concept (Report Builder and SSRS)</span></span>
  <span data-ttu-id="00191-103">Vous pouvez ajouter des paramètres à un rapport pour lier des rapports connexes, pour contrôler l'apparence d'un rapport, pour filtrer les données du rapport, ou pour limiter l'étendue d'un rapport à des utilisateurs ou des emplacements spécifiques.</span><span class="sxs-lookup"><span data-stu-id="00191-103">You can add parameters to a report to link related reports, to control the report appearance, to filter report data, or to narrow the scope of a report to specific users or locations.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
 <span data-ttu-id="00191-104">Les paramètres de rapport sont créés des manières suivantes :</span><span class="sxs-lookup"><span data-stu-id="00191-104">Report parameters are created in the following ways:</span></span>  
  
-   <span data-ttu-id="00191-105">Automatiquement, lorsque vous définissez la requête de dataset qui contient des variables de requête.</span><span class="sxs-lookup"><span data-stu-id="00191-105">Automatically, when you define dataset query that contains query variables.</span></span> <span data-ttu-id="00191-106">Pour chaque variable de requête, un paramètre de requête de dataset et un paramètre de rapport correspondants portant les mêmes noms sont créés.</span><span class="sxs-lookup"><span data-stu-id="00191-106">For each query variable, a corresponding dataset query parameter and report parameter with the same names are created.</span></span> <span data-ttu-id="00191-107">Un paramètre de requête peut être une référence à une variable de requête ou à un paramètre d'entrée pour une procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="00191-107">A query parameter can be a reference to a query variable or to an input parameter for a stored procedure.</span></span>  
  
-   <span data-ttu-id="00191-108">Automatiquement, lorsque vous ajoutez une référence à un dataset partagé qui contient des paramètres de requête.</span><span class="sxs-lookup"><span data-stu-id="00191-108">Automatically, when you add a reference to a shared dataset that contains query parameters.</span></span>  
  
-   <span data-ttu-id="00191-109">Manuellement, lorsque vous créez des paramètres de rapport dans le volet Données du rapport.</span><span class="sxs-lookup"><span data-stu-id="00191-109">Manually, when you create report parameters in the Report Data pane.</span></span> <span data-ttu-id="00191-110">Les paramètres font partie des collections intégrées que vous pouvez inclure dans une expression dans un rapport.</span><span class="sxs-lookup"><span data-stu-id="00191-110">Parameters are one of the built-in collections that you can include in an expression in a report.</span></span> <span data-ttu-id="00191-111">Étant donné que les expressions sont utilisées pour définir des valeurs dans l'ensemble d'une définition de rapport, vous pouvez utiliser des paramètres pour contrôler l'apparence du rapport ou pour transmettre des valeurs aux sous-rapports ou aux rapports connexes qui utilisent également des paramètres.</span><span class="sxs-lookup"><span data-stu-id="00191-111">Because expressions are used to define values throughout a report definition, you can use parameters to control report appearance or to pass values to related subreports or reports that also use parameters.</span></span>  
  
 <span data-ttu-id="00191-112">Pour plus d'informations, consultez [Paramètres de rapport &#40;Générateur de rapports et Concepteur de rapports&#41;](report-parameters-report-builder-and-report-designer.md).</span><span class="sxs-lookup"><span data-stu-id="00191-112">For more information, see [Report Parameters &#40;Report Builder and Report Designer&#41;](report-parameters-report-builder-and-report-designer.md).</span></span>  
  
 <span data-ttu-id="00191-113">Les paramètres sont fréquemment utilisés pour filtrer des données de rapport à la fois avant et après le retour des données sur le rapport.</span><span class="sxs-lookup"><span data-stu-id="00191-113">Parameters are frequently used to filter report data both before and after the data is returned to the report.</span></span> <span data-ttu-id="00191-114">Pour plus d’informations, consultez [Filtrer, regrouper et trier des données &#40;Générateur de rapports et SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="00191-114">For more information, see [Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="00191-115">Lorsque vous concevez un rapport, les paramètres de rapport sont enregistrés dans la définition de rapport.</span><span class="sxs-lookup"><span data-stu-id="00191-115">When you design a report, report parameters are saved in the report definition.</span></span> <span data-ttu-id="00191-116">Lorsque vous publiez un rapport, les paramètres de rapport sont enregistrés et gérés indépendamment de la définition de rapport.</span><span class="sxs-lookup"><span data-stu-id="00191-116">When you publish a report, report parameters are saved and managed separately from the report definition.</span></span> <span data-ttu-id="00191-117">Après avoir enregistré le rapport sur le serveur de rapports, vous pouvez effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="00191-117">After you save the report to the report server, you can do the following:</span></span>  
  
-   <span data-ttu-id="00191-118">Modifiez des valeurs de paramètres du rapport directement sur le serveur de rapports, indépendamment de la définition de rapport.</span><span class="sxs-lookup"><span data-stu-id="00191-118">Change report parameter values directly on the report server independently from the report definition.</span></span>  
  
-   <span data-ttu-id="00191-119">Créez plusieurs rapports liés dans lesquels chaque rapport lié est un lien vers la définition de rapport avec un jeu distinct de valeurs de paramètres pouvant être gérées indépendamment sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="00191-119">Create multiple linked reports in which each linked report is a link to the report definition with a separate set of parameter values that can be managed independently on the report server.</span></span>  
  
 <span data-ttu-id="00191-120">Si vous projetez de créer des instantanés de rapport, des historiques ou des abonnements à un rapport publié, vous devez comprendre l'effet des paramètres de rapport sur les exigences de conception du rapport.</span><span class="sxs-lookup"><span data-stu-id="00191-120">If you plan to create report snapshots, histories, or subscriptions to a published report, you must understand how report parameters affect the design requirements for the report.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00191-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="00191-121">See Also</span></span>  
 <span data-ttu-id="00191-122">[Concepts de création de rapports &#40;Générateur de rapports et SSRS&#41;](report-authoring-concepts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="00191-122">[Report Authoring Concepts &#40;Report Builder and SSRS&#41;](report-authoring-concepts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="00191-123">[Datasets incorporés dans le rapport et datasets partagés &#40;Générateur de rapports et SSRS&#41;](../report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="00191-123">[Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](../report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="00191-124">Didacticiel : Ajouter un paramètre à un rapport &#40;Générateur de rapports&#41;</span><span class="sxs-lookup"><span data-stu-id="00191-124">Tutorial: Add a Parameter to Your Report &#40;Report Builder&#41;</span></span>](../tutorial-add-a-parameter-to-your-report-report-builder.md)  
  
  
