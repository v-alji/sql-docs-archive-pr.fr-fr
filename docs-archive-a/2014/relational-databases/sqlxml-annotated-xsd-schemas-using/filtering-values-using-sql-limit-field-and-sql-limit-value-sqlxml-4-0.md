---
title: 'Filtrage de valeurs à l’aide de SQL : Limit-Field et SQL : Limit-Value (SQLXML 4,0) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- annotated XSD schemas, filtering values
- limiting values [SQLXML]
- limit-value annotation
- limit-field annotation
- sql:limit-field
- sql:limit-value
- filtering [SQLXML]
ms.assetid: c0f7ae92-eeec-430e-a66a-f22c3ae64a5e
author: rothja
ms.author: jroth
ms.openlocfilehash: 7886a9a6f51c76ed693576ca6f4659f4051d1f20
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709035"
---
# <a name="filtering-values-using-sqllimit-field-and-sqllimit-value-sqlxml-40"></a><span data-ttu-id="1f916-102">Filtrage de valeurs à l'aide des annotations sql:limit-field et sql:limit-value (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="1f916-102">Filtering Values Using sql:limit-field and sql:limit-value (SQLXML 4.0)</span></span>
  <span data-ttu-id="1f916-103">Vous pouvez limiter les lignes qui sont retournées à partir d'une requête de base de données et d'après une valeur de limitation.</span><span class="sxs-lookup"><span data-stu-id="1f916-103">You can limit rows that are returned from a database query on the basis of some limiting value.</span></span> <span data-ttu-id="1f916-104">Les annotations `sql:limit-field` et `sql:limit-value` sont utilisées pour identifier la colonne de base de données qui contient les valeurs de limitation et spécifier une valeur de limitation spécifique à utiliser pour filtrer les données retournées.</span><span class="sxs-lookup"><span data-stu-id="1f916-104">The `sql:limit-field` and `sql:limit-value` annotations are used to identify the database column that contains limiting values and to specify a specific limiting value to be used to filter the data returned.</span></span>  
  
 <span data-ttu-id="1f916-105">L'annotation `sql:limit-field` sert à identifier une colonne qui contient une valeur de limitation ; elle est autorisée dans chaque élément ou attribut mappé.</span><span class="sxs-lookup"><span data-stu-id="1f916-105">The `sql:limit-field` annotation is used to identify a column that contains a limiting value; it is allowed on each mapped element or attribute.</span></span>  
  
 <span data-ttu-id="1f916-106">L'annotation `sql:limit-value` est utilisée pour spécifier la valeur limitée dans la colonne elle-même spécifiée dans une annotation `sql:limit-field`.</span><span class="sxs-lookup"><span data-stu-id="1f916-106">The `sql:limit-value` annotation is used to specify the limited value in the column that is specified in the `sql:limit-field` annotation.</span></span> <span data-ttu-id="1f916-107">L'annotation `sql:limit-value` est facultative.</span><span class="sxs-lookup"><span data-stu-id="1f916-107">The `sql:limit-value` annotation is optional.</span></span> <span data-ttu-id="1f916-108">Si `sql:limit-value` n'est pas spécifiée, une valeur NULL est validée.</span><span class="sxs-lookup"><span data-stu-id="1f916-108">If `sql:limit-value` is not specified, a NULL value is assumed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1f916-109">Lors de l'utilisation d'une annotation `sql:limit-field` où la colonne SQL mappée est de type `real`, SQLXML 4.0 effectue une conversion sur l'annotation `sql:limit-value` comme spécifié dans les schémas XML sous la forme d'une valeur `nvarchar` spécifiée.</span><span class="sxs-lookup"><span data-stu-id="1f916-109">When working with a `sql:limit-field` where the mapped SQL column is of type `real`, SQLXML 4.0 performs conversion on the `sql:limit-value` as specified in XML schemas as an `nvarchar` specified value.</span></span> <span data-ttu-id="1f916-110">Pour cela, les valeurs de limite décimales doivent être spécifiées à l'aide de la notation scientifique complète.</span><span class="sxs-lookup"><span data-stu-id="1f916-110">This requires that decimal limit values be specified using full scientific notation.</span></span> <span data-ttu-id="1f916-111">Pour plus d'informations, consultez l'exemple B ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="1f916-111">For more information, see Example B below.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="1f916-112">Exemples</span><span class="sxs-lookup"><span data-stu-id="1f916-112">Examples</span></span>  
 <span data-ttu-id="1f916-113">Pour créer des exemples fonctionnels à l'aide de ces exemples, vous devez avoir installé les composants suivants :</span><span class="sxs-lookup"><span data-stu-id="1f916-113">To create working samples using these examples, you need to have the following installed:</span></span>  
  
