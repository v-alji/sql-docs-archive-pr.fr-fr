---
title: bcp_control | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_control
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_control function
ms.assetid: 32187282-1385-4c52-9134-09f061eb44f5
author: rothja
ms.author: jroth
ms.openlocfilehash: 7ea5d60da8069707a53f3bdf2de53345cd11090f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599985"
---
# <a name="bcp_control"></a><span data-ttu-id="1bb54-102">bcp_control</span><span class="sxs-lookup"><span data-stu-id="1bb54-102">bcp_control</span></span>
  <span data-ttu-id="1bb54-103">Modifie les paramètres par défaut pour différents paramètres de contrôle pour une copie en bloc entre un fichier et [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1bb54-103">Changes the default settings for various control parameters for a bulk copy between a file and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bb54-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="1bb54-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_control (  
HDBC   
hdbc  
,  
INT   
eOption  
,  
void*   
iValue  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="1bb54-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="1bb54-105">Arguments</span></span>  
 <span data-ttu-id="1bb54-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="1bb54-106">*hdbc*</span></span>  
 <span data-ttu-id="1bb54-107">Handle de connexion ODBC compatible avec la copie en bloc.</span><span class="sxs-lookup"><span data-stu-id="1bb54-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="1bb54-108">*eOption*</span><span class="sxs-lookup"><span data-stu-id="1bb54-108">*eOption*</span></span>  
 <span data-ttu-id="1bb54-109">Prend l'une des valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="1bb54-109">Is one of the following:</span></span>  
  
 <span data-ttu-id="1bb54-110">BCPABORT</span><span class="sxs-lookup"><span data-stu-id="1bb54-110">BCPABORT</span></span>  
 <span data-ttu-id="1bb54-111">Arrête une opération de copie en bloc déjà en cours.</span><span class="sxs-lookup"><span data-stu-id="1bb54-111">Stops a bulk-copy operation that is already in progress.</span></span> <span data-ttu-id="1bb54-112">Appelez **bcp_control** avec un *eOption* de BCPABORT à partir d’un autre thread pour arrêter l’exécution d’une opération de copie en bloc.</span><span class="sxs-lookup"><span data-stu-id="1bb54-112">Call **bcp_control** with an *eOption* of BCPABORT from another thread to stop a running bulk copy operation.</span></span> <span data-ttu-id="1bb54-113">Le paramètre *iValue* est ignoré.</span><span class="sxs-lookup"><span data-stu-id="1bb54-113">The *iValue* parameter is ignored.</span></span>  
  
 <span data-ttu-id="1bb54-114">BCPBATCH</span><span class="sxs-lookup"><span data-stu-id="1bb54-114">BCPBATCH</span></span>  
 <span data-ttu-id="1bb54-115">Nombre de lignes par lot.</span><span class="sxs-lookup"><span data-stu-id="1bb54-115">Is the number of rows per batch.</span></span> <span data-ttu-id="1bb54-116">La valeur par défaut est 0, ce qui indique soit que toutes les lignes sont dans une table, lorsque les données sont extraites, soit que toutes les lignes sont dans le fichier des données utilisateur, lorsque les données sont copiées vers un serveur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1bb54-116">The default is 0, which indicates either all rows in a table, when data is being extracted, or all rows in the user data file, when data is being copied to an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="1bb54-117">Une valeur inférieure à 1 rétablit la valeur par défaut de BCPBATCH.</span><span class="sxs-lookup"><span data-stu-id="1bb54-117">A value less than 1 resets BCPBATCH to the default.</span></span>  
  
 <span data-ttu-id="1bb54-118">BCPDELAYREADFMT</span><span class="sxs-lookup"><span data-stu-id="1bb54-118">BCPDELAYREADFMT</span></span>  
 <span data-ttu-id="1bb54-119">Une valeur booléenne, si la valeur est true, provoque la lecture de [bcp_readfmt](bcp-readfmt.md) lors de l’exécution.</span><span class="sxs-lookup"><span data-stu-id="1bb54-119">A Boolean, if set to true, will cause [bcp_readfmt](bcp-readfmt.md) to read at execution.</span></span> <span data-ttu-id="1bb54-120">Si la valeur est false (valeur par défaut), bcp_readfmt lit immédiatement le fichier de format.</span><span class="sxs-lookup"><span data-stu-id="1bb54-120">If false (the default), bcp_readfmt will immediately read the format file.</span></span> <span data-ttu-id="1bb54-121">Une erreur de séquence se produit si BCPDELAYREADFMT a la valeur true et que vous appelez bcp_columns ou bcp_setcolfmt.</span><span class="sxs-lookup"><span data-stu-id="1bb54-121">A sequence error will occur if BCPDELAYREADFMT is true and you call bcp_columns or bcp_setcolfmt.</span></span>  
  
 <span data-ttu-id="1bb54-122">Une erreur de séquence se produira également si vous appelez `bcp_control(hdbc,` BCPDELAYREADFMT `, (void *)FALSE)` après avoir appelé `bcp_control(hdbc,` BCPDELAYREADFMT `, (void *)TRUE)` et bcp_writefmt.</span><span class="sxs-lookup"><span data-stu-id="1bb54-122">A sequence error will also occur if you call `bcp_control(hdbc,` BCPDELAYREADFMT`, (void *)FALSE)` after calling `bcp_control(hdbc,` BCPDELAYREADFMT`, (void *)TRUE)` and bcp_writefmt.</span></span>  
  
 <span data-ttu-id="1bb54-123">Pour plus d’informations, consultez [Découverte des métadonnées](../native-client/features/metadata-discovery.md).</span><span class="sxs-lookup"><span data-stu-id="1bb54-123">For more information, see [Metadata Discovery](../native-client/features/metadata-discovery.md).</span></span>  
  
 <span data-ttu-id="1bb54-124">BCPFILECP</span><span class="sxs-lookup"><span data-stu-id="1bb54-124">BCPFILECP</span></span>  
 <span data-ttu-id="1bb54-125">*iValue* contient le numéro de la page de codes pour le fichier de données.</span><span class="sxs-lookup"><span data-stu-id="1bb54-125">*iValue* contains the number of the code page for the data file.</span></span> <span data-ttu-id="1bb54-126">Vous pouvez spécifier le numéro de la page de codes, par exemple 1252 ou 850, ou l'une de ces valeurs :</span><span class="sxs-lookup"><span data-stu-id="1bb54-126">You can specify the number of the code page, such as 1252 or 850, or one of these values:</span></span>  
  
 <span data-ttu-id="1bb54-127">BCPFILE_ACP : les données du fichier se trouvent dans Microsoft Windows ?</span><span class="sxs-lookup"><span data-stu-id="1bb54-127">BCPFILE_ACP: data in the file is in the Microsoft Windows??</span></span> <span data-ttu-id="1bb54-128">page de codes du client.</span><span class="sxs-lookup"><span data-stu-id="1bb54-128">code page of the client.</span></span>  
  
 <span data-ttu-id="1bb54-129">BCPFILE_OEMCP : les données dans le fichier figurent dans la page de codes OEM du client (valeur par défaut).</span><span class="sxs-lookup"><span data-stu-id="1bb54-129">BCPFILE_OEMCP: data in the file is in the OEM code page of the client (default).</span></span>  
  
 <span data-ttu-id="1bb54-130">BCPFILE_RAW : les données dans le fichier figurent dans la page de codes du serveur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1bb54-130">BCPFILE_RAW: data in the file is in the code page of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="1bb54-131">BCPFILEFMT</span><span class="sxs-lookup"><span data-stu-id="1bb54-131">BCPFILEFMT</span></span>  
 <span data-ttu-id="1bb54-132">Numéro de version du format de fichier de données.</span><span class="sxs-lookup"><span data-stu-id="1bb54-132">The version number of the data file format.</span></span> <span data-ttu-id="1bb54-133">Il peut s’agir de 80 ( [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] ), 90 ( [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] ), 100 ( [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] ou [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] ), 110 ( [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] ) ou 120 ( [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] ).</span><span class="sxs-lookup"><span data-stu-id="1bb54-133">This can be 80 ([!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)]), 90 ([!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]), 100 ([!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] or [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]), 110 ([!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]), or 120 ([!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]).</span></span> <span data-ttu-id="1bb54-134">120 est la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="1bb54-134">120 is the default.</span></span> <span data-ttu-id="1bb54-135">Cela s'avère utile pour exporter et importer des données dans des formats pris en charge par une version antérieure du serveur.</span><span class="sxs-lookup"><span data-stu-id="1bb54-135">This is useful for exporting and importing data in formats that were supported by earlier version of the server.</span></span> <span data-ttu-id="1bb54-136">Par exemple, pour importer des données obtenues à partir d’une colonne de texte d’un [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] serveur dans une colonne **varchar (max)** dans un [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] serveur ou ultérieur, vous devez spécifier 80.</span><span class="sxs-lookup"><span data-stu-id="1bb54-136">For example, to import data that was obtained from a text column in a [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] server into a **varchar(max)** column in a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or later server, you should specify 80.</span></span> <span data-ttu-id="1bb54-137">De même, si vous spécifiez 80 lors de l’exportation de données à partir d’une colonne **varchar (max)** , celles-ci sont enregistrées de la même façon que les colonnes de texte sont enregistrées au [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] format et peuvent être importées dans une colonne de texte d’un [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] serveur.</span><span class="sxs-lookup"><span data-stu-id="1bb54-137">Similarly, if you specify 80 when exporting data from a **varchar(max)** column, it will be saved just like text columns are saved in the [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] format, and can be imported into a text column of a [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] server.</span></span>  
  
 <span data-ttu-id="1bb54-138">BCPFIRST</span><span class="sxs-lookup"><span data-stu-id="1bb54-138">BCPFIRST</span></span>  
 <span data-ttu-id="1bb54-139">Première ligne du fichier de données ou de la table à copier.</span><span class="sxs-lookup"><span data-stu-id="1bb54-139">Is the first row of data to file or table to copy.</span></span> <span data-ttu-id="1bb54-140">La valeur par défaut est 1 ; une valeur inférieure à 1 rétablit la valeur par défaut de cette option.</span><span class="sxs-lookup"><span data-stu-id="1bb54-140">The default is 1; a value less than 1 resets this option to its default.</span></span>  
  
 <span data-ttu-id="1bb54-141">BCPFIRSTEX</span><span class="sxs-lookup"><span data-stu-id="1bb54-141">BCPFIRSTEX</span></span>  
 <span data-ttu-id="1bb54-142">Pour les opérations bcp out, spécifie la première ligne de la table de base de données à copier dans le fichier de données.</span><span class="sxs-lookup"><span data-stu-id="1bb54-142">For BCP out operations, specifies the first row of the database table to copy into the data file.</span></span>  
  
 <span data-ttu-id="1bb54-143">Pour les opérations bcp in, spécifie la première ligne du fichier de données à copier dans la table de base de données.</span><span class="sxs-lookup"><span data-stu-id="1bb54-143">For BCP in operations, specifies the first row of the data file to copy into the database table.</span></span>  
  
 <span data-ttu-id="1bb54-144">Le paramètre *iValue* doit être l’adresse d’un entier 64 bits signé contenant la valeur.</span><span class="sxs-lookup"><span data-stu-id="1bb54-144">The *iValue* parameter is expected to be the address of a signed 64-bit integer containing the value.</span></span> <span data-ttu-id="1bb54-145">La valeur maximale qui peut être passée à BCPFIRSTEX est est 2 ^ 63-1.</span><span class="sxs-lookup"><span data-stu-id="1bb54-145">The maximum value that can be passed to BCPFIRSTEX is 2^63-1.</span></span>  
  
 <span data-ttu-id="1bb54-146">BCPFMTXML</span><span class="sxs-lookup"><span data-stu-id="1bb54-146">BCPFMTXML</span></span>  
 <span data-ttu-id="1bb54-147">Spécifie que le fichier de format généré doit être au format XML.</span><span class="sxs-lookup"><span data-stu-id="1bb54-147">Specifies that the format file generated should be in XML format.</span></span> <span data-ttu-id="1bb54-148">Il est désactivé par défaut.</span><span class="sxs-lookup"><span data-stu-id="1bb54-148">It is off by default.</span></span>  
  
 <span data-ttu-id="1bb54-149">Les fichiers au format XML offrent plus de souplesse, mais aussi quelques contraintes supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="1bb54-149">XML format files provide greater flexibility but with some added constraints.</span></span> <span data-ttu-id="1bb54-150">Par exemple, vous ne pouvez pas spécifier simultanément le préfixe et la terminaison pour un champ, ce qui était possible dans les fichiers de format plus anciens.</span><span class="sxs-lookup"><span data-stu-id="1bb54-150">For example, you can not specify the prefix and terminator for a field simultaneously, which was possible in older format files.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1bb54-151">Les fichiers de format XML ne sont pris en charge que si [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est installé conjointement avec [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="1bb54-151">XML format files are only supported when [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed along with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
 <span data-ttu-id="1bb54-152">BCPHINTS</span><span class="sxs-lookup"><span data-stu-id="1bb54-152">BCPHINTS</span></span>  
 <span data-ttu-id="1bb54-153">*iValue* contient un pointeur de chaîne de caractères SQLTCHAR.</span><span class="sxs-lookup"><span data-stu-id="1bb54-153">*iValue* contains an SQLTCHAR character string pointer.</span></span> <span data-ttu-id="1bb54-154">La chaîne adressée spécifie des indicateurs de traitement de copie en bloc [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou une instruction Transact-SQL qui retourne un jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="1bb54-154">The string addressed specifies either [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] bulk-copy processing hints or a Transact-SQL statement that returns a result set.</span></span> <span data-ttu-id="1bb54-155">Si une instruction Transact-SQL est spécifiée qui retourne plusieurs jeux de résultats, tous les jeux de résultats après le premier sont ignorés.</span><span class="sxs-lookup"><span data-stu-id="1bb54-155">If a Transact-SQL statement is specified that returns more than one result set, all result sets after the first are ignored.</span></span> <span data-ttu-id="1bb54-156">Pour plus d’informations sur les indicateurs de traitement de copie en bloc, consultez [BCP Utility](../../tools/bcp-utility.md).</span><span class="sxs-lookup"><span data-stu-id="1bb54-156">For more information about bulk-copy processing hints, see [bcp Utility](../../tools/bcp-utility.md).</span></span>  
  
 <span data-ttu-id="1bb54-157">BCPKEEPIDENTITY</span><span class="sxs-lookup"><span data-stu-id="1bb54-157">BCPKEEPIDENTITY</span></span>  
 <span data-ttu-id="1bb54-158">Quand *iValue* a la valeur true, spécifie que les fonctions de copie en bloc insèrent des valeurs de données fournies pour les [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] colonnes définies avec une contrainte d’identité.</span><span class="sxs-lookup"><span data-stu-id="1bb54-158">When *iValue* is TRUE, specifies that bulk copy functions insert data values supplied for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] columns defined with an identity constraint.</span></span> <span data-ttu-id="1bb54-159">Le fichier d'entrée doit fournir des valeurs pour les colonnes d'identité.</span><span class="sxs-lookup"><span data-stu-id="1bb54-159">The input file must supply values for the identity columns.</span></span> <span data-ttu-id="1bb54-160">Si cela n'est pas défini, de nouvelles valeurs d'identités sont générées pour les lignes insérées.</span><span class="sxs-lookup"><span data-stu-id="1bb54-160">If this is not set, new identity values are generated for the inserted rows.</span></span> <span data-ttu-id="1bb54-161">Toutes les données présentes dans le fichier pour les colonnes d'identité sont ignorées.</span><span class="sxs-lookup"><span data-stu-id="1bb54-161">Any data present in the file for the identity columns is ignored.</span></span>  
  
 <span data-ttu-id="1bb54-162">BCPKEEPNULLS</span><span class="sxs-lookup"><span data-stu-id="1bb54-162">BCPKEEPNULLS</span></span>  
 <span data-ttu-id="1bb54-163">Spécifie si les valeurs de données vides dans le fichier sont converties en valeurs NULL dans la table [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1bb54-163">Specifies whether empty data values in the file will be converted to NULL values in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span> <span data-ttu-id="1bb54-164">Quand *iValue* a la valeur true, les valeurs vides sont converties en valeurs NULL dans la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span><span class="sxs-lookup"><span data-stu-id="1bb54-164">When *iValue* is TRUE, empty values will be converted to NULL in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span> <span data-ttu-id="1bb54-165">L'option par défaut consiste à convertir les valeurs vides en une valeur par défaut pour la colonne dans la table [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] si une valeur par défaut existe.</span><span class="sxs-lookup"><span data-stu-id="1bb54-165">The default is for empty values to be converted to a default value for the column in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table if a default exists.</span></span>  
  
 <span data-ttu-id="1bb54-166">BCPLAST</span><span class="sxs-lookup"><span data-stu-id="1bb54-166">BCPLAST</span></span>  
 <span data-ttu-id="1bb54-167">Dernière ligne à copier.</span><span class="sxs-lookup"><span data-stu-id="1bb54-167">Is the last row to copy.</span></span> <span data-ttu-id="1bb54-168">L'option par défaut consiste à copier toutes les lignes ; une valeur inférieure à 1 rétablit la valeur par défaut de cette option.</span><span class="sxs-lookup"><span data-stu-id="1bb54-168">The default is to copy all rows; a value less than 1 resets this option to its default.</span></span>  
  
 <span data-ttu-id="1bb54-169">BCPLASTEX</span><span class="sxs-lookup"><span data-stu-id="1bb54-169">BCPLASTEX</span></span>  
 <span data-ttu-id="1bb54-170">Pour les opérations bcp out, spécifie la dernière ligne de la table de base de données à copier dans le fichier de données.</span><span class="sxs-lookup"><span data-stu-id="1bb54-170">For BCP out operations, specifies the last row of the database table to copy into the data file.</span></span>  
  
 <span data-ttu-id="1bb54-171">Pour les opérations bcp in, spécifie la dernière ligne du fichier de données à copier dans la table de base de données.</span><span class="sxs-lookup"><span data-stu-id="1bb54-171">For BCP in operations, specifies the last row of the data file to copy into the database table.</span></span>  
  
 <span data-ttu-id="1bb54-172">Le paramètre *iValue* doit être l’adresse d’un entier 64 bits signé contenant la valeur.</span><span class="sxs-lookup"><span data-stu-id="1bb54-172">The *iValue* parameter is expected to be the address of a signed 64-bit integer containing the value.</span></span> <span data-ttu-id="1bb54-173">La valeur maximale qui peut être passée à BCPLASTEX est 2^63-1.</span><span class="sxs-lookup"><span data-stu-id="1bb54-173">The maximum value that can be passed to BCPLASTEX is 2^63-1.</span></span>  
  
 <span data-ttu-id="1bb54-174">BCPMAXERRS</span><span class="sxs-lookup"><span data-stu-id="1bb54-174">BCPMAXERRS</span></span>  
 <span data-ttu-id="1bb54-175">Nombre d’erreurs autorisées avant l’échec de l’opération de copie en bloc.</span><span class="sxs-lookup"><span data-stu-id="1bb54-175">Is the number of errors allowed before the bulk copy operation fails.</span></span> <span data-ttu-id="1bb54-176">La valeur par défaut est 10 ; une valeur inférieure à 1 rétablit la valeur par défaut de cette option.</span><span class="sxs-lookup"><span data-stu-id="1bb54-176">The default is 10; a value less than 1 resets this option to its default.</span></span> <span data-ttu-id="1bb54-177">La copie en bloc impose 65 535 erreurs au maximum.</span><span class="sxs-lookup"><span data-stu-id="1bb54-177">Bulk copy imposes a maximum of 65,535 errors.</span></span> <span data-ttu-id="1bb54-178">Toute tentative d'attribution d'une valeur supérieure à 65 535 à cette option entraîne l'attribution de la valeur 65 535 à l'option.</span><span class="sxs-lookup"><span data-stu-id="1bb54-178">An attempt to set this option to a value larger than 65,535 results in the option being set to 65,535.</span></span>  
  
 <span data-ttu-id="1bb54-179">BCPODBC</span><span class="sxs-lookup"><span data-stu-id="1bb54-179">BCPODBC</span></span>  
 <span data-ttu-id="1bb54-180">Si la valeur est TRUE, spécifie que les valeurs **DateTime** et **smalldatetime** enregistrées au format caractère utilisent le préfixe et le suffixe de séquence d’échappement d’horodateur ODBC.</span><span class="sxs-lookup"><span data-stu-id="1bb54-180">When TRUE, specifies that **datetime** and **smalldatetime** values saved in character format will use the ODBC timestamp escape sequence prefix and suffix.</span></span> <span data-ttu-id="1bb54-181">L'option BCPODBC s'applique uniquement à BCP_OUT.</span><span class="sxs-lookup"><span data-stu-id="1bb54-181">The BCPODBC option only applies to BCP_OUT.</span></span>  
  
 <span data-ttu-id="1bb54-182">Quand la valeur est FALSe, une valeur **DateTime** représentant le 1er janvier 1997 est convertie en chaîne de caractères : 1997-01-01 00:00:00.000.</span><span class="sxs-lookup"><span data-stu-id="1bb54-182">When FALSE, a **datetime** value representing January 1, 1997 is converted to the character string: 1997-01-01 00:00:00.000.</span></span> <span data-ttu-id="1bb54-183">Si la valeur est TRUE, la même valeur **DateTime** est représentée comme suit : {ts' 1997-01-01 00:00:00.000 '}.</span><span class="sxs-lookup"><span data-stu-id="1bb54-183">When TRUE, the same **datetime** value is represented as: {ts '1997-01-01 00:00:00.000'}.</span></span>  
  
 <span data-ttu-id="1bb54-184">BCPROWCOUNT</span><span class="sxs-lookup"><span data-stu-id="1bb54-184">BCPROWCOUNT</span></span>  
 <span data-ttu-id="1bb54-185">Retourne le nombre de lignes affectées par l'opération BCP en cours (ou la dernière).</span><span class="sxs-lookup"><span data-stu-id="1bb54-185">Returns the number of rows affected by the current (or last) BCP operation.</span></span>  
  
 <span data-ttu-id="1bb54-186">BCPTEXTFILE</span><span class="sxs-lookup"><span data-stu-id="1bb54-186">BCPTEXTFILE</span></span>  
 <span data-ttu-id="1bb54-187">Lorsque la valeur est TRUE, spécifie que le fichier de données est un fichier texte et non un fichier binaire.</span><span class="sxs-lookup"><span data-stu-id="1bb54-187">When TRUE, specifies that the data file is a text file, rather than a binary file.</span></span> <span data-ttu-id="1bb54-188">Si le fichier est un fichier texte, BCP détermine s'il est ou non un fichier Unicode en vérifiant le marqueur d'octet Unicode dans les deux premiers octets du fichier de données.</span><span class="sxs-lookup"><span data-stu-id="1bb54-188">If the file is a text file, BCP determines whether or not it is Unicode by checking the Unicode byte marker in the first two bytes of the data file.</span></span>  
  
 <span data-ttu-id="1bb54-189">BCPUNICODEFILE</span><span class="sxs-lookup"><span data-stu-id="1bb54-189">BCPUNICODEFILE</span></span>  
 <span data-ttu-id="1bb54-190">Lorsque la valeur est TRUE, spécifie que le fichier d'entrée est un fichier Unicode.</span><span class="sxs-lookup"><span data-stu-id="1bb54-190">When TRUE, specifies the input file is a Unicode file.</span></span>  
  
 <span data-ttu-id="1bb54-191">*iValue*</span><span class="sxs-lookup"><span data-stu-id="1bb54-191">*iValue*</span></span>  
 <span data-ttu-id="1bb54-192">Valeur du *eOption*spécifié.</span><span class="sxs-lookup"><span data-stu-id="1bb54-192">Is the value for the specified *eOption*.</span></span> <span data-ttu-id="1bb54-193">*iValue* est une valeur entière (LongLong) transtypée en un pointeur void pour permettre une expansion future vers des valeurs 64 bits.</span><span class="sxs-lookup"><span data-stu-id="1bb54-193">*iValue* is an integer (LONGLONG) value cast to a void pointer to allow for future expansion to 64 bit values.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="1bb54-194">Retours</span><span class="sxs-lookup"><span data-stu-id="1bb54-194">Returns</span></span>  
 <span data-ttu-id="1bb54-195">SUCCEED ou FAIL.</span><span class="sxs-lookup"><span data-stu-id="1bb54-195">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1bb54-196">Notes</span><span class="sxs-lookup"><span data-stu-id="1bb54-196">Remarks</span></span>  
 <span data-ttu-id="1bb54-197">Cette fonction définit différents paramètres de contrôle pour les opérations de copie en bloc, y compris le nombre d'erreurs autorisées avant l'annulation de la copie en bloc, les numéros des première et dernière lignes à copier à partir d'un fichier de données, et la taille du lot.</span><span class="sxs-lookup"><span data-stu-id="1bb54-197">This function sets various control parameters for bulk-copy operations, including the number of errors allowed before canceling a bulk copy, the numbers of the first and last rows to copy from a data file, and the batch size.</span></span>  
  
 <span data-ttu-id="1bb54-198">Cette fonction est également utilisée pour spécifier l'instruction SELECT lors de la copie en bloc à partir du jeu de résultats [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] d'une instruction SELECT.</span><span class="sxs-lookup"><span data-stu-id="1bb54-198">This function is also used to specify the SELECT statement when bulk copying out from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] the result set of a SELECT.</span></span> <span data-ttu-id="1bb54-199">Affectez à *eOption* la valeur valeur BCPHINTS et à *iValue* la valeur d’un pointeur vers une chaîne SQLTCHAR contenant l’instruction SELECT.</span><span class="sxs-lookup"><span data-stu-id="1bb54-199">Set *eOption* to BCPHINTS and set *iValue* to have a pointer to an SQLTCHAR string containing the SELECT statement.</span></span>  
  
 <span data-ttu-id="1bb54-200">Ces paramètres de contrôle ne sont explicites qu'en cas de copie entre un fichier utilisateur et une table [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1bb54-200">These control parameters are only meaningful when copying between a user file and an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span> <span data-ttu-id="1bb54-201">Les paramètres de contrôle n’ont aucun effet sur les lignes copiées dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] avec [bcp_sendrow](bcp-sendrow.md).</span><span class="sxs-lookup"><span data-stu-id="1bb54-201">Control parameter settings have no effect on rows copied to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with [bcp_sendrow](bcp-sendrow.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1bb54-202"> Exemple</span><span class="sxs-lookup"><span data-stu-id="1bb54-202">Example</span></span>  
  
```  
// Variables like henv not specified.  
SQLHDBC      hdbc;  
DBINT      nRowsProcessed;  
  
// Application initiation, get an ODBC environment handle, allocate the  
// hdbc, and so on.  
...   
  
// Enable bulk copy prior to connecting on allocated hdbc.  
SQLSetConnectAttr(hdbc, SQL_COPT_SS_BCP, (SQLPOINTER) SQL_BCP_ON,  
   SQL_IS_INTEGER);  
  
// Connect to the data source, return on error.  
if (!SQL_SUCCEEDED(SQLConnect(hdbc, _T("myDSN"), SQL_NTS,  
   _T("myUser"), SQL_NTS, _T("myPwd"), SQL_NTS)))  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Initialize bulk copy.   
if (bcp_init(hdbc, _T("address"), _T("address.add"), _T("addr.err"),  
   DB_IN) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Set the number of rows per batch.   
if (bcp_control(hdbc, BCPBATCH, (void*) 1000) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Set file column count.   
if (bcp_columns(hdbc, 1) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Set the file format.   
if (bcp_colfmt(hdbc, 1, 0, 0, SQL_VARLEN_DATA, '\n', 1, 1)  
   == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Execute the bulk copy.   
if (bcp_exec(hdbc, &nRowsProcessed) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
printf_s("%ld rows processed by bulk copy.", nRowsProcessed);  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="1bb54-203"> Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1bb54-203">See Also</span></span>  
 [<span data-ttu-id="1bb54-204">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="1bb54-204">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
