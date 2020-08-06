---
title: Service Report Server Windows (MSSQLServer) 107 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- MSSQLServer 107 error
ms.assetid: 52b5704b-27f9-400a-a821-d8fa0786afe4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 8651f98b47b698fbe3cfb6a152b9220a84ed7256
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604383"
---
# <a name="report-server-windows-service-mssqlserver-107"></a><span data-ttu-id="b00e1-102">Service Report Server Windows (MSSQLServer) 107</span><span class="sxs-lookup"><span data-stu-id="b00e1-102">Report Server Windows Service (MSSQLServer) 107</span></span>
    
## <a name="details"></a><span data-ttu-id="b00e1-103">Détails</span><span class="sxs-lookup"><span data-stu-id="b00e1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b00e1-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="b00e1-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="b00e1-105">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="b00e1-105">Event ID</span></span>|<span data-ttu-id="b00e1-106">107</span><span class="sxs-lookup"><span data-stu-id="b00e1-106">107</span></span>|  
|<span data-ttu-id="b00e1-107">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="b00e1-107">Event Source</span></span>|<span data-ttu-id="b00e1-108">Report Server Windows Service</span><span class="sxs-lookup"><span data-stu-id="b00e1-108">Report Server Windows Service</span></span>|  
|<span data-ttu-id="b00e1-109">Composant</span><span class="sxs-lookup"><span data-stu-id="b00e1-109">Component</span></span>|[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]|  
|<span data-ttu-id="b00e1-110">Texte du message</span><span class="sxs-lookup"><span data-stu-id="b00e1-110">Message Text</span></span>|<span data-ttu-id="b00e1-111">Le service Report Server Windows (MSSQLSERVER) ne peut pas se connecter à la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="b00e1-111">Report Server Windows Service (MSSQLSERVER) cannot connect to the report server database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b00e1-112">Explication</span><span class="sxs-lookup"><span data-stu-id="b00e1-112">Explanation</span></span>  
 <span data-ttu-id="b00e1-113">Le service Report Server [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ne peut pas se connecter à la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="b00e1-113">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Report Server service cannot connect to the report server database.</span></span> <span data-ttu-id="b00e1-114">Cette erreur se produit au cours du redémarrage d'un service si une connexion à la base de données du serveur de rapports ne peut pas être établie.</span><span class="sxs-lookup"><span data-stu-id="b00e1-114">This error occurs during a service restart if a connection to the report server database cannot be established.</span></span> <span data-ttu-id="b00e1-115">Les conditions dans lesquelles cette erreur se produit incluent :</span><span class="sxs-lookup"><span data-stu-id="b00e1-115">Conditions under which this error occurs include the following:</span></span>  
  
-   <span data-ttu-id="b00e1-116">Le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] n’est pas en cours d’exécution lorsque le service Serveur de rapports démarre.</span><span class="sxs-lookup"><span data-stu-id="b00e1-116">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] service is not running when the Report Server service starts.</span></span>  
  
-   <span data-ttu-id="b00e1-117">La connexion au service du [!INCLUDE[ssDE](../../includes/ssde-md.md)] échoue, car les connexions distantes ou le protocole TCP/IP ne sont pas activés.</span><span class="sxs-lookup"><span data-stu-id="b00e1-117">The connection to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] service fails because remote connections or the TCP/IP protocol is not enabled.</span></span>  
  
-   <span data-ttu-id="b00e1-118">La base de données du serveur de rapports n'est pas configurée correctement.</span><span class="sxs-lookup"><span data-stu-id="b00e1-118">The report server database is not configured correctly.</span></span>  
  
-   <span data-ttu-id="b00e1-119">Le compte de service n'est pas configuré correctement ou le compte n'a plus d'autorisations sur la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="b00e1-119">The service account is not configured correctly, or the account no longer has permissions on the report server database.</span></span> <span data-ttu-id="b00e1-120">Cela peut se produire si vous n'utilisez pas l'outil de configuration de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] pour configurer le compte ou la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="b00e1-120">This can occur if you do not use the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool to set up the account or the report server database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b00e1-121">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="b00e1-121">User Action</span></span>  
 <span data-ttu-id="b00e1-122">Démarrez le service du [!INCLUDE[ssDE](../../includes/ssde-md.md)] s'il ne s'exécute pas et vérifiez que les connexions distantes sont activées pour le protocole TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="b00e1-122">Start the [!INCLUDE[ssDE](../../includes/ssde-md.md)] service if it is not running and check that remote connections are enabled for TCP/IP protocol.</span></span>  
  
 <span data-ttu-id="b00e1-123">Utilisez l’outil de configuration de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] pour configurer la base de données du serveur de rapports et le compte de service.</span><span class="sxs-lookup"><span data-stu-id="b00e1-123">Use the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool to configure the report server database and service account.</span></span>  
  
## <a name="internal-only"></a><span data-ttu-id="b00e1-124">Interne uniquement</span><span class="sxs-lookup"><span data-stu-id="b00e1-124">Internal-Only</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b00e1-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b00e1-125">See Also</span></span>  
 <span data-ttu-id="b00e1-126">[Configurer le compte de service Report Server &#40;Gestionnaire de configuration de SSRS&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="b00e1-126">[Configure the Report Server Service Account &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="b00e1-127">[Gestionnaire de configuration de Reporting Services &#40;mode natif&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="b00e1-127">[Reporting Services Configuration Manager &#40;Native Mode&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) </span></span>  
 [<span data-ttu-id="b00e1-128">Démarrer et arrêter le service du serveur de rapports</span><span class="sxs-lookup"><span data-stu-id="b00e1-128">Start and Stop the Report Server Service</span></span>](../report-server/start-and-stop-the-report-server-service.md)  
  
  
