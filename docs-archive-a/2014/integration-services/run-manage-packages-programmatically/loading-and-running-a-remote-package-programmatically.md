---
title: Chargement et exécution d’un package distant par programmation | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- Integration Services packages, running
- packages [Integration Services], running
- remote packages [Integration Services]
ms.assetid: 9f6ef376-3408-46bf-b5fa-fc7b18c689c9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 06565140ae8ea3603461e2944e242aa91213de47
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707679"
---
# <a name="loading-and-running-a-remote-package-programmatically"></a><span data-ttu-id="f24de-102">Chargement et exécution d'un package distant par programme</span><span class="sxs-lookup"><span data-stu-id="f24de-102">Loading and Running a Remote Package Programmatically</span></span>
  <span data-ttu-id="f24de-103">Pour exécuter des packages distants à partir d'un ordinateur local sur lequel [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] n'est pas installé, démarrez les packages afin qu'ils s'exécutent sur l'ordinateur distant sur lequel [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] est installé.</span><span class="sxs-lookup"><span data-stu-id="f24de-103">To run remote packages from a local computer that does not have [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] installed, start the packages so that they run on the remote computer on which [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] is installed.</span></span> <span data-ttu-id="f24de-104">Pour cela, vous faites utiliser par l'ordinateur local l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], un service Web ou un composant distant pour démarrer les packages sur l'ordinateur distant.</span><span class="sxs-lookup"><span data-stu-id="f24de-104">You do this by having the local computer use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, a Web service, or a remote component to start the packages on the remote computer.</span></span> <span data-ttu-id="f24de-105">Si vous essayez de démarrer directement les packages distants à partir de l'ordinateur local, les packages se chargeront sur l'ordinateur local et essayeront de s'exécuter à partir de ce dernier.</span><span class="sxs-lookup"><span data-stu-id="f24de-105">If you try to start the remote packages directly from the local computer, the packages will load onto and try to run from the local computer.</span></span> <span data-ttu-id="f24de-106">Si [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] n'est pas installé sur l'ordinateur local, les packages ne s'exécuteront pas.</span><span class="sxs-lookup"><span data-stu-id="f24de-106">If the local computer does not have [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] installed, the packages will not run.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f24de-107">Vous ne pouvez pas exécuter de packages en dehors de [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] sur un ordinateur client sur lequel [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] n’est pas installé, et les termes de votre licence [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ne vous permettent peut-être pas d’installer [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sur d’autres ordinateurs.</span><span class="sxs-lookup"><span data-stu-id="f24de-107">You cannot run packages outside [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] on a client computer that does not have [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] installed, and the terms of your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] licensing might not let you install [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] on additional computers.</span></span> <span data-ttu-id="f24de-108">([!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] est un composant serveur et n'est pas redistribuable aux ordinateurs clients.)</span><span class="sxs-lookup"><span data-stu-id="f24de-108">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] is a server component and is not redistributable to client computers.</span></span>  
  
 <span data-ttu-id="f24de-109">Alternativement, vous pouvez exécuter un package distant à partir d'un ordinateur local sur lequel [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] est installé.</span><span class="sxs-lookup"><span data-stu-id="f24de-109">Alternately, you can run a remote package from a local computer that has [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] installed.</span></span> <span data-ttu-id="f24de-110">Pour plus d’informations, consultez [Chargement et exécution d’un package local par programmation](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="f24de-110">For more information, see [Loading and Running a Local Package Programmatically](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md).</span></span>  
  
##  <a name="running-a-remote-package-on-the-remote-computer"></a><a name="top"></a> <span data-ttu-id="f24de-111">Exécution d’un package distant sur l’ordinateur distant</span><span class="sxs-lookup"><span data-stu-id="f24de-111">Running a Remote Package on the Remote Computer</span></span>  
 <span data-ttu-id="f24de-112">Comme mentionné précédemment, il existe plusieurs manières d'exécuter un package distant sur un serveur distant :</span><span class="sxs-lookup"><span data-stu-id="f24de-112">As mentioned above, there are multiple ways in which you can run a remote package on a remote server:</span></span>  
  
