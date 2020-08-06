---
title: Propriétés de SQL Server (onglet Ouvrir une session) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 405073fc-eaa3-43c6-bf82-2cd58cacc1c3
author: stevestein
ms.author: sstein
ms.openlocfilehash: adec9ed7c69023218baa96ab8f8edbb6f2b365bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605859"
---
# <a name="sql-server-properties-log-on-tab"></a><span data-ttu-id="7396e-102">Propriétés de SQL Server (onglet Ouvrir une session)</span><span class="sxs-lookup"><span data-stu-id="7396e-102">SQL Server Properties (Log On Tab)</span></span>
  <span data-ttu-id="7396e-103">L'onglet **Ouvrir une session** de la boîte de dialogue **Propriétés de SQL Server** permet de spécifier le compte utilisé par le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , de modifier le mot de passe d'un compte, ainsi que de démarrer et d'arrêter ce service.</span><span class="sxs-lookup"><span data-stu-id="7396e-103">Use the **Log On** tab of the **SQL Server Properties** dialog box to specify the account used by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service, to change the password of an account, and to start and stop the service.</span></span> <span data-ttu-id="7396e-104">La modification du mot de passe d'un compte prend effet immédiatement.</span><span class="sxs-lookup"><span data-stu-id="7396e-104">Changing the password of an account takes effect immediately.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7396e-105">Lorsque vous modifiez le nom du compte utilisé par un service sur une instance cluster, le nouveau compte doit être un membre du groupe de domaine spécifié au cours de l'installation pour le service modifié ou vous devez disposer de l'autorisation d'ajouter des membres à ce groupe.</span><span class="sxs-lookup"><span data-stu-id="7396e-105">When changing the account name used by a service on a clustered instance, the new account must be a member of the domain group specified during setup for the service being changed, or you must have permission to add members to that group.</span></span> <span data-ttu-id="7396e-106">Si vous ne disposez pas de l'autorisation de modifier l'appartenance aux groupes, contactez l'administrateur de domaine.</span><span class="sxs-lookup"><span data-stu-id="7396e-106">If you do not have permission to modify group membership, contact the domain administrator.</span></span>  
