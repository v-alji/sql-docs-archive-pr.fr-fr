---
title: Configurer la destination du fichier plat (Assistant Importation et Exportation SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.configureflatfiledest.f1
ms.assetid: 318e8da0-37d3-46cd-943a-fc5d66aad93a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2af8a1653d9a1aef0828aa112a25825ed23b8bf6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611895"
---
# <a name="configure-flat-file-destination-sql-server-import-and-export-wizard"></a><span data-ttu-id="df061-102">Configurer la destination du fichier plat (Assistant Importation et Exportation SQL Server)</span><span class="sxs-lookup"><span data-stu-id="df061-102">Configure Flat File Destination (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="df061-103">Utilisez la page **configurer la destination de fichier plat** pour spécifier les options de mise en forme pour le fichier plat de destination et pour afficher un aperçu des résultats avant de continuer.</span><span class="sxs-lookup"><span data-stu-id="df061-103">Use the **Configure Flat File Destination** page to specify formatting options for the destination flat file, and to preview results before continuing.</span></span>  
  
 <span data-ttu-id="df061-104">Pour en savoir plus sur cet Assistant, consultez [Assistant Importation et Exportation SQL Server](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="df061-104">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="df061-105">Pour en savoir plus sur les options de démarrage de l’Assistant, ainsi que sur les autorisations requises pour exécuter correctement l’Assistant, consultez [exécuter l’Assistant importation et exportation SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="df061-105">To learn about the options for starting the wizard, as well as the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="df061-106">La fonction de l'Assistant Importation et Exportation SQL Server est de copier des données d'une source vers une destination.</span><span class="sxs-lookup"><span data-stu-id="df061-106">The purpose of the SQL Server Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="df061-107">L'Assistant peut également créer une base de données de destination et des tables de destination à votre intention.</span><span class="sxs-lookup"><span data-stu-id="df061-107">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="df061-108">Toutefois, si vous devez copier plusieurs tables ou bases de données, ou autres types d'objets de bases de données, vous devez plutôt utiliser l'Assistant Copie de base de données.</span><span class="sxs-lookup"><span data-stu-id="df061-108">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="df061-109">Pour plus d'informations, consultez [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="df061-109">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="df061-110">Options</span><span class="sxs-lookup"><span data-stu-id="df061-110">Options</span></span>  
 <span data-ttu-id="df061-111">**Fichier plat source**</span><span class="sxs-lookup"><span data-stu-id="df061-111">**Source flat file**</span></span>  
 <span data-ttu-id="df061-112">Nom du fichier de destination.</span><span class="sxs-lookup"><span data-stu-id="df061-112">The name of the destination file.</span></span>  
  
 <span data-ttu-id="df061-113">**Séparateur de lignes**</span><span class="sxs-lookup"><span data-stu-id="df061-113">**Row delimiter**</span></span>  
 <span data-ttu-id="df061-114">Effectuez une sélection dans la liste des délimiteurs de lignes.</span><span class="sxs-lookup"><span data-stu-id="df061-114">Select from the list of delimiters for rows.</span></span>  
  
|<span data-ttu-id="df061-115">Valeur</span><span class="sxs-lookup"><span data-stu-id="df061-115">Value</span></span>|<span data-ttu-id="df061-116">Description</span><span class="sxs-lookup"><span data-stu-id="df061-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="df061-117">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="df061-117">**{CR}{LF}**</span></span>|<span data-ttu-id="df061-118">La ligne est délimitée par une combinaison retour chariot/saut de ligne.</span><span class="sxs-lookup"><span data-stu-id="df061-118">The row is delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="df061-119">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="df061-119">**{CR}**</span></span>|<span data-ttu-id="df061-120">La ligne est délimitée par un retour chariot.</span><span class="sxs-lookup"><span data-stu-id="df061-120">The row is delimited by a carriage return.</span></span>|  
|<span data-ttu-id="df061-121">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="df061-121">**{LF}**</span></span>|<span data-ttu-id="df061-122">La ligne est délimitée par un saut de ligne.</span><span class="sxs-lookup"><span data-stu-id="df061-122">The row is delimited by a line feed.</span></span>|  
|<span data-ttu-id="df061-123">**Point-virgule {;}**</span><span class="sxs-lookup"><span data-stu-id="df061-123">**Semicolon {;}**</span></span>|<span data-ttu-id="df061-124">La ligne est délimitée par un point-virgule.</span><span class="sxs-lookup"><span data-stu-id="df061-124">The row is delimited by a semicolon.</span></span>|  
|<span data-ttu-id="df061-125">**Deux-points {:}**</span><span class="sxs-lookup"><span data-stu-id="df061-125">**Colon {:}**</span></span>|<span data-ttu-id="df061-126">La ligne est délimitée par un deux-points.</span><span class="sxs-lookup"><span data-stu-id="df061-126">The row is delimited by a colon.</span></span>|  
|<span data-ttu-id="df061-127">**Virgule {,}**</span><span class="sxs-lookup"><span data-stu-id="df061-127">**Comma {,}**</span></span>|<span data-ttu-id="df061-128">La ligne est délimitée par une virgule.</span><span class="sxs-lookup"><span data-stu-id="df061-128">The row is delimited by a comma.</span></span>|  
|<span data-ttu-id="df061-129">**Tabulation {t}**</span><span class="sxs-lookup"><span data-stu-id="df061-129">**Tab {t}**</span></span>|<span data-ttu-id="df061-130">La ligne est délimitée par une tabulation.</span><span class="sxs-lookup"><span data-stu-id="df061-130">The row is delimited by a tab.</span></span>|  
|<span data-ttu-id="df061-131">**Barre verticale {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="df061-131">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="df061-132">La ligne est délimitée par une barre verticale.</span><span class="sxs-lookup"><span data-stu-id="df061-132">The row is delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="df061-133">**Délimiteur de colonne**</span><span class="sxs-lookup"><span data-stu-id="df061-133">**Column delimiter**</span></span>  
 <span data-ttu-id="df061-134">Effectuez une sélection dans la liste des délimiteurs de colonnes.</span><span class="sxs-lookup"><span data-stu-id="df061-134">Select from the list of delimiters for columns.</span></span>  
  
|<span data-ttu-id="df061-135">Valeur</span><span class="sxs-lookup"><span data-stu-id="df061-135">Value</span></span>|<span data-ttu-id="df061-136">Description</span><span class="sxs-lookup"><span data-stu-id="df061-136">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="df061-137">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="df061-137">**{CR}{LF}**</span></span>|<span data-ttu-id="df061-138">Les colonnes sont délimitées par une combinaison retour chariot/saut de ligne.</span><span class="sxs-lookup"><span data-stu-id="df061-138">The columns are delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="df061-139">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="df061-139">**{CR}**</span></span>|<span data-ttu-id="df061-140">Les colonnes sont délimitées par un retour chariot.</span><span class="sxs-lookup"><span data-stu-id="df061-140">The columns are delimited by a carriage return.</span></span>|  
|<span data-ttu-id="df061-141">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="df061-141">**{LF}**</span></span>|<span data-ttu-id="df061-142">Les colonnes sont délimitées par un saut de ligne.</span><span class="sxs-lookup"><span data-stu-id="df061-142">The columns are delimited by a line feed.</span></span>|  
|<span data-ttu-id="df061-143">**Point-virgule {;}**</span><span class="sxs-lookup"><span data-stu-id="df061-143">**Semicolon {;}**</span></span>|<span data-ttu-id="df061-144">Les colonnes sont délimitées par un point-virgule.</span><span class="sxs-lookup"><span data-stu-id="df061-144">The columns are delimited by a semicolon.</span></span>|  
|<span data-ttu-id="df061-145">**Deux-points {:}**</span><span class="sxs-lookup"><span data-stu-id="df061-145">**Colon {:}**</span></span>|<span data-ttu-id="df061-146">Les colonnes sont délimitées par un deux-points.</span><span class="sxs-lookup"><span data-stu-id="df061-146">The columns are delimited by a colon.</span></span>|  
|<span data-ttu-id="df061-147">**Virgule {,}**</span><span class="sxs-lookup"><span data-stu-id="df061-147">**Comma {,}**</span></span>|<span data-ttu-id="df061-148">Les colonnes sont délimitées par une virgule.</span><span class="sxs-lookup"><span data-stu-id="df061-148">The columns are delimited by a comma.</span></span>|  
|<span data-ttu-id="df061-149">**Tabulation {t}**</span><span class="sxs-lookup"><span data-stu-id="df061-149">**Tab {t}**</span></span>|<span data-ttu-id="df061-150">Les colonnes sont délimitées par une tabulation.</span><span class="sxs-lookup"><span data-stu-id="df061-150">The columns are delimited by a tab.</span></span>|  
|<span data-ttu-id="df061-151">**Barre verticale {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="df061-151">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="df061-152">Les colonnes sont délimitées par une barre verticale.</span><span class="sxs-lookup"><span data-stu-id="df061-152">The columns are delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="df061-153">**Préversion**</span><span class="sxs-lookup"><span data-stu-id="df061-153">**Preview**</span></span>  
 <span data-ttu-id="df061-154">Affichez dans la boîte de dialogue **aperçu des données** les résultats des options de mise en forme sélectionnées pour le fichier plat de destination.</span><span class="sxs-lookup"><span data-stu-id="df061-154">View in the **Preview Data** dialog box the results of the selected formatting options for the destination flat file.</span></span>  
  
 <span data-ttu-id="df061-155">**Modifier la transformation**</span><span class="sxs-lookup"><span data-stu-id="df061-155">**Edit transform**</span></span>  
 <span data-ttu-id="df061-156">Supprimer des lignes, ajouter des lignes et configurer des colonnes dans le fichier de destination à l’aide de la boîte de dialogue **mappage de colonnes** .</span><span class="sxs-lookup"><span data-stu-id="df061-156">Delete rows, append rows, and configure columns in the destination file by using the **Column Mappings** dialog box.</span></span>  
  
  
