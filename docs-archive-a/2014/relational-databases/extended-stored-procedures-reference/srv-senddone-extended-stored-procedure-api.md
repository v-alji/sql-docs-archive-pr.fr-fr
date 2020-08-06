---
title: srv_senddone (API de procédure stockée étendue) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_senddone
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_senddone
ms.assetid: 1fc4f1d5-56d4-43f6-b5e4-0c0cc295cba3
author: rothja
ms.author: jroth
ms.openlocfilehash: 877acdc1b666c7f4cbaab737590a1c55e474eb05
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710599"
---
# <a name="srv_senddone-extended-stored-procedure-api"></a><span data-ttu-id="de3ca-102">srv_senddone (API de procédure stockée étendue)</span><span class="sxs-lookup"><span data-stu-id="de3ca-102">srv_senddone (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="de3ca-103">Utilisez l’intégration CLR à la place.</span><span class="sxs-lookup"><span data-stu-id="de3ca-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="de3ca-104">Envoie un message d'achèvement de résultat au client.</span><span class="sxs-lookup"><span data-stu-id="de3ca-104">Sends a result completion message to the client.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de3ca-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="de3ca-105">Syntax</span></span>  
  
```  
  
int srv_senddone (  
SRV_PROC *  
srvproc  
,  
DBUSMALLINT   
status  
,  
DBUSMALLINT  
info  
,  
DBINT  
count   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="de3ca-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="de3ca-106">Arguments</span></span>  
 <span data-ttu-id="de3ca-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="de3ca-107">*srvproc*</span></span>  
 <span data-ttu-id="de3ca-108">Pointeur vers la structure SRV_PROC qui est le handle d'une connexion cliente particulière (dans ce cas, le handle qui a reçu la demande de langue).</span><span class="sxs-lookup"><span data-stu-id="de3ca-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the language request).</span></span> <span data-ttu-id="de3ca-109">La structure contient des informations que la bibliothèque d'API de procédure stockée étendue utilise pour gérer les communications et les données entre l'application et le client.</span><span class="sxs-lookup"><span data-stu-id="de3ca-109">The structure contains information that the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="de3ca-110">*statut*</span><span class="sxs-lookup"><span data-stu-id="de3ca-110">*status*</span></span>  
 <span data-ttu-id="de3ca-111">Champ de deux octets pour différents indicateurs *status* .</span><span class="sxs-lookup"><span data-stu-id="de3ca-111">Is a 2-byte field for various *status* flags.</span></span> <span data-ttu-id="de3ca-112">Vous pouvez définir plusieurs indicateurs à l'aide des opérateurs logiques AND et OR avec des valeurs d'indicateur *status* .</span><span class="sxs-lookup"><span data-stu-id="de3ca-112">Multiple flags can be set by using the AND and OR logical operators with *status* flag values.</span></span> <span data-ttu-id="de3ca-113">Le tableau suivant répertorie les indicateurs *status* possibles.</span><span class="sxs-lookup"><span data-stu-id="de3ca-113">The following table lists possible *status* flags.</span></span>  
  
|<span data-ttu-id="de3ca-114">Indicateur d'état</span><span class="sxs-lookup"><span data-stu-id="de3ca-114">Status flag</span></span>|<span data-ttu-id="de3ca-115">Description</span><span class="sxs-lookup"><span data-stu-id="de3ca-115">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="de3ca-116">SRV_DONE_COUNT</span><span class="sxs-lookup"><span data-stu-id="de3ca-116">SRV_DONE_COUNT</span></span>|<span data-ttu-id="de3ca-117">Le paramètre *count* contient un nombre valide.</span><span class="sxs-lookup"><span data-stu-id="de3ca-117">The *count* parameter contains a valid count.</span></span>|  
|<span data-ttu-id="de3ca-118">SRV_DONE_ERROR</span><span class="sxs-lookup"><span data-stu-id="de3ca-118">SRV_DONE_ERROR</span></span>|<span data-ttu-id="de3ca-119">La commande cliente actuelle a reçu une erreur.</span><span class="sxs-lookup"><span data-stu-id="de3ca-119">The current client command received an error.</span></span>|  
  
 <span data-ttu-id="de3ca-120">*info*</span><span class="sxs-lookup"><span data-stu-id="de3ca-120">*info*</span></span>  
 <span data-ttu-id="de3ca-121">Champ réservé de deux octets.</span><span class="sxs-lookup"><span data-stu-id="de3ca-121">Is a reserved, 2-byte field.</span></span> <span data-ttu-id="de3ca-122">Attribuez à ce champ la valeur 0.</span><span class="sxs-lookup"><span data-stu-id="de3ca-122">Set this value to 0.</span></span>  
  
 <span data-ttu-id="de3ca-123">*count*</span><span class="sxs-lookup"><span data-stu-id="de3ca-123">*count*</span></span>  
 <span data-ttu-id="de3ca-124">Champ de quatre octets utilisé pour indiquer un nombre pour le jeu de résultats actuel.</span><span class="sxs-lookup"><span data-stu-id="de3ca-124">Is a 4-byte field used to indicate a count for the current result set.</span></span> <span data-ttu-id="de3ca-125">Si l'indicateur SRV_DONE_COUNT est défini dans le champ *status* , *count* contient un nombre valide.</span><span class="sxs-lookup"><span data-stu-id="de3ca-125">If the SRV_DONE_COUNT flag is set in the *status* field, *count* holds a valid count.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="de3ca-126">Retours</span><span class="sxs-lookup"><span data-stu-id="de3ca-126">Returns</span></span>  
 <span data-ttu-id="de3ca-127">SUCCEED ou FAIL</span><span class="sxs-lookup"><span data-stu-id="de3ca-127">SUCCEED or FAIL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="de3ca-128">Notes</span><span class="sxs-lookup"><span data-stu-id="de3ca-128">Remarks</span></span>  
 <span data-ttu-id="de3ca-129">Une requête du client peut faire en sorte que le serveur exécute plusieurs commandes et retourne plusieurs jeux de résultats.</span><span class="sxs-lookup"><span data-stu-id="de3ca-129">A client request can cause the server to execute a number of commands and to return a number of result sets.</span></span> <span data-ttu-id="de3ca-130">Pour chaque jeu de résultats, **srv_senddone** doit retourner un message d'achèvement de résultat au client.</span><span class="sxs-lookup"><span data-stu-id="de3ca-130">For each result set, **srv_senddone** must return a result completion message to the client.</span></span>  
  
 <span data-ttu-id="de3ca-131">Le champ *count* indique le nombre de lignes affectées par une commande.</span><span class="sxs-lookup"><span data-stu-id="de3ca-131">The *count* field indicates the number of rows affected by a command.</span></span> <span data-ttu-id="de3ca-132">Si le champ *count* contient un nombre, l'indicateur SRV_DONE_COUNT doit être défini dans le champ *status* .</span><span class="sxs-lookup"><span data-stu-id="de3ca-132">If the *count* field contains a count, the SRV_DONE_COUNT flag should be set in the *status* field.</span></span> <span data-ttu-id="de3ca-133">Ce paramètre permet au client d'effectuer la distinction entre une valeur *count* de 0 et un champ *count* inutilisé.</span><span class="sxs-lookup"><span data-stu-id="de3ca-133">This setting allows the client to distinguish between a *count* value of 0 and an unused *count* field.</span></span>  
  
 <span data-ttu-id="de3ca-134">N'appelez pas **srv_senddone** à partir du gestionnaire SRV_CONNECT.</span><span class="sxs-lookup"><span data-stu-id="de3ca-134">Do not call **srv_senddone** from the SRV_CONNECT handler.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="de3ca-135">Il est préférable d'examiner avec soin le code source des procédures stockées étendues et de tester les DLL compilées avant de les installer sur un serveur de production.</span><span class="sxs-lookup"><span data-stu-id="de3ca-135">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="de3ca-136">Pour plus d'informations sur l'examen et les tests de sécurité, consultez ce [site Web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="de3ca-136">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
