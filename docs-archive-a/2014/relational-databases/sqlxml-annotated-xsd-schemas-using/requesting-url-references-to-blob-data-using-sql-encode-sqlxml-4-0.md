---
title: 'Demande de références URL à des données BLOB à l’aide de SQL : encode (SQLXML 4,0) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- sql:encode
- encode annotation
- URL references to BLOB data [SQLXML]
- references to BLOB data [SQLXML]
- annotated XSD schemas, URL references to BLOB data
- requesting URL references to BLOB data
- BLOBs, URL references
- Base 64-encoded format
ms.assetid: 2f8cd93b-c636-462b-8291-167197233ee0
author: rothja
ms.author: jroth
ms.openlocfilehash: 8a9f5edcfab4a9d7307327d97bc2099c78c666c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613381"
---
# <a name="requesting-url-references-to-blob-data-using-sqlencode-sqlxml-40"></a><span data-ttu-id="ba4c1-102">Demande de références URL à des données BLOB à l'aide de sql:encode (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="ba4c1-102">Requesting URL References to BLOB Data Using sql:encode (SQLXML 4.0)</span></span>
  <span data-ttu-id="ba4c1-103">Dans un schéma XSD annoté, lorsqu'un attribut (ou élément) est mappé à une colonne BLOB dans Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], les données sont retournées au format encodé en base 64 dans XML.</span><span class="sxs-lookup"><span data-stu-id="ba4c1-103">In an annotated XSD schema, when an attribute (or element) is mapped to a BLOB column in Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the data is returned in Base 64-encoded format within XML.</span></span>  
  
 <span data-ttu-id="ba4c1-104">Si vous souhaitez retourner une référence aux données (un URI) qui pourra être utilisée ultérieurement pour récupérer les données BLOB dans un format binaire, spécifiez l'annotation `sql:encode`.</span><span class="sxs-lookup"><span data-stu-id="ba4c1-104">If you want a reference to the data (a URI) to be returned that can be used later to retrieve the BLOB data in a binary format, specify the `sql:encode` annotation.</span></span> <span data-ttu-id="ba4c1-105">Vous pouvez spécifier `sql:encode` sur un attribut ou un élément de type simple.</span><span class="sxs-lookup"><span data-stu-id="ba4c1-105">You can specify `sql:encode` on an attribute or element of simple type.</span></span>  
  
 <span data-ttu-id="ba4c1-106">Spécifiez l'annotation `sql:encode` pour indiquer qu'une URL au champ doit être retournée au lieu de la valeur du champ.</span><span class="sxs-lookup"><span data-stu-id="ba4c1-106">Specify the `sql:encode` annotation to indicate that a URL to the field should be returned instead of the value of the field.</span></span> <span data-ttu-id="ba4c1-107">`sql:encode` dépend de la clé primaire pour générer une sélection singleton dans l'URL.</span><span class="sxs-lookup"><span data-stu-id="ba4c1-107">`sql:encode` depends on the primary key to generate a singleton select in the URL.</span></span> <span data-ttu-id="ba4c1-108">La clé primaire peut être spécifiée à l’aide de l' `sql:key-fields` annotation.</span><span class="sxs-lookup"><span data-stu-id="ba4c1-108">The primary key can be specified using the `sql:key-fields` annotation.</span></span>  
  
 <span data-ttu-id="ba4c1-109">La valeur « url » ou « default » peut être attribuée à l'annotation `sql:encode`.</span><span class="sxs-lookup"><span data-stu-id="ba4c1-109">The `sql:encode` annotation can be assigned the "url" or the "default" value.</span></span> <span data-ttu-id="ba4c1-110">Une valeur « default » retourne des données au format encodé en base 64.</span><span class="sxs-lookup"><span data-stu-id="ba4c1-110">A value of "default" returns data in Base 64-encoded format.</span></span>  
  
 <span data-ttu-id="ba4c1-111">L'annotation `sql:encode` ne peut pas être utilisée avec `sql:use-cdata` ou sur les types d'attributs ID, IDREF, IDREFS, NMTOKEN ou NMTOKENS.</span><span class="sxs-lookup"><span data-stu-id="ba4c1-111">The `sql:encode` annotation cannot be used with `sql:use-cdata` or on the ID, IDREF, IDREFS, NMTOKEN, or NMTOKENS attribute types.</span></span> <span data-ttu-id="ba4c1-112">Elle ne peut pas non plus être utilisée avec l’attribut **fixed** XSD.</span><span class="sxs-lookup"><span data-stu-id="ba4c1-112">It can also not be used with XSD **fixed** attribute.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ba4c1-113">Les colonnes de type BLOB ne peuvent pas être utilisées en tant que partie d'une clé ou d'une clé étrangère.</span><span class="sxs-lookup"><span data-stu-id="ba4c1-113">BLOB-type columns cannot be used as a part of a key or foreign key.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="ba4c1-114">Exemples</span><span class="sxs-lookup"><span data-stu-id="ba4c1-114">Examples</span></span>  
 <span data-ttu-id="ba4c1-115">Pour créer des exemples fonctionnels à l'aide des exemples suivants, vous devez répondre à certaines conditions requises.</span><span class="sxs-lookup"><span data-stu-id="ba4c1-115">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="ba4c1-116">Pour plus d’informations, consultez [Configuration requise pour l’exécution d’exemples SQLXML](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="ba4c1-116">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-sqlencode-to-obtain-a-url-reference-to-blob-data"></a><span data-ttu-id="ba4c1-117">R.</span><span class="sxs-lookup"><span data-stu-id="ba4c1-117">A.</span></span> <span data-ttu-id="ba4c1-118">Spécification de sql:encode pour obtenir une référence URL à des données BLOB</span><span class="sxs-lookup"><span data-stu-id="ba4c1-118">Specifying sql:encode to obtain a URL reference to BLOB data</span></span>  
 <span data-ttu-id="ba4c1-119">Dans cet exemple, le schéma de mappage spécifie `sql:encode` sur l’attribut **LargePhoto** pour récupérer la référence URI à une photo de produit spécifique (au lieu de récupérer les données binaires dans un format encodé en base 64).</span><span class="sxs-lookup"><span data-stu-id="ba4c1-119">In this example, the mapping schema specifies `sql:encode` on the **LargePhoto** attribute to retrieve the URI reference to a specific product photo (instead of retrieving the binary data in Base 64-encoded format).</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  
  <xsd:element name="ProductPhoto" sql:relation="Production.ProductPhoto"   
               sql:key-fields="ProductPhotoID" >  
   <xsd:complexType>  
      <xsd:attribute name="ProductPhotoID"  type="xsd:int"  />  
     <xsd:attribute name="LargePhoto" type="xsd:string" sql:encode="url" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="ba4c1-120">Pour tester un exemple de requête XPath sur le schéma</span><span class="sxs-lookup"><span data-stu-id="ba4c1-120">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="ba4c1-121">Copiez le code de schéma ci-dessus et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="ba4c1-121">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="ba4c1-122">Enregistrez le fichier en tant que sqlEncode.xml.</span><span class="sxs-lookup"><span data-stu-id="ba4c1-122">Save the file as sqlEncode.xml.</span></span>  
  
