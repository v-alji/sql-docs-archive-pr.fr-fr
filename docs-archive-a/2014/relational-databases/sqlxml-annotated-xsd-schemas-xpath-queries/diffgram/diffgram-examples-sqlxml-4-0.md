---
title: Exemples DiffGram (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- DiffGrams [SQLXML], examples
- examples [SQLXML], DiffGram
- diffgr:parentID
- parentID annotation
ms.assetid: fc148583-dfd3-4efb-a413-f47b150b0975
author: rothja
ms.author: jroth
ms.openlocfilehash: 04fb355af01f9853149a84af72471375d9135468
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610555"
---
# <a name="diffgram-examples-sqlxml-40"></a><span data-ttu-id="15a18-102">Exemples de DiffGrams (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="15a18-102">DiffGram Examples (SQLXML 4.0)</span></span>
  <span data-ttu-id="15a18-103">Cette rubrique contient des exemples de DiffGrams qui réalisent des opérations d'insertion, de mise à jour et de suppression dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="15a18-103">The examples in this topic consist of DiffGrams that perform insert, update, and delete operations to the database.</span></span> <span data-ttu-id="15a18-104">Avant d'utiliser les exemples, notez les points suivants :</span><span class="sxs-lookup"><span data-stu-id="15a18-104">Before using the examples, note the following:</span></span>  
  
-   <span data-ttu-id="15a18-105">Les exemples utilisent deux tables (Cust et Ord) qui doivent être créées si vous souhaitez tester les exemples de DiffGrams :</span><span class="sxs-lookup"><span data-stu-id="15a18-105">The examples use two tables (Cust and Ord) that must be created if you want to test the DiffGram examples:</span></span>  
  
    ```  
    Cust(CustomerID, CompanyName, ContactName)  
    Ord(OrderID, CustomerID)  
    ```  
  
-   <span data-ttu-id="15a18-106">La plupart des exemples de cette rubrique utilise le schéma XSD suivant :</span><span class="sxs-lookup"><span data-stu-id="15a18-106">Most of the examples in this topic use the following XSD Schema:</span></span>  
  
    ```  
    <xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
                xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  
    <xsd:annotation>  
      <xsd:documentation>  
        Diffgram Customers/Orders Schema.  
      </xsd:documentation>  
      <xsd:appinfo>  
           <sql:relationship name="CustomersOrders"   
                      parent="Cust"  
                      parent-key="CustomerID"  
                      child-key="CustomerID"  
                      child="Ord"/>  
      </xsd:appinfo>  
    </xsd:annotation>  
  
    <xsd:element name="Customer" sql:relation="Cust">  
      <xsd:complexType>  
        <xsd:sequence>  
          <xsd:element name="CompanyName"    type="xsd:string"/>  
          <xsd:element name="ContactName"    type="xsd:string"/>  
           <xsd:element name="Order" sql:relation="Ord" sql:relationship="CustomersOrders">  
            <xsd:complexType>  
              <xsd:attribute name="OrderID" type="xsd:int" sql:field="OrderID"/>  
              <xsd:attribute name="CustomerID" type="xsd:string"/>  
            </xsd:complexType>  
          </xsd:element>  
        </xsd:sequence>  
        <xsd:attribute name="CustomerID" type="xsd:string" sql:field="CustomerID"/>  
      </xsd:complexType>  
    </xsd:element>  
  
    </xsd:schema>     
    ```  
  
     <span data-ttu-id="15a18-107">Enregistrez ce schéma sous le nom DiffGramSchema.xml dans le dossier où vous enregistrez les autres fichiers utilisés dans les exemples.</span><span class="sxs-lookup"><span data-stu-id="15a18-107">Save this schema as DiffGramSchema.xml in the same folder where you save other files used in the examples.</span></span>  
  
## <a name="a-deleting-a-record-by-using-a-diffgram"></a><span data-ttu-id="15a18-108">R.</span><span class="sxs-lookup"><span data-stu-id="15a18-108">A.</span></span> <span data-ttu-id="15a18-109">Suppression d'un enregistrement à l'aide d'un DiffGram</span><span class="sxs-lookup"><span data-stu-id="15a18-109">Deleting a record by using a DiffGram</span></span>  
 <span data-ttu-id="15a18-110">Le DiffGram de cet exemple supprime un client (dont CustomerID a la valeur ALFKI) de la table Cust et supprime l'enregistrement de commande correspondant (dont OrderID a la valeur 1) de la table Ord.</span><span class="sxs-lookup"><span data-stu-id="15a18-110">The DiffGram in this example deletes a customer (whose CustomerID is ALFKI) record from the Cust table and deletes the corresponding order record (whose OrderID is 1) from the Ord table.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql" sql:mapping-schema="DiffGramSchema.xml">  
  <diffgr:diffgram   
           xmlns:msdata="urn:schemas-microsoft-com:xml-msdata"   
           xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1">  
    <DataInstance/>  
  
    <diffgr:before>  
        <Order diffgr:id="Order1"   
               msdata:rowOrder="0"   
               CustomerID="ALFKI"   
               OrderID="1"/>  
        <Customer diffgr:id="Customer1"   
                  msdata:rowOrder="0"   
                  CustomerID="ALFKI">  
           <CompanyName>Alfreds Futterkiste</CompanyName>  
           <ContactName>Maria Anders</ContactName>  
        </Customer>  
    </diffgr:before>  
    <msdata:errors/>  
  </diffgr:diffgram>  
</ROOT>  
```  
  
 <span data-ttu-id="15a18-111">Dans le **\<before>** bloc, il existe un **\<Order>** élément (**diffgr : ID = "Order1"**) et un **\<Customer>** élément (**diffgr : ID = "Customer1"**).</span><span class="sxs-lookup"><span data-stu-id="15a18-111">In the **\<before>** block, there is an **\<Order>** element (**diffgr:id="Order1"**) and a **\<Customer>** element (**diffgr:id="Customer1"**).</span></span> <span data-ttu-id="15a18-112">Ces éléments représentent les enregistrements existants de la base de données.</span><span class="sxs-lookup"><span data-stu-id="15a18-112">These elements represent existing records in the database.</span></span> <span data-ttu-id="15a18-113">L' **\<DataInstance>** élément n’a pas les enregistrements correspondants (avec le même **diffgr : ID**).</span><span class="sxs-lookup"><span data-stu-id="15a18-113">The **\<DataInstance>** element does not have the corresponding records (with the same **diffgr:id**).</span></span> <span data-ttu-id="15a18-114">Cela indique une opération de suppression.</span><span class="sxs-lookup"><span data-stu-id="15a18-114">This indicates a delete operation.</span></span>  
  
#### <a name="to-test-the-diffgram"></a><span data-ttu-id="15a18-115">Pour tester le DiffGram</span><span class="sxs-lookup"><span data-stu-id="15a18-115">To test the DiffGram</span></span>  
  
1.  <span data-ttu-id="15a18-116">Créez ces tables dans la base de données **tempdb** .</span><span class="sxs-lookup"><span data-stu-id="15a18-116">Create these tables in the **tempdb** database.</span></span>  
  
    ```  
    CREATE TABLE Cust(  
            CustomerID  nchar(5) Primary Key,  
            CompanyName nvarchar(40) NOT NULL ,  
            ContactName nvarchar(60) NULL)  
    GO  
  
    CREATE TABLE Ord(  
       OrderID    int Primary Key,  
       CustomerID nchar(5) Foreign Key REFERENCES Cust(CustomerID))  
    GO  
    ```  
  
2.  <span data-ttu-id="15a18-117">Ajoutez les exemples de données suivants :</span><span class="sxs-lookup"><span data-stu-id="15a18-117">Add this sample data:</span></span>  
  
    ```  
    INSERT INTO Cust(CustomerID, CompanyName, ContactName) VALUES  
         (N'ALFKI', N'Alfreds Futterkiste', N'Maria Anders')  
    INSERT INTO Cust(CustomerID, CompanyName, ContactName) VALUES  
         (N'ANATR', N'Ana Trujillo Emparedados y helados', N'Ana Trujillo')  
    INSERT INTO Cust(CustomerID, CompanyName, ContactName) VALUES  
         (N'ANTON', N'Antonio Moreno Taquer??a', N'Antonio Moreno')  
  
    INSERT INTO Ord(OrderID, CustomerID) VALUES(1, N'ALFKI')  
    INSERT INTO Ord(OrderID, CustomerID) VALUES(2, N'ANATR')  
    INSERT INTO Ord(OrderID, CustomerID) VALUES(3, N'ANTON')  
    ```  
  
3.  <span data-ttu-id="15a18-118">Copiez le DiffGram ci-dessus et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="15a18-118">Copy the DiffGram above and paste it into a text file.</span></span> <span data-ttu-id="15a18-119">Enregistrez le fichier sous le nom MyDiffGram.xml dans le même dossier qu'à l'étape précédente.</span><span class="sxs-lookup"><span data-stu-id="15a18-119">Save the file as MyDiffGram.xml in the same folder used in the previous step.</span></span>  
  
4.  <span data-ttu-id="15a18-120">Copiez le DiffGramSchema fourni plus haut dans cette rubrique et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="15a18-120">Copy the DiffGramSchema provided earlier in this topic and paste it into a text file.</span></span> <span data-ttu-id="15a18-121">Enregistrez le fichier sous le nom DiffGramSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="15a18-121">Save the file as DiffGramSchema.xml.</span></span>  
  
5.  <span data-ttu-id="15a18-122">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le DiffGram.</span><span class="sxs-lookup"><span data-stu-id="15a18-122">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the DiffGram.</span></span>  
  
     <span data-ttu-id="15a18-123">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="15a18-123">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
## <a name="b-inserting-a-record-by-using-a-diffgram"></a><span data-ttu-id="15a18-124">B.</span><span class="sxs-lookup"><span data-stu-id="15a18-124">B.</span></span> <span data-ttu-id="15a18-125">Insertion d'un enregistrement à l'aide d'un DiffGram</span><span class="sxs-lookup"><span data-stu-id="15a18-125">Inserting a record by using a DiffGram</span></span>  
 <span data-ttu-id="15a18-126">Dans cet exemple, le DiffGram insère un enregistrement dans la table Cust et un enregistrement dans la table Ord.</span><span class="sxs-lookup"><span data-stu-id="15a18-126">In this example, the DiffGram inserts a record in the Cust table and a record in the Ord table.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql"   
      sql:mapping-schema="DiffGramSchema.xml">  
  <diffgr:diffgram   
          xmlns:msdata="urn:schemas-microsoft-com:xml-msdata"   
          xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1">  
    <DataInstance>  
       <Customer diffgr:id="Customer1" msdata:rowOrder="0"    
                 diffgr:hasChanges="inserted" CustomerID="ALFKI">  
        <CompanyName>C3Company</CompanyName>  
        <ContactName>C3Contact</ContactName>  
        <Order diffgr:id="Order1"   
               msdata:rowOrder="0"  
               diffgr:hasChanges="inserted"   
               CustomerID="ALFKI" OrderID="1"/>  
      </Customer>  
    </DataInstance>  
  
  </diffgr:diffgram>  
</ROOT>  
```  
  
 <span data-ttu-id="15a18-127">Dans ce DiffGram, le **\<before>** bloc n’est pas spécifié (aucun enregistrement de base de données existant n’a été identifié).</span><span class="sxs-lookup"><span data-stu-id="15a18-127">In this DiffGram the **\<before>** block is not specified (no existing database records identified).</span></span> <span data-ttu-id="15a18-128">Deux instances d’enregistrement (identifiées par les **\<Customer>** **\<Order>** éléments et dans le **\<DataInstance>** bloc) sont mappées aux tables Cust et ORD, respectivement.</span><span class="sxs-lookup"><span data-stu-id="15a18-128">There are two record instances (identified by the **\<Customer>** and **\<Order>** elements in the **\<DataInstance>** block) that map to Cust and Ord tables, respectively.</span></span> <span data-ttu-id="15a18-129">Ces deux éléments spécifient l’attribut **diffgr : hasChanges** (**HasChanges = "inserted"**).</span><span class="sxs-lookup"><span data-stu-id="15a18-129">Both of these elements specify the **diffgr:hasChanges** attribute (**hasChanges="inserted"**).</span></span> <span data-ttu-id="15a18-130">Cela indique une opération d'insertion.</span><span class="sxs-lookup"><span data-stu-id="15a18-130">This indicates an insert operation.</span></span> <span data-ttu-id="15a18-131">Dans ce DiffGram, si vous spécifiez **HasChanges = "modified"**, vous indiquez que vous souhaitez modifier un enregistrement qui n’existe pas, ce qui génère une erreur.</span><span class="sxs-lookup"><span data-stu-id="15a18-131">In this DiffGram, if you specify **hasChanges="modified"**, you are indicating that you want to modify a record that does not exist, which results in an error.</span></span>  
  
#### <a name="to-test-the-diffgram"></a><span data-ttu-id="15a18-132">Pour tester le DiffGram</span><span class="sxs-lookup"><span data-stu-id="15a18-132">To test the DiffGram</span></span>  
  
1.  <span data-ttu-id="15a18-133">Créez ces tables dans la base de données **tempdb** .</span><span class="sxs-lookup"><span data-stu-id="15a18-133">Create these tables in the **tempdb** database.</span></span>  
  
    ```  
    CREATE TABLE Cust(  
            CustomerID  nchar(5) Primary Key,  
            CompanyName nvarchar(40) NOT NULL ,  
            ContactName nvarchar(60) NULL)  
    GO  
  
    CREATE TABLE Ord(  
       OrderID    int Primary Key,  
       CustomerID nchar(5) Foreign Key REFERENCES Cust(CustomerID))  
    GO  
    ```  
  
2.  <span data-ttu-id="15a18-134">Ajoutez les exemples de données suivants :</span><span class="sxs-lookup"><span data-stu-id="15a18-134">Add this sample data:</span></span>  
  
    ```  
    INSERT INTO Cust(CustomerID, CompanyName, ContactName) VALUES  
         (N'ALFKI', N'Alfreds Futterkiste', N'Maria Anders')  
    INSERT INTO Cust(CustomerID, CompanyName, ContactName) VALUES  
         (N'ANATR', N'Ana Trujillo Emparedados y helados', N'Ana Trujillo')  
    INSERT INTO Cust(CustomerID, CompanyName, ContactName) VALUES  
         (N'ANTON', N'Antonio Moreno Taquer??a', N'Antonio Moreno')  
  
    INSERT INTO Ord(OrderID, CustomerID) VALUES(1, N'ALFKI')  
    INSERT INTO Ord(OrderID, CustomerID) VALUES(2, N'ANATR')  
    INSERT INTO Ord(OrderID, CustomerID) VALUES(3, N'ANTON')  
    ```  
  
3.  <span data-ttu-id="15a18-135">Copiez le DiffGram ci-dessus et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="15a18-135">Copy the DiffGram above and paste it into a text file.</span></span> <span data-ttu-id="15a18-136">Enregistrez le fichier sous le nom MyDiffGram.xml dans le même dossier qu'à l'étape précédente.</span><span class="sxs-lookup"><span data-stu-id="15a18-136">Save the file as MyDiffGram.xml in the same folder used in the previous step.</span></span>  
  
4.  <span data-ttu-id="15a18-137">Copiez le DiffGramSchema fourni plus haut dans cette rubrique et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="15a18-137">Copy the DiffGramSchema provided earlier in this topic and paste it into a text file.</span></span> <span data-ttu-id="15a18-138">Enregistrez le fichier sous le nom DiffGramSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="15a18-138">Save the file as DiffGramSchema.xml.</span></span>  
  
5.  <span data-ttu-id="15a18-139">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le DiffGram.</span><span class="sxs-lookup"><span data-stu-id="15a18-139">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the DiffGram.</span></span>  
  
     <span data-ttu-id="15a18-140">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="15a18-140">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
## <a name="c-updating-an-existing-record-by-using-a-diffgram"></a><span data-ttu-id="15a18-141">C.</span><span class="sxs-lookup"><span data-stu-id="15a18-141">C.</span></span> <span data-ttu-id="15a18-142">Mise à jour d'un enregistrement existant à l'aide d'un DiffGram</span><span class="sxs-lookup"><span data-stu-id="15a18-142">Updating an existing record by using a DiffGram</span></span>  
 <span data-ttu-id="15a18-143">Dans cet exemple, le DiffGram met à jour les informations sur les clients (CompanyName et ContactName) pour le client ALFKI.</span><span class="sxs-lookup"><span data-stu-id="15a18-143">In this example, the DiffGram updates customer information (CompanyName and ContactName) for customer ALFKI.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql" sql:mapping-schema="DiffGramSchema.xml">  
  <diffgr:diffgram   
           xmlns:msdata="urn:schemas-microsoft-com:xml-msdata"   
           xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1">  
    <DataInstance>  
      <Customer diffgr:id="Customer1"   
                msdata:rowOrder="0" diffgr:hasChanges="modified"   
                CustomerID="ALFKI">  
          <CompanyName>Bottom Dollar Markets</CompanyName>  
          <ContactName>Antonio Moreno</ContactName>  
      </Customer>  
    </DataInstance>  
  
    <diffgr:before>  
     <Customer diffgr:id="Customer1"   
               msdata:rowOrder="0"   
               CustomerID="ALFKI">  
        <CompanyName>Alfreds Futterkiste</CompanyName>  
        <ContactName>Maria Anders</ContactName>  
      </Customer>  
    </diffgr:before>  
  
  </diffgr:diffgram>  
</ROOT>  
```  
  
 <span data-ttu-id="15a18-144">Le **\<before>** bloc comprend un **\<Customer>** élément (**diffgr : ID = "Customer1"**).</span><span class="sxs-lookup"><span data-stu-id="15a18-144">The **\<before>** block includes a **\<Customer>** element (**diffgr:id="Customer1"**).</span></span> <span data-ttu-id="15a18-145">Le **\<DataInstance>** bloc comprend l' **\<Customer>** élément correspondant avec le même **ID**. L' **\<customer>** élément dans le **\<NewDataSet>** spécifie également **diffgr : hasChanges = "modified"**.</span><span class="sxs-lookup"><span data-stu-id="15a18-145">The **\<DataInstance>** block includes the corresponding **\<Customer>** element with same **id**. The **\<customer>** element in the **\<NewDataSet>** also specifies **diffgr:hasChanges="modified"**.</span></span> <span data-ttu-id="15a18-146">Cela indique une opération de mise à jour et l’enregistrement du client dans la table **cust** est mis à jour en conséquence.</span><span class="sxs-lookup"><span data-stu-id="15a18-146">This indicates an update operation, and the customer record in the **Cust** table is updated accordingly.</span></span> <span data-ttu-id="15a18-147">Notez que si l’attribut **diffgr : hasChanges** n’est pas spécifié, la logique de traitement DiffGram ignore cet élément et aucune mise à jour n’est effectuée.</span><span class="sxs-lookup"><span data-stu-id="15a18-147">Note that if the **diffgr:hasChanges** attribute is not specified, the DiffGram processing logic ignores this element and no updates are performed.</span></span>  
  
#### <a name="to-test-the-diffgram"></a><span data-ttu-id="15a18-148">Pour tester le DiffGram</span><span class="sxs-lookup"><span data-stu-id="15a18-148">To test the DiffGram</span></span>  
  
1.  <span data-ttu-id="15a18-149">Créez ces tables dans la base de données **tempdb** .</span><span class="sxs-lookup"><span data-stu-id="15a18-149">Create these tables in the **tempdb** database.</span></span>  
  
    ```  
    CREATE TABLE Cust(  
            CustomerID  nchar(5) Primary Key,  
            CompanyName nvarchar(40) NOT NULL ,  
            ContactName nvarchar(60) NULL)  
    GO  
  
    CREATE TABLE Ord(  
       OrderID    int Primary Key,  
       CustomerID nchar(5) Foreign Key REFERENCES Cust(CustomerID))  
    GO  
    ```  
  
2.  <span data-ttu-id="15a18-150">Ajoutez les exemples de données suivants :</span><span class="sxs-lookup"><span data-stu-id="15a18-150">Add this sample data:</span></span>  
  
    ```  
    INSERT INTO Cust(CustomerID, CompanyName, ContactName) VALUES  
         (N'ALFKI', N'Alfreds Futterkiste', N'Maria Anders')  
    INSERT INTO Cust(CustomerID, CompanyName, ContactName) VALUES  
         (N'ANATR', N'Ana Trujillo Emparedados y helados', N'Ana Trujillo')  
    INSERT INTO Cust(CustomerID, CompanyName, ContactName) VALUES  
         (N'ANTON', N'Antonio Moreno Taquer??a', N'Antonio Moreno')  
  
    INSERT INTO Ord(OrderID, CustomerID) VALUES(1, N'ALFKI')  
    INSERT INTO Ord(OrderID, CustomerID) VALUES(2, N'ANATR')  
    INSERT INTO Ord(OrderID, CustomerID) VALUES(3, N'ANTON')  
    ```  
  
3.  <span data-ttu-id="15a18-151">Copiez le DiffGram ci-dessus et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="15a18-151">Copy the DiffGram above and paste it into a text file.</span></span> <span data-ttu-id="15a18-152">Enregistrez le fichier sous le nom MyDiffGram.xml dans le même dossier qu'à l'étape précédente.</span><span class="sxs-lookup"><span data-stu-id="15a18-152">Save the file as MyDiffGram.xml in the same folder used in the previous step.</span></span>  
  
4.  <span data-ttu-id="15a18-153">Copiez le DiffGramSchema fourni plus haut dans cette rubrique et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="15a18-153">Copy the DiffGramSchema provided earlier in this topic and paste it into a text file.</span></span> <span data-ttu-id="15a18-154">Enregistrez le fichier sous le nom DiffGramSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="15a18-154">Save the file as DiffGramSchema.xml.</span></span>  
  
5.  <span data-ttu-id="15a18-155">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le DiffGram.</span><span class="sxs-lookup"><span data-stu-id="15a18-155">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the DiffGram.</span></span>  
  
     <span data-ttu-id="15a18-156">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="15a18-156">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
## <a name="d-inserting-updating-and-deleting-records-by-using-a-diffgram"></a><span data-ttu-id="15a18-157">D.</span><span class="sxs-lookup"><span data-stu-id="15a18-157">D.</span></span> <span data-ttu-id="15a18-158">Insertion, mise à jour et suppression d'enregistrements à l'aide d'un DiffGram</span><span class="sxs-lookup"><span data-stu-id="15a18-158">Inserting, updating, and deleting records by using a DiffGram</span></span>  
 <span data-ttu-id="15a18-159">Dans cet exemple, un DiffGram relativement complexe est utilisé pour effectuer des opérations d'insertion, de mise à jour et de suppression.</span><span class="sxs-lookup"><span data-stu-id="15a18-159">In this example, a relatively complex DiffGram is used to perform insert, update, and delete operations.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql" sql:mapping-schema="DiffGramSchema.xml">  
  <diffgr:diffgram   
         xmlns:msdata="urn:schemas-microsoft-com:xml-msdata"   
         xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1">  
    <DataInstance>  
      <Customer diffgr:id="Customer2" msdata:rowOrder="1"   
                diffgr:hasChanges="modified"   
                CustomerID="ANATR">  
          <CompanyName>Bottom Dollar Markets</CompanyName>  
          <ContactName>Elizabeth Lincoln</ContactName>  
          <Order diffgr:id="Order2" msdata:rowOrder="1"   
               msdata:hiddenCustomerID="ANATR"   
               CustomerID="ANATR" OrderID="2"/>  
      </Customer>  
  
      <Customer diffgr:id="Customer3" msdata:rowOrder="2"   
                CustomerID="ANTON">  
         <CompanyName>Chop-suey Chinese</CompanyName>  
         <ContactName>Yang Wang</ContactName>  
         <Order diffgr:id="Order3" msdata:rowOrder="2"   
               msdata:hiddenCustomerID="ANTON"   
               CustomerID="ANTON" OrderID="3"/>  
      </Customer>  
      <Customer diffgr:id="Customer4" msdata:rowOrder="3"   
                diffgr:hasChanges="inserted"   
                CustomerID="AROUT">  
         <CompanyName>Around the Horn</CompanyName>  
         <ContactName>Thomas Hardy</ContactName>  
         <Order diffgr:id="Order4" msdata:rowOrder="3"   
                diffgr:hasChanges="inserted"   
                msdata:hiddenCustomerID="AROUT"   
               CustomerID="AROUT" OrderID="4"/>  
      </Customer>  
    </DataInstance>  
    <diffgr:before>  
      <Order diffgr:id="Order1" msdata:rowOrder="0"   
             msdata:hiddenCustomerID="ALFKI"   
             CustomerID="ALFKI" OrderID="1"/>  
      <Customer diffgr:id="Customer1" msdata:rowOrder="0"   
                CustomerID="ALFKI">  
        <CompanyName>Alfreds Futterkiste</CompanyName>  
        <ContactName>Maria Anders</ContactName>  
      </Customer>  
      <Customer diffgr:id="Customer2" msdata:rowOrder="1"   
                CustomerID="ANATR">  
        <CompanyName>Ana Trujillo Emparedados y helados</CompanyName>  
        <ContactName>Ana Trujillo</ContactName>  
      </Customer>  
    </diffgr:before>  
  </diffgr:diffgram>  
</ROOT>  
```  
  
 <span data-ttu-id="15a18-160">La logique du DiffGram traite ce DiffGram comme suit :</span><span class="sxs-lookup"><span data-stu-id="15a18-160">The DiffGram logic processes this DiffGram as follows:</span></span>  
  
-   <span data-ttu-id="15a18-161">Conformément à la logique de traitement DiffGram, tous les éléments de niveau supérieur du **\<before>** bloc sont mappés aux tables correspondantes, comme décrit dans le schéma de mappage.</span><span class="sxs-lookup"><span data-stu-id="15a18-161">In accordance with DiffGram processing logic, all the top-level elements in the **\<before>** block map to corresponding tables, as described in the mapping schema.</span></span>  
  
-   <span data-ttu-id="15a18-162">Le **\<before>** bloc a un **\<Order>** élément (**dffgr : ID = "Order1"**) et un **\<Customer>** élément (**diffgr : ID = "Customer1"**) pour lequel il n’existe aucun élément correspondant dans le **\<DataInstance>** bloc (avec le même ID).</span><span class="sxs-lookup"><span data-stu-id="15a18-162">The **\<before>** block has an **\<Order>** element (**dffgr:id="Order1"**) and a **\<Customer>** element (**diffgr:id="Customer1"**) for which there is no corresponding element in the **\<DataInstance>** block (with the same ID).</span></span> <span data-ttu-id="15a18-163">Cela indique une opération de suppression et les enregistrements sont supprimés des tables Cust et Ord.</span><span class="sxs-lookup"><span data-stu-id="15a18-163">This indicates a delete operation, and the records are deleted from the Cust and Ord tables.</span></span>  
  
-   <span data-ttu-id="15a18-164">Le **\<before>** bloc possède un **\<Customer>** élément (**diffgr : ID = "Customer2"**) pour lequel il existe un **\<Customer>** élément correspondant dans le **\<DataInstance>** bloc (avec le même ID).</span><span class="sxs-lookup"><span data-stu-id="15a18-164">The **\<before>** block has a **\<Customer>** element (**diffgr:id="Customer2"**) for which there is a corresponding **\<Customer>** element in the **\<DataInstance>** block (with the same ID).</span></span> <span data-ttu-id="15a18-165">L’élément dans le **\<DataInstance>** bloc spécifie **diffgr : hasChanges = "modified"**.</span><span class="sxs-lookup"><span data-stu-id="15a18-165">The element in the **\<DataInstance>** block specifies **diffgr:hasChanges="modified"**.</span></span> <span data-ttu-id="15a18-166">Il s’agit d’une opération de mise à jour dans laquelle, pour le client ANATR, les informations CompanyName et ContactName sont mises à jour dans la table Cust à l’aide des valeurs spécifiées dans le **\<DataInstance>** bloc.</span><span class="sxs-lookup"><span data-stu-id="15a18-166">This is an update operation in which for customer ANATR, the CompanyName and ContactName information is updated in the Cust table using values that are specified in the **\<DataInstance>** block.</span></span>  
  
-   <span data-ttu-id="15a18-167">Le **\<DataInstance>** bloc possède un **\<Customer>** élément (**diffgr : ID = "customer3"**) et un **\<Order>** élément (**diffgr : ID = "Order3"**).</span><span class="sxs-lookup"><span data-stu-id="15a18-167">The **\<DataInstance>** block has a **\<Customer>** element (**diffgr:id="Customer3"**) and an **\<Order>** element (**diffgr:id="Order3"**).</span></span> <span data-ttu-id="15a18-168">Aucun de ces éléments ne spécifie l’attribut **diffgr : hasChanges** .</span><span class="sxs-lookup"><span data-stu-id="15a18-168">Neither of these elements specify the **diffgr:hasChanges** attribute.</span></span> <span data-ttu-id="15a18-169">Par conséquent, la logique de traitement du DiffGram ignore ces éléments.</span><span class="sxs-lookup"><span data-stu-id="15a18-169">Therefore, the DiffGram processing logic ignores these elements.</span></span>  
  
-   <span data-ttu-id="15a18-170">Le **\<DataInstance>** bloc possède un **\<Customer>** élément (**diffgr : ID = "Customer4"**) et un **\<Order>** élément (**diffgr : ID = "Order4"**) pour lequel il n’y a pas d’éléments correspondants dans le \<before> bloc.</span><span class="sxs-lookup"><span data-stu-id="15a18-170">The **\<DataInstance>** block has a **\<Customer>** element (**diffgr:id="Customer4"**) and an **\<Order>** element (**diffgr:id="Order4"**) for which there are no corresponding elements in the \<before> block.</span></span> <span data-ttu-id="15a18-171">Ces éléments dans le **\<DataInstance>** bloc spécifient **diffgr : hasChanges = "inserted"**.</span><span class="sxs-lookup"><span data-stu-id="15a18-171">These elements in the **\<DataInstance>** block specify **diffgr:hasChanges="inserted"**.</span></span> <span data-ttu-id="15a18-172">Par conséquent, un nouvel enregistrement est ajouté dans les tables Cust et Ord.</span><span class="sxs-lookup"><span data-stu-id="15a18-172">Therefore, a new record is added in the Cust table and in the Ord table.</span></span>  
  
#### <a name="to-test-the-diffgram"></a><span data-ttu-id="15a18-173">Pour tester le DiffGram</span><span class="sxs-lookup"><span data-stu-id="15a18-173">To test the DiffGram</span></span>  
  
1.  <span data-ttu-id="15a18-174">Créez les tables suivantes dans la base de données **tempdb** .</span><span class="sxs-lookup"><span data-stu-id="15a18-174">Create the following tables in the **tempdb** database.</span></span>  
  
    ```  
    CREATE TABLE Cust(  
            CustomerID  nchar(5) Primary Key,  
            CompanyName nvarchar(40) NOT NULL ,  
            ContactName nvarchar(60) NULL)  
    GO  
  
    CREATE TABLE Ord(  
       OrderID    int Primary Key,  
       CustomerID nchar(5) Foreign Key REFERENCES Cust(CustomerID))  
    GO  
    ```  
  
2.  <span data-ttu-id="15a18-175">Ajoutez les exemples de données suivants :</span><span class="sxs-lookup"><span data-stu-id="15a18-175">Add this sample data:</span></span>  
  
    ```  
    INSERT INTO Cust(CustomerID, CompanyName, ContactName) VALUES  
         (N'ALFKI', N'Alfreds Futterkiste', N'Maria Anders')  
    INSERT INTO Cust(CustomerID, CompanyName, ContactName) VALUES  
         (N'ANATR', N'Ana Trujillo Emparedados y helados', N'Ana Trujillo')  
    INSERT INTO Cust(CustomerID, CompanyName, ContactName) VALUES  
         (N'ANTON', N'Antonio Moreno Taquer??a', N'Antonio Moreno')  
  
    INSERT INTO Ord(OrderID, CustomerID) VALUES(1, N'ALFKI')  
    INSERT INTO Ord(OrderID, CustomerID) VALUES(2, N'ANATR')  
    INSERT INTO Ord(OrderID, CustomerID) VALUES(3, N'ANTON')  
    ```  
  
3.  <span data-ttu-id="15a18-176">Copiez le DiffGram ci-dessus et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="15a18-176">Copy the DiffGram above and paste it into a text file.</span></span> <span data-ttu-id="15a18-177">Enregistrez le fichier sous le nom MyDiffGram.xml dans le même dossier qu'à l'étape précédente.</span><span class="sxs-lookup"><span data-stu-id="15a18-177">Save the file as MyDiffGram.xml in the same folder used in the previous step.</span></span>  
  
4.  <span data-ttu-id="15a18-178">Copiez le DiffGramSchema fourni plus haut dans cette rubrique et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="15a18-178">Copy the DiffGramSchema provided earlier in this topic and paste it into a text file.</span></span> <span data-ttu-id="15a18-179">Enregistrez le fichier sous le nom DiffGramSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="15a18-179">Save the file as DiffGramSchema.xml.</span></span>  
  
5.  <span data-ttu-id="15a18-180">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le DiffGram.</span><span class="sxs-lookup"><span data-stu-id="15a18-180">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the DiffGram.</span></span>  
  
     <span data-ttu-id="15a18-181">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="15a18-181">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
## <a name="e-applying-updates-by-using-a-diffgram-with-the-diffgrparentid-annotation"></a><span data-ttu-id="15a18-182">E.</span><span class="sxs-lookup"><span data-stu-id="15a18-182">E.</span></span> <span data-ttu-id="15a18-183">Application de mises à jour à l'aide d'un DiffGram avec l'annotation diffgr:parentID</span><span class="sxs-lookup"><span data-stu-id="15a18-183">Applying updates by using a DiffGram with the diffgr:parentID annotation</span></span>  
 <span data-ttu-id="15a18-184">Cet exemple montre comment l’annotation **ParentId** spécifiée dans le **\<before>** bloc du DiffGram est utilisée pour appliquer les mises à jour.</span><span class="sxs-lookup"><span data-stu-id="15a18-184">This example illustrates how the **parentID** annotation that is specified in the **\<before>** block of the DiffGram is used in applying the updates.</span></span>  
  
```  
<NewDataSet />  
<diffgr:before>  
   <Order diffgr:id="Order1" msdata:rowOrder="0" OrderID="2" />  
   <Order diffgr:id="Order3" msdata:rowOrder="2" OrderID="4" />  
  
   <OrderDetail diffgr:id="OrderDetail1"   
                diffgr:parentId="Order1"   
                msdata:rowOrder="0"   
                ProductID="13"   
                OrderID="2" />  
   <OrderDetail diffgr:id="OrderDetail3"   
                diffgr:parentId="Order3"  
                ProductID="77"  
                OrderID="4"/>  
</diffgr:before>  
</diffgr:diffgram>  
```  
  
 <span data-ttu-id="15a18-185">Ce DiffGram spécifie une opération de suppression, car il n’existe qu’un seul **\<before>** bloc.</span><span class="sxs-lookup"><span data-stu-id="15a18-185">This DiffGram specifies a delete operation because there is only a **\<before>** block.</span></span> <span data-ttu-id="15a18-186">Dans le DiffGram, l’annotation **ParentId** est utilisée pour spécifier une relation parent-enfant entre les commandes et les détails de commande.</span><span class="sxs-lookup"><span data-stu-id="15a18-186">In the DiffGram, the **parentID** annotation is used to specify a parent-child relationship between the orders and order details.</span></span> <span data-ttu-id="15a18-187">Lorsque SQLXML supprime des enregistrements, il les supprime de la table enfant qui est identifiée par cette relation, puis supprime les enregistrements de la table parente correspondante.</span><span class="sxs-lookup"><span data-stu-id="15a18-187">When SQLXML deletes the records, it deletes records from the child table that is identified by this relationship and then deletes the records from the corresponding parent table.</span></span>  
  
  
