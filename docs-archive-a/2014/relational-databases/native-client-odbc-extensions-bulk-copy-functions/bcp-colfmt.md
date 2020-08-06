---
title: bcp_colfmt | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_colfmt
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_colfmt function
ms.assetid: 5c3b6299-80c7-4e84-8e69-4ff33009548e
author: rothja
ms.author: jroth
ms.openlocfilehash: f646f3aaf9a8f640d829020bd6762c07c406b61f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709376"
---
# <a name="bcp_colfmt"></a><span data-ttu-id="1d34d-102">bcp_colfmt</span><span class="sxs-lookup"><span data-stu-id="1d34d-102">bcp_colfmt</span></span>
  <span data-ttu-id="1d34d-103">Spécifie le format source ou cible des données d'un fichier utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1d34d-103">Specifies the source or target format of the data in a user file.</span></span> <span data-ttu-id="1d34d-104">En cas d'utilisation comme format source, **bcp_colfmt** spécifie le format d'un fichier de données existant utilisé comme source de données dans une copie en bloc sur une table [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1d34d-104">When used as a source format, **bcp_colfmt** specifies the format of an existing data file used as the source of data in a bulk copy to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span> <span data-ttu-id="1d34d-105">En cas d'utilisation comme format cible, le fichier de données est créé à l'aide des formats de colonne spécifiés avec **bcp_colfmt**.</span><span class="sxs-lookup"><span data-stu-id="1d34d-105">When used as a target format, the data file is created using the column formats specified with **bcp_colfmt**.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d34d-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="1d34d-106">Syntax</span></span>  
  
