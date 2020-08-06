---
title: Éditeur de tâche de requête d’exploration de données (onglet modèle d’exploration de données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dmquerytask.miningmodel.f1
helpviewer_keywords:
- Data Mining Query Task Editor
ms.assetid: 0ede9b86-be27-471e-b012-22a65adce579
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 794365c8d15ff9725fc385bb43d51e70ffa529b0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703224"
---
# <a name="data-mining-query-task-editor-mining-model-tab"></a><span data-ttu-id="d3132-102">Éditeur de tâche de requête d'exploration de données (onglet Modèle d'exploration de données)</span><span class="sxs-lookup"><span data-stu-id="d3132-102">Data Mining Query Task Editor (Mining Model Tab)</span></span>
  <span data-ttu-id="d3132-103">Utilisez l’onglet **Modèle d’exploration de données** de la boîte de dialogue **Tâche de requête d’exploration de données** pour spécifier la structure et le modèle d’exploration de données à utiliser.</span><span class="sxs-lookup"><span data-stu-id="d3132-103">Use the **Mining Model** tab of the **Data Mining Query Task** dialog box to specify the mining structure and mining model to use.</span></span>  
  
 <span data-ttu-id="d3132-104">Pour en savoir plus sur l’implémentation de l’exploration de données dans les packages, consultez [Tâche de requête d’exploration de données](control-flow/data-mining-query-task.md) et [Solutions d’exploration de données](https://docs.microsoft.com/analysis-services/data-mining/data-mining-solutions).</span><span class="sxs-lookup"><span data-stu-id="d3132-104">To learn about implementing data mining in packages, see [Data Mining Query Task](control-flow/data-mining-query-task.md) and [Data Mining Solutions](https://docs.microsoft.com/analysis-services/data-mining/data-mining-solutions).</span></span>  
  
## <a name="general-options"></a><span data-ttu-id="d3132-105">Options générales</span><span class="sxs-lookup"><span data-stu-id="d3132-105">General Options</span></span>  
 <span data-ttu-id="d3132-106">**Nom**</span><span class="sxs-lookup"><span data-stu-id="d3132-106">**Name**</span></span>  
 <span data-ttu-id="d3132-107">Fournissez un nom unique pour la tâche de requête d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="d3132-107">Provide a unique name for the Data Mining Query task.</span></span> <span data-ttu-id="d3132-108">Ce nom sert d'étiquette à l'icône de la tâche.</span><span class="sxs-lookup"><span data-stu-id="d3132-108">This name is used as the label in the task icon.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d3132-109">Les noms de tâche doivent être uniques dans un package.</span><span class="sxs-lookup"><span data-stu-id="d3132-109">Task names must be unique within a package.</span></span>  
  
 <span data-ttu-id="d3132-110">**Description**</span><span class="sxs-lookup"><span data-stu-id="d3132-110">**Description**</span></span>  
 <span data-ttu-id="d3132-111">Saisissez la description de la tâche de requête d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="d3132-111">Type a description of the Data Mining Query task.</span></span>  
  
## <a name="mining-model-tab-options"></a><span data-ttu-id="d3132-112">Options de l'onglet Modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="d3132-112">Mining Model Tab Options</span></span>  
 <span data-ttu-id="d3132-113">**Connection**</span><span class="sxs-lookup"><span data-stu-id="d3132-113">**Connection**</span></span>  
 <span data-ttu-id="d3132-114">Choisissez un gestionnaire de connexions [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] dans la liste ou cliquez sur **Nouveau** pour créer un gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="d3132-114">Select an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] connection manager in the list or click **New** to create a new connection manager.</span></span>  
  
 <span data-ttu-id="d3132-115">**Rubriques connexes :**  [Gestionnaire de connexions Analysis Services](connection-manager/analysis-services-connection-manager.md)</span><span class="sxs-lookup"><span data-stu-id="d3132-115">**Related Topics:**  [Analysis Services Connection Manager](connection-manager/analysis-services-connection-manager.md)</span></span>  
  
 <span data-ttu-id="d3132-116">**Nouveau**</span><span class="sxs-lookup"><span data-stu-id="d3132-116">**New**</span></span>  
 <span data-ttu-id="d3132-117">Créez un gestionnaire de connexions [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d3132-117">Create a new [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] connection manager.</span></span>  
  
 <span data-ttu-id="d3132-118">**Rubriques connexes :** [Référence de l’interface utilisateur de la boîte de dialogue Ajout d’un gestionnaire de connexions Analysis Services](connection-manager/add-analysis-services-connection-manager-dialog-box-ui-reference.md)</span><span class="sxs-lookup"><span data-stu-id="d3132-118">**Related Topics:** [Add Analysis Services Connection Manager Dialog Box UI Reference](connection-manager/add-analysis-services-connection-manager-dialog-box-ui-reference.md)</span></span>  
  
 <span data-ttu-id="d3132-119">**Structure d’exploration de données**</span><span class="sxs-lookup"><span data-stu-id="d3132-119">**Mining structure**</span></span>  
 <span data-ttu-id="d3132-120">Sélectionnez une structure d'exploration de données dans la liste.</span><span class="sxs-lookup"><span data-stu-id="d3132-120">Select a mining structure in the list.</span></span>  
  
 <span data-ttu-id="d3132-121">**Modèles d’exploration de données**</span><span class="sxs-lookup"><span data-stu-id="d3132-121">**Mining models**</span></span>  
 <span data-ttu-id="d3132-122">Sélectionnez un modèle d'exploration de données qui repose sur la structure sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="d3132-122">Select a mining model built on the selected mining structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3132-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d3132-123">See Also</span></span>  
 <span data-ttu-id="d3132-124">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="d3132-124">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="d3132-125">[Éditeur de tâche de requête d’exploration de données &#40;onglet requête&#41;](../../2014/integration-services/data-mining-query-task-editor-query-tab.md) </span><span class="sxs-lookup"><span data-stu-id="d3132-125">[Data Mining Query Task Editor &#40;Query Tab&#41;](../../2014/integration-services/data-mining-query-task-editor-query-tab.md) </span></span>  
 <span data-ttu-id="d3132-126">[Éditeur de tâche de requête d’exploration de données &#40;onglet sortie&#41;](../../2014/integration-services/data-mining-query-task-editor-output-tab.md) </span><span class="sxs-lookup"><span data-stu-id="d3132-126">[Data Mining Query Task Editor &#40;Output Tab&#41;](../../2014/integration-services/data-mining-query-task-editor-output-tab.md) </span></span>  
 [<span data-ttu-id="d3132-127">Concepteur d’exploration de données</span><span class="sxs-lookup"><span data-stu-id="d3132-127">Data Mining Designer</span></span>](https://docs.microsoft.com/analysis-services/data-mining/data-mining-designer)  
  
  
