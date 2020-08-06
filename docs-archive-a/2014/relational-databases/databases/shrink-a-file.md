---
title: Réduire un fichier | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.shrinkfile.f1
helpviewer_keywords:
- shrinking files
- decreasing file size
- databases [SQL Server], shrinking
- reducing file size
- size [SQL Server], files
- file size [SQL Server]
ms.assetid: ce5c8798-c039-4ab2-81e7-90a8d688b893
author: stevestein
ms.author: sstein
ms.openlocfilehash: ac69e4bd2db3ef7fe0815d235dd1de7d3396b302
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695688"
---
# <a name="shrink-a-file"></a><span data-ttu-id="a533d-102">Réduire un fichier</span><span class="sxs-lookup"><span data-stu-id="a533d-102">Shrink a File</span></span>
  <span data-ttu-id="a533d-103">Cette rubrique explique comment réduire un fichier de données ou un fichier journal dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a533d-103">This topic describes how to shrink a data or log file in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="a533d-104">La réduction des fichiers de données permet de récupérer de l'espace en déplaçant des pages de données de la fin du fichier vers un espace inoccupé plus proche de l'avant du fichier.</span><span class="sxs-lookup"><span data-stu-id="a533d-104">Shrinking data files recovers space by moving pages of data from the end of the file to unoccupied space closer to the front of the file.</span></span> <span data-ttu-id="a533d-105">Lorsqu'une quantité d'espace libre suffisante est créée à la fin du fichier, des pages de données à la fin du fichier peuvent être désallouées et retournées au système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="a533d-105">When enough free space is created at the end of the file, data pages at end of the file can deallocated and returned to the file system.</span></span>  
  
 <span data-ttu-id="a533d-106">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="a533d-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a533d-107">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="a533d-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a533d-108">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="a533d-108">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="a533d-109">Recommandations</span><span class="sxs-lookup"><span data-stu-id="a533d-109">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="a533d-110">Sécurité</span><span class="sxs-lookup"><span data-stu-id="a533d-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a533d-111">**Pour réduire un fichier de données ou un fichier journal, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="a533d-111">**To shrink a data or log file, using:**</span></span>  
  
     [<span data-ttu-id="a533d-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a533d-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="a533d-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a533d-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a533d-114">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="a533d-114">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="a533d-115">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="a533d-115">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="a533d-116">La taille du fichier de données primaire ne peut pas être inférieure à celle du fichier primaire de la base de données model.</span><span class="sxs-lookup"><span data-stu-id="a533d-116">The primary data file cannot be made smaller than the size of the primary file in the model database.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="a533d-117">Recommandations</span><span class="sxs-lookup"><span data-stu-id="a533d-117">Recommendations</span></span>  
  
-   <span data-ttu-id="a533d-118">Les données qui sont déplacées pour réduire un fichier peuvent être dispersées à n'importe quel emplacement disponible dans le fichier.</span><span class="sxs-lookup"><span data-stu-id="a533d-118">Data that is moved to shrink a file can be scattered to any available location in the file.</span></span> <span data-ttu-id="a533d-119">Cela provoque la fragmentation de l'index et peut ralentir les performances des requêtes qui recherchent une plage de l'index.</span><span class="sxs-lookup"><span data-stu-id="a533d-119">This causes index fragmentation and can slow the performance of queries that search a range of the index.</span></span> <span data-ttu-id="a533d-120">Pour éliminer la fragmentation, reconstruisez les index dans le fichier après réduction.</span><span class="sxs-lookup"><span data-stu-id="a533d-120">To eliminate the fragmentation, consider rebuilding the indexes on the file after shrinking.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a533d-121">Sécurité</span><span class="sxs-lookup"><span data-stu-id="a533d-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a533d-122">Autorisations</span><span class="sxs-lookup"><span data-stu-id="a533d-122">Permissions</span></span>  
 <span data-ttu-id="a533d-123">Nécessite l’appartenance au rôle de serveur fixe **sysadmin** ou au rôle de base de données fixe **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="a533d-123">Requires membership in the **sysadmin** fixed server role or the **db_owner** fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a533d-124">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a533d-124">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-shrink-a-data-or-log-file"></a><span data-ttu-id="a533d-125">Pour réduire un fichier de données ou un fichier journal</span><span class="sxs-lookup"><span data-stu-id="a533d-125">To shrink a data or log file</span></span>  
  
1.  <span data-ttu-id="a533d-126">Dans l'Explorateur d'objets, connectez-vous à une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] et développez-la.</span><span class="sxs-lookup"><span data-stu-id="a533d-126">In Object Explorer, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="a533d-127">Développez **Bases de données** , puis cliquez avec le bouton droit sur la base de données à réduire.</span><span class="sxs-lookup"><span data-stu-id="a533d-127">Expand **Databases** and then right-click the database that you want to shrink.</span></span>  
  
