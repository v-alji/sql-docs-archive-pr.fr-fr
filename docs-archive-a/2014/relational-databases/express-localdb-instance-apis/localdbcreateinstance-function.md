---
title: LocalDBCreateInstance fonction) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBCreateInstance
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: 3eebb485-8a53-4a79-82a9-57b8de9f8e84
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: ff822c552176ad8c083a1c8ea6c0f2430f72972f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612364"
---
# <a name="localdbcreateinstance-function"></a><span data-ttu-id="eef77-102">Fonction LocalDBCreateInstance</span><span class="sxs-lookup"><span data-stu-id="eef77-102">LocalDBCreateInstance Function</span></span>
  <span data-ttu-id="eef77-103">Crée une instance SQL Server Express LocalDB.</span><span class="sxs-lookup"><span data-stu-id="eef77-103">Creates a new SQL Server Express LocalDB instance.</span></span>  
  
 <span data-ttu-id="eef77-104">**Fichier d'en-tête :** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="eef77-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eef77-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="eef77-105">Syntax</span></span>  
  
```  
HRESULT LocalDBCreateInstance(  
           PCWSTR wszVersion,  
           PCWSTR pInstanceName,   
           DWORD dwFlags   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eef77-106">Paramètres</span><span class="sxs-lookup"><span data-stu-id="eef77-106">Parameters</span></span>  
 <span data-ttu-id="eef77-107">*wszVersion*</span><span class="sxs-lookup"><span data-stu-id="eef77-107">*wszVersion*</span></span>  
 <span data-ttu-id="eef77-108">[Entrée] Version de LocalDB, par exemple 11.0 ou 11.0.1094.2.</span><span class="sxs-lookup"><span data-stu-id="eef77-108">[Input] The LocalDB version, for example 11.0 or 11.0.1094.2.</span></span>  
  
 <span data-ttu-id="eef77-109">*pInstanceName*</span><span class="sxs-lookup"><span data-stu-id="eef77-109">*pInstanceName*</span></span>  
 <span data-ttu-id="eef77-110">[Entrée] Nom de l'instance de LocalDB à créer.</span><span class="sxs-lookup"><span data-stu-id="eef77-110">[Input] The name for the LocalDB instance to create.</span></span>  
  
 <span data-ttu-id="eef77-111">*dwFlags*</span><span class="sxs-lookup"><span data-stu-id="eef77-111">*dwFlags*</span></span>  
 <span data-ttu-id="eef77-112">[Entrée] Réservé à un usage ultérieur.</span><span class="sxs-lookup"><span data-stu-id="eef77-112">[Input] Reserved for future use.</span></span> <span data-ttu-id="eef77-113">Actuellement doit avoir la valeur 0.</span><span class="sxs-lookup"><span data-stu-id="eef77-113">Currently should be set to 0.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="eef77-114">Retours</span><span class="sxs-lookup"><span data-stu-id="eef77-114">Returns</span></span>  
 <span data-ttu-id="eef77-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="eef77-115">S_OK</span></span>  
 <span data-ttu-id="eef77-116">La fonction a réussi.</span><span class="sxs-lookup"><span data-stu-id="eef77-116">The function succeeded.</span></span>  
  
 [<span data-ttu-id="eef77-117">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="eef77-117">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="eef77-118">SQL Server Express LocalDB n'est pas installé sur l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="eef77-118">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="eef77-119">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="eef77-119">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="eef77-120">Un ou plusieurs paramètres d'entrée spécifiés ne sont pas valides.</span><span class="sxs-lookup"><span data-stu-id="eef77-120">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="eef77-121">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span><span class="sxs-lookup"><span data-stu-id="eef77-121">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span></span>](../express-localdb-error-messages/localdb-error-invalid-instance-name.md)  
 <span data-ttu-id="eef77-122">Le nom d'instance spécifié n'est pas valide.</span><span class="sxs-lookup"><span data-stu-id="eef77-122">The specified instance name is invalid.</span></span>  
  
 [<span data-ttu-id="eef77-123">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span><span class="sxs-lookup"><span data-stu-id="eef77-123">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span></span>](../express-localdb-error-messages/localdb-error-instance-folder-path-too-long.md)  
 <span data-ttu-id="eef77-124">Le chemin d'accès où l'instance doit être stockée est plus long que MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="eef77-124">The path where the instance should be stored is longer than MAX_PATH.</span></span>  
  
 [<span data-ttu-id="eef77-125">LOCALDB_ERROR_INSTANCE_EXISTS_WITH_LOWER_VERSION</span><span class="sxs-lookup"><span data-stu-id="eef77-125">LOCALDB_ERROR_INSTANCE_EXISTS_WITH_LOWER_VERSION</span></span>](../express-localdb-error-messages/localdb-error-instance-exists-with-lower-version.md)  
 <span data-ttu-id="eef77-126">L'instance spécifiée existe déjà mais sa version est inférieure à celle demandée.</span><span class="sxs-lookup"><span data-stu-id="eef77-126">The specified instance already exists but its version is lower than requested.</span></span>  
  
 [<span data-ttu-id="eef77-127">LOCALDB_ERROR_UNKNOWN_VERSION</span><span class="sxs-lookup"><span data-stu-id="eef77-127">LOCALDB_ERROR_UNKNOWN_VERSION</span></span>](../express-localdb-error-messages/localdb-error-unknown-version.md)  
 <span data-ttu-id="eef77-128">La version spécifiée n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="eef77-128">The specified version is not available.</span></span>  
  
 [<span data-ttu-id="eef77-129">LOCALDB_ERROR_VERSION_REQUESTED_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="eef77-129">LOCALDB_ERROR_VERSION_REQUESTED_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-version-requested-not-installed.md)  
 <span data-ttu-id="eef77-130">Le niveau de correctif de logiciel spécifié n'est pas installé.</span><span class="sxs-lookup"><span data-stu-id="eef77-130">The specified patch level is not installed.</span></span>  
  
 [<span data-ttu-id="eef77-131">LOCALDB_ERROR_CANNOT_CREATE_INSTANCE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="eef77-131">LOCALDB_ERROR_CANNOT_CREATE_INSTANCE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-create-instance-folder.md)  
 <span data-ttu-id="eef77-132">Impossible de créer un dossier sous %userprofile%.</span><span class="sxs-lookup"><span data-stu-id="eef77-132">A folder cannot be created under %userprofile%.</span></span>  
  
 [<span data-ttu-id="eef77-133">LOCALDB_ERROR_CANNOT_GET_USER_PROFILE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="eef77-133">LOCALDB_ERROR_CANNOT_GET_USER_PROFILE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-get-user-profile-folder.md)  
 <span data-ttu-id="eef77-134">Impossible de récupérer un dossier du profil utilisateur.</span><span class="sxs-lookup"><span data-stu-id="eef77-134">A user profile folder cannot be retrieved.</span></span>  
  
 [<span data-ttu-id="eef77-135">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="eef77-135">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-folder.md)  
 <span data-ttu-id="eef77-136">Un dossier d'instance n'est pas accessible.</span><span class="sxs-lookup"><span data-stu-id="eef77-136">An instance folder cannot be accessed.</span></span>  
  
 [<span data-ttu-id="eef77-137">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="eef77-137">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-registry.md)  
 <span data-ttu-id="eef77-138">Un Registre d'instance n'est pas accessible.</span><span class="sxs-lookup"><span data-stu-id="eef77-138">An instance registry cannot be accessed.</span></span>  
  
 [<span data-ttu-id="eef77-139">LOCALDB_ERROR_CANNOT_MODIFY_INSTANCE_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="eef77-139">LOCALDB_ERROR_CANNOT_MODIFY_INSTANCE_REGISTRY</span></span>](../express-localdb-error-messages/localdb-error-cannot-modify-instance-registry.md)  
 <span data-ttu-id="eef77-140">Impossible de modifier un Registre d'instance.</span><span class="sxs-lookup"><span data-stu-id="eef77-140">An instance registry cannot be modified.</span></span>  
  
 [<span data-ttu-id="eef77-141">LOCALDB_ERROR_SQL_SERVER_STARTUP_FAILED</span><span class="sxs-lookup"><span data-stu-id="eef77-141">LOCALDB_ERROR_SQL_SERVER_STARTUP_FAILED</span></span>](../express-localdb-error-messages/localdb-error-sql-server-startup-failed.md)  
 <span data-ttu-id="eef77-142">Un processus SQL Server est démarré, mais le démarrage de SQL Server a échoué.</span><span class="sxs-lookup"><span data-stu-id="eef77-142">A SQL Server process is started but SQL Server startup failed.</span></span>  
  
 [<span data-ttu-id="eef77-143">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span><span class="sxs-lookup"><span data-stu-id="eef77-143">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span></span>](../express-localdb-error-messages/localdb-error-instance-configuration-corrupt.md)  
 <span data-ttu-id="eef77-144">Une configuration d'instance est endommagée.</span><span class="sxs-lookup"><span data-stu-id="eef77-144">An instance configuration is corrupted.</span></span>  
  
 [<span data-ttu-id="eef77-145">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="eef77-145">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="eef77-146">Une erreur inattendue s’est produite.</span><span class="sxs-lookup"><span data-stu-id="eef77-146">An unexpected error occurred.</span></span> <span data-ttu-id="eef77-147">Pour plus d'informations, consultez le journal des événements.</span><span class="sxs-lookup"><span data-stu-id="eef77-147">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eef77-148">Notes</span><span class="sxs-lookup"><span data-stu-id="eef77-148">Remarks</span></span>  
 <span data-ttu-id="eef77-149">Si une instance de LocalDB entièrement fonctionnelle portant le nom spécifié existe déjà et sa version est supérieure ou égale à la version demandée, le résultat est S_OK.</span><span class="sxs-lookup"><span data-stu-id="eef77-149">If a fully functional LocalDB instance with the specified name already exists and its version is equal to or higher than requested, the result is S_OK.</span></span>  
  
 <span data-ttu-id="eef77-150">Dans les cas où une instance existante est endommagée, les appels suivants à la méthode d'API `LocalDBCreateInstance` échouent.</span><span class="sxs-lookup"><span data-stu-id="eef77-150">In cases when an existing instance becomes corrupted, subsequent calls to the `LocalDBCreateInstance` API method will fail.</span></span> <span data-ttu-id="eef77-151">Les instances endommagées doivent être corrigées manuellement ou être explicitement supprimées avant de pouvoir être réutilisées.</span><span class="sxs-lookup"><span data-stu-id="eef77-151">Corrupted instances must be fixed manually or explicitly deleted before they can be used again.</span></span>  
  
 <span data-ttu-id="eef77-152">Pour un exemple de code qui utilise l'API LocalDB, consultez [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="eef77-152">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eef77-153">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="eef77-153">See Also</span></span>  
 [<span data-ttu-id="eef77-154">En-tête et informations de version SQL Server Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="eef77-154">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
