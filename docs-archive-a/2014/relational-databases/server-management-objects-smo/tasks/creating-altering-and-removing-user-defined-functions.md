---
title: Création, modification et suppression de fonctions définies par l’utilisateur | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- user-defined functions [SMO]
ms.assetid: 0ebebd3b-0775-41c2-989d-aa4cf81af12a
author: stevestein
ms.author: sstein
ms.openlocfilehash: b9ff6d1b6e675d41e96f26fc24e6e0dd4ba69454
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613934"
---
# <a name="creating-altering-and-removing-user-defined-functions"></a><span data-ttu-id="e7031-102">Création, modification et suppression de fonctions définies par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="e7031-102">Creating, Altering, and Removing User-Defined Functions</span></span>
  <span data-ttu-id="e7031-103">L' <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction> objet fournit des fonctionnalités qui permettent aux utilisateurs de gérer par programme des fonctions définies par l’utilisateur dans [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e7031-103">The <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction> object provides functionality that lets users programmatically manage user-defined functions in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="e7031-104">Les fonctions définies par l'utilisateur prennent en charge les paramètres d'entrée et de sortie, ainsi que les références directes aux colonnes de table.</span><span class="sxs-lookup"><span data-stu-id="e7031-104">User-defined functions support input and output parameters, and also support direct references to table columns.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="e7031-105">requiert l'enregistrement d'assemblys dans une base de données pour que ceux-ci puissent être utilisés dans des procédures stockées, des fonctions définies par l'utilisateur, des déclencheurs et des types de données définis par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e7031-105">requires assemblies to be registered within a database before these can be used inside stored procedures, user defined functions, triggers, and user defined data types.</span></span> <span data-ttu-id="e7031-106">SMO prend en charge cette fonctionnalité avec l'objet <xref:Microsoft.SqlServer.Management.Smo.SqlAssembly>.</span><span class="sxs-lookup"><span data-stu-id="e7031-106">SMO supports this feature with the <xref:Microsoft.SqlServer.Management.Smo.SqlAssembly> object.</span></span>  
  
 <span data-ttu-id="e7031-107">L'objet <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction> référence l'assembly .NET avec les propriétés <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction.AssemblyName%2A>, <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction.ClassName%2A> et <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction.MethodName%2A>.</span><span class="sxs-lookup"><span data-stu-id="e7031-107">The <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction> object references the .NET assembly with the <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction.AssemblyName%2A>, <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction.ClassName%2A>, and <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction.MethodName%2A> properties.</span></span>  
  
 <span data-ttu-id="e7031-108">Lorsque l'objet <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction> référence un assembly .NET, vous devez enregistrer l'assembly en créant un objet <xref:Microsoft.SqlServer.Management.Smo.SqlAssembly> et en l'ajoutant à l'objet <xref:Microsoft.SqlServer.Management.Smo.SqlAssemblyCollection>, qui fait partie de l'objet <xref:Microsoft.SqlServer.Management.Smo.Database>.</span><span class="sxs-lookup"><span data-stu-id="e7031-108">When the <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction> object references a .NET assembly, you must register the assembly by creating a <xref:Microsoft.SqlServer.Management.Smo.SqlAssembly> object and adding it to the <xref:Microsoft.SqlServer.Management.Smo.SqlAssemblyCollection> object, which belongs to the <xref:Microsoft.SqlServer.Management.Smo.Database> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7031-109">Exemple</span><span class="sxs-lookup"><span data-stu-id="e7031-109">Example</span></span>  
 <span data-ttu-id="e7031-110">Pour utiliser un exemple de code qui est fourni, vous devrez choisir l'environnement de programmation, le modèle de programmation et le langage de programmation dans lequel créer votre application.</span><span class="sxs-lookup"><span data-stu-id="e7031-110">To use any code example that is provided, you will have to choose the programming environment, the programming template, and the programming language in which to create your application.</span></span> <span data-ttu-id="e7031-111">Pour plus d’informations, consultez [créer un projet Visual Basic Smo dans Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) ou [créer un projet Visual C&#35; Smo dans Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="e7031-111">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) or [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="creating-a-scalar-user-defined-function-in-visual-basic"></a><span data-ttu-id="e7031-112">Création d'une fonction scalaire définie par l'utilisateur en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e7031-112">Creating a Scalar User-Defined Function in Visual Basic</span></span>  
 <span data-ttu-id="e7031-113">Cet exemple de code montre comment créer et supprimer une fonction scalaire définie par l'utilisateur qui a un paramètre d'objet <xref:System.DateTime> en entrée et un type de retour entier en [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e7031-113">This code example shows how to create and remove a scalar user-defined function that has an input <xref:System.DateTime> object parameter and an integer return type in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)].</span></span> <span data-ttu-id="e7031-114">La fonction définie par l'utilisateur est créée dans la base de données [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e7031-114">The user-defined function is created on the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] database.</span></span> <span data-ttu-id="e7031-115">L'exemple crée une fonction définie par l'utilisateur, ISOweek, qui accepte un argument de date et calcule le numéro de semaine ISO.</span><span class="sxs-lookup"><span data-stu-id="e7031-115">The example creates a user-defined function, ISOweek, which takes a date argument and calculates the ISO week number.</span></span> <span data-ttu-id="e7031-116">Pour que ce calcul puisse être correctement réalisé, la valeur 1 doit être affectée à l'option de base de données DATEFIRST avant l'appel de la fonction.</span><span class="sxs-lookup"><span data-stu-id="e7031-116">For this function to calculate correctly, the database DATEFIRST option must be set to 1 before the function is called.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBUserDefFuncs1](SMO How to#SMO_VBUserDefFuncs1)]  -->  
  
## <a name="creating-a-scalar-user-defined-function-in-visual-c"></a><span data-ttu-id="e7031-117">Création d'une fonction scalaire définie par l'utilisateur en Visual C#</span><span class="sxs-lookup"><span data-stu-id="e7031-117">Creating a Scalar User-Defined Function in Visual C#</span></span>  
 <span data-ttu-id="e7031-118">Cet exemple de code montre comment créer et supprimer une fonction scalaire définie par l'utilisateur qui a un paramètre d'objet <xref:System.DateTime> en entrée et un type de retour entier en [!INCLUDE[csprcs](../../../includes/csprcs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e7031-118">This code example shows how to create and remove a scalar user-defined function that has an input <xref:System.DateTime> object parameter and an integer return type in [!INCLUDE[csprcs](../../../includes/csprcs-md.md)].</span></span> <span data-ttu-id="e7031-119">La fonction définie par l'utilisateur est créée dans la base de données [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e7031-119">The user-defined function is created on the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] database.</span></span> <span data-ttu-id="e7031-120">L'exemple crée la fonction définie par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e7031-120">The example creates the user-defined function.</span></span> <span data-ttu-id="e7031-121">`ISOweek`.</span><span class="sxs-lookup"><span data-stu-id="e7031-121">`ISOweek`.</span></span> <span data-ttu-id="e7031-122">Cette fonction prend un argument date et calcule le numéro de semaine ISO.</span><span class="sxs-lookup"><span data-stu-id="e7031-122">This function takes a date argument and calculates the ISO week number.</span></span> <span data-ttu-id="e7031-123">Pour que ce calcul puisse être correctement réalisé, la valeur `DATEFIRST` doit être affectée à l'option de base de données `1` avant l'appel de la fonction.</span><span class="sxs-lookup"><span data-stu-id="e7031-123">For this function to calculate correctly, the database `DATEFIRST` option must be set to `1` before the function is called.</span></span>  
  
```csharp
{  
            //Connect to the local, default instance of SQL Server.   
           Server srv = new Server();  
            //Reference the AdventureWorks2012 database.   
           Database db = srv.Databases["AdventureWorks2012"];  
  
            //Define a UserDefinedFunction object variable by supplying the parent database and the name arguments in the constructor.   
            UserDefinedFunction udf = new UserDefinedFunction(db, "IsOWeek");  
  
            //Set the TextMode property to false and then set the other properties.   
            udf.TextMode = false;  
            udf.DataType = DataType.Int;  
            udf.ExecutionContext = ExecutionContext.Caller;  
            udf.FunctionType = UserDefinedFunctionType.Scalar;  
            udf.ImplementationType = ImplementationType.TransactSql;  
  
            //Add a parameter.   
  
     UserDefinedFunctionParameter par = new UserDefinedFunctionParameter(udf, "@DATE", DataType.DateTime);  
            udf.Parameters.Add(par);  
  
            //Set the TextBody property to define the user-defined function.   
            udf.TextBody = "BEGIN DECLARE @ISOweek int SET @ISOweek= DATEPART(wk,@DATE)+1 -DATEPART(wk,CAST(DATEPART(yy,@DATE) as CHAR(4))+'0104') IF (@ISOweek=0) SET @ISOweek=dbo.ISOweek(CAST(DATEPART(yy,@DATE)-1 AS CHAR(4))+'12'+ CAST(24+DATEPART(DAY,@DATE) AS CHAR(2)))+1 IF ((DATEPART(mm,@DATE)=12) AND ((DATEPART(dd,@DATE)-DATEPART(dw,@DATE))>= 28)) SET @ISOweek=1 RETURN(@ISOweek) END;";  
  
            //Create the user-defined function on the instance of SQL Server.   
            udf.Create();  
  
            //Remove the user-defined function.   
            udf.Drop();  
        }  
```  
  
## <a name="creating-a-scalar-user-defined-function-in-powershell"></a><span data-ttu-id="e7031-124">Création d'une fonction scalaire définie par l'utilisateur dans PowerShell</span><span class="sxs-lookup"><span data-stu-id="e7031-124">Creating a Scalar User-Defined Function in PowerShell</span></span>  
 <span data-ttu-id="e7031-125">Cet exemple de code montre comment créer et supprimer une fonction scalaire définie par l'utilisateur qui a un paramètre d'objet <xref:System.DateTime> en entrée et un type de retour entier en [!INCLUDE[csprcs](../../../includes/csprcs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e7031-125">This code example shows how to create and remove a scalar user-defined function that has an input <xref:System.DateTime> object parameter and an integer return type in [!INCLUDE[csprcs](../../../includes/csprcs-md.md)].</span></span> <span data-ttu-id="e7031-126">La fonction définie par l'utilisateur est créée dans la base de données [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e7031-126">The user-defined function is created on the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] database.</span></span> <span data-ttu-id="e7031-127">L'exemple crée la fonction définie par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e7031-127">The example creates the user-defined function.</span></span> <span data-ttu-id="e7031-128">`ISOweek`.</span><span class="sxs-lookup"><span data-stu-id="e7031-128">`ISOweek`.</span></span> <span data-ttu-id="e7031-129">Cette fonction prend un argument date et calcule le numéro de semaine ISO.</span><span class="sxs-lookup"><span data-stu-id="e7031-129">This function takes a date argument and calculates the ISO week number.</span></span> <span data-ttu-id="e7031-130">Pour que ce calcul puisse être correctement réalisé, la valeur `DATEFIRST` doit être affectée à l'option de base de données `1` avant l'appel de la fonction.</span><span class="sxs-lookup"><span data-stu-id="e7031-130">For this function to calculate correctly, the database `DATEFIRST` option must be set to `1` before the function is called.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server and get a reference to AdventureWorks2012  
CD \sql\localhost\default\databases  
$db = Get-Item Adventureworks2012  
  
# Define a user defined function object variable by supplying the parent database and name arguments in the constructor.
$udf  = New-Object -TypeName Microsoft.SqlServer.Management.SMO.UserDefinedFunction -argumentlist $db, "IsOWeek"  
  
# Set the TextMode property to false and then set the other properties.
$udf.TextMode = $false  
$udf.DataType = [Microsoft.SqlServer.Management.SMO.DataType]::Int
$udf.ExecutionContext = [Microsoft.SqlServer.Management.SMO.ExecutionContext]::Caller  
$udf.FunctionType = [Microsoft.SqlServer.Management.SMO.UserDefinedFunctionType]::Scalar  
$udf.ImplementationType = [Microsoft.SqlServer.Management.SMO.ImplementationType]::TransactSql  
  
# Define a Parameter object variable by supplying the parent function, name and type arguments in the constructor.  
$type = [Microsoft.SqlServer.Management.SMO.DataType]::DateTime  
$par  = New-Object -TypeName Microsoft.SqlServer.Management.SMO.UserDefinedFunctionParameter -argumentlist $udf, "@DATE",$type  
  
# Add the parameter to the function  
$udf.Parameters.Add($par)  
  
#Set the TextBody property to define the user-defined function.
$udf.TextBody = "BEGIN DECLARE @ISOweek int SET @ISOweek= DATEPART(wk,@DATE)+1 -DATEPART(wk,CAST(DATEPART(yy,@DATE) as CHAR(4))+'0104') IF (@ISOweek=0) SET @ISOweek=dbo.ISOweek(CAST(DATEPART(yy,@DATE)-1 AS CHAR(4))+'12'+ CAST(24+DATEPART(DAY,@DATE) AS CHAR(2)))+1 IF ((DATEPART(mm,@DATE)=12) AND ((DATEPART(dd,@DATE)-DATEPART(dw,@DATE))>= 28)) SET @ISOweek=1 RETURN(@ISOweek) END;"  
  
# Create the user-defined function on the instance of SQL Server.
$udf.Create()  
  
# Remove the user-defined function.
$udf.Drop()  
```  
  
## <a name="see-also"></a><span data-ttu-id="e7031-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e7031-131">See Also</span></span>  
 <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction>  
