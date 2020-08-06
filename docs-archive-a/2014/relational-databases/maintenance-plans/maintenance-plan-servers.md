---
title: Plan de maintenance (Serveurs) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.maintplanproperties.server.f1
- sql12.swb.maint.servers.f1
ms.assetid: ac24d1a8-dd2f-4162-b804-c0df1fc1e61d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c971edc9b641846068313f47ca410715ec552014
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603975"
---
# <a name="maintenance-plan-servers"></a><span data-ttu-id="f98a2-102">Plan de maintenance (Serveurs)</span><span class="sxs-lookup"><span data-stu-id="f98a2-102">Maintenance Plan (Servers)</span></span>
  <span data-ttu-id="f98a2-103">La boîte de dialogue **Serveurs** permet de sélectionner les serveurs sur lesquels vous souhaitez exécuter le plan de maintenance.</span><span class="sxs-lookup"><span data-stu-id="f98a2-103">Use the **Servers** dialog box to select the servers where you want to run the maintenance plan.</span></span>  
  
 <span data-ttu-id="f98a2-104">Pour créer un plan de maintenance multiserveur, vous devez configurer un environnement multiserveur contenant un serveur maître et un ou plusieurs serveurs cibles.</span><span class="sxs-lookup"><span data-stu-id="f98a2-104">A multiserver environment containing one master server and one or more target servers must be configured to create a multiserver maintenance plan.</span></span> <span data-ttu-id="f98a2-105">Pour les plans de maintenance multiserveurs, le serveur local doit être configuré comme serveur maître.</span><span class="sxs-lookup"><span data-stu-id="f98a2-105">For multiserver maintenance plans, the local server should be configured as a master server.</span></span> <span data-ttu-id="f98a2-106">Dans les environnements multiserveurs, cette boîte de dialogue affiche le serveur maître **(local)** et tous les serveurs cibles correspondants.</span><span class="sxs-lookup"><span data-stu-id="f98a2-106">In multiserver environments, this dialog box displays the **(local)** master server and all corresponding target servers.</span></span> <span data-ttu-id="f98a2-107">Un travail de l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est créé pour le serveur local.</span><span class="sxs-lookup"><span data-stu-id="f98a2-107">One [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job is created for the local server.</span></span> <span data-ttu-id="f98a2-108">Celui-ci est activé ou désactivé selon que vous avez sélectionné le serveur **(local)** .</span><span class="sxs-lookup"><span data-stu-id="f98a2-108">It is enabled or disabled depending on whether you select the **(local)** server.</span></span> <span data-ttu-id="f98a2-109">Si des serveurs cibles sont sélectionnés, un travail multiserveur est créé et téléchargé vers chacun des serveurs cibles sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="f98a2-109">If target servers are selected, a multiserver job is created and downloaded to each of the selected target servers.</span></span> <span data-ttu-id="f98a2-110">Si aucun serveur cible n'est sélectionné, le travail multiserveur est supprimé.</span><span class="sxs-lookup"><span data-stu-id="f98a2-110">If no target servers are selected, the multiserver job is deleted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f98a2-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f98a2-111">See Also</span></span>  
 <span data-ttu-id="f98a2-112">[Plans de maintenance](maintenance-plans.md) </span><span class="sxs-lookup"><span data-stu-id="f98a2-112">[Maintenance Plans](maintenance-plans.md) </span></span>  
 <span data-ttu-id="f98a2-113">[Créer un environnement multi-serveur](../../ssms/agent/create-a-multiserver-environment.md) </span><span class="sxs-lookup"><span data-stu-id="f98a2-113">[Create a Multiserver Environment](../../ssms/agent/create-a-multiserver-environment.md) </span></span>  
 <span data-ttu-id="f98a2-114">[Créer un serveur maître](../../ssms/agent/make-a-master-server.md) </span><span class="sxs-lookup"><span data-stu-id="f98a2-114">[Make a Master Server](../../ssms/agent/make-a-master-server.md) </span></span>  
 [<span data-ttu-id="f98a2-115">Créer un serveur cible</span><span class="sxs-lookup"><span data-stu-id="f98a2-115">Make a Target Server</span></span>](../../ssms/agent/make-a-target-server.md)  
  
  
