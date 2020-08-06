---
title: srv_pfieldex (API de procédure stockée étendue) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_pfieldex
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_pfieldex
ms.assetid: d4e9a34b-b3a3-434f-8556-768bd20d145a
author: rothja
ms.author: jroth
ms.openlocfilehash: a474eafcb6b6d42161a7e67ce7f93636269c46c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602841"
---
# <a name="srv_pfieldex-extended-stored-procedure-api"></a><span data-ttu-id="cdede-102">srv_pfieldex (API de procédure stockée étendue)</span><span class="sxs-lookup"><span data-stu-id="cdede-102">srv_pfieldex (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="cdede-103">Utilisez l’intégration CLR à la place.</span><span class="sxs-lookup"><span data-stu-id="cdede-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="cdede-104">Retourne un pointeur vers des données qui contiennent le champ SRV_PROC demandé.</span><span class="sxs-lookup"><span data-stu-id="cdede-104">Returns a pointer to data containing the requested SRV_PROC field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cdede-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="cdede-105">Syntax</span></span>  
  
```  
  
void *srv_pfieldex(SRV_PROC *   
srvproc  
, int   
field  
, int *   
len  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="cdede-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="cdede-106">Arguments</span></span>  
 <span data-ttu-id="cdede-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="cdede-107">*srvproc*</span></span>  
 <span data-ttu-id="cdede-108">Pointeur vers la structure SRV_PROC qui est le handle pour une connexion cliente particulière.</span><span class="sxs-lookup"><span data-stu-id="cdede-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection.</span></span> <span data-ttu-id="cdede-109">La structure contient des informations que la bibliothèque d'API de procédure stockée étendue utilise pour gérer les communications et les données entre l'application et le client.</span><span class="sxs-lookup"><span data-stu-id="cdede-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="cdede-110">*case*</span><span class="sxs-lookup"><span data-stu-id="cdede-110">*field*</span></span>  
 <span data-ttu-id="cdede-111">Spécifie le champ *srvproc* à retourner.</span><span class="sxs-lookup"><span data-stu-id="cdede-111">Specifies the *srvproc* field to return.</span></span>  
  
|<span data-ttu-id="cdede-112">Champ</span><span class="sxs-lookup"><span data-stu-id="cdede-112">Field</span></span>|<span data-ttu-id="cdede-113">Description</span><span class="sxs-lookup"><span data-stu-id="cdede-113">Description</span></span>|<span data-ttu-id="cdede-114">Type renvoyé</span><span class="sxs-lookup"><span data-stu-id="cdede-114">Return-type</span></span>|  
|-----------|-----------------|------------------|  
|<span data-ttu-id="cdede-115">SRV_MSGLCID</span><span class="sxs-lookup"><span data-stu-id="cdede-115">SRV_MSGLCID</span></span>|<span data-ttu-id="cdede-116">LCID du message de la session active.</span><span class="sxs-lookup"><span data-stu-id="cdede-116">Current session message LCID.</span></span>|<span data-ttu-id="cdede-117">ULONG\*</span><span class="sxs-lookup"><span data-stu-id="cdede-117">ULONG\*</span></span>|  
|<span data-ttu-id="cdede-118">SRV_INSTANCENAME</span><span class="sxs-lookup"><span data-stu-id="cdede-118">SRV_INSTANCENAME</span></span>|<span data-ttu-id="cdede-119">Nom de l'instance (si elle est nommée) ; sinon, retourne NULL.</span><span class="sxs-lookup"><span data-stu-id="cdede-119">Instance name (if named); otherwise, returns NULL.</span></span>|<span data-ttu-id="cdede-120">WCHAR\*</span><span class="sxs-lookup"><span data-stu-id="cdede-120">WCHAR\*</span></span>|  
  
 <span data-ttu-id="cdede-121">*Len*</span><span class="sxs-lookup"><span data-stu-id="cdede-121">*len*</span></span>  
 <span data-ttu-id="cdede-122">Pointeur vers une variable **int** contenant la longueur de la valeur *field* retournée en octets.</span><span class="sxs-lookup"><span data-stu-id="cdede-122">Is a pointer to an **int** variable that contains the length of the returned *field* value in bytes.</span></span> <span data-ttu-id="cdede-123">Si *len* a la valeur NULL, la longueur n’est pas retournée.</span><span class="sxs-lookup"><span data-stu-id="cdede-123">If *len* is NULL, the length is not returned.</span></span> <span data-ttu-id="cdede-124">Quand NULL est retourné \**len* a la valeur 0.</span><span class="sxs-lookup"><span data-stu-id="cdede-124">When NULL is returned \**len* is set to 0.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="cdede-125">Retours</span><span class="sxs-lookup"><span data-stu-id="cdede-125">Returns</span></span>  
 <span data-ttu-id="cdede-126">Pointeur vers des données dont le type dépend de *field*.</span><span class="sxs-lookup"><span data-stu-id="cdede-126">A pointer to data whose type depends on *field*.</span></span> <span data-ttu-id="cdede-127">NULL est retourné quand *len* a la valeur 0 ou quand *srvproc* a la valeur NULL.</span><span class="sxs-lookup"><span data-stu-id="cdede-127">NULL is returned when *len* is NULL or *srvproc* is NULL.</span></span> <span data-ttu-id="cdede-128">Si *field* est inconnu, la valeur NULL est retournée.</span><span class="sxs-lookup"><span data-stu-id="cdede-128">If the *field* is unknown, NULL is returned.</span></span> <span data-ttu-id="cdede-129">Quand NULL est retourné \**len* a la valeur 0.</span><span class="sxs-lookup"><span data-stu-id="cdede-129">When NULL is returned \**len* is set to 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="cdede-130">La mémoire tampon retournée à partir du serveur doit être en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="cdede-130">The buffer returned from the server should be read only.</span></span> <span data-ttu-id="cdede-131">Dans le cas contraire, l'état du serveur peut être endommagé.</span><span class="sxs-lookup"><span data-stu-id="cdede-131">Otherwise, the server state may be corrupted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cdede-132">Notes</span><span class="sxs-lookup"><span data-stu-id="cdede-132">Remarks</span></span>  
 <span data-ttu-id="cdede-133">**Remarque relative à la sécurité** Il est recommandé de revoir en détail le code source des procédures stockées étendues et de tester les DLL compilées avant de les installer sur un serveur de production.</span><span class="sxs-lookup"><span data-stu-id="cdede-133">**Security Note** You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="cdede-134">Pour plus d'informations sur l'examen et les tests de sécurité, consultez ce [site Web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="cdede-134">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
