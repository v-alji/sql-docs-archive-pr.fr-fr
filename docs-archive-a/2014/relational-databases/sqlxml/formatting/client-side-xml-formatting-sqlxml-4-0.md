---
title: Mise en forme XML côté client (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- FOR XML clause, formatting
- middle tier XML formatting [SQLXML]
- client-side XML formatting
- client-side-xml attribute
ms.assetid: 9630a21d-a93b-4d3b-8a25-c4b32399f993
author: rothja
ms.author: jroth
ms.openlocfilehash: bf4a680d79a25d24ebdf779b41fd3be5a5d6a605
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611664"
---
# <a name="client-side-xml-formatting-sqlxml-40"></a><span data-ttu-id="f369c-102">Mise en forme XML côté client (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="f369c-102">Client-side XML Formatting (SQLXML 4.0)</span></span>
  <span data-ttu-id="f369c-103">Cette rubrique fournit des informations sur la mise en forme XML côté client.</span><span class="sxs-lookup"><span data-stu-id="f369c-103">This topic provides information about client-side XML formatting.</span></span> <span data-ttu-id="f369c-104">La mise en forme côté client fait référence à la mise en forme du code XML dans la couche intermédiaire.</span><span class="sxs-lookup"><span data-stu-id="f369c-104">Client-side formatting refers to the formatting of XML on the middle tier.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f369c-105">Cette rubrique fournit des informations supplémentaires sur l'utilisation de la clause FOR XML côté client ; elle suppose que la clause FOR XML vous est déjà familière.</span><span class="sxs-lookup"><span data-stu-id="f369c-105">This topic provides additional information about using the FOR XML clause on the client side, and assumes you are already familiar with the FOR XML clause.</span></span> <span data-ttu-id="f369c-106">Pour plus d’informations sur FOR XML, consultez [construction de XML à l’aide de for XML](../../xml/for-xml-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f369c-106">For more information about FOR XML, see [Constructing XML Using FOR XML](../../xml/for-xml-sql-server.md).</span></span>  
  
 <span data-ttu-id="f369c-107">**Important** Pour utiliser la fonctionnalité FOR XML côté client avec le nouveau `xml` type de données, les clients doivent toujours utiliser le [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] fournisseur de données Native Client (SQLNCLI11) au lieu du fournisseur SQLOLEDB.</span><span class="sxs-lookup"><span data-stu-id="f369c-107">**Important** To use client-side FOR XML functionality with the new `xml` data type, clients should always use the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) data provider instead of the SQLOLEDB provider.</span></span> <span data-ttu-id="f369c-108">SQLNCLI11 est la version la plus récente du fournisseur SQL Server et prend complètement en charge les types de données apparus dans [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f369c-108">SQLNCLI11 is the latest version of the SQL Server provider and fully understands data types introduced in [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="f369c-109">Avec l'utilisation de FOR XML côté client et du fournisseur SQLOLEDB, les types de données sont traités en tant que chaînes `xml`.</span><span class="sxs-lookup"><span data-stu-id="f369c-109">The behavior for client side FOR XML with the SQLOLEDB provider will treat `xml` data types as strings.</span></span>  
  
## <a name="formatting-xml-documents-on-the-client-side"></a><span data-ttu-id="f369c-110">Mise en forme de documents XML côté client</span><span class="sxs-lookup"><span data-stu-id="f369c-110">Formatting XML Documents on the Client Side</span></span>  
 <span data-ttu-id="f369c-111">Lorsqu'une application cliente exécute la requête suivante :</span><span class="sxs-lookup"><span data-stu-id="f369c-111">When a client application executes the following query:</span></span>  
  
```  
SELECT FirstName, LastName  
FROM   Person.Contact  
FOR XML RAW  
```  
  
 <span data-ttu-id="f369c-112">...seule cette partie de la requête est envoyée au serveur :</span><span class="sxs-lookup"><span data-stu-id="f369c-112">...only this part of the query is sent to the server:</span></span>  
  
```  
SELECT FirstName, LastName  
FROM   Person.Contact  
```  
  
 <span data-ttu-id="f369c-113">Le serveur exécute la requête et retourne un ensemble de lignes (qui contient FirstName et LastNamecolumns) au client.</span><span class="sxs-lookup"><span data-stu-id="f369c-113">The server executes the query and returns a rowset (which contains FirstName and LastNamecolumns) to the client.</span></span> <span data-ttu-id="f369c-114">La couche intermédiaire applique ensuite la transformation FOR XML à l'ensemble de lignes et retourne la mise en forme XML au client.</span><span class="sxs-lookup"><span data-stu-id="f369c-114">The middle tier then applies the FOR XML transformation to the rowset and returns XML formatting to the client.</span></span>  
  
 <span data-ttu-id="f369c-115">De la même façon, lorsque vous exécutez une requête XPath, le serveur retourne l'ensemble de lignes au client et la transformation FOR XML EXPLICIT est appliquée à l'ensemble de lignes sur le client, ce qui génère la mise en forme XML souhaitée.</span><span class="sxs-lookup"><span data-stu-id="f369c-115">Similarly, when you execute an XPath query, the server returns the rowset to the client and the FOR XML EXPLICIT transformation is applied to the rowset on the client, generating the desired XML formatting.</span></span>  
  
 <span data-ttu-id="f369c-116">Le tableau suivant montre les modes que vous pouvez spécifier avec FOR XML côté client.</span><span class="sxs-lookup"><span data-stu-id="f369c-116">The following table shows the modes you can specify with client-side FOR XML.</span></span>  
  
|<span data-ttu-id="f369c-117">Mode FOR XML côté client</span><span class="sxs-lookup"><span data-stu-id="f369c-117">Client-side FOR XML mode</span></span>|<span data-ttu-id="f369c-118">Commentaire</span><span class="sxs-lookup"><span data-stu-id="f369c-118">Comment</span></span>|  
|-------------------------------|-------------|  
|<span data-ttu-id="f369c-119">RAW</span><span class="sxs-lookup"><span data-stu-id="f369c-119">RAW</span></span>|<span data-ttu-id="f369c-120">Produit des résultats identiques lors de la spécification de FOR XML côté client ou côté serveur.</span><span class="sxs-lookup"><span data-stu-id="f369c-120">Produces identical results when specified in client-side or server-side FOR XML.</span></span>|  
|<span data-ttu-id="f369c-121">NESTED</span><span class="sxs-lookup"><span data-stu-id="f369c-121">NESTED</span></span>|<span data-ttu-id="f369c-122">Est semblable au mode FOR XML AUTO côté serveur.</span><span class="sxs-lookup"><span data-stu-id="f369c-122">Is similar to FOR XML AUTO mode on the server-side.</span></span>|  
|<span data-ttu-id="f369c-123">EXPLICIT</span><span class="sxs-lookup"><span data-stu-id="f369c-123">EXPLICIT</span></span>|<span data-ttu-id="f369c-124">Est semblable au mode FOR XML EXPLICIT côté serveur.</span><span class="sxs-lookup"><span data-stu-id="f369c-124">Is similar to server-side FOR XML EXPLICIT mode.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="f369c-125">Si vous spécifiez le mode AUTO et si vous demandez une mise en forme XML côté client, la requête entière est envoyée au serveur ; en d'autres termes, la mise en forme XML s'effectue sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="f369c-125">If you specify AUTO mode and request client-side XML formatting, the entire query is sent to the server; that is, XML formatting occurs on the server.</span></span> <span data-ttu-id="f369c-126">Cela répond à une question de commodité. Toutefois, notez que le mode NESTED retourne les noms de tables de base en tant que noms d'éléments dans le document XML généré.</span><span class="sxs-lookup"><span data-stu-id="f369c-126">This is done for convenience, but note that the NESTED mode returns base table names as element names in the XML document that is generated.</span></span> <span data-ttu-id="f369c-127">Certaines des applications que vous écrivez peuvent nécessiter des noms de tables de base.</span><span class="sxs-lookup"><span data-stu-id="f369c-127">Some of the applications you write might require base table names.</span></span> <span data-ttu-id="f369c-128">Par exemple, vous pouvez exécuter une procédure stockée et charger les données résultantes dans un dataset (dans [!INCLUDE[msCoName](../../../includes/msconame-md.md)].NET Framework), puis générer ultérieurement un DiffGram pour mettre à jour les données dans les tables.</span><span class="sxs-lookup"><span data-stu-id="f369c-128">For example, you might execute a stored procedure and load the resulting data in a Dataset (in the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework), and then later generate a DiffGram to update data in the tables.</span></span> <span data-ttu-id="f369c-129">Dans ce cas, vous avez besoin des informations sur les tables de base et vous devez utiliser le mode NESTED.</span><span class="sxs-lookup"><span data-stu-id="f369c-129">In such a case, you would need the base table information and you would have to use the NESTED mode.</span></span>  
  
## <a name="benefits-of-client-side-xml-formatting"></a><span data-ttu-id="f369c-130">Avantages de la mise en forme XML côté client</span><span class="sxs-lookup"><span data-stu-id="f369c-130">Benefits of Client-side XML formatting</span></span>  
 <span data-ttu-id="f369c-131">Vous trouverez ci-après la description de certains avantages liés à la mise en forme XML sur le client.</span><span class="sxs-lookup"><span data-stu-id="f369c-131">The following are some benefits of formatting XML on the client.</span></span>  
  
### <a name="if-you-have-stored-procedures-on-the-server-that-return-a-single-rowset-you-can-request-client-side-for-xml-transformation-to-generate-an-xml"></a><span data-ttu-id="f369c-132">Si vous avez des procédures stockées sur le serveur qui retournent un ensemble de lignes unique, vous pouvez demander une transformation FOR XML côté client pour générer du code XML.</span><span class="sxs-lookup"><span data-stu-id="f369c-132">If you have stored procedures on the server that return a single rowset, you can request client-side FOR XML transformation to generate an XML.</span></span>  
 <span data-ttu-id="f369c-133">Prenons l'exemple de la procédure stockée ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="f369c-133">For example, consider the following stored procedure.</span></span> <span data-ttu-id="f369c-134">Cette procédure retourne les noms et prénoms des employés à partir de la table Person.Contact de la base de données AdventureWorks :</span><span class="sxs-lookup"><span data-stu-id="f369c-134">This procedure returns the first and last names of employees from the Person.Contact table in the AdventureWorks database:</span></span>  
  
```  
IF EXISTS (SELECT name FROM sysobjects  
   WHERE name = 'GetContacts' AND type = 'P')  
   DROP PROCEDURE GetContacts  
GO  
CREATE PROCEDURE GetContacts  
AS  
    SELECT   FirstName, LastName  
    FROM     Person.Contact  
```  
  
 <span data-ttu-id="f369c-135">L'exemple de modèle XML suivant exécute la procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="f369c-135">The following sample XML template executes the stored procedure.</span></span> <span data-ttu-id="f369c-136">La clause FOR XML est spécifiée après le nom de la procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="f369c-136">The FOR XML clause is specified after the stored procedure name.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query client-side-xml="1">  
    EXEC GetContacts FOR XML NESTED  
  </sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="f369c-137">Étant donné que l’attribut **Client-Side-XML** a la valeur 1 (true) dans le modèle, la procédure stockée est exécutée sur le serveur et l’ensemble de lignes à deux colonnes retourné par le serveur est transformé en XML sur la couche intermédiaire et retourné au client.</span><span class="sxs-lookup"><span data-stu-id="f369c-137">Because the **client-side-xml** attribute is set to 1 (true) in the template, the stored procedure is executed on the server and the two-column rowset that is returned by the server is transformed into XML on the middle tier and returned to the client.</span></span> <span data-ttu-id="f369c-138">(Seul un résultat partiel est montré ici.)</span><span class="sxs-lookup"><span data-stu-id="f369c-138">(Only a partial result is shown here.)</span></span>  
  
```  
 <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Person.Contact FirstName="Gustavo" LastName="Achong" />   
  <Person.Contact FirstName="Catherine" LastName="Abel" />  
</ROOT>  
```  
  
> [!NOTE]  
>  <span data-ttu-id="f369c-139">Lorsque vous utilisez le fournisseur SQLXMLOLEDB ou les classes managées SQLXML, vous pouvez utiliser la propriété `ClientSideXml` pour demander une mise en forme XML côté client.</span><span class="sxs-lookup"><span data-stu-id="f369c-139">When you are using the SQLXMLOLEDB Provider or SQLXML Managed Classes, you can use the `ClientSideXml` property to request client-side XML formatting.</span></span>  
  
### <a name="the-workload-is-more-balanced"></a><span data-ttu-id="f369c-140">La charge de travail est plus équilibrée.</span><span class="sxs-lookup"><span data-stu-id="f369c-140">The workload is more balanced.</span></span>  
 <span data-ttu-id="f369c-141">Dans la mesure où le client effectue la mise en forme XML, la charge de travail est équilibrée entre le serveur et le client, ce qui permet au serveur d'exécuter d'autres tâches.</span><span class="sxs-lookup"><span data-stu-id="f369c-141">Because the client does the XML formatting, the workload is balanced between the server and client, freeing the server to do other things.</span></span>  
  
## <a name="supporting-client-side-xml-formatting"></a><span data-ttu-id="f369c-142">Prise en charge de la mise en forme XML côté client</span><span class="sxs-lookup"><span data-stu-id="f369c-142">Supporting Client-side XML Formatting</span></span>  
 <span data-ttu-id="f369c-143">Pour permettre la prise en charge des fonctionnalités de mise en forme XML côté client, SQLXML offre les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="f369c-143">To support the client-side XML formatting functionality, SQLXML provides:</span></span>  
  
-   <span data-ttu-id="f369c-144">fournisseur SQLXMLOLEDB</span><span class="sxs-lookup"><span data-stu-id="f369c-144">SQLXMLOLEDB Provider</span></span>  
  
-   <span data-ttu-id="f369c-145">classes managées SQLXML</span><span class="sxs-lookup"><span data-stu-id="f369c-145">SQLXML Managed Classes</span></span>  
  
-   <span data-ttu-id="f369c-146">prise en charge améliorée du modèle XML.</span><span class="sxs-lookup"><span data-stu-id="f369c-146">Enhanced XML template support</span></span>  
  
-   <span data-ttu-id="f369c-147">SqlXmlCommand. ClientSideXml, propriété</span><span class="sxs-lookup"><span data-stu-id="f369c-147">SqlXmlCommand.ClientSideXml property</span></span>  
  
     <span data-ttu-id="f369c-148">Vous pouvez spécifier la mise en forme côté client en définissant cette propriété des classes managées SQLXML à true.</span><span class="sxs-lookup"><span data-stu-id="f369c-148">You can specify client-side formatting by setting this property of the SQLXML managed classes to true.</span></span>  
  
## <a name="enhanced-xml-template-support"></a><span data-ttu-id="f369c-149">Prise en charge améliorée du modèle XML.</span><span class="sxs-lookup"><span data-stu-id="f369c-149">Enhanced XML Template Support</span></span>  
 <span data-ttu-id="f369c-150">À partir de [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] , le modèle XML dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] a été amélioré avec l’ajout de l’attribut **XML côté client** .</span><span class="sxs-lookup"><span data-stu-id="f369c-150">Beginning with [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], the XML template in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] has been enhanced with the addition of the **client-side-xml** attribute.</span></span> <span data-ttu-id="f369c-151">Si cet attribut a la valeur true, le code XML est mis en forme sur le client.</span><span class="sxs-lookup"><span data-stu-id="f369c-151">If this attribute is set to true, XML is formatted on the client.</span></span> <span data-ttu-id="f369c-152">Notez que cet attribut de modèle est identique dans les fonctionnalités de la propriété ClientSideXML spécifique au fournisseur SQLXMLOLEDB.</span><span class="sxs-lookup"><span data-stu-id="f369c-152">Note that this template attribute is identical in functionality to the SQLXMLOLEDB Provider-specific ClientSideXML property.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f369c-153">Si vous exécutez un modèle XML dans une application ADO qui utilise le fournisseur SQLXMLOLEDB et que vous spécifiez à la fois l’attribut **Client-Side-XML** dans le modèle et la propriété ClientSideXML du fournisseur, la valeur spécifiée dans le modèle est prioritaire.</span><span class="sxs-lookup"><span data-stu-id="f369c-153">If you execute an XML template in an ADO application that is using the SQLXMLOLEDB Provider, and you specify both the **client-side-xml** attribute in the template and the provider ClientSideXML property, the value specified in the template takes precedence.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f369c-154">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f369c-154">See Also</span></span>  
 <span data-ttu-id="f369c-155">[Architecture de la mise en forme XML côté client et côté serveur &#40;SQLXML 4,0&#41;](server-side-xml-formatting-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="f369c-155">[Architecture of Client-side and Server-side XML Formatting &#40;SQLXML 4.0&#41;](server-side-xml-formatting-sqlxml-4-0.md) </span></span>  
 <span data-ttu-id="f369c-156">[FOR XML &#40;SQL Server&#41;](../../xml/for-xml-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f369c-156">[FOR XML &#40;SQL Server&#41;](../../xml/for-xml-sql-server.md) </span></span>  
 <span data-ttu-id="f369c-157">[Considérations relatives à la sécurité XML &#40;SQLXML 4,0&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/security/for-xml-security-considerations-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="f369c-157">[FOR XML Security Considerations &#40;SQLXML 4.0&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/security/for-xml-security-considerations-sqlxml-4-0.md) </span></span>  
 <span data-ttu-id="f369c-158">[Prise en charge des types de données XML dans SQLXML 4,0](../xml-data-type-support-in-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="f369c-158">[xml Data Type Support in SQLXML 4.0](../xml-data-type-support-in-sqlxml-4-0.md) </span></span>  
 <span data-ttu-id="f369c-159">[Classes managées SQLXML](../../sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/sqlxml-4-0-net-framework-support-managed-classes.md) </span><span class="sxs-lookup"><span data-stu-id="f369c-159">[SQLXML Managed Classes](../../sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/sqlxml-4-0-net-framework-support-managed-classes.md) </span></span>  
 <span data-ttu-id="f369c-160">[Mise en forme XML côté client et côté serveur &#40;SQLXML 4,0&#41;](client-side-vs-server-side-xml-formatting-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="f369c-160">[Client-side vs. Server-side XML Formatting &#40;SQLXML 4.0&#41;](client-side-vs-server-side-xml-formatting-sqlxml-4-0.md) </span></span>  
 <span data-ttu-id="f369c-161">[Objet SqlXmlCommand &#40;les classes managées SQLXML&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/sqlxml-managed-classes-sqlxmlcommand-object.md) </span><span class="sxs-lookup"><span data-stu-id="f369c-161">[SqlXmlCommand Object &#40;SQLXML Managed Classes&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/sqlxml-managed-classes-sqlxmlcommand-object.md) </span></span>  
 [<span data-ttu-id="f369c-162">Données XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f369c-162">XML Data &#40;SQL Server&#41;</span></span>](../../xml/xml-data-sql-server.md)  
  
  
