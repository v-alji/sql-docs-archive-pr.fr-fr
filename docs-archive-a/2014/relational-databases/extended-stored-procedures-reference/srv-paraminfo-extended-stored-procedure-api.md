---
title: srv_paraminfo (API de procédure stockée étendue) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_paraminfo
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_paraminfo
ms.assetid: ee2afd4e-0d91-462b-9403-98d481546330
author: rothja
ms.author: jroth
ms.openlocfilehash: cc3d51acc2ca560246c46267840db72934223999
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709499"
---
# <a name="srv_paraminfo-extended-stored-procedure-api"></a><span data-ttu-id="6faa8-102">srv_paraminfo (API de procédure stockée étendue)</span><span class="sxs-lookup"><span data-stu-id="6faa8-102">srv_paraminfo (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="6faa8-103">Utilisez l’intégration CLR à la place.</span><span class="sxs-lookup"><span data-stu-id="6faa8-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="6faa8-104">Retourne des informations sur un paramètre.</span><span class="sxs-lookup"><span data-stu-id="6faa8-104">Returns information about a parameter.</span></span> <span data-ttu-id="6faa8-105">Cette fonction remplace les fonctions suivantes : [srv_paramtype](srv-paramtype-extended-stored-procedure-api.md), [srv_paramlen](srv-paramlen-extended-stored-procedure-api.md), [srv_parammaxlen](srv-parammaxlen-extended-stored-procedure-api.md) et [srv_paramdata](srv-paramdata-extended-stored-procedure-api.md).</span><span class="sxs-lookup"><span data-stu-id="6faa8-105">This function supersedes the following functions: [srv_paramtype](srv-paramtype-extended-stored-procedure-api.md), [srv_paramlen](srv-paramlen-extended-stored-procedure-api.md), [srv_parammaxlen](srv-parammaxlen-extended-stored-procedure-api.md), and [srv_paramdata](srv-paramdata-extended-stored-procedure-api.md).</span></span> <span data-ttu-id="6faa8-106">**srv_paraminfo** prend en charge les types de données dans [Data Types](data-types-extended-stored-procedure-api.md) et les données de longueur nulle.</span><span class="sxs-lookup"><span data-stu-id="6faa8-106">**srv_paraminfo** supports the data types in [Data Types](data-types-extended-stored-procedure-api.md) and zero-length data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6faa8-107">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="6faa8-107">Syntax</span></span>  
  
