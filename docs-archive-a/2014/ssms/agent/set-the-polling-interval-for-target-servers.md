---
title: Définir la fréquence d’interrogation pour les serveurs cibles | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- interval for polling [SQL Server]
- target servers [SQL Server], polling interval
- polling interval [SQL Server]
ms.assetid: 4ffbbefa-77fb-442e-a77c-cb8c6cab9f3c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 36517f60a99a1a844f6d14d489587eef1de9cb13
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710092"
---
# <a name="set-the-polling-interval-for-target-servers"></a><span data-ttu-id="8957f-102">Set the Polling Interval for Target Servers</span><span class="sxs-lookup"><span data-stu-id="8957f-102">Set the Polling Interval for Target Servers</span></span>
  <span data-ttu-id="8957f-103">Cette rubrique explique comment définir la fréquence à laquelle l' [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] agent actualise les informations du serveur maître sur les serveurs cibles.</span><span class="sxs-lookup"><span data-stu-id="8957f-103">This topic describes how to set the frequency that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent refreshes information from the master to the target servers.</span></span> <span data-ttu-id="8957f-104">Un travail est une série d'actions exécutées par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="8957f-104">A job is a specified series of actions that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent performs.</span></span> <span data-ttu-id="8957f-105">Un travail multiserveur est un travail exécuté par un serveur maître sur un ou plusieurs serveurs cibles.</span><span class="sxs-lookup"><span data-stu-id="8957f-105">A multiserver job is a job that a master server runs on one or more target servers.</span></span>  
  
