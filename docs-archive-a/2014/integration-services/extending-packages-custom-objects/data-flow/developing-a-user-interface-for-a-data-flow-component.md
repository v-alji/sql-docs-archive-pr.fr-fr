---
title: Développement d’une interface utilisateur pour un composant de flux de données | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data flow components [Integration Services], custom editors
- user interfaces [Integration Services]
- custom data flow components [Integration Services], custom editors
- custom component editors [Integration Services]
- IDtsComponentUI interface
- UITypeName property
- custom user interface [Integration Services], custom data flow component
- editors [Integration Services]
ms.assetid: 10b829a1-609b-42e3-9070-cfe5a2bb698c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f97f21ad14a5fa67fb49192931a0cb46d0cb41da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697024"
---
# <a name="developing-a-user-interface-for-a-data-flow-component"></a><span data-ttu-id="6de2b-102">Développement d'une interface utilisateur pour un composant de flux de données</span><span class="sxs-lookup"><span data-stu-id="6de2b-102">Developing a User Interface for a Data Flow Component</span></span>
  <span data-ttu-id="6de2b-103">Les développeurs de composants peuvent fournir une interface utilisateur personnalisée pour un composant. Cette interface s'affiche dans [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] lors de la modification du composant.</span><span class="sxs-lookup"><span data-stu-id="6de2b-103">Component developers can provide a custom user interface for a component, which is displayed in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] when the component is edited.</span></span> <span data-ttu-id="6de2b-104">Grâce à l'implémentation d'une interface utilisateur personnalisée, vous êtes averti lorsque le composant est ajouté ou supprimé d'une tâche de flux de données, et lorsque de l'aide est demandée pour le composant.</span><span class="sxs-lookup"><span data-stu-id="6de2b-104">Implementing a custom user interface provides you with notification when the component is added to or deleted from a data flow task, and when help is requested for the component.</span></span>

 <span data-ttu-id="6de2b-105">Si vous ne fournissez pas d'interface utilisateur personnalisée pour votre composant, les utilisateurs peuvent encore configurer le composant et ses propriétés personnalisées à l'aide de l'éditeur avancé.</span><span class="sxs-lookup"><span data-stu-id="6de2b-105">If you do not provide a custom user interface for your component, users can still configure the component and its custom properties by using the Advanced Editor.</span></span> <span data-ttu-id="6de2b-106">Vous pouvez vous assurer que l'éditeur avancé permet aux utilisateurs de modifier convenablement des valeurs de propriété personnalisées à l'aide des propriétés <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.TypeConverter%2A> et <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.UITypeEditor%2A> de <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100> le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="6de2b-106">You can ensure that the Advanced Editor allows users to edit custom property values appropriately by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.TypeConverter%2A> and <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.UITypeEditor%2A> properties of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100> when appropriate.</span></span> <span data-ttu-id="6de2b-107">Pour plus d’informations, consultez « Création de propriétés personnalisées » dans [Méthodes de conception d’un composant de flux de données](design-time-methods-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="6de2b-107">For more information, see "Creating Custom Properties" in [Design-time Methods of a Data Flow Component](design-time-methods-of-a-data-flow-component.md).</span></span>

## <a name="setting-the-uitypename-property"></a><span data-ttu-id="6de2b-108">Définition de la propriété UITypeName</span><span class="sxs-lookup"><span data-stu-id="6de2b-108">Setting the UITypeName Property</span></span>
 <span data-ttu-id="6de2b-109">Pour fournir une interface utilisateur personnalisée, le développeur doit attribuer à la propriété <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.UITypeName%2A> de <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute> le nom d'une classe qui implémente l'interface <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI>.</span><span class="sxs-lookup"><span data-stu-id="6de2b-109">To provide a custom user interface, the developer must set the <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.UITypeName%2A> property of the <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute> to the name of a class that implements the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI> interface.</span></span> <span data-ttu-id="6de2b-110">Lorsque cette propriété est définie par le composant, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] charge et appelle l’interface utilisateur personnalisée lorsque le composant est modifié dans le concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6de2b-110">When this property is set by the component, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] loads and calls the custom user interface when the component is edited in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>

 <span data-ttu-id="6de2b-111">La propriété <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.UITypeName%2A> est une chaîne délimitée par des virgules qui identifie le nom qualifié complet du type.</span><span class="sxs-lookup"><span data-stu-id="6de2b-111">The <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.UITypeName%2A> property is a comma-delimited string that identifies the fully qualified name of the type.</span></span> <span data-ttu-id="6de2b-112">La liste suivante affiche, dans l'ordre, les éléments qui identifient le type :</span><span class="sxs-lookup"><span data-stu-id="6de2b-112">The following list shows, in order, the elements that identify the type:</span></span>

