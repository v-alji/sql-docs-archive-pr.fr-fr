---
title: srv_sendmsg (API de procédure stockée étendue) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_sendmsg
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_sendmsg
ms.assetid: efcb50b9-f8ff-4121-bf67-05830171b928
author: rothja
ms.author: jroth
ms.openlocfilehash: 0821ad88f48313cfadea634a489def9b242a49f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710595"
---
# <a name="srv_sendmsg-extended-stored-procedure-api"></a><span data-ttu-id="64733-102">srv_sendmsg (API de procédure stockée étendue)</span><span class="sxs-lookup"><span data-stu-id="64733-102">srv_sendmsg (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="64733-103">Utilisez l’intégration CLR à la place.</span><span class="sxs-lookup"><span data-stu-id="64733-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="64733-104">Envoie un message au client.</span><span class="sxs-lookup"><span data-stu-id="64733-104">Sends a message to the client.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64733-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="64733-105">Syntax</span></span>  
  
```  
  
int srv_sendmsg (  
SRV_PROC *  
srvproc  
,  
int  
msgtype  
,  
DBINT  
msgnum  
,  
DBTINYINT  
class  
,   
DBTINYINT  
state  
,  
DBCHAR *  
rpcname  
,  
int   
rpcnamelen  
,  
DBUSMALLINT  
linenum  
,  
DBCHAR *  
message  
,  
int  
msglen   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="64733-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="64733-106">Arguments</span></span>  
 <span data-ttu-id="64733-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="64733-107">*srvproc*</span></span>  
 <span data-ttu-id="64733-108">Pointeur vers la structure SRV_PROC qui est le handle d'une connexion cliente particulière (dans ce cas, le handle qui a reçu la demande de langue).</span><span class="sxs-lookup"><span data-stu-id="64733-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the language request).</span></span> <span data-ttu-id="64733-109">La structure contient des informations que la bibliothèque d'API de procédure stockée étendue utilise pour gérer les communications et les données entre l'application et le client.</span><span class="sxs-lookup"><span data-stu-id="64733-109">The structure contains information that the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="64733-110">*msgtype*</span><span class="sxs-lookup"><span data-stu-id="64733-110">*msgtype*</span></span>  
 <span data-ttu-id="64733-111">SRV_MSG_INFO ou SRV_MSG_ERROR, selon que le serveur envoie un message d'information ou un message d'erreur.</span><span class="sxs-lookup"><span data-stu-id="64733-111">Is either SRV_MSG_INFO or SRV_MSG_ERROR, depending on whether the server is sending an informational or error message.</span></span>  
  
 <span data-ttu-id="64733-112">*msgnum*</span><span class="sxs-lookup"><span data-stu-id="64733-112">*msgnum*</span></span>  
 <span data-ttu-id="64733-113">Numéro de message à 4 octets.</span><span class="sxs-lookup"><span data-stu-id="64733-113">Is a 4-byte message number.</span></span>  
  
 <span data-ttu-id="64733-114">*class*</span><span class="sxs-lookup"><span data-stu-id="64733-114">*class*</span></span>  
 <span data-ttu-id="64733-115">Spécifie la gravité de l'erreur.</span><span class="sxs-lookup"><span data-stu-id="64733-115">Specifies the error severity.</span></span> <span data-ttu-id="64733-116">Une gravité inférieure ou égale à 10 est considérée comme un message d'information.</span><span class="sxs-lookup"><span data-stu-id="64733-116">A severity less than or equal to 10 is considered an informational message.</span></span>  
  
 <span data-ttu-id="64733-117">*state*</span><span class="sxs-lookup"><span data-stu-id="64733-117">*state*</span></span>  
 <span data-ttu-id="64733-118">Fournit le numéro d'état de l'erreur pour le message actuel.</span><span class="sxs-lookup"><span data-stu-id="64733-118">Provides the error state number for the current message.</span></span> <span data-ttu-id="64733-119">Le numéro d'état de l'erreur fournit des informations sur le contexte de l'erreur.</span><span class="sxs-lookup"><span data-stu-id="64733-119">The error state number provides information about the context of the error.</span></span> <span data-ttu-id="64733-120">Les numéros d'état valides sont compris entre 0 et 255.</span><span class="sxs-lookup"><span data-stu-id="64733-120">Valid state numbers are from 0 through 255.</span></span>  
  
 <span data-ttu-id="64733-121">*rpcname*</span><span class="sxs-lookup"><span data-stu-id="64733-121">*rpcname*</span></span>  
 <span data-ttu-id="64733-122">N’est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="64733-122">Is currently not supported.</span></span>  
  
 <span data-ttu-id="64733-123">*rpcnamelen*</span><span class="sxs-lookup"><span data-stu-id="64733-123">*rpcnamelen*</span></span>  
 <span data-ttu-id="64733-124">N’est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="64733-124">Is currently not supported.</span></span>  
  
 <span data-ttu-id="64733-125">*linenum*</span><span class="sxs-lookup"><span data-stu-id="64733-125">*linenum*</span></span>  
 <span data-ttu-id="64733-126">Numéro de ligne dans le lot de commandes du langage auquel le message s'applique.</span><span class="sxs-lookup"><span data-stu-id="64733-126">Is the line number in the language command batch where the message applies.</span></span> <span data-ttu-id="64733-127">La numérotation des lignes débute à 1.</span><span class="sxs-lookup"><span data-stu-id="64733-127">Line numbers start at 1.</span></span> <span data-ttu-id="64733-128">Si *linenum* ne s’applique pas au message, définissez cette valeur sur 0.</span><span class="sxs-lookup"><span data-stu-id="64733-128">If *linenum* does not apply to the message, set to 0.</span></span>  
  
 <span data-ttu-id="64733-129">*message*</span><span class="sxs-lookup"><span data-stu-id="64733-129">*message*</span></span>  
 <span data-ttu-id="64733-130">Pointeur vers la chaîne de caractères à envoyer au client.</span><span class="sxs-lookup"><span data-stu-id="64733-130">Is a pointer to the character string to be sent to the client.</span></span>  
  
 <span data-ttu-id="64733-131">*msglen*</span><span class="sxs-lookup"><span data-stu-id="64733-131">*msglen*</span></span>  
 <span data-ttu-id="64733-132">Spécifie la longueur, en octets, de *message*.</span><span class="sxs-lookup"><span data-stu-id="64733-132">Specifies the length, in bytes, of *message*.</span></span> <span data-ttu-id="64733-133">Si *message* se termine par le caractère NULL, définissez *msglen* sur SRV_NULLTERM.</span><span class="sxs-lookup"><span data-stu-id="64733-133">If *message* is null-terminated, set *msglen* to SRV_NULLTERM.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="64733-134">Retours</span><span class="sxs-lookup"><span data-stu-id="64733-134">Returns</span></span>  
 <span data-ttu-id="64733-135">SUCCEED ou FAIL</span><span class="sxs-lookup"><span data-stu-id="64733-135">SUCCEED or FAIL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="64733-136">Notes</span><span class="sxs-lookup"><span data-stu-id="64733-136">Remarks</span></span>  
 <span data-ttu-id="64733-137">Cette fonction envoie des messages d'erreur ou d'information au client.</span><span class="sxs-lookup"><span data-stu-id="64733-137">This function sends error or informational messages to the client.</span></span> <span data-ttu-id="64733-138">Elle est appelée une fois pour chaque message à envoyer.</span><span class="sxs-lookup"><span data-stu-id="64733-138">It is called once for each message to be sent.</span></span>  
  
 <span data-ttu-id="64733-139">Les messages peuvent être envoyés au client avec **srv_sendmsg** dans n’importe quel ordre avant ou après que toutes les lignes (le cas échéant) ont été envoyées avec **srv_sendrow**.</span><span class="sxs-lookup"><span data-stu-id="64733-139">Messages can be sent to the client with **srv_sendmsg** in any order before or after all rows (if any) have been sent with **srv_sendrow**.</span></span> <span data-ttu-id="64733-140">Tous les messages, s’il en existe, doivent être envoyés au client avant que l’état d’achèvement soit envoyé avec **srv_senddone**.</span><span class="sxs-lookup"><span data-stu-id="64733-140">All messages, if any, must be sent to the client before the completion status is sent with **srv_senddone**.</span></span>  
  
 <span data-ttu-id="64733-141">Pour envoyer des messages en Unicode, utilisez **srv_wsendmsg** à la place de **srv_sendmsg**.</span><span class="sxs-lookup"><span data-stu-id="64733-141">To send messages in Unicode, use **srv_wsendmsg** rather than **srv_sendmsg**.</span></span>  
  
 <span data-ttu-id="64733-142">Pour plus d’informations, consultez [Données Unicode et pages de codes du serveur](../extended-stored-procedures-programming/unicode-data-and-server-code-pages.md).</span><span class="sxs-lookup"><span data-stu-id="64733-142">For more information see [Unicode Data and Server Code Pages](../extended-stored-procedures-programming/unicode-data-and-server-code-pages.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="64733-143">Il est préférable d'examiner avec soin le code source des procédures stockées étendues et de tester les DLL compilées avant de les installer sur un serveur de production.</span><span class="sxs-lookup"><span data-stu-id="64733-143">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="64733-144">Pour plus d'informations sur l'examen et les tests de sécurité, consultez ce [site Web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="64733-144">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
