---
title: Connexion à une instance de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- SQL Server Management Objects, connections
- connections [SMO]
- instances of SQL Server, connections
- SMO [SQL Server], connections
ms.assetid: ad3cf354-b2e3-468b-b986-1232e375fd84
author: stevestein
ms.author: sstein
ms.openlocfilehash: efc21451f4a876c6edfe4a2389ca937d11bc5c8e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613952"
---
# <a name="connecting-to-an-instance-of-sql-server"></a><span data-ttu-id="b6b9b-102">Connexion à une instance de SQL Server</span><span class="sxs-lookup"><span data-stu-id="b6b9b-102">Connecting to an Instance of SQL Server</span></span>
  <span data-ttu-id="b6b9b-103">La première étape de programmation dans une [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] application Smo (Management Objects) consiste à créer une instance de l' <xref:Microsoft.SqlServer.Management.Smo.Server> objet et à établir sa connexion à une instance de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b6b9b-103">The first programming step in a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Management Objects (SMO) application is to create an instance of the <xref:Microsoft.SqlServer.Management.Smo.Server> object and to establish its connection to an instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="b6b9b-104">Vous pouvez créer une instance de l'objet <xref:Microsoft.SqlServer.Management.Smo.Server> et établir une connexion avec l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] de trois manières.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-104">You can create an instance of the <xref:Microsoft.SqlServer.Management.Smo.Server> object and establish a connection to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in three ways.</span></span> <span data-ttu-id="b6b9b-105">La première est d'utiliser une variable objet <xref:Microsoft.SqlServer.Management.Common.ServerConnection> pour fournir les informations de connexion.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-105">The first is using a <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object variable to provide the connection information.</span></span> <span data-ttu-id="b6b9b-106">La deuxième est de fournir les informations de connexion en définissant explicitement les propriétés de l'objet <xref:Microsoft.SqlServer.Management.Smo.Server>.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-106">The second is to provide the connection information by explicitly setting the <xref:Microsoft.SqlServer.Management.Smo.Server> object properties.</span></span> <span data-ttu-id="b6b9b-107">La troisième est de passer le nom de l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] dans le constructeur d'objet <xref:Microsoft.SqlServer.Management.Smo.Server>.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-107">The third is to pass the name of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance in the <xref:Microsoft.SqlServer.Management.Smo.Server> object constructor.</span></span>  
  
 <span data-ttu-id="b6b9b-108">**Utilisation d'un objet ServerConnection**</span><span class="sxs-lookup"><span data-stu-id="b6b9b-108">**Using a ServerConnection object**</span></span>  
  
 <span data-ttu-id="b6b9b-109">L'avantage de l'utilisation de la variable objet <xref:Microsoft.SqlServer.Management.Common.ServerConnection> est que vous pouvez réutiliser les informations de connexion.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-109">The advantage of using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object variable is that the connection information can be reused.</span></span> <span data-ttu-id="b6b9b-110">Déclarez une variable objet <xref:Microsoft.SqlServer.Management.Smo.Server>,</span><span class="sxs-lookup"><span data-stu-id="b6b9b-110">Declare a <xref:Microsoft.SqlServer.Management.Smo.Server> object variable.</span></span> <span data-ttu-id="b6b9b-111">puis un objet <xref:Microsoft.SqlServer.Management.Common.ServerConnection> et définissez les propriétés à l'aide des informations de connexion, telles que le nom de l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] et le mode d'authentification.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-111">Then, declare a <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object and set properties with connection information such as the name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], and the authentication mode.</span></span> <span data-ttu-id="b6b9b-112">Passez ensuite la variable objet <xref:Microsoft.SqlServer.Management.Common.ServerConnection> en tant que paramètre au constructeur d'objet <xref:Microsoft.SqlServer.Management.Smo.Server>.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-112">Then, pass the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object variable as a parameter to the <xref:Microsoft.SqlServer.Management.Smo.Server> object constructor.</span></span> <span data-ttu-id="b6b9b-113">Le partage simultané de connexions entre différents objets serveur n'est pas recommandé.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-113">It is not recommended to share connections between different server objects at the same time.</span></span> <span data-ttu-id="b6b9b-114">Utilisez la méthode <xref:Microsoft.SqlServer.Management.Common.ServerConnection.Copy%2A> pour vous procurer une copie des paramètres de connexion existants.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-114">Use the <xref:Microsoft.SqlServer.Management.Common.ServerConnection.Copy%2A> method to get a copy of the existing connection settings.</span></span>  
  
 <span data-ttu-id="b6b9b-115">**Définition explicite des propriétés d'objet serveur**</span><span class="sxs-lookup"><span data-stu-id="b6b9b-115">**Setting Server object properties explicitly**</span></span>  
  
 <span data-ttu-id="b6b9b-116">Vous pouvez également déclarer la variable objet <xref:Microsoft.SqlServer.Management.Smo.Server> et appeler le constructeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-116">Alternatively, you can declare the <xref:Microsoft.SqlServer.Management.Smo.Server> object variable and call the default constructor.</span></span> <span data-ttu-id="b6b9b-117">En l'état, l'objet <xref:Microsoft.SqlServer.Management.Smo.Server> tente de se connecter à l'instance par défaut de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] avec tous les paramètres de connexion par défaut.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-117">As is, the <xref:Microsoft.SqlServer.Management.Smo.Server> object tries to connect to the default instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] with all the default connection settings.</span></span>  
  
 <span data-ttu-id="b6b9b-118">**Insertion du nom de l'instance de SQL Server dans le constructeur d'objet serveur**</span><span class="sxs-lookup"><span data-stu-id="b6b9b-118">**Providing the SQL Server instance name in the Server object constructor**</span></span>  
  
 <span data-ttu-id="b6b9b-119">Déclarez la variable objet <xref:Microsoft.SqlServer.Management.Smo.Server> et passez le nom de l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] en tant que paramètre de chaîne dans le constructeur.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-119">Declare the <xref:Microsoft.SqlServer.Management.Smo.Server> object variable and pass the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance name as a string parameter in the constructor.</span></span> <span data-ttu-id="b6b9b-120">L'objet <xref:Microsoft.SqlServer.Management.Smo.Server> établit une connexion à l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] avec les paramètres de connexion par défaut.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-120">The <xref:Microsoft.SqlServer.Management.Smo.Server> object establishes a connection with the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] with the default connection settings.</span></span>  
  
