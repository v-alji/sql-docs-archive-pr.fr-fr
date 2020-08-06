---
title: Simulation d’une sortie d’erreur pour le composant Script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script component [Integration Services], error output
- error outputs [Integration Services], Script component
ms.assetid: f8b6ecff-ac99-4231-a0e7-7ce4ad76bad0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bed458ce378eb26cd863811b4974b5f39429e1b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696995"
---
# <a name="simulating-an-error-output-for-the-script-component"></a><span data-ttu-id="6578b-102">Simulation d'une sortie d'erreur pour le composant Script</span><span class="sxs-lookup"><span data-stu-id="6578b-102">Simulating an Error Output for the Script Component</span></span>
  <span data-ttu-id="6578b-103">Bien qu'il soit impossible de configurer directement une sortie en tant que sortie d'erreur dans le composant Script à des fins de gestion automatique des lignes d'erreur, vous pouvez reproduire les fonctionnalités d'une sortie d'erreur intégrée en créant une sortie supplémentaire et en utilisant une logique conditionnelle dans votre script afin de diriger des lignes vers cette sortie, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="6578b-103">Although you cannot directly configure an output as an error output in the Script component for automatic handling of error rows, you can reproduce the functionality of a built-in error output by creating an additional output and using conditional logic in your script to direct rows to this output when appropriate.</span></span> <span data-ttu-id="6578b-104">Vous pouvez imiter le comportement d'une sortie d'erreur intégrée en ajoutant deux colonnes de sortie supplémentaires pour recevoir le numéro d'erreur et l'ID de la colonne dans laquelle une erreur s'est produite.</span><span class="sxs-lookup"><span data-stu-id="6578b-104">You may want to imitate the behavior of a built-in error output by adding two additional output columns to receive the error number and the ID of the column in which an error occurred.</span></span>  
  
 <span data-ttu-id="6578b-105">Si vous souhaitez ajouter la description d'erreur qui correspond à un code d'erreur [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] prédéfini spécifique, vous pouvez utiliser la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.GetErrorDescription%2A> de l'interface <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100>, disponible via la propriété <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A> du composant Script.</span><span class="sxs-lookup"><span data-stu-id="6578b-105">If you want to add the error description that corresponds to a specific predefined [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] error code, you can use the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.GetErrorDescription%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface, available through the Script component's <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6578b-106">Exemple</span><span class="sxs-lookup"><span data-stu-id="6578b-106">Example</span></span>  
 <span data-ttu-id="6578b-107">L'exemple indiqué ici utilise un composant Script configuré en tant que transformation qui possède deux sorties synchrones.</span><span class="sxs-lookup"><span data-stu-id="6578b-107">The example shown here uses a Script component configured as a transformation that has two synchronous outputs.</span></span> <span data-ttu-id="6578b-108">L'objectif du composant Script est de filtrer les lignes d'erreur parmi les données d'adresse dans l'exemple de base de données AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="6578b-108">The purpose of the Script component is to filter error rows from address data in the AdventureWorks sample database.</span></span> <span data-ttu-id="6578b-109">Cet exemple fictif suppose que nous préparons une promotion pour les clients d'Amérique du Nord et que nous avons besoin d'éliminer les adresses qui ne se trouvent pas en Amérique du Nord par filtrage.</span><span class="sxs-lookup"><span data-stu-id="6578b-109">This fictitious example assumes that we are preparing a promotion for North American customers and need to filter out addresses that are not located in North America.</span></span>  
  
#### <a name="to-configure-the-example"></a><span data-ttu-id="6578b-110">Pour configurer l'exemple</span><span class="sxs-lookup"><span data-stu-id="6578b-110">To configure the example</span></span>  
  
1.  <span data-ttu-id="6578b-111">Avant de créer le composant Script, créez un gestionnaire de connexions et configurez une source de flux de données qui sélectionne les données d'adresse de l'exemple de base de données AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="6578b-111">Before creating the new Script component, create a connection manager and configure a data flow source that selects address data from the AdventureWorks sample database.</span></span> <span data-ttu-id="6578b-112">Pour cet exemple, qui examine uniquement la colonne CountryRegionName, vous pouvez utiliser simplement la vue Person.vStateCountryProvinceRegion, ou vous pouvez sélectionner des données en liant les tables Person.Address, Person.StateProvince et Person.CountryRegion.</span><span class="sxs-lookup"><span data-stu-id="6578b-112">For this example, which only looks at the CountryRegionName column, you can simply use the Person.vStateCountryProvinceRegion view, or you can select data by joining the Person.Address, Person.StateProvince, and Person.CountryRegion tables.</span></span>  
  
