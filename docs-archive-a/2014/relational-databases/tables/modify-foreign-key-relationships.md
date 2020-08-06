---
title: Modifier des relations de clé étrangère | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
f1_keywords:
- vdtsql.chm:65538
- vdt.ppg.relationships
helpviewer_keywords:
- foreign keys [SQL Server], modifying
- modifying foreign keys
ms.assetid: 0c9ca80d-d79b-44c4-a21e-0fce39c398ec
author: stevestein
ms.author: sstein
ms.openlocfilehash: ba9010b0d634a174dd35391c870d5003aa78efa1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601290"
---
# <a name="modify-foreign-key-relationships"></a><span data-ttu-id="b087e-102">Modifier des relations de clé étrangère</span><span class="sxs-lookup"><span data-stu-id="b087e-102">Modify Foreign Key Relationships</span></span>
  <span data-ttu-id="b087e-103">Vous pouvez modifier le côté clé étrangère d'une relation dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b087e-103">You can modify the foreign key side of a relationship in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="b087e-104">La modification de la clé étrangère d’une table modifie les colonnes liées aux colonnes figurant dans la table de clé primaire.</span><span class="sxs-lookup"><span data-stu-id="b087e-104">Modifying a table's foreign key changes which columns are related to columns in the primary key table.</span></span>  
  
 <span data-ttu-id="b087e-105">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="b087e-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b087e-106">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="b087e-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b087e-107">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="b087e-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="b087e-108">Sécurité</span><span class="sxs-lookup"><span data-stu-id="b087e-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b087e-109">**Pour modifier une clé étrangère, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="b087e-109">**To modify a foreign key using:**</span></span>  
  
     [<span data-ttu-id="b087e-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b087e-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b087e-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b087e-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b087e-112">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="b087e-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="b087e-113">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="b087e-113">Limitations and Restrictions</span></span>  
 <span data-ttu-id="b087e-114">Le type de données et la taille de la nouvelle colonne clé étrangère doivent correspondre à ceux de la colonne clé primaire à laquelle elle est associée, à ceci près :</span><span class="sxs-lookup"><span data-stu-id="b087e-114">The new foreign key column must match the data type and size of the primary key column to which it relates, with these exceptions:</span></span>  
  
-   <span data-ttu-id="b087e-115">Une colonne `char` ou `sysname` peut être en relation avec une colonne `varchar`.</span><span class="sxs-lookup"><span data-stu-id="b087e-115">A `char` column or `sysname` column can relate to a `varchar` column.</span></span>  
  
-   <span data-ttu-id="b087e-116">Une colonne `binary` peut être en relation avec une colonne `varbinary`.</span><span class="sxs-lookup"><span data-stu-id="b087e-116">A `binary` column can relate to a `varbinary` column.</span></span>  
  
-   <span data-ttu-id="b087e-117">Un type de données alias peut être en relation avec son type de base.</span><span class="sxs-lookup"><span data-stu-id="b087e-117">An alias data type can relate to its base type.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b087e-118">Sécurité</span><span class="sxs-lookup"><span data-stu-id="b087e-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b087e-119">Autorisations</span><span class="sxs-lookup"><span data-stu-id="b087e-119">Permissions</span></span>  
 <span data-ttu-id="b087e-120">Requiert une autorisation ALTER sur la table.</span><span class="sxs-lookup"><span data-stu-id="b087e-120">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b087e-121">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b087e-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-a-foreign-key"></a><span data-ttu-id="b087e-122">Pour modifier une clé étrangère</span><span class="sxs-lookup"><span data-stu-id="b087e-122">To modify a foreign key</span></span>  
  
1.  <span data-ttu-id="b087e-123">Dans l' **Explorateur d'objets**, développez la table avec la clé étrangère, puis développez **Clés**.</span><span class="sxs-lookup"><span data-stu-id="b087e-123">In **Object Explorer**, expand the table with the foreign key and then expand **Keys**.</span></span>  
  
2.  <span data-ttu-id="b087e-124">Cliquez avec le bouton droit sur la clé étrangère à modifier et sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="b087e-124">Right-click the foreign key to be modified and select **Modify**.</span></span>  
  
3.  <span data-ttu-id="b087e-125">Dans la boîte de dialogue **Relations de clé étrangère** , vous pouvez apporter les modifications suivantes.</span><span class="sxs-lookup"><span data-stu-id="b087e-125">In the **Foreign Key Relationships** dialog box, you can make the following modifications.</span></span>  
  
     <span data-ttu-id="b087e-126">**Relation sélectionnée**</span><span class="sxs-lookup"><span data-stu-id="b087e-126">**Selected Relationship**</span></span>  
     <span data-ttu-id="b087e-127">Répertorie les relations existantes.</span><span class="sxs-lookup"><span data-stu-id="b087e-127">Lists existing relationships.</span></span> <span data-ttu-id="b087e-128">Sélectionnez une relation pour afficher ses propriétés dans la partie droite de la grille.</span><span class="sxs-lookup"><span data-stu-id="b087e-128">Select a relationship to show its properties in the grid to the right.</span></span> <span data-ttu-id="b087e-129">Si la liste est vide, aucune relation n'est définie pour la table.</span><span class="sxs-lookup"><span data-stu-id="b087e-129">If the list is empty, no relationships have been defined for the table.</span></span>  
  
     <span data-ttu-id="b087e-130">**Ajouter**</span><span class="sxs-lookup"><span data-stu-id="b087e-130">**Add**</span></span>  
     <span data-ttu-id="b087e-131">Crée une nouvelle relation.</span><span class="sxs-lookup"><span data-stu-id="b087e-131">Create a new relationship.</span></span> <span data-ttu-id="b087e-132">Une relation valide exige que la **Spécification de tables et colonnes** soit définie.</span><span class="sxs-lookup"><span data-stu-id="b087e-132">The **Tables and Columns Specifications** must be set before the relationship will be valid.</span></span>  
  
     <span data-ttu-id="b087e-133">**Supprimer**</span><span class="sxs-lookup"><span data-stu-id="b087e-133">**Delete**</span></span>  
     <span data-ttu-id="b087e-134">Supprime la relation sélectionnée dans la liste **Relation sélectionnée** .</span><span class="sxs-lookup"><span data-stu-id="b087e-134">Delete the relationship selected in the **Selected Relationships** list.</span></span> <span data-ttu-id="b087e-135">Pour annuler l'ajout d'une relation, supprimez la relation à l'aide de ce bouton.</span><span class="sxs-lookup"><span data-stu-id="b087e-135">To cancel the addition of a relationship, use this button to remove the relationship.</span></span>  
  
     <span data-ttu-id="b087e-136">**Catégorie Général**</span><span class="sxs-lookup"><span data-stu-id="b087e-136">**General Category**</span></span>  
     <span data-ttu-id="b087e-137">Se développe pour afficher **Vérifier les données existantes à la création ou à la réactivation** et **Spécification de tables et colonnes**.</span><span class="sxs-lookup"><span data-stu-id="b087e-137">Expand to show **Check Existing Data on Creation or RE-Enabling** and **Tables and Columns Specifications**.</span></span>  
  
     <span data-ttu-id="b087e-138">**Check Existing Data on Creation or Re-Enabling**</span><span class="sxs-lookup"><span data-stu-id="b087e-138">**Check Existing Data on Creation or Re-Enabling**</span></span>  
     <span data-ttu-id="b087e-139">Vérifie en fonction de la contrainte, toutes les données qui existaient dans la table avant la création ou la réactivation de la contrainte.</span><span class="sxs-lookup"><span data-stu-id="b087e-139">Verify all existing data in the table before the constraint was created or re-enabled, against the constraint.</span></span>  
  
     <span data-ttu-id="b087e-140">**Catégorie Spécification de tables et colonnes**</span><span class="sxs-lookup"><span data-stu-id="b087e-140">**Tables and Columns Specifications Category**</span></span>  
     <span data-ttu-id="b087e-141">Se développe pour afficher les colonnes des tables jouant le rôle de clé étrangère et de clé primaire (ou unique) dans la relation.</span><span class="sxs-lookup"><span data-stu-id="b087e-141">Expand to show which columns from which tables act as the foreign key and primary (or unique) key in the relationship.</span></span> <span data-ttu-id="b087e-142">Pour modifier ou définir ces valeurs, cliquez sur le bouton de sélection ( **...** ) à droite du champ de propriété.</span><span class="sxs-lookup"><span data-stu-id="b087e-142">To edit or define these values, click the ellipsis button (**...**) to the right of the property field.</span></span>  
  
     <span data-ttu-id="b087e-143">**Table de base de clé étrangère**</span><span class="sxs-lookup"><span data-stu-id="b087e-143">**Foreign Key Base Table**</span></span>  
     <span data-ttu-id="b087e-144">Affiche la table qui contient la colonne jouant le rôle de clé étrangère dans la relation sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="b087e-144">Shows which table contains the column acting as a foreign key in the selected relationship.</span></span>  
  
     <span data-ttu-id="b087e-145">**Colonnes clés étrangères**</span><span class="sxs-lookup"><span data-stu-id="b087e-145">**Foreign Key Columns**</span></span>  
     <span data-ttu-id="b087e-146">Affiche la colonne qui joue le rôle de clé étrangère dans la relation sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="b087e-146">Shows which column acts as a foreign key in the selected relationship.</span></span>  
  
     <span data-ttu-id="b087e-147">**Table de base de clé Primary/Unique**</span><span class="sxs-lookup"><span data-stu-id="b087e-147">**Primary/Unique Key Base Table**</span></span>  
     <span data-ttu-id="b087e-148">Affiche la table qui contient la colonne jouant le rôle de clé primaire (ou unique) dans la relation sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="b087e-148">Shows which table contains the column acting as a primary (or unique) key in the selected relationship.</span></span>  
  
     <span data-ttu-id="b087e-149">**Colonnes clés Primary/Unique**</span><span class="sxs-lookup"><span data-stu-id="b087e-149">**Primary/Unique Key Columns**</span></span>  
     <span data-ttu-id="b087e-150">Affiche la colonne jouant le rôle de clé primaire (ou unique) dans la relation sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="b087e-150">Shows which column acts as a primary (or unique) key in the selected relationship.</span></span>  
  
     <span data-ttu-id="b087e-151">**Catégorie Identité**</span><span class="sxs-lookup"><span data-stu-id="b087e-151">**Identity Category**</span></span>  
     <span data-ttu-id="b087e-152">Se développe pour afficher les champs de propriété pour le **Nom** et la **Description**.</span><span class="sxs-lookup"><span data-stu-id="b087e-152">Expand to show the property fields for **Name** and **Description**.</span></span>  
  
     <span data-ttu-id="b087e-153">**Nom**</span><span class="sxs-lookup"><span data-stu-id="b087e-153">**Name**</span></span>  
     <span data-ttu-id="b087e-154">Indique le nom de la relation.</span><span class="sxs-lookup"><span data-stu-id="b087e-154">Shows the name of the relationship.</span></span> <span data-ttu-id="b087e-155">Lorsqu'une nouvelle relation est créée, elle obtient un nom par défaut basé sur la table affichée dans la fenêtre active du **Concepteur de tables**.</span><span class="sxs-lookup"><span data-stu-id="b087e-155">When a new relationship is created, it is given a default name based on the table in the active window in **Table Designer**.</span></span> <span data-ttu-id="b087e-156">Vous pouvez modifier le nom à tout moment.</span><span class="sxs-lookup"><span data-stu-id="b087e-156">You can change the name at any time.</span></span>  
  
     <span data-ttu-id="b087e-157">**Description**</span><span class="sxs-lookup"><span data-stu-id="b087e-157">**Description**</span></span>  
     <span data-ttu-id="b087e-158">Décrit la relation.</span><span class="sxs-lookup"><span data-stu-id="b087e-158">Describe the relationship.</span></span> <span data-ttu-id="b087e-159">Pour écrire une description plus détaillée, cliquez sur **Description** , puis sur le bouton de sélection **(...)** qui apparaît à droite du champ de propriété.</span><span class="sxs-lookup"><span data-stu-id="b087e-159">To write a more detailed description, click **Description** and then click the ellipsis **(...)** that appears to the right of the property field.</span></span> <span data-ttu-id="b087e-160">Vous obtiendrez une zone d'écriture plus large.</span><span class="sxs-lookup"><span data-stu-id="b087e-160">This provides a larger area in which to write text.</span></span>  
  
     <span data-ttu-id="b087e-161">**Catégorie Concepteur de tables**</span><span class="sxs-lookup"><span data-stu-id="b087e-161">**Table Designer Category**</span></span>  
     <span data-ttu-id="b087e-162">Se développe pour afficher des informations relatives aux options **Vérifier les données existantes à la création ou à la réactivation** et **Appliquer la réplication**.</span><span class="sxs-lookup"><span data-stu-id="b087e-162">Expand to show information for **Check Existing Data on Creation or Re-Enabling** and **Enforce for Replication**.</span></span>  
  
     <span data-ttu-id="b087e-163">**Appliquer la réplication**</span><span class="sxs-lookup"><span data-stu-id="b087e-163">**Enforce For Replication**</span></span>  
     <span data-ttu-id="b087e-164">Indique si la contrainte doit être appliquée lorsqu'un Agent de réplication effectue une requête Insert, Update ou Delete sur cette table.</span><span class="sxs-lookup"><span data-stu-id="b087e-164">Indicates whether to enforce the constraint when a replication agent performs an insert, update, or delete on this table.</span></span>  
  
     <span data-ttu-id="b087e-165">**Appliquer la contrainte de clé étrangère**</span><span class="sxs-lookup"><span data-stu-id="b087e-165">**Enforce Foreign Key Constraint**</span></span>  
     <span data-ttu-id="b087e-166">Spécifie si les modifications apportées aux données des colonnes dans la relation sont autorisées lorsqu'elles annulent l'intégrité de la relation de clé étrangère.</span><span class="sxs-lookup"><span data-stu-id="b087e-166">Specify whether changes are allowed to the data of the columns in the relationship if those changes would invalidate the integrity of the foreign key relationship.</span></span> <span data-ttu-id="b087e-167">Choisissez **Oui** si vous ne souhaitez pas autoriser de telles modifications et **Non** si vous souhaitez les autoriser.</span><span class="sxs-lookup"><span data-stu-id="b087e-167">Choose **Yes** if you do not want to allow such changes, and choose **No** if you do want to allow them.</span></span>  
  
     <span data-ttu-id="b087e-168">**Catégorie Spécification INSERT et UPDATE**</span><span class="sxs-lookup"><span data-stu-id="b087e-168">**INSERT and UPDATE Specification Category**</span></span>  
     <span data-ttu-id="b087e-169">Se développe pour afficher des informations relatives aux options **Règle de suppression** et **Règle de mise à jour** pour la relation.</span><span class="sxs-lookup"><span data-stu-id="b087e-169">Expand to show information for the **Delete Rule** and the **Update Rule** for the relationship.</span></span>  
  
     <span data-ttu-id="b087e-170">**Règle de suppression**</span><span class="sxs-lookup"><span data-stu-id="b087e-170">**Delete Rule**</span></span>  
     <span data-ttu-id="b087e-171">Spécifie ce qui se produit si un utilisateur tente de supprimer une ligne contenant des données impliquées dans une relation de clé étrangère :</span><span class="sxs-lookup"><span data-stu-id="b087e-171">Specify what happens if a user tries to delete a row with data that is involved in a foreign key relationship:</span></span>  
  
    -   <span data-ttu-id="b087e-172">**Aucune action** Un message d'erreur indique à l'utilisateur que la suppression n'est pas autorisée et la commande DELETE est annulée.</span><span class="sxs-lookup"><span data-stu-id="b087e-172">**No Action** An error message tells the user that the deletion is not allowed and the DELETE is rolled back.</span></span>  
  
    -   <span data-ttu-id="b087e-173">**Cascade** Supprime toutes les lignes contenant des données qui interviennent dans la relation de clé étrangère.</span><span class="sxs-lookup"><span data-stu-id="b087e-173">**Cascade** Deletes all rows containing data involved in the foreign key relationship.</span></span> <span data-ttu-id="b087e-174">Ne spécifiez pas CASCADE si la table est incluse dans une publication de fusion qui utilise des enregistrements logiques.</span><span class="sxs-lookup"><span data-stu-id="b087e-174">Do not specify CASCADE if the table will be included in a merge publication that uses logical records.</span></span>  
  
    -   <span data-ttu-id="b087e-175">**Définir Null** Affecte la valeur Null si toutes les colonnes clés étrangères de la table acceptent des valeurs Null.</span><span class="sxs-lookup"><span data-stu-id="b087e-175">**Set Null** Sets the value to null if all foreign key columns for the table can accept null values.</span></span>  
  
    -   <span data-ttu-id="b087e-176">**Définir la valeur par défaut** Définit la valeur par défaut définie pour la colonne si toutes les colonnes clés étrangères de la table ont des valeurs par défaut définies.</span><span class="sxs-lookup"><span data-stu-id="b087e-176">**Set Default** Sets the value to the default value defined for the column if all foreign key columns for the table have defaults defined for them.</span></span>  
  
     <span data-ttu-id="b087e-177">**Règle de mise à jour**</span><span class="sxs-lookup"><span data-stu-id="b087e-177">**Update Rule**</span></span>  
     <span data-ttu-id="b087e-178">Spécifie ce qui se produit si un utilisateur tente de mettre à jour une ligne contenant des données impliquées dans une relation de clé étrangère :</span><span class="sxs-lookup"><span data-stu-id="b087e-178">Specify what occurs if a user tries to update a row with data that is involved in a foreign key relationship:</span></span>  
  
    -   <span data-ttu-id="b087e-179">**Aucune action** Un message d'erreur indique à l'utilisateur que la mise à jour n'est pas autorisée et la commande UPDATE est annulée.</span><span class="sxs-lookup"><span data-stu-id="b087e-179">**No Action** An error message tells the user that the update is not allowed and the UPDATE is rolled back.</span></span>  
  
    -   <span data-ttu-id="b087e-180">**Cascade** Met à jour toutes les lignes contenant des données qui interviennent dans la relation de clé étrangère.</span><span class="sxs-lookup"><span data-stu-id="b087e-180">**Cascade** Updates all rows that contain data involved in the foreign key relationship.</span></span> <span data-ttu-id="b087e-181">Ne spécifiez pas CASCADE si la table est incluse dans une publication de fusion qui utilise des enregistrements logiques.</span><span class="sxs-lookup"><span data-stu-id="b087e-181">Do not specify CASCADE if the table will be included in a merge publication that uses logical records.</span></span>  
  
    -   <span data-ttu-id="b087e-182">**Définir Null** Affecte la valeur Null si toutes les colonnes clés étrangères de la table acceptent des valeurs Null.</span><span class="sxs-lookup"><span data-stu-id="b087e-182">**Set Null** Sets the value to null if all foreign key columns for the table can accept null values.</span></span>  
  
    -   <span data-ttu-id="b087e-183">**Définir la valeur par défaut** Affecte la valeur par défaut définie pour la colonne si toutes les colonnes clés étrangères de la table ont des valeurs par défaut définies.</span><span class="sxs-lookup"><span data-stu-id="b087e-183">**Set Default** Sets the value to the default value that is defined for the column if all foreign key columns for the table have defaults defined for them.</span></span>  
  
4.  <span data-ttu-id="b087e-184">Dans le menu **Fichier**, cliquez sur **Enregistrer**_nom de la table_.</span><span class="sxs-lookup"><span data-stu-id="b087e-184">On the **File** menu, click **Save**_table name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b087e-185">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b087e-185">Using Transact-SQL</span></span>  
 <span data-ttu-id="b087e-186">**Pour modifier une clé étrangère**</span><span class="sxs-lookup"><span data-stu-id="b087e-186">**To modify a foreign key**</span></span>  
  
 <span data-ttu-id="b087e-187">Pour modifier une contrainte FOREIGN KEY à l'aide de Transact-SQL, vous devez d'abord supprimer la contrainte FOREIGN KEY existante, puis la recréer avec sa nouvelle définition.</span><span class="sxs-lookup"><span data-stu-id="b087e-187">To modify a FOREIGN KEY constraint by using Transact-SQL, you must first delete the existing FOREIGN KEY constraint and then re-create it with the new definition.</span></span> <span data-ttu-id="b087e-188">Pour plus d'informations, consultez [Delete Foreign Key Relationships](delete-foreign-key-relationships.md) et [Create Foreign Key Relationships](create-foreign-key-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="b087e-188">For more information, see [Delete Foreign Key Relationships](delete-foreign-key-relationships.md) and [Create Foreign Key Relationships](create-foreign-key-relationships.md).</span></span>  
  
###  <a name="TsqlExample"></a>  
