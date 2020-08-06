---
title: Surveillance et dépannage de la fusion pour les paires de fichiers de données et Delta | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: a8b0bacc-4d2c-42e4-84bf-1a97e0bd385b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5dc57d08f3db1792a9359b3aa79aaceecd03a025
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613623"
---
# <a name="monitoring-and-troubleshooting-merge-for-data-and-delta-file-pairs"></a><span data-ttu-id="1a309-102">Surveiller et dépanner la fusion de paires de fichiers de données et de fichiers delta</span><span class="sxs-lookup"><span data-stu-id="1a309-102">Monitoring and Troubleshooting Merge for Data and Delta File Pairs</span></span>
  <span data-ttu-id="1a309-103">L'OLTP en mémoire utilise une stratégie de fusion pour fusionner des paires de fichiers de données et delta automatiquement.</span><span class="sxs-lookup"><span data-stu-id="1a309-103">In-Memory OLTP uses a merge policy to merge adjacent data and delta file pairs automatically.</span></span> <span data-ttu-id="1a309-104">Vous ne pouvez pas désactiver l'activité de fusion.</span><span class="sxs-lookup"><span data-stu-id="1a309-104">You cannot disable merge activity.</span></span>  
  
 <span data-ttu-id="1a309-105">Surveillez les paires de fichiers de données et delta, comme suit :</span><span class="sxs-lookup"><span data-stu-id="1a309-105">You can monitor data and delta file pairs, as follows:</span></span>  
  
-   <span data-ttu-id="1a309-106">Comparez la taille du stockage en mémoire à la taille globale du stockage.</span><span class="sxs-lookup"><span data-stu-id="1a309-106">Compare the size of in-memory storage to overall size of storage.</span></span> <span data-ttu-id="1a309-107">Si le stockage a une taille disproportionnée, il est possible que la fusion ne se déclenche pas.</span><span class="sxs-lookup"><span data-stu-id="1a309-107">If the storage is dis-proportionately large, then it is likely that merge is not getting triggered.</span></span> <span data-ttu-id="1a309-108">Pour plus d'informations</span><span class="sxs-lookup"><span data-stu-id="1a309-108">For information</span></span>  
  
-   <span data-ttu-id="1a309-109">Examinez l’espace utilisé dans les fichiers de données et Delta à l’aide de [sys. dm_db_xtp_checkpoint_files &#40;&#41;Transact-SQL](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-xtp-checkpoint-files-transact-sql) pour voir si la fusion n’est pas déclenchée quand elle le devrait.</span><span class="sxs-lookup"><span data-stu-id="1a309-109">Look at the used space in data and delta files using [sys.dm_db_xtp_checkpoint_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-xtp-checkpoint-files-transact-sql) to see if merge is not getting triggered when it should.</span></span>  
  
## <a name="performing-a-manual-merge"></a><span data-ttu-id="1a309-110">Exécution d'une fusion manuelle</span><span class="sxs-lookup"><span data-stu-id="1a309-110">Performing a Manual Merge</span></span>  
 <span data-ttu-id="1a309-111">Vous pouvez utiliser [sys. sp_xtp_merge_checkpoint_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-merge-checkpoint-files-transact-sql) pour effectuer une fusion manuelle.</span><span class="sxs-lookup"><span data-stu-id="1a309-111">You can use [sys.sp_xtp_merge_checkpoint_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-merge-checkpoint-files-transact-sql) to perform a manual merge.</span></span>  
  
 <span data-ttu-id="1a309-112">Utilisez la requête suivante pour récupérer les informations sur les fichiers de données et delta :</span><span class="sxs-lookup"><span data-stu-id="1a309-112">Use the following query to retrieve information about the data and delta files,</span></span>  
  
```sql  
select checkpoint_file_id, file_type_desc, internal_storage_slot, file_size_in_bytes, file_size_used_in_bytes,   
inserted_row_count, deleted_row_count, lower_bound_tsn, upper_bound_tsn   
from sys.dm_db_xtp_checkpoint_files  
where state = 1  
order by file_type_desc, upper_bound_tsn  
```  
  
 <span data-ttu-id="1a309-113">Supposons que vous avez trouvé trois fichiers de données qui n’ont pas été fusionnés.</span><span class="sxs-lookup"><span data-stu-id="1a309-113">Assume that you found three data files that have not been merged.</span></span> <span data-ttu-id="1a309-114">Utilisez la valeur `lower_bound_tsn` du premier fichier de données et la valeur `upper_bound_tsn` du dernier fichier de données pour émettre la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="1a309-114">Using the `lower_bound_tsn` value of the first data file and the `upper_bound_tsn` of the last data file, you can issue the following command:</span></span>  
  
```sql  
exec sys.sp_xtp_merge_checkpoint_files 'H_DB',  12345, 67890  
```  
  
 <span data-ttu-id="1a309-115">Supposez que les trois paires de fichiers de données et delta comportent chacune 15 836 lignes et 5 279 lignes supprimées.</span><span class="sxs-lookup"><span data-stu-id="1a309-115">Assume that the three data and delta file pairs each had 15,836 rows and 5,279 deleted rows.</span></span> <span data-ttu-id="1a309-116">Une fois la fusion terminée, le nouveau fichier de données contient 31 872 lignes et 0 ligne supprimée.</span><span class="sxs-lookup"><span data-stu-id="1a309-116">After the merge, the new data file has 31,872 rows and 0 deleted rows.</span></span> <span data-ttu-id="1a309-117">La taille du nouveau fichier de données peut être beaucoup plus volumineuse que la taille initialement allouée de 128 Mo.</span><span class="sxs-lookup"><span data-stu-id="1a309-117">The size of the new data file can be much larger than the initially allocated size of 128MB.</span></span> <span data-ttu-id="1a309-118">Cela est dû au fait que la fusion manuelle remplace la stratégie de fusion et force la fusion des fichiers demandés.</span><span class="sxs-lookup"><span data-stu-id="1a309-118">This is because manual merge overrides the merge policy and forces the merge of the requested files.</span></span>  
  
 <span data-ttu-id="1a309-119">La [transition de l’état du blog des fichiers de point de contrôle dans les bases de données avec des tables mémoire optimisées](https://cloudblogs.microsoft.com/sqlserver/2014/01/23/state-transition-of-checkpoint-files-in-databases-with-memory-optimized-tables/) décrit la transition d’état des paires de fichiers de données et Delta de la création à la garbage collection.</span><span class="sxs-lookup"><span data-stu-id="1a309-119">The blog [State Transition of Checkpoint Files in Databases with Memory-Optimized Tables](https://cloudblogs.microsoft.com/sqlserver/2014/01/23/state-transition-of-checkpoint-files-in-databases-with-memory-optimized-tables/) describes state transition of data and delta file pairs from inception to garbage collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a309-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1a309-120">See Also</span></span>  
 [<span data-ttu-id="1a309-121">Création et gestion du stockage des objets à mémoire optimisée</span><span class="sxs-lookup"><span data-stu-id="1a309-121">Creating and Managing Storage for Memory-Optimized Objects</span></span>](../relational-databases/in-memory-oltp/creating-and-managing-storage-for-memory-optimized-objects.md)  
  
