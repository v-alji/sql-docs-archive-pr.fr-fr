---
title: bcp_sendrow | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_sendrow
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_sendrow function
ms.assetid: ddbdb4bd-ad4e-4bf1-9a75-656aa26ce10a
author: rothja
ms.author: jroth
ms.openlocfilehash: 3d2f55486ba57101ffc7b1903de5d19ac8eaaca2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603496"
---
# <a name="bcp_sendrow"></a><span data-ttu-id="f9019-102">bcp_sendrow</span><span class="sxs-lookup"><span data-stu-id="f9019-102">bcp_sendrow</span></span>
  <span data-ttu-id="f9019-103">Envoie une ligne de données à partir de variables de programme à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9019-103">Sends a row of data from program variables to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9019-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="f9019-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_sendrow (  
    HDBC   
hdbc  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="f9019-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="f9019-105">Arguments</span></span>  
 <span data-ttu-id="f9019-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="f9019-106">*hdbc*</span></span>  
 <span data-ttu-id="f9019-107">Handle de connexion ODBC compatible avec la copie en bloc.</span><span class="sxs-lookup"><span data-stu-id="f9019-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="f9019-108">Retours</span><span class="sxs-lookup"><span data-stu-id="f9019-108">Returns</span></span>  
 <span data-ttu-id="f9019-109">SUCCEED ou FAIL.</span><span class="sxs-lookup"><span data-stu-id="f9019-109">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f9019-110">Notes</span><span class="sxs-lookup"><span data-stu-id="f9019-110">Remarks</span></span>  
 <span data-ttu-id="f9019-111">La fonction **bcp_sendrow** génère une ligne à partir de variables de programme et l'envoie à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9019-111">The **bcp_sendrow** function builds a row from program variables and sends it to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="f9019-112">Avant d'appeler **bcp_sendrow**, vous devez effectuer des appels à [bcp_bind](bcp-bind.md) pour spécifier les variables de programme qui contiennent des données de ligne.</span><span class="sxs-lookup"><span data-stu-id="f9019-112">Before calling **bcp_sendrow**, you must make calls to [bcp_bind](bcp-bind.md) to specify the program variables containing row data.</span></span>  
  
 <span data-ttu-id="f9019-113">Si **bcp_bind** est appelé en spécifiant un type de données long de longueur variable (par exemple, un paramètre *eDataType* SQLTEXT et un paramètre *pData* nonNULL), **bcp_sendrow** envoie la valeur de données entière, comme pour tout autre type de données.</span><span class="sxs-lookup"><span data-stu-id="f9019-113">If **bcp_bind** is called specifying a long, variable-length data type, for example, an *eDataType* parameter of SQLTEXT and a nonNULL *pData* parameter, **bcp_sendrow** sends the entiredata value, just as it does for any other data type.</span></span> <span data-ttu-id="f9019-114">Toutefois, si **bcp_bind** possède un paramètre *pData* NULL, **bcp_sendrow** redonne le contrôle à l'application immédiatement après que tous les colonnes avec des données spécifiées ont été envoyées à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9019-114">If, however, **bcp_bind** has a NULL *pData* parameter, **bcp_sendrow** returns control to the application immediately after all columns with data specified are sent to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f9019-115">L'application peut ensuite appeler [bcp_moretext](bcp-moretext.md) à plusieurs reprises pour envoyer les données longues de longueur variable à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], segment par segment.</span><span class="sxs-lookup"><span data-stu-id="f9019-115">The application can then call [bcp_moretext](bcp-moretext.md) repeatedly to send the long, variable-length data to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], a chunk at a time.</span></span> <span data-ttu-id="f9019-116">Pour plus d'informations, consultez [bcp_moretext](bcp-moretext.md).</span><span class="sxs-lookup"><span data-stu-id="f9019-116">For more information, see [bcp_moretext](bcp-moretext.md).</span></span>  
  
 <span data-ttu-id="f9019-117">Lorsque **bcp_sendrow** est utilisé pour copier en bloc des lignes à partir de variables de programme dans des tables [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , les lignes sont validées uniquement lorsque l'utilisateur appelle [bcp_batch](bcp-batch.md) ou [bcp_done](bcp-done.md).</span><span class="sxs-lookup"><span data-stu-id="f9019-117">When **bcp_sendrow** is used to bulk copy rows from program variables into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tables, rows are committed only when the user calls [bcp_batch](bcp-batch.md) or [bcp_done](bcp-done.md).</span></span> <span data-ttu-id="f9019-118">L'utilisateur peut choisir d'appeler **bcp_batch** une fois chaque *n* lignes ou lors de creux entre deux périodes de données entrantes.</span><span class="sxs-lookup"><span data-stu-id="f9019-118">The user can choose to call **bcp_batch** once every *n* rows or when there is a lull between periods of incoming data.</span></span> <span data-ttu-id="f9019-119">Si **bcp_batch** n'est jamais appelé, les lignes sont validées lorsque **bcp_done** est appelé.</span><span class="sxs-lookup"><span data-stu-id="f9019-119">If **bcp_batch** is never called, the rows are committed when **bcp_done** is called.</span></span>  
  
 <span data-ttu-id="f9019-120">Pour plus d’informations sur la modification avec rupture dans la copie en bloc à compter de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] , consultez [exécution d’opérations de copie en bloc &#40;ODBC&#41;](../native-client-odbc-bulk-copy-operations/performing-bulk-copy-operations-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="f9019-120">For information about a breaking change in bulk-copying beginning in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], see [Performing Bulk Copy Operations &#40;ODBC&#41;](../native-client-odbc-bulk-copy-operations/performing-bulk-copy-operations-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9019-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f9019-121">See Also</span></span>  
 [<span data-ttu-id="f9019-122">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="f9019-122">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
