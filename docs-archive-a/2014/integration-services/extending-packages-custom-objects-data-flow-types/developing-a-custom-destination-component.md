---
title: Développement d’un composant de destination personnalisé | Microsoft Docs
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
- validation [Integration Services], components
- destinations [Integration Services], components
- ProcessInput method
- external data sources [Integration Services]
- custom data flow components [Integration Services], destination components
- data flow components [Integration Services], destination components
ms.assetid: 24619363-9535-4c0e-8b62-1d22c6630e40
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6979d14afa0490638162c35bb660f15506803484
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694656"
---
# <a name="developing-a-custom-destination-component"></a><span data-ttu-id="d8ef6-102">Développement d'un composant de destination personnalisé</span><span class="sxs-lookup"><span data-stu-id="d8ef6-102">Developing a Custom Destination Component</span></span>
  [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="d8ef6-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] offre aux développeurs la capacité d’écrire des composants de destination personnalisés qui peuvent se connecter à n’importe quelle source de données personnalisée et y stocker des données.</span><span class="sxs-lookup"><span data-stu-id="d8ef6-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] gives developers the ability to write custom destination components that can connect to and store data in any custom data source.</span></span> <span data-ttu-id="d8ef6-104">Les composants de destination personnalisés sont utiles lorsque vous devez vous connecter à des sources de données qui ne sont pas accessibles via l'un des composants sources existants inclus dans [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d8ef6-104">Custom destination components are useful when you need to connect to data sources that cannot be accessed by using one of the existing source components included with [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span>

 <span data-ttu-id="d8ef6-105">Les composants de destination possèdent une ou plusieurs entrées et zéro sortie.</span><span class="sxs-lookup"><span data-stu-id="d8ef6-105">Destination components have one or more inputs and zero outputs.</span></span> <span data-ttu-id="d8ef6-106">Au moment de la conception, ils créent et configurent des connexions et lisent les métadonnées des colonnes à partir de la source de données externe.</span><span class="sxs-lookup"><span data-stu-id="d8ef6-106">At design time, they create and configure connections and read column metadata from the external data source.</span></span> <span data-ttu-id="d8ef6-107">Pendant l'exécution, ils se connectent à leur source de données externe et y ajoutent des lignes provenant de composants situés en amont du flux de données.</span><span class="sxs-lookup"><span data-stu-id="d8ef6-107">During execution, they connect to their external data source and add rows that are received from the components upstream in the data flow to the external data source.</span></span> <span data-ttu-id="d8ef6-108">Si la source de données externe existe avant l'exécution du composant, le composant de destination doit également s'assurer que les types de données des colonnes que le composant reçoit correspondent aux types de données des colonnes au niveau de la source de données externe.</span><span class="sxs-lookup"><span data-stu-id="d8ef6-108">If the external data source exists prior to execution of the component, the destination component must also ensure that the data types of the columns that the component receives match the data types of the columns at the external data source.</span></span>

 <span data-ttu-id="d8ef6-109">Cette section explique en détail comment développer des composants de destination et fournit des exemples de code pour clarifier des concepts importants.</span><span class="sxs-lookup"><span data-stu-id="d8ef6-109">This section discusses the details of how to develop destination components, and provides code examples to clarify important concepts.</span></span> <span data-ttu-id="d8ef6-110">Pour une vue d’ensemble du développement de composants de flux de données, consultez [Développement d’un composant de flux de données personnalisé](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="d8ef6-110">For a general overview of data flow component development, see [Developing a Custom Data Flow Component](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span></span>

## <a name="design-time"></a><span data-ttu-id="d8ef6-111">Moment de la conception</span><span class="sxs-lookup"><span data-stu-id="d8ef6-111">Design Time</span></span>
 <span data-ttu-id="d8ef6-112">Pour implémenter les fonctionnalités au moment de la conception d'un composant de destination, vous devez spécifier une connexion à une source de données externe et confirmer que le composant a été correctement configuré.</span><span class="sxs-lookup"><span data-stu-id="d8ef6-112">Implementing the design-time functionality of a destination component involves specifying a connection to an external data source and validating that the component has been correctly configured.</span></span> <span data-ttu-id="d8ef6-113">Par définition, un composant de destination possède une entrée et éventuellement une sortie d'erreur.</span><span class="sxs-lookup"><span data-stu-id="d8ef6-113">By definition, a destination component has one input and possibly one error output.</span></span>

### <a name="creating-the-component"></a><span data-ttu-id="d8ef6-114">Création du composant</span><span class="sxs-lookup"><span data-stu-id="d8ef6-114">Creating the Component</span></span>
 <span data-ttu-id="d8ef6-115">Les composants de destination se connectent à des sources de données externes à l'aide d'objets <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> définis dans un package.</span><span class="sxs-lookup"><span data-stu-id="d8ef6-115">Destination components connect to external data sources by using <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> objects defined in a package.</span></span> <span data-ttu-id="d8ef6-116">Le composant de destination indique qu’il a besoin d’un gestionnaire de connexions au concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] et aux utilisateurs du composant, en ajoutant un élément à la collection <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A> de <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A>.</span><span class="sxs-lookup"><span data-stu-id="d8ef6-116">The destination component indicates its requirement for a connection manager to the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, and to users of the component, by adding an element to the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A> collection of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A>.</span></span> <span data-ttu-id="d8ef6-117">Cette collection remplit deux rôles : d'abord, elle publie le besoin d'un gestionnaire de connexions auprès du concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] ; puis, lorsque l'utilisateur a sélectionné ou créé un gestionnaire de connexions, elle contient une référence au gestionnaire de connexions dans le package utilisé par le composant.</span><span class="sxs-lookup"><span data-stu-id="d8ef6-117">This collection serves two purposes: first, it advertises the need for a connection manager to [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer; then, after the user has selected or created a connection manager, it holds a reference to the connection manager in the package that is being used by the component.</span></span> <span data-ttu-id="d8ef6-118">Lorsqu’un objet <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100> est ajouté à la collection, l’**Éditeur avancé** affiche l’onglet **Propriétés de connexion** pour inviter l’utilisateur à sélectionner ou créer une connexion dans le package utilisée par le composant.</span><span class="sxs-lookup"><span data-stu-id="d8ef6-118">When an <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100> is added to the collection, the **Advanced Editor** displays the **Connection Properties** tab, to prompt the user to select or create a connection in the package for use by the component.</span></span>

 <span data-ttu-id="d8ef6-119">L'exemple de code suivant affiche une implémentation de <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> qui ajoute une entrée, puis ajoute un objet <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100> à <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A>.</span><span class="sxs-lookup"><span data-stu-id="d8ef6-119">The following code sample shows an implementation of <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> that adds an input, and then adds a <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100> object to the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A>.</span></span>

