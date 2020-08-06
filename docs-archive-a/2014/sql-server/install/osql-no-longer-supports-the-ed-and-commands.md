---
title: osql ne prend plus en charge les commandes | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- ED command
- osql utility [SQL Server]
- '!! command'
ms.assetid: 7cc2852f-94e8-4292-9326-c3f1a1acd281
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 1ad92a32c47002c8f56e56a5b3695d42d3bdd671
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605894"
---
# <a name="osql-no-longer-supports-the-ed-and--commands"></a><span data-ttu-id="441a7-103">osql ne prend plus en charge les</span><span class="sxs-lookup"><span data-stu-id="441a7-103">osql no longer supports the ED and !!</span></span> <span data-ttu-id="441a7-104">commandes</span><span class="sxs-lookup"><span data-stu-id="441a7-104">commands</span></span>
  <span data-ttu-id="441a7-105">L’utilitaire **osql** ne prend pas en charge les **Ed** et **!!**</span><span class="sxs-lookup"><span data-stu-id="441a7-105">The **osql** utility does not support the **ED** and **!!**</span></span> <span data-ttu-id="441a7-106">commandes.</span><span class="sxs-lookup"><span data-stu-id="441a7-106">commands.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="441a7-107">Action corrective</span><span class="sxs-lookup"><span data-stu-id="441a7-107">Corrective Action</span></span>  
 <span data-ttu-id="441a7-108">Supprimez les références aux **Ed** et **!!**</span><span class="sxs-lookup"><span data-stu-id="441a7-108">Remove references to the **ED** and **!!**</span></span> <span data-ttu-id="441a7-109">commandes de vos scripts.</span><span class="sxs-lookup"><span data-stu-id="441a7-109">commands from your scripts.</span></span>  
  
 <span data-ttu-id="441a7-110">Si vous souhaitez utiliser le **Ed** et **!!**</span><span class="sxs-lookup"><span data-stu-id="441a7-110">If you want to use the **ED** and **!!**</span></span> <span data-ttu-id="441a7-111">des commandes, utilisez l’utilitaire **sqlcmd** au lieu de **osql**.</span><span class="sxs-lookup"><span data-stu-id="441a7-111">commands, use the **sqlcmd** utility instead of **osql**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="441a7-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="441a7-112">See Also</span></span>  
 <span data-ttu-id="441a7-113">[Problèmes de mise à niveau Moteur de base de données](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="441a7-113">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="441a7-114">Le conseiller de mise à niveau de SQL Server 2014 &#91;nouveau&#93;</span><span class="sxs-lookup"><span data-stu-id="441a7-114">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
