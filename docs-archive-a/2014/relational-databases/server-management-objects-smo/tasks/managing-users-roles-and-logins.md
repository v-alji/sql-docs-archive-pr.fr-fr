---
title: Gestion des utilisateurs, des rôles et des connexions | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- logins [SMO]
- roles [SMO]
- users [SMO]
ms.assetid: 74e411fa-74ed-49ec-ab58-68c250f2280e
author: stevestein
ms.author: sstein
ms.openlocfilehash: bb53e7b4a5748e46c7cb147e1cda50652d8b8805
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612204"
---
# <a name="managing-users-roles-and-logins"></a><span data-ttu-id="99b8a-102">Gestion des utilisateurs, rôles et connexions</span><span class="sxs-lookup"><span data-stu-id="99b8a-102">Managing Users, Roles, and Logins</span></span>
  <span data-ttu-id="99b8a-103">Dans SMO, les connexions sont représentées par l'objet <xref:Microsoft.SqlServer.Management.Smo.Login>.</span><span class="sxs-lookup"><span data-stu-id="99b8a-103">In SMO, logins are represented by the <xref:Microsoft.SqlServer.Management.Smo.Login> object.</span></span> <span data-ttu-id="99b8a-104">Lorsque la connexion existe dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], elle peut être ajoutée à un rôle serveur.</span><span class="sxs-lookup"><span data-stu-id="99b8a-104">When the logon exists in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], it can be added to a server role.</span></span> <span data-ttu-id="99b8a-105">Le rôle de serveur est représenté par l'objet <xref:Microsoft.SqlServer.Management.Smo.ServerRole>.</span><span class="sxs-lookup"><span data-stu-id="99b8a-105">The server role is represented by the <xref:Microsoft.SqlServer.Management.Smo.ServerRole> object.</span></span> <span data-ttu-id="99b8a-106">Le rôle de base de données est représenté par l'objet <xref:Microsoft.SqlServer.Management.Smo.DatabaseRole> et le rôle d'application est représenté par l'objet <xref:Microsoft.SqlServer.Management.Smo.ApplicationRole>.</span><span class="sxs-lookup"><span data-stu-id="99b8a-106">The database role is represented by the <xref:Microsoft.SqlServer.Management.Smo.DatabaseRole> object and the application role is represented by the <xref:Microsoft.SqlServer.Management.Smo.ApplicationRole> object.</span></span>  
  
 <span data-ttu-id="99b8a-107">Les privilèges associés au niveau serveur sont répertoriés sous la forme de propriétés de l'objet <xref:Microsoft.SqlServer.Management.Smo.ServerPermission>.</span><span class="sxs-lookup"><span data-stu-id="99b8a-107">Privileges associated with the server level are listed as properties of the <xref:Microsoft.SqlServer.Management.Smo.ServerPermission> object.</span></span> <span data-ttu-id="99b8a-108">Les privilèges au niveau serveur peuvent être accordés, refusés ou révoqués pour les comptes d'ouverture de session individuels.</span><span class="sxs-lookup"><span data-stu-id="99b8a-108">The server level privileges can be granted to, denied to, or revoked from individual logon accounts.</span></span>  
  
 <span data-ttu-id="99b8a-109">Chaque objet <xref:Microsoft.SqlServer.Management.Smo.Database> a un objet <xref:Microsoft.SqlServer.Management.Smo.UserCollection> qui spécifie tous les utilisateurs de la base de données.</span><span class="sxs-lookup"><span data-stu-id="99b8a-109">Every <xref:Microsoft.SqlServer.Management.Smo.Database> object has a <xref:Microsoft.SqlServer.Management.Smo.UserCollection> object that specifies all users in the database.</span></span> <span data-ttu-id="99b8a-110">Chaque utilisateur est associé à une ouverture de session.</span><span class="sxs-lookup"><span data-stu-id="99b8a-110">Each user is associated with a logon.</span></span> <span data-ttu-id="99b8a-111">Une ouverture de session peut être associée à plusieurs utilisateurs d'une base de données.</span><span class="sxs-lookup"><span data-stu-id="99b8a-111">One logon can be associated with users in more than one database.</span></span> <span data-ttu-id="99b8a-112">La méthode <xref:Microsoft.SqlServer.Management.Smo.Login> de l'objet <xref:Microsoft.SqlServer.Management.Smo.Login.EnumDatabaseMappings%2A> peut être utilisée pour répertorier tous les utilisateurs dans chaque base de données associée à l'ouverture de session.</span><span class="sxs-lookup"><span data-stu-id="99b8a-112">The <xref:Microsoft.SqlServer.Management.Smo.Login> object's <xref:Microsoft.SqlServer.Management.Smo.Login.EnumDatabaseMappings%2A> method can be used to list all users in every database that is associated with the logon.</span></span> <span data-ttu-id="99b8a-113">Ou bien, la propriété <xref:Microsoft.SqlServer.Management.Smo.User> de l'objet <xref:Microsoft.SqlServer.Management.Smo.Login> spécifie l'ouverture de session qui est associée à l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="99b8a-113">Alternatively, the <xref:Microsoft.SqlServer.Management.Smo.User> object's <xref:Microsoft.SqlServer.Management.Smo.Login> property specifies the logon that is associated with the user.</span></span>  
  
 <span data-ttu-id="99b8a-114">Les bases de données [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ont également des rôles qui spécifient un jeu de privilèges de niveau base de données qui permettent à un utilisateur d'effectuer des tâches spécifiques.</span><span class="sxs-lookup"><span data-stu-id="99b8a-114">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] databases also have roles that specify a set of database level privileges that let a user perform specific tasks.</span></span> <span data-ttu-id="99b8a-115">Contrairement aux rôles de serveur, les rôles de base de données ne sont pas fixes.</span><span class="sxs-lookup"><span data-stu-id="99b8a-115">Unlike server roles, database roles are not fixed.</span></span> <span data-ttu-id="99b8a-116">Ils peuvent être créés, modifiés et supprimés.</span><span class="sxs-lookup"><span data-stu-id="99b8a-116">They can be created, modified, and removed.</span></span> <span data-ttu-id="99b8a-117">Les privilèges et utilisateurs peuvent être attribués à un rôle de base de données pour une administration en masse.</span><span class="sxs-lookup"><span data-stu-id="99b8a-117">Privileges and users can be assigned to a database role for bulk administration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="99b8a-118">Exemple</span><span class="sxs-lookup"><span data-stu-id="99b8a-118">Example</span></span>  
 <span data-ttu-id="99b8a-119">Dans l'exemple de code suivant, vous devez sélectionner l'environnement, le modèle et le langage de programmation à utiliser pour créer votre application.</span><span class="sxs-lookup"><span data-stu-id="99b8a-119">For the following code example, you will have to select the programming environment, programming template and the programming language to create your application.</span></span> <span data-ttu-id="99b8a-120">Pour plus d’informations, consultez [créer un projet Visual Basic Smo dans Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) et [créer un projet Visual C&#35; Smo dans Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="99b8a-120">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) and [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="enumerating-logins-and-associated-users-in-visual-basic"></a><span data-ttu-id="99b8a-121">Énumération des connexions et des utilisateurs associés en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="99b8a-121">Enumerating Logins and Associated Users in Visual Basic</span></span>  
 <span data-ttu-id="99b8a-122">Chaque utilisateur d'une base de données est associé à une ouverture de session.</span><span class="sxs-lookup"><span data-stu-id="99b8a-122">Every user in a database is associated with a logon.</span></span> <span data-ttu-id="99b8a-123">L'ouverture de session peut être associée à plusieurs utilisateurs dans plusieurs bases de données.</span><span class="sxs-lookup"><span data-stu-id="99b8a-123">The logon can be associated with users in more than one database.</span></span> <span data-ttu-id="99b8a-124">L'exemple de code montre comment appeler la méthode <xref:Microsoft.SqlServer.Management.Smo.Login.EnumDatabaseMappings%2A> de l'objet <xref:Microsoft.SqlServer.Management.Smo.Login> pour répertorier tous les utilisateurs de la base de données qui sont associés à l'ouverture de session.</span><span class="sxs-lookup"><span data-stu-id="99b8a-124">The code example shows how to call the <xref:Microsoft.SqlServer.Management.Smo.Login.EnumDatabaseMappings%2A> method of the <xref:Microsoft.SqlServer.Management.Smo.Login> object to list all the database users who are associated with the logon.</span></span> <span data-ttu-id="99b8a-125">L'exemple crée une ouverture de session et un utilisateur dans la base de données [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] pour garantir la présence d'informations de mappage à énumérer.</span><span class="sxs-lookup"><span data-stu-id="99b8a-125">The example creates a logon and user in the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] database to make sure there is mapping information to enumerate.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBLogins1](SMO How to#SMO_VBLogins1)]  -->  
  
## <a name="enumerating-logins-and-associated-users-in-visual-c"></a><span data-ttu-id="99b8a-126">Énumération des connexions et des utilisateurs associés en Visual C#</span><span class="sxs-lookup"><span data-stu-id="99b8a-126">Enumerating Logins and Associated Users in Visual C#</span></span>  
 <span data-ttu-id="99b8a-127">Chaque utilisateur d'une base de données est associé à une ouverture de session.</span><span class="sxs-lookup"><span data-stu-id="99b8a-127">Every user in a database is associated with a logon.</span></span> <span data-ttu-id="99b8a-128">L'ouverture de session peut être associée à plusieurs utilisateurs dans plusieurs bases de données.</span><span class="sxs-lookup"><span data-stu-id="99b8a-128">The logon can be associated with users in more than one database.</span></span> <span data-ttu-id="99b8a-129">L'exemple de code montre comment appeler la méthode <xref:Microsoft.SqlServer.Management.Smo.Login.EnumDatabaseMappings%2A> de l'objet <xref:Microsoft.SqlServer.Management.Smo.Login> pour répertorier tous les utilisateurs de la base de données qui sont associés à l'ouverture de session.</span><span class="sxs-lookup"><span data-stu-id="99b8a-129">The code example shows how to call the <xref:Microsoft.SqlServer.Management.Smo.Login.EnumDatabaseMappings%2A> method of the <xref:Microsoft.SqlServer.Management.Smo.Login> object to list all the database users who are associated with the logon.</span></span> <span data-ttu-id="99b8a-130">L'exemple crée une ouverture de session et un utilisateur dans la base de données [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] pour garantir la présence d'informations de mappage à énumérer.</span><span class="sxs-lookup"><span data-stu-id="99b8a-130">The example creates a logon and user in the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] database to make sure there is mapping information to enumerate.</span></span>  
  
```csharp
{   
Server srv = new Server();   
//Iterate through each database and display.   
  
foreach ( Database db in srv.Databases) {   
   Console.WriteLine("========");   
   Console.WriteLine("Login Mappings for the database: " + db.Name);   
   Console.WriteLine(" ");   
   //Run the EnumLoginMappings method and return details of database user-login mappings to a DataTable object variable.   
   DataTable d;  
   d = db.EnumLoginMappings();   
   //Display the mapping information.   
   foreach (DataRow r in d.Rows) {   
      foreach (DataColumn c in r.Table.Columns) {   
         Console.WriteLine(c.ColumnName + " = " + r[c]);   
      }   
      Console.WriteLine(" ");   
   }   
}   
}  
```  
  
## <a name="enumerating-logins-and-associated-users-in-powershell"></a><span data-ttu-id="99b8a-131">Énumération des connexions et des utilisateurs associés dans PowerShell</span><span class="sxs-lookup"><span data-stu-id="99b8a-131">Enumerating Logins and Associated Users in PowerShell</span></span>  
 <span data-ttu-id="99b8a-132">Chaque utilisateur d'une base de données est associé à une ouverture de session.</span><span class="sxs-lookup"><span data-stu-id="99b8a-132">Every user in a database is associated with a logon.</span></span> <span data-ttu-id="99b8a-133">L'ouverture de session peut être associée à plusieurs utilisateurs dans plusieurs bases de données.</span><span class="sxs-lookup"><span data-stu-id="99b8a-133">The logon can be associated with users in more than one database.</span></span> <span data-ttu-id="99b8a-134">L'exemple de code montre comment appeler la méthode <xref:Microsoft.SqlServer.Management.Smo.Login.EnumDatabaseMappings%2A> de l'objet <xref:Microsoft.SqlServer.Management.Smo.Login> pour répertorier tous les utilisateurs de la base de données qui sont associés à l'ouverture de session.</span><span class="sxs-lookup"><span data-stu-id="99b8a-134">The code example shows how to call the <xref:Microsoft.SqlServer.Management.Smo.Login.EnumDatabaseMappings%2A> method of the <xref:Microsoft.SqlServer.Management.Smo.Login> object to list all the database users who are associated with the logon.</span></span> <span data-ttu-id="99b8a-135">L'exemple crée une ouverture de session et un utilisateur dans la base de données [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] pour garantir la présence d'informations de mappage à énumérer.</span><span class="sxs-lookup"><span data-stu-id="99b8a-135">The example creates a logon and user in the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] database to make sure there is mapping information to enumerate.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server.  
CD \sql\localhost\Default\Databases  
  
#Iterate through all databases  
 foreach ($db in Get-ChildItem)  
 {  
 "====="  
 "Login Mappings for the database: "+ $db.Name  
  
 #get the datatable containing the mapping from the smo database object  
 $dt = $db.EnumLoginMappings()  
  
 #display the results  
 foreach($row in $dt.Rows)  
     {  
        foreach($col in $row.Table.Columns)  
      {  
        $col.ColumnName + "=" + $row[$col]  
       }
     }  
 }  
```  
  
## <a name="managing-roles-and-users"></a><span data-ttu-id="99b8a-136">Gestion des rôles et des utilisateurs</span><span class="sxs-lookup"><span data-stu-id="99b8a-136">Managing Roles and Users</span></span>  
 <span data-ttu-id="99b8a-137">Cet exemple montre comment gérer les rôles et les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="99b8a-137">This sample demonstrates how to how to manage roles and users.</span></span> <span data-ttu-id="99b8a-138">Le premier exemple utilise C#, et le second Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="99b8a-138">The first sample uses C#, the second Visual Basic.</span></span> <span data-ttu-id="99b8a-139">Ces exemples doivent référencer les assemblys suivants :</span><span class="sxs-lookup"><span data-stu-id="99b8a-139">These samples need to reference the following assemblies:</span></span>  
  
-   <span data-ttu-id="99b8a-140">Microsoft.SqlServer.Smo.dll</span><span class="sxs-lookup"><span data-stu-id="99b8a-140">Microsoft.SqlServer.Smo.dll</span></span>  
  
-   <span data-ttu-id="99b8a-141">Microsoft.SqlServer.Management.Sdk.Sfc.dll</span><span class="sxs-lookup"><span data-stu-id="99b8a-141">Microsoft.SqlServer.Management.Sdk.Sfc.dll</span></span>  
  
-   <span data-ttu-id="99b8a-142">Microsoft.SqlServer.ConnectionInfo.dll</span><span class="sxs-lookup"><span data-stu-id="99b8a-142">Microsoft.SqlServer.ConnectionInfo.dll</span></span>  
  
-   <span data-ttu-id="99b8a-143">Microsoft.SqlServer.SqlEnum.dll</span><span class="sxs-lookup"><span data-stu-id="99b8a-143">Microsoft.SqlServer.SqlEnum.dll</span></span>  
  
```csharp
using Microsoft.SqlServer.Management.Smo;  
using System;  
  
public class A {  
   public static void Main() {  
      Server svr = new Server();  
      Database db = new Database(svr, "TESTDB");  
      db.Create();  
  
      // Creating Logins  
      Login login = new Login(svr, "Login1");  
      login.LoginType = LoginType.SqlLogin;  
      login.Create("password@1");  
  
      Login login2 = new Login(svr, "Login2");  
      login2.LoginType = LoginType.SqlLogin;  
      login2.Create("password@1");  
  
      // Creating Users in the database for the logins created  
      User user1 = new User(db, "User1");  
      user1.Login = "Login1";  
      user1.Create();  
  
      User user2 = new User(db, "User2");  
      user2.Login = "Login2";  
      user2.Create();  
  
      // Creating database permission Sets  
      DatabasePermissionSet dbPermSet = new DatabasePermissionSet(DatabasePermission.AlterAnySchema);  
      dbPermSet.Add(DatabasePermission.AlterAnyUser);  
  
      DatabasePermissionSet dbPermSet2 = new DatabasePermissionSet(DatabasePermission.CreateType);  
      dbPermSet2.Add(DatabasePermission.CreateSchema);  
      dbPermSet2.Add(DatabasePermission.CreateTable);  
  
      // Creating Database roles  
      DatabaseRole role1 = new DatabaseRole(db, "Role1");  
      role1.Create();  
  
      DatabaseRole role2 = new DatabaseRole(db, "Role2");  
      role2.Create();  
  
      // Granting Database Permission Sets to Roles  
      db.Grant(dbPermSet, role1.Name);  
      db.Grant(dbPermSet2, role2.Name);  
  
      // Adding members (Users / Roles) to Role  
      role1.AddMember("User1");  
  
      role2.AddMember("User2");  
  
      // Role1 becomes a member of Role2  
      role2.AddMember("Role1");  
  
      // Enumerating through explicit permissions granted to Role1  
      // enumerates all database permissions for the Grantee  
      DatabasePermissionInfo[] dbPermsRole1 = db.EnumDatabasePermissions("Role1");     
      foreach (DatabasePermissionInfo dbp in dbPermsRole1) {  
         Console.WriteLine(dbp.Grantee + " has " + dbp.PermissionType.ToString() + " permission.");  
      }  
      Console.WriteLine(" ");  
   }  
}  
```  
  
 <span data-ttu-id="99b8a-144">Version Visual Basic :</span><span class="sxs-lookup"><span data-stu-id="99b8a-144">This is the Visual Basic version:</span></span>  
  
```vb
Imports Microsoft.SqlServer.Management.Smo  
  
Public Class A  
   Public Shared Sub Main()  
      Dim svr As New Server()  
      Dim db As New Database(svr, "TESTDB")  
      db.Create()  
  
      ' Creating Logins  
      Dim login As New Login(svr, "Login1")  
      login.LoginType = LoginType.SqlLogin  
      login.Create("password@1")  
  
      Dim login2 As New Login(svr, "Login2")  
      login2.LoginType = LoginType.SqlLogin  
      login2.Create("password@1")  
  
      ' Creating Users in the database for the logins created  
      Dim user1 As New User(db, "User1")  
      user1.Login = "Login1"  
      user1.Create()  
  
      Dim user2 As New User(db, "User2")  
      user2.Login = "Login2"  
      user2.Create()  
  
      ' Creating database permission Sets  
      Dim dbPermSet As New DatabasePermissionSet(DatabasePermission.AlterAnySchema)  
      dbPermSet.Add(DatabasePermission.AlterAnyUser)  
  
      Dim dbPermSet2 As New DatabasePermissionSet(DatabasePermission.CreateType)  
      dbPermSet2.Add(DatabasePermission.CreateSchema)  
      dbPermSet2.Add(DatabasePermission.CreateTable)  
  
      ' Creating Database roles  
      Dim role1 As New DatabaseRole(db, "Role1")  
      role1.Create()  
  
      Dim role2 As New DatabaseRole(db, "Role2")  
      role2.Create()  
  
      ' Granting Database Permission Sets to Roles  
      db.Grant(dbPermSet, role1.Name)  
      db.Grant(dbPermSet2, role2.Name)  
  
      ' Adding members (Users / Roles) to Role  
      role1.AddMember("User1")  
  
      role2.AddMember("User2")  
  
      ' Role1 becomes a member of Role2  
      role2.AddMember("Role1")  
  
      ' Enumerating through explicit permissions granted to Role1  
      ' enumerates all database permissions for the Grantee  
      Dim dbPermsRole1 As DatabasePermissionInfo() = db.EnumDatabasePermissions("Role1")  
      For Each dbp As DatabasePermissionInfo In dbPermsRole1  
         Console.WriteLine(dbp.Grantee + " has " & dbp.PermissionType.ToString() & " permission.")  
      Next  
      Console.WriteLine(" ")  
   End Sub  
End Class  
```  
