---
title: Méthodes de conception d’un composant de flux de données | Microsoft Docs
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
- custom data flow components [Integration Services], method execution sequence
- ProcessInput method
- method execution sequence [Integration Services]
- PrimeOutput method
- data flow components [Integration Services], method execution sequence
ms.assetid: b5a121a1-b87c-441b-a42c-2cec628dc81c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e33fc4eb5805318dac217d2c5cbaedfd4bca70fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611917"
---
# <a name="design-time-methods-of-a-data-flow-component"></a><span data-ttu-id="0c632-102">Méthodes de conception d'un composant de flux de données</span><span class="sxs-lookup"><span data-stu-id="0c632-102">Design-time Methods of a Data Flow Component</span></span>
  <span data-ttu-id="0c632-103">Avant l'exécution, la tâche de flux de données est dite au moment de la conception, puisqu'elle subit des modifications incrémentielles.</span><span class="sxs-lookup"><span data-stu-id="0c632-103">Before execution, the data flow task is said to be in a design-time state, as it undergoes incremental changes.</span></span> <span data-ttu-id="0c632-104">Les modifications peuvent inclure l'ajout ou la suppression de composants, l'ajout ou la suppression d'objets de chemin d'accès qui connectent des composants, ainsi que des modifications apportées aux métadonnées des composants.</span><span class="sxs-lookup"><span data-stu-id="0c632-104">Changes may include the addition or removal of components, the addition or removal of the path objects that connect components, and changes to the metadata of the components.</span></span> <span data-ttu-id="0c632-105">Lorsque des modifications de métadonnées se produisent, le composant peut les surveiller et y réagir.</span><span class="sxs-lookup"><span data-stu-id="0c632-105">When metadata changes occur, the component can monitor and react to the changes.</span></span> <span data-ttu-id="0c632-106">Par exemple, un composant peut rejeter certaines modifications ou apporter des modifications supplémentaires en réponse à une modification.</span><span class="sxs-lookup"><span data-stu-id="0c632-106">For example, a component can disallow certain changes or make additional changes in response to a change.</span></span> <span data-ttu-id="0c632-107">Au moment de la conception, le concepteur interagit avec un composant via l'interface <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100> du moment de la conception.</span><span class="sxs-lookup"><span data-stu-id="0c632-107">At design time, the designer interacts with a component through the design-time <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100> interface.</span></span>

## <a name="design-time-implementation"></a><span data-ttu-id="0c632-108">Implémentation au moment de la conception</span><span class="sxs-lookup"><span data-stu-id="0c632-108">Design-Time Implementation</span></span>
 <span data-ttu-id="0c632-109">L'interface de conception d'un composant est décrite par l'interface <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100>.</span><span class="sxs-lookup"><span data-stu-id="0c632-109">The design-time interface of a component is described by the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100> interface.</span></span> <span data-ttu-id="0c632-110">Bien que vous n'implémentiez pas cette interface explicitement, la connaissance des méthodes définies dans cette interface vous aidera à comprendre quelles méthodes de la classe de base <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> correspondent à l'instance de conception d'un composant.</span><span class="sxs-lookup"><span data-stu-id="0c632-110">Although you do not explicitly implement this interface, a familiarity with the methods defined in this interface will help you understand which methods of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> base class correspond to the design-time instance of a component.</span></span>

 <span data-ttu-id="0c632-111">Lorsqu'un composant est chargé dans [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], l'instance de conception du composant est instanciée et les méthodes de l'interface <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100> sont appelées alors que le composant est modifié.</span><span class="sxs-lookup"><span data-stu-id="0c632-111">When a component is loaded in the [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], the design-time instance of the component is instantiated and the methods of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSDesigntimeComponent100> interface are called as the component is edited.</span></span> <span data-ttu-id="0c632-112">L'implémentation de la classe de base vous permet de remplacer uniquement les méthodes que votre composant requiert.</span><span class="sxs-lookup"><span data-stu-id="0c632-112">The implementation of the base class lets you override only those methods that your component requires.</span></span> <span data-ttu-id="0c632-113">Dans de nombreux cas, vous pouvez remplacer ces méthodes pour empêcher des modifications inappropriées d'un composant.</span><span class="sxs-lookup"><span data-stu-id="0c632-113">In many cases, you may override these methods to prevent inappropriate edits to a component.</span></span> <span data-ttu-id="0c632-114">Par exemple, pour empêcher des utilisateurs d'ajouter une sortie à un composant, remplacez la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.InsertOutput%2A>.</span><span class="sxs-lookup"><span data-stu-id="0c632-114">For example, to prevent users from adding an output to a component, override the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.InsertOutput%2A> method.</span></span> <span data-ttu-id="0c632-115">Sinon, lorsque l'implémentation de cette méthode par la classe de base est appelée, elle ajoute une sortie au composant.</span><span class="sxs-lookup"><span data-stu-id="0c632-115">Otherwise, when the implementation of this method by the base class is called, it adds an output to the component.</span></span>

 <span data-ttu-id="0c632-116">Indépendamment de l'objectif ou des fonctionnalités de votre composant, vous devez remplacer les méthodes <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A> et <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReinitializeMetaData%2A>.</span><span class="sxs-lookup"><span data-stu-id="0c632-116">Regardless of the purpose or functionality of your component, you should override the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A>, <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A>, and <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReinitializeMetaData%2A> methods.</span></span> <span data-ttu-id="0c632-117">Pour plus d’informations sur <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A> et <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReinitializeMetaData%2A>, consultez [Validation d’un composant de flux de données](validating-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="0c632-117">For more information about <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A> and <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReinitializeMetaData%2A>, see [Validating a Data Flow Component](validating-a-data-flow-component.md).</span></span>

