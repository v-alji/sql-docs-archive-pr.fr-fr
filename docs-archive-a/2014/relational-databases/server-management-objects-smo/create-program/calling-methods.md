---
title: Appel des méthodes | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- methods [SMO]
- calling methods
- SQL Server Management Objects, method calling
- SMO [SQL Server], method calling
ms.assetid: c88d5c5f-9ff0-4f84-b2b6-24c6b90fa15e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 13216b4c533527d4249471073580d7c86f6b07e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704011"
---
# <a name="calling-methods"></a><span data-ttu-id="4804e-102">Appel de méthodes</span><span class="sxs-lookup"><span data-stu-id="4804e-102">Calling Methods</span></span>
  <span data-ttu-id="4804e-103">Les méthodes effectuent des tâches spécifiques relatives à l’objet, telles que l’émission d’un `Checkpoint` sur une base de données ou la demande d’une liste énumérée d’ouvertures de session pour l’instance de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4804e-103">Methods perform specific tasks related to the object, such as issuing a `Checkpoint` on a database or requesting an enumerated list of logons for the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="4804e-104">Les méthodes effectuent une opération sur un objet.</span><span class="sxs-lookup"><span data-stu-id="4804e-104">Methods perform an operation on an object.</span></span> <span data-ttu-id="4804e-105">Les méthodes peuvent accepter des paramètres et possèdent souvent une valeur de retour.</span><span class="sxs-lookup"><span data-stu-id="4804e-105">Methods can take parameters and often have a return value.</span></span> <span data-ttu-id="4804e-106">La valeur de retour peut être un type de données simple, un objet complexe ou une structure qui contient de nombreux membres.</span><span class="sxs-lookup"><span data-stu-id="4804e-106">The return value can be a simple data type, a complex object, or a structure that contains many members.</span></span>  
  
 <span data-ttu-id="4804e-107">Utilisez la gestion des exceptions pour détecter si la méthode a réussi.</span><span class="sxs-lookup"><span data-stu-id="4804e-107">Use exception handling to detect whether the method has been successful.</span></span> <span data-ttu-id="4804e-108">Pour plus d'informations, voir [Handling SMO Exceptions](handling-smo-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="4804e-108">For more information, see [Handling SMO Exceptions](handling-smo-exceptions.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="4804e-109">Exemples</span><span class="sxs-lookup"><span data-stu-id="4804e-109">Examples</span></span>  
 [!INCLUDE[ssChooseProgEnv](../../../includes/sschooseprogenv-md.md)]  
  
## <a name="using-a-simple-smo-method-in-visual-basic"></a><span data-ttu-id="4804e-110">Utilisation d'une méthode SMO simple en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4804e-110">Using a Simple SMO Method in Visual Basic</span></span>  
 <span data-ttu-id="4804e-111">Dans cet exemple, la méthode <xref:Microsoft.SqlServer.Management.Smo.Database.Create%2A> n'accepte aucun paramètre et ne possède aucune valeur de retour.</span><span class="sxs-lookup"><span data-stu-id="4804e-111">In this example, the <xref:Microsoft.SqlServer.Management.Smo.Database.Create%2A> method takes no parameters and has no return value.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBMethods1](SMO How to#SMO_VBMethods1)]  -->  
  
## <a name="using-a-simple-smo-method-in-visual-c"></a><span data-ttu-id="4804e-112">Utilisation d'une méthode SMO simple en Visual C#</span><span class="sxs-lookup"><span data-stu-id="4804e-112">Using a Simple SMO Method in Visual C#</span></span>  
 <span data-ttu-id="4804e-113">Dans cet exemple, la méthode <xref:Microsoft.SqlServer.Management.Smo.Database.Create%2A> n'accepte aucun paramètre et ne possède aucune valeur de retour.</span><span class="sxs-lookup"><span data-stu-id="4804e-113">In this example, the <xref:Microsoft.SqlServer.Management.Smo.Database.Create%2A> method takes no parameters and has no return value.</span></span>  
  
