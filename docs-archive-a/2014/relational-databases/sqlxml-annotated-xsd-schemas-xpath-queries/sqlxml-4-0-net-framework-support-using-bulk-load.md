---
title: Utilisation du chargement en masse SQLXML dans l’environnement .NET | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- SQLXML, XML Bulk Load
- XML Bulk Load [SQLXML], .NET environment
- .NET Framework [SQLXML], XML Bulk Load
- bulk load [SQLXML], .NET environment
ms.assetid: b85df83b-ba56-43bf-bcdf-b2a6fca43276
author: rothja
ms.author: jroth
ms.openlocfilehash: 6bd1c44a8b56bc5129aeb9843ed9ba814d45742a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706359"
---
# <a name="using-sqlxml-bulk-load-in-the-net-environment"></a><span data-ttu-id="283db-102">Utilisation du chargement en masse SQLXML dans l'environnement .NET</span><span class="sxs-lookup"><span data-stu-id="283db-102">Using SQLXML Bulk Load in the .NET Environment</span></span>
  <span data-ttu-id="283db-103">Cette rubrique explique comment exploiter la fonctionnalité de chargement en masse XML dans l'environnement .NET.</span><span class="sxs-lookup"><span data-stu-id="283db-103">This topic explains how the XML Bulk Load functionality can be used in the .NET environment.</span></span> <span data-ttu-id="283db-104">Pour plus d’informations sur le chargement en masse XML, consultez [exécution du chargement en masse de données xml &#40;SQLXML 4,0&#41;](bulk-load-xml/performing-bulk-load-of-xml-data-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="283db-104">For detailed information about XML Bulk Load, see [Performing Bulk Load of XML Data &#40;SQLXML 4.0&#41;](bulk-load-xml/performing-bulk-load-of-xml-data-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="283db-105">Pour utiliser l'objet COM de chargement en masse SQLXML depuis un environnement managé, vous devez ajouter une référence de projet à ce même objet.</span><span class="sxs-lookup"><span data-stu-id="283db-105">To use the SQLXML Bulk Load COM object from a managed environment, you need to add a project reference to this object.</span></span> <span data-ttu-id="283db-106">Ceci génère une interface de wrapper managé autour de l'objet COM de chargement en masse.</span><span class="sxs-lookup"><span data-stu-id="283db-106">This generates a managed wrapper interface around the Bulk Load COM object.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="283db-107">Le chargement en masse XML managé ne fonctionne pas avec les flux managés et nécessite l'intervention d'un wrapper autour des flux natifs.</span><span class="sxs-lookup"><span data-stu-id="283db-107">Managed XML Bulk load does not work with managed streams and requires a wrapper around native streams.</span></span> <span data-ttu-id="283db-108">Le composant de chargement en masse SQLXML ne s'exécutera pas dans un environnement multithread (attribut '[MTAThread]').</span><span class="sxs-lookup"><span data-stu-id="283db-108">The SQLXML Bulk Load component will not run in a multi-threaded environment ('[MTAThread]' attribute).</span></span> <span data-ttu-id="283db-109">Si vous tentez d’exécuter le composant de chargement en masse dans un environnement multithreads, vous recevez une exception InvalidCastException avec les informations supplémentaires suivantes : « échec de la commande «QueryInterface pour l’interface SQLXMLBULKLOADLib. ISQLXMLBulkLoad ».</span><span class="sxs-lookup"><span data-stu-id="283db-109">If you attempt to run the Bulk Load component in a multi-thread environment, you get an InvalidCastException exception with the following additional information: "QueryInterface for interface SQLXMLBULKLOADLib.ISQLXMLBulkLoad failed."</span></span> <span data-ttu-id="283db-110">La solution de contournement consiste à rendre l’objet qui contient l’objet de chargement en masse accessible à un seul thread (par exemple, en utilisant l’attribut **[STAThread]** comme indiqué dans l’exemple).</span><span class="sxs-lookup"><span data-stu-id="283db-110">The workaround is to make the object that contains the Bulk Load object single-thread accessible (for example, by using the **[STAThread]** attribute as shown in the sample).</span></span>  
  
 <span data-ttu-id="283db-111">Cette rubrique propose un exemple d'application C# fonctionnel pour les données XML de chargement en masse dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="283db-111">This topic provides a working C# sample application to bulk load XML data in the database.</span></span> <span data-ttu-id="283db-112">Pour créer un exemple fonctionnel, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="283db-112">To create a working sample, follow these steps:</span></span>  
  
