---
title: Méthodes d’exécution d’un composant de flux de données | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- run-time [Integration Services]
- data flow components [Integration Services], run-time methods
ms.assetid: fd9e4317-18dd-43af-bbdc-79db32183ac4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: df0afe4c29044541c5a57aa3a466283ab4fe4fef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703203"
---
# <a name="run-time-methods-of-a-data-flow-component"></a><span data-ttu-id="cc21e-102">Méthodes d'exécution d'un composant de flux de données</span><span class="sxs-lookup"><span data-stu-id="cc21e-102">Run-time Methods of a Data Flow Component</span></span>
  <span data-ttu-id="cc21e-103">Au moment de l'exécution, la tâche de flux de données examine la séquence de composants, prépare un plan d'exécution et gère un pool de threads de travail qui exécute le plan de travail.</span><span class="sxs-lookup"><span data-stu-id="cc21e-103">At run time, the data flow task examines the sequence of components, prepares an execution plan, and manages a pool of worker threads that execute the work plan.</span></span> <span data-ttu-id="cc21e-104">La tâche charge des lignes de données à partir des sources, les traite via des transformations, puis les enregistre dans des destinations.</span><span class="sxs-lookup"><span data-stu-id="cc21e-104">The task loads rows of data from sources, processes them through transformations, then saves them to destinations.</span></span>  
  
## <a name="sequence-of-method-execution"></a><span data-ttu-id="cc21e-105">Séquence d'exécution des méthodes</span><span class="sxs-lookup"><span data-stu-id="cc21e-105">Sequence of Method Execution</span></span>  
 <span data-ttu-id="cc21e-106">Pendant l'exécution d'un composant de flux de données, un sous-ensemble des méthodes de la classe de base <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> est appelé.</span><span class="sxs-lookup"><span data-stu-id="cc21e-106">During the execution of a data flow component, a subset of the methods in the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> base class is called.</span></span> <span data-ttu-id="cc21e-107">Les méthodes, et l'ordre dans lequel elles sont appelées, sont toujours les mêmes, à l'exception des méthodes <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> et <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="cc21e-107">The methods, and the sequence in which they are called, are always the same, with the exception of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> and <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> methods.</span></span> <span data-ttu-id="cc21e-108">Ces deux méthodes sont appelées en fonction de l'existence et de la configuration des objets <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100> et <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> d'un composant.</span><span class="sxs-lookup"><span data-stu-id="cc21e-108">These two methods are called based on the existence and configuration of a component's <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100> and <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> objects.</span></span>  
  
 <span data-ttu-id="cc21e-109">La liste suivante présente les méthodes dans l'ordre dans lequel elles sont appelées pendant l'exécution d'un composant.</span><span class="sxs-lookup"><span data-stu-id="cc21e-109">The following list shows the methods in the order in which they are called during component execution.</span></span> <span data-ttu-id="cc21e-110">Notez que lorsqu'elle est appelée, la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> l'est toujours avant la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="cc21e-110">Note that <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>, when called, is always called before <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrepareForExecute%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PostExecute%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Cleanup%2A>  
  
### <a name="primeoutput-method"></a><span data-ttu-id="cc21e-111">Méthode PrimeOutput</span><span class="sxs-lookup"><span data-stu-id="cc21e-111">PrimeOutput Method</span></span>  
 <span data-ttu-id="cc21e-112">La méthode <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100.PrimeOutput%2A> est appelée lorsqu'un composant possède au moins une sortie, attachée à un composant en aval via un objet <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100> et lorsque la propriété <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.SynchronousInputID%2A> de la sortie est nulle.</span><span class="sxs-lookup"><span data-stu-id="cc21e-112">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100.PrimeOutput%2A> method is called when a component has at least one output, attached to a downstream component through an <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100> object, and the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.SynchronousInputID%2A> property of the output is zero.</span></span> <span data-ttu-id="cc21e-113">La méthode <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100.PrimeOutput%2A> est appelée pour les composants source et les transformations à sorties asynchrones.</span><span class="sxs-lookup"><span data-stu-id="cc21e-113">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100.PrimeOutput%2A> method is called for source components and for transformations with asynchronous outputs.</span></span> <span data-ttu-id="cc21e-114">Contrairement à la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> décrite ci-dessous, la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> est appelée une seule fois pour chaque composant qui la requiert.</span><span class="sxs-lookup"><span data-stu-id="cc21e-114">Unlike the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method described below, the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> method is only called once for each component that requires it.</span></span>  
  
