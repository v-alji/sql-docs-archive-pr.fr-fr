---
title: MSSQL_ENG003724 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG003724 error
ms.assetid: 10cb119d-92df-4124-b85d-cd2f2666c99c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: dbfb68575c5ffa73276b3bbe1643381c3f0cc412
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709159"
---
# <a name="mssql_eng003724"></a><span data-ttu-id="4396f-102">MSSQL_ENG003724</span><span class="sxs-lookup"><span data-stu-id="4396f-102">MSSQL_ENG003724</span></span>
    
## <a name="message-details"></a><span data-ttu-id="4396f-103">Détails du message</span><span class="sxs-lookup"><span data-stu-id="4396f-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4396f-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="4396f-104">Product Name</span></span>|<span data-ttu-id="4396f-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="4396f-105">SQL Server</span></span>|  
|<span data-ttu-id="4396f-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="4396f-106">Event ID</span></span>|<span data-ttu-id="4396f-107">3724</span><span class="sxs-lookup"><span data-stu-id="4396f-107">3724</span></span>|  
|<span data-ttu-id="4396f-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="4396f-108">Event Source</span></span>|<span data-ttu-id="4396f-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="4396f-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="4396f-110">Composant</span><span class="sxs-lookup"><span data-stu-id="4396f-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="4396f-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="4396f-111">Symbolic Name</span></span>||  
|<span data-ttu-id="4396f-112">Texte du message</span><span class="sxs-lookup"><span data-stu-id="4396f-112">Message Text</span></span>|<span data-ttu-id="4396f-113">Impossible de% S_MSG% S_MSG'%. \* ls', car il est utilisé pour la réplication.</span><span class="sxs-lookup"><span data-stu-id="4396f-113">Cannot %S_MSG the %S_MSG '%.\*ls' because it is being used for replication.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4396f-114">Explication</span><span class="sxs-lookup"><span data-stu-id="4396f-114">Explanation</span></span>  
 <span data-ttu-id="4396f-115">Lorsque des objets d'une base de données sont répliqués, ils sont marqués comme étant répliqués dans la table système **sysarticles** (publications transactionnelles ou d'instantanés) ou dans la table système **sysmergearticles** (publications de fusion).</span><span class="sxs-lookup"><span data-stu-id="4396f-115">When objects in a database are replicated, they are marked as replicated in the system table **sysarticles** (for snapshot and transactional publications) or **sysmergearticles** (for merge publications).</span></span> <span data-ttu-id="4396f-116">Si vous tentez de supprimer un objet répliqué, cette erreur est générée.</span><span class="sxs-lookup"><span data-stu-id="4396f-116">If you attempt drop a replicated object, this error is raised.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4396f-117">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="4396f-117">User Action</span></span>  
 <span data-ttu-id="4396f-118">Vérifiez que l'objet de base de données n'est pas répliqué avant d'essayer de le supprimer.</span><span class="sxs-lookup"><span data-stu-id="4396f-118">Ensure the database object is not replicated before attempting to drop it.</span></span> <span data-ttu-id="4396f-119">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="4396f-119">For example:</span></span>  
  
-   <span data-ttu-id="4396f-120">Si l'erreur se produit dans la base de données de publication, supprimez l'article de la publication avant de supprimer l'objet.</span><span class="sxs-lookup"><span data-stu-id="4396f-120">If the error occurs in the publication database, drop the article from the publication before dropping the object.</span></span> <span data-ttu-id="4396f-121">Pour plus d’informations, consultez [Ajouter et supprimer des articles de publications existantes](publish/add-articles-to-and-drop-articles-from-existing-publications.md).</span><span class="sxs-lookup"><span data-stu-id="4396f-121">For more information, see [Add Articles to and Drop Articles from Existing Publications](publish/add-articles-to-and-drop-articles-from-existing-publications.md).</span></span>  
  
-   <span data-ttu-id="4396f-122">Si l'erreur se produit dans la base de données d'abonnement, supprimez l'abonnement avant de supprimer l'objet.</span><span class="sxs-lookup"><span data-stu-id="4396f-122">If the error occurs in the subscription database, drop the subscription before dropping the object.</span></span> <span data-ttu-id="4396f-123">Pour plus d’informations, consultez [S’abonner à des publications](subscribe-to-publications.md).</span><span class="sxs-lookup"><span data-stu-id="4396f-123">For more information, see [Subscribe to Publications](subscribe-to-publications.md).</span></span> <span data-ttu-id="4396f-124">Dans le cas d'abonnements aux publications transactionnelles, il est possible de supprimer l'abonnement à un article individuel plutôt qu'à la publication complète.</span><span class="sxs-lookup"><span data-stu-id="4396f-124">For subscriptions to transactional publications, it is possible to drop the subscription to an individual article rather than the entire publication.</span></span> <span data-ttu-id="4396f-125">Pour plus d’informations, consultez [sp_dropsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropsubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4396f-125">For more information, see [sp_dropsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropsubscription-transact-sql).</span></span>  
  
 <span data-ttu-id="4396f-126">Si cette erreur se produit dans une base de données qui n’est pas répliquée, exécutez [sp_removedbreplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) pour vérifier que les objets de la base de données ne sont pas marqués comme étant répliqués.</span><span class="sxs-lookup"><span data-stu-id="4396f-126">If this error occurs in a database that is not replicated, execute [sp_removedbreplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) to ensure objects in the database are not marked as replicated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4396f-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4396f-127">See Also</span></span>  
 [<span data-ttu-id="4396f-128">Guide de référence des erreurs et des événements &#40;réplication&#41;</span><span class="sxs-lookup"><span data-stu-id="4396f-128">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