1.  <span data-ttu-id="283db-113">Créez les tables suivantes :</span><span class="sxs-lookup"><span data-stu-id="283db-113">Create the following tables:</span></span>  
  
    ```  
    CREATE TABLE Ord (  
             OrderID     int identity(1,1)  PRIMARY KEY,  
             CustomerID  varchar(5))  
    GO  
    CREATE TABLE Product (  
             ProductID   int identity(1,1) PRIMARY KEY,  
             ProductName varchar(20))  
    GO  
    CREATE TABLE OrderDetail (  
           OrderID     int FOREIGN KEY REFERENCES Ord(OrderID),  
           ProductID   int FOREIGN KEY REFERENCES Product(ProductID),  
                       CONSTRAINT OD_key PRIMARY KEY (OrderID, ProductID))  
    GO  
    ```  
  
2.  <span data-ttu-id="283db-114">Enregistrez le schéma suivant dans un fichier (schema.xml) :</span><span class="sxs-lookup"><span data-stu-id="283db-114">Save the following schema in a file (schema.xml):</span></span>  
  
    ```  
    <xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
                xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
    <xsd:annotation>  
      <xsd:appinfo>  
        <sql:relationship name="OrderOD"  
              parent="Ord"  
              parent-key="OrderID"  
              child="OrderDetail"  
              child-key="OrderID" />  
  
        <sql:relationship name="ODProduct"  
              parent="OrderDetail"  
              parent-key="ProductID"  
              child="Product"  
              child-key="ProductID"   
              inverse="true"/>  
      </xsd:appinfo>  
    </xsd:annotation>  
  
      <xsd:element name="Order" sql:relation="Ord"   
                                sql:key-fields="OrderID" >  
       <xsd:complexType>  
         <xsd:sequence>  
            <xsd:element name="Product" sql:relation="Product"   
                         sql:key-fields="ProductID"  
                         sql:relationship="OrderOD ODProduct">  
              <xsd:complexType>  
                 <xsd:attribute name="ProductID" type="xsd:int" />  
                 <xsd:attribute name="ProductName" type="xsd:string" />  
              </xsd:complexType>  
            </xsd:element>  
         </xsd:sequence>  
            <xsd:attribute name="OrderID"   type="xsd:integer" />   
            <xsd:attribute name="CustomerID"   type="xsd:string" />  
        </xsd:complexType>  
      </xsd:element>  
    </xsd:schema>  
    ```  
  