```csharp
using System;
using Microsoft.SqlServer.Dts.Pipeline;
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;
using Microsoft.SqlServer.Dts.Runtime;

namespace Microsoft.Samples.SqlServer.Dts
{
    [DtsPipelineComponent(DisplayName = "Destination Component",ComponentType =ComponentType.DestinationAdapter)]
    public class DestinationComponent : PipelineComponent 
    {
        public override void ProvideComponentProperties()
        {
            // Reset the component.
            base.RemoveAllInputsOutputsAndCustomProperties();
            ComponentMetaData.RuntimeConnectionCollection.RemoveAll();

            IDTSInput100 input = ComponentMetaData.InputCollection.New();
            input.Name = "Input";

            IDTSRuntimeConnection100 connection = ComponentMetaData.RuntimeConnectionCollection.New();
            connection.Name = "ADO.net";
        }
    }
}
```

```vb
Imports System
Imports System.Data
Imports System.Data.SqlClient
Imports Microsoft.SqlServer.Dts.Pipeline
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper
Imports Microsoft.SqlServer.Dts.Runtime

Namespace Microsoft.Samples.SqlServer.Dts

    <DtsPipelineComponent(DisplayName:="Destination Component", ComponentType:=ComponentType.DestinationAdapter)> _
    Public Class DestinationComponent
        Inherits PipelineComponent

        Public Overrides Sub ProvideComponentProperties()

            ' Reset the component.
            Me.RemoveAllInputsOutputsAndCustomProperties()
            ComponentMetaData.RuntimeConnectionCollection.RemoveAll()

            Dim input As IDTSInput100 = ComponentMetaData.InputCollection.New()
            input.Name = "Input"

            Dim connection As IDTSRuntimeConnection100 = ComponentMetaData.RuntimeConnectionCollection.New()
            connection.Name = "ADO.net"

        End Sub
    End Class
End Namespace
```

