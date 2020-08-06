---
title: Charger des fichiers dans FileTables | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FileTables [SQL Server], migrating files
- FileTables [SQL Server], bulk loading
- FileTables [SQL Server], loading files
ms.assetid: dc842a10-0586-4b0f-9775-5ca0ecc761d9
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 43ea31523da2dfa8b387f68ce4f7c7f07868dd6f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707615"
---
# <a name="load-files-into-filetables"></a><span data-ttu-id="0b0d4-102">Charger des fichiers dans FileTables</span><span class="sxs-lookup"><span data-stu-id="0b0d4-102">Load Files into FileTables</span></span>
  <span data-ttu-id="0b0d4-103">Explique comment charger ou migrer des fichiers dans FileTables.</span><span class="sxs-lookup"><span data-stu-id="0b0d4-103">Describes how to load or migrate files into FileTables.</span></span>  
  
##  <a name="loading-or-migrating-files-into-a-filetable"></a><a name="BasicsLoadNew"></a> <span data-ttu-id="0b0d4-104">Chargement ou migration de fichiers dans un FileTable</span><span class="sxs-lookup"><span data-stu-id="0b0d4-104">Loading or Migrating Files into a FileTable</span></span>  
 <span data-ttu-id="0b0d4-105">La méthode que vous choisissez pour le chargement ou la migration de fichiers dans un FileTable dépend de l'emplacement de stockage actuel des fichiers.</span><span class="sxs-lookup"><span data-stu-id="0b0d4-105">The method that you choose for loading or migrating files into a FileTable depends on where the files are currently stored.</span></span>  
  
