---
title: SQLPutData | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLPutData function
ms.assetid: d39aaa5b-7fbc-4315-a7f2-5a7787e04f25
author: rothja
ms.author: jroth
ms.openlocfilehash: 31da9c21f9e4323a492a25629a979c66a4f7d365
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614013"
---
# <a name="sqlputdata"></a><span data-ttu-id="d9e4d-102">SQLPutData</span><span class="sxs-lookup"><span data-stu-id="d9e4d-102">SQLPutData</span></span>
  <span data-ttu-id="d9e4d-103">Les restrictions suivantes s’appliquent lors de l’utilisation de SQLPutData pour envoyer plus de 65 535 octets de données (pour la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version 4.21 a) ou de 400 Ko de données (pour SQL Server version 6,0 et ultérieure) pour une colonne SQL_LONGVARCHAR ( `text` ), SQL_WLONGVARCHAR ( `ntext` ) ou SQL_LONGVARBINARY ( `image` ) :</span><span class="sxs-lookup"><span data-stu-id="d9e4d-103">The following restrictions apply when using SQLPutData to send more than 65,535 bytes of data (for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version 4.21a) or 400 KB of data (for SQL Server version 6.0 and later) for a SQL_LONGVARCHAR (`text`), SQL_WLONGVARCHAR (`ntext`) or SQL_LONGVARBINARY (`image`) column:</span></span>  
  
-   <span data-ttu-id="d9e4d-104">Le paramètre référencé peut être le *insert_Value* dans une instruction INSERT.</span><span class="sxs-lookup"><span data-stu-id="d9e4d-104">The referenced parameter can be the *insert_value* in an INSERT statement.</span></span>  
  
-   <span data-ttu-id="d9e4d-105">Le paramètre référencé peut être une *expression* dans la clause SET d’une instruction Update.</span><span class="sxs-lookup"><span data-stu-id="d9e4d-105">The referenced parameter can be an *expression* in the SET clause of an UPDATE statement.</span></span>  
  
 <span data-ttu-id="d9e4d-106">L’annulation d’une séquence d’appels SQLPutData qui fournissent des données en blocs à un serveur exécutant [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provoque une mise à jour partielle de la valeur de la colonne lors de l’utilisation de la version 6,5 ou d’une version antérieure.</span><span class="sxs-lookup"><span data-stu-id="d9e4d-106">Canceling a sequence of SQLPutData calls that provide data in blocks to a server running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] causes a partial update of the column's value when using version 6.5 or earlier.</span></span> <span data-ttu-id="d9e4d-107">La `text` `ntext` colonne, ou `image` référencée quand SQLCancel a été appelé est définie sur une valeur d’espace réservé intermédiaire.</span><span class="sxs-lookup"><span data-stu-id="d9e4d-107">The `text`, `ntext`, or `image` column that was referenced when SQLCancel was called is set to an intermediate placeholder value.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d9e4d-108">Le pilote ODBC [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ne prend pas en charge la connexion à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version 6.5 ou antérieure.</span><span class="sxs-lookup"><span data-stu-id="d9e4d-108">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver does not support connecting to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version 6.5 and earlier.</span></span>  
  
