---
title: Création d’un composant au moment de la conception d’éléments de rapport personnalisé | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- custom report items, creating
ms.assetid: 323fd58a-a462-4c48-b188-77ebc0b4212e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b663dc3b0a9c54d1674bf153ee09dd36e0de7a00
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600656"
---
# <a name="creating-a-custom-report-item-design-time-component"></a><span data-ttu-id="63ea0-102">Création d'un composant au moment de la conception d'élément de rapport personnalisé</span><span class="sxs-lookup"><span data-stu-id="63ea0-102">Creating a Custom Report Item Design-Time Component</span></span>
  <span data-ttu-id="63ea0-103">Un composant au moment de la conception d'élément de rapport personnalisé est un contrôle qui peut être utilisé dans l'environnement du Concepteur de rapports Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="63ea0-103">A custom report item design-time component is a control that can be used in the Visual Studio Report Designer environment.</span></span> <span data-ttu-id="63ea0-104">Le composant au moment de la conception d'élément de rapport personnalisé fournit une aire de conception activée qui prend en charge les opérations de glisser-déplacer et l'intégration avec l'Explorateur de propriétés [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], tout en fournissant des éditeurs de propriété personnalisée.</span><span class="sxs-lookup"><span data-stu-id="63ea0-104">The custom report item design-time component provides an activated design surface that can accept drag-and-drop operations, integration with the [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] property browser, and the ability to provide custom property editors.</span></span>  
  
 <span data-ttu-id="63ea0-105">Avec un composant au moment de la conception d'élément de rapport personnalisé, l'utilisateur peut positionner un élément de rapport personnalisé sur un rapport dans l'environnement de conception, définir des propriétés de données personnalisées sur l'élément de rapport personnalisé, puis enregistrer cet élément en tant que partie du projet de rapport.</span><span class="sxs-lookup"><span data-stu-id="63ea0-105">With a custom report item design-time component, the user can position a custom report item on a report in the design environment, set custom data properties on the custom report item, and then save the custom report item as part of the report project.</span></span>  
  
 <span data-ttu-id="63ea0-106">Les propriétés définies à l'aide du composant au moment de la conception dans l'environnement de développement sont sérialisées et désérialisées par l'environnement de conception hôte, puis stockées comme éléments dans le fichier RDL (Report Definition Language).</span><span class="sxs-lookup"><span data-stu-id="63ea0-106">The properties that are set using the design-time component in the development environment are serialized and deserialized by the host design environment and then stored as elements in the Report Definition Language (RDL) file.</span></span> <span data-ttu-id="63ea0-107">Lorsque le rapport est exécuté par le processeur de rapports, les propriétés définies à l'aide du composant au moment de la conception sont passées par le processeur de rapports à un composant d'exécution d'élément de rapport personnalisé, qui génère l'élément de rapport personnalisé et le repasse au processeur de rapports.</span><span class="sxs-lookup"><span data-stu-id="63ea0-107">When the report is executed by the report processor, the properties that are set using the design-time component are passed by the report processor to a custom report item run-time component, which renders the custom report item and passes it back to the report processor.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="63ea0-108">Le composant au moment de la conception d’élément de rapport personnalisé est implémenté en tant que composant [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="63ea0-108">The custom report item design-time component is implemented as a [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] component.</span></span> <span data-ttu-id="63ea0-109">Ce document décrit les détails d'implémentation spécifiques au composant au moment de la conception d'élément de rapport personnalisé.</span><span class="sxs-lookup"><span data-stu-id="63ea0-109">This document will describe implementation details specific to the custom report item design-time component.</span></span> <span data-ttu-id="63ea0-110">Pour plus d’informations sur le développement de composants à l’aide de [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], consultez [Composants dans Visual Studio](https://go.microsoft.com/fwlink/?LinkId=116576) dans MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="63ea0-110">For more information about developing components using the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], see [Components in Visual Studio](https://go.microsoft.com/fwlink/?LinkId=116576) in the MSDN library.</span></span>  
  
 <span data-ttu-id="63ea0-111">Pour un exemple d’élément de rapport personnalisé totalement implémenté, consultez [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889) (Exemples Reporting Services pour le produit SQL Server).</span><span class="sxs-lookup"><span data-stu-id="63ea0-111">For a sample of a fully implemented custom report item, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="implementing-a-design-time-component"></a><span data-ttu-id="63ea0-112">Implémentation d'un composant au moment de la conception</span><span class="sxs-lookup"><span data-stu-id="63ea0-112">Implementing a Design-Time Component</span></span>  
 <span data-ttu-id="63ea0-113">La classe principale d'un composant au moment de la conception d'élément de rapport personnalisé est héritée de la classe `Microsoft.ReportDesigner.CustomReportItemDesigner`.</span><span class="sxs-lookup"><span data-stu-id="63ea0-113">The main class of a custom report item design-time component is inherited from the `Microsoft.ReportDesigner.CustomReportItemDesigner` class.</span></span> <span data-ttu-id="63ea0-114">En plus des attributs standard utilisés pour un contrôle [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], votre classe de composant doit définir un attribut `CustomReportItem`.</span><span class="sxs-lookup"><span data-stu-id="63ea0-114">In addition to the standard attributes used for a [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] control, your component class should define a `CustomReportItem` attribute.</span></span> <span data-ttu-id="63ea0-115">Cet attribut doit correspondre au nom de l'élément de rapport personnalisé tel que défini dans le fichier reportserver.config.</span><span class="sxs-lookup"><span data-stu-id="63ea0-115">This attribute must correspond to the name of the custom report item as it is defined in the reportserver.config file.</span></span> <span data-ttu-id="63ea0-116">Pour obtenir une liste des attributs [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], consultez la section Attributs dans la documentation du SDK du [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="63ea0-116">For a list of [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] attributes, see Attributes in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK documentation.</span></span>  
  
 <span data-ttu-id="63ea0-117">L'exemple de code suivant illustre l'application d'attributs à un contrôle au moment de la conception d'élément de rapport personnalisé :</span><span class="sxs-lookup"><span data-stu-id="63ea0-117">The following code example shows attributes being applied to a custom report item design-time control:</span></span>  
  
