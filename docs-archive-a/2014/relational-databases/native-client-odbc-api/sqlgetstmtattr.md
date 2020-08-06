---
title: SQLGetStmtAttr | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLGetStmtAttr function
ms.assetid: e64f4f94-eb73-4477-9745-080b6cbdc751
author: rothja
ms.author: jroth
ms.openlocfilehash: f1f9b6a0c0668540b566c9b3d7ede781c97a1dbf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610630"
---
# <a name="sqlgetstmtattr"></a><span data-ttu-id="ce671-102">SQLGetStmtAttr</span><span class="sxs-lookup"><span data-stu-id="ce671-102">SQLGetStmtAttr</span></span>
  <span data-ttu-id="ce671-103">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pilote ODBC Native Client étend SQLGetStmtAttr pour exposer des attributs d’instruction spécifiques au pilote.</span><span class="sxs-lookup"><span data-stu-id="ce671-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver extends SQLGetStmtAttr to expose driver-specific statement attributes.</span></span>  
  
 <span data-ttu-id="ce671-104">[SQLSetStmtAttr](sqlsetstmtattr.md) répertorie les attributs d'instruction qui sont à la fois accessibles en lecture et en écriture.</span><span class="sxs-lookup"><span data-stu-id="ce671-104">[SQLSetStmtAttr](sqlsetstmtattr.md) lists statement attributes that are both read and write.</span></span> <span data-ttu-id="ce671-105">Cette rubrique dresse la liste des attributs d'instruction accessibles en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="ce671-105">This topic lists the read only statement attributes.</span></span>  
  
## <a name="sql_sopt_ss_current_command"></a><span data-ttu-id="ce671-106">SQL_SOPT_SS_CURRENT_COMMAND</span><span class="sxs-lookup"><span data-stu-id="ce671-106">SQL_SOPT_SS_CURRENT_COMMAND</span></span>  
 <span data-ttu-id="ce671-107">L'attribut SQL_SOPT_SS_CURRENT_COMMAND expose la commande active d'un lot de commandes.</span><span class="sxs-lookup"><span data-stu-id="ce671-107">The SQL_SOPT_SS_CURRENT_COMMAND attribute exposes the current command of a command batch.</span></span> <span data-ttu-id="ce671-108">La valeur retournée est un entier qui spécifie l'emplacement de la commande dans le lot.</span><span class="sxs-lookup"><span data-stu-id="ce671-108">The return is an integer that specifies the location of the command in the batch.</span></span> <span data-ttu-id="ce671-109">La valeur de *ValuePtr* est de type SQLLEN.</span><span class="sxs-lookup"><span data-stu-id="ce671-109">The *ValuePtr* value is of type SQLLEN.</span></span>  
  
## <a name="sql_sopt_ss_nocount_status"></a><span data-ttu-id="ce671-110">SQL_SOPT_SS_NOCOUNT_STATUS</span><span class="sxs-lookup"><span data-stu-id="ce671-110">SQL_SOPT_SS_NOCOUNT_STATUS</span></span>  
 <span data-ttu-id="ce671-111">L'attribut SQL_SOPT_SS_NOCOUNT_STATUS indique le paramètre actif de l'option NOCOUNT, qui contrôle si [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] signale le nombre de lignes affectées par une instruction lorsque [SQLRowCount](sqlrowcount.md) est appelé.</span><span class="sxs-lookup"><span data-stu-id="ce671-111">The SQL_SOPT_SS_NOCOUNT_STATUS attribute indicates the current setting of the NOCOUNT option, which controls whether [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] reports the numbers of rows affected by a statement when [SQLRowCount](sqlrowcount.md) is called.</span></span> <span data-ttu-id="ce671-112">La valeur de *ValuePtr* est de type SQLLEN.</span><span class="sxs-lookup"><span data-stu-id="ce671-112">The *ValuePtr* value is of type SQLLEN.</span></span>  
  
