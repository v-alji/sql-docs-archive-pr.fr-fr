---
title: Supprimer les instructions qui modifient les autorisations au niveau des colonnes sur les objets système | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- column-level permissions [SQL Server]
- removed statement permissions [SQL Server]
ms.assetid: 7f4fbbef-2696-4911-903b-63f6d9e4484a
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: e55af3dca0c55c2babd09bc6cfc48ed0ddf3ad7a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612105"
---
# <a name="remove-statements-that-modify-column-level-permissions-on-system-objects"></a><span data-ttu-id="11e38-102">Supprimer les instructions qui modifient les autorisations de niveau colonne sur les objets système</span><span class="sxs-lookup"><span data-stu-id="11e38-102">Remove statements that modify column-level permissions on system objects</span></span>
  <span data-ttu-id="11e38-103">Le Conseiller de mise à niveau a détecté des autorisations non standard au niveau des colonnes sur les objets système.</span><span class="sxs-lookup"><span data-stu-id="11e38-103">The Upgrade Advisor detected nonstandard column-level permissions on system objects.</span></span> <span data-ttu-id="11e38-104">Ces changements d'autorisations ne seront pas conservés lors de la mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="11e38-104">These permission changes will not be maintained when you upgrade.</span></span> <span data-ttu-id="11e38-105">De plus, les autorisations au niveau des colonnes sur les objets système ne sont plus prises en charge.</span><span class="sxs-lookup"><span data-stu-id="11e38-105">Additionally, column-level permissions on system objects are no longer supported.</span></span> <span data-ttu-id="11e38-106">Supprimez les instructions de vos applications qui définissent des autorisations au niveau des colonnes sur les objets système.</span><span class="sxs-lookup"><span data-stu-id="11e38-106">Remove statements from your applications that set column-level permissions on system objects.</span></span>  
  
## <a name="component"></a><span data-ttu-id="11e38-107">Composant</span><span class="sxs-lookup"><span data-stu-id="11e38-107">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="11e38-108">Action corrective</span><span class="sxs-lookup"><span data-stu-id="11e38-108">Corrective Action</span></span>  
 <span data-ttu-id="11e38-109">Supprimez de votre application les instructions qui accordent, refusent ou révoquent des autorisations au niveau des colonnes sur les objets système.</span><span class="sxs-lookup"><span data-stu-id="11e38-109">Remove statements from your application that grant, deny, or revoke column-level permissions on system objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11e38-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="11e38-110">See Also</span></span>  
 <span data-ttu-id="11e38-111">[Problèmes de mise à niveau Moteur de base de données](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="11e38-111">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="11e38-112">Le conseiller de mise à niveau de SQL Server 2014 &#91;nouveau&#93;</span><span class="sxs-lookup"><span data-stu-id="11e38-112">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