-   [<span data-ttu-id="f24de-113">Utiliser SQL Server Agent pour exécuter le package distant par programmation</span><span class="sxs-lookup"><span data-stu-id="f24de-113">Use SQL Server Agent to run the remote package programmatically</span></span>](#agent)  
  
-   [<span data-ttu-id="f24de-114">Utiliser un service web ou un composant distant pour exécuter le package distant par programmation</span><span class="sxs-lookup"><span data-stu-id="f24de-114">Use a Web service or remote component to run the remote package programmatically</span></span>](#service)  
  
 <span data-ttu-id="f24de-115">Presque toutes les méthodes utilisées dans cette rubrique pour charger et enregistrer des packages requièrent une référence à l'assembly `Microsoft.SqlServer.ManagedDTS`.</span><span class="sxs-lookup"><span data-stu-id="f24de-115">Almost all the methods that are used in this topic to load and save packages require a reference to the `Microsoft.SqlServer.ManagedDTS` assembly.</span></span> <span data-ttu-id="f24de-116">L’exception est l’approche ADO.NET illustrée dans cette rubrique pour l’exécution de la procédure stockée **sp_start_job** , qui requiert uniquement une référence à `System.Data` .</span><span class="sxs-lookup"><span data-stu-id="f24de-116">The exception is the ADO.NET approach demonstrated in this topic for executing the **sp_start_job** stored procedure, which requires only a reference to `System.Data`.</span></span> <span data-ttu-id="f24de-117">Après avoir ajouté la référence à l'assembly `Microsoft.SqlServer.ManagedDTS` dans un nouveau projet, importez l'espace de noms <xref:Microsoft.SqlServer.Dts.Runtime> à l'aide d'une instruction `using` ou `Imports`.</span><span class="sxs-lookup"><span data-stu-id="f24de-117">After you add the reference to the `Microsoft.SqlServer.ManagedDTS` assembly in a new project, import the <xref:Microsoft.SqlServer.Dts.Runtime> namespace with a `using` or `Imports` statement.</span></span>  
  
###  <a name="using-sql-server-agent-to-run-a-remote-package-programmatically-on-the-server"></a><a name="agent"></a> <span data-ttu-id="f24de-118">Utilisation de SQL Server Agent pour exécuter par programmation un package distant sur le serveur</span><span class="sxs-lookup"><span data-stu-id="f24de-118">Using SQL Server Agent to Run a Remote Package Programmatically on the Server</span></span>  
 <span data-ttu-id="f24de-119">L'exemple de code suivant montre comment utiliser par programme l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour exécuter un package distant sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="f24de-119">The following code sample demonstrates how to programmatically use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to run a remote package on the server.</span></span> <span data-ttu-id="f24de-120">L’exemple de code appelle la procédure stockée système, **sp_start_job**, qui lance un travail de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="f24de-120">The code sample calls the system stored procedure, **sp_start_job**, which launches a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job.</span></span> <span data-ttu-id="f24de-121">Le travail que la procédure lance est nommé `RunSSISPackage`, et ce travail se trouve sur l'ordinateur distant.</span><span class="sxs-lookup"><span data-stu-id="f24de-121">The job that the procedure launches is named `RunSSISPackage`, and this job is on the remote computer.</span></span> <span data-ttu-id="f24de-122">Le travail `RunSSISPackage` exécute alors le package sur l'ordinateur distant.</span><span class="sxs-lookup"><span data-stu-id="f24de-122">The `RunSSISPackage` job then runs the package on the remote computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f24de-123">La valeur retournée par la procédure stockée **sp_start_job** indique si la procédure stockée a pu démarrer correctement le travail de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="f24de-123">The return value of the **sp_start_job** stored procedure indicates whether the stored procedure was able to start the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job successfully.</span></span> <span data-ttu-id="f24de-124">La valeur de retour n'indique pas si le package a réussi ou a échoué.</span><span class="sxs-lookup"><span data-stu-id="f24de-124">The return value does not indicate whether the package succeeded or failed.</span></span>  
  
 <span data-ttu-id="f24de-125">Pour plus d’informations sur la résolution des problèmes liés aux packages que vous exécutez à partir des travaux de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], consultez l’article Microsoft intitulé [Un package SSIS n’est pas exécuté quand vous appelez le package SSIS à partir d’une étape de travail de SQL Server Agent](https://support.microsoft.com/kb/918760).</span><span class="sxs-lookup"><span data-stu-id="f24de-125">For information on troubleshooting packages that are run from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs, see the Microsoft article, [An SSIS package does not run when you call the SSIS package from a SQL Server Agent job step](https://support.microsoft.com/kb/918760).</span></span>  
  
### <a name="sample-code"></a><span data-ttu-id="f24de-126">Exemple de code</span><span class="sxs-lookup"><span data-stu-id="f24de-126">Sample Code</span></span>  
  
```vb  
Imports System.Data  
Imports System.Data.SqlClient  
  
Module Module1  
  
  Sub Main()  
  
    Dim jobConnection As SqlConnection  
    Dim jobCommand As SqlCommand  
    Dim jobReturnValue As SqlParameter  
    Dim jobParameter As SqlParameter  
    Dim jobResult As Integer  
  
    jobConnection = New SqlConnection("Data Source=(local);Initial Catalog=msdb;Integrated Security=SSPI")  
    jobCommand = New SqlCommand("sp_start_job", jobConnection)  
    jobCommand.CommandType = CommandType.StoredProcedure  
  
    jobReturnValue = New SqlParameter("@RETURN_VALUE", SqlDbType.Int)  
    jobReturnValue.Direction = ParameterDirection.ReturnValue  
    jobCommand.Parameters.Add(jobReturnValue)  
  
    jobParameter = New SqlParameter("@job_name", SqlDbType.VarChar)  
    jobParameter.Direction = ParameterDirection.Input  
    jobCommand.Parameters.Add(jobParameter)  
    jobParameter.Value = "RunSSISPackage"  
  
    jobConnection.Open()  
    jobCommand.ExecuteNonQuery()  
    jobResult = DirectCast(jobCommand.Parameters("@RETURN_VALUE").Value, Integer)  
    jobConnection.Close()  
  
    Select Case jobResult  
      Case 0  
        Console.WriteLine("SQL Server Agent job, RunSISSPackage, started successfully.")  
      Case Else  
        Console.WriteLine("SQL Server Agent job, RunSISSPackage, failed to start.")  
    End Select  
    Console.Read()  
  
  End Sub  
  
End Module  
```  
  
```csharp  
using System;  
using System.Data;  
using System.Data.SqlClient;  
  
namespace LaunchSSISPackageAgent_CS  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      SqlConnection jobConnection;  
      SqlCommand jobCommand;  
      SqlParameter jobReturnValue;  
      SqlParameter jobParameter;  
      int jobResult;  
  
      jobConnection = new SqlConnection("Data Source=(local);Initial Catalog=msdb;Integrated Security=SSPI");  
      jobCommand = new SqlCommand("sp_start_job", jobConnection);  
      jobCommand.CommandType = CommandType.StoredProcedure;  
  
      jobReturnValue = new SqlParameter("@RETURN_VALUE", SqlDbType.Int);  
      jobReturnValue.Direction = ParameterDirection.ReturnValue;  
      jobCommand.Parameters.Add(jobReturnValue);  
  
      jobParameter = new SqlParameter("@job_name", SqlDbType.VarChar);  
      jobParameter.Direction = ParameterDirection.Input;  
      jobCommand.Parameters.Add(jobParameter);  
      jobParameter.Value = "RunSSISPackage";  
  
      jobConnection.Open();  
      jobCommand.ExecuteNonQuery();  
      jobResult = (Int32)jobCommand.Parameters["@RETURN_VALUE"].Value;  
      jobConnection.Close();  
  
      switch (jobResult)  
      {  
        case 0:  
          Console.WriteLine("SQL Server Agent job, RunSISSPackage, started successfully.");  
          break;  
        default:  
          Console.WriteLine("SQL Server Agent job, RunSISSPackage, failed to start.");  
          break;  
      }  
      Console.Read();  
    }  
  }  
}  
```  
  
 
  
###  <a name="using-a-web-service-or-remote-component-to-run-a-remote-package-programmatically"></a><a name="service"></a> <span data-ttu-id="f24de-127">Utilisation d’un service web ou d’un composant distant pour exécuter un package distant par programmation</span><span class="sxs-lookup"><span data-stu-id="f24de-127">Using a Web Service or Remote Component to Run a Remote Package Programmatically</span></span>  
 <span data-ttu-id="f24de-128">La solution précédente pour l'exécution de packages par programme sur le serveur ne requiert pas de code personnalisé sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="f24de-128">The previous solution for running packages programmatically on the server does not require any custom code on the server.</span></span> <span data-ttu-id="f24de-129">Toutefois, vous pouvez préférer une solution qui ne compte pas sur l'Agent SQL Server pour exécuter des packages.</span><span class="sxs-lookup"><span data-stu-id="f24de-129">However, you may prefer a solution that does not rely on SQL Server Agent to execute packages.</span></span> <span data-ttu-id="f24de-130">L'exemple suivant présente un service Web qui peut être créé sur le serveur pour démarrer des packages [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] localement, ainsi qu'une application de test qui peut être utilisée pour appeler le service Web à partir d'un ordinateur client.</span><span class="sxs-lookup"><span data-stu-id="f24de-130">The following example demonstrates a Web service that can be created on the server to start [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages locally, and a test application that can be used to call the Web service from a client computer.</span></span> <span data-ttu-id="f24de-131">Si vous préférez créer un composant distant au lieu d’un service web, vous pouvez utiliser la même logique de code avec très peu de changements dans un composant distant.</span><span class="sxs-lookup"><span data-stu-id="f24de-131">If you prefer to create a remote component instead of a Web service, you can use the same code logic with very few changes in a remote component.</span></span> <span data-ttu-id="f24de-132">Toutefois, un composant distant risque de requérir une configuration plus approfondie qu'un service Web.</span><span class="sxs-lookup"><span data-stu-id="f24de-132">However a remote component may require more extensive configuration than a Web service.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f24de-133">Avec ses paramètres par défaut pour l'authentification et l'autorisation, un service Web ne dispose généralement pas des autorisations suffisantes pour accéder à SQL Server ou au système de fichiers afin de charger et d'exécuter des packages.</span><span class="sxs-lookup"><span data-stu-id="f24de-133">With its default settings for authentication and authorization, a Web service generally does not have sufficient permissions to access SQL Server or the file system to load and execute packages.</span></span> <span data-ttu-id="f24de-134">Vous risquez de devoir attribuer les autorisations appropriées au service web en configurant ses paramètres d’authentification et d’autorisation dans le fichier **web.config** et en attribuant les autorisations d’accès appropriées à la base de données et au système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="f24de-134">You may have to assign appropriate permissions to the Web service by configuring its authentication and authorization settings in the **web.config** file and assigning database and file system permissions as appropriate.</span></span> <span data-ttu-id="f24de-135">La description complète des autorisations Web, de base de données et de système de fichiers sort de la portée de cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="f24de-135">A complete discussion of Web, database, and file system permissions is beyond the scope of this topic.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f24de-136">Les méthodes de la classe <xref:Microsoft.SqlServer.Dts.Runtime.Application> qui permettent d’utiliser le magasin de packages SSIS prennent uniquement en charge « . », localhost ou le nom du serveur local.</span><span class="sxs-lookup"><span data-stu-id="f24de-136">The methods of the <xref:Microsoft.SqlServer.Dts.Runtime.Application> class for working with the SSIS Package Store support only ".", localhost, or the server name for the local server.</span></span> <span data-ttu-id="f24de-137">Vous ne pouvez pas utiliser « (local) ».</span><span class="sxs-lookup"><span data-stu-id="f24de-137">You cannot use "(local)".</span></span>  
  
### <a name="sample-code"></a><span data-ttu-id="f24de-138">Exemple de code</span><span class="sxs-lookup"><span data-stu-id="f24de-138">Sample Code</span></span>  
 <span data-ttu-id="f24de-139">Les exemples de code suivants indiquent comment créer et tester le service Web.</span><span class="sxs-lookup"><span data-stu-id="f24de-139">The following code samples show how to create and test the Web service.</span></span>  
  
#### <a name="creating-the-web-service"></a><span data-ttu-id="f24de-140">Création du service Web</span><span class="sxs-lookup"><span data-stu-id="f24de-140">Creating the Web Service</span></span>  
 <span data-ttu-id="f24de-141">Un package [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] peut être chargé directement à partir d'un fichier, directement à partir de SQL Server ou à partir du magasin de packages SSIS, lequel gère le stockage des packages dans SQL Server et des dossiers spéciaux du système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="f24de-141">An [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package can be loaded directly from a file, directly from SQL Server, or from the SSIS Package Store, which manages package storage in both SQL Server and special file system folders.</span></span> <span data-ttu-id="f24de-142">Cet exemple prend en charge toutes les options disponibles en utilisant une construction `Select Case` ou `switch` pour sélectionner la syntaxe appropriée au démarrage du package et pour concaténer les arguments d'entrée convenablement.</span><span class="sxs-lookup"><span data-stu-id="f24de-142">This sample supports all the available options by using a `Select Case` or `switch` construct to select the appropriate syntax for starting the package and to concatenate the input arguments appropriately.</span></span> <span data-ttu-id="f24de-143">La méthode de service Web LaunchPackage renvoie le résultat de l'exécution du package sous la forme d'un entier plutôt que d'une valeur <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> afin que les ordinateurs clients ne requièrent pas de référence aux assemblys [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f24de-143">The LaunchPackage Web service method returns the result of package execution as an integer instead of a <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> value so that client computers do not require a reference to any [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] assemblies.</span></span>  
  
###### <a name="to-create-a-web-service-to-run-packages-on-the-server-programmatically"></a><span data-ttu-id="f24de-144">Pour créer un service Web afin d'exécuter par programme des packages sur le serveur</span><span class="sxs-lookup"><span data-stu-id="f24de-144">To create a Web service to run packages on the server programmatically</span></span>  
  
1.  <span data-ttu-id="f24de-145">Ouvrez Visual Studio et créez un projet de service Web dans votre langage de programmation préféré.</span><span class="sxs-lookup"><span data-stu-id="f24de-145">Open Visual Studio and create a Web service project in your preferred programming language.</span></span> <span data-ttu-id="f24de-146">L'exemple de code utilise le nom LaunchSSISPackageService pour le projet.</span><span class="sxs-lookup"><span data-stu-id="f24de-146">The sample code uses the name LaunchSSISPackageService for the project.</span></span>  
  
2.  <span data-ttu-id="f24de-147">Ajoutez une référence à `Microsoft.SqlServer.ManagedDTS` et ajoutez une `Imports` `using` instruction ou au fichier de code pour l’espace de noms **Microsoft. SqlServer. Dts. Runtime** .</span><span class="sxs-lookup"><span data-stu-id="f24de-147">Add a reference to `Microsoft.SqlServer.ManagedDTS` and add an `Imports` or `using` statement to the code file for the **Microsoft.SqlServer.Dts.Runtime** namespace.</span></span>  
  
3.  <span data-ttu-id="f24de-148">Collez l'exemple de code pour la méthode de service Web LaunchPackage dans la classe.</span><span class="sxs-lookup"><span data-stu-id="f24de-148">Paste the sample code for the LaunchPackage Web service method into the class.</span></span> <span data-ttu-id="f24de-149">(L'exemple présente tout le contenu de la fenêtre de code.)</span><span class="sxs-lookup"><span data-stu-id="f24de-149">(The sample shows the whole contents of the code window.)</span></span>  
  
4.  <span data-ttu-id="f24de-150">Générez et testez le service Web en fournissant un jeu de valeurs valides pour les arguments d'entrée de la méthode LaunchPackage qui pointent vers un package existant.</span><span class="sxs-lookup"><span data-stu-id="f24de-150">Build and test the Web service by providing a set of valid values for the input arguments of the LaunchPackage method that point to an existing package.</span></span> <span data-ttu-id="f24de-151">Par exemple, si package1.dtsx est stocké sur le serveur dans C:\My Packages, passez « file » comme valeur de sourceType, « C:\My Packages » comme valeur de sourceLocation et « package1 » (sans l'extension) comme valeur de packageName.</span><span class="sxs-lookup"><span data-stu-id="f24de-151">For example, if package1.dtsx is stored on the server in C:\My Packages, pass "file" as the value of the sourceType, "C:\My Packages" as the value of sourceLocation, and "package1" (without the extension) as the value of packageName.</span></span>  
  