-   <span data-ttu-id="6de2b-113">Nom de type</span><span class="sxs-lookup"><span data-stu-id="6de2b-113">Type name</span></span>

-   <span data-ttu-id="6de2b-114">Nom de l'assembly</span><span class="sxs-lookup"><span data-stu-id="6de2b-114">Assembly name</span></span>

-   <span data-ttu-id="6de2b-115">Version de fichier</span><span class="sxs-lookup"><span data-stu-id="6de2b-115">File version</span></span>

-   <span data-ttu-id="6de2b-116">Culture</span><span class="sxs-lookup"><span data-stu-id="6de2b-116">Culture</span></span>

-   <span data-ttu-id="6de2b-117">Jeton de clé publique</span><span class="sxs-lookup"><span data-stu-id="6de2b-117">Public key token</span></span>

 <span data-ttu-id="6de2b-118">L'exemple de code suivant montre une classe dérivée de la classe de base <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> et spécifie la propriété <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.UITypeName%2A>.</span><span class="sxs-lookup"><span data-stu-id="6de2b-118">The following code example shows a class that derives from the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> base class and specifies the <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.UITypeName%2A> property.</span></span>

```csharp
[DtsPipelineComponent(
DisplayName="SampleComponent",
UITypeName="MyNamespace.MyComponentUIClassName,MyAssemblyName,Version=1.0.0.0,Culture=neutral,PublicKeyToken=abcd...",
ComponentType = ComponentType.Transform)]
public class SampleComponent : PipelineComponent
{
//TODO: Implement the component here.
}
```

```vb
<DtsPipelineComponent(DisplayName="SampleComponent", _
UITypeName="MyNamespace.MyComponentUIClassName,MyAssemblyName,Version=1.0.0.0,Culture=neutral,PublicKeyToken=abcd...", ComponentType=ComponentType.Transform)> _ 
Public Class SampleComponent 
 Inherits PipelineComponent 
End Class
```

