---
title: srv_paramset (API de procédure stockée étendue) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_paramset
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_paramset
ms.assetid: 2a509206-a1b8-4b20-b0a2-ef680cef7bd8
author: rothja
ms.author: jroth
ms.openlocfilehash: 9ebe308e5e0c8fc24382582fb71db2f48c77541e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601467"
---
# <a name="srv_paramset-extended-stored-procedure-api"></a><span data-ttu-id="e43a3-102">srv_paramset (API de procédure stockée étendue)</span><span class="sxs-lookup"><span data-stu-id="e43a3-102">srv_paramset (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="e43a3-103">Utilisez l’intégration CLR à la place.</span><span class="sxs-lookup"><span data-stu-id="e43a3-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="e43a3-104">Définit la valeur d'un paramètre de retour d'appel de procédure stockée distante.</span><span class="sxs-lookup"><span data-stu-id="e43a3-104">Sets the value of a remote stored procedure call return parameter.</span></span> <span data-ttu-id="e43a3-105">Cette fonction a été remplacée par la fonction **srv_paramsetoutput**.</span><span class="sxs-lookup"><span data-stu-id="e43a3-105">This function has been superseded by the **srv_paramsetoutput** function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e43a3-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="e43a3-106">Syntax</span></span>  
  
```  
  
int srv_paramset (  
SRV_PROC *  
srvproc  
,  
int  
n  
,   
void *  
data  
,  
int  
len   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="e43a3-107">Arguments</span><span class="sxs-lookup"><span data-stu-id="e43a3-107">Arguments</span></span>  
 <span data-ttu-id="e43a3-108">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="e43a3-108">*srvproc*</span></span>  
 <span data-ttu-id="e43a3-109">Pointeur vers la structure SRV_PROC qui correspond au handle d'une connexion cliente particulière (dans ce cas, le handle qui a reçu l'appel de procédure stockée distante).</span><span class="sxs-lookup"><span data-stu-id="e43a3-109">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure call).</span></span> <span data-ttu-id="e43a3-110">La structure contient des informations que la bibliothèque d'API de procédure stockée étendue utilise pour gérer les communications et les données entre l'application et le client.</span><span class="sxs-lookup"><span data-stu-id="e43a3-110">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="e43a3-111">*n*</span><span class="sxs-lookup"><span data-stu-id="e43a3-111">*n*</span></span>  
 <span data-ttu-id="e43a3-112">Indique le numéro du paramètre à définir.</span><span class="sxs-lookup"><span data-stu-id="e43a3-112">Indicates the number of the parameter to set.</span></span> <span data-ttu-id="e43a3-113">Le premier paramètre est 1.</span><span class="sxs-lookup"><span data-stu-id="e43a3-113">The first parameter is 1.</span></span>  
  
 <span data-ttu-id="e43a3-114">*data*</span><span class="sxs-lookup"><span data-stu-id="e43a3-114">*data*</span></span>  
 <span data-ttu-id="e43a3-115">Pointeur vers la valeur de données à renvoyer au client en tant que paramètre de retour de procédure stockée distante.</span><span class="sxs-lookup"><span data-stu-id="e43a3-115">Is a pointer to the data value to be sent back to the client as the remote stored procedure return parameter.</span></span>  
  
 <span data-ttu-id="e43a3-116">*Len*</span><span class="sxs-lookup"><span data-stu-id="e43a3-116">*len*</span></span>  
 <span data-ttu-id="e43a3-117">Spécifie la longueur réelle des données à retourner.</span><span class="sxs-lookup"><span data-stu-id="e43a3-117">Specifies the actual length of the data to be returned.</span></span> <span data-ttu-id="e43a3-118">Si le type de données du paramètre est de longueur constante et qu’il n’autorise pas les valeurs NULL (par exemple, *srvbit* ou *srvint1*), *len* est ignoré.</span><span class="sxs-lookup"><span data-stu-id="e43a3-118">If the data type of the parameter is of a constant length and does not allow null values (for example, *srvbit* or *srvint1*), *len* is ignored.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="e43a3-119">Retours</span><span class="sxs-lookup"><span data-stu-id="e43a3-119">Returns</span></span>  
 <span data-ttu-id="e43a3-120">SUCCEED si la valeur de paramètre a été correctement définie ; sinon, FAIL.</span><span class="sxs-lookup"><span data-stu-id="e43a3-120">SUCCEED if the parameter value was successfully set; otherwise, FAIL.</span></span> <span data-ttu-id="e43a3-121">FAIL est retourné quand il n’y a pas de procédure stockée distante en cours, quand il n’y a aucun *n*ième paramètre de procédure stockée distante, quand le paramètre n’est pas un paramètre de retour et quand l’argument *len* n’est pas légal.</span><span class="sxs-lookup"><span data-stu-id="e43a3-121">FAIL is returned when there is no current remote stored procedure, when there is no *n*th remote stored procedure parameter, when the parameter is not a return parameter, and when the *len* argument is not legal.</span></span>  
  
 <span data-ttu-id="e43a3-122">Si *len* a pour valeur 0, il retourne NULL.</span><span class="sxs-lookup"><span data-stu-id="e43a3-122">If *len*is 0, it returns NULL.</span></span> <span data-ttu-id="e43a3-123">Pour retourner la valeur NULL au client, la seule façon est d’attribuer la valeur 0 à *len*.</span><span class="sxs-lookup"><span data-stu-id="e43a3-123">Setting *len* to 0 is the only way to return NULL to the client.</span></span>  
  
 <span data-ttu-id="e43a3-124">Cette fonction retourne les valeurs suivantes, si le paramètre est l’un des [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] types de données.</span><span class="sxs-lookup"><span data-stu-id="e43a3-124">This function returns the following values, if the parameter is one of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] data types.</span></span>  
  
|<span data-ttu-id="e43a3-125">Nouveaux types de données</span><span class="sxs-lookup"><span data-stu-id="e43a3-125">New data types</span></span>|<span data-ttu-id="e43a3-126">Longueur de données de retour</span><span class="sxs-lookup"><span data-stu-id="e43a3-126">Return data length</span></span>|  
|--------------------|------------------------|  
|`BITN`|<span data-ttu-id="e43a3-127">**NULL :** *len* = 0, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="e43a3-127">**NULL:** *len* = 0, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="e43a3-128">**ZERO :** N/A</span><span class="sxs-lookup"><span data-stu-id="e43a3-128">**ZERO:** N/A</span></span><br /><br /> <span data-ttu-id="e43a3-129">**>= 255 :** NON APPLICABLE</span><span class="sxs-lookup"><span data-stu-id="e43a3-129">**>=255:** N/A</span></span><br /><br /> <span data-ttu-id="e43a3-130">**<255 :** NON APPLICABLE</span><span class="sxs-lookup"><span data-stu-id="e43a3-130">**<255:** N/A</span></span>|  
|`BIGVARCHAR`|<span data-ttu-id="e43a3-131">**NULL :** *len* = 0, data = IG, RET = 1</span><span class="sxs-lookup"><span data-stu-id="e43a3-131">**NULL:** *len* = 0, data = IG, RET = 1</span></span><br /><br /> <span data-ttu-id="e43a3-132">**ZERO :** *len* = IG, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="e43a3-132">**ZERO:** *len* = IG, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="e43a3-133">**>=255 :** *len* = max8k, data = valide, RET = 0</span><span class="sxs-lookup"><span data-stu-id="e43a3-133">**>=255:** *len* = max8k, data = valid, RET = 0</span></span><br /><br /> <span data-ttu-id="e43a3-134">**<255 :** *len* = <8k, data = valide, RET = 1</span><span class="sxs-lookup"><span data-stu-id="e43a3-134">**<255:** *len* = <8k, data = valid, RET = 1</span></span>|  
|`BIGCHAR`|<span data-ttu-id="e43a3-135">**NULL :** *len* = 0, data = IG, RET = 1</span><span class="sxs-lookup"><span data-stu-id="e43a3-135">**NULL:** *len* = 0, data = IG, RET = 1</span></span><br /><br /> <span data-ttu-id="e43a3-136">**ZERO :** *len* = IG, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="e43a3-136">**ZERO:** *len* = IG, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="e43a3-137">**>=255 :** *len* = max8k, data = valide, RET = 0</span><span class="sxs-lookup"><span data-stu-id="e43a3-137">**>=255:** *len* = max8k, data = valid, RET = 0</span></span><br /><br /> <span data-ttu-id="e43a3-138">**<255 :** *len* = <8k, data = valide, RET = 1</span><span class="sxs-lookup"><span data-stu-id="e43a3-138">**<255:** *len* = <8k, data = valid, RET = 1</span></span>|  
|`BIGBINARY`|<span data-ttu-id="e43a3-139">**NULL :** *len* = 0, data = IG, RET = 1</span><span class="sxs-lookup"><span data-stu-id="e43a3-139">**NULL:** *len* = 0, data = IG, RET = 1</span></span><br /><br /> <span data-ttu-id="e43a3-140">**ZERO :** *len* = IG, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="e43a3-140">**ZERO:** *len* = IG, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="e43a3-141">**>=255 :** *len* = max8k, data = valide, RET = 0</span><span class="sxs-lookup"><span data-stu-id="e43a3-141">**>=255:** *len* = max8k, data = valid, RET = 0</span></span><br /><br /> <span data-ttu-id="e43a3-142">**<255 :** *len* = <8k, data = valide, RET = 1</span><span class="sxs-lookup"><span data-stu-id="e43a3-142">**<255:** *len* = <8k, data = valid, RET = 1</span></span>|  
|`BIGVARBINARY`|<span data-ttu-id="e43a3-143">**NULL :** *len* = 0, data = IG, RET = 1</span><span class="sxs-lookup"><span data-stu-id="e43a3-143">**NULL:** *len* = 0, data = IG, RET = 1</span></span><br /><br /> <span data-ttu-id="e43a3-144">**ZERO :** *len* = IG, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="e43a3-144">**ZERO:** *len* = IG, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="e43a3-145">**>=255 :** *len* = max8k, data = valide, RET = 0</span><span class="sxs-lookup"><span data-stu-id="e43a3-145">**>=255:** *len* = max8k, data = valid, RET = 0</span></span><br /><br /> <span data-ttu-id="e43a3-146">**<255 :** *len* = <8k, data = valide, RET = 1</span><span class="sxs-lookup"><span data-stu-id="e43a3-146">**<255:** *len* = <8k, data = valid, RET = 1</span></span>|  
|<span data-ttu-id="e43a3-147">NCHAR</span><span class="sxs-lookup"><span data-stu-id="e43a3-147">NCHAR</span></span>|<span data-ttu-id="e43a3-148">**NULL :** *len* = 0, data = IG, RET = 1</span><span class="sxs-lookup"><span data-stu-id="e43a3-148">**NULL:** *len* = 0, data = IG, RET = 1</span></span><br /><br /> <span data-ttu-id="e43a3-149">**ZERO :** *len* = IG, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="e43a3-149">**ZERO:** *len* = IG, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="e43a3-150">**>=255 :** *len* = max8k, data = valide, RET = 0</span><span class="sxs-lookup"><span data-stu-id="e43a3-150">**>=255:** *len* = max8k, data = valid, RET = 0</span></span><br /><br /> <span data-ttu-id="e43a3-151">**<255 :** *len* = <8k, data = valide, RET = 1</span><span class="sxs-lookup"><span data-stu-id="e43a3-151">**<255:** *len* = <8k, data = valid, RET = 1</span></span>|  
|<span data-ttu-id="e43a3-152">NVARCHAR</span><span class="sxs-lookup"><span data-stu-id="e43a3-152">NVARCHAR</span></span>|<span data-ttu-id="e43a3-153">**NULL :** *len* = 0, data = IG, RET = 1</span><span class="sxs-lookup"><span data-stu-id="e43a3-153">**NULL:** *len* = 0, data = IG, RET = 1</span></span><br /><br /> <span data-ttu-id="e43a3-154">**ZERO :** *len* = IG, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="e43a3-154">**ZERO:** *len* = IG, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="e43a3-155">**>=255 :** *len* = max8k, data = valide, RET = 0</span><span class="sxs-lookup"><span data-stu-id="e43a3-155">**>=255:** *len* = max8k, data = valid, RET = 0</span></span><br /><br /> <span data-ttu-id="e43a3-156">**<255 :** *len* = <8k, data = valide, RET = 1</span><span class="sxs-lookup"><span data-stu-id="e43a3-156">**<255:** *len* = <8k, data = valid, RET = 1</span></span>|  
|`NTEXT`|<span data-ttu-id="e43a3-157">**NULL :** *len* = IG, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="e43a3-157">**NULL:** *len* = IG, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="e43a3-158">**ZERO :** *len* = IG, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="e43a3-158">**ZERO:** *len* = IG, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="e43a3-159">**>=255 :** *len* = IG, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="e43a3-159">**>=255:** *len* = IG, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="e43a3-160">\*\* \< 255 :\*\* *Len* = IG, données = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="e43a3-160">**\<255:** *len* = IG, data = IG, RET = 0</span></span>|  
|<span data-ttu-id="e43a3-161">RET = Valeur de retour de srv_paramset.</span><span class="sxs-lookup"><span data-stu-id="e43a3-161">RET = Return value of srv_paramset</span></span>||  
|<span data-ttu-id="e43a3-162">IG = La valeur sera ignorée.</span><span class="sxs-lookup"><span data-stu-id="e43a3-162">IG = Value will be ignored</span></span>||  
|<span data-ttu-id="e43a3-163">valide = Tout pointeur valide vers des données.</span><span class="sxs-lookup"><span data-stu-id="e43a3-163">valid = Any valid pointer to data</span></span>||  
  
## <a name="remarks"></a><span data-ttu-id="e43a3-164">Notes</span><span class="sxs-lookup"><span data-stu-id="e43a3-164">Remarks</span></span>  
 <span data-ttu-id="e43a3-165">Les paramètres contiennent les données passées entre les clients et l'application avec des procédures stockées distantes.</span><span class="sxs-lookup"><span data-stu-id="e43a3-165">Parameters contain data passed between clients and the application with remote stored procedures.</span></span> <span data-ttu-id="e43a3-166">Le client peut spécifier certains paramètres en tant que paramètres de retour.</span><span class="sxs-lookup"><span data-stu-id="e43a3-166">The client can specify certain parameters as return parameters.</span></span> <span data-ttu-id="e43a3-167">Ces paramètres de retour peuvent contenir des valeurs que l'application serveur ODS (Open Data Services) repasse au client.</span><span class="sxs-lookup"><span data-stu-id="e43a3-167">These return parameters can contain values that the Open Data Services server application passes back to the client.</span></span> <span data-ttu-id="e43a3-168">L'utilisation de paramètres de retour est analogue au passage de paramètres par référence.</span><span class="sxs-lookup"><span data-stu-id="e43a3-168">Using return parameters is analogous to passing parameters by reference.</span></span>  
  
 <span data-ttu-id="e43a3-169">Vous ne pouvez pas définir la valeur de retour pour un paramètre qui n'a pas été appelé en tant que paramètre de retour.</span><span class="sxs-lookup"><span data-stu-id="e43a3-169">You cannot set the return value for a parameter that wasn't invoked as a return parameter.</span></span> <span data-ttu-id="e43a3-170">Vous pouvez utiliser **srv_paramstatus** pour déterminer comment le paramètre a été appelé.</span><span class="sxs-lookup"><span data-stu-id="e43a3-170">You can use **srv_paramstatus** to determine how the parameter was invoked.</span></span>  
  
 <span data-ttu-id="e43a3-171">Cette fonction définit la valeur de retour pour un paramètre, mais n'envoie pas vraiment la valeur de retour au client.</span><span class="sxs-lookup"><span data-stu-id="e43a3-171">This function sets the return value for a parameter but it does not actually send the return value to the client.</span></span> <span data-ttu-id="e43a3-172">Tous les paramètres de retour, que leurs valeurs de retour aient été définies avec **srv_paramset** ou non, sont automatiquement envoyés au client quand **srv_senddone** est appelé avec l’indicateur d’état défini avec la valeur SRV_DONE_FINAL.</span><span class="sxs-lookup"><span data-stu-id="e43a3-172">All return parameters, whether their return values have been set with **srv_paramset** or not, are automatically sent to the client when **srv_senddone** is called with the status flag SRV_DONE_FINAL set.</span></span>  
  
 <span data-ttu-id="e43a3-173">Quand un appel de procédure stockée distante est effectué avec des paramètres, ceux-ci peuvent être passés par nom ou par position (sans nom).</span><span class="sxs-lookup"><span data-stu-id="e43a3-173">When a remote stored procedure call is made with parameters, the parameters can be passed either by name or by position (unnamed).</span></span> <span data-ttu-id="e43a3-174">Si l'appel de procédure stockée distante est effectué avec certains paramètres passés par nom et certains passés par position, une erreur se produit.</span><span class="sxs-lookup"><span data-stu-id="e43a3-174">If the remote stored procedure call is made with some parameters passed by name and some passed by position, an error occurs.</span></span> <span data-ttu-id="e43a3-175">Le gestionnaire SRV_RPC est tout de même appelé, mais il apparaît comme s’il n’y avait aucun paramètre et **srv_rpcparams** retourne 0.</span><span class="sxs-lookup"><span data-stu-id="e43a3-175">The SRV_RPC handler is still called, but it appears as if there were no parameters, and **srv_rpcparams** returns 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e43a3-176">Il est préférable d'examiner avec soin le code source des procédures stockées étendues et de tester les DLL compilées avant de les installer sur un serveur de production.</span><span class="sxs-lookup"><span data-stu-id="e43a3-176">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="e43a3-177">Pour plus d'informations sur l'examen et les tests de sécurité, consultez ce [site Web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="e43a3-177">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e43a3-178">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e43a3-178">See Also</span></span>  
 [<span data-ttu-id="e43a3-179">srv_paramsetoutput &#40;API de procédure stockée étendue&#41;</span><span class="sxs-lookup"><span data-stu-id="e43a3-179">srv_paramsetoutput &#40;Extended Stored Procedure API&#41;</span></span>](srv-paramsetoutput-extended-stored-procedure-api.md)  
  
  
