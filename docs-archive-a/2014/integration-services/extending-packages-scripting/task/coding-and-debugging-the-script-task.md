---
title: Codage et débogage de la tâche de script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script task [Integration Services], debugging
- SSIS Script task, development environment
- SSIS Script task, debugging
- Script task [Integration Services], development environment
- Script task [Integration Services], coding
- debugging [Integration Services], scripts
- VSTA
- SSIS Script task, coding
ms.assetid: 687c262f-fcab-42e8-92ae-e956f3d92d69
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0f4383469368ac1fe3c70ff82f8c8bb2cf755838
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695855"
---
# <a name="coding-and-debugging-the-script-task"></a><span data-ttu-id="ee4df-102">Codage et débogage de la tâche de script</span><span class="sxs-lookup"><span data-stu-id="ee4df-102">Coding and Debugging the Script Task</span></span>
  <span data-ttu-id="ee4df-103">Après avoir configuré la tâche de script dans l’**éditeur de tâche de script**, vous pouvez écrire votre code personnalisé dans l’environnement de développement de tâche de script.</span><span class="sxs-lookup"><span data-stu-id="ee4df-103">After configuring the Script task in the **Script Task Editor**, you write your custom code in the Script task development environment.</span></span>

## <a name="script-task-development-environment"></a><span data-ttu-id="ee4df-104">Environnement de développement de tâche de script</span><span class="sxs-lookup"><span data-stu-id="ee4df-104">Script Task Development Environment</span></span>
 <span data-ttu-id="ee4df-105">La tâche de script utilise [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] Tools for Applications (VSTA) comme environnement de développement du script proprement dit.</span><span class="sxs-lookup"><span data-stu-id="ee4df-105">The Script task uses [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] Tools for Applications (VSTA) as the development environment for the script itself.</span></span>

 <span data-ttu-id="ee4df-106">Le code de script est écrit dans [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic ou [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#.</span><span class="sxs-lookup"><span data-stu-id="ee4df-106">Script code is written in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic or [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#.</span></span> <span data-ttu-id="ee4df-107">Vous pouvez spécifier le langage de script en définissant la propriété **ScriptLanguage** dans l’**éditeur de tâche de script**.</span><span class="sxs-lookup"><span data-stu-id="ee4df-107">You specify the script language by setting the **ScriptLanguage** property in the **Script Task Editor**.</span></span> <span data-ttu-id="ee4df-108">Si vous préférez utiliser un autre langage de programmation, vous pouvez développer un assembly personnalisé dans le langage de votre choix et appeler ses fonctionnalités à partir du code inclus dans la de script.</span><span class="sxs-lookup"><span data-stu-id="ee4df-108">If you prefer to use another programming language, you can develop a custom assembly in your language of choice and call its functionality from the code in the Script task.</span></span>

 <span data-ttu-id="ee4df-109">Le script que vous créez dans la tâche de script est stocké dans la définition du package.</span><span class="sxs-lookup"><span data-stu-id="ee4df-109">The script that you create in the Script task is stored in the package definition.</span></span> <span data-ttu-id="ee4df-110">Aucun fichier de script distinct n'est créé.</span><span class="sxs-lookup"><span data-stu-id="ee4df-110">There is no separate script file.</span></span> <span data-ttu-id="ee4df-111">Par conséquent, l'utilisation de la tâche de script n'affecte pas le déploiement de package.</span><span class="sxs-lookup"><span data-stu-id="ee4df-111">Therefore, the use of the Script task does not affect package deployment.</span></span>

> [!NOTE]
>  <span data-ttu-id="ee4df-112">Lorsque vous concevez le package et déboguez le script, le code de script est écrit temporairement dans un fichier projet.</span><span class="sxs-lookup"><span data-stu-id="ee4df-112">When you design the package and debug the script, the script code is temporarily written to a project file.</span></span> <span data-ttu-id="ee4df-113">Étant donné que le stockage d'informations sensibles dans un fichier représente un risque potentiel en termes de sécurité, nous vous recommandons de ne pas inclure d'informations sensibles, telles que des mots de passe, dans le code de script.</span><span class="sxs-lookup"><span data-stu-id="ee4df-113">Because storing sensitive information in a file is a potential security risk, we recommend that you do not include sensitive information such as passwords in the script code.</span></span>

 <span data-ttu-id="ee4df-114">Par défaut, `Option Strict` est désactivé dans l'environnement de développement intégré.</span><span class="sxs-lookup"><span data-stu-id="ee4df-114">By default, `Option Strict` is disabled in the IDE.</span></span>

## <a name="script-task-project-structure"></a><span data-ttu-id="ee4df-115">Structure du projet de tâche de script</span><span class="sxs-lookup"><span data-stu-id="ee4df-115">Script Task Project Structure</span></span>
 <span data-ttu-id="ee4df-116">Lorsque vous créez ou modifiez le script contenu dans une tâche de script, VSTA ouvre un nouveau projet vide ou rouvre le projet existant.</span><span class="sxs-lookup"><span data-stu-id="ee4df-116">When you create or modify the script that is contained in a Script task, VSTA opens an empty new project or reopens the existing project.</span></span> <span data-ttu-id="ee4df-117">La création de ce projet VSTA n'affecte pas le déploiement du package étant donné que le projet est enregistré à l'intérieur du fichier de package ; la tâche de script ne crée pas de fichiers supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="ee4df-117">The creation of this VSTA project does not affect the deployment of the package, because the project is saved inside the package file; the Script task does not create additional files.</span></span>

### <a name="project-items-and-classes-in-the-script-task-project"></a><span data-ttu-id="ee4df-118">Éléments et classes du projet de tâche de script</span><span class="sxs-lookup"><span data-stu-id="ee4df-118">Project Items and Classes in the Script Task Project</span></span>
 <span data-ttu-id="ee4df-119">Par défaut, le projet de tâche de script affiché dans la fenêtre Explorateur de projets VSTA contient un seul élément, `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="ee4df-119">By default, the Script task project displayed in the VSTA Project Explorer window contains a single item, `ScriptMain`.</span></span> <span data-ttu-id="ee4df-120">L'élément `ScriptMain` contient à son tour une classe unique, également appelée `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="ee4df-120">The `ScriptMain` item, in turn, contains a single class, also named `ScriptMain`.</span></span> <span data-ttu-id="ee4df-121">Les éléments de code inclus dans la classe varient selon le langage de programmation sélectionné pour la tâche de script :</span><span class="sxs-lookup"><span data-stu-id="ee4df-121">The code elements in the class vary depending on the programming language that you selected for the Script task:</span></span>

-   <span data-ttu-id="ee4df-122">Lorsque la tâche de script est configurée pour le [!INCLUDE[vb_orcas_long](../../../includes/vb-orcas-long-md.md)] langage de programmation, la `ScriptMain` classe possède une sous-routine publique, `Main` .</span><span class="sxs-lookup"><span data-stu-id="ee4df-122">When the Script task is configured for the [!INCLUDE[vb_orcas_long](../../../includes/vb-orcas-long-md.md)] programming language, the `ScriptMain` class has a public subroutine, `Main`.</span></span> <span data-ttu-id="ee4df-123">La sous-routine `ScriptMain.Main` est la méthode appelée par le runtime lorsque vous exécutez votre tâche de script.</span><span class="sxs-lookup"><span data-stu-id="ee4df-123">The `ScriptMain.Main` subroutine is the method that the runtime calls when you run your Script task.</span></span>

     <span data-ttu-id="ee4df-124">Par défaut, le seul code figurant dans la sous-routine `Main` d'un nouveau script est la ligne `Dts.TaskResult = ScriptResults.Success`.</span><span class="sxs-lookup"><span data-stu-id="ee4df-124">By default, the only code in the `Main` subroutine of a new script is the line `Dts.TaskResult = ScriptResults.Success`.</span></span> <span data-ttu-id="ee4df-125">Cette ligne informe le runtime que la tâche a été menée à bien.</span><span class="sxs-lookup"><span data-stu-id="ee4df-125">This line informs the runtime that the task was successful in its operation.</span></span> <span data-ttu-id="ee4df-126">La `Dts.TaskResult` propriété est décrite dans [retour des résultats de la tâche de script](../../extending-packages-scripting/task/returning-results-from-the-script-task.md).</span><span class="sxs-lookup"><span data-stu-id="ee4df-126">The `Dts.TaskResult` property is discussed in [Returning Results from the Script Task](../../extending-packages-scripting/task/returning-results-from-the-script-task.md).</span></span>

-   <span data-ttu-id="ee4df-127">Lorsque la tâche de script est configurée pour le langage de programmation Visual C#, la classe `ScriptMain` possède une méthode publique, `Main`.</span><span class="sxs-lookup"><span data-stu-id="ee4df-127">When the Script task is configured for the Visual C# programming language, the `ScriptMain` class has a public method, `Main`.</span></span> <span data-ttu-id="ee4df-128">La méthode est appelée lors de l'exécution de la tâche de script.</span><span class="sxs-lookup"><span data-stu-id="ee4df-128">The method is called when the Script task runs.</span></span>

     <span data-ttu-id="ee4df-129">Par défaut, la méthode `Main` inclut la ligne `Dts.TaskResult = (int)ScriptResults.Success`.</span><span class="sxs-lookup"><span data-stu-id="ee4df-129">By default, the `Main` method includes the line `Dts.TaskResult = (int)ScriptResults.Success`.</span></span> <span data-ttu-id="ee4df-130">Cette ligne informe le runtime que la tâche a été menée à bien.</span><span class="sxs-lookup"><span data-stu-id="ee4df-130">This line informs the runtime that the task was successful in its operation.</span></span>

 <span data-ttu-id="ee4df-131">L'élément `ScriptMain` peut contenir d'autres classes que la classe `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="ee4df-131">The `ScriptMain` item can contain classes other than the `ScriptMain` class.</span></span> <span data-ttu-id="ee4df-132">La tâche de script ne peut accéder qu'aux classes qu'elle héberge.</span><span class="sxs-lookup"><span data-stu-id="ee4df-132">Classes are available only to the Script task in which they reside.</span></span>

 <span data-ttu-id="ee4df-133">Par défaut, l'élément de projet `ScriptMain` contient le code généré automatiquement suivant :</span><span class="sxs-lookup"><span data-stu-id="ee4df-133">By default, the `ScriptMain` project item contains the following autogenerated code.</span></span> <span data-ttu-id="ee4df-134">Le modèle de code fournit également une vue d'ensemble de la tâche de script, ainsi que des informations supplémentaires sur la récupération et la manipulation des objets SSIS, tels que les variables, les événements et les connexions.</span><span class="sxs-lookup"><span data-stu-id="ee4df-134">The code template also provides an overview of the Script task, and additional information on how to retrieve and manipulate SSIS objects, such as variables, events, and connections.</span></span>

```vb
' Microsoft SQL Server Integration Services Script Task
' Write scripts using Microsoft Visual Basic 2008.
' The ScriptMain is the entry point class of the script.

Imports System
Imports System.Data
Imports System.Math
Imports Microsoft.SqlServer.Dts.Runtime.VSTAProxy

<System.AddIn.AddIn("ScriptMain", Version:="1.0", Publisher:="", Description:="")> _
Partial Class ScriptMain

Private Sub ScriptMain_Startup(ByVal sender As Object, ByVal e As System.EventArgs) Handles Me.Startup

End Sub

Private Sub ScriptMain_Shutdown(ByVal sender As Object, ByVal e As System.EventArgs) Handles Me.Shutdown
Try
' Unlock variables from the read-only and read-write variable collection properties
If (Dts.Variables.Count <> 0) Then
Dts.Variables.Unlock()
End If
Catch ex As Exception
        End Try
End Sub

Enum ScriptResults
Success = DTSExecResult.Success
Failure = DTSExecResult.Failure
End Enum

' The execution engine calls this method when the task executes.
' To access the object model, use the Dts property. Connections, variables, events,
' and logging features are available as members of the Dts property as shown in the following examples.
'
' To reference a variable, call Dts.Variables("MyCaseSensitiveVariableName").Value
' To post a log entry, call Dts.Log("This is my log text", 999, Nothing)
' To fire an event, call Dts.Events.FireInformation(99, "test", "hit the help message", "", 0, True)
'
' To use the connections collection use something like the following:
' ConnectionManager cm = Dts.Connections.Add("OLEDB")
' cm.ConnectionString = "Data Source=localhost;Initial Catalog=AdventureWorks;Provider=SQLNCLI10;Integrated Security=SSPI;Auto Translate=False;"
'
' Before returning from this method, set the value of Dts.TaskResult to indicate success or failure.
' 
' To open Help, press F1.

Public Sub Main()
'
' Add your code here
'
Dts.TaskResult = ScriptResults.Success
End Sub

End Class
```

```csharp
/*
   Microsoft SQL Server Integration Services Script Task
   Write scripts using Microsoft Visual C# 2008.
   The ScriptMain is the entry point class of the script.
*/

using System;
using System.Data;
using Microsoft.SqlServer.Dts.Runtime.VSTAProxy;
using System.Windows.Forms;

namespace ST_1bcfdbad36d94f8ba9f23a10375abe53.csproj
{
    [System.AddIn.AddIn("ScriptMain", Version = "1.0", Publisher = "", Description = "")]
    public partial class ScriptMain
    {
        private void ScriptMain_Startup(object sender, EventArgs e)
        {

        }

        private void ScriptMain_Shutdown(object sender, EventArgs e)
        {
            try
            {
                // Unlock variables from the read-only and read-write variable collection properties
                if (Dts.Variables.Count != 0)
                {
                    Dts.Variables.Unlock();
                }
            }
            catch
            {
            }
        }

        #region VSTA generated code
        private void InternalStartup()
        {
            this.Startup += new System.EventHandler(ScriptMain_Startup);
            this.Shutdown += new System.EventHandler(ScriptMain_Shutdown);
        }
        enum ScriptResults
        {
            Success = DTSExecResult.Success,
            Failure = DTSExecResult.Failure
        };

        #endregion

        /*
The execution engine calls this method when the task executes.
To access the object model, use the Dts property. Connections, variables, events,
and logging features are available as members of the Dts property as shown in the following examples.

To reference a variable, call Dts.Variables["MyCaseSensitiveVariableName"].Value;
To post a log entry, call Dts.Log("This is my log text", 999, null);
To fire an event, call Dts.Events.FireInformation(99, "test", "hit the help message", "", 0, true);

To use the connections collection use something like the following:
ConnectionManager cm = Dts.Connections.Add("OLEDB");
cm.ConnectionString = "Data Source=localhost;Initial Catalog=AdventureWorks;Provider=SQLNCLI10;Integrated Security=SSPI;Auto Translate=False;";

Before returning from this method, set the value of Dts.TaskResult to indicate success or failure.

To open Help, press F1.
*/

        public void Main()
        {
            // TODO: Add your code here
            Dts.TaskResult = (int)ScriptResults.Success;
        }
    }
```

### <a name="additional-project-items-in-the-script-task-project"></a><span data-ttu-id="ee4df-135">Autres éléments du projet de tâche de script</span><span class="sxs-lookup"><span data-stu-id="ee4df-135">Additional Project Items in the Script Task Project</span></span>
 <span data-ttu-id="ee4df-136">La tâche de script peut inclure d'autres éléments que l'élément `ScriptMain` par défaut.</span><span class="sxs-lookup"><span data-stu-id="ee4df-136">The Script task project can include items other than the default `ScriptMain` item.</span></span> <span data-ttu-id="ee4df-137">Vous pouvez ajouter des classes, des modules et des fichiers de code au projet.</span><span class="sxs-lookup"><span data-stu-id="ee4df-137">You can add classes, modules, and code files to the project.</span></span> <span data-ttu-id="ee4df-138">Vous pouvez également utiliser des dossiers pour organiser des groupes d'éléments.</span><span class="sxs-lookup"><span data-stu-id="ee4df-138">You can also use folders to organize groups of items.</span></span> <span data-ttu-id="ee4df-139">Tous les éléments que vous ajoutez sont rendus persistants à l'intérieur du package.</span><span class="sxs-lookup"><span data-stu-id="ee4df-139">All the items that you add are persisted inside the package.</span></span>

### <a name="references-in-the-script-task-project"></a><span data-ttu-id="ee4df-140">Références dans le projet de tâche de script</span><span class="sxs-lookup"><span data-stu-id="ee4df-140">References in the Script Task Project</span></span>
 <span data-ttu-id="ee4df-141">Vous pouvez ajouter des références aux assemblys managés en cliquant avec le bouton droit sur le projet de tâche de script dans l’**Explorateur de projets**, puis en cliquant sur **Ajouter une référence**.</span><span class="sxs-lookup"><span data-stu-id="ee4df-141">You can add references to managed assemblies by right-clicking the Script task project in **Project Explorer**, and then clicking **Add Reference**.</span></span> <span data-ttu-id="ee4df-142">Pour plus d’informations, consultez [Référencement d’autres assemblys dans les solutions de script](../referencing-other-assemblies-in-scripting-solutions.md).</span><span class="sxs-lookup"><span data-stu-id="ee4df-142">For more information, see [Referencing Other Assemblies in Scripting Solutions](../referencing-other-assemblies-in-scripting-solutions.md).</span></span>

> [!NOTE]
>  <span data-ttu-id="ee4df-143">Vous pouvez consulter des références de projet dans l’environnement de développement intégré VSTA dans l’**Affichage de classes** ou l’**Explorateur de projets**.</span><span class="sxs-lookup"><span data-stu-id="ee4df-143">You can view project references in the VSTA IDE in **Class View** or in **Project Explorer**.</span></span> <span data-ttu-id="ee4df-144">Vous ouvrez l’une ou l’autre de ces fenêtres à partir du menu **Affichage**.</span><span class="sxs-lookup"><span data-stu-id="ee4df-144">You open either of these windows from the **View** menu.</span></span> <span data-ttu-id="ee4df-145">Vous pouvez ajouter une nouvelle référence à partir du menu **Projet**, de l’**Explorateur de projets** ou d’**Affichage de classes**.</span><span class="sxs-lookup"><span data-stu-id="ee4df-145">You can add a new reference from the **Project** menu, from **Project Explorer**, or from **Class View**.</span></span>

## <a name="interacting-with-the-package-in-the-script-task"></a><span data-ttu-id="ee4df-146">Interaction avec le package dans la tâche de script</span><span class="sxs-lookup"><span data-stu-id="ee4df-146">Interacting with the Package in the Script Task</span></span>
 <span data-ttu-id="ee4df-147">La tâche de script utilise l'objet `Dts` global, qui est une instance de la classe <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel>, ainsi que ses membres, pour interagir avec le package qui la contient et avec le runtime [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ee4df-147">The Script task uses the global `Dts` object, which is an instance of the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel> class, and its members to interact with the containing package and with the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] runtime.</span></span>

 <span data-ttu-id="ee4df-148">Le tableau suivant répertorie les principaux membres publics de la classe <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel>, exposée au code de la tâche de script par le biais de l'objet `Dts` global.</span><span class="sxs-lookup"><span data-stu-id="ee4df-148">The following table lists the principal public members of the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel> class, which is exposed to Script task code through the global `Dts` object.</span></span> <span data-ttu-id="ee4df-149">Les rubriques de cette section examinent en détail l'utilisation de ces membres.</span><span class="sxs-lookup"><span data-stu-id="ee4df-149">The topics in this section discuss the use of these members in more detail.</span></span>

|<span data-ttu-id="ee4df-150">Membre</span><span class="sxs-lookup"><span data-stu-id="ee4df-150">Member</span></span>|<span data-ttu-id="ee4df-151">Objectif</span><span class="sxs-lookup"><span data-stu-id="ee4df-151">Purpose</span></span>|
|------------|-------------|
|<xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Connections%2A>|<span data-ttu-id="ee4df-152">Permet d'accéder aux gestionnaires de connexion définis dans le package.</span><span class="sxs-lookup"><span data-stu-id="ee4df-152">Provides access to connection managers defined in the package.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Events%2A>|<span data-ttu-id="ee4df-153">Fournit une interface d'événements pour permettre à la tâche de script de déclencher des erreurs, des avertissements et des messages d'information.</span><span class="sxs-lookup"><span data-stu-id="ee4df-153">Provides an events interface to let the Script task raise errors, warnings, and informational messages.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.ExecutionValue%2A>|<span data-ttu-id="ee4df-154">Offre un moyen simple de retourner un objet unique au runtime (en plus de `TaskResult`) qui peut également être utilisé pour la création de branche de flux de travail.</span><span class="sxs-lookup"><span data-stu-id="ee4df-154">Provides a simple way to return a single object to the runtime (in addition to the `TaskResult`) that can also be used for workflow branching.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Log%2A>|<span data-ttu-id="ee4df-155">Enregistre des informations, telles que la progression et le résultat d'une tâche, à des modules fournisseurs d'informations activés.</span><span class="sxs-lookup"><span data-stu-id="ee4df-155">Logs information such as task progress and results to enabled log providers.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.TaskResult%2A>|<span data-ttu-id="ee4df-156">Signale le succès ou l'échec de la tâche.</span><span class="sxs-lookup"><span data-stu-id="ee4df-156">Reports the success or failure of the task.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Transaction%2A>|<span data-ttu-id="ee4df-157">Fournit la transaction, le cas échéant, dans laquelle le conteneur de la tâche s'exécute.</span><span class="sxs-lookup"><span data-stu-id="ee4df-157">Provides the transaction, if any, within which the task's container is running.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A>|<span data-ttu-id="ee4df-158">Permet d'accéder aux variables répertoriées dans les propriétés de tâche `ReadOnlyVariables` et `ReadWriteVariables` à utiliser dans le script.</span><span class="sxs-lookup"><span data-stu-id="ee4df-158">Provides access to the variables listed in the `ReadOnlyVariables` and `ReadWriteVariables` task properties for use within the script.</span></span>|

 <span data-ttu-id="ee4df-159">La classe <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel> contient également quelques membres publics que vous n'utiliserez probablement pas.</span><span class="sxs-lookup"><span data-stu-id="ee4df-159">The <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel> class also contains some public members that you will probably not use.</span></span>

|<span data-ttu-id="ee4df-160">Membre</span><span class="sxs-lookup"><span data-stu-id="ee4df-160">Member</span></span>|<span data-ttu-id="ee4df-161">Description</span><span class="sxs-lookup"><span data-stu-id="ee4df-161">Description</span></span>|
|------------|-----------------|
|<xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.VariableDispenser%2A>|<span data-ttu-id="ee4df-162">La propriété <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> fournit un accès plus pratique aux variables.</span><span class="sxs-lookup"><span data-stu-id="ee4df-162">The <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> property provides more convenient access to variables.</span></span> <span data-ttu-id="ee4df-163">Vous pouvez utiliser <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.VariableDispenser%2A>, mais vous devez alors appeler des méthodes de manière explicite pour verrouiller et déverrouiller l'accès en lecture ou en écriture aux variables.</span><span class="sxs-lookup"><span data-stu-id="ee4df-163">Although you can use the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.VariableDispenser%2A>, you must explicitly call methods to lock and unlock variables for reading and writing.</span></span> <span data-ttu-id="ee4df-164">La tâche de script se charge de gérer la sémantique de verrouillage lorsque vous utilisez la propriété <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A>.</span><span class="sxs-lookup"><span data-stu-id="ee4df-164">The Script task handles locking semantics for you when you use the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> property.</span></span>|

## <a name="debugging-the-script-task"></a><span data-ttu-id="ee4df-165">Débogage de la tâche de script</span><span class="sxs-lookup"><span data-stu-id="ee4df-165">Debugging the Script Task</span></span>
 <span data-ttu-id="ee4df-166">Pour déboguer le code dans votre tâche de script, définissez au moins un point d'arrêt dans le code, puis fermez l'environnement de développement intégré VSTA pour exécuter le package dans [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ee4df-166">To debug the code in your Script task, set at least one breakpoint in the code, and then close the VSTA IDE to run the package in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="ee4df-167">Lorsque l'exécution du package entre la tâche de script, l'environnement de développement intégré s'ouvre à nouveau et affiche votre code en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="ee4df-167">When package execution enters the Script task, the VSTA IDE reopens and displays your code in read-only mode.</span></span> <span data-ttu-id="ee4df-168">Lorsque l'exécution atteint le point d'arrêt, vous pouvez examiner les valeurs des variables et exécuter pas à pas le code restant.</span><span class="sxs-lookup"><span data-stu-id="ee4df-168">After execution reaches your breakpoint, you can examine variable values and step through the remaining code.</span></span>

> [!WARNING]
>  <span data-ttu-id="ee4df-169">Vous pouvez déboguer la tâche de script lorsque vous exécutez le package en mode 64 bits.</span><span class="sxs-lookup"><span data-stu-id="ee4df-169">You can debug the Script task when you run the package in 64-bit mode.</span></span>

> [!NOTE]
>  <span data-ttu-id="ee4df-170">Vous devez exécuter le package à déboguer dans votre tâche de script.</span><span class="sxs-lookup"><span data-stu-id="ee4df-170">You must execute the package to debug into your Script task.</span></span> <span data-ttu-id="ee4df-171">Si vous exécutez uniquement la tâche, les points d'arrêt figurant dans le code de tâche de script sont ignorés.</span><span class="sxs-lookup"><span data-stu-id="ee4df-171">If you execute only the individual task, breakpoints in the Script task code are ignored.</span></span>

> [!NOTE]
>  <span data-ttu-id="ee4df-172">Vous ne pouvez pas déboguer une tâche de script si vous l'exécutez dans le cadre d'un package enfant exécuté à partir d'une tâche d'exécution de package.</span><span class="sxs-lookup"><span data-stu-id="ee4df-172">You cannot debug a Script task when you run the Script task as part of a child package that is run from an Execute Package task.</span></span> <span data-ttu-id="ee4df-173">Dans ce cas, les points d'arrêt définis dans la tâche de script dans le package enfant sont ignorés.</span><span class="sxs-lookup"><span data-stu-id="ee4df-173">Breakpoints that you set in the Script task in the child package are disregarded in these circumstances.</span></span> <span data-ttu-id="ee4df-174">Vous pouvez déboguer normalement le package enfant en l'exécutant séparément.</span><span class="sxs-lookup"><span data-stu-id="ee4df-174">You can debug the child package normally by running it separately.</span></span>

> [!NOTE]
>  <span data-ttu-id="ee4df-175">Lorsque vous déboguez un package qui contient plusieurs tâches Script, le débogueur n'en débogue qu'une seule.</span><span class="sxs-lookup"><span data-stu-id="ee4df-175">When you debug a package that contains multiple Script tasks, the debugger debugs one Script task.</span></span> <span data-ttu-id="ee4df-176">Le système peut déboguer une autre tâche Script si le débogueur a terminé, comme dans le cas d'une boucle Foreach ou du conteneur de boucles For.</span><span class="sxs-lookup"><span data-stu-id="ee4df-176">The system can debug another Script task if the debugger completes, as in the case of a Foreach Loop or For Loop container.</span></span>

## <a name="external-resources"></a><span data-ttu-id="ee4df-177">Ressources externes</span><span class="sxs-lookup"><span data-stu-id="ee4df-177">External Resources</span></span>

-   <span data-ttu-id="ee4df-178">Entrée de blog, [VSTA setup and configuration troubles for SSIS 2008 and R2 installations](https://go.microsoft.com/fwlink/?LinkId=215661), sur blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="ee4df-178">Blog entry, [VSTA setup and configuration troubles for SSIS 2008 and R2 installations](https://go.microsoft.com/fwlink/?LinkId=215661), on blogs.msdn.com.</span></span>

<span data-ttu-id="ee4df-179">![Icône de Integration Services (petite)](../../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="ee4df-179">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="ee4df-180">Pour obtenir les téléchargements, articles, exemples et vidéos les plus récents de [!INCLUDE[msCoName](../../../includes/msconame-md.md)], ainsi que les solutions retenues par la communauté informatique, consultez la page [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="ee4df-180">For the latest downloads, articles, samples, and videos from [!INCLUDE[msCoName](../../../includes/msconame-md.md)], as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="ee4df-181">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="ee4df-181">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="ee4df-182">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="ee4df-182">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="ee4df-183">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ee4df-183">See Also</span></span>
 <span data-ttu-id="ee4df-184">[Référencement d’autres assemblys dans des solutions de script](../referencing-other-assemblies-in-scripting-solutions.md) [configuration de la tâche de script dans l’éditeur de tâche de script](configuring-the-script-task-in-the-script-task-editor.md)</span><span class="sxs-lookup"><span data-stu-id="ee4df-184">[Referencing Other Assemblies in Scripting Solutions](../referencing-other-assemblies-in-scripting-solutions.md) [Configuring the Script Task in the Script Task Editor](configuring-the-script-task-in-the-script-task-editor.md)</span></span>


