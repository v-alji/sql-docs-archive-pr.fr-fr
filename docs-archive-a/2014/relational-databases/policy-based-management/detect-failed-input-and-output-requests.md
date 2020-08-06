---
title: Détection de la requête de sortie d’entrée non réussie | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 85373b2e-d9fe-42ef-9653-6e22fe5ecab0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6b3cdc219de06592924ca74cad33ed0027963ac3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695568"
---
# <a name="detect-failed-input-output-request"></a><span data-ttu-id="c33cf-102">Détection de la requête de sortie d’entrée ayant échoué</span><span class="sxs-lookup"><span data-stu-id="c33cf-102">Detect Failed Input Output Request</span></span>
  <span data-ttu-id="c33cf-103">Cette règle recherche l’ID d’événement 50 dans le journal des événements système.</span><span class="sxs-lookup"><span data-stu-id="c33cf-103">This rule checks the system event log for EventId 50.</span></span> <span data-ttu-id="c33cf-104">Cette erreur est due à une demande d'E/S ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="c33cf-104">This error is caused by a failed I/O request.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="c33cf-105">Meilleures pratiques recommandées</span><span class="sxs-lookup"><span data-stu-id="c33cf-105">Best Practices Recommendations</span></span>  
 <span data-ttu-id="c33cf-106">Pour plus d'informations sur la résolution de cette erreur, consultez les articles suivants de la Base de connaissances [!INCLUDE[msCoName](../../includes/msconame-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="c33cf-106">Review the following [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base articles for more information about how to troubleshoot this error:</span></span>  
  
-   [<span data-ttu-id="c33cf-107">Article 311081 de la Base de connaissances Microsoft</span><span class="sxs-lookup"><span data-stu-id="c33cf-107">Microsoft Knowledge Base article 311081</span></span>](https://go.microsoft.com/fwlink/?linkid=117744)  
  
-   [<span data-ttu-id="c33cf-108">Article 885688 de la Base de connaissances Microsoft</span><span class="sxs-lookup"><span data-stu-id="c33cf-108">Microsoft Knowledge Base article 885688</span></span>](https://go.microsoft.com/fwlink/?linkid=117745)  
  
  
