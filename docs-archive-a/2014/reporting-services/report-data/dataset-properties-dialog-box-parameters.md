---
title: Boîte de dialogue Propriétés du dataset, Paramètres | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10150"
- sql12.rtp.rptdesigner.datasetproperties.parameters.f1
ms.assetid: 43b00aab-e2c3-4e85-abe1-a2b5a21efeed
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0073971de373321ce347f416657671e1f497dd1f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710251"
---
# <a name="dataset-properties-dialog-box-parameters"></a><span data-ttu-id="5d69f-102">Boîte de dialogue Propriétés du dataset, Paramètres</span><span class="sxs-lookup"><span data-stu-id="5d69f-102">Dataset Properties Dialog Box, Parameters</span></span>
  <span data-ttu-id="5d69f-103">Sélectionnez **Paramètres** dans la boîte de dialogue **Propriétés du dataset** pour ajouter, modifier et supprimer des paramètres de requête, y compris ceux qui sont liés aux paramètres de rapport.</span><span class="sxs-lookup"><span data-stu-id="5d69f-103">Select **Parameters** on the **Dataset Properties** dialog box to add, change, and delete query parameters, including query parameters that link to report parameters.</span></span>  
  
 <span data-ttu-id="5d69f-104">Lorsque la requête est modifiée sous l'onglet Requête, la commande de requête est analysée.</span><span class="sxs-lookup"><span data-stu-id="5d69f-104">Whenever the query is changed on the query tab, the query command is parsed.</span></span> <span data-ttu-id="5d69f-105">Pour chaque paramètre de requête identifié, un paramètre de rapport avec un nom respectant la casse identique est créé.</span><span class="sxs-lookup"><span data-stu-id="5d69f-105">For each query parameter that is identified, a report parameter with an identical case-sensitive name is created.</span></span> <span data-ttu-id="5d69f-106">Par défaut, le paramètre de requête est ajouté automatiquement à la liste des paramètres de requête et lié au paramètre de rapport correspondant.</span><span class="sxs-lookup"><span data-stu-id="5d69f-106">By default, the query parameter is automatically added to the query parameter list and linked to the corresponding report parameter.</span></span>  
  
 <span data-ttu-id="5d69f-107">Pour les valeurs par défaut, s’il existe des dépendances entre un paramètre de rapport et un autre qui est lié à un paramètre de requête, l’ordre des paramètres de rapport (tels qu’ils apparaissent dans la boîte de dialogue **Propriétés du paramètre de rapport** ) est important.</span><span class="sxs-lookup"><span data-stu-id="5d69f-107">If there are dependencies for the default values of one report parameter on another report parameter that is linked to a query parameter, the order of report parameters (as they appear in the **Report Parameters Properties** dialog box) is important.</span></span> <span data-ttu-id="5d69f-108">Des paramètres de rapport figurant plus bas dans la liste peuvent faire référence à des paramètres de rapport situés plus haut dans la liste.</span><span class="sxs-lookup"><span data-stu-id="5d69f-108">Report parameters later in the list can refer to report parameters earlier in the list.</span></span> <span data-ttu-id="5d69f-109">Pour plus d’informations sur les paramètres de rapport, consultez [Paramètres de rapport &#40;Générateur de rapports et Concepteur de rapports&#41;](../report-design/report-parameters-report-builder-and-report-designer.md).</span><span class="sxs-lookup"><span data-stu-id="5d69f-109">For more information about report parameters, see [Report Parameters &#40;Report Builder and Report Designer&#41;](../report-design/report-parameters-report-builder-and-report-designer.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="5d69f-110">Options</span><span class="sxs-lookup"><span data-stu-id="5d69f-110">Options</span></span>  
 <span data-ttu-id="5d69f-111">**Ajouter**</span><span class="sxs-lookup"><span data-stu-id="5d69f-111">**Add**</span></span>  
 <span data-ttu-id="5d69f-112">Ajoutez un nouveau paramètre à la liste.</span><span class="sxs-lookup"><span data-stu-id="5d69f-112">Add a new parameter to the list.</span></span>  
  
 <span data-ttu-id="5d69f-113">**Supprimer**</span><span class="sxs-lookup"><span data-stu-id="5d69f-113">**Delete**</span></span>  
 <span data-ttu-id="5d69f-114">Supprimez le paramètre sélectionné de la liste.</span><span class="sxs-lookup"><span data-stu-id="5d69f-114">Remove the selected parameter from the list.</span></span>  
  
 <span data-ttu-id="5d69f-115">**Nom du paramètre**</span><span class="sxs-lookup"><span data-stu-id="5d69f-115">**Parameter name**</span></span>  
 <span data-ttu-id="5d69f-116">Tapez le nom d’un paramètre de requête que vous avez ajouté au dataset sous l’onglet **Requête** de la boîte de dialogue **Propriétés du dataset** .</span><span class="sxs-lookup"><span data-stu-id="5d69f-116">Type the name of a query parameter that you added to the dataset on the **Query** tab of the **Dataset Properties** dialog box.</span></span>  
  
 <span data-ttu-id="5d69f-117">**Valeur du paramètre**</span><span class="sxs-lookup"><span data-stu-id="5d69f-117">**Parameter value**</span></span>  
 <span data-ttu-id="5d69f-118">Entrez une valeur pour le paramètre de requête.</span><span class="sxs-lookup"><span data-stu-id="5d69f-118">Enter a value for the query parameter.</span></span> <span data-ttu-id="5d69f-119">Il peut s'agir d'une valeur statique ou d'une expression faisant référence à un objet présent dans le rapport ; toutefois, elle ne peut pas faire référence à des éléments de rapport ou des champs.</span><span class="sxs-lookup"><span data-stu-id="5d69f-119">This can be a static value or an expression that refers to an object within the report, but it cannot refer to any report items or fields.</span></span> <span data-ttu-id="5d69f-120">Par défaut, **Valeur** contient une expression qui pointe vers un paramètre de rapport.</span><span class="sxs-lookup"><span data-stu-id="5d69f-120">By default, **Value** contains an expression that points to a report parameter.</span></span>  
  
 <span data-ttu-id="5d69f-121">**Flèche haut**</span><span class="sxs-lookup"><span data-stu-id="5d69f-121">**Up arrow**</span></span>  
 <span data-ttu-id="5d69f-122">Déplacez le paramètre sélectionné vers le haut de la liste.</span><span class="sxs-lookup"><span data-stu-id="5d69f-122">Move the selected parameter up in the list.</span></span>  
  
 <span data-ttu-id="5d69f-123">**Flèche bas**</span><span class="sxs-lookup"><span data-stu-id="5d69f-123">**Down arrow**</span></span>  
 <span data-ttu-id="5d69f-124">Déplacez le paramètre sélectionné vers le bas de la liste.</span><span class="sxs-lookup"><span data-stu-id="5d69f-124">Move the selected parameter down in the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d69f-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5d69f-125">See Also</span></span>  
 <span data-ttu-id="5d69f-126">[Paramètres de rapport &#40;Générateur de rapports et Concepteur de rapports&#41;](../report-design/report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="5d69f-126">[Report Parameters &#40;Report Builder and Report Designer&#41;](../report-design/report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="5d69f-127">[Ajouter des données à un rapport &#40;Générateur de rapports et SSRS&#41;](report-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5d69f-127">[Add Data to a Report &#40;Report Builder and SSRS&#41;](report-datasets-ssrs.md) </span></span>  
 [<span data-ttu-id="5d69f-128">Modifier l’ordre d’un paramètre de rapport &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="5d69f-128">Change the Order of a Report Parameter &#40;Report Builder and SSRS&#41;</span></span>](../report-design/change-the-order-of-a-report-parameter-report-builder-and-ssrs.md)  
  
  
