---
title: Surveillance des compteurs de performances à l’aide de la tâche de script | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- performance counters [Integration Services]
- SSIS Script task, performance counters
- custom performance counters [Integration Services]
- Script task [Integration Services], examples
- Script task [Integration Services], performance counters
- counters [Integration Services]
ms.assetid: 86609bf1-cae6-435e-a58d-41bdfc521e94
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 143e11ff966eb11961aa15073a503522c4b9c86b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705291"
---
# <a name="monitoring-performance-counters-with-the-script-task"></a><span data-ttu-id="809bc-102">Surveillance des compteurs de performances à l'aide de la tâche de script</span><span class="sxs-lookup"><span data-stu-id="809bc-102">Monitoring Performance Counters with the Script Task</span></span>
  <span data-ttu-id="809bc-103">Les administrateurs peuvent avoir besoin de surveiller les performances des packages [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] qui effectuent des transformations complexes sur de grandes quantités de données.</span><span class="sxs-lookup"><span data-stu-id="809bc-103">Administrators may need to monitor the performance of [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages that perform complex transformations on large amounts of data.</span></span> <span data-ttu-id="809bc-104">L’espace de noms **System.Diagnostics** de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] fournit des classes permettant d’utiliser des compteurs de performances existants et de créer vos propres compteurs de performances.</span><span class="sxs-lookup"><span data-stu-id="809bc-104">The **System.Diagnostics** namespace of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] provides classes for using existing performance counters and for creating your own performance counters.</span></span>  
  
 <span data-ttu-id="809bc-105">Les compteurs de performances stockent des informations sur les performances des applications que vous pouvez utiliser pour analyser les performances des logiciels dans le temps.</span><span class="sxs-lookup"><span data-stu-id="809bc-105">Performance counters store application performance information that you can use to analyze the performance of software over time.</span></span> <span data-ttu-id="809bc-106">Les compteurs de performances peuvent être surveillés localement ou à distance en utilisant l’outil **Analyseur de performances**.</span><span class="sxs-lookup"><span data-stu-id="809bc-106">Performance counters can be monitored locally or remotely by using the **Performance Monitor** tool.</span></span> <span data-ttu-id="809bc-107">Vous pouvez stocker les valeurs des compteurs de performances dans des variables à des fins de branchement ultérieur du flux de contrôle dans le package.</span><span class="sxs-lookup"><span data-stu-id="809bc-107">You can store the values of performance counters in variables for later control flow branching in the package.</span></span>  
  
 <span data-ttu-id="809bc-108">Comme alternative à l'utilisation des compteurs de performances, vous pouvez déclencher l'événement <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireProgress%2A> via la propriété <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Events%2A> de l'objet `Dts`.</span><span class="sxs-lookup"><span data-stu-id="809bc-108">As an alternative to using performance counters, you can raise the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireProgress%2A> event through the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Events%2A> property of the `Dts` object.</span></span> <span data-ttu-id="809bc-109">L'événement <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireProgress%2A> indique à la fois les stades intermédiaires de l'avancement et le pourcentage d'avancement à l'exécution [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="809bc-109">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireProgress%2A> event returns both incremental progress and percentage complete information to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] runtime.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="809bc-110">Si vous souhaitez créer une tâche plus facilement réutilisable sur plusieurs packages, envisagez d'utiliser le code indiqué dans l'exemple de tâche de script comme point de départ d'une tâche personnalisée.</span><span class="sxs-lookup"><span data-stu-id="809bc-110">If you want to create a task that you can more easily reuse across multiple packages, consider using the code in this Script task sample as the starting point for a custom task.</span></span> <span data-ttu-id="809bc-111">Pour plus d’informations, consultez [Développement d’une tâche personnalisée](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="809bc-111">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>  
  
## <a name="description"></a><span data-ttu-id="809bc-112">Description</span><span class="sxs-lookup"><span data-stu-id="809bc-112">Description</span></span>  
 <span data-ttu-id="809bc-113">L'exemple suivant crée un compteur de performance personnalisé et incrémente le compteur.</span><span class="sxs-lookup"><span data-stu-id="809bc-113">The following example creates a custom performance counter and increments the counter.</span></span> <span data-ttu-id="809bc-114">Tout d'abord, l'exemple détermine si le compteur de performance existe déjà.</span><span class="sxs-lookup"><span data-stu-id="809bc-114">First, the example determines whether the performance counter already exists.</span></span> <span data-ttu-id="809bc-115">Si le compteur de performance n'a pas été créé, le script appelle la méthode `Create` de l'objet `PerformanceCounterCategory` pour le créer.</span><span class="sxs-lookup"><span data-stu-id="809bc-115">If the performance counter has not been created, the script calls the `Create` method of the `PerformanceCounterCategory` object to create it.</span></span> <span data-ttu-id="809bc-116">Après avoir créé le compteur de performance, le script incrémente le compteur.</span><span class="sxs-lookup"><span data-stu-id="809bc-116">After the performance counter has been created, the script increments the counter.</span></span> <span data-ttu-id="809bc-117">Enfin, l'exemple suit la méthode conseillée qui consiste à appeler la méthode `Close` sur le compteur de performance lorsqu'il n'est plus nécessaire.</span><span class="sxs-lookup"><span data-stu-id="809bc-117">Finally, the example follows the best practice of calling the `Close` method on the performance counter when it is no longer needed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="809bc-118">La création d'une nouvelle catégorie de compteur de performance et d'un compteur de performance requiert des droits d'administration.</span><span class="sxs-lookup"><span data-stu-id="809bc-118">Creating a new performance counter category and performance counter requires administrative rights.</span></span> <span data-ttu-id="809bc-119">En outre, la nouvelle catégorie et le compteur subsistent sur l'ordinateur après leur création.</span><span class="sxs-lookup"><span data-stu-id="809bc-119">Also, the new category and counter persist on the computer after creation.</span></span>  
  
#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="809bc-120">Pour configurer cet exemple de tâche de script</span><span class="sxs-lookup"><span data-stu-id="809bc-120">To configure this Script Task example</span></span>  
  
-   <span data-ttu-id="809bc-121">Utilisez une `Imports` instruction dans votre code pour importer l’espace de noms **System. Diagnostics** .</span><span class="sxs-lookup"><span data-stu-id="809bc-121">Use an `Imports` statement in your code to import the **System.Diagnostics** namespace.</span></span>  
  
### <a name="example-code"></a><span data-ttu-id="809bc-122">Exemple de code</span><span class="sxs-lookup"><span data-stu-id="809bc-122">Example Code</span></span>  
  
```vb  
Public Sub Main()  
  
    Dim myCounter As PerformanceCounter  
  
    Try  
        'Create the performance counter if it does not already exist.  
        If Not _  
        PerformanceCounterCategory.Exists("TaskExample") Then  
            PerformanceCounterCategory.Create("TaskExample", _  
                "Task Performance Counter Example", "Iterations", _  
                "Number of times this task has been called.")  
        End If  
  
        'Initialize the performance counter.  
        myCounter = New PerformanceCounter("TaskExample", _  
            "Iterations", String.Empty, False)  
  
        'Increment the performance counter.  
        myCounter.Increment()  
  
         myCounter.Close()  
        Dts.TaskResult = ScriptResults.Success  
    Catch ex As Exception  
        Dts.Events.FireError(0, _  
            "Task Performance Counter Example", _  
            ex.Message & ControlChars.CrLf & ex.StackTrace, _  
            String.Empty, 0)  
        Dts.TaskResult = ScriptResults.Failure  
    End Try  
  
End Sub  
```  
  
```csharp  
  
public class ScriptMain  
{  
  
public void Main()  
        {  
  
            PerformanceCounter myCounter;  
  
            try  
            {  
                //Create the performance counter if it does not already exist.  
                if (!PerformanceCounterCategory.Exists("TaskExample"))  
                {  
                    PerformanceCounterCategory.Create("TaskExample", "Task Performance Counter Example", "Iterations", "Number of times this task has been called.");  
                }  
  
                //Initialize the performance counter.  
                myCounter = new PerformanceCounter("TaskExample", "Iterations", String.Empty, false);  
  
                //Increment the performance counter.  
                myCounter.Increment();  
  
                myCounter.Close();  
                Dts.TaskResult = (int)ScriptResults.Success;  
            }  
            catch (Exception ex)  
            {  
                Dts.Events.FireError(0, "Task Performance Counter Example", ex.Message + "\r" + ex.StackTrace, String.Empty, 0);  
                Dts.TaskResult = (int)ScriptResults.Failure;  
            }  
  
            Dts.TaskResult = (int)ScriptResults.Success;  
        }  
  
```  
  
<span data-ttu-id="809bc-123">![Icône de Integration Services (petite)](../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="809bc-123">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="809bc-124">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="809bc-124">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="809bc-125">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="809bc-125">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="809bc-126">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="809bc-126">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