-   <span data-ttu-id="1f916-114">Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client</span><span class="sxs-lookup"><span data-stu-id="1f916-114">Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client</span></span>  
  
-   <span data-ttu-id="1f916-115">MDAC 2.6 ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="1f916-115">MDAC 2.6 or later</span></span>  
  
 <span data-ttu-id="1f916-116">Dans ces exemples, les modèles sont utilisés pour spécifier des requêtes XPath par rapport au schéma de mappage XSD.</span><span class="sxs-lookup"><span data-stu-id="1f916-116">In these examples, templates are used to specify XPath queries against the mapping XSD schema.</span></span>  
  
### <a name="a-limiting-the-customer-addresses-returned-to-a-specific-address-type"></a><span data-ttu-id="1f916-117">R.</span><span class="sxs-lookup"><span data-stu-id="1f916-117">A.</span></span> <span data-ttu-id="1f916-118">Limitation des adresses de clients retournées à un type d'adresse spécifique</span><span class="sxs-lookup"><span data-stu-id="1f916-118">Limiting the customer addresses returned to a specific address type</span></span>  
 <span data-ttu-id="1f916-119">Dans cet exemple, une base de données contient deux tables :</span><span class="sxs-lookup"><span data-stu-id="1f916-119">In this example, a database contains two tables:</span></span>  
  
-   <span data-ttu-id="1f916-120">Customer (CustomerID, CompanyName)</span><span class="sxs-lookup"><span data-stu-id="1f916-120">Customer (CustomerID, CompanyName)</span></span>  
  
