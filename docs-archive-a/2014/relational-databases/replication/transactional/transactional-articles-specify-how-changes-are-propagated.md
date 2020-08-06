---
title: Spécifier le mode de propagation des modifications des articles transactionnels | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- transactional replication, propagation methods
ms.assetid: a10c5001-22cc-4667-8f0b-3d0818dca2e9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 72d377ba89f1d393eab48bd9c918012b0f503f9c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699438"
---
# <a name="specify-how-changes-are-propagated-for-transactional-articles"></a><span data-ttu-id="e46af-102">Spécifier le mode de propagation des modifications des articles transactionnels</span><span class="sxs-lookup"><span data-stu-id="e46af-102">Specify How Changes Are Propagated for Transactional Articles</span></span>
  <span data-ttu-id="e46af-103">La réplication transactionnelle permet de préciser comment les modifications des données sont propagées entre le serveur de publication et les Abonnés.</span><span class="sxs-lookup"><span data-stu-id="e46af-103">Transactional replication allows you to specify how data changes are propagated from the Publisher to Subscribers.</span></span> <span data-ttu-id="e46af-104">Pour chaque table publiée, vous pouvez spécifier l'une des quatre méthodes de propagation possibles d'une opération (INSERT, UPDATE ou DELETE) vers l'Abonné :</span><span class="sxs-lookup"><span data-stu-id="e46af-104">For each published table, you can specify one of four ways that each operation (INSERT, UPDATE, or DELETE) should be propagated to the Subscriber:</span></span>  
  
-   <span data-ttu-id="e46af-105">Spécifier que la réplication transactionnelle doit générer un script puis appeler une procédure stockée pour propager les modifications aux Abonnés (option par défaut).</span><span class="sxs-lookup"><span data-stu-id="e46af-105">Specify that transactional replication should script out and subsequently call a stored procedure to propagate changes to Subscribers (the default).</span></span>  
  
