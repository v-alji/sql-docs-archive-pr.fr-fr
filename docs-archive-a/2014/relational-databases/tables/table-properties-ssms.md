---
title: Propriétés de la table | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
f1_keywords:
- sql12.swb.tableproperties.storage.f1
- sql12.SWB.SELECTCOLUMNS.F1
- sql12.swb.tableproperties.filetable.f1
- sql12.swb.tableproperties.general.f1
- sql12.swb.tableproperties.changetracking.f1
ms.assetid: ad8a2fd4-f092-4c0f-be85-54ce8b9d725a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 037e56649d3473e3fe09b9533bcc96b4729870d9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610522"
---
# <a name="table-properties"></a><span data-ttu-id="bb814-102">Propriétés de la table</span><span class="sxs-lookup"><span data-stu-id="bb814-102">Table Properties</span></span>
  <span data-ttu-id="bb814-103">Cette rubrique décrit les propriétés de table qui sont affichées dans la boîte de dialogue Propriétés d'une table dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bb814-103">This topic describes the table properties that are displayed in the Table Properties dialog box in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="bb814-104">Pour plus d’informations sur la façon d’afficher ces propriétés, consultez [Afficher la définition de table](view-the-table-definition.md).</span><span class="sxs-lookup"><span data-stu-id="bb814-104">For more information about how to display these properties, see [View the Table Definition](view-the-table-definition.md).</span></span>  
  
 <span data-ttu-id="bb814-105">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="bb814-105">**In This Topic**</span></span>  
  
