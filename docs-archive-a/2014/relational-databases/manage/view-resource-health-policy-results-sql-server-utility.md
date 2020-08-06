---
title: Consulter les résultats d’une stratégie de contrôle d’intégrité des ressources (utilitaire SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 80cb14fb-f4c6-4be2-ba17-eb4e4cddd35f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c4ab30ad0e87782f8187370a53747be4cf5d313d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701105"
---
# <a name="view-resource-health-policy-results-sql-server-utility"></a><span data-ttu-id="375a1-102">Consulter les résultats d'une stratégie de contrôle d'intégrité des ressources (Utilitaire SQL Server)</span><span class="sxs-lookup"><span data-stu-id="375a1-102">View Resource Health Policy Results (SQL Server Utility)</span></span>
  <span data-ttu-id="375a1-103">Utilisez le tableau de bord de l’utilitaire dans [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] pour consulter les paramètres des ressources de l’utilitaire [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] pour les instances managées de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] et les applications de la couche Données.</span><span class="sxs-lookup"><span data-stu-id="375a1-103">Use the Utility dashboard in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] to view [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Utility resource parameters for managed instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and data-tier applications.</span></span> <span data-ttu-id="375a1-104">Pour plus d’informations, consultez [Fonctionnalités et tâches de l’utilitaire SQL Server](sql-server-utility-features-and-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="375a1-104">For more information, see [SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md).</span></span>  
  
##  <a name="SSMSProcedure"></a>  
  
#### <a name="view-sql-server-utility-resource-health-policy-results"></a><span data-ttu-id="375a1-105">Consulter les résultats d'une stratégie de contrôle d'intégrité des ressources de l'utilitaire SQL Server.</span><span class="sxs-lookup"><span data-stu-id="375a1-105">View SQL Server Utility resource health policy results.</span></span>  
  
1.  <span data-ttu-id="375a1-106">Dans [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] (SSMS), cliquez sur **Affichage**, puis sur **Explorateur de l’utilitaire** pour afficher le volet Navigation de l’Explorateur de l’utilitaire.</span><span class="sxs-lookup"><span data-stu-id="375a1-106">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] (SSMS), click **View**, then click **Utility Explorer** to view the Utility Explorer navigation pane.</span></span> <span data-ttu-id="375a1-107">Pour afficher le volet de contenu, cliquez sur **Affichage**, puis sur **Contenu de l'Explorateur de l'utilitaire**.</span><span class="sxs-lookup"><span data-stu-id="375a1-107">To view the content pane, click **View**, then click **Utility Explorer Content**.</span></span>  
  
2.  <span data-ttu-id="375a1-108">Dans le volet Navigation, cliquez sur ![](../../database-engine/media/connect-to-utility.gif "Connect_to_Utility")**Se connecter à l’utilitaire**.</span><span class="sxs-lookup"><span data-stu-id="375a1-108">In the navigation pane, click ![](../../database-engine/media/connect-to-utility.gif "Connect_to_Utility")**Connect to Utility**.</span></span> <span data-ttu-id="375a1-109">Si vous n’avez pas créé de point de contrôle d’utilitaire (UCP) ou si vous n’avez pas inscrit d’instances de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ou d’applications de la couche Données dans l’utilitaire [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , consultez [Fonctionnalités et tâches de l’utilitaire SQL Server](sql-server-utility-features-and-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="375a1-109">If you have not created a utility control point (UCP) or if you have not enrolled instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] or data-tier applications into the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Utility, see [SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md).</span></span>  
  
3.  <span data-ttu-id="375a1-110">Cliquez sur le nœud UCP pour afficher les données de synthèse des instances managées de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] et des applications de la couche Données (cliquez avec le bouton droit pour actualiser).</span><span class="sxs-lookup"><span data-stu-id="375a1-110">Click the UCP node to view summary data for managed instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and data-tier applications (right-click to refresh).</span></span> <span data-ttu-id="375a1-111">Les données du tableau de bord sont affichées dans le volet Contenu.</span><span class="sxs-lookup"><span data-stu-id="375a1-111">Dashboard data is displayed in the content pane.</span></span>  
  
4.  <span data-ttu-id="375a1-112">Cliquez sur le nœud **Instances managées** pour afficher les données en mode Liste des instances managées de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (cliquez avec le bouton droit pour actualiser).</span><span class="sxs-lookup"><span data-stu-id="375a1-112">Click the **Managed Instances** node to view list view data for managed instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (right-click to refresh).</span></span> <span data-ttu-id="375a1-113">Les données en mode Liste sont affichées dans le volet Contenu.</span><span class="sxs-lookup"><span data-stu-id="375a1-113">List view data is displayed in the content pane.</span></span>  
  
5.  <span data-ttu-id="375a1-114">Cliquez sur le nœud **Applications de la couche Données déployées** pour afficher les données en mode Liste des applications de la couche Données (cliquez avec le bouton droit pour actualiser).</span><span class="sxs-lookup"><span data-stu-id="375a1-114">Click the **Deployed Data-tier Applications** node to view list view data for data-tier applications (right-click to refresh).</span></span> <span data-ttu-id="375a1-115">Les données en mode Liste sont affichées dans le volet Contenu.</span><span class="sxs-lookup"><span data-stu-id="375a1-115">List view data is displayed in the content pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="375a1-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="375a1-116">See Also</span></span>  
 <span data-ttu-id="375a1-117">[Fonctionnalités et tâches de l'utilitaire SQL Server](sql-server-utility-features-and-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="375a1-117">[SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md) </span></span>  
 <span data-ttu-id="375a1-118">[Réduire le bruit dans les stratégies d’utilisation du processeur &#40;Utilitaire SQL Server&#41;](reduce-noise-in-cpu-utilization-policies-sql-server-utility.md) </span><span class="sxs-lookup"><span data-stu-id="375a1-118">[Reduce Noise in CPU Utilization Policies &#40;SQL Server Utility&#41;](reduce-noise-in-cpu-utilization-policies-sql-server-utility.md) </span></span>  
 <span data-ttu-id="375a1-119">[Détails des applications de la couche Données déployées &#40;utilitaire SQL Server&#41;](../../database-engine/deployed-data-tier-application-details-sql-server-utility.md) </span><span class="sxs-lookup"><span data-stu-id="375a1-119">[Deployed Data-tier Application Details &#40;SQL Server Utility&#41;](../../database-engine/deployed-data-tier-application-details-sql-server-utility.md) </span></span>  
 <span data-ttu-id="375a1-120">[Détails de l’instance gérée &#40;utilitaire SQL Server&#41;](../../database-engine/managed-instance-details-sql-server-utility.md) </span><span class="sxs-lookup"><span data-stu-id="375a1-120">[Managed Instance Details &#40;SQL Server Utility&#41;](../../database-engine/managed-instance-details-sql-server-utility.md) </span></span>  
 [<span data-ttu-id="375a1-121">Administration de l’utilitaire &#40;utilitaire SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="375a1-121">Utility Administration &#40;SQL Server Utility&#41;</span></span>](../../database-engine/utility-administration-sql-server-utility.md)  
  
  
