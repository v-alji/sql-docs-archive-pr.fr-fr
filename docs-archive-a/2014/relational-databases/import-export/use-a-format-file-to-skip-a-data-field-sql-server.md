---
title: Utiliser un fichier de format pour ignorer un champ de données (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- format files [SQL Server], skipping data fields
- skipping data fields when importing
ms.assetid: 6a76517e-983b-47a1-8f02-661b99859a8b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2d3f78c3c97c5bbe862867d5f51ff35f57d147df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615151"
---
# <a name="use-a-format-file-to-skip-a-data-field-sql-server"></a><span data-ttu-id="08e53-102">Utiliser un fichier de format pour ignorer un champ de données (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="08e53-102">Use a Format File to Skip a Data Field (SQL Server)</span></span>
  <span data-ttu-id="08e53-103">Le nombre de champs contenus dans un fichier de données peut être supérieur au nombre de colonnes dans la table.</span><span class="sxs-lookup"><span data-stu-id="08e53-103">A data file can contain more fields than the number of columns in the table.</span></span> <span data-ttu-id="08e53-104">Cette rubrique explique comment modifier les fichiers de format non-XML et XML en mappant les colonnes de la table avec les champs de données correspondants et en ignorant les champs supplémentaires afin de prendre en charge un fichier de données contenant davantage de champs.</span><span class="sxs-lookup"><span data-stu-id="08e53-104">This topic describes modifying both non-XML and XML format files to accommodate a data file with more fields by mapping the table columns to the corresponding data fields and ignoring the extra fields.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="08e53-105">Vous pouvez utiliser un fichier de format non-XML ou XML pour importer en bloc un fichier de données dans la table à l’aide d’une commande **BCP** , d’une instruction BULK INSERT ou d’une instruction INSERT... SELECT \* FROM OPENROWSET (BULK...).</span><span class="sxs-lookup"><span data-stu-id="08e53-105">Either a non-XML or XML format file can be used to bulk import a data file into the table by using a **bcp** command, BULK INSERT statement, or INSERT ... SELECT \* FROM OPENROWSET(BULK...) statement.</span></span> <span data-ttu-id="08e53-106">Pour plus d’informations, consultez [Utiliser un fichier de format pour importer des données en bloc &#40;SQL Server&#41;](use-a-format-file-to-bulk-import-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="08e53-106">For more information, see [Use a Format File to Bulk Import Data &#40;SQL Server&#41;](use-a-format-file-to-bulk-import-data-sql-server.md).</span></span>  
  
## <a name="sample-data-file-and-table"></a><span data-ttu-id="08e53-107">Exemples de fichier de données et de table</span><span class="sxs-lookup"><span data-stu-id="08e53-107">Sample Data File and Table</span></span>  
 <span data-ttu-id="08e53-108">Les fichiers de format modifiés pris en exemple dans cette rubrique sont fondés sur la table et le fichier de données suivants.</span><span class="sxs-lookup"><span data-stu-id="08e53-108">The examples of modified format files in this topic are based on the following table and data file.</span></span>  
  
### <a name="sample-table"></a><span data-ttu-id="08e53-109">Exemple de table</span><span class="sxs-lookup"><span data-stu-id="08e53-109">Sample Table</span></span>  
 <span data-ttu-id="08e53-110">Une table nommée `myTestSkipField` doit être créée dans l'exemple de base de données [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] sous le schéma `dbo`.</span><span class="sxs-lookup"><span data-stu-id="08e53-110">The examples require that a table named `myTestSkipField` be created in the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] sample database under the `dbo` schema.</span></span> <span data-ttu-id="08e53-111">Pour créer cette table, dans [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] l’éditeur de requête, exécutez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="08e53-111">To create this table, in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor, run the following code:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
CREATE TABLE myTestSkipField   
   (  
   PersonID smallint,  
   FirstName nvarchar(50) ,  
   LastName nvarchar(50)   
   );  
GO  
```  
  
### <a name="sample-data-file"></a><span data-ttu-id="08e53-112">Fichier de données d'exemple</span><span class="sxs-lookup"><span data-stu-id="08e53-112">Sample Data File</span></span>  
 <span data-ttu-id="08e53-113">Le fichier de données, `myTestSkipField-c.dat`, contient les enregistrements suivants :</span><span class="sxs-lookup"><span data-stu-id="08e53-113">The data file, `myTestSkipField-c.dat`, contains the following records:</span></span>  
  
```  
1,Skipme,DataField3,DataField4  
1,Skipme,DataField3,DataField4  
1,Skipme,DataField3,DataField4  
```  
  
 <span data-ttu-id="08e53-114">Pour effectuer l’importation en bloc de données de `myTestSkipField-c.dat` dans la table `myTestSkipField` , le fichier de format doit effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="08e53-114">To bulk import data from `myTestSkipField-c.dat` into the `myTestSkipField` table, the format file must do the following:</span></span>  
  
-   <span data-ttu-id="08e53-115">mapper le premier champ des données à la première colonne, `PersonID`;</span><span class="sxs-lookup"><span data-stu-id="08e53-115">Map the first data field to the first column, `PersonID`.</span></span>  
  
-   <span data-ttu-id="08e53-116">ignorer le deuxième champ des données ;</span><span class="sxs-lookup"><span data-stu-id="08e53-116">Skip the second data field.</span></span>  
  
-   <span data-ttu-id="08e53-117">mapper le troisième champ des données à la deuxième colonne, `FirstName`;</span><span class="sxs-lookup"><span data-stu-id="08e53-117">Map the third data field to the second column, `FirstName`.</span></span>  
  
-   <span data-ttu-id="08e53-118">mapper le quatrième champ des données à la troisième colonne, `LastName`.</span><span class="sxs-lookup"><span data-stu-id="08e53-118">Map the fourth data field to the third column, `LastName`.</span></span>  
  
## <a name="non-xml-format-file-for-more-data-fields"></a><span data-ttu-id="08e53-119">Fichier de format non-XML pour davantage de champs de données</span><span class="sxs-lookup"><span data-stu-id="08e53-119">Non-XML Format File for More Data Fields</span></span>  
 <span data-ttu-id="08e53-120">Le fichier de format suivant, `myTestSkipField.fmt`, mappe les champs de `myTestSkipField-c.dat` aux colonnes de la table `myTestSkipField`.</span><span class="sxs-lookup"><span data-stu-id="08e53-120">The following format file, `myTestSkipField.fmt`, maps the fields in `myTestSkipField-c.dat` to the columns of the `myTestSkipField` table.</span></span> <span data-ttu-id="08e53-121">Ce fichier de format utilise le format de données caractères.</span><span class="sxs-lookup"><span data-stu-id="08e53-121">The format file uses character data format.</span></span> <span data-ttu-id="08e53-122">Pour ignorer le mappage d'une colonne, vous devez attribuer à son ordre de colonne la valeur 0, à l'image de la colonne `ExtraField` dans le fichier de format.</span><span class="sxs-lookup"><span data-stu-id="08e53-122">Skipping a column mapping requires changing its column order value to 0, as shown for the `ExtraField` column in the format file.</span></span>  
  
 <span data-ttu-id="08e53-123">Le fichier de format `myTestSkipField.fmt` contient les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="08e53-123">The `myTestSkipField.fmt` format file contains the following information:</span></span>  
  
```  
9.0  
4  
1       SQLCHAR       0       7       ","      1     PersonID               ""  
2       SQLCHAR       0       100       ","    0     ExtraField             SQL_Latin1_General_CP1_CI_AS  
3       SQLCHAR       0       100     ","      2     FirstName              SQL_Latin1_General_CP1_CI_AS  
4       SQLCHAR       0       100     "\r\n"   3     LastName               SQL_Latin1_General_CP1_CI_AS  
  
```  
  
> [!NOTE]  
>  <span data-ttu-id="08e53-124">Pour plus d’informations sur la syntaxe des fichiers de format non-XML, consultez [Fichiers de format non-XML &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="08e53-124">For information about the syntax of non-XML format files, see [Non-XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  
### <a name="examples"></a><span data-ttu-id="08e53-125">Exemples</span><span class="sxs-lookup"><span data-stu-id="08e53-125">Examples</span></span>  
 <span data-ttu-id="08e53-126">Cet exemple fait appel à `INSERT ... SELECT * FROM OPENROWSET(BULK...)` et utilise le fichier de format `myTestSkipField.fmt`.</span><span class="sxs-lookup"><span data-stu-id="08e53-126">The following example uses `INSERT ... SELECT * FROM OPENROWSET(BULK...)` using the `myTestSkipField.fmt` format file.</span></span> <span data-ttu-id="08e53-127">Dans cet exemple, le fichier de données `myTestSkipField-c.dat` est importé en bloc dans la table `myTestSkipField` .</span><span class="sxs-lookup"><span data-stu-id="08e53-127">The example bulk imports the `myTestSkipField-c.dat` data file into the `myTestSkipField` table.</span></span> <span data-ttu-id="08e53-128">Pour créer l'exemple de fichier de données et de table, consultez la section « Exemples de fichier de données et de table », plus haut dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="08e53-128">To create the sample table and data file, see "Sample Data File and Table," earlier in this topic.</span></span>  
  
 <span data-ttu-id="08e53-129">Dans l'Éditeur de requête [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], exécutez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="08e53-129">In the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor, run the following code:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
INSERT INTO myTestSkipField   
   SELECT *  
      FROM  OPENROWSET(BULK  'C:\myTestSkipField-c.dat',  
      FORMATFILE='C:\myTestSkipField.fmt'    
       ) AS t1;  
GO   
```  
  
## <a name="xml-format-file-for-more-data-fields"></a><span data-ttu-id="08e53-130">Fichier de format XML pour davantage de champs de données</span><span class="sxs-lookup"><span data-stu-id="08e53-130">XML Format File for More Data Fields</span></span>  
 <span data-ttu-id="08e53-131">Le fichier de format présenté dans cet exemple est basé sur un autre fichier de format, `myTestSkipField.xml`, qui utilise un format de données de caractères et dont le nombre et l'ordre des champs correspondent exactement à ceux des colonnes de la table `myTestSkipField`.</span><span class="sxs-lookup"><span data-stu-id="08e53-131">The format file presented in this example is based on another format file, `myTestSkipField.xml`, which uses character data format throughout and whose fields correspond exactly in number and order to the columns in the `myTestSkipField` table.</span></span> <span data-ttu-id="08e53-132">Pour afficher le contenu de ce fichier de format, consultez [Créer un fichier de format &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="08e53-132">To view the contents of that format file, see [Create a Format File &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span></span>  
  
 <span data-ttu-id="08e53-133">Le fichier de format suivant, `myTestSkipField.xml`, mappe les champs de `myTestSkipField-c.dat` aux colonnes de la table `myTestSkipField`.</span><span class="sxs-lookup"><span data-stu-id="08e53-133">The following format file, `myTestSkipField.xml`, maps the fields in `myTestSkipField-c.dat` to the columns of the `myTestSkipField` table.</span></span> <span data-ttu-id="08e53-134">Ce fichier de format utilise le format de données caractères.</span><span class="sxs-lookup"><span data-stu-id="08e53-134">The format file uses character data format.</span></span>  
  
 <span data-ttu-id="08e53-135">Le fichier de format `myTestSkipField.xml` contient les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="08e53-135">The `myTestSkipField.xml` format file contains the following information:</span></span>  
  
```  
<?xml version="1.0"?>  
<BCPFORMAT xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
 <RECORD>  
  <FIELD ID="1" xsi:type="CharTerm" TERMINATOR="," MAX_LENGTH="7"/>  
  <FIELD ID="2" xsi:type="CharTerm" TERMINATOR="," MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
  <FIELD ID="3" xsi:type="CharTerm" TERMINATOR="," MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
  <FIELD ID="4" xsi:type="CharTerm" TERMINATOR="\r\n" MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
 </RECORD>  
 <ROW>  
  <COLUMN SOURCE="1" NAME="PersonID" xsi:type="SQLSMALLINT"/>  
  <COLUMN SOURCE="3" NAME="FirstName" xsi:type="SQLNVARCHAR"/>  
  <COLUMN SOURCE="4" NAME="LastName" xsi:type="SQLNVARCHAR"/>  
 </ROW>  
</BCPFORMAT>  
```  
  
### <a name="examples"></a><span data-ttu-id="08e53-136">Exemples</span><span class="sxs-lookup"><span data-stu-id="08e53-136">Examples</span></span>  
 <span data-ttu-id="08e53-137">Cet exemple fait appel à `INSERT ... SELECT * FROM OPENROWSET(BULK...)` et utilise le fichier de format `myTestSkipField.Xml`.</span><span class="sxs-lookup"><span data-stu-id="08e53-137">The following example uses `INSERT ... SELECT * FROM OPENROWSET(BULK...)` using the `myTestSkipField.Xml` format file.</span></span> <span data-ttu-id="08e53-138">Dans cet exemple, le fichier de données `myTestSkipField-c.dat` est importé en bloc dans la table `myTestSkipField` .</span><span class="sxs-lookup"><span data-stu-id="08e53-138">The example bulk imports the `myTestSkipField-c.dat` data file into the `myTestSkipField` table.</span></span> <span data-ttu-id="08e53-139">Pour créer l'exemple de fichier de données et de table, consultez la section « Exemples de fichier de données et de table », plus haut dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="08e53-139">To create the sample table and data file, see "Sample Data File and Table," earlier in this topic.</span></span>  
  
 <span data-ttu-id="08e53-140">Dans l'Éditeur de requête [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], exécutez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="08e53-140">In the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor, run the following code:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
INSERT INTO myTestSkipField   
  SELECT *  
      FROM  OPENROWSET(BULK  'C:\myTestSkipField-c.dat',  
      FORMATFILE='C:\myTestSkipField.xml'    
       ) AS t1;  
GO  
  
```  
  
> [!NOTE]  
>  <span data-ttu-id="08e53-141">Pour plus d’informations sur la syntaxe du schéma XML et pour d’autres exemples de fichiers de format XML, consultez [Fichiers de format XML &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="08e53-141">For information about the syntax of the XML Schema and additional samples of XML format files, see [XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08e53-142">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="08e53-142">See Also</span></span>  
 <span data-ttu-id="08e53-143">[Utilitaire bcp](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="08e53-143">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="08e53-144">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="08e53-144">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 <span data-ttu-id="08e53-145">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="08e53-145">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 <span data-ttu-id="08e53-146">[Utiliser un fichier de format pour ignorer une colonne de table &#40;SQL Server&#41;](use-a-format-file-to-skip-a-table-column-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="08e53-146">[Use a Format File to Skip a Table Column &#40;SQL Server&#41;](use-a-format-file-to-skip-a-table-column-sql-server.md) </span></span>  
 [<span data-ttu-id="08e53-147">Utiliser un fichier de format pour mapper les colonnes d’une table sur les champs d’un fichier de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="08e53-147">Use a Format File to Map Table Columns to Data-File Fields &#40;SQL Server&#41;</span></span>](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md)  
  
  
