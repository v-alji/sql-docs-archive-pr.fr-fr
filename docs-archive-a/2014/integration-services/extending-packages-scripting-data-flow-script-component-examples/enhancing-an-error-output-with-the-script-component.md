---
title: Amélioration d’une sortie d’erreur à l’aide du composant Script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- transformations [Integration Services], components
- Script component [Integration Services], examples
- error outputs [Integration Services], enhancing
- Script component [Integration Services], transformation components
ms.assetid: f7c02709-f1fa-4ebd-b255-dc8b81feeaa5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 18637aa1e147ce989645ae859681929f4d0c438a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614180"
---
# <a name="enhancing-an-error-output-with-the-script-component"></a><span data-ttu-id="6239c-102">Amélioration d'une sortie d'erreur à l'aide du composant Script</span><span class="sxs-lookup"><span data-stu-id="6239c-102">Enhancing an Error Output with the Script Component</span></span>
  <span data-ttu-id="6239c-103">Par défaut, les deux colonnes supplémentaires d'une sortie d'erreur [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], ErrorCode et ErrorColumn, contiennent uniquement des codes numériques identifiant un numéro d'erreur et l'ID de la colonne dans laquelle l'erreur est survenue.</span><span class="sxs-lookup"><span data-stu-id="6239c-103">By default, the two extra columns in an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] error output, ErrorCode and ErrorColumn, contain only numeric codes that represent an error number, and the ID of the column in which the error occurred.</span></span> <span data-ttu-id="6239c-104">L'usage de ces valeurs numériques peut être limité sans la description d'erreur correspondante.</span><span class="sxs-lookup"><span data-stu-id="6239c-104">These numeric values may be of limited use without the corresponding error description.</span></span>  
  
 <span data-ttu-id="6239c-105">Cette rubrique décrit comment ajouter une colonne de description d'erreur à des données de sortie d'erreur existantes dans le flux de données en utilisant le composant Script.</span><span class="sxs-lookup"><span data-stu-id="6239c-105">This topic describes how to add an error description column to existing error output data in the data flow by using the Script component.</span></span> <span data-ttu-id="6239c-106">L'exemple ajoute la description d'erreur qui correspond à un code d'erreur [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] prédéfini spécifique à l'aide de la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.GetErrorDescription%2A> de l'interface <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100>, disponible via la propriété <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A> du composant Script.</span><span class="sxs-lookup"><span data-stu-id="6239c-106">The example adds the error description that corresponds to a specific predefined [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] error code by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.GetErrorDescription%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface, available through the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A> property of the Script component.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6239c-107">Si vous souhaitez créer un composant que vous pouvez réutiliser plus facilement dans plusieurs tâches de flux de données et plusieurs packages, utilisez le code présenté dans cet exemple de composant Script comme point de départ pour un composant de flux de données personnalisé.</span><span class="sxs-lookup"><span data-stu-id="6239c-107">If you want to create a component that you can more easily reuse across multiple Data Flow tasks and multiple packages, consider using the code in this Script component sample as the starting point for a custom data flow component.</span></span> <span data-ttu-id="6239c-108">Pour plus d’informations, consultez [Développement d’un composant de flux de données personnalisé](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="6239c-108">For more information, see [Developing a Custom Data Flow Component](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6239c-109">Exemple</span><span class="sxs-lookup"><span data-stu-id="6239c-109">Example</span></span>  
 <span data-ttu-id="6239c-110">L'exemple indiqué ici utilise un composant Script configuré en tant que transformation pour ajouter une colonne de description d'erreur à des données de sortie d'erreur existantes dans le flux de données.</span><span class="sxs-lookup"><span data-stu-id="6239c-110">The example shown here uses a Script component configured as a transformation to add an error description column to existing error output data in the data flow.</span></span>  
  
 <span data-ttu-id="6239c-111">Pour plus d’informations sur la configuration du composant script pour une utilisation en tant que transformation dans le workflow, consultez [création d’une transformation synchrone avec le composant script](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md)et [création d’une transformation asynchrone à l’aide du composant script](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="6239c-111">For more information about how to configure the Script component for use as a transformation in the data flow, see [Creating a Synchronous Transformation with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md)and [Creating an Asynchronous Transformation with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md).</span></span>  
  
#### <a name="to-configure-this-script-component-example"></a><span data-ttu-id="6239c-112">Pour configurer cet exemple de composant Script</span><span class="sxs-lookup"><span data-stu-id="6239c-112">To configure this Script Component example</span></span>  
  
1.  <span data-ttu-id="6239c-113">Avant de créer le composant Script, configurez un composant en amont dans le flux de données pour rediriger des lignes vers sa sortie d'erreur lorsqu'une erreur ou troncation se produit.</span><span class="sxs-lookup"><span data-stu-id="6239c-113">Before creating the new Script component, configure an upstream component in the data flow to redirect rows to its error output when an error or truncation occurs.</span></span> <span data-ttu-id="6239c-114">À des fins de test, vous pouvez configurer un composant de manière à garantir que des erreurs se produiront, par exemple en configurant une transformation de recherche entre deux tables où la recherche échouera.</span><span class="sxs-lookup"><span data-stu-id="6239c-114">For testing purposes, you may want to configure a component in a manner that ensures that errors will occur-for example, by configuring a Lookup transformation between two tables where the lookup will fail.</span></span>  
  
2.  <span data-ttu-id="6239c-115">Ajoutez un nouveau composant Script à l'aire du concepteur de flux de données et configurez-le en tant que transformation.</span><span class="sxs-lookup"><span data-stu-id="6239c-115">Add a new Script component to the Data Flow designer surface and configure it as a transformation.</span></span>  
  
3.  <span data-ttu-id="6239c-116">Connectez la sortie d'erreur du composant en amont au nouveau composant Script.</span><span class="sxs-lookup"><span data-stu-id="6239c-116">Connect the error output from the upstream component to the new Script component.</span></span>  
  
4.  <span data-ttu-id="6239c-117">Ouvrez l’**Éditeur de transformation de script**, puis dans la page **Script**, au niveau de la propriété **ScriptLanguage**, sélectionnez le langage de script.</span><span class="sxs-lookup"><span data-stu-id="6239c-117">Open the **Script Transformation Editor**, and on the **Script** page, for the **ScriptLanguage** property, select the script language.</span></span>  
  
5.  <span data-ttu-id="6239c-118">Cliquez sur **Modifier le script** pour ouvrir l’environnement de développement intégré [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA) et ajouter l’exemple de code indiqué ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="6239c-118">Click **Edit Script** to open the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA) IDE and add the sample code shown below.</span></span>  
  
