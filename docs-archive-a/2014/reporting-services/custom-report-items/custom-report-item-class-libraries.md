---
title: Bibliothèques de classes d’éléments de rapport personnalisés | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- custom report items, RDL
- RDL [Reporting Services], custom report items
ms.assetid: f18c5d8f-1d6b-4f0b-8657-c14896c2ce0d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 60f8cf912eb6ff3f5080e9cf757df40f37e65079
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600654"
---
# <a name="custom-report-item-class-libraries"></a><span data-ttu-id="2de9a-102">Bibliothèques de classes d'éléments de rapport personnalisés</span><span class="sxs-lookup"><span data-stu-id="2de9a-102">Custom Report Item Class Libraries</span></span>
  <span data-ttu-id="2de9a-103">Les éléments de rapport personnalisés utilisent des classes de l'espace de noms `Microsoft.ReportDesigner`.</span><span class="sxs-lookup"><span data-stu-id="2de9a-103">Custom report items use classes from the `Microsoft.ReportDesigner` namespace.</span></span> <span data-ttu-id="2de9a-104">Les classes utilisées pour implémenter un élément de rapport personnalisé peuvent être divisées en deux catégories principales : les classes uniques conçues pour prendre en charge l'infrastructure d'éléments de rapport personnalisés et les classes wrapper managées qui encapsulent les fonctionnalités d'éléments RDL (Report Definition Language) pertinents.</span><span class="sxs-lookup"><span data-stu-id="2de9a-104">The classes used to implement a custom report item can be grouped into two main categories: unique classes designed to support custom report item infrastructure, and managed wrapper classes that encapsulate the functionality of relevant Report Definition Language (RDL) elements.</span></span> <span data-ttu-id="2de9a-105">Pour un exemple de code montrant comment utiliser ces classes, consultez [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889) (Exemples Reporting Services pour le produit SQL Server).</span><span class="sxs-lookup"><span data-stu-id="2de9a-105">For a code sample on how to use these classes, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="custom-report-item-infrastructure-classes"></a><span data-ttu-id="2de9a-106">Classes d'infrastructure d'éléments de rapport personnalisés</span><span class="sxs-lookup"><span data-stu-id="2de9a-106">Custom Report Item Infrastructure Classes</span></span>  
 <span data-ttu-id="2de9a-107">Les classes suivantes sont utilisées pour implémenter un élément de rapport personnalisé.</span><span class="sxs-lookup"><span data-stu-id="2de9a-107">The following classes are used to implement a custom report item.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2de9a-108">Les tableaux suivants ne contiennent pas de listes exhaustives. Ils répertorient uniquement les propriétés les plus utilisées, ainsi que les méthodes de chaque classe.</span><span class="sxs-lookup"><span data-stu-id="2de9a-108">The following tables are not complete listings; they include only the most commonly used properties and methods for each class.</span></span>  
  
### <a name="microsoftreportdesignercustomreportitemdesigner"></a><span data-ttu-id="2de9a-109">Microsoft.ReportDesigner.CustomReportItemDesigner</span><span class="sxs-lookup"><span data-stu-id="2de9a-109">Microsoft.ReportDesigner.CustomReportItemDesigner</span></span>  
 <span data-ttu-id="2de9a-110">Cette classe correspond à la principale classe d'élément de rapport personnalisé.</span><span class="sxs-lookup"><span data-stu-id="2de9a-110">This is the main custom report item class.</span></span> <span data-ttu-id="2de9a-111">La principale classe de votre implémentation d'élément de rapport personnalisé doit hériter de cette classe.</span><span class="sxs-lookup"><span data-stu-id="2de9a-111">The main class of your custom report item implementation must inherit from this class.</span></span>  
  
#### <a name="public-properties"></a><span data-ttu-id="2de9a-112">Propri&#233;t&#233;s publiques</span><span class="sxs-lookup"><span data-stu-id="2de9a-112">Public Properties</span></span>  
  
