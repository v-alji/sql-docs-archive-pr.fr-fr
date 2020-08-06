---
title: Abonnés de réplication sur des tables optimisées en mémoire | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
ms.assetid: 1a8e6bc7-433e-471d-b646-092dc80a2d1a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: df61b83d2f6d07cbbd21773b8940dd4e5341f76b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600772"
---
# <a name="replication-to-memory-optimized-table-subscribers"></a><span data-ttu-id="19e7e-102">Abonnés de réplication sur des tables optimisées en mémoire</span><span class="sxs-lookup"><span data-stu-id="19e7e-102">Replication to Memory-Optimized Table Subscribers</span></span>
  <span data-ttu-id="19e7e-103">Les tables agissant comme des abonnés de réplication transactionnelle, à l'exclusion de la réplication transactionnelle d'égal à égal, peuvent être configurées en tant que tables mémoire optimisées.</span><span class="sxs-lookup"><span data-stu-id="19e7e-103">Tables acting as transactional replication subscribers, excluding Peer-to-peer transactional replication, can be configured as memory-optimized tables.</span></span> <span data-ttu-id="19e7e-104">Les autres configurations de réplication ne sont pas compatibles avec les tables mémoire optimisées.</span><span class="sxs-lookup"><span data-stu-id="19e7e-104">Other replication configurations are not compatible with memory-optimized tables.</span></span>  
  
## <a name="configuring-a-memory-optimized-table-as-a-subscriber"></a><span data-ttu-id="19e7e-105">Configuration d'une table mémoire optimisée en tant qu'abonné</span><span class="sxs-lookup"><span data-stu-id="19e7e-105">Configuring a memory-optimized table as a subscriber</span></span>  
 <span data-ttu-id="19e7e-106">Pour configurer une table mémoire optimisée en tant qu'abonné, effectuez les étapes suivantes.</span><span class="sxs-lookup"><span data-stu-id="19e7e-106">To configure a memory-optimized table as a subscriber, perform the following steps.</span></span>  
  
 <span data-ttu-id="19e7e-107">**Créer et activer une publication**</span><span class="sxs-lookup"><span data-stu-id="19e7e-107">**Create and Enable Publication**</span></span>  
  
1.  <span data-ttu-id="19e7e-108">Créer une publication</span><span class="sxs-lookup"><span data-stu-id="19e7e-108">Create a publication.</span></span>  
  
2.  <span data-ttu-id="19e7e-109">Ajoutez des articles à la publication.</span><span class="sxs-lookup"><span data-stu-id="19e7e-109">Add articles to the publication.</span></span> <span data-ttu-id="19e7e-110">Pour le paramètre `@upd_cmd`, utilisez la convention SCALL ou SQL.</span><span class="sxs-lookup"><span data-stu-id="19e7e-110">For the `@upd_cmd` parameter, use the SCALL or SQL convention.</span></span>  
  
    ```  
    EXEC sp_addarticle  
        @publication = N'Publication1',  
        @article = N'Mem_Table',  
        @source_owner = N'dbo',  
        @source_object = N'Mem_Table',  
        @type = N'logbased',  
        @description = null,  
        @creation_script = null,  
        @pre_creation_cmd = N'none',  
        @schema_option = 0x00000000080050DF,  
        @identityrangemanagementoption = N'manual',  
        @destination_table = N'Mem_Table',  
        @destination_owner = N'dbo',  
        @vertical_partition = N'false',  
        @ins_cmd = N'CALL sp_MSins_Mem_Table',  
        @del_cmd = N'CALL sp_MSdel_Mem_Table',  
        @upd_cmd = N'SCALL sp_MSupd_Mem_Table';  
    GO  
    ```  
  
 <span data-ttu-id="19e7e-111">**Générer un instantané et régler le schéma**</span><span class="sxs-lookup"><span data-stu-id="19e7e-111">**Generate a Snapshot and Adjust the Schema**</span></span>  
  
1.  <span data-ttu-id="19e7e-112">Créez un travail instantané et générez un instantané.</span><span class="sxs-lookup"><span data-stu-id="19e7e-112">Create a snapshot job and generate a snapshot.</span></span>  
  
    ```  
    EXEC sp_addpublication_snapshot @publication = N'Publication1', @frequency_type = 1;  
    EXEC sp_startpublication_snapshot @publication = N'Publication1';  
    ```  
  
