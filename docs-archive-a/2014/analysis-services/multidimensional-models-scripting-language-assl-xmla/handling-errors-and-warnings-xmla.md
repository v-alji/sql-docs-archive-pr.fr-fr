---
title: Gestion des erreurs et des avertissements (XMLA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- errors [XML for Analysis]
- inline errors [XMLA]
- SOAP faults [XML for Analysis]
- XML for Analysis, errors
- faults [XML for Analysis]
- messages [XML for Analysis]
- XMLA, errors
- warnings [XML for Analysis]
- inline warnings [XMLA]
ms.assetid: ab895282-098d-468e-9460-032598961f45
author: minewiskan
ms.author: owend
ms.openlocfilehash: 07b88d800237e5b4b06af0c1ff11cbd0af846600
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604224"
---
# <a name="handling-errors-and-warnings-xmla"></a><span data-ttu-id="0dd54-102">Gestion des erreurs et des avertissements (XMLA)</span><span class="sxs-lookup"><span data-stu-id="0dd54-102">Handling Errors and Warnings (XMLA)</span></span>
  <span data-ttu-id="0dd54-103">La gestion des erreurs est requise quand un appel de méthode de [découverte](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-discover) ou d' [exécution](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) de XML for Analysis (XMLA) ne s’exécute pas, s’exécute correctement mais génère des erreurs ou des avertissements, ou s’exécute correctement mais retourne des résultats qui contiennent des erreurs.</span><span class="sxs-lookup"><span data-stu-id="0dd54-103">Error handling is required when an XML for Analysis (XMLA) [Discover](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-discover) or [Execute](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) method call does not run, runs successfully but generates errors or warnings, or runs successfully but returns results that contain errors.</span></span>  
  
|<span data-ttu-id="0dd54-104">Error</span><span class="sxs-lookup"><span data-stu-id="0dd54-104">Error</span></span>|<span data-ttu-id="0dd54-105">Signalement</span><span class="sxs-lookup"><span data-stu-id="0dd54-105">Reporting</span></span>|  
|-----------|---------------|  
|<span data-ttu-id="0dd54-106">L'appel de méthode XMLA ne s'exécute pas</span><span class="sxs-lookup"><span data-stu-id="0dd54-106">The XMLA method call does not run</span></span>|[!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="0dd54-107">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] retourne un message d’erreur SOAP qui contient les détails de l’échec.</span><span class="sxs-lookup"><span data-stu-id="0dd54-107">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] returns a SOAP fault message that contains the details of the failure.</span></span><br /><br /> <span data-ttu-id="0dd54-108">Pour plus d’informations, consultez la section [gestion des erreurs SOAP](#handling_soap_faults).</span><span class="sxs-lookup"><span data-stu-id="0dd54-108">For more information, see the section, [Handling SOAP Faults](#handling_soap_faults).</span></span>|  
|<span data-ttu-id="0dd54-109">Erreurs ou avertissements sur un appel de méthode ayant abouti</span><span class="sxs-lookup"><span data-stu-id="0dd54-109">Errors or warnings on a successful method call</span></span>|[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]<span data-ttu-id="0dd54-110">inclut un élément d' [erreur](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/error-element-xmla) ou d' [Avertissement](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/warning-element-xmla) pour chaque erreur ou avertissement, respectivement, dans la propriété [messages](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/messages-element-xmla) de l’élément [racine](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/root-element-xmla) qui contient les résultats de l’appel de la méthode.</span><span class="sxs-lookup"><span data-stu-id="0dd54-110">includes an [error](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/error-element-xmla) or [warning](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/warning-element-xmla) element for each error or warning, respectively, in the [Messages](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/messages-element-xmla) property of the [root](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/root-element-xmla) element that contains the results of the method call.</span></span><br /><br /> <span data-ttu-id="0dd54-111">Pour plus d’informations, consultez la section [gestion des erreurs et des avertissements](#handling_errors_and_warnings).</span><span class="sxs-lookup"><span data-stu-id="0dd54-111">For more information, see the section, [Handling Errors and Warnings](#handling_errors_and_warnings).</span></span>|  
|<span data-ttu-id="0dd54-112">Erreurs dans les résultats d'un appel de méthode ayant abouti</span><span class="sxs-lookup"><span data-stu-id="0dd54-112">Errors in the result for a successful method call</span></span>|[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]<span data-ttu-id="0dd54-113">comprend un `error` élément ou inline `warning` pour l’erreur ou l’avertissement, respectivement, dans la [cellule](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/cell-element-xmla) ou l’élément de [ligne](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/row-element-xmla) approprié des résultats de l’appel de méthode.</span><span class="sxs-lookup"><span data-stu-id="0dd54-113">includes an inline `error` or `warning` element for the error or warning, respectively, within the appropriate [Cell](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/cell-element-xmla) or [row](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/row-element-xmla) element of the results of the method call.</span></span><br /><br /> <span data-ttu-id="0dd54-114">Pour plus d’informations, consultez la section [gestion des erreurs inline et des avertissements](#handling_inline_errors_and_warnings).</span><span class="sxs-lookup"><span data-stu-id="0dd54-114">For more information, see the section, [Handling Inline Errors and Warnings](#handling_inline_errors_and_warnings).</span></span>|  
  
##  <a name="handling-soap-faults"></a><a name="handling_soap_faults"></a><span data-ttu-id="0dd54-115">Gestion des erreurs SOAP</span><span class="sxs-lookup"><span data-stu-id="0dd54-115">Handling SOAP Faults</span></span>  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="0dd54-116">retourne une erreur SOAP lorsque les situations suivantes se présentent :</span><span class="sxs-lookup"><span data-stu-id="0dd54-116">returns a SOAP fault when the following situations occur:</span></span>  
  
-   <span data-ttu-id="0dd54-117">le message SOAP qui contient la méthode XMLA n'était pas correctement formé ou n'a pas pu être validé par l'instance [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ;</span><span class="sxs-lookup"><span data-stu-id="0dd54-117">The SOAP message that contains the XMLA method was not well-formed or could not be validated by the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance.</span></span>  
  
-   <span data-ttu-id="0dd54-118">une communication ou une autre erreur s'est produite impliquant le message SOAP qui contient la méthode XMLA ;</span><span class="sxs-lookup"><span data-stu-id="0dd54-118">A communications or other error occurred involving the SOAP message that contains the XMLA method.</span></span>  
  
-   <span data-ttu-id="0dd54-119">la méthode XMLA ne s'est pas exécutée sur l'instance [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0dd54-119">The XMLA method did not run on the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance.</span></span>  
  
 <span data-ttu-id="0dd54-120">Les codes d'erreur SOAP pour XMLstartA commencent par « XMLForAnalysis », suivis d'un point et du code de résultat hexadécimal HRESULT.</span><span class="sxs-lookup"><span data-stu-id="0dd54-120">The SOAP fault codes for XMLstartA start with "XMLForAnalysis", followed by a period and the hexadecimal HRESULT result code.</span></span> <span data-ttu-id="0dd54-121">Par exemple, le code d'erreur « `0x80000005` » prend la forme « `XMLForAnalysis.0x80000005` ».</span><span class="sxs-lookup"><span data-stu-id="0dd54-121">For example, an error code of "`0x80000005`" is formatted as "`XMLForAnalysis.0x80000005`".</span></span> <span data-ttu-id="0dd54-122">Pour plus d'informations sur le format d'erreur SOAP, consultez la rubrique consacrée aux erreurs Soap dans le document « Simple Object Access Protocol (SOAP) 1.1 » du W3C (en anglais).</span><span class="sxs-lookup"><span data-stu-id="0dd54-122">For more information about the SOAP fault format, see Soap Fault in the W3C Simple Object Access Protocol (SOAP) 1.1.</span></span>  
  
### <a name="fault-code-information"></a><span data-ttu-id="0dd54-123">Informations de code d'erreur</span><span class="sxs-lookup"><span data-stu-id="0dd54-123">Fault Code Information</span></span>  
 <span data-ttu-id="0dd54-124">Le tableau suivant présente les informations de code d'erreur XMLA contenues dans la section détaillée de la réponse SOAP.</span><span class="sxs-lookup"><span data-stu-id="0dd54-124">The following table shows the XMLA fault code information that is contained in the detail section of the SOAP response.</span></span> <span data-ttu-id="0dd54-125">Les colonnes représentent les attributs d'une erreur dans la section détaillée d'une erreur SOAP.</span><span class="sxs-lookup"><span data-stu-id="0dd54-125">The columns are the attributes of an error in the detail section of a SOAP fault.</span></span>  
  
|<span data-ttu-id="0dd54-126">Nom de la colonne</span><span class="sxs-lookup"><span data-stu-id="0dd54-126">Column name</span></span>|<span data-ttu-id="0dd54-127">Type</span><span class="sxs-lookup"><span data-stu-id="0dd54-127">Type</span></span>|<span data-ttu-id="0dd54-128">Description</span><span class="sxs-lookup"><span data-stu-id="0dd54-128">Description</span></span>|<span data-ttu-id="0dd54-129">Null autorisé<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0dd54-129">Null allowed<sup>1</sup></span></span>|  
|-----------------|----------|-----------------|------------------------------|  
|`ErrorCode`|`UnsignedInt`|<span data-ttu-id="0dd54-130">Code de retour qui indique le succès ou l'échec de la méthode.</span><span class="sxs-lookup"><span data-stu-id="0dd54-130">Return code that indicates the success or failure of the method.</span></span> <span data-ttu-id="0dd54-131">La valeur hexadécimale doit être convertie en valeur `UnsignedInt`.</span><span class="sxs-lookup"><span data-stu-id="0dd54-131">The hexadecimal value must be converted to an `UnsignedInt` value.</span></span>|<span data-ttu-id="0dd54-132">Non</span><span class="sxs-lookup"><span data-stu-id="0dd54-132">No</span></span>|  
|`WarningCode`|`UnsignedInt`|<span data-ttu-id="0dd54-133">Code de retour qui indique une condition d'avertissement.</span><span class="sxs-lookup"><span data-stu-id="0dd54-133">Return code that indicates a warning condition.</span></span> <span data-ttu-id="0dd54-134">La valeur hexadécimale doit être convertie en valeur `UnsignedInt`.</span><span class="sxs-lookup"><span data-stu-id="0dd54-134">The hexadecimal value must be converted to an `UnsignedInt` value.</span></span>|<span data-ttu-id="0dd54-135">Oui</span><span class="sxs-lookup"><span data-stu-id="0dd54-135">Yes</span></span>|  
|`Description`|`String`|<span data-ttu-id="0dd54-136">Texte et description de l'erreur ou de l'avertissement retourné par le composant qui a généré l'erreur.</span><span class="sxs-lookup"><span data-stu-id="0dd54-136">Error or warning text and description returned by the component that generated the error.</span></span>|<span data-ttu-id="0dd54-137">Oui</span><span class="sxs-lookup"><span data-stu-id="0dd54-137">Yes</span></span>|  
|`Source`|`String`|<span data-ttu-id="0dd54-138">Nom du composant qui a généré l'erreur ou l'avertissement.</span><span class="sxs-lookup"><span data-stu-id="0dd54-138">Name of the component that generated the error or warning.</span></span>|<span data-ttu-id="0dd54-139">Oui</span><span class="sxs-lookup"><span data-stu-id="0dd54-139">Yes</span></span>|  
|`HelpFile`|`String`|<span data-ttu-id="0dd54-140">Chemin d'accès ou URL menant au fichier ou à la rubrique d'aide qui décrit l'erreur ou l'avertissement.</span><span class="sxs-lookup"><span data-stu-id="0dd54-140">Path or URL to the Help file or topic that describes the error or warning.</span></span>|<span data-ttu-id="0dd54-141">Oui</span><span class="sxs-lookup"><span data-stu-id="0dd54-141">Yes</span></span>|  
  
 <span data-ttu-id="0dd54-142"><sup>1</sup> indique si les données sont obligatoires et doivent être retournées, ou si les données sont facultatives et une chaîne NULL est autorisée si la colonne ne s’applique pas.</span><span class="sxs-lookup"><span data-stu-id="0dd54-142"><sup>1</sup> Indicates whether the data is required and must be returned, or whether the data is optional and a null string is allowed if the column does not apply.</span></span>  
  
 <span data-ttu-id="0dd54-143">Voici un exemple d'erreur SOAP qui s'est produite à l'occasion d'un échec d'appel de méthode :</span><span class="sxs-lookup"><span data-stu-id="0dd54-143">The following is an example of a SOAP fault that occurred when a method call failed:</span></span>  
  
```  
<?xml version="1.0"?>  
   <SOAP-ENV:Envelope  
   xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"  
   SOAP-ENV:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/">  
      <SOAP-ENV:Fault>  
         <faultcode>XMLAnalysisError.0x80000005</faultcode>  
         <faultstring>The XML for Analysis provider encountered an error.</faultstring>  
         <faultactor>XML for Analysis Provider</faultactor>  
         <detail>  
<Error  
ErrorCode="2147483653"  
Description="An unexpected error has occurred."  
Source="XML for Analysis Provider"  
HelpFile="" />  
         </detail>  
      </SOAP-ENV:Fault>  
</SOAP-ENV:Envelope>  
```  
  
##  <a name="handling-errors-and-warnings"></a><a name="handling_errors_and_warnings"></a><span data-ttu-id="0dd54-144">Gestion des erreurs et des avertissements</span><span class="sxs-lookup"><span data-stu-id="0dd54-144">Handling Errors and Warnings</span></span>  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="0dd54-145">retourne la propriété `Messages` dans l'élément `root` d'une commande si les situations suivantes se présentent à la suite de l'exécution de cette commande :</span><span class="sxs-lookup"><span data-stu-id="0dd54-145">returns the `Messages` property in the `root` element for a command if the following situations occur after that command runs:</span></span>  
  
-   <span data-ttu-id="0dd54-146">la méthode proprement dite n'a pas échoué, mais un échec s'est produit dans l'instance [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] après que l'appel de méthode a abouti ;</span><span class="sxs-lookup"><span data-stu-id="0dd54-146">The method itself did not fail, but a failure occurred on the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance after the method call succeeded.</span></span>  
  
-   <span data-ttu-id="0dd54-147">l'instance [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] retourne un avertissement lorsque la commande aboutit.</span><span class="sxs-lookup"><span data-stu-id="0dd54-147">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance returns a warning when the command is successful.</span></span>  
  
 <span data-ttu-id="0dd54-148">La propriété `Messages` suit toutes les autres propriétés contenues dans l'élément `root` et peut contenir un ou plusieurs éléments `Message`.</span><span class="sxs-lookup"><span data-stu-id="0dd54-148">The `Messages` property follows all other properties that are contained by the `root` element, and can contain one or more `Message` elements.</span></span> <span data-ttu-id="0dd54-149">De leur côté, les éléments `Message` peut chacun contenir un élément `error` ou `warning` décrivant, respectivement, les erreurs ou les avertissements qui se sont produits pour la commande spécifiée.</span><span class="sxs-lookup"><span data-stu-id="0dd54-149">In turn, each `Message` element can contain either a single `error` or `warning` element describing any errors or warnings, respectively, that occurred for the specified command.</span></span>  
  
 <span data-ttu-id="0dd54-150">Pour plus d’informations sur les erreurs et les avertissements contenus dans la `Messages` propriété, consultez [élément Messages &#40;&#41;XMLA ](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/messages-element-xmla).</span><span class="sxs-lookup"><span data-stu-id="0dd54-150">For more information about errors and warnings that are contained in the `Messages` property, see [Messages Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/messages-element-xmla).</span></span>  
  
### <a name="handling-errors-during-serialization"></a><span data-ttu-id="0dd54-151">Gestion des erreurs pendant la sérialisation</span><span class="sxs-lookup"><span data-stu-id="0dd54-151">Handling Errors During Serialization</span></span>  
 <span data-ttu-id="0dd54-152">Si une erreur se produit après que l' [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance a déjà commencé la sérialisation de la sortie d’une commande exécutée avec succès, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] retourne un élément d' [exception](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/exception-element-xmla) dans un espace de noms différent au moment de l’erreur.</span><span class="sxs-lookup"><span data-stu-id="0dd54-152">If an error occurs after the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance has already begun serializing the output of a successfully run command, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] returns an [Exception](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/exception-element-xmla) element in a different namespace at the point of the error.</span></span> <span data-ttu-id="0dd54-153">L'instance [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ferme alors tous les éléments ouverts de telle sorte que le document XML envoyé au client soit un document valide.</span><span class="sxs-lookup"><span data-stu-id="0dd54-153">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance then closes all open elements so that the XML document sent to the client is a valid document.</span></span> <span data-ttu-id="0dd54-154">L'instance retourne également un élément `Messages` qui contient la description de l'erreur.</span><span class="sxs-lookup"><span data-stu-id="0dd54-154">The instance also returns a `Messages` element that contains the description of the error.</span></span>  
  
##  <a name="handling-inline-errors-and-warnings"></a><a name="handling_inline_errors_and_warnings"></a><span data-ttu-id="0dd54-155">Gestion des erreurs et des avertissements Inline</span><span class="sxs-lookup"><span data-stu-id="0dd54-155">Handling Inline Errors and Warnings</span></span>  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="0dd54-156">retourne un élément inséré `error` ou `warning` pour une commande si la méthode XMLA proprement dite n'a pas échoué, mais qu'une erreur spécifique à un élément de données contenu dans les résultats retournés par la méthode s'est produite dans l'instance [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] après que l'appel de méthode XMLA a abouti.</span><span class="sxs-lookup"><span data-stu-id="0dd54-156">returns an inline `error` or `warning` for a command if the XMLA method itself did not fail, but an error specific to a data element in the results returned by the method occurred on the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance after the XMLA method call succeeded.</span></span>  
  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]<span data-ttu-id="0dd54-157">fournit des éléments inline `error` `warning` si des problèmes spécifiques à une cellule ou à d’autres données contenues dans un `root` élément à l’aide du type de données [MDDataSet](https://docs.microsoft.com/bi-reference/xmla/xml-data-types/mddataset-data-type-xmla) se produisent, par exemple une erreur de sécurité ou une erreur de mise en forme pour une cellule.</span><span class="sxs-lookup"><span data-stu-id="0dd54-157">supplies inline `error` and `warning` elements if issues specific to a cell or to other data that are contained within a `root` element using the [MDDataSet](https://docs.microsoft.com/bi-reference/xmla/xml-data-types/mddataset-data-type-xmla) data type occur, such as a security error or formatting error for a cell.</span></span> <span data-ttu-id="0dd54-158">Dans ces cas, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] retourne un élément `error` ou `warning` dans l'élément `Cell` ou `row` qui contient, respectivement, l'erreur ou l'avertissement.</span><span class="sxs-lookup"><span data-stu-id="0dd54-158">In these cases, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] returns an `error` or `warning` element in the `Cell` or `row` element that contains the error or warning, respectively.</span></span>  
  
 <span data-ttu-id="0dd54-159">L’exemple suivant illustre un jeu de résultats qui contient une erreur dans l’ensemble de lignes retourné à partir d’une `Execute` méthode à l’aide de la commande d' [instruction](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/statement-element-xmla) .</span><span class="sxs-lookup"><span data-stu-id="0dd54-159">The following example illustrates a result set that contains an error in the rowset returned from an `Execute` method using the [Statement](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/statement-element-xmla) command.</span></span>  
  
```  
<return>  
   ...  
   <root>  
      ...  
      <CellData>  
      ...  
         <Cell CellOrdinal="10">  
            <Value>  
               <Error>  
                  <ErrorCode>2148497527</ErrorCode>   
                  <Description>Security Error.</Description>   
               </Error>  
            </Value>  
         </Cell>  
      </CellData>  
      ...  
   </root>  
   ...  
</return>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0dd54-160">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0dd54-160">See Also</span></span>  
 [<span data-ttu-id="0dd54-161">Développement avec XMLA dans Analysis Services</span><span class="sxs-lookup"><span data-stu-id="0dd54-161">Developing with XMLA in Analysis Services</span></span>](developing-with-xmla-in-analysis-services.md)  
  
  
