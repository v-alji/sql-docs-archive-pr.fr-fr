---
title: Exécution d’un DiffGram à l’aide de classes managées SQLXML | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- DiffGrams [SQLXML], Managed Classes
- SQLXML Managed Classes, DiffGrams
- Managed Classes [SQLXML], DiffGrams
- SQLXML, Managed Classes
ms.assetid: 81c687ca-8c9f-4f58-801f-8dabcc508a06
author: rothja
ms.author: jroth
ms.openlocfilehash: f36127c37eea73a2872d4bf0aef7172a88e430a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610547"
---
# <a name="executing-a-diffgram-by-using-sqlxml-managed-classes"></a><span data-ttu-id="1b223-102">Exécution d'un DiffGram à l'aide des classes managées SQLXML</span><span class="sxs-lookup"><span data-stu-id="1b223-102">Executing a DiffGram by Using SQLXML Managed Classes</span></span>
  <span data-ttu-id="1b223-103">Cet exemple montre comment exécuter un fichier DiffGram dans l' [!INCLUDE[msCoName](../../../includes/msconame-md.md)] environnement .NET Framework pour appliquer des mises à jour de données à des [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] tables à l’aide de classes managées SQLXML (Microsoft. Data. SQLXML).</span><span class="sxs-lookup"><span data-stu-id="1b223-103">This example shows how to execute a DiffGram file in the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework environment to apply data updates to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] tables using SQLXML Managed Classes (Microsoft.Data.SqlXml).</span></span>  
  
 <span data-ttu-id="1b223-104">Dans cet exemple, le DiffGram met à jour les informations sur les clients (CompanyName et ContactName) pour le client ALFKI.</span><span class="sxs-lookup"><span data-stu-id="1b223-104">In this example, the DiffGram updates customer information (CompanyName and ContactName) for customer ALFKI.</span></span>  
  
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
  
 <span data-ttu-id="1b223-105">Le **\<before>** bloc comprend un **\<Customer>** élément (**diffgr : ID = "Customer1"**).</span><span class="sxs-lookup"><span data-stu-id="1b223-105">The **\<before>** block includes a **\<Customer>** element (**diffgr:id="Customer1"**).</span></span> <span data-ttu-id="1b223-106">Le **\<DataInstance>** bloc comprend l' **\<Customer>** élément correspondant avec le même **ID**. L' **\<customer>** élément dans le **\<NewDataSet>** spécifie également **diffgr : hasChanges = "modified"**.</span><span class="sxs-lookup"><span data-stu-id="1b223-106">The **\<DataInstance>** block includes the corresponding **\<Customer>** element with same **id**. The **\<customer>** element in the **\<NewDataSet>** also specifies **diffgr:hasChanges="modified"**.</span></span> <span data-ttu-id="1b223-107">Cela indique une opération de mise à jour et l'enregistrement de client de la table Cust est mis à jour en conséquence.</span><span class="sxs-lookup"><span data-stu-id="1b223-107">This indicates an update operation, and the customer record in the Cust table is updated accordingly.</span></span> <span data-ttu-id="1b223-108">Notez que si l’attribut **diffgr : hasChanges** n’est pas spécifié, la logique de traitement DiffGram ignore cet élément et aucune mise à jour n’est effectuée.</span><span class="sxs-lookup"><span data-stu-id="1b223-108">Note that if the **diffgr:hasChanges** attribute is not specified, the DiffGram processing logic ignores this element and no updates are performed.</span></span>  
  
 <span data-ttu-id="1b223-109">Voici le code d’une application didacticiel C# qui montre comment utiliser les classes managées SQLXML pour exécuter le DiffGram ci-dessus et mettre à jour deux tables (cust, ORD) que vous allez également créer dans la base de données **tempdb** .</span><span class="sxs-lookup"><span data-stu-id="1b223-109">The following is code for a C# tutorial application that shows how to use the SQLXML Managed Classes to execute the above DiffGram and update two tables (Cust, Ord) you will also create in the **tempdb** database.</span></span>  
  
```  
using System;  
using System.Data;  
using Microsoft.Data.SqlXml;  
using System.IO;  
class Test  
{  
   static string ConnString = "Provider=SQLOLEDB;Server=MyServer;database=tempdb;Integrated Security=SSPI;";  
   public static int testParams()  
   {  
      SqlXmlAdapter ad;  
      // Need a memory stream to hold diff gram temporarily  
      MemoryStream ms = new MemoryStream();  
      SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
      cmd.RootTag = "ROOT";  
      cmd.CommandStream = new FileStream("MyDiffgram.xml", FileMode.Open, FileAccess.Read);  
      cmd.CommandType = SqlXmlCommandType.DiffGram;  
      cmd.SchemaPath = "DiffGramSchema.xml";  
      // Load data set  
      DataSet ds = new DataSet();  
      ad = new SqlXmlAdapter(cmd);  
      ad.Fill(ds);  
      ad.Update(ds);  
      return 0;  
   }  
   public static int Main(String[] args)  
   {  
      testParams();  
      return 0;  
   }  
}  
```  
  
