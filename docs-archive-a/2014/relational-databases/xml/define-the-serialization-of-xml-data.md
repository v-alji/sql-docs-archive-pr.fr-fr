---
title: Définir la sérialisation des données XML | Microsoft Docs
ms.custom: ''
ms.date: 10/18/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- entitization rules [XML in SQL Server]
- serialization
- reparsing serialized XML structures
- encoding [XML in SQL Server]
- XML [SQL Server], serialization
- xml data type [SQL Server], serialization
- typed XML
ms.assetid: 42b0b5a4-bdd6-4a60-b451-c87f14758d4b
author: rothja
ms.author: jroth
ms.openlocfilehash: df87dddd9fd4cf067125314c9d798eaa42523576
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614410"
---
# <a name="define-the-serialization-of-xml-data"></a><span data-ttu-id="22935-102">Définir la sérialisation des données XML</span><span class="sxs-lookup"><span data-stu-id="22935-102">Define the Serialization of XML Data</span></span>
  <span data-ttu-id="22935-103">Lors de la conversion explicite ou implicite du type de données xml en données SQL de type chaîne ou binaire, le contenu des données de type xml sera sérialisé conformément aux règles présentées dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="22935-103">When casting the xml data type explicitly or implicitly to a SQL string or binary type, the content of the xml data type will be serialized according to the rules outlined in this topic.</span></span>  
  
## <a name="serialization-encoding"></a><span data-ttu-id="22935-104">Encodage de la sérialisation</span><span class="sxs-lookup"><span data-stu-id="22935-104">Serialization Encoding</span></span>  
 <span data-ttu-id="22935-105">Si le type cible SQL est VARBINARY, le résultat est sérialisé au format UTF-16 avec une marque d'ordre d'octet UTF-16 au début, mais sans déclaration XML.</span><span class="sxs-lookup"><span data-stu-id="22935-105">If the SQL target type is VARBINARY, the result is serialized in UTF-16 with a UTF-16-byte order mark in front, but without an XML declaration.</span></span> <span data-ttu-id="22935-106">Si le type cible est trop petit, une erreur est générée.</span><span class="sxs-lookup"><span data-stu-id="22935-106">If the target type is too small, an error is raised.</span></span>  
  
 <span data-ttu-id="22935-107">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="22935-107">For example:</span></span>  
  
```sql
select CAST(CAST(N'<Δ/>' as XML) as VARBINARY(MAX))  
```  
  
 <span data-ttu-id="22935-108">Voici le résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="22935-108">This is the result:</span></span>  
  
```  
0xFFFE3C0094032F003E00  
```  
  
 <span data-ttu-id="22935-109">Si le type cible SQL est NVARCHAR ou NCHAR, le résultat est sérialisé au format UTF-16 sans marque d'ordre d'octet au début ni déclaration XML.</span><span class="sxs-lookup"><span data-stu-id="22935-109">If the SQL target type is NVARCHAR or NCHAR, the result is serialized in UTF-16 without the byte order mark in front and without an XML declaration.</span></span> <span data-ttu-id="22935-110">Si le type cible est trop petit, une erreur est générée.</span><span class="sxs-lookup"><span data-stu-id="22935-110">If the target type is too small, an error is raised.</span></span>  
  
 <span data-ttu-id="22935-111">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="22935-111">For example:</span></span>  
  
```sql
select CAST(CAST(N'<Δ/>' as XML) as NVARCHAR(MAX))  
```  
  
 <span data-ttu-id="22935-112">Voici le résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="22935-112">This is the result:</span></span>  
  
```  
<Δ/>  
```  
  
 <span data-ttu-id="22935-113">Si le type cible SQL est VARCHAR ou NCHAR, le résultat est sérialisé dans l'encodage correspondant à la page de codes du classement de la base de données sans marque d'ordre d'octet ni déclaration XML.</span><span class="sxs-lookup"><span data-stu-id="22935-113">If the SQL target type is VARCHAR or NCHAR, the result is serialized in the encoding that corresponds to the database's collation code page without a byte order mark or XML declaration.</span></span> <span data-ttu-id="22935-114">Si le type cible est trop petit ou s'il est impossible de faire correspondre la valeur à la page de codes du classement de la cible, une erreur est générée.</span><span class="sxs-lookup"><span data-stu-id="22935-114">If the target type is too small or the value cannot be mapped to the target collation code page, an error is raised.</span></span>  
  
 <span data-ttu-id="22935-115">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="22935-115">For example:</span></span>  
  
