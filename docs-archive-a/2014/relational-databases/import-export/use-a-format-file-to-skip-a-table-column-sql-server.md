---
title: Utiliser un fichier de format pour ignorer une colonne de table (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- skipping columns when importing
- format files [SQL Server], skipping columns
ms.assetid: 30e0e7b9-d131-46c7-90a4-6ccf77e3d4f3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 153ef21209ff4261020e26aca3bc52d28dc852a7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615143"
---
# <a name="use-a-format-file-to-skip-a-table-column-sql-server"></a><span data-ttu-id="481cb-102">Utiliser un fichier de format pour ignorer une colonne de table (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="481cb-102">Use a Format File to Skip a Table Column (SQL Server)</span></span>
  <span data-ttu-id="481cb-103">Cette rubrique décrit les fichiers de format.</span><span class="sxs-lookup"><span data-stu-id="481cb-103">This topic describes format files.</span></span> <span data-ttu-id="481cb-104">Vous pouvez utiliser un fichier de format pour ignorer l'importation d'une colonne de table lorsque le champ n'existe pas dans le fichier de données.</span><span class="sxs-lookup"><span data-stu-id="481cb-104">You can use a format file to skip importing a table column when the field does not exist in the data file.</span></span> <span data-ttu-id="481cb-105">Un fichier de données peut contenir moins de champs qu'il n'y a de colonnes dans la table uniquement si les colonnes ignorées peuvent être NULL et/ou avoir une valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="481cb-105">A data file can contain fewer fields than the number of columns in the table only if the skipped columns are nullable and/or have default value.</span></span>

## <a name="sample-table-and-data-file"></a><span data-ttu-id="481cb-106">Exemples de table et de fichier de données</span><span class="sxs-lookup"><span data-stu-id="481cb-106">Sample Table and Data File</span></span>
 <span data-ttu-id="481cb-107">Les exemples suivants nécessitent une table nommée `myTestSkipCol` dans la base de données exemple [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] sous le schéma **dbo** .</span><span class="sxs-lookup"><span data-stu-id="481cb-107">The following examples require a table named `myTestSkipCol` in the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] sample database under the **dbo** schema.</span></span> <span data-ttu-id="481cb-108">Créez cette table comme suit :</span><span class="sxs-lookup"><span data-stu-id="481cb-108">Create this table as follows:</span></span>

```
USE AdventureWorks2012;
GO
CREATE TABLE myTestSkipCol 
   (
   Col1 smallint,
   Col2 nvarchar(50) NULL,
   Col3 nvarchar(50) not NULL
   );
GO
```

 <span data-ttu-id="481cb-109">Les exemples suivants utilisent un fichier de données d'exemple, `myTestSkipCol2.dat`, doté uniquement de deux champs alors que la table correspondante contient trois colonnes :</span><span class="sxs-lookup"><span data-stu-id="481cb-109">The following examples use a sample data file, `myTestSkipCol2.dat`, which contains only two fields, although the corresponding table contains three columns:</span></span>

```
1,DataForColumn3
1,DataForColumn3
1,DataForColumn3

```

 <span data-ttu-id="481cb-110">Pour importer des données en bloc depuis `myTestSkipCol2.dat` dans la table `myTestSkipCol` , le fichier de format doit mapper le premier champ de données à `Col1`, le deuxième champ à `Col3`, en ignorant `Col2`.</span><span class="sxs-lookup"><span data-stu-id="481cb-110">To bulk import data from `myTestSkipCol2.dat` into the `myTestSkipCol` table, the format file must map the first data field to `Col1`, the second field to `Col3`, skipping `Col2`.</span></span>

