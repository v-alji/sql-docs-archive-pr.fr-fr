---
title: 'Récupération de données non consommées à l’aide de SQL : overflow-field (SQLXML 4,0) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- unconsumed data
- storing unconsumed data
- retrieving unconsumed data
- annotated XSD schemas, unconsumed data
- overflow data [SQLXML]
- sql:overflow-field
ms.assetid: 8526998d-b47d-4a32-8dc2-7f50a8d11097
author: rothja
ms.author: jroth
ms.openlocfilehash: 796fda9428954c5f18c5d37b353de9fd4122551e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613380"
---
# <a name="retrieving-unconsumed-data-using-the-sqloverflow-field-sqlxml-40"></a><span data-ttu-id="aca15-102">Extraction de données non consommées à l'aide de sql:overflow-field (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="aca15-102">Retrieving Unconsumed Data Using the sql:overflow-field (SQLXML 4.0)</span></span>
  <span data-ttu-id="aca15-103">Lorsque les enregistrements sont insérés dans une base de données à partir d'un document XML à l'aide de la fonction [!INCLUDE[tsql](../../includes/tsql-md.md)] OPENXML, toutes les données non consommées du document XML source peuvent être stockées dans une colonne.</span><span class="sxs-lookup"><span data-stu-id="aca15-103">When records are inserted in a database from an XML document by using the [!INCLUDE[tsql](../../includes/tsql-md.md)] OPENXML function, all the unconsumed data from the source XML document can be stored in a column.</span></span> <span data-ttu-id="aca15-104">Lors de la récupération des données à partir d'une base de données à l'aide des schémas annotés, l'attribut `sql:overflow-field` peut être spécifié pour identifier la colonne de la table où les données de dépassement de capacité sont stockées.</span><span class="sxs-lookup"><span data-stu-id="aca15-104">When you retrieve data from a database by using annotated schemas, you can specify the `sql:overflow-field` attribute to identify the column in the table in which the overflow data is stored.</span></span> <span data-ttu-id="aca15-105">L' `sql:overflow-field` attribut peut être spécifié sur **\<element>** .</span><span class="sxs-lookup"><span data-stu-id="aca15-105">The `sql:overflow-field` attribute can be specified on **\<element>**.</span></span>  
  
 <span data-ttu-id="aca15-106">Ces données sont alors récupérées selon les méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="aca15-106">This data is then retrieved in these ways:</span></span>  
  
-   <span data-ttu-id="aca15-107">Les attributs stockés dans la colonne de dépassement sont ajoutés à l'élément qui contient l'annotation `sql:overflow-field`.</span><span class="sxs-lookup"><span data-stu-id="aca15-107">Attributes stored in the overflow column are added to the element that contains the `sql:overflow-field` annotation.</span></span>  
  
