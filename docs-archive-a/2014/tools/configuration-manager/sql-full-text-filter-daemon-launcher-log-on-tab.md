---
title: Lanceur de démon de filtre de texte intégral SQL (onglet Ouvrir une session) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 13e260f9-a75f-430b-88a3-959ddcead8fe
author: stevestein
ms.author: sstein
ms.openlocfilehash: cb3f23907e96214929617bf2923e46148c0ab1f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613718"
---
# <a name="sql-full-text-filter-daemon-launcher-log-on-tab"></a><span data-ttu-id="14ec0-102">Lanceur de démon de filtre de texte intégral SQL (onglet Ouvrir une session)</span><span class="sxs-lookup"><span data-stu-id="14ec0-102">SQL Full-text Filter Daemon Launcher (Log On Tab)</span></span>
  <span data-ttu-id="14ec0-103">À compter de [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], le lanceur de démon de filtre de texte intégral SQL (service de lancement FDHOST) est utilisé par la recherche en texte intégral [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="14ec0-103">Beginning in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], the SQL Full-text Filter Daemon Launcher (FDHOST Launcher) service is used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] full-text search.</span></span> <span data-ttu-id="14ec0-104">Ce service doit être en cours d'exécution pendant que vous utilisez la recherche en texte intégral.</span><span class="sxs-lookup"><span data-stu-id="14ec0-104">This service must be running if you use full-text search.</span></span> <span data-ttu-id="14ec0-105">Pour plus d'informations sur les processus hôte de démon de filtre, consultez « Architecture de la recherche en texte intégral » dans la documentation en ligne de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="14ec0-105">For information about the filter daemon host processes, see "Full-Text Search Architecture" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="14ec0-106">L'onglet **Ouvrir une session** de la boîte de dialogue **Propriétés de Lanceur de démon de filtre de texte intégral SQL** permet de spécifier le compte utilisé par le service de recherche en texte intégral [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , de modifier le mot de passe d'un compte, ainsi que de démarrer et d'arrêter ce service.</span><span class="sxs-lookup"><span data-stu-id="14ec0-106">Use the **Log On** tab of the **SQL Full-text Filter Daemon Launcher  Properties** dialog box to specify the account used by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] full-text service, to change the password of an account, and to start and stop the service.</span></span> <span data-ttu-id="14ec0-107">La modification du mot de passe d'un compte prend effet après le redémarrage du service.</span><span class="sxs-lookup"><span data-stu-id="14ec0-107">Changing the password of an account takes affect after restarting the service.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="14ec0-108">Lorsque vous modifiez le nom du compte utilisé par un service sur une instance en cluster, soit le nouveau compte doit être un membre du groupe de domaine spécifié au cours de l'installation pour le service, soit vous devez disposer de l'autorisation d'ajouter des membres à ce groupe.</span><span class="sxs-lookup"><span data-stu-id="14ec0-108">When changing the account name used by a service on a clustered instance, either the new account must be a member of the domain group specified during setup for the service, or you must have permission to add members to that group.</span></span> <span data-ttu-id="14ec0-109">Si vous ne disposez pas de l'autorisation de modifier l'appartenance aux groupes, contactez l'administrateur de domaine.</span><span class="sxs-lookup"><span data-stu-id="14ec0-109">If you do not have permission to modify group membership, contact the domain administrator.</span></span>  
