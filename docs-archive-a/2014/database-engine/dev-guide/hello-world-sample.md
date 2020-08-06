---
title: Exemple de Hello World | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
ms.assetid: fed6c358-f5ee-4d4c-9ad6-089778383ba7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0d5616c1d4ef6428a011c8e36be3757931039c9f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709864"
---
# <a name="hello-world-sample"></a><span data-ttu-id="93e80-102">Exemple Hello World</span><span class="sxs-lookup"><span data-stu-id="93e80-102">Hello World Sample</span></span>
  <span data-ttu-id="93e80-103">L'exemple Hello World montre les opérations de base à effectuer pour créer, déployer et tester une procédure stockée simple et basée sur l'intégration du CLR (Common Language Runtime).</span><span class="sxs-lookup"><span data-stu-id="93e80-103">The Hello World sample demonstrates the basic operations that are involved in creating, deploying, and testing a simple common language runtime (CLR) integration-based stored procedure.</span></span> <span data-ttu-id="93e80-104">Cet exemple montre également comment retourner des données via un enregistrement qui est construit dynamiquement par la procédure stockée et retourné à l'appelant.</span><span class="sxs-lookup"><span data-stu-id="93e80-104">This sample also demonstrates how to return data through a record, which is dynamically constructed by the stored procedure and returned to the caller.</span></span>  
  
 <span data-ttu-id="93e80-105">La `HelloWorld` procédure stockée retourne la chaîne « Hello World ! »</span><span class="sxs-lookup"><span data-stu-id="93e80-105">The `HelloWorld` stored procedure returns the string "Hello world!"</span></span> <span data-ttu-id="93e80-106">dans un jeu de résultats composé d’une ligne.</span><span class="sxs-lookup"><span data-stu-id="93e80-106">in a result set consisting of one row.</span></span> <span data-ttu-id="93e80-107">Cet exemple illustre certaines utilisations des classes [Microsoft. SqlServer. Server. SqlMetaData](https://go.microsoft.com/fwlink/?LinkID=193572), [Microsoft. SqlServer. Server. SqlDataRecord](https://go.microsoft.com/fwlink/?LinkID=193573) et [Microsoft. SqlServer. Server. pipe](https://go.microsoft.com/fwlink/?LinkID=193571).</span><span class="sxs-lookup"><span data-stu-id="93e80-107">This example illustrates some uses for the classes [Microsoft.SqlServer.Server.SqlMetaData](https://go.microsoft.com/fwlink/?LinkID=193572), [Microsoft.SqlServer.Server.SqlDataRecord](https://go.microsoft.com/fwlink/?LinkID=193573) and [Microsoft.SqlServer.Server.Pipe](https://go.microsoft.com/fwlink/?LinkID=193571).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="93e80-108">Prérequis</span><span class="sxs-lookup"><span data-stu-id="93e80-108">Prerequisites</span></span>  
 <span data-ttu-id="93e80-109">Pour créer et exécuter ce projet, les logiciels suivants doivent être installés :</span><span class="sxs-lookup"><span data-stu-id="93e80-109">To create and run this project the following the following software must be installed:</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="93e80-110">ou [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express.</span><span class="sxs-lookup"><span data-stu-id="93e80-110">or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express.</span></span> <span data-ttu-id="93e80-111">Vous pouvez vous procurer gratuitement [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express à partir du site Web [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express Documentation and Samples [(en anglais)](https://www.microsoft.com/sql-server/sql-server-editions-express)</span><span class="sxs-lookup"><span data-stu-id="93e80-111">You can obtain [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express free of charge from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express Documentation and Samples [Web site](https://www.microsoft.com/sql-server/sql-server-editions-express)</span></span>  
  
-   <span data-ttu-id="93e80-112">Base de données AdventureWorks qui est disponible sur le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] site Web [du Centre pour les développeurs](https://go.microsoft.com/fwlink/?linkid=62796)</span><span class="sxs-lookup"><span data-stu-id="93e80-112">The AdventureWorks database that is available at the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Developer [Web site](https://go.microsoft.com/fwlink/?linkid=62796)</span></span>  
  
-   <span data-ttu-id="93e80-113">Le Kit de développement logiciel .NET Framework SDK 2.0 ou version ultérieure, ou Microsoft Visual Studio 2005 ou version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="93e80-113">.NET Framework SDK 2.0 or later or Microsoft Visual Studio 2005 or later.</span></span> <span data-ttu-id="93e80-114">Vous pouvez vous procurer gratuitement le Kit de développement logiciel .NET Framework SDK.</span><span class="sxs-lookup"><span data-stu-id="93e80-114">You can obtain .NET Framework SDK free of charge.</span></span>  
  
-   <span data-ttu-id="93e80-115">De plus, les conditions suivantes doivent être réunies :</span><span class="sxs-lookup"><span data-stu-id="93e80-115">In addition, the following conditions must be met:</span></span>  
  
-   <span data-ttu-id="93e80-116">L'intégration du CLR doit être activée sur l'instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que vous utilisez.</span><span class="sxs-lookup"><span data-stu-id="93e80-116">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you are using must have CLR integration enabled.</span></span>  
  
-   <span data-ttu-id="93e80-117">Pour activer l'intégration du CLR, effectuez les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="93e80-117">In order to enable CLR integration, perform the following steps:</span></span>  
  
    #### <a name="enabling-clr-integration"></a><span data-ttu-id="93e80-118">Activation de l'intégration du CLR</span><span class="sxs-lookup"><span data-stu-id="93e80-118">Enabling CLR Integration</span></span>  
  
    -   <span data-ttu-id="93e80-119">Exécutez les commandes [!INCLUDE[tsql](../../includes/tsql-md.md)] suivantes :</span><span class="sxs-lookup"><span data-stu-id="93e80-119">Execute the following [!INCLUDE[tsql](../../includes/tsql-md.md)] commands:</span></span>  
  
     `sp_configure 'clr enabled', 1`  
  
     `GO`  
  
     `RECONFIGURE`  
  
     `GO`  
  
    > [!NOTE]  
    >  <span data-ttu-id="93e80-120">Pour activer l'intégration du CLR, vous devez disposer de l'autorisation de niveau serveur `ALTER SETTINGS` qui est attribuée implicitement aux membres des rôles serveur fixes `sysadmin` et `serveradmin`.</span><span class="sxs-lookup"><span data-stu-id="93e80-120">To enable CLR, you must have `ALTER SETTINGS` server level permission, which is implicitly held by members of the `sysadmin` and `serveradmin` fixed server roles.</span></span>  
  
-   <span data-ttu-id="93e80-121">La base de données AdventureWorks doit être installée sur l'instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que vous utilisez.</span><span class="sxs-lookup"><span data-stu-id="93e80-121">The AdventureWorks database must be installed on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you are using.</span></span>  
  
-   <span data-ttu-id="93e80-122">Si vous n'êtes pas administrateur de l'instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilisée, vous devez demander à un administrateur de vous accorder l'autorisation **CreateAssembly** pour terminer l'installation.</span><span class="sxs-lookup"><span data-stu-id="93e80-122">If you are not an administrator for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you are using, you must have an administrator grant you **CreateAssembly** permission to complete the installation.</span></span>  
  
## <a name="building-the-sample"></a><span data-ttu-id="93e80-123">Génération de l'exemple</span><span class="sxs-lookup"><span data-stu-id="93e80-123">Building the Sample</span></span>  
  
#### <a name="create-and-run-the-sample-by-using-the-following-instructions"></a><span data-ttu-id="93e80-124">Créez et exécutez l'exemple à l'aide des instructions suivantes :</span><span class="sxs-lookup"><span data-stu-id="93e80-124">Create and run the sample by using the following instructions:</span></span>  
  
1.  <span data-ttu-id="93e80-125">Ouvrez une invite de commandes Visual Studio ou .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="93e80-125">Open a Visual Studio or .NET Framework command prompt.</span></span>  
  
2.  <span data-ttu-id="93e80-126">Si nécessaire, créez un répertoire pour votre exemple.</span><span class="sxs-lookup"><span data-stu-id="93e80-126">If necessary, create a directory for your sample.</span></span> <span data-ttu-id="93e80-127">Pour cet exemple, nous utiliserons C:\MySample.</span><span class="sxs-lookup"><span data-stu-id="93e80-127">For this example, we will use C:\MySample.</span></span>  
  
3.  <span data-ttu-id="93e80-128">Dans c:\MySample, créez `HelloWorld.vb` (pour l'exemple Visual Basic) ou `HelloWorld.cs` (pour l'exemple C#) et copiez l'exemple de code Visual Basic ou  C# approprié (ci-dessous) dans le fichier.</span><span class="sxs-lookup"><span data-stu-id="93e80-128">In c:\MySample, create `HelloWorld.vb` (for the Visual Basic sample) or `HelloWorld.cs` (for the C# sample) and copy the appropriate Visual Basic or C# sample code (below) into the file.</span></span>  
  
4.  <span data-ttu-id="93e80-129">Compilez l'exemple de code à partir de l'invite de ligne de commande en exécutant l'un des éléments suivants, selon le langage choisi.</span><span class="sxs-lookup"><span data-stu-id="93e80-129">Compile the sample code from the command line prompt by executing one of the following, depending on your choice of language.</span></span>  
  
    -   `vbc C:HelloWorld.vb /target:library`  
  
    -   `csc /target:library HelloWorld.cs`  
  
5.  <span data-ttu-id="93e80-130">Copiez le code d'installation [!INCLUDE[tsql](../../includes/tsql-md.md)] dans un fichier et enregistrez-le sous `Install.sql` dans le répertoire d'exemple.</span><span class="sxs-lookup"><span data-stu-id="93e80-130">Copy the [!INCLUDE[tsql](../../includes/tsql-md.md)] installation code into a file and save it as `Install.sql` in the sample directory.</span></span>  
  
6.  <span data-ttu-id="93e80-131">Déployez l'assembly et la procédure stockée en exécutant</span><span class="sxs-lookup"><span data-stu-id="93e80-131">Deploy the assembly and stored procedure by executing</span></span>  
  
    -   `sqlcmd -E -I -i install.sql -v root = "C:\MySample\"`  
  
7.  <span data-ttu-id="93e80-132">Copiez le script de la commande de test [!INCLUDE[tsql](../../includes/tsql-md.md)] dans un fichier et enregistrez-le sous `test.sql` dans le répertoire d'exemple.</span><span class="sxs-lookup"><span data-stu-id="93e80-132">Copy [!INCLUDE[tsql](../../includes/tsql-md.md)] test command script into a file and save it as `test.sql` in the sample directory.</span></span>  
  
8.  <span data-ttu-id="93e80-133">Exécutez le script de test avec la commande suivante</span><span class="sxs-lookup"><span data-stu-id="93e80-133">Execute the test script with the following command</span></span>  
  
    -   `sqlcmd -E -I -i test.sql`  
  
9. <span data-ttu-id="93e80-134">Copiez le script de nettoyage [!INCLUDE[tsql](../../includes/tsql-md.md)] dans un fichier et enregistrez-le sous `cleanup.sql` dans le répertoire d'exemple.</span><span class="sxs-lookup"><span data-stu-id="93e80-134">Copy the [!INCLUDE[tsql](../../includes/tsql-md.md)] cleanup script into a file and save it as `cleanup.sql` in the sample directory.</span></span>  
  
10. <span data-ttu-id="93e80-135">Exécutez le script avec la commande suivante</span><span class="sxs-lookup"><span data-stu-id="93e80-135">Execute the script with the  following command</span></span>  
  
    -   `sqlcmd -E -I -i cleanup.sql`  
  
## <a name="sample-code"></a><span data-ttu-id="93e80-136">Exemple de code</span><span class="sxs-lookup"><span data-stu-id="93e80-136">Sample Code</span></span>  
 <span data-ttu-id="93e80-137">Voici les listes de code pour cet exemple.</span><span class="sxs-lookup"><span data-stu-id="93e80-137">The following are the code listings for this sample.</span></span>  
  
 <span data-ttu-id="93e80-138">C#</span><span class="sxs-lookup"><span data-stu-id="93e80-138">C#</span></span>  
  
```  
using System;  
using System.Data;  
using System.Data.SqlClient;  
using System.Data.SqlTypes;  
using Microsoft.SqlServer.Server;  
public partial class StoredProcedures  
{  
    [Microsoft.SqlServer.Server.SqlProcedure]  
    public static void HelloWorld()  
    {  
        Microsoft.SqlServer.Server.SqlMetaData columnInfo  
                = new Microsoft.SqlServer.Server.SqlMetaData("Column1", SqlDbType.NVarChar, 12);  
        SqlDataRecord greetingRecord  
            = new SqlDataRecord(new Microsoft.SqlServer.Server.SqlMetaData[] { columnInfo });  
        greetingRecord.SetString(0, "Hello world!");  
        SqlContext.Pipe.Send(greetingRecord);  
    }  
};  
  
```  
  
 <span data-ttu-id="93e80-139">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="93e80-139">Visual Basic</span></span>  
  
```  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
  
Partial Public NotInheritable Class StoredProcedures  
    <Microsoft.SqlServer.Server.SqlProcedure()> _  
    Public Shared Sub HelloWorld()  
        Dim columnInfo As New Microsoft.SqlServer.Server.SqlMetaData("Column1", _  
            SqlDbType.NVarChar, 12)  
        Dim greetingRecord As New SqlDataRecord(New  _  
            Microsoft.SqlServer.Server.SqlMetaData() {columnInfo})  
        greetingRecord.SetString(0, "Hello World!")  
        SqlContext.Pipe.Send(greetingRecord)  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="93e80-140">Il s'agit du script d'installation [!INCLUDE[tsql](../../includes/tsql-md.md)] (`Install.sql`), qui déploie l'assembly et crée la procédure stockée dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="93e80-140">This is the [!INCLUDE[tsql](../../includes/tsql-md.md)] installation script (`Install.sql`), which deploys the assembly and creates the stored procedure in the database.</span></span>  
  
```  
USE AdventureWorks  
GO  
IF EXISTS (SELECT * FROM sys.procedures WHERE [name] = 'usp_HelloWorld')  
DROP PROCEDURE usp_HelloWorld;  
GO  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorld')  
DROP ASSEMBLY HelloWorld;  
GO  
DECLARE @SamplesPath nvarchar(1024)  
set @SamplesPath = '$(root)'  
CREATE ASSEMBLY HelloWorld   
FROM @SamplesPath + 'HelloWorld.dll'  
WITH permission_set = Safe;  
GO  
  
CREATE PROCEDURE usp_HelloWorld  
--(  
--    @Greeting nvarchar(12) OUTPUT  
--)  
AS EXTERNAL NAME HelloWorld.[StoredProcedures].HelloWorld;  
GO  
```  
  
 <span data-ttu-id="93e80-141">Il s'agit de `test.sql`, qui teste l'exemple en exécutant la procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="93e80-141">This is `test.sql`, which tests the sample by executing the stored procedure.</span></span>  
  
```  
use AdventureWorks  
go  
execute usp_HelloWorld  
  
USE AdventureWorks;  
GO  
IF EXISTS (SELECT * FROM sys.procedures WHERE [name] = 'usp_HelloWorld')  
DROP PROCEDURE usp_HelloWorld;  
GO  
```  
  
 <span data-ttu-id="93e80-142">Le code [!INCLUDE[tsql](../../includes/tsql-md.md)] suivant supprime l'assembly et la procédure stockée de la base de données.</span><span class="sxs-lookup"><span data-stu-id="93e80-142">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] removes the assembly and stored procedure from the database.</span></span>  
  
```  
USE AdventureWorks  
GO  
  
IF EXISTS (SELECT * FROM sys.procedures WHERE [name] = 'usp_HelloWorld')  
DROP PROCEDURE usp_HelloWorld;  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorld')  
DROP ASSEMBLY HelloWorld;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="93e80-143">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="93e80-143">See Also</span></span>  
 [<span data-ttu-id="93e80-144">Scénarios et exemples d’utilisation pour l’intégration du CLR &#40;Common Language Runtime&#41;</span><span class="sxs-lookup"><span data-stu-id="93e80-144">Usage Scenarios and Examples for Common Language Runtime &#40;CLR&#41; Integration</span></span>](../../../2014/database-engine/dev-guide/usage-scenarios-and-examples-for-common-language-runtime-clr-integration.md)  
  
  
