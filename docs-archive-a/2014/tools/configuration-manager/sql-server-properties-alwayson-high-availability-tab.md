---
title: Propriétés de SQL Server (onglet haute disponibilité AlwaysOn) | Microsoft Docs
description: Découvrez comment activer ou désactiver la fonctionnalité groupes de disponibilité AlwaysOn dans SQL Server 2014. Affichez les conditions préalables que l’instance de serveur doit remplir pour cette fonctionnalité.
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: d8630923-a600-4f1c-aca1-027453a3ec82
author: mikeraymsft
ms.author: mikeray
ms.openlocfilehash: 3939b40a334746e9ee96441338e2e50791987103
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703659"
---
# <a name="sql-server-properties-alwayson-high-availability-tab"></a><span data-ttu-id="1c7a7-104">Propriétés de SQL Server (onglet Haute disponibilité AlwaysOn)</span><span class="sxs-lookup"><span data-stu-id="1c7a7-104">SQL Server Properties (AlwaysOn High Availability Tab)</span></span>
  <span data-ttu-id="1c7a7-105">Utilisez l'onglet **Haute disponibilité AlwaysOn** de la boîte de dialogue **Propriétés de SQL Server** du Gestionnaire de configurations [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour activer ou désactiver la fonctionnalité Groupes de disponibilité AlwaysOn de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1c7a7-105">Use the **AlwaysOn High Availability** tab of the **SQL Server Properties** dialog box in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager to enable or disable the AlwaysOn Availability Groups feature in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="1c7a7-106">L'activation de Groupes de disponibilité AlwaysOn est une condition préalable nécessaire pour une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour utiliser les groupes de disponibilité comme solution de haute disponibilité et de récupération d'urgence.</span><span class="sxs-lookup"><span data-stu-id="1c7a7-106">Enabling AlwaysOn Availability Groups is a prerequisite for an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to use availability groups as a high availability and disaster recovery solution.</span></span>  
  
##  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="1c7a7-107">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="1c7a7-107">Prerequisites</span></span>  
 <span data-ttu-id="1c7a7-108">Pour être activée pour Groupes de disponibilité AlwaysOn, une instance de serveur doit respecter la configuration requise suivante :</span><span class="sxs-lookup"><span data-stu-id="1c7a7-108">To be enabled for AlwaysOn Availability Groups, a server instance must meet the following prerequisites:</span></span>  
  
-   <span data-ttu-id="1c7a7-109">L'instance de serveur doit résider sur un nœud de Clustering de basculement Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="1c7a7-109">The server instance must reside on a Windows Server Failover Clustering (WSFC) node.</span></span>  
  
-   <span data-ttu-id="1c7a7-110">Pour appartenir au même groupe de disponibilité, les instances doivent être dans le même cluster WSFC.</span><span class="sxs-lookup"><span data-stu-id="1c7a7-110">To be in the same availability group, instances must be in the same WSFC cluster.</span></span> <span data-ttu-id="1c7a7-111">Un groupe de disponibilité ne peut pas s'étendre sur plusieurs clusters WSFC.</span><span class="sxs-lookup"><span data-stu-id="1c7a7-111">An availability group cannot span WSFC clusters.</span></span>  
  
-   <span data-ttu-id="1c7a7-112">L'instance du serveur doit exécuter une édition de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui prend en charge [!INCLUDE[ssHADR](../../includes/sshadr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1c7a7-112">The server instance must be running an edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that supports [!INCLUDE[ssHADR](../../includes/sshadr-md.md)].</span></span>  
  