## <a name="using-a-non-xml-format-file"></a><span data-ttu-id="481cb-111">Utilisation d'un fichier de format non-XML</span><span class="sxs-lookup"><span data-stu-id="481cb-111">Using a Non-XML Format File</span></span>
 <span data-ttu-id="481cb-112">Vous pouvez modifier un fichier de format non XML pour ignorer une colonne de table.</span><span class="sxs-lookup"><span data-stu-id="481cb-112">You can modify a non-XML format file to skip a table column.</span></span> <span data-ttu-id="481cb-113">En règle générale, cette opération consiste à faire appel à l’utilitaire **bcp** pour créer un fichier de format non-XML par défaut et à modifier le fichier par défaut dans un éditeur de texte.</span><span class="sxs-lookup"><span data-stu-id="481cb-113">Typically, this involves using the **bcp** utility to create a default non-XML format file and the modifying the default file in a text editor.</span></span> <span data-ttu-id="481cb-114">Le fichier de format modifié doit mapper chaque champ existant à une colonne de table correspondante et indiquer quelle(s) colonne(s) de table ignorer.</span><span class="sxs-lookup"><span data-stu-id="481cb-114">The modified format file must map each existing fields to its corresponding table column and indicate which table column or columns to skip.</span></span> <span data-ttu-id="481cb-115">Il existe deux alternatives pour modifier un fichier de données non XML par défaut.</span><span class="sxs-lookup"><span data-stu-id="481cb-115">Two alternatives exist for modifying a default non-XML data file.</span></span> <span data-ttu-id="481cb-116">Quoi qu'il en soit, elles indiquent toutes deux que le champ de données n'existe pas dans le fichier de données et qu'aucune donnée ne sera insérée dans la colonne correspondante de la table.</span><span class="sxs-lookup"><span data-stu-id="481cb-116">Either alternative indicates that the data field does not exist in the data file and that no data will be inserted into the corresponding table column.</span></span>

### <a name="creating-a-default-non-xml-format-file"></a><span data-ttu-id="481cb-117">Création d'un fichier de format non XML par défaut</span><span class="sxs-lookup"><span data-stu-id="481cb-117">Creating a Default Non-XML Format File</span></span>
 <span data-ttu-id="481cb-118">Cette rubrique utilise le fichier de format non-XML par défaut créé pour l’exemple de table `myTestSkipCol` en faisant appel à la commande **bcp** suivante :</span><span class="sxs-lookup"><span data-stu-id="481cb-118">This topic uses the default non-XML format file that was created for the `myTestSkipCol` sample table by using the following **bcp** command:</span></span>

```
bcp AdventureWorks2012..myTestSkipCol format nul -f myTestSkipCol_Default.fmt -c -T
```

 <span data-ttu-id="481cb-119">La commande précédente crée un fichier de format non XML, `myTestSkipCol_Default.fmt`.</span><span class="sxs-lookup"><span data-stu-id="481cb-119">The previous command creates a non-XML format file, `myTestSkipCol_Default.fmt`.</span></span> <span data-ttu-id="481cb-120">Ce fichier de format s’appelle un *fichier de format par défaut* car il est au format généré par **bcp**.</span><span class="sxs-lookup"><span data-stu-id="481cb-120">This format file is called a *default format file* because it is the form generated by **bcp**.</span></span> <span data-ttu-id="481cb-121">Généralement, un fichier de format par défaut décrit une correspondance unique entre les champs données-fichier et les colonnes de table.</span><span class="sxs-lookup"><span data-stu-id="481cb-121">Typically, a default format file describes a one-to-one correspondence between data-file fields and table columns.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="481cb-122">Vous devrez peut-être spécifier le nom de l'instance de serveur à laquelle vous vous connectez.</span><span class="sxs-lookup"><span data-stu-id="481cb-122">You might have to specify the name of the server instance to which you are connecting.</span></span> <span data-ttu-id="481cb-123">Vous devrez aussi peut-être spécifier le nom d'utilisateur et le mot de passe.</span><span class="sxs-lookup"><span data-stu-id="481cb-123">Also, you might have to specify the user name and password.</span></span> <span data-ttu-id="481cb-124">Pour plus d’informations, consultez [bcp Utility](../../tools/bcp-utility.md).</span><span class="sxs-lookup"><span data-stu-id="481cb-124">For more information, see [bcp Utility](../../tools/bcp-utility.md).</span></span>

 <span data-ttu-id="481cb-125">L'illustration suivante montre les valeurs dans les exemples de fichier de format par défaut.</span><span class="sxs-lookup"><span data-stu-id="481cb-125">The following illustration shows the values in this sample default format files.</span></span> <span data-ttu-id="481cb-126">L'illustration montre également le nom de chaque champ fichier-format.</span><span class="sxs-lookup"><span data-stu-id="481cb-126">The illustration also shows the name of each format-file field.</span></span>

 <span data-ttu-id="481cb-127">![fichier de format non-XML par défaut pour myTestSkipCol](../../database-engine/media/mytestskipcol-f-c-default-fmt.gif "fichier de format non-XML par défaut pour myTestSkipCol")</span><span class="sxs-lookup"><span data-stu-id="481cb-127">![default non-XML format file for myTestSkipCol](../../database-engine/media/mytestskipcol-f-c-default-fmt.gif "default non-XML format file for myTestSkipCol")</span></span>

