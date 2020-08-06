---
title: srv_paramnumber (API de procédure stockée étendue) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_paramnumber
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_paramnumber
ms.assetid: d7a6dbff-71d9-4297-8a4f-bfd2876fe204
author: rothja
ms.author: jroth
ms.openlocfilehash: 1e621101c909ef251c40f38713e438d8e40d08a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612343"
---
# <a name="srv_paramnumber-extended-stored-procedure-api"></a><span data-ttu-id="97b15-102">srv_paramnumber (API de procédure stockée étendue)</span><span class="sxs-lookup"><span data-stu-id="97b15-102">srv_paramnumber (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="97b15-103">Utilisez l’intégration CLR à la place.</span><span class="sxs-lookup"><span data-stu-id="97b15-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="97b15-104">Retourne le numéro d'un paramètre d'appel de procédure stockée distante.</span><span class="sxs-lookup"><span data-stu-id="97b15-104">Returns the number of a remote stored procedure call parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97b15-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="97b15-105">Syntax</span></span>  
  
```  
  
int srv_paramnumber (  
SRV_PROC *  
srvproc  
,  
DBCHAR *  
name  
,   
int  
namelen   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="97b15-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="97b15-106">Arguments</span></span>  
 <span data-ttu-id="97b15-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="97b15-107">*srvproc*</span></span>  
 <span data-ttu-id="97b15-108">Pointeur vers la structure SRV_PROC qui correspond au handle d'une connexion cliente particulière (dans ce cas, le handle qui a reçu l'appel de procédure stockée distante).</span><span class="sxs-lookup"><span data-stu-id="97b15-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure call).</span></span> <span data-ttu-id="97b15-109">La structure contient des informations que la bibliothèque d'API de procédure stockée étendue utilise pour gérer les communications et les données entre l'application et le client.</span><span class="sxs-lookup"><span data-stu-id="97b15-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="97b15-110">*name*</span><span class="sxs-lookup"><span data-stu-id="97b15-110">*name*</span></span>  
 <span data-ttu-id="97b15-111">Pointeur vers le paramètre *name*.</span><span class="sxs-lookup"><span data-stu-id="97b15-111">Is a pointer to the parameter *name*.</span></span>  
  
 <span data-ttu-id="97b15-112">*namelen*</span><span class="sxs-lookup"><span data-stu-id="97b15-112">*namelen*</span></span>  
 <span data-ttu-id="97b15-113">Longueur de *name*.</span><span class="sxs-lookup"><span data-stu-id="97b15-113">Is the length of *name*.</span></span> <span data-ttu-id="97b15-114">Si *name* se termine par le caractère NULL, définissez *namelen* sur SRV_NULLTERM.</span><span class="sxs-lookup"><span data-stu-id="97b15-114">If *name* is null-terminated, set *namelen* to SRV_NULLTERM.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="97b15-115">Retours</span><span class="sxs-lookup"><span data-stu-id="97b15-115">Returns</span></span>  
 <span data-ttu-id="97b15-116">Numéro de paramètre du paramètre nommé.</span><span class="sxs-lookup"><span data-stu-id="97b15-116">The parameter number of the named parameter.</span></span> <span data-ttu-id="97b15-117">Le premier paramètre est 1.</span><span class="sxs-lookup"><span data-stu-id="97b15-117">The first parameter is 1.</span></span> <span data-ttu-id="97b15-118">S’il n’existe aucun paramètre nommé *name* ou aucune procédure stockée distante, 0 est retourné et un message est généré.</span><span class="sxs-lookup"><span data-stu-id="97b15-118">If there is no parameter named *name* or no remote stored procedure, 0 is returned and a message is generated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97b15-119">Notes</span><span class="sxs-lookup"><span data-stu-id="97b15-119">Remarks</span></span>  
 <span data-ttu-id="97b15-120">Quand un appel de procédure stockée distante est effectué avec des paramètres, ceux-ci peuvent être passés par nom ou par position (sans nom).</span><span class="sxs-lookup"><span data-stu-id="97b15-120">When a remote stored procedure call is made with parameters, the parameters can be passed either by name or by position (unnamed).</span></span> <span data-ttu-id="97b15-121">Si l'appel de procédure stockée distante est effectué avec certains paramètres passés par nom et certains passés par position, une erreur se produit.</span><span class="sxs-lookup"><span data-stu-id="97b15-121">If the remote stored procedure call is made with some parameters passed by name and some passed by position, an error occurs.</span></span> <span data-ttu-id="97b15-122">Le gestionnaire SRV_RPC est tout de même appelé, mais il apparaît comme s’il n’y avait aucun paramètre et **srv_rpcparams** retourne 0.</span><span class="sxs-lookup"><span data-stu-id="97b15-122">The SRV_RPC handler is still called, but it appears as if there were no parameters, and **srv_rpcparams** returns 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="97b15-123">Il est préférable d'examiner avec soin le code source des procédures stockées étendues et de tester les DLL compilées avant de les installer sur un serveur de production.</span><span class="sxs-lookup"><span data-stu-id="97b15-123">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="97b15-124">Pour plus d'informations sur l'examen et les tests de sécurité, consultez ce [site Web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="97b15-124">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97b15-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="97b15-125">See Also</span></span>  
 [<span data-ttu-id="97b15-126">srv_rpcparams &#40;API de procédure stockée étendue&#41;</span><span class="sxs-lookup"><span data-stu-id="97b15-126">srv_rpcparams &#40;Extended Stored Procedure API&#41;</span></span>](srv-rpcparams-extended-stored-procedure-api.md)  
  
  
