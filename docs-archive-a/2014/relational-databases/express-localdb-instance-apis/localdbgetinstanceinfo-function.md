---
title: LocalDBGetInstanceInfo fonction) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBGetInstanceInfo
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: 231706f5-26c6-42eb-ab47-315df6b8f824
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: dc7cbe2c59a7502a1fd0c8b4f92fb14e5defd50b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602848"
---
# <a name="localdbgetinstanceinfo-function"></a><span data-ttu-id="466d2-102">Fonction LocalDBGetInstanceInfo</span><span class="sxs-lookup"><span data-stu-id="466d2-102">LocalDBGetInstanceInfo Function</span></span>
  <span data-ttu-id="466d2-103">Retourne des informations pour l'instance de base de données locale SQL Server Express (LocalDB) spécifiée, entre autres si elle existe, la version de LocalDB qu'elle utilise, si elle s'exécute, et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="466d2-103">Returns information for the specified SQL Server Express LocalDB instance, such as whether it exists, the LocalDB version it uses, whether it is running, and so on.</span></span>  
  
 <span data-ttu-id="466d2-104">Les informations sont retournées dans un `struct` **LocalDBInstanceInfo**nommé, qui a la définition suivante.</span><span class="sxs-lookup"><span data-stu-id="466d2-104">The information is returned in a `struct` named **LocalDBInstanceInfo**, which has the following definition.</span></span>  
  
```  
typedef struct _LocalDBInstanceInfo  
{  
      // Contains the size of the LocalDBInstanceInfo struct  
      DWORD  cbLocalDBInstanceInfoSize;  
  
      // Holds the instance name  
      TLocalDBInstanceNamewszInstanceName;  
  
      // TRUE if the instance files exist on disk, FALSE otherwise  
      BOOL   bExists;  
  
      // TRUE if the instance configuration registry is corrupted, FALSE otherwise  
      BOOLbConfigurationCorrupted;  
  
      // TRUE if the instance is running at the moment, FALSE otherwise  
      BOOL   bIsRunning;  
  
      // Holds the LocalDB version for the instance in the format: major.minor.build.revision  
      DWORD  dwMajor;  
      DWORD  dwMinor;  
      DWORD  dwBuild;  
      DWORD  dwRevision;  
  
      // Holds the date and time when the instance was started for the last time  
      FILETIME ftLastStartUTC;  
  
      // Holds the name of the TDS named pipe to connect to the instance  
      WCHARwszConnection;  
  
      // TRUE if the instance is shared, FALSE otherwise  
      BOOLbIsShared;  
  
      // Holds the shared name for the instance (if the instance is shared)  
      TLocalDBInstanceNamewszSharedInstanceName;  
  
      // Holds the SID of the instance owner (if the instance is shared)  
      WCHARwszOwnerSID;   
  
      // TRUE if the instance is Automatic, FALSE otherwise  
      BOOLbIsAutomatic;  
} LocalDBInstanceInfo;  
  
```  
  
 <span data-ttu-id="466d2-105">**Fichier d'en-tête :** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="466d2-105">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="466d2-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="466d2-106">Syntax</span></span>  
  
