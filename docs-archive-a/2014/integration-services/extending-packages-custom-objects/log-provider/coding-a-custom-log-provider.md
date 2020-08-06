---
title: Codage d’un module fournisseur d’informations personnalisé | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- custom log providers [Integration Services], coding
ms.assetid: 979a29ca-956e-4fdd-ab47-f06e84cead7a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5d529420207ac065ae5ecb3c1d984de3021845b0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701303"
---
# <a name="coding-a-custom-log-provider"></a><span data-ttu-id="d7700-102">Codage d'un module fournisseur d'informations personnalisé</span><span class="sxs-lookup"><span data-stu-id="d7700-102">Coding a Custom Log Provider</span></span>
  <span data-ttu-id="d7700-103">Après avoir créé une classe qui hérite de la classe de base <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase>, puis appliqué l'attribut <xref:Microsoft.SqlServer.Dts.Runtime.DtsLogProviderAttribute> à cette classe, vous devez substituer l'implémentation des propriétés et des méthodes de la classe de base afin de fournir vos fonctionnalités personnalisées.</span><span class="sxs-lookup"><span data-stu-id="d7700-103">After you have created a class that inherits from the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase> base class, and applied the <xref:Microsoft.SqlServer.Dts.Runtime.DtsLogProviderAttribute> attribute to the class, you must override the implementation of the properties and methods of the base class to provide your custom functionality.</span></span>  
  
 <span data-ttu-id="d7700-104">Pour obtenir des exemples fonctionnels de modules personnalisés, consultez [Développement d’une interface utilisateur pour un module fournisseur d’informations personnalisé](developing-a-user-interface-for-a-custom-log-provider.md).</span><span class="sxs-lookup"><span data-stu-id="d7700-104">For working samples of custom log providers, see [Developing a User Interface for a Custom Log Provider](developing-a-user-interface-for-a-custom-log-provider.md).</span></span>  
  
## <a name="configuring-the-log-provider"></a><span data-ttu-id="d7700-105">Configuration du module fournisseur d’informations</span><span class="sxs-lookup"><span data-stu-id="d7700-105">Configuring the Log Provider</span></span>  
  
### <a name="initializing-the-log-provider"></a><span data-ttu-id="d7700-106">Initialisation du module fournisseur d'informations</span><span class="sxs-lookup"><span data-stu-id="d7700-106">Initializing the Log Provider</span></span>  
 <span data-ttu-id="d7700-107">Vous remplacez la méthode <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.InitializeLogProvider%2A> pour mettre en cache des références à la collection de connexions et à l'interface d'événements.</span><span class="sxs-lookup"><span data-stu-id="d7700-107">You override the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.InitializeLogProvider%2A> method to cache references to the connections collection and the events interface.</span></span> <span data-ttu-id="d7700-108">Vous pouvez utiliser ces références mises en cache ultérieurement dans d'autres méthodes du module fournisseur d'informations.</span><span class="sxs-lookup"><span data-stu-id="d7700-108">You can use these cached references later in other methods of the log provider.</span></span>  
  
### <a name="using-the-configstring-property"></a><span data-ttu-id="d7700-109">Utilisation de la propriété ConfigString</span><span class="sxs-lookup"><span data-stu-id="d7700-109">Using the ConfigString Property</span></span>  
 <span data-ttu-id="d7700-110">Au moment de la conception, un module fournisseur d’informations reçoit des informations de configuration de la colonne **Configuration**.</span><span class="sxs-lookup"><span data-stu-id="d7700-110">At design time, a log provider receives configuration information from the **Configuration** column.</span></span> <span data-ttu-id="d7700-111">Ces informations de configuration correspondent à la propriété <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A> du module fournisseur d'informations.</span><span class="sxs-lookup"><span data-stu-id="d7700-111">This configuration information corresponds to the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A> property of the log provider.</span></span> <span data-ttu-id="d7700-112">Par défaut, cette colonne contient une zone de texte à partir de laquelle vous pouvez extraire des informations de chaîne.</span><span class="sxs-lookup"><span data-stu-id="d7700-112">By default, this column contains a text box from which you can retrieve any string information.</span></span> <span data-ttu-id="d7700-113">La plupart des modules fournisseurs d'informations inclus dans [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] utilisent cette propriété pour stocker le nom du gestionnaire de connexions que le fournisseur utilise pour se connecter à une source de données externe.</span><span class="sxs-lookup"><span data-stu-id="d7700-113">Most of the log providers included with [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] use this property to store the name of the connection manager that the provider uses to connect to an external data source.</span></span> <span data-ttu-id="d7700-114">Si votre module fournisseur d’informations utilise la propriété <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A>, utilisez la méthode <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Validate%2A> pour valider cette propriété et vous assurer que la propriété est correctement définie.</span><span class="sxs-lookup"><span data-stu-id="d7700-114">If your log provider uses the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A> property, use the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Validate%2A> method to validate this property and make sure that the property is set correctly.</span></span>  
  
