---
title: Réplication transactionnelle bidirectionnelle | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- bidirectional replication
- transactional replication, bidirectional replication
- bidirectional transactional replication
ms.assetid: 98772e95-67ed-4010-8108-5113dbe709ff
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 57b18dde2e7134e0ba9eb6a9b2e8f5357d171a55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610590"
---
# <a name="bidirectional-transactional-replication"></a><span data-ttu-id="b2a69-102">réplication transactionnelle bidirectionnelle</span><span class="sxs-lookup"><span data-stu-id="b2a69-102">Bidirectional Transactional Replication</span></span>
  <span data-ttu-id="b2a69-103">Une réplication transactionnelle bidirectionnelle est une topologie de réplication transactionnelle spécifique qui permet à deux serveurs d'échanger des modifications : chaque serveur publie des données puis s'abonne à une publication contenant les mêmes données provenant de l'autre serveur.</span><span class="sxs-lookup"><span data-stu-id="b2a69-103">Bidirectional transactional replication is a specific transactional replication topology that allows two servers to exchange changes with each other: each server publishes data and then subscribes to a publication with the same data from the other server.</span></span> <span data-ttu-id="b2a69-104">Le **@loopback_detection** paramètre de [sp_addsubscription &#40;&#41;Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-addsubscription-transact-sql) a la valeur true pour garantir que les modifications sont envoyées uniquement à l’abonné et n’entraînent pas le renvoi de la modification au serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="b2a69-104">The **@loopback_detection** parameter of [sp_addsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addsubscription-transact-sql) is set to TRUE to ensure that changes are only sent to the Subscriber and do not result in the change being sent back to the Publisher.</span></span>  
  
 <span data-ttu-id="b2a69-105">Dans [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] et les versions ultérieures, cette topologie est également prise en charge par la réplication transactionnelle d'égal à égal, mais la réplication bidirectionnelle peut contribuer à améliorer les performances.</span><span class="sxs-lookup"><span data-stu-id="b2a69-105">In [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] and later versions, this topology is also supported by peer-to-peer transactional replication, but bidirectional replication can provide improved performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2a69-106">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b2a69-106">See Also</span></span>  
 [<span data-ttu-id="b2a69-107">Peer-to-Peer Transactional Replication</span><span class="sxs-lookup"><span data-stu-id="b2a69-107">Peer-to-Peer Transactional Replication</span></span>](peer-to-peer-transactional-replication.md)  
  
  
