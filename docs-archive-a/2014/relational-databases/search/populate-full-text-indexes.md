---
title: Alimenter des index de recherche en texte intégral | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- index populations [full-text search]
- incremental populations [full-text search]
- populations [full-text search]
- full-text search [SQL Server], populations
- crawls [full-text search]
- automatic full-text index updates
- change tracking-based populations [full-text search]
- manual updates [full-text search]
- manual populations [full-text search]
- auto populations [full-text search]
- full-text indexes [SQL Server], key column
- full populations [full-text search]
- full-text indexes [SQL Server], populations
ms.assetid: 76767b20-ef55-49ce-8dc4-e77cb8ff618a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9ab93a3514fa260c8c3836da85c767da3c3051a1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612742"
---
# <a name="populate-full-text-indexes"></a><span data-ttu-id="bd432-102">Alimenter des index de recherche en texte intégral</span><span class="sxs-lookup"><span data-stu-id="bd432-102">Populate Full-Text Indexes</span></span>
  <span data-ttu-id="bd432-103">La création et la maintenance d’un index de recherche en texte intégral impliquent le remplissage de l’index à l’aide d’un processus appelé *alimentation* (également appelé *analyse*).</span><span class="sxs-lookup"><span data-stu-id="bd432-103">Creating and maintaining a full-text index involves populating the index by using a process called a *population* (also known as a *crawl*).</span></span>  
  
##  <a name="types-of-population"></a><a name="types"></a><span data-ttu-id="bd432-104">Types de remplissage</span><span class="sxs-lookup"><span data-stu-id="bd432-104">Types of Population</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="bd432-105">prend en charge les types de remplissage suivants : alimentation complète, alimentation automatique ou manuelle basée sur le suivi des modifications et alimentation incrémentielle basée sur l’horodatage.</span><span class="sxs-lookup"><span data-stu-id="bd432-105">supports the following types of population: full population, change tracking-based automatic or manual population, and incremental timestamp-based population.</span></span>  
  
### <a name="full-population"></a><span data-ttu-id="bd432-106">Alimentation complète</span><span class="sxs-lookup"><span data-stu-id="bd432-106">Full Population</span></span>  
 <span data-ttu-id="bd432-107">Au cours d'une alimentation complète, les entrées d'index sont créées pour toutes les lignes d'une table ou d'une vue indexée.</span><span class="sxs-lookup"><span data-stu-id="bd432-107">During a full population, index entries are built for all the rows of a table or indexed view.</span></span> <span data-ttu-id="bd432-108">Une alimentation complète d'un index de recherche en texte intégral crée des entrées d'index pour toutes les lignes de la table de base ou de la vue indexée.</span><span class="sxs-lookup"><span data-stu-id="bd432-108">A full population of a full-text index, builds index entries for all the rows of the base table or indexed view.</span></span>  
  
 <span data-ttu-id="bd432-109">Par défaut, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alimente complètement un nouvel index de recherche en texte intégral dès que celui-ci est créé.</span><span class="sxs-lookup"><span data-stu-id="bd432-109">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] populates a new full-text index fully as soon as it is created.</span></span> <span data-ttu-id="bd432-110">Cependant, une alimentation complète peut consommer beaucoup de ressources.</span><span class="sxs-lookup"><span data-stu-id="bd432-110">However, a full population can consume a significant amount of resources.</span></span> <span data-ttu-id="bd432-111">Par conséquent, si vous créez un index de recherche en texte intégral pendant une période de pointe, il est recommandé de reporter l’alimentation complète à une période creuse, en particulier si la table de base d’un index de recherche en texte intégral est volumineuse.</span><span class="sxs-lookup"><span data-stu-id="bd432-111">Therefore, when creating a full-text index during peak periods, it is often a best practice to delay the full population until an off-peak time, particularly if the base table of an full-text index is large.</span></span> <span data-ttu-id="bd432-112">Toutefois, le catalogue de texte intégral auquel l'index appartient n'est pas utilisable tant que tous ses index de recherche en texte intégral ne sont pas alimentés.</span><span class="sxs-lookup"><span data-stu-id="bd432-112">However, the full-text catalog to which the index belongs is not usable until all of its full-text indexes are populated.</span></span> <span data-ttu-id="bd432-113">Pour créer un index de recherche en texte intégral sans l'alimenter immédiatement, spécifiez la clause CHANGE_TRACKING OFF, NO POPULATION dans l'instruction CREATE FULLTEXT INDEX.</span><span class="sxs-lookup"><span data-stu-id="bd432-113">To create a full-text index without populating it immediately, specify the CHANGE_TRACKING OFF, NO POPULATION clause in the CREATE FULLTEXT INDEX statement.</span></span> <span data-ttu-id="bd432-114">Si vous spécifiez CHANGE_TRACKING MANUAL, le Moteur d'indexation et de recherche en texte intégral utilise l'instruction.</span><span class="sxs-lookup"><span data-stu-id="bd432-114">If you specify CHANGE_TRACKING MANUAL, the Full-Text Engine uses statement.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="bd432-115">ne remplit pas le nouvel index de recherche en texte intégral tant que vous n’exécutez pas une instruction ALTER FULLTEXT INDEX à l’aide de la clause START FULL POPULATION ou START INCREMENTAL POPULATION.</span><span class="sxs-lookup"><span data-stu-id="bd432-115">will not populate the new full-text index until you execute an ALTER FULLTEXT INDEX statement using the START FULL POPULATION or START INCREMENTAL POPULATION clause.</span></span> <span data-ttu-id="bd432-116">Pour plus d'informations, consultez l'exemple « A.</span><span class="sxs-lookup"><span data-stu-id="bd432-116">For more information, see examples "A.</span></span> <span data-ttu-id="bd432-117">Création d'un index de recherche en texte intégral sans exécuter une alimentation complète » et l'exemple « B.</span><span class="sxs-lookup"><span data-stu-id="bd432-117">Creating a full-text index without running a full population" and "B.</span></span> <span data-ttu-id="bd432-118">Exécution d'une alimentation complète sur une table », présentés ultérieurement dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="bd432-118">Running a full population on table," later in this topic.</span></span>  
  

  