3.  <span data-ttu-id="283db-115">Enregistrez l'exemple de document XML suivant dans un fichier (data.xml) :</span><span class="sxs-lookup"><span data-stu-id="283db-115">Save the following sample XML document in a file (data.xml):</span></span>  
  
    ```  
    <ROOT>    
      <Order OrderID="11" CustomerID="ALFKI">  
        <Product ProductID="11" ProductName="Chai" />  
        <Product ProductID="22" ProductName="Chang" />  
      </Order>  
      <Order OrderID="22" CustomerID="ANATR">  
         <Product ProductID="33" ProductName="Aniseed Syrup" />  
        <Product ProductID="44" ProductName="Gumbo Mix" />  
      </Order>  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="283db-116">Démarrez Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="283db-116">Start Visual Studio.</span></span>  
  
5.  <span data-ttu-id="283db-117">Créez une application console C#.</span><span class="sxs-lookup"><span data-stu-id="283db-117">Create a C# console application.</span></span>  
  
6.  <span data-ttu-id="283db-118">Dans le menu **projet** , sélectionnez **Ajouter une référence**.</span><span class="sxs-lookup"><span data-stu-id="283db-118">From the **Project** menu, select **Add Reference**.</span></span>  
  
7.  <span data-ttu-id="283db-119">Sous l’onglet **com** , sélectionnez **bibliothèque de types Microsoft SQLXML Bulkload 4,0** (xblkld4.dll), puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="283db-119">In the **COM** tab, select **Microsoft SQLXML Bulkload 4.0 Type Library** (xblkld4.dll) and click **OK**.</span></span> <span data-ttu-id="283db-120">Vous verrez l’assembly **Interop. SQLXMLBULKLOADLib** créé dans le projet.</span><span class="sxs-lookup"><span data-stu-id="283db-120">You will see the **Interop.SQLXMLBULKLOADLib** assembly created in the project.</span></span>  
  
8.  <span data-ttu-id="283db-121">Remplacez la méthode Main() par le code ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="283db-121">Replace the Main() method with the following code.</span></span> <span data-ttu-id="283db-122">Mettez à jour la propriété **ConnectionString** et le chemin d’accès du fichier vers le schéma et les fichiers de données.</span><span class="sxs-lookup"><span data-stu-id="283db-122">Update the **ConnectionString** property and the file path to the schema and data files.</span></span>  
  
    ```  
    [STAThread]  
       static void Main(string[] args)  
       {     
             try  
             {  
                SQLXMLBULKLOADLib.SQLXMLBulkLoad4Class objBL = new SQLXMLBULKLOADLib.SQLXMLBulkLoad4Class();  
                objBL.ConnectionString = "Provider=sqloledb;server=server;database=databaseName;integrated security=SSPI";  
                objBL.ErrorLogFile = "error.xml";  
                objBL.KeepIdentity = false;  
                objBL.Execute ("schema.xml","data.xml");  
             }  
             catch(Exception e)  
             {  
             Console.WriteLine(e.ToString());  
             }  
       }  
    ```  
  
9. <span data-ttu-id="283db-123">Pour charger le code XML dans la table que vous avez créée, créez et exécutez le projet.</span><span class="sxs-lookup"><span data-stu-id="283db-123">To load the XML in the table you created, build and run the project.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="283db-124">La référence au composant de chargement en masse (xblkld4.dll) peut également être ajoutée à l'aide de l'outil tlbimp.exe disponible dans le cadre de l'infrastructure .NET.</span><span class="sxs-lookup"><span data-stu-id="283db-124">The reference to the Bulk Load component (xblkld4.dll) can also be added using the tlbimp.exe tool, which is available as part of .NET framework.</span></span> <span data-ttu-id="283db-125">Cet outil crée un wrapper managé pour la DLL native (xblkld4.dll) qui peut être utilisé ensuite dans tous les projets .NET.</span><span class="sxs-lookup"><span data-stu-id="283db-125">This tool creates a managed wrapper for the native DLL (xblkld4.dll), which can then be used in any .NET project.</span></span> <span data-ttu-id="283db-126">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="283db-126">For example:</span></span>  
  
    ```  
    c:\>tlbimp xblkld4.dll  
    ```  
  
     <span data-ttu-id="283db-127">Cet exemple crée la DLL de wrapper managé (SQLXMLBULKLOADLib.dll) que vous pouvez utiliser dans le projet .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="283db-127">This creates the managed wrapper DLL (SQLXMLBULKLOADLib.dll) that you can use in the .NET Framework project.</span></span> <span data-ttu-id="283db-128">Dans le .NET Framework, vous ajoutez une référence de projet à toutes les nouvelles DLL que vous créez.</span><span class="sxs-lookup"><span data-stu-id="283db-128">In the .NET Framework, you add project reference to the newly created DLL.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="283db-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="283db-129">See Also</span></span>  
 [<span data-ttu-id="283db-130">Exécution du chargement en masse de données XML &#40;SQLXML 4.0&#41;</span><span class="sxs-lookup"><span data-stu-id="283db-130">Performing Bulk Load of XML Data &#40;SQLXML 4.0&#41;</span></span>](bulk-load-xml/performing-bulk-load-of-xml-data-sqlxml-4-0.md)  
  
  