```vb  
Imports System.Web  
Imports System.Web.Services  
Imports System.Web.Services.Protocols  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports System.IO  
  
<WebService(Namespace:="http://dtsue/")> _  
<WebServiceBinding(ConformsTo:=WsiProfiles.BasicProfile1_1)> _  
<Global.Microsoft.VisualBasic.CompilerServices.DesignerGenerated()> _  
Public Class LaunchSSISPackageService  
  Inherits System.Web.Services.WebService  
  
  ' LaunchPackage Method Parameters:  
  ' 1. sourceType: file, sql, dts  
  ' 2. sourceLocation: file system folder, (none), logical folder  
  ' 3. packageName: for file system, ".dtsx" extension is appended  
  
  <WebMethod()> _  
  Public Function LaunchPackage( _  
    ByVal sourceType As String, _  
    ByVal sourceLocation As String, _  
    ByVal packageName As String) As Integer 'DTSExecResult  
  
    Dim packagePath As String  
    Dim myPackage As Package  
    Dim integrationServices As New Application  
  
    ' Combine path and file name.  
    packagePath = Path.Combine(sourceLocation, packageName)  
  
    Select Case sourceType  
      Case "file"  
        ' Package is stored as a file.  
        ' Add extension if not present.  
        If String.IsNullOrEmpty(Path.GetExtension(packagePath)) Then  
          packagePath = String.Concat(packagePath, ".dtsx")  
        End If  
        If File.Exists(packagePath) Then  
          myPackage = integrationServices.LoadPackage(packagePath, Nothing)  
        Else  
          Throw New ApplicationException( _  
            "Invalid file location: " & packagePath)  
        End If  
      Case "sql"  
        ' Package is stored in MSDB.  
        ' Combine logical path and package name.  
        If integrationServices.ExistsOnSqlServer(packagePath, ".", String.Empty, String.Empty) Then  
          myPackage = integrationServices.LoadFromSqlServer( _  
            packageName, "(local)", String.Empty, String.Empty, Nothing)  
        Else  
          Throw New ApplicationException( _  
            "Invalid package name or location: " & packagePath)  
        End If  
      Case "dts"  
        ' Package is managed by SSIS Package Store.  
        ' Default logical paths are File System and MSDB.  
        If integrationServices.ExistsOnDtsServer(packagePath, ".") Then  
          myPackage = integrationServices.LoadFromDtsServer(packagePath, "localhost", Nothing)  
        Else  
          Throw New ApplicationException( _  
            "Invalid package name or location: " & packagePath)  
        End If  
      Case Else  
        Throw New ApplicationException( _  
          "Invalid sourceType argument: valid values are 'file', 'sql', and 'dts'.")  
    End Select  
  
    Return myPackage.Execute()  
  
  End Function  
  
End Class  
```  
  
