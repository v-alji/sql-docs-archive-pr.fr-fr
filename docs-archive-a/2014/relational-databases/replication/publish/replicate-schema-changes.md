---
title: Répliquer les modifications de schéma | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], schema changes
- schemas [SQL Server replication], replicating changes
ms.assetid: c09007f0-9374-4f60-956b-8a87670cd043
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: bec2f363cd8c4f7dea45935568a88722b19323fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610606"
---
# <a name="replicate-schema-changes"></a><span data-ttu-id="4490a-102">Répliquer les modifications de schéma</span><span class="sxs-lookup"><span data-stu-id="4490a-102">Replicate Schema Changes</span></span>
  <span data-ttu-id="4490a-103">Cette rubrique explique comment répliquer les modification de schéma dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4490a-103">This topic describes how to replicate schema changes in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="4490a-104">Si vous apportez les modifications de schéma suivantes à un article publié, elles sont propagées, par défaut, aux Abonnés [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="4490a-104">If you make the following schema changes to a published article, they are propagated, by default, to [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Subscribers:</span></span>  
  
-   <span data-ttu-id="4490a-105">ALTER TABLE</span><span class="sxs-lookup"><span data-stu-id="4490a-105">ALTER TABLE</span></span>  
  
-   <span data-ttu-id="4490a-106">ALTER VIEW</span><span class="sxs-lookup"><span data-stu-id="4490a-106">ALTER VIEW</span></span>  
  
-   <span data-ttu-id="4490a-107">ALTER PROCEDURE</span><span class="sxs-lookup"><span data-stu-id="4490a-107">ALTER PROCEDURE</span></span>  
  
-   <span data-ttu-id="4490a-108">ALTER FUNCTION</span><span class="sxs-lookup"><span data-stu-id="4490a-108">ALTER FUNCTION</span></span>  
  
