---
title: Créer, modifier et supprimer des FileTables | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FileTables [SQL Server], altering
- FileTables [SQL Server], dropping
- FileTables [SQL Server], creating
ms.assetid: 47d69e37-8778-4630-809b-2261b5c41c2c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3a10e6333f6dd38a850a832b82a7cb7a0e0bf698
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601518"
---
# <a name="create-alter-and-drop-filetables"></a><span data-ttu-id="47c0b-102">Créer, modifier et supprimer des FileTables</span><span class="sxs-lookup"><span data-stu-id="47c0b-102">Create, Alter, and Drop FileTables</span></span>
  <span data-ttu-id="47c0b-103">Décrit la procédure de création d'un nouveau FileTable, ou de modification ou de suppression d'un FileTable existant.</span><span class="sxs-lookup"><span data-stu-id="47c0b-103">Describes how to create a new FileTable, or alter or drop an existing FileTable.</span></span>  
  
##  <a name="creating-a-filetable"></a><a name="BasicsCreate"></a> <span data-ttu-id="47c0b-104">Création d'un FileTable</span><span class="sxs-lookup"><span data-stu-id="47c0b-104">Creating a FileTable</span></span>  
 <span data-ttu-id="47c0b-105">Un FileTable est une table utilisateur spécialisée qui a un schéma prédéfini et fixe.</span><span class="sxs-lookup"><span data-stu-id="47c0b-105">A FileTable is a specialized user table that has a pre-defined and fixed schema.</span></span> <span data-ttu-id="47c0b-106">Ce schéma stocke des données FILESTREAM, des informations de répertoire et de fichier, ainsi que des attributs de fichier.</span><span class="sxs-lookup"><span data-stu-id="47c0b-106">This schema stores FILESTREAM data, file and directory information, and file attributes.</span></span> <span data-ttu-id="47c0b-107">Pour plus d'informations sur le schéma de FileTable, consultez [FileTable Schema](filetable-schema.md).</span><span class="sxs-lookup"><span data-stu-id="47c0b-107">For information about the FileTable schema, see [FileTable Schema](filetable-schema.md).</span></span>  
  
 <span data-ttu-id="47c0b-108">Vous pouvez créer un FileTable à l'aide de Transact-SQL ou de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="47c0b-108">You can create a new FileTable by using Transact-SQL or [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="47c0b-109">Puisqu'un FileTable dispose d'un schéma fixe, vous n'avez pas à spécifier une liste de colonnes.</span><span class="sxs-lookup"><span data-stu-id="47c0b-109">Since a FileTable has a fixed schema, you do not have to specify a list of columns.</span></span> <span data-ttu-id="47c0b-110">La syntaxe simple pour créer un FileTable vous permet de spécifier :</span><span class="sxs-lookup"><span data-stu-id="47c0b-110">The simple syntax for creating a FileTable lets you specify:</span></span>  
  
-   <span data-ttu-id="47c0b-111">Un nom de répertoire.</span><span class="sxs-lookup"><span data-stu-id="47c0b-111">A directory name.</span></span> <span data-ttu-id="47c0b-112">Dans la hiérarchie des dossiers FileTable, ce répertoire de niveau table devient l'enfant du répertoire de base de données spécifié au niveau de la base de données, et le parent des fichiers ou répertoires stocké dans la table.</span><span class="sxs-lookup"><span data-stu-id="47c0b-112">In the FileTable folder hierarchy, this table-level directory becomes the child of the database directory specified at the database level, and the parent of the files or directories stored in the table.</span></span>  
  
-   <span data-ttu-id="47c0b-113">Nom du classement à utiliser pour les noms de fichier dans la colonne **Nom** de FileTable.</span><span class="sxs-lookup"><span data-stu-id="47c0b-113">The name of the collation to be used for file names in the **Name** column of the FileTable.</span></span>  
  
-   <span data-ttu-id="47c0b-114">Noms à utiliser pour les 3 contraintes uniques et de clé primaire qui sont créées automatiquement.</span><span class="sxs-lookup"><span data-stu-id="47c0b-114">The names to be used for the 3 primary key and unique constraints that are automatically created.</span></span>  
  