### <a name="connecting-to-an-external-data-source"></a><span data-ttu-id="d8ef6-120">Connexion à une source de données externe</span><span class="sxs-lookup"><span data-stu-id="d8ef6-120">Connecting to an External Data Source</span></span>
 <span data-ttu-id="d8ef6-121">Une fois la connexion ajoutée à la collection <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A>, vous pouvez remplacer la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A> pour établir une connexion à la source de données externe.</span><span class="sxs-lookup"><span data-stu-id="d8ef6-121">After a connection is added to the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A>, you override the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A> method to establish a connection to the external data source.</span></span> <span data-ttu-id="d8ef6-122">Cette méthode est appelée au moment de la conception et au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="d8ef6-122">This method is called at design time and at run time.</span></span> <span data-ttu-id="d8ef6-123">Le composant doit établir une connexion au gestionnaire de connexions spécifié par la connexion au moment de l'exécution, et par la suite, à la source de données externe.</span><span class="sxs-lookup"><span data-stu-id="d8ef6-123">The component must establish a connection to the connection manager specified by the run-time connection, and subsequently, to the external data source.</span></span> <span data-ttu-id="d8ef6-124">Une fois la connexion établie, le composant doit la mettre en cache en interne et la libérer lorsque <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A> est appelé.</span><span class="sxs-lookup"><span data-stu-id="d8ef6-124">Once established, the component should cache the connection internally and release it when <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A> is called.</span></span> <span data-ttu-id="d8ef6-125">Les développeurs substituent cette méthode et libèrent la connexion établie par le composant pendant l'exécution de la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>.</span><span class="sxs-lookup"><span data-stu-id="d8ef6-125">Developers override this method, and release the connection established by the component during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>.</span></span> <span data-ttu-id="d8ef6-126">Les méthodes <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A> et <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A> sont appelées au moment de la conception et au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="d8ef6-126">Both of these methods, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A> and <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>, are called at design time and at run time.</span></span>

 <span data-ttu-id="d8ef6-127">L'exemple de code suivant montre un composant qui établit une connexion ADO.NET dans la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A>, puis ferme la connexion dans <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A>.</span><span class="sxs-lookup"><span data-stu-id="d8ef6-127">The following code example shows a component that connects to an ADO.NET connection in the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.AcquireConnections%2A> method, and then closes the connection in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReleaseConnections%2A>.</span></span>

```csharp
using Microsoft.SqlServer.Dts.Runtime.Wrapper;

private SqlConnection sqlConnection;

public override void AcquireConnections(object transaction)
{
    if (ComponentMetaData.RuntimeConnectionCollection[0].ConnectionManager != null)
    {
        ConnectionManager cm = Microsoft.SqlServer.Dts.Runtime.DtsConvert.GetWrapper(ComponentMetaData.RuntimeConnectionCollection[0].ConnectionManager);
        ConnectionManagerAdoNet cmado = cm.InnerObject as ConnectionManagerAdoNet;

        if (cmado == null)
            throw new Exception("The ConnectionManager " + cm.Name + " is not an ADO.NET connection.");

        sqlConnection = cmado.AcquireConnection(transaction) as SqlConnection;
        sqlConnection.Open();
    }
}

public override void ReleaseConnections()
{
    if (sqlConnection != null && sqlConnection.State != ConnectionState.Closed)
        sqlConnection.Close();
}
```

```vb
Imports Microsoft.SqlServer.Dts.Runtime.Wrapper

Private sqlConnection As SqlConnection

Public Overrides Sub AcquireConnections(ByVal transaction As Object)

    If IsNothing(ComponentMetaData.RuntimeConnectionCollection(0).ConnectionManager) = False Then

        Dim cm As ConnectionManager = DtsConvert.GetWrapper(ComponentMetaData.RuntimeConnectionCollection(0).ConnectionManager)
        Dim cmado As ConnectionManagerAdoNet = CType(cm.InnerObject,ConnectionManagerAdoNet)

        If IsNothing(cmado) Then
            Throw New Exception("The ConnectionManager " + cm.Name + " is not an ADO.NET connection.")
        End If

        sqlConnection = CType(cmado.AcquireConnection(transaction), SqlConnection)
        sqlConnection.Open()

    End If
End Sub

Public Overrides Sub ReleaseConnections()

    If IsNothing(sqlConnection) = False And sqlConnection.State <> ConnectionState.Closed Then
        sqlConnection.Close()
    End If

End Sub
```