## <a name="connection-pooling"></a><span data-ttu-id="b6b9b-121">Regroupement de connexions</span><span class="sxs-lookup"><span data-stu-id="b6b9b-121">Connection Pooling</span></span>  
 <span data-ttu-id="b6b9b-122">En règle générale, il n'est pas nécessaire d'appeler la méthode <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Connect%2A> de l'objet <xref:Microsoft.SqlServer.Management.Common.ServerConnection>.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-122">It is typically not required to call the <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Connect%2A> method of the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object.</span></span> <span data-ttu-id="b6b9b-123">SMO établit automatiquement une connexion lorsque cela est nécessaire et libère la connexion vers le groupement de connexions une fois les opérations terminées.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-123">SMO will automatically establish a connection when required, and release the connection to the connection pool after it has finished performing operations.</span></span> <span data-ttu-id="b6b9b-124">Lorsque vous appelez la méthode <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Connect%2A>, la connexion n'est pas libérée vers le groupement.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-124">When the <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Connect%2A> method is called, the connection is not released to the pool.</span></span> <span data-ttu-id="b6b9b-125">Un appel explicite à la méthode <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Disconnect%2A> est nécessaire pour libérer la connexion vers le groupement.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-125">An explicit call to the <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Disconnect%2A> method is required to release the connection to the pool.</span></span> <span data-ttu-id="b6b9b-126">Qui plus est, vous pouvez demander une connexion non regroupée en définissant la propriété <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.NonPooledConnection%2A> de l'objet <xref:Microsoft.SqlServer.Management.Common.ServerConnection>.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-126">Additionally, you can request a non-pooled connection by setting the <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.NonPooledConnection%2A> property of the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object.</span></span>  
  
## <a name="multithreaded-applications"></a><span data-ttu-id="b6b9b-127">Applications multithread</span><span class="sxs-lookup"><span data-stu-id="b6b9b-127">Multithreaded Applications</span></span>  
 <span data-ttu-id="b6b9b-128">Pour les applications multithread, un objet <xref:Microsoft.SqlServer.Management.Common.ServerConnection> distinct doit être utilisé dans chaque thread.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-128">For multithreaded applications, a separate <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object should be used in each thread.</span></span>  
  