-   <span data-ttu-id="e46af-106">Spécifier que la modification doit être propagée à l'aide d'une instruction INSERT, UPDATE ou DELETE (option par défaut pour les Abonnés non[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ).</span><span class="sxs-lookup"><span data-stu-id="e46af-106">Specify that the change should be propagated using an INSERT, UPDATE, or DELETE statement (the default for non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Subscribers).</span></span>  
  
-   <span data-ttu-id="e46af-107">Spécifier l'utilisation d'une procédure stockée personnalisée.</span><span class="sxs-lookup"><span data-stu-id="e46af-107">Specify that a custom stored procedure should be used.</span></span>  
  
-   <span data-ttu-id="e46af-108">Spécifier que cette action ne doit pas être effectuée sur les Abonnés.</span><span class="sxs-lookup"><span data-stu-id="e46af-108">Specify that this action should not be performed at any Subscriber.</span></span> <span data-ttu-id="e46af-109">Les transactions de ce type ne sont pas répliquées.</span><span class="sxs-lookup"><span data-stu-id="e46af-109">Transactions of that type are not replicated.</span></span>  
  
 <span data-ttu-id="e46af-110">Par défaut, la réplication transactionnelle propage les modifications vers les abonnés via un groupe de procédures stockées installées sur chaque abonné.</span><span class="sxs-lookup"><span data-stu-id="e46af-110">By default, transactional replication propagates changes to Subscribers through a set of stored procedures that are installed on each Subscriber.</span></span> <span data-ttu-id="e46af-111">Lorsqu'une opération Insert, Update ou Delete est effectuée sur une table du serveur de publication, elle est convertie en appel à une procédure stockée sur l'Abonné.</span><span class="sxs-lookup"><span data-stu-id="e46af-111">When an insert, update or delete occurs on a table at the Publisher, the operation is translated into a call to a stored procedure at the Subscriber.</span></span> <span data-ttu-id="e46af-112">La procédure stockée accepte des paramètres correspondant aux colonnes de la table, ce qui permet la modification de ces colonnes sur l'Abonné.</span><span class="sxs-lookup"><span data-stu-id="e46af-112">The stored procedure accepts parameters that map to the columns in the table, allowing those columns to be changed at the Subscriber.</span></span>  
  
 <span data-ttu-id="e46af-113">Pour définir la méthode de propagation des modifications de données des articles transactionnels, consultez [Définir la méthode de propagation des modifications de données des articles transactionnels](../publish/set-the-propagation-method-for-data-changes-to-transactional-articles.md).</span><span class="sxs-lookup"><span data-stu-id="e46af-113">To set the propagation method for data changes to transactional articles, see [Set the Propagation Method for Data Changes to Transactional Articles](../publish/set-the-propagation-method-for-data-changes-to-transactional-articles.md).</span></span>  
  
## <a name="default-and-custom-stored-procedures"></a><span data-ttu-id="e46af-114">Procédures stockées par défaut et personnalisées</span><span class="sxs-lookup"><span data-stu-id="e46af-114">Default and custom stored procedures</span></span>  
 <span data-ttu-id="e46af-115">Trois procédures sont créées par défaut par la réplication pour chaque article de table :</span><span class="sxs-lookup"><span data-stu-id="e46af-115">The three procedures that replication creates by default for each table article are:</span></span>  
  
-   <span data-ttu-id="e46af-116">**sp_MSins_\<** *tablename* **>** , qui gère les insertions.</span><span class="sxs-lookup"><span data-stu-id="e46af-116">**sp_MSins_\<** *tablename* **>**, which handles inserts.</span></span>  
  
-   <span data-ttu-id="e46af-117">**sp_MSupd_\<** *tablename* **>** , qui gère les mises à jour.</span><span class="sxs-lookup"><span data-stu-id="e46af-117">**sp_MSupd_\<** *tablename* **>**, which handles updates.</span></span>  
  
-   <span data-ttu-id="e46af-118">**sp_MSdel_\<** *tablename* **>** , qui gère les suppressions.</span><span class="sxs-lookup"><span data-stu-id="e46af-118">**sp_MSdel_\<** *tablename* **>**, which handles deletes.</span></span>  
  
 <span data-ttu-id="e46af-119">Le **\<***tablename***>** utilisé dans la procédure varie en fonction de la méthode employée pour ajouter l’article à la publication et si la base de données d’abonnement contient une table avec un nom identique mais avec un propriétaire différent.</span><span class="sxs-lookup"><span data-stu-id="e46af-119">The **\<***tablename***>** used in the procedure depends on how the article was added to the publication and whether the subscription database contains a table of the same name with a different owner.</span></span>  
  
 <span data-ttu-id="e46af-120">N'importe laquelle de ces procédures peut être remplacée par une procédure personnalisée que vous spécifiez lors de l'ajout d'un article à une publication.</span><span class="sxs-lookup"><span data-stu-id="e46af-120">Any of these procedures can be replaced with a custom procedure that you specify when adding an article to a publication.</span></span> <span data-ttu-id="e46af-121">Les procédures personnalisées sont utilisées dans le cas où l'application exige une logique personnalisée, par exemple l'insertion de données dans une table d'audit lors de la mise à jour d'une ligne sur l'Abonné.</span><span class="sxs-lookup"><span data-stu-id="e46af-121">Custom procedures are used if an application requires custom logic, such as inserting data into an audit table when a row is updated at a Subscriber.</span></span> <span data-ttu-id="e46af-122">Pour plus d'informations sur la définition de procédures stockées personnalisées, reportez-vous à la liste des rubriques ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="e46af-122">For more information about specifying custom stored procedures, see the how to topics listed above.</span></span>  
  
 <span data-ttu-id="e46af-123">Si vous utilisez les procédures de réplication par défaut ou les procédures personnalisées, vous devez également spécifier la syntaxe d'appel pour chaque procédure (la réplication sélectionne les valeurs par défaut si vous utilisez les procédures par défaut).</span><span class="sxs-lookup"><span data-stu-id="e46af-123">If you specify the default replication procedures or custom procedures, you also specify call syntax for each procedure (replication selects defaults if you use the default procedures).</span></span> <span data-ttu-id="e46af-124">La syntaxe d'appel détermine la structure des paramètres fournis à la procédure et la quantité d'informations envoyées à l'Abonné avec chaque modification de données.</span><span class="sxs-lookup"><span data-stu-id="e46af-124">The call syntax determines the structure of the parameters provided to the procedure and how much information is sent to the Subscriber with each data change.</span></span> <span data-ttu-id="e46af-125">Pour plus d'informations, consultez la section « Syntaxe d'appel des procédures stockées », plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="e46af-125">For more information, see the section "Call Syntax for Stored Procedures" in this topic.</span></span>  
  
### <a name="considerations-for-using-custom-stored-procedures"></a><span data-ttu-id="e46af-126">Considérations sur l'utilisation des procédures stockées personnalisées</span><span class="sxs-lookup"><span data-stu-id="e46af-126">Considerations for Using Custom Stored Procedures</span></span>  
 <span data-ttu-id="e46af-127">Les éléments suivants doivent être pris en compte lors de l'utilisation de procédures stockées personnalisées :</span><span class="sxs-lookup"><span data-stu-id="e46af-127">Keep the following considerations in mind when using custom stored procedures:</span></span>  
  
-   <span data-ttu-id="e46af-128">Vous devez prendre en charge la logique de la procédure stockée ; [!INCLUDE[msCoName](../../../includes/msconame-md.md)] n'assure pas la prise en charge d'une logique personnalisée.</span><span class="sxs-lookup"><span data-stu-id="e46af-128">You must support the logic in the stored procedure; [!INCLUDE[msCoName](../../../includes/msconame-md.md)] does not provide support for custom logic.</span></span>  
  
-   <span data-ttu-id="e46af-129">Afin d'éviter les conflits avec les transactions utilisées par la réplication, évitez d'utiliser des transactions explicites dans les procédures personnalisées.</span><span class="sxs-lookup"><span data-stu-id="e46af-129">In order to avoid conflicts with the transactions used by replication, explicit transactions should not be used in custom procedures.</span></span>  
  
-   <span data-ttu-id="e46af-130">Le schéma de l'Abonné est généralement identique à celui du serveur de publication mais il peut également représenter un sous-ensemble du schéma du serveur de publication si vous utilisez le filtrage de colonnes.</span><span class="sxs-lookup"><span data-stu-id="e46af-130">The schema at the Subscriber is typically identical to the schema at the Publisher, but can also be a subset of the Publisher schema if column filtering is used.</span></span> <span data-ttu-id="e46af-131">Toutefois, si vous devez transformer le schéma lors du déplacement des données de telle sorte que le schéma de l'Abonné ne représente pas un sous-ensemble du schéma sur le serveur de publication, [!INCLUDE[ssISCurrent](../../../includes/ssiscurrent-md.md)] est la solution recommandée.</span><span class="sxs-lookup"><span data-stu-id="e46af-131">However, if you need to transform the schema as the data is moved such that the schema on the Subscriber is not a subset of the schema on the Publisher, [!INCLUDE[ssISCurrent](../../../includes/ssiscurrent-md.md)] is the recommended solution.</span></span> <span data-ttu-id="e46af-132">Pour plus d’informations, consultez [SQL Server Integration Services](../../../integration-services/sql-server-integration-services.md).</span><span class="sxs-lookup"><span data-stu-id="e46af-132">For more information, see [SQL Server Integration Services](../../../integration-services/sql-server-integration-services.md).</span></span>  
  
-   <span data-ttu-id="e46af-133">Si vous modifiez le schéma d'une table publiée, les procédures personnalisées doivent être régénérées.</span><span class="sxs-lookup"><span data-stu-id="e46af-133">If you make schema changes to a published table, the custom procedures must be regenerated.</span></span> <span data-ttu-id="e46af-134">Pour plus d’informations, consultez [Régénérer des procédures transactionnelles personnalisées pour refléter des modifications de schéma](transactional-articles-regenerate-to-reflect-schema-changes.md).</span><span class="sxs-lookup"><span data-stu-id="e46af-134">For more information, see [Regenerate Custom Transactional Procedures to Reflect Schema Changes](transactional-articles-regenerate-to-reflect-schema-changes.md).</span></span>  
  
-   <span data-ttu-id="e46af-135">Si vous utilisez une valeur supérieure à 1 pour le paramètre **-SubscriptionStreams** de l’Agent de distribution, vérifiez que les mises à jour des colonnes clés primaires se sont correctement déroulées.</span><span class="sxs-lookup"><span data-stu-id="e46af-135">If you use a value greater than 1 for **-SubscriptionStreams** parameter of the Distribution Agent, you must ensure that updates to primary key columns are successful.</span></span> <span data-ttu-id="e46af-136">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="e46af-136">For example:</span></span>  
  
    ```  
    update ... set pk = 2 where pk = 1 -- update 1  
    update ... set pk = 3 where pk = 2 -- update 2  
    ```  
  
     <span data-ttu-id="e46af-137">Si l'Agent de distribution utilise plusieurs connexions, ces deux mises à jour peuvent être répliquées sur différentes connexions.</span><span class="sxs-lookup"><span data-stu-id="e46af-137">If the Distribution Agent uses more than one connection, these two updates might be replicated over different connections.</span></span> <span data-ttu-id="e46af-138">Si la première mise à jour (update 1) est d'abord appliquée, cela ne pose aucun problème ; en revanche, si la deuxième mise à jour (update 2) est la première appliquée, elle retourne '0 ligne affectée' parce que la première mise à jour n'a pas encore été effectuée.</span><span class="sxs-lookup"><span data-stu-id="e46af-138">If update 1 is applied first, there is no problem; if update 2 is applied first it will return '0 rows affected' because update 1 has not yet occurred.</span></span> <span data-ttu-id="e46af-139">Dans les procédures par défaut, cette situation génère une erreur si aucune ligne n'est affectée dans une mise à jour :</span><span class="sxs-lookup"><span data-stu-id="e46af-139">This situation is handled in the default procedures by raising an error if no rows are affected on an update:</span></span>  
  
    ```  
    if @@rowcount = 0  
        if @@microsoftversion>0x07320000  
            exec sys.sp_MSreplraiserror 20598  
    ```  
  
     <span data-ttu-id="e46af-140">La génération de l'erreur force l'Agent de distribution à retenter les mises à jour sur une seule connexion, lesquelles, dans ce cas, réussissent.</span><span class="sxs-lookup"><span data-stu-id="e46af-140">Raising the error forces the Distribution Agent to retry the updates over a single connection, which will succeed.</span></span> <span data-ttu-id="e46af-141">Les procédures stockées personnalisées doivent inclure une logique similaire.</span><span class="sxs-lookup"><span data-stu-id="e46af-141">Custom stored procedures must include similar logic.</span></span>  
  
### <a name="call-syntax-for-stored-procedures"></a><span data-ttu-id="e46af-142">Syntaxe d'appel des procédures stockées</span><span class="sxs-lookup"><span data-stu-id="e46af-142">Call syntax for stored procedures</span></span>  
 <span data-ttu-id="e46af-143">Vous avez le choix entre cinq options quant à la syntaxe employée pour appeler les procédures utilisées par la réplication transactionnelle :</span><span class="sxs-lookup"><span data-stu-id="e46af-143">There are five options for the syntax used to call the procedures used by transactional replication:</span></span>  
  
-   <span data-ttu-id="e46af-144">Syntaxe CALL.</span><span class="sxs-lookup"><span data-stu-id="e46af-144">CALL syntax.</span></span> <span data-ttu-id="e46af-145">Peut être utilisée pour les insertions, les mises à jour et les suppressions.</span><span class="sxs-lookup"><span data-stu-id="e46af-145">Can be used for inserts, updates, and deletes.</span></span> <span data-ttu-id="e46af-146">Par défaut, la réplication utilise cette syntaxe pour les insertions et les suppressions.</span><span class="sxs-lookup"><span data-stu-id="e46af-146">By default, replication uses this syntax for inserts and deletes.</span></span>  
  
-   <span data-ttu-id="e46af-147">Syntaxe SCALL.</span><span class="sxs-lookup"><span data-stu-id="e46af-147">SCALL syntax.</span></span> <span data-ttu-id="e46af-148">Peut être utilisée uniquement pour les mises à jour.</span><span class="sxs-lookup"><span data-stu-id="e46af-148">Can be used for updates only.</span></span> <span data-ttu-id="e46af-149">Par défaut, la réplication utilise cette syntaxe pour les mises à jour.</span><span class="sxs-lookup"><span data-stu-id="e46af-149">By default, replication uses this syntax for updates.</span></span>  
  
-   <span data-ttu-id="e46af-150">Syntaxe MCALL.</span><span class="sxs-lookup"><span data-stu-id="e46af-150">MCALL syntax.</span></span> <span data-ttu-id="e46af-151">Peut être utilisée uniquement pour les mises à jour.</span><span class="sxs-lookup"><span data-stu-id="e46af-151">Can be used for updates only.</span></span>  
  
-   <span data-ttu-id="e46af-152">Syntaxe XCALL</span><span class="sxs-lookup"><span data-stu-id="e46af-152">XCALL syntax.</span></span> <span data-ttu-id="e46af-153">Peut être utilisée pour les mises à jour et les suppressions.</span><span class="sxs-lookup"><span data-stu-id="e46af-153">Can be used for updates and deletes.</span></span>  
  
-   <span data-ttu-id="e46af-154">VCALL.</span><span class="sxs-lookup"><span data-stu-id="e46af-154">VCALL.</span></span> <span data-ttu-id="e46af-155">Utilisée pour les abonnements pouvant être mis à jour.</span><span class="sxs-lookup"><span data-stu-id="e46af-155">Used for updatable subscriptions.</span></span> <span data-ttu-id="e46af-156">À usage interne uniquement</span><span class="sxs-lookup"><span data-stu-id="e46af-156">Internal use only.</span></span>  
  
 <span data-ttu-id="e46af-157">Ces méthodes diffèrent par le volume de données propagé à l'Abonné.</span><span class="sxs-lookup"><span data-stu-id="e46af-157">Each method differs in the amount of data that is propagated to the Subscriber.</span></span> <span data-ttu-id="e46af-158">Par exemple, SCALL passe des valeurs uniquement pour les colonnes affectées par une mise à jour.</span><span class="sxs-lookup"><span data-stu-id="e46af-158">For example, SCALL passes in values only for the columns that are actually affected by an update.</span></span> <span data-ttu-id="e46af-159">XCALL, en revanche, exige toutes les colonnes (qu'elles soient affectées ou non par une mise à jour) et toutes les anciennes valeurs des données pour chaque colonne.</span><span class="sxs-lookup"><span data-stu-id="e46af-159">XCALL, by contrast, requires all columns (whether affected by an update or not) and all the old data values for each column.</span></span> <span data-ttu-id="e46af-160">La syntaxe SCALL convient généralement aux opérations de mise à jour sauf si votre application exige toutes les valeurs des données au cours d'une mise à jour, auquel cas vous pouvez utiliser XCALL.</span><span class="sxs-lookup"><span data-stu-id="e46af-160">In many cases, SCALL is appropriate for updates, but if your application requires all the data values during an update, XCALL allows for this.</span></span>  
  