-   <span data-ttu-id="1f916-121">Addresses (CustomerID, AddressType, StreetAddress)</span><span class="sxs-lookup"><span data-stu-id="1f916-121">Addresses (CustomerID, AddressType, StreetAddress)</span></span>  
  
 <span data-ttu-id="1f916-122">Un client peut disposer d'une adresse de livraison et/ou d'une adresse de facturation.</span><span class="sxs-lookup"><span data-stu-id="1f916-122">A customer can have a shipping address and/or a billing address.</span></span> <span data-ttu-id="1f916-123">Les valeurs de la colonne AddressType sont Shipping et Billing.</span><span class="sxs-lookup"><span data-stu-id="1f916-123">The AddressType column values are Shipping and Billing.</span></span>  
  
 <span data-ttu-id="1f916-124">Il s’agit du schéma de mappage dans lequel l’attribut de schéma **ShipTo** est mappé à la colonne StreetAddress dans la relation Addresses.</span><span class="sxs-lookup"><span data-stu-id="1f916-124">This is the mapping schema in which the **ShipTo** schema attribute maps to the StreetAddress column in the Addresses relation.</span></span> <span data-ttu-id="1f916-125">Les valeurs retournées pour cet attribut sont limitées uniquement aux adresses de livraison en spécifiant les annotations `sql:limit-field` et `sql:limit-value`.</span><span class="sxs-lookup"><span data-stu-id="1f916-125">The values that are returned for this attribute are limited to only shipping addresses by specifying the `sql:limit-field` and `sql:limit-value` annotations.</span></span> <span data-ttu-id="1f916-126">De même, l’attribut de schéma **BillTo** retourne uniquement l’adresse de facturation d’un client.</span><span class="sxs-lookup"><span data-stu-id="1f916-126">Similarly, the **BillTo** schema attribute returns only the billing address of a customer.</span></span>  
  
 <span data-ttu-id="1f916-127">Voici le schéma :</span><span class="sxs-lookup"><span data-stu-id="1f916-127">This is the schema:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="CustAddr"  
        parent="Customer"  
        parent-key="CustomerID"  
        child="Addresses"  
        child-key="CustomerID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Customer" sql:relation="Customer" >  
   <xsd:complexType>  
        <xsd:sequence>  
        <xsd:element name="BillTo"   
                       type="xsd:string"   
                       sql:relation="Addresses"   
                       sql:field="StreetAddress"  
                       sql:limit-field="AddressType"  
                       sql:limit-value="billing"  
                       sql:relationship="CustAddr" >  
        </xsd:element>  
        <xsd:element name="ShipTo"   
                       type="xsd:string"   
                       sql:relation="Addresses"   
                       sql:field="StreetAddress"  
                       sql:limit-field="AddressType"  
                       sql:limit-value="shipping"  
                       sql:relationship="CustAddr" >  
        </xsd:element>  
        </xsd:sequence>  
        <xsd:attribute name="CustomerID"   type="xsd:int" />   
        <xsd:attribute name="CompanyName"  type="xsd:string" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="1f916-128">Pour tester un exemple de requête XPath sur le schéma</span><span class="sxs-lookup"><span data-stu-id="1f916-128">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="1f916-129">Créez deux tables dans la base de données **tempdb** :</span><span class="sxs-lookup"><span data-stu-id="1f916-129">Create two tables in the **tempdb** database:</span></span>  
  
    ```  
    USE tempdb  
    CREATE TABLE Customer (CustomerID int primary key,   
                           CompanyName varchar(30))  
    CREATE TABLE Addresses(CustomerID int,   
                           StreetAddress varchar(50),  
                           AddressType varchar(10))  
    ```  
  
2.  <span data-ttu-id="1f916-130">Ajoutez les exemples de données :</span><span class="sxs-lookup"><span data-stu-id="1f916-130">Add the sample data:</span></span>  
  
    ```  
    INSERT INTO Customer values (1, 'Company A')  
    INSERT INTO Customer values (2, 'Company B')  
  
    INSERT INTO Addresses values  
               (1, 'Obere Str. 57 Berlin', 'billing')  
    INSERT INTO Addresses values  
               (1, 'Avda. de la Constituci??n 2222 M??xico D.F.', 'shipping')  
    INSERT INTO Addresses values  
               (2, '120 Hanover Sq., London', 'billing')  
    INSERT INTO Addresses values  
               (2, 'Forsterstr. 57, Mannheim', 'shipping')  
    ```  
  
3.  <span data-ttu-id="1f916-131">Copiez le code de schéma ci-dessus et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="1f916-131">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="1f916-132">Enregistrez le fichier sous le nom LimitFieldValue.xml.</span><span class="sxs-lookup"><span data-stu-id="1f916-132">Save the file as LimitFieldValue.xml.</span></span>  
  