###  <a name="how-to-create-a-filetable"></a><a name="HowToCreate"></a> <span data-ttu-id="47c0b-115">Procédure : Créer un FileTable</span><span class="sxs-lookup"><span data-stu-id="47c0b-115">How To: Create a FileTable</span></span>  
 <span data-ttu-id="47c0b-116">**Créer un FileTable à l'aide de Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="47c0b-116">**Create a FileTable by Using Transact-SQL**</span></span>  
 <span data-ttu-id="47c0b-117">Créez un FileTable en appelant l’instruction [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) avec l’option **AS FileTable**.</span><span class="sxs-lookup"><span data-stu-id="47c0b-117">Create a FileTable by calling the [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) statement with the **AS FileTable** option.</span></span> <span data-ttu-id="47c0b-118">Puisqu'un FileTable dispose d'un schéma fixe, vous n'avez pas à spécifier une liste de colonnes.</span><span class="sxs-lookup"><span data-stu-id="47c0b-118">Since a FileTable has a fixed schema, you do not have to specify a list of columns.</span></span> <span data-ttu-id="47c0b-119">Vous pouvez spécifier les paramètres suivants pour le nouveau FileTable :</span><span class="sxs-lookup"><span data-stu-id="47c0b-119">You can specify the following settings for the new FileTable:</span></span>  
  
1.  <span data-ttu-id="47c0b-120">**FILETABLE_DIRECTORY**.</span><span class="sxs-lookup"><span data-stu-id="47c0b-120">**FILETABLE_DIRECTORY**.</span></span> <span data-ttu-id="47c0b-121">Spécifie le répertoire qui sert de répertoire racine à tous les fichiers et répertoires stockés dans le FileTable.</span><span class="sxs-lookup"><span data-stu-id="47c0b-121">Specifies the directory that serves as the root directory for all the files and directories stored in the FileTable.</span></span> <span data-ttu-id="47c0b-122">Ce nom doit être unique parmi tous les noms de répertoire FileTable de la base de données.</span><span class="sxs-lookup"><span data-stu-id="47c0b-122">This name should be unique among all the FileTable directory names in the database.</span></span> <span data-ttu-id="47c0b-123">La comparaison d'unicité n'est pas sensible à la casse, indépendamment des paramètres de classement actuels.</span><span class="sxs-lookup"><span data-stu-id="47c0b-123">Comparison for uniqueness is case-insensitive, regardless of the current collation settings.</span></span>  
  
    -   <span data-ttu-id="47c0b-124">Cette valeur a le type de données **nvarchar(255)** et utilise le classement fixe **Latin1_General_CI_AS_KS_WS**.</span><span class="sxs-lookup"><span data-stu-id="47c0b-124">This value has a data type of **nvarchar(255)** and uses a fixed collation of **Latin1_General_CI_AS_KS_WS**.</span></span>  
  
    -   <span data-ttu-id="47c0b-125">Le nom de répertoire que vous fournissez doit se conformer aux configurations requises du système de fichiers concernant les noms de répertoire valides.</span><span class="sxs-lookup"><span data-stu-id="47c0b-125">The directory name that you provide must comply with the requirements of the file system for a valid directory name.</span></span>  
  
    -   <span data-ttu-id="47c0b-126">Ce nom doit être unique parmi tous les noms de répertoire FileTable de la base de données.</span><span class="sxs-lookup"><span data-stu-id="47c0b-126">This name should be unique among all the FileTable directory names in the database.</span></span> <span data-ttu-id="47c0b-127">La comparaison d'unicité n'est pas sensible à la casse, indépendamment des paramètres de classement actuels.</span><span class="sxs-lookup"><span data-stu-id="47c0b-127">Comparison for uniqueness is case-insensitive, regardless of the current collation settings.</span></span>  
  
    -   <span data-ttu-id="47c0b-128">Si vous ne fournissez pas un nom de répertoire lorsque vous créez le FileTable, le nom du FileTable lui-même est utilisé comme nom de répertoire.</span><span class="sxs-lookup"><span data-stu-id="47c0b-128">If you do not provide a directory name when you create the FileTable, then the name of the FileTable itself is used as the directory name.</span></span>  
  
2.  <span data-ttu-id="47c0b-129">**FILETABLE_COLLATE_FILENAME**.</span><span class="sxs-lookup"><span data-stu-id="47c0b-129">**FILETABLE_COLLATE_FILENAME**.</span></span> <span data-ttu-id="47c0b-130">Spécifie le nom du classement à appliquer à la colonne **Name** du FileTable.</span><span class="sxs-lookup"><span data-stu-id="47c0b-130">Specifies the name of the collation to be applied to the **Name** column in the FileTable.</span></span>  
  
    1.  <span data-ttu-id="47c0b-131">Le classement spécifié **ne doit pas être sensible à la casse** pour des raisons de conformité avec la sémantique de nom de fichier Windows.</span><span class="sxs-lookup"><span data-stu-id="47c0b-131">The specified collation must be **case-insensitive** to comply with Windows file naming semantics.</span></span>  
  
    2.  <span data-ttu-id="47c0b-132">Si vous ne fournissez pas de valeur pour **FILETABLE_COLLATE_FILENAME**ou spécifiez **database_default**, la colonne hérite du classement de la base de données active.</span><span class="sxs-lookup"><span data-stu-id="47c0b-132">If you do not provide a value for **FILETABLE_COLLATE_FILENAME**, or you specify **database_default**, the column inherits the collation of the current database.</span></span> <span data-ttu-id="47c0b-133">Si le classement de la base de données active respecte la casse, une erreur est générée et l’opération **CREATE TABLE** échoue.</span><span class="sxs-lookup"><span data-stu-id="47c0b-133">If the current database collation is case-sensitive, an error is raised and the **CREATE TABLE** operation fails.</span></span>  
  
