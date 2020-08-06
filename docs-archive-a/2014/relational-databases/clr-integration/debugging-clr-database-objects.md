---
title: Débogage d’objets de base de données CLR | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- database objects [CLR integration], debugging
- permissions [CLR integration]
- debugging [CLR integration]
- building database objects [CLR integration], debugging
- common language runtime [SQL Server], debugging
ms.assetid: 1332035c-d6ed-424d-8234-46ad21168319
author: rothja
ms.author: jroth
ms.openlocfilehash: 084b2494ec55b502f71154ca1f174a6de6d2ab70
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600077"
---
# <a name="debugging-clr-database-objects"></a><span data-ttu-id="9a210-102">Débogage d'objets de base de données CLR</span><span class="sxs-lookup"><span data-stu-id="9a210-102">Debugging CLR Database Objects</span></span>
  [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="9a210-103">prend en charge le débogage d'objets [!INCLUDE[tsql](../../../includes/tsql-md.md)] et CLR dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="9a210-103">provides support for debugging [!INCLUDE[tsql](../../../includes/tsql-md.md)] and common language runtime (CLR) objects in the database.</span></span> <span data-ttu-id="9a210-104">Les principaux atouts du débogage dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] sont la facilité d'installation et d'utilisation, et l'intégration du débogueur SQL Server avec le débogueur Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9a210-104">The key aspects of debugging in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] are the ease of setup and use, and the integration of the SQL Server debugger with the Microsoft Visual Studio debugger.</span></span> <span data-ttu-id="9a210-105">En outre, le débogage fonctionne sur plusieurs langages.</span><span class="sxs-lookup"><span data-stu-id="9a210-105">Furthermore, debugging works across languages.</span></span> <span data-ttu-id="9a210-106">Les utilisateurs peuvent effectuer de façon transparente un pas à pas détaillé dans les objets CLR à partir de [!INCLUDE[tsql](../../../includes/tsql-md.md)] et vice versa.</span><span class="sxs-lookup"><span data-stu-id="9a210-106">Users can step seamlessly into CLR objects from [!INCLUDE[tsql](../../../includes/tsql-md.md)], and vice versa.</span></span> <span data-ttu-id="9a210-107">Le débogueur Transact-SQL dans SQL Server Management Studio ne peut pas être utilisé pour déboguer des objets de base de données managés, mais vous pouvez déboguer les objets en utilisant les débogueurs de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9a210-107">The Transact-SQL debugger in SQL Server Management Studio cannot be used to debug managed database objects, but you can debug the objects by using the debuggers in Visual Studio.</span></span> <span data-ttu-id="9a210-108">Le débogage d'objets de base de données managés dans Visual Studio prend en charge toutes les fonctionnalités de débogage classiques, par exemple, les instructions "step into" et "step over" dans les routines qui s'exécutent sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="9a210-108">Managed database object debugging in Visual Studio supports all common debugging features, such as "step into" and "step over" statements within routines executing on the server.</span></span> <span data-ttu-id="9a210-109">Les débogueurs peuvent définir des points d'arrêt, inspecter la pile des appels, inspecter les variables et modifier des valeurs de variables en cours de débogage.</span><span class="sxs-lookup"><span data-stu-id="9a210-109">Debuggers can set breakpoints, inspect the call stack, inspect variables, and modify variable values while debugging.</span></span> <span data-ttu-id="9a210-110">Notez que Visual Studio .NET 2003 ne peut pas être utilisé pour le débogage ou la programmation de l'intégration du CLR.</span><span class="sxs-lookup"><span data-stu-id="9a210-110">Note that Visual Studio .NET 2003 cannot be used for CLR integration programming or debugging.</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="9a210-111">inclut le .NET Framework préinstallé et Visual Studio .NET 2003 ne peut pas utiliser les assemblys .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="9a210-111">includes the .NET Framework pre-installed, and Visual Studio .NET 2003 cannot use the .NET Framework 2.0 assemblies.</span></span>  
  
 <span data-ttu-id="9a210-112">Pour plus d’informations sur le débogage de code managé à l’aide de Visual Studio, consultez la rubrique «[débogage du code managé](https://go.microsoft.com/fwlink/?LinkId=120377)» dans la documentation de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9a210-112">For more information about debugging managed code using Visual Studio, see the "[Debugging Managed Code](https://go.microsoft.com/fwlink/?LinkId=120377)" topic in the Visual Studio documentation.</span></span>  
  
## <a name="debugging-permissions-and-restrictions"></a><span data-ttu-id="9a210-113">Autorisations et restrictions de débogage</span><span class="sxs-lookup"><span data-stu-id="9a210-113">Debugging Permissions and Restrictions</span></span>  
 <span data-ttu-id="9a210-114">Le débogage est une opération hautement privilégiée, et par conséquent, seuls les membres du rôle serveur fixe **sysadmin** sont autorisés à le faire dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9a210-114">Debugging is a highly privileged operation, and therefore only members of the **sysadmin** fixed server role are allowed to do so in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="9a210-115">Les restrictions suivantes s'appliquent dans le cadre du débogage :</span><span class="sxs-lookup"><span data-stu-id="9a210-115">The following restrictions apply while debugging:</span></span>  
  
-   <span data-ttu-id="9a210-116">Le débogage des routines CLR est restreint à une instance de débogueur à la fois.</span><span class="sxs-lookup"><span data-stu-id="9a210-116">Debugging CLR routines is restricted to one debugger instance at a time.</span></span> <span data-ttu-id="9a210-117">Cette limitation s'applique parce que l'exécution de la totalité du code CLR est gelée lorsqu'un point d'arrêt est atteint et qu'elle ne reprend que lorsque le débogueur continue à partir du point d'arrêt.</span><span class="sxs-lookup"><span data-stu-id="9a210-117">This limitation applies because all CLR code execution freezes when a break point is hit and execution does not continue until the debugger advances from the break point.</span></span> <span data-ttu-id="9a210-118">Toutefois, vous pouvez continuer à déboguer [!INCLUDE[tsql](../../../includes/tsql-md.md)] dans d'autres connexions.</span><span class="sxs-lookup"><span data-stu-id="9a210-118">However, you can continue debugging [!INCLUDE[tsql](../../../includes/tsql-md.md)] in other connections.</span></span> <span data-ttu-id="9a210-119">Bien que le débogage [!INCLUDE[tsql](../../../includes/tsql-md.md)] ne gèle pas d'autres exécutions sur le serveur, il peut provoquer la mise en attente d'autres connexions par le maintien d'un verrou.</span><span class="sxs-lookup"><span data-stu-id="9a210-119">Although [!INCLUDE[tsql](../../../includes/tsql-md.md)] debugging does not freeze other executions on the server, it could cause other connections to wait by holding a lock.</span></span>  
  
-   <span data-ttu-id="9a210-120">Les connexions existantes ne peuvent pas être déboguées ; seules les nouvelles connexions peuvent l'être, puisque [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] requiert des informations sur l'environnement du client et du débogueur pour que la connexion puisse être établie.</span><span class="sxs-lookup"><span data-stu-id="9a210-120">Existing connections cannot be debugged, only new connections, as [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] requires information about the client and debugger environment before the connection can be made.</span></span>  
  
 <span data-ttu-id="9a210-121">En raison des restrictions précitées, nous recommandons que le débogage du code [!INCLUDE[tsql](../../../includes/tsql-md.md)] et CLR soit effectué sur un serveur de test et non sur un serveur de production.</span><span class="sxs-lookup"><span data-stu-id="9a210-121">Due to the above restrictions, we recommend that [!INCLUDE[tsql](../../../includes/tsql-md.md)] and CLR code be debugged on a test server, and not on a production server.</span></span>  
  
## <a name="overview-of-debugging-managed-database-objects"></a><span data-ttu-id="9a210-122">Vue d'ensemble du débogage des objets de base de données managés</span><span class="sxs-lookup"><span data-stu-id="9a210-122">Overview of Debugging Managed Database Objects</span></span>  
 <span data-ttu-id="9a210-123">Le débogage dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] suit un modèle « par connexion ».</span><span class="sxs-lookup"><span data-stu-id="9a210-123">Debugging in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] follows a per-connection model.</span></span> <span data-ttu-id="9a210-124">Un débogueur peut détecter et déboguer des activités uniquement sur la connexion cliente à laquelle il est attaché.</span><span class="sxs-lookup"><span data-stu-id="9a210-124">A debugger can detect and debug activities only to the client connection to which it is attached.</span></span> <span data-ttu-id="9a210-125">Comme les fonctionnalités du débogueur ne sont pas limitées par le type de connexion, il est possible de déboguer à la fois des TDS (Tabular Data Stream) et des connexions HTTP.</span><span class="sxs-lookup"><span data-stu-id="9a210-125">Because the functionality of the debugger is not limited by the type of connection, both tabular data stream (TDS) and HTTP connections can be debugged.</span></span> <span data-ttu-id="9a210-126">Toutefois, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] n'autorise pas le débogage des connexions existantes.</span><span class="sxs-lookup"><span data-stu-id="9a210-126">However, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] does not allow debugging existing connections.</span></span> <span data-ttu-id="9a210-127">Le débogage prend en charge toutes les fonctionnalités de débogage communes dans les routines qui s'exécutent sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="9a210-127">Debugging supports all common debugging features within routines executing on the server.</span></span> <span data-ttu-id="9a210-128">L'interaction entre un débogueur et [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] s'effectue par le biais d'un modèle COM (Component Object Model) distribué.</span><span class="sxs-lookup"><span data-stu-id="9a210-128">The interaction between a debugger and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] happens through distributed Component Object Model (COM).</span></span>  
  
 <span data-ttu-id="9a210-129">Pour plus d’informations et des scénarios sur le débogage des procédures stockées managées, des fonctions, des déclencheurs, des types définis par l’utilisateur et des agrégats, consultez la rubrique «[SQL Server le débogage de base de données d’intégration CLR](https://go.microsoft.com/fwlink/?LinkId=120378)» dans la documentation de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9a210-129">For more information and scenarios about debugging managed stored procedures, functions, triggers, user-defined types, and aggregates, see the "[SQL Server CLR Integration Database Debugging](https://go.microsoft.com/fwlink/?LinkId=120378)" topic in the Visual Studio documentation.</span></span>  
  
 <span data-ttu-id="9a210-130">Le protocole réseau TCP/IP doit être activé sur l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] afin d'utiliser Visual Studio pour le développement et le débogage distants.</span><span class="sxs-lookup"><span data-stu-id="9a210-130">The TCP/IP network protocol must be enabled on the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance in order to use Visual Studio for remote development, debugging, and development.</span></span> <span data-ttu-id="9a210-131">Pour plus d’informations sur l’activation du protocole TCP/IP sur le serveur, consultez [configurer des protocoles clients](../../database-engine/configure-windows/configure-client-protocols.md).</span><span class="sxs-lookup"><span data-stu-id="9a210-131">For more information about enabling TCP/IP protocol on the server, see [Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md).</span></span>  
  
