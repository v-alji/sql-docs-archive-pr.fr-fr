---
title: MSSQL_ENG004929 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG004929 error
ms.assetid: 1d9b1d88-1fbf-4089-b392-687d3b0220ca
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b202b28eabe1feb1ed180bda0d58d2e84c7d10d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600816"
---
# <a name="mssql_eng004929"></a><span data-ttu-id="d6b20-102">MSSQL_ENG004929</span><span class="sxs-lookup"><span data-stu-id="d6b20-102">MSSQL_ENG004929</span></span>
    
## <a name="message-details"></a><span data-ttu-id="d6b20-103">Détails du message</span><span class="sxs-lookup"><span data-stu-id="d6b20-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d6b20-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="d6b20-104">Product Name</span></span>|<span data-ttu-id="d6b20-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d6b20-105">SQL Server</span></span>|  
|<span data-ttu-id="d6b20-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="d6b20-106">Event ID</span></span>|<span data-ttu-id="d6b20-107">4929</span><span class="sxs-lookup"><span data-stu-id="d6b20-107">4929</span></span>|  
|<span data-ttu-id="d6b20-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="d6b20-108">Event Source</span></span>|<span data-ttu-id="d6b20-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d6b20-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d6b20-110">Composant</span><span class="sxs-lookup"><span data-stu-id="d6b20-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="d6b20-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="d6b20-111">Symbolic Name</span></span>||  
|<span data-ttu-id="d6b20-112">Texte du message</span><span class="sxs-lookup"><span data-stu-id="d6b20-112">Message Text</span></span>|<span data-ttu-id="d6b20-113">Impossible de modifier le% S_MSG'%. \* ls', car il est en cours de publication pour la réplication.</span><span class="sxs-lookup"><span data-stu-id="d6b20-113">Cannot alter the %S_MSG '%.\*ls' because it is being published for replication.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d6b20-114">Explication</span><span class="sxs-lookup"><span data-stu-id="d6b20-114">Explanation</span></span>  
 <span data-ttu-id="d6b20-115">Cette erreur se produit généralement lorsque vous tentez de supprimer la contrainte de clé primaire d'une table publiée pour la réplication transactionnelle.</span><span class="sxs-lookup"><span data-stu-id="d6b20-115">This error typically occurs if you attempt to drop the primary key constraint on a table that is published for transactional replication.</span></span> <span data-ttu-id="d6b20-116">Comme la réplication transactionnelle nécessite une clé primaire pour chaque table publiée, la contrainte ne peut pas être supprimée.</span><span class="sxs-lookup"><span data-stu-id="d6b20-116">Transactional replication requires a primary key for each published table; therefore the constraint cannot be dropped.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d6b20-117">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="d6b20-117">User Action</span></span>  
 <span data-ttu-id="d6b20-118">Pour supprimer la contrainte, commencez par supprimer l'article associé à la table.</span><span class="sxs-lookup"><span data-stu-id="d6b20-118">To drop the constraint, first drop the article associated with the table.</span></span> <span data-ttu-id="d6b20-119">Pour plus d’informations, consultez [Ajouter et supprimer des articles de publications existantes](publish/add-articles-to-and-drop-articles-from-existing-publications.md).</span><span class="sxs-lookup"><span data-stu-id="d6b20-119">For more information, see [Add Articles to and Drop Articles from Existing Publications](publish/add-articles-to-and-drop-articles-from-existing-publications.md).</span></span> <span data-ttu-id="d6b20-120">Si cette erreur se produit dans une base de données qui n’est pas répliquée, exécutez [sp_removedbreplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) pour vérifier que les objets de la base de données ne sont pas marqués comme étant répliqués.</span><span class="sxs-lookup"><span data-stu-id="d6b20-120">If this error occurs in a database that is not replicated, execute [sp_removedbreplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) to ensure objects in the database are not marked as replicated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6b20-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d6b20-121">See Also</span></span>  
 [<span data-ttu-id="d6b20-122">Guide de référence des erreurs et des événements &#40;réplication&#41;</span><span class="sxs-lookup"><span data-stu-id="d6b20-122">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
