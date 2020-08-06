---
title: Mise à niveau de la version d’un composant de flux de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- PerformUpgrade method
- custom data flow components [Integration Services], upgrading version
- data flow components [Integration Services], upgrading version
- upgrading data flow components [Integration Services]
ms.assetid: c2a298c6-01b3-4ad1-884d-6108165eb56e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f494793a20f1cdcd108553278b82a44daeea75ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614738"
---
# <a name="upgrading-the-version-of-a-data-flow-component"></a><span data-ttu-id="5d14f-102">Mise à niveau de la version d'un composant de flux de données</span><span class="sxs-lookup"><span data-stu-id="5d14f-102">Upgrading the Version of a Data Flow Component</span></span>
  <span data-ttu-id="5d14f-103">Les packages créés avec une version antérieure de votre composant peuvent contenir des métadonnées qui ne sont plus valides, telles que des propriétés personnalisées dont l'utilisation a été modifiée dans les versions plus récentes du composant.</span><span class="sxs-lookup"><span data-stu-id="5d14f-103">Packages that were created with an older version of your component may contain metadata that is no longer valid, such as custom properties whose usage has been modified in newer versions of the component.</span></span> <span data-ttu-id="5d14f-104">Vous pouvez remplacer la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PerformUpgrade%2A> de la classe de base <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> pour mettre à jour les métadonnées précédemment enregistrées dans les packages plus anciens afin de refléter les propriétés actuelles de votre composant.</span><span class="sxs-lookup"><span data-stu-id="5d14f-104">You can override the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PerformUpgrade%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> base class to update the metadata previously saved in older packages to reflect the current properties of your component.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5d14f-105">Lorsque vous recompilez un composant personnalisé pour une nouvelle version de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], vous n'avez pas à modifier la valeur de la propriété <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.CurrentVersion%2A> si les propriétés du composant n'ont pas changé.</span><span class="sxs-lookup"><span data-stu-id="5d14f-105">When you recompile a custom component for a new version of [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], you do not have to change the value of the <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.CurrentVersion%2A> property if the component's properties have not changed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d14f-106">Exemple</span><span class="sxs-lookup"><span data-stu-id="5d14f-106">Example</span></span>  
 <span data-ttu-id="5d14f-107">L'exemple suivant contient le code de la version 2.0 d'un composant de flux de données fictif.</span><span class="sxs-lookup"><span data-stu-id="5d14f-107">The following sample contains code from version 2.0 of a fictitious data flow component.</span></span> <span data-ttu-id="5d14f-108">Le nouveau numéro de version est défini dans la propriété <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.CurrentVersion%2A> de l'objet <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute>.</span><span class="sxs-lookup"><span data-stu-id="5d14f-108">The new version number is defined in the <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.CurrentVersion%2A> property of the <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute>.</span></span> <span data-ttu-id="5d14f-109">Le composant possède une propriété qui définit la manière dont les valeurs numériques qui dépassent un seuil doivent être gérées.</span><span class="sxs-lookup"><span data-stu-id="5d14f-109">The component has a property that defines how numeric values that exceed a threshold are to be handled.</span></span> <span data-ttu-id="5d14f-110">Dans la version 1.0 du composant fictif, cette propriété a été nommée `RaiseErrorOnInvalidValue` et acceptait une valeur booléenne True ou False.</span><span class="sxs-lookup"><span data-stu-id="5d14f-110">In version 1.0 of the fictitious component, this property was named `RaiseErrorOnInvalidValue` and accepted a Boolean value of true or false.</span></span> <span data-ttu-id="5d14f-111">Dans la version 2.0 du composant fictif, la propriété a été renommée `InvalidValueHandling` et accepte l'une des quatre valeurs possibles d'une énumération personnalisée.</span><span class="sxs-lookup"><span data-stu-id="5d14f-111">In version 2.0 of the fictitious component, the property has been renamed to `InvalidValueHandling` and accepts one of four possible values from a custom enumeration.</span></span>  
  
 <span data-ttu-id="5d14f-112">La méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PerformUpgrade%2A> remplacée dans l'exemple suivant effectue les actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="5d14f-112">The overridden <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PerformUpgrade%2A> method in the following sample performs the following actions:</span></span>  
  
