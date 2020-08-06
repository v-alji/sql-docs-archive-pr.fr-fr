---
title: LocalDBStartInstance fonction) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBStartInstance
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: cb325f5d-10ee-4a56-ba28-db0074ab3926
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 748bc373e8b0dbad0a91247e068d21b67f2dbc1a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614079"
---
# <a name="localdbstartinstance-function"></a><span data-ttu-id="35bc1-102">Fonction LocalDBStartInstance</span><span class="sxs-lookup"><span data-stu-id="35bc1-102">LocalDBStartInstance Function</span></span>
  <span data-ttu-id="35bc1-103">Démarre l'instance SQL Server Express LocalDB spécifiée.</span><span class="sxs-lookup"><span data-stu-id="35bc1-103">Starts the specified SQL Server Express LocalDB instance.</span></span>  
  
 <span data-ttu-id="35bc1-104">**Fichier d'en-tête :** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="35bc1-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35bc1-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="35bc1-105">Syntax</span></span>  
  
```  
HRESULT LocalDBStartInstance(  
           PCWSTR pInstanceName,  
           DWORD dwFlags,   
           LPWSTR wszSqlConnection,   
           LPDWORD lpcchSqlConnection   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="35bc1-106">Paramètres</span><span class="sxs-lookup"><span data-stu-id="35bc1-106">Parameters</span></span>  
 <span data-ttu-id="35bc1-107">*pInstanceName*</span><span class="sxs-lookup"><span data-stu-id="35bc1-107">*pInstanceName*</span></span>  
 <span data-ttu-id="35bc1-108">[Entrée] Nom de l'instance de LocalDB à démarrer.</span><span class="sxs-lookup"><span data-stu-id="35bc1-108">[Input] The name of the LocalDB instance to start.</span></span>  
  
 <span data-ttu-id="35bc1-109">*dwFlags*</span><span class="sxs-lookup"><span data-stu-id="35bc1-109">*dwFlags*</span></span>  
 <span data-ttu-id="35bc1-110">[Entrée] Réservé à un usage ultérieur.</span><span class="sxs-lookup"><span data-stu-id="35bc1-110">[Input] Reserved for future use.</span></span> <span data-ttu-id="35bc1-111">Actuellement doit avoir la valeur 0.</span><span class="sxs-lookup"><span data-stu-id="35bc1-111">Currently should be set to 0.</span></span>  
  
 <span data-ttu-id="35bc1-112">*wszSqlConnection*</span><span class="sxs-lookup"><span data-stu-id="35bc1-112">*wszSqlConnection*</span></span>  
 <span data-ttu-id="35bc1-113">[Sortie] Mémoire tampon pour stocker la chaîne de connexion à l'instance de LocalDB.</span><span class="sxs-lookup"><span data-stu-id="35bc1-113">[Output] The buffer to store the connection string to the LocalDB instance.</span></span>  
  
 <span data-ttu-id="35bc1-114">*lpcchSqlConnection*</span><span class="sxs-lookup"><span data-stu-id="35bc1-114">*lpcchSqlConnection*</span></span>  
 <span data-ttu-id="35bc1-115">[Entrée/sortie] En entrée contient la taille de la mémoire tampon de *wszSqlConnection* en caractères, y compris les zéros de fin.</span><span class="sxs-lookup"><span data-stu-id="35bc1-115">[Input/Output] On input contains the size of the *wszSqlConnection* buffer in characters, including any trailing nulls.</span></span> <span data-ttu-id="35bc1-116">En sortie, si la taille de la mémoire tampon donnée est trop petite, contient la taille de la mémoire tampon requise en caractères, y compris les zéros de fin.</span><span class="sxs-lookup"><span data-stu-id="35bc1-116">On output, if the given buffer size is too small, contains the required buffer size in characters, including any trailing nulls.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="35bc1-117">Retours</span><span class="sxs-lookup"><span data-stu-id="35bc1-117">Returns</span></span>  
 <span data-ttu-id="35bc1-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="35bc1-118">S_OK</span></span>  
 <span data-ttu-id="35bc1-119">La fonction a réussi.</span><span class="sxs-lookup"><span data-stu-id="35bc1-119">The function succeeded.</span></span>  
  
 [<span data-ttu-id="35bc1-120">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="35bc1-120">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="35bc1-121">SQL Server Express LocalDB n'est pas installé sur l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="35bc1-121">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="35bc1-122">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="35bc1-122">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="35bc1-123">Un ou plusieurs paramètres d'entrée spécifiés ne sont pas valides.</span><span class="sxs-lookup"><span data-stu-id="35bc1-123">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="35bc1-124">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span><span class="sxs-lookup"><span data-stu-id="35bc1-124">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span></span>](../express-localdb-error-messages/localdb-error-invalid-instance-name.md)  
 <span data-ttu-id="35bc1-125">Le nom d'instance spécifié n'est pas valide.</span><span class="sxs-lookup"><span data-stu-id="35bc1-125">The specified instance name is invalid.</span></span>  
  
 [<span data-ttu-id="35bc1-126">LOCALDB_ERROR_UNKNOWN_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="35bc1-126">LOCALDB_ERROR_UNKNOWN_INSTANCE</span></span>](../express-localdb-error-messages/localdb-error-unknown-instance.md)  
 <span data-ttu-id="35bc1-127">L'instance n'existe pas.</span><span class="sxs-lookup"><span data-stu-id="35bc1-127">The instance does not exist.</span></span>  
  
 [<span data-ttu-id="35bc1-128">LOCALDB_ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="35bc1-128">LOCALDB_ERROR_INSUFFICIENT_BUFFER</span></span>](../express-localdb-error-messages/localdb-error-insufficient-buffer.md)  
 <span data-ttu-id="35bc1-129">Le tampon de *wszSqlConnection* spécifié est trop petit.</span><span class="sxs-lookup"><span data-stu-id="35bc1-129">The specified buffer *wszSqlConnection* is too small.</span></span>  
  
 [<span data-ttu-id="35bc1-130">LOCALDB_ERROR_WAIT_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="35bc1-130">LOCALDB_ERROR_WAIT_TIMEOUT</span></span>](../express-localdb-error-messages/localdb-error-wait-timeout.md)  
 <span data-ttu-id="35bc1-131">Un dépassement de délai s'est produit lors de la tentative d'acquisition des verrous de synchronisation.</span><span class="sxs-lookup"><span data-stu-id="35bc1-131">A time-out occurred while trying to acquire the synchronization locks.</span></span>  
  
 [<span data-ttu-id="35bc1-132">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span><span class="sxs-lookup"><span data-stu-id="35bc1-132">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span></span>](../express-localdb-error-messages/localdb-error-instance-folder-path-too-long.md)  
 <span data-ttu-id="35bc1-133">Le chemin d'accès où l'instance doit être stockée est plus long que MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="35bc1-133">The path where the instance should be stored is longer than MAX_PATH.</span></span>  
  
 [<span data-ttu-id="35bc1-134">LOCALDB_ERROR_CANNOT_GET_USER_PROFILE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="35bc1-134">LOCALDB_ERROR_CANNOT_GET_USER_PROFILE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-get-user-profile-folder.md)  
 <span data-ttu-id="35bc1-135">Impossible de récupérer un dossier du profil utilisateur.</span><span class="sxs-lookup"><span data-stu-id="35bc1-135">A user profile folder cannot be retrieved.</span></span>  
  
 [<span data-ttu-id="35bc1-136">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="35bc1-136">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-folder.md)  
 <span data-ttu-id="35bc1-137">Un dossier d'instance n'est pas accessible.</span><span class="sxs-lookup"><span data-stu-id="35bc1-137">An instance folder cannot be accessed.</span></span>  
  
 [<span data-ttu-id="35bc1-138">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="35bc1-138">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-registry.md)  
 <span data-ttu-id="35bc1-139">Un Registre d'instance n'est pas accessible.</span><span class="sxs-lookup"><span data-stu-id="35bc1-139">An instance registry cannot be accessed.</span></span>  
  
 [<span data-ttu-id="35bc1-140">LOCALDB_ERROR_CANNOT_MODIFY_INSTANCE_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="35bc1-140">LOCALDB_ERROR_CANNOT_MODIFY_INSTANCE_REGISTRY</span></span>](../express-localdb-error-messages/localdb-error-cannot-modify-instance-registry.md)  
 <span data-ttu-id="35bc1-141">Impossible de modifier un Registre d'instance.</span><span class="sxs-lookup"><span data-stu-id="35bc1-141">An instance registry cannot be modified.</span></span>  
  
 [<span data-ttu-id="35bc1-142">LOCALDB_ERROR_CANNOT_CREATE_SQL_PROCESS</span><span class="sxs-lookup"><span data-stu-id="35bc1-142">LOCALDB_ERROR_CANNOT_CREATE_SQL_PROCESS</span></span>](../express-localdb-error-messages/localdb-error-cannot-create-sql-process.md)  
 <span data-ttu-id="35bc1-143">Impossible de créer un processus pour SQL Server.</span><span class="sxs-lookup"><span data-stu-id="35bc1-143">A process for SQL Server cannot be created.</span></span>  
  
 [<span data-ttu-id="35bc1-144">LOCALDB_ERROR_SQL_SERVER_STARTUP_FAILED</span><span class="sxs-lookup"><span data-stu-id="35bc1-144">LOCALDB_ERROR_SQL_SERVER_STARTUP_FAILED</span></span>](../express-localdb-error-messages/localdb-error-sql-server-startup-failed.md)  
 <span data-ttu-id="35bc1-145">Un processus SQL Server a été démarré, mais le démarrage de SQL Server a échoué.</span><span class="sxs-lookup"><span data-stu-id="35bc1-145">A SQL Server process was started, but SQL Server startup failed.</span></span>  
  
 [<span data-ttu-id="35bc1-146">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span><span class="sxs-lookup"><span data-stu-id="35bc1-146">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span></span>](../express-localdb-error-messages/localdb-error-instance-configuration-corrupt.md)  
 <span data-ttu-id="35bc1-147">Une configuration d'instance a été endommagée.</span><span class="sxs-lookup"><span data-stu-id="35bc1-147">An instance configuration was corrupted.</span></span>  
  
 [<span data-ttu-id="35bc1-148">LOCALDB_ERROR_AUTO_INSTANCE_CREATE_FAILED</span><span class="sxs-lookup"><span data-stu-id="35bc1-148">LOCALDB_ERROR_AUTO_INSTANCE_CREATE_FAILED</span></span>](../express-localdb-error-messages/localdb-error-auto-instance-create-failed.md)  
 <span data-ttu-id="35bc1-149">Impossible de créer une instance automatique.</span><span class="sxs-lookup"><span data-stu-id="35bc1-149">Cannot create an automatic instance.</span></span> <span data-ttu-id="35bc1-150">Pour plus d'informations sur l'erreur, consultez le journal des événements des applications Windows.</span><span class="sxs-lookup"><span data-stu-id="35bc1-150">See the Windows Application event log for error details.</span></span>  
  
 [<span data-ttu-id="35bc1-151">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="35bc1-151">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="35bc1-152">Une erreur inattendue s’est produite.</span><span class="sxs-lookup"><span data-stu-id="35bc1-152">An unexpected error occurred.</span></span> <span data-ttu-id="35bc1-153">Pour plus d'informations, consultez le journal des événements.</span><span class="sxs-lookup"><span data-stu-id="35bc1-153">See the event log for details.</span></span>  
  
## <a name="details"></a><span data-ttu-id="35bc1-154">Détails</span><span class="sxs-lookup"><span data-stu-id="35bc1-154">Details</span></span>  
 <span data-ttu-id="35bc1-155">L'argument de mémoire tampon de connexion (*wszSqlConnection*) et l'argument de taille de mémoire tampon de connexion (*lpcchSqlConnection*) sont facultatifs.</span><span class="sxs-lookup"><span data-stu-id="35bc1-155">Both the connection buffer argument (*wszSqlConnection*) and the connection buffer size argument (*lpcchSqlConnection*) are optional.</span></span> <span data-ttu-id="35bc1-156">Le tableau suivant affiche les options d'utilisation de ces arguments et leurs résultats.</span><span class="sxs-lookup"><span data-stu-id="35bc1-156">The following table shows options for using these arguments and their results.</span></span>  
  
|<span data-ttu-id="35bc1-157">Buffer</span><span class="sxs-lookup"><span data-stu-id="35bc1-157">Buffer</span></span>|<span data-ttu-id="35bc1-158">buffer_size</span><span class="sxs-lookup"><span data-stu-id="35bc1-158">Buffer size</span></span>|<span data-ttu-id="35bc1-159">Rationale</span><span class="sxs-lookup"><span data-stu-id="35bc1-159">Rationale</span></span>|<span data-ttu-id="35bc1-160">Action</span><span class="sxs-lookup"><span data-stu-id="35bc1-160">Action</span></span>|  
|------------|-----------------|---------------|------------|  
|<span data-ttu-id="35bc1-161">NULL</span><span class="sxs-lookup"><span data-stu-id="35bc1-161">NULL</span></span>|<span data-ttu-id="35bc1-162">NULL</span><span class="sxs-lookup"><span data-stu-id="35bc1-162">NULL</span></span>|<span data-ttu-id="35bc1-163">L’utilisateur veut démarrer l’instance et n’a pas besoin d’un nom de canal.</span><span class="sxs-lookup"><span data-stu-id="35bc1-163">User wants to start the instance and doesn't need a pipe name.</span></span>|<span data-ttu-id="35bc1-164">Démarre une instance (aucun retour de canal et aucun retour obligatoire de taille de mémoire tampon).</span><span class="sxs-lookup"><span data-stu-id="35bc1-164">Starts an instance (no pipe return and no required buffer size return).</span></span>|  
|<span data-ttu-id="35bc1-165">NULL</span><span class="sxs-lookup"><span data-stu-id="35bc1-165">NULL</span></span>|<span data-ttu-id="35bc1-166">Présent</span><span class="sxs-lookup"><span data-stu-id="35bc1-166">Present</span></span>|<span data-ttu-id="35bc1-167">L'utilisateur demande la taille de la mémoire tampon de sortie.</span><span class="sxs-lookup"><span data-stu-id="35bc1-167">User asks for the output buffer size.</span></span> <span data-ttu-id="35bc1-168">(Dans l'appel suivant l'utilisateur demandera probablement un début réel.)</span><span class="sxs-lookup"><span data-stu-id="35bc1-168">(In the next call the user will probably ask for an actual start.)</span></span>|<span data-ttu-id="35bc1-169">Retourne une taille de mémoire tampon requise (aucun début et aucun retour de canal).</span><span class="sxs-lookup"><span data-stu-id="35bc1-169">Returns a required buffer size (no start and no pipe return).</span></span> <span data-ttu-id="35bc1-170">Le résultat est S_OK.</span><span class="sxs-lookup"><span data-stu-id="35bc1-170">Result is S_OK.</span></span>|  
|<span data-ttu-id="35bc1-171">Présent</span><span class="sxs-lookup"><span data-stu-id="35bc1-171">Present</span></span>|<span data-ttu-id="35bc1-172">NULL</span><span class="sxs-lookup"><span data-stu-id="35bc1-172">NULL</span></span>|<span data-ttu-id="35bc1-173">Non autorisé ; entrée incorrecte.</span><span class="sxs-lookup"><span data-stu-id="35bc1-173">Not allowed; incorrect input.</span></span>|<span data-ttu-id="35bc1-174">LOCALDB_ERROR_INVALID_PARAMETER est retourné.</span><span class="sxs-lookup"><span data-stu-id="35bc1-174">Returned result is LOCALDB_ERROR_INVALID_PARAMETER.</span></span>|  
|<span data-ttu-id="35bc1-175">Présent</span><span class="sxs-lookup"><span data-stu-id="35bc1-175">Present</span></span>|<span data-ttu-id="35bc1-176">Présent</span><span class="sxs-lookup"><span data-stu-id="35bc1-176">Present</span></span>|<span data-ttu-id="35bc1-177">L'utilisateur veut démarrer l'instance et a besoin du nom de canal pour s'y connecter après qu'il a été démarré.</span><span class="sxs-lookup"><span data-stu-id="35bc1-177">User wants to start the instance and needs the pipe name to connect to it after it is started.</span></span>|<span data-ttu-id="35bc1-178">Vérifie la taille de la mémoire tampon, démarre l'instance, puis retourne le nom de canal dans la mémoire tampon.</span><span class="sxs-lookup"><span data-stu-id="35bc1-178">Checks the buffer size, starts the instance, and returns the pipe name in the buffer.</span></span> <br /><span data-ttu-id="35bc1-179">L’argument de taille de mémoire tampon retourne la longueur de la chaîne « Server = », sans inclure les valeurs null de fin.</span><span class="sxs-lookup"><span data-stu-id="35bc1-179">The buffer size argument returns the length of the "server=" string, not including terminating nulls.</span></span>|  
  
 <span data-ttu-id="35bc1-180">Pour un exemple de code qui utilise l'API LocalDB, consultez [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="35bc1-180">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35bc1-181">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="35bc1-181">See Also</span></span>  
 [<span data-ttu-id="35bc1-182">En-tête et informations de version SQL Server Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="35bc1-182">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
