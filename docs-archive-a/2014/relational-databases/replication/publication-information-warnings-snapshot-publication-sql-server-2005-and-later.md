---
title: Informations de publication, avertissements (publication d’instantané, SQL Server 2005 et versions ultérieures) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publicationinfo.warningsandagents.snapshot.f1
ms.assetid: 7aa2eb52-b6b7-4dd3-8483-8ef00d9f0435
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a3ae662a339e1e211ce4f46a588f4d7de65bf5e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702744"
---
# <a name="publication-information-warnings-snapshot-publication-sql-server-2005-and-later"></a><span data-ttu-id="a3d6e-102">Informations de publication, Avertissements (Publication d'instantané, SQL Server 2005 et versions ultérieures)</span><span class="sxs-lookup"><span data-stu-id="a3d6e-102">Publication Information, Warnings (Snapshot Publication, SQL Server 2005 and Later)</span></span>
  <span data-ttu-id="a3d6e-103">L'onglet **Avertissements** est disponible pour les serveurs de distribution qui exécutent [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] et versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="a3d6e-103">The **Warnings** tab is available for Distributors that are running [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions.</span></span> <span data-ttu-id="a3d6e-104">L'onglet **Avertissements** vous permet d'effectuer les tâches suivantes selon la publication sélectionnée :</span><span class="sxs-lookup"><span data-stu-id="a3d6e-104">The **Warnings** tab allows you to perform the following tasks for the selected publication:</span></span>  
  
-   <span data-ttu-id="a3d6e-105">activer les avertissements ;</span><span class="sxs-lookup"><span data-stu-id="a3d6e-105">Enable warnings.</span></span>  
  
-   <span data-ttu-id="a3d6e-106">définir des seuils associés aux avertissements ;</span><span class="sxs-lookup"><span data-stu-id="a3d6e-106">Specify thresholds associated with warnings.</span></span>  
  
-   <span data-ttu-id="a3d6e-107">définir des alertes associées aux avertissements ;</span><span class="sxs-lookup"><span data-stu-id="a3d6e-107">Define alerts associated with warnings.</span></span>  
  
