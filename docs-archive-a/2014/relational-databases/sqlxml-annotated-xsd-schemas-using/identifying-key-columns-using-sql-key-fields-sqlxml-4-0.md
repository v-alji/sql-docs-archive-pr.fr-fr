---
title: 'Identification des colonnes clés à l’aide de SQL : key-fields (SQLXML 4,0) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- nesting XML results
- proper nesting in results [SQLXML]
- sql:key-fields
- XSD schemas [SQLXML], key columns
- identifying key columns [SQLXML]
- annotated XSD schemas, key columns
- key columns [SQLXML]
- relationships [SQLXML], key columns
- hierarchical relationships [SQLXML]
- key-fields annotation
ms.assetid: 1a5ad868-8602-45c4-913d-6fbb837eebb0
author: rothja
ms.author: jroth
ms.openlocfilehash: 0ab12b34874a54bad2e08a96d08ebd0cc994f946
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709024"
---
# <a name="identifying-key-columns-using-sqlkey-fields-sqlxml-40"></a><span data-ttu-id="fb137-102">Identification de colonnes clés à l'aide de sql:key-fields (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="fb137-102">Identifying Key Columns Using sql:key-fields (SQLXML 4.0)</span></span>
  <span data-ttu-id="fb137-103">Lorsqu'une requête XPath est spécifiée contre un schéma XSD, les informations de clés sont requises dans la plupart des cas pour obtenir une imbrication correcte dans le résultat.</span><span class="sxs-lookup"><span data-stu-id="fb137-103">When an XPath query is specified against an XSD schema, key information is required in most cases to obtain proper nesting in the result.</span></span> <span data-ttu-id="fb137-104">La spécification de l'annotation `sql:key-fields` est une méthode permettant de garantir que la hiérarchie appropriée est générée.</span><span class="sxs-lookup"><span data-stu-id="fb137-104">Specifying the `sql:key-fields` annotation is a way of ensuring that the appropriate hierarchy is generated.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fb137-105">Pour garantir l'imbrication correcte, il est recommandé de spécifier `sql:key-fields` pour les éléments qui mappent à des tables.</span><span class="sxs-lookup"><span data-stu-id="fb137-105">To ensure proper nesting, it is recommended that you specify `sql:key-fields` for elements that map to tables.</span></span> <span data-ttu-id="fb137-106">Le XML produit est sensible au classement du jeu de résultats sous-jacent.</span><span class="sxs-lookup"><span data-stu-id="fb137-106">The XML produced is sensitive to the ordering of the underlying result set.</span></span> <span data-ttu-id="fb137-107">Si `sql:key-fields` n'est pas spécifié, il se peut que le XML généré ne soit pas formé correctement.</span><span class="sxs-lookup"><span data-stu-id="fb137-107">If `sql:key-fields` is not specified, the XML generated might not be formed properly.</span></span>  
  
 <span data-ttu-id="fb137-108">La valeur de `sql:key-fields` identifie le ou les colonnes qui identifient de manière unique les lignes dans la relation.</span><span class="sxs-lookup"><span data-stu-id="fb137-108">The value of `sql:key-fields` identifies the column(s) that uniquely identify the rows in the relation.</span></span> <span data-ttu-id="fb137-109">Si plusieurs colonnes sont requises pour identifier une ligne de manière unique, les valeurs de colonnes sont délimitées par des espaces.</span><span class="sxs-lookup"><span data-stu-id="fb137-109">If more than one column is required to uniquely identify a row, the column values are delimited by spaces.</span></span>  
  
 <span data-ttu-id="fb137-110">Vous devez utiliser l' `sql:key-fields` annotation lorsqu’un élément contient un **\<sql:relationship>** qui est défini entre l’élément et un élément enfant, mais ne fournit pas la clé primaire de la table spécifiée dans l’élément parent.</span><span class="sxs-lookup"><span data-stu-id="fb137-110">You must use the `sql:key-fields` annotation when an element contains a **\<sql:relationship>** that is defined between the element and a child element but does not provide the primary key of the table that is specified in the parent element.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="fb137-111">Exemples</span><span class="sxs-lookup"><span data-stu-id="fb137-111">Examples</span></span>  
 <span data-ttu-id="fb137-112">Pour créer des exemples fonctionnels à l'aide des exemples suivants, vous devez répondre à certaines conditions requises.</span><span class="sxs-lookup"><span data-stu-id="fb137-112">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="fb137-113">Pour plus d’informations, consultez [Configuration requise pour l’exécution d’exemples SQLXML](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="fb137-113">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-producing-the-appropriate-nesting-when-sqlrelationship-does-not-provide-sufficient-information"></a><span data-ttu-id="fb137-114">R.</span><span class="sxs-lookup"><span data-stu-id="fb137-114">A.</span></span> <span data-ttu-id="fb137-115">Production de l’imbrication appropriée lorsque \<sql:relationship> ne fournit pas d’informations suffisantes</span><span class="sxs-lookup"><span data-stu-id="fb137-115">Producing the appropriate nesting when \<sql:relationship> does not provide sufficient information</span></span>  
 <span data-ttu-id="fb137-116">Cet exemple montre où `sql:key-fields` doit être spécifié.</span><span class="sxs-lookup"><span data-stu-id="fb137-116">This example shows where `sql:key-fields` must be specified.</span></span>  
  
 <span data-ttu-id="fb137-117">Prenons le schéma suivant :</span><span class="sxs-lookup"><span data-stu-id="fb137-117">Consider the following schema.</span></span> <span data-ttu-id="fb137-118">Le schéma spécifie une hiérarchie entre **\<Order>** les **\<Customer>** éléments et dans lesquels l' **\<Order>** élément est le parent et l' **\<Customer>** élément est un enfant.</span><span class="sxs-lookup"><span data-stu-id="fb137-118">The schema specifies a hierarchy between the **\<Order>** and **\<Customer>** elements in which the **\<Order>** element is the parent and the **\<Customer>** element is a child.</span></span>  
  
 <span data-ttu-id="fb137-119">La **\<sql:relationship>** balise est utilisée pour spécifier la relation parent-enfant.</span><span class="sxs-lookup"><span data-stu-id="fb137-119">The **\<sql:relationship>** tag is used to specify the parent-child relationship.</span></span> <span data-ttu-id="fb137-120">Elle identifie CustomerID dans la table Sales.SalesOrderHeader comme clé parente qui fait référence à la clé enfant CustomerID dans la table Sales.Customer.</span><span class="sxs-lookup"><span data-stu-id="fb137-120">It identifies CustomerID in the Sales.SalesOrderHeader table as the parent key that refers to the CustomerID child key in the Sales.Customer table.</span></span> <span data-ttu-id="fb137-121">Les informations fournies dans **\<sql:relationship>** ne sont pas suffisantes pour identifier de manière unique les lignes dans la table parente (Sales. SalesOrderHeader).</span><span class="sxs-lookup"><span data-stu-id="fb137-121">The information provided in **\<sql:relationship>** is not sufficient to uniquely identify rows in the parent table (Sales.SalesOrderHeader).</span></span> <span data-ttu-id="fb137-122">Par conséquent, sans l'annotation `sql:key-fields`, la hiérarchie générée est inexacte.</span><span class="sxs-lookup"><span data-stu-id="fb137-122">Therefore, without the `sql:key-fields` annotation, the hierarchy that is generated is inaccurate.</span></span>  
  
 <span data-ttu-id="fb137-123">Avec `sql:key-fields` spécifié sur **\<Order>** , l’annotation identifie de façon unique les lignes dans la table parente (Sales. SalesOrderHeader) et ses éléments enfants apparaissent sous son parent.</span><span class="sxs-lookup"><span data-stu-id="fb137-123">With `sql:key-fields` specified on **\<Order>**, the annotation uniquely identifies the rows in the parent (Sales.SalesOrderHeader table), and its child elements appear below its parent.</span></span>  
  
 <span data-ttu-id="fb137-124">Voici le schéma :</span><span class="sxs-lookup"><span data-stu-id="fb137-124">This is the schema:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="OrdCust"  
        parent="Sales.SalesOrderHeader"  
        parent-key="CustomerID"  
        child="Sales.Customer"  
        child-key="CustomerID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  <xsd:element name="Order" sql:relation="Sales.SalesOrderHeader"   
               sql:key-fields="SalesOrderID">  
   <xsd:complexType>  
     <xsd:sequence>  
     <xsd:element name="Customer" sql:relation="Sales.Customer"   
                       sql:relationship="OrdCust"  >  
       <xsd:complexType>  
         <xsd:attribute name="CustID" sql:field="CustomerID" />  
         <xsd:attribute name="SoldBy" sql:field="SalesPersonID" />  
       </xsd:complexType>  
     </xsd:element>  
     </xsd:sequence>  
     <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
     <xsd:attribute name= "CustomerID" type="xsd:string" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-create-a-working-sample-of-this-schema"></a><span data-ttu-id="fb137-125">Pour créer un exemple fonctionnel de ce schéma</span><span class="sxs-lookup"><span data-stu-id="fb137-125">To create a working sample of this schema</span></span>  
  
