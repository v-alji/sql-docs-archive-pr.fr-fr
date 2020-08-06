---
title: Ajout de connexions par programmation | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- connection managers [Integration Services], packages
- Integration Services packages, connections
- connections [Integration Services], packages
- SSIS packages, connections
- packages [Integration Services], connections
- intrinsic properties [Integration Services]
- SQL Server Integration Services packages, connections
- ConnectionManager class
- SSIS connection managers
- adding package connections
ms.assetid: d90716d1-4c65-466c-b82c-4aabbee1e3e5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a5952221dbf2689d2328695baf965ce884dc07fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604102"
---
# <a name="adding-connections-programmatically"></a><span data-ttu-id="66592-102">Ajout de connexions par programme</span><span class="sxs-lookup"><span data-stu-id="66592-102">Adding Connections Programmatically</span></span>
  <span data-ttu-id="66592-103">La classe <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> représente des connexions physiques aux sources de données externes.</span><span class="sxs-lookup"><span data-stu-id="66592-103">The <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> class represents physical connections to external data sources.</span></span> <span data-ttu-id="66592-104">La classe <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> isole du runtime les détails d'implémentation de la connexion.</span><span class="sxs-lookup"><span data-stu-id="66592-104">The <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> class isolates the implementation details of the connection from the runtime.</span></span> <span data-ttu-id="66592-105">Elle permet au runtime d'interagir avec chaque gestionnaire de connexions de façon cohérente et prévisible.</span><span class="sxs-lookup"><span data-stu-id="66592-105">This enables the runtime to interact with each connection manager in a consistent and predictable manner.</span></span> <span data-ttu-id="66592-106">Les gestionnaires de connexions contiennent un jeu de propriétés stock que toutes les connexions ont en commun, telles que les propriétés <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Name%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.ID%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Description%2A> et <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.ConnectionString%2A>.</span><span class="sxs-lookup"><span data-stu-id="66592-106">Connection managers contain a set of stock properties that all connections have in common, such as the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Name%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.ID%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Description%2A>, and <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.ConnectionString%2A>.</span></span> <span data-ttu-id="66592-107">Toutefois, les propriétés <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.ConnectionString%2A> et <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Name%2A> sont habituellement les seules propriétés requises pour configurer un gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="66592-107">However, the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.ConnectionString%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Name%2A> properties are ordinarily the only properties required to configure a connection manager.</span></span> <span data-ttu-id="66592-108">Contrairement à d'autres paradigmes de programmation, où les classes de connexion exposent des méthodes telles que `Open` ou `Connect` pour établir physiquement une connexion à la source de données, le moteur d'exécution gère toutes les connexions du package pendant qu'il s'exécute.</span><span class="sxs-lookup"><span data-stu-id="66592-108">Unlike other programming paradigms, where connection classes expose methods such as `Open` or `Connect` to physically establish a connection to the data source, the run-time engine manages all the connections for the package while it runs.</span></span>  
  
 <span data-ttu-id="66592-109">La classe <xref:Microsoft.SqlServer.Dts.Runtime.Connections> est une collection des gestionnaires de connexions qui ont été ajoutés à ce package et qui sont disponibles au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="66592-109">The <xref:Microsoft.SqlServer.Dts.Runtime.Connections> class is a collection of the connection managers that have been added to that package and are available for use at run time.</span></span> <span data-ttu-id="66592-110">Vous pouvez ajouter d'autres gestionnaires de connexions à la collection en utilisant la méthode <xref:Microsoft.SqlServer.Dts.Runtime.Connections.Add%2A> de la collection, et en fournissant une chaîne qui indique le type de gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="66592-110">You can add more connection managers to the collection by using the <xref:Microsoft.SqlServer.Dts.Runtime.Connections.Add%2A> method of the collection, and supplying a string that indicates the connection manager type.</span></span> <span data-ttu-id="66592-111">La méthode <xref:Microsoft.SqlServer.Dts.Runtime.Connections.Add%2A> renvoie l'instance <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> ajoutée au package.</span><span class="sxs-lookup"><span data-stu-id="66592-111">The <xref:Microsoft.SqlServer.Dts.Runtime.Connections.Add%2A> method returns the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> instance that was added to the package.</span></span>  
  
