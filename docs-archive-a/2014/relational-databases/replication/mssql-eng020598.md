---
title: MSSQL_ENG020598 | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG020598 error
ms.assetid: 1c3032f2-23d1-4ead-94ee-16ac4d75cd0c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8cef26001c353dea94ec9b658dfb38285231bc20
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697955"
---
# <a name="mssql_eng020598"></a><span data-ttu-id="b674c-102">MSSQL_ENG020598</span><span class="sxs-lookup"><span data-stu-id="b674c-102">MSSQL_ENG020598</span></span>
    
## <a name="message-details"></a><span data-ttu-id="b674c-103">Détails du message</span><span class="sxs-lookup"><span data-stu-id="b674c-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b674c-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="b674c-104">Product Name</span></span>|<span data-ttu-id="b674c-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b674c-105">SQL Server</span></span>|  
|<span data-ttu-id="b674c-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="b674c-106">Event ID</span></span>|<span data-ttu-id="b674c-107">20598</span><span class="sxs-lookup"><span data-stu-id="b674c-107">20598</span></span>|  
|<span data-ttu-id="b674c-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="b674c-108">Event Source</span></span>|<span data-ttu-id="b674c-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b674c-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b674c-110">Composant</span><span class="sxs-lookup"><span data-stu-id="b674c-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="b674c-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="b674c-111">Symbolic Name</span></span>||  
|<span data-ttu-id="b674c-112">Texte du message</span><span class="sxs-lookup"><span data-stu-id="b674c-112">Message Text</span></span>|<span data-ttu-id="b674c-113">La ligne n'a pas été trouvée chez l'Abonné lorsque la commande répliquée est appliquée.</span><span class="sxs-lookup"><span data-stu-id="b674c-113">The row was not found at the Subscriber when applying the replicated command.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b674c-114">Explication</span><span class="sxs-lookup"><span data-stu-id="b674c-114">Explanation</span></span>  
 <span data-ttu-id="b674c-115">Cette erreur est générée dans la réplication transactionnelle lorsque l'Agent de distribution tente de mettre à jour sur l'Abonné, mais que la ligne a été supprimée ou que la clé primaire de la ligne a été modifiée.</span><span class="sxs-lookup"><span data-stu-id="b674c-115">This error is raised in transactional replication if the Distribution Agent attempts to update a row at the Subscriber, but the row has been deleted or the primary key of the row has been changed.</span></span> <span data-ttu-id="b674c-116">Par défaut, les Abonnés à des publications transactionnelles doivent être traités en lecture seule, parce que les changements ne sont pas propagés vers le serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="b674c-116">By default, Subscribers to transactional publications should be treated as read-only, because changes are not propagated back to the Publisher.</span></span> <span data-ttu-id="b674c-117">Dans le cas de la réplication transactionnelle, les modifications des utilisateurs doivent être effectuées sur l'Abonné, uniquement si les abonnements devant être mis à jour ou la réplication d'égal à égal sont utilisés.</span><span class="sxs-lookup"><span data-stu-id="b674c-117">For transactional replication, user changes should be made at the Subscriber only if updatable subscriptions or peer-to-peer replication is used.</span></span> <span data-ttu-id="b674c-118">Pour plus d'informations sur ces options, consultez [Updatable Subscriptions for Transactional Replication](transactional/updatable-subscriptions-for-transactional-replication.md) et [Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="b674c-118">For information about these options, see [Updatable Subscriptions for Transactional Replication](transactional/updatable-subscriptions-for-transactional-replication.md) and [Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b674c-119">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="b674c-119">User Action</span></span>  
 <span data-ttu-id="b674c-120">**Pour rectifier ce problème :**</span><span class="sxs-lookup"><span data-stu-id="b674c-120">**To resolve this problem:**</span></span>  
  
1.  <span data-ttu-id="b674c-121">Si la réplication doit continuer pendant que vous identifiez la source de l’erreur, spécifiez le paramètre **-SkipErrors 20598** pour l’Agent de distribution.</span><span class="sxs-lookup"><span data-stu-id="b674c-121">If replication must continue while you identify the source of the error, specify the parameter **-SkipErrors 20598** for the Distribution Agent.</span></span> <span data-ttu-id="b674c-122">L'agent peut alors ignorer les modifications qui provoquent l'erreur 20598, tout en permettant la réplication des autres modifications.</span><span class="sxs-lookup"><span data-stu-id="b674c-122">This allows the agent to skip changes that result in error 20598, while allowing other changes to be replicated.</span></span>  
  
2.  <span data-ttu-id="b674c-123">Identifiez sur l'Abonné les modifications qui ont été supprimées ou qui comportent une clé primaire différente de celle des lignes correspondantes sur le serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="b674c-123">Identify which rows at the Subscriber have been deleted or have a different primary key than the corresponding rows at the Publisher.</span></span> <span data-ttu-id="b674c-124">Vous pouvez utiliser l' [tablediff Utility](../../tools/tablediff-utility.md) pour déterminer les lignes qui sont différentes dans les bases de données de publication et d'abonnement.</span><span class="sxs-lookup"><span data-stu-id="b674c-124">You can use the [tablediff Utility](../../tools/tablediff-utility.md) to determine which rows are different in the publication and subscription databases.</span></span> <span data-ttu-id="b674c-125">Pour obtenir des informations sur l’utilisation de cet utilitaire avec des bases de données répliquées, consultez [Comparer des tables répliquées pour identifier les différences &#40;programmation de la réplication&#41;](administration/compare-replicated-tables-for-differences-replication-programming.md).</span><span class="sxs-lookup"><span data-stu-id="b674c-125">For information about using this utility with replicated databases, see [Compare Replicated Tables for Differences &#40;Replication Programming&#41;](administration/compare-replicated-tables-for-differences-replication-programming.md).</span></span>  
  
3.  <span data-ttu-id="b674c-126">Corrigez les lignes sur l'Abonné à l'aide de l'utilitaire **tablediff** ou d'une autre méthode.</span><span class="sxs-lookup"><span data-stu-id="b674c-126">Correct the rows at the Subscriber using the **tablediff** utility or another method.</span></span>  
  
4.  <span data-ttu-id="b674c-127">(Facultatif) Supprimez le paramètre **-SkipErrors** .</span><span class="sxs-lookup"><span data-stu-id="b674c-127">(Optional) Remove the **-SkipErrors** parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b674c-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b674c-128">See Also</span></span>  
 [<span data-ttu-id="b674c-129">Guide de référence des erreurs et des événements &#40;réplication&#41;</span><span class="sxs-lookup"><span data-stu-id="b674c-129">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