#### <a name="call-syntax"></a><span data-ttu-id="e46af-161">Syntaxe CALL</span><span class="sxs-lookup"><span data-stu-id="e46af-161">CALL Syntax</span></span>  
 <span data-ttu-id="e46af-162">Procédures stockées INSERT</span><span class="sxs-lookup"><span data-stu-id="e46af-162">INSERT stored procedures</span></span>  
 <span data-ttu-id="e46af-163">Les procédures stockées qui gèrent des instructions INSERT recevront les valeurs insérées pour toutes les colonnes :</span><span class="sxs-lookup"><span data-stu-id="e46af-163">Stored procedures handling INSERT statements will be passed the inserted values for all columns:</span></span>  
  
```  
c1, c2, c3,... cn  
```  
  
 <span data-ttu-id="e46af-164">Procédures stockées UPDATE</span><span class="sxs-lookup"><span data-stu-id="e46af-164">UPDATE stored procedures</span></span>  
 <span data-ttu-id="e46af-165">Les procédures stockées gérant des instructions UPDATE recevront les valeurs mises à jour pour toutes les colonnes définies dans l'article, suivies des valeurs d'origine pour les colonnes clés primaire (aucune tentative ne sera faite pour déterminer les colonnes qui ont été modifiées) :</span><span class="sxs-lookup"><span data-stu-id="e46af-165">Stored procedures handling UPDATE statements will be passed the updated values for all columns defined in the article, followed by the original values for the primary key columns (no attempt is made to determine which columns were changed.):</span></span>  
  
