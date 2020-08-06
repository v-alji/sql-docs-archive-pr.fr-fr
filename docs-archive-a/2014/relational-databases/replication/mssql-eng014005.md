---
title: MSSQL_ENG014005 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014005 error
ms.assetid: f168f0d6-cb11-45d4-9781-c374d7f388ee
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d820fd26cceee72b0d08204d6f6ce73a76508e9c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600814"
---
# <a name="mssql_eng014005"></a><span data-ttu-id="25e39-102">MSSQL_ENG014005</span><span class="sxs-lookup"><span data-stu-id="25e39-102">MSSQL_ENG014005</span></span>
    
## <a name="message-details"></a><span data-ttu-id="25e39-103">Détails du message</span><span class="sxs-lookup"><span data-stu-id="25e39-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="25e39-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="25e39-104">Product Name</span></span>|<span data-ttu-id="25e39-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="25e39-105">SQL Server</span></span>|  
|<span data-ttu-id="25e39-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="25e39-106">Event ID</span></span>|<span data-ttu-id="25e39-107">14005</span><span class="sxs-lookup"><span data-stu-id="25e39-107">14005</span></span>|  
|<span data-ttu-id="25e39-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="25e39-108">Event Source</span></span>|<span data-ttu-id="25e39-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="25e39-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="25e39-110">Composant</span><span class="sxs-lookup"><span data-stu-id="25e39-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="25e39-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="25e39-111">Symbolic Name</span></span>||  
|<span data-ttu-id="25e39-112">Texte du message</span><span class="sxs-lookup"><span data-stu-id="25e39-112">Message Text</span></span>|<span data-ttu-id="25e39-113">Impossible de supprimer la publication.</span><span class="sxs-lookup"><span data-stu-id="25e39-113">Could not drop publication.</span></span> <span data-ttu-id="25e39-114">Il existe un abonnement.</span><span class="sxs-lookup"><span data-stu-id="25e39-114">A subscription exists to it.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="25e39-115">Explication</span><span class="sxs-lookup"><span data-stu-id="25e39-115">Explanation</span></span>  
 <span data-ttu-id="25e39-116">Vous avez tenté de supprimer une publication qui a un ou plusieurs abonnements associés.</span><span class="sxs-lookup"><span data-stu-id="25e39-116">You have tried to drop a publication which has one or more associated subscriptions.</span></span> <span data-ttu-id="25e39-117">Une publication peut être supprimée seulement s'il n'y a pas d'abonnements associés.</span><span class="sxs-lookup"><span data-stu-id="25e39-117">A publication can only be dropped if there are no associated subscriptions.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="25e39-118">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="25e39-118">User Action</span></span>  
 <span data-ttu-id="25e39-119">Supprimez les abonnements avant de supprimer la publication.</span><span class="sxs-lookup"><span data-stu-id="25e39-119">Drop the subscriptions before dropping the publication.</span></span> <span data-ttu-id="25e39-120">Si vous utilisez [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] pour supprimer la publication, vous pouvez choisir de supprimer automatiquement tous les abonnements associés avant de supprimer la publication.</span><span class="sxs-lookup"><span data-stu-id="25e39-120">If you use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to drop the publication, it will give you the option to automatically drop all associated subscriptions before dropping the publication.</span></span> <span data-ttu-id="25e39-121">Si vous utilisez des procédures stockées, vous devez d'abord explicitement supprimer les abonnements.</span><span class="sxs-lookup"><span data-stu-id="25e39-121">If you use stored procedures, you must explicitly drop the subscriptions first.</span></span> <span data-ttu-id="25e39-122">Pour plus d'informations, consultez [Delete a Push Subscription](delete-a-push-subscription.md) et [Delete a Pull Subscription](delete-a-pull-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="25e39-122">For more information, see [Delete a Push Subscription](delete-a-push-subscription.md) and [Delete a Pull Subscription](delete-a-pull-subscription.md).</span></span>  
  
 <span data-ttu-id="25e39-123">S'il semble ne pas exister d'abonnements pour la publication ou si vous voyez cette erreur quand vous créez une publication, il est possible qu'un abonnement antérieur n'ait pas été complètement nettoyé quand il a été supprimé.</span><span class="sxs-lookup"><span data-stu-id="25e39-123">If no subscriptions appear to exist for the publication or if you see this error when you create a publication, you might have a previous subscription that was not completely cleaned up when it was removed.</span></span> <span data-ttu-id="25e39-124">Exécutez [sp_removedbreplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) sur la base de données pour supprimer tous les objets et paramètres liés à la réplication.</span><span class="sxs-lookup"><span data-stu-id="25e39-124">Execute [sp_removedbreplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) on the database to remove all objects and settings related to replication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25e39-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="25e39-125">See Also</span></span>  
 [<span data-ttu-id="25e39-126">Guide de référence des erreurs et des événements &#40;réplication&#41;</span><span class="sxs-lookup"><span data-stu-id="25e39-126">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