1.  [<span data-ttu-id="bb814-106">Page Général</span><span class="sxs-lookup"><span data-stu-id="bb814-106">General Page</span></span>](#GeneralPage)  
  
2.  [<span data-ttu-id="bb814-107">Page de suivi des modifications</span><span class="sxs-lookup"><span data-stu-id="bb814-107">Change Tracking Page</span></span>](#ChangeTracking)  
  
3.  [<span data-ttu-id="bb814-108">Page de la table de fichier</span><span class="sxs-lookup"><span data-stu-id="bb814-108">File Table Page</span></span>](#FileTable)  
  
4.  [<span data-ttu-id="bb814-109">Page de stockage</span><span class="sxs-lookup"><span data-stu-id="bb814-109">Storage Page</span></span>](#Storage)  
  
##  <a name="general-page"></a><a name="GeneralPage"></a> <span data-ttu-id="bb814-110">Page Général</span><span class="sxs-lookup"><span data-stu-id="bb814-110">General Page</span></span>  
 <span data-ttu-id="bb814-111">**Sauvegarde de la base de données**</span><span class="sxs-lookup"><span data-stu-id="bb814-111">**Database**</span></span>  
 <span data-ttu-id="bb814-112">Nom de la base de données qui contient cette table.</span><span class="sxs-lookup"><span data-stu-id="bb814-112">The name of the database containing this table.</span></span>  
  
 <span data-ttu-id="bb814-113">**Serveur**</span><span class="sxs-lookup"><span data-stu-id="bb814-113">**Server**</span></span>  
 <span data-ttu-id="bb814-114">Nom de l'instance actuelle du serveur.</span><span class="sxs-lookup"><span data-stu-id="bb814-114">The name of the current server instance.</span></span>  
  
 <span data-ttu-id="bb814-115">**Utilisateur**</span><span class="sxs-lookup"><span data-stu-id="bb814-115">**User**</span></span>  
 <span data-ttu-id="bb814-116">Nom de l'utilisateur de cette connexion.</span><span class="sxs-lookup"><span data-stu-id="bb814-116">The name of the user of this connection.</span></span>  
  
 <span data-ttu-id="bb814-117">**Date de création**</span><span class="sxs-lookup"><span data-stu-id="bb814-117">**Created Date**</span></span>  
 <span data-ttu-id="bb814-118">Date et heure de création de la table.</span><span class="sxs-lookup"><span data-stu-id="bb814-118">The date and time that the table was created.</span></span>  
  
 <span data-ttu-id="bb814-119">**Nom**</span><span class="sxs-lookup"><span data-stu-id="bb814-119">**Name**</span></span>  
 <span data-ttu-id="bb814-120">Nom de la table.</span><span class="sxs-lookup"><span data-stu-id="bb814-120">The name of the table.</span></span>  
  
 <span data-ttu-id="bb814-121">**Schéma**</span><span class="sxs-lookup"><span data-stu-id="bb814-121">**Schema**</span></span>  
 <span data-ttu-id="bb814-122">Schéma auquel appartient la table.</span><span class="sxs-lookup"><span data-stu-id="bb814-122">The schema that owns the table.</span></span>  
  
 <span data-ttu-id="bb814-123">**Objet système**</span><span class="sxs-lookup"><span data-stu-id="bb814-123">**System object**</span></span>  
 <span data-ttu-id="bb814-124">Indique que cette table est une table système, utilisée par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour contenir des informations internes.</span><span class="sxs-lookup"><span data-stu-id="bb814-124">Indicates this table is a system table, used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to contain internal information.</span></span> <span data-ttu-id="bb814-125">Les tables système ne peuvent pas être référencées ou modifiées directement par les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="bb814-125">Users should not directly change or reference system tables.</span></span>  
  
 <span data-ttu-id="bb814-126">**Valeurs ANSI NULL**</span><span class="sxs-lookup"><span data-stu-id="bb814-126">**ANSI NULLs**</span></span>  
 <span data-ttu-id="bb814-127">Indique si l'objet a été créé avec l'option ANSI NULL activée (ON).</span><span class="sxs-lookup"><span data-stu-id="bb814-127">Indicates if the object was created with the ANSI NULLs option set to ON.</span></span> <span data-ttu-id="bb814-128">Pour plus d’informations, consultez [SET ANSI_NULLS &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-ansi-nulls-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="bb814-128">For more information, see [SET ANSI_NULLS &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-ansi-nulls-transact-sql)</span></span>  
  
 <span data-ttu-id="bb814-129">**Identificateur entre guillemets**</span><span class="sxs-lookup"><span data-stu-id="bb814-129">**Quoted identifier**</span></span>  
 <span data-ttu-id="bb814-130">Indique si l'objet a été créé avec l'option d'identificateur entre guillemets activée (ON).</span><span class="sxs-lookup"><span data-stu-id="bb814-130">Indicates if the object was created with the quoted identifier option set to ON.</span></span> <span data-ttu-id="bb814-131">Pour plus d’informations, consultez [SET QUOTED_IDENTIFIER &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-quoted-identifier-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="bb814-131">For more information, see [SET QUOTED_IDENTIFIER &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-quoted-identifier-transact-sql)</span></span>  
  
 <span data-ttu-id="bb814-132">**Escalade de verrous**</span><span class="sxs-lookup"><span data-stu-id="bb814-132">**Lock Escalation**</span></span>  
 <span data-ttu-id="bb814-133">Indique la granularité de l'escalade de verrous de la table.</span><span class="sxs-lookup"><span data-stu-id="bb814-133">Indicates the lock escalation granularity of the table.</span></span> <span data-ttu-id="bb814-134">Pour plus d'informations sur le verrouillage dans le moteur de base de données, consultez [Guide du verrouillage des transactions et du contrôle de version de ligne SQL Server](https://msdn.microsoft.com/library/jj856598.aspx).</span><span class="sxs-lookup"><span data-stu-id="bb814-134">For more information about locking in the Database Engine, see [SQL Server Transaction Locking and Row Versioning Guide](https://msdn.microsoft.com/library/jj856598.aspx).</span></span> <span data-ttu-id="bb814-135">Les valeurs possibles sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="bb814-135">Possible values are:</span></span>  
  
 <span data-ttu-id="bb814-136">AUTO</span><span class="sxs-lookup"><span data-stu-id="bb814-136">AUTO</span></span>  
 <span data-ttu-id="bb814-137">Cette option permet au [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] de sélectionner la granularité de l'escalade de verrous appropriée pour le schéma de la table.</span><span class="sxs-lookup"><span data-stu-id="bb814-137">This option allows the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] to select the lock escalation granularity that is appropriate for the table schema.</span></span>  
  
-   <span data-ttu-id="bb814-138">Si la table est partitionnée, l'escalade de verrous sera autorisée jusqu'à la granularité de segment de mémoire ou d'arbre B (B-tree) (HoBT, Heap or B-tree).</span><span class="sxs-lookup"><span data-stu-id="bb814-138">If the table is partitioned, lock escalation will be allowed to the heap or B-tree (HoBT) granularity.</span></span> <span data-ttu-id="bb814-139">Une fois que le verrou a atteint le niveau HoBT, il n'est plus escaladé jusqu'à la granularité TABLE.</span><span class="sxs-lookup"><span data-stu-id="bb814-139">After the lock is escalated to the HoBT level, the lock will not be escalated later to TABLE granularity.</span></span>  
  
-   <span data-ttu-id="bb814-140">Si la table n'est pas partitionnée, l'escalade de verrous continue jusqu'à la granularité TABLE.</span><span class="sxs-lookup"><span data-stu-id="bb814-140">If the table is not partitioned, the lock escalation will be done to the TABLE granularity.</span></span>  
  
 <span data-ttu-id="bb814-141">TABLE</span><span class="sxs-lookup"><span data-stu-id="bb814-141">TABLE</span></span>  
 <span data-ttu-id="bb814-142">L'escalade de verrous continue jusqu'à la granularité TABLE que la table soit ou non partitionnée.</span><span class="sxs-lookup"><span data-stu-id="bb814-142">Lock escalation will be done at table-level granularity regardless of whether the table is partitioned or not partitioned.</span></span> <span data-ttu-id="bb814-143">TABLE est la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="bb814-143">TABLE is the default value.</span></span>  
  
 <span data-ttu-id="bb814-144">DISABLE</span><span class="sxs-lookup"><span data-stu-id="bb814-144">DISABLE</span></span>  
 <span data-ttu-id="bb814-145">Empêche l'escalade de verrous dans la plupart des cas.</span><span class="sxs-lookup"><span data-stu-id="bb814-145">Prevents lock escalation in most cases.</span></span> <span data-ttu-id="bb814-146">Les verrous de niveau table ne sont pas totalement interdits.</span><span class="sxs-lookup"><span data-stu-id="bb814-146">Table-level locks are not completely disallowed.</span></span> <span data-ttu-id="bb814-147">Par exemple, lorsque vous analysez une table ne contenant aucun index cluster sous le niveau d'isolement sérialisable, le [!INCLUDE[ssDE](../../includes/ssde-md.md)] doit prendre un verrou de table pour protéger l'intégrité des données.</span><span class="sxs-lookup"><span data-stu-id="bb814-147">For example, when you are scanning a table that has no clustered index under the serializable isolation level, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] must take a table lock to protect data integrity.</span></span>  
  
 <span data-ttu-id="bb814-148">**Table répliquée**</span><span class="sxs-lookup"><span data-stu-id="bb814-148">**Table is replicated**</span></span>  
 <span data-ttu-id="bb814-149">Indique lorsqu'une table est répliquée vers une autre base de données à l'aide de la réplication [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bb814-149">Indicates when the table is replicated to another database using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] replication.</span></span> <span data-ttu-id="bb814-150">Les valeurs possibles sont `True` ou `False`.</span><span class="sxs-lookup"><span data-stu-id="bb814-150">Possible values are `True` or `False`.</span></span>  
  
##  <a name="change-tracking-page"></a><a name="ChangeTracking"></a><span data-ttu-id="bb814-151">Page Change Tracking</span><span class="sxs-lookup"><span data-stu-id="bb814-151">Change Tracking Page</span></span>  
 <span data-ttu-id="bb814-152">**Suivi des modifications**</span><span class="sxs-lookup"><span data-stu-id="bb814-152">**Change Tracking**</span></span>  
 <span data-ttu-id="bb814-153">Indique si le suivi des modifications est activé pour la table.</span><span class="sxs-lookup"><span data-stu-id="bb814-153">Indicates whether change tracking is enabled for the table.</span></span> <span data-ttu-id="bb814-154">La valeur par défaut est `False`.</span><span class="sxs-lookup"><span data-stu-id="bb814-154">The default value is `False`.</span></span>  
  
 <span data-ttu-id="bb814-155">Cette option est disponible uniquement lorsque le suivi des modifications est activé pour la base de données.</span><span class="sxs-lookup"><span data-stu-id="bb814-155">This option is available only when change tracking is enabled for the database.</span></span>  
  
 <span data-ttu-id="bb814-156">Pour activer le suivi des modifications, la table doit disposer d'une clé primaire et vous devez posséder une autorisation de modifier la table.</span><span class="sxs-lookup"><span data-stu-id="bb814-156">To enable change tracking, the table must have a primary key, and you must have permission to modify the table.</span></span> <span data-ttu-id="bb814-157">Vous pouvez configurer le suivi des modifications en utilisant [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="bb814-157">You can configure change tracking by using [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
 <span data-ttu-id="bb814-158">**Suivre les colonnes mises à jour**</span><span class="sxs-lookup"><span data-stu-id="bb814-158">**Track Columns Updated**</span></span>  
 <span data-ttu-id="bb814-159">Indique si le [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] effectue un suivi des colonnes mises à jour.</span><span class="sxs-lookup"><span data-stu-id="bb814-159">Indicates whether the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] tracks which columns were updated.</span></span>  
  
 <span data-ttu-id="bb814-160">Pour plus d’informations sur le suivi des modifications, consultez [À propos du suivi des modifications &#40;SQL Server&#41;](../track-changes/about-change-tracking-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="bb814-160">For more information about Change Tracking, see [About Change Tracking &#40;SQL Server&#41;](../track-changes/about-change-tracking-sql-server.md).</span></span>  
  
##  <a name="filetable-page"></a><a name="FileTable"></a><span data-ttu-id="bb814-161">Page filetable</span><span class="sxs-lookup"><span data-stu-id="bb814-161">FileTable Page</span></span>  
 <span data-ttu-id="bb814-162">Affiche les propriétés de la table associée aux FileTables.</span><span class="sxs-lookup"><span data-stu-id="bb814-162">Displays properties of the table related to FileTables.</span></span> <span data-ttu-id="bb814-163">Pour plus d’informations, consultez [FileTables &#40;SQL Server&#41;](../blob/filetables-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="bb814-163">For more information, see [FileTables &#40;SQL Server&#41;](../blob/filetables-sql-server.md).</span></span>  
  
 <span data-ttu-id="bb814-164">**Classement de la colonne de noms de FileTable**</span><span class="sxs-lookup"><span data-stu-id="bb814-164">**FileTable name column collation**</span></span>  
 <span data-ttu-id="bb814-165">Classement appliqué à la colonne **Nom** dans un FileTable.</span><span class="sxs-lookup"><span data-stu-id="bb814-165">The collation that is applied to the **Name** column in a FileTable.</span></span> <span data-ttu-id="bb814-166">La colonne de **nom** contient des noms de fichier et de répertoire.</span><span class="sxs-lookup"><span data-stu-id="bb814-166">The **Name** column contains file and directory names.</span></span>  
  
 <span data-ttu-id="bb814-167">**Nom du répertoire FileTable**</span><span class="sxs-lookup"><span data-stu-id="bb814-167">**FileTable directory name**</span></span>  
 <span data-ttu-id="bb814-168">Dossier racine pour le FileTable.</span><span class="sxs-lookup"><span data-stu-id="bb814-168">The root folder for the FileTable.</span></span>  
  
 <span data-ttu-id="bb814-169">**Espace de noms FileTable activé**</span><span class="sxs-lookup"><span data-stu-id="bb814-169">**FileTable namespace enabled**</span></span>  
 <span data-ttu-id="bb814-170">Lorsque `True` est défini, cette valeur indique que la table est un FileTable.</span><span class="sxs-lookup"><span data-stu-id="bb814-170">When `True`, this value indicates that the table is a FileTable.</span></span> <span data-ttu-id="bb814-171">Si vous remplacez cette valeur par `False`, vous modifiez le FileTable pour en faire une table utilisateur ordinaire.</span><span class="sxs-lookup"><span data-stu-id="bb814-171">If you change this value to `False`, you are changing the FileTable to an ordinary user table.</span></span> <span data-ttu-id="bb814-172">Si vous souhaitez ultérieurement remodifier la table pour en faire un FileTable, la table devra réussir la vérification de cohérence de FileTable pour la conversion puisse aboutir.</span><span class="sxs-lookup"><span data-stu-id="bb814-172">If you later want to change the table back to a FileTable, the table will have to pass a FileTable consistency check before the conversion succeeds.</span></span>  
  
##  <a name="storage-page"></a><a name="Storage"></a><span data-ttu-id="bb814-173">Page de stockage</span><span class="sxs-lookup"><span data-stu-id="bb814-173">Storage Page</span></span>  
 <span data-ttu-id="bb814-174">Affiche les propriétés de stockage de la table sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="bb814-174">Displays the storage related properties of the selected table.</span></span>  
  
### <a name="compression"></a><span data-ttu-id="bb814-175">Compression</span><span class="sxs-lookup"><span data-stu-id="bb814-175">Compression</span></span>  
 <span data-ttu-id="bb814-176">**Type de compression**</span><span class="sxs-lookup"><span data-stu-id="bb814-176">**Compression type**</span></span>  
 <span data-ttu-id="bb814-177">Type de compression de la table.</span><span class="sxs-lookup"><span data-stu-id="bb814-177">The compression type of the table.</span></span> <span data-ttu-id="bb814-178">Cette propriété est disponible uniquement pour les tables qui ne sont pas partitionnées.</span><span class="sxs-lookup"><span data-stu-id="bb814-178">This property is only available for tables that are not partitioned.</span></span> <span data-ttu-id="bb814-179">Pour plus d’informations, consultez [Compression de données](../data-compression/data-compression.md).</span><span class="sxs-lookup"><span data-stu-id="bb814-179">For more information, see [Data Compression](../data-compression/data-compression.md).</span></span>  
  
 <span data-ttu-id="bb814-180">**Partitions utilisant la compression de page**</span><span class="sxs-lookup"><span data-stu-id="bb814-180">**Partitions using page compression**</span></span>  
 <span data-ttu-id="bb814-181">Numéros des partitions qui utilisent la compression de page.</span><span class="sxs-lookup"><span data-stu-id="bb814-181">The partition numbers that are using page compression.</span></span> <span data-ttu-id="bb814-182">Cette propriété est disponible uniquement pour les tables partitionnées.</span><span class="sxs-lookup"><span data-stu-id="bb814-182">This property is only available for partitioned tables.</span></span>  
  
 <span data-ttu-id="bb814-183">**Partitions non compressées**</span><span class="sxs-lookup"><span data-stu-id="bb814-183">**Partitions not compressed**</span></span>  
 <span data-ttu-id="bb814-184">Numéros des partitions qui ne sont pas compressées.</span><span class="sxs-lookup"><span data-stu-id="bb814-184">The partition numbers that are not compressed.</span></span> <span data-ttu-id="bb814-185">Cette propriété est disponible uniquement pour les tables partitionnées.</span><span class="sxs-lookup"><span data-stu-id="bb814-185">This property is only available for partitioned tables.</span></span>  
  
 <span data-ttu-id="bb814-186">**Partitions utilisant la compression de ligne**</span><span class="sxs-lookup"><span data-stu-id="bb814-186">**Partitions using row compression**</span></span>  
 <span data-ttu-id="bb814-187">Numéros des partitions qui utilisent la compression de ligne.</span><span class="sxs-lookup"><span data-stu-id="bb814-187">The partition numbers that are using row compression.</span></span> <span data-ttu-id="bb814-188">Cette propriété est disponible uniquement pour les tables partitionnées.</span><span class="sxs-lookup"><span data-stu-id="bb814-188">This property is only available for partitioned tables.</span></span>  
  
### <a name="filegroup"></a><span data-ttu-id="bb814-189">Groupe de fichiers</span><span class="sxs-lookup"><span data-stu-id="bb814-189">Filegroup</span></span>  
 <span data-ttu-id="bb814-190">**Groupe de fichiers de texte**</span><span class="sxs-lookup"><span data-stu-id="bb814-190">**Text filegroup**</span></span>  
 <span data-ttu-id="bb814-191">Nom du groupe de fichiers qui contient les données texte de la table.</span><span class="sxs-lookup"><span data-stu-id="bb814-191">The name of the filegroup that contains the text data for the table.</span></span>  
  
 <span data-ttu-id="bb814-192">**Groupe de fichiers**</span><span class="sxs-lookup"><span data-stu-id="bb814-192">**Filegroup**</span></span>  
 <span data-ttu-id="bb814-193">Nom du groupe de fichiers contenant la table.</span><span class="sxs-lookup"><span data-stu-id="bb814-193">The name of the filegroup that contains the table.</span></span>  
  
 <span data-ttu-id="bb814-194">**Table partitionnée**</span><span class="sxs-lookup"><span data-stu-id="bb814-194">**Table is partitioned**</span></span>  
 <span data-ttu-id="bb814-195">Les valeurs possibles sont `True` et `False`.</span><span class="sxs-lookup"><span data-stu-id="bb814-195">Possible values are `True` and `False`.</span></span>  
  
 <span data-ttu-id="bb814-196">**Groupe de fichiers Filestream**</span><span class="sxs-lookup"><span data-stu-id="bb814-196">**Filestream filegroup**</span></span>  
 <span data-ttu-id="bb814-197">Indiquez le nom du groupe de fichiers de données FILESTREAM si la table contient une colonne `varbinary(max)` avec l'attribut FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="bb814-197">Specify the name of the FILESTREAM data filegroup if the table has a `varbinary(max)` column that has the FILESTREAM attribute.</span></span> <span data-ttu-id="bb814-198">La valeur par défaut est le groupe de fichiers de données FILESTREAM par défaut.</span><span class="sxs-lookup"><span data-stu-id="bb814-198">The default value is the default FILESTREAM data filegroup.</span></span>  
  
 <span data-ttu-id="bb814-199">Si la table ne contient pas de données FILESTREAM, ce champ est vierge.</span><span class="sxs-lookup"><span data-stu-id="bb814-199">If the table does not contain FILESTREAM data, the field is blank.</span></span>  
  
### <a name="general"></a><span data-ttu-id="bb814-200">Général</span><span class="sxs-lookup"><span data-stu-id="bb814-200">General</span></span>  
 <span data-ttu-id="bb814-201">**Le format de stockage VarDecimal est activé**</span><span class="sxs-lookup"><span data-stu-id="bb814-201">**Vardecimal storage format is enabled**</span></span>  
 <span data-ttu-id="bb814-202">Lorsque `True` la valeur est, cette valeur en lecture seule indique que les `decimal` `numeric` types de données et sont stockés à l’aide du format de stockage vardecimal.</span><span class="sxs-lookup"><span data-stu-id="bb814-202">When `True`, this read-only value indicates that `decimal` and `numeric` data types are stored by using the vardecimal storage format.</span></span> <span data-ttu-id="bb814-203">Pour modifier cette option, utilisez l' `vardecimal storage format` option de [sp_tableoption](/sql/relational-databases/system-stored-procedures/sp-tableoption-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="bb814-203">To change this option, use the `vardecimal storage format` option of [sp_tableoption](/sql/relational-databases/system-stored-procedures/sp-tableoption-transact-sql).</span></span> <span data-ttu-id="bb814-204">Le format de stockage vardecimal est déconseillé.</span><span class="sxs-lookup"><span data-stu-id="bb814-204">Vardecimal storage format is deprecated.</span></span> <span data-ttu-id="bb814-205">Utilisez plutôt la compression ROW.</span><span class="sxs-lookup"><span data-stu-id="bb814-205">Use ROW compression instead.</span></span>  
  
 <span data-ttu-id="bb814-206">**Espace d'index**</span><span class="sxs-lookup"><span data-stu-id="bb814-206">**Index space**</span></span>  
 <span data-ttu-id="bb814-207">Quantité d'espace occupée par les index dans la table, en mégaoctets.</span><span class="sxs-lookup"><span data-stu-id="bb814-207">The amount of space in megabytes that the indexes occupy in the table.</span></span> <span data-ttu-id="bb814-208">Cette valeur n'inclut pas l'utilisation de l'espace des index XML pour la table.</span><span class="sxs-lookup"><span data-stu-id="bb814-208">This value does not include XML index space usage for the table.</span></span> <span data-ttu-id="bb814-209">Si les index XML appartiennent à la table, utilisez plutôt [sp_spaceused](/sql/relational-databases/system-stored-procedures/sp-spaceused-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="bb814-209">If XML indexes belong to the table, use [sp_spaceused](/sql/relational-databases/system-stored-procedures/sp-spaceused-transact-sql) instead.</span></span>  
  
 <span data-ttu-id="bb814-210">**Nombre de lignes**</span><span class="sxs-lookup"><span data-stu-id="bb814-210">**Row count**</span></span>  
 <span data-ttu-id="bb814-211">Nombre de lignes du tableau.</span><span class="sxs-lookup"><span data-stu-id="bb814-211">The number of rows in the table.</span></span>  
  
 <span data-ttu-id="bb814-212">**Espace de données**</span><span class="sxs-lookup"><span data-stu-id="bb814-212">**Data space**</span></span>  
 <span data-ttu-id="bb814-213">Quantité d'espace occupée par les données dans la table, en mégaoctets.</span><span class="sxs-lookup"><span data-stu-id="bb814-213">The amount of space in megabytes that the data occupies in the table.</span></span>  
  
### <a name="partitioning"></a><span data-ttu-id="bb814-214">Partitionnement</span><span class="sxs-lookup"><span data-stu-id="bb814-214">Partitioning</span></span>  
 <span data-ttu-id="bb814-215">Cette section est disponible uniquement si la table est partitionnée.</span><span class="sxs-lookup"><span data-stu-id="bb814-215">This section is only available if the table is partitioned.</span></span> <span data-ttu-id="bb814-216">Pour plus d’informations, consultez [Tables et index partitionnés](../partitions/partitioned-tables-and-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="bb814-216">For more information, see [Partitioned Tables and Indexes](../partitions/partitioned-tables-and-indexes.md).</span></span>  
  
 <span data-ttu-id="bb814-217">**Colonne de partition**</span><span class="sxs-lookup"><span data-stu-id="bb814-217">**Partition column**</span></span>  
 <span data-ttu-id="bb814-218">Nom de la colonne sur laquelle la table est partitionnée.</span><span class="sxs-lookup"><span data-stu-id="bb814-218">The name of the column on which the table is partitioned.</span></span>  
  
 <span data-ttu-id="bb814-219">**Schéma de partition**</span><span class="sxs-lookup"><span data-stu-id="bb814-219">**Partition scheme**</span></span>  
 <span data-ttu-id="bb814-220">Nom du schéma de partition si la table est partitionnée.</span><span class="sxs-lookup"><span data-stu-id="bb814-220">Name of the partition scheme if the table is partitioned.</span></span> <span data-ttu-id="bb814-221">Si la table n'est pas partitionnée, le champ est vide.</span><span class="sxs-lookup"><span data-stu-id="bb814-221">If the table is not partitioned, the field is blank.</span></span>  
  
 <span data-ttu-id="bb814-222">**Nombre de partitions**</span><span class="sxs-lookup"><span data-stu-id="bb814-222">**Number of partitions**</span></span>  
 <span data-ttu-id="bb814-223">Nombre de partitions de la table.</span><span class="sxs-lookup"><span data-stu-id="bb814-223">The number of partitions in the table.</span></span>  
  
 <span data-ttu-id="bb814-224">**Schéma de partition FILESTREAM**</span><span class="sxs-lookup"><span data-stu-id="bb814-224">**FILESTREAM partition scheme**</span></span>  
 <span data-ttu-id="bb814-225">Nom du schéma de partition FILESTREAM, si la table est partitionnée.</span><span class="sxs-lookup"><span data-stu-id="bb814-225">The name of the FILESTREAM partition scheme if the table is partitioned.</span></span> <span data-ttu-id="bb814-226">Si la table n'est pas partitionnée, le champ est vide.</span><span class="sxs-lookup"><span data-stu-id="bb814-226">If the table is not partitioned, the field is blank.</span></span>  
  
 <span data-ttu-id="bb814-227">Le schéma de partition FILESTREAM doit être symétrique avec le schéma spécifié dans l'option **Schéma de partition** .</span><span class="sxs-lookup"><span data-stu-id="bb814-227">The FILESTREAM partition scheme must be symmetric to the scheme that is specified in the **Partition scheme** option.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb814-228">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bb814-228">See Also</span></span>  
 <span data-ttu-id="bb814-229">[Afficher la définition de la table](view-the-table-definition.md) </span><span class="sxs-lookup"><span data-stu-id="bb814-229">[View the Table Definition](view-the-table-definition.md) </span></span>  
 [<span data-ttu-id="bb814-230">Modifier des colonnes &#40;moteur de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="bb814-230">Modify Columns &#40;Database Engine&#41;</span></span>](../tables/modify-columns-database-engine.md)  
  
  