```sql
select CAST(CAST(N'<Δ/>' as XML) as VARCHAR(MAX))  
```  
  
 <span data-ttu-id="22935-116">Cela peut entraîner une erreur, si la page de codes du classement actuel ne peut pas représenter le caractère Unicode & # x10300 ;, ou si elle le représente dans l’encodage spécifique.</span><span class="sxs-lookup"><span data-stu-id="22935-116">This may result in an error, if the current collation's code page cannot represent the Unicode character &#x10300;, or it will represent it in the specific encoding.</span></span>  
  
 <span data-ttu-id="22935-117">Lors du renvoi des résultats XML côté client, les données seront transmises en UTF-16.</span><span class="sxs-lookup"><span data-stu-id="22935-117">When returning XML results to the client side, the data will be sent in UTF-16 encoding.</span></span> <span data-ttu-id="22935-118">Le fournisseur côté client exposera ensuite les données d'après les règles de son API.</span><span class="sxs-lookup"><span data-stu-id="22935-118">The client-side provider will then expose the data according to its API rules.</span></span>  
  
## <a name="serialization-of-the-xml-structures"></a><span data-ttu-id="22935-119">Sérialisation des structures XML</span><span class="sxs-lookup"><span data-stu-id="22935-119">Serialization of the XML Structures</span></span>  
 <span data-ttu-id="22935-120">Le contenu d’un type de données **xml** est sérialisé de manière habituelle.</span><span class="sxs-lookup"><span data-stu-id="22935-120">The content of an **xml** data type is serialized in the usual way.</span></span> <span data-ttu-id="22935-121">Plus précisément, les nœuds d'élément sont mappés au balisage d'élément et les nœuds de texte sont mappés au contenu texte.</span><span class="sxs-lookup"><span data-stu-id="22935-121">Specifically, element nodes are mapped to element markup, and text nodes are mapped to text content.</span></span> <span data-ttu-id="22935-122">Les circonstances dans lesquelles les caractères sont décomposés en entités et la façon dont les valeurs atomiques typées sont sérialisées sont décrites dans les sections suivantes.</span><span class="sxs-lookup"><span data-stu-id="22935-122">However, the circumstances under which characters are entitized and how typed atomic values are serialized are described in the following sections.</span></span>  
  
## <a name="entitization-of-xml-characters-during-serialization"></a><span data-ttu-id="22935-123">Codage d'entité des caractères XML au cours de la sérialisation</span><span class="sxs-lookup"><span data-stu-id="22935-123">Entitization of XML Characters During Serialization</span></span>  
 <span data-ttu-id="22935-124">Chaque structure XML sérialisée doit pouvoir subir une nouvelle analyse.</span><span class="sxs-lookup"><span data-stu-id="22935-124">Every serialized XML structure should be capable of being reparsed.</span></span> <span data-ttu-id="22935-125">C’est pourquoi certains caractères doivent être sérialisés à l’aide du codage d’entité de façon à autoriser les accès répétés aux caractères, tout au long de la phase de normalisation de l’analyseur XML.</span><span class="sxs-lookup"><span data-stu-id="22935-125">Therefore, some characters have to be serialized in an entitized way to preserve the round-trip capability of the characters through the XML parser's normalization phase .</span></span> <span data-ttu-id="22935-126">Il s'avère aussi nécessaire de spécifier le codage d'entité de certains caractères afin d'assurer la bonne formation du document et son analyse.</span><span class="sxs-lookup"><span data-stu-id="22935-126">However, some characters have to be entitized so that the document is well-formed and, therefore, able to be parsed.</span></span> <span data-ttu-id="22935-127">Voici les règles de codage d'entité qui s'appliquent au cours de la sérialisation :</span><span class="sxs-lookup"><span data-stu-id="22935-127">Following are the entitization rules that apply during serialization:</span></span>  
  
-   <span data-ttu-id="22935-128">Les caractères &, \<, and > sont toujours codés sous la forme &amp;, &lt; et &gt;, respectivement, s’ils se trouvent dans la valeur d’un attribut ou dans le contenu d’un élément.</span><span class="sxs-lookup"><span data-stu-id="22935-128">The characters &, \<, and > are always entitized to &amp;, &lt;, and &gt; respectively, if they occur inside an attribute value or element content.</span></span>  
  
