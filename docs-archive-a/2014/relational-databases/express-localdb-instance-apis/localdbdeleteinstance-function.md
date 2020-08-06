---
title: LocalDBDeleteInstance fonction) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBDeleteInstance
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: 37cb2a7e-672a-4223-b6f3-a94d7b8d58cd
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 8d4c873e045c5effed476ca9d147270d159ec3b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612359"
---
# <a name="localdbdeleteinstance-function"></a><span data-ttu-id="ee302-102">Fonction LocalDBDeleteInstance</span><span class="sxs-lookup"><span data-stu-id="ee302-102">LocalDBDeleteInstance Function</span></span>
  <span data-ttu-id="ee302-103">Supprime l'instance SQL Server Express LocalDB spécifiée.</span><span class="sxs-lookup"><span data-stu-id="ee302-103">Removes the specified SQL Server Express LocalDB instance.</span></span>  
  
 <span data-ttu-id="ee302-104">**Fichier d'en-tête :** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="ee302-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee302-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="ee302-105">Syntax</span></span>  
  
```  
HRESULT LocalDBDeleteInstance(  
           PCWSTR pInstanceName,  
           DWORD dwFlags   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ee302-106">Paramètres</span><span class="sxs-lookup"><span data-stu-id="ee302-106">Parameters</span></span>  
 <span data-ttu-id="ee302-107">*pInstanceName*</span><span class="sxs-lookup"><span data-stu-id="ee302-107">*pInstanceName*</span></span>  
 <span data-ttu-id="ee302-108">[Entrée] Nom de l'instance de LocalDB à supprimer.</span><span class="sxs-lookup"><span data-stu-id="ee302-108">[Input] The name of the LocalDB instance to remove.</span></span>  
  
 <span data-ttu-id="ee302-109">*dwFlags*</span><span class="sxs-lookup"><span data-stu-id="ee302-109">*dwFlags*</span></span>  
 <span data-ttu-id="ee302-110">[Entrée] Réservé à un usage ultérieur.</span><span class="sxs-lookup"><span data-stu-id="ee302-110">[Input] Reserved for future use.</span></span> <span data-ttu-id="ee302-111">Actuellement doit avoir la valeur 0.</span><span class="sxs-lookup"><span data-stu-id="ee302-111">Currently should be set to 0.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="ee302-112">Retours</span><span class="sxs-lookup"><span data-stu-id="ee302-112">Returns</span></span>  
 <span data-ttu-id="ee302-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="ee302-113">S_OK</span></span>  
 <span data-ttu-id="ee302-114">La fonction a réussi.</span><span class="sxs-lookup"><span data-stu-id="ee302-114">The function succeeded.</span></span>  
  
 [<span data-ttu-id="ee302-115">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="ee302-115">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="ee302-116">SQL Server Express LocalDB n'est pas installé sur l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="ee302-116">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="ee302-117">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="ee302-117">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="ee302-118">Un ou plusieurs paramètres d'entrée spécifiés ne sont pas valides.</span><span class="sxs-lookup"><span data-stu-id="ee302-118">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="ee302-119">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span><span class="sxs-lookup"><span data-stu-id="ee302-119">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span></span>](../express-localdb-error-messages/localdb-error-invalid-instance-name.md)  
 <span data-ttu-id="ee302-120">Le nom d'instance spécifié n'est pas valide.</span><span class="sxs-lookup"><span data-stu-id="ee302-120">The specified instance name is invalid.</span></span>  
  
 [<span data-ttu-id="ee302-121">LOCALDB_ERROR_UNKNOWN_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="ee302-121">LOCALDB_ERROR_UNKNOWN_INSTANCE</span></span>](../express-localdb-error-messages/localdb-error-unknown-instance.md)  
 <span data-ttu-id="ee302-122">L'instance spécifiée n'existe pas.</span><span class="sxs-lookup"><span data-stu-id="ee302-122">The specified instance does not exist.</span></span>  
  
 [<span data-ttu-id="ee302-123">LOCALDB_ERROR_INSTANCE_BUSY</span><span class="sxs-lookup"><span data-stu-id="ee302-123">LOCALDB_ERROR_INSTANCE_BUSY</span></span>](../express-localdb-error-messages/localdb-error-instance-busy.md)  
 <span data-ttu-id="ee302-124">L'instance spécifiée est en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="ee302-124">The specified instance is running.</span></span>  
  
 [<span data-ttu-id="ee302-125">LOCALDB_ERROR_WAIT_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ee302-125">LOCALDB_ERROR_WAIT_TIMEOUT</span></span>](../express-localdb-error-messages/localdb-error-wait-timeout.md)  
 <span data-ttu-id="ee302-126">Un dépassement de délai s'est produit lors de la tentative d'acquisition des verrous de synchronisation.</span><span class="sxs-lookup"><span data-stu-id="ee302-126">A time-out occurred while trying to acquire synchronization locks.</span></span>  
  
 [<span data-ttu-id="ee302-127">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span><span class="sxs-lookup"><span data-stu-id="ee302-127">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span></span>](../express-localdb-error-messages/localdb-error-instance-folder-path-too-long.md)  
 <span data-ttu-id="ee302-128">Le chemin d'accès où l'instance doit être stockée est plus long que MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="ee302-128">The path where the instance should be stored is longer than MAX_PATH.</span></span>  
  
 [<span data-ttu-id="ee302-129">LOCALDB_ERROR_CANNOT_GET_USER_PROFILE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="ee302-129">LOCALDB_ERROR_CANNOT_GET_USER_PROFILE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-get-user-profile-folder.md)  
 <span data-ttu-id="ee302-130">Impossible de récupérer un dossier du profil utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ee302-130">A user profile folder cannot be retrieved.</span></span>  
  
 [<span data-ttu-id="ee302-131">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="ee302-131">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-folder.md)  
 <span data-ttu-id="ee302-132">Un dossier d'instance n'est pas accessible.</span><span class="sxs-lookup"><span data-stu-id="ee302-132">An instance folder cannot be accessed.</span></span>  
  
 [<span data-ttu-id="ee302-133">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="ee302-133">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-registry.md)  
 <span data-ttu-id="ee302-134">Un Registre d'instance n'est pas accessible.</span><span class="sxs-lookup"><span data-stu-id="ee302-134">An instance registry cannot be accessed.</span></span>  
  
 [<span data-ttu-id="ee302-135">LOCALDB_ERROR_CANNOT_MODIFY_INSTANCE_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="ee302-135">LOCALDB_ERROR_CANNOT_MODIFY_INSTANCE_REGISTRY</span></span>](../express-localdb-error-messages/localdb-error-cannot-modify-instance-registry.md)  
 <span data-ttu-id="ee302-136">Impossible de modifier un Registre d'instance.</span><span class="sxs-lookup"><span data-stu-id="ee302-136">An instance registry cannot be modified.</span></span>  
  
 [<span data-ttu-id="ee302-137">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span><span class="sxs-lookup"><span data-stu-id="ee302-137">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span></span>](../express-localdb-error-messages/localdb-error-instance-configuration-corrupt.md)  
 <span data-ttu-id="ee302-138">Une configuration d'instance est endommagée.</span><span class="sxs-lookup"><span data-stu-id="ee302-138">An instance configuration is corrupted.</span></span>  
  
 [<span data-ttu-id="ee302-139">LOCALDB_ERROR_CALLER_IS_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ee302-139">LOCALDB_ERROR_CALLER_IS_NOT_OWNER</span></span>](../express-localdb-error-messages/localdb-error-caller-is-not-owner.md)  
 <span data-ttu-id="ee302-140">L'appelant de l'API n'est pas le propriétaire de l'instance de base de données locale.</span><span class="sxs-lookup"><span data-stu-id="ee302-140">API caller is not Local Database instance owner.</span></span>  
  
 [<span data-ttu-id="ee302-141">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="ee302-141">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="ee302-142">Une erreur inattendue s’est produite.</span><span class="sxs-lookup"><span data-stu-id="ee302-142">An unexpected error occurred.</span></span> <span data-ttu-id="ee302-143">Pour plus d'informations, consultez le journal des événements.</span><span class="sxs-lookup"><span data-stu-id="ee302-143">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ee302-144">Notes</span><span class="sxs-lookup"><span data-stu-id="ee302-144">Remarks</span></span>  
 <span data-ttu-id="ee302-145">Pour un exemple de code qui utilise l'API LocalDB, consultez [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="ee302-145">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee302-146">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ee302-146">See Also</span></span>  
 [<span data-ttu-id="ee302-147">En-tête et informations de version SQL Server Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="ee302-147">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