### <a name="validating-the-log-provider"></a><span data-ttu-id="d7700-115">Validation du module fournisseur d'informations</span><span class="sxs-lookup"><span data-stu-id="d7700-115">Validating the Log Provider</span></span>  
 <span data-ttu-id="d7700-116">Vous remplacez la méthode <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Validate%2A> pour vous assurer que le fournisseur a été configuré correctement et qu'il est prêt pour l'exécution.</span><span class="sxs-lookup"><span data-stu-id="d7700-116">You override the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Validate%2A> method to make sure that the provider has been configured correctly and is ready for execution.</span></span> <span data-ttu-id="d7700-117">En général, un niveau minimum de validation consiste à s'assurer que la propriété <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A> est correctement définie.</span><span class="sxs-lookup"><span data-stu-id="d7700-117">Typically, a minimum level of validation is to make sure that the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A> is set correctly.</span></span> <span data-ttu-id="d7700-118">L'exécution ne peut pas continuer tant que le module fournisseur d'informations ne renvoie pas <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult.Success> à partir de la méthode <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="d7700-118">Execution cannot continue until the log provider returns <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult.Success> from the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Validate%2A> method.</span></span>  
  
 <span data-ttu-id="d7700-119">L'exemple de code suivant illustre une implémentation de <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Validate%2A> qui s'assure que le nom d'un gestionnaire de connexions est spécifié, que ce gestionnaire de connexions existe dans le package et qu'il renvoie un nom de fichier dans la propriété <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A>.</span><span class="sxs-lookup"><span data-stu-id="d7700-119">The following code example shows an implementation of <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Validate%2A> that makes sure that the name of a connection manager name is specified, that the connection manager exists in the package, and that the connection manager returns a file name in the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A> property.</span></span>  
  
```csharp  
public override DTSExecResult Validate(IDTSInfoEvents infoEvents)  
{  
    if (this.ConfigString.Length == 0 || connections.Contains(ConfigString) == false)  
    {  
        infoEvents.FireError(0, "MyTextLogProvider", "The ConnectionManager " + ConfigString + " specified in the ConfigString property cannot be found in the collection.", "", 0);  
        return DTSExecResult.Failure;  
    }  
    else  
    {  
        string fileName = connections[ConfigString].AcquireConnection(null) as string;  
  
        if (fileName == null || fileName.Length == 0)  
        {  
            infoEvents.FireError(0, "MyTextLogProvider", "The ConnectionManager " + ConfigString + " specified in the ConfigString property cannot be found in the collection.", "", 0);  
            return DTSExecResult.Failure;  
        }  
    }  
    return DTSExecResult.Success;  
}  
```  
  
```vb  
Public Overrides Function Validate(ByVal infoEvents As IDTSInfoEvents) As DTSExecResult  
    If Me.ConfigString.Length = 0 Or connections.Contains(ConfigString) = False Then  
        infoEvents.FireError(0, "MyTextLogProvider", "The ConnectionManager " + ConfigString + " specified in the ConfigString property cannot be found in the collection.", "", 0)  
        Return DTSExecResult.Failure  
    Else   
        Dim fileName As String =  connections(ConfigString).AcquireConnectionCType(as string, Nothing)  
  
        If fileName = Nothing Or fileName.Length = 0 Then  
            infoEvents.FireError(0, "MyTextLogProvider", "The ConnectionManager " + ConfigString + " specified in the ConfigString property cannot be found in the collection.", "", 0)  
            Return DTSExecResult.Failure  
        End If  
    End If  
    Return DTSExecResult.Success  
End Function  
```  
  
