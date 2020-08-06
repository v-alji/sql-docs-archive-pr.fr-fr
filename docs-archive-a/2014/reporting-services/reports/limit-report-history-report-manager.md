---
title: Limiter l’historique de rapport (Gestionnaire de rapports) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- viewing report history
- report history [Reporting Services], viewing history
- report history [Reporting Services], configuring history
- historical data [Reporting Services]
- displaying report history
ms.assetid: 8e255792-d9ef-496f-a26c-9e969c1209a0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 01318b1e1ccf0b0bf4512ab57de90cbf5ebc7365
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697463"
---
# <a name="limit-report-history-report-manager"></a><span data-ttu-id="28cfd-102">Limiter l'historique de rapport (Gestionnaire de rapports)</span><span class="sxs-lookup"><span data-stu-id="28cfd-102">Limit Report History (Report Manager)</span></span>
  <span data-ttu-id="28cfd-103">L'historique de rapport est un ensemble d'instantanés de rapport que vous créez au fil du temps.</span><span class="sxs-lookup"><span data-stu-id="28cfd-103">Report history is a collection of report snapshots that you create over time.</span></span> <span data-ttu-id="28cfd-104">Vous pouvez soit créer l'historique de rapport à la demande, soit planifier la fréquence à laquelle un instantané est créée et ajoutée à l'historique de rapport.</span><span class="sxs-lookup"><span data-stu-id="28cfd-104">You can create report history on demand, or schedule how often a snapshot is created and added to report history.</span></span>  
  
 <span data-ttu-id="28cfd-105">L'historique de rapport est stocké dans la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="28cfd-105">Report history is stored in the report server database.</span></span> <span data-ttu-id="28cfd-106">Si les instantanés de rapport contiennent une grande quantité de données, songez à limiter l'historique de rapport afin de réduire l'impact de la rétention des instantanés sur la taille de la base de données.</span><span class="sxs-lookup"><span data-stu-id="28cfd-106">If report snapshots contain a large amount of data, you might consider limiting report history to minimize the affect of snapshot retention on database size.</span></span>  
  
### <a name="to-configure-report-history-for-a-report-server"></a><span data-ttu-id="28cfd-107">Pour configurer un historique de rapport destiné à un serveur de rapports</span><span class="sxs-lookup"><span data-stu-id="28cfd-107">To configure report history for a report server</span></span>  
  
1.  <span data-ttu-id="28cfd-108">Dans le Gestionnaire de rapports, dans la barre d’outils globale, cliquez sur **Paramètres du site** .</span><span class="sxs-lookup"><span data-stu-id="28cfd-108">In Report Manager, click **Site Settings** on the global toolbar.</span></span>  
  
2.  <span data-ttu-id="28cfd-109">Sélectionnez l’option **Conserver un nombre illimité d’instantanés dans l’historique de rapport** pour conserver tous les historiques de rapport sur une durée indéterminée.</span><span class="sxs-lookup"><span data-stu-id="28cfd-109">Select **Keep an unlimited number of snapshots in report history** if you want to keep all report history indefinitely.</span></span> <span data-ttu-id="28cfd-110">Sinon, choisissez **Limiter les copies de l’historique de rapport** pour spécifier le nombre maximal d’instantanés à conserver pour un rapport donné.</span><span class="sxs-lookup"><span data-stu-id="28cfd-110">Otherwise, select **Limit the copies of report history** to specify the maximum number of snapshots that can be kept for any given report.</span></span>  
  
3.  <span data-ttu-id="28cfd-111">Cliquez sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="28cfd-111">Click **Apply**.</span></span>  
  
### <a name="to-configure-report-history-for-a-specific-report"></a><span data-ttu-id="28cfd-112">Pour configurer un historique de rapport destiné à un rapport spécifique</span><span class="sxs-lookup"><span data-stu-id="28cfd-112">To configure report history for a specific report</span></span>  
  
1.  <span data-ttu-id="28cfd-113">Dans le Gestionnaire de rapports, parcourez l'arborescence jusqu'au rapport pour lequel configurer l'historique, puis cliquez sur cet élément pour l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="28cfd-113">In Report Manager, navigate to the report for which you want to configure history, and then click the report to open it.</span></span>  
  
2.  <span data-ttu-id="28cfd-114">Cliquez sur l’onglet **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="28cfd-114">Click the **Properties** tab.</span></span>  
  
3.  <span data-ttu-id="28cfd-115">Sélectionnez l'onglet **Historique**.</span><span class="sxs-lookup"><span data-stu-id="28cfd-115">Click the **History** tab.</span></span>  
  
4.  <span data-ttu-id="28cfd-116">Sélectionnez les options pour votre rapport, puis cliquez sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="28cfd-116">Select the options for your report and click **Apply**.</span></span> <span data-ttu-id="28cfd-117">Pour plus d’informations sur chaque option, consultez [Page de propriétés Options d’instantanés &#40;Gestionnaire de rapports&#41;](../snapshot-options-properties-page-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="28cfd-117">For details about each option, see [Snapshot Options Properties Page &#40;Report Manager&#41;](../snapshot-options-properties-page-report-manager.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28cfd-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="28cfd-118">See Also</span></span>  
 <span data-ttu-id="28cfd-119">[Ajoutez un instantané à l’historique de rapport &#40;Gestionnaire de rapports&#41;](../report-server/add-a-snapshot-to-report-history-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="28cfd-119">[Add a Snapshot to Report History &#40;Report Manager&#41;](../report-server/add-a-snapshot-to-report-history-report-manager.md) </span></span>  
 [<span data-ttu-id="28cfd-120">Gestionnaire de rapports &#40;SSRS en mode natif&#41;</span><span class="sxs-lookup"><span data-stu-id="28cfd-120">Report Manager  &#40;SSRS Native Mode&#41;</span></span>](../report-manager-ssrs-native-mode.md)  
  
  