6.  <span data-ttu-id="6239c-119">Fermez VSTA.</span><span class="sxs-lookup"><span data-stu-id="6239c-119">Close VSTA.</span></span>  
  
7.  <span data-ttu-id="6239c-120">Dans l’éditeur de transformation de script, dans la page **colonnes d’entrée** , sélectionnez la colonne ErrorCode.</span><span class="sxs-lookup"><span data-stu-id="6239c-120">In the Script Transformation Editor, on the **Input Columns** page, select the ErrorCode column.</span></span>  
  
8.  <span data-ttu-id="6239c-121">Sur la page **entrées et sorties** , ajoutez une nouvelle colonne de sortie de type `String` nommée **ErrorDescription**.</span><span class="sxs-lookup"><span data-stu-id="6239c-121">On the **Inputs and Outputs** page, add a new output column of type `String` named **ErrorDescription**.</span></span> <span data-ttu-id="6239c-122">Augmentez la longueur par défaut de la nouvelle colonne à 255 pour prendre en charge les longs messages.</span><span class="sxs-lookup"><span data-stu-id="6239c-122">Increase the default length of the new column to 255 to support long messages.</span></span>  
  
9. <span data-ttu-id="6239c-123">Fermez l’**Éditeur de transformation de script**.</span><span class="sxs-lookup"><span data-stu-id="6239c-123">Close the **Script Transformation Editor.**</span></span>  
  
10. <span data-ttu-id="6239c-124">Attachez la sortie du composant Script à une destination appropriée.</span><span class="sxs-lookup"><span data-stu-id="6239c-124">Attach the output of the Script component to a suitable destination.</span></span> <span data-ttu-id="6239c-125">Les destinations de fichiers plats sont les plus faciles à configurer à des fins de test ad hoc.</span><span class="sxs-lookup"><span data-stu-id="6239c-125">A Flat File destination is the easiest to configure for ad hoc testing.</span></span>  
  
11. <span data-ttu-id="6239c-126">Exécutez le package.</span><span class="sxs-lookup"><span data-stu-id="6239c-126">Run the package.</span></span>  
  
```vb  
Public Class ScriptMain  
    Inherits UserComponent  
    Public Overrides Sub Input0_ProcessInputRow(ByVal Row As Input0Buffer)  
  
  Row.ErrorDescription = _  
    Me.ComponentMetaData.GetErrorDescription(Row.ErrorCode)  
  
    End Sub  
End Class  
```  
  
```csharp  
public class ScriptMain:  
    UserComponent  
{  
    public override void Input0_ProcessInputRow(Input0Buffer Row)  
    {  
  
  Row.ErrorDescription = this.ComponentMetaData.GetErrorDescription(Row.ErrorCode);  
  
    }  
}  
  
```  
  
<span data-ttu-id="6239c-127">![Icône de Integration Services (petite)](../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="6239c-127">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="6239c-128">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="6239c-128">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="6239c-129">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="6239c-129">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="6239c-130">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="6239c-130">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6239c-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6239c-131">See Also</span></span>  
 <span data-ttu-id="6239c-132">[Gestion des erreurs dans les données](../data-flow/error-handling-in-data.md) </span><span class="sxs-lookup"><span data-stu-id="6239c-132">[Error Handling in Data](../data-flow/error-handling-in-data.md) </span></span>  
 <span data-ttu-id="6239c-133">[Utilisation de sorties d’erreur dans un composant de flux de données](../extending-packages-custom-objects/data-flow/using-error-outputs-in-a-data-flow-component.md) </span><span class="sxs-lookup"><span data-stu-id="6239c-133">[Using Error Outputs in a Data Flow Component](../extending-packages-custom-objects/data-flow/using-error-outputs-in-a-data-flow-component.md) </span></span>  
 [<span data-ttu-id="6239c-134">Création d’une transformation synchrone à l’aide du composant Script</span><span class="sxs-lookup"><span data-stu-id="6239c-134">Creating a Synchronous Transformation with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md) 
  
  
