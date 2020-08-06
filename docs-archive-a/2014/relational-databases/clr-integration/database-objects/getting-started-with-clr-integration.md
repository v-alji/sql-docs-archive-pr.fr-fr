---
title: Prise en main avec l’intégration du CLR | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
dev_langs:
- TSQL
- VB
- CSharp
helpviewer_keywords:
- database objects [CLR integration]
- namespaces [CLR integration]
- database objects [CLR integration], about CLR integration
- stored procedures [CLR integration]
- common language runtime [SQL Server], about CLR integration
- building database objects [CLR integration], about CLR integration
- common language runtime [SQL Server], stored procedures
- common language runtime [SQL Server], namespaces
- Hello World example [CLR integration]
- library [CLR integration]
ms.assetid: c73e628a-f54a-411a-bfe3-6dae519316cc
author: rothja
ms.author: jroth
ms.openlocfilehash: 43c97e411a4d74aa48b88f2edbbe420ae17f3534
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600078"
---
# <a name="getting-started-with-clr-integration"></a><span data-ttu-id="315fb-102">Mise en route avec l'intégration du CLR</span><span class="sxs-lookup"><span data-stu-id="315fb-102">Getting Started with CLR Integration</span></span>
  <span data-ttu-id="315fb-103">Cette rubrique fournit une vue d’ensemble des espaces de noms et des bibliothèques requis pour compiler des objets de base de données à l’aide de l' [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] intégration avec l' .NET Framework Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="315fb-103">This topic provides an overview of the namespaces and libraries required to compile database objects using the [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] integration with the .NET Framework common language runtime (CLR).</span></span> <span data-ttu-id="315fb-104">La rubrique vous indique également comment écrire, compiler et exécuter une procédure stockée CLR simple écrite dans [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#.</span><span class="sxs-lookup"><span data-stu-id="315fb-104">The topic also shows you how to write, compile, and run a simple CLR stored procedure written in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#.</span></span>  
  
## <a name="required-namespaces"></a><span data-ttu-id="315fb-105">Espaces de noms requis</span><span class="sxs-lookup"><span data-stu-id="315fb-105">Required Namespaces</span></span>  
 <span data-ttu-id="315fb-106">À partir de [!INCLUDE[ssVersion2005](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="315fb-106">Beginning with [!INCLUDE[ssVersion2005](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="315fb-107">Les fonctionnalités d'intégration du CLR sont exposées dans un assembly appelé system.data.dll, qui fait partie du .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="315fb-107">CLR integration functionality is exposed in an assembly called system.data.dll, which is part of the .NET Framework.</span></span> <span data-ttu-id="315fb-108">Cet assembly se trouve dans le Global Assembly Cache (GAC), ainsi que dans le répertoire .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="315fb-108">This assembly can be found in the Global Assembly Cache (GAC) as well as in the .NET Framework directory.</span></span> <span data-ttu-id="315fb-109">Une référence à cet assembly est ajoutée en général automatiquement par les outils en ligne de commande et [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Studio, afin qu'il ne soit pas nécessaire de l'ajouter manuellement.</span><span class="sxs-lookup"><span data-stu-id="315fb-109">A reference to this assembly is typically added automatically by both command line tools and [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Studio, so there is no need to add it manually.</span></span>  
  
 <span data-ttu-id="315fb-110">L'assembly system.data.dll contient les espaces de noms suivants, qui sont requis pour compiler les objets de base de données CLR :</span><span class="sxs-lookup"><span data-stu-id="315fb-110">The system.data.dll assembly contains the following namespaces, which are required for compiling CLR database objects:</span></span>  
  
 `System.Data`  
  
 `System.Data.Sql`  
  
 `Microsoft.SqlServer.Server`  
  
 `System.Data.SqlTypes`  
  
## <a name="writing-a-simple-hello-world-stored-procedure"></a><span data-ttu-id="315fb-111">Écriture d'une procédure stockée "Hello World" simple</span><span class="sxs-lookup"><span data-stu-id="315fb-111">Writing A Simple "Hello World" Stored Procedure</span></span>  
 <span data-ttu-id="315fb-112">Copiez et collez le code Visual C# ou [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic suivant dans un éditeur de texte et enregistrez-le dans un fichier nommé "helloworld.cs" ou "helloworld.vb".</span><span class="sxs-lookup"><span data-stu-id="315fb-112">Copy and paste the following Visual C# or [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic code into a text editor, and save it in a file named "helloworld.cs" or "helloworld.vb".</span></span>  
  
```csharp  
using System;  
using System.Data;  
using Microsoft.SqlServer.Server;  
using System.Data.SqlTypes;  
  
public class HelloWorldProc  
{  
    [Microsoft.SqlServer.Server.SqlProcedure]  
    public static void HelloWorld(out string text)  
    {  
        SqlContext.Pipe.Send("Hello world!" + Environment.NewLine);  
        text = "Hello world!";  
    }  
}  
```  
  
```vb  
Imports System  
Imports System.Data  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlTypes  
Imports System.Runtime.InteropServices  
  
Public Class HelloWorldProc  
    <Microsoft.SqlServer.Server.SqlProcedure> _   
    Public Shared  Sub HelloWorld(<Out()> ByRef text as String)  
        SqlContext.Pipe.Send("Hello world!" & Environment.NewLine)  
        text = "Hello world!"  
    End Sub  
End Class  
  
```  
  
 <span data-ttu-id="315fb-113">Ce programme simple contient une méthode statique unique sur une classe publique.</span><span class="sxs-lookup"><span data-stu-id="315fb-113">This simple program contains a single static method on a public class.</span></span> <span data-ttu-id="315fb-114">Cette méthode utilise deux nouvelles classes, `SqlContext` et `SqlPipe`, pour créer des objets de base de données managés afin d'obtenir un message textuel simple.</span><span class="sxs-lookup"><span data-stu-id="315fb-114">This method uses two new classes, `SqlContext` and `SqlPipe`, for creating managed database objects to output a simple text message.</span></span> <span data-ttu-id="315fb-115">La méthode assigne également la chaîne « Hello World ! »</span><span class="sxs-lookup"><span data-stu-id="315fb-115">The method also assigns the string "Hello world!"</span></span> <span data-ttu-id="315fb-116">comme valeur d’un paramètre de sortie.</span><span class="sxs-lookup"><span data-stu-id="315fb-116">as the value of an out parameter.</span></span> <span data-ttu-id="315fb-117">Cette méthode peut être déclarée en tant que procédure stockée dans une [!INCLUDE[ssNoVersion](../../../includes/tsql-md.md)] procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="315fb-117">This method can be declared as a stored procedure in [!INCLUDE[ssNoVersion](../../../includes/tsql-md.md)] stored procedure.</span></span>  
  
 <span data-ttu-id="315fb-118">Nous allons maintenant compiler ce programme sous la forme d'une bibliothèque, le charger dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] et l'exécuter en tant que procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="315fb-118">We will now compile this program as a library, load it into [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], and run it as a stored procedure.</span></span>  
  
## <a name="compiling-the-hello-world-stored-procedure"></a><span data-ttu-id="315fb-119">Compilation de la procédure stockée "Hello World"</span><span class="sxs-lookup"><span data-stu-id="315fb-119">Compiling the "Hello World" Stored Procedure</span></span>  
 [!INCLUDE[ssNoVersion](../../../includes/msconame-md.md)]<span data-ttu-id="315fb-120">.NET Framework les fichiers de redistribution par défaut.</span><span class="sxs-lookup"><span data-stu-id="315fb-120">.NET Framework redistribution files by default.</span></span> <span data-ttu-id="315fb-121">Ces fichiers incluent csc.exe et vbc.exe, les compilateurs de ligne de commande pour les programmes Visual C# et Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="315fb-121">These files include csc.exe and vbc.exe, the command-line compilers for Visual C# and Visual Basic programs.</span></span> <span data-ttu-id="315fb-122">Pour compiler notre exemple, vous devez modifier votre variable de chemin d'accès pour pointer sur le répertoire qui contient csc.exe ou vbc.exe.</span><span class="sxs-lookup"><span data-stu-id="315fb-122">In order to compile our sample, you must modify your path variable to point to the directory containing csc.exe or vbc.exe.</span></span> <span data-ttu-id="315fb-123">Le chemin d'installation par défaut du .NET Framework est le suivant :</span><span class="sxs-lookup"><span data-stu-id="315fb-123">The following is the default installation path of the .NET Framework.</span></span>  
  
```  
C:\Windows\Microsoft.NET\Framework\(version)  
```  
  
 <span data-ttu-id="315fb-124">La version contient le numéro de version du programme redistribuable .NET Framework installé.</span><span class="sxs-lookup"><span data-stu-id="315fb-124">Version contains the version number of the installed .NET Framework redistributable.</span></span> <span data-ttu-id="315fb-125">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="315fb-125">For example:</span></span>  
  
```  
C:\Windows\Microsoft.NET\Framework\v2.0.31113  
```  
  
 <span data-ttu-id="315fb-126">Une fois que vous avez ajouté le répertoire .NET Framework à votre chemin d'accès, vous pouvez compiler l'exemple de procédure stockée en assembly à l'aide de la commande ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="315fb-126">Once you have added the .NET Framework directory to your path, you can compile the sample stored procedure into an assembly with the following command.</span></span> <span data-ttu-id="315fb-127">L'option `/target` vous permet de le compiler en assembly.</span><span class="sxs-lookup"><span data-stu-id="315fb-127">The `/target` option allows you to compile it into an assembly.</span></span>  
  
 <span data-ttu-id="315fb-128">Pour les fichiers sources Visual C# :</span><span class="sxs-lookup"><span data-stu-id="315fb-128">For Visual C# source files:</span></span>  
  
```  
csc /target:library helloworld.cs   
```  
  
 <span data-ttu-id="315fb-129">Pour les fichiers sources Visual Basic :</span><span class="sxs-lookup"><span data-stu-id="315fb-129">For Visual Basic source files:</span></span>  
  
```  
vbc /target:library helloworld.vb  
```  
  
 <span data-ttu-id="315fb-130">Ces commandes lancent le compilateur Visual C# ou Visual Basic en utilisant l'option /target pour spécifier la génération d'une DLL de bibliothèque.</span><span class="sxs-lookup"><span data-stu-id="315fb-130">These commands launch the Visual C# or Visual Basic compiler using the /target option to specify building a library DLL.</span></span>  
  
## <a name="loading-and-running-the-hello-world-stored-procedure-in-sql-server"></a><span data-ttu-id="315fb-131">Chargement et exécution de la procédure stockée "Hello World" dans SQL Server</span><span class="sxs-lookup"><span data-stu-id="315fb-131">Loading and Running the "Hello World" Stored Procedure in SQL Server</span></span>  
 <span data-ttu-id="315fb-132">Une fois que l’exemple de procédure a été compilé avec succès, vous pouvez le tester dans [!INCLUDE[ssNoVersion](../../../includes/ssmanstudiofull-md.md)] et créer une nouvelle requête, en vous connectant à une base de données de test appropriée (par exemple, l’exemple de base de données AdventureWorks).</span><span class="sxs-lookup"><span data-stu-id="315fb-132">Once the sample procedure has successfully compiled, you can test it in [!INCLUDE[ssNoVersion](../../../includes/ssmanstudiofull-md.md)] and create a new query, connecting to a suitable test database (for example, the AdventureWorks sample database).</span></span>  
  
 <span data-ttu-id="315fb-133">La fonctionnalité d'exécution du code CLR est désactivée par défaut dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="315fb-133">The ability to execute common language runtime (CLR) code is set to OFF by default in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="315fb-134">Le code CLR peut être activé à l’aide de la procédure stockée système **sp_configure** .</span><span class="sxs-lookup"><span data-stu-id="315fb-134">The CLR code can be enabled by using the **sp_configure** system stored procedure.</span></span> <span data-ttu-id="315fb-135">Pour plus d’informations, consultez [Activation de l’intégration du CLR](../clr-integration-enabling.md).</span><span class="sxs-lookup"><span data-stu-id="315fb-135">For more information, see [Enabling CLR Integration](../clr-integration-enabling.md).</span></span>  
  
 <span data-ttu-id="315fb-136">Il est nécessaire de créer l'assembly afin de pouvoir accéder à la procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="315fb-136">We will need to create the assembly so we can access the stored procedure.</span></span> <span data-ttu-id="315fb-137">Pour cet exemple, nous supposerons que vous avez créé l'assembly helloworld.dll dans le répertoire C:\.</span><span class="sxs-lookup"><span data-stu-id="315fb-137">For this example, we will assume that you have created the helloworld.dll assembly in the C:\ directory.</span></span> <span data-ttu-id="315fb-138">Ajoutez l'instruction [!INCLUDE[tsql](../../../includes/tsql-md.md)] suivante à votre requête.</span><span class="sxs-lookup"><span data-stu-id="315fb-138">Add the following [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement to your query.</span></span>  
  
```  
CREATE ASSEMBLY helloworld from 'c:\helloworld.dll' WITH PERMISSION_SET = SAFE  
```  
  
 <span data-ttu-id="315fb-139">Une fois l'assembly créé, il est possible d'accéder à la méthode HelloWorld en utilisant l'instruction CREATE PROCEDURE.</span><span class="sxs-lookup"><span data-stu-id="315fb-139">Once the assembly has been created, we can now access our HelloWorld method by using the create procedure statement.</span></span> <span data-ttu-id="315fb-140">Nous appellerons la procédure stockée "hello" :</span><span class="sxs-lookup"><span data-stu-id="315fb-140">We will call our stored procedure "hello":</span></span>  
  
```  
  
CREATE PROCEDURE hello  
@i nchar(25) OUTPUT  
AS  
EXTERNAL NAME helloworld.HelloWorldProc.HelloWorld  
-- if the HelloWorldProc class is inside a namespace (called MyNS),  
-- the last line in the create procedure statement would be  
-- EXTERNAL NAME helloworld.[MyNS.HelloWorldProc].HelloWorld  
```  
  
 <span data-ttu-id="315fb-141">Une fois la procédure créée, elle peut être exécutée tout comme une procédure stockée normale écrite dans [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="315fb-141">Once the procedure has been created, it can be run just like a normal stored procedure written in [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="315fb-142">Exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="315fb-142">Execute the following command:</span></span>  
  
```  
DECLARE @J nchar(25)  
EXEC hello @J out  
PRINT @J  
```  
  
 <span data-ttu-id="315fb-143">Cela doit générer la sortie ci-dessous dans la fenêtre des messages [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="315fb-143">This should result in the following output in the [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] messages window.</span></span>  
  
```  
Hello world!  
Hello world!  
```  
  
## <a name="removing-the-hello-world-stored-procedure-sample"></a><span data-ttu-id="315fb-144">Suppression de l'exemple de procédure stockée "Hello World"</span><span class="sxs-lookup"><span data-stu-id="315fb-144">Removing the "Hello World" Stored Procedure Sample</span></span>  
 <span data-ttu-id="315fb-145">Lorsque vous avez terminé d'exécuter l'exemple de procédure stockée, vous pouvez supprimer la procédure et l'assembly de votre base de données de test.</span><span class="sxs-lookup"><span data-stu-id="315fb-145">When you are finished running the sample stored procedure, you can remove the procedure and the assembly from your test database.</span></span>  
  
 <span data-ttu-id="315fb-146">En premier lieu, supprimez la procédure à l'aide de la commande drop procedure.</span><span class="sxs-lookup"><span data-stu-id="315fb-146">First, remove the procedure using the drop procedure command.</span></span>  
  
```  
IF EXISTS (SELECT name FROM sysobjects WHERE name = 'hello')  
   drop procedure hello  
```  
  
 <span data-ttu-id="315fb-147">Une fois la procédure supprimée, vous pouvez supprimer l'assembly qui contient votre exemple de code.</span><span class="sxs-lookup"><span data-stu-id="315fb-147">Once the procedure has been dropped, you can remove the assembly containing your sample code.</span></span>  
  
```  
IF EXISTS (SELECT name FROM sys.assemblies WHERE name = 'helloworld')  
   drop assembly helloworld  
```  
  
## <a name="see-also"></a><span data-ttu-id="315fb-148">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="315fb-148">See Also</span></span>  
 <span data-ttu-id="315fb-149">[Procédures stockées CLR](../../../database-engine/dev-guide/clr-stored-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="315fb-149">[CLR Stored Procedures](../../../database-engine/dev-guide/clr-stored-procedures.md) </span></span>  
 <span data-ttu-id="315fb-150">[SQL Server des extensions spécifiques in-process à ADO.NET](../../clr-integration-data-access-in-process-ado-net/sql-server-in-process-specific-extensions-to-ado-net.md) </span><span class="sxs-lookup"><span data-stu-id="315fb-150">[SQL Server In-Process Specific Extensions to ADO.NET](../../clr-integration-data-access-in-process-ado-net/sql-server-in-process-specific-extensions-to-ado-net.md) </span></span>  
 <span data-ttu-id="315fb-151">[Débogage d’objets de base de données CLR](../debugging-clr-database-objects.md) </span><span class="sxs-lookup"><span data-stu-id="315fb-151">[Debugging CLR Database Objects](../debugging-clr-database-objects.md) </span></span>  
 [<span data-ttu-id="315fb-152">Sécurité de l'intégration du CLR</span><span class="sxs-lookup"><span data-stu-id="315fb-152">CLR Integration Security</span></span>](../security/clr-integration-security.md)  
  
  