-   <span data-ttu-id="5d14f-113">Obtient la version actuelle du composant.</span><span class="sxs-lookup"><span data-stu-id="5d14f-113">Gets the current version of the component.</span></span>  
  
-   <span data-ttu-id="5d14f-114">Obtient la valeur de l'ancienne propriété personnalisée.</span><span class="sxs-lookup"><span data-stu-id="5d14f-114">Gets the value of the old custom property.</span></span>  
  
-   <span data-ttu-id="5d14f-115">Supprime l'ancienne propriété de la collection de propriétés personnalisées.</span><span class="sxs-lookup"><span data-stu-id="5d14f-115">Removes the old property from the custom property collection.</span></span>  
  
-   <span data-ttu-id="5d14f-116">Définit la valeur de la nouvelle propriété personnalisée selon la valeur de l'ancienne propriété, si possible.</span><span class="sxs-lookup"><span data-stu-id="5d14f-116">Sets the value of the new custom property based on the value of the old property, if possible.</span></span>  
  
-   <span data-ttu-id="5d14f-117">Définit les métadonnées de version sur la version actuelle du composant.</span><span class="sxs-lookup"><span data-stu-id="5d14f-117">Sets the version metadata to the current version of the component.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5d14f-118">Le moteur de flux de données transmet son propre numéro de version dans la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PerformUpgrade%2A> dans le paramètre *pipelineVersion*.</span><span class="sxs-lookup"><span data-stu-id="5d14f-118">The data flow engine passes its own version number into the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PerformUpgrade%2A> method in the *pipelineVersion* parameter.</span></span> <span data-ttu-id="5d14f-119">Ce paramètre est inutile dans la version 1.0 de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], mais peut s'avérer utile dans les versions suivantes.</span><span class="sxs-lookup"><span data-stu-id="5d14f-119">This parameter is not useful in version 1.0 of [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], but may become useful in subsequent versions.</span></span>  
  
 <span data-ttu-id="5d14f-120">L'exemple de code utilise uniquement les deux valeurs d'énumération qui mappent directement aux valeurs booléennes antérieures de la propriété personnalisée.</span><span class="sxs-lookup"><span data-stu-id="5d14f-120">The sample code uses only the two enumeration values that map directly to the prior Boolean values for the custom property.</span></span> <span data-ttu-id="5d14f-121">Les utilisateurs peuvent sélectionner les autres valeurs d'énumération disponibles via l'interface utilisateur personnalisée du composant, dans l'éditeur avancé ou par programme.</span><span class="sxs-lookup"><span data-stu-id="5d14f-121">Users can select the other available enumeration values through the component's custom user interface, in the Advanced Editor, or programmatically.</span></span> <span data-ttu-id="5d14f-122">Pour plus d’informations sur l’affichage des valeurs d’énumération pour une propriété personnalisée dans l’Éditeur avancé, consultez « Création de propriétés personnalisées » dans [Méthodes de conception d’un composant de flux de données](design-time-methods-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="5d14f-122">For information on displaying enumeration values for a custom property in the Advanced Editor, see "Creating Custom Properties" in [Design-time Methods of a Data Flow Component](design-time-methods-of-a-data-flow-component.md).</span></span>  
  
```vb  
Imports Microsoft.SqlServer.Dts.Pipeline  
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper  
  
<DtsPipelineComponent(ComponentType:=ComponentType.Transform, CurrentVersion:=2)> _  
Public Class PerformUpgrade  
  Inherits PipelineComponent  
  
  ' Define the set of possible values for the new custom property.  
  Private Enum InvalidValueHandling  
    Ignore  
    FireInformation  
    FireWarning  
    FireError  
  End Enum  
  
  Public Overloads Overrides Sub PerformUpgrade(ByVal pipelineVersion As Integer)  
  
    ' Obtain the current component version from the attribute.  
    Dim componentAttribute As DtsPipelineComponentAttribute = _  
      CType(Attribute.GetCustomAttribute(Me.GetType, _  
      GetType(DtsPipelineComponentAttribute), False), _  
      DtsPipelineComponentAttribute)  
    Dim currentVersion As Integer = componentAttribute.CurrentVersion  
  
    ' If the component version saved in the package is less than  
    '  the current version, Version 2, perform the upgrade.  
    If ComponentMetaData.Version < currentVersion Then  
  
      ' Get the current value of the old custom property, RaiseErrorOnInvalidValue,   
      ' and then remove the property from the custom property collection.  
      Dim oldValue As Boolean = False  
      Try  
        Dim oldProperty As IDTSCustomProperty100 = _  
          ComponentMetaData.CustomPropertyCollection("RaiseErrorOnInvalidValue")  
        oldValue = CType(oldProperty.Value, Boolean)  
        ComponentMetaData.CustomPropertyCollection.RemoveObjectByIndex("RaiseErrorOnInvalidValue")  
      Catch ex As Exception  
        ' If the old custom property is not available, ignore the error.  
      End Try  
  
      ' Set the value of the new custom property, InvalidValueHandling,  
      '  by using the appropriate enumeration value.  
      Dim newProperty As IDTSCustomProperty100 = _  
        ComponentMetaData.CustomPropertyCollection("InvalidValueHandling")  
      If oldValue = True Then  
        newProperty.Value = InvalidValueHandling.FireError  
      Else  
        newProperty.Value = InvalidValueHandling.Ignore  
      End If  
  
    End If  
  
    ' Update the saved component version metadata to the current version.  
    ComponentMetaData.Version = currentVersion  
  
  End Sub  
  
End Class  
```  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Pipeline;  
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;  
  
[DtsPipelineComponent(ComponentType = ComponentType.Transform, CurrentVersion = 2)]  
public class PerformUpgradeCS :  
  PipelineComponent  
  
  // Define the set of possible values for the new custom property.  
{  
  private enum InvalidValueHandling  
  {  
    Ignore,  
    FireInformation,  
    FireWarning,  
    FireError  
  };  
  
  public override void PerformUpgrade(int pipelineVersion)  
  {  
  
    // Obtain the current component version from the attribute.  
    DtsPipelineComponentAttribute componentAttribute =   
      (DtsPipelineComponentAttribute)Attribute.GetCustomAttribute(this.GetType(), typeof(DtsPipelineComponentAttribute), false);  
    int currentVersion = componentAttribute.CurrentVersion;  
  
    // If the component version saved in the package is less than  
    //  the current version, Version 2, perform the upgrade.  
    if (ComponentMetaData.Version < currentVersion)  
  
    // Get the current value of the old custom property, RaiseErrorOnInvalidValue,   
    // and then remove the property from the custom property collection.  
    {  
      bool oldValue = false;  
      try  
      {  
        IDTSCustomProperty100 oldProperty =   
          ComponentMetaData.CustomPropertyCollection["RaiseErrorOnInvalidValue"];  
        oldValue = (bool)oldProperty.Value;  
        ComponentMetaData.CustomPropertyCollection.RemoveObjectByIndex("RaiseErrorOnInvalidValue");  
      }  
      catch (Exception ex)  
      {  
        // If the old custom property is not available, ignore the error.  
      }  
  
      // Set the value of the new custom property, InvalidValueHandling,  
      //  by using the appropriate enumeration value.  
      IDTSCustomProperty100 newProperty =   
         ComponentMetaData.CustomPropertyCollection["InvalidValueHandling"];  
      if (oldValue == true)  
      {  
        newProperty.Value = InvalidValueHandling.FireError;  
      }  
      else  
      {  
        newProperty.Value = InvalidValueHandling.Ignore;  
      }  
  
    }  
  
    // Update the saved component version metadata to the current version.  
    ComponentMetaData.Version = currentVersion;  
  
  }  
  
}  
```  
  
<span data-ttu-id="5d14f-123">![Icône de Integration Services (petite)](../../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="5d14f-123">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="5d14f-124">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="5d14f-124">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="5d14f-125">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="5d14f-125">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="5d14f-126">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="5d14f-126">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
