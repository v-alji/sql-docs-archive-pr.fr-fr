---
title: Traiter une structure d’exploration de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining structures [Analysis Services], processing
ms.assetid: 4162f33e-c23f-4293-8905-271781e45fa4
author: minewiskan
ms.author: owend
ms.openlocfilehash: 76d25a927ae61ee5ffadf4ca21073a1c04cdb542
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703447"
---
# <a name="process-a-mining-structure"></a><span data-ttu-id="dacfc-102">traiter une structure d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="dacfc-102">Process a Mining Structure</span></span>
  <span data-ttu-id="dacfc-103">Pour pouvoir consulter ou utiliser des modèles d'exploration de données associés à une structure d'exploration de données, vous devez déployer le projet [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] et traiter la structure d'exploration de données et les modèles d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="dacfc-103">Before you can browse or work with the mining models that are associated with a mining structure, you have to deploy the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project and process the mining structure and mining models.</span></span> <span data-ttu-id="dacfc-104">De plus, si vous modifiez la structure d’exploration de données ou les modèles d’exploration de données, un message vous invite à les redéployer et les retraiter.</span><span class="sxs-lookup"><span data-stu-id="dacfc-104">Also, if you make a change to the mining structure or mining models, you will be prompted to redeploy and process them.</span></span> <span data-ttu-id="dacfc-105">Le traitement de la structure sous l’onglet **Structure d’exploration de données** du Concepteur d’exploration de données de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] traite tous les modèles associés.</span><span class="sxs-lookup"><span data-stu-id="dacfc-105">Processing the structure in the **Mining Structure** tab of Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] processes all the associated models.</span></span>  
  
 <span data-ttu-id="dacfc-106">Vous pouvez traiter une structure d'exploration de données à l'aide de ces outils :</span><span class="sxs-lookup"><span data-stu-id="dacfc-106">You can process a mining structure by using these tools:</span></span>  
  
-   [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]  
  
-   <span data-ttu-id="dacfc-107">XMLA : commande Process</span><span class="sxs-lookup"><span data-stu-id="dacfc-107">XMLA: Process command</span></span>  
  
 <span data-ttu-id="dacfc-108">Pour plus d’informations sur la façon de traiter les différents modèles, consultez [Traiter un modèle d’exploration de données](process-a-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="dacfc-108">For information about how to process individual models, see [Process a Mining Model](process-a-mining-model.md).</span></span>  
  
### <a name="to-process-a-mining-structure-and-all-associated-mining-models-using-sql-server-data-tools"></a><span data-ttu-id="dacfc-109">Pour traiter une structure d'exploration de données et tous les modèles d'exploration de données associés à l'aide des outils de données SQL Server</span><span class="sxs-lookup"><span data-stu-id="dacfc-109">To process a mining structure and all associated mining models using SQL Server Data Tools</span></span>  
  
1.  <span data-ttu-id="dacfc-110">Sélectionnez **Traiter la structure d’exploration de données et tous les modèles** dans l’option de menu **Modèle d’exploration de données** de [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dacfc-110">Select **Process Mining Structure and All Models** from the **Mining Model** menu item in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span></span>  
  
     <span data-ttu-id="dacfc-111">Si vous modifiez la structure, un message vous demande de la redéployer avant de traiter les modèles.</span><span class="sxs-lookup"><span data-stu-id="dacfc-111">If you made changes to the structure, you will be prompted to redeploy the structure before processing the models.</span></span> <span data-ttu-id="dacfc-112">Cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="dacfc-112">Click **Yes**.</span></span>  
  
2.  <span data-ttu-id="dacfc-113">Dans la boîte de dialogue traitement de la \*\*structure d’exploration de données-, \<structure> \*\* cliquez sur **exécuter** .</span><span class="sxs-lookup"><span data-stu-id="dacfc-113">Click **Run** in the **Processing Mining Structure - \<structure>** dialog box.</span></span>  
  
     <span data-ttu-id="dacfc-114">La boîte de dialogue **État d’avancement du traitement** s’ouvre avec les informations sur le traitement des modèles.</span><span class="sxs-lookup"><span data-stu-id="dacfc-114">The **Process Progress** dialog box opens to display the details of model processing.</span></span>  
  
3.  <span data-ttu-id="dacfc-115">Cliquez sur **Fermer** dans la boîte de dialogue **État d’avancement du traitement** une fois que les modèles ont été traités.</span><span class="sxs-lookup"><span data-stu-id="dacfc-115">Click **Close** in the **Process Progress** dialog box after the models have completed processing.</span></span>  
  
4.  <span data-ttu-id="dacfc-116">Cliquez sur **Fermer** dans la boîte de dialogue traitement de la **structure d’exploration \<structure> de données-** .</span><span class="sxs-lookup"><span data-stu-id="dacfc-116">Click **Close** in the **Processing Mining Structure - \<structure>** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dacfc-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="dacfc-117">See Also</span></span>  
 [<span data-ttu-id="dacfc-118">Tâches de la structure d'exploration de données et procédures</span><span class="sxs-lookup"><span data-stu-id="dacfc-118">Mining Structure Tasks and How-tos</span></span>](mining-structure-tasks-and-how-tos.md)  
  
  
