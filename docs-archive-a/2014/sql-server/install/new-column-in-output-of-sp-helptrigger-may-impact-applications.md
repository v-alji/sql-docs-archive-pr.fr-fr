---
title: La nouvelle colonne dans la sortie de sp_helptrigger peut avoir un impact sur les applications | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- sp_helptrigger
ms.assetid: b7c42a8f-f2e0-4fa3-b046-3cf39c854c47
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0b1f5e936843ed84a5c6b88e2f3685e7a4272bc2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613768"
---
# <a name="new-column-in-output-of-sp_helptrigger-may-impact-applications"></a><span data-ttu-id="03289-102">La nouvelle colonne dans la sortie de sp_helptrigger peut avoir un impact sur des applications</span><span class="sxs-lookup"><span data-stu-id="03289-102">New column in output of sp_helptrigger may impact applications</span></span>
  <span data-ttu-id="03289-103">trigger_schemaias la dernière colonne dans le jeu de résultats retourné par la procédure stockée système sp_helptrigger.</span><span class="sxs-lookup"><span data-stu-id="03289-103">trigger_schemaias the last column in the result set returned by the sp_helptrigger system stored procedure.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)] <span data-ttu-id="03289-104">Pour obtenir des informations sur les déclencheurs définis sur une table particulière, interrogez l'affichage catalogue sys.triggers.</span><span class="sxs-lookup"><span data-stu-id="03289-104">To obtain information about triggers defined on a particular table, query the sys.triggers catalog view.</span></span>  
  
## <a name="component"></a><span data-ttu-id="03289-105">Composant</span><span class="sxs-lookup"><span data-stu-id="03289-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="03289-106">Action corrective</span><span class="sxs-lookup"><span data-stu-id="03289-106">Corrective Action</span></span>  
 <span data-ttu-id="03289-107">Vérifiez l'emploi de sp_helptrigger dans vos applications.</span><span class="sxs-lookup"><span data-stu-id="03289-107">Review the use of sp_helptrigger in applications.</span></span> <span data-ttu-id="03289-108">Vous devrez peut-être modifier vos applications pour tenir compte de cette colonne supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="03289-108">You may need to modify your applications to accommodate the additional column.</span></span> <span data-ttu-id="03289-109">Vous pouvez également utiliser l'affichage catalogue sys.triggers à la place.</span><span class="sxs-lookup"><span data-stu-id="03289-109">Alternatively, you can use the sys.triggers catalog view instead.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03289-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="03289-110">See Also</span></span>  
 <span data-ttu-id="03289-111">[Problèmes de mise à niveau Moteur de base de données](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="03289-111">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="03289-112">Le conseiller de mise à niveau de SQL Server 2014 &#91;nouveau&#93;</span><span class="sxs-lookup"><span data-stu-id="03289-112">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