### <a name="processinput-method"></a><span data-ttu-id="cc21e-115">Méthode ProcessInput</span><span class="sxs-lookup"><span data-stu-id="cc21e-115">ProcessInput Method</span></span>  
 <span data-ttu-id="cc21e-116">La méthode <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100.ProcessInput%2A> est appelée pour les composants qui possèdent au moins une entrée attachée à un composant en amont par un objet <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100>.</span><span class="sxs-lookup"><span data-stu-id="cc21e-116">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100.ProcessInput%2A> method is called for components that have at least one input attached to an upstream component by an <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100> object.</span></span> <span data-ttu-id="cc21e-117">La méthode <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100.ProcessInput%2A> est appelée pour les composants de destination et les transformations à sorties synchrones.</span><span class="sxs-lookup"><span data-stu-id="cc21e-117">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100.ProcessInput%2A> method is called for destination components and for transformations with synchronous outputs.</span></span> <span data-ttu-id="cc21e-118">l'<xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> est appelée à plusieurs reprises jusqu'à ce qu'il n'y ait plus aucune ligne à traiter à partir des composants en amont.</span><span class="sxs-lookup"><span data-stu-id="cc21e-118"><xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> is called repeatedly until there are no more rows to process from upstream components.</span></span>  
  
## <a name="working-with-inputs-and-outputs"></a><span data-ttu-id="cc21e-119">Utilisation des entrées et des sorties</span><span class="sxs-lookup"><span data-stu-id="cc21e-119">Working with Inputs and Outputs</span></span>  
 <span data-ttu-id="cc21e-120">Au moment de l'exécution, les composants de flux de données effectuent les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="cc21e-120">At run time, data flow components perform the following tasks:</span></span>  
  
-   <span data-ttu-id="cc21e-121">Les composants source ajoutent des lignes.</span><span class="sxs-lookup"><span data-stu-id="cc21e-121">Source components add rows.</span></span>  
  
-   <span data-ttu-id="cc21e-122">Les composants de transformation à sorties synchrones reçoivent les lignes fournies par les composants source.</span><span class="sxs-lookup"><span data-stu-id="cc21e-122">Transformation components with synchronous outputs receive rows provided by source components.</span></span>  
  
-   <span data-ttu-id="cc21e-123">Les composants de transformation à sorties asynchrones reçoivent des lignes et en ajoutent.</span><span class="sxs-lookup"><span data-stu-id="cc21e-123">Transformation components with asynchronous outputs receive rows and add rows.</span></span>  
  
-   <span data-ttu-id="cc21e-124">Les composants de destination reçoivent des lignes, puis les chargent dans une destination.</span><span class="sxs-lookup"><span data-stu-id="cc21e-124">Destination components receive rows and then load them into a destination.</span></span>  
  
 <span data-ttu-id="cc21e-125">Pendant l'exécution, la tâche de flux de données alloue des objets <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> qui contiennent toutes les colonnes définies dans les collections de colonnes de sortie d'une séquence de composants.</span><span class="sxs-lookup"><span data-stu-id="cc21e-125">During execution, the data flow task allocates <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> objects that contain all the columns defined in the output column collections of a sequence of components.</span></span> <span data-ttu-id="cc21e-126">Par exemple, si chacun des quatre composants d'une séquence de flux de données ajoute une colonne de sortie à sa collection de colonnes de sortie, le tampon fourni à chaque composant contient quatre colonnes, une pour chaque colonne de sortie par composant.</span><span class="sxs-lookup"><span data-stu-id="cc21e-126">For example, if each of four components in a data flow sequence adds one output column to its output column collection,the buffer that is provided to each component contains four columns, one for each output column per component.</span></span> <span data-ttu-id="cc21e-127">En raison de ce comportement, un composant reçoit parfois des tampons qui contiennent des colonnes qu'il n'utilise pas.</span><span class="sxs-lookup"><span data-stu-id="cc21e-127">Because of this behavior, a component sometimes receives buffers that contain columns it does not use.</span></span>  
  
 <span data-ttu-id="cc21e-128">Étant donné que les tampons reçus par votre composant peuvent contenir des colonnes que le composant n'utilisera pas, vous devez localiser les colonnes que vous souhaitez utiliser dans les collections de colonnes d'entrée et de sortie de votre composant dans le tampon fourni au composant par la tâche de flux de données.</span><span class="sxs-lookup"><span data-stu-id="cc21e-128">Since the buffers received by your component may contain columns that the component will not use, you must locate the columns that you want to use in your component's input and output column collections in the buffer provided to the component by the data flow task.</span></span> <span data-ttu-id="cc21e-129">Pour ce faire, vous utilisez la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A> de la propriété <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A>.</span><span class="sxs-lookup"><span data-stu-id="cc21e-129">You do this by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A> property.</span></span> <span data-ttu-id="cc21e-130">Pour des raisons liées aux performances, cette tâche s'effectue en général pendant la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A>, plutôt que pendant la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> ou <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="cc21e-130">For performance reasons, this task is ordinarily performed during the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> method, rather than in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> or <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span></span>  
  
 <span data-ttu-id="cc21e-131">La méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> est appelée avant les méthodes <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> et <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> et correspond à la première possibilité pour un composant d'effectuer ce travail une fois que la propriété <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A> est devenue disponible pour le composant.</span><span class="sxs-lookup"><span data-stu-id="cc21e-131"><xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> is called before the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> and <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> methods, and is the first opportunity for a component to perform this work after the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A> becomes available to the component.</span></span> <span data-ttu-id="cc21e-132">Pendant cette méthode, le composant doit localiser ses colonnes dans les tampons et stocker en interne ces informations afin que les colonnes puissent être utilisées dans les méthodes <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> ou <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="cc21e-132">During this method, the component should locate its columns in the buffers and store this information internally so the columns can be used in either the  <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> or <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> methods.</span></span>  
  
 <span data-ttu-id="cc21e-133">L'exemple de code suivant montre comment un composant de transformation à sortie synchrone localise ses colonnes d'entrée dans le tampon pendant la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A>.</span><span class="sxs-lookup"><span data-stu-id="cc21e-133">The following code example demonstrates how a transformation component with a synchronous output locates its input columns in the buffer during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A>.</span></span>  
  