```  
{   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Define a Database object variable by supplying the parent server and the database name arguments in the constructor.   
Database db;   
db = new Database(srv, "Test_SMO_Database");   
//Call the Create method to create the database on the instance of SQL Server.   
db.Create();   
```  
  
 <span data-ttu-id="4804e-114">}</span><span class="sxs-lookup"><span data-stu-id="4804e-114">}</span></span>  
  
## <a name="using-an-smo-method-with-a-parameter-in-visual-basic"></a><span data-ttu-id="4804e-115">Utilisation d'une méthode SMO avec un paramètre en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4804e-115">Using an SMO Method with a Parameter in Visual Basic</span></span>  
 <span data-ttu-id="4804e-116">L'objet <xref:Microsoft.SqlServer.Management.Smo.Table> possède une méthode appelée <xref:Microsoft.SqlServer.Management.Smo.Table.RebuildIndexes%2A>.</span><span class="sxs-lookup"><span data-stu-id="4804e-116">The <xref:Microsoft.SqlServer.Management.Smo.Table> object has a method called <xref:Microsoft.SqlServer.Management.Smo.Table.RebuildIndexes%2A>.</span></span> <span data-ttu-id="4804e-117">Cette méthode requiert un paramètre numérique qui spécifie le `FillFactor`.</span><span class="sxs-lookup"><span data-stu-id="4804e-117">This method requires a numeric parameter that specifies the `FillFactor`.</span></span>  
  
```  
Dim srv As Server  
srv = New Server  
Dim tb As Table  
tb = srv.Databases("AdventureWorks2012").Tables("Employee", "HumanResources")  
tb.RebuildIndexes(70)  
```  
  
## <a name="using-an-smo-method-with-a-parameter-in-visual-c"></a><span data-ttu-id="4804e-118">Utilisation d'une méthode SMO avec un paramètre en Visual C#</span><span class="sxs-lookup"><span data-stu-id="4804e-118">Using an SMO Method with a Parameter in Visual C#</span></span>  
 <span data-ttu-id="4804e-119">L'objet <xref:Microsoft.SqlServer.Management.Smo.Table> possède une méthode appelée <xref:Microsoft.SqlServer.Management.Smo.Table.RebuildIndexes%2A>.</span><span class="sxs-lookup"><span data-stu-id="4804e-119">The <xref:Microsoft.SqlServer.Management.Smo.Table> object has a method called <xref:Microsoft.SqlServer.Management.Smo.Table.RebuildIndexes%2A>.</span></span> <span data-ttu-id="4804e-120">Cette méthode requiert un paramètre numérique qui spécifie le `FillFactor`.</span><span class="sxs-lookup"><span data-stu-id="4804e-120">This method requires a numeric parameter that specifies the `FillFactor`.</span></span>  
  
```  
{   
Server srv = default(Server);   
srv = new Server();   
Table tb = default(Table);   
tb = srv.Databases("AdventureWorks2012").Tables("Employee", "HumanResources");   
tb.RebuildIndexes(70);   
}   
```  
  
## <a name="using-an-enumeration-method-that-returns-a-datatable-object-in-visual-basic"></a><span data-ttu-id="4804e-121">Utilisation d'une méthode d'énumération qui retourne un objet DataTable en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4804e-121">Using an Enumeration Method that Returns a DataTable Object in Visual Basic</span></span>  
 <span data-ttu-id="4804e-122">Cette section explique comment appeler une méthode d'énumération et comment gérer les données incluses dans l'objet <xref:System.Data.DataTable> retourné.</span><span class="sxs-lookup"><span data-stu-id="4804e-122">This section describes how to call an enumeration method and how to handle the data in the returned <xref:System.Data.DataTable> object.</span></span>  
  
 <span data-ttu-id="4804e-123">La méthode <xref:Microsoft.SqlServer.Management.Smo.Server.EnumCollations%2A> retourne un objet <xref:System.Data.DataTable>, qui requiert une navigation supplémentaire pour accéder à toutes les informations de classement disponibles sur l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4804e-123">The <xref:Microsoft.SqlServer.Management.Smo.Server.EnumCollations%2A> method returns a <xref:System.Data.DataTable> object, which requires further navigation to access all available collation information about the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