## <a name="connecting-to-an-instance-of-sql-server-for-rmo"></a><span data-ttu-id="b6b9b-129">Connexion à une instance de SQL Server pour RMO</span><span class="sxs-lookup"><span data-stu-id="b6b9b-129">Connecting to an Instance of SQL Server for RMO</span></span>  
 <span data-ttu-id="b6b9b-130">RMO (Replication Management Objects) utilise une méthode légèrement différente de celle de SMO pour se connecter à un serveur de réplication.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-130">Replication Management Objects (RMO) uses a slightly different method from SMO to connect to a replication server.</span></span>  
  
 <span data-ttu-id="b6b9b-131">Pour les objets de programmation RMO, il est nécessaire qu'une connexion à une instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] soit établie au moyen de l'objet <xref:Microsoft.SqlServer.Management.Common.ServerConnection> implémenté par l'espace de noms `Microsoft.SqlServer.Management.Common`.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-131">RMO programming objects require that a connection to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is made by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object implemented by the `Microsoft.SqlServer.Management.Common` namespace.</span></span> <span data-ttu-id="b6b9b-132">Cette connexion au serveur est établie indépendamment d'un objet de programmation RMO.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-132">This connection to the server is made independently of an RMO programming object.</span></span> <span data-ttu-id="b6b9b-133">Elle est ensuite transmise à l'objet RMO lors de la création de l'instance ou par affectation à la propriété <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> de l'objet.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-133">It is then it is passed to the RMO object either during instance creation or by assignment to the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property of the object.</span></span> <span data-ttu-id="b6b9b-134">De cette manière, un objet de programmation RMO et les instances d'objet de connexion peuvent être créés et gérés séparément, et un objet de connexion peut être réutilisé avec plusieurs objets de programmation RMO.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-134">In this manner, an RMO programming object and the connection object instances can be created and managed separately, and a single connection object can be reused with multiple RMO programming objects.</span></span> <span data-ttu-id="b6b9b-135">Les règles suivantes s'appliquent aux connexions à un serveur de réplication :</span><span class="sxs-lookup"><span data-stu-id="b6b9b-135">The following rules apply for connections to a replication server:</span></span>  
  
-   <span data-ttu-id="b6b9b-136">Toutes les propriétés de la connexion sont définies pour un objet <xref:Microsoft.SqlServer.Management.Common.ServerConnection> défini.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-136">All properties for the connection are defined for a specified <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object.</span></span>  
  
-   <span data-ttu-id="b6b9b-137">Chaque connexion à une instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] doit posséder son propre objet <xref:Microsoft.SqlServer.Management.Common.ServerConnection>.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-137">Each connection to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] must have its own <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object.</span></span>  
  
-   <span data-ttu-id="b6b9b-138">Toutes les informations d'authentification nécessaires pour l'établissement de la connexion et l'ouverture d'une session sur le serveur sont fournies dans l'objet <xref:Microsoft.SqlServer.Management.Common.ServerConnection>.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-138">All authentication information to make the connection and successfully log on to the server is supplied in the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object.</span></span>  
  
-   <span data-ttu-id="b6b9b-139">Par défaut, les connexions sont établies au moyen de l'authentification Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-139">By default, connections are made by using Microsoft Windows Authentication.</span></span> <span data-ttu-id="b6b9b-140">Pour l'utilisation de l'authentification [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], la propriété <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.LoginSecure%2A> doit avoir la valeur False et <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.Login%2A> et <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.Password%2A> doivent être définis avec un nom d'ouverture de session et un mot de passe [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] valides.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-140">To use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication, <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.LoginSecure%2A> must be set to False and <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.Login%2A> and <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.Password%2A> must be set to a valid [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] logon and password.</span></span> <span data-ttu-id="b6b9b-141">Les informations d’identification de sécurité doivent toujours être stockées et gérées en toute sécurité, et fournies au moment de l’exécution dans la mesure du possible.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-141">Security credentials must always be stored and handled securely, and supplied at run time whenever possible.</span></span>  
  
