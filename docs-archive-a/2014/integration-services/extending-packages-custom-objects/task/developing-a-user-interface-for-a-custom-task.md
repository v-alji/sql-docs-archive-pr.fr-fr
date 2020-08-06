---
title: Développement d’une interface utilisateur pour une tâche personnalisée | Microsoft Docs
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
- custom user interfaces [Integration Services]
- IDtsTaskUI interface
- DtsTaskAttribute attribute
- custom tasks [Integration Services], user interface
- custom user interface [Integration Services], custom tasks
- user interface [Integration Services]
- SSIS custom tasks, user interface
ms.assetid: 1e940cd1-c5f8-4527-b678-e89ba5dc398a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ed96bbc302cba4c207e5ce7b2e4fb4b74fed4ee2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613546"
---
# <a name="developing-a-user-interface-for-a-custom-task"></a><span data-ttu-id="56944-102">Développement d'une interface utilisateur pour une tâche personnalisée</span><span class="sxs-lookup"><span data-stu-id="56944-102">Developing a User Interface for a Custom Task</span></span>
  <span data-ttu-id="56944-103">Le modèle objet [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] fournit aux développeurs de tâches personnalisées la capacité de créer facilement une interface utilisateur personnalisée pour une tâche, qui peut ensuite être intégrée et affichée dans [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="56944-103">The [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] object model provides custom task developers the ability to easily create a custom user interface for a task that can then be integrated and displayed in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="56944-104">L'interface utilisateur fournit des informations utiles dans le concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] et aide les utilisateurs à configurer correctement les propriétés et les paramètres de la tâche personnalisée.</span><span class="sxs-lookup"><span data-stu-id="56944-104">The user interface can provide helpful information to the user in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, and guide users to correctly configure the properties and settings of the custom task.</span></span>  
  
 <span data-ttu-id="56944-105">Le développement d'une interface utilisateur personnalisée pour une tâche implique l'utilisation de deux classes importantes.</span><span class="sxs-lookup"><span data-stu-id="56944-105">Developing a custom user interface for a task involves using two important classes.</span></span> <span data-ttu-id="56944-106">Le tableau suivant décrit ces classes.</span><span class="sxs-lookup"><span data-stu-id="56944-106">The following table describes those classes.</span></span>  
  
|<span data-ttu-id="56944-107">Classe</span><span class="sxs-lookup"><span data-stu-id="56944-107">Class</span></span>|<span data-ttu-id="56944-108">Description</span><span class="sxs-lookup"><span data-stu-id="56944-108">Description</span></span>|  
|-----------|-----------------|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute>|<span data-ttu-id="56944-109">Attribut qui identifie une tâche managée et fournit des informations au moment de la conception par le biais de ses propriétés pour contrôler la manière dont le concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] affiche les objets et interagit avec eux.</span><span class="sxs-lookup"><span data-stu-id="56944-109">An attribute that identifies a managed task, and supplies design-time information through its properties to control how [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer displays and interacts with the object.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI>|<span data-ttu-id="56944-110">Interface utilisée par la tâche pour s'associer à son interface utilisateur personnalisée.</span><span class="sxs-lookup"><span data-stu-id="56944-110">An interface used by the task to associate the task with its custom user interface.</span></span>|  
  
 <span data-ttu-id="56944-111">Cette section décrit le rôle de l'attribut <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> et de l'interface <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI> lorsque vous développez une interface utilisateur pour une tâche personnalisée. Elle fournit également des informations sur la manière de créer, intégrer, déployer et déboguer la tâche dans le concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="56944-111">This section describes the role of the <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> attribute and the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI> interface when you are developing a user interface for a custom task, and provides details about how to create, integrate, deploy, and debug the task within [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="56944-112">Le concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] fournit plusieurs points d’entrée dans l’interface utilisateur pour la tâche : l’utilisateur peut sélectionner **Modifier** dans le menu contextuel, double-cliquer sur la tâche ou cliquer sur le lien **Afficher l’éditeur** en bas de la feuille de propriétés.</span><span class="sxs-lookup"><span data-stu-id="56944-112">The [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer provides multiple entry points to the user interface for the task: the user can select **Edit** on the shortcut menu, double-click the task, or click the **Show Editor** link at the bottom of the property sheet.</span></span> <span data-ttu-id="56944-113">Lorsque l'utilisateur accède à l'un de ces points d'entrée, le concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] recherche et charge l'assembly qui contient l'interface utilisateur pour la tâche.</span><span class="sxs-lookup"><span data-stu-id="56944-113">When the user accesses one of these entry points, [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer locates and loads the assembly that contains the user interface for the task.</span></span> <span data-ttu-id="56944-114">L'interface utilisateur de la tâche est chargée de créer la boîte de dialogue des propriétés affichée pour l'utilisateur dans [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="56944-114">The user interface for the task is responsible for creating the properties dialog box that is displayed to the user in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="56944-115">Une tâche et son interface utilisateur sont des entités distinctes.</span><span class="sxs-lookup"><span data-stu-id="56944-115">A task and its user interface are separate entities.</span></span> <span data-ttu-id="56944-116">Elles doivent être implémentées dans des assemblys séparés pour réduire les tâches de localisation, de déploiement et de maintenance.</span><span class="sxs-lookup"><span data-stu-id="56944-116">They should be implemented in separate assemblies to reduce localization, deployment, and maintenance work.</span></span> <span data-ttu-id="56944-117">La DLL n'a généralement pas connaissance de son interface utilisateur et ne charge ni n'appelle de données la concernant, à l'exception des informations contenues dans les valeurs d'attribut <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> codées dans la tâche.</span><span class="sxs-lookup"><span data-stu-id="56944-117">The task DLL does not load, call, or generally contain any knowledge of its user interface, except for the information that is contained in the <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> attribute values coded in the task.</span></span> <span data-ttu-id="56944-118">Il s'agit du seul lien qui unit une tâche et son interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="56944-118">This is the only way that a task and its user interface are associated.</span></span>  
  
## <a name="the-dtstask-attribute"></a><span data-ttu-id="56944-119">Attribut DtsTask</span><span class="sxs-lookup"><span data-stu-id="56944-119">The DtsTask Attribute</span></span>  
 <span data-ttu-id="56944-120">L'attribut <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> est inclus dans le code de classe de tâche pour associer une tâche à son interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="56944-120">The <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> attribute is included in the task class code to associate a task with its user interface.</span></span> <span data-ttu-id="56944-121">Le concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] utilise les propriétés de l'attribut pour déterminer comment afficher la tâche.</span><span class="sxs-lookup"><span data-stu-id="56944-121">The [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer uses the properties of the attribute to determine how to display the task in the designer.</span></span> <span data-ttu-id="56944-122">Ces propriétés incluent le nom à afficher et l'icône, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="56944-122">These properties include the name to display and the icon, if any.</span></span>  
  
 <span data-ttu-id="56944-123">Le tableau suivant décrit les propriétés de l'attribut <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute>.</span><span class="sxs-lookup"><span data-stu-id="56944-123">The following table describes the properties of the <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> attribute.</span></span>  
  
|<span data-ttu-id="56944-124">Propriété</span><span class="sxs-lookup"><span data-stu-id="56944-124">Property</span></span>|<span data-ttu-id="56944-125">Description</span><span class="sxs-lookup"><span data-stu-id="56944-125">Description</span></span>|  
|--------------|-----------------|  
|<xref:Microsoft.SqlServer.Dts.Runtime.Localization.DtsLocalizableAttribute.DisplayName%2A>|<span data-ttu-id="56944-126">Affiche le nom de la tâche dans la boîte à outils Flux de contrôle.</span><span class="sxs-lookup"><span data-stu-id="56944-126">Displays the task name in the Control Flow toolbox.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.Localization.DtsLocalizableAttribute.Description%2A>|<span data-ttu-id="56944-127">Description de la tâche (héritée de <xref:Microsoft.SqlServer.Dts.Runtime.Localization.DtsLocalizableAttribute>).</span><span class="sxs-lookup"><span data-stu-id="56944-127">The task description (inherited from <xref:Microsoft.SqlServer.Dts.Runtime.Localization.DtsLocalizableAttribute>).</span></span> <span data-ttu-id="56944-128">Cette propriété est affichée dans des info-bulles.</span><span class="sxs-lookup"><span data-stu-id="56944-128">This property is shown in ToolTips.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.IconResource%2A>|<span data-ttu-id="56944-129">Icône affichée dans le concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="56944-129">The icon displayed in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.RequiredProductLevel%2A>|<span data-ttu-id="56944-130">Si vous utilisez cette propriété, attribuez-lui l'une des valeurs de l'énumération <xref:Microsoft.SqlServer.Dts.Runtime.DTSProductLevel>.</span><span class="sxs-lookup"><span data-stu-id="56944-130">If used, set it to one of the values in the <xref:Microsoft.SqlServer.Dts.Runtime.DTSProductLevel> enumeration.</span></span> <span data-ttu-id="56944-131">Par exemple : `RequiredProductLevel = DTSProductLevel.None`.</span><span class="sxs-lookup"><span data-stu-id="56944-131">For example, `RequiredProductLevel = DTSProductLevel.None`.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.TaskContact%2A>|<span data-ttu-id="56944-132">Contient des informations de contact au cas où la tâche nécessite un support technique.</span><span class="sxs-lookup"><span data-stu-id="56944-132">Holds contact information for occasions when the task requires technical support.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.TaskType%2A>|<span data-ttu-id="56944-133">Assigne un type à la tâche.</span><span class="sxs-lookup"><span data-stu-id="56944-133">Assigns a type to the task.</span></span>|  
|<span data-ttu-id="56944-134">Attribute.TypeId</span><span class="sxs-lookup"><span data-stu-id="56944-134">Attribute.TypeId</span></span>|<span data-ttu-id="56944-135">Dans le cadre d'une implémentation dans une classe dérivée, obtient un identificateur unique pour cet attribut.</span><span class="sxs-lookup"><span data-stu-id="56944-135">When implemented in a derived class, gets a unique identifier for this Attribute.</span></span> <span data-ttu-id="56944-136">Pour plus d'informations, consultez la propriété `Attribute.TypeID` dans la bibliothèque de classes .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="56944-136">For more information, see `Attribute.TypeID` property in the .NET Framework Class Library.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.UITypeName%2A>|<span data-ttu-id="56944-137">Nom de type de l'assembly utilisé par le concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] pour charger l'assembly.</span><span class="sxs-lookup"><span data-stu-id="56944-137">The type name of the assembly that is used by [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer to load the assembly.</span></span> <span data-ttu-id="56944-138">Cette propriété permet de rechercher l'assembly de l'interface utilisateur pour la tâche.</span><span class="sxs-lookup"><span data-stu-id="56944-138">This property is used to find the user interface assembly for the task.</span></span>|  
  
 <span data-ttu-id="56944-139">L'exemple de code suivant présente le <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute>, au-dessus de la définition de classe.</span><span class="sxs-lookup"><span data-stu-id="56944-139">The following code example shows the <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> as it would look, coded above the class definition.</span></span>  
  
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
  
 <span data-ttu-id="56944-140">Le concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] utilise la propriété <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.UITypeName%2A> de l'attribut qui inclut le nom, le nom de type, la version, la culture et le jeton de clé publique de l'assembly, pour rechercher l'assembly dans le Global Assembly Cache (GAC) et le charger à l'usage du concepteur.</span><span class="sxs-lookup"><span data-stu-id="56944-140">The [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer uses the <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.UITypeName%2A> property of the attribute that includes the assembly name, type name, version, culture, and public key token, to locate the assembly in the Global Assembly Cache (GAC) and load it for use by the designer.</span></span>  
  
 <span data-ttu-id="56944-141">Une fois que l'assembly a été trouvé, le concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] utilise les autres propriétés de l'attribut pour afficher des informations supplémentaires sur la tâche dans le concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)], telles que le nom, l'icône et la description de la tâche.</span><span class="sxs-lookup"><span data-stu-id="56944-141">After the assembly has been located, [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer uses the other properties in the attribute to display additional information about the task in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, such as the name, icon, and description of the task.</span></span>  
  
 <span data-ttu-id="56944-142">Les propriétés <xref:Microsoft.SqlServer.Dts.Runtime.Localization.DtsLocalizableAttribute.DisplayName%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.Localization.DtsLocalizableAttribute.Description%2A> et <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.IconResource%2A> spécifient la manière dont la tâche est présentée à l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="56944-142">The <xref:Microsoft.SqlServer.Dts.Runtime.Localization.DtsLocalizableAttribute.DisplayName%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.Localization.DtsLocalizableAttribute.Description%2A>, and <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.IconResource%2A> properties specify how the task is presented to the user.</span></span> <span data-ttu-id="56944-143">La propriété <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.IconResource%2A> contient l'ID de ressource de l'icône incorporé dans l'assembly de l'interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="56944-143">The <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute.IconResource%2A> property contains the resource ID of the icon embedded in the user interface assembly.</span></span> <span data-ttu-id="56944-144">Le concepteur charge la ressource icône par ID à partir de l'assembly et l'affiche en regard du nom de la tâche dans la boîte à outils et dans l'aire du concepteur lorsque la tâche est ajoutée à un package.</span><span class="sxs-lookup"><span data-stu-id="56944-144">The designer loads the icon resource by ID from the assembly, and displays it next to the task name in the toolbox and on the designer surface when the task is added to a package.</span></span> <span data-ttu-id="56944-145">Si une tâche ne fournit pas de ressource icône, le concepteur utilise une icône par défaut pour la tâche.</span><span class="sxs-lookup"><span data-stu-id="56944-145">If a task does not provide an icon resource, the designer uses a default icon for the task.</span></span>  
  
## <a name="the-idtstaskui-interface"></a><span data-ttu-id="56944-146">Interface IDTSTaskUI</span><span class="sxs-lookup"><span data-stu-id="56944-146">The IDTSTaskUI Interface</span></span>  
 <span data-ttu-id="56944-147">L'interface <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI> définit la collection de méthodes et de propriétés appelées par le concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] pour initialiser et afficher l'interface utilisateur associée à la tâche.</span><span class="sxs-lookup"><span data-stu-id="56944-147">The <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI> interface defines the collection of methods and properties called by [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer to initialize and display the user interface associated with the task.</span></span> <span data-ttu-id="56944-148">Lorsque l'interface utilisateur d'une tâche est appelée, le concepteur appelle la méthode <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI.Initialize%2A>, implémentée par l'interface utilisateur de la tâche lorsque vous l'avez écrite, puis fournit les collections <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> et <xref:Microsoft.SqlServer.Dts.Runtime.Connections> de la tâche et du package, respectivement, en tant que paramètres.</span><span class="sxs-lookup"><span data-stu-id="56944-148">When the user interface for a task is invoked, the designer calls the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI.Initialize%2A> method, implemented by the task user interface when you wrote it, and then provides the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> and <xref:Microsoft.SqlServer.Dts.Runtime.Connections> collections of the task and package, respectively, as parameters.</span></span> <span data-ttu-id="56944-149">Ces collections sont stockées localement et utilisées par la suite dans la méthode <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI.GetView%2A>.</span><span class="sxs-lookup"><span data-stu-id="56944-149">These collections are stored locally, and used subsequently in the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI.GetView%2A> method.</span></span>  
  
 <span data-ttu-id="56944-150">Le concepteur appelle la méthode <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI.GetView%2A> pour demander la fenêtre affichée dans le concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="56944-150">The designer calls the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI.GetView%2A> method to request the window that is displayed in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="56944-151">La tâche crée une instance de la fenêtre qui contient l'interface utilisateur de la tâche et retourne l'interface utilisateur au concepteur afin qu'elle soit affichée.</span><span class="sxs-lookup"><span data-stu-id="56944-151">The task creates an instance of the window that contains the user interface for the task, and returns the user interface to the designer for display.</span></span> <span data-ttu-id="56944-152">En général, les objets <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> et <xref:Microsoft.SqlServer.Dts.Runtime.Connections> sont fournis à la fenêtre par le biais d'un constructeur surchargé afin qu'ils puissent être utilisés pour configurer la tâche.</span><span class="sxs-lookup"><span data-stu-id="56944-152">Typically, the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> and <xref:Microsoft.SqlServer.Dts.Runtime.Connections> objects are provided to the window through an overloaded constructor so they can be used to configure the task.</span></span>  
  
 <span data-ttu-id="56944-153">Pour afficher l'interface utilisateur de la tâche, le concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] appelle la méthode <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI.GetView%2A> associée.</span><span class="sxs-lookup"><span data-stu-id="56944-153">The [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer calls the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI.GetView%2A> method of the task UI to display the user interface for the task.</span></span> <span data-ttu-id="56944-154">L'interface utilisateur de la tâche retourne le Windows Form de cette méthode et le concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] affiche ce formulaire sous le forme d'une boîte de dialogue modale.</span><span class="sxs-lookup"><span data-stu-id="56944-154">The task user interface returns the Windows form from this method, and [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer shows this form as a modal dialog box.</span></span> <span data-ttu-id="56944-155">Lorsque le formulaire est fermé, le concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] examine la valeur de la propriété `DialogResult` du formulaire pour déterminer si la tâche a été modifiée et si ces modifications doivent être enregistrées.</span><span class="sxs-lookup"><span data-stu-id="56944-155">When the form is closed, [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer examines the value of the `DialogResult` property of the form to determine whether the task has been modified and if these modifications should be saved.</span></span> <span data-ttu-id="56944-156">Si la propriété `DialogResult` a la valeur `OK`, le concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] appelle les méthodes de persistance de la tâche pour enregistrer les modifications ; sinon, les modifications sont supprimées.</span><span class="sxs-lookup"><span data-stu-id="56944-156">If the value of the `DialogResult` property is `OK`, the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer calls the persistence methods of the task to save the changes; otherwise, the changes are discarded.</span></span>  
  
 <span data-ttu-id="56944-157">L'exemple de code suivant implémente l'interface <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI> et suppose l'existence d'une classe Windows Form nommée SampleTaskForm.</span><span class="sxs-lookup"><span data-stu-id="56944-157">The following code sample implements the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsTaskUI> interface, and assumes the existence of a Windows form class named SampleTaskForm.</span></span>  
  
```csharp  
using System;  
using System.Windows.Forms;  
using Microsoft.SqlServer.Dts.Runtime;  
using Microsoft.SqlServer.Dts.Runtime.Design;  
  
namespace Sample  
{  
   public class HelloWorldTaskUI : IDtsTaskUI  
   {  
      TaskHost   taskHost;  
      Connections connections;  
      public void Initialize(TaskHost taskHost, IServiceProvider serviceProvider)  
      {  
         this.taskHost = taskHost;  
         IDtsConnectionService cs = serviceProvider.GetService  
         ( typeof( IDtsConnectionService ) ) as   IDtsConnectionService;   
         this.connections = cs.GetConnections();  
      }  
      public ContainerControl GetView()  
      {  
        return new HelloWorldTaskForm(this.taskHost, this.connections);  
      }  
     public void Delete(IWin32Window parentWindow)  
     {  
     }  
     public void New(IWin32Window parentWindow)  
     {  
     }  
   }  
}  
```  
  
```vb  
Imports System  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports Microsoft.SqlServer.Dts.Runtime.Design  
Imports System.Windows.Forms  
  
Public Class HelloWorldTaskUI  
  Implements IDtsTaskUI  
  
  Dim taskHost As TaskHost  
  Dim connections As Connections  
  
  Public Sub Initialize(ByVal taskHost As TaskHost, ByVal serviceProvider As IServiceProvider) _  
    Implements IDtsTaskUI.Initialize  
  
    Dim cs As IDtsConnectionService  
  
    Me.taskHost = taskHost  
    cs = DirectCast(serviceProvider.GetService(GetType(IDtsConnectionService)), IDtsConnectionService)  
    Me.connections = cs.GetConnections()  
  
  End Sub  
  
  Public Function GetView() As ContainerControl _  
    Implements IDtsTaskUI.GetView  
  
    Return New HelloWorldTaskForm(Me.taskHost, Me.connections)  
  
  End Function  
  
  Public Sub Delete(ByVal parentWindow As IWin32Window) _  
    Implements IDtsTaskUI.Delete  
  
  End Sub  
  
  Public Sub [New](ByVal parentWindow As IWin32Window) _  
    Implements IDtsTaskUI.[New]  
  
  End Sub  
  
End Class  
```  
  
<span data-ttu-id="56944-158">![Icône de Integration Services (petite)](../../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="56944-158">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="56944-159">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="56944-159">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="56944-160">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="56944-160">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="56944-161">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="56944-161">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56944-162">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="56944-162">See Also</span></span>  
 <span data-ttu-id="56944-163">[Création d’une tâche personnalisée](creating-a-custom-task.md) </span><span class="sxs-lookup"><span data-stu-id="56944-163">[Creating a Custom Task](creating-a-custom-task.md) </span></span>  
 <span data-ttu-id="56944-164">[Codage d’une tâche personnalisée](coding-a-custom-task.md) </span><span class="sxs-lookup"><span data-stu-id="56944-164">[Coding a Custom Task](coding-a-custom-task.md) </span></span>  
 [<span data-ttu-id="56944-165">Développement d’une interface utilisateur pour une tâche personnalisée</span><span class="sxs-lookup"><span data-stu-id="56944-165">Developing a User Interface for a Custom Task</span></span>](developing-a-user-interface-for-a-custom-task.md)  
  
  
