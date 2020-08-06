---
title: Utiliser le format natif pour importer ou exporter des données (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- native data format [SQL Server]
- data formats [SQL Server], native
ms.assetid: eb279b2f-0f1f-428f-9b8f-2a7fc495b79f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ab42ba3eb6468aac3da2fa780d371818c8776690
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708396"
---
# <a name="use-native-format-to-import-or-export-data-sql-server"></a><span data-ttu-id="dc392-102">Utiliser le format natif pour importer ou exporter des données (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="dc392-102">Use Native Format to Import or Export Data (SQL Server)</span></span>
  <span data-ttu-id="dc392-103">Il est recommandé d'utiliser le format natif lorsque vous transférez des données en bloc entre plusieurs instances de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] au moyen d'un fichier de données qui ne contient pas de caractères appartenant à un jeu de caractères étendus/codés sur deux octets (DBCS).</span><span class="sxs-lookup"><span data-stu-id="dc392-103">Native format is recommended when you bulk transfer data between multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using a data file that does not contain any extended/double-byte character set (DBCS) characters.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dc392-104">Pour transférer des données en bloc entre plusieurs instances de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] au moyen d'un fichier de données qui contient des caractères appartenant à un jeu de caractères étendus/codés sur deux octets, utilisez de préférence le format natif Unicode.</span><span class="sxs-lookup"><span data-stu-id="dc392-104">To bulk transfer data between multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using a data file that contains extended or DBCS characters, you should use the Unicode native format.</span></span> <span data-ttu-id="dc392-105">Pour plus d’informations, consultez [Utiliser le format natif Unicode pour importer ou exporter des données &#40;SQL Server&#41;](use-unicode-native-format-to-import-or-export-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="dc392-105">For more information, see [Use Unicode Native Format to Import or Export Data &#40;SQL Server&#41;](use-unicode-native-format-to-import-or-export-data-sql-server.md).</span></span>  
  
 <span data-ttu-id="dc392-106">Le format natif préserve les types de données native d'une base de données.</span><span class="sxs-lookup"><span data-stu-id="dc392-106">Native format maintains the native data types of a database.</span></span> <span data-ttu-id="dc392-107">Il est destiné aux transferts de données à haute vitesse entre des tables [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dc392-107">Native format is intended for high-speed data transfer of data between [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tables.</span></span> <span data-ttu-id="dc392-108">Si vous utilisez un fichier de format, les tables source et cible ne doivent pas nécessairement être identiques.</span><span class="sxs-lookup"><span data-stu-id="dc392-108">If you use a format file, the source and target tables do not need to be identical.</span></span> <span data-ttu-id="dc392-109">Le transfert de données se déroule en deux étapes :</span><span class="sxs-lookup"><span data-stu-id="dc392-109">The data transfer involves two steps:</span></span>  
  
1.  <span data-ttu-id="dc392-110">exportation en bloc des données d'une table source vers un fichier de données ;</span><span class="sxs-lookup"><span data-stu-id="dc392-110">Bulk exporting the data from a source table into a data file</span></span>  
  
2.  <span data-ttu-id="dc392-111">importation en bloc des données d'un fichier de données vers la table cible.</span><span class="sxs-lookup"><span data-stu-id="dc392-111">Bulk importing the data from the data file into the target table</span></span>  
  
 <span data-ttu-id="dc392-112">L'utilisation d'un format natif entre tables identiques permet de gagner du temps et de l'espace puisque les conversions superflues des types de données à partir de et vers le format caractère sont éliminées.</span><span class="sxs-lookup"><span data-stu-id="dc392-112">The use of native format between identical tables avoids unnecessary conversion of data types to and from character format, saving time and space.</span></span> <span data-ttu-id="dc392-113">Pour atteindre la vitesse de transfert optimale, quelques contrôles sont effectués au niveau du formatage des données.</span><span class="sxs-lookup"><span data-stu-id="dc392-113">To achieve the optimum transfer rate, however, few checks are performed regarding data formatting.</span></span> <span data-ttu-id="dc392-114">Pour empêcher que des problèmes ne surviennent au niveau des données chargées, tenez compte des restrictions suivantes.</span><span class="sxs-lookup"><span data-stu-id="dc392-114">To prevent problems with the loaded data, see the following restrictions list.</span></span>  
  
## <a name="restrictions"></a><span data-ttu-id="dc392-115">Restrictions</span><span class="sxs-lookup"><span data-stu-id="dc392-115">Restrictions</span></span>  
 <span data-ttu-id="dc392-116">Pour importer des données au format natif, veillez à ce que les conditions suivantes soient réunies :</span><span class="sxs-lookup"><span data-stu-id="dc392-116">To import data in native format successfully, ensure that:</span></span>  
  
-   <span data-ttu-id="dc392-117">Le fichier de données doit être au format natif.</span><span class="sxs-lookup"><span data-stu-id="dc392-117">The data file is in native format.</span></span>  
  
-   <span data-ttu-id="dc392-118">Soit la table cible doit être compatible avec le fichier de données (qui doit présenter le nombre voulu de colonnes, avec les mêmes types de données, longueur de colonne, état NULL, etc.), soit vous devez utiliser un fichier de format pour mapper chacun des champs sur sa colonne correspondante.</span><span class="sxs-lookup"><span data-stu-id="dc392-118">Either the target table must be compatible with the data file (having the correct number of columns, data type, length, NULL status, and so forth), or you must use a format file to map each field to its corresponding columns.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="dc392-119">Si vous importez des données d'un fichier qui ne concorde pas avec la table cible, l'importation peut réussir mais les valeurs de données insérées dans la table cible peuvent être incorrectes.</span><span class="sxs-lookup"><span data-stu-id="dc392-119">If you import data from a file that is mismatched with the target table, the import operation might succeed but the data values inserted into the target table are likely to be incorrect.</span></span> <span data-ttu-id="dc392-120">En effet, les données du fichier sont interprétées en se basant sur le format de la table cible.</span><span class="sxs-lookup"><span data-stu-id="dc392-120">This is because the data from the file is interpreted by using the format of the target table.</span></span> <span data-ttu-id="dc392-121">Par conséquent, tout défaut de correspondance entraîne l'insertion de valeurs incorrectes.</span><span class="sxs-lookup"><span data-stu-id="dc392-121">Therefore, any mismatch results in the insertion of incorrect values.</span></span> <span data-ttu-id="dc392-122">Cependant, en aucun cas une telle non-correspondance peut-elle provoquer des incohérences logiques ou physiques dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="dc392-122">However, under no circumstances can such a mismatch cause logical or physical inconsistencies in the database.</span></span>  
  
     <span data-ttu-id="dc392-123">Pour plus d’informations sur l’utilisation de fichiers de format, consultez [Fichiers de format pour l’importation ou l’exportation de données &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="dc392-123">For information on using format files, see [Format Files for Importing or Exporting Data &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span></span>  
  
 <span data-ttu-id="dc392-124">Une importation réussie n'endommage pas la table cible.</span><span class="sxs-lookup"><span data-stu-id="dc392-124">A successful import will not corrupt the target table.</span></span>  
  
## <a name="how-bcp-handles-data-in-native-format"></a><span data-ttu-id="dc392-125">Traitement des données au format natif par l'utilitaire bcp</span><span class="sxs-lookup"><span data-stu-id="dc392-125">How bcp Handles Data in Native Format</span></span>  
 <span data-ttu-id="dc392-126">Cette section comporte des remarques spécifiques liées à la manière dont l'utilitaire **bcp** exporte et importe les données au format natif.</span><span class="sxs-lookup"><span data-stu-id="dc392-126">This section discusses special considerations for how the **bcp** utility exports and imports data in native format.</span></span>  
  
-   <span data-ttu-id="dc392-127">Données non-caractère</span><span class="sxs-lookup"><span data-stu-id="dc392-127">Noncharacter data</span></span>  
  
     <span data-ttu-id="dc392-128">Cet utilitaire emploie le format de données binaires interne de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour écrire des données non-caractère d'une table vers un fichier de données.</span><span class="sxs-lookup"><span data-stu-id="dc392-128">The bcp utility uses the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] internal binary data format to write noncharacter data from a table to a data file.</span></span>  
  
-   <span data-ttu-id="dc392-129">Données `char` ou `varchar`</span><span class="sxs-lookup"><span data-stu-id="dc392-129">`char` or `varchar` data</span></span>  
  
     <span data-ttu-id="dc392-130">Au début de chaque `char` champ ou `varchar` , **BCP** ajoute la longueur du préfixe.</span><span class="sxs-lookup"><span data-stu-id="dc392-130">At the beginning of each `char` or `varchar` field, **bcp** adds the prefix length.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="dc392-131">Lorsque le mode natif est utilisé, par défaut, l’utilitaire **BCP** convertit les caractères de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en caractères OEM avant de les copier dans un fichier de données.</span><span class="sxs-lookup"><span data-stu-id="dc392-131">When native mode is used, by default, the **bcp** utility converts characters from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to OEM characters before it copies them to a data file.</span></span> <span data-ttu-id="dc392-132">L’utilitaire **BCP** convertit les caractères d’un fichier de données en caractères ANSI avant de les importer en bloc dans une [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span><span class="sxs-lookup"><span data-stu-id="dc392-132">The **bcp** utility converts characters from a data file to ANSI characters before it bulk imports them into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span> <span data-ttu-id="dc392-133">Au cours de ces conversions, il est possible que des données caractères étendus soient perdues.</span><span class="sxs-lookup"><span data-stu-id="dc392-133">During these conversions, extended character data can be lost.</span></span> <span data-ttu-id="dc392-134">Dans le cas de caractères étendus, vous devez soit utiliser le format natif Unicode, soit spécifier une page de codes.</span><span class="sxs-lookup"><span data-stu-id="dc392-134">For extended characters, either use Unicode native format or specify a code page.</span></span>  
  
-   <span data-ttu-id="dc392-135">Données `sql_variant`</span><span class="sxs-lookup"><span data-stu-id="dc392-135">`sql_variant` data</span></span>  
  
     <span data-ttu-id="dc392-136">Si des données `sql_variant` sont stockées en tant que SQLVARIANT dans un fichier de données au format natif, elles conservent l'ensemble de leurs caractéristiques.</span><span class="sxs-lookup"><span data-stu-id="dc392-136">If `sql_variant` data is stored as a SQLVARIANT in a native-format data file, the data maintains all of its characteristics.</span></span> <span data-ttu-id="dc392-137">Les métadonnées qui enregistrent le type de données de chaque valeur de données sont stockées en même temps que celle-ci.</span><span class="sxs-lookup"><span data-stu-id="dc392-137">The metadata that records the data type of each data value is stored along with the data value.</span></span> <span data-ttu-id="dc392-138">Elles sont employées pour recréer la valeur de données avec le même type de données dans une colonne `sql_variant` de destination.</span><span class="sxs-lookup"><span data-stu-id="dc392-138">This metadata is used to re-create the data value with the same data type in a destination `sql_variant` column.</span></span>  
  
     <span data-ttu-id="dc392-139">Si le type de données de la colonne de destination n'est pas `sql_variant`, chaque valeur de données est convertie au type de données de la colonne de destination, suivant les règles normales de la conversion implicite de données.</span><span class="sxs-lookup"><span data-stu-id="dc392-139">If the data type of the destination column is not `sql_variant`, each data value is converted to the data type of the destination column, following the normal rules of implicit data conversion.</span></span> <span data-ttu-id="dc392-140">Si une erreur survient pendant la conversion des données, le traitement actif est annulé.</span><span class="sxs-lookup"><span data-stu-id="dc392-140">If an error occurs during data conversion, the current batch is rolled back.</span></span> <span data-ttu-id="dc392-141">Toute valeur `char` ou `varchar` transférée entre des colonnes `sql_variant` peut faire l'objet de problèmes de conversion des pages de codes.</span><span class="sxs-lookup"><span data-stu-id="dc392-141">Any `char` and `varchar` values that are transferred between `sql_variant` columns may have code page conversion issues.</span></span>  
  
     <span data-ttu-id="dc392-142">Pour plus d’informations sur la conversion de données, consultez [Conversion de types de données &#40;moteur de base de données&#41;](/sql/t-sql/data-types/data-type-conversion-database-engine).</span><span class="sxs-lookup"><span data-stu-id="dc392-142">For more information about data conversion, see [Data Type Conversion &#40;Database Engine&#41;](/sql/t-sql/data-types/data-type-conversion-database-engine).</span></span>  
  
## <a name="command-options-for-native-format"></a><span data-ttu-id="dc392-143">Options de commande pour le format natif</span><span class="sxs-lookup"><span data-stu-id="dc392-143">Command Options for Native Format</span></span>  
 <span data-ttu-id="dc392-144">Vous pouvez importer des données au format natif dans une table à l’aide de la commande **BCP**, Bulk Insert ou Insert... SELECT \* FROM OPENROWSET (BULK...). Pour une commande **BCP** ou une instruction BULK INSERT, vous pouvez spécifier le format de données sur la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="dc392-144">You can import native format data into a table using **bcp**, BULK INSERT or INSERT ... SELECT \* FROM OPENROWSET(BULK...). For a **bcp** command or BULK INSERT statement, you can specify the data format on the command line.</span></span> <span data-ttu-id="dc392-145">Pour une instruction INSERT... SELECT \* FROM OPENROWSET(BULK...), vous devez spécifier le format de données dans un fichier de format.</span><span class="sxs-lookup"><span data-stu-id="dc392-145">For an INSERT ... SELECT \* FROM OPENROWSET(BULK...) statement, you must specify the data format in a format file.</span></span>  
  
 <span data-ttu-id="dc392-146">Le format natif est pris en charge par les options de ligne de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="dc392-146">Native format is supported by the following command line options:</span></span>  
  
|<span data-ttu-id="dc392-147">Commande</span><span class="sxs-lookup"><span data-stu-id="dc392-147">Command</span></span>|<span data-ttu-id="dc392-148">Option</span><span class="sxs-lookup"><span data-stu-id="dc392-148">Option</span></span>|<span data-ttu-id="dc392-149">Description</span><span class="sxs-lookup"><span data-stu-id="dc392-149">Description</span></span>|  
|-------------|------------|-----------------|  
|<span data-ttu-id="dc392-150">**bcp**</span><span class="sxs-lookup"><span data-stu-id="dc392-150">**bcp**</span></span>|<span data-ttu-id="dc392-151">**-n**</span><span class="sxs-lookup"><span data-stu-id="dc392-151">**-n**</span></span>|<span data-ttu-id="dc392-152">Fait en sorte que l’utilitaire **BCP** utilise les types de données natifs des données. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="dc392-152">Causes the **bcp** utility to use the native data types of the data.<sup>1</sup></span></span>|  
|<span data-ttu-id="dc392-153">BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="dc392-153">BULK INSERT</span></span>|<span data-ttu-id="dc392-154">DATAFILETYPE **= '** native **'**</span><span class="sxs-lookup"><span data-stu-id="dc392-154">DATAFILETYPE **='** native **'**</span></span>|<span data-ttu-id="dc392-155">Utilise les types de données native ou widenative des données.</span><span class="sxs-lookup"><span data-stu-id="dc392-155">Uses the native or wide native data types of the data.</span></span> <span data-ttu-id="dc392-156">Notez que DATAFILETYPE n'est pas nécessaire si un fichier de format spécifie les types de données.</span><span class="sxs-lookup"><span data-stu-id="dc392-156">Note that DATAFILETYPE is not needed if a format file specifies the data types.</span></span>|  
  
 <span data-ttu-id="dc392-157"><sup>1</sup> pour charger des données natives (**-n**) dans un format compatible avec les versions antérieures des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] clients, utilisez le commutateur **-V** .</span><span class="sxs-lookup"><span data-stu-id="dc392-157"><sup>1</sup> To load native (**-n**) data to a format compatible with earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] clients, use the **-V** switch.</span></span> <span data-ttu-id="dc392-158">Pour plus d’informations, consultez [Importer des données au format natif et caractère à partir de versions antérieures de SQL Server](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="dc392-158">For more information, see [Import Native and Character Format Data from Earlier Versions of SQL Server](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md).</span></span>  
  
 <span data-ttu-id="dc392-159">Pour plus d’informations, consultez [Utilitaire bcp](../../tools/bcp-utility.md), [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) ou [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="dc392-159">For more information, see [bcp Utility](../../tools/bcp-utility.md), [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql), or [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dc392-160">Vous pouvez également spécifier le formatage par champ dans un fichier de format.</span><span class="sxs-lookup"><span data-stu-id="dc392-160">Alternatively, you can specify formatting on a per-field basis in a format file.</span></span> <span data-ttu-id="dc392-161">Pour plus d’informations, consultez [Fichiers de format pour l’importation ou l’exportation de données &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="dc392-161">For more information, see [Format Files for Importing or Exporting Data &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="dc392-162">Exemples</span><span class="sxs-lookup"><span data-stu-id="dc392-162">Examples</span></span>  
 <span data-ttu-id="dc392-163">Les exemples ci-après indiquent comment exporter en bloc des données au format natif par le biais de **bcp** , et importer en bloc ces mêmes données à l’aide de BULK INSERT.</span><span class="sxs-lookup"><span data-stu-id="dc392-163">The following examples demonstrate how to bulk export native data using **bcp** and bulk import the same data using BULK INSERT.</span></span>  
  
### <a name="sample-table"></a><span data-ttu-id="dc392-164">Exemple de table</span><span class="sxs-lookup"><span data-stu-id="dc392-164">Sample Table</span></span>  
 <span data-ttu-id="dc392-165">Une table nommée **myTestNativeData** doit être créée dans l'exemple de base de données **AdventureWorks** sous le schéma **dbo** .</span><span class="sxs-lookup"><span data-stu-id="dc392-165">The examples require that a table named **myTestNativeData** table be created in the **AdventureWorks** sample database under the **dbo** schema.</span></span> <span data-ttu-id="dc392-166">Avant de commencer, vous devez créer cette base de données.</span><span class="sxs-lookup"><span data-stu-id="dc392-166">Before you can run the examples, you must create this table.</span></span> <span data-ttu-id="dc392-167">Dans l'Éditeur de requête [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], exécutez :</span><span class="sxs-lookup"><span data-stu-id="dc392-167">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
CREATE TABLE myTestNativeData (  
   Col1 smallint,  
   Col2 nvarchar(50),  
   Col3 nvarchar(50)  
   );   
```  
  
 <span data-ttu-id="dc392-168">Pour remplir cette table et afficher le contenu résultant, exécutez les instructions suivantes :</span><span class="sxs-lookup"><span data-stu-id="dc392-168">To populate this table and view the resulting contents execute the following statements:</span></span>  
  
```  
INSERT INTO myTestNativeData(Col1,Col2,Col3)  
   VALUES(1,'DataField2','DataField3');  
INSERT INTO myTestNativeData(Col1,Col2,Col3)  
   VALUES(2,'DataField2','DataField3');  
GO  
SELECT Col1,Col2,Col3 FROM myTestNativeData  
  
```  
  
### <a name="using-bcp-to-bulk-export-native-data"></a><span data-ttu-id="dc392-169">Utilisation de l'utilitaire bcp pour exporter en bloc des données au format natif</span><span class="sxs-lookup"><span data-stu-id="dc392-169">Using bcp to Bulk Export Native Data</span></span>  
 <span data-ttu-id="dc392-170">Pour exporter des données de la table vers le fichier de données, utilisez **bcp** avec l’option **out** et les qualificateurs suivants :</span><span class="sxs-lookup"><span data-stu-id="dc392-170">To export data from the table to the data file, use **bcp** with the **out** option and the following qualifiers:</span></span>  
  
|<span data-ttu-id="dc392-171">Qualificateurs</span><span class="sxs-lookup"><span data-stu-id="dc392-171">Qualifiers</span></span>|<span data-ttu-id="dc392-172">Description</span><span class="sxs-lookup"><span data-stu-id="dc392-172">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="dc392-173">**-n**</span><span class="sxs-lookup"><span data-stu-id="dc392-173">**-n**</span></span>|<span data-ttu-id="dc392-174">Spécifie les types de données natifs.</span><span class="sxs-lookup"><span data-stu-id="dc392-174">Specifies native data types.</span></span>|  
|<span data-ttu-id="dc392-175">**-T**</span><span class="sxs-lookup"><span data-stu-id="dc392-175">**-T**</span></span>|<span data-ttu-id="dc392-176">Spécifie que l'utilitaire **bcp** se connecte à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] avec une connexion approuvée qui utilise la sécurité intégrée.</span><span class="sxs-lookup"><span data-stu-id="dc392-176">Specifies that the **bcp** utility connects to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with a trusted connection using integrated security.</span></span> <span data-ttu-id="dc392-177">Si **-T** n’est pas spécifié, vous devez indiquer **-U** et **-P** pour vous connecter.</span><span class="sxs-lookup"><span data-stu-id="dc392-177">If **-T** is not specified, you need to specify **-U** and **-P** to successfully log in.</span></span>|  
  
 <span data-ttu-id="dc392-178">Dans l'exemple suivant, des données sont exportées en bloc au format natif de la table `myTestNativeData` vers un nouveau fichier de données nommé `myTestNativeData-n.Dat`.</span><span class="sxs-lookup"><span data-stu-id="dc392-178">The following example bulk exports data in native format from the `myTestNativeData` table into a new data file named `myTestNativeData-n.Dat` data file.</span></span> <span data-ttu-id="dc392-179">À l'invite de commandes [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, entrez :</span><span class="sxs-lookup"><span data-stu-id="dc392-179">At the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks..myTestNativeData out C:\myTestNativeData-n.Dat -n -T  
  
```  
  
### <a name="using-bulk-insert-to-bulk-import-native-data"></a><span data-ttu-id="dc392-180">Utilisation de BULK INSERT pour importer en bloc des données au format natif</span><span class="sxs-lookup"><span data-stu-id="dc392-180">Using BULK INSERT to Bulk Import Native Data</span></span>  
 <span data-ttu-id="dc392-181">L'exemple suivant utilise l'instruction BULK INSERT pour importer les données du fichier de données `myTestNativeData-n.Dat` dans la table `myTestNativeData`.</span><span class="sxs-lookup"><span data-stu-id="dc392-181">The following example uses BULK INSERT to import the data in the `myTestNativeData-n.Dat` data file into the `myTestNativeData` table.</span></span> <span data-ttu-id="dc392-182">Dans l'Éditeur de requête [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], exécutez :</span><span class="sxs-lookup"><span data-stu-id="dc392-182">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
BULK INSERT myTestNativeData   
    FROM 'C:\myTestNativeData-n.Dat'   
   WITH (DATAFILETYPE='native');   
GO  
SELECT Col1,Col2,Col3 FROM myTestNativeData  
GO  
  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="dc392-183">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="dc392-183">Related Tasks</span></span>  
 <span data-ttu-id="dc392-184">**Pour utiliser des formats de données pour l'importation ou l'exportation en bloc**</span><span class="sxs-lookup"><span data-stu-id="dc392-184">**To use data formats for bulk import or bulk export**</span></span>  
  
-   [<span data-ttu-id="dc392-185">Importer des données au format natif et caractère à partir de versions antérieures de SQL Server</span><span class="sxs-lookup"><span data-stu-id="dc392-185">Import Native and Character Format Data from Earlier Versions of SQL Server</span></span>](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md)  
  
-   [<span data-ttu-id="dc392-186">Utiliser le format caractère pour importer ou exporter des données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="dc392-186">Use Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="dc392-187">Utiliser le format caractère Unicode pour importer ou exporter des données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="dc392-187">Use Unicode Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="dc392-188">Utiliser le format natif Unicode pour importer ou exporter des données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="dc392-188">Use Unicode Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-native-format-to-import-or-export-data-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="dc392-189">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="dc392-189">See Also</span></span>  
 <span data-ttu-id="dc392-190">[Utilitaire bcp](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="dc392-190">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="dc392-191">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="dc392-191">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 <span data-ttu-id="dc392-192">[Types de données &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="dc392-192">[Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span></span>  
 <span data-ttu-id="dc392-193">[sql_variant &#40;Transact-SQL&#41;](/sql/t-sql/data-types/sql-variant-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="dc392-193">[sql_variant &#40;Transact-SQL&#41;](/sql/t-sql/data-types/sql-variant-transact-sql) </span></span>  
 <span data-ttu-id="dc392-194">[Importer des données au format natif et caractère à partir de versions antérieures de SQL Server](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="dc392-194">[Import Native and Character Format Data from Earlier Versions of SQL Server](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md) </span></span>  
 <span data-ttu-id="dc392-195">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="dc392-195">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 [<span data-ttu-id="dc392-196">Utiliser le format natif Unicode pour importer ou exporter des données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="dc392-196">Use Unicode Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-native-format-to-import-or-export-data-sql-server.md)  
  
  
