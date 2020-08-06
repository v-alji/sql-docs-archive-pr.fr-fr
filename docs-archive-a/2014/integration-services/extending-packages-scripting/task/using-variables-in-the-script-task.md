---
title: Utilisation de variables dans la tâche de script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Foreach Loop containers
- Script task [Integration Services], variables
- scripts [Integration Services], variables
- Variables property
- Variable object
- SSIS Script task, variables
- variables [Integration Services], Script task
ms.assetid: 593b5961-4bfa-4ce1-9531-a251c34e89d3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2cd8fee5741c3d0e28e52c8712c3896428a05e8a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710744"
---
# <a name="using-variables-in-the-script-task"></a><span data-ttu-id="e14c6-102">Utilisation de variables dans la tâche de script</span><span class="sxs-lookup"><span data-stu-id="e14c6-102">Using Variables in the Script Task</span></span>
  <span data-ttu-id="e14c6-103">Les variables permettent à la tâche de script d'échanger des données avec d'autres objets dans le package.</span><span class="sxs-lookup"><span data-stu-id="e14c6-103">Variables make it possible for the Script task to exchange data with other objects in the package.</span></span> <span data-ttu-id="e14c6-104">Pour plus d’informations, consultez [Variables Integration Services &#40;SSIS&#41;](../../integration-services-ssis-variables.md).</span><span class="sxs-lookup"><span data-stu-id="e14c6-104">For more information, see [Integration Services &#40;SSIS&#41; Variables](../../integration-services-ssis-variables.md).</span></span>  
  
 <span data-ttu-id="e14c6-105">La tâche de script utilise la propriété <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> de l'objet `Dts` pour lire et écrire dans les objets <xref:Microsoft.SqlServer.Dts.Runtime.Variable> du package.</span><span class="sxs-lookup"><span data-stu-id="e14c6-105">The Script task uses the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> property of the `Dts` object to read from and write to <xref:Microsoft.SqlServer.Dts.Runtime.Variable> objects in the package.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e14c6-106">La propriété <xref:Microsoft.SqlServer.Dts.Runtime.Variable.Value%2A> de la classe <xref:Microsoft.SqlServer.Dts.Runtime.Variable> est de type `Object`.</span><span class="sxs-lookup"><span data-stu-id="e14c6-106">The <xref:Microsoft.SqlServer.Dts.Runtime.Variable.Value%2A> property of the <xref:Microsoft.SqlServer.Dts.Runtime.Variable> class is of type `Object`.</span></span> <span data-ttu-id="e14c6-107">Comme `Option Strict` est activé dans la tâche de script, vous devez effectuer un cast de la propriété <xref:Microsoft.SqlServer.Dts.Runtime.Variable.Value%2A> en type approprié avant de pouvoir l'utiliser.</span><span class="sxs-lookup"><span data-stu-id="e14c6-107">Because the Script task has `Option Strict` enabled, you must cast the <xref:Microsoft.SqlServer.Dts.Runtime.Variable.Value%2A> property to the appropriate type before you can use it.</span></span>  
  
 <span data-ttu-id="e14c6-108">Vous ajoutez des variables existantes aux listes <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptTask.ReadOnlyVariables%2A> et <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptTask.ReadWriteVariables%2A> dans l’**éditeur de tâche de script** afin qu’elles puissent être utilisées dans le script personnalisé.</span><span class="sxs-lookup"><span data-stu-id="e14c6-108">You add existing variables to the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptTask.ReadOnlyVariables%2A> and <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptTask.ReadWriteVariables%2A> lists in the **Script Task Editor** to make them available to the custom script.</span></span> <span data-ttu-id="e14c6-109">N'oubliez pas que les noms de variables respectent la casse.</span><span class="sxs-lookup"><span data-stu-id="e14c6-109">Keep in mind that variable names are case-sensitive.</span></span> <span data-ttu-id="e14c6-110">Dans le script, vous accédez aux deux types de variables par le biais de la propriété <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> de l'objet `Dts`.</span><span class="sxs-lookup"><span data-stu-id="e14c6-110">Within the script, you access variables of both types through the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> property of the `Dts` object.</span></span> <span data-ttu-id="e14c6-111">Utilisez la propriété `Value` pour lire et écrire des variables individuelles.</span><span class="sxs-lookup"><span data-stu-id="e14c6-111">Use the `Value` property to read from and write to individual variables.</span></span> <span data-ttu-id="e14c6-112">La tâche de script gère de façon transparente le verrouillage pendant que le script lit et modifie les valeurs des variables.</span><span class="sxs-lookup"><span data-stu-id="e14c6-112">The Script task transparently manages locking as the script reads and modifies the values of variables.</span></span>  
  
 <span data-ttu-id="e14c6-113">La méthode <xref:Microsoft.SqlServer.Dts.Runtime.Variables.Contains%2A> de la collection <xref:Microsoft.SqlServer.Dts.Runtime.Variables> retournée par la propriété <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> vous permet de vérifier l'existence d'une variable avant de l'utiliser dans votre code.</span><span class="sxs-lookup"><span data-stu-id="e14c6-113">You can use the <xref:Microsoft.SqlServer.Dts.Runtime.Variables.Contains%2A> method of the <xref:Microsoft.SqlServer.Dts.Runtime.Variables> collection returned by the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> property to check for the existence of a variable before using it in your code.</span></span>  
  
 <span data-ttu-id="e14c6-114">La propriété <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.VariableDispenser%2A> (Dts.VariableDispenser) vous permet également d’utiliser des variables dans la tâche de script.</span><span class="sxs-lookup"><span data-stu-id="e14c6-114">You can also use the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.VariableDispenser%2A> property (Dts.VariableDispenser) to work with variables in the Script task.</span></span> <span data-ttu-id="e14c6-115">Lorsque vous utilisez la propriété <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.VariableDispenser%2A>, vous devez gérer à la fois la sémantique de verrouillage et la conversion des types de données pour les valeurs de variables dans votre propre code.</span><span class="sxs-lookup"><span data-stu-id="e14c6-115">When using the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.VariableDispenser%2A>, you must handle both the locking semantics and the casting of data types for variable values in your own code.</span></span> <span data-ttu-id="e14c6-116">Vous pourriez devoir utiliser la propriété <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.VariableDispenser%2A> à la place de la propriété <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> si vous souhaitez utiliser une variable qui n'est pas disponible au moment de la conception mais qui est créée par programme au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="e14c6-116">You may need to use the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.VariableDispenser%2A> property instead of the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> property if you want to work with a variable that is not available at design time but is created programmatically at run time.</span></span>  
  
## <a name="using-the-script-task-within-a-foreach-loop-container"></a><span data-ttu-id="e14c6-117">Utilisation de la tâche de script dans un conteneur de boucles Foreach</span><span class="sxs-lookup"><span data-stu-id="e14c6-117">Using the Script Task within a Foreach Loop Container</span></span>  
 <span data-ttu-id="e14c6-118">Lorsqu'une tâche de script s'exécute à plusieurs reprises dans un conteneur de boucles Foreach, le script doit généralement utiliser le contenu de l'élément actif dans l'énumérateur.</span><span class="sxs-lookup"><span data-stu-id="e14c6-118">When a Script task runs repeatedly within a Foreach Loop container, the script usually needs to work with the contents of the current item in the enumerator.</span></span> <span data-ttu-id="e14c6-119">Par exemple, lors de l'utilisation d'un énumérateur Foreach File, le script doit connaître le nom du fichier actif ; lors de l'utilisation d'un énumérateur ADO Foreach, le script doit connaître le contenu des colonnes dans la ligne de données en cours.</span><span class="sxs-lookup"><span data-stu-id="e14c6-119">For example, when using a Foreach File enumerator, the script needs to know the current file name; when using a Foreach ADO enumerator, the script needs to know the contents of the columns in the current row of data.</span></span>  
  
 <span data-ttu-id="e14c6-120">Les variables permettent d'établir cette communication entre le conteneur de boucles Foreach et la tâche de script.</span><span class="sxs-lookup"><span data-stu-id="e14c6-120">Variables make this communication between the Foreach Loop container and the Script task possible.</span></span> <span data-ttu-id="e14c6-121">Dans la page **Mappage de variables** de l’**Éditeur de boucle Foreach**, assignez des variables à chaque élément de données qui est retourné par un même élément énuméré.</span><span class="sxs-lookup"><span data-stu-id="e14c6-121">On the **Variable Mappings** page of the **Foreach Loop Editor**, assign variables to each item of data that is returned by a single enumerated item.</span></span> <span data-ttu-id="e14c6-122">Par exemple, un énumérateur Foreach File retourne uniquement un nom de fichier à l'index 0 et ne requiert donc qu'un seul mappage de variables, alors qu'un énumérateur qui retourne plusieurs colonnes de données dans chaque ligne requiert que vous mappiez une variable différente à chaque colonne que vous souhaitez utiliser dans la tâche de script.</span><span class="sxs-lookup"><span data-stu-id="e14c6-122">For example, a Foreach File enumerator returns only a file name at Index 0 and therefore requires only one variable mapping, whereas an enumerator that returns several columns of data in each row requires you to map a different variable to each column that you want to use in the Script task.</span></span>  
  
 <span data-ttu-id="e14c6-123">Une fois que vous avez mappé les éléments énumérés aux variables, vous devez ajouter les variables mappées à la `ReadOnlyVariables` propriété dans la page **script** de l **'éditeur de tâche de script** pour les mettre à la disposition de votre script.</span><span class="sxs-lookup"><span data-stu-id="e14c6-123">After you have mapped enumerated items to variables, then you must add the mapped variables to the `ReadOnlyVariables` property on the **Script** page of the **Script Task Editor** to make them available to your script.</span></span> <span data-ttu-id="e14c6-124">Pour obtenir un exemple de tâche de script dans un conteneur de boucles Foreach qui traite les fichiers image dans un dossier, consultez [Utilisation d’images à l’aide de la tâche de script](../../extending-packages-scripting-task-examples/working-with-images-with-the-script-task.md).</span><span class="sxs-lookup"><span data-stu-id="e14c6-124">For an example of a Script task within a Foreach Loop container that processes the image files in a folder, see [Working with Images with the Script Task](../../extending-packages-scripting-task-examples/working-with-images-with-the-script-task.md).</span></span>  
  
## <a name="variables-example"></a><span data-ttu-id="e14c6-125">Exemple de variables</span><span class="sxs-lookup"><span data-stu-id="e14c6-125">Variables Example</span></span>  
 <span data-ttu-id="e14c6-126">L'exemple suivant montre comment accéder à des variables et les utiliser dans une tâche de script pour déterminer le chemin d'accès du flux de travail du package.</span><span class="sxs-lookup"><span data-stu-id="e14c6-126">The following example demonstrates how to access and use variables in a Script task to determine the path of package workflow.</span></span> <span data-ttu-id="e14c6-127">L’exemple suppose que vous avez créé des variables de type entier nommées et que vous les avez `CustomerCount` `MaxRecordCount` ajoutées à la `ReadOnlyVariables` collection dans l **'éditeur de tâche de script**.</span><span class="sxs-lookup"><span data-stu-id="e14c6-127">The sample assumes that you have created integer variables named `CustomerCount` and `MaxRecordCount` and added them to the `ReadOnlyVariables` collection in the **Script Task Editor**.</span></span> <span data-ttu-id="e14c6-128">La variable `CustomerCount` contient le nombre d'enregistrements de client à importer.</span><span class="sxs-lookup"><span data-stu-id="e14c6-128">The `CustomerCount` variable contains the number of customer records to be imported.</span></span> <span data-ttu-id="e14c6-129">Si sa valeur est supérieure à la valeur de `MaxRecordCount`, la tâche de script signale une défaillance.</span><span class="sxs-lookup"><span data-stu-id="e14c6-129">If its value is greater than the value of `MaxRecordCount`, the Script task reports failure.</span></span> <span data-ttu-id="e14c6-130">Lorsqu'une défaillance se produit en raison du dépassement du seuil `MaxRecordCount`, le chemin d'accès aux erreurs du flux de travail peut implémenter les opérations de nettoyage requises.</span><span class="sxs-lookup"><span data-stu-id="e14c6-130">When a failure occurs because the `MaxRecordCount` threshold has been exceeded, the error path of the workflow can implement any required clean-up.</span></span>  
  
 <span data-ttu-id="e14c6-131">Pour compiler correctement l'exemple, vous devez ajouter une référence à l'assembly Microsoft.SqlServer.ScriptTask.</span><span class="sxs-lookup"><span data-stu-id="e14c6-131">To successfully compile the sample, you need to add a reference to the Microsoft.SqlServer.ScriptTask assembly.</span></span>  
  
```vb  
Public Sub Main()  
  
    Dim customerCount As Integer  
    Dim maxRecordCount As Integer  
  
    If Dts.Variables.Contains("CustomerCount") = True AndAlso _  
        Dts.Variables.Contains("MaxRecordCount") = True Then  
  
        customerCount = _  
            CType(Dts.Variables("CustomerCount").Value, Integer)  
        maxRecordCount = _  
            CType(Dts.Variables("MaxRecordCount").Value, Integer)  
  
    End If  
  
    If customerCount > maxRecordCount Then  
            Dts.TaskResult = ScriptResults.Failure  
    Else  
            Dts.TaskResult = ScriptResults.Success  
    End If  
  
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
        int customerCount;  
        int maxRecordCount;  
  
        if (Dts.Variables.Contains("CustomerCount")==true&&Dts.Variables.Contains("MaxRecordCount")==true)  
  
        {  
            customerCount = (int) Dts.Variables["CustomerCount"].Value;  
            maxRecordCount = (int) Dts.Variables["MaxRecordCount"].Value;  
  
        }  
  
        if (customerCount>maxRecordCount)  
        {  
            Dts.TaskResult = (int)ScriptResults.Failure;  
        }  
        else  
        {  
            Dts.TaskResult = (int)ScriptResults.Success;  
        }  
  
    }  
  
}  
  
```  
  
<span data-ttu-id="e14c6-132">![Icône de Integration Services (petite)](../../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="e14c6-132">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="e14c6-133">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="e14c6-133">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="e14c6-134">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="e14c6-134">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="e14c6-135">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="e14c6-135">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e14c6-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e14c6-136">See Also</span></span>  
 <span data-ttu-id="e14c6-137">[Variables Integration Services &#40;SSIS&#41;](../../integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="e14c6-137">[Integration Services &#40;SSIS&#41; Variables](../../integration-services-ssis-variables.md) </span></span>  
 [<span data-ttu-id="e14c6-138">Utiliser des variables dans des packages</span><span class="sxs-lookup"><span data-stu-id="e14c6-138">Use Variables in Packages</span></span>](../../use-variables-in-packages.md)  
  
  
