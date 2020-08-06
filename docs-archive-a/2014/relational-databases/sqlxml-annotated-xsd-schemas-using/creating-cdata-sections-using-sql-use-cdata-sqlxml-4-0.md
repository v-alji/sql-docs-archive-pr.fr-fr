---
title: 'Création de sections CDATA à l’aide de SQL : use-cdata (SQLXML 4,0) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- markup characters [SQLXML]
- special characters [SQLXML]
- use-cdata annotation
- plain text [SQLXML]
- CDATA sections
- escaping blocks of text [SQLXML]
- annotated XSD schemas, CDATA sections
- sql:use-cdata
ms.assetid: 26d2b9dc-f857-44ff-bcd4-aaf64ff809d0
author: rothja
ms.author: jroth
ms.openlocfilehash: c0ba0787efbda400590a75f0f3529e3df8819e41
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613389"
---
# <a name="creating-cdata-sections-using-sqluse-cdata-sqlxml-40"></a><span data-ttu-id="085f5-102">Création de sections CDATA à l'aide de sql:use-cdata (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="085f5-102">Creating CDATA Sections Using sql:use-cdata (SQLXML 4.0)</span></span>
  <span data-ttu-id="085f5-103">En XML, les sections CDATA sont utilisées pour l'échappement des blocs de texte qui contiennent des caractères qui seraient reconnus comme caractères de balisage dans un autre contexte.</span><span class="sxs-lookup"><span data-stu-id="085f5-103">In XML, CDATA sections are used to escape blocks of text that contain characters that would otherwise be recognized as markup characters.</span></span>  
  
 <span data-ttu-id="085f5-104">Une base de données dans Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] peut parfois contenir des caractères qui sont traités comme des caractères de balisage par l’analyseur XML. par exemple, les crochets pointus ( \< and > ), le symbole « inférieur à » ou « égal à » (<=) et les esperluette (&) sont traités comme des caractères de balisage.</span><span class="sxs-lookup"><span data-stu-id="085f5-104">A database in Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can sometimes contain characters that are treated as markup characters by the XML parser; for example, angle brackets (\< and >), the less-than-or-equal-to symbol (<=), and the ampersand (&) are treated as markup characters.</span></span> <span data-ttu-id="085f5-105">Toutefois, vous pouvez encapsuler ce type de caractères spéciaux dans une section CDATA afin de les empêcher d'être traités comme des caractères de balisage.</span><span class="sxs-lookup"><span data-stu-id="085f5-105">However, you can wrap this type of special characters in a CDATA section to prevent them from being treated as markup characters.</span></span> <span data-ttu-id="085f5-106">Le texte dans la section CDATA est traité par l'analyseur XML comme du texte brut.</span><span class="sxs-lookup"><span data-stu-id="085f5-106">The text within the CDATA section is treated by the XML parser as plain text.</span></span>  
  
 <span data-ttu-id="085f5-107">L'annotation `sql:use-cdata` est utilisée pour spécifier que les données retournées par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] doivent être encapsulées dans une section CDATA (autrement dit, elle indique si la valeur d'une colonne spécifiée par `sql:field` doit être placée dans une section CDATA).</span><span class="sxs-lookup"><span data-stu-id="085f5-107">The `sql:use-cdata` annotation is used to specify that the data returned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] should be wrapped in a CDATA section (that is, it indicates whether the value from a column that is specified by `sql:field` should be enclosed in a CDATA section).</span></span> <span data-ttu-id="085f5-108">L'annotation `sql:use-cdata` peut être spécifiée uniquement sur des éléments qui mappent à une colonne de base de données.</span><span class="sxs-lookup"><span data-stu-id="085f5-108">The `sql:use-cdata` annotation can be specified only on elements that map to a database column.</span></span>  
  
 <span data-ttu-id="085f5-109">L'annotation `sql:use-cdata` prend une valeur booléenne (0 = faux, 1 = vrai).</span><span class="sxs-lookup"><span data-stu-id="085f5-109">The `sql:use-cdata` annotation takes a Boolean value (0 = false, 1 = true).</span></span> <span data-ttu-id="085f5-110">Les valeurs acceptables sont 0, 1, true et false.</span><span class="sxs-lookup"><span data-stu-id="085f5-110">The acceptable values are 0, 1, true, and false.</span></span>  
  
 <span data-ttu-id="085f5-111">Cette annotation ne peut pas être utilisée avec `sql:url-encode`, ni sur les types d'attributs ID, IDREF, IDREFS, NMTOKEN et NMTOKENS.</span><span class="sxs-lookup"><span data-stu-id="085f5-111">This annotation cannot be used with `sql:url-encode` or on the ID, IDREF, IDREFS, NMTOKEN, and NMTOKENS attribute types.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="085f5-112">Exemples</span><span class="sxs-lookup"><span data-stu-id="085f5-112">Examples</span></span>  
 <span data-ttu-id="085f5-113">Pour créer des exemples fonctionnels à l'aide des exemples suivants, vous devez répondre à certaines conditions requises.</span><span class="sxs-lookup"><span data-stu-id="085f5-113">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="085f5-114">Pour plus d’informations, consultez [Configuration requise pour l’exécution d’exemples SQLXML](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="085f5-114">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-sqluse-cdata-on-an-element"></a><span data-ttu-id="085f5-115">R.</span><span class="sxs-lookup"><span data-stu-id="085f5-115">A.</span></span> <span data-ttu-id="085f5-116">Spécification de sql:use-cdata sur un élément</span><span class="sxs-lookup"><span data-stu-id="085f5-116">Specifying sql:use-cdata on an element</span></span>  
 <span data-ttu-id="085f5-117">Dans le schéma suivant, `sql:use-cdata` a la valeur 1 (true) pour le **\<AddressLine1>** au sein de l' **\<Address>** élément.</span><span class="sxs-lookup"><span data-stu-id="085f5-117">In the following schema, `sql:use-cdata` is set to 1 (True) for the **\<AddressLine1>** within the **\<Address>** element.</span></span> <span data-ttu-id="085f5-118">En conséquence, les données sont retournées dans une section CDATA.</span><span class="sxs-lookup"><span data-stu-id="085f5-118">As a result, the data is returned in a CDATA section.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Address"   
               sql:relation="Person.Address"   
               sql:key-fields="AddressID" >  
   <xsd:complexType>  
        <xsd:sequence>  
          <xsd:element name="AddressID"  type="xsd:string" />  
          <xsd:element name="AddressLine1" type="xsd:string"   
                       sql:use-cdata="1" />  
        </xsd:sequence>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="085f5-119">Pour tester un exemple de requête XPath sur le schéma</span><span class="sxs-lookup"><span data-stu-id="085f5-119">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="085f5-120">Copiez le code de schéma ci-dessus et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="085f5-120">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="085f5-121">Enregistrez le fichier sous le nom UseCData.xml.</span><span class="sxs-lookup"><span data-stu-id="085f5-121">Save the file as UseCData.xml.</span></span>  
  
