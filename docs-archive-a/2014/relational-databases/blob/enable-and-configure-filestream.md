---
title: Activer et configurer FILESTREAM | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.technology: filestream
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], enabling
ms.assetid: 78737e19-c65b-48d9-8fa9-aa6f1e1bce73
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f6c0e505bd32636d045519b36e439bc21c7079d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600097"
---
# <a name="enable-and-configure-filestream"></a><span data-ttu-id="4619d-102">Activer et configurer FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="4619d-102">Enable and Configure FILESTREAM</span></span>
  <span data-ttu-id="4619d-103">Pour pouvoir commencer à utiliser FILESTREAM, vous devez l’activer sur l’instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4619d-103">Before you can start to use FILESTREAM, you must enable FILESTREAM on the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span> <span data-ttu-id="4619d-104">Cette rubrique décrit comment activer FILESTREAM à l'aide du Gestionnaire de configuration SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4619d-104">This topic describes how to enable FILESTREAM by using SQL Server Configuration Manager.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4619d-105">Vous ne pouvez pas activer FILESTREAM sur une version 32 bits de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui est exécutée sur un système d'exploitation 64 bits.</span><span class="sxs-lookup"><span data-stu-id="4619d-105">You cannot enable FILESTREAM on a 32-bit version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on a 64-bit operating system.</span></span>  
  
##  <a name="enabling-filestream"></a><a name="enabling"></a> <span data-ttu-id="4619d-106">Activation de FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="4619d-106">Enabling FILESTREAM</span></span>  
  
#### <a name="to-enable-and-change-filestream-settings"></a><span data-ttu-id="4619d-107">Pour activer et modifier des paramètres FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="4619d-107">To enable and change FILESTREAM settings</span></span>  
  
1.  <span data-ttu-id="4619d-108">Dans le menu **Démarrer** , pointez sur **Tous les programmes**, sur [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]et sur **Outils de configuration**, puis cliquez sur **Gestionnaire de configuration SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="4619d-108">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="4619d-109">Dans la liste de services, cliquez avec le bouton droit sur **Services SQL Server**, puis cliquez sur **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="4619d-109">In the list of services, right-click **SQL Server Services**, and then click **Open**.</span></span>  
  
3.  <span data-ttu-id="4619d-110">Dans le composant logiciel enfichable **Gestionnaire de configuration SQL Server** , recherchez l’instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sur laquelle vous souhaitez activer FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="4619d-110">In the **SQL Server Configuration Manager** snap-in, locate the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on which you want to enable FILESTREAM.</span></span>  
  
4.  <span data-ttu-id="4619d-111">Cliquez avec le bouton droit sur l’instance, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="4619d-111">Right-click the instance, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="4619d-112">Dans la boîte de dialogue **Propriétés de SQL Server** , cliquez sur l'onglet **FILESTREAM** .</span><span class="sxs-lookup"><span data-stu-id="4619d-112">In the **SQL Server Properties** dialog box, click the **FILESTREAM** tab.</span></span>  
  
6.  <span data-ttu-id="4619d-113">Cochez la case **Activer FILESTREAM pour l’accès Transact-SQL** .</span><span class="sxs-lookup"><span data-stu-id="4619d-113">Select the **Enable FILESTREAM for Transact-SQL access** check box.</span></span>  
  
7.  <span data-ttu-id="4619d-114">Si vous souhaitez lire et écrire des données FILESTREAM à partir de Windows, cliquez sur **Activer FILESTREAM pour l’accès en continu aux E/S de fichier**.</span><span class="sxs-lookup"><span data-stu-id="4619d-114">If you want to read and write FILESTREAM data from Windows, click **Enable FILESTREAM for file I/O streaming access**.</span></span> <span data-ttu-id="4619d-115">Entrez le nom du partage Windows dans la zone **Nom de partage Windows** .</span><span class="sxs-lookup"><span data-stu-id="4619d-115">Enter the name of the Windows share in the **Windows Share Name** box.</span></span>  
  
