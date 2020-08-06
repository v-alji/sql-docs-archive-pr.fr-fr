---
title: Syntaxe de base de la clause FOR XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- BINARY BASE64 directive
- ROOT directive
- FOR XML clause, BINARY BASE64 directive
- FOR XML clause, syntax
- FOR XML clause, ROOT directive
ms.assetid: df19ecbf-d28e-4e9c-aaa3-700f8bbd3be4
author: rothja
ms.author: jroth
ms.openlocfilehash: dc0410e7a54674673f64442d8a3cf9476d250033
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600697"
---
# <a name="basic-syntax-of-the-for-xml-clause"></a><span data-ttu-id="da3a7-102">Syntaxe de base de la clause FOR XML</span><span class="sxs-lookup"><span data-stu-id="da3a7-102">Basic Syntax of the FOR XML Clause</span></span>
  <span data-ttu-id="da3a7-103">Le mode de la clause FOR XML peut être RAW, AUTO, EXPLICIT ou PATH.</span><span class="sxs-lookup"><span data-stu-id="da3a7-103">The FOR XML mode can be RAW, AUTO, EXPLICIT, or PATH.</span></span> <span data-ttu-id="da3a7-104">Il détermine la forme du code XML résultant.</span><span class="sxs-lookup"><span data-stu-id="da3a7-104">It determines the shape of the resulting XML.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="da3a7-105">La directive XMLDATA de l'option FOR XML est déconseillée.</span><span class="sxs-lookup"><span data-stu-id="da3a7-105">The XMLDATA directive to the FOR XML option is deprecated.</span></span> <span data-ttu-id="da3a7-106">Utilisez la génération XSD en mode RAW et AUTO.</span><span class="sxs-lookup"><span data-stu-id="da3a7-106">Use XSD generation in the case of RAW and AUTO modes.</span></span> <span data-ttu-id="da3a7-107">Il n'existe aucune solution de remplacement pour la directive XMLDATA en mode EXPLICIT.</span><span class="sxs-lookup"><span data-stu-id="da3a7-107">There is no replacement for the XMLDATA directive in EXPLICT mode.</span></span> [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]  
  
 <span data-ttu-id="da3a7-108">Voici la syntaxe de base décrite dans [clause for (Transact-SQL)](/sql/t-sql/queries/select-for-clause-transact-sql):</span><span class="sxs-lookup"><span data-stu-id="da3a7-108">Following is the basic syntax that is described in [FOR Clause (Transact-SQL)](/sql/t-sql/queries/select-for-clause-transact-sql):</span></span>  
  
