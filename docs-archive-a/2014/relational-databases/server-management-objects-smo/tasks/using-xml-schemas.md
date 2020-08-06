---
title: Utilisation de schémas XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- XML [SMO]
ms.assetid: 9d04de01-efeb-4b2d-8c28-3234bc7ff2f3
author: stevestein
ms.author: sstein
ms.openlocfilehash: a0e5c58bb05da7025651a4e55e29541d694ba1ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709036"
---
# <a name="using-xml-schemas"></a><span data-ttu-id="e57be-102">Utilisation de schémas XML</span><span class="sxs-lookup"><span data-stu-id="e57be-102">Using XML Schemas</span></span>
  <span data-ttu-id="e57be-103">La programmation XML dans SMO se limite à la fourniture de types de données XML, d'espaces de noms XML et à l'indexation simple sur les colonnes de type de données XML.</span><span class="sxs-lookup"><span data-stu-id="e57be-103">XML programming in SMO is limited to providing XML data types, XML namespaces, and simple indexing on XML data type columns.</span></span>  
  
 [!INCLUDE[msCoName](../../../includes/msconame-md.md)]<span data-ttu-id="e57be-104">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]fournit le stockage natif pour les instances de document XML.</span><span class="sxs-lookup"><span data-stu-id="e57be-104">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] provides native storage for XML document instances.</span></span> <span data-ttu-id="e57be-105">Les schémas XML vous permettent de définir des types de données XML complexes, qui peuvent être utilisés pour valider des documents XML afin de garantir l'intégrité des données.</span><span class="sxs-lookup"><span data-stu-id="e57be-105">XML schemas let you define complex XML data types, which can be used to validate XML documents to ensure data integrity.</span></span> <span data-ttu-id="e57be-106">Le schéma XML est défini dans l'objet <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection>.</span><span class="sxs-lookup"><span data-stu-id="e57be-106">The XML schema is defined in the <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e57be-107">Exemple</span><span class="sxs-lookup"><span data-stu-id="e57be-107">Example</span></span>  
 <span data-ttu-id="e57be-108">Pour utiliser un exemple de code qui est fourni, vous devrez choisir l'environnement de programmation, le modèle de programmation et le langage de programmation dans lequel créer votre application.</span><span class="sxs-lookup"><span data-stu-id="e57be-108">To use any code example that is provided, you will have to choose the programming environment, the programming template, and the programming language in which to create your application.</span></span> <span data-ttu-id="e57be-109">Pour plus d’informations, consultez [créer un projet Visual Basic Smo dans Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) ou [créer un projet Visual C&#35; Smo dans Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="e57be-109">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) or [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="creating-an-xml-schema-in-visual-basic"></a><span data-ttu-id="e57be-110">Création d'un schéma XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e57be-110">Creating an XML Schema in Visual Basic</span></span>  
 <span data-ttu-id="e57be-111">Cet exemple de code montre comment créer un schéma XML à l'aide de l'objet <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection>.</span><span class="sxs-lookup"><span data-stu-id="e57be-111">This code example shows how to create an XML schema by using the <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection> object.</span></span> <span data-ttu-id="e57be-112">La propriété <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection.Text%2A>, qui définit la collection de schémas XML, contient plusieurs guillemets doubles.</span><span class="sxs-lookup"><span data-stu-id="e57be-112">The <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection.Text%2A> property, which defines the XML schema collection, contains several double quotation marks.</span></span> <span data-ttu-id="e57be-113">Ils sont remplacés par la chaîne `chr(34)` .</span><span class="sxs-lookup"><span data-stu-id="e57be-113">These are replaced by the `chr(34)` string.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBXMLSchema1](SMO How to#SMO_VBXMLSchema1)]  -->  
  
## <a name="creating-an-xml-schema-in-visual-c"></a><span data-ttu-id="e57be-114">Création d'un schéma XML en Visual C#</span><span class="sxs-lookup"><span data-stu-id="e57be-114">Creating an XML Schema in Visual C#</span></span>  
 <span data-ttu-id="e57be-115">Cet exemple de code montre comment créer un schéma XML à l'aide de l'objet <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection>.</span><span class="sxs-lookup"><span data-stu-id="e57be-115">This code example shows how to create an XML schema by using the <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection> object.</span></span> <span data-ttu-id="e57be-116">La propriété <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection.Text%2A>, qui définit la collection de schémas XML, contient plusieurs guillemets doubles.</span><span class="sxs-lookup"><span data-stu-id="e57be-116">The <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection.Text%2A> property, which defines the XML schema collection, contains several double quotation marks.</span></span> <span data-ttu-id="e57be-117">Ils sont remplacés par la chaîne `chr(34)` .</span><span class="sxs-lookup"><span data-stu-id="e57be-117">These are replaced by the `chr(34)` string.</span></span>  
  
```csharp
{  
            //Connect to the local, default instance of SQL Server.   
            Server srv = default(Server);  
            srv = new Server();  
            //Reference the AdventureWorks2012 database.   
            Database db = default(Database);  
            db = srv.Databases["AdventureWorks2012"];  
            //Define an XmlSchemaCollection object by supplying the parent  
            // database and name arguments in the constructor.   
            XmlSchemaCollection xsc = default(XmlSchemaCollection);  
            xsc = new XmlSchemaCollection(db, "MySampleCollection");  
            xsc.Text = "<schema xmlns=" + Strings.Chr(34) + "http://www.w3.org/2001/XMLSchema" + Strings.Chr(34) + " xmlns:ns=" + Strings.Chr(34) + "http://ns" + Strings.Chr(34) + "><element name=" + Strings.Chr(34) + "e" + Strings.Chr(34) + " type=" + Strings.Chr(34) + "dateTime" + Strings.Chr(34) + "/></schema>";  
            //Create the XML schema collection on the instance of SQL Server.   
            xsc.Create();  
        }  
```  
  
## <a name="creating-an-xml-schema-in-powershell"></a><span data-ttu-id="e57be-118">Création d'un schéma XML dans PowerShell</span><span class="sxs-lookup"><span data-stu-id="e57be-118">Creating an XML Schema in PowerShell</span></span>  
 <span data-ttu-id="e57be-119">Cet exemple de code montre comment créer un schéma XML à l'aide de l'objet <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection>.</span><span class="sxs-lookup"><span data-stu-id="e57be-119">This code example shows how to create an XML schema by using the <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection> object.</span></span> <span data-ttu-id="e57be-120">La propriété <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection.Text%2A>, qui définit la collection de schémas XML, contient plusieurs guillemets doubles.</span><span class="sxs-lookup"><span data-stu-id="e57be-120">The <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection.Text%2A> property, which defines the XML schema collection, contains several double quotation marks.</span></span> <span data-ttu-id="e57be-121">Ils sont remplacés par la chaîne `chr(34)` .</span><span class="sxs-lookup"><span data-stu-id="e57be-121">These are replaced by the `chr(34)` string.</span></span>  
  
```powershell
#Get a server object which corresponds to the default instance replace LocalMachine with the physical server  
cd \sql\LocalHost  
$srv = Get-Item default  
  
#Reference the AdventureWorks database.  
$db = $srv.Databases["AdventureWorks2012"]  
  
#Create a new schema collection  
$xsc = New-Object -TypeName Microsoft.SqlServer.Management.SMO.XmlSchemaCollection `  
-argumentlist $db,"MySampleCollection"  
  
#Add the xml  
$dq = '"' # the double quote character  
$xsc.Text = "<schema xmlns=" + $dq + "http://www.w3.org/2001/XMLSchema" + $dq + `  
"  xmlns:ns=" + $dq + "http://ns" + $dq + "><element name=" + $dq + "e" + $dq +`  
 " type=" + $dq + "dateTime" + $dq + "/></schema>"  
  
#Create the XML schema collection on the instance of SQL Server.  
$xsc.Create()  
```  
