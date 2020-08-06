---
title: Activer la compression sur une table ou un index | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.compwiz.selectaction.f1
- sql12.swb.compwiz.welcome.f1
- sql12.swb.compwiz.scriptfileoption.f1
- sql12.swb.compwiz.createjob.f1
- sql12.swb.compwiz.progress.f1
- sql12.swb.compwiz.outputoptions.f1
- sql12.swb.compwiz.compressiontype.f1
- sql12.swb.compwiz.summary.f1
helpviewer_keywords:
- data compression wizard
- compression [SQL Server], enable
ms.assetid: b7442cff-e616-475a-9c5a-5a765089e5f2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8a51c3b5e0c4e9b5624911310ce20db5a8e060a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612957"
---
# <a name="enable-compression-on-a-table-or-index"></a><span data-ttu-id="cf49c-102">Activer la compression sur une table ou un index</span><span class="sxs-lookup"><span data-stu-id="cf49c-102">Enable Compression on a Table or Index</span></span>
  <span data-ttu-id="cf49c-103">Cette rubrique explique comment activer la compression sur une table ou un index dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cf49c-103">This topic describes how to enable compression on a table or index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="cf49c-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="cf49c-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="cf49c-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="cf49c-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="cf49c-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="cf49c-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="cf49c-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="cf49c-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="cf49c-108">**Pour activer la compression sur une table ou un index à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="cf49c-108">**To enable compression on a table or index, using:**</span></span>  
  
     [<span data-ttu-id="cf49c-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cf49c-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="cf49c-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cf49c-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="cf49c-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="cf49c-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="cf49c-112">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="cf49c-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="cf49c-113">Les tables système ne peuvent pas être activées pour la compression.</span><span class="sxs-lookup"><span data-stu-id="cf49c-113">System tables cannot be enabled for compression.</span></span>  
  
-   <span data-ttu-id="cf49c-114">Si la table est un segment de mémoire, l'opération de reconstruction pour le mode ONLINE sera monothread.</span><span class="sxs-lookup"><span data-stu-id="cf49c-114">If the table is a heap, the rebuild operation for ONLINE mode will be single threaded.</span></span> <span data-ttu-id="cf49c-115">Utilisez le mode OFFLINE pour une opération de reconstruction de segment de mémoire multithread.</span><span class="sxs-lookup"><span data-stu-id="cf49c-115">Use OFFLINE mode for a multi-threaded heap rebuild operation.</span></span> <span data-ttu-id="cf49c-116">Pour plus d’informations sur la compression de données, consultez [Compression des données](data-compression.md).</span><span class="sxs-lookup"><span data-stu-id="cf49c-116">For a more information about data compression, see [Data Compression](data-compression.md).</span></span>  
  
-   <span data-ttu-id="cf49c-117">Vous ne pouvez pas modifier le paramètre de compression d'une partition unique si la table possède des index non alignés.</span><span class="sxs-lookup"><span data-stu-id="cf49c-117">You cannot change the compression setting of a single partition if the table has nonaligned indexes.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="cf49c-118">Sécurité</span><span class="sxs-lookup"><span data-stu-id="cf49c-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="cf49c-119">Autorisations</span><span class="sxs-lookup"><span data-stu-id="cf49c-119">Permissions</span></span>  
 <span data-ttu-id="cf49c-120">Nécessite une autorisation ALTER sur la table ou l'index.</span><span class="sxs-lookup"><span data-stu-id="cf49c-120">Requires ALTER permission on the table or index.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="cf49c-121">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cf49c-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-enable-compression-on-a-table-or-index"></a><span data-ttu-id="cf49c-122">Pour activer la compression sur une table ou un index</span><span class="sxs-lookup"><span data-stu-id="cf49c-122">To enable compression on a table or index</span></span>  
  
1.  <span data-ttu-id="cf49c-123">Dans l'Explorateur d'objets, développez la base de données qui contient la table que vous souhaitez compresser, puis développez le dossier **Tables** .</span><span class="sxs-lookup"><span data-stu-id="cf49c-123">In Object Explorer, expand the database that contains the table that you want to compress and then expand the **Tables** folder.</span></span>  
  
2.  <span data-ttu-id="cf49c-124">Pour compresser un index, développez la table contenant l'index que vous souhaitez compresser, puis développez le dossier **Index** .</span><span class="sxs-lookup"><span data-stu-id="cf49c-124">To compress an index, expand the table that contains the index that you want to compress and then expand the **Indexes** folder.</span></span>  
  
3.  <span data-ttu-id="cf49c-125">Cliquez avec le bouton droit sur la table ou l’index à compresser, pointez sur **Stockage** et sélectionnez **Gérer la compression...** .</span><span class="sxs-lookup"><span data-stu-id="cf49c-125">Right-click the table or index to compress, point to **Storage** and select **Manage Compression...**.</span></span>  
  
4.  <span data-ttu-id="cf49c-126">Dans l'Assistant Compression de données, sur la page **Assistant Compression de données** , cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="cf49c-126">In the Data Compression Wizard, on the **Welcome to the Data Compression Wizard** page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="cf49c-127">Dans la page **Sélectionner le type de compression** , sélectionnez le type de compression à appliquer à chaque partition de la table ou de l'index que vous souhaitez compresser.</span><span class="sxs-lookup"><span data-stu-id="cf49c-127">On the **Select Compression Type** page, select the compression type to apply to each partition in the table or index you want to compress.</span></span> <span data-ttu-id="cf49c-128">Une fois que vous avez terminé, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="cf49c-128">When finished, click **Next**.</span></span>  
  
     <span data-ttu-id="cf49c-129">Les options suivantes sont disponibles dans la page **Sélectionner le type de compression** :</span><span class="sxs-lookup"><span data-stu-id="cf49c-129">The following options are available on the **Select Compression Type** page:</span></span>  
  
     <span data-ttu-id="cf49c-130">Case**Utiliser le même type de compression pour toutes les partitions**</span><span class="sxs-lookup"><span data-stu-id="cf49c-130">**Use the same compression type for all partitions** check box</span></span>  
     <span data-ttu-id="cf49c-131">Sélectionnez cette option pour configurer le même paramètre de compression pour toutes les partitions.</span><span class="sxs-lookup"><span data-stu-id="cf49c-131">Select to configure the same compression setting for all partitions.</span></span> <span data-ttu-id="cf49c-132">La zone de sélection est alors activée et la colonne **Type de compression** de la grille est désactivée.</span><span class="sxs-lookup"><span data-stu-id="cf49c-132">This enables the selection box and disables the **Compression Type** column in the grid.</span></span> <span data-ttu-id="cf49c-133">Lorsqu'une option est sélectionnée, les options dans la liste adjacente sont **None**, **Row**et **Page**.</span><span class="sxs-lookup"><span data-stu-id="cf49c-133">When selected, the options in the adjacent list are **None**, **Row**, and **Page**.</span></span>  
  
     <span data-ttu-id="cf49c-134">**Numéro de partition**</span><span class="sxs-lookup"><span data-stu-id="cf49c-134">**Partition Number**</span></span>  
     <span data-ttu-id="cf49c-135">Répertorie chaque partition de la table ou de l'index.</span><span class="sxs-lookup"><span data-stu-id="cf49c-135">Lists each partition in the table or index.</span></span> <span data-ttu-id="cf49c-136">Cette colonne est en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="cf49c-136">This column is read-only.</span></span>  
  
     <span data-ttu-id="cf49c-137">**Type de compression**</span><span class="sxs-lookup"><span data-stu-id="cf49c-137">**Compression Type**</span></span>  
     <span data-ttu-id="cf49c-138">Sélectionnez l'option de compression de chaque partition.</span><span class="sxs-lookup"><span data-stu-id="cf49c-138">Select the compression option for each partition.</span></span> <span data-ttu-id="cf49c-139">Non disponible lorsque **Utiliser le même type de compression pour toutes les partitions** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="cf49c-139">Is not available when **Use the same compression type for all partitions** is selected.</span></span> <span data-ttu-id="cf49c-140">Les options de la liste sont **None**, **Row**et **Page**.</span><span class="sxs-lookup"><span data-stu-id="cf49c-140">List options are **None**, **Row**, and **Page**.</span></span>  
  
     <span data-ttu-id="cf49c-141">**Limite**</span><span class="sxs-lookup"><span data-stu-id="cf49c-141">**Boundary**</span></span>  
     <span data-ttu-id="cf49c-142">Affiche la limite de la partition.</span><span class="sxs-lookup"><span data-stu-id="cf49c-142">Displays the partition boundary.</span></span> <span data-ttu-id="cf49c-143">Cette colonne est en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="cf49c-143">This column is read-only.</span></span>  
  
     <span data-ttu-id="cf49c-144">**Nombre de lignes**</span><span class="sxs-lookup"><span data-stu-id="cf49c-144">**Row Count**</span></span>  
     <span data-ttu-id="cf49c-145">Affiche le nombre de lignes de cette partition.</span><span class="sxs-lookup"><span data-stu-id="cf49c-145">Displays the number of rows in this partition.</span></span> <span data-ttu-id="cf49c-146">Cette colonne est en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="cf49c-146">This column is read-only.</span></span>  
  
     <span data-ttu-id="cf49c-147">**Espace actuel**</span><span class="sxs-lookup"><span data-stu-id="cf49c-147">**Current Space**</span></span>  
     <span data-ttu-id="cf49c-148">Affiche l'espace actuellement occupé par cette partition en mégaoctets (Mo).</span><span class="sxs-lookup"><span data-stu-id="cf49c-148">Displays the current space this partition occupies in megabytes (MB).</span></span> <span data-ttu-id="cf49c-149">Cette colonne est en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="cf49c-149">This column is read-only.</span></span>  
  
     <span data-ttu-id="cf49c-150">**Espace compressé requis**</span><span class="sxs-lookup"><span data-stu-id="cf49c-150">**Requested Compressed Space**</span></span>  
     <span data-ttu-id="cf49c-151">Après avoir cliqué sur **Calculer**, cette colonne affiche la taille estimée de chaque partition après la compression en utilisant le paramètre spécifié dans la colonne **Type de compression** .</span><span class="sxs-lookup"><span data-stu-id="cf49c-151">After you click **Calculate**, this column displays the estimated size of each partition after compression by using the setting specified in the **Compression Type** column.</span></span> <span data-ttu-id="cf49c-152">Cette colonne est en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="cf49c-152">This column is read-only.</span></span>  
  
     <span data-ttu-id="cf49c-153">**Calculer**</span><span class="sxs-lookup"><span data-stu-id="cf49c-153">**Calculate**</span></span>  
     <span data-ttu-id="cf49c-154">Cliquez sur ce bouton pour estimer la taille de chaque partition après la compression en utilisant le paramètre spécifié dans la colonne **Type de compression** .</span><span class="sxs-lookup"><span data-stu-id="cf49c-154">Click to estimate the size of each partition after compression by using the setting specified in the **Compression Type** column.</span></span>  
  
6.  <span data-ttu-id="cf49c-155">Sur la page **Sélectionner une option de sortie** , spécifiez de quelle manière vous souhaitez terminer votre compression.</span><span class="sxs-lookup"><span data-stu-id="cf49c-155">In the **Select an Output Option** page, specify how you want to complete your compression.</span></span> <span data-ttu-id="cf49c-156">Sélectionnez **Créer un script** pour créer un script SQL basé sur les pages précédentes de l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="cf49c-156">Select **Create Script** to create a SQL script based the previous pages in the wizard.</span></span> <span data-ttu-id="cf49c-157">Sélectionnez **Exécuter immédiatement** pour créer la nouvelle table partitionnée après avoir complété toutes les pages restantes de l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="cf49c-157">Select **Run immediately** to create the new partitioned table after completing all remaining pages in the wizard.</span></span> <span data-ttu-id="cf49c-158">Sélectionnez **Planification** pour créer la nouvelle table partitionnée à un moment prédéterminé dans le futur.</span><span class="sxs-lookup"><span data-stu-id="cf49c-158">Select **Schedule** to create the new partitioned table at a predetermined time in the future.</span></span>  
  
     <span data-ttu-id="cf49c-159">Si vous sélectionnez **Créer un script**, les options suivantes sont disponibles sous **Options de script**:</span><span class="sxs-lookup"><span data-stu-id="cf49c-159">If you select **Create script**, the following options are available under **Script options**:</span></span>  
  
     <span data-ttu-id="cf49c-160">**Générer un script sur fichier**</span><span class="sxs-lookup"><span data-stu-id="cf49c-160">**Script to file**</span></span>  
     <span data-ttu-id="cf49c-161">Génère le script sous la forme d'un fichier .sql.</span><span class="sxs-lookup"><span data-stu-id="cf49c-161">Generates the script as a .sql file.</span></span> <span data-ttu-id="cf49c-162">Entrez un nom de fichier et un emplacement dans la boîte de dialogue **Nom de fichier** ou cliquez sur **Parcourir** pour ouvrir la boîte de dialogue **Emplacement du fichier de script** .</span><span class="sxs-lookup"><span data-stu-id="cf49c-162">Enter a file name and location in the **File name** box or click **Browse** to open the **Script File Location** dialog box.</span></span> <span data-ttu-id="cf49c-163">Pour **Enregistrer sous**, sélectionnez **Texte Unicode** ou **Texte ANSI**.</span><span class="sxs-lookup"><span data-stu-id="cf49c-163">From **Save As**, select **Unicode text** or **ANSI text**.</span></span>  
  
     <span data-ttu-id="cf49c-164">**Générer un script sur le Presse-papiers**</span><span class="sxs-lookup"><span data-stu-id="cf49c-164">**Script to Clipboard**</span></span>  
     <span data-ttu-id="cf49c-165">Enregistre le script dans le Presse-papiers.</span><span class="sxs-lookup"><span data-stu-id="cf49c-165">Saves the script to the Clipboard.</span></span>  
  
     <span data-ttu-id="cf49c-166">**Générer un script dans une nouvelle fenêtre de requête**</span><span class="sxs-lookup"><span data-stu-id="cf49c-166">**Script to New Query Window**</span></span>  
     <span data-ttu-id="cf49c-167">Génère le script dans une nouvelle fenêtre de l'éditeur de requêtes.</span><span class="sxs-lookup"><span data-stu-id="cf49c-167">Generates the script to a new Query Editor window.</span></span> <span data-ttu-id="cf49c-168">Il s'agit de la sélection par défaut.</span><span class="sxs-lookup"><span data-stu-id="cf49c-168">This is the default selection.</span></span>  
  
     <span data-ttu-id="cf49c-169">Si vous sélectionnez **Planification**, cliquez sur **Modifier la planification**.</span><span class="sxs-lookup"><span data-stu-id="cf49c-169">If you select **Schedule**, click **Change schedule**.</span></span>  
  
    1.  <span data-ttu-id="cf49c-170">Dans la boîte de dialogue **Nouvelle planification du travail**, dans la zone **Nom**, entrez le nom de la planification du travail.</span><span class="sxs-lookup"><span data-stu-id="cf49c-170">In the **New Job Schedule** dialog box, in the **Name** box, enter the job schedule's name.</span></span>  
  
    2.  <span data-ttu-id="cf49c-171">Dans la liste **Type de planification** , sélectionnez le type de la planification :</span><span class="sxs-lookup"><span data-stu-id="cf49c-171">On the **Schedule type** list, select the type of schedule:</span></span>  
  
        -   <span data-ttu-id="cf49c-172">**Lancer automatiquement au démarrage de SQL Server Agent**</span><span class="sxs-lookup"><span data-stu-id="cf49c-172">**Start automatically when SQL Server Agent starts**</span></span>  
  
        -   <span data-ttu-id="cf49c-173">**Démarrer dès que les processeurs sont inactifs**</span><span class="sxs-lookup"><span data-stu-id="cf49c-173">**Start whenever the CPUs become idle**</span></span>  
  
        -   <span data-ttu-id="cf49c-174">**Périodique**.</span><span class="sxs-lookup"><span data-stu-id="cf49c-174">**Recurring**.</span></span> <span data-ttu-id="cf49c-175">Sélectionnez cette option si votre nouvelle table partitionnée est mise à jour régulièrement avec de nouvelles informations.</span><span class="sxs-lookup"><span data-stu-id="cf49c-175">Select this option if your new partitioned table updates with new information on a regular basis.</span></span>  
  
        -   <span data-ttu-id="cf49c-176">**Une fois**.</span><span class="sxs-lookup"><span data-stu-id="cf49c-176">**One time**.</span></span> <span data-ttu-id="cf49c-177">Il s'agit de la sélection par défaut.</span><span class="sxs-lookup"><span data-stu-id="cf49c-177">This is the default selection.</span></span>  
  
    3.  <span data-ttu-id="cf49c-178">Activez ou désactivez la case à cocher **Activé** pour activer ou désactiver la planification.</span><span class="sxs-lookup"><span data-stu-id="cf49c-178">Select or clear the **Enabled** check box to enable or disable the schedule.</span></span>  
  
    4.  <span data-ttu-id="cf49c-179">Si vous sélectionnez **Périodique**:</span><span class="sxs-lookup"><span data-stu-id="cf49c-179">If you select **Recurring**:</span></span>  
  
        1.  <span data-ttu-id="cf49c-180">Sous **Fréquence**, dans la liste **Périodicité** , spécifiez la fréquence d'occurrence :</span><span class="sxs-lookup"><span data-stu-id="cf49c-180">Under **Frequency**, on the **Occurs** list, specify the frequency of occurrence:</span></span>  
  
            -   <span data-ttu-id="cf49c-181">Si vous sélectionnez **Quotidienne**, dans la zone **Répéter toutes les** , entrez la fréquence de répétition du travail de planification en jours.</span><span class="sxs-lookup"><span data-stu-id="cf49c-181">If you select **Daily**, in the **Recurs every** box, enter how often the job schedule repeats in days.</span></span>  
  
            -   <span data-ttu-id="cf49c-182">Si vous sélectionnez **Hebdomadaire**, dans la zone **Répéter toutes les** , entrez la fréquence de répétition du travail de planification en semaines.</span><span class="sxs-lookup"><span data-stu-id="cf49c-182">If you select **Weekly**, in the **Recurs every** box, enter how often the job schedule repeats in weeks.</span></span> <span data-ttu-id="cf49c-183">Sélectionnez le jour ou les jours de la semaine pendant lesquels la planification du travail est exécutée.</span><span class="sxs-lookup"><span data-stu-id="cf49c-183">Select the day or days of the week on which the job schedule is run.</span></span>  
  
            -   <span data-ttu-id="cf49c-184">Si vous sélectionnez **Mensuelle**, sélectionnez **Jour** ou **Le**.</span><span class="sxs-lookup"><span data-stu-id="cf49c-184">If you select **Monthly**, select either **Day** or **The**.</span></span>  
  
                -   <span data-ttu-id="cf49c-185">Si vous sélectionnez **Jour**, entrez la date du mois à laquelle vous souhaitez que la planification du travail s'exécute, ainsi que la fréquence de répétition de la planification du travail en mois.</span><span class="sxs-lookup"><span data-stu-id="cf49c-185">If you select **Day**, enter both the date of the month you want the job schedule to run and how often the job schedule repeats in months.</span></span> <span data-ttu-id="cf49c-186">Par exemple, si vous souhaitez que la planification du travail s’exécute le 15 du mois un mois sur deux, sélectionnez **Jour**, puis entrez « 15 » dans la première zone et « 2 » dans la deuxième zone.</span><span class="sxs-lookup"><span data-stu-id="cf49c-186">For example, if you want the job schedule to run on the 15th day of the month every other month, select **Day** and enter "15" in the first box and "2" in the second box.</span></span> <span data-ttu-id="cf49c-187">Notez que le nombre maximum autorisé dans la deuxième zone est « 99 ».</span><span class="sxs-lookup"><span data-stu-id="cf49c-187">Please note that the largest number allowed in the second box is "99".</span></span>  
  
                -   <span data-ttu-id="cf49c-188">Si vous sélectionnez **Le**, sélectionnez le jour spécifique de la semaine et du mois pendant lequel vous voulez que la planification du travail s'exécute et la fréquence à laquelle la planification du travail doit se répéter en mois.</span><span class="sxs-lookup"><span data-stu-id="cf49c-188">If you select **The**, select the specific day of the week within the month that you want the job schedule to run and how often the job schedule repeats in months.</span></span> <span data-ttu-id="cf49c-189">Par exemple, si vous souhaitez que la planification du travail s’exécute le dernier jour de la semaine un mois sur deux, sélectionnez **Jour**, puis **dernier** dans la première liste, **jour ouvrable** dans la deuxième liste et « 2 » dans la dernière zone.</span><span class="sxs-lookup"><span data-stu-id="cf49c-189">For example, if you want the job schedule to run on the last weekday of the month every other month, select **Day**, select **last** from the first list and **weekday** from the second list, and then enter "2" in the last box.</span></span> <span data-ttu-id="cf49c-190">Vous pouvez également sélectionner **premier**, **deuxième**, **troisième**ou **quatrième**, ainsi que des jours de la semaine spécifiques (par exemple, dimanche ou mercredi) dans les deux premières listes.</span><span class="sxs-lookup"><span data-stu-id="cf49c-190">You can also select **first**, **second**, **third**, or **fourth**, as well as specific weekdays (for example: Sunday or Wednesday) from the first two lists.</span></span> <span data-ttu-id="cf49c-191">Notez que le nombre maximum autorisé dans la dernière zone est « 99 ».</span><span class="sxs-lookup"><span data-stu-id="cf49c-191">Please note that the largest number allowed in the last box is "99".</span></span>  
  
        2.  <span data-ttu-id="cf49c-192">Sous **Fréquence quotidienne**, spécifiez la fréquence à laquelle la planification du travail se répète le jour de son exécution :</span><span class="sxs-lookup"><span data-stu-id="cf49c-192">Under **Daily frequency**, specify how often the job schedule repeats on the day the job schedule runs:</span></span>  
  
            -   <span data-ttu-id="cf49c-193">Si vous sélectionnez **Une fois à**, entrez l'heure spécifique à laquelle la planification du travail doit s'exécuter dans la zone **Une fois à** .</span><span class="sxs-lookup"><span data-stu-id="cf49c-193">If you select **Occurs once at**, enter the specific time of day when the job schedule should run in the **Occurs once at** box.</span></span> <span data-ttu-id="cf49c-194">Entrez l'heure, les minutes et les secondes du jour, ainsi que AM ou PM.</span><span class="sxs-lookup"><span data-stu-id="cf49c-194">Enter the hour, minute, and second of the day, as well as AM or PM.</span></span>  
  
            -   <span data-ttu-id="cf49c-195">Si vous sélectionnez **Toutes les**, spécifiez la fréquence à laquelle la planification du travail s'exécute pendant la journée choisie sous **Fréquence**.</span><span class="sxs-lookup"><span data-stu-id="cf49c-195">If you select **Occurs every**, specify how often the job schedule runs during the day chosen under **Frequency**.</span></span> <span data-ttu-id="cf49c-196">Par exemple, si vous souhaitez que la planification du travail se répète toutes les 2 heures le jour d’exécution de la planification du travail, sélectionnez **Toutes les**, entrez « 2 » dans la première zone, puis sélectionnez **heure(s)** dans la liste.</span><span class="sxs-lookup"><span data-stu-id="cf49c-196">For example, if you want the job schedule to repeat every 2 hours during the day that the job schedule is run, select **Occurs every**, enter "2" in the first box, and then select **hour(s)** from the list.</span></span> <span data-ttu-id="cf49c-197">Dans cette liste, vous pouvez également sélectionner **minute(s)** et **seconde(s)** .</span><span class="sxs-lookup"><span data-stu-id="cf49c-197">From this list you can also select **minute(s)** and **second(s)**.</span></span> <span data-ttu-id="cf49c-198">Notez que le nombre maximum autorisé dans la première zone est « 100 ».</span><span class="sxs-lookup"><span data-stu-id="cf49c-198">Please note that the largest number allowed in the first box is "100".</span></span>  
  
                 <span data-ttu-id="cf49c-199">Dans la zone **Début** , entrez l'heure à laquelle l'exécution de la planification du travail doit démarrer.</span><span class="sxs-lookup"><span data-stu-id="cf49c-199">In the **Starting at** box, enter the time that the job schedule should start running.</span></span> <span data-ttu-id="cf49c-200">Dans la zone **Fin** , entrez l'heure à laquelle la planification du travail doit s'arrêter.</span><span class="sxs-lookup"><span data-stu-id="cf49c-200">In the **Ending at** box, enter the time that the job schedule should stop repeating.</span></span> <span data-ttu-id="cf49c-201">Entrez l'heure, les minutes et les secondes du jour, ainsi que AM ou PM.</span><span class="sxs-lookup"><span data-stu-id="cf49c-201">Enter the hour, minute, and second of the day, as well as AM or PM.</span></span>  
  
        3.  <span data-ttu-id="cf49c-202">Sous **Durée**, dans la zone **Date de début**, entrez la date à laquelle vous souhaitez que l'exécution de la planification du travail commence.</span><span class="sxs-lookup"><span data-stu-id="cf49c-202">Under **Duration**, in **Start date**, enter the date that you want the job schedule to start running.</span></span> <span data-ttu-id="cf49c-203">Sélectionnez **Date de fin** ou **Aucune date de fin** pour indiquer à quel moment l'exécution de la planification du travail doit s'arrêter.</span><span class="sxs-lookup"><span data-stu-id="cf49c-203">Select **End date** or **No end date** to indicate when the job schedule should stop running.</span></span> <span data-ttu-id="cf49c-204">Si vous sélectionnez **Date de fin**, entrez la date à laquelle l'exécution de la planification du travail doit s'arrêter.</span><span class="sxs-lookup"><span data-stu-id="cf49c-204">If you select **End date**, enter the date that you want to job schedule to stop running.</span></span>  
  
    5.  <span data-ttu-id="cf49c-205">Si vous sélectionnez **Une fois**sous **Une seule occurrence**, dans la zone **Date** , entrez la date à laquelle la planification du travail est exécutée.</span><span class="sxs-lookup"><span data-stu-id="cf49c-205">If you select **One Time**, under **One-time occurrence**, in the **Date** box, enter the date that the job schedule will be run.</span></span> <span data-ttu-id="cf49c-206">Dans la zone **Heure** , entrez l'heure à laquelle la planification du travail sera exécutée.</span><span class="sxs-lookup"><span data-stu-id="cf49c-206">In the **Time** box, enter the time that the job schedule will be run.</span></span> <span data-ttu-id="cf49c-207">Entrez l'heure, les minutes et les secondes du jour, ainsi que AM ou PM.</span><span class="sxs-lookup"><span data-stu-id="cf49c-207">Enter the hour, minute, and second of the day, as well as AM or PM.</span></span>  
  
    6.  <span data-ttu-id="cf49c-208">Sous **Résumé**, dans **Description**, vérifiez que tous les paramètres de planification du travail sont corrects.</span><span class="sxs-lookup"><span data-stu-id="cf49c-208">Under **Summary**, in **Description**, verify that all job schedule settings are correct.</span></span>  
  
    7.  <span data-ttu-id="cf49c-209">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="cf49c-209">Click **OK**.</span></span>  
  
     <span data-ttu-id="cf49c-210">Après avoir complété cette page, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="cf49c-210">After completing this page, click **Next**.</span></span>  
  
7.  <span data-ttu-id="cf49c-211">Dans la page **Vérifier le résumé** , sous **Vérifier vos sélections**, développez toutes les options disponibles pour vérifier que tous les paramètres de compression sont corrects.</span><span class="sxs-lookup"><span data-stu-id="cf49c-211">On the **Review Summary** page, under **Review your selections**, expand all available options to verify that all compression settings are correct.</span></span> <span data-ttu-id="cf49c-212">Si tout est conforme à vos attentes, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="cf49c-212">If everything is as expected, click **Finish**.</span></span>  
  
8.  <span data-ttu-id="cf49c-213">Sur la page **Progression de l'Assistant Compression de données** , surveillez les informations d'état relatives aux actions de l'Assistant Création de partition.</span><span class="sxs-lookup"><span data-stu-id="cf49c-213">On the **Compression Wizard Progress** page, monitor status information about the actions of the Create Partition Wizard.</span></span> <span data-ttu-id="cf49c-214">Selon les options sélectionnées dans l'Assistant, la page de progression peut contenir une ou plusieurs actions.</span><span class="sxs-lookup"><span data-stu-id="cf49c-214">Depending on the options that you selected in the wizard, the progress page might contain one or more actions.</span></span> <span data-ttu-id="cf49c-215">La zone supérieure affiche l'état global de l'Assistant et le nombre des messages d'état, d'erreur et d'avertissement qu'il a reçus.</span><span class="sxs-lookup"><span data-stu-id="cf49c-215">The top box displays the overall status of the wizard and the number of status, error, and warning messages that the wizard has received.</span></span>  
  
     <span data-ttu-id="cf49c-216">Les options suivantes sont disponibles sur la page **Progression de l'Assistant Compression de données** :</span><span class="sxs-lookup"><span data-stu-id="cf49c-216">The following options are available on the **Compression Wizard Progress** page:</span></span>  
  
     <span data-ttu-id="cf49c-217">**Détails**</span><span class="sxs-lookup"><span data-stu-id="cf49c-217">**Details**</span></span>  
     <span data-ttu-id="cf49c-218">Indique l'action, l'état et tous les messages retournés suite à l'action entreprise par l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="cf49c-218">Provides the action, status, and any messages that are returned from action taken by the wizard.</span></span>  
  
     <span data-ttu-id="cf49c-219">**Action**</span><span class="sxs-lookup"><span data-stu-id="cf49c-219">**Action**</span></span>  
     <span data-ttu-id="cf49c-220">Indique le type et le nom de chaque action.</span><span class="sxs-lookup"><span data-stu-id="cf49c-220">Specifies the type and name of each action.</span></span>  
  
     <span data-ttu-id="cf49c-221">**État**</span><span class="sxs-lookup"><span data-stu-id="cf49c-221">**Status**</span></span>  
     <span data-ttu-id="cf49c-222">Indique si l’action de l’Assistant dans son ensemble a retourné la valeur **Réussite** ou **Échec**.</span><span class="sxs-lookup"><span data-stu-id="cf49c-222">Indicates whether the wizard action as a whole returned the value of **Success** or **Failure**.</span></span>  
  
     <span data-ttu-id="cf49c-223">**Message**</span><span class="sxs-lookup"><span data-stu-id="cf49c-223">**Message**</span></span>  
     <span data-ttu-id="cf49c-224">Indique les messages d'erreur ou d'avertissement retournés par le processus.</span><span class="sxs-lookup"><span data-stu-id="cf49c-224">Provides any error or warning messages that are returned from the process.</span></span>  
  
     <span data-ttu-id="cf49c-225">**Report**</span><span class="sxs-lookup"><span data-stu-id="cf49c-225">**Report**</span></span>  
     <span data-ttu-id="cf49c-226">Crée un rapport qui contient les résultats de l'Assistant Création de partition.</span><span class="sxs-lookup"><span data-stu-id="cf49c-226">Creates a report that contains the results of the Create Partition Wizard.</span></span> <span data-ttu-id="cf49c-227">Les options sont **Afficher le rapport**, **Enregistrer le rapport dans un fichier**, **Copier le rapport dans le Presse-papiers**et **Envoyer le rapport sous forme de courrier électronique**.</span><span class="sxs-lookup"><span data-stu-id="cf49c-227">The options are **View Report**, **Save Report to File**, **Copy Report to Clipboard**, and **Send Report as Email**.</span></span>  
  
     <span data-ttu-id="cf49c-228">**Afficher le rapport**</span><span class="sxs-lookup"><span data-stu-id="cf49c-228">**View Report**</span></span>  
     <span data-ttu-id="cf49c-229">Ouvre la boîte de dialogue **Afficher le rapport** , qui contient un rapport au format texte de la progression de l’Assistant Création de partition.</span><span class="sxs-lookup"><span data-stu-id="cf49c-229">Opens the **View Report** dialog box, which contains a text report of the progress of the Create Partition Wizard.</span></span>  
  
     <span data-ttu-id="cf49c-230">**Enregistrer le rapport dans un fichier**</span><span class="sxs-lookup"><span data-stu-id="cf49c-230">**Save Report to File**</span></span>  
     <span data-ttu-id="cf49c-231">Ouvre la boîte de dialogue **Enregistrer le rapport sous** .</span><span class="sxs-lookup"><span data-stu-id="cf49c-231">Opens the **Save Report As** dialog box.</span></span>  
  
     <span data-ttu-id="cf49c-232">**Copier le rapport dans le Presse-papiers**</span><span class="sxs-lookup"><span data-stu-id="cf49c-232">**Copy Report to Clipboard**</span></span>  
     <span data-ttu-id="cf49c-233">Copie les résultats du rapport de progression de l’Assistant dans le Presse-papiers.</span><span class="sxs-lookup"><span data-stu-id="cf49c-233">Copies the results of the wizard's progress report to the Clipboard.</span></span>  
  
     <span data-ttu-id="cf49c-234">**Envoyer le rapport sous forme de courrier électronique**</span><span class="sxs-lookup"><span data-stu-id="cf49c-234">**Send Report as Email**</span></span>  
     <span data-ttu-id="cf49c-235">Copie les résultats du rapport de progression de l’Assistant dans un e-mail.</span><span class="sxs-lookup"><span data-stu-id="cf49c-235">Copies the results of the wizard's progress report into an email message.</span></span>  
  
     <span data-ttu-id="cf49c-236">Une fois terminé, cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="cf49c-236">When complete, click **Close**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="cf49c-237">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cf49c-237">Using Transact-SQL</span></span>  
  
#### <a name="to-enable-compression-on-a-table"></a><span data-ttu-id="cf49c-238">Pour activer la compression sur une table</span><span class="sxs-lookup"><span data-stu-id="cf49c-238">To enable compression on a table</span></span>  
  
1.  <span data-ttu-id="cf49c-239">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cf49c-239">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="cf49c-240">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="cf49c-240">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="cf49c-241">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="cf49c-241">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="cf49c-242">L'exemple exécute d'abord la procédure stockée `sp_estimate_data_compression_savings` pour retourner la taille estimée de l'objet selon le paramètre de compression ROW.</span><span class="sxs-lookup"><span data-stu-id="cf49c-242">The example first executes the stored procedure `sp_estimate_data_compression_savings` to return the estimated size of the object if it were to use the ROW compression setting.</span></span> <span data-ttu-id="cf49c-243">L'exemple active la compression ROW sur toutes les partitions dans la table spécifiée.</span><span class="sxs-lookup"><span data-stu-id="cf49c-243">The example then enables ROW compression on all partitions in the specified table.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    EXEC sp_estimate_data_compression_savings 'Production', 'TransactionHistory', NULL, NULL, 'ROW' ;  
  
    ALTER TABLE Production.TransactionHistory REBUILD PARTITION = ALL  
    WITH (DATA_COMPRESSION = ROW);   
    GO  
    ```  
  
#### <a name="to-enable-compression-on-an-index"></a><span data-ttu-id="cf49c-244">Pour activer la compression sur un index</span><span class="sxs-lookup"><span data-stu-id="cf49c-244">To enable compression on an index</span></span>  
  
1.  <span data-ttu-id="cf49c-245">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cf49c-245">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="cf49c-246">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="cf49c-246">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="cf49c-247">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="cf49c-247">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="cf49c-248">Dans l'exemple, l'affichage catalogue `sys.indexes` est d'abord interrogé pour retourner le nom et l' `index_id` de chaque index de la table `Production.TransactionHistory` .</span><span class="sxs-lookup"><span data-stu-id="cf49c-248">The example first queries the `sys.indexes` catalog view to return the name and `index_id` for each index on the `Production.TransactionHistory` table.</span></span> <span data-ttu-id="cf49c-249">La procédure stockée `sp_estimate_data_compression_savings` est ensuite exécutée pour retourner la taille estimée de l'ID d'index spécifié selon le paramètre de compression PAGE.</span><span class="sxs-lookup"><span data-stu-id="cf49c-249">It then executes the stored procedure `sp_estimate_data_compression_savings` to return the estimated size of the specified index ID if it were to use the PAGE compression setting.</span></span> <span data-ttu-id="cf49c-250">Enfin, l'exemple reconstruit ID d'index 2 (`IX_TransactionHistory_ProductID`), en spécifiant la compression PAGE.</span><span class="sxs-lookup"><span data-stu-id="cf49c-250">Finally, the example rebuilds index ID 2 (`IX_TransactionHistory_ProductID`), specifying PAGE compression.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    SELECT name, index_id  
    FROM sys.indexes  
    WHERE OBJECT_NAME (object_id) = N'TransactionHistory';  
  
    EXEC sp_estimate_data_compression_savings   
        @schema_name = 'Production',   
        @object_name = 'TransactionHistory',  
        @index_id = 2,   
        @partition_number = NULL,   
        @data_compression = 'PAGE' ;   
  
    ALTER INDEX IX_TransactionHistory_ProductID ON Production.TransactionHistory REBUILD PARTITION = ALL WITH (DATA_COMPRESSION = PAGE);  
    GO  
    ```  
  
 <span data-ttu-id="cf49c-251">Pour plus d’informations, consultez [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) et [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="cf49c-251">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) and [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf49c-252">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cf49c-252">See Also</span></span>  
 <span data-ttu-id="cf49c-253">[Compression de données](data-compression.md) </span><span class="sxs-lookup"><span data-stu-id="cf49c-253">[Data Compression](data-compression.md) </span></span>  
 [<span data-ttu-id="cf49c-254">sp_estimate_data_compression_savings &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cf49c-254">sp_estimate_data_compression_savings &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-estimate-data-compression-savings-transact-sql)  
  
  
