---
title: srv_rpcoptions (API de procédure stockée étendue) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_rpcoptions
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_rpcoptions
ms.assetid: dbcce5d1-d5a1-4379-9597-04e43af5923d
author: rothja
ms.author: jroth
ms.openlocfilehash: f5ebe4ab48721002e679ce149293b474a934e348
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710608"
---
# <a name="srv_rpcoptions-extended-stored-procedure-api"></a><span data-ttu-id="cf82c-102">srv_rpcoptions (API de procédure stockée étendue)</span><span class="sxs-lookup"><span data-stu-id="cf82c-102">srv_rpcoptions (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="cf82c-103">Utilisez l’intégration CLR à la place.</span><span class="sxs-lookup"><span data-stu-id="cf82c-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="cf82c-104">Retourne les options d'exécution pour la procédure stockée distante actuelle.</span><span class="sxs-lookup"><span data-stu-id="cf82c-104">Returns run-time options for the current remote stored procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf82c-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="cf82c-105">Syntax</span></span>  
  
```  
  
DBUSMALLINT srv_rpcoptions ( SRV_PROC *  
srvproc   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="cf82c-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="cf82c-106">Arguments</span></span>  
 <span data-ttu-id="cf82c-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="cf82c-107">*srvproc*</span></span>  
 <span data-ttu-id="cf82c-108">Pointeur vers la structure SRV_PROC qui est le handle d'une connexion cliente particulière (dans ce cas, le handle qui a reçu la procédure stockée distante).</span><span class="sxs-lookup"><span data-stu-id="cf82c-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure).</span></span> <span data-ttu-id="cf82c-109">La structure contient des informations que la bibliothèque d'API de procédure stockée étendue utilise pour gérer les communications et les données entre l'application et le client.</span><span class="sxs-lookup"><span data-stu-id="cf82c-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="cf82c-110">Retours</span><span class="sxs-lookup"><span data-stu-id="cf82c-110">Returns</span></span>  
 <span data-ttu-id="cf82c-111">Bitmap qui contient les indicateurs d'exécution joints dans un OR logique pour la procédure stockée distante actuelle.</span><span class="sxs-lookup"><span data-stu-id="cf82c-111">A bitmap that contains the run-time flags joined in a logical OR for the current remote stored procedure.</span></span> <span data-ttu-id="cf82c-112">En l'absence de procédure stockée distante actuelle, 0 est retourné et un message est généré.</span><span class="sxs-lookup"><span data-stu-id="cf82c-112">If there is not a current remote stored procedure, 0 is returned and a message is generated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf82c-113">Notes</span><span class="sxs-lookup"><span data-stu-id="cf82c-113">Remarks</span></span>  
 <span data-ttu-id="cf82c-114">Le tableau ci-dessous décrit chaque indicateur d'exécution.</span><span class="sxs-lookup"><span data-stu-id="cf82c-114">The following table describes each run-time flag.</span></span>  
  
|<span data-ttu-id="cf82c-115">Indicateur d'exécution</span><span class="sxs-lookup"><span data-stu-id="cf82c-115">Run-time flag</span></span>|<span data-ttu-id="cf82c-116">Description</span><span class="sxs-lookup"><span data-stu-id="cf82c-116">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="cf82c-117">SRV_NOMETADATA</span><span class="sxs-lookup"><span data-stu-id="cf82c-117">SRV_NOMETADATA</span></span>|<span data-ttu-id="cf82c-118">Le client a demandé des résultats sans informations de métadonnées.</span><span class="sxs-lookup"><span data-stu-id="cf82c-118">The client has requested results without metadata information.</span></span> <span data-ttu-id="cf82c-119">Cet indicateur est utilisé uniquement lorsque le client communique avec une instance de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cf82c-119">This flag is only used when the client is communicating with an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="cf82c-120">Une application de l'API de procédure stockée étendue ne peut pas omettre les informations de métadonnées.</span><span class="sxs-lookup"><span data-stu-id="cf82c-120">An Extended Stored Procedure API application cannot omit metadata information.</span></span>|  
|<span data-ttu-id="cf82c-121">SRV_RECOMPILE</span><span class="sxs-lookup"><span data-stu-id="cf82c-121">SRV_RECOMPILE</span></span>|<span data-ttu-id="cf82c-122">Le client a demandé de recompiler la procédure stockée distante avant de l'exécuter.</span><span class="sxs-lookup"><span data-stu-id="cf82c-122">The client has requested to recompile the remote stored procedure before executing it.</span></span> <span data-ttu-id="cf82c-123">Cet indicateur peut ne pas s'appliquer à une application de l'API de procédure stockée étendue.</span><span class="sxs-lookup"><span data-stu-id="cf82c-123">This flag may not apply to an Extended Stored Procedure API application.</span></span>|  
  
> [!IMPORTANT]  
>  <span data-ttu-id="cf82c-124">Il est préférable d'examiner avec soin le code source des procédures stockées étendues et de tester les DLL compilées avant de les installer sur un serveur de production.</span><span class="sxs-lookup"><span data-stu-id="cf82c-124">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="cf82c-125">Pour plus d'informations sur l'examen et les tests de sécurité, consultez ce [site Web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="cf82c-125">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
