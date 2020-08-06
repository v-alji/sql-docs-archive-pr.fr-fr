---
title: Développement d’un composant de transformation personnalisé avec des sorties asynchrones | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- custom data flow components [Integration Services], transformation components
- asynchronous outputs [Integration Services]
- ProcessInput method
- cache [Integration Services]
- buffer allocations [Integration Services]
- transformation components [Integration Services]
- output columns [Integration Services]
- PrimeOutput method
- data flow components [Integration Services], transformation components
ms.assetid: 1c3e92c7-a4fa-4fdd-b9ca-ac3069536274
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 41e2ecdf9f90765e75ff2b8c9c0681a25366e080
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705316"
---
# <a name="developing-a-custom-transformation-component-with-asynchronous-outputs"></a><span data-ttu-id="4c13f-102">Développement d'un composant de transformation personnalisé à sorties asynchrones</span><span class="sxs-lookup"><span data-stu-id="4c13f-102">Developing a Custom Transformation Component with Asynchronous Outputs</span></span>
  <span data-ttu-id="4c13f-103">Vous utilisez un composant à sorties asynchrones lorsqu'une transformation ne peut pas extraire de lignes tant que le composant n'a pas reçu toutes ses lignes d'entrée, ou lorsqu'une transformation ne génère pas exactement une ligne de sortie pour chaque ligne reçue en tant qu'entrée.</span><span class="sxs-lookup"><span data-stu-id="4c13f-103">You use a component with asynchronous outputs when a transform cannot output rows until the component has received all its input rows, or when the transformation does not produce exactly one output row for each row received as input.</span></span> <span data-ttu-id="4c13f-104">La transformation d'agrégation, par exemple, ne peut pas calculer une somme de lignes tant qu'elle n'a pas lu toutes les lignes.</span><span class="sxs-lookup"><span data-stu-id="4c13f-104">The Aggregate transformation, for example, cannot calculate a sum across rows until it has read all the rows.</span></span> <span data-ttu-id="4c13f-105">Par opposition, vous pouvez utiliser un composant à sorties synchrones lorsque vous modifiez chaque ligne de données au moment de leur transfert.</span><span class="sxs-lookup"><span data-stu-id="4c13f-105">In contrast, you can use a component with synchronous outputs any time when you modify each row of data as it passes through.</span></span> <span data-ttu-id="4c13f-106">Vous pouvez modifier les données de chaque ligne en place ou créer une ou plusieurs colonnes, chacune contenant une valeur pour chaque ligne d'entrée.</span><span class="sxs-lookup"><span data-stu-id="4c13f-106">You can modify the data for each row in place, or you can create one or more new columns, each of which has a value for every one of the input rows.</span></span> <span data-ttu-id="4c13f-107">Pour plus d’informations sur la différence entre les composants synchrones et asynchrones, consultez [Présentation des transformations synchrones et asynchrones](../understanding-synchronous-and-asynchronous-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="4c13f-107">For more information about the difference between synchronous and asynchronous components, see [Understanding Synchronous and Asynchronous Transformations](../understanding-synchronous-and-asynchronous-transformations.md).</span></span>

 <span data-ttu-id="4c13f-108">Les composants de transformation à sorties asynchrones sont uniques dans la mesure où ils font office à la fois de composants sources et de composants de destination.</span><span class="sxs-lookup"><span data-stu-id="4c13f-108">Transformation components with asynchronous outputs are unique because they act as both destination and source components.</span></span> <span data-ttu-id="4c13f-109">Ce type de composant reçoit des lignes des composants en amont et ajoute des lignes utilisées par les composants en aval.</span><span class="sxs-lookup"><span data-stu-id="4c13f-109">This kind of component receives rows from upstream components, and adds rows that are consumed by downstream components.</span></span> <span data-ttu-id="4c13f-110">Aucun autre composant de flux de données n'effectue ces deux opérations.</span><span class="sxs-lookup"><span data-stu-id="4c13f-110">No other data flow component performs both of these operations.</span></span>

 <span data-ttu-id="4c13f-111">Les colonnes des composants en amont disponibles pour un composant à sorties synchrones sont automatiquement accessibles aux composants situés en aval du composant.</span><span class="sxs-lookup"><span data-stu-id="4c13f-111">The columns from upstream components that are available to a component with synchronous outputs are automatically available to components downstream from the component.</span></span> <span data-ttu-id="4c13f-112">Par conséquent, un composant à sorties synchrones n'a pas besoin de définir de colonne de sortie pour fournir des colonnes et des lignes au composant suivant.</span><span class="sxs-lookup"><span data-stu-id="4c13f-112">Therefore, a component with synchronous outputs does not have to define any output columns to provide columns and rows to the next component.</span></span> <span data-ttu-id="4c13f-113">Les composants à sorties asynchrones, en revanche, doivent définir des colonnes de sortie et fournir des lignes aux composants en aval.</span><span class="sxs-lookup"><span data-stu-id="4c13f-113">Components with asynchronous outputs, on the other hand, must define output columns and provide rows to downstream components.</span></span> <span data-ttu-id="4c13f-114">Par conséquent, un composant à sorties asynchrones doit exécuter un plus grand nombre de tâches au moment de la conception et de l'exécution, et le développeur de composants doit implémenter davantage de code.</span><span class="sxs-lookup"><span data-stu-id="4c13f-114">Therefore a component with asynchronous outputs has more tasks to perform during both design and execution time, and the component developer has more code to implement.</span></span>

 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="4c13f-115">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] contient plusieurs transformations à sorties asynchrones.</span><span class="sxs-lookup"><span data-stu-id="4c13f-115">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] contains several transformations with asynchronous outputs.</span></span> <span data-ttu-id="4c13f-116">Par exemple, la transformation de tri requiert toutes ses lignes avant de pouvoir les trier et elle utilise pour cela des sorties asynchrones.</span><span class="sxs-lookup"><span data-stu-id="4c13f-116">For example, the Sort transformation requires all its rows before it can sort them, and achieves this by using asynchronous outputs.</span></span> <span data-ttu-id="4c13f-117">Une fois qu'elle a reçu toutes ses lignes, elle les trie et les ajoute à sa sortie.</span><span class="sxs-lookup"><span data-stu-id="4c13f-117">After it has received all its rows, it sorts them and adds them to its output.</span></span>

 <span data-ttu-id="4c13f-118">Cette section explique en détail comment développer des transformations à sorties asynchrones.</span><span class="sxs-lookup"><span data-stu-id="4c13f-118">This section explains in detail how to develop transformations with asynchronous outputs.</span></span> <span data-ttu-id="4c13f-119">Pour plus d’informations sur le développement de composants sources, consultez [Développement d’un composant source personnalisé](../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md).</span><span class="sxs-lookup"><span data-stu-id="4c13f-119">For more information about source component development, see [Developing a Custom Source Component](../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md).</span></span>

