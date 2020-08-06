---
title: srv_paramdata (API de procédure stockée étendue) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_paramdata
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_paramdata
ms.assetid: 3104514d-b404-47c9-b6d7-928106384874
author: rothja
ms.author: jroth
ms.openlocfilehash: 092ca5b811a12c3e6b199a6041ce6e4f8e02f4b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612346"
---
# <a name="srv_paramdata-extended-stored-procedure-api"></a><span data-ttu-id="54f04-102">srv_paramdata (API de procédure stockée étendue)</span><span class="sxs-lookup"><span data-stu-id="54f04-102">srv_paramdata (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="54f04-103">Utilisez l’intégration CLR à la place.</span><span class="sxs-lookup"><span data-stu-id="54f04-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="54f04-104">Retourne la valeur d'un paramètre d'appel de procédure stockée distante.</span><span class="sxs-lookup"><span data-stu-id="54f04-104">Returns the value of a remote stored procedure call parameter.</span></span> <span data-ttu-id="54f04-105">Cette fonction a été remplacée par la fonction **srv_paraminfo**.</span><span class="sxs-lookup"><span data-stu-id="54f04-105">This function has been superseded by the **srv_paraminfo** function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54f04-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="54f04-106">Syntax</span></span>  
  
```  
  
void * srv_paramdata (  
SRV_PROC *  
srvproc  
,  
int  
n   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="54f04-107">Arguments</span><span class="sxs-lookup"><span data-stu-id="54f04-107">Arguments</span></span>  
 <span data-ttu-id="54f04-108">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="54f04-108">*srvproc*</span></span>  
 <span data-ttu-id="54f04-109">Pointeur vers la structure SRV_PROC qui correspond au handle d'une connexion cliente particulière (dans ce cas, le handle qui a reçu l'appel de procédure stockée distante).</span><span class="sxs-lookup"><span data-stu-id="54f04-109">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure call).</span></span> <span data-ttu-id="54f04-110">La structure contient des informations que la bibliothèque de procédure stockée étendue utilise pour gérer les communications et les données entre l'application et le client.</span><span class="sxs-lookup"><span data-stu-id="54f04-110">The structure contains information the Extended Stored Procedure library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="54f04-111">*n*</span><span class="sxs-lookup"><span data-stu-id="54f04-111">*n*</span></span>  
 <span data-ttu-id="54f04-112">Numéro du paramètre.</span><span class="sxs-lookup"><span data-stu-id="54f04-112">Is the number of the parameter.</span></span> <span data-ttu-id="54f04-113">Le premier paramètre est le numéro 1.</span><span class="sxs-lookup"><span data-stu-id="54f04-113">The first parameter is number 1.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="54f04-114">Retours</span><span class="sxs-lookup"><span data-stu-id="54f04-114">Returns</span></span>  
 <span data-ttu-id="54f04-115">Pointeur vers la valeur de paramètre.</span><span class="sxs-lookup"><span data-stu-id="54f04-115">A pointer to the parameter value.</span></span> <span data-ttu-id="54f04-116">Si le *n*ième paramètre est NULL, qu’il n’y a pas de *n*ième paramètre ou qu’il n’y a aucune procédure stockée distante, la valeur NULL est retournée.</span><span class="sxs-lookup"><span data-stu-id="54f04-116">If the *n*th parameter is NULL, there is no *n*th parameter, or there is no remote stored procedure, returns NULL.</span></span> <span data-ttu-id="54f04-117">Si la valeur de paramètre est une chaîne, elle peut ne pas se terminer par le caractère NULL.</span><span class="sxs-lookup"><span data-stu-id="54f04-117">If the parameter value is a string, it might not be null-terminated.</span></span> <span data-ttu-id="54f04-118">Utilisez **srv_paramlen** pour déterminer la longueur de la chaîne.</span><span class="sxs-lookup"><span data-stu-id="54f04-118">Use **srv_paramlen** to determine the length of the string.</span></span>  
  
 <span data-ttu-id="54f04-119">Cette fonction retourne les valeurs suivantes, si le paramètre est l’un des [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] types de données.</span><span class="sxs-lookup"><span data-stu-id="54f04-119">This function returns the following values, if the parameter is one of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types.</span></span> <span data-ttu-id="54f04-120">Les données du pointeur indiquent si le pointeur pour le type de données est valide (VP), NULL ou non applicable (N/A), et le contenu des données désignées par le pointeur.</span><span class="sxs-lookup"><span data-stu-id="54f04-120">Pointer data includes whether the pointer for the data type is valid (VP), NULL, or not applicable (N/A), and the contents of the data pointed to.</span></span>  
  
|<span data-ttu-id="54f04-121">Nouveaux types de données</span><span class="sxs-lookup"><span data-stu-id="54f04-121">New data types</span></span>|<span data-ttu-id="54f04-122">Longueur de données d'entrée</span><span class="sxs-lookup"><span data-stu-id="54f04-122">Input data length</span></span>|  
|--------------------|-----------------------|  
|<span data-ttu-id="54f04-123">BITN</span><span class="sxs-lookup"><span data-stu-id="54f04-123">BITN</span></span>|<span data-ttu-id="54f04-124">**NULL :** VP, NULL</span><span class="sxs-lookup"><span data-stu-id="54f04-124">**NULL:** VP, NULL</span></span><br /><br /> <span data-ttu-id="54f04-125">**ZERO :** VP, NULL</span><span class="sxs-lookup"><span data-stu-id="54f04-125">**ZERO:** VP, NULL</span></span><br /><br /> <span data-ttu-id="54f04-126">**>= 255 :** NON APPLICABLE</span><span class="sxs-lookup"><span data-stu-id="54f04-126">**>=255:** N/A</span></span><br /><br /> <span data-ttu-id="54f04-127">**<255 :** NON APPLICABLE</span><span class="sxs-lookup"><span data-stu-id="54f04-127">**<255:** N/A</span></span>|  
|<span data-ttu-id="54f04-128">BIGVARCHAR</span><span class="sxs-lookup"><span data-stu-id="54f04-128">BIGVARCHAR</span></span>|<span data-ttu-id="54f04-129">**NULL :** NULL, N/A</span><span class="sxs-lookup"><span data-stu-id="54f04-129">**NULL:** NULL, N/A</span></span><br /><br /> <span data-ttu-id="54f04-130">**ZERO :** VP, NULL</span><span class="sxs-lookup"><span data-stu-id="54f04-130">**ZERO:** VP, NULL</span></span><br /><br /> <span data-ttu-id="54f04-131">**>=255 :** VP, 255 caractères</span><span class="sxs-lookup"><span data-stu-id="54f04-131">**>=255:** VP, 255 chars</span></span><br /><br /> <span data-ttu-id="54f04-132">**<255 :** VP, données réelles</span><span class="sxs-lookup"><span data-stu-id="54f04-132">**<255:** VP, actual data</span></span>|  
|<span data-ttu-id="54f04-133">BIGCHAR</span><span class="sxs-lookup"><span data-stu-id="54f04-133">BIGCHAR</span></span>|<span data-ttu-id="54f04-134">**NULL :** NULL, N/A</span><span class="sxs-lookup"><span data-stu-id="54f04-134">**NULL:** NULL, N/A</span></span><br /><br /> <span data-ttu-id="54f04-135">**ZERO :** VP, 255 espaces</span><span class="sxs-lookup"><span data-stu-id="54f04-135">**ZERO:** VP, 255 spaces</span></span><br /><br /> <span data-ttu-id="54f04-136">**>=255 :** VP, 255 caractères</span><span class="sxs-lookup"><span data-stu-id="54f04-136">**>=255:** VP, 255 chars</span></span><br /><br /> <span data-ttu-id="54f04-137">**<255 :** VP, données réelles + remplissage (jusqu’à 255)</span><span class="sxs-lookup"><span data-stu-id="54f04-137">**<255:** VP, actual data + padding (up to 255)</span></span>|  
|<span data-ttu-id="54f04-138">BIGBINARY</span><span class="sxs-lookup"><span data-stu-id="54f04-138">BIGBINARY</span></span>|<span data-ttu-id="54f04-139">**NULL :** NULL, N/A</span><span class="sxs-lookup"><span data-stu-id="54f04-139">**NULL:** NULL, N/A</span></span><br /><br /> <span data-ttu-id="54f04-140">**ZERO :** VP, 255 0x00</span><span class="sxs-lookup"><span data-stu-id="54f04-140">**ZERO:** VP, 255 0x00</span></span><br /><br /> <span data-ttu-id="54f04-141">**>=255 :** VP, 255 octets</span><span class="sxs-lookup"><span data-stu-id="54f04-141">**>=255:** VP, 255 bytes</span></span><br /><br /> <span data-ttu-id="54f04-142">**<255 :** VP, données réelles + remplissage (jusqu’à 255)</span><span class="sxs-lookup"><span data-stu-id="54f04-142">**<255:** VP, actual data + padding (up to 255)</span></span>|  
|<span data-ttu-id="54f04-143">BIGVARBINARY</span><span class="sxs-lookup"><span data-stu-id="54f04-143">BIGVARBINARY</span></span>|<span data-ttu-id="54f04-144">**NULL :** NULL, N/A</span><span class="sxs-lookup"><span data-stu-id="54f04-144">**NULL:** NULL, N/A</span></span><br /><br /> <span data-ttu-id="54f04-145">**ZERO :** VP, 0x00</span><span class="sxs-lookup"><span data-stu-id="54f04-145">**ZERO:** VP, 0x00</span></span><br /><br /> <span data-ttu-id="54f04-146">**>=255 :** VP, 255 octets</span><span class="sxs-lookup"><span data-stu-id="54f04-146">**>=255:** VP, 255 bytes</span></span><br /><br /> <span data-ttu-id="54f04-147">**<255 :** VP, données réelles</span><span class="sxs-lookup"><span data-stu-id="54f04-147">**<255:** VP, actual data</span></span>|  
|<span data-ttu-id="54f04-148">NCHAR</span><span class="sxs-lookup"><span data-stu-id="54f04-148">NCHAR</span></span>|<span data-ttu-id="54f04-149">**NULL :** NULL, N/A</span><span class="sxs-lookup"><span data-stu-id="54f04-149">**NULL:** NULL, N/A</span></span><br /><br /> <span data-ttu-id="54f04-150">**ZERO :** VP, 255 espaces</span><span class="sxs-lookup"><span data-stu-id="54f04-150">**ZERO:** VP, 255 spaces</span></span><br /><br /> <span data-ttu-id="54f04-151">**>=255 :** VP, 255 caractères</span><span class="sxs-lookup"><span data-stu-id="54f04-151">**>=255:** VP, 255 chars</span></span><br /><br /> <span data-ttu-id="54f04-152">**<255 :** VP, données réelles + remplissage (jusqu’à 255)</span><span class="sxs-lookup"><span data-stu-id="54f04-152">**<255:** VP, actual data + padding (up to 255)</span></span>|  
|<span data-ttu-id="54f04-153">NVARCHAR</span><span class="sxs-lookup"><span data-stu-id="54f04-153">NVARCHAR</span></span>|<span data-ttu-id="54f04-154">**NULL :** NULL, N/A</span><span class="sxs-lookup"><span data-stu-id="54f04-154">**NULL:** NULL, N/A</span></span><br /><br /> <span data-ttu-id="54f04-155">**ZERO :** VP, NULL</span><span class="sxs-lookup"><span data-stu-id="54f04-155">**ZERO:** VP, NULL</span></span><br /><br /> <span data-ttu-id="54f04-156">**>=255 :** VP, 255 caractères</span><span class="sxs-lookup"><span data-stu-id="54f04-156">**>=255:** VP, 255 chars</span></span><br /><br /> <span data-ttu-id="54f04-157">**<255 :** VP, données réelles</span><span class="sxs-lookup"><span data-stu-id="54f04-157">**<255:** VP, actual data</span></span>|  
|<span data-ttu-id="54f04-158">NTEXT</span><span class="sxs-lookup"><span data-stu-id="54f04-158">NTEXT</span></span>|<span data-ttu-id="54f04-159">**NULL :** N/A</span><span class="sxs-lookup"><span data-stu-id="54f04-159">**NULL:** N/A</span></span><br /><br /> <span data-ttu-id="54f04-160">**ZERO :** N/A</span><span class="sxs-lookup"><span data-stu-id="54f04-160">**ZERO:** N/A</span></span><br /><br /> <span data-ttu-id="54f04-161">**>= 255 :** NON APPLICABLE</span><span class="sxs-lookup"><span data-stu-id="54f04-161">**>=255:** N/A</span></span><br /><br /> <span data-ttu-id="54f04-162">\*\* \< 255 :\*\* N/A</span><span class="sxs-lookup"><span data-stu-id="54f04-162">**\<255:** N/A</span></span>|  
  
 <span data-ttu-id="54f04-163">\*   Les données ne se terminent pas par le caractère NULL ; aucun avertissement n’est émis en cas de troncation de données >255 caractères.</span><span class="sxs-lookup"><span data-stu-id="54f04-163">\*   data is not null-terminated; no warning is issued on truncation for data >255 characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="54f04-164">Notes</span><span class="sxs-lookup"><span data-stu-id="54f04-164">Remarks</span></span>  
 <span data-ttu-id="54f04-165">Si vous connaissez le nom du paramètre, vous pouvez utiliser **srv_paramnumber** pour obtenir le numéro du paramètre.</span><span class="sxs-lookup"><span data-stu-id="54f04-165">If you know the parameter name, you can use **srv_paramnumber** to get the parameter number.</span></span> <span data-ttu-id="54f04-166">Pour déterminer si un paramètre est NULL, utilisez **srv_paramlen**.</span><span class="sxs-lookup"><span data-stu-id="54f04-166">To determine whether a parameter is NULL, use **srv_paramlen**.</span></span>  
  
 <span data-ttu-id="54f04-167">Lorsqu'un appel de procédure stockée distante est effectué avec des paramètres, ceux-ci peuvent être passés par nom ou par position (sans nom).</span><span class="sxs-lookup"><span data-stu-id="54f04-167">When a remote stored procedure call is made with parameters, the parameters can be passed by name or by position (unnamed).</span></span> <span data-ttu-id="54f04-168">Si l'appel de procédure stockée distante est effectué avec certains paramètres passés par nom et certains passés par position, une erreur se produit.</span><span class="sxs-lookup"><span data-stu-id="54f04-168">If the remote stored procedure call is made with some parameters passed by name and some passed by position, an error occurs.</span></span> <span data-ttu-id="54f04-169">Si une erreur se produit, le gestionnaire SRV_RPC est tout de même appelé, mais il apparaît comme s’il n’y avait aucun paramètre et **srv_rpcparams** retourne 0.</span><span class="sxs-lookup"><span data-stu-id="54f04-169">If an error occurs, the SRV_RPC handler is still called, but it appears as if there were no parameters and **srv_rpcparams** returns 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="54f04-170">Il est préférable d'examiner avec soin le code source des procédures stockées étendues et de tester les DLL compilées avant de les installer sur un serveur de production.</span><span class="sxs-lookup"><span data-stu-id="54f04-170">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="54f04-171">Pour plus d'informations sur l'examen et les tests de sécurité, consultez ce [site Web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="54f04-171">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54f04-172">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="54f04-172">See Also</span></span>  
 [<span data-ttu-id="54f04-173">srv_rpcparams &#40;API de procédure stockée étendue&#41;</span><span class="sxs-lookup"><span data-stu-id="54f04-173">srv_rpcparams &#40;Extended Stored Procedure API&#41;</span></span>](srv-rpcparams-extended-stored-procedure-api.md)  
  
  
