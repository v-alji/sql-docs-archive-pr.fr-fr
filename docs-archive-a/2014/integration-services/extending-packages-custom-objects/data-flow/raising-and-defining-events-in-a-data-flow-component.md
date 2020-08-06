---
title: Déclenchement et définition d’événements dans un composant de flux de données | Microsoft Docs
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
- data flow components [Integration Services], events
- events [Integration Services], custom
- custom events [Integration Services]
- custom data flow components [Integration Services], events
- events [Integration Services], raising
- predefined events [Integration Services]
ms.assetid: 1d8c5358-9384-47a8-b7cb-7b0650384119
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 25f4572f8a8af829145da4e4d685f5dddad4a29a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697003"
---
# <a name="raising-and-defining-events-in-a-data-flow-component"></a><span data-ttu-id="70eac-102">Déclenchement et définition d'événements dans un composant de flux de données</span><span class="sxs-lookup"><span data-stu-id="70eac-102">Raising and Defining Events in a Data Flow Component</span></span>
  <span data-ttu-id="70eac-103">Les développeurs de composants peuvent déclencher un sous-ensemble des événements définis dans l'interface <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents> en appelant les méthodes exposées sur la propriété <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A>.</span><span class="sxs-lookup"><span data-stu-id="70eac-103">Component developers can raise a subset of the events defined in the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents> interface by calling the methods exposed on the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A> property.</span></span> <span data-ttu-id="70eac-104">Vous pouvez également définir des événements personnalisés à l'aide de la collection <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.EventInfos%2A>, puis les déclencher pendant l'exécution en utilisant la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireCustomEvent%2A>.</span><span class="sxs-lookup"><span data-stu-id="70eac-104">You can also define custom events by using the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.EventInfos%2A> collection, and raise them during execution by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireCustomEvent%2A> method.</span></span> <span data-ttu-id="70eac-105">Cette section décrit comment créer et déclencher un événement. Elle fournit également des conseils sur l'opportunité de déclencher des événements au moment de la conception.</span><span class="sxs-lookup"><span data-stu-id="70eac-105">This section describes how to create and raise an event, and provides guidelines on when you should raise events at design time.</span></span>

## <a name="raising-events"></a><span data-ttu-id="70eac-106">Déclenchement d’événements</span><span class="sxs-lookup"><span data-stu-id="70eac-106">Raising Events</span></span>
 <span data-ttu-id="70eac-107">Les composants déclenchent des événements à l’aide des méthodes **Fire\<X>** de l’interface <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100>.</span><span class="sxs-lookup"><span data-stu-id="70eac-107">Components raise events by using the **Fire\<X>** methods of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface.</span></span> <span data-ttu-id="70eac-108">Vous pouvez déclencher des événements pendant la conception et l'exécution de composants.</span><span class="sxs-lookup"><span data-stu-id="70eac-108">You can raise events during component design and execution.</span></span> <span data-ttu-id="70eac-109">En général, les méthodes <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireError%2A> et <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireWarning%2A> sont appelées pendant la validation, lors de la conception de composants.</span><span class="sxs-lookup"><span data-stu-id="70eac-109">Typically, during component design, the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireError%2A> and <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireWarning%2A> methods are called during validation.</span></span> <span data-ttu-id="70eac-110">Ces événements affichent des messages dans le volet **Liste d’erreurs[!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] de**  et fournissent des commentaires aux utilisateurs du composant lorsque ce dernier n’est pas correctement configuré.</span><span class="sxs-lookup"><span data-stu-id="70eac-110">These events display messages in the **Error List** pane of [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] and provide feedback to users of the component when a component is incorrectly configured.</span></span>

 <span data-ttu-id="70eac-111">Les composants peuvent également déclencher des événements à tout moment pendant l'exécution.</span><span class="sxs-lookup"><span data-stu-id="70eac-111">Components can also raise events at any point during execution.</span></span> <span data-ttu-id="70eac-112">Les événements permettent aux développeurs de composants de fournir des commentaires aux utilisateurs du composant pendant son exécution.</span><span class="sxs-lookup"><span data-stu-id="70eac-112">Events allow component developers to provide feedback to users of the component as it executes.</span></span> <span data-ttu-id="70eac-113">L'appel de la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireError%2A> pendant l'exécution risque de provoquer l'échec du package.</span><span class="sxs-lookup"><span data-stu-id="70eac-113">Calling the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireError%2A> method during execution is likely to fail the package.</span></span>