## <a name="design-time"></a><span data-ttu-id="4c13f-120">Moment de la conception</span><span class="sxs-lookup"><span data-stu-id="4c13f-120">Design Time</span></span>

### <a name="creating-the-component"></a><span data-ttu-id="4c13f-121">Création du composant</span><span class="sxs-lookup"><span data-stu-id="4c13f-121">Creating the Component</span></span>
 <span data-ttu-id="4c13f-122">La propriété <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.SynchronousInputID%2A> sur l'objet <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> détermine si une sortie est synchrone ou asynchrone.</span><span class="sxs-lookup"><span data-stu-id="4c13f-122">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.SynchronousInputID%2A> property on the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> object identifies whether an output is synchronous or asynchronous.</span></span> <span data-ttu-id="4c13f-123">Pour créer une sortie asynchrone, ajoutez la sortie au composant et attribuez la valeur zéro à <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.SynchronousInputID%2A>.</span><span class="sxs-lookup"><span data-stu-id="4c13f-123">To create an asynchronous output, add the output to the component and set the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.SynchronousInputID%2A> to zero.</span></span> <span data-ttu-id="4c13f-124">La définition de cette propriété détermine également si la tâche de flux alloue des objets <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> à l'entrée et la sortie du composant, ou si une seule mémoire tampon est allouée et partagée entre les deux objets.</span><span class="sxs-lookup"><span data-stu-id="4c13f-124">Setting this property also determines whether the data flow task allocates <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> objects for both the input and output of the component, or whether a single buffer is allocated and shared between the two objects.</span></span>

 <span data-ttu-id="4c13f-125">L'exemple de code suivant affiche un composant qui crée une sortie asynchrone dans son implémentation <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A>.</span><span class="sxs-lookup"><span data-stu-id="4c13f-125">The following sample code shows a component that creates an asynchronous output in its <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> implementation.</span></span>

