---
title: Paramètres du moniteur d’envoi des journaux | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.databaseproperties.logshipping.settings.monitor.f1
ms.assetid: 45e2ba7d-b3aa-4643-9451-bcb991572314
author: stevestein
ms.author: sstein
ms.openlocfilehash: 162fdc1b8b0ef850a7e58d1380c533426e16539c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709544"
---
# <a name="log-shipping-monitor-settings"></a><span data-ttu-id="582a4-102">Paramètres du moniteur d'envoi des journaux</span><span class="sxs-lookup"><span data-stu-id="582a4-102">Log Shipping Monitor Settings</span></span>
  <span data-ttu-id="582a4-103">Cette page vous permet de configurer et de modifier les propriétés du serveur moniteur d'envoi des journaux.</span><span class="sxs-lookup"><span data-stu-id="582a4-103">Use this page to configure and to modify the properties of the log shipping monitor server.</span></span>  
  
 <span data-ttu-id="582a4-104">Pour obtenir des explications sur les concepts de copie des journaux de transaction, consultez [À propos de la copie des journaux de transaction &#40;SQL Server&#41;](../../database-engine/log-shipping/about-log-shipping-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="582a4-104">For an explanation of log shipping concepts, see [About Log Shipping &#40;SQL Server&#41;](../../database-engine/log-shipping/about-log-shipping-sql-server.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="582a4-105">Options</span><span class="sxs-lookup"><span data-stu-id="582a4-105">Options</span></span>  
 <span data-ttu-id="582a4-106">**Instance du serveur moniteur**</span><span class="sxs-lookup"><span data-stu-id="582a4-106">**Monitor server instance**</span></span>  
 <span data-ttu-id="582a4-107">Affiche le nom de l'instance du serveur actuellement configurée comme serveur moniteur dans la configuration d'envoi des journaux.</span><span class="sxs-lookup"><span data-stu-id="582a4-107">Displays the name of the server instance that is currently configured as the monitor server for the log shipping configuration.</span></span>  
  
 <span data-ttu-id="582a4-108">**Connexion**</span><span class="sxs-lookup"><span data-stu-id="582a4-108">**Connect**</span></span>  
 <span data-ttu-id="582a4-109">Sélectionnez et connectez-vous à une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à utiliser comme serveur moniteur.</span><span class="sxs-lookup"><span data-stu-id="582a4-109">Choose and connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to be used as the monitor server.</span></span> <span data-ttu-id="582a4-110">Le compte utilisé pour se connecter doit être membre du rôle serveur fixe sysadmin sur l'instance de serveur secondaire.</span><span class="sxs-lookup"><span data-stu-id="582a4-110">The account used to connect must be a member of the sysadmin fixed server role on the secondary server instance.</span></span>  
  
 <span data-ttu-id="582a4-111">**En imitant le compte proxy du travail**</span><span class="sxs-lookup"><span data-stu-id="582a4-111">**By impersonating the proxy account of the job**</span></span>  
 <span data-ttu-id="582a4-112">L'envoi des journaux doit imiter le compte proxy de l'Agent SQL Server lors de la connexion à l'instance du serveur moniteur.</span><span class="sxs-lookup"><span data-stu-id="582a4-112">Have log shipping impersonate the SQL Server Agent proxy account when connecting to the monitor server instance.</span></span> <span data-ttu-id="582a4-113">Les processus de sauvegarde, copie et restauration doivent être capables de se connecter au serveur moniteur pour mettre à jour l'état des opérations d'envoi de journaux.</span><span class="sxs-lookup"><span data-stu-id="582a4-113">The backup, copy, and restore processes must be able to connect to the monitor server to update the status of log shipping operations.</span></span>  
  
 <span data-ttu-id="582a4-114">**En utilisant la connexion SQL Server suivante**</span><span class="sxs-lookup"><span data-stu-id="582a4-114">**Using the following SQL Server login**</span></span>  
 <span data-ttu-id="582a4-115">Permet à l'envoi des journaux d'utiliser une connexion [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] spécifique lors de la connexion à l'instance du serveur moniteur.</span><span class="sxs-lookup"><span data-stu-id="582a4-115">Allow log shipping to use a specific [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login when connecting to the monitor server instance.</span></span> <span data-ttu-id="582a4-116">Les processus de sauvegarde, copie et restauration doivent être capables de se connecter au serveur moniteur pour mettre à jour l'état des opérations d'envoi de journaux.</span><span class="sxs-lookup"><span data-stu-id="582a4-116">The backup, copy, and restore processes must be able to connect to the monitor server to update the status of log shipping operations.</span></span> <span data-ttu-id="582a4-117">Choisissez cette option pour que l'envoi des journaux utilise une connexion [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] spécifique, puis spécifiez le nom d'accès et le mot de passe.</span><span class="sxs-lookup"><span data-stu-id="582a4-117">Choose this option if you want log shipping to use a specific [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login and then specify the login and password.</span></span>  
  
 <span data-ttu-id="582a4-118">**Supprimer l'historique après le**</span><span class="sxs-lookup"><span data-stu-id="582a4-118">**Delete history after**</span></span>  
 <span data-ttu-id="582a4-119">Spécifiez la durée pendant laquelle il convient de conserver les informations de l'historique d'envoi des journaux sur le serveur moniteur avant de les supprimer.</span><span class="sxs-lookup"><span data-stu-id="582a4-119">Specify the amount of time to retain log shipping history information on the monitor server before it is deleted.</span></span>  
  
 <span data-ttu-id="582a4-120">**Nom du travail**</span><span class="sxs-lookup"><span data-stu-id="582a4-120">**Job name**</span></span>  
 <span data-ttu-id="582a4-121">Spécifie le nom du travail d'alerte de l'Agent SQL Server utilisé par l'envoi des journaux pour déclencher des alertes lors du dépassement des seuils de sauvegarde ou de restauration.</span><span class="sxs-lookup"><span data-stu-id="582a4-121">Indicates the name of the SQL Server Agent alert job used by log shipping to raise alerts when backup or restore thresholds have been exceeded.</span></span> <span data-ttu-id="582a4-122">Lors de la création de ce travail, vous pouvez modifier son nom en le tapant dans cette zone.</span><span class="sxs-lookup"><span data-stu-id="582a4-122">When first creating this job, you can change the name by typing in the box.</span></span>  
  
 <span data-ttu-id="582a4-123">**Planification**</span><span class="sxs-lookup"><span data-stu-id="582a4-123">**Schedule**</span></span>  
 <span data-ttu-id="582a4-124">Indique la planification en cours du travail d'alerte de l'Agent SQL Server.</span><span class="sxs-lookup"><span data-stu-id="582a4-124">Indicates the current schedule of the SQL Server Agent alert job.</span></span>  
  
 <span data-ttu-id="582a4-125">**Modifier**</span><span class="sxs-lookup"><span data-stu-id="582a4-125">**Edit**</span></span>  
 <span data-ttu-id="582a4-126">Modifiez les paramètres du travail d'alerte de l'Agent SQL Server.</span><span class="sxs-lookup"><span data-stu-id="582a4-126">Modify the SQL Server Agent alert job parameters.</span></span>  
  
 <span data-ttu-id="582a4-127">**Désactiver ce travail**</span><span class="sxs-lookup"><span data-stu-id="582a4-127">**Disable this job**</span></span>  
 <span data-ttu-id="582a4-128">Permet de suspendre le travail d'alerte de l'Agent SQL Server.</span><span class="sxs-lookup"><span data-stu-id="582a4-128">Suspend the SQL Server Agent alert job.</span></span>  
  
  