|<span data-ttu-id="ce671-113">Valeur</span><span class="sxs-lookup"><span data-stu-id="ce671-113">Value</span></span>|<span data-ttu-id="ce671-114">Description</span><span class="sxs-lookup"><span data-stu-id="ce671-114">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ce671-115">SQL_NC_OFF</span><span class="sxs-lookup"><span data-stu-id="ce671-115">SQL_NC_OFF</span></span>|<span data-ttu-id="ce671-116">NOCOUNT a la valeur OFF.</span><span class="sxs-lookup"><span data-stu-id="ce671-116">NOCOUNT is OFF.</span></span> <span data-ttu-id="ce671-117">SQLRowCount retourne le nombre de lignes affectées.</span><span class="sxs-lookup"><span data-stu-id="ce671-117">SQLRowCount returns number of rows affected.</span></span>|  
|<span data-ttu-id="ce671-118">SQL_NC_ON</span><span class="sxs-lookup"><span data-stu-id="ce671-118">SQL_NC_ON</span></span>|<span data-ttu-id="ce671-119">NOCOUNT a la valeur ON.</span><span class="sxs-lookup"><span data-stu-id="ce671-119">NOCOUNT is ON.</span></span> <span data-ttu-id="ce671-120">Le nombre de lignes affectées n’est pas retourné par SQLRowCount et la valeur retournée est 0.</span><span class="sxs-lookup"><span data-stu-id="ce671-120">The number of rows affected is not returned by SQLRowCount and the returned value is 0.</span></span>|  
  
 <span data-ttu-id="ce671-121">Si SQLRowCount retourne 0, l’application doit tester SQL_SOPT_SS_NOCOUNT_STATUS.</span><span class="sxs-lookup"><span data-stu-id="ce671-121">If SQLRowCount returns 0, the application should test SQL_SOPT_SS_NOCOUNT_STATUS.</span></span> <span data-ttu-id="ce671-122">Si SQL_NC_ON est retourné, la valeur 0 de SQLRowCount indique uniquement que n' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a pas retourné de nombre de lignes.</span><span class="sxs-lookup"><span data-stu-id="ce671-122">If SQL_NC_ON is returned, the value of 0 from SQLRowCount only indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has not returned a row count.</span></span> <span data-ttu-id="ce671-123">Si SQL_NC_OFF est retourné, cela signifie que l'option NOCOUNT est désactivée et la valeur 0 de SQLRowCount indique que l'instruction n'a affecté aucune ligne.</span><span class="sxs-lookup"><span data-stu-id="ce671-123">If SQL_NC_OFF is returned, it means that NOCOUNT is off and the value of 0 from SQLRowCount indicates that the statement did not affect any rows.</span></span>  
  
 <span data-ttu-id="ce671-124">Les applications ne doivent pas afficher la valeur de SQLRowCount quand SQL_SOPT_SS_NOCOUNT_STATUS a la valeur SQL_NC_OFF.</span><span class="sxs-lookup"><span data-stu-id="ce671-124">Applications should not display the value of SQLRowCount when SQL_SOPT_SS_NOCOUNT_STATUS is SQL_NC_OFF.</span></span> <span data-ttu-id="ce671-125">Les lots ou procédures stockées de grande taille peuvent contenir plusieurs instructions SET NOCOUNT. Il n'est donc pas possible de supposer que SQL_SOPT_SS_NOCOUNT_STATUS reste constant.</span><span class="sxs-lookup"><span data-stu-id="ce671-125">Large batches or stored procedures can contain multiple SET NOCOUNT statements, so it cannot be assumed that SQL_SOPT_SS_NOCOUNT_STATUS remains constant.</span></span> <span data-ttu-id="ce671-126">Cette option doit être testée à chaque fois que SQLRowCount retourne 0.</span><span class="sxs-lookup"><span data-stu-id="ce671-126">This option should be tested each time SQLRowCount returns 0.</span></span>  
  
## <a name="sql_sopt_ss_querynotification_msgtext"></a><span data-ttu-id="ce671-127">SQL_SOPT_SS_QUERYNOTIFICATION_MSGTEXT</span><span class="sxs-lookup"><span data-stu-id="ce671-127">SQL_SOPT_SS_QUERYNOTIFICATION_MSGTEXT</span></span>  
 <span data-ttu-id="ce671-128">L'attribut SQL_SOPT_SS_QUERYNOTIFICATION_MSGTEXT retourne le texte du message pour la demande de notification de requête.</span><span class="sxs-lookup"><span data-stu-id="ce671-128">The SQL_SOPT_SS_QUERYNOTIFICATION_MSGTEXT attribute returns the message text for the query notification request.</span></span>  
  
## <a name="sqlgetstmtattr-and-table-valued-parameters"></a><span data-ttu-id="ce671-129">SQLGetStmtAttr et paramètres table</span><span class="sxs-lookup"><span data-stu-id="ce671-129">SQLGetStmtAttr and Table-valued Parameters</span></span>  
 <span data-ttu-id="ce671-130">SQLGetStmtAttr peut être appelé pour extraire la valeur de SQL_SOPT_SS_PARAM_FOCUS dans le descripteur de paramètre d’application (APD) lors de l’utilisation de paramètres table.</span><span class="sxs-lookup"><span data-stu-id="ce671-130">SQLGetStmtAttr can be called to get the value of SQL_SOPT_SS_PARAM_FOCUS in the application parameter descriptor (APD) when working with table-valued parameters.</span></span> <span data-ttu-id="ce671-131">Pour plus d'informations sur SQL_SOPT_SS_PARAM_FOCUS, consultez [SQLSetStmtAttr](sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="ce671-131">For more information on SQL_SOPT_SS_PARAM_FOCUS, see [SQLSetStmtAttr](sqlsetstmtattr.md).</span></span>  
  
 <span data-ttu-id="ce671-132">Pour plus d’informations sur les paramètres table, consultez [paramètres table &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="ce671-132">For more information about table-valued parameters, see [Table-Valued Parameters &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce671-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ce671-133">See Also</span></span>  
 <span data-ttu-id="ce671-134">[SQLSetStmtAttr, fonction](https://go.microsoft.com/fwlink/?LinkId=59370) </span><span class="sxs-lookup"><span data-stu-id="ce671-134">[SQLSetStmtAttr Function](https://go.microsoft.com/fwlink/?LinkId=59370) </span></span>  
 [<span data-ttu-id="ce671-135">Détails de l’implémentation d’API ODBC</span><span class="sxs-lookup"><span data-stu-id="ce671-135">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
