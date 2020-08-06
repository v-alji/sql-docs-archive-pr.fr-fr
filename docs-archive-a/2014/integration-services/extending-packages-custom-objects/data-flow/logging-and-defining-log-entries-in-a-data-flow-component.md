---
title: Enregistrement et définition d’entrées de journal dans un composant de flux de données | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- logs [Integration Services], custom
- custom log entries [Integration Services]
- custom data flow components [Integration Services], logging
- data flow components [Integration Services], logging
ms.assetid: 2190dba9-59b5-480b-b8e9-21d5a54c5917
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 14dfec71679bbe455ae8be5face98b776a80b9e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697000"
---
# <a name="logging-and-defining-log-entries-in-a-data-flow-component"></a><span data-ttu-id="c31cf-102">Enregistrement et définition d'entrées de journal dans un composant de flux de données</span><span class="sxs-lookup"><span data-stu-id="c31cf-102">Logging and Defining Log Entries in a Data Flow Component</span></span>
  <span data-ttu-id="c31cf-103">Les composants de flux de données personnalisés peuvent publier des messages dans une entrée de journal existante à l'aide de la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.PostLogMessage%2A> de l'interface <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100>.</span><span class="sxs-lookup"><span data-stu-id="c31cf-103">Custom data flow components can post messages to an existing log entry by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.PostLogMessage%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface.</span></span> <span data-ttu-id="c31cf-104">Ils peuvent également présenter des informations à l'utilisateur en utilisant la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireInformation%2A>, ou des méthodes semblables, de l'interface <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100>.</span><span class="sxs-lookup"><span data-stu-id="c31cf-104">They can also present information to the user by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireInformation%2A> method or similar methods of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface.</span></span> <span data-ttu-id="c31cf-105">Toutefois, cette procédure induit une surcharge causée par le déclenchement et la gestion d'événements supplémentaires et force l'utilisateur à passer en revue les messages d'information documentés pour rechercher ceux susceptibles de l'intéresser.</span><span class="sxs-lookup"><span data-stu-id="c31cf-105">However, this approach incurs the overhead of raising and handling additional events, and forces the user to sift through verbose informational messages for the messages that may be of interest to them.</span></span> <span data-ttu-id="c31cf-106">Vous pouvez utiliser une entrée de journal personnalisée, tel que décrit ci-dessous, pour fournir aux utilisateurs de votre composant des informations de journal personnalisées étiquetées.</span><span class="sxs-lookup"><span data-stu-id="c31cf-106">You can use a custom log entry as described below to provide distinctly labeled custom log information to users of your component.</span></span>  
  
## <a name="registering-and-using-a-custom-log-entry"></a><span data-ttu-id="c31cf-107">Inscription et utilisation d'une entrée de journal personnalisée</span><span class="sxs-lookup"><span data-stu-id="c31cf-107">Registering and Using a Custom Log Entry</span></span>  
  
### <a name="registering-a-custom-log-entry"></a><span data-ttu-id="c31cf-108">Inscription d'une entrée de journal personnalisée</span><span class="sxs-lookup"><span data-stu-id="c31cf-108">Registering a Custom Log Entry</span></span>  
 <span data-ttu-id="c31cf-109">Pour inscrire une entrée de journal personnalisée destinée à votre composant, substituez la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.RegisterLogEntries%2A> de la classe de base <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent>.</span><span class="sxs-lookup"><span data-stu-id="c31cf-109">To register a custom log entry for use by your component, override the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.RegisterLogEntries%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> base class.</span></span> <span data-ttu-id="c31cf-110">L'exemple suivant inscrit une entrée de journal personnalisée et lui fournit un nom et une description.</span><span class="sxs-lookup"><span data-stu-id="c31cf-110">The following example registers a custom log entry and provides a name and description.</span></span>  
  
```csharp  
using Microsoft.SqlServer.Dts.Runtime;  
...  
private const string MyLogEntryName = "My Custom Component Log Entry";  
private const string MyLogEntryDescription = "Log entry from My Custom Component ";  
...  
    public override void RegisterLogEntries()  
    {  
      this.LogEntryInfos.Add(MyLogEntryName,  
        MyLogEntryDescription,  
        Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_CONSISTENT);  
    }  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
...  
Private Const MyLogEntryName As String = "My Custom Component Log Entry"   
Private Const MyLogEntryDescription As String = "Log entry from My Custom Component "  
...  
Public  Overrides Sub RegisterLogEntries()   
  Me.LogEntryInfos.Add(MyLogEntryName, _  
    MyLogEntryDescription, _  
    Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_CONSISTENT)   
End Sub  
```  
  
 <span data-ttu-id="c31cf-111">L'énumération <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency> fournit au Runtime une indication quant à la fréquence de journalisation de l'événement :</span><span class="sxs-lookup"><span data-stu-id="c31cf-111">The <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency> enumeration provides a hint to the runtime about how frequently the event will be logged:</span></span>  
  