```csharp  
private int []bufferColumnIndex;  
public override void PreExecute()  
{  
    IDTSInput100 input = ComponentMetaData.InputCollection[0];  
    bufferColumnIndex = new int[input.InputColumnCollection.Count];  
  
    for( int x=0; x < input.InputColumnCollection.Count; x++)  
    {  
        IDTSInputColumn100 column = input.InputColumnCollection[x];  
        bufferColumnIndex[x] = BufferManager.FindColumnByLineageID( input.Buffer, column.LineageID);  
    }  
}  
```  
  
```vb  
Dim bufferColumnIndex As Integer()  
  
    Public Overrides Sub PreExecute()  
  
        Dim input As IDTSInput100 = ComponentMetaData.InputCollection(0)  
  
        ReDim bufferColumnIndex(input.InputColumnCollection.Count)  
  
        For x As Integer = 0 To input.InputColumnCollection.Count  
  
            Dim column As IDTSInputColumn100 = input.InputColumnCollection(x)  
            bufferColumnIndex(x) = BufferManager.FindColumnByLineageID(input.Buffer, column.LineageID)  
  
        Next  
  
    End Sub  
```  
  
### <a name="adding-rows"></a><span data-ttu-id="cc21e-134">Ajout de lignes</span><span class="sxs-lookup"><span data-stu-id="cc21e-134">Adding Rows</span></span>  
 <span data-ttu-id="cc21e-135">Les composants fournissent des lignes aux composants en aval en ajoutant des lignes aux objets <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer>.</span><span class="sxs-lookup"><span data-stu-id="cc21e-135">Components supply rows to downstream components by adding rows to <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> objects.</span></span> <span data-ttu-id="cc21e-136">La tâche de flux de données fournit un tableau de tampons de sortie, un pour chaque objet <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> connecté à un composant en aval, en tant que paramètre de la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>.</span><span class="sxs-lookup"><span data-stu-id="cc21e-136">The data flow task provides an array of output buffers - one for each <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> object that is connected to a downstream component - as a parameter to the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> method.</span></span> <span data-ttu-id="cc21e-137">Les composants source et de transformation à sorties asynchrones ajoutent des lignes aux tampons et appellent la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.SetEndOfRowset%2A> lorsqu'ils ont terminé d'ajouter des lignes.</span><span class="sxs-lookup"><span data-stu-id="cc21e-137">Source components and transformation components with asynchronous outputs add rows to the buffers and call the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.SetEndOfRowset%2A> method when they are finished adding rows.</span></span> <span data-ttu-id="cc21e-138">La tâche de flux de données gère les tampons de sortie qu'elle fournit aux composants et, lorsque le tampon sature, déplace automatiquement les lignes incluses dans le tampon vers le composant suivant.</span><span class="sxs-lookup"><span data-stu-id="cc21e-138">The data flow task manages the output buffers that it supplies to components and, as a buffer becomes full, automatically moves the rows in the buffer to the next component.</span></span> <span data-ttu-id="cc21e-139">La méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> est appelée une fois par composant, contrairement à la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>, appelée à plusieurs reprises.</span><span class="sxs-lookup"><span data-stu-id="cc21e-139">The <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> method is called one time per component, unlike  the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method, which is called repeatedly.</span></span>  
  
 <span data-ttu-id="cc21e-140">L'exemple de code suivant montre comment un composant ajoute des lignes à ses tampons de sortie pendant la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>, puis appelle la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.SetEndOfRowset%2A>.</span><span class="sxs-lookup"><span data-stu-id="cc21e-140">The following code example demonstrates how a component adds rows to its output buffers during the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> method, then calls the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.SetEndOfRowset%2A> method.</span></span>  
  