```  
  
RETCODE bcp_colfmt (  
HDBC   
hdbc  
,  
INT  
idxUserDataCol  
,  
BYTE   
eUserDataType  
,  
INT   
cbIndicator  
,  
DBINT   
cbUserData  
,  
LPCBYTE   
pUserDataTerm  
,  
INT   
cbUserDataTerm  
,  
INT   
idxServerCol  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="1d34d-107">Arguments</span><span class="sxs-lookup"><span data-stu-id="1d34d-107">Arguments</span></span>  
 <span data-ttu-id="1d34d-108">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="1d34d-108">*hdbc*</span></span>  
 <span data-ttu-id="1d34d-109">Handle de connexion ODBC compatible avec la copie en bloc.</span><span class="sxs-lookup"><span data-stu-id="1d34d-109">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="1d34d-110">*idxUserDataCol*</span><span class="sxs-lookup"><span data-stu-id="1d34d-110">*idxUserDataCol*</span></span>  
 <span data-ttu-id="1d34d-111">Numéro de colonne ordinal dans le fichier des données utilisateur pour lequel le format est spécifié.</span><span class="sxs-lookup"><span data-stu-id="1d34d-111">Is the ordinal column number in the user data file for which the format is being specified.</span></span> <span data-ttu-id="1d34d-112">La première colonne est 1.</span><span class="sxs-lookup"><span data-stu-id="1d34d-112">The first column is 1.</span></span>  
  
 <span data-ttu-id="1d34d-113">*eUserDataType*</span><span class="sxs-lookup"><span data-stu-id="1d34d-113">*eUserDataType*</span></span>  
 <span data-ttu-id="1d34d-114">Type de données de la colonne dans le fichier utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1d34d-114">Is the data type of this column in the user file.</span></span> <span data-ttu-id="1d34d-115">Si le type de données est différent de celui de la colonne correspondante dans la table de base de données (*idxServerColumn*), la copie en bloc convertit si possible les données.</span><span class="sxs-lookup"><span data-stu-id="1d34d-115">If different from the data type of the corresponding column in the database table (*idxServerColumn*), bulk copy converts the data if possible.</span></span>  
  
 [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]<span data-ttu-id="1d34d-116">a introduit la prise en charge des jetons de type de données SQLXML et SQLUDT dans le paramètre *eUserDataType* .</span><span class="sxs-lookup"><span data-stu-id="1d34d-116">introduced support for SQLXML and SQLUDT data type tokens in the *eUserDataType* parameter.</span></span>  
  
 <span data-ttu-id="1d34d-117">Le paramètre *eUserDataType* est énuméré par les jetons de type de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dans sqlncli.h, et non par les énumérateurs de type de données C ODBC.</span><span class="sxs-lookup"><span data-stu-id="1d34d-117">The *eUserDataType* parameter is enumerated by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type tokens in sqlncli.h, not the ODBC C data type enumerators.</span></span> <span data-ttu-id="1d34d-118">Par exemple, vous pouvez spécifier une chaîne de caractères, ODBC type SQL_C_CHAR, à l'aide du SQLCHARACTER de type propre à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1d34d-118">For example, you can specify a character string, ODBC type SQL_C_CHAR, using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-specific type SQLCHARACTER.</span></span>  
  
 <span data-ttu-id="1d34d-119">Pour spécifier la représentation des données par défaut pour le type de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , attribuez la valeur 0 à ce paramètre.</span><span class="sxs-lookup"><span data-stu-id="1d34d-119">To specify the default data representation for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type, set this parameter to 0.</span></span>  
  
 <span data-ttu-id="1d34d-120">Pour une copie en bloc à partir de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dans un fichier, lorsque *eUserDataType* est de type SQLDECIMAL ou SQLNUMERIC :</span><span class="sxs-lookup"><span data-stu-id="1d34d-120">For a bulk copy out of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] into a file, when *eUserDataType* is SQLDECIMAL or SQLNUMERIC:</span></span>  
  
-   <span data-ttu-id="1d34d-121">Si la colonne source n’est pas **décimale** ou **numérique**, la précision et l’échelle par défaut sont utilisées.</span><span class="sxs-lookup"><span data-stu-id="1d34d-121">If the source column is not **decimal** or **numeric**, the default precision and scale are used.</span></span>  
  
-   <span data-ttu-id="1d34d-122">Si la colonne source est **décimale** ou **numérique**, la précision et l’échelle de la colonne source sont utilisées.</span><span class="sxs-lookup"><span data-stu-id="1d34d-122">If the source column is **decimal** or **numeric**, the precision and scale of the source column are used.</span></span>  
  
 <span data-ttu-id="1d34d-123">*cbIndicator*</span><span class="sxs-lookup"><span data-stu-id="1d34d-123">*cbIndicator*</span></span>  
 <span data-ttu-id="1d34d-124">Longueur, en octets, d'une longueur/indicateur null au sein des données de la colonne.</span><span class="sxs-lookup"><span data-stu-id="1d34d-124">Is the length, in bytes, of a length/null indicator within the column data.</span></span> <span data-ttu-id="1d34d-125">Les valeurs de longueur d'indicateur valides sont 0 (quand aucun indicateur n'est utilisé), 1, 2, 4 ou 8.</span><span class="sxs-lookup"><span data-stu-id="1d34d-125">Valid indicator length values are 0 (when using no indicator), 1, 2, 4, or 8.</span></span>  
  
 <span data-ttu-id="1d34d-126">Pour spécifier l'utilisation d'un indicateur de copie en bloc par défaut, définissez ce paramètre sur SQL_VARLEN_DATA.</span><span class="sxs-lookup"><span data-stu-id="1d34d-126">To specify default bulk copy indicator usage, set this parameter to SQL_VARLEN_DATA.</span></span>  
  
 <span data-ttu-id="1d34d-127">Les indicateurs apparaissent directement en mémoire avant les autres données et, dans le fichier de données, juste avant les données auxquelles ils s'appliquent.</span><span class="sxs-lookup"><span data-stu-id="1d34d-127">Indicators appear in memory directly before any data, and in the data file directly before the data to which they apply.</span></span>  
  
 <span data-ttu-id="1d34d-128">Si plusieurs méthodes de spécification de la longueur de colonne d'un fichier de données sont utilisées (par exemple, un indicateur et une longueur de colonne maximale, ou un indicateur et une séquence de terminaison), la copie en bloc choisit celle qui implique la quantité de données à copier la moins élevée.</span><span class="sxs-lookup"><span data-stu-id="1d34d-128">If more than one means of specifying a data file column length is used (such as an indicator and a maximum column length, or an indicator and a terminator sequence), bulk copy chooses the one that results in the least amount of data being copied.</span></span>  
  
 <span data-ttu-id="1d34d-129">Les fichiers de données générés par la copie en bloc lorsqu'aucune intervention de l'utilisateur n'ajuste le format des données contiennent des indicateurs si la longueur des données de la colonne est variable ou si la colonne peut accepter la valeur NULL.</span><span class="sxs-lookup"><span data-stu-id="1d34d-129">Data files generated by bulk copy when no user intervention adjusts the format of the data contain indicators when the column data can vary in length or the column can accept NULL as a value.</span></span>  
  
 <span data-ttu-id="1d34d-130">*cbUserData*</span><span class="sxs-lookup"><span data-stu-id="1d34d-130">*cbUserData*</span></span>  
 <span data-ttu-id="1d34d-131">Longueur maximale, en octets, des données de cette colonne dans le fichier utilisateur, sans compter la longueur d'un indicateur de longueur ou d'un terminateur.</span><span class="sxs-lookup"><span data-stu-id="1d34d-131">Is the maximum length, in bytes, of this column's data in the user file, not including the length of any length indicator or terminator.</span></span>  
  
 <span data-ttu-id="1d34d-132">L'attribution de SQL_NULL_DATA à *cbUserData* indique que toutes les valeurs de la colonne du fichier de données sont ou doivent être NULL.</span><span class="sxs-lookup"><span data-stu-id="1d34d-132">Setting *cbUserData* to SQL_NULL_DATA indicates that all values in the data file column are, or should be set to NULL.</span></span>  
  
 <span data-ttu-id="1d34d-133">L'attribution de SQL_VARLEN_DATA à *cbUserData* indique que le système doit déterminer la longueur des données dans chaque colonne.</span><span class="sxs-lookup"><span data-stu-id="1d34d-133">Setting *cbUserData* to SQL_VARLEN_DATA indicates that the system should determine the length of data in each column.</span></span> <span data-ttu-id="1d34d-134">Pour certaines colonnes, cela peut signifier qu'un indicateur de longueur/null est généré pour précéder les données dans une copie à partir de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]ou que l'indicateur est attendu dans les données copiées vers [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1d34d-134">For some columns, this could mean that a length/null indicator is generated to precede data on a copy from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], or that the indicator is expected in data copied to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="1d34d-135">Pour les types de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] character et binary, *cbUserData* peut avoir la valeur SQL_VARLEN_DATA, SQL_NULL_DATA, 0 ou une valeur positive quelconque.</span><span class="sxs-lookup"><span data-stu-id="1d34d-135">For [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] character and binary data types, *cbUserData* can be SQL_VARLEN_DATA, SQL_NULL_DATA, 0, or some positive value.</span></span> <span data-ttu-id="1d34d-136">Si *cbUserData* a la valeur SQL_VARLEN_DATA, le système utilise l'indicateur de longueur, s'il est présent, ou une séquence de terminaison pour déterminer la longueur des données.</span><span class="sxs-lookup"><span data-stu-id="1d34d-136">If *cbUserData* is SQL_VARLEN_DATA, the system uses either the length indicator, if present, or a terminator sequence to determine the length of the data.</span></span> <span data-ttu-id="1d34d-137">Si un indicateur de longueur et une séquence de terminaison sont fournis, la copie en bloc utilise celui qui implique le volume de données à copier le plus faible.</span><span class="sxs-lookup"><span data-stu-id="1d34d-137">If both a length indicator and a terminator sequence are supplied, bulk copy uses the one that results in the least amount of data being copied.</span></span> <span data-ttu-id="1d34d-138">Si *cbUserData* a la valeur SQL_VARLEN_DATA, le type de données est un type [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] character ou binary, et si aucun indicateur de longueur ou séquence de terminaison n'est spécifié, le système retourne un message d'erreur.</span><span class="sxs-lookup"><span data-stu-id="1d34d-138">If *cbUserData* is SQL_VARLEN_DATA, the data type is an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] character or binary type, and neither a length indicator nor a terminator sequence is specified, the system returns an error message.</span></span>  
  
 <span data-ttu-id="1d34d-139">Si *cbUserData* a la valeur 0 ou une valeur positive, le système utilise *cbUserData* comme longueur de données maximale.</span><span class="sxs-lookup"><span data-stu-id="1d34d-139">If *cbUserData* is 0 or a positive value, the system uses *cbUserData* as the maximum data length.</span></span> <span data-ttu-id="1d34d-140">Toutefois, si un indicateur de longueur ou une séquence de terminaison est fournie en plus d'une valeur *cbUserData*positive, le système détermine la longueur de données en utilisant la méthode qui entraîne la plus petite quantité de données à copier.</span><span class="sxs-lookup"><span data-stu-id="1d34d-140">However, if, in addition to a positive *cbUserData*, a length indicator or terminator sequence is provided, the system determines the data length by using the method that results in the least amount of data being copied.</span></span>  
  
 <span data-ttu-id="1d34d-141">La valeur *cbUserData* représente le nombre d'octets de données.</span><span class="sxs-lookup"><span data-stu-id="1d34d-141">The *cbUserData* value represents the count of bytes of data.</span></span> <span data-ttu-id="1d34d-142">Si des données caractères sont représentées par des caractères Unicode étendus, une valeur de paramètre *cbUserData* positive représente le nombre de caractères multiplié par la taille, en octets, de chaque caractère.</span><span class="sxs-lookup"><span data-stu-id="1d34d-142">If character data is represented by Unicode wide characters, then a positive *cbUserData* parameter value represents the number of characters multiplied by the size, in bytes, of each character.</span></span>  
  
 <span data-ttu-id="1d34d-143">*pUserDataTerm*</span><span class="sxs-lookup"><span data-stu-id="1d34d-143">*pUserDataTerm*</span></span>  
 <span data-ttu-id="1d34d-144">Séquence de terminaison à utiliser pour cette colonne.</span><span class="sxs-lookup"><span data-stu-id="1d34d-144">Is the terminator sequence to be used for this column.</span></span> <span data-ttu-id="1d34d-145">Ce paramètre est utile surtout pour les types de données de caractères puisque tous les autres types sont de longueur fixe ou, dans le cas des données binaires, nécessitent un indicateur de longueur pour enregistrer avec précision le nombre d'octets présents.</span><span class="sxs-lookup"><span data-stu-id="1d34d-145">This parameter is useful mainly for character data types because all other types are of fixed length or, in the case of binary data, require an indicator of length to accurately record the number of bytes present.</span></span>  
  
 <span data-ttu-id="1d34d-146">Pour éviter de terminer des données extraites ou pour indiquer que les données dans un fichier utilisateur ne sont pas terminées, attribuez la valeur NULL à ce paramètre.</span><span class="sxs-lookup"><span data-stu-id="1d34d-146">To avoid terminating extracted data, or to indicate that data in a user file is not terminated, set this parameter to NULL.</span></span>  
  
 <span data-ttu-id="1d34d-147">Si plusieurs méthodes sont employées pour définir la longueur des colonnes du fichier utilisateur (par exemple, un terminateur et un indicateur de longueur, ou un terminateur et une longueur de colonne maximale), la copie en bloc choisit celle qui implique le volume de données à copier le moins élevé.</span><span class="sxs-lookup"><span data-stu-id="1d34d-147">If more than one means of specifying a user-file column length is used (such as a terminator and a length indicator, or a terminator and a maximum column length), bulk copy chooses the one that results in the least amount of data being copied.</span></span>  
  
 <span data-ttu-id="1d34d-148">L'interface de programmation d'applications (API) de la copie en bloc procède à la conversion des caractères Unicode vers MBCS en fonction des besoins.</span><span class="sxs-lookup"><span data-stu-id="1d34d-148">The bulk copy API performs Unicode-to-MBCS character conversion as required.</span></span> <span data-ttu-id="1d34d-149">Prenez soin de définir comme il se doit la chaîne d'octets de terminaison et la longueur de cette même chaîne.</span><span class="sxs-lookup"><span data-stu-id="1d34d-149">Care must be taken to ensure that both the terminator byte string and the length of the byte string are set correctly.</span></span>  
  
 <span data-ttu-id="1d34d-150">*cbUserDataTerm*</span><span class="sxs-lookup"><span data-stu-id="1d34d-150">*cbUserDataTerm*</span></span>  
 <span data-ttu-id="1d34d-151">Longueur, en octets, de la séquence de marque de fin à utiliser pour la colonne.</span><span class="sxs-lookup"><span data-stu-id="1d34d-151">Is the length, in bytes, of the terminator sequence to be used for this column.</span></span> <span data-ttu-id="1d34d-152">Si aucune marque de fin n'est présente ou désirée dans les données, attribuez 0 à cette valeur.</span><span class="sxs-lookup"><span data-stu-id="1d34d-152">If no terminator is present or desired in the data, set this value to 0.</span></span>  
  
 <span data-ttu-id="1d34d-153">*idxServerCol*</span><span class="sxs-lookup"><span data-stu-id="1d34d-153">*idxServerCol*</span></span>  
 <span data-ttu-id="1d34d-154">Position ordinale de la colonne dans la table de base de données.</span><span class="sxs-lookup"><span data-stu-id="1d34d-154">Is the ordinal position of the column in the database table.</span></span> <span data-ttu-id="1d34d-155">Le premier numéro de colonne est 1.</span><span class="sxs-lookup"><span data-stu-id="1d34d-155">The first column number is 1.</span></span> <span data-ttu-id="1d34d-156">La position ordinale d'une colonne est indiquée par [SQLColumns](../native-client-odbc-api/sqlcolumns.md).</span><span class="sxs-lookup"><span data-stu-id="1d34d-156">The ordinal position of a column is reported by [SQLColumns](../native-client-odbc-api/sqlcolumns.md).</span></span>  
  
 <span data-ttu-id="1d34d-157">Si cette valeur est 0, la copie en bloc ignore la colonne dans le fichier de données.</span><span class="sxs-lookup"><span data-stu-id="1d34d-157">If this value is 0, bulk copy ignores the column in the data file.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="1d34d-158">Retours</span><span class="sxs-lookup"><span data-stu-id="1d34d-158">Returns</span></span>  
 <span data-ttu-id="1d34d-159">SUCCEED ou FAIL.</span><span class="sxs-lookup"><span data-stu-id="1d34d-159">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1d34d-160">Notes</span><span class="sxs-lookup"><span data-stu-id="1d34d-160">Remarks</span></span>  
 <span data-ttu-id="1d34d-161">La fonction **bcp_colfmt** permet de spécifier le format du fichier utilisateur pour les copies en bloc.</span><span class="sxs-lookup"><span data-stu-id="1d34d-161">The **bcp_colfmt** function allows you to specify the user-file format for bulk copies.</span></span> <span data-ttu-id="1d34d-162">Pour la copie en bloc, un format se compose des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="1d34d-162">For bulk copy, a format contains the following parts:</span></span>  
  
-   <span data-ttu-id="1d34d-163">Mappage des colonnes du fichier utilisateur avec les colonnes de la base de données</span><span class="sxs-lookup"><span data-stu-id="1d34d-163">A mapping from user-file columns to database columns.</span></span>  
  
-   <span data-ttu-id="1d34d-164">Type de données de chaque colonne du fichier utilisateur</span><span class="sxs-lookup"><span data-stu-id="1d34d-164">The data type of each user-file column.</span></span>  
  
-   <span data-ttu-id="1d34d-165">Longueur de l'indicateur facultatif pour chaque colonne</span><span class="sxs-lookup"><span data-stu-id="1d34d-165">The length of the optional indicator for each column.</span></span>  
  
-   <span data-ttu-id="1d34d-166">Longueur maximale des données par colonne du fichier utilisateur</span><span class="sxs-lookup"><span data-stu-id="1d34d-166">The maximum length of data per user-file column.</span></span>  
  
-   <span data-ttu-id="1d34d-167">Séquence d'octets de fin facultative pour chaque colonne</span><span class="sxs-lookup"><span data-stu-id="1d34d-167">The optional terminating byte sequence for each column.</span></span>  
  
-   <span data-ttu-id="1d34d-168">Longueur de la séquence d'octets de fin facultative</span><span class="sxs-lookup"><span data-stu-id="1d34d-168">The length of the optional terminating byte sequence.</span></span>  
  
 <span data-ttu-id="1d34d-169">Chaque appel à **bcp_colfmt** spécifie le format pour une colonne du fichier utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1d34d-169">Each call to **bcp_colfmt** specifies the format for one user-file column.</span></span> <span data-ttu-id="1d34d-170">Par exemple, pour modifier les paramètres par défaut de trois colonnes d'un fichier de données utilisateur de cinq colonnes, appelez d'abord [bcp_columns](bcp-columns.md)**(5)**, puis **bcp_colfmt** cinq fois (trois de ces appels définissant votre format personnalisé).</span><span class="sxs-lookup"><span data-stu-id="1d34d-170">For example, to change the default settings for three columns in a five-column user data file, first call [bcp_columns](bcp-columns.md)**(5)**, and then call **bcp_colfmt** five times, with three of those calls setting your custom format.</span></span> <span data-ttu-id="1d34d-171">Pour les deux appels restants, définissez *eUserDataType* avec la valeur 0 et définissez respectivement *cbIndicator*, *cbUserData*et *cbUserDataTerm* avec les valeurs 0, SQL_VARLEN_DATA et 0.</span><span class="sxs-lookup"><span data-stu-id="1d34d-171">For the remaining two calls, set *eUserDataType* to 0, and set *cbIndicator*, *cbUserData*, and *cbUserDataTerm* to 0, SQL_VARLEN_DATA, and 0 respectively.</span></span> <span data-ttu-id="1d34d-172">Cette procédure copie les cinq colonnes, trois avec votre format personnalisé et deux avec le format par défaut.</span><span class="sxs-lookup"><span data-stu-id="1d34d-172">This procedure copies all five columns, three with your customized format and two with the default format.</span></span>  
  
 <span data-ttu-id="1d34d-173">Pour *cbIndicator*, la valeur 8 pour indiquer un type valeur élevé est désormais valide.</span><span class="sxs-lookup"><span data-stu-id="1d34d-173">For *cbIndicator*, a value of 8 to indicate a large value type is now valid.</span></span> <span data-ttu-id="1d34d-174">Si le préfixe est spécifié pour un champ dont la colonne correspondante est un nouveau type max, il ne peut avoir que la valeur 8.</span><span class="sxs-lookup"><span data-stu-id="1d34d-174">If the prefix is specified for a field whose corresponding column is a new max type, it can only be set to 8.</span></span> <span data-ttu-id="1d34d-175">Pour plus d’informations, consultez [bcp_bind](bcp-bind.md).</span><span class="sxs-lookup"><span data-stu-id="1d34d-175">For details, see [bcp_bind](bcp-bind.md).</span></span>  
  
 <span data-ttu-id="1d34d-176">La fonction **bcp_columns** doit être appelée avant tout appel de **bcp_colfmt**.</span><span class="sxs-lookup"><span data-stu-id="1d34d-176">The **bcp_columns** function must be called before any calls to **bcp_colfmt**.</span></span>  
  
 <span data-ttu-id="1d34d-177">Vous devez appeler **bcp_colfmt** une fois pour chaque colonne du fichier utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1d34d-177">You must call **bcp_colfmt** once for each column in the user file.</span></span>  
  
 <span data-ttu-id="1d34d-178">L’appel de **bcp_colfmt** plusieurs fois pour une colonne de fichier utilisateur génère une erreur.</span><span class="sxs-lookup"><span data-stu-id="1d34d-178">Calling **bcp_colfmt** more than once for any user-file column causes an error.</span></span>  
  
 <span data-ttu-id="1d34d-179">Vous n'avez pas besoin de copier toutes les données d'un fichier utilisateur dans la table [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1d34d-179">You do not need to copy all data in a user file to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span> <span data-ttu-id="1d34d-180">Pour ignorer une colonne, spécifiez le format des données de la colonne, en affectant la valeur 0 au paramètre *idxServerCol* .</span><span class="sxs-lookup"><span data-stu-id="1d34d-180">To skip a column, specify the format of the data for the column, setting the *idxServerCol* parameter to 0.</span></span> <span data-ttu-id="1d34d-181">Pour ignorer une colonne, vous devez spécifier son type.</span><span class="sxs-lookup"><span data-stu-id="1d34d-181">If you want to skip a column, you must specify its type.</span></span>  
  
 <span data-ttu-id="1d34d-182">La fonction [bcp_writefmt](bcp-writefmt.md) peut être utilisée pour garantir la persistance du format spécifié.</span><span class="sxs-lookup"><span data-stu-id="1d34d-182">The [bcp_writefmt](bcp-writefmt.md) function can be used to persist the format specification.</span></span>  
  
## <a name="bcp_colfmt-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="1d34d-183">Prise en charge de bcp_colfmt pour les fonctionnalités Date et Heure améliorées</span><span class="sxs-lookup"><span data-stu-id="1d34d-183">bcp_colfmt Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="1d34d-184">Pour plus d’informations sur les types utilisés avec le paramètre *eUserDataType* pour les types date/time, consultez [modifications de copie en bloc pour les types de date et d’heure améliorés &#40;OLE DB et ODBC&#41;](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="1d34d-184">For information aboutt he types used with the *eUserDataType* parameter for date/time types, see [Bulk Copy Changes for Enhanced Date and Time Types &#40;OLE DB and ODBC&#41;](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span></span>  
  
 <span data-ttu-id="1d34d-185">Pour plus d’informations, consultez améliorations de la [date et de l’heure &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="1d34d-185">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d34d-186">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1d34d-186">See Also</span></span>  
 [<span data-ttu-id="1d34d-187">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="1d34d-187">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
