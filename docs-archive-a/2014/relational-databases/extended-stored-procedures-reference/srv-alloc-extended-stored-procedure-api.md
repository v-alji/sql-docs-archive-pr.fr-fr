---
title: srv_alloc (API de procédure stockée étendue) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_alloc
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_alloc
ms.assetid: 91505c59-a273-452f-b71d-5e8205c21863
author: rothja
ms.author: jroth
ms.openlocfilehash: 7b372c1b43987e5bebd1fb82e995dc6d262455ae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602846"
---
# <a name="srv_alloc-extended-stored-procedure-api"></a><span data-ttu-id="44282-102">srv_alloc (API de procédure stockée étendue)</span><span class="sxs-lookup"><span data-stu-id="44282-102">srv_alloc (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="44282-103">Utilisez l’intégration CLR à la place.</span><span class="sxs-lookup"><span data-stu-id="44282-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="44282-104">Alloue la mémoire dynamiquement.</span><span class="sxs-lookup"><span data-stu-id="44282-104">Allocates memory dynamically.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44282-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="44282-105">Syntax</span></span>  
  
```  
  
void * srv_alloc ( DBINT  
size  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="44282-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="44282-106">Arguments</span></span>  
 <span data-ttu-id="44282-107">*size*</span><span class="sxs-lookup"><span data-stu-id="44282-107">*size*</span></span>  
 <span data-ttu-id="44282-108">Spécifie le nombre d'octets à allouer.</span><span class="sxs-lookup"><span data-stu-id="44282-108">Specifies the number of bytes to allocate.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="44282-109">Retours</span><span class="sxs-lookup"><span data-stu-id="44282-109">Returns</span></span>  
 <span data-ttu-id="44282-110">Un pointeur vers l'espace qui vient d'être alloué.</span><span class="sxs-lookup"><span data-stu-id="44282-110">A pointer to the newly allocated space.</span></span> <span data-ttu-id="44282-111">Si *size* octets ne peuvent pas être alloués, un pointeur Null est retourné.</span><span class="sxs-lookup"><span data-stu-id="44282-111">If *size* bytes cannot be allocated, a null pointer is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44282-112">Notes</span><span class="sxs-lookup"><span data-stu-id="44282-112">Remarks</span></span>  
 <span data-ttu-id="44282-113">La fonction **srv_alloc** est équivalente à la fonction API [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows **GlobalAlloc**.</span><span class="sxs-lookup"><span data-stu-id="44282-113">The **srv_alloc** function is equivalent to the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows API  **GlobalAlloc** function.</span></span> <span data-ttu-id="44282-114">Les fonctions ordinaires de gestion de la mémoire du runtime C de l'API Windows peuvent être utilisées dans une application API de procédure stockée étendue.</span><span class="sxs-lookup"><span data-stu-id="44282-114">Normal Windows API C run-time memory management functions can be used in an Extended Stored Procedure API application.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="44282-115">Il est préférable d'examiner avec soin le code source des procédures stockées étendues et de tester les DLL compilées avant de les installer sur un serveur de production.</span><span class="sxs-lookup"><span data-stu-id="44282-115">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="44282-116">Pour plus d'informations sur l'examen et les tests de sécurité, consultez ce [site Web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="44282-116">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
