---
title: srv_message_handler (API de procédure stockée étendue) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_message_handler
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_message_handler
ms.assetid: 41bcd057-436f-4fa8-8293-fc8057a30877
author: rothja
ms.author: jroth
ms.openlocfilehash: 7e7b6472ed4fabb6dc2d545eb51a1e026635ce19
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602845"
---
# <a name="srv_message_handler-extended-stored-procedure-api"></a><span data-ttu-id="af9de-102">srv_message_handler (API de procédure stockée étendue)</span><span class="sxs-lookup"><span data-stu-id="af9de-102">srv_message_handler (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="af9de-103">Utilisez l’intégration CLR à la place.</span><span class="sxs-lookup"><span data-stu-id="af9de-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="af9de-104">Appelle le gestionnaire de messages de l'API de procédure stockée étendue installée.</span><span class="sxs-lookup"><span data-stu-id="af9de-104">Calls the installed Extended Stored Procedure API message handler.</span></span> <span data-ttu-id="af9de-105">Cette fonction est généralement utilisée pour appeler [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à partir d’une procédure stockée étendue afin de consigner une erreur (définie par la procédure stockée étendue) dans le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fichier journal des erreurs ou le [!INCLUDE[msCoName](../../includes/msconame-md.md)] Journal des applications Windows.</span><span class="sxs-lookup"><span data-stu-id="af9de-105">This function is usually used to call [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from an extended stored procedure to log an error (defined by the extended stored procedure) in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log file or the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows application log.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af9de-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="af9de-106">Syntax</span></span>  
  
