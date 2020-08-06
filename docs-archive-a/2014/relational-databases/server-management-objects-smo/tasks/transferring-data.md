---
title: Transfert de données | Microsoft Docs
ms.custom: ''
ms.date: 10/20/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- data transfers [SMO]
- transferring data
ms.assetid: eea255c3-8251-40f0-973b-fe4ef6cb5261
author: stevestein
ms.author: sstein
ms.openlocfilehash: dcbcdc1e61c2d18f6a98f797385145f04dfecc7c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700920"
---
# <a name="transferring-data"></a><span data-ttu-id="8efcf-102">Transfert de données</span><span class="sxs-lookup"><span data-stu-id="8efcf-102">Transferring Data</span></span>
  <span data-ttu-id="8efcf-103">La classe <xref:Microsoft.SqlServer.Management.Smo.Transfer> est une classe utilitaire qui fournit des outils pour transférer des objets et des données.</span><span class="sxs-lookup"><span data-stu-id="8efcf-103">The <xref:Microsoft.SqlServer.Management.Smo.Transfer> class is a utility class that provides tools to transfer objects and data.</span></span>  
  
 <span data-ttu-id="8efcf-104">Les objets du schéma de base de données sont transférés en exécutant un script généré sur le serveur cible.</span><span class="sxs-lookup"><span data-stu-id="8efcf-104">Objects in the database schema are transferred by executing a generated script on the target server.</span></span> <span data-ttu-id="8efcf-105">Les données <xref:Microsoft.SqlServer.Management.Smo.Table> sont transférées avec un package DTS créé dynamiquement.</span><span class="sxs-lookup"><span data-stu-id="8efcf-105"><xref:Microsoft.SqlServer.Management.Smo.Table> data is transferred with a dynamically created DTS package.</span></span>  
  
 <span data-ttu-id="8efcf-106">L'objet <xref:Microsoft.SqlServer.Management.Smo.Transfer> contient toutes les fonctionnalités des objets <xref:Microsoft.SqlServer.Management.Smo.Transfer> dans DMO, de même que des fonctionnalités [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="8efcf-106">The <xref:Microsoft.SqlServer.Management.Smo.Transfer> object contains all the functionality of the <xref:Microsoft.SqlServer.Management.Smo.Transfer> objects in DMO and additional [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] functionality.</span></span> <span data-ttu-id="8efcf-107">Toutefois, dans SMO dans [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] , l' <xref:Microsoft.SqlServer.Management.Smo.Transfer> objet utilise l’API [SQLBulkCopy](https://msdn.microsoft.com/library/system.data.sqlclient.sqlbulkcopy\(v=VS.90\).aspx) pour transférer des données.</span><span class="sxs-lookup"><span data-stu-id="8efcf-107">However, in SMO in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)], the <xref:Microsoft.SqlServer.Management.Smo.Transfer> object uses the [SQLBulkCopy](https://msdn.microsoft.com/library/system.data.sqlclient.sqlbulkcopy\(v=VS.90\).aspx) API to transfer data.</span></span> <span data-ttu-id="8efcf-108">Par ailleurs, les méthodes et les propriétés utilisées pour effectuer les transferts de données résident sur l'objet <xref:Microsoft.SqlServer.Management.Smo.Transfer> et non sur l'objet <xref:Microsoft.SqlServer.Management.Smo.Database>.</span><span class="sxs-lookup"><span data-stu-id="8efcf-108">Also, the methods and properties that are used to perform data transfers reside on the <xref:Microsoft.SqlServer.Management.Smo.Transfer> object instead of the <xref:Microsoft.SqlServer.Management.Smo.Database> object.</span></span> <span data-ttu-id="8efcf-109">Le déplacement de fonctionnalités des classes d'instance vers les classes utilitaires est compatible avec un modèle objet plus léger car le code de tâches spécifiques est chargé uniquement lorsqu'il est requis.</span><span class="sxs-lookup"><span data-stu-id="8efcf-109">Moving functionality from the instance classes to utility classes is consistent with a lighter object model because the code for specific tasks is loaded only when it is required.</span></span>  
  
 <span data-ttu-id="8efcf-110">L'objet <xref:Microsoft.SqlServer.Management.Smo.Transfer> ne prend pas en charge les transferts de données vers une base de données cible dont un <xref:Microsoft.SqlServer.Management.Smo.Database.CompatibilityLevel%2A> est inférieur à la version de l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8efcf-110">The <xref:Microsoft.SqlServer.Management.Smo.Transfer> object does not support data transfers to a target database that has a <xref:Microsoft.SqlServer.Management.Smo.Database.CompatibilityLevel%2A> less than the version of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="example"></a><span data-ttu-id="8efcf-111">Exemple</span><span class="sxs-lookup"><span data-stu-id="8efcf-111">Example</span></span>  
 [!INCLUDE[ssChooseProgEnv](../../../includes/sschooseprogenv-md.md)]  
  
## <a name="transferring-schema-and-data-from-one-database-to-another-in-visual-basic"></a><span data-ttu-id="8efcf-112">Transfert de schéma et de données d'une base de données vers une autre en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8efcf-112">Transferring Schema and Data from One Database to Another in Visual Basic</span></span>  
 <span data-ttu-id="8efcf-113">Cet exemple de code indique comment transférer un schéma et des données d'une base de données vers une autre à l'aide de l'objet <xref:Microsoft.SqlServer.Management.Smo.Transfer>.</span><span class="sxs-lookup"><span data-stu-id="8efcf-113">This code example shows how to transfer schema and data from one database to another using the <xref:Microsoft.SqlServer.Management.Smo.Transfer> object.</span></span>  
  
```vb
'Connect to the local, default instance of SQL Server.
Dim srv As Server
srv = New Server
'Reference the AdventureWorks2012 2008R2 database
Dim db As Database
db = srv.Databases("AdventureWorks2012")
'Create a new database that is to be destination database.
Dim dbCopy As Database
dbCopy = New Database(srv, "AdventureWorks2012Copy")
dbCopy.Create()
'Define a Transfer object and set the required options and properties.
Dim xfr As Transfer
xfr = New Transfer(db)
xfr.CopyAllTables = True
xfr.Options.WithDependencies = True
xfr.Options.ContinueScriptingOnError = True
xfr.DestinationDatabase = "AdventureWorks2012Copy"
xfr.DestinationServer = srv.Name
xfr.DestinationLoginSecure = True
xfr.CopySchema = True
'Script the transfer. Alternatively perform immediate data transfer with TransferData method.
xfr.ScriptTransfer()
```
  
## <a name="transferring-schema-and-data-from-one-database-to-another-in-visual-c"></a><span data-ttu-id="8efcf-114">Transfert de schéma et de données d'une base de données vers une autre en Visual C#</span><span class="sxs-lookup"><span data-stu-id="8efcf-114">Transferring Schema and Data from One Database to Another in Visual C#</span></span>  
 <span data-ttu-id="8efcf-115">Cet exemple de code indique comment transférer un schéma et des données d'une base de données vers une autre à l'aide de l'objet <xref:Microsoft.SqlServer.Management.Smo.Transfer>.</span><span class="sxs-lookup"><span data-stu-id="8efcf-115">This code example shows how to transfer schema and data from one database to another using the <xref:Microsoft.SqlServer.Management.Smo.Transfer> object.</span></span>  
  
```csharp
{  
            Server srv;  
            srv = new Server();  
            //Reference the AdventureWorks2012 database   
            Database db;  
            db = srv.Databases["AdventureWorks2012"];  
            //Create a new database that is to be destination database.   
            Database dbCopy;  
            dbCopy = new Database(srv, "AdventureWorks2012Copy");  
            dbCopy.Create();  
            //Define a Transfer object and set the required options and properties.   
            Transfer xfr;  
            xfr = new Transfer(db);  
            xfr.CopyAllTables = true;  
            xfr.Options.WithDependencies = true;  
            xfr.Options.ContinueScriptingOnError = true;  
            xfr.DestinationDatabase = "AdventureWorks2012Copy";  
            xfr.DestinationServer = srv.Name;  
            xfr.DestinationLoginSecure = true;  
            xfr.CopySchema = true;  
            //Script the transfer. Alternatively perform immediate data transfer   
            // with TransferData method.   
            xfr.ScriptTransfer();  
        }   
```  
  
## <a name="transferring-schema-and-data-from-one-database-to-another-in-powershell"></a><span data-ttu-id="8efcf-116">Transfert de schéma et de données d'une base de données vers une autre dans PowerShell</span><span class="sxs-lookup"><span data-stu-id="8efcf-116">Transferring Schema and Data from One Database to Another in PowerShell</span></span>  
 <span data-ttu-id="8efcf-117">Cet exemple de code indique comment transférer un schéma et des données d'une base de données vers une autre à l'aide de l'objet <xref:Microsoft.SqlServer.Management.Smo.Transfer>.</span><span class="sxs-lookup"><span data-stu-id="8efcf-117">This code example shows how to transfer schema and data from one database to another using the <xref:Microsoft.SqlServer.Management.Smo.Transfer> object.</span></span>  
  
```powershell
#Connect to the local, default instance of SQL Server.  
  
#Get a server object which corresponds to the default instance  
$srv = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Server  
  
#Reference the AdventureWorks2012 database.  
$db = $srv.Databases["AdventureWorks2012"]  
  
#Create a database to hold the copy of AdventureWorks  
$dbCopy = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Database -ArgumentList $srv, "AdventureWorksCopy"  
$dbCopy.Create()  
  
#Define a Transfer object and set the required options and properties.  
$xfr = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Transfer -ArgumentList $db  
  
#Set this objects properties  
$xfr.CopyAllTables = $true  
$xfr.Options.WithDependencies = $true  
$xfr.Options.ContinueScriptingOnError = $true  
$xfr.DestinationDatabase = "AdventureWorksCopy"  
$xfr.DestinationServer = $srv.Name  
$xfr.DestinationLoginSecure = $true  
$xfr.CopySchema = $true  
"Scripting Data Transfer"  
#Script the transfer. Alternatively perform immediate data transfer with TransferData method.  
$xfr.ScriptTransfer()  
```  
