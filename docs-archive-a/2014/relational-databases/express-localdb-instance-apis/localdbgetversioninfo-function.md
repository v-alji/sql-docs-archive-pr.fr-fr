---
title: LocalDBGetVersionInfo fonction) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBGetVersionInfo
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: d4aaea30-1d0d-4436-bcdc-5c101d27b1c1
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: e30bb4dcd4c258db899883f650dbfe7100171ef8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709508"
---
# <a name="localdbgetversioninfo-function"></a><span data-ttu-id="1dc7a-102">Fonction LocalDBGetVersionInfo</span><span class="sxs-lookup"><span data-stu-id="1dc7a-102">LocalDBGetVersionInfo Function</span></span>
  <span data-ttu-id="1dc7a-103">Retourne des informations pour la version spécifiée de SQL Server Express LocalDB, notamment si elle existe, ainsi que le numéro de version complet de LocalDB (avec les numéros de build et de version).</span><span class="sxs-lookup"><span data-stu-id="1dc7a-103">Returns information for the specified SQL Server Express LocalDB version, such as whether it exists and the full LocalDB version number (including build and release numbers).</span></span>  
  
 <span data-ttu-id="1dc7a-104">Les informations sont retournées sous la forme d’un `struct` **LocalDBVersionInfo**nommé, qui a la définition suivante.</span><span class="sxs-lookup"><span data-stu-id="1dc7a-104">The information is returned in the form of a `struct` named **LocalDBVersionInfo**, which has the following definition.</span></span>  
  
```  
typedef struct _LocalDBVersionInfo  
{  
      // Contains the size of the LocalDBVersionInfo struct  
      DWORD  cbLocalDBVersionInfoSize;  
  
      // Holds the version name  
      TLocalDBVersionwszVersion;  
  
      // TRUE if the instance files exist on disk, FALSE otherwise  
      BOOL   bExists;  
  
      // Holds the LocalDB version for the instance in the format: major.minor.build.revision  
      DWORD  dwMajor;  
      DWORD  dwMinor;  
      DWORD  dwBuild;  
      DWORD  dwRevision;  
} LocalDBVersionInfo;  
  
```  
  
 <span data-ttu-id="1dc7a-105">**Fichier d'en-tête :** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="1dc7a-105">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1dc7a-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="1dc7a-106">Syntax</span></span>  
  