```  
c1, c2, c3,... cn, pkc1, pkc2, pkc3,... pkcn  
```  
  
 <span data-ttu-id="e46af-166">Procédures stockées DELETE</span><span class="sxs-lookup"><span data-stu-id="e46af-166">DELETE stored procedures</span></span>  
 <span data-ttu-id="e46af-167">Les procédures stockées qui gèrent des instructions DELETE recevront des valeurs pour les colonnes clés primaire :</span><span class="sxs-lookup"><span data-stu-id="e46af-167">Stored procedures handling DELETE statements will be passed values for the primary key columns:</span></span>  
  
```  
pkc1, pkc2, pkc3,... pkcn  
```  
  
#### <a name="scall-syntax"></a><span data-ttu-id="e46af-168">Syntaxe SCALL</span><span class="sxs-lookup"><span data-stu-id="e46af-168">SCALL Syntax</span></span>  
 <span data-ttu-id="e46af-169">Procédures stockées UPDATE</span><span class="sxs-lookup"><span data-stu-id="e46af-169">UPDATE stored procedures</span></span>  
 <span data-ttu-id="e46af-170">Les procédures stockées gérant des instructions UPDATE ne recevront les valeurs mises à jour que pour les colonnes qui ont été modifiées, suivies tout d'abord des valeurs d'origine des colonnes clés primaire, puis d'un paramètre de masque binaire (`binary(n)`) indiquant les colonnes modifiées.</span><span class="sxs-lookup"><span data-stu-id="e46af-170">Stored procedures handling UPDATE statements will be passed the updated values only for those columns that have changed, followed by the original values for the primary key columns, followed by a bitmask (`binary(n)`) parameter that indicates the changed columns.</span></span> <span data-ttu-id="e46af-171">Dans l'exemple suivant, la colonne 2 (c2) n'a pas été modifiée :</span><span class="sxs-lookup"><span data-stu-id="e46af-171">In the following example, column 2 (c2) has not changed:</span></span>  
  