```  
[ FOR { BROWSE | <XML> } ]  
<XML> ::=  
XML   
    {   
      { RAW [ ('ElementName') ] | AUTO }   
        [   
           <CommonDirectives>   
           [ , { XMLDATA | XMLSCHEMA [ ('TargetNameSpaceURI') ]} ]   
           [ , ELEMENTS [ XSINIL | ABSENT ]   
        ]  
      | EXPLICIT   
        [   
           <CommonDirectives>   
           [ , XMLDATA ]   
        ]  
      | PATH [ ('ElementName') ]   
        [   
           <CommonDirectives>   
           [ , ELEMENTS [ XSINIL | ABSENT ] ]  
        ]  
     }   
  
 <CommonDirectives> ::=   
   [ , BINARY BASE64 ]  
   [ , TYPE ]  
   [ , ROOT [ ('RootName') ] ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="da3a7-109">Arguments</span><span class="sxs-lookup"><span data-stu-id="da3a7-109">Arguments</span></span>  
 <span data-ttu-id="da3a7-110">RAW[('*ElementName*)]</span><span class="sxs-lookup"><span data-stu-id="da3a7-110">RAW[('*ElementName*')]</span></span>  
 <span data-ttu-id="da3a7-111">Prend le résultat de la requête et transforme chaque ligne du jeu de résultats en un élément XML comportant un identificateur générique \<row />, comme balise d’élément.</span><span class="sxs-lookup"><span data-stu-id="da3a7-111">Takes the query result and transforms each row in the result set into an XML element that has a generic identifier, \<row />, as the element tag.</span></span> <span data-ttu-id="da3a7-112">Vous pouvez, si vous le souhaitez, spécifier un nom pour l'élément de ligne en cas d'utilisation de cette directive.</span><span class="sxs-lookup"><span data-stu-id="da3a7-112">You can optionally specify a name for the row element when you use this directive.</span></span> <span data-ttu-id="da3a7-113">Le code XML qui en résulte utilise l’ *ElementName* spécifié pour identifier l’élément de ligne généré pour chaque ligne.</span><span class="sxs-lookup"><span data-stu-id="da3a7-113">The resulting XML will use the specified *ElementName* as the row element generated for each row.</span></span> <span data-ttu-id="da3a7-114">Pour plus d’informations, consultez [Utiliser le mode RAW avec FOR XML](use-raw-mode-with-for-xml.md).</span><span class="sxs-lookup"><span data-stu-id="da3a7-114">For more information, see [Use RAW Mode with FOR XML](use-raw-mode-with-for-xml.md).</span></span>  
  
 <span data-ttu-id="da3a7-115">AUTO</span><span class="sxs-lookup"><span data-stu-id="da3a7-115">AUTO</span></span>  
 <span data-ttu-id="da3a7-116">Renvoie les résultats de la requête dans une arborescence XML simple et imbriquée.</span><span class="sxs-lookup"><span data-stu-id="da3a7-116">Returns query results in a simple, nested XML tree.</span></span> <span data-ttu-id="da3a7-117">Chaque table dans la clause FROM pour laquelle au moins une colonne existe dans la clause SELECT est représentée comme un élément XML.</span><span class="sxs-lookup"><span data-stu-id="da3a7-117">Each table in the FROM clause for which at least one column is listed in the SELECT clause is represented as an XML element.</span></span> <span data-ttu-id="da3a7-118">Les colonnes listées dans la clause SELECT sont mappées vers les attributs d'éléments appropriés.</span><span class="sxs-lookup"><span data-stu-id="da3a7-118">The columns listed in the SELECT clause are mapped to the appropriate element attributes.</span></span> <span data-ttu-id="da3a7-119">Pour plus d’informations, consultez [Utiliser le mode AUTO avec FOR XML](use-auto-mode-with-for-xml.md).</span><span class="sxs-lookup"><span data-stu-id="da3a7-119">For more information, see [Use AUTO Mode with FOR XML](use-auto-mode-with-for-xml.md).</span></span>  
  
 <span data-ttu-id="da3a7-120">EXPLICIT</span><span class="sxs-lookup"><span data-stu-id="da3a7-120">EXPLICIT</span></span>  
 <span data-ttu-id="da3a7-121">Spécifie que la forme de l'arborescence XML résultante est définie de manière explicite.</span><span class="sxs-lookup"><span data-stu-id="da3a7-121">Specifies that the shape of the resulting XML tree is defined explicitly.</span></span> <span data-ttu-id="da3a7-122">Dans ce mode, les requêtes doivent être écrites d'une manière particulière afin que des informations complémentaires sur l'imbrication souhaitée soient spécifiées de manière explicite.</span><span class="sxs-lookup"><span data-stu-id="da3a7-122">By using this mode, queries must be written in a particular way so additional information about the nesting you want is specified explicitly.</span></span> <span data-ttu-id="da3a7-123">Pour plus d’informations, consultez [Utiliser le mode EXPLICIT avec FOR XML](use-explicit-mode-with-for-xml.md).</span><span class="sxs-lookup"><span data-stu-id="da3a7-123">For more information, see [Use EXPLICIT Mode with FOR XML](use-explicit-mode-with-for-xml.md).</span></span>  
  
 <span data-ttu-id="da3a7-124">PATH</span><span class="sxs-lookup"><span data-stu-id="da3a7-124">PATH</span></span>  
 <span data-ttu-id="da3a7-125">Constitue un moyen simple de mélanger les éléments et les attributs, et d'introduire des imbrications supplémentaires pour représenter des propriétés complexes.</span><span class="sxs-lookup"><span data-stu-id="da3a7-125">Provides a simpler way to mix elements and attributes, and to introduce additional nesting for representing complex properties.</span></span> <span data-ttu-id="da3a7-126">Vous pouvez utiliser des requêtes FOR XML en mode EXPLICIT pour construire cette sorte de XML à partir d'un ensemble de lignes, mais le mode PATH est une alternative plus simple aux requêtes en mode EXPLICIT souvent beaucoup plus lourdes à manier.</span><span class="sxs-lookup"><span data-stu-id="da3a7-126">You can use FOR XML EXPLICIT mode queries to construct this kind of XML from a rowset, but the PATH mode provides a simpler alternative to the possibly cumbersome EXPLICIT mode queries.</span></span> <span data-ttu-id="da3a7-127">Le mode PATH, allié à la possibilité d’écrire des requêtes FOR XML imbriquées et de faire appel à la directive TYPE pour renvoyer les instances de type **xml** , vous permet d’écrire des requêtes de moindre complexité.</span><span class="sxs-lookup"><span data-stu-id="da3a7-127">PATH mode, together with the ability to write nested FOR XML queries and the TYPE directive to return **xml** type instances, allows you to write queries with less complexity.</span></span> <span data-ttu-id="da3a7-128">Il offre une alternative à l'écriture de la plupart des requêtes en mode EXPLICIT.</span><span class="sxs-lookup"><span data-stu-id="da3a7-128">It provides an alternative to writing most EXPLICIT mode queries.</span></span> <span data-ttu-id="da3a7-129">Par défaut, le mode PATH génère un wrapper d’élément \<row> pour chaque ligne du jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="da3a7-129">By default, PATH mode generates a \<row> element wrapper for each row in the result set.</span></span> <span data-ttu-id="da3a7-130">Vous pouvez, si vous le souhaitez, spécifier un nom d'élément.</span><span class="sxs-lookup"><span data-stu-id="da3a7-130">You can optionally specify an element name.</span></span> <span data-ttu-id="da3a7-131">Si telle est votre intention, le nom spécifié est utilisé comme nom d'élément du wrapper.</span><span class="sxs-lookup"><span data-stu-id="da3a7-131">If you do, the specified name is used as the wrapper element name.</span></span> <span data-ttu-id="da3a7-132">Si vous fournissez une chaîne vide (FOR XML PATH ('')), aucun élément wrapper n'est généré.</span><span class="sxs-lookup"><span data-stu-id="da3a7-132">If you provide an empty string (FOR XML PATH ('')), no wrapper element is generated.</span></span> <span data-ttu-id="da3a7-133">Pour plus d’informations, consultez [Utiliser le mode PATH avec FOR XML](use-path-mode-with-for-xml.md).</span><span class="sxs-lookup"><span data-stu-id="da3a7-133">For more information, see [Use PATH Mode with FOR XML](use-path-mode-with-for-xml.md).</span></span>  
  
 <span data-ttu-id="da3a7-134">XMLDATA</span><span class="sxs-lookup"><span data-stu-id="da3a7-134">XMLDATA</span></span>  
 <span data-ttu-id="da3a7-135">Indique qu'un schéma XDR (XML-Data Reduced) doit être renvoyé.</span><span class="sxs-lookup"><span data-stu-id="da3a7-135">Specifies that an inline XML-Data Reduced (XDR) schema should be returned.</span></span> <span data-ttu-id="da3a7-136">Le schéma est ajouté au début du document sous la forme d'un schéma en ligne.</span><span class="sxs-lookup"><span data-stu-id="da3a7-136">The schema is prepended to the document as an inline schema.</span></span> <span data-ttu-id="da3a7-137">Pour obtenir un exemple fonctionnel, consultez [Utiliser le mode RAW avec FOR XML](use-raw-mode-with-for-xml.md).</span><span class="sxs-lookup"><span data-stu-id="da3a7-137">For a working sample, see [Use RAW Mode with FOR XML](use-raw-mode-with-for-xml.md).</span></span>  
  
 <span data-ttu-id="da3a7-138">XMLSCHEMA</span><span class="sxs-lookup"><span data-stu-id="da3a7-138">XMLSCHEMA</span></span>  
 <span data-ttu-id="da3a7-139">Renvoie un schéma XML W3C (XSD) en ligne.</span><span class="sxs-lookup"><span data-stu-id="da3a7-139">Returns an inline W3C XML Schema (XSD).</span></span> <span data-ttu-id="da3a7-140">Vous pouvez, si vous le souhaitez, spécifier un URI d'espace de noms cible en cas d'utilisation de cette directive</span><span class="sxs-lookup"><span data-stu-id="da3a7-140">You can optionally specify a target namespace URI when specifying this directive.</span></span> <span data-ttu-id="da3a7-141">de façon à ce que l'espace de noms spécifié soit renvoyé dans le schéma.</span><span class="sxs-lookup"><span data-stu-id="da3a7-141">This returns the specified namespace in the schema.</span></span> <span data-ttu-id="da3a7-142">Pour plus d’informations, consultez [Générer un schéma XSD Inline](generate-an-inline-xsd-schema.md).</span><span class="sxs-lookup"><span data-stu-id="da3a7-142">For more information, see [Generate an Inline XSD Schema](generate-an-inline-xsd-schema.md).</span></span> <span data-ttu-id="da3a7-143">Pour obtenir un exemple fonctionnel, consultez [Utiliser le mode RAW avec FOR XML](use-raw-mode-with-for-xml.md).</span><span class="sxs-lookup"><span data-stu-id="da3a7-143">For a working sample, see [Use RAW Mode with FOR XML](use-raw-mode-with-for-xml.md).</span></span>  
  
 <span data-ttu-id="da3a7-144">ELEMENTS</span><span class="sxs-lookup"><span data-stu-id="da3a7-144">ELEMENTS</span></span>  
 <span data-ttu-id="da3a7-145">Si l'option ELEMENTS est spécifiée, les colonnes sont renvoyées sous forme de sous-éléments.</span><span class="sxs-lookup"><span data-stu-id="da3a7-145">If the ELEMENTS option is specified, the columns are returned as subelements.</span></span> <span data-ttu-id="da3a7-146">Sinon, elles sont mappées avec des attributs XML.</span><span class="sxs-lookup"><span data-stu-id="da3a7-146">Otherwise, they are mapped to XML attributes.</span></span> <span data-ttu-id="da3a7-147">Cette option n'est prise en charge que dans les modes RAW, AUTO et PATH.</span><span class="sxs-lookup"><span data-stu-id="da3a7-147">This option is supported in RAW, AUTO, and PATH modes only.</span></span> <span data-ttu-id="da3a7-148">Vous pouvez, si vous le souhaitez, spécifier XSINIL ou ABSENT en cas d'utilisation de cette directive.</span><span class="sxs-lookup"><span data-stu-id="da3a7-148">You can optionally specify XSINIL or ABSENT when you use this directive.</span></span> <span data-ttu-id="da3a7-149">XSINIL spécifie qu’un élément qui a un attribut **xsi:nil** défini avec la valeur True soit créé pour les valeurs de colonne NULL.</span><span class="sxs-lookup"><span data-stu-id="da3a7-149">XSINIL specifies that an element that has an **xsi:nil** attribute set to True be created for NULL column values.</span></span> <span data-ttu-id="da3a7-150">Par défaut, ou lorsque ABSENT est spécifié avec ELEMENTS, aucun élément n'est créé pour des valeurs NULL.</span><span class="sxs-lookup"><span data-stu-id="da3a7-150">By default or when ABSENT is specified together with ELEMENTS, no elements are created for NULL values.</span></span> <span data-ttu-id="da3a7-151">Pour obtenir un exemple fonctionnel, consultez [Utiliser le mode RAW avec FOR XML](use-raw-mode-with-for-xml.md) et [Utiliser le mode AUTO avec FOR XML](use-auto-mode-with-for-xml.md).</span><span class="sxs-lookup"><span data-stu-id="da3a7-151">For a working sample, see [Use RAW Mode with FOR XML](use-raw-mode-with-for-xml.md) and [Use AUTO Mode with FOR XML](use-auto-mode-with-for-xml.md).</span></span>  
  
 <span data-ttu-id="da3a7-152">BINARY BASE64</span><span class="sxs-lookup"><span data-stu-id="da3a7-152">BINARY BASE64</span></span>  
 <span data-ttu-id="da3a7-153">Si l'option BINARY Base64 est spécifiée, toutes les données binaires renvoyées par la requête sont représentées dans un format encodé en base 64.</span><span class="sxs-lookup"><span data-stu-id="da3a7-153">If the BINARY Base64 option is specified, any binary data returned by the query is represented in base64-encoded format.</span></span> <span data-ttu-id="da3a7-154">Cette option doit être spécifiée pour l'extraction de données binaires en mode RAW et EXPLICIT.</span><span class="sxs-lookup"><span data-stu-id="da3a7-154">To retrieve binary data by using RAW and EXPLICIT mode, this option must be specified.</span></span> <span data-ttu-id="da3a7-155">En mode AUTO, des données binaires sont renvoyées comme une référence par défaut.</span><span class="sxs-lookup"><span data-stu-id="da3a7-155">In AUTO mode, binary data is returned as a reference by default.</span></span> <span data-ttu-id="da3a7-156">Pour obtenir un exemple fonctionnel, consultez [Utiliser le mode RAW avec FOR XML](use-raw-mode-with-for-xml.md).</span><span class="sxs-lookup"><span data-stu-id="da3a7-156">For a working sample, see [Use RAW Mode with FOR XML](use-raw-mode-with-for-xml.md).</span></span>  
  
 <span data-ttu-id="da3a7-157">TYPE</span><span class="sxs-lookup"><span data-stu-id="da3a7-157">TYPE</span></span>  
 <span data-ttu-id="da3a7-158">Spécifie que la requête retourne des résultats de type **xml** .</span><span class="sxs-lookup"><span data-stu-id="da3a7-158">Specifies that the query returns the results as the **xml** type.</span></span> <span data-ttu-id="da3a7-159">Pour plus d’informations, consultez [Directive TYPE dans les requêtes FOR XML](type-directive-in-for-xml-queries.md).</span><span class="sxs-lookup"><span data-stu-id="da3a7-159">For more information, see [TYPE Directive in FOR XML Queries](type-directive-in-for-xml-queries.md).</span></span>  
  
 <span data-ttu-id="da3a7-160">ROOT [('*RootName*')]</span><span class="sxs-lookup"><span data-stu-id="da3a7-160">ROOT [('*RootName*')]</span></span>  
 <span data-ttu-id="da3a7-161">Spécifie qu'un et un seul élément de premier niveau doit être ajouté au code XML résultant.</span><span class="sxs-lookup"><span data-stu-id="da3a7-161">Specifies that a single, top-level element be added to the resulting XML.</span></span> <span data-ttu-id="da3a7-162">Vous pouvez, si vous le souhaitez, spécifier le nom d'élément racine à générer.</span><span class="sxs-lookup"><span data-stu-id="da3a7-162">You can optionally specify the root element name to generate.</span></span> <span data-ttu-id="da3a7-163">La valeur par défaut est « root ».</span><span class="sxs-lookup"><span data-stu-id="da3a7-163">The default value is "root".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da3a7-164">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="da3a7-164">See Also</span></span>  
 <span data-ttu-id="da3a7-165">[Utiliser le mode RAW avec FOR XML](use-raw-mode-with-for-xml.md) </span><span class="sxs-lookup"><span data-stu-id="da3a7-165">[Use RAW Mode with FOR XML](use-raw-mode-with-for-xml.md) </span></span>  
 <span data-ttu-id="da3a7-166">[UTiliser le mode AUTO avec FOR XML](use-auto-mode-with-for-xml.md) </span><span class="sxs-lookup"><span data-stu-id="da3a7-166">[Use AUTO Mode with FOR XML](use-auto-mode-with-for-xml.md) </span></span>  
 <span data-ttu-id="da3a7-167">[Utiliser le mode EXPLICIT avec FOR XML](use-explicit-mode-with-for-xml.md) </span><span class="sxs-lookup"><span data-stu-id="da3a7-167">[Use EXPLICIT Mode with FOR XML](use-explicit-mode-with-for-xml.md) </span></span>  
 <span data-ttu-id="da3a7-168">[Utiliser le mode PATH avec FOR XML](use-path-mode-with-for-xml.md) </span><span class="sxs-lookup"><span data-stu-id="da3a7-168">[Use PATH Mode with FOR XML](use-path-mode-with-for-xml.md) </span></span>  
 <span data-ttu-id="da3a7-169">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="da3a7-169">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span></span>  
 [<span data-ttu-id="da3a7-170">FOR XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="da3a7-170">FOR XML &#40;SQL Server&#41;</span></span>](for-xml-sql-server.md)  
  
  