>   
>  <span data-ttu-id="14ec0-110">Pour plus d'informations sur la sélection d'un compte pour exécuter le service, consultez « Configuration des comptes de service Windows » dans la documentation en ligne de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="14ec0-110">For more information about selecting an account to run the service, see "Setting Up Windows Service Accounts" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="options"></a><span data-ttu-id="14ec0-111">Options</span><span class="sxs-lookup"><span data-stu-id="14ec0-111">Options</span></span>  
 <span data-ttu-id="14ec0-112">**Compte intégré**</span><span class="sxs-lookup"><span data-stu-id="14ec0-112">**Built-in account**</span></span>  
 <span data-ttu-id="14ec0-113">**Système local**</span><span class="sxs-lookup"><span data-stu-id="14ec0-113">**Local System**</span></span>  
 <span data-ttu-id="14ec0-114">Spécifiez le compte système local.</span><span class="sxs-lookup"><span data-stu-id="14ec0-114">Specify the local system account.</span></span> <span data-ttu-id="14ec0-115">Ce compte ne nécessite pas de mot de passe.</span><span class="sxs-lookup"><span data-stu-id="14ec0-115">This account does not require a password.</span></span> <span data-ttu-id="14ec0-116">Toutefois, le compte système local peut empêcher le service d'interagir avec les autres serveurs, en fonction des privilèges accordés au compte.</span><span class="sxs-lookup"><span data-stu-id="14ec0-116">However, the local system account may prevent the service from interacting with other servers, depending on the privileges granted to the account.</span></span>  
  
 <span data-ttu-id="14ec0-117">**Service local**</span><span class="sxs-lookup"><span data-stu-id="14ec0-117">**Local Service**</span></span>  
 <span data-ttu-id="14ec0-118">Spécifiez le compte de service local.</span><span class="sxs-lookup"><span data-stu-id="14ec0-118">Specify the local service account.</span></span> <span data-ttu-id="14ec0-119">Ce compte ne nécessite pas de mot de passe.</span><span class="sxs-lookup"><span data-stu-id="14ec0-119">This account does not require a password.</span></span> <span data-ttu-id="14ec0-120">Cependant, le compte de service local peut empêcher le service d'interagir avec les autres serveurs, en fonction des privilèges accordés au compte.</span><span class="sxs-lookup"><span data-stu-id="14ec0-120">However, the local service account may prevent the service from interacting with other servers, depending on the privileges granted to the account.</span></span>  
  
 <span data-ttu-id="14ec0-121">**Service réseau**</span><span class="sxs-lookup"><span data-stu-id="14ec0-121">**Network Service**</span></span>  
 <span data-ttu-id="14ec0-122">Il est recommandé de ne pas utiliser le compte de service réseau pour les services [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="14ec0-122">We recommend that you do not use the Network Service account for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services or the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent services.</span></span> <span data-ttu-id="14ec0-123">Les comptes d'utilisateur local et d'utilisateur de domaine conviennent mieux à ces services.</span><span class="sxs-lookup"><span data-stu-id="14ec0-123">Local User or Domain User accounts are more appropriate for these services.</span></span>  
  
 <span data-ttu-id="14ec0-124">**Ce compte**</span><span class="sxs-lookup"><span data-stu-id="14ec0-124">**This account**</span></span>  
 <span data-ttu-id="14ec0-125">Spécifiez un compte d'utilisateur local ou de domaine qui utilise l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="14ec0-125">Specify a local or domain user account that uses Windows Authentication.</span></span> <span data-ttu-id="14ec0-126">Nous vous recommandons d'utiliser un compte d'utilisateur de domaine doté d'autorisations minimales pour les services.</span><span class="sxs-lookup"><span data-stu-id="14ec0-126">We recommend that you use a domain user account that has minimal rights for services.</span></span>  
  
 <span data-ttu-id="14ec0-127">**Nom du compte**</span><span class="sxs-lookup"><span data-stu-id="14ec0-127">**Account Name**</span></span>  
 <span data-ttu-id="14ec0-128">Spécifie le nom de compte d'utilisateur local ou de domaine.</span><span class="sxs-lookup"><span data-stu-id="14ec0-128">Specify the local or domain user account name.</span></span>  
  
 <span data-ttu-id="14ec0-129">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="14ec0-129">**Password**</span></span>  
 <span data-ttu-id="14ec0-130">Tapez le mot de passe du compte.</span><span class="sxs-lookup"><span data-stu-id="14ec0-130">Type the password of the account.</span></span>  
  
 <span data-ttu-id="14ec0-131">**Confirmer le mot de passe**</span><span class="sxs-lookup"><span data-stu-id="14ec0-131">**Confirm password**</span></span>  
 <span data-ttu-id="14ec0-132">Tapez de nouveau le mot de passe du compte.</span><span class="sxs-lookup"><span data-stu-id="14ec0-132">Type the password of the account again.</span></span>  
  
 <span data-ttu-id="14ec0-133">**Start**</span><span class="sxs-lookup"><span data-stu-id="14ec0-133">**Start**</span></span>  
 <span data-ttu-id="14ec0-134">Démarrez le service.</span><span class="sxs-lookup"><span data-stu-id="14ec0-134">Start the service.</span></span>  
  
 <span data-ttu-id="14ec0-135">**Stop**</span><span class="sxs-lookup"><span data-stu-id="14ec0-135">**Stop**</span></span>  
 <span data-ttu-id="14ec0-136">Arrête le service.</span><span class="sxs-lookup"><span data-stu-id="14ec0-136">Stop the service.</span></span>  
  
 <span data-ttu-id="14ec0-137">**Suspendre**</span><span class="sxs-lookup"><span data-stu-id="14ec0-137">**Pause**</span></span>  
 <span data-ttu-id="14ec0-138">Suspend le service.</span><span class="sxs-lookup"><span data-stu-id="14ec0-138">Pause the service.</span></span> <span data-ttu-id="14ec0-139">Non disponible pour ce service.</span><span class="sxs-lookup"><span data-stu-id="14ec0-139">Not available for this service.</span></span>  
  
 <span data-ttu-id="14ec0-140">**Reprendre**</span><span class="sxs-lookup"><span data-stu-id="14ec0-140">**Resume**</span></span>  
 <span data-ttu-id="14ec0-141">Reprend un service suspendu.</span><span class="sxs-lookup"><span data-stu-id="14ec0-141">Resume a paused service.</span></span>  
  
  
