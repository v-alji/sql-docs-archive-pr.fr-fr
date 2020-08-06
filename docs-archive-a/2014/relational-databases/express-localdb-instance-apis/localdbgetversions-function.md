---
title: LocalDBGetVersions fonction) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBGetVersions
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: 033a9c6b-0d7f-4f8a-ab60-33cd6fee0d33
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 37d2a927346252f1b126f5e3a4ec78ea03cde0a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708416"
---
# <a name="localdbgetversions-function"></a><span data-ttu-id="dbea9-102">Fonction LocalDBGetVersions</span><span class="sxs-lookup"><span data-stu-id="dbea9-102">LocalDBGetVersions Function</span></span>
  <span data-ttu-id="dbea9-103">Retourne toutes les versions de SQL Server Express LocalDB disponibles sur l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="dbea9-103">Returns all SQL Server Express LocalDB versions available on the computer.</span></span>  
  
 <span data-ttu-id="dbea9-104">**Fichier d'en-tête :** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="dbea9-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbea9-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="dbea9-105">Syntax</span></span>  
  
```  
#define MAX_LOCALDB_VERSION_LENGTH 43typedef WCHAR TLocalDBVersion[MAX_LOCALDB_VERSION_LENGTH + 1];typedef TLocalDBVersion* PTLocalDBVersion;HRESULT LocalDBGetVersions(           PTLocalDBVersion pVersion,           LPDWORD lpdwNumberOfVersions);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dbea9-106">Paramètres</span><span class="sxs-lookup"><span data-stu-id="dbea9-106">Parameters</span></span>  
 <span data-ttu-id="dbea9-107">*pVersionNames*</span><span class="sxs-lookup"><span data-stu-id="dbea9-107">*pVersionNames*</span></span>  
 <span data-ttu-id="dbea9-108">Sortie Contient les noms des versions de base de données locale disponibles sur la station de travail de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="dbea9-108">[Output] Contains names of the LocalDB versions that are available on the user's workstation.</span></span>  
  
 <span data-ttu-id="dbea9-109">*lpdwNumberOfVersions*</span><span class="sxs-lookup"><span data-stu-id="dbea9-109">*lpdwNumberOfVersions*</span></span>  
 <span data-ttu-id="dbea9-110">[Entrée/sortie] En entrée, contient le nombre d'emplacements de versions dans la mémoire tampon de *pVersionNames* .</span><span class="sxs-lookup"><span data-stu-id="dbea9-110">[Input/Output] On input holds the number of slots for versions in the *pVersionNames* buffer.</span></span>   
<span data-ttu-id="dbea9-111">En sortie, contient le nombre de versions de LocalDB existantes.</span><span class="sxs-lookup"><span data-stu-id="dbea9-111">On output, holds the number of existing LocalDB versions.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="dbea9-112">Retours</span><span class="sxs-lookup"><span data-stu-id="dbea9-112">Returns</span></span>  
 <span data-ttu-id="dbea9-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="dbea9-113">S_OK</span></span>  
 <span data-ttu-id="dbea9-114">La fonction a réussi.</span><span class="sxs-lookup"><span data-stu-id="dbea9-114">The function succeeded.</span></span>  
  
 [<span data-ttu-id="dbea9-115">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="dbea9-115">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="dbea9-116">SQL Server Express LocalDB n'est pas installé sur l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="dbea9-116">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="dbea9-117">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="dbea9-117">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="dbea9-118">Un ou plusieurs paramètres d'entrée spécifiés ne sont pas valides.</span><span class="sxs-lookup"><span data-stu-id="dbea9-118">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="dbea9-119">LOCALDB_ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="dbea9-119">LOCALDB_ERROR_INSUFFICIENT_BUFFER</span></span>](../express-localdb-error-messages/localdb-error-insufficient-buffer.md)  
 <span data-ttu-id="dbea9-120">Le tampon d'entrée est trop court, et la troncation n'a pas été demandée.</span><span class="sxs-lookup"><span data-stu-id="dbea9-120">The input buffer is too short, and truncation was not requested.</span></span>  
  
 [<span data-ttu-id="dbea9-121">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="dbea9-121">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="dbea9-122">Une erreur inattendue s’est produite.</span><span class="sxs-lookup"><span data-stu-id="dbea9-122">An unexpected error occurred.</span></span> <span data-ttu-id="dbea9-123">Pour plus d'informations, consultez le journal des événements.</span><span class="sxs-lookup"><span data-stu-id="dbea9-123">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dbea9-124">Notes</span><span class="sxs-lookup"><span data-stu-id="dbea9-124">Remarks</span></span>  
 <span data-ttu-id="dbea9-125">Pour un exemple de code qui utilise l'API LocalDB, consultez [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="dbea9-125">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbea9-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="dbea9-126">See Also</span></span>  
 [<span data-ttu-id="dbea9-127">En-tête et informations de version SQL Server Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="dbea9-127">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
