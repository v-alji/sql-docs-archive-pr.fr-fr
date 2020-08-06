---
title: Supprimer un article | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- articles [SQL Server replication], dropping
- sp_droparticle
- sp_dropmergearticle
- deleting articles
- removing articles
- dropping articles
ms.assetid: 185b58fc-38c0-4abe-822e-6ec20066c863
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 082f90d33c2b8dedfae34dcada9b3935bed134ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602064"
---
# <a name="delete-an-article"></a><span data-ttu-id="9d180-102">Supprimer un article</span><span class="sxs-lookup"><span data-stu-id="9d180-102">Delete an Article</span></span>
  <span data-ttu-id="9d180-103">Cette rubrique explique comment supprimer un article dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[tsql](../../../includes/tsql-md.md)] ou des objets RMO (Replication Management Objects).</span><span class="sxs-lookup"><span data-stu-id="9d180-103">This topic describes how to delete an article in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../../includes/tsql-md.md)] or Replication Management Objects (RMO).</span></span> <span data-ttu-id="9d180-104">Pour plus d’informations sur les conditions dans lesquelles un article peut être supprimé et pour savoir si la suppression d’un article requiert un nouvel instantané ou la réinitialisation des abonnements, consultez [Ajouter et supprimer des articles de publications existantes](add-articles-to-and-drop-articles-from-existing-publications.md).</span><span class="sxs-lookup"><span data-stu-id="9d180-104">For information about the conditions under which articles can be dropped and whether dropping an article requires a new snapshot or the reinitialization of subscriptions, see [Add Articles to and Drop Articles from Existing Publications](add-articles-to-and-drop-articles-from-existing-publications.md).</span></span>  
  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="9d180-105">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9d180-105">Using Transact-SQL</span></span>  
 <span data-ttu-id="9d180-106">Les articles peuvent être supprimés par programme en utilisant des procédures stockées de réplication.</span><span class="sxs-lookup"><span data-stu-id="9d180-106">Articles can be deleted programmatically using replication stored procedures.</span></span> <span data-ttu-id="9d180-107">Les procédures stockées utilisées dépendent du type de publication auquel l'article appartient.</span><span class="sxs-lookup"><span data-stu-id="9d180-107">The stored procedures that you use depend on the type of publication to which the article belongs.</span></span>  
  
#### <a name="to-delete-an-article-from-a-snapshot-or-transactional-publication"></a><span data-ttu-id="9d180-108">Pour supprimer un article d'une publication transactionnelle ou d'instantané</span><span class="sxs-lookup"><span data-stu-id="9d180-108">To delete an article from a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="9d180-109">Exécutez [sp_droparticle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-droparticle-transact-sql) pour supprimer un article spécifié par **\@article** d’une publication spécifiée par **\@publication**.</span><span class="sxs-lookup"><span data-stu-id="9d180-109">Execute [sp_droparticle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-droparticle-transact-sql) to delete an article, specified by **\@article**, from a publication, specified by **\@publication**.</span></span> <span data-ttu-id="9d180-110">Spécifiez une valeur de **1** pour \*\* \@ force_invalidate_snapshot\*\*.</span><span class="sxs-lookup"><span data-stu-id="9d180-110">Specify a value of **1** for **\@force_invalidate_snapshot**.</span></span>  
  
2.  <span data-ttu-id="9d180-111">(Facultatif) Pour supprimer entièrement l'objet publié de la base de données, exécutez la commande `DROP <objectname>` au niveau du serveur de publication dans la base de données de publication.</span><span class="sxs-lookup"><span data-stu-id="9d180-111">(Optional) To remove the published object from the database entirely, execute the `DROP <objectname>` command at the Publisher on the publication database.</span></span>  
  
#### <a name="to-delete-an-article-from-a-merge-publication"></a><span data-ttu-id="9d180-112">Pour supprimer un article d'une publication de fusion</span><span class="sxs-lookup"><span data-stu-id="9d180-112">To delete an article from a merge publication</span></span>  
  
1.  <span data-ttu-id="9d180-113">Exécutez [sp_dropmergearticle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropmergearticle-transact-sql) pour supprimer un article spécifié par **\@article** d’une publication spécifiée par **\@publication**.</span><span class="sxs-lookup"><span data-stu-id="9d180-113">Execute [sp_dropmergearticle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropmergearticle-transact-sql) to delete an article, specified by **\@article**, from a publication, specified by **\@publication**.</span></span> <span data-ttu-id="9d180-114">Si nécessaire, affectez la valeur **1** à \*\* \@ force_invalidate_snapshot\*\* et la valeur **1** à \*\* \@ force_reinit_subscription\*\*.</span><span class="sxs-lookup"><span data-stu-id="9d180-114">If necessary, specify a value of **1** for **\@force_invalidate_snapshot** and a value of **1** for **\@force_reinit_subscription**.</span></span>  
  
