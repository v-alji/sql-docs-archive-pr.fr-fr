---
title: Utiliser un fichier de format pour importer des données en bloc (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- bulk importing [SQL Server], format files
- format files [SQL Server], importing data using
ms.assetid: 2956df78-833f-45fa-8a10-41d6522562b9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c6d9779209b3ffb317658243c168d74740f6731b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615152"
---
# <a name="use-a-format-file-to-bulk-import-data-sql-server"></a><span data-ttu-id="2c0df-102">Utiliser un fichier de format pour importer des données en bloc (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="2c0df-102">Use a Format File to Bulk Import Data (SQL Server)</span></span>
  <span data-ttu-id="2c0df-103">Cette rubrique illustre l'utilisation d'un fichier de format dans les importations en bloc.</span><span class="sxs-lookup"><span data-stu-id="2c0df-103">This topic illustrates the use of a format file in bulk-import operations.</span></span> <span data-ttu-id="2c0df-104">Le fichier de format met en relation les champs du fichier de données avec les colonnes de la table.</span><span class="sxs-lookup"><span data-stu-id="2c0df-104">The format file maps the fields of the data file to the columns of the table.</span></span>  <span data-ttu-id="2c0df-105">Vous pouvez utiliser un fichier de format non-XML ou XML pour importer des données en bloc lors de l’utilisation d’une commande **BCP** ou d’une BULK INSERT ou d’une instruction INSERT... SELECT \* FROM OPENROWSET (BULK...) [!INCLUDE[tsql](../../includes/tsql-md.md)] commande.</span><span class="sxs-lookup"><span data-stu-id="2c0df-105">You can use a non-XML or XML format file to bulk import data when using a **bcp** command or a BULK INSERT or INSERT ... SELECT \* FROM OPENROWSET(BULK...) [!INCLUDE[tsql](../../includes/tsql-md.md)] command.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2c0df-106">Pour qu'un fichier de format fonctionne avec un fichier de données de caractères Unicode, tous les champs d'entrée doivent être des chaînes de texte Unicode (autrement dit, des chaînes Unicode de taille fixe ou terminées par un caractère).</span><span class="sxs-lookup"><span data-stu-id="2c0df-106">For a format file to work with a Unicode character data file, all the input fields must be Unicode text strings (that is, either fixed-size or character-terminated Unicode strings).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2c0df-107">Si vous n’êtes pas familiarisé avec les fichiers de format, consultez [fichiers de format non-XML &#40;SQL Server&#41;](xml-format-files-sql-server.md) et les [fichiers de format XML &#40;SQL Server ](xml-format-files-sql-server.md)&#41;.</span><span class="sxs-lookup"><span data-stu-id="2c0df-107">If you are unfamiliar with format files, see [Non-XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md) and [XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  
## <a name="format-file-options-for-bulk-import-commands"></a><span data-ttu-id="2c0df-108">Options des fichiers de format pour les commandes d'importation en bloc</span><span class="sxs-lookup"><span data-stu-id="2c0df-108">Format File Options for Bulk-Import Commands</span></span>  
 <span data-ttu-id="2c0df-109">Le tableau ci-dessous récapitule l'option de fichier de format de chaque commande d'importation en bloc.</span><span class="sxs-lookup"><span data-stu-id="2c0df-109">The following table summarizes the format-file option of for each of the bulk-import commands.</span></span>  
  
|<span data-ttu-id="2c0df-110">Commande de chargement en bloc</span><span class="sxs-lookup"><span data-stu-id="2c0df-110">Bulk-load Command</span></span>|<span data-ttu-id="2c0df-111">Utilisation de l'option de fichier de format</span><span class="sxs-lookup"><span data-stu-id="2c0df-111">Using the Format-File Option</span></span>|  
|------------------------|-----------------------------------|  
|<span data-ttu-id="2c0df-112">BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="2c0df-112">BULK INSERT</span></span>|<span data-ttu-id="2c0df-113">FORMATFILE = '*chemin_fichier_format*'</span><span class="sxs-lookup"><span data-stu-id="2c0df-113">FORMATFILE = '*format_file_path*'</span></span>|  
|<span data-ttu-id="2c0df-114">INSERT ... SELECT \* FROM OPENROWSET(BULK...)</span><span class="sxs-lookup"><span data-stu-id="2c0df-114">INSERT ... SELECT \* FROM OPENROWSET(BULK...)</span></span>|<span data-ttu-id="2c0df-115">FORMATFILE = '*chemin_fichier_format*'</span><span class="sxs-lookup"><span data-stu-id="2c0df-115">FORMATFILE = '*format_file_path*'</span></span>|  
|<span data-ttu-id="2c0df-116">**BCP** ... **dans**</span><span class="sxs-lookup"><span data-stu-id="2c0df-116">**bcp** ... **in**</span></span>|<span data-ttu-id="2c0df-117">**-f** *format_file*</span><span class="sxs-lookup"><span data-stu-id="2c0df-117">**-f** *format_file*</span></span>|  
  
 <span data-ttu-id="2c0df-118">Pour plus d’informations, consultez [Utilitaire bcp](../../tools/bcp-utility.md), [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) ou [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2c0df-118">For more information, see [bcp Utility](../../tools/bcp-utility.md), [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql), or [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2c0df-119">Pour exporter ou importer en bloc des données SQLXML, utilisez l'un des types de données ci-dessous dans votre fichier de format : SQLCHAR ou SQLVARYCHAR (les données sont envoyées dans la page de codes client ou dans la page de codes inhérente au classement) ; SQLNCHAR ou SQLNVARCHAR (les données sont envoyées au format Unicode) ; SQLBINARY ou SQLVARYBIN (les données sont envoyées sans être converties).</span><span class="sxs-lookup"><span data-stu-id="2c0df-119">To bulk export or import SQLXML data, use one of the following data types in your format file: SQLCHAR or SQLVARYCHAR (the data is sent in the client code page or in the code page implied by the collation), SQLNCHAR or SQLNVARCHAR (the data is sent as Unicode), or SQLBINARY or SQLVARYBIN (the data is sent without any conversion).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="2c0df-120">Exemples</span><span class="sxs-lookup"><span data-stu-id="2c0df-120">Examples</span></span>  
 <span data-ttu-id="2c0df-121">Les exemples de cette section illustrent l’utilisation de fichiers de format pour importer des données en bloc à l’aide de la commande **BCP** et du Bulk Insert, ainsi que des instructions INSERT... SELECT \* FROM OPENROWSET (BULK...).</span><span class="sxs-lookup"><span data-stu-id="2c0df-121">The examples in this section illustrate how to use format files to bulk-import data by using the **bcp** command and the BULK INSERT, and INSERT ... SELECT \* FROM OPENROWSET(BULK...) statements.</span></span> <span data-ttu-id="2c0df-122">Avant de pouvoir exécuter un des exemples d'importation en bloc, vous devez créer un exemple de table, de fichier de données et de fichier de format.</span><span class="sxs-lookup"><span data-stu-id="2c0df-122">Before you can run one of the bulk-import examples, you need to create a sample table, data file, and a format file.</span></span>  
  
### <a name="sample-table"></a><span data-ttu-id="2c0df-123">Exemple de table</span><span class="sxs-lookup"><span data-stu-id="2c0df-123">Sample Table</span></span>  
 <span data-ttu-id="2c0df-124">Une table nommée **myTestFormatFiles** doit être créée dans l'exemple de base de données [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] sous le schéma **dbo** .</span><span class="sxs-lookup"><span data-stu-id="2c0df-124">The examples require that a table named **myTestFormatFiles** table be created in the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] sample database under the **dbo** schema.</span></span> <span data-ttu-id="2c0df-125">Pour créer cette table, dans l'éditeur de requêtes [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] , exécutez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="2c0df-125">To create this table, in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
CREATE TABLE myTestFormatFiles (  
   Col1 smallint,  
   Col2 nvarchar(50),  
   Col3 nvarchar(50),  
   Col4 nvarchar(50)  
   );  
GO  
```  
  
### <a name="sample-data-file"></a><span data-ttu-id="2c0df-126">Fichier de données d'exemple</span><span class="sxs-lookup"><span data-stu-id="2c0df-126">Sample Data File</span></span>  
 <span data-ttu-id="2c0df-127">Les exemples utilisent un fichier de données d'exemple, `myTestFormatFiles-c.Dat`, qui contient les enregistrements suivants.</span><span class="sxs-lookup"><span data-stu-id="2c0df-127">The examples use a sample data file, `myTestFormatFiles-c.Dat`, which contains the following records.</span></span> <span data-ttu-id="2c0df-128">Pour créer le fichier de données, à l'invite de commandes [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, entrez :</span><span class="sxs-lookup"><span data-stu-id="2c0df-128">To create the data file, at the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows command prompt, enter:</span></span>  
  
```  
10,Field2,Field3,Field4  
15,Field2,Field3,Field4  
46,Field2,Field3,Field4  
58,Field2,Field3,Field4  
```  
  
### <a name="sample-format-files"></a><span data-ttu-id="2c0df-129">Exemple de fichiers de format</span><span class="sxs-lookup"><span data-stu-id="2c0df-129">Sample Format Files</span></span>  
 <span data-ttu-id="2c0df-130">Certains exemples de cette section utilisent un fichier de format XML, `myTestFormatFiles-f-x-c.Xml`, d'autres exemples un fichier de format non XML.</span><span class="sxs-lookup"><span data-stu-id="2c0df-130">Some of the examples in this section use an XML format file, `myTestFormatFiles-f-x-c.Xml`, and other examples use a non-XML format file.</span></span> <span data-ttu-id="2c0df-131">Ces deux types de fichiers utilisent des formats de données de type caractère et une marque de fin de champ non définie par défaut (,).</span><span class="sxs-lookup"><span data-stu-id="2c0df-131">Both format files use character data formats and a non-default field terminator (,).</span></span>  
  
#### <a name="the-sample-non-xml-format-file"></a><span data-ttu-id="2c0df-132">Exemple de fichier de format non XML</span><span class="sxs-lookup"><span data-stu-id="2c0df-132">The Sample Non-XML Format File</span></span>  
 <span data-ttu-id="2c0df-133">L’exemple suivant a recours à la commande **bcp** pour générer un fichier de format XML à partir de la table `myTestFormatFiles` .</span><span class="sxs-lookup"><span data-stu-id="2c0df-133">The following example uses **bcp** to generate an XML format file from the `myTestFormatFiles` table.</span></span> <span data-ttu-id="2c0df-134">Le fichier `myTestFormatFiles.Fmt` contient les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="2c0df-134">The `myTestFormatFiles.Fmt` file contains the following information:</span></span>  
  
```  
9.0  
4  
1       SQLCHAR       0       7       ","      1     Col1         ""  
2       SQLCHAR       0       100     ","      2     Col2         SQL_Latin1_General_CP1_CI_AS  
3       SQLCHAR       0       100     ","      3     Col3         SQL_Latin1_General_CP1_CI_AS  
4       SQLCHAR       0       100     "\r\n"   4     Col4         SQL_Latin1_General_CP1_CI_AS  
```  
  
 <span data-ttu-id="2c0df-135">Pour utiliser la commande **bcp** avec l’option **format** pour créer ce fichier de format, dans l’invite de commandes Windows, tapez :</span><span class="sxs-lookup"><span data-stu-id="2c0df-135">To use **bcp** with the **format** option to create this format file, at the Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks2012..MyTestFormatFiles format nul -c -t, -f myTestFormatFiles.Fmt -T  
  
```  
  
 <span data-ttu-id="2c0df-136">Pour plus d’informations sur la création d’un fichier de format, consultez [Créer un fichier de format &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="2c0df-136">For more information about creating a format file, see [Create a Format File &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span></span>  
  
#### <a name="the-sample-xml-format-file"></a><span data-ttu-id="2c0df-137">Exemple de fichier de format XML</span><span class="sxs-lookup"><span data-stu-id="2c0df-137">The Sample XML Format File</span></span>  
 <span data-ttu-id="2c0df-138">L’exemple suivant a recours à la commande **bcp** pour générer un fichier de format XML à partir de la table `myTestFormatFiles` .</span><span class="sxs-lookup"><span data-stu-id="2c0df-138">The following example uses **bcp** to create to generate an XML format file from the `myTestFormatFiles` table.</span></span> <span data-ttu-id="2c0df-139">Le fichier `myTestFormatFiles.Xml` contient les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="2c0df-139">The `myTestFormatFiles.Xml` file contains the following information:</span></span>  
  
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
  <COLUMN SOURCE="1" NAME="Col1" xsi:type="SQLSMALLINT"/>  
  <COLUMN SOURCE="2" NAME="Col2" xsi:type="SQLNVARCHAR"/>  
  <COLUMN SOURCE="3" NAME="Col3" xsi:type="SQLNVARCHAR"/>  
  <COLUMN SOURCE="4" NAME="Col4" xsi:type="SQLNVARCHAR"/>  
 </ROW>  
</BCPFORMAT>  
```  
  
 <span data-ttu-id="2c0df-140">Pour utiliser la commande **bcp** avec l’option **format** pour créer ce fichier de format, dans l’invite de commandes Windows, tapez :</span><span class="sxs-lookup"><span data-stu-id="2c0df-140">To use **bcp** with the **format** option to create this format file, at the Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks2012..MyTestFormatFiles format nul -c -t, -x -f myTestFormatFiles.Xml -T  
```  
  
### <a name="using-bcp"></a><span data-ttu-id="2c0df-141">Utilisation de la commande bcp</span><span class="sxs-lookup"><span data-stu-id="2c0df-141">Using bcp</span></span>  
 <span data-ttu-id="2c0df-142">L’exemple suivant a recours à la commande **bcp** pour importer des données en bloc à partir du fichier de données `myTestFormatFiles-c.Dat` dans la table `HumanResources.myTestFormatFiles` de l’exemple de base de données.</span><span class="sxs-lookup"><span data-stu-id="2c0df-142">The following example uses **bcp** to bulk import data from the `myTestFormatFiles-c.Dat` data file into `HumanResources.myTestFormatFiles` table in the  sample database.</span></span> <span data-ttu-id="2c0df-143">Cet exemple utilise le fichier de format XML `MyTestFormatFiles.Xml`.</span><span class="sxs-lookup"><span data-stu-id="2c0df-143">This example uses an XML format file, `MyTestFormatFiles.Xml`.</span></span> <span data-ttu-id="2c0df-144">Il supprime toutes les lignes existantes de la table avant d'importer le fichier de données.</span><span class="sxs-lookup"><span data-stu-id="2c0df-144">The example deletes any existing table rows before importing the data file.</span></span>  
  
 <span data-ttu-id="2c0df-145">À l'invite de commandes Windows, entrez :</span><span class="sxs-lookup"><span data-stu-id="2c0df-145">At the Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks2012..myTestFormatFiles in C:\myTestFormatFiles-c.Dat -f C:\myTestFormatFiles.Xml -T  
```  
  
> [!NOTE]  
>  <span data-ttu-id="2c0df-146">Pour plus d’informations sur cette commande, consultez [Utilitaire bcp](../../tools/bcp-utility.md).</span><span class="sxs-lookup"><span data-stu-id="2c0df-146">For more information about this command, see [bcp Utility](../../tools/bcp-utility.md).</span></span>  
  
### <a name="using-bulk-insert"></a><span data-ttu-id="2c0df-147">Utilisation de BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="2c0df-147">Using BULK INSERT</span></span>  
 <span data-ttu-id="2c0df-148">Dans l'exemple suivant, l'instruction BULK INSERT est utilisée pour importer des données en bloc à partir du fichier de données `myTestFormatFiles-c.Dat` dans la table `HumanResources.myTestFormatFiles` dans l'exemple de base de données [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2c0df-148">The following example uses BULK INSERT to bulk import data from the `myTestFormatFiles-c.Dat` data file into `HumanResources.myTestFormatFiles` table in the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] sample database.</span></span> <span data-ttu-id="2c0df-149">Cet exemple utilise le fichier de format non XML `MyTestFormatFiles.Fmt`.</span><span class="sxs-lookup"><span data-stu-id="2c0df-149">This example uses a non-XML format file, `MyTestFormatFiles.Fmt`.</span></span> <span data-ttu-id="2c0df-150">Il supprime toutes les lignes existantes de la table avant d'importer le fichier de données.</span><span class="sxs-lookup"><span data-stu-id="2c0df-150">The example deletes any existing table rows before importing the data file.</span></span>  
  
 <span data-ttu-id="2c0df-151">Dans l'Éditeur de requête [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], exécutez :</span><span class="sxs-lookup"><span data-stu-id="2c0df-151">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
DELETE myTestFormatFiles;  
GO  
BULK INSERT myTestFormatFiles   
   FROM 'C:\myTestFormatFiles-c.Dat'   
   WITH (FORMATFILE = 'C:\myTestFormatFiles.Fmt');  
GO  
SELECT * FROM myTestFormatFiles;  
GO  
```  
  
> [!NOTE]  
>  <span data-ttu-id="2c0df-152">Pour plus d’informations sur cette instruction, consultez [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2c0df-152">For more information about this statement, see [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql).</span></span>  
  
### <a name="using-the-openrowset-bulk-rowset-provider"></a><span data-ttu-id="2c0df-153">Utilisation du fournisseur d'ensembles de lignes en bloc OPENROWSET</span><span class="sxs-lookup"><span data-stu-id="2c0df-153">Using the OPENROWSET Bulk Rowset Provider</span></span>  
 <span data-ttu-id="2c0df-154">Dans l'exemple suivant, la commande `INSERT ... SELECT * FROM OPENROWSET(BULK...)` est utilisée pour importer des données en bloc à partir du fichier de données `myTestFormatFiles-c.Dat` dans la table `HumanResources.myTestFormatFiles` dans l'exemple de base de données `AdventureWorks`.</span><span class="sxs-lookup"><span data-stu-id="2c0df-154">The following example uses `INSERT ... SELECT * FROM OPENROWSET(BULK...)` to bulk import data from the `myTestFormatFiles-c.Dat` data file into `HumanResources.myTestFormatFiles` table in the `AdventureWorks` sample database.</span></span> <span data-ttu-id="2c0df-155">Cet exemple utilise le fichier de format XML `MyTestFormatFiles.Xml`.</span><span class="sxs-lookup"><span data-stu-id="2c0df-155">This example uses an XML format file, `MyTestFormatFiles.Xml`.</span></span> <span data-ttu-id="2c0df-156">Il supprime toutes les lignes existantes de la table avant d'importer le fichier de données.</span><span class="sxs-lookup"><span data-stu-id="2c0df-156">The example deletes any existing table rows before importing the data file.</span></span>  
  
 <span data-ttu-id="2c0df-157">Dans l'Éditeur de requête [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], exécutez :</span><span class="sxs-lookup"><span data-stu-id="2c0df-157">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks2012;  
DELETE myTestFormatFiles;  
GO  
INSERT INTO myTestFormatFiles  
    SELECT *  
      FROM  OPENROWSET(BULK  'C:\myTestFormatFiles-c.Dat',  
      FORMATFILE='C:\myTestFormatFiles.Xml'       
      ) as t1 ;  
GO  
SELECT * FROM myTestFormatFiles;  
GO  
```  
  
 <span data-ttu-id="2c0df-158">Lorsque vous avez terminé d'utiliser la table d'exemple, vous pouvez la supprimer au moyen de l'instruction suivante :</span><span class="sxs-lookup"><span data-stu-id="2c0df-158">When you finish using the sample table, you can drop it using the following statement:</span></span>  
  
```  
DROP TABLE myTestFormatFiles  
```  
  
> [!NOTE]  
>  <span data-ttu-id="2c0df-159">Pour plus d’informations sur la clause OPENROWSET BULK, consultez [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2c0df-159">For more information about the OPENROWSET BULK clause, see [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span></span>  
  
## <a name="additional-examples"></a><span data-ttu-id="2c0df-160">Autres exemples</span><span class="sxs-lookup"><span data-stu-id="2c0df-160">Additional Examples</span></span>  
 [<span data-ttu-id="2c0df-161">Créer un fichier de format &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2c0df-161">Create a Format File &#40;SQL Server&#41;</span></span>](create-a-format-file-sql-server.md)  
  
 [<span data-ttu-id="2c0df-162">Utiliser un fichier de format pour ignorer une colonne de table &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2c0df-162">Use a Format File to Skip a Table Column &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-table-column-sql-server.md)  
  
 [<span data-ttu-id="2c0df-163">Utiliser un fichier de format pour ignorer un champ de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2c0df-163">Use a Format File to Skip a Data Field &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-data-field-sql-server.md)  
  
 [<span data-ttu-id="2c0df-164">Utiliser un fichier de format pour mapper les colonnes d’une table sur les champs d’un fichier de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2c0df-164">Use a Format File to Map Table Columns to Data-File Fields &#40;SQL Server&#41;</span></span>](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="2c0df-165">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2c0df-165">See Also</span></span>  
 <span data-ttu-id="2c0df-166">[Utilitaire bcp](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="2c0df-166">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="2c0df-167">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2c0df-167">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 <span data-ttu-id="2c0df-168">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2c0df-168">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 <span data-ttu-id="2c0df-169">[Fichiers de format non-XML &#40;SQL Server&#41;](xml-format-files-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2c0df-169">[Non-XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md) </span></span>  
 [<span data-ttu-id="2c0df-170">Fichiers de format XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2c0df-170">XML Format Files &#40;SQL Server&#41;</span></span>](xml-format-files-sql-server.md)  
  
  