### <a name="change-tracking-based-population"></a><span data-ttu-id="bd432-119">Alimentation basée sur le suivi des modifications</span><span class="sxs-lookup"><span data-stu-id="bd432-119">Change Tracking-Based Population</span></span>  
 <span data-ttu-id="bd432-120">Vous pouvez éventuellement utiliser le suivi des modifications pour procéder à la gestion d'un index de recherche en texte intégral après son alimentation complète initiale.</span><span class="sxs-lookup"><span data-stu-id="bd432-120">Optionally, you can use change tracking to maintain a full-text index after its initial full population.</span></span> <span data-ttu-id="bd432-121">La surcharge associée au suivi des modifications est réduite, car [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] gère une table dans laquelle il suit les modifications apportées à la table de base depuis la dernière alimentation.</span><span class="sxs-lookup"><span data-stu-id="bd432-121">There is a small overhead associated with change tracking because [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] maintains a table in which it tracks changes to the base table since the last population.</span></span> <span data-ttu-id="bd432-122">Lorsque le suivi des modifications est utilisé, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] gère un enregistrement des lignes de la table de base ou de la vue indexée ayant été modifiées par des opérations de mise à jour, de suppression ou d'insertion.</span><span class="sxs-lookup"><span data-stu-id="bd432-122">When change tracking is used, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] maintains a record of the rows in the base table or indexed view that have been modified by updates, deletes, or inserts.</span></span> <span data-ttu-id="bd432-123">Les modifications apportées aux données via WRITETEXT et UPDATETEXT ne sont pas répercutées dans l'index de recherche en texte intégral et ne sont pas prises en compte par le suivi des modifications.</span><span class="sxs-lookup"><span data-stu-id="bd432-123">Data changes through WRITETEXT and UPDATETEXT are not reflected in the full-text index, and are not picked up with change tracking.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bd432-124">Pour les tables qui contiennent une colonne `timestamp`, vous pouvez utiliser des alimentations incrémentielles.</span><span class="sxs-lookup"><span data-stu-id="bd432-124">For tables containing a `timestamp` column, you can use incremental populations.</span></span>  
  
 <span data-ttu-id="bd432-125">Lorsque le suivi des modifications est activé pendant la création d’index, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alimente complètement le nouvel index de recherche en texte intégral juste après sa création.</span><span class="sxs-lookup"><span data-stu-id="bd432-125">When change tracking is enabled during index creation, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fully populates the new full-text index immediately after it is created.</span></span> <span data-ttu-id="bd432-126">Ensuite, les modifications font l'objet d'un suivi et propagées à l'index de recherche en texte intégral.</span><span class="sxs-lookup"><span data-stu-id="bd432-126">Thereafter, changes are tracked and propagated to the full-text index.</span></span> <span data-ttu-id="bd432-127">Il existe deux types de suivi des modifications : automatique (option CHANGE_TRACKING AUTO) et manuel (option CHANGE_TRACKING MANUAL).</span><span class="sxs-lookup"><span data-stu-id="bd432-127">There are two types of change tracking, automatic (CHANGE_TRACKING AUTO option) and manual (CHANGE_TRACKING MANUAL option).</span></span> <span data-ttu-id="bd432-128">Le suivi des modifications automatique est le comportement par défaut.</span><span class="sxs-lookup"><span data-stu-id="bd432-128">Automatic change tracking is the default behavior.</span></span>  
  
 <span data-ttu-id="bd432-129">Le type de suivi des modifications détermine la façon dont l'index de recherche en texte intégral est alimenté, comme expliqué ci-après.</span><span class="sxs-lookup"><span data-stu-id="bd432-129">The type of change tracking determines how the full-text index is populated, as follows:</span></span>  
  