## <a name="implementing-the-idtscomponentui-interface"></a><span data-ttu-id="6de2b-119">Implémentation de l'interface IDtsComponentUI</span><span class="sxs-lookup"><span data-stu-id="6de2b-119">Implementing the IDtsComponentUI Interface</span></span>
 <span data-ttu-id="6de2b-120">L'interface <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI> contient des méthodes que le concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] appelle lorsqu'un composant est ajouté, supprimé ou modifié.</span><span class="sxs-lookup"><span data-stu-id="6de2b-120">The <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI> interface contains methods that [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer calls when a component is added, deleted, and edited.</span></span> <span data-ttu-id="6de2b-121">Les développeurs de composants peuvent fournir du code dans leur implémentation de ces méthodes pour interagir avec les utilisateurs des composants.</span><span class="sxs-lookup"><span data-stu-id="6de2b-121">Component developers can provide code in their implementation of these methods to interact with users of the component.</span></span>

 <span data-ttu-id="6de2b-122">Cette classe est généralement implémentée dans un assembly distinct du composant lui-même.</span><span class="sxs-lookup"><span data-stu-id="6de2b-122">This class is typically implemented in an assembly separate from the component itself.</span></span> <span data-ttu-id="6de2b-123">Bien qu'elle ne soit pas obligatoire, l'utilisation d'un assembly séparé permet au développeur de générer et déployer le composant et l'interface utilisateur indépendamment l'un de l'autre et de limiter l'encombrement binaire du composant.</span><span class="sxs-lookup"><span data-stu-id="6de2b-123">Although use of a separate assembly is not required, this lets the developer build and deploy the component and the user interface independently of each other, and keeps the binary footprint of the component small.</span></span>

 <span data-ttu-id="6de2b-124">L'implémentation d'une interface utilisateur personnalisée permet au développeur de composants de mieux contrôler le composant lorsqu'il est modifié dans le concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6de2b-124">Implementing a custom user interface gives the component developer more control over the component as it is edited in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="6de2b-125">Par exemple, un composant peut ajouter du code à la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.New%2A>, appelée lorsqu'un composant est initialement ajouté à une tâche de flux de données, et afficher un Assistant qui guide l'utilisateur à travers la configuration initiale du composant.</span><span class="sxs-lookup"><span data-stu-id="6de2b-125">For example, a component can add code to the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.New%2A> method, which is called when a component is initially added to a data flow task, and display a wizard that guides the user through the initial configuration of the component.</span></span>

 <span data-ttu-id="6de2b-126">Après avoir créé une classe qui implémente l'interface <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI>, vous devez ajouter du code pour répondre à l'interaction de l'utilisateur avec le composant.</span><span class="sxs-lookup"><span data-stu-id="6de2b-126">After you have created a class that implements the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI> interface, you must add code to respond to user interaction with the component.</span></span> <span data-ttu-id="6de2b-127">La méthode <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Initialize%2A> fournit l'interface <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> du composant et est appelée avant les méthodes <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.New%2A> et <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Edit%2A>.</span><span class="sxs-lookup"><span data-stu-id="6de2b-127">The <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Initialize%2A> method provides the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface of the component, and is called before the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.New%2A> and <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Edit%2A> methods.</span></span> <span data-ttu-id="6de2b-128">Cette référence doit être stockée dans une variable membre privée et utilisée ensuite pour modifier les métadonnées du composant.</span><span class="sxs-lookup"><span data-stu-id="6de2b-128">This reference should be stored in a private member variable and used to modify the component's metadata thereafter.</span></span>

## <a name="modifying-a-component-and-persisting-changes"></a><span data-ttu-id="6de2b-129">Modification d'un composant et persistance des modifications</span><span class="sxs-lookup"><span data-stu-id="6de2b-129">Modifying a Component and Persisting Changes</span></span>
 <span data-ttu-id="6de2b-130">L'interface <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> est fournie en tant que paramètre à la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Initialize%2A>.</span><span class="sxs-lookup"><span data-stu-id="6de2b-130">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface is provided as a parameter to the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Initialize%2A> method.</span></span> <span data-ttu-id="6de2b-131">Cette référence doit être mise en cache dans une variable membre par le code d'interface utilisateur, puis utilisée pour modifier le composant en réponse à l'interaction de l'utilisateur avec l'interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6de2b-131">This reference should be cached in a member variable by the user interface code, and then used to modify the component in response to user interaction with the user interface.</span></span>

 <span data-ttu-id="6de2b-132">Bien que vous puissiez modifier le composant directement à partir de l'interface <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100>, il est préférable de créer une instance de <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapper> à l'aide de la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.Instantiate%2A>.</span><span class="sxs-lookup"><span data-stu-id="6de2b-132">Although you can modify the component directly through the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface, it is better to create an instance of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapper> by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.Instantiate%2A> method.</span></span> <span data-ttu-id="6de2b-133">Lorsque vous modifiez directement le composant à l'aide de l'interface, vous contournez les dispositifs de protection de la validation du composant.</span><span class="sxs-lookup"><span data-stu-id="6de2b-133">When you edit the component directly by using the interface, you bypass the component's validation safeguards.</span></span> <span data-ttu-id="6de2b-134">L'utilisation de l'instance du composant au moment de la conception par le biais de <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapper> présente l'avantage de garantir que le composant peut contrôler les modifications qui lui sont appliquées.</span><span class="sxs-lookup"><span data-stu-id="6de2b-134">The advantage of using the design-time instance of the component through the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.CManagedComponentWrapper> is that you ensure that the component has control over the changes made to it.</span></span>

 <span data-ttu-id="6de2b-135">La valeur de retour de la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Edit%2A> détermine si les modifications apportées à un composant sont conservées ou supprimées.</span><span class="sxs-lookup"><span data-stu-id="6de2b-135">The return value of the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Edit%2A> method determines whether changes made to a component are persisted or discarded.</span></span> <span data-ttu-id="6de2b-136">Lorsque cette méthode retourne `false`, toutes les modifications sont ignorées ; `true` rend persistantes les modifications apportées au composant et marque le package comme devant être enregistré.</span><span class="sxs-lookup"><span data-stu-id="6de2b-136">When this method returns `false`, all changes are discarded; `true` persists the changes to the component and marks the package as needing to be saved.</span></span>

### <a name="using-the-services-of-the-ssis-designer"></a><span data-ttu-id="6de2b-137">Utilisation des services du concepteur SSIS</span><span class="sxs-lookup"><span data-stu-id="6de2b-137">Using the Services of the SSIS Designer</span></span>
 <span data-ttu-id="6de2b-138">Le paramètre `IServiceProvider` de la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Initialize%2A> fournit l'accès aux services suivants du concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="6de2b-138">The `IServiceProvider` parameter of the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Initialize%2A> method provides access to the following services of [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer:</span></span>

|<span data-ttu-id="6de2b-139">Service</span><span class="sxs-lookup"><span data-stu-id="6de2b-139">Service</span></span>|<span data-ttu-id="6de2b-140">Description</span><span class="sxs-lookup"><span data-stu-id="6de2b-140">Description</span></span>|
|-------------|-----------------|
|<xref:Microsoft.SqlServer.Dts.Design.IDtsClipboardService>|<span data-ttu-id="6de2b-141">Permet de déterminer si le composant a été généré dans le cadre d'une opération copier/coller ou couper/coller.</span><span class="sxs-lookup"><span data-stu-id="6de2b-141">Used to determine whether the component was generated as part of a copy/paste or cut/paste operation.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionService>|<span data-ttu-id="6de2b-142">Permet d'accéder aux connexions existantes ou de créer des connexions dans le package.</span><span class="sxs-lookup"><span data-stu-id="6de2b-142">Used to access existing connections or to create new connections in the package.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Design.IErrorCollectionService>|<span data-ttu-id="6de2b-143">Permet de capturer des événements à partir de composants de flux de données lorsque vous devez capturer l'ensemble des erreurs et avertissements déclenchés par le composant au lieu de ne recevoir que la dernière erreur ou le dernier avertissement.</span><span class="sxs-lookup"><span data-stu-id="6de2b-143">Used to capture events from data flow components when you need to capture all the errors and warnings raised by the component instead of receiving only the last error or warning.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsVariableService>|<span data-ttu-id="6de2b-144">Permet d'accéder aux variables existantes ou de créer des variables dans le package.</span><span class="sxs-lookup"><span data-stu-id="6de2b-144">Used to access existing variables or to create new variables in the package.</span></span>|
|<xref:Microsoft.SqlServer.Dts.Design.IDtsPipelineEnvironmentService>|<span data-ttu-id="6de2b-145">Permet aux composants de flux de données d'accéder à la tâche de flux de données parente et aux autres composants dans le flux de données.</span><span class="sxs-lookup"><span data-stu-id="6de2b-145">Used by data flow components to access the parent Data Flow task and other components in the data flow.</span></span> <span data-ttu-id="6de2b-146">Cette fonctionnalité pourrait être utilisée pour développer un composant semblable à l'Assistant Dimension à variation lente qui crée et connecte des composants de flux de données supplémentaires si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="6de2b-146">This feature could be used to develop a component like the Slowly Changing Dimension Wizard that creates and connects additional data flow components as needed.</span></span>|

 <span data-ttu-id="6de2b-147">Ces services fournissent aux développeurs de composants la capacité d'accéder à des objets (ou d'en créer) dans le package dans lequel le composant est chargé.</span><span class="sxs-lookup"><span data-stu-id="6de2b-147">These services provide component developers the ability to access and create objects in the package in which the component is loaded.</span></span>

