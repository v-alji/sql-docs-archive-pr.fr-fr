---
title: Gestion des événements SMO | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- events [SMO]
- SQL Server Management Objects, events
- SMO [SQL Server], events
- events [SMO], about events
ms.assetid: b4f120dd-ba78-46ff-99c5-e47effac8544
author: stevestein
ms.author: sstein
ms.openlocfilehash: f7ea438142ac283c5ad19670fa827b5e248e80f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613946"
---
# <a name="handling-smo-events"></a><span data-ttu-id="b06c5-102">Gestion des événements SMO</span><span class="sxs-lookup"><span data-stu-id="b06c5-102">Handling SMO Events</span></span>
  <span data-ttu-id="b06c5-103">Il existe des types d'événement de serveur auxquels il est possible de s'abonner en utilisant un gestionnaire d'événements et l'objet <xref:Microsoft.SqlServer.Management.Common.ServerConnection>.</span><span class="sxs-lookup"><span data-stu-id="b06c5-103">There are server event types that can be subscribed to by using an event handler and the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object.</span></span>  
  
 <span data-ttu-id="b06c5-104">De nombreuses classes d'instance dans SMO [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Management Objects) peuvent déclencher des événements lorsque certaines actions se produisent sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="b06c5-104">Many of the instance classes in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Management Objects (SMO) can trigger events when certain actions on the server occur.</span></span>  
  
 <span data-ttu-id="b06c5-105">Ces événements peuvent être contrôlés par programme en installant un gestionnaire d'événements et en s'abonnant aux événements associés.</span><span class="sxs-lookup"><span data-stu-id="b06c5-105">These events can be handled programmatically by setting up an event handler and subscribing to the associated events.</span></span> <span data-ttu-id="b06c5-106">Ce type de gestion des événements est transitoire car tous les abonnements sont supprimés lorsque le programme client SMO prend fin.</span><span class="sxs-lookup"><span data-stu-id="b06c5-106">This type of event handling is transient because all the subscriptions are removed when the SMO client program exits.</span></span>  
  
## <a name="connectioncontext-event-handling"></a><span data-ttu-id="b06c5-107">Gestion des événements ConnectionContext</span><span class="sxs-lookup"><span data-stu-id="b06c5-107">ConnectionContext Event Handling</span></span>  
 <span data-ttu-id="b06c5-108">L'objet <xref:Microsoft.SqlServer.Management.Common.ServerConnection> prend en charge plusieurs types d'événement.</span><span class="sxs-lookup"><span data-stu-id="b06c5-108">The <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object supports several event types.</span></span> <span data-ttu-id="b06c5-109">La propriété d'événement doit être définie sur une instance d'un gestionnaire d'événements approprié, et l'objet gestionnaire d'événements doit être défini comme une fonction protégée qui gère l'événement.</span><span class="sxs-lookup"><span data-stu-id="b06c5-109">The event property must be set to an instance of an appropriate event handler, and the event handler object must be defined as a protected function that handles the event.</span></span>  
  
## <a name="event-subscription"></a><span data-ttu-id="b06c5-110">Abonnement à un événement</span><span class="sxs-lookup"><span data-stu-id="b06c5-110">Event Subscription</span></span>  
 <span data-ttu-id="b06c5-111">Pour gérer des événements, vous devez écrire une classe de gestionnaire d'événements, créer une instance de cet événement, attribuer le gestionnaire d'événements à l'objet parent, puis vous abonner à l'événement.</span><span class="sxs-lookup"><span data-stu-id="b06c5-111">You handle events by writing an event handler class, creating an instance of it, assigning the event handler to the parent object, and then subscribing to the event.</span></span>  
  
 <span data-ttu-id="b06c5-112">La gestion d'événements requiert l'écriture d'une classe de gestionnaire d'événements.</span><span class="sxs-lookup"><span data-stu-id="b06c5-112">An event handler class must be written to handle events.</span></span> <span data-ttu-id="b06c5-113">La classe de gestionnaire d'événements peut contenir plusieurs fonctions de gestionnaire d'événements et doit être installée pour les événements à gérer.</span><span class="sxs-lookup"><span data-stu-id="b06c5-113">The event handler class can contain more than one event handler function, and must be installed for the events to be handled.</span></span> <span data-ttu-id="b06c5-114">Les fonctions du gestionnaire d’événements reçoivent des informations sur l’événement à partir du paramètre *ServerEventNotificatificationArgs* qui peut être utilisé pour signaler des informations sur l’événement.</span><span class="sxs-lookup"><span data-stu-id="b06c5-114">The event handler functions receive information about the event from the *ServerEventNotificatificationArgs* parameter that can be used to report information about the event.</span></span>  
  
 <span data-ttu-id="b06c5-115">Les types d’événements de base de données et de serveur qui peuvent être gérés sont répertoriés dans la <xref:Microsoft.SqlServer.Management.Smo.DatabaseEventSet> classe et la <xref:Microsoft.SqlServer.Management.Smo.ServerEventSet> classe.</span><span class="sxs-lookup"><span data-stu-id="b06c5-115">The types of database and server events that can be handled are listed in the <xref:Microsoft.SqlServer.Management.Smo.DatabaseEventSet> class and the <xref:Microsoft.SqlServer.Management.Smo.ServerEventSet>class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b06c5-116">Exemple</span><span class="sxs-lookup"><span data-stu-id="b06c5-116">Example</span></span>  
 [!INCLUDE[ssChooseProgEnv](../../../includes/sschooseprogenv-md.md)]  
  