4.  <span data-ttu-id="1f916-133">Créez le modèle suivant (LimitFieldValueT.xml) et enregistrez-le dans le même répertoire où vous avez enregistré le schéma (LimitFieldValue.xml) lors de l'étape précédente :</span><span class="sxs-lookup"><span data-stu-id="1f916-133">Create the following template (LimitFieldValueT.xml), and save it in the same where you saved the schema (LimitFieldValue.xml) in the previous step:</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="LimitFieldValue.xml">  
            /Customer  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="1f916-134">Le chemin d'accès au répertoire spécifié pour le schéma de mappage (LimitFieldValue.xml) a trait au répertoire dans lequel le modèle est enregistré.</span><span class="sxs-lookup"><span data-stu-id="1f916-134">The directory path specified for the mapping schema (LimitFieldValue.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="1f916-135">Vous pouvez également spécifier un chemin d'accès absolu, par exemple :</span><span class="sxs-lookup"><span data-stu-id="1f916-135">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\LimitFieldValue.xml"  
    ```  
  
5.  <span data-ttu-id="1f916-136">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le modèle.</span><span class="sxs-lookup"><span data-stu-id="1f916-136">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="1f916-137">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="1f916-137">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="1f916-138">Voici le résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="1f916-138">This is the result:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">   
  <Customer CustomerID="1" CompanyName="Company A">   
     <BillTo>Obere Str. 57 Berlin</BillTo>   
     <ShipTo>Avda. de la Constituci??n 2222 M??xico D.F.</ShipTo>   
  </Customer>   
  <Customer CustomerID="2" CompanyName="Company B">   
     <BillTo>120 Hanover Sq., London</BillTo>   
     <ShipTo>Forsterstr. 57, Mannheim</ShipTo>   
   </Customer>   
</ROOT>  
```  
  
### <a name="b-limiting-results-based-on-a-discount-value-of-type-real-data"></a><span data-ttu-id="1f916-139">B.</span><span class="sxs-lookup"><span data-stu-id="1f916-139">B.</span></span> <span data-ttu-id="1f916-140">Limitation des résultats en fonction d'une valeur de remise de type de données real</span><span class="sxs-lookup"><span data-stu-id="1f916-140">Limiting results based on a discount value of type real data</span></span>  
 <span data-ttu-id="1f916-141">Dans cet exemple, une base de données contient deux tables :</span><span class="sxs-lookup"><span data-stu-id="1f916-141">In this example, a database contains two tables:</span></span>  
  
-   <span data-ttu-id="1f916-142">Orders (OrderID)</span><span class="sxs-lookup"><span data-stu-id="1f916-142">Orders (OrderID)</span></span>  
  
