---
title: MSSQL_ENG014144 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014144 error
ms.assetid: fdc744d5-530e-48c4-9420-cca032fd482b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0d93f06a585bcc01c52438ff7b99bbd635532402
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599918"
---
# <a name="mssql_eng014144"></a><span data-ttu-id="9f352-102">MSSQL_ENG014144</span><span class="sxs-lookup"><span data-stu-id="9f352-102">MSSQL_ENG014144</span></span>
    
## <a name="message-details"></a><span data-ttu-id="9f352-103">Détails du message</span><span class="sxs-lookup"><span data-stu-id="9f352-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9f352-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="9f352-104">Product Name</span></span>|<span data-ttu-id="9f352-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="9f352-105">SQL Server</span></span>|  
|<span data-ttu-id="9f352-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="9f352-106">Event ID</span></span>|<span data-ttu-id="9f352-107">14144</span><span class="sxs-lookup"><span data-stu-id="9f352-107">14144</span></span>|  
|<span data-ttu-id="9f352-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="9f352-108">Event Source</span></span>|<span data-ttu-id="9f352-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="9f352-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="9f352-110">Composant</span><span class="sxs-lookup"><span data-stu-id="9f352-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="9f352-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="9f352-111">Symbolic Name</span></span>||  
|<span data-ttu-id="9f352-112">Texte du message</span><span class="sxs-lookup"><span data-stu-id="9f352-112">Message Text</span></span>|<span data-ttu-id="9f352-113">Impossible de supprimer l’Abonné '%s'.</span><span class="sxs-lookup"><span data-stu-id="9f352-113">Cannot drop Subscriber '%s'.</span></span> <span data-ttu-id="9f352-114">La base de données de publication '%s' comporte des abonnements qui lui sont associés.</span><span class="sxs-lookup"><span data-stu-id="9f352-114">There are subscriptions for it in the publication database '%s'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9f352-115">Explication</span><span class="sxs-lookup"><span data-stu-id="9f352-115">Explanation</span></span>  
 <span data-ttu-id="9f352-116">Une instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui est configurée en tant qu'Abonné ne peut pas être supprimée du rôle Abonné tant qu'il y a des abonnements actifs configurés pour l'instance.</span><span class="sxs-lookup"><span data-stu-id="9f352-116">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that is configured as a Subscriber cannot be removed from the role of Subscriber while there are active subscriptions configured for the instance.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9f352-117">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="9f352-117">User Action</span></span>  
 <span data-ttu-id="9f352-118">Supprimez tous les abonnements associés avant d'essayer de modifier l'état de l'Abonné de l'instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="9f352-118">Drop all associated subscriptions before attempting to change the Subscriber status of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance:</span></span>  
  
1.  <span data-ttu-id="9f352-119">Exécutez [sp_helpsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql) dans la base de données de publication sur le serveur de publication pour rechercher des abonnements.</span><span class="sxs-lookup"><span data-stu-id="9f352-119">Execute [sp_helpsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql) in the publication database at the Publisher to find subscriptions.</span></span>  
  
2.  <span data-ttu-id="9f352-120">Exécutez [sp_dropsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropsubscription-transact-sql) dans la base de données de publication pour supprimer des abonnements.</span><span class="sxs-lookup"><span data-stu-id="9f352-120">Execute [sp_dropsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropsubscription-transact-sql) in the publication database to drop subscriptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f352-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9f352-121">See Also</span></span>  
 <span data-ttu-id="9f352-122">[Guide de référence des erreurs et des événements &#40;réplication&#41;](errors-and-events-reference-replication.md) </span><span class="sxs-lookup"><span data-stu-id="9f352-122">[Errors and Events Reference &#40;Replication&#41;](errors-and-events-reference-replication.md) </span></span>  
 [<span data-ttu-id="9f352-123">S'abonner à des publications</span><span class="sxs-lookup"><span data-stu-id="9f352-123">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