## <a name="diagnostics"></a><span data-ttu-id="d9e4d-109">Diagnostics</span><span class="sxs-lookup"><span data-stu-id="d9e4d-109">Diagnostics</span></span>  
 <span data-ttu-id="d9e4d-110">Il existe une [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] SQLSTATE spécifique Native Client pour SQLPutData :</span><span class="sxs-lookup"><span data-stu-id="d9e4d-110">There is one [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client specific SQLSTATE for SQLPutData:</span></span>  
  
|<span data-ttu-id="d9e4d-111">SQLSTATE</span><span class="sxs-lookup"><span data-stu-id="d9e4d-111">SQLSTATE</span></span>|<span data-ttu-id="d9e4d-112">Error</span><span class="sxs-lookup"><span data-stu-id="d9e4d-112">Error</span></span>|<span data-ttu-id="d9e4d-113">Description</span><span class="sxs-lookup"><span data-stu-id="d9e4d-113">Description</span></span>|  
|--------------|-----------|-----------------|  
|<span data-ttu-id="d9e4d-114">22026</span><span class="sxs-lookup"><span data-stu-id="d9e4d-114">22026</span></span>|<span data-ttu-id="d9e4d-115">Chaîne de données ou longueur non correspondante</span><span class="sxs-lookup"><span data-stu-id="d9e4d-115">String data, length mismatch</span></span>|<span data-ttu-id="d9e4d-116">Si la longueur des données en octets à envoyer a été spécifiée par une application, par exemple avec SQL_LEN_DATA_AT_EXEC (*n*) où *n* est supérieur à 0, le nombre total d’octets fournis par l’application via SQLPutData doit correspondre à la longueur spécifiée.</span><span class="sxs-lookup"><span data-stu-id="d9e4d-116">If the length of data in bytes to be sent has been specified by an application, for example, with SQL_LEN_DATA_AT_EXEC(*n*) where *n* is greater than 0, the total number of bytes given by the application via SQLPutData must match the specified length.</span></span>|  
  
## <a name="sqlputdata-and-table-valued-parameters"></a><span data-ttu-id="d9e4d-117">SQLPutData et paramètres table</span><span class="sxs-lookup"><span data-stu-id="d9e4d-117">SQLPutData and Table-Valued Parameters</span></span>  
 <span data-ttu-id="d9e4d-118">SQLPutData est utilisé par une application lors de l’utilisation d’une liaison de ligne variable avec des paramètres table.</span><span class="sxs-lookup"><span data-stu-id="d9e4d-118">SQLPutData is used by an application when using variable row binding with table-valued parameters.</span></span> <span data-ttu-id="d9e4d-119">Le paramètre *StrLen_Or_Ind* indique qu’il est prêt pour le pilote de collecter des données pour la ou les lignes suivantes de données de paramètre table, ou qu’il n’y a plus de lignes disponibles :</span><span class="sxs-lookup"><span data-stu-id="d9e4d-119">The *StrLen_Or_Ind* parameter indicates that it is ready for the driver to collect data for the next row or rows of table-valued parameter data, or that no more rows are available:</span></span>  
  
-   <span data-ttu-id="d9e4d-120">Une valeur supérieure à 0 indique que le jeu suivant de valeurs de ligne est disponible.</span><span class="sxs-lookup"><span data-stu-id="d9e4d-120">A value greater than 0 indicates that the next set of row values is available.</span></span>  
  
-   <span data-ttu-id="d9e4d-121">La valeur 0 indique qu'il ne reste plus de lignes à envoyer.</span><span class="sxs-lookup"><span data-stu-id="d9e4d-121">A value of 0 indicates that there are no more rows to be sent.</span></span>  
  
-   <span data-ttu-id="d9e4d-122">Toute valeur inférieure à 0 est une erreur et entraîne la consignation d'un enregistrement de diagnostic avec SQLState HY090 et le message « Longueur de chaîne ou de mémoire tampon non valide ».</span><span class="sxs-lookup"><span data-stu-id="d9e4d-122">Any value less than 0 is an error and results in a diagnostic record being logged with SQLState HY090 and the messaage "Invalid string or buffer length".</span></span>  
  
 <span data-ttu-id="d9e4d-123">Le paramètre *DataPtr* est ignoré, mais doit être défini sur une valeur non null.</span><span class="sxs-lookup"><span data-stu-id="d9e4d-123">The *DataPtr* parameter is ignored, but must be set to a non-NULL value.</span></span> <span data-ttu-id="d9e4d-124">Pour plus d’informations, consultez la section sur la variable TVP liaison de ligne dans [Binding and transfert de données of Table-valued Parameters and Column Values](../native-client-odbc-table-valued-parameters/binding-and-data-transfer-of-table-valued-parameters-and-column-values.md).</span><span class="sxs-lookup"><span data-stu-id="d9e4d-124">For more information, see the section on Variable TVP row binding in [Binding and Data Transfer of Table-Valued Parameters and Column Values](../native-client-odbc-table-valued-parameters/binding-and-data-transfer-of-table-valued-parameters-and-column-values.md).</span></span>  
  
 <span data-ttu-id="d9e4d-125">Si *StrLen_Or_Ind* a une valeur autre que SQL_DEFAULT_PARAM ou un nombre compris entre 0 et le SQL_PARAMSET_SIZE (autrement dit, le paramètre de *colonne* de SQLBindParameter), il s’agit d’une erreur.</span><span class="sxs-lookup"><span data-stu-id="d9e4d-125">If *StrLen_Or_Ind* has any value other than SQL_DEFAULT_PARAM or a number between 0 and the SQL_PARAMSET_SIZE (that is, the *ColumnSize* parameter of SQLBindParameter), it is an error.</span></span> <span data-ttu-id="d9e4d-126">Cette erreur conduit SQLPutData à retourner SQL_ERROR: SQLSTATE=HY090, « Longueur de chaîne ou de mémoire tampon non valide ».</span><span class="sxs-lookup"><span data-stu-id="d9e4d-126">This error causes SQLPutData to return SQL_ERROR: SQLSTATE=HY090, "Invalid string or buffer length".</span></span>  
  
 <span data-ttu-id="d9e4d-127">Pour plus d’informations sur les paramètres table, consultez [paramètres table &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="d9e4d-127">For more information about table-valued parameters, see [Table-Valued Parameters &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span></span>  
  
## <a name="sqlputdata-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="d9e4d-128">Prise en charge de SQLPutData pour les fonctionnalités Date et Heure améliorées</span><span class="sxs-lookup"><span data-stu-id="d9e4d-128">SQLPutData Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="d9e4d-129">Les valeurs de paramètre de types date/heure sont converties comme décrit dans [conversions de C en SQL](../native-client-odbc-date-time/datetime-data-type-conversions-from-c-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="d9e4d-129">Parameter values of date/time types are converted as described in [Conversions from C to SQL](../native-client-odbc-date-time/datetime-data-type-conversions-from-c-to-sql.md).</span></span>  
  
 <span data-ttu-id="d9e4d-130">Pour plus d’informations, consultez améliorations de la [date et de l’heure &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="d9e4d-130">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="sqlputdata-support-for-large-clr-udts"></a><span data-ttu-id="d9e4d-131">Prise en charge des grands types définis par l'utilisateur CLR par SQLPutData</span><span class="sxs-lookup"><span data-stu-id="d9e4d-131">SQLPutData Support for Large CLR UDTs</span></span>  
 <span data-ttu-id="d9e4d-132">`SQLPutData` prend en charge les grands types CLR définis par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d9e4d-132">`SQLPutData` supports large CLR user-defined types (UDTs).</span></span> <span data-ttu-id="d9e4d-133">Pour plus d’informations, consultez [types CLR volumineux définis par l’utilisateur &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="d9e4d-133">For more information, see [Large CLR User-Defined Types &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9e4d-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d9e4d-134">See Also</span></span>  
 <span data-ttu-id="d9e4d-135">[SQLPutData, fonction](https://go.microsoft.com/fwlink/?LinkId=59365) </span><span class="sxs-lookup"><span data-stu-id="d9e4d-135">[SQLPutData Function](https://go.microsoft.com/fwlink/?LinkId=59365) </span></span>  
 [<span data-ttu-id="d9e4d-136">Détails de l’implémentation d’API ODBC</span><span class="sxs-lookup"><span data-stu-id="d9e4d-136">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
