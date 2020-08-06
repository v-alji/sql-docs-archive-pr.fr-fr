---
title: Conversion de DB-Library en copie en bloc ODBC | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- converting DB-Library to ODBC bulk copy
- SQL Server Native Client ODBC driver, bulk copy
- bulk copy [ODBC], DB-Library bulk copy
- ODBC, bulk copy operations
- DB-Library bulk copy
ms.assetid: 0bc15bdb-f19f-4537-ac6c-f249f42cf07f
author: rothja
ms.author: jroth
ms.openlocfilehash: 866900606e582f08695fd4695a1098f34fb2b426
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612303"
---
# <a name="converting-from-db-library-to-odbc-bulk-copy"></a><span data-ttu-id="69e17-102">Conversion à partir de la bibliothèque de bases de données vers une copie en bloc ODBC</span><span class="sxs-lookup"><span data-stu-id="69e17-102">Converting from DB-Library to ODBC Bulk Copy</span></span>
  <span data-ttu-id="69e17-103">La conversion d’un programme de copie en bloc DB-Library vers ODBC est simple, car les fonctions de copie en bloc prises en charge par le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pilote ODBC native client sont similaires aux fonctions de copie en bloc de DB-Library, avec les exceptions suivantes :</span><span class="sxs-lookup"><span data-stu-id="69e17-103">Converting a DB-Library bulk copy program to ODBC is easy because the bulk copy functions supported by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver are similar to the DB-Library bulk copy functions, with the following exceptions:</span></span>  
  
-   <span data-ttu-id="69e17-104">Les applications de bibliothèque de bases de données passent un pointeur à une structure DBPROCESS comme premier paramètre de fonctions de copie en bloc.</span><span class="sxs-lookup"><span data-stu-id="69e17-104">DB-Library applications pass a pointer to a DBPROCESS structure as the first parameter of bulk copy functions.</span></span> <span data-ttu-id="69e17-105">Dans les applications ODBC, le pointeur DBPROCESS est remplacé par un handle de connexion ODBC.</span><span class="sxs-lookup"><span data-stu-id="69e17-105">In ODBC applications, the DBPROCESS pointer is replaced with an ODBC connection handle.</span></span>  
  
-   <span data-ttu-id="69e17-106">Les applications DB-Library appellent **BCP_SETL** avant de se connecter pour activer les opérations de copie en bloc sur un DBPROCESS.</span><span class="sxs-lookup"><span data-stu-id="69e17-106">DB-Library applications call **BCP_SETL** before connecting to enable bulk copy operations on a DBPROCESS.</span></span> <span data-ttu-id="69e17-107">Les applications ODBC appellent plutôt [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) avant de se connecter pour activer les opérations en bloc sur un handle de connexion :</span><span class="sxs-lookup"><span data-stu-id="69e17-107">ODBC applications instead call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) before connecting to enable bulk operations on a connection handle:</span></span>  
  
    ```  
    SQLSetConnectAttr(hdbc, SQL_COPT_SS_BCP,  
        (void *)SQL_BCP_ON, SQL_IS_INTEGER);  
    ```  
  
-   <span data-ttu-id="69e17-108">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pilote ODBC Native Client ne prend pas en charge les gestionnaires d’erreurs et de messages DB-Library ; vous devez appeler **SQLGetDiagRec** pour recevoir les erreurs et les messages générés par les fonctions de copie en bloc ODBC.</span><span class="sxs-lookup"><span data-stu-id="69e17-108">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver does not support DB-Library message and error handlers; you must call **SQLGetDiagRec** to get errors and messages raised by the ODBC bulk copy functions.</span></span> <span data-ttu-id="69e17-109">Les versions ODBC de fonctions de copie en bloc retournent les codes de retour de copie en bloc standard de SUCCEED ou FAILED, et non les codes de retour de style ODBC, tels que SQL_SUCCESS ou SQL_ERROR.</span><span class="sxs-lookup"><span data-stu-id="69e17-109">The ODBC versions of bulk copy functions return the standard bulk copy return codes of SUCCEED or FAILED, not ODBC-style return codes, such as SQL_SUCCESS or SQL_ERROR.</span></span>  
  