```csharp  
namespace PolygonsCRI  
{  
    [LocalizedName("Polygons")]  
    [Editor(typeof(CustomEditor), typeof(ComponentEditor))]  
        [ToolboxBitmap(typeof(PolygonsDesigner),"Polygons.ico")]  
        [CustomReportItem("Polygons")]  
  
    public class PolygonsDesigner : CustomReportItemDesigner  
    {  
...  
```  
  
### <a name="initializing-the-component"></a><span data-ttu-id="63ea0-118">Initialisation du composant</span><span class="sxs-lookup"><span data-stu-id="63ea0-118">Initializing the Component</span></span>  
 <span data-ttu-id="63ea0-119">Pour passer des propriétés spécifiées par l'utilisateur pour un élément de rapport personnalisé, une classe <xref:Microsoft.ReportingServices.RdlObjectModel.CustomData> doit être utilisée.</span><span class="sxs-lookup"><span data-stu-id="63ea0-119">You pass user-specified properties for a custom report item using a <xref:Microsoft.ReportingServices.RdlObjectModel.CustomData> class.</span></span> <span data-ttu-id="63ea0-120">Votre implémentation de la classe `CustomReportItemDesigner` doit se substituer à la méthode `InitializeNewComponent` pour créer une nouvelle instance de la classe <xref:Microsoft.ReportingServices.RdlObjectModel.CustomData> de votre composant et lui attribuer les valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="63ea0-120">Your implementation of the `CustomReportItemDesigner` class should override the `InitializeNewComponent` method to create a new instance of your component's <xref:Microsoft.ReportingServices.RdlObjectModel.CustomData> class and set it to default values.</span></span>  
  
 <span data-ttu-id="63ea0-121">L'exemple de code suivant illustre la substitution de la méthode `CustomReportItemDesigner.InitializeNewComponent` par une classe de composant au moment de la conception d'élément de rapport personnalisé pour initialiser la classe <xref:Microsoft.ReportingServices.RdlObjectModel.CustomData> du composant :</span><span class="sxs-lookup"><span data-stu-id="63ea0-121">The following code example shows an example of a custom report item design-time component class overriding the `CustomReportItemDesigner.InitializeNewComponent` method to initialize the component's <xref:Microsoft.ReportingServices.RdlObjectModel.CustomData> class:</span></span>  
  