3.  <span data-ttu-id="47c0b-134">Vous pouvez également spécifier les noms à utiliser pour les 3 contraintes uniques et de clé primaire qui sont créées automatiquement.</span><span class="sxs-lookup"><span data-stu-id="47c0b-134">You can also specify the names to be used for the 3 primary key and unique constraints that are automatically created.</span></span> <span data-ttu-id="47c0b-135">Si vous ne fournissez pas de noms, le système génère des noms comme décrit plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="47c0b-135">If you do not provide names, then the system generates names as described later in this topic.</span></span>  
  
    -   <span data-ttu-id="47c0b-136">**FILETABLE_PRIMARY_KEY_CONSTRAINT_NAME**</span><span class="sxs-lookup"><span data-stu-id="47c0b-136">**FILETABLE_PRIMARY_KEY_CONSTRAINT_NAME**</span></span>  
  
    -   <span data-ttu-id="47c0b-137">**FILETABLE_STREAMID_UNIQUE_CONSTRAINT_NAME**</span><span class="sxs-lookup"><span data-stu-id="47c0b-137">**FILETABLE_STREAMID_UNIQUE_CONSTRAINT_NAME**</span></span>  
  
    -   <span data-ttu-id="47c0b-138">**FILETABLE_FULLPATH_UNIQUE_CONSTRAINT_NAME**</span><span class="sxs-lookup"><span data-stu-id="47c0b-138">**FILETABLE_FULLPATH_UNIQUE_CONSTRAINT_NAME**</span></span>  
  
 <span data-ttu-id="47c0b-139">**Exemples**</span><span class="sxs-lookup"><span data-stu-id="47c0b-139">**Examples**</span></span>  
  
 <span data-ttu-id="47c0b-140">L’exemple suivant crée un FileTable et spécifie les valeurs définies par l’utilisateur pour **FILETABLE_DIRECTORY** et **FILETABLE_COLLATE_FILENAME**.</span><span class="sxs-lookup"><span data-stu-id="47c0b-140">The following example creates a new FileTable and specifies user-defined values for both **FILETABLE_DIRECTORY** and **FILETABLE_COLLATE_FILENAME**.</span></span>  
  
```sql  
CREATE TABLE DocumentStore AS FileTable  
    WITH (   
          FileTable_Directory = 'DocumentTable',  
          FileTable_Collate_Filename = database_default  
         );  
GO  
```  
  
 <span data-ttu-id="47c0b-141">L'exemple suivant crée également un nouveau FileTable.</span><span class="sxs-lookup"><span data-stu-id="47c0b-141">The following example also creates a new FileTable.</span></span> <span data-ttu-id="47c0b-142">Étant donné que les valeurs définies par l’utilisateur ne sont pas spécifiées, la valeur de **FILETABLE_DIRECTORY** devient le nom du FileTable, la valeur de **FILETABLE_COLLATE_FILENAME** devient database_default et les contraintes uniques et de clé primaire reçoivent des noms générés par le système.</span><span class="sxs-lookup"><span data-stu-id="47c0b-142">Since user-defined values are not specified, the value of **FILETABLE_DIRECTORY** becomes the name of the FileTable, the value of **FILETABLE_COLLATE_FILENAME** becomes database_default, and the primary key and unique contraints receive system-generated names.</span></span>  
  