-   <span data-ttu-id="bd432-130">Alimentation automatique</span><span class="sxs-lookup"><span data-stu-id="bd432-130">Automatic population</span></span>  
  
     <span data-ttu-id="bd432-131">Par défaut, ou si vous spécifiez CHANGE_TRACKING AUTO, le Moteur d'indexation et de recherche en texte intégral utilise l'alimentation automatique sur l'index de recherche en texte intégral.</span><span class="sxs-lookup"><span data-stu-id="bd432-131">By default, or if you specify CHANGE_TRACKING AUTO, the Full-Text Engine uses automatic population on the full-text index.</span></span> <span data-ttu-id="bd432-132">Une fois l'alimentation complète initiale terminée, les données modifiées dans la table de base font l'objet d'un suivi, et ces modifications sont propagées automatiquement.</span><span class="sxs-lookup"><span data-stu-id="bd432-132">After the initial full population completes, changes are tracked as data is modified in the base table, and the tracked changes are propagated automatically.</span></span> <span data-ttu-id="bd432-133">L'index de recherche en texte intégral étant toutefois mis à jour en arrière-plan, il se peut que les modifications propagées ne soient pas répercutées immédiatement dans l'index.</span><span class="sxs-lookup"><span data-stu-id="bd432-133">The full-text index is updated in the background, however, so propagated changes might not be reflected immediately in the index.</span></span>  
  
     <span data-ttu-id="bd432-134">**Pour configurer le suivi des modifications avec remplissage automatique**</span><span class="sxs-lookup"><span data-stu-id="bd432-134">**To set up tracking changes with automatic population**</span></span>  
  
    -   <span data-ttu-id="bd432-135">[CREATE FULLTEXT INDEX](/sql/t-sql/statements/create-fulltext-index-transact-sql) ... WITH CHANGE_TRACKING AUTO</span><span class="sxs-lookup"><span data-stu-id="bd432-135">[CREATE FULLTEXT INDEX](/sql/t-sql/statements/create-fulltext-index-transact-sql) ... WITH CHANGE_TRACKING AUTO</span></span>  
  
    -   <span data-ttu-id="bd432-136">[ALTER FULLTEXT INDEX](/sql/t-sql/statements/alter-fulltext-index-transact-sql) ... SET CHANGE_TRACKING AUTO</span><span class="sxs-lookup"><span data-stu-id="bd432-136">[ALTER FULLTEXT INDEX](/sql/t-sql/statements/alter-fulltext-index-transact-sql) ... SET CHANGE_TRACKING AUTO</span></span>  
  
     <span data-ttu-id="bd432-137">Pour plus d'informations, consultez l'exemple « E.</span><span class="sxs-lookup"><span data-stu-id="bd432-137">For more information, see example "E.</span></span> <span data-ttu-id="bd432-138">Modification d'un index de recherche en texte intégral pour qu'il utilise le suivi des modifications automatique », présenté ultérieurement dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="bd432-138">Altering a full-text index to use automatic change tracking," later in this topic.</span></span>  
  
-   <span data-ttu-id="bd432-139">Alimentation manuelle</span><span class="sxs-lookup"><span data-stu-id="bd432-139">Manual population</span></span>  
  
     <span data-ttu-id="bd432-140">Si vous spécifiez CHANGE_TRACKING MANUAL, le moteur d'indexation et de recherche en texte intégral utilise le remplissage manuel sur l'index de recherche en texte intégral.</span><span class="sxs-lookup"><span data-stu-id="bd432-140">If you specify CHANGE_TRACKING MANUAL, the Full-Text Engine uses manual population on the full-text index.</span></span> <span data-ttu-id="bd432-141">Une fois le remplissage complet initial terminé, les données modifiées dans la table de base font l'objet d'un suivi.</span><span class="sxs-lookup"><span data-stu-id="bd432-141">After the initial full population completes, changes are tracked as data is modified in the base table.</span></span> <span data-ttu-id="bd432-142">Toutefois, elles ne sont pas propagées à l’index de recherche en texte intégral tant que vous n’exécutez pas une instruction ALTER FULLTEXT INDEX ... START UPDATE POPULATION .</span><span class="sxs-lookup"><span data-stu-id="bd432-142">However, they are not propagated to the full-text index until you execute an ALTER FULLTEXT INDEX ... START UPDATE POPULATION statement.</span></span> <span data-ttu-id="bd432-143">Vous pouvez utiliser l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour appeler régulièrement cette instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bd432-143">You can use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to call this [!INCLUDE[tsql](../../includes/tsql-md.md)] statement periodically.</span></span>  
  
     <span data-ttu-id="bd432-144">**Pour commencer le suivi des modifications avec remplissage manuel**</span><span class="sxs-lookup"><span data-stu-id="bd432-144">**To start tracking changes with manual population**</span></span>  
  
    -   <span data-ttu-id="bd432-145">[CREATE FULLTEXT INDEX](/sql/t-sql/statements/create-fulltext-index-transact-sql) ... WITH CHANGE_TRACKING MANUAL</span><span class="sxs-lookup"><span data-stu-id="bd432-145">[CREATE FULLTEXT INDEX](/sql/t-sql/statements/create-fulltext-index-transact-sql) ... WITH CHANGE_TRACKING MANUAL</span></span>  
  
    -   <span data-ttu-id="bd432-146">[ALTER FULLTEXT INDEX](/sql/t-sql/statements/alter-fulltext-index-transact-sql) ... SET CHANGE_TRACKING MANUAL</span><span class="sxs-lookup"><span data-stu-id="bd432-146">[ALTER FULLTEXT INDEX](/sql/t-sql/statements/alter-fulltext-index-transact-sql) ... SET CHANGE_TRACKING MANUAL</span></span>  
  
     <span data-ttu-id="bd432-147">Pour plus d'informations, consultez l'exemple « C.</span><span class="sxs-lookup"><span data-stu-id="bd432-147">For more information, see examples "C.</span></span> <span data-ttu-id="bd432-148">Création d'un index de recherche en texte intégral avec le suivi des modifications manuel » et l'exemple « D.</span><span class="sxs-lookup"><span data-stu-id="bd432-148">Creating a full-text index with manual change tracking" and "D.</span></span> <span data-ttu-id="bd432-149">Exécution d'un remplissage manuel », présentés ultérieurement dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="bd432-149">Running a manual population," later in this topic.</span></span>  
  
 <span data-ttu-id="bd432-150">**Pour désactiver le suivi des modifications**</span><span class="sxs-lookup"><span data-stu-id="bd432-150">**To turn off change tracking**</span></span>  
  