```csharp
using Microsoft.SqlServer.Dts.Pipeline;
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;
using Microsoft.SqlServer.Dts.Runtime;

namespace Microsoft.Samples.SqlServer.Dts
{
    [DtsPipelineComponent(DisplayName = "AsyncComponent",ComponentType = ComponentType.Transform)]
    public class AsyncComponent : PipelineComponent
    {
        public override void ProvideComponentProperties()
        {
            // Call the base class, which adds a synchronous input
            // and output.
            base.ProvideComponentProperties();

            // Make the output asynchronous.
            IDTSOutput100 output = ComponentMetaData.OutputCollection[0];
            output.SynchronousInputID = 0;
        }
    }
}
```

```vb
Imports Microsoft.SqlServer.Dts.Pipeline
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper
Imports Microsoft.SqlServer.Dts.Runtime

<DtsPipelineComponent(DisplayName:="AsyncComponent", ComponentType:=ComponentType.Transform)> _
Public Class AsyncComponent
    Inherits PipelineComponent

    Public Overrides Sub ProvideComponentProperties()

        ' Call the base class, which adds a synchronous input
        ' and output.
        Me.ProvideComponentProperties()

        ' Make the output asynchronous.
        Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection(0)
        output.SynchronousInputID = 0

    End Sub

End Class
```

### <a name="creating-and-configuring-output-columns"></a><span data-ttu-id="4c13f-126">Création et configuration de colonnes de sortie</span><span class="sxs-lookup"><span data-stu-id="4c13f-126">Creating and Configuring Output Columns</span></span>
 <span data-ttu-id="4c13f-127">Comme nous l'avons déjà mentionné, un composant asynchrone ajoute des colonnes à sa collection de colonnes de sortie pour fournir des colonnes aux composants en aval.</span><span class="sxs-lookup"><span data-stu-id="4c13f-127">As mentioned earlier, an asynchronous component adds columns to its output column collection to provide columns to downstream components.</span></span> <span data-ttu-id="4c13f-128">Vous pouvez choisir entre plusieurs méthodes au moment de la conception, en fonction des besoins du composant.</span><span class="sxs-lookup"><span data-stu-id="4c13f-128">There are several design-time methods to choose from, depending on the needs of the component.</span></span> <span data-ttu-id="4c13f-129">Par exemple, si vous souhaitez transférer toutes les colonnes des composants en amont aux composants en aval, vous devez substituer la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.OnInputPathAttached%2A> pour ajouter les colonnes, car il s'agit de la première méthode dans laquelle les colonnes d'entrée sont accessibles au composant.</span><span class="sxs-lookup"><span data-stu-id="4c13f-129">For example, if you want to pass all the columns from the upstream components to the downstream components, you would override the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.OnInputPathAttached%2A> method to add the columns, because this is the first method in which the input columns are available to the component.</span></span>

 <span data-ttu-id="4c13f-130">Si le composant crée des colonnes de sortie en fonction des colonnes sélectionnées pour son entrée, substituez la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.SetUsageType%2A> pour sélectionner les colonnes de sortie et indiquer comment elles doivent être utilisées.</span><span class="sxs-lookup"><span data-stu-id="4c13f-130">If the component creates output columns based on the columns selected for its input, override the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.SetUsageType%2A> method to select the output columns and to indicate how they will be used.</span></span>

 <span data-ttu-id="4c13f-131">Si un composant à sorties asynchrones crée des colonnes de sortie basées sur les colonnes de composants en amont et que les colonnes disponibles en amont sont modifiées, le composant doit mettre à jour sa collection de colonnes de sortie.</span><span class="sxs-lookup"><span data-stu-id="4c13f-131">If a component with asynchronous outputs creates output columns based on the columns from upstream components, and the available upstream columns change, the component should update its output column collection.</span></span> <span data-ttu-id="4c13f-132">Ces modifications doivent être détectées par le composant pendant l'exécution de la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A> et corrigées pendant l'exécution de la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReinitializeMetaData%2A>.</span><span class="sxs-lookup"><span data-stu-id="4c13f-132">These changes should be detected by the component during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A>, and fixed during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReinitializeMetaData%2A>.</span></span>

