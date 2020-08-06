---
title: Bases de données autonomes avec les groupes de disponibilité Always On (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- contained database [SQL Server], AlwaysOn Availability Groups
- Availability Groups [SQL Server], interoperability
ms.assetid: cacce3ae-e940-4566-8298-6607c4268e74
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 74c8a0b41ee7224dad83fb41691a4898c15b7b38
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601110"
---
# <a name="contained-databases-with-always-on-availability-groups-sql-server"></a><span data-ttu-id="6835b-102">Bases de données autonomes avec les groupes de disponibilité Always On (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="6835b-102">Contained Databases with Always On Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="6835b-103">Cette rubrique contient des informations sur l'utilisation d'une base de données autonome avec [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6835b-103">This topic contains information about the using a contained database with [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="6835b-104">**Dans cette rubrique :**</span><span class="sxs-lookup"><span data-stu-id="6835b-104">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="6835b-105">Composants requis</span><span class="sxs-lookup"><span data-stu-id="6835b-105">Prerequisites</span></span>](#Prerequisites)  
  
-   [<span data-ttu-id="6835b-106">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="6835b-106">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="6835b-107">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="6835b-107">Prerequisites</span></span>  
  
-   <span data-ttu-id="6835b-108">Avant d'ajouter une base de données autonome à un groupe de disponibilité, vérifiez que l'option de serveur `contained database authentication` est définie sur `1` sur chaque instance de serveur qui héberge un réplica de disponibilité pour le groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="6835b-108">Before adding a contained database to an availability group, ensure that the `contained database authentication` server option is set to `1` on every server instance that hosts an availability replica for the availability group.</span></span> <span data-ttu-id="6835b-109">Pour plus d'informations, consultez [Authentification de la base de données autonome (option de configuration de serveur)](../../configure-windows/contained-database-authentication-server-configuration-option.md) et [Server Configuration Options &#40;SQL Server&#41;](../../configure-windows/server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="6835b-109">For more information, see [contained database authentication Server Configuration Option](../../configure-windows/contained-database-authentication-server-configuration-option.md) and [Server Configuration Options &#40;SQL Server&#41;](../../configure-windows/server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="6835b-110">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="6835b-110">Related Tasks</span></span>  
  
-   [<span data-ttu-id="6835b-111">Options de configuration de serveur &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6835b-111">Server Configuration Options &#40;SQL Server&#41;</span></span>](../../configure-windows/server-configuration-options-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="6835b-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6835b-112">See Also</span></span>  
 <span data-ttu-id="6835b-113">[Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6835b-113">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="6835b-114">Bases de données autonomes</span><span class="sxs-lookup"><span data-stu-id="6835b-114">Contained Databases</span></span>](../../../relational-databases/databases/contained-databases.md)  
  
  
