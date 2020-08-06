---
title: Programme externe de la messagerie de base de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- external programs [Database Mail]
- DatabaseMail90.exe
- Database Mail [SQL Server], external programs
ms.assetid: bc124164-eb6e-4b7f-bf66-98a3113d02f7
author: stevestein
ms.author: sstein
ms.openlocfilehash: 698fc8d97a565b4181552691a0260486c9c43bfd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709628"
---
# <a name="database-mail-external-program"></a><span data-ttu-id="833fb-102">Programme externe de la messagerie de base de données</span><span class="sxs-lookup"><span data-stu-id="833fb-102">Database Mail External Program</span></span>
  <span data-ttu-id="833fb-103">L’exécutable externe de la messagerie de base de données est **DatabaseMail.exe**, situé dans le **répertoire MSSQL\Binn** de l’installation [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="833fb-103">The Database Mail external executable is **DatabaseMail.exe**, located in the **MSSQL\Binn directory** of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation.</span></span> <span data-ttu-id="833fb-104">La messagerie de base de données utilise l'activation Service Broker pour démarrer le programme externe lorsque des messages électroniques doivent être traités.</span><span class="sxs-lookup"><span data-stu-id="833fb-104">Database Mail uses Service Broker activation to start the external program when there are e-mail messages to be processed.</span></span> <span data-ttu-id="833fb-105">La messagerie de base de données démarre une instance du programme externe.</span><span class="sxs-lookup"><span data-stu-id="833fb-105">Database Mail starts one instance of the external program.</span></span> <span data-ttu-id="833fb-106">Le programme externe s'exécute dans le contexte de sécurité du compte de services pour [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="833fb-106">The external program runs in the security context of the service account for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="833fb-107">**Dans cette rubrique :**</span><span class="sxs-lookup"><span data-stu-id="833fb-107">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="833fb-108">Concepts du programme externe de la messagerie de base de données</span><span class="sxs-lookup"><span data-stu-id="833fb-108">Database Mail External Program Concepts</span></span>](#ComponentsAndConcepts)  
  
-   [<span data-ttu-id="833fb-109">Tâches liées à la configuration du programme externe de messagerie de base de données</span><span class="sxs-lookup"><span data-stu-id="833fb-109">Tasks Related to Configuring Database Mail External Program</span></span>](#RelatedTasks)  
  
##  <a name="database-mail-external-program-concepts"></a><a name="ComponentsAndConcepts"></a> <span data-ttu-id="833fb-110">Concepts du programme externe de la messagerie de base de données</span><span class="sxs-lookup"><span data-stu-id="833fb-110">Database Mail External Program Concepts</span></span>  
 <span data-ttu-id="833fb-111">Lorsque le programme externe démarre, il se connecte à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à l'aide de l'authentification Windows et débute le traitement des messages électroniques.</span><span class="sxs-lookup"><span data-stu-id="833fb-111">When the external program starts, the program connects to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using Windows Authentication and begins processing e-mail messages.</span></span> <span data-ttu-id="833fb-112">S'il n'y a eu aucun message à envoyer pendant le délai d'attente spécifié, le programme est fermé.</span><span class="sxs-lookup"><span data-stu-id="833fb-112">When there have been no messages to send for the specified time-out period, the program exits.</span></span> <span data-ttu-id="833fb-113">Vous pouvez configurer la durée du délai d'attente du programme avant qu'il ne soit fermé en utilisant soit l'Assistant Configuration de la messagerie de base de données, soit les procédures stockées de la messagerie de base de données.</span><span class="sxs-lookup"><span data-stu-id="833fb-113">You can configure the amount of time that the program waits before exiting by using either Database Mail Configuration Wizard or the Database Mail stored procedures.</span></span> <span data-ttu-id="833fb-114">Pour plus d’informations, consultez [sysmail_configure_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-configure-sp-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="833fb-114">For more information, see [sysmail_configure_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-configure-sp-transact-sql).</span></span>  
  
 <span data-ttu-id="833fb-115">Le programme externe stocke les informations dans les tables système de la base de données **msdb** .</span><span class="sxs-lookup"><span data-stu-id="833fb-115">The external program stores information in system tables in the **msdb** database.</span></span> <span data-ttu-id="833fb-116">Si le programme externe ne peut pas communiquer avec [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], il consigne des erreurs dans le journal des événements des applications Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="833fb-116">If the external program cannot communicate with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the program logs errors to the Microsoft Windows application event log.</span></span> <span data-ttu-id="833fb-117">Une journalisation supplémentaire des messages est assurée si vous définissez le niveau de journalisation à **Commentaires** dans la boîte de dialogue **Configurer les paramètres du système** de l' **Assistant Configuration de la messagerie de base de données**.</span><span class="sxs-lookup"><span data-stu-id="833fb-117">Additional message logging is provided when the logging level is set to **Verbose** in the **Configure System Parameters** dialog box of the **Database Mail Configuration Wizard**.</span></span>  
  
 <span data-ttu-id="833fb-118">Notez que, pour des raisons d'efficacité, le programme externe met en cache les informations de compte et de profil.</span><span class="sxs-lookup"><span data-stu-id="833fb-118">Notice that, for efficiency, the external program caches account and profile information.</span></span> <span data-ttu-id="833fb-119">Les changements de configuration des comptes et profils peuvent donc ne pas être pris en compte dans le programme externe avant quelques minutes.</span><span class="sxs-lookup"><span data-stu-id="833fb-119">Therefore, configuration changes to accounts and profiles may not be reflected in the external program for a few minutes.</span></span>  
  
##  <a name="tasks-related-to-configuring-database-mail-external-program"></a><a name="RelatedTasks"></a> <span data-ttu-id="833fb-120">Tâches liées à la configuration du programme externe de messagerie de base de données</span><span class="sxs-lookup"><span data-stu-id="833fb-120">Tasks Related to Configuring Database Mail External Program</span></span>  
  
|<span data-ttu-id="833fb-121">Tâche de configuration</span><span class="sxs-lookup"><span data-stu-id="833fb-121">Configuration Task</span></span>|<span data-ttu-id="833fb-122">Lien de rubrique</span><span class="sxs-lookup"><span data-stu-id="833fb-122">Topic Link</span></span>|  
|------------------------|----------------|  
|<span data-ttu-id="833fb-123">Spécifiez l'heure à laquelle le programme externe s'arrête.</span><span class="sxs-lookup"><span data-stu-id="833fb-123">Specify the time that the External Program before exiting.</span></span>|[<span data-ttu-id="833fb-124">sysmail_configure_sp &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="833fb-124">sysmail_configure_sp &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sysmail-configure-sp-transact-sql)|  
  
## <a name="see-also"></a><span data-ttu-id="833fb-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="833fb-125">See Also</span></span>  
 <span data-ttu-id="833fb-126">[SQL Server Service Broker](../../database-engine/configure-windows/sql-server-service-broker.md) </span><span class="sxs-lookup"><span data-stu-id="833fb-126">[SQL Server Service Broker](../../database-engine/configure-windows/sql-server-service-broker.md) </span></span>  
 <span data-ttu-id="833fb-127">[Journal et audits de la messagerie de base de données](database-mail-log-and-audits.md) </span><span class="sxs-lookup"><span data-stu-id="833fb-127">[Database Mail Log and Audits](database-mail-log-and-audits.md) </span></span>  
 [<span data-ttu-id="833fb-128">Messagerie de base de données</span><span class="sxs-lookup"><span data-stu-id="833fb-128">Database Mail</span></span>](database-mail.md)  
  
  