-   <span data-ttu-id="8957f-106">**Avant de commencer :**  [Sécurité](#Security)</span><span class="sxs-lookup"><span data-stu-id="8957f-106">**Before you begin:**  [Security](#Security)</span></span>  
  
-   <span data-ttu-id="8957f-107">**Pour définir l’intervalle d’interrogation pour les serveurs cibles, avec :**  [SQL Server Management Studio](#SSMS), [Transact-SQL](#TSQL)</span><span class="sxs-lookup"><span data-stu-id="8957f-107">**To set the polling interval for target servers, using:**  [SQL Server Management Studio](#SSMS), [Transact-SQL](#TSQL)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8957f-108">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="8957f-108">Before You Begin</span></span>  
 <span data-ttu-id="8957f-109">Chaque serveur cible peut exécuter une instance du même travail au même moment.</span><span class="sxs-lookup"><span data-stu-id="8957f-109">Each target server can run one instance of the same job at the same time.</span></span> <span data-ttu-id="8957f-110">Chaque serveur cible interroge régulièrement le serveur maître, télécharge une copie des nouveaux travaux affectés au serveur cible, puis se déconnecte.</span><span class="sxs-lookup"><span data-stu-id="8957f-110">Each target server periodically polls the master server, downloads a copy of any new jobs assigned to the target server, and then disconnects.</span></span> <span data-ttu-id="8957f-111">Le serveur cible exécute localement le travail, puis se reconnecte au serveur maître pour charger l'état de la sortie du travail.</span><span class="sxs-lookup"><span data-stu-id="8957f-111">The target server runs the job locally and then reconnects to the master server to upload the job outcome status.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8957f-112">Si le serveur maître est accessible lorsque le serveur cible tente de charger l'état du travail, ce dernier est mis en attente dans le spouleur jusqu'à ce que le serveur maître soit accessible.</span><span class="sxs-lookup"><span data-stu-id="8957f-112">If the master server is inaccessible when the target server tries to upload job status, the job status is spooled until the master server can be accessed.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8957f-113">Sécurité</span><span class="sxs-lookup"><span data-stu-id="8957f-113">Security</span></span>  
 <span data-ttu-id="8957f-114">Pour plus d'informations, consultez [Implement SQL Server Agent Security](implement-sql-server-agent-security.md) et [Choose the Right SQL Server Agent Service Account for Multiserver Environments](choose-the-right-sql-server-agent-service-account-for-multiserver-environments.md).</span><span class="sxs-lookup"><span data-stu-id="8957f-114">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md) and [Choose the Right SQL Server Agent Service Account for Multiserver Environments](choose-the-right-sql-server-agent-service-account-for-multiserver-environments.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="8957f-115">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8957f-115">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="8957f-116">**Pour définir l'intervalle d'interrogation pour les serveurs cibles**</span><span class="sxs-lookup"><span data-stu-id="8957f-116">**To set the polling interval for target servers**</span></span>  
  
1.  <span data-ttu-id="8957f-117">Dans l' **Explorateur d’objets,** Connectez-vous à une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , puis développez cette instance.</span><span class="sxs-lookup"><span data-stu-id="8957f-117">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="8957f-118">Cliquez avec le bouton droit sur **Agent SQL Server**, pointez sur **Administration multiserveur**, puis cliquez sur **Gérer les serveurs cibles**.</span><span class="sxs-lookup"><span data-stu-id="8957f-118">Right-click **SQL Server Agent**, point to **Multi Server Administration**, and then click **Manage Target Servers**.</span></span>  
  
3.  <span data-ttu-id="8957f-119">Sous l'onglet **État du serveur cible** , cliquez sur **Publier les instructions**.</span><span class="sxs-lookup"><span data-stu-id="8957f-119">On the **Target Server Status** tab, click **Post Instructions**.</span></span>  
  
4.  <span data-ttu-id="8957f-120">Dans la liste **Type d'instruction** , sélectionnez **Définir la fréquence d'interrogation**.</span><span class="sxs-lookup"><span data-stu-id="8957f-120">In the **Instruction type** list, select **Set polling interval**.</span></span>  
  
5.  <span data-ttu-id="8957f-121">Dans la zone **Fréquence d'interrogation** , entrez le nombre de secondes, entre 10 et 28800, qui doivent s'écouler avant que le serveur cible n'interroge le serveur maître.</span><span class="sxs-lookup"><span data-stu-id="8957f-121">In the **Polling interval** box, enter the number of seconds from 10 through 28,800 that must pass before the target server polls the master server.</span></span>  
  
6.  <span data-ttu-id="8957f-122">Sous **Destinataires**, activez l'une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="8957f-122">Under **Recipients**, do one of the following:</span></span>  
  
    1.  <span data-ttu-id="8957f-123">Cliquez sur **Tous les serveurs cibles** si tous les serveurs cibles partagent la même fréquence d'interrogation.</span><span class="sxs-lookup"><span data-stu-id="8957f-123">Click **All target servers** if all target servers share the same polling interval.</span></span>  
  
    2.  <span data-ttu-id="8957f-124">Cliquez sur **Serveurs cibles sélectionnés** si les serveurs cibles ne partagent pas tous la même fréquence d'interrogation, puis sélectionnez chacun des serveurs cibles qui utilisera cette fréquence d'interrogation.</span><span class="sxs-lookup"><span data-stu-id="8957f-124">Click **These target servers** if not all target servers share the same polling interval, and then select each target server that will use this polling interval.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="8957f-125">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8957f-125">Using Transact-SQL</span></span>  
 <span data-ttu-id="8957f-126">**Pour définir l'intervalle d'interrogation pour les serveurs cibles**</span><span class="sxs-lookup"><span data-stu-id="8957f-126">**To set the polling interval for target servers**</span></span>  
  
1.  <span data-ttu-id="8957f-127">Dans l'Explorateur d'objets, connectez-vous à une instance du moteur de base de données et développez-la.</span><span class="sxs-lookup"><span data-stu-id="8957f-127">In Object Explorer, connect to an instance of the Database Engine, and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="8957f-128">Dans la barre d'outils, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="8957f-128">On the toolbar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8957f-129">Dans la fenêtre de requête, utilisez la procédure stockée système [sp_post_msx_operation &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-post-msx-operation-transact-sql) pour définir la fréquence d’interrogation pour les serveurs cibles.</span><span class="sxs-lookup"><span data-stu-id="8957f-129">In the query window, use the [sp_post_msx_operation &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-post-msx-operation-transact-sql) system stored procedure to set the polling interval for target servers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8957f-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8957f-130">See Also</span></span>  
 [<span data-ttu-id="8957f-131">dbo.sysdownloadlist &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8957f-131">dbo.sysdownloadlist &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-tables/dbo-sysdownloadlist-transact-sql)  
  
  
