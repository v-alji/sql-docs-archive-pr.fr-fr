---
title: MSSQLSERVER_17883 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17883 (Database Engine error)
ms.assetid: adaf1c04-e397-4a69-90b8-9353a37277ea
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 46488fb6f7adac2c1109871f2aad4c79352829ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696883"
---
# <a name="mssqlserver_17883"></a><span data-ttu-id="ddcfe-102">MSSQLSERVER_17883</span><span class="sxs-lookup"><span data-stu-id="ddcfe-102">MSSQLSERVER_17883</span></span>
    
## <a name="details"></a><span data-ttu-id="ddcfe-103">Détails</span><span class="sxs-lookup"><span data-stu-id="ddcfe-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ddcfe-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="ddcfe-104">Product Name</span></span>|<span data-ttu-id="ddcfe-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="ddcfe-105">SQL Server</span></span>|  
|<span data-ttu-id="ddcfe-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="ddcfe-106">Event ID</span></span>|<span data-ttu-id="ddcfe-107">17883</span><span class="sxs-lookup"><span data-stu-id="ddcfe-107">17883</span></span>|  
|<span data-ttu-id="ddcfe-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="ddcfe-108">Event Source</span></span>|<span data-ttu-id="ddcfe-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="ddcfe-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="ddcfe-110">Composant</span><span class="sxs-lookup"><span data-stu-id="ddcfe-110">Component</span></span>|<span data-ttu-id="ddcfe-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="ddcfe-111">SQLEngine</span></span>|  
|<span data-ttu-id="ddcfe-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="ddcfe-112">Symbolic Name</span></span>|<span data-ttu-id="ddcfe-113">SRV_SCHEDULER_NONYIELDING</span><span class="sxs-lookup"><span data-stu-id="ddcfe-113">SRV_SCHEDULER_NONYIELDING</span></span>|  
|<span data-ttu-id="ddcfe-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="ddcfe-114">Message Text</span></span>|<span data-ttu-id="ddcfe-115">Le processus %ld:%ld:%ld (0x%lx) travail 0x%p semble être improductif dans le Planificateur %ld.</span><span class="sxs-lookup"><span data-stu-id="ddcfe-115">Process %ld:%ld:%ld (0x%lx) Worker 0x%p appears to be non-yielding on Scheduler %ld.</span></span> <span data-ttu-id="ddcfe-116">Heure de création du thread : %I64d.</span><span class="sxs-lookup"><span data-stu-id="ddcfe-116">Thread creation time: %I64d.</span></span> <span data-ttu-id="ddcfe-117">Utilisation approximative de l'UC pour ce thread : noyau %I64d ms, utilisateur %I64d ms.</span><span class="sxs-lookup"><span data-stu-id="ddcfe-117">Approx Thread CPU Used: kernel %I64d ms, user %I64d ms.</span></span> <span data-ttu-id="ddcfe-118">Utilisation du processus %d%%.</span><span class="sxs-lookup"><span data-stu-id="ddcfe-118">Process Utilization %d%%.</span></span> <span data-ttu-id="ddcfe-119">Système inactif %d%%.</span><span class="sxs-lookup"><span data-stu-id="ddcfe-119">System Idle %d%%.</span></span> <span data-ttu-id="ddcfe-120">Intervalle : %I64d ms.</span><span class="sxs-lookup"><span data-stu-id="ddcfe-120">Interval: %I64d ms.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ddcfe-121">Explication</span><span class="sxs-lookup"><span data-stu-id="ddcfe-121">Explanation</span></span>  
 <span data-ttu-id="ddcfe-122">Indique un problème possible avec un thread improductif dans un Planificateur.</span><span class="sxs-lookup"><span data-stu-id="ddcfe-122">Indicates that there is a possible problem with a thread not yielding on a scheduler.</span></span>  <span data-ttu-id="ddcfe-123">Il peut s'agir d'un bogue dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou si le nombre de cycles à exécuter par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est insuffisant.</span><span class="sxs-lookup"><span data-stu-id="ddcfe-123">This could be caused by a bug in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is not getting enough cycles to execute.</span></span>  <span data-ttu-id="ddcfe-124">Cette erreur peut se résoudre si le thread finit par être productif.</span><span class="sxs-lookup"><span data-stu-id="ddcfe-124">This error could go away if the thread eventually yields.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ddcfe-125">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="ddcfe-125">User Action</span></span>  
 <span data-ttu-id="ddcfe-126">Si la charge excessive sur le système réduit la charge en général, contactez le service de support technique Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ddcfe-126">If excessive load on system reduce load otherwise contact Microsoft Customer Support Services.</span></span>  
  
  
