---
title: Propriétés d’Analysis Server (onglet Ouvrir une session) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: a82e0c98-efaa-4b0b-9582-3c879ee42444
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8db5576e48e7f12ef1733175875d2cd065e376fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708875"
---
# <a name="analysis-server-properties-log-on-tab"></a><span data-ttu-id="6420b-102">Propriétés de Analysis Server (onglet Ouvrir une session)</span><span class="sxs-lookup"><span data-stu-id="6420b-102">Analysis Server Properties (Log On Tab)</span></span>
  <span data-ttu-id="6420b-103">L'onglet **Ouvrir une session** de la boîte de dialogue **Propriétés de Analysis Server** permet de spécifier le compte utilisé par le service [!INCLUDE[ssAS](../../includes/ssas-md.md)] , ainsi que de démarrer et d'arrêter ce service.</span><span class="sxs-lookup"><span data-stu-id="6420b-103">Use the **Log On** tab of the **Analysis Server Properties** dialog box to specify the account used by the [!INCLUDE[ssAS](../../includes/ssas-md.md)] service, and to start and stop the service.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6420b-104">Lorsque vous modifiez le **Nom du compte** utilisé par un service sur une instance cluster, le nouveau compte doit être un membre du groupe de domaine spécifié au cours de l'installation pour le service modifié ou vous devez posséder l'autorisation d'ajouter des membres à ce groupe.</span><span class="sxs-lookup"><span data-stu-id="6420b-104">When changing the **Account Name** used by a service on a clustered instance, the new account must either be a member of the domain group specified during setup for the service being changed, or you must have permission to add members to that group.</span></span> <span data-ttu-id="6420b-105">Si vous ne disposez pas de l'autorisation de modifier l'appartenance aux groupes, contactez l'administrateur de domaine.</span><span class="sxs-lookup"><span data-stu-id="6420b-105">If you do not have permission to modify group membership, contact the domain administrator.</span></span>  
  
## <a name="options"></a><span data-ttu-id="6420b-106">Options</span><span class="sxs-lookup"><span data-stu-id="6420b-106">Options</span></span>  
 <span data-ttu-id="6420b-107">**Compte système local**</span><span class="sxs-lookup"><span data-stu-id="6420b-107">**Local System account**</span></span>  
 <span data-ttu-id="6420b-108">Spécifie un compte système local, qui ne requiert pas de mot de passe.</span><span class="sxs-lookup"><span data-stu-id="6420b-108">Specify a local system account, which does not require a password.</span></span> <span data-ttu-id="6420b-109">Cependant, le compte système local peut limiter l'interaction du service avec les autres serveurs, en fonction des privilèges accordés au compte.</span><span class="sxs-lookup"><span data-stu-id="6420b-109">However, the local system account may restrict the service from interacting with other servers, depending on the privileges granted to the account.</span></span>  
  
 <span data-ttu-id="6420b-110">**Ce compte**</span><span class="sxs-lookup"><span data-stu-id="6420b-110">**This account**</span></span>  
 <span data-ttu-id="6420b-111">Spécifiez un compte d'utilisateur local ou de domaine qui utilise l'authentification [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="6420b-111">Specify a local or domain user account that uses [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="6420b-112">recommande d'utiliser un compte d'utilisateur de domaine doté d'autorisations minimales pour les services.</span><span class="sxs-lookup"><span data-stu-id="6420b-112">recommends using a domain user account with minimal rights for services.</span></span> <span data-ttu-id="6420b-113">Pour plus d'informations sur la sélection d'un compte, recherchez dans la documentation en ligne la rubrique « Configuration des comptes de services Windows ».</span><span class="sxs-lookup"><span data-stu-id="6420b-113">For information about selecting an account, search Books Online for the topic Setting Up Windows Service Accounts.</span></span>  
  
 <span data-ttu-id="6420b-114">**Nom du compte**</span><span class="sxs-lookup"><span data-stu-id="6420b-114">**Account Name**</span></span>  
 <span data-ttu-id="6420b-115">Spécifie le nom de compte d'utilisateur local ou de domaine.</span><span class="sxs-lookup"><span data-stu-id="6420b-115">Specify the local or domain user account name.</span></span>  
  
 <span data-ttu-id="6420b-116">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="6420b-116">**Password**</span></span>  
 <span data-ttu-id="6420b-117">Tapez le mot de passe du compte.</span><span class="sxs-lookup"><span data-stu-id="6420b-117">Type the password of the account.</span></span>  
  
 <span data-ttu-id="6420b-118">**Confirmer le mot de passe**</span><span class="sxs-lookup"><span data-stu-id="6420b-118">**Confirm password**</span></span>  
 <span data-ttu-id="6420b-119">Tapez de nouveau le mot de passe du compte.</span><span class="sxs-lookup"><span data-stu-id="6420b-119">Type the password of the account again.</span></span>  
  
 <span data-ttu-id="6420b-120">**Start**</span><span class="sxs-lookup"><span data-stu-id="6420b-120">**Start**</span></span>  
 <span data-ttu-id="6420b-121">Démarrez le service.</span><span class="sxs-lookup"><span data-stu-id="6420b-121">Start the service.</span></span>  
  
 <span data-ttu-id="6420b-122">**Stop**</span><span class="sxs-lookup"><span data-stu-id="6420b-122">**Stop**</span></span>  
 <span data-ttu-id="6420b-123">Arrête le service.</span><span class="sxs-lookup"><span data-stu-id="6420b-123">Stop the service.</span></span>  
  
 <span data-ttu-id="6420b-124">**Suspendre**</span><span class="sxs-lookup"><span data-stu-id="6420b-124">**Pause**</span></span>  
 <span data-ttu-id="6420b-125">Suspend le service.</span><span class="sxs-lookup"><span data-stu-id="6420b-125">Pause the service.</span></span>  
  
 <span data-ttu-id="6420b-126">**Reprendre**</span><span class="sxs-lookup"><span data-stu-id="6420b-126">**Resume**</span></span>  
 <span data-ttu-id="6420b-127">Reprend un service suspendu.</span><span class="sxs-lookup"><span data-stu-id="6420b-127">Resume a paused service.</span></span>  
  
  
