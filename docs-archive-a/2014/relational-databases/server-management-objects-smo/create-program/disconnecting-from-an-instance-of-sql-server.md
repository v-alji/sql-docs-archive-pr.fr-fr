---
title: Déconnexion d’une instance de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- SQL Server Management Objects, disconnecting
- SMO [SQL Server], disconnecting
- instances of SQL Server, disconnecting
- disconnecting [SMO]
ms.assetid: 4ca7f7eb-6b3f-4c73-ac63-88afa8570b61
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3514fce8fb8f1ccc8bd1b54acfa27825eaebbd34
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613950"
---
# <a name="disconnecting-from-an-instance-of-sql-server"></a><span data-ttu-id="06c75-102">Déconnexion d'une instance de SQL Server</span><span class="sxs-lookup"><span data-stu-id="06c75-102">Disconnecting from an Instance of SQL Server</span></span>
  <span data-ttu-id="06c75-103">Il n'est pas nécessaire de fermer et de déconnecter manuellement des objets SMO ( [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Management Objects).</span><span class="sxs-lookup"><span data-stu-id="06c75-103">Manually closing and disconnecting [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Management Objects (SMO) objects is not required.</span></span> <span data-ttu-id="06c75-104">Les connexions sont ouvertes et fermées en fonction des besoins.</span><span class="sxs-lookup"><span data-stu-id="06c75-104">Connections are opened and closed as required.</span></span>  
  
## <a name="connection-pooling"></a><span data-ttu-id="06c75-105">Regroupement de connexions</span><span class="sxs-lookup"><span data-stu-id="06c75-105">Connection Pooling</span></span>  
 <span data-ttu-id="06c75-106">Lorsque la méthode <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Connect%2A> est appelée, la connexion n'est pas automatiquement libérée.</span><span class="sxs-lookup"><span data-stu-id="06c75-106">When the <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Connect%2A> method is called, the connection is not automatically released.</span></span> <span data-ttu-id="06c75-107">La méthode <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Disconnect%2A> doit être appelée explicitement pour libérer la connexion au pool de connexions.</span><span class="sxs-lookup"><span data-stu-id="06c75-107">The <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Disconnect%2A> method must be called explicitly to release the connection to the connection pool.</span></span> <span data-ttu-id="06c75-108">Vous pouvez également demander une connexion non regroupée.</span><span class="sxs-lookup"><span data-stu-id="06c75-108">Also, you can request a non-pooled connection.</span></span> <span data-ttu-id="06c75-109">Pour ce faire, vous définissez la propriété <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.NonPooledConnection%2A> de la propriété <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A> qui fait référence à l'objet <xref:Microsoft.SqlServer.Management.Common.ServerConnection>.</span><span class="sxs-lookup"><span data-stu-id="06c75-109">You do this by setting the <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.NonPooledConnection%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A> property that references the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object.</span></span>  
  
## <a name="disconnecting-from-an-instance-of-sql-server-for-rmo"></a><span data-ttu-id="06c75-110">Déconnexion d'une instance de SQL Server pour des objets RMO</span><span class="sxs-lookup"><span data-stu-id="06c75-110">Disconnecting from an Instance of SQL Server for RMO</span></span>  
 <span data-ttu-id="06c75-111">La fermeture des connexions au serveur lorsque vous programmez avec des objets RMO est légèrement différente de la procédure utilisée avec des objets SMO.</span><span class="sxs-lookup"><span data-stu-id="06c75-111">Closing server connections when you are programming with RMO works slightly different from SMO.</span></span>  
  
 <span data-ttu-id="06c75-112">Étant donné que la connexion au serveur pour un objet RMO est conservée par l' <xref:Microsoft.SqlServer.Management.Common.ServerConnection> objet, cet objet est également utilisé lors de la déconnexion d’une instance de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] lorsque vous programmez à l’aide de RMO.</span><span class="sxs-lookup"><span data-stu-id="06c75-112">Because the server connection for an RMO object is maintained by the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object, this object is also used when disconnecting from an instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] when you program by using RMO.</span></span> <span data-ttu-id="06c75-113">Pour fermer une connexion à l'aide de l'objet <xref:Microsoft.SqlServer.Management.Common.ServerConnection>, appelez la méthode <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Disconnect%2A> de l'objet RMO.</span><span class="sxs-lookup"><span data-stu-id="06c75-113">To close a connection by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object, call the <xref:Microsoft.SqlServer.Management.Common.ConnectionManager.Disconnect%2A> method of the RMO object.</span></span> <span data-ttu-id="06c75-114">Une fois la connexion fermée, les objets RMO ne peuvent pas être utilisés.</span><span class="sxs-lookup"><span data-stu-id="06c75-114">After the connection has been closed, RMO objects cannot be used.</span></span>  
  
## <a name="example"></a><span data-ttu-id="06c75-115">Exemple</span><span class="sxs-lookup"><span data-stu-id="06c75-115">Example</span></span>  
 [!INCLUDE[ssChooseProgEnv](../../../includes/sschooseprogenv-md.md)]  
  
## <a name="closing-and-disconnecting-an-smo-object-in-visual-basic"></a><span data-ttu-id="06c75-116">Fermeture et déconnexion d'un objet SMO en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="06c75-116">Closing and Disconnecting an SMO Object in Visual Basic</span></span>  
 <span data-ttu-id="06c75-117">Cet exemple de code indique comment demander une connexion non regroupée en définissant la propriété <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.NonPooledConnection%2A> de la propriété de l'objet <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A>.</span><span class="sxs-lookup"><span data-stu-id="06c75-117">This code example shows how to request a non-pooled connection by setting the <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.NonPooledConnection%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A> object property.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VB4](SMO How to#SMO_VB4)]  -->  
  
## <a name="closing-and-disconnecting-an-smo-object-in-visual-c"></a><span data-ttu-id="06c75-118">Fermeture et déconnexion d'un objet SMO en Visual C#</span><span class="sxs-lookup"><span data-stu-id="06c75-118">Closing and Disconnecting an SMO Object in Visual C#</span></span>  
 <span data-ttu-id="06c75-119">Cet exemple de code indique comment demander une connexion non regroupée en définissant la propriété <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.NonPooledConnection%2A> de la propriété de l'objet <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A>.</span><span class="sxs-lookup"><span data-stu-id="06c75-119">This code example shows how to request a non-pooled connection by setting the <xref:Microsoft.SqlServer.Management.Common.ConnectionSettings.NonPooledConnection%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A> object property.</span></span>  
  
```  
{   
Server srv;   
srv = new Server();   
//Disable automatic disconnection.   
srv.ConnectionContext.AutoDisconnectMode = AutoDisconnectMode.NoAutoDisconnect;   
//Connect to the local, default instance of SQL Server.   
srv.ConnectionContext.Connect();   
//The actual connection is made when a property is retrieved.   
Console.WriteLine(srv.Information.Version);   
//Disconnect explicitly.   
srv.ConnectionContext.Disconnect();  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="06c75-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="06c75-120">See Also</span></span>  
 <xref:Microsoft.SqlServer.Management.Smo.Server>   
 <xref:Microsoft.SqlServer.Management.Common.ServerConnection>  
  
  
