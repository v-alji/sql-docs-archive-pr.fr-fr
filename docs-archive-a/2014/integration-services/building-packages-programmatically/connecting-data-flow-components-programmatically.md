---
title: Connexion de composants de flux de données par programmation | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data flow task [Integration Services], components
- paths [Integration Services], components
- components [Integration Services], data flow
- data flow [Integration Services], components
ms.assetid: 404ecab7-7698-447b-93d6-dd256beb11ff
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 39494fee5314f309b79abfd30303fdd607fd3c50
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604094"
---
# <a name="connecting-data-flow-components-programmatically"></a><span data-ttu-id="c36d0-102">Connexion de composants de flux de données par programme</span><span class="sxs-lookup"><span data-stu-id="c36d0-102">Connecting Data Flow Components Programmatically</span></span>
  <span data-ttu-id="c36d0-103">Après avoir ajouté des composants à la tâche de flux de données, vous devez les connecter pour créer une arborescence d'exécution qui représente le flux de données des sources vers des destinations en passant par des transformations.</span><span class="sxs-lookup"><span data-stu-id="c36d0-103">After you have added components to the data flow task, you connect them to create an execution tree that represents the flow of data from sources through transformations to destinations.</span></span> <span data-ttu-id="c36d0-104">Ces objets <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100> permettent de connecter les composants du flux de données.</span><span class="sxs-lookup"><span data-stu-id="c36d0-104">You use <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100> objects to connect the components in the data flow.</span></span>  
  
## <a name="creating-a-path"></a><span data-ttu-id="c36d0-105">Création d'un chemin d'accès</span><span class="sxs-lookup"><span data-stu-id="c36d0-105">Creating a Path</span></span>  
 <span data-ttu-id="c36d0-106">Appelez la méthode New de la propriété <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.MainPipeClass.PathCollection%2A> de l’interface <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.MainPipe> pour créer un chemin et l’ajouter à la collection de chemins dans la tâche de flux de données.</span><span class="sxs-lookup"><span data-stu-id="c36d0-106">Call the New method of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.MainPipeClass.PathCollection%2A> property of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.MainPipe> interface to create a new path and add it to the collection of paths in the data flow task.</span></span> <span data-ttu-id="c36d0-107">Cette méthode retourne un nouvel objet <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100> déconnecté, que vous utilisez alors pour connecter deux composants.</span><span class="sxs-lookup"><span data-stu-id="c36d0-107">This method returns a new, disconnected <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100> object, which you then use to connect two components.</span></span>  
  
 <span data-ttu-id="c36d0-108">Appelez la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100.AttachPathAndPropagateNotifications%2A> pour connecter le chemin d'accès et indiquer aux composants faisant partie du chemin d'accès qu'ils ont été connectés.</span><span class="sxs-lookup"><span data-stu-id="c36d0-108">Call the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100.AttachPathAndPropagateNotifications%2A> method to connect the path and to notify the components participating in the path that they have been connected.</span></span> <span data-ttu-id="c36d0-109">Cette méthode accepte un <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> du composant en amont et un <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100> du composant en aval en tant que paramètres.</span><span class="sxs-lookup"><span data-stu-id="c36d0-109">This method accepts an <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> of the upstream component and an <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100> of the downstream component as parameters.</span></span> <span data-ttu-id="c36d0-110">Par défaut, l'appel à la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> du composant crée une entrée unique pour les composants qui possèdent des entrées, et une sortie unique pour les composants qui possèdent des sorties.</span><span class="sxs-lookup"><span data-stu-id="c36d0-110">By default, the call to the component's <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> method creates a single input for components that have inputs, and a single output for components that have outputs.</span></span> <span data-ttu-id="c36d0-111">L'exemple suivant utilise cette sortie par défaut de la source et cette entrée par défaut de la destination.</span><span class="sxs-lookup"><span data-stu-id="c36d0-111">The following example uses this default output of the source and input of the destination.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="c36d0-112">étape suivante</span><span class="sxs-lookup"><span data-stu-id="c36d0-112">Next Step</span></span>  
 <span data-ttu-id="c36d0-113">Après avoir établi un chemin entre deux composants, l’étape suivante consiste à mapper les colonnes d’entrée dans le composant en aval, comme indiqué dans la nouvelle rubrique, [Sélection de colonnes d’entrée par programmation](../building-packages-programmatically/selecting-input-columns-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="c36d0-113">After you establish a path between two components, the next step is to map input columns in the downstream component, which is discussed in the next topic, [Selecting Input Columns Programmatically](../building-packages-programmatically/selecting-input-columns-programmatically.md).</span></span>  
  
## <a name="sample"></a><span data-ttu-id="c36d0-114">Exemple</span><span class="sxs-lookup"><span data-stu-id="c36d0-114">Sample</span></span>  
 <span data-ttu-id="c36d0-115">L'exemple de code suivant indique comment établir un chemin d'accès entre deux composants.</span><span class="sxs-lookup"><span data-stu-id="c36d0-115">The following code sample shows how to establish a path between two components.</span></span>  
  
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
      Package package = new Package();  
      Executable e = package.Executables.Add("STOCK:PipelineTask");  
      TaskHost thMainPipe = e as TaskHost;  
      MainPipe dataFlowTask = thMainPipe.InnerObject as MainPipe;  
  
      // Create the source component.    
      IDTSComponentMetaData100 source =  
        dataFlowTask.ComponentMetaDataCollection.New();  
      source.ComponentClassID = "DTSAdapter.OleDbSource";  
      CManagedComponentWrapper srcDesignTime = source.Instantiate();  
      srcDesignTime.ProvideComponentProperties();  
  
      // Create the destination component.  
      IDTSComponentMetaData100 destination =  
        dataFlowTask.ComponentMetaDataCollection.New();  
      destination.ComponentClassID = "DTSAdapter.OleDbDestination";  
      CManagedComponentWrapper destDesignTime = destination.Instantiate();  
      destDesignTime.ProvideComponentProperties();  
  
      // Create the path.  
      IDTSPath100 path = dataFlowTask.PathCollection.New();  
      path.AttachPathAndPropagateNotifications(source.OutputCollection[0],  
        destination.InputCollection[0]);  
    }  
  }  
