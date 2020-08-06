---
title: Propriétés de la table (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.tabledesigner
- vdt.designers.properties.Table
ms.assetid: cc392987-1aab-45f5-b5af-a26be53409bf
author: stevestein
ms.author: sstein
ms.openlocfilehash: df4a0332ebc622b069c468e51c461b7cba20aa36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704608"
---
# <a name="table-properties-visual-database-tools"></a><span data-ttu-id="fdb3e-102">Propriétés de la table (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="fdb3e-102">Table Properties (Visual Database Tools)</span></span>
  <span data-ttu-id="fdb3e-103">Ces propriétés apparaissent dans la fenêtre Propriétés lorsque vous cliquez avec le bouton droit dans le Concepteur de tables puis sélectionnez Propriétés.</span><span class="sxs-lookup"><span data-stu-id="fdb3e-103">These properties appear in the Properties window when you right click in Table Designer and select Properties.</span></span> <span data-ttu-id="fdb3e-104">Sauf indication contraire, vous pouvez modifier ces propriétés dans la fenêtre Propriétés lorsque la table est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="fdb3e-104">Unless otherwise noted, you can edit these properties in the Properties window when the table is selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fdb3e-105">Si la table est publiée pour réplication, vous devez apporter vos modifications au schéma à l’aide de l’instruction Transact-SQL [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) ou de SMO (SQL Server Management Objects).</span><span class="sxs-lookup"><span data-stu-id="fdb3e-105">If the table is published for replication, you must make schema changes using the Transact-SQL statement [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) or SQL Server Management Objects (SMO).</span></span> <span data-ttu-id="fdb3e-106">Lorsque les modifications sont apportées au diagramme à l’aide du Concepteur de tables ou du Concepteur de diagrammes de base de données, celui-ci tente d’abandonner la table et de la recréer.</span><span class="sxs-lookup"><span data-stu-id="fdb3e-106">When schema changes are made using the Table Designer or the Database Diagram Designer, it attempts to drop and recreate the table.</span></span> <span data-ttu-id="fdb3e-107">Toutefois, il est impossible d'abandonner les objets publiés, par conséquent les modifications du schéma échoueront.</span><span class="sxs-lookup"><span data-stu-id="fdb3e-107">You cannot drop published objects, therefore the schema change will fail.</span></span>  
  
## <a name="show-table-properties-in-table-designer"></a><span data-ttu-id="fdb3e-108">Affichage des propriétés de la table dans le Concepteur de tables</span><span class="sxs-lookup"><span data-stu-id="fdb3e-108">Show Table Properties in Table Designer</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fdb3e-109">Les propriétés mentionnées dans cette rubrique sont classées par catégorie et non par ordre alphabétique.</span><span class="sxs-lookup"><span data-stu-id="fdb3e-109">The properties in this topic are ordered by category rather than alphabet.</span></span>  
  
 <span data-ttu-id="fdb3e-110">**Catégorie Identité**</span><span class="sxs-lookup"><span data-stu-id="fdb3e-110">**Identity Category**</span></span>  
 <span data-ttu-id="fdb3e-111">Se développe pour afficher les propriétés de **Nom**, **Description**et **Schéma**.</span><span class="sxs-lookup"><span data-stu-id="fdb3e-111">Expands to show properties for **Name**, **Description**, and **Schema**.</span></span>  
  
 <span data-ttu-id="fdb3e-112">**Nom**</span><span class="sxs-lookup"><span data-stu-id="fdb3e-112">**Name**</span></span>  
 <span data-ttu-id="fdb3e-113">Affiche le nom de la table.</span><span class="sxs-lookup"><span data-stu-id="fdb3e-113">Displays the name of the table.</span></span> <span data-ttu-id="fdb3e-114">Pour modifier le nom, tapez-le dans la zone de texte.</span><span class="sxs-lookup"><span data-stu-id="fdb3e-114">To edit the name, type in the text box.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="fdb3e-115">En effet, s’il existe des requêtes, des vues, des fonctions définies par l’utilisateur, des procédures stockées ou des programmes qui font référence à la table, le changement de nom rend tous ces objets non valides.</span><span class="sxs-lookup"><span data-stu-id="fdb3e-115">If existing queries, views, user-defined functions, stored procedures, or programs refer to the table, the name modification will make these objects invalid.</span></span>  
  
 <span data-ttu-id="fdb3e-116">**Database Name**</span><span class="sxs-lookup"><span data-stu-id="fdb3e-116">**Database Name**</span></span>  
 <span data-ttu-id="fdb3e-117">Affiche le nom de la source de données de la table sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="fdb3e-117">Shows the name of the data source of the selected table.</span></span>  
  
 <span data-ttu-id="fdb3e-118">**Description**</span><span class="sxs-lookup"><span data-stu-id="fdb3e-118">**Description**</span></span>  
 <span data-ttu-id="fdb3e-119">Indique la description de la table sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="fdb3e-119">Shows a description of the selected table.</span></span> <span data-ttu-id="fdb3e-120">Pour afficher l’intégralité de la description ou la modifier, cliquez sur la description, puis sur le bouton de sélection **(...)** situé à droite de la propriété.</span><span class="sxs-lookup"><span data-stu-id="fdb3e-120">To see the entire description, or to edit it, click the description and then click the ellipses **(...)** to the right of the property.</span></span>  
  
 <span data-ttu-id="fdb3e-121">**Schéma**</span><span class="sxs-lookup"><span data-stu-id="fdb3e-121">**Schema**</span></span>  
 <span data-ttu-id="fdb3e-122">Affiche le nom du schéma auquel cette table appartient.</span><span class="sxs-lookup"><span data-stu-id="fdb3e-122">Shows the name of the schema to which this table belongs.</span></span> <span data-ttu-id="fdb3e-123">(S'applique uniquement à Microsoft SQL Server.)</span><span class="sxs-lookup"><span data-stu-id="fdb3e-123">(Applies only to Microsoft SQL Server.)</span></span>  
  
 <span data-ttu-id="fdb3e-124">**Nom de serveur**</span><span class="sxs-lookup"><span data-stu-id="fdb3e-124">**Server Name**</span></span>  
 <span data-ttu-id="fdb3e-125">Affiche le nom du serveur de la source de données.</span><span class="sxs-lookup"><span data-stu-id="fdb3e-125">Shows the name of the server for the data source.</span></span>  
  
 <span data-ttu-id="fdb3e-126">**Catégorie Concepteur de tables**</span><span class="sxs-lookup"><span data-stu-id="fdb3e-126">**Table Designer Category**</span></span>  
 <span data-ttu-id="fdb3e-127">Se développe pour afficher des propriétés pour **Colonne d’identité**, **Is Indexable**et **Is Replicated**.</span><span class="sxs-lookup"><span data-stu-id="fdb3e-127">Expands to show properties for **Identity Column**, **Is Indexable**, and **Is Replicated**.</span></span>  
  
 <span data-ttu-id="fdb3e-128">**Colonne d’identité**</span><span class="sxs-lookup"><span data-stu-id="fdb3e-128">**Identity Column**</span></span>  
 <span data-ttu-id="fdb3e-129">Affiche la colonne utilisée comme colonne d'identité de la table.</span><span class="sxs-lookup"><span data-stu-id="fdb3e-129">Shows the column used as the table's identity column.</span></span> <span data-ttu-id="fdb3e-130">Pour modifier l'identité d'une colonne, choisissez-la dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="fdb3e-130">To change the identity column, choose from the drop-down list.</span></span> <span data-ttu-id="fdb3e-131">Seules les colonnes d'un type de données numérique s'affichent dans la liste.</span><span class="sxs-lookup"><span data-stu-id="fdb3e-131">Only columns of a numeric data type will show in the list.</span></span>  
  
 <span data-ttu-id="fdb3e-132">**Indexable**</span><span class="sxs-lookup"><span data-stu-id="fdb3e-132">**Is Indexable**</span></span>  
 <span data-ttu-id="fdb3e-133">Indique si la table peut être indexée.</span><span class="sxs-lookup"><span data-stu-id="fdb3e-133">Shows whether the table can be indexed.</span></span> <span data-ttu-id="fdb3e-134">Si la table n'est pas indexable, cela peut être dû au fait que vous n'êtes pas le propriétaire de la table ou que la table contient des colonnes possédant des types de données texte, ntext ou image.</span><span class="sxs-lookup"><span data-stu-id="fdb3e-134">If the table is not indexable it may be because you are not the table owner or because the table contains columns with data types of text, ntext, or image.</span></span>  
  
 <span data-ttu-id="fdb3e-135">**Répliquée**</span><span class="sxs-lookup"><span data-stu-id="fdb3e-135">**Is Replicated**</span></span>  
 <span data-ttu-id="fdb3e-136">Indique si la table est répliquée à un autre emplacement.</span><span class="sxs-lookup"><span data-stu-id="fdb3e-136">Shows whether the table is replicated in another location.</span></span>  
  
 <span data-ttu-id="fdb3e-137">**Catégorie Spécification d'espace de données régulière**</span><span class="sxs-lookup"><span data-stu-id="fdb3e-137">**Regular Data Space Specification Category**</span></span>  
 <span data-ttu-id="fdb3e-138">Se développe pour afficher des propriétés pour **(Type d’espace de données)** , **Nom du schéma de partition ou du groupe de fichiers**et **Liste des colonnes de partition**.</span><span class="sxs-lookup"><span data-stu-id="fdb3e-138">Expands to show properties for **(Data Space Type)**, **Filegroup or Partition Scheme Name**, and **Partition Column List**.</span></span>  
  
 <span data-ttu-id="fdb3e-139">**(Type d’espace de données)**</span><span class="sxs-lookup"><span data-stu-id="fdb3e-139">**(Data Space Type)**</span></span>  
 <span data-ttu-id="fdb3e-140">Indique si cette table est stockée à l'aide d'un groupe de fichiers ou d'un schéma de partition.</span><span class="sxs-lookup"><span data-stu-id="fdb3e-140">Shows whether this table is stored using a filegroup or partition scheme.</span></span>  
  
 <span data-ttu-id="fdb3e-141">**Nom du schéma de partition ou du groupe de fichiers**</span><span class="sxs-lookup"><span data-stu-id="fdb3e-141">**Filegroup or Partition Scheme Name**</span></span>  
 <span data-ttu-id="fdb3e-142">Affiche le nom du groupe de fichiers ou du schéma de partition.</span><span class="sxs-lookup"><span data-stu-id="fdb3e-142">Shows the name of the filegroup or partition scheme.</span></span>  
  
 <span data-ttu-id="fdb3e-143">**Liste des colonnes de partition**</span><span class="sxs-lookup"><span data-stu-id="fdb3e-143">**Partition Column List**</span></span>  
 <span data-ttu-id="fdb3e-144">Donne accès à la boîte de dialogue **Liste des colonnes de partition** .</span><span class="sxs-lookup"><span data-stu-id="fdb3e-144">Provides access to the **Partition Column List** dialog box.</span></span>  
  
 <span data-ttu-id="fdb3e-145">**Colonne RowGuid**</span><span class="sxs-lookup"><span data-stu-id="fdb3e-145">**Row GUID Column**</span></span>  
 <span data-ttu-id="fdb3e-146">Affiche la colonne utilisée par Microsoft SQL Server comme colonne ROWGUID de la table.</span><span class="sxs-lookup"><span data-stu-id="fdb3e-146">Shows the column used by Microsoft SQL Server as the table's ROWGUID column.</span></span> <span data-ttu-id="fdb3e-147">Pour changer de colonne ROWGUID, choisissez-la dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="fdb3e-147">To change the ROWGUID column, choose from the drop-down list.</span></span> <span data-ttu-id="fdb3e-148">(S'applique uniquement à SQL Server 7.0 ou version ultérieure.)</span><span class="sxs-lookup"><span data-stu-id="fdb3e-148">(Applies only to SQL Server 7.0 or higher.)</span></span>  
  
 <span data-ttu-id="fdb3e-149">**Groupe de fichiers Text/Image**</span><span class="sxs-lookup"><span data-stu-id="fdb3e-149">**Text/Image Filegroup**</span></span>  
 <span data-ttu-id="fdb3e-150">Fournit une liste déroulante dans laquelle vous pouvez choisir le groupe de fichiers des colonnes possédant des types de données texte ou image.</span><span class="sxs-lookup"><span data-stu-id="fdb3e-150">Provides a drop-down list from which you can choose the filegroup for columns that have text or image data types.</span></span> <span data-ttu-id="fdb3e-151">Si la table est stockée à l'aide d'un schéma de partition, laissez ce champ vierge.</span><span class="sxs-lookup"><span data-stu-id="fdb3e-151">If the table is stored using a partition scheme, leave this field blank.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdb3e-152">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fdb3e-152">See Also</span></span>  
 [<span data-ttu-id="fdb3e-153">Concevoir des tables &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="fdb3e-153">Design Tables &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
