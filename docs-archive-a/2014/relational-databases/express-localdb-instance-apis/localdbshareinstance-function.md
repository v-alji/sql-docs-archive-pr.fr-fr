---
title: LocalDBShareInstance fonction) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBShareInstance
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: 21eb3b9a-7d32-455b-89bb-f624198cd202
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 238bff0b3512ceb03ead186dc001165274bd4e30
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604450"
---
# <a name="localdbshareinstance-function"></a><span data-ttu-id="07c9c-102">Fonction LocalDBShareInstance</span><span class="sxs-lookup"><span data-stu-id="07c9c-102">LocalDBShareInstance Function</span></span>
  <span data-ttu-id="07c9c-103">Partage l'instance de base de données locale SQL Server Express spécifiée avec d'autres utilisateurs de l'ordinateur, en utilisant le nom partagé spécifié.</span><span class="sxs-lookup"><span data-stu-id="07c9c-103">Shares the specified SQL Server Express LocalDB instance with other users of the computer, using the specified shared name.</span></span>  
  
 <span data-ttu-id="07c9c-104">**Fichier d'en-tête :** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="07c9c-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07c9c-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="07c9c-105">Syntax</span></span>  
  
```  
HRESULT LocalDBShareInstance(  
           PSID pOwnerSID,  
           PCWSTR pInstancePrivateName,  
           PCWSTR pInstanceSharedName,   
           DWORD dwFlags   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="07c9c-106">Paramètres</span><span class="sxs-lookup"><span data-stu-id="07c9c-106">Parameters</span></span>  
 <span data-ttu-id="07c9c-107">*pOwnerSID*</span><span class="sxs-lookup"><span data-stu-id="07c9c-107">*pOwnerSID*</span></span>  
 <span data-ttu-id="07c9c-108">[Entrée] SID du propriétaire de l'instance.</span><span class="sxs-lookup"><span data-stu-id="07c9c-108">[Input] The SID of the instance owner.</span></span>  
  
 <span data-ttu-id="07c9c-109">*pInstancePrivateName*</span><span class="sxs-lookup"><span data-stu-id="07c9c-109">*pInstancePrivateName*</span></span>  
 <span data-ttu-id="07c9c-110">[Entrée] Nom privé de l'instance de base de données locale à partager.</span><span class="sxs-lookup"><span data-stu-id="07c9c-110">[Input] The private name for the LocalDB instance to share.</span></span>  
  
 <span data-ttu-id="07c9c-111">*pInstanceSharedName*</span><span class="sxs-lookup"><span data-stu-id="07c9c-111">*pInstanceSharedName*</span></span>  
 <span data-ttu-id="07c9c-112">[Entrée] Nom partagé de l'instance de base de données locale à partager.</span><span class="sxs-lookup"><span data-stu-id="07c9c-112">[Input] The shared name for the LocalDB instance to share.</span></span>  
  
 <span data-ttu-id="07c9c-113">*dwFlags*</span><span class="sxs-lookup"><span data-stu-id="07c9c-113">*dwFlags*</span></span>  
 <span data-ttu-id="07c9c-114">[Entrée] Réservé à un usage ultérieur.</span><span class="sxs-lookup"><span data-stu-id="07c9c-114">[Input] Reserved for future use.</span></span> <span data-ttu-id="07c9c-115">Actuellement doit avoir la valeur 0.</span><span class="sxs-lookup"><span data-stu-id="07c9c-115">Currently should be set to 0.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="07c9c-116">Retours</span><span class="sxs-lookup"><span data-stu-id="07c9c-116">Returns</span></span>  
 <span data-ttu-id="07c9c-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="07c9c-117">S_OK</span></span>  
 <span data-ttu-id="07c9c-118">La fonction a réussi.</span><span class="sxs-lookup"><span data-stu-id="07c9c-118">The function succeeded.</span></span>  
  
 [<span data-ttu-id="07c9c-119">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="07c9c-119">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="07c9c-120">SQL Server Express LocalDB n'est pas installé sur l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="07c9c-120">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="07c9c-121">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="07c9c-121">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="07c9c-122">Un ou plusieurs paramètres d'entrée spécifiés ne sont pas valides.</span><span class="sxs-lookup"><span data-stu-id="07c9c-122">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="07c9c-123">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span><span class="sxs-lookup"><span data-stu-id="07c9c-123">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span></span>](../express-localdb-error-messages/localdb-error-invalid-instance-name.md)  
 <span data-ttu-id="07c9c-124">Le nom d'instance spécifié n'est pas valide.</span><span class="sxs-lookup"><span data-stu-id="07c9c-124">The specified instance name is invalid.</span></span>  
  
 [<span data-ttu-id="07c9c-125">LOCALDB_ERROR_UNKNOWN_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="07c9c-125">LOCALDB_ERROR_UNKNOWN_INSTANCE</span></span>](../express-localdb-error-messages/localdb-error-unknown-instance.md)  
 <span data-ttu-id="07c9c-126">L'instance spécifiée n'existe pas.</span><span class="sxs-lookup"><span data-stu-id="07c9c-126">The specified instance does not exist.</span></span>  
  
 [<span data-ttu-id="07c9c-127">LOCALDB_ERROR_ADMIN_RIGHTS_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="07c9c-127">LOCALDB_ERROR_ADMIN_RIGHTS_REQUIRED</span></span>](../express-localdb-error-messages/localdb-error-admin-rights-required.md)  
 <span data-ttu-id="07c9c-128">Des privilèges d'administrateur sont requis pour effectuer cette opération.</span><span class="sxs-lookup"><span data-stu-id="07c9c-128">Administrator privileges are required in order to execute this operation.</span></span>  
  
 [<span data-ttu-id="07c9c-129">LOCALDB_ERROR_SHARED_NAME_TAKEN</span><span class="sxs-lookup"><span data-stu-id="07c9c-129">LOCALDB_ERROR_SHARED_NAME_TAKEN</span></span>](../express-localdb-error-messages/localdb-error-shared-name-taken.md)  
 <span data-ttu-id="07c9c-130">Le nom partagé spécifié est déjà utilisé.</span><span class="sxs-lookup"><span data-stu-id="07c9c-130">The specified shared name is already taken.</span></span>  
  
 [<span data-ttu-id="07c9c-131">LOCALDB_ERROR_INSTANCE_ALREADY_SHARED</span><span class="sxs-lookup"><span data-stu-id="07c9c-131">LOCALDB_ERROR_INSTANCE_ALREADY_SHARED</span></span>](../express-localdb-error-messages/localdb-error-instance-already-shared.md)  
 <span data-ttu-id="07c9c-132">L'instance spécifiée est déjà partagée.</span><span class="sxs-lookup"><span data-stu-id="07c9c-132">The specified instance is already shared.</span></span>  
  
 [<span data-ttu-id="07c9c-133">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="07c9c-133">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="07c9c-134">Une erreur inattendue s’est produite.</span><span class="sxs-lookup"><span data-stu-id="07c9c-134">An unexpected error occurred.</span></span> <span data-ttu-id="07c9c-135">Pour plus d'informations, consultez le journal des événements.</span><span class="sxs-lookup"><span data-stu-id="07c9c-135">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="07c9c-136">Notes</span><span class="sxs-lookup"><span data-stu-id="07c9c-136">Remarks</span></span>  
 <span data-ttu-id="07c9c-137">Pour un exemple de code qui utilise l'API LocalDB, consultez [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="07c9c-137">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07c9c-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="07c9c-138">See Also</span></span>  
 [<span data-ttu-id="07c9c-139">En-tête et informations de version SQL Server Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="07c9c-139">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
