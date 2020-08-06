---
title: Ajout de composants de flux de données par programmation | Microsoft Docs
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
- data flow task [Integration Services], components
- components [Integration Services], data flow
- data flow [Integration Services], components
ms.assetid: c06065cf-43e5-4b6b-9824-7309d7f5e35e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 807e758e42b738c4b0bf64b1d6f48bc29649ae6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604101"
---
# <a name="adding-data-flow-components-programmatically"></a><span data-ttu-id="dbf27-102">Ajout de composants de flux de données par programme</span><span class="sxs-lookup"><span data-stu-id="dbf27-102">Adding Data Flow Components Programmatically</span></span>
  <span data-ttu-id="dbf27-103">Lorsque vous générez un flux de données, vous commencez par ajouter des composants.</span><span class="sxs-lookup"><span data-stu-id="dbf27-103">When you build a data flow, you start by adding components.</span></span> <span data-ttu-id="dbf27-104">Puis vous configurez ces composants et vous les connectez ensemble pour établir le flux de données au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="dbf27-104">Then you configure those components and connect them together to establish the flow of data at run time.</span></span> <span data-ttu-id="dbf27-105">Cette section décrit l'ajout d'un composant à la tâche de flux de données, lequel permet de créer l'instance du moment de la conception du composant, puis de configurer ce composant.</span><span class="sxs-lookup"><span data-stu-id="dbf27-105">This section describes adding a component to the data flow task, creating the design-time instance of the component, and then configuring the component.</span></span> <span data-ttu-id="dbf27-106">Pour plus d’informations sur la connexion de composants, consultez [Connexion de composants de flux de données par programmation](../building-packages-programmatically/connecting-data-flow-components-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="dbf27-106">For information about how to connect components, see [Connecting Data Flow Components Programmatically](../building-packages-programmatically/connecting-data-flow-components-programmatically.md).</span></span>  
  
