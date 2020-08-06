---
title: Référencer la collection de schémas XML intégrée (sys) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- sys XML schema collections [SQL Server]
- schema collections [SQL Server], predefined
- predefined XML schema collections [SQL Server]
- XML schema collections [SQL Server], predefined
- built-in XML schema collections [SQL Server]
ms.assetid: 1e118303-5df0-4ee4-bd8d-14ced7544144
author: rothja
ms.author: jroth
ms.openlocfilehash: 7fa30107e1746b33e3f9b8eb1cfa53d1f4d25fb8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697603"
---
# <a name="reference-the-built-in-xml-schema-collection-sys"></a><span data-ttu-id="893c1-102">Référencer la collection de schémas XML intégrée (sys)</span><span class="sxs-lookup"><span data-stu-id="893c1-102">Reference the Built-in XML Schema Collection (sys)</span></span>
  <span data-ttu-id="893c1-103">Chaque base de données que vous créez a une collection de schémas XML **sys** prédéfinie dans le schéma relationnel **sys** .</span><span class="sxs-lookup"><span data-stu-id="893c1-103">Every database you create has a predefined **sys** XML schema collection in the **sys** relational schema.</span></span> <span data-ttu-id="893c1-104">Elle réserve ces schémas prédéfinis, qui sont accessibles à toute autre collection de schémas XML créés par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="893c1-104">It reserves these predefined schemas, and they can be accessed from any other user-created XML schema collection.</span></span> <span data-ttu-id="893c1-105">Les préfixes utilisés dans ces schémas prédéfinis ont une signification dans XQuery.</span><span class="sxs-lookup"><span data-stu-id="893c1-105">The prefixes used in these predefined schemas are meaningful in XQuery.</span></span> <span data-ttu-id="893c1-106">Seul **xml** est un préfixe réservé.</span><span class="sxs-lookup"><span data-stu-id="893c1-106">Only **xml** is a reserved prefix.</span></span>  
  
