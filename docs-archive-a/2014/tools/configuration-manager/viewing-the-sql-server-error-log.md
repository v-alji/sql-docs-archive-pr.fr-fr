---
title: Affichage du journal des erreurs SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- cycling SQL Server error log
- viewing SQL Server error log
- errors [SQL Server], logs
- SQL Server error log
- displaying SQL Server error log
- logs [SQL Server], SQL Server error logs
ms.assetid: 6908c21a-65e3-458f-a272-fee256d86448
author: stevestein
ms.author: sstein
ms.openlocfilehash: 822ae4fba589f005aaee41857a9db3388a309254
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599722"
---
# <a name="viewing-the-sql-server-error-log"></a><span data-ttu-id="b6f5c-102">Consultation du journal des erreurs de SQL Server</span><span class="sxs-lookup"><span data-stu-id="b6f5c-102">Viewing the SQL Server Error Log</span></span>
  <span data-ttu-id="b6f5c-103">Consultez le journal des erreurs de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour vérifier que l’exécution des processus a réussi (par exemple les opérations de sauvegarde et de restauration, les commandes de traitement ou d’autres scripts et processus).</span><span class="sxs-lookup"><span data-stu-id="b6f5c-103">View the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to ensure that processes have completed successfully (for example, backup and restore operations, batch commands, or other scripts and processes).</span></span> <span data-ttu-id="b6f5c-104">Cela peut s’avérer utile pour détecter tout problème en cours ou potentiel, y compris les messages de récupération automatique (surtout si une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a été arrêtée, puis redémarrée), les messages du noyau ou d’autres messages d’erreur de niveau serveur.</span><span class="sxs-lookup"><span data-stu-id="b6f5c-104">This can be helpful to detect any current or potential problem areas, including automatic recovery messages (particularly if an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has been stopped and restarted), kernel messages, or other server-level error messages.</span></span>  
  
 <span data-ttu-id="b6f5c-105">Consultez le journal des erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de n'importe quel éditeur de texte.</span><span class="sxs-lookup"><span data-stu-id="b6f5c-105">View the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or any text editor.</span></span> <span data-ttu-id="b6f5c-106">Pour plus d'informations sur l'affichage du journal des erreurs, consultez [Open Log File Viewer](../../relational-databases/logs/log-file-viewer.md).</span><span class="sxs-lookup"><span data-stu-id="b6f5c-106">For more information about how to view the error log, see [Open Log File Viewer](../../relational-databases/logs/log-file-viewer.md).</span></span> <span data-ttu-id="b6f5c-107">Par défaut, le journal des erreurs se trouve dans les fichiers `Program Files\Microsoft SQL Server\MSSQL.`*n*`\MSSQL\LOG\ERRORLOG` et `ERRORLOG.`*n* .</span><span class="sxs-lookup"><span data-stu-id="b6f5c-107">By default, the error log is located at `Program Files\Microsoft SQL Server\MSSQL.`*n*`\MSSQL\LOG\ERRORLOG` and `ERRORLOG.`*n* files.</span></span>  
  
 <span data-ttu-id="b6f5c-108">Un journal des erreurs est créé à chaque démarrage d’une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , bien que la procédure stockée système [sp_cycle_errorlog](/sql/relational-databases/system-stored-procedures/sp-cycle-errorlog-transact-sql) puisse être utilisée pour recycler les fichiers du journal des erreurs sans devoir redémarrer l’instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b6f5c-108">A new error log is created each time an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is started, although the [sp_cycle_errorlog](/sql/relational-databases/system-stored-procedures/sp-cycle-errorlog-transact-sql) system stored procedure can be used to cycle the error log files without having to restart the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b6f5c-109">En principe, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] conserve une copie de sauvegarde des six derniers journaux des erreurs, attribuant l'extension .1 au plus récent, l'extension .2 à celui qui le précède, et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="b6f5c-109">Typically, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] retains backups of the previous six logs and gives the most recent log backup the extension .1, the second most recent the extension .2, and so on.</span></span> <span data-ttu-id="b6f5c-110">Le journal des erreurs en cours n'a aucune extension.</span><span class="sxs-lookup"><span data-stu-id="b6f5c-110">The current error log has no extension.</span></span>  
  
 <span data-ttu-id="b6f5c-111">Soyez informé que vous pouvez également consulter le journal des erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sur les instances de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui est hors connexion ou ne peut pas démarrer.</span><span class="sxs-lookup"><span data-stu-id="b6f5c-111">Be aware that you can also view the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log on instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are offline or cannot start.</span></span> <span data-ttu-id="b6f5c-112">Pour plus d’informations, consultez [Afficher les fichiers journaux hors connexion](../../relational-databases/logs/view-offline-log-files.md).</span><span class="sxs-lookup"><span data-stu-id="b6f5c-112">For more information, see [View Offline Log Files](../../relational-databases/logs/view-offline-log-files.md).</span></span>  
  
  
