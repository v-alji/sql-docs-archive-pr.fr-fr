---
title: 'Création d’éléments constants à l’aide de SQL : is-constant (SQLXML 4,0) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- element does not map [SQLXML]
- sql:is-constant
- XSD schemas [SQLXML], constant elements
- element mapping [SQLXML], constant elements
- is-constant annotation
- constant elements [SQLXML]
- annotated XSD schemas, constant elements
ms.assetid: 940eea1b-54f5-445f-b844-c894d9f3941b
author: rothja
ms.author: jroth
ms.openlocfilehash: 8deedd8547d6bc3f0154eedb889ad908750f071a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702559"
---
# <a name="creating-constant-elements-using-sqlis-constant-sqlxml-40"></a><span data-ttu-id="6553c-102">Création d'éléments constants à l'aide de sql:is-constant (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="6553c-102">Creating Constant Elements Using sql:is-constant (SQLXML 4.0)</span></span>
  <span data-ttu-id="6553c-103">Pour spécifier un élément constant, c’est-à-dire un élément dans le schéma XSD qui n’est mappé à aucune table ou colonne de base de données, vous pouvez utiliser l' `sql:is-constant` annotation.</span><span class="sxs-lookup"><span data-stu-id="6553c-103">To specify a constant element-that is, an element in the XSD schema that does not map to any database table or column-you can use the `sql:is-constant` annotation.</span></span> <span data-ttu-id="6553c-104">Cette annotation accepte une valeur booléenne (0 = false, 1 = true).</span><span class="sxs-lookup"><span data-stu-id="6553c-104">This annotation takes a Boolean value (0 = false, 1 = true).</span></span> <span data-ttu-id="6553c-105">Les valeurs acceptables sont 0, 1, true et false.</span><span class="sxs-lookup"><span data-stu-id="6553c-105">The acceptable values are 0, 1, true, and false.</span></span> <span data-ttu-id="6553c-106">L'annotation `sql:is-constant` peut être spécifiée sur un élément qui n'a pas d'attributs.</span><span class="sxs-lookup"><span data-stu-id="6553c-106">The `sql:is-constant` annotation can be specified on an element that does not have any attributes.</span></span> <span data-ttu-id="6553c-107">Si elle est spécifiée sur un élément qui a la valeur true (ou 1), cet élément n'est pas mappé à la base de données mais apparaît néanmoins dans le document XML.</span><span class="sxs-lookup"><span data-stu-id="6553c-107">If it is specified on an element with the value true (or 1), that element is not mapped to the database but still appears in the XML document.</span></span>  
  
 <span data-ttu-id="6553c-108">L'annotation `sql:is-constant` peut être utilisée pour :</span><span class="sxs-lookup"><span data-stu-id="6553c-108">The `sql:is-constant` annotation can be used for:</span></span>  
  
-   <span data-ttu-id="6553c-109">ajouter un élément de niveau supérieur au document XML.</span><span class="sxs-lookup"><span data-stu-id="6553c-109">Adding a top-level element to the XML document.</span></span> <span data-ttu-id="6553c-110">Le code XML requiert un seul élément de niveau supérieur (élément racine) pour le document ;</span><span class="sxs-lookup"><span data-stu-id="6553c-110">XML requires a single top-level element (root element) for the document.</span></span>  
  
