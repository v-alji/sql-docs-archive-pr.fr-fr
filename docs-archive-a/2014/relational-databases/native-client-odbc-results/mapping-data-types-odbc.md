---
title: Mappage de types de données (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- mapping data types [ODBC]
- result sets [ODBC], data types
- ODBC data types, mapping
- SQL Server Native Client ODBC driver, result sets
- ODBC applications, result sets
- data types [ODBC], mapping
- sql_variant data type
- SQL Server Native Client ODBC driver, data types
ms.assetid: 4ba0924d-9fca-4c48-aced-0a8d817b3dde
author: rothja
ms.author: jroth
ms.openlocfilehash: 545e738afb6b3283b2ff2f3830921da8ed13202f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709335"
---
# <a name="mapping-data-types-odbc"></a><span data-ttu-id="d5974-102">Mappage de types de données (ODBC)</span><span class="sxs-lookup"><span data-stu-id="d5974-102">Mapping Data Types (ODBC)</span></span>
  <span data-ttu-id="d5974-103">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pilote ODBC Native Client mappe les [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] types de données SQL aux types de données SQL ODBC.</span><span class="sxs-lookup"><span data-stu-id="d5974-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver maps [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] SQL data types to ODBC SQL data types.</span></span> <span data-ttu-id="d5974-104">Les sections suivantes traitent des types de données SQL [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et des types de données SQL ODBC auxquels ils sont mappés.</span><span class="sxs-lookup"><span data-stu-id="d5974-104">The sections below discuss the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] SQL data types and the ODBC SQL data types to which they map.</span></span> <span data-ttu-id="d5974-105">Elles décrivent également les types de données SQL ODBC et leurs types de données C ODBC correspondants, ainsi que les conversions prises en charge et par défaut.</span><span class="sxs-lookup"><span data-stu-id="d5974-105">They also discuss the ODBC SQL data types and their corresponding ODBC C data types, and the supported and default conversions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d5974-106">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] type de données **timestamp** est mappé sur le type de données SQL_BINARY ou SQL_VARBINARY ODBC, car les valeurs des colonnes **timestamp** ne sont pas des valeurs **DateTime** , mais des valeurs **Binary (8)** ou **varbinary (8)** qui indiquent la séquence de l' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] activité sur la ligne.</span><span class="sxs-lookup"><span data-stu-id="d5974-106">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**timestamp** data type maps to the SQL_BINARY or SQL_VARBINARY ODBC data type because the values in **timestamp** columns are not **datetime** values, but **binary(8)** or **varbinary(8)** values that indicate the sequence of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] activity on the row.</span></span> <span data-ttu-id="d5974-107">Si le pilote ODBC [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client rencontre une valeur SQL_C_WCHAR (Unicode) qui correspond à un nombre impair d'octets, l'octet impaire de fin est tronqué.</span><span class="sxs-lookup"><span data-stu-id="d5974-107">If the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver encounters a SQL_C_WCHAR (Unicode) value that is an odd number of bytes, the trailing odd byte is truncated.</span></span>  
  
## <a name="dealing-with-sql_variant-data-type-in-odbc"></a><span data-ttu-id="d5974-108">Traitement du type de données sql_variant dans ODBC</span><span class="sxs-lookup"><span data-stu-id="d5974-108">Dealing with sql_variant Data Type in ODBC</span></span>  
 <span data-ttu-id="d5974-109">La colonne de type de données **sql_variant** peut contenir l’un des types de données dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , à l’exception des objets de grande taille (LOB), tels que **Text**, **ntext**et **image**.</span><span class="sxs-lookup"><span data-stu-id="d5974-109">The **sql_variant** data type column can contain any of the data types in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] except large objects (LOBs), such as **text**, **ntext**, and **image**.</span></span> <span data-ttu-id="d5974-110">Par exemple, la colonne peut contenir des valeurs **smallint** pour certaines lignes, des valeurs **float** pour d’autres lignes et des valeurs **CHAR/NCHAR** dans le reste.</span><span class="sxs-lookup"><span data-stu-id="d5974-110">For example, the column could contain **smallint** values for some rows, **float** values for other rows, and **char/nchar** values in the remainder.</span></span>  
  
 <span data-ttu-id="d5974-111">Le type de données **sql_variant** est semblable au type de données **variant** dans Microsoft Visual Basic ??.</span><span class="sxs-lookup"><span data-stu-id="d5974-111">The **sql_variant** data type is similar to the **Variant** data type in Microsoft Visual Basic??.</span></span>  
  