-   <span data-ttu-id="bd432-151">[CREATE FULLTEXT INDEX](/sql/t-sql/statements/create-fulltext-index-transact-sql) ... WITH CHANGE_TRACKING OFF</span><span class="sxs-lookup"><span data-stu-id="bd432-151">[CREATE FULLTEXT INDEX](/sql/t-sql/statements/create-fulltext-index-transact-sql) ... WITH CHANGE_TRACKING OFF</span></span>  
  
-   <span data-ttu-id="bd432-152">[ALTER FULLTEXT INDEX](/sql/t-sql/statements/alter-fulltext-index-transact-sql) ... SET CHANGE_TRACKING OFF</span><span class="sxs-lookup"><span data-stu-id="bd432-152">[ALTER FULLTEXT INDEX](/sql/t-sql/statements/alter-fulltext-index-transact-sql) ... SET CHANGE_TRACKING OFF</span></span>  
  

  
### <a name="incremental-timestamp-based-population"></a><span data-ttu-id="bd432-153">Alimentation incrémentielle basée sur un horodateur</span><span class="sxs-lookup"><span data-stu-id="bd432-153">Incremental Timestamp-Based Population</span></span>  
 <span data-ttu-id="bd432-154">L'alimentation incrémentielle est un autre mécanisme permettant d'alimenter manuellement un index de recherche en texte intégral.</span><span class="sxs-lookup"><span data-stu-id="bd432-154">An incremental population is an alternative mechanism for manually populating a full-text index.</span></span> <span data-ttu-id="bd432-155">Vous pouvez exécuter une alimentation incrémentielle pour un index de recherche en texte intégral pour lequel CHANGE_TRACKING a la valeur MANUAL ou OFF.</span><span class="sxs-lookup"><span data-stu-id="bd432-155">You can run an incremental population for a full-text index that has CHANGE_TRACKING set to MANUAL or OFF.</span></span> <span data-ttu-id="bd432-156">Si la première alimentation d'un index de recherche en texte intégral est une alimentation incrémentielle, elle indexe toutes les lignes, ce qui équivaut à une alimentation complète.</span><span class="sxs-lookup"><span data-stu-id="bd432-156">If the first population on a full-text index is an incremental population, it indexes all rows, making it equivalent to a full population.</span></span>  
  
 <span data-ttu-id="bd432-157">Pour permettre une alimentation incrémentielle, la table indexée doit disposer d'une colonne dont le type de données est `timestamp`.</span><span class="sxs-lookup"><span data-stu-id="bd432-157">The requirement for incremental population is that the indexed table must have a column of the `timestamp` data type.</span></span> <span data-ttu-id="bd432-158">S'il n'existe pas de colonne de type `timestamp`, l'alimentation incrémentielle ne peut s'effectuer.</span><span class="sxs-lookup"><span data-stu-id="bd432-158">If a `timestamp` column does not exist, incremental population cannot be performed.</span></span> <span data-ttu-id="bd432-159">Une demande d'alimentation incrémentielle dans une table sans colonne de type `timestamp` entraîne une alimentation complète.</span><span class="sxs-lookup"><span data-stu-id="bd432-159">A request for incremental population on a table without a `timestamp` column results in a full population operation.</span></span> <span data-ttu-id="bd432-160">En outre, si des métadonnées concernant l'index de recherche en texte intégral de la table ont été modifiées depuis la dernière alimentation, les demandes d'alimentation incrémentielle sont implémentées comme des alimentations complètes.</span><span class="sxs-lookup"><span data-stu-id="bd432-160">Also, if any metadata that affects the full-text index for the table has changed since the last population, incremental population requests are implemented as full populations.</span></span> <span data-ttu-id="bd432-161">Cela concerne les modifications de métadonnées provoquées par des modifications de définitions de colonne, d'index ou d'index de recherche en texte intégral.</span><span class="sxs-lookup"><span data-stu-id="bd432-161">This includes metadata changes caused by altering any column, index, or full-text index definitions.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="bd432-162">utilise la colonne `timestamp` pour identifier des lignes qui ont été modifiées depuis la dernière alimentation.</span><span class="sxs-lookup"><span data-stu-id="bd432-162">uses the `timestamp` column to identify rows that have changed since the last population.</span></span> <span data-ttu-id="bd432-163">L'alimentation incrémentielle met alors à jour l'index de recherche en texte intégral avec les lignes ajoutées, supprimées ou modifiées après la dernière alimentation ou pendant l'exécution de cette dernière.</span><span class="sxs-lookup"><span data-stu-id="bd432-163">The incremental population then updates the full-text index for rows added, deleted, or modified after the last population, or while the last population was in progress.</span></span> <span data-ttu-id="bd432-164">Si une table fait l'objet d'un nombre important d'insertions, l'alimentation incrémentielle peut s'avérer plus efficace que l'alimentation manuelle.</span><span class="sxs-lookup"><span data-stu-id="bd432-164">If a table experiences a high volume of inserts, using incremental population can be more efficient that using manual population.</span></span>  
  
 <span data-ttu-id="bd432-165">À la fin d'une alimentation, le Moteur d'indexation et de recherche en texte intégral enregistre une nouvelle valeur `timestamp`.</span><span class="sxs-lookup"><span data-stu-id="bd432-165">At the end of a population, the Full-Text Engine records a new `timestamp` value.</span></span> <span data-ttu-id="bd432-166">Il s'agit de la plus grande valeur `timestamp` rencontrée par l'utilitaire de rassemblement SQL.</span><span class="sxs-lookup"><span data-stu-id="bd432-166">This value is the largest `timestamp` value that SQL Gatherer has encountered.</span></span> <span data-ttu-id="bd432-167">Cette valeur sera utilisée au démarrage de la prochaine alimentation incrémentielle.</span><span class="sxs-lookup"><span data-stu-id="bd432-167">This value will be used when a subsequent incremental population starts.</span></span>  
  
 <span data-ttu-id="bd432-168">Pour exécuter une alimentation incrémentielle, exécutez une instruction ALTER FULLTEXT INDEX avec la clause START INCREMENTAL POPULATION.</span><span class="sxs-lookup"><span data-stu-id="bd432-168">To run an incremental population, execute an ALTER FULLTEXT INDEX statement using the START INCREMENTAL POPULATION clause.</span></span>  
  

  