#### <a name="to-debug-a-managed-database-object"></a><span data-ttu-id="9a210-132">Pour déboguer un objet de base de données managé</span><span class="sxs-lookup"><span data-stu-id="9a210-132">To debug a managed database object</span></span>  
  
1.  <span data-ttu-id="9a210-133">Ouvrez Microsoft Visual Studio, créez un projet [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] et établissez une connexion à une base de données sur une instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9a210-133">Open Microsoft Visual Studio, create a new [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] project, and establish a connection to a database on an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="9a210-134">Créez un type.</span><span class="sxs-lookup"><span data-stu-id="9a210-134">Create a new type.</span></span> <span data-ttu-id="9a210-135">Dans **Explorateur de solutions**, cliquez avec le bouton droit sur le projet, puis sélectionnez **Ajouter** et **nouvel élément...** Dans la **fenêtre Ajouter un nouvel élément** , sélectionnez **procédure stockée**, **fonction définie par l’utilisateur**, **type défini par l’utilisateur**, **déclencheur**, **agrégat**ou **classe**.</span><span class="sxs-lookup"><span data-stu-id="9a210-135">In **Solution Explorer**, right-click the project, select **Add** and **New Item...** From the **Add New Item** window, select **Stored Procedure**, **User-Defined Function**, **User-Defined Type**, **Trigger**, **Aggregate**, or **Class**.</span></span> <span data-ttu-id="9a210-136">Spécifiez un nom pour le fichier source du nouveau type, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="9a210-136">Specify a name for the source file of the new type and click **Add**.</span></span>  
  