## <a name="sample"></a><span data-ttu-id="6de2b-148">Exemple</span><span class="sxs-lookup"><span data-stu-id="6de2b-148">Sample</span></span>
 <span data-ttu-id="6de2b-149">L'exemple de code suivant montre l'intégration d'une classe d'interface utilisateur personnalisée qui implémente l'interface <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI>, et un Windows Form qui fait office d'éditeur pour un composant.</span><span class="sxs-lookup"><span data-stu-id="6de2b-149">The following code example shows the integration of a custom user interface class that implements the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI> interface, and a Windows form that serves as the editor for a component.</span></span>

### <a name="custom-user-interface-class"></a><span data-ttu-id="6de2b-150">Classe d'interface utilisateur personnalisée</span><span class="sxs-lookup"><span data-stu-id="6de2b-150">Custom User Interface Class</span></span>
 <span data-ttu-id="6de2b-151">Le code suivant montre la classe qui implémente l'interface <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI>.</span><span class="sxs-lookup"><span data-stu-id="6de2b-151">The following code shows the class that implements the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI> interface.</span></span> <span data-ttu-id="6de2b-152">La méthode <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Edit%2A> crée l'éditeur de composant, puis affiche le formulaire.</span><span class="sxs-lookup"><span data-stu-id="6de2b-152">The <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Edit%2A> method creates the component editor and then displays the form.</span></span> <span data-ttu-id="6de2b-153">La valeur de retour du formulaire détermine si les modifications apportées au composant sont rendues persistantes.</span><span class="sxs-lookup"><span data-stu-id="6de2b-153">The return value of the form determines whether changes to the component are persisted.</span></span>

