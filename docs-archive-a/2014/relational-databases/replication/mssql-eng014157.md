---
title: MSSQL_ENG014157 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014157 error
ms.assetid: 1a0890cf-d977-43e0-a2ba-9c5ff1a8f856
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0682d740d82c995d64427f56aabce24b8a48ca65
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603946"
---
# <a name="mssql_eng014157"></a><span data-ttu-id="729e5-102">MSSQL_ENG014157</span><span class="sxs-lookup"><span data-stu-id="729e5-102">MSSQL_ENG014157</span></span>
    
## <a name="message-details"></a><span data-ttu-id="729e5-103">Détails du message</span><span class="sxs-lookup"><span data-stu-id="729e5-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="729e5-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="729e5-104">Product Name</span></span>|<span data-ttu-id="729e5-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="729e5-105">SQL Server</span></span>|  
|<span data-ttu-id="729e5-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="729e5-106">Event ID</span></span>|<span data-ttu-id="729e5-107">14157</span><span class="sxs-lookup"><span data-stu-id="729e5-107">14157</span></span>|  
|<span data-ttu-id="729e5-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="729e5-108">Event Source</span></span>|<span data-ttu-id="729e5-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="729e5-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="729e5-110">Composant</span><span class="sxs-lookup"><span data-stu-id="729e5-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="729e5-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="729e5-111">Symbolic Name</span></span>||  
|<span data-ttu-id="729e5-112">Texte du message</span><span class="sxs-lookup"><span data-stu-id="729e5-112">Message Text</span></span>|<span data-ttu-id="729e5-113">L'abonnement créé par l'Abonné '%1!' à la publication '%2!' a expiré et a été supprimé.</span><span class="sxs-lookup"><span data-stu-id="729e5-113">The subscription created by Subscriber '%s' to publication '%s' has expired and has been dropped.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="729e5-114">Explication</span><span class="sxs-lookup"><span data-stu-id="729e5-114">Explanation</span></span>  
 <span data-ttu-id="729e5-115">Un Abonné doit effectuer une synchronisation avec le serveur de publication dans les délais définis par la période de rétention de la publication.</span><span class="sxs-lookup"><span data-stu-id="729e5-115">A Subscriber must synchronize with the Publisher within the time specified in the publication retention period.</span></span> <span data-ttu-id="729e5-116">Si un Abonné n'effectue pas la synchronisation dans cette période, l'abonnement expire.</span><span class="sxs-lookup"><span data-stu-id="729e5-116">If a Subscriber does not synchronize within this period, the subscription expires.</span></span> <span data-ttu-id="729e5-117">Pour plus d’informations, voir [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span><span class="sxs-lookup"><span data-stu-id="729e5-117">For more information, see [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="729e5-118">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="729e5-118">User Action</span></span>  
 <span data-ttu-id="729e5-119">L'abonnement doit être recréé et initialisé avant que l'Abonné ne recommence à recevoir des modifications de données :</span><span class="sxs-lookup"><span data-stu-id="729e5-119">The subscription must be re-created and initialized before the Subscriber can begin receiving data changes again:</span></span>  
  
-   <span data-ttu-id="729e5-120">Pour plus d’informations sur la création d’abonnements, consultez [S’abonner à des publications](subscribe-to-publications.md).</span><span class="sxs-lookup"><span data-stu-id="729e5-120">For information about creating subscriptions, see [Subscribe to Publications](subscribe-to-publications.md).</span></span>  
  
-   <span data-ttu-id="729e5-121">Pour plus d’informations sur l’initialisation des abonnements, consultez [Initialiser un abonnement](initialize-a-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="729e5-121">For information about initializing subscriptions, see [Initialize a Subscription](initialize-a-subscription.md).</span></span>  
  
 <span data-ttu-id="729e5-122">Si la base de données d'abonnement contient des modifications qui n'ont pas été synchronisées avec le serveur de publication, vous pouvez utiliser l' [tablediff Utility](../../tools/tablediff-utility.md) pour identifier les lignes qui sont différentes dans les bases de publication et les bases d'abonnement.</span><span class="sxs-lookup"><span data-stu-id="729e5-122">If the subscription database contains changes that have not been synchronized with the Publisher, you can use the [tablediff Utility](../../tools/tablediff-utility.md) to determine which rows are different in the publication and subscription databases.</span></span>  
  
 <span data-ttu-id="729e5-123">Vous pouvez augmenter la période de rétention de la publication afin d'empêcher l'expiration des abonnements.</span><span class="sxs-lookup"><span data-stu-id="729e5-123">You can increase the publication retention period to avoid having subscriptions expire.</span></span> <span data-ttu-id="729e5-124">Faites preuve de la plus grande vigilance lors de la définition d'une valeur élevée car plus le nombre de données et de métadonnées stockées est important, moins les performances sont bonnes.</span><span class="sxs-lookup"><span data-stu-id="729e5-124">Use caution in setting a high value, because this can result in more data and metadata being stored, which affects performance.</span></span> <span data-ttu-id="729e5-125">Pour plus d’informations, voir [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span><span class="sxs-lookup"><span data-stu-id="729e5-125">For more information, see [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="729e5-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="729e5-126">See Also</span></span>  
 [<span data-ttu-id="729e5-127">Guide de référence des erreurs et des événements &#40;réplication&#41;</span><span class="sxs-lookup"><span data-stu-id="729e5-127">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
