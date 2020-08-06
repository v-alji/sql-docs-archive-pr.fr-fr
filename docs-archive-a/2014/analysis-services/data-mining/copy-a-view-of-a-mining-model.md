---
title: Copier une vue d’un modèle d’exploration de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- clipboards [data mining]
- Mining Model Viewer [Analysis Services], clipboards
- copying mining models to clipboard
ms.assetid: 768372db-e5b4-4990-b459-03d854fd9a6d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 36d4d372bd235cd1cc0c043ff98151091e242269
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694847"
---
# <a name="copy-a-view-of-a-mining-model"></a><span data-ttu-id="1c286-102">Copier une vue d'un modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="1c286-102">Copy a View of a Mining Model</span></span>
  <span data-ttu-id="1c286-103">L’onglet **Visionneuse de modèle d’exploration de données** du Concepteur d’exploration de données de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] utilise une visionneuse distincte pour chaque type de modèle d’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="1c286-103">The **Mining Model Viewer** tab of Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] uses a separate viewer for each type of mining model.</span></span> <span data-ttu-id="1c286-104">Plusieurs des visionneuses ont des composants à partir desquels vous pouvez copier le contenu vers le Presse-papiers, puis coller le contenu dans un document ou un logiciel de manipulation d'image.</span><span class="sxs-lookup"><span data-stu-id="1c286-104">Several of the viewers have components from which you can copy the contents to the Clipboard, and from there paste the contents into a document or into image manipulation software.</span></span> <span data-ttu-id="1c286-105">Cette fonctionnalité est disponible avec les composants suivants :</span><span class="sxs-lookup"><span data-stu-id="1c286-105">The following components make this functionality available:</span></span>  
  
-   <span data-ttu-id="1c286-106">Diagramme de cluster dans [!INCLUDE[msCoName](../../includes/msconame-md.md)] Cluster Viewer et la Visionneuse de l'algorithme MSC ( [!INCLUDE[msCoName](../../includes/msconame-md.md)] Sequence Cluster)</span><span class="sxs-lookup"><span data-stu-id="1c286-106">Cluster Diagram in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Cluster Viewer and the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Sequence Cluster Viewer</span></span>  
  
-   <span data-ttu-id="1c286-107">Arbre de décision dans la Visionneuse d’arborescence [!INCLUDE[msCoName](../../includes/msconame-md.md)] et la Visionneuse de l’algorithme MTS ( [!INCLUDE[msCoName](../../includes/msconame-md.md)] Time Series)</span><span class="sxs-lookup"><span data-stu-id="1c286-107">Decision Tree in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Tree Viewer and the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Time Series Viewer</span></span>  
  
-   <span data-ttu-id="1c286-108">Transitions d'état dans la Visionneuse de l'algorithme MSC ( [!INCLUDE[msCoName](../../includes/msconame-md.md)] Sequence Cluster)</span><span class="sxs-lookup"><span data-stu-id="1c286-108">State Transitions in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Sequence Cluster Viewer</span></span>  
  
-   <span data-ttu-id="1c286-109">Réseau de dépendances dans la Visionneuse de l'algorithme MAR ( [!INCLUDE[msCoName](../../includes/msconame-md.md)] Association Rules), la Visionneuse de l'algorithme MNB ( [!INCLUDE[msCoName](../../includes/msconame-md.md)] Naive Bayes) et la Visionneuse d'arborescence [!INCLUDE[msCoName](../../includes/msconame-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c286-109">Dependency Network in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Association Rules Viewer, the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Naive Bayes Viewer, and the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Tree Viewer</span></span>  
  
