---
title: Suspendre le traitement des rapports et des abonnements | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- pausing schedules
- subscriptions [Reporting Services], pausing
- report processing [Reporting Services], pausing
- shared data sources [Reporting Services]
- pausing subscription processing
- pausing report processing
- temporarily stopping report processing
- disabling shared data sources
- roles [Reporting Services], modifying
- shared schedules [Reporting Services], pausing
ms.assetid: 3cf9a240-24cc-46d4-bec6-976f82d8f830
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1607637630c507588602dd7e566917ce1eeb6080
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704843"
---
# <a name="pause-report-and-subscription-processing"></a><span data-ttu-id="40a58-102">Suspendre le traitement des rapports et des abonnements</span><span class="sxs-lookup"><span data-stu-id="40a58-102">Pause Report and Subscription Processing</span></span>
  <span data-ttu-id="40a58-103">Vous ne pouvez pas suspendre directement un rapport ou un abonnement.</span><span class="sxs-lookup"><span data-stu-id="40a58-103">You cannot pause a report or subscription directly.</span></span> <span data-ttu-id="40a58-104">Cependant, vous pouvez bloquer le traitement du rapport et de l'abonnement avant le démarrage du processus ou lorsqu'une connexion à une source de données est établie.</span><span class="sxs-lookup"><span data-stu-id="40a58-104">However, you can interrupt report and subscription processing prior to the process starting or when a data source connection is made.</span></span> <span data-ttu-id="40a58-105">Vous pouvez également empêcher le traitement d'un rapport ou d'un abonnement en le rendant inaccessible aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="40a58-105">You can also prevent a report or subscription from processing by making it inaccessible to users.</span></span>  
  
 <span data-ttu-id="40a58-106">Les stratégies suivantes permettent d'empêcher temporairement l'exécution d'un processus.</span><span class="sxs-lookup"><span data-stu-id="40a58-106">The following strategies can be used to temporarily prevent a process from occurring.</span></span>  
  
## <a name="modify-role-assignments-to-prevent-access"></a><span data-ttu-id="40a58-107">Modifier les attributions de rôles afin d'empêcher les accès</span><span class="sxs-lookup"><span data-stu-id="40a58-107">Modify Role Assignments to Prevent Access</span></span>  
 <span data-ttu-id="40a58-108">Le meilleur moyen de rendre un rapport indisponible consiste à supprimer temporairement l'attribution de rôle qui permet d'accéder au rapport.</span><span class="sxs-lookup"><span data-stu-id="40a58-108">The best way to make a report unavailable is to temporarily remove the role assignment that provides access to the report.</span></span> <span data-ttu-id="40a58-109">Cette méthode peut s'appliquer à tous les rapports, quelle que soit la façon dont est établie la connexion à la source de données.</span><span class="sxs-lookup"><span data-stu-id="40a58-109">This approach can be used on all reports regardless of how the data source connection is made.</span></span> <span data-ttu-id="40a58-110">Elle a une incidence uniquement sur le rapport et n'affecte pas la mise en œuvre des autres rapports ou éléments.</span><span class="sxs-lookup"><span data-stu-id="40a58-110">This approach targets only the report, without affecting the operation of other reports or items.</span></span>  
  
 <span data-ttu-id="40a58-111">Pour supprimer une attribution de rôle, ouvrez la page Propriétés de sécurité du rapport dans le Gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="40a58-111">To remove the role assignment, open the Security Properties page of the report in Report Manager.</span></span> <span data-ttu-id="40a58-112">Si le rapport hérite de la sécurité d’un parent, cliquez sur **Modifier la sécurité de l’élément** pour créer une stratégie de sécurité restrictive qui supprime les attributions de rôles offrant un accès étendu. Par exemple, vous pouvez supprimer une attribution de rôle qui fournit un accès à Tout le monde et conserver l’attribution de rôle offrant un accès à un petit groupe d’utilisateurs, comme le groupe Administrateurs.</span><span class="sxs-lookup"><span data-stu-id="40a58-112">If the report inherits security from a parent, you can click **Edit Item Security** to create a restrictive security policy that omits role assignments that provide widespread access (for example, you can remove a role assignment that provides access to Everyone, and keep the role assignment that provides access to a small group of users, such as Administrators).</span></span>  
  
