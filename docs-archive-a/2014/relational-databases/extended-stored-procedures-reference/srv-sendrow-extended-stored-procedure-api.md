---
title: srv_sendrow (API de procédure stockée étendue) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_sendrow
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_sendrow
ms.assetid: a08f608a-10e6-4bff-9b48-0d02e8026cdb
author: rothja
ms.author: jroth
ms.openlocfilehash: df40348b8792a70f84719abfb42152fda9487e6b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710592"
---
# <a name="srv_sendrow-extended-stored-procedure-api"></a><span data-ttu-id="43fec-102">srv_sendrow (API de procédure stockée étendue)</span><span class="sxs-lookup"><span data-stu-id="43fec-102">srv_sendrow (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="43fec-103">Utilisez l’intégration CLR à la place.</span><span class="sxs-lookup"><span data-stu-id="43fec-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="43fec-104">Transmet une ligne de données au client.</span><span class="sxs-lookup"><span data-stu-id="43fec-104">Transmits a row of data to the client.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43fec-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="43fec-105">Syntax</span></span>  
  
```  
  
int srv_sendrow ( SRV_PROC *  
srvproc   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="43fec-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="43fec-106">Arguments</span></span>  
 <span data-ttu-id="43fec-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="43fec-107">*srvproc*</span></span>  
 <span data-ttu-id="43fec-108">Pointeur vers la structure SRV_PROC qui est le handle d'une connexion cliente particulière (dans ce cas, le handle qui a reçu la demande de langue).</span><span class="sxs-lookup"><span data-stu-id="43fec-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the language request).</span></span> <span data-ttu-id="43fec-109">La structure contient des informations que la bibliothèque d'API de procédure stockée étendue utilise pour gérer les communications et les données entre l'application et le client.</span><span class="sxs-lookup"><span data-stu-id="43fec-109">The structure contains information that the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="43fec-110">Retours</span><span class="sxs-lookup"><span data-stu-id="43fec-110">Returns</span></span>  
 <span data-ttu-id="43fec-111">SUCCEED ou FAIL.</span><span class="sxs-lookup"><span data-stu-id="43fec-111">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43fec-112">Notes</span><span class="sxs-lookup"><span data-stu-id="43fec-112">Remarks</span></span>  
 <span data-ttu-id="43fec-113">La fonction **srv_sendrow** est appelée une fois pour chaque ligne envoyée au client.</span><span class="sxs-lookup"><span data-stu-id="43fec-113">The **srv_sendrow** function is called once for each row sent to the client.</span></span> <span data-ttu-id="43fec-114">Toutes les lignes doivent être envoyées au client avant que les messages, valeurs d'état ou états d'achèvement ne soient envoyés avec **srv_sendmsg**, **srv_status**ou **srv_senddone**.</span><span class="sxs-lookup"><span data-stu-id="43fec-114">All rows must be sent to the client before any messages, status values, or completion statuses are sent with **srv_sendmsg**, **srv_status**, or **srv_senddone**.</span></span>  
  
 <span data-ttu-id="43fec-115">L'envoi d'une ligne dont toutes les colonnes n'ont pas été définies avec **srv_describe** oblige l'application de l'API de procédure stockée étendue à déclencher un message d'erreur d'information et à retourner FAIL au client.</span><span class="sxs-lookup"><span data-stu-id="43fec-115">Sending a row that has not had all its columns defined with **srv_describe** causes the Extended Stored Procedure API application to raise an informational error message and return FAIL to the client.</span></span> <span data-ttu-id="43fec-116">Dans ce cas, la ligne n'est pas envoyée.</span><span class="sxs-lookup"><span data-stu-id="43fec-116">In this case, the row is not sent.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="43fec-117">L'API de procédure stockée étendue ne prend pas en charge l'envoi de lignes calculées au client.</span><span class="sxs-lookup"><span data-stu-id="43fec-117">The Extended Stored Procedure API does not support sending compute rows to the client.</span></span> <span data-ttu-id="43fec-118">En outre, si une ligne contenant des données `ntext`, `text` ou `image` est envoyée au client, le pointeur de texte et l'horodateur de texte ne sont pas inclus.</span><span class="sxs-lookup"><span data-stu-id="43fec-118">Also, if a row containing `ntext`, `text`, or `image` data is sent to the client, the text pointer and text timestamp are not included.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="43fec-119">Il est préférable d'examiner avec soin le code source des procédures stockées étendues et de tester les DLL compilées avant de les installer sur un serveur de production.</span><span class="sxs-lookup"><span data-stu-id="43fec-119">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="43fec-120">Pour plus d'informations sur l'examen et les tests de sécurité, consultez ce [site Web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="43fec-120">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43fec-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="43fec-121">See Also</span></span>  
 [<span data-ttu-id="43fec-122">srv_describe &#40;API de procédure stockée étendue&#41;</span><span class="sxs-lookup"><span data-stu-id="43fec-122">srv_describe &#40;Extended Stored Procedure API&#41;</span></span>](srv-describe-extended-stored-procedure-api.md)  
  
  
