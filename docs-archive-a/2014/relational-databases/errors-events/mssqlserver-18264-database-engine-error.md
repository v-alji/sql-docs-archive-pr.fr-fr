---
title: MSSQLSERVER_18264 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 18264 (Database Engine error)
ms.assetid: 3050fc56-2be5-43cf-916b-50a3ac5f89aa
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3edfeb82601e254c02df87cc4a978b9ab5e653e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611099"
---
# <a name="mssqlserver_18264"></a><span data-ttu-id="34c82-102">MSSQLSERVER_18264</span><span class="sxs-lookup"><span data-stu-id="34c82-102">MSSQLSERVER_18264</span></span>
    
## <a name="details"></a><span data-ttu-id="34c82-103">Détails</span><span class="sxs-lookup"><span data-stu-id="34c82-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="34c82-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="34c82-104">Product Name</span></span>|<span data-ttu-id="34c82-105">Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="34c82-105">Microsoft SQL Server</span></span>|  
|<span data-ttu-id="34c82-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="34c82-106">Event ID</span></span>|<span data-ttu-id="34c82-107">18264</span><span class="sxs-lookup"><span data-stu-id="34c82-107">18264</span></span>|  
|<span data-ttu-id="34c82-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="34c82-108">Event Source</span></span>|<span data-ttu-id="34c82-109">MSSQLENGINE</span><span class="sxs-lookup"><span data-stu-id="34c82-109">MSSQLENGINE</span></span>|  
|<span data-ttu-id="34c82-110">Composant</span><span class="sxs-lookup"><span data-stu-id="34c82-110">Component</span></span>|<span data-ttu-id="34c82-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="34c82-111">SQLEngine</span></span>|  
|<span data-ttu-id="34c82-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="34c82-112">Symbolic Name</span></span>|<span data-ttu-id="34c82-113">STRMIO_DBDUMP</span><span class="sxs-lookup"><span data-stu-id="34c82-113">STRMIO_DBDUMP</span></span>|  
|<span data-ttu-id="34c82-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="34c82-114">Message Text</span></span>|<span data-ttu-id="34c82-115">Base de données sauvegardée.</span><span class="sxs-lookup"><span data-stu-id="34c82-115">Database backed up.</span></span> <span data-ttu-id="34c82-116">Base de données : %s, date de création (heure) : %s(%s), pages vidées : %d, premier numéro séquentiel : %s, dernier numéro séquentiel : %s, nombre d'unités de vidage : %d, informations sur l'unité : (%s).</span><span class="sxs-lookup"><span data-stu-id="34c82-116">Database: %s, creation date(time): %s(%s), pages dumped: %d, first LSN: %s, last LSN: %s, number of dump devices: %d, device information: (%s).</span></span> <span data-ttu-id="34c82-117">Ce message est fourni uniquement à titre d'information.</span><span class="sxs-lookup"><span data-stu-id="34c82-117">This is an informational message only.</span></span> <span data-ttu-id="34c82-118">Aucune action de l'utilisateur n'est requise.</span><span class="sxs-lookup"><span data-stu-id="34c82-118">No user action is required.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="34c82-119">Explication</span><span class="sxs-lookup"><span data-stu-id="34c82-119">Explanation</span></span>  
 <span data-ttu-id="34c82-120">Par défaut, chaque sauvegarde réussie ajoute ce message d'information au journal des erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et au journal des événements système.</span><span class="sxs-lookup"><span data-stu-id="34c82-120">By default, every successful backup adds this informational message to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log and the system event log.</span></span> <span data-ttu-id="34c82-121">Si vous sauvegardez très fréquemment le journal des transactions, ces messages peuvent rapidement s’accumuler, créer des journaux des erreurs très volumineux et compliquer la recherche d’autres messages.</span><span class="sxs-lookup"><span data-stu-id="34c82-121">If you very frequently back up the transaction log, these messages can accumulate quickly, creating very large error logs that can make finding other messages difficult.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="34c82-122">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="34c82-122">User Action</span></span>  
 <span data-ttu-id="34c82-123">Vous pouvez supprimer ces entrées de journal à l’aide de l’indicateur de trace [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**3226**.</span><span class="sxs-lookup"><span data-stu-id="34c82-123">You can suppress these log entries by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] trace flag **3226**.</span></span> <span data-ttu-id="34c82-124">Cela est utile si vous exécutez des sauvegardes de fichiers journaux fréquentes et si aucun de vos scripts ne dépend de ces entrées.</span><span class="sxs-lookup"><span data-stu-id="34c82-124">Enabling this trace flag is useful if you are running frequent log backups and if none of your scripts depend on those entries.</span></span>  
  
 <span data-ttu-id="34c82-125">Pour plus d'informations sur les indicateurs de trace, consultez la documentation en ligne de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="34c82-125">For information about using trace flags, see SQL Server Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34c82-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="34c82-126">See Also</span></span>  
 [<span data-ttu-id="34c82-127">Indicateurs de trace &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="34c82-127">Trace Flags &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql)  
  
  