3.  <span data-ttu-id="a533d-128">Dans le menu **Tâches**, pointez sur **Réduire**, puis cliquez sur **Fichiers**.</span><span class="sxs-lookup"><span data-stu-id="a533d-128">Point to **Tasks**, point to **Shrink**, and then click **Files**.</span></span>  
  
     <span data-ttu-id="a533d-129">**Sauvegarde de la base de données**</span><span class="sxs-lookup"><span data-stu-id="a533d-129">**Database**</span></span>  
     <span data-ttu-id="a533d-130">Affiche le nom de la base de données sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="a533d-130">Displays the name of the selected database.</span></span>  
  
     <span data-ttu-id="a533d-131">**Type de fichier**</span><span class="sxs-lookup"><span data-stu-id="a533d-131">**File type**</span></span>  
     <span data-ttu-id="a533d-132">Sélectionnez le type du fichier.</span><span class="sxs-lookup"><span data-stu-id="a533d-132">Select the file type for the file.</span></span> <span data-ttu-id="a533d-133">Les choix possibles sont **Données** et **Journal** .</span><span class="sxs-lookup"><span data-stu-id="a533d-133">The available choices are **Data** and **Log** files.</span></span> <span data-ttu-id="a533d-134">La sélection par défaut est **Données**.</span><span class="sxs-lookup"><span data-stu-id="a533d-134">The default selection is **Data**.</span></span> <span data-ttu-id="a533d-135">La sélection d'un autre type de groupe de fichiers modifie en conséquence les sélections des autres champs.</span><span class="sxs-lookup"><span data-stu-id="a533d-135">Selecting a different filegroup type changes the selections in the other fields accordingly.</span></span>  
  
     <span data-ttu-id="a533d-136">**Groupe de fichiers**</span><span class="sxs-lookup"><span data-stu-id="a533d-136">**Filegroup**</span></span>  
     <span data-ttu-id="a533d-137">Sélectionnez un groupe de fichiers dans la liste des groupes de fichiers associés au **Type de fichier** sélectionné auparavant.</span><span class="sxs-lookup"><span data-stu-id="a533d-137">Select a filegroup from the list of Filegroups associated with the selected **File type** above.</span></span> <span data-ttu-id="a533d-138">La sélection d'un autre groupe de fichiers modifie en conséquence les sélections des autres champs.</span><span class="sxs-lookup"><span data-stu-id="a533d-138">Selecting a different filegroup changes the selections in the other fields accordingly.</span></span>  
  
     <span data-ttu-id="a533d-139">**Nom de fichier**</span><span class="sxs-lookup"><span data-stu-id="a533d-139">**File name**</span></span>  
     <span data-ttu-id="a533d-140">Sélectionnez un fichier dans la liste des fichiers disponibles pour le groupe de fichiers et le type de fichier choisis.</span><span class="sxs-lookup"><span data-stu-id="a533d-140">Select a file from the list of available files of the selected filegroup and file type.</span></span>  
  
     <span data-ttu-id="a533d-141">**Lieu**</span><span class="sxs-lookup"><span data-stu-id="a533d-141">**Location**</span></span>  
     <span data-ttu-id="a533d-142">Affiche le chemin d'accès complet au fichier actuellement sélectionné.</span><span class="sxs-lookup"><span data-stu-id="a533d-142">Displays the full path to the currently selected file.</span></span> <span data-ttu-id="a533d-143">Le chemin d'accès n'est pas modifiable, mais il peut être copié dans le Presse-papiers.</span><span class="sxs-lookup"><span data-stu-id="a533d-143">The path is not editable, but it can be copied to the clipboard.</span></span>  
  
     <span data-ttu-id="a533d-144">**Espace actuellement alloué**</span><span class="sxs-lookup"><span data-stu-id="a533d-144">**Currently allocated space**</span></span>  
     <span data-ttu-id="a533d-145">Pour les fichiers de données, affiche l'espace actuellement alloué.</span><span class="sxs-lookup"><span data-stu-id="a533d-145">For data files, displays the current allocated space.</span></span> <span data-ttu-id="a533d-146">Pour les fichiers journaux, ce champ affiche l'espace actuellement alloué qui est calculé à partir de la sortie de DBCC SQLPERF(LOGSPACE).</span><span class="sxs-lookup"><span data-stu-id="a533d-146">For log files, displays the current allocated space computed from the output of DBCC SQLPERF(LOGSPACE).</span></span>  
  
     <span data-ttu-id="a533d-147">**Espace libre disponible**</span><span class="sxs-lookup"><span data-stu-id="a533d-147">**Available free space**</span></span>  
     <span data-ttu-id="a533d-148">Pour les fichiers de données, ce champ affiche l'espace libre actuellement disponible qui est calculé à partir de la sortie de DBCC SHOWFILESTATS(fileid).</span><span class="sxs-lookup"><span data-stu-id="a533d-148">For data files, displays the current available free space computed from the output of DBCC SHOWFILESTATS(fileid).</span></span> <span data-ttu-id="a533d-149">Pour les fichiers journaux, ce champ affiche l'espace libre actuellement disponible qui est calculé à partir de la sortie de DBCC SQLPERF(LOGSPACE).</span><span class="sxs-lookup"><span data-stu-id="a533d-149">For log files, displays the current available free space computed from the output of DBCC SQLPERF(LOGSPACE).</span></span>  
  
     <span data-ttu-id="a533d-150">**Libérer l'espace inutilisé**</span><span class="sxs-lookup"><span data-stu-id="a533d-150">**Release unused space**</span></span>  
     <span data-ttu-id="a533d-151">Tout espace inutilisé dans les fichiers est libéré pour le système d'exploitation et le fichier est réduit à la dernière extension allouée, ce qui en réduit la taille sans toucher aux données.</span><span class="sxs-lookup"><span data-stu-id="a533d-151">Cause any unused space in the files to be released to the operating system and shrink the file to the last allocated extent, reducing the file size without moving any data.</span></span> <span data-ttu-id="a533d-152">Aucune tentative de réaffectation des lignes aux pages non allouées n'est entreprise.</span><span class="sxs-lookup"><span data-stu-id="a533d-152">No attempt is made to relocate rows to unallocated pages.</span></span>  
  
     <span data-ttu-id="a533d-153">**Réorganiser les pages avant de libérer l'espace inutilisé**</span><span class="sxs-lookup"><span data-stu-id="a533d-153">**Reorganize pages before releasing unused space**</span></span>  
     <span data-ttu-id="a533d-154">Équivaut à exécuter DBCC SHRINKFILE en spécifiant la taille du fichier cible.</span><span class="sxs-lookup"><span data-stu-id="a533d-154">Equivalent to executing DBCC SHRINKFILE specifying the target file size.</span></span> <span data-ttu-id="a533d-155">Lorsque cette option est activée, l'utilisateur doit spécifier la taille du fichier cible dans la zone **Réduire le fichier à** .</span><span class="sxs-lookup"><span data-stu-id="a533d-155">When this option is selected, the user must specify a target file size in the **Shrink file to** box.</span></span>  
  
     <span data-ttu-id="a533d-156">**Réduire le fichier à**</span><span class="sxs-lookup"><span data-stu-id="a533d-156">**Shrink file to**</span></span>  
     <span data-ttu-id="a533d-157">Spécifie la taille du fichier cible pour l'opération de réduction.</span><span class="sxs-lookup"><span data-stu-id="a533d-157">Specifies the target file size for the shrink operation.</span></span> <span data-ttu-id="a533d-158">La taille ne peut pas être inférieure à l'espace actuellement alloué ou supérieure à l'extension totale qui est allouée au fichier.</span><span class="sxs-lookup"><span data-stu-id="a533d-158">The size cannot be less than the current allocated space or more than the total extents allocated to the file.</span></span> <span data-ttu-id="a533d-159">Lorsqu'une valeur supérieure à la valeur minimale ou maximale est entrée, la valeur min ou max est rétablie lorsqu'un autre élément est sélectionné ou que vous cliquez sur un bouton de la barre d'outils.</span><span class="sxs-lookup"><span data-stu-id="a533d-159">Entering a value beyond the minimum or the maximum will revert to the min or the max once the focus is changed or when any of the buttons on the toolbar are clicked.</span></span>  
  
     <span data-ttu-id="a533d-160">**Vider le fichier en effectuant une migration des données vers d'autres fichiers dans le même groupe de fichiers**</span><span class="sxs-lookup"><span data-stu-id="a533d-160">**Empty file by migrating the data to other files in the same filegroup**</span></span>  
     <span data-ttu-id="a533d-161">Migre toutes les données du fichier spécifié.</span><span class="sxs-lookup"><span data-stu-id="a533d-161">Migrate all data from the specified file.</span></span> <span data-ttu-id="a533d-162">Cette option permet au fichier d'être supprimé à l'aide de l'instruction ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="a533d-162">This option allows the file to be dropped using the ALTER DATABASE statement.</span></span> <span data-ttu-id="a533d-163">Elle équivaut à exécuter DBCC SHRINKFILE avec l'option EMPTYFILE.</span><span class="sxs-lookup"><span data-stu-id="a533d-163">This option is equivalent to executing DBCC SHRINKFILE with the EMPTYFILE option.</span></span>  
  
