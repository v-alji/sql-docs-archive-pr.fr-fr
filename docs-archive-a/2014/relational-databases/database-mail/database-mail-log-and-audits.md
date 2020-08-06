---
title: Journal et audits de la messagerie de base de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- auditing [SQL Server]
- Database Mail [SQL Server], auditing
- logs [Database Mail]
- audits [SQL Server], Database Mail
- Database Mail [SQL Server], logging
ms.assetid: 846589ee-5fe5-4ab3-b335-0c253e569f99
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6267389f187b955982ec1c18c411f703b4562f3c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709612"
---
# <a name="database-mail-log-and-audits"></a><span data-ttu-id="9dea3-102">Journal et audits de la messagerie de base de données</span><span class="sxs-lookup"><span data-stu-id="9dea3-102">Database Mail Log and Audits</span></span>
  <span data-ttu-id="9dea3-103">La fonctionnalité de journalisation de la messagerie de base de données offre un moyen d'isoler et de résoudre les problèmes.</span><span class="sxs-lookup"><span data-stu-id="9dea3-103">The Database Mail logging functionality is designed to provide a way to isolate and correct problems.</span></span> <span data-ttu-id="9dea3-104">La messagerie de base de données stocke les informations du journal dans la base de données **msdb** .</span><span class="sxs-lookup"><span data-stu-id="9dea3-104">Database Mail stores the log information in the **msdb** database.</span></span> <span data-ttu-id="9dea3-105">Les informations sur le contenu des messages électroniques de la messagerie de base de données, l'état des messages électroniques et tous les messages reçus (notamment les erreurs) sont enregistrées par la messagerie de base de données et peuvent être utilisées à des fins de dépannage et d'audit.</span><span class="sxs-lookup"><span data-stu-id="9dea3-105">Information about Database Mail e-mail content, status of e-mails, and any messages received, such as errors  are logged by Database Mail and can be used for troubleshooting and auditing purposes.</span></span>  
  
## <a name="database-mail-logs"></a><span data-ttu-id="9dea3-106">Journaux de la messagerie de base de données</span><span class="sxs-lookup"><span data-stu-id="9dea3-106">Database Mail Logs</span></span>  
 <span data-ttu-id="9dea3-107">Les tables de la base de données **msdb** journalisent les informations en provenance du [Programme externe de la messagerie de base de données](database-mail-external-program.md).</span><span class="sxs-lookup"><span data-stu-id="9dea3-107">Tables in the **msdb** database log information from the [Database Mail External Program](database-mail-external-program.md).</span></span> <span data-ttu-id="9dea3-108">Dans [Vues de la messagerie de base de données &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/database-mail-views-transact-sql), des tables sont exposées à des fins de dépannage.</span><span class="sxs-lookup"><span data-stu-id="9dea3-108">[Database Mail Views &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/database-mail-views-transact-sql) expose the tables for troubleshooting purposes.</span></span> <span data-ttu-id="9dea3-109">Des erreurs apparaissent dans la vue [sysmail_event_log &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sysmail-event-log-transact-sql) si Service Broker ne peut pas activer le programme externe, si celui-ci rencontre des erreurs réseau ou si le serveur SMTP (Simple Mail Transport Protocol) refuse un message électronique.</span><span class="sxs-lookup"><span data-stu-id="9dea3-109">Errors appear in the [sysmail_event_log &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sysmail-event-log-transact-sql) view if Service Broker cannot activate the external program, if the external program encounters networking errors or if the Simple Mail Transport Protocol (SMTP) server refuses an e-mail message.</span></span> <span data-ttu-id="9dea3-110">Si le programme externe ne peut pas se connecter aux tables **msdb** , il consigne les erreurs dans le journal des événements des applications Windows.</span><span class="sxs-lookup"><span data-stu-id="9dea3-110">In the event that the external program cannot log to the **msdb** tables, the program logs errors to the Windows application event log.</span></span>  
  
 <span data-ttu-id="9dea3-111">Les tables internes de la base de données **msdb** contiennent les messages électroniques et les pièces jointes envoyés depuis la messagerie de base de données, ainsi que l’état actuel de chaque message.</span><span class="sxs-lookup"><span data-stu-id="9dea3-111">Internal tables in the **msdb** database contain the e-mail messages and attachments sent from Database Mail, together with the current status of each message.</span></span> <span data-ttu-id="9dea3-112">La messagerie de base de données met ces tables à jour chaque fois qu'un message est traité.</span><span class="sxs-lookup"><span data-stu-id="9dea3-112">Database Mail updates these tables as each message is processed.</span></span>  
  
## <a name="database-mail-auditing-tasks"></a><span data-ttu-id="9dea3-113">Tâches d'audit de la messagerie de base de données</span><span class="sxs-lookup"><span data-stu-id="9dea3-113">Database Mail Auditing tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9dea3-114">**Vérification et gestion des journaux de la messagerie de base de données**</span><span class="sxs-lookup"><span data-stu-id="9dea3-114">**Reviewing and managing Database Mail logs**</span></span>|<span data-ttu-id="9dea3-115">**Lien vers la rubrique**</span><span class="sxs-lookup"><span data-stu-id="9dea3-115">**Link to Topic**</span></span>|  
|<span data-ttu-id="9dea3-116">Vérifier l'état de remise d'un message individuel</span><span class="sxs-lookup"><span data-stu-id="9dea3-116">Check the delivery status of an individual message</span></span>|[<span data-ttu-id="9dea3-117">Vérifier l’état des messages électroniques envoyés avec la messagerie de base de données</span><span class="sxs-lookup"><span data-stu-id="9dea3-117">Check the Status of E-Mail Messages Sent With Database Mail</span></span>](check-the-status-of-e-mail-messages-sent-with-database-mail.md)|  
|<span data-ttu-id="9dea3-118">Nettoyer les messages, les pièces jointes et les entrées de journal de la messagerie de base de données</span><span class="sxs-lookup"><span data-stu-id="9dea3-118">Clean up Database Mail messages, attachments, and log entries</span></span>|[<span data-ttu-id="9dea3-119">sysmail_delete_mailitems_sp &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9dea3-119">sysmail_delete_mailitems_sp &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sysmail-delete-mailitems-sp-transact-sql)<br /><br /> [<span data-ttu-id="9dea3-120">sysmail_delete_log_sp &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9dea3-120">sysmail_delete_log_sp &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sysmail-delete-log-sp-transact-sql)|  
|<span data-ttu-id="9dea3-121">Archiver les messages et les journaux de la messagerie de base de données</span><span class="sxs-lookup"><span data-stu-id="9dea3-121">Archive the Database Email Messages and Logs</span></span>|[<span data-ttu-id="9dea3-122">Créer un travail SQL Server Agent pour archiver les messages et les journaux d’événements de la messagerie de base de données</span><span class="sxs-lookup"><span data-stu-id="9dea3-122">Create a SQL Server Agent Job to Archive Database Mail Messages and Event Logs</span></span>](create-a-sql-server-agent-job-to-archive-database-mail-messages-and-event-logs.md)|  
  
## <a name="see-also"></a><span data-ttu-id="9dea3-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9dea3-123">See Also</span></span>  
 [<span data-ttu-id="9dea3-124">Analyser l’utilisation des ressources &#40;Moniteur système&#41;</span><span class="sxs-lookup"><span data-stu-id="9dea3-124">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](../performance-monitor/monitor-resource-usage-system-monitor.md)  
  
  
