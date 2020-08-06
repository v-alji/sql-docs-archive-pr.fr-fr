---
title: MSSQL_ENG021286 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG021286 error
ms.assetid: b63620b7-1c6d-46f7-90ea-3a8e99af8de4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 592c788b563046e5949217c94006de2d4755f049
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697938"
---
# <a name="mssql_eng021286"></a><span data-ttu-id="47ad1-102">MSSQL_ENG021286</span><span class="sxs-lookup"><span data-stu-id="47ad1-102">MSSQL_ENG021286</span></span>
    
## <a name="message-details"></a><span data-ttu-id="47ad1-103">Détails du message</span><span class="sxs-lookup"><span data-stu-id="47ad1-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="47ad1-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="47ad1-104">Product Name</span></span>|<span data-ttu-id="47ad1-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="47ad1-105">SQL Server</span></span>|  
|<span data-ttu-id="47ad1-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="47ad1-106">Event ID</span></span>|<span data-ttu-id="47ad1-107">21286</span><span class="sxs-lookup"><span data-stu-id="47ad1-107">21286</span></span>|  
|<span data-ttu-id="47ad1-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="47ad1-108">Event Source</span></span>|<span data-ttu-id="47ad1-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="47ad1-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="47ad1-110">Composant</span><span class="sxs-lookup"><span data-stu-id="47ad1-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="47ad1-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="47ad1-111">Symbolic Name</span></span>||  
|<span data-ttu-id="47ad1-112">Texte du message</span><span class="sxs-lookup"><span data-stu-id="47ad1-112">Message Text</span></span>|<span data-ttu-id="47ad1-113">La table de conflits '%1!' n'existe pas.</span><span class="sxs-lookup"><span data-stu-id="47ad1-113">Conflict table '%s' does not exist.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="47ad1-114">Explication</span><span class="sxs-lookup"><span data-stu-id="47ad1-114">Explanation</span></span>  
 <span data-ttu-id="47ad1-115">Cette erreur est générée si la table de conflits d’un article répertorié dans [sysmergearticles &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/sysmergearticles-transact-sql) n’existe pas.</span><span class="sxs-lookup"><span data-stu-id="47ad1-115">This error is raised if the conflict table for an article listed in [sysmergearticles &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/sysmergearticles-transact-sql) does not actually exist.</span></span> <span data-ttu-id="47ad1-116">Cette erreur peut se produire lorsque vous tentez d'ajouter ou de supprimer une colonne d'une table publiée pour la réplication de fusion.</span><span class="sxs-lookup"><span data-stu-id="47ad1-116">The error can occur when you attempt to add a column to or drop a column from a table published for merge replication.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="47ad1-117">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="47ad1-117">User Action</span></span>  
 <span data-ttu-id="47ad1-118">Exécutez [DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) sur la base de données avec la table de conflits manquante pour vérifier qu’il n’existe pas de problèmes de cohérence des données.</span><span class="sxs-lookup"><span data-stu-id="47ad1-118">Execute [DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) on the database with the missing conflict table to verify there are no data consistency issues.</span></span>  
  
 <span data-ttu-id="47ad1-119">Si la table de conflits n'existe pas sur un Abonné, supprimez l'abonnement puis recréez-le.</span><span class="sxs-lookup"><span data-stu-id="47ad1-119">If the conflict table is missing on a Subscriber, drop the subscription and recreate it.</span></span> <span data-ttu-id="47ad1-120">Si la table des conflits n'existe pas sur un serveur de publication, supprimez tous les abonnement, supprimez la publication puis recréez la publication et tous les abonnements.</span><span class="sxs-lookup"><span data-stu-id="47ad1-120">If the conflict table is missing on a Publisher, drop all subscriptions, drop the publication, and then recreate the publication and all subscriptions.</span></span> <span data-ttu-id="47ad1-121">Pour plus d’informations, consultez [Publier des données et des objets de base de données](publish/publish-data-and-database-objects.md) et [S’abonner à des publications](subscribe-to-publications.md).</span><span class="sxs-lookup"><span data-stu-id="47ad1-121">For more information, see [Publish Data and Database Objects](publish/publish-data-and-database-objects.md) and [Subscribe to Publications](subscribe-to-publications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47ad1-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="47ad1-122">See Also</span></span>  
 [<span data-ttu-id="47ad1-123">Guide de référence des erreurs et des événements &#40;réplication&#41;</span><span class="sxs-lookup"><span data-stu-id="47ad1-123">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