## <a name="defining-and-raising-custom-events"></a><span data-ttu-id="70eac-114">Définition et déclenchement d'événements personnalisés</span><span class="sxs-lookup"><span data-stu-id="70eac-114">Defining and Raising Custom Events</span></span>

### <a name="defining-a-custom-event"></a><span data-ttu-id="70eac-115">Définition d'un événement personnalisé</span><span class="sxs-lookup"><span data-stu-id="70eac-115">Defining a Custom Event</span></span>
 <span data-ttu-id="70eac-116">L'appel de la méthode <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.IDTSEventInfos100.Add%2A> de la collection <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.EventInfos%2A> permet de créer des événements personnalisés.</span><span class="sxs-lookup"><span data-stu-id="70eac-116">Custom events are created by calling the <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.IDTSEventInfos100.Add%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.EventInfos%2A> collection.</span></span> <span data-ttu-id="70eac-117">Cette collection est définie par la tâche de flux de données et fournie en tant que propriété au développeur de composants par le biais de la classe de base <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent>.</span><span class="sxs-lookup"><span data-stu-id="70eac-117">This collection is set by the data flow task and provided as a property to the component developer through the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> base class.</span></span> <span data-ttu-id="70eac-118">Cette classe contient des événements personnalisés définis par la tâche de flux de données et des événements personnalisés définis par le composant pendant l'exécution de la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.RegisterEvents%2A>.</span><span class="sxs-lookup"><span data-stu-id="70eac-118">This class contains custom events defined by the data flow task and custom events defined by the component during the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.RegisterEvents%2A> method.</span></span>

 <span data-ttu-id="70eac-119">Les événements personnalisés d'un composant ne sont pas conservés dans le package XML.</span><span class="sxs-lookup"><span data-stu-id="70eac-119">The custom events of a component are not persisted in the package XML.</span></span> <span data-ttu-id="70eac-120">Par conséquent, la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.RegisterEvents%2A> est appelée pendant la conception et l'exécution pour permettre au composant de définir les événements qu'il déclenche.</span><span class="sxs-lookup"><span data-stu-id="70eac-120">Therefore, the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.RegisterEvents%2A> method is called during both design and execution to allow the component to define the events it raises.</span></span>

 <span data-ttu-id="70eac-121">Le paramètre *allowEventHandlers* de la méthode <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.IDTSEventInfos100.Add%2A> spécifie si le composant autorise la création d’objets <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> pour l’événement.</span><span class="sxs-lookup"><span data-stu-id="70eac-121">The *allowEventHandlers* parameter of the <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.IDTSEventInfos100.Add%2A> method specifies whether the component allows <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> objects to be created for the event.</span></span> <span data-ttu-id="70eac-122">Notez que les <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandlers> sont synchrones.</span><span class="sxs-lookup"><span data-stu-id="70eac-122">Note that <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandlers> are synchronous.</span></span> <span data-ttu-id="70eac-123">Par conséquent, le composant ne recommence à s'exécuter qu'après la fin de l'exécution d'un <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> attaché à l'événement personnalisé.</span><span class="sxs-lookup"><span data-stu-id="70eac-123">Therefore the component does not resume execution until an <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> attached to the custom event has finished executing.</span></span> <span data-ttu-id="70eac-124">Si le paramètre *AllowEventHandlers* est `true` , chaque paramètre de l’événement est automatiquement mis à la disposition de tous les <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> objets par le biais de variables créées et remplies automatiquement par le [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] Runtime.</span><span class="sxs-lookup"><span data-stu-id="70eac-124">If the *allowEventHandlers* parameter is `true`, each parameter of the event is automatically made available to any <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> objects through variables that are created and populated automatically by the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] runtime.</span></span>

### <a name="raising-a-custom-event"></a><span data-ttu-id="70eac-125">Déclenchement d'un événement personnalisé</span><span class="sxs-lookup"><span data-stu-id="70eac-125">Raising a Custom Event</span></span>
 <span data-ttu-id="70eac-126">Les composants déclenchent des événements personnalisés en appelant la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireCustomEvent%2A> et en fournissant le nom, le texte et les paramètres de l'événement.</span><span class="sxs-lookup"><span data-stu-id="70eac-126">Components raise custom events by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireCustomEvent%2A> method, and providing the name, text, and parameters of the event.</span></span> <span data-ttu-id="70eac-127">Si le paramètre *AllowEventHandlers* est `true` , tous les <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandlers> créés pour l’événement personnalisé sont exécutés par le [!INCLUDE[ssIS](../../../includes/ssis-md.md)] moteur d’exécution.</span><span class="sxs-lookup"><span data-stu-id="70eac-127">If the *allowEventHandlers* parameter is `true`, any <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandlers> that are created for the custom event are executed by the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] run-time engine.</span></span>