### <a name="persisting-the-log-provider"></a><span data-ttu-id="d7700-120">Persistance du module fournisseur d'informations</span><span class="sxs-lookup"><span data-stu-id="d7700-120">Persisting the Log Provider</span></span>  
 <span data-ttu-id="d7700-121">D'ordinaire, vous n'avez pas à implémenter de persistance personnalisée pour un gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="d7700-121">Ordinarily you do not have to implement custom persistence for a connection manager.</span></span> <span data-ttu-id="d7700-122">Une persistance personnalisée est uniquement requise lorsque les propriétés d'un objet utilisent des types de données complexes.</span><span class="sxs-lookup"><span data-stu-id="d7700-122">Custom persistence is required only when the properties of an object use complex data types.</span></span> <span data-ttu-id="d7700-123">Pour plus d’informations, consultez [Développement d’objets personnalisés pour Integration Services](../developing-custom-objects-for-integration-services.md).</span><span class="sxs-lookup"><span data-stu-id="d7700-123">For more information, see [Developing Custom Objects for Integration Services](../developing-custom-objects-for-integration-services.md).</span></span>  
  
## <a name="logging-with-the-log-provider"></a><span data-ttu-id="d7700-124">Journalisation avec le module fournisseur d'informations</span><span class="sxs-lookup"><span data-stu-id="d7700-124">Logging with the Log Provider</span></span>  
 <span data-ttu-id="d7700-125">Il existe trois méthodes d'exécution qui doivent être remplacées par tous les modules fournisseurs d'informations : <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A> et <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.CloseLog%2A>.</span><span class="sxs-lookup"><span data-stu-id="d7700-125">There are three run-time methods that must be overridden by all log providers: <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A>, <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A>, and <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.CloseLog%2A>.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d7700-126">Pendant la validation et l'exécution d'un package unique, les méthodes <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A> et <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.CloseLog%2A> sont appelées plusieurs fois.</span><span class="sxs-lookup"><span data-stu-id="d7700-126">During the validation and execution of a single package, the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.CloseLog%2A> methods are called more than one time.</span></span> <span data-ttu-id="d7700-127">Assurez-vous que votre code personnalisé n'engendre pas l'écrasement des entrées de journal précédentes lors de l'ouverture et de la fermeture suivantes du journal.</span><span class="sxs-lookup"><span data-stu-id="d7700-127">Make sure that your custom code does not cause earlier log entries to be overwritten by the next opening and closing of the log.</span></span> <span data-ttu-id="d7700-128">Si vous avez choisi de journaliser les événements de validation dans votre package test, le premier événement journalisé que vous devez voir est OnPreValidate ; si le premier événement journalisé est PackageStart, les événements de validation initiaux ont été écrasés.</span><span class="sxs-lookup"><span data-stu-id="d7700-128">If you have selected to log validation events in your test package, the first logged event that you should see is OnPreValidate; if instead the first logged event that you see is PackageStart, the initial validation events have been overwritten.</span></span>  
  
