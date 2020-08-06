---
title: srv_wsendmsg (API de procédure stockée étendue) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_wsendmsg
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_wsendmsg
ms.assetid: f2153076-32c9-4a52-8e1b-fc9618153543
author: rothja
ms.author: jroth
ms.openlocfilehash: 4cc915cce0befccb5c5af58e703c11b750af855b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709467"
---
# <a name="srv_wsendmsg-extended-stored-procedure-api"></a><span data-ttu-id="e8eeb-102">srv_wsendmsg (API de procédure stockée étendue)</span><span class="sxs-lookup"><span data-stu-id="e8eeb-102">srv_wsendmsg (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="e8eeb-103">Utilisez l’intégration CLR à la place.</span><span class="sxs-lookup"><span data-stu-id="e8eeb-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="e8eeb-104">Envoie un message Unicode au client.</span><span class="sxs-lookup"><span data-stu-id="e8eeb-104">Sends a Unicode message to the client.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8eeb-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="e8eeb-105">Syntax</span></span>  
  
```  
  
int srv_wsendmsg(SRV_PROC *   
srvproc  
, int   
msgnum  
, int   
severity  
, WCHAR *   
message  
, int   
msglen  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="e8eeb-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="e8eeb-106">Arguments</span></span>  
 <span data-ttu-id="e8eeb-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="e8eeb-107">*srvproc*</span></span>  
 <span data-ttu-id="e8eeb-108">Pointeur vers la structure SRV_PROC qui est le handle pour une connexion cliente particulière.</span><span class="sxs-lookup"><span data-stu-id="e8eeb-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection.</span></span> <span data-ttu-id="e8eeb-109">La structure contient des informations que la bibliothèque d'API de procédure stockée étendue utilise pour gérer les communications et les données entre l'application et le client.</span><span class="sxs-lookup"><span data-stu-id="e8eeb-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="e8eeb-110">*Msgnum*</span><span class="sxs-lookup"><span data-stu-id="e8eeb-110">*Msgnum*</span></span>  
 <span data-ttu-id="e8eeb-111">Numéro de message à 4 octets.</span><span class="sxs-lookup"><span data-stu-id="e8eeb-111">Is a 4-byte message number.</span></span>  
  
 <span data-ttu-id="e8eeb-112">*Niveau de gravité*</span><span class="sxs-lookup"><span data-stu-id="e8eeb-112">*Severity*</span></span>  
 <span data-ttu-id="e8eeb-113">Spécifie la gravité de l'erreur.</span><span class="sxs-lookup"><span data-stu-id="e8eeb-113">Specifies the severity of the error.</span></span> <span data-ttu-id="e8eeb-114">Une gravité inférieure ou égale à 10 est considérée comme un message d'information ; sinon, il s'agit d'une erreur.</span><span class="sxs-lookup"><span data-stu-id="e8eeb-114">A severity less than or equal to 10 is considered an informational message; otherwise, it is an error.</span></span>  
  
 <span data-ttu-id="e8eeb-115">*message*</span><span class="sxs-lookup"><span data-stu-id="e8eeb-115">*message*</span></span>  
 <span data-ttu-id="e8eeb-116">Pointeur vers une chaîne Unicode à envoyer au client.</span><span class="sxs-lookup"><span data-stu-id="e8eeb-116">Is a pointer to a Unicode string to be sent to the client.</span></span>  
  
 <span data-ttu-id="e8eeb-117">*msglen*</span><span class="sxs-lookup"><span data-stu-id="e8eeb-117">*msglen*</span></span>  
 <span data-ttu-id="e8eeb-118">Spécifie la longueur, en caractères, de *message*.</span><span class="sxs-lookup"><span data-stu-id="e8eeb-118">Specifies the length, in characters, of *message*.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="e8eeb-119">Retours</span><span class="sxs-lookup"><span data-stu-id="e8eeb-119">Returns</span></span>  
 <span data-ttu-id="e8eeb-120">SUCCEED ou FAIL.</span><span class="sxs-lookup"><span data-stu-id="e8eeb-120">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e8eeb-121">Notes</span><span class="sxs-lookup"><span data-stu-id="e8eeb-121">Remarks</span></span>  
 <span data-ttu-id="e8eeb-122">Utilisez cette fonction pour envoyer des messages en Unicode.</span><span class="sxs-lookup"><span data-stu-id="e8eeb-122">Use this function to send messages in Unicode.</span></span> <span data-ttu-id="e8eeb-123">Cette fonction est semblable à **srv_sendmsg**, mais le message qu'elle envoie est une chaîne WCHAR et non une chaîne de type DBCHAR.</span><span class="sxs-lookup"><span data-stu-id="e8eeb-123">It is similar to **srv_sendmsg**, but the message it sends is a WCHAR string rather than type DBCHAR string.</span></span> <span data-ttu-id="e8eeb-124">Notez que la longueur de message est exprimée en caractères et non en octets, et que *msglen* ne sera jamais égal à SRV_NULLTERM.</span><span class="sxs-lookup"><span data-stu-id="e8eeb-124">Note that message length is reported in characters rather than bytes, and *msglen* will never be equal to SRV_NULLTERM.</span></span>  
  
 <span data-ttu-id="e8eeb-125">Cette fonction retourne FAIL dans les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="e8eeb-125">The function returns FAIL when</span></span>  
  
-   <span data-ttu-id="e8eeb-126">L'argument *msglen* spécifié n'est pas compris dans la plage 0-32242.</span><span class="sxs-lookup"><span data-stu-id="e8eeb-126">The *msglen* given is not in the range of 0-32242.</span></span>  
  
-   <span data-ttu-id="e8eeb-127">L'argument *msglen* spécifié est 0 mais le pointeur de message est NULL.</span><span class="sxs-lookup"><span data-stu-id="e8eeb-127">The *msglen* given is 0 but the message pointer is NULL.</span></span>  
  
-   <span data-ttu-id="e8eeb-128">Une erreur se produit lors de l'envoi du message d'erreur par le biais du réseau.</span><span class="sxs-lookup"><span data-stu-id="e8eeb-128">There is error when sending the error message through network.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e8eeb-129">Il est préférable d'examiner avec soin le code source des procédures stockées étendues et de tester les DLL compilées avant de les installer sur un serveur de production.</span><span class="sxs-lookup"><span data-stu-id="e8eeb-129">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="e8eeb-130">Pour plus d'informations sur l'examen et les tests de sécurité, consultez ce [site Web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="e8eeb-130">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8eeb-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e8eeb-131">See Also</span></span>  
 [<span data-ttu-id="e8eeb-132">srv_sendmsg &#40;API de procédure stockée étendue&#41;</span><span class="sxs-lookup"><span data-stu-id="e8eeb-132">srv_sendmsg &#40;Extended Stored Procedure API&#41;</span></span>](srv-sendmsg-extended-stored-procedure-api.md)  
  
  
