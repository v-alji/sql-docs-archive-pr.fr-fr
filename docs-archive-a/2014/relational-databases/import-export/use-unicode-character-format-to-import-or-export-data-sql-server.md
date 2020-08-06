---
title: Utiliser le format caractère Unicode pour importer ou exporter des données (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- data formats [SQL Server], Unicode character
- Unicode [SQL Server], bulk importing and exporting
ms.assetid: 74342a11-c1c0-4746-b482-7f3537744a70
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 520ce1b4eed8dc11d6d3fe038969257aea1e90fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708392"
---
# <a name="use-unicode-character-format-to-import-or-export-data-sql-server"></a><span data-ttu-id="11d25-102">Utiliser le format caractère Unicode pour importer ou exporter des données (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="11d25-102">Use Unicode Character Format to Import or Export Data (SQL Server)</span></span>
  <span data-ttu-id="11d25-103">Le format caractère Unicode est recommandé pour le transfert en bloc de données entre plusieurs instances de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à l'aide d'un fichier de données qui contient des caractères étendus ou DBCS.</span><span class="sxs-lookup"><span data-stu-id="11d25-103">Unicode character format is recommended for bulk transfer of data between multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using a data file that contains extended/DBCS characters.</span></span> <span data-ttu-id="11d25-104">Le format de données caractère Unicode permet d'exporter des données depuis un serveur à l'aide d'une page de codes différente de celle utilisée par le client qui effectue l'opération.</span><span class="sxs-lookup"><span data-stu-id="11d25-104">The Unicode character data format allows data to be exported from a server by using a code page that differs from the code page used by the client that is performing the operation.</span></span> <span data-ttu-id="11d25-105">Dans ces cas, l'utilisation du format caractère Unicode présente les avantages suivants :</span><span class="sxs-lookup"><span data-stu-id="11d25-105">In such cases, use of Unicode character format has the following advantages:</span></span>  
  
-   <span data-ttu-id="11d25-106">Si les données sources et de destination sont de types de données Unicode, l'utilisation du format caractère Unicode conserve toutes les données caractère.</span><span class="sxs-lookup"><span data-stu-id="11d25-106">If the source and destination data are Unicode data types, use of Unicode character format preserves all of the character data.</span></span>  
  
-   <span data-ttu-id="11d25-107">Si les données sources et de destination ne sont pas de types de données Unicode, l'utilisation du format caractère Unicode réduit au minimum la perte de caractères étendus dans les données sources qui ne peuvent pas être représentées sur la destination.</span><span class="sxs-lookup"><span data-stu-id="11d25-107">if the source and destination data are not Unicode data types, use of Unicode character format minimizes the loss of extended characters in the source data that cannot be represented at the destination.</span></span>  
  
 <span data-ttu-id="11d25-108">Les fichiers de données de format caractère Unicode respectent les conventions pour les fichiers Unicode.</span><span class="sxs-lookup"><span data-stu-id="11d25-108">Unicode character format data files follow the conventions for Unicode files.</span></span> <span data-ttu-id="11d25-109">Les deux premiers octets du fichier sont des nombres hexadécimaux (0xFFFE).</span><span class="sxs-lookup"><span data-stu-id="11d25-109">The first two bytes of the file are hexadecimal numbers, 0xFFFE.</span></span> <span data-ttu-id="11d25-110">Ces octets sont utilisés comme indicateurs de l'ordre des octets, précisant si l'octet de poids fort est enregistré en premier ou en dernier dans le fichier.</span><span class="sxs-lookup"><span data-stu-id="11d25-110">These bytes serve as byte-order marks, specifying whether the high-order byte is stored first or last in the file.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="11d25-111">Pour qu'un fichier de format fonctionne avec un fichier de données de caractères Unicode, tous les champs d'entrée doivent être des chaînes de texte Unicode (autrement dit, des chaînes Unicode de taille fixe ou terminées par un caractère).</span><span class="sxs-lookup"><span data-stu-id="11d25-111">For a format file to work with a Unicode character data file, all the input fields must be Unicode text strings (that is, either fixed-size or character-terminated Unicode strings).</span></span>  
  
 <span data-ttu-id="11d25-112">Les données `sql_variant` stockées dans un fichier de données de format caractère Unicode fonctionnent comme dans un fichier de données de format caractère, à la différence que les données sont stockées en tant que données `nchar` et non pas `char`.</span><span class="sxs-lookup"><span data-stu-id="11d25-112">The `sql_variant` data that is stored in a Unicode character-format data file operates in the same way it operates in a character-format data file, except that the data is stored as `nchar` instead of `char` data.</span></span> <span data-ttu-id="11d25-113">Pour plus d’informations sur le format caractère, consultez [Prise en charge d’Unicode et du classement](../collations/collation-and-unicode-support.md).</span><span class="sxs-lookup"><span data-stu-id="11d25-113">For more information about character format, see [Collation and Unicode Support](../collations/collation-and-unicode-support.md).</span></span>  
  
 <span data-ttu-id="11d25-114">Pour utiliser un indicateur de fin de champ ou de ligne autre que l’indicateur par défaut du format caractère Unicode, consultez [Spécifier des indicateurs de fin de champ et de fin de ligne &#40;SQL Server&#41;](specify-field-and-row-terminators-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="11d25-114">To use a field or row terminator other than the default that is provided with Unicode character format, see [Specify Field and Row Terminators &#40;SQL Server&#41;](specify-field-and-row-terminators-sql-server.md).</span></span>  
  
## <a name="command-options-for-unicode-character-format"></a><span data-ttu-id="11d25-115">Options de commande du format caractère Unicode</span><span class="sxs-lookup"><span data-stu-id="11d25-115">Command Options for Unicode Character Format</span></span>  
 <span data-ttu-id="11d25-116">Vous pouvez importer des données au format caractère Unicode dans une table à l’aide de la commande **BCP**, Bulk Insert ou Insert... SELECT \* FROM OPENROWSET (BULK...). Pour une commande **BCP** ou une instruction BULK INSERT, vous pouvez spécifier le format de données sur la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="11d25-116">You can import Unicode character format data into a table using **bcp**, BULK INSERT or INSERT ... SELECT \* FROM OPENROWSET(BULK...). For a **bcp** command or BULK INSERT statement, you can specify the data format on the command line.</span></span> <span data-ttu-id="11d25-117">Pour une instruction INSERT... SELECT \* FROM OPENROWSET(BULK...), vous devez spécifier le format de données dans un fichier de format.</span><span class="sxs-lookup"><span data-stu-id="11d25-117">For an INSERT ... SELECT \* FROM OPENROWSET(BULK...) statement, you must specify the data format in a format file.</span></span>  
  
 <span data-ttu-id="11d25-118">Le format caractère Unicode est pris en charge par les options de ligne de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="11d25-118">Unicode character format is supported by the following command line options:</span></span>  
  
|<span data-ttu-id="11d25-119">Commande</span><span class="sxs-lookup"><span data-stu-id="11d25-119">Command</span></span>|<span data-ttu-id="11d25-120">Option</span><span class="sxs-lookup"><span data-stu-id="11d25-120">Option</span></span>|<span data-ttu-id="11d25-121">Description</span><span class="sxs-lookup"><span data-stu-id="11d25-121">Description</span></span>|  
|-------------|------------|-----------------|  
|<span data-ttu-id="11d25-122">**bcp**</span><span class="sxs-lookup"><span data-stu-id="11d25-122">**bcp**</span></span>|<span data-ttu-id="11d25-123">**-w**</span><span class="sxs-lookup"><span data-stu-id="11d25-123">**-w**</span></span>|<span data-ttu-id="11d25-124">Utilise le format caractère Unicode.</span><span class="sxs-lookup"><span data-stu-id="11d25-124">Uses the Unicode character format.</span></span>|  
|<span data-ttu-id="11d25-125">BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="11d25-125">BULK INSERT</span></span>|<span data-ttu-id="11d25-126">DATAFILETYPE **= '** widechar **'**</span><span class="sxs-lookup"><span data-stu-id="11d25-126">DATAFILETYPE **='** widechar **'**</span></span>|<span data-ttu-id="11d25-127">Utilise le format caractère Unicode lors de l'importation de données en bloc.</span><span class="sxs-lookup"><span data-stu-id="11d25-127">Uses Unicode character format when bulk importing data.</span></span>|  
  
 <span data-ttu-id="11d25-128">Pour plus d’informations, consultez [Utilitaire bcp](../../tools/bcp-utility.md), [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) ou [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="11d25-128">For more information, see [bcp Utility](../../tools/bcp-utility.md), [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql), or [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="11d25-129">Vous pouvez également spécifier le formatage par champ dans un fichier de format.</span><span class="sxs-lookup"><span data-stu-id="11d25-129">Alternatively, you can specify formatting on a per-field basis in a format file.</span></span> <span data-ttu-id="11d25-130">Pour plus d’informations, consultez [Fichiers de format pour l’importation ou l’exportation de données &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="11d25-130">For more information, see [Format Files for Importing or Exporting Data &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="11d25-131">Exemples</span><span class="sxs-lookup"><span data-stu-id="11d25-131">Examples</span></span>  
 <span data-ttu-id="11d25-132">Les exemples suivants montrent comment exporter en bloc des données de caractères Unicode à l’aide de la commande **bcp** et importer en bloc les mêmes données à l’aide de l’instruction BULK INSERT.</span><span class="sxs-lookup"><span data-stu-id="11d25-132">The following examples demonstrate how to bulk export Unicode character data using **bcp** and to bulk import the same data using BULK INSERT.</span></span>  
  
### <a name="sample-table"></a><span data-ttu-id="11d25-133">Exemple de table</span><span class="sxs-lookup"><span data-stu-id="11d25-133">Sample Table</span></span>  
 <span data-ttu-id="11d25-134">Une table nommée `myTestUniCharData` doit être créée dans l'exemple de base de données [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] sous le schéma `dbo` .</span><span class="sxs-lookup"><span data-stu-id="11d25-134">The examples require that a table named `myTestUniCharData` table be created in the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] sample database under the `dbo` schema.</span></span> <span data-ttu-id="11d25-135">Avant de commencer, vous devez créer cette base de données.</span><span class="sxs-lookup"><span data-stu-id="11d25-135">Before you can run the examples, you must create this table.</span></span> <span data-ttu-id="11d25-136">Pour créer cette table, dans l'éditeur de requêtes [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] , exécutez le code suivant :</span><span class="sxs-lookup"><span data-stu-id="11d25-136">To create this table, in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
CREATE TABLE myTestUniCharData (  
   Col1 smallint,  
   Col2 nvarchar(50),  
   Col3 nvarchar(50)  
   );   
```  
  
 <span data-ttu-id="11d25-137">Pour remplir cette table et afficher le contenu résultant, exécutez les instructions suivantes :</span><span class="sxs-lookup"><span data-stu-id="11d25-137">To populate this table and view the resulting contents execute the following statements:</span></span>  
  
```  
INSERT INTO myTestUniCharData(Col1,Col2,Col3)  
   VALUES(1,'DataField2','DataField3')   
        ,(2,'DataField2','DataField3');  
GO  
SELECT Col1,Col2,Col3 FROM myTestUniCharData;  
  
```  
  
### <a name="using-bcp-to-bulk-export-unicode-character-data"></a><span data-ttu-id="11d25-138">Utilisation de la commande bcp pour exporter en bloc des données caractère Unicode</span><span class="sxs-lookup"><span data-stu-id="11d25-138">Using bcp to Bulk Export Unicode Character Data</span></span>  
 <span data-ttu-id="11d25-139">Pour exporter des données de la table vers le fichier de données, utilisez **bcp** avec l’option **out** et les qualificateurs suivants :</span><span class="sxs-lookup"><span data-stu-id="11d25-139">To export data from the table to the data file, use **bcp** with the **out** option and the following qualifiers:</span></span>  
  
|<span data-ttu-id="11d25-140">Qualificateurs</span><span class="sxs-lookup"><span data-stu-id="11d25-140">Qualifiers</span></span>|<span data-ttu-id="11d25-141">Description</span><span class="sxs-lookup"><span data-stu-id="11d25-141">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="11d25-142">**-w**</span><span class="sxs-lookup"><span data-stu-id="11d25-142">**-w**</span></span>|<span data-ttu-id="11d25-143">Spécifie le format caractère Unicode.</span><span class="sxs-lookup"><span data-stu-id="11d25-143">Specifies Unicode character format.</span></span>|  
|<span data-ttu-id="11d25-144">**-t** `,`</span><span class="sxs-lookup"><span data-stu-id="11d25-144">**-t** `,`</span></span>|<span data-ttu-id="11d25-145">Virgule (`,`) servant d'indicateur de fin de champ.</span><span class="sxs-lookup"><span data-stu-id="11d25-145">Specifies a comma (`,`) as the field terminator.</span></span><br /><br /> <span data-ttu-id="11d25-146">Remarque : la marque de fin de champ par défaut est le caractère Unicode de tabulation (\t).</span><span class="sxs-lookup"><span data-stu-id="11d25-146">Note: The default field terminator is the tab Unicode character (\t).</span></span> <span data-ttu-id="11d25-147">Pour plus d’informations, consultez [Spécifier des indicateurs de fin de champ et de fin de ligne &#40;SQL Server&#41;](specify-field-and-row-terminators-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="11d25-147">For more information, see [Specify Field and Row Terminators &#40;SQL Server&#41;](specify-field-and-row-terminators-sql-server.md).</span></span>|  
|<span data-ttu-id="11d25-148">**-T**</span><span class="sxs-lookup"><span data-stu-id="11d25-148">**-T**</span></span>|<span data-ttu-id="11d25-149">Spécifie que l'utilitaire **bcp** se connecte à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] avec une connexion approuvée qui utilise la sécurité intégrée.</span><span class="sxs-lookup"><span data-stu-id="11d25-149">Specifies that the **bcp** utility connects to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with a trusted connection using integrated security.</span></span> <span data-ttu-id="11d25-150">Si **-T** n’est pas spécifié, vous devez indiquer **-U** et **-P** pour vous connecter.</span><span class="sxs-lookup"><span data-stu-id="11d25-150">If **-T** is not specified, you need to specify **-U** and **-P** to successfully log in.</span></span>|  
  
 <span data-ttu-id="11d25-151">L'exemple suivant exporte en bloc des données au format de caractères Unicode à partir de la table `myTestUniCharData` dans un nouveau fichier de données nommé `myTestUniCharData-w.Dat` qui utilise la virgule (`,`) comme marque de fin de champ.</span><span class="sxs-lookup"><span data-stu-id="11d25-151">The following example bulk exports data in Unicode character format from the `myTestUniCharData` table into a new data file named `myTestUniCharData-w.Dat` data file that uses the comma (`,`) as the field terminator.</span></span> <span data-ttu-id="11d25-152">À l'invite de commandes [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, entrez :</span><span class="sxs-lookup"><span data-stu-id="11d25-152">At the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks2012..myTestUniCharData out C:\myTestUniCharData-w.Dat -w -t, -T  
  
```  
  
### <a name="using-bulk-insert-to-bulk-import-unicode-character-data"></a><span data-ttu-id="11d25-153">Utilisation de l'instruction BULK INSERT pour importer en bloc des données caractère Unicode</span><span class="sxs-lookup"><span data-stu-id="11d25-153">Using BULK INSERT to Bulk Import Unicode Character Data</span></span>  
 <span data-ttu-id="11d25-154">Dans l'exemple ci-dessous, l'instruction `BULK INSERT` est employée pour importer les données du fichier de données `myTestUniCharData-w.Dat` dans la table `myTestUniCharData`.</span><span class="sxs-lookup"><span data-stu-id="11d25-154">The following example uses `BULK INSERT` to import the data in the `myTestUniCharData-w.Dat` data file into the `myTestUniCharData` table.</span></span> <span data-ttu-id="11d25-155">La marque de fin de champ autre que celle par défaut (`,`) doit être déclarée dans l'instruction.</span><span class="sxs-lookup"><span data-stu-id="11d25-155">The nondefault field terminator (`,`) must be declared in the statement.</span></span> <span data-ttu-id="11d25-156">Dans l'Éditeur de requête [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], exécutez :</span><span class="sxs-lookup"><span data-stu-id="11d25-156">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
BULK INSERT myTestUniCharData   
   FROM 'C:\myTestUniCharData-w.Dat'   
   WITH (  
      DATAFILETYPE='widechar',  
      FIELDTERMINATOR=','  
   );   
GO  
SELECT Col1,Col2,Col3 FROM myTestUniCharData;  
GO  
  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="11d25-157">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="11d25-157">Related Tasks</span></span>  
 <span data-ttu-id="11d25-158">**Pour utiliser des formats de données pour l'importation ou l'exportation en bloc**</span><span class="sxs-lookup"><span data-stu-id="11d25-158">**To use data formats for bulk import or bulk export**</span></span>  
  
-   [<span data-ttu-id="11d25-159">Importer des données au format natif et caractère à partir de versions antérieures de SQL Server</span><span class="sxs-lookup"><span data-stu-id="11d25-159">Import Native and Character Format Data from Earlier Versions of SQL Server</span></span>](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md)  
  
-   [<span data-ttu-id="11d25-160">Utiliser le format caractère pour importer ou exporter des données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="11d25-160">Use Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="11d25-161">Utiliser le format natif pour importer ou exporter des données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="11d25-161">Use Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-native-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="11d25-162">Utiliser le format natif Unicode pour importer ou exporter des données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="11d25-162">Use Unicode Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-native-format-to-import-or-export-data-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="11d25-163">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="11d25-163">See Also</span></span>  
 <span data-ttu-id="11d25-164">[Utilitaire bcp](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="11d25-164">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="11d25-165">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="11d25-165">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 <span data-ttu-id="11d25-166">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="11d25-166">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 <span data-ttu-id="11d25-167">[Types de données &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="11d25-167">[Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span></span>  
 [<span data-ttu-id="11d25-168">Prise en charge d'Unicode et du classement</span><span class="sxs-lookup"><span data-stu-id="11d25-168">Collation and Unicode Support</span></span>](../collations/collation-and-unicode-support.md)  
  
  
