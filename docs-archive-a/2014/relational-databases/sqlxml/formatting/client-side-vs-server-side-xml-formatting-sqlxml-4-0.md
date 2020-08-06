---
title: Mise en forme XML côté client et côté serveur (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- NESTED mode
- FOR XML clause, formatting
- client-side XML formatting
- server-side XPath
- server-side XML formatting
- AUTO mode
- client-side XPath
ms.assetid: f807ab7a-c5f8-4e61-9b00-23aebfabc47e
author: rothja
ms.author: jroth
ms.openlocfilehash: fa155fc6d346cb90de54e5599aca1c296623faa7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611666"
---
# <a name="client-side-vs-server-side-xml-formatting-sqlxml-40"></a><span data-ttu-id="5c0fa-102">Côté client et Mise en forme XML côté serveur (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="5c0fa-102">Client-side vs. Server-side XML Formatting (SQLXML 4.0)</span></span>
  <span data-ttu-id="5c0fa-103">Cette rubrique décrit les principales différences entre la mise en forme XML côté client et côté serveur dans SQLXML.</span><span class="sxs-lookup"><span data-stu-id="5c0fa-103">This topic describes the general differences between client-side and server-side XML formatting in SQLXML.</span></span>  
  
## <a name="multiple-rowset-queries-not-supported-in-client-side-formatting"></a><span data-ttu-id="5c0fa-104">Les requêtes générant plusieurs ensembles de lignes ne sont pas prises en charge dans la mise en forme côté client</span><span class="sxs-lookup"><span data-stu-id="5c0fa-104">Multiple Rowset Queries Not Supported in Client-side Formatting</span></span>  
 <span data-ttu-id="5c0fa-105">Les requêtes qui génèrent plusieurs ensembles de lignes ne sont pas prises en charge lorsque vous utilisez la mise en forme XML côté client.</span><span class="sxs-lookup"><span data-stu-id="5c0fa-105">Queries that generate multiple rowsets are not supported when you use client-side XML formatting.</span></span> <span data-ttu-id="5c0fa-106">Supposons par exemple que vous ayez un répertoire virtuel dans lequel une mise en forme côté client est spécifiée.</span><span class="sxs-lookup"><span data-stu-id="5c0fa-106">For example, assume you have a virtual directory in which you have client-side formatting specified.</span></span> <span data-ttu-id="5c0fa-107">Considérez cet exemple de modèle, qui contient deux instructions SELECT dans un **\<sql:query>** bloc :</span><span class="sxs-lookup"><span data-stu-id="5c0fa-107">Consider this sample template, which has two SELECT statements in a **\<sql:query>** block:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query>  
     SELECT FirstName FROM Person.Contact FOR XML Nested;   
     SELECT LastName FROM Person.Contact FOR XML Nested    
  </sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="5c0fa-108">Si vous exécutez ce modèle dans un code d'application, une erreur est alors retournée car la mise en forme XML côté client ne prend pas en charge la mise en forme de plusieurs ensembles de lignes.</span><span class="sxs-lookup"><span data-stu-id="5c0fa-108">You can execute this template in application code and an error is returned, because client-side XML formatting does not support formatting of multiple rowsets.</span></span> <span data-ttu-id="5c0fa-109">Si vous spécifiez les requêtes dans deux **\<sql:query>** blocs distincts, vous obtiendrez les résultats souhaités.</span><span class="sxs-lookup"><span data-stu-id="5c0fa-109">If you specify the queries in two separate **\<sql:query>** blocks, you will get the desired results.</span></span>  
  
## <a name="timestamp-maps-differently-in-client--vs-server-side-formatting"></a><span data-ttu-id="5c0fa-110">timestamp est mappé différemment dans la mise en forme côté client et la mise en forme côté serveur</span><span class="sxs-lookup"><span data-stu-id="5c0fa-110">timestamp Maps Differently in Client- vs. Server-side Formatting</span></span>  
 <span data-ttu-id="5c0fa-111">Dans la mise en forme XML côté serveur, la colonne de base de données de type `timestamp` est mappée au type XDR i8 (lorsque l'option XMLDATA est spécifiée dans la requête).</span><span class="sxs-lookup"><span data-stu-id="5c0fa-111">In server-side XML formatting, the database column of `timestamp` type maps to the i8 XDR type (when the XMLDATA option is specified in the query).</span></span>  
  
 <span data-ttu-id="5c0fa-112">Dans la mise en forme XML côté client, la colonne de base de données de type `timestamp` est mappée au type XDR `uri` ou `bin.base64` (selon que l'option BINARY BASE64 est spécifiée dans la requête).</span><span class="sxs-lookup"><span data-stu-id="5c0fa-112">In client-side XML formatting, the database column of `timestamp` type maps to either the `uri` or the `bin.base64` XDR type (depending on whether the binary base64 option is specified in the query).</span></span> <span data-ttu-id="5c0fa-113">Le `bin.base64` type XDR est utile si vous utilisez les fonctionnalités mise à jour et bulkload, car ce type est converti en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] `timestamp` type.</span><span class="sxs-lookup"><span data-stu-id="5c0fa-113">The `bin.base64` XDR type is useful if you use the updategram and bulkload features, because this type is converted to the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] `timestamp` type.</span></span> <span data-ttu-id="5c0fa-114">De cette manière, l'opération insert, update ou delete réussit.</span><span class="sxs-lookup"><span data-stu-id="5c0fa-114">This way, the insert, update, or delete operation succeeds.</span></span>  
  
## <a name="deep-variants-are-used-in-server-side-formatting"></a><span data-ttu-id="5c0fa-115">Les sous-types Deep du type VARIANT sont utilisés dans la mise en forme côté serveur</span><span class="sxs-lookup"><span data-stu-id="5c0fa-115">Deep VARIANTs Are Used in Server-side Formatting</span></span>  
 <span data-ttu-id="5c0fa-116">Dans la mise en forme XML côté serveur, les types Deep d'un type de données VARIANT sont utilisés.</span><span class="sxs-lookup"><span data-stu-id="5c0fa-116">In server-side XML formatting, the deep types of a VARIANT type are used.</span></span> <span data-ttu-id="5c0fa-117">Si vous utilisez la mise en forme XML côté client, les variantes sont converties en chaîne Unicode et les sous-types de VARIANT ne sont pas utilisés.</span><span class="sxs-lookup"><span data-stu-id="5c0fa-117">If you use client-side XML formatting, the variants are converted to Unicode string, and the subtypes of VARIANT are not used.</span></span>  
  
## <a name="nested-mode-vs-auto-mode"></a><span data-ttu-id="5c0fa-118">Mode NESTED et mode AUTO</span><span class="sxs-lookup"><span data-stu-id="5c0fa-118">NESTED Mode vs. AUTO Mode</span></span>  
 <span data-ttu-id="5c0fa-119">Le mode NESTED de FOR XML côté client est semblable au mode AUTO de FOR XML côté serveur, avec les exceptions suivantes :</span><span class="sxs-lookup"><span data-stu-id="5c0fa-119">The NESTED mode of the client-side FOR XML is similar to the AUTO mode of server-side FOR XML, with the following exceptions:</span></span>  
  
### <a name="when-you-query-views-using-auto-mode-on-the-server-side-the-view-name-is-returned-as-the-element-name-in-the-resulting-xml"></a><span data-ttu-id="5c0fa-120">Lorsque vous interrogez des vues à l'aide du mode AUTO côté serveur, le nom de la vue est retourné comme nom de l'élément dans le XML résultant.</span><span class="sxs-lookup"><span data-stu-id="5c0fa-120">When you query views using AUTO mode on the server-side, the view name is returned as the element name in the resulting XML.</span></span>  
 <span data-ttu-id="5c0fa-121">Par exemple, supposons que la vue suivante est créée sur la table Person. contact dans AdventureWorksdatabase :</span><span class="sxs-lookup"><span data-stu-id="5c0fa-121">For example, assume that the following view is created on the Person.Contact table in the AdventureWorksdatabase:</span></span>  
  
```  
CREATE VIEW ContactView AS (SELECT ContactID as CID,  
                               FirstName  as FName,  
                               LastName  as LName  
                        FROM Person.Contact)  
```  
  
 <span data-ttu-id="5c0fa-122">Le modèle suivant spécifie une requête sur la vue ContactView, de même que la mise en forme XML côté serveur :</span><span class="sxs-lookup"><span data-stu-id="5c0fa-122">The following template specifies a query against the ContactView view, and also specifies server-side XML formatting:</span></span>  
  
```  
 <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query client-side-xml="0">  
    SELECT *  
    FROM   ContactView  
    FOR XML AUTO  
  </sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="5c0fa-123">Lorsque vous exécutez le modèle, le XML suivant est retourné</span><span class="sxs-lookup"><span data-stu-id="5c0fa-123">When you execute the template, the following XML is returned.</span></span> <span data-ttu-id="5c0fa-124">(Seuls les résultats partiels sont affichés.) Notez que les noms d’éléments sont les noms des vues sur lesquelles la requête est exécutée.</span><span class="sxs-lookup"><span data-stu-id="5c0fa-124">(Only partial results are shown.) Note that the element names are the names of the views against which the query is executed.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <ContactView CID="1" FName="Gustavo" LName="Achong" />   
  <ContactView CID="2" FName="Catherine" LName="Abel" />   
...  
</ROOT>  
```  
  
 <span data-ttu-id="5c0fa-125">Lorsque vous spécifiez la mise en forme XML côté client en utilisant le mode NESTED correspondant, les noms des tables de base sont retournés comme noms des éléments dans le XML résultant.</span><span class="sxs-lookup"><span data-stu-id="5c0fa-125">When you specify client-side XML formatting by using the corresponding NESTED mode, the base table name(s) are returned as the element name(s) in the resulting XML.</span></span> <span data-ttu-id="5c0fa-126">Par exemple, le modèle modifié suivant exécute la même instruction SELECT, mais la mise en forme XML est effectuée côté client (autrement dit, le **code XML côté client** est défini sur true dans le modèle) :</span><span class="sxs-lookup"><span data-stu-id="5c0fa-126">For example, the following revised template executes the same SELECT statement, but the XML formatting is performed on the client-side (that is, **client-side-xml** is set to true in the template):</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query client-side-xml="1">  
    SELECT *  
    FROM   ContactView  
    FOR XML NESTED  
  </sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="5c0fa-127">L'exécution de ce modèle génère le XML suivant.</span><span class="sxs-lookup"><span data-stu-id="5c0fa-127">Executing this template produces the following XML.</span></span> <span data-ttu-id="5c0fa-128">Notez que dans ce cas, le nom de l'élément correspond au nom de la table de base.</span><span class="sxs-lookup"><span data-stu-id="5c0fa-128">Note that the element name is the base table name in this case.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Person.Contact CID="1" FName="Gustavo" LName="Achong" />   
  <Person.Contact CID="2" FName="Catherine" LName="Abel" />   
...  
</ROOT>  
```  
  
### <a name="when-you-use-auto-mode-of-the-server-side-for-xml-the-table-aliases-specified-in-the-query-are-returned-as-element-names-in-the-resulting-xml"></a><span data-ttu-id="5c0fa-129">Lorsque vous utilisez le mode AUTO de FOR XML côté serveur, les alias de tables spécifiés dans la requête sont retournés en tant que noms des éléments dans le XML résultant.</span><span class="sxs-lookup"><span data-stu-id="5c0fa-129">When you use AUTO mode of the server-side FOR XML, the table aliases specified in the query are returned as element names in the resulting XML.</span></span>  
 <span data-ttu-id="5c0fa-130">Considérons par exemple le modèle suivant :</span><span class="sxs-lookup"><span data-stu-id="5c0fa-130">For example, consider this template:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query client-side-xml="0">  
    SELECT FirstName as fname,  
           LastName as lname  
    FROM   Person.Contact C  
    FOR XML AUTO  
  </sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="5c0fa-131">L'exécution de ce modèle génère le XML suivant :</span><span class="sxs-lookup"><span data-stu-id="5c0fa-131">Executing the template produces the following XML:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <C fname="Gustavo" lname="Achong" />   
  <C fname="Catherine" lname="Abel" />   
...  
</ROOT>   
```  
  
 <span data-ttu-id="5c0fa-132">Lorsque vous utilisez le mode NESTED de FOR XML côté client, les noms des tables sont retournés en tant que noms des éléments dans le XML résultant.</span><span class="sxs-lookup"><span data-stu-id="5c0fa-132">When you use the NESTED mode of the client-side FOR XML, the table names are returned as element names in the resulting XML.</span></span> <span data-ttu-id="5c0fa-133">(Les alias de tables spécifiés dans la requête ne sont pas utilisés.) Par exemple, considérez ce modèle :</span><span class="sxs-lookup"><span data-stu-id="5c0fa-133">(Table aliases that are specified in the query are not used.) For example, consider this template:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query client-side-xml="1">  
    SELECT FirstName as fname,  
           LastName as lname  
    FROM   Person.Contact C  
    FOR XML NESTED  
  </sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="5c0fa-134">L'exécution de ce modèle génère le XML suivant :</span><span class="sxs-lookup"><span data-stu-id="5c0fa-134">Executing the template produces the following XML:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Person.Contact fname="Gustavo" lname="Achong" />   
  <Person.Contact fname="Catherine" lname="Abel" />   
...  
</ROOT>  
```  
  
### <a name="if-you-have-a-query-that-returns-columns-as-dbobject-queries-you-cannot-use-aliases-for-these-columns"></a><span data-ttu-id="5c0fa-135">Si une requête retourne des colonnes sous forme de requêtes dbobject, vous ne pouvez pas utiliser d'alias pour ces colonnes.</span><span class="sxs-lookup"><span data-stu-id="5c0fa-135">If you have a query that returns columns as dbobject queries, you cannot use aliases for these columns.</span></span>  
 <span data-ttu-id="5c0fa-136">Considérons par exemple le modèle suivant qui exécute une requête retournant un ID d'employé et une photo.</span><span class="sxs-lookup"><span data-stu-id="5c0fa-136">For example, consider the following template, which executes a query that returns an employee ID and a photo.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
<sql:query client-side-xml="1">  
   SELECT ProductPhotoID, LargePhoto as P  
   FROM   Production.ProductPhoto  
   WHERE  ProductPhotoID=5  
   FOR XML NESTED, elements  
</sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="5c0fa-137">L'exécution de ce modèle retourne la colonne Photo sous forme de requête dbobject.</span><span class="sxs-lookup"><span data-stu-id="5c0fa-137">Executing this template returns the Photo column as a dbobject query.</span></span> <span data-ttu-id="5c0fa-138">Dans cette requête dbobject, `@P` fait référence à un nom de colonne qui n'existe pas.</span><span class="sxs-lookup"><span data-stu-id="5c0fa-138">In this dbobject query, `@P` refers to a column name that does not exist.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Production.ProductPhoto>  
    <ProductPhotoID>5</ProductPhotoID>  
    <LargePhoto>dbobject/Production.ProductPhoto[@ProductPhotoID='5']/@P</LargePhoto>  
  </Production.ProductPhoto>  
</ROOT>  
```  
  
 <span data-ttu-id="5c0fa-139">Si la mise en forme XML est effectuée sur le serveur (**client-side-xml = "0"**), vous pouvez utiliser l’alias pour les colonnes qui retournent des requêtes DBOBJECT dans lesquelles les noms de tables et de colonnes réels sont retournés (même si vous avez spécifié des alias).</span><span class="sxs-lookup"><span data-stu-id="5c0fa-139">If the XML formatting is done on the server (**client-side-xml="0"**), you can use the alias for the columns that return dbobject queries in which actual table and column names are returned (even if you have aliases specified).</span></span> <span data-ttu-id="5c0fa-140">Par exemple, le modèle suivant exécute une requête, et la mise en forme XML est effectuée sur le serveur (l’option **Client-Side-XML** n’est pas spécifiée et l’option **exécuter sur le client** n’est pas sélectionnée pour la racine virtuelle).</span><span class="sxs-lookup"><span data-stu-id="5c0fa-140">For example, the following template executes a query, and the XML formatting is done on the server (the **client-side-xml** option is not specified and the **Run On Client** option is not selected for the virtual root).</span></span> <span data-ttu-id="5c0fa-141">La requête spécifie également le mode AUTO (pas le mode NESTED côté client).</span><span class="sxs-lookup"><span data-stu-id="5c0fa-141">The query also specifies AUTO mode (not the client-side NESTED mode).</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
<sql:query   
   SELECT ProductPhotoID, LargePhoto as P  
   FROM   Production.ProductPhoto  
   WHERE  ProductPhotoID=5  
   FOR XML AUTO, elements  
</sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="5c0fa-142">Lorsque ce modèle est exécuté, le document XML suivant est retourné (notez que les alias ne sont pas utilisés dans la requête dbobject pour la colonne LargePhoto) :</span><span class="sxs-lookup"><span data-stu-id="5c0fa-142">When this template is executed, the following XML document is returned (note that aliases are not used in the dbobject query for the LargePhoto column):</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Production.ProductPhoto>  
    <ProductPhotoID>5</ProductPhotoID>  
    <LargePhoto>dbobject/Production.ProductPhoto[@ProductPhotoID='5']/@LargePhoto</LargePhoto>  
  </Production.ProductPhoto>  
</ROOT>  
```  
  
### <a name="client-side-vs-server-side-xpath"></a><span data-ttu-id="5c0fa-143">XPath côté client et côté serveur</span><span class="sxs-lookup"><span data-stu-id="5c0fa-143">Client-side vs. Server-side XPath</span></span>  
 <span data-ttu-id="5c0fa-144">XPath côté client et XPath côté serveur fonctionnement de la même manière, à quelques différences près :</span><span class="sxs-lookup"><span data-stu-id="5c0fa-144">Client-side XPath and server-side XPath work the same except for these differences:</span></span>  
  
-   <span data-ttu-id="5c0fa-145">Les conversions de données appliquées lorsque vous utilisez des requêtes XPath côté client sont différentes de celles qui s'appliquent lorsque vous utilisez des requêtes XPath côté serveur.</span><span class="sxs-lookup"><span data-stu-id="5c0fa-145">The data conversions that are applied when you use client-side XPath queries are different from those that are applied when you use server-side XPath queries.</span></span> <span data-ttu-id="5c0fa-146">Les requêtes XPath côté client utilisent CAST au lieu du mode CONVERT 126.</span><span class="sxs-lookup"><span data-stu-id="5c0fa-146">Client-side XPath uses CAST instead of CONVERT mode 126.</span></span>  
  
-   <span data-ttu-id="5c0fa-147">Lorsque vous spécifiez **client-side-xml = "0"** (false) dans un modèle, vous demandez une mise en forme XML côté serveur.</span><span class="sxs-lookup"><span data-stu-id="5c0fa-147">When you specify **client-side-xml="0"** (false) in a template, you are requesting server-side XML formatting.</span></span> <span data-ttu-id="5c0fa-148">Par conséquent, vous ne pouvez pas spécifier FOR XML NESTED car le serveur ne reconnaît pas l'option NESTED.</span><span class="sxs-lookup"><span data-stu-id="5c0fa-148">Therefore, you cannot specify FOR XML NESTED because the server does not recognize the NESTED option.</span></span> <span data-ttu-id="5c0fa-149">Cela génère une erreur.</span><span class="sxs-lookup"><span data-stu-id="5c0fa-149">This generates an error.</span></span> <span data-ttu-id="5c0fa-150">Vous devez utiliser les modes AUTO, RAW ou EXPLICIT, que le serveur reconnaît.</span><span class="sxs-lookup"><span data-stu-id="5c0fa-150">You must use the AUTO, RAW, or EXPLICIT modes, which the server does recognize.</span></span>  
  
-   <span data-ttu-id="5c0fa-151">Lorsque vous spécifiez **client-side-xml = "1"** (true) dans un modèle, vous demandez la mise en forme XML côté client.</span><span class="sxs-lookup"><span data-stu-id="5c0fa-151">When you specify **client-side-xml="1"** (true) in a template, you are requesting client-side XML formatting.</span></span> <span data-ttu-id="5c0fa-152">Dans ce cas, vous pouvez spécifier FOR XML NESTED.</span><span class="sxs-lookup"><span data-stu-id="5c0fa-152">In this case, you can specify FOR XML NESTED.</span></span> <span data-ttu-id="5c0fa-153">Si vous spécifiez FOR XML AUTO, la mise en forme XML se produit côté serveur, bien que le **client-side-xml = "1"** soit spécifié dans le modèle.</span><span class="sxs-lookup"><span data-stu-id="5c0fa-153">If you specify FOR XML AUTO, the XML formatting occurs on the server side although **client-side-xml="1"** is specified in the template.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c0fa-154">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5c0fa-154">See Also</span></span>  
 <span data-ttu-id="5c0fa-155">[Considérations relatives à la sécurité XML &#40;SQLXML 4,0&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/security/for-xml-security-considerations-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="5c0fa-155">[FOR XML Security Considerations &#40;SQLXML 4.0&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/security/for-xml-security-considerations-sqlxml-4-0.md) </span></span>  
 <span data-ttu-id="5c0fa-156">[Mise en forme XML côté client &#40;SQLXML 4,0&#41;](client-side-xml-formatting-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="5c0fa-156">[Client-side XML Formatting &#40;SQLXML 4.0&#41;](client-side-xml-formatting-sqlxml-4-0.md) </span></span>  
 [<span data-ttu-id="5c0fa-157">La mise en forme XML côté serveur &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="5c0fa-157">Server-side XML Formatting &#40;SQLXML 4.0&#41;</span></span>](server-side-xml-formatting-sqlxml-4-0.md)  
  
  
