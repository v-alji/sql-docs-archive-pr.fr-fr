---
title: Connexion de tâches par programmation | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- tasks [Integration Services], precedence constraints
- precedence constraints [Integration Services], connecting tasks
- constraints [Integration Services]
ms.assetid: 23668e88-cef4-4009-a9cf-38e607eab7a2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5aeeb70ed5741cc7372fdfc63e637fd53d932f91
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604093"
---
# <a name="connecting-tasks-programmatically"></a><span data-ttu-id="fad20-102">Connexion de tâches par programme</span><span class="sxs-lookup"><span data-stu-id="fad20-102">Connecting Tasks Programmatically</span></span>
  <span data-ttu-id="fad20-103">Une contrainte de précédence, représentée dans le modèle objet par la classe <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint>, établit l'ordre dans lequel les objets <xref:Microsoft.SqlServer.Dts.Runtime.Executable> s'exécutent dans un package.</span><span class="sxs-lookup"><span data-stu-id="fad20-103">A precedence constraint, represented in the object model by the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint> class, establishes the order in which <xref:Microsoft.SqlServer.Dts.Runtime.Executable> objects run in a package.</span></span> <span data-ttu-id="fad20-104">La contrainte de précédence permet de rendre l'exécution des conteneurs et des tâches d'un package dépendante du résultat de l'exécution d'une tâche ou d'un conteneur précédent.</span><span class="sxs-lookup"><span data-stu-id="fad20-104">The precedence constraint allows the execution of the containers and tasks in a package to be dependent on the result of the execution of a previous task or container.</span></span> <span data-ttu-id="fad20-105">Les contraintes de précédence sont établies entre des paires d'objets <xref:Microsoft.SqlServer.Dts.Runtime.Executable> en appelant la méthode <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraints.Add%2A> de la collection <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraints> sur l'objet conteneur.</span><span class="sxs-lookup"><span data-stu-id="fad20-105">Precedence constraints are established between pairs of <xref:Microsoft.SqlServer.Dts.Runtime.Executable> objects by calling the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraints.Add%2A> method of the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraints> collection on the container object.</span></span> <span data-ttu-id="fad20-106">Après avoir créé une contrainte entre deux objets exécutables, vous devez définir la propriété <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Value%2A> pour établir les critères d'exécution du deuxième objet exécutable défini dans la contrainte.</span><span class="sxs-lookup"><span data-stu-id="fad20-106">After you create a constraint between two executable objects, you set the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Value%2A> property to establish the criteria for executing the second executable defined in the constraint.</span></span>  
  
 <span data-ttu-id="fad20-107">Vous pouvez utiliser une contrainte ou une expression dans une seule contrainte de précédence, en fonction de la valeur spécifiée pour la propriété <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.EvalOp%2A>, tel que décrit dans le tableau suivant :</span><span class="sxs-lookup"><span data-stu-id="fad20-107">You can use both a constraint and an expression in a single precedence constraint, depending on the value that you specify for the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.EvalOp%2A> property, as described in the following table:</span></span>  
  