```csharp  
using System;  
using System.Web;  
using System.Web.Services;  
using System.Web.Services.Protocols;  
using Microsoft.SqlServer.Dts.Runtime;  
using System.IO;  
  
[WebService(Namespace = "http://dtsue/")]  
[WebServiceBinding(ConformsTo = WsiProfiles.BasicProfile1_1)]  
public class LaunchSSISPackageServiceCS : System.Web.Services.WebService  
{  
  public LaunchSSISPackageServiceCS()  
  {  
    }  
  
  // LaunchPackage Method Parameters:  
  // 1. sourceType: file, sql, dts  
  // 2. sourceLocation: file system folder, (none), logical folder  
  // 3. packageName: for file system, ".dtsx" extension is appended  
  
  [WebMethod]  
  public int LaunchPackage(string sourceType, string sourceLocation, string packageName)  
  {   
  
    string packagePath;  
    Package myPackage;  
    Application integrationServices = new Application();  
  
    // Combine path and file name.  
    packagePath = Path.Combine(sourceLocation, packageName);  
  
    switch(sourceType)  
    {  
      case "file":  
        // Package is stored as a file.  
        // Add extension if not present.  
        if (String.IsNullOrEmpty(Path.GetExtension(packagePath)))  
        {  
          packagePath = String.Concat(packagePath, ".dtsx");  
        }  
        if (File.Exists(packagePath))  
        {  
          myPackage = integrationServices.LoadPackage(packagePath, null);  
        }  
        else  
        {  
          throw new ApplicationException("Invalid file location: "+packagePath);  
        }  
        break;  
      case "sql":  
        // Package is stored in MSDB.  
        // Combine logical path and package name.  
        if (integrationServices.ExistsOnSqlServer(packagePath, ".", String.Empty, String.Empty))  
        {  
          myPackage = integrationServices.LoadFromSqlServer(packageName, "(local)", String.Empty, String.Empty, null);  
        }  
        else  
        {  
          throw new ApplicationException("Invalid package name or location: "+packagePath);  
        }  
        break;  
      case "dts":  
        // Package is managed by SSIS Package Store.  
        // Default logical paths are File System and MSDB.  
        if (integrationServices.ExistsOnDtsServer(packagePath, "."))  
        {  
          myPackage = integrationServices.LoadFromDtsServer(packagePath, "localhost", null);  
        }  
        else  
        {  
          throw new ApplicationException("Invalid package name or location: "+packagePath);  
        }  
        break;  
      default:  
        throw new ApplicationException("Invalid sourceType argument: valid values are 'file', 'sql', and 'dts'.");  
    }  
  
    return (Int32)myPackage.Execute();  
  
  }  
  
}  
```  
  