## <a name="warnings-thresholds-and-alerts"></a><span data-ttu-id="a3d6e-108">Avertissements, seuils et alertes</span><span class="sxs-lookup"><span data-stu-id="a3d6e-108">Warnings, Thresholds, and Alerts</span></span>  
 <span data-ttu-id="a3d6e-109">Le moniteur de réplication affiche par défaut des avertissements relatifs aux abonnements non initialisés : l’état **Abonnement non initialisé** s’affiche en tant qu’avertissement dans la colonne **État** des pages incluant des informations propres aux abonnements.</span><span class="sxs-lookup"><span data-stu-id="a3d6e-109">By default, Replication Monitor displays warnings for uninitialized subscriptions: a status of **Uninitialized subscription** is displayed as a warning in the **Status** column of pages that include subscription information.</span></span> <span data-ttu-id="a3d6e-110">Pour les publications de instantanés, vous pouvez également indiquer que l'expiration d'abonnement imminente génère un avertissement en définissant l'option **Avertir si un abonnement expire avant le seuil défini**.</span><span class="sxs-lookup"><span data-stu-id="a3d6e-110">For snapshot publications, you can also specify that imminent subscription expiration results in a warning by setting the option **Warn if a subscription will expire within the threshold**.</span></span> <span data-ttu-id="a3d6e-111">Si le seuil précisé est atteint ou dépassé, l'état de l'abonnement se change alors en **Expire bientôt/Expiré** (à moins qu'un problème dont la priorité est supérieure doit être affiché avant l'état de l'abonnement).</span><span class="sxs-lookup"><span data-stu-id="a3d6e-111">If the specified threshold is met or exceeded, the subscription status is displayed as **Expiring soon/Expired** (unless an issue with a higher priority needs to be displayed).</span></span>  
  
 <span data-ttu-id="a3d6e-112">L'atteinte d'un seuil déclenche un avertissement dans le Moniteur de réplication, mais également une alerte.</span><span class="sxs-lookup"><span data-stu-id="a3d6e-112">In addition to displaying a warning in Replication Monitor, reaching a threshold can also trigger an alert.</span></span> <span data-ttu-id="a3d6e-113">Les alertes sont définies en cliquant sur **Configurer des alertes** et en fournissant les informations nécessaires dans la boîte de dialogue **Configurer les alertes de réplication** .</span><span class="sxs-lookup"><span data-stu-id="a3d6e-113">Alerts are defined by clicking **Configure Alerts** and providing information in the **Configure Replication Alerts** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a3d6e-114">Options</span><span class="sxs-lookup"><span data-stu-id="a3d6e-114">Options</span></span>  
 <span data-ttu-id="a3d6e-115">**Activé**</span><span class="sxs-lookup"><span data-stu-id="a3d6e-115">**Enabled**</span></span>  
 <span data-ttu-id="a3d6e-116">Permet d'activer un avertissement et de définir un seuil.</span><span class="sxs-lookup"><span data-stu-id="a3d6e-116">Select to enable a warning and specify a threshold.</span></span>  
  
 <span data-ttu-id="a3d6e-117">**Avertissement**</span><span class="sxs-lookup"><span data-stu-id="a3d6e-117">**Warning**</span></span>  
 <span data-ttu-id="a3d6e-118">Description de l'avertissement associé à un seuil.</span><span class="sxs-lookup"><span data-stu-id="a3d6e-118">A description of the warning associated with a threshold.</span></span>  
  
 <span data-ttu-id="a3d6e-119">**Seuil**</span><span class="sxs-lookup"><span data-stu-id="a3d6e-119">**Threshold**</span></span>  
 <span data-ttu-id="a3d6e-120">Permet de spécifier une valeur pour le seuil.</span><span class="sxs-lookup"><span data-stu-id="a3d6e-120">Specify a value for the threshold.</span></span>  
  
 <span data-ttu-id="a3d6e-121">**Configurer des alertes**</span><span class="sxs-lookup"><span data-stu-id="a3d6e-121">**Configure Alerts**</span></span>  
 <span data-ttu-id="a3d6e-122">Sélectionnez une ligne dans la grille **Avertissements** , puis cliquez sur **Configurer des alertes** pour ouvrir la boîte de dialogue **Configurer des alertes de réplication** .</span><span class="sxs-lookup"><span data-stu-id="a3d6e-122">Select a row in the **Warnings** grid, and click **Configure Alerts** to launch the **Configure Replication Alerts** dialog box.</span></span> <span data-ttu-id="a3d6e-123">Cette boîte de dialogue permet de définir une alerte associée au seuil et à l'avertissement sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="a3d6e-123">The dialog box allows you to define an alert, which is associated with the selected threshold and warning.</span></span>  
  
 <span data-ttu-id="a3d6e-124">**Ignorer les modifications**</span><span class="sxs-lookup"><span data-stu-id="a3d6e-124">**Discard Changes**</span></span>  
 <span data-ttu-id="a3d6e-125">Permet d'annuler les modifications apportées aux avertissements et aux seuils.</span><span class="sxs-lookup"><span data-stu-id="a3d6e-125">Click to discard any changes to warnings and thresholds.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a3d6e-126">Cliquer sur **Ignorer les modifications** n'affecte en rien les alertes définies dans la boîte de dialogue **Configurer les alertes de réplication** .</span><span class="sxs-lookup"><span data-stu-id="a3d6e-126">Clicking **Discard Changes** does not affect alerts defined in the **Configure Replication Alerts** dialog box.</span></span>  
  
 <span data-ttu-id="a3d6e-127">**Save Changes**</span><span class="sxs-lookup"><span data-stu-id="a3d6e-127">**Save Changes**</span></span>  
 <span data-ttu-id="a3d6e-128">Permet d'enregistrer toute modification apportée aux avertissements et aux seuils.</span><span class="sxs-lookup"><span data-stu-id="a3d6e-128">Click to save any changes to warnings and thresholds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3d6e-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a3d6e-129">See Also</span></span>  
 <span data-ttu-id="a3d6e-130">[Démarrer le Moniteur de réplication](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="a3d6e-130">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="a3d6e-131">[Afficher des informations et effectuer des tâches à l’aide du moniteur de réplication](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="a3d6e-131">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 [<span data-ttu-id="a3d6e-132">Surveillance de la réplication</span><span class="sxs-lookup"><span data-stu-id="a3d6e-132">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