```  
c1, , c3,... cn, pkc1, pkc2, pkc3,... pkcn, bitmask  
```  
  
#### <a name="mcall-syntax"></a><span data-ttu-id="e46af-172">Syntaxe MCALL</span><span class="sxs-lookup"><span data-stu-id="e46af-172">MCALL Syntax</span></span>  
 <span data-ttu-id="e46af-173">Procédures stockées UPDATE</span><span class="sxs-lookup"><span data-stu-id="e46af-173">UPDATE stored procedures</span></span>  
 <span data-ttu-id="e46af-174">Les procédures stockées gérant des instructions UPDATE recevront les valeurs mises à jour de toutes les colonnes définies dans l'article, suivies tout d'abord des valeurs d'origine des colonnes clés primaire, puis d'un paramètre de masque binaire (`binary(n)`) indiquant les colonnes modifiées :</span><span class="sxs-lookup"><span data-stu-id="e46af-174">Stored procedures handling UPDATE statements will be passed the updated values for all columns defined in the article, followed by the original values for the primary key columns, followed by a bitmask (`binary(n)`) parameter that indicates the changed columns:</span></span>  
  
```  
c1, c2, c3,... cn, pkc1, pkc2, pkc3,... pkcn, bitmask  
```  
  
#### <a name="xcall-syntax"></a><span data-ttu-id="e46af-175">Syntaxe XCALL</span><span class="sxs-lookup"><span data-stu-id="e46af-175">XCALL Syntax</span></span>  
 <span data-ttu-id="e46af-176">Procédures stockées UPDATE</span><span class="sxs-lookup"><span data-stu-id="e46af-176">UPDATE stored procedures</span></span>  
 <span data-ttu-id="e46af-177">Les procédures stockées gérant des instructions UPDATE recevront les valeurs d'origine (c'est-à-dire l'image avant) de toutes les colonnes définies dans l'article, suivies des valeurs mises à jour (image après) de ces mêmes colonnes :</span><span class="sxs-lookup"><span data-stu-id="e46af-177">Stored procedures handling UPDATE statements will be passed the original values (the before image) for all columns defined in the article, followed by the updated values (the after image) for all columns defined in the article:</span></span>  
  