### <a name="retrieving-data-from-the-server"></a><span data-ttu-id="d5974-112">Récupération de données à partir du serveur</span><span class="sxs-lookup"><span data-stu-id="d5974-112">Retrieving Data from the Server</span></span>  
 <span data-ttu-id="d5974-113">ODBC n’a pas de concept de types variants, ce qui limite l’utilisation du type de données **sql_variant** avec un pilote ODBC dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d5974-113">ODBC does not have a concept of variant types, limiting the use of the **sql_variant** data type with an ODBC driver in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d5974-114">Dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , si la liaison est spécifiée, le type de données **sql_variant** doit être lié à l’un des types de données ODBC documentés.</span><span class="sxs-lookup"><span data-stu-id="d5974-114">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], if binding is specified, the **sql_variant** data type must be bound to one of the documented ODBC data types.</span></span> <span data-ttu-id="d5974-115">**SQL_CA_SS_VARIANT_TYPE**, un nouvel attribut propre au [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pilote ODBC Native Client, retourne le type de données d’une instance de la colonne **sql_variant** à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d5974-115">**SQL_CA_SS_VARIANT_TYPE**, a new attribute specific to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver, returns the data type of an instance in the **sql_variant** column to the user.</span></span>  
  
 <span data-ttu-id="d5974-116">Si aucune liaison n’est spécifiée, la fonction [SQLGetData](../native-client-odbc-api/sqlgetdata.md) peut être utilisée pour déterminer le type de données d’une instance dans la colonne **sql_variant** .</span><span class="sxs-lookup"><span data-stu-id="d5974-116">If no binding is specified, the [SQLGetData](../native-client-odbc-api/sqlgetdata.md) function can be used to determine the data type of an instance in the **sql_variant** column.</span></span>  
  
 <span data-ttu-id="d5974-117">Pour récupérer **sql_variant** données, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="d5974-117">To retrieve **sql_variant** data follow these steps.</span></span>  
  
1.  <span data-ttu-id="d5974-118">Appelez **SQLFetch** pour positionner sur la ligne récupérée.</span><span class="sxs-lookup"><span data-stu-id="d5974-118">Call **SQLFetch** to position to the row retrieved.</span></span>  
  
2.  <span data-ttu-id="d5974-119">Appelez **SQLGetData**, en spécifiant SQL_C_BINARY pour le type et 0 pour la longueur des données.</span><span class="sxs-lookup"><span data-stu-id="d5974-119">Call **SQLGetData**, specifying SQL_C_BINARY for the type and 0 for the data length.</span></span> <span data-ttu-id="d5974-120">Cela force le pilote à lire l’en-tête **sql_variant** .</span><span class="sxs-lookup"><span data-stu-id="d5974-120">This forces the driver to read the **sql_variant** header.</span></span> <span data-ttu-id="d5974-121">L’en-tête fournit le type de données de cette instance dans la colonne **sql_variant** .</span><span class="sxs-lookup"><span data-stu-id="d5974-121">The header provides the data type of that instance in the **sql_variant** column.</span></span> <span data-ttu-id="d5974-122">**SQLGetData** retourne la taille (en octets) de la valeur.</span><span class="sxs-lookup"><span data-stu-id="d5974-122">**SQLGetData** returns the size (in bytes) of the value.</span></span>  
  
3.  <span data-ttu-id="d5974-123">Appelez [SQLColAttribute](../native-client-odbc-api/sqlcolattribute.md) en spécifiant **SQL_CA_SS_VARIANT_TYPE** comme valeur d’attribut.</span><span class="sxs-lookup"><span data-stu-id="d5974-123">Call [SQLColAttribute](../native-client-odbc-api/sqlcolattribute.md) by specifying **SQL_CA_SS_VARIANT_TYPE** as its attribute value.</span></span> <span data-ttu-id="d5974-124">Cette fonction retourne le type de données C de l’instance dans la colonne **sql_variant** au client.</span><span class="sxs-lookup"><span data-stu-id="d5974-124">This function will return the C data type of the instance in the **sql_variant** column to the client.</span></span>  
  
 <span data-ttu-id="d5974-125">Voici un segment de code qui illustre les étapes précédentes.</span><span class="sxs-lookup"><span data-stu-id="d5974-125">Here is a code segment showing the preceding steps.</span></span>  
  
```  
while ((retcode = SQLFetch (hstmt))==SQL_SUCCESS)  
{  
    if (retcode != SQL_SUCCESS && retcode != SQL_SUCCESS_WITH_INFO)  
    {  
        SQLError (NULL, NULL, hstmt, NULL,   
                    &lNativeError,szError,MAX_DATA,&sReturned);  
        printf_s ("%s\n",szError);  
        goto Exit;  
    }  
    retcode = SQLGetData (hstmt, 1, SQL_C_BINARY,   
                                pBuff,0,&Indicator);//Figure out the length  
    if (retcode != SQL_SUCCESS_WITH_INFO && retcode != SQL_SUCCESS)  
    {  
        SQLError (NULL, NULL, hstmt, NULL, &lNativeError,   
                    szError,MAX_DATA,&sReturned);  
        printf_s ("%s\n",szError);  
        goto Exit;  
    }  
    printf_s ("Byte length : %d ",Indicator); //Print out the byte length  
  
    int iValue = 0;  
    retcode = SQLColAttribute (hstmt, 1, SQL_CA_SS_VARIANT_TYPE, NULL,   
                                        NULL,NULL,&iValue);  //Figure out the type  
    printf_s ("Sub type = %d ",iValue);//Print the type, the return is C_type of the column]  
  
// Set up a new binding or do the SQLGetData on that column with   
// the appropriate type  
}  
```  
  
 <span data-ttu-id="d5974-126">Si l’utilisateur crée la liaison à l’aide de [SQLBindCol](../native-client-odbc-api/sqlbindcol.md), le pilote lit les métadonnées et les données.</span><span class="sxs-lookup"><span data-stu-id="d5974-126">If the user creates the binding using [SQLBindCol](../native-client-odbc-api/sqlbindcol.md), the driver reads the metadata and the data.</span></span> <span data-ttu-id="d5974-127">Le pilote convertit ensuite les données en un type ODBC approprié tel que spécifié dans la liaison.</span><span class="sxs-lookup"><span data-stu-id="d5974-127">The driver then converts the data to the appropriate ODBC type specified in the binding.</span></span>  
  
### <a name="sending-data-to-the-server"></a><span data-ttu-id="d5974-128">Envoi de données au serveur</span><span class="sxs-lookup"><span data-stu-id="d5974-128">Sending Data to the Server</span></span>  
 <span data-ttu-id="d5974-129">**SQL_SS_VARIANT**, un nouveau type de données spécifique au [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pilote ODBC Native Client, est utilisé pour les données envoyées à une colonne **sql_variant** .</span><span class="sxs-lookup"><span data-stu-id="d5974-129">**SQL_SS_VARIANT**, a new data type specific to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver, is used for data sent to an **sql_variant** column.</span></span> <span data-ttu-id="d5974-130">Lors de l’envoi de données au serveur à l’aide de paramètres (par exemple, INSERT dans des valeurs TableName ( ?, ?)), [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md) est utilisé pour spécifier les informations sur les paramètres, y compris le type C et le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] type correspondant.</span><span class="sxs-lookup"><span data-stu-id="d5974-130">When sending data to the server using parameters (for example, INSERT INTO TableName VALUES (?,?)), [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md) is used to specify the parameter information including the C type and the corresponding [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] type.</span></span> <span data-ttu-id="d5974-131">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pilote ODBC native client convertit le type de données C en un des sous-types **sql_variant** appropriés.</span><span class="sxs-lookup"><span data-stu-id="d5974-131">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver will convert the C data type to one of the appropriate **sql_variant** subtypes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5974-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d5974-132">See Also</span></span>  
 [<span data-ttu-id="d5974-133">Traitement des résultats &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="d5974-133">Processing Results &#40;ODBC&#41;</span></span>](processing-results-odbc.md)  
  
  