|||  
|-|-|  
|`Name`|<span data-ttu-id="2de9a-113">Nom de l'élément de rapport personnalisé.</span><span class="sxs-lookup"><span data-stu-id="2de9a-113">The name of the custom report item.</span></span>|  
|`Type`|<span data-ttu-id="2de9a-114">Type de l'élément de rapport personnalisé.</span><span class="sxs-lookup"><span data-stu-id="2de9a-114">The type of the custom report item.</span></span>|  
|`CustomData`|<span data-ttu-id="2de9a-115">Objet <xref:Microsoft.ReportingServices.RdlObjectModel.CustomData> qui encapsule les propriétés des données de l'élément de rapport personnalisé, spécifiées au moment de la conception.</span><span class="sxs-lookup"><span data-stu-id="2de9a-115">A <xref:Microsoft.ReportingServices.RdlObjectModel.CustomData> object that encapsulates the custom report item data properties specified at design time.</span></span>|  
|`CustomProperties`|<span data-ttu-id="2de9a-116">Collection de propriétés personnalisées destinées à l'élément de rapport personnalisé.</span><span class="sxs-lookup"><span data-stu-id="2de9a-116">A collection of custom properties for the custom report item.</span></span>|  
|`Height`|<span data-ttu-id="2de9a-117">Hauteur du contrôle de l'élément de rapport personnalisé.</span><span class="sxs-lookup"><span data-stu-id="2de9a-117">The height of the custom report item control.</span></span>|  
|`Width`|<span data-ttu-id="2de9a-118">Largeur du contrôle de l'élément de rapport personnalisé.</span><span class="sxs-lookup"><span data-stu-id="2de9a-118">The width of the custom report item control.</span></span>|  
|`Report`|<span data-ttu-id="2de9a-119">Conteneur pour les propriétés figurant au niveau du rapport, telles que la liste des datasets contenus dans ce rapport.</span><span class="sxs-lookup"><span data-stu-id="2de9a-119">A container for the report-level properties, such as the list of datasets in the report.</span></span>|  
|`AltReportItem`|<span data-ttu-id="2de9a-120">Objet de remplacement d'élément de rapport, à utiliser lorsque le contrôle DTC de l'élément de rapport personnalisé n'est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="2de9a-120">The alternate report item object, to be used where the custom report item run-time control is not supported.</span></span>|  
|`Style`|<span data-ttu-id="2de9a-121">Propriétés de style destinées à l'élément de rapport personnalisé.</span><span class="sxs-lookup"><span data-stu-id="2de9a-121">The style properties for the custom report item.</span></span>|  
|`Adornment`|<span data-ttu-id="2de9a-122">Fenêtre d'ornement utilisée pour modifier de manière interactive le contrôle.</span><span class="sxs-lookup"><span data-stu-id="2de9a-122">An adornment window used for interactive editing of the control.</span></span>|  
|`Site`|<span data-ttu-id="2de9a-123">`ISite` du composant.</span><span class="sxs-lookup"><span data-stu-id="2de9a-123">The `ISite` of the component.</span></span>|  
|`DesignerVerbCollection`|<span data-ttu-id="2de9a-124">Tableau de verbes personnalisés pour le menu contextuel du contrôle.</span><span class="sxs-lookup"><span data-stu-id="2de9a-124">An array of custom verbs for the control's shortcut menu.</span></span>|  
  
#### <a name="public-methods"></a><span data-ttu-id="2de9a-125">M&#233;thodes publiques</span><span class="sxs-lookup"><span data-stu-id="2de9a-125">Public Methods</span></span>  
  
|||  
|-|-|  
|`BeginEdit`|<span data-ttu-id="2de9a-126">Active la modification interactive du contrôle.</span><span class="sxs-lookup"><span data-stu-id="2de9a-126">Activates interactive editing for the control.</span></span>|  
|`DoDefaultAction`|<span data-ttu-id="2de9a-127">Appelé en cas de double-clic ou lorsque le bouton de retour du contrôle est enfoncé.</span><span class="sxs-lookup"><span data-stu-id="2de9a-127">Called in response to double-clicking or pressing Return on the control.</span></span>|  
|`EndEdit`|<span data-ttu-id="2de9a-128">Désactive la modification interactive du contrôle.</span><span class="sxs-lookup"><span data-stu-id="2de9a-128">Deactivates interactive editing for the control.</span></span>|  
|`GetService`|<span data-ttu-id="2de9a-129">Retourne un objet qui représente un service.</span><span class="sxs-lookup"><span data-stu-id="2de9a-129">Returns an object which represents a service.</span></span>|  
|`InitializeNewComponent`|<span data-ttu-id="2de9a-130">Appelé lorsqu'un nouvel élément de rapport personnalisé est créé.</span><span class="sxs-lookup"><span data-stu-id="2de9a-130">Called when a new custom report item is created.</span></span>|  
|`Invalidate`|<span data-ttu-id="2de9a-131">Repeint l'intégralité de la surface du contrôle.</span><span class="sxs-lookup"><span data-stu-id="2de9a-131">Repaints the entire surface of the control.</span></span>|  
|`OnDragEnter`<br /><br /> `OnDragDrop`|<span data-ttu-id="2de9a-132">Appelé lorsqu'un objet est déplacé jusqu'au contrôle.</span><span class="sxs-lookup"><span data-stu-id="2de9a-132">Called when an object is dragged onto the control.</span></span>|  
|`OnPaint`|<span data-ttu-id="2de9a-133">Appelé en réponse à l'événement `Paint`.</span><span class="sxs-lookup"><span data-stu-id="2de9a-133">Called in response to the `Paint` event.</span></span>|  
  
