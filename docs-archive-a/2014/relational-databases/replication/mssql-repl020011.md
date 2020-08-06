---
title: MSSQL_REPL020011 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_REPL020011 error
ms.assetid: f72072d7-bbb6-48ad-ac88-afa74aeb4d58
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 646f25740ebb007f8d04a89690d3b712781efcc8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705040"
---
# <a name="mssql_repl020011"></a><span data-ttu-id="120e4-102">MSSQL_REPL020011</span><span class="sxs-lookup"><span data-stu-id="120e4-102">MSSQL_REPL020011</span></span>
    
## <a name="message-details"></a><span data-ttu-id="120e4-103">Détails du message</span><span class="sxs-lookup"><span data-stu-id="120e4-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="120e4-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="120e4-104">Product Name</span></span>|<span data-ttu-id="120e4-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="120e4-105">SQL Server</span></span>|  
|<span data-ttu-id="120e4-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="120e4-106">Event ID</span></span>|<span data-ttu-id="120e4-107">20011</span><span class="sxs-lookup"><span data-stu-id="120e4-107">20011</span></span>|  
|<span data-ttu-id="120e4-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="120e4-108">Event Source</span></span>|<span data-ttu-id="120e4-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="120e4-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="120e4-110">Composant</span><span class="sxs-lookup"><span data-stu-id="120e4-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="120e4-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="120e4-111">Symbolic Name</span></span>||  
|<span data-ttu-id="120e4-112">Texte du message</span><span class="sxs-lookup"><span data-stu-id="120e4-112">Message Text</span></span>|<span data-ttu-id="120e4-113">Le processus n'a pas pu exécuter '%1' sur '%2'.</span><span class="sxs-lookup"><span data-stu-id="120e4-113">The process could not execute '%1' on '%2'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="120e4-114">Explication</span><span class="sxs-lookup"><span data-stu-id="120e4-114">Explanation</span></span>  
 <span data-ttu-id="120e4-115">Cette erreur peut être signalée dans plusieurs circonstances lors du traitement de la réplication transactionnelle, par exemple quand l’Agent de lecture du journal exécute **sp_replcmds** (Le processus n’a pas pu exécuter « sp_replcmds » sur \<ServerName>) ou **sp_repldone** (Le processus n’a pas pu exécuter « sp_repldone » sur \<ServerName>).</span><span class="sxs-lookup"><span data-stu-id="120e4-115">This error can be raised in a number of circumstances during transactional replication processing, such as when the Log Reader Agent executes **sp_replcmds** (The process could not execute 'sp_replcmds' on \<ServerName>) or **sp_repldone** (The process could not execute 'sp_repldone' on \<ServerName>).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="120e4-116">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="120e4-116">User Action</span></span>  
 <span data-ttu-id="120e4-117">Si cette erreur est signalée dans une base de données que vous venez tout juste de restaurer à partir d'une sauvegarde, vérifiez que vous avez suivi les étapes indiquées dans la documentation sur la sauvegarde et la restauration, notamment l'exécution de **sp_replrestart** si elle est appropriée.</span><span class="sxs-lookup"><span data-stu-id="120e4-117">If this error is raised in a database that you have just restored from a backup, ensure you have followed the steps outlined in the backup and restore documentation, including executing **sp_replrestart** if appropriate.</span></span> <span data-ttu-id="120e4-118">Pour plus d’informations, voir [Stratégies de sauvegarde et de restauration de la réplication transactionnelle et d'instantané](administration/strategies-for-backing-up-and-restoring-snapshot-and-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="120e4-118">For more information, see [Strategies for Backing Up and Restoring Snapshot and Transactional Replication](administration/strategies-for-backing-up-and-restoring-snapshot-and-transactional-replication.md).</span></span>  
  
 <span data-ttu-id="120e4-119">Cette erreur est une erreur de traitement interne et, si elle est signalée dans d'autres circonstances que celle d'une restauration, elle indique généralement que la réplication doit être supprimée et reconfigurée.</span><span class="sxs-lookup"><span data-stu-id="120e4-119">This error is an internal processing error and if it is raised in circumstances other than a restore, it typically indicates that replication must be removed and reconfigured.</span></span> <span data-ttu-id="120e4-120">Si vous ne parvenez pas à supprimer la réplication, contactez le support technique pour obtenir de l'aide.</span><span class="sxs-lookup"><span data-stu-id="120e4-120">If you cannot remove replication, contact customer support for assistance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="120e4-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="120e4-121">See Also</span></span>  
 <span data-ttu-id="120e4-122">[Guide de référence des erreurs et des événements &#40;réplication&#41;](errors-and-events-reference-replication.md) </span><span class="sxs-lookup"><span data-stu-id="120e4-122">[Errors and Events Reference &#40;Replication&#41;](errors-and-events-reference-replication.md) </span></span>  
 <span data-ttu-id="120e4-123">[sp_replcmds &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replcmds-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="120e4-123">[sp_replcmds &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replcmds-transact-sql) </span></span>  
 [<span data-ttu-id="120e4-124">sp_repldone &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="120e4-124">sp_repldone &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-repldone-transact-sql)  
  
  
