---
title: bcp_bind | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_bind
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_bind function
ms.assetid: 6e335a5c-64b2-4bcf-a88f-35dc9393f329
author: rothja
ms.author: jroth
ms.openlocfilehash: db0a58398bf47bd0bb96bd1ef587d41890ed8461
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698166"
---
# <a name="bcp_bind"></a><span data-ttu-id="270db-102">bcp_bind</span><span class="sxs-lookup"><span data-stu-id="270db-102">bcp_bind</span></span>
  <span data-ttu-id="270db-103">Lie les données d'une variable de programme à une colonne de table pour une copie en bloc dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="270db-103">Binds data from a program variable to a table column for bulk copy into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="270db-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="270db-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_bind (  
HDBC   
hdbc  
,   
LPCBYTE   
pData  
,  
INT   
cbIndicator  
,  
DBINT   
cbData  
,  
LPCBYTE   
pTerm  
,  
INT   
cbTerm  
,  
INT   
eDataType  
,  
INT   
idxServerCol  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="270db-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="270db-105">Arguments</span></span>  
 <span data-ttu-id="270db-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="270db-106">*hdbc*</span></span>  
 <span data-ttu-id="270db-107">Handle de connexion ODBC compatible avec la copie en bloc.</span><span class="sxs-lookup"><span data-stu-id="270db-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="270db-108">*pData*</span><span class="sxs-lookup"><span data-stu-id="270db-108">*pData*</span></span>  
 <span data-ttu-id="270db-109">Pointeur vers les données copiées.</span><span class="sxs-lookup"><span data-stu-id="270db-109">Is a pointer to the data copied.</span></span> <span data-ttu-id="270db-110">Si *eDataType* a la valeur SQLTEXT, SQLNTEXT, SQLXML, SQLUDT, SQLCHARACTER, SQLVARCHAR, SQLVARBINARY, SqlBinary, SQLNCHAR ou SQLIMAGE, *pData* peut être null.</span><span class="sxs-lookup"><span data-stu-id="270db-110">If *eDataType* is SQLTEXT, SQLNTEXT, SQLXML, SQLUDT, SQLCHARACTER, SQLVARCHAR, SQLVARBINARY, SQLBINARY, SQLNCHAR or SQLIMAGE, *pData* can be NULL.</span></span> <span data-ttu-id="270db-111">Un *pData* null indique que les valeurs de données de type long sont envoyées à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en segments à l’aide de [bcp_moretext](bcp-moretext.md).</span><span class="sxs-lookup"><span data-stu-id="270db-111">A NULL *pData* indicates that long data values will be sent to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in chunks using [bcp_moretext](bcp-moretext.md).</span></span> <span data-ttu-id="270db-112">L’utilisateur doit uniquement définir *pData* sur la valeur null si la colonne correspondant au champ lié à l’utilisateur est une colonne BLOB, sinon **bcp_bind** échoue.</span><span class="sxs-lookup"><span data-stu-id="270db-112">The user should only set *pData* to NULL if the column corresponding to the user bound field is a BLOB column otherwise **bcp_bind** will fail.</span></span>  
  
 <span data-ttu-id="270db-113">Si les indicateurs sont présents dans les données, ils apparaissent directement en mémoire avant les données.</span><span class="sxs-lookup"><span data-stu-id="270db-113">If indicators are present in the data, they appear in memory directly before the data.</span></span> <span data-ttu-id="270db-114">Le paramètre *pData* pointe vers la variable indicateur dans ce cas, et la largeur de l’indicateur, le paramètre *cbIndicator* , est utilisée par la copie en bloc pour traiter correctement les données utilisateur.</span><span class="sxs-lookup"><span data-stu-id="270db-114">The *pData* parameter points to the indicator variable in this case, and the width of the indicator, the *cbIndicator* parameter, is used by bulk copy to address user data correctly.</span></span>  
  
 <span data-ttu-id="270db-115">*cbIndicator*</span><span class="sxs-lookup"><span data-stu-id="270db-115">*cbIndicator*</span></span>  
 <span data-ttu-id="270db-116">Longueur, en octets, d'un indicateur de longueur ou d'un indicateur null pour les données de la colonne.</span><span class="sxs-lookup"><span data-stu-id="270db-116">Is the length, in bytes, of a length or null indicator for the column's data.</span></span> <span data-ttu-id="270db-117">Les valeurs de longueur d'indicateur valides sont 0 (quand aucun indicateur n'est utilisé), 1, 2, 4 ou 8.</span><span class="sxs-lookup"><span data-stu-id="270db-117">Valid indicator length values are 0 (when using no indicator), 1, 2, 4, or 8.</span></span> <span data-ttu-id="270db-118">Les indicateurs apparaissent directement en mémoire avant les données.</span><span class="sxs-lookup"><span data-stu-id="270db-118">Indicators appear in memory directly before any data.</span></span> <span data-ttu-id="270db-119">Par exemple, la définition de type de structure suivante peut être utilisée pour insérer les valeurs entières dans une table [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à l'aide de la copie en bloc :</span><span class="sxs-lookup"><span data-stu-id="270db-119">For example, the following structure type definition could be used to insert integer values into an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table using bulk copy:</span></span>  
  
```  
typedef struct tagBCPBOUNDINT  
    {  
    int iIndicator;  
    int Value;  
    } BCPBOUNDINT;  
```  
  
 <span data-ttu-id="270db-120">Dans le cas de l’exemple, le paramètre *pData* est défini sur l’adresse d’une instance déclarée de la structure, l’adresse du membre de la structure BCPBOUNDINT *iIndicator* .</span><span class="sxs-lookup"><span data-stu-id="270db-120">In the example case, the *pData* parameter would be set to the address of a declared instance of the structure, the address of the BCPBOUNDINT *iIndicator* structure member.</span></span> <span data-ttu-id="270db-121">Le paramètre *cbIndicator* est défini sur la taille d’un entier (sizeof (int)) et le paramètre *cbData* sur la valeur de la taille d’un entier (sizeof (int)).</span><span class="sxs-lookup"><span data-stu-id="270db-121">The *cbIndicator* parameter would be set to the size of an integer (sizeof(int)), and the *cbData* parameter would again be set to the size of an integer (sizeof(int)).</span></span> <span data-ttu-id="270db-122">Pour copier en bloc une ligne sur le serveur contenant une valeur NULL pour la colonne liée, la valeur du membre *iIndicator* de l’instance doit être définie sur SQL_NULL_DATA.</span><span class="sxs-lookup"><span data-stu-id="270db-122">To bulk copy a row to the server containing a NULL value for the bound column, the value of the instance's *iIndicator* member should be set to SQL_NULL_DATA.</span></span>  
  
 <span data-ttu-id="270db-123">*cbData*</span><span class="sxs-lookup"><span data-stu-id="270db-123">*cbData*</span></span>  
 <span data-ttu-id="270db-124">Nombre d'octets de données dans la variable de programme, à l'exclusion de tout indicateur de longueur ou indicateur null ou terminateur.</span><span class="sxs-lookup"><span data-stu-id="270db-124">Is the count of bytes of data in the program variable, not including the length of any length or null indicator or terminator.</span></span>  
  
 <span data-ttu-id="270db-125">La définition de *cbData* sur SQL_NULL_DATA signifie que toutes les lignes copiées sur le serveur contiennent une valeur null pour la colonne.</span><span class="sxs-lookup"><span data-stu-id="270db-125">Setting *cbData* to SQL_NULL_DATA signifies that all rows copied to the server contain a NULL value for the column.</span></span>  
  
 <span data-ttu-id="270db-126">La définition de *cbData* sur SQL_VARLEN_DATA indique que le système utilisera un terminateur de chaîne ou une autre méthode pour déterminer la longueur des données copiées.</span><span class="sxs-lookup"><span data-stu-id="270db-126">Setting *cbData* to SQL_VARLEN_DATA indicates that the system will use a string terminator, or other method, to determine the length of data copied.</span></span>  
  
 <span data-ttu-id="270db-127">Pour les types de données de longueur fixe, tels que les entiers, le type de données indique la longueur des données au système.</span><span class="sxs-lookup"><span data-stu-id="270db-127">For fixed-length data types, such as integers, the data type indicates the length of the data to the system.</span></span> <span data-ttu-id="270db-128">Par conséquent, pour les types de données de longueur fixe, *cbData* peut être SQL_VARLEN_DATA en toute sécurité ou la longueur des données.</span><span class="sxs-lookup"><span data-stu-id="270db-128">Therefore, for fixed-length data types, *cbData* can safely be SQL_VARLEN_DATA or the length of the data.</span></span>  
  
 <span data-ttu-id="270db-129">Pour les [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] types de données caractère et binaire, *cbData* peut être SQL_VARLEN_DATA, SQL_NULL_DATA, une valeur positive ou 0.</span><span class="sxs-lookup"><span data-stu-id="270db-129">For [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] character and binary data types, *cbData* can be SQL_VARLEN_DATA, SQL_NULL_DATA, some positive value, or 0.</span></span> <span data-ttu-id="270db-130">Si *cbData* est SQL_VARLEN_DATA, le système utilise un indicateur de longueur/null (le cas échéant) ou une séquence de marque de fin pour déterminer la longueur des données.</span><span class="sxs-lookup"><span data-stu-id="270db-130">If *cbData* is SQL_VARLEN_DATA, the system uses either a length/null indicator (if present) or a terminator sequence to determine the length of the data.</span></span> <span data-ttu-id="270db-131">Si les deux sont fournis, le système utilise celui qui se traduit par la quantité de données à copier la moins élevée.</span><span class="sxs-lookup"><span data-stu-id="270db-131">If both are supplied, the system uses the one that results in the least amount of data being copied.</span></span> <span data-ttu-id="270db-132">Si *cbData* est SQL_VARLEN_DATA, le type de données de la colonne est un [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] type caractère ou binaire, et ni un indicateur de longueur ni une séquence de marque de fin n’est spécifié, le système retourne un message d’erreur.</span><span class="sxs-lookup"><span data-stu-id="270db-132">If *cbData* is SQL_VARLEN_DATA, the data type of the column is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] character or binary type, and neither a length indicator nor a terminator sequence is specified, the system returns an error message.</span></span>  
  
 <span data-ttu-id="270db-133">Si *cbData* est égal à 0 ou à une valeur positive, le système utilise *cbData* comme longueur de données.</span><span class="sxs-lookup"><span data-stu-id="270db-133">If *cbData* is 0 or a positive value, the system uses *cbData* as the data length.</span></span> <span data-ttu-id="270db-134">Toutefois, si, en plus d’une valeur *cbData* positive, un indicateur de longueur ou une séquence de terminaison est fourni, le système détermine la longueur des données à l’aide de la méthode qui produit le moins de données copiées.</span><span class="sxs-lookup"><span data-stu-id="270db-134">However, if, in addition to a positive *cbData* value, a length indicator or terminator sequence is provided, the system determines the data length by using the method that results in the least amount of data being copied.</span></span>  
  
 <span data-ttu-id="270db-135">La valeur du paramètre *cbData* représente le nombre d’octets de données.</span><span class="sxs-lookup"><span data-stu-id="270db-135">The *cbData* parameter value represents the count of bytes of data.</span></span> <span data-ttu-id="270db-136">Si les données caractères sont représentées par des caractères larges Unicode, une valeur de paramètre *cbData* positive représente le nombre de caractères multiplié par la taille en octets de chaque caractère.</span><span class="sxs-lookup"><span data-stu-id="270db-136">If character data is represented by Unicode wide characters, then a positive *cbData* parameter value represents the number of characters multiplied by the size in bytes of each character.</span></span>  
  
 <span data-ttu-id="270db-137">*pTerm*</span><span class="sxs-lookup"><span data-stu-id="270db-137">*pTerm*</span></span>  
 <span data-ttu-id="270db-138">Pointeur vers le modèle d'octet, s'il existe, qui marque la fin de cette variable de programme.</span><span class="sxs-lookup"><span data-stu-id="270db-138">Is a pointer to the byte pattern, if any, that marks the end of this program variable.</span></span> <span data-ttu-id="270db-139">Par exemple, les chaines C ANSI et MBCS ont habituellement un terminateur d'1 octet (\0).</span><span class="sxs-lookup"><span data-stu-id="270db-139">For example, ANSI and MBCS C strings usually have a 1-byte terminator (\0).</span></span>  
  
 <span data-ttu-id="270db-140">Si aucune marque de fin n’est définie pour la variable, affectez la valeur NULL à *pterm* .</span><span class="sxs-lookup"><span data-stu-id="270db-140">If there is no terminator for the variable, set *pTerm* to NULL.</span></span>  
  
 <span data-ttu-id="270db-141">Vous pouvez utiliser une chaîne vide ("") pour désigner l'indicateur de fin C null comme terminateur de variable de programme.</span><span class="sxs-lookup"><span data-stu-id="270db-141">You can use an empty string ("") to designate the C null terminator as the program-variable terminator.</span></span> <span data-ttu-id="270db-142">Étant donné que la chaîne vide se terminant par un caractère null constitue un octet unique (l’octet de terminateur lui-même), affectez la valeur 1 à *cbTerm avec* .</span><span class="sxs-lookup"><span data-stu-id="270db-142">Because the null-terminated empty string constitutes a single byte (the terminator byte itself), set *cbTerm* to 1.</span></span> <span data-ttu-id="270db-143">Par exemple, pour indiquer que la chaîne dans *szName* se termine par un caractère null et que la marque de fin doit être utilisée pour indiquer la longueur :</span><span class="sxs-lookup"><span data-stu-id="270db-143">For example, to indicate that the string in *szName* is null-terminated and that the terminator should be used to indicate the length:</span></span>  
  
