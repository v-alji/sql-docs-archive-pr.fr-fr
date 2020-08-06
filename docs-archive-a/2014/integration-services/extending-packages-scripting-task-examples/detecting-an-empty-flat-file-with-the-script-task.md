---
title: Détection d’un fichier plat vide à l’aide de la tâche de script | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- flat files
- Script task [Integration Services], empty flat files
- SSIS Script task, empty flat files
- Script task [Integration Services], examples
ms.assetid: 1b4defb8-886a-483d-8056-d1b91d37bc90
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 379b11bd18752ad648fc5f24d11d9ed5bfb63e14
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610727"
---
# <a name="detecting-an-empty-flat-file-with-the-script-task"></a><span data-ttu-id="5662e-102">Détection d'un fichier plat vide à l'aide de la tâche de script</span><span class="sxs-lookup"><span data-stu-id="5662e-102">Detecting an Empty Flat File with the Script Task</span></span>
  <span data-ttu-id="5662e-103">La source de fichier plat ne détermine pas si un fichier plat contient des lignes de données avant de tenter de les traiter.</span><span class="sxs-lookup"><span data-stu-id="5662e-103">The Flat File source does not determine whether a flat file contains rows of data before attempting to process it.</span></span> <span data-ttu-id="5662e-104">Vous pouvez améliorer l'efficacité d'un package, notamment d'un package qui parcourt de nombreux fichiers plats, en ignorant les fichiers qui ne contiennent aucune ligne de données.</span><span class="sxs-lookup"><span data-stu-id="5662e-104">You may want to improve the efficiency of a package, especially of a package that iterates over numerous flat files, by skipping files that do not contain any rows of data.</span></span> <span data-ttu-id="5662e-105">La tâche de script peut rechercher un fichier plat vide avant que le package ne commence à traiter le flux de données.</span><span class="sxs-lookup"><span data-stu-id="5662e-105">The Script task can look for an empty flat file before the package begins to process the data flow.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5662e-106">Si vous souhaitez créer une tâche plus facilement réutilisable sur plusieurs packages, envisagez d'utiliser le code indiqué dans l'exemple de tâche de script comme point de départ d'une tâche personnalisée.</span><span class="sxs-lookup"><span data-stu-id="5662e-106">If you want to create a task that you can more easily reuse across multiple packages, consider using the code in this Script task sample as the starting point for a custom task.</span></span> <span data-ttu-id="5662e-107">Pour plus d’informations, consultez [Développement d’une tâche personnalisée](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="5662e-107">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>  
  
## <a name="description"></a><span data-ttu-id="5662e-108">Description</span><span class="sxs-lookup"><span data-stu-id="5662e-108">Description</span></span>  
 <span data-ttu-id="5662e-109">L'exemple suivant utilise des méthodes de l'espace de noms `System.IO` pour tester le fichier plat spécifié dans un gestionnaire de connexions de fichiers plats afin de déterminer si le fichier est vide ou s'il contient uniquement les lignes attendues ne correspondant pas à des données, telles que des en-têtes de colonnes ou des lignes vides.</span><span class="sxs-lookup"><span data-stu-id="5662e-109">The following example uses methods from the `System.IO` namespace to test the flat file specified in a Flat File connection manager to determine whether the file is empty, or whether it contains only expected non-data rows such as column headers or an empty line.</span></span> <span data-ttu-id="5662e-110">Le script vérifie d'abord la taille du fichier ; une taille de zéro octets indique que le fichier est vide.</span><span class="sxs-lookup"><span data-stu-id="5662e-110">The script checks the size of the file first; if the size is zero bytes, the file is empty.</span></span> <span data-ttu-id="5662e-111">Si la taille du fichier est supérieure à zéro, le script lit les lignes du fichier jusqu'à la dernière, ou jusqu'à ce que le nombre de lignes dépasse le nombre attendu de lignes ne correspondant pas à des données.</span><span class="sxs-lookup"><span data-stu-id="5662e-111">If the file size is greater than zero, the script reads lines from the file until there are no more lines, or until the number of lines exceeds the expected number of non-data rows.</span></span> <span data-ttu-id="5662e-112">Si le nombre de lignes dans le fichier est inférieur ou égal au nombre attendu de lignes ne correspondant pas à des données, le fichier est considéré comme vide.</span><span class="sxs-lookup"><span data-stu-id="5662e-112">If the number of lines in the file is less than or equal to the expected number of non-data rows, then the file is considered empty.</span></span> <span data-ttu-id="5662e-113">Le résultat est retourné sous la forme d'une valeur booléenne dans une variable utilisateur, dont la valeur peut être utilisée pour le branchement du flux de contrôle du package.</span><span class="sxs-lookup"><span data-stu-id="5662e-113">The result is returned as a Boolean value in a user variable, the value of which can be used for branching in the package's control flow.</span></span> <span data-ttu-id="5662e-114">La `FireInformation` méthode affiche également le résultat dans la fenêtre **sortie** des [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] outils pour les applications (VSTA).</span><span class="sxs-lookup"><span data-stu-id="5662e-114">The `FireInformation` method also displays the result in the **Output** window of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span></span>  
  
#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="5662e-115">Pour configurer cet exemple de tâche de script</span><span class="sxs-lookup"><span data-stu-id="5662e-115">To configure this Script Task example</span></span>  
  
1.  <span data-ttu-id="5662e-116">Créez et configurez un gestionnaire de connexions de fichiers plats nommé `EmptyFlatFileTest` .</span><span class="sxs-lookup"><span data-stu-id="5662e-116">Create and configure a flat file connection manager named `EmptyFlatFileTest`.</span></span>  
  
2.  <span data-ttu-id="5662e-117">Créez une variable de type entier appelée `FFNonDataRows` et attribuez-lui une valeur égale au nombre attendu de lignes ne correspondant pas à des données dans le fichier plat.</span><span class="sxs-lookup"><span data-stu-id="5662e-117">Create an integer variable named `FFNonDataRows` and set its value to the number of non-data rows expected in the flat file.</span></span>  
  
3.  <span data-ttu-id="5662e-118">Créez une variable booléenne appelée `FFIsEmpty`.</span><span class="sxs-lookup"><span data-stu-id="5662e-118">Create a Boolean variable named `FFIsEmpty`.</span></span>  
  
4.  <span data-ttu-id="5662e-119">Ajoutez la variable `FFNonDataRows` à la propriété **ReadOnlyVariables** de la tâche de script.</span><span class="sxs-lookup"><span data-stu-id="5662e-119">Add the `FFNonDataRows` variable to the Script task's **ReadOnlyVariables** property.</span></span>  
  
5.  <span data-ttu-id="5662e-120">Ajoutez la variable `FFIsEmpty` à la propriété **ReadWriteVariables** de la tâche de script.</span><span class="sxs-lookup"><span data-stu-id="5662e-120">Add the `FFIsEmpty` variable to the Script task's **ReadWriteVariables** property.</span></span>  
  
6.  <span data-ttu-id="5662e-121">Dans votre code, importez l'espace de noms `System.IO`.</span><span class="sxs-lookup"><span data-stu-id="5662e-121">In your code, import the `System.IO` namespace.</span></span>  
  
 <span data-ttu-id="5662e-122">Si vous parcourez les fichiers avec un énumérateur Foreach File, au lieu d'utiliser un seul gestionnaire de connexions de fichiers plats, vous devez modifier l'exemple de code ci-dessous pour obtenir le nom et le chemin d'accès du fichier à partir de la variable dans laquelle la valeur énumérée est stockée et non à partir du gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="5662e-122">If you are iterating over files with a Foreach File enumerator, instead of using a single Flat File connection manager, you will need to modify the sample code below to obtain the file name and path from the variable in which the enumerated value is stored instead of from the connection manager.</span></span>  
  
### <a name="code"></a><span data-ttu-id="5662e-123">Code</span><span class="sxs-lookup"><span data-stu-id="5662e-123">Code</span></span>  
  
```vb  
Public Sub Main()  
  
  Dim nonDataRows As Integer = _  
      DirectCast(Dts.Variables("FFNonDataRows").Value, Integer)  
  Dim ffConnection As String = _  
      DirectCast(Dts.Connections("EmptyFlatFileTest").AcquireConnection(Nothing), _  
      String)  
  Dim flatFileInfo As New FileInfo(ffConnection)  
  ' If file size is 0 bytes, flat file does not contain data.  
  Dim fileSize As Long = flatFileInfo.Length  
  If fileSize > 0 Then  
    Dim lineCount As Integer = 0  
    Dim line As String  
    Dim fsFlatFile As New StreamReader(ffConnection)  
    Do Until fsFlatFile.EndOfStream  
      line = fsFlatFile.ReadLine  
      lineCount += 1  
      ' If line count > expected number of non-data rows,  
      '  flat file contains data (default value).  
      If lineCount > nonDataRows Then  
        Exit Do  
      End If  
      ' If line count <= expected number of non-data rows,  
      '  flat file does not contain data.  
      If lineCount <= nonDataRows Then  
        Dts.Variables("FFIsEmpty").Value = True  
      End If  
    Loop  
  Else  
    Dts.Variables("FFIsEmpty").Value = True  
  End If  
  
  Dim fireAgain As Boolean = False  
  Dts.Events.FireInformation(0, "Script Task", _  
      String.Format("{0}: {1}", ffConnection, _  
      Dts.Variables("FFIsEmpty").Value.ToString), _  
      String.Empty, 0, fireAgain)  
  
  Dts.TaskResult = ScriptResults.Success  
  
End Sub  
```  
  
```csharp  
public void Main()  
        {  
  
            int nonDataRows = (int)(Dts.Variables["FFNonDataRows"].Value);  
            string ffConnection = (string)(Dts.Connections["EmptyFlatFileTest"].AcquireConnection(null) as String);  
            FileInfo flatFileInfo = new FileInfo(ffConnection);  
            // If file size is 0 bytes, flat file does not contain data.  
            long fileSize = flatFileInfo.Length;  
            if (fileSize > 0)  
            {  
  
                int lineCount = 0;  
                string line;  
                StreamReader fsFlatFile = new StreamReader(ffConnection);  
                while (!(fsFlatFile.EndOfStream))  
                {  
                    Console.WriteLine (fsFlatFile.ReadLine());  
                    lineCount += 1;  
                    // If line count > expected number of non-data rows,  
                    //  flat file contains data (default value).  
                    if (lineCount > nonDataRows)  
                    {  
                        break;  
                    }  
                    // If line count <= expected number of non-data rows,  
                    //  flat file does not contain data.  
                    if (lineCount <= nonDataRows)  
                    {  
                        Dts.Variables["FFIsEmpty"].Value = true;  
                    }  
                }  
            }  
            else  
            {  
                Dts.Variables["FFIsEmpty"].Value = true;  
            }  
  
            bool fireAgain = false;  
            Dts.Events.FireInformation(0, "Script Task", String.Format("{0}: {1}", ffConnection, Dts.Variables["FFIsEmpty"].Value), String.Empty, 0, ref fireAgain);  
  
            Dts.TaskResult = (int)ScriptResults.Success;  
  
        }  
```  
  
<span data-ttu-id="5662e-124">![Icône de Integration Services (petite)](../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="5662e-124">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="5662e-125">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="5662e-125">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="5662e-126">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="5662e-126">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="5662e-127">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="5662e-127">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5662e-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5662e-128">See Also</span></span>  
 [<span data-ttu-id="5662e-129">Exemples de tâche de script</span><span class="sxs-lookup"><span data-stu-id="5662e-129">Script Task Examples</span></span>](../extending-packages-scripting-task-examples/script-task-examples.md)  
  
  