### <a name="validating-the-component"></a><span data-ttu-id="d8ef6-128">Validation du composant</span><span class="sxs-lookup"><span data-stu-id="d8ef6-128">Validating the Component</span></span>
 <span data-ttu-id="d8ef6-129">Les développeurs de composants de destination doivent procéder à une opération de validation décrite dans [Validation de composants](../extending-packages-custom-objects/data-flow/validating-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="d8ef6-129">Destination component developers should perform validation as described in [Component Validation](../extending-packages-custom-objects/data-flow/validating-a-data-flow-component.md).</span></span> <span data-ttu-id="d8ef6-130">De plus, ils doivent vérifier que les propriétés de type de données des colonnes définies dans la collection de colonnes d'entrée du composant correspondent aux colonnes au niveau de la source de données externe.</span><span class="sxs-lookup"><span data-stu-id="d8ef6-130">In addition, they should verify that the data type properties of the columns defined in the component's input column collection match the columns at the external data source.</span></span> <span data-ttu-id="d8ef6-131">Il est parfois impossible ou déconseillé de vérifier les colonnes d'entrée par rapport à la source de données externe, notamment lorsque le composant ou le concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] est déconnecté, ou lorsque les allers-retours au serveur ne sont pas acceptables.</span><span class="sxs-lookup"><span data-stu-id="d8ef6-131">At times, verifying the input columns against the external data source can be impossible or undesirable, such as when the component or the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer is in a disconnected state, or when round trips to the server are not acceptable.</span></span> <span data-ttu-id="d8ef6-132">Dans ce cas, il est toujours possible de valider les colonnes dans la collection de colonnes d'entrée à l'aide de la propriété <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100.ExternalMetadataColumnCollection%2A> de l'objet d'entrée.</span><span class="sxs-lookup"><span data-stu-id="d8ef6-132">In these situations, the columns in the input column collection can still be validated by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100.ExternalMetadataColumnCollection%2A> of the input object.</span></span>

 <span data-ttu-id="d8ef6-133">Cette collection existe sur les objets d'entrée et de sortie et doit être remplie par le développeur de composants à partir des colonnes au niveau de la source de données externe.</span><span class="sxs-lookup"><span data-stu-id="d8ef6-133">This collection exists on both input and output objects and must be populated by the component developer from the columns at the external data source.</span></span> <span data-ttu-id="d8ef6-134">Cette collection permet de valider les colonnes d'entrée lorsque le concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] est hors connexion, lorsque le composant est déconnecté ou lorsque la propriété <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ValidateExternalMetadata%2A> a la valeur `false`.</span><span class="sxs-lookup"><span data-stu-id="d8ef6-134">This collection can be used to validate the input columns when the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer is offline, when the component is disconnected, or when the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ValidateExternalMetadata%2A> property is `false`.</span></span>

 <span data-ttu-id="d8ef6-135">L'exemple de code suivant ajoute une colonne de métadonnées externe basée sur une colonne d'entrée existante.</span><span class="sxs-lookup"><span data-stu-id="d8ef6-135">The following sample code adds an external metadata column based on an existing input column.</span></span>

```csharp
private void AddExternalMetaDataColumn(IDTSInput100 input,IDTSInputColumn100 inputColumn)
{
    // Set the properties of the external metadata column.
    IDTSExternalMetadataColumn100 externalColumn = input.ExternalMetadataColumnCollection.New();
    externalColumn.Name = inputColumn.Name;
    externalColumn.Precision = inputColumn.Precision;
    externalColumn.Length = inputColumn.Length;
    externalColumn.DataType = inputColumn.DataType;
    externalColumn.Scale = inputColumn.Scale;

    // Map the external column to the input column.
    inputColumn.ExternalMetadataColumnID = externalColumn.ID;
}
```

```vb
Private Sub AddExternalMetaDataColumn(ByVal input As IDTSInput100, ByVal inputColumn As IDTSInputColumn100)

    ' Set the properties of the external metadata column.
    Dim externalColumn As IDTSExternalMetadataColumn100 = input.ExternalMetadataColumnCollection.New()
    externalColumn.Name = inputColumn.Name
    externalColumn.Precision = inputColumn.Precision
    externalColumn.Length = inputColumn.Length
    externalColumn.DataType = inputColumn.DataType
    externalColumn.Scale = inputColumn.Scale

    ' Map the external column to the input column.
    inputColumn.ExternalMetadataColumnID = externalColumn.ID

End Sub
```

