---
title: Mettre en cache un rapport (Gestionnaire de rapports) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- report execution properties [Reporting Services]
- cache [Reporting Services]
- cached reports [Reporting Services]
- schedules [Reporting Services], report expiration
- expiration [Reporting Services]
ms.assetid: 723d1cb0-c2e7-4763-8690-a6a7a8bbbb90
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2e359e6c7a40b267979137ef2b3a285667a6fdb2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611564"
---
# <a name="cache-a-report-report-manager"></a><span data-ttu-id="09684-102">mettre en cache un rapport (Gestionnaire de rapports)</span><span class="sxs-lookup"><span data-stu-id="09684-102">Cache a Report (Report Manager)</span></span>
  <span data-ttu-id="09684-103">L'un des moyens d'améliorer les performances est de configurer les propriétés de mise en cache d'un rapport.</span><span class="sxs-lookup"><span data-stu-id="09684-103">One way to improve performance is to configure caching properties for a report.</span></span> <span data-ttu-id="09684-104">Lorsqu'un rapport est mis en cache, une copie du rapport rendu est enregistrée pour une courte durée.</span><span class="sxs-lookup"><span data-stu-id="09684-104">When a report is cached, a copy of the rendered report is saved for a short period of time.</span></span> <span data-ttu-id="09684-105">Le premier utilisateur qui demande le rapport doit attendre que son traitement soit entièrement terminé avant de pouvoir l'afficher.</span><span class="sxs-lookup"><span data-stu-id="09684-105">The first user who requests the report must wait for all processing to complete before viewing the report.</span></span> <span data-ttu-id="09684-106">Les utilisateurs ultérieurs qui demandent le rapport pendant la période de mise en cache peuvent le consulter immédiatement, car son traitement a déjà eu lieu.</span><span class="sxs-lookup"><span data-stu-id="09684-106">Subsequent users who request the report within the caching period can view it right away because processing has already occurred.</span></span>  
  
 <span data-ttu-id="09684-107">Il existe des restrictions concernant les types de rapports que vous pouvez mettre en cache.</span><span class="sxs-lookup"><span data-stu-id="09684-107">There are restrictions on the types of reports that you can cache.</span></span> <span data-ttu-id="09684-108">Par exemple, un rapport ne peut pas être mis en cache si sa sortie varie selon l'identité de l'utilisateur, ou si les données sont récupérées à l'aide du jeton de sécurité de l'utilisateur qui demande le rapport.</span><span class="sxs-lookup"><span data-stu-id="09684-108">For example, a report cannot be cached if report output varies based on the user identity or if data is retrieved using the security token of the user who requests the report.</span></span> <span data-ttu-id="09684-109">Pour plus d’informations, consultez [Mise en cache de rapports &#40;SSRS&#41;](caching-reports-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="09684-109">For more information, see [Caching Reports &#40;SSRS&#41;](caching-reports-ssrs.md).</span></span>  
  
### <a name="to-schedule-the-expiration-of-a-cached-report"></a><span data-ttu-id="09684-110">Pour planifier l'expiration d'un rapport mis en cache</span><span class="sxs-lookup"><span data-stu-id="09684-110">To schedule the expiration of a cached report</span></span>  
  
1.  <span data-ttu-id="09684-111">Démarrez le [Gestionnaire de rapports &#40;SSRS en mode natif&#41;](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="09684-111">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="09684-112">Dans le Gestionnaire de rapports, parcourez l'arborescence jusqu'à la page **Contenu** .</span><span class="sxs-lookup"><span data-stu-id="09684-112">In Report Manager, navigate to the **Contents** page.</span></span> <span data-ttu-id="09684-113">Accédez au rapport pour lequel vous souhaitez définir des propriétés de mise en cache, pointez sur l'élément et cliquez sur la flèche déroulante.</span><span class="sxs-lookup"><span data-stu-id="09684-113">Navigate to the report for which you want to set caching properties, hover over the item, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="09684-114">Dans le menu déroulant, cliquez sur **Gérer**.</span><span class="sxs-lookup"><span data-stu-id="09684-114">In the drop-down menu, click **Manage**.</span></span>  
  
4.  <span data-ttu-id="09684-115">Dans le cadre de gauche, cliquez sur **Options de traitement**.</span><span class="sxs-lookup"><span data-stu-id="09684-115">In the left frame, click the **Processing Options**.</span></span>  
  
5.  <span data-ttu-id="09684-116">Dans la page qui s’affiche, sélectionnez **Toujours exécuter ce rapport avec les données les plus récentes**.</span><span class="sxs-lookup"><span data-stu-id="09684-116">On the page, select **Always run this report with the most recent data**.</span></span>  
  
6.  <span data-ttu-id="09684-117">Sélectionnez l’une des deux options de cache suivantes et configurez l’expiration comme suit :</span><span class="sxs-lookup"><span data-stu-id="09684-117">Select one of the following two cache options and configure expiration as follows:</span></span>  
  
    -   <span data-ttu-id="09684-118">Pour configurer l'expiration d'une copie mise en cache après l'écoulement d'une durée particulière, cliquez sur **Mettre en cache une copie temporaire du rapport. Faire expirer la copie du rapport après un certain nombre de minutes**.</span><span class="sxs-lookup"><span data-stu-id="09684-118">To configure a cached copy to expire after a particular time period, click **Cache a temporary copy of the report. Expire copy of report after a number of minutes**.</span></span> <span data-ttu-id="09684-119">Tapez le nombre de minutes pour l'expiration du rapport.</span><span class="sxs-lookup"><span data-stu-id="09684-119">Type the number of minutes for report expiration.</span></span>  
  
    -   <span data-ttu-id="09684-120">Pour configurer l’expiration d’une copie mise en cache selon une planification, cliquez sur **Mettre en cache une copie temporaire du rapport. Faire expirer la copie du rapport selon la planification suivante.**</span><span class="sxs-lookup"><span data-stu-id="09684-120">To configure a cached copy to expire on a schedule, click **Cache a temporary copy of the report. Expire copy of report on the following schedule.**</span></span> <span data-ttu-id="09684-121">Cliquez sur **Configurer**ou sélectionnez une planification partagée pour contrôler l’expiration du rapport.</span><span class="sxs-lookup"><span data-stu-id="09684-121">Click **Configure**, or select a shared schedule to control report expiration</span></span>  
  
7.  <span data-ttu-id="09684-122">Cliquez sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="09684-122">Click **Apply**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09684-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="09684-123">See Also</span></span>  
 <span data-ttu-id="09684-124">[Définir les propriétés de traitement d’un rapport](set-report-processing-properties.md) </span><span class="sxs-lookup"><span data-stu-id="09684-124">[Set Report Processing Properties](set-report-processing-properties.md) </span></span>  
 [<span data-ttu-id="09684-125">Mise en cache de rapports &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="09684-125">Caching Reports &#40;SSRS&#41;</span></span>](caching-reports-ssrs.md)  
  
  
