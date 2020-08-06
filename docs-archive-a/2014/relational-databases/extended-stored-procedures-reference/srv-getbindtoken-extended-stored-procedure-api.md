---
title: srv_getbindtoken (API de procédure stockée étendue) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_getbindtoken
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_getbindtoken
ms.assetid: c947d011-08ac-4fb8-b925-3da6e0999277
author: rothja
ms.author: jroth
ms.openlocfilehash: d42f95c8a7df87f20ebaa30501b96b5f2a00815a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614064"
---
# <a name="srv_getbindtoken-extended-stored-procedure-api"></a><span data-ttu-id="486a5-102">srv_getbindtoken (API de procédure stockée étendue)</span><span class="sxs-lookup"><span data-stu-id="486a5-102">srv_getbindtoken (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="486a5-103">Utilisez l’intégration CLR à la place.</span><span class="sxs-lookup"><span data-stu-id="486a5-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="486a5-104">Obtient un jeton de liaison de la transaction dans la session cliente actuelle qui appelle la procédure stockée étendue.</span><span class="sxs-lookup"><span data-stu-id="486a5-104">Obtains a bind token of the transaction in the current client session that invokes the extended stored procedure.</span></span>  
  
 <span data-ttu-id="486a5-105">La procédure stockée étendue peut utiliser ensuite **sp_bindsession** pour lier toute nouvelle session qu’elle crée sur le même serveur à la transaction existante, afin que la nouvelle session puisse partager le même espace de verrouillage de transaction avec la session cliente qui a appelé la procédure stockée étendue.</span><span class="sxs-lookup"><span data-stu-id="486a5-105">The extended stored procedure can then use **sp_bindsession** to bind any new session it creates against the same server to the existing transaction so that the new session can share the same transaction lock space with the client session that invoked the extended stored procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="486a5-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="486a5-106">Syntax</span></span>  
  
