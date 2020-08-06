---
title: Connexion à des sources de données dans une tâche personnalisée | Microsoft Docs
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
- ConnectionManager objects
- connection managers [Integration Services], external data sources
- data sources [Integration Services], external
- custom tasks [Integration Services], external data sources
- external data sources [Integration Services]
- connections [Integration Services], external data sources
- SSIS custom tasks, external data sources
ms.assetid: 9f0b3a43-3eaa-4b3c-bb08-29b630c11306
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 71c504f4b528a0c9809d00de74de4beb9c67c4f5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611180"
---
# <a name="connecting-to-data-sources-in-a-custom-task"></a><span data-ttu-id="d912d-102">Connexion à des sources de données dans une tâche personnalisée</span><span class="sxs-lookup"><span data-stu-id="d912d-102">Connecting to Data Sources in a Custom Task</span></span>
  <span data-ttu-id="d912d-103">Les tâches se connectent à des sources de données externes pour extraire ou enregistrer des données à l'aide d'un gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="d912d-103">Tasks connect to external data sources to retrieve or save data by using a connection manager.</span></span> <span data-ttu-id="d912d-104">Au moment de la conception, un gestionnaire de connexions représente une connexion logique et décrit des informations clés telles que le nom du serveur et des propriétés d'authentification.</span><span class="sxs-lookup"><span data-stu-id="d912d-104">At design time, a connection manager represents a logical connection, and describes key information such as the server name and any authentication properties.</span></span> <span data-ttu-id="d912d-105">Au moment de l'exécution, les tâches appellent la méthode <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> du gestionnaire de connexions pour établir la connexion physique à la source de données.</span><span class="sxs-lookup"><span data-stu-id="d912d-105">At run time, tasks call the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> method of the connection manager to establish the physical connection to the data source.</span></span>  
  
 <span data-ttu-id="d912d-106">Étant donné qu'un package peut contenir de nombreuses tâches, lesquelles peuvent chacune avoir des connexions à des sources de données différentes, le package suit tous les gestionnaires de connexions dans une collection, la collection <xref:Microsoft.SqlServer.Dts.Runtime.Connections>.</span><span class="sxs-lookup"><span data-stu-id="d912d-106">Because a package can contain many tasks, each of which may have connections to different data sources, the package tracks all the connection managers in a collection, the <xref:Microsoft.SqlServer.Dts.Runtime.Connections> collection.</span></span> <span data-ttu-id="d912d-107">Les tâches utilisent la collection de leur package pour rechercher le gestionnaire de connexions qu'elles utiliseront pendant la validation et l'exécution.</span><span class="sxs-lookup"><span data-stu-id="d912d-107">Tasks use the collection in their package to find the connection manager that they will use during validation and execution.</span></span> <span data-ttu-id="d912d-108">La collection <xref:Microsoft.SqlServer.Dts.Runtime.Connections> constitue le premier paramètre des méthodes <xref:Microsoft.SqlServer.Dts.Runtime.Task.Validate%2A> et <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A>.</span><span class="sxs-lookup"><span data-stu-id="d912d-108">The <xref:Microsoft.SqlServer.Dts.Runtime.Connections> collection is the first parameter to the <xref:Microsoft.SqlServer.Dts.Runtime.Task.Validate%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A> methods.</span></span>  
  
 <span data-ttu-id="d912d-109">Vous pouvez empêcher la tâche d'utiliser le mauvais gestionnaire de connexions en présentant les objets <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> de la collection à l'utilisateur, en utilisant une boîte de dialogue ou une liste déroulante dans l'interface utilisateur graphique.</span><span class="sxs-lookup"><span data-stu-id="d912d-109">You can prevent the task from using the wrong connection manager by displaying the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> objects from the collection to the user, by using a dialog box or drop-down list in the graphical user interface.</span></span> <span data-ttu-id="d912d-110">Cela permet à l'utilisateur de disposer d'un moyen d'effectuer une sélection uniquement parmi les objets <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> du type approprié et contenus dans le package.</span><span class="sxs-lookup"><span data-stu-id="d912d-110">This gives the user a way to select from among only those <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> objects of the appropriate type that are contained in the package.</span></span>  
  
 <span data-ttu-id="d912d-111">Les tâches appellent la méthode <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> pour établir la connexion physique à la source de données.</span><span class="sxs-lookup"><span data-stu-id="d912d-111">Tasks call the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> method to establish the physical connection to the data source.</span></span> <span data-ttu-id="d912d-112">La méthode renvoie l'objet de connexion sous-jacent qui peut alors être utilisé par la tâche.</span><span class="sxs-lookup"><span data-stu-id="d912d-112">The method returns the underlying connection object that can then be used by the task.</span></span> <span data-ttu-id="d912d-113">Étant donné que le gestionnaire de connexions isole de la tâche les détails d'implémentation de l'objet de connexion sous-jacent, la tâche doit seulement appeler la méthode <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> pour établir la connexion et n'a pas à s'occuper des autres aspects de la connexion.</span><span class="sxs-lookup"><span data-stu-id="d912d-113">Because the connection manager isolates the implementation details of the underlying connection object from the task, the task only has to call the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> method to establish the connection, and does not have to be concerned with other aspects of the connection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d912d-114">Exemple</span><span class="sxs-lookup"><span data-stu-id="d912d-114">Example</span></span>  
 <span data-ttu-id="d912d-115">L'exemple de code suivant montre la validation du nom <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> dans les méthodes Validate et Execute, puis indique comment utiliser la méthode <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> pour établir la connexion physique dans la méthode Execute.</span><span class="sxs-lookup"><span data-stu-id="d912d-115">The following sample code demonstrates validation of the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> name in the Validate and Execute methods, and shows how to use the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> method to establish the physical connection in the Execute method.</span></span>  
  