>   
>  <span data-ttu-id="7396e-107">Pour plus d'informations sur la sélection d'un compte pour exécuter le service, consultez « Configuration des comptes de service Windows » dans la documentation en ligne de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7396e-107">For more information about selecting an account to run the service, see "Setting Up Windows Service Accounts" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="options"></a><span data-ttu-id="7396e-108">Options</span><span class="sxs-lookup"><span data-stu-id="7396e-108">Options</span></span>  
 <span data-ttu-id="7396e-109">**Compte intégré**</span><span class="sxs-lookup"><span data-stu-id="7396e-109">**Built-in account**</span></span>  
 <span data-ttu-id="7396e-110">**Système local**</span><span class="sxs-lookup"><span data-stu-id="7396e-110">**Local System**</span></span>  
 -   <span data-ttu-id="7396e-111">Spécifiez le compte système local.</span><span class="sxs-lookup"><span data-stu-id="7396e-111">Specify the local system account.</span></span> <span data-ttu-id="7396e-112">Ce compte ne nécessite pas de mot de passe.</span><span class="sxs-lookup"><span data-stu-id="7396e-112">This account does not require a password.</span></span> <span data-ttu-id="7396e-113">Toutefois, le compte système local peut empêcher le service d'interagir avec les autres serveurs, en fonction des privilèges accordés au compte.</span><span class="sxs-lookup"><span data-stu-id="7396e-113">However, the local system account may prevent the service from interacting with other servers, depending on the privileges granted to the account.</span></span>  
  
 <span data-ttu-id="7396e-114">**Service local**</span><span class="sxs-lookup"><span data-stu-id="7396e-114">**Local Service**</span></span>  
 -   <span data-ttu-id="7396e-115">Spécifiez le compte de service local.</span><span class="sxs-lookup"><span data-stu-id="7396e-115">Specify the local service account.</span></span> <span data-ttu-id="7396e-116">Ce compte ne nécessite pas de mot de passe.</span><span class="sxs-lookup"><span data-stu-id="7396e-116">This account does not require a password.</span></span> <span data-ttu-id="7396e-117">Cependant, le compte de service local peut empêcher le service d'interagir avec les autres serveurs, en fonction des privilèges accordés au compte.</span><span class="sxs-lookup"><span data-stu-id="7396e-117">However, the local service account may prevent the service from interacting with other servers, depending on the privileges granted to the account.</span></span>  
  
 <span data-ttu-id="7396e-118">**Service réseau**</span><span class="sxs-lookup"><span data-stu-id="7396e-118">**Network Service**</span></span>  
 -   <span data-ttu-id="7396e-119">Il est recommandé de ne pas utiliser le compte de service réseau pour les services [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="7396e-119">We recommend that you do not use the Network Service account for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent services.</span></span> <span data-ttu-id="7396e-120">Les comptes d'utilisateur local et d'utilisateur de domaine conviennent mieux à ces services.</span><span class="sxs-lookup"><span data-stu-id="7396e-120">Local User or Domain User accounts are more appropriate for these services.</span></span>  
  
 <span data-ttu-id="7396e-121">**Ce compte**</span><span class="sxs-lookup"><span data-stu-id="7396e-121">**This account**</span></span>  
 <span data-ttu-id="7396e-122">Spécifiez un compte d'utilisateur local ou de domaine qui utilise l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="7396e-122">Specify a local or domain user account that uses Windows Authentication.</span></span> <span data-ttu-id="7396e-123">Nous vous recommandons d'utiliser un compte d'utilisateur de domaine doté d'autorisations minimales pour les services.</span><span class="sxs-lookup"><span data-stu-id="7396e-123">We recommend that you use a domain user account that has minimal rights for services.</span></span>  
  
 <span data-ttu-id="7396e-124">**Nom du compte**</span><span class="sxs-lookup"><span data-stu-id="7396e-124">**Account Name**</span></span>  
 <span data-ttu-id="7396e-125">Spécifie le nom de compte d'utilisateur local ou de domaine.</span><span class="sxs-lookup"><span data-stu-id="7396e-125">Specify the local or domain user account name.</span></span>  
  
 <span data-ttu-id="7396e-126">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="7396e-126">**Password**</span></span>  
 <span data-ttu-id="7396e-127">Tapez le mot de passe du compte.</span><span class="sxs-lookup"><span data-stu-id="7396e-127">Type the password of the account.</span></span>  
  
 <span data-ttu-id="7396e-128">**Confirmer le mot de passe**</span><span class="sxs-lookup"><span data-stu-id="7396e-128">**Confirm password**</span></span>  
 <span data-ttu-id="7396e-129">Tapez de nouveau le mot de passe du compte.</span><span class="sxs-lookup"><span data-stu-id="7396e-129">Type the password of the account again.</span></span>  
  
 <span data-ttu-id="7396e-130">**Start**</span><span class="sxs-lookup"><span data-stu-id="7396e-130">**Start**</span></span>  
 <span data-ttu-id="7396e-131">Démarrez le service.</span><span class="sxs-lookup"><span data-stu-id="7396e-131">Start the service.</span></span>  
  
 <span data-ttu-id="7396e-132">**Stop**</span><span class="sxs-lookup"><span data-stu-id="7396e-132">**Stop**</span></span>  
 <span data-ttu-id="7396e-133">Arrête le service.</span><span class="sxs-lookup"><span data-stu-id="7396e-133">Stop the service.</span></span>  
  
 <span data-ttu-id="7396e-134">**Suspendre**</span><span class="sxs-lookup"><span data-stu-id="7396e-134">**Pause**</span></span>  
 <span data-ttu-id="7396e-135">Suspend le service.</span><span class="sxs-lookup"><span data-stu-id="7396e-135">Pause the service.</span></span>  
  
 <span data-ttu-id="7396e-136">**Reprendre**</span><span class="sxs-lookup"><span data-stu-id="7396e-136">**Resume**</span></span>  
 <span data-ttu-id="7396e-137">Reprend un service suspendu.</span><span class="sxs-lookup"><span data-stu-id="7396e-137">Resume a paused service.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="7396e-138">Par défaut, seuls les membres du groupe des administrateurs locaux peuvent démarrer, arrêter, interrompre, reprendre ou redémarrer un service.</span><span class="sxs-lookup"><span data-stu-id="7396e-138">By default, only members of the local administrators group can start, stop, pause, resume or restart a service.</span></span> <span data-ttu-id="7396e-139">Pour accorder aux non-administrateurs la capacité de gérer des services, consultez [Comment accorder aux utilisateurs des droits de gestion des services dans Windows Server 2003](https://support.microsoft.com/kb/325349).</span><span class="sxs-lookup"><span data-stu-id="7396e-139">To grant non-administrators the ability to manage services, see [How to grant users rights to manage services in Windows Server 2003](https://support.microsoft.com/kb/325349).</span></span> <span data-ttu-id="7396e-140">(le processus est semblable sur d'autres versions de Windows).</span><span class="sxs-lookup"><span data-stu-id="7396e-140">(The process is similar on other versions of Windows.)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7396e-141">Lors du démarrage de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], une erreur WMI contenant l'expression « non implémenté [0x80004001] » peut indiquer que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] n'est pas installé sur l'ordinateur cible.</span><span class="sxs-lookup"><span data-stu-id="7396e-141">When starting [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], a WMI error containing the phrase "not implemented [0x80004001]" may indicate that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is not installed on the target computer.</span></span>  
  
  