3.  <span data-ttu-id="9a210-137">Ajoutez le code du nouveau type à l'éditeur de texte.</span><span class="sxs-lookup"><span data-stu-id="9a210-137">Add code for the new type to the text editor.</span></span> <span data-ttu-id="9a210-138">Pour obtenir le code d'un exemple de procédure stockée, consultez la section correspondante plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="9a210-138">For sample code for an example stored procedure, see the section later in this topic.</span></span>  
  
4.  <span data-ttu-id="9a210-139">Ajoutez un script qui teste le type.</span><span class="sxs-lookup"><span data-stu-id="9a210-139">Add a script that tests the type.</span></span> <span data-ttu-id="9a210-140">Dans **Explorateur de solutions**, développez le répertoire **TestScripts** double-cliquez sur **test. SQL** pour ouvrir le fichier source du script de test par défaut.</span><span class="sxs-lookup"><span data-stu-id="9a210-140">In **Solution Explorer**, expand the **TestScripts** directory double-click **Test.sql** to open the default test script source file.</span></span> <span data-ttu-id="9a210-141">Ajoutez à l'éditeur de texte un script de test qui appelle le code à déboguer.</span><span class="sxs-lookup"><span data-stu-id="9a210-141">Add the test script, one that invokes the code to be debugged, to the text editor.</span></span> <span data-ttu-id="9a210-142">Un exemple de script est proposé ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="9a210-142">See below for a sample script.</span></span>  
  
