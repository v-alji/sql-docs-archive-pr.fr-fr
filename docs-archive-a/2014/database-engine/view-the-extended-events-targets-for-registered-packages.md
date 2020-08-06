---
title: Afficher les cibles d’événements étendus pour les packages inscrits | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- targets [SQL Server extended events]
- viewing event targets
- extended events [SQL Server], viewing targets
ms.assetid: 4985aa5f-ac99-49f6-852c-9d25916549e9
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 8e796d141ef943399fc2469c232b34b1956cef3b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614764"
---
# <a name="view-the-extended-events-targets-for-registered-packages"></a><span data-ttu-id="7c875-102">Afficher les cibles d'événements étendus pour les packages enregistrés</span><span class="sxs-lookup"><span data-stu-id="7c875-102">View the Extended Events Targets for Registered Packages</span></span>
  <span data-ttu-id="7c875-103">Avant de créer une session d’événements étendus [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , il est utile de déterminer quelles sont les cibles d’événements étendus présentes.</span><span class="sxs-lookup"><span data-stu-id="7c875-103">Before you create a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Extended Events session, it is useful to determine what Extended Events targets are available.</span></span> <span data-ttu-id="7c875-104">Cette tâche implique l'utilisation de l'Éditeur de requête dans [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] pour effectuer la procédure suivante.</span><span class="sxs-lookup"><span data-stu-id="7c875-104">This task involves using Query Editor in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to perform the following procedure.</span></span>  
  
 <span data-ttu-id="7c875-105">Une fois que les instructions de cette procédure sont exécutées, l’onglet **Résultats** de l’éditeur de requête affiche les deux colonnes suivantes :</span><span class="sxs-lookup"><span data-stu-id="7c875-105">After the statements in this procedure finish, the **Results** tab of Query Editor displays the following two columns:</span></span>  
  
-   <span data-ttu-id="7c875-106">package_name</span><span class="sxs-lookup"><span data-stu-id="7c875-106">package_name</span></span>  
  
-   <span data-ttu-id="7c875-107">target_name</span><span class="sxs-lookup"><span data-stu-id="7c875-107">target_name</span></span>  
  
## <a name="to-view-the-extended-events-targets-for-registered-packages-using-query-editor"></a><span data-ttu-id="7c875-108">Pour afficher les cibles d'événements étendus pour les packages enregistrés à l'aide de l'éditeur de requête</span><span class="sxs-lookup"><span data-stu-id="7c875-108">To view the Extended Events targets for registered packages using Query Editor</span></span>  
  
-   <span data-ttu-id="7c875-109">Dans l'éditeur de requêtes, émettez les instructions suivantes.</span><span class="sxs-lookup"><span data-stu-id="7c875-109">In Query Editor, issue the following statements.</span></span>  
  
    ```  
    USE msdb  
    SELECT p.name package_name, o.name target_name  
    FROM sys.dm_xe_objects o  
    JOIN sys.dm_xe_packages p  
         ON o.package_guid = p.guid  
    WHERE o.object_type = 'target'  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7c875-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7c875-110">See Also</span></span>  
 <span data-ttu-id="7c875-111">[Cibles des Événements étendus SQL Server](../../2014/database-engine/sql-server-extended-events-targets.md) </span><span class="sxs-lookup"><span data-stu-id="7c875-111">[SQL Server Extended Events Targets](../../2014/database-engine/sql-server-extended-events-targets.md) </span></span>  
 <span data-ttu-id="7c875-112">[sys.dm_xe_objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-objects-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7c875-112">[sys.dm_xe_objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-objects-transact-sql) </span></span>  
 [<span data-ttu-id="7c875-113">sys.dm_xe_packages &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7c875-113">sys.dm_xe_packages &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-packages-transact-sql)  
  
  