### <a name="opening-the-log"></a><span data-ttu-id="d7700-129">Ouverture du journal</span><span class="sxs-lookup"><span data-stu-id="d7700-129">Opening the Log</span></span>  
 <span data-ttu-id="d7700-130">La plupart des modules fournisseurs d'informations se connectent à une source de données externe, telle qu'un fichier ou une base de données, pour stocker les informations d'événements collectées pendant l'exécution du package.</span><span class="sxs-lookup"><span data-stu-id="d7700-130">Most log providers connect to an external data source, such as a file or database, to store the event information that is collected during package execution.</span></span> <span data-ttu-id="d7700-131">Comme avec tout autre objet inclus dans l'exécution, la connexion à la source de données externe est en général établie en utilisant des objets de gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="d7700-131">As with any other object in the runtime, connecting to the external data source is typically accomplished by using connection manager objects.</span></span>  
  
 <span data-ttu-id="d7700-132">La méthode <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A> est appelée au début de l'exécution du package. Remplacez cette méthode pour établir une connexion à la source de données externe.</span><span class="sxs-lookup"><span data-stu-id="d7700-132">The <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A> method is called at the start of package execution.Override this method to establish a connection to the external data source.</span></span>  
  
 <span data-ttu-id="d7700-133">L'exemple de code suivant représente un module fournisseur d'informations qui ouvre un fichier texte à des fins d'écriture pendant la méthode <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A>.</span><span class="sxs-lookup"><span data-stu-id="d7700-133">The following sample code shows a log provider that opens a text file for writing during <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A>.</span></span> <span data-ttu-id="d7700-134">Il ouvre le fichier en appelant la méthode <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> du gestionnaire de connexions qui a été spécifié dans la propriété <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A>.</span><span class="sxs-lookup"><span data-stu-id="d7700-134">It opens the file by calling the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> method of the connection manager that was specified in the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A> property.</span></span>  
  
```csharp  
public override void OpenLog()  
{  
    if(!this.connections.Contains(this.ConfigString))  
        throw new Exception("The ConnectionManager " + this.ConfigString + " does not exist in the Connections collection.");  
  
    this.connectionManager = connections[ConfigString];  
    string filePath = this.connectionManager.AcquireConnection(null) as string;  
  
    if(filePath == null || filePath.Length == 0)  
        throw new Exception("The ConnectionManager " + this.ConfigString + " is not a valid FILE ConnectionManager");  
  
    //  Create a StreamWriter to append to.  
    sw = new StreamWriter(filePath,true);  
  
    sw.WriteLine("Open log" + System.DateTime.Now.ToShortTimeString());  
}  
```  
  
```vb  
Public Overrides  Sub OpenLog()  
    If Not Me.connections.Contains(Me.ConfigString) Then  
        Throw New Exception("The ConnectionManager " + Me.ConfigString + " does not exist in the Connections collection.")  
    End If  
  
    Me.connectionManager = connections(ConfigString)  
    Dim filePath As String =  Me.connectionManager.AcquireConnectionCType(as string, Nothing)  
  
    If filePath = Nothing Or filePath.Length = 0 Then  
        Throw New Exception("The ConnectionManager " + Me.ConfigString + " is not a valid FILE ConnectionManager")  
    End If  
  
    '  Create a StreamWriter to append to.  
    sw = New StreamWriter(filePath,True)  
  
    sw.WriteLine("Open log" + System.DateTime.Now.ToShortTimeString())  
End Sub  
```  
  
### <a name="writing-log-entries"></a><span data-ttu-id="d7700-135">Écriture des entrées du journal</span><span class="sxs-lookup"><span data-stu-id="d7700-135">Writing Log Entries</span></span>  
 <span data-ttu-id="d7700-136">La méthode <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A> est appelée chaque fois qu’un objet compris dans le package déclenche un événement en appelant une méthode Fire\<event> sur l’une des interfaces d’événements.</span><span class="sxs-lookup"><span data-stu-id="d7700-136">The <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A> method is called every time that an object in the package raises an event by calling a Fire\<event> method on one of the event interfaces.</span></span> <span data-ttu-id="d7700-137">Chaque événement est déclenché avec des informations sur son contexte et habituellement un message explicatif.</span><span class="sxs-lookup"><span data-stu-id="d7700-137">Each event is raised with information about its context and usually an explanatory message.</span></span> <span data-ttu-id="d7700-138">Toutefois, tous les appels de la méthode <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A> n'incluent pas d'informations sur chaque paramètre de méthode.</span><span class="sxs-lookup"><span data-stu-id="d7700-138">However, not every call to the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A> method includes information for every method parameter.</span></span> <span data-ttu-id="d7700-139">Par exemple, certains événements standard dont les noms sont évidents ne fournissent pas MessageText, et DataCode et DataBytes sont prévus pour des informations supplémentaires facultatives.</span><span class="sxs-lookup"><span data-stu-id="d7700-139">For example, some standard events whose names are self-explanatory do not provide MessageText, and DataCode and DataBytes are intended for optional supplemental information.</span></span>  
  
 <span data-ttu-id="d7700-140">L'exemple de code suivant implémente la méthode <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A> et écrit les événements dans le flux qui a été ouvert dans la section précédente.</span><span class="sxs-lookup"><span data-stu-id="d7700-140">The following code example implements the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A> method, and writes the events to the stream that was opened in the previous section.</span></span>  
  