## <a name="run-time"></a><span data-ttu-id="d8ef6-136">Moment de l'exécution</span><span class="sxs-lookup"><span data-stu-id="d8ef6-136">Run Time</span></span>
 <span data-ttu-id="d8ef6-137">Pendant l'exécution, le composant de destination reçoit un appel à la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> chaque fois qu'un <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> saturé est disponible à partir du composant en amont.</span><span class="sxs-lookup"><span data-stu-id="d8ef6-137">During execution, the destination component receives a call to the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> method each time a full <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> is available from the upstream component.</span></span> <span data-ttu-id="d8ef6-138">Cette méthode est appelée à plusieurs reprises jusqu'à ce qu'il n'y ait plus de mémoire tampon disponible et que la propriété <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.EndOfRowset%2A> prenne la valeur `true`.</span><span class="sxs-lookup"><span data-stu-id="d8ef6-138">This method is called repeatedly until there are no more buffers available and the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.EndOfRowset%2A> property is `true`.</span></span> <span data-ttu-id="d8ef6-139">Pendant l'exécution de cette méthode, les composants de destination lisent les colonnes et les lignes dans la mémoire tampon et les ajoutent à la source de données externe.</span><span class="sxs-lookup"><span data-stu-id="d8ef6-139">During this method, destination components read columns and rows in the buffer, and add them to the external data source.</span></span>

### <a name="locating-columns-in-the-buffer"></a><span data-ttu-id="d8ef6-140">Localisation des colonnes dans le tampon</span><span class="sxs-lookup"><span data-stu-id="d8ef6-140">Locating Columns in the Buffer</span></span>
 <span data-ttu-id="d8ef6-141">La mémoire tampon d'entrée d'un composant contient toutes les colonnes définies dans les collections de colonnes de sortie des composants situés en amont du composant dans le flux de données.</span><span class="sxs-lookup"><span data-stu-id="d8ef6-141">The input buffer for a component contains all the columns defined in the output column collections of the components upstream from the component in the data flow.</span></span> <span data-ttu-id="d8ef6-142">Par exemple, si un composant source fournit trois colonnes dans sa sortie, et que le composant suivant ajoute une colonne de sortie supplémentaire, la mémoire tampon fournie au composant de destination contient quatre colonnes, même si le composant de destination n'écrit que deux colonnes.</span><span class="sxs-lookup"><span data-stu-id="d8ef6-142">For example, if a source component provides three columns in its output, and the next component adds an additional output column, the buffer provided to the destination component contains four columns, even if the destination component will write only two columns.</span></span>

 <span data-ttu-id="d8ef6-143">L'ordre des colonnes dans la mémoire tampon d'entrée n'est pas défini par l'index de la colonne dans la collection de colonnes d'entrée du composant de destination.</span><span class="sxs-lookup"><span data-stu-id="d8ef6-143">The order of the columns in the input buffer is not defined by the index of the column in the input column collection of the destination component.</span></span> <span data-ttu-id="d8ef6-144">Des colonnes peuvent être placées de manière fiable dans une ligne de la mémoire tampon à l'aide de la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A> de <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A>.</span><span class="sxs-lookup"><span data-stu-id="d8ef6-144">Columns can be reliably located in a buffer row only by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.BufferManager%2A>.</span></span> <span data-ttu-id="d8ef6-145">Cette méthode recherche la colonne avec l'ID de lignage spécifié dans la mémoire tampon spécifiée et retourne son emplacement dans la ligne.</span><span class="sxs-lookup"><span data-stu-id="d8ef6-145">This method locates the column that has the specified lineage ID in the specified buffer, and returns its location in the row.</span></span> <span data-ttu-id="d8ef6-146">Les index des colonnes d'entrée sont généralement localisés lors de l'exécution de la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> et mis en cache afin d'être utilisés ultérieurement par le développeur lors de l'exécution de la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="d8ef6-146">The indexes of the input columns are typically located during the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> method, and cached by the developer for use later during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span></span>

 <span data-ttu-id="d8ef6-147">L'exemple de code suivant recherche l'emplacement des colonnes d'entrée dans la mémoire tampon pendant l'exécution de la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> et les stocke dans un tableau.</span><span class="sxs-lookup"><span data-stu-id="d8ef6-147">The following code example finds the location of the input columns in the buffer during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> and stores them in an array.</span></span> <span data-ttu-id="d8ef6-148">Le tableau est ensuite utilisé au cours de l'exécution de la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> pour lire les valeurs des colonnes dans la mémoire tampon.</span><span class="sxs-lookup"><span data-stu-id="d8ef6-148">The array is subsequently used during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A> to read the values of the columns in the buffer.</span></span>

