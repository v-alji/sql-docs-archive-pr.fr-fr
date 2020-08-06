---
title: Importation de données (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- staging process [Master Data Services], about staging process
- importing data [Master Data Services]
- staging process [Master Data Services]
ms.assetid: 181d1e22-379c-45d1-b03c-e1e22ff14164
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 403eca212611397fb3ba30f8fe12a2aa8b5e83ae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601003"
---
# <a name="data-import-master-data-services"></a><span data-ttu-id="d1780-102">Importation de données (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="d1780-102">Data Import (Master Data Services)</span></span>
  <span data-ttu-id="d1780-103">Une fois que vous avez créé un modèle pour vos données dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], vous pouvez commencer à ajouter des données et à apporter des modifications aux données de la base de données [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d1780-103">Once you've created a model for your data in [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], you can start adding data and make changes to data in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span>   <span data-ttu-id="d1780-104">Vous utilisez les tables de mise en lots [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] , les procédures stockées et Master Data Manager.</span><span class="sxs-lookup"><span data-stu-id="d1780-104">You use [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] staging tables, stored procedures and Master Data Manager .</span></span>

 <span data-ttu-id="d1780-105">Vous pouvez également utiliser le [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] [!INCLUDE[ssMDSXLS](../includes/ssmdsxls-md.md)] pour ajouter des données au référentiel MDS ( [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] base de données).</span><span class="sxs-lookup"><span data-stu-id="d1780-105">You can also use the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)][!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../includes/ssmdsxls-md.md)], to add data to the MDS repository ([!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database).</span></span> <span data-ttu-id="d1780-106">Pour plus d’informations, consultez [publication de données &#40;Complément MDS pour Excel&#41;](microsoft-excel-add-in/overview-importing-data-from-excel-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="d1780-106">For more information, see [Publishing Data &#40;MDS Add-in for Excel&#41;](microsoft-excel-add-in/overview-importing-data-from-excel-mds-add-in-for-excel.md).</span></span>

 <span data-ttu-id="d1780-107">Lorsque vous ajoutez et mettez à jour des données, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="d1780-107">When you add and update data, you can do the following.</span></span>

-   <span data-ttu-id="d1780-108">Charger et mettre à jour les membres, puis mettre à jour les valeurs d'attribut</span><span class="sxs-lookup"><span data-stu-id="d1780-108">Load and update members, and update attribute values</span></span>

-   <span data-ttu-id="d1780-109">Désactiver et supprimer les membres</span><span class="sxs-lookup"><span data-stu-id="d1780-109">Deactivate and delete members</span></span>

-   <span data-ttu-id="d1780-110">Déplacer les membres d’une hiérarchie explicite</span><span class="sxs-lookup"><span data-stu-id="d1780-110">Move explicit hierarchy members</span></span>

 <span data-ttu-id="d1780-111">L’ajout et la mise à jour des données incluent les tâches principales suivantes.</span><span class="sxs-lookup"><span data-stu-id="d1780-111">Adding and updating data  includes the following main tasks.</span></span>

1.  <span data-ttu-id="d1780-112">Chargez les données dans des tables de mise en lots dans la base de données [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d1780-112">Load data into the staging tables in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span>

2.  <span data-ttu-id="d1780-113">Chargez les données des tables de mise en lots vers les tables [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] appropriées.</span><span class="sxs-lookup"><span data-stu-id="d1780-113">Load the data from the staging tables into the appropriate [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] tables.</span></span>

     <span data-ttu-id="d1780-114">Vous utilisez des procédures stockées intermédiaires ou [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] pour charger les données.</span><span class="sxs-lookup"><span data-stu-id="d1780-114">You use staging stored procedures or [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] to load the data.</span></span>

> [!NOTE]
>  <span data-ttu-id="d1780-115">Dans [!INCLUDE[ssSQL14](../includes/sssql14-md.md)], la prise en charge des processus de mise en lots [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] est déconseillée.</span><span class="sxs-lookup"><span data-stu-id="d1780-115">In [!INCLUDE[ssSQL14](../includes/sssql14-md.md)], support for the [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] staging processes is deprecated.</span></span>

## <a name="deactivating-and-deleting-members"></a><span data-ttu-id="d1780-116">Désactivation et suppression de membres</span><span class="sxs-lookup"><span data-stu-id="d1780-116">Deactivating and Deleting Members</span></span>
 <span data-ttu-id="d1780-117">La désactivation signifie que le membre peut être réactivé.</span><span class="sxs-lookup"><span data-stu-id="d1780-117">Deactivating means the member can be reactivated.</span></span> <span data-ttu-id="d1780-118">La réactivation d'un membre permet de restaurer ses attributs et son appartenance aux hiérarchies et collections.</span><span class="sxs-lookup"><span data-stu-id="d1780-118">If you reactivate a member, its attributes and its membership in hierarchies and collections are restored.</span></span> <span data-ttu-id="d1780-119">Toutes les transactions précédentes sont intactes.</span><span class="sxs-lookup"><span data-stu-id="d1780-119">All previous transactions are intact.</span></span> <span data-ttu-id="d1780-120">Les transactions de désactivation sont visibles par les administrateurs dans la zone fonctionnelle **Gestion des versions** de Master Data Manager.</span><span class="sxs-lookup"><span data-stu-id="d1780-120">Deactivation transactions are visible to administrators in the **Version Management** functional area of the Master Data Manager.</span></span>

 <span data-ttu-id="d1780-121">La suppression signifie retirer définitivement le membre du système.</span><span class="sxs-lookup"><span data-stu-id="d1780-121">Deleting means purging the member from the system permanently.</span></span> <span data-ttu-id="d1780-122">Toutes les transactions du membre, toutes les relations et tous les attributs sont supprimés définitivement.</span><span class="sxs-lookup"><span data-stu-id="d1780-122">All transactions for the member, all relationships, and all attributes are permanently deleted.</span></span>

> [!NOTE]
>  <span data-ttu-id="d1780-123">Vous ne pouvez pas utiliser la mise en lots pour réactiver des membres.</span><span class="sxs-lookup"><span data-stu-id="d1780-123">You cannot use staging to reactivate members.</span></span> <span data-ttu-id="d1780-124">Vous devez le faire manuellement dans Master Data Manager.</span><span class="sxs-lookup"><span data-stu-id="d1780-124">You must do it manually in the Master Data Manager.</span></span> <span data-ttu-id="d1780-125">Pour plus d’informations, consultez [Réactiver un membre ou une collection &#40;Master Data Services&#41;](reactivate-a-member-or-collection-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="d1780-125">For more information, see [Reactivate a Member or Collection &#40;Master Data Services&#41;](reactivate-a-member-or-collection-master-data-services.md).</span></span>
> 
>  <span data-ttu-id="d1780-126">Vous ne pouvez pas utiliser la mise en lots pour supprimer ou désactiver des collections.</span><span class="sxs-lookup"><span data-stu-id="d1780-126">You cannot use staging to delete or deactivate collections.</span></span> <span data-ttu-id="d1780-127">Pour plus d’informations sur la désactivation manuelle des collections, consultez [Supprimer un membre ou une collection &#40;Master Data Services&#41;](../../2014/master-data-services/delete-a-member-or-collection-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="d1780-127">For more information on manually deactivating collections, see [Delete a Member or Collection &#40;Master Data Services&#41;](../../2014/master-data-services/delete-a-member-or-collection-master-data-services.md).</span></span>

## <a name="moving-explicit-hierarchy-members"></a><span data-ttu-id="d1780-128">Déplacement des membres d’une hiérarchie explicite</span><span class="sxs-lookup"><span data-stu-id="d1780-128">Moving explicit hierarchy members</span></span>
 <span data-ttu-id="d1780-129">Lorsque vous déplacez en bloc des membres des hiérarchies explicites, vous pouvez désigner les membres comme suit.</span><span class="sxs-lookup"><span data-stu-id="d1780-129">When you move the location of members in explicit hierarchies in bulk, you can designate the following.</span></span>

-   <span data-ttu-id="d1780-130">Un membre consolidé comme un parent d'un membre consolidé.</span><span class="sxs-lookup"><span data-stu-id="d1780-130">A consolidated member as a parent of a consolidated member.</span></span>

-   <span data-ttu-id="d1780-131">Un membre consolidé comme un parent d'un membre feuille.</span><span class="sxs-lookup"><span data-stu-id="d1780-131">A consolidated member as a parent of a leaf member.</span></span>

-   <span data-ttu-id="d1780-132">Un membre feuille comme un frère d'une feuille ou un membre consolidé.</span><span class="sxs-lookup"><span data-stu-id="d1780-132">A leaf member as a sibling of a leaf or consolidated member.</span></span>

-   <span data-ttu-id="d1780-133">Un membre consolidé comme un frère d'une feuille ou un membre consolidé.</span><span class="sxs-lookup"><span data-stu-id="d1780-133">A consolidated member as a sibling of a leaf or consolidated member.</span></span>

## <a name="staging-tables-and-stored-procedures"></a><span data-ttu-id="d1780-134">Tables de mise en lots et procédures stockées</span><span class="sxs-lookup"><span data-stu-id="d1780-134">Staging Tables and Stored Procedures</span></span>
 <span data-ttu-id="d1780-135">La base de données [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] inclut les types suivants de tables de mise en lots que vous pouvez remplir avec vos données.</span><span class="sxs-lookup"><span data-stu-id="d1780-135">The [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database includes the following types of staging tables that you can populate with your  data.</span></span>

-   [<span data-ttu-id="d1780-136">Table de mise en lots des membres feuille &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d1780-136">Leaf Member Staging Table &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/leaf-member-staging-table-master-data-services.md)

-   [<span data-ttu-id="d1780-137">Table de mise en lots des membres consolidés &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d1780-137">Consolidated Member Staging Table &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/consolidated-member-staging-table-master-data-services.md)

-   [<span data-ttu-id="d1780-138">Table de mise en lots des relations &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d1780-138">Relationship Staging Table &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/relationship-staging-table-master-data-services.md)

 <span data-ttu-id="d1780-139">Pour chaque entité du modèle, il existe une table de mise en lots.</span><span class="sxs-lookup"><span data-stu-id="d1780-139">For each entity in the model, there is a staging table.</span></span> <span data-ttu-id="d1780-140">Le nom de la table indique l'entité correspondante et le type d'entité comme membre feuille.</span><span class="sxs-lookup"><span data-stu-id="d1780-140">The table name indicates the corresponding entity, and the entity type such as leaf member.</span></span> <span data-ttu-id="d1780-141">L'illustration suivante montre les tables de mise en lots pour les entités Devise, Client et Produit.</span><span class="sxs-lookup"><span data-stu-id="d1780-141">The following image shows the staging tables for the currency, customer, and product entities.</span></span>

 <span data-ttu-id="d1780-142">![Tables intermédiaires dans la base de données MDS](../../2014/master-data-services/media/mds-stagingtables.png "Tables intermédiaires dans la base de données MDS")</span><span class="sxs-lookup"><span data-stu-id="d1780-142">![Staging Tables in MDS database](../../2014/master-data-services/media/mds-stagingtables.png "Staging Tables in MDS database")</span></span>

 <span data-ttu-id="d1780-143">Le nom de la table est spécifié lors de la création d'une entité et ne peut pas être modifié.</span><span class="sxs-lookup"><span data-stu-id="d1780-143">The name of the  table is specified when an entity is created and cannot be changed.</span></span> <span data-ttu-id="d1780-144">Si le nom de la table de mise en lots contient un _1 ou tout autre nombre, une autre table de ce nom existait déjà lorsque l'entité a été créée.</span><span class="sxs-lookup"><span data-stu-id="d1780-144">If the staging table name contains a _1 or other number, another table of that name already existed when the entity was created.</span></span>

 <span data-ttu-id="d1780-145">[!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] inclut les types suivants de procédures stockées de mise en lots.</span><span class="sxs-lookup"><span data-stu-id="d1780-145">The [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] includes the following types of staging stored procedures.</span></span>

-   <span data-ttu-id="d1780-146">STG. udp_ \<name> _Leaf</span><span class="sxs-lookup"><span data-stu-id="d1780-146">stg.udp_\<name>_Leaf</span></span>

-   <span data-ttu-id="d1780-147">STG. udp_ \<name> _Consolidated</span><span class="sxs-lookup"><span data-stu-id="d1780-147">stg.udp_\<name>_Consolidated</span></span>

-   <span data-ttu-id="d1780-148">STG. udp_ \<name> _Relationship</span><span class="sxs-lookup"><span data-stu-id="d1780-148">stg.udp_\<name>_Relationship</span></span>

 <span data-ttu-id="d1780-149">Pour chaque entité du modèle, il existe trois procédures stockées qui correspondent à un membre feuille, un membre consolidé et les tables de mise en lots de relations.</span><span class="sxs-lookup"><span data-stu-id="d1780-149">For each entity in the model, there are three stored procedures that correspond to the leaf member, consolidated member, and relationship staging tables.</span></span>  <span data-ttu-id="d1780-150">L'illustration suivante montre les procédures stockées de mise en lots pour les entités Devise, Client et Produit.</span><span class="sxs-lookup"><span data-stu-id="d1780-150">The following image shows the staging stored procedures for the currency, customer, and product entities.</span></span>

 <span data-ttu-id="d1780-151">![Procédures stockées intermédiaires dans la base de données MDS](../../2014/master-data-services/media/mds-stagingstoredprocedures.png "Procédures stockées intermédiaires dans la base de données MDS")</span><span class="sxs-lookup"><span data-stu-id="d1780-151">![Staging Stored Procedures in MDS database](../../2014/master-data-services/media/mds-stagingstoredprocedures.png "Staging Stored Procedures in MDS database")</span></span>

 <span data-ttu-id="d1780-152">Pour plus d’informations sur les procédures stockées, consultez [Procédure stockée de mise en lots &#40;Master Data Services&#41;](../../2014/master-data-services/staging-stored-procedure-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="d1780-152">For more information on the stored procedures, see [Staging Stored Procedure &#40;Master Data Services&#41;](../../2014/master-data-services/staging-stored-procedure-master-data-services.md).</span></span>

## <a name="logging-transactions"></a><span data-ttu-id="d1780-153">Journalisation des transactions</span><span class="sxs-lookup"><span data-stu-id="d1780-153">Logging Transactions</span></span>
 <span data-ttu-id="d1780-154">Toutes les transactions qui se produisent lors de l'importation ou de la mise à jour des données ou des relations peuvent être enregistrées dans un journal.</span><span class="sxs-lookup"><span data-stu-id="d1780-154">All transactions that occur when data or relationships are imported or updated can be logged.</span></span> <span data-ttu-id="d1780-155">Une option dans la procédure stockée permet cette journalisation.</span><span class="sxs-lookup"><span data-stu-id="d1780-155">An option in the stored procedure allows this logging.</span></span> <span data-ttu-id="d1780-156">Si vous initialisez le processus de site à l’aide de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], aucune journalisation n'a lieu.</span><span class="sxs-lookup"><span data-stu-id="d1780-156">If you initiate the staging process using [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], no logging occurs.</span></span>

 <span data-ttu-id="d1780-157">Dans le [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)], le paramètre **Journaliser toutes les transactions intermédiaires** ne s'applique pas à cette méthode de mise en lot des données.</span><span class="sxs-lookup"><span data-stu-id="d1780-157">In [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)], the **Log staging transactions** setting does not apply to this method of staging data.</span></span>

## <a name="related-content"></a><span data-ttu-id="d1780-158">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="d1780-158">Related Content</span></span>

-   [<span data-ttu-id="d1780-159">Validation &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d1780-159">Validation &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validation-master-data-services.md)

-   [<span data-ttu-id="d1780-160">Règles d’entreprise &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d1780-160">Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/business-rules-master-data-services.md)


