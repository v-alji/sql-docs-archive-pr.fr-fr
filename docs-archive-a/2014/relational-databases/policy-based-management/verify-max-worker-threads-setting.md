---
title: Vérifier le paramètre de l’option Max Worker Threads | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 2d94adfd-3ba1-493a-b29a-b436f9d583df
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5dbffb87f58d2beb633f43ff18680222ea62cf5e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603434"
---
# <a name="verify-max-worker-threads-setting"></a><span data-ttu-id="a9a5f-102">Vérifier le paramètre de l'option Max Worker Threads</span><span class="sxs-lookup"><span data-stu-id="a9a5f-102">Verify Max Worker Threads Setting</span></span>
  <span data-ttu-id="a9a5f-103">Cette règle vérifie que le paramètre de l'option de serveur max worker threads (nombre maximum de threads de travail) est correct.</span><span class="sxs-lookup"><span data-stu-id="a9a5f-103">This rule checks the max worker threads server option for potentially incorrect settings.</span></span> <span data-ttu-id="a9a5f-104">L'affectation d'une valeur faible à l'option max worker threads peut empêcher qu'un nombre suffisant de threads traite les demandes entrantes des clients en temps voulu et peut entraîner une pénurie de threads.</span><span class="sxs-lookup"><span data-stu-id="a9a5f-104">Setting the max worker threads option to a small value may prevent enough threads from servicing incoming client requests in a timely manner and could lead to "thread starvation".</span></span> <span data-ttu-id="a9a5f-105">Toutefois, dans la mesure où chaque thread actif utilise 512 Ko sur les serveurs 32 bits et jusqu'à 4 Mo sur les serveurs 64 bits, l'affectation d'une valeur élevée à cette option peut entraîner un gaspillage de l'espace d'adressage.</span><span class="sxs-lookup"><span data-stu-id="a9a5f-105">However, setting the option to a large value can waste address space, because each active thread consumes 512 KB on 32-bit servers and up to 4 MB on 64-bit servers.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="a9a5f-106">Meilleures pratiques recommandées</span><span class="sxs-lookup"><span data-stu-id="a9a5f-106">Best Practices Recommendations</span></span>  
 <span data-ttu-id="a9a5f-107">Affectez à l’option Nombre maximum de threads de travail la valeur 0.</span><span class="sxs-lookup"><span data-stu-id="a9a5f-107">Set the max worker threads option to 0.</span></span> <span data-ttu-id="a9a5f-108">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] peut ainsi déterminer automatiquement le nombre correct de threads de travail actifs en fonction des demandes des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="a9a5f-108">This enables [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to automatically determine the correct number of active worker threads based on user requests.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="a9a5f-109">Pour plus d'informations</span><span class="sxs-lookup"><span data-stu-id="a9a5f-109">For More Information</span></span>  
 [<span data-ttu-id="a9a5f-110">Configurer l'option de configuration du serveur max worker threads</span><span class="sxs-lookup"><span data-stu-id="a9a5f-110">Configure the max worker threads Server Configuration Option</span></span>](../../database-engine/configure-windows/configure-the-max-worker-threads-server-configuration-option.md)  
  
## <a name="see-also"></a><span data-ttu-id="a9a5f-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a9a5f-111">See Also</span></span>  
 [<span data-ttu-id="a9a5f-112">Contrôler et appliquer les bonnes pratiques à l’aide de la gestion basée sur des stratégies</span><span class="sxs-lookup"><span data-stu-id="a9a5f-112">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