-   <span data-ttu-id="b6b9b-142">La méthode <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Connect%2A> doit être appelée avant de passer la connexion à n'importe quel objet de programmation RMO.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-142">The <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Connect%2A> method must be called before passing the connection to any RMO programming object.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="b6b9b-143">Exemples</span><span class="sxs-lookup"><span data-stu-id="b6b9b-143">Examples</span></span>  
 [!INCLUDE[ssChooseProgEnv](../../../includes/sschooseprogenv-md.md)]  
  
## <a name="connecting-to-the-local-instance-of-sql-server-by-using-windows-authentication-in-visual-basic"></a><span data-ttu-id="b6b9b-144">Connexion à l'instance locale de SQL Server via l'authentification Windows en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b6b9b-144">Connecting to the Local Instance of SQL Server by Using Windows Authentication in Visual Basic</span></span>  
 <span data-ttu-id="b6b9b-145">La connexion à l'instance locale de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] n'exige pas beaucoup de code.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-145">Connecting to the local instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] does not require much code.</span></span> <span data-ttu-id="b6b9b-146">À la place, elle se base sur les paramètres par défaut pour la méthode d'authentification et le serveur.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-146">Instead, it relies on default settings for authentication method and server.</span></span> <span data-ttu-id="b6b9b-147">La première opération nécessitant la récupération des données entraîne la création d'une connexion.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-147">The first operation that requires data to be retrieved will cause a connection to be created.</span></span>  
  
 <span data-ttu-id="b6b9b-148">Cet exemple est un [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] code .net qui se connecte à l’instance locale de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] à l’aide de l’authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-148">This example is [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] .NET code that connects to the local instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using Windows Authentication.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VB1](SMO How to#SMO_VB1)]  -->  
  
## <a name="connecting-to-the-local-instance-of-sql-server-by-using-windows-authentication-in-visual-c"></a><span data-ttu-id="b6b9b-149">Connexion à l'instance locale de SQL Server via l'authentification Windows en Visual C#</span><span class="sxs-lookup"><span data-stu-id="b6b9b-149">Connecting to the Local Instance of SQL Server by Using Windows Authentication in Visual C#</span></span>  
 <span data-ttu-id="b6b9b-150">La connexion à l'instance locale de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] n'exige pas beaucoup de code.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-150">Connecting to the local instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] does not require much code.</span></span> <span data-ttu-id="b6b9b-151">À la place, elle se base sur les paramètres par défaut pour la méthode d'authentification et le serveur.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-151">Instead, it relies on default settings for authentication method and server.</span></span> <span data-ttu-id="b6b9b-152">La première opération nécessitant la récupération des données entraîne la création d'une connexion.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-152">The first operation that requires data to be retrieved will cause a connection to be created.</span></span>  
  
 <span data-ttu-id="b6b9b-153">Cet exemple de code Visual C# .NET permet de se connecter à l'instance locale de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] via l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-153">This example is Visual C# .NET code that connects to the local instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using Windows Authentication.</span></span>  
  
```  
{   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//The connection is established when a property is requested.   
Console.WriteLine(srv.Information.Version);   
}   
//The connection is automatically disconnected when the Server variable goes out of scope.  
```  
  
