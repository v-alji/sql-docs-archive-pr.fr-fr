---
title: LocalDBStartTracing fonction) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBStartTracing
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: c7b83833-6d2a-4a06-9cb7-42767bed52c6
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 1b10482e9839d43e29da72dbe2c194a01d8248eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710627"
---
# <a name="localdbstarttracing-function"></a><span data-ttu-id="8fad7-102">Fonction LocalDBStartTracing</span><span class="sxs-lookup"><span data-stu-id="8fad7-102">LocalDBStartTracing Function</span></span>
  <span data-ttu-id="8fad7-103">Active le suivi des appels d'API pour toutes les instances SQL Server Express LocalDB détenues par l'utilisateur Windows actuel.</span><span class="sxs-lookup"><span data-stu-id="8fad7-103">Enables tracing of API calls for all the SQL Server Express LocalDB instances owned by the current Windows user.</span></span>  
  
 <span data-ttu-id="8fad7-104">**Fichier d'en-tête :** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="8fad7-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fad7-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="8fad7-105">Syntax</span></span>  
  
```  
HRESULT LocalDBStartTracing();  
```  
  
## <a name="returns"></a><span data-ttu-id="8fad7-106">Retours</span><span class="sxs-lookup"><span data-stu-id="8fad7-106">Returns</span></span>  
 <span data-ttu-id="8fad7-107">S_OK</span><span class="sxs-lookup"><span data-stu-id="8fad7-107">S_OK</span></span>  
 <span data-ttu-id="8fad7-108">La fonction a réussi.</span><span class="sxs-lookup"><span data-stu-id="8fad7-108">The function succeeded.</span></span>  
  
 [<span data-ttu-id="8fad7-109">LOCALDB_ERROR_XEVENT_FAILED</span><span class="sxs-lookup"><span data-stu-id="8fad7-109">LOCALDB_ERROR_XEVENT_FAILED</span></span>](../express-localdb-error-messages/localdb-error-xevent-failed.md)  
 <span data-ttu-id="8fad7-110">Échec du démarrage du moteur XEvent dans l'API de l'instance de LocalDB.</span><span class="sxs-lookup"><span data-stu-id="8fad7-110">Failed to start XEvent engine within the LocalDB Instance API.</span></span>  
  
 [<span data-ttu-id="8fad7-111">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="8fad7-111">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="8fad7-112">Une erreur inattendue s’est produite.</span><span class="sxs-lookup"><span data-stu-id="8fad7-112">An unexpected error occurred.</span></span> <span data-ttu-id="8fad7-113">Pour plus d'informations, consultez le journal des événements.</span><span class="sxs-lookup"><span data-stu-id="8fad7-113">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8fad7-114">Notes</span><span class="sxs-lookup"><span data-stu-id="8fad7-114">Remarks</span></span>  
 <span data-ttu-id="8fad7-115">Pour un exemple de code qui utilise l'API LocalDB, consultez [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="8fad7-115">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fad7-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8fad7-116">See Also</span></span>  
 [<span data-ttu-id="8fad7-117">En-tête et informations de version SQL Server Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="8fad7-117">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