8.  <span data-ttu-id="4619d-116">Si des clients distants doivent accéder aux données FILESTREAM stockées sur ce partage, sélectionnez **Autoriser les clients distants à avoir un accès en continu aux données FILESTREAM**.</span><span class="sxs-lookup"><span data-stu-id="4619d-116">If remote clients must access the FILESTREAM data that is stored on this share, select **Allow remote clients to have streaming access to FILESTREAM data**.</span></span>  
  
9. <span data-ttu-id="4619d-117">Cliquez sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="4619d-117">Click **Apply**.</span></span>  
  
10. <span data-ttu-id="4619d-118">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], cliquez sur **Nouvelle requête** pour afficher l'Éditeur de requête.</span><span class="sxs-lookup"><span data-stu-id="4619d-118">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], click **New Query** to display the Query Editor.</span></span>  
  
11. <span data-ttu-id="4619d-119">Dans l'Éditeur de requête, entrez le code [!INCLUDE[tsql](../../includes/tsql-md.md)] suivant :</span><span class="sxs-lookup"><span data-stu-id="4619d-119">In Query Editor, enter the following [!INCLUDE[tsql](../../includes/tsql-md.md)] code:</span></span>  
  
    ```sql  
    EXEC sp_configure filestream_access_level, 2  
    RECONFIGURE  
    ```  
  
12. <span data-ttu-id="4619d-120">Cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="4619d-120">Click **Execute**.</span></span>  
  
13. <span data-ttu-id="4619d-121">Redémarrez le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4619d-121">Restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  

  
##  <a name="best-practices"></a><a name="best"></a> <span data-ttu-id="4619d-122">Bonnes pratiques</span><span class="sxs-lookup"><span data-stu-id="4619d-122">Best Practices</span></span>  
  
###  <a name="physical-configuration-and-maintenance"></a><a name="config"></a><span data-ttu-id="4619d-123">Configuration et maintenance physiques</span><span class="sxs-lookup"><span data-stu-id="4619d-123">Physical Configuration and Maintenance</span></span>  
 <span data-ttu-id="4619d-124">Lorsque vous configurez des volumes de stockage FILESTREAM, prenez en compte les recommandations suivantes :</span><span class="sxs-lookup"><span data-stu-id="4619d-124">When you set up FILESTREAM storage volumes, consider the following guidelines:</span></span>  
  
-   <span data-ttu-id="4619d-125">Désactivez les noms de fichiers courts sur les systèmes informatiques FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="4619d-125">Turn off short file names on FILESTREAM computer systems.</span></span> <span data-ttu-id="4619d-126">La création de noms de fichiers courts demande beaucoup plus de temps.</span><span class="sxs-lookup"><span data-stu-id="4619d-126">Short file names take significantly longer to create.</span></span> <span data-ttu-id="4619d-127">Pour désactiver les noms de fichiers courts, servez-vous de l’utilitaire Windows **fsutil** .</span><span class="sxs-lookup"><span data-stu-id="4619d-127">To disable short file names, use the Windows **fsutil** utility.</span></span>  
  
-   <span data-ttu-id="4619d-128">Défragmentez régulièrement les systèmes informatiques FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="4619d-128">Regularly defragment FILESTREAM computer systems.</span></span>  
  
-   <span data-ttu-id="4619d-129">Utilisez des clusters NTFS de 64 Ko.</span><span class="sxs-lookup"><span data-stu-id="4619d-129">Use 64-KB NTFS clusters.</span></span> <span data-ttu-id="4619d-130">Les volumes compressés doivent être définis à l'aide de clusters NTFS de 4 Ko.</span><span class="sxs-lookup"><span data-stu-id="4619d-130">Compressed volumes must be set to 4-KB NTFS clusters.</span></span>  
  
