---
title: MSSQL_ENG020574 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG02574 error
ms.assetid: 4e98f8de-287c-4090-81ee-dc8f80dfa6a1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8e224e9a87d40fa826a05c669216649c45185037
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614540"
---
# <a name="mssql_eng020574"></a><span data-ttu-id="a3f3c-102">MSSQL_ENG020574</span><span class="sxs-lookup"><span data-stu-id="a3f3c-102">MSSQL_ENG020574</span></span>
    
## <a name="message-details"></a><span data-ttu-id="a3f3c-103">Détails du message</span><span class="sxs-lookup"><span data-stu-id="a3f3c-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a3f3c-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="a3f3c-104">Product Name</span></span>|<span data-ttu-id="a3f3c-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a3f3c-105">SQL Server</span></span>|  
|<span data-ttu-id="a3f3c-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="a3f3c-106">Event ID</span></span>|<span data-ttu-id="a3f3c-107">20574</span><span class="sxs-lookup"><span data-stu-id="a3f3c-107">20574</span></span>|  
|<span data-ttu-id="a3f3c-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="a3f3c-108">Event Source</span></span>|<span data-ttu-id="a3f3c-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a3f3c-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a3f3c-110">Composant</span><span class="sxs-lookup"><span data-stu-id="a3f3c-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="a3f3c-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="a3f3c-111">Symbolic Name</span></span>||  
|<span data-ttu-id="a3f3c-112">Texte du message</span><span class="sxs-lookup"><span data-stu-id="a3f3c-112">Message Text</span></span>|<span data-ttu-id="a3f3c-113">L'Abonné '%s' avec un abonnement à l'article '%s' de la publication '%s' n'a pas réussi la validation de données.</span><span class="sxs-lookup"><span data-stu-id="a3f3c-113">Subscriber '%s' subscription to article '%s' in publication '%s' failed data validation.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a3f3c-114">Explication</span><span class="sxs-lookup"><span data-stu-id="a3f3c-114">Explanation</span></span>  
 <span data-ttu-id="a3f3c-115">Lors de la validation des données de l'Abonné par rapport aux données du serveur de publication, les données ne correspondaient pas, par conséquent la validation a échoué.</span><span class="sxs-lookup"><span data-stu-id="a3f3c-115">The data at the Subscriber was validated against the data at the Publisher, and the data did not match; therefore validation failed.</span></span> <span data-ttu-id="a3f3c-116">Pour plus d'informations sur la validation, consultez [Validate Replicated Data](validate-data-at-the-subscriber.md).</span><span class="sxs-lookup"><span data-stu-id="a3f3c-116">For more information about validation, see [Validate Replicated Data](validate-data-at-the-subscriber.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a3f3c-117">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="a3f3c-117">User Action</span></span>  
 <span data-ttu-id="a3f3c-118">Nous vous recommandons de procéder comme suit :</span><span class="sxs-lookup"><span data-stu-id="a3f3c-118">We recommend that you do the following:</span></span>  
  
-   <span data-ttu-id="a3f3c-119">Déterminez la raison de l'échec de la validation.</span><span class="sxs-lookup"><span data-stu-id="a3f3c-119">Determine why validation failed.</span></span>  
  
-   <span data-ttu-id="a3f3c-120">Corrigez le problème sous-jacent qui est à l'origine de cet échec.</span><span class="sxs-lookup"><span data-stu-id="a3f3c-120">Correct the underlying issue that caused the failure.</span></span>  
  
-   <span data-ttu-id="a3f3c-121">Établissez la convergence des données en réinitialisant l'abonnement ou en utilisant une autre méthode.</span><span class="sxs-lookup"><span data-stu-id="a3f3c-121">Bring the data into convergence by reinitializing the subscription or through another method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3f3c-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a3f3c-122">See Also</span></span>  
 [<span data-ttu-id="a3f3c-123">Guide de référence des erreurs et des événements &#40;réplication&#41;</span><span class="sxs-lookup"><span data-stu-id="a3f3c-123">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