|<span data-ttu-id="0b0d4-106">Emplacement actuel des fichiers</span><span class="sxs-lookup"><span data-stu-id="0b0d4-106">Current location of files</span></span>|<span data-ttu-id="0b0d4-107">Options de migration</span><span class="sxs-lookup"><span data-stu-id="0b0d4-107">Options for migration</span></span>|  
|-------------------------------|---------------------------|  
|<span data-ttu-id="0b0d4-108">Les fichiers sont actuellement stockés dans le système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="0b0d4-108">Files are currently stored in the file system.</span></span><br /><br /> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="0b0d4-109">n'a aucune connaissance des fichiers.</span><span class="sxs-lookup"><span data-stu-id="0b0d4-109">has no knowledge of the files.</span></span>|<span data-ttu-id="0b0d4-110">Étant donné qu'un FileTable s'affiche en tant que dossier dans le système de fichiers Windows, vous pouvez charger facilement des fichiers dans un nouveau FileTable en faisant appel à l'une des méthodes disponibles pour le déplacement ou la copie de fichiers.</span><span class="sxs-lookup"><span data-stu-id="0b0d4-110">Since a FileTable appears as a folder in the Windows file system, you can easily load files into a new FileTable by using any of the available methods for moving or copying files.</span></span> <span data-ttu-id="0b0d4-111">Ces méthodes incluent l'Explorateur Windows, les options de ligne de commande, notamment xcopy et robocopy, ainsi que les applications ou les scripts personnalisés.</span><span class="sxs-lookup"><span data-stu-id="0b0d4-111">These methods include Windows Explorer, command line options including xcopy and robocopy, and custom scripts or applications.</span></span><br /><br /> <span data-ttu-id="0b0d4-112">Il est impossible de convertir un dossier existant en FileTable.</span><span class="sxs-lookup"><span data-stu-id="0b0d4-112">You cannot convert an existing folder to a FileTable.</span></span>|  
|<span data-ttu-id="0b0d4-113">Les fichiers sont actuellement stockés dans le système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="0b0d4-113">Files are currently stored in the file system.</span></span><br /><br /> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="0b0d4-114">contient une table de métadonnées qui contient des pointeurs sur les fichiers.</span><span class="sxs-lookup"><span data-stu-id="0b0d4-114">contains a table of metadata that contains pointers to the files.</span></span>|<span data-ttu-id="0b0d4-115">La première étape consiste à déplacer ou à copier les fichiers à l'aide de l'une des méthodes indiquées ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="0b0d4-115">The first step is to move or copy the files by using one of the methods mentioned above.</span></span><br /><br /> <span data-ttu-id="0b0d4-116">La deuxième étape consiste à mettre à jour la table de métadonnées existante de sorte qu'elle pointe sur le nouvel emplacement des fichiers.</span><span class="sxs-lookup"><span data-stu-id="0b0d4-116">The second step is to update the existing table of metadata to point to the new location of the files.</span></span><br /><br /> <span data-ttu-id="0b0d4-117">Pour plus d'informations, consultez [Exemple : migration de fichiers à partir du système de fichiers dans un FileTable](#HowToMigrateFiles) dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="0b0d4-117">For more information, see [Example: Migrating Files from the File System into a FileTable](#HowToMigrateFiles) in this topic.</span></span>|  
  
###  <a name="how-to-load-files-into-a-filetable"></a><a name="HowToLoadNew"></a> <span data-ttu-id="0b0d4-118">Procédure : charger des fichiers dans un FileTable</span><span class="sxs-lookup"><span data-stu-id="0b0d4-118">How To: Load Files into a FileTable</span></span>  
 <span data-ttu-id="0b0d4-119">Voici quelques-unes des méthodes que vous pouvez appliquer pour charger des fichiers dans un FileTable :</span><span class="sxs-lookup"><span data-stu-id="0b0d4-119">The methods that you can use to load files into a FileTable include the following:</span></span>  
  
-   <span data-ttu-id="0b0d4-120">Faites glisser et déplacez des fichiers depuis les dossiers source vers le nouveau dossier FileTable dans l'Explorateur Windows.</span><span class="sxs-lookup"><span data-stu-id="0b0d4-120">Drag and drop files from the source folders to the new FileTable folder in Windows Explorer.</span></span>  
  
-   <span data-ttu-id="0b0d4-121">Utilisez les options de ligne de commande telles que MOVE, COPY, XCOPY ou ROBOCOPY de l'invite de commandes ou dans un fichier de commandes ou un script.</span><span class="sxs-lookup"><span data-stu-id="0b0d4-121">Use command line options such as MOVE, COPY, XCOPY, or ROBOCOPY from the command prompt or in a batch file or script.</span></span>  
  
-   <span data-ttu-id="0b0d4-122">Écrivez une application personnalisée en C# ou Visual Basic.NET qui utilise des méthodes de l’espace de noms **System.IO** pour déplacer ou copier les fichiers.</span><span class="sxs-lookup"><span data-stu-id="0b0d4-122">Write a custom application in C# or Visual Basic.NET that uses methods from the **System.IO** namespace to move or copy the files.</span></span>  
  
###  <a name="example-migrating-files-from-the-file-system-into-a-filetable"></a><a name="HowToMigrateFiles"></a> <span data-ttu-id="0b0d4-123">Exemple : migration de fichiers à partir du système de fichiers dans un FileTable</span><span class="sxs-lookup"><span data-stu-id="0b0d4-123">Example: Migrating Files from the File System into a FileTable</span></span>  
 <span data-ttu-id="0b0d4-124">Dans ce scénario, vos fichiers sont stockés dans le système de fichiers et vous disposez d'une table de métadonnées dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui contient des pointeurs sur les fichiers.</span><span class="sxs-lookup"><span data-stu-id="0b0d4-124">In this scenario, your files are stored in the file system, and you have a table of metadata in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that contains pointers to the files.</span></span> <span data-ttu-id="0b0d4-125">Vous souhaitez déplacer les fichiers dans un FileTable, puis remplacer le chemin UNC d'origine pour chaque fichier dans les métadonnées par le chemin UNC de FileTable.</span><span class="sxs-lookup"><span data-stu-id="0b0d4-125">You want to move the files into a FileTable, and then replace the original UNC path for each file in the metadata with the FileTable UNC path.</span></span> <span data-ttu-id="0b0d4-126">La fonction [GetPathLocator &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/getpathlocator-transact-sql) vous aide à accomplir cet objectif.</span><span class="sxs-lookup"><span data-stu-id="0b0d4-126">The [GetPathLocator &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/getpathlocator-transact-sql) function helps you to achieve this goal.</span></span>  
  
 <span data-ttu-id="0b0d4-127">Pour cet exemple, supposons qu’il existe une table de base de données existante, `PhotoMetadata` , qui contient des données sur les photographies.</span><span class="sxs-lookup"><span data-stu-id="0b0d4-127">For this example, assume that there is an existing database table, `PhotoMetadata`, which contains data about photographs.</span></span> <span data-ttu-id="0b0d4-128">Cette table comprend une colonne `UNCPath` de type `varchar` (512) qui contient le chemin UNC réel d’accès à un fichier .jpg.</span><span class="sxs-lookup"><span data-stu-id="0b0d4-128">This table has a column `UNCPath` of type `varchar`(512) which contains the actual UNC path to a .jpg file.</span></span>  
  
 <span data-ttu-id="0b0d4-129">Pour migrer les fichiers image du système de fichiers vers un FileTable, vous devez effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="0b0d4-129">To migrate the image files from the file system into a FileTable, you have to do the following:</span></span>  
  
1.  <span data-ttu-id="0b0d4-130">Créez un nouveau FileTable pour contenir les fichiers.</span><span class="sxs-lookup"><span data-stu-id="0b0d4-130">Create a new FileTable to hold the files.</span></span> <span data-ttu-id="0b0d4-131">Cet exemple utilise le nom de la table, `dbo.PhotoTable`, mais ne fournit pas le code permettant de créer la table.</span><span class="sxs-lookup"><span data-stu-id="0b0d4-131">This example uses the table name, `dbo.PhotoTable`, but does not show the code to create the table.</span></span>  
  
2.  <span data-ttu-id="0b0d4-132">Utilisez xcopy ou un outil similaire pour copier les fichiers .jpg, avec leur structure de répertoire, dans le répertoire racine du FileTable.</span><span class="sxs-lookup"><span data-stu-id="0b0d4-132">Use xcopy or a similar tool to copy the .jpg files, with their directory structure, into the root directory of the FileTable.</span></span>  
  
3.  <span data-ttu-id="0b0d4-133">Corrigez les métadonnées dans la table `PhotoMetadata`, en utilisant un code similaire à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="0b0d4-133">Fix the metadata in the `PhotoMetadata` table, by using code similar to the following:</span></span>  
  
```sql  
--  Add a path locator column to the PhotoMetadata table.  
ALTER TABLE PhotoMetadata ADD pathlocator hierarchyid;  
  
-- Get the root path of the Photo directory on the File Server.  
DECLARE @UNCPathRoot varchar(100) = '\\RemoteShare\Photographs';  
  
-- Get the root path of the FileTable.  
DECLARE @FileTableRoot varchar(1000);  
SELECT @FileTableRoot = FileTableRootPath('dbo.PhotoTable');  
  
-- Update the PhotoMetadata table.  
  
-- Replace the File Server UNC path with the FileTable path.  
UPDATE PhotoMetadata  
    SET UNCPath = REPLACE(UNCPath, @UNCPathRoot, @FileTableRoot);  
  
-- Update the pathlocator column to contain the pathlocator IDs from the FileTable.  
UPDATE PhotoMetadata  
    SET pathlocator = GetPathLocator(UNCPath);  
```  
  
##  <a name="bulk-loading-files-into-a-filetable"></a><a name="BasicsBulkLoad"></a> <span data-ttu-id="0b0d4-134">Chargement en masse de fichiers dans un FileTable</span><span class="sxs-lookup"><span data-stu-id="0b0d4-134">Bulk Loading Files into a FileTable</span></span>  
 <span data-ttu-id="0b0d4-135">Un FileTable se comporte comme une table normale pour les opérations en bloc, avec les caractéristiques suivantes.</span><span class="sxs-lookup"><span data-stu-id="0b0d4-135">A FileTable behaves like a normal table for bulk operations, with the following qualifications.</span></span>  
  
 <span data-ttu-id="0b0d4-136">Un FileTable a des contraintes définies par le système qui garantissent le maintien de l'intégrité de l'espace de noms de fichier/répertoire.</span><span class="sxs-lookup"><span data-stu-id="0b0d4-136">A FileTable has system-defined constraints which ensure that the integrity of the file and directory namespace is maintained.</span></span> <span data-ttu-id="0b0d4-137">Ces contraintes doivent être vérifiées sur le volume de données chargé dans le FileTable.</span><span class="sxs-lookup"><span data-stu-id="0b0d4-137">These constraints have to be verified on the data bulk loaded into the FileTable.</span></span> <span data-ttu-id="0b0d4-138">Puisque certaines opérations d'insertion en masse permettent d'ignorer les contraintes de table, les conditions requises suivantes sont appliquées.</span><span class="sxs-lookup"><span data-stu-id="0b0d4-138">Since some bulk insert operations allow table constraints to be ignored, the following requirements are enforced.</span></span>  
  
-   <span data-ttu-id="0b0d4-139">Les opérations de chargement en masse qui appliquent des contraintes peuvent être exécutées sur un FileTable comme sur toute autre table.</span><span class="sxs-lookup"><span data-stu-id="0b0d4-139">Bulk loading operations that enforce constraints can be run against a FileTable as against any other table.</span></span> <span data-ttu-id="0b0d4-140">Cette catégorie comprend les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="0b0d4-140">This category includes the following operations:</span></span>  
  
    -   <span data-ttu-id="0b0d4-141">bcp avec clause CHECK_CONSTRAINTS.</span><span class="sxs-lookup"><span data-stu-id="0b0d4-141">bcp with CHECK_CONSTRAINTS clause.</span></span>  
  
    -   <span data-ttu-id="0b0d4-142">BULK INSERT avec clause CHECK_CONSTRAINTS.</span><span class="sxs-lookup"><span data-stu-id="0b0d4-142">BULK INSERT with CHECK_CONSTRAINTS clause.</span></span>  
  
    -   <span data-ttu-id="0b0d4-143">INSERT INTO ... SELECT \* FROM OPENROWSET(BULK ...) sans clause IGNORE_CONSTRAINTS.</span><span class="sxs-lookup"><span data-stu-id="0b0d4-143">INSERT INTO ... SELECT \* FROM OPENROWSET(BULK ...) without IGNORE_CONSTRAINTS clause.</span></span>  
  
-   <span data-ttu-id="0b0d4-144">Les opérations de chargement en masse qui n'imposent pas de contraintes échouent à moins que les contraintes de FileTable définies par le système aient été désactivées.</span><span class="sxs-lookup"><span data-stu-id="0b0d4-144">Bulk loading operations that do not enforce constraints fail unless the FileTable system-defined constraints have been disabled.</span></span> <span data-ttu-id="0b0d4-145">Cette catégorie comprend les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="0b0d4-145">This category includes the following operations:</span></span>  
  
    -   <span data-ttu-id="0b0d4-146">bcp sans clause CHECK_CONSTRAINTS.</span><span class="sxs-lookup"><span data-stu-id="0b0d4-146">bcp without CHECK_CONSTRAINTS clause.</span></span>  
  
    -   <span data-ttu-id="0b0d4-147">BULK INSERT sans clause CHECK_CONSTRAINTS.</span><span class="sxs-lookup"><span data-stu-id="0b0d4-147">BULK INSERT without CHECK_CONSTRAINTS clause.</span></span>  
  
    -   <span data-ttu-id="0b0d4-148">INSERT INTO ... SELECT \* FROM OPENROWSET(BULK ...) avec clause IGNORE_CONSTRAINTS.</span><span class="sxs-lookup"><span data-stu-id="0b0d4-148">INSERT INTO ... SELECT \* FROM OPENROWSET(BULK ...) with IGNORE_CONSTRAINTS clause.</span></span>  
  
###  <a name="how-to-bulk-load-files-into-a-filetable"></a><a name="HowToBulkLoad"></a> <span data-ttu-id="0b0d4-149">Procédure : charger des fichiers en masse dans un FileTable</span><span class="sxs-lookup"><span data-stu-id="0b0d4-149">How To: Bulk Load Files into a FileTable</span></span>  
 <span data-ttu-id="0b0d4-150">Vous pouvez faire appel à différentes méthodes pour charger en masse des fichiers dans un FileTable :</span><span class="sxs-lookup"><span data-stu-id="0b0d4-150">You can use various methods to bulk load files into a FileTable:</span></span>  
  
-   <span data-ttu-id="0b0d4-151">**bcp**</span><span class="sxs-lookup"><span data-stu-id="0b0d4-151">**bcp**</span></span>  
  
    -   <span data-ttu-id="0b0d4-152">Effectuez un appel avec la clause **CHECK_CONSTRAINTS** .</span><span class="sxs-lookup"><span data-stu-id="0b0d4-152">Call with the **CHECK_CONSTRAINTS** clause.</span></span>  
  
    -   <span data-ttu-id="0b0d4-153">Désactivez l’espace de noms FileTable et effectuez un appel sans la clause **CHECK_CONSTRAINTS** .</span><span class="sxs-lookup"><span data-stu-id="0b0d4-153">Disable the FileTable namespace and call without the **CHECK_CONSTRAINTS** clause.</span></span> <span data-ttu-id="0b0d4-154">Ensuite, réactivez l'espace de noms FileTable.</span><span class="sxs-lookup"><span data-stu-id="0b0d4-154">Then re-enable the FileTable namespace.</span></span>  
  
-   <span data-ttu-id="0b0d4-155">**BULK INSERT**</span><span class="sxs-lookup"><span data-stu-id="0b0d4-155">**BULK INSERT**</span></span>  
  
    -   <span data-ttu-id="0b0d4-156">Effectuez un appel avec la clause **CHECK_CONSTRAINTS** .</span><span class="sxs-lookup"><span data-stu-id="0b0d4-156">Call with the **CHECK_CONSTRAINTS** clause.</span></span>  
  
    -   <span data-ttu-id="0b0d4-157">Désactivez l’espace de noms FileTable et effectuez un appel sans la clause **CHECK_CONSTRAINTS** .</span><span class="sxs-lookup"><span data-stu-id="0b0d4-157">Disable the FileTable namespace and call without the **CHECK_CONSTRAINTS** clause.</span></span> <span data-ttu-id="0b0d4-158">Ensuite, réactivez l'espace de noms FileTable.</span><span class="sxs-lookup"><span data-stu-id="0b0d4-158">Then re-enable the FileTable namespace.</span></span>  
  
-   <span data-ttu-id="0b0d4-159">**INSERT INTO ... SELECT \* FROM OPENROWSET(BULK ...)**</span><span class="sxs-lookup"><span data-stu-id="0b0d4-159">**INSERT INTO ... SELECT \* FROM OPENROWSET(BULK ...)**</span></span>  
  
    -   <span data-ttu-id="0b0d4-160">Effectuez un appel avec la clause **IGNORE_CONSTRAINTS** .</span><span class="sxs-lookup"><span data-stu-id="0b0d4-160">Call with the **IGNORE_CONSTRAINTS** clause.</span></span>  
  
    -   <span data-ttu-id="0b0d4-161">Désactivez l’espace de noms FileTable et effectuez un appel sans la clause **IGNORE_CONSTRAINTS** .</span><span class="sxs-lookup"><span data-stu-id="0b0d4-161">Disable the FileTable namespace and call without the **IGNORE_CONSTRAINTS** clause.</span></span> <span data-ttu-id="0b0d4-162">Ensuite, réactivez l'espace de noms FileTable.</span><span class="sxs-lookup"><span data-stu-id="0b0d4-162">Then re-enable the FileTable namespace.</span></span>  
  
 <span data-ttu-id="0b0d4-163">Pour plus d’informations sur la désactivation des contraintes FileTable, consultez [Gérer des FileTables](manage-filetables.md).</span><span class="sxs-lookup"><span data-stu-id="0b0d4-163">For information about disabling the FileTable constraints, see [Manage FileTables](manage-filetables.md).</span></span>  
  
###  <a name="how-to-disable-filetable-constraints-for-bulk-loading"></a><a name="disabling"></a> <span data-ttu-id="0b0d4-164">Procédure : désactiver les contraintes de FileTable pour le chargement en masse</span><span class="sxs-lookup"><span data-stu-id="0b0d4-164">How To: Disable FileTable Constraints for Bulk Loading</span></span>  
 <span data-ttu-id="0b0d4-165">Pour charger en masse des fichiers dans un FileTable sans la surcharge liée à l'application des contraintes définies par le système, vous pouvez désactiver temporairement les contraintes.</span><span class="sxs-lookup"><span data-stu-id="0b0d4-165">To bulk load files into a FileTable without the overhead of enforcing the system-defined constraints, you can temporarily disable the constraints.</span></span> <span data-ttu-id="0b0d4-166">Pour plus d’informations, consultez [Gérer des FileTables](manage-filetables.md).</span><span class="sxs-lookup"><span data-stu-id="0b0d4-166">For more information, see [Manage FileTables](manage-filetables.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b0d4-167">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0b0d4-167">See Also</span></span>  
 <span data-ttu-id="0b0d4-168">[Accéder aux FileTables avec Transact-SQL](access-filetables-with-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="0b0d4-168">[Access FileTables with Transact-SQL](access-filetables-with-transact-sql.md) </span></span>  
 [<span data-ttu-id="0b0d4-169">Accéder aux FileTables avec des API d’entrée-sortie de fichier</span><span class="sxs-lookup"><span data-stu-id="0b0d4-169">Access FileTables with File Input-Output APIs</span></span>](access-filetables-with-file-input-output-apis.md)  
  
  