-   <span data-ttu-id="22935-129">Étant donné que SQL Server utilise les guillemets (U+0022) pour délimiter les valeurs des attributs, le guillemet des valeurs de l’attribut est codé par &quot;.</span><span class="sxs-lookup"><span data-stu-id="22935-129">Because SQL Server uses a quotation mark (U+0022) for enclosing attribute values, the quotation mark in attribute values is entitized as &quot;.</span></span>  
  
-   <span data-ttu-id="22935-130">Une paire de substitution est codée sous forme d'une seule référence de caractère numérique, lors de la conversion sur le serveur uniquement.</span><span class="sxs-lookup"><span data-stu-id="22935-130">A surrogate pair is entitized as a single numeric character reference, when casting on the server only.</span></span> <span data-ttu-id="22935-131">Par exemple, la paire de substitution U+D800 U+DF00 est codée par la référence de caractère numérique &\#x00010300;.</span><span class="sxs-lookup"><span data-stu-id="22935-131">For example the surrogate pair U+D800 U+DF00 is entitized to the numeric character reference &\#x00010300;.</span></span>  
  
-   <span data-ttu-id="22935-132">Pour empêcher la normalisation d’une tabulation (U+0009) et d’un saut de ligne (LF, U+000A) lors de l’analyse, ces derniers sont codés par leurs références de caractère numérique, &\#x9; et &\#xA; respectivement, dans les valeurs des attributs.</span><span class="sxs-lookup"><span data-stu-id="22935-132">To protect a TAB (U+0009) and a linefeed (LF, U+000A) from being normalized during parsing, they are entitized to their numeric character references &\#x9; and &\#xA; respectively, inside attribute values.</span></span>  
  
-   <span data-ttu-id="22935-133">Pour empêcher la normalisation d’un retour chariot (CR, U+000D) lors de l’analyse, ce dernier est codé par sa référence de caractère numérique, &\#xD; dans les valeurs des attributs et le contenu des éléments.</span><span class="sxs-lookup"><span data-stu-id="22935-133">To prevent a carriage return (CR, U+000D) from being normalized during parsing, it is entitized to its numeric character reference, &\#xD; inside both attribute values and element content.</span></span>  
  
-   <span data-ttu-id="22935-134">Pour protéger les nœuds de texte contenant des espaces, l'un des espaces (généralement le dernier) est codé par sa référence de caractère numérique.</span><span class="sxs-lookup"><span data-stu-id="22935-134">To protect text nodes that only contain white space, one of the white-space characters, generally the last one, is entitized as its numeric character reference.</span></span> <span data-ttu-id="22935-135">De cette façon, l'analyse préserve le nœud de texte contenant des espaces, quel que soit le mode de traitement choisi pour les espaces au cours de l'analyse.</span><span class="sxs-lookup"><span data-stu-id="22935-135">In this way, reparsing preserves the white-space text node, regardless of the setting of the white-space handling during parsing.</span></span>  
  
 <span data-ttu-id="22935-136">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="22935-136">For example:</span></span>  
  
```sql
declare @u NVARCHAR(50)  
set @u = N'<a a="  
    '+NCHAR(0xD800)+NCHAR(0xDF00)+N'>">   '+NCHAR(0xA)+N'</a>'  
select CAST(CONVERT(XML,@u,1) as NVARCHAR(50))  
```  
  
 <span data-ttu-id="22935-137">Voici le résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="22935-137">This is the result:</span></span>  
  
```  
<a a="  
    𐌀>">     
</a>  
```  
  
 <span data-ttu-id="22935-138">Si vous ne voulez pas appliquer la règle de protection du dernier espace, vous pouvez utiliser explicitement l’option 1 de CONVERT lors de la conversion de **xml** en type chaîne ou binaire.</span><span class="sxs-lookup"><span data-stu-id="22935-138">If you do not want to apply the last white-space protection rule, you can use the explicit CONVERT option 1 when casting from **xml** to a string or binary type.</span></span> <span data-ttu-id="22935-139">Par exemple, vous pouvez éviter le codage d'entité en procédant ainsi :</span><span class="sxs-lookup"><span data-stu-id="22935-139">For example, to avoid entitization, you can do the following:</span></span>  
  