2.  <span data-ttu-id="19e7e-113">Naviguez jusqu'au dossier d'instantané.</span><span class="sxs-lookup"><span data-stu-id="19e7e-113">Navigate to the snapshot folder.</span></span> <span data-ttu-id="19e7e-114">L’emplacement par défaut est «C:\Program Files\Microsoft SQL Server\MSSQL12. \<INSTANCE> \MSSQL\repldata\unc\XXX\YYYYMMDDHHMMSS \\ ».</span><span class="sxs-lookup"><span data-stu-id="19e7e-114">The default location is "C:\Program Files\Microsoft SQL Server\MSSQL12.\<INSTANCE>\MSSQL\repldata\unc\XXX\YYYYMMDDHHMMSS\\".</span></span>  
  
3.  <span data-ttu-id="19e7e-115">Recherchez **. Fichier SCH** pour votre table et ouvrez-le dans Management Studio.</span><span class="sxs-lookup"><span data-stu-id="19e7e-115">Locate the **.SCH** file for your table and open it in Management Studio.</span></span> <span data-ttu-id="19e7e-116">Modifiez le schéma de la table et mettez à jour la procédure stockée comme décrit ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="19e7e-116">Change the table schema and update the stored procedure as described below.</span></span>  
  
     <span data-ttu-id="19e7e-117">Évaluez les index définis dans le fichier IDX.</span><span class="sxs-lookup"><span data-stu-id="19e7e-117">Evaluate the indexes defined in the IDX file.</span></span> <span data-ttu-id="19e7e-118">Modifiez `CREATE TABLE` pour spécifier les index, les contraintes, la clé primaire et la syntaxe mémoire optimisée requis.</span><span class="sxs-lookup"><span data-stu-id="19e7e-118">Modify `CREATE TABLE` to specify the required indexes, constraints, primary key, and memory-optimized syntax.</span></span> <span data-ttu-id="19e7e-119">Pour les tables mémoire optimisées, les colonnes d'index doivent être NOT NULL et les colonnes d'index des types de caractères doivent être Unicode et utiliser le classement BIN2.</span><span class="sxs-lookup"><span data-stu-id="19e7e-119">For memory-optimized tables, index columns should be NOT NULL and index columns of character types must be Unicode and use BIN2 collation.</span></span> <span data-ttu-id="19e7e-120">Voir l'exemple ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="19e7e-120">See example below:</span></span>  
  
    ```  
    SET ANSI_PADDING ON;  
    GO  
  
    SET ANSI_NULLS ON;  
    GO  
  
    SET QUOTED_IDENTIFIER ON;  
    GO  
  
    CREATE TABLE [dbo].[Mem_Table]([c1] [int] NOT NULL,  
        [c2] [float] NOT NULL,  
        [c3] [decimal](10, 2) NOT NULL,  
        [c4] [nvarchar](5) COLLATE SQL_Latin1_General_CP850_BIN2 NOT NULL,  
        INDEX [hash_index_sample_memoryoptimizedtable_c2] HASH (c2) WITH (BUCKET_COUNT = 1024),  
        INDEX [index_sample_memoryoptimizedtable_c3] NONCLUSTERED ([c3]),  
        INDEX [nvarchar_index_sample_memoryoptimizedtable_c4] ([c4]),  
        CONSTRAINT [PK_sample_memoryoptimizedtable] PRIMARY KEY NONCLUSTERED ([c1])) WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA);  
    GO  
    ```  
  
