---
title: Afficher les événements pour les packages enregistrés | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- viewing events
- extended events [SQL Server], viewing events
ms.assetid: 9a90b1a2-aa69-43f6-bdeb-cc5f57a26c6f
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 5e3665a695bd3f40407a8680872c9b0dc79fbc53
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614765"
---
# <a name="view-the-events-for-registered-packages"></a><span data-ttu-id="687ff-102">Consulter les événements pour les packages enregistrés</span><span class="sxs-lookup"><span data-stu-id="687ff-102">View the Events for Registered Packages</span></span>
  <span data-ttu-id="687ff-103">Avant de créer une session des événements étendus [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , il est utile de savoir quels sont les événements présents dans les packages enregistrés.</span><span class="sxs-lookup"><span data-stu-id="687ff-103">Before you create a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Extended Events session, it is useful to find out what events are available in the registered packages.</span></span> <span data-ttu-id="687ff-104">Pour plus d'informations, consultez [SQL Server Extended Events Packages](../relational-databases/extended-events/sql-server-extended-events-packages.md).</span><span class="sxs-lookup"><span data-stu-id="687ff-104">For more information, see [SQL Server Extended Events Packages](../relational-databases/extended-events/sql-server-extended-events-packages.md).</span></span>  
  
 <span data-ttu-id="687ff-105">L’utilisation de l'éditeur de requêtes dans [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] est nécessaire pour effectuer la procédure suivante.</span><span class="sxs-lookup"><span data-stu-id="687ff-105">Accomplishing this task involves using Query Editor in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to carry out the following procedure.</span></span>  
  
 <span data-ttu-id="687ff-106">Une fois que les instructions de cette procédure sont exécutées, l’onglet **Résultats** de l’éditeur de requêtes affiche les colonnes suivantes :</span><span class="sxs-lookup"><span data-stu-id="687ff-106">After the statements in this procedure finish, the **Results** tab of Query Editor displays the following columns:</span></span>  
  
-   <span data-ttu-id="687ff-107">nom.</span><span class="sxs-lookup"><span data-stu-id="687ff-107">name.</span></span> <span data-ttu-id="687ff-108">Nom du package.</span><span class="sxs-lookup"><span data-stu-id="687ff-108">The package name.</span></span>  
  
-   <span data-ttu-id="687ff-109">événement.</span><span class="sxs-lookup"><span data-stu-id="687ff-109">event.</span></span> <span data-ttu-id="687ff-110">Nom de l'événement.</span><span class="sxs-lookup"><span data-stu-id="687ff-110">The event name.</span></span>  
  
-   <span data-ttu-id="687ff-111">mot clé.</span><span class="sxs-lookup"><span data-stu-id="687ff-111">keyword.</span></span> <span data-ttu-id="687ff-112">Mot clé dérivé d'une table de mappage numérique interne.</span><span class="sxs-lookup"><span data-stu-id="687ff-112">A keyword derived from an internal numeric mapping table.</span></span>  
  
-   <span data-ttu-id="687ff-113">canal.</span><span class="sxs-lookup"><span data-stu-id="687ff-113">channel.</span></span> <span data-ttu-id="687ff-114">Audience pour un événement.</span><span class="sxs-lookup"><span data-stu-id="687ff-114">The audience for an event.</span></span>  
  
-   <span data-ttu-id="687ff-115">description.</span><span class="sxs-lookup"><span data-stu-id="687ff-115">description.</span></span> <span data-ttu-id="687ff-116">Description de l'événement.</span><span class="sxs-lookup"><span data-stu-id="687ff-116">The event description.</span></span>  
  
## <a name="to-view-the-events-for-registered-packages-using-query-editor"></a><span data-ttu-id="687ff-117">Pour afficher les événements pour les packages enregistrés à l'aide de l'Éditeur de requête</span><span class="sxs-lookup"><span data-stu-id="687ff-117">To view the events for registered packages using Query Editor</span></span>  
  
-   <span data-ttu-id="687ff-118">Dans l'éditeur de requêtes, émettez les instructions suivantes.</span><span class="sxs-lookup"><span data-stu-id="687ff-118">In Query Editor, issue the following statements.</span></span>  
  
    ```  
    USE msdb  
    SELECT p.name, c.event, k.keyword, c.channel, c.description FROM  
    (  
    SELECT event_package=o.package_guid, o.description,   
    event=c.object_name, channel=v.map_value  
    FROM sys.dm_xe_objects o  
    LEFT JOIN sys.dm_xe_object_columns c ON o.name=c.object_name  
    INNER JOIN sys.dm_xe_map_values v ON c.type_name=v.name   
    AND c.column_value=cast(v.map_key AS nvarchar)  
    WHERE object_type='event' AND (c.name='CHANNEL' or c.name IS NULL)  
  
    ) c LEFT JOIN   
    (  
    SELECT event_package=c.object_package_guid, event=c.object_name,   
    keyword=v.map_value  
    FROM sys.dm_xe_object_columns c INNER JOIN sys.dm_xe_map_values v   
    ON c.type_name=v.name AND c.column_value=v.map_key   
    AND c.type_package_guid=v.object_package_guid  
    INNER JOIN sys.dm_xe_objects o ON o.name=c.object_name   
    AND o.package_guid=c.object_package_guid  
    WHERE object_type='event' AND c.name='KEYWORD'   
    ) k  
    ON  
    k.event_package=c.event_package AND (k.event=c.event or k.event IS NULL)  
    INNER JOIN sys.dm_xe_packages p ON p.guid=c.event_package  
    ORDER BY keyword desc, channel, event  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="687ff-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="687ff-119">See Also</span></span>  
 <span data-ttu-id="687ff-120">[SQL Server des packages d’événements étendus](../relational-databases/extended-events/sql-server-extended-events-packages.md) </span><span class="sxs-lookup"><span data-stu-id="687ff-120">[SQL Server Extended Events Packages](../relational-databases/extended-events/sql-server-extended-events-packages.md) </span></span>  
 <span data-ttu-id="687ff-121">[sys.dm_xe_objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-objects-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="687ff-121">[sys.dm_xe_objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-objects-transact-sql) </span></span>  
 [<span data-ttu-id="687ff-122">sys.dm_xe_packages &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="687ff-122">sys.dm_xe_packages &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-packages-transact-sql)  
  
  
