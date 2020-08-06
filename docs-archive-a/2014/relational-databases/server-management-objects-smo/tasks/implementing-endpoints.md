---
title: Implémentation des points de terminaison | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- endpoints [SMO]
ms.assetid: f8674dbb-9bc0-488f-9def-e9e0ce1ddf86
author: stevestein
ms.author: sstein
ms.openlocfilehash: 293a661c6e1ad6f6139e30e0824e99686af98f90
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707323"
---
# <a name="implementing-endpoints"></a><span data-ttu-id="efeca-102">Implémentation de points de terminaison</span><span class="sxs-lookup"><span data-stu-id="efeca-102">Implementing Endpoints</span></span>
  <span data-ttu-id="efeca-103">Un point de terminaison est un service qui peut écouter les requêtes en mode natif.</span><span class="sxs-lookup"><span data-stu-id="efeca-103">An endpoint is a service that can listen natively for requests.</span></span> <span data-ttu-id="efeca-104">SMO prend en charge différents types de points de terminaison en utilisant l'objet <xref:Microsoft.SqlServer.Management.Smo.Endpoint>.</span><span class="sxs-lookup"><span data-stu-id="efeca-104">SMO supports various types of endpoints by using the <xref:Microsoft.SqlServer.Management.Smo.Endpoint> object.</span></span> <span data-ttu-id="efeca-105">Vous pouvez créer un service de point de terminaison qui gère un type spécifique de charge utile, qui utilise un protocole spécifique, en créant une instance d'un objet <xref:Microsoft.SqlServer.Management.Smo.Endpoint> et en définissant ses propriétés.</span><span class="sxs-lookup"><span data-stu-id="efeca-105">You can create an endpoint service that handles a specific type of payload, which uses a specific protocol, by creating an instance of an <xref:Microsoft.SqlServer.Management.Smo.Endpoint> object and setting its properties.</span></span>  
  
 <span data-ttu-id="efeca-106">La propriété <xref:Microsoft.SqlServer.Management.Smo.Endpoint.EndpointType%2A> de l'objet <xref:Microsoft.SqlServer.Management.Smo.Endpoint> peut être utilisée pour spécifier l'un des types de charge utile suivants :</span><span class="sxs-lookup"><span data-stu-id="efeca-106">The <xref:Microsoft.SqlServer.Management.Smo.Endpoint.EndpointType%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Endpoint> object can be used to specify on of the following payload types:</span></span>  
  
-   <span data-ttu-id="efeca-107">Mise en miroir de bases de données</span><span class="sxs-lookup"><span data-stu-id="efeca-107">Database mirroring</span></span>  
  
-   <span data-ttu-id="efeca-108">SOAP (la prise en charge des points de terminaison SOAP est présente dans [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] et les versions antérieures de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] )</span><span class="sxs-lookup"><span data-stu-id="efeca-108">SOAP (support for SOAP endpoints is present in [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] and earlier [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] versions)</span></span>  
  
-   <span data-ttu-id="efeca-109">Service Broker</span><span class="sxs-lookup"><span data-stu-id="efeca-109">Service Broker</span></span>  
  
-   [!INCLUDE[tsql](../../../includes/tsql-md.md)]  
  
 <span data-ttu-id="efeca-110">En outre, la propriété <xref:Microsoft.SqlServer.Management.Smo.Endpoint.ProtocolType%2A> peut être utilisée pour spécifier les deux protocoles pris en charge qui suivent :</span><span class="sxs-lookup"><span data-stu-id="efeca-110">Also, the <xref:Microsoft.SqlServer.Management.Smo.Endpoint.ProtocolType%2A> property can be used to specify the following two supported protocols:</span></span>  
  
-   <span data-ttu-id="efeca-111">Protocole HTTP</span><span class="sxs-lookup"><span data-stu-id="efeca-111">HTTP protocol</span></span>  
  
