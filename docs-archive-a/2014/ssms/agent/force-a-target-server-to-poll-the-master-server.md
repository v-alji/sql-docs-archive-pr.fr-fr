---
title: Forcer l’interrogation d’un serveur maître par un serveur cible | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- forcing master server polling
- polling master servers [SQL Server]
- master servers [SQL Server], polling
- target servers [SQL Server], polling the master server
ms.assetid: f1189a47-5ac3-45e2-9c5f-847810672279
author: stevestein
ms.author: sstein
ms.openlocfilehash: b37bf19bfe8e8fb55c29c8d94c28a341d06df5da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600466"
---
# <a name="force-a-target-server-to-poll-the-master-server"></a><span data-ttu-id="304dd-102">Forcer un serveur cible à interroger le serveur maître</span><span class="sxs-lookup"><span data-stu-id="304dd-102">Force a Target Server to Poll the Master Server</span></span>
  <span data-ttu-id="304dd-103">Cette rubrique explique comment forcer l'interrogation du serveur maître par un serveur cible.</span><span class="sxs-lookup"><span data-stu-id="304dd-103">This topic describes how to force a target server to poll the master server.</span></span> <span data-ttu-id="304dd-104">Le serveur cible doit être un serveur inscrit sur le serveur maître.</span><span class="sxs-lookup"><span data-stu-id="304dd-104">The target server must be a registered server on the master server.</span></span>  
  
 <span data-ttu-id="304dd-105">Un travail est une série d'actions exécutées par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="304dd-105">A job is a specified series of actions that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent performs.</span></span> <span data-ttu-id="304dd-106">Un travail multiserveur est un travail exécuté par un serveur maître sur un ou plusieurs serveurs cibles.</span><span class="sxs-lookup"><span data-stu-id="304dd-106">A multiserver job is a job that a master server runs on one or more target servers.</span></span> <span data-ttu-id="304dd-107">Chaque serveur cible peut exécuter une instance du même travail au même moment.</span><span class="sxs-lookup"><span data-stu-id="304dd-107">Each target server can run one instance of the same job at the same time.</span></span> <span data-ttu-id="304dd-108">Chaque serveur cible interroge régulièrement le serveur maître, télécharge une copie des nouveaux travaux affectés au serveur cible, puis se déconnecte.</span><span class="sxs-lookup"><span data-stu-id="304dd-108">Each target server periodically polls the master server, downloads a copy of any new jobs assigned to the target server, and then disconnects.</span></span> <span data-ttu-id="304dd-109">Le serveur cible exécute localement le travail, puis se reconnecte au serveur maître pour charger l'état de la sortie du travail.</span><span class="sxs-lookup"><span data-stu-id="304dd-109">The target server runs the job locally and then reconnects to the master server to upload the job outcome status.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="304dd-110">Si le serveur maître est accessible lorsque le serveur cible tente de charger l'état du travail, ce dernier est mis en attente dans le spouleur jusqu'à ce que le serveur maître soit accessible.</span><span class="sxs-lookup"><span data-stu-id="304dd-110">If the master server is inaccessible when the target server tries to upload job status, the job status is spooled until the master server can be accessed.</span></span>  
  
-   <span data-ttu-id="304dd-111">**Avant de commencer :**  [Limitations et restrictions](#Restrictions), [sécurité](#Security)</span><span class="sxs-lookup"><span data-stu-id="304dd-111">**Before you begin:**  [Limitations and Restrictions](#Restrictions), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="304dd-112">**Pour forcer l’interrogation du serveur maître par un serveur cible, avec :**  [SQL Server Management Studio](#SSMS)</span><span class="sxs-lookup"><span data-stu-id="304dd-112">**To force a target server to poll the master server, using:**  [SQL Server Management Studio](#SSMS)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="304dd-113">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="304dd-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="304dd-114">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="304dd-114">Limitations and Restrictions</span></span>  
 <span data-ttu-id="304dd-115">Le serveur cible doit être un serveur inscrit sur le serveur maître.</span><span class="sxs-lookup"><span data-stu-id="304dd-115">The target server must be a registered server on the master server.</span></span> <span data-ttu-id="304dd-116">Vous devez exécuter les instructions fournies dans cette rubrique à partir du serveur maître.</span><span class="sxs-lookup"><span data-stu-id="304dd-116">You must run the instructions given in this topic from the master server.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="304dd-117">Sécurité</span><span class="sxs-lookup"><span data-stu-id="304dd-117">Security</span></span>  
 <span data-ttu-id="304dd-118">Pour plus d'informations, consultez [Implement SQL Server Agent Security](implement-sql-server-agent-security.md) et [Choose the Right SQL Server Agent Service Account for Multiserver Environments](choose-the-right-sql-server-agent-service-account-for-multiserver-environments.md).</span><span class="sxs-lookup"><span data-stu-id="304dd-118">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md) and [Choose the Right SQL Server Agent Service Account for Multiserver Environments](choose-the-right-sql-server-agent-service-account-for-multiserver-environments.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="304dd-119">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="304dd-119">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="304dd-120">**Pour forcer l'interrogation d'un serveur maître par un serveur cible**</span><span class="sxs-lookup"><span data-stu-id="304dd-120">**To force a target server to poll the master server**</span></span>  
  
1.  <span data-ttu-id="304dd-121">Dans l' **Explorateur d'objets**, développez le serveur maître.</span><span class="sxs-lookup"><span data-stu-id="304dd-121">In **Object Explorer**, expand the master server.</span></span>  
  
2.  <span data-ttu-id="304dd-122">Cliquez avec le bouton droit sur **Agent SQL Server**, pointez sur **Administration multiserveur**, puis cliquez sur **Gérer les serveurs cibles**.</span><span class="sxs-lookup"><span data-stu-id="304dd-122">Right-click **SQL Server Agent**, point to **Multi Server Administration**, and then click **Manage Target Servers**.</span></span>  
  
3.  <span data-ttu-id="304dd-123">Cliquez sur un serveur cible, puis sur **Forcer l'interrogation**.</span><span class="sxs-lookup"><span data-stu-id="304dd-123">Click a target server, and then click **Force Poll**.</span></span>  
  
  