-   <span data-ttu-id="69e17-110">Les valeurs spécifiées pour le paramètre DB-Library [bcp_bind](../native-client-odbc-extensions-bulk-copy-functions/bcp-bind.md)*varlen* sont interprétées différemment du paramètre ODBC **bcp_bind**_cbData_ .</span><span class="sxs-lookup"><span data-stu-id="69e17-110">The values specified for the DB-Library [bcp_bind](../native-client-odbc-extensions-bulk-copy-functions/bcp-bind.md)*varlen* parameter are interpreted differently than the ODBC **bcp_bind**_cbData_ parameter.</span></span>  
  
    |<span data-ttu-id="69e17-111">Condition indiquée</span><span class="sxs-lookup"><span data-stu-id="69e17-111">Condition indicated</span></span>|<span data-ttu-id="69e17-112">Valeur *VARLEN* DB-Library</span><span class="sxs-lookup"><span data-stu-id="69e17-112">DB-Library *varlen* value</span></span>|<span data-ttu-id="69e17-113">Valeur *CBDATA* ODBC</span><span class="sxs-lookup"><span data-stu-id="69e17-113">ODBC *cbData* value</span></span>|  
    |-------------------------|--------------------------------|-------------------------|  
    |<span data-ttu-id="69e17-114">Valeurs NULL fournies</span><span class="sxs-lookup"><span data-stu-id="69e17-114">Null values supplied</span></span>|<span data-ttu-id="69e17-115">0</span><span class="sxs-lookup"><span data-stu-id="69e17-115">0</span></span>|<span data-ttu-id="69e17-116">-1 (SQL_NULL_DATA)</span><span class="sxs-lookup"><span data-stu-id="69e17-116">-1 (SQL_NULL_DATA)</span></span>|  
    |<span data-ttu-id="69e17-117">Données de variables fournies</span><span class="sxs-lookup"><span data-stu-id="69e17-117">Variable data supplied</span></span>|<span data-ttu-id="69e17-118">-1</span><span class="sxs-lookup"><span data-stu-id="69e17-118">-1</span></span>|<span data-ttu-id="69e17-119">-10 (SQL_VARLEN_DATA)</span><span class="sxs-lookup"><span data-stu-id="69e17-119">-10 (SQL_VARLEN_DATA)</span></span>|  
    |<span data-ttu-id="69e17-120">Caractère de longueur nulle ou chaîne binaire</span><span class="sxs-lookup"><span data-stu-id="69e17-120">Zero length character or binary string</span></span>|<span data-ttu-id="69e17-121">N/D</span><span class="sxs-lookup"><span data-stu-id="69e17-121">NA</span></span>|<span data-ttu-id="69e17-122">0</span><span class="sxs-lookup"><span data-stu-id="69e17-122">0</span></span>|  
  
     <span data-ttu-id="69e17-123">Dans DB-Library, une valeur *varlen* de-1 indique que les données de longueur variable sont fournies, ce qui, dans le *cbData* ODBC, est interprété comme signifiant que seules les valeurs NULL sont fournies.</span><span class="sxs-lookup"><span data-stu-id="69e17-123">In DB-Library, a *varlen* value of -1 indicates that variable length data is being supplied, which in the ODBC *cbData* is interpreted to mean that only NULL values are being supplied.</span></span> <span data-ttu-id="69e17-124">Modifiez les spécifications *VARLEN* DB-Library de-1 en SQL_VARLEN_DATA et toutes les spécifications *varlen* de 0 à SQL_NULL_DATA.</span><span class="sxs-lookup"><span data-stu-id="69e17-124">Change any DB-Library *varlen* specifications of -1 to SQL_VARLEN_DATA and any *varlen* specifications of 0 to SQL_NULL_DATA.</span></span>  
  
