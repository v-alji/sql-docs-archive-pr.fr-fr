---
title: Propriétés de Report Server (onglet Ouvrir une session) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: f54be594-f290-4db2-bf18-fd2521728a4a
author: stevestein
ms.author: sstein
ms.openlocfilehash: a2fca58ee9b419613bc8f1dbd325481efc9069c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611425"
---
# <a name="report-server-properties-log-on-tab"></a><span data-ttu-id="d3b35-102">Propriétés de SQL Server Reporting Services (onglet Ouvrir une session)</span><span class="sxs-lookup"><span data-stu-id="d3b35-102">Report Server Properties (Log On Tab)</span></span>
  <span data-ttu-id="d3b35-103">L'onglet **Ouvrir une session** de la boîte de dialogue **Propriétés de SQL Server Reporting Services** permet de spécifier le compte utilisé par le service Report Server, ainsi que de démarrer et d'arrêter ce service.</span><span class="sxs-lookup"><span data-stu-id="d3b35-103">Use the **Log On** tab of the **Report Server Properties** dialog box to specify the account used by the Report Server service, and to start and stop the service.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d3b35-104">Options</span><span class="sxs-lookup"><span data-stu-id="d3b35-104">Options</span></span>  
 <span data-ttu-id="d3b35-105">**Compte système local**</span><span class="sxs-lookup"><span data-stu-id="d3b35-105">**Local System account**</span></span>  
 <span data-ttu-id="d3b35-106">Spécifie un compte système local, qui ne requiert pas de mot de passe.</span><span class="sxs-lookup"><span data-stu-id="d3b35-106">Specify a local system account, which does not require a password.</span></span> <span data-ttu-id="d3b35-107">Cependant, le compte système local peut limiter l'interaction du service avec les autres serveurs, en fonction des privilèges accordés au compte.</span><span class="sxs-lookup"><span data-stu-id="d3b35-107">However, the local system account may restrict the service from interacting with other servers, depending on the privileges granted to the account.</span></span>  
  
 <span data-ttu-id="d3b35-108">**Ce compte**</span><span class="sxs-lookup"><span data-stu-id="d3b35-108">**This account**</span></span>  
 <span data-ttu-id="d3b35-109">Spécifiez un compte d'utilisateur local ou de domaine qui utilise l'authentification [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="d3b35-109">Specify a local or domain user account that uses [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="d3b35-110">recommande d'utiliser un compte d'utilisateur de domaine doté d'autorisations minimales pour les services.</span><span class="sxs-lookup"><span data-stu-id="d3b35-110">recommends using a domain user account with minimal rights for services.</span></span> <span data-ttu-id="d3b35-111">Pour plus d'informations sur la sélection d'un compte, recherchez dans la documentation en ligne la rubrique « Configuration des comptes de services Windows ».</span><span class="sxs-lookup"><span data-stu-id="d3b35-111">For information about selecting an account, search Books Online for the topic Setting Up Windows Service Accounts.</span></span>  
  
 <span data-ttu-id="d3b35-112">**Nom du compte**</span><span class="sxs-lookup"><span data-stu-id="d3b35-112">**Account Name**</span></span>  
 <span data-ttu-id="d3b35-113">Spécifie le nom de compte d'utilisateur local ou de domaine.</span><span class="sxs-lookup"><span data-stu-id="d3b35-113">Specify the local or domain user account name.</span></span>  
  
 <span data-ttu-id="d3b35-114">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="d3b35-114">**Password**</span></span>  
 <span data-ttu-id="d3b35-115">Tapez le mot de passe du compte.</span><span class="sxs-lookup"><span data-stu-id="d3b35-115">Type the password of the account.</span></span>  
  
 <span data-ttu-id="d3b35-116">**Confirmer le mot de passe**</span><span class="sxs-lookup"><span data-stu-id="d3b35-116">**Confirm password**</span></span>  
 <span data-ttu-id="d3b35-117">Tapez de nouveau le mot de passe du compte.</span><span class="sxs-lookup"><span data-stu-id="d3b35-117">Type the password of the account again.</span></span>  
  
 <span data-ttu-id="d3b35-118">**Start**</span><span class="sxs-lookup"><span data-stu-id="d3b35-118">**Start**</span></span>  
 <span data-ttu-id="d3b35-119">Démarrez le service.</span><span class="sxs-lookup"><span data-stu-id="d3b35-119">Start the service.</span></span>  
  
 <span data-ttu-id="d3b35-120">**Stop**</span><span class="sxs-lookup"><span data-stu-id="d3b35-120">**Stop**</span></span>  
 <span data-ttu-id="d3b35-121">Arrête le service.</span><span class="sxs-lookup"><span data-stu-id="d3b35-121">Stop the service.</span></span>  
  
 <span data-ttu-id="d3b35-122">**Suspendre**</span><span class="sxs-lookup"><span data-stu-id="d3b35-122">**Pause**</span></span>  
 <span data-ttu-id="d3b35-123">Suspend le service.</span><span class="sxs-lookup"><span data-stu-id="d3b35-123">Pause the service.</span></span>  
  
 <span data-ttu-id="d3b35-124">**Reprendre**</span><span class="sxs-lookup"><span data-stu-id="d3b35-124">**Resume**</span></span>  
 <span data-ttu-id="d3b35-125">Reprend un service suspendu.</span><span class="sxs-lookup"><span data-stu-id="d3b35-125">Resume a paused service.</span></span>  
  
  
