---
title: Serveur de distribution | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.replicationutilities.selectdistributor.f1
ms.assetid: 787f0e9c-09dd-438a-bc04-5b8f99c127b8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c601a540088b5cd9d7a2033510a5cf9b83c3170e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601360"
---
# <a name="distributor"></a><span data-ttu-id="e4a75-102">Serveur de distribution</span><span class="sxs-lookup"><span data-stu-id="e4a75-102">Distributor</span></span>
  <span data-ttu-id="e4a75-103">La page **Serveur de distribution** figure dans l'Assistant Configuration de la distribution et l'Assistant Nouvelle publication.</span><span class="sxs-lookup"><span data-stu-id="e4a75-103">The **Distributor** page appears in the Configure Distribution Wizard and in the New Publication Wizard.</span></span> <span data-ttu-id="e4a75-104">Le serveur de distribution est le serveur qui contient la base de données de distribution et qui stocke les métadonnées et les données d'historique de tous les types de réplications.</span><span class="sxs-lookup"><span data-stu-id="e4a75-104">The Distributor is a server that contains the distribution database and stores metadata and history data for all types of replication.</span></span> <span data-ttu-id="e4a75-105">Le serveur de distribution stocke également les transactions de la réplication transactionnelle.</span><span class="sxs-lookup"><span data-stu-id="e4a75-105">The Distributor also stores transactions for transactional replication.</span></span> <span data-ttu-id="e4a75-106">Le serveur de distribution peut correspondre au serveur de publication (serveur de distribution) ou à un serveur distinct du serveur de publication (serveur de distribution distant).</span><span class="sxs-lookup"><span data-stu-id="e4a75-106">The Distributor can be the same server as the Publisher (a local Distributor) or it can be a separate server from the Publisher (a remote Distributor).</span></span> <span data-ttu-id="e4a75-107">Le rôle du serveur de distribution varie en fonction du type de réplication implémenté.</span><span class="sxs-lookup"><span data-stu-id="e4a75-107">The role of the Distributor varies, depending on which type of replication you implement.</span></span> <span data-ttu-id="e4a75-108">En règle générale, il joue un rôle beaucoup plus important pour la réplication transactionnelle que pour la réplication de fusion et la réplication d'instantané.</span><span class="sxs-lookup"><span data-stu-id="e4a75-108">In general, its role is much greater for transactional replication than it is for merge replication and snapshot replication.</span></span> <span data-ttu-id="e4a75-109">La réplication de fusion et la réplication d'instantané utilisent un serveur de distribution local, mais la réplication transactionnelle sur un système très occupé peut tirer parti d'un serveur de distribution distant.</span><span class="sxs-lookup"><span data-stu-id="e4a75-109">Merge and snapshot replication typically use a local Distributor, but transactional replication on a very busy system can benefit from using a remote Distributor.</span></span>  
  
 <span data-ttu-id="e4a75-110">Le serveur de distribution utilise les ressources supplémentaires suivantes sur le serveur sur lequel il se trouve :</span><span class="sxs-lookup"><span data-stu-id="e4a75-110">The Distributor uses these additional resources on the server where it is located:</span></span>  
  
-   <span data-ttu-id="e4a75-111">espace disque supplémentaire si les fichiers d'instantané de la publication y sont stockés (ce qui est généralement le cas) ;</span><span class="sxs-lookup"><span data-stu-id="e4a75-111">Additional disk space if the snapshot files for the publication are stored on it (which they typically are).</span></span>  
  
-   <span data-ttu-id="e4a75-112">espace disque supplémentaire pour stocker la base de données de distribution ;</span><span class="sxs-lookup"><span data-stu-id="e4a75-112">Additional disk space to store the distribution database.</span></span>  
  
-   <span data-ttu-id="e4a75-113">augmentation de l'utilisation du processeur par les agents de réplication pour les abonnements par envoi de données (push) exécutés sur le serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="e4a75-113">Additional processor usage by replication agents for push subscriptions running on the Distributor.</span></span>  
  
 <span data-ttu-id="e4a75-114">Le serveur que vous sélectionnez comme serveur de distribution doit avoir un espace disque suffisant et un processeur suffisamment puissant pour prendre en charge la réplication et toutes les autres activités basées sur ce serveur.</span><span class="sxs-lookup"><span data-stu-id="e4a75-114">The server you select as the Distributor should have adequate disk space and processor power to support replication and any other activities on that server.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e4a75-115">Options</span><span class="sxs-lookup"><span data-stu-id="e4a75-115">Options</span></span>  
 <span data-ttu-id="e4a75-116">**'\<ServerName>' agit comme son propre serveur de distribution ; SQL Server crée une base de données de distribution et un journal**</span><span class="sxs-lookup"><span data-stu-id="e4a75-116">**'\<ServerName>' will act as its own Distributor; SQL Server will create a distribution database and log**</span></span>  
 <span data-ttu-id="e4a75-117">Sélectionnez cette option pour configurer le serveur auquel vous êtes connecté comme serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="e4a75-117">Select this option to configure the server you are connected to as a Distributor.</span></span>  
  
 <span data-ttu-id="e4a75-118">**Utiliser le serveur suivant comme serveur de distribution (le serveur que vous sélectionnez doit déjà être configuré en tant que serveur de distribution)**</span><span class="sxs-lookup"><span data-stu-id="e4a75-118">**Use the following server as the Distributor (Note: the server you select must already be configured as a Distributor)**</span></span>  
 <span data-ttu-id="e4a75-119">Sélectionnez cette option et cliquez sur le nom d'un serveur en dessous pour configurer un autre serveur comme serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="e4a75-119">Select this option and then click on the name of a server below to configure another server as the Distributor.</span></span>  
  
 <span data-ttu-id="e4a75-120">**Ajouter**</span><span class="sxs-lookup"><span data-stu-id="e4a75-120">**Add**</span></span>  
 <span data-ttu-id="e4a75-121">Si le serveur que vous voulez utiliser comme serveur de distribution ne figure pas dans la liste, cliquez sur **Ajouter** pour identifier le serveur et l'ajouter à la liste.</span><span class="sxs-lookup"><span data-stu-id="e4a75-121">If the server you want to use as a Distributor is not listed, click **Add** to identify the server and add it to the list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e4a75-122">Pour utiliser un serveur distant comme serveur de distribution, le serveur distant doit être déjà configuré comme serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="e4a75-122">To use a remote server as the Distributor, the remote server must already be configured as a Distributor.</span></span> <span data-ttu-id="e4a75-123">Le serveur par rapport auquel cet Assistant est exécuté doit être activé comme serveur de publication sur ce serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="e4a75-123">The server against which this wizard is running must be enabled as a Publisher on that Distributor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4a75-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e4a75-124">See Also</span></span>  
 <span data-ttu-id="e4a75-125">[Configurer la distribution](configure-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="e4a75-125">[Configure Distribution](configure-distribution.md) </span></span>  
 [<span data-ttu-id="e4a75-126">Configurer la publication et la distribution</span><span class="sxs-lookup"><span data-stu-id="e4a75-126">Configure Publishing and Distribution</span></span>](configure-publishing-and-distribution.md)  
  
  
