---
title: LocalDBGetInstances fonction) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBGetInstances
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: f95a9980-8bc0-426c-8aa1-e2660b6784cf
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 4a6f758bd647fd69a14f72a0651bb3e2e33a7c79
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695616"
---
# <a name="localdbgetinstances-function"></a><span data-ttu-id="48d6d-102">Fonction LocalDBGetInstances</span><span class="sxs-lookup"><span data-stu-id="48d6d-102">LocalDBGetInstances Function</span></span>
  <span data-ttu-id="48d6d-103">Retourne toutes les instances de SQL Server Express LocalDB avec la version donnée.</span><span class="sxs-lookup"><span data-stu-id="48d6d-103">Returns all SQL Server Express LocalDB instances with the given version.</span></span>  
  
 <span data-ttu-id="48d6d-104">**Fichier d'en-tête :** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="48d6d-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48d6d-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="48d6d-105">Syntax</span></span>  
  
```  
#define MAX_LOCALDB_INSTANCE_NAME_LENGTH 128typedef WCHAR TLocalDBInstanceName[MAX_LOCALDB_INSTANCE_NAME_LENGTH + 1];typedef TLocalDBInstanceName* PTLocalDBInstanceName;  
HRESULT LocalDBGetInstances(  
           PTLocalDBInstanceName pInstanceNames,  
           LPDWORD lpdwNumberOfInstances  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48d6d-106">Paramètres</span><span class="sxs-lookup"><span data-stu-id="48d6d-106">Parameters</span></span>  
 <span data-ttu-id="48d6d-107">*pInstanceNames*</span><span class="sxs-lookup"><span data-stu-id="48d6d-107">*pInstanceNames*</span></span>  
 <span data-ttu-id="48d6d-108">Sortie Lorsque cette fonction est retournée, contient les noms des instances de base de données locale nommées et par défaut sur la station de travail de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="48d6d-108">[Output] When this function returns, contains the names of both named and default LocalDB instances on the user's workstation.</span></span>  
  
 <span data-ttu-id="48d6d-109">*lpdwNumberOfInstances*</span><span class="sxs-lookup"><span data-stu-id="48d6d-109">*lpdwNumberOfInstances*</span></span>  
 <span data-ttu-id="48d6d-110">[Entrée/sortie] En entrée, contient le nombre d'emplacements de noms d'instances dans la mémoire tampon de *pInstanceNames* .</span><span class="sxs-lookup"><span data-stu-id="48d6d-110">[Input/Output] On input, contains the number of slots for instance names in the *pInstanceNames* buffer.</span></span> <span data-ttu-id="48d6d-111">En sortie, contient le nombre d’instances de base de données locale trouvées sur la station de travail de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="48d6d-111">On output, contains the number of LocalDB instances found on the user's workstation.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="48d6d-112">Retours</span><span class="sxs-lookup"><span data-stu-id="48d6d-112">Returns</span></span>  
 <span data-ttu-id="48d6d-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="48d6d-113">S_OK</span></span>  
 <span data-ttu-id="48d6d-114">La fonction a réussi.</span><span class="sxs-lookup"><span data-stu-id="48d6d-114">The function succeeded.</span></span>  
  
 [<span data-ttu-id="48d6d-115">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="48d6d-115">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="48d6d-116">SQL Server Express LocalDB n'est pas installé sur l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="48d6d-116">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="48d6d-117">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="48d6d-117">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="48d6d-118">Un ou plusieurs paramètres d'entrée spécifiés ne sont pas valides.</span><span class="sxs-lookup"><span data-stu-id="48d6d-118">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="48d6d-119">LOCALDB_ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="48d6d-119">LOCALDB_ERROR_INSUFFICIENT_BUFFER</span></span>](../express-localdb-error-messages/localdb-error-insufficient-buffer.md)  
 <span data-ttu-id="48d6d-120">Le tampon d'entrée est trop court, et la troncation n'a pas été demandée.</span><span class="sxs-lookup"><span data-stu-id="48d6d-120">The input buffer is too short, and truncation was not requested.</span></span>  
  
 [<span data-ttu-id="48d6d-121">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span><span class="sxs-lookup"><span data-stu-id="48d6d-121">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span></span>](../express-localdb-error-messages/localdb-error-instance-folder-path-too-long.md)  
 <span data-ttu-id="48d6d-122">Le chemin d'accès où l'instance doit être stockée est plus long que MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="48d6d-122">The path where the instance should be stored is longer than MAX_PATH.</span></span>  
  
 [<span data-ttu-id="48d6d-123">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="48d6d-123">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-registry.md)  
 <span data-ttu-id="48d6d-124">Un Registre d'instance n'est pas accessible.</span><span class="sxs-lookup"><span data-stu-id="48d6d-124">An instance registry cannot be accessed.</span></span>  
  
 [<span data-ttu-id="48d6d-125">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span><span class="sxs-lookup"><span data-stu-id="48d6d-125">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span></span>](../express-localdb-error-messages/localdb-error-instance-configuration-corrupt.md)  
 <span data-ttu-id="48d6d-126">Une configuration d'instance est endommagée.</span><span class="sxs-lookup"><span data-stu-id="48d6d-126">An instance configuration is corrupted.</span></span>  
  
 [<span data-ttu-id="48d6d-127">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="48d6d-127">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="48d6d-128">Une erreur inattendue s’est produite.</span><span class="sxs-lookup"><span data-stu-id="48d6d-128">An unexpected error occurred.</span></span> <span data-ttu-id="48d6d-129">Pour plus d'informations, consultez le journal des événements.</span><span class="sxs-lookup"><span data-stu-id="48d6d-129">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="48d6d-130">Notes</span><span class="sxs-lookup"><span data-stu-id="48d6d-130">Remarks</span></span>  
 <span data-ttu-id="48d6d-131">Pour un exemple de code qui utilise l'API LocalDB, consultez [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="48d6d-131">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48d6d-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="48d6d-132">See Also</span></span>  
 [<span data-ttu-id="48d6d-133">En-tête et informations de version SQL Server Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="48d6d-133">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