```csharp  
public override void Log(string logEntryName, string computerName, string operatorName, string sourceName, string sourceID, string executionID, string messageText, DateTime startTime, DateTime endTime, int dataCode, byte[] dataBytes)  
{  
    sw.Write(logEntryName + ",");  
    sw.Write(computerName + ",");  
    sw.Write(operatorName + ",");  
    sw.Write(sourceName + ",");  
    sw.Write(sourceID + ",");  
    sw.Write(messageText + ",");  
    sw.Write(dataBytes + ",");  
    sw.WriteLine("");  
}  
```  
  
```vb  
Public Overrides  Sub Log(ByVal logEnTryName As String, ByVal computerName As String, ByVal operatorName As String, ByVal sourceName As String, ByVal sourceID As String, ByVal executionID As String, ByVal messageText As String, ByVal startTime As DateTime, ByVal endTime As DateTime, ByVal dataCode As Integer, ByVal dataBytes() As Byte)  
    sw.Write(logEnTryName + ",")  
    sw.Write(computerName + ",")  
    sw.Write(operatorName + ",")  
    sw.Write(sourceName + ",")  
    sw.Write(sourceID + ",")  
    sw.Write(messageText + ",")  
    sw.Write(dataBytes + ",")  
    sw.WriteLine("")  
End Sub  
```  
  
### <a name="closing-the-log"></a><span data-ttu-id="d7700-141">Fermeture du journal</span><span class="sxs-lookup"><span data-stu-id="d7700-141">Closing the Log</span></span>  
 <span data-ttu-id="d7700-142">La méthode <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.CloseLog%2A> est appelée à la fin de l'exécution du package, une fois que tous les objets compris dans le package ont achevé leur exécution ou lorsque le package s'arrête en raison d'erreurs.</span><span class="sxs-lookup"><span data-stu-id="d7700-142">The <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.CloseLog%2A> method is called at the end of package execution, after all the objects in the package have completed execution, or, when the package stops because of errors.</span></span>  
  
 <span data-ttu-id="d7700-143">L'exemple de code suivant montre une implémentation de la méthode <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.CloseLog%2A> qui ferme le flux de fichiers qui a été ouvert pendant la méthode <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A>.</span><span class="sxs-lookup"><span data-stu-id="d7700-143">The following code example demonstrates an implementation of the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.CloseLog%2A> method that closes the file stream that was opened during the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.OpenLog%2A> method.</span></span>  
  
```csharp  
public override void CloseLog()  
{  
    if (sw != null)  
    {  
        sw.WriteLine("Close log" + System.DateTime.Now.ToShortTimeString());  
        sw.Close();  
    }  
}  
```  
  
```vb  
Public Overrides  Sub CloseLog()  
    If Not sw Is Nothing Then  
        sw.WriteLine("Close log" + System.DateTime.Now.ToShortTimeString())  
        sw.Close()  
    End If  
End Sub  
```  
  
<span data-ttu-id="d7700-144">![Icône de Integration Services (petite)](../../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="d7700-144">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="d7700-145">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="d7700-145">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="d7700-146">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="d7700-146">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="d7700-147">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="d7700-147">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7700-148">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d7700-148">See Also</span></span>  
 <span data-ttu-id="d7700-149">[Création d’un module fournisseur d’informations personnalisé](creating-a-custom-log-provider.md) </span><span class="sxs-lookup"><span data-stu-id="d7700-149">[Creating a Custom Log Provider](creating-a-custom-log-provider.md) </span></span>  
 [<span data-ttu-id="d7700-150">Développement d’une interface utilisateur pour un module fournisseur d’informations personnalisé</span><span class="sxs-lookup"><span data-stu-id="d7700-150">Developing a User Interface for a Custom Log Provider</span></span>](developing-a-user-interface-for-a-custom-log-provider.md)  
  
  
