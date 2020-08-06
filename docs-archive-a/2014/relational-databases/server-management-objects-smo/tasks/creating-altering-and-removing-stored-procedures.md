---
title: Création, modification et suppression de procédures stockées | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- stored procedures [SMO]
ms.assetid: 2a072f9c-8f11-4364-ab71-3990735a8d66
author: stevestein
ms.author: sstein
ms.openlocfilehash: 73e8313f3befd4c7c5cb20cdb6649c87ea72b037
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613939"
---
# <a name="creating-altering-and-removing-stored-procedures"></a><span data-ttu-id="7b08a-102">Création, modification et suppression des procédures stockées</span><span class="sxs-lookup"><span data-stu-id="7b08a-102">Creating, Altering, and Removing Stored Procedures</span></span>
  <span data-ttu-id="7b08a-103">Dans SMO ([!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Management Objects), les procédures stockées sont représentées par l'objet <xref:Microsoft.SqlServer.Management.Smo.StoredProcedure>.</span><span class="sxs-lookup"><span data-stu-id="7b08a-103">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Management Objects (SMO), stored procedures are represented by the <xref:Microsoft.SqlServer.Management.Smo.StoredProcedure> object.</span></span>  
  
 <span data-ttu-id="7b08a-104">La création d'un objet <xref:Microsoft.SqlServer.Management.Smo.StoredProcedure> dans SMO requiert la définition de la propriété <xref:Microsoft.SqlServer.Management.Smo.StoredProcedure.TextBody%2A> sur le script [!INCLUDE[tsql](../../../includes/tsql-md.md)] qui définit la procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="7b08a-104">Creating a <xref:Microsoft.SqlServer.Management.Smo.StoredProcedure> object in SMO requires setting the <xref:Microsoft.SqlServer.Management.Smo.StoredProcedure.TextBody%2A> property to the [!INCLUDE[tsql](../../../includes/tsql-md.md)] script that defines the stored procedure.</span></span> <span data-ttu-id="7b08a-105">Les paramètres requièrent le \@ préfixe et doivent être créés individuellement en utilisant <xref:Microsoft.SqlServer.Management.Smo.StoredProcedureParameter> des objets et en ajoutant à la <xref:Microsoft.SqlServer.Management.Smo.StoredProcedureParameter> collection de l' <xref:Microsoft.SqlServer.Management.Smo.StoredProcedure> objet.</span><span class="sxs-lookup"><span data-stu-id="7b08a-105">Parameters require the \@ prefix and must be created individually by using <xref:Microsoft.SqlServer.Management.Smo.StoredProcedureParameter> objects and adding to the <xref:Microsoft.SqlServer.Management.Smo.StoredProcedureParameter> collection of the <xref:Microsoft.SqlServer.Management.Smo.StoredProcedure> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b08a-106">Exemple</span><span class="sxs-lookup"><span data-stu-id="7b08a-106">Example</span></span>  
 <span data-ttu-id="7b08a-107">Pour utiliser un exemple de code qui est fourni, vous devrez choisir l'environnement de programmation, le modèle de programmation et le langage de programmation dans lequel créer votre application.</span><span class="sxs-lookup"><span data-stu-id="7b08a-107">To use any code example that is provided, you will have to choose the programming environment, the programming template, and the programming language in which to create your application.</span></span> <span data-ttu-id="7b08a-108">Pour plus d’informations, consultez [créer un projet Visual Basic Smo dans Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) ou [créer un projet Visual C&#35; Smo dans Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="7b08a-108">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) or [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="creating-altering-and-removing-a-stored-procedure-in-visual-basic"></a><span data-ttu-id="7b08a-109">Création, modification et suppression d'une procédure stockée en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7b08a-109">Creating, Altering, and Removing a Stored Procedure in Visual Basic</span></span>  
 <span data-ttu-id="7b08a-110">Cet exemple de code montre comment créer une procédure stockée pour la base de données [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7b08a-110">This code example shows how to create a stored procedure for the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] database.</span></span> <span data-ttu-id="7b08a-111">L'exemple retourne le nom d'un employé lorsque le numéro d'ID d'employé est fourni.</span><span class="sxs-lookup"><span data-stu-id="7b08a-111">The example returns the last name of an employee when it is given the employee ID number.</span></span> <span data-ttu-id="7b08a-112">La procédure stockée requiert un paramètre d'entrée pour spécifier le numéro d'ID d'employé et un paramètre de sortie pour retourner le nom de l'employé.</span><span class="sxs-lookup"><span data-stu-id="7b08a-112">The stored procedure requires one input parameter to specify the employee ID number and one output parameter to return the last name of the employee.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBStoredProcs1](SMO How to#SMO_VBStoredProcs1)]  -->  
  
## <a name="creating-altering-and-removing-a-stored-procedure-in-visual-c"></a><span data-ttu-id="7b08a-113">Création, modification et suppression d'une procédure stockée en Visual C#</span><span class="sxs-lookup"><span data-stu-id="7b08a-113">Creating, Altering, and Removing a Stored Procedure in Visual C#</span></span>  
 <span data-ttu-id="7b08a-114">Cet exemple de code montre comment créer une procédure stockée pour la base de données [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7b08a-114">This code example shows how to create a stored procedure for the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] database.</span></span> <span data-ttu-id="7b08a-115">L'exemple retourne le nom d'un employé lorsque le numéro d'ID d'employé est fourni (`BusinessEntityID`).</span><span class="sxs-lookup"><span data-stu-id="7b08a-115">The example returns the last name of an employee when it is given the employee ID number (`BusinessEntityID`).</span></span> <span data-ttu-id="7b08a-116">La procédure stockée requiert un paramètre d'entrée pour spécifier le numéro d'ID d'employé et un paramètre de sortie pour retourner le nom de l'employé.</span><span class="sxs-lookup"><span data-stu-id="7b08a-116">The stored procedure requires one input parameter to specify the employee ID number and one output parameter to return the last name of the employee.</span></span>  
  
```csharp
{  
            //Connect to the local, default instance of SQL Server.   
            Server srv;  
            srv = new Server();  
            //Reference the AdventureWorks2012 database.   
            Database db;  
            db = srv.Databases["AdventureWorks2012"];  
            //Define a StoredProcedure object variable by supplying the parent database and name arguments in the constructor.   
            StoredProcedure sp;  
            sp = new StoredProcedure(db, "GetLastNameByBusinessEntityID");  
            //Set the TextMode property to false and then set the other object properties.   
            sp.TextMode = false;  
            sp.AnsiNullsStatus = false;  
            sp.QuotedIdentifierStatus = false;  
            //Add two parameters.   
            StoredProcedureParameter param;  
            param = new StoredProcedureParameter(sp, "@empval", DataType.Int);  
            sp.Parameters.Add(param);  
            StoredProcedureParameter param2;  
            param2 = new StoredProcedureParameter(sp, "@retval", DataType.NVarChar(50));  
            param2.IsOutputParameter = true;  
            sp.Parameters.Add(param2);  
            //Set the TextBody property to define the stored procedure.   
            string stmt;  
            stmt = " SELECT @retval = (SELECT LastName FROM Person.Person,HumanResources.Employee WHERE Person.Person.BusinessEntityID = HumanResources.Employee.BusinessentityID AND HumanResources.Employee.BusinessEntityID = @empval )";  
            sp.TextBody = stmt;  
            //Create the stored procedure on the instance of SQL Server.   
            sp.Create();  
            //Modify a property and run the Alter method to make the change on the instance of SQL Server.   
            sp.QuotedIdentifierStatus = true;  
            sp.Alter();  
            //Remove the stored procedure.   
            sp.Drop();  
        }  
```  
  
## <a name="creating-altering-and-removing-a-stored-procedure-in-powershell"></a><span data-ttu-id="7b08a-117">Création, modification et suppression d'une procédure stockée dans PowerShell</span><span class="sxs-lookup"><span data-stu-id="7b08a-117">Creating, Altering, and Removing a Stored Procedure in PowerShell</span></span>  
 <span data-ttu-id="7b08a-118">Cet exemple de code montre comment créer une procédure stockée pour la base de données [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7b08a-118">This code example shows how to create a stored procedure for the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] database.</span></span> <span data-ttu-id="7b08a-119">L'exemple retourne le nom d'un employé lorsque le numéro d'ID d'employé est fourni (`BusinessEntityID`).</span><span class="sxs-lookup"><span data-stu-id="7b08a-119">The example returns the last name of an employee when it is given the employee ID number (`BusinessEntityID`).</span></span> <span data-ttu-id="7b08a-120">La procédure stockée requiert un paramètre d'entrée pour spécifier le numéro d'ID d'employé et un paramètre de sortie pour retourner le nom de l'employé.</span><span class="sxs-lookup"><span data-stu-id="7b08a-120">The stored procedure requires one input parameter to specify the employee ID number and one output parameter to return the last name of the employee.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server and get a reference to AdventureWorks2012  
CD \sql\localhost\default\databases  
$db = Get-Item Adventureworks2012  
  
# Define a StoredProcedure object variable by supplying the parent database and name arguments in the constructor.
$sp = New-Object -TypeName Microsoft.SqlServer.Management.SMO.StoredProcedure -argumentlist $db, "GetLastNameByBusinessEntityID"  
  
#Set the TextMode property to false and then set the other object properties.
$sp.TextMode = $false  
$sp.AnsiNullsStatus = $false  
$sp.QuotedIdentifierStatus = $false  
  
# Add two parameters  
$type = [Microsoft.SqlServer.Management.SMO.Datatype]::Int  
$param  = New-Object -TypeName Microsoft.SqlServer.Management.SMO.StoredProcedureParameter -argumentlist $sp,"@empval",$type  
$sp.Parameters.Add($param)  
  
$type = [Microsoft.SqlServer.Management.SMO.DataType]::NVarChar(50)  
$param2  = New-Object -TypeName Microsoft.SqlServer.Management.SMO.StoredProcedureParameter -argumentlist $sp,"@retval",$type  
$param2.IsOutputParameter = $true  
$sp.Parameters.Add($param2)  
  
#Set the TextBody property to define the stored procedure.
$sp.TextBody =  " SELECT @retval = (SELECT LastName FROM Person.Person,HumanResources.Employee WHERE Person.Person.BusinessEntityID = HumanResources.Employee.BusinessentityID AND HumanResources.Employee.BusinessEntityID = @empval )"  
  
# Create the stored procedure on the instance of SQL Server.
$sp.Create()  
  
# Modify a property and run the Alter method to make the change on the instance of SQL Server.
$sp.QuotedIdentifierStatus = $true  
$sp.Alter()  
  
#Remove the stored procedure.
$sp.Drop()  
```  
  
## <a name="see-also"></a><span data-ttu-id="7b08a-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7b08a-121">See Also</span></span>  
 <xref:Microsoft.SqlServer.Management.Smo.StoredProcedure>  
