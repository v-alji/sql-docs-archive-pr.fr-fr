---
title: Utiliser la session system_health | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xevents
ms.topic: conceptual
helpviewer_keywords:
- extended events [SQL Server], system health session
- extended events [SQL Server], system_health session
- system_health session [SQL Server extended events]
- system health session [SQL Server extended events]
ms.assetid: 1e1fad43-d747-4775-ac0d-c50648e56d78
author: yualan
ms.author: alayu
ms.openlocfilehash: 86c3221fb4c0ea0690b369888ac8f2f9f82d6ef9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600902"
---
# <a name="use-the-system_health-session"></a><span data-ttu-id="52913-102">Utiliser la session system_health</span><span class="sxs-lookup"><span data-stu-id="52913-102">Use the system_health Session</span></span>
  <span data-ttu-id="52913-103">La session system_health est une session Événements étendus incluse par défaut avec [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="52913-103">The system_health session is an Extended Events session that is included by default with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="52913-104">Cette session démarre automatiquement en même temps que le [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] et s’exécute sans effet notable sur les performances.</span><span class="sxs-lookup"><span data-stu-id="52913-104">This session starts automatically when the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] starts, and runs without any noticeable performance effects.</span></span> <span data-ttu-id="52913-105">Elle recueille des données système qui peuvent vous aider à résoudre des problèmes de performances dans le [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="52913-105">The session collects system data that you can use to help troubleshoot performance issues in the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="52913-106">Il est donc déconseillé de l'arrêter ou de la supprimer.</span><span class="sxs-lookup"><span data-stu-id="52913-106">Therefore, we recommend that you do not stop or delete the session.</span></span>  
  
 <span data-ttu-id="52913-107">Cette session recueille des informations, dont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="52913-107">The session collects information that includes the following:</span></span>  
  
-   <span data-ttu-id="52913-108">Le sql_text et le session_id des sessions qui rencontrent une erreur de gravité >= 20.</span><span class="sxs-lookup"><span data-stu-id="52913-108">The sql_text and session_id for any sessions that encounter an error that has a severity >=20.</span></span>  
  
-   <span data-ttu-id="52913-109">Le sql_text et le session_id des sessions qui rencontrent une erreur de mémoire.</span><span class="sxs-lookup"><span data-stu-id="52913-109">The sql_text and session_id for any sessions that encounter a memory-related error.</span></span> <span data-ttu-id="52913-110">Il s'agit des erreurs 17803, 701, 802, 8645, 8651, 8657 et 8902.</span><span class="sxs-lookup"><span data-stu-id="52913-110">The errors include 17803, 701, 802, 8645, 8651, 8657 and 8902.</span></span>  
  
-   <span data-ttu-id="52913-111">L'historique des problèmes d'improductivité du planificateur.</span><span class="sxs-lookup"><span data-stu-id="52913-111">A record of any non-yielding scheduler problems.</span></span> <span data-ttu-id="52913-112">(Ceux-ci s'affichent dans le journal des erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sous l'erreur 17883).</span><span class="sxs-lookup"><span data-stu-id="52913-112">(These appear in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log as error 17883.)</span></span>  
  
-   <span data-ttu-id="52913-113">Les interblocages détectés.</span><span class="sxs-lookup"><span data-stu-id="52913-113">Any deadlocks that are detected.</span></span>  
  
-   <span data-ttu-id="52913-114">Le callstack, sql_text et le session_id des sessions ayant attendu des verrous (ou d’autres ressources pertinentes) pendant plus de 15 secondes.</span><span class="sxs-lookup"><span data-stu-id="52913-114">The callstack, sql_text, and session_id for any sessions that have waited on latches (or other interesting resources) for > 15 seconds.</span></span>  
  
-   <span data-ttu-id="52913-115">Le callstack, le sql_text et le session_id des sessions ayant attendu des verrous pendant plus de 30 secondes.</span><span class="sxs-lookup"><span data-stu-id="52913-115">The callstack, sql_text, and session_id for any sessions that have waited on locks for > 30 seconds.</span></span>  
  
-   <span data-ttu-id="52913-116">Le callstack, le sql_text et le session_id des sessions ayant attendu longtemps des attentes préemptives.</span><span class="sxs-lookup"><span data-stu-id="52913-116">The callstack, sql_text, and session_id for any sessions that have waited for a long time for preemptive waits.</span></span> <span data-ttu-id="52913-117">La durée varie selon le type d'attente.</span><span class="sxs-lookup"><span data-stu-id="52913-117">The duration varies by wait type.</span></span> <span data-ttu-id="52913-118">Une attente préemptive est une situation où [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] attend des appels d'API externes.</span><span class="sxs-lookup"><span data-stu-id="52913-118">A preemptive wait is where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is waiting for external API calls.</span></span>  
  
-   <span data-ttu-id="52913-119">callstack et session_id pour l'allocation CLR et les échecs d'allocation virtuelle.</span><span class="sxs-lookup"><span data-stu-id="52913-119">The callstack and session_id for CLR allocation and virtual allocation failures.</span></span>  
  
-   <span data-ttu-id="52913-120">Les événements ring_buffer pour le gestionnaire d'allocation mémoire, le moniteur du planificateur, l'insuffisance mémoire du nœud de mémoire, la sécurité et la connectivité.</span><span class="sxs-lookup"><span data-stu-id="52913-120">The ring_buffer events for the memory broker, scheduler monitor, memory node OOM, security, and connectivity.</span></span>  
  
-   <span data-ttu-id="52913-121">Résultats des composants système depuis sp_server_diagnostics.</span><span class="sxs-lookup"><span data-stu-id="52913-121">System component results from sp_server_diagnostics.</span></span>  
  
-   <span data-ttu-id="52913-122">Intégrité de l'instance recueillie par scheduler_monitor_system_health_ring_buffer_recorded.</span><span class="sxs-lookup"><span data-stu-id="52913-122">Instance health collected by scheduler_monitor_system_health_ring_buffer_recorded.</span></span>  
  
-   <span data-ttu-id="52913-123">Échecs d'allocation CLR</span><span class="sxs-lookup"><span data-stu-id="52913-123">CLR Allocation failures.</span></span>  
  
-   <span data-ttu-id="52913-124">Erreurs de connectivité avec connectivity_ring_buffer_recorded.</span><span class="sxs-lookup"><span data-stu-id="52913-124">Connectivity errors using connectivity_ring_buffer_recorded.</span></span>  
  
-   <span data-ttu-id="52913-125">Erreurs de sécurité avec security_error_ring_buffer_recorded.</span><span class="sxs-lookup"><span data-stu-id="52913-125">Security errors using security_error_ring_buffer_recorded.</span></span>  
  
## <a name="viewing-the-session-data"></a><span data-ttu-id="52913-126">Consultation des données de session</span><span class="sxs-lookup"><span data-stu-id="52913-126">Viewing the Session Data</span></span>  
 <span data-ttu-id="52913-127">La session utilise la cible de mémoire tampon en anneau pour stocker les données.</span><span class="sxs-lookup"><span data-stu-id="52913-127">The session uses the ring buffer target to store the data.</span></span> <span data-ttu-id="52913-128">Pour consulter les données de session, utilisez la requête suivante :</span><span class="sxs-lookup"><span data-stu-id="52913-128">To view the session data, use the following query:</span></span>  
  
```  
SELECT CAST(xet.target_data as xml) FROM sys.dm_xe_session_targets xet  
JOIN sys.dm_xe_sessions xe  
ON (xe.address = xet.event_session_address)  
WHERE xe.name = 'system_health'  
```  
  
 <span data-ttu-id="52913-129">Pour afficher les données de session depuis les fichier d'événements, utilisez l'interface utilisateur Événements étendus disponible dans Management Studio.</span><span class="sxs-lookup"><span data-stu-id="52913-129">To view the session data from the event file, use the Extended Events user interface available in Management Studio.</span></span> <span data-ttu-id="52913-130">Pour plus d’informations, consultez [afficher les données de session d’événements](../../database-engine/view-event-session-data.md) .</span><span class="sxs-lookup"><span data-stu-id="52913-130">See [View Event Session Data](../../database-engine/view-event-session-data.md) for more information.</span></span>  
  
## <a name="restoring-the-system_health-session"></a><span data-ttu-id="52913-131">Restauration de la session system_health</span><span class="sxs-lookup"><span data-stu-id="52913-131">Restoring the system_health Session</span></span>  
 <span data-ttu-id="52913-132">Si vous supprimez la session system_health, vous pouvez la restaurer en exécutant le fichier **u_tables.sql** dans l’Éditeur de requête.</span><span class="sxs-lookup"><span data-stu-id="52913-132">If you delete the system_health session, you can restore it by executing the **u_tables.sql** file in Query Editor.</span></span> <span data-ttu-id="52913-133">Ce fichier se trouve dans le dossier suivant, où C: représente le lecteur sur lequel vous avez installé les fichiers du programme [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="52913-133">This file is located in the following folder, where C: represents the drive where you installed the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] program files:</span></span>  
  
 <span data-ttu-id="52913-134">C:\Program Files\Microsoft SQL Server\MSSQL12. \<*instanceid*> \MSSQL\Install</span><span class="sxs-lookup"><span data-stu-id="52913-134">C:\Program Files\Microsoft SQL Server\MSSQL12.\<*instanceid*>\MSSQL\Install</span></span>  
  
 <span data-ttu-id="52913-135">Sachez qu’après avoir restauré la session, vous devez la démarrer en utilisant l’instruction ALTER EVENT SESSION ou en utilisant le nœud **Événements étendus** dans l’Explorateur d’objets.</span><span class="sxs-lookup"><span data-stu-id="52913-135">Be aware that after you restore the session, you must start the session by using the ALTER EVENT SESSION statement or by using the **Extended Events** node in Object Explorer.</span></span> <span data-ttu-id="52913-136">Sinon, la session démarre automatiquement la prochaine fois que vous redémarrerez le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="52913-136">Otherwise, the session starts automatically the next time that you restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52913-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="52913-137">See Also</span></span>  
 [<span data-ttu-id="52913-138">Outils associés aux événements étendus</span><span class="sxs-lookup"><span data-stu-id="52913-138">Extended Events Tools</span></span>](extended-events-tools.md)  
  
  
