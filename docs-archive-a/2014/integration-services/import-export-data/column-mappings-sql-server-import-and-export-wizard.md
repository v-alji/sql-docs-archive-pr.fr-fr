---
title: Mappage de colonnes (Assistant Importation et Exportation SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.columnmapandtransform.f1
ms.assetid: eadc54a6-f936-4ffc-91d7-fbfd2bdcab93
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7994de1292677421447d441c1ac5aeb2b6fbc618
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611894"
---
# <a name="column-mappings-sql-server-import-and-export-wizard"></a><span data-ttu-id="17c1c-102">Mappage de colonnes (Assistant Importation et exportation SQL Server)</span><span class="sxs-lookup"><span data-stu-id="17c1c-102">Column Mappings (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="17c1c-103">Utilisez la boîte de dialogue **mappage de colonnes** pour modifier les paramètres de transformation.</span><span class="sxs-lookup"><span data-stu-id="17c1c-103">Use the **Column Mappings** dialog box to edit transformation parameters.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="17c1c-104">Vous n'êtes pas obligé de copier toutes les colonnes d'une table lorsque vous sélectionnez l'option de copie de table.</span><span class="sxs-lookup"><span data-stu-id="17c1c-104">You do not have to copy all the columns in a table when you select the Table Copy option.</span></span> <span data-ttu-id="17c1c-105">Sélectionnez **\<ignore>** dans la colonne **destination** de cette boîte de dialogue les colonnes que vous souhaitez ignorer.</span><span class="sxs-lookup"><span data-stu-id="17c1c-105">Select **\<ignore>** in the **Destination** column of this dialog box for columns that you want to skip.</span></span>  
  
 <span data-ttu-id="17c1c-106">Pour en savoir plus sur cet Assistant, consultez [Assistant Importation et Exportation SQL Server](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="17c1c-106">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="17c1c-107">Pour en savoir plus sur les options de démarrage de l’Assistant, ainsi que sur les autorisations requises pour exécuter correctement l’Assistant, consultez [exécuter l’Assistant importation et exportation SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="17c1c-107">To learn about the options for starting the wizard, as well as the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="17c1c-108">La fonction de l'Assistant Importation et Exportation SQL Server est de copier des données d'une source vers une destination.</span><span class="sxs-lookup"><span data-stu-id="17c1c-108">The purpose of the SQL Server Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="17c1c-109">L'Assistant peut également créer une base de données de destination et des tables de destination à votre intention.</span><span class="sxs-lookup"><span data-stu-id="17c1c-109">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="17c1c-110">Toutefois, si vous devez copier plusieurs tables ou bases de données, ou autres types d'objets de bases de données, vous devez plutôt utiliser l'Assistant Copie de base de données.</span><span class="sxs-lookup"><span data-stu-id="17c1c-110">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="17c1c-111">Pour plus d'informations, consultez [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="17c1c-111">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="17c1c-112">Options</span><span class="sxs-lookup"><span data-stu-id="17c1c-112">Options</span></span>  
 <span data-ttu-id="17c1c-113">**Source**</span><span class="sxs-lookup"><span data-stu-id="17c1c-113">**Source**</span></span>  
 <span data-ttu-id="17c1c-114">Identifie la table, la vue ou la requête source sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="17c1c-114">Identifies the selected source table, view, or query.</span></span>  
  
 <span data-ttu-id="17c1c-115">**Destination**</span><span class="sxs-lookup"><span data-stu-id="17c1c-115">**Destination**</span></span>  
 <span data-ttu-id="17c1c-116">Identifie la table, la vue ou la requête de destination sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="17c1c-116">Identifies the selected destination table, view, or query.</span></span>  
  
 <span data-ttu-id="17c1c-117">**Créer la table/le fichier de destination**</span><span class="sxs-lookup"><span data-stu-id="17c1c-117">**Create destination table/file**</span></span>  
 <span data-ttu-id="17c1c-118">Indiquez si la table de destination doit être créée si elle n'existe pas.</span><span class="sxs-lookup"><span data-stu-id="17c1c-118">Specify whether to create the destination table if it does not already exist.</span></span>  
  
 <span data-ttu-id="17c1c-119">**Supprimer des lignes dans la table/le fichier de destination**</span><span class="sxs-lookup"><span data-stu-id="17c1c-119">**Delete rows in destination table/file**</span></span>  
 <span data-ttu-id="17c1c-120">Indiquez si les données d'une table existante doivent être effacées avant d'en charger de nouvelles.</span><span class="sxs-lookup"><span data-stu-id="17c1c-120">Specify whether to clear the data from an existing table before loading new data.</span></span>  
  
 <span data-ttu-id="17c1c-121">**Ajouter des lignes à la table/au fichier de destination**</span><span class="sxs-lookup"><span data-stu-id="17c1c-121">**Append rows to destination table/file**</span></span>  
 <span data-ttu-id="17c1c-122">Indiquez si les nouvelles données doivent être ajoutées à la suite des données déjà présentes dans une table existante.</span><span class="sxs-lookup"><span data-stu-id="17c1c-122">Specify whether to append the new data to the data already present in an existing table.</span></span>  
  
 <span data-ttu-id="17c1c-123">**Modifier SQL**</span><span class="sxs-lookup"><span data-stu-id="17c1c-123">**Edit SQL**</span></span>  
 <span data-ttu-id="17c1c-124">Utilisez l’instruction default dans la boîte de dialogue **instruction SQL de création de table** ou modifiez-la selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="17c1c-124">Use the default statement in the **Create Table SQL Statement** dialog box, or modify it for your purposes.</span></span> <span data-ttu-id="17c1c-125">Si vous la modifiez, vous devez également effectuer les modifications associées au mappage de table.</span><span class="sxs-lookup"><span data-stu-id="17c1c-125">If you modify this statement, you must also make associated changes to table mapping.</span></span>  
  
 <span data-ttu-id="17c1c-126">**Supprimer et recréer la table de destination**</span><span class="sxs-lookup"><span data-stu-id="17c1c-126">**Drop and re-create destination table**</span></span>  
 <span data-ttu-id="17c1c-127">Choisissez cette option pour remplacer la table de destination.</span><span class="sxs-lookup"><span data-stu-id="17c1c-127">Choose this option to overwrite the destination table.</span></span> <span data-ttu-id="17c1c-128">Cette option est disponible uniquement lorsque vous faites appel à l'Assistant pour créer la table de destination.</span><span class="sxs-lookup"><span data-stu-id="17c1c-128">This option is only available when you use the wizard to create the destination table.</span></span> <span data-ttu-id="17c1c-129">La table de destination est uniquement supprimée et recréée si vous enregistrez le package créé par l'Assistant, puis exécutez de nouveau le package.</span><span class="sxs-lookup"><span data-stu-id="17c1c-129">The destination table is only dropped and re-created if you save the package that the wizard creates, and then run the package again.</span></span>  
  
 <span data-ttu-id="17c1c-130">**Activer l’insertion d’identité**</span><span class="sxs-lookup"><span data-stu-id="17c1c-130">**Enable identity insert**</span></span>  
 <span data-ttu-id="17c1c-131">Permet d'insérer des valeurs d'identité des données source dans une colonne d'identité de la table de destination.</span><span class="sxs-lookup"><span data-stu-id="17c1c-131">Choose this option to allow existing identity values in the source data to be inserted into an identity column in the destination table.</span></span> <span data-ttu-id="17c1c-132">Par défaut, la colonne d'identité de destination ne permet pas cela.</span><span class="sxs-lookup"><span data-stu-id="17c1c-132">By default, the destination identity column does not allow this.</span></span>  
  
 <span data-ttu-id="17c1c-133">**Mappages**</span><span class="sxs-lookup"><span data-stu-id="17c1c-133">**Mappings**</span></span>  
 <span data-ttu-id="17c1c-134">Affiche la manière dont chaque colonne dans la source de données est mappée à une colonne dans la destination.</span><span class="sxs-lookup"><span data-stu-id="17c1c-134">Displays how each column in the data source maps to a column in the destination.</span></span>  
  
 <span data-ttu-id="17c1c-135">Cette liste présente les colonnes suivantes :</span><span class="sxs-lookup"><span data-stu-id="17c1c-135">This list has the following columns:</span></span>  
  
 <span data-ttu-id="17c1c-136">**Source**</span><span class="sxs-lookup"><span data-stu-id="17c1c-136">**Source**</span></span>  
 <span data-ttu-id="17c1c-137">Affiche chaque colonne source pour laquelle vous voulez définir des paramètres de transformation.</span><span class="sxs-lookup"><span data-stu-id="17c1c-137">View each source column for which you can set transformation parameters.</span></span>  
  
 <span data-ttu-id="17c1c-138">**Destination**</span><span class="sxs-lookup"><span data-stu-id="17c1c-138">**Destination**</span></span>  
 <span data-ttu-id="17c1c-139">Spécifiez si vous voulez ignorer une colonne pendant la copie.</span><span class="sxs-lookup"><span data-stu-id="17c1c-139">Specify whether you want to ignore a column during the copy operation.</span></span> <span data-ttu-id="17c1c-140">Vous ne pouvez copier qu’un sous-ensemble de colonnes en sélectionnant **\<ignore>** dans cette colonne les colonnes que vous souhaitez ignorer.</span><span class="sxs-lookup"><span data-stu-id="17c1c-140">You can copy only a subset of columns by selecting **\<ignore>** in this column for columns that you want to skip.</span></span> <span data-ttu-id="17c1c-141">Avant de mapper les colonnes, vous devez ignorer toutes les colonnes qui ne seront pas mappées.</span><span class="sxs-lookup"><span data-stu-id="17c1c-141">Before you map columns, you must ignore all columns that will not be mapped.</span></span>  
  
 <span data-ttu-id="17c1c-142">**Type**</span><span class="sxs-lookup"><span data-stu-id="17c1c-142">**Type**</span></span>  
 <span data-ttu-id="17c1c-143">Sélectionnez un type de données pour la colonne.</span><span class="sxs-lookup"><span data-stu-id="17c1c-143">Select a data type for the column.</span></span>  
  
 <span data-ttu-id="17c1c-144">**Nullable**</span><span class="sxs-lookup"><span data-stu-id="17c1c-144">**Nullable**</span></span>  
 <span data-ttu-id="17c1c-145">Spécifiez si une colonne peut contenir une valeur NULL.</span><span class="sxs-lookup"><span data-stu-id="17c1c-145">Specify whether a column will allow a null value.</span></span>  
  
 <span data-ttu-id="17c1c-146">**Taille**</span><span class="sxs-lookup"><span data-stu-id="17c1c-146">**Size**</span></span>  
 <span data-ttu-id="17c1c-147">Spécifiez le nombre de caractères dans la colonne.</span><span class="sxs-lookup"><span data-stu-id="17c1c-147">Specify the number of characters in the column.</span></span>  
  
 <span data-ttu-id="17c1c-148">**Précision**</span><span class="sxs-lookup"><span data-stu-id="17c1c-148">**Precision**</span></span>  
 <span data-ttu-id="17c1c-149">Spécifiez la précision des données affichées en indiquant le nombre de chiffres.</span><span class="sxs-lookup"><span data-stu-id="17c1c-149">Specify the precision of displayed data, referring to the number of digits.</span></span>  
  
 <span data-ttu-id="17c1c-150">**Mise à l’échelle**</span><span class="sxs-lookup"><span data-stu-id="17c1c-150">**Scale**</span></span>  
 <span data-ttu-id="17c1c-151">Spécifiez l'échelle des données affichées en indiquant le nombre de décimales.</span><span class="sxs-lookup"><span data-stu-id="17c1c-151">Specify the scale of displayed data, referring to the number of decimal places.</span></span>  
  
  
