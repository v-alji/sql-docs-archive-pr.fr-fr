---
title: Nettoyer les métadonnées de fusion (programmation Transact-SQL de la réplication) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- metadata [SQL Server replication]
- sp_mergemetadataretentioncleanup
ms.assetid: 9b88baea-b7c6-4e5d-88f9-93d6a0ff0368
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5a2306db72fd3f0098e18ff058796a5498eafcac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705083"
---
# <a name="clean-up-merge-metadata-replication-transact-sql-programming"></a><span data-ttu-id="e4c1e-102">Nettoyer les métadonnées de fusion (programmation Transact-SQL de la réplication)</span><span class="sxs-lookup"><span data-stu-id="e4c1e-102">Clean Up Merge Metadata (Replication Transact-SQL Programming)</span></span>
  <span data-ttu-id="e4c1e-103">Les métadonnées de réplication de fusion sont nettoyées régulièrement par l'Agent de fusion en fonction du paramètre de rétention de la publication.</span><span class="sxs-lookup"><span data-stu-id="e4c1e-103">Merge replication metadata is cleaned up periodically by the Merge Agent based on the retention setting for the publication.</span></span> <span data-ttu-id="e4c1e-104">Cela se produit sur le serveur de publication et l'Abonné dans les tables système [MSmerge_genhistory](/sql/relational-databases/system-tables/msmerge-genhistory-transact-sql), [MSmerge_contents](/sql/relational-databases/system-tables/msmerge-contents-transact-sql), [MSmerge_tombstone](/sql/relational-databases/system-tables/msmerge-tombstone-transact-sql), [MSmerge_past_partition_mappings](/sql/relational-databases/system-tables/msmerge-past-partition-mappings-transact-sql)et [MSmerge_current_partition_mappings](/sql/relational-databases/system-tables/msmerge-current-partition-mappings) .</span><span class="sxs-lookup"><span data-stu-id="e4c1e-104">This occurs at the Publisher and Subscriber in the [MSmerge_genhistory](/sql/relational-databases/system-tables/msmerge-genhistory-transact-sql), [MSmerge_contents](/sql/relational-databases/system-tables/msmerge-contents-transact-sql), [MSmerge_tombstone](/sql/relational-databases/system-tables/msmerge-tombstone-transact-sql), [MSmerge_past_partition_mappings](/sql/relational-databases/system-tables/msmerge-past-partition-mappings-transact-sql), and [MSmerge_current_partition_mappings](/sql/relational-databases/system-tables/msmerge-current-partition-mappings) system tables.</span></span> <span data-ttu-id="e4c1e-105">Vous pouvez également nettoyer par programmation les données dans ces tables à l'aide de procédures stockées de réplication.</span><span class="sxs-lookup"><span data-stu-id="e4c1e-105">You can also programmatically clean up the data in these tables using replication stored procedures.</span></span>  
  
### <a name="to-manually-clean-up-merge-metadata"></a><span data-ttu-id="e4c1e-106">Pour nettoyer les métadonnées de fusion manuellement</span><span class="sxs-lookup"><span data-stu-id="e4c1e-106">To manually clean up merge metadata</span></span>  
  
1.  <span data-ttu-id="e4c1e-107">Sur la base de données de publication du serveur de publication, exécutez [sp_mergemetadataretentioncleanup](/sql/relational-databases/system-stored-procedures/sp-mergemetadataretentioncleanup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e4c1e-107">At the Publisher on the publication database, execute [sp_mergemetadataretentioncleanup](/sql/relational-databases/system-stored-procedures/sp-mergemetadataretentioncleanup-transact-sql).</span></span>  
  
2.  <span data-ttu-id="e4c1e-108">Facultatif Notez le nombre de lignes supprimées à l’étape 1 dans les tables système [MSmerge_genhistory](/sql/relational-databases/system-tables/msmerge-genhistory-transact-sql), [MSmerge_contents](/sql/relational-databases/system-tables/msmerge-contents-transact-sql)et [MSmerge_tombstone](/sql/relational-databases/system-tables/msmerge-tombstone-transact-sql) , retournées respectivement dans les **@num_genhistory_rows** paramètres de **@num_contents_rows** sortie, et **@num_tombstone_rows** .</span><span class="sxs-lookup"><span data-stu-id="e4c1e-108">(Optional) Note the number of rows removed in step 1 from the [MSmerge_genhistory](/sql/relational-databases/system-tables/msmerge-genhistory-transact-sql), [MSmerge_contents](/sql/relational-databases/system-tables/msmerge-contents-transact-sql), and [MSmerge_tombstone](/sql/relational-databases/system-tables/msmerge-tombstone-transact-sql) system tables, returned respectively in the **@num_genhistory_rows**, **@num_contents_rows**, and **@num_tombstone_rows** output parameters.</span></span>  
  
3.  <span data-ttu-id="e4c1e-109">Répétez les étapes 1 et 2 sur l'Abonné à nettoyer les métadonnées de la base de données d'abonnement.</span><span class="sxs-lookup"><span data-stu-id="e4c1e-109">Repeat steps 1 and 2 at the Subscriber to clean up metadata on the subscription database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4c1e-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e4c1e-110">See Also</span></span>  
 [<span data-ttu-id="e4c1e-111">Expiration et désactivation des abonnements</span><span class="sxs-lookup"><span data-stu-id="e4c1e-111">Subscription Expiration and Deactivation</span></span>](../subscription-expiration-and-deactivation.md)  
  
  