1.  <span data-ttu-id="fb137-126">Copiez le code de schéma ci-dessus et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="fb137-126">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="fb137-127">Enregistrez le fichier en tant que KeyFields1.xml.</span><span class="sxs-lookup"><span data-stu-id="fb137-127">Save the file as KeyFields1.xml.</span></span>  
  
2.  <span data-ttu-id="fb137-128">Copiez le modèle suivant et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="fb137-128">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="fb137-129">Enregistrez le fichier en tant que KeyFields1T.xml dans le même répertoire où vous avez enregistré KeyFields1.xml.</span><span class="sxs-lookup"><span data-stu-id="fb137-129">Save the file as KeyFields1T.xml in the same directory where you saved KeyFields1.xml.</span></span> <span data-ttu-id="fb137-130">La requête XPath dans le modèle retourne tous les **\<Order>** éléments dont le CustomerID est inférieur à 3.</span><span class="sxs-lookup"><span data-stu-id="fb137-130">The XPath query in the template returns all the **\<Order>** elements with a CustomerID of less than 3.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="KeyFields1.xml">  
            /Order[@CustomerID < 3]  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="fb137-131">Le chemin d'accès au répertoire spécifié pour le schéma de mappage (KeyFields1.xml) est relatif au répertoire où le modèle est enregistré.</span><span class="sxs-lookup"><span data-stu-id="fb137-131">The directory path specified for the mapping schema (KeyFields1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="fb137-132">Vous pouvez également spécifier un chemin d'accès absolu, par exemple :</span><span class="sxs-lookup"><span data-stu-id="fb137-132">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\KeyFields1.xml"  
    ```  
  
3.  <span data-ttu-id="fb137-133">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le modèle.</span><span class="sxs-lookup"><span data-stu-id="fb137-133">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="fb137-134">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="fb137-134">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="fb137-135">Voici le jeu de résultats partiel :</span><span class="sxs-lookup"><span data-stu-id="fb137-135">This is the partial result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
    <Order SalesOrderID="43860" CustomerID="1">  
       <Customer CustID="1" SoldBy="280"/>  
    </Order>  
    <Order SalesOrderID="44501" CustomerID="1">  
       <Customer CustID="1" SoldBy="280"/>  
    </Order>  
    <Order SalesOrderID="45283" CustomerID="1">  
       <Customer CustID="1" SoldBy="280"/>  
    </Order>  
    .....  
</ROOT>  
```  
  