-   <span data-ttu-id="1f916-143">OrderDetails (OrderID, ProductID, UnitPrice, Quantity, Price, Discount)</span><span class="sxs-lookup"><span data-stu-id="1f916-143">OrderDetails (OrderID, ProductID, UnitPrice, Quantity, Price, Discount)</span></span>  
  
 <span data-ttu-id="1f916-144">Il s’agit du schéma de mappage dans lequel l’attribut **OrderID** sur les détails de la commande est mappé à la colonne OrderID dans la relation Orders.</span><span class="sxs-lookup"><span data-stu-id="1f916-144">This is the mapping schema in which the **OrderID** attribute on the order details maps to the OrderID column in the orders relation.</span></span> <span data-ttu-id="1f916-145">Les valeurs retournées pour cet attribut sont limitées uniquement à celles qui ont une valeur de 2, 0000000E e-001 (0,2) comme spécifié pour l’attribut **discount** à l’aide des `sql:limit-field` `sql:limit-value` annotations et.</span><span class="sxs-lookup"><span data-stu-id="1f916-145">The values that are returned for this attribute are limited to only those that have a value of 2.0000000e-001 (0.2) as specified for the **Discount** attribute using the `sql:limit-field` and `sql:limit-value` annotations.</span></span>  
  
 <span data-ttu-id="1f916-146">Voici le schéma :</span><span class="sxs-lookup"><span data-stu-id="1f916-146">This is the schema:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:annotation>  
   <xsd:appinfo>  
    <sql:relationship name="OrderOrderDetails"  
        parent="Orders"  
        parent-key="OrderID"  
        child="OrderDetails"  
        child-key="OrderID" />  
   </xsd:appinfo>  
  </xsd:annotation>  
  <xsd:element name="root" sql:is-constant="1">  
   <xsd:complexType>  
     <xsd:sequence>  
       <xsd:element name="Order" sql:relation="Orders" >  
          <xsd:complexType>  
             <xsd:sequence>  
                <xsd:element name="orderDetail"   
                       sql:relation="OrderDetails"   
                       sql:limit-field="Discount"                       sql:limit-value="2.0000000e-001"  
                       sql:relationship="OrderOrderDetails">  
                   <xsd:complexType>  
                     <xsd:attribute name="OrderID"   />   
                     <xsd:attribute name="ProductID" />   
                     <xsd:attribute name="Discount"  />   
                     <xsd:attribute name="Quantity"  />   
                     <xsd:attribute name="UnitPrice" />   
                   </xsd:complexType>  
                </xsd:element>  
            </xsd:sequence>  
           <xsd:attribute name="OrderID"/>   
          </xsd:complexType>  
       </xsd:element>  
     </xsd:sequence>  
   </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="1f916-147">Pour tester un exemple de requête XPath sur le schéma</span><span class="sxs-lookup"><span data-stu-id="1f916-147">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="1f916-148">Créez deux tables dans la base de données **tempdb** :</span><span class="sxs-lookup"><span data-stu-id="1f916-148">Create two tables in the **tempdb** database:</span></span>  
  
    ```  
    USE tempdb  
    CREATE TABLE Orders ([OrderID] int NOT NULL ) ON [PRIMARY]  
    ALTER TABLE Orders WITH NOCHECK ADD   
    CONSTRAINT [PK_Orders] PRIMARY KEY  CLUSTERED (  
       [OrderID]  
     )  ON [PRIMARY]   
    CREATE TABLE [OrderDetails] (  
       [OrderID] int NOT NULL ,  
       [ProductID] int NOT NULL ,  
       [UnitPrice] money NULL ,  
       [Quantity] smallint NOT NULL ,  
       [Discount] real NOT NULL   
    ) ON [PRIMARY]  
    ```  
  
2.  <span data-ttu-id="1f916-149">Ajoutez les exemples de données :</span><span class="sxs-lookup"><span data-stu-id="1f916-149">Add the sample data:</span></span>  
  
    ```  
    INSERT INTO Orders ([OrderID]) values (10248)  
    INSERT INTO Orders ([OrderID]) values (10250)  
    INSERT INTO Orders ([OrderID]) values (10251)  
    INSERT INTO Orders ([OrderID]) values (10257)  
    INSERT INTO Orders ([OrderID]) values (10258)  
    INSERT INTO [OrderDetails] ([OrderID],[ProductID],[UnitPrice],[Quantity],[Discount]) values (10248,11,14,12,0)  
    INSERT INTO [OrderDetails] ([OrderID],[ProductID],[UnitPrice],[Quantity],[Discount]) values (10250,51,42.4,35,0.15)  
    INSERT INTO [OrderDetails] ([OrderID],[ProductID],[UnitPrice],[Quantity],[Discount]) values (10251,22,16.8,6,0.05)  
    INSERT INTO [OrderDetails] ([OrderID],[ProductID],[UnitPrice],[Quantity],[Discount]) values (10257,77,10.4,15,0)  
    INSERT INTO [OrderDetails] ([OrderID],[ProductID],[UnitPrice],[Quantity],[Discount]) values (10258,2,15.2,50,0.2)  
    ```  
  
3.  <span data-ttu-id="1f916-150">Enregistrez le schéma (LimitFieldValue.xml) dans un répertoire.</span><span class="sxs-lookup"><span data-stu-id="1f916-150">Save the schema (LimitFieldValue.xml) in a directory.</span></span>  
  
