---
title: ISQLServerErrorInfo::GetErrorInfo (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- ISQLServerErrorInfo::GetErrorInfo (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- GetErrorInfo method
ms.assetid: 83265c9c-eaf9-41f0-9f73-b0ae0972f0d5
author: rothja
ms.author: jroth
ms.openlocfilehash: c3e325cd99276e04a178b89c19b233289edc09fa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702895"
---
# <a name="isqlservererrorinfogeterrorinfo-ole-db"></a><span data-ttu-id="3bea8-102">ISQLServerErrorInfo::GetErrorInfo (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="3bea8-102">ISQLServerErrorInfo::GetErrorInfo (OLE DB)</span></span>
  <span data-ttu-id="3bea8-103">Retourne un pointeur vers une [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] structure SSERRORINFO du fournisseur OLE DB Native Client contenant les détails de l' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] erreur.</span><span class="sxs-lookup"><span data-stu-id="3bea8-103">Returns a pointer to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider SSERRORINFO structure containing the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error details.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3bea8-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="3bea8-104">Syntax</span></span>  
  
```  
  
   HRESULT GetErrorInfo(  
SSERRORINFO**ppSSErrorInfo,  
OLECHAR**ppErrorStrings);  
```  
  
## <a name="arguments"></a><span data-ttu-id="3bea8-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="3bea8-105">Arguments</span></span>  
 <span data-ttu-id="3bea8-106">*ppSSErrorInfo*[out]</span><span class="sxs-lookup"><span data-stu-id="3bea8-106">*ppSSErrorInfo*[out]</span></span>  
 <span data-ttu-id="3bea8-107">Pointeur vers une structure SSERRORINFO.</span><span class="sxs-lookup"><span data-stu-id="3bea8-107">A pointer to a SSERRORINFO structure.</span></span> <span data-ttu-id="3bea8-108">Si la méthode échoue ou qu’il n’existe pas d’informations [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] associées à l’erreur, le fournisseur n’alloue pas de mémoire et vérifie que l’argument *ppSSErrorInfo* est un pointeur null en sortie.</span><span class="sxs-lookup"><span data-stu-id="3bea8-108">If the method fails or there is no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] information associated with the error, the provider does not allocate any memory, and ensures that the *ppSSErrorInfo* argument is a null pointer on output.</span></span>  
  
 <span data-ttu-id="3bea8-109">*ppErrorStrings*[out]</span><span class="sxs-lookup"><span data-stu-id="3bea8-109">*ppErrorStrings*[out]</span></span>  
 <span data-ttu-id="3bea8-110">Pointeur vers un pointeur de chaîne de caractère Unicode.</span><span class="sxs-lookup"><span data-stu-id="3bea8-110">A pointer to a Unicode character-string pointer.</span></span> <span data-ttu-id="3bea8-111">Si la méthode échoue ou qu’il n’existe pas d’informations [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] associées à l’erreur, le fournisseur n’alloue pas de mémoire et vérifie que l’argument *ppErrorStrings* est un pointeur null en sortie.</span><span class="sxs-lookup"><span data-stu-id="3bea8-111">If the method fails or there is no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] information associated with an error, the provider does not allocate any memory, and ensures that the *ppErrorStrings* argument is a null pointer on output.</span></span> <span data-ttu-id="3bea8-112">La libération de l’argument *ppErrorStrings* avec la méthode **IMalloc::Free** libère les trois membres de type chaîne individuels de la structure SSERRORINFO retournée, la mémoire étant allouée dans un bloc.</span><span class="sxs-lookup"><span data-stu-id="3bea8-112">Freeing the *ppErrorStrings* argument with the **IMalloc::Free** method frees the three individual string members of the returned SSERRORINFO structure, as the memory is allocated in a block.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="3bea8-113">Codet de retour</span><span class="sxs-lookup"><span data-stu-id="3bea8-113">Return Code Values</span></span>  
 <span data-ttu-id="3bea8-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="3bea8-114">S_OK</span></span>  
 <span data-ttu-id="3bea8-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="3bea8-115">The method succeeded.</span></span>  
  
 <span data-ttu-id="3bea8-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="3bea8-116">E_INVALIDARG</span></span>  
 <span data-ttu-id="3bea8-117">L'argument *ppSSErrorInfo* ou *ppErrorStrings* était NULL.</span><span class="sxs-lookup"><span data-stu-id="3bea8-117">Either the *ppSSErrorInfo* or the *ppErrorStrings* argument was NULL.</span></span>  
  
 <span data-ttu-id="3bea8-118">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="3bea8-118">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="3bea8-119">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client n’a pas pu allouer suffisamment de mémoire pour terminer la demande.</span><span class="sxs-lookup"><span data-stu-id="3bea8-119">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider could not allocate sufficient memory to complete the request.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3bea8-120">Notes</span><span class="sxs-lookup"><span data-stu-id="3bea8-120">Remarks</span></span>  
 <span data-ttu-id="3bea8-121">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client alloue de la mémoire pour les chaînes SSERRORINFO et OLECHAR retournées par le biais des pointeurs passés par le consommateur.</span><span class="sxs-lookup"><span data-stu-id="3bea8-121">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider allocates memory for the SSERRORINFO and OLECHAR strings returned through the pointers passed by the consumer.</span></span> <span data-ttu-id="3bea8-122">Le consommateur doit désallouer cette mémoire avec la méthode **IMalloc::Free** quand il n’est plus nécessaire d’accéder aux données d’erreur.</span><span class="sxs-lookup"><span data-stu-id="3bea8-122">The consumer must deallocate this memory by using the **IMalloc::Free** method when it no longer requires access to the error data.</span></span>  
  
 <span data-ttu-id="3bea8-123">La structure SSERRORINFO est définie comme suit :</span><span class="sxs-lookup"><span data-stu-id="3bea8-123">The SSERRORINFO structure is defined as follows:</span></span>  
  
