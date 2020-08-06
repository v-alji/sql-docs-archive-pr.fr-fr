---
title: Fichiers de format pour l’importation ou l’exportation de données (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- bulk exporting [SQL Server], format files
- bulk importing [SQL Server], format files
- format files [SQL Server]
ms.assetid: b7b97d68-4336-4091-aee4-1941fab568e3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1143690f0322fef2612fde51eebcb7427ee237ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612339"
---
# <a name="format-files-for-importing-or-exporting-data-sql-server"></a><span data-ttu-id="cc5eb-102">Fichiers de format pour l'importation ou l'exportation de données (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="cc5eb-102">Format Files for Importing or Exporting Data (SQL Server)</span></span>
  <span data-ttu-id="cc5eb-103">Lorsque vous importez en bloc des données dans une table [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou exportez en bloc des données depuis une table, utilisez un *fichier de format* pour stocker toutes les informations de format nécessaires à l'exportation ou l'importation en bloc des données.</span><span class="sxs-lookup"><span data-stu-id="cc5eb-103">When you bulk import data into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table or bulk export data from a table, you can use a *format file* to store all the format information that is required to bulk export or bulk import data.</span></span> <span data-ttu-id="cc5eb-104">Cela inclut les informations de format pour chaque champ dans un fichier de données relatif à cette table.</span><span class="sxs-lookup"><span data-stu-id="cc5eb-104">This includes format information for each field in a data file relative to that table.</span></span>  
  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="cc5eb-105">prend en charge deux types de fichiers de format : les fichiers de formats XML et de format non-XML.</span><span class="sxs-lookup"><span data-stu-id="cc5eb-105">supports two types of format files: XML formats and non-XML format files.</span></span> <span data-ttu-id="cc5eb-106">Les fichiers de format XML et non-XML contiennent la description de chacun des champs d'un fichier de données, et les fichiers de format XML contiennent également des descriptions des colonnes de table correspondantes.</span><span class="sxs-lookup"><span data-stu-id="cc5eb-106">Both non-XML format files and XML format files contain descriptions of every field in a data file, and XML format files also contain descriptions of the corresponding table columns.</span></span> <span data-ttu-id="cc5eb-107">En règle générale, les fichiers de format XML et non-XML sont interchangeables.</span><span class="sxs-lookup"><span data-stu-id="cc5eb-107">Generally, XML and non-XML format files are interchangeable.</span></span> <span data-ttu-id="cc5eb-108">Toutefois, nous recommandons d'utiliser la syntaxe XML pour les nouveaux fichiers de format, car elle offre plusieurs avantages par rapport aux fichiers de format non-XML.</span><span class="sxs-lookup"><span data-stu-id="cc5eb-108">However, we recommend that you use the XML syntax for new format files because they provide several advantages over non-XML format files.</span></span> <span data-ttu-id="cc5eb-109">Pour plus d’informations, consultez [Fichiers de format XML &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="cc5eb-109">For more information, see [XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  
 
  
##  <a name="benefits-of-format-files"></a><a name="Benefits"></a> <span data-ttu-id="cc5eb-110">Avantages des fichiers de format</span><span class="sxs-lookup"><span data-stu-id="cc5eb-110">Benefits of Format Files</span></span>  
  
-   <span data-ttu-id="cc5eb-111">Fournit un système souple d'écriture de fichiers de données, nécessitant peu ou aucune édition pour se conformer aux autres formats de données, ou de lecture de fichiers de données provenant d'autres logiciels.</span><span class="sxs-lookup"><span data-stu-id="cc5eb-111">Provides a flexible system for writing data files that requires little or no editing to comply with other data formats or to read data files from other software.</span></span>  
  
-   <span data-ttu-id="cc5eb-112">Vous permet d'importer les données en bloc sans avoir à ajouter ou supprimer des données inutiles ou à réorganiser les données du fichier de données.</span><span class="sxs-lookup"><span data-stu-id="cc5eb-112">Enables you to bulk import data without having to add or delete unnecessary data or to reorder existing data in the data file.</span></span> <span data-ttu-id="cc5eb-113">Les fichiers de format sont particulièrement utiles lorsqu'il existe des différences entre les champs du fichier de données et les colonnes dans la table.</span><span class="sxs-lookup"><span data-stu-id="cc5eb-113">Format files are particularly useful when a mismatch exists between fields in the data file and columns in the table.</span></span>  
  
##  <a name="examples-of-format-files"></a><a name="ExamplesOfFFs"></a> <span data-ttu-id="cc5eb-114">Exemples de fichiers de format</span><span class="sxs-lookup"><span data-stu-id="cc5eb-114">Examples of Format Files</span></span>  
 <span data-ttu-id="cc5eb-115">Les exemples suivants illustrent la structure d'un fichier de format XML et non XML.</span><span class="sxs-lookup"><span data-stu-id="cc5eb-115">The following examples show the layout of a non-XML format file and of an XML format file.</span></span> <span data-ttu-id="cc5eb-116">Ces fichiers de format correspondent à la table `HumanResources.myTeam` dans l'exemple de base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cc5eb-116">These format files correspond to the `HumanResources.myTeam` table in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span> <span data-ttu-id="cc5eb-117">Cette table contient quatre colonnes : `EmployeeID`, `Name`, `Title`et `ModifiedDate`.</span><span class="sxs-lookup"><span data-stu-id="cc5eb-117">This table contains four columns: `EmployeeID`, `Name`, `Title`, and `ModifiedDate`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cc5eb-118">Pour plus d’informations sur cette table et la manière de la créer, consultez [Exemple de table HumanResources.myTeam &#40;SQL Server&#41;](humanresources-myteam-sample-table-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="cc5eb-118">For information about this table and how to create it, see [HumanResources.myTeam Sample Table &#40;SQL Server&#41;](humanresources-myteam-sample-table-sql-server.md).</span></span>  
  
### <a name="a-using-a-non-xml-format-file"></a><span data-ttu-id="cc5eb-119">R.</span><span class="sxs-lookup"><span data-stu-id="cc5eb-119">A.</span></span> <span data-ttu-id="cc5eb-120">Utilisation d'un fichier de format non-XML</span><span class="sxs-lookup"><span data-stu-id="cc5eb-120">Using a non-XML format file</span></span>  
 <span data-ttu-id="cc5eb-121">Le fichier de format non XML suivant utilise le format de données natif [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de la table `HumanResources.myTeam` .</span><span class="sxs-lookup"><span data-stu-id="cc5eb-121">The following non-XML format file uses the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native data format for the `HumanResources.myTeam` table.</span></span> <span data-ttu-id="cc5eb-122">Ce fichier de format a été créé à l'aide de la commande `bcp` suivante.</span><span class="sxs-lookup"><span data-stu-id="cc5eb-122">This format file was created by using the following `bcp` command.</span></span>  
  
```  
bcp AdventureWorks.HumanResources.myTeam format nul -f myTeam.Fmt -n -T   
The contents of this format file are as follows: 9.0  
4  
1       SQLSMALLINT   0       2       ""   1     EmployeeID               ""  
2       SQLNCHAR      2       100     ""   2     Name                     SQL_Latin1_General_CP1_CI_AS  
3       SQLNCHAR      2       100     ""   3     Title                    SQL_Latin1_General_CP1_CI_AS  
4       SQLNCHAR      2       100     ""   4     Background               SQL_Latin1_General_CP1_CI_AS  
```  
  
 <span data-ttu-id="cc5eb-123">Pour plus d’informations, consultez [Fichiers de format non-XML &#40;SQL Server&#41;](non-xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="cc5eb-123">For more information, see [Non-XML Format Files &#40;SQL Server&#41;](non-xml-format-files-sql-server.md).</span></span>  
  
 
  
### <a name="b-using-an-xml-format-file"></a><span data-ttu-id="cc5eb-124">B.</span><span class="sxs-lookup"><span data-stu-id="cc5eb-124">B.</span></span> <span data-ttu-id="cc5eb-125">Utilisation d'un fichier de format XML</span><span class="sxs-lookup"><span data-stu-id="cc5eb-125">Using an XML format file</span></span>  
 <span data-ttu-id="cc5eb-126">Le fichier de format XML suivant utilise le format de données natif [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de la table `HumanResources.myTeam` .</span><span class="sxs-lookup"><span data-stu-id="cc5eb-126">The following XML format file uses the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native data format for the `HumanResources.myTeam` table.</span></span> <span data-ttu-id="cc5eb-127">Ce fichier de format a été créé à l'aide de la commande `bcp` suivante.</span><span class="sxs-lookup"><span data-stu-id="cc5eb-127">This format file was created by using the following `bcp` command.</span></span>  
  
```  
bcp AdventureWorks.HumanResources.myTeam format nul -f myTeam.Xml -x -n -T   
```  
  
 <span data-ttu-id="cc5eb-128">Le fichier de format contient :</span><span class="sxs-lookup"><span data-stu-id="cc5eb-128">The format file contains:</span></span>  
  
```  
 <?xml version="1.0"?>  
<BCPFORMAT xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
 <RECORD>  
  <FIELD ID="1" xsi:type="NativePrefix" LENGTH="1"/>  
  <FIELD ID="2" xsi:type="NCharPrefix" PREFIX_LENGTH="2" MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
  <FIELD ID="3" xsi:type="NCharPrefix" PREFIX_LENGTH="2" MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
  <FIELD ID="4" xsi:type="NCharPrefix" PREFIX_LENGTH="2" MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
 </RECORD>  
 <ROW>  
  <COLUMN SOURCE="1" NAME="EmployeeID" xsi:type="SQLSMALLINT"/>  
  <COLUMN SOURCE="2" NAME="Name" xsi:type="SQLNVARCHAR"/>  
  <COLUMN SOURCE="3" NAME="Title" xsi:type="SQLNVARCHAR"/>  
  <COLUMN SOURCE="4" NAME="Background" xsi:type="SQLNVARCHAR"/>  
 </ROW>  
</BCPFORMAT>  
```  
  
 <span data-ttu-id="cc5eb-129">Pour plus d’informations, consultez [Fichiers de format XML &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="cc5eb-129">For more information, see [XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  

  
##  <a name="when-is-a-format-file-required"></a><a name="WhenFFrequired"></a> <span data-ttu-id="cc5eb-130">Quand faut-il utiliser un format de fichier ?</span><span class="sxs-lookup"><span data-stu-id="cc5eb-130">When Is a Format File Required?</span></span>  
 <span data-ttu-id="cc5eb-131">Une instruction INSERT ... SELECT \* FROM OPENROWSET(BULK...) nécessite toujours un fichier de format.</span><span class="sxs-lookup"><span data-stu-id="cc5eb-131">An INSERT ... SELECT \* FROM OPENROWSET(BULK...) statement always requires a format file.</span></span>  
  
-   <span data-ttu-id="cc5eb-132">Pour **bcp** ou BULK INSERT, dans les cas simples, l’utilisation d’un fichier de format est facultative et rarement nécessaire.</span><span class="sxs-lookup"><span data-stu-id="cc5eb-132">For **bcp** or BULK INSERT, in simple situations, using a format file is optional and rarely necessary.</span></span> <span data-ttu-id="cc5eb-133">Toutefois, pour les importations en bloc complexes, un fichier de format est souvent nécessaire.</span><span class="sxs-lookup"><span data-stu-id="cc5eb-133">However, for complex bulk-import situations, a format file is frequently required.</span></span>  
  
 <span data-ttu-id="cc5eb-134">Des fichiers de format sont nécessaires dans les cas suivants :</span><span class="sxs-lookup"><span data-stu-id="cc5eb-134">Format files are required if:</span></span>  
  
-   <span data-ttu-id="cc5eb-135">Le même fichier de données est utilisé comme source pour plusieurs tables possédant des schémas différents.</span><span class="sxs-lookup"><span data-stu-id="cc5eb-135">The same data file is used as a source for multiple tables that have different schemas.</span></span>  
  
-   <span data-ttu-id="cc5eb-136">Le fichier de données contient un nombre de champs différent du nombre de colonnes dans la table cible. Par exemple :</span><span class="sxs-lookup"><span data-stu-id="cc5eb-136">The data file has a different number of fields that the target table has columns; for example:</span></span>  
  
    -   <span data-ttu-id="cc5eb-137">La table cible contient au moins une colonne pour laquelle une valeur par défaut est définie ou une valeur NULL est autorisée.</span><span class="sxs-lookup"><span data-stu-id="cc5eb-137">The target table contains at least one column for which either a default value is defined or NULL is allowed.</span></span>  
  
    -   <span data-ttu-id="cc5eb-138">Les utilisateurs n'ont pas les autorisations SELECT/INSERT sur une ou plusieurs colonnes de la table.</span><span class="sxs-lookup"><span data-stu-id="cc5eb-138">The users do not have SELECT/INSERT permissions on one or more columns in the table.</span></span>  
  
    -   <span data-ttu-id="cc5eb-139">Un seul fichier de données est utilisé avec au moins deux tables dont les schémas sont différents.</span><span class="sxs-lookup"><span data-stu-id="cc5eb-139">A single data file is used with two or more tables that have different schemas.</span></span>  
  
-   <span data-ttu-id="cc5eb-140">L'ordre des colonnes est différent dans le fichier des données et la table.</span><span class="sxs-lookup"><span data-stu-id="cc5eb-140">The column order is different for the data file and table.</span></span>  
  
-   <span data-ttu-id="cc5eb-141">Les caractères de fin ou les longueurs de préfixes sont différents dans les colonnes du fichier de données.</span><span class="sxs-lookup"><span data-stu-id="cc5eb-141">The terminating characters or prefix lengths differ among the columns of the data file.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cc5eb-142">S’il n’existe pas de fichier de format et si une commande **bcp** définit un commutateur de format de données ( **-n**, **-c**, **-w**ou **-N**) ou si une opération BULK INSERT définit l’option DATAFILETYPE, le format de données défini est utilisé comme méthode par défaut pour interpréter les champs du fichier de données.</span><span class="sxs-lookup"><span data-stu-id="cc5eb-142">In the absence of a format file, if a **bcp** command specifies a data-format switch (**-n**, **-c**, **-w**, or **-N**) or a BULK INSERT operation specifies the DATAFILETYPE option, the specified data format is used as the default method of interpreting the fields of the data file.</span></span>  
  
 
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="cc5eb-143">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="cc5eb-143">Related Tasks</span></span>  
  
-   [<span data-ttu-id="cc5eb-144">Créer un fichier de format &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="cc5eb-144">Create a Format File &#40;SQL Server&#41;</span></span>](create-a-format-file-sql-server.md)  
  
-   [<span data-ttu-id="cc5eb-145">Utiliser un fichier de format pour importer des données en bloc &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="cc5eb-145">Use a Format File to Bulk Import Data &#40;SQL Server&#41;</span></span>](use-a-format-file-to-bulk-import-data-sql-server.md)  
  
-   [<span data-ttu-id="cc5eb-146">Utiliser un fichier de format pour ignorer une colonne de table &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="cc5eb-146">Use a Format File to Skip a Table Column &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-table-column-sql-server.md)  
  
-   [<span data-ttu-id="cc5eb-147">Utiliser un fichier de format pour ignorer un champ de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="cc5eb-147">Use a Format File to Skip a Data Field &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-data-field-sql-server.md)  
  
-   [<span data-ttu-id="cc5eb-148">Utiliser un fichier de format pour mapper les colonnes d’une table sur les champs d’un fichier de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="cc5eb-148">Use a Format File to Map Table Columns to Data-File Fields &#40;SQL Server&#41;</span></span>](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md)  
  

  
## <a name="see-also"></a><span data-ttu-id="cc5eb-149">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cc5eb-149">See Also</span></span>  
 <span data-ttu-id="cc5eb-150">[Fichiers de format non-XML &#40;SQL Server&#41;](non-xml-format-files-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="cc5eb-150">[Non-XML Format Files &#40;SQL Server&#41;](non-xml-format-files-sql-server.md) </span></span>  
 <span data-ttu-id="cc5eb-151">[Fichiers de format XML &#40;SQL Server&#41;](xml-format-files-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="cc5eb-151">[XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md) </span></span>  
 [<span data-ttu-id="cc5eb-152">Formats de données pour l’importation ou l’exportation en bloc &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="cc5eb-152">Data Formats for Bulk Import or Bulk Export &#40;SQL Server&#41;</span></span>](data-formats-for-bulk-import-or-bulk-export-sql-server.md)  
  
  