## <a name="intrinsic-properties"></a><span data-ttu-id="66592-112">Propriétés intrinsèques</span><span class="sxs-lookup"><span data-stu-id="66592-112">Intrinsic Properties</span></span>  
 <span data-ttu-id="66592-113">La classe <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> expose un jeu de propriétés communes à toutes les connexions.</span><span class="sxs-lookup"><span data-stu-id="66592-113">The <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> class exposes a set of properties that are common to all connections.</span></span> <span data-ttu-id="66592-114">Toutefois, vous avez parfois besoin d'accéder aux propriétés qui sont uniques au type de connexion spécifique.</span><span class="sxs-lookup"><span data-stu-id="66592-114">However, sometimes you need access to properties that are unique to the specific connection type.</span></span> <span data-ttu-id="66592-115">La collection <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Properties%2A> de la classe <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> fournit l'accès à ces propriétés.</span><span class="sxs-lookup"><span data-stu-id="66592-115">The <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Properties%2A> collection of the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> class provides access to these properties.</span></span> <span data-ttu-id="66592-116">Les propriétés peuvent être extraites de la collection à l’aide de l’indexeur ou du nom de propriété et de la méthode **GetValue**, et les valeurs sont définies à l’aide de la méthode **SetValue**.</span><span class="sxs-lookup"><span data-stu-id="66592-116">The properties can be retrieved from the collection using the indexer or the property name and the **GetValue** method, and the values are set using the **SetValue** method.</span></span> <span data-ttu-id="66592-117">Les propriétés des propriétés de l'objet de connexion sous-jacente peuvent également être définies via l'acquisition d'une instance réelle de l'objet et la définition directe de ses propriétés.</span><span class="sxs-lookup"><span data-stu-id="66592-117">The properties of the underlying connection object properties can also be set by acquiring an actual instance of the object and setting its properties directly.</span></span> <span data-ttu-id="66592-118">Pour obtenir la connexion sous-jacente, utilisez la propriété <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.InnerObject%2A> du gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="66592-118">To get the underlying connection, use the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.InnerObject%2A> property of the connection manager.</span></span> <span data-ttu-id="66592-119">La ligne de code suivante présente une ligne C# qui crée un gestionnaire de connexions ADO.NET qui possède la classe sous-jacente <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.ConnectionManagerAdoNetClass>.</span><span class="sxs-lookup"><span data-stu-id="66592-119">The following line of code shows a C# line that creates an ADO.NET connection manager that has the underlying class, <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.ConnectionManagerAdoNetClass>.</span></span>  
  
 `ConnectionManagerAdoNetClass cmado = cm.InnerObject as ConnectionManagerAdoNet;`  
  
 <span data-ttu-id="66592-120">Elle convertit l'objet du gestionnaire de connexions managées en son objet de connexion sous-jacente.</span><span class="sxs-lookup"><span data-stu-id="66592-120">This casts the managed connection manager object to its underlying connection object.</span></span> <span data-ttu-id="66592-121">Si vous utilisez C++, la méthode `QueryInterface` de l'objet <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> est appelée et l'interface de l'objet de connexion sous-jacente est demandée.</span><span class="sxs-lookup"><span data-stu-id="66592-121">If you are using C++, the `QueryInterface` method of the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> object is called and the interface of the underlying connection object is requested.</span></span>  
  
 <span data-ttu-id="66592-122">Le tableau suivant répertorie les gestionnaires de connexions fournis avec [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="66592-122">The following table lists the connection managers included with [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="66592-123">et la chaîne utilisée dans l'instruction `package.Connections.Add("xxx")`.</span><span class="sxs-lookup"><span data-stu-id="66592-123">and the string that is used in the `package.Connections.Add("xxx")` statement.</span></span> <span data-ttu-id="66592-124">Pour obtenir la liste de tous les gestionnaires de connexions, consultez [Connexions Integration Services &#40;SSIS&#41;](../connection-manager/integration-services-ssis-connections.md).</span><span class="sxs-lookup"><span data-stu-id="66592-124">For a list of all connection managers, see [Integration Services &#40;SSIS&#41; Connections](../connection-manager/integration-services-ssis-connections.md).</span></span>  
  
|<span data-ttu-id="66592-125">String</span><span class="sxs-lookup"><span data-stu-id="66592-125">String</span></span>|<span data-ttu-id="66592-126">Gestionnaire de connexions</span><span class="sxs-lookup"><span data-stu-id="66592-126">Connection manager</span></span>|  
|------------|------------------------|  
|<span data-ttu-id="66592-127">"OLEDB"</span><span class="sxs-lookup"><span data-stu-id="66592-127">"OLEDB"</span></span>|<span data-ttu-id="66592-128">Gestionnaire de connexions pour les connexions OLE DB.</span><span class="sxs-lookup"><span data-stu-id="66592-128">Connection manager for OLE DB connections.</span></span>|  
|<span data-ttu-id="66592-129">"ODBC"</span><span class="sxs-lookup"><span data-stu-id="66592-129">"ODBC"</span></span>|<span data-ttu-id="66592-130">Gestionnaire de connexions pour les connexions ODBC.</span><span class="sxs-lookup"><span data-stu-id="66592-130">Connection manager for ODBC connections.</span></span>|  
|<span data-ttu-id="66592-131">"ADO"</span><span class="sxs-lookup"><span data-stu-id="66592-131">"ADO"</span></span>|<span data-ttu-id="66592-132">Gestionnaire de connexions pour les connexions ADO.</span><span class="sxs-lookup"><span data-stu-id="66592-132">Connection manager for ADO connections.</span></span>|  
|<span data-ttu-id="66592-133">"ADO.NET:SQL"</span><span class="sxs-lookup"><span data-stu-id="66592-133">"ADO.NET:SQL"</span></span>|<span data-ttu-id="66592-134">Gestionnaire de connexions pour les connexions ADO.NET (fournisseur de données SQL).</span><span class="sxs-lookup"><span data-stu-id="66592-134">Connection manager for ADO.NET (SQL data provider) connections.</span></span>|  
|<span data-ttu-id="66592-135">"ADO.NET:OLEDB"</span><span class="sxs-lookup"><span data-stu-id="66592-135">"ADO.NET:OLEDB"</span></span>|<span data-ttu-id="66592-136">Gestionnaire de connexions pour les connexions ADO.NET (fournisseur de données OLE DB).</span><span class="sxs-lookup"><span data-stu-id="66592-136">Connection manager for ADO.NET (OLE DB data provider) connections.</span></span>|  
|<span data-ttu-id="66592-137">"FLATFILE"</span><span class="sxs-lookup"><span data-stu-id="66592-137">"FLATFILE"</span></span>|<span data-ttu-id="66592-138">Gestionnaire de connexions pour les connexions de fichiers plats.</span><span class="sxs-lookup"><span data-stu-id="66592-138">Connection manager for flat file connections.</span></span>|  
|<span data-ttu-id="66592-139">"FILE"</span><span class="sxs-lookup"><span data-stu-id="66592-139">"FILE"</span></span>|<span data-ttu-id="66592-140">Gestionnaire de connexions pour les connexions de fichiers.</span><span class="sxs-lookup"><span data-stu-id="66592-140">Connection manager for file connections.</span></span>|  
|<span data-ttu-id="66592-141">"MULTIFLATFILE"</span><span class="sxs-lookup"><span data-stu-id="66592-141">"MULTIFLATFILE"</span></span>|<span data-ttu-id="66592-142">Gestionnaire de connexions pour les connexions de fichiers plats multiples.</span><span class="sxs-lookup"><span data-stu-id="66592-142">Connection manager for multiple flat file connections.</span></span>|  
|<span data-ttu-id="66592-143">"MULTIFILE"</span><span class="sxs-lookup"><span data-stu-id="66592-143">"MULTIFILE"</span></span>|<span data-ttu-id="66592-144">Gestionnaire de connexions pour les connexions de fichiers multiples.</span><span class="sxs-lookup"><span data-stu-id="66592-144">Connection manager for multiple file connections.</span></span>|  
|<span data-ttu-id="66592-145">"SQLMOBILE"</span><span class="sxs-lookup"><span data-stu-id="66592-145">"SQLMOBILE"</span></span>|<span data-ttu-id="66592-146">Gestionnaire de connexions pour les connexions [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="66592-146">Connection manager for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact connections.</span></span>|  
|<span data-ttu-id="66592-147">"MSOLAP100"</span><span class="sxs-lookup"><span data-stu-id="66592-147">"MSOLAP100"</span></span>|<span data-ttu-id="66592-148">Gestionnaire de connexions pour les connexions [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="66592-148">Connection manager for [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] connections.</span></span>|  
|<span data-ttu-id="66592-149">"FTP"</span><span class="sxs-lookup"><span data-stu-id="66592-149">"FTP"</span></span>|<span data-ttu-id="66592-150">Gestionnaire de connexions pour les connexions FTP.</span><span class="sxs-lookup"><span data-stu-id="66592-150">Connection manager for FTP connections.</span></span>|  
|<span data-ttu-id="66592-151">"HTTP"</span><span class="sxs-lookup"><span data-stu-id="66592-151">"HTTP"</span></span>|<span data-ttu-id="66592-152">Gestionnaire de connexions pour les connexions HTTP.</span><span class="sxs-lookup"><span data-stu-id="66592-152">Connection manager for HTTP connections.</span></span>|  
|<span data-ttu-id="66592-153">"MSMQ"</span><span class="sxs-lookup"><span data-stu-id="66592-153">"MSMQ"</span></span>|<span data-ttu-id="66592-154">Gestionnaire de connexions pour les connexions Message Queuing (également appelées MSMQ).</span><span class="sxs-lookup"><span data-stu-id="66592-154">Connection manager for Message Queuing (also known as MSMQ) connections.</span></span>|  
|<span data-ttu-id="66592-155">"SMTP"</span><span class="sxs-lookup"><span data-stu-id="66592-155">"SMTP"</span></span>|<span data-ttu-id="66592-156">Gestionnaire de connexions pour les connexions SMTP.</span><span class="sxs-lookup"><span data-stu-id="66592-156">Connection manager for SMTP connections.</span></span>|  
|<span data-ttu-id="66592-157">"WMI"</span><span class="sxs-lookup"><span data-stu-id="66592-157">"WMI"</span></span>|<span data-ttu-id="66592-158">Gestionnaire de connexions pour les connexions WMI (Microsoft Windows Management Instrumentation).</span><span class="sxs-lookup"><span data-stu-id="66592-158">Connection manager for Microsoft Windows Management Instrumentation (WMI) connections.</span></span>|  
  
 <span data-ttu-id="66592-159">L'exemple de code suivant montre l'ajout d'une connexion OLE DB et FILE à la collection <xref:Microsoft.SqlServer.Dts.Runtime.Package.Connections%2A> d'un objet <xref:Microsoft.SqlServer.Dts.Runtime.Package>.</span><span class="sxs-lookup"><span data-stu-id="66592-159">The following code example demonstrates adding an OLE DB and FILE connection to the <xref:Microsoft.SqlServer.Dts.Runtime.Package.Connections%2A> collection of a <xref:Microsoft.SqlServer.Dts.Runtime.Package>.</span></span> <span data-ttu-id="66592-160">L'exemple définit ensuite les propriétés <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.ConnectionString%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Name%2A> et <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Description%2A>.</span><span class="sxs-lookup"><span data-stu-id="66592-160">The example then sets the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.ConnectionString%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Name%2A>, and <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.Description%2A> properties.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      // Create a package, and retrieve its connections.  
      Package pkg = new Package();  
      Connections pkgConns = pkg.Connections;  
  
      // Add an OLE DB connection to the package, using the   
      // method defined in the AddConnection class.  
      CreateConnection myOLEDBConn = new CreateConnection();  
      myOLEDBConn.CreateOLEDBConnection(pkg);  
  
      // View the new connection in the package.  
      Console.WriteLine("Connection description: {0}",  
         pkg.Connections["SSIS Connection Manager for OLE DB"].Description);  
  
      // Add a second connection to the package.  
      CreateConnection myFileConn = new CreateConnection();  
      myFileConn.CreateFileConnection(pkg);  
  
      // View the second connection in the package.  
      Console.WriteLine("Connection description: {0}",  
        pkg.Connections["SSIS Connection Manager for Files"].Description);  
  
      Console.WriteLine();  
      Console.WriteLine("Number of connections in package: {0}", pkg.Connections.Count);  
  
      Console.Read();  
    }  
  }  
  // <summary>  
  // This class contains the definitions for multiple  
  // connection managers.  
  // </summary>  
  public class CreateConnection  
  {  
    // Private data.  
    private ConnectionManager ConMgr;  
  
    // Class definition for OLE DB Provider.  
    public void CreateOLEDBConnection(Package p)  
    {  
      ConMgr = p.Connections.Add("OLEDB");  
      ConMgr.ConnectionString = "Provider=SQLOLEDB.1;" +  
        "Integrated Security=SSPI;Initial Catalog=AdventureWorks;" +  
        "Data Source=(local);";  
      ConMgr.Name = "SSIS Connection Manager for OLE DB";  
      ConMgr.Description = "OLE DB connection to the AdventureWorks database.";  
    }  
    public void CreateFileConnection(Package p)  
    {  
      ConMgr = p.Connections.Add("File");  
      ConMgr.ConnectionString = @"\\<yourserver>\<yourfolder>\books.xml";  
      ConMgr.Name = "SSIS Connection Manager for Files";  
      ConMgr.Description = "Flat File connection";  
    }  
  }  
  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    ' Create a package, and retrieve its connections.  
    Dim pkg As New Package()  
    Dim pkgConns As Connections = pkg.Connections  
  
    ' Add an OLE DB connection to the package, using the   
    ' method defined in the AddConnection class.  
    Dim myOLEDBConn As New CreateConnection()  
    myOLEDBConn.CreateOLEDBConnection(pkg)  
  
    ' View the new connection in the package.  
    Console.WriteLine("Connection description: {0}", _  
      pkg.Connections("SSIS Connection Manager for OLE DB").Description)  
  
    ' Add a second connection to the package.  
    Dim myFileConn As New CreateConnection()  
    myFileConn.CreateFileConnection(pkg)  
  
    ' View the second connection in the package.  
    Console.WriteLine("Connection description: {0}", _  
      pkg.Connections("SSIS Connection Manager for Files").Description)  
  
    Console.WriteLine()  
    Console.WriteLine("Number of connections in package: {0}", pkg.Connections.Count)  
  
    Console.Read()  
  
  End Sub  
  
End Module  
  
' This class contains the definitions for multiple  
' connection managers.  
  
Public Class CreateConnection  
  ' Private data.  
  Private ConMgr As ConnectionManager  
  
  ' Class definition for OLE DB provider.  
  Public Sub CreateOLEDBConnection(ByVal p As Package)  
    ConMgr = p.Connections.Add("OLEDB")  
    ConMgr.ConnectionString = "Provider=SQLOLEDB.1;" & _  
      "Integrated Security=SSPI;Initial Catalog=AdventureWorks;" & _  
      "Data Source=(local);"  
    ConMgr.Name = "SSIS Connection Manager for OLE DB"  
    ConMgr.Description = "OLE DB connection to the AdventureWorks database."  
  End Sub  
  
  Public Sub CreateFileConnection(ByVal p As Package)  
    ConMgr = p.Connections.Add("File")  
    ConMgr.ConnectionString = "\\<yourserver>\<yourfolder>\books.xml"  
    ConMgr.Name = "SSIS Connection Manager for Files"  
    ConMgr.Description = "Flat File connection"  
  End Sub  
  
End Class  
```  
  
 <span data-ttu-id="66592-161">**Exemple de sortie :**</span><span class="sxs-lookup"><span data-stu-id="66592-161">**Sample Output:**</span></span>  
  
 `Connection description: OLE DB connection to the AdventureWorks database.`  
  
 `Connection description: OLE DB connection to the AdventureWorks database.`  
  
 `Number of connections in package: 2`  
  
## <a name="external-resources"></a><span data-ttu-id="66592-162">Ressources externes</span><span class="sxs-lookup"><span data-stu-id="66592-162">External Resources</span></span>  
 <span data-ttu-id="66592-163">Article technique, [Connection Strings](https://go.microsoft.com/fwlink/?LinkId=220743), sur carlprothman.net.</span><span class="sxs-lookup"><span data-stu-id="66592-163">Technical article, [Connection Strings](https://go.microsoft.com/fwlink/?LinkId=220743), on carlprothman.net.</span></span>  
  
<span data-ttu-id="66592-164">![Icône de Integration Services (petite)](../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="66592-164">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="66592-165">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="66592-165">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="66592-166">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="66592-166">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="66592-167">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="66592-167">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66592-168">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="66592-168">See Also</span></span>  
 <span data-ttu-id="66592-169">[Integration Services &#40;les connexions de&#41; SSIS](../connection-manager/integration-services-ssis-connections.md) </span><span class="sxs-lookup"><span data-stu-id="66592-169">[Integration Services &#40;SSIS&#41; Connections](../connection-manager/integration-services-ssis-connections.md) </span></span>  
 [<span data-ttu-id="66592-170">Créer des gestionnaires de connexions</span><span class="sxs-lookup"><span data-stu-id="66592-170">Create Connection Managers</span></span>](../create-connection-managers.md)  
  
  
