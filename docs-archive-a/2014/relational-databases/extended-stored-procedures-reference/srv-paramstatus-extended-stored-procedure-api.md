---
title: srv_paramstatus (API de procédure stockée étendue) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_paramstatus
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_paramstatus
ms.assetid: 86cecd45-0b09-42e9-8152-32a12a1c2b7a
author: rothja
ms.author: jroth
ms.openlocfilehash: d89d4ccbb6a97ff47669ad4ed9c0b4c22ac934eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695600"
---
# <a name="srv_paramstatus-extended-stored-procedure-api"></a><span data-ttu-id="c8c5e-102">srv_paramstatus (API de procédure stockée étendue)</span><span class="sxs-lookup"><span data-stu-id="c8c5e-102">srv_paramstatus (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="c8c5e-103">Utilisez l’intégration CLR à la place.</span><span class="sxs-lookup"><span data-stu-id="c8c5e-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="c8c5e-104">Retourne l'état d'un paramètre d'appel d'une procédure stockée distante particulière.</span><span class="sxs-lookup"><span data-stu-id="c8c5e-104">Returns the status of a particular remote stored procedure call parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8c5e-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="c8c5e-105">Syntax</span></span>  
  
```  
  
int srv_paramstatus (  
SRV_PROC *  
srvproc  
,  
int  
n   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="c8c5e-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="c8c5e-106">Arguments</span></span>  
 <span data-ttu-id="c8c5e-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="c8c5e-107">*srvproc*</span></span>  
 <span data-ttu-id="c8c5e-108">Pointeur vers la structure SRV_PROC qui correspond au handle d'une connexion cliente particulière (dans ce cas, le handle qui a reçu l'appel de procédure stockée distante).</span><span class="sxs-lookup"><span data-stu-id="c8c5e-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure call).</span></span> <span data-ttu-id="c8c5e-109">La structure contient des informations que la bibliothèque d'API de procédure stockée étendue utilise pour gérer les communications et les données entre l'application et le client.</span><span class="sxs-lookup"><span data-stu-id="c8c5e-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="c8c5e-110">*n*</span><span class="sxs-lookup"><span data-stu-id="c8c5e-110">*n*</span></span>  
 <span data-ttu-id="c8c5e-111">Indique le numéro du paramètre.</span><span class="sxs-lookup"><span data-stu-id="c8c5e-111">Indicates the number of the parameter.</span></span> <span data-ttu-id="c8c5e-112">Le premier paramètre est le numéro 1.</span><span class="sxs-lookup"><span data-stu-id="c8c5e-112">The first parameter is number 1.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="c8c5e-113">Retours</span><span class="sxs-lookup"><span data-stu-id="c8c5e-113">Returns</span></span>  
 <span data-ttu-id="c8c5e-114">Un `int` qui contient les indicateurs d'état du paramètre.</span><span class="sxs-lookup"><span data-stu-id="c8c5e-114">An `int` that contains status flags for the parameter.</span></span> <span data-ttu-id="c8c5e-115">Actuellement, il existe un seul indicateur: Si le bit 0 est défini sur 1, le paramètre est un paramètre de retour.</span><span class="sxs-lookup"><span data-stu-id="c8c5e-115">Currently, there is only one flag: If bit 0 is set to 1, the parameter is a return parameter.</span></span> <span data-ttu-id="c8c5e-116">En l’absence du *n*ième paramètre ou d’une procédure stockée distante, la valeur -1 est retournée.</span><span class="sxs-lookup"><span data-stu-id="c8c5e-116">If there is no *n*th parameter or if there is no remote stored procedure, it returns -1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c8c5e-117">Notes</span><span class="sxs-lookup"><span data-stu-id="c8c5e-117">Remarks</span></span>  
 <span data-ttu-id="c8c5e-118">Cette routine retourne les indicateurs d'état pour un paramètre d'appel d'une procédure stockée distante.</span><span class="sxs-lookup"><span data-stu-id="c8c5e-118">This routine returns the status flags for a remote stored procedure call parameter.</span></span>  
  
 <span data-ttu-id="c8c5e-119">Les paramètres contiennent les données passées entre les clients et l'application avec des procédures stockées distantes.</span><span class="sxs-lookup"><span data-stu-id="c8c5e-119">Parameters contain data passed between clients and the application with remote stored procedures.</span></span> <span data-ttu-id="c8c5e-120">Le client peut spécifier certains paramètres en tant que paramètres de retour.</span><span class="sxs-lookup"><span data-stu-id="c8c5e-120">The client can specify certain parameters as return parameters.</span></span> <span data-ttu-id="c8c5e-121">Ces paramètres de retour peuvent contenir des valeurs que l'application transmet au client.</span><span class="sxs-lookup"><span data-stu-id="c8c5e-121">These return parameters can contain values that the application passes back to the client.</span></span>  
  
 <span data-ttu-id="c8c5e-122">Actuellement, le seul indicateur d'état est celui qui indique si le paramètre est un paramètre de retour.</span><span class="sxs-lookup"><span data-stu-id="c8c5e-122">Currently, the only status flag is one that indicates whether the parameter is a return parameter.</span></span>  
  
 <span data-ttu-id="c8c5e-123">Quand un appel de procédure stockée distante est effectué avec des paramètres, ceux-ci peuvent être passés par nom ou par position (sans nom).</span><span class="sxs-lookup"><span data-stu-id="c8c5e-123">When a remote stored procedure call is made with parameters, the parameters can be passed either by name or by position (unnamed).</span></span> <span data-ttu-id="c8c5e-124">Si l'appel de procédure stockée distante est effectué avec certains paramètres passés par nom et certains passés par position, une erreur se produit.</span><span class="sxs-lookup"><span data-stu-id="c8c5e-124">If the remote stored procedure call is made with some parameters passed by name and some passed by position, an error occurs.</span></span> <span data-ttu-id="c8c5e-125">Si une erreur se produit, le gestionnaire de SRV_RPC est toujours appelé, mais il apparaît comme s’il n’y avait aucun paramètre, et **srv_rpcparams** retourne 0.</span><span class="sxs-lookup"><span data-stu-id="c8c5e-125">If an error occurs, the SRV_RPC handler is still called, but it appears as if there were no parameters, and **srv_rpcparams** returns 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c8c5e-126">Il est préférable d'examiner avec soin le code source des procédures stockées étendues et de tester les DLL compilées avant de les installer sur un serveur de production.</span><span class="sxs-lookup"><span data-stu-id="c8c5e-126">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="c8c5e-127">Pour plus d'informations sur l'examen et les tests de sécurité, consultez ce [site Web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="c8c5e-127">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8c5e-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c8c5e-128">See Also</span></span>  
 [<span data-ttu-id="c8c5e-129">srv_rpcparams &#40;API de procédure stockée étendue&#41;</span><span class="sxs-lookup"><span data-stu-id="c8c5e-129">srv_rpcparams &#40;Extended Stored Procedure API&#41;</span></span>](srv-rpcparams-extended-stored-procedure-api.md)  
  
  