## <a name="connecting-to-a-remote-instance-of-sql-server-by-using-windows-authentication-in-visual-basic"></a><span data-ttu-id="b6b9b-154">Connexion à une instance distante de SQL Server via l'authentification Windows en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b6b9b-154">Connecting to a Remote Instance of SQL Server by Using Windows Authentication in Visual Basic</span></span>  
 <span data-ttu-id="b6b9b-155">Lorsque vous vous connectez à une instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] au moyen de l'authentification Windows, vous n'avez pas besoin de spécifier le type d'authentification.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-155">When you connect to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using Windows Authentication, you do not have to specify the authentication type.</span></span> <span data-ttu-id="b6b9b-156">La méthode par défaut est l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-156">Windows Authentication is the default.</span></span>  
  
 <span data-ttu-id="b6b9b-157">Cet exemple est un [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] code .net qui se connecte à l’instance distante de à [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] l’aide de l’authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-157">This example is [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] .NET code that connects to the remote instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using Windows Authentication.</span></span> <span data-ttu-id="b6b9b-158">La variable de chaîne *strServer* contient le nom de l’instance distante.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-158">The string variable *strServer* contains the name of the remote instance.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VB2](SMO How to#SMO_VB2)]  -->  
  
## <a name="connecting-to-a-remote-instance-of-sql-server-by-using-windows-authentication-in-visual-c"></a><span data-ttu-id="b6b9b-159">Connexion à une instance distante de SQL Server via l'authentification Windows en Visual C#</span><span class="sxs-lookup"><span data-stu-id="b6b9b-159">Connecting to a Remote Instance of SQL Server by Using Windows Authentication in Visual C#</span></span>  
 <span data-ttu-id="b6b9b-160">Lorsque vous vous connectez à une instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] au moyen de l'authentification Windows, vous n'avez pas besoin de spécifier le type d'authentification.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-160">When you connect to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using Windows Authentication, you do not have to specify the authentication type.</span></span> <span data-ttu-id="b6b9b-161">La méthode par défaut est l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-161">Windows Authentication is the default.</span></span>  
  
 <span data-ttu-id="b6b9b-162">Cet exemple de code Visual C# .NET permet de se connecter à l'instance distante de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] via l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-162">This example is Visual C# .NET code that connects to the remote instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using Windows Authentication.</span></span> <span data-ttu-id="b6b9b-163">La variable de chaîne *strServer* contient le nom de l’instance distante.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-163">The string variable *strServer* contains the name of the remote instance.</span></span>  
  
```  
{   
//Connect to a remote instance of SQL Server.   
Server srv;   
//The strServer string variable contains the name of a remote instance of SQL Server.   
srv = new Server(strServer);   
//The actual connection is made when a property is retrieved.   
Console.WriteLine(srv.Information.Version);   
}   
//The connection is automatically disconnected when the Server variable goes out of scope.  
```  
  
## <a name="connecting-to-an-instance-of-sql-server-by-using-sql-server-authentication-in-visual-basic"></a><span data-ttu-id="b6b9b-164">Connexion à une instance de SQL Server via l'authentification SQL Server en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b6b9b-164">Connecting to an Instance of SQL Server by Using SQL Server Authentication in Visual Basic</span></span>  
 <span data-ttu-id="b6b9b-165">Lorsque vous vous connectez à une instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] via l'authentification [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], vous devez préciser le type d'authentification.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-165">When you connect to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication, you must specify the authentication type.</span></span> <span data-ttu-id="b6b9b-166">Cet exemple montre l'autre méthode avec laquelle vous pouvez déclarer une variable objet <xref:Microsoft.SqlServer.Management.Common.ServerConnection> qui permet de réutiliser les informations de connexion.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-166">This example demonstrates the alternative method of declaring a <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object variable, which enables the connection information to be reused.</span></span>  
  
 <span data-ttu-id="b6b9b-167">L’exemple de [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] code .net montre comment se connecter à Remote et *vPassword* contiennent l’ouverture de session et le mot de passe.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-167">The example is [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] .NET code that demonstrates how to connect to the remote and *vPassword* contain the logon and password.</span></span>  
  
```  
' compile with:   
' /r:Microsoft.SqlServer.Smo.dll  
' /r:Microsoft.SqlServer.ConnectionInfo.dll  
' /r:Microsoft.SqlServer.Management.Sdk.Sfc.dll   
  
Imports Microsoft.SqlServer.Management.Smo  
Imports Microsoft.SqlServer.Management.Common  
  
Public Class A  
   Public Shared Sub Main()  
      Dim sqlServerLogin As [String] = "user_id"  
      Dim password As [String] = "pwd"  
      Dim instanceName As [String] = "instance_name"  
      Dim remoteSvrName As [String] = "remote_server_name"  
  
      ' Connecting to an instance of SQL Server using SQL Server Authentication  
      Dim srv1 As New Server()   ' connects to default instance  
      srv1.ConnectionContext.LoginSecure = False   ' set to true for Windows Authentication  
      srv1.ConnectionContext.Login = sqlServerLogin  
      srv1.ConnectionContext.Password = password  
      Console.WriteLine(srv1.Information.Version)   ' connection is established  
  
      ' Connecting to a named instance of SQL Server with SQL Server Authentication using ServerConnection  
      Dim srvConn As New ServerConnection()  
      srvConn.ServerInstance = ".\" & instanceName   ' connects to named instance  
      srvConn.LoginSecure = False   ' set to true for Windows Authentication  
      srvConn.Login = sqlServerLogin  
      srvConn.Password = password  
      Dim srv2 As New Server(srvConn)  
      Console.WriteLine(srv2.Information.Version)   ' connection is established  
  
      ' For remote connection, remote server name / ServerInstance needs to be specified  
      Dim srvConn2 As New ServerConnection(remoteSvrName)  
      srvConn2.LoginSecure = False  
      srvConn2.Login = sqlServerLogin  
      srvConn2.Password = password  
      Dim srv3 As New Server(srvConn2)  
      Console.WriteLine(srv3.Information.Version)   ' connection is established  
   End Sub  
End Class  
```  
  
