---
title: srv_parammaxlen (API de procédure stockée étendue) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_parammaxlen
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_parammaxlen
ms.assetid: 49bfc29d-f76a-4963-b0e6-b8532dfda850
author: rothja
ms.author: jroth
ms.openlocfilehash: b289743b3de4b115a67a029dcc0261854ee3a40b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709487"
---
# <a name="srv_parammaxlen-extended-stored-procedure-api"></a><span data-ttu-id="90bde-102">srv_parammaxlen (API de procédure stockée étendue)</span><span class="sxs-lookup"><span data-stu-id="90bde-102">srv_parammaxlen (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="90bde-103">Utilisez l’intégration CLR à la place.</span><span class="sxs-lookup"><span data-stu-id="90bde-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="90bde-104">Retourne la longueur de données maximale d'un paramètre d'appel de procédure stockée distante.</span><span class="sxs-lookup"><span data-stu-id="90bde-104">Returns the maximum data length of a remote stored procedure call parameter.</span></span> <span data-ttu-id="90bde-105">Cette fonction a été remplacée par la fonction **srv_paraminfo**.</span><span class="sxs-lookup"><span data-stu-id="90bde-105">This function has been superseded by the **srv_paraminfo** function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90bde-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="90bde-106">Syntax</span></span>  
  
