---
title: Démarrage de SQL Server avec une configuration minimale | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- minimal configuration [SQL Server]
- starting SQL Server, minimal configuration
ms.assetid: 4d733c99-28b3-42d8-b7f6-7b943b548173
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5c78fc10be584803b438b2cd125a77400ff369b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601082"
---
# <a name="start-sql-server-with-minimal-configuration"></a><span data-ttu-id="2be69-102">Démarrage de SQL Server avec une configuration minimale</span><span class="sxs-lookup"><span data-stu-id="2be69-102">Start SQL Server with Minimal Configuration</span></span>
  <span data-ttu-id="2be69-103">Si vous rencontrez des problèmes de configuration qui empêchent le démarrage du serveur, vous pouvez démarrer une instance de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à l’aide de l’option de démarrage en configuration minimale.</span><span class="sxs-lookup"><span data-stu-id="2be69-103">If you have configuration problems that prevent the server from starting, you can start an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using the minimal configuration startup option.</span></span> <span data-ttu-id="2be69-104">Il s’agit de l’option de démarrage **-f**.</span><span class="sxs-lookup"><span data-stu-id="2be69-104">This is the startup option **-f**.</span></span> <span data-ttu-id="2be69-105">Le démarrage d'une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] SQL Server avec une configuration minimale fait automatiquement passer le serveur en mode mono-utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2be69-105">Starting an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with minimal configuration automatically puts the server in single-user mode.</span></span>  
  
 <span data-ttu-id="2be69-106">Lorsque vous démarrez une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en mode configuration minimale, notez les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="2be69-106">When you start an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in minimal configuration mode, note the following:</span></span>  
  
-   <span data-ttu-id="2be69-107">un seul utilisateur peut se connecter, tandis que le processus CHECKPOINT n'est pas exécuté ;</span><span class="sxs-lookup"><span data-stu-id="2be69-107">Only a single user can connect, and the CHECKPOINT process is not executed.</span></span>  
  
-   <span data-ttu-id="2be69-108">L'accès à distance et la lecture anticipée sont désactivés.</span><span class="sxs-lookup"><span data-stu-id="2be69-108">Remote access and read-ahead are disabled.</span></span>  
  
-   <span data-ttu-id="2be69-109">Les procédures stockées de démarrage ne sont pas exécutées.</span><span class="sxs-lookup"><span data-stu-id="2be69-109">Startup stored procedures do not run.</span></span>  
  
 <span data-ttu-id="2be69-110">N'oubliez pas ensuite de revenir à l'option de démarrage appropriée, d'arrêter le serveur, puis de le redémarrer.</span><span class="sxs-lookup"><span data-stu-id="2be69-110">After the server has been started with minimal configuration, you should change the appropriate server option value or values, stop, and then restart the server.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2be69-111">Utilisez l’utilitaire **sqlcmd** et la connexion administrateur dédiée (DAC) pour vous connecter à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2be69-111">Use the **sqlcmd** utility and the dedicated administrator connection (DAC) to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="2be69-112">Si vous utilisez une connexion par défaut, arrêtez le service SQL Server Agent avant de vous connecter à une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en mode de configuration minimale.</span><span class="sxs-lookup"><span data-stu-id="2be69-112">If you use a typical connection, stop the SQL Server Agent service before connecting to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in minimal configuration mode.</span></span> <span data-ttu-id="2be69-113">Sinon, le service SQL Server Agent utilise la connexion et bloque votre connexion à SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2be69-113">Otherwise, the SQL Server Agent service uses the connection, thereby blocking it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2be69-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2be69-114">See Also</span></span>  
 <span data-ttu-id="2be69-115">[Démarrer, arrêter ou suspendre le service SQL Server Agent](../../ssms/agent/start-stop-or-pause-the-sql-server-agent-service.md) </span><span class="sxs-lookup"><span data-stu-id="2be69-115">[Start, Stop, or Pause the SQL Server Agent Service](../../ssms/agent/start-stop-or-pause-the-sql-server-agent-service.md) </span></span>  
 <span data-ttu-id="2be69-116">[Connexion de diagnostic pour les administrateurs de base de données](diagnostic-connection-for-database-administrators.md) </span><span class="sxs-lookup"><span data-stu-id="2be69-116">[Diagnostic Connection for Database Administrators](diagnostic-connection-for-database-administrators.md) </span></span>  
 <span data-ttu-id="2be69-117">[Utilitaire sqlcmd](../../tools/sqlcmd-utility.md) </span><span class="sxs-lookup"><span data-stu-id="2be69-117">[sqlcmd Utility](../../tools/sqlcmd-utility.md) </span></span>  
 <span data-ttu-id="2be69-118">[Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2be69-118">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="2be69-119">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2be69-119">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="2be69-120">Options de démarrage du service moteur de base de données</span><span class="sxs-lookup"><span data-stu-id="2be69-120">Database Engine Service Startup Options</span></span>](database-engine-service-startup-options.md)  
  
  