```  
  
int srv_paraminfo (  
SRV_PROC *  
srvproc  
,  
int  
n  
,  
BYTE *  
pbType  
,  
ULONG *  
pcbMaxLen  
,  
ULONG *  
pcbActualLen  
,  
BYTE *  
pbData  
,  
BOOL *  
pfNull  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="6faa8-108">Arguments</span><span class="sxs-lookup"><span data-stu-id="6faa8-108">Arguments</span></span>  
 <span data-ttu-id="6faa8-109">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="6faa8-109">*srvproc*</span></span>  
 <span data-ttu-id="6faa8-110">Handle d'une connexion cliente.</span><span class="sxs-lookup"><span data-stu-id="6faa8-110">A handle for a client connection.</span></span>  
  
 <span data-ttu-id="6faa8-111">*n*</span><span class="sxs-lookup"><span data-stu-id="6faa8-111">*n*</span></span>  
 <span data-ttu-id="6faa8-112">Nombre ordinal du paramètre à définir.</span><span class="sxs-lookup"><span data-stu-id="6faa8-112">The ordinal number of the parameter to be set.</span></span> <span data-ttu-id="6faa8-113">Le premier paramètre est 1.</span><span class="sxs-lookup"><span data-stu-id="6faa8-113">The first parameter is 1.</span></span>  
  
 <span data-ttu-id="6faa8-114">*pbType*</span><span class="sxs-lookup"><span data-stu-id="6faa8-114">*pbType*</span></span>  
 <span data-ttu-id="6faa8-115">Type de données du paramètre.</span><span class="sxs-lookup"><span data-stu-id="6faa8-115">The data type of the parameter.</span></span>  
  
 <span data-ttu-id="6faa8-116">*pcbMaxLen*</span><span class="sxs-lookup"><span data-stu-id="6faa8-116">*pcbMaxLen*</span></span>  
 <span data-ttu-id="6faa8-117">Pointeur vers la longueur maximale du paramètre.</span><span class="sxs-lookup"><span data-stu-id="6faa8-117">Pointer to the maximum length of the parameter.</span></span>  
  
 <span data-ttu-id="6faa8-118">*pcbActualLen*</span><span class="sxs-lookup"><span data-stu-id="6faa8-118">*pcbActualLen*</span></span>  
 <span data-ttu-id="6faa8-119">Pointeur vers la longueur réelle du paramètre.</span><span class="sxs-lookup"><span data-stu-id="6faa8-119">Pointer to the actual length of the parameter.</span></span> <span data-ttu-id="6faa8-120">La valeur 0 (\**pcbActualLen* == 0) indique des données de longueur nulle si \**pfNull* a la valeur FALSE.</span><span class="sxs-lookup"><span data-stu-id="6faa8-120">A value of 0 (\**pcbActualLen* == 0) signifies zero-length data if \**pfNull* is set to FALSE.</span></span>  
  
 <span data-ttu-id="6faa8-121">*pbData*</span><span class="sxs-lookup"><span data-stu-id="6faa8-121">*pbData*</span></span>  
 <span data-ttu-id="6faa8-122">Pointeur vers la mémoire tampon des données de paramètre.</span><span class="sxs-lookup"><span data-stu-id="6faa8-122">Pointer to the buffer for parameter data.</span></span> <span data-ttu-id="6faa8-123">Si *pbData* n’est pas NULL, l’API de procédure stockée étendue écrit \**pcbActualLen* octets de données dans \**pbData*.</span><span class="sxs-lookup"><span data-stu-id="6faa8-123">If *pbData* is not NULL, the Extended Store Procedure API writes \**pcbActualLen* bytes of data to \**pbData*.</span></span> <span data-ttu-id="6faa8-124">Si *pbData* est NULL, aucune donnée n’est écrite dans \**pbData*, mais la fonction retourne \**pbType*, \**pcbMaxLen*, \**pcbActualLen* et \**pfNull*.</span><span class="sxs-lookup"><span data-stu-id="6faa8-124">If *pbData* is NULL, no data is written to \**pbData* but the function returns \**pbType*, \**pcbMaxLen*, \**pcbActualLen*, and \**pfNull*.</span></span> <span data-ttu-id="6faa8-125">Cette mémoire tampon doit être gérée par l'application.</span><span class="sxs-lookup"><span data-stu-id="6faa8-125">The memory for this buffer must be managed by the application.</span></span>  
  
 <span data-ttu-id="6faa8-126">*pfNull*</span><span class="sxs-lookup"><span data-stu-id="6faa8-126">*pfNull*</span></span>  
 <span data-ttu-id="6faa8-127">Pointeur vers un indicateur null.</span><span class="sxs-lookup"><span data-stu-id="6faa8-127">Pointer to a null flag.</span></span><span data-ttu-id="6faa8-128">\ **pfNull* a la valeur TRUE si la valeur du paramètre est NULL.</span><span class="sxs-lookup"><span data-stu-id="6faa8-128">\ **pfNull* is set to TRUE if the value of the parameter is NULL.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="6faa8-129">Retours</span><span class="sxs-lookup"><span data-stu-id="6faa8-129">Returns</span></span>  
 <span data-ttu-id="6faa8-130">Si les informations sur le paramètre ont été obtenues avec succès, la valeur SUCCEED est retournée ; sinon, FAIL.</span><span class="sxs-lookup"><span data-stu-id="6faa8-130">If the parameter information was successfully obtained, SUCCEED is returned; otherwise, FAIL.</span></span> <span data-ttu-id="6faa8-131">La valeur FAIL est retournée en l’absence de procédure stockée distante active ou en l’absence d’un *n*ième paramètre de procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="6faa8-131">FAIL is returned when there is no current remote stored procedure and when there is no *n*th remote stored procedure parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6faa8-132">Notes</span><span class="sxs-lookup"><span data-stu-id="6faa8-132">Remarks</span></span>  
 <span data-ttu-id="6faa8-133">**Remarque relative à la sécurité** Il est recommandé de revoir en détail le code source des procédures stockées étendues et de tester les DLL compilées avant de les installer sur un serveur de production.</span><span class="sxs-lookup"><span data-stu-id="6faa8-133">**Security Note** You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="6faa8-134">Pour plus d'informations sur l'examen et les tests de sécurité, consultez ce [site Web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="6faa8-134">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6faa8-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6faa8-135">See Also</span></span>  
 [<span data-ttu-id="6faa8-136">Guide de référence du programmeur sur les procédures stockées étendues</span><span class="sxs-lookup"><span data-stu-id="6faa8-136">Extended Stored Procedures Programmer's Reference</span></span>](database-engine-extended-stored-procedures-reference.md)  
  
  