##  <a name="examples-of-populating-full-text-indexes"></a><a name="examples"></a><span data-ttu-id="bd432-169">Exemples de remplissage d’index de recherche en texte intégral</span><span class="sxs-lookup"><span data-stu-id="bd432-169">Examples of Populating Full-Text Indexes</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bd432-170">Les exemples de cette section utilisent la table `Production.Document` ou `HumanResources.JobCandidate` de l'exemple de base de données `AdventureWorks` .</span><span class="sxs-lookup"><span data-stu-id="bd432-170">The examples in this section use the `Production.Document` or `HumanResources.JobCandidate` table of the `AdventureWorks` sample database.</span></span>  
  
### <a name="a-creating-a-full-text-index-without-running-a-full-population"></a><span data-ttu-id="bd432-171">R.</span><span class="sxs-lookup"><span data-stu-id="bd432-171">A.</span></span> <span data-ttu-id="bd432-172">Création d'un index de recherche en texte intégral sans exécuter une alimentation complète</span><span class="sxs-lookup"><span data-stu-id="bd432-172">Creating a full-text index without running a full population</span></span>  
 <span data-ttu-id="bd432-173">L'exemple ci-après crée un index de recherche en texte intégral sur la table `Production.Document` de l'exemple de base de données `AdventureWorks` .</span><span class="sxs-lookup"><span data-stu-id="bd432-173">The following example creates a full-text index on the `Production.Document` table of the `AdventureWorks` sample database.</span></span> <span data-ttu-id="bd432-174">Cet exemple utilise WITH CHANGE_TRACKING OFF, NO POPULATION pour différer l'alimentation complète initiale.</span><span class="sxs-lookup"><span data-stu-id="bd432-174">This example uses WITH CHANGE_TRACKING OFF, NO POPULATION to delay the initial full population.</span></span>  
  
```  
CREATE UNIQUE INDEX ui_ukDoc ON Production.Document(DocumentID);  
CREATE FULLTEXT CATALOG AW_Production_FTCat;  
CREATE FULLTEXT INDEX ON Production.Document  
(  
    Document                         --Full-text index column name   
        TYPE COLUMN FileExtension    --Name of column that contains file type information  
        Language 1033                 --1033 is LCID for the English language  
)  
    KEY INDEX ui_ukDoc  
    ON AW_Production_FTCat  
    WITH CHANGE_TRACKING OFF, NO POPULATION;  
GO  
  
```  
  