> [!NOTE]
>  <span data-ttu-id="4c13f-133">Lorsqu'une colonne de sortie est supprimée de la collection de colonnes de sortie, les composants en aval dans le flux de données qui font référence à cette colonne sont affectés de façon négative.</span><span class="sxs-lookup"><span data-stu-id="4c13f-133">When an output column is removed from the output column collection, downstream components in the data flow that reference the column are adversely affected.</span></span> <span data-ttu-id="4c13f-134">La colonne de sortie doit être réparée sans être supprimée ni recréée pour empêcher l'arrêt des composants en aval.</span><span class="sxs-lookup"><span data-stu-id="4c13f-134">The output column must be repaired without removing and recreating the column to prevent breaking the downstream components.</span></span> <span data-ttu-id="4c13f-135">Par exemple, si le type de données de la colonne a été modifié, vous devez le mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="4c13f-135">For example, if the data type of the column has changed, you must update the data type.</span></span>

 <span data-ttu-id="4c13f-136">L'exemple de code suivant montre un composant qui ajoute une colonne de sortie à sa collection de colonnes de sortie pour chaque colonne disponible à partir du composant en amont.</span><span class="sxs-lookup"><span data-stu-id="4c13f-136">The following code example shows a component that adds an output column to its output column collection for each column available from the upstream component.</span></span>

```csharp
public override void OnInputPathAttached(int inputID)
{
   IDTSInput100 input = ComponentMetaData.InputCollection.GetObjectByID(inputID);
   IDTSOutput100 output = ComponentMetaData.OutputCollection[0];
   IDTSVirtualInput100 vInput = input.GetVirtualInput();

   foreach (IDTSVirtualInputColumn100 vCol in vInput.VirtualInputColumnCollection)
   {
      IDTSOutputColumn100 outCol = output.OutputColumnCollection.New();
      outCol.Name = vCol.Name;
      outCol.SetDataTypeProperties(vCol.DataType, vCol.Length, vCol.Precision, vCol.Scale, vCol.CodePage);
   }
}
```

```vb
Public Overrides Sub OnInputPathAttached(ByVal inputID As Integer)

    Dim input As IDTSInput100 = ComponentMetaData.InputCollection.GetObjectByID(inputID)
    Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection(0)
    Dim vInput As IDTSVirtualInput100 = input.GetVirtualInput()

    For Each vCol As IDTSVirtualInputColumn100 In vInput.VirtualInputColumnCollection

        Dim outCol As IDTSOutputColumn100 = output.OutputColumnCollection.New()
        outCol.Name = vCol.Name
        outCol.SetDataTypeProperties(vCol.DataType, vCol.Length, vCol.Precision, vCol.Scale, vCol.CodePage)

    Next
End Sub
```

## <a name="run-time"></a><span data-ttu-id="4c13f-137">Moment de l'exécution</span><span class="sxs-lookup"><span data-stu-id="4c13f-137">Run Time</span></span>
 <span data-ttu-id="4c13f-138">Les composants à sorties asynchrones exécutent également une séquence de méthodes au moment de l'exécution qui diffère des autres types de composants.</span><span class="sxs-lookup"><span data-stu-id="4c13f-138">Components with asynchronous outputs also execute a different sequence of methods at run time than other types of components.</span></span> <span data-ttu-id="4c13f-139">En premier lieu, ce sont les seuls composants qui reçoivent un appel des méthodes <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> et <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="4c13f-139">First, they are the only components that receive a call to both the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> and the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> methods.</span></span> <span data-ttu-id="4c13f-140">Les composants à sorties asynchrones requièrent également l'accès à toutes les lignes entrantes avant de pouvoir commencer le traitement. Ils doivent donc mettre en cache les lignes d'entrée en interne jusqu'à ce que toutes les lignes aient été lues.</span><span class="sxs-lookup"><span data-stu-id="4c13f-140">Components with asynchronous outputs also require access to all the incoming rows before they can start processing; therefore, they must cache the input rows internally until all rows have been read.</span></span> <span data-ttu-id="4c13f-141">Enfin, les composants à sorties asynchrones reçoivent une mémoire tampon d'entrée et une mémoire tampon de sortie, contrairement aux autres composants.</span><span class="sxs-lookup"><span data-stu-id="4c13f-141">Finally, unlike other components, components with asynchronous outputs receive both an input buffer and an output buffer.</span></span>

