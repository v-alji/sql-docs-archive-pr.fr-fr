---
title: Sauvegarder la base de données (page Options de sauvegarde) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.backupdatabase.options.f1
- swb.backupdatabase.options.f1
ms.assetid: df0ddcdb-c94e-472b-b786-469ae8117b93
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ffd527ba4334244c7fd4c5d4a73099093cb8520b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614688"
---
# <a name="back-up-database-backup-options-page"></a><span data-ttu-id="ef272-102">Sauvegarder la base de données (page Options de sauvegarde)</span><span class="sxs-lookup"><span data-stu-id="ef272-102">Back Up Database (Backup Options Page)</span></span>
  <span data-ttu-id="ef272-103">Utilisez la page  **Options de sauvegarde** de la boîte de dialogue **Sauvegarder la base de données** pour afficher ou modifier les options de sauvegarde de la base de données.</span><span class="sxs-lookup"><span data-stu-id="ef272-103">Use the  **Backup Options** page of the **Back Up Database** dialog box to view or modify database backup options.</span></span>  
  
 <span data-ttu-id="ef272-104">**Pour créer une sauvegarde à l'aide de SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="ef272-104">**To create a backup by using SQL Server Management Studio**</span></span>  
  
-   [<span data-ttu-id="ef272-105">Créer une sauvegarde complète de base de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ef272-105">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](create-a-full-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="ef272-106">Créer une sauvegarde différentielle de base de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ef272-106">Create a Differential Database Backup &#40;SQL Server&#41;</span></span>](create-a-differential-database-backup-sql-server.md)  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ef272-107">Vous pouvez définir un plan de maintenance de base de données pour créer des sauvegardes de base de données.</span><span class="sxs-lookup"><span data-stu-id="ef272-107">You can define a database maintenance plan to create database backups.</span></span> <span data-ttu-id="ef272-108">Pour plus d’informations, consultez [Plans de maintenance](../maintenance-plans/maintenance-plans.md) et [Utiliser l’Assistant Plan de maintenance](../maintenance-plans/use-the-maintenance-plan-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="ef272-108">For more information, see [Maintenance Plans](../maintenance-plans/maintenance-plans.md) and [Use the Maintenance Plan Wizard](../maintenance-plans/use-the-maintenance-plan-wizard.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ef272-109">Quand vous spécifiez une tâche de sauvegarde à l’aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], vous pouvez générer le script [!INCLUDE[tsql](../../includes/tsql-md.md)][BACKUP](/sql/t-sql/statements/backup-transact-sql) correspondant en cliquant sur le bouton **Script** et en sélectionnant une destination pour le script.</span><span class="sxs-lookup"><span data-stu-id="ef272-109">When you specify a backup task by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], you can generate the corresponding [!INCLUDE[tsql](../../includes/tsql-md.md)][BACKUP](/sql/t-sql/statements/backup-transact-sql) script by clicking the **Script** button and then selecting a destination for the script.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ef272-110">Options</span><span class="sxs-lookup"><span data-stu-id="ef272-110">Options</span></span>  
  
### <a name="backup-set"></a><span data-ttu-id="ef272-111">Jeu de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="ef272-111">Backup set</span></span>  
 <span data-ttu-id="ef272-112">Les options du volet **Jeu de sauvegarde** vous permettent de spécifier des informations facultatives concernant le jeu de sauvegarde créé par l'opération de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="ef272-112">The options of the **Backup set** panel allow for you to specify optional information about the backup set created by the back up operation.</span></span>  
  
 <span data-ttu-id="ef272-113">**Nom**</span><span class="sxs-lookup"><span data-stu-id="ef272-113">**Name**</span></span>  
 <span data-ttu-id="ef272-114">Spécifiez le nom du jeu de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="ef272-114">Specify the backup set name.</span></span> <span data-ttu-id="ef272-115">Le système suggère automatiquement un nom par défaut en fonction du nom de la base de données et du type de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="ef272-115">The system automatically suggests a default name based on the database name and the backup type.</span></span>  
  
 <span data-ttu-id="ef272-116">Pour plus d’informations sur les jeux de sauvegarde, consultez [Jeux de supports, familles de supports et jeux de sauvegarde &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ef272-116">For information about backup sets, see [Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span></span>  
  
 <span data-ttu-id="ef272-117">**Description**</span><span class="sxs-lookup"><span data-stu-id="ef272-117">**Description**</span></span>  
 <span data-ttu-id="ef272-118">Entrez une description du jeu de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="ef272-118">Enter a description of the backup set.</span></span>  
  
 <span data-ttu-id="ef272-119">**Expiration du jeu de sauvegarde**</span><span class="sxs-lookup"><span data-stu-id="ef272-119">**Backup set will expire**</span></span>  
 <span data-ttu-id="ef272-120">Choisissez une des options d'expiration ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="ef272-120">Choose one of the following expiration options.</span></span> <span data-ttu-id="ef272-121">Cette option est désactivée si **URL** est choisie en tant que destination de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="ef272-121">This option is disabled if **URL** is chosen as the backup destination.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ef272-122">**Après**</span><span class="sxs-lookup"><span data-stu-id="ef272-122">**After**</span></span>|<span data-ttu-id="ef272-123">Spécifiez le nombre de jours qui doivent s'écouler avant que le jeu de sauvegarde expire et puisse être écrasé.</span><span class="sxs-lookup"><span data-stu-id="ef272-123">Specify the number of days that must elapse before this backup set expires and can be overwritten.</span></span> <span data-ttu-id="ef272-124">Cette valeur doit être comprise entre 0 et 99999 jours ; une valeur de 0 jour signifie que le jeu de sauvegarde n'expirera jamais.</span><span class="sxs-lookup"><span data-stu-id="ef272-124">This value can be from 0 to 99999 days; a value of 0 days means that the backup set will never expire.</span></span><br /><br /> <span data-ttu-id="ef272-125">La valeur par défaut d’expiration de sauvegarde correspond à la valeur définie dans l’option **Délai de rétention par défaut du support de sauvegarde (jours)** .</span><span class="sxs-lookup"><span data-stu-id="ef272-125">The default value for backup expiration is the value set in the **Default backup media retention (in days)** option.</span></span> <span data-ttu-id="ef272-126">Pour accéder à cette option, cliquez avec le bouton droit sur le nom du serveur dans l’Explorateur d’objets et cliquez sur **Propriétés**; ensuite, cliquez sur la page **Paramètres de base de données** de la boîte de dialogue **Propriétés du serveur** .</span><span class="sxs-lookup"><span data-stu-id="ef272-126">To access this, right-click the server name in Object Explorer and select **Properties**; then click the **Database Settings** page of the **Server Properties** dialog box.</span></span>|  
|<span data-ttu-id="ef272-127">**Actif**</span><span class="sxs-lookup"><span data-stu-id="ef272-127">**On**</span></span>|<span data-ttu-id="ef272-128">Spécifiez une date spécifique à laquelle le jeu de sauvegarde expire et peut être écrasé.</span><span class="sxs-lookup"><span data-stu-id="ef272-128">Specify a specific date when the backup set expires and can be overwritten.</span></span>|  
  
### <a name="compression"></a><span data-ttu-id="ef272-129">Compression</span><span class="sxs-lookup"><span data-stu-id="ef272-129">Compression</span></span>  
 [!INCLUDE[ssEnterpriseEd10](../../../includes/ssenterpriseed10-md.md)] <span data-ttu-id="ef272-130">(ou une version ultérieure) prend en charge la [compression de sauvegarde](backup-compression-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ef272-130">(or a later version) supports [backup compression](backup-compression-sql-server.md).</span></span>  
  
 <span data-ttu-id="ef272-131">**Définir la compression de la sauvegarde**</span><span class="sxs-lookup"><span data-stu-id="ef272-131">**Set backup compression**</span></span>  
 <span data-ttu-id="ef272-132">Dans [!INCLUDE[ssEnterpriseEd10](../../../includes/ssenterpriseed10-md.md)] (ou version ultérieure), sélectionnez l'une des valeurs de compression de la sauvegarde suivantes :</span><span class="sxs-lookup"><span data-stu-id="ef272-132">In [!INCLUDE[ssEnterpriseEd10](../../../includes/ssenterpriseed10-md.md)] (or a later version), select one of the following backup compression values:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ef272-133">**Utiliser le paramètre du serveur par défaut**</span><span class="sxs-lookup"><span data-stu-id="ef272-133">**Use the default server setting**</span></span>|<span data-ttu-id="ef272-134">Cliquez sur cette option pour utiliser la valeur par défaut au niveau du serveur.</span><span class="sxs-lookup"><span data-stu-id="ef272-134">Click to use the server-level default.</span></span><br /><br /> <span data-ttu-id="ef272-135">Cette valeur par défaut est définie par l’option de configuration de serveur **Compression par défaut des sauvegardes** .</span><span class="sxs-lookup"><span data-stu-id="ef272-135">This default is set by the **backup compression default** server-configuration option.</span></span> <span data-ttu-id="ef272-136">Pour plus d’informations sur l’affichage du paramétrage actuel de cette option, consultez [Afficher ou configurer l’option de configuration du serveur valeur par défaut de compression de la sauvegarde](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="ef272-136">For information about how to view the current setting of this option, see [View or Configure the backup compression default Server Configuration Option](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md).</span></span>|  
|<span data-ttu-id="ef272-137">**Compresser la sauvegarde**</span><span class="sxs-lookup"><span data-stu-id="ef272-137">**Compress backup**</span></span>|<span data-ttu-id="ef272-138">Cliquez sur cette option pour compresser la sauvegarde, indépendamment de la valeur par défaut au niveau du serveur.</span><span class="sxs-lookup"><span data-stu-id="ef272-138">Click to compress the backup, regardless of the server-level default.</span></span><br /><br /> <span data-ttu-id="ef272-139">**\*\* Important \*\*** Par défaut, la compression augmente considérablement l’utilisation de l’UC et l’UC supplémentaire consommée par le processus de compression peut avoir un impact néfaste sur les opérations simultanées.</span><span class="sxs-lookup"><span data-stu-id="ef272-139">**\*\* Important \*\*** By default, compression significantly increases CPU usage, and the additional CPU consumed by the compression process might adversely impact concurrent operations.</span></span> <span data-ttu-id="ef272-140">Par conséquent, il peut être préférable de créer une sauvegarde compressée de priorité basse dans une session où l’utilisation de l’UC est limitée par [Resource Governor](../resource-governor/resource-governor.md).</span><span class="sxs-lookup"><span data-stu-id="ef272-140">Therefore, you might want to create low-priority compressed backups in a session whose CPU usage is limited by [Resource Governor](../resource-governor/resource-governor.md).</span></span> <span data-ttu-id="ef272-141">Pour plus d'informations, consultez [Utiliser Resource Governor pour limiter l’utilisation de l’UC par compression de la sauvegarde &#40;Transact-SQL&#41;](use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="ef272-141">For more information, see [Use Resource Governor to Limit CPU Usage by Backup Compression &#40;Transact-SQL&#41;](use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md).</span></span>|  
|<span data-ttu-id="ef272-142">**Ne pas compresser la sauvegarde**</span><span class="sxs-lookup"><span data-stu-id="ef272-142">**Do not compress backup**</span></span>|<span data-ttu-id="ef272-143">Cliquez sur cette option pour créer une sauvegarde non compressée, indépendamment de la valeur par défaut au niveau du serveur.</span><span class="sxs-lookup"><span data-stu-id="ef272-143">Click to create an uncompressed backup, regardless of the server-level default.</span></span>|  
  
### <a name="encryption"></a><span data-ttu-id="ef272-144">Chiffrement</span><span class="sxs-lookup"><span data-stu-id="ef272-144">Encryption</span></span>  
 <span data-ttu-id="ef272-145">Pour créer une sauvegarde chiffrée, activez la case à cocher **Chiffrer le fichier de sauvegarde** .</span><span class="sxs-lookup"><span data-stu-id="ef272-145">To create an encrypted backup, check the **Encrypt backup** check box.</span></span> <span data-ttu-id="ef272-146">Sélectionnez l'algorithme de chiffrement à utiliser pour l'étape de chiffrement et fournissez un certificat ou une clé asymétrique dans la liste des certificats ou clés numériques existants.</span><span class="sxs-lookup"><span data-stu-id="ef272-146">Select an encryption algorithm to use for the encryption step, and provide a Certificate or Asymmetric key from a list of existing certificates or asymmetric keys.</span></span> <span data-ttu-id="ef272-147">Les algorithmes disponibles pour le chiffrement sont :</span><span class="sxs-lookup"><span data-stu-id="ef272-147">The available algorithms for encryption are:</span></span>  
  
-   <span data-ttu-id="ef272-148">AES 128</span><span class="sxs-lookup"><span data-stu-id="ef272-148">AES 128</span></span>  
  
-   <span data-ttu-id="ef272-149">AES 192</span><span class="sxs-lookup"><span data-stu-id="ef272-149">AES 192</span></span>  
  
-   <span data-ttu-id="ef272-150">AES 256</span><span class="sxs-lookup"><span data-stu-id="ef272-150">AES 256</span></span>  
  
-   <span data-ttu-id="ef272-151">Triple DES</span><span class="sxs-lookup"><span data-stu-id="ef272-151">Triple DES</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="ef272-152">L'option de chiffrement est désactivée si vous avez choisi d'ajouter la sauvegarde à un jeu de sauvegarde existant.</span><span class="sxs-lookup"><span data-stu-id="ef272-152">The encryption option is disabled if you selected to append to existing backup set.</span></span>  
>   
>  <span data-ttu-id="ef272-153">Il s'agit de la méthode conseillée pour sauvegarder votre certificat ou vos clés et les stocker dans un emplacement différent de celui de la sauvegarde chiffrée.</span><span class="sxs-lookup"><span data-stu-id="ef272-153">It is recommended practice to back up your certificate or keys and store them in a different location than the backup you encrypted.</span></span>  
>   
>  <span data-ttu-id="ef272-154">Seules les clés résidant dans la gestion de clés extensible (EKM) sont prises en charge.</span><span class="sxs-lookup"><span data-stu-id="ef272-154">Only keys residing in the Extensible Key Management (EKM) are supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef272-155"> Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ef272-155">See Also</span></span>  
 <span data-ttu-id="ef272-156">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ef272-156">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="ef272-157">[Sauvegarder un journal des transactions &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ef272-157">[Back Up a Transaction Log &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span></span>  
 <span data-ttu-id="ef272-158">[Sauvegarder des fichiers et des groupes de fichiers &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ef272-158">[Back Up Files and Filegroups &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span></span>  
 [<span data-ttu-id="ef272-159">Sauvegarder le journal des transactions lorsque la base de données est endommagée &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ef272-159">Back Up the Transaction Log When the Database Is Damaged &#40;SQL Server&#41;</span></span>](back-up-the-transaction-log-when-the-database-is-damaged-sql-server.md)  
  
  
