---
title: Utiliser la messagerie de base de données plutôt que SQL Mail | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: b08df7be-d8be-4184-a661-38ec0ac85cd1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a6a957b65975645bdeb9f55faee4e650b53718b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603436"
---
# <a name="use-database-mail-instead-of-sql-mail"></a><span data-ttu-id="1bb23-102">Utiliser la messagerie de base de données plutôt que SQL Mail</span><span class="sxs-lookup"><span data-stu-id="1bb23-102">Use Database Mail Instead of SQL Mail</span></span>
  <span data-ttu-id="1bb23-103">Cette règle vérifie dans l'affichage catalogue sys.configurations si l'option de configuration au niveau serveur sqlmail XPs est définie sur ON.</span><span class="sxs-lookup"><span data-stu-id="1bb23-103">This rule checks the sys.configurations catalog view to determine whether the SQL Mail XPs server-wide configuration option is set to ON.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="1bb23-104">Meilleures pratiques recommandées</span><span class="sxs-lookup"><span data-stu-id="1bb23-104">Best Practices Recommendations</span></span>  
 <span data-ttu-id="1bb23-105">SQL Mail sera supprimé dans une version ultérieure de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1bb23-105">SQL Mail will be removed in a future version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="1bb23-106">Évitez d'utiliser cette fonctionnalité dans de nouveaux travaux de développement, et prévoyez de modifier les applications qui utilisent actuellement cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="1bb23-106">Avoid using this feature in new development work, and plan to modify applications that currently use this feature.</span></span> <span data-ttu-id="1bb23-107">Pour envoyer du courrier, utilisez la messagerie de base de données.</span><span class="sxs-lookup"><span data-stu-id="1bb23-107">To send mail, use Database Mail.</span></span>  
  
 <span data-ttu-id="1bb23-108">SQL Mail s'exécute dans un processus interne à un service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1bb23-108">SQL Mail runs in-process to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span> <span data-ttu-id="1bb23-109">Si SQL Mail arrête de fonctionner, il en sera de même pour le serveur.</span><span class="sxs-lookup"><span data-stu-id="1bb23-109">If SQL Mail goes down, so does the server.</span></span> <span data-ttu-id="1bb23-110">La messagerie de base de données s'exécute en dehors de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dans un processus distinct, est évolutive et ne requiert pas l'installation des composants clients MAPI étendus sur le serveur de production.</span><span class="sxs-lookup"><span data-stu-id="1bb23-110">Database Mail runs outside [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in a separate process, is scalable, and does not require Extended MAPI client components to be installed on the production server.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="1bb23-111">Pour plus d'informations</span><span class="sxs-lookup"><span data-stu-id="1bb23-111">For More Information</span></span>  
 [<span data-ttu-id="1bb23-112">Messagerie de base de données</span><span class="sxs-lookup"><span data-stu-id="1bb23-112">Database Mail</span></span>](../database-mail/database-mail.md)  
  
## <a name="see-also"></a><span data-ttu-id="1bb23-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1bb23-113">See Also</span></span>  
 [<span data-ttu-id="1bb23-114">Contrôler et appliquer les bonnes pratiques à l’aide de la gestion basée sur des stratégies</span><span class="sxs-lookup"><span data-stu-id="1bb23-114">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