```  
  
int srv_getbindtoken (  
SRV_PROC*  
srvproc  
,  
char*  
bindtoken  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="486a5-107">Arguments</span><span class="sxs-lookup"><span data-stu-id="486a5-107">Arguments</span></span>  
 <span data-ttu-id="486a5-108">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="486a5-108">*srvproc*</span></span>  
 <span data-ttu-id="486a5-109">Pointeur vers la structure SRV_PROC qui est le handle pour une connexion cliente particulière.</span><span class="sxs-lookup"><span data-stu-id="486a5-109">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection.</span></span> <span data-ttu-id="486a5-110">La structure contient toutes les informations que la bibliothèque d'API de procédure stockée étendue utilise pour gérer les communications et les données entre l'application et le client.</span><span class="sxs-lookup"><span data-stu-id="486a5-110">The structure contains all the information that the Extended Stored Procedure API library uses to manage communications and data between the application and the client.</span></span>  
  
 <span data-ttu-id="486a5-111">*bindtoken*</span><span class="sxs-lookup"><span data-stu-id="486a5-111">*bindtoken*</span></span>  
 <span data-ttu-id="486a5-112">Pointeur vers une mémoire tampon où le jeton de liaison sera copié.</span><span class="sxs-lookup"><span data-stu-id="486a5-112">Is a pointer to a buffer where the bind token will be copied.</span></span> <span data-ttu-id="486a5-113">Le jeton de liaison est représenté sous la forme d'une chaîne terminée par le caractère NULL.</span><span class="sxs-lookup"><span data-stu-id="486a5-113">The bind token is represented as a null-terminated string.</span></span> <span data-ttu-id="486a5-114">La mémoire tampon que vous spécifiez doit avoir une longueur minimale de 255 octets.</span><span class="sxs-lookup"><span data-stu-id="486a5-114">The buffer you specify should be at least 255 bytes in length.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="486a5-115">Retours</span><span class="sxs-lookup"><span data-stu-id="486a5-115">Returns</span></span>  
 <span data-ttu-id="486a5-116">SUCCEED ou FAIL.</span><span class="sxs-lookup"><span data-stu-id="486a5-116">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="486a5-117">Notes</span><span class="sxs-lookup"><span data-stu-id="486a5-117">Remarks</span></span>  
  
### <a name="to-bind-an-extended-stored-procedure-session-to-the-client-session-that-called-it-so-they-share-the-same-transaction-lock-space"></a><span data-ttu-id="486a5-118">Pour lier une session de procédure stockée étendue à la session cliente qui l'a appelée pour qu'elles partagent le même espace de verrouillage de transaction</span><span class="sxs-lookup"><span data-stu-id="486a5-118">To bind an extended stored procedure session to the client session that called it so they share the same transaction lock space</span></span>  
  
1.  <span data-ttu-id="486a5-119">La procédure stockée étendue appelle **svr_getbindtoken** pour obtenir le jeton de liaison pour la transaction en cours dans la session.</span><span class="sxs-lookup"><span data-stu-id="486a5-119">The extended stored procedure calls **svr_getbindtoken** to get the bind token for the current transaction in the session.</span></span> <span data-ttu-id="486a5-120">Le jeton est retourné dans le paramètre *bindtoken* donné.</span><span class="sxs-lookup"><span data-stu-id="486a5-120">The token is returned in the given *bindtoken* parameter.</span></span>  
  
2.  <span data-ttu-id="486a5-121">La procédure stockée étendue ouvre une ou de nouvelles sessions sur le même serveur.</span><span class="sxs-lookup"><span data-stu-id="486a5-121">The extended stored procedure opens new session(s) against the same server.</span></span> <span data-ttu-id="486a5-122">Au sein de cette session, la procédure stockée étendue utilise le jeton de liaison avec **sp_bindsession** pour lier la nouvelle session à la même transaction.</span><span class="sxs-lookup"><span data-stu-id="486a5-122">Inside that session, the extended stored procedure uses the bind token with **sp_bindsession** to bind the new session to the same transaction.</span></span> <span data-ttu-id="486a5-123">La procédure stockée étendue peut créer plusieurs sessions et lier toutes les sessions à la même transaction.</span><span class="sxs-lookup"><span data-stu-id="486a5-123">The extended stored procedure can create multiple sessions and bind all the sessions to the same transaction.</span></span>  
  
3.  <span data-ttu-id="486a5-124">Une session liée est détachée quand la procédure stockée externe retourne une chaîne vide ou quand **sp_bindsession** est appelé avec une chaîne vide.</span><span class="sxs-lookup"><span data-stu-id="486a5-124">A bound session is unbound when the external stored procedure returns or when **sp_bindsession** is called with an empty string.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="486a5-125">Une seule session liée peut avoir accès à une connexion partagée à la fois.</span><span class="sxs-lookup"><span data-stu-id="486a5-125">Only one bound session at a time can have access to a shared connection.</span></span> <span data-ttu-id="486a5-126">Si une session exécute une instruction côté serveur ou si elle attend des résultats du serveur, aucune autre session partageant la même connexion liée ne peut accéder au serveur tant que la session active n'a pas fini d'exécuter l'instruction en cours.</span><span class="sxs-lookup"><span data-stu-id="486a5-126">If one session is currently executing a statement at the server or has results pending from the server, no other sessions sharing the same bound connection can gain access to the server until the current session has finished executing the current statement.</span></span> <span data-ttu-id="486a5-127">Si une session essaie d'accéder à la connexion pendant que le serveur est occupé, une erreur est retournée à la session en conflit, qui indique que la connexion est en cours d'utilisation et que la session doit réessayer ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="486a5-127">If a session attempts to gain access to the connection while the server is busy, an error is returned to the conflicting session indicating the connection is in use and the session should retry later.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="486a5-128">Il est préférable d'examiner avec soin le code source des procédures stockées étendues et de tester les DLL compilées avant de les installer sur un serveur de production.</span><span class="sxs-lookup"><span data-stu-id="486a5-128">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="486a5-129">Pour plus d'informations sur l'examen et les tests de sécurité, consultez ce [site Web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="486a5-129">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="486a5-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="486a5-130">See Also</span></span>  
 <span data-ttu-id="486a5-131">[sp_bindsession &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-bindsession-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="486a5-131">[sp_bindsession &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-bindsession-transact-sql) </span></span>  
 [<span data-ttu-id="486a5-132">sp_getbindtoken &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="486a5-132">sp_getbindtoken &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-getbindtoken-transact-sql)  
  
  