```csharp
using System;
using System.Windows.Forms;
using Microsoft.SqlServer.Dts.Runtime;
using Microsoft.SqlServer.Dts.Pipeline.Design;
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;

namespace Microsoft.Samples.SqlServer.Dts
{
    public class SampleComponentUI : IDtsComponentUI
    {
        IDTSComponentMetaData100 md;
        IServiceProvider sp;

        public void Help(System.Windows.Forms.IWin32Window parentWindow)
        {
        }
        public void New(System.Windows.Forms.IWin32Window parentWindow)
        {
        }
        public void Delete(System.Windows.Forms.IWin32Window parentWindow)
        {
        }
        public bool Edit(System.Windows.Forms.IWin32Window parentWindow, Variables vars, Connections cons)
        {
            // Create and display the form for the user interface.
            SampleComponentUIForm componentEditor = new SampleComponentUIForm(cons, vars, md);

            DialogResult result  = componentEditor.ShowDialog(parentWindow);

            if (result == DialogResult.OK)
                return true;

            return false;
        }
        public void Initialize(IDTSComponentMetaData100 dtsComponentMetadata, IServiceProvider serviceProvider)
        {
            // Store the component metadata.
            this.md = dtsComponentMetadata;
        }
    }
}
```

```vb
Imports System 
Imports System.Windows.Forms 
Imports Microsoft.SqlServer.Dts.Runtime 
Imports Microsoft.SqlServer.Dts.Pipeline.Design 
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper 

Namespace Microsoft.Samples.SqlServer.Dts 

 Public Class SampleComponentUI 
 Implements IDtsComponentUI 
   Private md As IDTSComponentMetaData100 
   Private sp As IServiceProvider 

   Public Sub Help(ByVal parentWindow As System.Windows.Forms.IWin32Window) 
   End Sub 

   Public Sub New(ByVal parentWindow As System.Windows.Forms.IWin32Window) 
   End Sub 

   Public Sub Delete(ByVal parentWindow As System.Windows.Forms.IWin32Window) 
   End Sub 

   Public Function Edit(ByVal parentWindow As System.Windows.Forms.IWin32Window, ByVal vars As Variables, ByVal cons As Connections) As Boolean 
     ' Create and display the form for the user interface.
     Dim componentEditor As SampleComponentUIForm = New SampleComponentUIForm(cons, vars, md) 
     Dim result As DialogResult = componentEditor.ShowDialog(parentWindow) 
     If result = DialogResult.OK Then 
       Return True 
     End If 
     Return False 
   End Function 

   Public Sub Initialize(ByVal dtsComponentMetadata As IDTSComponentMetaData100, ByVal serviceProvider As IServiceProvider) 
     Me.md = dtsComponentMetadata 
   End Sub 
 End Class 

End Namespace
```

