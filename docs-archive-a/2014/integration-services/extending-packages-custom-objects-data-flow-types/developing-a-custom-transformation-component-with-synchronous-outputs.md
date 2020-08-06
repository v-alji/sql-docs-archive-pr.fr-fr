---
title: Développement d’un composant de transformation personnalisé avec des sorties synchrones | Microsoft Docs
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
- ProcessInput method
- buffer allocations [Integration Services]
- synchronous outputs [Integration Services]
- transformation components [Integration Services]
- output columns [Integration Services]
- data flow components [Integration Services], transformation components
ms.assetid: b694d21f-9919-402d-9192-666c6449b0b7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 94d78872570103d3df7e1cb96aecb144fafe4257
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705319"
---
# <a name="developing-a-custom-transformation-component-with-synchronous-outputs"></a><span data-ttu-id="b79a5-102">Développement d'un composant de transformation personnalisé à sorties synchrones</span><span class="sxs-lookup"><span data-stu-id="b79a5-102">Developing a Custom Transformation Component with Synchronous Outputs</span></span>
  <span data-ttu-id="b79a5-103">Les composants de transformation à sorties synchrones reçoivent des lignes en provenance des composants en amont, puis lisent ou modifient les valeurs comprises dans les colonnes de ces lignes alors qu'ils transfèrent les lignes aux composants en aval.</span><span class="sxs-lookup"><span data-stu-id="b79a5-103">Transformation components with synchronous outputs receive rows from upstream components, and read or modify the values in the columns of these rows as they pass the rows to downstream components.</span></span> <span data-ttu-id="b79a5-104">Ils peuvent également définir des colonnes de sortie supplémentaires dérivées des colonnes fournies par les composants en amont, mais ils n'ajoutent pas de lignes au flux de données.</span><span class="sxs-lookup"><span data-stu-id="b79a5-104">They may also define additional output columns that are derived from the columns provided by upstream components, but they do not add rows to the data flow.</span></span> <span data-ttu-id="b79a5-105">Pour plus d’informations sur la différence entre les composants synchrones et asynchrones, consultez [Présentation des transformations synchrones et asynchrones](../understanding-synchronous-and-asynchronous-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="b79a5-105">For more information about the difference between synchronous and asynchronous components, see [Understanding Synchronous and Asynchronous Transformations](../understanding-synchronous-and-asynchronous-transformations.md).</span></span>  
  
 <span data-ttu-id="b79a5-106">Ce type de composant convient aux tâches dans lesquelles les données sont modifiées en ligne à mesure qu'elles sont fournies au composant et dans lesquelles le composant n'a pas à consulter toutes les lignes avant de les traiter.</span><span class="sxs-lookup"><span data-stu-id="b79a5-106">This kind of component is suited for tasks where the data is modified inline as it is provided to the component and where the component does not have to see all the rows before processing them.</span></span> <span data-ttu-id="b79a5-107">Il s'agit du composant le plus facile à développer parce que les transformations à sorties synchrones ne se connectent pas en général à des sources de données externes, gèrent des colonnes de métadonnées externes ou ajoutent des lignes aux tampons de sortie.</span><span class="sxs-lookup"><span data-stu-id="b79a5-107">It is the easiest component to develop because transformations with synchronous outputs typically do not connect to external data sources, manage external metadata columns, or add rows to output buffers.</span></span>  
  
 <span data-ttu-id="b79a5-108">La création d'un composant de transformation à sorties synchrones implique d'ajouter un objet <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100> qui contiendra des colonnes en amont sélectionnées pour le composant, et un objet <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> qui peut contenir des colonnes dérivées créées par le composant.</span><span class="sxs-lookup"><span data-stu-id="b79a5-108">Creating a transformation component with synchronous outputs involves adding an <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100> that will contain the upstream columns selected for the component, and a <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> object that may contain derived columns created by the component.</span></span> <span data-ttu-id="b79a5-109">Il inclut également l'implémentation des méthodes de conception, ainsi que la fourniture du code qui lit ou modifie les colonnes dans les lignes du tampon entrantes pendant l'exécution.</span><span class="sxs-lookup"><span data-stu-id="b79a5-109">It also includes implementing the design-time methods, and providing code that reads or modifies the columns in the incoming buffer rows during execution.</span></span>  
  
 <span data-ttu-id="b79a5-110">Cette section fournit les informations requises pour implémenter un composant de transformation personnalisé et des exemples de code pour vous aider à mieux comprendre les concepts.</span><span class="sxs-lookup"><span data-stu-id="b79a5-110">This section provides the information that is required to implement a custom transformation component, and provides code examples to help you better understand the concepts.</span></span>  
  
## <a name="design-time"></a><span data-ttu-id="b79a5-111">Moment de la conception</span><span class="sxs-lookup"><span data-stu-id="b79a5-111">Design Time</span></span>  
 <span data-ttu-id="b79a5-112">Le code du moment de la conception de ce composant implique la création des entrées et sorties, l'ajout de toutes colonnes de sortie supplémentaires que le composant génère et la validation de la configuration du composant.</span><span class="sxs-lookup"><span data-stu-id="b79a5-112">The design-time code for this component involves creating the inputs and outputs, adding any additional output columns that the component generates, and validating the configuration of the component.</span></span>  
  
### <a name="creating-the-component"></a><span data-ttu-id="b79a5-113">Création du composant</span><span class="sxs-lookup"><span data-stu-id="b79a5-113">Creating the Component</span></span>  
 <span data-ttu-id="b79a5-114">Les entrées, sorties et propriétés personnalisées du composant sont en général créées pendant la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A>.</span><span class="sxs-lookup"><span data-stu-id="b79a5-114">The inputs, outputs, and custom properties of the component are typically created during the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> method.</span></span> <span data-ttu-id="b79a5-115">Il existe deux manières d'ajouter l'entrée et la sortie d'un composant de transformation à sorties synchrones.</span><span class="sxs-lookup"><span data-stu-id="b79a5-115">There are two ways that you can add the input and the output of a transformation component with synchronous outputs.</span></span> <span data-ttu-id="b79a5-116">Vous pouvez utiliser l'implémentation de la classe de base de la méthode, puis modifier l'entrée et la sortie par défaut qu'elle crée, ou vous pouvez ajouter explicitement l'entrée et la sortie vous-même.</span><span class="sxs-lookup"><span data-stu-id="b79a5-116">You can use the base class implementation of the method and then modify the default input and output that it creates, or you can explicitly add the input and output yourself.</span></span>  
  
 <span data-ttu-id="b79a5-117">L'exemple de code suivant présente une implémentation de la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> qui ajoute explicitement les objets d'entrée et de sortie.</span><span class="sxs-lookup"><span data-stu-id="b79a5-117">The following code example shows an implementation of <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> that explicitly adds the input and output objects.</span></span> <span data-ttu-id="b79a5-118">L'appel de la classe de base qui accomplirait la même chose est inclus dans un commentaire.</span><span class="sxs-lookup"><span data-stu-id="b79a5-118">The call to the base class that would accomplish the same thing is included in a comment.</span></span>  
  
```csharp  
using Microsoft.SqlServer.Dts.Pipeline;  
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace Microsoft.Samples.SqlServer.Dts  
{  
    [DtsPipelineComponent(DisplayName = "SynchronousComponent", ComponentType = ComponentType.Transform)]  
    public class SyncComponent : PipelineComponent  
    {  
  
        public override void ProvideComponentProperties()  
        {  
            // Add the input.  
            IDTSInput100 input = ComponentMetaData.InputCollection.New();  
            input.Name = "Input";  
  
            // Add the output.  
            IDTSOutput100 output = ComponentMetaData.OutputCollection.New();  
            output.Name = "Output";  
            output.SynchronousInputID = input.ID;  
  
            // Alternatively, you can let the base class add the input and output  
            // and set the SynchronousInputID of the output to the ID of the input.  
            // base.ProvideComponentProperties();  
        }  
    }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Pipeline  
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper  
Imports Microsoft.SqlServer.Dts.Runtime  
  
<DtsPipelineComponent(DisplayName:="SynchronousComponent", ComponentType:=ComponentType.Transform)> _  
Public Class SyncComponent  
    Inherits PipelineComponent  
  
    Public Overrides Sub ProvideComponentProperties()  
  
        ' Add the input.  
        Dim input As IDTSInput100 = ComponentMetaData.InputCollection.New()  
        input.Name = "Input"  
  
        ' Add the output.  
        Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection.New()  
        output.Name = "Output"  
        output.SynchronousInputID = Input.ID  
  
        ' Alternatively, you can let the base class add the input and output  
        ' and set the SynchronousInputID of the output to the ID of the input.  
        ' base.ProvideComponentProperties();  
  
    End Sub  
  
End Class  
```  
  
### <a name="creating-and-configuring-output-columns"></a><span data-ttu-id="b79a5-119">Création et configuration de colonnes de sortie</span><span class="sxs-lookup"><span data-stu-id="b79a5-119">Creating and Configuring Output Columns</span></span>  
 <span data-ttu-id="b79a5-120">Bien que les composants de transformation à sorties synchrones n'ajoutent pas de lignes aux tampons, ils peuvent ajouter des colonnes de sortie supplémentaires à leur sortie.</span><span class="sxs-lookup"><span data-stu-id="b79a5-120">Although transformation components with synchronous outputs do not add rows to buffers, they may add extra output columns to their output.</span></span> <span data-ttu-id="b79a5-121">En général, lorsqu'un composant ajoute une colonne de sortie, les valeurs de la nouvelle colonne de sortie sont dérivées au moment de l'exécution des données contenues dans une ou plusieurs colonnes parmi celles fournies au composant par un composant en amont.</span><span class="sxs-lookup"><span data-stu-id="b79a5-121">Typically, when a component adds an output column, the values for the new output column are derived at run time from the data that is contained in one or more of the columns provided to the component by an upstream component.</span></span>  
  
 <span data-ttu-id="b79a5-122">Après avoir créé une colonne de sortie, ses propriétés de type de données doivent être définies.</span><span class="sxs-lookup"><span data-stu-id="b79a5-122">After an output column has been created, its data type properties must be set.</span></span> <span data-ttu-id="b79a5-123">La définition des propriétés de type de données d'une colonne de sortie requiert une gestion spéciale et s'effectue en appelant la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.SetDataTypeProperties%2A>.</span><span class="sxs-lookup"><span data-stu-id="b79a5-123">Setting the data type properties of an output column requires special handling and is performed by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.SetDataTypeProperties%2A> method.</span></span> <span data-ttu-id="b79a5-124">Cette méthode est requise parce que les propriétés <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.Length%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.Precision%2A> et <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.CodePage%2A> sont individuellement en lecture seule, parce que chacune dépend des paramètres de l'autre.</span><span class="sxs-lookup"><span data-stu-id="b79a5-124">This method is required because the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.Length%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.Precision%2A>, and <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.CodePage%2A> properties are individually read-only, because each depends on the settings of the other.</span></span> <span data-ttu-id="b79a5-125">Cette méthode garantit que les valeurs des propriétés sont définies de manière cohérente et que la tâche de flux de données valide leur définition correcte.</span><span class="sxs-lookup"><span data-stu-id="b79a5-125">This method guarantees that the values of the properties are set consistently, and the data flow task validates that they are set correctly.</span></span>  
  
 <span data-ttu-id="b79a5-126">La propriété <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A> de la colonne détermine les valeurs définies pour les autres propriétés.</span><span class="sxs-lookup"><span data-stu-id="b79a5-126">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A> of the column determines the values that are set for the other properties.</span></span> <span data-ttu-id="b79a5-127">Le tableau suivant indique les conditions requises sur les propriétés dépendantes de chaque propriété <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A>.</span><span class="sxs-lookup"><span data-stu-id="b79a5-127">The following table shows the requirements on the dependent properties for each <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.DataType%2A>.</span></span> <span data-ttu-id="b79a5-128">Les types de données non répertoriés ont leurs propriétés dépendantes définies sur zéro.</span><span class="sxs-lookup"><span data-stu-id="b79a5-128">The data types not listed have their dependent properties set to zero.</span></span>  
  
|<span data-ttu-id="b79a5-129">DataType</span><span class="sxs-lookup"><span data-stu-id="b79a5-129">DataType</span></span>|<span data-ttu-id="b79a5-130">Longueur</span><span class="sxs-lookup"><span data-stu-id="b79a5-130">Length</span></span>|<span data-ttu-id="b79a5-131">Scale</span><span class="sxs-lookup"><span data-stu-id="b79a5-131">Scale</span></span>|<span data-ttu-id="b79a5-132">Precision</span><span class="sxs-lookup"><span data-stu-id="b79a5-132">Precision</span></span>|<span data-ttu-id="b79a5-133">CodePage</span><span class="sxs-lookup"><span data-stu-id="b79a5-133">CodePage</span></span>|  
|--------------|------------|-----------|---------------|--------------|  
|<span data-ttu-id="b79a5-134">DT_DECIMAL</span><span class="sxs-lookup"><span data-stu-id="b79a5-134">DT_DECIMAL</span></span>|<span data-ttu-id="b79a5-135">0</span><span class="sxs-lookup"><span data-stu-id="b79a5-135">0</span></span>|<span data-ttu-id="b79a5-136">Supérieur à 0 et inférieur ou égal à 28.</span><span class="sxs-lookup"><span data-stu-id="b79a5-136">Greater than 0 and less than or equal to 28.</span></span>|<span data-ttu-id="b79a5-137">0</span><span class="sxs-lookup"><span data-stu-id="b79a5-137">0</span></span>|<span data-ttu-id="b79a5-138">0</span><span class="sxs-lookup"><span data-stu-id="b79a5-138">0</span></span>|  
|<span data-ttu-id="b79a5-139">DT_CY</span><span class="sxs-lookup"><span data-stu-id="b79a5-139">DT_CY</span></span>|<span data-ttu-id="b79a5-140">0</span><span class="sxs-lookup"><span data-stu-id="b79a5-140">0</span></span>|<span data-ttu-id="b79a5-141">0</span><span class="sxs-lookup"><span data-stu-id="b79a5-141">0</span></span>|<span data-ttu-id="b79a5-142">0</span><span class="sxs-lookup"><span data-stu-id="b79a5-142">0</span></span>|<span data-ttu-id="b79a5-143">0</span><span class="sxs-lookup"><span data-stu-id="b79a5-143">0</span></span>|  
|<span data-ttu-id="b79a5-144">DT_NUMERIC</span><span class="sxs-lookup"><span data-stu-id="b79a5-144">DT_NUMERIC</span></span>|<span data-ttu-id="b79a5-145">0</span><span class="sxs-lookup"><span data-stu-id="b79a5-145">0</span></span>|<span data-ttu-id="b79a5-146">Supérieur à 0 et inférieur ou égale à 28 et inférieur à Précision.</span><span class="sxs-lookup"><span data-stu-id="b79a5-146">Greater than 0 and less than or equal to 28, and less than Precision.</span></span>|<span data-ttu-id="b79a5-147">Supérieur ou égal à 1 et inférieur ou égal à 38.</span><span class="sxs-lookup"><span data-stu-id="b79a5-147">Greater than or equal to 1 and less than or equal to 38.</span></span>|<span data-ttu-id="b79a5-148">0</span><span class="sxs-lookup"><span data-stu-id="b79a5-148">0</span></span>|  
|<span data-ttu-id="b79a5-149">DT_BYTES</span><span class="sxs-lookup"><span data-stu-id="b79a5-149">DT_BYTES</span></span>|<span data-ttu-id="b79a5-150">Supérieur à 0.</span><span class="sxs-lookup"><span data-stu-id="b79a5-150">Greater than 0.</span></span>|<span data-ttu-id="b79a5-151">0</span><span class="sxs-lookup"><span data-stu-id="b79a5-151">0</span></span>|<span data-ttu-id="b79a5-152">0</span><span class="sxs-lookup"><span data-stu-id="b79a5-152">0</span></span>|<span data-ttu-id="b79a5-153">0</span><span class="sxs-lookup"><span data-stu-id="b79a5-153">0</span></span>|  
|<span data-ttu-id="b79a5-154">DT_STR</span><span class="sxs-lookup"><span data-stu-id="b79a5-154">DT_STR</span></span>|<span data-ttu-id="b79a5-155">Supérieur à 0 et inférieur à 8 000.</span><span class="sxs-lookup"><span data-stu-id="b79a5-155">Greater than 0 and less than 8000.</span></span>|<span data-ttu-id="b79a5-156">0</span><span class="sxs-lookup"><span data-stu-id="b79a5-156">0</span></span>|<span data-ttu-id="b79a5-157">0</span><span class="sxs-lookup"><span data-stu-id="b79a5-157">0</span></span>|<span data-ttu-id="b79a5-158">Différent de 0 et une page de codes valide.</span><span class="sxs-lookup"><span data-stu-id="b79a5-158">Not 0, and a valid code page.</span></span>|  
|<span data-ttu-id="b79a5-159">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="b79a5-159">DT_WSTR</span></span>|<span data-ttu-id="b79a5-160">Supérieur à 0 et inférieur à 4000.</span><span class="sxs-lookup"><span data-stu-id="b79a5-160">Greater than 0 and less than 4000.</span></span>|<span data-ttu-id="b79a5-161">0</span><span class="sxs-lookup"><span data-stu-id="b79a5-161">0</span></span>|<span data-ttu-id="b79a5-162">0</span><span class="sxs-lookup"><span data-stu-id="b79a5-162">0</span></span>|<span data-ttu-id="b79a5-163">0</span><span class="sxs-lookup"><span data-stu-id="b79a5-163">0</span></span>|  
  
 <span data-ttu-id="b79a5-164">Étant donné que les restrictions sur les propriétés de type de données sont basées sur le type de données de la colonne de sortie, vous devez choisir le type de données [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] correct lorsque vous utilisez des types managés.</span><span class="sxs-lookup"><span data-stu-id="b79a5-164">Because the restrictions on the data type properties are based on the data type of the output column, you must choose the correct [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] data type when you work with managed types.</span></span> <span data-ttu-id="b79a5-165">La classe de base fournit trois méthodes d'assistance, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ConvertBufferDataTypeToFitManaged%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferTypeToDataRecordType%2A> et <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.DataRecordTypeToBufferType%2A> qui aident les développeurs de composants managés à sélectionner un type de données [!INCLUDE[ssIS](../../includes/ssis-md.md)] en fonction d'un type managé.</span><span class="sxs-lookup"><span data-stu-id="b79a5-165">The base class provides three helper methods, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ConvertBufferDataTypeToFitManaged%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferTypeToDataRecordType%2A>, and <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.DataRecordTypeToBufferType%2A> that assist managed component developers in selecting an [!INCLUDE[ssIS](../../includes/ssis-md.md)] data type given a managed type.</span></span> <span data-ttu-id="b79a5-166">Ces méthodes convertissent des types de données managées en types de données [!INCLUDE[ssIS](../../includes/ssis-md.md)], et vice versa.</span><span class="sxs-lookup"><span data-stu-id="b79a5-166">These methods convert managed data types to [!INCLUDE[ssIS](../../includes/ssis-md.md)] data types, and vice versa.</span></span>  
  
## <a name="run-time"></a><span data-ttu-id="b79a5-167">Moment de l'exécution</span><span class="sxs-lookup"><span data-stu-id="b79a5-167">Run Time</span></span>  
 <span data-ttu-id="b79a5-168">En général, l’implémentation de la partie exécution du composant se divise en deux tâches : localisation des colonnes d’entrée et de sortie du composant dans le tampon et lecture ou écriture des valeurs de ces colonnes dans les lignes du tampon entrantes.</span><span class="sxs-lookup"><span data-stu-id="b79a5-168">Generally, the implementation of the run-time part of the component is categorized into two tasks-locating the input and output columns of the component in the buffer, and reading or writing the values of these columns in the incoming buffer rows.</span></span>  
  
### <a name="locating-columns-in-the-buffer"></a><span data-ttu-id="b79a5-169">Localisation des colonnes dans le tampon</span><span class="sxs-lookup"><span data-stu-id="b79a5-169">Locating Columns in the Buffer</span></span>  
 <span data-ttu-id="b79a5-170">Le nombre de colonnes dans les tampons fournis à un composant pendant l'exécution dépassera probablement le nombre de colonnes dans les collections d'entrée ou de sortie du composant.</span><span class="sxs-lookup"><span data-stu-id="b79a5-170">The number of columns in the buffers that are provided to a component during execution will likely exceed the number of columns in the input or output collections of the component.</span></span> <span data-ttu-id="b79a5-171">Ce dépassement est dû au fait que chaque tampon contient toutes les colonnes de sortie définies dans les composants d'un flux de données.</span><span class="sxs-lookup"><span data-stu-id="b79a5-171">This is because each buffer contains all the output columns defined in the components in a data flow.</span></span> <span data-ttu-id="b79a5-172">Pour garantir que les colonnes de tampon sont correctement mises en correspondance avec les colonnes d'entrée ou de sortie, les développeurs de composants doivent utiliser la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A> de la propriété <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A>.</span><span class="sxs-lookup"><span data-stu-id="b79a5-172">To ensure that the buffer columns are correctly matched to the columns of the input or output, component developers must use the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A>.</span></span> <span data-ttu-id="b79a5-173">Cette méthode localise une colonne dans le tampon spécifié par son ID de lignage.</span><span class="sxs-lookup"><span data-stu-id="b79a5-173">This method locates a column in the specified buffer by its lineage ID.</span></span> <span data-ttu-id="b79a5-174">En général, les colonnes sont localisées pendant la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> parce qu'il s'agit de la première méthode d'exécution où la propriété <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A> devient disponible.</span><span class="sxs-lookup"><span data-stu-id="b79a5-174">Typically columns are located during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> because this is the first run-time method where the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A> property becomes available.</span></span>  
  
 <span data-ttu-id="b79a5-175">L'exemple de code suivant présente un composant qui localise des index des colonnes dans sa collection de colonnes d'entrée et de sortie pendant la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A>.</span><span class="sxs-lookup"><span data-stu-id="b79a5-175">The following code example shows a component that locates indexes of the columns in its input and output column collection during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A>.</span></span> <span data-ttu-id="b79a5-176">Les index de colonne sont stockés dans un tableau d'entiers et sont accessibles via le composant pendant la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="b79a5-176">The column indexes are stored in an integer array, and can be accessed by the component during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span></span>  
  
```csharp  
int []inputColumns;  
int []outputColumns;  
  
public override void PreExecute()  
{  
    IDTSInput100 input = ComponentMetaData.InputCollection[0];  
    IDTSOutput100 output = ComponentMetaData.OutputCollection[0];  
  
    inputColumns = new int[input.InputColumnCollection.Count];  
    outputColumns = new int[output.OutputColumnCollection.Count];  
  
    for(int col=0; col < input.InputColumnCollection.Count; col++)  
    {  
        IDTSInputColumn100 inputColumn = input.InputColumnCollection[col];  
        inputColumns[col] = BufferManager.FindColumnByLineageID(input.Buffer, inputColumn.LineageID);  
    }  
  
    for(int col=0; col < output.OutputColumnCollection.Count; col++)  
    {  
        IDTSOutputColumn100 outputColumn = output.OutputColumnCollection[col];  
        outputColumns[col] = BufferManager.FindColumnByLineageID(input.Buffer, outputColumn.LineageID);  
    }  
  
}  
```  
  
```vb  
Public Overrides Sub PreExecute()  
  
    Dim input As IDTSInput100 = ComponentMetaData.InputCollection(0)  
    Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection(0)  
  
    ReDim inputColumns(input.InputColumnCollection.Count)  
    ReDim outputColumns(output.OutputColumnCollection.Count)  
  
    For col As Integer = 0 To input.InputColumnCollection.Count  
  
        Dim inputColumn As IDTSInputColumn100 = input.InputColumnCollection(col)  
        inputColumns(col) = BufferManager.FindColumnByLineageID(input.Buffer, inputColumn.LineageID)  
    Next  
  
    For col As Integer = 0 To output.OutputColumnCollection.Count  
  
        Dim outputColumn As IDTSOutputColumn100 = output.OutputColumnCollection(col)  
        outputColumns(col) = BufferManager.FindColumnByLineageID(input.Buffer, outputColumn.LineageID)  
    Next  
  
End Sub  
```  
  
### <a name="processing-rows"></a><span data-ttu-id="b79a5-177">Traitement de lignes</span><span class="sxs-lookup"><span data-stu-id="b79a5-177">Processing Rows</span></span>  
 <span data-ttu-id="b79a5-178">Les composants reçoivent des objets <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> qui contiennent des lignes et des colonnes dans la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="b79a5-178">Components receive <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> objects that contain rows and columns in the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method.</span></span> <span data-ttu-id="b79a5-179">Pendant cette méthode, les lignes comprises dans le tampon sont parcourues, puis les colonnes identifiées pendant la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> sont lues et modifiées.</span><span class="sxs-lookup"><span data-stu-id="b79a5-179">During this method the rows in the buffer are iterated, and the columns identified during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> are read and modified.</span></span> <span data-ttu-id="b79a5-180">La méthode est appelée à plusieurs reprises par la tâche de flux de données jusqu'à ce qu'aucune ligne ne soit fournie à partir du composant en amont.</span><span class="sxs-lookup"><span data-stu-id="b79a5-180">The method is called repeatedly by the data flow task until no more rows are provided from the upstream component.</span></span>  
  
 <span data-ttu-id="b79a5-181">Une colonne individuelle dans le tampon est lue ou écrite en utilisant la méthode d'accès de l'indexeur du tableau ou en utilisant l'une des méthodes `Get` ou `Set`.</span><span class="sxs-lookup"><span data-stu-id="b79a5-181">An individual column in the buffer is read or written by using the array indexer access method, or by using one of the `Get` or `Set` methods.</span></span> <span data-ttu-id="b79a5-182">Les méthodes `Get` et `Set` sont plus efficaces et doivent être utilisées lorsque le type de données de la colonne dans le tampon est connu.</span><span class="sxs-lookup"><span data-stu-id="b79a5-182">The `Get` and `Set` methods are more efficient and should be used when the data type of the column in the buffer is known.</span></span>  
  
 <span data-ttu-id="b79a5-183">L'exemple de code suivant présente une implémentation de la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> qui traite des lignes entrantes.</span><span class="sxs-lookup"><span data-stu-id="b79a5-183">The following code example shows an implementation of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method that processes incoming rows.</span></span>  
  
```csharp  
public override void ProcessInput( int InputID, PipelineBuffer buffer)  
{  
       while( buffer.NextRow())  
       {  
            for(int x=0; x < inputColumns.Length;x++)  
            {  
                if(!buffer.IsNull(inputColumns[x]))  
                {  
                    object columnData = buffer[inputColumns[x]];  
                    // TODO: Modify the column data.  
                    buffer[inputColumns[x]] = columnData;  
                }  
            }  
  
      }  
}  
```  
  
```vb  
Public Overrides Sub ProcessInput(ByVal InputID As Integer, ByVal buffer As PipelineBuffer)  
  
        While (buffer.NextRow())  
  
            For x As Integer = 0 To inputColumns.Length  
  
                if buffer.IsNull(inputColumns(x)) = false then  
  
                    Dim columnData As Object = buffer(inputColumns(x))  
                    ' TODO: Modify the column data.  
                    buffer(inputColumns(x)) = columnData  
  
                End If  
            Next  
  
        End While  
End Sub  
```  
  
## <a name="sample"></a><span data-ttu-id="b79a5-184">Exemple</span><span class="sxs-lookup"><span data-stu-id="b79a5-184">Sample</span></span>  
 <span data-ttu-id="b79a5-185">L'exemple suivant présente un composant de transformation simple à sorties synchrones qui convertit les valeurs de toutes les colonnes de chaîne en majuscule.</span><span class="sxs-lookup"><span data-stu-id="b79a5-185">The following sample shows a simple transformation component with synchronous outputs that converts the values of all string columns to uppercase.</span></span> <span data-ttu-id="b79a5-186">Cet exemple ne contient pas toutes les méthodes et fonctionnalités présentées dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="b79a5-186">This sample does not demonstrate all the methods and functionality discussed in this topic.</span></span> <span data-ttu-id="b79a5-187">Il illustre les méthodes importantes que chaque composant de transformation personnalisé à sorties synchrones doit substituer, mais ne contient pas de code pour la validation au moment de la conception.</span><span class="sxs-lookup"><span data-stu-id="b79a5-187">It demonstrates the important methods that every custom transformation component with synchronous outputs must override, but does not contain code for design-time validation.</span></span>  
  
```csharp  
using System;  
using System.Collections;  
using Microsoft.SqlServer.Dts.Pipeline;  
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;  
using Microsoft.SqlServer.Dts.Runtime.Wrapper;  
  
namespace Uppercase  
{  
  [DtsPipelineComponent(DisplayName = "Uppercase")]  
  public class Uppercase : PipelineComponent  
  {  
    ArrayList m_ColumnIndexList = new ArrayList();  
  
    public override void ProvideComponentProperties()  
    {  
      base.ProvideComponentProperties();  
      ComponentMetaData.InputCollection[0].Name = "Uppercase Input";  
      ComponentMetaData.OutputCollection[0].Name = "Uppercase Output";  
    }  
  
    public override void PreExecute()  
    {  
      IDTSInput100 input = ComponentMetaData.InputCollection[0];  
      IDTSInputColumnCollection100 inputColumns = input.InputColumnCollection;  
  
      foreach (IDTSInputColumn100 column in inputColumns)  
      {  
        if (column.DataType == DataType.DT_STR || column.DataType == DataType.DT_WSTR)  
        {  
          m_ColumnIndexList.Add((int)BufferManager.FindColumnByLineageID(input.Buffer, column.LineageID));  
        }  
      }  
    }  
  
    public override void ProcessInput(int inputID, PipelineBuffer buffer)  
    {  
      while (buffer.NextRow())  
      {  
        foreach (int columnIndex in m_ColumnIndexList)  
        {  
          string str = buffer.GetString(columnIndex);  
          buffer.SetString(columnIndex, str.ToUpper());  
        }  
      }  
    }  
  }  
}  
```  
  
```vb  
Imports System   
Imports System.Collections   
Imports Microsoft.SqlServer.Dts.Pipeline   
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper   
Imports Microsoft.SqlServer.Dts.Runtime.Wrapper   
Namespace Uppercase   
  
 <DtsPipelineComponent(DisplayName="Uppercase")> _   
 Public Class Uppercase   
 Inherits PipelineComponent   
   Private m_ColumnIndexList As ArrayList = New ArrayList   
  
   Public  Overrides Sub ProvideComponentProperties()   
     MyBase.ProvideComponentProperties   
     ComponentMetaData.InputCollection(0).Name = "Uppercase Input"   
     ComponentMetaData.OutputCollection(0).Name = "Uppercase Output"   
   End Sub   
  
   Public  Overrides Sub PreExecute()   
     Dim input As IDTSInput100 = ComponentMetaData.InputCollection(0)   
     Dim inputColumns As IDTSInputColumnCollection100 = input.InputColumnCollection   
     For Each column As IDTSInputColumn100 In inputColumns   
       If column.DataType = DataType.DT_STR OrElse column.DataType = DataType.DT_WSTR Then   
         m_ColumnIndexList.Add(CType(BufferManager.FindColumnByLineageID(input.Buffer, column.LineageID), Integer))   
       End If   
     Next   
   End Sub   
  
   Public  Overrides Sub ProcessInput(ByVal inputID As Integer, ByVal buffer As PipelineBuffer)   
     While buffer.NextRow   
       For Each columnIndex As Integer In m_ColumnIndexList   
         Dim str As String = buffer.GetString(columnIndex)   
         buffer.SetString(columnIndex, str.ToUpper)   
       Next   
     End While   
   End Sub   
 End Class   
End Namespace  
```  
  
<span data-ttu-id="b79a5-188">![Icône de Integration Services (petite)](../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="b79a5-188">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="b79a5-189">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="b79a5-189">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="b79a5-190">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="b79a5-190">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="b79a5-191">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="b79a5-191">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b79a5-192">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b79a5-192">See Also</span></span>  
 <span data-ttu-id="b79a5-193">[Développement d’un composant de transformation personnalisé avec des sorties asynchrones](../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-asynchronous-outputs.md) </span><span class="sxs-lookup"><span data-stu-id="b79a5-193">[Developing a Custom Transformation Component with Asynchronous Outputs](../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-asynchronous-outputs.md) </span></span>  
 <span data-ttu-id="b79a5-194">[Compréhension des transformations synchrones et asynchrones](../understanding-synchronous-and-asynchronous-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="b79a5-194">[Understanding Synchronous and Asynchronous Transformations](../understanding-synchronous-and-asynchronous-transformations.md) </span></span>  
 [<span data-ttu-id="b79a5-195">Création d'une transformation synchrone à l'aide du composant Script</span><span class="sxs-lookup"><span data-stu-id="b79a5-195">Creating a Synchronous Transformation with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md) 
  
  