### <a name="custom-event-sample"></a><span data-ttu-id="70eac-128">Exemple d'événement personnalisé</span><span class="sxs-lookup"><span data-stu-id="70eac-128">Custom Event Sample</span></span>
 <span data-ttu-id="70eac-129">L'exemple de code suivant présente un composant qui définit un événement personnalisé pendant l'exécution de la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.RegisterEvents%2A>, puis qui déclenche l'événement au moment de l'exécution en appelant la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireCustomEvent%2A>.</span><span class="sxs-lookup"><span data-stu-id="70eac-129">The following code example shows a component that defines a custom event during the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.RegisterEvents%2A> method, and then raises the event at run time by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireCustomEvent%2A> method.</span></span>

```csharp
public override void RegisterEvents()
{
    string [] parameterNames = new string[2]{"RowCount", "StartTime"};
    ushort [] parameterTypes = new ushort[2]{ DtsConvert.VarTypeFromTypeCode(TypeCode.Int32), DtsConvert.VarTypeFromTypeCode(TypeCode.DateTime)};
    string [] parameterDescriptions = new string[2]{"The number of rows to sort.", "The start time of the Sort operation."};
    EventInfos.Add("StartingSort","Fires when the component begins sorting the rows.",false,ref parameterNames, ref parameterTypes, ref parameterDescriptions);
}
public override void ProcessInput(int inputID, PipelineBuffer buffer)
{
    while (buffer.NextRow())
    {
       // Process buffer rows.
    }

    IDTSEventInfo100 eventInfo = EventInfos["StartingSort"];
    object []arguments = new object[2]{buffer.RowCount, DateTime.Now };
    ComponentMetaData.FireCustomEvent("StartingSort", "Beginning sort operation.", ref arguments, ComponentMetaData.Name, ref FireSortEventAgain);
}
```

```vb
Public  Overrides Sub RegisterEvents() 
  Dim parameterNames As String() = New String(2) {"RowCount", "StartTime"} 
  Dim parameterTypes As System.UInt16() = New System.UInt16(2) {DtsConvert.VarTypeFromTypeCode(TypeCode.Int32), DtsConvert.VarTypeFromTypeCode(TypeCode.DateTime)} 
  Dim parameterDescriptions As String() = New String(2) {"The number of rows to sort.", "The start time of the Sort operation."} 
  EventInfos.Add("StartingSort", "Fires when the component begins sorting the rows.", False, parameterNames, parameterTypes, parameterDescriptions) 
End Sub 

Public  Overrides Sub ProcessInput(ByVal inputID As Integer, ByVal buffer As PipelineBuffer) 
  While buffer.NextRow 
  End While 
  Dim eventInfo As IDTSEventInfo100 = EventInfos("StartingSort") 
  Dim arguments As Object() = New Object(2) {buffer.RowCount, DateTime.Now} 
  ComponentMetaData.FireCustomEvent("StartingSort", _
    "Beginning sort operation.", arguments, _
    ComponentMetaData.Name, FireSortEventAgain) 
End Sub
```

<span data-ttu-id="70eac-130">![Icône de Integration Services (petite)](../../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="70eac-130">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="70eac-131">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="70eac-131">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="70eac-132">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="70eac-132">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="70eac-133">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="70eac-133">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="70eac-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="70eac-134">See Also</span></span>
 <span data-ttu-id="70eac-135">[Integration Services &#40;des gestionnaires d’événements de&#41; SSIS](../../integration-services-ssis-event-handlers.md) [Ajouter un gestionnaire d’événements à un package](../../add-an-event-handler-to-a-package.md)</span><span class="sxs-lookup"><span data-stu-id="70eac-135">[Integration Services &#40;SSIS&#41; Event Handlers](../../integration-services-ssis-event-handlers.md) [Add an Event Handler to a Package](../../add-an-event-handler-to-a-package.md)</span></span>