### <a name="b-running-a-full-population-on-table"></a><span data-ttu-id="bd432-175">B.</span><span class="sxs-lookup"><span data-stu-id="bd432-175">B.</span></span> <span data-ttu-id="bd432-176">Exécution d'une alimentation complète sur une table</span><span class="sxs-lookup"><span data-stu-id="bd432-176">Running a full population on table</span></span>  
 <span data-ttu-id="bd432-177">L'exemple ci-après exécute une alimentation complète sur la table `Production.Document` de l'exemple de base de données `AdventureWorks` .</span><span class="sxs-lookup"><span data-stu-id="bd432-177">The following example runs a full population on the `Production.Document` table of the `AdventureWorks` sample database.</span></span>  
  
```  
ALTER FULLTEXT INDEX ON Production.Document  
   START FULL POPULATION;  
```  
  
### <a name="c-creating-a-full-text-index-with-manual-change-tracking"></a><span data-ttu-id="bd432-178">C.</span><span class="sxs-lookup"><span data-stu-id="bd432-178">C.</span></span> <span data-ttu-id="bd432-179">Création d'un index de recherche en texte intégral avec le suivi manuel des modifications</span><span class="sxs-lookup"><span data-stu-id="bd432-179">Creating a full-text index with manual change tracking</span></span>  
 <span data-ttu-id="bd432-180">L'exemple ci-après crée un index de recherche en texte intégral qui utilisera le suivi des modifications avec alimentation manuelle sur la table `HumanResources.JobCandidate` de l'exemple de base de données `AdventureWorks` .</span><span class="sxs-lookup"><span data-stu-id="bd432-180">The following example creates a full-text index that will use change tracking with manual population on the `HumanResources.JobCandidate` table of the `AdventureWorks` sample database.</span></span>  
  
```  
USE AdventureWorks;  
GO  
CREATE UNIQUE INDEX ui_ukJobCand ON HumanResources.JobCandidate(JobCandidateID);  
CREATE FULLTEXT CATALOG ft AS DEFAULT;  
CREATE FULLTEXT INDEX ON HumanResources.JobCandidate(Resume)   
   KEY INDEX ui_ukJobCand   
   WITH CHANGE_TRACKING=MANUAL;  
GO  
```  
  
### <a name="d-running-a-manual-population"></a><span data-ttu-id="bd432-181">D.</span><span class="sxs-lookup"><span data-stu-id="bd432-181">D.</span></span> <span data-ttu-id="bd432-182">Exécution d'une alimentation manuelle</span><span class="sxs-lookup"><span data-stu-id="bd432-182">Running a manual population</span></span>  
 <span data-ttu-id="bd432-183">L'exemple ci-après exécute une alimentation manuelle sur l'index de recherche en texte intégral faisant l'objet d'un suivi des modifications, sur la table `HumanResources.JobCandidate` de l'exemple de base de données `AdventureWorks` .</span><span class="sxs-lookup"><span data-stu-id="bd432-183">The following example runs a manual population on the change-tracked full-text index of the `HumanResources.JobCandidate` table of the `AdventureWorks` sample database.</span></span>  
  
```  
USE AdventureWorks;  
GO  
ALTER FULLTEXT INDEX ON HumanResources.JobCandidate START UPDATE POPULATION;  
GO  
```  
  
### <a name="e-altering-a-full-text-index-to-use-automatic-change-tracking"></a><span data-ttu-id="bd432-184">E.</span><span class="sxs-lookup"><span data-stu-id="bd432-184">E.</span></span> <span data-ttu-id="bd432-185">Modification d'un index de recherche en texte intégral pour qu'il utilise le suivi automatique des modifications</span><span class="sxs-lookup"><span data-stu-id="bd432-185">Altering a full-text index to use automatic change tracking</span></span>  
 <span data-ttu-id="bd432-186">L'exemple ci-après modifie l'index de recherche en texte intégral de la table `HumanResources.JobCandidate` de l'exemple de base de données `AdventureWorks` pour qu'il utilise le suivi des modifications avec alimentation automatique.</span><span class="sxs-lookup"><span data-stu-id="bd432-186">The following example changes the full-text index of the `HumanResources.JobCandidate` table of the `AdventureWorks` sample database to use change tracking with automatic population.</span></span>  
  
```  
USE AdventureWorks;  
GO  
ALTER FULLTEXT INDEX ON HumanResources.JobCandidate SET CHANGE_TRACKING AUTO;  
GO   
```  
  

  
##  <a name="creating-or-changing-a-schedule-for-incremental-population"></a><a name="create"></a><span data-ttu-id="bd432-187">Création ou modification d’une planification pour l’alimentation incrémentielle</span><span class="sxs-lookup"><span data-stu-id="bd432-187">Creating or Changing a Schedule for Incremental Population</span></span>  
  
#### <a name="to-create-or-change-a-schedule-for-incremental-population-in-management-studio"></a><span data-ttu-id="bd432-188">Pour créer ou modifier une planification pour l'alimentation incrémentielle dans Management Studio</span><span class="sxs-lookup"><span data-stu-id="bd432-188">To create or change a schedule for incremental population in Management Studio</span></span>  
  
