---
title: Compression des sauvegardes (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- log shipping [SQL Server], backup compression
- backup compression [SQL Server], about backup compression
- compression [SQL Server], backup compression
- backups [SQL Server], compression
- backing up [SQL Server], backup compression
- backup compression [SQL Server]
ms.assetid: 05bc9c4f-3947-4dd4-b823-db77519bd4d2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3291a858d8ef037e7cca92eb2e6abb19aec4da8e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601524"
---
# <a name="backup-compression-sql-server"></a><span data-ttu-id="43eaf-102">Compression de sauvegardes (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="43eaf-102">Backup Compression (SQL Server)</span></span>
  <span data-ttu-id="43eaf-103">Cette rubrique décrit la compression des sauvegardes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , notamment les restrictions, les compromis en termes de performances pour la compression des sauvegardes, la configuration pour la compression des sauvegardes et le taux de compression.</span><span class="sxs-lookup"><span data-stu-id="43eaf-103">This topic describes the compression of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backups, including restrictions, performance trade-off of compressing backups, the configuration of backup compression, and the compression ratio.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="43eaf-104">Pour plus d’informations sur les éditions de qui [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] prennent en charge la compression de sauvegarde, consultez [fonctionnalités prises en charge par les éditions de SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="43eaf-104">For information which editions of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] support backup compression, see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span> <span data-ttu-id="43eaf-105">Chaque édition de [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] et ultérieure peut restaurer une sauvegarde compressée.</span><span class="sxs-lookup"><span data-stu-id="43eaf-105">Every edition of [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] and later can restore a compressed backup.</span></span>  
  
  
##  <a name="benefits"></a><a name="Benefits"></a> <span data-ttu-id="43eaf-106">Avantages</span><span class="sxs-lookup"><span data-stu-id="43eaf-106">Benefits</span></span>  
  
-   <span data-ttu-id="43eaf-107">Une sauvegarde compressée étant plus petite qu'une sauvegarde non compressée des mêmes données, la compression d'une sauvegarde requiert en général moins d'E/S de périphérique et, par conséquent, augmente souvent considérablement la vitesse de la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="43eaf-107">Because a compressed backup is smaller than an uncompressed backup of the same data, compressing a backup typically requires less device I/O and therefore usually increases backup speed significantly.</span></span>  
  
     <span data-ttu-id="43eaf-108">Pour plus d'informations, consultez [Impact sur les performances de la compression des sauvegardes](#PerfImpact), plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="43eaf-108">For more information, see [Performance Impact of Compressing Backups](#PerfImpact), later in this topic.</span></span>  
  
  
##  <a name="restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="43eaf-109">Restrictions</span><span class="sxs-lookup"><span data-stu-id="43eaf-109">Restrictions</span></span>  
 <span data-ttu-id="43eaf-110">Les restrictions suivantes s'appliquent aux sauvegardes compressées :</span><span class="sxs-lookup"><span data-stu-id="43eaf-110">The following restrictions apply to compressed backups:</span></span>  
  
-   <span data-ttu-id="43eaf-111">Les sauvegardes compressées et non compressées ne peuvent pas co-exister dans un support de sauvegardes.</span><span class="sxs-lookup"><span data-stu-id="43eaf-111">Compressed and uncompressed backups cannot co-exist in a media set.</span></span>  
  
-   <span data-ttu-id="43eaf-112">Toutefois, les versions précédentes de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ne peuvent pas lire les sauvegardes compressées.</span><span class="sxs-lookup"><span data-stu-id="43eaf-112">Previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot read compressed backups.</span></span>  
  
-   <span data-ttu-id="43eaf-113">NTbackups ne peut pas partager de bande avec les sauvegardes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] compressées.</span><span class="sxs-lookup"><span data-stu-id="43eaf-113">NTbackups cannot share a tape with compressed [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backups.</span></span>  
  
  
##  <a name="performance-impact-of-compressing-backups"></a><a name="PerfImpact"></a> <span data-ttu-id="43eaf-114">Impact sur les performances de la compression des sauvegardes</span><span class="sxs-lookup"><span data-stu-id="43eaf-114">Performance Impact of Compressing Backups</span></span>  
 <span data-ttu-id="43eaf-115">Par défaut, la compression augmente considérablement l'utilisation de l'UC et l'UC supplémentaire consommée par le processus de compression peut avoir un impact néfaste sur les opérations simultanées.</span><span class="sxs-lookup"><span data-stu-id="43eaf-115">By default, compression significantly increases CPU usage, and the additional CPU consumed by the compression process might adversely impact concurrent operations.</span></span> <span data-ttu-id="43eaf-116">Ainsi, dans une session où l’utilisation de l’UC est limitée, il peut être préférable de créer une sauvegarde compressée de priorité basse à l’aide de[Resource Governor](../resource-governor/resource-governor.md).</span><span class="sxs-lookup"><span data-stu-id="43eaf-116">Therefore, you might want to create low-priority compressed backups in a session whose CPU usage is limited by[Resource Governor](../resource-governor/resource-governor.md).</span></span> <span data-ttu-id="43eaf-117">Pour plus d'informations, consultez [Utiliser Resource Governor pour limiter l’utilisation de l’UC par compression de la sauvegarde &#40;Transact-SQL&#41;](use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="43eaf-117">For more information, see [Use Resource Governor to Limit CPU Usage by Backup Compression &#40;Transact-SQL&#41;](use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md).</span></span>  
  
 <span data-ttu-id="43eaf-118">Pour obtenir une bonne image de vos performances d'E/S de sauvegarde, vous pouvez isoler l'E/S de sauvegarde en direction ou depuis des unités en évaluant les types suivants de compteurs de performance :</span><span class="sxs-lookup"><span data-stu-id="43eaf-118">To obtain a good picture of your backup I/O performance, you can isolate the backup I/O to or from devices by evaluating the following sorts of performance counters:</span></span>  
  
-   <span data-ttu-id="43eaf-119">Compteurs de performance d'E/S Windows, tels que les compteurs de disque physique</span><span class="sxs-lookup"><span data-stu-id="43eaf-119">Windows I/O performance counters, such as the physical-disk counters</span></span>  
  
-   <span data-ttu-id="43eaf-120">Compteur **Débit d’unité en octets/s** de l’objet [SQLServer:Backup Device](../performance-monitor/sql-server-backup-device-object.md)</span><span class="sxs-lookup"><span data-stu-id="43eaf-120">The **Device Throughput Bytes/sec** counter of the [SQLServer:Backup Device](../performance-monitor/sql-server-backup-device-object.md) object</span></span>  
  
-   <span data-ttu-id="43eaf-121">Compteur **Débit de sauvegarde/restauration/s** de l’objet [SQLServer:Databases](../performance-monitor/sql-server-databases-object.md)</span><span class="sxs-lookup"><span data-stu-id="43eaf-121">The **Backup/Restore Throughput/sec** counter of the [SQLServer:Databases](../performance-monitor/sql-server-databases-object.md) object</span></span>  
  
 <span data-ttu-id="43eaf-122">Pour des informations sur les compteurs Windows, consultez l'aide de Windows.</span><span class="sxs-lookup"><span data-stu-id="43eaf-122">For information about Windows counters, see Windows help.</span></span> <span data-ttu-id="43eaf-123">Pour obtenir des informations sur l’utilisation des compteurs SQL Server, consultez [Utiliser des objets SQL Server](../performance-monitor/use-sql-server-objects.md).</span><span class="sxs-lookup"><span data-stu-id="43eaf-123">For information about how to work with SQL Server counters, see [Use SQL Server Objects](../performance-monitor/use-sql-server-objects.md).</span></span>  
  
  
##  <a name="calculate-the-compression-ratio-of-a-compressed-backup"></a><a name="CompressionRatio"></a> <span data-ttu-id="43eaf-124">Calculer le taux de compression d'une sauvegarde compressée</span><span class="sxs-lookup"><span data-stu-id="43eaf-124">Calculate the Compression Ratio of a Compressed Backup</span></span>  
 <span data-ttu-id="43eaf-125">Pour calculer le taux de compression d’une sauvegarde, utilisez les valeurs pour la sauvegarde dans les colonnes **backup_size** et **compressed_backup_size** de la table de l’historique [backupset](/sql/relational-databases/system-tables/backupset-transact-sql) , comme suit :</span><span class="sxs-lookup"><span data-stu-id="43eaf-125">To calculate the compression ratio of a backup, use the values for the backup in the **backup_size** and **compressed_backup_size** columns of the [backupset](/sql/relational-databases/system-tables/backupset-transact-sql) history table, as follows:</span></span>  
  
 <span data-ttu-id="43eaf-126">**backup_size**:**compressed_backup_size**</span><span class="sxs-lookup"><span data-stu-id="43eaf-126">**backup_size**:**compressed_backup_size**</span></span>  
  
 <span data-ttu-id="43eaf-127">Par exemple, un taux de compression 3:1 indique que vous économisez environ 66 % de l'espace disque.</span><span class="sxs-lookup"><span data-stu-id="43eaf-127">For example, a 3:1 compression ratio indicates that you are saving about 66% on disk space.</span></span> <span data-ttu-id="43eaf-128">Pour effectuer une requête sur ces colonnes, vous pouvez utiliser l'instruction Transact-SQL suivante :</span><span class="sxs-lookup"><span data-stu-id="43eaf-128">To query on these columns, you can use the following Transact-SQL statement:</span></span>  
  
```  
SELECT backup_size/compressed_backup_size FROM msdb..backupset;  
```  
  
 <span data-ttu-id="43eaf-129">Le taux de compression d'une sauvegarde compressée dépend des données compressées.</span><span class="sxs-lookup"><span data-stu-id="43eaf-129">The compression ratio of a compressed backup depends on the data that has been compressed.</span></span> <span data-ttu-id="43eaf-130">Divers facteurs peuvent avoir une incidence sur le taux de compression obtenu.</span><span class="sxs-lookup"><span data-stu-id="43eaf-130">A variety of factors can impact the compression ratio obtained.</span></span> <span data-ttu-id="43eaf-131">Les facteurs majeurs sont :</span><span class="sxs-lookup"><span data-stu-id="43eaf-131">Major factors include:</span></span>  
  
-   <span data-ttu-id="43eaf-132">Le type des données.</span><span class="sxs-lookup"><span data-stu-id="43eaf-132">The type of data.</span></span>  
  
     <span data-ttu-id="43eaf-133">Les données caractères se compressent plus que d'autres types de données.</span><span class="sxs-lookup"><span data-stu-id="43eaf-133">Character data compresses more than other types of data.</span></span>  
  
-   <span data-ttu-id="43eaf-134">La cohérence des données dans les lignes sur une page.</span><span class="sxs-lookup"><span data-stu-id="43eaf-134">The consistency of the data among rows on a page.</span></span>  
  
     <span data-ttu-id="43eaf-135">En général, si une page contient plusieurs lignes dans lesquelles un champ contient la même valeur, une compression importante peut se produire pour cette valeur.</span><span class="sxs-lookup"><span data-stu-id="43eaf-135">Typically, if a page contains several rows in which a field contains the same value, significant compression might occur for that value.</span></span> <span data-ttu-id="43eaf-136">En revanche, pour une base de données qui contient des données aléatoires ou qui contient une seule grande ligne par page, une sauvegarde compressée serait presque aussi importante qu'une sauvegarde non compressée.</span><span class="sxs-lookup"><span data-stu-id="43eaf-136">In contrast, for a database that contains random data or that contains only one large row per page, a compressed backup would be almost as large as an uncompressed backup.</span></span>  
  
-   <span data-ttu-id="43eaf-137">Si les données sont chiffrées.</span><span class="sxs-lookup"><span data-stu-id="43eaf-137">Whether the data is encrypted.</span></span>  
  
     <span data-ttu-id="43eaf-138">Le taux de compression des données chiffrées est beaucoup moins élevé que celui des données non chiffrées correspondantes.</span><span class="sxs-lookup"><span data-stu-id="43eaf-138">Encrypted data compresses significantly less than equivalent unencrypted data.</span></span> <span data-ttu-id="43eaf-139">Si le chiffrement transparent des données est utilisé pour chiffrer une base de données entière, la compression des sauvegardes ne réduit pas leur taille de manière significative, voire pas du tout.</span><span class="sxs-lookup"><span data-stu-id="43eaf-139">If transparent data encryption is used to encrypt an entire database, compressing backups might not reduce their size by much, if at all.</span></span>  
  
-   <span data-ttu-id="43eaf-140">Si la base de données est compressée.</span><span class="sxs-lookup"><span data-stu-id="43eaf-140">Whether the database is compressed.</span></span>  
  
     <span data-ttu-id="43eaf-141">Si la base de données est compressée, compresser des sauvegardes peut réduire faiblement leur taille, voire pas du tout.</span><span class="sxs-lookup"><span data-stu-id="43eaf-141">If the database is compressed, compressing backups might not reduce their size by much, if at all.</span></span>  
  
  
##  <a name="allocation-of-space-for-the-backup-file"></a><a name="Allocation"></a> <span data-ttu-id="43eaf-142">Allocation d'espace pour le fichier de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="43eaf-142">Allocation of Space for the Backup File</span></span>  
 <span data-ttu-id="43eaf-143">Pour les sauvegardes compressées, la taille du fichier de sauvegarde final dépend de la capacité de compression des données. Or, celle-ci n'est pas connue avant la fin de l'opération de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="43eaf-143">For compressed backups, the size of the final backup file depends on how compressible the data is, and this is unknown before the backup operation finishes.</span></span>  <span data-ttu-id="43eaf-144">Par conséquent, par défaut, lors de la sauvegarde d'une base de données faisant appel à la compression, le moteur de base de données utilise un algorithme de préallocation pour le fichier de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="43eaf-144">Therefore, by default, when backing up a database using compression, the Database Engine uses a pre-allocation algorithm for the backup file.</span></span> <span data-ttu-id="43eaf-145">Cette algorithme préalloue un pourcentage prédéfini de la taille de la base de données pour le fichier de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="43eaf-145">This algorithm pre-allocates a predefined percentage of the size of the database for the backup file.</span></span> <span data-ttu-id="43eaf-146">Si davantage d'espace est requis au cours de l'opération de sauvegarde, le moteur de base de données augmente la taille du fichier.</span><span class="sxs-lookup"><span data-stu-id="43eaf-146">If more space is needed during the backup operation, the Database Engine grows the file.</span></span> <span data-ttu-id="43eaf-147">Si la taille finale est inférieure à l'espace alloué, à la fin de l'opération de sauvegarde, le moteur de base de données réduit le fichier à la taille finale réelle de la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="43eaf-147">If the final size is less than the allocated space, at the end of the backup operation, the Database Engine shrinks the file to the actual final size of the backup.</span></span>  
  
 <span data-ttu-id="43eaf-148">Pour permettre au fichier de sauvegarde de croître autant que nécessaire uniquement afin d'atteindre sa taille définitive, utilisez l'indicateur de trace 3042.</span><span class="sxs-lookup"><span data-stu-id="43eaf-148">To allow the backup file to grow only as needed to reach its final size, use trace flag 3042.</span></span> <span data-ttu-id="43eaf-149">L'indicateur de trace 3042 permet à l'opération de sauvegarde de contourner l'algorithme de préallocation de la compression de sauvegarde par défaut.</span><span class="sxs-lookup"><span data-stu-id="43eaf-149">Trace flag 3042 causes the backup operation to bypass the default backup compression pre-allocation algorithm.</span></span> <span data-ttu-id="43eaf-150">Cet indicateur de trace est utile si vous devez économiser de l'espace en allouant uniquement la taille réelle requise pour la sauvegarde compressée.</span><span class="sxs-lookup"><span data-stu-id="43eaf-150">This trace flag is useful if you need to save on space by allocating only the actual size required for the compressed backup.</span></span> <span data-ttu-id="43eaf-151">Toutefois, le recours à cet indicateur de trace peut entraîner une légère baisse des performances (augmentation possible de la durée de l'opération de sauvegarde).</span><span class="sxs-lookup"><span data-stu-id="43eaf-151">However, using this trace flag might cause a slight performance penalty (a possible increase in the duration of the backup operation).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="43eaf-152">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="43eaf-152">Related Tasks</span></span>  
  
-   [<span data-ttu-id="43eaf-153">Configurer la compression de sauvegarde &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="43eaf-153">Configure Backup Compression &#40;SQL Server&#41;</span></span>](backup-compression-sql-server.md)  
  
-   [<span data-ttu-id="43eaf-154">Afficher ou configurer la compression par défaut des sauvegardes (option de configuration de serveur)</span><span class="sxs-lookup"><span data-stu-id="43eaf-154">View or Configure the backup compression default Server Configuration Option</span></span>](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md)  
  
-   [<span data-ttu-id="43eaf-155">Utiliser Resource Governor pour limiter l’utilisation de l’UC par compression de la sauvegarde &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="43eaf-155">Use Resource Governor to Limit CPU Usage by Backup Compression &#40;Transact-SQL&#41;</span></span>](use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md)  
  
-   [<span data-ttu-id="43eaf-156">DBCC TRACEON &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="43eaf-156">DBCC TRACEON &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-traceon-transact-sql)  
  
-   [<span data-ttu-id="43eaf-157">DBCC TRACEOFF &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="43eaf-157">DBCC TRACEOFF &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-traceoff-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="43eaf-158">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="43eaf-158">See Also</span></span>  
 <span data-ttu-id="43eaf-159">[Vue d’ensemble de la sauvegarde &#40;SQL Server&#41;](backup-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="43eaf-159">[Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md) </span></span>  
 [<span data-ttu-id="43eaf-160">Indicateurs de trace &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="43eaf-160">Trace Flags &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql)  
  
  