```csharp  
public override void InitializeNewComponent()  
        {  
            CustomData = new CustomData();  
            CustomData.DataRowHierarchy = new DataHierarchy();  
  
            // Shape grouping  
            CustomData.DataRowHierarchy.DataMembers.Add(new DataMember());  
            CustomData.DataRowHierarchy.DataMembers[0].Group = new Group();  
            CustomData.DataRowHierarchy.DataMembers[0].Group.Name = Name + "_Shape";  
            CustomData.DataRowHierarchy.DataMembers[0].Group.GroupExpressions.Add(new ReportExpression());  
  
            // Point grouping  
            CustomData.DataRowHierarchy.DataMembers[0].DataMembers.Add(new DataMember());  
            CustomData.DataRowHierarchy.DataMembers[0].DataMembers[0].Group = new Group();  
            CustomData.DataRowHierarchy.DataMembers[0].DataMembers[0].Group.Name = Name + "_Point";  
            CustomData.DataRowHierarchy.DataMembers[0].DataMembers[0].Group.GroupExpressions.Add(new ReportExpression());  
  
            // Static column  
            CustomData.DataColumnHierarchy = new DataHierarchy();  
            CustomData.DataColumnHierarchy.DataMembers.Add(new DataMember());  
  
            // Points  
            IList<IList<DataValue>> dataValues = new List<IList<DataValue>>();  
            CustomData.DataRows.Add(dataValues);  
            CustomData.DataRows[0].Add(new List<DataValue>());  
            CustomData.DataRows[0][0].Add(NewDataValue("X", ""));  
            CustomData.DataRows[0][0].Add(NewDataValue("Y", ""));  
        }  
```  
  