1.  <span data-ttu-id="bd432-189">Dans l'Explorateur d'objets, développez le serveur.</span><span class="sxs-lookup"><span data-stu-id="bd432-189">In Object Explorer, expand the server.</span></span>  
  
2.  <span data-ttu-id="bd432-190">Développez **Bases de données**, puis la base de données qui contient l’index de recherche en texte intégral.</span><span class="sxs-lookup"><span data-stu-id="bd432-190">Expand **Databases**, and then expand the database that contains the full-text index.</span></span>  
  
3.  <span data-ttu-id="bd432-191">Développez **Tables**.</span><span class="sxs-lookup"><span data-stu-id="bd432-191">Expand **Tables**.</span></span>  
  
 <span data-ttu-id="bd432-192">Cliquez avec le bouton droit sur la table sur laquelle l’index de recherche en texte intégral est défini, sélectionnez **Index de recherche en texte intégral**et, dans le menu contextuel **Index de recherche en texte intégral** , cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="bd432-192">Right-click the table on which the full-text index is defined, select **Full-Text index**, and on the **Full-Text index** context menu, click **Properties**.</span></span> <span data-ttu-id="bd432-193">La boîte de dialogue **Propriétés d’index de recherche en texte intégral** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="bd432-193">This opens the **Full-text index Properties** dialog box.</span></span>  
  
1.  <span data-ttu-id="bd432-194">Dans le volet **Sélectionner une page** , sélectionnez Planifications.</span><span class="sxs-lookup"><span data-stu-id="bd432-194">In the **Select a page** pane, select Schedules.</span></span>  
  
     <span data-ttu-id="bd432-195">Utilisez cette page pour créer ou gérer des planifications pour un travail de l'Agent SQL Server qui démarre une alimentation de table incrémentielle sur la table de base ou la vue indexée de l'index de recherche en texte intégral.</span><span class="sxs-lookup"><span data-stu-id="bd432-195">Use this page to create or manage schedules for a SQL Server Agent job that starts an incremental table population on the base table or indexed view of the full-text index.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="bd432-196">Si la table de base ou la vue ne contient pas une colonne du type de données `timestamp`, une alimentation complète est effectuée.</span><span class="sxs-lookup"><span data-stu-id="bd432-196">If the base table or view does not contain a column of the `timestamp` data type, a full population is performed.</span></span>  
  
     <span data-ttu-id="bd432-197">Les options disponibles sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="bd432-197">The options are as follows:</span></span>  
  
    -   <span data-ttu-id="bd432-198">Pour créer une planification, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="bd432-198">To create a new schedule, click **New**.</span></span>  
  
         <span data-ttu-id="bd432-199">La boîte de dialogue **Nouvelle planification de la table d’indexation de texte intégral** s’affiche pour vous permettre de créer une planification.</span><span class="sxs-lookup"><span data-stu-id="bd432-199">This opens the **New Full-Text Indexing Table Schedule** dialog box, where you can create a schedule.</span></span> <span data-ttu-id="bd432-200">Pour enregistrer la planification, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="bd432-200">To save the schedule, click **OK**.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="bd432-201">Un travail SQL Server Agent (démarrage de l’alimentation de table incrémentielle sur *nom_base_de_données*.*nom_table*) est associé à une nouvelle planification une fois que vous avez fermé la boîte de dialogue **Propriétés d’index de texte intégral** .</span><span class="sxs-lookup"><span data-stu-id="bd432-201">A SQL Server Agent job (Start Incremental Table Population on *database_name*.*table_name*) is associated with a new schedule after you exit the **Full-Text Index Properties** dialog box.</span></span> <span data-ttu-id="bd432-202">Si vous créez plusieurs planifications pour l'index de recherche en texte intégral, elles utilisent toutes le même travail.</span><span class="sxs-lookup"><span data-stu-id="bd432-202">If you create multiple schedules for the full-text index, they all use the same job.</span></span>  
  
    -   <span data-ttu-id="bd432-203">Pour modifier une planification, sélectionnez-la, puis cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="bd432-203">To change a schedule, select it and click **Edit**.</span></span>  
  
         <span data-ttu-id="bd432-204">La boîte de dialogue **Nouvelle planification de la table d’indexation de texte intégral** s’affiche pour vous permettre de modifier la planification.</span><span class="sxs-lookup"><span data-stu-id="bd432-204">This opens the **New Full-Text Indexing Table Schedule** dialog box, where you can modify the schedule.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="bd432-205">Pour plus d’informations sur la modification d’un travail, consultez [Modifier un travail](../../ssms/agent/modify-a-job.md).</span><span class="sxs-lookup"><span data-stu-id="bd432-205">For information about modifying a job, see [Modify a Job](../../ssms/agent/modify-a-job.md).</span></span>  
  
    -   <span data-ttu-id="bd432-206">Pour supprimer une planification, sélectionnez-la, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="bd432-206">To remove a schedule, select it and click **Delete**.</span></span>  
  
