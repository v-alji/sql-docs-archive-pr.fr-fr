---
title: Création d’un composant de flux de données personnalisé | Microsoft Docs
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
- design-time component interface [Integration Services]
- custom data flow components [Integration Services], about data flow components
- custom data flow components [Integration Services]
- data flow components [Integration Services]
- data flow components [Integration Services], developing
ms.assetid: 9d96bcf5-eba8-44bd-b113-ed51ad0d0521
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 110d07ff88707ad1a01f299b6f532df99ce58404
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611184"
---
# <a name="creating-a-custom-data-flow-component"></a><span data-ttu-id="59b86-102">Création d'un composant de flux de données personnalisé</span><span class="sxs-lookup"><span data-stu-id="59b86-102">Creating a Custom Data Flow Component</span></span>
  <span data-ttu-id="59b86-103">Dans [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], la tâche de flux de données expose un modèle objet qui permet aux développeurs de créer des composants de flux de données personnalisés (sources, transformations et destinations) à l’aide de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] et de code managé.</span><span class="sxs-lookup"><span data-stu-id="59b86-103">In [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], the data flow task exposes an object model that lets developers create custom data flow components-sources, transformations, and destinations-by using the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] and managed code.</span></span>  
  
 <span data-ttu-id="59b86-104">Une tâche de flux de données comprend des composants qui contiennent une interface <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> et une collection d'objets <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100> qui définissent le déplacement de données entre les composants.</span><span class="sxs-lookup"><span data-stu-id="59b86-104">A data flow task consists of components that contain an <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface and a collection of <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSPath100> objects that define the movement of data between components.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="59b86-105">Lorsque vous créez un fournisseur personnalisé, vous devez mettre à jour le dossier ProviderDescriptors.xml avec les valeurs de la colonne de métadonnées.</span><span class="sxs-lookup"><span data-stu-id="59b86-105">When you create a custom provider, you need to update the ProviderDescriptors.xml file with the metadata column values.</span></span>  
  
## <a name="design-time-and-run-time"></a><span data-ttu-id="59b86-106">Moment de la conception et moment de l'exécution</span><span class="sxs-lookup"><span data-stu-id="59b86-106">Design Time and Run Time</span></span>  
 <span data-ttu-id="59b86-107">Avant l'exécution, la tâche de flux de données est dite au moment de la conception, puisqu'elle subit des modifications incrémentielles.</span><span class="sxs-lookup"><span data-stu-id="59b86-107">Before execution, the data flow task is said to be in a design-time state, as it undergoes incremental changes.</span></span> <span data-ttu-id="59b86-108">Les modifications peuvent inclure l'ajout ou la suppression de composants, l'ajout ou la suppression d'objets de chemin d'accès qui connectent des composants, ainsi que des modifications apportées aux métadonnées des composants.</span><span class="sxs-lookup"><span data-stu-id="59b86-108">Changes may include the addition or removal of components, the addition or removal of the path objects that connect components, and changes to the metadata of the components.</span></span> <span data-ttu-id="59b86-109">Lorsque des modifications de métadonnées se produisent, le composant peut les surveiller et y réagir.</span><span class="sxs-lookup"><span data-stu-id="59b86-109">When metadata changes occur, the component can monitor and react to the changes.</span></span> <span data-ttu-id="59b86-110">Par exemple, un composant peut rejeter certaines modifications ou apporter des modifications supplémentaires en réponse à une modification.</span><span class="sxs-lookup"><span data-stu-id="59b86-110">For example, a component can disallow certain changes or to make additional changes in response to a change.</span></span> <span data-ttu-id="59b86-111">Au moment de la conception, le concepteur interagit avec un composant via l'interface <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100> du moment de la conception.</span><span class="sxs-lookup"><span data-stu-id="59b86-111">At design time, the designer interacts with a component through the design-time <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100> interface.</span></span>  
  
 <span data-ttu-id="59b86-112">Au moment de l'exécution, la tâche de flux de données examine la séquence de composants, prépare un plan d'exécution et gère un pool de threads de travail qui exécute le plan de travail.</span><span class="sxs-lookup"><span data-stu-id="59b86-112">At execution time, the data flow task examines the sequence of components, prepares an execution plan, and manages a pool of worker threads that execute the work plan.</span></span> <span data-ttu-id="59b86-113">Bien que chaque thread de travail effectue un travail qui est interne à la tâche de flux de données, la tâche principale du thread de travail consiste à appeler les méthodes du composant via l'interface <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100> du moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="59b86-113">Although each worker thread performs some work that is internal to the data flow task, the principal task of the worker thread is to call the methods of the component through the run-time <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100> interface.</span></span>  
  