-   <span data-ttu-id="efeca-112">Protocole TCP</span><span class="sxs-lookup"><span data-stu-id="efeca-112">TCP protocol</span></span>  
  
 <span data-ttu-id="efeca-113">Après avoir précisé le type de charge utile, il est possible de définir la charge utile réelle à l'aide de la propriété d'objet <xref:Microsoft.SqlServer.Management.Smo.Endpoint.Payload%2A>.</span><span class="sxs-lookup"><span data-stu-id="efeca-113">Having specified the type of payload, the actual payload can be set by using the <xref:Microsoft.SqlServer.Management.Smo.Endpoint.Payload%2A> object property.</span></span> <span data-ttu-id="efeca-114">La propriété d'objet <xref:Microsoft.SqlServer.Management.Smo.Payload> fournit une référence vers un objet de charge utile du type spécifié, dont les propriétés peuvent être modifiées.</span><span class="sxs-lookup"><span data-stu-id="efeca-114">The <xref:Microsoft.SqlServer.Management.Smo.Payload> object property provides a reference to a payload object of the specified type, for which the properties can be modified.</span></span>  
  
 <span data-ttu-id="efeca-115">Pour l'objet <xref:Microsoft.SqlServer.Management.Smo.DatabaseMirroringPayload>, vous devez spécifier le rôle de mise en miroir et si le chiffrement est activé.</span><span class="sxs-lookup"><span data-stu-id="efeca-115">For the <xref:Microsoft.SqlServer.Management.Smo.DatabaseMirroringPayload> object, you must specify the mirroring role and whether encryption is enabled.</span></span> <span data-ttu-id="efeca-116">L'objet <xref:Microsoft.SqlServer.Management.Smo.ServiceBrokerPayload> requiert des informations à propos du transfert de messages, du nombre maximal de connexions autorisé et du mode d'authentification.</span><span class="sxs-lookup"><span data-stu-id="efeca-116">The <xref:Microsoft.SqlServer.Management.Smo.ServiceBrokerPayload> object requires information about message forwarding, maximum number of connections allowed and the authentication mode.</span></span> <span data-ttu-id="efeca-117">L'objet <xref:Microsoft.SqlServer.Management.Smo.SoapPayloadMethod.%23ctor%2A> requiert la définition de différentes propriétés, notamment la propriété d'objet <xref:Microsoft.SqlServer.Management.Smo.SoapPayloadMethodCollection.Add%2A> qui spécifie les méthodes de charge utile SOAP disponibles pour les clients (procédures stockées et fonctions définies par l'utilisateur).</span><span class="sxs-lookup"><span data-stu-id="efeca-117">The <xref:Microsoft.SqlServer.Management.Smo.SoapPayloadMethod.%23ctor%2A> object requires various properties to be set including the <xref:Microsoft.SqlServer.Management.Smo.SoapPayloadMethodCollection.Add%2A> object property that specifies the SOAP payload methods available to clients (stored procedures and user-defined functions).</span></span>  
  
 <span data-ttu-id="efeca-118">De la même façon, le protocole réel peut être défini à l'aide de la propriété d'objet <xref:Microsoft.SqlServer.Management.Smo.Endpoint.Protocol%2A> qui référence un objet de protocole du type spécifié par propriété <xref:Microsoft.SqlServer.Management.Smo.Endpoint.ProtocolType%2A>.</span><span class="sxs-lookup"><span data-stu-id="efeca-118">Similarly, the actual protocol can be set by using the <xref:Microsoft.SqlServer.Management.Smo.Endpoint.Protocol%2A> object property that references a protocol object of the type specified by <xref:Microsoft.SqlServer.Management.Smo.Endpoint.ProtocolType%2A> property.</span></span> <span data-ttu-id="efeca-119">L'objet <xref:Microsoft.SqlServer.Management.Smo.HttpProtocol> requiert une liste d'adresses IP restreintes, ainsi que des informations sur le port, le site Web et l'authentification.</span><span class="sxs-lookup"><span data-stu-id="efeca-119">The <xref:Microsoft.SqlServer.Management.Smo.HttpProtocol> object requires a list of restricted IP addresses, and port, website, and authentication information.</span></span> <span data-ttu-id="efeca-120">L'objet <xref:Microsoft.SqlServer.Management.Smo.TcpProtocol> requiert également une liste d'adresses IP restreintes, ainsi que des informations sur le port.</span><span class="sxs-lookup"><span data-stu-id="efeca-120">The <xref:Microsoft.SqlServer.Management.Smo.TcpProtocol> object also requires a list of restricted IP addresses and port information.</span></span>  
  
 <span data-ttu-id="efeca-121">Lorsque le point de terminaison a été créé et complètement défini, l'accès peut être accordé, révoqué ou refusé aux utilisateurs, groupes, rôles et ouvertures de session de la base de données.</span><span class="sxs-lookup"><span data-stu-id="efeca-121">When the endpoint has been created and fully defined, access can be granted to, revoked from, and denied to database users, groups, roles, and logons.</span></span>  
  