```  
  
int srv_message_handler (  
SRV_PROC *  
srvproc  
,  
int  
errornum  
,  
BYTE   
severity  
,  
BYTE  
state  
,  
int  
oserrnum  
,  
char *  
errtext  
,  
int  
errtextlen  
,  
char *  
oserrtext  
,  
int  
oserrtextlen  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="af9de-107">Arguments</span><span class="sxs-lookup"><span data-stu-id="af9de-107">Arguments</span></span>  
 <span data-ttu-id="af9de-108">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="af9de-108">*srvproc*</span></span>  
 <span data-ttu-id="af9de-109">Pointeur vers la structure SRV_PROC qui est le handle pour une connexion cliente particulière.</span><span class="sxs-lookup"><span data-stu-id="af9de-109">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection.</span></span> <span data-ttu-id="af9de-110">Le paramètre *srvproc* contient des informations utilisées pour gérer les communications et les données entre l’application et le client.</span><span class="sxs-lookup"><span data-stu-id="af9de-110">The *srvproc* parameter contains information that is used to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="af9de-111">*errornum*</span><span class="sxs-lookup"><span data-stu-id="af9de-111">*errornum*</span></span>  
 <span data-ttu-id="af9de-112">Numéro d'erreur défini par la procédure stockée étendue.</span><span class="sxs-lookup"><span data-stu-id="af9de-112">Is an error number defined by the extended stored procedure.</span></span> <span data-ttu-id="af9de-113">Ce nombre doit être compris entre 50 001 et 2 147 483 647.</span><span class="sxs-lookup"><span data-stu-id="af9de-113">This number must be from 50,001 through 2,147,483,647.</span></span>  
  
 <span data-ttu-id="af9de-114">*severity*</span><span class="sxs-lookup"><span data-stu-id="af9de-114">*severity*</span></span>  
 <span data-ttu-id="af9de-115">Valeur de gravité [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] standard pour l'erreur.</span><span class="sxs-lookup"><span data-stu-id="af9de-115">Is a standard [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] severity value for the error.</span></span> <span data-ttu-id="af9de-116">Ce nombre doit être compris entre 0 et 24.</span><span class="sxs-lookup"><span data-stu-id="af9de-116">This number must be from 0 through 24.</span></span>  
  
 <span data-ttu-id="af9de-117">*state*</span><span class="sxs-lookup"><span data-stu-id="af9de-117">*state*</span></span>  
 <span data-ttu-id="af9de-118">Valeur d'état [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour l'erreur.</span><span class="sxs-lookup"><span data-stu-id="af9de-118">Is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] state value for the error.</span></span>  
  
 <span data-ttu-id="af9de-119">*oserrnum*</span><span class="sxs-lookup"><span data-stu-id="af9de-119">*oserrnum*</span></span>  
 <span data-ttu-id="af9de-120">Numéro d'erreur du système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="af9de-120">Is the operating-system error number.</span></span> <span data-ttu-id="af9de-121">Cet argument est ignoré.</span><span class="sxs-lookup"><span data-stu-id="af9de-121">This argument is ignored.</span></span>  
  
 <span data-ttu-id="af9de-122">*errtext*</span><span class="sxs-lookup"><span data-stu-id="af9de-122">*errtext*</span></span>  
 <span data-ttu-id="af9de-123">Description de l’erreur de la procédure stockée étendue *errornum*.</span><span class="sxs-lookup"><span data-stu-id="af9de-123">Is the description of the extended stored procedure error *errornum*.</span></span>  
  
 <span data-ttu-id="af9de-124">*errtextlen*</span><span class="sxs-lookup"><span data-stu-id="af9de-124">*errtextlen*</span></span>  
 <span data-ttu-id="af9de-125">Longueur de la chaîne d’erreur de la procédure stockée étendue *errtext*.</span><span class="sxs-lookup"><span data-stu-id="af9de-125">Is the length of the extended stored procedure error string *errtext*.</span></span>  
  
 <span data-ttu-id="af9de-126">*oserrtext*</span><span class="sxs-lookup"><span data-stu-id="af9de-126">*oserrtext*</span></span>  
 <span data-ttu-id="af9de-127">Description de l’erreur du système d’exploitation *oserrnum*.</span><span class="sxs-lookup"><span data-stu-id="af9de-127">Is the description of the operating-system error *oserrnum*.</span></span> <span data-ttu-id="af9de-128">Cet argument est ignoré.</span><span class="sxs-lookup"><span data-stu-id="af9de-128">This argument is ignored.</span></span>  
  
 <span data-ttu-id="af9de-129">*oserrtextlen*</span><span class="sxs-lookup"><span data-stu-id="af9de-129">*oserrtextlen*</span></span>  
 <span data-ttu-id="af9de-130">Longueur de la chaîne d’erreur du système d’exploitation *oserrtext*.</span><span class="sxs-lookup"><span data-stu-id="af9de-130">Is the length of the operating-system error string *oserrtext*.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="af9de-131">Retours</span><span class="sxs-lookup"><span data-stu-id="af9de-131">Returns</span></span>  
 <span data-ttu-id="af9de-132">SUCCEED ou FAIL.</span><span class="sxs-lookup"><span data-stu-id="af9de-132">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="af9de-133">Notes</span><span class="sxs-lookup"><span data-stu-id="af9de-133">Remarks</span></span>  
 <span data-ttu-id="af9de-134">La fonction **srv_message_handler** permet l’intégration d’une procédure stockée étendue aux fonctionnalités centralisées de journalisation des erreurs et de création de rapports de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="af9de-134">The **srv_message_handler** function enables an extended stored procedure to integrate with the centralized error logging and reporting features of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="af9de-135">Vous pouvez établir des alertes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour les événements de procédures stockées étendues, et SQL Server Agent surveillera ces conditions d’alerte.</span><span class="sxs-lookup"><span data-stu-id="af9de-135">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alerts can be established for events from extended stored procedures, and SQL Server Agent will monitor for these alert conditions.</span></span>  
  
 <span data-ttu-id="af9de-136">Si le message d'erreur est plus long, il est tronqué à 412 octets.</span><span class="sxs-lookup"><span data-stu-id="af9de-136">If the error message is longer, it is truncated to 412 bytes.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="af9de-137">Il est préférable d'examiner avec soin le code source des procédures stockées étendues et de tester les DLL compilées avant de les installer sur un serveur de production.</span><span class="sxs-lookup"><span data-stu-id="af9de-137">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="af9de-138">Pour plus d'informations sur l'examen et les tests de sécurité, consultez ce [site Web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="af9de-138">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
