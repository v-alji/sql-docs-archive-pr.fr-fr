---
title: Importer des données au format natif et caractère à partir de versions antérieures de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- earlier versions [SQL Server], import and export data formats
- -V switch
- data formats [SQL Server], earlier versions
- previous versions [SQL Server], import and export data formats
ms.assetid: e644696f-9017-428e-a5b3-d445d1c630b3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 274c984d6ecec8af8f5bea27496450a45fc2f1df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612331"
---
# <a name="import-native-and-character-format-data-from-earlier-versions-of-sql-server"></a><span data-ttu-id="9febd-102">Importer des données au format natif et caractère à partir de versions antérieures de SQL Server</span><span class="sxs-lookup"><span data-stu-id="9febd-102">Import Native and Character Format Data from Earlier Versions of SQL Server</span></span>
  <span data-ttu-id="9febd-103">Dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], vous pouvez utiliser la commande **bcp** pour importer des données au format natif et caractère à partir de [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]ou [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , à l’aide du commutateur **-V** .</span><span class="sxs-lookup"><span data-stu-id="9febd-103">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], you can use **bcp** to import native and character format data from [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], or [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] by using the **-V** switch.</span></span> <span data-ttu-id="9febd-104">Le commutateur **-V** entraîne l’utilisation par [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] des types de données à partir de la version antérieure spécifiée de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], et le format du fichier de données est identique à celui de cette version antérieure.</span><span class="sxs-lookup"><span data-stu-id="9febd-104">The **-V** switch causes [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] to use data types from the specified earlier version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and the data file format are the same as the format in that earlier version.</span></span>  
  
 <span data-ttu-id="9febd-105">Pour spécifier une version antérieure de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour un fichier de données, utilisez le commutateur **-V** avec l’un des qualificateurs suivants :</span><span class="sxs-lookup"><span data-stu-id="9febd-105">To specify an earlier [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version for a data file, use the **-V** switch with one of the following qualifiers:</span></span>  
  
|<span data-ttu-id="9febd-106">Version de SQL Server</span><span class="sxs-lookup"><span data-stu-id="9febd-106">SQL Server version</span></span>|<span data-ttu-id="9febd-107">Qualificateur</span><span class="sxs-lookup"><span data-stu-id="9febd-107">Qualifier</span></span>|  
|------------------------|---------------|  
|[!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)]|<span data-ttu-id="9febd-108">**-V80**</span><span class="sxs-lookup"><span data-stu-id="9febd-108">**-V80**</span></span>|  
|[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]|<span data-ttu-id="9febd-109">**-V90**</span><span class="sxs-lookup"><span data-stu-id="9febd-109">**-V90**</span></span>|  
|[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]|<span data-ttu-id="9febd-110">**-V100**</span><span class="sxs-lookup"><span data-stu-id="9febd-110">**-V100**</span></span>|  
|[!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]|<span data-ttu-id="9febd-111">**-V 110**</span><span class="sxs-lookup"><span data-stu-id="9febd-111">**-V 110**</span></span>|  
  