```sql  
CREATE TABLE DocumentStore AS FileTable;  
GO  
```  
  
 <span data-ttu-id="47c0b-143">**Créer un FileTable à l'aide de SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="47c0b-143">**Create a FileTable by Using SQL Server Management Studio**</span></span>  
 <span data-ttu-id="47c0b-144">Dans l’Explorateur d’objets, développez les objets sous la base de données sélectionnée, cliquez avec le bouton droit sur le dossier **Tables** , puis sélectionnez **Nouveau FileTable**.</span><span class="sxs-lookup"><span data-stu-id="47c0b-144">In Object Explorer, expand the objects under the selected database, then right-click on the **Tables** folder, and then select **New FileTable**.</span></span>  
  
 <span data-ttu-id="47c0b-145">Cette option ouvre une nouvelle fenêtre de script qui contient un modèle de script Transact-SQL que vous pouvez personnaliser et exécuter pour créer un FileTable.</span><span class="sxs-lookup"><span data-stu-id="47c0b-145">This option opens a new script window which contains a Transact-SQL script template that you can customize and run to create a FileTable.</span></span> <span data-ttu-id="47c0b-146">Utilisez l'option **Spécifier les valeurs des paramètres du modèle** dans le menu **Requête** pour personnaliser le script facilement.</span><span class="sxs-lookup"><span data-stu-id="47c0b-146">Use the **Specify Values for Template Parameters** option on the **Query** menu to customize the script easily.</span></span>  
  
###  <a name="requirements-and-restrictions-for-creating-a-filetable"></a><a name="ReqCreate"></a> <span data-ttu-id="47c0b-147">Exigences et restrictions concernant la création d'un FileTable</span><span class="sxs-lookup"><span data-stu-id="47c0b-147">Requirements and Restrictions for Creating a FileTable</span></span>  
  
-   <span data-ttu-id="47c0b-148">Vous ne pouvez pas modifier une table existante pour la convertir en FileTable.</span><span class="sxs-lookup"><span data-stu-id="47c0b-148">You cannot alter an existing table to convert it into a FileTable.</span></span>  
  
-   <span data-ttu-id="47c0b-149">Le répertoire parent précédemment spécifié au niveau de la base de données doit avoir une valeur non Null.</span><span class="sxs-lookup"><span data-stu-id="47c0b-149">The parent directory previously specified at the database level must have a non-null value.</span></span> <span data-ttu-id="47c0b-150">Pour plus d’informations sur la spécification du répertoire au niveau de la base de données, consultez [Activer les conditions préalables pour les FileTables](enable-the-prerequisites-for-filetable.md).</span><span class="sxs-lookup"><span data-stu-id="47c0b-150">For information about specifying the database-level directory, see [Enable the Prerequisites for FileTable](enable-the-prerequisites-for-filetable.md).</span></span>  
  
-   <span data-ttu-id="47c0b-151">Puisqu'un FileTable contient une colonne FILESTREAM, un FileTable requiert un groupe de fichiers FILESTREAM valide.</span><span class="sxs-lookup"><span data-stu-id="47c0b-151">A FileTable requires a valid FILESTREAM filegroup, since a FileTable contains a FILESTREAM column.</span></span> <span data-ttu-id="47c0b-152">Vous pouvez éventuellement spécifier un groupe de fichiers FILESTREAM valide dans le cadre de la commande **CREATE TABLE** pour la création d'un FileTable.</span><span class="sxs-lookup"><span data-stu-id="47c0b-152">You can optionally specify a valid FILESTREAM filegroup as part of the **CREATE TABLE** command for creating a FileTable.</span></span> <span data-ttu-id="47c0b-153">Si vous ne spécifiez pas de groupe de fichiers, le FileTable utilise le groupe de fichiers FILESTREAM par défaut pour la base de données.</span><span class="sxs-lookup"><span data-stu-id="47c0b-153">If you do not specify a filegroup, then the FileTable uses the default FILESTREAM filegroup for the database.</span></span> <span data-ttu-id="47c0b-154">Si la base de données n'a pas de groupe de fichiers FILESTREAM, une erreur est générée.</span><span class="sxs-lookup"><span data-stu-id="47c0b-154">If the database does not have a FILESTREAM filegroup, then an error is raised.</span></span>  
  
-   <span data-ttu-id="47c0b-155">Vous ne pouvez pas créer de contrainte de table dans le cadre d’une instruction **CREATE TABLE...AS FILETABLE**.</span><span class="sxs-lookup"><span data-stu-id="47c0b-155">You cannot create a table constraint as part of a **CREATE TABLE...AS FILETABLE** statement.</span></span> <span data-ttu-id="47c0b-156">Toutefois, vous pouvez ajouter la contrainte ultérieurement à l'aide d'une instruction **ALTER TABLE** .</span><span class="sxs-lookup"><span data-stu-id="47c0b-156">However you can add the constraint later by using an **ALTER TABLE** statement.</span></span>  
  