-   <span data-ttu-id="4619d-131">Désactivez l’indexation sur les volumes FILESTREAM et définissez **disablelastaccess** . Pour définir **disablelastaccess**, servez-vous de l’utilitaire Windows **fsutil** .</span><span class="sxs-lookup"><span data-stu-id="4619d-131">Disable indexing on FILESTREAM volumes and set **disablelastaccess** To set **disablelastaccess**, use the Windows **fsutil** utility.</span></span>  
  
-   <span data-ttu-id="4619d-132">Désactivez l'analyse antivirus des volumes FILESTREAM lorsqu'elle n'est pas nécessaire.</span><span class="sxs-lookup"><span data-stu-id="4619d-132">Disable antivirus scanning of FILESTREAM volumes when it is not unnecessary.</span></span> <span data-ttu-id="4619d-133">Si l'analyse antivirus est nécessaire, ne définissez pas de stratégies qui suppriment automatiquement les fichiers incriminés.</span><span class="sxs-lookup"><span data-stu-id="4619d-133">If antivirus scanning is necessary, avoid setting policies that will automatically delete offending files.</span></span>  
  
-   <span data-ttu-id="4619d-134">Configurez et paramétrez le niveau RAID pour la tolérance de panne et en fonction des performances requises par une application.</span><span class="sxs-lookup"><span data-stu-id="4619d-134">Set up and tune the RAID level for fault tolerance and the performance that is required by an application.</span></span>  
  
||||||  
|-|-|-|-|-|  
|<span data-ttu-id="4619d-135">Niveau RAID</span><span class="sxs-lookup"><span data-stu-id="4619d-135">RAID level</span></span>|<span data-ttu-id="4619d-136">Performances en écriture</span><span class="sxs-lookup"><span data-stu-id="4619d-136">Write performance</span></span>|<span data-ttu-id="4619d-137">Performances en lecture</span><span class="sxs-lookup"><span data-stu-id="4619d-137">Read performance</span></span>|<span data-ttu-id="4619d-138">Tolérance de panne</span><span class="sxs-lookup"><span data-stu-id="4619d-138">Fault tolerance</span></span>|<span data-ttu-id="4619d-139">Notes</span><span class="sxs-lookup"><span data-stu-id="4619d-139">Remarks</span></span>|  
|<span data-ttu-id="4619d-140">RAID 5</span><span class="sxs-lookup"><span data-stu-id="4619d-140">RAID 5</span></span>|<span data-ttu-id="4619d-141">Normal</span><span class="sxs-lookup"><span data-stu-id="4619d-141">Normal</span></span>|<span data-ttu-id="4619d-142">Normal</span><span class="sxs-lookup"><span data-stu-id="4619d-142">Normal</span></span>|<span data-ttu-id="4619d-143">Excellent</span><span class="sxs-lookup"><span data-stu-id="4619d-143">Excellent</span></span>|<span data-ttu-id="4619d-144">Les performances sont meilleures qu'avec un seul disque ou une simple concaténation de disques, mais elles sont moins bonnes qu'avec le niveau RAID 0 ou le niveau RAID 5 utilisant l'agrégation par bandes.</span><span class="sxs-lookup"><span data-stu-id="4619d-144">Performance is better than one disk or JBOD; and less than RAID 0 or RAID 5 with striping.</span></span>|  
|<span data-ttu-id="4619d-145">RAID 0</span><span class="sxs-lookup"><span data-stu-id="4619d-145">RAID 0</span></span>|<span data-ttu-id="4619d-146">Excellent</span><span class="sxs-lookup"><span data-stu-id="4619d-146">Excellent</span></span>|<span data-ttu-id="4619d-147">Excellent</span><span class="sxs-lookup"><span data-stu-id="4619d-147">Excellent</span></span>|<span data-ttu-id="4619d-148">None</span><span class="sxs-lookup"><span data-stu-id="4619d-148">None</span></span>||  
|<span data-ttu-id="4619d-149">RAID 5 + agrégation par bandes</span><span class="sxs-lookup"><span data-stu-id="4619d-149">RAID 5 + stripping</span></span>|<span data-ttu-id="4619d-150">Excellent</span><span class="sxs-lookup"><span data-stu-id="4619d-150">Excellent</span></span>|<span data-ttu-id="4619d-151">Excellent</span><span class="sxs-lookup"><span data-stu-id="4619d-151">Excellent</span></span>|<span data-ttu-id="4619d-152">Excellent</span><span class="sxs-lookup"><span data-stu-id="4619d-152">Excellent</span></span>|<span data-ttu-id="4619d-153">Option la plus chère.</span><span class="sxs-lookup"><span data-stu-id="4619d-153">Most expensive option.</span></span>|  
  

  
###  <a name="physical-database-design"></a><a name="database"></a><span data-ttu-id="4619d-154">Conception de base de données physique</span><span class="sxs-lookup"><span data-stu-id="4619d-154">Physical Database Design</span></span>  
 <span data-ttu-id="4619d-155">Lorsque vous concevez une base de données FILESTREAM, prenez en compte les recommandations suivantes:</span><span class="sxs-lookup"><span data-stu-id="4619d-155">When you design a FILESTREAM database, consider the following guidelines:</span></span>  
  