-   <span data-ttu-id="69e17-125">Le fichier \*\* \_ colfmt\**de la bibliothèque de bases de fichiers bcp et le [bcp_colfmt](../native-client-odbc-extensions-bulk-copy-functions/bcp-colfmt.md)ODBC*cbUserData\* ont le même problème que les paramètres **bcp_bind**_varlen_ et *cbData* indiqués ci-dessus._ \_ _</span><span class="sxs-lookup"><span data-stu-id="69e17-125">The DB-Library **bcp\_colfmt**_file\_collen_ and the ODBC [bcp_colfmt](../native-client-odbc-extensions-bulk-copy-functions/bcp-colfmt.md)*cbUserData* have the same issue as the **bcp_bind**_varlen_ and *cbData* parameters noted above.</span></span> <span data-ttu-id="69e17-126">Remplacez les spécifications de *FILE_COLLEN* DB-Library de-1 par SQL_VARLEN_DATA et toutes les spécifications de *file_collen* comprises entre 0 et SQL_NULL_DATA.</span><span class="sxs-lookup"><span data-stu-id="69e17-126">Change any DB-Library *file_collen* specifications of -1 to SQL_VARLEN_DATA and any *file_collen* specifications of 0 to SQL_NULL_DATA.</span></span>  
  
-   <span data-ttu-id="69e17-127">Le paramètre *iValue* de la fonction [bcp_control](../native-client-odbc-extensions-bulk-copy-functions/bcp-control.md) ODBC est un pointeur void.</span><span class="sxs-lookup"><span data-stu-id="69e17-127">The *iValue* parameter of the ODBC [bcp_control](../native-client-odbc-extensions-bulk-copy-functions/bcp-control.md) function is a void pointer.</span></span> <span data-ttu-id="69e17-128">Dans DB-Library, *iValue* était un entier.</span><span class="sxs-lookup"><span data-stu-id="69e17-128">In DB-Library, *iValue* was an integer.</span></span> <span data-ttu-id="69e17-129">Effectuez un cast des valeurs pour le *IVALUE* ODBC vers void \*.</span><span class="sxs-lookup"><span data-stu-id="69e17-129">Cast the values for the ODBC *iValue* to void \*.</span></span>  
  
-   <span data-ttu-id="69e17-130">L’option **BCP_CONTROL** BCPMAXERRS spécifie le nombre de lignes individuelles pouvant comporter des erreurs avant l’échec d’une opération de copie en bloc.</span><span class="sxs-lookup"><span data-stu-id="69e17-130">The **bcp_control** option BCPMAXERRS specifies how many individual rows can have errors before a bulk copy operation fails.</span></span> <span data-ttu-id="69e17-131">La valeur par défaut de BCPMAXERRS est 0 (échec de la première erreur) dans la version DB-Library de **bcp_control** et 10 dans la version ODBC.</span><span class="sxs-lookup"><span data-stu-id="69e17-131">The default for BCPMAXERRS is 0 (fail on first error) in the DB-Library version of **bcp_control** and 10 in the ODBC version.</span></span> <span data-ttu-id="69e17-132">Les applications DB-Library qui dépendent de la valeur par défaut 0 pour terminer une opération de copie en bloc doivent être modifiées pour appeler le **BCP_CONTROL** ODBC afin de définir BCPMAXERRS sur 0.</span><span class="sxs-lookup"><span data-stu-id="69e17-132">DB-Library applications that depend on the default of 0 to terminate a bulk copy operation must be changed to call the ODBC **bcp_control** to set BCPMAXERRS to 0.</span></span>  
  
