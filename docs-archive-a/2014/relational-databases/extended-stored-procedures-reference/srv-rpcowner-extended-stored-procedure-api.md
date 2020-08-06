---
title: srv_rpcowner (API de procédure stockée étendue) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_rpcowner
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_rpcowner
ms.assetid: e81a60e6-14ea-47bc-a11c-3d7635344447
author: rothja
ms.author: jroth
ms.openlocfilehash: f903870d0ee01256addb1557eb7e9123853b39e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710607"
---
# <a name="srv_rpcowner-extended-stored-procedure-api"></a><span data-ttu-id="74cd9-102">srv_rpcowner (API de procédure stockée étendue)</span><span class="sxs-lookup"><span data-stu-id="74cd9-102">srv_rpcowner (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="74cd9-103">Utilisez l’intégration CLR à la place.</span><span class="sxs-lookup"><span data-stu-id="74cd9-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="74cd9-104">Retourne le composant propriétaire de la procédure stockée distante actuelle.</span><span class="sxs-lookup"><span data-stu-id="74cd9-104">Returns the owner component for the current remote stored procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74cd9-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="74cd9-105">Syntax</span></span>  
  
```  
  
DBCHAR * srv_rpcowner (  
SRV_PROC *  
srvproc  
,  
int *  
len   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="74cd9-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="74cd9-106">Arguments</span></span>  
 <span data-ttu-id="74cd9-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="74cd9-107">*srvproc*</span></span>  
 <span data-ttu-id="74cd9-108">Pointeur vers la structure SRV_PROC qui est le handle d'une connexion cliente particulière (dans ce cas, le handle qui a reçu la procédure stockée distante).</span><span class="sxs-lookup"><span data-stu-id="74cd9-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure).</span></span> <span data-ttu-id="74cd9-109">La structure contient des informations que la bibliothèque d'API de procédure stockée étendue utilise pour gérer les communications et les données entre l'application et le client.</span><span class="sxs-lookup"><span data-stu-id="74cd9-109">The structure contains information that the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="74cd9-110">*Len*</span><span class="sxs-lookup"><span data-stu-id="74cd9-110">*len*</span></span>  
 <span data-ttu-id="74cd9-111">Pointeur vers une variable de type entier qui reçoit la longueur du nom du propriétaire.</span><span class="sxs-lookup"><span data-stu-id="74cd9-111">Is a pointer to an integer variable that receives the length of the owner name.</span></span> <span data-ttu-id="74cd9-112">Le paramètre *len* peut être NULL ; dans ce cas, la longueur du composant propriétaire n’est pas retournée.</span><span class="sxs-lookup"><span data-stu-id="74cd9-112">The parameter *len* can be NULL, in which case the length of the owner component is not returned.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="74cd9-113">Retours</span><span class="sxs-lookup"><span data-stu-id="74cd9-113">Returns</span></span>  
 <span data-ttu-id="74cd9-114">Un pointeur DBCHAR vers le composant propriétaire, terminé par le caractère NULL, de la procédure stockée distante actuelle.</span><span class="sxs-lookup"><span data-stu-id="74cd9-114">A DBCHAR pointer to the null-terminated owner component for the current remote stored procedure.</span></span> <span data-ttu-id="74cd9-115">En l’absence de procédure stockée distante actuelle, NULL est retourné et *len* est défini sur -1.</span><span class="sxs-lookup"><span data-stu-id="74cd9-115">If there is no current remote stored procedure, NULL is returned and *len* is set to - 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="74cd9-116">Notes</span><span class="sxs-lookup"><span data-stu-id="74cd9-116">Remarks</span></span>  
 <span data-ttu-id="74cd9-117">Cette fonction retourne uniquement le composant propriétaire de la procédure stockée distante.</span><span class="sxs-lookup"><span data-stu-id="74cd9-117">This function returns only the owner component of the remote stored procedure.</span></span> <span data-ttu-id="74cd9-118">Elle n'inclut pas les spécificateurs facultatifs pour le nom, le nom de la procédure stockée distante et le numéro de la procédure stockée distante.</span><span class="sxs-lookup"><span data-stu-id="74cd9-118">It does not include the optional specifiers for name, remote stored procedure name, and remote stored procedure number.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="74cd9-119">Il est préférable d'examiner avec soin le code source des procédures stockées étendues et de tester les DLL compilées avant de les installer sur un serveur de production.</span><span class="sxs-lookup"><span data-stu-id="74cd9-119">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="74cd9-120">Pour plus d'informations sur l'examen et les tests de sécurité, consultez ce [site Web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="74cd9-120">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