#### <a name="testing-the-web-service"></a><span data-ttu-id="f24de-152">Test du service Web</span><span class="sxs-lookup"><span data-stu-id="f24de-152">Testing the Web Service</span></span>  
 <span data-ttu-id="f24de-153">L'exemple d'application console suivant utilise le service Web pour exécuter un package.</span><span class="sxs-lookup"><span data-stu-id="f24de-153">The following sample console application uses the Web service to run a package.</span></span> <span data-ttu-id="f24de-154">La méthode LaunchPackage du service Web renvoie le résultat de l'exécution du package sous la forme d'un entier plutôt que d'une valeur <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> afin que les ordinateurs clients ne requièrent pas de référence aux assemblys [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f24de-154">The LaunchPackage method of the Web service returns the result of package execution as an integer instead of a <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> value so that client computers do not require a reference to any [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] assemblies.</span></span> <span data-ttu-id="f24de-155">L'exemple crée une énumération privée dont les valeurs reflètent les valeurs <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> pour rapporter les résultats de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="f24de-155">The sample creates a private enumeration whose values mirror the <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> values to report the results of execution.</span></span>  
  
###### <a name="to-create-a-console-application-to-test-the-web-service"></a><span data-ttu-id="f24de-156">Pour créer une application console afin de tester le service Web</span><span class="sxs-lookup"><span data-stu-id="f24de-156">To create a console application to test the Web service</span></span>  
  