2.  <span data-ttu-id="9d180-115">(Facultatif) Pour supprimer entièrement l'objet publié de la base de données, exécutez la commande `DROP <objectname>` au niveau du serveur de publication dans la base de données de publication.</span><span class="sxs-lookup"><span data-stu-id="9d180-115">(Optional) To remove the published object from the database entirely, execute the `DROP <objectname>` command at the Publisher on the publication database.</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="9d180-116">Exemples (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="9d180-116">Examples (Transact-SQL)</span></span>  
 <span data-ttu-id="9d180-117">L'exemple suivant supprime un article d'une publication transactionnelle.</span><span class="sxs-lookup"><span data-stu-id="9d180-117">The following example deletes an article from a transactional publication.</span></span> <span data-ttu-id="9d180-118">Étant donné que cette modification invalide l’instantané existant, la valeur **1** est spécifiée pour le paramètre \*\* \@ force_invalidate_snapshot\*\* .</span><span class="sxs-lookup"><span data-stu-id="9d180-118">Because this change invalidates the existing snapshot, a value of **1** is specified for the **\@force_invalidate_snapshot** parameter.</span></span>  
  
 [!code-sql[HowTo#sp_droparticle](../../../snippets/tsql/SQL15/replication/howto/tsql/droptranpub.sql#sp_droparticle)]  
  
 <span data-ttu-id="9d180-119">L'exemple suivant supprime deux articles d'une publication de fusion.</span><span class="sxs-lookup"><span data-stu-id="9d180-119">The following example deletes two articles from a merge publication.</span></span> <span data-ttu-id="9d180-120">Étant donné que ces modifications invalident l’instantané existant, la valeur **1** est spécifiée pour le paramètre \*\* \@ force_invalidate_snapshot\*\* .</span><span class="sxs-lookup"><span data-stu-id="9d180-120">Because these changes invalidate the existing snapshot, a value of **1** is specified for the **\@force_invalidate_snapshot** parameter.</span></span>  
  
 [!code-sql[HowTo#sp_dropmergearticle](../../../snippets/tsql/SQL15/replication/howto/tsql/dropmergepub.sql#sp_dropmergearticle)]
 [!code-sql[HowTo#sp_dropmergearticle](../../../snippets/tsql/SQL15/replication/howto/tsql/dropmergearticles.sql#sp_dropmergearticle)]  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="9d180-121">Utilisation d'objets RMO (Replication Management Objects)</span><span class="sxs-lookup"><span data-stu-id="9d180-121">Using Replication Management Objects (RMO)</span></span>  
 <span data-ttu-id="9d180-122">Vous pouvez supprimer des articles par programme à l'aide des objets RMO (Replication Management Objects).</span><span class="sxs-lookup"><span data-stu-id="9d180-122">You can delete articles programmatically by using Replication Management Objects (RMO).</span></span> <span data-ttu-id="9d180-123">Les classes RMO à utiliser pour supprimer un article dépendent du type de publication auquel l'article appartient.</span><span class="sxs-lookup"><span data-stu-id="9d180-123">The RMO classes you use to delete an article depend on the type of publication to which the article belongs.</span></span>  
  
#### <a name="to-delete-an-article-that-belongs-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="9d180-124">Pour supprimer un article qui appartient à une publication transactionnelle ou d'instantané.</span><span class="sxs-lookup"><span data-stu-id="9d180-124">To delete an article that belongs to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="9d180-125">Créez une connexion au serveur de publication en utilisant la classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="9d180-125">Create a connection to the Publisher by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="9d180-126">Créez une instance de la classe <xref:Microsoft.SqlServer.Replication.TransArticle>.</span><span class="sxs-lookup"><span data-stu-id="9d180-126">Create an instance of the <xref:Microsoft.SqlServer.Replication.TransArticle> class.</span></span>  
  
3.  <span data-ttu-id="9d180-127">Définissez les propriétés <xref:Microsoft.SqlServer.Replication.Article.Name%2A>, <xref:Microsoft.SqlServer.Replication.Article.PublicationName%2A>et <xref:Microsoft.SqlServer.Replication.Article.DatabaseName%2A> .</span><span class="sxs-lookup"><span data-stu-id="9d180-127">Set the <xref:Microsoft.SqlServer.Replication.Article.Name%2A>, <xref:Microsoft.SqlServer.Replication.Article.PublicationName%2A>, and <xref:Microsoft.SqlServer.Replication.Article.DatabaseName%2A> properties.</span></span>  
  
4.  <span data-ttu-id="9d180-128">Définissez la connexion créée à l'étape 1 pour la propriété <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> .</span><span class="sxs-lookup"><span data-stu-id="9d180-128">Set the connection from step 1 for the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property.</span></span>  
  
5.  <span data-ttu-id="9d180-129">Vérifiez la propriété <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> pour vérifier que l'article existe.</span><span class="sxs-lookup"><span data-stu-id="9d180-129">Check the <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> property to verify that the article exists.</span></span> <span data-ttu-id="9d180-130">Si la valeur de cette propriété est `false`, soit les propriétés de l'article ont été définies de manière incorrecte à l'étape 3, soit l'article n'existe pas.</span><span class="sxs-lookup"><span data-stu-id="9d180-130">If the value of this property is `false`, either the article properties in step 3 were defined incorrectly or the article does not exist.</span></span>  
  
6.  <span data-ttu-id="9d180-131">Appelez la méthode <xref:Microsoft.SqlServer.Replication.Article.Remove%2A> .</span><span class="sxs-lookup"><span data-stu-id="9d180-131">Call the <xref:Microsoft.SqlServer.Replication.Article.Remove%2A> method.</span></span>  
  
7.  <span data-ttu-id="9d180-132">Fermez toutes les connexions.</span><span class="sxs-lookup"><span data-stu-id="9d180-132">Close all connections.</span></span>  
  
#### <a name="to-delete-an-article-that-belongs-to-a-merge-publication"></a><span data-ttu-id="9d180-133">Pour supprimer un article qui appartient à une publication de fusion</span><span class="sxs-lookup"><span data-stu-id="9d180-133">To delete an article that belongs to a merge publication</span></span>  
  
1.  <span data-ttu-id="9d180-134">Créez une connexion au serveur de publication en utilisant la classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="9d180-134">Create a connection to the Publisher by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="9d180-135">Créez une instance de la classe <xref:Microsoft.SqlServer.Replication.MergeArticle>.</span><span class="sxs-lookup"><span data-stu-id="9d180-135">Create an instance of the <xref:Microsoft.SqlServer.Replication.MergeArticle> class.</span></span>  
  
3.  <span data-ttu-id="9d180-136">Définissez les propriétés <xref:Microsoft.SqlServer.Replication.Article.Name%2A>, <xref:Microsoft.SqlServer.Replication.Article.PublicationName%2A>et <xref:Microsoft.SqlServer.Replication.Article.DatabaseName%2A> .</span><span class="sxs-lookup"><span data-stu-id="9d180-136">Set the <xref:Microsoft.SqlServer.Replication.Article.Name%2A>, <xref:Microsoft.SqlServer.Replication.Article.PublicationName%2A>, and <xref:Microsoft.SqlServer.Replication.Article.DatabaseName%2A> properties.</span></span>  
  
4.  <span data-ttu-id="9d180-137">Définissez la connexion créée à l'étape 1 pour la propriété <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> .</span><span class="sxs-lookup"><span data-stu-id="9d180-137">Set the connection from step 1 for the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property.</span></span>  
  
5.  <span data-ttu-id="9d180-138">Vérifiez la propriété <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> pour vérifier que l'article existe.</span><span class="sxs-lookup"><span data-stu-id="9d180-138">Check the <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> property to verify that the article exists.</span></span> <span data-ttu-id="9d180-139">Si la valeur de cette propriété est `false`, soit les propriétés de l'article ont été définies de manière incorrecte à l'étape 3, soit l'article n'existe pas.</span><span class="sxs-lookup"><span data-stu-id="9d180-139">If the value of this property is `false`, either the article properties in step 3 were defined incorrectly or the article does not exist.</span></span>  
  
6.  <span data-ttu-id="9d180-140">Appelez la méthode <xref:Microsoft.SqlServer.Replication.Article.Remove%2A> .</span><span class="sxs-lookup"><span data-stu-id="9d180-140">Call the <xref:Microsoft.SqlServer.Replication.Article.Remove%2A> method.</span></span>  
  
7.  <span data-ttu-id="9d180-141">Fermez toutes les connexions.</span><span class="sxs-lookup"><span data-stu-id="9d180-141">Close all connections.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d180-142">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9d180-142">See Also</span></span>  
 <span data-ttu-id="9d180-143">[Ajouter et supprimer des articles de publications existantes](add-articles-to-and-drop-articles-from-existing-publications.md) </span><span class="sxs-lookup"><span data-stu-id="9d180-143">[Add Articles to and Drop Articles from Existing Publications](add-articles-to-and-drop-articles-from-existing-publications.md) </span></span>  
 [<span data-ttu-id="9d180-144">Replication System Stored Procedures Concepts</span><span class="sxs-lookup"><span data-stu-id="9d180-144">Replication System Stored Procedures Concepts</span></span>](../concepts/replication-system-stored-procedures-concepts.md)  
  
  
