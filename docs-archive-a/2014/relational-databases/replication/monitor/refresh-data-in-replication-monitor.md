---
title: Actualiser des données dans le moniteur de réplication | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- refreshing data
ms.assetid: e9582244-7d00-45f4-be16-020a65c76a5e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2f097dea21b06540293e9b60b7de9315323b4168
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709191"
---
# <a name="refresh-data-in-replication-monitor"></a><span data-ttu-id="6aa3a-102">Actualiser des données dans le Moniteur de réplication</span><span class="sxs-lookup"><span data-stu-id="6aa3a-102">Refresh Data in Replication Monitor</span></span>
  <span data-ttu-id="6aa3a-103">Dans le moniteur de réplication, la fenêtre principale et les fenêtres de détails (ces fenêtres lancées à partir de la fenêtre principale) peuvent être actualisées automatiquement ou manuellement.</span><span class="sxs-lookup"><span data-stu-id="6aa3a-103">In Replication Monitor, the main window and detail windows (those windows launched from the main window) can be refreshed automatically or manually.</span></span> <span data-ttu-id="6aa3a-104">Pour actualiser une fenêtre manuellement, appuyez sur la touche F5.</span><span class="sxs-lookup"><span data-stu-id="6aa3a-104">To refresh a window manually, press F5.</span></span> <span data-ttu-id="6aa3a-105">Par défaut, la fenêtre principale est actualisée automatiquement toutes les cinq secondes ; la fréquence peut être personnalisée pour chaque serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="6aa3a-105">By default, the main window is refreshed automatically every five seconds; the rate can be customized for each Publisher.</span></span>  
  
 <span data-ttu-id="6aa3a-106">Les données affichées dans le moniteur de réplication sont recherchées dans une mémoire cache. Pour plus d’informations sur les relations entre la mémoire cache et l’actualisation du moniteur de réplication, consultez [Mise en cache, actualisation et performances du moniteur de réplication](caching-refresh-and-replication-monitor-performance.md).</span><span class="sxs-lookup"><span data-stu-id="6aa3a-106">The data displayed in Replication Monitor is queried from a cache; for information about the relationship between the cache and refreshing Replication Monitor, see [Caching, Refresh, and Replication Monitor Performance](caching-refresh-and-replication-monitor-performance.md).</span></span> <span data-ttu-id="6aa3a-107">Pour plus d’informations sur le démarrage du Moniteur de réplication, consultez [Démarrer le Moniteur de réplication](start-the-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="6aa3a-107">For information about starting Replication Monitor, see [Start the Replication Monitor](start-the-replication-monitor.md).</span></span>  
  
### <a name="to-set-refresh-options-for-replication-monitor"></a><span data-ttu-id="6aa3a-108">Pour définir les options d'actualisation pour le moniteur de réplication</span><span class="sxs-lookup"><span data-stu-id="6aa3a-108">To set refresh options for Replication Monitor</span></span>  
  
1.  <span data-ttu-id="6aa3a-109">Cliquez avec le bouton droit dans le volet gauche du moniteur de réplication, puis cliquez sur **Paramètres du serveur de publication**.</span><span class="sxs-lookup"><span data-stu-id="6aa3a-109">Right-click a Publisher in the left pane of Replication Monitor, and then click **Publisher Settings**.</span></span>  
  
2.  <span data-ttu-id="6aa3a-110">Dans la boîte de dialogue **Paramètres du serveur de publication** , définissez les options **Actualisation automatique** et **Fréquence d'actualisation** .</span><span class="sxs-lookup"><span data-stu-id="6aa3a-110">In the **Publisher Settings** dialog box, set the **Auto refresh** and **Refresh rate** options.</span></span> <span data-ttu-id="6aa3a-111">Le paramètre **Actualisation automatique** affecte la fenêtre principale du moniteur de réplication.</span><span class="sxs-lookup"><span data-stu-id="6aa3a-111">The **Auto refresh** setting affects the main window in Replication Monitor.</span></span> <span data-ttu-id="6aa3a-112">Le paramètre **Fréquence d'actualisation** affecte également toutes les fenêtres de détails qui sont paramétrées pour s'actualiser automatiquement (les modifications du paramètre affectent seulement les fenêtres de détails ouvertes après la modification).</span><span class="sxs-lookup"><span data-stu-id="6aa3a-112">The **Refresh rate** setting also affects any detail windows that are set to refresh automatically (changes to the setting only affect the detail windows opened after the change).</span></span>  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="to-specify-that-a-detail-window-should-automatically-refresh"></a><span data-ttu-id="6aa3a-113">Pour spécifier qu'une fenêtre de détails doit s'actualiser automatiquement</span><span class="sxs-lookup"><span data-stu-id="6aa3a-113">To specify that a detail window should automatically refresh</span></span>  
  
1.  <span data-ttu-id="6aa3a-114">Ouvrez une fenêtre de détails dans le moniteur de réplication.</span><span class="sxs-lookup"><span data-stu-id="6aa3a-114">Open a detail window in Replication Monitor.</span></span> <span data-ttu-id="6aa3a-115">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="6aa3a-115">For example:</span></span>  
  
    1.  <span data-ttu-id="6aa3a-116">Développez un groupe de serveurs de publication dans le volet gauche, développez un serveur de publication, puis cliquez sur une publication.</span><span class="sxs-lookup"><span data-stu-id="6aa3a-116">Expand a Publisher group in the left pane, expand a Publisher, and then click a publication.</span></span>  
  
    2.  <span data-ttu-id="6aa3a-117">Cliquez sur l'onglet **Tous les abonnements** .</span><span class="sxs-lookup"><span data-stu-id="6aa3a-117">Click the **All Subscriptions** tab.</span></span>  
  
    3.  <span data-ttu-id="6aa3a-118">Cliquez avec le bouton droit sur un abonnement, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="6aa3a-118">Right-click a subscription, and then click **View Details**.</span></span>  
  
2.  <span data-ttu-id="6aa3a-119">Dans la fenêtre **Détail de l’abonnement \<SubscriptionName>** , cliquez sur **Action**, puis cliquez sur **Actualisation automatique**.</span><span class="sxs-lookup"><span data-stu-id="6aa3a-119">In the **Subscription \<SubscriptionName>** detail window, click **Action**, and then click **Auto Refresh**.</span></span> <span data-ttu-id="6aa3a-120">La fréquence d'actualisation est déterminée par le paramètre **Fréquence d'actualisation** dans la boîte de dialogue **Paramètres du serveur de publication** .</span><span class="sxs-lookup"><span data-stu-id="6aa3a-120">The refresh rate is determined by the **Refresh rate** setting in the **Publisher Settings** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6aa3a-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6aa3a-121">See Also</span></span>  
 [<span data-ttu-id="6aa3a-122">Surveillance de la réplication</span><span class="sxs-lookup"><span data-stu-id="6aa3a-122">Monitoring Replication</span></span>](../monitoring-replication.md)  
  
  
