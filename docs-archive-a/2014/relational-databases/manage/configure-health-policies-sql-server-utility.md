---
title: Configurer des stratégies de contrôle d’intégrité (utilitaire SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 030aac3b-8901-4c41-91ed-aba96420276c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c5ee466dd2d5bac2ea64364bfc78de8f2f5bea10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602142"
---
# <a name="configure-health-policies-sql-server-utility"></a><span data-ttu-id="9569e-102">Configurer des stratégies de contrôle d'intégrité (utilitaire SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9569e-102">Configure Health Policies (SQL Server Utility)</span></span>
  <span data-ttu-id="9569e-103">Utilisez le tableau de bord de l’utilitaire [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] pour consulter les paramètres des ressources de l’utilitaire [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour les instances gérées de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et les applications de la couche Données.</span><span class="sxs-lookup"><span data-stu-id="9569e-103">Use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility dashboard in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to view [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility resource parameters for managed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and data-tier applications.</span></span> <span data-ttu-id="9569e-104">Pour plus d’informations, consultez [Fonctionnalités et tâches de l’utilitaire SQL Server](sql-server-utility-features-and-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="9569e-104">For more information, see [SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md).</span></span>  
  
 <span data-ttu-id="9569e-105">Pour consulter les résultats d'une stratégie de contrôle d'intégrité de l'utilitaire [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , connectez-vous à un point de contrôle de l'utilitaire de [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9569e-105">To view [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility health policy results, connect to a utility control point from [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span> <span data-ttu-id="9569e-106">Pour plus d’informations, consultez [Utiliser l’Explorateur de l’utilitaire pour gérer l’Utilitaire SQL Server](use-utility-explorer-to-manage-the-sql-server-utility.md).</span><span class="sxs-lookup"><span data-stu-id="9569e-106">For more information, see [Use Utility Explorer to Manage the SQL Server Utility](use-utility-explorer-to-manage-the-sql-server-utility.md).</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="9569e-107">Les stratégies de contrôle d’intégrité de l’utilitaire peuvent être configurées pour des applications de la couche Données et des instances gérées de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9569e-107">Utility health policies can be configured for data-tier applications and managed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="9569e-108">Les stratégies d’intégrité peuvent être définies globalement pour toutes les applications de la couche Données et toutes les instances gérées de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dans l’utilitaire [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Elles peuvent également être définies individuellement pour chaque application de la couche Données et pour chaque instance gérée de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dans l’utilitaire [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9569e-108">Health policies can be defined globally for all data-tier applications and managed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility, or they can be defined individually for each data-tier application and for each managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span>  
  
## <a name="monitoring-policies-for-data-tier-applications"></a><span data-ttu-id="9569e-109">Stratégies de surveillance pour les applications de couche Données</span><span class="sxs-lookup"><span data-stu-id="9569e-109">Monitoring Policies for Data-tier Applications</span></span>  
 <span data-ttu-id="9569e-110">Les stratégies de surexploitation et de sous-exploitation pour les applications de la couche Données de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="9569e-110">Overutilization and underutilization policies for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data-tier applications are as follows:</span></span>  
  
-   <span data-ttu-id="9569e-111">utilisation du processeur par l'application de couche Données ;</span><span class="sxs-lookup"><span data-stu-id="9569e-111">Data-tier application processor utilization.</span></span>  
  
-   <span data-ttu-id="9569e-112">espace de fichier de l'application de couche Données pour les fichiers de base de données ;</span><span class="sxs-lookup"><span data-stu-id="9569e-112">Data-tier application file space for database files.</span></span>  
  
-   <span data-ttu-id="9569e-113">espace de fichier de l'application de couche Données pour les volumes de stockage ;</span><span class="sxs-lookup"><span data-stu-id="9569e-113">Data-tier application file space for storage volumes.</span></span>  
  
-   <span data-ttu-id="9569e-114">utilisation du processeur de l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="9569e-114">Computer processor utilization.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9569e-115">Le volume de stockage et l'utilisation du processeur sont des stratégies en lecture seule pour les applications de la couche Données.</span><span class="sxs-lookup"><span data-stu-id="9569e-115">Storage volume and processor utilization are read-only policies for data-tier applications.</span></span>  
  
 <span data-ttu-id="9569e-116">Pour plus d’informations sur l’affichage ou la modification des stratégies de surveillance globales pour les applications de la couche Données, consultez [Administration de l’utilitaire &#40;utilitaire SQL Server&#41;](../../database-engine/utility-administration-sql-server-utility.md).</span><span class="sxs-lookup"><span data-stu-id="9569e-116">For more information about viewing or changing global monitoring policies for data-tier applications, see [Utility Administration &#40;SQL Server Utility&#41;](../../database-engine/utility-administration-sql-server-utility.md).</span></span>  
  
 <span data-ttu-id="9569e-117">Pour plus d’informations sur l’affichage ou la modification des stratégies de surveillance pour des applications de la couche Données spécifiques, consultez [Détails des applications de la couche Données déployées &#40;utilitaire SQL Server&#41;](../../database-engine/deployed-data-tier-application-details-sql-server-utility.md).</span><span class="sxs-lookup"><span data-stu-id="9569e-117">For more information about viewing or changing monitoring policies for individual data-tier applications, see [Deployed Data-tier Application Details &#40;SQL Server Utility&#41;](../../database-engine/deployed-data-tier-application-details-sql-server-utility.md).</span></span>  
  
## <a name="monitoring-policies-for-managed-instances-of-sql-server"></a><span data-ttu-id="9569e-118">Stratégies de surveillance pour les instances gérées de SQL Server</span><span class="sxs-lookup"><span data-stu-id="9569e-118">Monitoring Policies for Managed Instances of SQL Server</span></span>  
 <span data-ttu-id="9569e-119">Les stratégies de surexploitation et de sous-exploitation pour les instances gérées de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="9569e-119">Overutilization and underutilization policies for managed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are as follows:</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="9569e-120">;</span><span class="sxs-lookup"><span data-stu-id="9569e-120">instance processor utilization.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="9569e-121">pour les fichiers de base de données ;</span><span class="sxs-lookup"><span data-stu-id="9569e-121">instance file space for database files.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="9569e-122">pour les volumes de stockage ;</span><span class="sxs-lookup"><span data-stu-id="9569e-122">instance file space for storage volumes.</span></span>  
  
-   <span data-ttu-id="9569e-123">utilisation du processeur de l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="9569e-123">Computer processor utilization.</span></span>  
  
 <span data-ttu-id="9569e-124">Pour plus d’informations sur l’affichage ou la modification des stratégies de surveillance globales pour les instances gérées de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], consultez [Administration de l’utilitaire &#40;utilitaire SQL Server&#41;](../../database-engine/utility-administration-sql-server-utility.md).</span><span class="sxs-lookup"><span data-stu-id="9569e-124">For more information about viewing or changing global monitoring policies for managed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Utility Administration &#40;SQL Server Utility&#41;](../../database-engine/utility-administration-sql-server-utility.md).</span></span>  
  
 <span data-ttu-id="9569e-125">Pour plus d’informations sur l’affichage ou la modification des stratégies de surveillance globales pour des instances gérées de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] spécifiques, consultez [Détails de l’instance gérée &#40;utilitaire SQL Server&#41;](../../database-engine/managed-instance-details-sql-server-utility.md).</span><span class="sxs-lookup"><span data-stu-id="9569e-125">For more information about viewing or changing monitoring policies for individual managed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Managed Instance Details &#40;SQL Server Utility&#41;](../../database-engine/managed-instance-details-sql-server-utility.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9569e-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9569e-126">See Also</span></span>  
 <span data-ttu-id="9569e-127">[Fonctionnalités et tâches de l'utilitaire SQL Server](sql-server-utility-features-and-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="9569e-127">[SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md) </span></span>  
 [<span data-ttu-id="9569e-128">Réduire le bruit dans les stratégies d’utilisation du processeur &#40;utilitaire SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9569e-128">Reduce Noise in CPU Utilization Policies &#40;SQL Server Utility&#41;</span></span>](reduce-noise-in-cpu-utilization-policies-sql-server-utility.md)  
  
  