1.  <span data-ttu-id="f24de-157">Dans Visual Studio, ajoutez une nouvelle application console, à l'aide de votre langage de programmation préféré, à la même solution que celle qui contient le projet de service Web.</span><span class="sxs-lookup"><span data-stu-id="f24de-157">In Visual Studio, add a new console application, using your preferred programming language, to the same solution that contains the Web service project.</span></span> <span data-ttu-id="f24de-158">L'exemple de code utilise le nom LaunchSSISPackageTest pour le projet.</span><span class="sxs-lookup"><span data-stu-id="f24de-158">The sample code uses the name LaunchSSISPackageTest for the project.</span></span>  
  
2.  <span data-ttu-id="f24de-159">Définissez la nouvelle application console en tant que projet de démarrage dans la solution.</span><span class="sxs-lookup"><span data-stu-id="f24de-159">Set the new console application as the startup project in the solution.</span></span>  
  
3.  <span data-ttu-id="f24de-160">Ajoutez une référence Web pour le projet de service Web.</span><span class="sxs-lookup"><span data-stu-id="f24de-160">Add a Web reference for the Web service project.</span></span> <span data-ttu-id="f24de-161">Si nécessaire, ajustez la déclaration de variable dans l'exemple de code pour le nom que vous attribuez à l'objet proxy de service Web.</span><span class="sxs-lookup"><span data-stu-id="f24de-161">If necessary, adjust the variable declaration in the sample code for the name that you assign to the Web service proxy object.</span></span>  
  
