---
title: srv_paramlen (API de procédure stockée étendue) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_paramlen
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_paramlen
ms.assetid: d1fe92ff-cad6-4396-8216-125e5642e81e
author: rothja
ms.author: jroth
ms.openlocfilehash: fc2a0fa7f8409767a2afaa9c4c621ea72732b701
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709491"
---
# <a name="srv_paramlen-extended-stored-procedure-api"></a><span data-ttu-id="67759-102">srv_paramlen (API de procédure stockée étendue)</span><span class="sxs-lookup"><span data-stu-id="67759-102">srv_paramlen (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="67759-103">Utilisez l’intégration CLR à la place.</span><span class="sxs-lookup"><span data-stu-id="67759-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="67759-104">Retourne la longueur de données d'un paramètre d'appel de procédure stockée distante.</span><span class="sxs-lookup"><span data-stu-id="67759-104">Returns the data length of a remote stored procedure call parameter.</span></span> <span data-ttu-id="67759-105">Cette fonction a été remplacée par la fonction **srv_paraminfo**.</span><span class="sxs-lookup"><span data-stu-id="67759-105">This function has been superseded by the **srv_paraminfo** function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67759-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="67759-106">Syntax</span></span>  
  
```  
  
int srv_paramlen (  
SRV_PROC *  
srvproc  
,  
int  
n   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="67759-107">Arguments</span><span class="sxs-lookup"><span data-stu-id="67759-107">Arguments</span></span>  
 <span data-ttu-id="67759-108">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="67759-108">*srvproc*</span></span>  
 <span data-ttu-id="67759-109">Pointeur vers la structure SRV_PROC qui correspond au handle d'une connexion cliente particulière (dans ce cas, le handle qui a reçu l'appel de procédure stockée distante).</span><span class="sxs-lookup"><span data-stu-id="67759-109">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure call).</span></span> <span data-ttu-id="67759-110">La structure contient des informations que la bibliothèque d'API de procédure stockée étendue utilise pour gérer les communications et les données entre l'application et le client.</span><span class="sxs-lookup"><span data-stu-id="67759-110">The structure contains information that the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="67759-111">*n*</span><span class="sxs-lookup"><span data-stu-id="67759-111">*n*</span></span>  
 <span data-ttu-id="67759-112">Indique le numéro du paramètre.</span><span class="sxs-lookup"><span data-stu-id="67759-112">Indicates the number of the parameter.</span></span> <span data-ttu-id="67759-113">Le premier paramètre est 1.</span><span class="sxs-lookup"><span data-stu-id="67759-113">The first parameter is 1.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="67759-114">Retours</span><span class="sxs-lookup"><span data-stu-id="67759-114">Returns</span></span>  
 <span data-ttu-id="67759-115">Longueur réelle, en octets, des données de paramètre.</span><span class="sxs-lookup"><span data-stu-id="67759-115">The actual length, in bytes, of the parameter data.</span></span> <span data-ttu-id="67759-116">En l’absence de *n*ième paramètre ou de procédure stockée distante, la valeur -1 est retournée.</span><span class="sxs-lookup"><span data-stu-id="67759-116">If there is no *n*th parameter or there is no remote stored procedure, it returns -1.</span></span> <span data-ttu-id="67759-117">Si le *n*ième paramètre est NULL, la valeur retournée est 0.</span><span class="sxs-lookup"><span data-stu-id="67759-117">If the *n*th parameter is NULL, it returns 0.</span></span>  
  
 <span data-ttu-id="67759-118">Cette fonction retourne les valeurs suivantes, si le paramètre est l’un des [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] types de données système suivants.</span><span class="sxs-lookup"><span data-stu-id="67759-118">This function returns the following values, if the parameter is one of the following [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] system data types.</span></span>  
  
|<span data-ttu-id="67759-119">Nouveaux types de données</span><span class="sxs-lookup"><span data-stu-id="67759-119">New data types</span></span>|<span data-ttu-id="67759-120">Longueur de données d'entrée</span><span class="sxs-lookup"><span data-stu-id="67759-120">Input data length</span></span>|  
|--------------------|-----------------------|  
|`BITN`|<span data-ttu-id="67759-121">**NULL :** 1</span><span class="sxs-lookup"><span data-stu-id="67759-121">**NULL:** 1</span></span><br /><br /> <span data-ttu-id="67759-122">**Zéro :** 1</span><span class="sxs-lookup"><span data-stu-id="67759-122">**ZERO:** 1</span></span><br /><br /> <span data-ttu-id="67759-123">**>= 255 :** NON APPLICABLE</span><span class="sxs-lookup"><span data-stu-id="67759-123">**>=255:** N/A</span></span><br /><br /> <span data-ttu-id="67759-124">**<255 :** NON APPLICABLE</span><span class="sxs-lookup"><span data-stu-id="67759-124">**<255:** N/A</span></span>|  
|`BIGVARCHAR`|<span data-ttu-id="67759-125">**NULL :** 0</span><span class="sxs-lookup"><span data-stu-id="67759-125">**NULL:** 0</span></span><br /><br /> <span data-ttu-id="67759-126">**Zéro :** 1</span><span class="sxs-lookup"><span data-stu-id="67759-126">**ZERO:** 1</span></span><br /><br /> <span data-ttu-id="67759-127">**>= 255 :** 255</span><span class="sxs-lookup"><span data-stu-id="67759-127">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="67759-128">\**<255 :\*\*\*len* réel</span><span class="sxs-lookup"><span data-stu-id="67759-128">**<255:** actual *len*</span></span>|  
|`BIGCHAR`|<span data-ttu-id="67759-129">**NULL :** 0</span><span class="sxs-lookup"><span data-stu-id="67759-129">**NULL:** 0</span></span><br /><br /> <span data-ttu-id="67759-130">**ZERO :** 255</span><span class="sxs-lookup"><span data-stu-id="67759-130">**ZERO:** 255</span></span><br /><br /> <span data-ttu-id="67759-131">**>= 255 :** 255</span><span class="sxs-lookup"><span data-stu-id="67759-131">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="67759-132">**<255:** 255</span><span class="sxs-lookup"><span data-stu-id="67759-132">**<255:** 255</span></span>|  
|`BIGBINARY`|<span data-ttu-id="67759-133">**NULL :** 0</span><span class="sxs-lookup"><span data-stu-id="67759-133">**NULL:** 0</span></span><br /><br /> <span data-ttu-id="67759-134">**ZERO :** 255</span><span class="sxs-lookup"><span data-stu-id="67759-134">**ZERO:** 255</span></span><br /><br /> <span data-ttu-id="67759-135">**>= 255 :** 255</span><span class="sxs-lookup"><span data-stu-id="67759-135">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="67759-136">**<255:** 255</span><span class="sxs-lookup"><span data-stu-id="67759-136">**<255:** 255</span></span>|  
|`BIGVARBINARY`|<span data-ttu-id="67759-137">**NULL :** 0</span><span class="sxs-lookup"><span data-stu-id="67759-137">**NULL:** 0</span></span><br /><br /> <span data-ttu-id="67759-138">**Zéro :** 1</span><span class="sxs-lookup"><span data-stu-id="67759-138">**ZERO:** 1</span></span><br /><br /> <span data-ttu-id="67759-139">**>= 255 :** 255</span><span class="sxs-lookup"><span data-stu-id="67759-139">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="67759-140">\**<255 :\*\*\*len* réel</span><span class="sxs-lookup"><span data-stu-id="67759-140">**<255:** actual *len*</span></span>|  
|`NCHAR`|<span data-ttu-id="67759-141">**NULL :** 0</span><span class="sxs-lookup"><span data-stu-id="67759-141">**NULL:** 0</span></span><br /><br /> <span data-ttu-id="67759-142">**ZERO :** 255</span><span class="sxs-lookup"><span data-stu-id="67759-142">**ZERO:** 255</span></span><br /><br /> <span data-ttu-id="67759-143">**>= 255 :** 255</span><span class="sxs-lookup"><span data-stu-id="67759-143">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="67759-144">**<255:** 255</span><span class="sxs-lookup"><span data-stu-id="67759-144">**<255:** 255</span></span>|  
|`NVARCHAR`|<span data-ttu-id="67759-145">**NULL :** 0</span><span class="sxs-lookup"><span data-stu-id="67759-145">**NULL:** 0</span></span><br /><br /> <span data-ttu-id="67759-146">**Zéro :** 1</span><span class="sxs-lookup"><span data-stu-id="67759-146">**ZERO:** 1</span></span><br /><br /> <span data-ttu-id="67759-147">**>= 255 :** 255</span><span class="sxs-lookup"><span data-stu-id="67759-147">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="67759-148">\**<255 :\*\*\*len* réel</span><span class="sxs-lookup"><span data-stu-id="67759-148">**<255:** actual *len*</span></span>|  
|`NTEXT`|<span data-ttu-id="67759-149">**Null :** -1</span><span class="sxs-lookup"><span data-stu-id="67759-149">**NULL:** -1</span></span><br /><br /> <span data-ttu-id="67759-150">**ZERO :** -1</span><span class="sxs-lookup"><span data-stu-id="67759-150">**ZERO:** -1</span></span><br /><br /> <span data-ttu-id="67759-151">**>= 255 :** -1</span><span class="sxs-lookup"><span data-stu-id="67759-151">**>=255:** -1</span></span><br /><br /> <span data-ttu-id="67759-152">**<255 :** -1</span><span class="sxs-lookup"><span data-stu-id="67759-152">**<255:** -1</span></span>|  
  
 <span data-ttu-id="67759-153">\**len* réel = longueur de chaîne de caractères multioctets (cch)</span><span class="sxs-lookup"><span data-stu-id="67759-153">\*   actual *len* = Length of multibyte character string (cch)</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="67759-154">Notes</span><span class="sxs-lookup"><span data-stu-id="67759-154">Remarks</span></span>  
 <span data-ttu-id="67759-155">Chaque paramètre de procédure stockée distante possède une longueur de données réelle et une longueur de données maximale.</span><span class="sxs-lookup"><span data-stu-id="67759-155">Each remote stored procedure parameter has an actual and a maximum data length.</span></span> <span data-ttu-id="67759-156">Pour les types de données de longueur fixe standard qui n'autorisent pas les valeurs NULL, les longueurs réelle et maximale sont les mêmes.</span><span class="sxs-lookup"><span data-stu-id="67759-156">For standard fixed-length data types that do not allow null values, the actual and maximum lengths are the same.</span></span> <span data-ttu-id="67759-157">Pour les types de données de longueur variable, les longueurs peuvent varier.</span><span class="sxs-lookup"><span data-stu-id="67759-157">For variable-length data types, the lengths can vary.</span></span> <span data-ttu-id="67759-158">Par exemple, un paramètre déclaré comme `varchar(30)` peut posséder des données longues de 10 octets seulement.</span><span class="sxs-lookup"><span data-stu-id="67759-158">For example, a parameter declared as `varchar(30)` can have data that is only 10 bytes long.</span></span> <span data-ttu-id="67759-159">La longueur réelle du paramètre est 10 et sa longueur maximale est 30.</span><span class="sxs-lookup"><span data-stu-id="67759-159">The parameter's actual length is 10 and its maximum length is 30.</span></span> <span data-ttu-id="67759-160">La fonction **srv_paramlen** obtient la longueur de données réelle, en octets, d’une procédure stockée distante.</span><span class="sxs-lookup"><span data-stu-id="67759-160">The **srv_paramlen** function gets the actual data length, in bytes, of a remote stored procedure.</span></span> <span data-ttu-id="67759-161">Pour obtenir la longueur de données maximale d’un paramètre, utilisez **srv_parammaxlen**.</span><span class="sxs-lookup"><span data-stu-id="67759-161">To obtain the maximum data length of a parameter, use **srv_parammaxlen**.</span></span>  
  
 <span data-ttu-id="67759-162">Quand un appel de procédure stockée distante est effectué avec des paramètres, ceux-ci peuvent être passés par nom ou par position (sans nom).</span><span class="sxs-lookup"><span data-stu-id="67759-162">When a remote stored procedure call is made with parameters, the parameters can be passed either by name or by position (unnamed).</span></span> <span data-ttu-id="67759-163">Si l'appel de procédure stockée distante est effectué avec certains paramètres passés par nom et certains passés par position, une erreur se produit.</span><span class="sxs-lookup"><span data-stu-id="67759-163">If the remote stored procedure call is made with some parameters passed by name and some passed by position, an error occurs.</span></span> <span data-ttu-id="67759-164">Le gestionnaire de SRV_RPC est toujours appelé, mais il apparaît comme s’il n’y avait aucun paramètre et **srv_rpcparams** retourne 0.</span><span class="sxs-lookup"><span data-stu-id="67759-164">The SRV_RPC handler is still called, but it appears as if there were no parameters and **srv_rpcparams** returns 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="67759-165">Il est préférable d'examiner avec soin le code source des procédures stockées étendues et de tester les DLL compilées avant de les installer sur un serveur de production.</span><span class="sxs-lookup"><span data-stu-id="67759-165">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="67759-166">Pour plus d'informations sur l'examen et les tests de sécurité, consultez ce [site Web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="67759-166">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67759-167">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="67759-167">See Also</span></span>  
 <span data-ttu-id="67759-168">[srv_paraminfo &#40;API de procédure stockée étendue&#41;](srv-paraminfo-extended-stored-procedure-api.md) </span><span class="sxs-lookup"><span data-stu-id="67759-168">[srv_paraminfo &#40;Extended Stored Procedure API&#41;](srv-paraminfo-extended-stored-procedure-api.md) </span></span>  
 [<span data-ttu-id="67759-169">srv_rpcparams &#40;API de procédure stockée étendue&#41;</span><span class="sxs-lookup"><span data-stu-id="67759-169">srv_rpcparams &#40;Extended Stored Procedure API&#41;</span></span>](srv-rpcparams-extended-stored-procedure-api.md)  
  
  