2.  <span data-ttu-id="085f5-122">Copiez le modèle suivant et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="085f5-122">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="085f5-123">Enregistrez le fichier sous le nom UseCDataT.xml dans le répertoire où vous avez enregistré le fichier UseCData.xml.</span><span class="sxs-lookup"><span data-stu-id="085f5-123">Save the file as UseCDataT.xml in the same directory where you saved UseCData.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="UseCData.xml">  
            /Address[AddressID < 11]  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="085f5-124">Le chemin d'accès au répertoire spécifié pour le schéma de mappage (UseCData.xml) est relatif au répertoire où le modèle est enregistré.</span><span class="sxs-lookup"><span data-stu-id="085f5-124">The directory path specified for the mapping schema (UseCData.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="085f5-125">Vous pouvez également spécifier un chemin d'accès absolu, par exemple :</span><span class="sxs-lookup"><span data-stu-id="085f5-125">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\UseCData.xml"  
    ```  
  
3.  <span data-ttu-id="085f5-126">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le modèle.</span><span class="sxs-lookup"><span data-stu-id="085f5-126">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="085f5-127">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML 4,0](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="085f5-127">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="085f5-128">Voici le jeu de résultats partiel :</span><span class="sxs-lookup"><span data-stu-id="085f5-128">This is the partial result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">   
  <Address>   
    <AddressID>1</CustomerID>   
    <AddressLine1>   
      <![CDATA[ 1970 Napa Ct.  ]]>   
    </AddressLine1>   
  </Address>  
  <Address>  
    <AddressLine1>   
      <![CDATA[ 9833 Mt. Dias Blv. ]]>   
    </AddressLine1>   
  </Address>  
  ...  
</ROOT>  
```  
  
  