4.  <span data-ttu-id="19e7e-121">En cas d'utilisation de la convention SCALL pour le paramètre `@upd_cmd`, accédez au fichier de schéma (.SCH) et modifiez l'instruction de mise à jour de table dans `create procedure [sp_MSupd_<SCHEMA><TABLE_NAME>]` pour supprimer les colonnes de clé primaire.</span><span class="sxs-lookup"><span data-stu-id="19e7e-121">When using SCALL convention for the `@upd_cmd` parameter, go to the schema (.SCH) file and change the table update statement in `create procedure [sp_MSupd_<SCHEMA><TABLE_NAME>]` to remove primary key columns.</span></span>  
  
     <span data-ttu-id="19e7e-122">Pour prendre en charge les mises à jour de clé primaire, utilisez une procédure stockée de mise à jour personnalisée pour remplacer l'instruction de mise à jour de clé primaire, comme suit :</span><span class="sxs-lookup"><span data-stu-id="19e7e-122">To support primary key updates, use a custom update stored procedure to replace the primary key update statement, as follows:</span></span>  
  
    1.  <span data-ttu-id="19e7e-123">Sélectionnez les valeurs de colonne manquantes (SCALL fournit uniquement la colonne impliquée dans l'opération de mise à jour).</span><span class="sxs-lookup"><span data-stu-id="19e7e-123">Select missing column values (SCALL only provides the column involved into the update operation).</span></span>  
  
    2.  <span data-ttu-id="19e7e-124">Supprimez l'enregistrement existant.</span><span class="sxs-lookup"><span data-stu-id="19e7e-124">Delete the existing record.</span></span>  
  
    3.  <span data-ttu-id="19e7e-125">Insérez un nouvel enregistrement avec les nouvelles valeurs fournies comprenant la nouvelle clé primaire.</span><span class="sxs-lookup"><span data-stu-id="19e7e-125">Insert a new record with new values provided including the new primary key.</span></span>  
  
     <span data-ttu-id="19e7e-126">La procédure de mise à jour d'origine est la suivante :</span><span class="sxs-lookup"><span data-stu-id="19e7e-126">The original update procedure looks like this:</span></span>  
  
    ```  
    create procedure [sp_MSupd_Mem_Table]  
                   @c1 int = NULL,  
                   @c2 float = NULL,  
                   @c3 decimal(10,2) = NULL,  
                   @c4 nvarchar(5) = NULL,  
                   @pkc1 int = NULL,  
                   @bitmap binary(1)  
    as  
    begin    
    if (substring(@bitmap,1,1) & 1 = 1)  
    begin   
    update [dbo].[Mem_Table] set  
                   [c1] = case substring(@bitmap,1,1) & 1 when 1 then @c1 else [c1] end,  
                   [c2] = case substring(@bitmap,1,1) & 2 when 2 then @c2 else [c2] end,  
                   [c3] = case substring(@bitmap,1,1) & 4 when 4 then @c3 else [c3] end,  
                   [c4] = case substring(@bitmap,1,1) & 8 when 8 then @c4 else [c4] end  
    where [c1] = @pkc1  
    if @@rowcount = 0  
        if @@microsoftversion>0x07320000  
            exec sp_MSreplraiserror 20598  
    end    
    else  
    begin   
    update [dbo].[Mem_Table] set  
                   [c2] = case substring(@bitmap,1,1) & 2 when 2 then @c2 else [c2] end,  
                   [c3] = case substring(@bitmap,1,1) & 4 when 4 then @c3 else [c3] end,  
                   [c4] = case substring(@bitmap,1,1) & 8 when 8 then @c4 else [c4] end  
    where [c1] = @pkc1  
    if @@rowcount = 0  
        if @@microsoftversion>0x07320000  
            exec sp_MSreplraiserror 20598  
    end   
    end   
    go  
    ```  
  
     <span data-ttu-id="19e7e-127">Si la clé primaire ne doit jamais être mise à jour sur un serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="19e7e-127">If the primary key should never be updated on a publisher.</span></span> <span data-ttu-id="19e7e-128">Commenter la mise à jour de ces colonnes dans la procédure de mise à jour comme suit :</span><span class="sxs-lookup"><span data-stu-id="19e7e-128">Comment out the update to such columns in the update procedure as follows:</span></span>  
  
    ```  
    create procedure [sp_MSupd_Mem_Table]  
                   @c1 int = NULL,  
                   @c2 float = NULL,  
                   @c3 decimal(10,2) = NULL,  
                   @c4 nvarchar(5) = NULL,  
                   @pkc1 int = NULL,  
                   @bitmap binary(1)  
    as  
    begin    
    if (substring(@bitmap,1,1) & 1 = 1)  
    begin   
    update [dbo].[Mem_Table] set  
    --             [c1] = case substring(@bitmap,1,1) & 1 when 1 then @c1 else [c1] end,  
                   [c2] = case substring(@bitmap,1,1) & 2 when 2 then @c2 else [c2] end,  
                   [c3] = case substring(@bitmap,1,1) & 4 when 4 then @c3 else [c3] end,  
                   [c4] = case substring(@bitmap,1,1) & 8 when 8 then @c4 else [c4] end  
    where [c1] = @pkc1  
    if @@rowcount = 0  
        if @@microsoftversion>0x07320000  
            exec sp_MSreplraiserror 20598  
    end    
    else  
    begin   
    update [dbo].[Mem_Table] set  
                   [c2] = case substring(@bitmap,1,1) & 2 when 2 then @c2 else [c2] end,  
                   [c3] = case substring(@bitmap,1,1) & 4 when 4 then @c3 else [c3] end,  
                   [c4] = case substring(@bitmap,1,1) & 8 when 8 then @c4 else [c4] end  
    where [c1] = @pkc1  
    if @@rowcount = 0  
        if @@microsoftversion>0x07320000  
            exec sp_MSreplraiserror 20598  
    end   
    end   
    go  
    ```  
  
     <span data-ttu-id="19e7e-129">Pour permettre la prise en charge des mises à jour dans la clé primaire, modifiez la procédure de mise à jour comme suit :</span><span class="sxs-lookup"><span data-stu-id="19e7e-129">To allow the support of updates to the primary key, modify the update procedure to read as follows</span></span>  
  
    ```  
    create procedure [sp_MSupd_Mem_Table]  
                   @c1 int = NULL,  
                   @c2 float = NULL,  
                   @c3 decimal(10,2) = NULL,  
                   @c4 nvarchar(5) = NULL,  
                    @pkc1 int = NULL,  
                   @bitmap binary(1)  
    as  
    begin    
    if (substring(@bitmap,1,1) & 1 = 1)  
    begin   
    select  
                   @c1 = case substring(@bitmap,1,1) & 1 when 1 then @c1 else [c1] end,  
                   @c2 = case substring(@bitmap,1,1) & 2 when 2 then @c2 else [c2] end,  
                   @c3 = case substring(@bitmap,1,1) & 4 when 4 then @c3 else [c3] end,  
                   @c4 = case substring(@bitmap,1,1) & 8 when 8 then @c4 else [c4] end  
    from [dbo].[Mem_Table] where [c1] = @pkc1  
    if @@rowcount <> 0 begin  
            delete [dbo].[Mem_Table] where [c1] = @pkc1  
            if @@rowcount <> 0  
                   insert into [dbo].[Mem_Table]([c1],  
                           [c2],  
                           [c3],  
                           [c4]) values (  
                           @c1,  
                           @c2,  
                           @c3,  
                           @c4  
                   )   
    end  
    if @@rowcount = 0  
        if @@microsoftversion>0x07320000  
            exec sp_MSreplraiserror 20598  
    end    
    else  
    begin   
    update [dbo].[Mem_Table] set  
                   [c2] = case substring(@bitmap,1,1) & 2 when 2 then @c2 else [c2] end,  
                   [c3] = case substring(@bitmap,1,1) & 4 when 4 then @c3 else [c3] end,  
                   [c4] = case substring(@bitmap,1,1) & 8 when 8 then @c4 else [c4] end  
    where [c1] = @pkc1  
    if @@rowcount = 0  
        if @@microsoftversion>0x07320000  
            exec sp_MSreplraiserror 20598  
    end   
    end   
    go  
    ```  
  
5.  <span data-ttu-id="19e7e-130">Créez la base de données de l’abonné à l’aide de l’option **d’isolation élever à la capture instantanée** et définissez le classement par défaut sur Latin1_General_CS_AS_KS_WS en cas d’utilisation de types de données caractères non Unicode.</span><span class="sxs-lookup"><span data-stu-id="19e7e-130">Create subscriber database using the **elevate to snapshot isolation** option and set the default collation to Latin1_General_CS_AS_KS_WS in case of using non Unicode character data types.</span></span>  
  
    ```  
    CREATE DATABASE [Sub]   
    CONTAINMENT = NONE   
    ON PRIMARY ( NAME = [Sub], FILENAME = [C:\Program Files\Microsoft SQL Server\MSSQL12\MSSQL\DATA\Sub.mdf]),   
    FILEGROUP [mem] CONTAINS MEMORY_OPTIMIZED_DATA ( NAME = [mem],   
    FILENAME = [C:\Program Files\Microsoft SQL Server\MSSQL12\MSSQL\DATA\Sub])  
    LOG ON ( NAME = [Sub_log], FILENAME = [C:\Program Files\Microsoft SQL Server\MSSQL12\MSSQL\DATA\Sub.ldf])  
    COLLATE Latin1_General_CS_AS_KS_WS;  
  
    ALTER DATABASE [Sub] SET MEMORY_OPTIMIZED_ELEVATE_TO_SNAPSHOT = ON;  
    GO  
    ```  
  
6.  <span data-ttu-id="19e7e-131">Appliquez le schéma à la base de données d’un abonné et enregistrez le schéma pour une utilisation ultérieure.</span><span class="sxs-lookup"><span data-stu-id="19e7e-131">Apply the schema to a subscriber's database and save the schema for future use.</span></span>  
  
7.  <span data-ttu-id="19e7e-132">Chargez les données du serveur de publication (source) sur l'abonné.</span><span class="sxs-lookup"><span data-stu-id="19e7e-132">Load the publisher (source) data to the subscriber.</span></span> <span data-ttu-id="19e7e-133">Les données ne doivent pas changer sur le serveur de publication jusqu'à ce que vous ajoutiez un abonnement.</span><span class="sxs-lookup"><span data-stu-id="19e7e-133">Data should not change at the publisher until you add a subscription.</span></span>  <span data-ttu-id="19e7e-134">Utilisez BCP comme indiqué ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="19e7e-134">You can use BCP as shown below:</span></span>  
  
    ```  
    bcp Pub.dbo.Mem_Table out Mem_Table.bcp -S. -T -C1252 -n  
    bcp Sub.dbo.Mem_Table in Mem_Table.bcp -S. -T -C1252 -n  
    ```  
  
8.  <span data-ttu-id="19e7e-135">Reconfigurez l'article pour désactiver les modifications de schéma sur l'abonné :</span><span class="sxs-lookup"><span data-stu-id="19e7e-135">Reconfigure the article to disable schema changes on the subscriber:</span></span>  
  
    ```  
    EXEC sp_changearticle  
        @publication = N'Publication1',  
        @article = N'Mem_Table',  
        @property = N'schema_option',  
        @value = 0,  
        @force_invalidate_snapshot = 1,  
        @force_reinit_subscription = 1;  
    GO  
    ```  
  
 <span data-ttu-id="19e7e-136">**Ajouter un abonnement sans synchronisation**</span><span class="sxs-lookup"><span data-stu-id="19e7e-136">**Add no sync Subscription**</span></span>  
  
 <span data-ttu-id="19e7e-137">Ajoutez un abonnement nosync.</span><span class="sxs-lookup"><span data-stu-id="19e7e-137">Add a nosync subscription.</span></span>  
  
```  
EXEC sp_addsubscription  
    @publication = N' Publication1',  
    @subscriber = @@ServerName,  
    @destination_db = N'Sub',  
    @subscription_type = N'Push',  
    @sync_type = N'replication support only',  
    @article = N'all',  
    @update_mode = N'read only',  
    @subscriber_type = 0;  
GO  
```  
  
 <span data-ttu-id="19e7e-138">Les tables mémoire optimisées doivent maintenant commencer à recevoir les mises à jour du serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="19e7e-138">Memory-optimized tables should now start receiving updates from the publisher.</span></span>  
  
## <a name="restrictions"></a><span data-ttu-id="19e7e-139">Restrictions</span><span class="sxs-lookup"><span data-stu-id="19e7e-139">Restrictions</span></span>  
 <span data-ttu-id="19e7e-140">Seule la réplication transactionnelle monodirectionnelle est prise en charge.</span><span class="sxs-lookup"><span data-stu-id="19e7e-140">Only one-way transactional replication is supported.</span></span> <span data-ttu-id="19e7e-141">La réplication transactionnelle d'égal à égal n'est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="19e7e-141">Peer-to-peer transactional replication is not supported.</span></span>  
  
 <span data-ttu-id="19e7e-142">Les tables mémoire optimisées ne peuvent pas être publiées.</span><span class="sxs-lookup"><span data-stu-id="19e7e-142">Memory-optimized tables cannot be published.</span></span>  
  
 <span data-ttu-id="19e7e-143">Les tables de réplication sur le serveur de distribution ne peuvent pas être configurées comme des tables mémoire optimisées.</span><span class="sxs-lookup"><span data-stu-id="19e7e-143">Replication tables on the distributor cannot be configured as memory-optimized tables.</span></span>  
  
 <span data-ttu-id="19e7e-144">La réplication de fusion ne peut pas inclure des tables mémoire optimisées.</span><span class="sxs-lookup"><span data-stu-id="19e7e-144">Merge replication cannot include memory-optimized tables.</span></span>  
  
 <span data-ttu-id="19e7e-145">Sur l'abonné, les tables impliquées dans la réplication transactionnelle peuvent être configurées en tant que tables mémoire optimisées, mais les tables d'abonné doivent répondre aux exigences des tables mémoire optimisées.</span><span class="sxs-lookup"><span data-stu-id="19e7e-145">At the subscriber, tables involved in transactional replication can be configured as memory optimized tables, but the subscriber tables must meet the requirements of memory-optimized tables.</span></span> <span data-ttu-id="19e7e-146">Cette fonction requiert les restrictions suivantes.</span><span class="sxs-lookup"><span data-stu-id="19e7e-146">This requires the following restrictions.</span></span>  
  
-   <span data-ttu-id="19e7e-147">Pour créer une table mémoire optimisée sur un abonné de réplication transactionnelle, les fichiers de schéma d'instantané utilisés pour créer les tables mémoire optimisées doivent être modifiés manuellement.</span><span class="sxs-lookup"><span data-stu-id="19e7e-147">To create a memory-optimized table on a transactional replication subscriber, the snapshot schema files used to create the memory-optimized tables must be manually modified.</span></span> <span data-ttu-id="19e7e-148">Pour plus d’informations, consultez [modification d’un fichier de schéma](#Schema).</span><span class="sxs-lookup"><span data-stu-id="19e7e-148">For more information, see [Modifying a schema file](#Schema).</span></span>  
  
-   <span data-ttu-id="19e7e-149">Les tables répliquées en tables mémoire optimisées sur un abonné appliquent la limite de 8060 octets par ligne des tables mémoire optimisées.</span><span class="sxs-lookup"><span data-stu-id="19e7e-149">Tables replicated to memory-optimized tables on a subscriber are limited to the 8060 bytes per row limit of memory-optimized tables.</span></span>  
  
-   <span data-ttu-id="19e7e-150">Les tables répliquées en tables mémoire optimisées sur un abonné sont limitées aux types de données autorisés dans les tables mémoire optimisées.</span><span class="sxs-lookup"><span data-stu-id="19e7e-150">Tables replicated to memory-optimized tables on a subscriber are limited to the data types permitted in memory-optimized tables.</span></span> <span data-ttu-id="19e7e-151">Pour plus d’informations, consultez [types de données pris en charge](../in-memory-oltp/supported-data-types-for-in-memory-oltp.md).</span><span class="sxs-lookup"><span data-stu-id="19e7e-151">For more information, see [Supported Data Types](../in-memory-oltp/supported-data-types-for-in-memory-oltp.md).</span></span>  
  
-   <span data-ttu-id="19e7e-152">Il existe des restrictions pour la mise à jour de la clé primaire des tables répliquées en une table mémoire optimisée sur un abonné.</span><span class="sxs-lookup"><span data-stu-id="19e7e-152">There are restrictions on updating the primary key of tables being replicated to a memory-optimized table on a subscriber.</span></span> <span data-ttu-id="19e7e-153">Pour plus d’informations, consultez [réplication des modifications apportées à une clé primaire](#PrimaryKey).</span><span class="sxs-lookup"><span data-stu-id="19e7e-153">For more information, see [Replicating changes to a primary key](#PrimaryKey).</span></span>  
  
-   <span data-ttu-id="19e7e-154">La clé étrangère, la contrainte unique, les déclencheurs, les modifications de schéma, ROWGUIDCOL, les colonnes calculées, la compression de données, les types de données d'alias, le contrôle de version et les verrous ne sont pas pris en charge dans les tables mémoire optimisées.</span><span class="sxs-lookup"><span data-stu-id="19e7e-154">Foreign key, unique constraint, triggers, schema modifications, ROWGUIDCOL, computed columns, data compression, alias data types, versioning, and locks are not supported in memory-optimized tables.</span></span> <span data-ttu-id="19e7e-155">Pour plus d'informations, consultez [Transact-SQL Constructs Not Supported by In-Memory OLTP](../in-memory-oltp/transact-sql-constructs-not-supported-by-in-memory-oltp.md) .</span><span class="sxs-lookup"><span data-stu-id="19e7e-155">See [Transact-SQL Constructs Not Supported by In-Memory OLTP](../in-memory-oltp/transact-sql-constructs-not-supported-by-in-memory-oltp.md) for information.</span></span>  
  
##  <a name="modifying-a-schema-file"></a><a name="Schema"></a><span data-ttu-id="19e7e-156">Modification d’un fichier de schéma</span><span class="sxs-lookup"><span data-stu-id="19e7e-156">Modifying a schema file</span></span>  
  
-   <span data-ttu-id="19e7e-157">Les index cluster ne sont pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="19e7e-157">Clustered indexes are not supported.</span></span> <span data-ttu-id="19e7e-158">Modifiez les index cluster en index non-cluster.</span><span class="sxs-lookup"><span data-stu-id="19e7e-158">Change any clustered indexes to nonclustered indexes.</span></span>  
  
-   <span data-ttu-id="19e7e-159">Toutes les colonnes dans la clé d'un index doivent être spécifiées comme `NOT NULL`.</span><span class="sxs-lookup"><span data-stu-id="19e7e-159">All columns in the key of an index must be specified as `NOT NULL`.</span></span>  
  
-   <span data-ttu-id="19e7e-160">Si vous utilisez l'option de table mémoire optimisée `DURABILITY = SCHEMA_AND_DATA` , la table doit avoir un index de clé primaire non cluster.</span><span class="sxs-lookup"><span data-stu-id="19e7e-160">If using the memory-optimized table option `DURABILITY = SCHEMA_AND_DATA` the table must have a nonclustered primary key index.</span></span>  
  
-   <span data-ttu-id="19e7e-161">ANSI_PADDING doit être activé.</span><span class="sxs-lookup"><span data-stu-id="19e7e-161">ANSI_PADDING must be ON.</span></span>  
  
##  <a name="replicating-changes-to-a-primary-key"></a><a name="PrimaryKey"></a><span data-ttu-id="19e7e-162">Réplication des modifications apportées à une clé primaire</span><span class="sxs-lookup"><span data-stu-id="19e7e-162">Replicating changes to a primary key</span></span>  
 <span data-ttu-id="19e7e-163">La clé primaire d'une table mémoire optimisée ne peut pas être mise à jour.</span><span class="sxs-lookup"><span data-stu-id="19e7e-163">The primary key of a memory-optimized table cannot be updated.</span></span> <span data-ttu-id="19e7e-164">Pour répliquer une mise à jour de clé primaire sur un abonné, modifiez la procédure stockée de mise à jour pour fournir la mise à jour en tant que paire d'opérations de suppression et insertion.</span><span class="sxs-lookup"><span data-stu-id="19e7e-164">To replicate a primary key update on a subscriber, modify the update stored procedure to deliver the update as a delete and insert pair.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19e7e-165">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="19e7e-165">See Also</span></span>  
 [<span data-ttu-id="19e7e-166">Réplication SQL Server</span><span class="sxs-lookup"><span data-stu-id="19e7e-166">SQL Server Replication</span></span>](sql-server-replication.md)  
  
  