```  
bcp_bind(hdbc, szName, 0,  
   SQL_VARLEN_DATA, "", 1,  
   SQLCHARACTER, 2)  
```  
  
 <span data-ttu-id="270db-144">Une forme non terminée de cet exemple peut indiquer que 15 caractères sont copiés de la variable *szName* vers la deuxième colonne de la table liée :</span><span class="sxs-lookup"><span data-stu-id="270db-144">A nonterminated form of this example could indicate that 15 characters be copied from the *szName* variable to the second column of the bound table:</span></span>  
  
```  
bcp_bind(hdbc, szName, 0, 15,   
   NULL, 0, SQLCHARACTER, 2)  
```  
  
 <span data-ttu-id="270db-145">L'interface de programmation d'applications (API) de la copie en bloc procède à la conversion des caractères Unicode vers MBCS en fonction des besoins.</span><span class="sxs-lookup"><span data-stu-id="270db-145">The bulk copy API performs Unicode-to-MBCS character conversion as required.</span></span> <span data-ttu-id="270db-146">Veillez à définir correctement la chaîne d'octet de marque de fin et la longueur de la chaîne d'octets.</span><span class="sxs-lookup"><span data-stu-id="270db-146">Make sure that both the terminator byte string and the length of the byte string are set correctly.</span></span> <span data-ttu-id="270db-147">Par exemple, pour indiquer que la chaîne dans *szName* est une chaîne Unicode à caractères larges, se termine par la valeur de terminateur NULL Unicode :</span><span class="sxs-lookup"><span data-stu-id="270db-147">For example, to indicate that the string in *szName* is a Unicode wide character string, terminated by the Unicode null terminator value:</span></span>  
  
