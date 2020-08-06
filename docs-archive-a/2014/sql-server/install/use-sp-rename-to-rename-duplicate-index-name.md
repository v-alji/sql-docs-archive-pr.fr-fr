---
title: Utiliser sp_rename pour renommer le nom d’index en double | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- table names [SQL Server]
- duplicate table names
- index names [SQL Server]
- sp_rename
- duplicate index names
ms.assetid: ee66c7a5-eb6d-4fcf-970c-ab099d78c8d9
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: b8ffe3b9befd0c7239d32094e5738e0fb2947c5a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710123"
---
# <a name="use-sp_rename-to-rename-duplicate-index-name"></a><span data-ttu-id="8acbd-102">Utiliser sp_rename pour renommer le nom d'index en double</span><span class="sxs-lookup"><span data-stu-id="8acbd-102">Use sp_rename to rename duplicate index name</span></span>
  <span data-ttu-id="8acbd-103">Le Conseiller de mise à niveau a détecté des noms d'index de table ou de vue en double.</span><span class="sxs-lookup"><span data-stu-id="8acbd-103">Upgrade Advisor has detected duplicate table or view index names.</span></span> <span data-ttu-id="8acbd-104">Renommez les index afin de supprimer les doublons avant la mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="8acbd-104">Rename the indexes to remove duplicates before upgrading.</span></span>  
  
## <a name="component"></a><span data-ttu-id="8acbd-105">Composant</span><span class="sxs-lookup"><span data-stu-id="8acbd-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="8acbd-106">Action corrective</span><span class="sxs-lookup"><span data-stu-id="8acbd-106">Corrective Action</span></span>  
  
1.  <span data-ttu-id="8acbd-107">Localisez les index en double en exécutant la requête ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="8acbd-107">Locate the duplicate indexes by executing the following query.</span></span>  
  
    ```  
    SELECT DISTINCT OBJECT_NAME(o.id), name  
    FROM sysindexes as o  
    WHERE EXISTS   
        (SELECT name FROM sysindexes  as i  
          WHERE i.id = o.id  
          AND i.name = o.name and i.indid < o.indid);  
    ```  
  
2.  <span data-ttu-id="8acbd-108">Utilisez **sp_rename** pour changer l'un des noms d'index.</span><span class="sxs-lookup"><span data-stu-id="8acbd-108">Use **sp_rename** to change one of the index names.</span></span> <span data-ttu-id="8acbd-109">Ces noms étant identiques, vous ne pouvez pas déterminer quel index sera renommé.</span><span class="sxs-lookup"><span data-stu-id="8acbd-109">Because the index names are the same, you cannot determine which index will be renamed.</span></span> <span data-ttu-id="8acbd-110">La procédure qui suit vous permet de différencier les index.</span><span class="sxs-lookup"><span data-stu-id="8acbd-110">This step allows you to differentiate the indexes.</span></span>  
  
    ```  
    EXEC sp_rename N'table_name.index_name', N'new_index_name', N'INDEX'  
    ```  
  
3.  <span data-ttu-id="8acbd-111">Pour vérifier quel index a été renommé, exécutez la requête ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="8acbd-111">Verify which index was renamed by executing the following query.</span></span> <span data-ttu-id="8acbd-112">Elle renvoie tous les index (y compris les noms des colonnes clés) de la table ou de la vue spécifiée.</span><span class="sxs-lookup"><span data-stu-id="8acbd-112">This query returns all indexes (including key column names) on the specified table or view.</span></span>  
  
    ```  
    SELECT i.name AS IndexName, c.name AS ColumnName, ik.colid, ik.keyno  
    FROM sysindexes i  
    JOIN sysindexkeys ik ON i.id = ik.id and i.indid = ik.indid   
    JOIN syscolumns c ON c.id = ik.id and ik.colid = c.colid  
    WHERE i.id = OBJECT_ID('table_or_view_name')  
    ```  
  
4.  <span data-ttu-id="8acbd-113">Si nécessaire, utilisez de nouveau **sp_rename** pour corriger les noms d'index.</span><span class="sxs-lookup"><span data-stu-id="8acbd-113">If necessary, use **sp_rename** again to correct the index names.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8acbd-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8acbd-114">See Also</span></span>  
 <span data-ttu-id="8acbd-115">[Problèmes de mise à niveau Moteur de base de données](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="8acbd-115">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="8acbd-116">Le conseiller de mise à niveau de SQL Server 2014 &#91;nouveau&#93;</span><span class="sxs-lookup"><span data-stu-id="8acbd-116">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
