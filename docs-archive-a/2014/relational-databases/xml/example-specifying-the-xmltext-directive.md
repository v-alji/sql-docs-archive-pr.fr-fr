---
title: 'Exemple : Spécification de la directive XMLTEXT | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- XMLTEXT directive
ms.assetid: e78008ec-51e8-4fd1-b86f-1058a781de17
author: rothja
ms.author: jroth
ms.openlocfilehash: d14299ad3e989c6600434b857a650fbbddd7a590
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613341"
---
# <a name="example-specifying-the-xmltext-directive"></a><span data-ttu-id="f47d1-102">Exemple : Spécification de la directive XMLTEXT</span><span class="sxs-lookup"><span data-stu-id="f47d1-102">Example: Specifying the XMLTEXT Directive</span></span>
  <span data-ttu-id="f47d1-103">Cet exemple illustre l'adressage des informations contenues dans la colonne de dépassement de capacité à l'aide de la directive `XMLTEXT` dans une instruction `SELECT` utilisant le mode EXPLICIT.</span><span class="sxs-lookup"><span data-stu-id="f47d1-103">This example illustrates how data in the overflow column is addressed by using the `XMLTEXT` directive in a `SELECT` statement using EXPLICIT mode.</span></span>  
  
 <span data-ttu-id="f47d1-104">Soit la table `Person` .</span><span class="sxs-lookup"><span data-stu-id="f47d1-104">Consider the `Person` table.</span></span> <span data-ttu-id="f47d1-105">Cette table possède une colonne nommée `Overflow` , qui stocke les données non consommées du document XML.</span><span class="sxs-lookup"><span data-stu-id="f47d1-105">This table has an `Overflow` column that stores the unconsumed part of the XML document.</span></span>  
  
```  
USE tempdb;  
GO  
CREATE TABLE Person(PersonID varchar(5), PersonName varchar(20), Overflow nvarchar(200));  
GO  
INSERT INTO Person VALUES   
    ('P1','Joe',N'<SomeTag attr1="data">content</SomeTag>')  
   ,('P2','Joe',N'<SomeTag attr2="data"/>')  
   ,('P3','Joe',N'<SomeTag attr3="data" PersonID="P">content</SomeTag>');  
```  
  
 <span data-ttu-id="f47d1-106">La requête suivante extrait des colonnes de la table `Person` .</span><span class="sxs-lookup"><span data-stu-id="f47d1-106">This query retrieves columns from the `Person` table.</span></span> <span data-ttu-id="f47d1-107">Concernant la colonne `Overflow` , *AttributeName* n’est pas spécifié, mais *directive* a pour valeur `XMLTEXT` et fournit une composante du nom d’une colonne de la table universelle.</span><span class="sxs-lookup"><span data-stu-id="f47d1-107">For the `Overflow` column, *AttributeName* is not specified, but *directive* is set to `XMLTEXT` as part of providing a universal table column name.</span></span>  
  
```  
SELECT 1 as Tag, NULL as parent,  
       PersonID as [Parent!1!PersonID],  
       PersonName as [Parent!1!PersonName],  
       Overflow as [Parent!1!!XMLTEST] -- No AttributeName; XMLTEXT directive  
FROM Person  
FOR XML EXPLICIT;  
```  
  
 <span data-ttu-id="f47d1-108">Dans le document XML obtenu :</span><span class="sxs-lookup"><span data-stu-id="f47d1-108">In the resulting XML document:</span></span>  
  
-   <span data-ttu-id="f47d1-109">Comme *AttributeName* n’est pas spécifié pour la colonne `Overflow` et que la directive `xmltext` est spécifiée, les attributs de l’élément <`overflow`> sont ajoutés à la liste d’attributs de l’élément englobant <`Parent`>.</span><span class="sxs-lookup"><span data-stu-id="f47d1-109">Because *AttributeName* is not specified for the `Overflow` column and the `xmltext` directive is specified, the attributes in the <`overflow`> element are appended to the attribute list of the enclosing <`Parent`> element.</span></span>  
  