-   <span data-ttu-id="4619d-156">Les colonnes FILESTREAM doivent être accompagnées d’une `uniqueidentifier` colonne rowguid correspondante.</span><span class="sxs-lookup"><span data-stu-id="4619d-156">FILESTREAM columns must be accompanied by a corresponding `uniqueidentifier`ROWGUID column.</span></span> <span data-ttu-id="4619d-157">Ces types de tables doivent également être accompagnés d'un index unique.</span><span class="sxs-lookup"><span data-stu-id="4619d-157">These kinds of tables must also be accompanied by a unique index.</span></span> <span data-ttu-id="4619d-158">En règle générale, cet index n'est pas un index cluster.</span><span class="sxs-lookup"><span data-stu-id="4619d-158">Typically this index is not a clustered index.</span></span> <span data-ttu-id="4619d-159">Si la logique métier des bases de données requiert un index cluster, vous devez vous assurer que les valeurs stockées dans l'index ne sont pas aléatoires.</span><span class="sxs-lookup"><span data-stu-id="4619d-159">If the databases business logic requires a clustered index, you have to make sure that the values stored in the index are not random.</span></span> <span data-ttu-id="4619d-160">Les valeurs aléatoires entraînent une réorganisation de l'index chaque fois qu'une ligne est ajoutée ou supprimée dans la table.</span><span class="sxs-lookup"><span data-stu-id="4619d-160">Random values will cause the index to be reordered every time that a row is added or removed from the table.</span></span>  
  
-   <span data-ttu-id="4619d-161">Pour des raisons de performances, les groupes de fichiers et conteneurs FILESTREAM doivent résider sur d'autres volumes que ceux du système d'exploitation, de la base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , du journal [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , de la base de données tempdb ou du fichier de pagination.</span><span class="sxs-lookup"><span data-stu-id="4619d-161">For performance reasons, FILESTREAM filegroups and containers should reside on volumes other than the operating system, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log, tempdb, or paging file.</span></span>  
  
-   <span data-ttu-id="4619d-162">La gestion de l'espace et les stratégies ne sont pas prises en charge directement par FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="4619d-162">Space management and policies are not directly supported by FILESTREAM.</span></span> <span data-ttu-id="4619d-163">Toutefois, vous pouvez gérer l'espace et appliquer des stratégies de manière indirecte en affectant chaque groupe de fichiers FILESTREAM à un volume distinct et en utilisant les fonctionnalités de gestion du volume.</span><span class="sxs-lookup"><span data-stu-id="4619d-163">However, you can manage space and apply policies indirectly by assigning each FILESTREAM filegroup to a separate volume and using the volume's management features.</span></span>  
  
  
