---
title: Propriétés de SQL Server Browser (onglet Ouvrir une session) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: c77871ec-c2f4-4e4a-9a10-5aeb4ae70507
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0c1f7d0cfd9e9b05a2a04f3c3e9efba687522298
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695059"
---
# <a name="sql-server-browser-properties-log-on-tab"></a><span data-ttu-id="b12d5-102">Propriétés de SQL Server Browser (onglet Ouvrir une session)</span><span class="sxs-lookup"><span data-stu-id="b12d5-102">SQL Server Browser Properties (Log On Tab)</span></span>
  <span data-ttu-id="b12d5-103">Le programme [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser s'exécute sur le serveur en tant que service.</span><span class="sxs-lookup"><span data-stu-id="b12d5-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser program runs as a service on the server.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="b12d5-104">Browser est à l’écoute des demandes entrantes pour les ressources [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et fournit des informations sur les instances [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installées sur l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="b12d5-104">Browser listens for incoming requests for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resources and provides information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances installed on the computer.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="b12d5-105">Browser est à l’écoute d’un port UDP et accepte les demandes non authentifiées à l’aide du protocole SSRP ( [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Resolution Protocol).</span><span class="sxs-lookup"><span data-stu-id="b12d5-105">Browser listens on a UDP port and accepts unauthenticated requests using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Resolution Protocol (SSRP).</span></span>  
  
 <span data-ttu-id="b12d5-106">La modification du mot de passe d'un compte prend effet immédiatement sans redémarrer le service.</span><span class="sxs-lookup"><span data-stu-id="b12d5-106">Changing the password of an account takes effect immediately without restarting the service.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b12d5-107">Options</span><span class="sxs-lookup"><span data-stu-id="b12d5-107">Options</span></span>  
 <span data-ttu-id="b12d5-108">**Compte système local**</span><span class="sxs-lookup"><span data-stu-id="b12d5-108">**Local System account**</span></span>  
 <span data-ttu-id="b12d5-109">Exécutez le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser dans le contexte de sécurité du compte système local.</span><span class="sxs-lookup"><span data-stu-id="b12d5-109">Run the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service in the security context of the Local System account.</span></span> <span data-ttu-id="b12d5-110">Quand cela est possible, utilisez à la place de celui-ci un compte à faible niveau d'autorisation.</span><span class="sxs-lookup"><span data-stu-id="b12d5-110">When possible, use a low-permission account instead.</span></span>  
  
 <span data-ttu-id="b12d5-111">**Ce compte**</span><span class="sxs-lookup"><span data-stu-id="b12d5-111">**This account**</span></span>  
 <span data-ttu-id="b12d5-112">Spécifiez un compte d'utilisateur local ou de domaine qui utilise l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="b12d5-112">Specify a local or domain user account that uses Windows Authentication.</span></span> <span data-ttu-id="b12d5-113">Nous vous recommandons d'utiliser un compte d'utilisateur de domaine doté d'autorisations minimales pour les services.</span><span class="sxs-lookup"><span data-stu-id="b12d5-113">We recommend using a domain user account with minimal rights for services.</span></span> <span data-ttu-id="b12d5-114">Pour plus d'informations sur la sélection d'un compte, consultez « Configuration des comptes de service Windows » dans la documentation en ligne de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b12d5-114">For information about selecting an account, see "Setting Up Windows Service Accounts" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="b12d5-115">**Parcourir**</span><span class="sxs-lookup"><span data-stu-id="b12d5-115">**Browse**</span></span>  
 <span data-ttu-id="b12d5-116">Recherchez un principal de sécurité utilisateur ou intégré.</span><span class="sxs-lookup"><span data-stu-id="b12d5-116">Browse for a user or built-in security principal.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b12d5-117">Utilisez un compte à faible niveau d'autorisation.</span><span class="sxs-lookup"><span data-stu-id="b12d5-117">Use a low-permission account.</span></span> <span data-ttu-id="b12d5-118">Pour plus d’informations sur les autorisations nécessaires pour le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser, consultez la section relative à la sécurité de la rubrique [Service SQL Server Browser](../../../2014/tools/configuration-manager/sql-server-browser-service.md).</span><span class="sxs-lookup"><span data-stu-id="b12d5-118">For information about the permissions required for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser Service, see the Security section of [SQL Server Browser Service](../../../2014/tools/configuration-manager/sql-server-browser-service.md).</span></span>  
  
 <span data-ttu-id="b12d5-119">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="b12d5-119">**Password**</span></span>  
 <span data-ttu-id="b12d5-120">Entrez le mot de passe du principal de sécurité.</span><span class="sxs-lookup"><span data-stu-id="b12d5-120">Enter the password of the security principal.</span></span>  
  
 <span data-ttu-id="b12d5-121">**Confirmer le mot de passe**</span><span class="sxs-lookup"><span data-stu-id="b12d5-121">**Confirm password**</span></span>  
 <span data-ttu-id="b12d5-122">Confirmez le mot de passe du principal de sécurité.</span><span class="sxs-lookup"><span data-stu-id="b12d5-122">Confirm the password of the security principal.</span></span>  
  
 <span data-ttu-id="b12d5-123">**État du service**</span><span class="sxs-lookup"><span data-stu-id="b12d5-123">**Service status**</span></span>  
 <span data-ttu-id="b12d5-124">Indique si ce service est en cours d'exécution, arrêté ou désactivé.</span><span class="sxs-lookup"><span data-stu-id="b12d5-124">Indicates whether this service is running, stopped, or disabled.</span></span> <span data-ttu-id="b12d5-125">« **…** » indique qu’un changement d’état est en attente.</span><span class="sxs-lookup"><span data-stu-id="b12d5-125">"**...**" indicates a state change is pending.</span></span>  
  
 <span data-ttu-id="b12d5-126">**Start**</span><span class="sxs-lookup"><span data-stu-id="b12d5-126">**Start**</span></span>  
 <span data-ttu-id="b12d5-127">Démarre le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser.</span><span class="sxs-lookup"><span data-stu-id="b12d5-127">Start the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service.</span></span>  
  
 <span data-ttu-id="b12d5-128">**Stop**</span><span class="sxs-lookup"><span data-stu-id="b12d5-128">**Stop**</span></span>  
 <span data-ttu-id="b12d5-129">Arrête le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser.</span><span class="sxs-lookup"><span data-stu-id="b12d5-129">Stop the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service.</span></span>  
  
 <span data-ttu-id="b12d5-130">**Suspendre**</span><span class="sxs-lookup"><span data-stu-id="b12d5-130">**Pause**</span></span>  
 <span data-ttu-id="b12d5-131">Interrompt le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser.</span><span class="sxs-lookup"><span data-stu-id="b12d5-131">Pause the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service.</span></span>  
  
 <span data-ttu-id="b12d5-132">**Reprendre**</span><span class="sxs-lookup"><span data-stu-id="b12d5-132">**Resume**</span></span>  
 <span data-ttu-id="b12d5-133">Reprend un service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser suspendu.</span><span class="sxs-lookup"><span data-stu-id="b12d5-133">Resume a paused [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b12d5-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b12d5-134">See Also</span></span>  
 [<span data-ttu-id="b12d5-135">Service SQL Server Browser</span><span class="sxs-lookup"><span data-stu-id="b12d5-135">SQL Server Browser Service</span></span>](../../../2014/tools/configuration-manager/sql-server-browser-service.md)  
  
  