```  
  
 <span data-ttu-id="c36d0-116">}</span><span class="sxs-lookup"><span data-stu-id="c36d0-116">}</span></span>  
  
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
  
    ' Create the source component.    
    Dim source As IDTSComponentMetaData100 = _  
      dataFlowTask.ComponentMetaDataCollection.New()  
    source.ComponentClassID = "DTSAdapter.OleDbSource"  
    Dim srcDesignTime As CManagedComponentWrapper = source.Instantiate()  
    srcDesignTime.ProvideComponentProperties()  
  
    ' Create the destination component.  
    Dim destination As IDTSComponentMetaData100 = _  
      dataFlowTask.ComponentMetaDataCollection.New()  
    destination.ComponentClassID = "DTSAdapter.OleDbDestination"  
    Dim destDesignTime As CManagedComponentWrapper = destination.Instantiate()  
    destDesignTime.ProvideComponentProperties()  
  
    ' Create the path.  
    Dim path As IDTSPath100 = dataFlowTask.PathCollection.New()  
    path.AttachPathAndPropagateNotifications(source.OutputCollection(0), _  
      destination.InputCollection(0))  
  
  End Sub  
  
End Module  
```  
  
<span data-ttu-id="c36d0-117">![Icône de Integration Services (petite)](../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="c36d0-117">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="c36d0-118">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="c36d0-118">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="c36d0-119">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="c36d0-119">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="c36d0-120">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="c36d0-120">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c36d0-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c36d0-121">See Also</span></span>  
 [<span data-ttu-id="c36d0-122">Sélection de colonnes d'entrée par programme</span><span class="sxs-lookup"><span data-stu-id="c36d0-122">Selecting Input Columns Programmatically</span></span>](../building-packages-programmatically/selecting-input-columns-programmatically.md)  
  
  
