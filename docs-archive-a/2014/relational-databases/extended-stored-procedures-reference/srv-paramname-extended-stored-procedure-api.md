---
title: srv_paramname (API de procédure stockée étendue) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_paramname
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_paramname
ms.assetid: 1a53d707-7b06-49cc-a0df-ac727cfe953f
author: rothja
ms.author: jroth
ms.openlocfilehash: 2227ac3d46efe7d09abc05964248229f3533d42d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709484"
---
# <a name="srv_paramname-extended-stored-procedure-api"></a><span data-ttu-id="4d4c3-102">srv_paramname (API de procédure stockée étendue)</span><span class="sxs-lookup"><span data-stu-id="4d4c3-102">srv_paramname (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="4d4c3-103">Utilisez l’intégration CLR à la place.</span><span class="sxs-lookup"><span data-stu-id="4d4c3-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="4d4c3-104">Retourne le nom d'un paramètre d'appel de procédure stockée distante.</span><span class="sxs-lookup"><span data-stu-id="4d4c3-104">Returns the name of a remote stored procedure call parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d4c3-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="4d4c3-105">Syntax</span></span>  
  
```  
  
DBCHAR * srv_paramname (  
SRV_PROC * srvproc,intn, int *len );  
```  
  
## <a name="arguments"></a><span data-ttu-id="4d4c3-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="4d4c3-106">Arguments</span></span>  
 <span data-ttu-id="4d4c3-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="4d4c3-107">*srvproc*</span></span>  
 <span data-ttu-id="4d4c3-108">Pointeur vers la structure SRV_PROC qui correspond au handle d'une connexion cliente particulière (dans ce cas, le handle qui a reçu l'appel de procédure stockée distante).</span><span class="sxs-lookup"><span data-stu-id="4d4c3-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure call).</span></span> <span data-ttu-id="4d4c3-109">La structure contient des informations que la bibliothèque d'API de procédure stockée étendue utilise pour gérer les communications et les données entre l'application et le client.</span><span class="sxs-lookup"><span data-stu-id="4d4c3-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="4d4c3-110">*n*</span><span class="sxs-lookup"><span data-stu-id="4d4c3-110">*n*</span></span>  
 <span data-ttu-id="4d4c3-111">Indique le numéro du paramètre.</span><span class="sxs-lookup"><span data-stu-id="4d4c3-111">Indicates the number of the parameter.</span></span> <span data-ttu-id="4d4c3-112">Le premier paramètre est 1.</span><span class="sxs-lookup"><span data-stu-id="4d4c3-112">The first parameter is 1.</span></span>  
  
 <span data-ttu-id="4d4c3-113">*Len*</span><span class="sxs-lookup"><span data-stu-id="4d4c3-113">*len*</span></span>  
 <span data-ttu-id="4d4c3-114">Fournit un pointeur vers une variable `int` qui contient la longueur, en octets, du nom de paramètre.</span><span class="sxs-lookup"><span data-stu-id="4d4c3-114">Provides a pointer to an `int` variable that contains the length, in bytes, of the parameter name.</span></span> <span data-ttu-id="4d4c3-115">Si *len* est NULL, la longueur du nom de paramètre de procédure stockée distante n’est pas retournée.</span><span class="sxs-lookup"><span data-stu-id="4d4c3-115">If *len* is NULL, the length of the remote stored procedure parameter name is not returned.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="4d4c3-116">Retours</span><span class="sxs-lookup"><span data-stu-id="4d4c3-116">Returns</span></span>  
 <span data-ttu-id="4d4c3-117">Pointeur vers une chaîne de caractères terminée par le caractère NULL qui contient le nom du paramètre.</span><span class="sxs-lookup"><span data-stu-id="4d4c3-117">A pointer to a null-terminated character string that contains the parameter name.</span></span> <span data-ttu-id="4d4c3-118">La longueur du nom de paramètre est stockée dans *len*.</span><span class="sxs-lookup"><span data-stu-id="4d4c3-118">The length of the parameter name is stored in *len*.</span></span> <span data-ttu-id="4d4c3-119">S’il n’y a aucun *n*ième paramètre ni aucune procédure stockée distante, la valeur NULL est retournée, la valeur -1 est affectée à *len* et un message d’erreur d’information est envoyé.</span><span class="sxs-lookup"><span data-stu-id="4d4c3-119">If there is no *n*th parameter or no remote stored procedure, it returns NULL, *len* is set to -1, and an informational error message is sent.</span></span> <span data-ttu-id="4d4c3-120">Si le nom de paramètre est NULL, la valeur 0 est affectée à *len* et une chaîne vide se terminant par NULL est retournée.</span><span class="sxs-lookup"><span data-stu-id="4d4c3-120">If the parameter name is NULL, *len* is set to 0 and a null-terminated empty string is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4d4c3-121">Notes</span><span class="sxs-lookup"><span data-stu-id="4d4c3-121">Remarks</span></span>  
 <span data-ttu-id="4d4c3-122">Cette fonction obtient le nom d'un paramètre d'appel de procédure stockée distante.</span><span class="sxs-lookup"><span data-stu-id="4d4c3-122">This function gets the name of a remote stored procedure call parameter.</span></span> <span data-ttu-id="4d4c3-123">Quand un appel de procédure stockée distante est effectué avec des paramètres, ceux-ci peuvent être passés par nom ou par position (sans nom).</span><span class="sxs-lookup"><span data-stu-id="4d4c3-123">When a remote stored procedure call is made with parameters, the parameters can be passed either by name or by position (unnamed).</span></span> <span data-ttu-id="4d4c3-124">Si l'appel de procédure stockée distante est effectué avec certains paramètres passés par nom et certains passés par position, une erreur se produit.</span><span class="sxs-lookup"><span data-stu-id="4d4c3-124">If the remote stored procedure call is made with some parameters passed by name and some passed by position, an error occurs.</span></span> <span data-ttu-id="4d4c3-125">Le gestionnaire SRV_RPC est tout de même appelé, mais il apparaît comme s’il n’y avait aucun paramètre et **srv_rpcparams** retourne 0.</span><span class="sxs-lookup"><span data-stu-id="4d4c3-125">The SRV_RPC handler is still called, but it appears as if there were no parameters, and **srv_rpcparams** returns 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4d4c3-126">Il est préférable d'examiner avec soin le code source des procédures stockées étendues et de tester les DLL compilées avant de les installer sur un serveur de production.</span><span class="sxs-lookup"><span data-stu-id="4d4c3-126">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="4d4c3-127">Pour plus d'informations sur l'examen et les tests de sécurité, consultez ce [site Web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="4d4c3-127">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d4c3-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4d4c3-128">See Also</span></span>  
 [<span data-ttu-id="4d4c3-129">srv_rpcparams &#40;API de procédure stockée étendue&#41;</span><span class="sxs-lookup"><span data-stu-id="4d4c3-129">srv_rpcparams &#40;Extended Stored Procedure API&#41;</span></span>](srv-rpcparams-extended-stored-procedure-api.md)  
  
  
