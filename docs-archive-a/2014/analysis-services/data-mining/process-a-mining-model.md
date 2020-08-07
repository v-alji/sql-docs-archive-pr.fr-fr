---
title: Traiter un modèle d’exploration de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models [Analysis Services], processing
ms.assetid: c2204472-c500-47a5-9afa-7ce2ca78b233
author: minewiskan
ms.author: owend
ms.openlocfilehash: c2fed5d72c677dc175f4c9681096d1859b30d829
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703440"
---
# <a name="process-a-mining-model"></a><span data-ttu-id="c6ee3-102">Traiter un modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="c6ee3-102">Process a Mining Model</span></span>
  <span data-ttu-id="c6ee3-103">Dans l'onglet Modèles d'exploration de données du Concepteur d'exploration de données de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], vous pouvez traiter un modèle d'exploration de données associé à une structure d'exploration de données, ou traiter tous les modèles associés à la structure.</span><span class="sxs-lookup"><span data-stu-id="c6ee3-103">In the Mining Models tab of Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], you can either process a specific mining model that is associated with a mining structure or you can process all the models that are associated with the structure.</span></span>  
  
 <span data-ttu-id="c6ee3-104">Vous pouvez traiter un modèle d'exploration de données à l'aide des outils suivants :</span><span class="sxs-lookup"><span data-stu-id="c6ee3-104">You can process a mining model by using the following tools:</span></span>  
  
