---
title: Spécifier le type de stockage de fichiers à l’aide de bcp (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- bcp utility [SQL Server], file storage types
- importing data, file storage types
- native data format [SQL Server]
- file storage types [SQL Server]
- data formats [SQL Server], file storage types
ms.assetid: 85e12df8-1be7-4bdc-aea9-05aade085c06
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c1f3ad2a94ffe3e0f1db19a8e66f85497e7143dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601461"
---
# <a name="specify-file-storage-type-by-using-bcp-sql-server"></a><span data-ttu-id="34797-102">Spécifier le type de stockage de fichiers à l'aide de bcp (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="34797-102">Specify File Storage Type by Using bcp (SQL Server)</span></span>
  <span data-ttu-id="34797-103">Le *type de stockage de fichier* décrit la façon dont les données sont stockées dans le fichier de données.</span><span class="sxs-lookup"><span data-stu-id="34797-103">The *file storage type* describes how data is stored in the data file.</span></span> <span data-ttu-id="34797-104">Les données peuvent être exportées vers un fichier de données au type de table de base de données (format natif), dans sa représentation caractères (format caractères) ou tout type de données pour lesquelles la conversion implicite est prise en charge ; par exemple, en copiant un type de données `smallint` comme `int`.</span><span class="sxs-lookup"><span data-stu-id="34797-104">Data can be exported to a data file as its database table type (native format), in its character representation (character format), or as any data type where implicit conversion is supported; for example, copying a `smallint` as an `int`.</span></span> <span data-ttu-id="34797-105">Les types de données définis par l'utilisateur sont exportés en tant que leurs propres types de base.</span><span class="sxs-lookup"><span data-stu-id="34797-105">User-defined data types are exported as their base types.</span></span>  
  
## <a name="the-bcp-prompt-for-file-storage-type"></a><span data-ttu-id="34797-106">Invite bcp pour le type de stockage de fichier</span><span class="sxs-lookup"><span data-stu-id="34797-106">The bcp Prompt for File Storage Type</span></span>  
 <span data-ttu-id="34797-107">Si une commande **bcp** interactive contient l’option **in** ou **out** sans commutateur de fichier de format ( **-f**) ou sans commutateur de format de données ( **-n**, **-c**, **-w**ou **-N**), la commande demande le type de stockage de fichiers de chaque champ de données, comme suit :</span><span class="sxs-lookup"><span data-stu-id="34797-107">If an interactive **bcp** command contains the **in** or **out** option without either the format file switch (**-f**) or a data-format switch (**-n**, **-c**, **-w**, or **-N**), the command prompts for the file storage type of each data field, as follows:</span></span>  
  
 `Enter the file storage type of field <field_name> [<default>]:`  
  
 <span data-ttu-id="34797-108">Votre réponse à cette invite dépend de la tâche effectuée :</span><span class="sxs-lookup"><span data-stu-id="34797-108">Your response to this prompt depends on the task you perform, as follows:</span></span>  
  
-   <span data-ttu-id="34797-109">Pour exporter des données en bloc d’une instance de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vers un fichier de données au format de stockage le plus compact possible (format de données natif), vous devez accepter les types de stockage de fichier par défaut fournis par l’utilitaire **bcp**.</span><span class="sxs-lookup"><span data-stu-id="34797-109">To bulk export data from an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to a data file in the most compact storage possible (native data format), accept the default file storage types that are provided by **bcp**.</span></span> <span data-ttu-id="34797-110">Pour la liste des types de stockage de fichier natifs, consultez la section « Types de stockage de fichier natifs » plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="34797-110">For a list of the native file storage types, see "Native File Storage Types," later in this topic.</span></span>  
  
-   <span data-ttu-id="34797-111">Pour exporter en bloc des données d'une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vers un fichier de données au format caractère, spécifiez le paramètre `char` comme type de stockage de fichier pour toutes les colonnes de la table.</span><span class="sxs-lookup"><span data-stu-id="34797-111">To bulk export data from an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to a data file in character format, specify `char` as the file storage type for all columns in the table.</span></span>  
  
-   <span data-ttu-id="34797-112">Pour importer en bloc des données dans une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à partir d'un fichier de données, spécifiez le type de stockage de fichier `char` pour les types stockés au format caractère et, pour les données stockées dans le format de type de données natif, spécifiez l'un des types de stockage de fichier appropriés :</span><span class="sxs-lookup"><span data-stu-id="34797-112">To bulk import data to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from a data file, specify the file storage type as `char` for types stored in character format and, for data stored in native data type format, specify one of the file storage types, as appropriate:</span></span>  
  
    |<span data-ttu-id="34797-113">type de stockage de fichier</span><span class="sxs-lookup"><span data-stu-id="34797-113">File storage type</span></span>|<span data-ttu-id="34797-114">Entrer sur la ligne de commande</span><span class="sxs-lookup"><span data-stu-id="34797-114">Enter at command prompt</span></span>|  
    |-----------------------|-----------------------------|  
    |<span data-ttu-id="34797-115">`char`<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="34797-115">`char` <sup>1</sup></span></span>|<span data-ttu-id="34797-116">`c`[`har`]</span><span class="sxs-lookup"><span data-stu-id="34797-116">`c`[`har`]</span></span>|  
    |`varchar`|`c[har]`|  
    |`nchar`|`w`|  
    |`nvarchar`|`w`|  
    |<span data-ttu-id="34797-117">`text`<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="34797-117">`text` <sup>2</sup></span></span>|<span data-ttu-id="34797-118">`T`[`ext`]</span><span class="sxs-lookup"><span data-stu-id="34797-118">`T`[`ext`]</span></span>|  
    |`ntext2`|`W`|  
    |`binary`|`x`|  
    |`varbinary`|`x`|  
    |<span data-ttu-id="34797-119">`image`<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="34797-119">`image` <sup>2</sup></span></span>|<span data-ttu-id="34797-120">`I`[`mage`]</span><span class="sxs-lookup"><span data-stu-id="34797-120">`I`[`mage`]</span></span>|  
    |`datetime`|<span data-ttu-id="34797-121">**d[ate]**</span><span class="sxs-lookup"><span data-stu-id="34797-121">**d[ate]**</span></span>|  
    |`smalldatetime`|`D`|  
    |`time`|`te`|  
    |`date`|`de`|  
    |`datetime2`|`d2`|  
    |`datetimeoffset`|`do`|  
    |`decimal`|`n`|  
    |`numeric`|`n`|  
    |`float`|<span data-ttu-id="34797-122">**f[loat]**</span><span class="sxs-lookup"><span data-stu-id="34797-122">**f[loat]**</span></span>|  
    |`real`|`r`|  
    |`Int`|<span data-ttu-id="34797-123">**i[nt]**</span><span class="sxs-lookup"><span data-stu-id="34797-123">**i[nt]**</span></span>|  
    |`bigint`|`B[igint]`|  
    |`smallint`|<span data-ttu-id="34797-124">**s[mallint]**</span><span class="sxs-lookup"><span data-stu-id="34797-124">**s[mallint]**</span></span>|  
    |`tinyint`|<span data-ttu-id="34797-125">**t[inyint]**</span><span class="sxs-lookup"><span data-stu-id="34797-125">**t[inyint]**</span></span>|  
    |`money`|<span data-ttu-id="34797-126">**m[oney]**</span><span class="sxs-lookup"><span data-stu-id="34797-126">**m[oney]**</span></span>|  
    |`smallmoney`|`M`|  
    |`bit`|`b[it]`|  
    |`uniqueidentifier`|`u`|  
    |`sql_variant`|`V[ariant]`|  
    |`timestamp`|`x`|  
    |<span data-ttu-id="34797-127">`UDT` (type de données défini par l'utilisateur)</span><span class="sxs-lookup"><span data-stu-id="34797-127">`UDT` (a user-defined data type)</span></span>|`U`|  
    |`XML`|`X`|  
  
     <span data-ttu-id="34797-128"><sup>1</sup> l’interaction entre la longueur de champ, la longueur de préfixe et les terminateurs détermine la quantité d’espace de stockage alloué dans un fichier de données pour les données non-caractères exportées en tant que `char` type de stockage de fichier.</span><span class="sxs-lookup"><span data-stu-id="34797-128"><sup>1</sup> The interaction of field length, prefix length, and terminators determines the amount of storage space that is allocated in a data file for noncharacter data that is exported as the `char` file storage type.</span></span>  
  
     <span data-ttu-id="34797-129"><sup>2</sup> les `ntext` `text` types de données, et `image` seront supprimés dans une future version de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="34797-129"><sup>2</sup> The `ntext`, `text`, and `image` data types will be removed in a future version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="34797-130">Dans un nouveau travail de développement, évitez ces types de données et prévoyez la modification des applications qui les utilisent actuellement.</span><span class="sxs-lookup"><span data-stu-id="34797-130">In new development work, avoid using these data types, and plan to modify applications that currently use them.</span></span> <span data-ttu-id="34797-131">Utilisez `nvarchar(max)` , `varchar(max)` et à la `varbinary(max)` place.</span><span class="sxs-lookup"><span data-stu-id="34797-131">Use `nvarchar(max)`, `varchar(max)`, and `varbinary(max)` instead.</span></span>  
  
## <a name="native-file-storage-types"></a><span data-ttu-id="34797-132">Types de stockage de fichier natifs</span><span class="sxs-lookup"><span data-stu-id="34797-132">Native File Storage Types</span></span>  
 <span data-ttu-id="34797-133">Chaque type de stockage de fichier natif est enregistré dans le fichier de format comme un type de données du fichier hôte correspondant.</span><span class="sxs-lookup"><span data-stu-id="34797-133">Each native file storage type is recorded in the format file as a corresponding host file data type.</span></span>  
  
|<span data-ttu-id="34797-134">type de stockage de fichier</span><span class="sxs-lookup"><span data-stu-id="34797-134">File storage type</span></span>|<span data-ttu-id="34797-135">Type de données du fichier hôte</span><span class="sxs-lookup"><span data-stu-id="34797-135">Host file data type</span></span>|  
|-----------------------|-------------------------|  
|<span data-ttu-id="34797-136">`char`<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="34797-136">`char` <sup>1</sup></span></span>|<span data-ttu-id="34797-137">SQLCHAR</span><span class="sxs-lookup"><span data-stu-id="34797-137">SQLCHAR</span></span>|  
|`varchar`|<span data-ttu-id="34797-138">SQLCHAR</span><span class="sxs-lookup"><span data-stu-id="34797-138">SQLCHAR</span></span>|  
|`nchar`|<span data-ttu-id="34797-139">SQLNCHAR</span><span class="sxs-lookup"><span data-stu-id="34797-139">SQLNCHAR</span></span>|  
|`nvarchar`|<span data-ttu-id="34797-140">SQLNCHAR</span><span class="sxs-lookup"><span data-stu-id="34797-140">SQLNCHAR</span></span>|  
|<span data-ttu-id="34797-141">`text`<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="34797-141">`text` <sup>2</sup></span></span>|<span data-ttu-id="34797-142">SQLCHAR</span><span class="sxs-lookup"><span data-stu-id="34797-142">SQLCHAR</span></span>|  
|<span data-ttu-id="34797-143">`ntext`<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="34797-143">`ntext` <sup>2</sup></span></span>|<span data-ttu-id="34797-144">SQLNCHAR</span><span class="sxs-lookup"><span data-stu-id="34797-144">SQLNCHAR</span></span>|  
|`binary`|<span data-ttu-id="34797-145">SQLBINARY</span><span class="sxs-lookup"><span data-stu-id="34797-145">SQLBINARY</span></span>|  
|`varbinary`|<span data-ttu-id="34797-146">SQLBINARY</span><span class="sxs-lookup"><span data-stu-id="34797-146">SQLBINARY</span></span>|  
|<span data-ttu-id="34797-147">`image`<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="34797-147">`image` <sup>2</sup></span></span>|<span data-ttu-id="34797-148">SQLBINARY</span><span class="sxs-lookup"><span data-stu-id="34797-148">SQLBINARY</span></span>|  
|`datetime`|<span data-ttu-id="34797-149">SQLDATETIME</span><span class="sxs-lookup"><span data-stu-id="34797-149">SQLDATETIME</span></span>|  
|`smalldatetime`|<span data-ttu-id="34797-150">SQLDATETIM4</span><span class="sxs-lookup"><span data-stu-id="34797-150">SQLDATETIM4</span></span>|  
|`decimal`|<span data-ttu-id="34797-151">SQLDECIMAL</span><span class="sxs-lookup"><span data-stu-id="34797-151">SQLDECIMAL</span></span>|  
|`numeric`|<span data-ttu-id="34797-152">SQLNUMERIC</span><span class="sxs-lookup"><span data-stu-id="34797-152">SQLNUMERIC</span></span>|  
|`float`|<span data-ttu-id="34797-153">SQLFLT8</span><span class="sxs-lookup"><span data-stu-id="34797-153">SQLFLT8</span></span>|  
|`real`|<span data-ttu-id="34797-154">SQLFLT4</span><span class="sxs-lookup"><span data-stu-id="34797-154">SQLFLT4</span></span>|  
|`int`|<span data-ttu-id="34797-155">SQLINT</span><span class="sxs-lookup"><span data-stu-id="34797-155">SQLINT</span></span>|  
|`bigint`|<span data-ttu-id="34797-156">SQLBIGINT</span><span class="sxs-lookup"><span data-stu-id="34797-156">SQLBIGINT</span></span>|  
|`smallint`|<span data-ttu-id="34797-157">SQLSMALLINT</span><span class="sxs-lookup"><span data-stu-id="34797-157">SQLSMALLINT</span></span>|  
|`tinyint`|<span data-ttu-id="34797-158">SQLTINYINT</span><span class="sxs-lookup"><span data-stu-id="34797-158">SQLTINYINT</span></span>|  
|`money`|<span data-ttu-id="34797-159">SQLMONEY</span><span class="sxs-lookup"><span data-stu-id="34797-159">SQLMONEY</span></span>|  
|`smallmoney`|<span data-ttu-id="34797-160">SQLMONEY4</span><span class="sxs-lookup"><span data-stu-id="34797-160">SQLMONEY4</span></span>|  
|`bit`|<span data-ttu-id="34797-161">SQLBIT</span><span class="sxs-lookup"><span data-stu-id="34797-161">SQLBIT</span></span>|  
|`uniqueidentifier`|<span data-ttu-id="34797-162">SQLUNIQUEID</span><span class="sxs-lookup"><span data-stu-id="34797-162">SQLUNIQUEID</span></span>|  
|`sql_variant`|<span data-ttu-id="34797-163">SQLVARIANT</span><span class="sxs-lookup"><span data-stu-id="34797-163">SQLVARIANT</span></span>|  
|`timestamp`|<span data-ttu-id="34797-164">SQLBINARY</span><span class="sxs-lookup"><span data-stu-id="34797-164">SQLBINARY</span></span>|  
|<span data-ttu-id="34797-165">UDT (type de données défini par l'utilisateur)</span><span class="sxs-lookup"><span data-stu-id="34797-165">UDT (a user-defined data type)</span></span>|<span data-ttu-id="34797-166">SQLUDT</span><span class="sxs-lookup"><span data-stu-id="34797-166">SQLUDT</span></span>|  
  
 <span data-ttu-id="34797-167"><sup>1</sup> les fichiers de données qui sont stockés au format caractère utilisent `char` comme type de stockage de fichier.</span><span class="sxs-lookup"><span data-stu-id="34797-167"><sup>1</sup> Data files that are stored in character format use `char` as the file storage type.</span></span> <span data-ttu-id="34797-168">Par conséquent, pour les fichiers de données de type caractère, SQLCHAR est le seul type de données qui apparaît dans un fichier de format.</span><span class="sxs-lookup"><span data-stu-id="34797-168">Therefore, for character data files, SQLCHAR is the only data type that appears in a format file.</span></span>  
  
 <span data-ttu-id="34797-169"><sup>2</sup> vous ne pouvez pas importer des données en bloc dans des `text` `ntext` colonnes, et `image` qui ont des valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="34797-169"><sup>2</sup> You cannot bulk import data into `text`, `ntext`, and `image` columns that have DEFAULT values.</span></span>  
  
## <a name="additional-considerations-for-file-storage-types"></a><span data-ttu-id="34797-170">Observations supplémentaires concernant les types de stockage de fichier</span><span class="sxs-lookup"><span data-stu-id="34797-170">Additional Considerations for File Storage Types</span></span>  
 <span data-ttu-id="34797-171">Lorsque vous exportez des données en bloc à partir d'une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vers un fichier de données :</span><span class="sxs-lookup"><span data-stu-id="34797-171">When you bulk export data from an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to a data file:</span></span>  
  
-   <span data-ttu-id="34797-172">Vous pouvez toujours spécifier `char` comme type de stockage de fichier.</span><span class="sxs-lookup"><span data-stu-id="34797-172">You can always specify `char` as the file storage type.</span></span>  
  
-   <span data-ttu-id="34797-173">Si vous entrez un type de stockage de fichier qui représente une conversion implicite non valide, **BCP** échoue. par exemple, bien que vous puissiez spécifier `int` pour des `smallint` données, si vous spécifiez `smallint` pour des `int` données, des erreurs de dépassement de capacité se produisent.</span><span class="sxs-lookup"><span data-stu-id="34797-173">If you enter a file storage type that represents an invalid implicit conversion, **bcp** fails; for example, though you can specify `int` for `smallint` data, if you specify `smallint` for `int` data, overflow errors result.</span></span>  
  
-   <span data-ttu-id="34797-174">Lorsque des types de données autres que des caractères tels que `float`, `money`, `datetime` ou `int` sont stockés avec leurs types de base de données, les données sont écrites dans le fichier de données au format natif de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="34797-174">When noncharacter data types such as `float`, `money`, `datetime`, or `int` are stored as their database types, the data is written to the data file in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native format.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="34797-175">Après avoir indiqué de façon interactive tous les champs d’une commande **bcp**, cette dernière vous demande de sauvegarder vos réponses dans un fichier de format autre que XML pour chacun des champs fournis.</span><span class="sxs-lookup"><span data-stu-id="34797-175">After you interactively specify all of the fields in a **bcp** command, the command prompts you save your responses for each field in a non-XML format file.</span></span> <span data-ttu-id="34797-176">Pour plus d’informations sur les fichiers de format non-XML, consultez [Fichiers de format non-XML &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="34797-176">For more information on non-XML format files, see [Non-XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34797-177">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="34797-177">See Also</span></span>  
 <span data-ttu-id="34797-178">[Utilitaire bcp](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="34797-178">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="34797-179">[Types de données &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="34797-179">[Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span></span>  
 <span data-ttu-id="34797-180">[Spécifier la longueur des champs au moyen de bcp &#40;SQL Server&#41;](specify-field-length-by-using-bcp-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="34797-180">[Specify Field Length by Using bcp &#40;SQL Server&#41;](specify-field-length-by-using-bcp-sql-server.md) </span></span>  
 <span data-ttu-id="34797-181">[Spécifier des indicateurs de fin de champ et de fin de ligne &#40;SQL Server&#41;](specify-field-and-row-terminators-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="34797-181">[Specify Field and Row Terminators &#40;SQL Server&#41;](specify-field-and-row-terminators-sql-server.md) </span></span>  
 [<span data-ttu-id="34797-182">Spécifier une longueur de préfixe dans des fichiers de données à l’aide de bcp &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="34797-182">Specify Prefix Length in Data Files by Using bcp &#40;SQL Server&#41;</span></span>](specify-prefix-length-in-data-files-by-using-bcp-sql-server.md)  
  
  