```sql
select CONVERT(NVARCHAR(50), CONVERT(XML, '<a>   </a>', 1), 1)  
```  
  
 <span data-ttu-id="22935-140">Remarquez que la [méthode query() (type de données xml)](/sql/t-sql/xml/query-method-xml-data-type) génère une instance de type xml.</span><span class="sxs-lookup"><span data-stu-id="22935-140">Note that, the [query() Method (xml Data Type)](/sql/t-sql/xml/query-method-xml-data-type) results in an xml data type instance.</span></span> <span data-ttu-id="22935-141">Ainsi, tout résultat de la méthode **query()** converti en type chaîne ou binaire a recours au codage d’entité conformément aux règles précédemment décrites.</span><span class="sxs-lookup"><span data-stu-id="22935-141">Therefore, any result of the **query()** method that is cast to a string or binary type is entitized according to the previously described rules.</span></span> <span data-ttu-id="22935-142">Si vous souhaitez obtenir les valeurs de chaîne sans conversion en entité, utilisez la [méthode value() (type de données xml)](/sql/t-sql/xml/value-method-xml-data-type) .</span><span class="sxs-lookup"><span data-stu-id="22935-142">If you want to obtain the string values that are not entitized, you should use the [value() Method (xml Data Type)](/sql/t-sql/xml/value-method-xml-data-type) instead.</span></span> <span data-ttu-id="22935-143">L’exemple suivant montre comment utiliser la méthode **query()** :</span><span class="sxs-lookup"><span data-stu-id="22935-143">Following is an example of using the **query()** method:</span></span>  
  
```sql
declare @x xml  
set @x = N'<a>This example contains an entitized char: <.</a>'  
select @x.query('/a/text()')  
```  
  
 <span data-ttu-id="22935-144">Voici le résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="22935-144">This is the result:</span></span>  
  
```  
This example contains an entitized char: <.  
```  
  
 <span data-ttu-id="22935-145">L’exemple suivant montre comment utiliser la méthode **value()** :</span><span class="sxs-lookup"><span data-stu-id="22935-145">Following is an example of using the **value()** method:</span></span>  
  
```sql
select @x.value('(/a/text())[1]', 'nvarchar(100)')  
```  
  
 <span data-ttu-id="22935-146">Voici le résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="22935-146">This is the result:</span></span>  
  
```  
This example contains an entitized char: <.  
```  
  
## <a name="serializing-a-typed-xml-data-type"></a><span data-ttu-id="22935-147">Sérialisation de données typées XML</span><span class="sxs-lookup"><span data-stu-id="22935-147">Serializing a Typed xml Data Type</span></span>  
 <span data-ttu-id="22935-148">Une instance typée **xml** contient des valeurs qui sont typées en fonction de leurs types de schémas XML.</span><span class="sxs-lookup"><span data-stu-id="22935-148">A typed **xml** data type instance contains values that are typed according to their XML schema types.</span></span> <span data-ttu-id="22935-149">Ces valeurs sont sérialisées selon leur type de schéma XML au format que produit la conversion XQuery vers xs:string.</span><span class="sxs-lookup"><span data-stu-id="22935-149">These values are serialized according to their XML schema type in the same format as the XQuery cast to xs:string produces.</span></span> <span data-ttu-id="22935-150">Pour plus d’informations, consultez [Règles de conversion de types dans XQuery](/sql/xquery/type-casting-rules-in-xquery).</span><span class="sxs-lookup"><span data-stu-id="22935-150">For more information, see [Type Casting Rules in XQuery](/sql/xquery/type-casting-rules-in-xquery).</span></span>  
  
 <span data-ttu-id="22935-151">Par exemple, la valeur xs:double 1.34e1 est sérialisée en 13.4 comme le montre l'exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="22935-151">For example, the xs:double value 1.34e1 is serialized to 13.4 as shown in the following example:</span></span>  
  
```sql
declare @x xml  
set @x =''  
select CAST(@x.query('1.34e1') as nvarchar(50))  
```  
  
 <span data-ttu-id="22935-152">Cela renvoie la valeur de chaîne 13.4.</span><span class="sxs-lookup"><span data-stu-id="22935-152">This returns the string value 13.4.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22935-153">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="22935-153">See Also</span></span>  
 <span data-ttu-id="22935-154">[Règles de conversion de types dans XQuery](/sql/xquery/type-casting-rules-in-xquery) </span><span class="sxs-lookup"><span data-stu-id="22935-154">[Type Casting Rules in XQuery](/sql/xquery/type-casting-rules-in-xquery) </span></span>  
 [<span data-ttu-id="22935-155">CAST et CONVERT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="22935-155">CAST and CONVERT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/cast-and-convert-transact-sql)  
  
  