```  
old-c1, old-c2, old-c3,... old-cn, c1, c2, c3,... cn,  
```  
  
 <span data-ttu-id="e46af-178">Procédures stockées DELETE</span><span class="sxs-lookup"><span data-stu-id="e46af-178">DELETE stored procedures</span></span>  
 <span data-ttu-id="e46af-179">Les procédures stockées qui gèrent des instructions DELETE recevront les valeurs d'origine (image avant) de toutes les colonnes définies dans l'article :</span><span class="sxs-lookup"><span data-stu-id="e46af-179">Stored procedures handling DELETE statements will be passed the original (the before image) values for all columns defined in the article:</span></span>  
  
```  
old-c1, old-c2, old-c3,... old-cn  
```  
  
> [!NOTE]  
>  <span data-ttu-id="e46af-180">Lorsque la syntaxe XCALL est utilisée, les valeurs de l'image avant des colonnes **text** et **image** sont censées être NULL.</span><span class="sxs-lookup"><span data-stu-id="e46af-180">When using XCALL, the before image values for **text** and **image** columns are expected to be NULL.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="e46af-181">Exemples</span><span class="sxs-lookup"><span data-stu-id="e46af-181">Examples</span></span>  
 <span data-ttu-id="e46af-182">Les procédures suivantes représentent les procédures par défaut créées pour la `Vendor Table` dans la base de données exemple de [!INCLUDE[ssSampleDBCoShort](../../../includes/sssampledbcoshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e46af-182">The following procedures are the default procedures created for the `Vendor Table` in the [!INCLUDE[ssSampleDBCoShort](../../../includes/sssampledbcoshort-md.md)] sample database.</span></span>  
  
```  
--INSERT procedure using CALL syntax  
create procedure [sp_MSins_PurchasingVendor]   
  @c1 int,@c2 nvarchar(15),@c3 nvarchar(50),@c4 tinyint,@c5 bit,@c6 bit,@c7 nvarchar(1024),@c8 datetime  
as   
begin   
insert into [Purchasing].[Vendor]([VendorID]  
,[AccountNumber]  
,[Name]  
,[CreditRating]  
,[PreferredVendorStatus]  
,[ActiveFlag]  
,[PurchasingWebServiceURL]  
,[ModifiedDate])  
values (   
 @c1  
,@c2  
,@c3  
,@c4  
,@c5  
,@c6  
,@c7  
,@c8  
 )   
end  
go  
  
--UPDATE procedure using SCALL syntax  
create procedure [sp_MSupd_PurchasingVendor]   
 @c1 int = null,@c2 nvarchar(15) = null,@c3 nvarchar(50) = null,@c4 tinyint = null,@c5 bit = null,@c6 bit = null,@c7 nvarchar(1024) = null,@c8 datetime = null,@pkc1 int  
,@bitmap binary(2)  
as  
begin  
update [Purchasing].[Vendor] set   
 [AccountNumber] = case substring(@bitmap,1,1) & 2 when 2 then @c2 else [AccountNumber] end  
,[Name] = case substring(@bitmap,1,1) & 4 when 4 then @c3 else [Name] end  
,[CreditRating] = case substring(@bitmap,1,1) & 8 when 8 then @c4 else [CreditRating] end  
,[PreferredVendorStatus] = case substring(@bitmap,1,1) & 16 when 16 then @c5 else [PreferredVendorStatus] end  
,[ActiveFlag] = case substring(@bitmap,1,1) & 32 when 32 then @c6 else [ActiveFlag] end  
,[PurchasingWebServiceURL] = case substring(@bitmap,1,1) & 64 when 64 then @c7 else [PurchasingWebServiceURL] end  
,[ModifiedDate] = case substring(@bitmap,1,1) & 128 when 128 then @c8 else [ModifiedDate] end  
where [VendorID] = @pkc1  
if @@rowcount = 0  
    if @@microsoftversion>0x07320000  
        exec sp_MSreplraiserror 20598  
end  
go  
  
--DELETE procedure using CALL syntax  
create procedure [sp_MSdel_PurchasingVendor]   
  @pkc1 int  
as   
begin   
delete [Purchasing].[Vendor]  
where [VendorID] = @pkc1  
if @@rowcount = 0  
    if @@microsoftversion>0x07320000  
        exec sp_MSreplraiserror 20598  
end   
go  
```  
  
## <a name="see-also"></a><span data-ttu-id="e46af-183">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e46af-183">See Also</span></span>  
 [<span data-ttu-id="e46af-184">Article Options for Transactional Replication</span><span class="sxs-lookup"><span data-stu-id="e46af-184">Article Options for Transactional Replication</span></span>](article-options-for-transactional-replication.md)  
  
  
