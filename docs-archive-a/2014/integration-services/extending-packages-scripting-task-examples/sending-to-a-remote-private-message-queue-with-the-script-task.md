---
title: Envoi vers une file d’attente de messages privée distante à l’aide de la tâche de script | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script task [Integration Services], remote private message queues
- Message Queue task [Integration Services]
- Script task [Integration Services], examples
ms.assetid: 636314fd-d099-45cd-8bb4-f730d0a06739
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 308815293dfc41f0a0ac60c21ce7f561a5e7f660
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701292"
---
# <a name="sending-to-a-remote-private-message-queue-with-the-script-task"></a><span data-ttu-id="eafed-102">Envoi vers une file d'attente de messages privée distante à l'aide de la tâche de script</span><span class="sxs-lookup"><span data-stu-id="eafed-102">Sending to a Remote Private Message Queue with the Script Task</span></span>
  <span data-ttu-id="eafed-103">Message Queuing (également appelé MSMQ) permet aux développeurs de communiquer de façon simple, rapide et fiable avec des programmes d'application par l'envoi et la réception de messages.</span><span class="sxs-lookup"><span data-stu-id="eafed-103">Message Queuing (also known as MSMQ) makes it easy for developers to communicate with application programs quickly and reliably by sending and receiving messages.</span></span> <span data-ttu-id="eafed-104">Une file d'attente de messages peut se trouver sur l'ordinateur local ou un ordinateur distant et être publique ou privée.</span><span class="sxs-lookup"><span data-stu-id="eafed-104">A message queue may be located on the local computer or a remote computer, and may be public or private.</span></span> <span data-ttu-id="eafed-105">Dans [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], le gestionnaire de connexions MSMQ et la tâche MSMQ ne prennent pas en charge l'envoi vers une file d'attente privée située sur un ordinateur distant.</span><span class="sxs-lookup"><span data-stu-id="eafed-105">In [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], the MSMQ connection manager and Message Queue task do not support sending to a private queue on a remote computer.</span></span> <span data-ttu-id="eafed-106">Toutefois, la tâche de script permet d'envoyer facilement un message à une file d'attente privée distante.</span><span class="sxs-lookup"><span data-stu-id="eafed-106">However, by using the Script task, it is easy to send a message to a remote private queue.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="eafed-107">Si vous souhaitez créer une tâche plus facilement réutilisable sur plusieurs packages, envisagez d'utiliser le code indiqué dans l'exemple de tâche de script comme point de départ d'une tâche personnalisée.</span><span class="sxs-lookup"><span data-stu-id="eafed-107">If you want to create a task that you can more easily reuse across multiple packages, consider using the code in this Script task sample as the starting point for a custom task.</span></span> <span data-ttu-id="eafed-108">Pour plus d’informations, consultez [Développement d’une tâche personnalisée](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="eafed-108">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>  
  
## <a name="description"></a><span data-ttu-id="eafed-109">Description</span><span class="sxs-lookup"><span data-stu-id="eafed-109">Description</span></span>  
 <span data-ttu-id="eafed-110">L’exemple suivant utilise un gestionnaire de connexions MSMQ existant, avec des objets et des méthodes de l’espace de noms System.Messaging, pour envoyer le texte contenu dans une variable de package à une file d’attente de messages privée distante.</span><span class="sxs-lookup"><span data-stu-id="eafed-110">The following example uses an existing MSMQ connection manager, together with objects and methods from the System.Messaging namespace, to send the text contained in a package variable to a remote private message queue.</span></span> <span data-ttu-id="eafed-111">L’appel à la méthode M :Microsoft.SqlServer.Dts.ManagedConnections.MSMQConn.AcquireConnection (System. Object) du gestionnaire de connexions MSMQ retourne un objet **MessageQueue** dont `Send` la méthode effectue cette tâche.</span><span class="sxs-lookup"><span data-stu-id="eafed-111">The call to the M:Microsoft.SqlServer.Dts.ManagedConnections.MSMQConn.AcquireConnection(System.Object) method of the MSMQ connection manager returns a **MessageQueue** object whose `Send` method accomplishes this task.</span></span>  
  
#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="eafed-112">Pour configurer cet exemple de tâche de script</span><span class="sxs-lookup"><span data-stu-id="eafed-112">To configure this Script Task example</span></span>  
  
