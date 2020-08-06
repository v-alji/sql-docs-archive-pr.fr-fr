---
title: Ouvrir le Moniteur d’activité (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Activity Monitor [SQL Server], setting the refresh interval
- refresh interval for Activity Monitor
- Activity Monitor [SQL Server], opening
- opening Activity Monitor
ms.assetid: 0a6eeb16-f02b-479d-9a60-543e40ebf46b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ea74122ad18a0a1ede5eef1e09684606ca0ce073
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707399"
---
# <a name="open-activity-monitor-sql-server-management-studio"></a><span data-ttu-id="60de8-102">Ouvrir le Moniteur d'activité (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="60de8-102">Open Activity Monitor (SQL Server Management Studio)</span></span>
  <span data-ttu-id="60de8-103">Cette rubrique décrit la façon d'ouvrir le Moniteur d'activité pour obtenir des informations sur les processus [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et la façon dont ces processus affectent l'instance actuelle de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="60de8-103">This topic describes how to open the Activity Monitor to obtain information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] processes and how these processes affect the current instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="60de8-104">Elle explique également comment définir l'intervalle d'actualisation du Moniteur d'activité.</span><span class="sxs-lookup"><span data-stu-id="60de8-104">It also describes how to set the refresh interval of the Activity Monitor.</span></span>  
  
 <span data-ttu-id="60de8-105">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="60de8-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="60de8-106">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="60de8-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="60de8-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="60de8-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="60de8-108">**Pour ouvrir le Moniteur d'activité à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="60de8-108">**To open the Activity Monitor using:**</span></span>  
  
     [<span data-ttu-id="60de8-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="60de8-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   <span data-ttu-id="60de8-110">**Pour définir l’intervalle d’actualisation avec :**  [SQL Server Management Studio](#Refresh)</span><span class="sxs-lookup"><span data-stu-id="60de8-110">**To set the refresh interval using:**  [SQL Server Management Studio](#Refresh)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="60de8-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="60de8-111">Before You Begin</span></span>  
 <span data-ttu-id="60de8-112">Le Moniteur d'activité exécute des requêtes sur l'instance analysée afin d'obtenir des informations pour ses volets d'informations.</span><span class="sxs-lookup"><span data-stu-id="60de8-112">Activity Monitor runs queries on the monitored instance to obtain information for the Activity Monitor display panes.</span></span> <span data-ttu-id="60de8-113">Si l'intervalle d'actualisation est défini sur une valeur inférieure à 10 secondes, le temps nécessaire à l'exécution de ces requêtes peut affecter les performances du serveur.</span><span class="sxs-lookup"><span data-stu-id="60de8-113">When the refresh interval is set to less than 10 seconds, the time that is used to run these queries can affect server performance</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="60de8-114">Sécurité</span><span class="sxs-lookup"><span data-stu-id="60de8-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="60de8-115">Autorisations</span><span class="sxs-lookup"><span data-stu-id="60de8-115">Permissions</span></span>  
 <span data-ttu-id="60de8-116">Pour afficher le Moniteur d'activité, un utilisateur doit disposer de l'autorisation VIEW SERVER STATE.</span><span class="sxs-lookup"><span data-stu-id="60de8-116">To view the Activity Monitor, a user must have VIEW SERVER STATE permission.</span></span> <span data-ttu-id="60de8-117">Pour afficher la section E/S du fichier de données du Moniteur d'activité, vous devez disposer de l'autorisation CREATE DATABASE, ALTER ANY DATABASE ou VIEW ANY DEFINITION en plus de VIEW SERVER STATE.</span><span class="sxs-lookup"><span data-stu-id="60de8-117">To view the Data File I/O section of Activity Monitor, you must have CREATE DATABASE, ALTER ANY DATABASE, or VIEW ANY DEFINITION permission in addition to VIEW SERVER STATE.</span></span>  
  
 <span data-ttu-id="60de8-118">Pour pouvoir mettre fin (KILL) à un processus, un utilisateur doit être membre des rôles serveur fixe sysadmin ou processadmin.</span><span class="sxs-lookup"><span data-stu-id="60de8-118">To KILL a process, a user must be a member of the sysadmin or processadmin fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="60de8-119">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="60de8-119">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-open-activity-monitor-in-sql-server-management-studio"></a><span data-ttu-id="60de8-120">Pour ouvrir le Moniteur d'activité dans SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="60de8-120">To open Activity Monitor in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="60de8-121">Dans la barre d'outils standard [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , cliquez sur **Moniteur d'activité**.</span><span class="sxs-lookup"><span data-stu-id="60de8-121">On the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] standard toolbar, click **Activity Monitor**.</span></span>  
  
2.  <span data-ttu-id="60de8-122">Dans la boîte de dialogue **Se connecter au serveur** , sélectionnez le nom de serveur et le mode d'authentification, puis cliquez sur **Se connecter**.</span><span class="sxs-lookup"><span data-stu-id="60de8-122">In the **Connect to Server** dialog box, select the server name and authentication mode, and then click **Connect**.</span></span>  
  
 <span data-ttu-id="60de8-123">Vous pouvez également ouvrir le Moniteur d'activité à tout moment en appuyant sur CTRL+ALT A.</span><span class="sxs-lookup"><span data-stu-id="60de8-123">You can also open Activity Monitor at any time by pressing CTRL+ALT A.</span></span>  
  
#### <a name="to-open-activity-monitor-in-object-explorer"></a><span data-ttu-id="60de8-124">Pour ouvrir le Moniteur d'activité dans l'Explorateur d'objets</span><span class="sxs-lookup"><span data-stu-id="60de8-124">To open Activity Monitor in Object Explorer</span></span>  
  
-   <span data-ttu-id="60de8-125">Dans l'Explorateur d'objets, cliquez avec le bouton droit sur le nom de l'instance, puis sélectionnez **Moniteur d'activité**.</span><span class="sxs-lookup"><span data-stu-id="60de8-125">In Object Explorer, right-click the instance name, and then select **Activity Monitor**.</span></span>  
  
#### <a name="to-open-activity-monitor-when-opening-sql-server-management-studio"></a><span data-ttu-id="60de8-126">Pour ouvrir le Moniteur d'activité lors de l'ouverture de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="60de8-126">To open Activity Monitor when opening SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="60de8-127">Dans le menu **Outils** , cliquez sur **Options**.</span><span class="sxs-lookup"><span data-stu-id="60de8-127">On the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="60de8-128">Dans la boîte de dialogue **Options** , développez **Environnement**, puis sélectionnez **Général**.</span><span class="sxs-lookup"><span data-stu-id="60de8-128">In the **Options** dialog box, expand **Environment**, and then select **General**.</span></span>  
  
3.  <span data-ttu-id="60de8-129">Dans la zone **Au démarrage** , sélectionnez **Ouvrir l'Explorateur d'objets et le Moniteur d'activité**.</span><span class="sxs-lookup"><span data-stu-id="60de8-129">In the **At startup** box, select **Open Object Explorer and Activity Monitor**.</span></span>  
  
4.  <span data-ttu-id="60de8-130">Pour activer les modifications, fermez et rouvrez [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="60de8-130">To activate the changes, close and reopen [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
###  <a name="to-set-the-activity-monitor-refresh-interval"></a><a name="Refresh"></a><span data-ttu-id="60de8-131">Pour définir l’intervalle d’actualisation du moniteur d’activité</span><span class="sxs-lookup"><span data-stu-id="60de8-131">To Set the Activity Monitor Refresh Interval</span></span>  
  
-   <span data-ttu-id="60de8-132">Ouvrez le Moniteur d'activité.</span><span class="sxs-lookup"><span data-stu-id="60de8-132">Open the Activity Monitor.</span></span>  
  
-   <span data-ttu-id="60de8-133">Cliquez avec le bouton droit sur **Vue d’ensemble**, sélectionnez **Intervalle d’actualisation**, puis choisissez l’intervalle dans lequel le Moniteur d’activité doit obtenir de nouvelles informations sur l’instance.</span><span class="sxs-lookup"><span data-stu-id="60de8-133">Right-click **Overview**, select **Refresh Interval**, and then select the interval in which Activity Monitor should obtain new instance information.</span></span>  
  
  