## <a name="adding-a-component"></a><span data-ttu-id="dbf27-107">Ajout d'un composant</span><span class="sxs-lookup"><span data-stu-id="dbf27-107">Adding a Component</span></span>  
 <span data-ttu-id="dbf27-108">Appelez la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaDataCollection100.New%2A> de la collection <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.MainPipeClass.ComponentMetaDataCollection%2A> pour créer un composant et l'ajouter à la tâche de flux de données.</span><span class="sxs-lookup"><span data-stu-id="dbf27-108">Call the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaDataCollection100.New%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.MainPipeClass.ComponentMetaDataCollection%2A> collection to create a new component and add it to the data flow task.</span></span> <span data-ttu-id="dbf27-109">Cette méthode renvoie l'interface <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> du composant.</span><span class="sxs-lookup"><span data-stu-id="dbf27-109">This method returns the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface of the component.</span></span> <span data-ttu-id="dbf27-110">Toutefois, à ce stade, l'objet <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> ne contient pas d'informations spécifiques à un composant.</span><span class="sxs-lookup"><span data-stu-id="dbf27-110">However, at this point, the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> does not contain information specific to any one component.</span></span> <span data-ttu-id="dbf27-111">Définissez la propriété <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ComponentClassID%2A> pour identifier le type de composant.</span><span class="sxs-lookup"><span data-stu-id="dbf27-111">Set the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ComponentClassID%2A> property to identify the type of component.</span></span> <span data-ttu-id="dbf27-112">La tâche de flux de données utilise la valeur de cette propriété pour créer une instance du composant au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="dbf27-112">The data flow task uses the value of this property to create an instance of the component at run time.</span></span>  
  
 <span data-ttu-id="dbf27-113">La valeur spécifiée dans la propriété <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ComponentClassID%2A> peut être le CLSID, le PROGID ou la propriété <xref:Microsoft.SqlServer.Dts.Runtime.PipelineComponentInfo.CreationName%2A> du composant.</span><span class="sxs-lookup"><span data-stu-id="dbf27-113">The value specified in the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ComponentClassID%2A> property can be the CLSID, PROGID, or <xref:Microsoft.SqlServer.Dts.Runtime.PipelineComponentInfo.CreationName%2A> property of the component.</span></span> <span data-ttu-id="dbf27-114">Le CLSID s'affiche normalement dans la fenêtre Propriétés en tant que valeur de la propriété <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ComponentClassID%2A> du composant.</span><span class="sxs-lookup"><span data-stu-id="dbf27-114">The CLSID is normally displayed in the Properties window as the value of the component's <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ComponentClassID%2A> property.</span></span> <span data-ttu-id="dbf27-115">Pour plus d’informations sur l’obtention de cette propriété et d’autres propriétés des composants disponibles, consultez [Découverte des composants de flux de données par programmation](../building-packages-programmatically/discovering-data-flow-components-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="dbf27-115">For information about obtaining this property and other properties of available components, see [Discovering Data Flow Components Programmatically](../building-packages-programmatically/discovering-data-flow-components-programmatically.md).</span></span>  
  
## <a name="adding-a-managed-component"></a><span data-ttu-id="dbf27-116">Ajout d'un composant managé</span><span class="sxs-lookup"><span data-stu-id="dbf27-116">Adding a Managed Component</span></span>  
 <span data-ttu-id="dbf27-117">Vous ne pouvez pas utiliser le CLSID ou le PROGID pour ajouter l'un des composants de flux de données managées au flux de données, parce que ces valeurs pointent vers un wrapper et non vers le composant lui-même.</span><span class="sxs-lookup"><span data-stu-id="dbf27-117">You cannot use the CLSID or PROGID to add one the managed data flow components to the data flow, because these values point to a wrapper and not to the component itself.</span></span> <span data-ttu-id="dbf27-118">Vous pouvez utiliser plutôt la propriété `CreationName` ou `AssemblyQualifiedName` comme indiqué dans l'exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="dbf27-118">Instead you can use the `CreationName` property or the `AssemblyQualifiedName` property as shown in the following sample.</span></span>  
  
 <span data-ttu-id="dbf27-119">Si vous envisagez d'utiliser la propriété `AssemblyQualifiedName`, vous devez ajouter une référence dans votre projet [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] à l'assembly qui contient le composant managé.</span><span class="sxs-lookup"><span data-stu-id="dbf27-119">If you intend to use the `AssemblyQualifiedName` property, then you must add a reference in your [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] project to the assembly that contains the managed component.</span></span> <span data-ttu-id="dbf27-120">Ces assemblys ne sont pas répertoriés sous l’onglet .NET de la boîte de dialogue **Ajouter une référence**.</span><span class="sxs-lookup"><span data-stu-id="dbf27-120">These assemblies are not listed on the .NET tab of the **Add Reference** dialog box.</span></span> <span data-ttu-id="dbf27-121">Vous devez généralement rechercher l’assembly dans le dossier **C:\Program Files\Microsoft SQL Server\100\DTS\PipelineComponents**.</span><span class="sxs-lookup"><span data-stu-id="dbf27-121">Normally you must browse to locate the assembly in the **C:\Program Files\Microsoft SQL Server\100\DTS\PipelineComponents** folder.</span></span>  
  
 <span data-ttu-id="dbf27-122">Les composants de flux de données managées intégrés incluent :</span><span class="sxs-lookup"><span data-stu-id="dbf27-122">The built-in managed data flow components include:</span></span>  
  
-   <span data-ttu-id="dbf27-123">Source [!INCLUDE[vstecado](../../includes/vstecado-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dbf27-123">[!INCLUDE[vstecado](../../includes/vstecado-md.md)] Source</span></span>  
  
-   <span data-ttu-id="dbf27-124">Source XML</span><span class="sxs-lookup"><span data-stu-id="dbf27-124">XML Source</span></span>  
  
-   <span data-ttu-id="dbf27-125">destination DataReader</span><span class="sxs-lookup"><span data-stu-id="dbf27-125">DataReader Destination</span></span>  
  
-   <span data-ttu-id="dbf27-126">Destination [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact</span><span class="sxs-lookup"><span data-stu-id="dbf27-126">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact Destination</span></span>  
  
-   <span data-ttu-id="dbf27-127">Composant Script</span><span class="sxs-lookup"><span data-stu-id="dbf27-127">Script Component</span></span>  
  
 <span data-ttu-id="dbf27-128">L'exemple de code suivant présente les deux façons d'ajouter un composant managé au flux de données :</span><span class="sxs-lookup"><span data-stu-id="dbf27-128">The following code sample shows both ways of adding a managed component to the data flow:</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
using Microsoft.SqlServer.Dts.Pipeline;  
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Microsoft.SqlServer.Dts.Runtime.Package package = new Microsoft.SqlServer.Dts.Runtime.Package();  
      Executable e = package.Executables.Add("STOCK:PipelineTask");  
      Microsoft.SqlServer.Dts.Runtime.TaskHost thMainPipe = (Microsoft.SqlServer.Dts.Runtime.TaskHost)e;  
      MainPipe dataFlowTask = (MainPipe)thMainPipe.InnerObject;  
  
      // The Application object will be used to obtain the CreationName  
      //  of a PipelineComponentInfo from its PipelineComponentInfos collection.  
      Application app = new Application();  
  
      // Add a first ADO NET source to the data flow.  
      //  The CreationName property requires an Application instance.  
      IDTSComponentMetaData100 component1 = dataFlowTask.ComponentMetaDataCollection.New();  
      component1.Name = "DataReader Source";  
      component1.ComponentClassID = app.PipelineComponentInfos["DataReader Source"].CreationName;  
  
      // Add a second ADO NET source to the data flow.  
      //  The AssemblyQualifiedName property requires a reference to the assembly.  
      IDTSComponentMetaData100 component2 = dataFlowTask.ComponentMetaDataCollection.New();  
      component2.Name = "DataReader Source";  
      component2.ComponentClassID = typeof(Microsoft.SqlServer.Dts.Pipeline.DataReaderSourceAdapter).AssemblyQualifiedName;  
    }  
  }  
}  
  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports Microsoft.SqlServer.Dts.Pipeline  
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper  
  
Module Module1  
  
  Sub Main()  
  
    Dim package As Microsoft.SqlServer.Dts.Runtime.Package = _  
      New Microsoft.SqlServer.Dts.Runtime.Package()  
    Dim e As Executable = package.Executables.Add("STOCK:PipelineTask")  
    Dim thMainPipe As Microsoft.SqlServer.Dts.Runtime.TaskHost = _  
      CType(e, Microsoft.SqlServer.Dts.Runtime.TaskHost)  
    Dim dataFlowTask As MainPipe = CType(thMainPipe.InnerObject, MainPipe)  
  
    ' The Application object will be used to obtain the CreationName  
    '  of a PipelineComponentInfo from its PipelineComponentInfos collection.  
    Dim app As New Application()  
  
    ' Add a first ADO NET source to the data flow.  
    '  The CreationName property requires an Application instance.  
    Dim component1 As IDTSComponentMetaData100 = _  
      dataFlowTask.ComponentMetaDataCollection.New()  
    component1.Name = "DataReader Source"  
    component1.ComponentClassID = app.PipelineComponentInfos("DataReader Source").CreationName  
  
    ' Add a second ADO NET source to the data flow.  
    '  The AssemblyQualifiedName property requires a reference to the assembly.  
    Dim component2 As IDTSComponentMetaData100 = _  
      dataFlowTask.ComponentMetaDataCollection.New()  
    component2.Name = "DataReader Source"  
    component2.ComponentClassID = _  
      GetType(Microsoft.SqlServer.Dts.Pipeline.DataReaderSourceAdapter).AssemblyQualifiedName  
  
  End Sub  
  
End Module  
```  
  
## <a name="creating-the-design-time-instance-of-the-component"></a><span data-ttu-id="dbf27-129">Création de l'instance de conception du composant</span><span class="sxs-lookup"><span data-stu-id="dbf27-129">Creating the Design-time Instance of the Component</span></span>  
 <span data-ttu-id="dbf27-130">Appelez la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.Instantiate%2A> pour créer l'instance de conception du composant identifié par la propriété <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ComponentClassID%2A>.</span><span class="sxs-lookup"><span data-stu-id="dbf27-130">Call the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.Instantiate%2A> method to create the design time instance of the component identified by the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ComponentClassID%2A> property.</span></span> <span data-ttu-id="dbf27-131">Cette méthode renvoie l'objet <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapper>, qui est le wrapper managé de l'interface <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100>.</span><span class="sxs-lookup"><span data-stu-id="dbf27-131">This method returns the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapper> object, which is the managed wrapper for the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100> interface.</span></span>  
  
 <span data-ttu-id="dbf27-132">Dès que possible, vous devez modifier un composant en utilisant les méthodes de l'instance de conception plutôt qu'en modifiant les métadonnées du composant directement.</span><span class="sxs-lookup"><span data-stu-id="dbf27-132">Whenever possible, you should modify a component by using the methods of the design-time instance instead of by modifying the component metadata directly.</span></span> <span data-ttu-id="dbf27-133">Bien qu'il existe des éléments à définir directement dans les métadonnées, tels que les connexions, il est généralement déconseillé de modifier les métadonnées directement parce que vous passez outre la capacité du composant à surveiller et valider les modifications.</span><span class="sxs-lookup"><span data-stu-id="dbf27-133">Although there are items in the metadata that you must set directly, such as connections, generally it is inadvisable to modify the metadata directly because you bypass the ability of the component to monitor and validate changes.</span></span>  
  
## <a name="assigning-connections"></a><span data-ttu-id="dbf27-134">Assignation de connexions</span><span class="sxs-lookup"><span data-stu-id="dbf27-134">Assigning Connections</span></span>  
 <span data-ttu-id="dbf27-135">Certains composants, tels que le composant source OLE DB, requièrent une connexion à des données externes et utilisent un objet <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> existant dans le package dans ce but.</span><span class="sxs-lookup"><span data-stu-id="dbf27-135">Some components, such as the OLE DB Source component, require a connection to external data and use an existing <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> object in the package for this purpose.</span></span> <span data-ttu-id="dbf27-136">La propriété <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnectionCollection100.Count%2A> de la collection <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A> indique le nombre d'objets <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> requis au moment de l'exécution par le composant.</span><span class="sxs-lookup"><span data-stu-id="dbf27-136">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnectionCollection100.Count%2A> property of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A> collection indicates the number of run-time <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> objects required by the component.</span></span> <span data-ttu-id="dbf27-137">Si le nombre est supérieur à zéro, le composant requiert une connexion.</span><span class="sxs-lookup"><span data-stu-id="dbf27-137">If the count is greater than zero, the component requires a connection.</span></span> <span data-ttu-id="dbf27-138">Assignez un gestionnaire de connexions depuis le package vers le composant en spécifiant les propriétés <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100.ConnectionManager%2A> et <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100.Name%2A> de la première connexion dans la propriété <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A>.</span><span class="sxs-lookup"><span data-stu-id="dbf27-138">Assign a connection manager from the package to the component by specifying the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100.ConnectionManager%2A> and <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeConnection100.Name%2A> properties of the first connection in the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.RuntimeConnectionCollection%2A>.</span></span> <span data-ttu-id="dbf27-139">Notez que le nom du gestionnaire de connexions figurant dans la collection de connexions au moment de l’exécution doit correspondre à celui du gestionnaire de connexions référencé depuis le package.</span><span class="sxs-lookup"><span data-stu-id="dbf27-139">Note that the name of the connection manager in the run-time connection collection must match the name of the connection managerreferenced from the package.</span></span>  
  
## <a name="setting-the-values-of-custom-properties"></a><span data-ttu-id="dbf27-140">Définition des valeurs des propriétés personnalisées</span><span class="sxs-lookup"><span data-stu-id="dbf27-140">Setting the Values of Custom Properties</span></span>  
 <span data-ttu-id="dbf27-141">Après avoir créé l'instance de conception du composant, appelez la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ProvideComponentProperties%2A>.</span><span class="sxs-lookup"><span data-stu-id="dbf27-141">After creating the design-time instance of the component, call the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ProvideComponentProperties%2A> method.</span></span> <span data-ttu-id="dbf27-142">Cette méthode est similaire à un constructeur parce qu'elle initialise un composant nouvellement créé en créant ses propriétés personnalisées et ses objets d'entrée et de sortie.</span><span class="sxs-lookup"><span data-stu-id="dbf27-142">This method is similar to a constructor because it initializes a newly created component by creating its custom properties and its input and output objects.</span></span> <span data-ttu-id="dbf27-143">N'appelez pas la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ProvideComponentProperties%2A> plusieurs fois sur un composant, parce que le composant risque de se réinitialiser et de perdre toutes les modifications précédemment apportées à ses métadonnées.</span><span class="sxs-lookup"><span data-stu-id="dbf27-143">Do not call <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ProvideComponentProperties%2A> more than one time on a component, because the component may reset itself and lose any modifications previously made to its metadata.</span></span>  
  
 <span data-ttu-id="dbf27-144">La propriété <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.CustomPropertyCollection%2A> du composant contient une collection d'objets <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100> propre au composant.</span><span class="sxs-lookup"><span data-stu-id="dbf27-144">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.CustomPropertyCollection%2A> of the component contains a collection of <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100> objects specific to the component.</span></span> <span data-ttu-id="dbf27-145">Contrairement à d'autres modèles de programmation, où les propriétés d'un objet sont toujours visibles sur l'objet, les composants renseignent uniquement leurs collections de propriétés personnalisées lorsque vous appelez la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ProvideComponentProperties%2A>.</span><span class="sxs-lookup"><span data-stu-id="dbf27-145">Unlike other programming models, where the properties of an object are always visible on the object, components only populate their custom property collections when you call the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ProvideComponentProperties%2A> method.</span></span> <span data-ttu-id="dbf27-146">Après avoir appelé la méthode, utilisez la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.SetComponentProperty%2A> de l'instance de conception du composant pour assigner des valeurs à ses propriétés personnalisées.</span><span class="sxs-lookup"><span data-stu-id="dbf27-146">After you call method, use the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.SetComponentProperty%2A> method of the design-time instance of the component to assign values to its custom properties.</span></span> <span data-ttu-id="dbf27-147">Cette méthode accepte une paire nom/valeur qui identifie la propriété personnalisée et fournit sa nouvelle valeur.</span><span class="sxs-lookup"><span data-stu-id="dbf27-147">This method accepts a name/value pair that identifies the custom property and provides its new value.</span></span>  
  
## <a name="initializing-output-columns"></a><span data-ttu-id="dbf27-148">Initialisation de colonnes de sortie</span><span class="sxs-lookup"><span data-stu-id="dbf27-148">Initializing Output Columns</span></span>  
 <span data-ttu-id="dbf27-149">Après avoir ajouté un composant à la tâche et l'avoir configuré, initialisez la collection de colonnes dans l'objet <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> de l'objet.</span><span class="sxs-lookup"><span data-stu-id="dbf27-149">After you add a component to the task and configure it, initialize the collection of columns in the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> of the object.</span></span> <span data-ttu-id="dbf27-150">Cette étape s'avère particulièrement utile pour les composants source, mais risque de ne pas initialiser les colonnes pour les composants de transformation et de destination parce qu'ils dépendent généralement des colonnes qu'ils reçoivent des composants en amont.</span><span class="sxs-lookup"><span data-stu-id="dbf27-150">This step is especially relevant for source components, but may not initialize the columns for transformation and destination components because they generally depend on the columns that they receive from upstream components.</span></span>  
  
 <span data-ttu-id="dbf27-151">Appelez la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ReinitializeMetaData%2A> pour initialiser les colonnes dans les sorties d'un composant source.</span><span class="sxs-lookup"><span data-stu-id="dbf27-151">Call the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ReinitializeMetaData%2A> method to initialize the columns in the outputs of a source component.</span></span> <span data-ttu-id="dbf27-152">Étant donné que les composants ne se connectent pas automatiquement aux sources de données externes, appelez la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.AcquireConnections%2A> avant d'appeler la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ReinitializeMetaData%2A> pour fournir au composant un accès à sa source de données externe et la capacité de renseigner ses métadonnées de colonne.</span><span class="sxs-lookup"><span data-stu-id="dbf27-152">Because components do not automatically connect to external data sources, call the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.AcquireConnections%2A> method before calling <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ReinitializeMetaData%2A> to provide the component access to its external data source and the ability to populate its column metadata.</span></span> <span data-ttu-id="dbf27-153">Enfin, appelez la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ReleaseConnections%2A> pour libérer la connexion.</span><span class="sxs-lookup"><span data-stu-id="dbf27-153">Finally, call the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapperClass.ReleaseConnections%2A> method to release the connection.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="dbf27-154">étape suivante</span><span class="sxs-lookup"><span data-stu-id="dbf27-154">Next Step</span></span>  
 <span data-ttu-id="dbf27-155">Après avoir ajouté et configuré le composant, l’étape suivante consiste à créer des chemins entre les composants, ce que décrit la rubrique [Création d’un chemin entre deux composants](../building-packages-programmatically/connecting-data-flow-components-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="dbf27-155">After adding and configuring the component, the next step is to create paths between components, which is discussed in the topic, [Creating a Path Between Two Components](../building-packages-programmatically/connecting-data-flow-components-programmatically.md).</span></span>  
  
## <a name="sample"></a><span data-ttu-id="dbf27-156">Exemple</span><span class="sxs-lookup"><span data-stu-id="dbf27-156">Sample</span></span>  
 <span data-ttu-id="dbf27-157">L'exemple de code suivant ajoute le composant source OLE DB à une tâche de flux de données, crée une instance de conception du composant et configure les propriétés du composant.</span><span class="sxs-lookup"><span data-stu-id="dbf27-157">The following code sample adds the OLE DB Source component to a data flow task, creates a design-time instance of the component, and configures the component's properties.</span></span> <span data-ttu-id="dbf27-158">Cet exemple requiert une référence supplémentaire à l'assembly Microsoft.SqlServer.DTSRuntimeWrap.</span><span class="sxs-lookup"><span data-stu-id="dbf27-158">This example requires an additional reference to the assembly Microsoft.SqlServer.DTSRuntimeWrap.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
using Microsoft.SqlServer.Dts.Runtime.Wrapper;  
using Microsoft.SqlServer.Dts.Pipeline;  
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Runtime.Package package = new Runtime.Package();  
      Executable e = package.Executables.Add("STOCK:PipelineTask");  
      Runtime.TaskHost thMainPipe = e as Runtime.TaskHost;  
      MainPipe dataFlowTask = thMainPipe.InnerObject as MainPipe;  
  
      // Add an OLEDB connection manager to the package.  
      ConnectionManager cm = package.Connections.Add("OLEDB");  
      cm.Name = "OLEDB ConnectionManager";  
      cm.ConnectionString = "Data Source=(local);" +   
        "Initial Catalog=AdventureWorks;Provider=SQLOLEDB.1;" +   
        "Integrated Security=SSPI;"  
  
      // Add an OLE DB source to the data flow.  
      IDTSComponentMetaData100 component =   
        dataFlowTask.ComponentMetaDataCollection.New();  
      component.Name = "OLEDBSource";  
      component.ComponentClassID = "DTSAdapter.OleDbSource.1";  
      // You can also use the CLSID of the component instead of the PROGID.  
      //component.ComponentClassID = "{2C0A8BE5-1EDC-4353-A0EF-B778599C65A0}";  
  
      // Get the design time instance of the component.  
      CManagedComponentWrapper instance = component.Instantiate();  
  
      // Initialize the component  
      instance.ProvideComponentProperties();  
  
      // Specify the connection manager.  
      if (component.RuntimeConnectionCollection.Count > 0)  
      {  
        component.RuntimeConnectionCollection[0].ConnectionManager =   
          DtsConvert.GetExtendedInterface(package.Connections[0]);  
        component.RuntimeConnectionCollection[0].ConnectionManagerID =   
          package.Connections[0].ID;      }  
  
      // Set the custom properties.  
      instance.SetComponentProperty("AccessMode", 2);  
      instance.SetComponentProperty("SqlCommand",   
        "Select * from Production.Product");  
  
      // Reinitialize the metadata.  
      instance.AcquireConnections(null);  
      instance.ReinitializeMetaData();  
      instance.ReleaseConnections();  
  
      // Add other components to the data flow and connect them.  
    }  
  }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports Microsoft.SqlServer.Dts.Runtime.Wrapper  
Imports Microsoft.SqlServer.Dts.Pipeline  
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper  
  
Module Module1  
  
  Sub Main()  
  
    Dim package As Microsoft.SqlServer.Dts.Runtime.Package = _  
      New Microsoft.SqlServer.Dts.Runtime.Package()  
    Dim e As Executable = package.Executables.Add("STOCK:PipelineTask")  
    Dim thMainPipe As Microsoft.SqlServer.Dts.Runtime.TaskHost = _  
      CType(e, Microsoft.SqlServer.Dts.Runtime.TaskHost)  
    Dim dataFlowTask As MainPipe = CType(thMainPipe.InnerObject, MainPipe)  
  
    ' Add an OLEDB connection manager to the package.  
    Dim cm As ConnectionManager = package.Connections.Add("OLEDB")  
    cm.Name = "OLEDB ConnectionManager"  
    cm.ConnectionString = "Data Source=(local);" & _  
      "Initial Catalog=AdventureWorks;Provider=SQLOLEDB.1;" & _  
      "Integrated Security=SSPI;"  
  
    ' Add an OLE DB source to the data flow.  
    Dim component As IDTSComponentMetaData100 = _  
      dataFlowTask.ComponentMetaDataCollection.New()  
    component.Name = "OLEDBSource"  
    component.ComponentClassID = "DTSAdapter.OleDbSource.1"  
    ' You can also use the CLSID of the component instead of the PROGID.  
    'component.ComponentClassID = "{2C0A8BE5-1EDC-4353-A0EF-B778599C65A0}";  
  
    ' Get the design time instance of the component.  
    Dim instance As CManagedComponentWrapper = component.Instantiate()  
  
    ' Initialize the component.  
    instance.ProvideComponentProperties()  
  
    ' Specify the connection manager.  
    If component.RuntimeConnectionCollection.Count > 0 Then  
      component.RuntimeConnectionCollection(0).ConnectionManager = _  
        DtsConvert.GetExtendedInterface(package.Connections(0))  
      component.RuntimeConnectionCollection(0).ConnectionManagerID = _  
        package.Connections(0).ID  
    End If  
  
    ' Set the custom properties.  
    instance.SetComponentProperty("AccessMode", 2)  
    instance.SetComponentProperty("SqlCommand", _  
      "Select * from Production.Product")  
  
    ' Reinitialize the metadata.  
    instance.AcquireConnections(vbNull)  
    instance.ReinitializeMetaData()  
    instance.ReleaseConnections()  
  
    ' Add other components to the data flow and connect them.  
  
  End Sub  
  
End Module  
```  
  
## <a name="external-resources"></a><span data-ttu-id="dbf27-159">Ressources externes</span><span class="sxs-lookup"><span data-stu-id="dbf27-159">External Resources</span></span>  
 <span data-ttu-id="dbf27-160">Entrée de blog, [EzAPI - Updated for SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=243223), sur blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="dbf27-160">Blog entry, [EzAPI - Updated for SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=243223), on blogs.msdn.com.</span></span>  
  
<span data-ttu-id="dbf27-161">![Icône de Integration Services (petite)](../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="dbf27-161">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="dbf27-162">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="dbf27-162">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="dbf27-163">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="dbf27-163">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="dbf27-164">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="dbf27-164">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbf27-165">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="dbf27-165">See Also</span></span>  
 [<span data-ttu-id="dbf27-166">Connexion de composants de flux de données par programme</span><span class="sxs-lookup"><span data-stu-id="dbf27-166">Connecting Data Flow Components Programmatically</span></span>](../building-packages-programmatically/connecting-data-flow-components-programmatically.md)  
  
  
