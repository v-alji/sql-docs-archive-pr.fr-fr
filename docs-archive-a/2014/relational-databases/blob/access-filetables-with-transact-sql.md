---
title: Accéder aux FileTables avec Transact-SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FileTables [SQL Server], accessing files with T-SQL
ms.assetid: 3c4a5ffb-c521-4696-99cb-2b03cffc9c02
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2c47751ef34747e1b3742accf5040846ecde074f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705180"
---
# <a name="access-filetables-with-transact-sql"></a><span data-ttu-id="d8d7b-102">Accéder aux FileTables avec Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d8d7b-102">Access FileTables with Transact-SQL</span></span>
  <span data-ttu-id="d8d7b-103">Décrit le fonctionnement des commandes de langage de manipulation de données (DML) [!INCLUDE[tsql](../../includes/tsql-md.md)] avec des FileTables.</span><span class="sxs-lookup"><span data-stu-id="d8d7b-103">Describes how [!INCLUDE[tsql](../../includes/tsql-md.md)] data manipulation language (DML) commands work with FileTables.</span></span>  
  
##  <a name="insert-operations-on-filetables"></a><a name="BasicsInsert"></a> <span data-ttu-id="d8d7b-104">Opérations INSERT sur les FileTables</span><span class="sxs-lookup"><span data-stu-id="d8d7b-104">INSERT Operations on FileTables</span></span>  
 <span data-ttu-id="d8d7b-105">Les points suivants s'appliquent aux opérations **INSERT** sur les FileTables :</span><span class="sxs-lookup"><span data-stu-id="d8d7b-105">The following considerations apply to **INSERT** Operations on FileTables:</span></span>  
  
-   <span data-ttu-id="d8d7b-106">Toutes les colonnes d'attribut de fichier ont des contraintes NOT NULL.</span><span class="sxs-lookup"><span data-stu-id="d8d7b-106">All the file attribute columns have NOT NULL constraints.</span></span> <span data-ttu-id="d8d7b-107">Si les valeurs ne sont pas définies explicitement, les valeurs par défaut appropriées sont fournies.</span><span class="sxs-lookup"><span data-stu-id="d8d7b-107">If values are not explicitly set, then appropriate default values are supplied.</span></span>  
  
-   <span data-ttu-id="d8d7b-108">Les contraintes définies par le système sont appliquées si l’instruction INSERT définit les valeurs **name**, **path_locator**, **parent_path_locator**, ou les attributs de fichier.</span><span class="sxs-lookup"><span data-stu-id="d8d7b-108">System-defined constraints are enforced if the INSERT statement sets the **name**, **path_locator**, **parent_path_locator**, or file attributes.</span></span>  
  
