---
title: Création d’une tâche personnalisée | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- custom tasks [Integration Services], creating
ms.assetid: 42965c09-1782-4cdb-9ce1-216af4c23e0a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f752acad7a442a8e0aad2d24e94938c14195a35d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611175"
---
# <a name="creating-a-custom-task"></a><span data-ttu-id="e2cb6-102">Création d'une tâche personnalisée</span><span class="sxs-lookup"><span data-stu-id="e2cb6-102">Creating a Custom Task</span></span>
  <span data-ttu-id="e2cb6-103">Les étapes de création d'une tâche personnalisée sont semblables aux étapes de création de tout autre objet personnalisé pour [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="e2cb6-103">The steps involved in creating a custom task are similar to the steps for creating any other custom object for [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="e2cb6-104">Créer une classe qui hérite de la classe de base.</span><span class="sxs-lookup"><span data-stu-id="e2cb6-104">Create a new class that inherits from the base class.</span></span> <span data-ttu-id="e2cb6-105">Pour une tâche, la classe de base est [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task).</span><span class="sxs-lookup"><span data-stu-id="e2cb6-105">For a task, the base class is [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task).</span></span>  
  
-   <span data-ttu-id="e2cb6-106">Appliquer l'attribut qui identifie le type d'objet auprès de la classe.</span><span class="sxs-lookup"><span data-stu-id="e2cb6-106">Apply the attribute that identifies the type of object to the class.</span></span> <span data-ttu-id="e2cb6-107">Pour une tâche, l'attribut est <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute>.</span><span class="sxs-lookup"><span data-stu-id="e2cb6-107">For a task, the attribute is <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute>.</span></span>  
  
-   <span data-ttu-id="e2cb6-108">Substituer l'implémentation des méthodes et des propriétés de la classe de base.</span><span class="sxs-lookup"><span data-stu-id="e2cb6-108">Override the implementation of the base class's methods and properties.</span></span> <span data-ttu-id="e2cb6-109">Pour une tâche, il s'agit notamment des méthodes <xref:Microsoft.SqlServer.Dts.Runtime.Task.Validate%2A> et <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A>.</span><span class="sxs-lookup"><span data-stu-id="e2cb6-109">For a task, these include the <xref:Microsoft.SqlServer.Dts.Runtime.Task.Validate%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A> methods.</span></span>  
  
-   <span data-ttu-id="e2cb6-110">Développer éventuellement une interface utilisateur personnalisée.</span><span class="sxs-lookup"><span data-stu-id="e2cb6-110">Optionally, develop a custom user interface.</span></span> <span data-ttu-id="e2cb6-111">Pour une tâche, cette opération requiert une classe qui implémente l'interface <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI>.</span><span class="sxs-lookup"><span data-stu-id="e2cb6-111">For a task, this requires a class that implements the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI> interface.</span></span>  
  
## <a name="getting-started-with-a-custom-task"></a><span data-ttu-id="e2cb6-112">Mise en route d'une tâche personnalisée</span><span class="sxs-lookup"><span data-stu-id="e2cb6-112">Getting Started with a Custom Task</span></span>  
  
### <a name="creating-projects-and-classes"></a><span data-ttu-id="e2cb6-113">Création de projets et de classes</span><span class="sxs-lookup"><span data-stu-id="e2cb6-113">Creating Projects and Classes</span></span>  
 <span data-ttu-id="e2cb6-114">Comme toutes les tâches managées dérivent de la classe de base [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task), la première étape de création d’une tâche personnalisée consiste à créer un projet Bibliothèque de classes dans votre langage de programmation managé par défaut et créer une classe qui hérite de la classe de base.</span><span class="sxs-lookup"><span data-stu-id="e2cb6-114">Because all managed tasks derive from the [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) base class, the first step when you create a custom task is to create a class library project in your preferred managed programming language and create a class that inherits from the base class.</span></span> <span data-ttu-id="e2cb6-115">Dans cette classe dérivée, vous devez substituer les méthodes et les propriétés de la classe de base pour implémenter vos fonctionnalités personnalisées.</span><span class="sxs-lookup"><span data-stu-id="e2cb6-115">In this derived class you will override the methods and properties of the base class to implement your custom functionality.</span></span>  
  
 <span data-ttu-id="e2cb6-116">Dans la même solution, créez un deuxième projet Bibliothèque de classes pour l'interface utilisateur personnalisée.</span><span class="sxs-lookup"><span data-stu-id="e2cb6-116">In the same solution, create a second class library project for the custom user interface.</span></span> <span data-ttu-id="e2cb6-117">Il est recommandé d'utiliser un assembly distinct pour l'interface utilisateur afin de faciliter le déploiement car vous pouvez ainsi mettre à jour et redéployer le gestionnaire de connexions ou son interface utilisateur de manière indépendante.</span><span class="sxs-lookup"><span data-stu-id="e2cb6-117">A separate assembly for the user interface is recommended for ease of deployment because it allows you to update and redeploy the connection manager or its user interface independently.</span></span>  
  
 <span data-ttu-id="e2cb6-118">Configurez les deux projets pour qu'ils signent les assemblys qui seront créés au moment de la génération à l'aide d'un fichier de clé de nom fort.</span><span class="sxs-lookup"><span data-stu-id="e2cb6-118">Configure both projects to sign the assemblies that will be generated at build time by using a strong name key file.</span></span>  
  