### <a name="b-specifying-sqlkey-fields-to-produce-proper-nesting-in-the-result"></a><span data-ttu-id="fb137-136">B.</span><span class="sxs-lookup"><span data-stu-id="fb137-136">B.</span></span> <span data-ttu-id="fb137-137">Spécification de sql:key-fields afin de produire l'imbrication correcte dans le résultat</span><span class="sxs-lookup"><span data-stu-id="fb137-137">Specifying sql:key-fields to produce proper nesting in the result</span></span>  
 <span data-ttu-id="fb137-138">Dans le schéma suivant, aucune hiérarchie n’est spécifiée à l’aide de **\<sql:relationship>** .</span><span class="sxs-lookup"><span data-stu-id="fb137-138">In the following schema, there is no hierarchy specified using **\<sql:relationship>**.</span></span> <span data-ttu-id="fb137-139">Le schéma requiert encore la spécification de l'annotation `sql:key-fields` afin d'identifier de manière unique les employés dans la table HumanResources.Employee.</span><span class="sxs-lookup"><span data-stu-id="fb137-139">The schema still requires specifying the `sql:key-fields` annotation to uniquely identify employees in the HumanResources.Employee table.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="HumanResources.Employee" sql:key-fields="EmployeeID" >  
   <xsd:complexType>  
     <xsd:sequence>  
        <xsd:element name="Title">  
          <xsd:complexType>  
            <xsd:simpleContent>  
              <xsd:extension base="xsd:string">  
                 <xsd:attribute name="EmployeeID" type="xsd:integer" />  
              </xsd:extension>  
            </xsd:simpleContent>  
          </xsd:complexType>  
        </xsd:element>  
     </xsd:sequence>  
   </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-create-a-working-sample-of-this-schema"></a><span data-ttu-id="fb137-140">Pour créer un exemple fonctionnel de ce schéma</span><span class="sxs-lookup"><span data-stu-id="fb137-140">To create a working sample of this schema</span></span>  
  