-   <span data-ttu-id="47c0b-157">Vous ne pouvez pas créer de FileTable dans la base de données **tempdb** ni dans aucune des autres bases de données système.</span><span class="sxs-lookup"><span data-stu-id="47c0b-157">You cannot create a FileTable in the **tempdb** database or in any of the other system databases.</span></span>  
  
-   <span data-ttu-id="47c0b-158">Vous ne pouvez pas créer de FileTable comme table temporaire.</span><span class="sxs-lookup"><span data-stu-id="47c0b-158">You cannot create a FileTable as a temporary table.</span></span>  
  
##  <a name="altering-a-filetable"></a><a name="BasicsAlter"></a> <span data-ttu-id="47c0b-159">Modification d'un FileTable</span><span class="sxs-lookup"><span data-stu-id="47c0b-159">Altering a FileTable</span></span>  
 <span data-ttu-id="47c0b-160">Puisqu'un FileTable dispose d'un schéma prédéfini et fixe, vous ne pouvez pas ajouter ni modifier ses colonnes.</span><span class="sxs-lookup"><span data-stu-id="47c0b-160">Since a FileTable has a pre-defined and fixed schema, you cannot add or change its columns.</span></span> <span data-ttu-id="47c0b-161">Toutefois, vous pouvez ajouter des index personnalisés, des déclencheurs, des contraintes et d'autres options à un FileTable.</span><span class="sxs-lookup"><span data-stu-id="47c0b-161">However, you can add custom indexes, triggers, constraints, and other options to a FileTable.</span></span>  
  
 <span data-ttu-id="47c0b-162">Pour plus d’informations sur l’utilisation de l’instruction ALTER TABLE pour activer ou désactiver l’espace de noms FileTable, dont les contraintes définies par le système, consultez [Gérer des FileTables](manage-filetables.md).</span><span class="sxs-lookup"><span data-stu-id="47c0b-162">For information about using the ALTER TABLE statement to enable or disable the FileTable namespace, including the system-defined constraints, see [Manage FileTables](manage-filetables.md).</span></span>  
  
###  <a name="how-to-change-the-directory-for-a-filetable"></a><a name="HowToChange"></a> <span data-ttu-id="47c0b-163">Procédure : modifier le répertoire d’un FileTable</span><span class="sxs-lookup"><span data-stu-id="47c0b-163">How To: Change the Directory for a FileTable</span></span>  
 <span data-ttu-id="47c0b-164">**Modifier le répertoire d'un FileTable à l'aide de Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="47c0b-164">**Change the Directory for a FileTable by Using Transact-SQL**</span></span>  
 <span data-ttu-id="47c0b-165">Appelez l’instruction ALTER TABLE et fournissez une nouvelle valeur valide pour l’option SET **FILETABLE_DIRECTORY** .</span><span class="sxs-lookup"><span data-stu-id="47c0b-165">Call the ALTER TABLE statement and provide a valid new value for the **FILETABLE_DIRECTORY** SET option.</span></span>  
  
 <span data-ttu-id="47c0b-166">**Exemple**</span><span class="sxs-lookup"><span data-stu-id="47c0b-166">**Example**</span></span>  
  
```sql  
ALTER TABLE filetable_name  
    SET ( FILETABLE_DIRECTORY = N'directory_name' );  
GO  
```  
  
 <span data-ttu-id="47c0b-167">**Lodifier le répertoire d'un FileTables à l'aide de SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="47c0b-167">**Change the Directory for a FileTable by Using SQL Server Management Studio**</span></span>  
 <span data-ttu-id="47c0b-168">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur le FileTable et sélectionnez **Propriétés** pour ouvrir la boîte de dialogue **Propriétés d’une table** .</span><span class="sxs-lookup"><span data-stu-id="47c0b-168">In Object Explorer, right-click on the FileTable and select **Properties** to open the **Table Properties** dialog box.</span></span> <span data-ttu-id="47c0b-169">Dans la page **FileTable** , entrez la valeur pour **Nom du répertoire FileTable**.</span><span class="sxs-lookup"><span data-stu-id="47c0b-169">On the **FileTable** page, enter a new value for **FileTable directory name**.</span></span>  
  
###  <a name="requirements-and-restrictions-for-altering-a-filetable"></a><a name="ReqAlter"></a> <span data-ttu-id="47c0b-170">Exigences et restrictions concernant la modification d'un FileTable</span><span class="sxs-lookup"><span data-stu-id="47c0b-170">Requirements and Restrictions for Altering a FileTable</span></span>  
  