2.  <span data-ttu-id="6578b-113">Ajoutez un nouveau composant Script à l'aire du concepteur de flux de données et configurez-le en tant que transformation.</span><span class="sxs-lookup"><span data-stu-id="6578b-113">Add a new Script component to the Data Flow designer surface and configure it as a transformation.</span></span> <span data-ttu-id="6578b-114">Ouvrez l' **Éditeur de transformation de script**.</span><span class="sxs-lookup"><span data-stu-id="6578b-114">Open the **Script Transformation Editor**.</span></span>  
  
3.  <span data-ttu-id="6578b-115">Dans la page **Script**, définissez la propriété **ScriptLanguage** sur le langage de script que vous souhaitez utiliser pour coder le script.</span><span class="sxs-lookup"><span data-stu-id="6578b-115">On the **Script** page, set the **ScriptLanguage** property to the script language that you want to use to code the script.</span></span>  
  
4.  <span data-ttu-id="6578b-116">Cliquez sur **Modifier le script** pour ouvrir [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span><span class="sxs-lookup"><span data-stu-id="6578b-116">Click **Edit Script** to open [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span></span>  
  
5.  <span data-ttu-id="6578b-117">Dans la méthode `Input0_ProcessInputRow`, tapez ou collez l'exemple de code indiqué ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="6578b-117">In the `Input0_ProcessInputRow` method, type or paste the sample code shown below.</span></span>  
  
6.  <span data-ttu-id="6578b-118">Fermez VSTA.</span><span class="sxs-lookup"><span data-stu-id="6578b-118">Close VSTA.</span></span>  
  
7.  <span data-ttu-id="6578b-119">Dans la page **Colonnes d’entrée**, sélectionnez les colonnes que vous souhaitez traiter dans la transformation de script.</span><span class="sxs-lookup"><span data-stu-id="6578b-119">On the **Input Columns** page, select the columns that you want to process in the Script transformation.</span></span> <span data-ttu-id="6578b-120">Cet exemple utilise uniquement la colonne CountryRegionName.</span><span class="sxs-lookup"><span data-stu-id="6578b-120">This example uses only the CountryRegionName column.</span></span> <span data-ttu-id="6578b-121">Les colonnes d'entrée disponibles que vous n'avez pas sélectionnées seront tout simplement transférées sans être modifiées dans le flux de données.</span><span class="sxs-lookup"><span data-stu-id="6578b-121">Available input columns that you leave unselected will simply be passed through unchanged in the data flow.</span></span>  
  
8.  <span data-ttu-id="6578b-122">Sur la page **entrées et sorties** , ajoutez une nouvelle sortie, puis définissez sa `SynchronousInputID` valeur sur l’ID de l’entrée, qui est également la valeur de la `SynchronousInputID` propriété de la sortie par défaut.</span><span class="sxs-lookup"><span data-stu-id="6578b-122">On the **Inputs and Outputs** page, add a new, second output, and set its `SynchronousInputID` value to the ID of the input, which is also the value of the `SynchronousInputID` property of the default output.</span></span> <span data-ttu-id="6578b-123">Définissez la propriété `ExclusionGroup` des deux sorties sur la même valeur différente de zéro (par exemple, 1) pour indiquer que chaque ligne sera dirigée vers une seule des deux sorties.</span><span class="sxs-lookup"><span data-stu-id="6578b-123">Set the `ExclusionGroup` property of both outputs to the same non-zero value (for example, 1) to indicate that each row will be directed to only one of the two outputs.</span></span> <span data-ttu-id="6578b-124">Attribuez à la nouvelle sortie d'erreur un nom distinct, tel que « MyErrorOutput ».</span><span class="sxs-lookup"><span data-stu-id="6578b-124">Give the new error output a distinctive name, such as "MyErrorOutput."</span></span>  
  
9. <span data-ttu-id="6578b-125">Ajoutez des colonnes de sortie supplémentaires à la nouvelle sortie d'erreur pour capturer les informations d'erreur souhaitées, qui peuvent inclure le code de l'erreur, l'ID de la colonne dans laquelle l'erreur s'est produite et éventuellement la description de l'erreur.</span><span class="sxs-lookup"><span data-stu-id="6578b-125">Add additional output columns to the new error output to capture the desired error information, which may include the error code, the ID of the column in which the error occurred, and possibly the error description.</span></span> <span data-ttu-id="6578b-126">Cet exemple crée les nouvelles colonnes, ErrorColumn et ErrorMessage.</span><span class="sxs-lookup"><span data-stu-id="6578b-126">This example creates the new columns, ErrorColumn and ErrorMessage.</span></span> <span data-ttu-id="6578b-127">Si vous interceptez des erreurs [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] prédéfinies dans votre propre implémentation, assurez-vous d'ajouter une colonne ErrorCode pour le numéro d'erreur.</span><span class="sxs-lookup"><span data-stu-id="6578b-127">If you are catching predefined [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] errors in your own implementation, make sure to add an ErrorCode column for the error number.</span></span>  
  
10. <span data-ttu-id="6578b-128">Notez la valeur d'ID de la ou des colonnes d'entrée dans lesquelles le composant Script va rechercher des conditions d'erreur.</span><span class="sxs-lookup"><span data-stu-id="6578b-128">Note the ID value of the input column or columns that the Script component will check for error conditions.</span></span> <span data-ttu-id="6578b-129">Cet exemple utilise cet identificateur de colonne pour renseigner la valeur ErrorColumn.</span><span class="sxs-lookup"><span data-stu-id="6578b-129">This example uses this column identifier to populate the ErrorColumn value.</span></span>  
  
11. <span data-ttu-id="6578b-130">Fermez l’**Éditeur de transformation de script**.</span><span class="sxs-lookup"><span data-stu-id="6578b-130">Close the **Script Transformation Editor.**</span></span>  
  
12. <span data-ttu-id="6578b-131">Attachez les sorties du composant Script aux destinations appropriées.</span><span class="sxs-lookup"><span data-stu-id="6578b-131">Attach the outputs of the Script component to suitable destinations.</span></span> <span data-ttu-id="6578b-132">Les destinations de fichiers plats sont les plus faciles à configurer pour les tests ad hoc.</span><span class="sxs-lookup"><span data-stu-id="6578b-132">Flat file destinations are the easiest to configure for ad hoc testing.</span></span>  
  
13. <span data-ttu-id="6578b-133">Exécutez le package.</span><span class="sxs-lookup"><span data-stu-id="6578b-133">Run the package.</span></span>  
  
```vb  
Public Overrides Sub Input0_ProcessInputRow(ByVal Row As Input0Buffer)  
  
  If Row.CountryRegionName <> "Canada" _  
      And Row.CountryRegionName <> "United States" Then  
  
    Row.ErrorColumn = 68 ' ID of CountryRegionName column  
    Row.ErrorMessage = "Address is not in North America."  
    Row.DirectRowToMyErrorOutput()  
  
  Else  
  
    Row.DirectRowToOutput0()  
  
  End If  
  
End Sub  
```  
  
```csharp  
public override void Input0_ProcessInputRow(Input0Buffer Row)  
{  
  
  if (Row.CountryRegionName!="Canada"&&Row.CountryRegionName!="United States")  
  
  {  
    Row.ErrorColumn = 68; // ID of CountryRegionName column  
    Row.ErrorMessage = "Address is not in North America.";  
    Row.DirectRowToMyErrorOutput();  
  
  }  
  else  
  {  
  
    Row.DirectRowToOutput0();  
  
  }  
  
}  
```  
  
<span data-ttu-id="6578b-134">![Icône de Integration Services (petite)](../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="6578b-134">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="6578b-135">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="6578b-135">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="6578b-136">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="6578b-136">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="6578b-137">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="6578b-137">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6578b-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6578b-138">See Also</span></span>  
 <span data-ttu-id="6578b-139">[Gestion des erreurs dans les données](../data-flow/error-handling-in-data.md) </span><span class="sxs-lookup"><span data-stu-id="6578b-139">[Error Handling in Data](../data-flow/error-handling-in-data.md) </span></span>  
 <span data-ttu-id="6578b-140">[Utilisation des sorties d’erreur dans un composant de transmission de données](../extending-packages-custom-objects/data-flow/using-error-outputs-in-a-data-flow-component.md) </span><span class="sxs-lookup"><span data-stu-id="6578b-140">[Using Error Outputs in a Data Flow Component](../extending-packages-custom-objects/data-flow/using-error-outputs-in-a-data-flow-component.md) </span></span>  
 [<span data-ttu-id="6578b-141">Création d'une transformation synchrone à l'aide du composant Script</span><span class="sxs-lookup"><span data-stu-id="6578b-141">Creating a Synchronous Transformation with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md) 
  
  