## <a name="providecomponentproperties-method"></a><span data-ttu-id="0c632-118">Méthode ProvideComponentProperties</span><span class="sxs-lookup"><span data-stu-id="0c632-118">ProvideComponentProperties Method</span></span>
 <span data-ttu-id="0c632-119">L'initialisation d'un composant se produit dans la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A>.</span><span class="sxs-lookup"><span data-stu-id="0c632-119">The initialization of a component occurs in the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> method.</span></span> <span data-ttu-id="0c632-120">Cette méthode est appelée par le Concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] lorsqu'un composant est ajouté à la tâche de flux de données et qu'il est similaire à un constructeur de classe.</span><span class="sxs-lookup"><span data-stu-id="0c632-120">This method is called by [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer when a component is added to the data flow task, and is similar to a class constructor.</span></span> <span data-ttu-id="0c632-121">Les développeurs de composants doivent créer et initialiser leurs entrées, sorties et propriétés personnalisées pendant cet appel de méthode.</span><span class="sxs-lookup"><span data-stu-id="0c632-121">Component developers should create and initialize their inputs, outputs, and custom properties during this method call.</span></span> <span data-ttu-id="0c632-122">La méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> diffère d'un constructeur parce qu'elle n'est pas appelée chaque fois que l'instance de conception ou l'instance d'exécution du composant est instanciée.</span><span class="sxs-lookup"><span data-stu-id="0c632-122">The <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> method differs from a constructor because it is not called every time that the design-time instance or run-time instance of the component is instantiated.</span></span>

 <span data-ttu-id="0c632-123">L'implémentation de la classe de base de la méthode ajoute une entrée et une sortie au composant et attribue l'ID de l'entrée à la propriété <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.SynchronousInputID%2A>.</span><span class="sxs-lookup"><span data-stu-id="0c632-123">The base class implementation of the method adds an input and an output to the component and assigns the ID of the input to the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.SynchronousInputID%2A> property.</span></span> <span data-ttu-id="0c632-124">Toutefois, les objets d'entrée et de sortie ajoutés par la classe de base ne sont pas nommés dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0c632-124">However, in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], the input and output objects added by the base class are not named.</span></span> <span data-ttu-id="0c632-125">Les packages qui contiennent un composant avec des objets d’entrée ou de sortie dont la propriété Name n’est pas définie ne se chargeront pas correctement.</span><span class="sxs-lookup"><span data-stu-id="0c632-125">Packages that contain a component with input or output objects whose Name property is not set will not successfully load.</span></span> <span data-ttu-id="0c632-126">Par conséquent, lorsque vous utilisez l’implémentation de base, vous devez attribuer explicitement des valeurs à la propriété Name de l’entrée ou la sortie par défaut.</span><span class="sxs-lookup"><span data-stu-id="0c632-126">Therefore, when you use the base implementation, you must assign values explicitly to the Name property of the default input and output.</span></span>

```csharp
public override void ProvideComponentProperties()
{
    /// TODO: Reset the component.
    /// TODO: Add custom properties.
    /// TODO: Add input objects.
    /// TODO: Add output objects.
}
```

```vb
Public Overrides Sub ProvideComponentProperties()
    ' TODO: Reset the component.
    ' TODO: Add custom properties.
    ' TODO: Add input objects.
    ' TODO: Add output objects.
End Sub
```

### <a name="creating-custom-properties"></a><span data-ttu-id="0c632-127">Création de propriétés personnalisées</span><span class="sxs-lookup"><span data-stu-id="0c632-127">Creating Custom Properties</span></span>
 <span data-ttu-id="0c632-128">L'appel de la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> est l'emplacement auquel les développeurs de composants doivent ajouter des propriétés personnalisées (<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100>) au composant.</span><span class="sxs-lookup"><span data-stu-id="0c632-128">The call to the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ProvideComponentProperties%2A> method is where component developers should add custom properties (<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100>) to the component.</span></span> <span data-ttu-id="0c632-129">Les propriétés personnalisées n'ont pas de propriété de type de données.</span><span class="sxs-lookup"><span data-stu-id="0c632-129">Custom properties do not have a data type property.</span></span> <span data-ttu-id="0c632-130">Le type de données d'une propriété personnalisée est défini par le type de données de la valeur que vous attribuez à sa propriété <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.Value%2A>.</span><span class="sxs-lookup"><span data-stu-id="0c632-130">The data type of a custom property is set by the data type of the value that you assign to its <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.Value%2A> property.</span></span> <span data-ttu-id="0c632-131">Toutefois, après avoir attribué une valeur initiale à la propriété personnalisée, vous ne pouvez pas attribuer une valeur dont le type de données est différent.</span><span class="sxs-lookup"><span data-stu-id="0c632-131">However, after you have assigned an initial value to the custom property, you cannot assign a value with a different data type.</span></span>

> [!NOTE]
>  <span data-ttu-id="0c632-132">L'interface <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100> offre une prise en charge limitée des valeurs de propriétés de type `Object`.</span><span class="sxs-lookup"><span data-stu-id="0c632-132">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100> interface has limited support for property values of type `Object`.</span></span> <span data-ttu-id="0c632-133">Le seul objet que vous pouvez stocker en tant que valeur d'une propriété personnalisée est un tableau de types simples tels que des chaînes ou des entiers.</span><span class="sxs-lookup"><span data-stu-id="0c632-133">The only object that you can store as the value of a custom property is an array of simple types such as strings or integers.</span></span>

 <span data-ttu-id="0c632-134">Vous pouvez indiquer que votre propriété personnalisée prend en charge des expressions de propriété en définissant la valeur de sa propriété <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.ExpressionType%2A> sur `CPET_NOTIFY` à partir de l'énumération <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSCustomPropertyExpressionType>, comme indiqué dans l'exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="0c632-134">You can indicate that your custom property supports property expressions by setting the value of its <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.ExpressionType%2A> property to `CPET_NOTIFY` from the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSCustomPropertyExpressionType> enumeration, as shown in the following example.</span></span> <span data-ttu-id="0c632-135">Vous ne devez pas ajouter de code pour gérer ou valider l'expression de propriété entrée par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0c632-135">You do not have to add any code to handle or to validate the property expression entered by the user.</span></span> <span data-ttu-id="0c632-136">Vous pouvez définir une valeur par défaut pour la propriété, validez sa valeur, ainsi que lire et utiliser normalement sa valeur.</span><span class="sxs-lookup"><span data-stu-id="0c632-136">You can set a default value for the property, validate its value, and read and use its value normally.</span></span>

```csharp
IDTSCustomProperty100 myCustomProperty;
...
myCustomProperty.ExpressionType = DTSCustomPropertyExpressionType.CPET_NOTIFY;
```

```vb
Dim myCustomProperty As IDTSCustomProperty100
...
myCustomProperty.ExpressionType = DTSCustomPropertyExpressionType.CPET_NOTIFY
```

 <span data-ttu-id="0c632-137">Vous pouvez limiter les utilisateurs à la sélection d’une valeur de propriété personnalisée à partir d’une énumération à l’aide de la <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.TypeConverter%2A> propriété, comme indiqué dans l’exemple suivant, qui suppose que vous avez défini une énumération publique nommée `MyValidValues` .</span><span class="sxs-lookup"><span data-stu-id="0c632-137">You can limit users to selecting a custom property value from an enumeration by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.TypeConverter%2A> property, as shown in the following example, which assumes that you have defined a public enumeration named `MyValidValues`.</span></span>

```csharp
IDTSCustomProperty100 customProperty = outputColumn.CustomPropertyCollection.New();
customProperty.Name = "My Custom Property";
// This line associates the type with the custom property.
customProperty.TypeConverter = typeof(MyValidValues).AssemblyQualifiedName;
// Now you can use the enumeration values directly.
customProperty.Value = MyValidValues.ValueOne;  
```

```vb
Dim customProperty As IDTSCustomProperty100 = outputColumn.CustomPropertyCollection.New 
customProperty.Name = "My Custom Property" 
' This line associates the type with the custom property.
customProperty.TypeConverter = GetType(MyValidValues).AssemblyQualifiedName 
' Now you can use the enumeration values directly.
customProperty.Value = MyValidValues.ValueOne
```

 <span data-ttu-id="0c632-138">Pour plus d’informations, consultez « Conversion de type généralisée » et « Implémentation d’un convertisseur de type » dans la [MSDN Library](https://go.microsoft.com/fwlink/?LinkId=7022).</span><span class="sxs-lookup"><span data-stu-id="0c632-138">For more information, see "Generalized Type Conversion" and "Implementing a Type Converter" in the [MSDN Library](https://go.microsoft.com/fwlink/?LinkId=7022).</span></span>

 <span data-ttu-id="0c632-139">Vous pouvez spécifier une boîte de dialogue d'éditeur personnalisée pour la valeur de votre propriété personnalisée en utilisant la propriété <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.UITypeEditor%2A>, comme indiqué dans l'exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="0c632-139">You can specify a custom editor dialog box for the value of your custom property by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.UITypeEditor%2A> property, as shown in the following example.</span></span> <span data-ttu-id="0c632-140">Tout d'abord, vous devez créer un éditeur de type personnalisé qui hérite de `System.Drawing.Design.UITypeEditor`, si vous ne pouvez pas localiser une classe existante d'éditeur de types muni d'une interface utilisateur qui répond à vos besoins.</span><span class="sxs-lookup"><span data-stu-id="0c632-140">First, you must create a custom type editor that inherits from `System.Drawing.Design.UITypeEditor`, if you cannot locate an existing UI type editor class that fits your needs.</span></span>

```csharp
public class MyCustomTypeEditor : UITypeEditor
{
...
}
```

```vb
Public Class MyCustomTypeEditor
  Inherits UITypeEditor 
  ...
End Class
```

 <span data-ttu-id="0c632-141">Ensuite, spécifiez cette classe en tant que valeur de la propriété <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.UITypeEditor%2A> de votre propriété personnalisée.</span><span class="sxs-lookup"><span data-stu-id="0c632-141">Next, specify this class as the value of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSCustomProperty100.UITypeEditor%2A> property of your custom property.</span></span>

```csharp
IDTSCustomProperty100 customProperty = outputColumn.CustomPropertyCollection.New();
customProperty.Name = "My Custom Property";
// This line associates the editor with the custom property.
customProperty.UITypeEditor = typeof(MyCustomTypeEditor).AssemblyQualifiedName;
```

```vb
Dim customProperty As IDTSCustomProperty100 = outputColumn.CustomPropertyCollection.New 
customProperty.Name = "My Custom Property" 
' This line associates the editor with the custom property.
customProperty.UITypeEditor = GetType(MyCustomTypeEditor).AssemblyQualifiedName
```

 <span data-ttu-id="0c632-142">Pour plus d’informations, consultez « Implémentation d’un éditeur de type d’interface utilisateur » dans [MSDN Library](https://go.microsoft.com/fwlink/?LinkId=7022).</span><span class="sxs-lookup"><span data-stu-id="0c632-142">For more information, see "Implementing a UI Type Editor" in the [MSDN Library](https://go.microsoft.com/fwlink/?LinkId=7022).</span></span>

<span data-ttu-id="0c632-143">![Icône de Integration Services (petite)](../../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="0c632-143">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="0c632-144">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="0c632-144">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="0c632-145">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="0c632-145">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="0c632-146">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="0c632-146">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="0c632-147">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0c632-147">See Also</span></span>
 [<span data-ttu-id="0c632-148">Méthodes d'exécution d'un composant de flux de données</span><span class="sxs-lookup"><span data-stu-id="0c632-148">Run-time Methods of a Data Flow Component</span></span>](run-time-methods-of-a-data-flow-component.md)


