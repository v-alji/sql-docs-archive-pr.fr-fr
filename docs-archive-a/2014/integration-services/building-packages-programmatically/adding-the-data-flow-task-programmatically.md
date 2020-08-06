---
title: Ajout de la tâche de flux de données par programmation | Microsoft Docs
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
- adding Data Flow task
- SSIS data flow
- data flow task [Integration Services], adding
- MainPipe object
ms.assetid: 0ca03712-a82e-4aa7-949b-f869a8936ddf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4f7e699cc8e88bafb2a4508fdac8560fa73befe1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604098"
---
# <a name="adding-the-data-flow-task-programmatically"></a><span data-ttu-id="ec6bd-102">Ajout de la tâche de flux de données par programmation</span><span class="sxs-lookup"><span data-stu-id="ec6bd-102">Adding the Data Flow Task Programmatically</span></span>
  [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] <span data-ttu-id="ec6bd-103">inclut une tâche appelée flux de données, représentée par l'espace de noms <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper> dans le modèle objet.</span><span class="sxs-lookup"><span data-stu-id="ec6bd-103">includes a task called the Data Flow task, which is represented by the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper> namespace in the object model.</span></span> <span data-ttu-id="ec6bd-104">La tâche de flux de données est une tâche spécialisée, hautement performante, dédiée à la transformation et au déplacement de données pendant l'exécution de package.</span><span class="sxs-lookup"><span data-stu-id="ec6bd-104">The Data Flow task is a specialized, high-performance task, dedicated to transforming and moving data during package execution.</span></span> <span data-ttu-id="ec6bd-105">Comme les autres tâches, la tâche de flux de données est encapsulée par l'objet <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> et, du point de vue du moteur d'exécution, rien ne la différencie des autres tâches du package.</span><span class="sxs-lookup"><span data-stu-id="ec6bd-105">Like other tasks, the Data Flow task is wrapped by the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> object, and from the perspective of the run-time engine, this task is just another task in the package.</span></span> <span data-ttu-id="ec6bd-106">Toutefois, le flux de données contient des objets supplémentaires appelés composants de flux de données.</span><span class="sxs-lookup"><span data-stu-id="ec6bd-106">However, the data flow contains additional objects called data flow components.</span></span> <span data-ttu-id="ec6bd-107">Il s'agit des composants qui permettent de déplacer les données d'une source à une destination, parfois par le biais d'une transformation.</span><span class="sxs-lookup"><span data-stu-id="ec6bd-107">These components are the components that make data move from a source to a destination, sometimes through a transformation.</span></span> <span data-ttu-id="ec6bd-108">Les composants définissent le sens du déplacement et le mode de transformation des données.</span><span class="sxs-lookup"><span data-stu-id="ec6bd-108">The components define both the direction of movement and how data is transformed.</span></span> <span data-ttu-id="ec6bd-109">Pour configurer la tâche de flux de données, il est nécessaire d'ajouter des composants à la tâche, puis de les connecter pour établir le flux des données et obtenir la transformation souhaitée.</span><span class="sxs-lookup"><span data-stu-id="ec6bd-109">Configuring the Data Flow task involves adding components to the task, and then connecting them to establish the flow of data and achieve the intended transformation.</span></span>  
  
 <span data-ttu-id="ec6bd-110">Une tâche de flux de données comporte trois types de composants : **Sources de flux de données**, **Transformations du flux de données** et **Destinations du flux de données**, affichés dans cet ordre dans la boîte à outils du concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ec6bd-110">There are three types of components within a Data Flow task: **Data Flow Sources**, **Data Flow Transformations**, and **Data Flow Destinations**, shown in that order within the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer toolbox.</span></span> <span data-ttu-id="ec6bd-111">Ces types sont également appelés sources, transformations ou destinations pour simplifier.</span><span class="sxs-lookup"><span data-stu-id="ec6bd-111">These types are also referred to more simply as sources, transformations, or destinations.</span></span> <span data-ttu-id="ec6bd-112">Comme leur nom l'indique, les données sont acheminées d'une source à une transformation, puis à une destination.</span><span class="sxs-lookup"><span data-stu-id="ec6bd-112">As implied by the names, data flows from a source to a transformation, and then to a destination.</span></span> <span data-ttu-id="ec6bd-113">Cette description très simplifiée du flux de données permet d'illustrer le concept. Toutefois, la tâche de flux de données est suffisamment flexible et puissante pour gérer plusieurs sources et connecter de nombreuses transformations qui envoient la sortie à plusieurs destinations.</span><span class="sxs-lookup"><span data-stu-id="ec6bd-113">This is a simplistic description of the data flow to illustrate the concept, but the Data Flow task is flexible and powerful enough to handle multiple sources, and to connect together many transformations that send output to multiple destinations.</span></span>  
  
 <span data-ttu-id="ec6bd-114">La tâche de flux de données est ajoutée à un package de la même manière que les autres tâches sont ajoutées.</span><span class="sxs-lookup"><span data-stu-id="ec6bd-114">The Data Flow task is added to a package the same way other tasks are added.</span></span> <span data-ttu-id="ec6bd-115">Une fois que la tâche de flux de données a été ajoutée, vous pouvez la configurer en y ajoutant des composants que vous pourrez configurer et connecter à la tâche.</span><span class="sxs-lookup"><span data-stu-id="ec6bd-115">After the task has been added, it is configured by adding components to the data flow task, and configuring and connecting components in the task.</span></span>  
  