### <a name="understanding-the-buffers"></a><span data-ttu-id="4c13f-142">Fonctionnement des mémoires tampons</span><span class="sxs-lookup"><span data-stu-id="4c13f-142">Understanding the Buffers</span></span>
 <span data-ttu-id="4c13f-143">Le composant reçoit la mémoire tampon d'entrée au moment de l'exécution de la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="4c13f-143">The input buffer is received by the component during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span></span> <span data-ttu-id="4c13f-144">Cette mémoire tampon contient les lignes ajoutées par les composants en amont.</span><span class="sxs-lookup"><span data-stu-id="4c13f-144">This buffer contains the rows added to the buffer by upstream components.</span></span> <span data-ttu-id="4c13f-145">La mémoire tampon contient également les colonnes de l'entrée du composant, en plus des colonnes qui ont été fournies dans la sortie d'un composant en amont mais qui n'ont pas été ajoutées à la collection d'entrée du composant asynchrone.</span><span class="sxs-lookup"><span data-stu-id="4c13f-145">The buffer also contains the columns of the component's input, in addition to the columns that were provided in the output of an upstream component but were not added to the asynchronous component's input collection.</span></span>

 <span data-ttu-id="4c13f-146">La mémoire tampon de sortie, fournie au composant dans <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>, ne contient pas de ligne initialement.</span><span class="sxs-lookup"><span data-stu-id="4c13f-146">The output buffer, which is provided to the component in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>, does not initially contain rows.</span></span> <span data-ttu-id="4c13f-147">Le composant ajoute des lignes à cette mémoire tampon et fournit cette dernière aux composants en aval lorsqu'elle est pleine.</span><span class="sxs-lookup"><span data-stu-id="4c13f-147">The component adds rows to this buffer and provides the buffer to downstream components when it is full.</span></span> <span data-ttu-id="4c13f-148">La mémoire tampon de sortie contient les colonnes définies dans la collection de colonnes de sortie du composant, en plus des colonnes que d'autres composants en aval ont ajoutées à leurs sorties.</span><span class="sxs-lookup"><span data-stu-id="4c13f-148">The output buffer contains the columns defined in the component's output column collection, in addition to any columns that other downstream components have added to their outputs.</span></span>

 <span data-ttu-id="4c13f-149">Ce comportement diffère de celui des composants à sorties synchrones, qui reçoivent une seule mémoire tampon partagée.</span><span class="sxs-lookup"><span data-stu-id="4c13f-149">This is different behavior from that of components with synchronous outputs, which receive a single shared buffer.</span></span> <span data-ttu-id="4c13f-150">La mémoire tampon partagée d'un composant à sorties synchrones contient les colonnes d'entrée et de sortie du composant, en plus des colonnes ajoutées aux sorties des composants en amont et en aval.</span><span class="sxs-lookup"><span data-stu-id="4c13f-150">The shared buffer of a component with synchronous outputs contains both the input and output columns of the component, in addition to columns added to the outputs of upstream and downstream components.</span></span>

### <a name="processing-rows"></a><span data-ttu-id="4c13f-151">Traitement de lignes</span><span class="sxs-lookup"><span data-stu-id="4c13f-151">Processing Rows</span></span>

