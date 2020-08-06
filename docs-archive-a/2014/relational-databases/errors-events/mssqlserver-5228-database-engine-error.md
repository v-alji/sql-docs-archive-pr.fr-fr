---
title: MSSQLSERVER_5228 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5228 (Database Engine error)
ms.assetid: 5e83c617-4aa2-4755-bcc5-a798c46b97e4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: eef59e62f00a44aad7bfefb1719a6d8d2b3d0290
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600970"
---
# <a name="mssqlserver_5228"></a><span data-ttu-id="81c4d-102">MSSQLSERVER_5228</span><span class="sxs-lookup"><span data-stu-id="81c4d-102">MSSQLSERVER_5228</span></span>
    
## <a name="details"></a><span data-ttu-id="81c4d-103">Détails</span><span class="sxs-lookup"><span data-stu-id="81c4d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="81c4d-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="81c4d-104">Product Name</span></span>|<span data-ttu-id="81c4d-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="81c4d-105">SQL Server</span></span>|  
|<span data-ttu-id="81c4d-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="81c4d-106">Event ID</span></span>|<span data-ttu-id="81c4d-107">5228</span><span class="sxs-lookup"><span data-stu-id="81c4d-107">5228</span></span>|  
|<span data-ttu-id="81c4d-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="81c4d-108">Event Source</span></span>|<span data-ttu-id="81c4d-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="81c4d-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="81c4d-110">Composant</span><span class="sxs-lookup"><span data-stu-id="81c4d-110">Component</span></span>|<span data-ttu-id="81c4d-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="81c4d-111">SQLEngine</span></span>|  
|<span data-ttu-id="81c4d-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="81c4d-112">Symbolic Name</span></span>|<span data-ttu-id="81c4d-113">DBCC4_ANTIMATTER_COLUMN_DETECTED</span><span class="sxs-lookup"><span data-stu-id="81c4d-113">DBCC4_ANTIMATTER_COLUMN_DETECTED</span></span>|  
|<span data-ttu-id="81c4d-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="81c4d-114">Message Text</span></span>|<span data-ttu-id="81c4d-115">Erreur de table, ID d’objet O_ID, ID d’index I_ID, ID de partition PN_ID, ID d’unité d’allocation A_ID (type TYPE), page PG_ID, ligne R_ID.</span><span class="sxs-lookup"><span data-stu-id="81c4d-115">Table error: Object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE), page PG_ID, row R_ID.</span></span> <span data-ttu-id="81c4d-116">DBCC a détecté un nettoyage incomplet lié à une opération de construction d'index en ligne.</span><span class="sxs-lookup"><span data-stu-id="81c4d-116">DBCC detected incomplete cleanup from an online index build operation.</span></span> <span data-ttu-id="81c4d-117">(La valeur de la colonne « antimatière » est VALUE.)</span><span class="sxs-lookup"><span data-stu-id="81c4d-117">(Antimatter column value is VALUE.)</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="81c4d-118">Explication</span><span class="sxs-lookup"><span data-stu-id="81c4d-118">Explanation</span></span>  
 <span data-ttu-id="81c4d-119">Une construction d’index en ligne non terminée a été détectée pour l’objet *O_ID*, l’index *I_ID* et la partition *PN_ID*.</span><span class="sxs-lookup"><span data-stu-id="81c4d-119">An unfinished online index build was detected for object *O_ID*, index *I_ID*, and partition *PN_ID*.</span></span> <span data-ttu-id="81c4d-120">Cela se traduit par la présence d’une colonne antimatière sur la ligne *R_ID*.</span><span class="sxs-lookup"><span data-stu-id="81c4d-120">This is manifested by the presence of an antimatter column on the row *R_ID*.</span></span> <span data-ttu-id="81c4d-121">Une colonne antimatière est utilisée pour réconcilier des enregistrements provenant de plusieurs sources lors de la construction d'un index en ligne.</span><span class="sxs-lookup"><span data-stu-id="81c4d-121">An antimatter column is used when reconciling records from multiple sources during an online index build.</span></span> <span data-ttu-id="81c4d-122">Le message d'erreur indique également la valeur de la colonne antimatière.</span><span class="sxs-lookup"><span data-stu-id="81c4d-122">The error message also indicates the value of the antimatter column.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="81c4d-123">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="81c4d-123">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="81c4d-124">Rechercher une défaillance matérielle</span><span class="sxs-lookup"><span data-stu-id="81c4d-124">Look for Hardware Failure</span></span>  
 <span data-ttu-id="81c4d-125">Exécutez les diagnostics matériels et corrigez les éventuels problèmes rencontrés.</span><span class="sxs-lookup"><span data-stu-id="81c4d-125">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="81c4d-126">Examinez également les journaux système et des applications de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, ainsi que le journal des erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour vérifier si l'erreur est due à une défaillance matérielle.</span><span class="sxs-lookup"><span data-stu-id="81c4d-126">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="81c4d-127">Corrigez les éventuels problèmes matériels contenus dans les journaux.</span><span class="sxs-lookup"><span data-stu-id="81c4d-127">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="81c4d-128">Si vous avez des problèmes persistants de données endommagées, tentez d'échanger votre ordinateur, vos contrôleurs et vos lecteurs de disque contre d'autres composants.</span><span class="sxs-lookup"><span data-stu-id="81c4d-128">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="81c4d-129">Assurez-vous que votre système n'a pas une mémoire cache d'écriture active sur le contrôleur de disque.</span><span class="sxs-lookup"><span data-stu-id="81c4d-129">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="81c4d-130">Si vous soupçonnez qu’il s’agit là de la source du problème, contactez votre fournisseur de matériel.</span><span class="sxs-lookup"><span data-stu-id="81c4d-130">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="81c4d-131">Enfin, il peut s'avérer bénéfique d'utiliser un matériel totalement nouveau,</span><span class="sxs-lookup"><span data-stu-id="81c4d-131">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="81c4d-132">avec reformatage des lecteurs de disque et réinstallation du système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="81c4d-132">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="81c4d-133">Restaurer à partir de la sauvegarde</span><span class="sxs-lookup"><span data-stu-id="81c4d-133">Restore from Backup</span></span>  
 <span data-ttu-id="81c4d-134">Si le problème n'est pas matériel et si une restauration réputée en bon état est disponible, restaurez la base de données à partir de la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="81c4d-134">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="81c4d-135">Exécuter DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="81c4d-135">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="81c4d-136">Si aucune sauvegarde saine n'est disponible, exécutez DBCC CHECKDB sans clause REPAIR afin de déterminer l'étendue de l'altération.</span><span class="sxs-lookup"><span data-stu-id="81c4d-136">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="81c4d-137">DBCC CHECKDB recommande une clause REPAIR à utiliser.</span><span class="sxs-lookup"><span data-stu-id="81c4d-137">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="81c4d-138">Puis, exécutez DBCC CHECKDB avec la clause REPAIR adéquate afin de réparer les dommages.</span><span class="sxs-lookup"><span data-stu-id="81c4d-138">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="81c4d-139">Si vous n'êtes pas sûr de l'effet de DBCC CHECKDB avec une clause REPAIR sur vos données, contactez l'assistance technique avant d'exécuter cette instruction.</span><span class="sxs-lookup"><span data-stu-id="81c4d-139">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="81c4d-140">Si l'exécution de DBCC CHECKDB avec une des clauses REPAIR ne résout pas le problème, contactez l’assistance technique.</span><span class="sxs-lookup"><span data-stu-id="81c4d-140">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="81c4d-141">Résultats de l'exécution des options REPAIR</span><span class="sxs-lookup"><span data-stu-id="81c4d-141">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="81c4d-142">L'exécution des options REPAIR entraînera la reconstruction de l'index spécifié et de tous ces index connexes.</span><span class="sxs-lookup"><span data-stu-id="81c4d-142">Running REPAIR will cause the specified index and all its dependent indexes to be rebuilt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81c4d-143">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="81c4d-143">See Also</span></span>  
 [<span data-ttu-id="81c4d-144">DBCC CHECKDB &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="81c4d-144">DBCC CHECKDB &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql)  
  
  