### <a name="microsoftreportdesignercustomreportitemattribute"></a><span data-ttu-id="2de9a-134">Microsoft.ReportDesigner.CustomReportItemAttribute</span><span class="sxs-lookup"><span data-stu-id="2de9a-134">Microsoft.ReportDesigner.CustomReportItemAttribute</span></span>  
 <span data-ttu-id="2de9a-135">Cet attribut est utilisé afin d'identifier le type de l'élément de rapport personnalisé.</span><span class="sxs-lookup"><span data-stu-id="2de9a-135">This is the attribute used to identify the type of the custom report item.</span></span> <span data-ttu-id="2de9a-136">Le nom doit correspondre à la valeur de l' `Name` attribut <> de l' `ReportItem` élément dans le fichier de configuration concepteur de rapports.</span><span class="sxs-lookup"><span data-stu-id="2de9a-136">The name must match the value of the <`Name`> attribute of the `ReportItem` element in the Report Designer configuration file.</span></span>  
  
#### <a name="public-methods"></a><span data-ttu-id="2de9a-137">M&#233;thodes publiques</span><span class="sxs-lookup"><span data-stu-id="2de9a-137">Public Methods</span></span>  
  
|||  
|-|-|  
|`CustomReportItemAttribute`|<span data-ttu-id="2de9a-138">Construit l'objet CustomReportItemAttribute.</span><span class="sxs-lookup"><span data-stu-id="2de9a-138">Constructs the CustomReportItemAttribute object.</span></span>|  
  
### <a name="microsoftreportdesignerlocalizednameattribute"></a><span data-ttu-id="2de9a-139">Microsoft.ReportDesigner.LocalizedNameAttribute</span><span class="sxs-lookup"><span data-stu-id="2de9a-139">Microsoft.ReportDesigner.LocalizedNameAttribute</span></span>  
 <span data-ttu-id="2de9a-140">Cet attribut est utilisé pour spécifier le nom d'affichage à utiliser pour le concepteur d'éléments de rapport personnalisés.</span><span class="sxs-lookup"><span data-stu-id="2de9a-140">This is the attribute used to specify display name to use for the custom report item designer.</span></span>  
  
#### <a name="public-methods"></a><span data-ttu-id="2de9a-141">M&#233;thodes publiques</span><span class="sxs-lookup"><span data-stu-id="2de9a-141">Public Methods</span></span>  
  
|||  
|-|-|  
|`LocalizedNameAttribute`|<span data-ttu-id="2de9a-142">Construit l'objet LocalizedNameAttribute.</span><span class="sxs-lookup"><span data-stu-id="2de9a-142">Constructs the LocalizedNameAttribute object.</span></span>|  
  
### <a name="microsoftreportdesigneradornment"></a><span data-ttu-id="2de9a-143">Microsoft.ReportDesigner.Adornment</span><span class="sxs-lookup"><span data-stu-id="2de9a-143">Microsoft.ReportDesigner.Adornment</span></span>  
 <span data-ttu-id="2de9a-144">La classe `Adornment` est utilisée par le composant de conception de l'élément de rapport personnalisé afin de définir des zones situées à l'extérieur du rectangle principal de l'aire de conception.</span><span class="sxs-lookup"><span data-stu-id="2de9a-144">The `Adornment` class is used by the custom report item design-time component to provide areas outside of the main rectangle of the design surface.</span></span> <span data-ttu-id="2de9a-145">Ces zones permettent de gérer les événements de l'interface utilisateur, tels que les clics de souris et les opérations de glisser-déplacer.</span><span class="sxs-lookup"><span data-stu-id="2de9a-145">These areas can handle user interface events, such as mouse clicks and drag-and-drop operations.</span></span>  
  
