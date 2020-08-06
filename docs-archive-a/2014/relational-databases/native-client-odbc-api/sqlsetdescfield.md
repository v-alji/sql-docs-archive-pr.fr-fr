---
title: SQLSetDescField | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQLSetDescField function
ms.assetid: de4bed15-15be-4825-994c-1046255e725a
author: rothja
ms.author: jroth
ms.openlocfilehash: 1b8290fd90c0c9bb91f08d94e119689d38fbc04e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614000"
---
# <a name="sqlsetdescfield"></a><span data-ttu-id="21fb1-102">SQLSetDescField</span><span class="sxs-lookup"><span data-stu-id="21fb1-102">SQLSetDescField</span></span>
  <span data-ttu-id="21fb1-103">SQLSetDescField peut être utilisé pour définir des champs de descripteur pour les paramètres table et les colonnes de paramètre table.</span><span class="sxs-lookup"><span data-stu-id="21fb1-103">SQLSetDescField can be used to set descriptor fields for table-valued parameters and table-valued parameter columns.</span></span> <span data-ttu-id="21fb1-104">Pour plus d’informations sur les champs disponibles, consultez champs de [descripteur de paramètre table](../native-client-odbc-table-valued-parameters/table-valued-parameter-descriptor-fields.md) et [champs de descripteur pour les colonnes constituantes de paramètre table](../native-client-odbc-table-valued-parameters/descriptor-fields-for-table-valued-parameter-constituent-columns.md).</span><span class="sxs-lookup"><span data-stu-id="21fb1-104">For information about the available fields, see [Table-Valued Parameter Descriptor Fields](../native-client-odbc-table-valued-parameters/table-valued-parameter-descriptor-fields.md) and [Descriptor Fields for Table-Valued Parameter Constituent Columns](../native-client-odbc-table-valued-parameters/descriptor-fields-for-table-valued-parameter-constituent-columns.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="21fb1-105">Notes</span><span class="sxs-lookup"><span data-stu-id="21fb1-105">Remarks</span></span>  
 <span data-ttu-id="21fb1-106">Les colonnes de paramètre table sont disponibles uniquement lorsque le champ d'en-tête de descripteur SQL_SOPT_SS_PARAM_FOCUS est défini sur l'ordinal d'un enregistrement pour lequel SQL_DESC_TYPE a la valeur SQL_SS_TABLE.</span><span class="sxs-lookup"><span data-stu-id="21fb1-106">Table-valued parameter columns are only available when the descriptor header field SQL_SOPT_SS_PARAM_FOCUS is set to the ordinal of a record that has SQL_DESC_TYPE set to SQL_SS_TABLE.</span></span> <span data-ttu-id="21fb1-107">Pour plus d'informations sur SQL_SOPT_SS_PARAM_FOCUS, consultez [SQLSetStmtAttr](sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="21fb1-107">For more information about SQL_SOPT_SS_PARAM_FOCUS, see [SQLSetStmtAttr](sqlsetstmtattr.md).</span></span>  
  
 <span data-ttu-id="21fb1-108">Si vous tentez de définir SQL_SOPT_SS_PARAM_FOCUS sur l’ordinal d’un paramètre qui n’est pas un paramètre table, SQLSetStmtAttr retourne SQL_ERROR et un enregistrement de diagnostic est créé avec SQLSTATE = HY024 et le message « valeur d’attribut non valide ».</span><span class="sxs-lookup"><span data-stu-id="21fb1-108">If an attempt is made to set SQL_SOPT_SS_PARAM_FOCUS to the ordinal of a parameter that is not a table-valued parameter, SQLSetStmtAttr returns SQL_ERROR, and a diagnostic record is created with SQLSTATE = HY024 and the message "Invalid attribute value".</span></span> <span data-ttu-id="21fb1-109">SQL_SOPT_SS_PARAM_FOCUS n'est pas modifié quand SQL_ERROR est retourné.</span><span class="sxs-lookup"><span data-stu-id="21fb1-109">SQL_SOPT_SS_PARAM_FOCUS is not changed when SQL_ERROR is returned.</span></span>  
  
 <span data-ttu-id="21fb1-110">La définition de SQL_SOPT_SS_PARAM_FOCUS sur 0 restaure l'accès aux enregistrements de descripteurs pour les paramètres.</span><span class="sxs-lookup"><span data-stu-id="21fb1-110">Setting SQL_SOPT_SS_PARAM_FOCUS to 0 restores access to descriptor records for parameters.</span></span>  
  
 <span data-ttu-id="21fb1-111">Pour plus d’informations sur les paramètres table, consultez [paramètres table &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="21fb1-111">For more information about table-valued parameters, see [Table-Valued Parameters &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span></span>  
  
## <a name="sqlsetdescfield-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="21fb1-112">Prise en charge par SQLSetDescField des fonctionnalités de date et heure améliorées</span><span class="sxs-lookup"><span data-stu-id="21fb1-112">SQLSetDescField Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="21fb1-113">Les fonctionnalités de date/heure ont été améliorées dans ODBC.</span><span class="sxs-lookup"><span data-stu-id="21fb1-113">Date/time features have been enhanced in ODBC.</span></span> <span data-ttu-id="21fb1-114">Pour plus d'informations sur le champ de descripteur disponible avec les nouveaux types de date/heure, consultez [Parameter and Result Metadata](../native-client-odbc-date-time/metadata-parameter-and-result.md).</span><span class="sxs-lookup"><span data-stu-id="21fb1-114">For information about the descriptor field provided for the new date/time types, see [Parameter and Result Metadata](../native-client-odbc-date-time/metadata-parameter-and-result.md).</span></span>  
  
 <span data-ttu-id="21fb1-115">Pour plus d’informations, consultez améliorations de la [date et de l’heure &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="21fb1-115">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="sqlsetdescfield-support-for-large-clr-udts"></a><span data-ttu-id="21fb1-116">Prise en charge par SQLSetDescField des grands types CLR définis par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="21fb1-116">SQLSetDescField Support for Large CLR UDTs</span></span>  
 <span data-ttu-id="21fb1-117">SQLSetDescField prend en charge les types CLR volumineux définis par l’utilisateur (UDT).</span><span class="sxs-lookup"><span data-stu-id="21fb1-117">SQLSetDescField supports large CLR user-defined types (UDTs).</span></span> <span data-ttu-id="21fb1-118">Pour plus d’informations, consultez [types CLR volumineux définis par l’utilisateur &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="21fb1-118">For more information, see [Large CLR User-Defined Types &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span></span>  
  
## <a name="sqlsetdescfield-support-for-sparse-columns"></a><span data-ttu-id="21fb1-119">Prise en charge par SQLSetDescField des colonnes éparses</span><span class="sxs-lookup"><span data-stu-id="21fb1-119">SQLSetDescField Support for Sparse Columns</span></span>  
 <span data-ttu-id="21fb1-120">SQLSetDecField peut être utilisé pour définir SQL_SOPT_SS_NAME_SCOPE dans le descripteur de paramètre d’application (APD) aux valeurs SQL_SS_NAME_SCOPE_EXTENDED et SQL_SS_NAME_SCOPE_SPARSE_COLUMN_SET.</span><span class="sxs-lookup"><span data-stu-id="21fb1-120">SQLSetDecField can be used to set SQL_SOPT_SS_NAME_SCOPE in the application parameter descriptor (APD) to the values SQL_SS_NAME_SCOPE_EXTENDED and SQL_SS_NAME_SCOPE_SPARSE_COLUMN_SET.</span></span>  
  
 <span data-ttu-id="21fb1-121">Pour plus d’informations, consultez la rubrique [prise en charge des colonnes éparses &#40;ODBC&#41;](../native-client/odbc/sparse-columns-support-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="21fb1-121">For more information, see [Sparse Columns Support &#40;ODBC&#41;](../native-client/odbc/sparse-columns-support-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21fb1-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="21fb1-122">See Also</span></span>  
 <span data-ttu-id="21fb1-123">[SQLSetDescField](https://go.microsoft.com/fwlink/?LinkId=80705) </span><span class="sxs-lookup"><span data-stu-id="21fb1-123">[SQLSetDescField](https://go.microsoft.com/fwlink/?LinkId=80705) </span></span>  
 [<span data-ttu-id="21fb1-124">Détails de l’implémentation d’API ODBC</span><span class="sxs-lookup"><span data-stu-id="21fb1-124">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