```  
HRESULT LocalDBGetVersionInfo(  
           PCWSTR wszVersionName,           PLocalDBVersionInfo pVersionInfo,           DWORD dwVersionInfoSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1dc7a-107">Paramètres</span><span class="sxs-lookup"><span data-stu-id="1dc7a-107">Parameters</span></span>  
 <span data-ttu-id="1dc7a-108">*wszVersionName*</span><span class="sxs-lookup"><span data-stu-id="1dc7a-108">*wszVersionName*</span></span>  
 <span data-ttu-id="1dc7a-109">[Entrée] Le nom de version de LocalDB.</span><span class="sxs-lookup"><span data-stu-id="1dc7a-109">[Input] The LocalDB version name.</span></span>  
  
 <span data-ttu-id="1dc7a-110">*pVersionInfo*</span><span class="sxs-lookup"><span data-stu-id="1dc7a-110">*pVersionInfo*</span></span>  
 <span data-ttu-id="1dc7a-111">[Sortie] La mémoire tampon pour stocker des informations sur la version de LocalDB.</span><span class="sxs-lookup"><span data-stu-id="1dc7a-111">[Output] The buffer to store the information about the LocalDB version.</span></span>  
  
 <span data-ttu-id="1dc7a-112">*dwVersionInfoSize*</span><span class="sxs-lookup"><span data-stu-id="1dc7a-112">*dwVersionInfoSize*</span></span>  
 <span data-ttu-id="1dc7a-113">Entrée Contient la taille de la mémoire tampon *VERSIONINFO* .</span><span class="sxs-lookup"><span data-stu-id="1dc7a-113">[Input] Holds the size of the *VersionInfo* buffer.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="1dc7a-114">Retours</span><span class="sxs-lookup"><span data-stu-id="1dc7a-114">Returns</span></span>  
 <span data-ttu-id="1dc7a-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="1dc7a-115">S_OK</span></span>  
 <span data-ttu-id="1dc7a-116">La fonction a réussi.</span><span class="sxs-lookup"><span data-stu-id="1dc7a-116">The function succeeded.</span></span>  
  
 [<span data-ttu-id="1dc7a-117">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="1dc7a-117">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="1dc7a-118">SQL Server Express LocalDB n'est pas installé sur l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="1dc7a-118">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="1dc7a-119">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="1dc7a-119">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="1dc7a-120">Un ou plusieurs paramètres d'entrée spécifiés ne sont pas valides.</span><span class="sxs-lookup"><span data-stu-id="1dc7a-120">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="1dc7a-121">LOCALDB_ERROR_UNKNOWN_VERSION</span><span class="sxs-lookup"><span data-stu-id="1dc7a-121">LOCALDB_ERROR_UNKNOWN_VERSION</span></span>](../express-localdb-error-messages/localdb-error-unknown-version.md)  
 <span data-ttu-id="1dc7a-122">La version spécifiée de LocalDB n'existe pas.</span><span class="sxs-lookup"><span data-stu-id="1dc7a-122">The specified LocalDB version does not exist.</span></span>  
  
 [<span data-ttu-id="1dc7a-123">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="1dc7a-123">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="1dc7a-124">Une erreur inattendue s’est produite.</span><span class="sxs-lookup"><span data-stu-id="1dc7a-124">An unexpected error occurred.</span></span> <span data-ttu-id="1dc7a-125">Pour plus d'informations, consultez le journal des événements.</span><span class="sxs-lookup"><span data-stu-id="1dc7a-125">See the event log for details.</span></span>  
  
## <a name="details"></a><span data-ttu-id="1dc7a-126">Détails</span><span class="sxs-lookup"><span data-stu-id="1dc7a-126">Details</span></span>  
 <span data-ttu-id="1dc7a-127">Le raisonnement derrière l’introduction de l' `struct` argument de taille (*lpVersionInfoSize*) consiste à permettre à l’API de retourner différentes versions du **LocalDBVersionInfostruct**, ce qui permet une compatibilité ascendante et descendante.</span><span class="sxs-lookup"><span data-stu-id="1dc7a-127">The rationale behind the introduction of the `struct` size argument (*lpVersionInfoSize*) is to enable the API to return different versions of the **LocalDBVersionInfostruct**, effectively enabling forward and backward compatibility.</span></span>  
  
 <span data-ttu-id="1dc7a-128">Si l' `struct` argument de taille (*lpVersionInfoSize*) correspond à la taille d’une version connue du **LocalDBVersionInfostruct**, cette version de `struct` est retournée.</span><span class="sxs-lookup"><span data-stu-id="1dc7a-128">If the `struct` size argument (*lpVersionInfoSize*) matches the size of a known version of the **LocalDBVersionInfostruct**, that version of the `struct` is returned.</span></span> <span data-ttu-id="1dc7a-129">Sinon, LOCALDB_ERROR_INVALID_PARAMETER est retourné.</span><span class="sxs-lookup"><span data-stu-id="1dc7a-129">Otherwise, LOCALDB_ERROR_INVALID_PARAMETER is returned.</span></span>  
  
 <span data-ttu-id="1dc7a-130">Voici un exemple typique d’utilisation de l’API **LocalDBGetVersionInfo** :</span><span class="sxs-lookup"><span data-stu-id="1dc7a-130">A typical example of **LocalDBGetVersionInfo** API usage looks like this:</span></span>  
  
```  
LocalDBVersionInfo vi;  
LocalDBVersionInfo(L"11.0", &vi, sizeof(LocalDBVersionInfo));  
  
```  
  
## <a name="remarks"></a><span data-ttu-id="1dc7a-131">Notes</span><span class="sxs-lookup"><span data-stu-id="1dc7a-131">Remarks</span></span>  
 <span data-ttu-id="1dc7a-132">Pour un exemple de code qui utilise l'API LocalDB, consultez [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="1dc7a-132">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1dc7a-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1dc7a-133">See Also</span></span>  
 [<span data-ttu-id="1dc7a-134">En-tête et informations de version SQL Server Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="1dc7a-134">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
