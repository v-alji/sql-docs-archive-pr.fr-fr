---
title: srv_rpcnumber (API de procédure stockée étendue) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_rpcnumber
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_rpcnumber
ms.assetid: 3094085e-fe9e-423d-bf87-7852352c2d26
author: rothja
ms.author: jroth
ms.openlocfilehash: 25f30f8288125cf64d6b10a867d6af03c0f8ee91
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709475"
---
# <a name="srv_rpcnumber-extended-stored-procedure-api"></a><span data-ttu-id="737ab-102">srv_rpcnumber (API de procédure stockée étendue)</span><span class="sxs-lookup"><span data-stu-id="737ab-102">srv_rpcnumber (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="737ab-103">Utilisez l’intégration CLR à la place.</span><span class="sxs-lookup"><span data-stu-id="737ab-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="737ab-104">Retourne le composant de numéro pour l'appel de procédure stockée distante actuelle.</span><span class="sxs-lookup"><span data-stu-id="737ab-104">Returns the number component for the current remote stored procedure call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="737ab-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="737ab-105">Syntax</span></span>  
  
```  
  
int srv_rpcnumber ( SRV_PROC *  
srvproc   
)  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="737ab-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="737ab-106">Arguments</span></span>  
 <span data-ttu-id="737ab-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="737ab-107">*srvproc*</span></span>  
 <span data-ttu-id="737ab-108">Pointeur vers la structure SRV_PROC qui est le handle d'une connexion cliente particulière (dans ce cas, le handle qui a reçu la procédure stockée distante).</span><span class="sxs-lookup"><span data-stu-id="737ab-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure).</span></span> <span data-ttu-id="737ab-109">La structure contient des informations que la bibliothèque d'API de procédure stockée étendue utilise pour gérer les communications et les données entre l'application et le client.</span><span class="sxs-lookup"><span data-stu-id="737ab-109">The structure contains information that the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="737ab-110">Retours</span><span class="sxs-lookup"><span data-stu-id="737ab-110">Returns</span></span>  
 <span data-ttu-id="737ab-111">Composant de numéro pour la procédure stockée distante actuelle.</span><span class="sxs-lookup"><span data-stu-id="737ab-111">The number component for the current remote stored procedure.</span></span> <span data-ttu-id="737ab-112">Si le client n'utilise pas de composant de numéro lors de l'exécution de la procédure stockée distante ou qu'il n'y a aucune procédure stockée distante en cours, il retourne - 1.</span><span class="sxs-lookup"><span data-stu-id="737ab-112">If the client does not use a number component when running the remote stored procedure or if there is no current remote stored procedure, it returns - 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="737ab-113">Notes</span><span class="sxs-lookup"><span data-stu-id="737ab-113">Remarks</span></span>  
 <span data-ttu-id="737ab-114">Cette fonction retourne uniquement le composant de numéro de la procédure stockée distante.</span><span class="sxs-lookup"><span data-stu-id="737ab-114">This function returns only the number component of the remote stored procedure.</span></span> <span data-ttu-id="737ab-115">Elle n'inclut pas les spécificateurs facultatifs pour le propriétaire, le nom de la procédure stockée distante et le nom de la base de données.</span><span class="sxs-lookup"><span data-stu-id="737ab-115">It does not include the optional specifiers for owner, remote stored procedure name, and database name.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="737ab-116">Il est préférable d'examiner avec soin le code source des procédures stockées étendues et de tester les DLL compilées avant de les installer sur un serveur de production.</span><span class="sxs-lookup"><span data-stu-id="737ab-116">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="737ab-117">Pour plus d'informations sur l'examen et les tests de sécurité, consultez ce [site Web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="737ab-117">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