-   <span data-ttu-id="1c7a7-113">Activez Groupes de disponibilité AlwaysOn pour une seule instance de serveur à la fois.</span><span class="sxs-lookup"><span data-stu-id="1c7a7-113">Enable AlwaysOn Availability Groups for only one server instance at a time.</span></span> <span data-ttu-id="1c7a7-114">Après avoir activé Groupes de disponibilité AlwaysOn, attendez le redémarrage du service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] avant d'activer l'instance de serveur suivante.</span><span class="sxs-lookup"><span data-stu-id="1c7a7-114">After enabling AlwaysOn Availability Groups, wait until the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service has restarted before you enable the next server instance.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1c7a7-115">Pour plus d’informations sur la prise en charge des fonctionnalités et sur les conditions préalables, restrictions et recommandations supplémentaires pour [!INCLUDE[ssHADR](../../includes/sshadr-md.md)], consultez la documentation en ligne de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1c7a7-115">For information about feature support and for information about additional prerequisites, restrictions, and recommendations for [!INCLUDE[ssHADR](../../includes/sshadr-md.md)], see [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Books Online.</span></span>  
  
## <a name="dialog-options"></a><span data-ttu-id="1c7a7-116">Options de boîte de dialogue</span><span class="sxs-lookup"><span data-stu-id="1c7a7-116">Dialog Options</span></span>  
 <span data-ttu-id="1c7a7-117">**Nom du cluster de basculement Windows**</span><span class="sxs-lookup"><span data-stu-id="1c7a7-117">**Windows failover cluster name**</span></span>  
 <span data-ttu-id="1c7a7-118">Affiche le nom du cluster WSFC dans lequel l'ordinateur local est un nœud.</span><span class="sxs-lookup"><span data-stu-id="1c7a7-118">Displays the name of the WSFC cluster in which the local computer is a node.</span></span>  
  
 <span data-ttu-id="1c7a7-119">**Activer groupes de disponibilité AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="1c7a7-119">**Enable AlwaysOn Availability Groups**</span></span>  
 <span data-ttu-id="1c7a7-120">Utilisez cette case à cocher pour activer ou désactiver Groupes de disponibilité AlwaysOn sur cette instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], comme suit :</span><span class="sxs-lookup"><span data-stu-id="1c7a7-120">Use this check box to enable or disable AlwaysOn Availability Groups on this instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], as follows:</span></span>  
  
-   <span data-ttu-id="1c7a7-121">Si cette case à cocher est vide, Groupes de disponibilité AlwaysOn est désactivé.</span><span class="sxs-lookup"><span data-stu-id="1c7a7-121">If this check box is empty, AlwaysOn Availability Groups is currently disabled.</span></span> <span data-ttu-id="1c7a7-122">Pour activer Groupes de disponibilité AlwaysOn, activez cette case à cocher, cliquez sur **OK**et redémarrez manuellement le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1c7a7-122">To enable AlwaysOn Availability Groups, select this check box, click **OK**, and manually restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  
-   <span data-ttu-id="1c7a7-123">Si cette case à cocher est déjà sélectionnée, Groupes de disponibilité AlwaysOn est activé.</span><span class="sxs-lookup"><span data-stu-id="1c7a7-123">If this check box is already selected, AlwaysOn Availability Groups is currently enabled.</span></span> <span data-ttu-id="1c7a7-124">Pour désactiver Groupes de disponibilité AlwaysOn, désactivez la case à cocher et cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="1c7a7-124">To disable AlwaysOn Availability Groups, uncheck the check box and click **OK**.</span></span> <span data-ttu-id="1c7a7-125">Cela entraîne le redémarrage de l'instance de serveur.</span><span class="sxs-lookup"><span data-stu-id="1c7a7-125">This causes the server instance to restart.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="1c7a7-126">Après avoir désactivé Groupes de disponibilité AlwaysOn, supprimez les réplicas de disponibilité locales de l'instance de serveur.</span><span class="sxs-lookup"><span data-stu-id="1c7a7-126">After disabling AlwaysOn Availability Groups, you should remove any local availability replicas from the server instance.</span></span> <span data-ttu-id="1c7a7-127">Si vous supprimez la dernière réplica d'un groupe de disponibilité donné, supprimez également le groupe.</span><span class="sxs-lookup"><span data-stu-id="1c7a7-127">If you remove the last replica of a given availability group, you should also remove the group.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="1c7a7-128">Liste d’éléments d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="1c7a7-128">UI element list</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1c7a7-129">Pour plus d'informations sur le suivi après la désactivation de Groupes de disponibilité AlwaysOn et la procédure à suivre pour créer et configurer des groupes de disponibilité, consultez la documentation en ligne de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1c7a7-129">For more information about follow up after you disable AlwaysOn Availability Groups and for information about how to create and configure availability groups, see [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Books Online.</span></span>  
  
  
