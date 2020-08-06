---
title: Type SQL ODBC pour les paramètres table | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL_SS_TABLE
ms.assetid: 6725bfb9-5f10-4115-be09-fd9c9f5779ea
author: rothja
ms.author: jroth
ms.openlocfilehash: c8ed46bf117c9158ae5b60c10ebd89e3d348f77c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612811"
---
# <a name="odbc-sql-type-for-table-valued-parameters"></a><span data-ttu-id="75650-102">type ODBC SQL pour les paramètres table</span><span class="sxs-lookup"><span data-stu-id="75650-102">ODBC SQL Type for Table-Valued Parameters</span></span>
  <span data-ttu-id="75650-103">La prise en charge des paramètres de table est fournie par un nouveau type SQL ODBC, SQL_SS_TABLE.</span><span class="sxs-lookup"><span data-stu-id="75650-103">Support for table-valued parameters is provided by a new ODBC SQL type, SQL_SS_TABLE.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="75650-104">Notes</span><span class="sxs-lookup"><span data-stu-id="75650-104">Remarks</span></span>  
 <span data-ttu-id="75650-105">SQL_SS_TABLE ne peut pas être converti en un autre type de données ODBC ou [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="75650-105">SQL_SS_TABLE cannot be converted to any other ODBC or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type.</span></span>  
  
 <span data-ttu-id="75650-106">Si SQL_SS_TABLE est utilisé comme type de données C dans le paramètre *ValueType* de SQLBindParameter ou si une tentative est faite pour définir SQL_DESC_TYPE dans un enregistrement de descripteur de paramètre d’application (APD) à SQL_SS_TABLE, SQL_ERROR est retourné et un enregistrement de diagnostic est généré avec SQLSTATE = HY003, « type de tampon d’application non valide ».</span><span class="sxs-lookup"><span data-stu-id="75650-106">If SQL_SS_TABLE is used as a C data type in the *ValueType* parameter of SQLBindParameter, or an attempt is made to set SQL_DESC_TYPE in an application parameter descriptor (APD) record to SQL_SS_TABLE, SQL_ERROR is returned and a diagnostic record is generated with SQLSTATE=HY003, "Invalid application buffer type".</span></span>  
  
 <span data-ttu-id="75650-107">Si SQL_DESC_TYPE est défini avec la valeur SQL_SS_TABLE dans un enregistrement IPD et que l'enregistrement APD correspondant n'est pas SQL_C_DEFAULT, SQL_ERROR est retourné et un enregistrement de diagnostic est généré avec SQLSTATE=HY003, « Type de tampon d'application non valide ».</span><span class="sxs-lookup"><span data-stu-id="75650-107">If SQL_DESC_TYPE is set to SQL_SS_TABLE in an IPD record and the corresponding application parameter descriptor record is not SQL_C_DEFAULT, SQL_ERROR is returned and a diagnostic record is generated with SQLSTATE=HY003, "Invalid application buffer type".</span></span> <span data-ttu-id="75650-108">Cela peut se produire avec le *ParameterType* d’un SQLSetDescField, SQLSetDescRec ou SQLBindParameter.</span><span class="sxs-lookup"><span data-stu-id="75650-108">This can occur with the *ParameterType* of a SQLSetDescField, SQLSetDescRec or SQLBindParameter.</span></span>  
  
 <span data-ttu-id="75650-109">Si le paramètre *TargetType* est SQL_SS_TABLE lors de l’appel de SQLGetData, SQL_ERROR est retourné et un enregistrement de diagnostic est généré avec SQLSTATE = HY003, « type de tampon d’application non valide ».</span><span class="sxs-lookup"><span data-stu-id="75650-109">If the *TargetType* parameter is SQL_SS_TABLE when calling SQLGetData, SQL_ERROR is returned and a diagnostic record is generated with SQLSTATE=HY003, "Invalid application buffer type".</span></span>  
  
 <span data-ttu-id="75650-110">Une colonne de paramètre table ne peut pas être liée comme type SQL_SS_TABLE.</span><span class="sxs-lookup"><span data-stu-id="75650-110">A table-valued parameter column cannot be bound as type SQL_SS_TABLE.</span></span> <span data-ttu-id="75650-111">Si `SQLBindParameter` est appelé avec *ParameterType* défini sur SQL_SS_TABLE, SQL_ERROR est retourné et un enregistrement de diagnostic est généré avec SQLSTATE = HY004, « type de données SQL non valide ».</span><span class="sxs-lookup"><span data-stu-id="75650-111">If `SQLBindParameter` is called with *ParameterType* set to SQL_SS_TABLE, SQL_ERROR is returned and a diagnostic record is generated with SQLSTATE=HY004, "Invalid SQL data type".</span></span> <span data-ttu-id="75650-112">Cela peut également se produire avec SQLSetDescField et SQLSetDescRec.</span><span class="sxs-lookup"><span data-stu-id="75650-112">This can also occur with SQLSetDescField and SQLSetDescRec.</span></span>  
  
 <span data-ttu-id="75650-113">Les valeurs des colonnes de paramètre table ont les mêmes options de conversion de données que les paramètres et les colonnes de résultat.</span><span class="sxs-lookup"><span data-stu-id="75650-113">Table-valued parameter column values have the same data conversion options as parameters and result columns.</span></span>  
  
 <span data-ttu-id="75650-114">Un paramètre table ne peut être un paramètre d'entrée que dans [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] ou version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="75650-114">A table-valued parameter can only be an input parameter in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] or later.</span></span> <span data-ttu-id="75650-115">Si une tentative est faite pour définir SQL_DESC_PARAMETER_TYPE sur une valeur autre que SQL_PARAM_INPUT via SQLBindParameter ou SQLSetDescField, SQL_ERROR est retourné et un enregistrement de diagnostic est ajouté à l’instruction avec SQLSTATE = HY105 et le message « type de paramètre non valide ».</span><span class="sxs-lookup"><span data-stu-id="75650-115">If an attempt is made to set SQL_DESC_PARAMETER_TYPE to a value other than SQL_PARAM_INPUT via SQLBindParameter or SQLSetDescField, SQL_ERROR is returned and a diagnostic record is added to the statement with SQLSTATE=HY105 and the message "Invalid parameter type".</span></span>  
  
 <span data-ttu-id="75650-116">Les colonnes de paramètre table ne peuvent pas utiliser SQL_DEFAULT_PARAM dans *StrLen_or_IndPtr*, parce que les valeurs par défaut par ligne ne sont pas prises en charge avec les paramètres table.</span><span class="sxs-lookup"><span data-stu-id="75650-116">Table-valued parameter columns cannot use SQL_DEFAULT_PARAM in *StrLen_or_IndPtr*, because per-row default values are not supported with table-valued parameters.</span></span> <span data-ttu-id="75650-117">À la place, une application peut définir l'attribut de colonne SQL_CA_SS_COL_HAS_DEFAULT_VALUE avec la valeur 1.</span><span class="sxs-lookup"><span data-stu-id="75650-117">Instead, an application can set the column attribute SQL_CA_SS_COL_HAS_DEFAULT_VALUE to 1.</span></span> <span data-ttu-id="75650-118">Cela signifie que la colonne aura des valeurs par défaut pour toutes les lignes.</span><span class="sxs-lookup"><span data-stu-id="75650-118">This means that the column will have default values for all rows.</span></span> <span data-ttu-id="75650-119">Si *StrLen_or_IndPtr* a la valeur SQL_DEFAULT_PARAM, SQLExecute ou SQLExecDirect retourne SQL_ERROR et un enregistrement de diagnostic est ajouté à l’instruction avec SQLSTATE = HY090 et le message « longueur de chaîne ou de mémoire tampon non valide ».</span><span class="sxs-lookup"><span data-stu-id="75650-119">If *StrLen_or_IndPtr* is set to SQL_DEFAULT_PARAM, SQLExecute or SQLExecDirect will return SQL_ERROR, and a diagnostic record will be added to the statement with SQLSTATE=HY090 and the message "Invalid string or buffer length".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75650-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="75650-120">See Also</span></span>  
 [<span data-ttu-id="75650-121">Paramètres table &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="75650-121">Table-Valued Parameters &#40;ODBC&#41;</span></span>](table-valued-parameters-odbc.md)  
  
  