4.  <span data-ttu-id="1f916-151">Créez le script de test suivant (TestQuery.vbs), modifiez MyServer en spécifiant le nom de votre ordinateur SQL Server et enregistrez-le dans le répertoire que vous avez utilisé à l'étape précédente pour enregistrer le schéma :</span><span class="sxs-lookup"><span data-stu-id="1f916-151">Create the following test script (TestQuery.vbs), modify MyServer to the name of your SQL Server computer and save it in the same directory as you used in the previous step to save the schema:</span></span>  
  
    ```  
    Set conn = CreateObject("ADODB.Connection")  
    conn.Open "Provider=SQLOLEDB;Data Source=MyServer;Database=tempdb;Integrated Security=SSPI"  
    conn.Properties("SQLXML Version") = "sqlxml.4.0"   
    Set cmd = CreateObject("ADODB.Command")  
    Set stm = CreateObject("ADODB.Stream")  
    Set cmd.ActiveConnection = conn  
    stm.open  
    result ="none"  
    strXPathQuery="/root"  
    DBGUID_XPATH = "{EC2A4293-E898-11D2-B1B7-00C04F680C56}"  
    cmd.Dialect = DBGUID_XPATH  
    cmd.CommandText = strXPathQuery  
    cmd.Properties("Mapping schema") = "LimitFieldReal.xml"  
    cmd.Properties("Output Stream").Value = stm  
    cmd.Properties("Output Encoding") = "utf-8"  
    WScript.Echo "executing for xml query"  
    On Error Resume Next  
    cmd.Execute , ,1024  
    if err then  
    Wscript.Echo err.description  
    Wscript.Echo err.Number  
    Wscript.Echo err.source  
    On Error GoTo 0  
    else  
    stm.Position = 0  
    result  = stm.ReadText  
    end if  
    WScript.Echo result  
    Wscript.Echo "done"  
    ```  
  
5.  <span data-ttu-id="1f916-152">Exécutez le fichier TestQuery.vbs en cliquant dessus dans l'Explorateur Windows.</span><span class="sxs-lookup"><span data-stu-id="1f916-152">Execute the TestQuery.vbs file by clicking on it in Windows Explorer.</span></span>  
  
     <span data-ttu-id="1f916-153">Voici le résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="1f916-153">This is the result:</span></span>  
  
    ```  
    <root>  
      <Order OrderID="10248"/>  
      <Order OrderID="10250"/>  
      <Order OrderID="10251"/>  
      <Order OrderID="10257"/>  
      <Order OrderID="10258">  
        <orderDetail OrderID="10258"   
                     ProductID="2"   
                     Discount="0.2"   
                     Quantity="50"/>  
      </Order>  
    </root>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="1f916-154">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1f916-154">See Also</span></span>  
 <span data-ttu-id="1f916-155">[&#41;Transact-SQL &#40;float et Real](/sql/t-sql/data-types/float-and-real-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1f916-155">[float and real &#40;Transact-SQL&#41;](/sql/t-sql/data-types/float-and-real-transact-sql) </span></span>  
 <span data-ttu-id="1f916-156">[nchar et nvarchar &#40;Transact-SQL&#41;](/sql/t-sql/data-types/nchar-and-nvarchar-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1f916-156">[nchar and nvarchar &#40;Transact-SQL&#41;](/sql/t-sql/data-types/nchar-and-nvarchar-transact-sql) </span></span>  
 <span data-ttu-id="1f916-157">[Installation de SQL Server Native Client](../../relational-databases/native-client/applications/installing-sql-server-native-client.md) </span><span class="sxs-lookup"><span data-stu-id="1f916-157">[Installing SQL Server Native Client](../../relational-databases/native-client/applications/installing-sql-server-native-client.md) </span></span>  
 [<span data-ttu-id="1f916-158">Utilisation de schémas XSD annotés dans les requêtes &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="1f916-158">Using Annotated XSD Schemas in Queries &#40;SQLXML 4.0&#41;</span></span>](../../relational-databases/sqlxml/annotated-xsd-schemas/using-annotated-xsd-schemas-in-queries-sqlxml-4-0.md)  
  
  
