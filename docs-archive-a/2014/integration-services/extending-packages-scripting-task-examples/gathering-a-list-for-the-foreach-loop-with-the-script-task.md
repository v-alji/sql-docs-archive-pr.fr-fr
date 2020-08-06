---
title: Création d’une liste pour la boucle Foreach à l’aide de la tâche de script | Microsoft Docs
ms.custom: ''
ms.date: 08/22/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- Foreach Loop containers
- Script task [Integration Services], Foreach loops
- Script task [Integration Services], examples
- SSIS Script task, Foreach loops
ms.assetid: 694f0462-d0c5-4191-b64e-821b1bdef055
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 039860da121efaa52115bb515b158ea10373e459
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696992"
---
# <a name="gathering-a-list-for-the-foreach-loop-with-the-script-task"></a><span data-ttu-id="f3a16-102">Création d'une liste pour la boucle Foreach à l'aide de la tâche de script</span><span class="sxs-lookup"><span data-stu-id="f3a16-102">Gathering a List for the ForEach Loop with the Script Task</span></span>
  <span data-ttu-id="f3a16-103">L'énumérateur Foreach à partir d'une variable énumère les éléments d'une liste qui lui est transmise via une variable et effectue les mêmes tâches sur chaque élément.</span><span class="sxs-lookup"><span data-stu-id="f3a16-103">The Foreach from Variable Enumerator enumerates over the items in a list that is passed to it in a variable and performs the same tasks on each item.</span></span> <span data-ttu-id="f3a16-104">Vous pouvez utiliser le code personnalisé dans une tâche de script pour remplir une liste à cet effet.</span><span class="sxs-lookup"><span data-stu-id="f3a16-104">You can use custom code in a Script task to populate a list for this purpose.</span></span> <span data-ttu-id="f3a16-105">Pour plus d’informations sur l’énumérateur, consultez [Conteneur de boucles Foreach](../control-flow/foreach-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="f3a16-105">For more information about the enumerator, see [Foreach Loop Container](../control-flow/foreach-loop-container.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f3a16-106">Si vous souhaitez créer une tâche plus facilement réutilisable sur plusieurs packages, envisagez d'utiliser le code indiqué dans l'exemple de tâche de script comme point de départ d'une tâche personnalisée.</span><span class="sxs-lookup"><span data-stu-id="f3a16-106">If you want to create a task that you can more easily reuse across multiple packages, consider using the code in this Script task sample as the starting point for a custom task.</span></span> <span data-ttu-id="f3a16-107">Pour plus d’informations, consultez [Développement d’une tâche personnalisée](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="f3a16-107">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>  
  
## <a name="description"></a><span data-ttu-id="f3a16-108">Description</span><span class="sxs-lookup"><span data-stu-id="f3a16-108">Description</span></span>  
 <span data-ttu-id="f3a16-109">L'exemple suivant utilise des méthodes de l'espace de noms `System.IO` pour dresser une liste de classeurs Excel sur l'ordinateur datant d'un certain nombre de jours spécifié par l'utilisateur dans une variable.</span><span class="sxs-lookup"><span data-stu-id="f3a16-109">The following example uses methods from the `System.IO` namespace to gather a list of Excel workbooks on the computer that are either newer or older than a number of days specified by the user in a variable.</span></span> <span data-ttu-id="f3a16-110">Il effectue une recherche récursive dans les répertoires du lecteur C pour trouver des fichiers dotés de l'extension .xls et examine la date de dernière modification de chaque fichier pour déterminer s'il appartient à la liste.</span><span class="sxs-lookup"><span data-stu-id="f3a16-110">It searches directories on Drive C recursively for files that have the .xls extension and examines the date on which each file was last modified to determine whether the file belongs in the list.</span></span> <span data-ttu-id="f3a16-111">Il ajoute les fichiers répondant aux critères à `ArrayList` et enregistre `ArrayList` dans une variable pour une utilisation ultérieure dans un conteneur de boucles Foreach.</span><span class="sxs-lookup"><span data-stu-id="f3a16-111">It adds qualifying files to an `ArrayList` and saves the `ArrayList` to a variable for later use in a Foreach Loop container.</span></span> <span data-ttu-id="f3a16-112">Le conteneur de boucles Foreach est configuré pour utiliser l'énumérateur Foreach à partir d'une variable.</span><span class="sxs-lookup"><span data-stu-id="f3a16-112">The Foreach Loop container is configured to use the Foreach from Variable enumerator.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f3a16-113">La variable utilisée avec l'énumérateur Foreach à partir d'une variable doit être de type `Object`.</span><span class="sxs-lookup"><span data-stu-id="f3a16-113">The variable that you use with the Foreach from Variable Enumerator must be of type `Object`.</span></span> <span data-ttu-id="f3a16-114">L'objet que vous placez dans la variable doit implémenter l'une des interfaces suivantes : `System.Collections.IEnumerable`, `System.Runtime.InteropServices.ComTypes.IEnumVARIANT`, `System.ComponentModel IListSource` ou `Microsoft.SqlServer.Dts.Runtime.Wrapper.ForEachEnumeratorHost`.</span><span class="sxs-lookup"><span data-stu-id="f3a16-114">The object that you place in the variable must implement one of the following interfaces: `System.Collections.IEnumerable`, `System.Runtime.InteropServices.ComTypes.IEnumVARIANT`, `System.ComponentModel IListSource`, or `Microsoft.SqlServer.Dts.Runtime.Wrapper.ForEachEnumeratorHost`.</span></span> <span data-ttu-id="f3a16-115">`Array` ou `ArrayList` est couramment utilisé.</span><span class="sxs-lookup"><span data-stu-id="f3a16-115">An `Array` or `ArrayList` is commonly used.</span></span> <span data-ttu-id="f3a16-116">`ArrayList` requiert une référence et une instruction `Imports` pour l'espace de noms `System.Collections`.</span><span class="sxs-lookup"><span data-stu-id="f3a16-116">The `ArrayList` requires a reference and an `Imports` statement for the `System.Collections` namespace.</span></span>  
  
 <span data-ttu-id="f3a16-117">Vous pouvez apprendre à manipuler cette tâche en attribuant différentes valeurs, positives et négatives, à la variable de package `FileAge`.</span><span class="sxs-lookup"><span data-stu-id="f3a16-117">You can experiment with this task by using different positive and negative values for the `FileAge` package variable.</span></span> <span data-ttu-id="f3a16-118">Par exemple, vous pouvez entrer 5 pour rechercher les fichiers créés au cours des cinq derniers jours ou entrer -3 pour rechercher les fichiers créés il y a plus de trois jours.</span><span class="sxs-lookup"><span data-stu-id="f3a16-118">For example, you can enter 5 to search for files created in the last five days, or enter -3 to search for files that were created more than three days ago.</span></span> <span data-ttu-id="f3a16-119">Cette tâche peut prendre une minute ou deux sur un lecteur contenant de nombreux dossiers à rechercher.</span><span class="sxs-lookup"><span data-stu-id="f3a16-119">This task may take a minute or two on a drive with many folders to search.</span></span>  
  
#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="f3a16-120">Pour configurer cet exemple de tâche de script</span><span class="sxs-lookup"><span data-stu-id="f3a16-120">To configure this Script Task example</span></span>  
  
1.  <span data-ttu-id="f3a16-121">Créez une variable de package nommée `FileAge` de type entier et entrez une valeur entière positive ou négative.</span><span class="sxs-lookup"><span data-stu-id="f3a16-121">Create a package variable named `FileAge` of type integer and enter a positive or negative integer value.</span></span> <span data-ttu-id="f3a16-122">Selon que la valeur est positive ou négative, le code recherche respectivement les fichiers postérieurs ou antérieurs à la date spécifiée (en nombre de jours).</span><span class="sxs-lookup"><span data-stu-id="f3a16-122">When the value is positive, the code searches for files newer than the specified number of days; when negative, for files older than the specified number of days.</span></span>  
  
2.  <span data-ttu-id="f3a16-123">Créez une variable de package nommée `FileList` de type `Object` pour recevoir la liste de fichiers dressée par la tâche de script, qui sera utilisée ultérieurement par l'énumérateur Foreach à partir d'une variable.</span><span class="sxs-lookup"><span data-stu-id="f3a16-123">Create a package variable named `FileList` of type `Object` to receive the list of files gathered by the Script task for later use by the Foreach from Variable Enumerator.</span></span>  
  
3.  <span data-ttu-id="f3a16-124">Ajoutez la variable `FileAge` à la propriété `ReadOnlyVariables` de la tâche de script et ajoutez la variable `FileList` à la propriété `ReadWriteVariables`.</span><span class="sxs-lookup"><span data-stu-id="f3a16-124">Add the `FileAge` variable to the Script task's `ReadOnlyVariables` property, and add the `FileList` variable to the `ReadWriteVariables` property.</span></span>  
  
4.  <span data-ttu-id="f3a16-125">Dans votre code, importez les espaces de noms `System.Collections` et `System.IO`.</span><span class="sxs-lookup"><span data-stu-id="f3a16-125">In your code, import the `System.Collections` and the `System.IO` namespaces.</span></span>  
  
### <a name="code"></a><span data-ttu-id="f3a16-126">Code</span><span class="sxs-lookup"><span data-stu-id="f3a16-126">Code</span></span>  
  
```vb  
Imports System  
Imports System.Data  
Imports System.Math  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports System.Collections  
Imports System.IO  
  
Public Class ScriptMain  
  
  Private Const FILE_AGE As Integer = -50  
  
  Private Const FILE_ROOT As String = "C:\"  
  Private Const FILE_FILTER As String = "*.xls"  
  
  Private isCheckForNewer As Boolean = True  
  Dim fileAgeLimit As Integer  
  Private listForEnumerator As ArrayList  
  
  Public Sub Main()  
  
    fileAgeLimit = DirectCast(Dts.Variables("FileAge").Value, Integer)  
  
    ' If value provided is positive, we want files NEWER THAN n days.  
    '  If negative, we want files OLDER THAN n days.  
    If fileAgeLimit < 0 Then  
      isCheckForNewer = False  
    End If  
    ' Extract number of days as positive integer.  
    fileAgeLimit = Math.Abs(fileAgeLimit)  
  
    listForEnumerator = New ArrayList  
  
    GetFilesInFolder(FILE_ROOT)  
  
    ' Return the list of files to the variable  
    '  for later use by the Foreach from Variable enumerator.  
    System.Windows.Forms.MessageBox.Show("Matching files: " & listForEnumerator.Count.ToString, "Results", Windows.Forms.MessageBoxButtons.OK, Windows.Forms.MessageBoxIcon.Information)  
    Dts.Variables("FileList").Value = listForEnumerator  
  
    Dts.TaskResult = ScriptResults.Success  
  
  End Sub  
  
  Private Sub GetFilesInFolder(ByVal folderPath As String)  
  
    Dim localFiles() As String  
    Dim localFile As String  
    Dim fileChangeDate As Date  
    Dim fileAge As TimeSpan  
    Dim fileAgeInDays As Integer  
    Dim childFolder As String  
  
    Try  
      localFiles = Directory.GetFiles(folderPath, FILE_FILTER)  
      For Each localFile In localFiles  
        fileChangeDate = File.GetLastWriteTime(localFile)  
        fileAge = DateTime.Now.Subtract(fileChangeDate)  
        fileAgeInDays = fileAge.Days  
        CheckAgeOfFile(localFile, fileAgeInDays)  
      Next  
  
      If Directory.GetDirectories(folderPath).Length > 0 Then  
        For Each childFolder In Directory.GetDirectories(folderPath)  
          GetFilesInFolder(childFolder)  
        Next  
      End If  
  
    Catch  
      ' Ignore exceptions on special folders such as System Volume Information.  
    End Try  
  
  End Sub  
  
  Private Sub CheckAgeOfFile(ByVal localFile As String, ByVal fileAgeInDays As Integer)  
  
    If isCheckForNewer Then  
      If fileAgeInDays <= fileAgeLimit Then  
        listForEnumerator.Add(localFile)  
      End If  
    Else  
      If fileAgeInDays > fileAgeLimit Then  
        listForEnumerator.Add(localFile)  
      End If  
    End If  
  
  End Sub  
  
End Class  
```  
  
```csharp  
using System;  
using System.Data;  
using System.Math;  
using Microsoft.SqlServer.Dts.Runtime;  
using System.Collections;  
using System.IO;  
  
public partial class ScriptMain : Microsoft.SqlServer.Dts.Tasks.ScriptTask.VSTARTScriptObjectModelBase  
    {  
  
        private const int FILE_AGE = -50;  
  
        private const string FILE_ROOT = "C:\\";  
        private const string FILE_FILTER = "*.xls";  
  
        private bool isCheckForNewer = true;  
        int fileAgeLimit;  
        private ArrayList listForEnumerator;  
  
        public void Main()  
  {  
  
    fileAgeLimit = (int)(Dts.Variables["FileAge"].Value);  
  
    // If value provided is positive, we want files NEWER THAN n days.  
    // If negative, we want files OLDER THAN n days.  
    if (fileAgeLimit<0)  
    {  
      isCheckForNewer = false;  
    }  
    // Extract number of days as positive integer.  
    fileAgeLimit = Math.Abs(fileAgeLimit);  
  
    ArrayList listForEnumerator = new ArrayList();  
  
    GetFilesInFolder(FILE_ROOT);  
  
    // Return the list of files to the variable  
    // for later use by the Foreach from Variable enumerator.  
    System.Windows.Forms.MessageBox.Show("Matching files: "+ listForEnumerator.Count, "Results",   
MessageBoxButtons.OK, MessageBoxIcon.Information);  
    Dts.Variables["FileList"].Value = listForEnumerator;  
  
    Dts.TaskResult = (int)ScriptResults.Success;  
  
  }  
  
        private void GetFilesInFolder(string folderPath)  
        {  
  
            string[] localFiles;  
            DateTime fileChangeDate;  
            TimeSpan fileAge;  
            int fileAgeInDays;  
  
            try  
            {  
                localFiles = Directory.GetFiles(folderPath, FILE_FILTER);  
                foreach (string localFile in localFiles)  
                {  
                    fileChangeDate = File.GetLastWriteTime(localFile);  
                    fileAge = DateTime.Now.Subtract(fileChangeDate);  
                    fileAgeInDays = fileAge.Days;  
                    CheckAgeOfFile(localFile, fileAgeInDays);  
                }  
  
                if (Directory.GetDirectories(folderPath).Length > 0)  
                {  
                    foreach (string childFolder in Directory.GetDirectories(folderPath))  
                    {  
                        GetFilesInFolder(childFolder);  
                    }  
                }  
  
            }  
            catch  
            {  
                // Ignore exceptions on special folders, such as System Volume Information.  
            }  
  
        }  
  
        private void CheckAgeOfFile(string localFile, int fileAgeInDays)  
        {  
  
            if (isCheckForNewer)  
            {  
                if (fileAgeInDays <= fileAgeLimit)  
                {  
                    listForEnumerator.Add(localFile);  
                }  
            }  
            else  
            {  
                if (fileAgeInDays > fileAgeLimit)  
                {  
                    listForEnumerator.Add(localFile);  
                }  
            }  
  
        }  
  
    }  
```  
  
<span data-ttu-id="f3a16-127">![Icône de Integration Services (petite)](../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="f3a16-127">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="f3a16-128">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="f3a16-128">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="f3a16-129">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="f3a16-129">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="f3a16-130">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="f3a16-130">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3a16-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f3a16-131">See Also</span></span>  
 <span data-ttu-id="f3a16-132">[Conteneur de boucles Foreach](../control-flow/foreach-loop-container.md) </span><span class="sxs-lookup"><span data-stu-id="f3a16-132">[Foreach Loop Container](../control-flow/foreach-loop-container.md) </span></span>  
 [<span data-ttu-id="f3a16-133">Configurer un conteneur de boucles Foreach</span><span class="sxs-lookup"><span data-stu-id="f3a16-133">Configure a Foreach Loop Container</span></span>](../configure-a-foreach-loop-container.md)  
  
  