#### <a name="caching-input-rows"></a><span data-ttu-id="4c13f-152">Mise en cache de lignes d'entrée</span><span class="sxs-lookup"><span data-stu-id="4c13f-152">Caching Input Rows</span></span>
 <span data-ttu-id="4c13f-153">Lorsque vous écrivez un composant à sorties asynchrones, vous avez le choix entre trois options pour ajouter des lignes à la mémoire tampon de sortie.</span><span class="sxs-lookup"><span data-stu-id="4c13f-153">When you write a component with asynchronous outputs, you have three options for adding rows to the output buffer.</span></span> <span data-ttu-id="4c13f-154">Vous pouvez les ajouter au moment de la réception des lignes d'entrée, les mettre en cache jusqu'à ce que le composant ait reçu toutes les lignes du composant en amont ou les ajouter au moment approprié pour le composant.</span><span class="sxs-lookup"><span data-stu-id="4c13f-154">You can add them as input rows are received, you can cache them until the component has received all the rows from the upstream component, or you can add them when it is appropriate to do so for the component.</span></span> <span data-ttu-id="4c13f-155">La méthode choisie dépend des exigences du composant.</span><span class="sxs-lookup"><span data-stu-id="4c13f-155">The method that you choose depends on the requirements of the component.</span></span> <span data-ttu-id="4c13f-156">Par exemple, le composant Sort requiert que toutes les lignes en amont soient reçues avant d'être triées.</span><span class="sxs-lookup"><span data-stu-id="4c13f-156">For example, the Sort component requires that all the upstream rows be received before they can be sorted.</span></span> <span data-ttu-id="4c13f-157">Par conséquent, il attend que toutes les lignes aient été lues avant d'ajouter des lignes à la mémoire tampon de sortie.</span><span class="sxs-lookup"><span data-stu-id="4c13f-157">Therefore, it waits until all rows have been read before adding rows to the output buffer.</span></span>

 <span data-ttu-id="4c13f-158">Les lignes reçues dans la mémoire tampon d'entrée doivent être mises en cache en interne par le composant en attendant qu'il soit prêt à les traiter.</span><span class="sxs-lookup"><span data-stu-id="4c13f-158">The rows that are received in the input buffer must be cached internally by the component until it is ready to process them.</span></span> <span data-ttu-id="4c13f-159">Les lignes entrantes de la mémoire tampon peuvent être mises en cache dans une table de données, un tableau multidimensionnel ou toute autre structure interne.</span><span class="sxs-lookup"><span data-stu-id="4c13f-159">The incoming buffer rows can be cached in a data table, a multidimensional array, or any other internal structure.</span></span>

#### <a name="adding-output-rows"></a><span data-ttu-id="4c13f-160">Ajout de lignes de sortie</span><span class="sxs-lookup"><span data-stu-id="4c13f-160">Adding Output Rows</span></span>
 <span data-ttu-id="4c13f-161">Si vous ajoutez des lignes à la mémoire tampon de sortie dès leur réception ou une fois que toutes les lignes ont été reçues, vous appelez pour cela la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.AddRow%2A> sur la mémoire tampon de sortie.</span><span class="sxs-lookup"><span data-stu-id="4c13f-161">Whether you add rows to the output buffer as they are received or after receiving all of the rows, you do so by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.AddRow%2A> method on the output buffer.</span></span> <span data-ttu-id="4c13f-162">Après avoir ajouté la ligne, vous définissez les valeurs de chaque colonne dans la nouvelle ligne.</span><span class="sxs-lookup"><span data-stu-id="4c13f-162">After you have added the row, you set the values of each column in the new row.</span></span>

 <span data-ttu-id="4c13f-163">Étant donné que la mémoire tampon de sortie contient parfois plus de colonnes que la collection de colonnes de sortie du composant, vous devez rechercher l'index de la colonne appropriée dans la mémoire tampon avant de définir sa valeur.</span><span class="sxs-lookup"><span data-stu-id="4c13f-163">Because there are sometimes more columns in the output buffer than in the output column collection of the component, you must locate the index of the appropriate column in the buffer before you can set its value.</span></span> <span data-ttu-id="4c13f-164">La méthode <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A> de la propriété <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A> retourne l'index de la colonne dans la ligne de la mémoire tampon avec l'ID de lignage spécifié, qui permet ensuite d'assigner la valeur à la colonne de la mémoire tampon.</span><span class="sxs-lookup"><span data-stu-id="4c13f-164">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A> property returns the index of the column in the buffer row with the specified lineage ID, which is then used to assign the value to the buffer column.</span></span>

 <span data-ttu-id="4c13f-165">La méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A>, appelée avant la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> ou la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> est la première qui permet d'accéder à la propriété <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A> et qui offre la possibilité de rechercher les index des colonnes dans les mémoires tampons d'entrée et de sortie.</span><span class="sxs-lookup"><span data-stu-id="4c13f-165">The <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> method, which is called before the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> method or the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method, is the first method where the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A> property is available, and the first opportunity to locate the indexes of the columns in the input and output buffers.</span></span>

