---
title: Erreur WMI 0x8007052f | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- 0x8007052f (WMI error)
ms.assetid: a33f12bd-15c4-42a8-b343-de44c3e87729
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: d6e857e0ccaad9b6f34bbdc9b88aea2e6d7291d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710476"
---
# <a name="wmi-error-0x8007052f"></a><span data-ttu-id="8c424-102">Erreur WMI 0x8007052f</span><span class="sxs-lookup"><span data-stu-id="8c424-102">WMI Error 0x8007052f</span></span>
    
## <a name="details"></a><span data-ttu-id="8c424-103">Détails</span><span class="sxs-lookup"><span data-stu-id="8c424-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8c424-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="8c424-104">Product Name</span></span>|<span data-ttu-id="8c424-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="8c424-105">SQL Server</span></span>|  
|<span data-ttu-id="8c424-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="8c424-106">Event ID</span></span>|<span data-ttu-id="8c424-107">0x8007052f</span><span class="sxs-lookup"><span data-stu-id="8c424-107">0x8007052f</span></span>|  
|<span data-ttu-id="8c424-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="8c424-108">Event Source</span></span>|<span data-ttu-id="8c424-109">Erreur du fournisseur WMI</span><span class="sxs-lookup"><span data-stu-id="8c424-109">WMI Provider Error</span></span>|  
|<span data-ttu-id="8c424-110">Composant</span><span class="sxs-lookup"><span data-stu-id="8c424-110">Component</span></span>|<span data-ttu-id="8c424-111">Gestionnaire de configuration SQL Server</span><span class="sxs-lookup"><span data-stu-id="8c424-111">SQL Server Configuration Manager</span></span>|  
|<span data-ttu-id="8c424-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="8c424-112">Symbolic Name</span></span>|<span data-ttu-id="8c424-113">N/D</span><span class="sxs-lookup"><span data-stu-id="8c424-113">NA</span></span>|  
|<span data-ttu-id="8c424-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="8c424-114">Message Text</span></span>|<span data-ttu-id="8c424-115">Échec d'ouverture de session : restriction de compte d'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8c424-115">Logon failure: user account restriction.</span></span> <span data-ttu-id="8c424-116">Parmi les explications possibles figurent les mots de passe vides qui ne sont pas autorisés, les restrictions liées aux heures de connexion ou l'application d'une restriction de stratégie.</span><span class="sxs-lookup"><span data-stu-id="8c424-116">Possible reasons are blank passwords not allowed, login hour restrictions, or a policy restriction has been enforced.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8c424-117">Explication</span><span class="sxs-lookup"><span data-stu-id="8c424-117">Explanation</span></span>  
 <span data-ttu-id="8c424-118">Cette erreur peut se produire lors de l'utilisation du Gestionnaire de configuration [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] pour basculer vers les comptes intégrés (Service réseau, Service local ou Système Local) lorsque [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] est exécuté sur un cluster de serveurs Windows Server ou un contrôleur de domaine Windows Server.</span><span class="sxs-lookup"><span data-stu-id="8c424-118">This error can occur when using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Configuration Manager to switch to the built-in accounts (Network Service, Local Service, or Local System) when [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] is running on a Windows Server Cluster or Windows Server Domain Controller.</span></span> <span data-ttu-id="8c424-119">N'exécutez pas de services sous les comptes intégrés sur un cluster de serveurs Windows Server ou un contrôleur de domaine Windows Server.</span><span class="sxs-lookup"><span data-stu-id="8c424-119">Do not run services under built-in accounts on a Windows Server Cluster or Windows Server Domain Controller.</span></span> <span data-ttu-id="8c424-120">Pour obtenir des recommandations sur les comptes de service, consultez la rubrique « Configuration des comptes de service Windows » dans la documentation en ligne de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8c424-120">For recommendations on service accounts, see the topic Setting Up Windows Service Accounts in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8c424-121">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="8c424-121">User Action</span></span>  
 <span data-ttu-id="8c424-122">Configurez [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] pour utiliser un compte de domaine.</span><span class="sxs-lookup"><span data-stu-id="8c424-122">Configure [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to use a domain account.</span></span>  
  
  
