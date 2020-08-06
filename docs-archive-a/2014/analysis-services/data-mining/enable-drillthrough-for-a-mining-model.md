---
title: Activer l’extraction pour un modèle d’exploration de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining [Analysis Services], how-to topics
- drillthrough [Analysis Services]
ms.assetid: 4fa44f60-ef9a-4b59-98c0-c0baf1195c8e
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0a6adfc389776f91132e527130f50f61c9783d9f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601167"
---
# <a name="enable-drillthrough-for-a-mining-model"></a><span data-ttu-id="7f20a-102">Activer l'extraction pour un modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="7f20a-102">Enable Drillthrough for a Mining Model</span></span>
  <span data-ttu-id="7f20a-103">Si vous avez activé l'extraction pour un modèle d'exploration de données, lorsque vous parcourez le modèle, vous pouvez extraire des informations détaillées sur les cas utilisés pour créer le modèle.</span><span class="sxs-lookup"><span data-stu-id="7f20a-103">If you have enabled drillthrough for a mining model, when you browse the model you can retrieve detailed information about the cases that were used to create the model.</span></span> <span data-ttu-id="7f20a-104">Pour consulter cette information, vous devez disposer des autorisations nécessaires et la structure doit déjà avoir été traitée.</span><span class="sxs-lookup"><span data-stu-id="7f20a-104">To view this information, you must have the necessary permissions, and the structure must have already been processed.</span></span>  
  
 <span data-ttu-id="7f20a-105">**Autorisations** Pour qu’un utilisateur extraie les données d’un modèle ou d’une structure, il doit être membre d’un rôle qui a les autorisations [AllowDrillThrough](https://docs.microsoft.com/bi-reference/assl/properties/allowdrillthrough-element-assl) pour le modèle ou la structure d’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="7f20a-105">**Permissions** For a user to drill through to either model data or structure data, the user must be a member of a role that has [AllowDrillThrough](https://docs.microsoft.com/bi-reference/assl/properties/allowdrillthrough-element-assl) permissions on the mining model or mining structure.</span></span> <span data-ttu-id="7f20a-106">Les autorisations d'extraction sont définies séparément sur la structure et le modèle.</span><span class="sxs-lookup"><span data-stu-id="7f20a-106">Drillthrough permissions are set separately on the structure and model.</span></span>  
  
-   <span data-ttu-id="7f20a-107">Les autorisations d'extraction sur le modèle vous permettent d'extraire à partir du modèle, même si vous n'avez pas d'autorisations sur la structure.</span><span class="sxs-lookup"><span data-stu-id="7f20a-107">Drillthrough permissions on the model enable you to drill through from the model, even if you do not have permissions on the structure.</span></span>  
  
-   <span data-ttu-id="7f20a-108">Les autorisations d’extraction sur la structure permettent en outre d’inclure des colonnes de structure dans les requêtes d’extraction à partir du modèle, à l’aide de la fonction [StructureColumn &#40;DMX&#41;](/sql/dmx/structurecolumn-dmx).</span><span class="sxs-lookup"><span data-stu-id="7f20a-108">Drillthrough permissions on the structure provide the additional ability to include structure columns in drillthrough queries from the model, by using the [StructureColumn &#40;DMX&#41;](/sql/dmx/structurecolumn-dmx) function.</span></span> <span data-ttu-id="7f20a-109">Vous pouvez également interroger les cas de test et d’apprentissage dans la structure à l’aide de l’option SELECT... À partir de \<structure> . Syntaxe des cas.</span><span class="sxs-lookup"><span data-stu-id="7f20a-109">You can also query the training and test cases in the structure by using the SELECT... FROM \<structure>.CASES syntax.</span></span>  
  
 <span data-ttu-id="7f20a-110">**Mise en cache de cas d’apprentissage** L’extraction consiste à récupérer des informations sur les cas d’apprentissage dans la structure d’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="7f20a-110">**Caching of training cases** Drillthrough works by retrieving information about the training cases in the mining structure.</span></span> <span data-ttu-id="7f20a-111">Ces informations sont mises en cache lorsque la structure est traitée.</span><span class="sxs-lookup"><span data-stu-id="7f20a-111">This information is cached when the structure is processed.</span></span> <span data-ttu-id="7f20a-112">Par conséquent, si vous choisissez d'effacer toutes les données en cache en modifiant la propriété <xref:Microsoft.AnalysisServices.MiningStructureCacheMode> en `ClearAfterProcessing`, l'extraction ne fonctionnera pas.</span><span class="sxs-lookup"><span data-stu-id="7f20a-112">Therefore, if you choose to clear all cached data by changing the <xref:Microsoft.AnalysisServices.MiningStructureCacheMode> property to `ClearAfterProcessing`, drillthrough will not work.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7f20a-113">Si les cas d’apprentissage n’ont pas été mis en cache, vous devez remplacer la propriété <xref:Microsoft.AnalysisServices.MiningStructureCacheMode> par **KeepTrainingCases** , puis retraiter le modèle avant de pouvoir consulter les données de cas.</span><span class="sxs-lookup"><span data-stu-id="7f20a-113">If the training cases have not been cached, you must change the <xref:Microsoft.AnalysisServices.MiningStructureCacheMode> property to **KeepTrainingCases** and then reprocess the model before you can view the case data.</span></span>  
  
 <span data-ttu-id="7f20a-114">Pour plus d’informations, consultez [Requêtes d’extraction &#40;exploration de données&#41;](drillthrough-queries-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="7f20a-114">For more information, see [Drillthrough Queries &#40;Data Mining&#41;](drillthrough-queries-data-mining.md).</span></span>  
  
### <a name="to-enable-drillthrough-on-a-mining-model"></a><span data-ttu-id="7f20a-115">Pour activer l'extraction sur un modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="7f20a-115">To enable drillthrough on a mining model</span></span>  
  
1.  <span data-ttu-id="7f20a-116">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], sous l’onglet **Modèles d’exploration de données** du Concepteur d’exploration de données, cliquez avec le bouton droit sur le nom du modèle d’exploration de données pour lequel vous voulez activer l’extraction, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="7f20a-116">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], on the **Mining Models** tab of Data Mining Designer, right-click the name of the mining model on which you want to enable drillthrough, and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="7f20a-117">Dans les fenêtres **Propriétés** , cliquez sur **AllowDrillThrough**, puis sélectionnez **true**.</span><span class="sxs-lookup"><span data-stu-id="7f20a-117">In the **Properties** windows, click **AllowDrillthrough**, and select **True**.</span></span>  
  
3.  <span data-ttu-id="7f20a-118">Dans l’onglet **modèles d’exploration de données** , cliquez avec le bouton droit sur le modèle, puis sélectionnez traiter le **modèle**.</span><span class="sxs-lookup"><span data-stu-id="7f20a-118">In the **Mining Models** tab, right-click the model, and select **Process Model**.</span></span>  
  
### <a name="to-enable-caching-for-a-mining-structure"></a><span data-ttu-id="7f20a-119">Pour activer la mise en cache pour une structure d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="7f20a-119">To enable caching for a mining structure</span></span>  
  
1.  <span data-ttu-id="7f20a-120">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], sous l’onglet **Structure d’exploration de données** du Concepteur d’exploration de données, cliquez avec le bouton droit sur le nom de la structure d’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="7f20a-120">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], on the **Mining Structure** tab of Data Mining Designer, right-click the name of the mining structure.</span></span>  
  
2.  <span data-ttu-id="7f20a-121">Ouvrez la fenêtre **Propriétés** .</span><span class="sxs-lookup"><span data-stu-id="7f20a-121">Open the **Properties** window.</span></span>  
  
3.  <span data-ttu-id="7f20a-122">Dans la fenêtre **Propriétés** , recherchez la propriété **CacheMode** , puis sélectionnez **KeepTrainingCases** dans la liste.</span><span class="sxs-lookup"><span data-stu-id="7f20a-122">In the **Properties** window, locate the **CacheMode** property, and select **KeepTrainingCases** from the list.</span></span>  
  
4.  <span data-ttu-id="7f20a-123">Dans le menu **Base de données** , sélectionnez **Traiter**.</span><span class="sxs-lookup"><span data-stu-id="7f20a-123">On the **Database** menu, select **Process**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f20a-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7f20a-124">See Also</span></span>  
 [<span data-ttu-id="7f20a-125">Requêtes d’extraction &#40;exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="7f20a-125">Drillthrough Queries &#40;Data Mining&#41;</span></span>](drillthrough-queries-data-mining.md)  
  
  