-   <span data-ttu-id="69e17-133">La fonction ODBC **bcp_control** prend en charge les options suivantes non prises en charge par la version DB-Library de **bcp_control**:</span><span class="sxs-lookup"><span data-stu-id="69e17-133">The ODBC **bcp_control** function supports the following options not supported by the DB-Library version of **bcp_control**:</span></span>  
  
    -   <span data-ttu-id="69e17-134">BCPODBC</span><span class="sxs-lookup"><span data-stu-id="69e17-134">BCPODBC</span></span>  
  
         <span data-ttu-id="69e17-135">Lorsque la valeur est TRUE, spécifie que les valeurs **DateTime** et **smalldatetime** enregistrées au format caractère auront le préfixe et le suffixe de séquence d’échappement d’horodateur ODBC.</span><span class="sxs-lookup"><span data-stu-id="69e17-135">When set to TRUE, specifies that **datetime** and **smalldatetime** values saved in character format will have the ODBC timestamp escape sequence prefix and suffix.</span></span> <span data-ttu-id="69e17-136">Cela s'applique seulement aux opérations BCP_OUT.</span><span class="sxs-lookup"><span data-stu-id="69e17-136">This only applies to BCP_OUT operations.</span></span>  
  
         <span data-ttu-id="69e17-137">Avec BCPODBC défini sur FALSe, une valeur **DateTime** convertie en chaîne de caractères est sortie comme suit :</span><span class="sxs-lookup"><span data-stu-id="69e17-137">With BCPODBC set to FALSE, a **datetime** value converted to a character string is output as:</span></span>  
  
        ```  
        1997-01-01 00:00:00.000  
        ```  
  
         <span data-ttu-id="69e17-138">Avec BCPODBC défini sur TRUE, la même valeur **DateTime** est générée comme suit :</span><span class="sxs-lookup"><span data-stu-id="69e17-138">With BCPODBC set to TRUE, the same **datetime** value is output as:</span></span>  
  
        ```  
        {ts '1997-01-01 00:00:00.000' }  
        ```  
  
    -   <span data-ttu-id="69e17-139">BCPKEEPIDENTITY</span><span class="sxs-lookup"><span data-stu-id="69e17-139">BCPKEEPIDENTITY</span></span>  
  
         <span data-ttu-id="69e17-140">Si la valeur est TRUE, spécifie que les fonctions de copie en bloc insèrent les valeurs de données fournies pour les colonnes avec des contraintes d'identité.</span><span class="sxs-lookup"><span data-stu-id="69e17-140">When set to TRUE, specifies that bulk copy functions insert data values supplied for columns with identity constraints.</span></span> <span data-ttu-id="69e17-141">Si cela n'est pas défini, de nouvelles valeurs d'identités sont générées pour les lignes insérées.</span><span class="sxs-lookup"><span data-stu-id="69e17-141">If this is not set, new identity values are generated for the inserted rows.</span></span>  
  
    -   <span data-ttu-id="69e17-142">BCPHINTS</span><span class="sxs-lookup"><span data-stu-id="69e17-142">BCPHINTS</span></span>  
  
         <span data-ttu-id="69e17-143">Spécifie diverses optimisations de copie en bloc.</span><span class="sxs-lookup"><span data-stu-id="69e17-143">Specifies various bulk copy optimizations.</span></span> <span data-ttu-id="69e17-144">Cette option ne peut pas être utilisée sur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version 6.5 ou antérieure.</span><span class="sxs-lookup"><span data-stu-id="69e17-144">This option cannot be used on 6.5 or earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
    -   <span data-ttu-id="69e17-145">BCPFILECP</span><span class="sxs-lookup"><span data-stu-id="69e17-145">BCPFILECP</span></span>  
  
         <span data-ttu-id="69e17-146">Spécifie la page de codes du fichier de copie en bloc.</span><span class="sxs-lookup"><span data-stu-id="69e17-146">Specifies the code page of the bulk copy file.</span></span>  
  
    -   <span data-ttu-id="69e17-147">BCPUNICODEFILE</span><span class="sxs-lookup"><span data-stu-id="69e17-147">BCPUNICODEFILE</span></span>  
  
         <span data-ttu-id="69e17-148">Spécifie qu'un fichier de copie en bloc en mode caractère est un fichier Unicode.</span><span class="sxs-lookup"><span data-stu-id="69e17-148">Specifies that a character mode bulk copy file is a Unicode file.</span></span>  
  
-   <span data-ttu-id="69e17-149">La fonction **BCP_COLFMT** ODBC ne prend pas en charge l’indicateur *file_type* de SQLCHAR, car elle est en conflit avec le typedef ODBC SQLCHAR.</span><span class="sxs-lookup"><span data-stu-id="69e17-149">The ODBC **bcp_colfmt** function does not support the *file_type* indicator of SQLCHAR because it conflicts with the ODBC SQLCHAR typedef.</span></span> <span data-ttu-id="69e17-150">Utilisez SQLCHARACTER à la place pour **bcp_colfmt**.</span><span class="sxs-lookup"><span data-stu-id="69e17-150">Use SQLCHARACTER instead for **bcp_colfmt**.</span></span>  
  