2.  <span data-ttu-id="ba4c1-123">Copiez le modèle suivant et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="ba4c1-123">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="ba4c1-124">Enregistrez le fichier sous le nom sqlEncodeT.xml dans le même répertoire où vous avez enregistré sqlEncode.xml.</span><span class="sxs-lookup"><span data-stu-id="ba4c1-124">Save the file as sqlEncodeT.xml in the same directory where you saved sqlEncode.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="sqlEncode.xml">  
            /ProductPhoto[@ProductPhotoID=100]  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="ba4c1-125">Le chemin d'accès au répertoire spécifié pour le schéma de mappage (sqlEncode.xml) est relatif au répertoire où le modèle est enregistré.</span><span class="sxs-lookup"><span data-stu-id="ba4c1-125">The directory path specified for the mapping schema (sqlEncode.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="ba4c1-126">Vous pouvez également spécifier un chemin d'accès absolu, par exemple :</span><span class="sxs-lookup"><span data-stu-id="ba4c1-126">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\sqlEncode.xml"  
    ```  
  
3.  <span data-ttu-id="ba4c1-127">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le modèle.</span><span class="sxs-lookup"><span data-stu-id="ba4c1-127">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="ba4c1-128">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML 4,0](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="ba4c1-128">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="ba4c1-129">Voici le résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="ba4c1-129">This is the result:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
   <ProductPhoto ProductPhotoID="100"  
                 LargePhoto="dbobject/Production.ProductPhoto[@ProductPhotoID="100"]/@LargePhoto" />   
</ROOT>  
```  
  
  