```csharp  
private string connectionManagerName = "";  
  
public string ConnectionManagerName  
{  
  get { return this.connectionManagerName; }  
  set { this.connectionManagerName = value; }  
}  
  
public override DTSExecResult Validate(  
  Connections connections, VariableDispenser variableDispenser,  
  IDTSComponentEvents componentEvents, IDTSLogging log)  
{  
  // If the connection manager exists, validation is successful;  
  // otherwise, fail validation.  
  try  
  {  
    ConnectionManager cm = connections[this.connectionManagerName];  
    return DTSExecResult.Success;  
  }  
  catch (System.Exception e)  
  {  
    componentEvents.FireError(0, "SampleTask", "Invalid connection manager.", "", 0);  
    return DTSExecResult.Failure;  
  }  
}  
  
public override DTSExecResult Execute(Connections connections,   
  VariableDispenser variableDispenser, IDTSComponentEvents componentEvents,   
  IDTSLogging log, object transaction)  
{  
  try  
  {  
    ConnectionManager cm = connections[this.connectionManagerName];  
    object connection = cm.AcquireConnection(transaction);  
    return DTSExecResult.Success;  
  }  
  catch (System.Exception exception)  
  {  
    componentEvents.FireError(0, "SampleTask", exception.Message, "", 0);  
    return DTSExecResult.Failure;  
  }  
}  
```  
  
```vb  
Private _connectionManagerName As String = ""  
  
Public Property ConnectionManagerName() As String  
  Get  
    Return Me._connectionManagerName  
  End Get  
  Set(ByVal Value As String)  
    Me._connectionManagerName = value  
  End Set  
End Property  
  
Public Overrides Function Validate( _  
  ByVal connections As Microsoft.SqlServer.Dts.Runtime.Connections, _  
  ByVal variableDispenser As Microsoft.SqlServer.Dts.Runtime.VariableDispenser, _  
  ByVal componentEvents As Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents, _  
  ByVal log As Microsoft.SqlServer.Dts.Runtime.IDTSLogging) _  
  As Microsoft.SqlServer.Dts.Runtime.DTSExecResult  
  
  ' If the connection manager exists, validation is successful;  
  ' otherwise fail validation.  
  Try  
    Dim cm As ConnectionManager = connections(Me._connectionManagerName)  
    Return DTSExecResult.Success  
  Catch e As System.Exception  
    componentEvents.FireError(0, "SampleTask", "Invalid connection manager.", "", 0)  
    Return DTSExecResult.Failure  
  End Try  
  
End Function  
  
Public Overrides Function Execute( _  
  ByVal connections As Microsoft.SqlServer.Dts.Runtime.Connections, _  
  ByVal variableDispenser As Microsoft.SqlServer.Dts.Runtime.VariableDispenser, _  
  ByVal componentEvents As Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents, _  
  ByVal log As Microsoft.SqlServer.Dts.Runtime.IDTSLogging, ByVal transaction As Object) _  
  As Microsoft.SqlServer.Dts.Runtime.DTSExecResult  
  
  Try  
    Dim cm As ConnectionManager = connections(Me._connectionManagerName)  
    Dim connection As Object = cm.AcquireConnection(transaction)  
    Return DTSExecResult.Success  
  Catch exception As System.Exception  
    componentEvents.FireError(0, "SampleTask", exception.Message, "", 0)  
    Return DTSExecResult.Failure  
  End Try  
  
End Function  
```  
  
<span data-ttu-id="d912d-116">![Icône de Integration Services (petite)](../../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="d912d-116">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="d912d-117">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="d912d-117">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="d912d-118">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="d912d-118">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="d912d-119">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="d912d-119">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d912d-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d912d-120">See Also</span></span>  
 <span data-ttu-id="d912d-121">[Integration Services &#40;les connexions de&#41; SSIS](../../connection-manager/integration-services-ssis-connections.md) </span><span class="sxs-lookup"><span data-stu-id="d912d-121">[Integration Services &#40;SSIS&#41; Connections](../../connection-manager/integration-services-ssis-connections.md) </span></span>  
 [<span data-ttu-id="d912d-122">Créer des gestionnaires de connexions</span><span class="sxs-lookup"><span data-stu-id="d912d-122">Create Connection Managers</span></span>](../../create-connection-managers.md)  
  
  