#### <a name="public-methods"></a><span data-ttu-id="2de9a-146">M&#233;thodes publiques</span><span class="sxs-lookup"><span data-stu-id="2de9a-146">Public Methods</span></span>  
  
|||  
|-|-|  
|`OnShow`|<span data-ttu-id="2de9a-147">Appelé lorsque `Adornment` est activé.</span><span class="sxs-lookup"><span data-stu-id="2de9a-147">Called when the `Adornment` is activated.</span></span>|  
|`OnHide`|<span data-ttu-id="2de9a-148">Appelé lorsque `Adornment` est désactivé.</span><span class="sxs-lookup"><span data-stu-id="2de9a-148">Called when the `Adornment` is deactivated.</span></span>|  
|`Paint`|<span data-ttu-id="2de9a-149">Appelé en réponse à l'événement `Paint`.</span><span class="sxs-lookup"><span data-stu-id="2de9a-149">Called in response to the `Paint` event.</span></span>|  
|`OnDragEnter`<br /><br /> `OnDragOver`<br /><br /> `OnDragLeave`<br /><br /> `OnDragDrop`|<span data-ttu-id="2de9a-150">Appelé lorsqu'un objet est déplacé jusqu'à `Adornment`.</span><span class="sxs-lookup"><span data-stu-id="2de9a-150">Called when an object is dragged into the `Adornment`.</span></span>|  
  
### <a name="microsoftreportdesigneradornerservice"></a><span data-ttu-id="2de9a-151">Microsoft.ReportDesigner.AdornerService</span><span class="sxs-lookup"><span data-stu-id="2de9a-151">Microsoft.ReportDesigner.AdornerService</span></span>  
 <span data-ttu-id="2de9a-152">Cette classe est utilisée pour fournir la collection de services d'affichage utilisée par l'élément de rapport personnalisé, et ce afin de prendre en charge les objets `Adornment` destinés à son composant de conception.</span><span class="sxs-lookup"><span data-stu-id="2de9a-152">This class is used to provide a collection of display services used by the custom report item to support `Adornment` objects for the custom report item design-time component.</span></span>  
  
#### <a name="public-properties"></a><span data-ttu-id="2de9a-153">Propri&#233;t&#233;s publiques</span><span class="sxs-lookup"><span data-stu-id="2de9a-153">Public Properties</span></span>  
  
|||  
|-|-|  
|`AdornerWindowBounds`|<span data-ttu-id="2de9a-154">Limites de la fenêtre de dispositif de décoration.</span><span class="sxs-lookup"><span data-stu-id="2de9a-154">The bounds of the Adorner window.</span></span>|  
|`AdornerWindowRegion`|<span data-ttu-id="2de9a-155">Région de la fenêtre de dispositif de décoration.</span><span class="sxs-lookup"><span data-stu-id="2de9a-155">The region of the Adorner window.</span></span>|  
|`AdornerWindowGraphics`|<span data-ttu-id="2de9a-156">Contexte graphique de la fenêtre de dispositif de décoration.</span><span class="sxs-lookup"><span data-stu-id="2de9a-156">A graphics context for the Adorner window.</span></span>|  
  
#### <a name="public-methods"></a><span data-ttu-id="2de9a-157">M&#233;thodes publiques</span><span class="sxs-lookup"><span data-stu-id="2de9a-157">Public Methods</span></span>  
  
|||  
|-|-|  
|`ComponentRectInDesignerFrame`|<span data-ttu-id="2de9a-158">Retourne les limites du composant sous la forme de coordonnées de cadre compréhensibles par le concepteur.</span><span class="sxs-lookup"><span data-stu-id="2de9a-158">Returns the bounds of the component translated into designer frame coordinates.</span></span>|  
|`InvalidateAdorner`|<span data-ttu-id="2de9a-159">Invalide la fenêtre de dispositif de décoration.</span><span class="sxs-lookup"><span data-stu-id="2de9a-159">Invalidates the Adorner window.</span></span>|  
|`PointToAdorner`|<span data-ttu-id="2de9a-160">Retourne un point exprimé en coordonnées d'écran sous la forme de coordonnées compréhensibles par la fenêtre de dispositif de décoration.</span><span class="sxs-lookup"><span data-stu-id="2de9a-160">Returns a point in screen coordinates translated to Adorner window coordinates.</span></span>|  
  