4.  <span data-ttu-id="a533d-164">Sélectionnez le type et le nom du fichier.</span><span class="sxs-lookup"><span data-stu-id="a533d-164">Select the file type and file name.</span></span>  
  
5.  <span data-ttu-id="a533d-165">Éventuellement, activez la case à cocher **Libérer l'espace inutilisé** .</span><span class="sxs-lookup"><span data-stu-id="a533d-165">Optionally, select the **Release unused space** check box.</span></span>  
  
     <span data-ttu-id="a533d-166">En activant cette case d'option, tout espace inutilisé dans les fichiers de données est libéré vers le système d'exploitation et le fichier est réduit à la dernière étendue allouée,</span><span class="sxs-lookup"><span data-stu-id="a533d-166">Selecting this option causes any unused space in the file to be released to the operating system and shrinks the file to the last allocated extent.</span></span> <span data-ttu-id="a533d-167">sans déplacement de données.</span><span class="sxs-lookup"><span data-stu-id="a533d-167">This reduces the file size without moving any data.</span></span>  
  
6.  <span data-ttu-id="a533d-168">Éventuellement, activez la case d'option **Réorganiser les pages avant de libérer de l'espace inutilisé** .</span><span class="sxs-lookup"><span data-stu-id="a533d-168">Optionally, select the **Reorganize files before releasing unused space** check box.</span></span> <span data-ttu-id="a533d-169">Si cette case d'option est activée, la valeur **Réduire le fichier à** doit être spécifiée.</span><span class="sxs-lookup"><span data-stu-id="a533d-169">If this is selected, the **Shrink file to** value must be specified.</span></span> <span data-ttu-id="a533d-170">Cette option est désactivée par défaut.</span><span class="sxs-lookup"><span data-stu-id="a533d-170">By default, the option is cleared.</span></span>  
  
     <span data-ttu-id="a533d-171">En activant cette case d'option, tout espace inutilisé dans les fichiers de données est libéré vers le système d'exploitation et, dans la mesure du possible, les lignes sont déplacées dans des pages non allouées.</span><span class="sxs-lookup"><span data-stu-id="a533d-171">Selecting this option causes any unused space in the file to be released to the operating system and tries to relocate rows to unallocated pages.</span></span>  
  
