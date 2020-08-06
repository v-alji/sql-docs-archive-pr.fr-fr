---
title: LocalDBFormatMessage fonction) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBFormatMessage
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: 31b3152a-94cf-4f75-a31b-296d7dd16dbe
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: ece28f19e3488fae248bf26c3a54a018ba6efd0c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710623"
---
# <a name="localdbformatmessage-function"></a><span data-ttu-id="615d1-102">Fonction LocalDBFormatMessage</span><span class="sxs-lookup"><span data-stu-id="615d1-102">LocalDBFormatMessage Function</span></span>
  <span data-ttu-id="615d1-103">Retourne la description textuelle localisée pour l'erreur SQL Server Express LocalDB spécifiée.</span><span class="sxs-lookup"><span data-stu-id="615d1-103">Returns the localized textual description for the specified SQL Server Express LocalDB error.</span></span>  
  
 <span data-ttu-id="615d1-104">**Fichier d'en-tête :** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="615d1-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="615d1-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="615d1-105">Syntax</span></span>  
  
```  
HRESULT LocalDBFormatMessage(  
           HRESULT hrLocalDB,  
           DWORD dwFlags,   
           DWORD dwLanguageId,   
           LPWSTR wszMessage,   
           LPDWORD lpcchMessage   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="615d1-106">Paramètres</span><span class="sxs-lookup"><span data-stu-id="615d1-106">Parameters</span></span>  
 <span data-ttu-id="615d1-107">*hrLocalDB*</span><span class="sxs-lookup"><span data-stu-id="615d1-107">*hrLocalDB*</span></span>  
 <span data-ttu-id="615d1-108">[Entrée] Code d'erreur de LocalDB.</span><span class="sxs-lookup"><span data-stu-id="615d1-108">[Input] The LocalDB error code.</span></span>  
  
 <span data-ttu-id="615d1-109">*dwFlags*</span><span class="sxs-lookup"><span data-stu-id="615d1-109">*dwFlags*</span></span>  
 <span data-ttu-id="615d1-110">[Entrée] Indicateurs spécifiant le comportement de cette fonction.</span><span class="sxs-lookup"><span data-stu-id="615d1-110">[Input] The flags specifying the behavior of this function.</span></span>  
  
 <span data-ttu-id="615d1-111">Indicateurs disponibles :</span><span class="sxs-lookup"><span data-stu-id="615d1-111">Available flags:</span></span>  
  
 <span data-ttu-id="615d1-112">LOCALDB_TRUNCATE_ERR_MESSAGE</span><span class="sxs-lookup"><span data-stu-id="615d1-112">LOCALDB_TRUNCATE_ERR_MESSAGE</span></span>  
 <span data-ttu-id="615d1-113">Si la mémoire tampon d'entrée est trop courte, le message d'erreur sera tronqué pour s'adapter à la mémoire tampon.</span><span class="sxs-lookup"><span data-stu-id="615d1-113">If the input buffer is too short, the error message will be truncated to fit the buffer.</span></span>  
  
 <span data-ttu-id="615d1-114">*dwLanguageId*</span><span class="sxs-lookup"><span data-stu-id="615d1-114">*dwLanguageId*</span></span>  
 <span data-ttu-id="615d1-115">[Entrée] Langue souhaitée (LANGID) ou 0, auquel cas l'ordre du langage Win32 FormatMessage est utilisé.</span><span class="sxs-lookup"><span data-stu-id="615d1-115">[Input] The language desired (LANGID) or 0, in which case the Win32 FormatMessage language order is used.</span></span>  
  
 <span data-ttu-id="615d1-116">*wszMessage*</span><span class="sxs-lookup"><span data-stu-id="615d1-116">*wszMessage*</span></span>  
 <span data-ttu-id="615d1-117">[Sortie] Mémoire tampon pour stocker le message d'erreur de LocalDB.</span><span class="sxs-lookup"><span data-stu-id="615d1-117">[Output] The buffer to store the LocalDB error message.</span></span>  
  
 <span data-ttu-id="615d1-118">*lpcchMessage*</span><span class="sxs-lookup"><span data-stu-id="615d1-118">*lpcchMessage*</span></span>  
 <span data-ttu-id="615d1-119">[Entrée/sortie] En entrée contient la taille de la mémoire tampon de *wszMessage* en caractères.</span><span class="sxs-lookup"><span data-stu-id="615d1-119">[Input/Output] On input contains the size of the *wszMessage* buffer in characters.</span></span> <span data-ttu-id="615d1-120">En sortie, si la taille de la mémoire tampon donnée est trop petite, contient la taille de la mémoire tampon requise en caractères, y compris les zéros de fin.</span><span class="sxs-lookup"><span data-stu-id="615d1-120">On output, if the given buffer size is too small, contains the buffer size required in characters, including any trailing nulls.</span></span> <span data-ttu-id="615d1-121">Si la fonction réussit, contient le nombre de caractères du message, à l'exception des zéros de fin.</span><span class="sxs-lookup"><span data-stu-id="615d1-121">If the function succeeds, contains the number of characters in the message, excluding any trailing nulls.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="615d1-122">Retours</span><span class="sxs-lookup"><span data-stu-id="615d1-122">Returns</span></span>  
 <span data-ttu-id="615d1-123">S_OK</span><span class="sxs-lookup"><span data-stu-id="615d1-123">S_OK</span></span>  
 <span data-ttu-id="615d1-124">La fonction a réussi.</span><span class="sxs-lookup"><span data-stu-id="615d1-124">The function succeeded.</span></span>  
  
 [<span data-ttu-id="615d1-125">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="615d1-125">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="615d1-126">SQL Server Express LocalDB n'est pas installé sur l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="615d1-126">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="615d1-127">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="615d1-127">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="615d1-128">Un ou plusieurs paramètres d'entrée spécifiés ne sont pas valides.</span><span class="sxs-lookup"><span data-stu-id="615d1-128">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="615d1-129">LOCALDB_ERROR_UNKNOWN_ERROR_CODE</span><span class="sxs-lookup"><span data-stu-id="615d1-129">LOCALDB_ERROR_UNKNOWN_ERROR_CODE</span></span>](../express-localdb-error-messages/localdb-error-unknown-error-code.md)  
 <span data-ttu-id="615d1-130">Le message demandé n'existe pas.</span><span class="sxs-lookup"><span data-stu-id="615d1-130">The requested message does not exist.</span></span>  
  
 [<span data-ttu-id="615d1-131">LOCALDB_ERROR_UNKNOWN_LANGUAGE_ID</span><span class="sxs-lookup"><span data-stu-id="615d1-131">LOCALDB_ERROR_UNKNOWN_LANGUAGE_ID</span></span>](../express-localdb-error-messages/localdb-error-unknown-language-id.md)  
 <span data-ttu-id="615d1-132">Le message n'est pas disponible dans la langue demandée.</span><span class="sxs-lookup"><span data-stu-id="615d1-132">The message is not available in the requested language.</span></span>  
  
 [<span data-ttu-id="615d1-133">LOCALDB_ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="615d1-133">LOCALDB_ERROR_INSUFFICIENT_BUFFER</span></span>](../express-localdb-error-messages/localdb-error-insufficient-buffer.md)  
 <span data-ttu-id="615d1-134">Le tampon d'entrée *wszMessage* est trop court, et la troncation n'est pas demandée.</span><span class="sxs-lookup"><span data-stu-id="615d1-134">The input buffer *wszMessage* is too short, and truncation is not requested.</span></span>  
  
 [<span data-ttu-id="615d1-135">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="615d1-135">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="615d1-136">Une erreur inattendue s’est produite.</span><span class="sxs-lookup"><span data-stu-id="615d1-136">An unexpected error occurred.</span></span> <span data-ttu-id="615d1-137">Pour plus d'informations, consultez le journal des événements.</span><span class="sxs-lookup"><span data-stu-id="615d1-137">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="615d1-138">Notes</span><span class="sxs-lookup"><span data-stu-id="615d1-138">Remarks</span></span>  
 <span data-ttu-id="615d1-139">Pour un exemple de code qui utilise l'API LocalDB, consultez [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="615d1-139">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="615d1-140">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="615d1-140">See Also</span></span>  
 [<span data-ttu-id="615d1-141">En-tête et informations de version SQL Server Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="615d1-141">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