### <a name="to-test-the-application"></a><span data-ttu-id="1b223-110">Pour tester l'application</span><span class="sxs-lookup"><span data-stu-id="1b223-110">To test the application</span></span>  
  
1.  <span data-ttu-id="1b223-111">Vérifiez que le .NET Framework est installé sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="1b223-111">Ensure that the .NET Framework is installed on your computer.</span></span>  
  
2.  <span data-ttu-id="1b223-112">Enregistrez le schéma XSD suivant (DiffGramSchema.xml) dans un dossier :</span><span class="sxs-lookup"><span data-stu-id="1b223-112">Save the following XSD schema (DiffGramSchema.xml) in a folder:</span></span>  
  
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
  
3.  <span data-ttu-id="1b223-113">Créez ces tables dans la base de données **tempdb** .</span><span class="sxs-lookup"><span data-stu-id="1b223-113">Create these tables in the **tempdb** database.</span></span>  
  
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
  
4.  <span data-ttu-id="1b223-114">Ajoutez les exemples de données suivants :</span><span class="sxs-lookup"><span data-stu-id="1b223-114">Add this sample data:</span></span>  
  
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
  
5.  <span data-ttu-id="1b223-115">Copiez le DiffGram ci-dessus et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="1b223-115">Copy the DiffGram above and paste it into a text file.</span></span> <span data-ttu-id="1b223-116">Enregistrez le fichier sous le nom MyDiffGram.xml dans le même dossier qu'à l'étape 1.</span><span class="sxs-lookup"><span data-stu-id="1b223-116">Save the file as MyDiffGram.xml in the same folder used in step 1.</span></span>  
  
6.  <span data-ttu-id="1b223-117">Enregistrez le code C# (DiffgramSample.cs) fourni ci-dessus dans le même dossier que celui dans lequel DiffGramSchema.xml et MyDiffGram.xml ont été stockés dans les étapes précédentes.</span><span class="sxs-lookup"><span data-stu-id="1b223-117">Save the C# code (DiffgramSample.cs) that is provided above in the same folder in which the DiffGramSchema.xml and MyDiffGram.xml were stored in previous steps.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1b223-118">Vous devrez remplacer le nom '`MyServer`' de l'instance [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] de la chaîne de connexion par le nom réel de votre instance installée de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1b223-118">You will need to update the name of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance in the connection string from '`MyServer`' to the actual name of your installed instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="1b223-119">Si vous stockez les fichiers dans un dossier différent, vous devrez modifier le code et spécifier le chemin d'accès approprié au répertoire pour le schéma de mappage.</span><span class="sxs-lookup"><span data-stu-id="1b223-119">If you store the files in a different folder, you will have to edit the code and specify the appropriate directory path for the mapping schema.</span></span>  
  
7.  <span data-ttu-id="1b223-120">Compilez le code.</span><span class="sxs-lookup"><span data-stu-id="1b223-120">Compile the code.</span></span> <span data-ttu-id="1b223-121">Pour compiler le code à l'invite de commandes, utilisez :</span><span class="sxs-lookup"><span data-stu-id="1b223-121">To compile the code at the command prompt, use:</span></span>  
  
    ```  
    csc /reference:Microsoft.Data.SqlXML.dll DiffgramSample.cs  
    ```  
  
     <span data-ttu-id="1b223-122">Un fichier exécutable (DiffgramSample.exe) est alors créé.</span><span class="sxs-lookup"><span data-stu-id="1b223-122">This creates an executable (DiffgramSample.exe).</span></span>  
  
8.  <span data-ttu-id="1b223-123">À l'invite de commandes, exécutez DiffgramSample.exe.</span><span class="sxs-lookup"><span data-stu-id="1b223-123">At the command prompt, execute DiffgramSample.exe.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b223-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1b223-124">See Also</span></span>  
 [<span data-ttu-id="1b223-125">Exemples DiffGram &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="1b223-125">DiffGram Examples &#40;SQLXML 4.0&#41;</span></span>](diffgram-examples-sqlxml-4-0.md)  
  
  
