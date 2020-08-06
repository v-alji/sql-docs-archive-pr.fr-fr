---
title: Plan d’exécution et allocation de mémoire tampon | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- custom data flow components [Integration Services], buffer allocations
- custom data flow components [Integration Services], execution plans
- buffer allocations [Integration Services]
- data flow components [Integration Services], buffer allocations
- data flow components [Integration Services], execution plans
- execution plans [Integration Services]
ms.assetid: 679d9ff0-641e-47c3-abb8-d1a7dcb279dd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 03b8bb22988ccf77f8920252ac2d600478c92f3b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697027"
---
# <a name="execution-plan-and-buffer-allocation"></a><span data-ttu-id="a9473-102">Plan d'exécution et allocation de mémoire tampon</span><span class="sxs-lookup"><span data-stu-id="a9473-102">Execution Plan and Buffer Allocation</span></span>
  <span data-ttu-id="a9473-103">Avant l'exécution, la tâche de flux de données examine ses composants et génère un plan d'exécution pour chaque séquence de composants.</span><span class="sxs-lookup"><span data-stu-id="a9473-103">Before execution, the data flow task examines its components and generates an execution plan for each sequence of components.</span></span> <span data-ttu-id="a9473-104">Cette section fournit des détails sur le plan d'exécution et son mode d'affichage, ainsi que sur l'allocation de mémoires tampons d'entrée et de sortie en fonction du plan d'exécution.</span><span class="sxs-lookup"><span data-stu-id="a9473-104">This section provides details about the execution plan, how to view the plan, and how input and output buffers are allocated based on the execution plan.</span></span>  
  
## <a name="understanding-the-execution-plan"></a><span data-ttu-id="a9473-105">Fonctionnement du plan d'exécution</span><span class="sxs-lookup"><span data-stu-id="a9473-105">Understanding the Execution Plan</span></span>  
 <span data-ttu-id="a9473-106">Un plan d'exécution contient des threads sources et des threads de travail. Chaque thread contient des listes de travaux qui spécifient des listes de travaux de sortie pour les threads sources ou des listes de travaux d'entrée et de sortie pour les threads de travail.</span><span class="sxs-lookup"><span data-stu-id="a9473-106">An execution plan contains source threads and work threads, and each thread contains work lists that specify output work lists for source threads or input and output work lists for work threads.</span></span> <span data-ttu-id="a9473-107">Les threads sources d’un plan d’exécution représentent les composants sources du flux de données et sont identifiés dans le plan d’exécution par *SourceThread \* \* n*, où *n* est le numéro de base zéro du thread source.</span><span class="sxs-lookup"><span data-stu-id="a9473-107">The source threads in an execution plan represent the source components in the data flow and are identified in the execution plan by *SourceThread\*\*n*, where *n* is the zero-based number of the source thread.</span></span>  
  
 <span data-ttu-id="a9473-108">Chaque thread source crée une mémoire tampon, définit un écouteur et appelle la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> sur le composant source.</span><span class="sxs-lookup"><span data-stu-id="a9473-108">Each source thread creates a buffer, sets a listener, and calls the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> method on the source component.</span></span> <span data-ttu-id="a9473-109">C'est de cet emplacement que démarre l'exécution et que proviennent les données, pendant que le composant source commence à ajouter des lignes aux mémoires tampons de sortie que lui fournit la tâche de flux de données.</span><span class="sxs-lookup"><span data-stu-id="a9473-109">This is where execution starts and data originates, as the source component starts adding rows to the output buffers that are provided to it by the data flow task.</span></span> <span data-ttu-id="a9473-110">Une fois que les threads sources sont exécutés, la charge de travail est répartie entre les threads de travail.</span><span class="sxs-lookup"><span data-stu-id="a9473-110">After the source threads are running, the balance of work is distributed among work threads.</span></span>  
  
 <span data-ttu-id="a9473-111">Un thread de travail peut contenir à la fois des listes de travaux d’entrée et de sortie et est identifié dans le plan d’exécution par *WorkThread \* \* n*, où *n* est le numéro de base zéro du thread de travail.</span><span class="sxs-lookup"><span data-stu-id="a9473-111">A work thread may contain both input and output work lists and is identified in the execution plan as *WorkThread\*\*n*, where *n* is the zero-based number of the work thread.</span></span> <span data-ttu-id="a9473-112">Ces threads contiennent des listes de travaux de sortie lorsque le graphique contient un composant à sorties asynchrones.</span><span class="sxs-lookup"><span data-stu-id="a9473-112">These threads contain output work lists when the graph contains a component with asynchronous outputs.</span></span>  
  
 <span data-ttu-id="a9473-113">L'exemple de plan d'exécution suivant représente un flux de données qui contient un composant source connecté à une transformation à sortie asynchrone connectée à un composant de destination.</span><span class="sxs-lookup"><span data-stu-id="a9473-113">The following sample execution plan represents a data flow that contains a source component connected to a transformation with an asynchronous output connected to a destination component.</span></span> <span data-ttu-id="a9473-114">Dans cet exemple, WorkThread0 contient une liste des travaux de sortie car le composant de transformation possède une sortie asynchrone.</span><span class="sxs-lookup"><span data-stu-id="a9473-114">In this example, WorkThread0 contains an output work list because the transformation component has an asynchronous output.</span></span>  
  
