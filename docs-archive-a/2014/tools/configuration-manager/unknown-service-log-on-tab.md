---
title: Service inconnu (onglet ouvrir une session) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: e9b35cb5-d8ae-42ea-b59e-deedc99c4823
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0bda49cd95475d4f922f41ebe1701a814c3f60fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601867"
---
# <a name="unknown-service-log-on-tab"></a><span data-ttu-id="a9f36-102">Service inconnu (onglet Ouvrir une session)</span><span class="sxs-lookup"><span data-stu-id="a9f36-102">Unknown Service (Log On Tab)</span></span>
  [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="a9f36-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Gestionnaire de configuration n'est pas en mesure d'identifier ce service.</span><span class="sxs-lookup"><span data-stu-id="a9f36-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager is unable to identify this service.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="a9f36-104">reçoit des informations de service émanant du fournisseur WMI installé sur l'ordinateur exécutant le service.</span><span class="sxs-lookup"><span data-stu-id="a9f36-104">Configuration Manager receives service information from the WMI provider on the computer running the service.</span></span> <span data-ttu-id="a9f36-105">Une erreur s'est produite lors de la lecture des propriétés du service ou celles-ci sont incomplètes.</span><span class="sxs-lookup"><span data-stu-id="a9f36-105">Either there was an error while reading the service properties, or the service properties are not complete.</span></span> <span data-ttu-id="a9f36-106">Pour résoudre le problème, essayez de fermer puis de rouvrir le Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , ou vérifiez le fournisseur WMI installé sur l'ordinateur exécutant le service.</span><span class="sxs-lookup"><span data-stu-id="a9f36-106">To resolve the problem, try closing and reopening [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, or check the WMI provider on the computer running the service.</span></span>  
  
 <span data-ttu-id="a9f36-107">Le fournisseur WMI est un composant Windows.</span><span class="sxs-lookup"><span data-stu-id="a9f36-107">The WMI provider is a Windows component.</span></span> <span data-ttu-id="a9f36-108">Pour plus d'informations sur la manière de vérifier les autorisations sur le fournisseur WMI, consultez « Procédure : configurer WMI pour afficher l'état du serveur dans les outils SQL Server », dans la documentation en ligne.</span><span class="sxs-lookup"><span data-stu-id="a9f36-108">For information on how to check permissions on the WMI provider, see "How to: Configure WMI to Show Server Status in SQL Server Tools" in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="a9f36-109">Si vous pensez que vous examinez le service approprié, utilisez l'onglet **Ouvrir une session** de la boîte de dialogue **Propriétés de Service inconnu** pour spécifier le compte utilisé par ce service, ainsi que pour démarrer et arrêter le service.</span><span class="sxs-lookup"><span data-stu-id="a9f36-109">If you believe you are viewing the correct service, use the **Log On** tab of the **Unknown Service Properties** dialog box to specify the account used by this service, and to start and stop the service.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a9f36-110">Options</span><span class="sxs-lookup"><span data-stu-id="a9f36-110">Options</span></span>  
 <span data-ttu-id="a9f36-111">**Compte système local**</span><span class="sxs-lookup"><span data-stu-id="a9f36-111">**Local System account**</span></span>  
 <span data-ttu-id="a9f36-112">Spécifie un compte système local, qui ne requiert pas de mot de passe.</span><span class="sxs-lookup"><span data-stu-id="a9f36-112">Specify a local system account, which does not require a password.</span></span> <span data-ttu-id="a9f36-113">Toutefois, le compte système local peut empêcher le service d'interagir avec les autres serveurs, en fonction des privilèges accordés au compte.</span><span class="sxs-lookup"><span data-stu-id="a9f36-113">However, the local system account may prevent the service from interacting with other servers, depending on the privileges granted to the account.</span></span>  
  
 <span data-ttu-id="a9f36-114">**Ce compte**</span><span class="sxs-lookup"><span data-stu-id="a9f36-114">**This account**</span></span>  
 <span data-ttu-id="a9f36-115">Spécifiez un compte d'utilisateur local ou de domaine qui utilise l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="a9f36-115">Specify a local or domain user account that uses Windows Authentication.</span></span> <span data-ttu-id="a9f36-116">Nous vous recommandons d'utiliser un compte d'utilisateur de domaine doté d'autorisations minimales pour les services.</span><span class="sxs-lookup"><span data-stu-id="a9f36-116">We recommend using a domain user account with minimal rights for services.</span></span> <span data-ttu-id="a9f36-117">Pour plus d'informations sur la sélection d'un compte, consultez « Configuration des comptes de service Windows » dans la documentation en ligne de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a9f36-117">For information about selecting an account, "Setting Up Windows Service Accounts" in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="a9f36-118">**Nom du compte**</span><span class="sxs-lookup"><span data-stu-id="a9f36-118">**Account Name**</span></span>  
 <span data-ttu-id="a9f36-119">Spécifie le nom de compte d'utilisateur local ou de domaine.</span><span class="sxs-lookup"><span data-stu-id="a9f36-119">Specify the local or domain user account name.</span></span>  
  
 <span data-ttu-id="a9f36-120">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="a9f36-120">**Password**</span></span>  
 <span data-ttu-id="a9f36-121">Tapez le mot de passe du compte.</span><span class="sxs-lookup"><span data-stu-id="a9f36-121">Type the password of the account.</span></span>  
  
 <span data-ttu-id="a9f36-122">**Confirmer le mot de passe**</span><span class="sxs-lookup"><span data-stu-id="a9f36-122">**Confirm password**</span></span>  
 <span data-ttu-id="a9f36-123">Tapez de nouveau le mot de passe du compte.</span><span class="sxs-lookup"><span data-stu-id="a9f36-123">Type the password of the account again.</span></span>  
  
 <span data-ttu-id="a9f36-124">**Start**</span><span class="sxs-lookup"><span data-stu-id="a9f36-124">**Start**</span></span>  
 <span data-ttu-id="a9f36-125">Démarrez le service.</span><span class="sxs-lookup"><span data-stu-id="a9f36-125">Start the service.</span></span>  
  
 <span data-ttu-id="a9f36-126">**Stop**</span><span class="sxs-lookup"><span data-stu-id="a9f36-126">**Stop**</span></span>  
 <span data-ttu-id="a9f36-127">Arrête le service.</span><span class="sxs-lookup"><span data-stu-id="a9f36-127">Stop the service.</span></span>  
  
 <span data-ttu-id="a9f36-128">**Suspendre**</span><span class="sxs-lookup"><span data-stu-id="a9f36-128">**Pause**</span></span>  
 <span data-ttu-id="a9f36-129">Suspend le service.</span><span class="sxs-lookup"><span data-stu-id="a9f36-129">Pause the service.</span></span>  
  
 <span data-ttu-id="a9f36-130">**Reprendre**</span><span class="sxs-lookup"><span data-stu-id="a9f36-130">**Resume**</span></span>  
 <span data-ttu-id="a9f36-131">Reprend un service suspendu.</span><span class="sxs-lookup"><span data-stu-id="a9f36-131">Resume a paused service.</span></span>  
  
  
