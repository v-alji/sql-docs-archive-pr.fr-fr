---
title: Utilisation de fichiers Excel avec la tâche de script | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script task [Integration Services], Excel files
- Script task [Integration Services], examples
- Excel [Integration Services]
ms.assetid: b8fa110a-2c9c-4f5a-8fe1-305555640e44
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 68a764452de548cd46e74d2a7f2f588a050a21c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605656"
---
# <a name="working-with-excel-files-with-the-script-task"></a><span data-ttu-id="ba65c-102">Utilisation de fichiers Excel avec la tâche de script</span><span class="sxs-lookup"><span data-stu-id="ba65c-102">Working with Excel Files with the Script Task</span></span>
  [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="ba65c-103">fournit le gestionnaire de connexions Excel, la source Excel et la destination Excel pour utiliser des données stockées dans des feuilles de calcul au format de fichier [!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel.</span><span class="sxs-lookup"><span data-stu-id="ba65c-103">provides the Excel connection manager, Excel source, and Excel destination for working with data stored in spreadsheets in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel file format.</span></span> <span data-ttu-id="ba65c-104">Les techniques décrites dans cette rubrique utilisent la tâche de script pour obtenir des informations sur les bases de données (fichiers de classeur) et tables (feuilles de calcul et plages nommées) Excel disponibles.</span><span class="sxs-lookup"><span data-stu-id="ba65c-104">The techniques described in this topic use the Script task to obtain information about available Excel databases (workbook files) and tables (worksheets and named ranges).</span></span> <span data-ttu-id="ba65c-105">Ces exemples peuvent être modifiés facilement afin d'utiliser l'une des autres sources de données basées sur des fichiers prises en charge par le fournisseur OLE DB [!INCLUDE[msCoName](../../includes/msconame-md.md)] Jet.</span><span class="sxs-lookup"><span data-stu-id="ba65c-105">These samples can easily be modified to work with any of the other file-based data sources supported by the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Jet OLE DB Provider.</span></span>  
  
 [<span data-ttu-id="ba65c-106">Configuration d’un package pour tester les exemples</span><span class="sxs-lookup"><span data-stu-id="ba65c-106">Configuring a Package to Test the Samples</span></span>](#configuring)  
  
 [<span data-ttu-id="ba65c-107">Exemple 1 : vérifier si un fichier Excel existe</span><span class="sxs-lookup"><span data-stu-id="ba65c-107">Example1: Check Whether an Excel File Exists</span></span>](#example1)  
  
 [<span data-ttu-id="ba65c-108">Exemple 2 : vérifier si une table Excel existe</span><span class="sxs-lookup"><span data-stu-id="ba65c-108">Example 2: Check Whether an Excel Table Exists</span></span>](#example2)  
  
 [<span data-ttu-id="ba65c-109">Exemple 3 : obtenir la liste des fichiers Excel contenus dans un dossier</span><span class="sxs-lookup"><span data-stu-id="ba65c-109">Example 3: Get a List of Excel Files in a Folder</span></span>](#example3)  
  
 [<span data-ttu-id="ba65c-110">Exemple 4 : obtenir la liste des tables contenues dans un fichier Excel</span><span class="sxs-lookup"><span data-stu-id="ba65c-110">Example 4: Get a List of Tables in an Excel File</span></span>](#example4)  
  
 [<span data-ttu-id="ba65c-111">Affichage des résultats des exemples</span><span class="sxs-lookup"><span data-stu-id="ba65c-111">Displaying the Results of the Samples</span></span>](#testing)  
  
> [!NOTE]  
>  <span data-ttu-id="ba65c-112">Si vous souhaitez créer une tâche plus facilement réutilisable sur plusieurs packages, envisagez d'utiliser le code indiqué dans l'exemple de tâche de script comme point de départ d'une tâche personnalisée.</span><span class="sxs-lookup"><span data-stu-id="ba65c-112">If you want to create a task that you can more easily reuse across multiple packages, consider using the code in this Script task sample as the starting point for a custom task.</span></span> <span data-ttu-id="ba65c-113">Pour plus d’informations, consultez [Développement d’une tâche personnalisée](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="ba65c-113">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>  
  
##  <a name="configuring-a-package-to-test-the-samples"></a><a name="configuring"></a> <span data-ttu-id="ba65c-114">Configuration d’un package pour tester les exemples</span><span class="sxs-lookup"><span data-stu-id="ba65c-114">Configuring a Package to Test the Samples</span></span>  
 <span data-ttu-id="ba65c-115">Vous pouvez configurer un package unique pour tester tous les exemples de cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="ba65c-115">You can configure a single package to test all the samples in this topic.</span></span> <span data-ttu-id="ba65c-116">Les exemples utilisent de nombreuses variables de package et classes [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] identiques.</span><span class="sxs-lookup"><span data-stu-id="ba65c-116">The samples use many of the same package variables and the same [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] classes.</span></span>  
  
#### <a name="to-configure-a-package-for-use-with-the-examples-in-this-topic"></a><span data-ttu-id="ba65c-117">Pour configurer un package à utiliser avec les exemples de cette rubrique</span><span class="sxs-lookup"><span data-stu-id="ba65c-117">To configure a package for use with the examples in this topic</span></span>  
  
1.  <span data-ttu-id="ba65c-118">Créez un projet [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] et ouvrez le package par défaut afin de le modifier.</span><span class="sxs-lookup"><span data-stu-id="ba65c-118">Create a new [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] and open the default package for editing.</span></span>  
  
2.  <span data-ttu-id="ba65c-119">**Variables**.</span><span class="sxs-lookup"><span data-stu-id="ba65c-119">**Variables**.</span></span> <span data-ttu-id="ba65c-120">Ouvrez la fenêtre **Variables** et définissez les variables suivantes :</span><span class="sxs-lookup"><span data-stu-id="ba65c-120">Open the **Variables** window and define the following variables:</span></span>  
  
    -   <span data-ttu-id="ba65c-121">`ExcelFile`, de type `String`.</span><span class="sxs-lookup"><span data-stu-id="ba65c-121">`ExcelFile`, of type `String`.</span></span> <span data-ttu-id="ba65c-122">Entrez le chemin d'accès complet et le nom de fichier d'un classeur Excel existant.</span><span class="sxs-lookup"><span data-stu-id="ba65c-122">Enter the complete path and filename to an existing Excel workbook.</span></span>  
  
    -   <span data-ttu-id="ba65c-123">`ExcelTable`, de type `String`.</span><span class="sxs-lookup"><span data-stu-id="ba65c-123">`ExcelTable`, of type `String`.</span></span> <span data-ttu-id="ba65c-124">Entrez le nom d'une feuille de calcul ou d'une plage nommée existante dans le classeur nommé dans la valeur de la variable `ExcelFile`.</span><span class="sxs-lookup"><span data-stu-id="ba65c-124">Enter the name of an existing worksheet or named range in the workbook named in the value of the `ExcelFile` variable.</span></span> <span data-ttu-id="ba65c-125">Cette valeur respecte la casse.</span><span class="sxs-lookup"><span data-stu-id="ba65c-125">This value is case-sensitive.</span></span>  
  
    -   <span data-ttu-id="ba65c-126">`ExcelFileExists`, de type `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="ba65c-126">`ExcelFileExists`, of type `Boolean`.</span></span>  
  
    -   <span data-ttu-id="ba65c-127">`ExcelTableExists`, de type `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="ba65c-127">`ExcelTableExists`, of type `Boolean`.</span></span>  
  
    -   <span data-ttu-id="ba65c-128">`ExcelFolder`, de type `String`.</span><span class="sxs-lookup"><span data-stu-id="ba65c-128">`ExcelFolder`, of type `String`.</span></span> <span data-ttu-id="ba65c-129">Entrez le chemin d'accès complet d'un dossier qui contient au moins un classeur Excel.</span><span class="sxs-lookup"><span data-stu-id="ba65c-129">Enter the complete path of a folder that contains at least one Excel workbook.</span></span>  
  
    -   <span data-ttu-id="ba65c-130">`ExcelFiles`, de type `Object`.</span><span class="sxs-lookup"><span data-stu-id="ba65c-130">`ExcelFiles`, of type `Object`.</span></span>  
  
    -   <span data-ttu-id="ba65c-131">`ExcelTables`, de type `Object`.</span><span class="sxs-lookup"><span data-stu-id="ba65c-131">`ExcelTables`, of type `Object`.</span></span>  
  
3.  <span data-ttu-id="ba65c-132">**Instructions Imports**.</span><span class="sxs-lookup"><span data-stu-id="ba65c-132">**Imports statements**.</span></span> <span data-ttu-id="ba65c-133">La plupart des exemples de code impliquent que vous importiez l'un des espaces de noms [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] suivants ou les deux au début de votre fichier de script :</span><span class="sxs-lookup"><span data-stu-id="ba65c-133">Most of the code samples require you to import one or both of the following [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] namespaces at the top of your script file:</span></span>  
  
    -   <span data-ttu-id="ba65c-134">`System.IO`, pour les opérations du système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="ba65c-134">`System.IO`, for file system operations.</span></span>  
  
    -   <span data-ttu-id="ba65c-135">`System.Data.OleDb`, pour ouvrir des fichiers Excel en tant que sources de données.</span><span class="sxs-lookup"><span data-stu-id="ba65c-135">`System.Data.OleDb`, to open Excel files as data sources.</span></span>  
  
4.  <span data-ttu-id="ba65c-136">**Références**.</span><span class="sxs-lookup"><span data-stu-id="ba65c-136">**References**.</span></span> <span data-ttu-id="ba65c-137">Les exemples de code qui lisent des informations de schéma à partir de fichiers Excel requièrent une référence supplémentaire, dans le projet de script, à l'espace de noms `System.Xml`.</span><span class="sxs-lookup"><span data-stu-id="ba65c-137">The code samples that read schema information from Excel files require an additional reference in the script project to the `System.Xml` namespace.</span></span>  
  
5.  <span data-ttu-id="ba65c-138">Définissez le langage de script par défaut du composant Script en utilisant l’option **Langage de script** dans la page **Général** de la boîte de dialogue **Options**.</span><span class="sxs-lookup"><span data-stu-id="ba65c-138">Set the default scripting language for the Script component by using the **Scripting language** option on the **General** page of the **Options** dialog box.</span></span> <span data-ttu-id="ba65c-139">Pour plus d'informations, consultez [General Page](../general-page-of-integration-services-designers-options.md).</span><span class="sxs-lookup"><span data-stu-id="ba65c-139">For more information, see [General Page](../general-page-of-integration-services-designers-options.md).</span></span>  
  
##  <a name="example-1-description-check-whether-an-excel-file-exists"></a><a name="example1"></a> <span data-ttu-id="ba65c-140">Description de l’exemple 1 : vérifier si un fichier Excel existe</span><span class="sxs-lookup"><span data-stu-id="ba65c-140">Example 1 Description: Check Whether an Excel File Exists</span></span>  
 <span data-ttu-id="ba65c-141">Cet exemple détermine si le fichier de classeur Excel spécifié dans la variable `ExcelFile` existe, puis définit la valeur booléenne de la variable `ExcelFileExists` sur le résultat.</span><span class="sxs-lookup"><span data-stu-id="ba65c-141">This example determines whether the Excel workbook file specified in the `ExcelFile` variable exists, and then sets the Boolean value of the `ExcelFileExists` variable to the result.</span></span> <span data-ttu-id="ba65c-142">Vous pouvez utiliser cette valeur booléenne pour créer une branche dans le flux de travail du package.</span><span class="sxs-lookup"><span data-stu-id="ba65c-142">You can use this Boolean value for branching in the workflow of the package.</span></span>  
  
#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="ba65c-143">Pour configurer cet exemple de tâche de script</span><span class="sxs-lookup"><span data-stu-id="ba65c-143">To configure this Script Task example</span></span>  
  
1.  <span data-ttu-id="ba65c-144">Ajoutez une nouvelle tâche de script au package et remplacez son nom par `ExcelFileExists` .</span><span class="sxs-lookup"><span data-stu-id="ba65c-144">Add a new Script task to the package and change its name to `ExcelFileExists`.</span></span>  
  
2.  <span data-ttu-id="ba65c-145">Dans l’**Éditeur de tâche de script**, sous l’onglet **Script**, cliquez sur **ReadOnlyVariables** et entrez la valeur de la propriété en utilisant l’une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="ba65c-145">In the **Script Task Editor**, on the **Script** tab, click **ReadOnlyVariables** and enter the property value using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="ba65c-146">Tapez `ExcelFile`.</span><span class="sxs-lookup"><span data-stu-id="ba65c-146">Type `ExcelFile`.</span></span>  
  
         <span data-ttu-id="ba65c-147">-ou-</span><span class="sxs-lookup"><span data-stu-id="ba65c-147">-or-</span></span>  
  
    -   <span data-ttu-id="ba65c-148">Cliquez sur le bouton de sélection (**...**) en regard du champ de propriété, puis dans la boîte de dialogue **Sélectionner des variables** , sélectionnez la `ExcelFile` variable.</span><span class="sxs-lookup"><span data-stu-id="ba65c-148">Click the ellipsis (**...**) button next to the property field, and in the **Select variables** dialog box, select the `ExcelFile` variable.</span></span>  
  
3.  <span data-ttu-id="ba65c-149">Cliquez sur **ReadWriteVariables** et entrez la valeur de propriété à l’aide de l’une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="ba65c-149">Click **ReadWriteVariables** and enter the property value using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="ba65c-150">Tapez `ExcelFileExists`.</span><span class="sxs-lookup"><span data-stu-id="ba65c-150">Type `ExcelFileExists`.</span></span>  
  
         <span data-ttu-id="ba65c-151">-ou-</span><span class="sxs-lookup"><span data-stu-id="ba65c-151">-or-</span></span>  
  
    -   <span data-ttu-id="ba65c-152">Cliquez sur le bouton de sélection (**...**) en regard du champ de propriété, puis dans la boîte de dialogue **Sélectionner des variables** , sélectionnez la `ExcelFileExists` variable.</span><span class="sxs-lookup"><span data-stu-id="ba65c-152">Click the ellipsis (**...**) button next to the property field, and in the **Select variables** dialog box, select the `ExcelFileExists` variable.</span></span>  
  
4.  <span data-ttu-id="ba65c-153">Cliquez sur **Modifier le script** pour ouvrir l’éditeur de script.</span><span class="sxs-lookup"><span data-stu-id="ba65c-153">Click **Edit Script** to open the script editor.</span></span>  
  
5.  <span data-ttu-id="ba65c-154">Ajoutez une instruction `Imports` pour l'espace de noms `System.IO` au début du fichier de script.</span><span class="sxs-lookup"><span data-stu-id="ba65c-154">Add an `Imports` statement for the `System.IO` namespace at the top of the script file.</span></span>  
  
6.  <span data-ttu-id="ba65c-155">Ajoutez le code ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="ba65c-155">Add the following code.</span></span>  
  
### <a name="example-1-code"></a><span data-ttu-id="ba65c-156">Code de l’exemple 1</span><span class="sxs-lookup"><span data-stu-id="ba65c-156">Example 1 Code</span></span>  
  
```vb  
Public Class ScriptMain  
  Public Sub Main()  
    Dim fileToTest As String  
  
    fileToTest = Dts.Variables("ExcelFile").Value.ToString  
    If File.Exists(fileToTest) Then  
      Dts.Variables("ExcelFileExists").Value = True  
    Else  
      Dts.Variables("ExcelFileExists").Value = False  
    End If  
  
    Dts.TaskResult = ScriptResults.Success  
  End Sub  
End Class  
```  
  
```csharp  
public class ScriptMain  
{  
  public void Main()  
  {  
    string fileToTest;  
  
    fileToTest = Dts.Variables["ExcelFile"].Value.ToString();  
    if (File.Exists(fileToTest))  
    {  
      Dts.Variables["ExcelFileExists"].Value = true;  
    }  
    else  
    {  
      Dts.Variables["ExcelFileExists"].Value = false;  
    }  
  
    Dts.TaskResult = (int)ScriptResults.Success;  
  }  
}  
```  
  
##  <a name="example-2-description-check-whether-an-excel-table-exists"></a><a name="example2"></a> <span data-ttu-id="ba65c-157">Description de l’exemple 2 : vérifier si une table Excel existe</span><span class="sxs-lookup"><span data-stu-id="ba65c-157">Example 2 Description: Check Whether an Excel Table Exists</span></span>  
 <span data-ttu-id="ba65c-158">Cet exemple détermine si la feuille de calcul ou la plage nommée Excel spécifiée dans la variable `ExcelTable` existe dans le fichier de classeur Excel spécifié dans la variable `ExcelFile`, puis définit la valeur booléenne de la variable `ExcelTableExists` sur le résultat.</span><span class="sxs-lookup"><span data-stu-id="ba65c-158">This example determines whether the Excel worksheet or named range specified in the `ExcelTable` variable exists in the Excel workbook file specified in the `ExcelFile` variable, and then sets the Boolean value of the `ExcelTableExists` variable to the result.</span></span> <span data-ttu-id="ba65c-159">Vous pouvez utiliser cette valeur booléenne pour créer une branche dans le flux de travail du package.</span><span class="sxs-lookup"><span data-stu-id="ba65c-159">You can use this Boolean value for branching in the workflow of the package.</span></span>  
  
#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="ba65c-160">Pour configurer cet exemple de tâche de script</span><span class="sxs-lookup"><span data-stu-id="ba65c-160">To configure this Script Task example</span></span>  
  
1.  <span data-ttu-id="ba65c-161">Ajoutez une nouvelle tâche de script au package et remplacez son nom par `ExcelTableExists` .</span><span class="sxs-lookup"><span data-stu-id="ba65c-161">Add a new Script task to the package and change its name to `ExcelTableExists`.</span></span>  
  
2.  <span data-ttu-id="ba65c-162">Dans l’**Éditeur de tâche de script**, sous l’onglet **Script**, cliquez sur **ReadOnlyVariables** et entrez la valeur de la propriété en utilisant l’une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="ba65c-162">In the **Script Task Editor**, on the **Script** tab, click **ReadOnlyVariables** and enter the property value using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="ba65c-163">Tapez `ExcelTable` et `ExcelFile` séparez-les par des virgules`.`</span><span class="sxs-lookup"><span data-stu-id="ba65c-163">Type `ExcelTable` and `ExcelFile` separated by commas`.`</span></span>  
  
         <span data-ttu-id="ba65c-164">-ou-</span><span class="sxs-lookup"><span data-stu-id="ba65c-164">-or-</span></span>  
  
    -   <span data-ttu-id="ba65c-165">Cliquez sur le bouton des points de suspension (**...**) en regard du champ de propriété, puis dans la boîte de dialogue **Sélectionner des variables** , sélectionnez les `ExcelTable` `ExcelFile` variables et.</span><span class="sxs-lookup"><span data-stu-id="ba65c-165">Click the ellipsis (**...**) button next to the property field, and in the **Select variables** dialog box, select the `ExcelTable` and `ExcelFile` variables.</span></span>  
  
3.  <span data-ttu-id="ba65c-166">Cliquez sur **ReadWriteVariables** et entrez la valeur de propriété à l’aide de l’une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="ba65c-166">Click **ReadWriteVariables** and enter the property value using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="ba65c-167">Tapez `ExcelTableExists`.</span><span class="sxs-lookup"><span data-stu-id="ba65c-167">Type `ExcelTableExists`.</span></span>  
  
         <span data-ttu-id="ba65c-168">-ou-</span><span class="sxs-lookup"><span data-stu-id="ba65c-168">-or-</span></span>  
  
    -   <span data-ttu-id="ba65c-169">Cliquez sur le bouton de sélection (**...**) en regard du champ de propriété, puis dans la boîte de dialogue **Sélectionner des variables** , sélectionnez la `ExcelTableExists` variable.</span><span class="sxs-lookup"><span data-stu-id="ba65c-169">Click the ellipsis (**...**) button next to the property field, and in the **Select variables** dialog box, select the `ExcelTableExists` variable.</span></span>  
  
4.  <span data-ttu-id="ba65c-170">Cliquez sur **Modifier le script** pour ouvrir l’éditeur de script.</span><span class="sxs-lookup"><span data-stu-id="ba65c-170">Click **Edit Script** to open the script editor.</span></span>  
  
5.  <span data-ttu-id="ba65c-171">Ajoutez une référence à l'assembly `System.Xml` dans le projet de script.</span><span class="sxs-lookup"><span data-stu-id="ba65c-171">Add a reference to the `System.Xml` assembly in the script project.</span></span>  
  
6.  <span data-ttu-id="ba65c-172">Ajoutez des instructions `Imports` pour les espaces de noms `System.IO` et `System.Data.OleDb` au début du fichier de script.</span><span class="sxs-lookup"><span data-stu-id="ba65c-172">Add `Imports` statements for the `System.IO` and `System.Data.OleDb` namespaces at the top of the script file.</span></span>  
  
7.  <span data-ttu-id="ba65c-173">Ajoutez le code ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="ba65c-173">Add the following code.</span></span>  
  
### <a name="example-2-code"></a><span data-ttu-id="ba65c-174">Code de l’exemple 2</span><span class="sxs-lookup"><span data-stu-id="ba65c-174">Example 2 Code</span></span>  
  
```vb  
Public Class ScriptMain  
  Public Sub Main()  
    Dim fileToTest As String  
    Dim tableToTest As String  
    Dim connectionString As String  
    Dim excelConnection As OleDbConnection  
    Dim excelTables As DataTable  
    Dim excelTable As DataRow  
    Dim currentTable As String  
  
    fileToTest = Dts.Variables("ExcelFile").Value.ToString  
    tableToTest = Dts.Variables("ExcelTable").Value.ToString  
  
    Dts.Variables("ExcelTableExists").Value = False  
    If File.Exists(fileToTest) Then  
      connectionString = "Provider=Microsoft.Jet.OLEDB.4.0;" & _  
        "Data Source=" & fileToTest & _  
        ";Extended Properties=Excel 8.0"  
      excelConnection = New OleDbConnection(connectionString)  
      excelConnection.Open()  
      excelTables = excelConnection.GetSchema("Tables")  
      For Each excelTable In excelTables.Rows  
        currentTable = excelTable.Item("TABLE_NAME").ToString  
        If currentTable = tableToTest Then  
          Dts.Variables("ExcelTableExists").Value = True  
        End If  
      Next  
    End If  
  
    Dts.TaskResult = ScriptResults.Success  
  End Sub  
End Class  
```  
  
```csharp  
public class ScriptMain  
{  
    public void Main()  
        {  
            string fileToTest;  
            string tableToTest;  
            string connectionString;  
            OleDbConnection excelConnection;  
            DataTable excelTables;  
            string currentTable;  
  
            fileToTest = Dts.Variables["ExcelFile"].Value.ToString();  
            tableToTest = Dts.Variables["ExcelTable"].Value.ToString();  
  
            Dts.Variables["ExcelTableExists"].Value = false;  
            if (File.Exists(fileToTest))  
            {  
                connectionString = "Provider=Microsoft.Jet.OLEDB.4.0;" +  
                "Data Source=" + fileToTest + ";Extended Properties=Excel 8.0";  
                excelConnection = new OleDbConnection(connectionString);  
                excelConnection.Open();  
                excelTables = excelConnection.GetSchema("Tables");  
                foreach (DataRow excelTable in excelTables.Rows)  
                {  
                    currentTable = excelTable["TABLE_NAME"].ToString();  
                    if (currentTable == tableToTest)  
                    {  
                        Dts.Variables["ExcelTableExists"].Value = true;  
                    }  
                }  
            }  
  
            Dts.TaskResult = (int)ScriptResults.Success;  
  
        }  
}  
```  
  
##  <a name="example-3-description-get-a-list-of-excel-files-in-a-folder"></a><a name="example3"></a> <span data-ttu-id="ba65c-175">Description de l’exemple 3 : obtenir la liste des fichiers Excel contenus dans un dossier</span><span class="sxs-lookup"><span data-stu-id="ba65c-175">Example 3 Description: Get a List of Excel Files in a Folder</span></span>  
 <span data-ttu-id="ba65c-176">Cet exemple remplit un tableau à l'aide de la liste des fichiers Excel détectés dans le dossier spécifié dans la valeur de la variable `ExcelFolder`, puis copie le tableau dans la variable `ExcelFiles`.</span><span class="sxs-lookup"><span data-stu-id="ba65c-176">This example fills an array with the list of Excel files found in the folder specified in the value of the `ExcelFolder` variable, and then copies the array into the `ExcelFiles` variable.</span></span> <span data-ttu-id="ba65c-177">Vous pouvez utiliser l'énumérateur Foreach à partir d'une variable pour parcourir les fichiers inclus dans le tableau.</span><span class="sxs-lookup"><span data-stu-id="ba65c-177">You can use the Foreach from Variable enumerator to iterate over the files in the array.</span></span>  
  
#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="ba65c-178">Pour configurer cet exemple de tâche de script</span><span class="sxs-lookup"><span data-stu-id="ba65c-178">To configure this Script Task example</span></span>  
  
1.  <span data-ttu-id="ba65c-179">Ajoutez une nouvelle tâche de script au package et remplacez son nom par **GetExcelFiles**.</span><span class="sxs-lookup"><span data-stu-id="ba65c-179">Add a new Script task to the package and change its name to **GetExcelFiles**.</span></span>  
  
2.  <span data-ttu-id="ba65c-180">Ouvrez l’**Éditeur de tâche de script**, puis sous l’onglet **Script**, cliquez sur **ReadOnlyVariables** et entrez la valeur de la propriété en utilisant l’une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="ba65c-180">Open the **Script Task Editor**, on the **Script** tab, click **ReadOnlyVariables** and enter the property value using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="ba65c-181">Tapez `ExcelFolder`.</span><span class="sxs-lookup"><span data-stu-id="ba65c-181">Type `ExcelFolder`</span></span>  
  
         <span data-ttu-id="ba65c-182">-ou-</span><span class="sxs-lookup"><span data-stu-id="ba65c-182">-or-</span></span>  
  
    -   <span data-ttu-id="ba65c-183">Cliquez sur le bouton des points de suspension (**...**) en regard du champ de propriété, puis dans la boîte de dialogue **Sélectionner des variables** , sélectionnez la variable ExcelFolder.</span><span class="sxs-lookup"><span data-stu-id="ba65c-183">Click the ellipsis (**...**) button next to the property field, and in the **Select variables** dialog box, select the ExcelFolder variable.</span></span>  
  
3.  <span data-ttu-id="ba65c-184">Cliquez sur **ReadWriteVariables** et entrez la valeur de propriété à l’aide de l’une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="ba65c-184">Click **ReadWriteVariables** and enter the property value using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="ba65c-185">Tapez `ExcelFiles`.</span><span class="sxs-lookup"><span data-stu-id="ba65c-185">Type `ExcelFiles`.</span></span>  
  
         <span data-ttu-id="ba65c-186">-ou-</span><span class="sxs-lookup"><span data-stu-id="ba65c-186">-or-</span></span>  
  
    -   <span data-ttu-id="ba65c-187">Cliquez sur le bouton des points de suspension (**...**) en regard du champ de propriété, puis dans la boîte de dialogue **Sélectionner des variables** , sélectionnez la variable EXCELFiles.</span><span class="sxs-lookup"><span data-stu-id="ba65c-187">Click the ellipsis (**...**) button next to the property field, and in the **Select variables** dialog box, select the ExcelFiles variable.</span></span>  
  
4.  <span data-ttu-id="ba65c-188">Cliquez sur **Modifier le script** pour ouvrir l’éditeur de script.</span><span class="sxs-lookup"><span data-stu-id="ba65c-188">Click **Edit Script** to open the script editor.</span></span>  
  
5.  <span data-ttu-id="ba65c-189">Ajoutez une instruction `Imports` pour l'espace de noms `System.IO` au début du fichier de script.</span><span class="sxs-lookup"><span data-stu-id="ba65c-189">Add an `Imports` statement for the `System.IO` namespace at the top of the script file.</span></span>  
  
6.  <span data-ttu-id="ba65c-190">Ajoutez le code ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="ba65c-190">Add the following code.</span></span>  
  
### <a name="example-3-code"></a><span data-ttu-id="ba65c-191">Code de l’exemple 3</span><span class="sxs-lookup"><span data-stu-id="ba65c-191">Example 3 Code</span></span>  
  
```vb  
Public Class ScriptMain  
  Public Sub Main()  
    Const FILE_PATTERN As String = "*.xls"  
  
    Dim excelFolder As String  
    Dim excelFiles As String()  
  
    excelFolder = Dts.Variables("ExcelFolder").Value.ToString  
    excelFiles = Directory.GetFiles(excelFolder, FILE_PATTERN)  
  
    Dts.Variables("ExcelFiles").Value = excelFiles  
  
    Dts.TaskResult = ScriptResults.Success  
  End Sub  
End Class  
```  
  
```csharp  
public class ScriptMain  
{  
  public void Main()  
  {  
    const string FILE_PATTERN = "*.xls";  
  
    string excelFolder;  
    string[] excelFiles;  
  
    excelFolder = Dts.Variables["ExcelFolder"].Value.ToString();  
    excelFiles = Directory.GetFiles(excelFolder, FILE_PATTERN);  
  
    Dts.Variables["ExcelFiles"].Value = excelFiles;  
  
    Dts.TaskResult = (int)ScriptResults.Success;  
  }  
}  
```  
  
### <a name="alternate-solution"></a><span data-ttu-id="ba65c-192">Autre solution</span><span class="sxs-lookup"><span data-stu-id="ba65c-192">Alternate Solution</span></span>  
 <span data-ttu-id="ba65c-193">Au lieu d'utiliser une tâche de script pour dresser la liste des fichiers Excel dans un tableau, vous pouvez également utiliser l'énumérateur ForEach File pour parcourir tous les fichiers Excel inclus dans un dossier.</span><span class="sxs-lookup"><span data-stu-id="ba65c-193">Instead of using a Script task to gather a list of Excel files into an array, you can also use the ForEach File enumerator to iterate over all the Excel files in a folder.</span></span> <span data-ttu-id="ba65c-194">Pour plus d’informations, consultez [Effectuer une boucle dans des fichiers et des tables Excel en utilisant un conteneur de boucles Foreach](../control-flow/foreach-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="ba65c-194">For more information, see [Loop through Excel Files and Tables by Using a Foreach Loop Container](../control-flow/foreach-loop-container.md).</span></span>  
  
##  <a name="example-4-description-get-a-list-of-tables-in-an-excel-file"></a><a name="example4"></a> <span data-ttu-id="ba65c-195">Description de l’exemple 4 : obtenir la liste des tables contenues dans un fichier Excel</span><span class="sxs-lookup"><span data-stu-id="ba65c-195">Example 4 Description: Get a List of Tables in an Excel File</span></span>  
 <span data-ttu-id="ba65c-196">Cet exemple remplit un tableau à l'aide de la liste des feuilles de calcul et plages nommées détectées dans le fichier de classeur Excel spécifié par la valeur de la variable `ExcelFile`, puis copie le tableau dans la variable `ExcelTables`.</span><span class="sxs-lookup"><span data-stu-id="ba65c-196">This example fills an array with the list of worksheets and named ranges found in the Excel workbook file specified by the value of the `ExcelFile` variable, and then copies the array into the `ExcelTables` variable.</span></span> <span data-ttu-id="ba65c-197">Vous pouvez utiliser l'énumérateur Foreach à partir d'une variable pour parcourir les tables incluses dans le tableau.</span><span class="sxs-lookup"><span data-stu-id="ba65c-197">You can use the Foreach from Variable Enumerator to iterate over the tables in the array.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ba65c-198">La liste des tableaux d'un classeur Excel comprend à la fois les feuilles de calcul (affectées du suffixe $) et les plages nommées.</span><span class="sxs-lookup"><span data-stu-id="ba65c-198">The list of tables in an Excel workbook includes both worksheets (which have the $ suffix) and named ranges.</span></span> <span data-ttu-id="ba65c-199">Si vous devez filtrer la liste uniquement pour obtenir uniquement les feuilles de calcul ou les plages nommées, vous pouvez être amené à ajouter du code supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="ba65c-199">If you have to filter the list for only worksheets or only named ranges, you may have to add additional code for this purpose.</span></span>  
  
#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="ba65c-200">Pour configurer cet exemple de tâche de script</span><span class="sxs-lookup"><span data-stu-id="ba65c-200">To configure this Script Task example</span></span>  
  
1.  <span data-ttu-id="ba65c-201">Ajoutez une nouvelle tâche de script au package et remplacez son nom par **GetExcelTables**.</span><span class="sxs-lookup"><span data-stu-id="ba65c-201">Add a new Script task to the package and change its name to **GetExcelTables**.</span></span>  
  
2.  <span data-ttu-id="ba65c-202">Ouvrez l’**Éditeur de tâche de script**, puis sous l’onglet **Script**, cliquez sur **ReadOnlyVariables** et entrez la valeur de la propriété en utilisant l’une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="ba65c-202">Open the **Script Task Editor**, on the **Script** tab, click **ReadOnlyVariables** and enter the property value using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="ba65c-203">Tapez `ExcelFile`.</span><span class="sxs-lookup"><span data-stu-id="ba65c-203">Type `ExcelFile`.</span></span>  
  
         <span data-ttu-id="ba65c-204">-ou-</span><span class="sxs-lookup"><span data-stu-id="ba65c-204">-or-</span></span>  
  
    -   <span data-ttu-id="ba65c-205">Cliquez sur le bouton des points de suspension (**...**) en regard du champ de propriété, puis dans la boîte de dialogue **Sélectionner des variables** , sélectionnez la variable ExcelFile.</span><span class="sxs-lookup"><span data-stu-id="ba65c-205">Click the ellipsis (**...**) button next to the property field, and in the **Select variables** dialog box, select the ExcelFile variable.</span></span>  
  
3.  <span data-ttu-id="ba65c-206">Cliquez sur **ReadWriteVariables** et entrez la valeur de propriété à l’aide de l’une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="ba65c-206">Click **ReadWriteVariables** and enter the property value using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="ba65c-207">Tapez `ExcelTables`.</span><span class="sxs-lookup"><span data-stu-id="ba65c-207">Type `ExcelTables`.</span></span>  
  
         <span data-ttu-id="ba65c-208">-ou-</span><span class="sxs-lookup"><span data-stu-id="ba65c-208">-or-</span></span>  
  
    -   <span data-ttu-id="ba65c-209">Cliquez sur le bouton de sélection (**...**) en regard du champ de propriété, puis dans la boîte de dialogue **Sélectionner des variables** , sélectionnez ExcelTablesvariable.</span><span class="sxs-lookup"><span data-stu-id="ba65c-209">Click the ellipsis (**...**) button next to the property field, and in the **Select variables** dialog box, select the ExcelTablesvariable.</span></span>  
  
4.  <span data-ttu-id="ba65c-210">Cliquez sur **Modifier le script** pour ouvrir l’éditeur de script.</span><span class="sxs-lookup"><span data-stu-id="ba65c-210">Click **Edit Script** to open the script editor.</span></span>  
  
5.  <span data-ttu-id="ba65c-211">Ajoutez une référence à l'espace de noms `System.Xml` dans le projet de script.</span><span class="sxs-lookup"><span data-stu-id="ba65c-211">Add a reference to the `System.Xml` namespace in the script project.</span></span>  
  
6.  <span data-ttu-id="ba65c-212">Ajoutez une instruction `Imports` pour l'espace de noms `System.Data.OleDb` au début du fichier de script.</span><span class="sxs-lookup"><span data-stu-id="ba65c-212">Add an `Imports` statement for the `System.Data.OleDb` namespace at the top of the script file.</span></span>  
  
7.  <span data-ttu-id="ba65c-213">Ajoutez le code ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="ba65c-213">Add the following code.</span></span>  
  
### <a name="example-4-code"></a><span data-ttu-id="ba65c-214">Code de l'exemple 4</span><span class="sxs-lookup"><span data-stu-id="ba65c-214">Example 4 Code</span></span>  
  
```vb  
Public Class ScriptMain  
  Public Sub Main()  
    Dim excelFile As String  
    Dim connectionString As String  
    Dim excelConnection As OleDbConnection  
    Dim tablesInFile As DataTable  
    Dim tableCount As Integer = 0  
    Dim tableInFile As DataRow  
    Dim currentTable As String  
    Dim tableIndex As Integer = 0  
  
    Dim excelTables As String()  
  
    excelFile = Dts.Variables("ExcelFile").Value.ToString  
    connectionString = "Provider=Microsoft.Jet.OLEDB.4.0;" & _  
        "Data Source=" & excelFile & _  
        ";Extended Properties=Excel 8.0"  
    excelConnection = New OleDbConnection(connectionString)  
    excelConnection.Open()  
    tablesInFile = excelConnection.GetSchema("Tables")  
    tableCount = tablesInFile.Rows.Count  
    ReDim excelTables(tableCount - 1)  
    For Each tableInFile In tablesInFile.Rows  
      currentTable = tableInFile.Item("TABLE_NAME").ToString  
      excelTables(tableIndex) = currentTable  
      tableIndex += 1  
    Next  
  
    Dts.Variables("ExcelTables").Value = excelTables  
  
    Dts.TaskResult = ScriptResults.Success  
  End Sub  
End Class  
```  
  
```csharp  
public class ScriptMain  
{  
  public void Main()  
        {  
            string excelFile;  
            string connectionString;  
            OleDbConnection excelConnection;  
            DataTable tablesInFile;  
            int tableCount = 0;  
            string currentTable;  
            int tableIndex = 0;  
  
            string[] excelTables = new string[5];  
  
            excelFile = Dts.Variables["ExcelFile"].Value.ToString();  
            connectionString = "Provider=Microsoft.Jet.OLEDB.4.0;" +  
                "Data Source=" + excelFile + ";Extended Properties=Excel 8.0";  
            excelConnection = new OleDbConnection(connectionString);  
            excelConnection.Open();  
            tablesInFile = excelConnection.GetSchema("Tables");  
            tableCount = tablesInFile.Rows.Count;  
  
            foreach (DataRow tableInFile in tablesInFile.Rows)  
            {  
                currentTable = tableInFile["TABLE_NAME"].ToString();  
                excelTables[tableIndex] = currentTable;  
                tableIndex += 1;  
            }  
  
            Dts.Variables["ExcelTables"].Value = excelTables;  
  
            Dts.TaskResult = (int)ScriptResults.Success;  
        }  
}  
```  
  
### <a name="alternate-solution"></a><span data-ttu-id="ba65c-215">Autre solution</span><span class="sxs-lookup"><span data-stu-id="ba65c-215">Alternate Solution</span></span>  
 <span data-ttu-id="ba65c-216">Au lieu d'utiliser une tâche de script pour dresser la liste des tables Excel dans un tableau, vous pouvez également utiliser l'énumérateur d'ensemble de lignes du schéma ADO.NET Foreach pour parcourir toutes les tables (autrement dit, les feuilles de calcul et les plages nommées) contenues dans un fichier de classeur Excel.</span><span class="sxs-lookup"><span data-stu-id="ba65c-216">Instead of using a Script task to gather a list of Excel tables into an array, you can also use the ForEach ADO.NET Schema Rowset Enumerator to iterate over all the tables (that is, worksheets and named ranges) in an Excel workbook file.</span></span> <span data-ttu-id="ba65c-217">Pour plus d’informations, consultez [Effectuer une boucle dans des fichiers et des tables Excel en utilisant un conteneur de boucles Foreach](../control-flow/foreach-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="ba65c-217">For more information, see [Loop through Excel Files and Tables by Using a Foreach Loop Container](../control-flow/foreach-loop-container.md).</span></span>  
  
##  <a name="displaying-the-results-of-the-samples"></a><a name="testing"></a> <span data-ttu-id="ba65c-218">Affichage des résultats des exemples</span><span class="sxs-lookup"><span data-stu-id="ba65c-218">Displaying the Results of the Samples</span></span>  
 <span data-ttu-id="ba65c-219">Si vous avez configuré chacun des exemples de cette rubrique dans le même package, vous pouvez connecter toutes les tâches de script à une tâche de script supplémentaire qui affiche la sortie de tous les exemples.</span><span class="sxs-lookup"><span data-stu-id="ba65c-219">If you have configured each of the examples in this topic in the same package, you can connect all the Script tasks to an additional Script task that displays the output of all the examples.</span></span>  
  
#### <a name="to-configure-a-script-task-to-display-the-output-of-the-examples-in-this-topic"></a><span data-ttu-id="ba65c-220">Pour configurer une tâche de script afin d'afficher la sortie des exemples de cette rubrique</span><span class="sxs-lookup"><span data-stu-id="ba65c-220">To configure a Script task to display the output of the examples in this topic</span></span>  
  
1.  <span data-ttu-id="ba65c-221">Ajoutez une nouvelle tâche de script au package et remplacez son nom par **DisplayResults**.</span><span class="sxs-lookup"><span data-stu-id="ba65c-221">Add a new Script task to the package and change its name to **DisplayResults**.</span></span>  
  
2.  <span data-ttu-id="ba65c-222">Connectez les quatre exemples de tâche de script entre eux, afin que chaque tâche s’exécute une fois que la tâche précédente s’est correctement achevée, puis connectez le quatrième exemple de tâche à la tâche **DisplayResults**.</span><span class="sxs-lookup"><span data-stu-id="ba65c-222">Connect each of the four example Script tasks to one another, so that each task runs after the preceding task completes successfully, and connect the fourth example task to the **DisplayResults** task.</span></span>  
  
3.  <span data-ttu-id="ba65c-223">Ouvrez la tâche **DisplayResults** dans l’**Éditeur de tâche de script**.</span><span class="sxs-lookup"><span data-stu-id="ba65c-223">Open the **DisplayResults** task in the **Script Task Editor**.</span></span>  
  
4.  <span data-ttu-id="ba65c-224">Sous l’onglet **Script**, cliquez sur **ReadOnlyVariables** et utilisez l’une des méthodes suivantes pour ajouter les sept variables répertoriées dans [Configuration d’un package pour tester les exemples](#configuring) :</span><span class="sxs-lookup"><span data-stu-id="ba65c-224">On the **Script** tab, click **ReadOnlyVariables** and use one of the following methods to add all seven variables listed in [Configuring a Package to Test the Samples](#configuring):</span></span>  
  
    -   <span data-ttu-id="ba65c-225">Tapez le nom de chaque variable en les séparant par des virgules.</span><span class="sxs-lookup"><span data-stu-id="ba65c-225">Type the name of each variable separated by commas.</span></span>  
  
         <span data-ttu-id="ba65c-226">-ou-</span><span class="sxs-lookup"><span data-stu-id="ba65c-226">-or-</span></span>  
  
    -   <span data-ttu-id="ba65c-227">Cliquez sur le bouton des points de suspension (**...**) en regard du champ de propriété, puis dans la boîte de dialogue **Sélectionner des variables, sélectionnez** les variables.</span><span class="sxs-lookup"><span data-stu-id="ba65c-227">Click the ellipsis (**...**) button next to the property field, and in the **Select variables** dialog box, selecting the variables.</span></span>  
  
5.  <span data-ttu-id="ba65c-228">Cliquez sur **Modifier le script** pour ouvrir l’éditeur de script.</span><span class="sxs-lookup"><span data-stu-id="ba65c-228">Click **Edit Script** to open the script editor.</span></span>  
  
6.  <span data-ttu-id="ba65c-229">Ajoutez des instructions `Imports` pour les espaces de noms `Microsoft.VisualBasic` et `System.Windows.Forms` au début du fichier de script.</span><span class="sxs-lookup"><span data-stu-id="ba65c-229">Add `Imports` statements for the `Microsoft.VisualBasic` and `System.Windows.Forms` namespaces at the top of the script file.</span></span>  
  
7.  <span data-ttu-id="ba65c-230">Ajoutez le code ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="ba65c-230">Add the following code.</span></span>  
  
8.  <span data-ttu-id="ba65c-231">Exécutez le package et examinez les résultats qui s'affichent dans un message.</span><span class="sxs-lookup"><span data-stu-id="ba65c-231">Run the package and examine the results displayed in a message box.</span></span>  
  
### <a name="code-to-display-the-results"></a><span data-ttu-id="ba65c-232">Code permettant d'afficher les résultats</span><span class="sxs-lookup"><span data-stu-id="ba65c-232">Code to Display the Results</span></span>  
  
```vb  
Public Class ScriptMain  
  Public Sub Main()  
    Const EOL As String = ControlChars.CrLf  
  
    Dim results As String  
    Dim filesInFolder As String()  
    Dim fileInFolder As String  
    Dim tablesInFile As String()  
    Dim tableInFile As String  
  
    results = _  
      "Final values of variables:" & EOL & _  
      "ExcelFile: " & Dts.Variables("ExcelFile").Value.ToString & EOL & _  
      "ExcelFileExists: " & Dts.Variables("ExcelFileExists").Value.ToString & EOL & _  
      "ExcelTable: " & Dts.Variables("ExcelTable").Value.ToString & EOL & _  
      "ExcelTableExists: " & Dts.Variables("ExcelTableExists").Value.ToString & EOL & _  
      "ExcelFolder: " & Dts.Variables("ExcelFolder").Value.ToString & EOL & _  
      EOL  
  
    results &= "Excel files in folder: " & EOL  
    filesInFolder = DirectCast(Dts.Variables("ExcelFiles").Value, String())  
    For Each fileInFolder In filesInFolder  
      results &= " " & fileInFolder & EOL  
    Next  
    results &= EOL  
  
    results &= "Excel tables in file: " & EOL  
    tablesInFile = DirectCast(Dts.Variables("ExcelTables").Value, String())  
    For Each tableInFile In tablesInFile  
      results &= " " & tableInFile & EOL  
    Next  
  
    MessageBox.Show(results, "Results", MessageBoxButtons.OK, MessageBoxIcon.Information)  
  
    Dts.TaskResult = ScriptResults.Success  
  End Sub  
End Class  
```  
  
```csharp  
public class ScriptMain  
{  
  public void Main()  
        {  
            const string EOL = "\r";  
  
            string results;  
            string[] filesInFolder;  
            //string fileInFolder;  
            string[] tablesInFile;  
            //string tableInFile;  
  
            results = "Final values of variables:" + EOL + "ExcelFile: " + Dts.Variables["ExcelFile"].Value.ToString() + EOL + "ExcelFileExists: " + Dts.Variables["ExcelFileExists"].Value.ToString() + EOL + "ExcelTable: " + Dts.Variables["ExcelTable"].Value.ToString() + EOL + "ExcelTableExists: " + Dts.Variables["ExcelTableExists"].Value.ToString() + EOL + "ExcelFolder: " + Dts.Variables["ExcelFolder"].Value.ToString() + EOL + EOL;  
  
            results += "Excel files in folder: " + EOL;  
            filesInFolder = (string[])(Dts.Variables["ExcelFiles"].Value);  
            foreach (string fileInFolder in filesInFolder)  
            {  
                results += " " + fileInFolder + EOL;  
            }  
            results += EOL;  
  
            results += "Excel tables in file: " + EOL;  
            tablesInFile = (string[])(Dts.Variables["ExcelTables"].Value);  
            foreach (string tableInFile in tablesInFile)  
            {  
                results += " " + tableInFile + EOL;  
            }  
  
            MessageBox.Show(results, "Results", MessageBoxButtons.OK, MessageBoxIcon.Information);  
  
            Dts.TaskResult = (int)ScriptResults.Success;  
        }  
}  
```  
  
<span data-ttu-id="ba65c-233">![Icône de Integration Services (petite)](../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="ba65c-233">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="ba65c-234">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="ba65c-234">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="ba65c-235">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="ba65c-235">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="ba65c-236">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="ba65c-236">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba65c-237">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ba65c-237">See Also</span></span>  
 <span data-ttu-id="ba65c-238">[Gestionnaire de connexions Excel](../connection-manager/excel-connection-manager.md) </span><span class="sxs-lookup"><span data-stu-id="ba65c-238">[Excel Connection Manager](../connection-manager/excel-connection-manager.md) </span></span>  
 [<span data-ttu-id="ba65c-239">Effectuer une boucle dans des fichiers et des tables Excel en utilisant un conteneur de boucles Foreach</span><span class="sxs-lookup"><span data-stu-id="ba65c-239">Loop through Excel Files and Tables by Using a Foreach Loop Container</span></span>](../control-flow/foreach-loop-container.md)  
  
  