## <a name="disable-a-shared-data-source"></a><span data-ttu-id="40a58-113">Désactiver une source de données partagée</span><span class="sxs-lookup"><span data-stu-id="40a58-113">Disable a Shared Data Source</span></span>  
 <span data-ttu-id="40a58-114">L'un des avantages de l'utilisation de sources de données partagées est que vous pouvez désactiver celles-ci pour empêcher l'exécution d'un rapport ou d'un abonnement piloté par les données.</span><span class="sxs-lookup"><span data-stu-id="40a58-114">One advantage to using shared data sources is that you can disable it to prevent a report or data-driven subscription from running.</span></span> <span data-ttu-id="40a58-115">La désactivation d'une source de données partagée déconnecte le rapport de sa source externe.</span><span class="sxs-lookup"><span data-stu-id="40a58-115">Disabling a shared data source disconnects the report from its external source.</span></span> <span data-ttu-id="40a58-116">Lorsqu'elle est désactivée, la source de données n'est plus disponible pour les rapports et les abonnements qui l'utilisent.</span><span class="sxs-lookup"><span data-stu-id="40a58-116">While it is disabled, the data source is unavailable to all reports and subscriptions that use it.</span></span> <span data-ttu-id="40a58-117">Pour désactiver une source de données partagée, ouvrez-la dans le Gestionnaire de rapports et désactivez la case à cocher **Activer cette source de données** .</span><span class="sxs-lookup"><span data-stu-id="40a58-117">To disable a shared data source, open the data source in Report Manager and clear the **Enable this data source** check box.</span></span>  
  
 <span data-ttu-id="40a58-118">Notez que le rapport continue à se charger même si la source de données n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="40a58-118">Note that the report still loads even if the data source is unavailable.</span></span> <span data-ttu-id="40a58-119">Le rapport ne contient pas de données, mais les utilisateurs dotés des autorisations appropriées peuvent accéder aux pages des propriétés, aux paramètres de sécurité, à l'historique de rapport et aux informations d'abonnement associés à ce rapport.</span><span class="sxs-lookup"><span data-stu-id="40a58-119">The report does not contain data, but users with appropriate permissions can access the property pages, security settings, report history, and subscription information associated with the report.</span></span>  
  
## <a name="pause-a-shared-schedule"></a><span data-ttu-id="40a58-120">Suspendre une planification partagée</span><span class="sxs-lookup"><span data-stu-id="40a58-120">Pause a Shared Schedule</span></span>  
 <span data-ttu-id="40a58-121">Si un rapport ou un abonnement s'exécute à partir d'une planification partagée, vous pouvez suspendre la planification pour empêcher le traitement.</span><span class="sxs-lookup"><span data-stu-id="40a58-121">If a report or subscription runs from a shared schedule, you can pause the schedule to prevent processing.</span></span> <span data-ttu-id="40a58-122">Tous les traitements de rapports et d'abonnements pilotés par la planification sont reportés jusqu'à la reprise de la planification.</span><span class="sxs-lookup"><span data-stu-id="40a58-122">All report and subscription processing that is driven by the schedule is deferred until the schedule is resumed.</span></span> <span data-ttu-id="40a58-123">Pour plus d’informations, consultez [suspendre et reprendre des planifications partagées](schedules.md).</span><span class="sxs-lookup"><span data-stu-id="40a58-123">For more information, see [Pause and Resume Shared Schedules](schedules.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40a58-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="40a58-124">See Also</span></span>  
 <span data-ttu-id="40a58-125">[Serveur de rapports Reporting Services &#40;mode natif&#41;](../report-server/reporting-services-report-server-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="40a58-125">[Reporting Services Report Server &#40;Native Mode&#41;](../report-server/reporting-services-report-server-native-mode.md) </span></span>  
 <span data-ttu-id="40a58-126">[Gestionnaire de rapports &#40;SSRS en mode natif&#41;](../report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="40a58-126">[Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md) </span></span>  
 [<span data-ttu-id="40a58-127">Propriétés de sécurité, éléments de la page &#40;Gestionnaire de rapports&#41;</span><span class="sxs-lookup"><span data-stu-id="40a58-127">Security Properties Page, Items &#40;Report Manager&#41;</span></span>](../security-properties-page-items-report-manager.md)  
  
  
