---
title: Serveurs de publications non-SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- heterogeneous database replication, non-SQL Server Publishers
- non-SQL Server Publishers
- heterogeneous data sources, non-SQL Server Publishers
- Publishers [SQL Server replication], Oracle
ms.assetid: 08a160a6-33be-46b5-bc7b-d53180d8bdf1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f15f07dbf294d697afd385318f3dbf1447c8e2d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600802"
---
# <a name="non-sql-server-publishers"></a><span data-ttu-id="5fe86-102">serveurs de publications non-SQL Server</span><span class="sxs-lookup"><span data-stu-id="5fe86-102">Non-SQL Server Publishers</span></span>
  <span data-ttu-id="5fe86-103">La publication de données à partir de sources non- [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] vous permet de consolider les données dans [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5fe86-103">Publishing data from non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] sources allows you to consolidate data in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="5fe86-104">peut s'abonner à des données transactionnelles ou à des données d'instantané à partir d'une base de données Oracle.</span><span class="sxs-lookup"><span data-stu-id="5fe86-104">can subscribe to snapshot or transactional data published from an Oracle database.</span></span> <span data-ttu-id="5fe86-105">Pour plus d’informations sur la publication à partir d’Oracle, consultez [Présentation de la publication Oracle](oracle-publishing-overview.md).</span><span class="sxs-lookup"><span data-stu-id="5fe86-105">For more information about publishing from Oracle, see [Oracle Publishing Overview](oracle-publishing-overview.md).</span></span>  
  
 <span data-ttu-id="5fe86-106">La réplication hétérogène sur les abonnés non SQL Server est déconseillée.</span><span class="sxs-lookup"><span data-stu-id="5fe86-106">Heterogeneous replication to non-SQL Server subscribers is deprecated.</span></span> <span data-ttu-id="5fe86-107">La publication Oracle est déconseillée.</span><span class="sxs-lookup"><span data-stu-id="5fe86-107">Oracle Publishing is deprecated.</span></span> <span data-ttu-id="5fe86-108">Pour déplacer des données, créez des solutions à l'aide de la Capture de données modifiées et [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5fe86-108">To move data, create solutions using change data capture and [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span></span>  
  
> [!CAUTION]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../../includes/ssnotedepfutureavoid-md.md)]  
  
 <span data-ttu-id="5fe86-109">La publication à partir de bases de données non[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] est idéale pour les scénarios suivants :</span><span class="sxs-lookup"><span data-stu-id="5fe86-109">Publishing from non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] databases is ideal for the following scenarios:</span></span>  
  
|<span data-ttu-id="5fe86-110">Scénario</span><span class="sxs-lookup"><span data-stu-id="5fe86-110">Scenario</span></span>|<span data-ttu-id="5fe86-111">Description</span><span class="sxs-lookup"><span data-stu-id="5fe86-111">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="5fe86-112">Déploiements d'applications[!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework</span><span class="sxs-lookup"><span data-stu-id="5fe86-112">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework application deployments</span></span>|<span data-ttu-id="5fe86-113">Développez avec [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Studio et [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] en exploitant des données répliquées à partir d’une base de données non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5fe86-113">Develop with [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Studio and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] while operating on data replicated from a non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database.</span></span>|  
|<span data-ttu-id="5fe86-114">Serveurs de secours pour l'entreposage des données</span><span class="sxs-lookup"><span data-stu-id="5fe86-114">Data warehousing staging servers</span></span>|<span data-ttu-id="5fe86-115">Gardez les bases de données intermédiaires [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] synchronisées avec une base de données non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5fe86-115">Keep [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] staging databases synchronized with a non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database.</span></span>|  
|<span data-ttu-id="5fe86-116">Migration vers [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5fe86-116">Migration to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]</span></span>|<span data-ttu-id="5fe86-117">Testez votre application en temps réel sur [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] tout en répliquant les changements du système source.</span><span class="sxs-lookup"><span data-stu-id="5fe86-117">Test your application in real time against [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] while replicating the source system's changes.</span></span> <span data-ttu-id="5fe86-118">Basculez vers [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] lorsque vous êtes satisfait de la migration.</span><span class="sxs-lookup"><span data-stu-id="5fe86-118">Switch to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] when satisfied with the migration.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5fe86-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5fe86-119">See Also</span></span>  
 [<span data-ttu-id="5fe86-120">Heterogeneous Database Replication</span><span class="sxs-lookup"><span data-stu-id="5fe86-120">Heterogeneous Database Replication</span></span>](heterogeneous-database-replication.md)  
  
  
