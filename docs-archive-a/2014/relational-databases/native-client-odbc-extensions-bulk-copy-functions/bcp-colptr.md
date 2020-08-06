---
title: bcp_colptr | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_colptr
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_colptr function
ms.assetid: 02ece13e-1da3-4f9d-b860-3177e43d2471
author: rothja
ms.author: jroth
ms.openlocfilehash: 8b725ace58ee1768fbca1a433cdea27e3e0e546e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709372"
---
# <a name="bcp_colptr"></a><span data-ttu-id="664b2-102">bcp_colptr</span><span class="sxs-lookup"><span data-stu-id="664b2-102">bcp_colptr</span></span>
  <span data-ttu-id="664b2-103">Définit l'adresse de données de variable de programme pour la copie actuelle dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="664b2-103">Sets the program variable data address for the current copy into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="664b2-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="664b2-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_colptr (  
HDBC   
hdbc  
,  
LPCBYTE   
pData  
,  
INT   
idxServerCol  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="664b2-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="664b2-105">Arguments</span></span>  
 <span data-ttu-id="664b2-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="664b2-106">*hdbc*</span></span>  
 <span data-ttu-id="664b2-107">Handle de connexion ODBC compatible avec la copie en bloc.</span><span class="sxs-lookup"><span data-stu-id="664b2-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="664b2-108">*pData*</span><span class="sxs-lookup"><span data-stu-id="664b2-108">*pData*</span></span>  
 <span data-ttu-id="664b2-109">Pointeur vers les données à copier.</span><span class="sxs-lookup"><span data-stu-id="664b2-109">Is a pointer to the data to copy.</span></span> <span data-ttu-id="664b2-110">Si le type de données lié est un type de valeur élevée (tel que SQLTEXT ou SQLIMAGE), *pData* peut être null.</span><span class="sxs-lookup"><span data-stu-id="664b2-110">If the bound data type is large value type (such as SQLTEXT or SQLIMAGE), *pData* can be NULL.</span></span> <span data-ttu-id="664b2-111">Un *pData* null indique que des valeurs de données longues sont envoyées à SQL Server dans des segments à l’aide de [bcp_moretext](bcp-moretext.md).</span><span class="sxs-lookup"><span data-stu-id="664b2-111">A NULL *pData* indicates long data values will be sent to SQL Server in chunks using [bcp_moretext](bcp-moretext.md).</span></span>  
  
 <span data-ttu-id="664b2-112">Si *pData* a la valeur null et que la colonne correspondant au champ lié n’est pas de type valeur élevée, **bcp_colptr** échoue.</span><span class="sxs-lookup"><span data-stu-id="664b2-112">If *pData* is set to NULL and the column corresponding to the bound field is not a large value type, **bcp_colptr** fails.</span></span>  
  
 <span data-ttu-id="664b2-113">Pour plus d’informations sur les types de valeur élevée, consultez [bcp_bind](bcp-bind.md)**.**</span><span class="sxs-lookup"><span data-stu-id="664b2-113">For more information on large value types, see [bcp_bind](bcp-bind.md)**.**</span></span>  
  
 <span data-ttu-id="664b2-114">*idxServerCol*</span><span class="sxs-lookup"><span data-stu-id="664b2-114">*idxServerCol*</span></span>  
 <span data-ttu-id="664b2-115">Position ordinale de la colonne dans la table de base de données vers laquelle les données sont copiées.</span><span class="sxs-lookup"><span data-stu-id="664b2-115">Is the ordinal position of the column in the database table to which the data is copied.</span></span> <span data-ttu-id="664b2-116">La première colonne d'une table est la colonne 1.</span><span class="sxs-lookup"><span data-stu-id="664b2-116">The first column in a table is column 1.</span></span> <span data-ttu-id="664b2-117">La position ordinale d'une colonne est indiquée par [SQLColumns](../native-client-odbc-api/sqlcolumns.md).</span><span class="sxs-lookup"><span data-stu-id="664b2-117">The ordinal position of a column is reported by [SQLColumns](../native-client-odbc-api/sqlcolumns.md).</span></span>  
  
## <a name="returns"></a><span data-ttu-id="664b2-118">Retours</span><span class="sxs-lookup"><span data-stu-id="664b2-118">Returns</span></span>  
 <span data-ttu-id="664b2-119">SUCCEED ou FAIL.</span><span class="sxs-lookup"><span data-stu-id="664b2-119">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="664b2-120">Notes</span><span class="sxs-lookup"><span data-stu-id="664b2-120">Remarks</span></span>  
 <span data-ttu-id="664b2-121">La fonction **bcp_colptr** vous permet de modifier l’adresse des données sources pour une colonne particulière lors de la copie des données vers SQL Server avec [bcp_sendrow](bcp-sendrow.md).</span><span class="sxs-lookup"><span data-stu-id="664b2-121">The **bcp_colptr** function allows you to change the address of source data for a particular column when copying data to SQL Server with [bcp_sendrow](bcp-sendrow.md).</span></span>  
  
 <span data-ttu-id="664b2-122">Initialement, le pointeur vers les données utilisateur est défini par un appel à **bcp_bind**.</span><span class="sxs-lookup"><span data-stu-id="664b2-122">Initially, the pointer to user data is set by a call to **bcp_bind**.</span></span> <span data-ttu-id="664b2-123">Si l’adresse des données de variable de programme change entre les appels à **bcp_sendrow**, vous pouvez appeler **bcp_colptr** pour réinitialiser le pointeur vers les données.</span><span class="sxs-lookup"><span data-stu-id="664b2-123">If the program variable data address changes between calls to **bcp_sendrow**, you can call **bcp_colptr** to reset the pointer to the data.</span></span> <span data-ttu-id="664b2-124">L’appel suivant à **bcp_sendrow** envoie les données adressées par l’appel à **bcp_colptr**.</span><span class="sxs-lookup"><span data-stu-id="664b2-124">The next call to **bcp_sendrow** sends the data addressed by the call to **bcp_colptr**.</span></span>  
  
 <span data-ttu-id="664b2-125">Il doit y avoir un appel de **bcp_colptr** distinct pour chaque colonne de la table dont vous souhaitez modifier l’adresse de données.</span><span class="sxs-lookup"><span data-stu-id="664b2-125">There must be a separate **bcp_colptr** call for every column in the table whose data address you want to modify.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="664b2-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="664b2-126">See Also</span></span>  
 [<span data-ttu-id="664b2-127">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="664b2-127">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