```  
HRESULT LocalDBGetInstanceInfo(  
           PCWSTR wszInstanceName,  
           PLocalDBInstanceInfo pInstanceInfo,  
           DWORD dwInstanceInfoSize   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="466d2-107">Paramètres</span><span class="sxs-lookup"><span data-stu-id="466d2-107">Parameters</span></span>  
 <span data-ttu-id="466d2-108">*wszInstanceName*</span><span class="sxs-lookup"><span data-stu-id="466d2-108">*wszInstanceName*</span></span>  
 <span data-ttu-id="466d2-109">[Entrée] Nom de l'instance.</span><span class="sxs-lookup"><span data-stu-id="466d2-109">[Input] The instance name.</span></span>  
  
 <span data-ttu-id="466d2-110">*pInstanceInfo*</span><span class="sxs-lookup"><span data-stu-id="466d2-110">*pInstanceInfo*</span></span>  
 <span data-ttu-id="466d2-111">[Sortie] La mémoire tampon pour stocker des informations sur l'instance de LocalDB.</span><span class="sxs-lookup"><span data-stu-id="466d2-111">[Output] The buffer to store the information about the LocalDB instance.</span></span>  
  
 <span data-ttu-id="466d2-112">*dwInstanceInfoSize*</span><span class="sxs-lookup"><span data-stu-id="466d2-112">*dwInstanceInfoSize*</span></span>  
 <span data-ttu-id="466d2-113">Entrée Contient la taille de la mémoire tampon *InstanceInfo* .</span><span class="sxs-lookup"><span data-stu-id="466d2-113">[Input] Holds the size of the *InstanceInfo* buffer.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="466d2-114">Retours</span><span class="sxs-lookup"><span data-stu-id="466d2-114">Returns</span></span>  
 <span data-ttu-id="466d2-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="466d2-115">S_OK</span></span>  
 <span data-ttu-id="466d2-116">La fonction a réussi.</span><span class="sxs-lookup"><span data-stu-id="466d2-116">The function succeeded.</span></span>  
  
 [<span data-ttu-id="466d2-117">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="466d2-117">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="466d2-118">SQL Server Express LocalDB n'est pas installé sur l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="466d2-118">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="466d2-119">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="466d2-119">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="466d2-120">Un ou plusieurs paramètres d'entrée spécifiés ne sont pas valides.</span><span class="sxs-lookup"><span data-stu-id="466d2-120">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="466d2-121">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span><span class="sxs-lookup"><span data-stu-id="466d2-121">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span></span>](../express-localdb-error-messages/localdb-error-invalid-instance-name.md)  
 <span data-ttu-id="466d2-122">Le nom d'instance spécifié n'est pas valide.</span><span class="sxs-lookup"><span data-stu-id="466d2-122">The specified instance name is invalid.</span></span>  
  
 [<span data-ttu-id="466d2-123">LOCALDB_ERROR_UNKNOWN_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="466d2-123">LOCALDB_ERROR_UNKNOWN_INSTANCE</span></span>](../express-localdb-error-messages/localdb-error-unknown-instance.md)  
 <span data-ttu-id="466d2-124">L'instance n'existe pas.</span><span class="sxs-lookup"><span data-stu-id="466d2-124">The instance does not exist.</span></span>  
  
 [<span data-ttu-id="466d2-125">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span><span class="sxs-lookup"><span data-stu-id="466d2-125">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span></span>](../express-localdb-error-messages/localdb-error-instance-folder-path-too-long.md)  
 <span data-ttu-id="466d2-126">Le chemin d'accès où l'instance doit être stockée est plus long que MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="466d2-126">The path where the instance should be stored is longer than MAX_PATH.</span></span>  
  
 [<span data-ttu-id="466d2-127">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="466d2-127">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-folder.md)  
 <span data-ttu-id="466d2-128">Un dossier d'instance n'est pas accessible.</span><span class="sxs-lookup"><span data-stu-id="466d2-128">An instance folder cannot be accessed.</span></span>  
  
 [<span data-ttu-id="466d2-129">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="466d2-129">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-registry.md)  
 <span data-ttu-id="466d2-130">Un Registre d'instance n'est pas accessible.</span><span class="sxs-lookup"><span data-stu-id="466d2-130">An instance registry cannot be accessed.</span></span>  
  
 [<span data-ttu-id="466d2-131">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span><span class="sxs-lookup"><span data-stu-id="466d2-131">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span></span>](../express-localdb-error-messages/localdb-error-instance-configuration-corrupt.md)  
 <span data-ttu-id="466d2-132">Une configuration d'instance est endommagée.</span><span class="sxs-lookup"><span data-stu-id="466d2-132">An instance configuration is corrupted.</span></span>  
  
 [<span data-ttu-id="466d2-133">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="466d2-133">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="466d2-134">Une erreur inattendue s’est produite.</span><span class="sxs-lookup"><span data-stu-id="466d2-134">An unexpected error occurred.</span></span> <span data-ttu-id="466d2-135">Pour plus d'informations, consultez le journal des événements.</span><span class="sxs-lookup"><span data-stu-id="466d2-135">See the event log for details.</span></span>  
  
## <a name="details"></a><span data-ttu-id="466d2-136">Détails</span><span class="sxs-lookup"><span data-stu-id="466d2-136">Details</span></span>  
 <span data-ttu-id="466d2-137">Le raisonnement derrière l’introduction de l' `struct` argument de taille (*lpInstanceInfoSize*) consiste à permettre à l’API de retourner différentes versions du **LocalDBInstanceInfostruct**, ce qui permet une compatibilité ascendante et descendante.</span><span class="sxs-lookup"><span data-stu-id="466d2-137">The rationale behind the introduction of the `struct` size argument (*lpInstanceInfoSize*) is to enable the API to return different versions of the **LocalDBInstanceInfostruct**, effectively enabling forward and backward compatibility.</span></span>  
  
 <span data-ttu-id="466d2-138">Si l' `struct` argument de taille (*lpInstanceInfoSize*) correspond à la taille d’une version connue du **LocalDBInstanceInfostruct**, cette version de `struct` est retournée.</span><span class="sxs-lookup"><span data-stu-id="466d2-138">If the `struct` size argument (*lpInstanceInfoSize*) matches the size of a known version of the **LocalDBInstanceInfostruct**, that version of the `struct` is returned.</span></span> <span data-ttu-id="466d2-139">Sinon, LOCALDB_ERROR_INVALID_PARAMETER est retourné.</span><span class="sxs-lookup"><span data-stu-id="466d2-139">Otherwise, LOCALDB_ERROR_INVALID_PARAMETER is returned.</span></span>  
  
 <span data-ttu-id="466d2-140">Voici un exemple typique d’utilisation de l’API **LocalDBGetInstanceInfo** :</span><span class="sxs-lookup"><span data-stu-id="466d2-140">A typical example of **LocalDBGetInstanceInfo** API usage looks like this:</span></span>  
  
```  
LocalDBInstanceInfo ii;  
LocalDBInstanceInfo(L"Test", &ii, sizeof(LocalDBInstanceInfo));  
  
```  
  
 <span data-ttu-id="466d2-141">Pour un exemple de code qui utilise l'API LocalDB, consultez [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="466d2-141">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="466d2-142">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="466d2-142">See Also</span></span>  
 [<span data-ttu-id="466d2-143">En-tête et informations de version SQL Server Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="466d2-143">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