```csharp  
public override void PrimeOutput( int outputs, int []outputIDs,PipelineBuffer []buffers)  
{  
    for( int x=0; x < outputs; x++ )  
    {  
        IDTSOutput100 output = ComponentMetaData.OutputCollection.GetObjectByID( outputIDs[x]);  
        PipelineBuffer buffer = buffers[x];  
  
        // TODO: Add rows to the output buffer.  
    }  
    foreach( PipelineBuffer buffer in buffers )  
    {  
        /// Notify the data flow task that no more rows are coming.  
        buffer.SetEndOfRowset();  
    }  
}  
```  
  
```vb  
public overrides sub PrimeOutput( outputs as Integer , outputIDs() as Integer ,buffers() as PipelineBuffer buffers)  
  
    For x As Integer = 0 To outputs.MaxValue  
  
        Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection.GetObjectByID(outputIDs(x))  
        Dim buffer As PipelineBuffer = buffers(x)  
  
        ' TODO: Add rows to the output buffer.  
  
    Next  
  
    For Each buffer As PipelineBuffer In buffers  
  
        ' Notify the data flow task that no more rows are coming.  
        buffer.SetEndOfRowset()  
  
    Next  
  
End Sub  
```  
  
 <span data-ttu-id="cc21e-141">Pour plus d’informations sur le développement de composants qui ajoutent des lignes aux mémoires tampons de sortie, consultez [Développement d’un composant source personnalisé](../../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md) et [Développement d’un composant de transformation personnalisé à sorties asynchrones](../../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-asynchronous-outputs.md).</span><span class="sxs-lookup"><span data-stu-id="cc21e-141">For more information about developing components that add rows to output buffers, see [Developing a Custom Source Component](../../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md) and [Developing a Custom Transformation Component with Asynchronous Outputs](../../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-asynchronous-outputs.md).</span></span>  
  