-   <span data-ttu-id="c31cf-112"><xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_OCCASIONAL> : l'événement est enregistré épisodiquement, mais pas à chaque exécution.</span><span class="sxs-lookup"><span data-stu-id="c31cf-112"><xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_OCCASIONAL>: Event is logged only sometimes, not during every execution.</span></span>  
  
-   <span data-ttu-id="c31cf-113"><xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_CONSISTENT> : l'événement est enregistré un nombre constant de fois pendant chaque exécution.</span><span class="sxs-lookup"><span data-stu-id="c31cf-113"><xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_CONSISTENT>: Event is logged a constant number of times during every execution.</span></span>  
  
-   <span data-ttu-id="c31cf-114"><xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_PROPORTIONAL> : l'événement est enregistré un nombre de fois proportionnel à la quantité de travail accompli.</span><span class="sxs-lookup"><span data-stu-id="c31cf-114"><xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_PROPORTIONAL>: Event is logged a number of times proportional to the amount of work completed.</span></span>  
  
 <span data-ttu-id="c31cf-115">L'exemple ci-dessus utilise <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_CONSISTENT> car le composant s'attend à enregistrer une entrée une fois par exécution.</span><span class="sxs-lookup"><span data-stu-id="c31cf-115">The example above uses <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_CONSISTENT> because the component expects to log an entry once per execution.</span></span>  
  
 <span data-ttu-id="c31cf-116">Après l’inscription de l’entrée de journal personnalisée et l’ajout d’une instance de votre composant personnalisé à l’aire du concepteur de flux de données, la boîte de dialogue **Enregistrement** dans le concepteur affiche une nouvelle entrée de journal appelée « Entrée de journal de mon composant personnalisé » dans la liste des entrées de journal disponibles.</span><span class="sxs-lookup"><span data-stu-id="c31cf-116">After registering the custom log entry and adding an instance of your custom component to the data flow designer surface, the **Logging** dialog box in the designer displays a new log entry with the name "My Custom Component Log Entry" in the list of available log entries.</span></span>  
  
### <a name="logging-to-a-custom-log-entry"></a><span data-ttu-id="c31cf-117">Enregistrement dans une entrée de journal personnalisée</span><span class="sxs-lookup"><span data-stu-id="c31cf-117">Logging to a Custom Log Entry</span></span>  
 <span data-ttu-id="c31cf-118">Après l'inscription de l'entrée de journal personnalisée, le composant peut désormais enregistrer des messages personnalisés.</span><span class="sxs-lookup"><span data-stu-id="c31cf-118">After registering the custom log entry, the component can now log custom messages.</span></span> <span data-ttu-id="c31cf-119">L'exemple suivant écrit une entrée de journal personnalisée pendant l'exécution de la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> qui contient le texte d'une instruction SQL utilisée par le composant.</span><span class="sxs-lookup"><span data-stu-id="c31cf-119">The example below writes a custom log entry during the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> method that contains the text of a SQL statement used by the component.</span></span>  
  
```csharp  
public override void PreExecute()  
{  
  DateTime now = DateTime.Now;  
  byte[] additionalData = null;  
  this.ComponentMetaData.PostLogMessage(MyLogEntryName,  
    this.ComponentMetaData.Name,  
    "Command Sent was: " + myCommand.CommandText,  
    now, now, 0, ref additionalData);  
}  
```  
  
```vb  
Public  Overrides Sub PreExecute()   
  Dim now As DateTime = DateTime.Now   
  Dim additionalData As Byte() = Nothing   
  Me.ComponentMetaData.PostLogMessage(MyLogEntryName, _  
    Me.ComponentMetaData.Name, _  
    "Command Sent was: " + myCommand.CommandText, _  
    now, now, 0, additionalData)   
End Sub  
```  
  
 <span data-ttu-id="c31cf-120">À présent, lorsque l’utilisateur exécute le package, après avoir sélectionné l’option « Entrée de journal de mon composant personnalisé » dans la boîte de dialogue **Enregistrement**, le journal contient une entrée clairement étiquetée « Utilisateur ::Entrée de journal de mon composant personnalisé ».</span><span class="sxs-lookup"><span data-stu-id="c31cf-120">Now when the user executes the package, after selecting the "My Custom Component Log Entry" in the **Logging** dialog box, the log will contain an entry clearly labeled as "User::My Custom Component Log Entry."</span></span> <span data-ttu-id="c31cf-121">Cette nouvelle entrée de journal contient le texte de l'instruction SQL, l'horodateur et toutes les données supplémentaires enregistrées par le développeur.</span><span class="sxs-lookup"><span data-stu-id="c31cf-121">This new log entry contains the text of the SQL statement, the timestamp, and any additional data logged by the developer.</span></span>  
  
<span data-ttu-id="c31cf-122">![Icône de Integration Services (petite)](../../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="c31cf-122">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="c31cf-123">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="c31cf-123">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="c31cf-124">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="c31cf-124">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="c31cf-125">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="c31cf-125">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c31cf-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c31cf-126">See Also</span></span>  
 [<span data-ttu-id="c31cf-127">Journalisation Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="c31cf-127">Integration Services &#40;SSIS&#41; Logging</span></span>](../../performance/integration-services-ssis-logging.md)  
  
  