-   <span data-ttu-id="6553c-111">Création d’éléments conteneurs, tels qu’un **\<Orders>** élément qui encapsule toutes les commandes.</span><span class="sxs-lookup"><span data-stu-id="6553c-111">Creating container elements, such as an **\<Orders>** element that wraps all orders.</span></span>  
  
 <span data-ttu-id="6553c-112">L' `sql:is-constant` annotation peut être ajoutée à un **\<complexType>** élément.</span><span class="sxs-lookup"><span data-stu-id="6553c-112">The `sql:is-constant` annotation can be added to a **\<complexType>** element.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="6553c-113">Exemples</span><span class="sxs-lookup"><span data-stu-id="6553c-113">Examples</span></span>  
 <span data-ttu-id="6553c-114">Pour créer des exemples fonctionnels à l'aide des exemples suivants, vous devez répondre à certaines conditions requises.</span><span class="sxs-lookup"><span data-stu-id="6553c-114">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="6553c-115">Pour plus d’informations, consultez [Configuration requise pour l’exécution d’exemples SQLXML](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="6553c-115">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-sqlis-constant-to-add-a-container-element"></a><span data-ttu-id="6553c-116">R.</span><span class="sxs-lookup"><span data-stu-id="6553c-116">A.</span></span> <span data-ttu-id="6553c-117">Spécification de sql:is-constant pour ajouter un élément conteneur</span><span class="sxs-lookup"><span data-stu-id="6553c-117">Specifying sql:is-constant to add a container element</span></span>  
 <span data-ttu-id="6553c-118">Dans ce schéma XSD annoté, **\<CustomerOrders>** est défini en tant qu’élément constant en spécifiant l' `sql:is-constant` attribut avec la valeur 1.</span><span class="sxs-lookup"><span data-stu-id="6553c-118">In this annotated XSD schema, **\<CustomerOrders>** is defined as a constant element by specifying the `sql:is-constant` attribute with a value of 1.</span></span> <span data-ttu-id="6553c-119">Par conséquent, **\<CustomerOrders>** n’est mappé à aucune table ou colonne de base de données.</span><span class="sxs-lookup"><span data-stu-id="6553c-119">Therefore, **\<CustomerOrders>** is not mapped to any database table or column.</span></span> <span data-ttu-id="6553c-120">Cet élément constant se compose des **\<Order>** éléments enfants.</span><span class="sxs-lookup"><span data-stu-id="6553c-120">This constant element consists of the **\<Order>** child elements.</span></span>  
  
 <span data-ttu-id="6553c-121">Bien que **\<CustomerOrders>** ne soit mappé à aucune table ou colonne de base de données, il apparaît toujours dans le XML résultant en tant qu’élément conteneur contenant les **\<Order>** éléments enfants.</span><span class="sxs-lookup"><span data-stu-id="6553c-121">Although **\<CustomerOrders>** does not map to any database table or column, it still appears in the resulting XML as a container element containing the **\<Order>** child elements.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="CustOrders"  
        parent="Sales.Customer"  
        parent-key="CustomerID"  
        child="Sales.SalesOrderHeader"  
        child-key="CustomerID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Customer" sql:relation="Sales.Customer" >  
   <xsd:complexType>  
     <xsd:sequence>  
        <xsd:element name="CustomerOrders" sql:is-constant="1" >  
          <xsd:complexType>  
            <xsd:sequence>  
              <xsd:element name="Order" sql:relation="Sales.SalesOrderHeader"  
                           sql:relationship="CustOrders"   
                           maxOccurs="unbounded" >  
                <xsd:complexType>  
                   <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
                   <xsd:attribute name="OrderDate" type="xsd:date" />  
                   <xsd:attribute name="CustomerID" type="xsd:string" />  
                </xsd:complexType>  
              </xsd:element>  
            </xsd:sequence>  
           </xsd:complexType>  
          </xsd:element>  
         </xsd:sequence>  
          <xsd:attribute name="CustomerID" type="xsd:string" />  
     </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="6553c-122">Pour tester un exemple de requête XPath sur le schéma</span><span class="sxs-lookup"><span data-stu-id="6553c-122">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="6553c-123">Copiez le code de schéma ci-dessus et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="6553c-123">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="6553c-124">Enregistrez le fichier sous le nom isConstant.xml.</span><span class="sxs-lookup"><span data-stu-id="6553c-124">Save the file as isConstant.xml.</span></span>  
  
2.  <span data-ttu-id="6553c-125">Copiez le modèle suivant et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="6553c-125">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="6553c-126">Enregistrez le fichier sous le nom isConstantT.xml dans le répertoire où vous avez enregistré le fichier isConstant.xml.</span><span class="sxs-lookup"><span data-stu-id="6553c-126">Save the file as isConstantT.xml in the same directory where you saved isConstant.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="isConstant.xml">  
            Customer[@CustomerID=1]  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="6553c-127">Le chemin d'accès au répertoire spécifié pour le schéma de mappage (isConstant.xml) est relatif au répertoire où le modèle est enregistré.</span><span class="sxs-lookup"><span data-stu-id="6553c-127">The directory path specified for the mapping schema (isConstant.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="6553c-128">Vous pouvez également spécifier un chemin d'accès absolu, par exemple :</span><span class="sxs-lookup"><span data-stu-id="6553c-128">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\isConstant.xml"  
    ```  
  
3.  <span data-ttu-id="6553c-129">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le modèle.</span><span class="sxs-lookup"><span data-stu-id="6553c-129">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="6553c-130">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="6553c-130">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="6553c-131">Voici le jeu de résultats partiel :</span><span class="sxs-lookup"><span data-stu-id="6553c-131">This is the partial result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">   
<Customer CustomerID="1">   
  <CustomerOrders>   
    <Order SalesOrderID="43860" OrderDate="2001-08-01" CustomerID="1" />   
    <Order SalesOrderID="44501" OrderDate="2001-11-01" CustomerID="1" />   
    <Order SalesOrderID="45283" OrderDate="2002-02-01" CustomerID="1" />   
    <Order SalesOrderID="46042" OrderDate="2002-05-01" CustomerID="1" />   
    ...  
  </CustomerOrders>   
</Customer>   
</ROOT>  
```  
  
  
