---
title: Empêcher le démarrage automatique d’une instance de SQL Server (Gestionnaire de configuration SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- automatic SQL Server startup
- SQL Server, stopping
- SQL Server, automatic startup
- canceling automatic startup
- stopping SQL Server
- preventing automatic startups [SQL Server]
ms.assetid: 782663cf-f3d7-4cc6-b621-21e4550f0322
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8f93f5abc749f589ab4208b3a4c9434ca63b8769
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610854"
---
# <a name="prevent-automatic-startup-of-an-instance-of-sql-server-sql-server-configuration-manager"></a><span data-ttu-id="335b6-102">Empêcher le démarrage automatique d'une instance de SQL Server (Gestionnaire de configuration SQL Server)</span><span class="sxs-lookup"><span data-stu-id="335b6-102">Prevent Automatic Startup of an Instance of SQL Server (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="335b6-103">Cette rubrique décrit comment empêcher une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de démarrer automatiquement dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide du Gestionnaire de configuration SQL Server.</span><span class="sxs-lookup"><span data-stu-id="335b6-103">This topic describes how prevent an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from starting automatically in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using SQL Server Configuration Manager.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="335b6-104">est en principe configuré afin de démarrer automatiquement.</span><span class="sxs-lookup"><span data-stu-id="335b6-104">is normally configured to start automatically.</span></span> <span data-ttu-id="335b6-105">Vous pouvez modifier ce comportement en définissant le mode de démarrage de l'instance sur Manuel.</span><span class="sxs-lookup"><span data-stu-id="335b6-105">You can change that by setting the start mode for the instance to manual.</span></span>  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="335b6-106">Utilisation du Gestionnaire de configuration SQL Server</span><span class="sxs-lookup"><span data-stu-id="335b6-106">Using SQL Server Configuration Manager</span></span>  
  
#### <a name="to-prevent-automatic-startup-of-an-instance-of-sql-server"></a><span data-ttu-id="335b6-107">Pour empêcher le démarrage automatique d'une instance de SQL Server</span><span class="sxs-lookup"><span data-stu-id="335b6-107">To prevent automatic startup of an instance of SQL Server</span></span>  
  
1.  <span data-ttu-id="335b6-108">Dans le menu **Démarrer** , pointez sur **Tous les programmes**, sur [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)]et sur **Outils de configuration**, puis cliquez sur **Gestionnaire de configuration SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="335b6-108">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="335b6-109">Dans le Gestionnaire de configuration SQL Server, développez **Services**, puis cliquez sur **SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="335b6-109">In SQL Server Configuration Manager, expand **Services**, and then click **SQL Server**.</span></span>  
  
3.  <span data-ttu-id="335b6-110">Dans le volet d’informations, cliquez avec le bouton droit sur **MSSQLServer**, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="335b6-110">In the details pane, right-click **MSSQLServer**, and then click **Properties.**</span></span>  
  
4.  <span data-ttu-id="335b6-111">Dans la boîte de dialogue \*\* \<**_instancename_**> propriétés du SQL Server\*\* , dans la zone **Propriétés** , définissez la valeur du **mode de démarrage** sur **Manuel**.</span><span class="sxs-lookup"><span data-stu-id="335b6-111">In the **SQL Server \<**_instancename_**> Properties** dialog box, in the **Properties** box, set the value of **Start Mode** to **Manual**.</span></span>  
  
5.  <span data-ttu-id="335b6-112">Cliquez sur **OK** pour fermer la boîte de dialogue **Propriétés de SQL Server \<**_instancename_**>** , puis fermez le Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="335b6-112">Click **OK** to close the **SQL Server \<**_instancename_**> Properties** dialog box, and then close [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="335b6-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="335b6-113">See Also</span></span>  
 [<span data-ttu-id="335b6-114">Démarrer, arrêter, suspendre, reprendre, redémarrer le moteur de base de données, SQL Server Agent ou le service SQL Server Browser</span><span class="sxs-lookup"><span data-stu-id="335b6-114">Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service</span></span>](start-stop-pause-resume-restart-sql-server-services.md)  
  
  
