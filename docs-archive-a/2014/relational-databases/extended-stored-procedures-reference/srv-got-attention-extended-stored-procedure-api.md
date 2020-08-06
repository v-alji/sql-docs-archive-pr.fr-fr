---
title: srv_got_attention (API de procédure stockée étendue) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_got_attention
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_got_attention
ms.assetid: 805e68e1-d17f-41bd-8b9f-a27283bb6fbe
author: rothja
ms.author: jroth
ms.openlocfilehash: bb5432e2f5e259187e506237842fbb9110e27a69
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709500"
---
# <a name="srv_got_attention-extended-stored-procedure-api"></a><span data-ttu-id="62633-102">srv_got_attention (API de procédure stockée étendue)</span><span class="sxs-lookup"><span data-stu-id="62633-102">srv_got_attention (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="62633-103">Utilisez l’intégration CLR à la place.</span><span class="sxs-lookup"><span data-stu-id="62633-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="62633-104">Vérifie si la connexion ou la tâche en cours a besoin d'être annulée et retourne TRUE si la connexion est arrêtée ou le lot supprimé.</span><span class="sxs-lookup"><span data-stu-id="62633-104">Checks whether the current connection or task needs to be aborted and returns TRUE if the connection is killed or the batch is aborted</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62633-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="62633-105">Syntax</span></span>  
  
```  
  
BOOL srv_got_attention  
(SRV_PROC *  
srvproc  
);  
  
```  
  
#### <a name="parameters"></a><span data-ttu-id="62633-106">Paramètres</span><span class="sxs-lookup"><span data-stu-id="62633-106">Parameters</span></span>  
 <span data-ttu-id="62633-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="62633-107">*srvproc*</span></span>  
 <span data-ttu-id="62633-108">Pointeur identifiant une connexion de base de données.</span><span class="sxs-lookup"><span data-stu-id="62633-108">Pointer identifying a database connection.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="62633-109">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="62633-109">Return Value</span></span>  
 <span data-ttu-id="62633-110">TRUE si la connexion est arrêtée ou le lot supprimé.</span><span class="sxs-lookup"><span data-stu-id="62633-110">TRUE if the connection is killed or the batch is aborted.</span></span> <span data-ttu-id="62633-111">FALSE si la connexion ou le lot est actif.</span><span class="sxs-lookup"><span data-stu-id="62633-111">FALSE if the connection or batch is active.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="62633-112">Notes</span><span class="sxs-lookup"><span data-stu-id="62633-112">Remarks</span></span>  
 <span data-ttu-id="62633-113">Une procédure stockée étendue dont l’exécution est longue doit contrôler l’attention du serveur en appelant périodiquement **srv_got_attention** afin que la procédure puisse se terminer si la connexion est arrêtée ou que le lot est abandonné.</span><span class="sxs-lookup"><span data-stu-id="62633-113">A long-running extended stored procedure should check the server attention by calling **srv_got_attention** periodically so that the procedure may terminate itself when the connection is killed or the batch is aborted.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="62633-114">Il est préférable d'examiner avec soin le code source des procédures stockées étendues et de tester les DLL compilées avant de les installer sur un serveur de production.</span><span class="sxs-lookup"><span data-stu-id="62633-114">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="62633-115">Pour plus d'informations sur l'examen et les tests de sécurité, consultez ce [site Web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="62633-115">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