## <a name="registering-event-handlers-and-subscribing-to-event-handling-in-visual-basic"></a><span data-ttu-id="b06c5-117">Enregistrement de gestionnaires d'événements et abonnement à la gestion des événements en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b06c5-117">Registering Event Handlers and Subscribing to Event Handling in Visual Basic</span></span>  
 <span data-ttu-id="b06c5-118">Cet exemple de code montre comment configurer le gestionnaire d'événements et comment s'abonner aux événements de base de données.</span><span class="sxs-lookup"><span data-stu-id="b06c5-118">This code example shows how to set up the event handler, and how to subscribe to the database events.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBEvents1](SMO How to#SMO_VBEvents1)]  -->  
  
## <a name="registering-event-handlers-and-subscribing-to-event-handling-in-visual-c"></a><span data-ttu-id="b06c5-119">Enregistrement de gestionnaires d'événements et abonnement à la gestion des événements en Visual C#</span><span class="sxs-lookup"><span data-stu-id="b06c5-119">Registering Event Handlers and Subscribing to Event Handling in Visual C#</span></span>  
 <span data-ttu-id="b06c5-120">Cet exemple de code montre comment configurer le gestionnaire d'événements et comment s'abonner aux événements de base de données.</span><span class="sxs-lookup"><span data-stu-id="b06c5-120">This code example shows how to set up the event handler, and how to subscribe to the database events.</span></span>  
  
```  
//Create an event handler subroutine that runs when a table is created.   
private void MyCreateEventHandler(object sender, ServerEventArgs e)   
{   
Console.WriteLine("A table has just been added to the AdventureWorks2012 database.");   
}   
//Create an event handler subroutine that runs when a table is deleted.   
private void MyDropEventHandler(object sender, ServerEventArgs e)   
{   
Console.WriteLine("A table has just been dropped from the AdventureWorks2012 database.");   
}   
public void Main()   
{   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Reference the AdventureWorks2012 database.   
Database db;   
db = srv.Databases("AdventureWorks2012");   
//Create a database event set that contains the CreateTable event only.   
DatabaseEventSet databaseCreateEventSet = new DatabaseEventSet();   
databaseCreateEventSet.CreateTable = true;   
//Create a server event handler and set it to the first event handler subroutine.   
ServerEventHandler serverCreateEventHandler;   
serverCreateEventHandler = new ServerEventHandler(MyCreateEventHandler);   
//Subscribe to the first server event handler when a CreateTable event occurs.   
db.Events.SubscribeToEvents(databaseCreateEventSet, serverCreateEventHandler);   
    //Create a database event set that contains the DropTable event only.   
DatabaseEventSet databaseDropEventSet = new DatabaseEventSet();   
databaseDropEventSet.DropTable = true;   
//Create a server event handler and set it to the second event handler subroutine.   
ServerEventHandler serverDropEventHandler;   
serverDropEventHandler = new ServerEventHandler(MyDropEventHandler);   
//Subscribe to the second server event handler when a DropTable event occurs.   
db.Events.SubscribeToEvents(databaseDropEventSet, serverDropEventHandler);   
//Start event handling.   
db.Events.StartEvents();   
//Create a table on the database.   
Table tb;   
tb = new Table(db, "Test_Table");   
Column mycol1;   
mycol1 = new Column(tb, "Name", DataType.NChar(50));   
mycol1.Collation = "Latin1_General_CI_AS";   
mycol1.Nullable = true;   
tb.Columns.Add(mycol1);   
tb.Create();   
//Remove the table.   
tb.Drop();   
//Wait until the events have occured.   
int x;   
int y;   
for (x = 1; x <= 1000000000; x++) {   
    y = x * 2;   
}   
//Stop event handling.   
db.Events.StopEvents();   
}  
```  
  
  