-   <span data-ttu-id="69e17-151">Dans les versions ODBC des fonctions de copie en bloc, le format d’utilisation des valeurs **DateTime** et **smalldatetime** dans les chaînes de caractères est le format ODBC aaaa-mm-jj hh : mm : SS. sss ; les valeurs **smalldatetime** utilisent le format ODBC aaaa-mm-jj hh : mm : SS.</span><span class="sxs-lookup"><span data-stu-id="69e17-151">In the ODBC versions of bulk copy functions, the format for working with **datetime** and **smalldatetime** values in character strings is the ODBC format of yyyy-mm-dd hh:mm:ss.sss; **smalldatetime** values use the ODBC format of yyyy-mm-dd hh:mm:ss.</span></span>  
  
     <span data-ttu-id="69e17-152">Les versions DB-Library des fonctions de copie en bloc acceptent les valeurs **DateTime** et **smalldatetime** dans les chaînes de caractères à l’aide de plusieurs formats :</span><span class="sxs-lookup"><span data-stu-id="69e17-152">The DB-Library versions of the bulk copy functions accept **datetime** and **smalldatetime** values in character strings using several formats:</span></span>  
  
    -   <span data-ttu-id="69e17-153">Le format par défaut est *mmm jj aaaa hh : mmxx* , où *XX* est AM ou PM.</span><span class="sxs-lookup"><span data-stu-id="69e17-153">The default format is *mmm dd yyyy hh:mmxx* where *xx* is either AM or PM.</span></span>  
  
    -   <span data-ttu-id="69e17-154">chaînes de caractères **DateTime** et **smalldatetime** dans n’importe quel format pris en charge par la fonction **DBConvert** de la bibliothèque DB-Library.</span><span class="sxs-lookup"><span data-stu-id="69e17-154">**datetime** and **smalldatetime** character strings in any format supported by the DB-Library **dbconvert** function.</span></span>  
  
    -   <span data-ttu-id="69e17-155">Lorsque la case **utiliser les paramètres internationaux** est cochée sous l’onglet **options** de la bibliothèque de bases de l' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilitaire réseau client, les fonctions de copie en bloc de la bibliothèque de bases de la bibliothèque acceptent également les dates au format de date régional défini pour les paramètres régionaux du registre de l’ordinateur client.</span><span class="sxs-lookup"><span data-stu-id="69e17-155">When the **Use international settings** box is checked on the DB-Library **Options** tab of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Client Network Utility, the DB-Library bulk copy functions also accept dates in the regional date format defined for the locale setting of the client computer registry.</span></span>  
  
     <span data-ttu-id="69e17-156">Les fonctions de copie en bloc de DB-Library n’acceptent pas les formats **DateTime** et **smalldatetime** ODBC.</span><span class="sxs-lookup"><span data-stu-id="69e17-156">The DB-Library bulk copy functions do not accept the ODBC **datetime** and **smalldatetime** formats.</span></span>  
  
     <span data-ttu-id="69e17-157">Si l'attribut d'instruction SQL_SOPT_SS_REGIONALIZE a la valeur SQL_RE_ON, les fonctions de copie en bloc ODBC acceptent les dates au format de date régional défini pour les paramètres régionaux du Registre de l'ordinateur client.</span><span class="sxs-lookup"><span data-stu-id="69e17-157">If the SQL_SOPT_SS_REGIONALIZE statement attribute is set to SQL_RE_ON, the ODBC bulk copy functions accept dates in the regional date format defined for the locale setting of the client computer registry.</span></span>  
  
-   <span data-ttu-id="69e17-158">Lorsque vous générez des valeurs **monétaires** au format caractère, les fonctions de copie en bloc ODBC fournissent quatre chiffres de précision et aucun séparateur de virgule. Les versions de DB-Library fournissent uniquement deux chiffres de précision et incluent les séparateurs de virgule.</span><span class="sxs-lookup"><span data-stu-id="69e17-158">When outputting **money** values in character format, ODBC bulk copy functions supply four digits of precision and no comma separators; DB-Library versions only supply two digits of precision and include the comma separators.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69e17-159">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="69e17-159">See Also</span></span>  
 <span data-ttu-id="69e17-160">[Exécution d’opérations de copie en bloc &#40;ODBC&#41;](performing-bulk-copy-operations-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="69e17-160">[Performing Bulk Copy Operations &#40;ODBC&#41;](performing-bulk-copy-operations-odbc.md) </span></span>  
 [<span data-ttu-id="69e17-161">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="69e17-161">Bulk Copy Functions</span></span>](../native-client-odbc-extensions-bulk-copy-functions/sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
