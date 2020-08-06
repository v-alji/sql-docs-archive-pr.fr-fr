---
title: Conserver des valeurs d’identité lors de l’importation de données en bloc (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- identity values [SQL Server], bulk imports
- data formats [SQL Server], identity values
- bulk importing [SQL Server], identity values
ms.assetid: 45894a3f-2d8a-4edd-9568-afa7d0d3061f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 07f6714f27f60afda91134034509ff439d92f071
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612330"
---
# <a name="keep-identity-values-when-bulk-importing-data-sql-server"></a><span data-ttu-id="9636b-102">Conserver des valeurs d'identité lors de l'importation de données en bloc (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9636b-102">Keep Identity Values When Bulk Importing Data (SQL Server)</span></span>
  <span data-ttu-id="9636b-103">Les fichiers de données qui contiennent des valeurs d’identité peuvent être importés en bloc dans une instance de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9636b-103">Data files that contain identity values can be bulk imported into an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="9636b-104">Par défaut, les valeurs de la colonne d'identité du fichier de données importé sont ignorées et [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] affecte automatiquement des valeurs uniques.</span><span class="sxs-lookup"><span data-stu-id="9636b-104">By default, the values for the identity column in the data file that is imported are ignored and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] assigns unique values automatically.</span></span> <span data-ttu-id="9636b-105">Ces valeurs uniques reposent sur les valeurs de départ et d'incrément spécifiées lors de la création de la table.</span><span class="sxs-lookup"><span data-stu-id="9636b-105">The unique values are based on the seed and increment values that are specified during table creation.</span></span>  
  
 <span data-ttu-id="9636b-106">Si les fichiers de données ne contiennent pas de valeurs pour la colonne d'identificateur de la table, vous devez utiliser un fichier de format pour préciser si la colonne d'identificateur de la table doit être ignorée lors de l'importation de données.</span><span class="sxs-lookup"><span data-stu-id="9636b-106">If the data file does not contain values for the identifier column in the table, use a format file to specify that the identifier column in the table should be skipped when importing data.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="9636b-107">assigne automatiquement des valeurs uniques pour la colonne.</span><span class="sxs-lookup"><span data-stu-id="9636b-107">assigns unique values for the column automatically.</span></span>  
  
 <span data-ttu-id="9636b-108">Pour empêcher [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] d'assigner des valeurs d'identité lors de l'importation en bloc de lignes de données dans une table, utilisez le qualificateur de commande de conservation d'identité approprié.</span><span class="sxs-lookup"><span data-stu-id="9636b-108">To prevent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from assigning identity values while bulk importing data rows into a table, use the appropriate keep-identity command qualifier.</span></span> <span data-ttu-id="9636b-109">Lorsque vous spécifiez un qualificateur de conservation d'identité, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilise les valeurs d'identité du fichier de données.</span><span class="sxs-lookup"><span data-stu-id="9636b-109">When you specify a keep-identity qualifier, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses the identity values in the data file.</span></span> <span data-ttu-id="9636b-110">Ces qualificateurs sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="9636b-110">These qualifiers are as follows:</span></span>  
  
|<span data-ttu-id="9636b-111">Commande</span><span class="sxs-lookup"><span data-stu-id="9636b-111">Command</span></span>|<span data-ttu-id="9636b-112">Qualificateur de conservation d'identité</span><span class="sxs-lookup"><span data-stu-id="9636b-112">Keep-identity qualifier</span></span>|<span data-ttu-id="9636b-113">Type de qualificateur</span><span class="sxs-lookup"><span data-stu-id="9636b-113">Qualifier type</span></span>|  
|-------------|------------------------------|--------------------|  
|`bcp`|<span data-ttu-id="9636b-114">**-E**</span><span class="sxs-lookup"><span data-stu-id="9636b-114">**-E**</span></span>|<span data-ttu-id="9636b-115">Commutateur</span><span class="sxs-lookup"><span data-stu-id="9636b-115">Switch</span></span>|  
|<span data-ttu-id="9636b-116">BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="9636b-116">BULK INSERT</span></span>|<span data-ttu-id="9636b-117">KEEPIDENTITY</span><span class="sxs-lookup"><span data-stu-id="9636b-117">KEEPIDENTITY</span></span>|<span data-ttu-id="9636b-118">Argument</span><span class="sxs-lookup"><span data-stu-id="9636b-118">Argument</span></span>|  
|<span data-ttu-id="9636b-119">INSERT ... SELECT \* FROM OPENROWSET(BULK...)</span><span class="sxs-lookup"><span data-stu-id="9636b-119">INSERT ... SELECT \* FROM OPENROWSET(BULK...)</span></span>|<span data-ttu-id="9636b-120">KEEPIDENTITY</span><span class="sxs-lookup"><span data-stu-id="9636b-120">KEEPIDENTITY</span></span>|<span data-ttu-id="9636b-121">Indicateur de table</span><span class="sxs-lookup"><span data-stu-id="9636b-121">Table hint</span></span>|  
  
 <span data-ttu-id="9636b-122">Pour plus d’informations, consultez [bcp Utility](../../tools/bcp-utility.md), [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql), [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql), [INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql), [SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) et [Indicateurs de table &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-table).</span><span class="sxs-lookup"><span data-stu-id="9636b-122">For more information, see [bcp Utility](../../tools/bcp-utility.md), [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql), [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql), [INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql), [SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql), and [Table Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-table).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9636b-123">Pour créer un numéro à incrémentation automatique qui peut être utilisé dans plusieurs tables ou être appelé par des applications sans faire référence à une table, consultez [Numéros de séquence](../sequence-numbers/sequence-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="9636b-123">To create an automatically incrementing number that can be used in multiple tables or that can be called from applications without referencing any table, see [Sequence Numbers](../sequence-numbers/sequence-numbers.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="9636b-124">Exemples</span><span class="sxs-lookup"><span data-stu-id="9636b-124">Examples</span></span>  
 <span data-ttu-id="9636b-125">Les exemples de cette rubrique importent des données en bloc à l’aide de l’instruction INSERT... SELECT \* FROM OPENROWSET (BULK...) et conserve les valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="9636b-125">The examples in this topic bulk import data using INSERT ... SELECT \* FROM OPENROWSET(BULK...) and keeping default values.</span></span>  
  
### <a name="sample-table"></a><span data-ttu-id="9636b-126">Exemple de table</span><span class="sxs-lookup"><span data-stu-id="9636b-126">Sample Table</span></span>  
 <span data-ttu-id="9636b-127">Dans ces exemples d’importation en bloc, la table **myTestKeepNulls** est créée dans l’exemple de base de données **AdventureWorks** sous le schéma **dbo**.</span><span class="sxs-lookup"><span data-stu-id="9636b-127">The bulk-import examples require that a table named **myTestKeepNulls** table be created in the **AdventureWorks** sample database under the **dbo** schema.</span></span> <span data-ttu-id="9636b-128">Pour créer cette table.</span><span class="sxs-lookup"><span data-stu-id="9636b-128">To create this table.</span></span> <span data-ttu-id="9636b-129">dans l'éditeur de requête [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], exécutez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="9636b-129">in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
SELECT * INTO HumanResources.myDepartment   
   FROM HumanResources.Department  
      WHERE 1=0;  
GO  
SELECT * FROM HumanResources.myDepartment;  
```  
  
 <span data-ttu-id="9636b-130">Dans la table **Department** sur laquelle repose `myDepartment`, l’option IDENTITY_INSERT est désactivée (valeur OFF).</span><span class="sxs-lookup"><span data-stu-id="9636b-130">The **Department** table on which `myDepartment` is based has IDENTITY_INSERT is set to OFF.</span></span> <span data-ttu-id="9636b-131">Ainsi, pour importer des données dans une colonne d’identité, vous devez spécifier KEEPIDENTITY ou **-E**.</span><span class="sxs-lookup"><span data-stu-id="9636b-131">Therefore, to import data into an identity column you must specify KEEPIDENTITY or **-E**.</span></span>  
  
### <a name="sample-data-file"></a><span data-ttu-id="9636b-132">Fichier de données d'exemple</span><span class="sxs-lookup"><span data-stu-id="9636b-132">Sample Data File</span></span>  
 <span data-ttu-id="9636b-133">Le fichier de données utilisé dans les exemples d'importation en bloc contient des données exportées en bloc à partir de la table `HumanResources.Department` dans leur format natif.</span><span class="sxs-lookup"><span data-stu-id="9636b-133">The data file used in the bulk-import examples contains data bulk exported from the `HumanResources.Department` table in native format.</span></span> <span data-ttu-id="9636b-134">Pour créer le fichier de données, à l'invite de commandes [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, entrez :</span><span class="sxs-lookup"><span data-stu-id="9636b-134">To create the data file, at the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks.HumanResources.Department out myDepartment-n.Dat -n -T  
```  
  
### <a name="sample-format-file"></a><span data-ttu-id="9636b-135">Fichier de format d'exemple</span><span class="sxs-lookup"><span data-stu-id="9636b-135">Sample Format File</span></span>  
 <span data-ttu-id="9636b-136">Dans cet exemple d'importation en bloc, le fichier de format XML (`myDepartment-f-x-n.Xml`) utilise des formats de données natifs.</span><span class="sxs-lookup"><span data-stu-id="9636b-136">This bulk-import examples use an XML format file, `myDepartment-f-x-n.Xml`, which uses native data formats.</span></span> <span data-ttu-id="9636b-137">Ce fichier de format est ici créé à l'aide de la commande `bcp`, à partir de la table `HumanResources.Department` de la base de données `AdventureWorks`.</span><span class="sxs-lookup"><span data-stu-id="9636b-137">This example uses `bcp` to create to generate this format file from the `HumanResources.Department` table of the `AdventureWorks` database.</span></span> <span data-ttu-id="9636b-138">À l'invite de commandes Windows, entrez :</span><span class="sxs-lookup"><span data-stu-id="9636b-138">At the Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks.HumanResources.Department format nul -n -x -f myDepartment-f-n-x.Xml -T  
```  
  
 <span data-ttu-id="9636b-139">Pour plus d’informations sur la création d’un fichier de format, consultez [Créer un fichier de format &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9636b-139">For more information about creating a format file, see [Create a Format File &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span></span>  
  
### <a name="a-using-bcp-and-keeping-identity-values"></a><span data-ttu-id="9636b-140">R.</span><span class="sxs-lookup"><span data-stu-id="9636b-140">A.</span></span> <span data-ttu-id="9636b-141">Utilisation de bcp et conservation des valeurs d'identité</span><span class="sxs-lookup"><span data-stu-id="9636b-141">Using bcp and Keeping Identity Values</span></span>  
 <span data-ttu-id="9636b-142">Cet exemple montre comment conserver les valeurs d'identité dans le cadre d'une importation de données en bloc avec la commande `bcp`.</span><span class="sxs-lookup"><span data-stu-id="9636b-142">The following example demonstrates how to keep identity values when using `bcp` to bulk import data.</span></span> <span data-ttu-id="9636b-143">La commande `bcp`, qui utilise le fichier de format `myDepartment-f-n-x.Xml`, contient les commutateurs suivants :</span><span class="sxs-lookup"><span data-stu-id="9636b-143">The `bcp` command uses the format file, `myDepartment-f-n-x.Xml`, and contains the following switches:</span></span>  
  
|<span data-ttu-id="9636b-144">Qualificateurs</span><span class="sxs-lookup"><span data-stu-id="9636b-144">Qualifiers</span></span>|<span data-ttu-id="9636b-145">Description</span><span class="sxs-lookup"><span data-stu-id="9636b-145">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="9636b-146">**-E**</span><span class="sxs-lookup"><span data-stu-id="9636b-146">**-E**</span></span>|<span data-ttu-id="9636b-147">Précise que les valeurs d'identité du fichier de données doivent être utilisées pour la colonne d'identité.</span><span class="sxs-lookup"><span data-stu-id="9636b-147">Specifies that identity value or values in the data file are to be used for the identity column.</span></span>|  
|<span data-ttu-id="9636b-148">**-T**</span><span class="sxs-lookup"><span data-stu-id="9636b-148">**-T**</span></span>|<span data-ttu-id="9636b-149">Spécifie que l' `bcp` utilitaire se connecte à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] avec une connexion approuvée.</span><span class="sxs-lookup"><span data-stu-id="9636b-149">Specifies that the `bcp` utility connects to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with a trusted connection.</span></span>|  
  
 <span data-ttu-id="9636b-150">À l'invite de commandes Windows, entrez :</span><span class="sxs-lookup"><span data-stu-id="9636b-150">At the Windows command prompt, enter.</span></span>  
  
```  
bcp AdventureWorks.HumanResources.myDepartment in C:\myDepartment-n.Dat -f C:\myDepartment-f-n-x.Xml -E -T  
  
```  
  
### <a name="b-using-bulk-insert-and-keeping-identity-values"></a><span data-ttu-id="9636b-151">B.</span><span class="sxs-lookup"><span data-stu-id="9636b-151">B.</span></span> <span data-ttu-id="9636b-152">Utilisation de BULK INSERT et conservation des valeurs d'identité</span><span class="sxs-lookup"><span data-stu-id="9636b-152">Using BULK INSERT and Keeping Identity Values</span></span>  
 <span data-ttu-id="9636b-153">Dans l'exemple suivant, l'instruction BULK INSERT est utilisée pour importer des données en bloc dans la table `myDepartment-c.Dat` à partir du fichier `AdventureWorks.HumanResources.myDepartment` .</span><span class="sxs-lookup"><span data-stu-id="9636b-153">The following example uses BULK INSERT to bulk import data from the `myDepartment-c.Dat` file into the `AdventureWorks.HumanResources.myDepartment` table.</span></span> <span data-ttu-id="9636b-154">L'instruction utilise le fichier de format `myDepartment-f-n-x.Xml` et inclut l'option KEEPIDENTITY pour assurer la conservation des valeurs d'identité éventuellement présentes dans le fichier de données.</span><span class="sxs-lookup"><span data-stu-id="9636b-154">The statement uses the `myDepartment-f-n-x.Xml` format file and includes the KEEPIDENTITY option to ensure that any identity values in the data file are retained.</span></span>  
  
 <span data-ttu-id="9636b-155">Dans l'Éditeur de requête [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], exécutez :</span><span class="sxs-lookup"><span data-stu-id="9636b-155">In the [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
DELETE HumanResources.myDepartment;  
GO  
BULK INSERT HumanResources.myDepartment  
   FROM 'C:\myDepartment-n.Dat'  
   WITH (  
      KEEPIDENTITY,  
      FORMATFILE='C:\myDepartment-f-n-x.Xml'  
   );  
GO  
SELECT * FROM HumanResources.myDepartment;  
  
```  
  
### <a name="c-using-openrowset-and-keeping-identity-values"></a><span data-ttu-id="9636b-156">C.</span><span class="sxs-lookup"><span data-stu-id="9636b-156">C.</span></span> <span data-ttu-id="9636b-157">Utilisation de OPENROWSET et conservation des valeurs d'identité</span><span class="sxs-lookup"><span data-stu-id="9636b-157">Using OPENROWSET and Keeping Identity Values</span></span>  
 <span data-ttu-id="9636b-158">Dans l'exemple suivant, le fournisseur d'ensembles de lignes en bloc OPENROWSET sert à importer des données en bloc dans la table `myDepartment-c.Dat` à partir du fichier `AdventureWorks.HumanResources.myDepartment` .</span><span class="sxs-lookup"><span data-stu-id="9636b-158">The following example uses the OPENROWSET bulk rowset provider to bulk import data from the `myDepartment-c.Dat` file into the `AdventureWorks.HumanResources.myDepartment` table.</span></span> <span data-ttu-id="9636b-159">L'instruction utilise le fichier de format `myDepartment-f-n-x.Xml` et inclut l'indicateur KEEPIDENTITY pour assurer la conservation des valeurs d'identité éventuellement présentes dans le fichier de données.</span><span class="sxs-lookup"><span data-stu-id="9636b-159">The statement uses the `myDepartment-f-n-x.Xml` format file and includes the KEEPIDENTITY hint to ensure that any identity values in the data file are retained.</span></span>  
  
 <span data-ttu-id="9636b-160">Dans l'Éditeur de requête [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], exécutez :</span><span class="sxs-lookup"><span data-stu-id="9636b-160">In the [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
DELETE HumanResources.myDepartment;  
GO  
  
INSERT INTO HumanResources.myDepartment  
   with (KEEPIDENTITY)  
   (DepartmentID, Name, GroupName, ModifiedDate)  
   SELECT *  
      FROM  OPENROWSET(BULK 'C:\myDepartment-n.Dat',  
      FORMATFILE='C:\myDepartment-f-n-x.Xml') as t1;  
GO  
  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="9636b-161">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="9636b-161">Related Tasks</span></span>  
  
-   [<span data-ttu-id="9636b-162">Conserver les valeurs NULL ou utiliser la valeur par défaut lors de l’importation en bloc &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9636b-162">Keep Nulls or Use Default Values During Bulk Import &#40;SQL Server&#41;</span></span>](keep-nulls-or-use-default-values-during-bulk-import-sql-server.md)  
  
-   [<span data-ttu-id="9636b-163">Préparer des données en vue d’une exportation ou d’une importation en bloc &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9636b-163">Prepare Data for Bulk Export or Import &#40;SQL Server&#41;</span></span>](prepare-data-for-bulk-export-or-import-sql-server.md)  
  
 <span data-ttu-id="9636b-164">**Pour utiliser un fichier de format**</span><span class="sxs-lookup"><span data-stu-id="9636b-164">**To use a format file**</span></span>  
  
-   [<span data-ttu-id="9636b-165">Créer un fichier de format &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9636b-165">Create a Format File &#40;SQL Server&#41;</span></span>](create-a-format-file-sql-server.md)  
  
-   [<span data-ttu-id="9636b-166">Utiliser un fichier de format pour importer des données en bloc &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9636b-166">Use a Format File to Bulk Import Data &#40;SQL Server&#41;</span></span>](use-a-format-file-to-bulk-import-data-sql-server.md)  
  
-   [<span data-ttu-id="9636b-167">Utiliser un fichier de format pour mapper les colonnes d’une table sur les champs d’un fichier de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9636b-167">Use a Format File to Map Table Columns to Data-File Fields &#40;SQL Server&#41;</span></span>](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md)  
  
-   [<span data-ttu-id="9636b-168">Utiliser un fichier de format pour ignorer un champ de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9636b-168">Use a Format File to Skip a Data Field &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-data-field-sql-server.md)  
  
-   [<span data-ttu-id="9636b-169">Utiliser un fichier de format pour ignorer une colonne de table &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9636b-169">Use a Format File to Skip a Table Column &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-table-column-sql-server.md)  
  
 <span data-ttu-id="9636b-170">**Pour utiliser des formats de données pour l'importation ou l'exportation en bloc**</span><span class="sxs-lookup"><span data-stu-id="9636b-170">**To use data formats for bulk import or bulk export**</span></span>  
  
-   [<span data-ttu-id="9636b-171">Importer des données au format natif et caractère à partir de versions antérieures de SQL Server</span><span class="sxs-lookup"><span data-stu-id="9636b-171">Import Native and Character Format Data from Earlier Versions of SQL Server</span></span>](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md)  
  
-   [<span data-ttu-id="9636b-172">Utiliser le format caractère pour importer ou exporter des données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9636b-172">Use Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="9636b-173">Utiliser le format natif pour importer ou exporter des données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9636b-173">Use Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-native-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="9636b-174">Utiliser le format caractère Unicode pour importer ou exporter des données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9636b-174">Use Unicode Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="9636b-175">Utiliser le format natif Unicode pour importer ou exporter des données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9636b-175">Use Unicode Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-native-format-to-import-or-export-data-sql-server.md)  
  
 <span data-ttu-id="9636b-176">**Pour spécifier des formats de données pour la compatibilité lors de l'utilisation de bcp**</span><span class="sxs-lookup"><span data-stu-id="9636b-176">**To specify data formats for compatibility when using bcp**</span></span>  
  
1.  [<span data-ttu-id="9636b-177">Spécifier des indicateurs de fin de champ et de fin de ligne &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9636b-177">Specify Field and Row Terminators &#40;SQL Server&#41;</span></span>](specify-field-and-row-terminators-sql-server.md)  
  
2.  [<span data-ttu-id="9636b-178">Spécifier une longueur de préfixe dans des fichiers de données à l’aide de bcp &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9636b-178">Specify Prefix Length in Data Files by Using bcp &#40;SQL Server&#41;</span></span>](specify-prefix-length-in-data-files-by-using-bcp-sql-server.md)  
  
3.  [<span data-ttu-id="9636b-179">Spécifier le type de stockage de fichiers à l’aide de bcp &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9636b-179">Specify File Storage Type by Using bcp &#40;SQL Server&#41;</span></span>](specify-file-storage-type-by-using-bcp-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="9636b-180">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9636b-180">See Also</span></span>  
 <span data-ttu-id="9636b-181">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9636b-181">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="9636b-182">[Utilitaire bcp](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="9636b-182">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="9636b-183">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9636b-183">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 <span data-ttu-id="9636b-184">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9636b-184">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 [<span data-ttu-id="9636b-185">Indicateurs de table &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9636b-185">Table Hints &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/hints-transact-sql-table)  
  
  
