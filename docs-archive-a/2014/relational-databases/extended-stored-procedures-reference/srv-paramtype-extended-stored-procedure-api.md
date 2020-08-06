---
title: srv_paramtype (API de procédure stockée étendue) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_paramtype
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_paramtype
ms.assetid: badc6d36-8a87-42b5-b28c-9c4f5ded8552
author: rothja
ms.author: jroth
ms.openlocfilehash: 0c4b4006f8214670e3bd2bddfbaabe917fb9d778
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602842"
---
# <a name="srv_paramtype-extended-stored-procedure-api"></a><span data-ttu-id="4542c-102">srv_paramtype (API de procédure stockée étendue)</span><span class="sxs-lookup"><span data-stu-id="4542c-102">srv_paramtype (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="4542c-103">Utilisez l’intégration CLR à la place.</span><span class="sxs-lookup"><span data-stu-id="4542c-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="4542c-104">Retourne le type de données d'un paramètre d'appel de procédure stockée distante.</span><span class="sxs-lookup"><span data-stu-id="4542c-104">Returns the data type of a remote stored procedure call parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4542c-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="4542c-105">Syntax</span></span>  
  
```  
  
int srv_paramtype (  
SRV_PROC *  
srvproc  
,  
int  
n   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="4542c-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="4542c-106">Arguments</span></span>  
 <span data-ttu-id="4542c-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="4542c-107">*srvproc*</span></span>  
 <span data-ttu-id="4542c-108">Pointeur vers la structure SRV_PROC qui correspond au handle d'une connexion cliente particulière (dans ce cas, le handle qui a reçu l'appel de procédure stockée distante).</span><span class="sxs-lookup"><span data-stu-id="4542c-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure call).</span></span> <span data-ttu-id="4542c-109">La structure contient des informations que la bibliothèque d'API de procédure stockée étendue utilise pour gérer les communications et les données entre l'application et le client.</span><span class="sxs-lookup"><span data-stu-id="4542c-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="4542c-110">*n*</span><span class="sxs-lookup"><span data-stu-id="4542c-110">*n*</span></span>  
 <span data-ttu-id="4542c-111">Indique le numéro du paramètre.</span><span class="sxs-lookup"><span data-stu-id="4542c-111">Indicates the number of the parameter.</span></span> <span data-ttu-id="4542c-112">Le premier paramètre est 1.</span><span class="sxs-lookup"><span data-stu-id="4542c-112">The first parameter is 1.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="4542c-113">Retours</span><span class="sxs-lookup"><span data-stu-id="4542c-113">Returns</span></span>  
 <span data-ttu-id="4542c-114">Une valeur de jeton du type de données du paramètre.</span><span class="sxs-lookup"><span data-stu-id="4542c-114">A token value for the data type of the parameter.</span></span> <span data-ttu-id="4542c-115">Pour plus d’informations sur les types de données, consultez [Types de données &#40;API de procédure stockée étendue&#41;](data-types-extended-stored-procedure-api.md).</span><span class="sxs-lookup"><span data-stu-id="4542c-115">For information about data types, see [Data Types &#40;Extended Stored Procedure API&#41;](data-types-extended-stored-procedure-api.md).</span></span> <span data-ttu-id="4542c-116">En l’absence du *n*ième paramètre ou d’une procédure stockée distante, la valeur -1 est retournée.</span><span class="sxs-lookup"><span data-stu-id="4542c-116">If there is no *n*th parameter or if there is no remote stored procedure, it returns - 1.</span></span>  
  
 <span data-ttu-id="4542c-117">Cette fonction retourne les valeurs suivantes, si le paramètre est l’un des [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] types de données.</span><span class="sxs-lookup"><span data-stu-id="4542c-117">This function returns the following values, if the parameter is one of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] data types.</span></span>  
  
|<span data-ttu-id="4542c-118">Nouveaux types de données</span><span class="sxs-lookup"><span data-stu-id="4542c-118">New data types</span></span>|<span data-ttu-id="4542c-119">Valeur retournée</span><span class="sxs-lookup"><span data-stu-id="4542c-119">Return value</span></span>|  
|--------------------|------------------|  
|`BITN`|<span data-ttu-id="4542c-120">SRVBIT</span><span class="sxs-lookup"><span data-stu-id="4542c-120">SRVBIT</span></span>|  
|`BIGVARCHAR`|<span data-ttu-id="4542c-121">VARCHAR</span><span class="sxs-lookup"><span data-stu-id="4542c-121">VARCHAR</span></span>|  
|`BIGCHAR`|<span data-ttu-id="4542c-122">CHAR</span><span class="sxs-lookup"><span data-stu-id="4542c-122">CHAR</span></span>|  
|`BIGBINARY`|<span data-ttu-id="4542c-123">BINARY</span><span class="sxs-lookup"><span data-stu-id="4542c-123">BINARY</span></span>|  
|`BIGVARBINARY`|<span data-ttu-id="4542c-124">VARBINARY</span><span class="sxs-lookup"><span data-stu-id="4542c-124">VARBINARY</span></span>|  
|`NCHAR`|<span data-ttu-id="4542c-125">CHAR</span><span class="sxs-lookup"><span data-stu-id="4542c-125">CHAR</span></span>|  
|`NVARCHAR`|<span data-ttu-id="4542c-126">VARCHAR</span><span class="sxs-lookup"><span data-stu-id="4542c-126">VARCHAR</span></span>|  
|`NTEXT`|<span data-ttu-id="4542c-127">-1</span><span class="sxs-lookup"><span data-stu-id="4542c-127">-1</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4542c-128">Notes</span><span class="sxs-lookup"><span data-stu-id="4542c-128">Remarks</span></span>  
 <span data-ttu-id="4542c-129">Quand un appel de procédure stockée distante est effectué avec des paramètres, ceux-ci peuvent être passés par nom ou par position (sans nom).</span><span class="sxs-lookup"><span data-stu-id="4542c-129">When a remote stored procedure call is made with parameters, the parameters can be passed either by name or by position (unnamed).</span></span> <span data-ttu-id="4542c-130">Si l'appel de procédure stockée distante est effectué avec certains paramètres passés par nom et certains passés par position, une erreur se produit.</span><span class="sxs-lookup"><span data-stu-id="4542c-130">If the remote stored procedure call is made with some parameters passed by name and some passed by position, an error occurs.</span></span> <span data-ttu-id="4542c-131">Le gestionnaire de SRV_RPC est toujours appelé, mais il apparaît comme s’il n’y avait aucun paramètre et **srv_rpcparams** retourne 0.</span><span class="sxs-lookup"><span data-stu-id="4542c-131">The SRV_RPC handler is still called, but it appears as if there were no parameters and **srv_rpcparams** returns 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4542c-132">Il est préférable d'examiner avec soin le code source des procédures stockées étendues et de tester les DLL compilées avant de les installer sur un serveur de production.</span><span class="sxs-lookup"><span data-stu-id="4542c-132">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="4542c-133">Pour plus d'informations sur l'examen et les tests de sécurité, consultez ce [site Web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="4542c-133">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4542c-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4542c-134">See Also</span></span>  
 <span data-ttu-id="4542c-135">[srv_paraminfo &#40;API de procédure stockée étendue&#41;](srv-paraminfo-extended-stored-procedure-api.md) </span><span class="sxs-lookup"><span data-stu-id="4542c-135">[srv_paraminfo &#40;Extended Stored Procedure API&#41;](srv-paraminfo-extended-stored-procedure-api.md) </span></span>  
 [<span data-ttu-id="4542c-136">srv_rpcparams &#40;API de procédure stockée étendue&#41;</span><span class="sxs-lookup"><span data-stu-id="4542c-136">srv_rpcparams &#40;Extended Stored Procedure API&#41;</span></span>](srv-rpcparams-extended-stored-procedure-api.md)  
  
  
