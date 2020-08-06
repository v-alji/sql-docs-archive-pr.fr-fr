---
title: SQLGetTypeInfo | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLGetTypeInfo function
ms.assetid: 13b982c3-ae03-4155-bc0d-e225050703ce
author: rothja
ms.author: jroth
ms.openlocfilehash: 3b2bca833eeed5e51237347a5ea118d839dd36de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614033"
---
# <a name="sqlgettypeinfo"></a><span data-ttu-id="69713-102">SQLGetTypeInfo</span><span class="sxs-lookup"><span data-stu-id="69713-102">SQLGetTypeInfo</span></span>
  <span data-ttu-id="69713-103">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pilote ODBC native client signale la colonne supplémentaire usertype dans le jeu de résultats de `SQLGetTypeInfo` .</span><span class="sxs-lookup"><span data-stu-id="69713-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver reports the additional column USERTYPE in the result set of `SQLGetTypeInfo`.</span></span> <span data-ttu-id="69713-104">USERTYPE signale la définition de type de données de bibliothèque de bases de données et est utile aux développeurs qui déplacent des applications de bibliothèque de bases de données existantes vers ODBC.</span><span class="sxs-lookup"><span data-stu-id="69713-104">USERTYPE reports the DB-Library data type definition and is useful to developers porting existing DB-Library applications to ODBC.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="69713-105">traite l'identité comme un attribut, tandis que ODBC la traite comme un type de données.</span><span class="sxs-lookup"><span data-stu-id="69713-105">treats identity as an attribute, whereas ODBC treats it as a data type.</span></span> <span data-ttu-id="69713-106">Pour résoudre cette incompatibilité, `SQLGetTypeInfo` retourne les types de données suivants : **intidentity**, **smallintidentity**, **tinyintidentity**, **decimalidentity**et **NumericIdentity**.</span><span class="sxs-lookup"><span data-stu-id="69713-106">To resolve this mismatch, `SQLGetTypeInfo` returns the data types: **intidentity**, **smallintidentity**, **tinyintidentity**, **decimalidentity**, and **numericidentity**.</span></span> <span data-ttu-id="69713-107">La `SQLGetTypeInfo` colonne de l’ensemble de résultats AUTO_UNIQUE_VALUE indique la valeur true pour ces types de données.</span><span class="sxs-lookup"><span data-stu-id="69713-107">The `SQLGetTypeInfo` result set column AUTO_UNIQUE_VALUE reports the value TRUE for these data types.</span></span>  
  
 <span data-ttu-id="69713-108">Pour les valeurs de type **varchar**, **nvarchar** et **varbinary**, le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pilote ODBC Native Client continue à signaler 8000, 4000 et 8000 pour la valeur COLUMN_SIZE, bien qu’il soit en fait illimité.</span><span class="sxs-lookup"><span data-stu-id="69713-108">For **varchar**, **nvarchar** and **varbinary**, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver continues to report 8000, 4000 and 8000 respectively for the COLUMN_SIZE value, even though it is actually unlimited.</span></span> <span data-ttu-id="69713-109">Ceci a pour but de garantir la compatibilité descendante.</span><span class="sxs-lookup"><span data-stu-id="69713-109">This is to ensure backward compatibility.</span></span>  
  
 <span data-ttu-id="69713-110">Pour le type de données **XML** , le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pilote ODBC Native Client signale SQL_SS_LENGTH_UNLIMITED COLUMN_SIZE pour indiquer une taille illimitée.</span><span class="sxs-lookup"><span data-stu-id="69713-110">For the **xml** data type, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver reports SQL_SS_LENGTH_UNLIMITED for COLUMN_SIZE to denote unlimited size.</span></span>  
  
## <a name="sqlgettypeinfo-and-table-valued-parameters"></a><span data-ttu-id="69713-111">SQLGetTypeInfo et paramètres table</span><span class="sxs-lookup"><span data-stu-id="69713-111">SQLGetTypeInfo and Table-Valued Parameters</span></span>  
 <span data-ttu-id="69713-112">Le type de table pour les paramètres table est en fait un type méta, c’est-à-dire un type utilisé pour définir d’autres types.</span><span class="sxs-lookup"><span data-stu-id="69713-112">The table type for table-valued parameters is effectively a meta-type-that is, a type used to define other types.</span></span> <span data-ttu-id="69713-113">Par conséquent, il n’est pas nécessaire de l’exposer via SQLGetTypeInfo.</span><span class="sxs-lookup"><span data-stu-id="69713-113">Therefore, it does not have to be exposed through SQLGetTypeInfo.</span></span> <span data-ttu-id="69713-114">Les applications doivent utiliser SQLTables, plutôt que SQLGetTypeInfo, pour récupérer les métadonnées des types de tables utilisés avec les paramètres table.</span><span class="sxs-lookup"><span data-stu-id="69713-114">Applications must use SQLTables, rather than SQLGetTypeInfo, to retrieve metadata for table types used with table-valued parameters.</span></span>  
  
 <span data-ttu-id="69713-115">Pour plus d’informations sur la récupération de métadonnées pour les paramètres table, consultez [attributs d’instruction qui affectent les paramètres table](../native-client-odbc-table-valued-parameters/statement-attributes-that-affect-table-valued-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="69713-115">For more information, about retrieving metdata for table-valued parameters, see [Statement Attributes that Affect Table-Valued Parameters](../native-client-odbc-table-valued-parameters/statement-attributes-that-affect-table-valued-parameters.md).</span></span>  
  
 <span data-ttu-id="69713-116">Pour plus d’informations sur les paramètres table, consultez [paramètres table &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="69713-116">For more information about table-valued parameters, see [Table-Valued Parameters &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span></span>  
  
## <a name="sqlgettypeinfo-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="69713-117">Prise en charge de SQLGetTypeInfo pour les fonctionnalités Date et Heure améliorées</span><span class="sxs-lookup"><span data-stu-id="69713-117">SQLGetTypeInfo Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="69713-118">Pour les valeurs retournées pour les types de date/heure, consultez [Catalog Metadata](../native-client-odbc-date-time/metadata-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="69713-118">For the values returned for date/time types, see [Catalog Metadata](../native-client-odbc-date-time/metadata-catalog.md).</span></span>  
  
 <span data-ttu-id="69713-119">Pour plus d’informations générales, consultez améliorations de la [date et de l’heure &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="69713-119">For more general information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="sqlgettypeinfo-support-for-large-clr-udts"></a><span data-ttu-id="69713-120">Prise en charge SQLGetTypeInfo pour les types CLR volumineux définis par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="69713-120">SQLGetTypeInfo Support for Large CLR UDTs</span></span>  
 <span data-ttu-id="69713-121">`SQLGetTypeInfo` prend en charge les grands types CLR définis par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="69713-121">`SQLGetTypeInfo` supports large CLR user-defined types (UDTs).</span></span> <span data-ttu-id="69713-122">Pour plus d’informations, consultez [types CLR volumineux définis par l’utilisateur &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="69713-122">For more information, see [Large CLR User-Defined Types &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69713-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="69713-123">See Also</span></span>  
 <span data-ttu-id="69713-124">[SQLGetTypeInfo, fonction](https://go.microsoft.com/fwlink/?LinkId=59356) </span><span class="sxs-lookup"><span data-stu-id="69713-124">[SQLGetTypeInfo Function](https://go.microsoft.com/fwlink/?LinkId=59356) </span></span>  
 [<span data-ttu-id="69713-125">Détails de l’implémentation d’API ODBC</span><span class="sxs-lookup"><span data-stu-id="69713-125">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
