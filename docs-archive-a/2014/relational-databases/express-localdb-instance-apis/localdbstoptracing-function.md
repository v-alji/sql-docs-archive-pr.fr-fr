---
title: LocalDBStopTracing fonction) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBStopTracing
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: 1d50e040-8602-4ffa-be8f-b8633fdfa7ff
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 2bf6051fe8c86728c2ebf0a0b2bc34fabb98edb9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601475"
---
# <a name="localdbstoptracing-function"></a><span data-ttu-id="8614e-102">Fonction LocalDBStopTracing</span><span class="sxs-lookup"><span data-stu-id="8614e-102">LocalDBStopTracing Function</span></span>
  <span data-ttu-id="8614e-103">Désactive le suivi des appels d'API pour toutes les instances SQL Server Express LocalDB détenues par l'utilisateur Windows actuel.</span><span class="sxs-lookup"><span data-stu-id="8614e-103">Disables tracing of API calls for all the SQL Server Express LocalDB instances owned by the current Windows user.</span></span>  
  
 <span data-ttu-id="8614e-104">**Fichier d'en-tête :** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="8614e-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8614e-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="8614e-105">Syntax</span></span>  
  
```  
HRESULT LocalDBStopTracing();  
```  
  
## <a name="returns"></a><span data-ttu-id="8614e-106">Retours</span><span class="sxs-lookup"><span data-stu-id="8614e-106">Returns</span></span>  
 <span data-ttu-id="8614e-107">S_OK</span><span class="sxs-lookup"><span data-stu-id="8614e-107">S_OK</span></span>  
 <span data-ttu-id="8614e-108">La fonction a réussi.</span><span class="sxs-lookup"><span data-stu-id="8614e-108">The function succeeded.</span></span>  
  
 [<span data-ttu-id="8614e-109">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="8614e-109">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="8614e-110">Une erreur inattendue s’est produite.</span><span class="sxs-lookup"><span data-stu-id="8614e-110">An unexpected error occurred.</span></span> <span data-ttu-id="8614e-111">Pour plus d'informations, consultez le journal des événements.</span><span class="sxs-lookup"><span data-stu-id="8614e-111">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8614e-112">Notes</span><span class="sxs-lookup"><span data-stu-id="8614e-112">Remarks</span></span>  
 <span data-ttu-id="8614e-113">Pour un exemple de code qui utilise l'API LocalDB, consultez [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="8614e-113">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8614e-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8614e-114">See Also</span></span>  
 [<span data-ttu-id="8614e-115">En-tête et informations de version SQL Server Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="8614e-115">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