### <a name="modifying-component-properties"></a><span data-ttu-id="63ea0-122">Modification des propriétés du composant</span><span class="sxs-lookup"><span data-stu-id="63ea0-122">Modifying Component Properties</span></span>  
 <span data-ttu-id="63ea0-123">Vous pouvez modifier les propriétés `CustomData` de plusieurs façons dans l'environnement de conception.</span><span class="sxs-lookup"><span data-stu-id="63ea0-123">You can modify `CustomData` properties in the design environment in several ways.</span></span> <span data-ttu-id="63ea0-124">Vous pouvez modifier toute propriété exposée par le composant au moment de la conception et marquée avec l'attribut <xref:System.ComponentModel.BrowsableAttribute>, à l'aide de l'Explorateur de propriétés [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="63ea0-124">You can modify any properties that are exposed by the design-time component that are marked with the <xref:System.ComponentModel.BrowsableAttribute> attribute by using the [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] property browser.</span></span> <span data-ttu-id="63ea0-125">Vous pouvez également modifier des propriétés en faisant glisser des éléments vers l’aire de conception de l’élément de rapport personnalisé ou en cliquant avec le bouton droit sur le contrôle dans l’environnement de conception et en sélectionnant **Propriétés** dans le menu contextuel pour afficher une fenêtre de propriétés personnalisées.</span><span class="sxs-lookup"><span data-stu-id="63ea0-125">In addition, you can modify properties by dragging items onto the custom report item's design surface, or by right-clicking the control in the design environment and selecting **Properties** on the shortcut menu to display a custom properties window.</span></span>  
  
 <span data-ttu-id="63ea0-126">L'exemple de code suivant illustre une propriété `Microsoft.ReportDesigner.CustomReportItemDesigner.CustomData` à laquelle est appliqué l'attribut <xref:System.ComponentModel.BrowsableAttribute>.</span><span class="sxs-lookup"><span data-stu-id="63ea0-126">The following code example shows a `Microsoft.ReportDesigner.CustomReportItemDesigner.CustomData` property that has the <xref:System.ComponentModel.BrowsableAttribute> attribute applied:</span></span>  
  
```csharp  
[Browsable(true), Category("Data")]  
public string DataSetName  
{  
      get  
      {  
         return CustomData.DataSetName;  
      }  
      set  
      {  
         CustomData.DataSetName = value;  
      }  
   }  
  
```  
  
 <span data-ttu-id="63ea0-127">Vous pouvez fournir votre composant au moment de la conception avec une boîte de dialogue d'éditeur de propriétés personnalisées.</span><span class="sxs-lookup"><span data-stu-id="63ea0-127">You can provide your design-time component with a custom properties editor dialog box.</span></span> <span data-ttu-id="63ea0-128">L'implémentation d'éditeur de propriétés personnalisées doit hériter de la classe <xref:System.ComponentModel.ComponentEditor> et doit créer une instance d'une boîte de dialogue destinée à l'édition de propriétés.</span><span class="sxs-lookup"><span data-stu-id="63ea0-128">The custom property editor implementation should inherit from the <xref:System.ComponentModel.ComponentEditor> class, and it should create an instance of a dialog box that can be used for property editing.</span></span>  
  
 <span data-ttu-id="63ea0-129">L'exemple suivant montre l'implémentation d'une classe qui hérite de <xref:System.ComponentModel.ComponentEditor> et ouvre une boîte de dialogue d'éditeur de propriétés personnalisées :</span><span class="sxs-lookup"><span data-stu-id="63ea0-129">The following example shows an implementation of a class that inherits from <xref:System.ComponentModel.ComponentEditor> and displays a custom property editor dialog box:</span></span>  
  
```csharp  
internal sealed class CustomEditor : ComponentEditor  
{  
   public override bool EditComponent(  
      ITypeDescriptorContext context, object component)  
    {  
     PolygonsDesigner designer = (PolygonsDesigner)component;  
     PolygonProperties dialog = new PolygonProperties();  
     dialog.m_designerComponent = designer;  
     DialogResult result = dialog.ShowDialog();  
     if (result == DialogResult.OK)  
     {  
        designer.Invalidate();  
        designer.ChangeService().OnComponentChanged(designer, null, null, null);  
        return true;  
     }  
     else  
        return false;  
    }  
}  
```  
  
 <span data-ttu-id="63ea0-130">Votre boîte de dialogue d'éditeur de propriétés personnalisées peut appeler l'Éditeur d'expressions du Concepteur de rapports.</span><span class="sxs-lookup"><span data-stu-id="63ea0-130">Your custom property editor dialog box can invoke the Report Designer Expression Editor.</span></span> <span data-ttu-id="63ea0-131">Dans l'exemple suivant, l'Éditeur d'expressions est appelé lorsque l'utilisateur sélectionne le premier élément dans la zone de liste déroulante :</span><span class="sxs-lookup"><span data-stu-id="63ea0-131">In the following example, the Expression Editor is invoked when the user selects the first element in the combo box:</span></span>  
  
```csharp  
private void EditableCombo_SelectedIndexChanged(object sender,   
    EventArgs e)  
{  
   ComboBox combo = (ComboBox)sender;  
   if (combo.SelectedIndex == 0 && m_launchEditor)  
   {  
      m_launchEditor = false;  
      ExpressionEditor editor = new ExpressionEditor();  
      string newValue;  
      newValue = (string)editor.EditValue(null, m_designerComponent.Site, m_oldComboValue);  
      combo.Items[0] = newValue;  
   }  
}  
  
```  
  
### <a name="using-designer-verbs"></a><span data-ttu-id="63ea0-132">Utilisation des verbes de concepteur</span><span class="sxs-lookup"><span data-stu-id="63ea0-132">Using Designer Verbs</span></span>  
 <span data-ttu-id="63ea0-133">Un verbe de concepteur est une commande de menu liée à un gestionnaire d'événements.</span><span class="sxs-lookup"><span data-stu-id="63ea0-133">A designer verb is a menu command linked to an event handler.</span></span> <span data-ttu-id="63ea0-134">Vous pouvez ajouter des verbes de concepteur qui apparaîtront dans le menu contextuel d'un composant lorsque votre contrôle au moment de l'exécution d'élément de rapport personnalisé est utilisé dans l'environnement de conception.</span><span class="sxs-lookup"><span data-stu-id="63ea0-134">You can add designer verbs that will appear in a component's shortcut menu when your custom report item run-time control is being used in the design environment.</span></span> <span data-ttu-id="63ea0-135">Vous pouvez retourner la liste des verbes de concepteur disponibles de votre composant d'exécution à l'aide de la propriété `Verbs`.</span><span class="sxs-lookup"><span data-stu-id="63ea0-135">You can return the list of available designer verbs from your run-time component by using the `Verbs` property.</span></span>  
  
 <span data-ttu-id="63ea0-136">L'exemple de code suivant illustre l'ajout d'un verbe de concepteur et d'un gestionnaire d'événements au <xref:System.ComponentModel.Design.DesignerVerbCollection>, ainsi que le code du gestionnaire d'événements :</span><span class="sxs-lookup"><span data-stu-id="63ea0-136">The following code example shows a designer verb and an event handler being added to the <xref:System.ComponentModel.Design.DesignerVerbCollection>, as well as the event handler code:</span></span>  
  
```csharp  
public override DesignerVerbCollection Verbs  
{  
    get  
    {  
        if (m_verbs == null)  
        {  
            m_verbs = new DesignerVerbCollection();  
            m_verbs.Add(new DesignerVerb("Proportional Scaling", new EventHandler(OnProportionalScaling)));  
         m_verbs[0].Checked = (GetCustomProperty("poly:Proportional") == bool.TrueString);  
        }  
  
        return m_verbs;  
    }  
}  
  
private void OnProportionalScaling(object sender, EventArgs e)  
{  
   bool proportional = !  
        (GetCustomProperty("poly:Proportional") == bool.TrueString);  
   m_verbs[0].Checked = proportional;  
   SetCustomProperty("poly:Proportional", proportional.ToString());  
   ChangeService().OnComponentChanged(this, null, null, null);  
   Invalidate();  
}  
```  
  
### <a name="using-adornments"></a><span data-ttu-id="63ea0-137">Utilisation d'ornements</span><span class="sxs-lookup"><span data-stu-id="63ea0-137">Using Adornments</span></span>  
 <span data-ttu-id="63ea0-138">Les classes d'éléments de rapport personnalisés peuvent également implémenter une classe `Microsoft.ReportDesigner.Design.Adornment`.</span><span class="sxs-lookup"><span data-stu-id="63ea0-138">Custom report item classes can also implement a `Microsoft.ReportDesigner.Design.Adornment` class.</span></span> <span data-ttu-id="63ea0-139">Un ornement permet au contrôle d'élément de rapport personnalisé de fournir des zones à l'extérieur du rectangle principal de l'aire de conception.</span><span class="sxs-lookup"><span data-stu-id="63ea0-139">An adornment allows the custom report item control to provide areas outside the main rectangle of the design surface.</span></span> <span data-ttu-id="63ea0-140">Ces zones permettent de gérer les événements de l'interface utilisateur, tels que les clics de souris et les opérations de glisser-déplacer.</span><span class="sxs-lookup"><span data-stu-id="63ea0-140">These areas can handle user interface events, such as mouse clicks and drag-and-drop operations.</span></span> <span data-ttu-id="63ea0-141">La `Adornment` classe définie dans l' [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] `Microsoft.ReportDesigner` espace de noms est une implémentation directe de la <xref:System.Windows.Forms.Design.Behavior.Adorner> classe trouvée dans Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="63ea0-141">The `Adornment` class that is defined in the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] `Microsoft.ReportDesigner` namespace is a pass-through implementation of the <xref:System.Windows.Forms.Design.Behavior.Adorner> class found in Windows Forms.</span></span> <span data-ttu-id="63ea0-142">Pour obtenir une documentation complète sur la `Adorner` classe, consultez [vue d’ensemble du service de comportement](https://go.microsoft.com/fwlink/?LinkId=116673) dans MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="63ea0-142">For complete documentation on the `Adorner` class, see [Behavior Service Overview](https://go.microsoft.com/fwlink/?LinkId=116673) in the MSDN library.</span></span> <span data-ttu-id="63ea0-143">Pour obtenir un exemple de code qui implémente une `Microsoft.ReportDesigner.Design.Adornment` classe, consultez [SQL Server Reporting Services les exemples de produits](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="63ea0-143">For sample code that implements a `Microsoft.ReportDesigner.Design.Adornment` class, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
 <span data-ttu-id="63ea0-144">Pour plus d'informations sur la programmation et l'utilisation de Windows Forms dans [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], consultez les rubriques suivantes dans MSDN Library :</span><span class="sxs-lookup"><span data-stu-id="63ea0-144">For more information about programming and using Windows Forms in [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], see these topics in the MSDN Library:</span></span>  
  
-   <span data-ttu-id="63ea0-145">Attributs au moment de la conception pour les composants</span><span class="sxs-lookup"><span data-stu-id="63ea0-145">Design-Time Attributes for Components</span></span>  
  
-   <span data-ttu-id="63ea0-146">Composants dans [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63ea0-146">Components in [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]</span></span>  
  
-   <span data-ttu-id="63ea0-147">Procédure pas à pas : création d'un contrôle Windows Forms qui tire parti des fonctionnalités au moment de la conception de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="63ea0-147">Walkthrough: Creating a Windows Forms Control that Takes Advantage of Visual Studio Design-Time Features</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63ea0-148">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="63ea0-148">See Also</span></span>  
 <span data-ttu-id="63ea0-149">[Architecture des éléments de rapports personnalisés](custom-report-item-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="63ea0-149">[Custom Report Item Architecture](custom-report-item-architecture.md) </span></span>  
 <span data-ttu-id="63ea0-150">[Création d’un composant d’exécution d’élément de rapport personnalisé](creating-a-custom-report-item-run-time-component.md) </span><span class="sxs-lookup"><span data-stu-id="63ea0-150">[Creating a Custom Report Item Run-Time Component](creating-a-custom-report-item-run-time-component.md) </span></span>  
 <span data-ttu-id="63ea0-151">[Bibliothèques de classes d’éléments de rapports personnalisés](custom-report-item-class-libraries.md) </span><span class="sxs-lookup"><span data-stu-id="63ea0-151">[Custom Report Item Class Libraries](custom-report-item-class-libraries.md) </span></span>  
 [<span data-ttu-id="63ea0-152">Procédure : déployer un élément de rapport personnalisé</span><span class="sxs-lookup"><span data-stu-id="63ea0-152">How to: Deploy a Custom Report Item</span></span>](how-to-deploy-a-custom-report-item.md)  
  
  
