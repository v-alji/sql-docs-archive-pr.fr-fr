---
title: MSSQL_REPL027056 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_REPL027056 error
ms.assetid: 92d62f3c-b8ae-482e-a348-2e9a8ee9786e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 44fb130321ec54c39559d52e493cc8f3424172fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705039"
---
# <a name="mssql_repl027056"></a><span data-ttu-id="b1699-102">MSSQL_REPL027056</span><span class="sxs-lookup"><span data-stu-id="b1699-102">MSSQL_REPL027056</span></span>
    
## <a name="message-details"></a><span data-ttu-id="b1699-103">Détails du message</span><span class="sxs-lookup"><span data-stu-id="b1699-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b1699-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="b1699-104">Product Name</span></span>|<span data-ttu-id="b1699-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b1699-105">SQL Server</span></span>|  
|<span data-ttu-id="b1699-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="b1699-106">Event ID</span></span>|<span data-ttu-id="b1699-107">27056</span><span class="sxs-lookup"><span data-stu-id="b1699-107">27056</span></span>|  
|<span data-ttu-id="b1699-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="b1699-108">Event Source</span></span>|<span data-ttu-id="b1699-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b1699-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b1699-110">Composant</span><span class="sxs-lookup"><span data-stu-id="b1699-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="b1699-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="b1699-111">Symbolic Name</span></span>||  
|<span data-ttu-id="b1699-112">Texte du message</span><span class="sxs-lookup"><span data-stu-id="b1699-112">Message Text</span></span>|<span data-ttu-id="b1699-113">Le processus de fusion n'a pas pu modifier l'historique de génération sur le '%1'.</span><span class="sxs-lookup"><span data-stu-id="b1699-113">The merge process was unable to change generation history at the '%1'.</span></span> <span data-ttu-id="b1699-114">Lors de la résolution du problème, redémarrez la synchronisation avec un enregistrement d'historique détaillé et spécifiez un fichier de sortie dans lequel écrire.</span><span class="sxs-lookup"><span data-stu-id="b1699-114">When troubleshooting, restart the synchronization with verbose history logging and specify an output file to which to write.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b1699-115">Explication</span><span class="sxs-lookup"><span data-stu-id="b1699-115">Explanation</span></span>  
 <span data-ttu-id="b1699-116">Cette erreur résulte généralement d'une contention dans les tables système de réplication de fusion devenues trop volumineuses.</span><span class="sxs-lookup"><span data-stu-id="b1699-116">This error is typically raised as a result of contention in merge replication system tables that have grown excessively large.</span></span> <span data-ttu-id="b1699-117">Une longue période de rétention de publication est souvent à l'origine d'une croissance excessive des tables système car les métadonnées doivent être stockées dans ces tables jusqu'à la fin de la période de rétention.</span><span class="sxs-lookup"><span data-stu-id="b1699-117">Large system tables are typically caused by a long publication retention period, because metadata must be stored in these tables until the retention period is reached.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b1699-118">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="b1699-118">User Action</span></span>  
 <span data-ttu-id="b1699-119">**Résolution du problème :**</span><span class="sxs-lookup"><span data-stu-id="b1699-119">**To resolve the issue:**</span></span>  
  
1.  <span data-ttu-id="b1699-120">Diminuez la valeur des paramètres **-DownloadGenerationsPerBatch** et **- UploadGenerationsPerBatch** pour que l’Agent de fusion autorise la poursuite du traitement pendant que vous résolvez le problème à l’origine de l’erreur.</span><span class="sxs-lookup"><span data-stu-id="b1699-120">Decrease the value of the -**DownloadGenerationsPerBatch** and **-UploadGenerationsPerBatch** parameters for the Merge Agent to allow processing to continue while you address the underlying issue causing the error.</span></span> <span data-ttu-id="b1699-121">Les paramètres des agents peuvent être spécifiés dans des profils d'agent et sur la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="b1699-121">Agent parameters can be specified in agent profiles and on the command line.</span></span> <span data-ttu-id="b1699-122">Pour plus d'informations, consultez les pages suivantes :</span><span class="sxs-lookup"><span data-stu-id="b1699-122">For more information, see:</span></span>  
  
    -   [<span data-ttu-id="b1699-123">Utiliser des profils d’agent de réplication</span><span class="sxs-lookup"><span data-stu-id="b1699-123">Work with Replication Agent Profiles</span></span>](agents/replication-agent-profiles.md)  
  
    -   [<span data-ttu-id="b1699-124">Afficher et modifier des paramètres d’invite de commandes d’un Agent de réplication &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="b1699-124">View and Modify Replication Agent Command Prompt Parameters &#40;SQL Server Management Studio&#41;</span></span>](agents/view-and-modify-replication-agent-command-prompt-parameters.md)  
  
    -   <span data-ttu-id="b1699-125">[Replication Agent Executables Concepts](concepts/replication-agent-executables-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="b1699-125">[Replication Agent Executables Concepts](concepts/replication-agent-executables-concepts.md).</span></span>  
  
2.  <span data-ttu-id="b1699-126">Spécifiez une période de rétention de publication la plus courte possible.</span><span class="sxs-lookup"><span data-stu-id="b1699-126">Specify the lowest setting possible for the publication retention period.</span></span> <span data-ttu-id="b1699-127">Pour plus d’informations, voir [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span><span class="sxs-lookup"><span data-stu-id="b1699-127">For more information, see [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span></span>  
  
3.  <span data-ttu-id="b1699-128">Dans le cadre de la gestion d'une réplication de fusion, contrôlez de temps en temps le développement des tables système associées à cette réplication : **MSmerge_contents**, **MSmerge_genhistory**, **MSmerge_tombstone**, **MSmerge_current_partition_mappings**et **MSmerge_past_partition_mappings**.</span><span class="sxs-lookup"><span data-stu-id="b1699-128">As part of maintenance for merge replication, occasionally check the growth of the system tables associated with merge replication: **MSmerge_contents**, **MSmerge_genhistory**, and **MSmerge_tombstone**, **MSmerge_current_partition_mappings**, and **MSmerge_past_partition_mappings**.</span></span> <span data-ttu-id="b1699-129">Réindexez périodiquement ces tables.</span><span class="sxs-lookup"><span data-stu-id="b1699-129">Periodically re-index these tables.</span></span> <span data-ttu-id="b1699-130">Pour plus d’informations, consultez [Réorganiser et reconstruire des index](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="b1699-130">For more information, see [Reorganize and Rebuild Indexes](../indexes/indexes.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1699-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b1699-131">See Also</span></span>  
 [<span data-ttu-id="b1699-132">Guide de référence des erreurs et des événements &#40;réplication&#41;</span><span class="sxs-lookup"><span data-stu-id="b1699-132">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
