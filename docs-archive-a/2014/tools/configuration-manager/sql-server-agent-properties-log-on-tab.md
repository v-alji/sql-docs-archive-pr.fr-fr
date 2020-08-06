---
title: Propriétés de SQL Server Agent (onglet Ouvrir une session) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 01fc6329-5d6b-4186-9565-395f375477bb
author: stevestein
ms.author: sstein
ms.openlocfilehash: cd899e8824adacd07fa1d8d7d51b2143d10cadd4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604784"
---
# <a name="sql-server-agent-properties-log-on-tab"></a><span data-ttu-id="6c613-102">Propriétés de l'Agent SQL Server (onglet Ouvrir une session)</span><span class="sxs-lookup"><span data-stu-id="6c613-102">SQL Server Agent Properties (Log On Tab)</span></span>
  <span data-ttu-id="6c613-103">L'onglet **Ouvrir une session** de la boîte de dialogue **Propriétés de l'Agent SQL Server** permet de spécifier le compte utilisé par le service de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , ainsi que de démarrer et d'arrêter ce service.</span><span class="sxs-lookup"><span data-stu-id="6c613-103">Use the **Log On** tab of the **SQL Server Agent Properties** dialog box to specify the account used by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service, and to start and stop the service.</span></span> <span data-ttu-id="6c613-104">La modification du mot de passe d'un compte prend effet immédiatement sans redémarrer le service.</span><span class="sxs-lookup"><span data-stu-id="6c613-104">Changing the password of an account takes effect immediately without restarting the service.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6c613-105">Lorsque vous modifiez le nom du compte utilisé par un service sur une instance cluster, le nouveau compte doit être un membre du groupe de domaine spécifié au cours de l'installation pour le service modifié ou vous devez disposer de l'autorisation d'ajouter des membres à ce groupe.</span><span class="sxs-lookup"><span data-stu-id="6c613-105">When changing the account name used by a service on a clustered instance, the new account must be a member of the domain group specified during setup for the service being changed, or you must have permission to add members to that group.</span></span> <span data-ttu-id="6c613-106">Si vous ne disposez pas de l'autorisation de modifier l'appartenance aux groupes, contactez l'administrateur de domaine.</span><span class="sxs-lookup"><span data-stu-id="6c613-106">If you do not have permission to modify group membership, contact the domain administrator.</span></span>  
  
## <a name="options"></a><span data-ttu-id="6c613-107">Options</span><span class="sxs-lookup"><span data-stu-id="6c613-107">Options</span></span>  
 <span data-ttu-id="6c613-108">**Compte système local**</span><span class="sxs-lookup"><span data-stu-id="6c613-108">**Local System account**</span></span>  
 <span data-ttu-id="6c613-109">Spécifie un compte système local, qui ne requiert pas de mot de passe.</span><span class="sxs-lookup"><span data-stu-id="6c613-109">Specify a local system account, which does not require a password.</span></span> <span data-ttu-id="6c613-110">Cependant, le compte système local peut limiter l'interaction du service avec les autres serveurs, en fonction des privilèges accordés au compte.</span><span class="sxs-lookup"><span data-stu-id="6c613-110">However, the local system account may restrict the service from interacting with other servers, depending on the privileges granted to the account.</span></span>  
  
 <span data-ttu-id="6c613-111">**Ce compte**</span><span class="sxs-lookup"><span data-stu-id="6c613-111">**This account**</span></span>  
 <span data-ttu-id="6c613-112">Spécifiez un compte d'utilisateur local ou de domaine qui utilise l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="6c613-112">Specify a local or domain user account that uses Windows Authentication.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="6c613-113">recommande d'utiliser un compte d'utilisateur de domaine doté d'autorisations minimales pour les services.</span><span class="sxs-lookup"><span data-stu-id="6c613-113">recommends using a domain user account with minimal rights for services.</span></span> <span data-ttu-id="6c613-114">Pour plus d'informations sur la sélection d'un compte, recherchez « Configuration des comptes de service Windows » dans la documentation en ligne.</span><span class="sxs-lookup"><span data-stu-id="6c613-114">For information about selecting an account, search Books Online for "Setting Up Windows Service Accounts."</span></span>  
  
 <span data-ttu-id="6c613-115">**Nom du compte**</span><span class="sxs-lookup"><span data-stu-id="6c613-115">**Account Name**</span></span>  
 <span data-ttu-id="6c613-116">Spécifie le nom de compte d'utilisateur local ou de domaine.</span><span class="sxs-lookup"><span data-stu-id="6c613-116">Specify the local or domain user account name.</span></span>  
  
 <span data-ttu-id="6c613-117">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="6c613-117">**Password**</span></span>  
 <span data-ttu-id="6c613-118">Tapez le mot de passe du compte.</span><span class="sxs-lookup"><span data-stu-id="6c613-118">Type the password of the account.</span></span>  
  
 <span data-ttu-id="6c613-119">**Confirmer le mot de passe**</span><span class="sxs-lookup"><span data-stu-id="6c613-119">**Confirm password**</span></span>  
 <span data-ttu-id="6c613-120">Tapez de nouveau le mot de passe du compte.</span><span class="sxs-lookup"><span data-stu-id="6c613-120">Type the password of the account again.</span></span>  
  
 <span data-ttu-id="6c613-121">**Start**</span><span class="sxs-lookup"><span data-stu-id="6c613-121">**Start**</span></span>  
 <span data-ttu-id="6c613-122">Démarrez le service.</span><span class="sxs-lookup"><span data-stu-id="6c613-122">Start the service.</span></span>  
  
 <span data-ttu-id="6c613-123">**Stop**</span><span class="sxs-lookup"><span data-stu-id="6c613-123">**Stop**</span></span>  
 <span data-ttu-id="6c613-124">Arrête le service.</span><span class="sxs-lookup"><span data-stu-id="6c613-124">Stop the service.</span></span>  
  
 <span data-ttu-id="6c613-125">**Suspendre**</span><span class="sxs-lookup"><span data-stu-id="6c613-125">**Pause**</span></span>  
 <span data-ttu-id="6c613-126">Suspend le service.</span><span class="sxs-lookup"><span data-stu-id="6c613-126">Pause the service.</span></span>  
  
 <span data-ttu-id="6c613-127">**Reprendre**</span><span class="sxs-lookup"><span data-stu-id="6c613-127">**Resume**</span></span>  
 <span data-ttu-id="6c613-128">Reprend un service suspendu.</span><span class="sxs-lookup"><span data-stu-id="6c613-128">Resume a paused service.</span></span>  
  
  