## <a name="connecting-to-an-instance-of-sql-server-by-using-sql-server-authentication-in-visual-c"></a><span data-ttu-id="b6b9b-168">Connexion à une instance de SQL Server via l'authentification SQL Server en Visual C#</span><span class="sxs-lookup"><span data-stu-id="b6b9b-168">Connecting to an Instance of SQL Server by Using SQL Server Authentication in Visual C#</span></span>  
 <span data-ttu-id="b6b9b-169">Lorsque vous vous connectez à une instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] via l'authentification [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], vous devez préciser le type d'authentification.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-169">When you connect to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication, you must specify the authentication type.</span></span> <span data-ttu-id="b6b9b-170">Cet exemple montre l'autre méthode avec laquelle vous pouvez déclarer une variable objet <xref:Microsoft.SqlServer.Management.Common.ServerConnection> qui permet de réutiliser les informations de connexion.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-170">This example demonstrates the alternative method of declaring a <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object variable, which enables the connection information to be reused.</span></span>  
  
 <span data-ttu-id="b6b9b-171">L’exemple est le code Visual C# .NET qui montre comment se connecter à Remote et *vPassword* contiennent l’ouverture de session et le mot de passe.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-171">The example is Visual C# .NET code that demonstrates how to connect to the remote and *vPassword* contain the logon and password.</span></span>  
  
```  
// compile with:   
// /r:Microsoft.SqlServer.Smo.dll  
// /r:Microsoft.SqlServer.ConnectionInfo.dll  
// /r:Microsoft.SqlServer.Management.Sdk.Sfc.dll   
  
using System;  
using Microsoft.SqlServer.Management.Smo;  
using Microsoft.SqlServer.Management.Common;  
  
public class A {  
   public static void Main() {   
      String sqlServerLogin = "user_id";  
      String password = "pwd";  
      String instanceName = "instance_name";  
      String remoteSvrName = "remote_server_name";  
  
      // Connecting to an instance of SQL Server using SQL Server Authentication  
      Server srv1 = new Server();   // connects to default instance  
      srv1.ConnectionContext.LoginSecure = false;   // set to true for Windows Authentication  
      srv1.ConnectionContext.Login = sqlServerLogin;  
      srv1.ConnectionContext.Password = password;  
      Console.WriteLine(srv1.Information.Version);   // connection is established  
  
      // Connecting to a named instance of SQL Server with SQL Server Authentication using ServerConnection  
      ServerConnection srvConn = new ServerConnection();  
      srvConn.ServerInstance = @".\" + instanceName;   // connects to named instance  
      srvConn.LoginSecure = false;   // set to true for Windows Authentication  
      srvConn.Login = sqlServerLogin;  
      srvConn.Password = password;  
      Server srv2 = new Server(srvConn);  
      Console.WriteLine(srv2.Information.Version);   // connection is established  
  
      // For remote connection, remote server name / ServerInstance needs to be specified  
      ServerConnection srvConn2 = new ServerConnection(remoteSvrName);  
      srvConn2.LoginSecure = false;  
      srvConn2.Login = sqlServerLogin;  
      srvConn2.Password = password;  
      Server srv3 = new Server(srvConn2);  
      Console.WriteLine(srv3.Information.Version);   // connection is established  
   }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="b6b9b-172">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b6b9b-172">See Also</span></span>  
 <xref:Microsoft.SqlServer.Management.Smo.Server>   
 <xref:Microsoft.SqlServer.Management.Common.ServerConnection>  
  
  
