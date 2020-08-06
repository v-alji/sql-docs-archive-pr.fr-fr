---
title: Journalisation dans la tâche de script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- SQL Server Integration Services packages, logs
- SSIS packages, logs
- logs [Integration Services], scripts
- Integration Services packages, logs
- Log method
- SSIS Script task, logs
- Script task [Integration Services], logs
- packages [Integration Services], logs
ms.assetid: 2e11fc15-df18-4309-bd2d-fc58aa4b9b7a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 61f7a46088de5df2765d860bd4a43e4872a1be6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700037"
---
# <a name="logging-in-the-script-task"></a><span data-ttu-id="8d445-102">Journalisation dans la tâche de script</span><span class="sxs-lookup"><span data-stu-id="8d445-102">Logging in the Script Task</span></span>
  <span data-ttu-id="8d445-103">L’utilisation de la journalisation dans les packages [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] vous permet d’enregistrer des informations détaillées sur l’avancement, les résultats et les problèmes d’exécution en enregistrant des événements prédéfinis ou des messages définis par l’utilisateur en vue d’une analyse ultérieure.</span><span class="sxs-lookup"><span data-stu-id="8d445-103">The use of logging in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] packages lets you record detailed information about execution progress, results, and problems by recording predefined events or user-defined messages for later analysis.</span></span> <span data-ttu-id="8d445-104">La tâche de script peut utiliser la méthode <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Log%2A> de l'objet `Dts` pour enregistrer des données définies par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8d445-104">The Script task can use the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Log%2A> method of the `Dts` object to log user-defined data.</span></span> <span data-ttu-id="8d445-105">Si la journalisation est activée et que l’événement **ScriptTaskLogEntry** est sélectionné pour la journalisation sous l’onglet **Détails** de la boîte de dialogue **Configurer les journaux SSIS**, un seul appel à la méthode <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Log%2A> stocke les informations sur l’événement dans tous les modules fournisseurs d’informations configurés pour la tâche.</span><span class="sxs-lookup"><span data-stu-id="8d445-105">If logging is enabled, and the **ScriptTaskLogEntry** event is selected for logging on the **Details** tab of the **Configure SSIS Logs** dialog box, a single call to the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Log%2A> method stores the event information in all the log providers configured for the task.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8d445-106">Bien qu'il soit possible d'exécuter la journalisation directement à partir de la tâche de script, il peut être préférable d'implémenter des événements plutôt que la journalisation.</span><span class="sxs-lookup"><span data-stu-id="8d445-106">Although you can perform logging directly from your Script task, you may want to consider implementing events rather than logging.</span></span> <span data-ttu-id="8d445-107">L’utilisation d’événements vous permet non seulement d’activer la journalisation des messages d’événements, mais également de répondre à un événement à l’aide de gestionnaires d’événements par défaut ou définis par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8d445-107">When using events, not only can you enable the logging of event messages, but you can also respond to the event with default or user-defined event handlers.</span></span>  
  
 <span data-ttu-id="8d445-108">Pour plus d’informations sur la journalisation, consultez [Journalisation Integration Services &#40;SSIS&#41;](../../performance/integration-services-ssis-logging.md).</span><span class="sxs-lookup"><span data-stu-id="8d445-108">For more information about logging, see [Integration Services &#40;SSIS&#41; Logging](../../performance/integration-services-ssis-logging.md).</span></span>  
  
## <a name="logging-example"></a><span data-ttu-id="8d445-109">Exemple de journalisation</span><span class="sxs-lookup"><span data-stu-id="8d445-109">Logging Example</span></span>  
 <span data-ttu-id="8d445-110">L'exemple suivant montre la journalisation d'une valeur représentant le nombre de lignes traitées à partir de la tâche de script.</span><span class="sxs-lookup"><span data-stu-id="8d445-110">The following example demonstrates logging from the Script task by logging a value that represents the number of rows processed.</span></span>  
  
```vb  
Public Sub Main()  
  
    Dim rowsProcessed As Integer = 100  
    Dim emptyBytes(0) As Byte  
  
    Try  
        Dts.Log("Rows processed: " & rowsProcessed.ToString, _  
            0, _  
            emptyBytes)  
        Dts.TaskResult = ScriptResults.Success  
    Catch ex As Exception  
        'An error occurred.  
        Dts.Events.FireError(0, "Script Task Example", _  
            ex.Message & ControlChars.CrLf & ex.StackTrace, _  
            String.Empty, 0)  
        Dts.TaskResult = ScriptResults.Failure  
    End Try  
  
End Sub  
```  
  
```csharp  
using System;  
using System.Data;  
using Microsoft.SqlServer.Dts.Runtime;  
  
public class ScriptMain  
{  
  
    public void Main()  
        {  
            //  
            int rowsProcessed = 100;  
            byte[] emptyBytes = new byte[0];  
  
            try  
            {  
                Dts.Log("Rows processed: " + rowsProcessed.ToString(), 0, emptyBytes);  
                Dts.TaskResult = (int)ScriptResults.Success;  
            }  
            catch (Exception ex)  
            {  
                //An error occurred.  
                Dts.Events.FireError(0, "Script Task Example", ex.Message + "\r" + ex.StackTrace, String.Empty, 0);  
                Dts.TaskResult = (int)ScriptResults.Failure;  
            }  
  
        }  
```  
  
 <span data-ttu-id="8d445-111">}</span><span class="sxs-lookup"><span data-stu-id="8d445-111">}</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="8d445-112">Ressources externes</span><span class="sxs-lookup"><span data-stu-id="8d445-112">External Resources</span></span>  
  
<span data-ttu-id="8d445-113">![Icône de Integration Services (petite)](../../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="8d445-113">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="8d445-114">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="8d445-114">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="8d445-115">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="8d445-115">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="8d445-116">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="8d445-116">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d445-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8d445-117">See Also</span></span>  
 [<span data-ttu-id="8d445-118">Journalisation Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="8d445-118">Integration Services &#40;SSIS&#41; Logging</span></span>](../../performance/integration-services-ssis-logging.md)  
  
  