1.  <span data-ttu-id="eafed-113">Créez un gestionnaire de connexions MSMQ avec le nom par défaut.</span><span class="sxs-lookup"><span data-stu-id="eafed-113">Create an MSMQ connection manager with the default name.</span></span> <span data-ttu-id="eafed-114">Définissez le chemin d'accès d'une file d'attente privée distante valide, dans le format suivant :</span><span class="sxs-lookup"><span data-stu-id="eafed-114">Set the path of a valid remote private queue, in the following format:</span></span>  
  
    ```  
    FORMATNAME:DIRECT=OS:<computername>\private$\<queuename>  
    ```  
  
2.  <span data-ttu-id="eafed-115">Créez une [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] variable nommée **MessageText** de type `String` pour passer le texte du message dans le script.</span><span class="sxs-lookup"><span data-stu-id="eafed-115">Create an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] variable named **MessageText** of type `String` to pass the message text into the script.</span></span> <span data-ttu-id="eafed-116">Entrez un message par défaut en tant que valeur de la variable.</span><span class="sxs-lookup"><span data-stu-id="eafed-116">Enter a default message as the value of the variable.</span></span>  
  
3.  <span data-ttu-id="eafed-117">Ajoutez une tâche de script à l'aire de conception et modifiez-la.</span><span class="sxs-lookup"><span data-stu-id="eafed-117">Add a Script Task to the design surface and edit it.</span></span> <span data-ttu-id="eafed-118">Sous l’onglet **Script** de l’**Éditeur de tâche de script**, ajoutez la variable `MessageText` à la propriété **ReadOnlyVariables** pour rendre la variable disponible dans le script.</span><span class="sxs-lookup"><span data-stu-id="eafed-118">On the **Script** tab of the **Script Task Editor**, add the `MessageText` variable to the **ReadOnlyVariables** property to make the variable available inside the script.</span></span>  
  
4.  <span data-ttu-id="eafed-119">Cliquez sur **Modifier le script** pour ouvrir l’éditeur de script [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span><span class="sxs-lookup"><span data-stu-id="eafed-119">Click **Edit Script** to open the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA) script editor.</span></span>  
  
5.  <span data-ttu-id="eafed-120">Dans le projet de script, ajoutez une référence à l'espace de noms `System.Messaging`.</span><span class="sxs-lookup"><span data-stu-id="eafed-120">Add a reference in the script project to the `System.Messaging` namespace.</span></span>  
  
6.  <span data-ttu-id="eafed-121">Remplacez le contenu de la fenêtre de script par le code dans la section suivante.</span><span class="sxs-lookup"><span data-stu-id="eafed-121">Replace the contents of the script window with the code in the following section.</span></span>  
  
## <a name="code"></a><span data-ttu-id="eafed-122">Code</span><span class="sxs-lookup"><span data-stu-id="eafed-122">Code</span></span>  
  
```vb  
Imports System  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports System.Messaging  
  
Public Class ScriptMain  
  
    Public Sub Main()  
  
        Dim remotePrivateQueue As MessageQueue  
        Dim messageText As String  
  
        remotePrivateQueue = _  
            DirectCast(Dts.Connections("Message Queue Connection Manager").AcquireConnection(Dts.Transaction), _  
            MessageQueue)  
        messageText = DirectCast(Dts.Variables("MessageText").Value, String)  
        remotePrivateQueue.Send(messageText)  
  
        Dts.TaskResult = ScriptResults.Success  
  
    End Sub  
  
End Class  
```  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
using System.Messaging;  
  
public class ScriptMain  
{  
  
    public void Main()  
        {  
  
            MessageQueue remotePrivateQueue = new MessageQueue();  
            string messageText;  
  
            remotePrivateQueue = (MessageQueue)(Dts.Connections["Message Queue Connection Manager"].AcquireConnection(Dts.Transaction) as MessageQueue);  
            messageText = (string)(Dts.Variables["MessageText"].Value);  
            remotePrivateQueue.Send(messageText);  
  
            Dts.TaskResult = (int)ScriptResults.Success;  
  
        }  
  
}  
```  
  
<span data-ttu-id="eafed-123">![Icône de Integration Services (petite)](../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="eafed-123">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="eafed-124">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="eafed-124">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="eafed-125">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="eafed-125">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="eafed-126">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="eafed-126">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eafed-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="eafed-127">See Also</span></span>  
 [<span data-ttu-id="eafed-128">Tâche MSMQ</span><span class="sxs-lookup"><span data-stu-id="eafed-128">Message Queue Task</span></span>](../control-flow/message-queue-task.md)  
  
  
