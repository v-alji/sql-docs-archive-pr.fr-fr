---
title: Recherche d’imprimantes installées à l’aide de la tâche de script | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- System.Drawing.Printing namespace
- printers [Integration Services]
- SSIS Script task, printers
- locating printers
- Printing namespace
- Script task [Integration Services], examples
- finding printers [SQL Server]
- Script task [Integration Services], printers
ms.assetid: 50a55014-e2c3-4ecd-84e1-3e877c55a260
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cc4bc06879a55d4d07afca1011cc479dd7e7903a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705315"
---
# <a name="finding-installed-printers-with-the-script-task"></a><span data-ttu-id="d35a1-102">Recherche d'imprimantes installées à l'aide de la tâche de script</span><span class="sxs-lookup"><span data-stu-id="d35a1-102">Finding Installed Printers with the Script Task</span></span>
  <span data-ttu-id="d35a1-103">La destination finale des données transformées par les packages [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] est souvent un rapport imprimé.</span><span class="sxs-lookup"><span data-stu-id="d35a1-103">The data that is transformed by [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages often has a printed report as its final destination.</span></span> <span data-ttu-id="d35a1-104">L' `System.Drawing.Printing` espace de noms dans le [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] fournit des classes pour l’utilisation des imprimantes.</span><span class="sxs-lookup"><span data-stu-id="d35a1-104">The `System.Drawing.Printing` namespace in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] provides classes for working with printers.</span></span>

> [!NOTE]
>  <span data-ttu-id="d35a1-105">Si vous souhaitez créer une tâche plus facilement réutilisable sur plusieurs packages, envisagez d'utiliser le code indiqué dans l'exemple de tâche de script comme point de départ d'une tâche personnalisée.</span><span class="sxs-lookup"><span data-stu-id="d35a1-105">If you want to create a task that you can more easily reuse across multiple packages, consider using the code in this Script task sample as the starting point for a custom task.</span></span> <span data-ttu-id="d35a1-106">Pour plus d’informations, consultez [Développement d’une tâche personnalisée](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="d35a1-106">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>

## <a name="description"></a><span data-ttu-id="d35a1-107">Description</span><span class="sxs-lookup"><span data-stu-id="d35a1-107">Description</span></span>
 <span data-ttu-id="d35a1-108">L'exemple suivant recherche les imprimantes installées sur le serveur qui prennent en charge le format de papier standard (utilisé en France).</span><span class="sxs-lookup"><span data-stu-id="d35a1-108">The following example locates printers installed on the server that support legal size paper (as used in the United States).</span></span> <span data-ttu-id="d35a1-109">Le code permettant de vérifier les formats de papier pris en charge est encapsulé dans une fonction privée.</span><span class="sxs-lookup"><span data-stu-id="d35a1-109">The code to check supported paper sizes is encapsulated in a private function.</span></span> <span data-ttu-id="d35a1-110">Pour vous permettre de suivre la progression du script pendant qu'il vérifie les paramètres de chaque imprimante, le script utilise la méthode <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Log%2A> qui déclenche un message d'information pour les imprimantes qui utilisent le format de papier standard et un avertissement pour les imprimantes qui ne l'utilisent pas.</span><span class="sxs-lookup"><span data-stu-id="d35a1-110">To enable you to track the progress of the script as it checks the settings for each printer, the script uses the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Log%2A> method to raise an informational message for printers with legal size paper, and to raise a warning for printers without legal size paper.</span></span> <span data-ttu-id="d35a1-111">Ces messages apparaissent dans la fenêtre **Sortie** de l’environnement de développement intégré [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA) lorsque vous exécutez le package dans le concepteur.</span><span class="sxs-lookup"><span data-stu-id="d35a1-111">These messages appear in the **Output** window of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA) IDE when you run the package in the designer.</span></span>

#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="d35a1-112">Pour configurer cet exemple de tâche de script</span><span class="sxs-lookup"><span data-stu-id="d35a1-112">To configure this Script Task example</span></span>

1.  <span data-ttu-id="d35a1-113">Créez la variable nommée `PrinterList` avec le type `Object`.</span><span class="sxs-lookup"><span data-stu-id="d35a1-113">Create the variable named `PrinterList` with type `Object`.</span></span>