```  
'Connect to the local, default instance of SQL Server.  
Dim srv As Server  
srv = New Server  
'Call the EnumCollations method and return collation information to DataTable variable.  
Dim d As DataTable  
'Select the returned data into an array of DataRow.  
d = srv.EnumCollations  
'Iterate through the rows and display collation details for the instance of SQL Server.  
Dim r As DataRow  
Dim c As DataColumn  
For Each r In d.Rows  
    Console.WriteLine("==")  
    For Each c In r.Table.Columns  
        Console.WriteLine(c.ColumnName + " = " + r(c).ToString)  
    Next  
Next  
```  
  
## <a name="using-an-enumeration-method-that-returns-a-datatable-object-in-visual-c"></a><span data-ttu-id="4804e-124">Utilisation d'une méthode d'énumération qui retourne un objet DataTable en Visual C#</span><span class="sxs-lookup"><span data-stu-id="4804e-124">Using an Enumeration Method that Returns a DataTable Object in Visual C#</span></span>  
 <span data-ttu-id="4804e-125">Cette section explique comment appeler une méthode d'énumération et comment gérer les données incluses dans l'objet <xref:System.Data.DataTable> retourné.</span><span class="sxs-lookup"><span data-stu-id="4804e-125">This section describes how to call an enumeration method and how to handle the data in the returned <xref:System.Data.DataTable> object.</span></span>  
  
 <span data-ttu-id="4804e-126">La méthode <xref:Microsoft.SqlServer.Management.Smo.Server.EnumCollations%2A> retourne un objet système <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="4804e-126">The <xref:Microsoft.SqlServer.Management.Smo.Server.EnumCollations%2A> method returns a system <xref:System.Data.DataTable> object.</span></span> <span data-ttu-id="4804e-127">L'objet <xref:System.Data.DataTable> requiert une navigation supplémentaire pour accéder à toutes les informations de classement disponibles sur l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4804e-127">The <xref:System.Data.DataTable> object requires further navigation to access all available collation information about the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
```  
//Connect to the local, default instance of SQL Server.   
{   
Server srv = default(Server);   
srv = new Server();   
//Call the EnumCollations method and return collation information to DataTable variable.   
DataTable d = default(DataTable);   
//Select the returned data into an array of DataRow.   
d = srv.EnumCollations;   
//Iterate through the rows and display collation details for the instance of SQL Server.   
DataRow r = default(DataRow);   
DataColumn c = default(DataColumn);   
foreach ( r in d.Rows) {   
  Console.WriteLine("=========");   
  foreach ( c in r.Table.Columns) {   
    Console.WriteLine(c.ColumnName + " = " + r(c).ToString);   
  }   
}   
}   
```  
  
