---
title: Conditions requises par le compte de service pour la mise à niveau vers SQL Server 2008 sur un contrôleur de domaine | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- domain controllers
- service accounts
- network service accounts
- local service accounts
ms.assetid: 574245b6-11e2-4849-b0ca-836d673ecd0d
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0680e09548e38760f6ac317fec63152486a4e5fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604902"
---
# <a name="service-account-requirements-for-upgrading-to-sql-server-2008-on-a-domain-controller"></a><span data-ttu-id="4ec68-102">Conditions requises par le compte de service pour la mise à niveau vers SQL Server 2008 sur un contrôleur de domaine</span><span class="sxs-lookup"><span data-stu-id="4ec68-102">Service account requirements for upgrading to SQL Server 2008 on a domain controller</span></span>
  <span data-ttu-id="4ec68-103">Le conseiller de mise à niveau a détecté une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] exécutée sous un service réseau ou un compte de service local sur un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] contrôleur de domaine.</span><span class="sxs-lookup"><span data-stu-id="4ec68-103">Upgrade Advisor detected an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running under a Network Service or Local Service account on a [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] domain controller.</span></span> <span data-ttu-id="4ec68-104">Lorsque [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est installé sur un contrôleur de domaine [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)], les services [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ne peuvent pas être exécutés avec les privilèges d'un compte de service local ou d'un compte de service réseau.</span><span class="sxs-lookup"><span data-stu-id="4ec68-104">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed on a [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] domain controller, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services cannot run under Local Service account or Network Service account privileges.</span></span>  
  
## <a name="component"></a><span data-ttu-id="4ec68-105">Composant</span><span class="sxs-lookup"><span data-stu-id="4ec68-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="4ec68-106">Action corrective</span><span class="sxs-lookup"><span data-stu-id="4ec68-106">Corrective Action</span></span>  
 <span data-ttu-id="4ec68-107">Assurez-vous que tous les comptes de service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sont assignés à des comptes de domaine ou des comptes système locaux.</span><span class="sxs-lookup"><span data-stu-id="4ec68-107">Make sure that all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service accounts are assigned to either Domain accounts or Local System accounts.</span></span> <span data-ttu-id="4ec68-108">Si cette modification n'est pas apportée avant la mise à niveau le programme d'installation se bloque.</span><span class="sxs-lookup"><span data-stu-id="4ec68-108">Failure to make this change before upgrading will block Setup.</span></span> <span data-ttu-id="4ec68-109">Les comptes de service SQL Writer, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et les services Active Directory Helper sont des exceptions car ils sont codés en dur dans le compte de service réseau et ne peuvent pas être modifiés.</span><span class="sxs-lookup"><span data-stu-id="4ec68-109">The service accounts SQL Writer, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and Active Directory Helper services are exceptions because they are hard-coded to the Network Service account and cannot be changed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ec68-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4ec68-110">See Also</span></span>  
 <span data-ttu-id="4ec68-111">[Problèmes de mise à niveau Moteur de base de données](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="4ec68-111">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="4ec68-112">Le conseiller de mise à niveau de SQL Server 2014 &#91;nouveau&#93;</span><span class="sxs-lookup"><span data-stu-id="4ec68-112">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