2.  <span data-ttu-id="d35a1-114">Dans la page **Script** de l’**Éditeur de tâche de script**, ajoutez cette variable à la propriété ReadWriteVariables.</span><span class="sxs-lookup"><span data-stu-id="d35a1-114">On the **Script** page of the **Script Task Editor**, add this variable to the ReadWriteVariables property.</span></span>

3.  <span data-ttu-id="d35a1-115">Dans le projet de script, ajoutez une référence à l’espace de noms **System.Xml**.</span><span class="sxs-lookup"><span data-stu-id="d35a1-115">In the script project, add a reference to the **System.Drawing** namespace.</span></span>

4.  <span data-ttu-id="d35a1-116">Dans votre code, utilisez des `Imports` instructions pour importer les **System. Collections** et les `System.Drawing.Printing` espaces de noms.</span><span class="sxs-lookup"><span data-stu-id="d35a1-116">In your code, use `Imports` statements to import the **System.Collections** and the `System.Drawing.Printing` namespaces.</span></span>

### <a name="code"></a><span data-ttu-id="d35a1-117">Code</span><span class="sxs-lookup"><span data-stu-id="d35a1-117">Code</span></span>

```vb
Public Sub Main()

    Dim printerName As String
    Dim currentPrinter As New PrinterSettings
    Dim size As PaperSize

    Dim printerList As New ArrayList
    For Each printerName In PrinterSettings.InstalledPrinters
        currentPrinter.PrinterName = printerName
        If PrinterHasLegalPaper(currentPrinter) Then
            printerList.Add(printerName)
            Dts.Events.FireInformation(0, "Example", _
                "Printer " & printerName & " has legal paper.", _
                String.Empty, 0, False)
        Else
            Dts.Events.FireWarning(0, "Example", _
                "Printer " & printerName & " DOES NOT have legal paper.", _
                String.Empty, 0)
        End If
    Next

    Dts.Variables("PrinterList").Value = printerList

    Dts.TaskResult = ScriptResults.Success

End Sub

Private Function PrinterHasLegalPaper( _
    ByVal thisPrinter As PrinterSettings) As Boolean

    Dim size As PaperSize
    Dim hasLegal As Boolean = False

    For Each size In thisPrinter.PaperSizes
        If size.Kind = PaperKind.Legal Then
            hasLegal = True
        End If
    Next

    Return hasLegal

End Function
```

```csharp
public void Main()
        {

            PrinterSettings currentPrinter = new PrinterSettings();
            PaperSize size;
            Boolean Flag = false;

            ArrayList printerList = new ArrayList();
            foreach (string printerName in PrinterSettings.InstalledPrinters)
            {
                currentPrinter.PrinterName = printerName;
                if (PrinterHasLegalPaper(currentPrinter))
                {
                    printerList.Add(printerName);
                    Dts.Events.FireInformation(0, "Example", "Printer " + printerName + " has legal paper.", String.Empty, 0, ref Flag);
                }
                else
                {
                    Dts.Events.FireWarning(0, "Example", "Printer " + printerName + " DOES NOT have legal paper.", String.Empty, 0);
                }
            }

            Dts.Variables["PrinterList"].Value = printerList;

            Dts.TaskResult = (int)ScriptResults.Success;

        }

        private bool PrinterHasLegalPaper(PrinterSettings thisPrinter)
        {

            bool hasLegal = false;

            foreach (PaperSize size in thisPrinter.PaperSizes)
            {
                if (size.Kind == PaperKind.Legal)
                {
                    hasLegal = true;
                }
            }

            return hasLegal;

        }
```

<span data-ttu-id="d35a1-118">![Icône de Integration Services (petite)](../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="d35a1-118">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="d35a1-119">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="d35a1-119">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="d35a1-120">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="d35a1-120">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="d35a1-121">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="d35a1-121">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="d35a1-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d35a1-122">See Also</span></span>
 [<span data-ttu-id="d35a1-123">Exemples de tâche de script</span><span class="sxs-lookup"><span data-stu-id="d35a1-123">Script Task Examples</span></span>](../extending-packages-scripting-task-examples/script-task-examples.md)