### <a name="microsoftreportdesignerexpressioneditor"></a><span data-ttu-id="2de9a-161">Microsoft.ReportDesigner.ExpressionEditor</span><span class="sxs-lookup"><span data-stu-id="2de9a-161">Microsoft.ReportDesigner.ExpressionEditor</span></span>  
 <span data-ttu-id="2de9a-162">Cette classe peut être utilisée à partir du contrôle DTC de l'élément de rapport personnalisé afin d'appeler l'Éditeur d'expressions.</span><span class="sxs-lookup"><span data-stu-id="2de9a-162">This class can be used from your custom report item design-time control to invoke the Expression Editor.</span></span>  
  
#### <a name="public-methods"></a><span data-ttu-id="2de9a-163">M&#233;thodes publiques</span><span class="sxs-lookup"><span data-stu-id="2de9a-163">Public Methods</span></span>  
  
|||  
|-|-|  
|`EditValue`|<span data-ttu-id="2de9a-164">Appelle l'Éditeur d'expressions, alors initialisé avec une valeur d'objet donnée.</span><span class="sxs-lookup"><span data-stu-id="2de9a-164">Invokes the Expression Editor, initialized with the given object value.</span></span>|  
  
### <a name="microsoftreportdesignerifieldsdataobject"></a><span data-ttu-id="2de9a-165">Microsoft.ReportDesigner.IFieldsDataObject</span><span class="sxs-lookup"><span data-stu-id="2de9a-165">Microsoft.ReportDesigner.IFieldsDataObject</span></span>  
 <span data-ttu-id="2de9a-166">Cette classe est une collection de champs [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] et est utilisée pour prendre en charge les événements glissé-déplacé dans un environnement de conception.</span><span class="sxs-lookup"><span data-stu-id="2de9a-166">This class is a collection of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] fields, and is used to support drag-and-drop events in the design environment.</span></span> <span data-ttu-id="2de9a-167">Hérite de `IReportItemDataObject`.</span><span class="sxs-lookup"><span data-stu-id="2de9a-167">Inherits from `IReportItemDataObject`.</span></span>  
  
#### <a name="public-properties"></a><span data-ttu-id="2de9a-168">Propri&#233;t&#233;s publiques</span><span class="sxs-lookup"><span data-stu-id="2de9a-168">Public Properties</span></span>  
  
|||  
|-|-|  
|`DataSetName`|<span data-ttu-id="2de9a-169">Nom du dataset qui contient les champs à déplacer.</span><span class="sxs-lookup"><span data-stu-id="2de9a-169">The name of the dataset containing the fields to be dropped.</span></span>|  
|`Fields`|<span data-ttu-id="2de9a-170">Collection de champs `Microsoft.ReportDesigner.Field`) à déplacer.</span><span class="sxs-lookup"><span data-stu-id="2de9a-170">The collection of fields (`Microsoft.ReportDesigner.Field`) to be dropped.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2de9a-171">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2de9a-171">See Also</span></span>  
 <span data-ttu-id="2de9a-172">[Report Definition Language &#40;SSRS&#41;](../reports/report-definition-language-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2de9a-172">[Report Definition Language &#40;SSRS&#41;](../reports/report-definition-language-ssrs.md) </span></span>  
 <span data-ttu-id="2de9a-173">[Création d’un composant d’exécution d’élément de rapport personnalisé](creating-a-custom-report-item-run-time-component.md) </span><span class="sxs-lookup"><span data-stu-id="2de9a-173">[Creating a Custom Report Item Run-Time Component](creating-a-custom-report-item-run-time-component.md) </span></span>  
 [<span data-ttu-id="2de9a-174">Création d'un composant au moment de la conception d'élément de rapport personnalisé</span><span class="sxs-lookup"><span data-stu-id="2de9a-174">Creating a Custom Report Item Design-Time Component</span></span>](creating-a-custom-report-item-design-time-component.md)  
  
  