```  
bcp_bind(hdbc, szName, 0,   
   SQL_VARLEN_DATA, L"",  
   sizeof(WCHAR), SQLNCHAR, 2)  
```  
  
 <span data-ttu-id="270db-148">Si la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] colonne liée est un caractère élargi, aucune conversion n’est effectuée sur [bcp_sendrow](bcp-sendrow.md).</span><span class="sxs-lookup"><span data-stu-id="270db-148">If the bound [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] column is wide character, no conversion is performed on [bcp_sendrow](bcp-sendrow.md).</span></span> <span data-ttu-id="270db-149">Si la colonne [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] possède MBCS comme type de caractère, la conversion des caractères larges en caractères multioctets s'effectue quand les données sont envoyées à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="270db-149">If the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] column is an MBCS character type, wide character to multibyte character conversion is performed as the data is sent to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="270db-150">*cbTerm*</span><span class="sxs-lookup"><span data-stu-id="270db-150">*cbTerm*</span></span>  
 <span data-ttu-id="270db-151">Nombre d'octets présents dans le terminateur de la variable de programme, s'il existe.</span><span class="sxs-lookup"><span data-stu-id="270db-151">Is the count of bytes present in the terminator for the program variable, if any.</span></span> <span data-ttu-id="270db-152">Si aucune marque de fin n’est définie pour la variable, affectez la valeur 0 à *cbTerm avec* .</span><span class="sxs-lookup"><span data-stu-id="270db-152">If there is no terminator for the variable, set *cbTerm* to 0.</span></span>  
  
 <span data-ttu-id="270db-153">*eDataType*</span><span class="sxs-lookup"><span data-stu-id="270db-153">*eDataType*</span></span>  
 <span data-ttu-id="270db-154">Type de données C de la variable de programme.</span><span class="sxs-lookup"><span data-stu-id="270db-154">Is the C data type of the program variable.</span></span> <span data-ttu-id="270db-155">Les données de la variable de programme sont converties dans le type de la colonne de base de données.</span><span class="sxs-lookup"><span data-stu-id="270db-155">The data in the program variable is converted to the type of the database column.</span></span> <span data-ttu-id="270db-156">Si ce paramètre est égal à 0, aucune conversion n'est effectuée.</span><span class="sxs-lookup"><span data-stu-id="270db-156">If this parameter is 0, no conversion is performed.</span></span>  
  
 <span data-ttu-id="270db-157">Le paramètre *eDataType* est énuméré par les [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] jetons de type de données dans sqlncli. h, et non par les énumérateurs de type de données C ODBC.</span><span class="sxs-lookup"><span data-stu-id="270db-157">The *eDataType* parameter is enumerated by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type tokens in sqlncli.h, not the ODBC C data type enumerators.</span></span> <span data-ttu-id="270db-158">Par exemple, vous pouvez spécifier un entier à deux octets, type ODBC SQL_C_SHORT, à l'aide du type SQLINT2 propre à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="270db-158">For example, you can specify a two-byte integer, ODBC type SQL_C_SHORT, using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-specific type SQLINT2.</span></span>  
  
 [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]<span data-ttu-id="270db-159">a introduit la prise en charge des jetons de type de données SQLXML et SQLUDT dans le *`eDataType`* .</span><span class="sxs-lookup"><span data-stu-id="270db-159">introduced support for SQLXML and SQLUDT data type tokens in the *`eDataType`* paramenter.</span></span>  
  
 <span data-ttu-id="270db-160">*idxServerCol*</span><span class="sxs-lookup"><span data-stu-id="270db-160">*idxServerCol*</span></span>  
 <span data-ttu-id="270db-161">Position ordinale de la colonne dans la table de base de données vers laquelle les données sont copiées.</span><span class="sxs-lookup"><span data-stu-id="270db-161">Is the ordinal position of the column in the database table to which the data is copied.</span></span> <span data-ttu-id="270db-162">La première colonne d'une table est la colonne 1.</span><span class="sxs-lookup"><span data-stu-id="270db-162">The first column in a table is column 1.</span></span> <span data-ttu-id="270db-163">La position ordinale d'une colonne est indiquée par [SQLColumns](../native-client-odbc-api/sqlcolumns.md).</span><span class="sxs-lookup"><span data-stu-id="270db-163">The ordinal position of a column is reported by [SQLColumns](../native-client-odbc-api/sqlcolumns.md).</span></span>  
  
