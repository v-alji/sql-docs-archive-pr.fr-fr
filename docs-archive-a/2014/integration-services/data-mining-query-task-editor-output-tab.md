---
title: Éditeur de tâche de requête d’exploration de données (onglet sortie) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dmquerytask.output.f1
helpviewer_keywords:
- Data Mining Query Task Editor
ms.assetid: 62f9e015-6fe0-4396-ad90-3ad51bf00025
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1508972b0487daa90f52af723d58185944a19a58
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706592"
---
# <a name="data-mining-query-task-editor-output-tab"></a><span data-ttu-id="75bed-102">Éditeur de tâche de requête d'exploration de données (onglet Sortie)</span><span class="sxs-lookup"><span data-stu-id="75bed-102">Data Mining Query Task Editor (Output Tab)</span></span>
  <span data-ttu-id="75bed-103">Utilisez l'onglet **Sortie** de la boîte de dialogue **Éditeur de tâche de requête d'exploration de données** pour définir la destination de la requête de prédiction.</span><span class="sxs-lookup"><span data-stu-id="75bed-103">Use the **Output** tab of the **Data Mining Query Task Editor** dialog box to specify the destination of the prediction query.</span></span>  
  
 <span data-ttu-id="75bed-104">Pour en savoir plus sur l’implémentation de l’exploration de données dans les packages, consultez [Tâche de requête d’exploration de données](control-flow/data-mining-query-task.md) et [Solutions d’exploration de données](https://docs.microsoft.com/analysis-services/data-mining/data-mining-solutions).</span><span class="sxs-lookup"><span data-stu-id="75bed-104">To learn about implementing data mining in packages, see [Data Mining Query Task](control-flow/data-mining-query-task.md) and [Data Mining Solutions](https://docs.microsoft.com/analysis-services/data-mining/data-mining-solutions).</span></span>  
  
## <a name="general-options"></a><span data-ttu-id="75bed-105">Options générales</span><span class="sxs-lookup"><span data-stu-id="75bed-105">General Options</span></span>  
 <span data-ttu-id="75bed-106">**Nom**</span><span class="sxs-lookup"><span data-stu-id="75bed-106">**Name**</span></span>  
 <span data-ttu-id="75bed-107">Fournissez un nom unique pour la tâche de requête d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="75bed-107">Provide a unique name for the Data Mining Query task.</span></span> <span data-ttu-id="75bed-108">Ce nom sert d'étiquette à l'icône de la tâche.</span><span class="sxs-lookup"><span data-stu-id="75bed-108">This name is used as the label in the task icon.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="75bed-109">Les noms de tâche doivent être uniques dans un package.</span><span class="sxs-lookup"><span data-stu-id="75bed-109">Task names must be unique within a package.</span></span>  
  
 <span data-ttu-id="75bed-110">**Description**</span><span class="sxs-lookup"><span data-stu-id="75bed-110">**Description**</span></span>  
 <span data-ttu-id="75bed-111">Saisissez la description de la tâche de requête d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="75bed-111">Type a description of the Data Mining Query task.</span></span>  
  
## <a name="output-tab-options"></a><span data-ttu-id="75bed-112">Options de l'onglet Sortie</span><span class="sxs-lookup"><span data-stu-id="75bed-112">Output Tab Options</span></span>  
 <span data-ttu-id="75bed-113">**Connection**</span><span class="sxs-lookup"><span data-stu-id="75bed-113">**Connection**</span></span>  
 <span data-ttu-id="75bed-114">Sélectionnez un gestionnaire de connexions dans la liste ou cliquez sur **Nouveau** pour en créer un.</span><span class="sxs-lookup"><span data-stu-id="75bed-114">Select a connection manager in the list or click **New** to create a new connection manager.</span></span>  
  
 <span data-ttu-id="75bed-115">**Nouveau**</span><span class="sxs-lookup"><span data-stu-id="75bed-115">**New**</span></span>  
 <span data-ttu-id="75bed-116">Crée un gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="75bed-116">Create a new connection manager.</span></span> <span data-ttu-id="75bed-117">Vous ne pouvez utiliser que les types de gestionnaires de connexions ADO.NET et OLE DB.</span><span class="sxs-lookup"><span data-stu-id="75bed-117">Only the ADO.NET and OLE DB connection manager types can be used.</span></span>  
  
 <span data-ttu-id="75bed-118">**Table de sortie**</span><span class="sxs-lookup"><span data-stu-id="75bed-118">**Output table**</span></span>  
 <span data-ttu-id="75bed-119">Définissez la table dans laquelle la requête de prédiction écrit ses résultats.</span><span class="sxs-lookup"><span data-stu-id="75bed-119">Specify the table to which the prediction query writes its results.</span></span>  
  
 <span data-ttu-id="75bed-120">**Supprimer et recréer la table de sortie**</span><span class="sxs-lookup"><span data-stu-id="75bed-120">**Drop and re-create the output table**</span></span>  
 <span data-ttu-id="75bed-121">Indiquez si la requête de prédiction doit remplacer le contenu de la table de destination en supprimant, puis en recréant la table.</span><span class="sxs-lookup"><span data-stu-id="75bed-121">Indicate whether the prediction query should overwrite content in the destination table by dropping and then re-creating the table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75bed-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="75bed-122">See Also</span></span>  
 <span data-ttu-id="75bed-123">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="75bed-123">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="75bed-124">[Éditeur de tâche de requête d’exploration de données &#40;onglet modèle d’exploration de données&#41;](../../2014/integration-services/data-mining-query-task-editor-mining-model-tab.md) </span><span class="sxs-lookup"><span data-stu-id="75bed-124">[Data Mining Query Task Editor &#40;Mining Model Tab&#41;](../../2014/integration-services/data-mining-query-task-editor-mining-model-tab.md) </span></span>  
 <span data-ttu-id="75bed-125">[Éditeur de tâche de requête d’exploration de données &#40;onglet requête&#41;](../../2014/integration-services/data-mining-query-task-editor-query-tab.md) </span><span class="sxs-lookup"><span data-stu-id="75bed-125">[Data Mining Query Task Editor &#40;Query Tab&#41;](../../2014/integration-services/data-mining-query-task-editor-query-tab.md) </span></span>  
 [<span data-ttu-id="75bed-126">Concepteur d’exploration de données</span><span class="sxs-lookup"><span data-stu-id="75bed-126">Data Mining Designer</span></span>](https://docs.microsoft.com/analysis-services/data-mining/data-mining-designer)  
  
  