```  
xml = http://www.w3.org/XML/1998/namespace  
xs = http://www.w3.org/2001/XMLSchema  
xsi = http://www.w3.org/2001/XMLSchema-instance  
fn = http://www.w3.org/2004/07/xpath-functions  
sqltypes = https://schemas.microsoft.com/sqlserver/2004/sqltypes  
xdt = http://www.w3.org/2004/07/xpath-datatypes  
(no prefix) = urn:schemas-microsoft-com:xml-sql  
(no prefix) = https://schemas.microsoft.com/sqlserver/2004/SOAP  
```  
  
 <span data-ttu-id="893c1-107">Notez que l’espace de noms **sqltypes** contient des composants qui peuvent être référencés à partir de toute collection de schémas XML créée par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="893c1-107">Note that the **sqltypes** namespace contains components that can be referenced from any user-created XML schema collection.</span></span> <span data-ttu-id="893c1-108">Vous pouvez télécharger le schéma **sqltypes** à partir de ce [site web de Microsoft](https://go.microsoft.com/fwlink/?linkid=31850).</span><span class="sxs-lookup"><span data-stu-id="893c1-108">You can download the **sqltypes** schema from this [Microsoft Web site](https://go.microsoft.com/fwlink/?linkid=31850).</span></span> <span data-ttu-id="893c1-109">Les composants intégrés incluent les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="893c1-109">The built-in components include the following:</span></span>  
  
-   <span data-ttu-id="893c1-110">Types XSD</span><span class="sxs-lookup"><span data-stu-id="893c1-110">XSD types</span></span>  
  
-   <span data-ttu-id="893c1-111">Attributs XML **lang**, **base**et **space**</span><span class="sxs-lookup"><span data-stu-id="893c1-111">XML attributes **lang**, **base**, and **space**</span></span>  
  
-   <span data-ttu-id="893c1-112">Composants de l’espace de noms **sqltypes**</span><span class="sxs-lookup"><span data-stu-id="893c1-112">Components of the **sqltypes** namespace</span></span>  
  
 <span data-ttu-id="893c1-113">La requête ci-dessous retourne les composants intégrés qui peuvent être référencés à partir d'une collection de schémas XML créés par l'utilisateur :</span><span class="sxs-lookup"><span data-stu-id="893c1-113">The following query returns built-in components that can be referenced from a user-created XML schema collection:</span></span>  
  
```  
SELECT C.name, N.name, C.symbol_space_desc from sys.xml_schema_components C join sys.xml_schema_namespaces N  
on ((C.xml_namespace_id = N.xml_namespace_id) AND (C.xml_collection_id = N.xml_collection_id))  
join sys.xml_schema_collections SC  
on SC.xml_collection_id = C.xml_collection_id  
where ((C.xml_collection_id = 1) AND (C.name is not null) AND (C.scoping_xml_component_id is null)   
AND (SC.schema_id = 4))  
GO  
```  
  
 <span data-ttu-id="893c1-114">L'exemple suivant montre comment ces composants sont référencés dans un schéma utilisateur.</span><span class="sxs-lookup"><span data-stu-id="893c1-114">The following example shows how these components are referenced in a user schema.</span></span> <span data-ttu-id="893c1-115">`CREATE XML SCHEMA COLLECTION` crée une collection de schémas XML qui fait référence au type `varchar` défini dans l’espace de noms `sqltypes` .</span><span class="sxs-lookup"><span data-stu-id="893c1-115">`CREATE XML SCHEMA COLLECTION` creates an XML schema collection that references the `varchar` type defined in the `sqltypes` namespace.</span></span> <span data-ttu-id="893c1-116">L'exemple référence également l'attribut `lang` défini dans l'espace de noms `xml` .</span><span class="sxs-lookup"><span data-stu-id="893c1-116">The example also references the `lang` attribute that is defined in the `xml` namespace.</span></span>  
  
```  
CREATE XML SCHEMA COLLECTION SC AS '  
<schema   
   xmlns="http://www.w3.org/2001/XMLSchema"   
   targetNamespace="myNS"  
   xmlns:ns="myNS"  
   xmlns:s="https://schemas.microsoft.com/sqlserver/2004/sqltypes" >   
   <import namespace="http://www.w3.org/XML/1998/namespace"/>  
   <import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes"/>  
   <element name="root">  
      <complexType>  
          <sequence>  
             <element name="a" type="string"/>  
             <element name="b" type="string"/>  
             <!-- varchar type is defined in the sys.sys collection and   
                  can be referenced in any user-defined schema -->  
             <element name="c" type="s:varchar"/>  
          </sequence>  
          <attribute name="att" type="int"/>  
          <!-- xml:lang attribute is defined in the sys.sys collection   
               and can be referenced in any user-defined schema -->  
          <attribute ref="xml:lang"/>  
      </complexType>  
    </element>  
 </schema>'  
GO  
 -- Cleanup  
DROP xml schema collection SC   
GO  
```  
  
 <span data-ttu-id="893c1-117">Notez les points suivants :</span><span class="sxs-lookup"><span data-stu-id="893c1-117">You should note the following:</span></span>  
  
-   <span data-ttu-id="893c1-118">Vous ne pouvez pas modifier les schémas XML avec ces espaces de noms dans toutes les collections de schémas XML créés par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="893c1-118">You cannot modify XML schemas with these namespaces in any user-defined XML schema collection.</span></span> <span data-ttu-id="893c1-119">Par exemple, la collection de schémas XML ci-dessous échoue, car elle ajoute un composant dans l'espace de noms protégé `sqltypes` :</span><span class="sxs-lookup"><span data-stu-id="893c1-119">For example, the following XML schema collection fails, because it is adding a component to the `sqltypes` protected namespace:</span></span>  
  
    ```  
    CREATE XML SCHEMA COLLECTION SC AS '  
    <schema xmlns="http://www.w3.org/2001/XMLSchema"   
    targetNamespace    
        ="https://schemas.microsoft.com/sqlserver/2004/sqltypes" >   
          <element name="root" type="string"/>  
    </schema>'  
    GO  
    ```  
  
-   <span data-ttu-id="893c1-120">Vous ne pouvez pas utiliser la collection de schémas XML `sys` pour taper des colonnes, des variables ou des paramètres `xml` .</span><span class="sxs-lookup"><span data-stu-id="893c1-120">You cannot use the `sys` XML schema collection to type `xml` columns, variables, or parameters.</span></span> <span data-ttu-id="893c1-121">Par exemple, le code suivant retourne une erreur :</span><span class="sxs-lookup"><span data-stu-id="893c1-121">For example, the following code returns an error:</span></span>  
  
    ```  
    DECLARE @x xml (sys.sys)  
    ```  
  
-   <span data-ttu-id="893c1-122">La sérialisation de ces schémas intégrés n'est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="893c1-122">Serialization of these built-in schemas is not supported.</span></span> <span data-ttu-id="893c1-123">Par exemple, le code suivant retourne une erreur :</span><span class="sxs-lookup"><span data-stu-id="893c1-123">For example, the following code returns an error:</span></span>  
  
    ```  
    SELECT XML_SCHEMA_NAMESPACE(N'sys',N'sys')  
    GO  
    ```  
  
 <span data-ttu-id="893c1-124">Le code suivant est un autre exemple dans lequel vous créez une collection de schémas XML qui utilise le type `varchar` défini dans l'espace de noms `sqltypes` :</span><span class="sxs-lookup"><span data-stu-id="893c1-124">The following code is another example in which you create an XML schema collection that uses the `varchar` type defined in the `sqltypes` namespace:</span></span>  
  
```  
CREATE XML SCHEMA COLLECTION SC AS '  
<schema xmlns="http://www.w3.org/2001/XMLSchema"   
        targetNamespace="myNS" xmlns:ns="myNS"  
        xmlns:s="https://schemas.microsoft.com/sqlserver/2004/sqltypes">  
   <import     
     namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes"/>  
      <simpleType name="myType">  
            <restriction base="s:varchar">  
                  <maxLength value="20"/>  
            </restriction>  
      </simpleType>  
      <element name="root" type="ns:myType"/>  
</schema>'  
go  
```  
  
 <span data-ttu-id="893c1-125">Comme illustré ci-dessous, vous pouvez créer une variable `XML` typée, lui attribuer une instance XML et vérifier que la valeur du type d'élément <`root`> est un type `varchar`.</span><span class="sxs-lookup"><span data-stu-id="893c1-125">As shown in the following, you can create a typed `XML` variable, assign an XML instance to it, and verify that the value of the <`root`> element type is a `varchar` type.</span></span>  
  
```  
DECLARE @var XML(SC)  
SET @var = '<root xmlns="myNS">My data</root>'  
SELECT @var.query('declare namespace sqltypes = "https://schemas.microsoft.com/sqlserver/2004/sqltypes";  
declare namespace ns="myNS";   
data(/ns:root[1]) instance of sqltypes:varchar?')  
GO  
```  
  
 <span data-ttu-id="893c1-126">L’expression `instance of sqltypes:varchar?` retourne TRUE, car la valeur de l’élément &lt;`root`&gt; est d’un type dérivé de **varchar`@var` d’après le schéma associé à la variable** .</span><span class="sxs-lookup"><span data-stu-id="893c1-126">The `instance of sqltypes:varchar?` expression returns TRUE, because the <`root`> element value is of a type derived from **varchar** according to the schema that is associated with the `@var` variable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="893c1-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="893c1-127">See Also</span></span>  
 [<span data-ttu-id="893c1-128">Collections de schémas XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="893c1-128">XML Schema Collections &#40;SQL Server&#41;</span></span>](xml-schema-collections-sql-server.md)  
  
  