```  
typedef struct tagSSErrorInfo  
   {  
   LPOLESTR pwszMessage;  
   LPOLESTR pwszServer;  
   LPOLESTR pwszProcedure;  
   LONG lNative;  
   BYTE bState;  
   BYTE bClass;  
   WORD wLineNumber;  
   }  
SSERRORINFO;  
```  
  
|<span data-ttu-id="3bea8-124">Membre</span><span class="sxs-lookup"><span data-stu-id="3bea8-124">Member</span></span>|<span data-ttu-id="3bea8-125">Description</span><span class="sxs-lookup"><span data-stu-id="3bea8-125">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="3bea8-126">*pwszMessage*</span><span class="sxs-lookup"><span data-stu-id="3bea8-126">*pwszMessage*</span></span>|<span data-ttu-id="3bea8-127">Message d'erreur de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3bea8-127">The error message from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="3bea8-128">Le message est retourné via la méthode **IErrorInfo::GetDescription**.</span><span class="sxs-lookup"><span data-stu-id="3bea8-128">The message is returned through the **IErrorInfo::GetDescription** method.</span></span>|  
|<span data-ttu-id="3bea8-129">*pwszServer*</span><span class="sxs-lookup"><span data-stu-id="3bea8-129">*pwszServer*</span></span>|<span data-ttu-id="3bea8-130">Nom de l'instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sur laquelle l'erreur s'est produite.</span><span class="sxs-lookup"><span data-stu-id="3bea8-130">The name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on which the error occurred.</span></span>|  
|<span data-ttu-id="3bea8-131">*pwszProcedure*</span><span class="sxs-lookup"><span data-stu-id="3bea8-131">*pwszProcedure*</span></span>|<span data-ttu-id="3bea8-132">Le nom de la procédure stockée qui génère l'erreur si l'erreur s'est produite dans une procédure stockée ; sinon, une chaîne vide.</span><span class="sxs-lookup"><span data-stu-id="3bea8-132">The name of the stored procedure generating the error if the error occurred in a stored procedure; otherwise, an empty string.</span></span>|  
|<span data-ttu-id="3bea8-133">*lNative*</span><span class="sxs-lookup"><span data-stu-id="3bea8-133">*lNative*</span></span>|<span data-ttu-id="3bea8-134">Numéro d'erreur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3bea8-134">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error number.</span></span> <span data-ttu-id="3bea8-135">Le numéro d’erreur est identique à celui retourné dans le paramètre *plNativeError* de la méthode **ISQLErrorInfo::GetSQLInfo**.</span><span class="sxs-lookup"><span data-stu-id="3bea8-135">The error number is identical to that returned in the *plNativeError* parameter of the **ISQLErrorInfo::GetSQLInfo** method.</span></span>|  
|<span data-ttu-id="3bea8-136">*bState*</span><span class="sxs-lookup"><span data-stu-id="3bea8-136">*bState*</span></span>|<span data-ttu-id="3bea8-137">État de l'erreur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3bea8-137">The state of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error.</span></span>|  
|<span data-ttu-id="3bea8-138">*bClass*</span><span class="sxs-lookup"><span data-stu-id="3bea8-138">*bClass*</span></span>|<span data-ttu-id="3bea8-139">Gravité de l'erreur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3bea8-139">The severity of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error.</span></span>|  
|<span data-ttu-id="3bea8-140">*wLineNumber*</span><span class="sxs-lookup"><span data-stu-id="3bea8-140">*wLineNumber*</span></span>|<span data-ttu-id="3bea8-141">Le cas échéant, la ligne d'une procédure stockée [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui a généré le message d'erreur.</span><span class="sxs-lookup"><span data-stu-id="3bea8-141">When applicable, the line of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedure that generated the error message.</span></span> <span data-ttu-id="3bea8-142">Si aucune procédure n'est impliquée, la valeur par défaut est 1.</span><span class="sxs-lookup"><span data-stu-id="3bea8-142">If no procedure is involved, the default value is 1.</span></span>|  
  
 <span data-ttu-id="3bea8-143">Pointeurs dans les adresses de type référence de la structure de la chaîne retournée dans l’argument *ppErrorStrings*.</span><span class="sxs-lookup"><span data-stu-id="3bea8-143">Pointers in the structure reference addresses in the string returned in the *ppErrorStrings* argument.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bea8-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3bea8-144">See Also</span></span>  
 <span data-ttu-id="3bea8-145">[&#41;&#40;de ISQLServerErrorInfo OLE DB](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="3bea8-145">[ISQLServerErrorInfo &#40;OLE DB&#41;](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) </span></span>  
 [<span data-ttu-id="3bea8-146">RAISERROR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3bea8-146">RAISERROR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/raiserror-transact-sql)  
  
  