## <a name="constructing-an-object-in-visual-basic"></a><span data-ttu-id="4804e-128">Construction d'un objet en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4804e-128">Constructing an Object in Visual Basic</span></span>  
 <span data-ttu-id="4804e-129">Le constructeur d'un objet quelconque peut être appelé au moyen de l'opérateur `New`.</span><span class="sxs-lookup"><span data-stu-id="4804e-129">The constructor of any object can be called by using the `New` operator.</span></span> <span data-ttu-id="4804e-130">Le constructeur d'objet <xref:Microsoft.SqlServer.Management.Smo.Database> est surchargé et la version du constructeur d'objet <xref:Microsoft.SqlServer.Management.Smo.Database> utilisée dans l'exemple accepte deux paramètres : l'objet parent <xref:Microsoft.SqlServer.Management.Smo.Server> auquel la base de données appartient et une chaîne qui représente le nom de la nouvelle base de données.</span><span class="sxs-lookup"><span data-stu-id="4804e-130">The <xref:Microsoft.SqlServer.Management.Smo.Database> object constructor is overloaded and the version of the <xref:Microsoft.SqlServer.Management.Smo.Database> object constructor that is used in the sample takes two parameters: the parent <xref:Microsoft.SqlServer.Management.Smo.Server> object to which the database belongs, and a string that represents the name of the new database.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBMethods4](SMO How to#SMO_VBMethods4)]  -->  
  
## <a name="constructing-an-object-in-visual-c"></a><span data-ttu-id="4804e-131">Construction d'un objet en Visual C#</span><span class="sxs-lookup"><span data-stu-id="4804e-131">Constructing an Object in Visual C#</span></span>  
 <span data-ttu-id="4804e-132">Le constructeur d'un objet quelconque peut être appelé au moyen de l'opérateur `New`.</span><span class="sxs-lookup"><span data-stu-id="4804e-132">The constructor of any object can be called by using the `New` operator.</span></span> <span data-ttu-id="4804e-133">Le constructeur d'objet <xref:Microsoft.SqlServer.Management.Smo.Database> est surchargé et la version du constructeur d'objet <xref:Microsoft.SqlServer.Management.Smo.Database> utilisée dans l'exemple accepte deux paramètres : l'objet parent <xref:Microsoft.SqlServer.Management.Smo.Server> auquel la base de données appartient et une chaîne qui représente le nom de la nouvelle base de données.</span><span class="sxs-lookup"><span data-stu-id="4804e-133">The <xref:Microsoft.SqlServer.Management.Smo.Database> object constructor is overloaded and the version of the <xref:Microsoft.SqlServer.Management.Smo.Database> object constructor that is used in the sample takes two parameters: the parent <xref:Microsoft.SqlServer.Management.Smo.Server> object to which the database belongs, and a string that represents the name of the new database.</span></span>  
  
```  
{   
Server srv;   
srv = new Server();   
Table tb;   
tb = srv.Databases("AdventureWorks2012").Tables("Employee", "HumanResources");   
tb.RebuildIndexes(70);   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Declare and define a Database object by supplying the parent server and the database name arguments in the constructor.   
Database d;   
d = new Database(srv, "Test_SMO_Database");   
//Create the database on the instance of SQL Server.   
d.Create();   
Console.WriteLine(d.Name);   
}  
```  
  
## <a name="copying-an-smo-object-in-visual-basic"></a><span data-ttu-id="4804e-134">Copie d'un objet SMO en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4804e-134">Copying an SMO Object in Visual Basic</span></span>  
 <span data-ttu-id="4804e-135">Cet exemple de code utilise la méthode <xref:Microsoft.SqlServer.Management.Common.ServerConnection.Copy%2A> pour créer une copie de l'objet <xref:Microsoft.SqlServer.Management.Smo.Server>.</span><span class="sxs-lookup"><span data-stu-id="4804e-135">This code example uses the <xref:Microsoft.SqlServer.Management.Common.ServerConnection.Copy%2A> method to create a copy of the <xref:Microsoft.SqlServer.Management.Smo.Server> object.</span></span> <span data-ttu-id="4804e-136">L'objet <xref:Microsoft.SqlServer.Management.Smo.Server> représente une connexion à une instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4804e-136">The <xref:Microsoft.SqlServer.Management.Smo.Server> object represents a connection to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VCMethods6](SMO How to#SMO_VCMethods6)]  -->  
  
## <a name="copying-an-smo-object-in-visual-c"></a><span data-ttu-id="4804e-137">Copie d'un objet SMO en Visual C#</span><span class="sxs-lookup"><span data-stu-id="4804e-137">Copying an SMO Object in Visual C#</span></span>  
 <span data-ttu-id="4804e-138">Cet exemple de code utilise la méthode <xref:Microsoft.SqlServer.Management.Common.ServerConnection.Copy%2A> pour créer une copie de l'objet <xref:Microsoft.SqlServer.Management.Smo.Server>.</span><span class="sxs-lookup"><span data-stu-id="4804e-138">This code example uses the <xref:Microsoft.SqlServer.Management.Common.ServerConnection.Copy%2A> method to create a copy of the <xref:Microsoft.SqlServer.Management.Smo.Server> object.</span></span> <span data-ttu-id="4804e-139">L'objet <xref:Microsoft.SqlServer.Management.Smo.Server> représente une connexion à une instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4804e-139">The <xref:Microsoft.SqlServer.Management.Smo.Server> object represents a connection to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
```  
{   
//Connect to the local, default instance of SQL Server.   
Server srv1;   
srv1 = new Server();   
//Modify the default database and the timeout period for the connection.   
srv1.ConnectionContext.DatabaseName = "AdventureWorks2012";   
srv1.ConnectionContext.ConnectTimeout = 30;   
//Make a second connection using a copy of the ConnectionContext property and verify settings.   
Server srv2;   
srv2 = new Server(srv1.ConnectionContext.Copy);   
Console.WriteLine(srv2.ConnectionContext.ConnectTimeout.ToString);   
}  
```  
  
## <a name="monitoring-server-processes-in-visual-basic"></a><span data-ttu-id="4804e-140">Surveillance des processus serveur en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4804e-140">Monitoring Server Processes in Visual Basic</span></span>  
 <span data-ttu-id="4804e-141">Vous pouvez obtenir les informations de type d'état actuelles sur l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] par le biais des méthodes d'énumération.</span><span class="sxs-lookup"><span data-stu-id="4804e-141">You can obtain the current status type information about the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] through enumeration methods.</span></span> <span data-ttu-id="4804e-142">L'exemple de code utilise la méthode <xref:Microsoft.SqlServer.Management.Smo.Server.EnumProcesses%2A> pour découvrir des informations sur les processus en cours.</span><span class="sxs-lookup"><span data-stu-id="4804e-142">The code example uses the <xref:Microsoft.SqlServer.Management.Smo.Server.EnumProcesses%2A> method to discover information about the current processes.</span></span> <span data-ttu-id="4804e-143">Il montre également comment utiliser les colonnes et les lignes incluses dans l'objet <xref:System.Data.DataTable> retourné.</span><span class="sxs-lookup"><span data-stu-id="4804e-143">It also demonstrates how to work with the columns and rows in the returned <xref:System.Data.DataTable> object.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBMethods5](SMO How to#SMO_VBMethods5)]  -->  
  
## <a name="monitoring-server-processes-in-visual-c"></a><span data-ttu-id="4804e-144">Surveillance des processus serveur en Visual C#</span><span class="sxs-lookup"><span data-stu-id="4804e-144">Monitoring Server Processes in Visual C#</span></span>  
 <span data-ttu-id="4804e-145">Vous pouvez obtenir les informations de type d'état actuelles sur l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] par le biais des méthodes d'énumération.</span><span class="sxs-lookup"><span data-stu-id="4804e-145">You can obtain the current status type information about the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] through enumeration methods.</span></span> <span data-ttu-id="4804e-146">L'exemple de code utilise la méthode <xref:Microsoft.SqlServer.Management.Smo.Server.EnumProcesses%2A> pour découvrir des informations sur les processus en cours.</span><span class="sxs-lookup"><span data-stu-id="4804e-146">The code example uses the <xref:Microsoft.SqlServer.Management.Smo.Server.EnumProcesses%2A> method to discover information about the current processes.</span></span> <span data-ttu-id="4804e-147">Il montre également comment utiliser les colonnes et les lignes incluses dans l'objet <xref:System.Data.DataTable> retourné.</span><span class="sxs-lookup"><span data-stu-id="4804e-147">It also demonstrates how to work with the columns and rows in the returned <xref:System.Data.DataTable> object.</span></span>  
  
```  
//Connect to the local, default instance of SQL Server.   
{   
Server srv = default(Server);   
srv = new Server();   
//Call the EnumCollations method and return collation information to DataTable variable.   
DataTable d = default(DataTable);   
//Select the returned data into an array of DataRow.   
d = srv.EnumProcesses;   
//Iterate through the rows and display collation details for the instance of SQL Server.   
DataRow r = default(DataRow);   
DataColumn c = default(DataColumn);   
foreach ( r in d.Rows) {   
  Console.WriteLine("=====");   
  foreach ( c in r.Table.Columns) {   
    Console.WriteLine(c.ColumnName + " = " + r(c).ToString);   
  }   
}   
}   
```  
  
## <a name="see-also"></a><span data-ttu-id="4804e-148">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4804e-148">See Also</span></span>  
 <xref:Microsoft.SqlServer.Management.Smo.Server>   
 <xref:Microsoft.SqlServer.Management.Common.ServerConnection>  
  
  
