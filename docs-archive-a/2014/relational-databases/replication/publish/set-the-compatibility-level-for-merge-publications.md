---
title: Définir le niveau de compatibilité des publications de fusion | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- compatibility [SQL Server], replication
- backward compatibility [SQL Server], replication
- publications [SQL Server replication], backward compatibility
ms.assetid: db47ac73-948b-4d77-b272-bb3565135ea5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 04ad80b0c99e7282ff2acfa459a08665efbdee1c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614505"
---
# <a name="set-the-compatibility-level-for-merge-publications"></a><span data-ttu-id="4d2be-102">Définir le niveau de compatibilité pour les publications de fusion</span><span class="sxs-lookup"><span data-stu-id="4d2be-102">Set the Compatibility Level for Merge Publications</span></span>
  <span data-ttu-id="4d2be-103">Cette rubrique explique comment définir le niveau de compatibilité pour les publications de fusion dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4d2be-103">This topic describes how to set the compatibility level for merge publications in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="4d2be-104">La réplication de fusion utilise le niveau de compatibilité de publication pour déterminer les fonctionnalités qui peuvent être utilisées par des publications dans une base de données particulière.</span><span class="sxs-lookup"><span data-stu-id="4d2be-104">Merge replication uses the publication compatibility level to determine which features can be used by publications in a given database.</span></span>  
  
 <span data-ttu-id="4d2be-105">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="4d2be-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="4d2be-106">**Pour définir le niveau de compatibilité des publications de fusion à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="4d2be-106">**To set the compatibility level for merge publications, using:**</span></span>  
  
     [<span data-ttu-id="4d2be-107">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4d2be-107">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="4d2be-108">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4d2be-108">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4d2be-109">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4d2be-109">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="4d2be-110">Définir le niveau de compatibilité sur la page **Types d'abonnés** de l'Assistant Nouvelle publication.</span><span class="sxs-lookup"><span data-stu-id="4d2be-110">Set the compatibility level on the **Subscriber Types** page of the New Publication Wizard.</span></span> <span data-ttu-id="4d2be-111">Pour plus d'informations sur l'accès à cet Assistant, consultez [Create a Publication](create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="4d2be-111">For more information on accessing this wizard, see [Create a Publication](create-a-publication.md).</span></span> <span data-ttu-id="4d2be-112">Après la création d'un instantané de publication, le niveau de compatibilité peut être augmenté, mais il ne peut pas être diminué.</span><span class="sxs-lookup"><span data-stu-id="4d2be-112">After a publication snapshot is created, the compatibility level can be increased but cannot be decreased.</span></span> <span data-ttu-id="4d2be-113">Augmentez le niveau de compatibilité dans la page **Général** de la boîte de dialogue **Propriétés de la publication - \<Publication>** .</span><span class="sxs-lookup"><span data-stu-id="4d2be-113">Increase the compatibility level on the **General** page of the **Publication Properties - \<Publication>** dialog box.</span></span> <span data-ttu-id="4d2be-114">Pour plus d'informations sur l'accès à cette boîte de dialogue, consultez [Afficher et modifier les propriétés d’un serveur de publication](view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="4d2be-114">For more information about accessing this dialog box, see [View and Modify Publication Properties](view-and-modify-publication-properties.md).</span></span> <span data-ttu-id="4d2be-115">Si vous augmentez le niveau de compatibilité de la publication, tous les abonnements existants sur les serveurs exécutant des versions antérieures au niveau de compatibilité ne peuvent plus se synchroniser.</span><span class="sxs-lookup"><span data-stu-id="4d2be-115">If you increase the publication compatibility level, any existing subscriptions at servers running versions prior to the compatibility level will no longer be able to synchronize.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4d2be-116">Le niveau de compatibilité ayant des implications sur d'autres propriétés de la publication et sur la détermination de la validité des propriétés des articles, ne modifiez pas le niveau de compatibilité ni d'autres propriétés dans la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="4d2be-116">Because the compatibility level has implications for other publication properties and for which article properties are valid, do not change the compatibility level and other properties in the same use of the dialog box.</span></span> <span data-ttu-id="4d2be-117">L'instantané pour la publication doit être régénéré après la modification de la propriété.</span><span class="sxs-lookup"><span data-stu-id="4d2be-117">The snapshot for the publication should be regenerated after the property is changed.</span></span>  
  
#### <a name="to-set-the-publication-compatibility-level"></a><span data-ttu-id="4d2be-118">Pour définir le niveau de compatibilité de la publication</span><span class="sxs-lookup"><span data-stu-id="4d2be-118">To set the publication compatibility level</span></span>  
  
-   <span data-ttu-id="4d2be-119">Sur la page **Types d'abonnés** de l'Assistant Nouvelle publication, sélectionnez les types d'abonnés que la publication doit prendre en charge.</span><span class="sxs-lookup"><span data-stu-id="4d2be-119">On the **Subscriber Types** page of the New Publication Wizard, select the types of Subscribers that the publication should support.</span></span>  
  
#### <a name="to-increase-the-publication-compatibility-level"></a><span data-ttu-id="4d2be-120">Pour augmenter le niveau de compatibilité de la publication</span><span class="sxs-lookup"><span data-stu-id="4d2be-120">To increase the publication compatibility level</span></span>  
  
-   <span data-ttu-id="4d2be-121">Dans la page **Général** de la boîte de dialogue **Propriétés de la publication - \<Publication>** , sélectionnez **Niveau de compatibilité**.</span><span class="sxs-lookup"><span data-stu-id="4d2be-121">On the **General** page of the **Publication Properties - \<Publication>** dialog box, select for **Compatibility level**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4d2be-122">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4d2be-122">Using Transact-SQL</span></span>  
 <span data-ttu-id="4d2be-123">Le niveau de compatibilité d'une publication de fusion peut être défini par programme au moment de la création d'une publication ou être modifié par programme ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="4d2be-123">The compatibility level for a merge publication can either be set programmatically when a publication is created or modified programmatically at a later time.</span></span> <span data-ttu-id="4d2be-124">Vous pouvez utiliser des procédures stockées de réplication pour définir ou modifier cette propriété de publication.</span><span class="sxs-lookup"><span data-stu-id="4d2be-124">You can use replication stored procedures to set or change this publication property.</span></span>  
  
#### <a name="to-set-the-publication-compatibility-level-for-a-merge-publication"></a><span data-ttu-id="4d2be-125">Pour définir le niveau de compatibilité d'une publication de fusion</span><span class="sxs-lookup"><span data-stu-id="4d2be-125">To set the publication compatibility level for a merge publication</span></span>  
  
1.  <span data-ttu-id="4d2be-126">Sur le serveur de publication, exécutez [sp_addmergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addmergepublication-transact-sql), en spécifiant une valeur pour **@publication_compatibility_level** pour que la publication soit compatible avec les versions antérieures de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4d2be-126">At the Publisher, execute [sp_addmergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addmergepublication-transact-sql), specifying a value for **@publication_compatibility_level** to make the publication compatible with older versions of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4d2be-127">Pour plus d’informations, voir [Create a Publication](create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="4d2be-127">For more information, see [Create a Publication](create-a-publication.md).</span></span>  
  
#### <a name="to-change-the-publication-compatibility-level-of-a-merge-publication"></a><span data-ttu-id="4d2be-128">Pour modifier le niveau de compatibilité d'une publication de fusion</span><span class="sxs-lookup"><span data-stu-id="4d2be-128">To change the publication compatibility level of a merge publication</span></span>  
  
1.  <span data-ttu-id="4d2be-129">Exécutez [sp_changemergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql), en spécifiant **publication_compatibility_level** pour **@property** et le niveau de compatibilité de publication approprié pour **@value** .</span><span class="sxs-lookup"><span data-stu-id="4d2be-129">Execute [sp_changemergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql), specifying **publication_compatibility_level** for **@property** and the appropriate publication compatibility level for **@value**.</span></span>  
  
#### <a name="to-determine-the-publication-compatibility-level-of-a-merge-publication"></a><span data-ttu-id="4d2be-130">Pour déterminer le niveau de compatibilité d'une publication de fusion</span><span class="sxs-lookup"><span data-stu-id="4d2be-130">To determine the publication compatibility level of a merge publication</span></span>  
  
1.  <span data-ttu-id="4d2be-131">Exécutez [sp_helpmergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpmergepublication-transact-sql), en spécifiant la publication souhaitée.</span><span class="sxs-lookup"><span data-stu-id="4d2be-131">Execute [sp_helpmergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpmergepublication-transact-sql), specifying the desired publication.</span></span>  
  
2.  <span data-ttu-id="4d2be-132">Recherchez le niveau de compatibilité de la publication dans la colonne **backward_comp_level** du jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="4d2be-132">Locate the publication compatibility level in the **backward_comp_level** column in the result set.</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="4d2be-133">Exemples (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="4d2be-133">Examples (Transact-SQL)</span></span>  
 <span data-ttu-id="4d2be-134">Cet exemple crée une publication de fusion et définit son niveau de compatibilité.</span><span class="sxs-lookup"><span data-stu-id="4d2be-134">This example creates a merge publication and sets the publication compatibility level.</span></span>  
  
```  
-- To avoid storing the login and password in the script file, the values   
-- are passed into SQLCMD as scripting variables. For information about   
-- how to use scripting variables on the command line and in SQL Server  
-- Management Studio, see the "Executing Replication Scripts" section in  
-- the topic "Programming Replication Using System Stored Procedures".  
  
--Add a new merge publication.  
DECLARE @publicationDB AS sysname;  
DECLARE @publication AS sysname;  
DECLARE @login AS sysname;  
DECLARE @password AS sysname;  
SET @publicationDB = N'AdventureWorks2012';   
SET @publication = N'AdvWorksSalesOrdersMerge'   
SET @login = $(Login);  
SET @password = $(Password);  
  
-- Create a new merge publication.   
USE [AdventureWorks2012]  
EXEC sp_addmergepublication   
@publication = @publication,   
-- Set the compatibility level to SQL Server 2014.  
@publication_compatibility_level = '120RTM';   
  
-- Create the snapshot job for the publication.  
EXEC sp_addpublication_snapshot   
@publication = @publication,  
@job_login = @login,  
@job_password = @password;  
GO  
```  
  
 <span data-ttu-id="4d2be-135">Cet exemple modifie le niveau de compatibilité d'une publication de fusion</span><span class="sxs-lookup"><span data-stu-id="4d2be-135">This example changes the publication compatibility level for the merge publication.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4d2be-136">La modification du niveau de compatibilité de la publication peut être interdite si la publication utilise une fonctionnalité qui requiert un niveau de compatibilité particulier.</span><span class="sxs-lookup"><span data-stu-id="4d2be-136">Changing the publication compatibility level might not be allowed if the publication uses any features that require a particular compatibility level.</span></span> <span data-ttu-id="4d2be-137">Pour plus d’informations, consultez [Compatibilité descendante de la réplication](../replication-backward-compatibility.md).</span><span class="sxs-lookup"><span data-stu-id="4d2be-137">For more information, see [Replication Backward Compatibility](../replication-backward-compatibility.md).</span></span>  
  
```  
DECLARE @publication AS sysname;  
SET @publication = N'AdvWorksSalesOrdersMerge' ;  
  
-- Change the publication compatibility level to   
-- SQL Server 2012.  
EXEC sp_changemergepublication   
@publication = @publication,   
@property = N'publication_compatibility_level',   
@value = N'110RTM';  
GO  
  
```  
  
 <span data-ttu-id="4d2be-138">Cet exemple retourne le niveau de compatibilité actuel de la publication de fusion</span><span class="sxs-lookup"><span data-stu-id="4d2be-138">This example returns the current publication compatibility level for the merge publication.</span></span>  
  
```  
DECLARE @publication AS sysname;  
SET @publication = N'AdvWorksSalesOrdersMerge' ;  
EXEC sp_helpmergepublication   
@publication = @publication;  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="4d2be-139">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4d2be-139">See Also</span></span>  
 [<span data-ttu-id="4d2be-140">Créer une publication</span><span class="sxs-lookup"><span data-stu-id="4d2be-140">Create a Publication</span></span>](create-a-publication.md)  
  
  