```  
SourceThread0   
    Influences: 72 158   
    Output Work List   
        CreatePrimeBuffer of type 1 for output id 10   
        SetBufferListener: "WorkThread0" for input ID 73   
        CallPrimeOutput on component "OLE DB Source" (1)   
    End Output Work List   
    This thread drives 0 distributors   
End SourceThread0   
WorkThread0   
    Influences: 72 158   
    Input Work list, input ID 73   
        CallProcessInput on input ID 73 on component "Sort" (72) for view type 2   
    End Input Work list for input 73   
    Output Work List   
        CreatePrimeBuffer of type 3 for output id 74   
        SetBufferListener: "WorkThread1" for input ID 171with internal handoff   
        CallPrimeOutput on component "Sort" (72)   
    End Output Work List   
    This thread drives 0 distributors   
End WorkThread0   
WorkThread1   
    Influences: 158   
    Input Work list, input ID 171  
        CallProcessInput on input ID 171 on component "OLE DB Destination" (158) for view type 4  
    End Input Work list for input 171   
    Output Work List   
    End Output Work List   
    This thread drives 0 distributors   
End WorkThread1  
```  
  
> [!NOTE]  
>  <span data-ttu-id="a9473-115">Le plan d’exécution est généré chaque fois qu’un package est exécuté. Il peut être capturé en ajoutant un module fournisseur d’informations au package, en activant la journalisation et en sélectionnant l’événement **PipelineExecutionPlan**.</span><span class="sxs-lookup"><span data-stu-id="a9473-115">The execution plan is generated every time a package is executed, and can be captured by adding a log provider to the package, enabling logging, and selecting the **PipelineExecutionPlan** event.</span></span>  
  
## <a name="understanding-buffer-allocation"></a><span data-ttu-id="a9473-116">Fonctionnement de l'allocation de mémoire tampon</span><span class="sxs-lookup"><span data-stu-id="a9473-116">Understanding Buffer Allocation</span></span>  
 <span data-ttu-id="a9473-117">En fonction du plan d'exécution, la tâche de flux de données crée des mémoires tampons qui contiennent les colonnes définies dans les sorties des composants de flux de données.</span><span class="sxs-lookup"><span data-stu-id="a9473-117">Based on the execution plan, the data flow task creates buffers that contain the columns defined in the outputs of the data flow components.</span></span> <span data-ttu-id="a9473-118">La mémoire tampon est réutilisée tandis que les données transitent par la séquence de composants, jusqu'à ce qu'un composant à sorties asynchrones soit trouvé.</span><span class="sxs-lookup"><span data-stu-id="a9473-118">The buffer is reused as the data flows through the sequence of components, until a component with asynchronous outputs is encountered.</span></span> <span data-ttu-id="a9473-119">Puis, une nouvelle mémoire tampon est créée, qui contient les colonnes de sortie de la sortie asynchrone et les colonnes de sortie des composants en aval.</span><span class="sxs-lookup"><span data-stu-id="a9473-119">Then, a new buffer is created, which contains the output columns of the asynchronous output and the output columns of downstream components.</span></span>  
  
 <span data-ttu-id="a9473-120">Pendant l'exécution, les composants ont accès à la mémoire tampon dans le thread source ou de travail actuel.</span><span class="sxs-lookup"><span data-stu-id="a9473-120">During execution, components have access to the buffer in the current source or work thread.</span></span> <span data-ttu-id="a9473-121">Il peut s'agir d'une mémoire tampon d'entrée, fournie par la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>, ou d'une mémoire tampon de sortie, fournie par la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>.</span><span class="sxs-lookup"><span data-stu-id="a9473-121">The buffer is either an input buffer, provided by the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method, or an output buffer, provided by the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> method.</span></span> <span data-ttu-id="a9473-122">La propriété <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.Mode%2A> de <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> identifie également chaque mémoire tampon en tant que mémoire tampon d'entrée ou de sortie.</span><span class="sxs-lookup"><span data-stu-id="a9473-122">The <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.Mode%2A> property of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> also identifies each buffer as an input or output buffer.</span></span>  
  
 <span data-ttu-id="a9473-123">Les composants de transformation à sorties asynchrones reçoivent la mémoire tampon d'entrée existante via la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> et la nouvelle mémoire tampon de sortie via la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>.</span><span class="sxs-lookup"><span data-stu-id="a9473-123">Transformation components with asynchronous outputs receive the existing input buffer from the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method, and receive the new output buffer from the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> method.</span></span> <span data-ttu-id="a9473-124">Les composants de transformation à sorties asynchrones sont les seuls types de composants de flux de données qui reçoivent à la fois une mémoire tampon d'entrée et de sortie.</span><span class="sxs-lookup"><span data-stu-id="a9473-124">A transformation component with asynchronous outputs is the only type of data flow component that receives both an input and an output buffer.</span></span>  
  
 <span data-ttu-id="a9473-125">Comme la mémoire tampon fournie à un composant est susceptible de contenir un nombre de colonnes supérieur à celui que possède le composant dans ses collections de colonnes d'entrée et de sortie, les développeurs de composants peuvent appeler la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A> pour rechercher une colonne dans la mémoire tampon en spécifiant son `LineageID`.</span><span class="sxs-lookup"><span data-stu-id="a9473-125">Because the buffer provided to a component is likely to contain more columns than the component has in its input or output column collections, component developers can call the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A> method to locate a column in the buffer by specifying its `LineageID`.</span></span>  
  
<span data-ttu-id="a9473-126">![Icône de Integration Services (petite)](../../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="a9473-126">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="a9473-127">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="a9473-127">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="a9473-128">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="a9473-128">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="a9473-129">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="a9473-129">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