## <a name="returns"></a><span data-ttu-id="270db-164">Retours</span><span class="sxs-lookup"><span data-stu-id="270db-164">Returns</span></span>  
 <span data-ttu-id="270db-165">SUCCEED ou FAIL.</span><span class="sxs-lookup"><span data-stu-id="270db-165">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="270db-166">Notes</span><span class="sxs-lookup"><span data-stu-id="270db-166">Remarks</span></span>  
 <span data-ttu-id="270db-167">Utilisez **bcp_bind** pour une façon rapide et efficace de copier des données à partir d’une variable de programme dans une table dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="270db-167">Use **bcp_bind** for a fast, efficient way to copy data from a program variable into a table in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="270db-168">Appelez [bcp_init](bcp-init.md) avant d’appeler cette fonction ou toute autre fonction de copie en bloc.</span><span class="sxs-lookup"><span data-stu-id="270db-168">Call [bcp_init](bcp-init.md) before calling this or any other bulk-copy function.</span></span> <span data-ttu-id="270db-169">L’appel de **bcp_init** définit la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table cible pour la copie en bloc.</span><span class="sxs-lookup"><span data-stu-id="270db-169">Calling **bcp_init** sets the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] target table for bulk copy.</span></span> <span data-ttu-id="270db-170">Lors de l’appel de **bcp_init** pour une utilisation avec **bcp_bind** et [bcp_sendrow](bcp-sendrow.md), le paramètre **bcp_init** _szDataFile_ , qui indique le fichier de données, a la valeur null ; le paramètre **bcp_init**_eDirection_ est défini sur DB_IN.</span><span class="sxs-lookup"><span data-stu-id="270db-170">When calling **bcp_init** for use with **bcp_bind** and [bcp_sendrow](bcp-sendrow.md), the **bcp_init** _szDataFile_ parameter, indicating the data file, is set to NULL; the **bcp_init**_eDirection_ parameter is set to DB_IN.</span></span>  
  
 <span data-ttu-id="270db-171">Effectuez un appel de **bcp_bind** distinct pour chaque colonne de la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table dans laquelle vous souhaitez effectuer la copie.</span><span class="sxs-lookup"><span data-stu-id="270db-171">Make a separate **bcp_bind** call for every column in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table into which you want to copy.</span></span> <span data-ttu-id="270db-172">Une fois les appels de **bcp_bind** nécessaires effectués, appelez **bcp_sendrow** pour envoyer une ligne de données à partir de vos variables de programme vers [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="270db-172">After the necessary **bcp_bind** calls have been made, then call **bcp_sendrow** to send a row of data from your program variables to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="270db-173">La reliaison des colonnes n'est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="270db-173">Rebinding a column is not supported.</span></span>  
  
 <span data-ttu-id="270db-174">Chaque fois que vous souhaitez [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] valider les lignes déjà reçues, appelez [bcp_batch](bcp-batch.md).</span><span class="sxs-lookup"><span data-stu-id="270db-174">Whenever you want [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to commit the rows already received, call [bcp_batch](bcp-batch.md).</span></span> <span data-ttu-id="270db-175">Par exemple, appelez **bcp_batch** une fois pour chaque ligne de 1000 insérée ou à tout autre intervalle.</span><span class="sxs-lookup"><span data-stu-id="270db-175">For example, call **bcp_batch** once for every 1000 rows inserted or at any other interval.</span></span>  
  
 <span data-ttu-id="270db-176">Lorsqu’il n’y a plus de lignes à insérer, appelez [bcp_done](bcp-done.md).</span><span class="sxs-lookup"><span data-stu-id="270db-176">When there are no more rows to be inserted, call [bcp_done](bcp-done.md).</span></span> <span data-ttu-id="270db-177">L'échec de cette opération entraîne une erreur.</span><span class="sxs-lookup"><span data-stu-id="270db-177">Failure to do so results in an error.</span></span>  
  
 <span data-ttu-id="270db-178">Les paramètres de contrôle de paramètre, spécifiés avec [bcp_control](bcp-control.md), n’ont aucun effet sur les transferts de lignes **bcp_bind** .</span><span class="sxs-lookup"><span data-stu-id="270db-178">Control parameter settings, specified with [bcp_control](bcp-control.md), have no effect on **bcp_bind** row transfers.</span></span>  
  
 <span data-ttu-id="270db-179">Si *pData* pour une colonne a la valeur null, car sa valeur sera fournie par les appels à [bcp_moretext](bcp-moretext.md), toutes les colonnes suivantes avec *EDATATYPE* défini sur SQLTEXT, SQLNTEXT, SQLXML, SQLUDT, SQLCHARACTER, SQLVARCHAR, SQLVARBINARY, SqlBinary, SQLNCHAR ou SQLIMAGE doivent également être liées avec *pData* ayant la valeur null, et leurs valeurs doivent également être fournies par les appels à `bcp_moretext` .</span><span class="sxs-lookup"><span data-stu-id="270db-179">If *pData* for a column is set to NULL because its value will be supplied by calls to [bcp_moretext](bcp-moretext.md), any subsequent columns with *eDataType* set to SQLTEXT, SQLNTEXT, SQLXML, SQLUDT, SQLCHARACTER, SQLVARCHAR, SQLVARBINARY, SQLBINARY, SQLNCHAR, or SQLIMAGE must also be bound with *pData* set to NULL, and their values must also be supplied by calls to `bcp_moretext`.</span></span>  
  
 <span data-ttu-id="270db-180">Pour les nouveaux types de valeur de grande taille, tels que `varchar(max)` , `varbinary(max)` ou `nvarchar(max)` , vous pouvez utiliser SQLCHARACTER, SQLVARCHAR, SQLVARBINARY, SqlBinary et SQLNCHAR comme indicateurs de type dans le paramètre *eDataType* .</span><span class="sxs-lookup"><span data-stu-id="270db-180">For new large value types, such as `varchar(max)`, `varbinary(max)`, or `nvarchar(max)`, you can use SQLCHARACTER, SQLVARCHAR, SQLVARBINARY, SQLBINARY, and SQLNCHAR as type indicators in the *eDataType* parameter.</span></span>  
  
 <span data-ttu-id="270db-181">Si *cbTerm avec* n’est pas égal à 0, toute valeur (1, 2, 4 ou 8) est valide pour le préfixe (*cbIndicator*).</span><span class="sxs-lookup"><span data-stu-id="270db-181">If *cbTerm* is not 0, any value (1, 2, 4, or 8) is valid for the prefix (*cbIndicator*).</span></span> <span data-ttu-id="270db-182">Dans ce cas, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native client recherche la marque de fin, calcule la longueur des données par rapport au terminateur (*i*) et affecte à *cbData* la valeur la plus petite et la valeur du préfixe.</span><span class="sxs-lookup"><span data-stu-id="270db-182">In this situation, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client will search for the terminator, calculate data length with respect to the terminator (*i*), and set the *cbData* to the smaller value of i and the value of prefix.</span></span>  
  
 <span data-ttu-id="270db-183">Si *cbTerm avec* a la valeur 0 et que *cbIndicator* (le préfixe) n’est pas égal à 0, *cbIndicator* doit avoir la valeur 8.</span><span class="sxs-lookup"><span data-stu-id="270db-183">If *cbTerm* is 0 and *cbIndicator* (the prefix) is not 0, *cbIndicator* must be 8.</span></span> <span data-ttu-id="270db-184">Le préfixe de 8 octets peut prendre les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="270db-184">The 8 byte prefix can take the following values:</span></span>  
  
-   <span data-ttu-id="270db-185">0xFFFFFFFFFFFFFFFF signifie une valeur NULL pour le champ</span><span class="sxs-lookup"><span data-stu-id="270db-185">0xFFFFFFFFFFFFFFFF means a null value for the field</span></span>  
  
-   <span data-ttu-id="270db-186">0xFFFFFFFFFFFFFFFE est traité comme valeur de préfixe spéciale utilisée pour envoyer efficacement les données par segments au serveur.</span><span class="sxs-lookup"><span data-stu-id="270db-186">0xFFFFFFFFFFFFFFFE is treated as a special prefix value which is used for efficiently sending data in chunks to the server.</span></span> <span data-ttu-id="270db-187">Le format des données avec ce préfixe particulier est :</span><span class="sxs-lookup"><span data-stu-id="270db-187">The format of data with this special prefix is:</span></span>  
  
-   <span data-ttu-id="270db-188"><SPECIAL_PREFIX> \<0 or more  DATA CHUNKS> <ZERO_CHUNK> où :</span><span class="sxs-lookup"><span data-stu-id="270db-188"><SPECIAL_PREFIX> \<0 or more  DATA CHUNKS> <ZERO_CHUNK> where:</span></span>  
  
-   <span data-ttu-id="270db-189">SPECIAL_PREFIX est 0xFFFFFFFFFFFFFFFE</span><span class="sxs-lookup"><span data-stu-id="270db-189">SPECIAL_PREFIX is 0xFFFFFFFFFFFFFFFE</span></span>  
  
-   <span data-ttu-id="270db-190">DATA_CHUNK est un préfixe de 4 octets qui contient longueur du segment, suivi par les données effectives dont la longueur est spécifiée dans le préfixe de 4 octets.</span><span class="sxs-lookup"><span data-stu-id="270db-190">DATA_CHUNK is a 4 byte prefix containing length of the chunk,followed by the actual data whose length is specified in the 4 byte prefix.</span></span>  
  
-   <span data-ttu-id="270db-191">ZERO_CHUNK est une valeur de 4 octets contenant tous les zéros (00000000) signifiant la fin des données.</span><span class="sxs-lookup"><span data-stu-id="270db-191">ZERO_CHUNK is a 4 byte value containing all zeros (00000000) indicating the end of data.</span></span>  
  
-   <span data-ttu-id="270db-192">Toute autre longueur de 8 octets valide est traitée comme longueur de données normale.</span><span class="sxs-lookup"><span data-stu-id="270db-192">Any other valid 8 byte length is treated as a regular data length.</span></span>  
  
 <span data-ttu-id="270db-193">L’appel de [bcp_columns](bcp-columns.md) lors de l’utilisation de **bcp_bind** génère une erreur.</span><span class="sxs-lookup"><span data-stu-id="270db-193">Calling [bcp_columns](bcp-columns.md) when using **bcp_bind** results in an error.</span></span>  
  
## <a name="bcp_bind-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="270db-194">Prise en charge de bcp_bind pour les fonctionnalités Date et Heure améliorées</span><span class="sxs-lookup"><span data-stu-id="270db-194">bcp_bind Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="270db-195">Pour plus d’informations sur les types utilisés avec le paramètre *eDataType* pour les types date/heure, consultez [modifications de copie en bloc pour les types de date et d’heure améliorés &#40;OLE DB et ODBC&#41;](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="270db-195">For information about the types used with the *eDataType* parameter for date/time types, see [Bulk Copy Changes for Enhanced Date and Time Types &#40;OLE DB and ODBC&#41;](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span></span>  
  
 <span data-ttu-id="270db-196">Pour plus d’informations, consultez améliorations de la [date et de l’heure &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="270db-196">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="270db-197"> Exemple</span><span class="sxs-lookup"><span data-stu-id="270db-197">Example</span></span>  
  
```  
#include sql.h  
#include sqlext.h  
#include odbcss.h  
// Variables like henv not specified.  
HDBC      hdbc;  
char         szCompanyName[MAXNAME];  
DBINT      idCompany;  
DBINT      nRowsProcessed;  
DBBOOL      bMoreData;  
char*      pTerm = "\t\t";  
  
// Application initiation, get an ODBC environment handle, allocate the  
// hdbc, and so on.  
...   
  
// Enable bulk copy prior to connecting on allocated hdbc.  
SQLSetConnectAttr(hdbc, SQL_COPT_SS_BCP, (SQLPOINTER) SQL_BCP_ON,  
   SQL_IS_INTEGER);  
  
// Connect to the data source; return on error.  
if (!SQL_SUCCEEDED(SQLConnect(hdbc, _T("myDSN"), SQL_NTS,  
   _T("myUser"), SQL_NTS, _T("myPwd"), SQL_NTS)))  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Initialize bcp.   
if (bcp_init(hdbc, "comdb..accounts_info", NULL, NULL  
   DB_IN) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Bind program variables to table columns.   
if (bcp_bind(hdbc, (LPCBYTE) &idCompany, 0, sizeof(DBINT), NULL, 0,  
   SQLINT4, 1)    == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
if (bcp_bind(hdbc, (LPCBYTE) szCompanyName, 0, SQL_VARLEN_DATA,  
   (LPCBYTE) pTerm, strnlen(pTerm, sizeof(pTerm)), SQLCHARACTER, 2) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
while (TRUE)  
   {  
   // Retrieve and process program data.   
   if ((bMoreData = getdata(&idCompany, szCompanyName)) == TRUE)  
      {  
      // Send the data.   
      if (bcp_sendrow(hdbc) == FAIL)  
         {  
         // Raise error and return.  
         return;  
         }  
      }  
   else  
      {  
      // Break out of loop.  
      break;  
      }  
   }  
  
// Terminate the bulk copy operation.  
if ((nRowsProcessed = bcp_done(hdbc)) == -1)  
   {  
   printf_s("Bulk-copy unsuccessful.\n");  
   return;  
   }  
  
printf_s("%ld rows copied.\n", nRowsProcessed);  
```  
  
## <a name="see-also"></a><span data-ttu-id="270db-198"> Voir aussi</span><span class="sxs-lookup"><span data-stu-id="270db-198">See Also</span></span>  
 [<span data-ttu-id="270db-199">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="270db-199">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
