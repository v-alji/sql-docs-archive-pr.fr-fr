---
title: Réplication de bases de données hétérogènes | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- heterogeneous database replication, about heterogeneous database replication
- replication [SQL Server], heterogeneous database replication
- heterogeneous database replication
ms.assetid: 3fd983ad-e206-45db-9054-417c9b5bb815
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d8988a425bc9519d43b8100e4cd34418114edae1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705012"
---
# <a name="heterogeneous-database-replication"></a><span data-ttu-id="33a93-102">réplication de bases de données hétérogènes</span><span class="sxs-lookup"><span data-stu-id="33a93-102">Heterogeneous Database Replication</span></span>
  [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="33a93-103">prend en charge les scénarios divers suivants pour la réplication transactionnelle et d'instantané :</span><span class="sxs-lookup"><span data-stu-id="33a93-103">supports the following heterogeneous scenarios for transactional and snapshot replication:</span></span>  
  
-   <span data-ttu-id="33a93-104">Publication de données d'Oracle vers [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="33a93-104">Publishing data from Oracle to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="33a93-105">Publication de données de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] vers des Abonnés non[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="33a93-105">Publishing data from [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Subscribers.</span></span>  
  
 <span data-ttu-id="33a93-106">La réplication hétérogène sur les abonnés non SQL Server est déconseillée.</span><span class="sxs-lookup"><span data-stu-id="33a93-106">Heterogeneous replication to non-SQL Server subscribers is deprecated.</span></span> <span data-ttu-id="33a93-107">La publication Oracle est déconseillée.</span><span class="sxs-lookup"><span data-stu-id="33a93-107">Oracle Publishing is deprecated.</span></span> <span data-ttu-id="33a93-108">Pour déplacer des données, créez des solutions à l'aide de la Capture de données modifiées et [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="33a93-108">To move data, create solutions using change data capture and [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span></span>  
  
> [!CAUTION]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../../includes/ssnotedepfutureavoid-md.md)]  
  
## <a name="publishing-data-from-oracle"></a><span data-ttu-id="33a93-109">Publication de données à partir d'Oracle</span><span class="sxs-lookup"><span data-stu-id="33a93-109">Publishing Data from Oracle</span></span>  
 <span data-ttu-id="33a93-110">Vous pouvez utiliser [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] pour publier des données à partir d'Oracle avec la plupart des fonctions et la même facilité qu'offre la réplication transactionnelle et d'instantané de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="33a93-110">You can use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to publish data from Oracle with most of the same features and ease-of-use as [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] snapshot and transactional replication.</span></span> <span data-ttu-id="33a93-111">La publication de données à partir d'Oracle est idéale pour les scénarios suivants :</span><span class="sxs-lookup"><span data-stu-id="33a93-111">Publishing data from Oracle is ideal for the following scenarios:</span></span>  
  
|<span data-ttu-id="33a93-112">Scénario</span><span class="sxs-lookup"><span data-stu-id="33a93-112">Scenario</span></span>|<span data-ttu-id="33a93-113">Description</span><span class="sxs-lookup"><span data-stu-id="33a93-113">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="33a93-114">Déploiements d'applications[!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework</span><span class="sxs-lookup"><span data-stu-id="33a93-114">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework application deployments</span></span>|<span data-ttu-id="33a93-115">Développez avec [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Studio et [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] en exploitant des données répliquées à partir d’une base de données non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="33a93-115">Develop with [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Studio and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] while operating on data replicated from a non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database.</span></span>|  
|<span data-ttu-id="33a93-116">Serveurs de secours pour l'entreposage des données</span><span class="sxs-lookup"><span data-stu-id="33a93-116">Data warehousing staging servers</span></span>|<span data-ttu-id="33a93-117">Gardez les bases de données intermédiaires [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] synchronisées avec une base de données non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="33a93-117">Keep [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] staging databases synchronized with a non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database.</span></span>|  
|<span data-ttu-id="33a93-118">Migration vers [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33a93-118">Migration to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]</span></span>|<span data-ttu-id="33a93-119">Testez votre application en temps réel sur [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] tout en répliquant les changements du système source.</span><span class="sxs-lookup"><span data-stu-id="33a93-119">Test your application in real time against [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] while replicating the source system's changes.</span></span> <span data-ttu-id="33a93-120">Basculez vers [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] lorsque vous êtes satisfait de la migration.</span><span class="sxs-lookup"><span data-stu-id="33a93-120">Switch to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] when satisfied with the migration.</span></span>|  
  
 <span data-ttu-id="33a93-121">Pour plus d’informations, consultez [Présentation de la publication Oracle](oracle-publishing-overview.md).</span><span class="sxs-lookup"><span data-stu-id="33a93-121">For more information, see [Oracle Publishing Overview](oracle-publishing-overview.md).</span></span>  
  
## <a name="publishing-data-to-non-sql-server-subscribers"></a><span data-ttu-id="33a93-122">Publication de données vers des Abonnés non-SQL Server</span><span class="sxs-lookup"><span data-stu-id="33a93-122">Publishing Data to Non-SQL Server Subscribers</span></span>  
 <span data-ttu-id="33a93-123">Les bases de données non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] sont prises en charge en tant qu'Abonnés aux publications transactionnelles et d'instantané :</span><span class="sxs-lookup"><span data-stu-id="33a93-123">The following non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] databases are supported as Subscribers to snapshot and transactional publications:</span></span>  
  
-   <span data-ttu-id="33a93-124">Oracle pour toutes les plateformes prises en charge par Oracle.</span><span class="sxs-lookup"><span data-stu-id="33a93-124">Oracle for all platforms that Oracle supports.</span></span>  
  
-   <span data-ttu-id="33a93-125">IBM DB2 pour AS400, MVS, Unix, Linux et Windows.</span><span class="sxs-lookup"><span data-stu-id="33a93-125">IBM DB2 for AS400, MVS, Unix, Linux, and Windows.</span></span>  
  
 <span data-ttu-id="33a93-126">Pour plus d’informations, consultez [Non-SQL Server Subscribers](non-sql-server-subscribers.md).</span><span class="sxs-lookup"><span data-stu-id="33a93-126">For more information, see [Non-SQL Server Subscribers](non-sql-server-subscribers.md).</span></span>  
  
  