### <a name="applying-the-dtstask-attribute"></a><span data-ttu-id="e2cb6-119">Application de l'attribut DtsTask</span><span class="sxs-lookup"><span data-stu-id="e2cb6-119">Applying the DtsTask Attribute</span></span>  
 <span data-ttu-id="e2cb6-120">Appliquez l'attribut <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> à la classe que vous avez créée pour l'identifier en tant que tâche.</span><span class="sxs-lookup"><span data-stu-id="e2cb6-120">Apply the <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> attribute to the class that you have created to identify it as a task.</span></span> <span data-ttu-id="e2cb6-121">Cet attribut fournit des informations au moment de la conception, telles que le nom, la description et le type de la tâche.</span><span class="sxs-lookup"><span data-stu-id="e2cb6-121">This attribute provides design-time information such as the name, description, and task type of the task.</span></span>  
  
 <span data-ttu-id="e2cb6-122">Utilisez la propriété <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.UITypeName%2A> pour lier la tâche à son interface utilisateur personnalisée.</span><span class="sxs-lookup"><span data-stu-id="e2cb6-122">Use the <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.UITypeName%2A> property to link the task to its custom user interface.</span></span> <span data-ttu-id="e2cb6-123">Pour obtenir le jeton de clé publique requis pour cette propriété, vous pouvez utiliser **sn.exe -t** de manière à afficher le jeton de clé publique du fichier de paire de clés (.snk) que vous voulez utiliser pour signer l’assembly de l’interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e2cb6-123">To obtain the public key token that is required for this property, you an use **sn.exe -t** to display the public key token from the key pair (.snk) file that you intend to use to sign the user interface assembly.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
namespace Microsoft.SSIS.Samples  
{  
  [DtsTask  
  (  
   DisplayName = "MyTask",  
   IconResource = "MyTask.MyTaskIcon.ico",  
   UITypeName = "My Custom Task," +  
   "Version=1.0.0.0," +  
   "Culture = Neutral," +  
   "PublicKeyToken = 12345abc6789de01",  
   TaskType = "PackageMaintenance",  
   TaskContact = "MyTask; company name; any other information",  
   RequiredProductLevel = DTSProductLevel.None  
   )]  
  public class MyTask : Task  
  {  
    // Your code here.  
  }  
}  
```  
  
```vb  
Imports System  
Imports Microsoft.SqlServer.Dts.Runtime  
  
<DtsTask(DisplayName:="MyTask", _  
 IconResource:="MyTask.MyTaskIcon.ico", _  
 UITypeName:="My Custom Task," & _  
 "Version=1.0.0.0,Culture=Neutral," & _  
 "PublicKeyToken=12345abc6789de01", _  
 TaskType:="PackageMaintenance", _  
 TaskContact:="MyTask; company name; any other information", _  
 RequiredProductLevel:=DTSProductLevel.None)> _  
Public Class MyTask  
  Inherits Task  
  
  ' Your code here.  
  
End Class 'MyTask  
```  
  
## <a name="building-deploying-and-debugging-a-custom-task"></a><span data-ttu-id="e2cb6-124">Génération, déploiement et débogage d'une tâche personnalisée</span><span class="sxs-lookup"><span data-stu-id="e2cb6-124">Building, Deploying, and Debugging a Custom Task</span></span>  
 <span data-ttu-id="e2cb6-125">Les étapes pour générer, déployer et déboguer une tâche personnalisée dans [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sont très semblables aux étapes requises pour les autres types d'objets personnalisés.</span><span class="sxs-lookup"><span data-stu-id="e2cb6-125">The steps for building, deploying, and debugging a custom task in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] are similar to the steps required for other types of custom objects.</span></span> <span data-ttu-id="e2cb6-126">Pour plus d’informations, consultez [Génération, déploiement et débogage d’objets personnalisés](../building-deploying-and-debugging-custom-objects.md).</span><span class="sxs-lookup"><span data-stu-id="e2cb6-126">For more information, see [Building, Deploying, and Debugging Custom Objects](../building-deploying-and-debugging-custom-objects.md).</span></span>  
  
<span data-ttu-id="e2cb6-127">![Icône de Integration Services (petite)](../../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="e2cb6-127">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="e2cb6-128">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="e2cb6-128">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="e2cb6-129">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="e2cb6-129">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="e2cb6-130">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="e2cb6-130">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2cb6-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e2cb6-131">See Also</span></span>  
 <span data-ttu-id="e2cb6-132">[Création d’une tâche personnalisée](creating-a-custom-task.md) </span><span class="sxs-lookup"><span data-stu-id="e2cb6-132">[Creating a Custom Task](creating-a-custom-task.md) </span></span>  
 <span data-ttu-id="e2cb6-133">[Codage d’une tâche personnalisée](coding-a-custom-task.md) </span><span class="sxs-lookup"><span data-stu-id="e2cb6-133">[Coding a Custom Task](coding-a-custom-task.md) </span></span>  
 [<span data-ttu-id="e2cb6-134">Développement d’une interface utilisateur pour une tâche personnalisée</span><span class="sxs-lookup"><span data-stu-id="e2cb6-134">Developing a User Interface for a Custom Task</span></span>](developing-a-user-interface-for-a-custom-task.md)  
  
  
