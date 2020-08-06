---
title: Déclenchement d’événements dans la tâche de script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- events [Integration Services], scripts
- warnings [Integration Services]
- SSIS events, scripts
- errors [Integration Services], events
- SSIS Script task, events
- Events property
- Script task [Integration Services], events
ms.assetid: 21ea07d1-e267-4fb1-a6cc-82c95a39beae
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e20a276b91e434b6915cfb218eba17c07acd6544
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700031"
---
# <a name="raising-events-in-the-script-task"></a><span data-ttu-id="02522-102">Déclenchement d'événements dans la tâche de script</span><span class="sxs-lookup"><span data-stu-id="02522-102">Raising Events in the Script Task</span></span>
  <span data-ttu-id="02522-103">Les événements offrent un moyen de signaler des erreurs, des avertissements et d'autres informations, telles que la progression ou l'état d'une tâche, au package conteneur.</span><span class="sxs-lookup"><span data-stu-id="02522-103">Events provide a way to report errors, warnings, and other information, such as task progress or status, to the containing package.</span></span> <span data-ttu-id="02522-104">Le package fournit des gestionnaires d'événements pour gérer les notifications d'événements.</span><span class="sxs-lookup"><span data-stu-id="02522-104">The package provides event handlers for managing event notifications.</span></span> <span data-ttu-id="02522-105">La tâche de script peut déclencher des événements en appelant des méthodes sur la propriété <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Events%2A> de l'objet `Dts`.</span><span class="sxs-lookup"><span data-stu-id="02522-105">The Script task can raise events by calling methods on the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Events%2A> property of the `Dts` object.</span></span> <span data-ttu-id="02522-106">Pour plus d’informations sur la manière dont les packages [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] gèrent les événements, consultez [Gestionnaires d’événements Integration Services &#40;SSIS&#41;](../../integration-services-ssis-event-handlers.md).</span><span class="sxs-lookup"><span data-stu-id="02522-106">For more information about how [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] packages handle events, see [Integration Services &#40;SSIS&#41; Event Handlers](../../integration-services-ssis-event-handlers.md).</span></span>  
  
 <span data-ttu-id="02522-107">Les événements peuvent être journalisés dans tout module fournisseur d'informations activé dans le package.</span><span class="sxs-lookup"><span data-stu-id="02522-107">Events can be logged to any log provider that is enabled in the package.</span></span> <span data-ttu-id="02522-108">Les modules fournisseurs d'informations stockent des informations à propos des événements dans une banque de données.</span><span class="sxs-lookup"><span data-stu-id="02522-108">Log providers store information about events in a data store.</span></span> <span data-ttu-id="02522-109">La tâche de script peut également utiliser la méthode <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Log%2A> pour journaliser des informations dans un module fournisseur d'informations sans déclencher d'événement.</span><span class="sxs-lookup"><span data-stu-id="02522-109">The Script task can also use the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Log%2A> method to log information to a log provider without raising an event.</span></span> <span data-ttu-id="02522-110">Pour plus d’informations sur la manière d’utiliser la méthode <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Log%2A>, consultez [Journalisation dans la tâche de script](logging-in-the-script-task.md).</span><span class="sxs-lookup"><span data-stu-id="02522-110">For more information about how to use the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Log%2A> method, see [Logging in the Script Task](logging-in-the-script-task.md).</span></span>  
  
 <span data-ttu-id="02522-111">Pour déclencher un événement, la tâche de script appelle l'une des méthodes exposées par la propriété <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Events%2A>.</span><span class="sxs-lookup"><span data-stu-id="02522-111">To raise an event, the Script task calls one of the methods exposed by the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Events%2A> property.</span></span> <span data-ttu-id="02522-112">Le tableau suivant répertorie les méthodes exposées par la propriété <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Events%2A>.</span><span class="sxs-lookup"><span data-stu-id="02522-112">The following table lists the methods exposed by the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Events%2A> property.</span></span>  
  
|<span data-ttu-id="02522-113">Événement</span><span class="sxs-lookup"><span data-stu-id="02522-113">Event</span></span>|<span data-ttu-id="02522-114">Description</span><span class="sxs-lookup"><span data-stu-id="02522-114">Description</span></span>|  
|-----------|-----------------|  
|<xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireCustomEvent%2A>|<span data-ttu-id="02522-115">Déclenche un événement personnalisé défini par l'utilisateur dans le package.</span><span class="sxs-lookup"><span data-stu-id="02522-115">Raises a user-defined custom event in the package.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireError%2A>|<span data-ttu-id="02522-116">Informe le package d'une condition d'erreur.</span><span class="sxs-lookup"><span data-stu-id="02522-116">Informs the package of an error condition.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireInformation%2A>|<span data-ttu-id="02522-117">Fournit des informations à l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="02522-117">Provides information to the user.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireProgress%2A>|<span data-ttu-id="02522-118">Informe le package de la progression de la tâche.</span><span class="sxs-lookup"><span data-stu-id="02522-118">Informs the package of the progress of the task.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireQueryCancel%2A>|<span data-ttu-id="02522-119">Retourne une valeur qui indique si le package nécessite l'arrêt prématuré de la tâche.</span><span class="sxs-lookup"><span data-stu-id="02522-119">Returns a value that indicates whether the package needs the task to shut down prematurely.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireWarning%2A>|<span data-ttu-id="02522-120">Informe le package que la tâche est dans un état qui garantit la notification de l'utilisateur, mais qui n'est pas une condition d'erreur.</span><span class="sxs-lookup"><span data-stu-id="02522-120">Informs the package that the task is in a state that warrants user notification, but is not an error condition.</span></span>|  
  
## <a name="events-example"></a><span data-ttu-id="02522-121">Exemples d'événements</span><span class="sxs-lookup"><span data-stu-id="02522-121">Events Example</span></span>  
 <span data-ttu-id="02522-122">L'exemple suivant montre comment déclencher des événements à partir de la tâche de script.</span><span class="sxs-lookup"><span data-stu-id="02522-122">The following example demonstrates how to raise events from within the Script task.</span></span> <span data-ttu-id="02522-123">L'exemple utilise une fonction API Windows native pour déterminer si une connexion Internet est disponible.</span><span class="sxs-lookup"><span data-stu-id="02522-123">The example uses a native Windows API function to determine whether an Internet connection is available.</span></span> <span data-ttu-id="02522-124">Si aucune connexion n'est disponible, il génère une erreur.</span><span class="sxs-lookup"><span data-stu-id="02522-124">If no connection is available, it raises an error.</span></span> <span data-ttu-id="02522-125">Si une connexion par modem potentiellement volatile est en cours d'utilisation, l'exemple déclenche un avertissement.</span><span class="sxs-lookup"><span data-stu-id="02522-125">If a potentially volatile modem connection is in use, the example raises a warning.</span></span> <span data-ttu-id="02522-126">Sinon, il retourne un message d'information indiquant qu'une connexion Internet a été détectée.</span><span class="sxs-lookup"><span data-stu-id="02522-126">Otherwise, it returns an informational message that an Internet connection has been detected.</span></span>  
  
```vb  
Private Declare Function InternetGetConnectedState Lib "wininet" _  
    (ByRef dwFlags As Long, ByVal dwReserved As Long) As Long  
  
Private Enum ConnectedStates  
    LAN = &H2  
    Modem = &H1  
    Proxy = &H4  
    Offline = &H20  
    Configured = &H40  
    RasInstalled = &H10  
End Enum  
  
Public Sub Main()  
  
    Dim dwFlags As Long  
    Dim connectedState As Long  
    Dim fireAgain as Boolean  
  
    connectedState = InternetGetConnectedState(dwFlags, 0)  
  
    If connectedState <> 0 Then  
        If (dwFlags And ConnectedStates.Modem) = ConnectedStates.Modem Then  
            Dts.Events.FireWarning(0, "Script Task Example", _  
                "Volatile Internet connection detected.", String.Empty, 0)  
        Else  
            Dts.Events.FireInformation(0, "Script Task Example", _  
                "Internet connection detected.", String.Empty, 0, fireAgain)  
        End If  
    Else  
        ' If not connected to the Internet, raise an error.  
        Dts.Events.FireError(0, "Script Task Example", _  
            "Internet connection not available.", String.Empty, 0)  
    End If  
  
    Dts.TaskResult = ScriptResults.Success  
  
End Sub  
```  
  
```csharp  
using System;  
using System.Data;  
using Microsoft.SqlServer.Dts.Runtime;  
using System.Windows.Forms;  
using System.Runtime.InteropServices;  
  
public class ScriptMain  
{  
  
[DllImport("wininet")]  
        private extern static long InternetGetConnectedState(ref long dwFlags, long dwReserved);  
  
        private enum ConnectedStates  
        {  
            LAN = 0x2,  
            Modem = 0x1,  
            Proxy = 0x4,  
            Offline = 0x20,  
            Configured = 0x40,  
            RasInstalled = 0x10  
        };  
  
        public void Main()  
        {  
            //  
            long dwFlags = 0;  
            long connectedState;  
            bool fireAgain = true;  
            int state;  
  
            connectedState = InternetGetConnectedState(ref dwFlags, 0);  
            state = (int)ConnectedStates.Modem;  
            if (connectedState != 0)  
            {  
                if ((dwFlags & state) == state)  
                {  
                    Dts.Events.FireWarning(0, "Script Task Example", "Volatile Internet connection detected.", String.Empty, 0);  
                }  
                else  
                {  
                    Dts.Events.FireInformation(0, "Script Task Example", "Internet connection detected.", String.Empty, 0, ref fireAgain);  
                }  
            }  
            else  
            {  
                // If not connected to the Internet, raise an error.  
                Dts.Events.FireError(0, "Script Task Example", "Internet connection not available.", String.Empty, 0);  
            }  
  
            Dts.TaskResult = (int)ScriptResults.Success;  
  
        }  
  
```  
  
<span data-ttu-id="02522-127">![Icône de Integration Services (petite)](../../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="02522-127">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="02522-128">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="02522-128">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="02522-129">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="02522-129">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="02522-130">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="02522-130">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02522-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="02522-131">See Also</span></span>  
 <span data-ttu-id="02522-132">[Gestionnaires d’événements Integration Services &#40;SSIS&#41](../../integration-services-ssis-event-handlers.md) </span><span class="sxs-lookup"><span data-stu-id="02522-132">[Integration Services &#40;SSIS&#41; Event Handlers](../../integration-services-ssis-event-handlers.md) </span></span>  
 [<span data-ttu-id="02522-133">Ajouter un gestionnaire d’événements à un package</span><span class="sxs-lookup"><span data-stu-id="02522-133">Add an Event Handler to a Package</span></span>](../../add-an-event-handler-to-a-package.md)  
  
  