### <a name="custom-editor"></a><span data-ttu-id="6de2b-154">Éditeur personnalisé</span><span class="sxs-lookup"><span data-stu-id="6de2b-154">Custom Editor</span></span>
 <span data-ttu-id="6de2b-155">Le code suivant montre l'implémentation du Windows Form affiché lors de l'appel à la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Edit%2A>.</span><span class="sxs-lookup"><span data-stu-id="6de2b-155">The following code shows the implementation of the Windows form that is shown during the call to the <xref:Microsoft.SqlServer.Dts.Pipeline.Design.IDtsComponentUI.Edit%2A> method.</span></span>

```csharp
using System;
using System.Drawing;
using System.Collections;
using System.ComponentModel;
using System.Windows.Forms;
using System.Data;

using Microsoft.SqlServer.Dts.Pipeline.Wrapper;
using Microsoft.SqlServer.Dts.Runtime;

namespace Microsoft.Samples.SqlServer.Dts
{
    public partial class SampleComponentUIForm : System.Windows.Forms.Form
    {
        private Connections connections;
        private Variables variables;
        private IDTSComponentMetaData100 metaData;
        private CManagedComponentWrapper designTimeInstance;
        private System.ComponentModel.IContainer components = null;

        public SampleComponentUIForm( Connections cons, Variables vars, IDTSComponentMetaData100 md)
        {
            variables = vars;
            connections = cons;
            metaData = md;
        }

        private void btnOk_Click(object sender, System.EventArgs e)
        {
            if (designTimeInstance == null)
                designTimeInstance = metaData.Instantiate();

            designTimeInstance.SetComponentProperty( "CustomProperty", txtCustomPropertyValue.Text);

            this.Close();
        }

        private void btnCancel_Click(object sender, System.EventArgs e)
        {
            this.Close();
        }
    }
}
```

```vb
Imports System 
Imports System.Drawing 
Imports System.Collections 
Imports System.ComponentModel 
Imports System.Windows.Forms 
Imports System.Data 
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper 
Imports Microsoft.SqlServer.Dts.Runtime 

Namespace Microsoft.Samples.SqlServer.Dts 

 Public Partial Class SampleComponentUIForm 
  Inherits System.Windows.Forms.Form 
   Private connections As Connections 
   Private variables As Variables 
   Private metaData As IDTSComponentMetaData100 
   Private designTimeInstance As CManagedComponentWrapper 
   Private components As System.ComponentModel.IContainer = Nothing 

   Public Sub New(ByVal cons As Connections, ByVal vars As Variables, ByVal md As IDTSComponentMetaData100) 
     variables = vars 
     connections = cons 
     metaData = md 
   End Sub 

   Private Sub btnOk_Click(ByVal sender As Object, ByVal e As System.EventArgs) 
     If designTimeInstance Is Nothing Then 
       designTimeInstance = metaData.Instantiate 
     End If 
     designTimeInstance.SetComponentProperty("CustomProperty", txtCustomPropertyValue.Text) 
     Me.Close 
   End Sub 

   Private Sub btnCancel_Click(ByVal sender As Object, ByVal e As System.EventArgs) 
     Me.Close 
   End Sub 
 End Class 

End Namespace
```

<span data-ttu-id="6de2b-156">![Icône de Integration Services (petite)](../../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="6de2b-156">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="6de2b-157">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="6de2b-157">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="6de2b-158">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="6de2b-158">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="6de2b-159">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="6de2b-159">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="6de2b-160">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6de2b-160">See Also</span></span>
 [<span data-ttu-id="6de2b-161">Création d'un composant de flux de données personnalisé</span><span class="sxs-lookup"><span data-stu-id="6de2b-161">Creating a Custom Data Flow Component</span></span>](creating-a-custom-data-flow-component.md)