4.  <span data-ttu-id="f24de-162">Collez l'exemple de code pour la routine principale et l'énumération privée dans le code.</span><span class="sxs-lookup"><span data-stu-id="f24de-162">Paste the sample code for the Main routine and the private enumeration into the code.</span></span> <span data-ttu-id="f24de-163">(L'exemple présente tout le contenu de la fenêtre de code.)</span><span class="sxs-lookup"><span data-stu-id="f24de-163">(The sample shows the whole contents of the code window.)</span></span>  
  
5.  <span data-ttu-id="f24de-164">Modifiez la ligne de code qui appelle la méthode LaunchPackage afin de fournir un jeu de valeurs valides pour les arguments d'entrée qui pointent vers un package existant.</span><span class="sxs-lookup"><span data-stu-id="f24de-164">Edit the line of code that calls the LaunchPackage method to provide a set of valid values for the input arguments that point to an existing package.</span></span> <span data-ttu-id="f24de-165">Par exemple, si package1.dtsx est stocké sur le serveur dans C:\My Packages, passez « file » comme valeur de `sourceType`, « C:\My Packages » comme valeur de `sourceLocation` et « package1 » (sans l'extension) comme valeur de `packageName`.</span><span class="sxs-lookup"><span data-stu-id="f24de-165">For example, if package1.dtsx is stored on the server in C:\My Packages, pass "file" as the value of `sourceType`, "C:\My Packages" as the value of `sourceLocation`, and "package1" (without the extension) as the value of `packageName`.</span></span>  
  