|<span data-ttu-id="fad20-108">Valeur de la propriété EvalOp</span><span class="sxs-lookup"><span data-stu-id="fad20-108">Value of the EvalOp property</span></span>|<span data-ttu-id="fad20-109">Description</span><span class="sxs-lookup"><span data-stu-id="fad20-109">Description</span></span>|  
|----------------------------------|-----------------|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DTSPrecedenceEvalOp.Constraint>|<span data-ttu-id="fad20-110">Spécifie que le résultat de l'exécution détermine l'exécution de la tâche ou du conteneur contraint.</span><span class="sxs-lookup"><span data-stu-id="fad20-110">Specifies that the execution outcome determines whether the constrained container or task runs.</span></span> <span data-ttu-id="fad20-111">Affectez la valeur souhaitée de l'énumération <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Value%2A> à la propriété <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint> de <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult>.</span><span class="sxs-lookup"><span data-stu-id="fad20-111">Set the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Value%2A> property of the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint> to the desired value from the <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> enumeration.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DTSPrecedenceEvalOp.Expression>|<span data-ttu-id="fad20-112">Spécifie que la valeur d'une expression détermine l'exécution de la tâche ou du conteneur contraint.</span><span class="sxs-lookup"><span data-stu-id="fad20-112">Specifies that the value of an expression determines whether the constrained container or task runs.</span></span> <span data-ttu-id="fad20-113">Définissez la propriété <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Expression%2A> de <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint>.</span><span class="sxs-lookup"><span data-stu-id="fad20-113">Set the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Expression%2A> property of the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint>.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DTSPrecedenceEvalOp.ExpressionAndConstraint>|<span data-ttu-id="fad20-114">Spécifie que la contrainte doit produire un résultat et que l'expression doit prendre une valeur, pour que la tâche ou le conteneur contraint s'exécute.</span><span class="sxs-lookup"><span data-stu-id="fad20-114">Specifies that the constraint outcome must occur and the expression must evaluate for the constrained container or task to run.</span></span> <span data-ttu-id="fad20-115">Définissez les propriétés <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Value%2A> et <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Expression%2A> de <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint>, et attribuez la valeur `true` à la propriété <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.LogicalAnd%2A>.</span><span class="sxs-lookup"><span data-stu-id="fad20-115">Set both the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Value%2A> and the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Expression%2A> properties of the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint>, and set its <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.LogicalAnd%2A> property to `true`.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DTSPrecedenceEvalOp.ExpressionOrConstraint>|<span data-ttu-id="fad20-116">Spécifie que la contrainte doit produire un résultat ou que l'expression doit prendre une valeur, pour que la tâche ou le conteneur contraint s'exécute.</span><span class="sxs-lookup"><span data-stu-id="fad20-116">Specifies that either the constraint outcome must occur, or the expression must evaluate, for the constrained container or task to run.</span></span> <span data-ttu-id="fad20-117">Définissez les propriétés <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Value%2A> et <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Expression%2A> de <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint>, et attribuez la valeur `false` à la propriété <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.LogicalAnd%2A>.</span><span class="sxs-lookup"><span data-stu-id="fad20-117">Set both the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Value%2A> and the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Expression%2A> properties of the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint>, and set its <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.LogicalAnd%2A> property to `false`.</span></span>|  
  
 <span data-ttu-id="fad20-118">L'exemple de code suivant illustre l'ajout de deux tâches à un package.</span><span class="sxs-lookup"><span data-stu-id="fad20-118">The following code sample demonstrates adding two tasks to a package.</span></span> <span data-ttu-id="fad20-119">Un <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint> est créé entre elles pour empêcher l'exécution de la deuxième tâche tant que la première n'a pas fini de s'exécuter.</span><span class="sxs-lookup"><span data-stu-id="fad20-119">A <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint> is created between them that prevents the second task from running until the first task finishes.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Package p = new Package();  
  
      // Add a File System task.  
      Executable eFileTask1 = p.Executables.Add("STOCK:FileSystemTask");  
      TaskHost thFileHost1 = eFileTask1 as TaskHost;  
  
      // Add a second File System task.  
      Executable eFileTask2 = p.Executables.Add("STOCK:FileSystemTask");  
      TaskHost thFileHost2 = eFileTask2 as TaskHost;  
  
      // Put a precedence constraint between the tasks.  
      // Set the constraint to specify that the second File System task cannot run  
      // until the first File System task finishes.  
      PrecedenceConstraint pcFileTasks =   
        p.PrecedenceConstraints.Add((Executable)thFileHost1, (Executable)thFileHost2);  
      pcFileTasks.Value = DTSExecResult.Completion;  
    }  
  }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    Dim p As Package = New Package()  
    ' Add a File System task.  
    Dim eFileTask1 As Executable = p.Executables.Add("STOCK:FileSystemTask")  
    Dim thFileHost1 As TaskHost = CType(eFileTask1, TaskHost)  
  
    ' Add a second File System task.  
    Dim eFileTask2 As Executable = p.Executables.Add("STOCK:FileSystemTask")  
    Dim thFileHost2 As TaskHost = CType(eFileTask2, TaskHost)  
  
    ' Put a precedence constraint between the tasks.  
    ' Set the constraint to specify that the second File System task cannot run  
    ' until the first File System task finishes.  
    Dim pcFileTasks As PrecedenceConstraint = _  
      p.PrecedenceConstraints.Add(CType(thFileHost1, Executable), CType(thFileHost2, Executable))  
    pcFileTasks.Value = DTSExecResult.Completion  
  
  End Sub  
  
End Module  
```  
  
<span data-ttu-id="fad20-120">![Icône de Integration Services (petite)](../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="fad20-120">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="fad20-121">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="fad20-121">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="fad20-122">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="fad20-122">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="fad20-123">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="fad20-123">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fad20-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fad20-124">See Also</span></span>  
 [<span data-ttu-id="fad20-125">Ajout de la tâche de flux de données par programmation</span><span class="sxs-lookup"><span data-stu-id="fad20-125">Adding the Data Flow Task Programmatically</span></span>](../building-packages-programmatically/adding-the-data-flow-task-programmatically.md)  
  
  