7.  <span data-ttu-id="a533d-172">Éventuellement, entrez le pourcentage maximal d'espace libre à laisser dans le fichier de base de données après la réduction de la base de données.</span><span class="sxs-lookup"><span data-stu-id="a533d-172">Optionally, enter the maximum percentage of free space to be left in the database file after the database has been shrunk.</span></span> <span data-ttu-id="a533d-173">Les valeurs autorisées sont comprises entre 0 et 99.</span><span class="sxs-lookup"><span data-stu-id="a533d-173">Permissible values are between 0 and 99.</span></span> <span data-ttu-id="a533d-174">Cette option est disponible uniquement lorsque **Réorganiser les pages avant de libérer de l'espace inutilisé** est activée.</span><span class="sxs-lookup"><span data-stu-id="a533d-174">This option is only available when **Reorganize files before releasing unused space** is enabled.</span></span>  
  
8.  <span data-ttu-id="a533d-175">Éventuellement, activez la case d'option **Vider le fichier en effectuant une migration des données vers d'autres fichiers dans le même groupe de fichiers** .</span><span class="sxs-lookup"><span data-stu-id="a533d-175">Optionally, select the **Empty file by migrating the data to other files in the same filegroup** check box.</span></span>  
  
     <span data-ttu-id="a533d-176">L'activation de cette case d'option déplace toutes les données du fichier spécifié dans d'autres fichiers du groupe de fichiers.</span><span class="sxs-lookup"><span data-stu-id="a533d-176">Selecting this option moves all data from the specified file to other files in the filegroup.</span></span> <span data-ttu-id="a533d-177">Le fichier vide peut alors être supprimé.</span><span class="sxs-lookup"><span data-stu-id="a533d-177">The empty file can then be deleted.</span></span> <span data-ttu-id="a533d-178">Cette case d'option revient à exécuter DBCC SHRINKFILE avec l'option EMPTYFILE.</span><span class="sxs-lookup"><span data-stu-id="a533d-178">This option is the same as executing DBCC SHRINKFILE with the EMPTYFILE option.</span></span>  
  