-   <span data-ttu-id="4490a-109">ALTER TRIGGER</span><span class="sxs-lookup"><span data-stu-id="4490a-109">ALTER TRIGGER</span></span>  
  
 <span data-ttu-id="4490a-110">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="4490a-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="4490a-111">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="4490a-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="4490a-112">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="4490a-112">Limitations and Restrictions</span></span>](#Restrictions)  
  
-   <span data-ttu-id="4490a-113">**Pour répliquer les modifications de schéma à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="4490a-113">**To replicate schema changes, using:**</span></span>  
  
     [<span data-ttu-id="4490a-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4490a-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="4490a-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4490a-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4490a-116">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="4490a-116">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="4490a-117">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="4490a-117">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="4490a-118">L’instruction ALTER TABLE ... DROP COLUMN est toujours répliquée vers tous les Abonnés dont l’abonnement contient les colonnes à supprimer, même si vous désactivez la réplication des modifications de schéma.</span><span class="sxs-lookup"><span data-stu-id="4490a-118">The ALTER TABLE ... DROP COLUMN statement is always replicated to all Subscribers whose subscription contains the columns being dropped, even if you disable the replication of schema changes.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4490a-119">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4490a-119">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="4490a-120">Si vous ne voulez pas répliquer des modifications de schéma pour une publication, désactivez la réplication des modifications de schéma dans la boîte de dialogue **Propriétés de la publication - \<Publication>** .</span><span class="sxs-lookup"><span data-stu-id="4490a-120">If you do not want to replicate schema changes for a publication, disable the replication of schema changes in the **Publication Properties - \<Publication>** dialog box.</span></span> <span data-ttu-id="4490a-121">Pour plus d'informations sur l'accès à cette boîte de dialogue, consultez [Afficher et modifier les propriétés d’un serveur de publication](view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="4490a-121">For more information about accessing this dialog box, see [View and Modify Publication Properties](view-and-modify-publication-properties.md).</span></span>  
  
#### <a name="to-disable-replication-of-schema-changes"></a><span data-ttu-id="4490a-122">Pour désactiver la réplication des modifications de schéma</span><span class="sxs-lookup"><span data-stu-id="4490a-122">To disable replication of schema changes</span></span>  
  
1.  <span data-ttu-id="4490a-123">Dans la page **Options d’abonnement** de la boîte de dialogue **Propriétés de la publication - \<Publication>** , définissez la propriété **Répliquer les modifications de schéma** sur **False**.</span><span class="sxs-lookup"><span data-stu-id="4490a-123">On the **Subscription Options** page of the **Publication Properties - \<Publication>** dialog box, set the value of the **Replicate schema changes** property to **False**.</span></span>  
  
2.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
     <span data-ttu-id="4490a-124">Pour propager seulement des modifications de schéma spécifiques, définissez la propriété à **True** avant une modification de schéma, puis définissez-la à **False** après avoir effectué la modification.</span><span class="sxs-lookup"><span data-stu-id="4490a-124">To propagate only specific schema changes, set the property to **True** before a schema change, and then set it to **False** after the change is made.</span></span> <span data-ttu-id="4490a-125">Inversement, pour propager la plupart des modifications de schéma mais pas une modification spécifique, définissez la propriété à **False** avant la modification de schéma, puis définissez-la à **True** après avoir effectué la modification.</span><span class="sxs-lookup"><span data-stu-id="4490a-125">Conversely, to propagate most schema changes, but not a given change, set the property to **False** before the schema change, and then set it to **True** after the change is made.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4490a-126">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4490a-126">Using Transact-SQL</span></span>  
 <span data-ttu-id="4490a-127">Vous pouvez utiliser les procédures stockées de réplication pour spécifier si ces modifications de schéma sont répliquées.</span><span class="sxs-lookup"><span data-stu-id="4490a-127">You can use replication stored procedures to specify whether these schema changes are replicated.</span></span> <span data-ttu-id="4490a-128">La procédure stockée que vous utilisez dépend du type de publication.</span><span class="sxs-lookup"><span data-stu-id="4490a-128">The stored procedure that you use depends on the type of publication.</span></span>  
  
#### <a name="to-create-a-snapshot-or-transactional-publication-that-does-not-replicate-schema-changes"></a><span data-ttu-id="4490a-129">Pour créer une publication transactionnelle ou d'instantané qui ne réplique pas les modifications du schéma</span><span class="sxs-lookup"><span data-stu-id="4490a-129">To create a snapshot or transactional publication that does not replicate schema changes</span></span>  
  
1.  <span data-ttu-id="4490a-130">Dans la base de données de publication sur le serveur de publication, exécutez [sp_addpublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addpublication-transact-sql), en spécifiant la valeur **0** pour \*\* \@ replicate_ddl\*\*.</span><span class="sxs-lookup"><span data-stu-id="4490a-130">At the Publisher on the publication database, execute [sp_addpublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addpublication-transact-sql), specifying a value of **0** for **\@replicate_ddl**.</span></span> <span data-ttu-id="4490a-131">Pour plus d’informations, voir [Create a Publication](create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="4490a-131">For more information, see [Create a Publication](create-a-publication.md).</span></span>  
  
#### <a name="to-create-a-merge-publication-that-does-not-replicate-schema-changes"></a><span data-ttu-id="4490a-132">Pour créer une publication de fusion qui ne réplique pas les modifications du schéma</span><span class="sxs-lookup"><span data-stu-id="4490a-132">To create a merge publication that does not replicate schema changes</span></span>  
  
1.  <span data-ttu-id="4490a-133">Dans la base de données de publication sur le serveur de publication, exécutez [sp_addmergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addmergepublication-transact-sql), en spécifiant la valeur **0** pour \*\* \@ replicate_ddl\*\*.</span><span class="sxs-lookup"><span data-stu-id="4490a-133">At the Publisher on the publication database, execute [sp_addmergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addmergepublication-transact-sql), specifying a value of **0** for **\@replicate_ddl**.</span></span> <span data-ttu-id="4490a-134">Pour plus d’informations, voir [Create a Publication](create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="4490a-134">For more information, see [Create a Publication](create-a-publication.md).</span></span>  
  
#### <a name="to-temporarily-disable-replicating-schema-changes-for-a-snapshot-or-transactional-publication"></a><span data-ttu-id="4490a-135">Pour désactiver temporairement la réplication des modifications du schéma pour une publication transactionnelle ou d'instantané</span><span class="sxs-lookup"><span data-stu-id="4490a-135">To temporarily disable replicating schema changes for a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="4490a-136">Pour une publication avec réplication des modifications de schéma, exécutez [sp_changepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql), en affectant la valeur **replicate_ddl** à la \*\* \@ propriété\*\* et la valeur **0** à la \*\* \@ valeur\*\*.</span><span class="sxs-lookup"><span data-stu-id="4490a-136">For a publication with replication of schema changes, execute [sp_changepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql), specifying a value of **replicate_ddl** for **\@property** and a value of **0** for **\@value**.</span></span>  
  
2.  <span data-ttu-id="4490a-137">Exécutez la commande DDL sur l'objet publié.</span><span class="sxs-lookup"><span data-stu-id="4490a-137">Execute the DDL command on the published object.</span></span>  
  
3.  <span data-ttu-id="4490a-138">Facultatif Réactivez la réplication des modifications de schéma en exécutant [sp_changepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql), en affectant la valeur **replicate_ddl** à la \*\* \@ propriété\*\* et la valeur **1** à la \*\* \@ valeur\*\*.</span><span class="sxs-lookup"><span data-stu-id="4490a-138">(Optional) Re-enable replicating schema changes by executing [sp_changepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql), specifying a value of **replicate_ddl** for **\@property** and a value of **1** for **\@value**.</span></span>  
  
#### <a name="to-temporarily-disable-replicating-schema-changes-for-a-merge-publication"></a><span data-ttu-id="4490a-139">Pour désactiver temporairement la réplication des modifications du schéma pour une publication de fusion</span><span class="sxs-lookup"><span data-stu-id="4490a-139">To temporarily disable replicating schema changes for a merge publication</span></span>  
  
1.  <span data-ttu-id="4490a-140">Pour une publication avec réplication des modifications de schéma, exécutez [sp_changemergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql), en affectant la valeur **replicate_ddl** à la \*\* \@ propriété\*\* et la valeur **0** à la \*\* \@ valeur\*\*.</span><span class="sxs-lookup"><span data-stu-id="4490a-140">For a publication with replication of schema changes, execute [sp_changemergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql), specifying a value of **replicate_ddl** for **\@property** and a value of **0** for **\@value**.</span></span>  
  
2.  <span data-ttu-id="4490a-141">Exécutez la commande DDL sur l'objet publié.</span><span class="sxs-lookup"><span data-stu-id="4490a-141">Execute the DDL command on the published object.</span></span>  
  
3.  <span data-ttu-id="4490a-142">Facultatif Réactivez la réplication des modifications de schéma en exécutant [sp_changemergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql), en affectant la valeur **replicate_ddl** à la \*\* \@ propriété\*\* et la valeur **1** à la \*\* \@ valeur\*\*.</span><span class="sxs-lookup"><span data-stu-id="4490a-142">(Optional) Re-enable replicating schema changes by executing [sp_changemergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql), specifying a value of **replicate_ddl** for **\@property** and a value of **1** for **\@value**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4490a-143">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4490a-143">See Also</span></span>  
 <span data-ttu-id="4490a-144">[Modifier le schéma dans les bases de données de publication](make-schema-changes-on-publication-databases.md) </span><span class="sxs-lookup"><span data-stu-id="4490a-144">[Make Schema Changes on Publication Databases](make-schema-changes-on-publication-databases.md) </span></span>  
 [<span data-ttu-id="4490a-145">Modifier le schéma dans les bases de données de publication</span><span class="sxs-lookup"><span data-stu-id="4490a-145">Make Schema Changes on Publication Databases</span></span>](make-schema-changes-on-publication-databases.md)  
  
  
