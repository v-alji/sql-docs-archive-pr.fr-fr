---
title: IBCPSession::BCPExec (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- IBCPSession::BCPExec (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- BCPExec method
ms.assetid: 0f4ebb63-cf03-4e53-846e-6c3021cde007
author: rothja
ms.author: jroth
ms.openlocfilehash: 1452888e046b6223c64a6cdf6fe09b074b815702
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696800"
---
# <a name="ibcpsessionbcpexec-ole-db"></a><span data-ttu-id="7b367-102">IBCPSession::BCPExec (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="7b367-102">IBCPSession::BCPExec (OLE DB)</span></span>
  <span data-ttu-id="7b367-103">Effectue l'opération de copie en bloc.</span><span class="sxs-lookup"><span data-stu-id="7b367-103">Performs the bulk copy operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b367-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="7b367-104">Syntax</span></span>  
  
```  
  
HRESULT BCPExec(   
DBROWCOUNT *pRowsCopied);  
```  
  
## <a name="remarks"></a><span data-ttu-id="7b367-105">Notes</span><span class="sxs-lookup"><span data-stu-id="7b367-105">Remarks</span></span>  
 <span data-ttu-id="7b367-106">La méthode **BCPExec** copie des données à partir d’un fichier utilisateur vers une table de base de données ou vice versa, selon la valeur du paramètre *eDirection* utilisé avec la méthode [IBCPSession::BCPInit](ibcpsession-bcpinit-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="7b367-106">The **BCPExec** method copies data from a user file to a database table or vice versa, depending on the value of the *eDirection* parameter used with the [IBCPSession::BCPInit](ibcpsession-bcpinit-ole-db.md) method.</span></span>  
  
 <span data-ttu-id="7b367-107">Avant d'appeler **BCPExec**, appelez la méthode **BCPInit** avec un nom de fichier utilisateur valide.</span><span class="sxs-lookup"><span data-stu-id="7b367-107">Before calling **BCPExec**, call the **BCPInit** method with a valid user file name.</span></span> <span data-ttu-id="7b367-108">L'échec de cette opération entraîne une erreur.</span><span class="sxs-lookup"><span data-stu-id="7b367-108">Failure to do so results in an error.</span></span> <span data-ttu-id="7b367-109">La seule exception est si une requête doit être utilisée pour une opération de copie en bloc sortante.</span><span class="sxs-lookup"><span data-stu-id="7b367-109">The only exception is if a query is to be used for a bulk copy out operation.</span></span> <span data-ttu-id="7b367-110">Dans ce cas, spécifiez NULL pour le nom de table dans la méthode **BCPInit** , puis spécifiez la requête à l'aide de l'option BCP_OPTION_HINTS.</span><span class="sxs-lookup"><span data-stu-id="7b367-110">In that case specify NULL for the table name in the **BCPInit** method and then specify the query using the BCP_OPTION_HINTS option.</span></span>  
  
 <span data-ttu-id="7b367-111">La méthode **BCPExec** est la seule méthode de copie en bloc qui est susceptible d'être en attente pendant une durée prolongée.</span><span class="sxs-lookup"><span data-stu-id="7b367-111">The **BCPExec** method is the only bulk copy method that is likely to be outstanding for any length of time.</span></span> <span data-ttu-id="7b367-112">Il s'agit par conséquent de la seule méthode de copie en bloc qui prend en charge le mode asynchrone.</span><span class="sxs-lookup"><span data-stu-id="7b367-112">It is therefore the only bulk copy method that supports asynchronous mode.</span></span> <span data-ttu-id="7b367-113">Pour utiliser le mode asynchrone, affectez à la propriété de session spécifique du fournisseur SSPROP_ASYNCH_BULKCOPY la valeur VARIANT_TRUE avant d’appeler la méthode **BCPExec** .</span><span class="sxs-lookup"><span data-stu-id="7b367-113">To use asynchronous mode, set the provider specific session property SSPROP_ASYNCH_BULKCOPY to VARIANT_TRUE before calling the **BCPExec** method.</span></span> <span data-ttu-id="7b367-114">Cette propriété est disponible dans le jeu de propriétés DBPROPSET_SQLSERVERSESSION.</span><span class="sxs-lookup"><span data-stu-id="7b367-114">This property is available in the DBPROPSET_SQLSERVERSESSION property set.</span></span> <span data-ttu-id="7b367-115">Pour tester l'achèvement, appelez la méthode **BCPExec** avec les mêmes paramètres.</span><span class="sxs-lookup"><span data-stu-id="7b367-115">To test for completion, call the **BCPExec** method with the same parameters.</span></span> <span data-ttu-id="7b367-116">Si la copie en bloc n'est pas encore terminée, la méthode **BCPExec** retourne DB_S_ASYNCHRONOUS.</span><span class="sxs-lookup"><span data-stu-id="7b367-116">If the bulk copy has not yet completed, the **BCPExec** method returns DB_S_ASYNCHRONOUS.</span></span> <span data-ttu-id="7b367-117">Elle retourne également dans l'argument *pRowsCopied* le nombre de lignes qui ont été envoyées ou reçues à partir du serveur.</span><span class="sxs-lookup"><span data-stu-id="7b367-117">It also returns in the *pRowsCopied* argument a status count of the number of rows that have been sent to or received from the server.</span></span> <span data-ttu-id="7b367-118">Les lignes envoyées au serveur sont validées uniquement une fois la fin du lot atteinte.</span><span class="sxs-lookup"><span data-stu-id="7b367-118">Rows sent to the server are not committed until the end of a batch has been reached.</span></span>  
  
## <a name="arguments"></a><span data-ttu-id="7b367-119">Arguments</span><span class="sxs-lookup"><span data-stu-id="7b367-119">Arguments</span></span>  
 <span data-ttu-id="7b367-120">*pRowsCopied*[out]</span><span class="sxs-lookup"><span data-stu-id="7b367-120">*pRowsCopied*[out]</span></span>  
 <span data-ttu-id="7b367-121">Pointeur vers une valeur DWORD.</span><span class="sxs-lookup"><span data-stu-id="7b367-121">A pointer to a DWORD.</span></span> <span data-ttu-id="7b367-122">La méthode **BCPExec** remplit la valeur DWORD avec le nombre de lignes copiées avec succès.</span><span class="sxs-lookup"><span data-stu-id="7b367-122">The **BCPExec** method fills the DWORD with the number of rows successfully copied.</span></span> <span data-ttu-id="7b367-123">Si l'argument *pRowsCopied* a la valeur NULL, il est ignoré par la méthode **BCPExec** .</span><span class="sxs-lookup"><span data-stu-id="7b367-123">If the *pRowsCopied* argument is set to NULL, it is ignored by the **BCPExec** method.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="7b367-124">Codet de retour</span><span class="sxs-lookup"><span data-stu-id="7b367-124">Return Code Values</span></span>  
 <span data-ttu-id="7b367-125">S_OK</span><span class="sxs-lookup"><span data-stu-id="7b367-125">S_OK</span></span>  
 <span data-ttu-id="7b367-126">S_OK</span><span class="sxs-lookup"><span data-stu-id="7b367-126">The method succeeded.</span></span>  
  
 <span data-ttu-id="7b367-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7b367-127">E_FAIL</span></span>  
 <span data-ttu-id="7b367-128">Une erreur spécifique au fournisseur s’est produite ; Pour plus d’informations, utilisez l’interface [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) .</span><span class="sxs-lookup"><span data-stu-id="7b367-128">A provider-specific error occurred; for detailed information, use the [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) interface.</span></span>  
  
 <span data-ttu-id="7b367-129">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="7b367-129">E_UNEXPECTED</span></span>  
 <span data-ttu-id="7b367-130">L'appel à la méthode était inattendu.</span><span class="sxs-lookup"><span data-stu-id="7b367-130">The call to the method was unexpected.</span></span> <span data-ttu-id="7b367-131">Par exemple, la méthode **BCPInit** n'a pas été appelée avant cette méthode.</span><span class="sxs-lookup"><span data-stu-id="7b367-131">For example, the **BCPInit** method was not called before calling this method.</span></span> <span data-ttu-id="7b367-132">Se produit également si l'opération a été abandonnée suite à l'utilisation de l'option BCP_OPTION_ABORT et que la méthode **BCPExec** a été appelée ensuite.</span><span class="sxs-lookup"><span data-stu-id="7b367-132">Also occurs if the operation has been aborted through using the BCP_OPTION_ABORT option, and the **BCPExec** method was called afterwards.</span></span>  
  
 <span data-ttu-id="7b367-133">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="7b367-133">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="7b367-134">Erreur de mémoire insuffisante.</span><span class="sxs-lookup"><span data-stu-id="7b367-134">Out-of-memory error.</span></span>  
  
 <span data-ttu-id="7b367-135">DB_S_ENDOFROWSET</span><span class="sxs-lookup"><span data-stu-id="7b367-135">DB_S_ENDOFROWSET</span></span>  
 <span data-ttu-id="7b367-136">L'opération de copie en bloc s'est terminée et tout le transfert de données a été effectué.</span><span class="sxs-lookup"><span data-stu-id="7b367-136">The bulk copy operation finished, and all the data transfer was completed.</span></span>  
  
 <span data-ttu-id="7b367-137">DB_S_ASYNCHRONOUS</span><span class="sxs-lookup"><span data-stu-id="7b367-137">DB_S_ASYNCHRONOUS</span></span>  
 <span data-ttu-id="7b367-138">Le lot actuel de lignes a été copié.</span><span class="sxs-lookup"><span data-stu-id="7b367-138">The current batch of rows has been copied.</span></span> <span data-ttu-id="7b367-139">Rappelez la méthode **BCPExec** pour transférer le lot suivant.</span><span class="sxs-lookup"><span data-stu-id="7b367-139">Call the **BCPExec** method again to transfer the next batch.</span></span>  
  
 <span data-ttu-id="7b367-140">DB_S_ERRORSOCCURRED</span><span class="sxs-lookup"><span data-stu-id="7b367-140">DB_S_ERRORSOCCURRED</span></span>  
 <span data-ttu-id="7b367-141">Des erreurs se sont produites pendant l'opération de copie en bloc et certaines lignes n'ont pas pu être copiées.</span><span class="sxs-lookup"><span data-stu-id="7b367-141">Errors occurred during the bulk copy operation, and some rows might not have been copied.</span></span> <span data-ttu-id="7b367-142">Le nombre d'erreurs est inférieur au nombre maximal d'erreurs autorisé.</span><span class="sxs-lookup"><span data-stu-id="7b367-142">The number of errors is still less than the maximum errors allowed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b367-143">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7b367-143">See Also</span></span>  
 <span data-ttu-id="7b367-144">[IBCPSession &#40;OLE DB&#41;](ibcpsession-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="7b367-144">[IBCPSession &#40;OLE DB&#41;](ibcpsession-ole-db.md) </span></span>  
 [<span data-ttu-id="7b367-145">Exécution d'opérations de copie en bloc</span><span class="sxs-lookup"><span data-stu-id="7b367-145">Performing Bulk Copy Operations</span></span>](../native-client/features/performing-bulk-copy-operations.md)  
  
  