```csharp
int[] cols;

public override void PreExecute()
{
    IDTSInput100 input = ComponentMetaData.InputCollection[0];

    cols = new int[input.InputColumnCollection.Count];

    for (int x = 0; x < input.InputColumnCollection.Count; x++)
    {
        cols[x] = BufferManager.FindColumnByLineageID(input.Buffer, input.InputColumnCollection[x].LineageID);
    }
}
```

```vb
Private cols As Integer()

Public Overrides Sub PreExecute()

    Dim input As IDTSInput100 = ComponentMetaData.InputCollection(0)

    ReDim cols(input.InputColumnCollection.Count)

    For x As Integer = 0 To input.InputColumnCollection.Count

        cols(x) = BufferManager.FindColumnByLineageID(input.Buffer, input.InputColumnCollection(x).LineageID)
    Next x

End Sub
```

### <a name="processing-rows"></a><span data-ttu-id="d8ef6-149">Traitement de lignes</span><span class="sxs-lookup"><span data-stu-id="d8ef6-149">Processing Rows</span></span>
 <span data-ttu-id="d8ef6-150">Une fois que les colonnes d'entrée ont été localisées dans la mémoire tampon, elles peuvent être lues et écrites dans la source de données externe.</span><span class="sxs-lookup"><span data-stu-id="d8ef6-150">Once the input columns have been located in the buffer, they can be read and written to the external data source.</span></span>

 <span data-ttu-id="d8ef6-151">Pendant que le composant de destination écrit des lignes dans la source de données externe, vous pouvez mettre à jour les compteurs de performance « Lignes lues » ou « Octets BLOB lus » en appelant la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.IncrementPipelinePerfCounter%2A>.</span><span class="sxs-lookup"><span data-stu-id="d8ef6-151">While the destination component writes rows to the external data source, you may want to update the "Rows read" or "BLOB bytes read" performance counters by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.IncrementPipelinePerfCounter%2A> method.</span></span> <span data-ttu-id="d8ef6-152">Pour plus d’informations, consultez [Compteurs de performances](../performance/performance-counters.md).</span><span class="sxs-lookup"><span data-stu-id="d8ef6-152">For more information, see [Performance Counters](../performance/performance-counters.md).</span></span>

 <span data-ttu-id="d8ef6-153">L'exemple suivant présente un composant qui lit des lignes à partir de la mémoire tampon fournie dans <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span><span class="sxs-lookup"><span data-stu-id="d8ef6-153">The following example shows a component that reads rows from the buffer provided in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProcessInput%2A>.</span></span> <span data-ttu-id="d8ef6-154">La recherche des index des colonnes dans la mémoire tampon a été effectuée au cours de l'exécution de la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> dans l'exemple de code précédent.</span><span class="sxs-lookup"><span data-stu-id="d8ef6-154">The indexes of the columns in the buffer were located during <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> in the preceding code example.</span></span>

```csharp
public override void ProcessInput(int inputID, PipelineBuffer buffer)
{
        while (buffer.NextRow())
        {
            foreach (int col in cols)
            {
                if (!buffer.IsNull(col))
                {
                    //  TODO: Read the column data.
                }
            }
        }
}
```

```vb
Public Overrides Sub ProcessInput(ByVal inputID As Integer, ByVal buffer As PipelineBuffer)

        While (buffer.NextRow())

            For Each col As Integer In cols

                If buffer.IsNull(col) = False Then

                    '  TODO: Read the column data.
                End If

            Next col
        End While
End Sub
```

## <a name="sample"></a><span data-ttu-id="d8ef6-155">Exemple</span><span class="sxs-lookup"><span data-stu-id="d8ef6-155">Sample</span></span>
 <span data-ttu-id="d8ef6-156">L'exemple suivant montre un composant de destination simple qui utilise un gestionnaire de connexions de fichiers pour enregistrer les données binaires du flux de données dans des fichiers.</span><span class="sxs-lookup"><span data-stu-id="d8ef6-156">The following sample shows a simple destination component that uses a File connection manager to save binary data from the data flow into files.</span></span> <span data-ttu-id="d8ef6-157">Cet exemple ne contient pas toutes les méthodes et fonctionnalités présentées dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="d8ef6-157">This sample does not demonstrate all the methods and functionality discussed in this topic.</span></span> <span data-ttu-id="d8ef6-158">Il illustre les méthodes importantes que chaque composant de destination personnalisé doit substituer, mais ne contient pas de code pour la validation au moment de la conception.</span><span class="sxs-lookup"><span data-stu-id="d8ef6-158">It demonstrates the important methods that every custom destination component must override, but does not contain code for design-time validation.</span></span>