## <a name="example"></a><span data-ttu-id="efeca-122">Exemple</span><span class="sxs-lookup"><span data-stu-id="efeca-122">Example</span></span>  
 <span data-ttu-id="efeca-123">Dans l'exemple de code suivant, vous devez sélectionner l'environnement, le modèle et le langage de programmation à utiliser pour créer votre application.</span><span class="sxs-lookup"><span data-stu-id="efeca-123">For the following code example, you will have to select the programming environment, programming template and the programming language to create your application.</span></span> <span data-ttu-id="efeca-124">Pour plus d’informations, consultez [créer un projet Visual Basic Smo dans Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) et [créer un projet Visual C&#35; Smo dans Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="efeca-124">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) and [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="creating-a-database-mirroring-endpoint-service-in-visual-basic"></a><span data-ttu-id="efeca-125">Création d'un service de point de terminaison de mise en miroir de bases de données en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="efeca-125">Creating a Database Mirroring Endpoint Service in Visual Basic</span></span>  
 <span data-ttu-id="efeca-126">L'exemple de code montre comment créer un point de terminaison pour la mise en miroir de bases de données dans SMO.</span><span class="sxs-lookup"><span data-stu-id="efeca-126">The code example demonstrates how to create a Database Mirroring endpoint in SMO.</span></span> <span data-ttu-id="efeca-127">Cette étape est requise avant la création du miroir de base de données.</span><span class="sxs-lookup"><span data-stu-id="efeca-127">This is necessary before you create a database mirror.</span></span> <span data-ttu-id="efeca-128">Utilisez la propriété <xref:Microsoft.SqlServer.Management.Smo.Database.IsMirroringEnabled%2A> et d'autres propriétés sur l'objet <xref:Microsoft.SqlServer.Management.Smo.Database> pour créer un miroir de base de données.</span><span class="sxs-lookup"><span data-stu-id="efeca-128">Use the <xref:Microsoft.SqlServer.Management.Smo.Database.IsMirroringEnabled%2A> and other properties on the <xref:Microsoft.SqlServer.Management.Smo.Database> object to create a database mirror.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBEndpoints1](SMO How to#SMO_VBEndpoints1)]  -->  
  
## <a name="creating-a-database-mirroring-endpoint-service-in-visual-c"></a><span data-ttu-id="efeca-129">Création d'un service de point de terminaison de mise en miroir de bases de données en Visual C#</span><span class="sxs-lookup"><span data-stu-id="efeca-129">Creating a Database Mirroring Endpoint Service in Visual C#</span></span>  
 <span data-ttu-id="efeca-130">L'exemple de code montre comment créer un point de terminaison pour la mise en miroir de bases de données dans SMO.</span><span class="sxs-lookup"><span data-stu-id="efeca-130">The code example demonstrates how to create a Database Mirroring endpoint in SMO.</span></span> <span data-ttu-id="efeca-131">Cette étape est requise avant la création du miroir de base de données.</span><span class="sxs-lookup"><span data-stu-id="efeca-131">This is necessary before you create a database mirror.</span></span> <span data-ttu-id="efeca-132">Utilisez la propriété <xref:Microsoft.SqlServer.Management.Smo.Database.IsMirroringEnabled%2A> et d'autres propriétés sur l'objet <xref:Microsoft.SqlServer.Management.Smo.Database> pour créer un miroir de base de données.</span><span class="sxs-lookup"><span data-stu-id="efeca-132">Use the <xref:Microsoft.SqlServer.Management.Smo.Database.IsMirroringEnabled%2A> and other properties on the <xref:Microsoft.SqlServer.Management.Smo.Database> object to create a database mirror.</span></span>  
  
```csharp
{  
            //Set up a database mirroring endpoint on the server before   
        //setting up a database mirror.   
        //Connect to the local, default instance of SQL Server.   
            Server srv = new Server();  
            //Define an Endpoint object variable for database mirroring.   
            Endpoint ep = default(Endpoint);  
            ep = new Endpoint(srv, "Mirroring_Endpoint");  
            ep.ProtocolType = ProtocolType.Tcp;  
            ep.EndpointType = EndpointType.DatabaseMirroring;  
            //Specify the protocol ports.   
            ep.Protocol.Http.SslPort = 5024;  
            ep.Protocol.Tcp.ListenerPort = 6666;  
            //Specify the role of the payload.   
            ep.Payload.DatabaseMirroring.ServerMirroringRole = ServerMirroringRole.All;  
            //Create the endpoint on the instance of SQL Server.   
            ep.Create();  
            //Start the endpoint.   
            ep.Start();  
            Console.WriteLine(ep.EndpointState);  
        }  
```  
  
## <a name="creating-a-database-mirroring-endpoint-service-in-powershell"></a><span data-ttu-id="efeca-133">Création d'un service de point de terminaison de mise en miroir de bases de données dans PowerShell</span><span class="sxs-lookup"><span data-stu-id="efeca-133">Creating a Database Mirroring Endpoint Service in PowerShell</span></span>  
 <span data-ttu-id="efeca-134">L'exemple de code montre comment créer un point de terminaison pour la mise en miroir de bases de données dans SMO.</span><span class="sxs-lookup"><span data-stu-id="efeca-134">The code example demonstrates how to create a Database Mirroring endpoint in SMO.</span></span> <span data-ttu-id="efeca-135">Cette étape est requise avant la création du miroir de base de données.</span><span class="sxs-lookup"><span data-stu-id="efeca-135">This is necessary before you create a database mirror.</span></span> <span data-ttu-id="efeca-136">Utilisez la propriété <xref:Microsoft.SqlServer.Management.Smo.Database.IsMirroringEnabled%2A> et d'autres propriétés sur l'objet <xref:Microsoft.SqlServer.Management.Smo.Database> pour créer un miroir de base de données.</span><span class="sxs-lookup"><span data-stu-id="efeca-136">Use the <xref:Microsoft.SqlServer.Management.Smo.Database.IsMirroringEnabled%2A> and other properties on the <xref:Microsoft.SqlServer.Management.Smo.Database> object to create a database mirror.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server.  
CD \sql\localhost\  
$srv = Get-Item default  
  
#Get a new endpoint to congure and add  
$ep = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Endpoint -argumentlist $srv,"Mirroring_Endpoint"  
  
#Set some properties  
$ep.ProtocolType = [Microsoft.SqlServer.Management.SMO.ProtocolType]::Tcp  
$ep.EndpointType = [Microsoft.SqlServer.Management.SMO.EndpointType]::DatabaseMirroring  
$ep.Protocol.Http.SslPort = 5024  
$ep.Protocol.Tcp.ListenerPort = 6666 #inline comment  
$ep.Payload.DatabaseMirroring.ServerMirroringRole = [Microsoft.SqlServer.Management.SMO.ServerMirroringRole]::All  
  
# Create the endpoint on the instance  
$ep.Create()  
  
# Start the endpoint  
$ep.Start()  
  
# Report its state  
$ep.EndpointState;  
```  
  
## <a name="see-also"></a><span data-ttu-id="efeca-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="efeca-137">See Also</span></span>  
 [<span data-ttu-id="efeca-138">Point de terminaison de mise en miroir de bases de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="efeca-138">The Database Mirroring Endpoint &#40;SQL Server&#41;</span></span>](../../../database-engine/database-mirroring/the-database-mirroring-endpoint-sql-server.md)  
