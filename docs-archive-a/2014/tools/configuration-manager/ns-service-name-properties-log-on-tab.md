---
title: '&lt;Propriétés de nom du service NS $ &gt; (onglet ouvrir une session) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 5e6816ec-d4c5-4429-8033-b97427584890
author: stevestein
ms.author: sstein
ms.openlocfilehash: b175895f2385717a67642a41a44dc0d47a1d8d92
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705792"
---
# <a name="nsltservice-namegt-properties-log-on-tab"></a><span data-ttu-id="7612f-102">Propriétés de NS$&lt;service name&gt; (onglet Ouvrir une session)</span><span class="sxs-lookup"><span data-stu-id="7612f-102">NS$&lt;service name&gt; Properties (Log On Tab)</span></span>
  <span data-ttu-id="7612f-103">L'onglet **Ouvrir une session** de la boîte de dialogue **Propriétés de Notification Services** permet de spécifier le compte utilisé par le service [!INCLUDE[ssNS](../../includes/ssns-md.md)] , ainsi que de démarrer et d'arrêter ce service.</span><span class="sxs-lookup"><span data-stu-id="7612f-103">Use the **Log On** tab of the **Notification Services Properties** dialog box to specify the account used by the [!INCLUDE[ssNS](../../includes/ssns-md.md)] service, and to start and stop the service.</span></span>  
  
## <a name="options"></a><span data-ttu-id="7612f-104">Options</span><span class="sxs-lookup"><span data-stu-id="7612f-104">Options</span></span>  
 <span data-ttu-id="7612f-105">**Compte système local**</span><span class="sxs-lookup"><span data-stu-id="7612f-105">**Local System account**</span></span>  
 <span data-ttu-id="7612f-106">Spécifie un compte système local, qui ne requiert pas de mot de passe.</span><span class="sxs-lookup"><span data-stu-id="7612f-106">Specify a local system account, which does not require a password.</span></span> <span data-ttu-id="7612f-107">Cependant, le compte système local peut limiter l'interaction du service avec les autres serveurs, en fonction des privilèges accordés au compte.</span><span class="sxs-lookup"><span data-stu-id="7612f-107">However, the local system account may restrict the service from interacting with other servers, depending on the privileges granted to the account.</span></span>  
  
 <span data-ttu-id="7612f-108">**Ce compte**</span><span class="sxs-lookup"><span data-stu-id="7612f-108">**This account**</span></span>  
 <span data-ttu-id="7612f-109">Spécifiez un compte d'utilisateur local ou de domaine qui utilise l'authentification [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="7612f-109">Specify a local or domain user account that uses [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="7612f-110">recommande d'utiliser un compte d'utilisateur de domaine doté d'autorisations minimales pour les services.</span><span class="sxs-lookup"><span data-stu-id="7612f-110">recommends using a domain user account with minimal rights for services.</span></span> <span data-ttu-id="7612f-111">Pour plus d'informations sur la sélection d'un compte, recherchez dans la documentation en ligne la rubrique « Configuration des comptes de services Windows ».</span><span class="sxs-lookup"><span data-stu-id="7612f-111">For information about selecting an account, search Books Online for the topic, "Setting Up Windows Service Accounts."</span></span>  
  
 <span data-ttu-id="7612f-112">**Nom du compte**</span><span class="sxs-lookup"><span data-stu-id="7612f-112">**Account Name**</span></span>  
 <span data-ttu-id="7612f-113">Spécifie le nom de compte d'utilisateur local ou de domaine.</span><span class="sxs-lookup"><span data-stu-id="7612f-113">Specify the local or domain user account name.</span></span>  
  
 <span data-ttu-id="7612f-114">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="7612f-114">**Password**</span></span>  
 <span data-ttu-id="7612f-115">Tapez le mot de passe du compte.</span><span class="sxs-lookup"><span data-stu-id="7612f-115">Type the password of the account.</span></span>  
  
 <span data-ttu-id="7612f-116">**Confirmer le mot de passe**</span><span class="sxs-lookup"><span data-stu-id="7612f-116">**Confirm password**</span></span>  
 <span data-ttu-id="7612f-117">Tapez de nouveau le mot de passe du compte.</span><span class="sxs-lookup"><span data-stu-id="7612f-117">Type the password of the account again.</span></span>  
  
 <span data-ttu-id="7612f-118">**Start**</span><span class="sxs-lookup"><span data-stu-id="7612f-118">**Start**</span></span>  
 <span data-ttu-id="7612f-119">Démarrez le service.</span><span class="sxs-lookup"><span data-stu-id="7612f-119">Start the service.</span></span>  
  
 <span data-ttu-id="7612f-120">**Stop**</span><span class="sxs-lookup"><span data-stu-id="7612f-120">**Stop**</span></span>  
 <span data-ttu-id="7612f-121">Arrête le service.</span><span class="sxs-lookup"><span data-stu-id="7612f-121">Stop the service.</span></span>  
  
 <span data-ttu-id="7612f-122">**Suspendre**</span><span class="sxs-lookup"><span data-stu-id="7612f-122">**Pause**</span></span>  
 <span data-ttu-id="7612f-123">Suspend le service.</span><span class="sxs-lookup"><span data-stu-id="7612f-123">Pause the service.</span></span>  
  
 <span data-ttu-id="7612f-124">**Reprendre**</span><span class="sxs-lookup"><span data-stu-id="7612f-124">**Resume**</span></span>  
 <span data-ttu-id="7612f-125">Reprend un service suspendu.</span><span class="sxs-lookup"><span data-stu-id="7612f-125">Resume a paused service.</span></span>  
  
  
