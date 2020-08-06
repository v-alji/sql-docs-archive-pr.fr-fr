---
title: Accès à la fonctionnalité SQLXML dans l’environnement .NET | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- Managed Classes [SQLXML], accessing SQLXML functionality
- SQLXML Managed Classes, accessing SQLXML functionality
- DiffGrams [SQLXML], accessing SQLXML functionality
- .NET Framework [SQLXML], accessing SQLXML functionality
ms.assetid: 74744535-2945-414d-9a5b-7e8cc363953a
author: rothja
ms.author: jroth
ms.openlocfilehash: a2ba0a54310833c0a1a1315aa94d78fe5650d480
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610544"
---
# <a name="accessing-sqlxml-functionality-in-the-net-environment"></a><span data-ttu-id="18779-102">Accès aux fonctionnalités SQLXML dans l'environnement .NET</span><span class="sxs-lookup"><span data-stu-id="18779-102">Accessing SQLXML Functionality in the .NET Environment</span></span>
  <span data-ttu-id="18779-103">Dans cet exemple, vous pouvez voir les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="18779-103">This example shows:</span></span>  
  
-   <span data-ttu-id="18779-104">Comment utiliser [!INCLUDE[msCoName](../../../includes/msconame-md.md)] les classes managées SQLXML (Microsoft. Data. SQLXML) pour accéder à Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] dans l' [!INCLUDE[msCoName](../../../includes/msconame-md.md)] environnement .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="18779-104">How to use [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML Managed Classes (Microsoft.Data.SqlXml) to access Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework environment.</span></span>  
  
-   <span data-ttu-id="18779-105">Comment les DiffGrams générés dans l'environnement .NET Framework peuvent appliquer les mises à jour des données aux tables [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="18779-105">How DiffGrams that are generated in the .NET Framework environment can apply data updates to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] tables.</span></span>  
  
 <span data-ttu-id="18779-106">Dans cette application, une requête XPath est exécutée sur un schéma XSD.</span><span class="sxs-lookup"><span data-stu-id="18779-106">In this application, an XPath query is executed against an XSD schema.</span></span> <span data-ttu-id="18779-107">L’exécution de la requête XPath retourne un document XML constitué de données de contact (**FirstName**, **LastName**).</span><span class="sxs-lookup"><span data-stu-id="18779-107">The execution of the XPath query returns an XML document that consists of contact data (**FirstName**, **LastName**).</span></span> <span data-ttu-id="18779-108">L'application charge le document XML dans le dataset de l'environnement .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="18779-108">The application loads the XML document in the dataset in the .NET Framework environment.</span></span> <span data-ttu-id="18779-109">Les données du dataset sont modifiées : le prénom du contact est changé en « Susan » pour le premier contact du dataset.</span><span class="sxs-lookup"><span data-stu-id="18779-109">The data in the dataset is modified: the contact's first name is changed to "Susan" for the first contact in the dataset.</span></span> <span data-ttu-id="18779-110">Le DiffGram est généré à partir du dataset, puis la mise à jour spécifiée dans le DiffGram (modification du prénom de l'employé) est appliquée à la table Person.Contact.</span><span class="sxs-lookup"><span data-stu-id="18779-110">The DiffGram is generated from the dataset, and the update that is specified in the DiffGram (the change in the employee's first name) is then applied to the Person.Contact table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="18779-111">Dans le code, vous devez fournir le nom de l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] dans la chaîne de connexion.</span><span class="sxs-lookup"><span data-stu-id="18779-111">In the code, you must provide the name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span>  
  
```  
using System;  
using System.Data;  
using Microsoft.Data.SqlXml;  
using System.IO;  
class Test  
{  
   static string ConnString = "Provider=SQLOLEDB;Server=SqlServerName;database=AdventureWorks;Integrated Security=SSPI;";  
   public static int testParams()  
   {  
      DataRow row;  
      SqlXmlAdapter ad;  
      //need a memory stream to hold diff gram temporarily  
      MemoryStream ms = new MemoryStream();  
      SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
      cmd.RootTag = "ROOT";  
      cmd.CommandText = "Con";  
      cmd.CommandType = SqlXmlCommandType.XPath;  
      cmd.SchemaPath = "MySchema.xml";  
      //load data set  
      DataSet ds = new DataSet();  
      ad = new SqlXmlAdapter(cmd);  
      ad.Fill(ds);  
      row = ds.Tables["Con"].Rows[0];  
      row["FName"] = "Susan";  
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
  
 <span data-ttu-id="18779-112">**Pour tester l'exemple :**</span><span class="sxs-lookup"><span data-stu-id="18779-112">**To test the example:**</span></span>  
  
 <span data-ttu-id="18779-113">Pour tester cet exemple, le [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework doit être installé sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="18779-113">To test this example, you must have the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework installed on your computer.</span></span>  
  
1.  <span data-ttu-id="18779-114">Enregistrez ce schéma XSD (MySchema.xml) dans un dossier :</span><span class="sxs-lookup"><span data-stu-id="18779-114">Save this XSD schema (MySchema.xml) in a folder:</span></span>  
  
    ```  
    <xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
                xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
      <xsd:element name="Con" sql:relation="Person.Contact" >  
       <xsd:complexType>  
         <xsd:sequence>  
            <xsd:element name="FName"    
                         sql:field="FirstName"   
                         type="xsd:string" />   
            <xsd:element name="LName"    
                         sql:field="LastName"    
                         type="xsd:string" />  
         </xsd:sequence>  
         <xsd:attribute name="ContactID" type="xsd:integer" />  
        </xsd:complexType>  
      </xsd:element>  
    </xsd:schema>  
    ```  
  
2.  <span data-ttu-id="18779-115">Enregistrez le code C# (DocSample.cs) fourni dans cet exemple dans le même dossier que celui du schéma.</span><span class="sxs-lookup"><span data-stu-id="18779-115">Save the C# code (DocSample.cs) provided in this example in the same folder in which the schema is stored.</span></span> <span data-ttu-id="18779-116">(Si vous stockez les fichiers dans un dossier différent, vous devrez modifier le code et spécifier le chemin d'accès approprié au répertoire pour le schéma de mappage.)</span><span class="sxs-lookup"><span data-stu-id="18779-116">(If you store the files in a different folder, you will have to edit the code and specify the appropriate directory path for the mapping schema.)</span></span>  
  
3.  <span data-ttu-id="18779-117">Compilez le code.</span><span class="sxs-lookup"><span data-stu-id="18779-117">Compile the code.</span></span> <span data-ttu-id="18779-118">Pour compiler le code à l'invite de commandes, utilisez :</span><span class="sxs-lookup"><span data-stu-id="18779-118">To compile the code at the command prompt, use:</span></span>  
  
    ```  
    csc /reference:Microsoft.Data.SqlXML.dll DocSample.cs  
    ```  
  
     <span data-ttu-id="18779-119">Un fichier exécutable (DocSample.exe) est alors créé.</span><span class="sxs-lookup"><span data-stu-id="18779-119">This creates an executable (DocSample.exe).</span></span>  
  
 <span data-ttu-id="18779-120">À l'invite de commandes, exécutez DocSample.exe.</span><span class="sxs-lookup"><span data-stu-id="18779-120">At the command prompt, execute DocSample.exe.</span></span>  
  
  