-   [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]  
  
 <span data-ttu-id="c6ee3-105">Vous pouvez également utiliser une commande de traitement XMLA.</span><span class="sxs-lookup"><span data-stu-id="c6ee3-105">You can also use an XMLA Process command.</span></span> <span data-ttu-id="c6ee3-106">Pour plus d’informations, consultez [Outils et approches pour le traitement des &#40;Analysis Services&#41;](../multidimensional-models/tools-and-approaches-for-processing-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="c6ee3-106">For more information, see  [Tools and Approaches for Processing &#40;Analysis Services&#41;](../multidimensional-models/tools-and-approaches-for-processing-analysis-services.md).</span></span>  
  
### <a name="process-a-single-mining-model-using-sql-server-data-tools"></a><span data-ttu-id="c6ee3-107">Traiter un seul modèle d'exploration de données à l'aide des outils de données SQL Server</span><span class="sxs-lookup"><span data-stu-id="c6ee3-107">Process a single mining model using SQL Server Data Tools</span></span>  
  
1.  <span data-ttu-id="c6ee3-108">Sous l'onglet **Modèles d'exploration de données** du Concepteur d'exploration de données, sélectionnez un modèle d'exploration de données dans une ou plusieurs colonnes des modèles de la grille.</span><span class="sxs-lookup"><span data-stu-id="c6ee3-108">On the **Mining Models** tab of Data Mining Designer, select a mining model from the one or more columns of models in the grid.</span></span>  
  
2.  <span data-ttu-id="c6ee3-109">Dans le menu **Modèle d'exploration de données** , sélectionnez **Traiter le modèle**.</span><span class="sxs-lookup"><span data-stu-id="c6ee3-109">On the **Mining Model** menu, select **Process Model**.</span></span>  
  
     <span data-ttu-id="c6ee3-110">Si vous avez modifié la structure d'exploration de données, un message vous demande de la redéployer avant de traiter le modèle.</span><span class="sxs-lookup"><span data-stu-id="c6ee3-110">If you made changes to the mining structure, you will be prompted to redeploy the structure before processing the model.</span></span> <span data-ttu-id="c6ee3-111">Cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="c6ee3-111">Click **Yes**.</span></span>  
  
3.  <span data-ttu-id="c6ee3-112">Dans la boîte de dialogue **traitement \<model> du modèle d’exploration de données-** , cliquez sur **exécuter**.</span><span class="sxs-lookup"><span data-stu-id="c6ee3-112">In the **Processing Mining Model - \<model>** dialog box, click **Run**.</span></span>  
  
     <span data-ttu-id="c6ee3-113">La boîte de dialogue **État d'avancement du traitement** s'ouvre avec les informations de traitement du modèle.</span><span class="sxs-lookup"><span data-stu-id="c6ee3-113">The **Process Progress** dialog box opens to show the details of model processing.</span></span>  
  
4.  <span data-ttu-id="c6ee3-114">Une fois le modèle traité, cliquez sur **Fermer** dans la boîte de dialogue **État d'avancement du traitement** .</span><span class="sxs-lookup"><span data-stu-id="c6ee3-114">After the model has successfully completed processing, click **Close** in the **Process Progress** dialog box.</span></span>  
  
5.  <span data-ttu-id="c6ee3-115">Cliquez sur **Fermer** dans la boîte de dialogue \*\*traitement du modèle d’exploration de données- \<model> \*\* .</span><span class="sxs-lookup"><span data-stu-id="c6ee3-115">Click **Close** in the **Processing Mining Model - \<model>** dialog box.</span></span>  
  
 <span data-ttu-id="c6ee3-116">Seuls la structure d'exploration de données et le modèle d'exploration de données sélectionné ont été traités.</span><span class="sxs-lookup"><span data-stu-id="c6ee3-116">Only the mining structure and the selected mining model have been processed.</span></span>  
  
### <a name="process-all-mining-models-that-are-associated-with-a-mining-structure"></a><span data-ttu-id="c6ee3-117">Traiter tous les modèles d'exploration de données associés à une structure d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="c6ee3-117">Process all mining models that are associated with a mining structure</span></span>  
  
1.  <span data-ttu-id="c6ee3-118">Dans l'onglet **Modèles d'exploration de données** du Concepteur d'exploration de données, sélectionnez **Traiter l'exploration de données et tous les modèles** dans le menu **Modèle d'exploration de données** .</span><span class="sxs-lookup"><span data-stu-id="c6ee3-118">On the **Mining Models** tab of Data Mining Designer, select **Process Mining Structure and All Models** from the **Mining Model** menu.</span></span>  
  
2.  <span data-ttu-id="c6ee3-119">Si vous avez modifié la structure d'exploration de données, un message vous demande de la redéployer avant de traiter les modèles.</span><span class="sxs-lookup"><span data-stu-id="c6ee3-119">If you made changes to the mining structure, you will be prompted to redeploy the structure before processing the models.</span></span> <span data-ttu-id="c6ee3-120">Cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="c6ee3-120">Click **Yes**.</span></span>  
  
3.  <span data-ttu-id="c6ee3-121">Dans la boîte de dialogue traitement de la **structure d’exploration de \<structure> données-** , cliquez sur **exécuter**.</span><span class="sxs-lookup"><span data-stu-id="c6ee3-121">In the **Processing Mining Structure - \<structure>** dialog box, click **Run**.</span></span>  
  
4.  <span data-ttu-id="c6ee3-122">La boîte de dialogue **État d'avancement du traitement** s'ouvre avec les informations de traitement du modèle.</span><span class="sxs-lookup"><span data-stu-id="c6ee3-122">The **Process Progress** dialog box opens to show the details of model processing.</span></span>  
  
5.  <span data-ttu-id="c6ee3-123">Une fois les modèles traités, cliquez sur **Fermer** dans la boîte de dialogue **État d'avancement du traitement** .</span><span class="sxs-lookup"><span data-stu-id="c6ee3-123">After the models have successfully completed processing, click **Close** in the **Process Progress** dialog box.</span></span>  
  
6.  <span data-ttu-id="c6ee3-124">Cliquez sur **Fermer** dans la boîte de dialogue \*\*traitement \<model> \*\* .</span><span class="sxs-lookup"><span data-stu-id="c6ee3-124">Click **Close** in the **Processing \<model>** dialog box.</span></span>  
  
 <span data-ttu-id="c6ee3-125">La structure d'exploration de données et tous les modèles d'exploration de données associés ont été traités.</span><span class="sxs-lookup"><span data-stu-id="c6ee3-125">The mining structure and all the associated mining models have been processed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6ee3-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c6ee3-126">See Also</span></span>  
 [<span data-ttu-id="c6ee3-127">Tâches du modèle d'exploration de données et procédures</span><span class="sxs-lookup"><span data-stu-id="c6ee3-127">Mining Model Tasks and How-tos</span></span>](mining-model-tasks-and-how-tos.md)  
  
  
