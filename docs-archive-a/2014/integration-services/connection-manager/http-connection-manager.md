---
title: Gestionnaire de connexions HTTP | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- HTTP connection manager
- Web site connections [Integration Services]
- connection managers [Integration Services], HTTP
- Web server connections [Integration Services]
- connections [Integration Services], HTTP
ms.assetid: 26b2b3e1-d02c-46ca-8d31-7aef2bbc3c53
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 10c9f0778faa25aff8db4ad54ecaa8d3ccc5b359
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707708"
---
# <a name="http-connection-manager"></a><span data-ttu-id="8a638-102">Gestionnaire de connexions HTTP</span><span class="sxs-lookup"><span data-stu-id="8a638-102">HTTP Connection Manager</span></span>
  <span data-ttu-id="8a638-103">Une connexion HTTP permet à un package d'accéder à un serveur Web via HTTP pour l'envoi et la réception de fichiers.</span><span class="sxs-lookup"><span data-stu-id="8a638-103">An HTTP connection enables a package to access a Web server by using HTTP to send or receive files.</span></span> <span data-ttu-id="8a638-104">La tâche de service web incluse dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] utilise ce gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="8a638-104">The Web Service task that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] includes uses this connection manager.</span></span>  
  
 <span data-ttu-id="8a638-105">Lorsque vous ajoutez un gestionnaire de connexions HTTP à un package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] crée un gestionnaire de connexions qui sera converti en connexion HTTP au moment de l'exécution, définit les propriétés du gestionnaire de connexions et ajoute le gestionnaire de connexions à la collection `Connections` du package.</span><span class="sxs-lookup"><span data-stu-id="8a638-105">When you add an HTTP connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to an HTTP connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span>  
  
 <span data-ttu-id="8a638-106">La propriété `ConnectionManagerType` du gestionnaire de connexions a pour valeur `HTTP.`</span><span class="sxs-lookup"><span data-stu-id="8a638-106">The `ConnectionManagerType` property of the connection manager is set to `HTTP.`</span></span>  
  
 <span data-ttu-id="8a638-107">Vous pouvez configurer le gestionnaire de connexions HTTP de plusieurs manières :</span><span class="sxs-lookup"><span data-stu-id="8a638-107">You can configure the HTTP connection manager the following ways:</span></span>  
  
-   <span data-ttu-id="8a638-108">Utilisez des informations d'identification.</span><span class="sxs-lookup"><span data-stu-id="8a638-108">Use credentials.</span></span> <span data-ttu-id="8a638-109">Si le gestionnaire de connexions utilise des informations d'identification, ses propriétés incluent le nom d'utilisateur, le mot de passe et le domaine.</span><span class="sxs-lookup"><span data-stu-id="8a638-109">If the connection manager uses credentials, its properties include the user name, password, and domain.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="8a638-110">Le gestionnaire de connexions HTTP prend en charge uniquement l'authentification anonyme et l'authentification de base.</span><span class="sxs-lookup"><span data-stu-id="8a638-110">The HTTP connection manager supports only anonymous authentication and basic authentication.</span></span> <span data-ttu-id="8a638-111">Il ne prend pas en charge l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="8a638-111">It does not support Windows Authentication.</span></span>  
  
-   <span data-ttu-id="8a638-112">Utilisez un certificat client.</span><span class="sxs-lookup"><span data-stu-id="8a638-112">Use a client certificate.</span></span> <span data-ttu-id="8a638-113">Si le gestionnaire de connexions utilise un certificat client, ses propriétés incluent le nom du certificat.</span><span class="sxs-lookup"><span data-stu-id="8a638-113">If the connection manager uses a client certificate, its properties include the certificate name.</span></span>  
  
-   <span data-ttu-id="8a638-114">Indiquez un délai de connexion au serveur et une taille de segment pour l'écriture de données.</span><span class="sxs-lookup"><span data-stu-id="8a638-114">Provide a time-out for connecting to the server and a chunk size for writing data.</span></span>  
  
-   <span data-ttu-id="8a638-115">Utilisez un serveur proxy.</span><span class="sxs-lookup"><span data-stu-id="8a638-115">Use a proxy server.</span></span> <span data-ttu-id="8a638-116">Le serveur Proxy peut également être configuré pour utiliser les informations d'identification et pour ignorer le serveur proxy et utiliser à la place des adresses locales.</span><span class="sxs-lookup"><span data-stu-id="8a638-116">The proxy server can also be configured to use credentials and to bypass the proxy server and use local addresses instead.</span></span>  
  
## <a name="configuration-of-the-http-connection-manager"></a><span data-ttu-id="8a638-117">Configuration du gestionnaire de connexions HTTP</span><span class="sxs-lookup"><span data-stu-id="8a638-117">Configuration of the HTTP Connection Manager</span></span>  
 <span data-ttu-id="8a638-118">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou par programmation.</span><span class="sxs-lookup"><span data-stu-id="8a638-118">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="8a638-119">Pour plus d'informations sur les propriétés définissables dans le concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] , cliquez sur l'une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="8a638-119">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="8a638-120">Éditeur du gestionnaire de connexions HTTP &#40;page Serveur&#41;</span><span class="sxs-lookup"><span data-stu-id="8a638-120">HTTP Connection Manager Editor &#40;Server Page&#41;</span></span>](../http-connection-manager-editor-server-page.md)  
  
-   [<span data-ttu-id="8a638-121">Éditeur du gestionnaire de connexions HTTP &#40;page Proxy&#41;</span><span class="sxs-lookup"><span data-stu-id="8a638-121">HTTP Connection Manager Editor &#40;Proxy Page&#41;</span></span>](../http-connection-manager-editor-proxy-page.md)  
  
 <span data-ttu-id="8a638-122">Pour plus d’informations sur la configuration d’un gestionnaire de connexions par programmation, consultez <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>.</span><span class="sxs-lookup"><span data-stu-id="8a638-122">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a638-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8a638-123">See Also</span></span>  
 <span data-ttu-id="8a638-124">[Tâche de service Web](../control-flow/web-service-task.md) </span><span class="sxs-lookup"><span data-stu-id="8a638-124">[Web Service Task](../control-flow/web-service-task.md) </span></span>  
 [<span data-ttu-id="8a638-125">Connexions Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="8a638-125">Integration Services &#40;SSIS&#41; Connections</span></span>](integration-services-ssis-connections.md)  
  
  