```csharp
using System;
using System.IO;
using Microsoft.SqlServer.Dts.Pipeline;
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;

namespace BlobDst
{
  [DtsPipelineComponent(DisplayName = "BLOB Extractor Destination", Description = "Writes values of BLOB columns to files")]
  public class BlobDst : PipelineComponent
  {
    string m_DestDir;
    int m_FileNameColumnIndex = -1;
    int m_BlobColumnIndex = -1;

    public override void ProvideComponentProperties()
    {
      IDTSInput100 input = ComponentMetaData.InputCollection.New();
      input.Name = "BLOB Extractor Destination Input";
      input.HasSideEffects = true;

      IDTSRuntimeConnection100 conn = ComponentMetaData.RuntimeConnectionCollection.New();
      conn.Name = "FileConnection";
    }

    public override void AcquireConnections(object transaction)
    {
      IDTSRuntimeConnection100 conn = ComponentMetaData.RuntimeConnectionCollection[0];
      m_DestDir = (string)conn.ConnectionManager.AcquireConnection(null);

      if (m_DestDir.Length > 0 && m_DestDir[m_DestDir.Length - 1] != '\\')
        m_DestDir += "\\";
    }

    public override IDTSInputColumn100 SetUsageType(int inputID, IDTSVirtualInput100 virtualInput, int lineageID, DTSUsageType usageType)
    {
      IDTSInputColumn100 inputColumn = base.SetUsageType(inputID, virtualInput, lineageID, usageType);
      IDTSCustomProperty100 custProp;

      custProp = inputColumn.CustomPropertyCollection.New();
      custProp.Name = "IsFileName";
      custProp.Value = (object)false;

      custProp = inputColumn.CustomPropertyCollection.New();
      custProp.Name = "IsBLOB";
      custProp.Value = (object)false;

      return inputColumn;
    }

    public override void PreExecute()
    {
      IDTSInput100 input = ComponentMetaData.InputCollection[0];
      IDTSInputColumnCollection100 inputColumns = input.InputColumnCollection;
      IDTSCustomProperty100 custProp;

      foreach (IDTSInputColumn100 column in inputColumns)
      {
        custProp = column.CustomPropertyCollection["IsFileName"];
        if ((bool)custProp.Value == true)
        {
          m_FileNameColumnIndex = (int)BufferManager.FindColumnByLineageID(input.Buffer, column.LineageID);
        }

        custProp = column.CustomPropertyCollection["IsBLOB"];
        if ((bool)custProp.Value == true)
        {
          m_BlobColumnIndex = (int)BufferManager.FindColumnByLineageID(input.Buffer, column.LineageID);
        }
      }
    }

    public override void ProcessInput(int inputID, PipelineBuffer buffer)
    {
      while (buffer.NextRow())
      {
        string strFileName = buffer.GetString(m_FileNameColumnIndex);
        int blobLength = (int)buffer.GetBlobLength(m_BlobColumnIndex);
        byte[] blobData = buffer.GetBlobData(m_BlobColumnIndex, 0, blobLength);

        strFileName = TranslateFileName(strFileName);

        // Make sure directory exists before creating file.
        FileInfo fi = new FileInfo(strFileName);
        if (!fi.Directory.Exists)
          fi.Directory.Create();

        // Write the data to the file.
        FileStream fs = new FileStream(strFileName, FileMode.Create, FileAccess.Write, FileShare.None);
        fs.Write(blobData, 0, blobLength);
        fs.Close();
      }
    }

    private string TranslateFileName(string fileName)
    {
      if (fileName.Length > 2 && fileName[1] == ':')
        return m_DestDir + fileName.Substring(3, fileName.Length - 3);
      else
        return m_DestDir + fileName;
    }
  }
}
```

