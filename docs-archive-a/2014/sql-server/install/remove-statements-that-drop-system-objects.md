---
title: Supprimer les instructions qui suppriment des objets système | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- drop system objects [SQL Server]
ms.assetid: cdfc3c50-c801-4039-a4bf-b35f876f1c61
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: d9e8fbfd4a436e87cee413d95468ccf5dd36b9dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600490"
---
# <a name="remove-statements-that-drop-system-objects"></a><span data-ttu-id="71acb-102">Supprimer les instructions qui suppriment des objets système</span><span class="sxs-lookup"><span data-stu-id="71acb-102">Remove statements that drop system objects</span></span>
  <span data-ttu-id="71acb-103">Le Conseiller de mise à niveau a détecté des instructions qui suppriment les objets système.</span><span class="sxs-lookup"><span data-stu-id="71acb-103">Upgrade Advisor detected statements that drop system objects.</span></span> <span data-ttu-id="71acb-104">Les objets système, y compris les procédures stockées étendues, sont déployés dans une base de données de **ressources** en lecture seule (mssqlsystemresource) et ne peuvent pas être supprimés.</span><span class="sxs-lookup"><span data-stu-id="71acb-104">System objects, including extended stored procedures, are deployed in the read-only **resource** database (mssqlsystemresource) and cannot be dropped.</span></span> <span data-ttu-id="71acb-105">Modifiez vos applications pour révoquer ou refuser l'autorisation EXECUTE sur les objets système.</span><span class="sxs-lookup"><span data-stu-id="71acb-105">Modify your applications to either revoke or deny EXECUTE permission on system objects.</span></span>  
  
## <a name="component"></a><span data-ttu-id="71acb-106">Composant</span><span class="sxs-lookup"><span data-stu-id="71acb-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="71acb-107">Description</span><span class="sxs-lookup"><span data-stu-id="71acb-107">Description</span></span>  
 <span data-ttu-id="71acb-108">Des instructions telles que DROP TABLE, DROP PROCEDURE et **sp_dropextendedproc** ne peuvent pas être utilisées pour supprimer des objets système parce que ces objets sont déployés dans la base de données des **ressources** en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="71acb-108">Statements such as DROP TABLE, DROP PROCEDURE, and **sp_dropextendedproc** cannot be used to remove system objects, because these objects are deployed in the read-only **resource** database.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="71acb-109">Action corrective</span><span class="sxs-lookup"><span data-stu-id="71acb-109">Corrective Action</span></span>  
 <span data-ttu-id="71acb-110">Supprimez toutes les instructions qui tentent d'éliminer des objets système de votre application.</span><span class="sxs-lookup"><span data-stu-id="71acb-110">Remove all statements that try to drop system objects from your applications.</span></span> <span data-ttu-id="71acb-111">Modifiez vos applications pour révoquer ou refuser l'autorisation EXECUTE sur les objets système.</span><span class="sxs-lookup"><span data-stu-id="71acb-111">Modify your applications to either revoke or deny EXECUTE permission on system objects.</span></span> <span data-ttu-id="71acb-112">Vous pouvez également utiliser l'outil Configuration de la surface d'exposition pour désactiver certains de ces objets.</span><span class="sxs-lookup"><span data-stu-id="71acb-112">Alternatively, you can use the Surface Area Configuration (SAC) tool to disable some of these objects.</span></span> <span data-ttu-id="71acb-113">Par exemple, la procédure stockée étendue **xp_cmdshell** peut être désactivée ou activée à l'aide de l'outil SAC.</span><span class="sxs-lookup"><span data-stu-id="71acb-113">For example, the **xp_cmdshell** extended stored procedure can be disabled or enabled using the SAC tool.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71acb-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="71acb-114">See Also</span></span>  
 <span data-ttu-id="71acb-115">[Problèmes de mise à niveau Moteur de base de données](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="71acb-115">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="71acb-116">Le conseiller de mise à niveau de SQL Server 2014 &#91;nouveau&#93;</span><span class="sxs-lookup"><span data-stu-id="71acb-116">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