## <a name="sample"></a><span data-ttu-id="4c13f-166">Exemple</span><span class="sxs-lookup"><span data-stu-id="4c13f-166">Sample</span></span>
 <span data-ttu-id="4c13f-167">L'exemple suivant montre un composant de transformation simple à sorties asynchrones qui ajoute des lignes à la mémoire tampon de sortie au moment où elles sont reçues.</span><span class="sxs-lookup"><span data-stu-id="4c13f-167">The following sample shows a simple transformation component with asynchronous outputs that adds rows to the output buffer as they are received.</span></span> <span data-ttu-id="4c13f-168">Cet exemple ne contient pas toutes les méthodes et fonctionnalités présentées dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="4c13f-168">This sample does not demonstrate all the methods and functionality discussed in this topic.</span></span> <span data-ttu-id="4c13f-169">Il illustre les méthodes importantes que chaque composant de transformation personnalisé à sorties asynchrones doit substituer, mais ne contient pas de code pour la validation au moment de la conception.</span><span class="sxs-lookup"><span data-stu-id="4c13f-169">It demonstrates the important methods that every custom transformation component with asynchronous outputs must override, but does not contain code for design-time validation.</span></span> <span data-ttu-id="4c13f-170">Par ailleurs, le code dans <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> suppose que la collection de colonnes de sortie possède une colonne pour chaque colonne dans la collection de colonnes d'entrée.</span><span class="sxs-lookup"><span data-stu-id="4c13f-170">Also, the code in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> assumes that the output column collection has one column for each column in the input column collection.</span></span>

```csharp
using System;
using Microsoft.SqlServer.Dts.Pipeline;
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;
using Microsoft.SqlServer.Dts.Runtime.Wrapper;

namespace Microsoft.Samples.SqlServer.Dts
{
   [DtsPipelineComponent(DisplayName = "AsynchronousOutput")]
   public class AsynchronousOutput : PipelineComponent
   {
      PipelineBuffer outputBuffer;
      int[] inputColumnBufferIndexes;
      int[] outputColumnBufferIndexes;

      public override void ProvideComponentProperties()
      {
         // Let the base class add the input and output objects.
         base.ProvideComponentProperties();

         // Name the input and output, and make the
         // output asynchronous.
         ComponentMetaData.InputCollection[0].Name = "Input";
         ComponentMetaData.OutputCollection[0].Name = "AsyncOutput";
         ComponentMetaData.OutputCollection[0].SynchronousInputID = 0;
      }
      public override void PreExecute()
      {
         IDTSInput100 input = ComponentMetaData.InputCollection[0];
         IDTSOutput100 output = ComponentMetaData.OutputCollection[0];

         inputColumnBufferIndexes = new int[input.InputColumnCollection.Count];
         outputColumnBufferIndexes = new int[output.OutputColumnCollection.Count];

         for (int col = 0; col < input.InputColumnCollection.Count; col++)
            inputColumnBufferIndexes[col] = BufferManager.FindColumnByLineageID(input.Buffer, input.InputColumnCollection[col].LineageID);

         for (int col = 0; col < output.OutputColumnCollection.Count; col++)
            outputColumnBufferIndexes[col] = BufferManager.FindColumnByLineageID(output.Buffer, output.OutputColumnCollection[col].LineageID);

      }

      public override void PrimeOutput(int outputs, int[] outputIDs, PipelineBuffer[] buffers)
      {
         if (buffers.Length != 0)
            outputBuffer = buffers[0];
      }
      public override void ProcessInput(int inputID, PipelineBuffer buffer)
      {
            // Advance the buffer to the next row.
            while (buffer.NextRow())
            {
               // Add a row to the output buffer.
               outputBuffer.AddRow();
               for (int x = 0; x < inputColumnBufferIndexes.Length; x++)
               {
                  // Copy the data from the input buffer column to the output buffer column.
                  outputBuffer[outputColumnBufferIndexes[x]] = buffer[inputColumnBufferIndexes[x]];
               }
            }
         if (buffer.EndOfRowset)
         {
            // EndOfRowset on the input buffer is true.
            // Set EndOfRowset on the output buffer.
            outputBuffer.SetEndOfRowset();
         }
      }
   }
}
```