```vb
Imports System 
Imports System.IO 
Imports Microsoft.SqlServer.Dts.Pipeline 
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper 
Namespace BlobDst 

 <DtsPipelineComponent(DisplayName="BLOB Extractor Destination", Description="Writes values of BLOB columns to files")> _ 
 Public Class BlobDst 
 Inherits PipelineComponent 
   Private m_DestDir As String 
   Private m_FileNameColumnIndex As Integer = -1 
   Private m_BlobColumnIndex As Integer = -1 

   Public  Overrides Sub ProvideComponentProperties() 
     Dim input As IDTSInput100 = ComponentMetaData.InputCollection.New 
     input.Name = "BLOB Extractor Destination Input" 
     input.HasSideEffects = True 
     Dim conn As IDTSRuntimeConnection100 = ComponentMetaData.RuntimeConnectionCollection.New 
     conn.Name = "FileConnection" 
   End Sub 

   Public  Overrides Sub AcquireConnections(ByVal transaction As Object) 
     Dim conn As IDTSRuntimeConnection100 = ComponentMetaData.RuntimeConnectionCollection(0) 
     m_DestDir = CType(conn.ConnectionManager.AcquireConnection(Nothing), String) 
     If m_DestDir.Length > 0 AndAlso Not (m_DestDir(m_DestDir.Length - 1) = "\"C) Then 
       m_DestDir += "\" 
     End If 
   End Sub 

   Public  Overrides Function SetUsageType(ByVal inputID As Integer, ByVal virtualInput As IDTSVirtualInput100, ByVal lineageID As Integer, ByVal usageType As DTSUsageType) As IDTSInputColumn100 
     Dim inputColumn As IDTSInputColumn100 = MyBase.SetUsageType(inputID, virtualInput, lineageID, usageType) 
     Dim custProp As IDTSCustomProperty100 
     custProp = inputColumn.CustomPropertyCollection.New 
     custProp.Name = "IsFileName" 
     custProp.Value = CType(False, Object) 
     custProp = inputColumn.CustomPropertyCollection.New 
     custProp.Name = "IsBLOB" 
     custProp.Value = CType(False, Object) 
     Return inputColumn 
   End Function 

   Public  Overrides Sub PreExecute() 
     Dim input As IDTSInput100 = ComponentMetaData.InputCollection(0) 
     Dim inputColumns As IDTSInputColumnCollection100 = input.InputColumnCollection 
     Dim custProp As IDTSCustomProperty100 
     For Each column As IDTSInputColumn100 In inputColumns 
       custProp = column.CustomPropertyCollection("IsFileName") 
       If CType(custProp.Value, Boolean) = True Then 
         m_FileNameColumnIndex = CType(BufferManager.FindColumnByLineageID(input.Buffer, column.LineageID), Integer) 
       End If 
       custProp = column.CustomPropertyCollection("IsBLOB") 
       If CType(custProp.Value, Boolean) = True Then 
         m_BlobColumnIndex = CType(BufferManager.FindColumnByLineageID(input.Buffer, column.LineageID), Integer) 
       End If 
     Next 
   End Sub 

   Public  Overrides Sub ProcessInput(ByVal inputID As Integer, ByVal buffer As PipelineBuffer) 
     While buffer.NextRow 
       Dim strFileName As String = buffer.GetString(m_FileNameColumnIndex) 
       Dim blobLength As Integer = CType(buffer.GetBlobLength(m_BlobColumnIndex), Integer) 
       Dim blobData As Byte() = buffer.GetBlobData(m_BlobColumnIndex, 0, blobLength) 
       strFileName = TranslateFileName(strFileName) 
       Dim fi As FileInfo = New FileInfo(strFileName) 
       ' Make sure directory exists before creating file.
       If Not fi.Directory.Exists Then 
         fi.Directory.Create 
       End If 
       ' Write the data to the file.
       Dim fs As FileStream = New FileStream(strFileName, FileMode.Create, FileAccess.Write, FileShare.None) 
       fs.Write(blobData, 0, blobLength) 
       fs.Close 
     End While 
   End Sub 

   Private Function TranslateFileName(ByVal fileName As String) As String 
     If fileName.Length > 2 AndAlso fileName(1) = ":"C Then 
       Return m_DestDir + fileName.Substring(3, fileName.Length - 3) 
     Else 
       Return m_DestDir + fileName 
     End If 
   End Function 
 End Class 
End Namespace
```

<span data-ttu-id="d8ef6-159">![Icône de Integration Services (petite)](../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="d8ef6-159">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="d8ef6-160">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="d8ef6-160">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="d8ef6-161">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="d8ef6-161">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="d8ef6-162">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="d8ef6-162">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="d8ef6-163">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d8ef6-163">See Also</span></span>
 <span data-ttu-id="d8ef6-164">[Développement d’un composant source personnalisé](../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md) [création d’une destination à l’aide du composant script](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md)</span><span class="sxs-lookup"><span data-stu-id="d8ef6-164">[Developing a Custom Source Component](../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md) [Creating a Destination with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md)</span></span>


