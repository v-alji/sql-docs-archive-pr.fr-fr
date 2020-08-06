---
title: Syntaxe de requête XML pour les données de rapport XML (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- namespaces [Reporting Services]
- data processing extensions [Reporting Services], data sources
- xmldp [Reporting Services]
- XML [Reporting Services], data retrieval
ms.assetid: d203886f-faa1-4a02-88f5-dd4c217181ef
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 62dde2b3ab18b5edb5c3786d39173fea3a0854ac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600555"
---
# <a name="xml-query-syntax-for-xml-report-data-ssrs"></a><span data-ttu-id="921f5-102">Syntaxe de requête XML pour les données de rapport XML (SSRS)</span><span class="sxs-lookup"><span data-stu-id="921f5-102">XML Query Syntax for XML Report Data (SSRS)</span></span>
  <span data-ttu-id="921f5-103">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]vous permet de créer des datasets pour des sources de données XML.</span><span class="sxs-lookup"><span data-stu-id="921f5-103">In [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you can create datasets for XML data sources.</span></span> <span data-ttu-id="921f5-104">Après avoir défini une source de données, vous devez créer une requête pour le dataset.</span><span class="sxs-lookup"><span data-stu-id="921f5-104">After you define a data source, you create a query for the dataset.</span></span> <span data-ttu-id="921f5-105">Selon le type de données XML désigné par la source de données, vous pouvez créer la requête du dataset en incluant une `Query` XML ou un chemin d'accès à un élément.</span><span class="sxs-lookup"><span data-stu-id="921f5-105">Depending on the type of XML data pointed to by the data source, you create the dataset query by including an XML `Query` or an element path.</span></span> <span data-ttu-id="921f5-106">Un XML `Query` commence par une **\<Query>** balise et comprend des espaces de noms et des éléments XML qui varient en fonction de la source de données.</span><span class="sxs-lookup"><span data-stu-id="921f5-106">An XML `Query` starts with a **\<Query>** tag and includes namespaces and XML elements that vary depending on the data source.</span></span> <span data-ttu-id="921f5-107">Un chemin d'accès à un élément opère indépendamment des espaces de noms ; il précise les nœuds et les attributs de nœud à utiliser à partir des données XML sous-jacentes avec une syntaxe similaire à la syntaxe XPath.</span><span class="sxs-lookup"><span data-stu-id="921f5-107">An element path is namespace-independent and specifies which nodes and node attributes to use from the underlying XML data with an XPath-like syntax.</span></span> <span data-ttu-id="921f5-108">Pour plus d’informations sur les chemins d’éléments, consultez [Syntaxe du chemin vers l’élément pour des données de rapport XML &#40;SSRS&#41;](report-data-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="921f5-108">For more information about element paths, see [Element Path Syntax for XML Report Data &#40;SSRS&#41;](report-data-ssrs.md).</span></span>  
  
 <span data-ttu-id="921f5-109">Vous pouvez créer une source de données XML pour les types de données XML suivants :</span><span class="sxs-lookup"><span data-stu-id="921f5-109">You can create an XML data source for the following types of XML data:</span></span>  
  
-   <span data-ttu-id="921f5-110">Documents XML désignés par une URL utilisant le protocole HTTP</span><span class="sxs-lookup"><span data-stu-id="921f5-110">Xml documents pointed to by a URL using http protocol</span></span>  
  
-   <span data-ttu-id="921f5-111">Points de terminaison du service Web retournant des données XML</span><span class="sxs-lookup"><span data-stu-id="921f5-111">Web service endpoints that return XML data</span></span>  
  
-   <span data-ttu-id="921f5-112">Données XML incorporées</span><span class="sxs-lookup"><span data-stu-id="921f5-112">Embedded XML data</span></span>  
  
 <span data-ttu-id="921f5-113">La manière dont vous spécifiez une `Query` XML ou un chemin d'accès à un élément dépend du type de données XML.</span><span class="sxs-lookup"><span data-stu-id="921f5-113">How you specify an XML `Query` or an element path depends on the type of XML data.</span></span>  
  
 <span data-ttu-id="921f5-114">Dans le cadre d'un document XML, la requête `Query` XML est facultative.</span><span class="sxs-lookup"><span data-stu-id="921f5-114">For an XML document, the XML `Query` is optional.</span></span> <span data-ttu-id="921f5-115">Si elle est incluse, elle peut contenir un `ElementPath` XML facultatif.</span><span class="sxs-lookup"><span data-stu-id="921f5-115">If it is included, it can contain an optional XML `ElementPath`.</span></span> <span data-ttu-id="921f5-116">La valeur de l'élément `ElementPath` XML utilise la syntaxe du chemin d'accès à l'élément.</span><span class="sxs-lookup"><span data-stu-id="921f5-116">The value of the XML `ElementPath` uses the element path syntax.</span></span> <span data-ttu-id="921f5-117">Vous devez inclure les éléments `Query` et `ElementPath` XML pour traiter correctement les espaces de noms lorsque cela est requis par les données XML de la source de données.</span><span class="sxs-lookup"><span data-stu-id="921f5-117">You include the XML `Query` and XML `ElementPath` to process namespaces correctly when it is needed by the XML data from the data source.</span></span>  
  
 <span data-ttu-id="921f5-118">Dans le cadre d'un point de terminaison de service Web désigné par l'URL d'une chaîne de connexion, `Query` XML définit soit la méthode du service Web, soit l'action SOAP, soit les deux.</span><span class="sxs-lookup"><span data-stu-id="921f5-118">For a Web service endpoint pointed to by a connection string URL, the XML `Query` defines either the Web service method, the SOAP action, or both.</span></span> <span data-ttu-id="921f5-119">Le fournisseur de données XML crée une demande de service Web qui extrait les données XML à utiliser pour le rapport.</span><span class="sxs-lookup"><span data-stu-id="921f5-119">The XML data provider creates a Web service request that retrieves XML data to use for the report.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="921f5-120">Lorsque l'espace de noms d'un service Web comporte une barre oblique (`/)`, incluez à la fois la méthode du service Web et l'action SOAP de sorte que l'extension de traitement des données XML puisse correctement extraire l'espace de noms.</span><span class="sxs-lookup"><span data-stu-id="921f5-120">When a Web service namespace includes a forward slash (`/)` character, include both the Web service method and the SOAP action so that the XML data processing extension can derive the namespace correctly.</span></span>  
  
 <span data-ttu-id="921f5-121">Dans le cadre d'un document XML incorporé, la `Query` XML définit les données XML incorporées à utiliser, inclut des espaces de noms facultatifs et contient un `ElementPath` XML facultatif.</span><span class="sxs-lookup"><span data-stu-id="921f5-121">For an embedded XML document, the XML `Query` defines the embedded XML data to use, includes optional namespaces, and contains an optional XML `ElementPath`..</span></span>  
  
## <a name="specifying-query-parameters-for-xml-data"></a><span data-ttu-id="921f5-122">Spécification de paramètres de la requête pour des données XML</span><span class="sxs-lookup"><span data-stu-id="921f5-122">Specifying Query Parameters for XML Data</span></span>  
 <span data-ttu-id="921f5-123">Vous pouvez spécifier des paramètres de la requête pour les documents XML.</span><span class="sxs-lookup"><span data-stu-id="921f5-123">You can specify query parameters for XML documents.</span></span>  
  
-   <span data-ttu-id="921f5-124">Pour les requêtes URL, les paramètres de la requête sont inclus en tant que paramètres URL standard.</span><span class="sxs-lookup"><span data-stu-id="921f5-124">For URL requests, the query parameters are included as standard URL parameters.</span></span>  
  
-   <span data-ttu-id="921f5-125">Pour les requêtes du service Web, les paramètres de la requête sont passés à la méthode du service Web.</span><span class="sxs-lookup"><span data-stu-id="921f5-125">For Web service requests, query parameters are passed to the Web service method.</span></span> <span data-ttu-id="921f5-126">Pour définir un paramètre de requête, utilisez la page **Paramètres** de la boîte de dialogue **Propriétés du dataset** .</span><span class="sxs-lookup"><span data-stu-id="921f5-126">To define a query parameter, use the **Parameters** page of the **Dataset Properties** dialog box.</span></span> <span data-ttu-id="921f5-127">Pour plus d’informations, consultez [Boîte de dialogue Propriétés du dataset, Paramètres](dataset-properties-dialog-box-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="921f5-127">For more information, see [Dataset Properties Dialog Box, Parameters](dataset-properties-dialog-box-parameters.md).</span></span>  
  
### <a name="example"></a><span data-ttu-id="921f5-128">Exemple</span><span class="sxs-lookup"><span data-stu-id="921f5-128">Example</span></span>  
 <span data-ttu-id="921f5-129">Les exemples fournis dans le tableau ci-dessous illustrent la manière d'extraire des données du service Web Report Server, un document XML et des données XML incorporées.</span><span class="sxs-lookup"><span data-stu-id="921f5-129">The examples in the following table illustrate how to retrieve data from the Report Server Web service, an XML document, and embedded XML data.</span></span>  
  
|<span data-ttu-id="921f5-130">Source de données XML</span><span class="sxs-lookup"><span data-stu-id="921f5-130">XML data source</span></span>|<span data-ttu-id="921f5-131">Exemple de requête</span><span class="sxs-lookup"><span data-stu-id="921f5-131">Query example</span></span>|  
|---------------------|-------------------|  
|<span data-ttu-id="921f5-132">Données XML du service web provenant de la méthode ListChildren .</span><span class="sxs-lookup"><span data-stu-id="921f5-132">Web service XML data from ListChildren method.</span></span>|`<Query>`<br /><br /> `<Method Name="ListChildren" Namespace="https://schemas.microsoft.com/sqlserver/2005/06/30/reporting/reportingservices" />`<br /><br /> `</Query>`|  
|<span data-ttu-id="921f5-133">Données XML du service Web issues de SoapAction.</span><span class="sxs-lookup"><span data-stu-id="921f5-133">Web service XML data from SoapAction.</span></span>|`<Query xmlns=namespace>`<br /><br /> `<SoapAction>http://schemas/microsoft.com/sqlserver/2005/03/23/reporting/reportingservices/ListChildren</SoapAction>`<br /><br /> `</Query>`|  
|<span data-ttu-id="921f5-134">Document XML ou données XML incorporées qui utilisent des espaces de noms.</span><span class="sxs-lookup"><span data-stu-id="921f5-134">XML Document or embedded XML data that uses namespaces.</span></span><br /><br /> <span data-ttu-id="921f5-135">Élément de requête spécifiant des espaces de noms pour un chemin d'accès à un élément.</span><span class="sxs-lookup"><span data-stu-id="921f5-135">Query element specifying namespaces for an element path.</span></span>|`<Query xmlns:es="https://schemas.microsoft.com/StandardSchemas/ExtendedSales">`<br /><br /> `<ElementPath>/Customers/Customer/Orders/Order/es:LineItems/es:LineItem</ElementPath>`<br /><br /> `</Query>`|  
|<span data-ttu-id="921f5-136">Document XML incorporé.</span><span class="sxs-lookup"><span data-stu-id="921f5-136">Embedded XML document.</span></span>|`<Query>`<br /><br /> `<XmlData>`<br /><br /> `<Customers>`<br /><br /> `<Customer ID="1">Bobby</Customer>`<br /><br /> `</Customers>`<br /><br /> `</XmlData>`<br /><br /> `<ElementPath>Customer {@}</ElementPath>`<br /><br /> `</Query>`|  
|<span data-ttu-id="921f5-137">Document XML qui utilise la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="921f5-137">XML document that uses default.</span></span>|<span data-ttu-id="921f5-138">*Aucune requête*.</span><span class="sxs-lookup"><span data-stu-id="921f5-138">*No query*.</span></span><br /><br /> <span data-ttu-id="921f5-139">Le chemin d'accès à l'élément provient du document XML lui-même et est indépendant des espaces de noms.</span><span class="sxs-lookup"><span data-stu-id="921f5-139">The element path is derived from the XML document itself and is namespace-independent.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="921f5-140">Le premier exemple de service web répertorie le contenu du serveur de rapports qui utilise la méthode <xref:ReportService2006.ReportingService2006.ListChildren%2A> .</span><span class="sxs-lookup"><span data-stu-id="921f5-140">The first Web service example lists the contents of the report server that uses the <xref:ReportService2006.ReportingService2006.ListChildren%2A> method.</span></span> <span data-ttu-id="921f5-141">Pour exécuter cette requête, vous devez créer une nouvelle source de données et définir la chaîne de connexion sur http://localhost/reportserver/reportservice2006.asmx.</span><span class="sxs-lookup"><span data-stu-id="921f5-141">To run this query, you must create a new data source and set the connection string to http://localhost/reportserver/reportservice2006.asmx.</span></span> <span data-ttu-id="921f5-142">La méthode <xref:ReportService2006.ReportingService2006.ListChildren%2A> prend deux paramètres : `Item` et `Recursive`.</span><span class="sxs-lookup"><span data-stu-id="921f5-142">The <xref:ReportService2006.ReportingService2006.ListChildren%2A> method takes two parameters: `Item` and `Recursive`.</span></span> <span data-ttu-id="921f5-143">Définissez la valeur par défaut de `Item` sur `/` et celle de `Recursive` sur `1`.</span><span class="sxs-lookup"><span data-stu-id="921f5-143">Set the default value for `Item` to `/` and `Recursive` to `1`.</span></span>  
  
## <a name="specifying-namespaces"></a><span data-ttu-id="921f5-144">Définition d'espaces de noms</span><span class="sxs-lookup"><span data-stu-id="921f5-144">Specifying Namespaces</span></span>  
 <span data-ttu-id="921f5-145">Utilisez l'élément `Query` XML pour spécifier les espaces de noms qui sont utilisés dans les données XML de la source de données.</span><span class="sxs-lookup"><span data-stu-id="921f5-145">Use the XML `Query` element to specify the namespaces that are used in the XML data from the data source.</span></span> <span data-ttu-id="921f5-146">La requête XML suivante utilise l'espace de noms `sales`.</span><span class="sxs-lookup"><span data-stu-id="921f5-146">The following XML query uses the namespace `sales`.</span></span> <span data-ttu-id="921f5-147">Les nœuds `ElementPath` XML de `sales:LineItems` et `sales:LineItem` utilisent l'espace de noms `sales`.</span><span class="sxs-lookup"><span data-stu-id="921f5-147">The XML `ElementPath` nodes for `sales:LineItems` and `sales:LineItem` use the namespace `sales`.</span></span>  
  
```  
<Query xmlns:sales=  
"https://schemas.microsoft.com/StandardSchemas/ExtendedSales">  
   <SoapAction>  
      https://schemas.microsoft.com/SalesWebService/ListOrders   
   </SoapAction>  
   <ElementPath>  
      Customers/Customer/Orders/Order/sales:LineItems/sales:LineItem  
   </ElementPath>  
</Query>  
```  
  
 <span data-ttu-id="921f5-148">Pour préciser l'espace de noms du fournisseur de données afin que l'espace de noms par défaut reste vide, utilisez `xmldp`.</span><span class="sxs-lookup"><span data-stu-id="921f5-148">To specify the data provider namespace so that the default namespace remains empty, use `xmldp`.</span></span> <span data-ttu-id="921f5-149">Cela est illustré par l'exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="921f5-149">This is shown in the following example.</span></span>  
  
### <a name="example"></a><span data-ttu-id="921f5-150">Exemple</span><span class="sxs-lookup"><span data-stu-id="921f5-150">Example</span></span>  
 <span data-ttu-id="921f5-151">Les exemples suivants utilisent le document XML DPNamespace.xml fourni à titre d'illustration à la suite du tableau ci-après.</span><span class="sxs-lookup"><span data-stu-id="921f5-151">The following examples use the XML document DPNamespace.xml, which is provided for illustration after the table.</span></span> <span data-ttu-id="921f5-152">Ce tableau présente deux exemples de syntaxe ElementPath XML incluant des préfixes d'espaces de noms.</span><span class="sxs-lookup"><span data-stu-id="921f5-152">This table shows two examples of XML ElementPath syntax that includes namespace prefixes.</span></span>  
  
|<span data-ttu-id="921f5-153">Élément de requête XML</span><span class="sxs-lookup"><span data-stu-id="921f5-153">XML Query Element</span></span>|<span data-ttu-id="921f5-154">Champs obtenus dans le dataset</span><span class="sxs-lookup"><span data-stu-id="921f5-154">Resulting fields in the dataset</span></span>|  
|-----------------------|-------------------------------------|  
|\<Query/>|<span data-ttu-id="921f5-155">Valeur A : `https://schemas.microsoft.com/..` .</span><span class="sxs-lookup"><span data-stu-id="921f5-155">Value A: `https://schemas.microsoft.com/..`.</span></span><br /><br /> <span data-ttu-id="921f5-156">Valeur B : `https://schemas.microsoft.com/..` .</span><span class="sxs-lookup"><span data-stu-id="921f5-156">Value B: `https://schemas.microsoft.com/..`.</span></span><br /><br /> <span data-ttu-id="921f5-157">Valeur C : `https://schemas.microsoft.com/.` ..</span><span class="sxs-lookup"><span data-stu-id="921f5-157">Value C: `https://schemas.microsoft.com/.`..</span></span>|  
|\<xmldp:Query xmlns:xmldp="https://schemas.microsoft.com/sqlserver/2005/02/reporting/XmlDPQuery" xmlns:ns="https://schemas.microsoft.com/..."><br /><br /> <span data-ttu-id="921f5-158">\<xmldp:ElementPath>{}/NS racine : élément2/node\</xmldp:ElementPath></span><span class="sxs-lookup"><span data-stu-id="921f5-158">\<xmldp:ElementPath>Root {}/ns:Element2/Node\</xmldp:ElementPath></span></span><br /><br /> \</xmldp:Query>|<span data-ttu-id="921f5-159">Valeur D</span><span class="sxs-lookup"><span data-stu-id="921f5-159">Value D</span></span><br /><br /> <span data-ttu-id="921f5-160">Valeur E</span><span class="sxs-lookup"><span data-stu-id="921f5-160">Value E</span></span><br /><br /> <span data-ttu-id="921f5-161">Valeur F</span><span class="sxs-lookup"><span data-stu-id="921f5-161">Value F</span></span>|  
  
#### <a name="xml-document-dpnamespacexml"></a><span data-ttu-id="921f5-162">Document XML : DPNamespace.xml</span><span class="sxs-lookup"><span data-stu-id="921f5-162">XML document: DPNamespace.xml</span></span>  
 <span data-ttu-id="921f5-163">Vous pouvez copier ce document XML et l'enregistrer dans une URL disponible pour être utilisée en tant que source de données par le Concepteur de rapports : par exemple http://localhost/DPNamespace.xml.</span><span class="sxs-lookup"><span data-stu-id="921f5-163">You can copy this XML and save it to a URL available for Report Designer to use as an XML data source: for example, http://localhost/DPNamespace.xml.</span></span>  
  
```  
<Root xmlns:ns="https://schemas.microsoft.com/...">  
   <ns:Element1>  
      <Node>Value A</Node>  
      <Node>Value B</Node>  
      <Node>Value C</Node>  
   </ns:Element1>  
   <ns:Element2>  
      <Node>Value D</Node>  
      <Node>Value E</Node>  
      <Node>Value F</Node>  
   </ns:Element2>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="921f5-164">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="921f5-164">See Also</span></span>  
 <span data-ttu-id="921f5-165">[Type de connexion XML &#40;&#41;SSRS](xml-connection-type-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="921f5-165">[XML Connection Type &#40;SSRS&#41;](xml-connection-type-ssrs.md) </span></span>  
 [<span data-ttu-id="921f5-166">Didacticiels sur Reporting Services &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="921f5-166">Reporting Services Tutorials &#40;SSRS&#41;</span></span>](../reporting-services-tutorials-ssrs.md)  
  
  