9. <span data-ttu-id="a533d-179">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a533d-179">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a533d-180">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a533d-180">Using Transact-SQL</span></span>  
  
#### <a name="to-shrink-a-data-or-log-file"></a><span data-ttu-id="a533d-181">Pour réduire un fichier de données ou un fichier journal</span><span class="sxs-lookup"><span data-stu-id="a533d-181">To shrink a data or log file</span></span>  
  
1.  <span data-ttu-id="a533d-182">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a533d-182">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="a533d-183">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="a533d-183">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="a533d-184">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="a533d-184">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="a533d-185">Cet exemple utilise [DBCC SHRINKFILE](/sql/t-sql/database-console-commands/dbcc-shrinkfile-transact-sql) pour réduire la taille d'un fichier de données nommé `DataFile1` dans la base de données `UserDB` à 7 Mo.</span><span class="sxs-lookup"><span data-stu-id="a533d-185">This example uses [DBCC SHRINKFILE](/sql/t-sql/database-console-commands/dbcc-shrinkfile-transact-sql) to shrink the size of a data file named `DataFile1` in the `UserDB` database to 7 MB.</span></span>  
  
 [!code-sql[DBCC#DBCC_SHRINKFILE1](../../snippets/tsql/SQL14/tsql/dbcc/transact-sql/dbcc_other.sql#dbcc_shrinkfile1)]  
  
## <a name="see-also"></a><span data-ttu-id="a533d-186">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a533d-186">See Also</span></span>  
 <span data-ttu-id="a533d-187">[DBCC SHRINKDATABASE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-shrinkdatabase-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a533d-187">[DBCC SHRINKDATABASE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-shrinkdatabase-transact-sql) </span></span>  
 <span data-ttu-id="a533d-188">[Réduire une base de données](shrink-a-database.md) </span><span class="sxs-lookup"><span data-stu-id="a533d-188">[Shrink a Database](shrink-a-database.md) </span></span>  
 <span data-ttu-id="a533d-189">[Supprimer des fichiers de données ou des fichiers journaux d'une base de données](delete-data-or-log-files-from-a-database.md) </span><span class="sxs-lookup"><span data-stu-id="a533d-189">[Delete Data or Log Files from a Database](delete-data-or-log-files-from-a-database.md) </span></span>  
 <span data-ttu-id="a533d-190">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a533d-190">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span></span>  
 [<span data-ttu-id="a533d-191">sys.database_files &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a533d-191">sys.database_files &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql)  
  
  