### <a name="receiving-rows"></a><span data-ttu-id="cc21e-142">Réception de lignes</span><span class="sxs-lookup"><span data-stu-id="cc21e-142">Receiving Rows</span></span>  
 <span data-ttu-id="cc21e-143">Les composants reçoivent des lignes provenant des composants en amont dans les objets <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer>.</span><span class="sxs-lookup"><span data-stu-id="cc21e-143">Components receive rows from upstream components in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> objects.</span></span> <span data-ttu-id="cc21e-144">La tâche de flux de données fournit un objet <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> qui contient les lignes ajoutées au flux de données par les composants en amont en tant que paramètre de la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="cc21e-144">The data flow task provides a <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> object that contains the rows added to the data flow by upstream components as a parameter to the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method.</span></span> <span data-ttu-id="cc21e-145">Ce tampon d'entrée peut être utilisé pour examiner et modifier les lignes et colonnes dans le tampon, mais il ne permet pas d'ajouter ou de supprimer des lignes.</span><span class="sxs-lookup"><span data-stu-id="cc21e-145">This input buffer can be used to examine and modify the rows and columns in the buffer, but cannot be used to add or remove rows.</span></span> <span data-ttu-id="cc21e-146">La méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> est appelée à plusieurs reprises jusqu'à ce qu'il n'y ait plus de tampon disponible.</span><span class="sxs-lookup"><span data-stu-id="cc21e-146">The <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method is called repeatedly until there are no more available buffers.</span></span> <span data-ttu-id="cc21e-147">Lors du dernier appel, la propriété <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.EndOfRowset%2A> a pour valeur `true`.</span><span class="sxs-lookup"><span data-stu-id="cc21e-147">The last time it is called, the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.EndOfRowset%2A> property is `true`.</span></span> <span data-ttu-id="cc21e-148">Vous pouvez parcourir la collection de lignes dans le tampon en utilisant la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.NextRow%2A>, qui permet d'accéder à la ligne suivante du tampon.</span><span class="sxs-lookup"><span data-stu-id="cc21e-148">You can iterate over the collection of rows in the buffer by using the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.NextRow%2A> method, which advances the buffer to the next row.</span></span> <span data-ttu-id="cc21e-149">Cette méthode retourne `false` lorsque le tampon est sur la dernière ligne de la collection.</span><span class="sxs-lookup"><span data-stu-id="cc21e-149">This method returns `false` when the buffer is on the last row in the collection.</span></span> <span data-ttu-id="cc21e-150">Vous n'avez pas à vérifier la propriété <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.EndOfRowset%2A> sauf si vous devez effectuer une action supplémentaire une fois que les dernières lignes de données ont été traitées.</span><span class="sxs-lookup"><span data-stu-id="cc21e-150">You do not have to check the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.EndOfRowset%2A> property unless you have to perform an additional action after the last rows of data have been processed.</span></span>  
  
 <span data-ttu-id="cc21e-151">Le texte suivant illustre le modèle correct pour l'utilisation de la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.NextRow%2A> et de la propriété <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.EndOfRowset%2A> :</span><span class="sxs-lookup"><span data-stu-id="cc21e-151">The following text shows the correct pattern for using the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.NextRow%2A> method and the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.EndOfRowset%2A> property:</span></span>  
  
 `while (buffer.NextRow())`  
  
 `{`  
  
 `// Do something with each row.`  
  
 `}`  
  
 `if (buffer.EndOfRowset)`  
  
 `{`  
  
 `// Optionally, do something after all rows have been processed.`  
  
 `}`  
  
 <span data-ttu-id="cc21e-152">L'exemple de code suivant montre comment un composant traite les lignes dans les tampons d'entrée pendant la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="cc21e-152">The following code example demonstrates how a component processes the rows in input buffers during the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method.</span></span>  
  
```csharp  
public override void ProcessInput( int inputID, PipelineBuffer buffer )  
{  
    {  
        IDTSInput100 input = ComponentMetaData.InputCollection.GetObjectByID(inputID);  
        while( buffer.NextRow())  
        {  
            // TODO: Examine the columns in the current row.  
        }  
}  
```  
  
```vb  
Public Overrides Sub ProcessInput(ByVal inputID As Integer, ByVal buffer As PipelineBuffer)  
  
        Dim input As IDTSInput100 = ComponentMetaData.InputCollection.GetObjectByID(inputID)  
        While buffer.NextRow() = True  
  
            ' TODO: Examine the columns in the current row.  
        End While  
  
End Sub  
```  
  
 <span data-ttu-id="cc21e-153">Pour plus d’informations sur le développement de composants qui reçoivent des lignes dans les mémoires tampons d’entrée, consultez [Développement d’un composant de destination personnalisé](../../extending-packages-custom-objects-data-flow-types/developing-a-custom-destination-component.md) et [Développement d’un composant de transformation personnalisé à sorties asynchrones](../../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-synchronous-outputs.md).</span><span class="sxs-lookup"><span data-stu-id="cc21e-153">For more information about developing components that receive rows in input buffers, see [Developing a Custom Destination Component](../../extending-packages-custom-objects-data-flow-types/developing-a-custom-destination-component.md) and [Developing a Custom Transformation Component with Synchronous Outputs](../../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-synchronous-outputs.md).</span></span>  
  
<span data-ttu-id="cc21e-154">![Icône de Integration Services (petite)](../../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="cc21e-154">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="cc21e-155">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="cc21e-155">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="cc21e-156">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="cc21e-156">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="cc21e-157">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="cc21e-157">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc21e-158">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cc21e-158">See Also</span></span>  
 [<span data-ttu-id="cc21e-159">Méthodes de conception d'un composant de flux de données</span><span class="sxs-lookup"><span data-stu-id="cc21e-159">Design-time Methods of a Data Flow Component</span></span>](design-time-methods-of-a-data-flow-component.md)  
  
  