-   <span data-ttu-id="aca15-108">Les éléments enfants et leurs descendants, stockés dans la colonne de dépassement de capacité de la base de données, sont ajoutés comme éléments enfants après le contenu spécifié explicitement dans le schéma.</span><span class="sxs-lookup"><span data-stu-id="aca15-108">The child elements and their descendents, stored in the overflow column in the database, are added as child elements following the content that is explicitly specified in the schema.</span></span> <span data-ttu-id="aca15-109">(Aucun ordre n'est conservé.)</span><span class="sxs-lookup"><span data-stu-id="aca15-109">(No order is preserved.)</span></span>  
  
## <a name="examples"></a><span data-ttu-id="aca15-110">Exemples</span><span class="sxs-lookup"><span data-stu-id="aca15-110">Examples</span></span>  
 <span data-ttu-id="aca15-111">Pour créer des exemples fonctionnels à l'aide des exemples suivants, vous devez répondre à certaines conditions requises.</span><span class="sxs-lookup"><span data-stu-id="aca15-111">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="aca15-112">Pour plus d’informations, consultez [Configuration requise pour l’exécution d’exemples SQLXML](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="aca15-112">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-sqloverflow-field-for-an-element"></a><span data-ttu-id="aca15-113">R.</span><span class="sxs-lookup"><span data-stu-id="aca15-113">A.</span></span> <span data-ttu-id="aca15-114">Spécification de sql:overflow-field pour un élément</span><span class="sxs-lookup"><span data-stu-id="aca15-114">Specifying sql:overflow-field for an element</span></span>  
 <span data-ttu-id="aca15-115">Cet exemple suppose que le script suivant a été exécuté afin qu'une table nommée Customers2 existe dans la base de données tempdb :</span><span class="sxs-lookup"><span data-stu-id="aca15-115">This example assumes that the following script has been run so that a table named Customers2 exists in the tempdb database:</span></span>  
  
```  
USE tempdb  
CREATE TABLE Customers2 (  
CustomerID       VARCHAR(10),   
ContactName    VARCHAR(30),   
AddressOverflow    NVARCHAR(500))  
  
GO  
INSERT INTO Customers2 VALUES (  
'ALFKI',   
'Joe',  
'<Address>  
  <Address1>Maple St.</Address1>  
  <Address2>Apt. E105</Address2>  
  <City>Seattle</City>  
  <State>WA</State>  
  <Zip>98147</Zip>  
 </Address>')  
GO  
```  
  
 <span data-ttu-id="aca15-116">En outre, vous devez créer un répertoire virtuel pour la base de données tempdb et un nom virtuel de modèle de `template` type nommé « template ».</span><span class="sxs-lookup"><span data-stu-id="aca15-116">In addition, you must create a virtual directory for the tempdb database-and a template virtual name of `template` type named "template".</span></span>  
  
 <span data-ttu-id="aca15-117">Dans l'exemple suivant, le schéma de mappage extrait les données non consommées stockées dans la colonne AddressOverflow de la table Customers2 :</span><span class="sxs-lookup"><span data-stu-id="aca15-117">In the following example, the mapping schema retrieves the unconsumed data that is stored in the AddressOverflow column of the Customers2 table:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  
  <xsd:element name="Customers2" sql:overflow-field="AddressOverflow" >  
    <xsd:complexType>  
      <xsd:attribute name="CustomerID"  type="xsd:integer"/>  
      <xsd:attribute name="ContactName"  type="xsd:string" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="aca15-118">Pour tester un exemple de requête XPath sur le schéma</span><span class="sxs-lookup"><span data-stu-id="aca15-118">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="aca15-119">Copiez le code de schéma ci-dessus et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="aca15-119">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="aca15-120">Enregistrez ce fichier sous le nom Overflow.xml.</span><span class="sxs-lookup"><span data-stu-id="aca15-120">Save the file as Overflow.xml.</span></span>  
  
2.  <span data-ttu-id="aca15-121">Copiez le modèle suivant et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="aca15-121">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="aca15-122">Enregistrez ce fichier sous le nom OverflowT.xml dans le répertoire où vous avez enregistré Overflow.xml.</span><span class="sxs-lookup"><span data-stu-id="aca15-122">Save the file as OverflowT.xml in the same directory where you saved Overflow.xml.</span></span> <span data-ttu-id="aca15-123">La requête du modèle sélectionne les enregistrements de la table Customers2.</span><span class="sxs-lookup"><span data-stu-id="aca15-123">The query in the template selects the records in the Customers2 table.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="Overflow.xml">  
            /Customers2  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="aca15-124">Le chemin d'accès au répertoire spécifié pour le schéma de mappage (Overflow.xml) est relatif au répertoire dans lequel le modèle est enregistré.</span><span class="sxs-lookup"><span data-stu-id="aca15-124">The directory path specified for the mapping schema (Overflow.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="aca15-125">Vous pouvez également spécifier un chemin d'accès absolu, par exemple :</span><span class="sxs-lookup"><span data-stu-id="aca15-125">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\Overflow.xml"  
    ```  
  
3.  <span data-ttu-id="aca15-126">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le modèle.</span><span class="sxs-lookup"><span data-stu-id="aca15-126">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="aca15-127">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML 4,0](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="aca15-127">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="aca15-128">Voici l'ensemble de résultats obtenu :</span><span class="sxs-lookup"><span data-stu-id="aca15-128">Here is the result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Customers2 CustomerID="ALFKI" ContactName="Joe">  
    <Address1>Maple St.</Address1>   
    <Address2>Apt. E105</Address2>   
    <City>Seattle</City>   
    <State>WA</State>   
    <Zip>98147</Zip>   
  </Customers2>  
</ROOT>  
```  
  
  
