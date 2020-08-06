---
title: Supprimer les instructions qui modifient les objets système | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- direct system catalog updates [SQL Server]
- system catalogs [SQL Server]
ms.assetid: 221b46c2-c27e-4df8-bd8c-8b990d6d5e98
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 526181bc4bf7ab81df2eaa25f19e7627c9b7af10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710168"
---
# <a name="remove-statements-that-modify-system-objects"></a><span data-ttu-id="29b85-102">Supprimer les instructions qui modifient les objets système</span><span class="sxs-lookup"><span data-stu-id="29b85-102">Remove statements that modify system objects</span></span>
  <span data-ttu-id="29b85-103">Le Conseiller de mise à niveau a détecté des instructions qui mettent à jour le catalogue système.</span><span class="sxs-lookup"><span data-stu-id="29b85-103">Upgrade Advisor detected statements that update the system catalog.</span></span> <span data-ttu-id="29b85-104">Les mises à jour directes du catalogue système ne sont pas autorisées.</span><span class="sxs-lookup"><span data-stu-id="29b85-104">Direct system catalog updates are not allowed.</span></span> <span data-ttu-id="29b85-105">Modifiez vos scripts SQL pour utiliser des API officielles et documentées.</span><span class="sxs-lookup"><span data-stu-id="29b85-105">Modify your SQL scripts to use official and documented APIs.</span></span>  
  
## <a name="component"></a><span data-ttu-id="29b85-106">Composant</span><span class="sxs-lookup"><span data-stu-id="29b85-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="29b85-107">Description</span><span class="sxs-lookup"><span data-stu-id="29b85-107">Description</span></span>  
 <span data-ttu-id="29b85-108">Les mises à jour directes du catalogue système ne sont pas autorisées.</span><span class="sxs-lookup"><span data-stu-id="29b85-108">Direct system catalog updates are not allowed.</span></span> <span data-ttu-id="29b85-109">Toute tentative à cet égard génère l'erreur suivante :</span><span class="sxs-lookup"><span data-stu-id="29b85-109">Any attempt to do so will generate the following error:</span></span>  
  
 `Server: Msg 259, Level 16, State 1, Line 1`  
  
 `Ad hoc updates to system catalogs are not allowed.`  
  
## <a name="corrective-action"></a><span data-ttu-id="29b85-110">Action corrective</span><span class="sxs-lookup"><span data-stu-id="29b85-110">Corrective Action</span></span>  
 <span data-ttu-id="29b85-111">Modifiez vos scripts SQL pour utiliser des API officielles et documentées.</span><span class="sxs-lookup"><span data-stu-id="29b85-111">Modify your SQL scripts to use official and documented APIs.</span></span> <span data-ttu-id="29b85-112">Par exemple, utilisez ALTER DATABASE *database_name* SET EMERGENCY plutôt que d'exécuter une instruction UPDATE sur la table système **sysdatabases** .</span><span class="sxs-lookup"><span data-stu-id="29b85-112">For example, use ALTER DATABASE *database_name* SET EMERGENCY instead of running an UPDATE statement on the **sysdatabases** system table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29b85-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="29b85-113">See Also</span></span>  
 <span data-ttu-id="29b85-114">[Problèmes de mise à niveau Moteur de base de données](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="29b85-114">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="29b85-115">Le conseiller de mise à niveau de SQL Server 2014 &#91;nouveau&#93;</span><span class="sxs-lookup"><span data-stu-id="29b85-115">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](https://docs.microsoft.com/sql/sql-server/install/sql-server-2014-upgrade-advisor)  
  
  
