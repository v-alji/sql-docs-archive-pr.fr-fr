---
title: bcp_collen | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_collen
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_collen function
ms.assetid: faaf1f7a-81f2-4852-a178-56602c33673a
author: rothja
ms.author: jroth
ms.openlocfilehash: 3099e26b0c2cd0d1cfee7578f5b149b812f01765
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709368"
---
# <a name="bcp_collen"></a><span data-ttu-id="d9640-102">bcp_collen</span><span class="sxs-lookup"><span data-stu-id="d9640-102">bcp_collen</span></span>
  <span data-ttu-id="d9640-103">Définit la longueur des données dans la variable de programme pour la copie en bloc actuelle dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d9640-103">Sets the data length in the program variable for the current bulk copy into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9640-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="d9640-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_collen (  
HDBC   
hdbc  
,  
DBINT   
cbData  
,  
INT   
idxServerCol  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="d9640-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="d9640-105">Arguments</span></span>  
 <span data-ttu-id="d9640-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="d9640-106">*hdbc*</span></span>  
 <span data-ttu-id="d9640-107">Handle de connexion ODBC compatible avec la copie en bloc.</span><span class="sxs-lookup"><span data-stu-id="d9640-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="d9640-108">*cbData*</span><span class="sxs-lookup"><span data-stu-id="d9640-108">*cbData*</span></span>  
 <span data-ttu-id="d9640-109">Longueur des données dans la variable de programme, à l'exclusion de la longueur de tout indicateur de longueur ou terminateur.</span><span class="sxs-lookup"><span data-stu-id="d9640-109">Is the length of the data in the program variable, not including the length of any length indicator or terminator.</span></span> <span data-ttu-id="d9640-110">La définition de *cbData* avec la valeur SQL_NULL_DATA indique que toutes les lignes copiées sur le serveur contiennent une valeur NULL pour la colonne.</span><span class="sxs-lookup"><span data-stu-id="d9640-110">Setting *cbData* to SQL_NULL_DATA indicates all rows copied to the server contain a NULL value for the column.</span></span> <span data-ttu-id="d9640-111">La définition de cbData avec la valeur SQL_VARLEN_DATA indique qu'un terminateur de chaîne ou une autre méthode est utilisé pour déterminer la longueur des données copiées.</span><span class="sxs-lookup"><span data-stu-id="d9640-111">Setting it to SQL_VARLEN_DATA indicates that a string terminator or other method is used to determine the length of data copied.</span></span> <span data-ttu-id="d9640-112">S'il existe à la fois un indicateur de longueur et un terminateur, le système utilise celui qui entraîne la copie du moins grand nombre de données.</span><span class="sxs-lookup"><span data-stu-id="d9640-112">If both a length indicator and a terminator exist, the system uses whichever one results in less data being copied.</span></span>  
  
 <span data-ttu-id="d9640-113">*idxServerCol*</span><span class="sxs-lookup"><span data-stu-id="d9640-113">*idxServerCol*</span></span>  
 <span data-ttu-id="d9640-114">Position ordinale de la colonne dans la table vers laquelle les données sont copiées.</span><span class="sxs-lookup"><span data-stu-id="d9640-114">Is the ordinal position of the column in the table to which the data is copied.</span></span> <span data-ttu-id="d9640-115">La première colonne est 1.</span><span class="sxs-lookup"><span data-stu-id="d9640-115">The first column is 1.</span></span> <span data-ttu-id="d9640-116">La position ordinale d'une colonne est indiquée par [SQLColumns](../native-client-odbc-api/sqlcolumns.md).</span><span class="sxs-lookup"><span data-stu-id="d9640-116">The ordinal position of a column is reported by [SQLColumns](../native-client-odbc-api/sqlcolumns.md).</span></span>  
  
## <a name="returns"></a><span data-ttu-id="d9640-117">Retours</span><span class="sxs-lookup"><span data-stu-id="d9640-117">Returns</span></span>  
 <span data-ttu-id="d9640-118">SUCCEED ou FAIL.</span><span class="sxs-lookup"><span data-stu-id="d9640-118">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d9640-119">Notes</span><span class="sxs-lookup"><span data-stu-id="d9640-119">Remarks</span></span>  
 <span data-ttu-id="d9640-120">La fonction **bcp_collen** vous permet de modifier la longueur de données dans la variable de programme pour une colonne particulière lors de la copie de données vers [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] avec [bcp_sendrow](bcp-sendrow.md).</span><span class="sxs-lookup"><span data-stu-id="d9640-120">The **bcp_collen** function allows you to change the data length in the program variable for a particular column when copying data to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with [bcp_sendrow](bcp-sendrow.md).</span></span>  
  
 <span data-ttu-id="d9640-121">Initialement, la longueur de données est déterminée quand [bcp_bind](bcp-bind.md) est appelé.</span><span class="sxs-lookup"><span data-stu-id="d9640-121">Initially, the data length is determined when [bcp_bind](bcp-bind.md) is called.</span></span> <span data-ttu-id="d9640-122">Si la longueur de données change entre des appels à **bcp_sendrow** et qu'aucun préfixe de longueur ou terminateur n'est en cours d'utilisation, vous pouvez appeler **bcp_collen** pour réinitialiser la longueur.</span><span class="sxs-lookup"><span data-stu-id="d9640-122">If the data length changes between calls to **bcp_sendrow** and no length prefix or terminator is being used, you can call **bcp_collen** to reset the length.</span></span> <span data-ttu-id="d9640-123">L'appel suivant à **bcp_sendrow** utilise la longueur définie par l'appel à **bcp_collen**.</span><span class="sxs-lookup"><span data-stu-id="d9640-123">The next call to **bcp_sendrow** uses the length set by the call to **bcp_collen**.</span></span>  
  
 <span data-ttu-id="d9640-124">Vous devez appeler **bcp_collen** une fois pour chaque colonne de la table dont vous voulez modifier la longueur de données.</span><span class="sxs-lookup"><span data-stu-id="d9640-124">You must call **bcp_collen** once for each column in the table whose data length you want to modify.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9640-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d9640-125">See Also</span></span>  
 [<span data-ttu-id="d9640-126">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="d9640-126">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