## <a name="sample"></a><span data-ttu-id="ec6bd-116">Exemple</span><span class="sxs-lookup"><span data-stu-id="ec6bd-116">Sample</span></span>  
 <span data-ttu-id="ec6bd-117">L'exemple de code suivant indique comment ajouter une tâche de flux de données à un package.</span><span class="sxs-lookup"><span data-stu-id="ec6bd-117">The following code sample shows how to add a Data Flow task to a package.</span></span> <span data-ttu-id="ec6bd-118">Cet exemple requiert une référence aux assemblys Microsoft.SqlServer.PipelineHost, Microsoft.SqlServer.DTSPipelineWrap et Microsoft.SqlServer.ManagedDTS.</span><span class="sxs-lookup"><span data-stu-id="ec6bd-118">This example requires a reference to the assemblies Microsoft.SqlServer.PipelineHost, Microsoft.SqlServer.DTSPipelineWrap, and Microsoft.SqlServer.ManagedDTS.</span></span>  
  
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
      Package p = new Package();  
      Executable e = p.Executables.Add("STOCK:PipelineTask");  
      TaskHost thMainPipe = e as TaskHost;  
      MainPipe dataFlowTask = thMainPipe.InnerObject as MainPipe;   
    }  
  }  
}  
```  
  
```vb  
Imports System.IO  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports Microsoft.SqlServer.Dts.Pipeline  
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper  
  
Module Module1  
  
  Sub Main()  
  
    Dim p As Package = New Package()  
    Dim e As Executable = p.Executables.Add("STOCK:PipelineTask")  
    Dim thMainPipe As TaskHost = CType(e, TaskHost)  
    Dim dataFlowTask As MainPipe = CType(thMainPipe.InnerObject, MainPipe)  
  
  End Sub  
  
End Module  
```  
  
## <a name="external-resources"></a><span data-ttu-id="ec6bd-119">Ressources externes</span><span class="sxs-lookup"><span data-stu-id="ec6bd-119">External Resources</span></span>  
 <span data-ttu-id="ec6bd-120">Entrée de blog, [EzAPI - Updated for SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=243223), sur blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="ec6bd-120">Blog entry, [EzAPI - Updated for SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=243223), on blogs.msdn.com.</span></span>  
  
<span data-ttu-id="ec6bd-121">![Icône de Integration Services (petite)](../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="ec6bd-121">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="ec6bd-122">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="ec6bd-122">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="ec6bd-123">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="ec6bd-123">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="ec6bd-124">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="ec6bd-124">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec6bd-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ec6bd-125">See Also</span></span>  
 [<span data-ttu-id="ec6bd-126">Découverte des composants de flux de données par programme</span><span class="sxs-lookup"><span data-stu-id="ec6bd-126">Discovering Data Flow Components Programmatically</span></span>](../building-packages-programmatically/discovering-data-flow-components-programmatically.md)  
  
  
