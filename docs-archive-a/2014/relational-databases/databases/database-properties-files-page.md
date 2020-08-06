---
title: Propriétés de la base de données (page Fichiers) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.databaseproperties.files.f1
ms.assetid: 3c030e51-db82-4b43-b1e5-8547ddd3de87
author: stevestein
ms.author: sstein
ms.openlocfilehash: 955a17857ce0d847fb712473dddd581a072ab83d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695700"
---
# <a name="database-properties-files-page"></a><span data-ttu-id="47866-102">Propriétés de la base de données (page Fichiers)</span><span class="sxs-lookup"><span data-stu-id="47866-102">Database Properties (Files Page)</span></span>
  <span data-ttu-id="47866-103">Cette page vous permet de créer une nouvelle base de données, ainsi que d'afficher et de modifier les propriétés de la base de données sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="47866-103">Use this page to create a new database, or view or modify properties for the selected database.</span></span> <span data-ttu-id="47866-104">Cette rubrique s’applique aux **Propriétés de la base de données (page Fichiers)** pour les bases de données existantes et à la **Nouvelle base de données (page Général)** .</span><span class="sxs-lookup"><span data-stu-id="47866-104">This topic applies to the **Database Properties (Files Page)** for existing databases, and to the **New Database (General Page)**.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="47866-105">Liste d’éléments UI</span><span class="sxs-lookup"><span data-stu-id="47866-105">UI element list</span></span>  
 <span data-ttu-id="47866-106">**Nom de la base de données**</span><span class="sxs-lookup"><span data-stu-id="47866-106">**Database name**</span></span>  
 <span data-ttu-id="47866-107">Ajoutez ou affichez le nom de la base de données.</span><span class="sxs-lookup"><span data-stu-id="47866-107">Add or display the name of the database.</span></span>  
  
 <span data-ttu-id="47866-108">**Propriétaire**</span><span class="sxs-lookup"><span data-stu-id="47866-108">**Owner**</span></span>  
 <span data-ttu-id="47866-109">Spécifiez le propriétaire de la base de données en le sélectionnant dans la liste.</span><span class="sxs-lookup"><span data-stu-id="47866-109">Specify the owner of the database by selecting from the list.</span></span>  
  
 <span data-ttu-id="47866-110">**Utiliser l'indexation de texte intégral**</span><span class="sxs-lookup"><span data-stu-id="47866-110">**Use full-text indexing**</span></span>  
 <span data-ttu-id="47866-111">Cette case à cocher est activée et grisée, car l'indexation de texte intégral est toujours activée dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="47866-111">This check box is checked and disabled because full-text indexing is always enabled in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="47866-112">Pour plus d’informations, consultez [Recherche en texte intégral](../search/full-text-search.md).</span><span class="sxs-lookup"><span data-stu-id="47866-112">For more information, see [Full-Text Search](../search/full-text-search.md).</span></span>  
  
 <span data-ttu-id="47866-113">**Fichiers de base de données**</span><span class="sxs-lookup"><span data-stu-id="47866-113">**Database Files**</span></span>  
 <span data-ttu-id="47866-114">Ajoutez, affichez, modifiez ou supprimez les fichiers de base de données de la base de données associée.</span><span class="sxs-lookup"><span data-stu-id="47866-114">Add, view, modify, or remove database files for the associated database.</span></span> <span data-ttu-id="47866-115">Les fichiers de base de données ont les propriétés suivantes :</span><span class="sxs-lookup"><span data-stu-id="47866-115">Database files have the following properties:</span></span>  
  
 <span data-ttu-id="47866-116">**Nom logique**</span><span class="sxs-lookup"><span data-stu-id="47866-116">**Logical Name**</span></span>  
 <span data-ttu-id="47866-117">Entrez ou modifiez le nom du fichier.</span><span class="sxs-lookup"><span data-stu-id="47866-117">Enter or modify the name of the file.</span></span>  
  
 <span data-ttu-id="47866-118">**Type de fichier**</span><span class="sxs-lookup"><span data-stu-id="47866-118">**File Type**</span></span>  
 <span data-ttu-id="47866-119">Sélectionnez le type de fichier dans la liste.</span><span class="sxs-lookup"><span data-stu-id="47866-119">Select the file type from the list.</span></span> <span data-ttu-id="47866-120">Le type de fichier peut être **Données**, **Journal**ou **Données Filestream**.</span><span class="sxs-lookup"><span data-stu-id="47866-120">The file type can be **Data**, **Log**, or **Filestream Data**.</span></span> <span data-ttu-id="47866-121">Vous ne pouvez pas modifier le type de fichier d'un fichier existant.</span><span class="sxs-lookup"><span data-stu-id="47866-121">You cannot modify the file type of an existing file.</span></span>  
  
 <span data-ttu-id="47866-122">Sélectionnez **Données Filestream** si vous ajoutez des fichiers (conteneurs) à un groupe de fichiers optimisé en mémoire.</span><span class="sxs-lookup"><span data-stu-id="47866-122">Select **Filestream Data** if you are adding files (containers) to a memory-optimized filegroup.</span></span>  
  
 <span data-ttu-id="47866-123">Pour ajouter des fichiers (conteneurs) à un groupe de fichiers de données Filestream, FILESTREAM doit être activé.</span><span class="sxs-lookup"><span data-stu-id="47866-123">To add files (containers) to a Filestream data filegroup, FILESTREAM must be enabled.</span></span> <span data-ttu-id="47866-124">Vous pouvez activer FILESTREAM à l’aide de la boîte de dialogue [Propriétés du serveur (page Avancé)](../../database-engine/configure-windows/server-properties-advanced-page.md) .</span><span class="sxs-lookup"><span data-stu-id="47866-124">You can enable FILESTREAM by using the [Server Properties (Advanced Page)](../../database-engine/configure-windows/server-properties-advanced-page.md) dialog box.</span></span>  
  
 <span data-ttu-id="47866-125">**Groupe de fichiers**</span><span class="sxs-lookup"><span data-stu-id="47866-125">**Filegroup**</span></span>  
 <span data-ttu-id="47866-126">Sélectionnez le groupe de fichiers du fichier dans la liste.</span><span class="sxs-lookup"><span data-stu-id="47866-126">Select the filegroup for the file from the list.</span></span> <span data-ttu-id="47866-127">Par défaut, le groupe de fichiers est PRIMARY.</span><span class="sxs-lookup"><span data-stu-id="47866-127">By default, the filegroup is PRIMARY.</span></span> <span data-ttu-id="47866-128">Vous pouvez créer un nouveau groupe de fichiers en sélectionnant **\<new filegroup>** , puis en entrant les informations sur le groupe de fichiers dans la boîte de dialogue **Nouveau groupe de fichiers**.</span><span class="sxs-lookup"><span data-stu-id="47866-128">You can create a new filegroup by selecting **\<new filegroup>** and entering information about the filegroup in the **New Filegroup** dialog box.</span></span> <span data-ttu-id="47866-129">Il est également possible de créer un groupe de fichiers dans la page **Groupe de fichiers** .</span><span class="sxs-lookup"><span data-stu-id="47866-129">A new filegroup can also be created on the **Filegroup** page.</span></span> <span data-ttu-id="47866-130">Vous ne pouvez pas modifier le groupe de fichiers d'un fichier existant.</span><span class="sxs-lookup"><span data-stu-id="47866-130">You cannot modify the filegroup of an existing file.</span></span>  
  
 <span data-ttu-id="47866-131">Lors de l’ajout de fichiers (conteneurs) à un groupe de fichiers optimisé en mémoire, le champ **Groupe de fichiers** est rempli avec le nom du groupe de fichiers optimisé en mémoire de la base de données.</span><span class="sxs-lookup"><span data-stu-id="47866-131">When adding files (containers) to a memory-optimized filegroup, the **Filegroup** field will be populated with the name of the database's memory-optimized filegroup.</span></span>  
  
 <span data-ttu-id="47866-132">**Taille initiale**</span><span class="sxs-lookup"><span data-stu-id="47866-132">**Initial Size**</span></span>  
 <span data-ttu-id="47866-133">Entrez ou modifiez la taille initiale du fichier en mégaoctets.</span><span class="sxs-lookup"><span data-stu-id="47866-133">Enter or modify the initial size for the file in megabytes.</span></span> <span data-ttu-id="47866-134">Par défaut, il s’agit de la valeur de la base de données **model** .</span><span class="sxs-lookup"><span data-stu-id="47866-134">By default, this is the value of the **model** database.</span></span>  
  
 <span data-ttu-id="47866-135">Ce champ n'est pas valide pour les fichiers FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="47866-135">This field is not valid for FILESTREAM files.</span></span>  
  
 <span data-ttu-id="47866-136">Pour les fichiers des groupes de fichiers optimisés en mémoire, ce champ ne peut pas être modifié.</span><span class="sxs-lookup"><span data-stu-id="47866-136">For files in memory-optimized filegroups, this field cannot be modified.</span></span>  
  
 <span data-ttu-id="47866-137">**Croissance automatique**</span><span class="sxs-lookup"><span data-stu-id="47866-137">**Autogrowth**</span></span>  
 <span data-ttu-id="47866-138">Sélectionnez ou affichez les propriétés de croissance automatique du fichier.</span><span class="sxs-lookup"><span data-stu-id="47866-138">Select or display the autogrowth properties for the file.</span></span> <span data-ttu-id="47866-139">Ces propriétés contrôlent la manière dont le fichier croît une fois qu'il a atteint sa taille maximale.</span><span class="sxs-lookup"><span data-stu-id="47866-139">These properties control how the file expands when its maximum file size is reached.</span></span> <span data-ttu-id="47866-140">Pour modifier les valeurs de croissance automatique, cliquez sur le bouton Modifier en regard des propriétés de croissance automatique du fichier de votre choix, puis modifiez les valeurs dans la boîte de dialogue **Modifier la croissance automatique** .</span><span class="sxs-lookup"><span data-stu-id="47866-140">To edit autogrowth values, click the edit button next to the autogrowth properties for the file that you want, and change the values in the **Change Autogrowth** dialog box.</span></span> <span data-ttu-id="47866-141">Par défaut, il s’agit des valeurs de la base de données **model** .</span><span class="sxs-lookup"><span data-stu-id="47866-141">By default, these are the values of the **model** database.</span></span>  
  
 <span data-ttu-id="47866-142">Ce champ n'est pas valide pour les fichiers FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="47866-142">This field is not valid for FILESTREAM files.</span></span>  
  
 <span data-ttu-id="47866-143">Pour les fichiers des groupes de fichiers optimisés en mémoire, ce champ doit avoir la valeur **Illimité**.</span><span class="sxs-lookup"><span data-stu-id="47866-143">For files in memory-optimized filegroups, this field should be **Unlimited**.</span></span>  
  
 <span data-ttu-id="47866-144">**Chemin d’accès**</span><span class="sxs-lookup"><span data-stu-id="47866-144">**Path**</span></span>  
 <span data-ttu-id="47866-145">Affiche le chemin d'accès du fichier sélectionné.</span><span class="sxs-lookup"><span data-stu-id="47866-145">Displays the path of the selected file.</span></span> <span data-ttu-id="47866-146">Pour spécifier le chemin d'accès d'un nouveau fichier, cliquez sur le bouton Modifier en regard du chemin d'accès du fichier et parcourez l'arborescence jusqu'au dossier de destination.</span><span class="sxs-lookup"><span data-stu-id="47866-146">To specify a path for a new file, click the edit button next to the path for the file, and navigate to the destination folder.</span></span> <span data-ttu-id="47866-147">Vous ne pouvez pas modifier le chemin d'accès d'un fichier existant.</span><span class="sxs-lookup"><span data-stu-id="47866-147">You cannot modify the path of an existing file.</span></span>  
  
 <span data-ttu-id="47866-148">Pour les fichiers FILESTREAM, le chemin d'accès est un dossier.</span><span class="sxs-lookup"><span data-stu-id="47866-148">For FILESTREAM files, the path is a folder.</span></span> <span data-ttu-id="47866-149">Le [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] crée les fichiers sous-jacents dans ce dossier.</span><span class="sxs-lookup"><span data-stu-id="47866-149">The [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] will create the underlying files in this folder.</span></span>  
  
 <span data-ttu-id="47866-150">**Nom de fichier**</span><span class="sxs-lookup"><span data-stu-id="47866-150">**File Name**</span></span>  
 <span data-ttu-id="47866-151">Affiche le nom du fichier.</span><span class="sxs-lookup"><span data-stu-id="47866-151">Displays the name of the file.</span></span>  
  
 <span data-ttu-id="47866-152">Ce champ n'est pas valide pour les fichiers FILESTREAM, ce qui inclut les fichiers dans les groupes de fichiers optimisés en mémoire.</span><span class="sxs-lookup"><span data-stu-id="47866-152">This field is not valid for FILESTREAM files, including files in memory-optimized filegroups.</span></span>  
  
 <span data-ttu-id="47866-153">**Ajouter**</span><span class="sxs-lookup"><span data-stu-id="47866-153">**Add**</span></span>  
 <span data-ttu-id="47866-154">Ajoutez un nouveau fichier à la base de données.</span><span class="sxs-lookup"><span data-stu-id="47866-154">Add a new file to the database.</span></span>  
  
 <span data-ttu-id="47866-155">**Remove**</span><span class="sxs-lookup"><span data-stu-id="47866-155">**Remove**</span></span>  
 <span data-ttu-id="47866-156">Supprimez le fichier sélectionné de la base de données.</span><span class="sxs-lookup"><span data-stu-id="47866-156">Delete the selected file from the database.</span></span> <span data-ttu-id="47866-157">Un fichier ne peut pas être supprimé s'il n'est pas vide.</span><span class="sxs-lookup"><span data-stu-id="47866-157">A file cannot be removed unless it is empty.</span></span> <span data-ttu-id="47866-158">Le fichier de données primaire et le fichier journal ne peuvent pas être supprimés.</span><span class="sxs-lookup"><span data-stu-id="47866-158">The primary data file and log file cannot be removed.</span></span>  
  
 <span data-ttu-id="47866-159">Pour plus d’informations sur les fichiers, consultez [Groupes de fichiers et fichiers de base de données](database-files-and-filegroups.md).</span><span class="sxs-lookup"><span data-stu-id="47866-159">For information about files, see [Database Files and Filegroups](database-files-and-filegroups.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47866-160">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="47866-160">See Also</span></span>  
 <span data-ttu-id="47866-161">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="47866-161">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 [<span data-ttu-id="47866-162">sys.databases &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="47866-162">sys.databases &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql)  
  
  