1.  <span data-ttu-id="fb137-141">Copiez le code de schéma ci-dessus et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="fb137-141">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="fb137-142">Enregistrez le fichier en tant que KeyFields2.xml.</span><span class="sxs-lookup"><span data-stu-id="fb137-142">Save the file as KeyFields2.xml.</span></span>  
  
2.  <span data-ttu-id="fb137-143">Copiez le modèle suivant et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="fb137-143">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="fb137-144">Enregistrez le fichier en tant que KeyFields2T.xml dans le même répertoire où vous avez enregistré KeyFields2.xml.</span><span class="sxs-lookup"><span data-stu-id="fb137-144">Save the file as KeyFields2T.xml in the same directory where you saved KeyFields2.xml.</span></span> <span data-ttu-id="fb137-145">La requête XPath dans le modèle retourne tous les **\<HumanResources.Employee>** éléments :</span><span class="sxs-lookup"><span data-stu-id="fb137-145">The XPath query in the template returns all the **\<HumanResources.Employee>** elements:</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="KeyFields2.xml">  
        /HumanResources.Employee  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="fb137-146">Le chemin d'accès au répertoire spécifié pour le schéma de mappage (KeyFields2.xml) est relatif au répertoire où le modèle est enregistré.</span><span class="sxs-lookup"><span data-stu-id="fb137-146">The directory path specified for the mapping schema (KeyFields2.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="fb137-147">Vous pouvez également spécifier un chemin d'accès absolu, par exemple :</span><span class="sxs-lookup"><span data-stu-id="fb137-147">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\KeyFields2.xml"  
    ```  
  
3.  <span data-ttu-id="fb137-148">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le modèle.</span><span class="sxs-lookup"><span data-stu-id="fb137-148">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="fb137-149">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="fb137-149">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="fb137-150">Voici le résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="fb137-150">This is the result:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <HumanResources.Employee>  
    <Title EmployeeID="1">Production Technician - WC60</Title>   
  </HumanResources.Employee>  
  <HumanResources.Employee>  
    <Title EmployeeID="2">Marketing Assistant</Title>   
  </HumanResources.Employee>  
  <HumanResources.Employee>  
    <Title EmployeeID="3">Engineering Manager</Title>   
  </HumanResources.Employee>  
  ...  
</ROOT>  
```  
  
  