-   <span data-ttu-id="d8d7b-109">L’application peut obtenir la valeur **path_locator** pour un fichier ou un répertoire en fournissant le chemin d’accès au système de fichiers à la fonction [GetPathLocator &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/getpathlocator-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d8d7b-109">The application can obtain the **path_locator** for a file or directory by providing the file system path to the [GetPathLocator &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/getpathlocator-transact-sql) function.</span></span>  
  
##  <a name="update-operations-on-filetables"></a><a name="BasicsUpdate"></a> <span data-ttu-id="d8d7b-110">Opérations UPDATE sur les FileTables</span><span class="sxs-lookup"><span data-stu-id="d8d7b-110">UPDATE Operations on FileTables</span></span>  
 <span data-ttu-id="d8d7b-111">Les points suivants s'appliquent aux opérations **UPDATE** sur les FileTables :</span><span class="sxs-lookup"><span data-stu-id="d8d7b-111">The following considerations apply to **UPDATE** operations on FileTables:</span></span>  
  
-   <span data-ttu-id="d8d7b-112">Les mises à jour apportées aux données définies par l'utilisateur sont autorisées.</span><span class="sxs-lookup"><span data-stu-id="d8d7b-112">Updates to any user-defined data are allowed.</span></span>  
  
-   <span data-ttu-id="d8d7b-113">Les contraintes définies par le système sont appliquées si l’instruction INSERT définit les valeurs **name**, **path_locator**, **parent_path_locator**, ou les attributs de fichier.</span><span class="sxs-lookup"><span data-stu-id="d8d7b-113">System-defined constraints are enforced if the INSERT statement sets the **name**, **path_locator**, **parent_path_locator**, or file attributes.</span></span>  
  
-   <span data-ttu-id="d8d7b-114">Les mises à jour peuvent être apportées aux données FILESTREAM dans la colonne **file_stream** sans affecter aucune des autres colonnes, dont les horodateurs.</span><span class="sxs-lookup"><span data-stu-id="d8d7b-114">Updates can be made to the FILESTREAM data in the **file_stream** column without affecting any of the other columns, including the timestamps.</span></span>  
  
##  <a name="delete-operations-on-filetables"></a><a name="BasicsDelete"></a> <span data-ttu-id="d8d7b-115">Opérations DELETE sur les FileTables</span><span class="sxs-lookup"><span data-stu-id="d8d7b-115">DELETE Operations on FileTables</span></span>  
 <span data-ttu-id="d8d7b-116">Les points suivants s'appliquent aux opérations **DELETE** sur les FileTables :</span><span class="sxs-lookup"><span data-stu-id="d8d7b-116">The following considerations apply to **DELETE** operations on FileTables:</span></span>  
  
-   <span data-ttu-id="d8d7b-117">La suppression d'une ligne supprime également le fichier ou répertoire correspondant du système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="d8d7b-117">Deleting a row also removes the corresponding file or directory from the file system.</span></span>  
  
-   <span data-ttu-id="d8d7b-118">La suppression d'une ligne échoue si la ligne correspond à un répertoire qui contient d'autres fichiers ou répertoires.</span><span class="sxs-lookup"><span data-stu-id="d8d7b-118">Deleting a row fails if the row corresponds to a directory that contains other files or directories.</span></span>  
  
##  <a name="constraints-that-are-enforced-for-dml-operations-on-filetables"></a><a name="BasicsConstraints"></a> <span data-ttu-id="d8d7b-119">Contraintes appliquées pour les opérations DML sur les FileTables</span><span class="sxs-lookup"><span data-stu-id="d8d7b-119">Constraints That Are Enforced for DML Operations on FileTables</span></span>  
 <span data-ttu-id="d8d7b-120">Les contraintes définies par le système garantissent que les actions DML ne compromettent pas l'intégrité de la hiérarchie de l'espace de noms de fichier.</span><span class="sxs-lookup"><span data-stu-id="d8d7b-120">System-defined constraints ensure that DML actions do not compromise the integrity of the file namespace hierarchy.</span></span> <span data-ttu-id="d8d7b-121">Les contraintes appliquées sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="d8d7b-121">The constraints that are enforced include the following:</span></span>  
  
-   <span data-ttu-id="d8d7b-122">Lorsque vous définissez ou modifiez le **nom** du fichier ou du répertoire :</span><span class="sxs-lookup"><span data-stu-id="d8d7b-122">When you set or change the **name** of the file or directory:</span></span>  
  
    -   <span data-ttu-id="d8d7b-123">Les conventions d'affectation des noms de fichiers Windows et de répertoires sont appliquées.</span><span class="sxs-lookup"><span data-stu-id="d8d7b-123">Windows file and directory naming conventions are enforced.</span></span>  
  
    -   <span data-ttu-id="d8d7b-124">Le système impose l'unicité du nom dans le répertoire parent.</span><span class="sxs-lookup"><span data-stu-id="d8d7b-124">The uniqueness of the name in the parent directory is enforced.</span></span>  
  
-   <span data-ttu-id="d8d7b-125">Quand vous définissez ou modifiez l’emplacement d’un fichier ou d’un répertoire en définissant ou en modifiant la valeur **path_locator** ou **parent_path_locator**:</span><span class="sxs-lookup"><span data-stu-id="d8d7b-125">When you set or change the location of a file or directory by setting or changing the **path_locator** or **parent_path_locator**:</span></span>  
  
    -   <span data-ttu-id="d8d7b-126">L'unicité est appliquée.</span><span class="sxs-lookup"><span data-stu-id="d8d7b-126">Uniqueness is enforced.</span></span>  
  
    -   <span data-ttu-id="d8d7b-127">La cohérence de l’arborescence hiérarchique des répertoires et des fichiers est appliquée, notamment la cohérence des valeurs **path_locator** et **parent_path_locator** .</span><span class="sxs-lookup"><span data-stu-id="d8d7b-127">The consistency of the hierarchical tree of directories and files is enforced, including the consistency of **path_locator** and **parent_path_locator** values.</span></span>  
  
-   <span data-ttu-id="d8d7b-128">**is_directory** ne peut pas prendre la valeur True quand la colonne **file_stream** n’est pas Null.</span><span class="sxs-lookup"><span data-stu-id="d8d7b-128">The value of **is_directory** cannot be set to true when the **file_stream** column is not null.</span></span> <span data-ttu-id="d8d7b-129">Les données de la colonne **file_stream** indiquent que la ligne représente un fichier et pas un répertoire.</span><span class="sxs-lookup"><span data-stu-id="d8d7b-129">Data in the **file_stream** column indicates that the row represents a file and not a directory.</span></span>  
  
-   <span data-ttu-id="d8d7b-130">Les colonnes d'attributs de fichier ne peuvent pas être Null.</span><span class="sxs-lookup"><span data-stu-id="d8d7b-130">File attribute columns cannot be null.</span></span> <span data-ttu-id="d8d7b-131">Les contraintes NOT NULL sont appliquées avec des valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="d8d7b-131">NOT NULL constraints are enforced with default values.</span></span>  
  
-   <span data-ttu-id="d8d7b-132">La valeur de **last_access_time** ne peut pas être antérieure à **last_write_time** et **creation_time**.</span><span class="sxs-lookup"><span data-stu-id="d8d7b-132">The value of **last_access_time** cannot be earlier than **last_write_time** and **creation_time**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8d7b-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d8d7b-133">See Also</span></span>  
 <span data-ttu-id="d8d7b-134">[Charger des fichiers dans FileTables](load-files-into-filetables.md) </span><span class="sxs-lookup"><span data-stu-id="d8d7b-134">[Load Files into FileTables](load-files-into-filetables.md) </span></span>  
 <span data-ttu-id="d8d7b-135">[Work with Directories and Paths in FileTables](work-with-directories-and-paths-in-filetables.md) </span><span class="sxs-lookup"><span data-stu-id="d8d7b-135">[Work with Directories and Paths in FileTables](work-with-directories-and-paths-in-filetables.md) </span></span>  
 <span data-ttu-id="d8d7b-136">[Accéder aux FileTables avec des API d’entrée-sortie de fichier](access-filetables-with-file-input-output-apis.md) </span><span class="sxs-lookup"><span data-stu-id="d8d7b-136">[Access FileTables with File Input-Output APIs](access-filetables-with-file-input-output-apis.md) </span></span>  
 [<span data-ttu-id="d8d7b-137">DDL, fonctions, procédures stockées et vues FileTable</span><span class="sxs-lookup"><span data-stu-id="d8d7b-137">FileTable DDL, Functions, Stored Procedures, and Views</span></span>](../views/views.md)  
  
  
