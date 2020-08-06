---
title: Augmenter la valeur de l’option blocked process threshold ou la désactiver | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 71db8ef6-341b-4465-99db-5c63e48d4c7d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a7a90aea3fa8fb4d9c423cea1ec6008b01cde883
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601429"
---
# <a name="increase-or-disable-blocked-process-threshold"></a><span data-ttu-id="4ebee-102">Augmenter la valeur de l'option blocked process threshold ou la désactiver</span><span class="sxs-lookup"><span data-stu-id="4ebee-102">Increase or Disable Blocked Process Threshold</span></span>
  <span data-ttu-id="4ebee-103">Cette règle vérifie que l'option blocked process threshold (seuil de processus bloqué) est définie sur 0 (désactivé) ou sur une valeur supérieure ou égale à 5 (secondes).</span><span class="sxs-lookup"><span data-stu-id="4ebee-103">This rules checks that the blocked process threshold option is set to 0 (disabled) or set to a value higher than or equal to 5 (seconds).</span></span> <span data-ttu-id="4ebee-104">Si vous affectez à cette option une valeur comprise entre 1 et 4, le moniteur de blocage risque de s'exécuter en permanence.</span><span class="sxs-lookup"><span data-stu-id="4ebee-104">Setting the blocked process threshold option to a value from 1 to 4 can cause the deadlock monitor to run constantly.</span></span> <span data-ttu-id="4ebee-105">Les valeurs 1 à 4 ne doivent être utilisées que pour le dépannage et jamais à long terme ni dans un environnement de production sans l'aide du service clientèle et du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4ebee-105">Values 1 to 4 should only be used for troubleshooting, and never long term or in a production environment without the assistance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="4ebee-106">Meilleures pratiques recommandées</span><span class="sxs-lookup"><span data-stu-id="4ebee-106">Best Practices Recommendations</span></span>  
 <span data-ttu-id="4ebee-107">Pour résoudre ce problème, définissez l'option blocked process threshold sur la valeur 5 (secondes) ou une valeur supérieure ou désactivez cette option en la définissant sur 0.</span><span class="sxs-lookup"><span data-stu-id="4ebee-107">To resolve this problem, set the blocked process threshold option to a value of 5 (seconds) or higher, or disable blocked process threshold by setting the value to 0.</span></span> <span data-ttu-id="4ebee-108">Pour définir l'option blocked process threshold sur la valeur `5` secondes, exécutez l'instruction suivante :</span><span class="sxs-lookup"><span data-stu-id="4ebee-108">To set the blocked process threshold to a value of `5` seconds, execute the following statement:</span></span>  
  
```  
sp_configure 'show advanced options', 1 ;  
GO  
RECONFIGURE ;  
GO  
sp_configure 'blocked process threshold', 5 ;  
GO  
RECONFIGURE ;  
GO  
```  
  
## <a name="for-more-information"></a><span data-ttu-id="4ebee-109">Pour plus d'informations</span><span class="sxs-lookup"><span data-stu-id="4ebee-109">For More Information</span></span>  
 [<span data-ttu-id="4ebee-110">Seuil de processus bloqué (option de configuration de serveur)</span><span class="sxs-lookup"><span data-stu-id="4ebee-110">blocked process threshold Server Configuration Option</span></span>](../../database-engine/configure-windows/blocked-process-threshold-server-configuration-option.md)  
  
## <a name="see-also"></a><span data-ttu-id="4ebee-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4ebee-111">See Also</span></span>  
 [<span data-ttu-id="4ebee-112">Contrôler et appliquer les bonnes pratiques à l’aide de la gestion basée sur des stratégies</span><span class="sxs-lookup"><span data-stu-id="4ebee-112">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