2.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  

  
##  <a name="troubleshooting-errors-in-a-full-text-population-crawl"></a><a name="crawl"></a><span data-ttu-id="bd432-207">Résolution des erreurs dans une alimentation de texte intégral (analyse)</span><span class="sxs-lookup"><span data-stu-id="bd432-207">Troubleshooting Errors in a Full-Text Population (Crawl)</span></span>  
 <span data-ttu-id="bd432-208">Lorsqu'une erreur se produit durant une analyse, la fonction d'analyse de la recherche en texte intégral crée et conserve un journal de l'analyse sous forme de fichier texte.</span><span class="sxs-lookup"><span data-stu-id="bd432-208">When an error occurs during a crawl, the Full-Text Search crawl logging facility creates and maintains a crawl log, which is a plain text file.</span></span> <span data-ttu-id="bd432-209">Chaque journal de l'analyse correspond à un catalogue de texte intégral particulier.</span><span class="sxs-lookup"><span data-stu-id="bd432-209">Each crawl log corresponds to a particular full-text catalog.</span></span> <span data-ttu-id="bd432-210">Par défaut, les journaux d'analyse d'une instance donnée (dans le cas présent, la première instance) sont situés dans le dossier %ProgramFiles%\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\LOG.</span><span class="sxs-lookup"><span data-stu-id="bd432-210">By default crawl logs for a given instance, in this case, the first instance, are located in %ProgramFiles%\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\LOG folder.</span></span> <span data-ttu-id="bd432-211">Le fichier journal de l'analyse respecte le modèle de dénomination suivant :</span><span class="sxs-lookup"><span data-stu-id="bd432-211">The crawl log file follows the following naming scheme:</span></span>  
  
 <span data-ttu-id="bd432-212">SQLFT \<DatabaseID> \<FullTextCatalogID> . LOG [ \<n> ]</span><span class="sxs-lookup"><span data-stu-id="bd432-212">SQLFT\<DatabaseID>\<FullTextCatalogID>.LOG[\<n>]</span></span>  
  
 <`DatabaseID`>  
 <span data-ttu-id="bd432-213">ID d'une base de données.</span><span class="sxs-lookup"><span data-stu-id="bd432-213">The ID of a database.</span></span><span data-ttu-id="bd432-214"> <`dbid`> est un nombre à cinq chiffres avec des zéros non significatifs.</span><span class="sxs-lookup"><span data-stu-id="bd432-214"> <`dbid`> is a five digit number with leading zeros.</span></span>  
  
 <`FullTextCatalogID`>  
 <span data-ttu-id="bd432-215">ID du catalogue de texte intégral.</span><span class="sxs-lookup"><span data-stu-id="bd432-215">Full-text catalog ID.</span></span><span data-ttu-id="bd432-216"> <`catid`> est un nombre à cinq chiffres avec des zéros non significatifs.</span><span class="sxs-lookup"><span data-stu-id="bd432-216"> <`catid`> is a five digit number with leading zeros.</span></span>  
  
 <`n`>  
 <span data-ttu-id="bd432-217">Entier qui indique qu'il existe un ou plusieurs journaux d'analyse du même catalogue de texte intégral.</span><span class="sxs-lookup"><span data-stu-id="bd432-217">Is an integer that indicates one or more crawl logs of the same full-text catalog exist.</span></span>  
  
 <span data-ttu-id="bd432-218">Par exemple, SQLFT0000500008.2 est le fichier journal d'analyse pour une base de données présentant l'ID de base de données = 5 et l'ID de catalogue de texte intégral = 8.</span><span class="sxs-lookup"><span data-stu-id="bd432-218">For example, SQLFT0000500008.2 is the crawl log file for a database with database ID = 5, and full-text catalog ID = 8.</span></span> <span data-ttu-id="bd432-219">Le 2 à la fin du nom de fichier indique qu'il existe deux fichiers journaux d'analyse pour cette combinaison base de données/catalogue.</span><span class="sxs-lookup"><span data-stu-id="bd432-219">The 2 at the end of the file name indicates that there are two crawl log files for this database/catalog pair.</span></span>  
  

  
## <a name="see-also"></a><span data-ttu-id="bd432-220">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bd432-220">See Also</span></span>  
 <span data-ttu-id="bd432-221">[sys.dm_fts_index_population &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-index-population-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bd432-221">[sys.dm_fts_index_population &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-index-population-transact-sql) </span></span>  
 <span data-ttu-id="bd432-222">[Commencer à utiliser la recherche en texte intégral](get-started-with-full-text-search.md) </span><span class="sxs-lookup"><span data-stu-id="bd432-222">[Get Started with Full-Text Search](get-started-with-full-text-search.md) </span></span>  
 <span data-ttu-id="bd432-223">[Créer et gérer des index de recherche en texte intégral](create-and-manage-full-text-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="bd432-223">[Create and Manage Full-Text Indexes](create-and-manage-full-text-indexes.md) </span></span>  
 <span data-ttu-id="bd432-224">[CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bd432-224">[CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-index-transact-sql) </span></span>  
 [<span data-ttu-id="bd432-225">ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="bd432-225">ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-fulltext-index-transact-sql)  
  
  