-   <span data-ttu-id="f47d1-110">En raison du conflit entre l’attribut `PersonID` de l’élément <`xmltext`> et l’attribut `PersonID` extrait du même niveau d’éléments, l’attribut de l’élément <`xmltext`> est ignoré, même si `PersonID` a la valeur NULL.</span><span class="sxs-lookup"><span data-stu-id="f47d1-110">Because the `PersonID`attribute in the <`xmltext`> element conflicts with the `PersonID` attribute retrieved on the same element level, the attribute in the <`xmltext`> element is ignored, even if `PersonID` is NULL.</span></span> <span data-ttu-id="f47d1-111">En général, un attribut remplace un attribut de même nom dans les données en excès.</span><span class="sxs-lookup"><span data-stu-id="f47d1-111">Generally, an attribute overrides an attribute of the same name in the overflow.</span></span>  
  
 <span data-ttu-id="f47d1-112">Voici le résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="f47d1-112">This is the result:</span></span>  
  
 `<Parent PersonID="P1" PersonName="Joe" attr1="data">content</Parent>`  
  
 `<Parent PersonID="P2" PersonName="Joe" attr2="data"></Parent>`  
  
 `<Parent PersonID="P3" PersonName="Joe" attr3="data">content</Parent>`  
  
 <span data-ttu-id="f47d1-113">Si les données en excès contiennent des sous-éléments et que la même requête est exécutée, les sous-éléments contenus dans la colonne `Overflow` sont ajoutés en tant que sous-éléments de l'élément englobant <`Parent`>.</span><span class="sxs-lookup"><span data-stu-id="f47d1-113">If the overflow data has subelements and the same query is specified, the subelements in the `Overflow` column are added as the subelements of the enclosing <`Parent`> element.</span></span>  
  
 <span data-ttu-id="f47d1-114">Supposons, par exemple, que les données de la table `Person` sont modifiées afin que la colonne `Overflow` contienne des sous-éléments.</span><span class="sxs-lookup"><span data-stu-id="f47d1-114">For example, change the data in the `Person` table so that the `Overflow` column now has subelements.</span></span>  
  
```  
USE tempdb;  
GO  
TRUNCATE TABLE Person;  
GO  
INSERT INTO Person VALUES   
    ('P1','Joe',N'<SomeTag attr1="data">content</SomeTag>')  
   ,('P2','Joe',N'<SomeTag attr2="data"/>')  
    ,('P3','Joe',N'<SomeTag attr3="data" PersonID="P"><name>PersonName</name></SomeTag>');  
```  
  
 <span data-ttu-id="f47d1-115">Si la même requête est exécutée, les sous-éléments de l'élément <`xmltext`> sont ajoutés en tant que sous-éléments de l'élément englobant <`Parent`> :</span><span class="sxs-lookup"><span data-stu-id="f47d1-115">If the same query is executed, the subelements in the <`xmltext`> element are added as subelements of the enclosing <`Parent`> element:</span></span>  
  
```  
SELECT 1 as Tag, NULL as parent,  
       PersonID as [Parent!1!PersonID],  
       PersonName as [Parent!1!PersonName],  
       Overflow as [Parent!1!!XMLTEXT] -- no AttributeName, XMLTEXT directive  
FROM Person  
FOR XML EXPLICIT;  
```  
  
 <span data-ttu-id="f47d1-116">Voici le résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="f47d1-116">This is the result:</span></span>  
  
 `<Parent PersonID="P1" PersonName="Joe" attr1="data">content</Parent>`  
  
 `<Parent PersonID="P2" PersonName="Joe" attr2="data"></Parent>`  
  
 `<Parent PersonID="P3" PersonName="Joe" attr3="data">`  
  
 `<name>PersonName</name>`  
  
 `</Parent>`  
  
 <span data-ttu-id="f47d1-117">Si *AttributeName* est spécifié avec la directive `xmltext`, les attributs de l’élément <`overflow`> sont ajoutés en tant qu’attributs des sous-éléments de l’élément englobant <`Parent`>.</span><span class="sxs-lookup"><span data-stu-id="f47d1-117">If *AttributeName* is specified with the `xmltext` directive, the attributes of the <`overflow`> element are added as attributes of the subelements of the enclosing <`Parent`> element.</span></span> <span data-ttu-id="f47d1-118">Le nom spécifié pour *AttributeName* devient le nom du sous-élément.</span><span class="sxs-lookup"><span data-stu-id="f47d1-118">The name specified for *AttributeName* becomes the name of the subelement.</span></span>  
  
 <span data-ttu-id="f47d1-119">Dans cette requête, *AttributeName*, <`overflow`>, est spécifié en même temps que la `xmltext` directive :</span><span class="sxs-lookup"><span data-stu-id="f47d1-119">In this query, *AttributeName*, <`overflow`>, is specified together with the `xmltext` directive:</span></span>  
  