> [!NOTE]
>  <span data-ttu-id="481cb-128">Pour plus d’informations sur les champs de fichier de format, consultez [Fichiers de format non-XML &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="481cb-128">For more information about the format-file fields, see [Non-XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>

### <a name="methods-for-modifying-a-non-xml-format-file"></a><span data-ttu-id="481cb-129">Méthodes de modification d'un fichier de format non XML</span><span class="sxs-lookup"><span data-stu-id="481cb-129">Methods for Modifying a Non-XML Format File</span></span>
 <span data-ttu-id="481cb-130">Pour ignorer une colonne de table, modifiez le fichier de format non XML par défaut et modifiez-le à l'aide de l'une des méthodes alternatives suivantes :</span><span class="sxs-lookup"><span data-stu-id="481cb-130">To skip a table column, edit the default non-XML format file and modify the file by using one of the following alternative methods:</span></span>

-   <span data-ttu-id="481cb-131">La méthode recommandée consiste en une procédure de trois étapes.</span><span class="sxs-lookup"><span data-stu-id="481cb-131">The preferred method involves three basic steps.</span></span> <span data-ttu-id="481cb-132">Commencez par supprimer les lignes de fichier-format qui correspondent à un champ manquant dans le fichier de données.</span><span class="sxs-lookup"><span data-stu-id="481cb-132">First, delete any format-file row that describes a field that is missing from the data file.</span></span> <span data-ttu-id="481cb-133">Puis, réduisez la valeur « Ordre des champs du fichier hôte » de chaque ligne de fichier-format qui suit une ligne supprimée.</span><span class="sxs-lookup"><span data-stu-id="481cb-133">Then, reduce the "Host file field order" value of each format-file row that follows a deleted row.</span></span> <span data-ttu-id="481cb-134">L'objectif est les valeurs « Ordre des champs du fichier hôte » séquentielles, 1 à *n*, qui reflète la position réelle de chaque champ de données dans le fichier de données.</span><span class="sxs-lookup"><span data-stu-id="481cb-134">The goal is sequential "Host file field order" values, 1 through *n*, that reflect the actual position of each data field in the data file.</span></span> <span data-ttu-id="481cb-135">Enfin, réduisez la valeur du champ « Nombre de colonnes » pour refléter le nombre réel de champs figurant dans le fichier de données.</span><span class="sxs-lookup"><span data-stu-id="481cb-135">Finally, reduce the value in the "Number of columns" field to reflect the actual number of fields in the data file.</span></span>

     <span data-ttu-id="481cb-136">L'exemple suivant est basé sur le fichier de format par défaut pour la table `myTestSkipCol` et créé dans la section « Création d'un fichier de format non XML par défaut », plus haut dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="481cb-136">The following example is based on the default format file for the `myTestSkipCol` table, which is created in "Creating a Default Non-XML Format File," earlier in this topic.</span></span> <span data-ttu-id="481cb-137">Ce fichier de format modifié mappe le premier champ de données à `Col1`, ignore `Col2`, et mappe le deuxième champ de données à `Col3`.</span><span class="sxs-lookup"><span data-stu-id="481cb-137">This modified format file maps the first data field to `Col1`, skips `Col2`, and maps the second data field to `Col3`.</span></span> <span data-ttu-id="481cb-138">La ligne de `Col2` a été supprimée.</span><span class="sxs-lookup"><span data-stu-id="481cb-138">The row for `Col2` has been deleted.</span></span> <span data-ttu-id="481cb-139">Les autres modifications apparaissent en gras :</span><span class="sxs-lookup"><span data-stu-id="481cb-139">Other modifications are indicated in bold:</span></span>

    ```
    9.0
    2
    1       SQLCHAR       0       7       "\t"     1     Col1         ""
    2       SQLCHAR       0       100     "\r\n"   3     Col3         SQL_Latin1_General_CP1_CI_AS
    ```

-   <span data-ttu-id="481cb-140">Pour ignorer une colonne de table, vous pouvez aussi modifier la définition de la ligne du fichier-format qui correspond à la colonne de table.</span><span class="sxs-lookup"><span data-stu-id="481cb-140">Alternatively, to skip a table column, you can modify the definition of the format-file row that corresponds to the table column.</span></span> <span data-ttu-id="481cb-141">Dans cette ligne de fichier-format, les valeurs « longueur de préfixe », « longueur des données du fichier hôte » et « ordre des colonnes du serveur » doivent être égales à 0.</span><span class="sxs-lookup"><span data-stu-id="481cb-141">In this format-file row, the "prefix length," "host file data length," and "server column order" values must be set to 0.</span></span> <span data-ttu-id="481cb-142">De plus, les champs « terminateur » et « classement des colonnes » doivent avoir la valeur "" (NULL).</span><span class="sxs-lookup"><span data-stu-id="481cb-142">Also, the "terminator" and "column collation" fields must be set to "" (NULL).</span></span>

     <span data-ttu-id="481cb-143">La valeur « nom de la colonne du serveur » nécessite une chaîne non vide même si le nom de la colonne à proprement dit n'est pas nécessaire</span><span class="sxs-lookup"><span data-stu-id="481cb-143">The "server column name" value requires a nonblank string, though the actual column name is not necessary.</span></span> <span data-ttu-id="481cb-144">Les champs de format restants nécessitent leurs valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="481cb-144">The remaining format fields require their default values.</span></span>

     <span data-ttu-id="481cb-145">L'exemple suivant provient aussi du fichier de format par défaut pour la table `myTestSkipCol` .</span><span class="sxs-lookup"><span data-stu-id="481cb-145">The following example is also derived from the default format file for the `myTestSkipCol` table.</span></span> <span data-ttu-id="481cb-146">Les valeurs qui doivent être 0 ou NULL sont en gras.</span><span class="sxs-lookup"><span data-stu-id="481cb-146">Values that must be 0 or NULL are indicated in bold.</span></span>

    ```
    9.0
    3
    1       SQLCHAR       0       7       "\t"     1     Col1         ""
    2       SQLCHAR       00""0     Col2         ""
    3       SQLCHAR       0       100     "\r\n"   3     Col3         SQL_Latin1_General_CP1_CI_AS
    ```

### <a name="examples"></a><span data-ttu-id="481cb-147">Exemples</span><span class="sxs-lookup"><span data-stu-id="481cb-147">Examples</span></span>
 <span data-ttu-id="481cb-148">Les exemples suivants sont aussi basés sur l'exemple de table `myTestSkipCol` et l'exemple de fichier de données `myTestSkipCol2.dat` créés dans la section « Exemple de table et de fichier de données », plus haut dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="481cb-148">The following examples are also based on the `myTestSkipCol` sample table and the `myTestSkipCol2.dat` sample data file that are created in "Sample Table and Data File," earlier in this topic.</span></span>

#### <a name="using-bulk-insert"></a><span data-ttu-id="481cb-149">Utilisation de BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="481cb-149">Using BULK INSERT</span></span>
 <span data-ttu-id="481cb-150">Cet exemple décrit l'utilisation de l'un ou l'autre des fichiers de format non XML modifiés et créés dans la section « Méthodes de modification d'un fichier de format non XML », plus haut dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="481cb-150">This example works by using either of the modified non-XML format files created in "Methods for Modifying a Non-XML Format File," earlier in this topic.</span></span> <span data-ttu-id="481cb-151">Dans cet exemple, le fichier de format modifié est intitulé `C:\myTestSkipCol2.fmt`.</span><span class="sxs-lookup"><span data-stu-id="481cb-151">In this example, the modified format file is named `C:\myTestSkipCol2.fmt`.</span></span> <span data-ttu-id="481cb-152">Pour utiliser `BULK INSERT` afin d'importer en bloc le fichier de données `myTestSkipCol2.dat` , exécutez le code suivant dans l'éditeur de requête [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="481cb-152">To use `BULK INSERT` to bulk import the `myTestSkipCol2.dat` data file, in the [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute the following code:</span></span>

```
USE AdventureWorks2012;
GO
BULK INSERT myTestSkipCol 
   FROM 'C:\myTestSkipCol2.dat' 
   WITH (FORMATFILE = 'C:\myTestSkipCol2.fmt');
GO
SELECT * FROM myTestSkipCol;
GO
```

## <a name="using-an-xml-format-file"></a><span data-ttu-id="481cb-153">Utilisation d'un fichier de format XML</span><span class="sxs-lookup"><span data-stu-id="481cb-153">Using an XML Format File</span></span>
 <span data-ttu-id="481cb-154">Avec un fichier de format XML, vous ne pouvez pas ignorer une colonne lorsque vous procédez à une importation directement dans une table à l’aide d’une commande **bcp** ou d’une instruction BULK INSERT.</span><span class="sxs-lookup"><span data-stu-id="481cb-154">With an XML format file, you cannot skip a column when you are importing directly into a table by using a **bcp** command or a BULK INSERT statement.</span></span> <span data-ttu-id="481cb-155">Néanmoins, vous pouvez importer toutes les colonnes d'une table hormis la dernière.</span><span class="sxs-lookup"><span data-stu-id="481cb-155">However, you can import into all but the last column of a table.</span></span> <span data-ttu-id="481cb-156">Pour ignorer toutes les colonnes à l'exception de la dernière, vous devez créer une vue de la table cible contenant uniquement les colonnes figurant dans le fichier de données.</span><span class="sxs-lookup"><span data-stu-id="481cb-156">If you have to skip any but the last column, you must create a view of the target table that contains only the columns contained in the data file.</span></span> <span data-ttu-id="481cb-157">Vous pouvez ensuite importer en bloc les données de ce fichier dans la vue.</span><span class="sxs-lookup"><span data-stu-id="481cb-157">Then, you can bulk import data from that file into the view.</span></span>

 <span data-ttu-id="481cb-158">Pour utiliser un fichier de format XML afin d'ignorer une colonne de table à l'aide de OPENROWSET(BULK...), vous devez fournir une liste explicite des colonnes dans la liste de sélection mais aussi dans la table cible, comme ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="481cb-158">To use an XML format file to skip a table column by using OPENROWSET(BULK...), you have to provide explicit list of columns in the select list and also in the target table, as follows:</span></span>

 <span data-ttu-id="481cb-159">INSERT ...<column_list> SELECT <column_list> FROM OPENROWSET(BULK...)</span><span class="sxs-lookup"><span data-stu-id="481cb-159">INSERT ...<column_list> SELECT <column_list> FROM OPENROWSET(BULK...)</span></span>

### <a name="creating-a-default-xml-format-file"></a><span data-ttu-id="481cb-160">Création d'un fichier de format XML par défaut</span><span class="sxs-lookup"><span data-stu-id="481cb-160">Creating a Default XML Format File</span></span>
 <span data-ttu-id="481cb-161">Les exemples de fichiers de format modifiés sont basés sur l'exemple de table `myTestSkipCol` et de fichier de données créés dans la section « Exemple de table et de fichier de données », plus haut dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="481cb-161">The examples of modified format files are based on the `myTestSkipCol` sample table and data file that are created in "Sample Table and Data File," earlier in this topic.</span></span> <span data-ttu-id="481cb-162">La commande **bcp** suivante crée un fichier de format XML par défaut pour la table `myTestSkipCol` :</span><span class="sxs-lookup"><span data-stu-id="481cb-162">The following **bcp** command creates a default XML format file for the `myTestSkipCol` table:</span></span>

```
bcp AdventureWorks2012..myTestSkipCol format nul -f myTestSkipCol_Default.xml -c -x -T
```

 <span data-ttu-id="481cb-163">Le fichier de format non XML par défaut résultant décrit une correspondance unique entre les champs données-fichier et les colonnes de table de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="481cb-163">The resulting default non-XML format file describes a one-to-one correspondence between data-file fields and table columns, as follows:</span></span>

```
<?xml version="1.0"?>
<BCPFORMAT xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
 <RECORD>
  <FIELD ID="1" xsi:type="CharTerm" TERMINATOR="\t" MAX_LENGTH="7"/>
  <FIELD ID="2" xsi:type="CharTerm" TERMINATOR="\t" MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>
  <FIELD ID="3" xsi:type="CharTerm" TERMINATOR="\r\n" MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>
 </RECORD>
 <ROW>
  <COLUMN SOURCE="1" NAME="Col1" xsi:type="SQLSMALLINT"/>
  <COLUMN SOURCE="2" NAME="Col2" xsi:type="SQLNVARCHAR"/>
  <COLUMN SOURCE="3" NAME="Col3" xsi:type="SQLNVARCHAR"/>
 </ROW>
</BCPFORMAT>
```

> [!NOTE]
>  <span data-ttu-id="481cb-164">Pour plus d’informations sur la structure des fichiers de format XML, consultez [Fichiers de format XML &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="481cb-164">For information about the structure of XML format files, see [XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>

### <a name="examples"></a><span data-ttu-id="481cb-165">Exemples</span><span class="sxs-lookup"><span data-stu-id="481cb-165">Examples</span></span>
 <span data-ttu-id="481cb-166">Les exemples de cette section utilisent l'exemple de table `myTestSkipCol` et l'exemple de fichier de données `myTestSkipCol2.dat` de la section « Exemple de table et de fichier de données », plus haut dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="481cb-166">The examples in this section use the `myTestSkipCol` sample table and the `myTestSkipCol2.dat` sample data file that are created in "Sample Table and Data File," earlier in this topic.</span></span> <span data-ttu-id="481cb-167">Pour effectuer l'importation de `myTestSkipCol2.dat` dans la table `myTestSkipCol` , les exemples font appel au fichier de format XML modifié, `myTestSkipCol2-x.xml`.</span><span class="sxs-lookup"><span data-stu-id="481cb-167">To import the data from `myTestSkipCol2.dat` into the `myTestSkipCol` table, the examples use the following modified XML format file, `myTestSkipCol2-x.xml`.</span></span> <span data-ttu-id="481cb-168">Ces exemples sont basés sur le fichier de format créé dans la section « Création d'un fichier de format XML par défaut », plus haut dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="481cb-168">This is based on the format file that is created in "Creating a Default XML Format File," earlier in this topic.</span></span>

```
<?xml version="1.0"?>
<BCPFORMAT xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
 <RECORD>
  <FIELD ID="1" xsi:type="CharTerm" TERMINATOR="," MAX_LENGTH="7"/>
  <FIELD ID="2" xsi:type="CharTerm" TERMINATOR="\r\n" MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>
 </RECORD>
 <ROW>
  <COLUMN SOURCE="1" NAME="Col1" xsi:type="SQLSMALLINT"/>
  <COLUMN SOURCE="2" NAME="Col3" xsi:type="SQLNVARCHAR"/>
 </ROW>
</BCPFORMAT>
```

#### <a name="using-openrowsetbulk"></a><span data-ttu-id="481cb-169">Utilisation de OPENROWSET(BULK...)</span><span class="sxs-lookup"><span data-stu-id="481cb-169">Using OPENROWSET(BULK...)</span></span>
 <span data-ttu-id="481cb-170">L'exemple suivant utilise le fournisseur d'ensembles de lignes en bloc `OPENROWSET` et le fichier de format `myTestSkipCol2.xml` .</span><span class="sxs-lookup"><span data-stu-id="481cb-170">The following example uses the `OPENROWSET` bulk rowset provider and the `myTestSkipCol2.xml` format file.</span></span> <span data-ttu-id="481cb-171">Dans cet exemple, le fichier de données `myTestSkipCol2.dat` est importé en bloc dans la table `myTestSkipCol` .</span><span class="sxs-lookup"><span data-stu-id="481cb-171">The example bulk imports the `myTestSkipCol2.dat` data file into the `myTestSkipCol` table.</span></span> <span data-ttu-id="481cb-172">L'instruction contient une liste explicite des colonnes dans la liste de sélection et aussi dans la table cible.</span><span class="sxs-lookup"><span data-stu-id="481cb-172">The statement contains an explicit list of columns in the select list and also in the target table, as required.</span></span>

 <span data-ttu-id="481cb-173">Dans l'Éditeur de requête [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] , exécutez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="481cb-173">In the [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute the following code:</span></span>

```
USE AdventureWorks2012;
GO
INSERT INTO myTestSkipCol
  (Col1,Col3)
    SELECT Col1,Col3
      FROM  OPENROWSET(BULK  'C:\myTestSkipCol2.Dat',
      FORMATFILE='C:\myTestSkipCol2.Xml'  
       ) as t1 ;
GO
```

#### <a name="using-bulk-import-on-a-view"></a><span data-ttu-id="481cb-174">Utilisation de BULK IMPORT dans une vue</span><span class="sxs-lookup"><span data-stu-id="481cb-174">Using BULK IMPORT on a View</span></span>
 <span data-ttu-id="481cb-175">L'exemple suivant crée la vue `v_myTestSkipCol` dans la table `myTestSkipCol` .</span><span class="sxs-lookup"><span data-stu-id="481cb-175">The following example creates the `v_myTestSkipCol` on the `myTestSkipCol` table.</span></span> <span data-ttu-id="481cb-176">Cette vue ignore la deuxième colonne de la table, `Col2`.</span><span class="sxs-lookup"><span data-stu-id="481cb-176">This view skips the second table column, `Col2`.</span></span> <span data-ttu-id="481cb-177">L'exemple utilise ensuite l'instruction `BULK INSERT` pour importer le fichier de données `myTestSkipCol2.dat` dans cette vue.</span><span class="sxs-lookup"><span data-stu-id="481cb-177">The example then uses `BULK INSERT` to import the `myTestSkipCol2.dat` data file into this view.</span></span>

 <span data-ttu-id="481cb-178">Dans l'Éditeur de requête [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] , exécutez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="481cb-178">In the [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute the following code:</span></span>

```
CREATE VIEW v_myTestSkipCol AS
    SELECT Col1,Col3
    FROM myTestSkipCol;
GO

USE AdventureWorks2012;
GO
BULK INSERT v_myTestSkipCol
FROM 'C:\myTestSkipCol2.dat'
WITH (FORMATFILE='C:\myTestSkipCol2.xml');
GO
```

## <a name="see-also"></a><span data-ttu-id="481cb-179">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="481cb-179">See Also</span></span>
 <span data-ttu-id="481cb-180">[utilitaire bcp](../../tools/bcp-utility.md) [Bulk Insert &#40;transact-sql&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) [Utilisez un fichier de format pour ignorer un champ de données &#40;](use-a-format-file-to-skip-a-data-field-sql-server.md) SQL Server&#41;utilisez un [fichier de format pour mapper des colonnes de table à des champs de fichier de données &#40;](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md) SQL Server&#41;[Utilisez un fichier de format pour importer des données en bloc](use-a-format-file-to-bulk-import-data-sql-server.md) &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="481cb-180">[bcp Utility](../../tools/bcp-utility.md) [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) [Use a Format File to Skip a Data Field &#40;SQL Server&#41;](use-a-format-file-to-skip-a-data-field-sql-server.md) [Use a Format File to Map Table Columns to Data-File Fields &#40;SQL Server&#41;](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md) [Use a Format File to Bulk Import Data &#40;SQL Server&#41;](use-a-format-file-to-bulk-import-data-sql-server.md)</span></span>