```vb
Imports System
Imports Microsoft.SqlServer.Dts.Pipeline
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper
Imports Microsoft.SqlServer.Dts.Runtime.Wrapper

Namespace Microsoft.Samples.SqlServer.Dts

    <DtsPipelineComponent(DisplayName:="AsynchronousOutput")> _
    Public Class AsynchronousOutput

        Inherits PipelineComponent

        Private outputBuffer As PipelineBuffer
        Private inputColumnBufferIndexes As Integer()
        Private outputColumnBufferIndexes As Integer()

        Public Overrides Sub ProvideComponentProperties()

            ' Let the base class add the input and output objects.
            Me.ProvideComponentProperties()

            ' Name the input and output, and make the
            ' output asynchronous.
            ComponentMetaData.InputCollection(0).Name = "Input"
            ComponentMetaData.OutputCollection(0).Name = "AsyncOutput"
            ComponentMetaData.OutputCollection(0).SynchronousInputID = 0
        End Sub

        Public Overrides Sub PreExecute()

            Dim input As IDTSInput100 = ComponentMetaData.InputCollection(0)
            Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection(0)

            ReDim inputColumnBufferIndexes(input.InputColumnCollection.Count)
            ReDim outputColumnBufferIndexes(output.OutputColumnCollection.Count)

            For col As Integer = 0 To input.InputColumnCollection.Count
                inputColumnBufferIndexes(col) = BufferManager.FindColumnByLineageID(input.Buffer, input.InputColumnCollection(col).LineageID)
            Next

            For col As Integer = 0 To output.OutputColumnCollection.Count
                outputColumnBufferIndexes(col) = BufferManager.FindColumnByLineageID(output.Buffer, output.OutputColumnCollection(col).LineageID)
            Next

        End Sub
        Public Overrides Sub PrimeOutput(ByVal outputs As Integer, ByVal outputIDs As Integer(), ByVal buffers As PipelineBuffer())

            If buffers.Length <> 0 Then
                outputBuffer = buffers(0)
            End If

        End Sub

        Public Overrides Sub ProcessInput(ByVal inputID As Integer, ByVal buffer As PipelineBuffer)

                ' Advance the buffer to the next row.
                While (buffer.NextRow())

                    ' Add a row to the output buffer.
                    outputBuffer.AddRow()
                    For x As Integer = 0 To inputColumnBufferIndexes.Length

                        ' Copy the data from the input buffer column to the output buffer column.
                        outputBuffer(outputColumnBufferIndexes(x)) = buffer(inputColumnBufferIndexes(x))

                    Next
                End While

            If buffer.EndOfRowset = True Then
                ' EndOfRowset on the input buffer is true.
                ' Set the end of row set on the output buffer.
                outputBuffer.SetEndOfRowset()
            End If
        End Sub
    End Class
End Namespace
```

<span data-ttu-id="4c13f-171">![Icône de Integration Services (petite)](../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="4c13f-171">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="4c13f-172">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="4c13f-172">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="4c13f-173">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="4c13f-173">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="4c13f-174">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="4c13f-174">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="4c13f-175">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4c13f-175">See Also</span></span>
 <span data-ttu-id="4c13f-176">[Développement d’un composant de transformation personnalisé avec des sorties synchrones](../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-synchronous-outputs.md) [compréhension des transformations synchrones et asynchrones](../understanding-synchronous-and-asynchronous-transformations.md) [création d’une transformation asynchrone à l’aide du composant script](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md)</span><span class="sxs-lookup"><span data-stu-id="4c13f-176">[Developing a Custom Transformation Component with Synchronous Outputs](../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-synchronous-outputs.md) [Understanding Synchronous and Asynchronous Transformations](../understanding-synchronous-and-asynchronous-transformations.md) [Creating an Asynchronous Transformation with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md)</span></span>


