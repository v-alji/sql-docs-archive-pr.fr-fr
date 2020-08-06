---
title: Conserver les valeurs NULL ou utiliser la valeur par défaut lors de l’importation en bloc (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- bulk importing [SQL Server], null values
- bulk importing [SQL Server], default values
- data formats [SQL Server], null values
- bulk rowset providers [SQL Server]
- bcp utility [SQL Server], null values
- BULK INSERT statement
- default values
- OPENROWSET function, bulk importing
- data formats [SQL Server], default values
ms.assetid: 6b91d762-337b-4345-a159-88abb3e64a81
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 856aa12f6ad5e5094324e0df65941bc63d611451
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708412"
---
# <a name="keep-nulls-or-use-default-values-during-bulk-import-sql-server"></a><span data-ttu-id="6d918-102">Conserver les valeurs NULL ou utiliser la valeur par défaut lors de l'importation en bloc (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="6d918-102">Keep Nulls or Use Default Values During Bulk Import (SQL Server)</span></span>
  <span data-ttu-id="6d918-103">Par défaut, quand des données sont importées dans une table, la commande **bcp** et l’instruction BULK INSERT inspectent toutes les valeurs par défaut définies pour les colonnes de la table.</span><span class="sxs-lookup"><span data-stu-id="6d918-103">By default, when data is imported into a table, the **bcp** command and BULK INSERT statement observe any defaults that are defined for the columns in the table.</span></span> <span data-ttu-id="6d918-104">Par exemple, si un fichier de données contient un champ NULL, la valeur par défaut de la colonne est chargée à la place.</span><span class="sxs-lookup"><span data-stu-id="6d918-104">For example, if there is a null field in a data file, the default value for the column is loaded instead.</span></span> <span data-ttu-id="6d918-105">La commande **bcp** et l’instruction BULK INSERT vous permettent de spécifier que les valeurs NULL doivent être conservées.</span><span class="sxs-lookup"><span data-stu-id="6d918-105">The **bcp** command and BULK INSERT statement both allow you to specify that nulls values be retained.</span></span>  
  
 <span data-ttu-id="6d918-106">À l'opposé, une instruction INSERT standard conserve la valeur NULL au lieu d'insérer une valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="6d918-106">In contrast, a regular INSERT statement retains the null value instead of inserting a default value.</span></span> <span data-ttu-id="6d918-107">L'instruction INSERT ... L’instruction SELECT \* FROM OPENROWSET(BULK...) présente le même comportement de base que l’instruction INSERT standard, mais elle prend également en charge un indicateur de table pour l’insertion des valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="6d918-107">The INSERT ... SELECT \* FROM OPENROWSET(BULK...) statement provides the same basic behavior as regular INSERT but additionally supports a table hint for inserting the default values.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6d918-108">Pour obtenir des exemples de fichiers de format qui ignorent une colonne de table, consultez [Utiliser un fichier de format pour ignorer une colonne de table &#40;SQL Server&#41;](use-a-format-file-to-skip-a-table-column-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="6d918-108">For sample format files that skip a table column, see [Use a Format File to Skip a Table Column &#40;SQL Server&#41;](use-a-format-file-to-skip-a-table-column-sql-server.md).</span></span>  
  
## <a name="sample-table-and-data-file"></a><span data-ttu-id="6d918-109">Exemples de table et de fichier de données</span><span class="sxs-lookup"><span data-stu-id="6d918-109">Sample Table and Data File</span></span>  
 <span data-ttu-id="6d918-110">Pour exécuter les exemples proposés dans cette rubrique, vous devez créer un exemple de table et un exemple de fichier de données.</span><span class="sxs-lookup"><span data-stu-id="6d918-110">To run the examples in this topic, you need to create a sample table and data file.</span></span>  
  
### <a name="sample-table"></a><span data-ttu-id="6d918-111">Exemple de table</span><span class="sxs-lookup"><span data-stu-id="6d918-111">Sample Table</span></span>  
 <span data-ttu-id="6d918-112">Les exemples requièrent la création d'une table nommée **MyTestDefaultCol2** dans l'exemple de base de données **AdventureWorks** sous le schéma **dbo** .</span><span class="sxs-lookup"><span data-stu-id="6d918-112">The examples require that a table named **MyTestDefaultCol2** be created in the **AdventureWorks** sample database under the **dbo** schema.</span></span> <span data-ttu-id="6d918-113">Pour créer cette table, dans l' [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] éditeur de requête, exécutez :</span><span class="sxs-lookup"><span data-stu-id="6d918-113">To create this table, in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
CREATE TABLE MyTestDefaultCol2   
(Col1 smallint,  
Col2 nvarchar(50) DEFAULT 'Default value of Col2',  
Col3 nvarchar(50)   
);  
GO  
  
```  
  
 <span data-ttu-id="6d918-114">La deuxième colonne de table, `Col2`, a une valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="6d918-114">Notice that the second table column, `Col2`, has a default value.</span></span>  
  
### <a name="sample-format-file"></a><span data-ttu-id="6d918-115">Fichier de format d'exemple</span><span class="sxs-lookup"><span data-stu-id="6d918-115">Sample Format File</span></span>  
 <span data-ttu-id="6d918-116">Certains des exemples d'importation en bloc utilisent un fichier de format non-XML, `MyTestDefaultCol2-f-c.Fmt`, qui correspond exactement à la table `MyTestDefaultCol2`.</span><span class="sxs-lookup"><span data-stu-id="6d918-116">Some of the bulk-import examples use a non-XML format file, `MyTestDefaultCol2-f-c.Fmt` that corresponds exactly to the `MyTestDefaultCol2` table.</span></span> <span data-ttu-id="6d918-117">Pour créer ce fichier de format, à l'invite de commandes [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, saisissez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="6d918-117">To create this format file, at the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks..MyTestDefaultCol2 format nul -c -f C:\MyTestDefaultCol2-f-c.Fmt -t, -r\n -T  
  
```  
  
 <span data-ttu-id="6d918-118">Pour plus d’informations sur la création de fichiers de format, consultez [Créer un fichier de format &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="6d918-118">For more information about creating format files, see [Create a Format File &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span></span>  
  
### <a name="sample-data-file"></a><span data-ttu-id="6d918-119">Fichier de données d'exemple</span><span class="sxs-lookup"><span data-stu-id="6d918-119">Sample Data File</span></span>  
 <span data-ttu-id="6d918-120">L'exemple utilise un fichier de données, `MyTestEmptyField2-c.Dat`, dont le deuxième champ ne contient aucune valeur.</span><span class="sxs-lookup"><span data-stu-id="6d918-120">The example uses a sample data file, `MyTestEmptyField2-c.Dat`, that contains no values in the second field.</span></span> <span data-ttu-id="6d918-121">Le fichier de données `MyTestEmptyField2-c.Dat` contient les enregistrements suivants.</span><span class="sxs-lookup"><span data-stu-id="6d918-121">The `MyTestEmptyField2-c.Dat` data file contains the following records.</span></span>  
  
```  
1,,DataField3  
2,,DataField3  
  
```  
  
## <a name="keeping-null-values-with-bcp-or-bulk-insert"></a><span data-ttu-id="6d918-122">Conservation des valeurs NULL à l'aide de la commande bcp ou de l'instruction BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="6d918-122">Keeping Null Values with bcp or BULK INSERT</span></span>  
 <span data-ttu-id="6d918-123">Les qualificateurs suivants spécifient qu'un champ vide du fichier de données conserve sa valeur NULL lors de l'importation en bloc, au lieu d'hériter d'une valeur par défaut (s'il y en a une) pour les colonnes de table.</span><span class="sxs-lookup"><span data-stu-id="6d918-123">The following qualifiers specify that an empty field in the data file retains its null value during the bulk-import operation, rather than inheriting a default value (if any) for the table columns.</span></span>  
  
|<span data-ttu-id="6d918-124">Commande</span><span class="sxs-lookup"><span data-stu-id="6d918-124">Command</span></span>|<span data-ttu-id="6d918-125">Qualificateur</span><span class="sxs-lookup"><span data-stu-id="6d918-125">Qualifier</span></span>|<span data-ttu-id="6d918-126">Type de qualificateur</span><span class="sxs-lookup"><span data-stu-id="6d918-126">Qualifier type</span></span>|  
|-------------|---------------|--------------------|  
|<span data-ttu-id="6d918-127">**bcp**</span><span class="sxs-lookup"><span data-stu-id="6d918-127">**bcp**</span></span>|`-k`|<span data-ttu-id="6d918-128">Commutateur</span><span class="sxs-lookup"><span data-stu-id="6d918-128">Switch</span></span>|  
|<span data-ttu-id="6d918-129">BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="6d918-129">BULK INSERT</span></span>|<span data-ttu-id="6d918-130">KEEPNULLS<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="6d918-130">KEEPNULLS<sup>1</sup></span></span>|<span data-ttu-id="6d918-131">Argument</span><span class="sxs-lookup"><span data-stu-id="6d918-131">Argument</span></span>|  
  
 <span data-ttu-id="6d918-132"><sup>1</sup> pour Bulk Insert, si les valeurs par défaut ne sont pas disponibles, la colonne de table doit être définie de façon à autoriser les valeurs NULL.</span><span class="sxs-lookup"><span data-stu-id="6d918-132"><sup>1</sup> For BULK INSERT, if default values are not available, the table column must be defined to allow null values.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6d918-133">Ces qualificateurs désactivent le contrôle des définitions DEFAULT sur une table par ces commandes d'importation en bloc.</span><span class="sxs-lookup"><span data-stu-id="6d918-133">These qualifiers disable checking of DEFAULT definitions on a table by these bulk-import commands.</span></span> <span data-ttu-id="6d918-134">Toutefois, pour toute instruction INSERT concurrente, des définitions DEFAULT sont attendues.</span><span class="sxs-lookup"><span data-stu-id="6d918-134">However, for any concurrent INSERT statements, DEFAULT definitions are expected.</span></span>  
  
 <span data-ttu-id="6d918-135">Pour plus d’informations, consultez [bcp Utility](../../tools/bcp-utility.md) et [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6d918-135">For more information, see [bcp Utility](../../tools/bcp-utility.md) and [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql).</span></span>  
  
### <a name="examples"></a><span data-ttu-id="6d918-136">Exemples</span><span class="sxs-lookup"><span data-stu-id="6d918-136">Examples</span></span>  
 <span data-ttu-id="6d918-137">Les exemples de cette section réalisent des importations en bloc à l’aide de la commande **bcp** ou de l’instruction BULK INSERT et conservent les valeurs NULL.</span><span class="sxs-lookup"><span data-stu-id="6d918-137">The examples in this section bulk import using **bcp** or BULK INSERT and keep null values.</span></span>  
  
 <span data-ttu-id="6d918-138">La deuxième colonne de la table, **Col2**, a une valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="6d918-138">The second table column, **Col2**, has a default value.</span></span> <span data-ttu-id="6d918-139">Le champ correspondant du fichier de données contient une chaîne vide.</span><span class="sxs-lookup"><span data-stu-id="6d918-139">The corresponding field of the data file contains an empty string.</span></span> <span data-ttu-id="6d918-140">Par défaut, lorsque la commande **bcp** ou l’instruction BULK INSERT est utilisée pour importer des données à partir de ce fichier de données dans la table **MyTestDefaultCol2** , la valeur par défaut de la colonne **Col2** est insérée et le résultat suivant est obtenu :</span><span class="sxs-lookup"><span data-stu-id="6d918-140">By default, when **bcp** or BULK INSERT is used to import data from this data file into the **MyTestDefaultCol2** table, the default value of **Col2** is inserted, producing the following result:</span></span>  
  
||||  
|-|-|-|  
|`1`|`Default value of Col2`|`DataField3`|  
|`2`|`Default value of Col2`|`DataField3`|  
  
 <span data-ttu-id="6d918-141">Pour insérer « `NULL` » à la place de «» `Default value of Col2` , vous devez utiliser l' `-k` option Switch ou KEEPNULL, comme illustré dans les exemples suivants : **BCP** et Bulk Insert.</span><span class="sxs-lookup"><span data-stu-id="6d918-141">To insert "`NULL`" instead of "`Default value of Col2`", you need to use the `-k` switch or KEEPNULL option, as demonstrated in the following **bcp** and BULK INSERT examples.</span></span>  
  
#### <a name="using-bcp-and-keeping-null-values"></a><span data-ttu-id="6d918-142">Utilisation de la commande bcp et conservation des valeurs NULL</span><span class="sxs-lookup"><span data-stu-id="6d918-142">Using bcp and Keeping Null Values</span></span>  
 <span data-ttu-id="6d918-143">L’exemple suivant montre comment conserver les valeurs NULL dans une commande **bcp** .</span><span class="sxs-lookup"><span data-stu-id="6d918-143">The following example demonstrates how to keep null values in a **bcp** command.</span></span> <span data-ttu-id="6d918-144">La commande **BCP** contient les commutateurs suivants :</span><span class="sxs-lookup"><span data-stu-id="6d918-144">The **bcp** command contains the following switches:</span></span>  
  
|<span data-ttu-id="6d918-145">Commutateur</span><span class="sxs-lookup"><span data-stu-id="6d918-145">Switch</span></span>|<span data-ttu-id="6d918-146">Description</span><span class="sxs-lookup"><span data-stu-id="6d918-146">Description</span></span>|  
|------------|-----------------|  
|`-f`|<span data-ttu-id="6d918-147">La commande utilise un fichier de format.</span><span class="sxs-lookup"><span data-stu-id="6d918-147">Specifies that the command is using a format file..</span></span>|  
|`-k`|<span data-ttu-id="6d918-148">Pendant l’opération, les colonnes vides doivent conserver une valeur NULL et les colonnes insérées ne doivent pas prendre de valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="6d918-148">Specifies that empty columns should retain a null value during the operation, rather than have any default values for the columns inserted.</span></span>|  
|`-T`|<span data-ttu-id="6d918-149">L'utilitaire bcp se connecte à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à l'aide d'une connexion approuvée.</span><span class="sxs-lookup"><span data-stu-id="6d918-149">Specifies that the bcp utility connects to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with a trusted connection.</span></span>|  
  
 <span data-ttu-id="6d918-150">À l'invite de commandes Windows, entrez :</span><span class="sxs-lookup"><span data-stu-id="6d918-150">At the Windows command prompt, enter.</span></span>  
  
```  
bcp AdventureWorks..MyTestDefaultCol2 in C:\MyTestEmptyField2-c.Dat -f C:\MyTestDefaultCol2-f-c.Fmt -k -T  
  
```  
  
#### <a name="using-bulk-insert-and-keeping-null-values"></a><span data-ttu-id="6d918-151">Utilisation de l'instruction BULK INSERT et conservation des valeurs NULL</span><span class="sxs-lookup"><span data-stu-id="6d918-151">Using BULK INSERT and Keeping Null Values</span></span>  
 <span data-ttu-id="6d918-152">L'exemple suivant montre comment utiliser l'option KEEPNULLS dans une instruction BULK INSERT.</span><span class="sxs-lookup"><span data-stu-id="6d918-152">The following example demonstrates how to use the KEEPNULLS option in a BULK INSERT statement.</span></span> <span data-ttu-id="6d918-153">À partir d'un outil de requête tel que l'Éditeur de requête [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], exécutez :</span><span class="sxs-lookup"><span data-stu-id="6d918-153">From a query tool, such as [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
BULK INSERT MyTestDefaultCol2  
   FROM 'C:\MyTestEmptyField2-c.Dat'  
   WITH (  
      DATAFILETYPE = 'char',  
      FIELDTERMINATOR = ',',  
      KEEPNULLS  
   );  
GO  
  
```  
  
## <a name="keeping-default-values-with-insert--select--from-openrowsetbulk"></a><span data-ttu-id="6d918-154">Conservation des valeurs par défaut avec INSERT... SELECT \* FROM OPENROWSET (BULK...)</span><span class="sxs-lookup"><span data-stu-id="6d918-154">Keeping Default Values with INSERT ... SELECT \* FROM OPENROWSET(BULK...)</span></span>  
 <span data-ttu-id="6d918-155">Par défaut, toutes les colonnes qui ne sont pas spécifiées dans l’opération de chargement en bloc ont la valeur NULL par INSERT... SELECT \* FROM OPENROWSET (BULK...). Toutefois, vous pouvez spécifier que pour un champ vide dans le fichier de données, la colonne de table correspondante utilise sa valeur par défaut (le cas échéant).</span><span class="sxs-lookup"><span data-stu-id="6d918-155">By default, any columns that are not specified in the bulk-load operation are set to NULL by INSERT ... SELECT \* FROM OPENROWSET(BULK...). However, you can specify that for an empty field in the data file, the corresponding table column uses its default value (if any).</span></span> <span data-ttu-id="6d918-156">Pour utiliser les valeurs par défaut, spécifiez l'indicateur de table suivant :</span><span class="sxs-lookup"><span data-stu-id="6d918-156">To use default values, specify the following table hint:</span></span>  
  
|<span data-ttu-id="6d918-157">Commande</span><span class="sxs-lookup"><span data-stu-id="6d918-157">Command</span></span>|<span data-ttu-id="6d918-158">Qualificateur</span><span class="sxs-lookup"><span data-stu-id="6d918-158">Qualifier</span></span>|<span data-ttu-id="6d918-159">Type de qualificateur</span><span class="sxs-lookup"><span data-stu-id="6d918-159">Qualifier Type</span></span>|  
|-------------|---------------|--------------------|  
|<span data-ttu-id="6d918-160">INSERT ... SELECT \* FROM OPENROWSET(BULK...)</span><span class="sxs-lookup"><span data-stu-id="6d918-160">INSERT ... SELECT \* FROM OPENROWSET(BULK...)</span></span>|<span data-ttu-id="6d918-161">WITH(KEEPDEFAULTS)</span><span class="sxs-lookup"><span data-stu-id="6d918-161">WITH(KEEPDEFAULTS)</span></span>|<span data-ttu-id="6d918-162">Indicateur de table</span><span class="sxs-lookup"><span data-stu-id="6d918-162">Table hint</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="6d918-163">Pour plus d’informations, consultez [INSERT &#40;Transact-sql&#41;](/sql/t-sql/statements/insert-transact-sql), [Select &#40;transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql), [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql)et [indicateurs de table &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-table)</span><span class="sxs-lookup"><span data-stu-id="6d918-163">for more information, see [INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql), [SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql), [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql), and [Table Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-table)</span></span>  
  
### <a name="examples"></a><span data-ttu-id="6d918-164">Exemples</span><span class="sxs-lookup"><span data-stu-id="6d918-164">Examples</span></span>  
 <span data-ttu-id="6d918-165">L’instruction INSERT suivante... L’exemple SELECT \* FROM OPENROWSET (BULK...) importe en bloc des données et conserve les valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="6d918-165">The following INSERT ... SELECT \* FROM OPENROWSET(BULK...) example bulk imports data and keeps the default values.</span></span>  
  
 <span data-ttu-id="6d918-166">Pour exécuter les exemples, vous devez créer l'exemple de table **MyTestDefaultCol2** , le fichier de données `MyTestEmptyField2-c.Dat` et utiliser un fichier de format, `MyTestDefaultCol2-f-c.Fmt`.</span><span class="sxs-lookup"><span data-stu-id="6d918-166">To run the examples, you need to create the **MyTestDefaultCol2** sample table, the `MyTestEmptyField2-c.Dat` data file, and use a format file, `MyTestDefaultCol2-f-c.Fmt`.</span></span> <span data-ttu-id="6d918-167">Pour plus d'informations sur la création de ces exemples, consultez la section « Exemples de table et de fichier de données », plus haut dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="6d918-167">For information on creating these samples, see "Sample Table and Data File," earlier in this topic.</span></span>  
  
 <span data-ttu-id="6d918-168">La deuxième colonne de la table, **Col2**, a une valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="6d918-168">The second table column, **Col2**, has a default value.</span></span> <span data-ttu-id="6d918-169">Le champ correspondant du fichier de données contient une chaîne vide.</span><span class="sxs-lookup"><span data-stu-id="6d918-169">The corresponding field of the data file contains an empty string.</span></span> <span data-ttu-id="6d918-170">Quand INSERT... SELECT \* FROM OPENROWSET (BULK...) importe les champs de ce fichier de données dans la table **MyTestDefaultCol2** . par défaut, la valeur null est insérée dans **col2** au lieu de la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="6d918-170">When INSERT ... SELECT \* FROM OPENROWSET(BULK...) import the fields of this data file into the **MyTestDefaultCol2** table, by default, NULL is inserted into **Col2** instead of the default value.</span></span> <span data-ttu-id="6d918-171">Ce comportement par défaut produit le résultat suivant :</span><span class="sxs-lookup"><span data-stu-id="6d918-171">This default behavior produces the following result:</span></span>  
  
||||  
|-|-|-|  
|`1`|`NULL`|`DataField3`|  
|`2`|`NULL`|`DataField3`|  
  
 <span data-ttu-id="6d918-172">Pour insérer la valeur par défaut «`Default value of Col2`», au lieu de «`NULL`», vous devez utiliser l'indicateur de table KEEPDEFAULTS, comme le montre l'exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="6d918-172">To insert the default value, "`Default value of Col2`", instead of "`NULL`", you need to use KEEPDEFAULTS table hint, as demonstrated in the following example.</span></span> <span data-ttu-id="6d918-173">À partir d'un outil de requête tel que l'Éditeur de requête [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], exécutez :</span><span class="sxs-lookup"><span data-stu-id="6d918-173">From a query tool, such as [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
INSERT INTO MyTestDefaultCol2  
    WITH (KEEPDEFAULTS)  
    SELECT *  
      FROM OPENROWSET(BULK  'C:\MyTestEmptyField2-c.Dat',  
      FORMATFILE='C:\MyTestDefaultCol2-f-c.Fmt'       
      ) as t1 ;  
GO  
  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="6d918-174">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="6d918-174">Related Tasks</span></span>  
  
-   [<span data-ttu-id="6d918-175">Conserver des valeurs d’identité lors de l’importation de données en bloc &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6d918-175">Keep Identity Values When Bulk Importing Data &#40;SQL Server&#41;</span></span>](keep-identity-values-when-bulk-importing-data-sql-server.md)  
  
-   [<span data-ttu-id="6d918-176">Préparer des données en vue d’une exportation ou d’une importation en bloc &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6d918-176">Prepare Data for Bulk Export or Import &#40;SQL Server&#41;</span></span>](prepare-data-for-bulk-export-or-import-sql-server.md)  
  
 <span data-ttu-id="6d918-177">**Pour utiliser un fichier de format**</span><span class="sxs-lookup"><span data-stu-id="6d918-177">**To use a format file**</span></span>  
  
-   [<span data-ttu-id="6d918-178">Créer un fichier de format &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6d918-178">Create a Format File &#40;SQL Server&#41;</span></span>](create-a-format-file-sql-server.md)  
  
-   [<span data-ttu-id="6d918-179">Utiliser un fichier de format pour importer des données en bloc &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6d918-179">Use a Format File to Bulk Import Data &#40;SQL Server&#41;</span></span>](use-a-format-file-to-bulk-import-data-sql-server.md)  
  
-   [<span data-ttu-id="6d918-180">Utiliser un fichier de format pour mapper les colonnes d’une table sur les champs d’un fichier de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6d918-180">Use a Format File to Map Table Columns to Data-File Fields &#40;SQL Server&#41;</span></span>](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md)  
  
-   [<span data-ttu-id="6d918-181">Utiliser un fichier de format pour ignorer un champ de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6d918-181">Use a Format File to Skip a Data Field &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-data-field-sql-server.md)  
  
-   [<span data-ttu-id="6d918-182">Utiliser un fichier de format pour ignorer une colonne de table &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6d918-182">Use a Format File to Skip a Table Column &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-table-column-sql-server.md)  
  
 <span data-ttu-id="6d918-183">**Pour utiliser des formats de données pour l'importation ou l'exportation en bloc**</span><span class="sxs-lookup"><span data-stu-id="6d918-183">**To use data formats for bulk import or bulk export**</span></span>  
  
-   [<span data-ttu-id="6d918-184">Importer des données au format natif et caractère à partir de versions antérieures de SQL Server</span><span class="sxs-lookup"><span data-stu-id="6d918-184">Import Native and Character Format Data from Earlier Versions of SQL Server</span></span>](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md)  
  
-   [<span data-ttu-id="6d918-185">Utiliser le format caractère pour importer ou exporter des données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6d918-185">Use Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="6d918-186">Utiliser le format natif pour importer ou exporter des données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6d918-186">Use Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-native-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="6d918-187">Utiliser le format caractère Unicode pour importer ou exporter des données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6d918-187">Use Unicode Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="6d918-188">Utiliser le format natif Unicode pour importer ou exporter des données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6d918-188">Use Unicode Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-native-format-to-import-or-export-data-sql-server.md)  
  
 <span data-ttu-id="6d918-189">**Pour spécifier des formats de données pour la compatibilité lors de l'utilisation de bcp**</span><span class="sxs-lookup"><span data-stu-id="6d918-189">**To specify data formats for compatibility when using bcp**</span></span>  
  
-   [<span data-ttu-id="6d918-190">Spécifier des indicateurs de fin de champ et de fin de ligne &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6d918-190">Specify Field and Row Terminators &#40;SQL Server&#41;</span></span>](specify-field-and-row-terminators-sql-server.md)  
  
-   [<span data-ttu-id="6d918-191">Spécifier une longueur de préfixe dans des fichiers de données à l’aide de bcp &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6d918-191">Specify Prefix Length in Data Files by Using bcp &#40;SQL Server&#41;</span></span>](specify-prefix-length-in-data-files-by-using-bcp-sql-server.md)  
  
-   [<span data-ttu-id="6d918-192">Spécifier le type de stockage de fichiers à l’aide de bcp &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6d918-192">Specify File Storage Type by Using bcp &#40;SQL Server&#41;</span></span>](specify-file-storage-type-by-using-bcp-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="6d918-193">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6d918-193">See Also</span></span>  
 <span data-ttu-id="6d918-194">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6d918-194">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="6d918-195">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6d918-195">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 <span data-ttu-id="6d918-196">[Utilitaire bcp](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="6d918-196">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="6d918-197">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6d918-197">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 [<span data-ttu-id="6d918-198">Indicateurs de table &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6d918-198">Table Hints &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/hints-transact-sql-table)  
  
  
