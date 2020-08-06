---
title: La taille du paquet réseau ne doit pas dépasser 8060 octets | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 86db5da1-afe4-4fbb-8bf8-33cedc7e4361
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 01b500cbe65107767d73bc2901b6d5e028b94ee9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603450"
---
# <a name="network-packet-size-should-not-exceed-8060-bytes"></a><span data-ttu-id="2d0a7-102">La taille du paquet réseau ne doit pas dépasser 8060 octets</span><span class="sxs-lookup"><span data-stu-id="2d0a7-102">Network Packet Size Should Not Exceed 8060 Bytes</span></span>
  <span data-ttu-id="2d0a7-103">Si la valeur spécifiée pour sp_configure 'network packet size' ou si la taille du paquet réseau de tout utilisateur connecté est supérieure à 8060 octets, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] effectue des opérations d'allocation de mémoire différentes.</span><span class="sxs-lookup"><span data-stu-id="2d0a7-103">If the value specified for sp_configure 'network packet size' or if the network packet size of any logged-in user is more than 8060 bytes, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] performs different memory allocation operations.</span></span> <span data-ttu-id="2d0a7-104">Cela peut entraîner une augmentation de l'espace d'adressage virtuel de processus qui n'est pas réservé pour le pool de mémoires tampons.</span><span class="sxs-lookup"><span data-stu-id="2d0a7-104">This can cause an increase in the process virtual address space that is not reserved for the buffer pool.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="2d0a7-105">Meilleures pratiques recommandées</span><span class="sxs-lookup"><span data-stu-id="2d0a7-105">Best Practices Recommendations</span></span>  
 <span data-ttu-id="2d0a7-106">La taille du paquet réseau ne doit pas dépasser 8060 octets.</span><span class="sxs-lookup"><span data-stu-id="2d0a7-106">The network packet size should not exceed 8060 bytes.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="2d0a7-107">Pour plus d'informations</span><span class="sxs-lookup"><span data-stu-id="2d0a7-107">For More Information</span></span>  
 [<span data-ttu-id="2d0a7-108">Article 903002 de la Base de connaissances Microsoft</span><span class="sxs-lookup"><span data-stu-id="2d0a7-108">Microsoft Knowledge Base article 903002</span></span>](https://go.microsoft.com/fwlink/?linkid=117749)  
  
## <a name="see-also"></a><span data-ttu-id="2d0a7-109">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2d0a7-109">See Also</span></span>  
 [<span data-ttu-id="2d0a7-110">Contrôler et appliquer les bonnes pratiques à l’aide de la gestion basée sur des stratégies</span><span class="sxs-lookup"><span data-stu-id="2d0a7-110">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