## <a name="interpretation-of-data-types"></a><span data-ttu-id="9febd-112">Interprétation des types de données</span><span class="sxs-lookup"><span data-stu-id="9febd-112">Interpretation of Data Types</span></span>  
 [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] <span data-ttu-id="9febd-113">et les versions ultérieures prennent en charge certains nouveaux types.</span><span class="sxs-lookup"><span data-stu-id="9febd-113">and later versions have support for some new types.</span></span> <span data-ttu-id="9febd-114">Pour importer un nouveau type de données dans une version de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] antérieure, ce type de données doit être stocké dans un format lisible par les anciens clients **bcp** .</span><span class="sxs-lookup"><span data-stu-id="9febd-114">When you want to import a new data type into an earlier [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version, the data type must be stored in a format that readable by the older **bcp** clients.</span></span> <span data-ttu-id="9febd-115">Le tableau ci-dessous résume le mode de conversion des nouveaux types de données pour assurer leur compatibilité avec les versions précédentes de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9febd-115">The following table summarizes how the new data types are converted for compatibility with the earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
|<span data-ttu-id="9febd-116">Nouveaux types de données dans SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="9febd-116">New data types in SQL Server 2005</span></span>|<span data-ttu-id="9febd-117">Types de données compatibles dans la version 6*x*</span><span class="sxs-lookup"><span data-stu-id="9febd-117">Compatible data types in version 6*x*</span></span>|<span data-ttu-id="9febd-118">Types de données compatibles dans la version 70</span><span class="sxs-lookup"><span data-stu-id="9febd-118">Compatible data types in version 70</span></span>|<span data-ttu-id="9febd-119">Types de données compatibles dans la version 80</span><span class="sxs-lookup"><span data-stu-id="9febd-119">Compatible data types in version 80</span></span>|  
|---------------------------------------|-------------------------------------------|-----------------------------------------|-----------------------------------------|  
|`bigint`|`decimal`|`decimal`|*|  
|`sql_variant`|`text`|`nvarchar(4000)`|*|  
|`varchar(max)`|`text`|`text`|`text`|  
|`nvarchar(max)`|`ntext`|`ntext`|`ntext`|  
|`varbinary(max)`|`image`|`image`|`image`|  
|<span data-ttu-id="9febd-120">XML</span><span class="sxs-lookup"><span data-stu-id="9febd-120">XML</span></span>|`ntext`|`ntext`|`ntext`|  
|<span data-ttu-id="9febd-121">UDT<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="9febd-121">UDT<sup>1</sup></span></span>|`image`|`image`|`image`|  
  
 <span data-ttu-id="9febd-122">\*Ce type est pris en charge en mode natif.</span><span class="sxs-lookup"><span data-stu-id="9febd-122">\* This type is natively supported.</span></span>  
  
 <span data-ttu-id="9febd-123"><sup>1</sup> UDT indique un type défini par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9febd-123"><sup>1</sup> UDT indicates a user defined type.</span></span>  
  
## <a name="exporting-using--v-80"></a><span data-ttu-id="9febd-124">Exportation à l’aide de -V 80</span><span class="sxs-lookup"><span data-stu-id="9febd-124">Exporting using -V 80</span></span>  
 <span data-ttu-id="9febd-125">Lorsque vous exportez des données en bloc à l’aide du commutateur **-V80** , les données,,, `nvarchar(max)` `varchar(max)` `varbinary(max)` XML et UDT en mode natif sont stockées avec un préfixe à 4 octets, comme `text` `image` `ntext` les données, et, plutôt qu’avec un préfixe de 8 octets, qui est la valeur par défaut pour [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] et les versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="9febd-125">When you bulk export data by using the **-V80** switch, `nvarchar(max)`, `varchar(max)`, `varbinary(max)`, XML, and UDT data in native mode are stored with a 4-byte prefix, like `text`, `image`, and `ntext` data, rather than with an 8-byte prefix, which is the default for [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions.</span></span>  
  
## <a name="copying-date-values"></a><span data-ttu-id="9febd-126">Copie de valeurs de date</span><span class="sxs-lookup"><span data-stu-id="9febd-126">Copying Date Values</span></span>  
 <span data-ttu-id="9febd-127">**bcp** utilise l’API de copie en bloc ODBC.</span><span class="sxs-lookup"><span data-stu-id="9febd-127">**bcp** uses the ODBC bulk copy API.</span></span> <span data-ttu-id="9febd-128">Par conséquent, pour importer des valeurs de date dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], **bcp** utilise le format de date ODBC (*yyyy-mm-dd hh:mm:ss*[ *.f...* ]).</span><span class="sxs-lookup"><span data-stu-id="9febd-128">Therefore, to import date values into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], **bcp** uses the ODBC date format (*yyyy-mm-dd hh:mm:ss*[*.f...*]).</span></span>  
  
 <span data-ttu-id="9febd-129">La commande **BCP** exporte des fichiers de données au format caractère à l’aide du format par défaut ODBC pour les `datetime` `smalldatetime` valeurs et.</span><span class="sxs-lookup"><span data-stu-id="9febd-129">The **bcp** command exports character format data files using the ODBC default format for `datetime` and `smalldatetime` values.</span></span> <span data-ttu-id="9febd-130">Par exemple, une colonne `datetime` contenant la date `12 Aug 1998` est copiée en bloc dans un fichier de données en tant que chaîne de caractères `1998-08-12 00:00:00.000`.</span><span class="sxs-lookup"><span data-stu-id="9febd-130">For example, a `datetime` column containing the date `12 Aug 1998` is bulk copied to a data file as the character string `1998-08-12 00:00:00.000`.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9febd-131">Lorsque vous importez des données dans un `smalldatetime` champ à l’aide de **BCP**, assurez-vous que la valeur de secondes est 00,000 ; sinon, l’opération échouera.</span><span class="sxs-lookup"><span data-stu-id="9febd-131">When importing data into a `smalldatetime` field using **bcp**, be sure the value for seconds is 00.000; otherwise the operation will fail.</span></span> <span data-ttu-id="9febd-132">Le type de données `smalldatetime` ne conserve que les valeurs à la minute la plus proche.</span><span class="sxs-lookup"><span data-stu-id="9febd-132">The `smalldatetime` data type only holds values to the nearest minute.</span></span> <span data-ttu-id="9febd-133">BULK INSERT et INSERT ... SELECT \* FROM OPENROWSET(BULK...) n'échoueront pas dans ce cas, mais tronqueront la valeur des secondes.</span><span class="sxs-lookup"><span data-stu-id="9febd-133">BULK INSERT and INSERT ... SELECT \* FROM OPENROWSET(BULK...) will not fail in this instance but will truncate the seconds value.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="9febd-134">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="9febd-134">Related Tasks</span></span>  
 <span data-ttu-id="9febd-135">**Pour utiliser des formats de données pour l'importation ou l'exportation en bloc**</span><span class="sxs-lookup"><span data-stu-id="9febd-135">**To use data formats for bulk import or bulk export**</span></span>  
  
-   [<span data-ttu-id="9febd-136">Utiliser le format caractère pour importer ou exporter des données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9febd-136">Use Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="9febd-137">Utiliser le format natif pour importer ou exporter des données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9febd-137">Use Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-native-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="9febd-138">Utiliser le format caractère Unicode pour importer ou exporter des données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9febd-138">Use Unicode Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="9febd-139">Utiliser le format natif Unicode pour importer ou exporter des données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9febd-139">Use Unicode Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-native-format-to-import-or-export-data-sql-server.md)  
  
 
  
## <a name="see-also"></a><span data-ttu-id="9febd-140">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9febd-140">See Also</span></span>  
 <span data-ttu-id="9febd-141">[Utilitaire bcp](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="9febd-141">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="9febd-142">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9febd-142">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 <span data-ttu-id="9febd-143">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9febd-143">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 <span data-ttu-id="9febd-144">[Types de données &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9febd-144">[Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span></span>  
 <span data-ttu-id="9febd-145">[Compatibilité descendante du moteur de base de données SQL Server](../../database-engine/sql-server-database-engine-backward-compatibility.md) </span><span class="sxs-lookup"><span data-stu-id="9febd-145">[SQL Server Database Engine Backward Compatibility](../../database-engine/sql-server-database-engine-backward-compatibility.md) </span></span>  
 [<span data-ttu-id="9febd-146">CAST et CONVERT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9febd-146">CAST and CONVERT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/cast-and-convert-transact-sql)  
  
  
