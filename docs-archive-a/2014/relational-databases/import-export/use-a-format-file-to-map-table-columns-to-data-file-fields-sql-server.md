---
title: Utiliser un fichier de format pour mapper les colonnes d’une table aux champs d’un fichier de données (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- mapping columns to fields during import [SQL Server]
- format files [SQL Server], mapping columns to fields
ms.assetid: e7ee4f7e-24c4-4eb7-84d2-41e57ccc1ef1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c7de0b5ce486f187a1bdd27197984aa3c411f4a1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602839"
---
# <a name="use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server"></a><span data-ttu-id="5f32d-102">Utiliser un fichier de format pour mapper les colonnes d'une table aux champs d'un fichier de données (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="5f32d-102">Use a Format File to Map Table Columns to Data-File Fields (SQL Server)</span></span>
  <span data-ttu-id="5f32d-103">Il se peut que les champs d'un fichier de données ne soient pas dans le même ordre que les colonnes correspondantes présentes dans la table.</span><span class="sxs-lookup"><span data-stu-id="5f32d-103">A data file can contain fields arranged in a different order from the corresponding columns in the table.</span></span> <span data-ttu-id="5f32d-104">Cette rubrique présente les fichiers de format XML et non-XML ayant été modifiés de sorte à accepter un fichier de données dont les champs sont organisés dans un ordre différent de celui des colonnes de la table correspondante.</span><span class="sxs-lookup"><span data-stu-id="5f32d-104">This topic presents both non-XML and XML format files that have been modified to accommodate a data file whose fields are arranged in a different order from the table columns.</span></span> <span data-ttu-id="5f32d-105">Le fichier de format modifié permet de mapper les champs de données sur les colonnes correspondantes de la table.</span><span class="sxs-lookup"><span data-stu-id="5f32d-105">The modified format file maps the data fields to their corresponding table columns.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5f32d-106">Un fichier de format non-XML ou un fichier de format XML peut être utilisé pour importer en bloc un fichier de données dans la table à l’aide d’une commande **BCP** , d’une instruction BULK INSERT ou d’une instruction INSERT... SELECT \* FROM OPENROWSET (BULK...).</span><span class="sxs-lookup"><span data-stu-id="5f32d-106">Either a non-XML format file or an XML format file can be used to bulk import a data file into the table by using a **bcp** command, BULK INSERT statement, or INSERT ... SELECT \* FROM OPENROWSET(BULK...) statement.</span></span> <span data-ttu-id="5f32d-107">Pour plus d’informations, consultez [Utiliser un fichier de format pour importer des données en bloc &#40;SQL Server&#41;](use-a-format-file-to-bulk-import-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="5f32d-107">For more information, see [Use a Format File to Bulk Import Data &#40;SQL Server&#41;](use-a-format-file-to-bulk-import-data-sql-server.md).</span></span>  
  
## <a name="sample-table-and-data-file"></a><span data-ttu-id="5f32d-108">Exemples de table et de fichier de données</span><span class="sxs-lookup"><span data-stu-id="5f32d-108">Sample Table and Data File</span></span>  
 <span data-ttu-id="5f32d-109">Les fichiers de format modifiés pris en exemple dans cette rubrique sont fondés sur la table et le fichier de données suivants.</span><span class="sxs-lookup"><span data-stu-id="5f32d-109">The examples of modified format files in this topic are based on the following table and data file.</span></span>  
  
### <a name="sample-table"></a><span data-ttu-id="5f32d-110">Exemple de table</span><span class="sxs-lookup"><span data-stu-id="5f32d-110">Sample Table</span></span>  
 <span data-ttu-id="5f32d-111">Dans les exemples de cette rubrique, une table nommée `myTestOrder` doit être créée dans l'exemple de base de données [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] sous le schéma `dbo` .</span><span class="sxs-lookup"><span data-stu-id="5f32d-111">The examples in this topic require that a table named `myTestOrder` be created in the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] sample database under the `dbo` schema.</span></span> <span data-ttu-id="5f32d-112">Pour créer cette table, dans l'Éditeur de requêtes [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , exécutez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="5f32d-112">To create this table, in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor, execute the following code:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
CREATE TABLE myTestOrder   
   (  
   Col1 smallint,  
   Col2 nvarchar(50) ,  
   Col3 nvarchar(50) ,   
   Col4 nvarchar(50)   
   );  
GO  
  
```  
  
### <a name="data-file"></a><span data-ttu-id="5f32d-113">Fichier de données</span><span class="sxs-lookup"><span data-stu-id="5f32d-113">Data File</span></span>  
 <span data-ttu-id="5f32d-114">Le fichier de données, `myTestOrder-c.txt`, contient les enregistrements suivants :</span><span class="sxs-lookup"><span data-stu-id="5f32d-114">The data file, `myTestOrder-c.txt`, contains the following records:</span></span>  
  
```  
DataField3,DataField2,1,DataField4  
DataField3,DataField2,1,DataField4  
DataField3,DataField2,1,DataField4  
  
```  
  
 <span data-ttu-id="5f32d-115">Pour importer des données en bloc depuis `myTestSkipCol2-c.dat` dans la table `myTestSkipCol`, le fichier de format doit mapper le premier champ de données à `Col3`, le deuxième champ à `Col2`, le troisième champ à `Col1`, et le quatrième champ à `Col4`.</span><span class="sxs-lookup"><span data-stu-id="5f32d-115">To bulk import data from `myTestSkipCol2-c.dat` into the `myTestSkipCol` table, the format file must map the first data field to `Col3`, the second data field to `Col2`, the third data field to `Col1`, and the fourth data field to `Col4`.</span></span>  
  
## <a name="using-a-non-xml-format-file"></a><span data-ttu-id="5f32d-116">Utilisation d'un fichier de format non-XML</span><span class="sxs-lookup"><span data-stu-id="5f32d-116">Using a Non-XML Format File</span></span>  
 <span data-ttu-id="5f32d-117">Pour modifier l'ordre d'un mappage de colonne, vous devez modifier la valeur d'ordre de la colonne afin d'indiquer la position du champ de données correspondant.</span><span class="sxs-lookup"><span data-stu-id="5f32d-117">You can change the order of a column mapping by changing the order value for the column to indicate the position of the corresponding data field.</span></span>  
  
 <span data-ttu-id="5f32d-118">L'exemple suivant présente un fichier de format non-XML, `myTestOrder.fmt`, qui mappe les champs de `myTestOrder-c.txt` aux colonnes de la table `myTestOrder`.</span><span class="sxs-lookup"><span data-stu-id="5f32d-118">The following sample non-XML format file presents a format file, `myTestOrder.fmt`, that maps the fields in `myTestOrder-c.txt` to the columns of the `myTestOrder` table.</span></span> <span data-ttu-id="5f32d-119">Pour plus d'informations sur la table et le fichier de données et la manière de les créer, consultez la section « Exemples de fichier de données et de table », plus haut dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="5f32d-119">For information about how to create the data file and table, see "Sample Table and Data File," earlier in this topic.</span></span> <span data-ttu-id="5f32d-120">Ce fichier de format utilise le format de données caractères.</span><span class="sxs-lookup"><span data-stu-id="5f32d-120">The format file uses character data format.</span></span>  
  
 <span data-ttu-id="5f32d-121">Le fichier de format contient les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="5f32d-121">The format file contains the following information:</span></span>  
  
```  
9.0  
4  
1       SQLCHAR       0       100     ","     3     Col3               SQL_Latin1_General_CP1_CI_AS  
2       SQLCHAR       0       100     ","     2     Col2               SQL_Latin1_General_CP1_CI_AS  
3       SQLCHAR       0       7       ","     1     Col1               ""  
4       SQLCHAR       0       100     "\r\n"  4     Col4               SQL_Latin1_General_CP1_CI_AS  
  
```  
  
> [!NOTE]  
>  <span data-ttu-id="5f32d-122">Pour plus d’informations sur la structure des fichiers de format non-XML, consultez [Fichiers de format non-XML &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="5f32d-122">For more information about the layout of non-XML format files, see [Non-XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  
### <a name="example"></a><span data-ttu-id="5f32d-123">Exemple</span><span class="sxs-lookup"><span data-stu-id="5f32d-123">Example</span></span>  
 <span data-ttu-id="5f32d-124">L'exemple suivant utilise une instruction `BULK INSERT` pour procéder à l'importation en bloc de données issues du fichier de données `myTestOrder-c.txt` vers l'exemple de table `myTestOrder` à l'aide du fichier de format non-XML `myTestOrder.fmt`.</span><span class="sxs-lookup"><span data-stu-id="5f32d-124">The following example uses a `BULK INSERT` statement to bulk import data from the `myTestOrder-c.txt` data file into the `myTestOrder` sample table by using the `myTestOrder.fmt` non-XML format file.</span></span>  
  
 <span data-ttu-id="5f32d-125">Dans l'Éditeur de requête [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], exécutez :</span><span class="sxs-lookup"><span data-stu-id="5f32d-125">In the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
BULK INSERT myTestOrder  
FROM 'C:\myTestOrder-c.txt'   
WITH (formatfile='C:\myTestOrder.fmt');  
GO  
  
```  
  
## <a name="using-an-xml-format-file"></a><span data-ttu-id="5f32d-126">Utilisation d'un fichier de format XML</span><span class="sxs-lookup"><span data-stu-id="5f32d-126">Using an XML Format File</span></span>  
 <span data-ttu-id="5f32d-127">L'exemple suivant présente un fichier de format non-XML, `myTestOrder.xml`, qui mappe les champs de `myTestOrder-c.txt` sur les colonnes de la table `myTestOrder`. Pour plus d'informations sur la création du fichier de données et de la table, consultez « Exemples de table et de fichier de données » plus haut dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="5f32d-127">The following sample non-XML format file presents a format file, `myTestOrder.xml`, that maps the fields in `myTestOrder-c.txt` to the columns of the `myTestOrder` table For information about how to create the data file and table, see "Sample Table and Data File," earlier in this topic.</span></span>  
  
 <span data-ttu-id="5f32d-128">Le fichier de format `myTestOrder.xml` contient les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="5f32d-128">The `myTestOrder.xml` format file contains the following information:</span></span>  
  
```  
<?xml version="1.0"?>  
<BCPFORMAT xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format"   
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
 <RECORD>  
  <FIELD ID="1" xsi:type="CharTerm" TERMINATOR="," MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
  <FIELD ID="2" xsi:type="CharTerm" TERMINATOR="," MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
  <FIELD ID="3" xsi:type="CharTerm" TERMINATOR="," MAX_LENGTH="7"/>  
  <FIELD ID="4" xsi:type="CharTerm" TERMINATOR="\r\n" MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
 </RECORD>  
 <ROW>  
  <COLUMN SOURCE="3" NAME="Col1" xsi:type="SQLSMALLINT"/>  
  <COLUMN SOURCE="2" NAME="Col2" xsi:type="SQLNVARCHAR"/>  
  <COLUMN SOURCE="1" NAME="Col3" xsi:type="SQLNVARCHAR"/>  
  <COLUMN SOURCE="4" NAME="Col4" xsi:type="SQLNVARCHAR"/>  
 </ROW>  
</BCPFORMAT>  
  
```  
  
> [!NOTE]  
>  <span data-ttu-id="5f32d-129">Pour plus d’informations sur la syntaxe du schéma XML et pour d’autres exemples de fichiers de format XML, consultez [Fichiers de format XML &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="5f32d-129">For information about the syntax of the XML Schema and additional samples of XML format files, see [XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  
### <a name="example"></a><span data-ttu-id="5f32d-130">Exemple</span><span class="sxs-lookup"><span data-stu-id="5f32d-130">Example</span></span>  
 <span data-ttu-id="5f32d-131">L'exemple suivant utilise le fournisseur d'ensemble de lignes en bloc `OPENROWSET` pour procéder à l'importation du fichier de données `myTestOrder-c.txt` vers l'exemple de table `myTestOrder` à l'aide du fichier de format XML `myTestOrder.xml` .</span><span class="sxs-lookup"><span data-stu-id="5f32d-131">The following example uses the `OPENROWSET` bulk rowset provider to import data from the `myTestOrder-c.txt` data file into the `myTestOrder` sample table by using the `myTestOrder.xml` XML format file.</span></span> <span data-ttu-id="5f32d-132">L'instruction `INSERT... SELECT` spécifie la liste de colonnes de la liste de sélection.</span><span class="sxs-lookup"><span data-stu-id="5f32d-132">The `INSERT... SELECT` statement specifies the column list in the select list.</span></span>  
  
 <span data-ttu-id="5f32d-133">Dans l'Éditeur de requête [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , exécutez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="5f32d-133">In the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor, execute the following code:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
INSERT INTO myTestOrder   
  SELECT Col1, Col2, Col3, Col4  
      FROM  OPENROWSET(BULK  'C:\myTestOrder-c.txt',  
      FORMATFILE='C:\myTestOrder.Xml'    
       ) AS t1;  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="5f32d-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5f32d-134">See Also</span></span>  
 <span data-ttu-id="5f32d-135">[Utiliser un fichier de format pour ignorer une colonne de table &#40;SQL Server&#41;](use-a-format-file-to-skip-a-table-column-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5f32d-135">[Use a Format File to Skip a Table Column &#40;SQL Server&#41;](use-a-format-file-to-skip-a-table-column-sql-server.md) </span></span>  
 [<span data-ttu-id="5f32d-136">Utiliser un fichier de format pour ignorer un champ de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5f32d-136">Use a Format File to Skip a Data Field &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-data-field-sql-server.md)  
  
  