```  
SELECT 1 as Tag, NULL as parent,  
       PersonID as [Parent!1!PersonID],  
       PersonName as [Parent!1!PersonName],  
       Overflow as [Parent!1!overflow!XMLTEXT] -- Overflow is AttributeName  
                      -- XMLTEXT is a directive  
FROM Person  
FOR XML EXPLICIT  
```  
  
 <span data-ttu-id="f47d1-120">Voici le résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="f47d1-120">This is the result:</span></span>  
  
 `<Parent PersonID="P1" PersonName="Joe">`  
  
 `<overflow attr1="data">content</overflow>`  
  
 `</Parent>`  
  
 `<Parent PersonID="P2" PersonName="Joe">`  
  
 `<overflow attr2="data" />`  
  
 `</Parent>`  
  
 `<Parent PersonID="P3" PersonName="Joe">`  
  
 `<overflow attr3="data" PersonID="P">`  
  
 `<name>PersonName</name>`  
  
 `</overflow>`  
  
 `</Parent>`  
  
 <span data-ttu-id="f47d1-121">Dans l’élément de requête suivant, l’argument *directive* est spécifié pour l’attribut `PersonName` .</span><span class="sxs-lookup"><span data-stu-id="f47d1-121">In this query element, *directive* is specified for `PersonName` attribute.</span></span> <span data-ttu-id="f47d1-122">Par conséquent, `PersonName` est ajouté en tant que sous-élément de l'élément englobant <`Parent`>.</span><span class="sxs-lookup"><span data-stu-id="f47d1-122">This results in `PersonName` being added as a subelement of the enclosing <`Parent`> element.</span></span> <span data-ttu-id="f47d1-123">Les attributs de <`xmltext`> sont néanmoins ajoutés à l'élément englobant <`Parent`>.</span><span class="sxs-lookup"><span data-stu-id="f47d1-123">The attributes of the <`xmltext`> are still appended to the enclosing <`Parent`> element.</span></span> <span data-ttu-id="f47d1-124">Le contenu de l'élément <`overflow`>, les sous-éléments, sont ajoutés avant les autres sous-éléments des éléments englobants <`Parent`>.</span><span class="sxs-lookup"><span data-stu-id="f47d1-124">The contents of the <`overflow`> element, subelements, are prepended to the other subelements of the enclosing <`Parent`> elements.</span></span>  
  
```  
SELECT 1      AS Tag, NULL as parent,  
       PersonID   AS [Parent!1!PersonID],  
       PersonName AS [Parent!1!PersonName!element], -- element directive  
       Overflow   AS [Parent!1!!XMLTEXT]  
FROM Person  
FOR XML EXPLICIT;  
```  
  
 <span data-ttu-id="f47d1-125">Voici le résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="f47d1-125">This is the result:</span></span>  
  
 `<Parent PersonID="P1" attr1="data">content<PersonName>Joe</PersonName>`  
  
 `</Parent>`  
  
 `<Parent PersonID="P2" attr2="data">`  
  
 `<PersonName>Joe</PersonName>`  
  
 `</Parent>`  
  
 `<Parent PersonID="P3" attr3="data">`  
  
 `<name>PersonName</name>`  
  
 `<PersonName>Joe</PersonName>`  
  
 `</Parent>`  
  
 <span data-ttu-id="f47d1-126">Si les données de la colonne `XMLTEXT` contiennent des attributs sur l'élément racine, ces attributs ne sont pas montrés dans le schéma de données XML et l'analyseur MSXML ne valide pas le fragment de document XML obtenu.</span><span class="sxs-lookup"><span data-stu-id="f47d1-126">If the `XMLTEXT` column data contains attributes on the root element, these attributes are not shown in the XML data schema and the MSXML parser does not validate the resulting XML document fragment.</span></span> <span data-ttu-id="f47d1-127">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="f47d1-127">For example:</span></span>  
  
```  
SELECT 1 AS Tag,  
       0 ASParent,  
       N'<overflow a="1"/>' AS 'overflow!1!!xmltext'  
FOR XML EXPLICIT, xmldata;  
```  
  
 <span data-ttu-id="f47d1-128">Voici l'ensemble de résultats.</span><span class="sxs-lookup"><span data-stu-id="f47d1-128">This is the result.</span></span> <span data-ttu-id="f47d1-129">Notez que l'attribut en excès `a` ne figure pas dans le schéma renvoyé :</span><span class="sxs-lookup"><span data-stu-id="f47d1-129">Note that in the returned schema, the overflow attribute `a` is missing from the schema:</span></span>  
  
 `<Schema name="Schema2"`  
  
 `xmlns="urn:schemas-microsoft-com:xml-data"`  
  
 `xmlns:dt="urn:schemas-microsoft-com:datatypes">`  
  
 `<ElementType name="overflow" content="mixed" model="open">`  
  
 `</ElementType>`  
  
 `</Schema>`  
  
 `<overflow xmlns="x-schema:#Schema2" a="1">`  
  
 `</overflow>`  
  
## <a name="see-also"></a><span data-ttu-id="f47d1-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f47d1-130">See Also</span></span>  
 [<span data-ttu-id="f47d1-131">Utiliser le mode EXPLICIT avec FOR XML</span><span class="sxs-lookup"><span data-stu-id="f47d1-131">Use EXPLICIT Mode with FOR XML</span></span>](use-explicit-mode-with-for-xml.md)  
  
  