-   <span data-ttu-id="47c0b-171">Vous ne pouvez pas modifier la valeur de **FILETABLE_COLLATE_FILENAME**.</span><span class="sxs-lookup"><span data-stu-id="47c0b-171">You cannot alter the value of **FILETABLE_COLLATE_FILENAME**.</span></span>  
  
-   <span data-ttu-id="47c0b-172">Vous ne pouvez pas changer, supprimer ni désactiver les colonnes définies par le système d'un FileTable.</span><span class="sxs-lookup"><span data-stu-id="47c0b-172">You cannot change, drop, or disable the system-defined columns of a FileTable.</span></span>  
  
-   <span data-ttu-id="47c0b-173">Vous ne pouvez pas ajouter de nouvelles colonnes d'utilisateur, de colonnes calculées ou de colonnes calculées persistantes à un FileTable.</span><span class="sxs-lookup"><span data-stu-id="47c0b-173">You cannot add new user columns, computed columns, or persisted computed columns to a FileTable.</span></span>  
  
##  <a name="dropping-a-filetable"></a><a name="BasicsDrop"></a> <span data-ttu-id="47c0b-174">Suppression d'un FileTable</span><span class="sxs-lookup"><span data-stu-id="47c0b-174">Dropping a FileTable</span></span>  
 <span data-ttu-id="47c0b-175">Vous pouvez supprimer un FileTable en utilisant la syntaxe ordinaire de l’instruction [DROP TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="47c0b-175">You can drop a FileTable by using the ordinary syntax for the [DROP TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-table-transact-sql) statement.</span></span>  
  
 <span data-ttu-id="47c0b-176">Lorsque vous supprimez un FileTable, les objets suivants sont également supprimés :</span><span class="sxs-lookup"><span data-stu-id="47c0b-176">When you drop a FileTable, the following objects are also dropped:</span></span>  
  
-   <span data-ttu-id="47c0b-177">Toutes les colonnes du FileTable et tous les objets associés à la table, tels que les index, les contraintes et les déclencheurs, sont également supprimés.</span><span class="sxs-lookup"><span data-stu-id="47c0b-177">All the columns of the FileTable and all the objects associated with the table, such as indexes, constraints, and triggers, are also dropped.</span></span>  
  
-   <span data-ttu-id="47c0b-178">Le répertoire FileTable et les sous-répertoires qu'il contenait disparaissent de la hiérarchie de répertoires et de fichiers FILESTREAM de la base de données.</span><span class="sxs-lookup"><span data-stu-id="47c0b-178">The FileTable directory and the sub-directories that it contained disappear from the FILESTREAM file and directory hierarchy of the database.</span></span>  
  
 <span data-ttu-id="47c0b-179">La commande DROP TABLE échoue si des descripteurs de fichiers sont ouverts dans l’espace de noms du fichier du FileTable.</span><span class="sxs-lookup"><span data-stu-id="47c0b-179">The DROP TABLE command fails if there are open file handles in the FileTable's file namespace.</span></span> <span data-ttu-id="47c0b-180">Pour plus d’informations sur la fermeture de descripteurs ouverts, consultez [Gérer des FileTables](manage-filetables.md).</span><span class="sxs-lookup"><span data-stu-id="47c0b-180">For information about closing open handles, see [Manage FileTables](manage-filetables.md).</span></span>  
  
##  <a name="other-database-objects-are-created-when-you-create-a-filetable"></a><a name="BasicsOtherObjects"></a> <span data-ttu-id="47c0b-181">D'autres objets de base de données sont créés lorsque vous créez un FileTable</span><span class="sxs-lookup"><span data-stu-id="47c0b-181">Other Database Objects Are Created When You Create a FileTable</span></span>  
 <span data-ttu-id="47c0b-182">Lorsque vous créez un nouveau FileTable, quelques contraintes et index définis par le système sont également créés.</span><span class="sxs-lookup"><span data-stu-id="47c0b-182">When you create a new FileTable, some system-defined indexes and constraints are also created.</span></span> <span data-ttu-id="47c0b-183">Vous ne pouvez pas modifier ou supprimer ces objets ; ils disparaissent uniquement lorsque le FileTable lui-même est supprimé.</span><span class="sxs-lookup"><span data-stu-id="47c0b-183">You cannot alter or drop these objects; they disappear only when the FileTable itself is dropped.</span></span> <span data-ttu-id="47c0b-184">Pour consulter la liste de ces objets, interrogez l’affichage catalogue [sys.filetable_system_defined_objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-filetable-system-defined-objects-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="47c0b-184">To see the list of these objects, query the catalog view [sys.filetable_system_defined_objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-filetable-system-defined-objects-transact-sql).</span></span>  
  
```sql  
--View all objects for all filetables, unsorted  
SELECT * FROM sys.filetable_system_defined_objects;  
GO  
  
--View sorted list with friendly names  
SELECT OBJECT_NAME(parent_object_id) AS 'FileTable', OBJECT_NAME(object_id) AS 'System-defined Object'  
    FROM sys.filetable_system_defined_objects  
    ORDER BY FileTable, 'System-defined Object';  
GO  
```  
  
 <span data-ttu-id="47c0b-185">**Index créés lorsque vous créez un FileTable**</span><span class="sxs-lookup"><span data-stu-id="47c0b-185">**Indexes that are created when you create a new FileTable**</span></span>  
 <span data-ttu-id="47c0b-186">Lorsque vous créez un FileTable, les index définis par le système suivants sont également créés :</span><span class="sxs-lookup"><span data-stu-id="47c0b-186">When you create a new FileTable, the following system-defined indexes are also created:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="47c0b-187">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="47c0b-187">**Columns**</span></span>|<span data-ttu-id="47c0b-188">**Type d'index**</span><span class="sxs-lookup"><span data-stu-id="47c0b-188">**Index type**</span></span>|  
|<span data-ttu-id="47c0b-189">[path_locator] ASC</span><span class="sxs-lookup"><span data-stu-id="47c0b-189">[path_locator] ASC</span></span>|<span data-ttu-id="47c0b-190">Clé primaire, non-cluster</span><span class="sxs-lookup"><span data-stu-id="47c0b-190">Primary Key, nonclustered</span></span>|  
|<span data-ttu-id="47c0b-191">[parent_path_locator] ASC,</span><span class="sxs-lookup"><span data-stu-id="47c0b-191">[parent_path_locator] ASC,</span></span><br /><br /> <span data-ttu-id="47c0b-192">[name] ASC</span><span class="sxs-lookup"><span data-stu-id="47c0b-192">[name] ASC</span></span>|<span data-ttu-id="47c0b-193">Unique, non-cluster</span><span class="sxs-lookup"><span data-stu-id="47c0b-193">Unique, nonclustered</span></span>|  
|<span data-ttu-id="47c0b-194">[stream_id] ASC</span><span class="sxs-lookup"><span data-stu-id="47c0b-194">[stream_id] ASC</span></span>|<span data-ttu-id="47c0b-195">Unique, non-cluster</span><span class="sxs-lookup"><span data-stu-id="47c0b-195">Unique, nonclustered</span></span>|  
  
 <span data-ttu-id="47c0b-196">**Contraintes créées lorsque vous créez un FileTable**</span><span class="sxs-lookup"><span data-stu-id="47c0b-196">**Constraints that are created when you create a new FileTable**</span></span>  
 <span data-ttu-id="47c0b-197">Lorsque vous créez un FileTable, les contraintes définies par le système suivantes sont également créées :</span><span class="sxs-lookup"><span data-stu-id="47c0b-197">When you create a new FileTable, the following system-defined constraints are also created:</span></span>  
  
|<span data-ttu-id="47c0b-198">Contraintes</span><span class="sxs-lookup"><span data-stu-id="47c0b-198">Constraints</span></span>|<span data-ttu-id="47c0b-199">Applique</span><span class="sxs-lookup"><span data-stu-id="47c0b-199">Enforces</span></span>|  
|-----------------|--------------|  
|<span data-ttu-id="47c0b-200">Contraintes par défaut sur les colonnes suivantes :</span><span class="sxs-lookup"><span data-stu-id="47c0b-200">Default constraints on the following columns:</span></span><br /><br /> <span data-ttu-id="47c0b-201">**creation_time**</span><span class="sxs-lookup"><span data-stu-id="47c0b-201">**creation_time**</span></span> <br /> <span data-ttu-id="47c0b-202">**is_archive**</span><span class="sxs-lookup"><span data-stu-id="47c0b-202">**is_archive**</span></span> <br /> <span data-ttu-id="47c0b-203">**is_directory**</span><span class="sxs-lookup"><span data-stu-id="47c0b-203">**is_directory**</span></span> <br /> <span data-ttu-id="47c0b-204">**is_hidden**</span><span class="sxs-lookup"><span data-stu-id="47c0b-204">**is_hidden**</span></span> <br /> <span data-ttu-id="47c0b-205">**is_offline**</span><span class="sxs-lookup"><span data-stu-id="47c0b-205">**is_offline**</span></span> <br /> <span data-ttu-id="47c0b-206">**is_readonly**</span><span class="sxs-lookup"><span data-stu-id="47c0b-206">**is_readonly**</span></span> <br /> <span data-ttu-id="47c0b-207">**is_system**</span><span class="sxs-lookup"><span data-stu-id="47c0b-207">**is_system**</span></span> <br /> <span data-ttu-id="47c0b-208">**is_temporary**</span><span class="sxs-lookup"><span data-stu-id="47c0b-208">**is_temporary**</span></span> <br /> <span data-ttu-id="47c0b-209">**last_access_time**</span><span class="sxs-lookup"><span data-stu-id="47c0b-209">**last_access_time**</span></span> <br /> <span data-ttu-id="47c0b-210">**last_write_time**</span><span class="sxs-lookup"><span data-stu-id="47c0b-210">**last_write_time**</span></span> <br /> <span data-ttu-id="47c0b-211">**path_locator**</span><span class="sxs-lookup"><span data-stu-id="47c0b-211">**path_locator**</span></span> <br /> <span data-ttu-id="47c0b-212">**stream_id**</span><span class="sxs-lookup"><span data-stu-id="47c0b-212">**stream_id**</span></span>|<span data-ttu-id="47c0b-213">Les contraintes par défaut définies par le système appliquent les valeurs par défaut pour les colonnes spécifiées.</span><span class="sxs-lookup"><span data-stu-id="47c0b-213">The system-defined default constraints enforce default values for the specified columns.</span></span>|  
|<span data-ttu-id="47c0b-214">Contraintes de validation</span><span class="sxs-lookup"><span data-stu-id="47c0b-214">Check constraints</span></span>|<span data-ttu-id="47c0b-215">Les contraintes de validation définies par le système appliquent les spécifications requises suivantes :</span><span class="sxs-lookup"><span data-stu-id="47c0b-215">The system-defined check constraints enforce the following requirements:</span></span><br /><br /> <span data-ttu-id="47c0b-216">Noms de fichier valides.</span><span class="sxs-lookup"><span data-stu-id="47c0b-216">Valid filenames.</span></span><br /><br /> <span data-ttu-id="47c0b-217">Attributs de fichier valides.</span><span class="sxs-lookup"><span data-stu-id="47c0b-217">Valid file attributes.</span></span><br /><br /> <span data-ttu-id="47c0b-218">L'objet parent doit être un répertoire.</span><span class="sxs-lookup"><span data-stu-id="47c0b-218">Parent object must be a directory.</span></span><br /><br /> <span data-ttu-id="47c0b-219">La hiérarchie d'espace de noms est verrouillée pendant la manipulation de fichier.</span><span class="sxs-lookup"><span data-stu-id="47c0b-219">Namespace hierarchy is locked during file manipulation.</span></span>|  
  
 <span data-ttu-id="47c0b-220">**Convention d'affectation des noms pour les contraintes définies par le système**</span><span class="sxs-lookup"><span data-stu-id="47c0b-220">**Naming convention for the system-defined constraints**</span></span>  
 <span data-ttu-id="47c0b-221">Les contraintes définies par le système décrites ci-dessus sont nommées selon le format **\<constraintType>_\<tablename>[\_\<columnname>]\_\<uniquifier>** , où :</span><span class="sxs-lookup"><span data-stu-id="47c0b-221">The system-defined constraints described above are named in the format **\<constraintType>_\<tablename>[\_\<columnname>]\_\<uniquifier>** where:</span></span>  
  
-   <span data-ttu-id="47c0b-222">*<type_contrainte>* est CK (contrainte de validation), DF (contrainte par défaut), FK (clé étrangère), PK (clé primaire) ou UQ (contrainte unique).</span><span class="sxs-lookup"><span data-stu-id="47c0b-222">*<constraint_type>* is CK (check constraint), DF (default constraint), FK (foreign key), PK (primary key), or UQ (unique constraint).</span></span>  
  
-   <span data-ttu-id="47c0b-223">*\<uniquifier>* est une chaîne générée par le système pour rendre le nom unique.</span><span class="sxs-lookup"><span data-stu-id="47c0b-223">*\<uniquifier>* is a system-generated string to make the name unique.</span></span> <span data-ttu-id="47c0b-224">Cette chaîne peut contenir le nom du FileTable et un identificateur unique.</span><span class="sxs-lookup"><span data-stu-id="47c0b-224">This string may contain the FileTable name and a unique identifier.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47c0b-225">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="47c0b-225">See Also</span></span>  
 [<span data-ttu-id="47c0b-226">Gérer des FileTables</span><span class="sxs-lookup"><span data-stu-id="47c0b-226">Manage FileTables</span></span>](manage-filetables.md)  
  
  