5.  <span data-ttu-id="9a210-143">Placez un ou plusieurs points d'arrêt dans le code source.</span><span class="sxs-lookup"><span data-stu-id="9a210-143">Place one or more breakpoints in the source code.</span></span> <span data-ttu-id="9a210-144">Cliquez avec le bouton droit sur une ligne de code dans l’éditeur de texte, dans la fonction ou la routine que vous souhaitez déboguer, puis sélectionnez **point d’arrêt** et insérer un **point d’arrêt**.</span><span class="sxs-lookup"><span data-stu-id="9a210-144">Right-click on a line of code in the text editor, within the function or routine you want to debug, and select **Breakpoint** and **Insert Breakpoint**.</span></span> <span data-ttu-id="9a210-145">Le point d'arrêt est ajouté et la ligne de code est affichée en rouge.</span><span class="sxs-lookup"><span data-stu-id="9a210-145">The breakpoint is added, highlighting the line of code in red.</span></span>  
  
6.  <span data-ttu-id="9a210-146">Dans le menu **Déboguer** , sélectionnez **Démarrer le débogage** pour compiler, déployer et tester le projet.</span><span class="sxs-lookup"><span data-stu-id="9a210-146">In the **Debug** menu, select **Start Debugging** to compile, deploy, and test the project.</span></span> <span data-ttu-id="9a210-147">Le script de test dans Test.sql est exécuté et l'objet de base de données managé est appelé.</span><span class="sxs-lookup"><span data-stu-id="9a210-147">The test script in Test.sql will be run and the managed database object will be invoked.</span></span>  
  
