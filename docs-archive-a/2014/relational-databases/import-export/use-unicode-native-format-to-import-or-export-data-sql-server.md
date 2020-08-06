---
title: Utiliser le format natif Unicode pour importer ou exporter des données (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- Unicode [SQL Server], bulk importing and exporting
- data formats [SQL Server], Unicode native
ms.assetid: a6213308-f3d5-406e-9029-19d8bb3367f3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: beae2f836de16dedf3be6d8c196910c53be02266
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708383"
---
# <a name="use-unicode-native-format-to-import-or-export-data-sql-server"></a><span data-ttu-id="01fb8-102">Utiliser le format natif Unicode pour importer ou exporter des données (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="01fb8-102">Use Unicode Native Format to Import or Export Data (SQL Server)</span></span>
  <span data-ttu-id="01fb8-103">Le format natif Unicode est utile quand vous devez copier des informations d’une installation de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vers une autre.</span><span class="sxs-lookup"><span data-stu-id="01fb8-103">Unicode native format is helpful when information must be copied from one [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation to another.</span></span> <span data-ttu-id="01fb8-104">L'utilisation du format natif pour les données qui ne sont pas de type caractère (char) permet de gagner du temps, puisque vous supprimez les conversions inutiles des types de données depuis et vers le format caractère.</span><span class="sxs-lookup"><span data-stu-id="01fb8-104">The use of native format for noncharacter data saves time, eliminating unnecessary conversion of data types to and from character format.</span></span> <span data-ttu-id="01fb8-105">L'utilisation du format caractère Unicode pour toutes les données de type caractère évite la perte des caractères étendus lorsque vous transférez en bloc des données entre des serveurs utilisant des pages de codes différentes.</span><span class="sxs-lookup"><span data-stu-id="01fb8-105">The use of Unicode character format for all character data prevents loss of any extended characters during bulk transfer of data between servers using different code pages.</span></span> <span data-ttu-id="01fb8-106">Un fichier de données au format natif Unicode peut être lu par toutes les méthodes d'importation en bloc.</span><span class="sxs-lookup"><span data-stu-id="01fb8-106">A data file in Unicode native format can be read by any bulk-import method.</span></span>  
  
 <span data-ttu-id="01fb8-107">Le format natif Unicode est recommandé pour le transfert en bloc des données entre plusieurs instances de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] par le biais d'un fichier de données qui contient des caractères étendus ou des caractères codés sur deux octets (DBCS).</span><span class="sxs-lookup"><span data-stu-id="01fb8-107">Unicode native format is recommended for the bulk transfer of data between multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using a data file that contains extended or DBCS characters.</span></span> <span data-ttu-id="01fb8-108">Pour les données qui ne sont pas de type caractère, le format natif Unicode utilise des types de données (bases de données) natifs.</span><span class="sxs-lookup"><span data-stu-id="01fb8-108">For noncharacter data, Unicode native format uses native (database) data types.</span></span> <span data-ttu-id="01fb8-109">Pour les données de type caractère (par exemple `char`, `nchar`, `varchar`, `nvarchar`, `text`, `varchar(max)`, `nvarchar(max)` et `ntext`), le format natif Unicode utilise le format de données de type caractère Unicode.</span><span class="sxs-lookup"><span data-stu-id="01fb8-109">For character data, such as `char`, `nchar`, `varchar`, `nvarchar`, `text`, `varchar(max)`, `nvarchar(max)`, and `ntext`, the Unicode native format uses Unicode character data format.</span></span>  
  
 <span data-ttu-id="01fb8-110">Les données `sql_variant` qui sont stockées en tant que SQLVARIANT dans un fichier de données au format natif Unicode fonctionnent de la même manière que le fichier de données au format natif, sauf que les valeurs `char` et `varchar` sont converties en `nchar` et `nvarchar`, ce qui double l'espace de stockage nécessaire pour les colonnes affectées.</span><span class="sxs-lookup"><span data-stu-id="01fb8-110">The `sql_variant` data that is stored as a SQLVARIANT in a Unicode native-format data file operates in the same manner as it does in a native-format data file, except that `char` and `varchar` values are converted to `nchar` and `nvarchar`, which doubles the amount of storage required for the affected columns.</span></span> <span data-ttu-id="01fb8-111">Les métadonnées d'origine sont conservées, et les valeurs sont reconverties en leur type de données `char` et `varchar` d'origine lorsqu'elles sont importées en bloc dans une colonne de table.</span><span class="sxs-lookup"><span data-stu-id="01fb8-111">The original metadata is preserved, and the values are converted back to their original `char` and `varchar` data type when bulk imported into a table column.</span></span>  
  
## <a name="command-options-for-unicode-native-format"></a><span data-ttu-id="01fb8-112">Options de commande pour le format natif Unicode</span><span class="sxs-lookup"><span data-stu-id="01fb8-112">Command Options for Unicode Native Format</span></span>  
 <span data-ttu-id="01fb8-113">Vous pouvez importer des données au format natif Unicode dans une table à l’aide de la commande **BCP**, Bulk Insert ou Insert... SELECT \* FROM OPENROWSET (BULK...). Pour une commande **BCP** ou une instruction BULK INSERT, vous pouvez spécifier le format de données sur la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="01fb8-113">You can import Unicode native format data into a table using **bcp**, BULK INSERT or INSERT ... SELECT \* FROM OPENROWSET(BULK...). For a **bcp** command or BULK INSERT statement, you can specify the data format on the command line.</span></span> <span data-ttu-id="01fb8-114">Pour une instruction INSERT... SELECT \* FROM OPENROWSET(BULK...), vous devez spécifier le format de données dans un fichier de format.</span><span class="sxs-lookup"><span data-stu-id="01fb8-114">For an INSERT ... SELECT \* FROM OPENROWSET(BULK...) statement, you must specify the data format in a format file.</span></span>  
  
 <span data-ttu-id="01fb8-115">Le format natif Unicode est reconnu par les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="01fb8-115">Unicode native format is supported by the following options:</span></span>  
  
|<span data-ttu-id="01fb8-116">Commande</span><span class="sxs-lookup"><span data-stu-id="01fb8-116">Command</span></span>|<span data-ttu-id="01fb8-117">Option</span><span class="sxs-lookup"><span data-stu-id="01fb8-117">Option</span></span>|<span data-ttu-id="01fb8-118">Description</span><span class="sxs-lookup"><span data-stu-id="01fb8-118">Description</span></span>|  
|-------------|------------|-----------------|  
|<span data-ttu-id="01fb8-119">**bcp**</span><span class="sxs-lookup"><span data-stu-id="01fb8-119">**bcp**</span></span>|<span data-ttu-id="01fb8-120">**-N**</span><span class="sxs-lookup"><span data-stu-id="01fb8-120">**-N**</span></span>|<span data-ttu-id="01fb8-121">Fait en sorte que l’utilitaire **BCP** utilise le format natif Unicode, qui utilise des types de données (base de données) natifs pour toutes les données non-caractères et le format de données caractères Unicode pour toutes les données de type caractère (,,,, `char` `nchar` `varchar` `nvarchar` `text` et `ntext` ).</span><span class="sxs-lookup"><span data-stu-id="01fb8-121">Causes the **bcp** utility to use the Unicode native format, which uses native (database) data types for all noncharacter data and Unicode character data format for all character (`char`, `nchar`, `varchar`, `nvarchar`, `text`, and `ntext`) data.</span></span>|  
|<span data-ttu-id="01fb8-122">BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="01fb8-122">BULK INSERT</span></span>|<span data-ttu-id="01fb8-123">DATAFILETYPE **= '** widenative **'**</span><span class="sxs-lookup"><span data-stu-id="01fb8-123">DATAFILETYPE **='** widenative **'**</span></span>|<span data-ttu-id="01fb8-124">Utilisez le format natif Unicode lorsque vous importez en bloc des données.</span><span class="sxs-lookup"><span data-stu-id="01fb8-124">Use Unicode native format when bulk importing data.</span></span>|  
  
 <span data-ttu-id="01fb8-125">Pour plus d’informations, consultez [Utilitaire bcp](../../tools/bcp-utility.md), [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) ou [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="01fb8-125">For more information, see [bcp Utility](../../tools/bcp-utility.md), [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql), or [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="01fb8-126">Vous pouvez également spécifier le formatage par champ dans un fichier de format.</span><span class="sxs-lookup"><span data-stu-id="01fb8-126">Alternatively, you can specify formatting on a per-field basis in a format file.</span></span> <span data-ttu-id="01fb8-127">Pour plus d’informations, consultez [Fichiers de format pour l’importation ou l’exportation de données &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="01fb8-127">For more information, see [Format Files for Importing or Exporting Data &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="01fb8-128">Exemples</span><span class="sxs-lookup"><span data-stu-id="01fb8-128">Examples</span></span>  
 <span data-ttu-id="01fb8-129">Les exemples ci-après indiquent comment exporter en bloc des données au format natif par le biais de **bcp** , et importer en bloc ces mêmes données à l’aide de BULK INSERT.</span><span class="sxs-lookup"><span data-stu-id="01fb8-129">The following examples demonstrate how to bulk export native data using **bcp** and bulk import the same data using BULK INSERT.</span></span>  
  
### <a name="sample-table"></a><span data-ttu-id="01fb8-130">Exemple de table</span><span class="sxs-lookup"><span data-stu-id="01fb8-130">Sample Table</span></span>  
 <span data-ttu-id="01fb8-131">Les exemples utilisent une table nommée **myTestUniNativeData**, qui doit être créée dans l’exemple de base de données **AdventureWorks** sous le schéma **dbo**.</span><span class="sxs-lookup"><span data-stu-id="01fb8-131">The examples require that a table named **myTestUniNativeData** table be created in the **AdventureWorks** sample database under the **dbo** schema.</span></span> <span data-ttu-id="01fb8-132">Avant de commencer, vous devez créer cette base de données.</span><span class="sxs-lookup"><span data-stu-id="01fb8-132">Before you can run the examples, you must create this table.</span></span> <span data-ttu-id="01fb8-133">Dans l'Éditeur de requête [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], exécutez :</span><span class="sxs-lookup"><span data-stu-id="01fb8-133">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
CREATE TABLE myTestUniNativeData (  
   Col1 smallint,  
   Col2 nvarchar(50),  
   Col3 nvarchar(50)  
   );   
```  
  
 <span data-ttu-id="01fb8-134">Pour remplir cette table et afficher le contenu résultant, exécutez les instructions suivantes :</span><span class="sxs-lookup"><span data-stu-id="01fb8-134">To populate this table and view the resulting contents execute the following statements:</span></span>  
  
```  
INSERT INTO myTestUniNativeData(Col1,Col2,Col3)  
   VALUES(1,'DataField2','DataField3');  
INSERT INTO myTestUniNativeData(Col1,Col2,Col3)  
   VALUES(2,'DataField2','DataField3');  
GO  
SELECT Col1,Col2,Col3 FROM myTestUniNativeData  
  
```  
  
### <a name="using-bcp-to-bulk-export-native-data"></a><span data-ttu-id="01fb8-135">Utilisation de l'utilitaire bcp pour exporter en bloc des données au format natif</span><span class="sxs-lookup"><span data-stu-id="01fb8-135">Using bcp to Bulk Export Native Data</span></span>  
 <span data-ttu-id="01fb8-136">Pour exporter des données de la table vers le fichier de données, utilisez **bcp** avec l’option **out** et les qualificateurs suivants :</span><span class="sxs-lookup"><span data-stu-id="01fb8-136">To export data from the table to the data file, use **bcp** with the **out** option and the following qualifiers:</span></span>  
  
|<span data-ttu-id="01fb8-137">Qualificateurs</span><span class="sxs-lookup"><span data-stu-id="01fb8-137">Qualifiers</span></span>|<span data-ttu-id="01fb8-138">Description</span><span class="sxs-lookup"><span data-stu-id="01fb8-138">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="01fb8-139">**-N**</span><span class="sxs-lookup"><span data-stu-id="01fb8-139">**-N**</span></span>|<span data-ttu-id="01fb8-140">Spécifie les types de données natifs.</span><span class="sxs-lookup"><span data-stu-id="01fb8-140">Specifies native data types.</span></span>|  
|<span data-ttu-id="01fb8-141">**-T**</span><span class="sxs-lookup"><span data-stu-id="01fb8-141">**-T**</span></span>|<span data-ttu-id="01fb8-142">Spécifie que l'utilitaire **bcp** se connecte à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] avec une connexion approuvée qui utilise la sécurité intégrée.</span><span class="sxs-lookup"><span data-stu-id="01fb8-142">Specifies that the **bcp** utility connects to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with a trusted connection using integrated security.</span></span> <span data-ttu-id="01fb8-143">Si **-T** n’est pas spécifié, vous devez indiquer **-U** et **-P** pour vous connecter.</span><span class="sxs-lookup"><span data-stu-id="01fb8-143">If **-T** is not specified, you need to specify **-U** and **-P** to successfully log in.</span></span>|  
  
 <span data-ttu-id="01fb8-144">Dans l'exemple suivant, des données sont exportées en bloc au format natif de la table `myTestUniNativeData` vers un nouveau fichier de données nommé `myTestUniNativeData-N.Dat`.</span><span class="sxs-lookup"><span data-stu-id="01fb8-144">The following example bulk exports data in native format from the `myTestUniNativeData` table into a new data file named `myTestUniNativeData-N.Dat` data file.</span></span> <span data-ttu-id="01fb8-145">À l'invite de commandes [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, entrez :</span><span class="sxs-lookup"><span data-stu-id="01fb8-145">At the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks..myTestUniNativeData out C:\myTestUniNativeData-N.Dat -N -T  
  
```  
  
### <a name="using-bulk-insert-to-bulk-import-native-data"></a><span data-ttu-id="01fb8-146">Utilisation de BULK INSERT pour importer en bloc des données au format natif</span><span class="sxs-lookup"><span data-stu-id="01fb8-146">Using BULK INSERT to Bulk Import Native Data</span></span>  
 <span data-ttu-id="01fb8-147">L'exemple suivant utilise l'instruction BULK INSERT pour importer les données du fichier de données `myTestUniNativeData-N.Dat` dans la table `myTestUniNativeData`.</span><span class="sxs-lookup"><span data-stu-id="01fb8-147">The following example uses BULK INSERT to import the data in the `myTestUniNativeData-N.Dat` data file into the `myTestUniNativeData` table.</span></span> <span data-ttu-id="01fb8-148">Dans l'Éditeur de requête [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], exécutez :</span><span class="sxs-lookup"><span data-stu-id="01fb8-148">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
BULK INSERT myTestUniNativeData   
    FROM 'C:\myTestUniNativeData-N.Dat'   
   WITH (DATAFILETYPE='widenative');   
GO  
SELECT Col1,Col2,Col3 FROM myTestUniNativeData;  
GO  
  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="01fb8-149">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="01fb8-149">Related Tasks</span></span>  
 <span data-ttu-id="01fb8-150">**Pour utiliser des formats de données pour l'importation ou l'exportation en bloc**</span><span class="sxs-lookup"><span data-stu-id="01fb8-150">**To use data formats for bulk import or bulk export**</span></span>  
  
-   [<span data-ttu-id="01fb8-151">Importer des données au format natif et caractère à partir de versions antérieures de SQL Server</span><span class="sxs-lookup"><span data-stu-id="01fb8-151">Import Native and Character Format Data from Earlier Versions of SQL Server</span></span>](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md)  
  
-   [<span data-ttu-id="01fb8-152">Utiliser le format caractère pour importer ou exporter des données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="01fb8-152">Use Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="01fb8-153">Utiliser le format natif pour importer ou exporter des données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="01fb8-153">Use Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-native-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="01fb8-154">Utiliser le format caractère Unicode pour importer ou exporter des données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="01fb8-154">Use Unicode Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-character-format-to-import-or-export-data-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="01fb8-155">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="01fb8-155">See Also</span></span>  
 <span data-ttu-id="01fb8-156">[Utilitaire bcp](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="01fb8-156">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="01fb8-157">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="01fb8-157">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 <span data-ttu-id="01fb8-158">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="01fb8-158">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 [<span data-ttu-id="01fb8-159">Types de données &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="01fb8-159">Data Types &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/data-types-transact-sql)  
  
  
