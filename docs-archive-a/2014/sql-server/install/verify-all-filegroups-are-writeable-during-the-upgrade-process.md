---
title: Vérifier que tous les groupes de fichiers sont accessibles en écriture pendant le processus de mise à niveau | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- filegroups [SQL Server], writeable
- writeable filegroups [SQL Server]
ms.assetid: 2985efc1-4b14-46c3-abbd-a656b159f23c
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 8146efb876bf97c36c549a2b58d104592df611e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710108"
---
# <a name="verify-all-filegroups-are-writeable-during-the-upgrade-process"></a><span data-ttu-id="2a838-102">Vérifier que tous les groupes de fichiers sont accessibles en écriture pendant le processus de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="2a838-102">Verify all filegroups are writeable during the upgrade process</span></span>
  <span data-ttu-id="2a838-103">Le Conseiller de mise à niveau a détecté une base de données possédant un ou plusieurs groupes de fichiers en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="2a838-103">Upgrade Advisor detected a database that has one or more read-only filegroups.</span></span> <span data-ttu-id="2a838-104">Toutes les bases de données de l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] doivent avoir leurs groupes de fichiers définis sur READ_WRITE avant la mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="2a838-104">All databases in the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must have filegroups set to READ_WRITE before upgrading.</span></span>  
  
## <a name="component"></a><span data-ttu-id="2a838-105">Composant</span><span class="sxs-lookup"><span data-stu-id="2a838-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="2a838-106">Action corrective</span><span class="sxs-lookup"><span data-stu-id="2a838-106">Corrective Action</span></span>  
 <span data-ttu-id="2a838-107">Utilisez l'instruction ALTER DATABASE pour définir le groupe de fichiers sur READ_WRITE.</span><span class="sxs-lookup"><span data-stu-id="2a838-107">Use ALTER DATABASE to set the filegroup to READ_WRITE.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a838-108">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2a838-108">See Also</span></span>  
 <span data-ttu-id="2a838-109">[Problèmes de mise à niveau Moteur de base de données](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="2a838-109">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="2a838-110">Le conseiller de mise à niveau de SQL Server 2014 &#91;nouveau&#93;</span><span class="sxs-lookup"><span data-stu-id="2a838-110">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