```vb  
Module LaunchSSISPackageTest  
  
  Sub Main()  
  
    Dim launchPackageService As New LaunchSSISPackageService.LaunchSSISPackageService  
    Dim packageResult As Integer  
  
    Try  
      packageResult = launchPackageService.LaunchPackage("sql", String.Empty, "SimpleTestPackage")  
    Catch ex As Exception  
      ' The type of exception returned by a Web service is:  
      '  System.Web.Services.Protocols.SoapException  
      Console.WriteLine("The following exception occurred: " & ex.Message)  
    End Try  
  
    Console.WriteLine(CType(packageResult, PackageExecutionResult).ToString)  
    Console.ReadKey()  
  
  End Sub  
  
  Private Enum PackageExecutionResult  
    PackageSucceeded  
    PackageFailed  
    PackageCompleted  
    PackageWasCancelled  
  End Enum  
  
End Module  
```  
  
```csharp  
using System;  
  
namespace LaunchSSISPackageSvcTestCS  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      LaunchSSISPackageServiceCS.LaunchSSISPackageServiceCS launchPackageService = new LaunchSSISPackageServiceCS.LaunchSSISPackageServiceCS();  
      int packageResult = 0;  
  
      try  
      {  
        packageResult = launchPackageService.LaunchPackage("sql", String.Empty, "SimpleTestPackage");  
      }  
      catch (Exception ex)  
      {  
        // The type of exception returned by a Web service is:  
        //  System.Web.Services.Protocols.SoapException  
        Console.WriteLine("The following exception occurred: " + ex.Message);  
      }  
  
      Console.WriteLine(((PackageExecutionResult)packageResult).ToString());  
      Console.ReadKey();  
  
    }  
  
    private enum PackageExecutionResult  
    {  
      PackageSucceeded,  
      PackageFailed,  
      PackageCompleted,  
      PackageWasCancelled  
    };  
  
  }  
}  
```  
  

  
## <a name="external-resources"></a><span data-ttu-id="f24de-166">Ressources externes</span><span class="sxs-lookup"><span data-stu-id="f24de-166">External Resources</span></span>  
  
-   <span data-ttu-id="f24de-167">Vidéo, [Procédure : automatiser l’exécution du package SSIS à l’aide de SQL Server Agent (vidéo de SQL Server)](https://technet.microsoft.com/sqlserver/ff686764.aspx), sur technet.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="f24de-167">Video, [How to: Automate SSIS Package Execution by Using the SQL Server Agent (SQL Server Video)](https://technet.microsoft.com/sqlserver/ff686764.aspx), on technet.microsoft.com</span></span>  
  
<span data-ttu-id="f24de-168">![Icône de Integration Services (petite)](../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="f24de-168">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="f24de-169">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="f24de-169">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="f24de-170">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="f24de-170">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="f24de-171">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="f24de-171">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f24de-172">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f24de-172">See Also</span></span>  
 <span data-ttu-id="f24de-173">[Comprendre les différences entre l’exécution locale et l’exécution distante](../run-manage-packages-programmatically/understanding-the-differences-between-local-and-remote-execution.md) </span><span class="sxs-lookup"><span data-stu-id="f24de-173">[Understanding the Differences between Local and Remote Execution](../run-manage-packages-programmatically/understanding-the-differences-between-local-and-remote-execution.md) </span></span>  
 <span data-ttu-id="f24de-174">[Chargement et exécution d’un package local par programmation](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md) </span><span class="sxs-lookup"><span data-stu-id="f24de-174">[Loading and Running a Local Package Programmatically](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md) </span></span>  
 [<span data-ttu-id="f24de-175">Chargement de la sortie d'un package local</span><span class="sxs-lookup"><span data-stu-id="f24de-175">Loading the Output of a Local Package</span></span>](../run-manage-packages-programmatically/loading-the-output-of-a-local-package.md)  
  
  