## <a name="creating-a-component"></a><span data-ttu-id="59b86-114">Création d'un composant</span><span class="sxs-lookup"><span data-stu-id="59b86-114">Creating a Component</span></span>  
 <span data-ttu-id="59b86-115">Pour créer un composant de flux de données, vous dérivez une classe de la classe de base <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent>, vous appliquez la classe <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute>, puis vous remplacez les méthodes appropriées de la classe de base.</span><span class="sxs-lookup"><span data-stu-id="59b86-115">To create a data flow component, you derive a class from the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> base class, apply the <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute> class, and then override the appropriate methods of the base class.</span></span> <span data-ttu-id="59b86-116">L'objet <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> implémente les interfaces <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100> et <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100>, puis expose leurs méthodes pour que vous les remplaciez dans votre composant.</span><span class="sxs-lookup"><span data-stu-id="59b86-116">The <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> implements the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100> and <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSRuntimeComponent100> interfaces, and exposes their methods for you to override in your component.</span></span>  
  
 <span data-ttu-id="59b86-117">Selon les objets utilisés par votre composant, votre projet requerra des références à une partie ou la totalité des assemblys suivants :</span><span class="sxs-lookup"><span data-stu-id="59b86-117">Depending on the objects used by your component, your project will require references to some or all of the following assemblies:</span></span>  
  
|<span data-ttu-id="59b86-118">Fonctionnalité</span><span class="sxs-lookup"><span data-stu-id="59b86-118">Feature</span></span>|<span data-ttu-id="59b86-119">Assembly à référencer</span><span class="sxs-lookup"><span data-stu-id="59b86-119">Assembly to reference</span></span>|<span data-ttu-id="59b86-120">Espace de noms à importer</span><span class="sxs-lookup"><span data-stu-id="59b86-120">Namespace to import</span></span>|  
|-------------|---------------------------|-------------------------|  
|<span data-ttu-id="59b86-121">Flux de données</span><span class="sxs-lookup"><span data-stu-id="59b86-121">Data flow</span></span>|<span data-ttu-id="59b86-122">Microsoft.SqlServer.PipelineHost</span><span class="sxs-lookup"><span data-stu-id="59b86-122">Microsoft.SqlServer.PipelineHost</span></span>|<xref:Microsoft.SqlServer.Dts.Pipeline>|  
|<span data-ttu-id="59b86-123">Wrapper de flux de données</span><span class="sxs-lookup"><span data-stu-id="59b86-123">Data flow wrapper</span></span>|<span data-ttu-id="59b86-124">Microsoft.SqlServer.DTSPipelineWrap</span><span class="sxs-lookup"><span data-stu-id="59b86-124">Microsoft.SqlServer.DTSPipelineWrap</span></span>|<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper>|  
|<span data-ttu-id="59b86-125">Runtime</span><span class="sxs-lookup"><span data-stu-id="59b86-125">Runtime</span></span>|<span data-ttu-id="59b86-126">Microsoft.SQLServer.ManagedDTS</span><span class="sxs-lookup"><span data-stu-id="59b86-126">Microsoft.SQLServer.ManagedDTS</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime>|  
|<span data-ttu-id="59b86-127">Wrapper d'exécution</span><span class="sxs-lookup"><span data-stu-id="59b86-127">Runtime wrapper</span></span>|<span data-ttu-id="59b86-128">Microsoft.SqlServer.DTSRuntimeWrap</span><span class="sxs-lookup"><span data-stu-id="59b86-128">Microsoft.SqlServer.DTSRuntimeWrap</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Wrapper>|  
  
 <span data-ttu-id="59b86-129">L'exemple de code suivant montre un composant simple dérivé de la classe de base, puis applique l'objet <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute>.</span><span class="sxs-lookup"><span data-stu-id="59b86-129">The following code example shows a simple component that derives from the base class, and applies the <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute>.</span></span> <span data-ttu-id="59b86-130">Vous devez ajouter une référence à l'assembly DTSPipelineWrap.</span><span class="sxs-lookup"><span data-stu-id="59b86-130">You need to add a reference to the DTSPipelineWrap assembly.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Pipeline;  
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;  
  
namespace Microsoft.Samples.SqlServer.Dts  
{  
    [DtsPipelineComponent(DisplayName = "SampleComponent", ComponentType = ComponentType.Transform )]  
    public class BasicComponent: PipelineComponent  
    {  
        // TODO: Override the base class methods.  
    }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Pipeline  
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper  
  
<DtsPipelineComponent(DisplayName:="SampleComponent", ComponentType:=ComponentType.Transform)> _  
Public Class BasicComponent  
  
    Inherits PipelineComponent  
  
    ' TODO: Override the base class methods.  
  
End Class  
```  
  
<span data-ttu-id="59b86-131">![Icône de Integration Services (petite)](../../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="59b86-131">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="59b86-132">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="59b86-132">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="59b86-133">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="59b86-133">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="59b86-134">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="59b86-134">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59b86-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="59b86-135">See Also</span></span>  
 [<span data-ttu-id="59b86-136">Développement d'une interface utilisateur pour un composant de flux de données</span><span class="sxs-lookup"><span data-stu-id="59b86-136">Developing a User Interface for a Data Flow Component</span></span>](developing-a-user-interface-for-a-data-flow-component.md)  
  
  