7.  <span data-ttu-id="9a210-148">Lorsque la flèche jaune qui désigne le pointeur d'instruction apparaît au niveau du point d'arrêt, l'exécution du code est  suspendue et vous pouvez commencer à déboguer votre objet de base de données managé.</span><span class="sxs-lookup"><span data-stu-id="9a210-148">When the yellow arrow designating the instruction pointer appears at the breakpoint code execution pauses and you can begin debugging your managed database object.</span></span> <span data-ttu-id="9a210-149">Vous pouvez effectuer un **pas à pas principal** dans le menu **Déboguer** pour faire passer le pointeur d’instruction à la ligne de code suivante.</span><span class="sxs-lookup"><span data-stu-id="9a210-149">You can **Step Over** from the **Debug** menu to advance the instruction pointer to the next line of code.</span></span> <span data-ttu-id="9a210-150">La fenêtre **variables locales** est utilisée pour observer l’état des objets actuellement mis en surbrillance par le pointeur d’instruction.</span><span class="sxs-lookup"><span data-stu-id="9a210-150">The **Locals** window is used to observe the state of the objects currently highlighted by the instruction pointer.</span></span> <span data-ttu-id="9a210-151">Les variables peuvent être ajoutées à la fenêtre **Espion** .</span><span class="sxs-lookup"><span data-stu-id="9a210-151">Variables can be added to the **Watch** window.</span></span> <span data-ttu-id="9a210-152">L'état des variables espionnées peut être consulté tout au long de la session de débogage, et non uniquement lorsque la variable figure dans la ligne de code mise en surbrillance par le pointeur d'instruction.</span><span class="sxs-lookup"><span data-stu-id="9a210-152">The state of watched variables can be observed throughout the entire debugging session, not only when the variable is in the line of code currently highlighted by instruction pointer.</span></span> <span data-ttu-id="9a210-153">Sélectionnez Continuer dans le menu Déboguer pour faire avancer le pointeur d'instruction jusqu'au point d'arrêt suivant ou pour terminer l'exécution de la routine s'il n'y a plus de points d'arrêt.</span><span class="sxs-lookup"><span data-stu-id="9a210-153">Select Continue from the Debug menu to advance the instruction pointer to the next breakpoint or to complete execution of the routine if there are no more breakpoints.</span></span>  
  
### <a name="example"></a><span data-ttu-id="9a210-154">Exemple</span><span class="sxs-lookup"><span data-stu-id="9a210-154">Example</span></span>  
 <span data-ttu-id="9a210-155">L'exemple suivant retourne la version de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] à l'appelant.</span><span class="sxs-lookup"><span data-stu-id="9a210-155">The following example returns the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] version to the caller.</span></span>  
  
 <span data-ttu-id="9a210-156">C#</span><span class="sxs-lookup"><span data-stu-id="9a210-156">C#</span></span>  
  
```  
using System;  
using System.Data;  
using System.Data.SqlTypes;  
using System.Data.SqlClient;  
using Microsoft.SqlServer.Server;   
  
public class StoredProcedures   
{  
   [Microsoft.SqlServer.Server.SqlProcedure]  
   public static void GetVersion()  
   {  
   using(SqlConnection connection = new SqlConnection("context connection=true"))   
   {  
      connection.Open();  
      SqlCommand command = new SqlCommand("select @@version",  
                                           connection);  
      SqlContext.Pipe.ExecuteAndSend(command);  
      }  
   }  
}  
```  
  
 <span data-ttu-id="9a210-157">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9a210-157">Visual Basic</span></span>  
  
```  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlClient  
  
Partial Public Class StoredProcedures   
    <Microsoft.SqlServer.Server.SqlProcedure> _  
    Public Shared Sub GetVersion()  
        Using connection As New SqlConnection("context connection=true")  
            connection.Open()  
            Dim command As New SqlCommand("SELECT @@VERSION", connection)  
            SqlContext.Pipe.ExecuteAndSend(command)  
        End Using  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="9a210-158">Le code suivant est un script de test qui appelle la procédure stockée GetVersion définie précédemment.</span><span class="sxs-lookup"><span data-stu-id="9a210-158">The following is a test script that invokes the GetVersion stored procedure defined above.</span></span>  
  
```  
EXEC GetVersion  
```  
  
## <a name="see-also"></a><span data-ttu-id="9a210-159">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9a210-159">See Also</span></span>  
 [<span data-ttu-id="9a210-160">Concepts de programmation pour l’intégration du CLR &#40;Common Language Runtime&#41;</span><span class="sxs-lookup"><span data-stu-id="9a210-160">Common Language Runtime &#40;CLR&#41; Integration Programming Concepts</span></span>](common-language-runtime-clr-integration-programming-concepts.md)  
  
  
