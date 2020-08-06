---
title: Boîte de dialogue « Paramètres du serveur de distribution » | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.DistributorSettings.f1
helpviewer_keywords:
- Distributor Settings dialog box
ms.assetid: 8276a521-bdd1-4783-bdb6-7ab43499c0ca
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b864620f155e899868c95f58350f98e2b659c4e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601366"
---
# <a name="sql-server-replication-distributor-settings-dialog-box"></a><span data-ttu-id="88653-102">Réplication SQL Server boîte de dialogue « Paramètres du serveur de distribution »</span><span class="sxs-lookup"><span data-stu-id="88653-102">SQL Server Replication 'Distributor Settings' dialog box</span></span>
  <span data-ttu-id="88653-103">La boîte de dialogue **Paramètres du serveur de distribution** permet de changer les paramètres des serveurs de distribution ajoutés dans le volet de gauche du Moniteur de réplication.</span><span class="sxs-lookup"><span data-stu-id="88653-103">The **Distributor Settings** dialog box enables you to change settings for Distributors that were added to the left pane in Replication Monitor.</span></span>  
  
## <a name="options"></a><span data-ttu-id="88653-104">Options</span><span class="sxs-lookup"><span data-stu-id="88653-104">Options</span></span>  
 <span data-ttu-id="88653-105">**Se connecter automatiquement au démarrage du Moniteur de réplication**</span><span class="sxs-lookup"><span data-stu-id="88653-105">**Connect automatically when Replication Monitor starts**</span></span>  
 <span data-ttu-id="88653-106">Sélectionnez cette option pour permettre au Moniteur de réplication de se connecter au serveur de distribution  et d'extraire les informations d'état.</span><span class="sxs-lookup"><span data-stu-id="88653-106">Select to let Replication Monitor connect to the Distributor and retrieve status information.</span></span>  
  
 <span data-ttu-id="88653-107">**Connection**</span><span class="sxs-lookup"><span data-stu-id="88653-107">**Connection**</span></span>  
 <span data-ttu-id="88653-108">Cliquez pour ouvrir la boîte de dialogue **Se connecter au serveur** .</span><span class="sxs-lookup"><span data-stu-id="88653-108">Click to display the **Connect to Server** dialog box.</span></span> <span data-ttu-id="88653-109">Cela vous permet d'afficher et de modifier les propriétés de connexion et les informations d'identification que le Moniteur de réplication utilisent pour se connecter au serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="88653-109">This enables you to view and change the connection properties and credentials that Replication Monitor uses to connect to the Distributor.</span></span>  
  
 <span data-ttu-id="88653-110">**Actualiser automatiquement le statut de ce serveur de distribution et de ses publications**</span><span class="sxs-lookup"><span data-stu-id="88653-110">**Automatically refresh the status of this Distributor and its publications**</span></span>  
 <span data-ttu-id="88653-111">Sélectionnez cette option pour laisser le Moniteur de réplication actualiser automatiquement l'état pour le serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="88653-111">Select to let Replication Monitor automatically refresh the status for the Distributor.</span></span> <span data-ttu-id="88653-112">Si cette option est sélectionnée, le Moniteur de réplication interroge le serveur de distribution pour obtenir les informations d'état en fonction de la fréquence d'interrogation définie par l'option **Fréquence d'actualisation** .</span><span class="sxs-lookup"><span data-stu-id="88653-112">If this option is selected, Replication Monitor polls the Distributor for status information based on the polling interval set by the **Refresh rate** option.</span></span> <span data-ttu-id="88653-113">Pour plus d'informations sur l'actualisation du Moniteur de réplication, consultez [Caching, Refresh, and Replication Monitor Performance](monitor/caching-refresh-and-replication-monitor-performance.md).</span><span class="sxs-lookup"><span data-stu-id="88653-113">For more information about refresh in Replication Monitor, see [Caching, Refresh, and Replication Monitor Performance](monitor/caching-refresh-and-replication-monitor-performance.md).</span></span>  
  
 <span data-ttu-id="88653-114">**Fréquence d'actualisation**</span><span class="sxs-lookup"><span data-stu-id="88653-114">**Refresh rate**</span></span>  
 <span data-ttu-id="88653-115">Entrez une valeur (en secondes) pour définir la fréquence à laquelle le Moniteur de réplication interroge le serveur de distribution pour obtenir les informations d'état.</span><span class="sxs-lookup"><span data-stu-id="88653-115">Enter a value (in seconds) to specify how frequently Replication Monitor should poll the Distributor for status.</span></span> <span data-ttu-id="88653-116">Des valeurs faibles provoquent des interrogations plus fréquentes.</span><span class="sxs-lookup"><span data-stu-id="88653-116">Lower values result in more frequent polling.</span></span> <span data-ttu-id="88653-117">Cela peut affecter les performances du serveur de distribution si vous surveillez plusieurs serveurs de publication.</span><span class="sxs-lookup"><span data-stu-id="88653-117">This can affect performance at the Distributor if you are monitoring many Publishers.</span></span> <span data-ttu-id="88653-118">Il est recommandé de tester le système pour déterminer la valeur appropriée.</span><span class="sxs-lookup"><span data-stu-id="88653-118">We recommend that you test your system to determine an appropriate value.</span></span> <span data-ttu-id="88653-119">L'option **Fréquence d'actualisation** est également utilisée si vous sélectionnez **Actualisation automatique** dans une fenêtre de détail du Moniteur de réplication.</span><span class="sxs-lookup"><span data-stu-id="88653-119">The **Refresh rate** setting is also used if you select **Auto Refresh** in any of the detail windows in Replication Monitor.</span></span>  
  
 <span data-ttu-id="88653-120">**Afficher tous les serveurs de publication de ce serveur de distribution dans le groupe suivant**</span><span class="sxs-lookup"><span data-stu-id="88653-120">**Show all Publishers of this Distributor in the following group**</span></span>  
 <span data-ttu-id="88653-121">Sélectionnez un groupe de serveurs de publication dans la liste.</span><span class="sxs-lookup"><span data-stu-id="88653-121">Select a Publisher group from the list.</span></span> <span data-ttu-id="88653-122">Le serveur de publication se trouve dans ce groupe dans le volet de gauche.</span><span class="sxs-lookup"><span data-stu-id="88653-122">The Publisher is displayed under this group in the left pane.</span></span> <span data-ttu-id="88653-123">Les groupes permettent d'organiser les serveurs de publication et n'ont aucun impact sur le fonctionnement de la réplication.</span><span class="sxs-lookup"><span data-stu-id="88653-123">Groups provide a way for you to organize Publishers and do not affect how replication functions.</span></span>  
  
 <span data-ttu-id="88653-124">**Nouveau groupe**</span><span class="sxs-lookup"><span data-stu-id="88653-124">**New Group**</span></span>  
 <span data-ttu-id="88653-125">Cliquez pour créer un nouveau groupe de serveurs de publication.</span><span class="sxs-lookup"><span data-stu-id="88653-125">Click to create a new Publisher group.</span></span> <span data-ttu-id="88653-126">Un groupe de serveurs de publication permet d'organiser aisément les serveurs de publication dans le Moniteur de réplication.</span><span class="sxs-lookup"><span data-stu-id="88653-126">A Publisher group provides a way for you to conveniently organize Publishers within Replication Monitor.</span></span> <span data-ttu-id="88653-127">Les groupes n'affectent pas la réplication des données ni la relation entre les serveurs dans une topologie de réplication.</span><span class="sxs-lookup"><span data-stu-id="88653-127">Groups do not affect the replication of data or the relationship among servers in a replication topology.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88653-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="88653-128">See Also</span></span>  
 <span data-ttu-id="88653-129">[Démarrer le Moniteur de réplication](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="88653-129">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 [<span data-ttu-id="88653-130">Surveillance de la réplication</span><span class="sxs-lookup"><span data-stu-id="88653-130">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
