---
title: LocalDBStopInstance fonction) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBStopInstance
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: 4bd73187-0aac-4f03-ac54-2b78e41917e5
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 48b014e65e0a02a5f866e5301b12dae3cd255b95
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695615"
---
# <a name="localdbstopinstance-function"></a><span data-ttu-id="504ef-102">Fonction LocalDBStopInstance</span><span class="sxs-lookup"><span data-stu-id="504ef-102">LocalDBStopInstance Function</span></span>
  <span data-ttu-id="504ef-103">Arrête l'exécution de l'instance SQL Server Express LocalDB spécifiée.</span><span class="sxs-lookup"><span data-stu-id="504ef-103">Stops the specified SQL Server Express LocalDB instance from running.</span></span>  
  
 <span data-ttu-id="504ef-104">**Fichier d'en-tête :** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="504ef-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="504ef-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="504ef-105">Syntax</span></span>  
  
```  
HRESULT LocalDBStopInstance(  
           PCWSTR pInstanceName,  
           DWORD dwFlags,   
           ULONG ulTimeout   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="504ef-106">Paramètres</span><span class="sxs-lookup"><span data-stu-id="504ef-106">Parameters</span></span>  
 <span data-ttu-id="504ef-107">*pInstanceName*</span><span class="sxs-lookup"><span data-stu-id="504ef-107">*pInstanceName*</span></span>  
 <span data-ttu-id="504ef-108">[Entrée] Nom de l'instance de LocalDB à arrêter.</span><span class="sxs-lookup"><span data-stu-id="504ef-108">[Input] The name of the LocalDB instance to stop.</span></span>  
  
 <span data-ttu-id="504ef-109">*dwFlags*</span><span class="sxs-lookup"><span data-stu-id="504ef-109">*dwFlags*</span></span>  
 <span data-ttu-id="504ef-110">[Entrée] Valeur d'indicateur ou combinaison de valeurs d'indicateur indiquant la façon d'arrêter l'instance.</span><span class="sxs-lookup"><span data-stu-id="504ef-110">[Input] One or a combination of the flag values specifying the way to stop the instance.</span></span>  
  
 <span data-ttu-id="504ef-111">Indicateurs disponibles :</span><span class="sxs-lookup"><span data-stu-id="504ef-111">Available flags:</span></span>  
  
 <span data-ttu-id="504ef-112">LOCALDB_SHUTDOWN_KILL_PROCESS</span><span class="sxs-lookup"><span data-stu-id="504ef-112">LOCALDB_SHUTDOWN_KILL_PROCESS</span></span>  
 <span data-ttu-id="504ef-113">Arrêter immédiatement à l'aide de la commande du système d'exploitation Terminer le processus.</span><span class="sxs-lookup"><span data-stu-id="504ef-113">Shut down immediately using the kill process operating system command.</span></span>  
  
 <span data-ttu-id="504ef-114">LOCALDB_SHUTDOWN_WITH_NOWAIT</span><span class="sxs-lookup"><span data-stu-id="504ef-114">LOCALDB_SHUTDOWN_WITH_NOWAIT</span></span>  
 <span data-ttu-id="504ef-115">Arrêter à l'aide de l'option de commande Transact-SQL WITH NOWAIT.</span><span class="sxs-lookup"><span data-stu-id="504ef-115">Shut down using the WITH NOWAIT option Transact-SQL command.</span></span>  
  
 <span data-ttu-id="504ef-116">Si aucun des indicateurs n'est défini, l'instance de LocalDB sera arrêtée à l'aide de la commande Transact-SQL SHUTDOWN.</span><span class="sxs-lookup"><span data-stu-id="504ef-116">If none of the flags is set, the LocalDB instance will be shut down using the SHUTDOWN Transact-SQL command.</span></span> <span data-ttu-id="504ef-117">Si les deux indicateurs sont définis, l'indicateur LOCALDB_SHUTDOWN_KILL_PROCESS est prioritaire.</span><span class="sxs-lookup"><span data-stu-id="504ef-117">If both flags are set, the LOCALDB_SHUTDOWN_KILL_PROCESS flag takes precedence.</span></span>  
  
 <span data-ttu-id="504ef-118">*ulTimeout*</span><span class="sxs-lookup"><span data-stu-id="504ef-118">*ulTimeout*</span></span>  
 <span data-ttu-id="504ef-119">[Entrée] Durée d'attente en secondes pour l'exécution de cette opération.</span><span class="sxs-lookup"><span data-stu-id="504ef-119">[Input] The time in seconds to wait for this operation to complete.</span></span> <span data-ttu-id="504ef-120">Si cette valeur est 0, cette fonction retournera immédiatement sans attendre l'arrêt de l'instance de LocalDB.</span><span class="sxs-lookup"><span data-stu-id="504ef-120">If this value is 0, this function will return immediately without waiting for the LocalDB instance to stop.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="504ef-121">Retours</span><span class="sxs-lookup"><span data-stu-id="504ef-121">Returns</span></span>  
 <span data-ttu-id="504ef-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="504ef-122">S_OK</span></span>  
 <span data-ttu-id="504ef-123">La fonction a réussi.</span><span class="sxs-lookup"><span data-stu-id="504ef-123">The function succeeded.</span></span>  
  
 [<span data-ttu-id="504ef-124">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="504ef-124">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="504ef-125">SQL Server Express LocalDB n'est pas installé sur l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="504ef-125">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="504ef-126">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="504ef-126">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="504ef-127">Un ou plusieurs paramètres d'entrée spécifiés ne sont pas valides.</span><span class="sxs-lookup"><span data-stu-id="504ef-127">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="504ef-128">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span><span class="sxs-lookup"><span data-stu-id="504ef-128">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span></span>](../express-localdb-error-messages/localdb-error-invalid-instance-name.md)  
 <span data-ttu-id="504ef-129">Le nom d'instance spécifié n'est pas valide.</span><span class="sxs-lookup"><span data-stu-id="504ef-129">The specified instance name is invalid.</span></span>  
  
 [<span data-ttu-id="504ef-130">LOCALDB_ERROR_UNKNOWN_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="504ef-130">LOCALDB_ERROR_UNKNOWN_INSTANCE</span></span>](../express-localdb-error-messages/localdb-error-unknown-instance.md)  
 <span data-ttu-id="504ef-131">L'instance n'existe pas.</span><span class="sxs-lookup"><span data-stu-id="504ef-131">The instance does not exist.</span></span>  
  
 [<span data-ttu-id="504ef-132">LOCALDB_ERROR_WAIT_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="504ef-132">LOCALDB_ERROR_WAIT_TIMEOUT</span></span>](../express-localdb-error-messages/localdb-error-wait-timeout.md)  
 <span data-ttu-id="504ef-133">Un dépassement de délai s'est produit lors de la tentative d'acquisition des verrous de synchronisation.</span><span class="sxs-lookup"><span data-stu-id="504ef-133">A time-out occurred while trying to acquire the synchronization locks.</span></span>  
  
 [<span data-ttu-id="504ef-134">LOCALDB_ERROR_INSTANCE_STOP_FAILED</span><span class="sxs-lookup"><span data-stu-id="504ef-134">LOCALDB_ERROR_INSTANCE_STOP_FAILED</span></span>](../express-localdb-error-messages/localdb-error-instance-stop-failed.md)  
 <span data-ttu-id="504ef-135">L'opération d'arrêt ne s'est pas terminée dans le délai imparti.</span><span class="sxs-lookup"><span data-stu-id="504ef-135">The stop operation failed to complete within the given time.</span></span>  
  
 [<span data-ttu-id="504ef-136">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span><span class="sxs-lookup"><span data-stu-id="504ef-136">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span></span>](../express-localdb-error-messages/localdb-error-instance-folder-path-too-long.md)  
 <span data-ttu-id="504ef-137">Le chemin d'accès où l'instance doit être stockée est plus long que MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="504ef-137">The path where the instance should be stored is longer than MAX_PATH.</span></span>  
  
 [<span data-ttu-id="504ef-138">LOCALDB_ERROR_CANNOT_GET_USER_PROFILE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="504ef-138">LOCALDB_ERROR_CANNOT_GET_USER_PROFILE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-get-user-profile-folder.md)  
 <span data-ttu-id="504ef-139">Impossible de récupérer un dossier du profil utilisateur.</span><span class="sxs-lookup"><span data-stu-id="504ef-139">A user profile folder cannot be retrieved.</span></span>  
  
 [<span data-ttu-id="504ef-140">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="504ef-140">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-folder.md)  
 <span data-ttu-id="504ef-141">Un dossier d'instance n'est pas accessible.</span><span class="sxs-lookup"><span data-stu-id="504ef-141">An instance folder cannot be accessed.</span></span>  
  
 [<span data-ttu-id="504ef-142">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="504ef-142">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-registry.md)  
 <span data-ttu-id="504ef-143">Un Registre d'instance n'est pas accessible.</span><span class="sxs-lookup"><span data-stu-id="504ef-143">An instance registry cannot be accessed.</span></span>  
  
 [<span data-ttu-id="504ef-144">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span><span class="sxs-lookup"><span data-stu-id="504ef-144">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span></span>](../express-localdb-error-messages/localdb-error-instance-configuration-corrupt.md)  
 <span data-ttu-id="504ef-145">Une configuration d'instance est endommagée.</span><span class="sxs-lookup"><span data-stu-id="504ef-145">An instance configuration is corrupted.</span></span>  
  
 [<span data-ttu-id="504ef-146">LOCALDB_ERROR_CALLER_IS_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="504ef-146">LOCALDB_ERROR_CALLER_IS_NOT_OWNER</span></span>](../express-localdb-error-messages/localdb-error-caller-is-not-owner.md)  
 <span data-ttu-id="504ef-147">L'appelant de l'API n'est pas le propriétaire de l'instance de LocalDB.</span><span class="sxs-lookup"><span data-stu-id="504ef-147">API caller is not LocalDB instance owner.</span></span>  
  
 [<span data-ttu-id="504ef-148">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="504ef-148">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="504ef-149">Une erreur inattendue s’est produite.</span><span class="sxs-lookup"><span data-stu-id="504ef-149">An unexpected error occurred.</span></span> <span data-ttu-id="504ef-150">Pour plus d'informations, consultez le journal des événements.</span><span class="sxs-lookup"><span data-stu-id="504ef-150">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="504ef-151">Notes</span><span class="sxs-lookup"><span data-stu-id="504ef-151">Remarks</span></span>  
 <span data-ttu-id="504ef-152">Pour un exemple de code qui utilise l'API LocalDB, consultez [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="504ef-152">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="504ef-153">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="504ef-153">See Also</span></span>  
 [<span data-ttu-id="504ef-154">En-tête et informations de version SQL Server Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="504ef-154">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
