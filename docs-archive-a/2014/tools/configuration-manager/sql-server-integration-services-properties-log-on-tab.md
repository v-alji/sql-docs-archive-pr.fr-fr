---
title: Propriétés de SQL Server Integration Services (onglet Ouvrir une session) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: c0eb1b87-6bb0-475e-8492-0fd3c3f910ea
author: stevestein
ms.author: sstein
ms.openlocfilehash: dfef02a82872ea1df25e7ccb8526e488aaa5f406
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705780"
---
# <a name="sql-server-integration-services-properties-log-on-tab"></a><span data-ttu-id="f2d6b-102">Propriétés de SQL Server Integration Services (onglet Ouvrir une session)</span><span class="sxs-lookup"><span data-stu-id="f2d6b-102">SQL Server Integration Services Properties (Log On Tab)</span></span>
  <span data-ttu-id="f2d6b-103">L'onglet **Ouvrir une session** de la boîte de dialogue [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] **Propriétés de** permet de spécifier le compte utilisé par le service [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ainsi que de démarrer et d'arrêter ce service.</span><span class="sxs-lookup"><span data-stu-id="f2d6b-103">Use the **Log On** tab of the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] **Properties** dialog box to specify the account used by the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] service, and to start and stop the service.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f2d6b-104">Options</span><span class="sxs-lookup"><span data-stu-id="f2d6b-104">Options</span></span>  
 <span data-ttu-id="f2d6b-105">**Compte système local**</span><span class="sxs-lookup"><span data-stu-id="f2d6b-105">**Local System account**</span></span>  
 <span data-ttu-id="f2d6b-106">Spécifie un compte système local, qui ne requiert pas de mot de passe.</span><span class="sxs-lookup"><span data-stu-id="f2d6b-106">Specify a local system account, which does not require a password.</span></span> <span data-ttu-id="f2d6b-107">Cependant, le compte système local peut limiter l'interaction du service avec les autres serveurs, en fonction des privilèges accordés au compte.</span><span class="sxs-lookup"><span data-stu-id="f2d6b-107">However, the local system account may restrict the service from interacting with other servers, depending on the privileges granted to the account.</span></span>  
  
 <span data-ttu-id="f2d6b-108">**Ce compte**</span><span class="sxs-lookup"><span data-stu-id="f2d6b-108">**This account**</span></span>  
 <span data-ttu-id="f2d6b-109">Spécifiez un compte d'utilisateur local ou de domaine qui utilise l'authentification [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="f2d6b-109">Specify a local or domain user account that uses [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="f2d6b-110">recommande d'utiliser un compte d'utilisateur de domaine doté d'autorisations minimales pour les services.</span><span class="sxs-lookup"><span data-stu-id="f2d6b-110">recommends using a domain user account with minimal rights for services.</span></span> <span data-ttu-id="f2d6b-111">Pour plus d'informations sur la sélection d'un compte, recherchez dans la documentation en ligne la rubrique « Configuration des comptes de services Windows ».</span><span class="sxs-lookup"><span data-stu-id="f2d6b-111">For information about selecting an account, search Books Online for the topic, "Setting Up Windows Service Accounts."</span></span>  
  
 <span data-ttu-id="f2d6b-112">**Nom du compte**</span><span class="sxs-lookup"><span data-stu-id="f2d6b-112">**Account Name**</span></span>  
 <span data-ttu-id="f2d6b-113">Spécifie le nom de compte d'utilisateur local ou de domaine.</span><span class="sxs-lookup"><span data-stu-id="f2d6b-113">Specify the local or domain user account name.</span></span>  
  
 <span data-ttu-id="f2d6b-114">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="f2d6b-114">**Password**</span></span>  
 <span data-ttu-id="f2d6b-115">Tapez le mot de passe du compte.</span><span class="sxs-lookup"><span data-stu-id="f2d6b-115">Type the password of the account.</span></span>  
  
 <span data-ttu-id="f2d6b-116">**Confirmer le mot de passe**</span><span class="sxs-lookup"><span data-stu-id="f2d6b-116">**Confirm password**</span></span>  
 <span data-ttu-id="f2d6b-117">Tapez de nouveau le mot de passe du compte.</span><span class="sxs-lookup"><span data-stu-id="f2d6b-117">Type the password of the account again.</span></span>  
  
 <span data-ttu-id="f2d6b-118">**Start**</span><span class="sxs-lookup"><span data-stu-id="f2d6b-118">**Start**</span></span>  
 <span data-ttu-id="f2d6b-119">Démarrez le service.</span><span class="sxs-lookup"><span data-stu-id="f2d6b-119">Start the service.</span></span>  
  
 <span data-ttu-id="f2d6b-120">**Stop**</span><span class="sxs-lookup"><span data-stu-id="f2d6b-120">**Stop**</span></span>  
 <span data-ttu-id="f2d6b-121">Arrête le service.</span><span class="sxs-lookup"><span data-stu-id="f2d6b-121">Stop the service.</span></span>  
  
 <span data-ttu-id="f2d6b-122">**Suspendre**</span><span class="sxs-lookup"><span data-stu-id="f2d6b-122">**Pause**</span></span>  
 <span data-ttu-id="f2d6b-123">Suspend le service.</span><span class="sxs-lookup"><span data-stu-id="f2d6b-123">Pause the service.</span></span>  
  
 <span data-ttu-id="f2d6b-124">**Reprendre**</span><span class="sxs-lookup"><span data-stu-id="f2d6b-124">**Resume**</span></span>  
 <span data-ttu-id="f2d6b-125">Reprend un service suspendu.</span><span class="sxs-lookup"><span data-stu-id="f2d6b-125">Resume a paused service.</span></span>  
  
  