```  
  
int srv_parammaxlen (  
SRV_PROC *  
srvproc  
,  
int  
n   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="90bde-107">Arguments</span><span class="sxs-lookup"><span data-stu-id="90bde-107">Arguments</span></span>  
 <span data-ttu-id="90bde-108">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="90bde-108">*srvproc*</span></span>  
 <span data-ttu-id="90bde-109">Pointeur vers la structure SRV_PROC qui correspond au handle d'une connexion cliente particulière (dans ce cas, le handle qui a reçu l'appel de procédure stockée distante).</span><span class="sxs-lookup"><span data-stu-id="90bde-109">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure call).</span></span> <span data-ttu-id="90bde-110">La structure contient des informations que la bibliothèque d'API de procédure stockée étendue utilise pour gérer les communications et les données entre l'application et le client.</span><span class="sxs-lookup"><span data-stu-id="90bde-110">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="90bde-111">*n*</span><span class="sxs-lookup"><span data-stu-id="90bde-111">*n*</span></span>  
 <span data-ttu-id="90bde-112">Indique le numéro du paramètre.</span><span class="sxs-lookup"><span data-stu-id="90bde-112">Indicates the number of the parameter.</span></span> <span data-ttu-id="90bde-113">Le premier paramètre est 1.</span><span class="sxs-lookup"><span data-stu-id="90bde-113">The first parameter is 1.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="90bde-114">Retours</span><span class="sxs-lookup"><span data-stu-id="90bde-114">Returns</span></span>  
 <span data-ttu-id="90bde-115">Longueur maximale, en octets, des données du paramètre.</span><span class="sxs-lookup"><span data-stu-id="90bde-115">The maximum length, in bytes, of the parameter data.</span></span> <span data-ttu-id="90bde-116">En l’absence du *n*ième paramètre ou d’une procédure stockée distante, la valeur -1 est retournée.</span><span class="sxs-lookup"><span data-stu-id="90bde-116">If there is no *n*th parameter or if there is no remote stored procedure, it returns -1.</span></span>  
  
 <span data-ttu-id="90bde-117">Cette fonction retourne les valeurs suivantes, si le paramètre est l’un des [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] types de données suivants.</span><span class="sxs-lookup"><span data-stu-id="90bde-117">This function returns the following values, if the parameter is one of the following [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types.</span></span>  
  
|<span data-ttu-id="90bde-118">Nouveaux types de données</span><span class="sxs-lookup"><span data-stu-id="90bde-118">New data types</span></span>|<span data-ttu-id="90bde-119">Longueur de données d'entrée</span><span class="sxs-lookup"><span data-stu-id="90bde-119">Input data length</span></span>|  
|--------------------|-----------------------|  
|`BITN`|<span data-ttu-id="90bde-120">**NULL :** 1</span><span class="sxs-lookup"><span data-stu-id="90bde-120">**NULL:** 1</span></span><br /><br /> <span data-ttu-id="90bde-121">**Zéro :** 1</span><span class="sxs-lookup"><span data-stu-id="90bde-121">**ZERO:** 1</span></span><br /><br /> <span data-ttu-id="90bde-122">**>= 255 :** NON APPLICABLE</span><span class="sxs-lookup"><span data-stu-id="90bde-122">**>=255:** N/A</span></span><br /><br /> <span data-ttu-id="90bde-123">**<255 :** NON APPLICABLE</span><span class="sxs-lookup"><span data-stu-id="90bde-123">**<255:** N/A</span></span>|  
|`BIGVARCHAR`|<span data-ttu-id="90bde-124">**NULL :** 255</span><span class="sxs-lookup"><span data-stu-id="90bde-124">**NULL:** 255</span></span><br /><br /> <span data-ttu-id="90bde-125">**ZERO :** 255</span><span class="sxs-lookup"><span data-stu-id="90bde-125">**ZERO:** 255</span></span><br /><br /> <span data-ttu-id="90bde-126">**>= 255 :** 255</span><span class="sxs-lookup"><span data-stu-id="90bde-126">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="90bde-127">**<255:** 255</span><span class="sxs-lookup"><span data-stu-id="90bde-127">**<255:** 255</span></span>|  
|`BIGCHAR`|<span data-ttu-id="90bde-128">**NULL :** 255</span><span class="sxs-lookup"><span data-stu-id="90bde-128">**NULL:** 255</span></span><br /><br /> <span data-ttu-id="90bde-129">**ZERO :** 255</span><span class="sxs-lookup"><span data-stu-id="90bde-129">**ZERO:** 255</span></span><br /><br /> <span data-ttu-id="90bde-130">**>= 255 :** 255</span><span class="sxs-lookup"><span data-stu-id="90bde-130">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="90bde-131">**<255:** 255</span><span class="sxs-lookup"><span data-stu-id="90bde-131">**<255:** 255</span></span>|  
|`BIGBINARY`|<span data-ttu-id="90bde-132">**NULL :** 255</span><span class="sxs-lookup"><span data-stu-id="90bde-132">**NULL:** 255</span></span><br /><br /> <span data-ttu-id="90bde-133">**ZERO :** 255</span><span class="sxs-lookup"><span data-stu-id="90bde-133">**ZERO:** 255</span></span><br /><br /> <span data-ttu-id="90bde-134">**>= 255 :** 255</span><span class="sxs-lookup"><span data-stu-id="90bde-134">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="90bde-135">**<255:** 255</span><span class="sxs-lookup"><span data-stu-id="90bde-135">**<255:** 255</span></span>|  
|`BIGVARBINARY`|<span data-ttu-id="90bde-136">**NULL :** 255</span><span class="sxs-lookup"><span data-stu-id="90bde-136">**NULL:** 255</span></span><br /><br /> <span data-ttu-id="90bde-137">**ZERO :** 255</span><span class="sxs-lookup"><span data-stu-id="90bde-137">**ZERO:** 255</span></span><br /><br /> <span data-ttu-id="90bde-138">**>= 255 :** 255</span><span class="sxs-lookup"><span data-stu-id="90bde-138">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="90bde-139">**<255:** 255</span><span class="sxs-lookup"><span data-stu-id="90bde-139">**<255:** 255</span></span>|  
|`NCHAR`|<span data-ttu-id="90bde-140">**NULL :** 255</span><span class="sxs-lookup"><span data-stu-id="90bde-140">**NULL:** 255</span></span><br /><br /> <span data-ttu-id="90bde-141">**ZERO :** 255</span><span class="sxs-lookup"><span data-stu-id="90bde-141">**ZERO:** 255</span></span><br /><br /> <span data-ttu-id="90bde-142">**>= 255 :** 255</span><span class="sxs-lookup"><span data-stu-id="90bde-142">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="90bde-143">**<255:** 255</span><span class="sxs-lookup"><span data-stu-id="90bde-143">**<255:** 255</span></span>|  
|`NVARCHAR`|<span data-ttu-id="90bde-144">**NULL :** 255</span><span class="sxs-lookup"><span data-stu-id="90bde-144">**NULL:** 255</span></span><br /><br /> <span data-ttu-id="90bde-145">**ZERO :** 255</span><span class="sxs-lookup"><span data-stu-id="90bde-145">**ZERO:** 255</span></span><br /><br /> <span data-ttu-id="90bde-146">**>= 255 :** 255</span><span class="sxs-lookup"><span data-stu-id="90bde-146">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="90bde-147">**<255:** 255</span><span class="sxs-lookup"><span data-stu-id="90bde-147">**<255:** 255</span></span>|  
|`NTEXT`|<span data-ttu-id="90bde-148">**Null :** -1</span><span class="sxs-lookup"><span data-stu-id="90bde-148">**NULL:** -1</span></span><br /><br /> <span data-ttu-id="90bde-149">**ZERO :** -1</span><span class="sxs-lookup"><span data-stu-id="90bde-149">**ZERO:** -1</span></span><br /><br /> <span data-ttu-id="90bde-150">**>= 255 :** -1</span><span class="sxs-lookup"><span data-stu-id="90bde-150">**>=255:** -1</span></span><br /><br /> <span data-ttu-id="90bde-151">\*\* \< 255 :\*\* -1</span><span class="sxs-lookup"><span data-stu-id="90bde-151">**\<255:** -1</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="90bde-152">Notes</span><span class="sxs-lookup"><span data-stu-id="90bde-152">Remarks</span></span>  
 <span data-ttu-id="90bde-153">Chaque paramètre de procédure stockée distante possède une longueur de données réelle et une longueur de données maximale.</span><span class="sxs-lookup"><span data-stu-id="90bde-153">Each remote stored procedure parameter has an actual and a maximum data length.</span></span> <span data-ttu-id="90bde-154">Pour les types de données de longueur fixe standard qui n'autorisent pas les valeurs NULL, les longueurs réelle et maximale sont les mêmes.</span><span class="sxs-lookup"><span data-stu-id="90bde-154">For standard fixed-length data types that do not allow null values, the actual and maximum lengths are the same.</span></span> <span data-ttu-id="90bde-155">Pour les types de données de longueur variable, les longueurs peuvent varier.</span><span class="sxs-lookup"><span data-stu-id="90bde-155">For variable-length data types, the lengths can vary.</span></span> <span data-ttu-id="90bde-156">Par exemple, un paramètre déclaré en tant que **varchar(30)** peut posséder des données longues de 10 octets seulement.</span><span class="sxs-lookup"><span data-stu-id="90bde-156">For example, a parameter declared as **varchar(30)** can have data that is only 10 bytes long.</span></span> <span data-ttu-id="90bde-157">La longueur réelle du paramètre est 10 et sa longueur maximale est 30.</span><span class="sxs-lookup"><span data-stu-id="90bde-157">The parameter's actual length is 10 and its maximum length is 30.</span></span> <span data-ttu-id="90bde-158">La fonction **srv_parammaxlen** obtient la longueur de données maximale d’une procédure stockée distante.</span><span class="sxs-lookup"><span data-stu-id="90bde-158">The **srv_parammaxlen** function gets the maximum data length of a remote stored procedure.</span></span> <span data-ttu-id="90bde-159">Pour obtenir la longueur réelle d’un paramètre, utilisez **srv_paramlen**.</span><span class="sxs-lookup"><span data-stu-id="90bde-159">To obtain the actual length of a parameter, use **srv_paramlen**.</span></span>  
  
 <span data-ttu-id="90bde-160">Quand un appel de procédure stockée distante est effectué avec des paramètres, ceux-ci peuvent être passés par nom ou par position (sans nom).</span><span class="sxs-lookup"><span data-stu-id="90bde-160">When a remote stored procedure call is made with parameters, the parameters can be passed either by name or by position (unnamed).</span></span> <span data-ttu-id="90bde-161">Si l'appel de procédure stockée distante est effectué avec certains paramètres passés par nom et certains passés par position, une erreur se produit.</span><span class="sxs-lookup"><span data-stu-id="90bde-161">If the remote stored procedure call is made with some parameters passed by name and some passed by position, an error occurs.</span></span> <span data-ttu-id="90bde-162">Le gestionnaire SRV_RPC est tout de même appelé, mais il apparaît comme s’il n’y avait aucun paramètre et **srv_rpcparams** retourne 0.</span><span class="sxs-lookup"><span data-stu-id="90bde-162">The SRV_RPC handler is still called, but it appears as if there were no parameters, and **srv_rpcparams** returns 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="90bde-163">Il est préférable d'examiner avec soin le code source des procédures stockées étendues et de tester les DLL compilées avant de les installer sur un serveur de production.</span><span class="sxs-lookup"><span data-stu-id="90bde-163">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="90bde-164">Pour plus d'informations sur l'examen et les tests de sécurité, consultez ce [site Web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="90bde-164">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90bde-165">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="90bde-165">See Also</span></span>  
 <span data-ttu-id="90bde-166">[srv_paraminfo &#40;API de procédure stockée étendue&#41;](srv-paraminfo-extended-stored-procedure-api.md) </span><span class="sxs-lookup"><span data-stu-id="90bde-166">[srv_paraminfo &#40;Extended Stored Procedure API&#41;](srv-paraminfo-extended-stored-procedure-api.md) </span></span>  
 [<span data-ttu-id="90bde-167">srv_rpcparams &#40;API de procédure stockée étendue&#41;</span><span class="sxs-lookup"><span data-stu-id="90bde-167">srv_rpcparams &#40;Extended Stored Procedure API&#41;</span></span>](srv-rpcparams-extended-stored-procedure-api.md)  
  
  
