---
title: Spécifier des formats de données pour la compatibilité lors de l’utilisation de bcp (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- bulk exporting [SQL Server], compatibility
- bulk importing [SQL Server], compatibility
- compatibility [SQL Server], data formats
- data formats [SQL Server], compatibility
- bcp utility [SQL Server], compatibility
ms.assetid: cd5fc8c8-eab1-4165-9468-384f31e53f0a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5d12456760f32ddbd8cc434d474aebb0e0ecf141
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706524"
---
# <a name="specify-data-formats-for-compatibility-when-using-bcp-sql-server"></a><span data-ttu-id="14441-102">Spécifier des formats de données pour la compatibilité lors de l'utilisation de bcp (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="14441-102">Specify Data Formats for Compatibility when Using bcp (SQL Server)</span></span>
  <span data-ttu-id="14441-103">Cette rubrique décrit les attributs de format de données, les invites spécifiques aux champs et le stockage des données champ par champ dans un fichier de format non-XML de la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `bcp` commande.</span><span class="sxs-lookup"><span data-stu-id="14441-103">This topic describes the data-format attributes, field-specific prompts, and storing field-by-field data in a non-xml format file of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]`bcp` command.</span></span> <span data-ttu-id="14441-104">La compréhension de ces notions peut être utile lorsque vous exportez des données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en bloc à des fins d'importation en bloc dans un autre programme, tel qu'un autre programme de base de données.</span><span class="sxs-lookup"><span data-stu-id="14441-104">Understanding these can be helpful when you bulk export [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data for bulk import into another program, such as another database program.</span></span> <span data-ttu-id="14441-105">Les formats de données par défaut (natif, caractère ou Unicode) dans la table source peuvent être incompatibles avec la disposition des données attendue par l'autre programme. S'il existe une discordance lorsque vous exportez les données, vous devez décrire la disposition des données.</span><span class="sxs-lookup"><span data-stu-id="14441-105">The default data formats (native, character, or Unicode) in the source table might be incompatible with the data layout expected by the other program If an incompatibility exists, when you export the data, you must describe the data layout.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="14441-106">Si vous ne maîtrisez pas les formats de données pour l’importation ou l’exportation de données, consultez [Formats de données pour l’importation ou l’exportation en bloc &#40;SQL Server&#41;](data-formats-for-bulk-import-or-bulk-export-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="14441-106">If you are unfamiliar with data formats for importing or exporting data, see [Data Formats for Bulk Import or Bulk Export &#40;SQL Server&#41;](data-formats-for-bulk-import-or-bulk-export-sql-server.md).</span></span>  
  
 <span data-ttu-id="14441-107">**Dans cette rubrique :**</span><span class="sxs-lookup"><span data-stu-id="14441-107">**In This Topic:**</span></span>  
  
-   [<span data-ttu-id="14441-108">Attributs de format de données BCP</span><span class="sxs-lookup"><span data-stu-id="14441-108">bcp Data-Format Attributes</span></span>](#bcpDataFormatAttr)  
  
-   [<span data-ttu-id="14441-109">Vue d’ensemble des invites spécifiques aux champs</span><span class="sxs-lookup"><span data-stu-id="14441-109">Overview of the Field-Specific Prompts</span></span>](#FieldSpecificPrompts)  
  
-   [<span data-ttu-id="14441-110">Stockage des données champ par champ dans un fichier de format non XML</span><span class="sxs-lookup"><span data-stu-id="14441-110">Storing Field-by-Field Data in a Non-XML Format File</span></span>](#FieldByFieldNonXmlFF)  
  
-   [<span data-ttu-id="14441-111">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="14441-111">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="bcp-data-format-attributes"></a><a name="bcpDataFormatAttr"></a> <span data-ttu-id="14441-112">Attributs de format de données bcp</span><span class="sxs-lookup"><span data-stu-id="14441-112">bcp Data-Format Attributes</span></span>  
 <span data-ttu-id="14441-113">La commande `bcp` vous permet de spécifier la structure de chaque champ dans un fichier de données, selon les attributs de format de données suivants :</span><span class="sxs-lookup"><span data-stu-id="14441-113">The `bcp` command allows you to specify the structure of each field in a data file in terms of the following data-format attributes:</span></span>  
  
-   <span data-ttu-id="14441-114">type de stockage de fichier</span><span class="sxs-lookup"><span data-stu-id="14441-114">File storage type</span></span>  
  
     <span data-ttu-id="14441-115">Le *type de stockage de fichier* décrit la façon dont les données sont stockées dans le fichier de données.</span><span class="sxs-lookup"><span data-stu-id="14441-115">The *file storage type* describes how data is stored in the data file.</span></span> <span data-ttu-id="14441-116">Les données peuvent être exportées vers un fichier de données au type de table de base de données (format natif), dans sa représentation caractères (format caractères) ou tout type de données pour lesquelles la conversion implicite est prise en charge ; par exemple, en copiant un type de données `smallint` comme `int`.</span><span class="sxs-lookup"><span data-stu-id="14441-116">Data can be exported to a data file as its database table type (native format), in its character representation (character format), or as any data type where implicit conversion is supported; for example, copying a `smallint` as an `int`.</span></span> <span data-ttu-id="14441-117">Les types de données définis par l'utilisateur sont exportés en tant que leurs propres types de base.</span><span class="sxs-lookup"><span data-stu-id="14441-117">User-defined data types are exported as their base types.</span></span> <span data-ttu-id="14441-118">Pour plus d’informations, consultez [Spécifier le type de stockage de fichiers à l’aide de bcp &#40;SQL Server&#41;](specify-file-storage-type-by-using-bcp-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="14441-118">For more information, see [Specify File Storage Type by Using bcp &#40;SQL Server&#41;](specify-file-storage-type-by-using-bcp-sql-server.md).</span></span>  
  
-   <span data-ttu-id="14441-119">Longueur de préfixe</span><span class="sxs-lookup"><span data-stu-id="14441-119">Prefix length</span></span>  
  
     <span data-ttu-id="14441-120">Pour permettre le stockage de fichier le plus compact lors de l'exportation en bloc de données au format natif vers un fichier de données, la commande `bcp` ajoute devant chaque champ un ou plusieurs caractères indiquant la longueur du champ.</span><span class="sxs-lookup"><span data-stu-id="14441-120">To provide the most compact file storage for the bulk export of data in native format to a data file, the `bcp` command precedes each field with one or more characters that indicates the length of the field.</span></span> <span data-ttu-id="14441-121">Ces caractères portent le nom de *caractères de préfixe de longueur*.</span><span class="sxs-lookup"><span data-stu-id="14441-121">These characters are called *length prefix characters*.</span></span> <span data-ttu-id="14441-122">Pour plus d’informations, consultez [Spécifier une longueur de préfixe dans des fichiers de données à l’aide de bcp &#40;SQL Server&#41;](specify-prefix-length-in-data-files-by-using-bcp-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="14441-122">For more information, see [Specify Prefix Length in Data Files by Using bcp &#40;SQL Server&#41;](specify-prefix-length-in-data-files-by-using-bcp-sql-server.md).</span></span>  
  
-   <span data-ttu-id="14441-123">Longueur du champ</span><span class="sxs-lookup"><span data-stu-id="14441-123">Field length</span></span>  
  
     <span data-ttu-id="14441-124">La longueur de champ indique le nombre maximal de caractères nécessaires pour représenter les données au format caractères.</span><span class="sxs-lookup"><span data-stu-id="14441-124">The field length indicates the maximum number of characters that are required to represent data in character format.</span></span> <span data-ttu-id="14441-125">La longueur de champ est déjà connue si les données sont stockées au format natif.</span><span class="sxs-lookup"><span data-stu-id="14441-125">The field length is already known if the data is stored in the native format.</span></span> <span data-ttu-id="14441-126">Pour plus d’informations, consultez [Spécifier la longueur des champs au moyen de bcp &#40;SQL Server&#41;](specify-field-length-by-using-bcp-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="14441-126">For more information, see [Specify Field Length by Using bcp &#40;SQL Server&#41;](specify-field-length-by-using-bcp-sql-server.md).</span></span>  
  
-   <span data-ttu-id="14441-127">Marque de fin de champ</span><span class="sxs-lookup"><span data-stu-id="14441-127">Field terminator</span></span>  
  
     <span data-ttu-id="14441-128">Pour les champs de données caractères, des caractères de fin facultatifs vous permettent de marquer la fin de chaque champ dans un fichier de données (à l’aide d’une *marque de fin de champ*), ainsi que la fin de chaque ligne (avec une *marque de fin de ligne*).</span><span class="sxs-lookup"><span data-stu-id="14441-128">For character data fields, optional terminating characters allow you to mark the end of each field in a data file (using a *field terminator*) and the end of each row (using a *row terminator*).</span></span> <span data-ttu-id="14441-129">Les caractères de fin constituent un moyen d'indiquer aux programmes lisant le fichier de données la fin d'un champ ou d'une ligne et le début du suivant.</span><span class="sxs-lookup"><span data-stu-id="14441-129">Terminating characters are one way to indicate to programs reading the data file where one field or row ends and another begins.</span></span> <span data-ttu-id="14441-130">Pour plus d’informations, consultez [Spécifier des indicateurs de fin de champ et de fin de ligne &#40;SQL Server&#41;](specify-field-and-row-terminators-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="14441-130">For more information, see [Specify Field and Row Terminators &#40;SQL Server&#41;](specify-field-and-row-terminators-sql-server.md).</span></span>  
  
##  <a name="overview-of-the-field-specific-prompts"></a><a name="FieldSpecificPrompts"></a> <span data-ttu-id="14441-131">Vue d'ensemble des invites spécifiques aux champs</span><span class="sxs-lookup"><span data-stu-id="14441-131">Overview of the Field-Specific Prompts</span></span>  
 <span data-ttu-id="14441-132">Si une `bcp` commande interactive contient l’option in ou **out** , mais ne contient pas le commutateur de fichier **de** format **(-f**) ou un commutateur de format de données (**-n**, **-c**, **-w**ou **-n**), chaque colonne de la table source ou cible, la commande vous invite à fournir chacun des attributs précédents, à leur tour.</span><span class="sxs-lookup"><span data-stu-id="14441-132">If an interactive `bcp` command contains the **in** or **out** option but does not also contain either the format file switch (**-f**) or a data-format switch (**-n**, **-c**, **-w**, or **-N**),  each column in the source or target table, the command prompts for each of the preceding attributes, in turn.</span></span> <span data-ttu-id="14441-133">À chaque invite, la commande `bcp` fournit une valeur par défaut basée sur le type de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de la colonne de table.</span><span class="sxs-lookup"><span data-stu-id="14441-133">In each prompt, the `bcp` command provides a default value based on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type of the table column.</span></span> <span data-ttu-id="14441-134">L’acceptation de la valeur par défaut pour toutes les invites produit le même résultat que la spécification du format natif ( **-n**) sur la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="14441-134">Accepting the default value for all of the prompts produces the same result as specifying native format (**-n**) on the command line.</span></span> <span data-ttu-id="14441-135">Chaque invite affiche une valeur par défaut entre crochets : [*valeur par défaut*].</span><span class="sxs-lookup"><span data-stu-id="14441-135">Each prompt displays a default value in brackets: [*default*].</span></span> <span data-ttu-id="14441-136">En appuyant sur la touche Entrée, vous acceptez les valeurs par défaut affichées.</span><span class="sxs-lookup"><span data-stu-id="14441-136">Pressing ENTER accepts the displayed default.</span></span> <span data-ttu-id="14441-137">Pour spécifier une valeur différente de celle par défaut, entrez cette nouvelle valeur à l'invite.</span><span class="sxs-lookup"><span data-stu-id="14441-137">To specify a value other than the default, enter the new value at the prompt.</span></span>  
  
### <a name="example"></a><span data-ttu-id="14441-138">Exemple</span><span class="sxs-lookup"><span data-stu-id="14441-138">Example</span></span>  
 <span data-ttu-id="14441-139">L'exemple suivant utilise la commande `bcp` pour l'exportation en bloc interactive de données à partir de la table `HumanResources.myTeam` vers le fichier `myTeam.txt`.</span><span class="sxs-lookup"><span data-stu-id="14441-139">The following example uses the `bcp` command to bulk export data from the `HumanResources.myTeam` table interactively to the `myTeam.txt` file.</span></span> <span data-ttu-id="14441-140">Avant de pouvoir exécuter cet exemple, vous devez créer cette table.</span><span class="sxs-lookup"><span data-stu-id="14441-140">Before you can run the example, you must create this table.</span></span> <span data-ttu-id="14441-141">Pour plus d’informations sur la table et la manière de la créer, consultez [Exemple de table HumanResources.myTeam &#40;SQL Server&#41;](humanresources-myteam-sample-table-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="14441-141">For information about the table and how to create it, see [HumanResources.myTeam Sample Table &#40;SQL Server&#41;](humanresources-myteam-sample-table-sql-server.md).</span></span>  
  
 <span data-ttu-id="14441-142">La commande ne spécifie ni un fichier de format, ni un type de données ; l'utilitaire `bcp` vous invite donc à fournir des informations de format de données.</span><span class="sxs-lookup"><span data-stu-id="14441-142">The command specifies neither a format file nor a data type, causing `bcp` to prompt for data-format information.</span></span> <span data-ttu-id="14441-143">À l'invite de commandes [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, entrez :</span><span class="sxs-lookup"><span data-stu-id="14441-143">At the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks.HumanResources.myTeam out myTeam.txt -T  
```  
  
 <span data-ttu-id="14441-144">Pour chaque colonne, l'utilitaire bcp demande des valeurs spécifiques au champ.</span><span class="sxs-lookup"><span data-stu-id="14441-144">For each column, bcp prompts for field-specific values.</span></span> <span data-ttu-id="14441-145">L'exemple suivant illustre les messages spécifiques au champ pour les colonnes `EmployeeID` et `Name` de la table. En outre, il suggère le type de stockage de fichier par défaut (le format natif) pour chaque colonne.</span><span class="sxs-lookup"><span data-stu-id="14441-145">The following example shows the field-specific prompts for the `EmployeeID` and `Name` columns of the table, and suggests the default file storage type (the native format) for each column.</span></span> <span data-ttu-id="14441-146">Les longueurs de préfixe des colonnes `EmployeeID` et `Name` sont 0 et 2, respectivement.</span><span class="sxs-lookup"><span data-stu-id="14441-146">The prefix lengths of the `EmployeeID` and `Name` column are 0 and 2, respectively.</span></span> <span data-ttu-id="14441-147">L'utilisateur spécifie une virgule (`,`) en tant que marque de fin pour chaque champ.</span><span class="sxs-lookup"><span data-stu-id="14441-147">The user specifies a comma (`,`) as the terminator of each field.</span></span>  
  
 `Enter the file storage type of field EmployeeID [smallint]:`  
  
 `Enter prefix-length of field EmployeeID [0]:`  
  
 `Enter field terminator [none]:,`  
  
 `Enter the file storage type of field Name [nvarchar]:`  
  
 `Enter prefix length of field Name [2]:`  
  
 `Enter field terminator [none]:,`  
  
 `.`  
  
 `.`  
  
 `.`  
  
 <span data-ttu-id="14441-148">Des messages équivalents (si nécessaire) s'affichent pour chacune des colonnes de table dans l'ordre.</span><span class="sxs-lookup"><span data-stu-id="14441-148">Equivalent prompts (as needed) are displayed for each of the table columns in order.</span></span>  
  
##  <a name="storing-field-by-field-data-in-a-non-xml-format-file"></a><a name="FieldByFieldNonXmlFF"></a> <span data-ttu-id="14441-149">Stockage de données champ par champ dans un fichier de format non-XML</span><span class="sxs-lookup"><span data-stu-id="14441-149">Storing Field-by-Field Data in a Non-XML Format File</span></span>  
 <span data-ttu-id="14441-150">Une fois toutes les colonnes de table spécifiées, la commande `bcp` vous invite à générer facultativement un fichier de format non-XML qui stocke les informations champ par champ venant d'être fournies (voir l'exemple précédent).</span><span class="sxs-lookup"><span data-stu-id="14441-150">After all of the table columns are specified, the `bcp` command prompts you to optionally generate a non-XML format file that stores the field-by-field information just supplied (see the preceding example).</span></span> <span data-ttu-id="14441-151">Si vous choisissez de générer un fichier de format, vous pouvez effectuer cette opération dès que vous exportez des données vers cette table ou que vous importez des données structurées de la sorte dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="14441-151">If you choose to generate a format file, you can whenever you export data out of that table or import like-structured data into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="14441-152">Vous pouvez utiliser le fichier de format pour importer en bloc des données à partir du fichier de données vers une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou exporter en bloc des données depuis la table, sans devoir spécifier à nouveau le format.</span><span class="sxs-lookup"><span data-stu-id="14441-152">You can use the format file to bulk import data from the data file into an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or to bulk export data from the table, without needing to respecify the format.</span></span> <span data-ttu-id="14441-153">Pour plus d’informations, consultez [Fichiers de format pour l’importation ou l’exportation de données &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="14441-153">For more information, see [Format Files for Importing or Exporting Data &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span></span>  
  
 <span data-ttu-id="14441-154">L'exemple suivant crée un fichier de format non XML nommé `myFormatFile.fmt`.</span><span class="sxs-lookup"><span data-stu-id="14441-154">The following example creates a non-XML format file named `myFormatFile.fmt`:</span></span>  
  
 `Do you want to save this format information in a file? [Y/n] y`  
  
 `Host filename: [bcp.fmt]myFormatFile.fmt`  
  
 <span data-ttu-id="14441-155">Le nom par défaut du fichier de format est bcp.fmt, mais vous pouvez spécifier un nom différent si vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="14441-155">The default name for the format file is bcp.fmt, but you can specify a different file name if you choose.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="14441-156">Pour un fichier de données qui utilise un seul format de données pour son type de stockage de fichiers, tel qu’un format caractère ou natif, vous pouvez créer rapidement un fichier de format sans exportation ni importation de données, à l’aide de l’option **format** .</span><span class="sxs-lookup"><span data-stu-id="14441-156">For a data file that uses a single data format for its file-storage type, such as character or native format, you can quickly create a format file without exporting or importing data by using the **format** option.</span></span> <span data-ttu-id="14441-157">Cette approche présente les avantages d'être aisée et de vous permettre de créer un fichier de format XML ou non-XML.</span><span class="sxs-lookup"><span data-stu-id="14441-157">This approach has the advantages of being easy and of allowing you to create either an XML format file or a non-XML format file.</span></span> <span data-ttu-id="14441-158">Pour plus d’informations, consultez [Créer un fichier de format &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="14441-158">For more information, see [Create a Format File &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="14441-159">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="14441-159">Related Tasks</span></span>  
  
-   [<span data-ttu-id="14441-160">Spécifier le type de stockage de fichiers à l’aide de bcp &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="14441-160">Specify File Storage Type by Using bcp &#40;SQL Server&#41;</span></span>](specify-file-storage-type-by-using-bcp-sql-server.md)  
  
-   [<span data-ttu-id="14441-161">Spécifier une longueur de préfixe dans des fichiers de données à l’aide de bcp &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="14441-161">Specify Prefix Length in Data Files by Using bcp &#40;SQL Server&#41;</span></span>](specify-prefix-length-in-data-files-by-using-bcp-sql-server.md)  
  
-   [<span data-ttu-id="14441-162">Spécifier la longueur des champs au moyen de bcp &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="14441-162">Specify Field Length by Using bcp &#40;SQL Server&#41;</span></span>](specify-field-length-by-using-bcp-sql-server.md)  
  
-   [<span data-ttu-id="14441-163">Spécifier des indicateurs de fin de champ et de fin de ligne &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="14441-163">Specify Field and Row Terminators &#40;SQL Server&#41;</span></span>](specify-field-and-row-terminators-sql-server.md)  
  
## <a name="related-content"></a><span data-ttu-id="14441-164">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="14441-164">Related Content</span></span>  
 <span data-ttu-id="14441-165">Aucun.</span><span class="sxs-lookup"><span data-stu-id="14441-165">None.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14441-166">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="14441-166">See Also</span></span>  
 <span data-ttu-id="14441-167">[Importation et exportation en bloc de données &#40;SQL Server&#41;](bulk-import-and-export-of-data-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="14441-167">[Bulk Import and Export of Data &#40;SQL Server&#41;](bulk-import-and-export-of-data-sql-server.md) </span></span>  
 <span data-ttu-id="14441-168">[Formats de données pour l’importation ou l’exportation en bloc &#40;SQL Server&#41;](data-formats-for-bulk-import-or-bulk-export-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="14441-168">[Data Formats for Bulk Import or Bulk Export &#40;SQL Server&#41;](data-formats-for-bulk-import-or-bulk-export-sql-server.md) </span></span>  
 <span data-ttu-id="14441-169">[Utilitaire bcp](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="14441-169">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 [<span data-ttu-id="14441-170">Types de données &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="14441-170">Data Types &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/data-types-transact-sql)  
  
  