-   <span data-ttu-id="1c286-110">Contenu du modèle d’exploration de données à partir du volet Détails du nœud de la Visionneuse de l’arborescence de contenu générique [!INCLUDE[msCoName](../../includes/msconame-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c286-110">Mining model content, from the Node Details pane of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Generic Content Tree Viewer</span></span>  
  
 <span data-ttu-id="1c286-111">Vous pouvez copier la représentation complète du modèle d'exploration de données ou simplement la partie visible dans la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="1c286-111">You can copy the complete representation of the mining model, or just the part that is visible in the viewer.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="1c286-112">Lorsque vous copiez un modèle à l'aide de la visionneuse, il ne crée pas de nouvel objet de modèle.</span><span class="sxs-lookup"><span data-stu-id="1c286-112">When you copy a model using the viewer, it does not create a new model object.</span></span> <span data-ttu-id="1c286-113">Pour créer un modèle, vous devez utiliser l'Assistant, ou le Concepteur d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="1c286-113">To create a new model, you must use either the wizard, or the Data Mining Designer,.</span></span> <span data-ttu-id="1c286-114">Pour plus d’informations, consultez [Créer une copie d’un modèle d’exploration de données](make-a-copy-of-a-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="1c286-114">For more information, see [Make a Copy of a Mining Model](make-a-copy-of-a-mining-model.md).</span></span>  
  
### <a name="to-copy-the-complete-model-to-the-clipboard"></a><span data-ttu-id="1c286-115">Pour copier le modèle complet dans le Presse-papiers</span><span class="sxs-lookup"><span data-stu-id="1c286-115">To copy the complete model to the Clipboard</span></span>  
  
1.  <span data-ttu-id="1c286-116">Dans la liste **Modèle d’exploration de données** sous l’onglet **Visionneuse de modèle d’exploration de données** , sélectionnez le modèle d’exploration de données à afficher.</span><span class="sxs-lookup"><span data-stu-id="1c286-116">From the **Mining Model** list on the **Mining Model Viewer** tab, select the mining model that you want to view.</span></span>  
  
2.  <span data-ttu-id="1c286-117">Sélectionnez l’onglet approprié, tel que l’onglet **Réseau de dépendances** , puis cliquez sur **Copier le graphique entier** dans la barre d’outils de l’onglet.</span><span class="sxs-lookup"><span data-stu-id="1c286-117">Select the appropriate tab, such as the **Dependency Network** tab, and then click **Copy Entire Graph** on the toolbar of that tab.</span></span>  
  
### <a name="to-copy-the-visible-piece-of-the-model-to-the-clipboard"></a><span data-ttu-id="1c286-118">Pour copier la partie visible du modèle vers le Presse-papiers</span><span class="sxs-lookup"><span data-stu-id="1c286-118">To copy the visible piece of the model to the Clipboard</span></span>  
  
1.  <span data-ttu-id="1c286-119">Dans la liste **Modèle d’exploration de données** sous l’onglet **Visionneuse de modèle d’exploration de données** , sélectionnez le modèle d’exploration de données à afficher.</span><span class="sxs-lookup"><span data-stu-id="1c286-119">From the **Mining Model** list on the **Mining Model Viewer** tab, select the mining model that you want to view.</span></span>  
  
2.  <span data-ttu-id="1c286-120">Sélectionnez l’onglet approprié, tel que l’onglet **Réseau de dépendances** , puis effectuez un zoom avant ou arrière sur le modèle au niveau approprié.</span><span class="sxs-lookup"><span data-stu-id="1c286-120">Select the appropriate tab, such as the **Dependency Network** tab, and then zoom in or out to view the model at the level that you want.</span></span>  
  
3.  <span data-ttu-id="1c286-121">Cliquez sur **Copier la vue du graphique** dans la barre d’outils de l’onglet sélectionné.</span><span class="sxs-lookup"><span data-stu-id="1c286-121">Click **Copy Graph View** on the toolbar of the selected tab.</span></span>  
  
### <a name="to-copy-the-mining-model-content-to-the-clipboard"></a><span data-ttu-id="1c286-122">Pour copier le contenu du modèle d'exploration de données dans le Presse-papiers</span><span class="sxs-lookup"><span data-stu-id="1c286-122">To copy the mining model content to the Clipboard</span></span>  
  
1.  <span data-ttu-id="1c286-123">Dans la liste **Modèle d’exploration de données** sous l’onglet **Visionneuse de modèle d’exploration de données** , sélectionnez le modèle d’exploration de données à afficher.</span><span class="sxs-lookup"><span data-stu-id="1c286-123">From the **Mining Model** list on the **Mining Model Viewer** tab, select the mining model that you want to view.</span></span>  
  
2.  <span data-ttu-id="1c286-124">Dans la liste déroulante **Visionneuse** , sélectionnez **Visionneuse de l’arborescence de contenu générique Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="1c286-124">From the **Viewer** drop-down list, select **Microsoft Generic Content Tree Viewer**.</span></span>  
  
3.  <span data-ttu-id="1c286-125">Dans le volet **Légende du nœud (ID unique)** , cliquez sur un nœud.</span><span class="sxs-lookup"><span data-stu-id="1c286-125">In the **Node Caption (Unique ID)** pane, click a node.</span></span>  
  
4.  <span data-ttu-id="1c286-126">Cliquez avec le bouton droit sur le volet **Détails du nœud** , puis sélectionnez **Sélectionner tout**.</span><span class="sxs-lookup"><span data-stu-id="1c286-126">Right-click the **Node Details** pane and then select **Select All**.</span></span>  
  
5.  <span data-ttu-id="1c286-127">Cliquez de nouveau avec le bouton droit sur le volet **Détails du nœud** , puis sélectionnez **Copier**.</span><span class="sxs-lookup"><span data-stu-id="1c286-127">Right-click the **Node Details** pane again and select **Copy**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c286-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1c286-128">See Also</span></span>  
 [<span data-ttu-id="1c286-129">Tâches de la visionneuse de modèle d'exploration de données et procédures</span><span class="sxs-lookup"><span data-stu-id="1c286-129">Mining Model Viewer Tasks and How-tos</span></span>](mining-model-viewer-tasks-and-how-tos.md)  
  
  
