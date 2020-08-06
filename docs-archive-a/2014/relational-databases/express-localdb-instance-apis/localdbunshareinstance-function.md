---
title: Localdbunshareinstance, fonction) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBUnshareInstance
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: 54012ccb-eded-43f7-8ea5-da5ce79224c6
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 77ebf8cad9d410b047fccede4360ca0041637986
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601476"
---
# <a name="localdbunshareinstance-function"></a><span data-ttu-id="08396-102">LocalDBUnshareInstance, fonction</span><span class="sxs-lookup"><span data-stu-id="08396-102">LocalDBUnshareInstance Function</span></span>
  <span data-ttu-id="08396-103">Arrête le partage de l'instance de base de données locale SQL Server Express spécifiée.</span><span class="sxs-lookup"><span data-stu-id="08396-103">Stops the sharing of the specified SQL Server Express LocalDB instance.</span></span>  
  
 <span data-ttu-id="08396-104">**Fichier d'en-tête :** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="08396-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08396-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="08396-105">Syntax</span></span>  
  
```  
HRESULT LocalDBUnShareInstance(  
           PCWSTR pInstanceSharedName,   
           DWORD dwFlags   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08396-106">Paramètres</span><span class="sxs-lookup"><span data-stu-id="08396-106">Parameters</span></span>  
 <span data-ttu-id="08396-107">*pInstanceSharedName*</span><span class="sxs-lookup"><span data-stu-id="08396-107">*pInstanceSharedName*</span></span>  
 <span data-ttu-id="08396-108">[Entrée] Nom partagé de l'instance de base de données locale dont il faut annuler le partage.</span><span class="sxs-lookup"><span data-stu-id="08396-108">[Input] The shared name for the LocalDB instance to unshare.</span></span>  
  
 <span data-ttu-id="08396-109">*dwFlags*</span><span class="sxs-lookup"><span data-stu-id="08396-109">*dwFlags*</span></span>  
 <span data-ttu-id="08396-110">[Entrée] Réservé à un usage ultérieur.</span><span class="sxs-lookup"><span data-stu-id="08396-110">[Input] Reserved for future use.</span></span> <span data-ttu-id="08396-111">Actuellement doit avoir la valeur 0.</span><span class="sxs-lookup"><span data-stu-id="08396-111">Currently should be set to 0.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="08396-112">Retours</span><span class="sxs-lookup"><span data-stu-id="08396-112">Returns</span></span>  
 <span data-ttu-id="08396-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="08396-113">S_OK</span></span>  
 <span data-ttu-id="08396-114">La fonction a réussi.</span><span class="sxs-lookup"><span data-stu-id="08396-114">The function succeeded.</span></span>  
  
 [<span data-ttu-id="08396-115">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="08396-115">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="08396-116">SQL Server Express LocalDB n'est pas installé sur l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="08396-116">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="08396-117">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="08396-117">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="08396-118">Un ou plusieurs paramètres d'entrée spécifiés ne sont pas valides.</span><span class="sxs-lookup"><span data-stu-id="08396-118">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="08396-119">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span><span class="sxs-lookup"><span data-stu-id="08396-119">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span></span>](../express-localdb-error-messages/localdb-error-invalid-instance-name.md)  
 <span data-ttu-id="08396-120">Le nom d'instance spécifié n'est pas valide.</span><span class="sxs-lookup"><span data-stu-id="08396-120">The specified instance name is invalid.</span></span>  
  
 [<span data-ttu-id="08396-121">LOCALDB_ERROR_UNKNOWN_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="08396-121">LOCALDB_ERROR_UNKNOWN_INSTANCE</span></span>](../express-localdb-error-messages/localdb-error-unknown-instance.md)  
 <span data-ttu-id="08396-122">L'instance spécifiée n'existe pas.</span><span class="sxs-lookup"><span data-stu-id="08396-122">The specified instance does not exist.</span></span>  
  
 [<span data-ttu-id="08396-123">LOCALDB_ERROR_ADMIN_RIGHTS_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="08396-123">LOCALDB_ERROR_ADMIN_RIGHTS_REQUIRED</span></span>](../express-localdb-error-messages/localdb-error-admin-rights-required.md)  
 <span data-ttu-id="08396-124">Des privilèges d'administrateur sont requis pour effectuer cette opération.</span><span class="sxs-lookup"><span data-stu-id="08396-124">Administrator privileges are required in order to execute this operation.</span></span>  
  
 [<span data-ttu-id="08396-125">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="08396-125">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="08396-126">Une erreur inattendue s’est produite.</span><span class="sxs-lookup"><span data-stu-id="08396-126">An unexpected error occurred.</span></span> <span data-ttu-id="08396-127">Pour plus d'informations, consultez le journal des événements.</span><span class="sxs-lookup"><span data-stu-id="08396-127">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="08396-128">Notes</span><span class="sxs-lookup"><span data-stu-id="08396-128">Remarks</span></span>  
 <span data-ttu-id="08396-129">Pour un exemple de code qui utilise l'API LocalDB, consultez [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="08396-129">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08396-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="08396-130">See Also</span></span>  
 [<span data-ttu-id="08396-131">En-tête et informations de version SQL Server Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="08396-131">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
