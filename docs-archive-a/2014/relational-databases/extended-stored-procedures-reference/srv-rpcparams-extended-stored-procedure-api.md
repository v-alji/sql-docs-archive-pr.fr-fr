---
title: srv_rpcparams (API de procédure stockée étendue) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_rpcparams
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_rpcparams
ms.assetid: 96a5e6f6-d320-4623-b96e-0a856e3abebb
author: rothja
ms.author: jroth
ms.openlocfilehash: 443b9ea8a67341afdb92f0c384148c8b1b42f752
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710600"
---
# <a name="srv_rpcparams-extended-stored-procedure-api"></a><span data-ttu-id="b95d6-102">srv_rpcparams (API de procédure stockée étendue)</span><span class="sxs-lookup"><span data-stu-id="b95d6-102">srv_rpcparams (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="b95d6-103">Utilisez l’intégration CLR à la place.</span><span class="sxs-lookup"><span data-stu-id="b95d6-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="b95d6-104">Retourne le nombre de paramètres pour la procédure stockée distante actuelle.</span><span class="sxs-lookup"><span data-stu-id="b95d6-104">Returns the number of parameters for the current remote stored procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b95d6-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="b95d6-105">Syntax</span></span>  
  
```  
  
int srv_rpcparams ( SRV_PROC *  
srvproc   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="b95d6-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="b95d6-106">Arguments</span></span>  
 <span data-ttu-id="b95d6-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="b95d6-107">*srvproc*</span></span>  
 <span data-ttu-id="b95d6-108">Pointeur vers la structure SRV_PROC qui est le handle d'une connexion cliente particulière (dans ce cas, le handle qui a reçu la procédure stockée distante).</span><span class="sxs-lookup"><span data-stu-id="b95d6-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure).</span></span> <span data-ttu-id="b95d6-109">La structure contient des informations que la bibliothèque d'API de procédure stockée étendue utilise pour gérer les communications et les données entre l'application et le client.</span><span class="sxs-lookup"><span data-stu-id="b95d6-109">The structure contains information that the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="b95d6-110">Retours</span><span class="sxs-lookup"><span data-stu-id="b95d6-110">Returns</span></span>  
 <span data-ttu-id="b95d6-111">Nombre de paramètres dans la procédure stockée distante.</span><span class="sxs-lookup"><span data-stu-id="b95d6-111">The number of parameters in the remote stored procedure.</span></span> <span data-ttu-id="b95d6-112">S'il n'y a pas de paramètres dans la procédure stockée distante ou s'il n'y a pas de procédure stockée distante actuellement, -1 est retourné et une erreur liée aux informations se produit.</span><span class="sxs-lookup"><span data-stu-id="b95d6-112">If there are no parameters in the remote stored procedure or if there is not a current remote stored procedure, -1 is returned and an information error occurs.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b95d6-113">Notes</span><span class="sxs-lookup"><span data-stu-id="b95d6-113">Remarks</span></span>  
 <span data-ttu-id="b95d6-114">Cette fonction retourne le nombre de paramètres dans la procédure stockée distante actuelle.</span><span class="sxs-lookup"><span data-stu-id="b95d6-114">This function returns the number of parameters in the current remote stored procedure.</span></span> <span data-ttu-id="b95d6-115">Elle est généralement appelée à partir de la procédure stockée distante.</span><span class="sxs-lookup"><span data-stu-id="b95d6-115">It is usually called from the remote stored procedure.</span></span>  
  
 <span data-ttu-id="b95d6-116">Quand un appel de procédure stockée distante est effectué avec des paramètres, ceux-ci peuvent être passés par nom ou par position (sans nom).</span><span class="sxs-lookup"><span data-stu-id="b95d6-116">When a remote stored procedure call is made with parameters, the parameters can be passed either by name or by position (unnamed).</span></span> <span data-ttu-id="b95d6-117">Si l'appel de procédure stockée distante a été effectué avec certains paramètres passés par nom et certains passés par position, une erreur se produit.</span><span class="sxs-lookup"><span data-stu-id="b95d6-117">If the remote stored procedure call was made with some parameters passed by name and some passed by position, an error occurs.</span></span> <span data-ttu-id="b95d6-118">Quand cette erreur se produit, le gestionnaire de procédures stockées distantes est appelé, mais il ne reçoit pas les paramètres et **srv_rpcparams** retourne 0.</span><span class="sxs-lookup"><span data-stu-id="b95d6-118">When this error occurs, the remote stored procedure handler is called, but it does not receive the parameters and **srv_rpcparams** returns 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b95d6-119">Il est préférable d'examiner avec soin le code source des procédures stockées étendues et de tester les DLL compilées avant de les installer sur un serveur de production.</span><span class="sxs-lookup"><span data-stu-id="b95d6-119">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="b95d6-120">Pour plus d'informations sur l'examen et les tests de sécurité, consultez ce [site Web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="b95d6-120">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
